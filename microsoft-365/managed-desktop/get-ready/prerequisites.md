---
title: Prerequisiti per Microsoft Managed Desktop
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, Service, documentazione
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 6351dd4696ed21b177dc2789b18c380fba4ebe91
ms.sourcegitcommit: 6b5370cded5d8259c9ed561eed324227f74c410b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/03/2019
ms.locfileid: "36171726"
---
# <a name="prerequisites-for-microsoft-managed-desktop"></a>Prerequisiti per Microsoft Managed Desktop

<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/prereq-azure); do not delete.-->
<!--from Prerequisites -->

In questo argomento vengono illustrati i requisiti dell'infrastruttura che è necessario soddisfare per garantire il successo con Microsoft Managed Desktop. 

Microsoft FastTrack è disponibile per aiutarti a soddisfare questi requisiti e a prepararti a partecipare a Microsoft Managed Desktop. Per ulteriori informazioni, vedere [Microsoft FastTrack](https://fasttrack.microsoft.com/about). 

Area | Dettagli dei prerequisiti
--- | ---
Licenze |Microsoft Managed Desktop richiede una delle seguenti licenze Microsoft 365 (o equivalenze):<br>-Microsoft 365 E5<br>-Microsoft 365 E3 con il componente aggiuntivo per la sicurezza di Microsoft 365 E5<br><br>Per ulteriori informazioni sulle licenze disponibili, vedere [Microsoft 365 Licensing](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans).
Connettività |  Tutti i dispositivi Microsoft Managed Desktop richiedono la connettività a numerosi endpoint dei servizi Microsoft dalla rete aziendale.<br><br>Per l'elenco completo degli indirizzi IP e degli URL necessari, vedere [configurazione di rete](../get-ready/network.md). 
Azure Active Directory |    Azure Active Directory (Azure AD) deve essere l'origine dell'autorità per tutti gli account utente oppure gli account utente devono essere sincronizzati da Active Directory locale utilizzando l'ultima versione supportata di Azure AD Connect.<br><br>Il [roaming dello stato dell'organizzazione](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-overview) deve essere abilitato per gli utenti di Microsoft Managed Desktop.<br><br>Per ulteriori informazioni su Azure AD Connect, vedere [Azure ad Connect](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-azure-ad-connect).<br><br>Per ulteriori informazioni sulle versioni supportate di Azure AD Connect, vedere [Azure ad Connect: Version Release History](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-version-history).
Autenticazione |    Se Azure AD non è l'origine dell'autorità per gli account utente, è necessario configurare uno di questi in Azure AD Connect:<br>-Sincronizzazione hash delle password<br>-Autenticazione pass-through<br>-Federazione con ADFS<br><br>Quando si impostano le opzioni di autenticazione con Azure AD Connect, è consigliato anche il writeback delle password. Per ulteriori informazioni, vedere [writeback delle password](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback). <br><br>Per ulteriori informazioni sulle opzioni di autenticazione con Azure AD, vedere [Opzioni di accesso utente di Azure ad Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-user-signin).
Office 365 |    OneDrive for business deve essere abilitato per gli utenti di Microsoft Managed Desktop.<br><br>Anche se non è necessario iscriversi con Microsoft Managed Desktop, è consigliabile eseguire la migrazione dei servizi seguenti al cloud:<br>-Posta elettronica: eseguire la migrazione alle cassette postali basate su cloud, Exchange Online o configurare con Exchange Online ibrido con Exchange 2013 o versione successiva, in locale.<br>-File e cartelle: eseguire la migrazione a OneDrive for business o SharePoint Online.<br>-Strumenti di collaborazione online: eseguire la migrazione a teams.
Gestione dei dispositivi | I dispositivi Microsoft Managed Desktop richiedono la gestione tramite Microsoft Intune. È necessario impostare Intune come autorità di gestione dei dispositivi mobili.<br><br>Per ulteriori informazioni, vedere [Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune). 
Backup e ripristino dei dati | Microsoft Managed Desktop richiede la sincronizzazione dei file in OneDrive for business per la protezione. I file non sincronizzati con OneDrive for business non sono garantiti da Microsoft Managed Desktop e potrebbero essere persi durante gli scambi di dispositivi o di supporto per le chiamate che richiedono il ripristino di un dispositivo.<br><br>Sebbene non sia necessario, Microsoft Managed Desktop consiglia vivamente la migrazione da unità di rete mappate alla soluzione cloud appropriata. 

Quando si è pronti per iniziare a utilizzare Microsoft Managed Desktop, contattare il proprio account Manager Microsoft. 
