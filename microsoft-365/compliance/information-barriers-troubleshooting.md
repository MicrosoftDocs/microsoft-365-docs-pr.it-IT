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
ms.openlocfilehash: 3810dd977ef0d25642ba86a2b62a036c9a4ace06
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126563"
---
# <a name="troubleshooting-information-barriers"></a>Risoluzione dei problemi relativi alle barriere informative

[Le barriere in](information-barriers.md) materia di informazioni possono aiutare l'organizzazione a rimanere conforme ai requisiti legali e alle normative del settore. Ad esempio, con le barriere in fatto di informazioni, è possibile limitare la comunicazione tra gruppi specifici di utenti per evitare conflitti di interesse o altri problemi. Per ulteriori informazioni su come configurare le barriere in campo delle informazioni, vedere [Definire i criteri per le barriere di informazioni.](information-barriers-policies.md)

Nel caso in cui si verificano problemi imprevisti dopo l'applicazione delle barriere di informazioni, è possibile eseguire alcuni passaggi per risolverli. Usa questo articolo come guida.

> [!IMPORTANT]
> Per eseguire le attività descritte in questo articolo, è necessario disporre di un ruolo appropriato, ad esempio uno dei seguenti:<br/>- Amministratore globale dell'organizzazione di Microsoft 365<br/>- amministratore globale<br/>- Amministratore conformità<br/>- IB Compliance Management (questo è un nuovo ruolo!)<p>Per ulteriori informazioni sui prerequisiti per le barriere delle informazioni, vedere [Prerequisiti (per i criteri delle barriere di informazioni).](information-barriers-policies.md#prerequisites)<p>Assicurarsi di [connettersi a PowerShell & Centro sicurezza e conformità.](/powershell/exchange/connect-to-scc-powershell)

## <a name="issue-users-are-unexpectedly-blocked-from-communicating-with-others-in-microsoft-teams"></a>Problema: agli utenti viene impedito in modo imprevisto di comunicare con altri utenti in Microsoft Teams 

In questo caso, gli utenti segnalano problemi imprevisti che comunicano con altri utenti in Microsoft Teams. Ecco alcuni esempi:

- Un utente cerca, ma non è in grado di trovare, un altro utente in Microsoft Teams.
- Un utente può trovare, ma non selezionare, un altro utente in Microsoft Teams.
- Un utente può visualizzare un altro utente, ma non può inviare messaggi a quell'altro utente in Microsoft Teams.

### <a name="what-to-do"></a>Soluzione

Determinare se gli utenti sono interessati da un criterio di barriere di informazioni. A seconda di come sono configurati i criteri, le barriere di informazioni potrebbero funzionare come previsto. In caso contrario, potrebbe essere necessario perfezionare i criteri dell'organizzazione.

1. Utilizzare il cmdlet **Get-InformationBarrierRecipientStatus** con il parametro Identity. 

    |**Sintassi**|**Esempio**|
    |:---------|:----------|
    | `Get-InformationBarrierRecipientStatus -Identity` <p> È possibile utilizzare qualsiasi valore di identità che identifichi ogni destinatario in modo univoco, ad esempio Nome, Alias, Nome distinto (DN), DN canonico, Indirizzo di posta elettronica o GUID. |`Get-InformationBarrierRecipientStatus -Identity meganb` <p> In questo esempio viene utilizzato un alias (*meganb*) per il parametro Identity. Questo cmdlet restituirà informazioni che indicano se l'utente è interessato da un criterio di barriere di informazioni. (Cercare *ExoPolicyId: \<GUID> .) |

    **Se gli utenti non sono inclusi nei criteri delle barriere di informazioni, contattare il supporto.** In caso contrario, andare al passaggio successivo.

2. Scopri quali segmenti sono inclusi nei criteri delle barriere di informazioni. A tale scopo, utilizzare il `Get-InformationBarrierPolicy` cmdlet con il parametro Identity. 

    |**Sintassi**|**Esempio**|
    |:---------|:----------|
    | `Get-InformationBarrierPolicy` <p> Utilizzare i dettagli, ad esempio il GUID del criterio (ExoPolicyId) ricevuto durante il passaggio precedente, come valore identity. | `Get-InformationBarrierPolicy -Identity b42c3d0f-49e9-4506-a0a5-bf2853b5df6f` <p> In questo esempio vengono fornite informazioni dettagliate sui criteri delle barriere di informazioni con ExoPolicyId *b42c3d0f-49e9-4506-a0a5-bf2853b5df6f.* |

    Dopo aver eseguito il cmdlet, nei risultati cercare i valori **AssignedSegment,** **SegmentsAllowed** **e SegmentsBlocked.**

    Ad esempio, dopo aver eseguito il cmdlet, è stato visualizzato quanto segue `Get-InformationBarrierPolicy` nell'elenco dei risultati:

    ```powershell
    AssignedSegment : Sales
    SegmentsAllowed : {}
    SegmentsBlocked : {Research}
    ```

    In questo caso, è possibile vedere che un criterio di barriere di informazioni influisce sulle persone che sono nei segmenti Vendite e Ricerca. In questo caso, agli utenti di Sales viene impedito di comunicare con gli utenti di Ricerca.

    Se ciò sembra corretto, le barriere di informazione funzionano come previsto. In caso contrario, procedere al passaggio successivo.

