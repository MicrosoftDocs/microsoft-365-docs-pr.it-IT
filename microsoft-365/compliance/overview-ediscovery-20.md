---
title: Panoramica della soluzione Advanced eDiscovery in Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- m365-security-compliance
- m365solution-aed
- m365initiative-compliance
- m365solution-overview
search.appverid:
- MOE150
- MET150
description: Informazioni sulla soluzione Advanced eDiscovery in Microsoft 365. In questo articolo viene fornita una panoramica delle Advanced eDiscovery in Microsoft 365, uno strumento che consente di gestire le indagini interne ed esterne. Vengono inoltre incorniciati i motivi aziendali per l'Advanced eDiscovery per gestire le indagini legali.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4fe94aed10a7b9e981e2a9d46e992d5557e35dcb
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256460"
---
# <a name="overview-of-microsoft-365-advanced-ediscovery"></a>Panoramica di Microsoft 365 Advanced eDiscovery

La Advanced eDiscovery in Microsoft 365 si basa sulle funzionalità di analisi e eDiscovery di Microsoft esistenti. Advanced eDiscovery fornisce un flusso di lavoro end-to-end per conservare, raccogliere, analizzare, esaminare ed esportare contenuto reattivo alle indagini interne ed esterne dell'organizzazione. Consente anche ai team legali di gestire l'intero flusso di lavoro per le notifiche di blocco a fini giudiziari per comunicare con i responsabili coinvolti in un caso.

## <a name="advanced-ediscovery-capabilities"></a>Advanced eDiscovery funzionalità

Advanced eDiscovery può aiutare l'organizzazione a rispondere a questioni legali o indagini interne individuando i dati in cui si trova. È possibile gestire senza problemi i flussi di lavoro di eDiscovery identificando le persone di interesse e le relative origini dati, applicare senza problemi i blocchi per conservare i dati e quindi gestire il processo di comunicazione del blocco legale. Raccogliendo i dati dall'origine, puoi cercare nella piattaforma Microsoft 365 live per trovare rapidamente ciò che ti serve. Le funzionalità di apprendimento automatico intelligenti, ad esempio l'indicizzazione approfondita, il threading della posta elettronica e il rilevamento quasi duplicato, consentono inoltre di ridurre grandi volumi di dati a un set di dati pertinente.

Le sezioni seguenti descrivono in che modo queste Advanced eDiscovery possono aiutare l'organizzazione.

![Advanced eDiscovery funzionalità](../media/advanced-ediscovery-capabilities.png)

### <a name="discover-and-collect-data-in-place"></a>Individuare e raccogliere dati sul posto

In genere, le organizzazioni che si basano su più soluzioni eDiscovery di terze parti richiedono la copia di grandi volumi di dati Microsoft 365 per elaborare e dover ospitare dati duplicati. Questa necessità aumenta il tempo necessario per trovare dati pertinenti e il rischio, i costi e la complessità della gestione di più soluzioni.

Advanced eDiscovery in Microsoft 365 consente di individuare i dati all'origine e di rimanere all'interno del Microsoft 365 di sicurezza e conformità.  Raccogliendo i dati sul posto dal sistema reale, Advanced eDiscovery riduce l'attrito di tornare all'origine e riduce il lavoro non necessario di dover trovare contenuto mancante, cosa che spesso accade quando l'inserimento nel journal è in ritardo nelle soluzioni eDiscovery tradizionali.

Le funzionalità di ricerca e raccolta native per i dati in Teams, Yammer, SharePoint Online, OneDrive for Business e Exchange Online migliorano ulteriormente l'individuazione dei dati. Ad esempio, Advanced eDiscovery:

- Ricostruisce Teams conversazioni (anziché restituire singoli messaggi dalle conversazioni).

- Raccoglie contenuto basato sul cloud condiviso con gli utenti tramite collegamenti o allegati moderni nei messaggi di posta elettronica e nelle Teams chat.

- Supporta centinaia di tipi di file non Microsoft 365 incorporati.

- Raccoglie dati da origini di terze parti (ad esempio Bloomberg, Facebook, Slack e Riunioni zoom) che vengono importati e archiviati in Microsoft 365 dai connettori [di dati.](archiving-third-party-data.md)

### <a name="manage-ediscovery-workflow-in-one-platform"></a>Gestire il flusso di lavoro di eDiscovery in una piattaforma

Advanced eDiscovery consente di ridurre il numero di soluzioni eDiscovery su cui è necessario fare affidamento. Offre un flusso di lavoro end-to-end semplificato, tutto ciò che si verifica all'interno di Microsoft 365. Advanced eDiscovery consente di ridurre l'attrito nell'identificare e raccogliere potenziali fonti di informazioni rilevanti mappando automaticamente origini dati univoche e condivise alla persona di interesse (nota come depositario) e fornendo report e analisi su dati potenzialmente rilevanti prima di raccoglierlo per l'analisi e la revisione.

