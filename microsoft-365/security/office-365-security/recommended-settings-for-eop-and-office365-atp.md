---
title: Consigli di Microsoft per le impostazioni di sicurezza di EOP e Office 365 ATP, consigli, Sender Policy Framework, Reporting e conformità dei messaggi basati su dominio, DomainKeys identificata, procedure, modalità di funzionamento, linee di base per la sicurezza, linee di base per EOP, linee di base per ATP, set up ATP, set up EOP, Configure ATP, Configure EOP, Security Configuration
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.date: ''
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: Quali sono le procedure consigliate per le impostazioni di sicurezza di Exchange Online Protection (EOP) e Advanced Threat Protection (ATP)? Quali sono le raccomandazioni aggiornate per la protezione standard? Che cosa dovrebbe essere utilizzato se si desidera essere più severi? Quali sono gli extra che si ottengono se si utilizza anche Advanced Threat Protection (ATP)?
ms.openlocfilehash: 4afd662be28c047d5f738dc0f70f0254e7a7a83f
ms.sourcegitcommit: 04a43a146cb62a10b1a4555ec3bed49eb08fbb99
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2020
ms.locfileid: "48806773"
---
# <a name="recommended-settings-for-eop-and-office-365-atp-security"></a>Impostazioni consigliate per la sicurezza ATP di EOP e Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Exchange Online Protection (EOP)** è il fulcro della sicurezza per le sottoscrizioni di Microsoft 365 e consente di evitare che i messaggi di posta elettronica dannosi raggiungano la posta in arrivo del dipendente. Tuttavia, con attacchi nuovi e sofisticati che emergono ogni giorno, sono spesso necessarie protezioni migliorate. **Office 365 Advanced Threat Protection (ATP)** ATP piano 1 o ATP piano 2 contengono funzionalità aggiuntive che forniscono agli amministratori più livelli di sicurezza, controllo ed indagini.

Anche se si autorizza gli amministratori della sicurezza a personalizzare le impostazioni di sicurezza, esistono due livelli di sicurezza in EOP e Office 365 ATP che è consigliabile: **standard** e **strict** . L'ambiente e i bisogni di ogni cliente sono diversi, ma riteniamo che questi livelli di filtraggio consentano di evitare che la posta indesiderata raggiunga la posta in arrivo dei dipendenti nella maggior parte delle situazioni.

Per applicare automaticamente le impostazioni standard o rigorose agli utenti, vedere [criteri di sicurezza preimpostati in EOP e Office 365 ATP](preset-security-policies.md).

> [!NOTE]
> La regola di posta indesiderata deve essere abilitata sulle cassette postali per consentire il corretto funzionamento del filtro. È abilitata per impostazione predefinita, ma è consigliabile verificarla se il filtro non sembra funzionare. Per altre informazioni, vedere [Configurare le impostazioni della posta indesiderata nelle cassette postali di Exchange Online in Office 365](configure-junk-email-settings-on-exo-mailboxes.md).

In questo articolo vengono descritte le impostazioni predefinite e anche le impostazioni standard e rigorose consigliate per la protezione degli utenti.

> [!TIP]
> Il modulo Analyzer (Advanced Threat Protection) di Office 365 per PowerShell consente agli amministratori di trovare i valori correnti di tali impostazioni. In particolare, il cmdlet **Get-ORCAReport** consente di generare una valutazione delle impostazioni di protezione da posta indesiderata, anti-phishing e altre funzionalità di igiene dei messaggi. È possibile scaricare il modulo ORCA all'indirizzo <https://www.powershellgallery.com/packages/ORCA/> .

## <a name="anti-spam-anti-malware-and-anti-phishing-protection-in-eop"></a>Protezione da posta indesiderata, anti-malware e anti-phishing in EOP

Le funzionalità di protezione da posta indesiderata, anti-malware e anti-phishing sono caratteristiche di EOP che possono essere configurate dagli amministratori. Si consiglia di eseguire le seguenti configurazioni standard o rigorose.

### <a name="eop-anti-spam-policy-settings"></a>Impostazioni dei criteri di protezione da posta indesiderata di EOP

Per creare e configurare criteri di protezione dalla posta indesiderata, vedere [configurare i criteri di protezione dalla posta indesiderata in Office 365](configure-your-spam-filter-policies.md).

****

