---
title: Introduzione alla gestione dei record in Microsoft 365
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Se è necessaria una soluzione di gestione dei record per Microsoft 365 che gestisca i contenuti di valore per obblighi legali, aziendali o normativi, di seguito vengono riportate alcune indicazioni utili per iniziare.
ms.openlocfilehash: 0382c1419654e4c1d2c809b3a9c32252fd50f554
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244345"
---
# <a name="get-started-with-records-management"></a>Introduzione alla gestione dei record

>*[Indicazioni per l'assegnazione di licenze di Microsoft 365 per sicurezza e conformità](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

Pronto a iniziare a gestire i contenuti di valore dell'organizzazione per gli obblighi legali, aziendali o normativi usando una soluzione di gestione dei record in Microsoft 365? Per iniziare, usare le indicazioni seguenti:

1. **Conoscere la soluzione di gestione dei record** e le azioni consentite o bloccate quando i documenti e i messaggi di posta elettronica vengono dichiarati come record: [Informazioni sulla gestione dei record](records-management.md). 

2. **Conoscere le etichette di conservazione e il meccanismo di conservazione** per SharePoint ed Exchange, perché le etichette di conservazione vengono usate per dichiarare i record: [Informazioni sui criteri e sulle etichette di conservazione](retention.md)

3. **Creare il piano di archiviazione per le impostazioni e le azioni di conservazione** [importando un piano esistente](file-plan-manager.md#import-retention-labels-into-your-file-plan ) se disponibile oppure creare [nuove etichette di conservazione che dichiarano i record](declare-records.md).

4. **Pubblicare e applicare le etichette di conservazione**. Le etichette di conservazione sono blocchi predefiniti riutilizzabili che possono essere usati in più criteri e incorporati nei flussi di lavoro degli utenti: 
    
    - [Creare etichette di conservazione e applicarle nelle app](create-apply-retention-labels.md)
    - [Applicare automaticamente un'etichetta di conservazione al contenuto](apply-retention-labels-automatically.md)

## <a name="subscription-and-licensing-requirements-for-records-management"></a>Requisiti di abbonamento e licenza per la gestione dei record 

Numerosi abbonamenti diversi supportano la gestione dei record e i requisiti di licenza per gli utenti dipendono dalle funzionalità utilizzate.

Per visualizzare le opzioni di licenza da assegnare agli utenti per trarre vantaggio dalle funzionalità di conformità di Microsoft 365, vedere [Indicazioni per l'assegnazione di licenze di Microsoft 365 per sicurezza e conformità](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance). Per la gestione dei record, vedere la sezione [Gestione dei record](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#records-management) e il relativo file PDF o Excel per i requisiti di licenza a livello di funzionalità.

## <a name="permissions-required-for-records-management"></a>Autorizzazioni necessarie per la gestione dei record

Ai membri del team di conformità responsabili della gestione dei record è necessario assegnare autorizzazioni per il [Centro conformità Microsoft 365](https://compliance.microsoft.com/). Per impostazione predefinita, l'amministratore del tenant (amministratore globale) ha accesso a questa posizione e può fornire l'accesso ai responsabili della conformità e ad altre persone senza concedere loro tutte le autorizzazioni di un amministratore del tenant. Per concedere queste autorizzazioni di amministrazione limitata, è consigliabile aggiungere gli utenti al gruppo di ruoli di amministratore **Gestione dei record**, che concede le autorizzazioni a tutte le funzionalità relative alla gestione record, tra cui [la revisione e verifica per l’eliminazione](disposition.md). 

Per un ruolo di sola lettura, è possibile creare un nuovo gruppo di ruoli e aggiungere a questo gruppo il ruolo **Gestione dei record View-Only**. 

Per altre informazioni su questi gruppi di ruoli e ruoli, vedere [Autorizzazioni nel Centro sicurezza e conformità](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center).

Per istruzioni su come aggiungere utenti a gruppi di ruoli e assegnare i ruoli, vedere [Concedere agli utenti l'accesso al Centro sicurezza e conformità](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).

Queste autorizzazioni sono necessarie solo per creare, configurare e applicare etichette di conservazione che dichiarano i record e gestire le eliminazioni. La persona che configura tali etichette non ha bisogno di accedere al contenuto.

## <a name="common-scenarios-for-records-management"></a>Scenari comuni per la gestione dei record

Usare la seguente tabella per eseguire il mapping dei requisiti aziendali relativi agli scenari supportati dalla gestione dei record.

> [!NOTE]
> Poiché la gestione dei record usa etichette di conservazione per contrassegnare un elemento come record, molti scenari in questa tabella sono elencati anche come [scenari comuni per i criteri e le etichette di conservazione](get-started-with-retention.md#common-scenarios-for-retention-policies-and-retention-labels).

|Operazione da eseguire|Documentazione|
|----------------|---------------|
|Dichiarare un record |[Usare le etichette di conservazione per dichiarare i record](declare-records.md)|
|Aggiornare un record |[Usare il controllo delle versioni per aggiornare i record archiviati in SharePoint o OneDrive](record-versioning.md)|
|Consentire ad amministratori e utenti di applicare manualmente azioni di conservazione ed eliminazione per documenti e messaggi di posta elettronica: <br />-  SharePoint <br />- OneDrive <br />- Outlook e Outlook sul Web|[Creare etichette di conservazione e applicarle nelle app](create-apply-retention-labels.md)|
|Consentire agli amministratori del sito di impostare azioni di conservazione ed eliminazione predefinite per tutto il contenuto di una raccolta, una cartella o un set di documenti di SharePoint|[Creare etichette di conservazione e applicarle nelle app](create-apply-retention-labels.md)|
|Consentire agli utenti di applicare automaticamente azioni di conservazione ed eliminazione ai messaggi di posta elettronica con le regole di Outlook|[Creare etichette di conservazione e applicarle nelle app](create-apply-retention-labels.md)|
|Consentire agli amministratori di applicare azioni di conservazione ed eliminazione a un modello di analisi dei documenti, in modo che vengano applicate automaticamente ai documenti identificati in una raccolta di SharePoint.|[Creare etichette di conservazione e applicarle nelle app](create-apply-retention-labels.md)|
|Applicare automaticamente azioni di conservazione ed eliminazione ai documenti e ai messaggi di posta elettronica |[Applicare automaticamente un'etichetta di conservazione al contenuto](apply-retention-labels-automatically.md)|
|Avviare il periodo di conservazione quando si verifica un evento, ad esempio:  <br />- Dipendenti che lasciano l'organizzazione <br />- Scadenza contratti <br />- Fine del ciclo di vita del prodotto| [Avviare la conservazione al verificarsi di un evento](event-driven-retention.md)|
|Limitare le modifiche ai criteri per soddisfare i requisiti normativi o garantire la protezione da amministratori non autorizzati| [Usare la protezione dell'archiviazione per limitare le modifiche ai criteri di conservazione e ai criteri per le etichette di conservazione](retention-preservation-lock.md)
|Gestire il ciclo di vita di tipi di documenti diversi in SharePoint| [Usare etichette di riservatezza per gestire il ciclo di vita dei documenti archiviati in SharePoint](auto-apply-retention-labels-scenario.md)|
|Assicurarsi il tutto sia revisionato e approvato prima di eliminare il contenuto al termine del periodo di conservazione|[Revisioni per l'eliminazione](disposition.md#disposition-reviews) |
|Disporre di una prova di eliminazione quando il contenuto viene eliminato definitivamente al termine del periodo di conservazione|[Eliminazione dei record](disposition.md#disposition-of-records) |
| Monitorare come e dove le impostazioni di conservazione ed eliminazione sono applicate agli elementi | [Monitoraggio delle etichette di conservazione](retention.md#monitoring-retention-labels) |

## <a name="end-user-documentation-for-records"></a>Documentazione per gli utenti finali sui record

Le etichette di conservazione che vengono usate per la gestione record sono presenti nelle app di Microsoft 365. Assicurarsi di fornire indicazioni agli utenti finali e all'help desk prima di distribuire le etichette di conservazione alla rete di produzione.

Per aiutare gli utenti ad applicare le etichette di conservazione in SharePoint e OneDrive, incluse le informazioni su come sbloccare i record per la modifica, vedere [Applicare etichette di conservazione ai file in SharePoint o OneDrive](https://support.microsoft.com/office/apply-retention-labels-to-files-in-sharepoint-or-onedrive-11a6835b-ec9f-40db-8aca-6f5ef18132df).

Tuttavia, la documentazione per gli utenti finali più efficace è costituita dalle indicazioni e istruzioni personalizzate per i nomi e le configurazioni delle etichette di conservazione scelte. Per informazioni su un pacchetto di download da usare per formare gli utenti e guidare l'adozione, leggere il post di blog seguente: [Formazione dell’utente finale sulle etichette di conservazione in M365 - Come velocizzare l'adozione](https://techcommunity.microsoft.com/t5/microsoft-security-and/end-user-training-for-retention-labels-in-m365-how-to-accelerate/ba-p/1750861).
