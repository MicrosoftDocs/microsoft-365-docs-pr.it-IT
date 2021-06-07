---
title: Punteggio della produttività Microsoft
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
monikerRange: o365-worldwide
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
description: Informazioni su come il punteggio della produttività Microsoft riflette le misurazioni delle persone e delle esperienze tecnologiche e confronta le organizzazioni con dimensioni simili.
ms.openlocfilehash: af0e8583bec00b1ddfd62145a4757a4e568108e8
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789040"
---
# <a name="microsoft-productivity-score"></a>Punteggio della produttività Microsoft 

Il punteggio della produttività supporta il percorso verso la trasformazione digitale con approfondimenti sul modo in cui l'organizzazione usa Microsoft 365 e le esperienze tecnologiche di supporto. Il punteggio dell’organizzazione riflette le misurazioni delle persone e dell'esperienza con la tecnologia e può essere confrontato con i benchmark di organizzazioni di dimensioni simili alla propria.

Fornisce:

- **Metriche** per acquisire consapevolezza sulla propria posizione nel percorso verso la trasformazione digitale.
- **Approfondimenti** sui dati che consentono di identificare le opportunità di miglioramento della produttività e della soddisfazione nell'organizzazione.
- **Azioni consigliate** che è possibile adottare per consentire l'utilizzo dei prodotti Microsoft 365 in modo efficiente.

Forniamo metriche, approfondimenti e consigli in due aree: 

- **Esperienze delle persone:** Quantifica come lavora l'organizzazione utilizzando le categorie di Microsoft 365 quali collaborazione ai contenuti, mobilità, riunioni e lavoro in team.  

    Per ognuna delle categorie menzionate, consultiamo le ricerche pubbliche per identificare alcune procedure consigliate e i vantaggi associati sotto forma di efficacia organizzativa. Ad esempio, una ricerca di Forrester ha mostrato che quando le persone collaborano e condividono contenuti nel cloud (invece di inviare contenuti per posta elettronica), possono risparmiare fino a 100 minuti a settimana. Inoltre, quantifichiamo l'utilizzo di queste best practice nell'organizzazione per verificare la propria posizione nel percorso verso la trasformazione digitale. 

