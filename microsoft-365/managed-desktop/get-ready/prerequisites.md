---
title: Prerequisiti per Microsoft Managed Desktop
description: Licenze, account Azure, impostazioni di autenticazione e impostazioni di Microsoft 365 da configurare prima della registrazione in Microsoft Managed Desktop
keywords: Microsoft Managed Desktop, Microsoft 365, servizio, documentazione
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: e4469d8abcfa8308c64e2efa7f7dc4f0156e5718
ms.sourcegitcommit: b6763a8ab240fbdd56078a7c9452445d0c4b9545
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2021
ms.locfileid: "51957528"
---
# <a name="prerequisites-for-microsoft-managed-desktop"></a>Prerequisiti per Microsoft Managed Desktop

<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/prereq-azure); do not delete.-->
<!--from Prerequisites -->

In questo argomento vengono descritti i requisiti dell'infrastruttura che è necessario soddisfare per garantire il successo con Microsoft Managed Desktop. 


Area | Dettagli prerequisiti
--- | ---
Licenze |Microsoft Managed Desktop richiede la licenza di Microsoft 365 E3 con Microsoft Defender for Endpoint (o equivalenti) assegnata agli utenti.<br>Per informazioni dettagliate sui piani di servizio specifici, vedere [Ulteriori informazioni sulle licenze](#more-about-licenses) in questo argomento.<br>Per ulteriori informazioni sulle licenze disponibili, vedere [Licenze di Microsoft 365.](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans)
Connettività |  Tutti i dispositivi Microsoft Managed Desktop richiedono la connettività a numerosi endpoint di servizio Microsoft dalla rete aziendale.<br><br>Per l'elenco completo degli INDIRIZZI IP e DEGLI URL necessari, vedere [Configurazione di rete.](../get-ready/network.md) 
Azure Active Directory |    Azure Active Directory (Azure AD) deve essere l'origine dell'autorità per tutti gli account utente oppure gli account utente devono essere sincronizzati da Active Directory locale utilizzando la versione più recente supportata di Azure AD Connect.<br><br>[Enterprise State Roaming](/azure/active-directory/devices/enterprise-state-roaming-overview) deve essere abilitato per gli utenti di Microsoft Managed Desktop.<br><br>Per ulteriori informazioni, vedere [Azure AD Connect.](/azure/active-directory/hybrid/whatis-azure-ad-connect)<br><br>Per ulteriori informazioni sulle versioni supportate di Azure AD Connect, vedere [Azure AD Connect:Version release history](/azure/active-directory/hybrid/reference-connect-version-history).
Autenticazione |    Se Azure AD non è l'origine dell'autenticazione principale per gli account utente, è necessario configurarne una in Azure AD Connect:<br>- Sincronizzazione hash password<br>- Autenticazione pass-through<br>- Provider di identità esterno (incluso ADFS di Windows Server e provider di identità non Microsoft) configurato per soddisfare i requisiti di integrazione di Azure AD. Per ulteriori [informazioni, vedere](https://www.microsoft.com/download/details.aspx?id=56843) le linee guida. <br><br>Quando si impostano le opzioni di autenticazione con Azure AD Connect, è consigliabile anche il writeback delle password. Per ulteriori informazioni, vedere [Writeback delle password.](/azure/active-directory/authentication/howto-sspr-writeback) <br><br>Se viene implementato un provider di identità esterno, è necessario convalidare la soluzione:<br>- Soddisfa i requisiti di integrazione di Azure AD<br>- Supporta l'accesso condizionale di Azure AD, che consente di configurare i criteri di conformità dei dispositivi Microsoft Managed Desktop<br>- Abilita la registrazione dei dispositivi e l'uso dei servizi o delle funzionalità di Microsoft 365 necessari come parte di Microsoft Managed Desktop <br><br>Per altre informazioni sulle opzioni di autenticazione con Azure AD, vedi Opzioni di accesso utente [di Azure AD Connect.](/azure/active-directory/connect/active-directory-aadconnect-user-signin)
Microsoft 365 | OneDrive for Business deve essere abilitato per gli utenti di Microsoft Managed Desktop.<br><br>Anche se non è necessario registrarsi con Microsoft Managed Desktop, è consigliabile eseguire la migrazione dei servizi seguenti nel cloud:<br>- Posta elettronica: eseguire la migrazione a cassette postali basate su cloud, Exchange online o configurare con Exchange Online Ibrido con Exchange 2013 o versione successiva, locale.<br>- File e cartelle: eseguire la migrazione a OneDrive for Business o SharePoint Online.<br>- Strumenti di collaborazione online: eseguire la migrazione a Teams.
Gestione dei dispositivi | I dispositivi Microsoft Managed Desktop richiedono la gestione con Microsoft Intune. Intune deve essere impostato come autorità di gestione dei dispositivi mobili.<br><br>Per ulteriori informazioni, vedere [Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune). 
Backup e ripristino dei dati |  Microsoft Managed Desktop richiede la sincronizzazione dei file con OneDrive for Business per la protezione. I file non sincronizzati con OneDrive for Business non sono garantiti da Microsoft Managed Desktop e potrebbero andare persi durante gli scambi di dispositivi o le chiamate di supporto che richiedono la reimpostazione del dispositivo.<br><br>Sebbene non sia obbligatorio, Microsoft Managed Desktop consiglia vivamente di eseguire la migrazione dalle unità di rete mappate alla soluzione cloud appropriata. Per ulteriori informazioni, vedere [Prepare mapped drives for Microsoft Managed Desktop](mapped-drives.md)

Quando sei pronto per iniziare a usare Microsoft Managed Desktop, contatta il tuo Account Manager Microsoft. 

## <a name="more-about-licenses"></a>Altre informazioni sulle licenze

Microsoft Managed Desktop richiede alcune opzioni di licenza per funzionare. Per informazioni sull'utilizzo di queste licenze, vedere Tecnologie Desktop gestito [Microsoft.](../intro/technologies.md)

> [!TIP]
> Per assegnare queste opzioni di licenza a utenti specifici, è consigliabile sfruttare la funzionalità di gestione delle licenze basata su [gruppo](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal) di Azure Active Directory.

- Azure Active Directory Premium P1
- Microsoft Intune 
- Windows 10 Enterprise  
- Microsoft Defender per endpoint
- Microsoft 365 Apps for enterprise
- Microsoft Teams
- [SharePoint Online piano 2](https://www.microsoft.com/microsoft-365/sharepoint/compare-sharepoint-plans)
- [Exchange Online piano 2](https://www.microsoft.com/microsoft-365/exchange/compare-microsoft-exchange-online-plans) 


> [!TIP]
> Microsoft Account Manager consente di esaminare le licenze e i piani di servizio correnti e di trovare il percorso più efficiente per ottenere eventuali licenze aggiuntive o piani di servizio necessari, evitando al contempo la duplicazione.

## <a name="steps-to-get-ready"></a>Passaggi per prepararsi

1. Esaminare [i prerequisiti per Microsoft Managed Desktop](prerequisites.md). (Questo articolo)
2. Utilizzare [gli strumenti di valutazione della conformità](readiness-assessment-tool.md).
3. [Prerequisiti per gli account Guest](guest-accounts.md)
4. [Configurazione rete in Microsoft Managed Desktop](network.md)
5. [Preparare certificati e profili di rete per Microsoft Managed Desktop](certs-wifi-lan.md)
6. [Preparare l'accesso alle risorse locali per Microsoft Managed Desktop](authentication.md)
7. [App in Microsoft Managed Desktop](apps.md)
8. [Preparare unità mappate per Microsoft Managed Desktop](mapped-drives.md)
9. [Preparare risorse di stampa per Microsoft Managed Desktop](printing.md)
