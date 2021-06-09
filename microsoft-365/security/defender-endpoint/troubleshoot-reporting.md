---
title: Risolvere i problemi relativi agli strumenti di creazione di report per Microsoft Defender AV
description: Identificare e risolvere i problemi comuni quando si tenta di segnalare lo stato di protezione di Microsoft Defender AV in Conformità degli aggiornamenti
keywords: risolvere i problemi, errore, correggere, conformità degli aggiornamenti, oms, monitorare, report, Microsoft Defender AV
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
ms.openlocfilehash: ab987089c20d0a1d0baed152e7ddcfdd2878cc65
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843459"
---
# <a name="troubleshoot-microsoft-defender-antivirus-reporting-in-update-compliance"></a>Risolvere i problemi relativi alla creazione di report di Microsoft Defender Antivirus nella procedura di aggiornamento per la conformità

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**

- [Microsoft Defender per endpoint](/microsoft-365/security/defender-endpoint/)

> [!IMPORTANT]
> Il 31 marzo 2020 verrà rimossa la Antivirus Microsoft Defender di report di Conformità degli aggiornamenti. È possibile continuare a definire ed esaminare i criteri di conformità della sicurezza [usando Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager), che consente un controllo più fine sulle funzionalità e gli aggiornamenti di sicurezza.

È possibile utilizzare Antivirus Microsoft Defender conformità degli aggiornamenti. Vedrai lo stato per le licenze E3, B, F1, VL e Pro licenze. Tuttavia, per le licenze E5, è necessario usare [il portale di Microsoft Defender for Endpoint.](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints) Per ulteriori informazioni sulle opzioni di licenza, vedere [Windows 10 opzioni di licenza del prodotto.](https://www.microsoft.com/licensing/product-licensing/windows10.aspx)

Quando si usa Windows conformità agli aggiornamenti di Windows Analytics per ottenere la segnalazione dello stato di protezione dei dispositivi o [degli endpoint](/windows/deployment/update/update-compliance-using#wdav-assessment) della rete che usano Antivirus Microsoft Defender, è possibile che si verifichino problemi o problemi.

In genere, gli indicatori più comuni di un problema sono:
- Viene visualizzato solo un numero limitato o un sottoinsieme di tutti i dispositivi che si prevedeva di visualizzare
- Non viene visualizzato alcun dispositivo
- I report e le informazioni visualizzati sono obsoleti (più vecchi di pochi giorni)

Per codici di errore comuni e ID evento correlati al servizio Antivirus Microsoft Defender che non sono correlati alla conformità degli aggiornamenti, vedere Antivirus Microsoft Defender [eventi](troubleshoot-microsoft-defender-antivirus.md). 

Esistono tre passaggi per la risoluzione di questi problemi:

1. Verificare di aver soddisfatto tutti i prerequisiti
2. Verificare la connettività al Windows Defender basato su cloud
3. Inviare i log di supporto

>[!IMPORTANT]
>In genere sono necessari 3 giorni prima che i dispositivi inizino a comparire in Conformità degli aggiornamenti.


## <a name="confirm-prerequisites"></a>Verificare i prerequisiti

Per fare in modo che i dispositivi siano visualizzati correttamente in Conformità degli aggiornamenti, è necessario soddisfare alcuni prerequisiti sia per il servizio di conformità degli aggiornamenti che per Antivirus Microsoft Defender:

>[!div class="checklist"]
>- Gli endpoint usano il Antivirus Microsoft Defender come unica app di protezione antivirus. [L'uso di qualsiasi altra app antivirus causerà](microsoft-defender-antivirus-compatibility.md) la disabilitazione di Microsoft Defender AV e l'endpoint non verrà segnalato in Conformità degli aggiornamenti.
> - [La protezione consegnata dal cloud è abilitata.](enable-cloud-protection-microsoft-defender-antivirus.md)
> - Gli endpoint possono [connettersi al cloud di Microsoft Defender AV](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud)
> - Se l'endpoint è Windows 10 versione 1607 o precedente, Windows 10 dati di diagnostica devono essere impostati [sul livello avanzato](/windows/configuration/configure-windows-diagnostic-data-in-your-organization#enhanced-level).
> - Sono 3 giorni che tutti i requisiti sono stati soddisfatti

"È possibile utilizzare Antivirus Microsoft Defender conformità degli aggiornamenti. Vedrai lo stato per le licenze E3, B, F1, VL e Pro licenze. Tuttavia, per le licenze E5, devi usare il portale di Microsoft Defender for Endpoint (/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints). Per ulteriori informazioni sulle opzioni di licenza, vedere Windows 10 opzioni di licenza del prodotto"

Se tutti i prerequisiti precedenti sono stati soddisfatti, potrebbe essere necessario procedere al passaggio successivo per raccogliere informazioni di diagnostica e inviarle a Microsoft.

> [!div class="nextstepaction"]
> [Raccogliere dati di diagnostica per la risoluzione dei problemi di conformità degli aggiornamenti](collect-diagnostic-data.md)  

## <a name="related-topics"></a>Argomenti correlati

- [Antivirus Microsoft Defender in Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Distribuire Antivirus Microsoft Defender](deploy-manage-report-microsoft-defender-antivirus.md)