Inoltre, le API di Microsoft Graph consentono di automatizzare il flusso di lavoro di eDiscovery ed estendere Advanced eDiscovery per soluzioni personalizzate.

### <a name="cull-data-intelligently"></a>Dati Cull in modo intelligente

Le funzionalità di apprendimento automatico intelligenti in Advanced eDiscovery consentono di ridurre la quantità di dati da esaminare. Queste funzionalità intelligenti consentono di ridurre e ridurre grandi volumi di dati a un set pertinente. Ad esempio, una query predefinita del set di revisione consente di filtrare solo il contenuto univoco identificando quasi duplicati. Questa funzionalità può ridurre notevolmente la quantità di dati da esaminare.

Ulteriori funzionalità di machine learning possono perfezionare e identificare ulteriormente i dati rilevanti utilizzando smart tag e strumenti di revisione assistiti dalla tecnologia come i moduli di pertinenza.

## <a name="advanced-ediscovery-alignment-with-the-electronic-discovery-reference-model"></a>Advanced eDiscovery allineamento con il modello di riferimento per l'individuazione elettronica

Il flusso di lavoro predefinito di Advanced eDiscovery in Microsoft 365 è allineato al processo di eDiscovery descritto dal modello EDRM (Electronic Discovery Reference Model).

![EdRM (Electronic Discovery Reference Model)](../media/EDRMv1.png)

(Origine immagine per gentile edrm.net. L'immagine di origine è stata resa disponibile in Creative Commons Attribution 3.0 Unported License.

A livello generale, ecco il modo in cui Advanced eDiscovery supporta il flusso di lavoro EDRM:

- **Identificazione.** Dopo aver identificato le persone potenzialmente coinvolte in un'indagine, è possibile aggiungerle in un caso di Advanced eDiscovery come responsabili (chiamati anche *responsabili dei dati*, perché potrebbero avere informazioni rilevanti per l'indagine). A quel punto, è possibile conservare, raccogliere e rivedere i documenti dei responsabili in tutta facilità.

- **Conservazione.** Per conservare e proteggere i dati rilevanti per un'indagine, Advanced eDiscovery consente di impostare un blocco a fini giudiziari sulle origini dati associate ai responsabili in un caso. È anche possibile impostare un blocco per i dati non correlati ai responsabili. Advanced eDiscovery include anche un flusso di lavoro predefinito per le comunicazioni, che consente di inviare ai responsabili notifiche di blocco a fini giudiziari e tenere traccia delle loro conferme.

- **Insieme.** Dopo aver identificato e conservato le origini dati rilevanti per l'indagine, è possibile usare lo strumento di ricerca incorporato in Advanced eDiscovery per cercare e raccogliere dati in tempo reale dalle origini dati dei responsabili (e, se applicabile, da origini dati non correlate ai responsabili) che potrebbero essere rilevanti per il caso.

- **Elaborazione.** Dopo aver raccolto tutti i dati rilevanti per il caso, il passaggio successivo consiste nella loro elaborazione per una revisione e un'analisi ulteriori. In Advanced eDiscovery i dati sul posto identificati nella fase di raccolta vengono copiati in una posizione di Archiviazione di Azure (denominata *insieme da rivedere*), che fornisce una visualizzazione statica dei dati del caso. 

- **Revisione.** Dopo aver aggiunto i dati a un set di revisioni, è possibile visualizzare documenti specifici ed eseguire query aggiuntive per ridurre i dati a ciò che è più rilevante per il caso. È possibile inoltre aggiungere annotazioni e tag a documenti specifici.

- **Analisi.** Advanced eDiscovery offre uno strumento di analisi integrato che consente di scegliere ulteriormente i dati dall'insieme da rivedere che si determina non pertinente per l'indagine. Oltre a ridurre il volume dei dati pertinenti, Advance eDiscovery permette anche di risparmiare sui costi di revisione legale, consentendo di organizzare i contenuti in modo da semplificare e rendere più efficiente il processo di revisione.

- **Produzione** e **presentazione.** Quando si è pronti, è possibile esportare i documenti da un insieme da rivedere per la revisione legale. È possibile esportare i documenti nel loro formato nativo o in un formato specificato da EDRM in modo da poter essere importati in applicazioni di revisione di terze parti.

## <a name="subscriptions-and-licensing"></a>Abbonamenti e licenze

Le licenze per Advanced eDiscovery richiedono l'abbonamento all'organizzazione appropriato e le licenze per utente.

