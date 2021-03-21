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
description: Informazioni sulla soluzione Advanced eDiscovery in Microsoft 365. In questo articolo viene fornita una panoramica di Advanced eDiscovery in Microsoft 365, uno strumento che consente di gestire le indagini interne ed esterne. Vengono inoltre incorniciati i motivi aziendali per l'utilizzo di Advanced eDiscovery per gestire le indagini legali.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0f6ae536f84190f81248bbf68ff66f438727e068
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927654"
---
# <a name="overview-of-microsoft-365-advanced-ediscovery"></a>Panoramica di Microsoft 365 Advanced eDiscovery

La soluzione Advanced eDiscovery in Microsoft 365 si basa sulle funzionalità di analisi e eDiscovery di Microsoft esistenti. Advanced eDiscovery offre un flusso di lavoro end-to-end per conservare, raccogliere, analizzare, esaminare, analizzare ed esportare contenuto che risponde alle indagini interne ed esterne dell'organizzazione. Consente inoltre ai team legali di gestire l'intero flusso di lavoro di notifica di blocco legale per comunicare con i custodi coinvolti in un caso.

## <a name="advanced-ediscovery-capabilities"></a>Funzionalità avanzate di eDiscovery

Advanced eDiscovery consente all'organizzazione di rispondere a questioni legali o indagini interne individuando i dati in cui si trova. È possibile gestire senza problemi i flussi di lavoro di eDiscovery identificando le persone di interesse e le relative origini dati, applicare senza problemi i blocchi per conservare i dati e quindi gestire il processo di comunicazione del blocco legale. Raccogliendo i dati dall'origine, è possibile cercare nella piattaforma Microsoft 365 live per trovare rapidamente ciò di cui si ha bisogno. Le funzionalità di apprendimento automatico intelligenti, ad esempio l'indicizzazione approfondita, il threading della posta elettronica e il rilevamento quasi duplicato, consentono inoltre di ridurre grandi volumi di dati a un set di dati pertinente.

Nelle sezioni seguenti viene descritto in che modo queste funzionalità di eDiscovery avanzate possono aiutare l'organizzazione.

![Funzionalità avanzate di eDiscovery](../media/advanced-ediscovery-capabilities.png)

### <a name="discover-and-collect-data-in-place"></a>Individuare e raccogliere dati sul posto

In genere, le organizzazioni che si basano su più soluzioni eDiscovery di terze parti richiedono la copia di grandi volumi di dati da Microsoft 365 per elaborare e dover ospitare dati duplicati. Questa necessità aumenta il tempo necessario per trovare dati pertinenti e il rischio, i costi e la complessità della gestione di più soluzioni.

Advanced eDiscovery in Microsoft 365 consente di individuare i dati all'origine e di rimanere entro i limiti di sicurezza e conformità di Microsoft 365.  Raccogliendo i dati sul posto dal sistema live, Advanced eDiscovery riduce l'attrito di tornare all'origine e riduce il lavoro non necessario di dover trovare contenuto mancante, cosa che spesso accade quando l'inserimento nel journal è in ritardo nelle soluzioni eDiscovery tradizionali.

Le funzionalità di ricerca e raccolta native per i dati in Teams, Yammer, SharePoint Online, OneDrive for Business ed Exchange Online migliorano ulteriormente l'individuazione dei dati. Ad esempio, Advanced eDiscovery:

- Ricostruisce le conversazioni di Teams anziché restituire singoli messaggi dalle conversazioni.

- Raccoglie contenuto basato sul cloud condiviso con gli utenti tramite collegamenti o allegati moderni nei messaggi di posta elettronica e nelle chat di Teams.

- Supporto incorporato per centinaia di tipi di file non Microsoft 365.

- Raccoglie dati da origini di terze parti (ad esempio Bloomberg, Facebook, Slack e Riunioni zoom) importati e archiviati in Microsoft 365 dai connettori [dati.](archiving-third-party-data.md)

### <a name="manage-ediscovery-workflow-in-one-platform"></a>Gestire il flusso di lavoro di eDiscovery in una piattaforma

