---
title: Proteggere i dati dell'organizzazione con il controllo del dispositivo
description: Monitorare la sicurezza dei dati dell'organizzazione tramite i report di controllo dei dispositivi.
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
ms.author: deniseb
author: denisebmsft
ms.reviewer: dansimp
ms.topic: article
manager: dansimp
audience: ITPro
ms.technology: mde
ms.openlocfilehash: 47eb80af58c948db5997dc9f5edfa5737a796837
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2021
ms.locfileid: "52772366"
---
# <a name="protect-your-organizations-data-with-device-control"></a>Proteggere i dati dell'organizzazione con il controllo del dispositivo

**Si applica a:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2069559)

Il controllo dei dispositivi Microsoft Defender for Endpoint protegge dalla perdita di dati, monitorando e controllando l'uso dei supporti da parte dei dispositivi dell'organizzazione, ad esempio l'uso di dispositivi di archiviazione rimovibili e unità USB.

Con il report di controllo del dispositivo puoi visualizzare gli eventi correlati all'utilizzo dei supporti, ad esempio:

- **Eventi di controllo:** Indica il numero di eventi di controllo che si verificano quando è connesso un supporto esterno.
- **Eventi dei criteri:** Mostra il numero di eventi dei criteri che si verificano quando viene attivato un criterio di controllo del dispositivo.

> [!NOTE]
> L'evento di controllo per tenere traccia dell'utilizzo dei contenuti multimediali è abilitato per impostazione predefinita per i dispositivi onboarded in Microsoft Defender per Endpoint.

## <a name="understanding-the-audit-events"></a>Informazioni sugli eventi di controllo

Gli eventi di controllo includono:

- **Montaggio e smontare unità USB:** Eventi di controllo generati quando un'unità USB viene montata o disinstallata.
- **PnP:** Gli eventi di controllo Plug and Play vengono generati quando viene connessa un'archiviazione rimovibile, una stampante o Bluetooth supporto.

## <a name="monitor-device-control-security"></a>Monitorare la sicurezza del controllo dei dispositivi

Il controllo dei dispositivi in Microsoft Defender for Endpoint offre agli amministratori della sicurezza strumenti che consentono loro di tenere traccia della sicurezza del controllo dei dispositivi dell'organizzazione tramite i report. Puoi trovare il report di controllo del dispositivo nel centro sicurezza Microsoft 365 sicurezza andando a **Report > Protezione del dispositivo**.

La scheda Protezione dispositivo nel dashboard **Report** mostra il numero di eventi di controllo generati dal tipo di supporto negli ultimi 180 giorni.

> [!div class="mx-imgBorder"]
> ![DeviceControlReportCard](images/devicecontrolcard.png)

Il **pulsante Visualizza dettagli** mostra più dati di utilizzo multimediale nella pagina del report del controllo **dispositivo.**

La pagina fornisce un dashboard con un numero aggregato di eventi per tipo e un elenco di eventi. Gli amministratori possono filtrare l'intervallo di tempo, il nome della classe multimediale e l'ID dispositivo.

> [!div class="mx-imgBorder"]
> ![DeviceControlReportDetails](images/Detaileddevicecontrolreport.png)

Quando si seleziona un evento, viene visualizzato un riquadro a comparsa che mostra ulteriori informazioni:

- **Dettagli generali:** Data, modalità azione e i criteri di questo evento.
- **Informazioni multimediali:** Le informazioni multimediali includono Nome supporto, Nome classe, GUID classe, ID dispositivo, ID fornitore, Volume, Numero di serie e Tipo di bus.
- **Dettagli percorso:** Nome del dispositivo e MDATP dispositivo.

> [!div class="mx-imgBorder"]
> ![FilterOnDeviceControlReport](images/devicecontrolreportfilter.png)

Per visualizzare le attività in tempo reale per questi elementi multimediali nell'organizzazione, selezionare il **pulsante Apri ricerca** avanzata. Include una query incorporata predefinita.

> [!div class="mx-imgBorder"]
> ![QueryOnDeviceControlReport](images/Devicecontrolreportquery.png)

Per visualizzare la sicurezza del dispositivo, seleziona il **pulsante Apri** pagina dispositivo nel riquadro a comparsa. Questo pulsante apre la pagina dell'entità dispositivo.

> [!div class="mx-imgBorder"]
> ![DeviceEntityPage](images/Devicesecuritypage.png)

## <a name="reporting-delays"></a>Segnalazione di ritardi

Il report di controllo del dispositivo può avere un ritardo di 12 ore dal momento in cui si verifica una connessione multimediale al momento in cui l'evento si riflette nella scheda o nell'elenco dei domini.
