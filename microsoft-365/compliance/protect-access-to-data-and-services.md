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
description: Informazioni su come proteggere l'accesso di utenti e dispositivi ai dati e ai servizi di Microsoft 365 e difendersi dalla perdita di dati.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 64baa2c9e49a9b24841ec50db3e5592ba3d7d55d
ms.sourcegitcommit: cd17328baa58448214487e3e68c37590ab9fd08d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/09/2020
ms.locfileid: "48399025"
---
# <a name="protect-user-and-device-access"></a>Proteggere l'accesso di utenti e dispositivi

La protezione dell'accesso ai dati e ai servizi di Microsoft 365 è fondamentale per difendersi da attacchi informatici e proteggersi dalla perdita di dati. Le stesse protezioni possono essere applicate ad altre applicazioni SaaS nell'ambiente e anche alle applicazioni locali pubblicate con il proxy di applicazione di Azure Active Directory.
  
## <a name="step-1-review-recommendations"></a>Passaggio 1: esaminare gli elementi consigliati

Funzionalità consigliate per proteggere le identità e i dispositivi che accedono a Office 365, ad altri servizi SaaS e ad applicazioni locali pubblicate con proxy di applicazione Azure AD.
  
[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [Altre lingue](https://www.microsoft.com/download/details.aspx?id=55032)
  
## <a name="step-2-protect-administrator-accounts-and-access"></a>Passaggio 2: Proteggere gli account amministratore e l'accesso
Gli account amministrativi utilizzati per amministrare l'ambiente Microsoft 365 includono privilegi elevati. Si tratta di obiettivi importanti per hacker e cyberattacker. 

Iniziare utilizzando gli account di amministratore solo per l'amministrazione. Gli amministratori devono disporre di un account utente separato per uso normale e non amministrativo e utilizzare il proprio account amministrativo solo se necessario per completare un'attività associata alla funzione lavorativa.

Proteggere gli account amministratore con l'autenticazione a più fattori e l'accesso condizionale. Per ulteriori informazioni, vedere [Protezione degli account amministratore.](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-prerequisites#protecting-administrator-accounts) 

Successivamente, configurare la gestione degli accessi con privilegi in Office 365. La gestione degli accessi privilegiati consente un controllo granulare dell'accesso sulle attività di amministrazione con privilegi in Office 365. Può aiutare a proteggere l'organizzazione da violazioni che potrebbero usare account amministratore con privilegi esistenti con accesso permanente ai dati sensibili o l'accesso alle impostazioni di configurazione critiche.

- [Panoramica della gestione degli accessi con privilegi](privileged-access-management-overview.md)
- [Configurare la gestione degli accessi con privilegi](privileged-access-management-configuration.md)

Un altro elemento consigliato è l'utilizzo di workstation configurate in modo specifico per il lavoro amministrativo. Si tratta di dispositivi dedicati usati solo per le attività amministrative. Vedere [Protezione dell'accesso con privilegi.](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/securing-privileged-access)

Infine, è possibile ridurre l'impatto della mancanza accidentale di accesso amministrativo creando due o più account di accesso di emergenza nel tenant. Vedi [Gestire gli account di accesso per gli interventi di emergenza in Azure AD.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access) 

## <a name="step-3-configure-recommended-identity-and-device-access-policies"></a>Passaggio 3: Configurare i criteri di identità e accesso dei dispositivi consigliati
L'autenticazione a più fattori (MFA) e i criteri di accesso condizionale sono potenti strumenti per attenuare gli account compromessi e l'accesso non autorizzato. È consigliabile implementare un set di criteri che sono stati testati insieme. Per ulteriori informazioni, inclusi i passaggi di distribuzione, vedere [Configurazioni di identità e accesso ai dispositivi.](../security/office-365-security/microsoft-365-policies-configurations.md)

 Questi criteri implementano le funzionalità seguenti:
- Autenticazione a più fattori
- Accesso condizionale
- Protezione delle app di Intune (protezione di app e dati per i dispositivi)
- Conformità dei dispositivi Intune
- Azure AD Identity Protection

L'implementazione della conformità dei dispositivi intune richiede la registrazione del dispositivo. La gestione dei dispositivi consente di verificare che siano integri e conformi prima di consentire loro l'accesso alle risorse nell'ambiente. Vedere [Registrare i dispositivi per la gestione in Intune](https://docs.microsoft.com/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)

## <a name="step-4-configure-sharepoint-device-access-policies"></a>Passaggio 4: Configurare i criteri di accesso ai dispositivi di SharePoint

Microsoft consiglia di proteggere i contenuti nei siti di SharePoint con contenuti sensibili e altamente regolamentati con controlli di accesso ai dispositivi. Per ulteriori informazioni, vedere Suggerimenti [sui criteri per la protezione di siti e file di SharePoint.](../security/office-365-security/sharepoint-file-access-policies.md)



    

