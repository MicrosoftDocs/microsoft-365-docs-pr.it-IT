---
title: Installare Microsoft Project o Microsoft Visio nei dispositivi Microsoft Managed Desktop
description: Informazioni sull'installazione di Microsoft Project o Microsoft Visio sui dispositivi Microsoft Managed Desktop
keywords: Microsoft Managed Desktop, Microsoft 365, Microsoft Project, Microsoft Visio
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 03/07/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 5c820e36b7b397fe770216ee229e38a1da5b034d
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32288997"
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
Dopo aver inviato la richiesta di supporto, Microsoft Managed Desktop creerà tre gruppi di Azure AD e tre distribuzioni di applicazioni tramite Microsoft Intune per distribuire le app al tenant.  

**Per distribuire Project e Visio**
1. **Presentare una richiesta di supporto** Gli amministratori IT devono presentare una richiesta di supporto per rendere queste applicazioni disponibili agli utenti. Per informazioni su come contattare Microsoft Managed Desktop, vedere [supporto di amministrazione per Microsoft managEd desktop](../working-with-managed-desktop/admin-support.md).
2. **Assegnare gli utenti ai nuovi gruppi di Azure ad** Microsoft Managed Desktop creerà tre gruppi di Azure AD nel tenant e 3 distribuzioni di applicazioni corrispondenti. Gli amministratori IT devono assegnare gli utenti ai gruppi adatti.

>[!NOTE]
>Assegnare gli utenti solo a uno di questi gruppi di Azure AD. 

Nome del gruppo di Azure AD | Quali utenti assegnare?   
 --- | ---
Microsoft-Office-Project-install | Gli utenti che hanno bisogno di solo Project
Microsoft-Office-Visio-install | Gli utenti che hanno bisogno di solo Visio
Microsoft-Office-Project e Visio-install | Gli utenti che hanno bisogno sia di Project che di Visio

Una volta assegnati a questi gruppi, le applicazioni saranno disponibili nel portale aziendale. La sincronizzazione potrebbe richiedere alcuni minuti, ma gli utenti possono installare le app dal portale aziendale. 

## <a name="communicate-changes"></a>Comunicare le modifiche
Per gli amministratori IT è importante consentire agli utenti di sapere come installare Project e Visio. Ciò include: 
- Notifica agli utenti quando sono disponibili per queste applicazioni. 
- Istruzioni su come installare queste applicazioni dal portale aziendale.

>[!NOTE]
>Gli utenti devono chiudere tutte le applicazioni di Office prima di installare Microsoft Project o Microsoft Visio dal portale aziendale. 
