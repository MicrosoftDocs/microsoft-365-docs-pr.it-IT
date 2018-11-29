Vedere anche [Prerequisiti](https://docs.microsoft.com/microsoft-365-enterprise/identity-access-policies#prerequisites) per ulteriori consigli sull'infrastruttura di gestione delle identità.

<a name="crit-identity-user-groups"></a>
### <a name="required-all-users-groups-and-group-memberships-have-been-created"></a>Obbligatorio: sono stati creati tutti gli utenti, i gruppi e l'appartenenza ai gruppi

Gli account e i gruppi utente sono stati creati in modo che:

- I dipendenti dell'organizzazione e i fornitori, i terzisti e i partner della stessa abbiano un account utente corrispondente in Azure Active Directory (AD).
- I gruppi di Azure AD e i relativi membri contengano account utente e altri gruppi per scopi diversi, come il provisioning delle impostazioni di sicurezza per i servizi cloud Microsoft, la gestione delle licenze automatica e altri utilizzi.

Se necessario, il [Passaggio 1](../identity-plan-users-groups.md) può aiutare a soddisfare questo requisito.

<a name="crit-identity-sync"></a>
### <a name="required-users-and-groups-are-synchronized-with-azure-ad"></a>Obbligatorio: gli utenti e i gruppi sono sincronizzati con Azure AD

Se si dispone di un provider di identità locale esistente, come Windows Server Active Directory (AD), è stato utilizzato Azure AD Connect per sincronizzare i gruppi e gli account utente dal provider di identità locale al tenant di Azure AD.

Grazie alla sincronizzazione della directory, gli utenti possono accedere a Office 365 e agli altri servizi cloud Microsoft utilizzando le stesse credenziali che usano per l'accesso ai loro computer e alle risorse locali.

Se necessario, il [Passaggio 7](../identity-azure-ad-connect.md) può aiutare a soddisfare questo requisito.

Se si ignora questo requisito, saranno disponibili due set di account utente e gruppi:

- Gli account utente e i gruppi esistenti nel provider di identità locale
- Gli account utente e i gruppi esistenti nel tenant di Azure AD

In questo stato, i due set di account e gruppi utente dovranno essere gestiti manualmente sia dagli utenti che dagli amministratori IT. Questo comporterà inevitabilmente la mancata sincronizzazione di account, password e gruppi.

#### <a name="how-to-test"></a>Come eseguire il test
Per verificare il corretto funzionamento dell'autenticazione con le credenziali locali, accedere al portale di Office 365 con le credenziali locali.

Per verificare il corretto funzionamento della sincronizzazione della directory, eseguire le operazioni seguenti:

1.  Creare un nuovo gruppo di test in Windows Server AD.
2.  Attendere la sincronizzazione.
3.  Controllare il tenant di Azure AD per verificare che venga visualizzato il nome del nuovo gruppo di test.

<a name="crit-identity-global-admin"></a>
### <a name="required-your-global-administrator-accounts-are-protected"></a>Obbligatorio: gli account di amministratore globale sono protetti 

Gli [account di amministratore globale di Office 365 sono stati protetti](https://support.office.com/article/Protect-your-Office-365-global-administrator-accounts-6b4ded77-ac8d-42ed-8606-c014fd947560) per evitare che vengano compromesse le credenziali e che quindi possa esserci la violazione di una sottoscrizione a Office 365.

Se si ignora questo requisito, gli account di amministratore globale potrebbero essere soggetti ad attacchi e violazioni, consentendo a terzi l'acquisizione di dati e l'utilizzo di tali informazioni per scopi di raccolta, distruzione o ricatto.

Se necessario, il [Passaggio 2](../identity-designate-protect-admin-accounts.md) può aiutare a soddisfare questo requisito.

#### <a name="how-to-test"></a>Come eseguire il test

Utilizzare questa procedura per verificare che gli account di amministratore globale siano protetti:

1. Eseguire il seguente comando di Azure AD v2 dal prompt dei comandi di PowerShell. Dovrebbe essere visualizzato solo l'elenco degli account di amministratore globale dedicati.
   ```
   Get-AzureADDirectoryRole | where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
   ```
2. Accedere a Office 365 utilizzando ognuno degli account del Passaggio 1. Ogni accesso dovrà richiedere l'autenticazione a più fattori e la forma più avanzata di autenticazione secondaria disponibile nell'organizzazione.

> [!Note]
> Vedere [Connettersi a PowerShell di Office 365](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell) per le istruzioni sull'istallazione del modulo Azure AD PowerShell v2 e sull'accesso a Office 365.

<a name="crit-identity-custom-sign-in"></a>
### <a name="optional-the-office-365-sign-in-screen-is-personalized-for-your-organization"></a>Facoltativo: la schermata di accesso a Office 365 è personalizzata per l'organizzazione

È stata utilizzata la procedura descritta in [Aggiungere il marchio dell'azienda alla pagina di accesso e alle pagine del riquadro di accesso](http://aka.ms/aadpaddbranding) per aggiungere le informazioni personalizzate distintive dell'azienda nella pagina di accesso di Office 365.

Se si ignora questa opzione, gli utenti visualizzeranno una schermata generica di accesso a Office 365 e non avranno la certezza di effettuare l'accesso al sito dell'organizzazione.

Se necessario, il [Passaggio 11](../identity-customize-office-365-sign-in.md) può aiutare con questa opzione.

#### <a name="how-to-test"></a>Come eseguire il test

Accedere al portale di Office 365 con il nome dell'account utente e l'autenticazione a più fattori. Dovrebbero essere visualizzati gli elementi di personalizzazione nella pagina di accesso.

<a name="crit-identity-mfa"></a>
### <a name="optional-multi-factor-authentication-is-enabled-for-your-users"></a>Facoltativo: l'autenticazione a più fattori è abilitata per gli utenti

È stata utilizzata la procedura descritta in [Pianificare l'autenticazione a più fattori per le distribuzioni di Office 365](https://support.office.com/article/Plan-for-multifactor-authentication-for-Office-365-Deployments-043807b2-21db-4d5c-b430-c8a6dee0e6ba) e [Configurare l'autenticazione a più fattori per gli utenti di Office 365](https://support.office.com/article/Set-up-multi-factor-authentication-for-Office-365-users-8f0454b2-f51a-4d9c-bcde-2c48e41621c6) per abilitare l'autenticazione a più fattori (MFA) per gli account utente.

Se si ignora questa opzione, gli account utente saranno vulnerabili alla violazione delle credenziali ad opera di possibili attacchi informatici. In caso di violazione della password di un account utente, tutte le risorse e le funzionalità dell'account (come i ruoli di amministratore) saranno a disposizione dell'utente malintenzionato, che potrà copiare, distruggere o conservare a scopo di ricatto documenti interni o altri dati.

Se necessario, il [Passaggio 5](../identity-multi-factor-authentication.md) può aiutare con questa opzione.

#### <a name="how-to-test"></a>Come eseguire il test

1.  Creare un account utente di test nel portale di amministrazione di Office 365 e assegnargli una licenza. 
2.  Configurare l'autenticazione a più fattori per l'account utente di test con il metodo di verifica aggiuntivo in uso per gli account utente effettivi, come per esempio l'invio di un messaggio al telefono. 
3.  Accedere al portale di Office 365 o di Azure con l'account utente di test.
4.  Verificare che l'autenticazione a più fattori richieda all'utente ulteriori informazioni di verifica e abbia esito positivo. 
5.  Eliminare l'account utente di test.

<a name="crit-identity-sync-health"></a>
### <a name="optional-directory-synchronization-is-monitored"></a>Facoltativo: la sincronizzazione delle directory viene monitorata

È stata consultata la documentazione disponibile in [Uso di Azure AD Connect Health per la sincronizzazione](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) (per la sincronizzazione delle password) o in [Uso di Azure AD Connect Health con AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) (per l'autenticazione federata) ed è stato implementato Azure AD Connect Health, che implica quanto segue:

- L'installazione dell'agente di Azure AD Connect Health su ciascuno dei server di identità locale.
- L'utilizzo del portale di Azure AD Connect Health per monitorare lo stato della sincronizzazione in corso.

Se si ignora questa opzione, è possibile valutare in maniera più precisa lo stato dell'infrastruttura di gestione delle identità basata sul cloud.

Se necessario, il [Passaggio 8](../identity-azure-ad-connect-health.md) può aiutare con questa opzione.

#### <a name="how-to-test"></a>Come eseguire il test
Il portale di Azure AD Connect Health mostra lo stato attuale e corretto dei server di identità locale e la sincronizzazione in corso.

<a name="crit-identity-pw-reset"></a>
### <a name="optional-users-can-reset-their-own-passwords"></a>Facoltativo: gli utenti possono reimpostare la propria password

È stata utilizzata la procedura descritta in [Distribuzione rapida della reimpostazione della password self-service di Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started) per configurare la reimpostazione della password per gli utenti.

Se non si soddisfa questa condizione, gli utenti dovranno dipendere dagli amministratori degli account utente per reimpostare le proprie password, con un sovraccarico sull'amministrazione IT.

Se necessario, il [Passaggio 4](../identity-password-reset.md) può aiutare con questa opzione.

#### <a name="how-to-test"></a>Come eseguire il test

1. Creare un account utente di test con una password iniziale.
2. Utilizzare i passaggi illustrati in [Consentire agli utenti di reimpostare le loro password in Office 365](https://support.office.com/article/Let-users-reset-their-own-passwords-in-Office-365-5bc3f460-13cc-48c0-abd6-b80bae72d04a) per reimpostare la password dell'account utente di test.
3. Disconnettersi ed effettuare di nuovo l'accesso con l'account utente di test con la nuova password.
4. Eliminare l'account utente di test.

<a name="crit-identity-pw-writeback"></a>
### <a name="optional-password-writeback-is-enabled-for-your-users"></a>Facoltativo: il writeback delle password è abilitato per gli utenti

Sono state utilizzate le istruzioni riportate in [Reimpostazione delle password in modalità self-service di Azure AD con writeback delle password](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started) per abilitare il writeback delle password per il tenant di Azure AD per la sottoscrizione di Microsoft 365 Enterprise.

Se si ignora questa opzione, gli utenti che non sono connessi con il server locale devono reimpostare o sbloccare le password di Windows Server AD tramite un amministratore IT.

Se necessario, il [Passaggio 9](../identity-password-writeback.md) può aiutare con questa opzione.

>[!Note]
>Il writeback delle password è necessario per utilizzare al meglio le funzioni di Azure AD Identity Protection, come la richiesta agli utenti di cambiare le password locali nel caso in cui Azure AD rilevi un alto rischio di violazione dell'account.
>

#### <a name="how-to-test"></a>Come eseguire il test

Per testare il writeback delle password, è necessario cambiare la password in Office 365. Dovrebbe essere possibile usare l'account e la nuova password per accedere alle risorse di Windows Server AD locale.

1. Creare un account utente di test per Windows Server AD locale, consentire la sincronizzazione della directory e concedere una licenza di Office 365 nel portale di amministrazione di Office 365.
2. Accedere al computer e al portale di Office 365 con le credenziali dell'account utente di test da un computer remoto nel dominio di Windows Server AD locale.
3. Selezionare **Impostazioni > Impostazioni di Office 365 > Password > Cambia password**.
4. Digitare la password corrente, inserirne una nuova e quindi confermarla.
5. Disconnettersi dal portale di Office 365 e dal computer remoto e quindi accedere al computer utilizzando l'account utente di test e la relativa nuova password. Questo passaggio dimostra che è stato possibile cambiare la password di un account utente di Windows Server AD locale tramite il tenant di Azure AD.

<a name="crit-identity-sso"></a>
### <a name="optional-users-can-sign-in-using-single-sign-on"></a>Facoltativo: gli utenti possono accedere utilizzando Single Sign-On

È stato abilitato [Azure AD Connect: accesso Single Sign-On facile](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start) per l'organizzazione, con lo scopo di semplificare l'accesso degli utenti alle applicazioni basate sul cloud, come Office 365.

Se si ignora questa opzione, gli utenti potrebbero dover immettere le credenziali quando accedono alle applicazioni aggiuntive che utilizzano Azure AD.

Se necessario, il [Passaggio 10](../identity-single-sign-on.md) può aiutare con questa opzione.


<a name="crit-identity-group-license"></a>
### <a name="optional-group-based-licensing-to-automatically-assign-and-remove-licenses-to-user-accounts-based-on-group-membership"></a>Facoltativo: gestione delle licenze basate su gruppo per assegnare e rimuovere automaticamente le licenze degli account utente in base all'appartenenza ai gruppi

È stata [abilitata la gestione delle licenze basate su gruppo](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal) per i gruppi di sicurezza di Azure AD appropriati in modo che le licenze di Office 365 ed EMS vengano assegnate o rimosse automaticamente.

Se si ignora questa opzione, sarà necessario eseguire manualmente i seguenti passaggi:

- Assegnare le licenze ai nuovi utenti che dovranno accedere a Office 365 ed EMS.
- Rimuovere le licenze dagli utenti che non fanno più parte dell'organizzazione o non hanno accesso a Office 365 ed EMS.

Se necessario, il [Passaggio 12](../identity-group-based-licensing.md) può aiutare con questa opzione.

#### <a name="how-to-test"></a>Come eseguire il test

1. Creare un gruppo di sicurezza in Azure AD con il portale di Azure e configurare la gestione delle licenze basate su gruppo per assegnare le licenze di Office 365 ed EMS.
2. Creare un account utente di test in Azure AD e aggiungerlo al gruppo di sicurezza di test.
3. Esaminare le proprietà dell'account utente nel portale di amministrazione di Office 365 per verificare che le licenze di Office 365 e EMS siano state assegnate.
4. Rimuovere l'account utente di test dal gruppo di sicurezza di test.
5. Esaminare le proprietà dell'account utente per verificare che non disponga più delle licenze di Office 365 ed EMS.
6. Eliminare il gruppo di sicurezza di test e l'account utente di test.

<a name="crit-identity-dyn-groups"></a>
### <a name="optional-dynamic-group-membership-settings-automatically-add-user-accounts-to-groups-based-on-user-account-attributes"></a>Facoltativo: le impostazioni di appartenenza a gruppi dinamici aggiungono automaticamente gli account utente ai gruppi in base agli attributi degli account utente

È stato configurato il set di gruppi dinamici di Azure AD e sono state utilizzate le istruzioni presenti in [Creare regole basate su attributi per l'appartenenza dinamica ai gruppi in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal) per creare i gruppi e le regole che determinano il set di attributi dell'account utente e i valori di appartenenza ai gruppi.

Se si ignora questa opzione, l'appartenenza ai gruppi deve essere eseguita manualmente quando vengono aggiunti nuovi account o se gli attributi degli account utente cambiano con il tempo. Ad esempio, se un utente passa dal Reparto vendite al Reparto contabilità, è necessario:

- Aggiornare il valore dell'attributo del reparto per quell'account utente.
- Rimuovere manualmente l'account dal gruppo delle vendite.
- Aggiungere manualmente l'account al gruppo della contabilità.

Se il gruppo delle vendite e il gruppo della contabilità erano gruppi dinamici, sarà necessario solo cambiare il valore del reparto dell'account utente.

Se necessario, il [Passaggio 15](../identity-automatic-group-membership.md) può aiutare con questa opzione.

#### <a name="how-to-test"></a>Come eseguire il test

1. Creare un gruppo di test dinamico in Azure AD con il portale di Azure e configurare una regola il reparto uguale a "test1".
2. Creare un account utente di test in Azure AD e impostare la proprietà del reparto su "test1".
3. Esaminare le proprietà dell'account utente per verificare che sia un membro del gruppo dinamico di test.
4. Cambiare il valore della proprietà del reparto per l'account utente di test impostandolo su "test2".
5. Esaminare le proprietà dell'account utente per verificare che non sia più membro del gruppo dinamico di test.
6. Eliminare il gruppo dinamico di test e l'account utente di test.

<a name="crit-identity-self-service-groups"></a>
### <a name="optional-self-service-group-management-is-enabled-for-specific-azure-ad-security-and-office-365-groups"></a>Facoltativo: la gestione dei gruppi in modalità self-service è abilitata per specifici gruppi di sicurezza di Azure AD e Office 365

È stato stabilito quali gruppi soddisfano i requisiti per la gestione in modalità self-service, i relativi proprietari sono stati istruiti sulle responsabilità e sul flusso di lavoro della gestione dei gruppi ed [è stata configurata la gestione in modalità self-service in Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management) per tali gruppi.

Se si ignora questa opzione, tutte le attività di gestione dei gruppi di Azure AD, dovranno essere eseguite dagli amministratori IT.

Se necessario, il [Passaggio 14](../identity-self-service-group-management.md) può aiutare con questa opzione.

#### <a name="how-to-test"></a>Come eseguire il test
1.  Creare un account utente di test in Azure AD con il portale di Azure.
2.  Accedere con l'account utente di test e creare un gruppo di sicurezza di test di Azure AD.
3.  Disconnettersi ed effettuare di nuovo l'accesso con l'account amministratore IT.
4.  Configurare il gruppo di sicurezza di test per la gestione in modalità self-service dell'account utente di test.
5.  Disconnettersi ed effettuare di nuovo l'accesso con l'account utente di test.
6.  Utilizzare il portale di Azure per aggiungere membri al gruppo di sicurezza di test.
7.  Eliminare il gruppo di sicurezza di test e l'account utente di test.

<a name="crit-identity-ident-prot"></a>
### <a name="optional-azure-ad-identity-protection-is-enabled-to-protect-against-credential-compromise"></a>Facoltativo: Azure AD Identity Protection è abilitato per proteggere le credenziali da eventuali violazioni

Azure AD Identity Protection è stato abilitato per:

- Far fronte a potenziali vulnerabilità delle identità.
- Rilevare possibili tentativi di violazione delle credenziali.
- Ricercare le cause e risolvere attività sospette relative alle identità.

Se si ignora questa opzione, non sarà possibile rilevare o contrastare tentativi di violazione delle credenziali o ricercare le cause dei problemi di sicurezza relativi alle identità. Questo potrebbe rendere l'organizzazione vulnerabile alla violazione delle credenziali e alla conseguente minaccia ai dati sensibili.

Se necessario, il [Passaggio 6](../identity-azure-ad-identity-protection.md) può aiutare con questa opzione.

<a name="crit-identity-pim"></a>
### <a name="optional-you-have-set-up-privileged-identity-management-to-support-on-demand-assignment-of-the-global-administrator-role"></a>Facoltativo: è stato configurato Privileged Identity Management per supportare l'assegnazione su richiesta del ruolo di amministratore globale

Sono state utilizzate le istruzioni presenti in [Configurare Azure AD Privileged Identity Management](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure) per abilitare PIM nel tenant di Azure AD e sono stati configurati gli account di amministratore globale idonei per il ruolo di amministratori.

Inoltre, sono stati seguiti i consigli presenti in [Protezione dell'accesso con privilegi per le distribuzioni ibride e cloud in Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices) per sviluppare una roadmap che protegga l'accesso con privilegi dagli attacchi informatici.

Se si ignora questa opzione, gli account di amministratore globale potranno essere soggetti ad attacco online e, se violati, un utente malintenzionato potrà raccogliere, distruggere o conservare le informazioni riservate a scopo di ricatto.

Se necessario, il [Passaggio 3](../identity-azure-ad-identity-protection.md) può aiutare con questa opzione.
