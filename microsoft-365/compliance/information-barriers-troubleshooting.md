---
title: Risoluzione dei problemi relativi alle barriere informative
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/08/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
description: Utilizzare questo articolo come guida per la risoluzione dei problemi relativi alle barriere informative.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f4e6087d0e1886d833a6cf0472ed467f8577c5d0
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/29/2020
ms.locfileid: "47307929"
---
# <a name="troubleshooting-information-barriers"></a>Risoluzione dei problemi relativi alle barriere informative

Gli [ostacoli alle informazioni](information-barriers.md) consentono all'organizzazione di rimanere conforme ai requisiti legali e ai regolamenti di settore. Ad esempio, con barriere informative, è possibile limitare le comunicazioni tra gruppi specifici di utenti per evitare conflitti di interesse o altri problemi. Per ulteriori informazioni su come configurare le barriere informative, vedere [define Policies for Information barriers](information-barriers-policies.md).

Nel caso in cui si verifichino problemi imprevisti dopo che sono state apportate barriere alle informazioni, è possibile eseguire alcuni passaggi per risolvere questi problemi. Utilizzare questo articolo come guida.

> [!IMPORTANT]
> Per eseguire le attività descritte in questo articolo, è necessario essere assegnati a un ruolo appropriato, ad esempio uno dei seguenti:<br/>-Microsoft 365 Enterprise Global Administrator<br/>-amministratore globale<br/>-Compliance Administrator<br/>-IB Compliance Management (questo è un nuovo ruolo)<p>Per ulteriori informazioni sui prerequisiti per le barriere informative, vedere [prerequisiti (per i criteri barriera informativi)](information-barriers-policies.md#prerequisites).<p>Assicurarsi di [connettersi a PowerShell per il Centro sicurezza & Compliance](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).

## <a name="issue-users-are-unexpectedly-blocked-from-communicating-with-others-in-microsoft-teams"></a>Problema: gli utenti sono inaspettatamente bloccati dalla comunicazione con gli altri membri di Microsoft Teams 

In questo caso, gli utenti segnalano problemi imprevisti che comunicano con altri utenti di Microsoft teams. Esempi:
- Un utente cerca, ma non è in grado di trovare un altro utente in Microsoft teams.
- Un utente può trovare, ma non è in grado di selezionare, un altro utente in Microsoft teams.
- Un utente può visualizzare un altro utente, ma non è in grado di inviare messaggi a un altro utente in Microsoft teams.

### <a name="what-to-do"></a>Soluzione

Determinare se gli utenti sono coinvolti in un criterio barriera informativo. A seconda del modo in cui vengono configurati i criteri, gli ostacoli alle informazioni potrebbero funzionare come previsto. In alternativa, potrebbe essere necessario perfezionare i criteri dell'organizzazione.

1. Utilizzare il cmdlet **Get-InformationBarrierRecipientStatus** con il parametro Identity. 

    |Sintassi  |Esempio  |
    |---------|---------|
    | `Get-InformationBarrierRecipientStatus -Identity` <p>È possibile utilizzare qualsiasi valore di identità che identifichi in modo univoco ogni destinatario, ad esempio nome, alias, nome distinto (DN), DN canonico, indirizzo di posta elettronica o GUID.     |`Get-InformationBarrierRecipientStatus -Identity meganb` <p>In questo esempio viene utilizzato un alias (*meganb*) per il parametro Identity. Questo cmdlet restituirà informazioni che indicano se l'utente è influenzato da un criterio barriera informativo. (Cercare * ExoPolicyId: \<GUID> .)         |

    **Se gli utenti non sono inclusi nei criteri di barriera delle informazioni, contattare il supporto**. In caso contrario, passare al passaggio successivo.

2. Scoprire quali segmenti sono inclusi in un criterio barriera informativo. A tale scopo, utilizzare il `Get-InformationBarrierPolicy` cmdlet con il parametro Identity. 

    |Sintassi  |Esempio  |
    |---------|---------|
    |`Get-InformationBarrierPolicy` <p>Utilizzare i dettagli, ad esempio il GUID dei criteri (ExoPolicyId) ricevuto durante il passaggio precedente, come valore di identità.     | `Get-InformationBarrierPolicy -Identity b42c3d0f-49e9-4506-a0a5-bf2853b5df6f` <p>In questo esempio, vengono fornite informazioni dettagliate sul criterio barriera informativo con ExoPolicyId *b42c3d0f-49E9-4506-a0a5-bf2853b5df6f*.         |

    Dopo aver eseguito il cmdlet, nei risultati cercare i valori **AssignedSegment**, **SegmentsAllowed**e **SegmentsBlocked** .

    Dopo aver eseguito il `Get-InformationBarrierPolicy` cmdlet, ad esempio, è stato riportato quanto segue nell'elenco dei risultati:

    ```powershell
        AssignedSegment      : Sales
        SegmentsAllowed      : {}
        SegmentsBlocked      : {Research}
    ```
    In questo caso, è possibile osservare che un criterio di barriera informativo interessa le persone che si trovano nei segmenti Sales and Research. In questo caso, agli utenti nelle vendite viene impedito di comunicare con gli utenti nella ricerca. 
    
    Se questo sembra corretto, le barriere informative funzionano come previsto. In caso contrario, procedere al passaggio successivo.

4. Verificare che i segmenti siano definiti correttamente. A tale scopo, utilizzare il `Get-OrganizationSegment` cmdlet ed esaminare l'elenco dei risultati. 

    |Sintassi  |Esempio  |
    |---------|---------|
    |`Get-OrganizationSegment`<p>Utilizzare questo cmdlet con un parametro Identity.     |`Get-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd` <p>In questo esempio vengono riportate informazioni sul segmento con GUID *c96e0837-C232-4a8a-841E-ef45787d8fcd*.         |

    Esaminare i dettagli del segmento. Se necessario, [modificare un segmento](information-barriers-edit-segments-policies.md#edit-a-segment)e quindi riutilizzare il `Start-InformationBarrierPoliciesApplication` cmdlet.

    **Se si verificano ancora problemi con il criterio barriera informativo, contattare il supporto**.

## <a name="issue-communications-are-allowed-between-users-who-should-be-blocked-in-microsoft-teams"></a>Problema: le comunicazioni sono consentite tra gli utenti che devono essere bloccati in Microsoft Teams

In questo caso, anche se le barriere informative sono definite, attive e applicate, le persone che dovrebbero essere impossibilitate a comunicare tra loro sono in grado di chattare e di chiamarsi a vicenda in Microsoft teams.

### <a name="what-to-do"></a>Soluzione

Verificare che gli utenti in questione siano inclusi in un criterio barriera informativo. 

1. Utilizzare il cmdlet **Get-InformationBarrierRecipientStatus** con i parametri Identity.

    |Sintassi  |Esempio  |
    |---------|---------|
    |`Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <p>È possibile utilizzare qualsiasi valore che identifichi in modo univoco ogni utente, ad esempio nome, alias, nome distinto, nome di dominio canonico, indirizzo di posta elettronica o GUID.     |`Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <p>In questo esempio, si fa riferimento a due account utente in Office 365: *meganb* per *Megan*e *alexw* per *Alex*.          |

    
    > [!TIP]
    > È inoltre possibile utilizzare questo cmdlet per un singolo utente: `Get-InformationBarrierRecipientStatus -Identity <value>`
    
2. Esaminare i risultati. Il cmdlet **Get-InformationBarrierRecipientStatus** restituisce informazioni sugli utenti, ad esempio i valori degli attributi e tutti i criteri di barriera delle informazioni applicati. 

    Esaminare i risultati e quindi eseguire i passaggi successivi, come descritto nella tabella seguente:
    
    |Risultati  |Cosa fare dopo  |
    |---------|---------|
    |Nessun segmento è elencato per l'utente o gli utenti selezionati     |Eseguire una delle operazioni seguenti:<br/>-Assegnare gli utenti a un segmento esistente modificando i relativi profili utente in Azure Active Directory. Vedere [configurare le proprietà degli account utente con Office 365 PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/configure-user-account-properties-with-microsoft-365-powershell).<br/>-Definire un segmento utilizzando un [attributo supportato per le barriere informative](information-barriers-attributes.md). [Definire quindi un nuovo criterio](information-barriers-policies.md#part-2-define-information-barrier-policies) o [modificare un criterio esistente](information-barriers-edit-segments-policies.md#edit-a-policy) per includere tale segmento.  |
    |I segmenti sono elencati ma non sono stati assegnati criteri barriera informativi a tali segmenti     |Eseguire una delle operazioni seguenti:<br/>- [Definire un nuovo criterio barriera informativo](information-barriers-policies.md#part-2-define-information-barrier-policies) per ogni segmento in questione<br/>- [Modificare un criterio barriera di informazioni esistente](information-barriers-edit-segments-policies.md#edit-a-policy) per assegnarlo al segmento corretto         |
    |I segmenti sono elencati e ognuno di essi è incluso in un criterio barriera informativo     |-Eseguire il `Get-InformationBarrierPolicy` cmdlet per verificare che i criteri di barriera delle informazioni siano attivi<br/>-Eseguire il `Get-InformationBarrierPoliciesApplicationStatus` cmdlet per verificare che i criteri vengano applicati<br/>-Eseguire il `Start-InformationBarrierPoliciesApplication` cmdlet per applicare tutti i criteri di barriera delle informazioni attive          |
    

## <a name="issue-i-need-to-remove-a-single-user-from-an-information-barrier-policy"></a>Problema: è necessario rimuovere un singolo utente da un criterio barriera informativo

In questo caso, i criteri per la barriera delle informazioni sono in vigore e uno o più utenti sono inaspettatamente bloccati dalla comunicazione con altri membri di Microsoft teams. Anziché rimuovere tutti i criteri di barriera delle informazioni, è possibile rimuovere uno o più singoli utenti dai criteri di barriera delle informazioni. 

### <a name="what-to-do"></a>Soluzione

I criteri barriera di informazioni vengono assegnati a segmenti di utenti. I segmenti vengono definiti utilizzando determinati [attributi nei profili degli account utente](information-barriers-attributes.md). Se è necessario rimuovere un criterio da un singolo utente, prendere in considerazione la possibilità di modificare il profilo dell'utente in Azure Active Directory in modo che l'utente non sia più incluso in un segmento influenzato dalle barriere informative.

1. Utilizzare il cmdlet **Get-InformationBarrierRecipientStatus** con i parametri Identity. Questo cmdlet restituisce informazioni sugli utenti, ad esempio i valori degli attributi e tutti i criteri di barriera delle informazioni applicati.

    |Sintassi  |Esempio  |
    |---------|---------|
    |`Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>`<p>È possibile utilizzare qualsiasi valore che identifichi in modo univoco ogni utente, ad esempio nome, alias, nome distinto, nome di dominio canonico, indirizzo di posta elettronica o GUID.     |`Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <p>In questo esempio, si fa riferimento a due account utente in Office 365: *meganb* per *Megan*e *alexw* per *Alex*.          |
    |`Get-InformationBarrierRecipientStatus -Identity <value>` <p>È possibile utilizzare qualsiasi valore che identifichi in modo univoco l'utente, ad esempio il nome, l'alias, il nome distinto, il nome di dominio canonico, l'indirizzo di posta elettronica o il GUID.|`Get-InformationBarrierRecipientStatus -Identity jeanp`<p>In questo esempio, si fa riferimento a un singolo account in Office 365: *jeanp*. |

2. Esaminare i risultati per vedere se sono assegnati criteri barriera informativi e a quali segmenti appartengono gli utenti. 

3. Per rimuovere un utente da un segmento influenzato dalle barriere informative, [aggiornare le informazioni sul profilo dell'utente in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).

4. Attendere circa 30 minuti affinché FwdSync si verifichi. In alternativa, eseguire il `Start-InformationBarrierPoliciesApplication` cmdlet per applicare tutti i criteri di barriera delle informazioni attive.

## <a name="issue-the-information-barrier-application-process-is-taking-too-long"></a>Problema: il processo di applicazione barriera alle informazioni richiede troppo tempo

Dopo aver eseguito il cmdlet **Start-InformationBarrierPoliciesApplication** , il processo richiede molto tempo per il completamento.

### <a name="what-to-do"></a>Soluzione

Tenere presente che, quando si esegue il cmdlet applicazione criteri, i criteri di barriera delle informazioni vengono applicati (o rimossi), utente per utente, per tutti gli account nell'organizzazione. Se si dispone di numerosi utenti, sarà necessario un po' di tempo per elaborarli. (Come linee guida generali, è necessario circa un'ora per elaborare gli account utente di 5.000).

1. Utilizzare il cmdlet **Get-InformationBarrierPoliciesApplicationStatus** per verificare lo stato dell'applicazione di criteri più recente.

    |Per visualizzare l'applicazione di criteri più recente  |Per visualizzare lo stato di tutte le applicazioni di criteri  |
    |---------|---------|
    |`Get-InformationBarrierPoliciesApplicationStatus`     |`Get-InformationBarrierPoliciesApplicationStatus -All $true`         |


    Verranno visualizzate informazioni sul modo in cui l'applicazione del criterio è stata completata, non è riuscita o è in corso.

2. A seconda dei risultati del passaggio precedente, eseguire una delle operazioni seguenti:
  
    |Stato  |Passaggio successivo  |
    |---------|---------|
    |**Non avviato**     |Se dopo aver eseguito il cmdlet **Start-InformationBarrierPoliciesApplication** sono stati eseguiti più di 45 minuti, esaminare il log di controllo per verificare se sono presenti errori nelle definizioni dei criteri o in qualche altro motivo per cui l'applicazione non è stata avviata. |
    |**Operazione non riuscita**     |Se l'applicazione ha avuto esito negativo, esaminare il log di controllo. Esaminare inoltre i segmenti e i criteri. Gli utenti sono assegnati a più di un segmento? I segmenti sono assegnati a più di un poliicy? Se necessario, [modificare i segmenti](information-barriers-edit-segments-policies.md#edit-a-segment) e/o [modificare i criteri](information-barriers-edit-segments-policies.md#edit-a-policy), quindi eseguire di nuovo il cmdlet **Start-InformationBarrierPoliciesApplication** .  |
    |**In corso**     |Se l'applicazione è ancora in corso, è necessario più tempo per il completamento. Se sono stati diversi giorni, raccogliere i registri di controllo e quindi contattare il supporto tecnico. |

## <a name="issue-information-barrier-policies-are-not-being-applied-at-all"></a>Problema: non vengono applicati criteri barriera di informazioni

In questo caso, sono stati definiti segmenti, criteri di barriere informativi definiti e si è tentato di applicare tali criteri. Tuttavia, quando si esegue il `Get-InformationBarrierPoliciesApplicationStatus` cmdlet, è possibile vedere che l'applicazione del criterio ha avuto esito negativo.

### <a name="what-to-do"></a>Soluzione

Assicurarsi che l'organizzazione non disponga di [Criteri rubrica di Exchange](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies) sul posto. Tali criteri impediscono l'applicazione dei criteri di barriera delle informazioni.

1. Connettersi a [PowerShell di Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps). 

2. Eseguire il cmdlet [Get-AddressBookPolicy](https://docs.microsoft.com/powershell/module/exchange/get-addressbookpolicy?view=exchange-ps) ed esaminare i risultati.

    |Risultati  |Passaggio successivo  |
    |---------|---------|
    |Sono elencati i criteri Rubrica di Exchange     |[Rimuovere i criteri rubrica](https://docs.microsoft.com/exchange/address-books/address-book-policies/remove-an-address-book-policy)         |
    |Non esistono criteri Rubrica |Esaminare i registri di controllo per scoprire perché l'applicazione dei criteri non riesce |

3. [Visualizzare lo stato degli account utente, i segmenti, i criteri o l'applicazione di criteri](information-barriers-policies.md#view-status-of-user-accounts-segments-policies-or-policy-application).

## <a name="issue-information-barrier-policy-not-applied-to-all-designated-users"></a>Problema: criteri barriera informativa non applicati a tutti gli utenti designati

Dopo aver definito i segmenti, i criteri di barriera delle informazioni definiti e aver tentato di applicare tali criteri, è possibile che il criterio si applichi a alcuni destinatari, ma non ad altri.
Quando si esegue il `Get-InformationBarrierPoliciesApplicationStatus` cmdlet, eseguire una ricerca nell'output per ottenere un testo simile al seguente.

> Identità `<application guid>`
>
> Destinatari totali: 81527
>
> Destinatari non riusciti: 2
>
> Categoria di errore: None
>
> Stato: completo

### <a name="what-to-do"></a>Soluzione

1. Ricerca nel registro di controllo per `<application guid>` . È possibile copiare il codice di PowerShell e modificarlo per le variabili.

```powershell
$DetailedLogs = Search-UnifiedAuditLog -EndDate <yyyy-mm-ddThh:mm:ss>  -StartDate <yyyy-mm-ddThh:mm:ss> -RecordType InformationBarrierPolicyApplication -ResultSize 1000 |?{$_.AuditData.Contains(<application guid>)} 
```

2. Controllare l'output dettagliato dal registro di controllo per i valori dei `"UserId"` campi e `"ErrorDetails"` . In questo modo si otterrà la causa dell'errore. È possibile copiare il codice di PowerShell e modificarlo per le variabili.

```powershell
   $DetailedLogs[1] |fl
```
 Ad esempio:

> "UserId": user1
> 
>"ErrorDetails": "stato: IBPolicyConflict. Errore: il segmento IB "Segment ID1" e IB segment "Segment ID2" ha un conflitto e non può essere assegnato al destinatario. 

3. In genere, si noterà che un utente è stato incluso in più di un segmento. Per risolvere il valore, è possibile aggiornarlo `-UserGroupFilter` in `OrganizationSegments` .

4. Applicare di nuovo i criteri di barriera delle informazioni usando queste procedure [criteri di barriere informative](information-barriers-policies.md#part-3-apply-information-barrier-policies).

## <a name="related-topics"></a>Argomenti correlati

[Definire i criteri per le barriere informative in Microsoft Teams](information-barriers-policies.md)

[Barriere informative](information-barriers.md)
