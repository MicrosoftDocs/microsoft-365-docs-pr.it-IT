---
title: Risoluzione dei problemi relativi al servizio Microsoft Threat Protection
description: Individuare le soluzioni e aggirare i problemi noti relativi a Microsoft Threat Protection
keywords: risoluzione dei problemi relativi alla protezione dalle minacce Microsoft, risoluzione dei problemi, Azure ATP, problemi, componente aggiuntivo, pagina impostazioni
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: bcf5b79fcd2fdf0a5af5648e6f6b7ea65d69594c
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201292"
---
# <a name="troubleshoot-microsoft-threat-protection-service-issues"></a>Risoluzione dei problemi relativi al servizio Microsoft Threat Protection

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft Threat Protection

Questa sezione consente di risolvere i problemi che potrebbero verificarsi se si utilizza il servizio Microsoft Threat Protection.


## <a name="i-dont-see-microsoft-threat-protection-content"></a>Non viene visualizzato il contenuto di Microsoft Threat Protection
Se non si visualizzano le funzionalità nel riquadro di spostamento, ad esempio gli eventi non consentiti, il centro azioni o la ricerca nel portale, è necessario verificare che il tenant disponga delle licenze appropriate. 

Per altre informazioni, vedere [Prerequisiti](prerequisites.md).

## <a name="azure-atp-alerts-are-not-showing-up-in-the-microsoft-threat-protection-incidents"></a>Gli avvisi di Azure ATP non sono visualizzati tra gli incidenti di Microsoft Threat Protection
Se si utilizza Azure ATP nell'ambiente distribuito ma non è possibile vedere gli avvisi di Azure ATP come incidenti di Microsoft Threat Protection, è necessario verificare che sia abilitata l'integrazione di Microsoft Cloud App Security e Azure ATP. 

Per altre informazioni, vedere [Integrazione di Azure ATP](https://docs.microsoft.com/cloud-app-security/aatp-integration).

## <a name="where-is-the-settings-page-for-turning-the-service-on"></a>Dove si trova la pagina impostazioni per l'attivazione del servizio?
Per abilitare Microsoft Threat Protection, accedere alle **Impostazioni** dal riquadro di spostamento nel centro sicurezza di Microsoft 365. Questo elemento di spostamento è visibile solo se si dispone delle [autorizzazioni e delle licenze prerequisite](mtp-enable.md#check-license-eligibility-and-required-permissions).
 

