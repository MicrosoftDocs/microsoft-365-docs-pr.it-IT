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
ms.collection: Strat_O365_IP
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- BCS160
f1.keywords:
- NOCSH
ms.assetid: 6b4ded77-ac8d-42ed-8606-c014fd947560
description: In questo articolo vengono fornite informazioni sulla protezione dell'accesso di amministratore globale all'abbonamento a Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0b234c0e5c0ca352f26ff30213f22d59e07de274
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327250"
---
# <a name="protect-your-microsoft-365-global-administrator-accounts"></a>Proteggere gli account di amministratore globale di Microsoft 365

*Questo articolo si applica sia a Microsoft 365 Enterprise che a Office 365 Enterprise*.

Le violazioni della sicurezza di un abbonamento a Microsoft 365, incluse le informazioni raccolte e gli attacchi di phishing, vengono in genere eseguite compromettendo le credenziali di un account di amministratore globale di Microsoft 365. La sicurezza nel cloud è una partnership tra l'utente e Microsoft:
  
- I servizi cloud Microsoft sono basati su una base di attendibilità e sicurezza. Microsoft fornisce controlli e funzionalità di sicurezza che consentono di proteggere i dati e le applicazioni.
    
- Possiedi i dati e le identità e la responsabilità di proteggerli, la sicurezza delle risorse locali e la sicurezza dei componenti cloud che controlli.
    
Microsoft fornisce funzionalità che consentono di proteggere l'organizzazione, ma sono effettive solo se vengono utilizzate. Se non vengono utilizzati, potrebbe essere vulnerabile all'attacco. Per proteggere gli account di amministratore globale, Microsoft è qui per informazioni dettagliate su come eseguire le operazioni seguenti:
  
1. Creare account di amministratore globale di Microsoft 365 dedicati e utilizzarli solo quando necessario.
    
2. Configurare l'autenticazione a più fattori per gli account di amministratore globale di Microsoft 365 dedicati e utilizzare la forma più complessa di autenticazione secondaria.
    
> [!Note]
> Anche se questo articolo è concentrato sugli account di amministratore globale, è opportuno considerare se gli account aggiuntivi con autorizzazioni di vasta portata per accedere ai dati dell'abbonamento, ad esempio l'amministratore di eDiscovery o gli account di amministratore di sicurezza o conformità, devono essere protetti nello stesso modo. <br > Un account di amministratore globale può essere creato senza aggiungere alcuna licenza.
  
## <a name="step-1-create-dedicated-microsoft-365-global-administrator-accounts-and-use-them-only-when-necessary"></a>Passaggio 1. Creare account di amministratore globale di Microsoft 365 dedicati e utilizzarli solo se necessario

Vi sono relativamente poche attività amministrative, ad esempio l'assegnazione di ruoli agli account utente, che richiedono privilegi di amministratore globale. Pertanto, anziché utilizzare gli account utente giornalieri a cui è stato assegnato il ruolo di amministratore globale, procedere come segue:
  
1. Determinare il set di account utente a cui è stato assegnato il ruolo di amministratore globale. È possibile eseguire questa operazione nell'interfaccia di amministrazione di Microsoft 365 o con il seguente comando di PowerShell per il grafico di Azure Active (Azure AD):
  
  ```powershell
  Get-AzureADDirectoryRole | where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```

2. Accedere all'abbonamento a Microsoft 365 con un account utente a cui è stato assegnato il ruolo di amministratore globale.
    
