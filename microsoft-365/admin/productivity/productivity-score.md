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
ms.openlocfilehash: f1edc1a66763562b233455609f3381e3f4fbfa98
ms.sourcegitcommit: 4debeb8f0fce67f361676340fc390f1b283a3069
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/03/2020
ms.locfileid: "49561475"
---
# <a name="microsoft-productivity-score"></a>Punteggio di produttività Microsoft 

La produttività Score supporta il viaggio verso la trasformazione digitale con approfondimenti su come l'organizzazione usa Microsoft 365 e le esperienze tecnologiche che la supportano. Il Punteggio dell'organizzazione riflette le misure di utenti e tecnologie e può essere paragonato ai benchmark di organizzazioni simili per dimensioni al proprio.

Offre:

- **Metriche** che consentono di visualizzare la posizione in cui si trova il percorso di trasformazione digitale.
- **Informazioni dettagliate sui** dati che consentono di identificare le opportunità di migliorare la produttività e la soddisfazione nell'organizzazione.
- **Azioni consigliate** che è possibile eseguire per aiutare l'organizzazione a utilizzare i prodotti Microsoft 365 in modo efficiente.

Vengono fornite metriche, informazioni dettagliate e suggerimenti in due aree: 

- **Esperienze degli utenti:** Quantifica il modo in cui l'organizzazione funziona con le categorie Microsoft 365 come la collaborazione, la mobilità, la comunicazione, le riunioni e il lavoro di squadra del contenuto.  

    Per ognuna delle categorie citate, vengono esaminate le ricerche pubbliche per identificare alcune procedure consigliate e i vantaggi associati in forma di efficacia organizzativa. Ad esempio, [Forrester] ( https://vc2prod.blob.core.windows.net/vc-resources/TEIStudies/TEI%20of%20Microsoft%20365%20E5%20-%20Oct%202018.pdf la ricerca ha mostrato che quando la gente collabora e condivide il contenuto nel cloud (invece di inviare messaggi di posta elettronica), può salvare fino a 100 minuti alla settimana. È inoltre possibile quantificare l'utilizzo di queste procedure consigliate nell'organizzazione per individuare la posizione del percorso di trasformazione digitale. 

- **Esperienze tecnologiche:** L'organizzazione dipende da una tecnologia affidabile e ben performante, nonché dall'utilizzo efficiente di Microsoft 365. L' [analisi di endpoint](https://aka.ms/endpointanalytics) consente di comprendere in che modo l'organizzazione può avere un impatto sui problemi di prestazioni e integrità dell'hardware e del software. Microsoft 365 Apps Health aiuta a capire se i dispositivi dell'organizzazione eseguono le app Microsoft 365 nei canali consigliati.

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
 
 In ogni categoria di punteggio vengono quantificati gli indicatori chiave per il modo in cui l'organizzazione utilizza Microsoft 365 nel suo percorso verso la trasformazione digitale. Vengono fornite le visualizzazioni di 28 giorni e 180 giorni delle attività principali. Sono inoltre disponibili metriche di supporto che non fanno parte del calcolo del punteggio, ma sono importanti per identificare le statistiche e le configurazioni di utilizzo sottostanti che è possibile risolvere.

### <a name="products-included-in-productivity-score"></a>Prodotti inclusi nel punteggio di produttività 

Il Punteggio di produttività include i dati di Exchange, SharePoint, OneDrive, teams, Word, Excel, PowerPoint, OneNote, Outlook, Yammer e Skype.

Il Punteggio dell'organizzazione viene aggiornato giornalmente e riflette le azioni degli utenti completate negli ultimi 28 (compreso il giorno corrente).


## <a name="pre-requisites"></a>Prerequisiti 

Per le persone che hanno esperienza di dati, è necessario un abbonamento a Microsoft 365 for business o Office 365 for Enterprise. Per i dati di analisi endpoint per il tenant, è necessario aggiungere Microsoft Intune all'abbonamento. Intune consente di proteggere i dati dell'organizzazione tramite la gestione di dispositivi e app. Dopo aver installato Intune, è possibile abilitare l'analisi di endpoint all'interno dell'esperienza di Intune. Per ulteriori informazioni, vedere [Microsoft Intune](https://docs.microsoft.com/mem/intune/). 
> [!NOTE]
> Non è necessaria una licenza per l'analisi del posto di lavoro per ottenere le funzionalità di valutazione della produttività.

Il Punteggio di produttività è disponibile solo nell'interfaccia di amministrazione di Microsoft 365 ed è accessibile solo ai professionisti IT che hanno uno dei ruoli seguenti:  

- Amministratore globale 
- Amministratori di Exchange
- Amministratore di SharePoint 
- Amministratore di Skype for Business 
- Amministratore di Teams 
- Ruolo con autorizzazioni di lettura globali 
- Lettore report 

Tenere presente che le informazioni devono essere utilizzate solo per favorire la trasformazione digitale tramite Microsoft 365 e pertanto è opportuno condividerle con discrezione. 

Microsoft si impegna a proteggere la privacy individuale. In questo [documento sulla privacy](privacy.md)  vengono illustrati i controlli che vengono forniti dall'amministratore IT dell'organizzazione per garantire che le informazioni siano eseguibili senza compromettere la relazione di trust eseguita in Microsoft.

È possibile accedere all'esperienza da Microsoft 365 admin Home in **report**  >  **Productivity Score**.

## <a name="interpreting-your-organizations-productivity-score"></a>Interpretazione del Punteggio di produttività dell'organizzazione 

La Home page del Punteggio di produttività Visualizza la cronologia totale dei punteggi e del punteggio dell'organizzazione e l'intuizione principale di ogni categoria.

:::image type="content" source="../../media/prodscore-landing.png" alt-text="Pagina Punteggio di produttività nei report.":::

**Il punteggio dell'organizzazione** viene visualizzato come valore percentuale e in punti. È possibile visualizzare i punti nel numeratore e i punti massimi possibili nel denominatore.

I **benchmark peer** consentono di confrontare il punteggio dell'organizzazione con organizzazioni come la propria. Il benchmark peer per le categorie people experiences viene calcolato come media delle misure all'interno di un insieme di organizzazioni simili. Il set di organizzazioni è costituito da organizzazioni nella propria area geografica con un numero analogo di utenti con licenza, tipi di licenze, industria e possesso di Microsoft 365. 

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

Questo rapporto aiuta le organizzazioni a comprendere quanto segue: 

- Il modo in cui la collaborazione e la comunicazione sono intaccate dal passaggio al lavoro remoto. 

- L'impatto sul saldo della vita lavorativa come la gente adatta a lavorare da casa. 

- Se le riunioni remote supportano un processo decisionale efficace.

[Ulteriori informazioni sul rapporto di continuità aziendale](https://aka.ms/bcrps)

[Altre informazioni su Microsoft Graph](https://docs.microsoft.com/graph/)

## <a name="we-want-to-hear-from-you"></a>Si vuole sapere da voi

Condividi i tuoi pensieri sul punteggio di produttività e sulle tue idee su come migliorarlo. Utilizzare le sezioni di **feedback** all'interno del prodotto e/o raggiungere il team del Punteggio di produttività in prodscorefeedback@microsoft.com.