|Nome della funzionalità di sicurezza|Predefiniti|Standard|Rigorosa|Aggiungere commenti|
|---|:---:|:---:|:---:|---|
|Azione di rilevamento della **posta indesiderata** <br/><br/> _SpamAction_|**Sposta messaggio nella cartella Posta indesiderata** <br/><br/> `MoveToJmf`|**Sposta messaggio nella cartella Posta indesiderata** <br/><br/> `MoveToJmf`|**Metti in quarantena messaggio** <br/><br/> `Quarantine`||
|Azione di rilevamento di **posta indesiderata con elevata sicurezza** <br/><br/> _HighConfidenceSpamAction_|**Sposta messaggio nella cartella Posta indesiderata** <br/><br/> `MoveToJmf`|**Metti in quarantena messaggio** <br/><br/> `Quarantine`|**Metti in quarantena messaggio** <br/><br/> `Quarantine`||
|Azione di rilevamento della **posta elettronica di phishing** <br/><br/> _PhishSpamAction_|**Sposta messaggio nella cartella Posta indesiderata** <br/><br/> `MoveToJmf`|**Metti in quarantena messaggio** <br/><br/> `Quarantine`|**Metti in quarantena messaggio** <br/><br/> `Quarantine`||
|Azione di rilevamento della **posta elettronica di phishing con elevata sicurezza** <br/><br/> _HighConfidencePhishAction_|**Metti in quarantena messaggio** <br/><br/> `Quarantine`|**Metti in quarantena messaggio** <br/><br/> `Quarantine`|**Metti in quarantena messaggio** <br/><br/> `Quarantine`||
|Azione di rilevamento della **posta elettronica in blocco** <br/><br/> _BulkSpamAction_|**Sposta messaggio nella cartella Posta indesiderata** <br/><br/> `MoveToJmf`|**Sposta messaggio nella cartella Posta indesiderata** <br/><br/> `MoveToJmf`|**Metti in quarantena messaggio** <br/><br/> `Quarantine`||
|Soglia di posta elettronica in blocco <br/><br/> _BulkThreshold_|7 |6 |4 |Per informazioni dettagliate, vedere [bulk lamentel Level (BCL) in Office 365](bulk-complaint-level-values.md).|
|Periodo di conservazione della quarantena <br/><br/> _QuarantineRetentionPeriod_|15 giorni|30 giorni|30 giorni||
|**Suggerimenti per la sicurezza** <br/><br/> _InlineSafetyTipsEnabled_|Attivato <br/><br/> `$true`|Attivato <br/><br/> `$true`|Attivato <br/><br/> `$true`||
|Mittenti consentiti <br/><br/> _AllowedSenders_|Nessuno|Nessuno|Nessuno||
|Domini mittenti consentiti <br/><br/> _AllowedSenderDomains_|Nessuno|Nessuno|Nessuno|L'aggiunta di domini all'elenco dei mittenti consentiti è una pessima idea. Gli aggressori sarebbero in grado di inviare messaggi di posta elettronica che altrimenti verrebbero filtrati. <br/><br/> Utilizzare l' [Intelligence spoof](learn-about-spoof-intelligence.md) nel centro sicurezza & Compliance nella pagina impostazioni di protezione da **posta indesiderata** per esaminare tutti i mittenti che eseguono lo spoofing degli indirizzi di posta elettronica del mittente nei domini di posta elettronica dell'organizzazione o nello spoofing degli indirizzi di posta elettronica del mittente nei domini esterni.|
|Mittenti bloccati <br/><br/> _BlockedSenders_|Nessuno|Nessuno|Nessuno||
|Domini mittenti bloccati <br/><br/> _BlockedSenderDomains_|Nessuno|Nessuno|Nessuno||
|**Abilita le notifiche di spam all'utente finale** <br/><br/> _EnableEndUserSpamNotifications_|Disattivato <br/><br/> `$false`|Abilitato <br/><br/> `$true`|Abilitato <br/><br/> `$true`||
|**Invia notifiche di spam agli utenti finali ogni (giorni)** <br/><br/> _EndUserSpamNotificationFrequency_|3 giorni|3 giorni|3 giorni||
|**Spam ZAP** <br/><br/> _SpamZapEnabled_|Abilitato <br/><br/> `$true`|Abilitato <br/><br/> `$true`|Abilitato <br/><br/> `$true`||
|**Phishing ZAP** <br/><br/> _PhishZapEnabled_|Abilitato <br/><br/> `$true`|Abilitato <br/><br/> `$true`|Abilitato <br/><br/> `$true`||
|_MarkAsSpamBulkMail_|Attivato|Attivato|Attivato|Questa impostazione è disponibile solo in PowerShell.|
|

In criteri di protezione da posta indesiderata sono disponibili diverse altre impostazioni avanzate per il filtro di posta indesiderata. Altre informazioni sulle sequenze temporali per l'ammortamento di queste caratteristiche verranno comunicate al di fuori di questo articolo.

