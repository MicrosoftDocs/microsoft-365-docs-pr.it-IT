---
title: Domande frequenti sulla crittografia dei messaggi
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 05/22/2020
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 0432dce9-d9b6-4e73-8a13-4a932eb0081e
description: Hai una domanda sul funzionamento delle nuove funzionalità di protezione dei messaggi? Verificare la disponibilità di una risposta qui.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1bb5e93b08b74f5691c76e9a59bf9fa970e08f36
ms.sourcegitcommit: 8950d3cb0f3087be7105e370ed02c7a575d00ec2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "50597196"
---
# <a name="message-encryption-faq"></a>Domande frequenti sulla crittografia dei messaggi

Hai una domanda sul funzionamento delle nuove funzionalità di protezione dei messaggi? Verificare la disponibilità di una risposta qui. Inoltre, esaminare le domande frequenti sulla protezione dei dati [in Azure Information Protection](https://docs.microsoft.com/information-protection/get-started/faqs-rms) per risposte a domande sul servizio di protezione dei dati, Azure Rights Management, in Azure Information Protection.

## <a name="what-is-office-365-message-encryption-ome"></a>Che cos'è Office 365 Message Encryption (OME)?

OME combina la crittografia della posta elettronica e le funzionalità di rights management. Le funzionalità di Rights management si basano sulla tecnologia Azure Information Protection.

## <a name="who-can-use-ome"></a>Chi può usare OME?

È possibile utilizzare le nuove funzionalità per OME nelle condizioni seguenti:
  
- Se non è mai stato configurato OME o IRM per Exchange Online in Office 365.

- Se OME e IRM sono stati impostati, è possibile utilizzare questi passaggi se si utilizza il servizio Azure Rights Management di Azure Information Protection.

- Se si utilizza Exchange Online con Active Directory Rights Management Service (AD RMS), non è possibile abilitare immediatamente queste nuove funzionalità. È invece necessario eseguire prima [la migrazione di AD RMS ad Azure Information Protection.](https://docs.microsoft.com/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms) Al termine della migrazione, è possibile configurare correttamente OME.

  Se si sceglie di continuare a utilizzare AD RMS locale con Exchange Online anziché eseguire la migrazione ad Azure Information Protection, non sarà possibile utilizzare queste nuove funzionalità.

## <a name="what-subscriptions-do-i-need-to-use-the-new-ome-capabilities"></a>Quali sottoscrizioni sono necessarie per usare le nuove funzionalità di OME?

Per usare le nuove funzionalità di OME, è necessario uno dei piani seguenti:
  
- La crittografia dei messaggi di Office 365 è disponibile come parte di Office 365 Enterprise E3 ed E5, Microsoft Enterprise E3 ed E5, Microsoft 365 Business Premium, Office 365 A1, A3 e A5 e Office 365 Government G3 e G5. I clienti non hanno bisogno di licenze aggiuntive per ricevere le nuove funzionalità di protezione basate su Azure Information Protection.

- È inoltre possibile aggiungere Azure Information Protection Piano 1 ai piani seguenti per ricevere le nuove funzionalità di crittografia dei messaggi di Office 365: Exchange Online Piano 1, Exchange Online Piano 2, Office 365 F1, Microsoft 365 Business Basic, Microsoft 365 Business Standard o Office 365 Enterprise E1.

- Ogni utente che trae vantaggio dalla crittografia dei messaggi di Office 365 deve essere concesso in licenza per essere coperto dalla funzionalità.

- Per l'elenco completo, vedere le [descrizioni del](https://technet.microsoft.com/library/exchange-online-service-description.aspx) servizio Exchange Online per la crittografia dei messaggi di Office 365.

## <a name="can-i-use-exchange-online-with-bring-your-own-key-byok-in-azure-information-protection"></a>È possibile usare Exchange Online con bring your own key (BYOK) in Azure Information Protection?

Sì. Microsoft consiglia di completare la procedura per configurare BYOK prima di configurare OME.
  
Per ulteriori informazioni su BYOK, vedere Pianificazione e implementazione della [chiave tenant di Azure Information Protection.](https://docs.microsoft.com/information-protection/plan-design/plan-implement-tenant-key)
  
## <a name="do-ome-and-byok-with-azure-information-protection-change-microsofts-approach-to-third-party-data-requests-such-as-subpoenas"></a>OME e BYOK con Azure Information Protection modificano l'approccio di Microsoft alle richieste di dati di terze parti, ad esempio i compari?

No. OME e l'opzione per fornire e controllare le proprie chiavi di crittografia, denominate BYOK, da Azure Information Protection non sono state progettate per rispondere alle richieste di comparizione delle forze dell'ordine. OME, con BYOK per Azure Information Protection, è stato progettato per i clienti incentrati sulla conformità. Microsoft prende molto seriamente in considerazione le richieste di terze parti per i dati dei clienti. In qualità di provider di servizi cloud, sosteniamo sempre la privacy dei dati dei clienti. Nel caso in cui riceviamo una citazione in citazione, tentiamo sempre di reindirizzare la terza parte al cliente per ottenere le informazioni. (Leggi il blog di Brad Smith: [Protezione dei dati dei clienti da snooping governativi).](https://blogs.microsoft.com/blog/2013/12/04/protecting-customer-data-from-government-snooping/) Microsoft pubblica periodicamente informazioni dettagliate sulla richiesta ricevuta. Per ulteriori informazioni sulle richieste di [](https://www.microsoft.com/trustcenter/privacy/govt-requests-for-data) dati di terze parti, vedere Rispondere alle richieste del governo e delle forze dell'ordine per accedere ai dati dei clienti nel Centro protezione Microsoft. Inoltre, vedere "Divulgazione dei dati dei clienti" nelle Condizioni [dei servizi online (OST).](https://www.microsoft.com/Licensing/product-licensing/products.aspx)
  
## <a name="how-is-this-feature-related-to-legacy-office-365-message-encryption-ome-and-information-rights-management-irm-features"></a>In che modo questa funzionalità è correlata alle funzionalità legacy di Crittografia messaggi di Office 365 e Information Rights Management (IRM) ?

Le nuove funzionalità per la crittografia dei messaggi di Office 365 sono un'evoluzione delle soluzioni IRM e OME legacy esistenti. Nella tabella seguente sono disponibili ulteriori dettagli.
  
**Confronto tra OME legacy, IRM e nuove funzionalità di OME**

| Funzionalità | Versioni precedenti di OME | IRM | Nuove funzionalità di OME |
|:-----|:-----|:-----|:-----|
|**Invio di un messaggio di posta elettronica crittografato**|Solo tramite le regole del flusso di posta di Exchange|Utente finale avviato da Outlook per Windows, Outlook per Mac o Outlook sul Web; o tramite le regole del flusso di posta di Exchange|Utente finale avviato da Outlook per Windows, Outlook per Mac o Outlook sul Web; o tramite regole del flusso di posta|
|**Gestione dei diritti**|-|Opzione Non inoltrare e modelli personalizzati|Opzione Non inoltrare, opzione di sola crittografia, modelli predefiniti e personalizzati|
|**Tipo di destinatario supportato**|Solo destinatari esterni|Solo destinatari interni|Destinatari interni ed esterni|
|**Esperienza per il destinatario**|I destinatari esterni hanno ricevuto un messaggio HTML che hanno scaricato e aperto in un browser o in un'app per dispositivi mobili scaricata.|I destinatari interni hanno ricevuto solo messaggi di posta elettronica crittografati in Outlook per Windows, Outlook per Mac e Outlook sul Web.|I destinatari interni ed esterni ricevono messaggi di posta elettronica in Outlook per Windows, Outlook per Mac, Outlook sul Web, Outlook per Android e Outlook per iOS oppure tramite un portale Web, indipendentemente dal fatto che siano o meno nella stessa organizzazione o in qualsiasi organizzazione. Il portale OME non richiede alcun download separato.|
|**Supporto bring your own key**|Non disponibile|Non disponibile| BYOK supportato|

## <a name="how-do-i-enable-the-new-ome-capabilities-for-my-organization"></a>Come si abilitano le nuove funzionalità di OME per l'organizzazione?

Vedere [Configurare le nuove funzionalità di crittografia dei messaggi di Office 365.](set-up-new-message-encryption-capabilities.md)
  
## <a name="will-the-previous-version-of-ome-be-deprecated"></a>La versione precedente di OME sarà deprecata?

È ancora possibile usare la versione precedente di OME, che non sarà deprecata al momento. Tuttavia, è consigliabile che le organizzazioni usino la nuova e migliorata soluzione OME. I clienti che non hanno già distribuito OME non possono configurare una nuova distribuzione della versione precedente di OME.
  
## <a name="my-organization-uses-active-directory-rights-management-can-i-use-this-functionality"></a>L'organizzazione utilizza Active Directory Rights Management, è possibile utilizzare questa funzionalità?

No. Se si utilizza Exchange Online con Active Directory Rights Management Service (AD RMS), non è possibile abilitare immediatamente queste nuove funzionalità. È invece necessario eseguire prima [la migrazione di AD RMS ad Azure Information Protection.](https://docs.microsoft.com/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)
  
## <a name="my-organization-has-an-exchange-hybrid-deployment-can-i-use-this-feature"></a>L'organizzazione ha una distribuzione ibrida di Exchange. È possibile utilizzare questa funzionalità?

Gli utenti locali possono inviare posta crittografata utilizzando le regole del flusso di posta di Exchange Online. A tale scopo, è necessario instradare la posta elettronica tramite Exchange Online. Per ulteriori informazioni, vedere Parte 2: Configurare il flusso di posta dal server di posta elettronica [a Microsoft 365.](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-2-configure-mail-to-flow-from-your-email-server-to-office-365)
  
## <a name="what-email-client-do-i-need-to-use-in-order-to-create-an-ome-encrypted-message-what-applications-are-supported-for-sending-protected-messages"></a>Quale client di posta elettronica è necessario utilizzare per creare un messaggio crittografato con OME? Quali applicazioni sono supportate per l'invio di messaggi protetti?

È possibile creare messaggi protetti da Outlook 2016, Outlook 2013 per Windows e Mac e da Outlook sul Web. Per ulteriori informazioni sull'invio di messaggi crittografati, vedere Inviare, visualizzare e rispondere [ai messaggi crittografati in Outlook per PC.](https://support.microsoft.com/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980?ui=en-us&rs=en-us&ad=us)
  
## <a name="what-email-clients-are-supported-to-read-and-reply-to-protected-emails"></a>Quali client di posta elettronica sono supportati per leggere e rispondere ai messaggi di posta elettronica protetti?

Gli utenti di Microsoft 365 possono leggere e rispondere da Outlook per Windows e Mac (2013 e 2016), Outlook sul Web e Outlook mobile (Android e iOS). È inoltre possibile utilizzare il client di posta nativo di iOS se l'organizzazione lo consente. Se non si è un utente di Microsoft 365, è possibile leggere e rispondere ai messaggi crittografati sul Web tramite il Web browser.

## <a name="what-email-clients-support-the-encrypt-only-protected-emails"></a>Quali client di posta elettronica supportano i messaggi di posta elettronica protetti solo con crittografia?

Gli utenti di Microsoft 365 possono usare Outlook per PC versioni 2019 e Microsoft 365 per creare posta protetta con i criteri di sola crittografia.  Ciò significa che i messaggi a cui è applicato il nuovo criterio di sola crittografia possono essere letti direttamente in Outlook sul Web, in Outlook per iOS e Android e ora in Outlook per PC versioni 2019 e Microsoft 365.

## <a name="is-there-a-size-limit-for-messages-you-can-send-with-ome"></a>Esiste un limite di dimensione per i messaggi che è possibile inviare con OME?

Sì. La dimensione massima dei messaggi che è possibile inviare con OME, inclusi gli allegati, è 25 MB. Per ulteriori informazioni, vedere [Limiti relativi ai messaggi.](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#message-limits-1)

## <a name="what-file-types-are-supported-as-attachments-in-protected-emails-do-attachments-inherit-the-protection-policies-associated-with-protected-emails"></a>Quali tipi di file sono supportati come allegati nei messaggi di posta elettronica protetti? Gli allegati ereditano i criteri di protezione associati ai messaggi di posta elettronica protetti?

È possibile allegare qualsiasi tipo di file a un messaggio di posta elettronica protetto. Con un'eccezione, i criteri di protezione vengono applicati solo ai formati di file indicati nei tipi di [file supportati dal client Azure Information Protection.](https://docs.microsoft.com/information-protection/rms-client/client-admin-guide-file-types) OME non supporta le versioni 97-2003 delle applicazioni di Office seguenti: Word (doc), Excel (xls) e PowerPoint (ppt).

Se è supportato un formato di file, ad esempio un file di Word, Excel o PowerPoint, il file è sempre protetto, anche dopo che l'allegato è stato scaricato dal destinatario. Si supponga, ad esempio, che un allegato sia protetto da Non inoltrare. Il destinatario originale scarica il file, crea un messaggio a un nuovo destinatario e allega il file. Quando il nuovo destinatario riceve il file, il destinatario non sarà in grado di aprire il file protetto.
  
## <a name="are-pdf-file-attachments-supported"></a>Gli allegati di file PDF sono supportati?

La risposta breve è sì. La crittografia PDF consente di proteggere i documenti PDF sensibili tramite comunicazioni protette o la collaborazione protetta. Quando si invia un messaggio di posta elettronica, il servizio Office 365 crittografa gli allegati di file PDF non il client Outlook.

Per Outlook sul Web, Outlook per iOS e Outlook per Android, è possibile crittografare i PDF inviati senza ulteriori passaggi. Questi client supportano in modo nativo la crittografia PDF.

Il desktop di Outlook non supporta in modo nativo la crittografia degli allegati di file PDF. Sarà invece necessario configurare le regole del flusso di posta di Exchange o DLP per applicare prima la crittografia agli allegati PDF. Quando si invia un messaggio di posta elettronica da Outlook Desktop con un allegato PDF, il client invia prima il messaggio con l'allegato al servizio. Quando il servizio riceve il file, il servizio applica la protezione OME del criterio di prevenzione della perdita dei dati (DLP) o della regola del flusso di posta in Exchange Online. Successivamente, Exchange Online invia il messaggio con il file PDF protetto allegato.

Per abilitare la crittografia per gli allegati PDF, eseguire il seguente comando in [PowerShell di Exchange Online:](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)

```powershell
Set-IRMConfiguration -EnablePdfEncryption $true
```

La crittografia PDF consente di proteggere i documenti PDF sensibili tramite comunicazioni protette o la collaborazione protetta. Per tutti i client Outlook, i messaggi e gli allegati PDF non protetti ereditano la protezione OME del criterio di prevenzione della perdita di dati (DLP) o della regola del flusso di posta in Exchange Online. Inoltre, se un utente di Outlook sul Web allega un documento PDF non protetto e applica la protezione al messaggio, il messaggio eredita la protezione del messaggio. Gli utenti possono aprire gli allegati crittografati solo in applicazioni che supportano PDF protetti (ad esempio, il portale OME e il visualizzatore di Azure Information Protection).

> [!IMPORTANT]
> Il client desktop di Outlook non supporta la crittografia PDF.

## <a name="are-onedrive-for-business-attachments-supported"></a>Gli allegati di OneDrive for Business sono supportati?

Not yet. Gli allegati di OneDrive for Business non sono supportati e gli utenti finali non possono crittografare un messaggio contenente un allegato di OneDrive for Business cloud.
  
## <a name="what-email-clients-support-preview-of-encrypted-attachments-in-protected-emails"></a>Quali client di posta elettronica supportano l'anteprima degli allegati crittografati nei messaggi di posta elettronica protetti?

Quando gli allegati sono protetti con un messaggio di posta elettronica protetto, i client Outlook offrono la possibilità di visualizzare direttamente l'anteprima del documento. Outlook supporta l'anteprima dei documenti di Office (docx, xlsx, pptx, doc, xls, ppt). Outlook sul Web supporta l'anteprima dei documenti di Office (docx, xlsx, pptx) e PDF.  

## <a name="what-email-clients-support-revocation-of-protected-emails"></a>Quali client di posta elettronica supportano la revoca dei messaggi di posta elettronica protetti?

Outlook sul Web supporta la revoca della posta protetta.  Per [informazioni dettagliate, vedere](https://docs.microsoft.com/microsoft-365/compliance/revoke-ome-encrypted-mail?view=o365-worldwide#how-to-revoke-an-encrypted-message-that-you-sent) Come revocare un messaggio crittografato inviato dall'utente.


## <a name="can-i-automatically-encrypt-messages-by-setting-up-policies"></a>È possibile crittografare automaticamente i messaggi configurando i criteri?

Sì. Utilizzare le regole del flusso di posta in Exchange Online per crittografare automaticamente un messaggio in base a determinate condizioni. Ad esempio, è possibile creare criteri basati sull'ID destinatario, sul dominio del destinatario o sul contenuto del corpo o dell'oggetto del messaggio. Vedere [Definire le regole del flusso di posta per crittografare i messaggi di posta elettronica in Office 365.](define-mail-flow-rules-to-encrypt-email.md)
  
## <a name="can-i-automatically-remove-encryption-on-incoming-and-outgoing-mail"></a>È possibile rimuovere automaticamente la crittografia nella posta in arrivo e in uscita?

Gli amministratori possono configurare una regola del flusso di posta per rimuovere la crittografia per la posta in uscita. Non è possibile configurare una regola per rimuovere la crittografia per la posta in arrivo.

## <a name="can-i-automatically-encrypt-messages-by-setting-up-policies-in-data-loss-prevention-dlp-through-the-security-amp-compliance-center"></a>È possibile crittografare automaticamente i messaggi configurando criteri in Prevenzione della perdita di dati (DLP) tramite il Centro &amp; sicurezza e conformità?

Sì. È possibile configurare le regole del flusso di posta in Exchange Online o tramite DLP nel Centro &amp; sicurezza e conformità.
  
## <a name="can-i-customize-encrypted-messages-with-my-company-branding"></a>È possibile personalizzare i messaggi crittografati con la personalizzazione della società?

Sì. Per informazioni sulla personalizzazione dei messaggi di posta elettronica e del portale OME, vedere Aggiungere il marchio dell'organizzazione ai messaggi crittografati. Vedere [Aggiungere il marchio dell'organizzazione ai messaggi crittografati.](add-your-organization-brand-to-encrypted-messages.md)
  
## <a name="are-there-any-reporting-capabilities-or-insights-for-encrypted-emails"></a>Sono disponibili funzionalità di creazione di report o informazioni dettagliate per i messaggi di posta elettronica crittografati?

È disponibile un report crittografia nel Centro sicurezza e conformità. Vedere Visualizzare i report di sicurezza della posta elettronica nel [Centro sicurezza & conformità.](../security/office-365-security/view-email-security-reports.md)
  
## <a name="can-i-use-message-encryption-with-compliance-features-such-as-ediscovery"></a>È possibile utilizzare la crittografia dei messaggi con funzionalità di conformità come eDiscovery?

Sì. Tutti i messaggi di posta elettronica crittografati sono individuabili dalle funzionalità di conformità di Microsoft 365.

## <a name="can-i-remove-encryption-from-email"></a>È possibile rimuovere la crittografia dalla posta elettronica?

Gli amministratori possono configurare una regola del flusso di posta per rimuovere la crittografia. Non è possibile rimuovere la crittografia utilizzando una regola del flusso di posta dalla posta applicata da un'altra organizzazione, a meno che la posta non venga incririzzata utilizzando la protezione solo crittografia.

## <a name="is-delegated-access-supported"></a>L'accesso delegato è supportato?

Non in questo momento.

## <a name="can-i-send-as-a-shared-mailbox-and-encrypt-emails"></a>È possibile inviare messaggi come cassetta postale condivisa e crittografare i messaggi di posta elettronica?

Quando un utente invia un messaggio di posta elettronica che corrisponde a una regola del flusso di posta elettronica di crittografia, il messaggio viene crittografato prima di essere inviato.

## <a name="can-i-open-encrypted-messages-sent-to-a-shared-mailbox"></a>È possibile aprire i messaggi crittografati inviati a una cassetta postale condivisa?

Sì. I messaggi crittografati sono supportati per una cassetta postale condivisa.

- Gli utenti possono aprire i messaggi di posta protetti in una cassetta postale condivisa in cui la cassetta postale condivisa ha ricevuto una posta protetta come parte di un gruppo di distribuzione.

- Gli utenti possono visualizzare gli allegati che ereditano la protezione dalla posta elettronica quando utilizzano Outlook per Windows, Outlook per Mac e Outlook sul Web.

Nella tabella seguente sono elencati i client supportati per le cassette postali condivise.

| Piattaforma | Lettura della posta | Visualizzare gli allegati di posta elettronica |
|----------|-----------|------------------------|
| Outlook sul Web | Sì | Sì                |
|  Outlook per Windows| Sì | Sì                |
| Outlook per Mac    | Sì | Sì                |
| Outlook per Android| Sì | No                 |
| Outlook per iOS    | Sì | No                 |
|

Esistono attualmente due limitazioni note:

- Non è possibile aprire allegati ai messaggi di posta elettronica ricevuti nei dispositivi mobili utilizzando Outlook Mobile.

- Non è possibile l'assegnazione tramite un gruppo di sicurezza abilitato alla posta elettronica. Microsoft supporta solo l'accesso fornito dall'assegnazione diretta dell'utente alla cassetta postale condivisa e tale mapping automatico è abilitato per Exchange Online. Il mapping automatico è abilitato per impostazione predefinita per Exchange Online.

**Per assegnare un utente alla cassetta postale condivisa**

1. [Connettersi a Exchange Online utilizzando Remote PowerShell.](https://technet.microsoft.com/library/jj984289?v=exchg.150%29.aspx)

2. Eseguire il cmdlet Add-MailboxPermission con il parametro Automapping. In questo esempio a Ayla vengono concesse le autorizzazioni di accesso completo a una cassetta postale di supporto.

   ```powershell
   Add-MailboxPermission -Identity support@contoso.onmicrosoft.com -User ayla@contoso.com -AccessRights FullAccess -AutoMapping $true
   ```
   
 ## <a name="can-i-open-encrypted-messages-sent-to-another-users-mailbox-with-fullaccess"></a>È possibile aprire i messaggi crittografati inviati alla cassetta postale di un altro utente con Accesso completo?

Gli utenti possono aprire i messaggi crittografati purché gli sia stato assegnato l'accesso diretto e il mapping automatico sia attivato. L'accesso non è consentito se l'accesso viene concesso tramite un gruppo di sicurezza abilitato alla posta elettronica.

## <a name="what-do-i-do-if-i-dont-receive-the-one-time-pass-code-after-i-requested-it"></a>Cosa fare se non si riceve il pass code una volta richiesto?

Prima di tutto, controllare la cartella posta indesiderata nel client di posta elettronica. Le impostazioni DKIM e DMARC per l'organizzazione potrebbero causare il filtro di questi messaggi di posta elettronica come posta indesiderata.

Successivamente, controllare la quarantena nel Centro sicurezza & conformità. Spesso, i messaggi contenenti un pass code una sola volta, in particolare i primi che l'organizzazione riceve, finiscono in quarantena.
