---
title: Punteggio di produttività Microsoft
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
monikerRange: o365-worldwide
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
description: Panoramica del Punteggio di produttività Microsoft.
ms.openlocfilehash: 3808583429c78460483cd7193d38810a7e189040
ms.sourcegitcommit: d578b28ed1886abd083b01b93f01b354067e6d47
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2020
ms.locfileid: "48804727"
---
# <a name="microsoft-productivity-score"></a>Punteggio di produttività Microsoft 

Il Punteggio di produttività consente alle organizzazioni di trasformare il lavoro svolto con informazioni su come gli utenti utilizzano Microsoft 365 e le esperienze tecnologiche che le supportano. Lo Score riflette le prestazioni dell'organizzazione rispetto alle persone e alle esperienze tecnologiche e confronta il tuo punteggio con organizzazioni come le tue.

La partitura include:

- **Metriche** che consentono di vedere in che modo le persone usano prodotti Microsoft 365 per collaborare, comunicare e lavorare su più piattaforme.
- Informazioni dettagliate sui dati utili per identificare le opportunità di migliorare la produttività e la **soddisfazione dei dipendenti** .
- Le **azioni consigliate** che è possibile eseguire per aiutare gli utenti dell'organizzazione a utilizzare i prodotti Microsoft 365 sono efficienti in modo che tutti possano svolgere il proprio lavoro.

Vengono forniti dati, informazioni dettagliate e suggerimenti in due aree: 

- **Esperienze degli utenti:** Misura il modo in cui le persone collaborano al contenuto, il modo in cui utilizzano i prodotti Microsoft 365 per comunicare e se utilizzano Microsoft 365 su più piattaforme. 

    Queste informazioni vengono fornite perché quando le persone collaborano online, risparmiano tempo e con la libertà di lavorare su qualsiasi dispositivo rende più produttivo e soddisfatto. La capacità di comunicare in modo flessibile rende le persone più efficienti, in grado di formare relazioni migliori e quindi rendere l'organizzazione più unita. Per ulteriori informazioni, vedere [rapporto Forrester](https://vc2prod.blob.core.windows.net/vc-resources/TEIStudies/TEI%20of%20Microsoft%20365%20E5%20-%20Oct%202018.pdf).

- **Esperienze tecnologiche:** La produttività del team dipende da una tecnologia affidabile e ben performante, oltre che da un utilizzo efficiente di Microsoft 365. L' [analisi di endpoint](https://aka.ms/endpointanalytics) consente di comprendere in che modo la produttività degli utenti può essere influenzata da problemi di prestazioni e integrità con l'hardware e il software. Le azioni consigliate consentono di risolvere questi problemi. Microsoft 365 informazioni sulla connettività di rete consentono di risolvere i problemi di connectivty per l'organizzazione.

