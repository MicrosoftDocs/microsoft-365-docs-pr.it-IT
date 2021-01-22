---
title: Risolvere i problemi del servizio Microsoft 365 Defender
description: Trovare soluzioni e soluzioni per problemi noti di Microsoft 365 Defender
keywords: risoluzione dei problemi di Microsoft Threat Protection, risoluzione dei problemi, Azure ATP, problemi, componente aggiuntivo, pagina delle impostazioni
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 414743fa5ba25b9d2714c1dd08dd38e34ec94372
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49925719"
---
# <a name="troubleshoot-microsoft-365-defender-service-issues"></a>Risolvere i problemi del servizio Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender

In questa sezione vengono risolti i problemi che possono verificarsi quando si utilizza il servizio Microsoft 365 Defender.

## <a name="i-dont-see-microsoft-365-defender-content"></a>I don't see Microsoft 365 Defender content

Se nel riquadro di spostamento non sono disponibili funzionalità come Eventi imprevisti, Centro notifiche o Ricerca nel portale, è necessario verificare che il tenant abbia le licenze appropriate.

Per altre informazioni, vedere [Prerequisiti](prerequisites.md).

## <a name="microsoft-defender-for-identity-alerts-are-not-showing-up-in-the-microsoft-365-defender-incidents"></a>Gli avvisi di Microsoft Defender per l'identità non vengono visualizzati negli eventi imprevisti di Microsoft 365 Defender

Se nell'ambiente è distribuito Microsoft Defender for Identity, ma gli avvisi di Defender for Identity non vengono visualizzati come parte degli incidenti di Microsoft 365 Defender, è necessario verificare che l'integrazione di Microsoft Cloud App Security e Defender for Identity sia abilitata.

Per altre informazioni, vedere [Integrazione di Microsoft Defender per l'identità.](https://docs.microsoft.com/cloud-app-security/mdi-integration)

## <a name="where-is-the-settings-page-for-turning-the-service-on"></a>Dove si trova la pagina delle impostazioni per l'attivazione del servizio?

Per attivare Microsoft 365 Defender, accedere a **Impostazioni** dal riquadro di spostamento nel Centro sicurezza Microsoft 365. Questo elemento di spostamento è visibile solo se si dispone delle autorizzazioni [e delle licenze](mtp-enable.md#check-license-eligibility-and-required-permissions)prerequisiti.
