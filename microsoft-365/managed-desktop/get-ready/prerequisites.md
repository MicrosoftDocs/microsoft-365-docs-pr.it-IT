---
title: Prerequisiti per Microsoft Managed Desktop
description: Licenze, account di Azure, impostazioni di autenticazione e impostazioni di Microsoft 365 da configurare prima di eseguire la registrazione in Microsoft Managed Desktop
keywords: Microsoft Managed Desktop, Microsoft 365, servizi, documentazione
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 79ae949d9624021121492edb811a4ea5bfcc729a
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659141"
---
# <a name="prerequisites-for-microsoft-managed-desktop"></a>Prerequisiti per Microsoft Managed Desktop

<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/prereq-azure); do not delete.-->
<!--from Prerequisites -->

In questo argomento vengono illustrati i requisiti dell'infrastruttura che è necessario soddisfare per garantire il successo con Microsoft Managed Desktop. 


Area | Dettagli dei prerequisiti
--- | ---
Licenze |Microsoft Managed Desktop richiede la licenza Microsoft 365 E3 con Microsoft Defender per endpoint e Azure Active Directory Premium 2 (o equivalenti).<br>Per informazioni dettagliate sui piani di servizio specifici, vedere [altre informazioni sulle licenze](#more-about-licenses) in questo argomento.<br>Per ulteriori informazioni sulle licenze disponibili, vedere [Microsoft 365 Licensing](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans).
Connettività |  Tutti i dispositivi Microsoft Managed Desktop richiedono la connettività a numerosi endpoint dei servizi Microsoft dalla rete aziendale.<br><br>Per l'elenco completo degli indirizzi IP e degli URL necessari, vedere [configurazione di rete](../get-ready/network.md). 
Azure Active Directory |    Azure Active Directory (Azure AD) deve essere l'origine dell'autorità per tutti gli account utente oppure gli account utente devono essere sincronizzati da Active Directory locale utilizzando l'ultima versione supportata di Azure AD Connect.<br><br>Il [roaming dello stato dell'organizzazione](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-overview) deve essere abilitato per gli utenti di Microsoft Managed Desktop.<br><br>Per ulteriori informazioni, vedere [Azure ad Connect](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-azure-ad-connect).<br><br>Per ulteriori informazioni sulle versioni supportate di Azure AD Connect, vedere [Azure ad Connect: Version Release History](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-version-history).
Autenticazione |    Se Azure AD non è l'origine dell'autenticazione primaria per gli account utente, è necessario configurare una di queste in Azure AD Connect:<br>-Sincronizzazione hash delle password<br>-Autenticazione pass-through<br>-Un provider di identità esterno (compresi gli sfollati Windows Server ADFS e non Microsoft) configurati per soddisfare i requisiti di integrazione di Azure AD. Per ulteriori informazioni, vedere le [linee guida](https://www.microsoft.com/download/details.aspx?id=56843) . <br><br>Quando si impostano le opzioni di autenticazione con Azure AD Connect, è consigliato anche il writeback delle password. Per ulteriori informazioni, vedere [writeback delle password](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback). <br><br>Se viene implementato un provider di identità esterno, è necessario convalidare la soluzione:<br>-Soddisfa i requisiti di integrazione di Azure AD<br>-Supporta l'accesso condizionale di Azure AD, che consente di configurare i criteri di conformità del dispositivo desktop Microsoft gestito<br>-Abilita la registrazione dei dispositivi e l'utilizzo di servizi o funzionalità di Microsoft 365 richiesti come parte di Microsoft Managed Desktop <br><br>Per ulteriori informazioni sulle opzioni di autenticazione con Azure AD, vedere [Opzioni di accesso utente di Azure ad Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-user-signin).
Microsoft 365 | OneDrive for business deve essere abilitato per gli utenti di Microsoft Managed Desktop.<br><br>Anche se non è necessario iscriversi con Microsoft Managed Desktop, è consigliabile eseguire la migrazione dei servizi seguenti al cloud:<br>-Posta elettronica: eseguire la migrazione alle cassette postali basate su cloud, Exchange Online o configurare con Exchange Online ibrido con Exchange 2013 o versione successiva, in locale.<br>-File e cartelle: eseguire la migrazione a OneDrive for business o SharePoint Online.<br>-Strumenti di collaborazione online: eseguire la migrazione a teams.
Gestione dei dispositivi | I dispositivi Microsoft Managed Desktop richiedono la gestione tramite Microsoft Intune. È necessario impostare Intune come autorità di gestione dei dispositivi mobili.<br><br>Per ulteriori informazioni, vedere [Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune). 
Backup e ripristino dei dati |  Microsoft Managed Desktop richiede la sincronizzazione dei file in OneDrive for business per la protezione. I file non sincronizzati con OneDrive for business non sono garantiti da Microsoft Managed Desktop e potrebbero essere persi durante gli scambi di dispositivi o di supporto per le chiamate che richiedono il ripristino di un dispositivo.<br><br>Sebbene non sia necessario, Microsoft Managed Desktop consiglia vivamente la migrazione da unità di rete mappate alla soluzione cloud appropriata. Per ulteriori informazioni, vedere [preparare le unità mappate per Microsoft Managed Desktop](mapped-drives.md)

Quando si è pronti per iniziare a utilizzare Microsoft Managed Desktop, contattare il proprio account Manager Microsoft. 

## <a name="more-about-licenses"></a>Altre informazioni sulle licenze

Microsoft Managed Desktop richiede determinate opzioni di licenza per funzionare. Per informazioni sulle modalità di utilizzo di queste licenze, vedere [Microsoft Managed Desktop Technologies](../intro/technologies.md) .

> [!TIP]
> Per assegnare queste opzioni di licenza a utenti specifici, è consigliabile usufruire della [caratteristica di gestione delle licenze basata su gruppo](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal) di Azure Active Directory.

- Azure Active Directory Premium P2
- Microsoft Intune 
- Windows 10 Enterprise  
- Microsoft Defender per endpoint
- Microsoft 365 Apps for enterprise
- Microsoft Teams
- [SharePoint Online piano 2](https://www.microsoft.com/microsoft-365/sharepoint/compare-sharepoint-plans)
- [Exchange Online piano 2](https://www.microsoft.com/microsoft-365/exchange/compare-microsoft-exchange-online-plans) 


> [!TIP]
> Il tuo account Manager Microsoft ti aiuterà a esaminare le licenze e i piani di servizio correnti e a trovare il percorso più efficiente per ottenere qualsiasi licenza o piano di servizio aggiuntivo che potrebbe essere necessario, evitando la duplicazione.
