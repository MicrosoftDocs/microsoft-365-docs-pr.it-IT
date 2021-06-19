---
title: Assegnare priorità agli eventi imprevisti in Microsoft 365 Defender
description: Informazioni su come filtrare gli eventi imprevisti dalla coda degli eventi imprevisti in Microsoft 365 Defender
keywords: incidente, coda, panoramica, dispositivi, identità, utenti, cassetta postale, posta elettronica, eventi imprevisti, analizzare, risposta
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 4d793d49d669510b722a72160ae396ee73ab9699
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028512"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a>Assegnare priorità agli eventi imprevisti in Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Si applica a:**
- Microsoft 365 Defender

Microsoft 365 Defender l'analisi della correlazione e aggrega gli avvisi correlati e le indagini automatizzate di prodotti diversi in un evento imprevisto. Microsoft 365 Defender attiva anche avvisi univoci sulle attività che possono essere identificate solo come dannose data la visibilità end-to-end che Microsoft 365 Defender ha nell'intera famiglia di prodotti. Questa visualizzazione offre agli analisti della sicurezza la più ampia storia di attacco, che li aiuta a comprendere meglio e gestire le minacce complesse all'interno dell'organizzazione.

La **coda eventi imprevisti** mostra una raccolta di eventi imprevisti creati su dispositivi, utenti e cassette postali. Ti aiuta a ordinare gli eventi imprevisti in base alla loro priorità e a definire una risposta di cybersecurity mirata. 

