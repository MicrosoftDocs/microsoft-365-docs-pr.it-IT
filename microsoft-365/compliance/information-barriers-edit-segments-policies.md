---
title: Gestire i criteri di barriera delle informazioni
description: Informazioni su come modificare o rimuovere i criteri per le barriere alle informazioni.
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
ms.openlocfilehash: 668ca8e26371d80f068c2723357ce3ee407db03a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925552"
---
# <a name="manage-information-barrier-policies"></a>Gestire i criteri di barriera delle informazioni

Dopo aver definito [i criteri](information-barriers-policies.md)di barriera delle informazioni, potrebbe essere necessario apportare [](information-barriers-troubleshooting.md) modifiche a tali criteri o ai segmenti di utenti, come parte della risoluzione dei problemi o come manutenzione regolare. Usa questo articolo come guida.

## <a name="what-do-you-want-to-do"></a>Operazione desiderata

|**Azione**|**Descrizione**|
|:---------|:--------------|
| [Modificare gli attributi dell'account utente](#edit-user-account-attributes) | Compilare gli attributi in Azure Active Directory che possono essere usati per definire i segmenti.<br/>Modificare gli attributi dell'account utente quando gli utenti non sono inclusi nei segmenti che dovrebbero essere, per modificare i segmenti in cui sono gli utenti o per definire i segmenti con attributi diversi. |
| [Modificare un segmento](#edit-a-segment) | Modificare i segmenti quando si desidera modificare la modalità di definizione di un segmento. <br/>Ad esempio, potresti aver originariamente definito segmenti usando *Department* e ora vuoi usare un altro attributo, ad esempio *MemberOf.* |
| [Modificare un criterio](#edit-a-policy) | Modificare un criterio di barriera delle informazioni quando si desidera modificare il funzionamento di un criterio.<br/>Ad esempio, invece di bloccare le comunicazioni tra due segmenti, potresti decidere di consentire la comunicazione solo tra determinati segmenti. |
| [Impostare un criterio sullo stato inattivo](#set-a-policy-to-inactive-status) |Impostare un criterio sullo stato inattivo quando si desidera apportare modifiche a un criterio o quando non si desidera che un criterio sia attivo. |
| [Rimuovere un criterio](#remove-a-policy) | Rimuovere un criterio di barriera delle informazioni quando non è più necessario un criterio specifico. |
| [Arrestare un'applicazione di criteri](#stop-a-policy-application) | Eseguire questa azione quando si desidera interrompere il processo di applicazione dei criteri di barriera delle informazioni.<br/> L'arresto di un'applicazione dei criteri non è istantaneo e non annulla i criteri già applicati agli utenti. |
| [Definire i criteri per le barriere delle informazioni](information-barriers-policies.md) | Definire un criterio di barriera delle informazioni quando non si dispone già di tali criteri ed è necessario limitare o limitare le comunicazioni tra gruppi specifici di utenti. |
| [Risoluzione dei problemi relativi alle barriere informative](information-barriers-troubleshooting.md) | Fare riferimento a questo articolo quando si verificano problemi imprevisti con le barriere alle informazioni. |

> [!IMPORTANT]
> Per eseguire le attività descritte in questo articolo, è necessario disporre di un ruolo appropriato, ad esempio uno dei seguenti:<br/>- Amministratore globale dell'organizzazione di Microsoft 365<br/>- Amministratore globale<br/>- Amministratore conformità<br/>- Gestione della conformità IB (questo è un nuovo ruolo!)<br><br>Per ulteriori informazioni sui prerequisiti per le barriere alle informazioni, vedere [Prerequisites (for information barrier policies)](information-barriers-policies.md#prerequisites).<br><br> Assicurarsi di [connettersi a PowerShell & Centro sicurezza e conformità.](/powershell/exchange/connect-to-scc-powershell)

## <a name="edit-user-account-attributes"></a>Modificare gli attributi dell'account utente

Utilizzare questa procedura per modificare gli attributi utilizzati per segmentare gli utenti. Ad esempio, se si utilizza un attributo Department e uno o più account utente non dispongono attualmente di valori elencati per Department, è necessario modificare tali account utente in modo da includere le informazioni relative al reparto. Gli attributi dell'account utente vengono utilizzati per definire i segmenti in modo da poter assegnare i criteri di barriera delle informazioni.

1. Per visualizzare i dettagli di un account utente specifico, ad esempio i valori degli attributi e i segmenti assegnati, utilizzare il cmdlet **Get-InformationBarrierRecipientStatus** con i parametri Identity.

    |**Sintassi**|**Esempio**|
    |:---------|:----------|
    | `Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <p> È possibile utilizzare qualsiasi valore che identifichi ogni utente in modo univoco, ad esempio nome, alias, nome distinto, nome di dominio canonico, indirizzo di posta elettronica o GUID. <p> È inoltre possibile utilizzare questo cmdlet per un singolo `Get-InformationBarrierRecipientStatus -Identity <value>` utente: |`Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <p> In questo esempio, si fa riferimento a due account utente in Office 365: *meganb* per *Megan* e *alexw* per *Alex*. |

2. Determinare l'attributo che si desidera modificare per i profili dell'account utente. Per ulteriori informazioni, vedere [Attributi per i criteri di barriera delle informazioni.](information-barriers-attributes.md) 

3. Modificare uno o più account utente per includere i valori per l'attributo selezionato nel passaggio precedente. Per eseguire questa operazione, utilizzare una delle procedure seguenti:

    - Per modificare un singolo account, vedere Aggiungere o aggiornare le informazioni del profilo di un [utente con Azure Active Directory.](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)

    - Per modificare più account (o usare PowerShell per modificare un singolo account), vedere [Configure user account properties with Office 365 PowerShell](../enterprise/configure-user-account-properties-with-microsoft-365-powershell.md).

## <a name="edit-a-segment"></a>Modificare un segmento

Utilizzare questa procedura per modificare la definizione di un segmento di utenti. Ad esempio, potresti modificare il nome di un segmento o il filtro utilizzato per determinare chi è incluso nel segmento.

1. Per visualizzare tutti i segmenti esistenti, utilizzare il cmdlet **Get-OrganizationSegment.**

    Sintassi: `Get-OrganizationSegment`

    Verrà visualizzato un elenco di segmenti e dettagli per ognuno di essi, ad esempio il tipo di segmento, il relativo valore UserGroupFilter, l'utente che lo ha creato o modificato per l'ultima volta, il GUID e così via.

    > [!TIP]
    > Stampa o salva l'elenco di segmenti per riferimento in un secondo momento. Ad esempio, se si desidera modificare un segmento, è necessario conoscerne il nome o identificare il valore (utilizzato con il parametro Identity).

2. Per modificare un segmento, utilizzare il cmdlet **Set-OrganizationSegment** con il **parametro Identity** e i dettagli pertinenti.

    |**Sintassi**|**Esempio**|
    |:---------|:----------|
    | `Set-OrganizationSegment -Identity GUID -UserGroupFilter "attribute -eq 'attributevalue'"` |`Set-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd -UserGroupFilter "Department -eq 'HRDept'"` <p> In questo esempio, per il segmento con GUID *c96e0837-c232-4a8a-841e-ef45787d8fcd,* il nome del reparto è stato aggiornato in "HRDept". |

Dopo aver modificato i segmenti per l'organizzazione, è possibile definire o [modificare i](#edit-a-policy) criteri di barriera delle informazioni. [](information-barriers-policies.md#part-2-define-information-barrier-policies)

## <a name="edit-a-policy"></a>Modificare un criterio

1. Per visualizzare un elenco dei criteri di barriera delle informazioni correnti, utilizzare il cmdlet **Get-InformationBarrierPolicy.**

    Sintassi: `Get-InformationBarrierPolicy`

    Nell'elenco dei risultati identificare il criterio che si desidera modificare. Prendere nota del GUID e del nome del criterio.

2. Utilizzare il cmdlet **Set-InformationBarrierPolicy** con un parametro **Identity** e specificare le modifiche che si desidera apportare.

    Esempio: si supponga che sia stato definito un criterio per impedire al segmento *Ricerche* di comunicare con i *segmenti Vendite* *e* Marketing. Il criterio è stato definito utilizzando questo cmdlet: `New-InformationBarrierPolicy -Name "Research-SalesMarketing" -AssignedSegment "Research" -SegmentsBlocked "Sales","Marketing"`

    Supponiamo di volerlo modificare in modo che gli utenti del segmento *Ricerca* possano comunicare solo con persone nel *segmento HR.* Per apportare questa modifica, viene utilizzato questo cmdlet: `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -SegmentsAllowed "HR"`

    In questo esempio abbiamo modificato "SegmentsBlocked" in "SegmentsAllowed" e specificato il *segmento HR.*

3. Al termine della modifica di un criterio, assicurarsi di applicare le modifiche. (Vedere [Applicare i criteri di barriera delle informazioni](information-barriers-policies.md#part-3-apply-information-barrier-policies).)

## <a name="set-a-policy-to-inactive-status"></a>Impostare un criterio sullo stato inattivo

1. Per visualizzare un elenco dei criteri di barriera delle informazioni correnti, utilizzare il cmdlet **Get-InformationBarrierPolicy.**

    Sintassi: `Get-InformationBarrierPolicy`

    Nell'elenco dei risultati identificare il criterio che si desidera modificare o rimuovere. Prendere nota del GUID e del nome del criterio.

2. Per impostare lo stato del criterio su inattivo, utilizzare il cmdlet **Set-InformationBarrierPolicy** con un parametro Identity e il parametro State impostato su Inactive.

    |**Sintassi**|**Esempio**|
    |:---------|:----------|
    | `Set-InformationBarrierPolicy -Identity GUID -State Inactive` | `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c9377247 -State Inactive` <p> In questo esempio viene impostato un criterio di barriera delle informazioni con GUID *43c37853-ea10-4b90-a23d-ab8c9377247* su uno stato inattivo. |

3. Per applicare le modifiche, utilizzare il cmdlet **Start-InformationBarrierPoliciesApplication.**

    Sintassi: `Start-InformationBarrierPoliciesApplication`

    Le modifiche vengono applicate, utente per utente, per l'organizzazione. Se l'organizzazione è di grandi dimensioni, il completamento di questo processo può richiedere 24 ore (o più). Come linea guida generale, l'elaborazione di 5.000 account utente richiede circa un'ora.

A questo punto, uno o più criteri di barriera delle informazioni sono impostati sullo stato inattivo. Da qui è possibile eseguire una delle operazioni seguenti:

- Mantenerlo così come è (un criterio impostato sullo stato inattivo non ha alcun effetto sugli utenti)
- [Modificare un criterio](#edit-a-policy) 
- [Rimuovere un criterio](#remove-a-policy)

## <a name="remove-a-policy"></a>Rimuovere un criterio

1. Per visualizzare un elenco dei criteri di barriera delle informazioni correnti, utilizzare il cmdlet **Get-InformationBarrierPolicy.**

    Sintassi: `Get-InformationBarrierPolicy`

    Nell'elenco dei risultati identificare il criterio che si desidera rimuovere. Prendere nota del GUID e del nome del criterio. Assicurati che il criterio sia impostato sullo stato inattivo.

2. Utilizzare il cmdlet **Remove-InformationBarrierPolicy** con un parametro Identity.

    |**Sintassi**|**Esempio**|
    |:---------|:----------|
    | `Remove-InformationBarrierPolicy -Identity GUID` | `Remove-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471` <p> In questo esempio viene rimosso il criterio con GUID *43c37853-ea10-4b90-a23d-ab8c93772471*. |

    Quando richiesto, confermare la modifica.

3. Ripetere i passaggi da 1 a 2 per ogni criterio che si desidera rimuovere.

4. Al termine della rimozione dei criteri, applicare le modifiche. Per eseguire questa operazione, utilizzare il cmdlet **Start-InformationBarrierPoliciesApplication.**

    Sintassi: `Start-InformationBarrierPoliciesApplication`

    Le modifiche vengono applicate, utente per utente, per l'organizzazione. Se l'organizzazione è di grandi dimensioni, il completamento di questo processo può richiedere 24 ore (o più).

## <a name="stop-a-policy-application"></a>Arrestare un'applicazione di criteri

Dopo aver avviato l'applicazione dei criteri di protezione delle informazioni, se si desidera impedire l'applicazione di tali criteri, eseguire la procedura seguente. L'inizio del processo richiederà circa 30-35 minuti.

1. Per visualizzare lo stato dell'applicazione dei criteri di protezione delle informazioni più recente, utilizzare il cmdlet **Get-InformationBarrierPoliciesApplicationStatus.**

    Sintassi: `Get-InformationBarrierPoliciesApplicationStatus`

    Prendere nota del GUID dell'applicazione.

2. Utilizzare il cmdlet **Stop-InformationBarrierPoliciesApplication** con un parametro Identity.

    |**Sintassi**|**Esempio**|
    |:---------|:----------|
    | `Stop-InformationBarrierPoliciesApplication -Identity GUID` | `Stop-InformationBarrierPoliciesApplication -Identity 46237888-12ca-42e3-a541-3fcb7b5231d1` <p> In questo esempio, stiamo interrompendo l'applicazione dei criteri di barriera delle informazioni. |

## <a name="resources"></a>Risorse

- [Ottenere una panoramica delle barriere in fatto di informazioni](information-barriers.md)
- [Definire i criteri per le barriere delle informazioni](information-barriers-policies.md)
- [Ulteriori informazioni sulle barriere di informazioni in Microsoft Teams](/MicrosoftTeams/information-barriers-in-teams)
- [Ulteriori informazioni sulle barriere di informazioni in SharePoint Online](/sharepoint/information-barriers)
- [Ulteriori informazioni sulle barriere di informazioni in OneDrive](/onedrive/information-barriers)
- [Attributi per i criteri delle barriere informative](information-barriers-attributes.md)
- [Risoluzione dei problemi relativi alle barriere informative](information-barriers-troubleshooting.md)