Si **consiglia di disattivare queste impostazioni ASF** sia per i livelli **standard** che per quelli **rigorosi** . Per ulteriori informazioni sulle impostazioni ASF, vedere [Advanced Spam Filter (ASF) Settings in Office 365](advanced-spam-filtering-asf-options.md).

****

|Nome della funzionalità di sicurezza|Aggiungere commenti|
|---|---|
|**Collegamenti di immagini a siti remoti** ( _IncreaseScoreWithImageLinks_ )||
|**Indirizzo IP numerico in URL** ( _IncreaseScoreWithNumericIps_ )||
|**Reindirizzamento UL ad altre porte** ( _IncreaseScoreWithRedirectToOtherPort_ )||
|**URL di siti Web. biz o. info** ( _IncreaseScoreWithBizOrInfoUrls_ )||
|**Messaggi vuoti** ( _MarkAsSpamEmptyMessages_ )||
|**JavaScript o VBScript in HTML** ( _MarkAsSpamJavaScriptInHtml_ )||
|**Tag frame o iframe in formato HTML** ( _MarkAsSpamFramesInHtml_ )||
|**Tag Object in HTML** ( _MarkAsSpamObjectTagsInHtml_ )||
|**Tag embed in HTML** ( _MarkAsSpamEmbedTagsInHtml_ )||
|**Tag del modulo in formato HTML** ( _MarkAsSpamFormTagsInHtml_ )||
|**Bug Web in HTML** ( _MarkAsSpamWebBugsInHtml_ )||
|**Applicazione di un elenco di parole riservate** ( _MarkAsSpamSensitiveWordList_ )||
|**Record SPF: errore** irreversibile ( _MarkAsSpamSpfRecordHardFail_ )||
|**Filtro ID mittente condizionale: errore** irreversibile ( _MarkAsSpamFromAddressAuthFail_ )||
|Backscatter del rapporto di **mancato recapito** ( _MarkAsSpamNdrBackscatter_ )||
|

#### <a name="eop-outbound-spam-policy-settings"></a>Impostazioni di criteri di posta indesiderata in uscita di EOP

Per creare e configurare i criteri di posta indesiderata in uscita, vedere [Configure Outbound Spam Filtering in Office 365](configure-the-outbound-spam-policy.md).

Per ulteriori informazioni sui limiti di invio predefiniti nel servizio, vedere [invio di limiti](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1).

****

|Nome della funzionalità di sicurezza|Predefiniti|Standard|Rigorosa|Aggiungere commenti|
|---|:---:|:---:|:---:|---|
|**Numero massimo di destinatari per utente: limite orario esterno** <br/><br/> _RecipientLimitExternalPerHour_|0|500|400|Il valore predefinito 0 indica che vengono utilizzati i valori predefiniti del servizio.|
|**Numero massimo di destinatari per utente: limite orario interno** <br/><br/> _RecipientLimitInternalPerHour_|0|1000|800|Il valore predefinito 0 indica che vengono utilizzati i valori predefiniti del servizio.|
|**Numero massimo di destinatari per utente: limite giornaliero** <br/><br/> _RecipientLimitPerDay_|0|1000|800|Il valore predefinito 0 indica che vengono utilizzati i valori predefiniti del servizio.|
|**Azione quando un utente supera i limiti** <br/><br/> _ActionWhenThresholdReached_|**Impedire all'utente di inviare messaggi di posta elettronica fino al giorno seguente** <br/><br/> `BlockUserForToday`|**Impedire all'utente di inviare messaggi di posta elettronica** <br/><br/> `BlockUser`|**Impedire all'utente di inviare messaggi di posta elettronica** <br/><br/> `BlockUser`||
|

### <a name="eop-anti-malware-policy-settings"></a>Impostazioni dei criteri anti-malware di EOP

Per creare e configurare criteri anti-malware, vedere [Configure anti-malware Policies in Office 365](configure-anti-malware-policies.md).

****

