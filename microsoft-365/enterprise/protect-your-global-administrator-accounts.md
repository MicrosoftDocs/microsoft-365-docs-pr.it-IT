---
title: Proteggere gli account di amministratore globale di Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/30/2020
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- m365initiative-coredeploy
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- BCS160
f1.keywords:
- NOCSH
ms.assetid: 6b4ded77-ac8d-42ed-8606-c014fd947560
description: In questo articolo vengono fornite informazioni sulla protezione dell'accesso dell'amministratore globale all'abbonamento a Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1f84ca33a620c3ea3c24f46eb29c1a39c28840e7
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289640"
---
# <a name="protect-your-microsoft-365-global-administrator-accounts"></a>Proteggere gli account di amministratore globale di Microsoft 365

*Questo articolo si applica sia a Microsoft 365 Enterprise che a Office 365 Enterprise*.

Le violazioni della sicurezza di un abbonamento a Microsoft 365, inclusi gli attacchi di phishing e raccolta di informazioni, vengono in genere eseguite compromettendo le credenziali di un account amministratore globale di Microsoft 365. La sicurezza nel cloud è una partnership tra te e Microsoft:
  
- I servizi cloud Microsoft si basano su una base di attendibilità e sicurezza. Microsoft fornisce controlli di sicurezza e funzionalità che consentono di proteggere i dati e le applicazioni.
    
- Si è proprietari dei dati e delle identità e la responsabilità di proteggerli, la sicurezza delle risorse locali e la sicurezza dei componenti cloud che si controllano.
    
Microsoft offre funzionalità che consentono di proteggere l'organizzazione, ma sono efficaci solo se vengono usate. Se non vengono utilizzati, è possibile che l'utente sia vulnerabile agli attacchi. Per proteggere gli account di amministratore globale, Microsoft è qui per aiutarti con istruzioni dettagliate per:
  
1. Creare account di amministratore globale di Microsoft 365 dedicati e usarli solo se necessario.
    
2. Configurare l'autenticazione a più fattori per gli account di amministratore globale di Microsoft 365 dedicati e usare la forma più avanzata di autenticazione secondaria.
    
> [!Note]
> Anche se questo articolo è incentrato sugli account di amministratore globale, è consigliabile valutare se gli account aggiuntivi con autorizzazioni di accesso ai dati nell'abbonamento, ad esempio gli account di amministratore di eDiscovery o di sicurezza o di conformità, devono essere protetti allo stesso modo. <br > È possibile creare un account amministratore globale senza aggiungere licenze.
  
## <a name="step-1-create-dedicated-microsoft-365-global-administrator-accounts-and-use-them-only-when-necessary"></a>Passaggio 1. Creare account di amministratore globale di Microsoft 365 dedicati e usarli solo se necessario

Esistono relativamente poche attività amministrative, ad esempio l'assegnazione di ruoli agli account utente, che richiedono privilegi di amministratore globale. Pertanto, anziché utilizzare gli account utente di uso quotidiano a cui è stato assegnato il ruolo di amministratore globale, eseguire la procedura seguente:
  
1. Determinare il set di account utente a cui è stato assegnato il ruolo di amministratore globale. È possibile eseguire questa operazione nell'interfaccia di amministrazione di Microsoft 365 o con il comando Azure Active (Azure AD) Directory PowerShell per Graph seguente:
  
  ```powershell
  Get-AzureADDirectoryRole | where { $_.DisplayName -eq "Global Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```

2. Accedere all'abbonamento a Microsoft 365 con un account utente a cui è stato assegnato il ruolo di amministratore globale.
    
