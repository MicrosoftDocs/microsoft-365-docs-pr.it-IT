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
ms.openlocfilehash: d359cae62fbd1bf2468ad753670ff8e385d6f25b
ms.sourcegitcommit: cd17328baa58448214487e3e68c37590ab9fd08d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/09/2020
ms.locfileid: "48398962"
---
# <a name="device-management-roadmap-for-microsoft-365"></a>Roadmap per la gestione dei dispositivi per Microsoft 365

Microsoft 365 per Enterprise include funzionalità che consentono di gestire i dispositivi e le relative app all'interno dell'organizzazione. La gestione dei dispositivi mobili consente di proteggere le risorse dell'organizzazione e di proteggerle.

Sono disponibili due opzioni per la gestione dei dispositivi:

- [Microsoft Intune](#microsoft-intune)
- [Mobilità e sicurezza di base](#basic-mobility-and-security)

## <a name="microsoft-intune"></a>Microsoft Intune

È possibile utilizzare Microsoft Intune per gestire l'accesso all'organizzazione tramite la gestione dei dispositivi mobili o la gestione delle applicazioni mobili. La gestione dei dispositivi mobili è quella in cui gli utenti "iscrivono" i propri dispositivi in Intune. Dopo la registrazione di un dispositivo, si tratta di un dispositivo gestito. Pertanto, è in grado di ricevere i criteri, le regole e le impostazioni dell'organizzazione. Ad esempio, è possibile installare app specifiche, creare un criterio password, installare una connessione VPN e altro ancora.

Gli utenti che dispongono di dispositivi personali potrebbero non voler registrare i propri dispositivi o essere gestiti da Intune e dai criteri dell'organizzazione. Tuttavia, è comunque necessario proteggere le risorse e i dati dell'organizzazione. In questo scenario, è possibile proteggere le app utilizzando la gestione delle applicazioni per dispositivi mobili. Ad esempio, è possibile utilizzare un criterio di gestione delle applicazioni per dispositivi mobili che richiede a un utente di immettere un PIN quando si accede a SharePoint Online sul dispositivo.

È inoltre possibile determinare come gestire i dispositivi personali e i dispositivi di proprietà dell'organizzazione. Potrebbe essere opportuno trattare i dispositivi in modo diverso, a seconda dell'utilizzo.

## <a name="basic-mobility-and-security"></a>Mobilità e sicurezza di base

Questa funzionalità è integrata in Microsoft 365 e consente di proteggere e gestire i dispositivi mobili degli utenti, ad esempio iPhone, iPad, Android e Windows Phone. È possibile creare e gestire criteri di sicurezza, cancellare tutti i dati in remoto e visualizzare report dettagliati sui dispositivi.

## <a name="choose-between-the-two-options"></a>Scegliere tra le due opzioni

Per una migliore valutazione dell'opzione di gestione dei dispositivi, vedere [scegliere tra Basic Mobility Security e Intune](https://docs.microsoft.com/office365/securitycompliance/choose-between-mdm-and-intune).

In base alla valutazione, iniziare a gestire i dispositivi con:

- [Intune](https://docs.microsoft.com/mem/intune/fundamentals/planning-guide).
- [Mobilità e sicurezza di base](https://support.microsoft.com/office/set-up-basic-mobility-and-security-dd892318-bc44-4eb1-af00-9db5430be3cd).
 
## <a name="identity-and-device-access-recommendations"></a>Consigli sull’identità e sull’accesso dei dispositivi

Microsoft offre una serie di consigli per [identità e accesso ai dispositivi](../security/office-365-security/microsoft-365-policies-configurations.md) per garantire un ambiente di lavoro protetto e produttivo. Per l'accesso ai dispositivi, utilizzare i suggerimenti e le impostazioni disponibili in questi articoli:

- [Prerequisiti](../security/office-365-security/identity-access-prerequisites.md)
- [Criteri comuni di identità e accesso dei dispositivi](../security/office-365-security/identity-access-policies.md)

## <a name="how-contoso-did-device-management-for-microsoft-365"></a>Informazioni su come Contoso ha eseguito la gestione dei dispositivi per Microsoft 365

Per informazioni su come un'azienda multinazionale fittizia ma rappresentativa ha distribuito l'infrastruttura di gestione dei dispositivi mobili con i servizi cloud di Microsoft 365, vedere [gestione dei dispositivi mobili per contoso](contoso-mdm.md).
