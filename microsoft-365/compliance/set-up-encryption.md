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
description: Con Office 365, alcune funzionalità di crittografia sono attivate per impostazione predefinita. altre funzionalità possono essere configurate per soddisfare determinati requisiti di conformità o legali.
ms.openlocfilehash: 78831446f3d56f64c05ff2f27e376a609bdd6419
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919482"
---
# <a name="set-up-encryption-in-office-365-enterprise"></a>Configurare la crittografia in Office 365 Enterprise

La crittografia può proteggere il contenuto dalla lettura da parte di utenti non autorizzati. Poiché [la crittografia in Office 365](encryption.md) può essere eseguita utilizzando diverse tecnologie e metodi, non esiste un'unica posizione in cui attivare o configurare la crittografia. In questo articolo vengono fornite informazioni sui vari modi in cui è possibile impostare o configurare la crittografia nell'ambito della strategia di protezione delle informazioni.
  
> [!TIP]
> Per ulteriori dettagli tecnici sulla crittografia, vedere Informazioni di riferimento tecniche sulla crittografia [in Office 365.](technical-reference-details-about-encryption.md)
  
Con Office 365, per impostazione predefinita sono disponibili diverse funzionalità di crittografia. È possibile configurare ulteriori funzionalità di crittografia per soddisfare determinati requisiti di conformità o legali. Nella tabella seguente vengono descritti diversi metodi di crittografia per scenari diversi.
  
|**Scenario**|**Metodi di crittografia**|
|:-----|:-----|
|I file vengono salvati nei computer Windows  <br/> |La crittografia a livello di computer può essere eseguita usando BitLocker nei dispositivi Windows. In quanto amministratore aziendale o professionista IT, puoi configurarlo usando Microsoft Deployment Toolkit (MDT). Vedi [Configurare MDT per BitLocker.](/windows/deployment/deploy-windows-mdt/set-up-mdt-for-bitlocker)  <br/> |
|I file vengono salvati nei dispositivi mobili  <br/> |Alcuni tipi di dispositivi mobili crittografano i file salvati in tali dispositivi per impostazione predefinita. Con Funzionalità di gestione dei dispositivi mobili integrata per [Office 365,](https://support.microsoft.com/en-us/office/capabilities-of-built-in-mobile-device-management-for-microsoft-365-a1da44e5-7475-4992-be91-9ccec25905b0)è possibile impostare criteri che determinano se consentire ai dispositivi mobili di accedere ai dati in Office 365. Ad esempio, è possibile impostare un criterio che consenta solo ai dispositivi che crittografano il contenuto di accedere ai dati di Office 365. Vedi [Creare e distribuire criteri di sicurezza dei dispositivi.](https://support.microsoft.com/office/create-and-deploy-device-security-policies-d310f556-8bfb-497b-9bd7-fe3c36ea2fd6)  <br/> Per un controllo aggiuntivo sul modo in cui i dispositivi mobili interagiscono con Office 365, è possibile prendere in considerazione l'aggiunta [di Microsoft Intune.](/mem/intune/fundamentals/setup-steps)  <br/> |
|È necessario controllare le chiavi di crittografia utilizzate per crittografare i dati nei data center di Microsoft  <br/> | Gli amministratori di Office 365 possono controllare le chiavi di crittografia dell'organizzazione e quindi configurare Office 365 per usarle per crittografare i dati in pausa nei data center di Microsoft.  <br/> [Crittografia del servizio con Customer Key in Office 365](customer-key-overview.md) <br/> |
|Le persone comunicano tramite posta elettronica (Exchange Online)  <br/> | Come amministratore di Exchange Online, sono disponibili diverse opzioni per configurare la crittografia della posta elettronica. Ad esempio:  <br/>  Utilizzo della crittografia dei messaggi di [Office 365 (OME)](set-up-new-message-encryption-capabilities.md) con Azure Rights Management (Azure RMS) per consentire agli utenti di inviare messaggi crittografati all'interno o all'esterno dell'organizzazione  <br/>  Utilizzo [di S/MIME per la firma e la crittografia dei](../security/office-365-security/s-mime-for-message-signing-and-encryption.md) messaggi per crittografare e firmare digitalmente i messaggi di posta elettronica  <br/>  Utilizzo di TLS per [configurare i connettori per il flusso di posta sicuro con un'altra organizzazione](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner) <br/>  Vedere [Crittografia della posta elettronica in Office 365](./email-encryption.md).  <br/> |
|È possibile accedere ai file da siti del team o raccolte documenti (OneDrive for Business o SharePoint Online)  <br/> |Quando gli utenti lavorano con i file salvati in OneDrive for Business o SharePoint Online, vengono utilizzate le connessioni TLS. Questo è incorporato in Office 365 automaticamente. Vedere [Crittografia dei dati in OneDrive for Business e SharePoint Online.](./data-encryption-in-odb-and-spo.md)  <br/> |
|I file vengono condivisi nelle riunioni online e nelle conversazioni di messaggistica istantanea (Skype for Business online)  <br/> |Quando gli utenti usano i file con Skype for Business online, viene usato TLS per la connessione. Questo è incorporato in Office 365 automaticamente. Vedere [Sicurezza e archiviazione (Skype for Business online).](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-features)  <br/> |
|I file vengono condivisi nelle riunioni online e nelle conversazioni di messaggistica istantanea (Microsoft Teams)  <br/> |Quando gli utenti utilizzano i file con Microsoft Teams, viene utilizzato TLS per la connessione. Questo è incorporato in Office 365 automaticamente. Microsoft Teams attualmente non supporta il rendering in linea della posta elettronica crittografata. Per impedire l'arrivo della posta elettronica crittografata in Microsoft Teams come crittografata, vedere [Domande frequenti sulla crittografia dei messaggi](./ome-faq.md?view=o365-worldwide#can-i-automatically-remove-encryption-on-incoming-and-outgoing-mail).  <br/> 

## <a name="additional-information"></a>Ulteriori informazioni

Per ulteriori informazioni sulle soluzioni di protezione dei file che includono opzioni di crittografia, vedere [Soluzioni di protezione dei file in Office 365.](https://www.microsoft.com/download/details.aspx?id=55523)
