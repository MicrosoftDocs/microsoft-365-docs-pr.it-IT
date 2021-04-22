---
title: Compatibilità di Microsoft Defender Antivirus con Defender for Endpoint
description: Informazioni su come Windows Defender con Microsoft Defender per Endpoint e su come funziona quando viene utilizzato un client antimalware di terze parti.
keywords: Compatibilità con windows Defender, defender, Microsoft Defender for Endpoint, defender per endpoint, antivirus, mde
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
ms.topic: conceptual
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: a8dca4a80385fabcdc64a5584474214d05be4a6c
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935378"
---
# <a name="microsoft-defender-antivirus-compatibility-with-microsoft-defender-for-endpoint"></a>Compatibilità di Microsoft Defender Antivirus con Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-defendercompat-abovefoldlink)

L'agente microsoft Defender for Endpoint dipende da Microsoft Defender Antivirus per alcune funzionalità, ad esempio l'analisi dei file.

>[!IMPORTANT]
>Defender for Endpoint non rispetta le impostazioni di esclusione di Microsoft Defender Antivirus. 

Devi configurare gli aggiornamenti di Security intelligence in Defender per i dispositivi endpoint indipendentemente dal fatto che Microsoft Defender Antivirus sia l'antimalware attivo o meno. Per altre informazioni, vedi [Gestire gli aggiornamenti di Microsoft Defender Antivirus e applicare le linee di base.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus.md)

Se un dispositivo onboarded è protetto da un client antimalware di terze parti, Microsoft Defender Antivirus su tale endpoint entra in modalità passiva.

Microsoft Defender Antivirus continuerà a ricevere gli aggiornamenti e il processo *dimspeng.exe* verrà elencato come un servizio in esecuzione, ma non eseguirà analisi e non sostituirà il client antimalware di terze parti in esecuzione.

L'interfaccia di Microsoft Defender Antivirus verrà disabilitata e gli utenti nel dispositivo non potranno usare Microsoft Defender Antivirus per eseguire analisi su richiesta o configurare la maggior parte delle opzioni.

Per altre informazioni, vedi l'argomento Microsoft Defender Antivirus e Defender per la compatibilità [degli endpoint.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)
