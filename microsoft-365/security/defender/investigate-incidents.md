---
title: Analizzare gli incidenti in Microsoft 365 Defender
description: Analizzare gli incidenti relativi a dispositivi, utenti e cassette postali.
keywords: incidente, incidenti, computer, dispositivi, utenti, identificare, posta, posta elettronica, cassetta postale, indagine, grafico, prova
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
ms.openlocfilehash: 99acc25c3949b758dab990a9c2e9104b9158accd
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861876"
---
# <a name="investigate-incidents-in-microsoft-365-defender"></a>Analizzare gli incidenti in Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**

- Microsoft 365 Defender

Microsoft 365 Defender aggrega tutti gli avvisi, gli asset, le indagini e le prove correlati provenienti da dispositivi, utenti e cassette postali in un evento imprevisto per fornire una panoramica completa dell'intera ampiezza di un attacco.

All'interno di un evento imprevisto, si esaminano gli avvisi che influiscono sulla rete, si comprende il loro significato e si fascicolano le prove in modo da poter elaborare un piano di correzione efficace.

## <a name="initial-investigation"></a>Indagine iniziale

Prima di esaminare i dettagli, esaminare le proprietà e il riepilogo dell'evento imprevisto.

È possibile iniziare selezionando l'evento imprevisto dalla colonna del segno di spunta. Di seguito viene riportato un esempio.

:::image type="content" source="../../media/investigate-incidents/incidents-ss-incident-select.png" alt-text="Esempio di selezione di un evento imprevisto dalla colonna del segno di spunta":::

Quando si esegue questa operazione, viene visualizzato un riquadro di riepilogo con informazioni chiave sull'evento imprevisto, ad esempio la gravità, a cui è assegnato e le categorie [MITRE ATT &trade;&CK](https://attack.mitre.org/) per l'evento imprevisto. Di seguito viene riportato un esempio.

:::image type="content" source="../../media/investigate-incidents/incidents-ss-incident-side-panel.png" alt-text="Esempio del riquadro di riepilogo per un evento imprevisto":::

Da qui è possibile selezionare Apri **pagina evento imprevisto.** Verrà aperta la pagina principale dell'evento imprevisto in cui sono disponibili ulteriori informazioni di riepilogo e schede per avvisi, dispositivi, utenti, indagini ed elementi di prova.

È inoltre possibile aprire la pagina principale di un evento imprevisto selezionando il nome dell'evento imprevisto dalla coda degli eventi imprevisti.

## <a name="summary"></a>Riepilogo

La **pagina** Riepilogo offre uno sguardo istantaneo sugli aspetti principali da notare sull'evento imprevisto.

:::image type="content" source="../../media/incidents-overview/incidents-ss-incident-summary.png" alt-text="Esempio della pagina Riepilogo per un evento imprevisto nel Centro sicurezza Microsoft 365":::

Le categorie di attacco offrono una visualizzazione visiva e numerica dell'avanzamento dell'attacco contro la catena di uccidi. Come per altri prodotti di sicurezza Microsoft, Microsoft 365 Defender è allineato al framework [MITRE ATT&&trade; CK.](https://attack.mitre.org/)

La sezione relativa all'ambito fornisce un elenco delle principali risorse interessate che fanno parte di questo incidente. Se sono presenti informazioni specifiche su una determinata risorsa (ad esempio, il livello di rischio, la priorità dell'indagine e i contrassegni sulle attività) saranno disponibili in questa sezione.

La sequenza temporale degli avvisi fornisce un'anteprima dell'ordine cronologico in cui si sono verificati gli avvisi, nonché i motivi per cui questi avvisi sono collegati a questo evento imprevisto.

Infine, la sezione delle prove fornisce un riepilogo del numero di artefatti diversi inclusi nell'evento imprevisto e del relativo stato di correzione, in modo da poter identificare immediatamente se è necessaria un'azione da parte dell'utente.

Questa panoramica può essere di aiuto nella analisi iniziale dell'evento imprevisto fornendo informazioni dettagliate sulle caratteristiche principali dell'evento imprevisto di cui è necessario tenere conto.

## <a name="alerts"></a>Avvisi

Nella scheda **Avviso** è possibile visualizzare la coda degli avvisi relativi all'evento imprevisto e altre informazioni su di essi, ad esempio:

- Gravità.
- Entità coinvolte nell'avviso.
- Origine degli avvisi (Microsoft Defender for Identity, Microsoft Defender for Endpoint, Microsoft Defender per Office 365).
- Motivo per cui sono stati collegati tra loro.

Di seguito viene riportato un esempio.

:::image type="content" source="../../media/investigate-incidents/incident-alerts.png" alt-text="Esempio di pagina Avvisi per un evento imprevisto":::

Per impostazione predefinita, gli avvisi vengono ordinati cronologicamente per consentire di vedere come si è verificata l'evento imprevisto nel tempo. La selezione di ogni avviso consente di accedere alla pagina principale dell'avviso, in cui è possibile eseguire un'analisi approfondita dell'avviso. 

Informazioni su come usare le pagine di avviso e coda di avviso in [Analizzare gli avvisi](investigate-alerts.md)

