<a name="crit-infoprotect-step1"></a>
### <a name="required-security-and-information-protection-levels-for-your-organization-are-defined"></a>Necessario: vengono definiti i livelli di protezione delle informazioni e di sicurezza dell'organizzazione

Sono stati pianificati e determinati i livelli di sicurezza in base alle esigenze dell'organizzazione. Questi livelli definiscono un livello minimo di sicurezza e livelli aggiuntivi per informazioni sempre più riservate e la relativa sicurezza dei dati necessaria.

Come minimo, si usano tre livelli di sicurezza:

- Protezione di base
- Dati sensibili
- Protezione per ambienti altamente regolamentati

Se necessario, il [Passaggio 1](../infoprotect-define-sec-infoprotect-levels.md) può aiutare a soddisfare questo requisito. 

<a name="crit-infoprotect-step3"></a>
### <a name="required-increased-security-for-microsoft-365-is-configured"></a>Obbligatorio: è stato configurato un livello di sicurezza maggiore per Microsoft 365

Sono state configurate le impostazioni seguenti per una [sicurezza maggiore di Microsoft 365](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security):

- Criteri di gestione delle minacce nel Centro sicurezza Microsoft 365
- Impostazioni tenant aggiuntive di Exchange Online
- Criteri di condivisione del tenant nell'interfaccia di amministrazione di SharePoint Online
- Impostazioni di Azure Active Directory (Azure AD)

È stato inoltre [abilitato Office 365 Advanced Threat Protection (ATP) per SharePoint Online, OneDrive e Microsoft Teams](https://docs.microsoft.com/office365/securitycompliance/turn-on-atp-for-spo-odb-and-teams).

Se necessario, il [Passaggio 3](../infoprotect-configure-increased-security-office-365.md) può aiutare a soddisfare questo requisito. 

<a name="crit-infoprotect-step2"></a>
### <a name="optional-classification-is-configured-across-your-environment"></a>Facoltativo: la classificazione è configurata nell'ambiente

Si è collaborato con i team legale e della conformità per sviluppare una classificazione appropriata e uno schema di etichettatura per la governance dei dati dell'organizzazione e i criteri di sicurezza. 

I criteri corrispondono alla configurazione e distribuzione di:

- Tipi di dati riservati
- Etichette di conservazione
- Etichette di riservatezza
- Etichette di Azure Information Protection

Se necessario, il [Passaggio 2](../infoprotect-configure-classification.md) può aiutare a soddisfare questo requisito. 


<a name="crit-infoprotect-step4"></a>
### <a name="optional-windows-information-protection-is-deployed-across-your-environment"></a>Facoltativo: Windows Information Protection viene distribuito nel proprio ambiente

I dispositivi Windows 10 Enterprise registrati hanno un criterio di Intune distribuito e applicato che definisce:

- Quali applicazioni proteggere.
- Il livello di protezione.
- L’estensione della protezione.

Se necessario, il [Passaggio 4](../infoprotect-deploy-windows-information-protection.md) può aiutare a soddisfare questo requisito. 

<a name="crit-infoprotect-step5"></a>
### <a name="optional-data-loss-prevention-dlp-is-deployed"></a>Facoltativo: Prevenzione perdita di dati (DLP)

Il set di criteri DLP è stato analizzato, testato e quindi distribuito - con le posizioni e le regole con condizioni e azioni- richieste dall'organizzazione per la protezione dei clienti e altri tipi di dati riservati e conformarsi alle normative e i requisiti locali e industriali.

Il personale di sicurezza e conformità dati utilizza il dashboard di Sicurezza e conformità per monitorare gli eventi imprevisti del DLP.

Se necessario, il [Passaggio 5](../infoprotect-data-loss-prevention.md) può aiutare a soddisfare questo requisito. 

<a name="crit-infoprotect-step6"></a>
### <a name="optional-email-encryption-is-configured"></a>Facoltativo: la crittografia della posta elettronica è configurata

La crittografia della posta elettronica seguente è stata configurata in base alle esigenze dell'organizzazione:

|||
|:-------|:-----|
| **Metodo di crittografia** | **Per la posta elettronica inviata** |
| [Office 365 Message Encryption (OME)](https://docs.microsoft.com/Office365/SecurityCompliance/ome)  | A contatti esterni all'organizzazione con la crittografia |
| [Information Rights Management (IRM)](https://docs.microsoft.com/office365/SecurityCompliance/information-rights-management-in-exchange-online) | Sia con crittografia che con le autorizzazioni |
| [S/MIME (Secure/Multipurpose Internet Mail Extensions)](https://docs.microsoft.com/Exchange/policy-and-compliance/smime) | Sia con la crittografia che con le firme digitale con crittografia a chiave pubblica |
|||

Se necessario, il [Passaggio 6](../infoprotect-email-encryption.md) può aiutare a soddisfare questo requisito.

<a name="crit-infoprotect-step7"></a>
### <a name="optional-configure-privileged-access-management-in-office-365"></a>Facoltativo: configurare la gestione degli accessi con privilegi in Office 365

Sono state usate le informazioni contenute nell'argomento [Configurare la gestione degli accessi con privilegi in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) per abilitare l'accesso con privilegi e creare uno o più criteri di accesso con privilegi all'interno dell'organizzazione. I criteri sono stati configurati ed è abilitato l'accesso just-in-time ai dati sensibili o alle impostazioni di configurazione critiche.

Se necessario, il [Passaggio 7](../infoprotect-configure-privileged-access-management.md) può aiutare a soddisfare questo requisito. 
