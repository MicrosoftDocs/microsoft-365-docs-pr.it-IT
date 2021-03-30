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
ms.openlocfilehash: 589a28690d1654576ace45edd482b8d67161d616
ms.sourcegitcommit: c75aac39ee8d93218a79585113ef6b36f47c9ddf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/29/2021
ms.locfileid: "51408591"
---
# <a name="message-encryption-faq"></a>Domande frequenti sulla crittografia dei messaggi

Hai una domanda sul funzionamento delle nuove funzionalità di protezione dei messaggi? Verificare la disponibilità di una risposta qui. Inoltre, esaminare le domande frequenti sulla protezione dei dati [in Azure Information Protection](/information-protection/get-started/faqs-rms) per risposte a domande sul servizio di protezione dei dati, Azure Rights Management, in Azure Information Protection.

## <a name="what-is-office-365-message-encryption-ome"></a>Che cos'è La crittografia dei messaggi di Office 365 ??

OME combina la crittografia della posta elettronica e le funzionalità di rights management. Le funzionalità di Rights management si basano sulla tecnologia Azure Information Protection.

## <a name="who-can-use-ome"></a>Chi può usare OME?

È possibile utilizzare le nuove funzionalità per OME nelle condizioni seguenti:
  
- Se non è mai stato configurato OME o IRM per Exchange Online in Office 365.

- Se sono stati impostati OME e IRM, è possibile utilizzare questi passaggi se si utilizza il servizio Azure Rights Management da Azure Information Protection.

- Se si utilizza Exchange Online con Active Directory Rights Management Service (AD RMS), non è possibile abilitare subito queste nuove funzionalità. È invece necessario eseguire prima [la migrazione di AD RMS ad Azure Information Protection.](/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms) Al termine della migrazione, è possibile configurare correttamente OME.

  Se si sceglie di continuare a usare AD RMS locale con Exchange Online anziché eseguire la migrazione ad Azure Information Protection, non sarà possibile utilizzare queste nuove funzionalità.

## <a name="what-subscriptions-do-i-need-to-use-the-new-ome-capabilities"></a>Quali sottoscrizioni sono necessarie per usare le nuove funzionalità OME?

Per usare le nuove funzionalità OME, è necessario uno dei piani seguenti:
  
- La crittografia dei messaggi di Office 365 è disponibile nell'ambito di Office 365 Enterprise E3 ed E5, Microsoft Enterprise E3 ed E5, Microsoft 365 Business Premium, Office 365 A1, A3 e A5 e Office 365 Government G3 e G5. I clienti non necessitano di licenze aggiuntive per ricevere le nuove funzionalità di protezione basate su Azure Information Protection.

- È inoltre possibile aggiungere Azure Information Protection Piano 1 ai piani seguenti per ricevere le nuove funzionalità di crittografia dei messaggi di Office 365: Exchange Online Piano 1, Exchange Online Piano 2, Office 365 F1, Microsoft 365 Business Basic, Microsoft 365 Business Standard o Office 365 Enterprise E1.

- Ogni utente che beneficia della crittografia dei messaggi di Office 365 deve essere concesso in licenza per essere coperto dalla funzionalità.

- Per l'elenco completo, vedere le [descrizioni del](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description) servizio Exchange Online per la crittografia dei messaggi di Office 365.

## <a name="can-i-use-exchange-online-with-bring-your-own-key-byok-in-azure-information-protection"></a>Posso usare Exchange Online con bring your own key (BYOK) in Azure Information Protection?

Sì. Microsoft consiglia di completare la procedura per configurare BYOK prima di configurare OME.
  
Per ulteriori informazioni su BYOK, vedere [Planning and implementing your Azure Information Protection tenant key.](/information-protection/plan-design/plan-implement-tenant-key)
  
## <a name="do-ome-and-byok-with-azure-information-protection-change-microsofts-approach-to-third-party-data-requests-such-as-subpoenas"></a>OME e BYOK con Azure Information Protection modificano l'approccio di Microsoft alle richieste di dati di terze parti, ad esempio i mandati di comparizione?

