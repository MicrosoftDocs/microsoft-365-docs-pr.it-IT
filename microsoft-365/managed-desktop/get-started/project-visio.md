---
title: Installare Microsoft Project o Microsoft Visio nei Microsoft Managed Desktop dispositivi
description: Informazioni sull'installazione di Microsoft Project o Microsoft Visio nei Microsoft Managed Desktop dispositivi
keywords: Microsoft Managed Desktop, Microsoft 365, Microsoft Project, Microsoft Visio
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.localizationpriority: normal
ms.date: 03/07/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 9fd46410877012d92e847ba7ff8b60cd5acceb1e
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925540"
---
# <a name="install-microsoft-project-or-microsoft-visio-on-microsoft-managed-desktop-devices"></a>Installare Microsoft Project o Microsoft Visio nei Microsoft Managed Desktop dispositivi

Microsoft Project e Microsoft Visio devono essere installati in dispositivi Microsoft Managed Desktop specifici. In questo argomento vengono documentati i prerequisiti e il processo di installazione per queste applicazioni.

## <a name="prerequisites"></a>Prerequisiti

Gli amministratori devono verificare che soddisfino questi prerequisiti:
- **Quantità di** licenze: la quantità corretta di Microsoft Project e microsoft Visio deve essere disponibile per gli utenti. Microsoft Managed Desktop attualmente supporta solo le versioni a 64 bit di queste applicazioni. 
- **Nomi delle licenze:** i nomi di licenza appropriati per queste applicazioni sono:
    - **Microsoft Project** - Project Online Professional o Project Online Premium
    - **Microsoft Visio** - Visio Online Piano 2
- **Portale aziendale-** Il Portale aziendale deve essere disponibile nel tenant per consentire agli utenti di installare queste applicazioni. Se il Portale aziendale non è distribuito nel tenant, vedere [Portale aziendale](company-portal.md).

## <a name="deploy-project-and-visio-for-microsoft-managed-desktop-devices"></a>Distribuire Project e Visio per Microsoft Managed Desktop dispositivi
Microsoft Managed Desktop aggiungerà Microsoft Project e Microsoft Visio come due applicazioni Win32 in Microsoft Intune. Verranno inoltre creati due gruppi in Azure Active Directory che verranno assegnati all'applicazione corrispondente con lo scopo "Disponibile". 

**Per distribuire Project e Visio** Aggiungi l'utente al gruppo appropriato e l'applicazione diventerà disponibile nella Portale aziendale. La sincronizzazione potrebbe richiedere alcuni minuti, ma gli utenti possono installare le app da Portale aziendale. 

Nome del gruppo di Azure AD | Quali utenti assegnare?   
 --- | ---
Modern Workplace-Office-Project_Install | Utenti che necessitano di Project
Modern Workplace-Office-Visio_Install | Utenti che necessitano Visio

## <a name="communicate-changes"></a>Comunicare le modifiche
È importante che gli amministratori IT sappiano come installare Project e Visio. Tra questi vi sono anche: 
- Notifica agli utenti quando queste applicazioni sono disponibili per loro. 
- Istruzioni su come installare queste applicazioni dal Portale aziendale.
