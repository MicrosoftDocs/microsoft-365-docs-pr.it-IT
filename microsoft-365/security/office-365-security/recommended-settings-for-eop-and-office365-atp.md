---
title: Suggerimenti Microsoft per EOP e Defender per le impostazioni di sicurezza di Office 365, suggerimenti, Sender Policy Framework, Reporting e conformità dei messaggi basati su dominio, DomainKeys identificata, procedure, modalità di funzionamento, linee di base per la sicurezza, linee di base per EOP, linee di base per il difensore per Office 365, configurare il difensore per Office 365, configurare 365 EOP
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
description: Quali sono le procedure consigliate per le impostazioni di sicurezza di Exchange Online Protection (EOP) e Defender per Office 365? Quali sono le raccomandazioni aggiornate per la protezione standard? Che cosa dovrebbe essere utilizzato se si desidera essere più severi? Quali sono gli extra che si ottengono se si utilizza Defender anche per Office 365?
ms.openlocfilehash: 192e37a1a9a373f7b6712600bc3c81189f7c51ad
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2020
ms.locfileid: "49615961"
---
# <a name="recommended-settings-for-eop-and-microsoft-defender-for-office-365-security"></a>Impostazioni consigliate per EOP e Microsoft Defender per la sicurezza di Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Exchange Online Protection (EOP)** è il fulcro della sicurezza per le sottoscrizioni di Microsoft 365 e consente di evitare che i messaggi di posta elettronica dannosi raggiungano la posta in arrivo del dipendente. Tuttavia, con attacchi nuovi e sofisticati che emergono ogni giorno, sono spesso necessarie protezioni migliorate. **Microsoft Defender per Office 365** Il piano 1 o il piano 2 contengono funzionalità aggiuntive che conferiscono agli amministratori più livelli di sicurezza, controllo e analisi.

Anche se gli amministratori della sicurezza sono autorizzati a personalizzare le impostazioni di sicurezza, esistono due livelli di sicurezza in EOP e Microsoft Defender per Office 365 che è consigliabile: **standard** e **strict**. L'ambiente e i bisogni di ogni cliente sono diversi, ma riteniamo che questi livelli di filtraggio consentano di evitare che la posta indesiderata raggiunga la posta in arrivo dei dipendenti nella maggior parte delle situazioni.

