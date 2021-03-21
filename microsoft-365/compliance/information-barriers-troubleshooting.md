---
title: Risoluzione dei problemi relativi alle barriere informative
description: Utilizzare questo articolo come guida per la risoluzione dei problemi relativi alle barriere di informazioni.
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: de415ba7b68df786ead038bb72465c445a86ba5a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928006"
---
# <a name="troubleshooting-information-barriers"></a>Risoluzione dei problemi relativi alle barriere informative

[Le barriere in](information-barriers.md) materia di informazioni possono aiutare l'organizzazione a rimanere conforme ai requisiti legali e alle normative del settore. Ad esempio, con le barriere alle informazioni, è possibile limitare la comunicazione tra gruppi specifici di utenti per evitare un conflitto di interesse o altri problemi. Per ulteriori informazioni su come configurare le barriere alle informazioni, vedere [Definire i criteri per le barriere di informazioni.](information-barriers-policies.md)

Nel caso in cui si verificano problemi imprevisti dopo l'applicazione delle barriere alle informazioni, è possibile eseguire alcuni passaggi per risolverli. Usa questo articolo come guida.

> [!IMPORTANT]
> Per eseguire le attività descritte in questo articolo, è necessario disporre di un ruolo appropriato, ad esempio uno dei seguenti:<br/>- Amministratore globale dell'organizzazione di Microsoft 365<br/>- Amministratore globale<br/>- Amministratore conformità<br/>- Gestione della conformità IB (questo è un nuovo ruolo!)<p>Per ulteriori informazioni sui prerequisiti per le barriere alle informazioni, vedere [Prerequisites (for information barrier policies)](information-barriers-policies.md#prerequisites).<p>Assicurarsi di [connettersi a PowerShell & Centro sicurezza e conformità.](/powershell/exchange/connect-to-scc-powershell)

## <a name="issue-users-are-unexpectedly-blocked-from-communicating-with-others-in-microsoft-teams"></a>Problema: agli utenti viene impedito in modo imprevisto di comunicare con altri utenti in Microsoft Teams 

In questo caso, gli utenti segnalano problemi imprevisti che comunicano con altri utenti in Microsoft Teams. Ecco alcuni esempi:

- Un utente cerca, ma non è in grado di trovarlo, un altro utente in Microsoft Teams.
- Un utente può trovare, ma non selezionare, un altro utente in Microsoft Teams.
- Un utente può visualizzare un altro utente, ma non può inviare messaggi a tale altro utente in Microsoft Teams.

### <a name="what-to-do"></a>Soluzione

Determinare se gli utenti sono interessati da un criterio di barriera delle informazioni. A seconda della configurazione dei criteri, le barriere alle informazioni potrebbero funzionare come previsto. In caso contrario, potrebbe essere necessario perfezionare i criteri dell'organizzazione.

1. Utilizzare il cmdlet **Get-InformationBarrierRecipientStatus** con il parametro Identity. 

    |**Sintassi**|**Esempio**|
    |:---------|:----------|
    | `Get-InformationBarrierRecipientStatus -Identity` <p> È possibile utilizzare qualsiasi valore identity che identifichi ogni destinatario in modo univoco, ad esempio Name, Alias, Distinguished Name (DN), Canonical DN, Email address o GUID. |`Get-InformationBarrierRecipientStatus -Identity meganb` <p> In questo esempio viene utilizzato un alias (*meganb*) per il parametro Identity. Questo cmdlet restituirà informazioni che indicano se l'utente è interessato da un criterio di barriera delle informazioni. (Cercare *ExoPolicyId: \<GUID> .) |

    **Se gli utenti non sono inclusi nei criteri di barriera delle informazioni, contattare il supporto**. In caso contrario, andare al passaggio successivo.

2. Scopri quali segmenti sono inclusi in un criterio di barriera delle informazioni. A tale scopo, utilizzare il `Get-InformationBarrierPolicy` cmdlet con il parametro Identity. 

    |**Sintassi**|**Esempio**|
    |:---------|:----------|
    | `Get-InformationBarrierPolicy` <p> Utilizzare i dettagli, ad esempio il GUID del criterio (ExoPolicyId) ricevuto durante il passaggio precedente, come valore identity. | `Get-InformationBarrierPolicy -Identity b42c3d0f-49e9-4506-a0a5-bf2853b5df6f` <p> In questo esempio vengono fornite informazioni dettagliate sui criteri di barriera delle informazioni con ExoPolicyId *b42c3d0f-49e9-4506-a0a5-bf2853b5df6f*. |

    Dopo aver eseguito il cmdlet, nei risultati cercare i valori **AssignedSegment,** **SegmentsAllowed** **e SegmentsBlocked.**

    Ad esempio, dopo aver eseguito il cmdlet, nell'elenco dei risultati è stato visualizzato `Get-InformationBarrierPolicy` quanto segue:

    ```powershell
    AssignedSegment : Sales
    SegmentsAllowed : {}
    SegmentsBlocked : {Research}
    ```

    In questo caso, possiamo vedere che un criterio di barriera delle informazioni influisce sulle persone che sono nei segmenti Vendite e Ricerca. In questo caso, agli utenti di Vendite non viene impedito di comunicare con gli utenti di Ricerca.

    Se ciò sembra corretto, le barriere alle informazioni funzionano come previsto. In caso contrario, procedere al passaggio successivo.

