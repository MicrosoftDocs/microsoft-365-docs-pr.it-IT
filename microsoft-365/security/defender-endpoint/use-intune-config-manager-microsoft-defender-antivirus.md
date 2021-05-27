---
title: Configurare Antivirus Microsoft Defender tramite Microsoft Endpoint Manager
description: Usare Microsoft Endpoint Manager e Microsoft Intune per configurare Microsoft Defender AV e Endpoint Protection
keywords: scep, intune, endpoint protection, configurazione
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/24/2021
ms.reviewer: phuijbr, oogunrinde
manager: dansimp
ms.technology: mde
audience: ITPro
ms.topic: how-to
ms.openlocfilehash: ab77f3ab5ac9385d1ce049061730d2192e3bcb0c
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2021
ms.locfileid: "52683752"
---
# <a name="use-microsoft-endpoint-manager-to-configure-and-manage-microsoft-defender-antivirus"></a>Utilizzare Microsoft Endpoint Manager per configurare e gestire le Antivirus Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**

- [Microsoft Defender per endpoint](/microsoft-365/security/defender-endpoint/)

È possibile utilizzare [Microsoft Endpoint Manager](/mem/endpoint-manager-overview) per configurare Antivirus Microsoft Defender analisi. [Microsoft Intune](/mem/intune/fundamentals/what-is-intune) e [Configuration Manager](/mem/configmgr/core/understand/introduction) fanno ora parte di Endpoint Manager.  

## <a name="configure-microsoft-defender-antivirus-scans-in-endpoint-manager"></a>Configurare Antivirus Microsoft Defender analisi in Endpoint Manager

1. Accedere all'Microsoft Endpoint Manager di amministrazione ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) e accedere.

2. Passare a **Endpoint Security**.

3. In **Gestisci** scegliere **Antivirus.**

4. Selezionare i criteri Antivirus Microsoft Defender criteri. 

5. In **Gestisci** scegliere **Proprietà**.

6. Accanto a **Impostazioni di configurazione** scegliere **Modifica**.

7. Espandere la **sezione Analisi** ed esaminare o modificare le impostazioni di analisi.

8. Scegliere **Revisione e salvataggio**


> [!TIP]
> Hai bisogno di assistenza? Vedi [Gestire la sicurezza degli endpoint in Microsoft Intune](/mem/intune/protect/endpoint-security).


## <a name="related-articles"></a>Articoli correlati

- [Articoli di riferimento per gli strumenti di gestione e configurazione](configuration-management-reference-microsoft-defender-antivirus.md)
- [Antivirus Microsoft Defender in Windows 10](microsoft-defender-antivirus-in-windows-10.md)