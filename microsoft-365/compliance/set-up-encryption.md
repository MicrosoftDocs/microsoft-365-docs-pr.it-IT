---
title: Configurare la crittografia in Office 365 Enterprise
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 4/2/2018
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e86fc991-0161-4f01-9c1c-d25e87733d06
description: Con Office 365, alcune funzionalità di crittografia sono attivate per impostazione predefinita; altre funzionalità possono essere configurate per soddisfare determinati requisiti di conformità o legali.
ms.openlocfilehash: 268bd7b57884549b7ab4abb45a7b69485498f1cb
ms.sourcegitcommit: 89636f35b0194986f156302fc1bb96af25d4805b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/18/2020
ms.locfileid: "44799991"
---
# <a name="set-up-encryption-in-office-365-enterprise"></a>Configurare la crittografia in Office 365 Enterprise

La crittografia può proteggere il contenuto dalla lettura da parte di utenti non autorizzati. Poiché [la crittografia in Office 365](encryption.md) può essere eseguita con diversi metodi e tecnologie, non esiste un'unica posizione in cui attivare o configurare la crittografia. In questo articolo vengono fornite informazioni sui diversi modi in cui è possibile impostare o configurare la crittografia nell'ambito della strategia di protezione delle informazioni.
  
> [!TIP]
> Per ulteriori dettagli tecnici sulla crittografia, vedere Informazioni di riferimento tecniche sulla crittografia [in Office 365.](technical-reference-details-about-encryption.md)
  
Con Office 365, per impostazione predefinita sono disponibili diverse funzionalità di crittografia. È possibile configurare ulteriori funzionalità di crittografia per soddisfare determinati requisiti di conformità o legali. Nella tabella seguente vengono descritti diversi metodi di crittografia per scenari diversi.
  
|**Scenario**|**Metodi di crittografia**|
|:-----|:-----|
|I file vengono salvati nei computer Windows  <br/> |La crittografia a livello di computer può essere eseguita usando BitLocker nei dispositivi Windows. In quanto amministratore aziendale o professionista IT, puoi configurarla usando Microsoft Deployment Toolkit (MDT). Vedi [Configurare MDT per BitLocker.](https://go.microsoft.com/fwlink/?linkid=849282)  <br/> |
|I file vengono salvati nei dispositivi mobili  <br/> |Alcuni tipi di dispositivi mobili crittografano i file salvati in tali dispositivi per impostazione predefinita. Con le funzionalità di gestione dei dispositivi mobili integrata per [Office 365,](https://support.microsoft.com/en-us/office/capabilities-of-built-in-mobile-device-management-for-microsoft-365-a1da44e5-7475-4992-be91-9ccec25905b0)è possibile impostare criteri che determinano se consentire ai dispositivi mobili di accedere ai dati in Office 365. Ad esempio, è possibile impostare un criterio che consenta solo ai dispositivi che crittografano il contenuto di accedere ai dati di Office 365. Vedi [Creare e distribuire i criteri di sicurezza dei dispositivi.](https://support.microsoft.com/office/create-and-deploy-device-security-policies-d310f556-8bfb-497b-9bd7-fe3c36ea2fd6)  <br/> Per un controllo aggiuntivo sul modo in cui i dispositivi mobili interagiscono con Office 365, è possibile prendere in considerazione l'aggiunta [di Microsoft Intune.](https://docs.microsoft.com/mem/intune/fundamentals/setup-steps)  <br/> |
|È necessario controllare le chiavi di crittografia utilizzate per crittografare i dati nei data center Microsoft  <br/> | Gli amministratori di Office 365 possono controllare le chiavi di crittografia dell'organizzazione e quindi configurare Office 365 per usarle per crittografare i dati in stato di inquieto nei data center di Microsoft.  <br/> [Crittografia del servizio con Customer Key in Office 365](customer-key-overview.md) <br/> |
|Le persone comunicano tramite posta elettronica (Exchange Online)  <br/> | Come amministratore di Exchange Online, sono disponibili diverse opzioni per configurare la crittografia della posta elettronica. Ad esempio:  <br/>  Uso [della crittografia dei messaggi di Office 365 (OME)](set-up-new-message-encryption-capabilities.md) con Azure Rights Management (Azure RMS) per consentire agli utenti di inviare messaggi crittografati all'interno o all'esterno dell'organizzazione  <br/>  Utilizzo [di S/MIME per la firma e la crittografia](https://aka.ms/c6dozg) dei messaggi per crittografare e firmare digitalmente i messaggi di posta elettronica  <br/>  Utilizzo di TLS per [configurare i connettori per il flusso di posta sicuro con un'altra organizzazione](https://aka.ms/hs809p) <br/>  Vedere [Crittografia della posta elettronica in Office 365.](https://aka.ms/hic3f7)  <br/> |
|Accesso ai file da siti del team o raccolte documenti (OneDrive for Business o SharePoint Online)  <br/> |Quando gli utenti lavorano con i file salvati in OneDrive for Business o SharePoint Online, vengono utilizzate le connessioni TLS. Questo è incorporato in Office 365 automaticamente. Vedere [Crittografia dei dati in OneDrive for Business e SharePoint Online.](https://go.microsoft.com/fwlink/?linkid=526379)  <br/> |
|I file vengono condivisi nelle riunioni online e nelle conversazioni di messaggistica istantanea (Skype for Business online)  <br/> |Quando gli utenti lavorano con i file con Skype for Business online, viene usato TLS per la connessione. Questo è incorporato in Office 365 automaticamente. Vedere [Sicurezza e archiviazione (Skype for Business online).](https://aka.ms/nuq4ws)  <br/> |
|I file vengono condivisi nelle riunioni online e nelle conversazioni di messaggistica istantanea (Microsoft Teams)  <br/> |Quando gli utenti usano i file con Microsoft Teams, per la connessione viene usato TLS. Questo è incorporato in Office 365 automaticamente. Microsoft Teams attualmente non supporta il rendering inline della posta elettronica crittografata. Per impedire che la posta elettronica crittografata sia in arrivo in Microsoft Teams come crittografata, vedere [Domande frequenti sulla crittografia dei messaggi.](https://docs.microsoft.com/microsoft-365/compliance/ome-faq?view=o365-worldwide#can-i-automatically-remove-encryption-on-incoming-and-outgoing-mail)  <br/> 

## <a name="additional-information"></a>Informazioni aggiuntive

Per ulteriori informazioni sulle soluzioni di protezione dei file che includono opzioni di crittografia, vedere [Soluzioni di protezione dei file in Office 365.](https://www.microsoft.com/download/details.aspx?id=55523)
 