3. Creare fino a un massimo di quattro account utente amministratore globale dedicati. **Utilizzare password complesse di almeno 12 caratteri.** Per [ulteriori informazioni, vedere](https://support.microsoft.com/help/4026406/microsoft-account-create-a-strong-password) Creare una password complessa. Archiviare le password per i nuovi account in una posizione sicura. 
    
4. Assegnare il ruolo di amministratore globale a ognuno dei nuovi account utente di amministratore globale dedicati.
    
5. Disconnettersi da Microsoft 365.
    
6. Accedere con uno dei nuovi account utente di amministratore globale dedicati.
    
7. Per ogni account utente esistente a cui è stato assegnato il ruolo di amministratore globale dal passaggio 1:
    
  - Rimuovere il ruolo di amministratore globale.
    
  - Assegnare ruoli di amministratore all'account appropriato per la funzione e la responsabilità dell'utente. Per ulteriori informazioni sui vari ruoli di amministratore in Microsoft 365, vedere [Informazioni sui ruoli di amministratore.](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)
    
8. Disconnettersi da Microsoft 365.
    
I risultati dovrebbero essere:
  
- Gli unici account utente dell'abbonamento a cui è assegnato il ruolo di amministratore globale sono i nuovi account di amministratore globale dedicati. Verificarlo con il comando di PowerShell seguente:
    
  ```powershell
  Get-AzureADDirectoryRole | where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```

- A tutti gli altri account utente quotidiani che gestiscono l'abbonamento sono assegnati ruoli di amministratore associati ai propri ruoli professionali.
    
Da questo momento in poi, si accede con gli account di amministratore globale dedicati solo per le attività che richiedono privilegi di amministratore globale. Tutte le altre attività di amministrazione di Microsoft 365 devono essere eseguite assegnando altri ruoli di amministrazione agli account utente.
  
> [!NOTE]
> Questa operazione richiede ulteriori passaggi per disconnettersi come account utente di tutti i giorni e accedere con un account amministratore globale dedicato. Tuttavia, questa operazione deve essere eseguita solo occasionalmente per le operazioni di amministratore globale. Considerare che il ripristino dell'abbonamento a Microsoft 365 dopo una violazione dell'account amministratore globale richiede molti più passaggi.
  
## <a name="step-2-configure-multi-factor-authentication-for-your-dedicated-microsoft-365-global-administrator-accounts"></a>Passaggio 2. Configurare l'autenticazione a più fattori per gli account di amministratore globale di Microsoft 365 dedicati

L'autenticazione a più fattori (MFA) richiede ulteriori informazioni oltre al nome e alla password dell'account. Microsoft 365 supporta questi metodi di verifica aggiuntivi:
  
- L'app Microsoft Authenticator

- Una telefonata
    
- Un codice di verifica generato in modo casuale inviato tramite un SMS
    
- Una smart card virtuale o fisica
    
- Un dispositivo biometrico
    
>[!Note]
>Per le organizzazioni che devono rispettare gli standard NIST (National Institute of Standards and Technology), l'uso di una chiamata telefonica o di ulteriori metodi di verifica basati su SMS è limitato. Fare [clic qui](https://pages.nist.gov/800-63-FAQ/#q-b01) per i dettagli.
>

Se si è una piccola azienda che utilizza account utente archiviati solo nel cloud (il modello di identità solo [cloud),](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication) configurare l'autenticazione a più fattori per configurare l'autenticazione a più fattori utilizzando una chiamata telefonica o un codice di verifica sms inviato a uno smartphone per ogni account amministratore globale dedicato.
    
Se si è un'organizzazione di grandi dimensioni che utilizza un modello di identità ibrido di Microsoft 365, sono disponibili più opzioni di verifica. Se è già presente l'infrastruttura di sicurezza per un metodo di autenticazione secondario più [sicuro,](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication) configurare l'autenticazione a più fattori e ogni account amministratore globale dedicato per il metodo di verifica appropriato.
  
Se l'infrastruttura di sicurezza per il metodo di verifica più sicuro desiderato non è presente e funziona per Microsoft 365 MFA, è consigliabile configurare account di amministratore globale dedicati con MFA utilizzando l'app Microsoft Authenticator, una chiamata telefonica o un codice di verifica sms inviato a uno smartphone per gli account di amministratore globale come misura di sicurezza provvisoria. Non lasciare gli account di amministratore globale dedicati senza la protezione aggiuntiva fornita dall'autenticazione a più fattori.
  
Per altre informazioni, vedere [MFA per Microsoft 365.](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/multi-factor-authentication-microsoft-365)
  
Per connettersi ai servizi di Microsoft 365 con MFA e PowerShell, vedere questi articoli:

- [PowerShell per Microsoft 365 per account utente, gruppi e licenze](connect-to-microsoft-365-powershell.md)
- [Microsoft Teams](https://docs.microsoft.com/microsoftteams/teams-powershell-install)
- [Exchange Online](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell#connect-to-exchange-online-powershell-using-mfa)
- [SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online#to-connect-with-multifactor-authentication-mfa)
- [Skype for Business online](manage-skype-for-business-online-with-microsoft-365-powershell.md#connect-using-an-admin-account-with-multi-factor-authentication)

## <a name="additional-protections-for-enterprise-organizations"></a>Protezioni aggiuntive per le organizzazioni aziendali

Utilizzare questi metodi aggiuntivi per garantire che l'account amministratore globale e la configurazione eseguita utilizzandolo siano il più sicuri possibile.
  
### <a name="privileged-access-workstation"></a>Workstation con accesso privilegiato

Per garantire che l'esecuzione di attività con privilegi elevati sia il più sicura possibile, utilizzare una workstation con accesso privilegiato (PAW). Una paW è un computer dedicato che viene utilizzato solo per le attività di configurazione riservate, ad esempio la configurazione di Microsoft 365 che richiede un account amministratore globale. Poiché questo computer non viene utilizzato quotidianamente per l'esplorazione di Internet o la posta elettronica, è meglio protetto da attacchi e minacce Internet.
  
Per istruzioni su come configurare una paw, vedere [https://aka.ms/cyberpaw](https://aka.ms/cyberpaw) .

Per attivare Azure PIM per gli account tenant e amministratore Azure Active Directory, vedere la [procedura per configurare PIM](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).

Per sviluppare una roadmap che protegga l'accesso con privilegi dagli attacchi informatici, vedere [Protezione dell'accesso con privilegi per le distribuzioni ibride e cloud in Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices).

### <a name="azure-ad-privileged-identity-management"></a>Azure AD Privileged Identity Management

Anziché assegnare definitivamente agli account di amministratore globale il ruolo di amministratore globale, è possibile utilizzare Azure AD Privileged Identity Management (PIM) per abilitare l'assegnazione just-in-time su richiesta del ruolo di amministratore globale quando necessario.
  
Gli account di amministratore globale passano da amministratori permanenti ad amministratori idonei. Il ruolo di amministratore globale è inattivo fino a quando qualcuno non ne ha bisogno. È quindi necessario completare un processo di attivazione per aggiungere il ruolo di amministratore globale all'account amministratore globale per un periodo di tempo predeterminato. Alla scadenza del periodo di tempo, PIM rimuove il ruolo di amministratore globale dall'account amministratore globale.
  
L'utilizzo di PIM e di questo processo riduce in modo significativo la quantità di tempo per cui gli account amministratore globale sono vulnerabili agli attacchi e all'utilizzo da parte di utenti malintenzionati.

PIM è disponibile con Azure Active Directory Premium P2, incluso in Microsoft 365 E5. In alternativa, è possibile acquistare singole licenze di Azure Active Directory Premium P2 per gli account di amministratore.
  
Per altre informazioni, vedere [Azure AD Privileged Identity Management.](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)
  

### <a name="privileged-access-management"></a>Gestione accessi con privilegi

La gestione degli accessi con privilegi è abilitata mediante la configurazione di criteri che specificano l'accesso just-in-time per le operazioni basate sulle attività nel tenant. Può aumentare il livello di protezione dell'organizzazione da violazioni che possono usare gli account amministratore con privilegi esistenti con accesso permanente a dati sensibili o con accesso a impostazioni di configurazione cruciali. Ad esempio, è possibile configurare un criterio di gestione degli accessi con privilegi che richiede l'approvazione esplicita per accedere e modificare le impostazioni delle cassette postali dell'organizzazione nel tenant.

In questo passaggio verrà abilitata la gestione degli accessi con privilegi nel tenant e verranno configurati i criteri di accesso con privilegi che garantiscono una maggiore protezione per gli accessi basati sulle attività a impostazioni dati e configurazione dell'organizzazione. Esistono tre passaggi di base per iniziare a usare gli accessi con privilegi nell'organizzazione:

- Creazione di un gruppo responsabile dell'approvazione
- Abilitazione dell’accesso con privilegi
- Creazione di criteri per l'approvazione

La gestione degli accessi privilegiati consente all'organizzazione di operare senza privilegi permanenti e di fornire un livello di difesa contro le vulnerabilità derivanti da tale accesso amministrativo permanente. L'accesso con privilegi richiede l'approvazione per l'esecuzione di qualsiasi attività a cui è associato un criterio di approvazione definito. Gli utenti che devono eseguire le attività incluse nel criterio di approvazione devono richiedere e ottenere l'approvazione dell'accesso.

Per abilitare la gestione degli accessi con privilegi, vedere [Configurare la gestione degli accessi con privilegi.](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration)

Per ulteriori informazioni, vedere [Privileged access management.](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview)

### <a name="security-information-and-event-management-siem-software-for-microsoft-365-logging"></a>Software siem (Security Information and Event Management) per la registrazione di Microsoft 365

Il software SIEM eseguito in un server esegue un'analisi in tempo reale degli avvisi di sicurezza e degli eventi creati dalle applicazioni e dall'hardware di rete. Per consentire al server SIEM di includere gli eventi e gli avvisi di sicurezza di Microsoft 365 nelle funzioni di analisi e creazione di report, integrare Azure AD in SEIM. Vedere [Introduzione all'integrazione dei log di Azure.](https://docs.microsoft.com/azure/security/security-azure-log-integration-overview)

## <a name="next-step"></a>Passaggio successivo

Se si configura l'identità per l'abbonamento a Microsoft 365, vedere:

- [Identità solo cloud se](cloud-only-identities.md) si usa l'identità solo cloud
- [Preparare la sincronizzazione della directory](prepare-for-directory-synchronization.md) se si utilizza l'identità ibrida

  
## <a name="see-also"></a>Vedere anche

[Guida di orientamento alla sicurezza di Microsoft 365](https://docs.microsoft.com/office365/securitycompliance/security-roadmap)
