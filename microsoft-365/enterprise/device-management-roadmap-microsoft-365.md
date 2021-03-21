---
title: Roadmap di gestione dei dispositivi per Microsoft 365
keywords: Microsoft 365, Microsoft 365 per le aziende, documentazione di Microsoft 365, gestione dei dispositivi mobili, Intune
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
ms.openlocfilehash: 4c37033898865372fea19ddbb53ec9c8586f27b1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918967"
---
# <a name="device-management-roadmap-for-microsoft-365"></a>Roadmap di gestione dei dispositivi per Microsoft 365

Microsoft 365 per le aziende include funzionalità che consentono di gestire i dispositivi e le relative app all'interno dell'organizzazione. La gestione dei dispositivi mobili consente di proteggere e proteggere le risorse dell'organizzazione.

Esistono due opzioni per la gestione dei dispositivi:

- [Microsoft Intune](#microsoft-intune)
- [Basic Mobility + Security](#basic-mobility-and-security)

## <a name="microsoft-intune"></a>Microsoft Intune

È possibile usare Microsoft Intune per gestire l'accesso all'organizzazione tramite la gestione dei dispositivi mobili o delle applicazioni mobili. La gestione dei dispositivi mobili si verifica quando gli utenti "registrano" i propri dispositivi in Intune. Dopo la registrazione di un dispositivo, si tratta di un dispositivo gestito. pertanto, può ricevere i criteri, le regole e le impostazioni dell'organizzazione. Ad esempio, puoi installare app specifiche, creare criteri password, installare una connessione VPN e altro ancora.

Gli utenti con i propri dispositivi personali potrebbero non voler registrare i propri dispositivi o essere gestiti da Intune e dai criteri dell'organizzazione. È comunque necessario proteggere le risorse e i dati dell'organizzazione. In questo scenario, puoi proteggere le tue app usando la gestione delle applicazioni per dispositivi mobili. Ad esempio, è possibile utilizzare un criterio di gestione delle applicazioni per dispositivi mobili che richiede a un utente di immettere un PIN quando accede a SharePoint Online nel dispositivo.

Determinerai anche come gestire i dispositivi personali e i dispositivi di proprietà dell'organizzazione. Potresti voler trattare i dispositivi in modo diverso, a seconda del loro utilizzo.

## <a name="basic-mobility-and-security"></a>Basic Mobility + Security

Questo è integrato in Microsoft 365 e consente di proteggere e gestire i dispositivi mobili degli utenti come iPhone, iPad, Android e telefoni Windows. È possibile creare e gestire criteri di sicurezza, cancellare tutti i dati in remoto e visualizzare report dettagliati sui dispositivi.

## <a name="choose-between-the-two-options"></a>Scegliere tra le due opzioni

Per valutare meglio l'opzione di gestione dei dispositivi più adatta a te, vedi Scegliere tra [Basic Mobility Security e Intune.](/office365/securitycompliance/choose-between-mdm-and-intune)

In base alla valutazione, inizia a gestire i dispositivi con:

- [Intune](/mem/intune/fundamentals/planning-guide)
- [Basic Mobility + Security](https://support.microsoft.com/office/set-up-basic-mobility-and-security-dd892318-bc44-4eb1-af00-9db5430be3cd)
 
## <a name="identity-and-device-access-recommendations"></a>Consigli sull’identità e sull’accesso dei dispositivi

Microsoft offre una serie di consigli per [identità e accesso ai dispositivi](../security/office-365-security/microsoft-365-policies-configurations.md) per garantire un ambiente di lavoro protetto e produttivo. Per l'accesso ai dispositivi, usa i suggerimenti e le impostazioni in questi articoli:

- [Prerequisiti](../security/office-365-security/identity-access-prerequisites.md)
- [Criteri comuni di identità e accesso dei dispositivi](../security/office-365-security/identity-access-policies.md)

## <a name="how-contoso-did-device-management-for-microsoft-365"></a>Come Contoso ha fatto la gestione dei dispositivi per Microsoft 365

Per informazioni sul modo in cui un'azienda fittizia ma rappresentativa multinazionale ha distribuito l'infrastruttura di gestione dei dispositivi mobili con i servizi cloud di Microsoft 365, vedere Gestione dei dispositivi mobili [per Contoso.](contoso-mdm.md)