Per applicare automaticamente le impostazioni standard o rigorose agli utenti, vedere [criteri di sicurezza preimpostati in EOP e Microsoft Defender per Office 365](preset-security-policies.md).

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
|Azione di rilevamento della **posta indesiderata** <p> _SpamAction_|**Sposta messaggio nella cartella Posta indesiderata** <p> `MoveToJmf`|**Sposta messaggio nella cartella Posta indesiderata** <p> `MoveToJmf`|**Metti in quarantena messaggio** <p> `Quarantine`||
|Azione di rilevamento di **posta indesiderata con elevata sicurezza** <p> _HighConfidenceSpamAction_|**Sposta messaggio nella cartella Posta indesiderata** <p> `MoveToJmf`|**Metti in quarantena messaggio** <p> `Quarantine`|**Metti in quarantena messaggio** <p> `Quarantine`||
|Azione di rilevamento della **posta elettronica di phishing** <p> _PhishSpamAction_|**Sposta messaggio nella cartella Posta indesiderata** <p> `MoveToJmf`|**Metti in quarantena messaggio** <p> `Quarantine`|**Metti in quarantena messaggio** <p> `Quarantine`||
|Azione di rilevamento della **posta elettronica di phishing con elevata sicurezza** <p> _HighConfidencePhishAction_|**Metti in quarantena messaggio** <p> `Quarantine`|**Metti in quarantena messaggio** <p> `Quarantine`|**Metti in quarantena messaggio** <p> `Quarantine`||
|Azione di rilevamento della **posta elettronica in blocco** <p> _BulkSpamAction_|**Sposta messaggio nella cartella Posta indesiderata** <p> `MoveToJmf`|**Sposta messaggio nella cartella Posta indesiderata** <p> `MoveToJmf`|**Metti in quarantena messaggio** <p> `Quarantine`||
|Soglia di posta elettronica in blocco <p> _BulkThreshold_|7 |6 |4 |Per informazioni dettagliate, vedere [bulk lamentel Level (BCL) in Office 365](bulk-complaint-level-values.md).|
|Periodo di conservazione della quarantena <p> _QuarantineRetentionPeriod_|15 giorni|30 giorni|30 giorni||
|**Suggerimenti per la sicurezza** <p> _InlineSafetyTipsEnabled_|Attivato <p> `$true`|Attivato <p> `$true`|Attivato <p> `$true`||
|Mittenti consentiti <p> _AllowedSenders_|Nessuno|Nessuno|Nessuno||
|Domini mittenti consentiti <p> _AllowedSenderDomains_|Nessuno|Nessuno|Nessuno|L'aggiunta di domini all'elenco dei mittenti consentiti è una pessima idea. Gli aggressori sarebbero in grado di inviare messaggi di posta elettronica che altrimenti verrebbero filtrati. <p> Utilizzare l' [Intelligence spoof](learn-about-spoof-intelligence.md) nel centro sicurezza & Compliance nella pagina impostazioni di protezione da **posta indesiderata** per esaminare tutti i mittenti che eseguono lo spoofing degli indirizzi di posta elettronica del mittente nei domini di posta elettronica dell'organizzazione o nello spoofing degli indirizzi di posta elettronica del mittente nei domini esterni.|
|Mittenti bloccati <p> _BlockedSenders_|Nessuno|Nessuno|Nessuno||
|Domini mittenti bloccati <p> _BlockedSenderDomains_|Nessuno|Nessuno|Nessuno||
|**Abilita le notifiche di spam all'utente finale** <p> _EnableEndUserSpamNotifications_|Disattivato <p> `$false`|Abilitato <p> `$true`|Abilitato <p> `$true`||
|**Invia notifiche di spam agli utenti finali ogni (giorni)** <p> _EndUserSpamNotificationFrequency_|3 giorni|3 giorni|3 giorni||
|**Spam ZAP** <p> _SpamZapEnabled_|Abilitato <p> `$true`|Abilitato <p> `$true`|Abilitato <p> `$true`||
|**Phishing ZAP** <p> _PhishZapEnabled_|Abilitato <p> `$true`|Abilitato <p> `$true`|Abilitato <p> `$true`||
|_MarkAsSpamBulkMail_|Attivato|Attivato|Attivato|Questa impostazione è disponibile solo in PowerShell.|
|

In criteri di protezione da posta indesiderata sono disponibili diverse altre impostazioni avanzate per il filtro di posta indesiderata. Altre informazioni sulle sequenze temporali per l'ammortamento di queste caratteristiche verranno comunicate al di fuori di questo articolo.

Si **consiglia di disattivare queste impostazioni ASF** sia per i livelli **standard** che per quelli **rigorosi** . Per ulteriori informazioni sulle impostazioni ASF, vedere [Advanced Spam Filter (ASF) Settings in Office 365](advanced-spam-filtering-asf-options.md).

****

|Nome della funzionalità di sicurezza|Aggiungere commenti|
|---|---|
|**Collegamenti di immagini a siti remoti** (_IncreaseScoreWithImageLinks_)||
|**Indirizzo IP numerico in URL** (_IncreaseScoreWithNumericIps_)||
|**Reindirizzamento UL ad altre porte** (_IncreaseScoreWithRedirectToOtherPort_)||
|**URL di siti Web. biz o. info** (_IncreaseScoreWithBizOrInfoUrls_)||
|**Messaggi vuoti** (_MarkAsSpamEmptyMessages_)||
|**JavaScript o VBScript in HTML** (_MarkAsSpamJavaScriptInHtml_)||
|**Tag frame o iframe in formato HTML** (_MarkAsSpamFramesInHtml_)||
|**Tag Object in HTML** (_MarkAsSpamObjectTagsInHtml_)||
|**Tag embed in HTML** (_MarkAsSpamEmbedTagsInHtml_)||
|**Tag del modulo in formato HTML** (_MarkAsSpamFormTagsInHtml_)||
|**Bug Web in HTML** (_MarkAsSpamWebBugsInHtml_)||
|**Applicazione di un elenco di parole riservate** (_MarkAsSpamSensitiveWordList_)||
|**Record SPF: errore** irreversibile (_MarkAsSpamSpfRecordHardFail_)||
|**Filtro ID mittente condizionale: errore** irreversibile (_MarkAsSpamFromAddressAuthFail_)||
|Backscatter del rapporto di **mancato recapito** (_MarkAsSpamNdrBackscatter_)||
|