- **Esperienze con la tecnologia:** l'organizzazione dipende da una tecnologia affidabile con prestazioni elevate, nonché dall'uso efficiente di Microsoft 365. [L'analisi degli endpoint](https://aka.ms/endpointanalytics) consente di comprendere in che modo l'organizzazione può essere influenzata da problemi di prestazioni e integrità con l'hardware e il software. L'integrità di Microsoft  365 Apps consente di comprendere se i dispositivi nell'organizzazione eseguono Microsoft 365 Apps sui canali consigliati.

## <a name="before-you-begin"></a>Prima di iniziare

Per una panoramica e dettagli sui prerequisiti, vedere [Informazioni sull'analisi degli endpoint](/mem/analytics/overview). Per altre informazioni sugli approfondimenti della connettività di rete di Microsoft 365, vedere [Panoramica sulla connettività di rete](../../enterprise/microsoft-365-networking-overview.md).

I dati sulle esperienze degli utente richiedono un abbonamento a Microsoft 365 for business o Office 365 per aziende. Per i dati di analisi degli endpoint per il tenant è necessario aggiungere Microsoft Intune all'abbonamento. Intune consente di proteggere i dati dell'organizzazione con la gestione di dispositivi e app. Dopo aver aggiunto Intune, è possibile attivare la funzione analisi endpoint nell'esperienza di Intune. Per ulteriori informazioni su Microsoft Intune, vedere la documentazione [Microsoft Intune](/mem/intune/). 

> [!NOTE]
> Non è necessaria una licenza per Workplace Analytics per ottenere le funzionalità del punteggio della produttività.

Il punteggio della produttività è disponibile solo nell'interfaccia di amministrazione di Microsoft 365 e solo i professionisti IT che dispongono dei seguenti ruoli vi possono accedere:  

- Amministratore globale
- Amministratori di Exchange
- Amministratore di SharePoint
- Amministratore di Skype for Business
- Amministratore di Teams
- Lettore globale
- Amministratore che legge i report
- Amministratore che legge i report Riepilogo utilizzo

> [!NOTE]
> Solo un professionista IT con un ruolo di amministratore globale può registrarsi o acconsentire esplicitamente in un tenant per il punteggio della produttività.

Il modello di controllo degli accessi in base al ruolo per Punteggio della produttività aiuta le organizzazioni a eseguire ulteriori operazioni di trasformazione digitale con Microsoft 365, fornendo la flessibilità necessaria per assegnare ruoli ai professionisti IT all'interno di un'organizzazione.

Microsoft si impegna a proteggere la privacy di tutti gli utenti. Questo [documento sulla privacy](privacy.md) spiega i controlli che forniamo, in quanto amministratori IT della tua organizzazione, per garantire che le informazioni siano utilizzabili senza compromettere la fiducia riposta in Microsoft.

È possibile accedere all'esperienza dalla home page di Amministrazione Microsoft 365 in **report** > **Punteggio della produttività**.
  
## <a name="how-the-score-is-calculated"></a>Come viene calcolato il punteggio

Il Punteggio di produttività è basato sui punteggi combinati delle categorie di persone ed esperienze con la tecnologia. Ogni categoria viene misurata proporzionalmente, con un totale di 100 punti. Il punteggio di produttività più alto possibile è 800.

### <a name="score-categories"></a>Categorie di punteggio 

- Comunicazione (100 punti)
- Riunioni (100 punti)
- Collaborazione sui contenuti (100 punti)
- Lavoro in team (100 punti)
- Mobilità (100 punti)
- Analisi endpoint (100 punti)
- Connettività di rete (100 punti)
- Integrità di Microsoft 365 Apps (100 punti)
- **Totale possibile= 800 punti**
 
In ogni categoria di punteggio, quantifichiamo gli indicatori chiave su come l'organizzazione sta utilizzando Microsoft 365 nel suo percorso verso la trasformazione digitale. Sono disponibili panoramiche sulle attività chiave di 28 giorni e 180 giorni. Sono inoltre disponibili metriche di supporto che non fanno parte del calcolo del punteggio, ma sono importanti per identificare le statistiche sull'utilizzo sottostante e le configurazioni da risolvere.

### <a name="products-included-in-productivity-score"></a>Prodotti inclusi nel punteggio della produttività 

Il punteggio della produttività include i dati di Exchange, SharePoint, OneDrive, Teams, Word, Excel, PowerPoint, OneNote, Outlook, Yammer e Skype.

Il punteggio dell'organizzazione viene aggiornato ogni giorno e riflette le azioni dell'utente completate negli ultimi 28 giorni (compreso il giorno corrente).

## <a name="interpreting-your-organizations-productivity-score"></a>Interpretare il punteggio della produttività dell'organizzazione 

La home page del punteggio della produttività mostra il punteggio totale dell'organizzazione, la cronologia del punteggio e le informazioni principali per ogni categoria.

:::image type="content" source="../../media/prodscore-landing.png" alt-text="Pagina punteggio della produttività in Report.":::

**Il punteggio dell'organizzazione** viene visualizzato come valore percentuale e in punti. È possibile visualizzare i punti nel numeratore e i punti massimi nel denominatore.

I **benchmark del peer** consentono di confrontare il punteggio con organizzazioni simili alla propria. Il benchmark del peer per le categorie di esperienze delle persone è dato da una media all'interno di un insieme di organizzazioni simili. L’insieme di organizzazioni è composto da organizzazioni della propria area geografica con un numero analogo di utenti dotati di licenza, tipi di licenze, settore ed esperienza con Microsoft 365.

> [!NOTE]
> Microsoft usa i dati interni per determinare il settore in cui un'organizzazione ha eseguito il mapping. Ai tenant in un'organizzazione padre viene eseguito il mapping allo stesso settore dell'organizzazione padre. Le organizzazioni non possono visualizzare o modificare i mapping di settore.

Il peer benchmark dell’analisi degli endpoint include obiettivi per le prestazioni di avvio del dispositivo e la configurazione software consigliata in base ai valori mediani aggregati di tutti i tenant.

Per la connettività di rete, il benchmark consigliato è 80 punti.

La sezione **Dettaglio punteggio** include un’analisi dettagliata del punteggio della produttività con benchmark per persona e aree di esperienza con la tecnologia.

La cronologia del punteggio mostra il modo in cui il punteggio di ogni categoria è cambiato negli ultimi sei mesi.

Le aree dell'**esperienze degli utenti** e le **esperienze con la tecnologia** contengono i dati analitici delle categorie in queste aree. È possibile selezionare ogni categoria per visualizzare i dati analitici.

## <a name="category-details-pages"></a>Pagine dettagli categoria

Ogni pagina dei dettagli della categoria illustra le metriche principali e di supporto, oltre a ricerche correlate e azioni che è possibile eseguire per la modifica delle unità nell'organizzazione. La ricerca supporta l'importanza e la logica alla base delle intuizioni primarie per ciascuna categoria. Per altre informazioni, [leggere il report Forrester](https://query.prod.cms.rt.microsoft.com/cms/api/am/binary/RE2PBrb).

Le pagine dei dettagli sono:
- [Collaborazione sui contenuti: esperienze delle persone](content-collaboration.md)
- [Comunicazione: esperienze delle persone](communication.md)
- [Riunioni: esperienze delle persone](meetings.md)
- [Mobilità: esperienze delle persone](mobility.md)
- [Lavoro in team: esperienze delle persone](teamwork.md)
- [Integrità Microsoft 365 Apps: esperienze con la tecnologia](apps-health.md)
- [Analisi endpoint](/mem/analytics/productivity-score)

## <a name="business-continuity-special-report"></a>Report speciale continuità aziendale

Il report sulla continuità aziendale è un report dell'intelligence di Workplace a tempo limitato, disponibile per tutti i clienti di Microsoft 365 per aiutarli a guidare le loro organizzazioni in questo periodo difficile.  

Questo report aiuta le organizzazioni a capire: 

- in che modo la collaborazione e la comunicazione sono influenzate dal passaggio al lavoro remoto. 

- l'impatto sull'equilibrio tra lavoro e vita privata, affinché gli utenti possano adattarsi al lavoro da casa. 

- se le riunioni da remoto supportano un processo decisionale efficace.

[Altre informazioni sul report continuità aziendale](/Workplace-Analytics/tutorials/bcrps)

[Altre informazioni su Microsoft Graph](/graph/).

> [!NOTE]
> Sono disponibili dati analitici sulla produttività da [MyAnalytics dashboard](/workplace-analytics/myanalytics/use/dashboard-2).


## <a name="we-want-to-hear-from-you"></a>L'opinione degli utenti è importante

È possibile condividere la propria opinione sul punteggio della produttività e le proprie idee su come migliorarlo. Usare le sezioni **Feedback** all'interno del prodotto e/o contatta il team dedicato al Punteggio della produttività all'indirizzo prodscorefeedback@microsoft.com.

## <a name="related-content"></a>Contenuto correlato

[Monitorare l'attività Microsoft 365 utilizzando i report](../../admin/activity-reports/activity-reports.md) (articolo)\
[Abilitare l'analisi dell'utilizzo di Microsoft 365](../../admin/usage-analytics/enable-usage-analytics.md) (articolo)\
[Informazioni generali sull'interfaccia di amministrazione di Microsoft 365](../../business-video/admin-center-overview.md) (video)