Advanced eDiscovery consente di ridurre il numero di soluzioni eDiscovery su cui è necessario fare affidamento. Offre un flusso di lavoro end-to-end semplificato, tutto ciò che avviene all'interno di Microsoft 365. Advanced eDiscovery consente di ridurre l'attrito nell'identificare e raccogliere potenziali fonti di informazioni rilevanti mappando automaticamente origini dati univoche e condivise alla persona di interesse (nota come depositario) e fornendo report e analisi su dati potenzialmente rilevanti prima di raccoglierlo per l'analisi e la revisione.

Inoltre, le API di Microsoft Graph consentono di automatizzare il flusso di lavoro di eDiscovery ed estendere Advanced eDiscovery per soluzioni personalizzate.

### <a name="cull-data-intelligently"></a>Dati Cull in modo intelligente

Le funzionalità di apprendimento automatico intelligenti in Advanced eDiscovery consentono di ridurre la quantità di dati da esaminare. Queste funzionalità intelligenti consentono di ridurre e ridurre grandi volumi di dati a un set pertinente. Ad esempio, una query predefinita del set di revisione consente di filtrare solo il contenuto univoco identificando quasi duplicati. Questa funzionalità può ridurre notevolmente la quantità di dati da esaminare.

Ulteriori funzionalità di machine learning possono perfezionare e identificare ulteriormente i dati rilevanti utilizzando smart tag e strumenti di revisione assistiti dalla tecnologia come i moduli di pertinenza.

## <a name="advanced-ediscovery-alignment-with-the-electronic-discovery-reference-model"></a>Allineamento avanzato di eDiscovery con il modello di riferimento per l'individuazione elettronica

Il flusso di lavoro predefinito di Advanced eDiscovery in Microsoft 365 si allinea al processo di eDiscovery descritto dal modello di riferimento per l'individuazione elettronica (EDRM).

![EdRM (Electronic Discovery Reference Model)](../media/EDRMv1.png)

(Origine immagine per gentile edrm.net. L'immagine di origine è stata resa disponibile in Creative Commons Attribution 3.0 Unported License.

A livello di alto livello, ecco come Advanced eDiscovery supporta il flusso di lavoro EDRM:

- **Identificazione.** Dopo aver identificato le potenziali persone di interesse per un'indagine, è possibile aggiungerle come responsabili (detti anche responsabili dei dati *,* perché potrebbero disporre di informazioni rilevanti per l'indagine) a un caso advanced eDiscovery. Dopo l'aggiunta degli utenti come custodi, è facile conservare, raccogliere ed esaminare i documenti depositario.

- **Conservazione.** Per conservare e proteggere i dati rilevanti per un'indagine, Advanced eDiscovery consente di conservare legalmente le origini dati associate ai custodi in un caso. È inoltre possibile mettere in attesa i dati non depositario. Advanced eDiscovery include anche un flusso di lavoro integrato per le comunicazioni, in modo da poter inviare notifiche di blocco legale ai custodi e tenere traccia dei loro riconoscimenti.

- **Insieme.** Dopo aver identificato (e conservato) le origini dati rilevanti per l'indagine, è possibile utilizzare lo strumento di ricerca incorporato in Advanced eDiscovery per cercare e raccogliere dati in tempo reale dalle origini dati di custodia (e da origini dati non depositate, se applicabile) che potrebbero essere rilevanti per il caso.

- **Elaborazione.** Dopo aver raccolto tutti i dati rilevanti per il caso, il passaggio successivo consiste nell'elaborarlo per un'ulteriore revisione e analisi. In Advanced eDiscovery, i dati sul posto identificati nella fase di raccolta vengono copiati in un percorso di archiviazione di Azure (denominato *set* di revisione), che fornisce una visualizzazione statica dei dati del caso. 

- **Revisione.** Dopo aver aggiunto i dati a un set di revisioni, è possibile visualizzare documenti specifici ed eseguire query aggiuntive per ridurre i dati a ciò che è più rilevante per il caso. Inoltre, è possibile aggiungere annotazioni e contrassegnare documenti specifici.

- **Analisi.** Advanced eDiscovery offre uno strumento di analisi integrato che consente di aggiungere ulteriori dati dal set di revisione che si determina non è rilevante per l'indagine. Oltre a ridurre il volume di dati rilevanti, Advance eDiscovery consente inoltre di risparmiare sui costi di revisione legale consentendo di organizzare il contenuto per semplificare ed efficienza il processo di revisione.

