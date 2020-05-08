---
title: Introduzione a Microsoft 365 for business
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- TRN_SMB
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- TRN_M365B
- OKR_SMB_Videos
- seo-marvel-mar
search.appverid:
- BCS160
- MET150
ms.assetid: 496e690b-b75d-4ff5-bf34-cc32905d0364
description: Informazioni su Microsoft 365 for business, su come configurarlo e su come preparare i dispositivi e i PC degli utenti per assicurarsi che siano protetti da Microsoft 365 for business.
ms.openlocfilehash: a470f015857117d3cbbc15255e8d815438222509
ms.sourcegitcommit: 46644f9778bc70ab6d62783e0a1e60ba2eccc27f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2020
ms.locfileid: "44165790"
---
# <a name="get-started-with-microsoft-365-for-business"></a>Introduzione a Microsoft 365 for business

## <a name="what-is-microsoft-365-for-business"></a>Che cos'è Microsoft 365 for business

Microsoft 365 for business è un set completo di strumenti di produttività e collaborazione aziendali, come Outlook, Word, Excel e altri prodotti Office, che sono sempre aggiornati. È possibile proteggere i file di lavoro su tutti i dispositivi iOS, Android e Windows 10 con sicurezza di livello aziendale semplice da gestire.

Guardare questo video per una breve panoramica di Microsoft 365 for business.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2mhaA] 
  
