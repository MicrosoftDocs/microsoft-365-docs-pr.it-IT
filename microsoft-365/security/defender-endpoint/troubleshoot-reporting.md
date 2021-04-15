---
title: Risolvere i problemi relativi agli strumenti di creazione di report per Microsoft Defender AV
description: Identificare e risolvere i problemi comuni quando si tenta di segnalare lo stato di protezione di Microsoft Defender AV in Conformità degli aggiornamenti
keywords: risolvere i problemi, errore, correggere, conformità degli aggiornamenti, oms, monitorare, report, Microsoft Defender AV
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 50136c620450861c41513650f27bf24fc782e968
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764532"
---
# <a name="troubleshoot-microsoft-defender-antivirus-reporting-in-update-compliance"></a>Risolvere i problemi relativi ai report di Microsoft Defender Antivirus in Conformità degli aggiornamenti

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**

- [Microsoft Defender per endpoint](/microsoft-365/security/defender-endpoint/)

> [!IMPORTANT]
> Il 31 marzo 2020, la funzionalità di segnalazione di Microsoft Defender Antivirus di Conformità degli aggiornamenti verrà rimossa. È possibile continuare a definire ed esaminare i criteri di conformità della sicurezza utilizzando [Microsoft Endpoint Manager,](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager)che consente un controllo più fine sulle funzionalità di sicurezza e gli aggiornamenti.

Puoi usare Microsoft Defender Antivirus con la conformità degli aggiornamenti. Verrà visualizzato lo stato per le licenze E3, B, F1, VL e Pro. Tuttavia, per le licenze E5, è necessario usare [il portale di Microsoft Defender for Endpoint.](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints) Per altre informazioni sulle opzioni di licenza, vedi [Opzioni di licenza dei prodotti Windows 10.](https://www.microsoft.com/licensing/product-licensing/windows10.aspx)

Quando usi [Conformità aggiornamenti di Windows Analytics](/windows/deployment/update/update-compliance-using#wdav-assessment) per ottenere la segnalazione dello stato di protezione dei dispositivi o degli endpoint nella rete che usano Microsoft Defender Antivirus, potresti riscontrare problemi o problemi.

In genere, gli indicatori più comuni di un problema sono:
- Viene visualizzato solo un numero limitato o un sottoinsieme di tutti i dispositivi che si prevedeva di visualizzare
- Non viene visualizzato alcun dispositivo
- I report e le informazioni visualizzati sono obsoleti (più vecchi di pochi giorni)

Per codici di errore comuni e ID evento correlati al servizio Microsoft Defender Antivirus che non sono correlati alla conformità degli aggiornamenti, vedi [Eventi di Microsoft Defender Antivirus.](troubleshoot-microsoft-defender-antivirus.md) 

Esistono tre passaggi per la risoluzione di questi problemi:

1. Verificare di aver soddisfatto tutti i prerequisiti
2. Verificare la connettività al Windows Defender basato su cloud
3. Inviare i log di supporto

>[!IMPORTANT]
>In genere sono necessari 3 giorni prima che i dispositivi inizino a comparire in Conformità degli aggiornamenti.


## <a name="confirm-prerequisites"></a>Verificare i prerequisiti

Per fare in modo che i dispositivi siano visualizzati correttamente in Conformità degli aggiornamenti, è necessario soddisfare alcuni prerequisiti sia per il servizio di conformità degli aggiornamenti che per Microsoft Defender Antivirus:

>[!div class="checklist"]
>- Gli endpoint usano Microsoft Defender Antivirus come unica app di protezione antivirus. [L'uso di qualsiasi altra app antivirus causerà](microsoft-defender-antivirus-compatibility.md) la disabilitazione di Microsoft Defender AV e l'endpoint non verrà segnalato in Conformità degli aggiornamenti.
> - [La protezione consegnata dal cloud è abilitata.](enable-cloud-protection-microsoft-defender-antivirus.md)
> - Gli endpoint possono [connettersi al cloud di Microsoft Defender AV](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud)
> - Se l'endpoint esegue Windows 10 versione 1607 o precedente, i dati di diagnostica di [Windows 10](/windows/configuration/configure-windows-diagnostic-data-in-your-organization#enhanced-level)devono essere impostati sul livello avanzato .
> - Sono 3 giorni che tutti i requisiti sono stati soddisfatti

"È possibile utilizzare Microsoft Defender Antivirus con la conformità degli aggiornamenti. Verrà visualizzato lo stato per le licenze E3, B, F1, VL e Pro. Tuttavia, per le licenze E5, devi usare il portale di Microsoft Defender for Endpoint ( https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints) . Per altre informazioni sulle opzioni di licenza, vedi Opzioni di licenza dei prodotti Windows 10"

Se tutti i prerequisiti precedenti sono stati soddisfatti, potrebbe essere necessario procedere al passaggio successivo per raccogliere informazioni di diagnostica e inviarle a Microsoft.

> [!div class="nextstepaction"]
> [Raccogliere dati di diagnostica per la risoluzione dei problemi di conformità degli aggiornamenti](collect-diagnostic-data.md)  

## <a name="related-topics"></a>Argomenti correlati

- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Distribuire Microsoft Defender Antivirus](deploy-manage-report-microsoft-defender-antivirus.md)