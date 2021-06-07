---
title: Microsoft 365 Integrazione di Defender con Azure Sentinel
description: Usa Azure Sentinel come SIEM per Microsoft 365 eventi ed eventi di Defender.
keywords: incidenti, avvisi, analizzare, analizzare, risposta, correlazione, attacco, computer, dispositivi, utenti, identità, identità, identità, cassetta postale, posta elettronica, 365, microsoft, m365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 7d9cff584f35c39544034501c607b7156a0f1bf2
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782922"
---
# <a name="microsoft-365-defender-integration-with-azure-sentinel"></a>Microsoft 365 Integrazione di Defender con Azure Sentinel

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Si applica a:**
- Microsoft 365 Defender

Il connettore Microsoft 365 Defender per Azure Sentinel (anteprima) invia tutti gli eventi imprevisti e gli avvisi di Microsoft 365 Defender ad Azure Sentinel e mantiene sincronizzati gli eventi imprevisti. 

Dopo aver aggiunto il connettore, gli eventi imprevisti di Microsoft 365 Defender che includono tutti gli avvisi, le entità e le informazioni pertinenti associati ricevuti da Microsoft Defender for Endpoint, Microsoft Defender for Identity, Microsoft Defender per Office 365 e Microsoft Cloud App Security vengono trasmessi ad Azure Sentinel come dati &mdash; siem (Security Information and Event Management), fornendo il contesto per eseguire la triage e la risposta agli incidenti con &mdash; Azure Sentinel. 

Una volta in Azure Sentinel, gli incidenti rimangono sincronizzati bidirezionalemente con Microsoft 365 Defender, consentendoti di sfruttare i vantaggi del Centro sicurezza Microsoft 365 e di Azure Sentinel nel portale di Azure per l'indagine e la risposta agli incidenti.

Ecco come funziona.

:::image type="content" source="../../media/microsoft-365-defender-integration-with-azure-sentinel/microsoft-365-defender-integration-with-azure-sentinel.png" alt-text="Flusso e condivisione dei dati degli eventi imprevisti tra Microsoft 365 Defender e Azure Sentinel":::

## <a name="next-steps"></a>Passaggi successivi

1. Informazioni più approfondite [sull'integrazione Microsoft 365 Defender con Azure Sentinel.](/azure/sentinel/microsoft-365-defender-sentinel-integration)
2. [Connessione dati da Microsoft 365 Defender ad Azure Sentinel.](/azure/sentinel/connect-microsoft-365-defender)

## <a name="see-also"></a>Vedere anche

- [Panoramica degli eventi imprevisti in Microsoft 365 Defender](incidents-overview.md)
- [Analizzare gli eventi imprevisti con Azure Sentinel](/azure/sentinel/tutorial-investigate-cases)
