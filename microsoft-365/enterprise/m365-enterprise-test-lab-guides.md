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
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: 706d5449-45e5-4b0c-a012-ab60501899ad
description: Utilizzare queste guide al lab di test per configurare dimostrazioni, modelli di verifica o ambienti di sviluppo e test per Microsoft 365 per le aziende.
ms.openlocfilehash: a006f549d0ac68562faee9c935df7f15161b2f12
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909599"
---
# <a name="microsoft-365-for-enterprise-test-lab-guides"></a>Guide al lab di test di Microsoft 365 per le aziende

*Questo articolo si applica sia a Microsoft 365 per le aziende che a Office 365 Enterprise.*

Le guide al lab di test (TLG) facilitano la conoscenza dei prodotti Microsoft. Forniscono istruzioni prescrittive per configurare ambienti di testing semplificati ma rappresentativi. È possibile utilizzare questi ambienti per la dimostrazione, la personalizzazione o la creazione di modelli di verifica complessi per la durata di un abbonamento di valutazione o a pagamento.

I TG sono progettati per essere modulari. Si basano l'uno sull'altro per creare più configurazioni che corrispondano più strettamente alle esigenze di apprendimento o di configurazione di test. L'esperienza hands-on "L'ho creata io e funziona" consente di comprendere i requisiti di distribuzione di un nuovo prodotto o scenario, in modo da poter pianificare meglio l'hosting in produzione.

È inoltre possibile utilizzare IGG per creare ambienti rappresentativi per sviluppare e testare applicazioni, note anche come ambienti di sviluppo/test.
  
![Guide al lab di test per il cloud Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

Per una mappa visiva a tutti gli articoli dello stack guida del laboratorio di testing di Microsoft 365 per le aziende, espandere il grafico seguente o passare a [Microsoft 365 per enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).

[![Serie di guide al lab di test di Microsoft 365 per le aziende](../media/m365-enterprise-test-lab-guides/microsoft-365-enterprise-tlg-stack.png)](../downloads/Microsoft365EnterpriseTLGStack.pdf)

## <a name="base-configuration"></a>Configurazione di base

Innanzitutto, creare un ambiente di testing [per Microsoft 365 per le aziende](/microsoft-365-enterprise/). È possibile creare due diversi tipi di configurazioni di base:

- [Configurazione di base](lightweight-base-configuration-microsoft-365-enterprise.md) leggera: utilizzare questa opzione quando si desidera configurare e dimostrare le funzionalità e le funzionalità di Microsoft 365 per le aziende in un ambiente solo cloud, che non include componenti locali.

- [Configurazione](simulated-ent-base-configuration-microsoft-365-enterprise.md) di base aziendale simulata: utilizzare questa opzione quando si desidera configurare e dimostrare le funzionalità e le funzionalità di Microsoft 365 per le aziende in un ambiente cloud ibrido, che utilizza componenti locali, ad esempio un dominio di Servizi di dominio Active Directory.

È anche possibile creare ambienti di test per Office 365 E5 non aggiungendo la licenza di Microsoft 365 E5 all'ambiente di test di prova o di produzione.
    
## <a name="identity"></a>Identità

Per verificare le funzionalità e le capacità relative alla gestione delle identità, vedere:

- [Sincronizzazione hash delle password](password-hash-sync-m365-ent-test-environment.md)
  
   Abilitare e testare la sincronizzazione della directory basata su hash delle password da un controller di dominio di AD DS.

- [Autenticazione pass-through](pass-through-auth-m365-ent-test-environment.md)
  
   Abilitare e testare l'autenticazione pass-through per un controller di dominio di Active Directory Domain Services.

- [Autenticazione federata](federated-identity-for-your-microsoft-365-dev-test-environment.md)
  
   Abilitare e testare l'autenticazione federata per un controller di dominio di Active Directory Domain Services.

- [Accesso Single Sign-On facile di Azure AD](single-sign-on-m365-ent-test-environment.md)
  
   Abilitare e testare Azure AD Seamless Single Sign-On (SSO senza soluzione di continuità) con un controller di dominio di Servizi di dominio Active Directory.Enable and test Azure AD Seamless Single Sign-On (Seamless SSO) with an AD DS domain controller.

- [Autenticazione a più fattori](multi-factor-authentication-microsoft-365-test-environment.md)
  
   Abilitare e testare l'autenticazione a più fattori basata su smartphone per un account utente specifico.

- [Proteggere gli account amministratore globale](protect-global-administrator-accounts-microsoft-365-test-environment.md)

   Bloccare gli account di amministratore globale con criteri di accesso condizionale.

- [Writeback delle password](password-writeback-m365-ent-test-environment.md)

   Usare il writeback delle password per modificare la password per l'account utente di Active Directory Domain Services da Azure AD.

- [Reimpostazione delle password](password-reset-m365-ent-test-environment.md)

   Utilizzare la reimpostazione della password self-service per reimpostare la password.

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