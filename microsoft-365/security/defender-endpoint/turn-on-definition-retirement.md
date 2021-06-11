---
title: Attivare il ritiro delle definizioni per Antivirus Microsoft Defender
description: Attivare il ritiro delle definizioni per Antivirus Microsoft Defender.
keywords: Antivirus Microsoft Defender, antimalware, sicurezza, difensore, ritiro delle definizioni
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.date: 06/10/2021
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 505270d319a78de20bf6fed01b7ca79c9fc2b400
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/11/2021
ms.locfileid: "52903805"
---
# <a name="turn-on-definition-retirement"></a>Attivare il ritiro delle definizioni

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**

- [Microsoft Defender per endpoint](/microsoft-365/security/defender-endpoint/)

È possibile configurare il ritiro delle definizioni utilizzando Criteri di gruppo. Il ritiro delle definizioni controlla se un computer dispone degli aggiornamenti della sicurezza necessari per proteggerlo da una particolare vulnerabilità. Se il sistema non è vulnerabile all'exploit rilevato da una definizione, tale definizione viene "ritirata". Se tutte le informazioni di sicurezza per un determinato protocollo vengono ritirate, il protocollo non viene più analizzato. L'abilitazione di questa funzionalità consente di migliorare le prestazioni. In un computer aggiornato con tutti gli aggiornamenti della sicurezza più recenti, la protezione di rete non avrà alcun impatto sulle prestazioni della rete.

## <a name="use-group-policy-to-configure-definition-retirement"></a>Utilizzare Criteri di gruppo per configurare il ritiro delle definizioni

1. Nell'endpoint di gestione di Criteri di gruppo aprire Console [Gestione Criteri di gruppo.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))

2. Passare a **Configurazione computer** Modelli  >  **amministrativi Windows**  >  **componenti**  >  **Antivirus Microsoft Defender**  >  **Network Inspection System**. 

3. Selezionare **Attiva ritiro definizione.** Per impostazione predefinita, questo criterio è abilitato. Se impostato **su Non configurato,** il ritiro delle definizioni è abilitato. 

4. Per modificare il criterio, selezionare il **collegamento Modifica impostazione criterio.**

5. Selezionare **Abilitato** e quindi **OK.**

6. Distribuire l'oggetto Criteri di gruppo aggiornato. Vedere [Console Gestione Criteri di gruppo.](/windows/win32/srvnodes/group-policy)

> [!TIP]
> Si usano oggetti Criteri di gruppo in locale? Scopri come traducono nel cloud. Analizzare gli oggetti Criteri di gruppo [locali usando l'analisi di Criteri](/mem/intune/configuration/group-policy-analytics)di gruppo in Microsoft Endpoint Manager - Anteprima . 
  