- **Produzione** e **presentazione.** Quando si è pronti, è possibile esportare i documenti da un set di recensioni per la revisione legale. È possibile esportare i documenti nel formato nativo o in un formato specificato da EDRM in modo che possano essere importati in applicazioni di revisione di terze parti.

## <a name="subscriptions-and-licensing"></a>Abbonamenti e licenze

Le licenze per Advanced eDiscovery richiedono l'abbonamento all'organizzazione appropriato e le licenze per utente.

- **Sottoscrizione organizzazione:** Per accedere a Advanced eDiscovery nel Centro conformità Microsoft 365, l'organizzazione deve disporre di uno degli elementi seguenti:

  - Abbonamento a Microsoft 365 E5 o a Office 365 E5
  
  - Abbonamento a Microsoft 365 E3 con il componente aggiuntivo E5 Compliance

  - Abbonamento a Microsoft 365 E3 con il componente aggiuntivo eDiscovery e controllo di E5

  Se non si dispone di un piano Microsoft 365 E5 esistente e si desidera provare Advanced eDiscovery, è possibile aggiungere [Microsoft 365](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365) all'abbonamento esistente o iscriversi [per](https://www.microsoft.com/microsoft-365/enterprise) una versione di valutazione di Microsoft 365 E5.

- **Licenze per utente:** Per aggiungere un utente come responsabile in un caso di Advance eDiscovery, a tale utente deve essere assegnata una delle licenze seguenti, a seconda dell'abbonamento all'organizzazione:

  - Microsoft 365: agli utenti deve essere assegnata una licenza di Microsoft 365 E5, una licenza del componente aggiuntivo Conformità E5 o una licenza del componente aggiuntivo E5 eDiscovery e controllo.

  - Office 365: agli utenti deve essere assegnata una licenza di Office 365 E5.

   Per informazioni su come assegnare licenze, vedere [Assegnare licenze agli utenti.](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)

> [!NOTE]
> Gli utenti necessitano solo di una licenza E5 (o della licenza del componente aggiuntivo appropriata) da aggiungere come custodi a un caso advanced eDiscovery. Gli amministratori IT, i responsabili di eDiscovery, gli avvocati, i paralegali o gli investigatori che utilizzano Advanced eDiscovery per gestire i casi e rivedere i dati dei casi non necessitano di una licenza E5 o di un componente aggiuntivo.

## <a name="get-started-with-advanced-ediscovery"></a>Introduzione ad Advanced eDiscovery

Sono disponibili due passaggi rapidi e semplici per iniziare a usare Advanced eDiscovery.

![Introduzione al flusso di lavoro con Advanced eDiscovery](../media/get-started-AeD.png)

|Passaggi  |Descrizione  |
|:---------|:---------|
|[Configurare Advanced eDiscovery](get-started-with-advanced-ediscovery.md)| Dopo aver verificato i requisiti di sottoscrizione e licenze, è possibile assegnare le autorizzazioni e configurare le impostazioni a livello di organizzazione per iniziare a usare Advanced eDiscovery.|
|[Creare e gestire i casi](create-and-manage-advanced-ediscoveryv2-case.md) | Creare casi per gestire il flusso di lavoro Advanced eDiscovery per tutti i tipi di indagini legali e di altro tipo nell'organizzazione.|
|||

## <a name="advanced-ediscovery-architecture"></a>Architettura avanzata di eDiscovery

Ecco un diagramma dell'architettura di Advanced eDiscovery che mostra il flusso di lavoro end-to-end in un ambiente con una singola area geografica e in un ambiente multi-geografico e il flusso di dati end-to-end allineato a [EDRM.](#advanced-ediscovery-alignment-with-the-electronic-discovery-reference-model)

[![Poster modello: Architettura avanzata di eDiscovery in Microsoft 365](../media/solutions-architecture-center/ediscovery-poster-thumb.png)](../media/solutions-architecture-center/m365-advanced-ediscovery-architecture.png)

[Visualizzazione come immagine](../media/solutions-architecture-center/m365-advanced-ediscovery-architecture.png)

[Scarica come file PDF](https://download.microsoft.com/download/d/1/c/d1ce536d-9bcf-4d31-b75b-fcf0dc560665/m365-advanced-ediscovery-architecture.pdf)

[Download come file di Visio](https://download.microsoft.com/download/d/1/c/d1ce536d-9bcf-4d31-b75b-fcf0dc560665/m365-advanced-ediscovery-architecture.vsdx)
