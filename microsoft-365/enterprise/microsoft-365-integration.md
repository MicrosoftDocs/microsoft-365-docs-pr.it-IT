---
title: Integrazione di Microsoft 365 con ambienti locali
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.date: 10/08/2019
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.collection:
- Ent_O365
search.appverid:
- MET150
- LYN150
- SPS150
- MOE150
- MED150
ms.assetid: 263faf8d-aa21-428b-aed3-2021837a4b65
description: In questo articolo vengono fornite informazioni su come integrare Microsoft 365 con i servizi directory esistenti e gli ambienti locali.
ms.openlocfilehash: 46f0fab6396dd1db82524ea1aeedc6894ce7ab70
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691516"
---
# <a name="microsoft-365-integration-with-on-premises-environments"></a>Integrazione di Microsoft 365 con ambienti locali

*Questo articolo può essere applicato sia a Microsoft 365 Enterprise che a Office 365 Enterprise.*

È possibile integrare Microsoft 365 con i servizi directory esistenti e con un'installazione locale di Exchange Server, Skype for Business Server 2015 o SharePoint Server.
  
 - Eseguendo l'integrazione con i servizi directory, è possibile sincronizzare e gestire gli account utente di entrambi gli ambienti. È anche possibile aggiungere la sincronizzazione dell'hash delle password o Single Sign-On (SSO) per consentire agli utenti di accedere a entrambi gli ambienti con le proprie credenziali locali.
 - Mediante l'integrazione con i prodotti server locali viene creato un ambiente ibrido. Un ambiente ibrido può essere di aiuto durante la migrazione di utenti o informazioni a Microsoft 365 oppure è possibile continuare ad avere alcuni utenti o alcune informazioni in locale e altre nel cloud. Per altre informazioni sugli ambienti ibridi, vedere [Panoramica sul cloud ibrido](https://docs.microsoft.com/Office365/Enterprise/hybrid-cloud-overview).

È inoltre possibile utilizzare i consulenti di Azure Active Directory (Azure AD) per le istruzioni di installazione personalizzate (è necessario essere connessi a Microsoft 365):

- [Sincronizzare gli utenti dalla directory dell'organizzazione](https://aka.ms/aadconnectpwsync)
- [Assistente distribuzione di AD FS](https://aka.ms/adfsguidance)
- [Guida alla configurazione di Azure AD](https://aka.ms/aadpguidance)
   
## <a name="before-you-begin"></a>Prima di iniziare

Prima di integrare Microsoft 365 e un ambiente locale, è inoltre necessario partecipare alla [pianificazione della rete e all'ottimizzazione delle prestazioni](network-planning-and-performance.md). È anche opportuno conoscere i [modelli di identità](about-microsoft-365-identity.md). 

Vedere [dove gestire gli account di microsoft 365](manage-microsoft-365-accounts.md) per un elenco di strumenti che è possibile utilizzare per gestire gli utenti e gli account di Microsoft 365. 
  
## <a name="integrate-microsoft-365-with-directory-services"></a>Integrazione di Microsoft 365 con i servizi directory
Se si dispone di account utente esistenti in una directory locale, non si vuole ricreare tutti gli account in Microsoft 365 e rischiare di introdurre differenze o errori tra gli ambienti. La sincronizzazione della directory consente di eseguire il mirroring degli account tra l'ambiente online e quello locale. La sincronizzazione della directory evita agli utenti la necessità di ricordare nuove informazioni per ogni ambiente e all'amministratore di creare o aggiornare gli account due volte. Sarà necessario [preparare la directory locale per la](prepare-for-directory-synchronization.md) sincronizzazione della directory.
  
![Usare la sincronizzazione della directory per mantenere sincronizzate le informazioni degli account locali e di quelli online](../media/a64af0d0-9be6-46b1-8727-277e683abf5e.png)
  
Se si desidera che gli utenti siano in grado di accedere a Microsoft 365 con le credenziali locali, è anche possibile configurare SSO. Con SSO, Microsoft 365 è configurato per considerare attendibile l'ambiente locale per l'autenticazione degli utenti.
  
![Con Single Sign-On, lo stesso account è disponibile sia nell'ambiente locale che nell'ambiente online](../media/d76235f2-8a53-405e-b8ef-dfa4cfc208b8.png)
  
Tecniche di gestione degli account utente diverse offrono agli utenti esperienze diverse, come illustrato nella tabella seguente.
 
### <a name="directory-synchronization-with-or-without-password-hash-synchronization-or-pass-through-authentication"></a>Sincronizzazione della directory con o senza sincronizzazione dell'hash delle password o autenticazione pass-through

Un utente accede all'ambiente locale con il proprio account utente (dominio\nomeutente). Quando si accede a Microsoft 365, è necessario eseguire di nuovo l'accesso con l'account aziendale o dell'Istituto di istruzione (user@domain.com). Il nome utente è lo stesso in entrambi gli ambienti. Quando si aggiunge l'autenticazione hash della password o pass-through, l'utente ha la stessa password per entrambi gli ambienti, ma sarà necessario fornire tali credenziali quando si accede a Microsoft 365. La sincronizzazione della directory con la sincronizzazione dell'hash delle password è lo scenario più di frequente.

Per configurare la sincronizzazione della directory, usare Azure Active Directory Connect. Per istruzioni, leggere [configurare la sincronizzazione della directory per Microsoft 365](set-up-directory-synchronization.md)e [Azure ad Connect con le impostazioni Express](https://go.microsoft.com/fwlink/p/?LinkId=698537).

Per ulteriori informazioni, vedere [preparazione della sincronizzazione della directory a Microsoft 365](prepare-for-directory-synchronization.md) e [integrazione delle identificazioni locali con Azure Active Directory](https://go.microsoft.com/fwlink/?LinkId=518101).

### <a name="directory-synchronization-with-sso"></a>Sincronizzazione della directory con SSO

Un utente accede all'ambiente locale con il proprio account utente. Quando si accede a Microsoft 365, sono connessi automaticamente oppure eseguono l'accesso utilizzando le stesse credenziali utilizzate per l'ambiente locale (dominio\nomeutente).

Per configurare SSO si usa anche Azure AD Connect. Per le istruzioni, vedere [Installazione personalizzata di Azure AD Connect](https://go.microsoft.com/fwlink/p/?LinkID=698430).

Vedere [Accesso Single Sign-On alle applicazioni in Azure Active Directory](https://go.microsoft.com/fwlink/p/?LinkId=698604).

## <a name="azure-ad-connect"></a>Azure AD Connect

Azure AD Connect sostituisce le precedenti versioni di strumenti di integrazione delle identità come DirSync e Azure AD Sync. Per altre informazioni, vedere [Che cos'è l'identità ibrida con Azure Active Directory?](https://go.microsoft.com/fwlink/p/?LinkId=527969). Per eseguire l'aggiornamento da Azure Active Directory Sync ad Azure AD Connect, vedere le [istruzioni di aggiornamento](https://go.microsoft.com/fwlink/p/?LinkId=733240). 

Vedere anche [deploy microsoft 365 Directory Synchronization in Microsoft Azure](https://go.microsoft.com/fwlink/?LinkId=517887).

## <a name="see-also"></a>Vedere anche

[Panoramica di Microsoft 365 Enterprise](microsoft-365-overview.md)