3. Creare fino a un massimo di quattro account utente di amministratore globale dedicati. **Utilizzare password complesse con una lunghezza di almeno 12 caratteri.** Per ulteriori informazioni, vedere [creare una password complessa](https://support.microsoft.com/help/4026406/microsoft-account-create-a-strong-password) . Archiviare le password per i nuovi account in una posizione sicura. 
    
4. Assegnare il ruolo di amministratore globale a ognuno dei nuovi account utente di amministratore globale dedicato.
    
5. Disconnettersi da Microsoft 365.
    
6. Accedere con uno dei nuovi account utente di amministratore globale dedicati.
    
7. Per ogni account utente esistente a cui è stato assegnato il ruolo di amministratore globale dal passaggio 1:
    
  - Rimuovere il ruolo di amministratore globale.
    
  - Assegnare i ruoli di amministratore all'account appropriato per la funzione e la responsabilità del processo dell'utente. Per ulteriori informazioni sui vari ruoli di amministratore in Microsoft 365, vedere [informazioni sui ruoli di amministratore](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles).
    
8. Disconnettersi da Microsoft 365.
    
I risultati devono essere i seguenti:
  
- Gli unici account utente dell'abbonamento a cui è assegnato il ruolo di amministratore globale sono i nuovi account di amministratore globale dedicati. Verificarlo con il seguente comando di PowerShell:
    
  ```powershell
  Get-AzureADDirectoryRole | where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
  ```

- A tutti gli altri account utente quotidiani che gestiscono l'abbonamento sono assegnati ruoli di amministratore associati ai propri ruoli professionali.
    
Da questo momento in poi, si accede con gli account amministratore globale dedicato solo per le attività che richiedono privilegi di amministratore globale. Tutte le altre attività di amministrazione di Microsoft 365 devono essere eseguite assegnando altri ruoli di amministrazione agli account utente.
  
> [!NOTE]
> In questo modo, è necessario eseguire ulteriori passaggi per disconnettersi come account utente giornaliero e accedere con un account di amministratore globale dedicato. Tuttavia, è necessario eseguire questa operazione solo occasionalmente per le operazioni di amministratore globale. Si consideri che il ripristino della sottoscrizione Microsoft 365 dopo una violazione dell'account amministratore globale richiede passaggi molto più.
  
## <a name="step-2-configure-multi-factor-authentication-for-your-dedicated-microsoft-365-global-administrator-accounts"></a>Passaggio 2. Configurare l'autenticazione a più fattori per gli account di amministratore globale di Microsoft 365 dedicati

L'autenticazione a più fattori richiede ulteriori informazioni oltre il nome e la password dell'account. Microsoft 365 supporta questi metodi di verifica aggiuntivi:
  
- L'app Microsoft Authenticator

- Una telefonata
    
- Un codice di verifica generato casualmente inviato tramite un messaggio di testo
    
- Una smart card virtuale o fisica
    
- Un dispositivo biometrico
    
>[!Note]
>Per le organizzazioni che devono aderire agli standard di National Institute of Standards and Technology (NIST), l'utilizzo di una chiamata telefonica o di metodi di verifica aggiuntivi basati su messaggi di testo sono limitati. Fare clic [qui](https://pages.nist.gov/800-63-FAQ/#q-b01) per i dettagli.
>

Se si è una società di piccole dimensioni che utilizza account utente archiviati solo nel cloud (il modello di identità solo cloud), configurare il [Master](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication) per configurare l'AMF tramite una telefonata o un codice di verifica del messaggio di testo inviato a uno Smart Phone per ogni account amministratore globale dedicato.
    
Se si è un'organizzazione più grande che utilizza un modello di identità ibrido di Microsoft 365, sono disponibili altre opzioni di verifica. Se si dispone dell'infrastruttura di sicurezza già in vigore per un metodo di autenticazione secondario più forte, configurare [Mae](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication) e configurare ogni account amministratore globale dedicato per il metodo di verifica appropriato.
  
Se l'infrastruttura di sicurezza per il metodo di verifica più avanzato desiderato non è in esecuzione e funziona per Microsoft 365 Mae, è consigliabile configurare gli account di amministratore globale dedicati con AMF utilizzando l'app Microsoft Authenticator, una telefonata o un codice di verifica del messaggio di testo inviato a uno Smart Phone per gli account di amministratore globale come misura di sicurezza provvisoria. Non lasciare gli account di amministratore globale dedicati senza l'ulteriore protezione fornita dall'AMF.
  
Per ulteriori informazioni, vedere [AMF per Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/multi-factor-authentication-microsoft-365).
  
Per connettersi ai servizi di Microsoft 365 con AMF e PowerShell, vedere gli articoli seguenti:

- [PowerShell per Microsoft 365 per gli account utente, i gruppi e le licenze](connect-to-microsoft-365-powershell.md)
- [Microsoft Teams](https://docs.microsoft.com/microsoftteams/teams-powershell-install)
- [Exchange Online](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell#connect-to-exchange-online-powershell-using-mfa)
- [SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online#to-connect-with-multifactor-authentication-mfa)
- [Skype for Business online](manage-skype-for-business-online-with-microsoft-365-powershell.md#connect-using-an-admin-account-with-multi-factor-authentication)

## <a name="additional-protections-for-enterprise-organizations"></a>Protezioni aggiuntive per le organizzazioni aziendali

Utilizzare questi metodi aggiuntivi per verificare che l'account di amministratore globale e la configurazione eseguita con esso siano più sicuri possibile.
  
### <a name="privileged-access-workstation"></a>Workstation con accesso privilegiato

Per garantire che l'esecuzione di attività con privilegi elevati sia la più sicura possibile, utilizzare una workstation con accesso privilegiato (PAW). La ZAMPa è un computer dedicato utilizzato solo per le attività di configurazione sensibili, ad esempio la configurazione di Microsoft 365 che richiede un account di amministratore globale. Poiché questo computer non viene utilizzato giornalmente per la navigazione Internet o la posta elettronica, è meglio proteggerlo dagli attacchi e dalle minacce di Internet.
  
Per istruzioni su come configurare una ZAMPa, vedere [https://aka.ms/cyberpaw](https://aka.ms/cyberpaw) .

Per attivare Azure PIM per gli account tenant e amministratore Azure Active Directory, vedere la [procedura per configurare PIM](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).

Per sviluppare una roadmap che protegga l'accesso con privilegi dagli attacchi informatici, vedere [Protezione dell'accesso con privilegi per le distribuzioni ibride e cloud in Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices).

### <a name="azure-ad-privileged-identity-management"></a>Azure AD Privileged Identity Management

Invece di avere gli account amministratore globale assegnati definitivamente al ruolo di amministratore globale, è possibile utilizzare Azure AD Privileged Identity Management (PIM) per abilitare l'assegnazione su richiesta, just-in-Time del ruolo di amministratore globale quando necessario.
  
Gli account di amministratore globale passano dall'essere amministratori permanenti agli amministratori idonei. Il ruolo di amministratore globale è inattivo finché non è necessario per un utente. Completare quindi un processo di attivazione per aggiungere il ruolo di amministratore globale all'account di amministratore globale per un periodo di tempo predeterminato. Quando il tempo scade, PIM rimuove il ruolo di amministratore globale dall'account di amministratore globale.
  
L'utilizzo di PIM e questo processo riduce significativamente la quantità di tempo in cui gli account di amministratore globale sono vulnerabili all'attacco e all'utilizzo da parte di utenti malintenzionati.

PIM è disponibile con Azure Active Directory Premium P2, incluso in Microsoft 365 E5. In alternativa, è possibile acquistare singole licenze di Azure Active Directory Premium P2 per gli account di amministratore.
  
Per ulteriori informazioni, vedere [Azure ad Privileged Identity Management](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).
  

### <a name="privileged-access-management"></a>Gestione accessi con privilegi

La gestione degli accessi con privilegi è abilitata mediante la configurazione di criteri che specificano l'accesso just-in-time per le operazioni basate sulle attività nel tenant. Può aumentare il livello di protezione dell'organizzazione da violazioni che possono usare gli account amministratore con privilegi esistenti con accesso permanente a dati sensibili o con accesso a impostazioni di configurazione cruciali. Ad esempio, è possibile configurare un criterio di gestione degli accessi con privilegi che richiede l'approvazione esplicita per accedere e modificare le impostazioni delle cassette postali dell'organizzazione nel tenant.

In questo passaggio verrà abilitata la gestione degli accessi con privilegi nel tenant e verranno configurati i criteri di accesso con privilegi che garantiscono una maggiore protezione per gli accessi basati sulle attività a impostazioni dati e configurazione dell'organizzazione. Esistono tre passaggi di base per iniziare a usare gli accessi con privilegi nell'organizzazione:

- Creazione di un gruppo responsabile dell'approvazione
- Abilitazione dell’accesso con privilegi
- Creazione di criteri per l'approvazione

La gestione degli accessi con privilegi consente all'organizzazione di operare con privilegi zero in piedi e di fornire un livello di difesa contro le vulnerabilità derivanti dall'accesso amministrativo permanente. Per l'accesso con privilegi è necessario approvare l'esecuzione di tutte le attività in cui è stato definito un criterio di approvazione associato. Gli utenti che desiderano eseguire le attività incluse nel criterio di approvazione devono richiedere e ricevere l'approvazione dell'accesso.

Per abilitare la gestione degli accessi con privilegi, vedere [Configure Privileged Access Management](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration).

Per ulteriori informazioni, vedere [gestione degli accessi con privilegi](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview).

### <a name="security-information-and-event-management-siem-software-for-microsoft-365-logging"></a>Software di sicurezza e gestione eventi (SIEM) per la registrazione di Microsoft 365

Il software di SIEM eseguito su un server esegue un'analisi in tempo reale degli avvisi di sicurezza e degli eventi creati dalle applicazioni e dall'hardware di rete. Per consentire al server SIEM di includere gli avvisi e gli eventi di sicurezza di Microsoft 365 nelle sue funzioni di analisi e Reporting, integrare Azure AD in You SEIM. Vedere [Introduzione all'integrazione del registro di Azure](https://docs.microsoft.com/azure/security/security-azure-log-integration-overview).

## <a name="next-step"></a>Passaggio successivo

Se si sta configurando l'identità per la sottoscrizione Microsoft 365, vedere:

- [Identità solo cloud](cloud-only-identities.md) se si utilizza l'identità solo cloud
- [Preparare la sincronizzazione della directory](prepare-for-directory-synchronization.md) se si utilizza l'identità ibrida

  
## <a name="see-also"></a>Vedere anche

[Guida di orientamento alla sicurezza di Microsoft 365](https://docs.microsoft.com/office365/securitycompliance/security-roadmap)
