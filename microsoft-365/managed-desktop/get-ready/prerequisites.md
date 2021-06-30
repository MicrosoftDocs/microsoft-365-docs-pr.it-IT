---
title: Prerequisiti per Microsoft Managed Desktop
description: Licenze, account Azure, impostazioni di autenticazione e impostazioni Microsoft 365 da configurare prima della registrazione in Microsoft Managed Desktop
keywords: Microsoft Managed Desktop, Microsoft 365, servizio, documentazione
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 31077b3ffbddb78ecac8841c22c77fa75f6e2c32
ms.sourcegitcommit: 99e67bfe1d677c2f51712b05dcc54908b343cf6f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/29/2021
ms.locfileid: "53203089"
---
# <a name="prerequisites-for-microsoft-managed-desktop"></a>Prerequisiti per Microsoft Managed Desktop

<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/prereq-azure); do not delete.-->
<!--from Prerequisites -->

In questo argomento vengono descritti i requisiti dell'infrastruttura che è necessario soddisfare per garantire il successo con Microsoft Managed Desktop. 


Area | Dettagli prerequisiti
--- | ---
Licenze |Microsoft Managed Desktop richiede la licenza Microsoft 365 E3 con Microsoft Defender for Endpoint (o equivalenti) assegnata agli utenti.<br>Per informazioni dettagliate sui piani di servizio specifici, vedere [Ulteriori informazioni sulle licenze](#more-about-licenses) in questo argomento.<br>Per ulteriori informazioni sulle licenze disponibili, vedere [Microsoft 365 licenze](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans).
Connettività |  Tutti Microsoft Managed Desktop dispositivi richiedono la connettività a numerosi endpoint di servizio Microsoft dalla rete aziendale.<br><br>Per l'elenco completo degli INDIRIZZI IP e DEGLI URL necessari, vedere [Configurazione di rete.](../get-ready/network.md) 
Azure Active Directory |    Azure Active Directory (Azure AD) deve essere l'origine dell'autorità per tutti gli account utente oppure gli account utente devono essere sincronizzati da Active Directory locale utilizzando la versione più recente supportata di Azure AD Connessione.<br><br>Per ulteriori informazioni, vedere [Azure AD Connessione](/azure/active-directory/hybrid/whatis-azure-ad-connect).<br><br>Per ulteriori informazioni sulle versioni di Azure AD Connessione supportate, vedere [Azure AD Connessione:Version release history](/azure/active-directory/hybrid/reference-connect-version-history).
Autenticazione |    Se Azure AD non è l'origine dell'autenticazione principale per gli account utente, è necessario configurarne una in Azure AD Connessione:<br>- Sincronizzazione hash password<br>- Autenticazione pass-through<br>- Un provider di identità esterno (incluso Windows Server ADFS e IDP non Microsoft) configurato per soddisfare i requisiti di integrazione di Azure AD. Per ulteriori [informazioni, vedere](https://www.microsoft.com/download/details.aspx?id=56843) le linee guida. <br><br>Quando si impostano le opzioni di autenticazione con Azure AD Connessione, è consigliabile anche il writeback delle password. Per ulteriori informazioni, vedere [Writeback delle password.](/azure/active-directory/authentication/howto-sspr-writeback) <br><br>Se viene implementato un provider di identità esterno, è necessario convalidare la soluzione:<br>- Soddisfa i requisiti di integrazione di Azure AD<br>- Supporta l'accesso condizionale di Azure AD, che consente Microsoft Managed Desktop criteri di conformità del dispositivo da configurare<br>- Abilita la registrazione dei dispositivi e l'uso di Microsoft 365 o funzionalità necessarie come parte di Microsoft Managed Desktop <br><br>Per altre informazioni sulle opzioni di autenticazione con Azure AD, vedi Opzioni di accesso Connessione utente [di Azure AD.](/azure/active-directory/connect/active-directory-aadconnect-user-signin)
Microsoft 365 | OneDrive for Business deve essere abilitato per Microsoft Managed Desktop utenti.<br><br>Anche se non è necessario eseguire la registrazione con Microsoft Managed Desktop, è consigliabile eseguire la migrazione dei servizi seguenti nel cloud:<br>- Posta elettronica: eseguire la migrazione alle cassette postali basate su cloud, Exchange online o configurare con Exchange Online Hybrid con Exchange 2013 o versione successiva, locale.<br>- File e cartelle: eseguire la migrazione a OneDrive for Business o SharePoint Online.<br>- Strumenti di collaborazione online: eseguire la migrazione a Teams.
Gestione dei dispositivi | Microsoft Managed Desktop dispositivi richiedono la gestione tramite Microsoft Intune. Intune deve essere impostato come autorità di gestione dei dispositivi mobili.<br><br>Per ulteriori informazioni, vedere [Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune). 
Backup e ripristino dei dati |  Microsoft Managed Desktop i file devono essere sincronizzati con OneDrive for Business per la protezione. Tutti i file non sincronizzati con OneDrive for Business non sono garantiti da Microsoft Managed Desktop e potrebbero andare persi durante gli scambi di dispositivi o le chiamate di supporto che richiedono la reimpostazione del dispositivo.<br><br>Anche se non è necessario, Microsoft Managed Desktop la migrazione dalle unità di rete mappate alla soluzione cloud appropriata. Per ulteriori informazioni, vedere [Prepare mapped drives for Microsoft Managed Desktop](mapped-drives.md)

Quando sei pronto per iniziare a usare Microsoft Managed Desktop, contatta il tuo Account Manager Microsoft. 

## <a name="more-about-licenses"></a>Altre informazioni sulle licenze

Microsoft Managed Desktop alcune opzioni di licenza per funzionare. Vedere [Microsoft Managed Desktop tecnologie per](../intro/technologies.md) informazioni sull'utilizzo di queste licenze.

> [!TIP]
> Per assegnare queste opzioni di licenza a utenti [](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal) specifici, è consigliabile sfruttare la funzionalità di gestione delle licenze basata su gruppo di Azure Active Directory.

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
