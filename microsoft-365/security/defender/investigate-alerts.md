---
title: Analizzare gli avvisi in Microsoft 365 Defender
description: Analizzare gli avvisi visualizzati su dispositivi, utenti e cassette postali.
keywords: incidenti, avvisi, analizzare, analizzare, risposta, correlazione, attacco, computer, dispositivi, utenti, identità, identità, identità, cassetta postale, posta elettronica, 365, microsoft, m365
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
ms.openlocfilehash: 18b4df6a2dbb22235d6781f1430f7a75e319fbcf
ms.sourcegitcommit: 4076b43a4b661de029f6307ddc1a989ab3108edb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2021
ms.locfileid: "51939543"
---
# <a name="analyze-alerts-in-microsoft-365-defender"></a>Analizzare gli avvisi in Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Si applica a:**
- Microsoft 365 Defender

Gli avvisi sono alla base di tutti gli eventi imprevisti e indicano il verificarsi di eventi dannosi o sospetti nell'ambiente. Gli avvisi fanno in genere parte di un attacco più ampio e forniscono indicazioni su un evento imprevisto.

In Microsoft 365 Defender, gli avvisi correlati vengono aggregati insieme per formare [eventi imprevisti.](incidents-overview.md) Gli incidenti forniscono sempre il contesto più ampio di un attacco, tuttavia, l'analisi degli avvisi può essere utile quando è necessaria un'analisi più approfondita. 

