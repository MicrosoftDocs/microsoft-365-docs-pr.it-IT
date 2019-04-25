<a name="crit-infoprotect-step1"></a>
### <a name="required-security-and-information-protection-levels-for-your-organization-are-defined"></a>Necessario: vengono definiti i livelli di protezione delle informazioni e di sicurezza dell'organizzazione

Sono stati pianificati e determinati i livelli di sicurezza in base alle esigenze dell'organizzazione. Questi livelli definiscono un livello minimo di sicurezza e livelli aggiuntivi per informazioni sempre più riservate e la relativa sicurezza dei dati necessaria.

Come minimo, si usano tre livelli di sicurezza:

- Protezione di base
- Dati sensibili
- Protezione per ambienti altamente regolamentati

Se necessario, il [Passaggio 1](../infoprotect-define-sec-infoprotect-levels.md) può aiutare a soddisfare questo requisito. 

<a name="crit-infoprotect-step4"></a>
### <a name="required-increased-security-for-microsoft-365-is-configured"></a>Obbligatorio: è stata configurato un livello di sicurezza maggiore per Microsoft 365

Sono state configurate le impostazioni seguenti per una [sicurezza maggiore di Office 365](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security):

- Criteri di gestione delle minacce nel Centro sicurezza di Microsoft 365
- Impostazioni tenant aggiuntive di Exchange Online
- Criteri di condivisione del tenant nell'interfaccia di amministrazione di SharePoint
- Impostazioni di Azure Active Directory (Azure AD)

È stato inoltre [abilitato Office 365 Advanced Threat Protection (ATP) per SharePoint Online, OneDrive e Microsoft Teams.](https://docs.microsoft.com/it-IT/office365/securitycompliance/turn-on-atp-for-spo-odb-and-teams)

Se necessario, il [Passaggio 3](../infoprotect-configure-increased-security-office-365.md) può aiutare a soddisfare questo requisito. 

<a name="crit-infoprotect-step3"></a>
### <a name="optional-classification-is-configured-across-your-environment"></a>Facoltativo: la classificazione è configurata nell'ambiente

Si è collaborato con i team legale e della conformità per sviluppare una classificazione appropriata e uno schema di etichettatura per la governance dei dati dell'organizzazione e i criteri di sicurezza.  

I criteri corrispondono alla configurazione e distribuzione di:

- Tipi di dati riservati
- Etichette di conservazione
- Etichette di riservatezza
- Etichette di Azure Information Protection

Se necessario, il [Passaggio 2](../infoprotect-configure-classification.md) può aiutare a soddisfare questo requisito. 

<a name="crit-infoprotect-step5"></a>
### <a name="optional-configure-privileged-access-management-in-office-365"></a>Facoltativo: configurare la gestione degli accessi con privilegi in Office 365

Sono state usate le informazioni contenute nell’argomento [Configurare la gestione degli accessi con privilegi in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) per abilitare l'accesso con privilegi e creare uno o più criteri di accesso con privilegi all'interno dell'organizzazione. I criteri sono stati configurati ed è abilitato l'accesso just-in-time ai dati sensibili o alle impostazioni di configurazione critiche.

Se necessario, il [Passaggio 4](../infoprotect-configure-privileged-access-management.md) può aiutare a soddisfare questo requisito. 