Vedere [che cos'è l'analisi di endpoint](https://docs.microsoft.com/mem/analytics/overview) per una panoramica e Dettagli prerequisito. Per ulteriori informazioni sulle considerazioni relative alla connettività di rete di Microsoft 365, leggere [la panoramica della connettività di rete](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-networking-overview).
  

## <a name="how-the-score-is-calculated"></a>Modalità di calcolo del Punteggio

Il Punteggio di produttività è basato sui punteggi combinati delle categorie di persone e esperienze tecnologiche. Ogni categoria viene ponderata equamente, con un totale di 100 punti. Il Punteggio di produttività massimo possibile è 800.

### <a name="score-categories"></a>Categorie di Punteggio 

- Comunicazione (100 punti)
- Riunioni (100 punti)
- Collaborazione del contenuto (100 punti)
- Teamwork (100 punti)
- Mobilità (100 punti)
- Analisi degli endpoint (100 punti)
- Connettività di rete (100 punti)
- Microsoft 365 Apps Health (100 punti)
- **Totale possibile = 800 punti**
 
 In ogni categoria di punteggio vengono identificati i modelli per le attività chiave che sono indicatori per la modalità con cui gli utenti utilizzano i prodotti Microsoft 365 per collaborare, comunicare e lavorare su più piattaforme. Vengono fornite le visualizzazioni di 28 giorni e 180 giorni delle attività principali. Sono inoltre disponibili metriche di supporto che non fanno parte del calcolo del punteggio, ma sono importanti per identificare i comportamenti e le impostazioni sottostanti che è possibile risolvere.

### <a name="products-included-in-productivity-score"></a>Prodotti inclusi nel punteggio di produttività 

Il Punteggio di produttività include i dati di Exchange, SharePoint, OneDrive, teams, Word, Excel, PowerPoint, OneNote, Outlook, Yammer e Skype.

Il Punteggio viene aggiornato giornalmente e riflette le azioni dell'utente completate negli ultimi 28 (compreso il giorno corrente).


## <a name="pre-requisites"></a>Prerequisiti 

Per le persone che hanno esperienza di dati, è necessario un abbonamento a Microsoft 365 for business o Office 365 for Enterprise. Per i dati di analisi endpoint per il tenant, è necessario aggiungere Microsoft Intune all'abbonamento. Intune consente di proteggere i dati dell'organizzazione tramite la gestione di dispositivi e app. Dopo aver installato Intune, è possibile abilitare l'analisi di endpoint all'interno dell'esperienza di Intune. Per ulteriori informazioni, vedere Microsoft Intune. 
> [!NOTE]
> Non è necessaria una licenza per l'analisi del posto di lavoro per ottenere le funzionalità di valutazione della produttività.

Per visualizzare il Punteggio di produttività per l'organizzazione, è necessario disporre di uno dei ruoli seguenti: 

- Amministratore globale 
- Amministratori di Exchange
- Amministratore di SharePoint 
- Amministratore di Skype for Business 
- Amministratore di Teams 
- Ruolo con autorizzazioni di lettura globali 
- Lettore report 

È possibile accedere all'esperienza da Microsoft 365 admin Home in **report**  >  **Productivity Score** .

## <a name="interpreting-productivity-score"></a>Interpretazione del Punteggio di produttività 

La Home page del Punteggio di produttività Visualizza il punteggio totale e la cronologia dei punteggi e l'intuizione principale di ogni categoria.

:::image type="content" source="../../media/prodscore-landing.png" alt-text="Pagina Punteggio di produttività nei report.":::

**Il Punteggio** viene visualizzato come valore percentuale e in punti. È possibile visualizzare i punti nel numeratore e i punti massimi possibili nel denominatore.

I **benchmark peer** consentono di confrontare il punteggio con organizzazioni come la propria. Il benchmark peer per le categorie people experiences viene calcolato come media delle misure all'interno di un insieme di organizzazioni simili. Il set di organizzazioni è costituito da organizzazioni nella propria area geografica con un numero analogo di utenti con licenza, tipi di licenze, industria e possesso di Microsoft 365. 

Il benchmark peer analisi endpoint include gli obiettivi per le prestazioni di avvio del dispositivo e la configurazione software consigliata in base ai valori mediani aggregati in tutti i tenant.

Per la connettività di rete, il benchmark consigliato è 80 punti.

La sezione **Score Breakdown** fornisce una ripartizione del Punteggio di produttività con benchmark da parte di utenti e aree di utilizzo della tecnologia.

La cronologia dei punteggi Visualizza la modalità di modifica del Punteggio di ogni categoria negli ultimi 6 mesi.

Le aree esperienze e esperienze **tecnologiche** delle **persone** contengono le informazioni principali per le categorie in queste aree. È possibile fare clic su ogni categoria per visualizzare le informazioni più approfondite.

## <a name="category-details-pages"></a>Pagine dei dettagli categoria

In ogni pagina dei dettagli della categoria vengono illustrate le metriche principale e di supporto, nonché le attività relative alla ricerca e alle azioni che è possibile eseguire per gestire le modifiche nell'organizzazione. La ricerca supporta l'importanza e la logica dietro le intuizioni principali di ogni categoria. Per ulteriori informazioni, [leggere il rapporto Forrester](https://vc2prod.blob.core.windows.net/vc-resources/TEIStudies/TEI%20of%20Microsoft%20365%20E5%20-%20Oct%202018.pdf).

Le pagine dei dettagli sono le seguenti:
- [Collaborazione tra i contenuti – esperienze degli utenti](content-collaboration.md)
- [Comunicazione – esperienze degli utenti](communication.md)
- [Riunioni – esperienze degli utenti](meetings.md)
- [Mobilità – esperienze degli utenti](mobility.md)
- [Teamwork – esperienze degli utenti](teamwork.md)
- [Microsoft 365 Apps Health – esperienze tecnologiche](apps-health.md)

## <a name="business-continuity-special-report"></a>Rapporto speciale di continuità aziendale

Il rapporto di continuità aziendale è un report di intelligence sul luogo di lavoro a tempo limitato disponibile per tutti i clienti di Microsoft 365 per aiutarli a guidare le loro organizzazioni durante questo momento impegnativo.  

Questo rapporto aiuta i leader aziendali a comprendere quanto segue: 

- Il modo in cui la collaborazione e la comunicazione sono intaccate dal passaggio al lavoro remoto. 

- L'impatto sul saldo della vita lavorativa come la gente adatta a lavorare da casa. 

- Se le riunioni remote supportano un processo decisionale efficace.

[Ulteriori informazioni sul rapporto di continuità aziendale](https://aka.ms/bcrps)

[Altre informazioni su Microsoft Graph](https://docs.microsoft.com/graph/)

## <a name="we-want-to-hear-from-you"></a>Si vuole sapere da voi

Condividi i tuoi pensieri sul punteggio di produttività e sulle tue idee su come migliorarlo. Utilizzare le sezioni di **feedback** all'interno del prodotto e/o raggiungere il team del Punteggio di produttività in ProductivityScorePreview@service.microsoft.com.
