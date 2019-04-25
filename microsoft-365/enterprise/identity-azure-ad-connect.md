---
title: "Passaggio 3: configurare l'identità ibrida"
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 02/25/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Informazioni sulle opzioni di identità e su come configurare Azure AD Connect per sincronizzare l'ambiente Active Directory Domain Services locale con Azure AD.
ms.openlocfilehash: 6e582a3e3c68b00968faac17fd60b922eaaf7121
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32289600"
---
# <a name="step-3-configure-hybrid-identity"></a>Passaggio 3: configurare l'identità ibrida

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-sync"></a>
## <a name="synchronize-identities"></a>Sincronizzare le identità

*Questo passaggio è obbligatorio per gli ambienti ibridi e si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*

In questa sezione si sincronizzerà l'ambiente Active Directory Domain Services locale (AD DS) con il tenant di Azure Active Directory (Azure AD) usato dagli abbonamenti a Office 365 ed Enterprise Mobility + Security (EMS).

Azure AD Connect è lo strumento Microsoft supportato che guida gli amministratori nel processo di sincronizzazione delle sole identità realmente necessarie da ambienti Azure Active Directory con una più foreste con il proprio tenant di Azure AD. La figura seguente mostra il processo di base per la sincronizzazione di Azure AD Connect.

![Come Azure AD Connect sincronizza la directory locale con Azure AD](./media/identity-azure-ad-connect/azure-ad-connect.png)

1. Azure AD Connect in esecuzione in un server esegue il polling per rilevare le modifiche apportate ad account, gruppi e contatti in Active Directory Domain Services.
2. Azure AD Connect invia le modifiche al tenant di Azure AD dell'abbonamento a Microsoft 365.

La prima decisione relativa alla soluzione delle identità ibride, riguarda i requisiti di autenticazione. Le opzioni sono le seguenti:

- Con l'**autenticazione gestita**, Azure AD gestisce il processo di autenticazione per l'accesso utente. Esistono due metodi di autenticazione gestita: 
    - **Sincronizzazione dell'hash delle password** [Opzione consigliata e obbligatoria per alcune funzionalità Premium]. Questo è il modo più semplice per abilitare l'autenticazione per gli oggetti directory locali in Azure AD. Azure AD Connect estrae le password con hash da Active Directory Domain Services, esegue ulteriori procedure di sicurezza sulla password e la salva in Azure AD. Per altre informazioni, vedere [Implementare la sincronizzazione dell'hash delle password con il servizio di sincronizzazione Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-synchronization).
    - L'**autenticazione pass-through di Azure AD** offre una soluzione di convalida delle password semplice per i servizi basati su Azure AD. Usa un agente in esecuzione in uno o più server locali per convalidare le autenticazioni utente direttamente con Active Directory Domain Services locale. Per altre informazioni, vedere [Accesso utente con l'autenticazione pass-through di Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-pass-through-authentication).
- Con l'**autenticazione federata**, il processo di autenticazione viene reindirizzato a un altro provider di identità tramite un server federativo di identità, come Active Directory Federation Services (ADFS), per l'accesso utente. Il provider di identità può fornire altri metodi di autenticazione, ad esempio l'autenticazione basata su una smart card. Per ulteriori informazioni, vedere [Scegliere il giusto metodo di autenticazione per la soluzione delle identità ibride di Azure Active Directory](https://docs.microsoft.com/azure/security/azure-ad-choose-authn).

Una volta determinata la soluzione per le identità ibride, scaricare ed eseguire lo [Strumento IdFix DirSync Error Remediation Tool](https://www.microsoft.com/download/details.aspx?id=36832) per analizzare Active Directory Domain Services e cercare eventuali problemi.

Dopo aver risolto tutti i problemi identificati tramite lo strumento IdFix, vedere [Implementare la sincronizzazione dell'hash delle password](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-implement-password-hash-synchronization) per installare lo strumento Azure AD Connect e configurare la sincronizzazione delle directory tra Active Directory Domain Services locale e il tenant di Azure AD per gli abbonamenti a Office 365 ed EMS. Dopo l'inizio della sincronizzazione, sarà possibile mantenere gli account utente e i gruppi con il provider di identità locale, come Active Directory Domain Services.

Microsoft offre una serie di consigli per [identità e accesso ai dispositivi](microsoft-365-policies-configurations.md) per garantire un ambiente di lavoro protetto e produttivo. 

- Per i requisiti consigliati per gli ambienti ibridi, vedere la colonna **Active Directory con sincronizzazione delle password hash** in [Prerequisiti](identity-access-prerequisites.md#prerequisites). 

- Per i requisiti consigliati per gli ambienti solo cloud, vedere la colonna **Solo cloud** in [Prerequisiti](identity-access-prerequisites.md#prerequisites).

Quando in Azure AD sono presenti gli utenti e i gruppi locali, è possibile iniziare ad assegnare le licenze e a usare Exchange Online. Per implementare Exchange Online per gli utenti ed eseguire la migrazione delle cassette postali locali, vedere [Distribuire Exchange Online per Microsoft 365 Enterprise](exchangeonline-workload.md).

|||
|:-------|:-----|
|![Guide al lab di test per il cloud Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Guida del laboratorio di testing: sincronizzazione hash delle password](password-hash-sync-m365-ent-test-environment.md)<br> [Guida del laboratorio di testing: autenticazione pass-through](pass-through-auth-m365-ent-test-environment.md) |
|||

Come checkpoint provvisorio, vedere i [criteri di uscita](identity-exit-criteria.md#crit-identity-sync) relativi a questa sezione.

<a name="identity-sync-health"></a>
## <a name="monitor-synchronization-health"></a>Monitorare l'integrità della sincronizzazione

*Questo passaggio è facoltativo e si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*

In questa sezione si installerà un agente di Azure AD Connect Health in ogni server di identità locale per monitorare l'infrastruttura di gestione delle identità e i servizi di sincronizzazione forniti da Azure AD Connect. Le informazioni sul monitoraggio vengono rese disponibili nel portale di Azure AD Connect Health, dove è possibile visualizzare avvisi, il monitoraggio delle prestazioni, analisi sull'utilizzo e altre informazioni.

![Componenti di Azure AD Connect Health](./media/identity-azure-ad-connect-health/identity-azure-ad-connect-health.png)

La decisione di progettazione chiave su come usare Azure AD Connect Health si basa sul modo in cui si utilizza Azure AD Connect:

- Se si usa l'opzione **autenticazione gestita** iniziare con [Uso di Azure AD Connect Health con la sincronizzazione](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) per comprendere e configurare Azure AD Connect Health.
- Se si stanno sincronizzando soli i nomi di account e gruppi tramite l'**autenticazione federata** con Active Directory Federation Services (AD FS), iniziare con [Uso di Azure AD Connect Health con AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) per comprendere e configurare Azure AD Connect Health.

Dopo aver completato questa sezione:

- L'agente di Azure AD Connect Health è installato su ciascuno dei server del provider di identità locale.
- Il portale di Azure AD Connect Health mostra lo stato corrente dell'infrastruttura locale e le attività di sincronizzazione con il tenant di Azure AD per gli abbonamenti a Office 365 e EMS.

Come checkpoint provvisorio, è possibile vedere i [criteri uscita](identity-exit-criteria.md#crit-identity-sync-health) per questa sezione.

## <a name="next-step"></a>Passaggio successivo

|||
|:-------|:-----|
![](./media/stepnumbers/Step4.png)| [Configurare l'autenticazione utente sicura](identity-multi-factor-authentication.md)
