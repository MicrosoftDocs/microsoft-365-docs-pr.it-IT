---
title: Introduzione a Microsoft 365 per le aziende
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 496e690b-b75d-4ff5-bf34-cc32905d0364
description: Informazioni su Microsoft 365 per le aziende, su come configurarlo e su come preparare i dispositivi e i PC degli utenti per assicurarsi che siano protetti da Microsoft 365 per le aziende.
ms.openlocfilehash: be5f0e74b71f412bf647e4ef0e496cd932fc306a
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706459"
---
# <a name="get-started-with-microsoft-365-for-business"></a>Introduzione a Microsoft 365 per le aziende

## <a name="what-is-microsoft-365-for-business"></a>Che cos'è Microsoft 365 per le aziende

Microsoft 365 for business è un insieme completo di strumenti di produttività e collaborazione aziendali, ad esempio Outlook, Word, Excel e altri prodotti Office, sempre aggiornati. Puoi proteggere i file di lavoro in tutti i dispositivi iOS, Android e Windows 10 con una sicurezza di livello aziendale semplice da gestire.

## <a name="watch-what-is-microsoft-365-business-premium"></a>Watch: What is Microsoft 365 Business Premium

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2mhaA] 
  
Microsoft 365 per le aziende è destinato a un massimo di 300 licenze. Se occorrono più licenze, vedere la documentazione di [Microsoft 365 Enterprise](../enterprise/index.yml) per maggiori informazioni. 
  
## <a name="get-microsoft-365-for-business"></a>Ottenere Microsoft 365 per le aziende

- If you have a partner, they'll get Microsoft 365 for business: [Get Microsoft 365 for business from Microsoft Partner Center](get-microsoft-365-business.md).
    
- Se non si dispone di un partner e si desidera ottenere Microsoft 365 per le aziende, è possibile [acquistarlo qui.](https://www.microsoft.com/microsoft-365/business)
    
## <a name="set-up-microsoft-365-for-business"></a>Configurare Microsoft 365 per le aziende

 **Panoramica della configurazione Microsoft 365 suite per le aziende**
  
Nel diagramma seguente viene descritto come gli amministratori configurano Microsoft 365 per le aziende. Vengono inoltre descritti i passaggi per preparare Windows PC per Microsoft 365 per le aziende. Puoi anche aggiungere nuovi dispositivi nell'Microsoft 365 di amministrazione con [Windows AutoPilot.](add-autopilot-devices-and-profile.md) Puoi usare AutoPilot per configurare e pre-configurare i nuovi dispositivi in modo che siano pronti per l'uso produttivo non appena un utente accede con le credenziali Microsoft 365 per le aziende.
  
![A diagram that shows the setup and management flow for admins, and also for a user](../media/249f81fc-7e79-44c7-8425-3a0b7b651c3b.png)

## <a name="watch-set-up-microsoft-365-business"></a>Watch: Set up Microsoft 365 Business

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FYSM] 

Se il video è stato utile, consultare la [serie dei corsi di formazione completa per piccole imprese e nuovi utenti di Microsoft 365](../business-video/index.yml).

  
### <a name="1-set-up-microsoft-365-for-business-admin"></a>1: Configurare Microsoft 365 per le aziende (amministratore)

