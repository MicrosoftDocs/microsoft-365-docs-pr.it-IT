---
title: Punteggio di produttività Microsoft - Collaborazione contenuto
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
monikerRange: o365-worldwide
search.appverid:
- MET150
- MOE150
description: Dettagli della collaborazione contenuto - Esperienze utente Punteggio di produttività.
ms.openlocfilehash: 2921cc738d1325416a0a5a8ab4a8eea9456b3269
ms.sourcegitcommit: 17d82e5617f0466eb825e15ab88594afcdaf4437
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/06/2021
ms.locfileid: "53300084"
---
# <a name="content-collaboration--people-experiences"></a>Collaborazione contenuto - Esperienze utente

Il punteggio di produttività fornisce informazioni approfondite sul percorso di trasformazione digitale dell'organizzazione attraverso l'uso di Microsoft 365 e le esperienze tecnologiche che la supportano. Il punteggio dell'organizzazione riflette le misurazioni delle persone e dell'esperienza tecnologica e può essere confrontato con i benchmark di organizzazioni simili al tuo. La categoria di collaborazione del contenuto fa parte delle misurazioni dell'esperienza utente. Per ulteriori informazioni, consultare la panoramica [del punteggio di produttività](productivity-score.md) e leggere [l'Informativa sulla privacy di Microsoft.](https://privacy.microsoft.com/privacystatement)

## <a name="prerequisites"></a>Prerequisiti

Per iniziare a usare le informazioni dettagliate sulla collaborazione dei contenuti, gli utenti dell'organizzazione devono disporre di una licenza per:

- OneDrive for Business
- SharePoint
- Exchange Online

Per ulteriori informazioni, vedere [assegnare licenze agli utenti.](../manage/assign-licenses-to-users.md)

 Dopo che le persone sono state attive nei prodotti di cui sopra almeno una volta negli ultimi 28 giorni, inizi a vedere le informazioni dettagliate.

## <a name="why-your-organization39s-content-collaboration-score-matters"></a>Perché l'organizzazione&#39;il punteggio di collaborazione dei contenuti è importante

Un aspetto chiave della trasformazione digitale è il modo in cui le persone collaborano nei file. Con il contenuto in Microsoft 365, gli utenti accedono, creano, modificano e collaborano al contenuto con altri utenti da qualsiasi posizione. La ricerca mostra che quando le persone collaborano con i file online, ogni persona risparmia in media 100 minuti a settimana.

## <a name="how-we-calculate-the-content-collaboration-score"></a>Come viene calcolato il punteggio di collaborazione del contenuto

Forniamo una panoramica principale che contiene le metriche chiave per la collaborazione dei contenuti nell'organizzazione. Viene quindi usato un framework di punteggio descritto di seguito per queste metriche per calcolare il punteggio dell'organizzazione.

> [!NOTE]
> Il 22 aprile 2021 è stato modificato il modo in cui viene calcolata la metrica dei collaboratori. Ciò influisce [sulle informazioni principali,](#primary-insight)sulla collaborazione [su file](#number-of-files-collaborated-on)e sul modo in cui viene misurato il punteggio di collaborazione del contenuto. Questa modifica consente di ridurre il rumore dei dati provenienti da agenti non umani (o bot) da Microsoft e da altre applicazioni di terze parti, con conseguente punteggio più accurato e utilizzabile.

### <a name="primary-insight"></a>Informazioni principali

Microsoft OneDrive per le aziende e SharePoint aiutare gli utenti a creare, leggere e individuare facilmente il contenuto individuale e condiviso in Microsoft 365 da dispositivi e applicazioni. Consentono inoltre agli utenti di condividere e collaborare in modo sicuro al contenuto. Le informazioni dettagliate principali contengono informazioni di tutti gli utenti che possono OneDrive for Business e SharePoint. Vengono inoltre scomporsi i dettagli sul numero di persone che leggono, creano e collaborano al contenuto archiviato in OneDrive for Business e SharePoint.

:::image type="content" source="../../media/collabscore_primary.jpg" alt-text="Dati principali del punteggio di collaborazione per le comunicazioni.":::


I tipi considerati per queste informazioni includono i file Word, Excel, PowerPoint, OneNote e PDF.

1. **Intestazione:** Mostra la percentuale di persone dell'organizzazione che hanno accesso a OneDrive o SharePoint che collaborano al contenuto.
2. **Corpo:** Fornisce ulteriori informazioni sul modo in cui i comportamenti di lettura e creazione di file online sono collegati alla collaborazione sui file.
3. **Visualizzazione (stato corrente):**
    - Barre orizzontali in cui le parti di colore blu rappresentano la percentuale di persone abilitate per la collaborazione di file tramite OneDrive o SharePoint che sono stati **lettori,** creatori o **collaboratori** di file online negli ultimi 28 giorni.

        Sono definiti come segue:</br>
        **Lettori:** Persone che accedono o scaricano file online in OneDrive o SharePoint.</br>
        **Creatori:** Persone che creano, modificano, caricano, sincronizzano, archiviano, copiano o spostano file OneDrive o SharePoint online.</br>
        **Collaboratori:** Persone che collaborano con i file online usando OneDrive o SharePoint. Due persone sono collaboratori se una di esse legge o modifica un app Office online o un PDF dopo che l'altra persona lo ha creato o modificato, entro una finestra di 28 giorni.

        > [!NOTE]
        > I file considerati nella visualizzazione sono i file word, Excel, PowerPoint, OneNote o PDF online e salvati in OneDrive o SharePoint. 

    - L'evidenziazione (numeratore/denominatore) della frazione viene utilizzata per calcolare la percentuale espressa in ognuna delle barre orizzontali.
    
      - **Lettori:**</br>
          - Numeratore: numero di persone che accedono o scaricano file online in OneDrive o SharePoint negli ultimi 28 giorni</br>
          - Denominatore: numero di persone che hanno avuto accesso a OneDrive o SharePoint per almeno 1 degli ultimi 28 giorni</br>
      - **Creatori:**</br>
        - Numeratore: numero di persone che creano, modificano, caricano, sincronizzano, archiviano, copiano o spostano file online in OneDrive o SharePoint negli ultimi 28 giorni</br>
        - Denominatore: numero di persone che hanno avuto accesso a OneDrive o SharePoint per almeno 1 degli ultimi 28 giorni. </br> 
      - **Collaboratori:**</br>
        - Numeratore: numero di persone che hanno collaborato a file online in OneDrive o SharePoint negli ultimi 28 giorni</br>
        - Denominatore: numero di persone che hanno avuto accesso a OneDrive o SharePoint per almeno 1 degli ultimi 28 giorni

    - Il valore di benchmark peer per ogni lettore, creatore e collaboratore viene visualizzato come percentuale. In altre parole, il valore del numero di creatori viene visualizzato come percentuale del numero di persone che hanno accesso a OneDrive o SharePoint.
    
1. **Collegamento alle risorse:** Selezionare questo collegamento per visualizzare i video fascicolati e altri contenuti della Guida correlati.


#### <a name="trend-visualization-of-primary-insight"></a>Visualizzazione delle tendenze delle informazioni principali

Il grafico delle visualizzazioni delle tendenze mostra la linea di tendenza delle metriche chiave di approfondimento principali per lettori, creatori e collaboratori, negli ultimi 180 giorni. Ogni punto dati del grafico è un aggregato di attività per gli ultimi 28 giorni. Ogni punto dati creatore fornisce un conteggio di tutte le persone contrassegnate come creatori negli ultimi 28 giorni per ogni data sull'asse x.

:::image type="content" source="../../media/trendvisualization.jpg" alt-text="Grafico delle tendenze per le informazioni principali sulla collaborazione.":::

### <a name="scoring-framework"></a>Framework di punteggio

Il punteggio di collaborazione del contenuto per le misure dell'organizzazione a livello aggregato (organizzazione) sia che gli utenti leggono, creino o collaborino costantemente su file Office online come Word, Excel, PowerPoint, OneNote o PDF o in OneDrive o SharePoint.

I punteggi non vengono forniti a livello di singolo utente.

## <a name="explore-how-your-organization-collaborates"></a>Esplorare il modo in cui l'organizzazione collabora

Vengono inoltre fornite informazioni che consentono di acquisire visibilità sul modo in cui l'organizzazione collabora al contenuto. Queste metriche aggiuntive non contribuiscono direttamente al punteggio di produttività, ma consentono di creare un piano d'azione come parte della trasformazione digitale per ottimizzare il modo in cui le persone lavorano.

### <a name="creating-files-in-onedrive-or-sharepoint"></a>Creazione di file in OneDrive o SharePoint

:::image type="content" source="../../media/sharepointonedrivefiles.jpg" alt-text="Grafico che mostra il numero di persone che creano file in OneDrive o SharePoint":::

1. **Intestazione:** Evidenzia la percentuale di persone attive nelle Microsoft 365 Office che creano file OneDrive o SharePoint.
2. **Corpo:** Fornisce informazioni sul valore della creazione di contenuto in OneDrive e SharePoint.
3. **Visualizzazione:** La suddivisione nella visualizzazione rappresenta la misura in cui gli utenti che usano Microsoft Office app per creare file in OneDrive e SharePoint, come indicato di seguito:
      - **OneDrive:** La parte blu (colorata) della barra e la frazione sulla barra rappresentano la percentuale di persone attive nelle applicazioni Office che creano contenuto OneDrive come segue:
        - Numeratore: numero di persone che creano, modificano, caricano, sincronizzano, archiviano, copiano o spostano file Office online OneDrive negli ultimi 28 giorni.</br>
        - Denominatore: numero di persone che hanno accesso a OneDrive o SharePoint e accedono ai file di Office negli ultimi 28 giorni.
      - **SharePoint:** La parte blu (colorata) della barra e la frazione sulla barra rappresentano la percentuale di persone attive nelle applicazioni Office e creano contenuto in SharePoint come:</br>
         - Numeratore: numero di persone che creano, modificano, caricano, sincronizzano, archiviano, copiano o spostano file Office online (file Microsoft Word, Excel, PowerPoint o OneNote) in SharePoint negli ultimi 28 giorni.</br>
        - Denominatore: numero di persone che hanno accesso a OneDrive o SharePoint e hanno eseguito l'accesso Office file negli ultimi 28 giorni.

4. **Collegamento alle risorse:** Selezionare questo collegamento per visualizzare il contenuto della Guida.

### <a name="use-of-attachments-in-email"></a>Uso degli allegati nella posta elettronica

**Uso degli allegati nella posta elettronica** Comprendere quanti utenti allegano file fisici nella posta elettronica anziché collegamenti al contenuto nel cloud e monitorare la riduzione di questo numero nel tempo.

:::image type="content" source="../../media/emailattachments.png" alt-text="Utilizzo di allegati di posta elettronica.":::

1. **Intestazione:** Evidenzia la percentuale di persone che utilizzano allegati nei messaggi di posta elettronica che non sono stati salvati OneDrive o SharePoint.
2. **Corpo:** Fornisce informazioni sul valore della condivisione dei collegamenti ai file online dal punto di vista della collaborazione e della sicurezza.
3. **Visualizzazione:** La suddivisione nella visualizzazione ha lo scopo di rappresentare la misura in cui gli utenti che allegano contenuto nei messaggi di posta elettronica utilizzano modalità diverse (file non presenti in OneDrive o SharePoint, collegamenti a file online e collegamenti incorporati nel messaggio di posta elettronica):
      - **Allega file:** La parte blu (colorata) della barra e la frazione (numeratore/denominatore) sulla barra rappresenta la percentuale di persone che utilizzano allegati nei messaggi di posta elettronica.
        - Numeratore: numero di persone che allegano file alla posta elettronica che non sono stati salvati OneDrive o SharePoint negli ultimi 28 giorni.
        - Denominatore: numero di persone che hanno avuto accesso a Exchange e OneDrive, SharePoint o a entrambi negli ultimi 28 giorni.
      - **Collegamenti a file online:** La parte blu (colorata) della barra e la frazione (numeratore/denominatore) sulla barra rappresentano la percentuale di persone che utilizzano allegati e allegano collegamenti a file nei messaggi di posta elettronica.
        - Numeratore: numero di persone che allegano collegamenti a file online (salvati in OneDrive o SharePoint) ai messaggi di posta elettronica negli ultimi 28 giorni.
        - Denominatore: numero di persone che hanno accesso a Exchange e OneDrive, SharePoint o a entrambi negli ultimi 28 giorni.
4. **Collegamento alle risorse:** Selezionare questo collegamento per visualizzare il contenuto della Guida.

### <a name="sharing-of-online-files"></a>Condivisione di file online

:::image type="content" source="../../media/sharingonlinefiles.png" alt-text="Grafico che mostra il numero di persone che condividono file online.":::

1. **Intestazione:** Evidenzia la percentuale di persone che hanno accesso a OneDrive o SharePoint che condividono file esternamente.
2. **Corpo:** Fornisce informazioni sugli amministratori&#39; di modificare le impostazioni di condivisione file nell'organizzazione per abilitare il livello di collaborazione più adatto all'organizzazione.
3. **Visualizzazione:** Rappresenta la misura in cui gli utenti che hanno accesso a OneDrive o SharePoint condividono file internamente o esternamente:
      - **Esternamente:** La parte blu (colorata) della barra e la frazione (numeratore/denominatore) sulla barra rappresentano la percentuale di persone che hanno accesso a OneDrive o SharePoint e condividono file esternamente.
        -  Numeratore: numero di persone con cui i file sono stati condivisi esternamente negli ultimi 28 giorni
        - Denominatore: il numero totale di persone che hanno avuto accesso a OneDrive o SharePoint per almeno 1 degli ultimi 28 giorni.
      - **Solo internamente:** La parte blu (colorata) della barra e la frazione (numeratore/denominatore) sulla barra rappresentano la percentuale di persone che hanno accesso a OneDrive o SharePoint e condividono i file solo internamente.
        - Numeratore: numero di persone che hanno condiviso i file internamente solo negli ultimi 28 giorni
        - Denominatore: il numero totale di persone che hanno avuto accesso a OneDrive o SharePoint per almeno 1 degli ultimi 28 giorni.
4. **Collegamento alle risorse:** Selezionare questo collegamento per visualizzare il contenuto della Guida.

### <a name="number-of-files-collaborated-on"></a>Numero di file a cui è stata collaborata

:::image type="content" source="../../media/intensityofcollab.png" alt-text="Grafico che mostra il numero di file su cui è stata più collaborata.":::

1. **Intestazione:** Evidenzia la percentuale di persone che hanno accesso a OneDrive o SharePoint che collaborano a 4 o più file.
2. **Corpo:** Fornisce informazioni su come gli utenti possono sfruttare i file online per una migliore collaborazione.
3. **Visualizzazione:** Mostra una distribuzione delle persone che hanno accesso a OneDrive o SharePoint, in base al numero di file a cui collaborano. Ciò viene mostrato nelle quattro categorie seguenti (per ognuna, la parte blu della barra e la frazione rappresentano la percentuale di persone che hanno accesso a OneDrive o SharePoint che rientrano in tale categoria):
      - **Nessuna collaborazione:**
        - Numeratore: numero di persone che non collaborano ad alcun file negli ultimi 28 giorni.
        - Denominatore: numero totale di persone che hanno accesso a OneDrive o SharePoint per almeno 1 degli ultimi 28 giorni.
      - **Collaborazione su 1-3 file:**
        - Numeratore: numero di persone che collaborano a 1-3 file negli ultimi 28 giorni.
        - Denominatore: numero totale di persone che hanno avuto accesso a OneDrive o SharePoint per almeno 1 degli ultimi 28 giorni.
      - **Collaborazione su 4-10 file:**
        - Numeratore: numero di persone che collaborano a 4-10 file negli ultimi 28 giorni.
        - Denominatore: numero totale di persone che hanno avuto accesso a OneDrive o SharePoint per almeno 1 degli ultimi 28 giorni.
      - **Collaborazione su 11 o più file:**
        - Numeratore: numero di persone che collaborano a 11 o più file negli ultimi 28 giorni.
        - Denominatore: numero totale di persone che hanno avuto accesso a OneDrive o SharePoint per almeno 1 degli ultimi 28 giorni.
        
4. **Collegamento alle risorse:** Selezionare questo collegamento per visualizzare il contenuto della Guida.

### <a name="network-performance-strength-for-onedrive-and-sharepoint"></a>Potenza delle prestazioni di rete per OneDrive e SharePoint

:::image type="content" source="../../media/networkperfstrength.png" alt-text="Grafico delle prestazioni di rete per OneDrive e SharePoint.":::

1. **Intestazione:** Evidenzia la percentuale di dispositivi di tutti i dispositivi testati con una connessione di rete scarsa OneDrive e SharePoint. 
2. **Corpo:** Fornisce informazioni sui motivi per cui le prestazioni delle connessioni di rete sono importanti per la collaborazione. 
3. **Visualizzazione:** Mostra una percentuale di dispositivi con diversi livelli di prestazioni di connettività di rete correlati a OneDrive e SharePoint:
      - **81-100 (migliore):** la parte verde scuro (colorata) della barra rappresenta la percentuale di dispositivi con le prestazioni migliori.
      - **61-80**: la parte verde (colorata) della barra rappresenta la percentuale di dispositivi con un punteggio di prestazioni di rete compreso tra 60 e 80. 
      - **41-60**: la parte arancione (colorata) della barra rappresenta la percentuale di dispositivi con un punteggio di prestazioni di rete compreso tra 40 e 60. 
      - **21-40**: La parte rossa (colorata) della barra rappresenta la percentuale di dispositivi con un punteggio di prestazioni di rete compreso tra 20 e 40. 
      - **0-20**: la parte rosso scuro (colorata) della barra rappresenta la percentuale di dispositivi con il peggior punteggio di prestazioni di rete compreso tra 0 e 20. 

## <a name="related-content"></a>Contenuto correlato

[Microsoft 365 integrità delle app - Esperienze tecnologiche](apps-health.md) (articolo)\
[Comunicazione - Esperienze degli utenti](communication.md) (articolo)\
[Riunioni - Esperienze utente](meetings.md) (articolo)\
[Mobilità - Esperienze degli utenti](mobility.md) (articolo)\
[Controlli della privacy per il punteggio di produttività](privacy.md) (articolo)\
[Lavoro in team - Esperienze degli utenti](teamwork.md) (articolo)