Si arriva alla coda degli eventi imprevisti da **Eventi imprevisti &** avvisi > eventi imprevisti sulla barra di avvio veloce del portale di Microsoft 365 Defender ([security.microsoft.com](https://security.microsoft.com)). Di seguito viene riportato un esempio.

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Esempio di coda degli eventi imprevisti":::

La **sezione Eventi imprevisti e avvisi più** recenti mostra un grafico del numero di avvisi ricevuti e di eventi imprevisti creati nelle ultime 24 ore.

Per impostazione predefinita, nella coda degli eventi imprevisti nel portale Microsoft 365 Defender vengono visualizzati gli eventi imprevisti visualizzati negli ultimi sei mesi. L'evento imprevisto più recente si trova all'inizio dell'elenco in modo da poterlo visualizzare per primo.

La coda eventi imprevisti include colonne personalizzabili **(selezionare** Scegli colonne) che offrono visibilità sulle diverse caratteristiche dell'evento imprevisto o sulle entità influenzate. Ciò consente di prendere una decisione informata sulla definizione di priorità degli incidenti per l'analisi.

Per una maggiore visibilità a colpo d'occhio, la denominazione automatica degli eventi imprevisti genera nomi di eventi imprevisti in base agli attributi di avviso, ad esempio il numero di endpoint interessati, gli utenti interessati, le origini di rilevamento o le categorie. In questo modo è possibile comprendere rapidamente l'ambito dell'evento imprevisto.

Ad esempio: *evento imprevisto a più fasi in più endpoint segnalati da più origini.*

> [!NOTE]
> Gli eventi imprevisti che si verificavano prima dell'implementazione della denominazione automatica degli eventi imprevisti non cambieranno il nome.

La coda degli eventi imprevisti espone inoltre più opzioni di filtro, che, se applicate, consentono di eseguire un'ampia gamma di tutti gli eventi imprevisti esistenti nell'ambiente o di decidere di concentrarsi su uno scenario o una minaccia specifici. Applicando i filtri a una coda di eventi imprevisti puoi determinare quale evento richiede un’attenzione immediata. 

## <a name="available-filters"></a>Filtri disponibili

Dalla coda eventi imprevisti predefinita, è possibile selezionare **Filtri** per visualizzare un riquadro Filtri, da cui è possibile visualizzare un set filtrato di eventi imprevisti. Ecco un esempio.

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-filters.png" alt-text="Esempio del riquadro dei filtri per la coda eventi imprevisti":::

In questa tabella sono elencati i nomi dei filtri disponibili.

| Nome filtro | Descrizione |
|:-------|:-----|
| Assegnata a | Puoi scegliere di visualizzare gli avvisi assegnati all'utente o a quelli gestiti dall'automazione. |
| Categorie | Scegli le categorie per concentrarti su tattiche, tecniche o componenti di attacco specifici. |
| Classificazione | Filtrare gli eventi imprevisti in base alle classificazioni impostate degli avvisi correlati. I valori includono avvisi true, falsi avvisi o non impostati. |
| Riservatezza dei dati | Alcuni attacchi sono incentrati sull’estrazione di dati riservati o di valore. Applicando un filtro per vedere se sono coinvolte informazioni riservate nell'evento, puoi determinare rapidamente se le informazioni riservate sono potenzialmente compromesse e assegnare priorità all'intervento. <br><br> Applicabile solo se Microsoft Information Protection è attivo.|
| Gruppo di dispositivi | Filtra in base ai gruppi di dispositivi definiti. |
| Stato dell'indagine | Filtra gli incidenti in base allo stato dell'indagine automatizzata.  |
| Più categorie | È possibile scegliere di visualizzare solo gli eventi imprevisti mappati a più categorie e quindi causare più danni. |
| Più servizi di origine  | Filtra per visualizzare solo gli eventi imprevisti che contengono avvisi da origini diverse (Microsoft Defender per Endpoint, Microsoft Cloud App Security, Microsoft Defender per l'identità, Microsoft Defender per Office 365). |
| Piattaforma del sistema operativo | Limitare la visualizzazione della coda degli eventi imprevisti in base al sistema operativo. |
| Servizi di origine | Scegliendo un’origine specifica puoi concentrarti sugli eventi imprevisti che contengono almeno un avviso dall'origine selezionata. |
| Gravità | La gravità di un incidente è indicativa dell'impatto che può avere sulle risorse. Maggiore è la gravità, maggiore è l'impatto e in genere richiede l'attenzione più immediata. |
| Stato | Puoi scegliere di limitare l'elenco degli eventi imprevisti visualizzati in base al loro stato per vedere quali sono attivi o risolti. |
|||

## <a name="save-defined-filters-as-urls"></a>Salvare i filtri definiti come URL

Dopo aver configurato un filtro utile nella coda degli eventi imprevisti, è possibile aggiungere un segnalibro all'URL della scheda del browser o salvarlo in altro modo come collegamento in una pagina Web, in un documento di Word o in un punto a scelta. In questo modo sarà possibile accedere con un solo clic alle visualizzazioni chiave della coda degli eventi imprevisti, ad esempio:

- Nuovi eventi imprevisti
- Eventi imprevisti di gravità elevata
- Eventi imprevisti non assegnati
- Eventi imprevisti non assegnati e di gravità elevata
- Eventi imprevisti assegnati a me
- Eventi imprevisti assegnati a me e a Microsoft Defender per Endpoint
- Eventi imprevisti con uno o più tag specifici
- Eventi imprevisti con una categoria di minacce specifica
- Eventi imprevisti con una minaccia associata specifica
- Eventi imprevisti con un attore specifico

Dopo aver compilato e archiviato l'elenco di visualizzazioni filtro utili come URL, è possibile utilizzarlo per elaborare e definire rapidamente le priorità degli eventi imprevisti nella coda e gestirli per l'assegnazione e l'analisi successive. [](manage-incidents.md)

## <a name="next-steps"></a>Passaggi successivi

Dopo aver determinato quale evento imprevisto richiede la priorità più alta, selezionarlo e:

- [Gestire](manage-incidents.md) le proprietà dell'evento imprevisto per tag, assegnazione, risoluzione immediata per incidenti falsi positivi e commenti.
- Iniziare le [indagini](investigate-incidents.md).

## <a name="see-also"></a>Vedere anche
- [Panoramica degli eventi imprevisti](incidents-overview.md)
- [Gestire gli incidenti](manage-incidents.md)
- [Indagare sugli incidenti](investigate-incidents.md)
