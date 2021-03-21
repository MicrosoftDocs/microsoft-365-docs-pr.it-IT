---
title: Configurare le nuove funzionalità di Message Encryption
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 4/30/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 7ff0c040-b25c-4378-9904-b1b50210d00e
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: Scopri di più sulle nuove funzionalità crittografiche di Office 365, che consentono di comunicare tramite posta elettronica in sicurezza con le persone all’interno e all’esterno dell’organizzazione.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1519748c4bd535e0a3ea1cc3ee653e2c81e807bd
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919392"
---
# <a name="set-up-new-message-encryption-capabilities"></a>Configurare le nuove funzionalità di Message Encryption

Le nuove funzionalità di Office 365 Message Encryption (OME) consentono alle organizzazioni di condividere la posta elettronica protetta con qualsiasi dispositivo. Gli utenti possono scambiare messaggi protetti con altre organizzazioni di Microsoft 365, oltre che con clienti che usano Outlook.com, Gmail e altri servizi di posta elettronica.

Seguire questa procedura per verificare che le nuove funzionalità di OME siano disponibili nell'organizzazione.

## <a name="verify-that-azure-rights-management-is-active"></a>Verificare che Azure Rights Management sia attivo

Le nuove funzionalità di OME sfruttano le caratteristiche di protezione di [Azure Rights Management Services (Azure RMS)](/azure/information-protection/what-is-information-protection), la tecnologia usata da [Azure Information Protection](/azure/information-protection/what-is-azure-rms) per proteggere i messaggi di posta elettronica e i documenti tramite crittografia e controlli di accesso.

L'unico requisito necessario per usare le nuove funzionalità di OME è che [Azure Rights Management](/azure/information-protection/what-is-azure-rms) debba essere attivato nel tenant dell'organizzazione. In tal caso, Microsoft 365 attiva automaticamente le nuove funzionalità di OME e non è necessario eseguire alcuna operazione.

Azure RMS viene attivato automaticamente anche per la maggior parte dei piani idonei, pertanto non è necessario eseguire alcuna operazione a tal riguardo. Per altre informazioni, vedere [Attivazione di Azure Rights Management](/azure/information-protection/activate-service).

>[!IMPORTANT]
>Se si usa Active Directory Rights Management Services (AD RMS) con Exchange Online, è necessario [eseguire la migrazione ad Azure Information Protection](/azure/information-protection/migrate-from-ad-rms-to-azure-rms) prima di poter usare le nuove funzionalità di OME. OME non è compatibile con AD RMS.  

Per ulteriori informazioni, vedere:

- [Quali abbonamenti sono necessari per usare le nuove funzionalità di OME? ](ome-faq.md#what-subscriptions-do-i-need-to-use-the-new-ome-capabilities) per verificare se il piano di abbonamento include Azure Information Protection (che include le funzionalità di Azure RMS).
- Per informazioni sull'acquisto di un abbonamento idoneo, vedere [Azure Information Protection](https://azure.microsoft.com/services/information-protection/).  

### <a name="manually-activating-azure-rights-management"></a>Attivazione manuale di Azure Rights Management

Se è stato disabilitato Azure RMS o se non è stato attivato automaticamente, è possibile attivarlo manualmente in:

- **Interfaccia di amministrazione di Microsoft 365**: per istruzioni, vedere [Come attivare Azure Rights Management dall'interfaccia di amministrazione](/azure/information-protection/activate-office365).
- **Portale di Azure**: per istruzioni, vedere [Come attivare Azure Rights Management dal Portale di Azure](/azure/information-protection/activate-azure).

## <a name="configure-management-of-your-azure-information-protection-tenant-key"></a>Configurare la gestione della chiave tenant di Azure Information Protection

Questo passo è facoltativo. A Microsoft è consentita la gestione della chiave radice di Azure Information Protection per impostazione predefinita ed è la procedura consigliata per la maggior parte delle organizzazioni. Se questo è il caso, non è necessario eseguire alcuna operazione.

Ci sono diversi motivi, ad esempio i requisiti di conformità, che possono richiedere di generare e gestire una chiave radice, nota anche come bring your own key (BYOK). In questo caso, è consigliabile completare i passaggi necessari prima di configurare le nuove funzionalità di OME. Per altre informazioni, vedere [Pianificazione e implementazione della chiave tenant di Azure Information Protection](/information-protection/plan-design/plan-implement-tenant-key).

## <a name="verify-new-ome-configuration-in-exchange-online-powershell"></a>Verificare la nuova configurazione di OME in PowerShell di Exchange Online

È possibile verificare se il tenant di Microsoft 365 è configurato correttamente per l'uso delle nuove funzionalità di OME disponibili in [PowerShell di Exchange Online](/powershell/exchange/exchange-online-powershell).
  
1. [Connettersi a PowerShell di Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell) usando un account con autorizzazioni di amministratore globale nel tenant di Microsoft 365.

2. Eseguire il cmdlet Get-IRMConfiguration.

     Dovrebbe essere visualizzato un valore di $True per il parametro AzureRMSLicensingEnabled, che indica che OME è configurato nel tenant. Se non lo è, usare Set-IRMConfiguration per impostare il valore di AzureRMSLicensingEnabled su $True per abilitare OME.

3. Eseguire il cmdlet Test-IRMConfiguration usando la sintassi seguente:

     ```powershell
     Test-IRMConfiguration [-Sender <email address >]
     ```  

   **Esempio**:

     ```powershell
     Test-IRMConfiguration -Sender securityadmin@contoso.com
     ```

     - L'inserimento di un indirizzo di posta elettronica del mittente è facoltativo, ma forza il sistema a eseguire ulteriori controlli. Usare l'indirizzo e-mail di un utente nel tenant di Microsoft 365.

     Il risultato dovrebbe essere simile al seguente:

     ```text
     Results : Acquiring RMS Templates ...
                - PASS: RMS Templates acquired.  Templates available: Contoso  - Confidential View Only, Contoso  - Confidential, Do Not
            Forward.
            Verifying encryption ...
                - PASS: Encryption verified successfully.
            Verifying decryption ...
                - PASS: Decryption verified successfully.
            Verifying IRM is enabled ...
                - PASS: IRM verified successfully.

            OVERALL RESULT: PASS
     ```

   - Il nome dell'organizzazione sostituirà *Contoso*.

   - I nomi dei modelli predefiniti potrebbero essere diversi rispetto a quelli visualizzati in precedenza. Per altre informazioni, vedere [Configurazione e gestione dei modelli per Azure Information Protection](/azure/information-protection/configure-policy-templates).

4. Eseguire il cmdlet Remove-PSSession per disconnettersi dal servizio Rights Management.

     ```powershell
     Remove-PSSession $session
     ```

## <a name="next-steps-define-mail-flow-rules-to-use-new-ome-capabilities"></a>Passaggi successivi: definire le regole del flusso di posta per usare le nuove funzionalità di OME

Se in precedenza sono state configurate regole del flusso di posta per crittografare la posta elettronica nell'organizzazione, è necessario aggiornare le regole esistenti per usare le nuove funzionalità di OME. Per le nuove distribuzioni, è necessario creare nuove regole per il flusso di posta.

>[!IMPORTANT]
>In caso contrario, gli utenti continueranno a ricevere messaggi crittografati che usano il formato dell'allegato HTML precedente invece della nuova esperienza di OME.

Le regole del flusso di posta elettronica determinano le condizioni con cui i messaggi di posta elettronica devono essere crittografati e le condizioni per rimuovere la crittografia. Quando si imposta un'azione per una regola, tutti i messaggi che soddisfano le condizioni della regola vengono crittografati al momento dell'invio.
  
Per altre passaggi sulla creazione delle regole del flusso di posta elettronica di OME, vedere [Definire le regole del flusso di posta elettronica per crittografare i messaggi di posta elettronica in Office 365](define-mail-flow-rules-to-encrypt-email.md).

Aggiornare le regole esistenti per usare le nuove funzionalità di OME:

1. Nell'interfaccia di amministrazione di Microsoft 365, passare a **Interfacce di amministrazione > Exchange**.
2. Nell'interfaccia di amministrazione di Exchange, passare a **Flusso di posta > Regole**.
3. Per ogni regola, in **Fai quanto segue**:
    - Selezionare **Modifica la sicurezza del messaggio**.
    - Selezionare **Applica Office 365 Message Encryption e la protezione tramite diritti**.
    - Selezionare un modello RMS dall'elenco.
    - Selezionare **Salva**.
    - Selezionare **OK**.