- **Sottoscrizione organizzazione:** Per accedere Advanced eDiscovery'Centro conformità Microsoft 365, l'organizzazione deve disporre di una delle opzioni seguenti:

  - Abbonamento a Microsoft 365 E5 o a Office 365 E5
  
  - Abbonamento a Microsoft 365 E3 con il componente aggiuntivo E5 Compliance

  - Microsoft 365 E3 sottoscrizione con il componente aggiuntivo E5 eDiscovery e Controllo

  - Microsoft 365 Education Sottoscrizione A5 o Office 365 Education A5

   Se non si dispone di un piano di Microsoft 365 E5 esistente e si desidera provare Advanced eDiscovery, è possibile aggiungere [Microsoft 365](/office365/admin/try-or-buy-microsoft-365) all'abbonamento esistente o iscriversi [per](https://www.microsoft.com/microsoft-365/enterprise) una versione di valutazione di Microsoft 365 E5.

- **Licenze per utente:** Per aggiungere un utente come responsabile in un caso di Advance eDiscovery, a tale utente deve essere assegnata una delle licenze seguenti, a seconda dell'abbonamento all'organizzazione:

  - Microsoft 365: agli utenti deve essere assegnata una licenza di Microsoft 365 E5, una licenza del componente aggiuntivo Conformità E5 o una licenza del componente aggiuntivo E5 eDiscovery e controllo. Microsoft 365 Education agli utenti deve essere assegnata una licenza A5.

  - Office 365: agli utenti deve essere assegnata una licenza Office 365 E5 o Office 365 Education A5.

   Per informazioni su come assegnare licenze, vedere [Assegnare licenze agli utenti.](/microsoft-365/admin/manage/assign-licenses-to-users)

> [!NOTE]
> Gli utenti necessitano solo di una licenza E5 o A5 (o della licenza del componente aggiuntivo appropriata) da aggiungere come depositario a un Advanced eDiscovery caso. Gli amministratori IT, i responsabili di eDiscovery, gli avvocati, i paralegali o gli investigatori che utilizzano Advanced eDiscovery per gestire i casi e esaminare i dati dei casi non necessitano di una licenza E5, A5 o add-on.

## <a name="get-started-with-advanced-ediscovery"></a>Introduzione ad Advanced eDiscovery

Esistono due semplici e rapidi passaggi per iniziare a usare Advanced eDiscovery.

![Introduzione al flusso di lavoro Advanced eDiscovery](../media/get-started-AeD.png)

|Passaggi  |Descrizione  |
|:---------|:---------|
|[Configurare Advanced eDiscovery](get-started-with-advanced-ediscovery.md)| Dopo aver verificato i requisiti di sottoscrizione e licenze, è possibile assegnare le autorizzazioni e configurare le impostazioni a livello di organizzazione per iniziare a usare Advanced eDiscovery.|
|[Creare e gestire i casi](create-and-manage-advanced-ediscoveryv2-case.md) | Creare casi per gestire il flusso Advanced eDiscovery per tutti i tipi di indagini legali e di altro tipo nell'organizzazione.|
|||

## <a name="advanced-ediscovery-architecture"></a>Advanced eDiscovery architettura

Ecco un diagramma dell'architettura di Advanced eDiscovery che mostra il flusso di lavoro end-to-end in un ambiente geografico singolo e in un ambiente multi-geografico e il flusso di dati end-to-end allineato a [EDRM.](#advanced-ediscovery-alignment-with-the-electronic-discovery-reference-model)

[![Poster modello: Advanced eDiscovery architettura in Microsoft 365](../media/solutions-architecture-center/ediscovery-poster-thumb.png)](../media/solutions-architecture-center/m365-advanced-ediscovery-architecture.png)

[Visualizzazione come immagine](../media/solutions-architecture-center/m365-advanced-ediscovery-architecture.png)

[Scarica come file PDF](https://download.microsoft.com/download/d/1/c/d1ce536d-9bcf-4d31-b75b-fcf0dc560665/m365-advanced-ediscovery-architecture.pdf)

[Scarica come file Visio](https://download.microsoft.com/download/d/1/c/d1ce536d-9bcf-4d31-b75b-fcf0dc560665/m365-advanced-ediscovery-architecture.vsdx)

## <a name="training"></a>Formazione

La formazione degli amministratori IT, dei responsabili di eDiscovery e dei team di analisi della conformità nelle nozioni di base per Advanced eDiscovery può aiutare l'organizzazione a iniziare più rapidamente a usare Microsoft 365 eDiscovery. Microsoft 365 fornisce la risorsa seguente per aiutare questi utenti nell'organizzazione a iniziare a usare eDiscovery: Descrivere le funzionalità [di eDiscovery](/learn/modules/describe-ediscovery-capabilities-of-microsoft-365)e controllo di Microsoft 365 .
