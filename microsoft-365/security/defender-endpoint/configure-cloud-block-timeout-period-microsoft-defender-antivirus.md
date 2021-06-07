---
title: Configurare il periodo di timeout Antivirus Microsoft Defender blocco cloud
description: Puoi configurare per quanto tempo Antivirus Microsoft Defender l'esecuzione di un file durante l'attesa di una determinazione del cloud.
keywords: Antivirus Microsoft Defender, antimalware, sicurezza, defender, cloud, timeout, blocco, periodo, secondi
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.date: 06/04/2021
ms.openlocfilehash: dfb75b77119d9550931c3e476323bde67a3b148f
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789088"
---
# <a name="configure-the-cloud-block-timeout-period"></a>Configurare il periodo di timeout del blocco cloud

**Si applica a:**

- [Microsoft Defender per endpoint](/microsoft-365/security/defender-endpoint/)

Quando Antivirus Microsoft Defender trova un file sospetto, può impedire l'esecuzione del file durante la query al [Antivirus Microsoft Defender cloud.](cloud-protection-microsoft-defender-antivirus.md)

Il periodo predefinito di blocco [del](configure-block-at-first-sight-microsoft-defender-antivirus.md) file è 10 secondi. Se si è un amministratore della sicurezza, è possibile specificare più tempo di attesa prima che sia consentita l'esecuzione del file. L'estensione del periodo di timeout del blocco cloud può contribuire a garantire che sia disponibile tempo sufficiente per ricevere una corretta determinazione dal servizio cloud Antivirus Microsoft Defender cloud.

## <a name="prerequisites-to-use-the-extended-cloud-block-timeout"></a>Prerequisiti per l'utilizzo del timeout del blocco cloud esteso

[Il blocco al primo sguardo](configure-block-at-first-sight-microsoft-defender-antivirus.md) e i relativi prerequisiti devono essere abilitati prima di poter specificare un periodo di timeout esteso.

## <a name="specify-the-extended-timeout-period-using-microsoft-endpoint-manager"></a>Specificare il periodo di timeout esteso utilizzando Microsoft Endpoint Manager

È possibile specificare il periodo di timeout del blocco cloud con un criterio di sicurezza [degli endpoint in Microsoft Endpoint Manager](/mem/intune/protect/endpoint-security-policy).

1. Accedere all'Endpoint Manager di amministrazione ( [https://endpoint.microsoft.com/](https://endpoint.microsoft.com/) ) e accedere.

2. Selezionare **Endpoint security** e quindi in **Manage** scegliere **Antivirus.**

3. Selezionare (o creare) un criterio antivirus.

4. Nella sezione **Impostazioni di configurazione** espandere Protezione **cloud**. Quindi, nella casella Timeout esteso **defender cloud in** secondi, specificare il tempo maggiore, in secondi, da 1 secondo a 50 secondi. Qualsiasi valore specificato viene aggiunto ai 10 secondi predefiniti.

5. (Questo passaggio è facoltativo) Apportare altre modifiche ai criteri antivirus. (Serve assistenza? Vedere [Impostazioni per Antivirus Microsoft Defender criteri in Microsoft Intune](/mem/intune/protect/antivirus-microsoft-defender-settings-windows).)

6. Scegliere **Avanti** e completare la configurazione dei criteri.

## <a name="specify-the-extended-timeout-period-using-group-policy"></a>Specificare il periodo di timeout esteso tramite Criteri di gruppo

È possibile utilizzare Criteri di gruppo per specificare un timeout esteso per i controlli cloud.

1. Nel computer di gestione di Criteri di gruppo aprire Console [Gestione Criteri di gruppo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))

2. Fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e quindi scegliere **Modifica.**

3. **Nell'Editor Gestione Criteri di gruppo** passare a Configurazione **computer** e quindi selezionare **Modelli amministrativi.**

3. Espandere l'albero per **Windows componenti**  >  **Antivirus Microsoft Defender**  >  **MpEngine**.

4. Fare doppio clic **su Configura controllo cloud esteso** e verificare che l'opzione sia abilitata. 

   Specificare la quantità di tempo aggiuntiva per impedire l'esecuzione del file in attesa di una determinazione del cloud. Specificare il tempo aggiuntivo, in secondi, da 1 secondo a 50 secondi. Qualsiasi valore specificato viene aggiunto ai 10 secondi predefiniti.

5. Selezionare **OK**.

 