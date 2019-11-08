---
title: Introduzione a Microsoft 365 Business
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
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: 496e690b-b75d-4ff5-bf34-cc32905d0364
description: Informazioni su come configurare Microsoft 365 business.
ms.openlocfilehash: 4c744d6a900dba3c11ee51e75602a430268e15bb
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/07/2019
ms.locfileid: "38029105"
---
# <a name="get-started-with-microsoft-365-business"></a>Introduzione a Microsoft 365 Business

## <a name="what-is-microsoft-365-business"></a>Che cos'è Microsoft 365 business

Microsoft 365 Business è un set completo di strumenti per la produttività e la collaborazione aziendali sempre aggiornati, tra cui Outlook, Word, Excel e altri prodotti di Office. È possibile proteggere i file di lavoro in tutti i dispositivi iOS, Android e Windows 10 con sicurezza di livello aziendale semplice da gestire.
  
Microsoft 365 business è destinato a un massimo di 300 licenze, per ulteriori informazioni, vedere [microsoft 365 Enterprise](https://go.microsoft.com/fwlink/p/?linkid=860986) Documentation. 
  
## <a name="get-microsoft-365-business"></a>Ottenere Microsoft 365 Business

- I partner riceveranno Microsoft 365 Business: [Ottenere Microsoft 365 Business dal Centro per i partner Microsoft](get-microsoft-365-business.md).
    
- Se non si dispone di un partner e si desidera ottenere Microsoft 365 business, è possibile [acquistarlo qui](https://www.microsoft.com/microsoft-365/business).
    
## <a name="set-up-microsoft-365-business"></a>Configurare Microsoft 365 Business

 **Panoramica di Microsoft 365 business suite set up**
  
Nel diagramma seguente viene illustrato il modo in cui gli amministratori hanno configurato Microsoft 365 business. Illustra anche la procedura per preparare i PC Windows per Microsoft 365 Business. È anche possibile aggiungere nuovi dispositivi nell'interfaccia di amministrazione di Microsoft 365 Business con [Windows AutoPilot](add-autopilot-devices-and-profile.md). AutoPilot consente di installare e pre-configurare nuovi dispositivi, predisponendoli per l'uso non appena un utente accede con le proprie credenziali di Microsoft 365 Business.
  
![A diagram that shows the setup and management flow for admins, and also for a user](media/249f81fc-7e79-44c7-8425-3a0b7b651c3b.png)
  
### <a name="1-set-up-microsoft-365-business-admin"></a>1: configurare Microsoft 365 business (amministratore)

Accedere all'[interfaccia di amministrazione di Microsoft Business 365](https://portal.office.com/adminportal/home) con le credenziali di amministratore globale e completare la procedura seguente per configurare Microsoft 365 Business. 
  
1. [Prerequisiti per proteggere i dati nei dispositivi con Microsoft 365 Business](pre-requisites-for-data-protection.md)
    
    Leggere prima di tutto i prerequisiti per assicurarsi che i dispositivi siano pronti per Microsoft 365 Business.
    
2. [Configurare Microsoft 365 Business usando la configurazione guidata](set-up.md)
    
    Se si sta **spostando definitivamente da una Active Directory locale al cloud**, è possibile aggiungere gli utenti manualmente nell'interfaccia di amministrazione di Microsoft 365 business utilizzando l'installazione guidata oppure è possibile eseguire una sincronizzazione una tantum con Azure ad Connect. Questa operazione può essere eseguita in due modi: 
    
  - Se si dispone anche di un server Exchange 2010, Exchange 2013 o Exchange 2016, è possibile [utilizzare un ambiente ibrido minimo per eseguire rapidamente la migrazione delle cassette postali di Exchange a Office 365](https://support.office.com/article/fdecceed-0702-4af3-85be-f2a0013937ef). I passaggi con le funzionalità ibride minime includono un'unica sincronizzazione degli utenti in Azure AD e anche la migrazione della posta elettronica dall'ambiente locale al cloud. Al termine della migrazione della posta elettronica, la sincronizzazione della directory viene automaticamente disattivata quando si usa questo metodo.
    
  - Usare la sincronizzazione guidata della directory di Office 365 per sincronizzare gli utenti con il cloud. Per completare questo processo, seguire i passaggi descritti in [Configurare la sincronizzazione della directory per Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846). Dopo avere sincronizzato gli utenti con il cloud, sarà necessario [disattivare la sincronizzazione della directory](https://support.office.com/article/ee5f861e-bd48-4267-83d1-a4ead4b4a00d).
    
    Sarà inoltre necessario assegnare una licenza per Microsoft 365 Business a ogni utente aggiunto in questo modo. È possibile eseguire questa operazione nell' [installazione guidata](set-up.md)o nell'assegnazione delle [licenze agli utenti di Office 365 for business](https://support.office.com/article/997596B5-4173-4627-B915-36ABAC6786DC).
    
### <a name="2-prepare-mobile-devices"></a>2: preparare i dispositivi mobili

Seguire la procedura descritta in[set up mobile devices for Microsoft 365 business users](set-up-mobile-devices.md) per installare le app di Office nei dispositivi e per garantire che siano protette da Microsoft 365 business. 
  
### <a name="3-prepare-pcs"></a>3: preparare i PC

Gli amministratori possono preselezionare le impostazioni per i nuovi dispositivi Windows 10 PC utilizzando [Windows Autopilot](add-autopilot-devices-and-profile.md). Gli utenti possono configurare i dispositivi Windows 10 esistenti o nuovi attenendosi alla procedura descritta in questo argomento: [configurare i PC Windows per gli utenti aziendali di Microsoft 365](set-up-windows-devices.md). Per gli utenti di dispositivi esistenti, **facoltativamente**, è anche possibile[spostare i file in OneDrive for business](move-files-to-onedrive.md). Possono anche utilizzare strumenti di terze parti per spostare i file associati al profilo di Windows in OneDrive.
  
Se l'organizzazione utilizza Windows Server Active Directory in locale, è possibile configurare Microsoft 365 business per proteggere i dispositivi Windows 10, mantenendo comunque l'accesso alle risorse locali che richiedono l'autenticazione locale. Seguire la procedura descritta in [Enable domain-joined Windows 10 devices to be managed by Microsoft 365 business](manage-windows-devices.md) to set this up. Questo è il metodo preferito e i dispositivi in questo stato sono denominati **dispositivi ibridi di Azure ad Uniti**. 
  
Se si conserva un Active Directory locale che contiene alcune risorse locali (ad esempio condivisioni di file e stampanti), è possibile consentire ai **dispositivi di Azure ad-join** di accedere a tali risorse attenendosi alla procedura seguente: [accedere alle risorse locali da un dispositivo di Azure ad-join in Microsoft 365 business](access-resources.md).
  
Dopo aver configurato i PC con Windows 10, è possibile [installare automaticamente Office](auto-install-or-uninstall-office.md) nei dispositivi. 
  
## <a name="contact-support"></a>Contattare il supporto

 **Se è necessario contattare il supporto:**
  
- Contattare il partner.
    
- In qualità di amministratore Microsoft 365 business, è possibile accedere al team di supporto clienti, ** [contattare il supporto tecnico per i prodotti aziendali-Guida per gli amministratori](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)**
    
## <a name="related-topics"></a>Argomenti correlati
[Documentazione e risorse su Microsoft 365 Business](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
Gestire la migrazione di [microsoft 365 business](manage.md)[a Microsoft 365 business](migrate-to-microsoft-365-business.md)
  

