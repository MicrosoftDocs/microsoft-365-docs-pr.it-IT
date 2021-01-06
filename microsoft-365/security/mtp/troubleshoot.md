---
title: Risoluzione dei problemi relativi al servizio Microsoft 365 Defender
description: Individuare soluzioni e risolvere i problemi noti di Microsoft 365 Defender
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
ms.openlocfilehash: b7b6ea55d084c114b79dfee0e061b09c8ede8632
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/06/2021
ms.locfileid: "49760459"
---
# <a name="troubleshoot-microsoft-365-defender-service-issues"></a>Risoluzione dei problemi relativi al servizio Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender

In questa sezione vengono affrontati i problemi che potrebbero verificarsi durante l'utilizzo del servizio Microsoft 365 Defender.

## <a name="i-dont-see-microsoft-365-defender-content"></a>Non viene visualizzato il contenuto Microsoft 365 Defender

Se non si visualizzano le funzionalità nel riquadro di spostamento, ad esempio gli eventi non consentiti, il centro azioni o la ricerca nel portale, è necessario verificare che il tenant disponga delle licenze appropriate.

Per altre informazioni, vedere [Prerequisiti](prerequisites.md).

## <a name="microsoft-defender-for-identity-alerts-are-not-showing-up-in-the-microsoft-365-defender-incidents"></a>Microsoft Defender per gli avvisi di identità non viene visualizzato negli incidenti Microsoft 365 Defender

Se si dispone di Microsoft Defender per Identity distribuito nell'ambiente, ma non si vedono i difensori per gli avvisi di identità come parte degli incidenti Microsoft 365 Defender, è necessario verificare che Microsoft cloud app Security and Defender for Identity Integration sia abilitato.

Per ulteriori informazioni, vedere [Microsoft Defender for Identity Integration](https://docs.microsoft.com/cloud-app-security/mdi-integration).

## <a name="where-is-the-settings-page-for-turning-the-service-on"></a>Dove si trova la pagina impostazioni per l'attivazione del servizio?

Per abilitare Microsoft 365 Defender, accedere alle **Impostazioni** dal riquadro di spostamento nel centro sicurezza di Microsoft 365. Questo elemento di spostamento è visibile solo se si dispone delle [autorizzazioni e delle licenze prerequisite](mtp-enable.md#check-license-eligibility-and-required-permissions).
