---
title: Prerequisiti per Microsoft Managed Desktop
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, Service, documentazione
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 6595b6496c8fb2e71542b6aae9f35e4f40c08aa4
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/14/2019
ms.locfileid: "36981717"
---
# <a name="prerequisites-for-microsoft-managed-desktop"></a>Prerequisiti per Microsoft Managed Desktop

<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/prereq-azure); do not delete.-->
<!--from Prerequisites -->

In questo argomento vengono illustrati i requisiti dell'infrastruttura che è necessario soddisfare per garantire il successo con Microsoft Managed Desktop. 

Microsoft FastTrack è disponibile per aiutarti a soddisfare questi requisiti e a prepararti a partecipare a Microsoft Managed Desktop. Per ulteriori informazioni, vedere [Microsoft FastTrack](https://fasttrack.microsoft.com/about). 

Area | Dettagli dei prerequisiti
--- | ---
Licenze |Microsoft Managed Desktop richiede una delle seguenti licenze Microsoft 365 (o equivalenti):<br>-Microsoft 365 E5<br>-Microsoft 365 E3 con il componente aggiuntivo per la sicurezza di Microsoft 365 E5<br><br>Per informazioni dettagliate sui piani di servizio specifici e sul relativo ruolo in Microsoft Managed Desktop, vedere [altre informazioni sulle licenze](#more-about-licenses) in questo argomento.<br>Per ulteriori informazioni sulle licenze disponibili, vedere [Microsoft 365 Licensing](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans).
Connettività |  Tutti i dispositivi Microsoft Managed Desktop richiedono la connettività a numerosi endpoint dei servizi Microsoft dalla rete aziendale.<br><br>Per l'elenco completo degli indirizzi IP e degli URL necessari, vedere [configurazione di rete](../get-ready/network.md). 
Azure Active Directory |    Azure Active Directory (Azure AD) deve essere l'origine dell'autorità per tutti gli account utente oppure gli account utente devono essere sincronizzati da Active Directory locale utilizzando l'ultima versione supportata di Azure AD Connect.<br><br>Il [roaming dello stato dell'organizzazione](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-overview) deve essere abilitato per gli utenti di Microsoft Managed Desktop.<br><br>Per ulteriori informazioni, vedere [Azure ad Connect](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-azure-ad-connect).<br><br>Per ulteriori informazioni sulle versioni supportate di Azure AD Connect, vedere [Azure ad Connect: Version Release History](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-version-history).
Autenticazione |    Se Azure AD non è l'origine dell'autorità per gli account utente, è necessario configurare uno di questi in Azure AD Connect:<br>-Sincronizzazione hash delle password<br>-Autenticazione pass-through<br>-Federazione con ADFS<br><br>Quando si impostano le opzioni di autenticazione con Azure AD Connect, è consigliato anche il writeback delle password. Per ulteriori informazioni, vedere [writeback delle password](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback). <br><br>Per ulteriori informazioni sulle opzioni di autenticazione con Azure AD, vedere [Opzioni di accesso utente di Azure ad Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-user-signin).
Office 365 |    OneDrive for business deve essere abilitato per gli utenti di Microsoft Managed Desktop.<br><br>Anche se non è necessario iscriversi con Microsoft Managed Desktop, è consigliabile eseguire la migrazione dei servizi seguenti al cloud:<br>-Posta elettronica: eseguire la migrazione alle cassette postali basate su cloud, Exchange Online o configurare con Exchange Online ibrido con Exchange 2013 o versione successiva, in locale.<br>-File e cartelle: eseguire la migrazione a OneDrive for business o SharePoint Online.<br>-Strumenti di collaborazione online: eseguire la migrazione a teams.
Gestione dei dispositivi | I dispositivi Microsoft Managed Desktop richiedono la gestione tramite Microsoft Intune. È necessario impostare Intune come autorità di gestione dei dispositivi mobili.<br><br>Per ulteriori informazioni, vedere [Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune). 
Backup e ripristino dei dati | Microsoft Managed Desktop richiede la sincronizzazione dei file in OneDrive for business per la protezione. I file non sincronizzati con OneDrive for business non sono garantiti da Microsoft Managed Desktop e potrebbero essere persi durante gli scambi di dispositivi o di supporto per le chiamate che richiedono il ripristino di un dispositivo.<br><br>Sebbene non sia necessario, Microsoft Managed Desktop consiglia vivamente la migrazione da unità di rete mappate alla soluzione cloud appropriata. Per ulteriori informazioni, vedere [preparare le unità mappate per Microsoft Managed Desktop](mapped-drives.md)

Quando si è pronti per iniziare a utilizzare Microsoft Managed Desktop, contattare il proprio account Manager Microsoft. 

## <a name="more-about-licenses"></a>Altre informazioni sulle licenze

Microsoft Managed Desktop richiede determinate opzioni di licenza per funzionare. Queste opzioni sono disponibili in vari bundle di licenza, alcuni dei quali potrebbero essere già proprietari. In questa tabella sono riportate le opzioni disponibili, in cui vengono riepilogate le licenze e il loro ruolo in Microsoft Managed Desktop.

> [!TIP]
> Per assegnare queste opzioni di licenza a utenti specifici, è consigliabile usufruire della [caratteristica di gestione delle licenze basata su gruppo](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal) di Azure Active Directory.



|Opzione di licenza |Disponibile in *uno qualsiasi* di questi prodotti di licenza |Utilizzo di Microsoft Managed Desktop|
|-------------|-------------|-------------|
|Azure Active Directory Premium P1     |-Microsoft 365 E5<br>-Componente aggiuntivo per la sicurezza di Microsoft 365 E3 + Microsoft 365 *E5*<br>-Enterprise Mobility + Security E5<br>-Enterprise Mobility + Security E3<br>-Azure Active Directory Premium P1|  Fornisce l'accesso ai servizi cloud Microsoft; consente di registrare i dispositivi in Autopilot      |
|Microsoft Intune | -Microsoft 365 E5<br>-Componente aggiuntivo per la sicurezza di Microsoft 365 E3 + Microsoft 365 *E5*<br>-Enterprise Mobility + Security E5<br>-Enterprise Mobility + Security E3<br>-Microsoft Intune  |  Necessario per registrare i dispositivi, distribuire gli aggiornamenti e gestire i dispositivi       |
|Windows 10 Enterprise  |-Microsoft 365 E5<br>-Componente aggiuntivo per la sicurezza di Microsoft 365 E3 + Microsoft 365 *E5*<br>-Windows 10 Enterprise E3<br>-Windows 10 Enterprise E5 | Fornisce le caratteristiche dell'organizzazione di Windows 10       |
|Protezione avanzata dalle minacce di Microsoft Defender | -Microsoft 365 E5<br>-Componente aggiuntivo per la sicurezza di Microsoft 365 E3 + Microsoft 365 *E5*<br>-Windows 10 Enterprise E5<br>-Protezione avanzata dalle minacce di Microsoft Defender   |  Fornisce il rilevamento, il monitoraggio, l'avviso e la risposta alle minacce  |
|Office 365 ProPlus  |-Microsoft 365 E5<br>-Microsoft 365 E3<br>-Office 365 E5<br>-Office 365 E3| Attiva gli strumenti di Office e di produttività e collaborazione    |

> [!TIP]
> Il tuo account Manager Microsoft ti aiuterà a esaminare le licenze e i piani di servizio correnti e a trovare il percorso più efficiente per ottenere qualsiasi licenza o piano di servizio aggiuntivo che potrebbe essere necessario, evitando la duplicazione.