|Nome della funzionalità di sicurezza|Predefiniti|Standard|Rigorosa|Aggiungere commenti|
|---|:---:|:---:|:---:|---|
|**Si desidera inviare una notifica ai destinatari se i messaggi vengono messi in quarantena?** <br/><br/> _Azione_|No <br/><br/> _DeleteMessage_|No <br/><br/> _DeleteMessage_|No <br/><br/> _DeleteMessage_|Se il malware viene rilevato in un allegato di posta elettronica, il messaggio viene messo in quarantena e può essere rilasciato solo da un amministratore.|
|**Filtro di tipi di allegati comuni** <br/><br/> _EnableFileFilter_|Disattivato <br/><br/> `$false`|Attivato <br/><br/> `$true`|Attivato <br/><br/> `$true`|Questa impostazione mette in quarantena i messaggi che contengono allegati eseguibili in base al tipo di file, indipendentemente dal contenuto degli allegati.|
|**Malware zero-hour auto Purge** <br/><br/> _ZapEnabled_|Attivato <br/><br/> `$true`|Attivato <br/><br/> `$true`|Attivato <br/><br/> `$true`||
|**Notifica ai mittenti interni** del messaggio non recapitato <br/><br/> _EnableInternalSenderNotifications_|Disattivato <br/><br/> `$false`|Disattivato <br/><br/> `$false`|Disattivato <br/><br/> `$false`||
|**Notifica ai mittenti esterni** del messaggio non recapitato <br/><br/> _EnableExternalSenderNotifications_|Disattivato <br/><br/> `$false`|Disattivato <br/><br/> `$false`|Disattivato <br/><br/> `$false`||
|

### <a name="eop-default-anti-phishing-policy-settings"></a>Impostazioni di criteri anti-phishing predefinite di EOP

