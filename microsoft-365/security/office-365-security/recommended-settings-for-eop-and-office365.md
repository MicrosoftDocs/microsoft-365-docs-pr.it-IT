---
title: Suggerimenti Microsoft per EOP e Defender per Office 365 sicurezza
keywords: Office 365 security recommendations, Sender Policy Framework, Domain-based Message Reporting and Conformance, DomainKeys Identified Mail, steps, how does it work, security baselines, baselines for EOP, baselines for Defender for Office 365, set up Defender for Office 365, set up EOP, configure Defender for Office 365, configure EOP, security configuration
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.date: ''
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Quali sono le procedure consigliate per Exchange Online Protection (EOP) e Defender per Office 365 sicurezza? Quali sono i consigli correnti per la protezione standard? Cosa deve essere usato se si desidera essere più rigidi? E quali extra ottieni se usi anche Defender per Office 365?
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 67d1b133e0d0ac7e622ed0bfdbfd17214608d77a
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083549"
---
# <a name="recommended-settings-for-eop-and-microsoft-defender-for-office-365-security"></a>Impostazioni consigliate per EOP e Microsoft Defender per Office 365 sicurezza

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

**Exchange Online Protection (EOP)** è il fulcro della sicurezza per le sottoscrizioni Microsoft 365 e consente di evitare che messaggi di posta elettronica dannosi raggiungano le cartelle Posta in arrivo dei dipendenti. Tuttavia, con nuovi attacchi più sofisticati che emergono ogni giorno, spesso sono necessarie protezioni migliorate. **Microsoft Defender per Office 365** Il piano 1 o il piano 2 contengono funzionalità aggiuntive che offrono agli amministratori più livelli di sicurezza, controllo e analisi.

Anche se consentiamo agli amministratori della sicurezza di personalizzare le impostazioni di sicurezza, in EOP e Microsoft Defender per Office 365 sono disponibili due livelli di sicurezza: **Standard** e **Strict.** L'ambiente e le esigenze di ogni cliente sono diversi, ma riteniamo che questi livelli di filtro impediranno alla posta indesiderata di raggiungere la Posta in arrivo dei dipendenti nella maggior parte delle situazioni.

Per applicare automaticamente le impostazioni Standard o Strict agli utenti, vedi Criteri di sicurezza predefiniti [in EOP e Microsoft Defender per Office 365](preset-security-policies.md).

> [!NOTE]
> Per il corretto funzionamento del filtro, è necessario che la regola di posta indesiderata sia abilitata per le cassette postali. È abilitato per impostazione predefinita, ma è consigliabile controllarlo se il filtro non sembra funzionare. Per altre informazioni, vedere [Configurare le impostazioni della posta indesiderata nelle cassette postali di Exchange Online](configure-junk-email-settings-on-exo-mailboxes.md).

In questo articolo vengono descritte le impostazioni predefinite e le impostazioni Standard e Strict consigliate per proteggere gli utenti. Le tabelle contengono le impostazioni nel portale di Microsoft 365 Defender e PowerShell (Exchange Online PowerShell o powershell Exchange Online Protection autonomo per le organizzazioni senza Exchange Online cassette postali).

> [!TIP]
> Il Office 365 Advanced Threat Protection Recommended Configuration Analyzer (ORCA) per PowerShell consente agli amministratori di trovare i valori correnti di queste impostazioni. In particolare, il cmdlet **Get-ORCAReport** genera una valutazione della protezione da posta indesiderata, anti-phishing e altre impostazioni di igiene dei messaggi. È possibile scaricare il modulo ORCA all'indirizzo <https://www.powershellgallery.com/packages/ORCA/> .

## <a name="anti-spam-anti-malware-and-anti-phishing-protection-in-eop"></a>Protezione da posta indesiderata, antimalware e anti-phishing in EOP

Anti-spam, anti-malware, and anti-phishing are EOP features that can be configured by admins. È consigliabile utilizzare le configurazioni Standard o Strict seguenti.

### <a name="eop-anti-spam-policy-settings"></a>Impostazioni dei criteri di protezione da posta indesiderata di EOP

Per creare e configurare criteri di protezione da posta indesiderata, vedere [Configure anti-spam policies in EOP.](configure-your-spam-filter-policies.md)

<br>

****

