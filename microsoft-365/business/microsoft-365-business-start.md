---
title: Introduzione a Microsoft 365 Business
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
search.appverid:
- BCS160
- MET150
ms.assetid: 496e690b-b75d-4ff5-bf34-cc32905d0364
description: Informazioni su come configurare Microsoft 365 business.
ms.openlocfilehash: 5491486c2bf8da1ee38fcd986d5ecd682d57c82e
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42065613"
---
# <a name="get-started-with-microsoft-365-business"></a>Introduzione a Microsoft 365 Business

## <a name="what-is-microsoft-365-business"></a>Che cos'è Microsoft 365 business

Microsoft 365 business è un set completo di strumenti per la produttività e la collaborazione aziendali, come Outlook, Word, Excel e altri prodotti Office, che sono sempre aggiornati. È possibile proteggere i file di lavoro su tutti i dispositivi iOS, Android e Windows 10 con sicurezza di livello aziendale semplice da gestire.

Guardare questo video per una breve panoramica di Microsoft 365 business.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2mhaA] 
  
Microsoft 365 business è destinato a un massimo di 300 licenze. Per ulteriori informazioni, vedere documentazione relativa a [Microsoft 365 Enterprise](https://go.microsoft.com/fwlink/p/?linkid=860986) . 
  
## <a name="get-microsoft-365-business"></a>Ottenere Microsoft 365 Business

- Se si ha un partner, otterranno Microsoft 365 business: [ottenere microsoft 365 business da Microsoft Partner Center](get-microsoft-365-business.md).
    
- Se non si dispone di un partner e si desidera ottenere Microsoft 365 business, è possibile [acquistarlo qui](https://www.microsoft.com/microsoft-365/business).
    
## <a name="set-up-microsoft-365-business"></a>Configurare Microsoft 365 Business

 **Panoramica di Microsoft 365 business suite set up**
  
Nel diagramma seguente viene illustrato il modo in cui gli amministratori hanno configurato Microsoft 365 business. Illustra anche la procedura per preparare i PC Windows per Microsoft 365 Business. È inoltre possibile aggiungere nuovi dispositivi nell'interfaccia di amministrazione di Microsoft 365 business con [Windows Autopilot](add-autopilot-devices-and-profile.md). È possibile utilizzare Autopilot per impostare e preconfigurare nuovi dispositivi in modo che siano pronti per l'utilizzo produttivo non appena un utente accede con le proprie credenziali di Microsoft 365 business.
  
![A diagram that shows the setup and management flow for admins, and also for a user](../media/249f81fc-7e79-44c7-8425-3a0b7b651c3b.png)

Guardare questo video per una panoramica della configurazione di Microsoft 365 business.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FYSM] 

Se il video è stato utile, consultare la [serie di formazione completa per piccole imprese e nuovi utenti di Microsoft 365](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).

  
### <a name="1-set-up-microsoft-365-business-admin"></a>1: configurare Microsoft 365 business (amministratore)

Accedere a [microsoft 365 Business Admin Center](https://portal.office.com/adminportal/home) con le credenziali di amministratore globale e completare i passaggi seguenti per configurare Microsoft 365 business. 
  
1. [Prerequisiti per la protezione dei dati nei dispositivi con Microsoft 365 business](pre-requisites-for-data-protection.md)
    
    Leggere prima i prerequisiti per assicurarsi che i dispositivi siano pronti per Microsoft 365 business.
    
2. [Utilizzo dell'installazione guidata per configurare Microsoft 365 business](set-up.md)
    
    Se si sta **spostando definitivamente da una Active Directory locale al cloud**, è possibile accedere all'interfaccia di amministrazione di Microsoft 365 business e utilizzare l'installazione guidata per aggiungere manualmente gli utenti oppure è possibile eseguire una sincronizzazione una tantum con Azure ad Connect. Questa operazione può essere eseguita in due modi: 
    
    - Se si dispone anche di un server Exchange 2010, Exchange 2013 o Exchange 2016, è possibile [utilizzare un ambiente ibrido minimo per eseguire rapidamente la migrazione delle cassette postali di Exchange a Office 365](https://support.office.com/article/fdecceed-0702-4af3-85be-f2a0013937ef). I passaggi ibridi minimi includono una sincronizzazione una tantum degli utenti in Azure AD e la migrazione della posta elettronica da locale al cloud. Una volta completata la migrazione della posta elettronica, la sincronizzazione della directory viene disattivata automaticamente quando si utilizza questo metodo.
    
    - Utilizzare la procedura guidata di sincronizzazione della directory di Office 365 per sincronizzare gli utenti con il cloud. Per completare questo processo, seguire i passaggi descritti in [Configurare la sincronizzazione della directory per Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846). Dopo aver sincronizzato gli utenti nel cloud, è necessario disattivare la [sincronizzazione della directory per Office 365](https://support.office.com/article/ee5f861e-bd48-4267-83d1-a4ead4b4a00d).
    
    È inoltre necessario fornire a ciascun utente aggiunto in questo modo una licenza a Microsoft 365 business. È possibile eseguire questa operazione nell' [installazione guidata](set-up.md) oppure è possibile [assegnare licenze agli utenti in Office 365 for business](https://support.office.com/article/997596B5-4173-4627-B915-36ABAC6786DC).
    
### <a name="2-prepare-mobile-devices"></a>2: preparare i dispositivi mobili

Seguire la procedura descritta in [set up mobile devices for Microsoft 365 business users](set-up-mobile-devices.md) per installare le app di Office nei dispositivi e assicurarsi che siano protette da Microsoft 365 business. 
  
### <a name="3-prepare-pcs"></a>3: preparare i PC

Gli amministratori possono preselezionare le impostazioni per i nuovi PC Windows 10 utilizzando [Windows Autopilot](add-autopilot-devices-and-profile.md). Gli utenti possono configurare i dispositivi Windows 10 esistenti o nuovi attenendosi alla procedura descritta in questo argomento: [configurare i PC Windows per gli utenti aziendali di Microsoft 365](set-up-windows-devices.md). Per i dispositivi esistenti, gli utenti possono **facoltativamente** [spostare i file in OneDrive for business](move-files-to-onedrive.md). Possono anche utilizzare strumenti di terze parti per spostare i file associati al profilo di Windows in OneDrive.
  
Se l'organizzazione utilizza Windows Server Active Directory in locale, è possibile configurare Microsoft 365 business per proteggere i dispositivi Windows 10, mantenendo comunque l'accesso alle risorse locali che richiedono l'autenticazione locale. Seguire la procedura descritta in [Enable domain-joined Windows 10 devices to be managed by Microsoft 365 business](manage-windows-devices.md) to set this up. Questo metodo è preferito e i dispositivi in questo stato sono denominati **dispositivi ibridi di Azure ad Uniti**. 
  
Se si conserva un Active Directory locale che contiene alcune risorse locali (ad esempio condivisioni di file e stampanti), è possibile consentire ai **dispositivi di Azure ad-join** di accedere a tali risorse attenendosi alla procedura seguente: [accedere alle risorse locali da un dispositivo di Azure ad-join in Microsoft 365 business](access-resources.md).
  
  
## <a name="contact-support"></a>Contattare il supporto

 **Se è necessario contattare il supporto:**
  
- Contattare il partner.
    
- In qualità di amministratore di Microsoft 365 business, è possibile accedere al team di supporto clienti: ** [contattare il supporto tecnico per i prodotti aziendali-Guida per gli amministratori](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)**
    
## <a name="see-also"></a>Vedere anche

[Documentazione e risorse su Microsoft 365 Business](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
Gestire la migrazione di [microsoft 365 business](manage.md)[a Microsoft 365 business](migrate-to-microsoft-365-business.md)

[Video per la formazione di Microsoft 365 Business](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816) 