No. OME e l'opzione per fornire e controllare le proprie chiavi di crittografia, denominate BYOK, da Azure Information Protection non sono state progettate per rispondere alle richieste di comparizione delle forze dell'ordine. OME, con BYOK per Azure Information Protection, è stato progettato per i clienti incentrati sulla conformità. Microsoft prende sul serio le richieste di terze parti per i dati dei clienti. In qualità di provider di servizi cloud, sosteniamo sempre la privacy dei dati dei clienti. Nel caso in cui riceviamo un mandato di comparizione, tentiamo sempre di reindirizzare la terza parte al cliente per ottenere le informazioni. (Leggere il blog di Brad Smith: [Protezione dei dati dei clienti dallo snooping governativo](https://blogs.microsoft.com/blog/2013/12/04/protecting-customer-data-from-government-snooping/)). Microsoft pubblica periodicamente informazioni dettagliate sulla richiesta ricevuta. Per ulteriori informazioni sulle richieste di dati di terze parti, vedere [Risposta alle](https://www.microsoft.com/trustcenter/privacy/govt-requests-for-data) richieste del governo e delle forze dell'ordine per accedere ai dati dei clienti nel Centro protezione Microsoft. Vedere anche "Divulgazione dei dati dei clienti" nelle Condizioni [dei servizi online (OST).](https://www.microsoft.com/Licensing/product-licensing/products.aspx)
  
## <a name="how-is-this-feature-related-to-legacy-office-365-message-encryption-ome-and-information-rights-management-irm-features"></a>In che modo questa funzionalità è correlata alle funzionalità legacy di Crittografia messaggi di Office 365 (OME) e Information Rights Management (IRM) ?

Le nuove funzionalità per la crittografia dei messaggi di Office 365 sono un'evoluzione delle soluzioni IRM e OME legacy esistenti. Nella tabella seguente sono disponibili ulteriori dettagli.
  
**Confronto tra OME legacy, IRM e nuove funzionalità OME**

| Funzionalità | Versioni precedenti di OME | IRM | Nuove funzionalità OME |
|:-----|:-----|:-----|:-----|
|**Invio di un messaggio di posta elettronica crittografato**|Solo tramite le regole del flusso di posta di Exchange|Utente finale avviato da Outlook per Windows, Outlook per Mac o Outlook sul Web; o tramite le regole del flusso di posta di Exchange|Utente finale avviato da Outlook per Windows, Outlook per Mac o Outlook sul Web; o tramite regole del flusso di posta|
|**Gestione dei diritti**|-|Opzione Non inoltrare e modelli personalizzati|Opzione Non inoltrare, opzione di sola crittografia, modelli predefiniti e personalizzati|
|**Tipo di destinatario supportato**|Solo destinatari esterni|Solo destinatari interni|Destinatari interni ed esterni|
|**Esperienza per il destinatario**|I destinatari esterni hanno ricevuto un messaggio HTML che hanno scaricato e aperto in un browser o in un'app per dispositivi mobili scaricata.|I destinatari interni hanno ricevuto solo messaggi di posta elettronica crittografati in Outlook per Windows, Outlook per Mac e Outlook sul Web.|I destinatari interni ed esterni ricevono messaggi di posta elettronica in Outlook per Windows, Outlook per Mac, Outlook sul Web, Outlook per Android e Outlook per iOS o tramite un portale Web, indipendentemente dal fatto che siano o meno nella stessa organizzazione o in qualsiasi organizzazione. Il portale OME non richiede alcun download separato.|
|**Supporto per Bring Your Own Key**|Non disponibile|Non disponibile| BYOK supportato|

## <a name="how-do-i-enable-the-new-ome-capabilities-for-my-organization"></a>Come si abilitano le nuove funzionalità OME per l'organizzazione?

Vedere [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md).
  
## <a name="will-the-previous-version-of-ome-be-deprecated"></a>La versione precedente di OME verrà deprecata?

È comunque possibile utilizzare la versione precedente di OME, non sarà deprecata al momento. Tuttavia, è consigliabile incoraggiare le organizzazioni a utilizzare la soluzione OME nuova e migliorata. I clienti che non hanno già distribuito OME non possono configurare una nuova distribuzione della versione precedente di OME.
  
## <a name="my-organization-uses-active-directory-rights-management-can-i-use-this-functionality"></a>L'organizzazione utilizza Active Directory Rights Management, è possibile utilizzare questa funzionalità?

No. Se si utilizza Exchange Online con Active Directory Rights Management Service (AD RMS), non è possibile abilitare subito queste nuove funzionalità. È invece necessario eseguire prima [la migrazione di AD RMS ad Azure Information Protection.](/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)
  
## <a name="my-organization-has-an-exchange-hybrid-deployment-can-i-use-this-feature"></a>L'organizzazione ha una distribuzione ibrida di Exchange. È possibile utilizzare questa funzionalità?

Gli utenti locali possono inviare posta crittografata utilizzando le regole del flusso di posta di Exchange Online. A tale scopo, è necessario instradare la posta elettronica tramite Exchange Online. Per ulteriori informazioni, vedere [Part 2: Configure mail to flow from your email server to Microsoft 365](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#part-2-configure-mail-to-flow-from-your-email-server-to-office-365).
  
## <a name="what-email-client-do-i-need-to-use-in-order-to-create-an-ome-encrypted-message-what-applications-are-supported-for-sending-protected-messages"></a>Quale client di posta elettronica è necessario utilizzare per creare un messaggio crittografato OME? Quali applicazioni sono supportate per l'invio di messaggi protetti?

È possibile creare messaggi protetti da Outlook 2016, Outlook 2013 per Windows e Mac e da Outlook sul Web. Per ulteriori informazioni sull'invio di messaggi crittografati, vedere [Send, view, and reply to encrypted messages in Outlook for PC](https://support.microsoft.com/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980?ui=en-us&rs=en-us&ad=us).
  
## <a name="what-email-clients-are-supported-to-read-and-reply-to-protected-emails"></a>Quali client di posta elettronica sono supportati per leggere e rispondere ai messaggi di posta elettronica protetti?

Gli utenti di Microsoft 365 possono leggere e rispondere da Outlook per Windows e Mac (2013 e 2016), Outlook sul Web e Outlook mobile (Android e iOS). È inoltre possibile utilizzare il client di posta nativo iOS se l'organizzazione lo consente. Se non si è un utente di Microsoft 365, è possibile leggere e rispondere ai messaggi crittografati sul Web tramite il Web browser.

## <a name="what-email-clients-support-the-encrypt-only-protected-emails"></a>Quali client di posta elettronica supportano i messaggi di posta elettronica protetti solo con crittografia?

Gli utenti di Microsoft 365 possono utilizzare Outlook per PC versioni 2019 e Microsoft 365 per creare posta protetta con il criterio di sola crittografia.  Ciò significa che i messaggi a cui è applicato il nuovo criterio di sola crittografia possono essere letti direttamente in Outlook sul Web, in Outlook per iOS e Android e ora outlook per PC versioni 2019 e Microsoft 365.

## <a name="is-there-a-size-limit-for-messages-you-can-send-with-ome"></a>Esiste un limite di dimensione per i messaggi che è possibile inviare con OME?

Sì. La dimensione massima dei messaggi che è possibile inviare con OME, inclusi gli allegati, è di 25 MB. Per ulteriori informazioni, vedere [Limiti dei messaggi](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#message-limits-1).

## <a name="what-file-types-are-supported-as-attachments-in-protected-emails-do-attachments-inherit-the-protection-policies-associated-with-protected-emails"></a>Quali tipi di file sono supportati come allegati nei messaggi di posta elettronica protetti? Gli allegati ereditano i criteri di protezione associati ai messaggi di posta elettronica protetti?

È possibile allegare qualsiasi tipo di file a un messaggio di posta elettronica protetto. Con un'eccezione, i criteri di protezione vengono applicati solo ai formati di file indicati in [Tipi di file supportati dal client Azure Information Protection.](/information-protection/rms-client/client-admin-guide-file-types) OME non supporta le versioni 97-2003 delle seguenti applicazioni di Office: Word (doc), Excel (xls) e PowerPoint (ppt).

Se è supportato un formato di file, ad esempio un file di Word, Excel o PowerPoint, il file è sempre protetto, anche dopo che l'allegato è stato scaricato dal destinatario. Si supponga ad esempio che un allegato sia protetto da Non inoltrare. Il destinatario originale scarica il file, crea un messaggio a un nuovo destinatario e allega il file. Quando il nuovo destinatario riceve il file, il destinatario non sarà in grado di aprire il file protetto.
  
## <a name="are-pdf-file-attachments-supported"></a>I file allegati PDF sono supportati?

La risposta breve è sì! Se abilitata, la crittografia PDF consente di proteggere i documenti PDF sensibili tramite comunicazioni protette o collaborazione sicura. Quando si invia un messaggio di posta elettronica, il servizio Office 365 crittografa gli allegati di file PDF. Il client Outlook non crittografa i file allegati PDF.

Per Outlook sul Web, Outlook per iOS e Outlook per Android, è possibile crittografare i PDF inviati senza ulteriori passaggi. Questi client supportano in modo nativo la crittografia PDF.

Il desktop di Outlook non supporta in modo nativo la crittografia dei file allegati PDF. Sarà invece necessario configurare le regole del flusso di posta di Exchange o DLP per applicare prima la crittografia agli allegati PDF. Quando si invia la posta da Outlook Desktop con un allegato PDF, il client invia prima il messaggio con l'allegato al servizio. Quando il servizio riceve il file, il servizio applica la protezione OME del criterio di prevenzione della perdita dei dati (DLP) o della regola del flusso di posta in Exchange Online. Successivamente, Exchange Online invia il messaggio con il file PDF protetto allegato.

Per abilitare la crittografia per gli allegati PDF, eseguire il comando seguente in [PowerShell di Exchange Online:](/powershell/exchange/connect-to-exchange-online-powershell)

```powershell
Set-IRMConfiguration -EnablePdfEncryption $true
```

La crittografia PDF consente di proteggere i documenti PDF sensibili tramite comunicazioni protette o collaborazione sicura. Per tutti i client Outlook, i messaggi e gli allegati PDF non protetti ereditano la protezione OME del criterio di prevenzione della perdita dei dati (DLP) o della regola del flusso di posta in Exchange Online. Inoltre, se un utente di Outlook sul Web allega un documento PDF non protetto e applica la protezione al messaggio, il messaggio eredita la protezione del messaggio. Gli utenti possono aprire gli allegati crittografati solo in applicazioni che supportano PDF protetti (ad esempio, il portale OME e il visualizzatore di Azure Information Protection).

> [!IMPORTANT]
> Il client desktop di Outlook non supporta la crittografia PDF.

## <a name="are-onedrive-for-business-attachments-supported"></a>Gli allegati di OneDrive for Business sono supportati?

Not yet. Gli allegati di OneDrive for Business non sono supportati e gli utenti finali non possono crittografare un messaggio contenente un allegato di OneDrive for Business cloud.
  
## <a name="what-email-clients-support-preview-of-encrypted-attachments-in-protected-emails"></a>Quali client di posta elettronica supportano l'anteprima degli allegati crittografati nei messaggi di posta elettronica protetti?

Quando gli allegati sono protetti con un messaggio di posta elettronica protetto, i client Outlook offrono la possibilità di visualizzare direttamente l'anteprima del documento. Outlook supporta l'anteprima dei documenti di Office (docx, xlsx, pptx, doc, xls, ppt). Outlook sul Web supporta l'anteprima dei documenti di Office (docx, xlsx, pptx) e PDF.  

## <a name="what-email-clients-support-revocation-of-protected-emails"></a>Quali client di posta elettronica supportano la revoca dei messaggi di posta elettronica protetti?

Outlook sul Web supporta la revoca della posta protetta.  Per [informazioni dettagliate, vedere Come](revoke-ome-encrypted-mail.md#how-to-revoke-an-encrypted-message-that-you-sent) revocare un messaggio crittografato inviato.

## <a name="can-i-automatically-encrypt-messages-by-setting-up-policies"></a>È possibile crittografare automaticamente i messaggi impostando criteri?

Sì. Utilizzare le regole del flusso di posta in Exchange Online per crittografare automaticamente un messaggio in base a determinate condizioni. Ad esempio, è possibile creare criteri basati sull'ID destinatario, sul dominio del destinatario o sul contenuto nel corpo o nell'oggetto del messaggio. Vedere [Definire le regole del flusso di posta per crittografare i messaggi di posta elettronica in Office 365.](define-mail-flow-rules-to-encrypt-email.md)
  
## <a name="can-i-automatically-remove-encryption-on-incoming-and-outgoing-mail"></a>È possibile rimuovere automaticamente la crittografia della posta in arrivo e in uscita?

Gli amministratori possono configurare una regola del flusso di posta per rimuovere la crittografia per la posta in uscita. Non è possibile configurare una regola per rimuovere la crittografia per la posta in arrivo.

## <a name="can-i-automatically-encrypt-messages-by-setting-up-policies-in-data-loss-prevention-dlp-through-the-security-amp-compliance-center"></a>È possibile crittografare automaticamente i messaggi impostando criteri in Prevenzione della perdita dei dati (DLP) tramite il Centro &amp; sicurezza e conformità?

Sì. È possibile configurare le regole del flusso di posta in Exchange Online o tramite DLP nel Centro &amp; sicurezza e conformità.
  
## <a name="can-i-customize-encrypted-messages-with-my-company-branding"></a>È possibile personalizzare i messaggi crittografati con il marchio aziendale?

Sì. Per informazioni sulla personalizzazione dei messaggi di posta elettronica e del portale OME, vedere Aggiungere il marchio dell'organizzazione ai messaggi crittografati. Vedere [Aggiungere il marchio dell'organizzazione ai messaggi crittografati.](add-your-organization-brand-to-encrypted-messages.md)
  
## <a name="are-there-any-reporting-capabilities-or-insights-for-encrypted-emails"></a>Esistono funzionalità di creazione di report o informazioni dettagliate per i messaggi di posta elettronica crittografati?

È presente un report Crittografia nel Centro sicurezza e conformità. Vedere [View email security reports in the Security & Compliance Center.](../security/office-365-security/view-email-security-reports.md)
  
## <a name="can-i-use-message-encryption-with-compliance-features-such-as-ediscovery"></a>È possibile utilizzare la crittografia dei messaggi con funzionalità di conformità come eDiscovery?

Sì. Tutti i messaggi di posta elettronica crittografati sono individuabili dalle funzionalità di conformità di Microsoft 365.

## <a name="can-i-remove-encryption-from-email"></a>È possibile rimuovere la crittografia dalla posta elettronica?

Gli amministratori possono configurare una regola del flusso di posta per rimuovere la crittografia. Non è possibile rimuovere la crittografia utilizzando una regola del flusso di posta dalla posta applicata da un'altra organizzazione, a meno che la posta non venga crittografata utilizzando la protezione di sola crittografia.

## <a name="is-delegated-access-supported"></a>L'accesso delegato è supportato?

Non in questo momento.

## <a name="can-i-send-as-a-shared-mailbox-and-encrypt-emails"></a>Posso inviare come cassetta postale condivisa e crittografare i messaggi di posta elettronica?

Quando un utente invia un messaggio di posta elettronica che corrisponde a una regola del flusso di posta elettronica di crittografia, il messaggio viene crittografato prima di essere inviato.

## <a name="can-i-open-encrypted-messages-sent-to-a-shared-mailbox"></a>È possibile aprire i messaggi crittografati inviati a una cassetta postale condivisa?

Sì. I messaggi crittografati sono supportati per una cassetta postale condivisa.

- Gli utenti possono aprire i messaggi protetti in una cassetta postale condivisa in cui la cassetta postale condivisa ha ricevuto una posta protetta come parte di un gruppo di distribuzione.

- Gli utenti possono visualizzare gli allegati che ereditano la protezione dalla posta elettronica quando utilizzano Outlook per Windows, Outlook per Mac e Outlook sul Web.

Nella tabella seguente sono elencati i client supportati per le cassette postali condivise.

| Piattaforma | Lettura della posta | Visualizzare gli allegati di posta elettronica |
|----------|-----------|------------------------|
| Outlook sul Web | Sì | Sì                |
| Outlook per Windows| Sì | Sì                |
| Outlook per Mac    | Sì | Sì                |
| Outlook per Android| Sì | No                 |
| Outlook per iOS    | Sì | No                 |
|

Esistono attualmente due limitazioni note:

- Non è possibile aprire allegati ai messaggi di posta elettronica ricevuti nei dispositivi mobili utilizzando Outlook mobile.

- Non supportiamo l'assegnazione tramite un gruppo di sicurezza abilitato alla posta elettronica. Supportiamo solo l'accesso fornito dall'assegnazione diretta degli utenti alla cassetta postale condivisa e che il mapping automatico è abilitato per Exchange Online. Il mapping automatico è abilitato per impostazione predefinita per Exchange Online.

**Per assegnare un utente alla cassetta postale condivisa**

1. [Connettersi a Exchange Online utilizzando Remote PowerShell](/powershell/exchange/connect-to-exchange-online-powershell?v=exchg.150).aspx).

2. Eseguire il cmdlet Add-MailboxPermission con il parametro Automapping. In questo esempio a Ayla vengono concesse autorizzazioni di accesso completo a una cassetta postale di supporto.

   ```powershell
   Add-MailboxPermission -Identity support@contoso.onmicrosoft.com -User ayla@contoso.com -AccessRights FullAccess -AutoMapping $true
   ```

## <a name="can-i-open-encrypted-messages-sent-to-another-users-mailbox-with-fullaccess"></a>È possibile aprire i messaggi crittografati inviati alla cassetta postale di un altro utente con Accesso completo?

Gli utenti possono aprire i messaggi crittografati purché gli sia stato assegnato l'accesso diretto e il mapping automatico sia attivato. L'accesso non è consentito se l'accesso viene concesso tramite un gruppo di sicurezza abilitato alla posta elettronica.

## <a name="what-do-i-do-if-i-dont-receive-the-one-time-pass-code-after-i-requested-it"></a>Cosa fare se non si riceve il pass code una sola volta dopo che è stato richiesto?

Innanzitutto, controllare la cartella posta indesiderata nel client di posta elettronica. Le impostazioni DKIM e DMARC per l'organizzazione potrebbero causare il filtro di questi messaggi di posta elettronica come posta indesiderata.

Quindi, controllare la quarantena nel Centro sicurezza & conformità. Spesso, i messaggi contenenti un pass code una sola volta, in particolare i primi ricevuti dall'organizzazione, finiscono in quarantena.