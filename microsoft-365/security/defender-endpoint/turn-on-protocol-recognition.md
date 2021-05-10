---
title: Attivare il riconoscimento del protocollo per Antivirus Microsoft Defender
description: Attivare il riconoscimento protocollo per Antivirus Microsoft Defender.
keywords: Antivirus Microsoft Defender, antimalware, sicurezza, difensore, riconoscimento protocollo
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.date: 05/07/2021
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 890303a15618a0318db0421c9c80f270583e19bf
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/10/2021
ms.locfileid: "52296478"
---
# <a name="turn-on-protocol-recognition"></a>Attivare il riconoscimento del protocollo 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**

- [Microsoft Defender per endpoint](/microsoft-365/security/defender-endpoint/)

Questa impostazione dei criteri consente di configurare il riconoscimento del protocollo per la protezione della rete da exploit di vulnerabilità note. Se si abilita o non si configura questa impostazione, verrà abilitato il riconoscimento del protocollo. Se disabiliti questa impostazione, il riconoscimento del protocollo verrà disabilitato.

## <a name="use-group-policy-to-configure-protocol-recognition"></a>Utilizzare Criteri di gruppo per configurare il riconoscimento protocollo

1. Nell'endpoint di gestione di Criteri di gruppo aprire Console [Gestione Criteri di gruppo.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))

2. Passare a **Configurazione computer** Modelli  >  **amministrativi Windows**  >  **componenti**  >  **Antivirus Microsoft Defender**  >  **Network Inspection System**. 

3. Selezionare **riconoscimento protocollo**. Per impostazione predefinita, questo criterio è abilitato. Se impostato **su Non configurato,** il ritiro delle definizioni è abilitato. 

4. Per modificare il criterio, selezionare il **collegamento Modifica impostazione criterio.**

5. Selezionare **Abilitato** e quindi **OK.**

6. Distribuire l'oggetto Criteri di gruppo aggiornato. Vedere [Console Gestione Criteri di gruppo.](/windows/win32/srvnodes/group-policy)

> [!TIP]
> Si usano oggetti Criteri di gruppo in locale? Scopri come traducono nel cloud. Analizzare gli oggetti Criteri di gruppo [locali usando l'analisi di Criteri](/mem/intune/configuration/group-policy-analytics)di gruppo in Microsoft Endpoint Manager - Anteprima . 
  
## <a name="related-articles"></a>Articoli correlati

- [Antivirus Microsoft Defender in Windows 10](microsoft-defender-antivirus-in-windows-10.md)
 
- [Abilitare la protezione fornita dal cloud](enable-cloud-protection-microsoft-defender-antivirus.md)

- [Come creare e distribuire criteri antimalware: servizio di protezione cloud](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)