---
title: Integrazione di Microsoft 365 con ambienti locali
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
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
ms.openlocfilehash: 9c5e287ed4a440d1f62081a4c94e39f0f162b4dc
ms.sourcegitcommit: 11d1044c6600b1f568b6dc8a53db9b07f2f0ad1c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/08/2020
ms.locfileid: "48384881"
---
# <a name="microsoft-365-integration-with-on-premises-environments"></a>Integrazione di Microsoft 365 con ambienti locali

*Questo articolo si applica sia a Microsoft 365 Enterprise che a Office 365 Enterprise*.

È possibile integrare Microsoft 365 con i servizi di dominio Active Directory (AD DS) e con le installazioni locali di Exchange Server, Skype for Business Server 2015 o SharePoint Server.
  
 - Quando si integra servizi di dominio Active Directory, è possibile sincronizzare e gestire gli account utente per entrambi gli ambienti. È inoltre possibile aggiungere la sincronizzazione degli hash delle password (pH) o Single Sign-on (SSO), in modo che gli utenti possano accedere a entrambi gli ambienti con le credenziali locali.
 - Mediante l'integrazione con i prodotti server locali viene creato un ambiente ibrido. Un ambiente ibrido può essere di aiuto durante la migrazione di utenti o informazioni a Microsoft 365 oppure è possibile continuare ad avere alcuni utenti o alcune informazioni in locale e altre nel cloud. Per ulteriori informazioni sugli ambienti ibridi, vedere [cloud ibrido](../solutions/cloud-architecture-models.md#hybrid).

È inoltre possibile utilizzare i consulenti di Azure Active Directory (Azure AD) per le istruzioni di installazione personalizzate nell'interfaccia di amministrazione di Microsoft 365 (è necessario essere connessi a Microsoft 365):

- [Guida alla configurazione di Azure AD](https://aka.ms/aadpguidance)
- [Sincronizzare gli utenti dalla directory dell'organizzazione](https://aka.ms/aadconnectpwsync)
- [Consulente per la distribuzione di Active Directory Federation Services (AD FS)](https://aka.ms/adfsguidance)
   
## <a name="before-you-begin"></a>Informazioni preliminari

Prima di integrare Microsoft 365 e un ambiente locale, è inoltre necessario eseguire la pianificazione della [rete e l'ottimizzazione delle prestazioni](network-planning-and-performance.md). È anche opportuno conoscere i [modelli di identità](about-microsoft-365-identity.md). 

Vedere [gestire gli account microsoft 365](manage-microsoft-365-accounts.md) per un elenco degli strumenti che è possibile utilizzare per gestire gli account utente di Microsoft 365. 
  
## <a name="integrate-microsoft-365-with-ad-ds"></a>Integrazione di Microsoft 365 con servizi di dominio Active Directory

Se si dispone di account utente esistenti in servizi di dominio Active Directory, non si desidera ricreare tutti gli account in Microsoft 365 e rischiare di introdurre differenze o errori tra gli ambienti. La sincronizzazione della directory consente di rispecchiare gli account tra gli ambienti locali e online. La sincronizzazione della directory evita agli utenti la necessità di ricordare nuove informazioni per ogni ambiente e all'amministratore di creare o aggiornare gli account due volte. Sarà necessario [preparare la directory locale per la](prepare-for-directory-synchronization.md) sincronizzazione della directory.
  
![Usare la sincronizzazione della directory per mantenere sincronizzate le informazioni degli account locali e di quelli online](../media/microsoft-365-integration/directory-synchronization.png)
  
Se si desidera che gli utenti siano in grado di accedere a Microsoft 365 con le credenziali locali, è anche possibile configurare SSO. Con SSO, Microsoft 365 è configurato per considerare attendibile l'ambiente locale per l'autenticazione degli utenti.
  
![Con Single Sign-On, lo stesso account è disponibile sia nell'ambiente locale che nell'ambiente online](../media/microsoft-365-integration/single-sign-on.png)

### <a name="directory-synchronization-with-or-without-password-hash-synchronization-or-pass-through-authentication-pta"></a>Sincronizzazione della directory con o senza sincronizzazione dell'hash delle password o autenticazione pass-through (PTA)

Un utente accede all'ambiente locale con il proprio account utente (dominio\nomeutente). Quando si accede a Microsoft 365, è necessario eseguire di nuovo l'accesso con l'account aziendale o dell'Istituto di istruzione (user@domain.com). Il nome utente è lo stesso in entrambi gli ambienti. Quando si aggiungono pH o PTA, l'utente ha la stessa password per entrambi gli ambienti, ma sarà necessario fornire tali credenziali quando si accede a Microsoft 365. La sincronizzazione della directory con pH è la sincronizzazione delle directory più comunemente utilizzata.

Per configurare la sincronizzazione della directory, utilizzare Azure AD Connect. Per istruzioni, vedere [configurare la sincronizzazione della directory per Microsoft 365](set-up-directory-synchronization.md) e [Azure ad Connect with Express Settings](https://go.microsoft.com/fwlink/p/?LinkId=698537).

Per ulteriori informazioni, vedere [preparazione della sincronizzazione della directory a Microsoft 365](prepare-for-directory-synchronization.md).

### <a name="directory-synchronization-with-sso"></a>Sincronizzazione della directory con SSO

Un utente accede all'ambiente locale con il proprio account utente. Quando si accede a Microsoft 365, sono connessi automaticamente oppure eseguono l'accesso utilizzando le stesse credenziali utilizzate per l'ambiente locale (dominio\nomeutente).

Per configurare SSO si usa anche Azure AD Connect. Per istruzioni, vedere [Custom Installation of Azure ad Connect](https://go.microsoft.com/fwlink/p/?LinkID=698430).

Per ulteriori informazioni, vedere [Single Sign-on](https://go.microsoft.com/fwlink/p/?LinkId=698604).

## <a name="azure-ad-connect"></a>Azure AD Connect

Azure AD Connect sostituisce le versioni precedenti degli strumenti di integrazione delle identità, come DirSync e Azure AD Sync. Se si desidera eseguire l'aggiornamento dalla sincronizzazione di Azure Active Directory ad Azure AD Connect, vedere [le istruzioni per l'aggiornamento](https://go.microsoft.com/fwlink/p/?LinkId=733240). 

## <a name="see-also"></a>Vedere anche

[Panoramica di Microsoft 365 Enterprise](microsoft-365-overview.md)