3. Assicurati che i segmenti siano definiti correttamente. A tale scopo, utilizzare il `Get-OrganizationSegment` cmdlet ed esaminare l'elenco dei risultati.

    |**Sintassi**|**Esempio**|
    |:---------|:----------|
    | `Get-OrganizationSegment`<p> Utilizzare questo cmdlet con un parametro Identity. | `Get-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd` <p> In questo esempio vengono fornite informazioni sul segmento con GUID *c96e0837-c232-4a8a-841e-ef45787d8fcd*. |

    Esamina i dettagli per il segmento. Se necessario, [modificare un segmento](information-barriers-edit-segments-policies.md#edit-a-segment)e quindi utilizzare di nuovo il `Start-InformationBarrierPoliciesApplication` cmdlet.

    **If you are still having issues with your information barrier policy, contact support.**

## <a name="issue-communications-are-allowed-between-users-who-should-be-blocked-in-microsoft-teams"></a>Problema: le comunicazioni sono consentite tra gli utenti che devono essere bloccati in Microsoft Teams

In questo caso, anche se le barriere di informazioni sono definite, attive e applicate, le persone a cui dovrebbe essere impedito di comunicare tra loro sono in qualche modo in grado di chattare e chiamarsi in Microsoft Teams.

### <a name="what-to-do"></a>Soluzione

Verificare che gli utenti in questione siano inclusi in un criterio di barriere di informazioni. 

1. Utilizzare il cmdlet **Get-InformationBarrierRecipientStatus** con i parametri Identity.

    |**Sintassi** _|_ *Esempio**|
    |:----------|:----------|
    | `Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <p> È possibile utilizzare qualsiasi valore che identifichi ogni utente in modo univoco, ad esempio nome, alias, nome distinto, nome di dominio canonico, indirizzo di posta elettronica o GUID. |`Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <p> In questo esempio si fa riferimento a due account utente in Office 365: *meganb* per *Megan* e *alexw* per *Alex.* |

    > [!TIP]
    > È inoltre possibile utilizzare questo cmdlet per un singolo utente: `Get-InformationBarrierRecipientStatus -Identity <value>`

2. Esaminare i risultati. Il cmdlet **Get-InformationBarrierRecipientStatus** restituisce informazioni sugli utenti, ad esempio i valori degli attributi e gli eventuali criteri delle barriere di informazioni applicati.

    Esaminare i risultati e quindi eseguire i passaggi successivi, come descritto nella tabella seguente:

    |**Risultati**|**Cosa fare dopo**|
    |:----------|:------------------|
    | Nessun segmento elencato per gli utenti selezionati | Eseguire una delle operazioni seguenti:<br/>- Assegnare gli utenti a un segmento esistente modificando i profili utente in Azure Active Directory. Vedere [Configurare le proprietà dell'account utente con PowerShell di Office 365.](/microsoft-365/enterprise/configure-user-account-properties-with-microsoft-365-powershell)<br/>- Definire un segmento usando un [attributo supportato per le barriere di informazioni.](information-barriers-attributes.md) Quindi, definisci [un nuovo criterio o](information-barriers-policies.md#part-2-define-information-barrier-policies) modifica un criterio esistente [per](information-barriers-edit-segments-policies.md#edit-a-policy) includere tale segmento. |
    | I segmenti sono elencati, ma non vengono assegnati criteri delle barriere di informazioni a tali segmenti | Eseguire una delle operazioni seguenti:<br/>- [Definire un nuovo criterio di barriere di informazioni](information-barriers-policies.md#part-2-define-information-barrier-policies) per ogni segmento in questione <br/>- [Modificare un criterio di barriere di](information-barriers-edit-segments-policies.md#edit-a-policy) informazioni esistente per assegnarlo al segmento corretto |
    | I segmenti sono elencati e ognuno è incluso in un criterio di barriere di informazioni | - Eseguire il `Get-InformationBarrierPolicy` cmdlet per verificare che i criteri delle barriere di informazioni siano attivi<br/>- Eseguire il `Get-InformationBarrierPoliciesApplicationStatus` cmdlet per verificare che i criteri siano applicati<br/>- Eseguire il `Start-InformationBarrierPoliciesApplication` cmdlet per applicare tutti i criteri delle barriere di informazioni attive |

## <a name="issue-i-need-to-remove-a-single-user-from-an-information-barrier-policy"></a>Problema: è necessario rimuovere un singolo utente dai criteri delle barriere di informazioni

In questo caso, i criteri delle barriere di informazioni sono in vigore e a uno o più utenti viene impedito in modo imprevisto di comunicare con altri utenti in Microsoft Teams. Anziché rimuovere completamente i criteri delle barriere di informazioni, è possibile rimuovere uno o più singoli utenti dai criteri delle barriere di informazioni.

### <a name="what-to-do"></a>Soluzione

I criteri delle barriere di informazioni vengono assegnati a segmenti di utenti. I segmenti vengono definiti utilizzando determinati attributi [nei profili degli account utente.](information-barriers-attributes.md) Se è necessario rimuovere un criterio da un singolo utente, valutare la possibilità di modificare il profilo dell'utente in Azure Active Directory in modo che l'utente non sia più incluso in un segmento interessato dalle barriere in fatto di informazioni.

1. Utilizzare il cmdlet **Get-InformationBarrierRecipientStatus** con i parametri Identity. Questo cmdlet restituisce informazioni sugli utenti, ad esempio i valori degli attributi e gli eventuali criteri delle barriere di informazioni applicati.

    |**Sintassi**|**Esempio**|
    |:---------|:----------|
    | `Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <p> È possibile utilizzare qualsiasi valore che identifichi ogni utente in modo univoco, ad esempio nome, alias, nome distinto, nome di dominio canonico, indirizzo di posta elettronica o GUID. | `Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <p> In questo esempio si fa riferimento a due account utente in Office 365: *meganb* per *Megan* e *alexw* per *Alex.*          |
    | `Get-InformationBarrierRecipientStatus -Identity <value>` <p> È possibile utilizzare qualsiasi valore che identifichi l'utente in modo univoco, ad esempio nome, alias, nome distinto, nome di dominio canonico, indirizzo di posta elettronica o GUID.|`Get-InformationBarrierRecipientStatus -Identity jeanp`<p> In questo esempio, si fa riferimento a un singolo account in Office 365: *aziendale.* |

2. Esaminare i risultati per verificare se sono assegnati i criteri delle barriere di informazioni e a quali segmenti appartengono gli utenti.

3. Per rimuovere un utente da un segmento interessato dalle barriere in fatto di informazioni, aggiornare le informazioni del profilo [dell'utente in Azure Active Directory.](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)

4. Attendere circa 30 minuti che FwdSync si verifichi. In or, run the `Start-InformationBarrierPoliciesApplication` cmdlet to apply all active information barrier policies.

## <a name="issue-the-information-barrier-application-process-is-taking-too-long"></a>Problema: il processo di applicazione della barriera delle informazioni sta prendendo troppo tempo

Dopo aver eseguito il cmdlet **Start-InformationBarrierPoliciesApplication,** il completamento del processo sta prendendo molto tempo.

### <a name="what-to-do"></a>Soluzione

Tenere presente che quando si esegue il cmdlet dell'applicazione dei criteri, i criteri delle barriere di informazioni vengono applicati (o rimossi), utente per utente, per tutti gli account dell'organizzazione. Se sono molti gli utenti, l'elaborazione richiederà un po' di tempo. Come linea guida generale, l'elaborazione di 5.000 account utente richiede circa un'ora.

1. Utilizzare il cmdlet **Get-InformationBarrierPoliciesApplicationStatus** per verificare lo stato dell'applicazione dei criteri più recente.

    |**Per visualizzare l'applicazione dei criteri più recente**|**Per visualizzare lo stato di tutte le applicazioni di criteri**|
    |:---------------------------------------------|:---------------------------------------------|
    | `Get-InformationBarrierPoliciesApplicationStatus` | `Get-InformationBarrierPoliciesApplicationStatus -All $true` |

    Verranno visualizzate informazioni sul completamento, l'esito negativo o l'esecuzione dell'applicazione dei criteri.

2. A seconda dei risultati del passaggio precedente, eseguire una delle operazioni seguenti:
  
    |**Stato**|**Passaggio successivo**|
    |:---------|:------------|
    | **Non avviato** | Se sono stati più di 45 minuti dall'esecuzione del cmdlet **Start-InformationBarrierPoliciesApplication,** esaminare il log di controllo per verificare se sono presenti errori nelle definizioni dei criteri o per un altro motivo per cui l'applicazione non è stata avviata. |
    | **Operazione non riuscita** | Se l'applicazione non è riuscita, esaminare il log di controllo. Esamina anche i segmenti e i criteri. Gli utenti sono assegnati a più segmenti? Sono assegnati più segmenti a più di una poliicy? Se necessario, [modificare segmenti](information-barriers-edit-segments-policies.md#edit-a-segment) [e/o](information-barriers-edit-segments-policies.md#edit-a-policy)modificare i criteri, quindi eseguire di nuovo il cmdlet **Start-InformationBarrierPoliciesApplication.** |
    | **In corso** | Se l'applicazione è ancora in corso, lascia più tempo per il completamento. Se sono stati diversi giorni, raccogliere i log di controllo e quindi contattare il supporto. |

## <a name="issue-information-barrier-policies-are-not-being-applied-at-all"></a>Problema: i criteri delle barriere di informazioni non vengono applicati affatto

In questo caso, sono stati definiti segmenti, sono stati definiti criteri delle barriere di informazioni e si è tentato di applicare tali criteri. Tuttavia, quando si esegue il `Get-InformationBarrierPoliciesApplicationStatus` cmdlet, è possibile vedere che l'applicazione dei criteri non è riuscita.

### <a name="what-to-do"></a>Soluzione

Assicurarsi che nell'organizzazione non siano presenti criteri della rubrica di [Exchange.](/exchange/address-books/address-book-policies/address-book-policies) Tali criteri impediranno l'applicazione dei criteri delle barriere di informazioni.

1. Connettersi [a PowerShell di Exchange Online.](/powershell/exchange/connect-to-exchange-online-powershell)

2. Eseguire il cmdlet [Get-AddressBookPolicy](/powershell/module/exchange/get-addressbookpolicy) ed esaminare i risultati.

    |**Risultati**|**Passaggio successivo**|
    |:----------|:------------|
    | Sono elencati i criteri della rubrica di Exchange | [Rimuovere i criteri rubrica](/exchange/address-books/address-book-policies/remove-an-address-book-policy) |
    | Non esistono criteri della rubrica |Esaminare i log di controllo per scoprire perché l'applicazione dei criteri non riesce |

3. [Visualizzare lo stato di account utente, segmenti, criteri o applicazioni di criteri.](information-barriers-policies.md#view-status-of-user-accounts-segments-policies-or-policy-application)

## <a name="issue-information-barrier-policy-not-applied-to-all-designated-users"></a>Problema: i criteri delle barriere di informazioni non vengono applicati a tutti gli utenti designati

Dopo aver definito segmenti, definito i criteri delle barriere di informazioni e aver tentato di applicare tali criteri, è possibile che il criterio venga applicato ad alcuni destinatari, ma non ad altri.
Quando si esegue il `Get-InformationBarrierPoliciesApplicationStatus` cmdlet, cercare nell'output testo simile al seguente.

> Identità: `<application guid>`
>
> Destinatari totali: 81527
>
> Destinatari non riusciti: 2
>
> Categoria errore: Nessuna
>
> Status: Complete

### <a name="what-to-do"></a>Soluzione

1. Cercare nel log di controllo `<application guid>` . È possibile copiare il codice di PowerShell e modificarlo per le variabili.

```powershell
$DetailedLogs = Search-UnifiedAuditLog -EndDate <yyyy-mm-ddThh:mm:ss>  -StartDate <yyyy-mm-ddThh:mm:ss> -RecordType InformationBarrierPolicyApplication -ResultSize 1000 |?{$_.AuditData.Contains(<application guid>)} 
```

2. Controllare l'output dettagliato del log di controllo per i valori dei `"UserId"` campi `"ErrorDetails"` e. In questo modo verrà visualizzato il motivo dell'errore. È possibile copiare il codice di PowerShell e modificarlo per le variabili.

```powershell
   $DetailedLogs[1] |fl
```

Ad esempio:

> "UserId": User1
>
>"ErrorDetails":"Status: IBPolicyConflict. Errore: Il segmento IB "segment id1" e il segmento IB "segment id2" sono in conflitto e non possono essere assegnati al destinatario.

3. In genere, un utente è stato incluso in più segmenti. È possibile risolvere il problema aggiornando `-UserGroupFilter` il valore in `OrganizationSegments` .

4. Ri applicare di nuovo i criteri delle barriere di informazioni utilizzando queste [procedure.](information-barriers-policies.md#part-3-apply-information-barrier-policies)

## <a name="resources"></a>Risorse

- [Definire i criteri per le barriere delle informazioni in Microsoft Teams](information-barriers-policies.md)
- [Barriere informative](information-barriers.md)
