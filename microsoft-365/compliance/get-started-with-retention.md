---
title: Informazioni sui criteri e sulle etichette di conservazione
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
- m365solution-mig
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Pronti per iniziare a implementare i criteri e le etichette di riservatezza per gestire i dati della tua organizzazione, ma in dubbio su come iniziare? Leggere alcune indicazioni utili per iniziare.
ms.openlocfilehash: 65c196f8838378a10263370b1377b3eb43b14915
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051908"
---
# <a name="get-started-with-retention-policies-and-retention-labels"></a>Informazioni sui criteri e sulle etichette di conservazione

>*[Indicazioni per l'assegnazione di licenze di Microsoft 365 per sicurezza e conformità](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

Pronti per iniziare a gestire i dati della tua organizzazione, conservando il contenuto che occorre mantenere ed eliminando il contenuto non necessario? Usare le seguenti indicazioni generali per iniziare:

1. **Comprendere il funzionamento della conservazione** in Microsoft 365, e identificare se necessario usare criteri o etichette di conservazione oppure una combinazione tra i due: [Informazioni sulla conservazione](retention.md)

2. **Identificare le impostazioni di conservazione e le azioni** necessarie per i criteri dell'organizzazione o le normative di settore.
    
    Nell'ambito di questo processo di valutazione, determinare se si userà [Gestione dei record](records-management.md).

3. **Creare criteri di conservazione e etichette di conservazione**, in base alle impostazioni e azioni di conservazione identificate.
    
    Per le etichette di conservazione, potrebbe risultare utile usare un [piano di archiviazione](file-plan-manager.md) per definire e perfezionare le etichette di conservazione in un foglio di calcolo. Successivamente, importare il foglio di calcolo per creare le etichette.
    
3. **Pubblicare e applicare le etichette di conservazione**. Anche se i criteri di conservazione sono pensati per una configurazione "imposta e dimentica", le etichette di conservazione sono blocchi predefiniti riutilizzabili che possono essere usati in più criteri e incorporati nei flussi di lavoro degli utenti. Vedere l'elenco degli [scenari comuni](#common-scenarios-for-retention-policies-and-retention-labels) per identificare il modo in cui è possibile usare le etichette di conservazione. 

## <a name="subscription-and-licensing-requirements-for-retention-policies-and-retention-labels"></a>Requisiti di abbonamento e licenza per i criteri e le etichette di conservazione

I criteri, le etichette di conservazione e i requisiti di licenza per gli utenti in base alle caratteristiche da usare sono supportati da una serie di abbonamenti diversi.

Per visualizzare le opzioni di licenza da assegnare agli utenti per trarre vantaggio dalle funzionalità di conformità di Microsoft 365, vedere [Indicazioni per l'assegnazione di licenze di Microsoft 365 per sicurezza e conformità](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance). Per la conservazione, vedere la sezione [Governance delle informazioni](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-governance) e il relativo file PDF o Excel per i requisiti di licenza a livello di funzionalità.

## <a name="permissions-required-to-create-and-manage-retention-policies-and-retention-labels"></a>Autorizzazioni necessarie per la creazione e gestione dei criteri ed etichette di conservazione

Ai membri del team di conformità che creeranno e gestiranno i criteri e le etichette di conservazione è necessario assegnare autorizzazioni per il [Centro conformità Microsoft 365](https://compliance.microsoft.com/). Per impostazione predefinita, l'amministratore del tenant (amministratore globale) ha accesso a questa posizione e può fornire l'accesso ai responsabili della conformità e ad altre persone senza concedere loro tutte le autorizzazioni di un amministratore del tenant. Per concedere le autorizzazioni per questa amministrazione limitata, è consigliabile aggiungere gli utenti al gruppo di ruoli di amministratore **Amministratore di conformità**.

In alternativa all'utilizzo di questo ruolo predefinito, è possibile creare un nuovo gruppo di ruoli e aggiungere a questo gruppo il ruolo **Gestione conservazione**. Per sola lettura, usare **Gestione conservazione solo visualizzazione**. 

Per altre informazioni su gruppi di ruoli e ruoli, vedere [Autorizzazioni nel Centro sicurezza e conformità](../security/defender-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center).

Per istruzioni su come aggiungere utenti a gruppi di ruoli e assegnare i ruoli, vedere [Concedere agli utenti l'accesso al Centro sicurezza e conformità](../security/defender-365-security/grant-access-to-the-security-and-compliance-center.md).

Queste autorizzazioni sono necessarie solo per creare, configurare e applicare criteri di conservazione ed etichette di conservazione. La persona che configura tali criteri ed etichette non ha bisogno di accedere al contenuto.

## <a name="common-scenarios-for-retention-policies-and-retention-labels"></a>Scenari comuni sui criteri e le etichette di conservazione

Usare la seguente tabella per eseguire il mapping dei requisiti aziendali relativi agli scenari di conservazione supportati dai criteri e le etichette di conservazione.

|Operazione da eseguire|Documentazione|
|----------------|---------------|
|Configurare in modo efficiente le azioni di conservazione ed eliminazione tramite i servizi di Microsoft 365: <br />-  Exchange  <br />- SharePoint  <br />- OneDrive  <br />- Gruppi di Microsoft 365 <br />- Skype for Business  <br />- Microsoft Teams <br />- Rete Yammer |[Creare e configurare criteri di conservazione](create-retention-policies.md)|
|Consentire ad amministratori e utenti di applicare manualmente azioni di conservazione ed eliminazione per documenti e messaggi di posta elettronica: <br />-  SharePoint <br />- OneDrive <br />- Outlook e Outlook sul Web|[Creare etichette di conservazione e applicarle nelle app](create-apply-retention-labels.md)|
|Consentire agli amministratori del sito di impostare azioni di conservazione ed eliminazione predefinite per tutto il contenuto di una raccolta, una cartella o un set di documenti di SharePoint|[Creare etichette di conservazione e applicarle nelle app](create-apply-retention-labels.md)|
|Consentire agli utenti di applicare automaticamente azioni di conservazione ed eliminazione ai messaggi di posta elettronica con le regole di Outlook|[Creare etichette di conservazione e applicarle nelle app](create-apply-retention-labels.md)|
|Consentire agli amministratori di applicare azioni di conservazione ed eliminazione a un modello di analisi dei documenti, in modo che vengano applicate automaticamente ai documenti identificati in una raccolta di SharePoint.|[Creare etichette di conservazione e applicarle nelle app](create-apply-retention-labels.md)|
|Applicare automaticamente azioni di conservazione ed eliminazione ai documenti e ai messaggi di posta elettronica |[Applicare automaticamente un'etichetta di conservazione al contenuto](apply-retention-labels-automatically.md)|
|Avviare il periodo di conservazione quando si verifica un evento, ad esempio:  <br />- Dipendenti che lasciano l'organizzazione <br />- Scadenza contratti <br />- Fine del ciclo di vita del prodotto| [Avviare la conservazione al verificarsi di un evento](event-driven-retention.md)|
|Limitare le modifiche ai criteri per soddisfare i requisiti normativi o garantire la protezione da amministratori non autorizzati| [Usare la protezione dell'archiviazione per limitare le modifiche ai criteri di conservazione e ai criteri per le etichette di conservazione](retention-preservation-lock.md)
|Assicurarsi il tutto sia revisionato e approvato prima di eliminare il contenuto al termine del periodo di conservazione|[Revisioni per l'eliminazione](disposition.md#disposition-reviews) |
| Monitorare come e dove le impostazioni di conservazione ed eliminazione sono applicate agli elementi | [Monitoraggio delle etichette di conservazione](retention.md#monitoring-retention-labels) |
|Usare una soluzione di gestione dei record singola per documenti e messaggi di posta elettronica |[Informazioni sulla gestione dei record](records-management.md) |

Se si usano etichette di conservazione per la gestione dei record, esistono ulteriori scenari, univoci per le etichette di conservazione, che consentono di contrassegnare il contenuto come record. Vedere [Scenari comuni per la gestione dei record](get-started-with-records-management.md#common-scenarios-for-records-management).

## <a name="end-user-documentation-for-retention"></a>Documentazione per l'utente finale per la conservazione

La maggior parte dei criteri di conservazione funzionano in modo discreto in background senza interazione dell'utente. Pertanto, richiedono poca documentazione per gli utenti. I criteri di conservazione per Teams informano gli utenti quando i loro messaggi sono stati eliminati attraverso un collegamento a [Messaggi di Teams sui criteri di conservazione](https://support.microsoft.com/office/teams-messages-about-retention-policies-c151fa2f-1558-4cf9-8e51-854e925b483b).

Poiché le etichette di conservazione sono presenti nelle app di Microsoft 365, assicurarsi di fornire indicazioni agli utenti finali e all'help desk prima di distribuire le etichette alla rete di produzione.

La documentazione per gli utenti finali più efficace è costituita dalle indicazioni e istruzioni personalizzate per i nomi e le configurazioni delle etichette di conservazione scelte. Per informazioni su un pacchetto di download da usare per formare gli utenti e guidare l'adozione, leggere il post di blog seguente: [Formazione dell’utente finale sulle etichette di conservazione in M365 - Come velocizzare l'adozione](https://techcommunity.microsoft.com/t5/microsoft-security-and/end-user-training-for-retention-labels-in-m365-how-to-accelerate/ba-p/1750861).

Nella sezione seguente sono disponibili anche le istruzioni per gli utenti di base: [Applicare manualmente le etichette di conservazione](create-apply-retention-labels.md#manually-apply-retention-labels).