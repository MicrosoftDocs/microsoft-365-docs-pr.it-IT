<a name="crit-infoprotect-step1"></a>
### <a name="required-security-and-information-protection-levels-for-your-organization-are-defined"></a>Necessario: vengono definiti i livelli di protezione delle informazioni e di sicurezza dell'organizzazione

Sono stati pianificati e determinati i livelli di sicurezza in base alle esigenze dell'organizzazione. Questi livelli definiscono un livello minimo di sicurezza e livelli aggiuntivi per informazioni sempre più riservate e la relativa sicurezza dei dati necessaria.

Vengono utilizzati almeno tre livelli di protezione delle informazioni:

- Protezione di base
- Dati sensibili
- Protezione per ambienti altamente regolamentati

Se necessario, il [Passaggio 1](../infoprotect-define-sec-infoprotect-levels.md) può aiutare a soddisfare questo requisito. 

<a name="crit-infoprotect-step4"></a>
### <a name="required-increased-security-for-office-365-is-configured"></a>Necessario: è stata configurata maggiore sicurezza per Office 365

Sono state configurate le seguenti impostazioni per aumentare la sicurezza in base alle informazioni in [Configurare il tenant di Office 365 per una maggiore sicurezza](https://support.office.com/article/Configure-your-Office-365-tenant-for-increased-security-8d274fe3-db51-4107-ba64-865e7155b355):

- Criteri di gestione delle minacce nel Centro sicurezza e conformità di Office 365
- Impostazioni tenant aggiuntive di Exchange Online
- Criteri di condivisione del tenant nell'interfaccia di amministrazione di SharePoint
- Impostazioni di Azure Active Directory

È stata anche abilitata [Office 365 Advanced Threat Protection (ATP)](https://support.office.com/article/Office-365-ATP-for-SharePoint-OneDrive-and-Microsoft-Teams-26261670-db33-4c53-b125-af0662c34607#turniton).

Se necessario, il [Passaggio 3](../infoprotect-configure-increased-security-office-365.md) può aiutare a soddisfare questo requisito. 

<a name="crit-infoprotect-step3"></a>
### <a name="optional-classification-is-configured-across-your-environment"></a>Facoltativo: la classificazione è configurata nell'ambiente

Si è collaborato con i team legale e della conformità per sviluppare una classificazione appropriata e uno schema di etichettatura per i dati dell'organizzazione, che può includere:

- Tipi di dati riservati
- Etichette di Office 365
- Etichette di Azure Information Protection

Se necessario, il [Passaggio 2](../infoprotect-configure-classification.md) può aiutare a soddisfare questo requisito. 

<a name="crit-infoprotect-step5"></a>
### <a name="optional-configure-privileged-access-management-in-office-365"></a>Facoltativo: configurare la gestione degli accessi con privilegi in Office 365

Le informazioni dell’argomento [Configurare la gestione degli accessi con privilegi in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) sono state usate per consentire l'accesso con privilegi e creare uno o più criteri di accesso con privilegi all'interno dell'organizzazione di Office 365. I criteri sono stati configurati e l'accesso just-in-time è abilitato per l'accesso a dati sensibili o a impostazioni di configurazione cruciali.

Se necessario, il [Passaggio 4](../infoprotect-configure-privileged-access-management.md) può aiutare a soddisfare questo requisito. 
