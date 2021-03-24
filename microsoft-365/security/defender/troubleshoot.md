---
title: Risolvere i problemi del servizio Microsoft 365 Defender
description: Trovare soluzioni e soluzioni per i problemi noti di Microsoft 365 Defender
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 8d8083cbba3582c41ca91c57978675987822d0d9
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51065898"
---
# <a name="troubleshoot-microsoft-365-defender-service-issues"></a>Risolvere i problemi del servizio Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender

In questa sezione vengono risolti i problemi che possono verificarsi quando si utilizza il servizio Microsoft 365 Defender.

## <a name="i-dont-see-microsoft-365-defender-content"></a>I don't see Microsoft 365 Defender content

Se nel riquadro di spostamento non sono disponibili funzionalità come Eventi imprevisti, Centro notifiche o Ricerca nel portale, è necessario verificare che il tenant abbia le licenze appropriate.

Per altre informazioni, vedere [Prerequisiti](prerequisites.md).

## <a name="microsoft-defender-for-identity-alerts-are-not-showing-up-in-the-microsoft-365-defender-incidents"></a>Gli avvisi di Microsoft Defender for Identity non vengono visualizzati negli eventi imprevisti di Microsoft 365 Defender

Se nel tuo ambiente è distribuito Microsoft Defender for Identity ma non vedi gli avvisi di Defender for Identity come parte degli incidenti di Microsoft 365 Defender, dovrai assicurarti che l'integrazione di Microsoft Cloud App Security e Defender for Identity sia abilitata.

Per altre informazioni, vedi [Microsoft Defender per l'integrazione delle identità.](/cloud-app-security/mdi-integration)

## <a name="where-is-the-settings-page-for-turning-the-service-on"></a>Dove si trova la pagina delle impostazioni per attivare il servizio?

Per attivare Microsoft 365 Defender, accedere a **Impostazioni** dal riquadro di spostamento nel Centro sicurezza Microsoft 365. Questo elemento di spostamento è visibile solo se si dispone delle autorizzazioni e delle [licenze prerequisiti.](m365d-enable.md#check-license-eligibility-and-required-permissions)
