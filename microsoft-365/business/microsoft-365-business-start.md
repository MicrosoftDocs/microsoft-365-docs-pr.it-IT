---
title: Introduzione a Microsoft 365 per le aziende
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 496e690b-b75d-4ff5-bf34-cc32905d0364
description: Informazioni su Microsoft 365 per le aziende, su come configurarlo e su come preparare i dispositivi e i PC degli utenti per assicurarsi che siano protetti da Microsoft 365 per le aziende.
ms.openlocfilehash: ec50036f589cfd8497b0e7e9af6519b30d25dcd3
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/29/2020
ms.locfileid: "47306490"
---
# <a name="get-started-with-microsoft-365-for-business"></a>Introduzione a Microsoft 365 per le aziende

## <a name="what-is-microsoft-365-for-business"></a>Che cos'è Microsoft 365 per le aziende

Microsoft 365 per le aziende è un set completo di strumenti di produttività e collaborazione aziendali, come Outlook, Word, Excel e altri prodotti Office, sempre aggiornati. Puoi proteggere i file di lavoro in tutti i dispositivi iOS, Android e Windows 10 con una sicurezza di livello aziendale semplice da gestire.

Guardare questo video per una rapida panoramica di Microsoft 365 per le aziende.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2mhaA] 
  
Microsoft 365 per le aziende è pensato per un massimo di 300 licenze. Se occorrono più licenze, vedere la documentazione di [Microsoft 365 Enterprise](https://go.microsoft.com/fwlink/p/?linkid=860986) per maggiori informazioni. 
  
## <a name="get-microsoft-365-for-business"></a>Ottenere Microsoft 365 per le aziende

- If you have a partner, they'll get Microsoft 365 for business: [Get Microsoft 365 for business from Microsoft Partner Center.](get-microsoft-365-business.md)
    
- Se non si ha un partner e si vuole ottenere Microsoft 365 per le aziende, è possibile [acquistarlo qui.](https://www.microsoft.com/microsoft-365/business)
    
## <a name="set-up-microsoft-365-for-business"></a>Configurare Microsoft 365 per le aziende

 **Panoramica della configurazione di Microsoft 365 for business Suite**
  
Il diagramma seguente descrive come gli amministratori configurano Microsoft 365 per le aziende. Vengono inoltre descritti i passaggi per preparare i PC Windows per Microsoft 365 per le aziende. È anche possibile aggiungere nuovi dispositivi nell'interfaccia di amministrazione di Microsoft 365 [con Windows AutoPilot.](add-autopilot-devices-and-profile.md) È possibile usare AutoPilot per configurare e pre-configurare i nuovi dispositivi in modo che siano pronti per l'uso produttivo non appena un utente accede con le credenziali di Microsoft 365 per le aziende.
  
![A diagram that shows the setup and management flow for admins, and also for a user](../media/249f81fc-7e79-44c7-8425-3a0b7b651c3b.png)

Guardare questo video per una panoramica della configurazione di Microsoft 365 per le aziende.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FYSM] 

Se il video è stato utile, consultare la [serie dei corsi di formazione completa per piccole imprese e nuovi utenti di Microsoft 365](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816).

  
### <a name="1-set-up-microsoft-365-for-business-admin"></a>1: Configurare Microsoft 365 per le aziende (amministratore)

Accedere all'interfaccia di amministrazione di [Microsoft 365](https://portal.office.com/adminportal/home) con le credenziali di amministratore globale e completare la procedura seguente per configurare Microsoft 365 per le aziende. 
  
1. [Prerequisiti per la protezione dei dati nei dispositivi con Microsoft 365 per le aziende](pre-requisites-for-data-protection.md)
    
    Leggere prima i prerequisiti per assicurarsi che i dispositivi siano pronti per Microsoft 365 per le aziende.
    
2. [Usare la configurazione guidata per configurare Microsoft 365 per le aziende](set-up.md)
    
    Se si sta passando in modo permanente da Active Directory locale al **cloud,** è possibile passare all'interfaccia di amministrazione di Microsoft 365 e usare la configurazione guidata per aggiungere manualmente gli utenti oppure è possibile eseguire una sincronizzazione una sola volta con Azure AD Connect. Questa operazione può essere eseguita in due modi: 
    
    - Se si dispone anche di un server Exchange 2010, Exchange 2013 o Exchange 2016, è possibile utilizzare l'ambiente ibrido minimo per eseguire rapidamente la migrazione delle cassette postali di Exchange a [Microsoft 365.](https://docs.microsoft.com/Exchange/mailbox-migration/use-minimal-hybrid-to-quickly-migrate) I passaggi ibridi minimi includono una sincronizzazione unica degli utenti con Azure AD e la migrazione della posta elettronica dall'ambiente locale al cloud. Al termine della migrazione della posta elettronica, la sincronizzazione della directory viene disattivata automaticamente quando si utilizza questo metodo.
    
    - Usare la sincronizzazione guidata della directory per sincronizzare gli utenti con il cloud. Seguire i passaggi descritti in [Configurare la sincronizzazione della directory per Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization) per completare questo processo. Dopo aver sincronizzato gli utenti nel cloud, è necessario disattivare la sincronizzazione [della directory per Microsoft 365.](https://docs.microsoft.com/microsoft-365/enterprise/turn-off-directory-synchronization)
    
    Dovrai anche assegnare a ogni utente aggiunto in questo modo una licenza a Microsoft 365 per le aziende. È possibile eseguire questa operazione nella [configurazione guidata](set-up.md) oppure [assegnare licenze agli utenti.](../admin/manage/assign-licenses-to-users.md)
    
### <a name="2-prepare-mobile-devices"></a>2: Preparare i dispositivi mobili

Seguire i passaggi descritti in Configurare i dispositivi mobili per gli utenti di [Microsoft 365 per](set-up-mobile-devices.md) le aziende per installare le app di Office nei dispositivi e assicurarsi che siano protetti da Microsoft 365 per le aziende. 
  
### <a name="3-prepare-pcs"></a>3: Preparare i PC

Gli amministratori possono pre-selezionare le impostazioni per i nuovi PC Windows 10 tramite [Windows AutoPilot.](add-autopilot-devices-and-profile.md) Gli utenti possono configurare i dispositivi Windows 10 esistenti o nuovi seguendo la procedura descritta in questo argomento: Configurare i PC Windows per gli utenti di [Microsoft 365 per le aziende.](set-up-windows-devices.md) Per i dispositivi esistenti, gli utenti **possono facoltativamente spostare** [i file in OneDrive for Business.](move-files-to-onedrive.md) Possono anche usare strumenti di terze parti per spostare i file associati al profilo Windows in OneDrive.
  
Se l'organizzazione usa Windows Server Active Directory in locale, è possibile configurare Microsoft 365 per le aziende per proteggere i dispositivi Windows 10, mantenendo comunque l'accesso alle risorse locali che richiedono l'autenticazione locale. Seguire i passaggi descritti in Abilitare i dispositivi Windows 10 aggiunti a un dominio a essere gestiti da [Microsoft 365 per le aziende](manage-windows-devices.md) per configurare questa funzionalità. Questo metodo è preferibile e i dispositivi in questo stato sono denominati dispositivi aggiunti **ad Azure AD ibrido.** 
  
Se si conserva un ambiente Active Directory locale che contiene alcune risorse locali (ad esempio condivisioni file e stampanti), è possibile concedere ai dispositivi aggiunti ad **Azure AD** l'accesso a queste risorse seguendo la procedura seguente: Accedere alle risorse locali da un dispositivo aggiunto ad Azure AD in [Microsoft 365 per le aziende.](access-resources.md)
  
  
## <a name="contact-support"></a>Contattare il supporto

 **Se è necessario contattare il supporto:**
  
- Contattare il partner.
    
- Gli amministratori di Microsoft 365 per le aziende hanno accesso al team di supporto dei clienti: contattare il supporto per i prodotti per le aziende **[- Guida per gli amministratori](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products)**
    
## <a name="see-also"></a>Vedere anche

[Documentazione e risorse di Microsoft 365 per le aziende](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
[Gestire Microsoft 365 per le aziende](manage.md)[Eseguire la migrazione a Microsoft 365 per le aziende](migrate-to-microsoft-365-business.md)

[Video di formazione su Microsoft 365 per le aziende](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816) 
