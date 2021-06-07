---
title: Compatibilità della soluzione antivirus con Defender for Endpoint
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
ms.date: 05/06/2021
ms.technology: mde
ms.openlocfilehash: f5a0db755f919cb47c4cd284857ddf4e27d16996
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782886"
---
# <a name="antivirus-solution-compatibility-with-microsoft-defender-for-endpoint"></a>Compatibilità delle soluzioni antivirus con Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-defendercompat-abovefoldlink)

L'agente di Microsoft Defender for Endpoint dipende Antivirus Microsoft Defender alcune funzionalità, ad esempio l'analisi dei file.

>[!IMPORTANT]
>Defender for Endpoint non rispetta le impostazioni Antivirus Microsoft Defender esclusioni. 

Devi configurare gli aggiornamenti di Security Intelligence in Defender per i dispositivi endpoint Antivirus Microsoft Defender è l'antimalware attivo o meno. Per ulteriori informazioni, vedere [Manage Antivirus Microsoft Defender updates and apply baselines](manage-updates-baselines-microsoft-defender-antivirus.md).

Se un dispositivo onboarded è protetto da un client antimalware di terze parti, Antivirus Microsoft Defender su tale endpoint verrà attivata la modalità passiva.

Antivirus Microsoft Defender continuerà a ricevere gli aggiornamenti e il processo *dimspeng.exe* verrà elencato come un servizio in esecuzione, ma non eseguirà analisi e non sostituirà il client antimalware di terze parti in esecuzione.

L Antivirus Microsoft Defender interno verrà disabilitata e gli utenti nel dispositivo non potranno usare Antivirus Microsoft Defender per eseguire analisi su richiesta o configurare la maggior parte delle opzioni.

Per altre informazioni, vedi l'argomento [Antivirus Microsoft Defender e Defender per la compatibilità degli endpoint.](microsoft-defender-antivirus-compatibility.md)