3. Assicurati che i segmenti siano definiti correttamente. A tale scopo, utilizzare il `Get-OrganizationSegment` cmdlet ed esaminare l'elenco dei risultati.

    |**Sintassi**|**Esempio**|
    |:---------|:----------|
    | `Get-OrganizationSegment`<p> Utilizzare questo cmdlet con un parametro Identity. | `Get-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd` <p> In questo esempio vengono fornite informazioni sul segmento con GUID *c96e0837-c232-4a8a-841e-ef45787d8fcd*. |

    Esaminare i dettagli per il segmento. Se necessario, [modificare un segmento](information-barriers-edit-segments-policies.md#edit-a-segment)e quindi utilizzare di nuovo il `Start-InformationBarrierPoliciesApplication` cmdlet.

    **Se si verificano ancora problemi con i criteri di protezione delle informazioni, contattare il supporto** tecnico.

## <a name="issue-communications-are-allowed-between-users-who-should-be-blocked-in-microsoft-teams"></a>Problema: le comunicazioni sono consentite tra gli utenti che devono essere bloccati in Microsoft Teams

In questo caso, anche se le barriere alle informazioni sono definite, attive e applicate, le persone a cui dovrebbe essere impedito di comunicare tra loro sono in qualche modo in grado di chattare e chiamarsi a vicenda in Microsoft Teams.

### <a name="what-to-do"></a>Soluzione

Verificare che gli utenti in questione siano inclusi in un criterio di barriera delle informazioni. 

1. Utilizzare il cmdlet **Get-InformationBarrierRecipientStatus** con i parametri Identity.

    |**Sintassi** _|_ *Esempio**|
    |:----------|:----------|
    | `Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <p> È possibile utilizzare qualsiasi valore che identifichi ogni utente in modo univoco, ad esempio nome, alias, nome distinto, nome di dominio canonico, indirizzo di posta elettronica o GUID. |`Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <p> In questo esempio, si fa riferimento a due account utente in Office 365: *meganb* per *Megan* e *alexw* per *Alex*. |

    > [!TIP]
    > È inoltre possibile utilizzare questo cmdlet per un singolo utente: `Get-InformationBarrierRecipientStatus -Identity <value>`

2. Esaminare i risultati. Il cmdlet **Get-InformationBarrierRecipientStatus** restituisce informazioni sugli utenti, ad esempio i valori degli attributi e gli eventuali criteri di barriera delle informazioni applicati.

    Esaminare i risultati e quindi eseguire i passaggi successivi, come descritto nella tabella seguente:

    |**Risultati**|**Cosa fare dopo**|
    |:----------|:------------------|
    | Nessun segmento elencato per gli utenti selezionati | Eseguire una delle operazioni seguenti:<br/>- Assegnare gli utenti a un segmento esistente modificando i profili utente in Azure Active Directory. Vedere [Configurare le proprietà dell'account utente con PowerShell di Office 365.](../enterprise/configure-user-account-properties-with-microsoft-365-powershell.md)<br/>- Definire un segmento utilizzando un [attributo supportato per le barriere di informazioni.](information-barriers-attributes.md) Quindi, definisci [un nuovo criterio o](information-barriers-policies.md#part-2-define-information-barrier-policies) modifica un criterio [esistente](information-barriers-edit-segments-policies.md#edit-a-policy) per includere tale segmento. |
    | I segmenti sono elencati, ma non vengono assegnati criteri di barriera delle informazioni a tali segmenti | Eseguire una delle operazioni seguenti:<br/>- [Definire un nuovo criterio di barriera delle](information-barriers-policies.md#part-2-define-information-barrier-policies) informazioni per ogni segmento in questione <br/>- [Modificare un criterio di barriera delle informazioni](information-barriers-edit-segments-policies.md#edit-a-policy) esistente per assegnarlo al segmento corretto |
    | I segmenti sono elencati e ognuno è incluso in un criterio di barriera delle informazioni | - Eseguire il `Get-InformationBarrierPolicy` cmdlet per verificare che i criteri di barriera delle informazioni siano attivi<br/>- Eseguire il `Get-InformationBarrierPoliciesApplicationStatus` cmdlet per verificare che i criteri siano applicati<br/>- Eseguire il `Start-InformationBarrierPoliciesApplication` cmdlet per applicare tutti i criteri di barriera delle informazioni attive |

## <a name="issue-i-need-to-remove-a-single-user-from-an-information-barrier-policy"></a>Problema: è necessario rimuovere un singolo utente da un criterio di barriera delle informazioni

In questo caso, i criteri di barriera delle informazioni sono in vigore e a uno o più utenti viene impedito in modo imprevisto di comunicare con altri utenti in Microsoft Teams. Anziché rimuovere completamente i criteri di barriera delle informazioni, è possibile rimuovere uno o più singoli utenti dai criteri di barriera delle informazioni.

### <a name="what-to-do"></a>Soluzione

I criteri di barriera delle informazioni vengono assegnati a segmenti di utenti. I segmenti vengono definiti utilizzando determinati attributi [nei profili degli account utente.](information-barriers-attributes.md) Se è necessario rimuovere un criterio da un singolo utente, valutare la possibilità di modificare il profilo dell'utente in Azure Active Directory in modo che l'utente non sia più incluso in un segmento interessato da ostacoli alle informazioni.

1. Utilizzare il cmdlet **Get-InformationBarrierRecipientStatus** con i parametri Identity. Questo cmdlet restituisce informazioni sugli utenti, ad esempio i valori degli attributi e gli eventuali criteri di barriera delle informazioni applicati.

    |**Sintassi**|**Esempio**|
    |:---------|:----------|
    | `Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <p> È possibile utilizzare qualsiasi valore che identifichi ogni utente in modo univoco, ad esempio nome, alias, nome distinto, nome di dominio canonico, indirizzo di posta elettronica o GUID. | `Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <p> In questo esempio, si fa riferimento a due account utente in Office 365: *meganb* per *Megan* e *alexw* per *Alex*.          |
    | `Get-InformationBarrierRecipientStatus -Identity <value>` <p> È possibile utilizzare qualsiasi valore che identifichi l'utente in modo univoco, ad esempio nome, alias, nome distinto, nome di dominio canonico, indirizzo di posta elettronica o GUID.|`Get-InformationBarrierRecipientStatus -Identity jeanp`<p> In questo esempio, si fa riferimento a un singolo account in Office 365: *jeanp*. |

2. Esaminare i risultati per verificare se sono assegnati criteri di barriera delle informazioni e a quali segmenti appartengono gli utenti.

3. Per rimuovere un utente da un segmento interessato da barriere di informazioni, aggiornare le informazioni [del profilo dell'utente in Azure Active Directory.](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)

4. Attendere circa 30 minuti perché FwdSync si verifichi. In caso contrario, eseguire il `Start-InformationBarrierPoliciesApplication` cmdlet per applicare tutti i criteri di protezione delle informazioni attivi.

## <a name="issue-the-information-barrier-application-process-is-taking-too-long"></a>Problema: il processo di applicazione della barriera delle informazioni sta prendendo troppo tempo

Dopo aver eseguito il cmdlet **Start-InformationBarrierPoliciesApplication,** il completamento del processo sta prendendo molto tempo.

### <a name="what-to-do"></a>Soluzione

Tenere presente che quando si esegue il cmdlet dell'applicazione dei criteri, i criteri di barriera delle informazioni vengono applicati (o rimossi), utente per utente, per tutti gli account dell'organizzazione. Se si dispone di molti utenti, l'elaborazione richiederà un po' di tempo. Come linea guida generale, l'elaborazione di 5.000 account utente richiede circa un'ora.

1. Utilizzare il cmdlet **Get-InformationBarrierPoliciesApplicationStatus** per verificare lo stato dell'applicazione dei criteri più recente.

    |**Per visualizzare l'applicazione dei criteri più recente**|**Per visualizzare lo stato di tutte le applicazioni dei criteri**|
    |:---------------------------------------------|:---------------------------------------------|
    | `Get-InformationBarrierPoliciesApplicationStatus` | `Get-InformationBarrierPoliciesApplicationStatus -All $true` |

    Verranno visualizzate informazioni sul completamento, l'esito negativo o l'esecuzione dell'applicazione dei criteri.

2. A seconda dei risultati del passaggio precedente, eseguire una delle operazioni seguenti:
  
    |**Stato**|**Passaggio successivo**|
    |:---------|:------------|
    | **Non avviato** | Se sono stati eseguiti più di 45 minuti dall'esecuzione del cmdlet **Start-InformationBarrierPoliciesApplication,** esaminare il log di controllo per verificare se sono presenti errori nelle definizioni dei criteri o altri motivi per cui l'applicazione non è stata avviata. |
    | **Operazione non riuscita** | Se l'applicazione ha avuto esito negativo, esaminare il log di controllo. Esaminare anche i segmenti e i criteri. Gli utenti sono assegnati a più segmenti? A tutti i segmenti sono assegnati più di una poliicy? Se necessario, [modificare i segmenti](information-barriers-edit-segments-policies.md#edit-a-segment) e/o i criteri, quindi eseguire di nuovo il cmdlet **Start-InformationBarrierPoliciesApplication.** [](information-barriers-edit-segments-policies.md#edit-a-policy) |
    | **In corso** | Se l'applicazione è ancora in corso, concedere più tempo per il completamento. Se sono stati diversi giorni, raccogliere i log di controllo e quindi contattare il supporto. |

## <a name="issue-information-barrier-policies-are-not-being-applied-at-all"></a>Problema: i criteri di barriera delle informazioni non vengono applicati affatto

In questo caso, sono stati definiti segmenti, definiti criteri di barriera delle informazioni e si è tentato di applicare tali criteri. Tuttavia, quando si esegue il `Get-InformationBarrierPoliciesApplicationStatus` cmdlet, è possibile vedere che l'applicazione dei criteri non è riuscita.

### <a name="what-to-do"></a>Soluzione

Verificare che nell'organizzazione non siano presenti criteri [della rubrica di Exchange.](/exchange/address-books/address-book-policies/address-book-policies) Tali criteri impediranno l'applicazione dei criteri di barriera delle informazioni.

1. Connettersi [a PowerShell di Exchange Online.](/powershell/exchange/connect-to-exchange-online-powershell)

2. Eseguire il cmdlet [Get-AddressBookPolicy](/powershell/module/exchange/get-addressbookpolicy) ed esaminare i risultati.

    |**Risultati**|**Passaggio successivo**|
    |:----------|:------------|
    | I criteri della rubrica di Exchange sono elencati | [Rimuovere i criteri rubrica](/exchange/address-books/address-book-policies/remove-an-address-book-policy) |
    | Non esistono criteri della rubrica |Esaminare i log di controllo per scoprire perché l'applicazione dei criteri non riesce |

3. [Visualizzare lo stato di account utente, segmenti, criteri o applicazione di criteri.](information-barriers-policies.md#view-status-of-user-accounts-segments-policies-or-policy-application)

## <a name="issue-information-barrier-policy-not-applied-to-all-designated-users"></a>Problema: i criteri di barriera delle informazioni non vengono applicati a tutti gli utenti designati

Dopo aver definito segmenti, definito criteri di barriera delle informazioni e aver tentato di applicare tali criteri, è possibile che il criterio venga applicato ad alcuni destinatari, ma non ad altri.
Quando si esegue il `Get-InformationBarrierPoliciesApplicationStatus` cmdlet, cercare nell'output testo simile al seguente.

> Identità: `<application guid>`
>
> Totale destinatari: 81527
>
> Destinatari non riusciti: 2
>
> Categoria errore: nessuna
>
> Stato: Completato

### <a name="what-to-do"></a>Soluzione

1. Cercare nel log di controllo `<application guid>` . È possibile copiare il codice di PowerShell e modificarlo per le variabili.

```powershell
$DetailedLogs = Search-UnifiedAuditLog -EndDate <yyyy-mm-ddThh:mm:ss>  -StartDate <yyyy-mm-ddThh:mm:ss> -RecordType InformationBarrierPolicyApplication -ResultSize 1000 |?{$_.AuditData.Contains(<application guid>)} 
```

2. Controllare l'output dettagliato del log di controllo per i valori dei `"UserId"` campi e `"ErrorDetails"` . In questo modo verrà visualizzato il motivo dell'errore. È possibile copiare il codice di PowerShell e modificarlo per le variabili.

```powershell
   $DetailedLogs[1] |fl
```

Ad esempio:

> "UserId": User1
>
>"ErrorDetails":"Status: IBPolicyConflict. Errore: il segmento IB "segment id1" e il segmento IB "segment id2" sono in conflitto e non possono essere assegnati al destinatario.

3. In genere, si scoprirà che un utente è stato incluso in più segmenti. È possibile risolvere il problema aggiornando `-UserGroupFilter` il valore in `OrganizationSegments` .

4. Ri-applicare i criteri di barriera delle informazioni utilizzando queste procedure [Criteri barriere informazioni](information-barriers-policies.md#part-3-apply-information-barrier-policies).

## <a name="resources"></a>Risorse

- [Definire i criteri per le barriere alle informazioni in Microsoft Teams](information-barriers-policies.md)
- [Barriere informative](information-barriers.md)