Microsoft 365 for business è destinato a un massimo di 300 licenze. Se occorrono più licenze, vedere la documentazione di [Microsoft 365 Enterprise](https://go.microsoft.com/fwlink/p/?linkid=860986) per maggiori informazioni. 
  
## <a name="get-microsoft-365-for-business"></a>Ottenere Microsoft 365 per le aziende

- Se si dispone di un partner, otterranno Microsoft 365 per le aziende: [ottenere microsoft 365 for business da Microsoft Partner Center](get-microsoft-365-business.md).
    
- Se non si dispone di un partner e si desidera ottenere Microsoft 365 for business, è possibile [acquistarlo qui](https://www.microsoft.com/microsoft-365/business).
    
## <a name="set-up-microsoft-365-for-business"></a>Configurare Microsoft 365 per le aziende

 **Panoramica di Microsoft 365 for Business Suite set up**
  
Nel diagramma seguente viene illustrato il modo in cui gli amministratori hanno configurato Microsoft 365 for business. Vengono inoltre descritti i passaggi necessari per preparare i PC Windows per Microsoft 365 for business. È inoltre possibile aggiungere nuovi dispositivi nell'interfaccia di amministrazione di Microsoft 365 con [Windows Autopilot](add-autopilot-devices-and-profile.md). È possibile utilizzare Autopilot per impostare e preconfigurare nuovi dispositivi in modo che siano pronti per l'utilizzo produttivo non appena un utente accede con le proprie credenziali di Microsoft 365 for business.
  
![A diagram that shows the setup and management flow for admins, and also for a user](../media/249f81fc-7e79-44c7-8425-3a0b7b651c3b.png)

Guardare questo video per una panoramica della configurazione di Microsoft 365 per le aziende.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FYSM] 

Se il video è stato utile, consultare la [serie di formazione completa per piccole imprese e nuovi utenti di Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).

  
### <a name="1-set-up-microsoft-365-for-business-admin"></a>1: configurare Microsoft 365 for business (amministratore)

Accedere all'interfaccia di [amministrazione di microsoft 365](https://portal.office.com/adminportal/home) con le credenziali di amministratore globale e completare i passaggi seguenti per configurare Microsoft 365 for business. 
  
1. [Prerequisiti per la protezione dei dati nei dispositivi con Microsoft 365 for business](pre-requisites-for-data-protection.md)
    
    Leggere prima i prerequisiti per assicurarsi che i dispositivi siano pronti per Microsoft 365 for business.
    
2. [Utilizzo dell'installazione guidata per configurare Microsoft 365 for business](set-up.md)
    
    Se si sta **spostando definitivamente da una Active Directory locale al cloud**, è possibile accedere all'interfaccia di amministrazione di Microsoft 365 e utilizzare l'installazione guidata per aggiungere manualmente gli utenti oppure è possibile eseguire una sincronizzazione una tantum con Azure ad Connect. Questa operazione può essere eseguita in due modi: 
    
    - Se si dispone anche di un server Exchange 2010, Exchange 2013 o Exchange 2016, è possibile [utilizzare un ambiente ibrido minimo per eseguire rapidamente la migrazione delle cassette postali di Exchange a Office 365](https://docs.microsoft.com/Exchange/mailbox-migration/use-minimal-hybrid-to-quickly-migrate). I passaggi ibridi minimi includono una sincronizzazione una tantum degli utenti in Azure AD e la migrazione della posta elettronica da locale al cloud. Una volta completata la migrazione della posta elettronica, la sincronizzazione della directory viene disattivata automaticamente quando si utilizza questo metodo.
    
    - Utilizzare la procedura guidata di sincronizzazione della directory per sincronizzare gli utenti con il cloud. Seguire la procedura descritta in [set up Directory Synchronization for Microsoft 365](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization) per completare il processo. Dopo aver sincronizzato gli utenti nel cloud, è necessario disattivare la [sincronizzazione della directory per Office 365](https://docs.microsoft.com/office365/enterprise/turn-off-directory-synchronization).
    
    È inoltre necessario fornire a ciascun utente aggiunto in questo modo una licenza a Microsoft 365 for business. È possibile eseguire questa operazione nell' [installazione guidata](set-up.md) oppure è possibile [assegnare licenze agli utenti in Microsoft 365 for business](https://docs.microsoft.com/microsoft-365/admin/add-users/add-users).
    
### <a name="2-prepare-mobile-devices"></a>2: preparare i dispositivi mobili

Seguire la procedura descritta in [set up mobile devices for Microsoft 365 for Business Users](set-up-mobile-devices.md) per installare le app di Office nei dispositivi e assicurarsi che siano protette da Microsoft 365 for business. 
  
### <a name="3-prepare-pcs"></a>3: preparare i PC

Gli amministratori possono preselezionare le impostazioni per i nuovi PC Windows 10 utilizzando [Windows Autopilot](add-autopilot-devices-and-profile.md). Gli utenti possono configurare i dispositivi Windows 10 esistenti o nuovi attenendosi alla procedura descritta in questo argomento: [configurare i PC Windows per gli utenti di Microsoft 365 per le aziende](set-up-windows-devices.md). Per i dispositivi esistenti, gli utenti possono **facoltativamente** [spostare i file in OneDrive for business](move-files-to-onedrive.md). Possono anche utilizzare strumenti di terze parti per spostare i file associati al profilo di Windows in OneDrive.
  
Se l'organizzazione utilizza Windows Server Active Directory in locale, è possibile configurare Microsoft 365 for business in modo da proteggere i dispositivi Windows 10, mantenendo comunque l'accesso alle risorse locali che richiedono l'autenticazione locale. Seguire la procedura descritta in [Enable domain-joined Windows 10 devices to be managed by Microsoft 365 for business](manage-windows-devices.md) to set this up. Questo metodo è preferito e i dispositivi in questo stato sono denominati **dispositivi ibridi di Azure ad Uniti**. 
  
Se si conserva un Active Directory locale che contiene alcune risorse locali (ad esempio condivisioni di file e stampanti), è possibile consentire ai **dispositivi di Azure ad-join** di accedere a tali risorse attenendosi alla procedura seguente: [accedere alle risorse locali da un dispositivo di Azure ad-join in Microsoft 365 for business](access-resources.md).
  
  
## <a name="contact-support"></a>Contattare il supporto

 **Se è necessario contattare il supporto:**
  
- Contattare il partner.
    
- In qualità di amministratore Microsoft 365 for business, è possibile accedere al team di supporto clienti: ** [contattare il supporto tecnico per i prodotti aziendali-Guida](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products) per gli amministratori**
    
## <a name="see-also"></a>Vedere anche

[Documentazione e risorse su Microsoft 365 per le aziende](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
[Gestire microsoft 365 for business](manage.md)[migrate a Microsoft 365 for business](migrate-to-microsoft-365-business.md)

[Video di formazione su Microsoft 365 per le aziende](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816) 
