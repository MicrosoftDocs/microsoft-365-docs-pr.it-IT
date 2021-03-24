---
title: Analizzare i domini di Microsoft Defender per endpoint
description: Usa le opzioni di indagine per verificare se i dispositivi e i server comunicano con domini dannosi.
keywords: analizzare dominio, dominio, dominio dannoso, microsoft defender atp, avviso, URL
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: b2e858a7533c17bc5c425ec1de73a45eaf5b6b31
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51065738"
---
# <a name="investigate-a-domain-associated-with-a-microsoft-defender-for-endpoint-alert"></a>Analizzare un dominio associato a un avviso di Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**
- [Microsoft Defender ATP](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatedomain-abovefoldlink) 

Analizzare un dominio per verificare se i dispositivi e i server della rete aziendale comunicano con un dominio dannoso noto.

Puoi analizzare un dominio usando la funzionalità di ricerca o facendo clic su un collegamento di dominio dalla **sequenza temporale del dispositivo.**

È possibile visualizzare le informazioni delle sezioni seguenti nella visualizzazione URL:

- Dettagli URL, Contatti, Server dei nomi
- Avvisi correlati a questo URL 
- URL nell'organizzazione
- Dispositivi osservati più recenti con URL

## <a name="url-worldwide"></a>URL in tutto il mondo

Nella **sezione URL in** tutto il mondo sono elencati l'URL, un collegamento a ulteriori dettagli su Whois, il numero di eventi imprevisti aperti correlati e il numero di avvisi attivi.

## <a name="incident"></a>Incidente

La **scheda Evento** imprevisto visualizza un grafico a barre di tutti gli avvisi attivi negli eventi imprevisti degli ultimi 180 giorni.

## <a name="prevalence"></a>Prevalenza

La **scheda Prevalenza** fornisce dettagli sulla diffusione dell'URL all'interno dell'organizzazione in un periodo di tempo specificato.

Anche se il periodo di tempo predefinito è degli ultimi 30 giorni, è possibile personalizzare l'intervallo selezionando la freccia rivolta verso il basso nell'angolo della scheda. L'intervallo più breve disponibile è per la diffusione nell'ultimo giorno, mentre l'intervallo più lungo è negli ultimi 6 mesi.

## <a name="alerts"></a>Avvisi

Nella **scheda Avvisi** è disponibile un elenco di avvisi associati all'URL. La tabella riportata di seguito è una versione filtrata degli avvisi visibili nella schermata Della coda degli avvisi, che mostra solo gli avvisi associati al dominio, la gravità, lo stato, l'evento imprevisto associato, la classificazione, lo stato dell'indagine e altro ancora.

La scheda Avvisi può essere modificata in modo da visualizzare più o meno informazioni selezionando **Personalizza** colonne dal menu delle azioni sopra le intestazioni di colonna. È inoltre possibile modificare il numero di elementi visualizzati selezionando gli elementi **per pagina** nello stesso menu.

## <a name="observed-in-organization"></a>Osservato nell'organizzazione

La **scheda Osservati nell'organizzazione** fornisce una visualizzazione cronologica degli eventi e degli avvisi associati osservati nell'URL. Questa scheda include una sequenza temporale e una tabella personalizzabile che elenca i dettagli dell'evento, ad esempio l'ora, il dispositivo e una breve descrizione dell'evento. 

È possibile visualizzare gli eventi di diversi periodi di tempo immettendo le date nei campi di testo sopra le intestazioni della tabella. Puoi anche personalizzare l'intervallo di tempo selezionando diverse aree della sequenza temporale.

**Analizzare un dominio:**

1. Seleziona **URL** dal menu **a** discesa della barra di ricerca.
2. Immettere l'URL nel **campo** Di ricerca.
3. Fare clic sull'icona di ricerca o premere **INVIO.** Vengono visualizzati i dettagli sull'URL. Nota: i risultati della ricerca verranno restituiti solo per gli URL osservati nelle comunicazioni dai dispositivi dell'organizzazione.
4. Utilizzare i filtri di ricerca per definire i criteri di ricerca. Puoi anche usare la casella di ricerca della sequenza temporale per filtrare i risultati visualizzati di tutti i dispositivi nell'organizzazione osservati comunicando con l'URL, il file associato alla comunicazione e l'ultima data osservata.
5. Se fai clic su uno dei nomi dei dispositivi, potrai passare alla visualizzazione del dispositivo, in cui puoi continuare ad analizzare gli avvisi, i comportamenti e gli eventi segnalati.

## <a name="related-topics"></a>Argomenti correlati
- [Visualizzare e organizzare la coda di Microsoft Defender for Endpoint Alerts](alerts-queue.md)
- [Gestire gli avvisi di Microsoft Defender for Endpoint](manage-alerts.md)
- [Analizzare gli avvisi di Microsoft Defender for Endpoint](investigate-alerts.md)
- [Analizzare un file associato a un avviso di Microsoft Defender for Endpoint](investigate-files.md)
- [Analizzare i dispositivi nell'elenco Di Microsoft Defender per dispositivi endpoint](investigate-machines.md)
- [Analizzare un indirizzo IP associato a un avviso di Microsoft Defender for Endpoint](investigate-ip.md)
- [Analizzare un account utente in Microsoft Defender for Endpoint](investigate-user.md)
