---
title: Prerequisiti per Microsoft Managed Desktop
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, Service, documentazione
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 11/1/2018
ms.collection: M365-modern-desktop
ms.openlocfilehash: 8d9c008af9531bc5b829d248665dc5b58ac6034b
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32277387"
---
# <a name="prerequisites-for-microsoft-managed-desktop"></a>Prerequisiti per Microsoft Managed Desktop

<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/prereq-azure); do not delete.-->
<!--from Prerequisites -->

L'esito positivo di Microsoft Managed Desktop inizia con i requisiti ben noti, documentati e concordati per l'infrastruttura del cliente. In questa sezione vengono descritti i requisiti di infrastruttura. 

Microsoft FastTrack è disponibile per aiutare i clienti a soddisfare questi requisiti e a prepararsi a partecipare a Microsoft Managed Desktop. Per ulteriori informazioni, vedere [Microsoft FastTrack](https://fasttrack.microsoft.com/about). 

Area | Dettagli dei prerequisiti
--- | ---
Licenze | A ogni utente di MMD deve essere assegnata una delle opzioni di licenza seguenti:<br>-Microsoft 365 E5<br>-Microsoft 365 E3, Enterprise Mobility + Security E5 e Windows 10 Enterprise E5<br>-Office 365 E3, Enterprise Mobility + Security E5 e Windows 10 Enterprise E5<br><br>Potrebbe essere necessario seguire le linee guida per abilitare l'attivazione della sottoscrizione di Windows 10 Enterprise nel tenant di Azure AD. Per ulteriori informazioni, vedere [Deploy Windows 10 Enterprise licenses](https://docs.microsoft.com/windows/deployment/deploy-enterprise-licenses#enabling-subscription-activation-with-an-existing-ea).<br><br>Le licenze di prodotto possono essere assegnate utilizzando gruppi di sicurezza mediante la configurazione delle licenze basate su gruppo di Azure AD. Per ulteriori informazioni, vedere [che cos'è il licensing basato su gruppo in Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal).<br><br>Per ulteriori informazioni sulle licenze disponibili, vedere [Microsoft 365 Licensing](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans).
Connettività |  Tutti i dispositivi Microsoft Managed Desktop richiedono la connettività a numerosi endpoint dei servizi Microsoft dalla rete aziendale.<br><br>Per l'elenco completo degli indirizzi IP e degli URL necessari, vedere [configurazione di rete](../get-ready/network.md). 
Azure Active Directory |    Azure Active Directory (Azure AD) deve essere l'origine dell'autorità per tutti gli account utente oppure gli account utente devono essere sincronizzati da Active Directory locale utilizzando l'ultima versione supportata di Azure AD Connect.<br><br>Per ulteriori informazioni su Azure AD Connect, vedere [Azure ad Connect](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-azure-ad-connect).<br><br>Per ulteriori informazioni sulle versioni supportate di Azure AD Connect, vedere [Azure ad Connect: Version Release History](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-version-history).
Autenticazione |    Se Azure AD non è l'origine dell'autorità per gli account utente, è necessario configurare uno di questi in Azure AD Connect:<br>-Sincronizzazione hash delle password<br>-Autenticazione pass-through<br>-Federazione con ADFS<br><br>Quando si impostano le opzioni di autenticazione con Azure AD Connect, è necessario anche il writeback delle password. Per ulteriori informazioni, vedere [writeback delle password](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback). <br><br>Per ulteriori informazioni sulle opzioni di autenticazione con Azure AD, vedere [Opzioni di accesso utente di Azure ad Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-user-signin).
Office 365 |    Anche se non è necessario iscriversi con Microsoft Managed Desktop, è consigliabile eseguire la migrazione dei servizi seguenti al cloud:<br>-Posta elettronica-eseguire la migrazione alle cassette postali basate su cloud, Exchange Online o essere configurate con Exchange Online ibrido con Exchange 2013 o versione successiva, in locale.<br>-File e cartelle: eseguire la migrazione a OneDrive for business/SharePoint Online.<br>-Strumenti di collaborazione online: eseguire la migrazione a teams.
Gestione dei dispositivi | I dispositivi Microsoft Managed Desktop richiedono la gestione tramite Microsoft Intune. È necessario impostare Intune come autorità di gestione dei dispositivi mobili.<br><br>Per ulteriori informazioni, vedere [Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune). 
Backup e ripristino dei dati | Microsoft Managed Desktop richiede la sincronizzazione dei file in OneDrive for business per la protezione. I file non sincronizzati con OneDrive for business non sono garantiti da Microsoft Managed Desktop e possono essere persi durante gli scambi di dispositivi o supportano le chiamate che richiedono un reset del dispositivo.<br><br>Sebbene non sia necessario, Microsoft Managed Desktop consiglia vivamente la migrazione da unità di rete mappate alla soluzione cloud appropriata.  

Quando si è pronti per iniziare a utilizzare Microsoft Managed Desktop, contattare il proprio account Manager Microsoft. 
