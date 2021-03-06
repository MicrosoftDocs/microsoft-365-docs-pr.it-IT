---
title: Risolvere i problemi del servizio di Microsoft Defender per endpoint
description: Trovare soluzioni e soluzioni alternative a problemi noti, ad esempio errori del server quando si tenta di accedere al servizio.
keywords: risolvere i problemi di Microsoft Defender per Endpoint, errore del server, accesso negato, credenziali non valide, nessun dato, portale dashboard, consenti, visualizzatore eventi
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
ms.topic: troubleshooting
ms.technology: mde
ms.openlocfilehash: 8aaea65c617300a16f99a9a3e3a62d94b7983198
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538352"
---
# <a name="troubleshoot-service-issues"></a>Risolvere i problemi dei servizi

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


In questa sezione vengono risolti i problemi che possono verificarsi quando usi il servizio Microsoft Defender for Endpoint.

## <a name="server-error---access-is-denied-due-to-invalid-credentials"></a>Errore del server - Accesso negato a causa di credenziali non valide
Se si verifica un errore del server quando si tenta di accedere al servizio, è necessario modificare le impostazioni dei cookie del browser.
Configurare il browser per consentire i cookie.

## <a name="elements-or-data-missing-on-the-portal"></a>Elementi o dati mancanti nel portale
Se alcuni elementi o dati non sono presenti Microsoft Defender Security Center è possibile che le impostazioni proxy lo blocchino.

Assicurati che sia `*.securitycenter.windows.com` incluso l'elenco di proxy consentiti.


> [!NOTE]
> È necessario utilizzare il protocollo HTTPS quando si aggiungono gli endpoint seguenti.

## <a name="microsoft-defender-for-endpoint-service-shows-event-or-error-logs-in-the-event-viewer"></a>Il servizio Microsoft Defender for Endpoint mostra i registri eventi o di errore nel Visualizzatore eventi

Vedi Esaminare gli eventi e gli errori tramite il [Visualizzatore](event-error-codes.md) eventi per un elenco degli ID evento segnalati dal servizio Microsoft Defender per endpoint. L'articolo contiene anche i passaggi per la risoluzione dei problemi relativi agli errori degli eventi.

## <a name="microsoft-defender-for-endpoint-service-fails-to-start-after-a-reboot-and-shows-error-577"></a>Microsoft Defender for Endpoint service fails to start after a reboot and shows error 577

Se l'onboarding dei dispositivi viene completato correttamente ma Microsoft Defender for Endpoint non viene avviato dopo un riavvio e viene visualizzato l'errore 577, verificare che Windows Defender non sia disabilitato da un criterio.

Per ulteriori informazioni, vedere [Ensure that Antivirus Microsoft Defender is not disabled by policy](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy).

## <a name="known-issues-with-regional-formats"></a>Problemi noti con i formati regionali

**Formati di data e ora**<br>
Esistono alcuni problemi noti relativi ai formati di data e ora. 

Sono supportati i formati di data seguenti:
- MM/gg/aaaa
- gg/MM/aaaa

I formati di data e ora seguenti non sono attualmente supportati:
- Formato data aaaa/MM/gg
- Formato data gg/MM/aa
- Formato data con yy. Mostrerà solo aaaa.
- Formato ora HH:mm:ss non supportato (il formato AM/PM di 12 ore non è supportato). È supportato solo il formato 24 ore.

**Uso della virgola per indicare le migliaia**<br>
Il supporto dell'utilizzo della virgola come separatore nei numeri non è supportato. Le aree in cui un numero è separato da una virgola per indicare mille, potranno vedere solo l'uso di un punto come separatore. Ad esempio, 15,5K viene visualizzato come 15,5K.

>Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-troubleshoot-belowfoldlink)

## <a name="microsoft-defender-for-endpoint-tenant-was-automatically-created-in-europe"></a>Il tenant di Microsoft Defender for Endpoint è stato creato automaticamente in Europa
Quando si usa Azure Defender per monitorare i server, viene creato automaticamente un tenant di Microsoft Defender for Endpoint. I dati di Microsoft Defender for Endpoint sono archiviati in Europa per impostazione predefinita.





## <a name="related-topics"></a>Argomenti correlati
- [Risolvere i problemi di onboarding di Microsoft Defender per endpoint](troubleshoot-onboarding.md)
- [Esaminare eventi ed errori tramite il Visualizzatore eventi](event-error-codes.md)