La **coda Avvisi** mostra il set corrente di avvisi. Si arriva alla coda degli avvisi da **Eventi imprevisti & avvisi > avvisi** sulla barra di avvio veloce del Centro sicurezza Microsoft 365 ([security.microsoft.com](https://security.microsoft.com)).

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-queue.png" alt-text="Esempio di coda degli avvisi":::

Gli avvisi di diverse soluzioni di sicurezza Microsoft come Microsoft Defender for Endpoint, Microsoft Defender per Office 365 e Microsoft 365 Defender vengono visualizzati qui.

Per impostazione predefinita, nella coda degli avvisi nel Centro sicurezza Microsoft 365 vengono visualizzati gli avvisi nuovi e in corso degli ultimi 30 giorni. L'avviso più recente si trova all'inizio dell'elenco in modo da poterlo visualizzare per primo. 

Dalla coda degli avvisi predefinita, è  possibile selezionare **Filtri** per visualizzare un riquadro Filtri, da cui è possibile specificare un sottoinsieme degli avvisi. Di seguito viene riportato un esempio.

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-filter.png" alt-text="Esempio del riquadro dei filtri per la coda degli avvisi":::

È possibile filtrare gli avvisi in base ai criteri seguenti:

- Gravità
- Stato
- Categoria
- Origine di rilevamento
- Tag
- Criteri
- Asset influenzati

## <a name="analyze-an-alert"></a>Analizzare un avviso

Per visualizzare la pagina di avviso principale, selezionare il nome dell'avviso. Di seguito viene riportato un esempio.

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-main.png" alt-text="Esempio della pagina dei dettagli di un avviso nel Centro sicurezza Microsoft 365":::

È inoltre possibile selezionare **l'azione Apri la pagina di avviso** principale nel riquadro **Gestisci** avviso.

Una pagina di avviso è composta da queste sezioni: 

- Alert story
- Azioni intraprese (incluse le risorse influenzate)
- Eventi correlati
- Dettagli di riepilogo

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-main.png" alt-text="Esempio della pagina dei dettagli di un avviso nel Centro sicurezza Microsoft 365":::

In tutta una pagina di avviso, puoi selezionare i puntini di sospensione (**...**) accanto a qualsiasi entità per visualizzare le azioni disponibili, ad esempio l'apertura della pagina di asset specifica o la procedura di correzione specifica.

### <a name="analyze-affected-assets"></a>Analizzare gli asset interessati

La **sezione Azioni eseguite** contiene un elenco di asset interessati, ad esempio cassette postali, dispositivi e utenti interessati da questo avviso. 

È inoltre possibile selezionare **Visualizza nel centro notifiche** per visualizzare la scheda **Cronologia** del **centro** notifiche nel centro sicurezza Microsoft 365. 

### <a name="trace-an-alerts-role-in-the-alert-story"></a>Tracciare il ruolo di un avviso nella storia di avviso

La storia dell'avviso visualizza tutti gli asset o le entità correlati all'avviso in una visualizzazione albero del processo. L'avviso nel titolo è quello a fuoco quando si atterra per la prima volta nella pagina dell'avviso selezionato. Gli asset nella storia di avviso sono espandibili e selezionabili. Forniscono informazioni aggiuntive e velocizzano la risposta consentendoti di intervenire direttamente nel contesto della pagina di avviso. 

> [!NOTE]
> La sezione della storia dell'avviso può contenere più di un avviso, con altri avvisi correlati allo stesso albero di esecuzione visualizzati prima o dopo l'avviso selezionato.

### <a name="view-more-alert-information-on-the-details-page"></a>Visualizzare ulteriori informazioni sugli avvisi nella pagina dei dettagli

La pagina dei dettagli mostra i dettagli dell'avviso selezionato, con i dettagli e le azioni ad esso correlati. Se si seleziona una delle risorse o entità interessate nella storia di avviso, la pagina dei dettagli cambia per fornire informazioni contestuali e azioni per l'oggetto selezionato.

Dopo aver selezionato un'entità di interesse, la pagina dei dettagli cambia per visualizzare le informazioni sul tipo di entità selezionato, le informazioni storiche quando sono disponibili e le opzioni per eseguire un'azione su questa entità direttamente dalla pagina di avviso.

## <a name="manage-alerts"></a>Gestire gli avvisi

Per gestire un avviso, selezionare l'avviso nella coda degli avvisi nella riga corrispondente per visualizzare un **riquadro Gestisci** avviso. Di seguito viene riportato un esempio.

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-manage.png" alt-text="Esempio del riquadro di riepilogo per un avviso":::

Il **riquadro Gestisci** avviso consente di specificare:

- Stato dell'avviso (Nuovo, Risolto, In corso).
- Classificazione dell'avviso (Non impostato, True alert, False Alert).
- Per la classificazione come avviso vero, il tipo di minaccia per l'avviso nel **campo Determinazione.**
- Commento sull'avviso.

> [!NOTE]
> Un modo per gestire gli avvisi tramite l'uso di tag. La funzionalità di tagging per Microsoft Defender per Office 365 è in fase di implementazione incrementale ed è attualmente in anteprima. <br>
> Attualmente, i nomi dei tag modificati vengono applicati solo agli avvisi creati *dopo l'aggiornamento.* Gli avvisi generati prima della modifica non rifletteranno il nome del tag aggiornato. 

Da questo riquadro è inoltre possibile eseguire queste azioni aggiuntive: 

- Aprire la pagina di avviso principale
- Consultare un esperto di minacce Microsoft
- Visualizzare l'invio
- Collegamento a un altro evento imprevisto
- Visualizzare l'avviso in una sequenza temporale
- Creare una regola di eliminazione

Di seguito viene riportato un esempio.

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-actions.png" alt-text="Esempio di azioni su un avviso nel Centro sicurezza Microsoft 365":::

L'elenco delle azioni aggiuntive dipende dal tipo di avviso.

## <a name="resolve-an-alert"></a>Risolvere un avviso

Una volta completata l'analisi di un avviso e  può essere risolto, passare al riquadro  Gestisci avviso per l'avviso e contrassegnarlo come Risolto e classificarlo come avviso **False** o **True.** Per gli avvisi veri, specificare il tipo di minaccia dell'avviso nel **campo Determinazione.**

Classificare gli avvisi e specificarne la determinazione aiuta a ottimizzare Microsoft 365 Defender per fornire avvisi più veri e meno falsi.

## <a name="see-also"></a>Vedere anche

- [Panoramica degli eventi imprevisti](incidents-overview.md)
- [Gestire gli incidenti](manage-incidents.md)
- [Analizzare gli eventi imprevisti](investigate-incidents.md)
