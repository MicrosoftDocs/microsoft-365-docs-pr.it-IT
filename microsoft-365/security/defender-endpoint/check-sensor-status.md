---
title: Controllare lo stato di integrità del sensore in Microsoft Defender per Endpoint
description: Controlla l'integrità del sensore nei dispositivi per identificare quelli configurati in modo erre, inattivi o che non segnalano i dati del sensore.
keywords: sensore, integrità del sensore, configurazione errata, inattiva, nessun dato del sensore, dati del sensore, comunicazioni compromesse, comunicazione
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
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: 0361b7956339670d006c9f050274e07d4e979bca
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/20/2021
ms.locfileid: "51904165"
---
# <a name="check-sensor-health-state-in-microsoft-defender-for-endpoint"></a>Controllare lo stato di integrità del sensore in Microsoft Defender per Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-checksensor-abovefoldlink)

Il **riquadro Dispositivi con problemi del** sensore è disponibile nel dashboard Operazioni di sicurezza. Questo riquadro fornisce informazioni sulla capacità del singolo dispositivo di fornire dati sul sensore e comunicare con il servizio Defender per endpoint. Segnala quanti dispositivi richiedono attenzione e aiuta a identificare i dispositivi problematici per intraprendere le azioni volte a correggere i problemi noti.

Nel riquadro sono presenti due indicatori di stato che forniscono informazioni sul numero di dispositivi che non segnalano correttamente al servizio:
- **Configurazione errata: questi** dispositivi potrebbero segnalare parzialmente i dati del sensore al servizio Defender for Endpoint e potrebbero avere errori di configurazione che devono essere corretti.
- **Inattivo:** dispositivi che hanno interrotto la segnalazione al servizio Defender for Endpoint per più di sette giorni nell'ultimo mese.

Se fai clic su uno dei gruppi, viene visualizzato **l'elenco Dispositivi,** filtrato in base alla tua scelta.

![Screenshot del riquadro Dispositivi con problemi del sensore](images/atp-devices-with-sensor-issues-tile.png)

**Nell'elenco Dispositivi** è possibile filtrare l'elenco degli stati di integrità in base allo stato seguente:
- **Active** - Dispositivi che segnalano attivamente al servizio Defender for Endpoint.
- **Configurazione errata: questi** dispositivi potrebbero segnalare parzialmente i dati del sensore al servizio Defender for Endpoint, ma potrebbero avere errori di configurazione che devono essere corretti. Nei dispositivi non configurati correttamente possono verificarsi uno o più dei seguenti problemi:
  - **Nessun dato del sensore:** i dispositivi hanno smesso di inviare i dati del sensore. Il dispositivo può generare avvisi limitati.
  - **Comunicazioni con problemi** - La capacità di comunicare con il dispositivo è compromessa. L'invio di file per un'analisi approfondita, il blocco dei file, l'isolamento del dispositivo dalla rete e altre azioni che richiedono la comunicazione con il dispositivo potrebbero non funzionare.
- **Inattivo:** dispositivi che hanno interrotto la segnalazione al servizio Defender for Endpoint.

Puoi anche scaricare l'intero elenco in formato CSV usando la **funzionalità Esporta.** Per altre informazioni sui filtri, vedi [Visualizzare e organizzare l'elenco Dispositivi.](machines-view-overview.md)

>[!NOTE]
>Esportare l'elenco in formato CSV per visualizzare i dati non filtrati. Il file CSV includerà tutti i dispositivi dell'organizzazione, indipendentemente dai filtri applicati nella visualizzazione stessa e può richiedere molto tempo per il download, a seconda delle dimensioni dell'organizzazione.

![Screenshot della pagina elenco Dispositivi](images/atp-devices-list-page.png)

Puoi visualizzare i dettagli del dispositivo quando fai clic su un dispositivo non configurato correttamente o inattivo.

## <a name="related-topic"></a>Argomento correlato
- [Risolvere i sensori non integri in Defender for Endpoint](fix-unhealthy-sensors.md)
