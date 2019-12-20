---
title: Caccia alle minacce in Microsoft 365
description: Utilizzo delle funzionalità di ricerca di minacce nel centro sicurezza Microsoft 365 per individuare in modo proattivo le violazioni e altre minacce
keywords: sicurezza, malware, Microsoft 365, M365, Microsoft Threat Protection, MTP, Centro sicurezza, Hunt, Threat Hunting, cyberthreat Hunting, Microsoft Defender ATP, Office 365 ATP, Azure ATP, Advanced Hunting
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
ms.author: lomayor
author: lomayor
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.openlocfilehash: 12705fa525374af8870aedcd211d8e9dcdd17f9c
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/19/2019
ms.locfileid: "40808741"
---
# <a name="hunt-for-threats-in-microsoft-365"></a>Caccia alle minacce in Microsoft 365

Con le funzionalità di ricerca di minacce nel centro sicurezza Microsoft 365, è possibile trovare in modo proattivo minacce nell'organizzazione che interessano la posta elettronica e i dati, i dispositivi e le identità. Nella schermata di **caccia** è possibile accedere agli strumenti di ricerca di minacce resi disponibili da diverse soluzioni:
- Office 365 ATP: [caccia alle minacce per la posta elettronica e i dati](../office-365-security/office-365-atp.md)
- Microsoft Defender ATP: [caccia alle minacce ai dispositivi](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting)
- Azure ATP: [ricerca di minacce per le identità](https://docs.microsoft.com/azure-advanced-threat-protection/investigate-a-user)

![Pagina di caccia](../images/hunt.png)


## <a name="hunt-with-microsoft-threat-protection"></a>Cercare con Microsoft Threat Protection

[Abilitare Microsoft Threat Protection](mtp-enable.md) per ottenere l'interfaccia di query di ricerca avanzata direttamente nel centro sicurezza Microsoft 365. Con la [ricerca avanzata](advanced-hunting-overview.md), è possibile creare singole query che esaminano i dati di Microsoft Defender ATP, coprendo i dati dai dispositivi onboarded e Office 365 ATP, fornendo dati da messaggi di posta elettronica.

## <a name="related-topics"></a>Argomenti correlati
- [Panoramica della ricerca avanzata](advanced-hunting-overview.md)
- [Panoramica su Microsoft Threat Protection](microsoft-threat-protection.md)
- [Attivare Microsoft Threat Protection](mtp-enable.md)