---
title: Gestire i criteri di barriera delle informazioni
description: Informazioni su come modificare o rimuovere i criteri per le barriere informative.
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
ms.openlocfilehash: 62e9910a1b94862ba23ecdc63c0fea1ec644043a
ms.sourcegitcommit: c10eb675da725830e9776d2a0566ba3622eb361c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "49980079"
---
# <a name="manage-information-barrier-policies"></a>Gestire i criteri di barriera delle informazioni

Dopo aver [definito i criteri di barriera delle informazioni](information-barriers-policies.md), potrebbe essere necessario apportare modifiche a tali criteri o ai segmenti di utenti, come parte della [risoluzione dei problemi](information-barriers-troubleshooting.md) o come manutenzione regolare. Utilizzare questo articolo come guida.

## <a name="what-do-you-want-to-do"></a>Operazione desiderata

|**Azione**|**Descrizione**|
|:---------|:--------------|
| [Modificare gli attributi degli account utente](#edit-user-account-attributes) | Inserire gli attributi in Azure Active Directory che è possibile utilizzare per definire i segmenti.<br/>Modificare gli attributi degli account utente quando gli utenti non sono inclusi nei segmenti che devono essere, per modificare i segmenti in cui si trovano gli utenti o per definire segmenti che utilizzano attributi diversi. |
| [Modifica di un segmento](#edit-a-segment) | Modificare i segmenti quando si desidera modificare la modalità di definizione di un segmento. <br/>Ad esempio, è possibile che i segmenti siano stati definiti in origine utilizzando il *reparto* e ora si desidera utilizzare un altro attributo, come *membro*. |
| [Modificare un criterio](#edit-a-policy) | Modificare un criterio di barriera delle informazioni quando si desidera modificare la modalità di funzionamento di un criterio.<br/>Ad esempio, invece di bloccare le comunicazioni tra due segmenti, è possibile decidere se si desidera consentire la comunicazione solo tra alcuni segmenti. |
| [Impostare un criterio su stato inattivo](#set-a-policy-to-inactive-status) |Impostare un criterio sullo stato inattivo quando si desidera apportare modifiche a un criterio o quando non si desidera che un criterio venga applicato. |
| [Rimozione di un criterio](#remove-a-policy) | Rimuovere un criterio barriera informativo quando non è più necessario disporre di un criterio specifico. |
| [Arrestare un'applicazione di criteri](#stop-a-policy-application) | Eseguire questa azione quando si desidera interrompere il processo di applicazione dei criteri di barriera delle informazioni.<br/> L'interruzione di un'applicazione di criteri non è immediata e non annulla i criteri già applicati agli utenti. |
| [Definire i criteri per le barriere informative](information-barriers-policies.md) | Definire un criterio barriera informativo se non si dispone già di tali criteri e si devono limitare o limitare le comunicazioni tra gruppi specifici di utenti. |
| [Risoluzione dei problemi relativi alle barriere informative](information-barriers-troubleshooting.md) | Fare riferimento a questo articolo quando si verificano problemi imprevisti con barriere informative. |

> [!IMPORTANT]
> Per eseguire le attività descritte in questo articolo, è necessario essere assegnati a un ruolo appropriato, ad esempio uno dei seguenti:<br/>-Microsoft 365 Enterprise Global Administrator<br/>-Amministratore globale<br/>-Compliance Administrator<br/>-IB Compliance Management (questo è un nuovo ruolo)<br><br>Per ulteriori informazioni sui prerequisiti per le barriere informative, vedere [prerequisiti (per i criteri barriera informativi)](information-barriers-policies.md#prerequisites).<br><br> Assicurarsi di eseguire [la connessione al centro sicurezza & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).

## <a name="edit-user-account-attributes"></a>Modificare gli attributi degli account utente

Utilizzare questa procedura per modificare gli attributi utilizzati per la segmentazione degli utenti. Ad esempio, se si utilizza un attributo Department e uno o più account utente attualmente non dispongono di alcun valore elencato per Department, è necessario modificare tali account utente in modo da includere informazioni di reparto. Gli attributi degli account utente vengono utilizzati per definire i segmenti in modo che i criteri di barriera delle informazioni possano essere assegnati.

1. Per visualizzare i dettagli relativi a un account utente specifico, ad esempio i valori degli attributi e i segmenti assegnati, utilizzare il cmdlet **Get-InformationBarrierRecipientStatus** con i parametri Identity.

    |**Sintassi**|**Esempio**|
    |:---------|:----------|
    | `Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <p> È possibile utilizzare qualsiasi valore che identifichi in modo univoco ogni utente, ad esempio nome, alias, nome distinto, nome di dominio canonico, indirizzo di posta elettronica o GUID. <p> È inoltre possibile utilizzare questo cmdlet per un singolo `Get-InformationBarrierRecipientStatus -Identity <value>` utente: |`Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <p> In questo esempio, si fa riferimento a due account utente in Office 365: *meganb* per *Megan* e *alexw* per *Alex*. |

2. Determinare l'attributo che si desidera modificare per i profili dell'account utente. Per ulteriori informazioni, vedere [attributi per i criteri di barriera delle informazioni](information-barriers-attributes.md). 

3. Modificare uno o più account utente in modo da includere i valori dell'attributo selezionato nel passaggio precedente. Per eseguire questa operazione, utilizzare una delle seguenti procedure:

    - Per modificare un singolo account, vedere [aggiungere o aggiornare le informazioni sul profilo di un utente utilizzando Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).

    - Per modificare più account o utilizzare PowerShell per modificare un singolo account, vedere [Configure user account properties with Office 365 PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/configure-user-account-properties-with-microsoft-365-powershell).

## <a name="edit-a-segment"></a>Modifica di un segmento

Utilizzare questa procedura per modificare la definizione di un segmento di utenti. Ad esempio, è possibile modificare il nome di un segmento o il filtro utilizzato per determinare chi è incluso nel segmento.

1. Per visualizzare tutti i segmenti esistenti, utilizzare il cmdlet **Get-OrganizationSegment** .

    Sintassi `Get-OrganizationSegment`

    Verrà visualizzato un elenco di segmenti e dettagli per ognuno, ad esempio il tipo di segmento, il valore di UserGroupFilter, che ha creato o modificato l'oggetto, il GUID e così via.

    > [!TIP]
    > Stampa o salvataggio dell'elenco dei segmenti per riferimento in un secondo momento. Ad esempio, se si desidera modificare un segmento, è necessario conoscere il nome o il valore di identificazione (utilizzato con il parametro Identity).

2. Per modificare un segmento, utilizzare il cmdlet **set-OrganizationSegment** con il parametro **Identity** e i dettagli rilevanti.

    |**Sintassi**|**Esempio**|
    |:---------|:----------|
    | `Set-OrganizationSegment -Identity GUID -UserGroupFilter "attribute -eq 'attributevalue'"` |`Set-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd -UserGroupFilter "Department -eq 'HRDept'"` <p> In questo esempio, per il segmento che ha il GUID *c96e0837-C232-4a8a-841E-ef45787d8fcd*, il nome del reparto è stato aggiornato in "HRDept". |

Dopo aver completato la modifica dei segmenti per l'organizzazione, è possibile [definire](information-barriers-policies.md#part-2-define-information-barrier-policies) o [modificare](#edit-a-policy) i criteri di barriera delle informazioni.

## <a name="edit-a-policy"></a>Modificare un criterio

1. Per visualizzare un elenco dei criteri di barriera delle informazioni correnti, utilizzare il cmdlet **Get-InformationBarrierPolicy** .

    Sintassi `Get-InformationBarrierPolicy`

    Nell'elenco dei risultati, identificare il criterio che si desidera modificare. Prendere nota del GUID e del nome del criterio.

2. Utilizzare il cmdlet **set-InformationBarrierPolicy** con un parametro **Identity** e specificare le modifiche che si desidera eseguire.

    Ad esempio, si supponga che sia stato definito un criterio per bloccare il segmento di *ricerca* dalla comunicazione con i segmenti *Sales* and *Marketing* . Il criterio è stato definito utilizzando il cmdlet seguente: `New-InformationBarrierPolicy -Name "Research-SalesMarketing" -AssignedSegment "Research" -SegmentsBlocked "Sales","Marketing"`

    Si supponga di voler cambiare la comunicazione in modo che gli utenti del segmento di *ricerca* possano comunicare solo con gli utenti del segmento *HR* . Per apportare questa modifica, è possibile utilizzare questo cmdlet: `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -SegmentsAllowed "HR"`

    In questo esempio, "SegmentsBlocked" viene modificato in "SegmentsAllowed" e viene specificato il segmento *HR* .

3. Dopo aver completato la modifica di un criterio, accertarsi di applicare le modifiche. (Vedere [Apply Information Barrier Policies](information-barriers-policies.md#part-3-apply-information-barrier-policies)).

## <a name="set-a-policy-to-inactive-status"></a>Impostare un criterio su stato inattivo

1. Per visualizzare un elenco dei criteri di barriera delle informazioni correnti, utilizzare il cmdlet **Get-InformationBarrierPolicy** .

    Sintassi `Get-InformationBarrierPolicy`

    Nell'elenco dei risultati, identificare il criterio che si desidera modificare (o rimuovere). Prendere nota del GUID e del nome del criterio.

2. Per impostare lo stato del criterio su inattivo, utilizzare il cmdlet **set-InformationBarrierPolicy** con un parametro Identity e il parametro state impostato su inattivo.

    |**Sintassi**|**Esempio**|
    |:---------|:----------|
    | `Set-InformationBarrierPolicy -Identity GUID -State Inactive` | `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c9377247 -State Inactive` <p> In questo esempio, viene impostato un criterio barriera informativo che include GUID *43c37853-EA10-4b90-a23d-ab8c9377247* su uno stato inattivo. |

3. Per applicare le modifiche, utilizzare il cmdlet **Start-InformationBarrierPoliciesApplication** .

    Sintassi `Start-InformationBarrierPoliciesApplication`

    Le modifiche vengono applicate dall'utente per l'organizzazione. Se l'organizzazione è di grandi dimensioni, il completamento di questo processo può richiedere 24 ore (o più). (Come linee guida generali, è necessario circa un'ora per elaborare gli account utente di 5.000).

A questo punto, uno o più criteri barriera informazioni sono impostati sullo stato inattivo. Da qui, è possibile eseguire una delle operazioni seguenti:

- Keep it as is (un criterio impostato su stato inattivo non ha alcun effetto sugli utenti)
- [Modificare un criterio](#edit-a-policy) 
- [Rimozione di un criterio](#remove-a-policy)

## <a name="remove-a-policy"></a>Rimozione di un criterio

1. Per visualizzare un elenco dei criteri di barriera delle informazioni correnti, utilizzare il cmdlet **Get-InformationBarrierPolicy** .

    Sintassi `Get-InformationBarrierPolicy`

    Nell'elenco dei risultati, identificare il criterio che si desidera rimuovere. Prendere nota del GUID e del nome del criterio. Verificare che il criterio sia impostato su stato inattivo.

2. Utilizzare il cmdlet **Remove-InformationBarrierPolicy** con un parametro Identity.

    |**Sintassi**|**Esempio**|
    |:---------|:----------|
    | `Remove-InformationBarrierPolicy -Identity GUID` | `Remove-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471` <p> In questo esempio viene rimosso il criterio che include GUID *43c37853-EA10-4b90-a23d-ab8c93772471*. |

    Quando richiesto, confermare la modifica.

3. Ripetere i passaggi 1-2 per ogni criterio che si desidera rimuovere.

4. Una volta terminata la rimozione dei criteri, applicare le modifiche. Per eseguire questa operazione, utilizzare il cmdlet **Start-InformationBarrierPoliciesApplication** .

    Sintassi `Start-InformationBarrierPoliciesApplication`

    Le modifiche vengono applicate dall'utente per l'organizzazione. Se l'organizzazione è di grandi dimensioni, il completamento di questo processo può richiedere 24 ore (o più).

## <a name="stop-a-policy-application"></a>Arrestare un'applicazione di criteri

Dopo aver avviato l'applicazione dei criteri di barriera delle informazioni, se si desidera impedire l'applicazione di tali criteri, utilizzare la procedura seguente. L'avvio del processo richiederà circa 30-35 minuti.

1. Per visualizzare lo stato dell'applicazione del criterio barriera alle informazioni più recente, utilizzare il cmdlet **Get-InformationBarrierPoliciesApplicationStatus** .

    Sintassi `Get-InformationBarrierPoliciesApplicationStatus`

    Tenere presente il GUID dell'applicazione.

2. Utilizzare il cmdlet **Stop-InformationBarrierPoliciesApplication** con un parametro Identity.

    |**Sintassi**|**Esempio**|
    |:---------|:----------|
    | `Stop-InformationBarrierPoliciesApplication -Identity GUID` | `Stop-InformationBarrierPoliciesApplication -Identity 46237888-12ca-42e3-a541-3fcb7b5231d1` <p> In questo esempio viene interrotto l'applicazione dei criteri di barriera delle informazioni. |

## <a name="resources"></a>Risorse

- [Ottenere una panoramica delle barriere informative](information-barriers.md)
- [Definire i criteri per le barriere informative](information-barriers-policies.md)
- [Per ulteriori informazioni, vedere barriere informative in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)
- [Attributi per i criteri delle barriere informative](information-barriers-attributes.md)
- [Risoluzione dei problemi relativi alle barriere informative](information-barriers-troubleshooting.md)