Accedi [all'Microsoft 365 di amministrazione](https://portal.office.com/adminportal/home) con le credenziali di amministratore globale e completa i passaggi seguenti per configurare Microsoft 365 per le aziende. 
  
1. [Prerequisiti per la protezione dei dati nei dispositivi con Microsoft 365 per le aziende](pre-requisites-for-data-protection.md)
    
    Leggere prima i prerequisiti per assicurarsi che i dispositivi siano pronti per Microsoft 365 per le aziende.
    
2. [Utilizzare la configurazione guidata per configurare Microsoft 365 per le aziende](set-up.md)
    
    Se si sta passando in modo permanente da active Directory locale al **cloud,** è possibile passare all'interfaccia di amministrazione di Microsoft 365 e usare la configurazione guidata per aggiungere manualmente gli utenti oppure eseguire una sincronizzazione una sola volta con Azure AD Connessione. È possibile eseguire questa operazione in due modi: 
    
    - Se si dispone anche di un server Exchange 2010, Exchange 2013 o Exchange 2016, è possibile utilizzare [Minimal Hybrid](/Exchange/mailbox-migration/use-minimal-hybrid-to-quickly-migrate)per eseguire rapidamente la migrazione delle cassette postali di Exchange Microsoft 365 . I passaggi ibridi minimi includono una sincronizzazione unica degli utenti con Azure AD e la migrazione della posta elettronica da locale al cloud. Al termine della migrazione della posta elettronica, la sincronizzazione della directory viene disattivata automaticamente quando si utilizza questo metodo.
    
    - Usare la procedura guidata di sincronizzazione della directory per sincronizzare gli utenti nel cloud. Seguire i passaggi descritti in [Set up directory synchronization for Microsoft 365](../enterprise/set-up-directory-synchronization.md) to complete this process. Dopo aver sincronizzato gli utenti nel cloud, è necessario disattivare la sincronizzazione [della directory per Microsoft 365](../enterprise/turn-off-directory-synchronization.md).
    
    Dovrai anche assegnare a ogni utente aggiunto in questo modo una licenza per Microsoft 365 per le aziende. È possibile eseguire questa operazione nella [configurazione guidata](set-up.md) oppure [assegnare licenze agli utenti](../admin/manage/assign-licenses-to-users.md).
    
### <a name="2-prepare-mobile-devices"></a>2: Preparare i dispositivi mobili

Segui i passaggi descritti in Configurare i dispositivi mobili per Microsoft 365 [per](set-up-mobile-devices.md) gli utenti aziendali per installare le app di Office nei dispositivi e assicurarsi che siano protetti da Microsoft 365 per le aziende. 
  
### <a name="3-prepare-pcs"></a>3: Preparare i PC

Gli amministratori possono pre-selezionare le impostazioni per Windows 10 PC Windows [AutoPilot.](add-autopilot-devices-and-profile.md) Gli utenti possono configurare i dispositivi Windows 10 esistenti o nuovi seguendo la procedura descritta in questo argomento: Configurare i PC Windows per Microsoft 365 [per gli utenti aziendali.](set-up-windows-devices.md) Per i dispositivi esistenti, gli utenti **possono facoltativamente spostare** [i file in OneDrive for Business](move-files-to-onedrive.md). Possono anche usare strumenti di terze parti per spostare i file associati Windows profilo OneDrive.
  
Se l'organizzazione usa Windows Server Active Directory locale, è possibile configurare Microsoft 365 per le aziende per proteggere i dispositivi Windows 10, mantenendo comunque l'accesso alle risorse locali che richiedono l'autenticazione locale. Segui i passaggi descritti in [Enable domain-joined Windows 10 devices to be managed by Microsoft 365 for business](manage-windows-devices.md) to set this up. Questo metodo è preferibile e i dispositivi in questo stato sono denominati dispositivi aggiunti **ad Azure AD ibrido.** 
  
Se si conserva un Active Directory locale contenente alcune risorse locali (ad esempio condivisioni file e stampanti), è possibile concedere ai dispositivi aggiunti ad **Azure AD** l'accesso a queste risorse seguendo la procedura seguente: Accedere alle risorse locali da un dispositivo aggiunto [ad Azure AD in Microsoft 365 per le aziende.](access-resources.md)
  
  
## <a name="contact-support"></a>Contattare il supporto

 **Se è necessario contattare il supporto:**
  
- Contattare il partner.
    
- In qualità di Microsoft 365 per le aziende, hai accesso al team di supporto dei clienti: contatta il supporto per i prodotti **[aziendali - Guida per gli amministratori](../business-video/get-help-support.md)**
    
## <a name="related-content"></a>Contenuto correlato

[Microsoft 365 documentazione e risorse per le aziende](./index.yml) (pagina di collegamento)\
[Gestire Microsoft 365 per le aziende](manage.md) (articolo)\
[Eseguire la migrazione a Microsoft 365 per le aziende](migrate-to-microsoft-365-business.md) (articolo)\
[video Microsoft 365 formazione su Microsoft 365](../business-video/index.yml) per le aziende (pagina dei collegamenti)