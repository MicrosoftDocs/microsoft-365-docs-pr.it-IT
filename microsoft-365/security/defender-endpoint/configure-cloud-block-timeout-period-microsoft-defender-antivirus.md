---
title: Configurare il periodo di timeout del blocco cloud di Microsoft Defender Antivirus
description: Puoi configurare per quanto tempo Microsoft Defender Antivirus blocterà l'esecuzione di un file in attesa di una determinazione del cloud.
keywords: Microsoft Defender Antivirus, antimalware, sicurezza, defender, cloud, timeout, blocco, periodo, secondi
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 7ec134c2861b0185f66a08257fbc410b7a475b5a
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690454"
---
# <a name="configure-the-cloud-block-timeout-period"></a>Configurare il periodo di timeout del blocco cloud

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**

- [Microsoft Defender per endpoint](/microsoft-365/security/defender-endpoint/)

Quando Microsoft Defender Antivirus rileva un file sospetto, può impedire l'esecuzione del file durante la query al [servizio cloud Microsoft Defender Antivirus.](cloud-protection-microsoft-defender-antivirus.md)

Il periodo predefinito per il blocco [del](configure-block-at-first-sight-microsoft-defender-antivirus.md) file è 10 secondi. È possibile specificare un ulteriore periodo di tempo prima che il file possa essere eseguito. In questo modo è possibile assicurarsi che sia disponibile tempo sufficiente per ricevere una determinazione appropriata dal servizio cloud Microsoft Defender Antivirus.

## <a name="prerequisites-to-use-the-extended-cloud-block-timeout"></a>Prerequisiti per l'utilizzo del timeout del blocco cloud esteso

[Il blocco al primo sguardo](configure-block-at-first-sight-microsoft-defender-antivirus.md) e i relativi prerequisiti devono essere abilitati prima di poter specificare un periodo di timeout esteso.

## <a name="specify-the-extended-timeout-period"></a>Specificare il periodo di timeout esteso

È possibile utilizzare Criteri di gruppo per specificare un timeout esteso per i controlli cloud.

1. Nel computer di gestione di Criteri di gruppo, aprire console Gestione Criteri di [gruppo,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e scegliere **Modifica**.

2. **Nell'Editor Gestione Criteri di gruppo** passare a Configurazione computer **e** fare clic su **Modelli amministrativi.**

3. Espandere l'albero fino **ai componenti di Windows > Microsoft Defender Antivirus > MpEngine**

4. Fare doppio clic **su Configura controllo cloud esteso** e verificare che l'opzione sia abilitata. Specifica la quantità di tempo aggiuntiva per impedire l'esecuzione del file durante l'attesa di una determinazione del cloud. È possibile specificare il tempo aggiuntivo, in secondi, da 1 secondo a 50 secondi. Questa ora verrà aggiunta ai 10 secondi predefiniti.

5. Fare clic su **OK**.

## <a name="related-topics"></a>Argomenti correlati

- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Usare tecnologie antivirus di nuova generazione tramite la protezione basata su cloud](cloud-protection-microsoft-defender-antivirus.md)
- [Configurare il blocco al primo avvistamento](configure-block-at-first-sight-microsoft-defender-antivirus.md)
- [Abilitare la protezione basata sul cloud](enable-cloud-protection-microsoft-defender-antivirus.md)