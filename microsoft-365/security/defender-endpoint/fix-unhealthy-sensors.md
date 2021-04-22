---
title: Risolvere i sensori non integri in Microsoft Defender for Endpoint
description: Correggere i sensori del dispositivo che segnalano come non configurati correttamente o inattivi in modo che il servizio riceva i dati dal dispositivo.
keywords: non configurato correttamente, inattivo, correggere il sensore, l'integrità del sensore, nessun dato del sensore, dati del sensore, comunicazioni compromesse, comunicazione
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
ms.date: 11/06/2020
ms.technology: mde
ms.openlocfilehash: c4cdc80170b49a111f476d2d17222c41e2b5c55f
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935366"
---
# <a name="fix-unhealthy-sensors-in-microsoft-defender-for-endpoint"></a>Risolvere i sensori non integri in Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

- Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-fixsensor-abovefoldlink)

I dispositivi classificati come non configurati correttamente o inattivi possono essere contrassegnati a causa di cause diverse. Questa sezione fornisce alcune spiegazioni su cosa potrebbe aver causato la categorizzazione di un dispositivo come inattivo o non configurato correttamente.

## <a name="inactive-devices"></a>Dispositivi inattivi

Un dispositivo inattivo non è necessariamente contrassegnato a causa di un problema. Le azioni seguenti eseguite su un dispositivo possono causare la categorizzazione di un dispositivo come inattivo:

### <a name="device-is-not-in-use"></a>Il dispositivo non è in uso

Se il dispositivo non è in uso da più di sette giorni per qualsiasi motivo, rimarrà nello stato "Inattivo" nel portale.

### <a name="device-was-reinstalled-or-renamed"></a>Il dispositivo è stato reinstallato o rinominato
Un dispositivo reinstallato o rinominato genererà una nuova entità dispositivo in Microsoft Defender Security Center. L'entità dispositivo precedente rimarrà con stato "Inattivo" nel portale. Se hai reinstallato un dispositivo e distribuito il pacchetto Defender for Endpoint, cerca il nuovo nome del dispositivo per verificare che il dispositivo segnala normalmente.

### <a name="device-was-offboarded"></a>Il dispositivo è stato offboarded
Se il dispositivo è stato offboarded, verrà comunque visualizzato nell'elenco dei dispositivi. Dopo sette giorni, lo stato di integrità del dispositivo deve essere inattivo.

### <a name="device-is-not-sending-signals"></a>Il dispositivo non invia segnali
Se il dispositivo non invia alcun segnale per più di sette giorni a uno qualsiasi dei canali di Microsoft Defender for Endpoint per qualsiasi motivo, incluse le condizioni che rientrano nella classificazione dei dispositivi non configurati correttamente, un dispositivo può essere considerato inattivo. 

Si prevede che un dispositivo sia in stato "Attivo"? [Aprire un ticket di supporto](https://support.microsoft.com/getsupport?wf=0&tenant=ClassicCommercial&oaspworkflow=start_1.0.0.0&locale=en-us&supportregion=en-us&pesid=16055&ccsid=636206786382823561).

## <a name="misconfigured-devices"></a>Dispositivi non configurati correttamente
I dispositivi non configurati correttamente possono essere ulteriormente classificati in:
- Comunicazioni con problemi
- Nessun dato sensore

### <a name="impaired-communications"></a>Comunicazioni con problemi
Questo stato indica che la comunicazione tra il dispositivo e il servizio è limitata.

Le azioni suggerite seguenti possono aiutare a risolvere i problemi relativi a un dispositivo non configurato correttamente con comunicazioni con problemi di comunicazione:

- [Verificare che il dispositivo abbia una connessione Internet](troubleshoot-onboarding.md#troubleshoot-onboarding-issues-on-the-device)</br>
  Il sensore Microsoft Defender per endpoint richiede che Microsoft Windows HTTP (WinHTTP) segnali dati dei sensori e comunichi con il servizio Microsoft Defender per endpoint.

- [Verificare la connettività client a Microsoft Defender per gli URL del servizio endpoint](configure-proxy-internet.md#verify-client-connectivity-to-microsoft-defender-for-endpoint-service-urls)</br>
  Verificare che la configurazione del proxy sia stata completata correttamente, che WinHTTP sia in grado di individuare e comunicare tramite il server proxy nell'ambiente e che il server proxy consenta il traffico verso gli URL del servizio Microsoft Defender for Endpoint.

Se hai intrapreso azioni correttive e lo stato del dispositivo non è ancora configurato correttamente, [apri un ticket di supporto.](https://go.microsoft.com/fwlink/?LinkID=761093&clcid=0x409)

### <a name="no-sensor-data"></a>Nessun dato sensore
Un dispositivo non configurato correttamente con stato "Nessun dato sensore" è in grado di comunicare con il servizio, ma può segnalare solo dati parziali del sensore.
Seguire queste azioni per correggere i problemi noti relativi a un dispositivo non configurato correttamente con stato "Nessun dato sensore":

- [Verificare che il dispositivo abbia una connessione Internet](troubleshoot-onboarding.md#troubleshoot-onboarding-issues-on-the-device)</br>
  Il sensore Microsoft Defender per endpoint richiede che Microsoft Windows HTTP (WinHTTP) segnali dati dei sensori e comunichi con il servizio Microsoft Defender per endpoint.

- [Verificare la connettività client a Microsoft Defender per gli URL del servizio endpoint](configure-proxy-internet.md#verify-client-connectivity-to-microsoft-defender-for-endpoint-service-urls)</br>
  Verificare che la configurazione del proxy sia stata completata correttamente, che WinHTTP sia in grado di individuare e comunicare tramite il server proxy nell'ambiente e che il server proxy consenta il traffico verso gli URL del servizio Microsoft Defender for Endpoint.

- [Verificare che il servizio dati di diagnostica sia abilitato](troubleshoot-onboarding.md#ensure-the-diagnostics-service-is-enabled)</br>
Se i dispositivi non segnalano correttamente, potrebbe essere necessario verificare che il servizio dati di diagnostica di Windows 10 sia impostato per l'avvio automatico e sia in esecuzione nell'endpoint.

- [Verificare che Microsoft Defender Antivirus non sia disabilitato dai criteri](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)</br>
Se i dispositivi eseguono un client antimalware di terze parti, l'agente Defender for Endpoint deve essere abilitato il driver Antimalware antimalware (Early Launch Antimalware) di Microsoft Defender Antivirus.

Se hai intrapreso azioni correttive e lo stato del dispositivo non è ancora configurato correttamente, [apri un ticket di supporto.](https://go.microsoft.com/fwlink/?LinkID=761093&clcid=0x409)

## <a name="see-also"></a>Vedere anche
- [Controllare lo stato di integrità del sensore in Microsoft Defender per Endpoint](check-sensor-status.md)
