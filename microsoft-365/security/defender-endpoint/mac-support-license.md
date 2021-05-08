---
title: Risolvere i problemi di licenza per Microsoft Defender per Endpoint su Mac
description: Risolvere i problemi relativi alle licenze in Microsoft Defender per Endpoint su Mac.
keywords: microsoft, defender, Microsoft Defender for Endpoint, mac, prestazioni
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
ms.openlocfilehash: 1f8428c2995eec2dece290049eda67a3683b4c1e
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244981"
---
# <a name="troubleshoot-license-issues-for-microsoft-defender-for-endpoint-on-macos"></a>Risolvere i problemi di licenza per Microsoft Defender per Endpoint in macOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**

- [Microsoft Defender per endpoint su macOS](microsoft-defender-endpoint-mac.md)
- [Microsoft Defender ATP](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Durante l'esecuzione di Microsoft Defender for [](mac-install-manually.md) Endpoint su [macOS](microsoft-defender-endpoint-mac.md) e test di distribuzione manuale o di un modello di prova (PoC), è possibile che venga visualizzato l'errore seguente:

![Immagine dell'errore di licenza](images/no-license-found.png)

**Messaggio:** 

Nessuna licenza trovata

Sembra che l'organizzazione non abbia una licenza per Microsoft 365 Enterprise abbonamento.

Contattare l'amministratore per assistenza.

**Causa:** 

Hai distribuito e/o installato il pacchetto Microsoft Defender for Endpoint per macOS ("Scarica pacchetto di installazione"), ma potresti aver eseguito lo script di configurazione ("Scarica pacchetto di onboarding" oppure non hai assegnato una licenza all'utente.

**Soluzione:**

Seguire le MicrosoftDefenderATPOnboardingMacOs.py seguenti: Configurazione [client](mac-install-manually.md#client-configuration)
