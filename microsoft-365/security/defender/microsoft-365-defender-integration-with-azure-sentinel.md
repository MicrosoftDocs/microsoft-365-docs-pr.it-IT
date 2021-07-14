---
title: Le integrazioni di Microsoft 365 Defender con Azure Sentinel.
description: Usa Azure Sentinel come SIEM per eventi Microsoft 365 Defender eventi imprevisti.
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
ms.openlocfilehash: adb65c82713464da2df4d473d2fd7a055e0dbeb3
ms.sourcegitcommit: 4046c2c390851dffcdb430e1ba38c4df23fe2e69
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/13/2021
ms.locfileid: "53415579"
---
# <a name="microsoft-365-defender-integration-with-azure-sentinel"></a>Le integrazioni di Microsoft 365 Defender con Azure Sentinel.

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Si applica a:**
- Microsoft 365 Defender

Il connettore Microsoft 365 Defender per Azure Sentinel (anteprima) invia tutte le informazioni relative Microsoft 365 Defender eventi imprevisti e avvisi ad Azure Sentinel e mantiene sincronizzati gli eventi imprevisti. 

Dopo aver aggiunto il connettore, gli eventi imprevisti di Microsoft 365 Defender che includono tutti gli avvisi, le entità e le informazioni pertinenti associati ricevuti da Microsoft Defender for Endpoint, Microsoft Defender for Identity, Microsoft Defender per Office 365 e Microsoft Cloud App Security vengono trasmessi ad Azure Sentinel come dati &mdash; siem (Security Information and Event Management), fornendo il contesto per eseguire la triage e la risposta agli incidenti con &mdash; Azure Sentinel. 

Una volta in Azure Sentinel, gli incidenti rimangono sincronizzati bidirezionalemente con Microsoft 365 Defender, consentendoti di sfruttare i vantaggi del portale di Microsoft 365 Defender e di Azure Sentinel nel portale di Azure per l'indagine e la risposta agli incidenti.

Guarda questa breve panoramica dell'integrazione di Azure Sentinel con Microsoft 365 Defender (4 minuti).

<br>

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWFIRo]


Ecco come funziona.

:::image type="content" source="../../media/microsoft-365-defender-integration-with-azure-sentinel/microsoft-365-defender-integration-with-azure-sentinel.png" alt-text="Flusso e condivisione dei dati degli eventi imprevisti tra Microsoft 365 Defender e Azure Sentinel":::

## <a name="next-steps"></a>Passaggi successivi

1. Informazioni più approfondite [sull'Microsoft 365 Defender'integrazione con Azure Sentinel.](/azure/sentinel/microsoft-365-defender-sentinel-integration)
2. [Connessione dati da Microsoft 365 Defender ad Azure Sentinel.](/azure/sentinel/connect-microsoft-365-defender)

## <a name="see-also"></a>Vedere anche

- [Panoramica degli eventi imprevisti in Microsoft 365 Defender](incidents-overview.md)
- [Analizzare gli eventi imprevisti con Azure Sentinel](/azure/sentinel/tutorial-investigate-cases)
