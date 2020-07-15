---
title: Installare Microsoft Project o Microsoft Visio nei dispositivi Microsoft Managed Desktop
description: Informazioni sull'installazione di Microsoft Project o Microsoft Visio sui dispositivi Microsoft Managed Desktop
keywords: Microsoft Managed Desktop, Microsoft 365, Microsoft Project, Microsoft Visio
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.date: 03/07/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: c8690db17c71fd5ce604fd9165fee7e54a41c639
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2020
ms.locfileid: "45126828"
---
# <a name="install-microsoft-project-or-microsoft-visio-on-microsoft-managed-desktop-devices"></a>Installare Microsoft Project o Microsoft Visio nei dispositivi Microsoft Managed Desktop

Microsoft Project e Microsoft Visio richiedono una procedura specifica da installare sui dispositivi Microsoft Managed Desktop. In questo argomento vengono documentati i prerequisiti e il processo di installazione per queste applicazioni.

## <a name="prerequisites"></a>Prerequisiti

Gli amministratori devono verificare che soddisfino questi prerequisiti:
- **Quantità di licenza** : la quantità corretta di Microsoft Project e delle licenze di Microsoft Visio deve essere disponibile per gli utenti. Microsoft Managed Desktop attualmente supporta solo le versioni a 64 bit di queste applicazioni. 
- **Nomi delle licenze** -i nomi delle licenze appropriate per queste applicazioni sono:
    - **Microsoft Project** -Project Online Professional o Project Online Premium
    - **Microsoft Visio** -Visio online, piano 2
- **Portale aziendale** : il portale aziendale deve essere disponibile nel tenant per consentire agli utenti di installare queste applicazioni. Se il portale aziendale non è distribuito nel tenant, vedere [Company Portal](company-portal.md).

## <a name="deploy-project-and-visio-for-microsoft-managed-desktop-devices"></a>Distribuire Project e Visio per i dispositivi Microsoft Managed Desktop
Microsoft Managed Desktop aggiungerà Microsoft Project e Microsoft Visio come due applicazioni Win32 in Microsoft Intune. Verranno inoltre creati due gruppi in Azure Active Directory che verranno assegnati all'applicazione corrispondente con lo scopo "available". 

**Per distribuire Project e Visio** Aggiungere l'utente al gruppo appropriato e l'applicazione diventerà disponibile nel portale aziendale. La sincronizzazione potrebbe richiedere alcuni minuti, ma gli utenti possono installare le app dal portale aziendale. 

Nome del gruppo di Azure AD | Quali utenti assegnare?   
 --- | ---
Ambiente di lavoro moderno-Office-Project_Install | Utenti che necessitano di un progetto
Ambiente di lavoro moderno-Office-Visio_Install | Utenti che hanno bisogno di Visio

## <a name="communicate-changes"></a>Comunicare le modifiche
Per gli amministratori IT è importante consentire agli utenti di sapere come installare Project e Visio. Ciò include: 
- Notifica agli utenti quando sono disponibili per queste applicazioni. 
- Istruzioni su come installare queste applicazioni dal portale aziendale.
