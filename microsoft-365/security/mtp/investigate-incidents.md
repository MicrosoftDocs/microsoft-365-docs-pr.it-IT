---
title: Analizzare gli eventi imprevisti in Microsoft 365 Defender
description: Analizzare gli incidenti relativi a dispositivi, utenti e cassette postali.
keywords: incidente, incidenti, computer, dispositivi, utenti, identificare, posta, posta elettronica, cassetta postale, indagine, grafico, prova
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 6a3bd6be81b4ea4ef11a366267d7a36d45e622b9
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926895"
---
# <a name="investigate-incidents-in-microsoft-365-defender"></a>Analizzare gli eventi imprevisti in Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**

- Microsoft 365 Defender

Microsoft 365 Defender aggrega tutti gli avvisi, le risorse, le indagini e le prove correlati provenienti da dispositivi, utenti e cassette postali per fornire un quadro completo dell'intera gamma di attacchi.

Analizzare gli avvisi che riguardano la rete, comprenderne il significato e raccogliere le prove associate agli incidenti consente di poter elaborare un piano di correzione efficace.

## <a name="investigate-an-incident"></a>Analizzare un incidente

1. Selezionare un incidente dalla relativa coda. <BR> Si apre un pannello laterale che offre un'anteprima delle informazioni importanti, ad esempio stato, gravità, categorie ed entità influenzate.

    ![Immagine del riquadro laterale dell'incidente](../../media/incident-side-panel.png)

2. Selezionare **Apri pagina dell'incidente**. <BR> Verrà aperta la pagina dell'evento imprevisto in cui sono disponibili ulteriori informazioni su eventi imprevisti, commenti e azioni, schede (panoramica, avvisi, dispositivi, utenti, indagini, prove).

3. Esaminare gli avvisi, i dispositivi, gli utenti e altre entità coinvolte nell'incidente.

## <a name="incident-overview"></a>Panoramica dell'incidente

La pagina di panoramica offre un quadro generale sugli elementi principali relativi all'incidente a cui prestare attenzione.

![Immagine della pagina di panoramica degli incidenti](../../media/incidents-overview.png)

Le categorie di attacco offrono una visualizzazione visiva e numerica dell'avanzamento dell'attacco rispetto alla kill chain. Come per altri prodotti di sicurezza Microsoft, Microsoft 365 Defender è allineato al framework [MITRE ATT&&trade; CK.](https://attack.mitre.org/)

La sezione relativa all'ambito fornisce un elenco delle principali risorse interessate che fanno parte di questo incidente. Se sono presenti informazioni specifiche su una determinata risorsa (ad esempio, il livello di rischio, la priorità dell'indagine e i contrassegni sulle attività) saranno disponibili in questa sezione.

La sequenza temporale degli avvisi permette di visualizzare un'anteprima dell'ordine cronologico in cui si sono verificati gli avvisi, nonché i motivi per cui tali avvisi sono collegati a questo incidente.

Infine, la sezione delle prove fornisce un riepilogo di quanti artefatti diversi sono stati inclusi nell'incidente e il relativo stato di correzione, in modo da poter identificare immediatamente se sono necessarie azioni da parte dell'utente.

Questa panoramica può essere utile nella valutazione iniziale dell'incidente fornendo dati analitici relativi alle principali caratteristiche dell'incidente di cui l'utente dovrebbe essere a conoscenza.

## <a name="alerts"></a>Avvisi

È possibile visualizzare tutti gli avvisi correlati all'evento imprevisto e altre informazioni su di essi, ad esempio la gravità, le entità coinvolte nell'avviso, l'origine degli avvisi (Microsoft Defender for Identity, Microsoft Defender for Endpoint, Microsoft Defender per Office 365) e il motivo per cui sono stati collegati tra loro.

![Immagine della pagina degli avvisi dell'incidente](../../media/incident-alerts.png)

Per impostazione predefinita, gli avvisi sono ordinati cronologicamente, per consentire di visualizzare prima come si è svolto l'attacco nel tempo. Facendo clic su ogni avviso verrà visualizzata la pagina di avviso pertinente in cui è possibile eseguire un'analisi approfondita dell'avviso.

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

Analizzare tutte le cassette postali che sono state identificate come parte di un relativo incidente, oppure relative a esso. Per eseguire ulteriori attività di indagine, selezionando l'avviso correlato alla posta elettronica si aprirà Microsoft Defender per Office 365 in cui è possibile eseguire azioni correttive.

![Immagine della scheda delle cassette postali di un incidente](../../media/incident-mailboxes.png)

## <a name="investigations"></a>Indagini

Selezionare **Indagini per** visualizzare tutte le indagini automatizzate attivate dagli avvisi in questo incidente. Le indagini eseguiranno azioni correttive o attenderanno l'approvazione da parte dell'analista delle azioni, a seconda di come sono configurate le indagini automatizzate per l'esecuzione in Microsoft Defender per Endpoint e Defender per Office 365.

![Immagine della scheda delle indagini di un incidente](../../media/incident-investigations.png)

Selezionare un'indagine per accedere alla pagina dei dettagli dell'indagine per ottenere informazioni complete sull'indagine e sullo stato della correzione. Se sono presenti azioni in sospeso per l'approvazione nell'ambito dell'indagine, verranno visualizzate nella scheda Azioni in sospeso. Eseguire un'azione nell'ambito della correzione degli eventi imprevisti.

## <a name="evidence"></a>Prove

Microsoft 365 Defender analizza automaticamente tutti gli eventi supportati e le entità sospette degli eventi imprevisti negli avvisi, fornendo una risposta automatica e informazioni su file, processi, servizi, messaggi di posta elettronica e altro ancora importanti. Ciò consente di rilevare e bloccare rapidamente le potenziali minacce nell'incidente.

![Immagine della scheda delle prove di un incidente](../../media/incident-evidence.png)

Ognuna delle entità analizzate sarà contrassegnata con un verdetto (Dannosa, Sospetta, Pulita) e uno stato di correzione. Ciò consente di comprendere lo stato di correzione dell'intero incidente e quali sono i prossimi passi che possono essere presi per porre ulteriore rimedio.

## <a name="related-topics"></a>Argomenti correlati

- [Panoramica sugli incidenti](incidents-overview.md)
- [Assegnare priorità agli incidenti](incident-queue.md)
- [Gestire gli incidenti](manage-incidents.md)

