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
ms.openlocfilehash: efb0d8401cca8fd0e8c2450a5d35788015f37dad
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42073179"
---
# <a name="get-started-with-sensitivity-labels"></a>Iniziare a usare le etichette di riservatezza

Per informazioni sulle etichette di riservatezza e su come favoriscono la protezione dei dati dell'organizzazione, vedere [informazioni sulle etichette di riservatezza](sensitivity-labels.md).

Se si ha [Azure Information Protection](https://docs.microsoft.com/azure/information-protection/what-is-information-protection), determinare se è necessario eseguire la migrazione delle etichette alla piattaforma di etichetta unificata e quale client di etichettatura usare:
- [Come si può determinare se il tenant si trova nella piattaforma di etichettatura unificata?](https://docs.microsoft.com/azure/information-protection/faqs#how-can-i-determine-if-my-tenant-is-on-the-unified-labeling-platform)
- [Scegliere il client di etichettatura da usare per i computer Windows](https://docs.microsoft.com/azure/information-protection/rms-client/use-client#choose-which-labeling-client-to-use-for-windows-computers)

Quando si è pronti per iniziare a proteggere i dati dell'organizzazione usando le etichette di riservatezza:

1. **Creare le etichette.** Creare e assegnare un nome alle etichette di riservatezza in base alla tassonomia di classificazione dell'organizzazione per i diversi livelli di riservatezza del contenuto. Usare termini o nomi comuni che abbiano senso per gli utenti. Se non si ha già una tassonomia stabilita, è consigliabile iniziare con nomi di etichetta come Personale, Pubblico, Generale, Riservato ed Estremamente riservato. Sarà poi possibile usare sottoetichette per raggruppare le etichette simili per categoria. Quando si crea un'etichetta, usare il testo della descrizione comando per aiutare gli utenti a selezionare l'etichetta appropriata.

2. **Definire le caratteristiche di ogni etichetta.** Configurare le impostazioni di protezione che si vogliono associare a ciascuna etichetta. Ad esempio, a un contenuto con un basso grado di riservatezza (come un'etichetta "Generale") si potrebbe applicare solo un'intestazione o un piè di pagina, mentre a un contenuto con un maggiore grado di riservatezza (come un'etichetta "Riservato") si potrebbero applicare una filigrana, la crittografia e la protezione dell'endpoint.

3. **Pubblicare le etichette.** Dopo aver configurato le etichette di riservatezza, pubblicarle usando un criterio di etichetta. Decidere quali utenti e gruppi devono avere le etichette e quali impostazioni dei criteri usare. Una singola etichetta è riutilizzabile, vale a dire che è possibile definirla una sola volta e quindi includerla in diversi criteri di etichetta assegnati a più utenti. Ad esempio, è possibile provare a usare le etichette di riservatezza assegnando un criterio di etichetta a pochi utenti. Successivamente, una volta pronti a distribuire le etichette nell'organizzazione, si potrà creare un nuovo criterio per le etichette e, stavolta, specificare tutti gli utenti.

Ecco il flusso di base delle operazioni eseguite da amministratore, utente e app e servizi di Office per consentire il funzionamento delle etichette di riservatezza:

![Diagramma che mostra il flusso di lavoro per le etichette di riservatezza](../media/Sensitivity-label-flow.png)

## <a name="common-scenarios-for-sensitivity-labels"></a>Scenari comuni per le etichette di riservatezza

Usare la documentazione seguente a supporto della distribuzione delle etichette di riservatezza:

|Operazione da eseguire|Documentazione|
|----------------|---------------|
|Creare e pubblicare etichette di riservatezza per proteggere i dati dell'organizzazione|[Creare e configurare etichette di riservatezza e i relativi criteri](create-sensitivity-labels.md)|
|Crittografare documenti e messaggi di posta elettronica con etichette di riservatezza e limitare gli utenti autorizzati ad accedervi e l’uso del contenuto |[Limitare l'accesso al contenuto utilizzando le etichette di riservatezza per applicare la crittografia](encryption-sensitivity-labels.md)|
|Abilitare le funzionalità di collaborazione in SharePoint e OneDrive per i documenti etichettati con crittografia | [Abilitare le etichette di riservatezza per i file di Office in SharePoint e OneDrive (anteprima pubblica)](sensitivity-labels-sharepoint-onedrive-files.md)
|Gestire le etichette di riservatezza per le app di Office in modo che il contenuto venga etichettato non appena creato |[Usare le etichette di riservatezza nelle app di Office](sensitivity-labels-office-apps.md)|
|Applicare automaticamente etichette di riservatezza o consigliare etichette agli utenti al momento della creazione del contenuto | [Applicare automaticamente un'etichetta di riservatezza al contenuto](apply-sensitivity-label-automatically.md)|
|Usare le etichette di riservatezza per proteggere il contenuto in Teams e SharePoint |[Usare le etichette di riservatezza con Microsoft Teams, gruppi di Office 365 e siti di SharePoint (anteprima pubblica)](sensitivity-labels-teams-groups-sites.md)|
|Individuare, etichettare e proteggere i file archiviati negli archivi dati locali |[Distribuzione dello strumento di analisi di Azure Information Protection per classificare e proteggere automaticamente i file](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner)|
|Individuare, etichettare e proteggere i file archiviati negli archivi dati nel cloud |[Individuare, classificare, etichettare e proteggere i dati regolamentati e sensibili archiviati nel cloud](https://docs.microsoft.com/cloud-app-security/best-practices#discover-classify-label-and-protect-regulated-and-sensitive-data-stored-in-the-cloud)|
|Visualizzare il modo in cui le etichette di riservatezza vengono usate per creare report sullo stato di distribuzione e ottimizzare la configurazione delle etichette|[Visualizzare l'utilizzo delle etichette con Analisi delle etichette](label-analytics.md)|


## <a name="end-user-documentation-for-sensitivity-labels"></a>Documentazione per gli utenti finali sulle etichette di riservatezza

- [Applicare etichette di riservatezza ai file e ai messaggi di posta elettronica in Office](https://support.office.com/article/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)

- [Problemi noti relativi alle etichette di riservatezza in Office](https://support.office.com/en-us/article/known-issues-with-sensitivity-labels-in-office-b169d687-2bbd-4e21-a440-7da1b2743edc)

- [Applicare automaticamente o consigliare l'applicazione di etichette di riservatezza ai file e ai messaggi di posta elettronica in Office](https://support.office.com/article/automatically-apply-or-recommend-sensitivity-labels-to-your-files-and-emails-in-office-622e0d9c-f38c-470a-bcdb-9e90b24d71a1)

- [Problemi noti con l'applicazione automatica o la raccomandazione delle etichette di riservatezza](https://support.office.com/article/known-issues-with-automatically-applying-or-recommending-sensitivity-labels-451698ae-311b-4d28-83aa-a839a66f6efc)


