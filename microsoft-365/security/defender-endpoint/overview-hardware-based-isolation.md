---
title: Isolamento basato su hardware (Windows 10)
ms.reviewer: ''
description: Scopri come l'isolamento basato su hardware in Windows 10 aiuta a contrastare il malware.
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.author: macapara
ms.date: 09/07/2018
ms.technology: mde
ms.openlocfilehash: b31db39e03ed23698e71c4b38fb0937d2ba59727
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51060953"
---
# <a name="hardware-based-isolation-in-windows-10"></a>Isolamento basato su hardware in Windows 10

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender ATP](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


L'isolamento basato su hardware consente di proteggere l'integrità del sistema in Windows 10 ed è integrato con Microsoft Defender for Endpoint. 

| Funzionalità | Descrizione |
|------------|-------------|
| [Windows Defender Application Guard](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-application-guard/md-app-guard-overview.md) | Application Guard protegge il dispositivo da attacchi avanzati, mantenendoti produttivo. Utilizzando un approccio di isolamento basato su hardware univoco, l'obiettivo è isolare i siti Web e i documenti PDF non attendibili all'interno di un contenitore leggero separato dal sistema operativo tramite l'hypervisor windows nativo. Se un sito o un documento PDF non attendibile risulta dannoso, rimane comunque contenuto nel contenitore sicuro di Application Guard, mantenendo il PC desktop protetto e l'autore dell'attacco lontano dai dati aziendali. |
| [Windows Defender System Guard](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-system-guard/system-guard-how-hardware-based-root-of-trust-helps-protect-windows.md) | System Guard protegge e mantiene l'integrità del sistema all'avvio e dopo l'esecuzione e convalida l'integrità del sistema utilizzando l'attestazione.  |
