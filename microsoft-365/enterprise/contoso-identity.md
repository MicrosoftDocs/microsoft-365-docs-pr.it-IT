---
title: Identità per Contoso Corporation
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Come Contoso sfrutta l’identità come servizio (IDaaS) e fornisce l'autenticazione basata su cloud per i dipendenti e l'autenticazione federata per i partner e clienti.
ms.openlocfilehash: accd60f6699e7ebf04963213128d1ca1ffc8f7fe
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911073"
---
# <a name="identity-for-the-contoso-corporation"></a>Identità per Contoso Corporation

Microsoft fornisce Identity as a Service (IDaaS) nelle offerte cloud tramite Azure Active Directory (Azure AD). Per adottare Microsoft 365 per le aziende, la soluzione Contoso IDaaS doveva utilizzare il proprio provider di identità locale e includere l'autenticazione federata con i provider di identità attendibili di terze parti esistenti.

## <a name="the-contoso-active-directory-domain-services-forest"></a>Foresta di Servizi di dominio Active Directory Contoso

Contoso utilizza una singola foresta di Servizi di dominio Active Directory (AD DS) per contoso com con sette \. sottodomini, uno per ogni area geografica del mondo. La sede principale, le sedi centrali regionali e le filiali contengono controller di dominio per l'autorizzazione e l'autenticazione locali.

Ecco la foresta contoso con domini regionali per le diverse parti del mondo che contengono hub regionali.

![Foresta di Contoso e domini a livello mondiale](../media/contoso-identity/contoso-identity-fig1.png)
 
Contoso ha deciso di utilizzare gli account e i gruppi nella foresta contoso com per l'autenticazione e l'autorizzazione per i carichi di lavoro e i servizi di \. Microsoft 365.

## <a name="the-contoso-federated-authentication-infrastructure"></a>Infrastruttura di autenticazione federata Contoso

Contoso consente:

- I clienti possono usare i propri account Microsoft, Facebook o Google Mail per accedere al sito Web pubblico dell'azienda.
- Fornitori e partner per usare i propri account LinkedIn, Salesforce o Google Mail per accedere all'Extranet partner dell'azienda.

Ecco la dmZ contoso contenente un sito Web pubblico, una extranet partner e un set di server Active Directory Federation Services (AD FS). La rete perimetrale è connessa a Internet che contiene clienti, partner e servizi Internet.

![Supporto di Contoso per l'autenticazione federata per clienti e partner](../media/contoso-identity/contoso-identity-fig2.png)
 
I server AD FS nella rete perimetrale facilitano l'autenticazione delle credenziali dei clienti da parte dei provider di identità per l'accesso al sito Web pubblico e le credenziali del partner per l'accesso alla extranet del partner.

Contoso ha deciso di mantenere questa infrastruttura e dedicarla all'autenticazione di clienti e partner. Gli architetti per le identità di Contoso stanno valutando la conversione di questa infrastruttura in soluzioni [B2B](/azure/active-directory/b2b/hybrid-organizations) e [B2C](/azure/active-directory-b2c/solution-articles) di Azure AD.

## <a name="hybrid-identity-with-password-hash-synchronization-for-cloud-based-authentication"></a>Identità ibrida con sincronizzazione dell'hash delle password per l'autenticazione basata su cloud

Contoso desiderava utilizzare la foresta di Servizi di dominio Active Directory locale per l'autenticazione alle risorse cloud di Microsoft 365. Ha deciso di usare la sincronizzazione dell'hash delle password (PHS).

PHS sincronizza la foresta di Servizi di dominio Active Directory locale con il tenant di Azure AD della sottoscrizione a Microsoft 365 per le aziende, copiando gli account utente e di gruppo e una versione con hash delle password degli account utente.

Per eseguire la sincronizzazione della directory, Contoso ha distribuito lo strumento Azure AD Connect in un server nel datacenter di Parigi.

Ecco il server che esegue Azure AD Connect che esegue il polling della foresta di Contoso AD DS per le modifiche e quindi la sincronizzazione di tali modifiche con il tenant di Azure AD.

![Infrastruttura di sincronizzazione della directory PHS contoso](../media/contoso-identity/contoso-identity-fig4.png)
 
## <a name="conditional-access-policies-for-identity-and-device-access"></a>Criteri di accesso condizionale per l’identità e l’accesso dei dispositivi

Contoso ha creato un insieme di [criteri di accesso condizionale](../security/office-365-security/identity-access-policies.md) per Azure AD e Intune per tre livelli di protezione:

- *Le* protezioni di base si applicano a tutti gli account utente.
- *Le* protezioni sensibili si applicano ai dirigenti e ai dirigenti.
- *Le protezioni* altamente regolamentate si applicano a utenti specifici dei reparti finanziari, legali e di ricerca che hanno accesso a dati altamente regolamentati.

Ecco il set risultante di criteri di accesso condizionale dell'identità e del dispositivo contoso.

![Criteri di accesso condizionale di identità e dispositivi di Contoso](../media/contoso-identity/contoso-identity-fig5.png)
 
## <a name="next-step"></a>Passaggio successivo

Scopri come Contoso usa l'infrastruttura di Microsoft Endpoint Configuration Manager per [distribuire e mantenere Windows 10 Enterprise corrente](contoso-win10.md) all'interno dell'organizzazione.

## <a name="see-also"></a>Vedere anche

[Roadmap delle identità per Microsoft 365](identity-roadmap-microsoft-365.md)

[Panoramica di Microsoft 365 per le aziende](microsoft-365-overview.md)

[Guide dei laboratori di testing](m365-enterprise-test-lab-guides.md)