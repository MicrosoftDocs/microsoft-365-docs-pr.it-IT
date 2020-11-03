---
title: Esaminare gli incidenti in Microsoft 365 Defender
description: Analizzare gli incidenti relativi a dispositivi, utenti e cassette postali.
keywords: incidente, incidenti, computer, dispositivi, utenti, identificare, posta, posta elettronica, cassetta postale, indagine, grafico, prova
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: a6cdf55b33c91a33675bb4909c0cb08e8561d212
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846749"
---
# <a name="investigate-incidents-in-microsoft-365-defender"></a>Esaminare gli incidenti in Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**

- Microsoft 365 Defender

Microsoft 365 Defender aggrega tutti gli avvisi, le risorse, le indagini e le evidenze correlate da tutti i dispositivi, gli utenti e le cassette postali per fornire una panoramica completa dell'intera gamma di un attacco.

Analizzare gli avvisi che riguardano la rete, comprenderne il significato e raccogliere le prove associate agli incidenti consente di poter elaborare un piano di correzione efficace.

## <a name="investigate-an-incident"></a>Analizzare un incidente

1. Selezionare un incidente dalla relativa coda. <BR> Viene visualizzata una finestra laterale che fornisce un'anteprima di informazioni importanti quali stato, gravità, categorie e entità interessate.

    ![Immagine del riquadro laterale dell'incidente](../../media/incident-side-panel.png)

2. Selezionare **Apri pagina dell'incidente**. <BR> Verrà aperta la pagina degli incidenti in cui sono disponibili ulteriori informazioni sugli incidenti, i commenti e le azioni, le schede (panoramica, avvisi, dispositivi, utenti, indagini, prove).

3. Esaminare gli avvisi, i dispositivi, gli utenti e altre entità coinvolte nell'incidente.

## <a name="incident-overview"></a>Panoramica dell'incidente

La pagina di panoramica offre un quadro generale sugli elementi principali relativi all'incidente a cui prestare attenzione.

![Immagine della pagina di panoramica degli incidenti](../../media/incidents-overview.png)

Le categorie di attacco forniscono una visualizzazione visiva e numerica di come è progredito l'attacco avanzato rispetto alla catena di Kill. Come per altri prodotti Microsoft per la sicurezza, Microsoft 365 Defender è allineato al quadro di taglio [&CK &trade; ](https://attack.mitre.org/) .

La sezione relativa all'ambito fornisce un elenco delle principali risorse interessate che fanno parte di questo incidente. Se sono presenti informazioni specifiche su una determinata risorsa (ad esempio, il livello di rischio, la priorità dell'indagine e i contrassegni sulle attività) saranno disponibili in questa sezione.

La sequenza temporale degli avvisi permette di visualizzare un'anteprima dell'ordine cronologico in cui si sono verificati gli avvisi, nonché i motivi per cui tali avvisi sono collegati a questo incidente.

Infine, la sezione delle prove fornisce un riepilogo di quanti artefatti diversi sono stati inclusi nell'incidente e il relativo stato di correzione, in modo da poter identificare immediatamente se sono necessarie azioni da parte dell'utente.

Questa panoramica può essere utile nella valutazione iniziale dell'incidente fornendo dati analitici relativi alle principali caratteristiche dell'incidente di cui l'utente dovrebbe essere a conoscenza.

## <a name="alerts"></a>Avvisi

È possibile visualizzare tutti gli avvisi relativi all'incidente e altre informazioni su di esse, ad esempio la gravità, le entità che sono state coinvolte nell'avviso, l'origine degli avvisi (Microsoft Defender for Identity, Microsoft Defender for endpoint, Microsoft Defender per Office 365) e il motivo per cui sono stati collegati tra loro.

![Immagine della pagina degli avvisi dell'incidente](../../media/incident-alerts.png)

Per impostazione predefinita, gli avvisi sono ordinati cronologicamente, per consentire di visualizzare prima come si è svolto l'attacco nel tempo. Se si fa clic su ogni avviso, viene configurata la pagina di avviso pertinente, in cui è possibile eseguire un'analisi approfondita di tale avviso.

## <a name="devices"></a>Dispositivi

Nella scheda dei dispositivi sono elencati tutti i dispositivi in cui vengono visualizzati gli avvisi relativi all'incidente.

Facendo clic sul nome del computer in cui si è verificato l'attacco, si accede alla relativa pagina in cui è possibile visualizzare gli avvisi che sono stati attivati e gli eventi correlati forniti per facilitare l'indagine.

![Immagine della scheda dei computer di un incidente](../../media/incident-machines.png)

Selezionando la scheda della sequenza temporale è possibile scorrere la sequenza temporale del computer e visualizzare tutti gli eventi e i comportamenti osservati sul computer in ordine cronologico, intervallati dagli avvisi generati.

## <a name="users"></a>Utenti

Visualizzare gli utenti che sono stati identificati come parte di un determinato incidente, oppure relativi a esso.

Facendo clic sul nome utente si accede alla pagina di Cloud App Security dell'utente dove è possibile condurre ulteriori indagini.

![Immagine della scheda degli utenti di un incidente](../../media/incident-users.png)

## <a name="mailboxes"></a>Cassette postali

Analizzare tutte le cassette postali che sono state identificate come parte di un relativo incidente, oppure relative a esso. Per ulteriori operazioni di indagine, la selezione dell'avviso relativo alla posta elettronica aprirà Microsoft Defender per Office 365, dove è possibile eseguire operazioni di correzione.

![Immagine della scheda delle cassette postali di un incidente](../../media/incident-mailboxes.png)

## <a name="investigations"></a>Indagini

Selezionare **indagini** per visualizzare tutte le indagini automatizzate attivate dagli avvisi in questo incidente. Le indagini eseguono azioni di correzione o attendono l'approvazione dell'analista delle azioni, a seconda di come sono state configurate le indagini automatizzate per l'esecuzione in Microsoft Defender per endpoint e Defender per Office 365.

![Immagine della scheda delle indagini di un incidente](../../media/incident-investigations.png)

Selezionare un'indagine per accedere alla pagina dei dettagli dell'indagine per ottenere informazioni complete sull'indagine e sullo stato della correzione. Se nell'ambito dell'inchiesta sono presenti azioni in sospeso per l'approvazione, queste verranno visualizzate nella scheda azioni in sospeso. Eseguire un'azione nell'ambito della correzione degli incidenti.

## <a name="evidence"></a>Prove

Microsoft 365 Defender analizza automaticamente tutti gli eventi e le entità sospette degli incidenti supportati negli avvisi, fornendo risposta automatica e informazioni sui file importanti, i processi, i servizi, i messaggi di posta elettronica e altro ancora. Ciò consente di rilevare e bloccare rapidamente le potenziali minacce nell'incidente.

![Immagine della scheda delle prove di un incidente](../../media/incident-evidence.png)

Ognuna delle entità analizzate sarà contrassegnata con un verdetto (Dannosa, Sospetta, Pulita) e uno stato di correzione. Ciò consente di comprendere lo stato di correzione dell'intero incidente e quali sono i prossimi passi che possono essere presi per porre ulteriore rimedio.

## <a name="related-topics"></a>Argomenti correlati

- [Panoramica sugli incidenti](incidents-overview.md)
- [Assegnare priorità agli incidenti](incident-queue.md)
- [Gestire gli incidenti](manage-incidents.md)