|Nome funzionalità di sicurezza|Predefiniti|Standard|Strict|Commento|
|---|:---:|:---:|:---:|---|
|**Soglia di posta elettronica in blocco & di posta indesiderata**||||
|**Soglia posta elettronica in blocco** <p> _BulkThreshold_|7 |6 |4 |Per informazioni dettagliate, vedere [Bulk complaint level (BCL) in EOP.](bulk-complaint-level-values.md)|
|_MarkAsSpamBulkMail_|`On`|`On`|`On`|Questa impostazione è disponibile solo in PowerShell.|
|**Aumentare le impostazioni del punteggio di** posta indesiderata|Disattivato|Disattivato|Disattivato|Tutte queste impostazioni fanno parte di Advanced Spam Filter (ASF). Per ulteriori informazioni, vedere la sezione [Impostazioni ASF nei](#asf-settings-in-anti-spam-policies) criteri di protezione da posta indesiderata in questo articolo.|
|**Contrassegnare come impostazioni di posta** indesiderata|Disattivato|Disattivato|Disattivato|La maggior parte di queste impostazioni fa parte di ASF. Per ulteriori informazioni, vedere la sezione [Impostazioni ASF nei](#asf-settings-in-anti-spam-policies) criteri di protezione da posta indesiderata in questo articolo.|
|**Contiene lingue specifiche** <p> _EnableLanguageBlockList_ <p> _LanguageBlockList_|**Disattivato** <p> `$false` <p> Vuoto|**Disattivato** <p> `$false` <p> Vuoto|**Disattivato** <p> `$false` <p> Vuoto|Non sono disponibili suggerimenti specifici per questa impostazione. È possibile bloccare i messaggi in lingue specifiche in base alle esigenze aziendali.|
|**Da questi paesi** <p> _EnableRegionBlockList_ <p> _RegionBlockList_|**Disattivato** <p> `$false` <p> Vuoto|**Disattivato** <p> `$false` <p> Vuoto|**Disattivato** <p> `$false` <p> Vuoto|Non sono disponibili suggerimenti specifici per questa impostazione. È possibile bloccare i messaggi provenienti da paesi specifici in base alle esigenze aziendali.|
|**Modalità test** (_TestModeAction_)|**Nessuna**|**Nessuna**|**Nessuna**|Questa impostazione fa parte di ASF. Per ulteriori informazioni, vedere la sezione [Impostazioni ASF nei](#asf-settings-in-anti-spam-policies) criteri di protezione da posta indesiderata in questo articolo.|
|**Azioni**|||||
|**Azione di** rilevamento della posta indesiderata <p> _SpamAction_|**Sposta messaggio nella cartella Posta indesiderata** <p> `MoveToJmf`|**Sposta messaggio nella cartella Posta indesiderata** <p> `MoveToJmf`|**Metti in quarantena messaggio** <p> `Quarantine`||
|**Azione di rilevamento della posta indesiderata ad** alta probabilità <p> _HighConfidenceSpamAction_|**Sposta messaggio nella cartella Posta indesiderata** <p> `MoveToJmf`|**Metti in quarantena messaggio** <p> `Quarantine`|**Metti in quarantena messaggio** <p> `Quarantine`||
|**Azione di rilevamento** phishing <p> _PhishSpamAction_|**Sposta messaggio nella cartella Posta indesiderata** <p> `MoveToJmf`|**Metti in quarantena messaggio** <p> `Quarantine`|**Metti in quarantena messaggio** <p> `Quarantine`||
|**Azione di rilevamento di phishing ad** alta probabilità <p> _HighConfidencePhishAction_|**Metti in quarantena messaggio** <p> `Quarantine`|**Metti in quarantena messaggio** <p> `Quarantine`|**Metti in quarantena messaggio** <p> `Quarantine`||
|**Azione di** rilevamento in blocco <p> _BulkSpamAction_|**Sposta messaggio nella cartella Posta indesiderata** <p> `MoveToJmf`|**Sposta messaggio nella cartella Posta indesiderata** <p> `MoveToJmf`|**Metti in quarantena messaggio** <p> `Quarantine`||
|**Conservare la posta indesiderata in quarantena per molti giorni** <p> _QuarantineRetentionPeriod_|15 giorni|30 giorni|30 giorni||
|**Abilitare i suggerimenti per la sicurezza della posta indesiderata** <p> _InlineSafetyTipsEnabled_|Selezionato <p> `$true`|Selezionato <p> `$true`|Selezionato <p> `$true`||
|Abilitare l'eliminazione automatica a zero ore (ZAP) per i messaggi di phishing <p> _PhishZapEnabled_|Selezionato <p> `$true`|Selezionato <p> `$true`|Selezionato <p> `$true`||
|Abilitare ZAP per i messaggi di posta indesiderata <p> _SpamZapEnabled_|Selezionato <p> `$true`|Selezionato <p> `$true`|Selezionato <p> `$true`||
|**Abilita le notifiche di spam all'utente finale** <p> _EnableEndUserSpamNotifications_|Opzione non selezionata <p> `$false`|Selezionato <p> `$true`|Selezionato <p> `$true`||
|**Invia notifiche di spam agli utenti finali ogni (giorni)** <p> _EndUserSpamNotificationFrequency_|3 giorni|3 giorni|3 giorni||
|**Allow & block list**|||||
|Mittenti consentiti <p> _AllowedSenders_|Nessuno|Nessuno|Nessuno||
|Domini mittente consentiti <p> _AllowedSenderDomains_|Nessuno|Nessuno|Nessuno|L'aggiunta di domini all'elenco dei mittenti consentiti è una pessima idea. Gli utenti malintenzionati potrebbero inviare messaggi di posta elettronica che altrimenti verrebbero filtrati. <p> Utilizzare le informazioni di intelligence per [lo spoofing](learn-about-spoof-intelligence.md) e l'elenco tenant [consenti/blocca](tenant-allow-block-list.md) per esaminare tutti i mittenti che effettuano lo spoofing degli indirizzi di posta elettronica dei mittenti nei domini di posta elettronica dell'organizzazione o lo spoofing degli indirizzi di posta elettronica dei mittenti in domini esterni.|
|Mittenti bloccati <p> _BlockedSenders_|Nessuno|Nessuno|Nessuno||
|Domini mittente bloccati <p> _BlockedSenderDomains_|Nessuno|Nessuno|Nessuno||
|

#### <a name="asf-settings-in-anti-spam-policies"></a>Impostazioni ASF nei criteri di protezione da posta indesiderata

Esistono molte impostazioni asf (Advanced Spam Filter) nei criteri di protezione da posta indesiderata che sono in fase di deprecazione. Ulteriori informazioni sulle sequenze temporali per l'ammortamento di queste funzionalità verranno comunicate all'esterno di questo articolo.

È consigliabile lasciare disattivate le impostazioni ASF seguenti **per** i **livelli Standard** **e Strict.** Per ulteriori informazioni sulle impostazioni ASF, vedere [Advanced Spam Filter (ASF) settings in EOP](advanced-spam-filtering-asf-options.md).

<br>

****

|Nome funzionalità di sicurezza|Commento|
|---|---|
|**Collegamenti immagine a siti remoti** (_IncreaseScoreWithImageLinks_)||
|**Indirizzo IP numerico nell'URL** (_IncreaseScoreWithNumericIps_)||
|**Reindirizzamento dell'URL ad altra porta** (_IncreaseScoreWithRedirectToOtherPort_)||
|**Collegamenti a siti Web .biz o .info** (_IncreaseScoreWithBizOrInfoUrls_)||
|**Messaggi vuoti** (_MarkAsSpamEmptyMessages_)||
|**Incorporare tag in HTML** (_MarkAsSpamEmbedTagsInHtml_)||
|**JavaScript o VBScript in HTML** (_MarkAsSpamJavaScriptInHtml_)||
|**Tag modulo in HTML** (_MarkAsSpamFormTagsInHtml_)||
|**Tag Frame o iframe in HTML** (_MarkAsSpamFramesInHtml_)||
|**Bug Web in HTML** (_MarkAsSpamWebBugsInHtml_)||
|**Tag oggetto in HTML** (_MarkAsSpamObjectTagsInHtml_)||
|**Parole riservate** (_MarkAsSpamSensitiveWordList_)||
|**Record SPF: hard fail** (_MarkAsSpamSpfRecordHardFail_)||
|**Filtro ID mittente non riuscito** (_MarkAsSpamFromAddressAuthFail_)||
|**Backscatter** (_MarkAsSpamNdrBackscatter_)||
|**Modalità test** (_TestModeAction_)|Per le impostazioni ASF che supportano **Test** come azione, è possibile configurare l'azione in modalità test su **Nessuno,** Aggiungi testo **X-Header** predefinito o Invia messaggio Ccn **(** , o `None` `AddXHeader` `BccMessage` ). Per ulteriori informazioni, vedere [Abilitare, disabilitare o testare le impostazioni ASF.](advanced-spam-filtering-asf-options.md#enable-disable-or-test-asf-settings)|
|

#### <a name="eop-outbound-spam-policy-settings"></a>Impostazioni dei criteri di posta indesiderata in uscita EOP

Per creare e configurare i criteri di posta indesiderata in uscita, vedere [Configure outbound spam filtering in EOP.](configure-the-outbound-spam-policy.md)

Per ulteriori informazioni sui limiti di invio predefiniti nel servizio, vedere [Limiti di invio](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1).

<br>

****

|Nome funzionalità di sicurezza|Predefiniti|Standard|Strict|Commento|
|---|:---:|:---:|:---:|---|
|**Impostare un limite per i messaggi esterni** <p> _RecipientLimitExternalPerHour_|0|500|400|Il valore predefinito 0 indica l'utilizzo delle impostazioni predefinite del servizio.|
|**Impostare un limite di messaggi interni** <p> _RecipientLimitInternalPerHour_|0|1000|800|Il valore predefinito 0 indica l'utilizzo delle impostazioni predefinite del servizio.|
|**Impostare un limite giornaliero per i messaggi** <p> _RecipientLimitPerDay_|0|1000|800|Il valore predefinito 0 indica l'utilizzo delle impostazioni predefinite del servizio.|
|**Restrizioni applicate agli utenti che raggiungono il limite dei messaggi** <p> _ActionWhenThresholdReached_|**Limitare l'invio di posta elettronica all'utente fino al giorno seguente** <p> `BlockUserForToday`|**Limitare l'invio di posta elettronica all'utente** <p> `BlockUser`|**Limitare l'invio di posta elettronica all'utente** <p> `BlockUser`||
|**Regole di inoltro automatico** <p> _AutoForwardingMode_|**Automatico - Controllato dal sistema** <p> `Automatic`|**Automatico - Controllato dal sistema** <p> `Automatic`|**Automatico - Controllato dal sistema** <p> `Automatic`|
|**Inviare una copia dei messaggi in uscita che superano questi limiti a questi utenti e gruppi** <p> _BccSuspiciousOutboundMail_ <p> _BccSuspiciousOutboundAdditionalRecipients_|Opzione non selezionata <p> `$false` <p> Vuoto|Opzione non selezionata <p> `$false` <p> Vuoto|Opzione non selezionata <p> `$false` <p> Vuoto|Non sono disponibili suggerimenti specifici per questa impostazione. <p> Questa impostazione funziona solo nel criterio di posta indesiderata in uscita predefinito. Non funziona nei criteri di posta indesiderata in uscita personalizzati creati dall'utente.|
|**Notificare a questi utenti e gruppi se un mittente è bloccato a causa dell'invio di posta indesiderata in uscita** <p> _NotifyOutboundSpam_ <p> _NotifyOutboundSpamRecipients_|Opzione non selezionata <p> `$false` <p> Vuoto|Opzione non selezionata <p> `$false` <p> Vuoto|Opzione non selezionata <p> `$false` <p> Vuoto|Il [](../../compliance/alert-policies.md) criterio di  avviso predefinito denominato Utente con restrizioni per l'invio di messaggi di posta elettronica invia già notifiche tramite posta elettronica ai membri del gruppo **TenantAdmins** (**Amministratori** globali ) quando gli utenti vengono bloccati a causa del superamento dei limiti nei criteri. **È consigliabile utilizzare il criterio** di avviso anziché questa impostazione nel criterio di posta indesiderata in uscita per inviare una notifica agli amministratori e ad altri utenti. Per istruzioni, vedere [Verificare le impostazioni degli avvisi per gli utenti con restrizioni.](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)|
|

### <a name="eop-anti-malware-policy-settings"></a>Impostazioni dei criteri antimalware EOP

Per creare e configurare criteri antimalware, vedere [Configure anti-malware policies in EOP.](configure-anti-malware-policies.md)

<br>

****

|Nome funzionalità di sicurezza|Predefiniti|Standard|Strict|Commento|
|---|:---:|:---:|:---:|---|
|**Impostazioni di protezione**|||||
|**Abilitare il filtro allegati comuni** <p> _EnableFileFilter_|Opzione non selezionata <p> `$false`|Selezionato <p> `$true`|Selezionato <p> `$true`|Questa impostazione consente di mettere in quarantena i messaggi che contengono allegati eseguibili in base al tipo di file, indipendentemente dal contenuto dell'allegato.|
|**Abilitare l'eliminazione automatica di zero ore per il malware** <p> _ZapEnabled_|Selezionato <p> `$true`|Selezionato <p> `$true`|Selezionato <p> `$true`||
|**Notifiche destinatario**|||||
|**Notificare ai destinatari quando i messaggi vengono messi in quarantena come malware** <p> _Azione_|Opzione non selezionata <p> _DeleteMessage_|Opzione non selezionata <p> _DeleteMessage_|Opzione non selezionata <p> _DeleteMessage_|Se viene rilevato malware in un allegato di posta elettronica, il messaggio viene messo in quarantena e può essere rilasciato solo da un amministratore.|
|**Notifiche mittente**|||||
|**Notificare ai mittenti interni quando i messaggi vengono messi in quarantena come malware** <p> _EnableInternalSenderNotifications_|Opzione non selezionata <p> `$false`|Opzione non selezionata <p> `$false`|Opzione non selezionata <p> `$false`||
|**Notificare ai mittenti esterni quando i messaggi vengono messi in quarantena come malware** <p> _EnableExternalSenderNotifications_|Opzione non selezionata <p> `$false`|Opzione non selezionata <p> `$false`|Opzione non selezionata <p> `$false`||
|**Notifiche dell'amministratore**|||||
|**Notificare a un amministratore i messaggi non recapitati dai mittenti interni** <p> _EnableInternalSenderAdminNotifications_ <p> _InternalSenderAdminAddress_|Opzione non selezionata <p> `$false`|Opzione non selezionata <p> `$false`|Opzione non selezionata <p> `$false`|Non sono disponibili suggerimenti specifici per questa impostazione.|
|**Notificare a un amministratore i messaggi non recapitati provenienti da mittenti esterni** <p> _EnableExternalSenderAdminNotifications_ <p> _ExternalSenderAdminAddress_|Opzione non selezionata <p> `$false`|Opzione non selezionata <p> `$false`|Opzione non selezionata <p> `$false`|Non sono disponibili suggerimenti specifici per questa impostazione.|
|**Personalizzare le notifiche**||||Non sono disponibili suggerimenti specifici per queste impostazioni.|
|**Usa testo di notifica personalizzato** <p> _CustomNotifications_|Opzione non selezionata <p> `$false`|Opzione non selezionata <p> `$false`|Opzione non selezionata <p> `$false`||
|**Nome mittente** <p> _CustomFromName_|Vuoto <p> `$null`|Vuoto <p> `$null`|Vuoto <p> `$null`||
|**Indirizzo mittente** <p> _CustomFromAddress_|Vuoto <p> `$null`|Vuoto <p> `$null`|Vuoto <p> `$null`||
|**Personalizzare le notifiche per i messaggi provenienti da mittenti interni**||||Queste impostazioni vengono utilizzate solo se è selezionata l'opzione Notifica ai mittenti interni quando i messaggi vengono messi in quarantena come **malware** o Notifica a un amministratore i messaggi non recapitati dai **mittenti** interni.|
|**Oggetto** <p> _CustomInternalSubject_|Vuoto <p> `$null`|Vuoto <p> `$null`|Vuoto <p> `$null`||
|**Messaggio** <p> _CustomInternalBody_|Vuoto <p> `$null`|Vuoto <p> `$null`|Vuoto <p> `$null`||
|**Personalizzare le notifiche per i messaggi provenienti da mittenti esterni**||||Queste impostazioni vengono utilizzate solo se è selezionata l'opzione Notifica ai mittenti esterni quando i messaggi vengono messi in quarantena come **malware** o Se è selezionata l'opzione Notifica a un amministratore dei messaggi non recapitati **provenienti** da mittenti esterni.|
|**Oggetto** <p> _CustomExternalSubject_|Vuoto <p> `$null`|Vuoto <p> `$null`|Vuoto <p> `$null`||
|**Messaggio** <p> _CustomExternalBody_|Vuoto <p> `$null`|Vuoto <p> `$null`|Vuoto <p> `$null`||
|

### <a name="eop-anti-phishing-policy-settings"></a>Impostazioni dei criteri anti-phishing di EOP

Per ulteriori informazioni su queste impostazioni, vedere [Spoofing settings.](set-up-anti-phishing-policies.md#spoof-settings) Per configurare queste impostazioni, vedere [Configure anti-phishing policies in EOP.](configure-anti-phishing-policies-eop.md)

<br>

****

|Nome funzionalità di sicurezza|Predefiniti|Standard|Strict|Commento|
|---|:---:|:---:|:---:|---|
|**Soglia di phishing & protezione**|||||
|**Abilitare spoof intelligence** <p> _EnableSpoofIntelligence_|Selezionato <p> `$true`|Selezionato <p> `$true`|Selezionato <p> `$true`||
|**Azioni**|||||
|**Se il messaggio viene rilevato come spoofing** <p> _AuthenticationFailAction_|**Spostare il messaggio nelle cartelle posta indesiderata dei destinatari** <p> `MoveToJmf`|**Spostare il messaggio nelle cartelle posta indesiderata dei destinatari** <p> `MoveToJmf`|**Mettere in quarantena il messaggio** <p> `Quarantine`|Questa impostazione si applica ai mittenti falsificati che sono stati bloccati automaticamente come mostrato nell'analisi [di spoofing intelligence](learn-about-spoof-intelligence.md) o bloccati manualmente nell'elenco [Tenant consentiti/bloccati](tenant-allow-block-list.md).|
|**Mostra il primo contatto suggerimento per la sicurezza** <p> _EnableFirstContactSafetyTips_|Opzione non selezionata <p> `$false`|Selezionato <p> `$true`|Selezionato <p> `$true`|Per ulteriori informazioni, vedere [First contact suggerimento per la sicurezza](set-up-anti-phishing-policies.md#first-contact-safety-tip).|
|**Mostrare (?) per i mittenti non autenticati per lo spoofing** <p> _EnableUnauthenticatedSender_|Selezionato <p> `$true`|Selezionato <p> `$true`|Selezionato <p> `$true`|Aggiunge un punto interrogativo (?) alla foto del mittente in Outlook mittenti falsificati non identificato. Per ulteriori informazioni, vedere [Unauthenticated sender](set-up-anti-phishing-policies.md#unauthenticated-sender).|
|**Mostra tag "via"** <p> _EnableViaTag_|Selezionato <p> `$true`|Selezionato <p> `$true`|Selezionato <p> `$true`|Aggiunge un tag via (chris@contoso.com tramite fabrikam.com) all'indirizzo From se è diverso dal dominio nella firma DKIM o nell'indirizzo **MAIL FROM.** <p> Per ulteriori informazioni, vedere [Unauthenticated sender](set-up-anti-phishing-policies.md#unauthenticated-sender).|
|

## <a name="microsoft-defender-for-office-365-security"></a>Microsoft Defender per la Office 365 sicurezza

Ulteriori vantaggi per la sicurezza sono offerti con un abbonamento a Microsoft Defender Office 365 sicurezza. Per le notizie e le informazioni più recenti, puoi vedere [Novità di Defender per Office 365](whats-new-in-defender-for-office-365.md).

> [!IMPORTANT]
>
> - Il criterio anti-phishing predefinito in Microsoft Defender per Office 365 fornisce protezione [spoofing](set-up-anti-phishing-policies.md#spoof-settings) e intelligence delle cassette postali per tutti i destinatari. Tuttavia, le altre funzionalità di [protezione della rappresentazione](#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) disponibili e [le impostazioni avanzate](#advanced-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) non sono configurate o abilitate nel criterio predefinito. Per abilitare tutte le funzionalità di protezione, modificare il criterio anti-phishing predefinito o creare ulteriori criteri anti-phishing.
>
> - Non esistono criteri predefiniti Cassaforte collegamenti o Cassaforte allegati che proteggano automaticamente tutti i destinatari nell'organizzazione. Per ottenere le protezioni, è necessario creare almeno un criterio Cassaforte collegamenti e Cassaforte allegati.
>
> - Cassaforte allegati per [SharePoint, OneDrive](mdo-for-spo-odb-and-teams.md) e Microsoft Teams e la protezione Cassaforte [documenti](safe-docs.md) non hanno dipendenze dai criteri Cassaforte collegamenti.

Se l'abbonamento include Microsoft Defender per Office 365 o se hai acquistato Defender per Office 365 come componente aggiuntivo, imposta le configurazioni Standard o Strict seguenti.

### <a name="anti-phishing-policy-settings-in-microsoft-defender-for-office-365"></a>Impostazioni dei criteri anti-phishing in Microsoft Defender per Office 365

I clienti EOP ottengono anti-phishing di base come descritto in precedenza, ma Defender per Office 365 include più funzionalità e controllo per prevenire, rilevare e correggere gli attacchi. Per creare e configurare questi criteri, vedere [Configure anti-phishing policies in Defender for Office 365](configure-mdo-anti-phishing-policies.md).

#### <a name="advanced-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Impostazioni avanzate nei criteri anti-phishing in Microsoft Defender per Office 365

Per ulteriori informazioni su questa impostazione, vedere [Soglie di phishing avanzate nei criteri anti-phishing in Microsoft Defender per Office 365](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365). Per configurare questa impostazione, vedere [Configure anti-phishing policies in Defender for Office 365](configure-mdo-anti-phishing-policies.md).

<br>

****

|Nome funzionalità di sicurezza|Predefiniti|Standard|Strict|Commento|
|---|:---:|:---:|:---:|---|
|**Soglia posta elettronica di phishing** <p> _PhishThresholdLevel_|**1 - Standard** <p> `1`|**2 - Aggressivo** <p> `2`|**3 - Più aggressivo** <p> `3`||
|

#### <a name="impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Impostazioni di rappresentazione nei criteri anti-phishing in Microsoft Defender per Office 365

Per ulteriori informazioni su queste impostazioni, vedere Impostazioni di rappresentazione nei criteri [anti-phishing in Microsoft Defender per Office 365](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365). Per configurare queste impostazioni, vedere [Configure anti-phishing policies in Defender for Office 365](configure-mdo-anti-phishing-policies.md).

<br>

****

|Nome funzionalità di sicurezza|Predefiniti|Standard|Strict|Commento|
|---|:---:|:---:|:---:|---|
|**Soglia di phishing & protezione**|||||
|**Consentire agli utenti di proteggere** (protezione utente impersonata)<p> _EnableTargetedUserProtection_ <p> _TargetedUsersToProtect_|Opzione non selezionata <p> `$false` <p> nessuno|Selezionato <p> `$true` <p> \<list of users\>|Selezionato <p> `$true` <p> \<list of users\>|È consigliabile aggiungere utenti (mittenti di messaggi) nei ruoli chiave. Internamente, i mittenti protetti potrebbero essere il CEO, il CFO e altri dirigenti senior. Esternamente, i mittenti protetti possono includere membri del consiglio o il consiglio di amministrazione.|
|**Abilitare i domini da proteggere** (protezione del dominio rappresentato)|Opzione non selezionata|Selezionato|Selezionato||
|**Includere i domini di cui sono proprietario** <p> _EnableOrganizationDomainsProtection_|Disattivato <p> `$false`|Selezionato <p> `$true`|Selezionato <p> `$true`||
|**Includere domini personalizzati** <p> _EnableTargetedDomainsProtection_ <p> _TargetedDomainsToProtect_|Disattivato <p> `$false` <p> nessuno|Selezionato <p> `$true` <p> \<list of domains\>|Selezionato <p> `$true` <p> \<list of domains\>|È consigliabile aggiungere domini (domini mittente) di cui non si è proprietari, ma con cui si interagisce frequentemente.|
|**Aggiungere mittenti e domini attendibili** <p> _ExcludedSenders_ <p> _ExcludedDomains_|Nessuno|Nessuno|Nessuno|A seconda dell'organizzazione, è consigliabile aggiungere mittenti o domini erroneamente identificati come tentativi di rappresentazione.|
|**Abilitare l'intelligence delle cassette postali** <p> _EnableMailboxIntelligence_|Selezionato <p> `$true`|Selezionato <p> `$true`|Selezionato <p> `$true`||
|**Abilitare l'intelligence per la protezione della rappresentazione** <p> _EnableMailboxIntelligenceProtection_|Disattivato <p> `$false`|Selezionato <p> `$true`|Selezionato <p> `$true`|Questa impostazione consente l'azione specificata per i rilevamenti di rappresentazione da parte dell'intelligence delle cassette postali.|
|**Azioni**|||||
|**Se il messaggio viene rilevato come utente rappresentato** <p> _TargetedUserProtectionAction_|**Non applicare alcuna azione** <p> `NoAction`|**Mettere in quarantena il messaggio** <p> `Quarantine`|**Mettere in quarantena il messaggio** <p> `Quarantine`||
|**Se il messaggio viene rilevato come dominio rappresentato** <p> _TargetedDomainProtectionAction_|**Non applicare alcuna azione** <p> `NoAction`|**Mettere in quarantena il messaggio** <p> `Quarantine`|**Mettere in quarantena il messaggio** <p> `Quarantine`||
|**Se l'intelligence delle cassette postali rileva e rappresenta l'utente** <p> _MailboxIntelligenceProtectionAction_|**Non applicare alcuna azione** <p> `NoAction`|**Spostare il messaggio nelle cartelle posta indesiderata dei destinatari** <p> `MoveToJmf`|**Mettere in quarantena il messaggio** <p> `Quarantine`||
|**Mostra rappresentazione utente suggerimento per la sicurezza** <p> _EnableSimilarUsersSafetyTips_|Disattivato <p> `$false`|Selezionato <p> `$true`|Selezionato <p> `$true`||
|**Mostra rappresentazione dominio suggerimento per la sicurezza** <p> _EnableSimilarDomainsSafetyTips_|Disattivato <p> `$false`|Selezionato <p> `$true`|Selezionato <p> `$true`||
|**Mostra caratteri insoliti di rappresentazione utente suggerimento per la sicurezza** <p> _EnableUnusualCharactersSafetyTips_|Disattivato <p> `$false`|Selezionato <p> `$true`|Selezionato <p> `$true`||
|

#### <a name="eop-anti-phishing-policy-settings-in-microsoft-defender-for-office-365"></a>Impostazioni dei criteri anti-phishing EOP in Microsoft Defender per Office 365

Si tratta delle stesse impostazioni disponibili nelle impostazioni dei criteri di protezione da posta [indesiderata in EOP.](#eop-anti-spam-policy-settings)

Le impostazioni di spoofing sono correlate tra loro, ma l'impostazione Mostra primo contatto **suggerimento per la sicurezza** non dipende dalle impostazioni di spoofing.

<br>

****

|Nome funzionalità di sicurezza|Predefiniti|Standard|Strict|Commento|
|---|:---:|:---:|:---:|---|
|**Soglia di phishing & protezione**|||||
|**Abilitare spoof intelligence** <p> _EnableSpoofIntelligence_|Selezionato <p> `$true`|Selezionato <p> `$true`|Selezionato <p> `$true`||
|**Azioni**|||||
|**Se il messaggio viene rilevato come spoofing** <p> _AuthenticationFailAction_|**Spostare il messaggio nelle cartelle posta indesiderata dei destinatari** <p> `MoveToJmf`|**Spostare il messaggio nelle cartelle posta indesiderata dei destinatari** <p> `MoveToJmf`|**Mettere in quarantena il messaggio** <p> `Quarantine`|Questa impostazione si applica ai mittenti falsificati che sono stati bloccati automaticamente come mostrato nell'analisi [di spoofing intelligence](learn-about-spoof-intelligence.md) o bloccati manualmente nell'elenco [Tenant consentiti/bloccati](tenant-allow-block-list.md).|
|**Mostra il primo contatto suggerimento per la sicurezza** <p> _EnableFirstContactSafetyTips_|Opzione non selezionata <p> `$false`|Selezionato <p> `$true`|Selezionato <p> `$true`|Per ulteriori informazioni, vedere [First contact suggerimento per la sicurezza](set-up-anti-phishing-policies.md#first-contact-safety-tip).|
|**Mostrare (?) per i mittenti non autenticati per lo spoofing** <p> _EnableUnauthenticatedSender_|Selezionato <p> `$true`|Selezionato <p> `$true`|Selezionato <p> `$true`|Aggiunge un punto interrogativo (?) alla foto del mittente in Outlook mittenti falsificati non identificato. Per ulteriori informazioni, vedere [Unauthenticated sender](set-up-anti-phishing-policies.md#unauthenticated-sender).|
|**Mostra tag "via"** <p> _EnableViaTag_|Selezionato <p> `$true`|Selezionato <p> `$true`|Selezionato <p> `$true`|Aggiunge un tag via (chris@contoso.com tramite fabrikam.com) all'indirizzo From se è diverso dal dominio nella firma DKIM o nell'indirizzo **MAIL FROM.** <p> Per ulteriori informazioni, vedere [Unauthenticated sender](set-up-anti-phishing-policies.md#unauthenticated-sender).|
|

### <a name="safe-attachments-settings"></a>Cassaforte Impostazioni allegati

Cassaforte Gli allegati in Microsoft Defender per Office 365 includono impostazioni globali che non hanno alcuna relazione con i criteri Cassaforte Allegati e impostazioni specifiche per ogni criterio collegamenti Cassaforte. Per altre informazioni, vedi [Cassaforte allegati in Defender per Office 365](safe-attachments.md).

#### <a name="global-settings-for-safe-attachments"></a>Impostazioni globali per Cassaforte allegati

Per configurare queste impostazioni, vedere Attivare Cassaforte allegati per [SharePoint, OneDrive e Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md) e [Cassaforte documenti in Microsoft 365 E5](safe-docs.md).

In PowerShell si utilizza il cmdlet [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365) per queste impostazioni.

<br>

****

|Nome funzionalità di sicurezza|Predefiniti|Standard|Strict|Commento|
|---|:---:|:---:|:---:|---|
|**Per altre informazioni, vedere Attivare Microsoft Defender per Office 365 per SharePoint, OneDrive e Microsoft Teams.** <p> _EnableATPForSPOTeamsODB_|Disattivato <p> `$false`|Attivato <p> `$true`|Attivato <p> `$true`||
|**Attivare documenti Cassaforte per Office client** <p> _EnableSafeDocs_|Disattivato <p> `$false`|Attivato <p> `$true`|Attivato <p> `$true`|Questa funzionalità è disponibile e significativa solo con Microsoft 365 E5 o Microsoft 365 E5 Security licenze. Per altre informazioni, vedi [Cassaforte documenti in Microsoft Defender per Office 365](safe-docs.md).|
|**Consentire agli utenti di fare clic su Visualizzazione protetta anche se Cassaforte documenti hanno identificato il file come dannoso** <p> _AllowSafeDocsOpen_|Disattivato <p> `$false`|Disattivato <p> `$false`|Disattivato <p> `$false`|Questa impostazione è correlata a Cassaforte documenti.|
|

#### <a name="safe-attachments-policy-settings"></a>Cassaforte Impostazioni dei criteri allegati

Per configurare queste impostazioni, vedi [Configurare i criteri Cassaforte allegati in Defender per Office 365](set-up-safe-attachments-policies.md).

In PowerShell, si utilizzano i cmdlet [New-SafeAttachmentPolicy](/powershell/module/exchange/new-safeattachmentpolicy) e [Set-SafeAttachmentPolicy](/powershell/module/exchange/set-safelinkspolicy) per queste impostazioni.

> [!NOTE]
> Come descritto in precedenza, non esiste un criterio Cassaforte allegati predefiniti. I valori nella colonna Default sono i valori predefiniti nei nuovi criteri Cassaforte allegati creati.

<br>

****

|Nome funzionalità di sicurezza|Predefiniti|Standard|Strict|Commento|
|---|:---:|:---:|:---:|---|
|**Cassaforte Allegati risposta malware sconosciuta** <p> _Azione_|**Disattivato** <p> `Block`|**Blocca** <p> `Block`|**Blocca** <p> `Block`||
|**Reindirizzare l'allegato con allegati rilevati** : **Abilita reindirizzamento** <p> _Reindirizza_ <p> _RedirectAddress_|Non selezionato e nessun indirizzo di posta elettronica specificato. <p> `$true` <p> nessuno|Selezionare e specificare un indirizzo di posta elettronica. <p> `$true` <p> un indirizzo di posta elettronica|Selezionare e specificare un indirizzo di posta elettronica. <p> `$true` <p> un indirizzo di posta elettronica|Reindirizzare i messaggi a un amministratore della sicurezza per la revisione.|
|**Applicare la risposta Cassaforte rilevamento allegati se l'analisi non può essere completata (timeout o errori)** <p> _ActionOnError_|Selezionato <p> `$true`|Selezionato <p> `$true`|Selezionato <p> `$true`||
|

### <a name="safe-links-settings"></a>Cassaforte Impostazioni collegamenti

Cassaforte I collegamenti in Defender per Office 365 includono impostazioni globali che si applicano a tutti gli utenti inclusi nei criteri dei collegamenti Cassaforte attivi e impostazioni specifiche per ogni criterio collegamenti Cassaforte. Per altre informazioni, vedi [collegamenti Cassaforte in Defender per Office 365](safe-links.md).

#### <a name="global-settings-for-safe-links"></a>Impostazioni globali per Cassaforte collegamenti

Per configurare queste impostazioni, vedere [Configure global settings for Cassaforte Links in Defender for Office 365](configure-global-settings-for-safe-links.md).

In PowerShell si utilizza il cmdlet [Set-AtpPolicyForO365](/powershell/module/exchange/set-atppolicyforo365) per queste impostazioni.

<br>

****

|Nome funzionalità di sicurezza|Predefiniti|Standard|Strict|Commento|
|---|:---:|:---:|:---:|---|
|**Blocca gli URL seguenti** <p> _ExcludedUrls_|Vuoto <p> `$null`|Vuoto <p> `$null`|Vuoto <p> `$null`|Non sono disponibili suggerimenti specifici per questa impostazione. <p> Per ulteriori informazioni, vedere [l'elenco "Bloccare gli URL seguenti" per Cassaforte collegamenti.](safe-links.md#block-the-following-urls-list-for-safe-links)
|**Usare Cassaforte collegamenti nelle Office 365 app** <p> _EnableSafeLinksForO365Clients_|Attivato <p> `$true`|Attivato <p> `$true`|Attivato <p> `$true`|Usa Cassaforte collegamenti nelle app Office 365 desktop e per dispositivi mobili (iOS e Android) supportate. Per altre informazioni, vedi impostazioni [Cassaforte collegamenti per Office 365 app](safe-links.md#safe-links-settings-for-office-365-apps).|
|**Non tenere traccia quando gli utenti fanno clic su collegamenti protetti nelle Office 365 app** <p> _TrackClicks_|Attivato <p> `$false`|Disattivato <p> `$true`|Disattivato <p> `$true`|Disattivando questa impostazione (impostando _TrackClicks su_ ) si tiene traccia dei clic degli utenti nelle app Office 365 `$true` supportate.|
|**Non consentire agli utenti di passare all'URL originale nelle Office 365 app** <p> _AllowClickThrough_|Attivato <p> `$false`|Attivato <p> `$false`|Attivato <p> `$false`|L'attivazione di questa impostazione (impostando _AllowClickThrough_ su ) impedisce di passare all'URL originale nelle app Office 365 `$false` supportate.|
|

#### <a name="safe-links-policy-settings"></a>Cassaforte Impostazioni dei criteri collegamenti

Per configurare queste impostazioni, vedi [Configurare i criteri Cassaforte collegamenti in Microsoft Defender per Office 365](set-up-safe-links-policies.md).

In PowerShell, si utilizzano i cmdlet [New-SafeLinksPolicy](/powershell/module/exchange/new-safelinkspolicy) e [Set-SafeLinksPolicy](/powershell/module/exchange/set-safelinkspolicy) per queste impostazioni.

> [!NOTE]
> Come descritto in precedenza, non esiste un criterio Cassaforte collegamenti predefiniti. I valori nella colonna Default sono i valori predefiniti nei nuovi criteri Cassaforte collegamenti creati.

<br>

****

|Nome funzionalità di sicurezza|Predefiniti|Standard|Strict|Commento|
|---|:---:|:---:|:---:|---|
|**Impostazioni di protezione**|||||
|**Selezionare l'azione per URL sconosciuti potenzialmente dannosi nei messaggi** <p> _IsEnabled_|**Disattivato** <p> `$false`|**Attivato** <p> `$true`|**Attivato** <p> `$true`||
|**Selezionare l'azione per URL sconosciuti o potenzialmente dannosi all'interno di Microsoft Teams** <p> _EnableSafeLinksForTeams_|**Disattivato** <p> `$false`|**Attivato** <p> `$true`|**Attivato** <p> `$true`|A partire da marzo 2020, questa funzionalità è disponibile in Anteprima ed è disponibile o funzionante solo per i membri del Microsoft Teams Technology Adoption Program (TAP).|
|**Applicare l'analisi degli URL in tempo reale per i collegamenti sospetti e i collegamenti che puntano ai file** <p> _ScanUrls_|Opzione non selezionata <p> `$false`|Selezionato <p> `$true`|Selezionato <p> `$true`||
|**Attendere il completamento dell'analisi degli URL prima di recapitare il messaggio** <p> _DeliverMessageAfterScan_|Opzione non selezionata <p> `$false`|Selezionato <p> `$true`|Selezionato <p> `$true`||
|**Applicare Cassaforte ai messaggi di posta elettronica inviati all'interno dell'organizzazione** <p> _EnableForInternalSenders_|Opzione non selezionata <p> `$false`|Selezionato <p> `$true`|Selezionato <p> `$true`||
|**Non tenere traccia dei clic degli utenti** <p> _DoNotTrackUserClicks_|Opzione non selezionata <p> `$false`|Opzione non selezionata <p> `$false`|Opzione non selezionata <p> `$false`|Disattivando questa impostazione (impostando _DoNotTrackUserClicks su_ `$false` ) si tiene traccia dei clic degli utenti.|
|**Non consentire agli utenti di passare all'URL originale** <p> _DoNotAllowClickThrough_|Opzione non selezionata <p> `$false`|Selezionato <p> `$true`|Selezionato <p> `$true`|L'attivazione di questa impostazione _(impostando DoNotAllowClickThrough_ su ) impedisce di `$true` passare all'URL originale.|
|**Visualizzare la personalizzazione dell'organizzazione nelle pagine di notifica e avviso** <p> _EnableOrganizationBranding_|Opzione non selezionata <p> `$false`|Opzione non selezionata <p> `$false`|Opzione non selezionata <p> `$false`|Non sono disponibili suggerimenti specifici per questa impostazione. <p> Prima di attivare questa impostazione, è necessario seguire le istruzioni in [Personalizzare](../../admin/setup/customize-your-organization-theme.md) il tema Microsoft 365 per l'organizzazione per caricare il logo aziendale.|
|**Non riscrivere gli URL seguenti** <p> _DoNotRewriteUrls_|Opzione non selezionata <p> `$false`|Opzione non selezionata <p> `$true`|Opzione non selezionata <p> `$true`|Non sono disponibili suggerimenti specifici per questa impostazione. Per ulteriori informazioni, vedere gli elenchi ["Non riscrivere gli URL seguenti" nei criteri Cassaforte collegamenti.](safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)|
|**Notifica**|||||
|**Come si desidera inviare una notifica agli utenti?**|**Usare il testo di notifica predefinito**|**Usare il testo di notifica predefinito**|**Usare il testo di notifica predefinito**|Non sono disponibili suggerimenti specifici per questa impostazione. <p> È possibile selezionare **Usa testo di notifica personalizzato** (_CustomNotificationText_) per immettere il testo di notifica personalizzato da utilizzare. Puoi anche selezionare **Usa Microsoft Translator** per la localizzazione automatica (_UseTranslatedNotificationText_) per tradurre il testo di notifica personalizzato nella lingua dell'utente.
|

## <a name="related-articles"></a>Articoli correlati

- Per informazioni sulle procedure consigliate per le regole Exchange del flusso di **posta (note** anche come regole di trasporto)? Vedere [Procedure consigliate per la configurazione delle regole del flusso di posta in Exchange Online](/exchange/security-and-compliance/mail-flow-rules/configuration-best-practices).

- Gli amministratori e gli utenti possono inviare falsi positivi (buona posta elettronica contrassegnata come non buona) e falsi negativi (posta elettronica non consentita) a Microsoft per l'analisi. Per altre informazioni, vedere [Segnalazione di messaggi e file a Microsoft](report-junk-email-messages-to-microsoft.md).

- Usa questi collegamenti per informazioni su come **configurare il** servizio [EOP](/exchange/standalone-eop/set-up-your-eop-service)e **configurare** Microsoft Defender [per Office 365](defender-for-office-365.md). Non dimenticare le indicazioni utili in '[Protect Against Threats in Office 365](protect-against-threats.md)'.

-  Le linee di base di sicurezza per Windows sono disponibili qui: Dove è possibile ottenere le linee di base della [sicurezza?](/windows/security/threat-protection/windows-security-baselines#where-can-i-get-the-security-baselines) per le opzioni degli oggetti Criteri di gruppo/locali e Usare le linee di base di sicurezza per configurare i dispositivi [Windows 10 in Intune](/intune/protect/security-baselines) per la sicurezza basata su Intune. Infine, un confronto tra Microsoft Defender per Endpoint e le linee di base della sicurezza Microsoft Intune è disponibile in Confronto tra Microsoft Defender per Endpoint e le linee di base di sicurezza di [Windows Intune.](/windows/security/threat-protection/microsoft-defender-atp/configure-machines-security-baseline#compare-the-microsoft-defender-atp-and-the-windows-intune-security-baselines)
