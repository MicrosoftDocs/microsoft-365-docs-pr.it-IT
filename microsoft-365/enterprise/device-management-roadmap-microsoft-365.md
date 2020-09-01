---
title: Roadmap per la gestione dei dispositivi per Microsoft 365
keywords: Microsoft 365, Microsoft 365 per Enterprise, documentazione di Microsoft 365, gestione dei dispositivi mobili, Intune
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 08/10/2020
ms.topic: conceptual
f1.keywords:
- NOCSH
ms.prod: microsoft-365-enterprise
ms.service: ''
ms.technology: ''
ms.assetid: fb4182e6-5e78-45d0-9641-d791c4519441
audience: ITPro
ms.custom: microsoft-intune
description: La roadmap per configurare la gestione dei dispositivi per Microsoft 365.
ms.openlocfilehash: 1a1bdb449aa1d1ba12cf1de422b3e279df6c1376
ms.sourcegitcommit: 19515d787246d38c4e0da579a767ce67b9dbc2bc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/31/2020
ms.locfileid: "47315742"
---
# <a name="device-management-roadmap-for-microsoft-365"></a>Roadmap per la gestione dei dispositivi per Microsoft 365


Microsoft 365 per Enterprise include funzionalità che consentono di gestire i dispositivi e le relative app all'interno dell'organizzazione. La gestione dei dispositivi mobili consente di proteggere le risorse dell'organizzazione e di proteggerle.

Sono disponibili due opzioni per la gestione dei dispositivi.

## <a name="microsoft-intune"></a>Microsoft Intune

Intune offre opzioni per la gestione dell'accesso all'organizzazione tramite la gestione dei dispositivi mobili (MDM) o la gestione delle applicazioni mobili (MAM). MDM è il momento in cui gli utenti "iscrivono" i propri dispositivi in Intune. Una volta registrati, sono dispositivi gestiti e possono ricevere tutti i criteri, le regole e le impostazioni utilizzate dall'organizzazione. Ad esempio, è possibile installare app specifiche, creare un criterio password, installare una connessione VPN e altro ancora.

Gli utenti che dispongono di dispositivi personali potrebbero non voler registrare i propri dispositivi o essere gestiti da Intune e dai criteri. Tuttavia, è comunque necessario proteggere le risorse e i dati dell'organizzazione. In questo scenario, è possibile proteggere le app utilizzando MAM. Ad esempio, è possibile utilizzare un criterio MAM che richiede a un utente di immettere un PIN quando si accede a SharePoint nel dispositivo.

È inoltre possibile determinare come gestire i dispositivi personali o di proprietà dell'organizzazione. È possibile che si desideri gestire i dispositivi in modo diverso, a seconda dell'utilizzo. 

Iniziare da [qui](https://docs.microsoft.com/mem/intune/fundamentals/planning-guide).

## <a name="basic-mobility-and-security"></a>Mobilità e sicurezza di base
 
Questa funzionalità è integrata in Microsoft 365 e consente di proteggere e gestire i dispositivi mobili degli utenti, ad esempio iPhone, iPad, Android e Windows Phone. È possibile creare e gestire criteri di sicurezza, cancellare tutti i dati in remoto e visualizzare report dettagliati sui dispositivi. 

Iniziare da [qui](https://support.microsoft.com/office/set-up-basic-mobility-and-security-dd892318-bc44-4eb1-af00-9db5430be3cd).
 
## <a name="identity-and-device-access-recommendations"></a>Consigli sull’identità e sull’accesso dei dispositivi

Microsoft offre una serie di consigli per [identità e accesso ai dispositivi](microsoft-365-policies-configurations.md) per garantire un ambiente di lavoro protetto e produttivo. Per l'accesso ai dispositivi, utilizzare i suggerimenti e le impostazioni disponibili in questi articoli:

- [Prerequisiti](identity-access-prerequisites.md)
- [Criteri comuni di identità e accesso dei dispositivi](identity-access-policies.md)

## <a name="how-contoso-did-device-management-for-microsoft-365"></a>Informazioni su come Contoso ha eseguito la gestione dei dispositivi per Microsoft 365

Vedere come Contoso Corporation, un'azienda multinazionale fittizia ma rappresentativa, ha [distribuito l'infrastruttura di gestione dei dispositivi mobili](contoso-mdm.md) con i servizi cloud di Microsoft 365.
