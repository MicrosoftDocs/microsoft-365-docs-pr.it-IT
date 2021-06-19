---
title: Risolvere i Microsoft 365 Defender dei servizi
description: Trovare soluzioni e soluzioni alternative per problemi Microsoft 365 Defender noti
keywords: risoluzione Microsoft 365 Defender, risoluzione dei problemi, Microsoft Defender per l'identità, problemi, componente aggiuntivo, pagina delle impostazioni
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
ms.openlocfilehash: 14033ffeb3d08efad7f45eb4c319ac0401b7df09
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028472"
---
# <a name="troubleshoot-microsoft-365-defender-service-issues"></a>Risolvere i Microsoft 365 Defender dei servizi

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender

In questa sezione vengono risolti i problemi che possono verificarsi quando si utilizza il Microsoft 365 Defender servizio.

## <a name="i-dont-see-microsoft-365-defender-content"></a>I don't see Microsoft 365 Defender content

Se nel riquadro di spostamento non sono disponibili funzionalità come Eventi imprevisti, Centro notifiche o Ricerca nel portale, è necessario verificare che il tenant abbia le licenze appropriate.

Per altre informazioni, vedere [Prerequisiti](prerequisites.md).

## <a name="microsoft-defender-for-identity-alerts-are-not-showing-up-in-the-microsoft-365-defender-incidents"></a>Gli avvisi di Microsoft Defender per l'identità non vengono visualizzati negli Microsoft 365 Defender imprevisti

Se nel tuo ambiente è distribuito Microsoft Defender for Identity ma non vedi gli avvisi di Defender for Identity come parte di eventi imprevisti di Microsoft 365 Defender, dovrai assicurarti che l'integrazione di Microsoft Cloud App Security e Defender for Identity sia abilitata.

Per altre informazioni, vedi [Microsoft Defender per l'integrazione delle identità.](/cloud-app-security/mdi-integration)

## <a name="where-is-the-settings-page-for-turning-on-the-service"></a>Dove si trova la pagina delle impostazioni per l'attivazione del servizio?

Per attivare la Microsoft 365 Defender, **accedere** Impostazioni dal riquadro di spostamento nel centro sicurezza Microsoft 365 sicurezza. Questo elemento di spostamento è visibile solo se si dispone delle autorizzazioni e delle [licenze prerequisiti.](m365d-enable.md#check-license-eligibility-and-required-permissions)

## <a name="how-do-i-create-an-exception-for-my-fileurl"></a>Come si crea un'eccezione per il file o l'URL?

Un falso positivo è un file o un URL rilevato come dannoso ma non una minaccia. Puoi creare indicatori e definire esclusioni per sbloccare e consentire determinati file/URL. Vedi [Indirizzo falsi positivi/negativi in Defender per Endpoint.](/microsoft-365/security/defender-endpoint/defender-endpoint-false-positives-negatives)


