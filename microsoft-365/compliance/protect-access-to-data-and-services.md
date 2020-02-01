---
title: Proteggere l'accesso di utenti e dispositivi
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 4/17/2018
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a6ef28a4-2447-4b43-aae2-f5af6d53c68e
description: pagina di destinazione per la protezione dell'accesso ai dati e ai servizi di O365
ms.openlocfilehash: eec1963f73b4b1e014f3605ae8fc5afee4ae039b
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "41601703"
---
# <a name="protect-user-and-device-access"></a>Proteggere l'accesso di utenti e dispositivi

La protezione dell'accesso ai dati e ai servizi di Office 365 è cruciale per la difesa da attacchi cibernetici e per la protezione dalla perdita di dati. Le stesse protezioni possono essere applicate ad altre applicazioni SaaS nell'ambiente e persino alle applicazioni locali pubblicate con il proxy di applicazione di Azure Active Directory.
  
## <a name="step-1-review-recommendations"></a>Passaggio 1: esaminare i suggerimenti

Funzionalità consigliate per proteggere le identità e i dispositivi che accedono a Office 365, ad altri servizi SaaS e ad applicazioni locali pubblicate con proxy di applicazione Azure AD.
  
[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [Altre lingue](https://www.microsoft.com/download/details.aspx?id=55032)
  
## <a name="step-2-protect-administrator-accounts-and-access"></a>Passaggio 2: proteggere gli account di amministratore e l'accesso
Gli account amministrativi utilizzati per amministrare l'ambiente di Office 365 includono privilegi elevati. Questi sono obiettivi validi per hacker e cyberattackers. 

Iniziare utilizzando solo gli account amministratore per l'amministrazione. Gli amministratori devono disporre di un account utente distinto per l'utilizzo regolare e non amministrativo e utilizzare il proprio account amministrativo solo quando necessario per completare un'attività associata alla loro funzione processi.

Proteggere gli account di amministratore con l'autenticazione a più fattori e l'accesso condizionale. Per ulteriori informazioni, vedere [protecting Administrator Accounts](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-prerequisites#protecting-administrator-accounts). 

Successivamente, configurare la gestione degli accessi con privilegi in Office 365. La gestione degli accessi con privilegi consente il controllo di accesso granulare sulle attività amministrative privilegiate in Office 365. Può aiutare a proteggere l'organizzazione da violazioni che possono utilizzare gli account di amministrazione privilegiati esistenti con accesso permanente ai dati sensibili o l'accesso alle impostazioni di configurazione critiche.

- [Panoramica della gestione degli accessi con privilegi](privileged-access-management-overview.md)
- [Configurare la gestione degli accessi con privilegi](privileged-access-management-configuration.md)

Un'altra raccomandazione principale consiste nell'utilizzare le workstation appositamente configurate per il lavoro amministrativo. Si tratta di dispositivi dedicati che vengono utilizzati solo per le attività amministrative. Vedere [protezione dell'accesso con privilegi](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/securing-privileged-access).

Infine, è possibile ridurre l'impatto della mancanza di accesso amministrativo accidentale creando due o più account di accesso di emergenza nel tenant. Vedere [gestire gli account di accesso per gli interventi di emergenza in Azure ad](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access). 

## <a name="step-3-configure-recommended-identity-and-device-access-policies"></a>Passaggio 3: configurare i criteri di identità e accesso ai dispositivi consigliati
L'autenticazione a più fattori e i criteri di accesso condizionale sono strumenti potenti per attenuare gli account compromessi e gli accessi non autorizzati. È consigliabile implementare un insieme di criteri che sono stati testati insieme. Per ulteriori informazioni, incluse le procedure di distribuzione, vedere [Identity and Device Access Configurations](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-policies-configurations).

 Questi criteri implementano le funzionalità seguenti:
- Autenticazione a più fattori
- Accesso condizionale
- Protezione delle app di Intune (app e protezione dei dati per i dispositivi)
- Conformità del dispositivo Intune
- Azure AD Identity Protection

L'implementazione della conformità del dispositivo Intune richiede la registrazione del dispositivo. La gestione dei dispositivi consente di assicurarsi che siano integre e conformi prima di consentire loro di accedere alle risorse nell'ambiente in uso. Vedere [registrazione dei dispositivi per la gestione in Intune](https://docs.microsoft.com/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)

## <a name="step-4-configure-sharepoint-device-access-policies"></a>Passaggio 4: configurare i criteri di accesso ai dispositivi di SharePoint

Microsoft consiglia di proteggere il contenuto nei siti di SharePoint con contenuti sensibili e altamente regolamentati con i controlli di accesso ai dispositivi. Per ulteriori informazioni, vedere [consigli sui criteri per la protezione di siti e file di SharePoint](https://docs.microsoft.com/microsoft-365/enterprise/sharepoint-file-access-policies).



    