Per ulteriori informazioni su queste impostazioni, vedere [spoofing Settings](set-up-anti-phishing-policies.md#spoof-settings). Per configurare queste impostazioni, vedere [Configure anti-phishing Policies in EOP](configure-anti-phishing-policies-eop.md).

****

|Nome della funzionalità di sicurezza|Predefiniti|Standard|Rigorosa|Aggiungere commenti|
|---|:---:|:---:|:---:|---|
|**Abilitare la protezione anti-spoofing** <br/><br/> _EnableAntispoofEnforcement_|Attivato <br/><br/> `$true`|Attivato <br/><br/> `$true`|Attivato <br/><br/> `$true`||
|**Abilitazione del mittente non autenticato** <br/><br/> _EnableUnauthenticatedSender_|Attivato <br/><br/> `$true`|Attivato <br/><br/> `$true`|Attivato <br/><br/> `$true`|Aggiunge un punto interrogativo (?) alla foto del mittente in Outlook per i mittenti non identificati falsificati. Per ulteriori informazioni, vedere [spoofing Settings in anti-phishing Policies](set-up-anti-phishing-policies.md).|
|**Se il messaggio di posta elettronica viene inviato da un utente che non ha il diritto di falsificare il dominio** <br/><br/> _AuthenticationFailAction_|**Spostare il messaggio nelle cartelle di posta indesiderata dei destinatari** <br/><br/> `MoveToJmf`|**Spostare il messaggio nelle cartelle di posta indesiderata dei destinatari** <br/><br/> `MoveToJmf`|**Mettere in quarantena il messaggio** <br/><br/> `Quarantine`|Questa impostazione si applica ai mittenti bloccati in [Intelligence contraffatta](learn-about-spoof-intelligence.md).|
|

## <a name="office-365-advanced-threat-protection-security"></a>Protezione avanzata dalle minacce di Office 365

Ulteriori vantaggi per la sicurezza sono disponibili con una sottoscrizione di Office 365 Advanced Threat Protection (ATP). Per le notizie e le informazioni più recenti, è possibile visualizzare le [novità di Office 365 ATP](whats-new-in-office-365-atp.md).

> [!IMPORTANT]
>
> - Il criterio anti-phishing predefinito di ATP fornisce la [protezione da spoofing](set-up-anti-phishing-policies.md#spoof-settings) per tutti i destinatari. Tuttavia, le impostazioni di [protezione della rappresentazione](#impersonation-settings-in-atp-anti-phishing-policies) disponibili per i mittenti o i domini mittenti specifici non sono configurate o abilitate nel criterio predefinito. Per abilitare la protezione della rappresentazione, configurare il criterio predefinito o creare ulteriori criteri anti-phishing ATP.
>
> - Non ci sono criteri collegamenti sicuri predefiniti o criteri allegati sicuri che proteggono automaticamente tutti i destinatari nell'organizzazione. Per ottenere le protezioni, è necessario creare almeno un criterio per i collegamenti sicuri e un criterio degli allegati sicuri.
>
> - [ATP per SharePoint, OneDrive e Microsoft teams](atp-for-spo-odb-and-teams.md) Protection and [Safe Documents](safe-docs.md) Protection non hanno dipendenze dai criteri dei collegamenti sicuri.

Se l'abbonamento include Office 365 ATP o se è stato acquistato Office 365 ATP come componente aggiuntivo, impostare le configurazioni standard o rigorose seguenti.

### <a name="atp-anti-phishing-policy-settings"></a>Impostazioni dei criteri di anti-phishing ATP

I clienti di EOP ottengono un anti-phishing di base come descritto in precedenza, ma Office 365 ATP include altre funzionalità e controlli che consentono di prevenire, rilevare e correggere gli attacchi. Per creare e configurare questi criteri, vedere [configurare i criteri di anti-phishing ATP in Office 365](configure-atp-anti-phishing-policies.md).

#### <a name="impersonation-settings-in-atp-anti-phishing-policies"></a>Impostazioni di rappresentazione nei criteri di anti-phishing ATP

Per ulteriori informazioni su queste impostazioni, vedere [impostazioni di rappresentazione nei criteri di anti-phishing ATP](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies). Per configurare queste impostazioni, vedere [Configure ATP anti-phishing Policies](configure-atp-anti-phishing-policies.md).

****

|Nome della funzionalità di sicurezza|Predefiniti|Standard|Rigorosa|Aggiungere commenti|
|---|:---:|:---:|:---:|---|
|Utenti protetti: **aggiungere utenti a Protect** <br/><br/> _È impostato enabletargeteduserprotection_ <br/><br/> _TargetedUsersToProtect_|Off <br/><br/> `$false` <br/><br/> nessuno|Attivato <br/><br/> `$true` <br/><br/> \<list of users\>|Attivato <br/><br/> `$true` <br/><br/> \<list of users\>|A seconda dell'organizzazione, è consigliabile aggiungere utenti (mittenti dei messaggi) in ruoli chiave. Internamente, i mittenti protetti potrebbero essere il CEO, il CFO e altri leader senior. Esternamente, i mittenti protetti possono includere i membri del Consiglio o il Consiglio di amministrazione.|
|Domini protetti: **includono automaticamente i domini che possiedo** <br/><br/> _EnableOrganizationDomainsProtection_|Disattivato <br/><br/> `$false`|Attivato <br/><br/> `$true`|Attivato <br/><br/> `$true`||
|Domini protetti: **includere domini personalizzati** <br/><br/> _EnableTargetedDomainsProtection_ <br/><br/> _TargetedDomainsToProtect_|Off <br/><br/> `$false` <br/><br/> nessuno|Attivato <br/><br/> `$true` <br/><br/> \<list of domains\>|Attivato <br/><br/> `$true` <br/><br/> \<list of domains\>|A seconda dell'organizzazione, è consigliabile aggiungere domini (domini mittenti) che non sono proprietari, ma con cui si interagisce spesso.|
|Utenti protetti: **se il messaggio di posta elettronica viene inviato da un utente rappresentato** <br/><br/> _TargetedUserProtectionAction_|**Non applicare alcuna azione** <br/><br/> `NoAction`|**Mettere in quarantena il messaggio** <br/><br/> `Quarantine`|**Mettere in quarantena il messaggio** <br/><br/> `Quarantine`||
|Domini protetti: **se il messaggio di posta elettronica viene inviato da un dominio rappresentato** <br/><br/> _TargetedDomainProtectionAction_|**Non applicare alcuna azione** <br/><br/> `NoAction`|**Mettere in quarantena il messaggio** <br/><br/> `Quarantine`|**Mettere in quarantena il messaggio** <br/><br/> `Quarantine`||
|**Mostrare il suggerimento per gli utenti rappresentati** <br/><br/> _EnableSimilarUsersSafetyTips_|Disattivato <br/><br/> `$false`|Attivato <br/><br/> `$true`|Attivato <br/><br/> `$true`||
|**Mostrare il suggerimento per i domini rappresentati** <br/><br/> _EnableSimilarDomainsSafetyTips_|Disattivato <br/><br/> `$false`|Attivato <br/><br/> `$true`|Attivato <br/><br/> `$true`||
|**Mostra suggerimento per i caratteri insoliti** <br/><br/> _EnableUnusualCharactersSafetyTips_|Disattivato <br/><br/> `$false`|Attivato <br/><br/> `$true`|Attivato <br/><br/> `$true`||
|**Abilitare l'intelligence delle cassette postali?** <br/><br/> _EnableMailboxIntelligence_|Attivato <br/><br/> `$true`|Attivato <br/><br/> `$true`|Attivato <br/><br/> `$true`||
|**Abilitare la protezione della rappresentazione basata sull'Intelligence delle cassette postali?** <br/><br/> _EnableMailboxIntelligenceProtection_|Disattivato <br/><br/> `$false`|Attivato <br/><br/> `$true`|Attivato <br/><br/> `$true`||
|**Se il messaggio di posta elettronica viene inviato da un utente rappresentato protetto dalla funzionalità di intelligence delle cassette postali** <br/><br/> _MailboxIntelligenceProtectionAction_|**Non applicare alcuna azione** <br/><br/> `NoAction`|**Spostare il messaggio nelle cartelle di posta indesiderata dei destinatari** <br/><br/> `MoveToJmf`|**Mettere in quarantena il messaggio** <br/><br/> `Quarantine`||
|**Mittenti attendibili** <br/><br/> _ExcludedSenders_|Nessuno|Nessuno|Nessuno|A seconda dell'organizzazione, è consigliabile aggiungere utenti che vengono erroneamente contrassegnati come phishing a causa solo della rappresentazione e non di altri filtri.|
|**Domini attendibili** <br/><br/> _ExcludedDomains_|Nessuno|Nessuno|Nessuno|A seconda dell'organizzazione, è consigliabile aggiungere domini che vengono erroneamente contrassegnati come phishing a causa solo della rappresentazione e non di altri filtri.|
|

#### <a name="spoof-settings-in-atp-anti-phishing-policies"></a>Impostazioni di spoofing nei criteri di anti-phishing ATP

Si noti che si tratta delle stesse impostazioni disponibili nelle impostazioni dei criteri di protezione [da posta indesiderata in EOP](#eop-anti-spam-policy-settings).

****

|Nome della funzionalità di sicurezza|Standard|Rigorosa|Aggiungere commenti|
|---|---|---|---|
|**Abilitare la protezione anti-spoofing** <br/><br/> _EnableAntispoofEnforcement_|Attivato <br/><br/> `$true`|Attivato <br/><br/> `$true`||
|**Abilitazione del mittente non autenticato** <br/><br/> _EnableUnauthenticatedSender_|Attivato <br/><br/> `$true`|Attivato <br/><br/> `$true`|Aggiunge un punto interrogativo (?) alla foto del mittente in Outlook per i mittenti non identificati falsificati. Per ulteriori informazioni, vedere [spoofing Settings in anti-phishing Policies](set-up-anti-phishing-policies.md).|
|**Se il messaggio di posta elettronica viene inviato da un utente che non ha il diritto di falsificare il dominio** <br/><br/> _AuthenticationFailAction_|**Spostare il messaggio nelle cartelle di posta indesiderata dei destinatari** <br/><br/> `MoveToJmf`|**Mettere in quarantena il messaggio** <br/><br/> `Quarantine`|Questa impostazione si applica ai mittenti bloccati in [Intelligence contraffatta](learn-about-spoof-intelligence.md).|
|

#### <a name="advanced-settings-in-atp-anti-phishing-policies"></a>Impostazioni avanzate nei criteri di anti-phishing ATP

Per ulteriori informazioni su questa impostazione, vedere [Advanced phishing Thresholds in ATP anti-phishing Policies](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-atp-anti-phishing-policies). Per configurare questa impostazione, vedere [Configure ATP anti-phishing Policies](configure-atp-anti-phishing-policies.md).

****

|Nome della funzionalità di sicurezza|Predefiniti|Standard|Rigorosa|Aggiungere commenti|
|---|:---:|:---:|:---:|---|
|**Soglie di phishing avanzate** <br/><br/> _PhishThresholdLevel_|**1-standard** <br/><br/> `1`|**2-aggressivo** <br/><br/> `2`|**3-maggiore aggressività** <br/><br/> `3`||
|

### <a name="safe-links-settings"></a>Impostazioni collegamenti attendibili

Collegamenti sicuri in Office 365 ATP sono incluse le impostazioni globali che si applicano a tutti gli utenti inclusi nei criteri dei collegamenti sicuri attivi e le impostazioni specifiche di ogni criterio dei collegamenti sicuri. Per ulteriori informazioni, vedere [collegamenti sicuri in Office 365 ATP](atp-safe-links.md).

#### <a name="global-settings-for-safe-links"></a>Impostazioni globali per i collegamenti sicuri

Per configurare queste impostazioni, vedere [Configure Global Settings for Safe Links in Office 365 ATP](configure-global-settings-for-safe-links.md).

In PowerShell, è possibile utilizzare il cmdlet [set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365) per queste impostazioni.

****

|Nome della funzionalità di sicurezza|Predefiniti|Standard|Rigorosa|Aggiungere commenti|
|---|:---:|:---:|:---:|---|
|**Utilizzare collegamenti sicuri in: applicazioni di Office 365** <br/><br/> _EnableSafeLinksForO365Clients_|Attivato <br/><br/> `$true`|Attivato <br/><br/> `$true`|Attivato <br/><br/> `$true`|Usare i collegamenti sicuri di ATP nelle app desktop e mobili (iOS e Android) supportate di Office 365. Per ulteriori informazioni, vedere [impostazioni dei collegamenti sicuri per le app di Office 365](atp-safe-links.md#safe-links-settings-for-office-365-apps).|
|**Non monitorare quando gli utenti fanno clic su collegamenti sicuri** <br/><br/> _TrackClicks_|Attivato <br/><br/> `$false`|Disattivato <br/><br/> `$true`|Off <br/><br/> `$true`|La disattivazione di questa impostazione (impostazione di _TrackClicks_ `$true` ) tiene traccia degli scatti degli utenti nelle app di Office 365 supportate.|
|**Non consentire agli utenti di fare clic su collegamenti sicuri all'URL originale** <br/><br/> _AllowClickThrough_|Attivato <br/><br/> `$false`|Attivato <br/><br/> `$false`|Attivato <br/><br/> `$false`|Se si attiva questa impostazione (impostare _AllowClickThrough_ su `$false` ), si impedisce di fare clic sull'URL originale nelle app di Office 365 supportate.|
|

#### <a name="safe-links-policy-settings"></a>Impostazioni per i criteri collegamenti sicuri

Per configurare queste impostazioni, vedere Configurare i [criteri dei collegamenti sicuri in Office 365 ATP](set-up-atp-safe-links-policies.md).

In PowerShell, è possibile utilizzare i cmdlet [New-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safelinkspolicy) e [set-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy) per queste impostazioni.

> [!NOTE]
> Come descritto in precedenza, non esiste alcun criterio di collegamenti sicuri predefinito. I valori nella colonna predefinita sono i valori predefiniti nei nuovi criteri collegamenti sicuri creati.

****

|Nome della funzionalità di sicurezza|Predefiniti|Standard|Rigorosa|Aggiungere commenti|
|---|:---:|:---:|:---:|---|
|**Selezionare l'azione per gli URL potenzialmente dannosi sconosciuti nei messaggi** <br/><br/> _Proprietà IsEnabled_|Disattivato <br/><br/> `$false`|Attivato <br/><br/> `$true`|Attivato <br/><br/> `$true`||
|**Selezionare l'azione per gli URL sconosciuti o potenzialmente dannosi all'interno di Microsoft Teams** <br/><br/> _EnableSafeLinksForTeams_|Disattivato <br/><br/> `$false`|Attivato <br/><br/> `$true`|Attivato <br/><br/> `$true`||
|**Applicazione dell'analisi degli URL in tempo reale per collegamenti e collegamenti sospetti che puntano a file** <br/><br/> _ScanUrls_|Disattivato <br/><br/> `$false`|Attivato <br/><br/> `$true`|Attivato <br/><br/> `$true`||
|**Attendere il completamento dell'analisi degli URL prima di recapitare il messaggio** <br/><br/> _DeliverMessageAfterScan_|Disattivato <br/><br/> `$false`|Attivato <br/><br/> `$true`|Attivato <br/><br/> `$true`||
|**Applicazione di collegamenti sicuri ai messaggi di posta elettronica inviati all'interno dell'organizzazione** <br/><br/> _EnableForInternalSenders_|Disattivato <br/><br/> `$false`|Attivato <br/><br/> `$true`|Attivato <br/><br/> `$true`||
|**Non monitorare i clic dell'utente** <br/><br/> _DoNotTrackUserClicks_|Off <br/><br/> `$false`|Off <br/><br/> `$false`|Off <br/><br/> `$false`|La disattivazione di questa impostazione (impostazione di _DoNotTrackUserClicks_ su `$false` ) tiene traccia degli utenti.|
|**Non consentire agli utenti di fare clic sull'URL originale** <br/><br/> _DoNotAllowClickThrough_|Disattivato <br/><br/> `$false`|Attivato <br/><br/> `$true`|Attivato <br/><br/> `$true`|Se si attiva questa impostazione (impostare _DoNotAllowClickThrough_ su `$true` ), si impedisce di fare clic sull'URL originale.|
|

### <a name="safe-attachments-settings"></a>Impostazioni degli allegati sicuri

Allegati sicuri in Office 365 ATP sono incluse le impostazioni globali che non hanno alcuna relazione con i criteri degli allegati sicuri e le impostazioni specifiche di ogni criterio per i collegamenti sicuri. Per ulteriori informazioni, vedere [Safe Attachments in Office 365 ATP](atp-safe-attachments.md).

#### <a name="global-settings-for-safe-attachments"></a>Impostazioni globali per gli allegati sicuri

Per configurare queste impostazioni, vedere [abilitare ATP per SharePoint, OneDrive e Microsoft teams](turn-on-atp-for-spo-odb-and-teams.md) e [documenti attendibili in Microsoft 365 E5](safe-docs.md).

In PowerShell, è possibile utilizzare il cmdlet [set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365) per queste impostazioni.

****

|Nome della funzionalità di sicurezza|Predefiniti|Standard|Rigorosa|Aggiungere commenti|
|---|:---:|:---:|:---:|---|
|**Attivare ATP per SharePoint, OneDrive e Microsoft Teams** <br/><br/> _EnableATPForSPOTeamsODB_|Attivato <br/><br/> `$true`|Attivato <br/><br/> `$true`||
|**Attivazione di documenti attendibili per i client di Office**<bt/><br/> _EnableSafeDocs_|Attivato <br/><br/> `$true`|Attivato <br/><br/> `$true`|Questa impostazione è disponibile solo con le licenze di sicurezza Microsoft 365 E5 o Microsoft 365 E5. Per ulteriori informazioni, vedere [documenti attendibili in Office 365 Advanced Threat Protection](safe-docs.md).|
|**Consenti agli utenti di fare clic su una visualizzazione protetta anche se i documenti attendibili hanno identificato il file come dannoso**<bt/><br/> _AllowSafeDocsOpen_|Off <br/><br/> `$false`|Off <br/><br/> `$false`|Questa impostazione è correlata ai documenti attendibili.|
|

#### <a name="safe-attachments-policy-settings"></a>Impostazioni di criteri per gli allegati sicuri

Per configurare queste impostazioni, vedere Configurare i criteri per gli [allegati sicuri in Office 365 ATP](set-up-atp-safe-attachments-policies.md).

In PowerShell, è possibile utilizzare i cmdlet [New-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentpolicy) e [set-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy) per queste impostazioni.

> [!NOTE]
> Come descritto in precedenza, non esiste alcun criterio di allegati sicuri predefinito. I valori nella colonna predefinita sono i valori predefiniti nei nuovi criteri allegati sicuri creati.

****

|Nome della funzionalità di sicurezza|Predefiniti|Standard|Rigorosa|Aggiungere commenti|
|---|:---:|:---:|:---:|---|
|**Risposta malware per gli allegati sicuri sconosciuta** <br/><br/> _Azione_|Blocca <br/><br/> `Block`|Blocca <br/><br/> `Block`|Blocca <br/><br/> `Block`||
|**Redirect Attachment on Detection** : **Enable redirect** <br/><br/> _Reindirizza_ <br/><br/> _RedirectAddress_|E non è stato specificato alcun indirizzo di posta elettronica. <br/><br/> `$true` <br/><br/> nessuno|Attiva e specificare un indirizzo di posta elettronica. <br/><br/> `$true` <br/><br/> un indirizzo di posta elettronica|Attiva e specificare un indirizzo di posta elettronica. <br/><br/> `$true` <br/><br/> un indirizzo di posta elettronica|Reindirizzare i messaggi a un amministratore della sicurezza per la revisione.|
|**Applicare la selezione precedente se si verifica un errore durante l'analisi di malware per gli allegati.** <br/><br/> _ActionOnError_|Attivato <br/><br/> `$true`|Attivato <br/><br/> `$true`|Attivato <br/><br/> `$true`||
|

## <a name="related-articles"></a>Articoli correlati

- Per informazioni sulle procedure consigliate per **le regole del flusso di posta di Exchange (note anche come regole di trasporto** ) Vedere [procedure consigliate per la configurazione delle regole del flusso di posta in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/configuration-best-practices).

- Gli amministratori e gli utenti possono inviare falsi positivi (buon messaggio di posta elettronica contrassegnato come cattivo) e falsi negativi (messaggi di posta elettronica non consentiti) a Microsoft per l'analisi. Per altre informazioni, vedere [Segnalazione di messaggi e file a Microsoft](report-junk-email-messages-to-microsoft.md).

- Utilizzare questi collegamenti per informazioni su come **configurare** il [servizio EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-your-eop-service)e **configurare** [Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp). Non dimenticare le indicazioni utili in '[protezione dalle minacce in Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats)'.

- Le **linee di base per la sicurezza per Windows** sono disponibili qui: [dove è possibile ottenere le previsioni di sicurezza? per le](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines#where-can-i-get-the-security-baselines) opzioni di criteri di gruppo/locali e utilizzare le [previsioni di sicurezza per configurare i dispositivi Windows 10 in Intune](https://docs.microsoft.com/intune/protect/security-baselines) per la sicurezza basata su Intune. Infine, è disponibile un confronto tra Microsoft Defender Advanced Threat Protection (ATP) e le previsioni di sicurezza di Microsoft Intune in [confronto tra Microsoft Defender ATP e le previsioni di sicurezza di Windows Intune](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-machines-security-baseline#compare-the-microsoft-defender-atp-and-the-windows-intune-security-baselines).