## <a name="devices"></a>Dispositivi

Nella **scheda Dispositivi** sono elencati tutti i dispositivi correlati all'evento imprevisto. Di seguito viene riportato un esempio.

:::image type="content" source="../../media/investigate-incidents/incident-devices.png" alt-text="Esempio di pagina Dispositivi per un evento imprevisto":::

Puoi selezionare il segno di spunta per un dispositivo per visualizzare i dettagli del dispositivo, i dati della directory, gli avvisi attivi e gli utenti connessi. Seleziona il nome del dispositivo per visualizzare i dettagli del dispositivo nell'inventario dei dispositivi di Microsoft Defender for Endpoints.

:::image type="content" source="../../media/investigate-incidents/incident-devices-details.png" alt-text="Esempio di pagina dei dispositivi per Microsoft Defender for Endpoints":::

Dalla pagina del dispositivo puoi raccogliere informazioni aggiuntive sul dispositivo, ad esempio tutti gli avvisi, una sequenza temporale e suggerimenti per la sicurezza. Ad esempio, dalla scheda **Sequenza** temporale puoi scorrere la sequenza temporale del computer e visualizzare tutti gli eventi e i comportamenti osservati nel computer in ordine cronologico, in sequenza con gli avvisi generati.

> [!TIP]
> Puoi eseguire analisi su richiesta in una pagina del dispositivo. Nel Centro sicurezza Microsoft 365 scegliere **Endpoint > inventario del dispositivo**. Selezionare un dispositivo con avvisi ed eseguire un'analisi antivirus. Le azioni, ad esempio le analisi antivirus, vengono rilevate e visibili nella **pagina Inventario** dispositivi. Per altre informazioni, vedi [Eseguire l'analisi di Microsoft Defender Antivirus nei dispositivi.](/microsoft-365/security/defender-endpoint/respond-machine-alerts#run-microsoft-defender-antivirus-scan-on-devices)

## <a name="users"></a>Utenti

Nella **scheda Utenti** sono elencati tutti gli utenti identificati come parte o correlati all'evento imprevisto. Di seguito viene riportato un esempio.

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="Esempio di pagina Utenti per un evento imprevisto":::

È possibile selezionare il segno di spunta per un utente per visualizzare i dettagli della minaccia, dell'esposizione e delle informazioni di contatto dell'account utente. Selezionare il nome utente per visualizzare ulteriori dettagli sull'account utente.

## <a name="mailboxes"></a>Cassette postali

Nella **scheda Cassette** postali sono elencate tutte le cassette postali identificate come parte o correlate all'evento imprevisto. Di seguito viene riportato un esempio.

:::image type="content" source="../../media/investigate-incidents/incident-mailboxes.png" alt-text="Esempio di pagina Cassette postali per un evento imprevisto":::

È possibile selezionare il segno di spunta per una cassetta postale per visualizzare un elenco di avvisi attivi. Selezionare il nome della cassetta postale per visualizzare ulteriori dettagli della cassetta postale nella pagina Esplora per Microsoft Defender per Office 365.

## <a name="investigations"></a>Indagini

Nella **scheda Indagini** sono elencate tutte le indagini automatizzate attivate dagli avvisi in questo evento imprevisto. Le indagini eseguiranno azioni di correzione o attenderanno l'approvazione degli analisti delle azioni, a seconda di come sono configurate le indagini automatizzate per l'esecuzione in Microsoft Defender per Endpoint e Defender per Office 365.

:::image type="content" source="../../media/investigate-incidents/incident-investigations.png" alt-text="Esempio di pagina Indagini per un evento imprevisto":::

Selezionare un'indagine per accedere alla pagina dei dettagli dell'indagine per ottenere informazioni complete sull'indagine e sullo stato della correzione. Se sono presenti azioni in sospeso per l'approvazione nell'ambito dell'indagine, verranno visualizzate nella scheda Azioni in sospeso. Eseguire un'azione nell'ambito della correzione degli eventi imprevisti.

## <a name="evidence-and-response"></a>Prova e risposta

La **scheda Prova e risposta** mostra tutti gli eventi supportati e le entità sospette negli avvisi nell'evento imprevisto. Di seguito viene riportato un esempio.

:::image type="content" source="../../media/investigate-incidents/incident-evidence.png" alt-text="Esempio di pagina Prova e risposta per un evento imprevisto":::

Microsoft 365 Defender analizza automaticamente tutti gli eventi supportati e le entità sospette degli incidenti negli avvisi, fornendo informazioni sui messaggi di posta elettronica, i file, i processi, i servizi, gli indirizzi IP e altro ancora importanti. In questo modo è possibile rilevare e bloccare rapidamente potenziali minacce nell'evento imprevisto.

Ogni entità analizzata è contrassegnata con un verdetto (Dannoso, Sospetto, Pulito) e uno stato di correzione. In questo modo è possibile comprendere lo stato di correzione dell'intero evento imprevisto e i passaggi successivi.

## <a name="related-topics"></a>Argomenti correlati

- [Panoramica sugli incidenti](incidents-overview.md)
- [Assegnare priorità agli incidenti](incident-queue.md)
- [Gestire gli incidenti](manage-incidents.md)