#### <a name="eop-outbound-spam-policy-settings"></a>Impostazioni di criteri di posta indesiderata in uscita di EOP

Per creare e configurare i criteri di posta indesiderata in uscita, vedere [Configure Outbound Spam Filtering in Office 365](configure-the-outbound-spam-policy.md).

Per ulteriori informazioni sui limiti di invio predefiniti nel servizio, vedere [invio di limiti](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1).

****

|Nome della funzionalità di sicurezza|Predefiniti|Standard|Rigorosa|Aggiungere commenti|
|---|:---:|:---:|:---:|---|
|**Numero massimo di destinatari per utente: limite orario esterno** <p> _RecipientLimitExternalPerHour_|0|500|400|Il valore predefinito 0 indica che vengono utilizzati i valori predefiniti del servizio.|
|**Numero massimo di destinatari per utente: limite orario interno** <p> _RecipientLimitInternalPerHour_|0|1000|800|Il valore predefinito 0 indica che vengono utilizzati i valori predefiniti del servizio.|
|**Numero massimo di destinatari per utente: limite giornaliero** <p> _RecipientLimitPerDay_|0|1000|800|Il valore predefinito 0 indica che vengono utilizzati i valori predefiniti del servizio.|
|**Azione quando un utente supera i limiti** <p> _ActionWhenThresholdReached_|**Impedire all'utente di inviare messaggi di posta elettronica fino al giorno seguente** <p> `BlockUserForToday`|**Impedire all'utente di inviare messaggi di posta elettronica** <p> `BlockUser`|**Impedire all'utente di inviare messaggi di posta elettronica** <p> `BlockUser`||
|

### <a name="eop-anti-malware-policy-settings"></a>Impostazioni dei criteri anti-malware di EOP

Per creare e configurare criteri anti-malware, vedere [Configure anti-malware Policies in Office 365](configure-anti-malware-policies.md).

****

|Nome della funzionalità di sicurezza|Predefiniti|Standard|Rigorosa|Aggiungere commenti|
|---|:---:|:---:|:---:|---|
|**Si desidera inviare una notifica ai destinatari se i messaggi vengono messi in quarantena?** <p> _Azione_|No <p> _DeleteMessage_|No <p> _DeleteMessage_|No <p> _DeleteMessage_|Se il malware viene rilevato in un allegato di posta elettronica, il messaggio viene messo in quarantena e può essere rilasciato solo da un amministratore.|
|**Filtro di tipi di allegati comuni** <p> _EnableFileFilter_|Disattivato <p> `$false`|Attivato <p> `$true`|Attivato <p> `$true`|Questa impostazione mette in quarantena i messaggi che contengono allegati eseguibili in base al tipo di file, indipendentemente dal contenuto degli allegati.|
|**Malware zero-hour auto Purge** <p> _ZapEnabled_|Attivato <p> `$true`|Attivato <p> `$true`|Attivato <p> `$true`||
|**Notifica ai mittenti interni** del messaggio non recapitato <p> _EnableInternalSenderNotifications_|Disattivato <p> `$false`|Disattivato <p> `$false`|Disattivato <p> `$false`||
|**Notifica ai mittenti esterni** del messaggio non recapitato <p> _EnableExternalSenderNotifications_|Disattivato <p> `$false`|Disattivato <p> `$false`|Disattivato <p> `$false`||
|

### <a name="eop-default-anti-phishing-policy-settings"></a>Impostazioni di criteri anti-phishing predefinite di EOP

