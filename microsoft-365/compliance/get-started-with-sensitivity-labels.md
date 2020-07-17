---
title: Iniziare a usare le etichette di riservatezza
f1.keywords:
- CSH
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
description: Pronti per iniziare a implementare le etichette di riservatezza per proteggere i dati dell'organizzazione, ma in dubbio su come iniziare? Leggere alcune guide pratiche utili per iniziare il percorso di implementazione dell'etichettatura.
ms.openlocfilehash: 1b22619b200cd0cdcccfdc9be0d52b0eaa25f303
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/30/2020
ms.locfileid: "44936373"
---
# <a name="get-started-with-sensitivity-labels"></a>Iniziare a usare le etichette di riservatezza

>*[Indicazioni per l'assegnazione di licenze di Microsoft 365 per sicurezza e conformità](https://aka.ms/ComplianceSD).*

Per informazioni sulle etichette di riservatezza e su come favoriscono la protezione dei dati dell'organizzazione, vedere [informazioni sulle etichette di riservatezza](sensitivity-labels.md).

Se si ha [Azure Information Protection](https://docs.microsoft.com/azure/information-protection/what-is-information-protection), determinare se è necessario eseguire la migrazione delle etichette alla piattaforma di etichetta unificata e quale client di etichettatura usare:
- [Come si può determinare se il tenant si trova nella piattaforma di etichettatura unificata?](https://docs.microsoft.com/azure/information-protection/faqs#how-can-i-determine-if-my-tenant-is-on-the-unified-labeling-platform)
- [Scegliere il client di etichettatura da usare per i computer Windows](https://docs.microsoft.com/azure/information-protection/rms-client/use-client#choose-which-labeling-client-to-use-for-windows-computers)

Quando si è pronti per iniziare a proteggere i dati dell'organizzazione usando le etichette di riservatezza:

1. **Creare le etichette.** Creare e assegnare un nome alle etichette di riservatezza in base alla tassonomia di classificazione dell'organizzazione per i diversi livelli di riservatezza del contenuto. Usare termini o nomi comuni che abbiano senso per gli utenti. Se non si ha già una tassonomia stabilita, è consigliabile iniziare con nomi di etichetta come Personale, Pubblico, Generale, Riservato ed Estremamente riservato. Sarà poi possibile usare sottoetichette per raggruppare le etichette simili per categoria. Quando si crea un'etichetta, usare il testo della descrizione comando per aiutare gli utenti a selezionare l'etichetta appropriata.
    
    Per indicazioni più approfondite su come definire una tassonomia di classificazione, scaricare il white paper "Data Classification & Sensitivity Label Taxonomy" (Tassonomia di etichette di riservatezza e classificazione dei dati) dal [Service Trust Portal](https://aka.ms/DataClassificationWhitepaper).

2. **Definire le caratteristiche di ogni etichetta.** Configurare le impostazioni di protezione che si vogliono associare a ciascuna etichetta. Ad esempio, a un contenuto con un basso grado di riservatezza (come un'etichetta "Generale") si potrebbe applicare solo un'intestazione o un piè di pagina, mentre a un contenuto con un maggiore grado di riservatezza (come un'etichetta "Riservato") si potrebbero applicare una filigrana e la crittografia.

3. **Pubblicare le etichette.** Dopo aver configurato le etichette di riservatezza, pubblicarle usando un criterio di etichetta. Decidere quali utenti e gruppi devono avere le etichette e quali impostazioni dei criteri usare. Una singola etichetta è riutilizzabile, vale a dire che è possibile definirla una sola volta e quindi includerla in diversi criteri di etichetta assegnati a più utenti. Ad esempio, è possibile provare a usare le etichette di riservatezza assegnando un criterio di etichetta a pochi utenti. Successivamente, una volta pronti a distribuire le etichette nell'organizzazione, si potrà creare un nuovo criterio per le etichette e, stavolta, specificare tutti gli utenti.

Procedura di base per la distribuzione e l'applicazione di etichette di riservatezza:

![Diagramma che mostra il flusso di lavoro per le etichette di riservatezza](../media/Sensitivity-label-flow.png)

## <a name="subscription-and-licensing-requirements-for-sensitivity-labels"></a>Requisiti di abbonamento e licenza per le etichette di riservatezza

Numerosi abbonamenti diversi supportano le etichette di riservatezza e i requisiti di licenza per gli utenti dipendono dalle funzionalità utilizzate.

Per visualizzare le opzioni di licenza da assegnare agli utenti per trarre vantaggio dalle funzionalità di conformità di Microsoft 365 a partire dal 1° aprile 2020, vedere [Indicazioni per l'assegnazione di licenze di Microsoft 365 per sicurezza e conformità](https://aka.ms/ComplianceSD). Per le etichette di riservatezza, vedere la sezione [Information Protection](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection) e il download del relativo PDF o Excel.

## <a name="permissions-required-to-create-and-manage-sensitivity-labels"></a>Autorizzazioni necessarie per creare e gestire etichette di riservatezza

I membri del team di conformità che creano un'etichetta di riservatezza necessitano delle autorizzazioni per il Centro conformità Microsoft 365, il Centro sicurezza Microsoft 365 o il Centro sicurezza e conformità. 

Per impostazione predefinita, gli amministratori globali del tenant hanno accesso a queste interfacce di amministrazione e possono fornire ai responsabili della conformità e ad altri utenti l'accesso, senza concedere tutte le autorizzazioni di un amministratore tenant. Per l'accesso di amministratore con delega, aggiungere utenti al gruppo di ruoli di **Amministratore dati di conformità**, **Amministratore di conformità** o **Amministratore della sicurezza**. 

In alternativa all'utilizzo dei ruoli predefiniti, è possibile creare un nuovo gruppo di ruoli e aggiungere l’**amministratore dell'etichetta di riservatezza** o la **configurazione dell’organizzazione** al gruppo. Per un ruolo di sola lettura, usare **Lettore di etichette di riservatezza**. 

Per istruzioni su come aggiungere utenti ai ruoli predefiniti o creare i gruppi di ruoli, vedere [Concedere agli utenti l'accesso al Centro sicurezza e conformità di Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/grant-access-to-the-security-and-compliance-center).

Queste autorizzazioni sono necessarie solo per creare e configurare le etichette di riservatezza e i relativi criteri di etichetta. Non sono invece necessarie per applicare le etichette nelle app o nei servizi. Se sono necessarie autorizzazioni aggiuntive per configurazioni specifiche relative alle etichette di riservatezza, tali autorizzazioni verranno riportate nelle rispettive istruzioni nella documentazione.

## <a name="deployment-strategy-for-sensitivity-labels"></a>Strategia di distribuzione per le etichette di riservatezza

Una strategia efficace per distribuire etichette di riservatezza per un'organizzazione consiste nel creare un team operativo virtuale che identifichi e gestisca le esigenze aziendali e tecniche, i test del modello di prova, i punti controllo interni e le approvazioni nonché la distribuzione finale per l'ambiente di produzione.

Se si utilizza la tabella presente nella sezione seguente, è consigliabile identificare uno o due scenari principali che corrispondano ai propri requisiti aziendali più rilevanti. Dopo la distribuzione di questi scenari, tornare all'elenco per identificare una o due priorità successive per la distribuzione.

Ulteriori indicazioni generali per la distribuzione sono disponibili nella guida scaricabile di Microsoft 365 sull'accelerazione della distribuzione di Information Protection e della Conformità. Per maggiori informazioni, vedere il post del blog [Guida all'accelerazione della distribuzione di Microsoft Information Protection e della Conformità](https://techcommunity.microsoft.com/t5/microsoft-security-and/microsoft-information-protection-and-compliance-deployment/ba-p/1403493).

## <a name="common-scenarios-for-sensitivity-labels"></a>Scenari comuni per le etichette di riservatezza

Tutti gli scenari richiedono di [Creare e configurare etichette di riservatezza e i relativi criteri](create-sensitivity-labels.md).

|Operazione da eseguire|Documentazione|
|----------------|---------------|
|Gestire le etichette di riservatezza per le app di Office in modo che il contenuto venga etichettato non appena creato |[Usare le etichette di riservatezza nelle app di Office](sensitivity-labels-office-apps.md)|
|Consentire agli utenti di etichettare e proteggere i file dai computer Windows tramite app di Office, Esplora file e PowerShell|[Client di etichettatura unificata di Azure Information Protection per Windows](https://docs.microsoft.com/azure/information-protection/rms-client/aip-clientv2)|
|Crittografare documenti e messaggi di posta elettronica con etichette di riservatezza e limitare gli utenti autorizzati ad accedervi e il relativo uso |[Limitare l'accesso al contenuto utilizzando le etichette di riservatezza per applicare la crittografia](encryption-sensitivity-labels.md)|
|Abilitare le etichette di riservatezza per Office sul Web, con supporto per creazione condivisa, eDiscovery, prevenzione della perdita dei dati e ricerca, anche quando i documenti sono crittografati | [Abilitare le etichette di riservatezza per i file di Office in SharePoint e OneDrive](sensitivity-labels-sharepoint-onedrive-files.md)
|Applicare automaticamente etichette di riservatezza ai documenti e ai messaggi di posta elettronica | [Applicare automaticamente un'etichetta di riservatezza al contenuto](apply-sensitivity-label-automatically.md)|
|Usare le etichette di riservatezza per proteggere il contenuto in Teams e SharePoint |[Usare le etichette di riservatezza con Microsoft Teams, gruppi di Microsoft 365 e siti di SharePoint](sensitivity-labels-teams-groups-sites.md)|
|Individuare, etichettare e proteggere i file archiviati negli archivi dati locali |[Distribuzione dello strumento di analisi Azure Information Protection per classificare e proteggere automaticamente i file](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner)|
|Individuare, etichettare e proteggere i file archiviati negli archivi dati nel cloud|[Individuare, classificare, etichettare e proteggere i dati regolamentati e sensibili archiviati nel cloud](https://docs.microsoft.com/cloud-app-security/best-practices#discover-classify-label-and-protect-regulated-and-sensitive-data-stored-in-the-cloud)|
|Applicare e visualizzare le etichette di riservatezza in Power BI e proteggere i dati durante l'esportazione|[Protezione dei dati in Power BI ](https://docs.microsoft.com/power-bi/admin/service-security-data-protection-overview)|
|Monitorare e capire come vengono usate le etichette di riservatezza nell'organizzazione|[Conoscere i dati - Panoramica della classificazione dei dati](data-classification-overview.md) <br /><br /> [Visualizzare l'utilizzo delle etichette con Analisi delle etichette](label-analytics.md)|

## <a name="end-user-documentation-for-sensitivity-labels"></a>Documentazione per gli utenti finali sulle etichette di riservatezza

La documentazione per gli utenti finali più efficace è costituita dalle indicazioni e dalle istruzioni personalizzate per i nomi e le configurazioni delle etichette scelti. Tuttavia, è possibile utilizzare le risorse seguenti per le istruzioni di base:   

- [Applicare le etichette di riservatezza ai file e ai messaggi di posta elettronica in Office](https://support.microsoft.com/it-IT/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)
    - [Problemi noti relativi alle etichette di riservatezza in Office](https://support.microsoft.com/it-IT/office/known-issues-with-sensitivity-labels-in-office-b169d687-2bbd-4e21-a440-7da1b2743edc)

- [Applicare automaticamente o consigliare l'applicazione di etichette di riservatezza ai file e ai messaggi di posta elettronica in Office](https://support.office.com/article/automatically-apply-or-recommend-sensitivity-labels-to-your-files-and-emails-in-office-622e0d9c-f38c-470a-bcdb-9e90b24d71a1)
    - [Problemi noti con l'applicazione automatica o consigliata delle etichette di riservatezza](https://support.office.com/article/known-issues-with-automatically-applying-or-recommending-sensitivity-labels-451698ae-311b-4d28-83aa-a839a66f6efc)

- [Manuale dell’utente per l’etichettatura unificata di Azure Information Protection](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-user-guide)


