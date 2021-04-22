---
title: Analizzare un indirizzo IP associato a un avviso
description: Usa le opzioni di indagine per esaminare le possibili comunicazioni tra dispositivi e indirizzi IP esterni.
keywords: analizzare, analizzare, indirizzo IP, avviso, Microsoft Defender for Endpoint, IP esterno
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
ms.openlocfilehash: cb95deb890b52f0f5fde26a3a193181713b8ae5f
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933830"
---
# <a name="investigate-an-ip-address-associated-with-a-microsoft-defender-for-endpoint-alert"></a>Analizzare un indirizzo IP associato a un avviso di Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

Esaminare le possibili comunicazioni tra i dispositivi e gli indirizzi IP (Internet Protocol) esterni.

L'identificazione di tutti i dispositivi dell'organizzazione che comunicano con un indirizzo IP sospetto o noto dannoso, come i server Command and Control (C2), consente di determinare l'ambito potenziale di violazione, i file associati e i dispositivi infetti.

È possibile trovare informazioni dalle sezioni seguenti nella visualizzazione degli indirizzi IP:

- IP in tutto il mondo
- Nomi DNS inversa
- Avvisi correlati a questo indirizzo IP
- IP nell'organizzazione
- Prevalenza

## <a name="ip-worldwide-and-reverse-dns-names"></a>Ip Worldwide e Reverse DNS names

La sezione Dettagli indirizzo IP mostra gli attributi dell'indirizzo IP, ad esempio il relativo ASN e i relativi nomi DNS inversa.

## <a name="alerts-related-to-this-ip"></a>Avvisi correlati a questo indirizzo IP

La **sezione Avvisi correlati a questo ip** fornisce un elenco di avvisi associati all'IP.

## <a name="ip-in-organization"></a>IP nell'organizzazione

La **sezione IP nell'organizzazione** fornisce informazioni dettagliate sulla diffusione dell'indirizzo IP nell'organizzazione.

## <a name="prevalence"></a>Prevalenza

La **sezione Prevalenza** mostra quanti dispositivi si sono connessi a questo indirizzo IP e quando l'IP è stato visualizzato per la prima volta e l'ultima volta. È possibile filtrare i risultati di questa sezione in base al periodo di tempo. il periodo predefinito è 30 giorni.

## <a name="most-recent-observed-devices-with-ip"></a>Dispositivi osservati più recenti con IP

La **sezione Dispositivi osservati più recenti** con IP fornisce una visualizzazione cronologica degli eventi e degli avvisi associati che sono stati osservati nell'indirizzo IP.

**Analizzare un IP esterno:**

1. Selezionare **IP** dal menu **a** discesa barra di ricerca.
2. Immettere l'indirizzo IP nel **campo** Cerca.
3. Fare clic sull'icona di ricerca o premere **INVIO.**

Vengono visualizzati i dettagli sull'indirizzo IP, tra cui: dettagli di registrazione (se disponibili), IP inversi (ad esempio, domini), prevalenza dei dispositivi nell'organizzazione che comunicavano con questo indirizzo IP (durante il periodo di tempo selezionabile) e i dispositivi dell'organizzazione che sono stati osservati comunicare con questo indirizzo IP.

> [!NOTE]
> I risultati della ricerca verranno restituiti solo per gli indirizzi IP osservati nelle comunicazioni con i dispositivi nell'organizzazione.

Utilizzare i filtri di ricerca per definire i criteri di ricerca. Puoi anche usare la casella di ricerca della sequenza temporale per filtrare i risultati visualizzati di tutti i dispositivi dell'organizzazione osservati in comunicazione con l'indirizzo IP, il file associato alla comunicazione e l'ultima data osservata.

Se fai clic su uno dei nomi dei dispositivi, potrai passare alla visualizzazione del dispositivo, in cui puoi continuare ad analizzare gli avvisi, i comportamenti e gli eventi segnalati.

## <a name="related-topics"></a>Argomenti correlati

- [Visualizzare e organizzare la coda di Microsoft Defender for Endpoint Alerts](alerts-queue.md)
- [Gestire gli avvisi di Microsoft Defender for Endpoint](manage-alerts.md)
- [Analizzare gli avvisi di Microsoft Defender for Endpoint](investigate-alerts.md)
- [Analizzare un file associato a un avviso di Microsoft Defender for Endpoint](investigate-files.md)
- [Analizzare i dispositivi nell'elenco Di Microsoft Defender per dispositivi endpoint](investigate-machines.md)
- [Analizzare un dominio associato a un avviso di Microsoft Defender for Endpoint](investigate-domain.md)
- [Analizzare un account utente in Microsoft Defender for Endpoint](investigate-user.md)
