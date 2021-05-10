---
title: Specificare set di definizioni aggiuntive per l'ispezione del traffico di rete per Antivirus Microsoft Defender
description: Specificare ulteriori set di definizioni per l'ispezione del traffico di rete per Antivirus Microsoft Defender.
keywords: Antivirus Microsoft Defender, antimalware, sicurezza, defender, ispezione del traffico di rete
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
ms.openlocfilehash: 82568df0a6ad2225fd31b4c0fa4a654710f1e98b
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/10/2021
ms.locfileid: "52300196"
---
# <a name="specify-additional-definition-sets-for-network-traffic-inspection"></a>Specificare ulteriori set di definizioni per l'ispezione del traffico di rete

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**

- [Microsoft Defender per endpoint](/microsoft-365/security/defender-endpoint/)

È possibile specificare ulteriori set di definizioni per l'ispezione del traffico di rete utilizzando Criteri di gruppo.

## <a name="use-group-policy-to-specify-additional-definition-sets-for-network-traffic-inspection"></a>Utilizzare Criteri di gruppo per specificare ulteriori set di definizioni per l'ispezione del traffico di rete

1. Nell'endpoint di gestione di Criteri di gruppo aprire Console [Gestione Criteri di gruppo.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))

2. Vai a **Windows componenti**  >  **Antivirus Microsoft Defender**  >  **Network Inspection System**. 

3. Selezionare **Specificare ulteriori set di definizioni per l'ispezione del traffico di rete.** Per impostazione predefinita, questo criterio è impostato su **Non configurato**. 

4. Per modificare il criterio, selezionare il **collegamento Modifica impostazione criterio.**

5. Selezionare **Abilitato** e quindi nella **sezione Opzioni** selezionare **Mostra...**.

6. Aggiungere voci all'elenco e quindi selezionare **OK.** 

   Ogni voce deve essere elencata come coppia nome-valore, dove il nome è una rappresentazione di stringa di un GUID del set di definizioni. Ad esempio, il GUID del set di definizioni per abilitare l'intelligence di sicurezza di test è definito come: `{b54b6ac9-a737-498e-9120-6616ad3bf590}` . Il valore non viene utilizzato, pertanto è consigliabile impostarlo su `0` . 

7. Selezionare **OK** e quindi distribuire l'oggetto Criteri di gruppo aggiornato. Vedere [Console Gestione Criteri di gruppo.](/windows/win32/srvnodes/group-policy)

> [!TIP]
> Si usano oggetti Criteri di gruppo in locale? Scopri come traducono nel cloud. Analizzare gli oggetti Criteri di gruppo [locali usando l'analisi di Criteri](/mem/intune/configuration/group-policy-analytics)di gruppo in Microsoft Endpoint Manager - Anteprima . 
  
## <a name="related-articles"></a>Articoli correlati

- [Antivirus Microsoft Defender in Windows 10](microsoft-defender-antivirus-in-windows-10.md)
 
- [Abilitare la protezione fornita dal cloud](enable-cloud-protection-microsoft-defender-antivirus.md)

- [Come creare e distribuire criteri antimalware: servizio di protezione cloud](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)