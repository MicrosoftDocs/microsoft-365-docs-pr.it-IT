---
title: Configurare Antivirus Microsoft Defender con WMI
description: Informazioni su come configurare e gestire Antivirus Microsoft Defender utilizzando script WMI per recuperare, modificare e aggiornare le impostazioni in Microsoft Defender for Endpoint.
keywords: wmi, script, strumentazione gestione Windows, configurazione
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
audience: ITPro
ms.topic: how-to
ms.openlocfilehash: 25518383131e4f7ecb7451965ef7a42b1c6eee4b
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764064"
---
# <a name="use-windows-management-instrumentation-wmi-to-configure-and-manage-microsoft-defender-antivirus"></a>Utilizzare Windows Management Instrumentation (WMI) per configurare e gestire Antivirus Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**

- [Microsoft Defender per endpoint](/microsoft-365/security/defender-endpoint/)

Windows Strumentazione gestione (WMI) è un'interfaccia di scripting che consente di recuperare, modificare e aggiornare le impostazioni.

Per ulteriori informazioni su WMI, vedere la libreria [Microsoft Developer Network System Administration.](/windows/win32/wmisdk/wmi-start-page)

Antivirus Microsoft Defender dispone di una serie di classi WMI specifiche che possono essere utilizzate per eseguire la maggior parte delle stesse funzioni di Criteri di gruppo e di altri strumenti di gestione. Molte delle classi sono analoghe ai [cmdlet di Defender PowerShell.](use-powershell-cmdlets-microsoft-defender-antivirus.md)

La [libreria di riferimento Windows Defender provider WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) di MSDN elenca le classi WMI disponibili per Antivirus Microsoft Defender e include script di esempio.

Le modifiche apportate con WMI influiranno sulle impostazioni locali nell'endpoint in cui le modifiche vengono distribuite o apportate. Ciò significa che le distribuzioni di criteri con Criteri di gruppo, Microsoft Endpoint Configuration Manager o Microsoft Intune possono sovrascrivere le modifiche apportate con WMI. 

È possibile [configurare le impostazioni che possono essere ignorate localmente con le sostituzioni dei criteri locali.](configure-local-policy-overrides-microsoft-defender-antivirus.md)

## <a name="related-topics"></a>Argomenti correlati

- [Argomenti di riferimento per gli strumenti di gestione e configurazione](configuration-management-reference-microsoft-defender-antivirus.md)
- [Antivirus Microsoft Defender in Windows 10](microsoft-defender-antivirus-in-windows-10.md)