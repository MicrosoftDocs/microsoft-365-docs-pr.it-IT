---
title: Identità per Contoso Corporation
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 10/01/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Come Contoso sfrutta l’identità come servizio (IDaaS) e fornisce l'autenticazione basata su cloud per i dipendenti e l'autenticazione federata per i partner e clienti.
ms.openlocfilehash: dc893fb1e632cf15a612ebf13e911173933d9af3
ms.sourcegitcommit: 9ee873c6a2f738a0c99921e036894b646742e706
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/15/2019
ms.locfileid: "38673212"
---
# <a name="identity-for-the-contoso-corporation"></a>Identità per Contoso Corporation

Microsoft fornisce un'identità come servizio (IDaaS) per le offerte cloud con Azure Active Directory (Azure AD). Per adottare Microsoft 365 Enterprise, la soluzione IDaaS di Contoso deve sfruttare i provider di identità locali e includere l'autenticazione federata con i provider di identità di terze parti esistenti e attendibili.

## <a name="contosos-active-directory-domain-services-forest"></a>Foresta di Servizi di dominio di Active Directory di Contoso

Contoso usa una foresta di Servizi di dominio di Active Directory (AD DS) singola per contoso.com con sette sottodomini, uno per ogni area geografica del mondo. La sede principale, le sedi centrali regionali e le filiali contengono controller di dominio per l'autorizzazione e l'autenticazione locali.

Di seguito viene mostrata la foresta di Contoso con domini regionali per le varie parti del mondo in cui sono presenti sedi centrali regionali.

![Foresta di Contoso e domini a livello mondiale](./media/contoso-identity/contoso-identity-fig1.png)
 
Contoso ha voluto utilizzare gli account e i gruppi della foresta contoso.com per l'autenticazione e l'autorizzazione per i servizi e i carichi di lavoro su Microsoft 365.

## <a name="contosos-federated-authentication-infrastructure"></a>Infrastruttura di autenticazione federata di Contoso

Contoso consente:

- Ai clienti di usare il proprio account Microsoft, Facebook o Google Mail per accedere al proprio sito Web pubblico.
- Ai fornitori e ai partner di usare il proprio account LinkedIn, Salesforce o Google Mail per accedere all’extranet dei partner.

Di seguito viene mostrata la rete perimetrale di Contoso contenente un sito Web pubblico, una rete extranet partner e un set di server Active Directory Federation Services (AD FS). La rete perimetrale è connessa alla rete Internet che contiene clienti, partner e servizi Internet.

![Supporto di Contoso per l'autenticazione federata di clienti e partner](./media/contoso-identity/contoso-identity-fig2.png)
 
I server AD FS nella DMZ semplificano l'autenticazione delle credenziali dei clienti da parte dei relativi provider di identità per l'accesso al sito Web pubblico e delle credenziali dei partner per l'accesso alla Extranet dei partner.

Contoso ha deciso di mantenere questa infrastruttura e dedicarla alle autenticazioni di clienti e partner. Gli architetti dell’identità di Contoso stanno studiando la conversione di questa infrastruttura alle soluzioni [B2B](https://docs.microsoft.com/azure/active-directory/b2b/hybrid-organizations) e [B2C](https://docs.microsoft.com/azure/active-directory-b2c/solution-articles) di Azure AD.

## <a name="hybrid-identity-with-password-hash-synchronization-for-cloud-based-authentication"></a>Identità ibrida con sincronizzazione dell'hash delle password per l'autenticazione basata su cloud

Contoso ha voluto sfruttare la foresta AD DS locale per l'autenticazione alle risorse cloud Microsoft 365. Ha deciso per la sincronizzazione dell'hash delle password (PHS).

PHS sincronizza la foresta locale di Active Directory con il tenant Azure AD dell'abbonamento a Microsoft 365 Enterprise, copiando gli account utente e gruppo e una versione hash della password dell'account utente. 

Per eseguire la sincronizzazione delle directory in corso, Contoso ha distribuito lo strumento Azure AD Connect in un server nel Data Center di Parigi. 

Di seguito viene mostrato il server che esegue Azure AD Connect mentre sonda la foresta AD DS di Contoso per le modifiche e quindi sincronizza le modifiche apportate con il tenant Azure AD.

![Infrastruttura di sincronizzazione della directory PHS di Contoso](./media/contoso-identity/contoso-identity-fig4.png)
 
## <a name="conditional-access-policies-for-identity-and-device-access"></a>Criteri di accesso condizionale per l’identità e l’accesso dei dispositivi

Contoso ha creato un insieme di [criteri di accesso condizionale](identity-access-policies.md) per Azure AD e Intune per tre livelli di protezione:

- **Base** le protezioni si applicano a tutti gli account utente
- **Riservate** le protezioni si applicano a dirigenti senior e staff esecutivo
- Le protezioni di**Riservatezza elevata** si applicano a utenti specifici nei dipartimenti finanziario, legale e di ricerca che hanno accesso a dati altamente riservati

Di seguito viene mostrato l’insieme di risultati dei criteri di accesso condizionale di identità e dispositivi di Contoso.

![Criteri di accesso condizionale di identità e dispositivi di Contoso](./media/contoso-identity/contoso-identity-fig5.png)
 
## <a name="next-step"></a>Passaggio successivo

[Informazioni su](contoso-win10.md) come Contoso si avvale dell'infrastruttura di Microsoft Endpoint Configuration Manager per distribuire e mantenere aggiornato Windows 10 Enterprise nell'organizzazione.

## <a name="see-also"></a>Vedere anche

[Identità per Microsoft 365 Enterprise](identity-infrastructure.md)

[Guida alla distribuzione](deploy-microsoft-365-enterprise.md)

[Guide dei laboratori di testing](m365-enterprise-test-lab-guides.md)
