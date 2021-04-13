---
title: Risolvere i problemi di licenza per Microsoft Defender ATP per Mac
description: Risolvere i problemi relativi alle licenze in Microsoft Defender ATP per Mac.
keywords: microsoft, defender, atp, mac, prestazioni
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 69dd85394837bb7f37e7d277110c8a5dbf7b6506
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689114"
---
# <a name="troubleshoot-license-issues-for-microsoft-defender-for-endpoint-on-macos"></a>Risolvere i problemi di licenza per Microsoft Defender per Endpoint in macOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**

- [Microsoft Defender per Endpoint in macOS](microsoft-defender-endpoint-mac.md)
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Durante l'esecuzione di Microsoft Defender for [](mac-install-manually.md) Endpoint su [macOS](microsoft-defender-endpoint-mac.md) e test di distribuzione manuale o di un modello di prova (PoC), è possibile che venga visualizzato l'errore seguente:

![Immagine dell'errore di licenza](images/no-license-found.png)

**Messaggio:** 

Nessuna licenza trovata

Sembra che l'organizzazione non abbia una licenza per l'abbonamento a Microsoft 365 Enterprise.

Contattare l'amministratore per assistenza.

**Causa:** 

Hai distribuito e/o installato il pacchetto Microsoft Defender for Endpoint su macOS ("Scarica pacchetto di installazione") ma potresti aver eseguito lo script di configurazione ("Scarica pacchetto di onboarding").

**Soluzione:**

Seguire le MicrosoftDefenderATPOnboardingMacOs.py seguenti: Configurazione [client](mac-install-manually.md#client-configuration)

