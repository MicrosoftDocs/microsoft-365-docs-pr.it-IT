---
title: Introduzione a Microsoft 365 Business
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.date: 9/20/2018
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_O365
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 496e690b-b75d-4ff5-bf34-cc32905d0364
description: Informazioni su come configurare Microsoft 365 Business.
ms.openlocfilehash: ee15ffa98de032d7936d950124cdf772335949bd
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868681"
---
# <a name="get-started-with-microsoft-365-business"></a>Introduzione a Microsoft 365 Business

## <a name="what-is-microsoft-365-business"></a>Che cos'è Microsoft 365 Business

Microsoft 365 Business è un set completo di strumenti per la produttività e la collaborazione aziendali sempre aggiornati, tra cui Outlook, Word, Excel e altri prodotti di Office. È possibile proteggere i file di lavoro in tutti i dispositivi iOS, Android e Windows 10 con sicurezza di livello aziendale semplice da gestire.
  
Microsoft Business 365 si intende per le licenze fino a 300, se sono necessarie ulteriori licenze, vedere la documentazione [Microsoft 365 Enterprise](https://go.microsoft.com/fwlink/p/?linkid=860986) . 
  
## <a name="get-microsoft-365-business"></a>Ottenere Microsoft 365 Business

- I partner riceveranno Microsoft 365 Business: [Ottenere Microsoft 365 Business dal Centro per i partner Microsoft](get-microsoft-365-business.md).
    
- Se non dispone di un partner e ottenere Microsoft 365 Business, è possibile [acquistarlo qui](https://www.microsoft.com/en-us/microsoft-365/business).
    
## <a name="set-up-microsoft-365-business"></a>Configurare Microsoft 365 Business

 **Panoramica della configurazione di Microsoft 365 Business Suite**
  
Nel diagramma seguente viene descritto come gli amministratori impostare Microsoft 365 Business. Vengono inoltre descritti i passaggi necessari per preparare Windows PC Microsoft 365 Business. È inoltre possibile aggiungere nuovi dispositivi nell'interfaccia di amministrazione di Microsoft Business 365 con [Windows AutoPilot](add-autopilot-devices-and-profile.md). È possibile utilizzare AutoPilot per impostare e pre-configurare nuovi dispositivi, tali operazioni preliminari per l'utilizzo di produttività non appena un utente esegue l'accesso con le proprie credenziali aziendali 365 Microsoft.
  
![A diagram that shows the setup and management flow for admins, and also for a user](media/249f81fc-7e79-44c7-8425-3a0b7b651c3b.png)
  
### <a name="1-set-up-microsoft-365-business-admin"></a>1: configurare Microsoft 365 Business (amministratori)

Accedere all'[interfaccia di amministrazione di Microsoft Business 365](https://portal.office.com/adminportal/home) con le credenziali di amministratore globale e completare la procedura seguente per configurare Microsoft 365 Business. 
  
1. [Prerequisiti per proteggere i dati nei dispositivi con Microsoft 365 Business](pre-requisites-for-data-protection.md)
    
    Leggere prima di tutto i prerequisiti per assicurarsi che i dispositivi siano pronti per Microsoft 365 Business.
    
2. [Configurare Microsoft 365 Business usando la configurazione guidata](set-up.md)
    
    Se si è **in modo permanente lo spostamento da un ambiente Active Directory locale al cloud**, è possibile aggiungere gli utenti manualmente nell'interfaccia di amministrazione di Microsoft 365 Business utilizzando l'installazione guidata oppure è possibile eseguire una sincronizzazione occasionale con Azure Active Directory Connetti. Esistono due modi per eseguire questa operazione: 
    
  - Se si dispone inoltre un Exchange 2010, Exchange 2013 o 2016 di Exchange server, è possibile [Utilizzare ibrida minimo rapidamente la migrazione delle cassette postali di Exchange a Office 365](https://support.office.com/article/fdecceed-0702-4af3-85be-f2a0013937ef). I passaggi ibrida minimo includono una sola volta sincronizzazione agli utenti di Azure Active Directory e su come la migrazione da locale al cloud di posta elettronica. Una volta completata la migrazione della posta elettronica, la sincronizzazione delle directory viene disattivata automaticamente quando si utilizza questo metodo.
    
  - Usare la sincronizzazione guidata della directory di Office 365 per sincronizzare gli utenti con il cloud. Per completare questo processo, seguire i passaggi descritti in [Configurare la sincronizzazione della directory per Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846). Dopo avere sincronizzato gli utenti con il cloud, sarà necessario [disattivare la sincronizzazione della directory](https://support.office.com/article/ee5f861e-bd48-4267-83d1-a4ead4b4a00d).
    
    È inoltre necessario assegnare a ogni utente che è stato aggiunto in questo modo una licenza per Microsoft 365 Business. È possibile farlo dell' [installazione guidata](set-up.md)o [assegnare licenze agli utenti di Office 365 per aziende](https://support.office.com/article/997596B5-4173-4627-B915-36ABAC6786DC).
    
### <a name="2-prepare-mobile-devices"></a>2: preparare i dispositivi mobili

Seguire i passaggi descritti in[configurare i dispositivi mobili per gli utenti aziendali di 365 Microsoft](set-up-mobile-devices.md) per l'installazione di Office apps nei dispositivi e assicurandosi che sono protetti da Microsoft 365 Business. 
  
### <a name="3-prepare-pcs"></a>3: preparazione PC

Gli amministratori possono pre-selezionare le impostazioni per nuovi dispositivi Windows 10 PC con [Windows AutoPilot](add-autopilot-devices-and-profile.md). Gli utenti possono configurare i dispositivi Windows 10 nuovi o esistenti seguendo i passaggi descritti in questo argomento: [impostare i PC per gli utenti aziendali di 365 Microsoft Windows](set-up-windows-devices.md). Per i dispositivi esistenti gli utenti possono inoltre **Se lo si desidera**[spostare i file di OneDrive for Business](move-files-to-onedrive.md). È inoltre possibile utilizzare gli strumenti di terze parti per spostare i file associati al profilo di Windows per OneDrive.
  
Se l'organizzazione utilizza Windows Server Active Directory locale, è possibile impostare Microsoft 365 Business per proteggere i dispositivi Windows 10, mantenendo l'accesso alle risorse locali che richiedono l'autenticazione locale. Seguire i passaggi descritti in [abilitarli per dominio Windows 10 per essere gestiti da Microsoft 365 Business](manage-windows-devices.md) configurazione. Si tratta del metodo preferito e dispositivi questo stato vengono chiamati **ibrida Azure Active Directory appartenente dispositivi**. 
  
Se si mantiene locale Active Directory che contiene alcune risorse (ad esempio condivisioni di file e stampanti) in locale, è possibile fornire accesso di **dispositivi Azure Active Directory appartenente** a queste risorse per la procedura descritta di seguito: [accesso locale risorse da un Dispositivo Azure Active Directory aggiunti in Microsoft 365 Business](access-resources.md).
  
Dopo che sono state impostate Windows 10 PC, è possibile [installare automaticamente Office](auto-install-or-uninstall-office.md) per i dispositivi. 
  
## <a name="contact-support"></a>Contattare il supporto

 **Se è necessario contattare il supporto:**
  
- Contattare il partner.
    
- Come un amministratore di Microsoft 365 Business, si dispone dell'accesso per il team dell'assistenza clienti, ** [contattare il supporto per i prodotti di business - della Guida di amministrazione](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)**
    

