---
title: Criteri uscita dell'infrastruttura di protezione delle informazioni
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/25/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Esaminare i criteri relativi ai servizi e all'infrastruttura basati sulla protezione delle informazioni per verificare che la configurazione soddisfi i criteri di Microsoft 365 Enterprise.
ms.openlocfilehash: 9c74a3994a1a404583326f65f1cec579fccbe659
ms.sourcegitcommit: 3b2d3e2b38c4860db977e73dda119a465c669fa4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "33400040"
---
# <a name="information-protection-infrastructure-exit-criteria"></a>Criteri uscita dell'infrastruttura di protezione delle informazioni

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

Verificare che l'infrastruttura di protezione delle informazioni soddisfi i criteri obbligatori seguenti e assicurarsi di tenere in considerazione quelli facoltativi.

<a name="crit-infoprotect-step1"></a>
## <a name="required-security-and-information-protection-levels-for-your-organization-are-defined"></a>Necessario: vengono definiti i livelli di protezione delle informazioni e di sicurezza dell'organizzazione

Sono stati pianificati e determinati i livelli di sicurezza in base alle esigenze dell'organizzazione. Questi livelli definiscono un livello minimo di sicurezza e livelli aggiuntivi per informazioni sempre più riservate e la relativa sicurezza dei dati necessaria.

Come minimo, si usano tre livelli di sicurezza:

- Protezione di base
- Dati sensibili
- Protezione per ambienti altamente regolamentati

Se necessario, il [Passaggio 1](infoprotect-define-sec-infoprotect-levels.md) può aiutare a soddisfare questo requisito. 

<a name="crit-infoprotect-step3"></a>
## <a name="required-increased-security-for-microsoft-365-is-configured"></a>Obbligatorio: è stato configurato un livello di sicurezza maggiore per Microsoft 365

Sono state configurate le impostazioni seguenti per una [sicurezza maggiore di Office 365](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security):

- Criteri di gestione delle minacce nel Centro sicurezza Microsoft 365
- Impostazioni tenant aggiuntive di Exchange Online
- Criteri di condivisione del tenant nell'interfaccia di amministrazione di SharePoint Online
- Impostazioni di Azure Active Directory (Azure AD)

È stato inoltre [abilitato Office 365 Advanced Threat Protection (ATP) per SharePoint Online, OneDrive e Microsoft Teams](https://docs.microsoft.com/office365/securitycompliance/turn-on-atp-for-spo-odb-and-teams).

Se necessario, il [Passaggio 3](infoprotect-configure-increased-security-office-365.md) può aiutare a soddisfare questo requisito. 

<a name="crit-infoprotect-step2"></a>
## <a name="optional-classification-is-configured-across-your-environment"></a>Facoltativo: la classificazione è configurata nell'ambiente

Si è collaborato con i team legale e della conformità per sviluppare una classificazione appropriata e uno schema di etichettatura per la governance dei dati dell'organizzazione e i criteri di sicurezza. 

I criteri corrispondono alla configurazione e distribuzione di:

- Tipi di dati riservati
- Etichette di conservazione
- Etichette di riservatezza
- Etichette di Azure Information Protection

Se necessario, il [Passaggio 2](infoprotect-configure-classification.md) può aiutare a soddisfare questo requisito. 


<a name="crit-infoprotect-step4"></a>
## <a name="optional-windows-information-protection-is-deployed-across-your-environment"></a>Facoltativo: Windows Information Protection viene distribuito nel proprio ambiente

I dispositivi Windows 10 Enterprise registrati hanno un criterio di Intune distribuito e applicato che definisce:

- Quali applicazioni proteggere.
- Il livello di protezione.
- L’estensione della protezione.

Se necessario, il [Passaggio 4](infoprotect-deploy-windows-information-protection.md) può aiutare a soddisfare questo requisito. 

<a name="crit-infoprotect-step5"></a>
## <a name="optional-office-365-data-loss-prevention-dlp-is-deployed"></a>Facoltativo: Prevenzione perdita di dati (DLP) di Office 365

Il set di criteri DLP è stato analizzato, testato e quindi distribuito - con le posizioni e le regole con condizioni e azioni- richieste dall'organizzazione per la protezione dei clienti e altri tipi di dati riservati e conformarsi alle normative e i requisiti locali e industriali.

Il personale di sicurezza e conformità dati utilizza il dashboard di Sicurezza e conformità di Office 365 per monitorare gli eventi imprevisti del DLP.

Se necessario, il [Passaggio 5](infoprotect-data-loss-prevention.md) può aiutare a soddisfare questo requisito. 


<a name="crit-infoprotect-step6"></a>
## <a name="optional-configure-privileged-access-management-in-office-365"></a>Facoltativo: configurare la gestione degli accessi con privilegi in Office 365

Sono state usate le informazioni contenute nell'argomento [Configurare la gestione degli accessi con privilegi in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) per abilitare l'accesso con privilegi e creare uno o più criteri di accesso con privilegi all'interno dell'organizzazione. I criteri sono stati configurati ed è abilitato l'accesso just-in-time ai dati sensibili o alle impostazioni di configurazione critiche.

Se necessario, il [Passaggio 6](infoprotect-configure-privileged-access-management.md) può aiutare a soddisfare questo requisito. 

## <a name="results-and-next-steps"></a>Risultati e passaggi successivi

L'infrastruttura di protezione delle informazioni per Microsoft 365 Enterprise usa livelli di sicurezza definiti, maggiore sicurezza per Office 365, classificazione con etichette e tipi di dati riservati, Windows Information Protection, criteri di prevenzione della perdita di dati e gestione degli accessi con privilegi.

Se si sta seguendo la distribuzione end-to-end di Microsoft 365 Enterprise, è possibile a questo punto far sì che i [carichi di lavoro e gli scenari](deploy-workloads.md) sfruttino tutte le funzionalità e la configurazione dell'infrastruttura di base.
