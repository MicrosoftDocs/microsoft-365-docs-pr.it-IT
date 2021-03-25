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
ms.openlocfilehash: 44105ae8d1872c3ecefcf84a5e2efef122849b8c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51066429"
---
# <a name="troubleshoot-license-issues-for-microsoft-defender-for-endpoint-for-mac"></a>Risolvere i problemi di licenza per Microsoft Defender per Endpoint per Mac

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**

- [Microsoft Defender per Endpoint per Mac](microsoft-defender-endpoint-mac.md)
- [Microsoft Defender ATP](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Mentre stai passando a [Microsoft Defender per Endpoint per Mac](microsoft-defender-endpoint-mac.md) e al test di distribuzione manuale o a un modello di prova (PoC), potresti ricevere l'errore seguente: [](mac-install-manually.md)

![Immagine dell'errore di licenza](images/no-license-found.png)

**Messaggio:** 

Nessuna licenza trovata

Sembra che l'organizzazione non abbia una licenza per l'abbonamento a Microsoft 365 Enterprise.

Contattare l'amministratore per assistenza.

**Causa:** 

Hai distribuito e/o installato il pacchetto Microsoft Defender for Endpoint per macOS ("Scarica pacchetto di installazione") ma potresti aver eseguito lo script di configurazione ("Scarica pacchetto di onboarding").

**Soluzione:**

Seguire le MicrosoftDefenderATPOnboardingMacOs.py seguenti: Configurazione [client](mac-install-manually.md#client-configuration)

