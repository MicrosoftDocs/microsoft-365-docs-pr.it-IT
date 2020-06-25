---
title: Guide al lab di test di Microsoft 365 per le aziende
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/20/2019
audience: ITPro
ms.topic: hub-page
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: 706d5449-45e5-4b0c-a012-ab60501899ad
description: Utilizzare queste guide al lab di test per configurare dimostrazioni, modelli di verifica o ambienti di sviluppo e test per Microsoft 365 per le aziende.
ms.openlocfilehash: 5907edd1bc42b9d679ed020331f225ef2d2b2594
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818742"
---
# <a name="microsoft-365-for-enterprise-test-lab-guides"></a>Guide al lab di test di Microsoft 365 per le aziende

*Questo articolo si applica sia a Microsoft 365 per le aziende che a Office 365 Enterprise.*

Test Lab Guides (TLGs) help you quickly learn about Microsoft products. They provide prescriptive instructions to configure simplified but representative test environments. You can use these environments for demonstration, customization, or creation of complex proofs of concept for the duration of a trial or paid subscription. 

TLGs are designed to be modular. They build upon each other to create multiple configurations that more closely match your learning or test configuration needs. The "I built it out myself and it works" hands-on experience helps you understand the deployment requirements of a new product or scenario so you can better plan for hosting it in production.

Queste guide permettono di creare anche ambienti appositi per lo sviluppo e il testing delle applicazioni, noti anche con il nome di ambienti di sviluppo/testing.
  
![Guide al lab di test per il cloud Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

Aprire la [Guida al lab di test](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) per consultare una mappa di tutti gli articoli della guida al lab di test di Microsoft 365 Enterprise.

[![Serie di guide al lab di test di Microsoft 365 per le aziende](../media/m365-enterprise-test-lab-guides/microsoft-365-enterprise-tlg-stack.png)](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)

## <a name="base-configuration"></a>Configurazione di base

First, you create a test environment for [Microsoft 365 for enterprise](https://docs.microsoft.com/microsoft-365-enterprise/) that includes Office 365 E5, Enterprise Mobility + Security (EMS) E5, and Windows 10 Enterprise. You can create two different types of base configurations:

- Usare la [configurazione di base semplificata](lightweight-base-configuration-microsoft-365-enterprise.md) quando si desidera configurare e dimostrare le caratteristiche e le funzionalità di Microsoft 365 per le aziende in un ambiente solo cloud, che non include componenti locali.

- Usare la [configurazione di base simulata per l'organizzazione](simulated-ent-base-configuration-microsoft-365-enterprise.md) quando si vuole configurare e dimostrare le caratteristiche e le funzionalità di Microsoft 365 per le aziende in un ambiente cloud ibrido, che usa componenti locali come un dominio di Active Directory Domain Services.

È anche possibile creare ambienti di test per Office 365 E5 non aggiungendo la licenza di Microsoft 365 E5 all'ambiente di test di prova o di produzione.
    
## <a name="identity"></a>Identità

Per verificare le funzionalità e le capacità relative alla gestione delle identità, vedere:

- [Sincronizzazione hash delle password](password-hash-sync-m365-ent-test-environment.md)
  
   Abilitare e testare la sincronizzazione della directory basata su hash delle password da un controller di dominio di AD DS.

- [Autenticazione pass-through](pass-through-auth-m365-ent-test-environment.md)
  
   Abilitare e testare l'autenticazione pass-through per un controller di dominio di Active Directory Domain Services.

- [Autenticazione federata](federated-identity-for-your-office-365-dev-test-environment.md)
  
   Abilitare e testare l'autenticazione federata per un controller di dominio di Active Directory Domain Services.

- [Accesso Single Sign-On facile di Azure AD](single-sign-on-m365-ent-test-environment.md)
  
   Attivare e testare l'accesso Single Sign-On facile di Azure AD con un controller di dominio di Active Directory Domain Services.

- [Autenticazione a più fattori](multi-factor-authentication-microsoft-365-test-environment.md)
  
   Abilitare e testare l'autenticazione a più fattori basata su smartphone per un account utente specifico.

- [Proteggere gli account amministratore globale](protect-global-administrator-accounts-microsoft-365-test-environment.md)
 
   Bloccare gli account di amministratore globale con criteri di accesso condizionale.

- [Writeback delle password](password-writeback-m365-ent-test-environment.md)

   Usare il writeback delle password per modificare la password per l'account utente di Active Directory Domain Services da Azure AD.

- [Reimpostazione delle password](password-reset-m365-ent-test-environment.md)

   Utilizzare la reimpostazione password self-service (SSPR) per reimpostare la password.

- [Licenze automatiche e appartenenza a gruppi](automate-licenses-group-membership-microsoft-365-test-environment.md)

   L'amministrazione di nuovi account è più facile che mai grazie alle licenze automatiche e all'appartenenza a gruppi dinamica.

- [Azure AD Identity Protection](azure-ad-identity-protection-microsoft-365-test-environment.md)

   Analizzare gli account utente correnti per individuare possibili vulnerabilità.

- [Accesso a identità e dispositivi](identity-device-access-m365-test-environment.md)

   Creare un ambiente per testare l'identità consigliata, le configurazioni dei dispositivi di accesso e i criteri di accesso condizionali.


## <a name="mobile-device-management"></a>Gestione dei dispositivi mobili

Per verificare le funzionalità e le capacità relative alla gestione dei dispositivi mobili, vedere:

- [Criteri di conformità dei dispositivi](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
    
   Creare un gruppo di utenti e un criterio di conformità dispositivo per i dispositivi Windows 10.
    
- [Registrazione di dispositivi iOS e Android](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
   
   Registrare dispositivi iOS e Android e gestirli in remoto.


## <a name="information-protection"></a>Protezione delle informazioni

Per verificare le funzionalità e le capacità relative alla gestione delle informazioni, vedere:

- [Sicurezza di Microsoft 365 aumentata](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md)
    
   Configurare le impostazioni per una sicurezza aumentata di Microsoft 365 ed esaminare gli strumenti incorporati per la sicurezza.
  
- [Classificazione dei dati](data-classification-microsoft-365-enterprise-dev-test-environment.md)
    
   Configurare e applicare le etichette a un documento in un sito del team di SharePoint Online.
    
- [Gestione accessi con privilegi](privileged-access-microsoft-365-enterprise-dev-test-environment.md)
    
   Configurare la gestione degli accessi con privilegi per l'accesso just-in-time alle attività con privilegi e privilegi elevati nell'organizzazione.