Per ulteriori informazioni su queste impostazioni, vedere [spoofing Settings](set-up-anti-phishing-policies.md#spoof-settings). Per configurare queste impostazioni, vedere [Configure anti-phishing Policies in EOP](configure-anti-phishing-policies-eop.md).

****

|Nome della funzionalità di sicurezza|Predefiniti|Standard|Rigorosa|Aggiungere commenti|
|---|:---:|:---:|:---:|---|
|**Abilitare la protezione anti-spoofing** <p> _EnableAntispoofEnforcement_|Attivato <p> `$true`|Attivato <p> `$true`|Attivato <p> `$true`||
|**Abilitazione del mittente non autenticato** <p> _EnableUnauthenticatedSender_|Attivato <p> `$true`|Attivato <p> `$true`|Attivato <p> `$true`|Aggiunge un punto interrogativo (?) alla foto del mittente in Outlook per i mittenti non identificati falsificati. Per ulteriori informazioni, vedere [spoofing Settings in anti-phishing Policies](set-up-anti-phishing-policies.md).|
|**Se il messaggio di posta elettronica viene inviato da un utente che non ha il diritto di falsificare il dominio** <p> _AuthenticationFailAction_|**Spostare il messaggio nelle cartelle di posta indesiderata dei destinatari** <p> `MoveToJmf`|**Spostare il messaggio nelle cartelle di posta indesiderata dei destinatari** <p> `MoveToJmf`|**Mettere in quarantena il messaggio** <p> `Quarantine`|Questa impostazione si applica ai mittenti bloccati in [Intelligence contraffatta](learn-about-spoof-intelligence.md).|
|

## <a name="microsoft-defender-for-office-365-security"></a>Microsoft Defender per la sicurezza di Office 365

Ulteriori vantaggi per la sicurezza sono disponibili con un abbonamento a Microsoft Defender per Office 365. Per le notizie e le informazioni più recenti, è possibile visualizzare le [novità di Defender per Office 365](whats-new-in-office-365-atp.md).

> [!IMPORTANT]
>
> - Il criterio anti-phishing predefinito in Microsoft Defender per Office 365 fornisce [protezione da spoofing](set-up-anti-phishing-policies.md#spoof-settings) e funzionalità di intelligence delle cassette postali per tutti i destinatari. Tuttavia, le altre funzionalità di [protezione delle rappresentazioni](#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) disponibili e le [Impostazioni avanzate](#advanced-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) non sono configurate o abilitate nel criterio predefinito. Per abilitare tutte le funzionalità di protezione, modificare il criterio di anti-phishing predefinito o creare ulteriori criteri anti-phishing.
>
> - Non ci sono criteri collegamenti sicuri predefiniti o criteri allegati sicuri che proteggono automaticamente tutti i destinatari nell'organizzazione. Per ottenere le protezioni, è necessario creare almeno un criterio per i collegamenti sicuri e un criterio degli allegati sicuri.
>
> - [ATP per SharePoint, OneDrive e Microsoft teams](atp-for-spo-odb-and-teams.md) Protection and [Safe Documents](safe-docs.md) Protection non hanno dipendenze dai criteri dei collegamenti sicuri.

Se l'abbonamento include Microsoft Defender per Office 365 o se è stato acquistato il difensore per Office 365 come componente aggiuntivo, impostare le configurazioni standard o rigorose seguenti.

### <a name="anti-phishing-policy-settings-in-microsoft-defender-for-office-365"></a>Impostazioni dei criteri di anti-phishing in Microsoft Defender per Office 365

I clienti di EOP ottengono un anti-phishing di base come descritto in precedenza, ma Microsoft Defender per Office 365 include altre caratteristiche e controlli che consentono di prevenire, rilevare e correggere gli attacchi. Per creare e configurare questi criteri, vedere [Configure anti-phishing policys in Defender for Office 365](configure-atp-anti-phishing-policies.md).

#### <a name="impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Impostazioni di rappresentazione nei criteri di anti-phishing in Microsoft Defender per Office 365

Per ulteriori informazioni su queste impostazioni, vedere [impostazioni di rappresentazione nei criteri di anti-phishing in Microsoft Defender per Office 365](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365). Per configurare queste impostazioni, vedere [Configure anti-phishing Policies in Defender for Office 365](configure-atp-anti-phishing-policies.md).

****

|Nome della funzionalità di sicurezza|Predefiniti|Standard|Rigorosa|Aggiungere commenti|
|---|:---:|:---:|:---:|---|
|Utenti protetti: **aggiungere utenti a Protect** <p> _È impostato enabletargeteduserprotection_ <p> _TargetedUsersToProtect_|Off <p> `$false` <p> nessuno|Attivato <p> `$true` <p> \<list of users\>|Attivato <p> `$true` <p> \<list of users\>|A seconda dell'organizzazione, è consigliabile aggiungere utenti (mittenti dei messaggi) in ruoli chiave. Internamente, i mittenti protetti potrebbero essere il CEO, il CFO e altri leader senior. Esternamente, i mittenti protetti possono includere i membri del Consiglio o il Consiglio di amministrazione.|
|Domini protetti: **includono automaticamente i domini che possiedo** <p> _EnableOrganizationDomainsProtection_|Disattivato <p> `$false`|Attivato <p> `$true`|Attivato <p> `$true`||
|Domini protetti: **includere domini personalizzati** <p> _EnableTargetedDomainsProtection_ <p> _TargetedDomainsToProtect_|Off <p> `$false` <p> nessuno|Attivato <p> `$true` <p> \<list of domains\>|Attivato <p> `$true` <p> \<list of domains\>|A seconda dell'organizzazione, è consigliabile aggiungere domini (domini mittenti) che non sono proprietari, ma con cui si interagisce spesso.|
|Utenti protetti: **se il messaggio di posta elettronica viene inviato da un utente rappresentato** <p> _TargetedUserProtectionAction_|**Non applicare alcuna azione** <p> `NoAction`|**Mettere in quarantena il messaggio** <p> `Quarantine`|**Mettere in quarantena il messaggio** <p> `Quarantine`||
|Domini protetti: **se il messaggio di posta elettronica viene inviato da un dominio rappresentato** <p> _TargetedDomainProtectionAction_|**Non applicare alcuna azione** <p> `NoAction`|**Mettere in quarantena il messaggio** <p> `Quarantine`|**Mettere in quarantena il messaggio** <p> `Quarantine`||
|**Mostrare il suggerimento per gli utenti rappresentati** <p> _EnableSimilarUsersSafetyTips_|Disattivato <p> `$false`|Attivato <p> `$true`|Attivato <p> `$true`||
|**Mostrare il suggerimento per i domini rappresentati** <p> _EnableSimilarDomainsSafetyTips_|Disattivato <p> `$false`|Attivato <p> `$true`|Attivato <p> `$true`||
|**Mostra suggerimento per i caratteri insoliti** <p> _EnableUnusualCharactersSafetyTips_|Disattivato <p> `$false`|Attivato <p> `$true`|Attivato <p> `$true`||
|**Abilitare l'intelligence delle cassette postali?** <p> _EnableMailboxIntelligence_|Attivato <p> `$true`|Attivato <p> `$true`|Attivato <p> `$true`||
|**Abilitare la protezione della rappresentazione basata sull'Intelligence delle cassette postali?** <p> _EnableMailboxIntelligenceProtection_|Disattivato <p> `$false`|Attivato <p> `$true`|Attivato <p> `$true`||
|**Se il messaggio di posta elettronica viene inviato da un utente rappresentato protetto dalla funzionalità di intelligence delle cassette postali** <p> _MailboxIntelligenceProtectionAction_|**Non applicare alcuna azione** <p> `NoAction`|**Spostare il messaggio nelle cartelle di posta indesiderata dei destinatari** <p> `MoveToJmf`|**Mettere in quarantena il messaggio** <p> `Quarantine`||
|**Mittenti attendibili** <p> _ExcludedSenders_|Nessuno|Nessuno|Nessuno|A seconda dell'organizzazione, è consigliabile aggiungere utenti che vengono erroneamente contrassegnati come phishing a causa solo della rappresentazione e non di altri filtri.|
|**Domini attendibili** <p> _ExcludedDomains_|Nessuno|Nessuno|Nessuno|A seconda dell'organizzazione, è consigliabile aggiungere domini che vengono erroneamente contrassegnati come phishing a causa solo della rappresentazione e non di altri filtri.|
|

#### <a name="spoof-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Impostazioni di spoofing nei criteri di anti-phishing in Microsoft Defender per Office 365

Si noti che si tratta delle stesse impostazioni disponibili nelle impostazioni dei criteri di protezione [da posta indesiderata in EOP](#eop-anti-spam-policy-settings).

****

|Nome della funzionalità di sicurezza|Predefiniti|Standard|Rigorosa|Aggiungere commenti|
|---|---|---|---|---|
|**Abilitare la protezione anti-spoofing** <p> _EnableAntispoofEnforcement_|Attivato <p> `$true`|Attivato <p> `$true`|Attivato <p> `$true`||
|**Abilitazione del mittente non autenticato** <p> _EnableUnauthenticatedSender_|Attivato <p> `$true`|Attivato <p> `$true`|Attivato <p> `$true`|Aggiunge un punto interrogativo (?) alla foto del mittente in Outlook per i mittenti non identificati falsificati. Per ulteriori informazioni, vedere [spoofing Settings in anti-phishing Policies](set-up-anti-phishing-policies.md).|
|**Se il messaggio di posta elettronica viene inviato da un utente che non ha il diritto di falsificare il dominio** <p> _AuthenticationFailAction_|**Spostare il messaggio nelle cartelle di posta indesiderata dei destinatari** <p> `MoveToJmf`|**Spostare il messaggio nelle cartelle di posta indesiderata dei destinatari** <p> `MoveToJmf`|**Mettere in quarantena il messaggio** <p> `Quarantine`|Questa impostazione si applica ai mittenti bloccati in [Intelligence contraffatta](learn-about-spoof-intelligence.md).|
|

#### <a name="advanced-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Impostazioni avanzate nei criteri di anti-phishing in Microsoft Defender per Office 365

Per ulteriori informazioni su questa impostazione, vedere [Advanced phishing Thresholds in anti-phishing Policies in Microsoft Defender for Office 365](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365). Per configurare questa impostazione, vedere [Configure anti-phishing Policies in Defender for Office 365](configure-atp-anti-phishing-policies.md).

****

|Nome della funzionalità di sicurezza|Predefiniti|Standard|Rigorosa|Aggiungere commenti|
|---|:---:|:---:|:---:|---|
|**Soglie di phishing avanzate** <p> _PhishThresholdLevel_|**1-standard** <p> `1`|**2-aggressivo** <p> `2`|**3-maggiore aggressività** <p> `3`||
|

### <a name="safe-links-settings"></a>Impostazioni collegamenti attendibili

I collegamenti sicuri in Defender per Office 365 includono le impostazioni globali che si applicano a tutti gli utenti inclusi nei criteri dei collegamenti sicuri attivi e le impostazioni specifiche per ogni criterio di collegamenti sicuri. Per ulteriori informazioni, vedere [collegamenti sicuri in Defender per Office 365](atp-safe-links.md).

#### <a name="global-settings-for-safe-links"></a>Impostazioni globali per i collegamenti sicuri

Per configurare queste impostazioni, vedere [Configure Global Settings for Safe Links in Defender for Office 365](configure-global-settings-for-safe-links.md).

In PowerShell, è possibile utilizzare il cmdlet [set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365) per queste impostazioni.

****

|Nome della funzionalità di sicurezza|Predefiniti|Standard|Rigorosa|Aggiungere commenti|
|---|:---:|:---:|:---:|---|
|**Utilizzare collegamenti sicuri in: applicazioni di Office 365** <p> _EnableSafeLinksForO365Clients_|Attivato <p> `$true`|Attivato <p> `$true`|Attivato <p> `$true`|Utilizzare collegamenti sicuri nelle app di Office 365 Desktop e mobili (iOS e Android) supportate. Per ulteriori informazioni, vedere [impostazioni dei collegamenti sicuri per le app di Office 365](atp-safe-links.md#safe-links-settings-for-office-365-apps).|
|**Non monitorare quando gli utenti fanno clic su collegamenti sicuri** <p> _TrackClicks_|Attivato <p> `$false`|Disattivato <p> `$true`|Off <p> `$true`|La disattivazione di questa impostazione (impostazione di _TrackClicks_ `$true` ) tiene traccia degli scatti degli utenti nelle app di Office 365 supportate.|
|**Non consentire agli utenti di fare clic su collegamenti sicuri all'URL originale** <p> _AllowClickThrough_|Attivato <p> `$false`|Attivato <p> `$false`|Attivato <p> `$false`|Se si attiva questa impostazione (impostare _AllowClickThrough_ su `$false` ), si impedisce di fare clic sull'URL originale nelle app di Office 365 supportate.|
|

#### <a name="safe-links-policy-settings"></a>Impostazioni per i criteri collegamenti sicuri

Per configurare queste impostazioni, vedere Configurare i [criteri dei collegamenti sicuri in Microsoft Defender per Office 365](set-up-atp-safe-links-policies.md).

In PowerShell, è possibile utilizzare i cmdlet [New-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safelinkspolicy) e [set-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy) per queste impostazioni.

> [!NOTE]
> Come descritto in precedenza, non esiste alcun criterio di collegamenti sicuri predefinito. I valori nella colonna predefinita sono i valori predefiniti nei nuovi criteri collegamenti sicuri creati.

****

|Nome della funzionalità di sicurezza|Predefiniti|Standard|Rigorosa|Aggiungere commenti|
|---|:---:|:---:|:---:|---|
|**Selezionare l'azione per gli URL potenzialmente dannosi sconosciuti nei messaggi** <p> _Proprietà IsEnabled_|Disattivato <p> `$false`|Attivato <p> `$true`|Attivato <p> `$true`||
|**Selezionare l'azione per gli URL sconosciuti o potenzialmente dannosi all'interno di Microsoft Teams** <p> _EnableSafeLinksForTeams_|Disattivato <p> `$false`|Attivato <p> `$true`|Attivato <p> `$true`||
|**Applicazione dell'analisi degli URL in tempo reale per collegamenti e collegamenti sospetti che puntano a file** <p> _ScanUrls_|Disattivato <p> `$false`|Attivato <p> `$true`|Attivato <p> `$true`||
|**Attendere il completamento dell'analisi degli URL prima di recapitare il messaggio** <p> _DeliverMessageAfterScan_|Disattivato <p> `$false`|Attivato <p> `$true`|Attivato <p> `$true`||
|**Applicazione di collegamenti sicuri ai messaggi di posta elettronica inviati all'interno dell'organizzazione** <p> _EnableForInternalSenders_|Disattivato <p> `$false`|Attivato <p> `$true`|Attivato <p> `$true`||
|**Non monitorare i clic dell'utente** <p> _DoNotTrackUserClicks_|Off <p> `$false`|Off <p> `$false`|Off <p> `$false`|La disattivazione di questa impostazione (impostazione di _DoNotTrackUserClicks_ su `$false` ) tiene traccia degli utenti.|
|**Non consentire agli utenti di fare clic sull'URL originale** <p> _DoNotAllowClickThrough_|Disattivato <p> `$false`|Attivato <p> `$true`|Attivato <p> `$true`|Se si attiva questa impostazione (impostare _DoNotAllowClickThrough_ su `$true` ), si impedisce di fare clic sull'URL originale.|
|

### <a name="safe-attachments-settings"></a>Impostazioni degli allegati sicuri

Gli allegati sicuri in Microsoft Defender per Office 365 includono le impostazioni globali che non hanno relazioni con i criteri degli allegati sicuri e le impostazioni specifiche di ogni criterio per i collegamenti sicuri. Per ulteriori informazioni, vedere [allegati sicuri in Defender per Office 365](atp-safe-attachments.md).

#### <a name="global-settings-for-safe-attachments"></a>Impostazioni globali per gli allegati sicuri

Per configurare queste impostazioni, vedere [abilitare ATP per SharePoint, OneDrive e Microsoft teams](turn-on-atp-for-spo-odb-and-teams.md) e [documenti attendibili in Microsoft 365 E5](safe-docs.md).

In PowerShell, è possibile utilizzare il cmdlet [set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365) per queste impostazioni.

****

|Nome della funzionalità di sicurezza|Predefiniti|Standard|Rigorosa|Aggiungere commenti|
|---|:---:|:---:|:---:|---|
|**Attivare ATP per SharePoint, OneDrive e Microsoft Teams** <p> _EnableATPForSPOTeamsODB_|Attivato <p> `$true`|Attivato <p> `$true`||
|**Attivazione di documenti attendibili per i client di Office** <p> _EnableSafeDocs_|Attivato <p> `$true`|Attivato <p> `$true`|Questa impostazione è disponibile solo con le licenze di sicurezza Microsoft 365 E5 o Microsoft 365 E5. Per ulteriori informazioni, vedere [documenti attendibili in Microsoft Defender per Office 365](safe-docs.md).|
|**Consenti agli utenti di fare clic su una visualizzazione protetta anche se i documenti attendibili hanno identificato il file come dannoso** <p> _AllowSafeDocsOpen_|Off <p> `$false`|Off <p> `$false`|Questa impostazione è correlata ai documenti attendibili.|
|

#### <a name="safe-attachments-policy-settings"></a>Impostazioni di criteri per gli allegati sicuri

Per configurare queste impostazioni, vedere Configurare i criteri per gli [allegati sicuri in Defender per Office 365](set-up-atp-safe-attachments-policies.md).

In PowerShell, è possibile utilizzare i cmdlet [New-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentpolicy) e [set-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy) per queste impostazioni.

> [!NOTE]
> Come descritto in precedenza, non esiste alcun criterio di allegati sicuri predefinito. I valori nella colonna predefinita sono i valori predefiniti nei nuovi criteri allegati sicuri creati.

****

|Nome della funzionalità di sicurezza|Predefiniti|Standard|Rigorosa|Aggiungere commenti|
|---|:---:|:---:|:---:|---|
|**Risposta malware per gli allegati sicuri sconosciuta** <p> _Azione_|Blocca <p> `Block`|Blocca <p> `Block`|Blocca <p> `Block`||
|**Redirect Attachment on Detection** : **Enable redirect** <p> _Reindirizza_ <p> _RedirectAddress_|E non è stato specificato alcun indirizzo di posta elettronica. <p> `$true` <p> nessuno|Attiva e specificare un indirizzo di posta elettronica. <p> `$true` <p> un indirizzo di posta elettronica|Attiva e specificare un indirizzo di posta elettronica. <p> `$true` <p> un indirizzo di posta elettronica|Reindirizzare i messaggi a un amministratore della sicurezza per la revisione.|
|**Applicare la selezione precedente se si verifica un errore durante l'analisi di malware per gli allegati.** <p> _ActionOnError_|Attivato <p> `$true`|Attivato <p> `$true`|Attivato <p> `$true`||
|

## <a name="related-articles"></a>Articoli correlati

- Per informazioni sulle procedure consigliate per **le regole del flusso di posta di Exchange (note anche come regole di trasporto**) Vedere [procedure consigliate per la configurazione delle regole del flusso di posta in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/configuration-best-practices).

- Gli amministratori e gli utenti possono inviare falsi positivi (buon messaggio di posta elettronica contrassegnato come cattivo) e falsi negativi (messaggi di posta elettronica non consentiti) a Microsoft per l'analisi. Per altre informazioni, vedere [Segnalazione di messaggi e file a Microsoft](report-junk-email-messages-to-microsoft.md).

- Utilizzare questi collegamenti per informazioni su come **configurare** il [servizio EOP](set-up-your-eop-service.md)e **configurare** [Microsoft Defender per Office 365](office-365-atp.md). Non dimenticare le indicazioni utili in '[protezione dalle minacce in Office 365](protect-against-threats.md)'.

- Le **linee di base per la sicurezza per Windows** sono disponibili qui: [dove è possibile ottenere le previsioni di sicurezza? per le](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines#where-can-i-get-the-security-baselines) opzioni di criteri di gruppo/locali e utilizzare le [previsioni di sicurezza per configurare i dispositivi Windows 10 in Intune](https://docs.microsoft.com/intune/protect/security-baselines) per la sicurezza basata su Intune. Infine, è disponibile un confronto tra le linee di sicurezza di Microsoft Defender per endpoint e Microsoft Intune in [confronto tra Microsoft Defender per endpoint e le previsioni di sicurezza di Windows Intune](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-machines-security-baseline#compare-the-microsoft-defender-atp-and-the-windows-intune-security-baselines).
