---
title: Suggerimenti Microsoft per le impostazioni di sicurezza di EOP e Defender per Office 365
keywords: Suggerimenti per la sicurezza di Office 365, Sender Policy Framework, Domain-based Message Reporting and Conformance, DomainKeys Identified Mail, passaggi, come funziona, linee di base della sicurezza, linee di base per EOP, linee di base per Defender per Office 365, configurare Defender per Office 365, configurare EOP, configurare Defender per Office 365, configurare Defender per Office 365, configurazione della sicurezza
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
description: Quali sono le procedure consigliate per le impostazioni di sicurezza di Exchange Online Protection (EOP) e Defender per Office 365? Quali sono i consigli correnti per la protezione standard? Cosa usare se si vuole essere più rigidi? E quali funzionalità aggiuntive si ottengono se si usa anche Defender per Office 365?
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d635a28c41c9aceb0e3c499301156e53a1e2fa68
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289354"
---
# <a name="recommended-settings-for-eop-and-microsoft-defender-for-office-365-security"></a>Impostazioni consigliate per EOP e Microsoft Defender per la sicurezza di Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

**Exchange Online Protection (EOP)** è il core della sicurezza per gli abbonamenti a Microsoft 365 e consente di evitare che messaggi di posta elettronica dannosi raggiungano le cartelle Posta in arrivo dei dipendenti. Tuttavia, con nuovi attacchi più sofisticati che emergono ogni giorno, spesso sono necessarie protezioni migliorate. **Microsoft Defender per Office 365** Il piano 1 o il piano 2 contengono funzionalità aggiuntive che offrono agli amministratori più livelli di sicurezza, controllo e analisi.

Sebbene gli amministratori della sicurezza siano in grado di personalizzare le impostazioni di sicurezza, sono disponibili due livelli di sicurezza in EOP e Microsoft Defender per Office 365: **Standard** e **Strict.** L'ambiente e le esigenze di ogni cliente sono diversi, ma riteniamo che questi livelli di filtro impediranno alla posta indesiderata di raggiungere la Posta in arrivo dei dipendenti nella maggior parte delle situazioni.

Per applicare automaticamente le impostazioni Standard o Strict agli utenti, vedere Criteri di sicurezza preimpostati [in EOP e Microsoft Defender per Office 365.](preset-security-policies.md)

> [!NOTE]
> Per il corretto funzionamento del filtro, è necessario che la regola di posta indesiderata sia abilitata nelle cassette postali. È abilitato per impostazione predefinita, ma è consigliabile controllarlo se il filtro non sembra funzionare. Per altre informazioni, vedere [Configurare le impostazioni della posta indesiderata nelle cassette postali di Exchange Online in Office 365](configure-junk-email-settings-on-exo-mailboxes.md).

In questo articolo vengono descritte le impostazioni predefinite e le impostazioni Standard e Strict consigliate per proteggere gli utenti.

> [!TIP]
> Il modulo Office 365 Advanced Threat Protection Recommended Configuration Analyzer (ORCA) per PowerShell consente agli amministratori di trovare i valori correnti di queste impostazioni. In particolare, il cmdlet **Get-ORCAReport** genera una valutazione della protezione da posta indesiderata, anti-phishing e altre impostazioni di igiene dei messaggi. È possibile scaricare il modulo ORCA all'indirizzo <https://www.powershellgallery.com/packages/ORCA/> .

## <a name="anti-spam-anti-malware-and-anti-phishing-protection-in-eop"></a>Protezione da posta indesiderata, antimalware e anti-phishing in EOP

La protezione da posta indesiderata, antimalware e anti-phishing sono funzionalità di EOP che possono essere configurate dagli amministratori. È consigliabile eseguire le configurazioni Standard o Strict seguenti.

### <a name="eop-anti-spam-policy-settings"></a>Impostazioni dei criteri di protezione da posta indesiderata di EOP

Per creare e configurare criteri di protezione dalla posta indesiderata, vedere Configurare i criteri di protezione da posta [indesiderata in Office 365.](configure-your-spam-filter-policies.md)

****

|Nome caratteristica di sicurezza|Predefiniti|Standard|Strict|Commento|
|---|:---:|:---:|:---:|---|
|**Azione di rilevamento** della posta indesiderata <p> _SpamAction_|**Sposta messaggio nella cartella Posta indesiderata** <p> `MoveToJmf`|**Sposta messaggio nella cartella Posta indesiderata** <p> `MoveToJmf`|**Metti in quarantena messaggio** <p> `Quarantine`||
|**Azione di rilevamento della posta indesiderata** con alta probabilità <p> _HighConfidenceSpamAction_|**Sposta messaggio nella cartella Posta indesiderata** <p> `MoveToJmf`|**Metti in quarantena messaggio** <p> `Quarantine`|**Metti in quarantena messaggio** <p> `Quarantine`||
|**Azione di rilevamento della posta** elettronica di phishing <p> _PhishSpamAction_|**Sposta messaggio nella cartella Posta indesiderata** <p> `MoveToJmf`|**Metti in quarantena messaggio** <p> `Quarantine`|**Metti in quarantena messaggio** <p> `Quarantine`||
|**Azione di rilevamento della posta elettronica di phishing** ad alta probabilità <p> _HighConfidencePhishAction_|**Metti in quarantena messaggio** <p> `Quarantine`|**Metti in quarantena messaggio** <p> `Quarantine`|**Metti in quarantena messaggio** <p> `Quarantine`||
|**Azione di rilevamento della posta** elettronica in blocco <p> _BulkSpamAction_|**Sposta messaggio nella cartella Posta indesiderata** <p> `MoveToJmf`|**Sposta messaggio nella cartella Posta indesiderata** <p> `MoveToJmf`|**Metti in quarantena messaggio** <p> `Quarantine`||
|Soglia posta elettronica in blocco <p> _BulkThreshold_|7 |6 |4 |Per informazioni dettagliate, vedere [Bulk complaint level (BCL) in Office 365.](bulk-complaint-level-values.md)|
|Periodo di conservazione della quarantena <p> _QuarantineRetentionPeriod_|15 giorni|30 giorni|30 giorni||
|**Suggerimenti per la sicurezza** <p> _InlineSafetyTipsEnabled_|Attivato <p> `$true`|Attivato <p> `$true`|Attivato <p> `$true`||
|Mittenti consentiti <p> _AllowedSenders_|Nessuno|Nessuno|Nessuno||
|Domini mittente consentiti <p> _AllowedSenderDomains_|Nessuno|Nessuno|Nessuno|L'aggiunta di domini all'elenco dei mittenti consentiti è una pessima idea. Gli utenti malintenzionati sarebbero in grado di inviare messaggi di posta elettronica che altrimenti verrebbero filtrati. <p> Usare [spoof intelligence](learn-about-spoof-intelligence.md) nel Centro sicurezza &  conformità nella pagina Impostazioni protezione posta indesiderata per esaminare tutti i mittenti che effettuano lo spoofing degli indirizzi di posta elettronica dei mittenti nei domini di posta elettronica dell'organizzazione o lo spoofing degli indirizzi di posta elettronica dei mittenti nei domini esterni.|
|Mittenti bloccati <p> _BlockedSenders_|Nessuno|Nessuno|Nessuno||
|Domini mittente bloccati <p> _BlockedSenderDomains_|Nessuno|Nessuno|Nessuno||
|**Abilita le notifiche di spam all'utente finale** <p> _EnableEndUserSpamNotifications_|Disattivato <p> `$false`|Abilitato <p> `$true`|Abilitato <p> `$true`||
|**Invia notifiche di spam agli utenti finali ogni (giorni)** <p> _EndUserSpamNotificationFrequency_|3 giorni|3 giorni|3 giorni||
|**ZaP della posta indesiderata** <p> _SpamZapEnabled_|Abilitato <p> `$true`|Abilitato <p> `$true`|Abilitato <p> `$true`||
|**Phish ZAP** <p> _PhishZapEnabled_|Abilitato <p> `$true`|Abilitato <p> `$true`|Abilitato <p> `$true`||
|_MarkAsSpamBulkMail_|Attivato|Attivato|Attivato|Questa impostazione è disponibile solo in PowerShell.|
|

Esistono diverse altre impostazioni di Advanced Spam Filter (ASF) nei criteri di protezione da posta indesiderata che sono in fase di deprecazione. Ulteriori informazioni sulle sequenze temporali per l'ammortamento di queste funzionalità verranno comunicate all'esterno di questo articolo.

Ti consigliamo di disattivare queste impostazioni ASF **per** i **livelli Standard** **e Strict.** Per ulteriori informazioni sulle impostazioni ASF, vedere [Advanced Spam Filter (ASF) settings in Office 365.](advanced-spam-filtering-asf-options.md)

****

|Nome caratteristica di sicurezza|Commento|
|---|---|
|**Collegamenti immagine a siti remoti** (_IncreaseScoreWithImageLinks_)||
|**Indirizzo IP numerico nell'URL** (_IncreaseScoreWithNumericIps_)||
|**Reindirizzamento UL ad altra porta** (_IncreaseScoreWithRedirectToOtherPort_)||
|**URL dei siti Web .biz o .info** (_IncreaseScoreWithBizOrInfoUrls_)||
|**Messaggi vuoti** (_MarkAsSpamEmptyMessages_)||
|**JavaScript o VBScript in HTML** (_MarkAsSpamJavaScriptInHtml_)||
|**Tag Frame o IFrame in HTML** (_MarkAsSpamFramesInHtml_)||
|**Tag oggetto in HTML** (_MarkAsSpamObjectTagsInHtml_)||
|**Incorporare tag in HTML** (_MarkAsSpamEmbedTagsInHtml_)||
|**Tag modulo in HTML** (_MarkAsSpamFormTagsInHtml_)||
|**Bug Web in HTML** (_MarkAsSpamWebBugsInHtml_)||
|**Applicare un elenco di parole** sensibili (_MarkAsSpamSensitiveWordList_)||
|**Record SPF: hard fail** (_MarkAsSpamSpfRecordHardFail_)||
|**Filtro ID mittente condizionale: non riuscito** (_MarkAsSpamFromAddressAuthFail_)||
|**Rapporto di mancato recapito** (_MarkAsSpamNdrBackscatter_)||
|

#### <a name="eop-outbound-spam-policy-settings"></a>Impostazioni dei criteri di protezione da posta indesiderata in uscita di EOP

Per creare e configurare i criteri di posta indesiderata in uscita, vedere Configurare il filtro posta [indesiderata in uscita in Office 365.](configure-the-outbound-spam-policy.md)

Per ulteriori informazioni sui limiti di invio predefiniti nel servizio, vedere [Limiti di invio.](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1)

****

|Nome caratteristica di sicurezza|Predefiniti|Standard|Strict|Commento|
|---|:---:|:---:|:---:|---|
|**Numero massimo di destinatari per utente: limite orario esterno** <p> _RecipientLimitExternalPerHour_|0|500|400|Il valore predefinito 0 indica l'utilizzo delle impostazioni predefinite del servizio.|
|**Numero massimo di destinatari per utente: limite orario interno** <p> _RecipientLimitInternalPerHour_|0|1000|800|Il valore predefinito 0 indica l'utilizzo delle impostazioni predefinite del servizio.|
|**Numero massimo di destinatari per utente: limite giornaliero** <p> _RecipientLimitPerDay_|0|1000|800|Il valore predefinito 0 indica l'utilizzo delle impostazioni predefinite del servizio.|
|**Azione quando un utente supera i limiti** <p> _ActionWhenThresholdReached_|**Impedire all'utente di inviare posta fino al giorno successivo** <p> `BlockUserForToday`|**Limitare l'invio di posta all'utente** <p> `BlockUser`|**Limitare l'invio di posta all'utente** <p> `BlockUser`||
|

### <a name="eop-anti-malware-policy-settings"></a>Impostazioni dei criteri antimalware di EOP

Per creare e configurare criteri antimalware, vedere [Configurare i criteri antimalware in Office 365.](configure-anti-malware-policies.md)

****

|Nome caratteristica di sicurezza|Predefiniti|Standard|Strict|Commento|
|---|:---:|:---:|:---:|---|
|**Si desidera inviare una notifica ai destinatari se i loro messaggi sono in quarantena?** <p> _Azione_|No <p> _DeleteMessage_|No <p> _DeleteMessage_|No <p> _DeleteMessage_|Se viene rilevato malware in un allegato di posta elettronica, il messaggio viene messo in quarantena e può essere rilasciato solo da un amministratore.|
|**Filtro tipi di allegati comuni** <p> _EnableFileFilter_|Disattivato <p> `$false`|Attivato <p> `$true`|Attivato <p> `$true`|Questa impostazione consente di mettere in quarantena i messaggi che contengono allegati eseguibili in base al tipo di file, indipendentemente dal contenuto dell'allegato.|
|**Malware Zero-hour Auto Purge** <p> _ZapEnabled_|Attivato <p> `$true`|Attivato <p> `$true`|Attivato <p> `$true`||
|**Notificare ai mittenti** interni il messaggio non recapitato <p> _EnableInternalSenderNotifications_|Disattivato <p> `$false`|Disattivato <p> `$false`|Disattivato <p> `$false`||
|**Notificare ai mittenti** esterni il messaggio non recapitato <p> _EnableExternalSenderNotifications_|Disattivato <p> `$false`|Disattivato <p> `$false`|Disattivato <p> `$false`||
|

### <a name="eop-default-anti-phishing-policy-settings"></a>Impostazioni dei criteri anti-phishing predefiniti di EOP

Per ulteriori informazioni su queste impostazioni, vedere [Impostazioni spoofing.](set-up-anti-phishing-policies.md#spoof-settings) Per configurare queste impostazioni, vedere [Configurare i criteri anti-phishing in EOP.](configure-anti-phishing-policies-eop.md)

****

|Nome caratteristica di sicurezza|Predefiniti|Standard|Strict|Commento|
|---|:---:|:---:|:---:|---|
|**Abilitare la protezione anti-spoofing** <p> _EnableSpoofIntelligence_|Attivato <p> `$true`|Attivato <p> `$true`|Attivato <p> `$true`||
|**Abilita mittente non autenticato** <p> _EnableUnauthenticatedSender_|Attivato <p> `$true`|Attivato <p> `$true`|Attivato <p> `$true`|Aggiunge un punto interrogativo (?) alla foto del mittente in Outlook per mittenti falsificati non identificati. Per ulteriori informazioni, vedere [Impostazioni di spoofing nei criteri anti-phishing.](set-up-anti-phishing-policies.md)|
|**Se la posta elettronica viene inviata da un utente a cui non è consentito effettuare lo spoofing del dominio** <p> _AuthenticationFailAction_|**Spostare il messaggio nelle cartelle Posta indesiderata dei destinatari** <p> `MoveToJmf`|**Spostare il messaggio nelle cartelle Posta indesiderata dei destinatari** <p> `MoveToJmf`|**Mettere in quarantena il messaggio** <p> `Quarantine`|Questa impostazione si applica ai mittenti bloccati in [spoof intelligence.](learn-about-spoof-intelligence.md)|
|

## <a name="microsoft-defender-for-office-365-security"></a>Sicurezza di Microsoft Defender per Office 365

Ulteriori vantaggi per la sicurezza sono disponibili con un abbonamento a Microsoft Defender per Office 365. Per le notizie e le informazioni più recenti, vedere Novità [di Defender per Office 365.](whats-new-in-office-365-atp.md)

> [!IMPORTANT]
>
> - Il criterio anti-phishing predefinito in Microsoft Defender per Office 365 fornisce protezione [spoofing](set-up-anti-phishing-policies.md#spoof-settings) e intelligence delle cassette postali per tutti i destinatari. Tuttavia, le altre funzionalità di [protezione della rappresentazione](#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) disponibili e le [impostazioni avanzate](#advanced-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) non sono configurate o abilitate nel criterio predefinito. Per abilitare tutte le funzionalità di protezione, modificare il criterio anti-phishing predefinito o creare ulteriori criteri anti-phishing.
>
> - Non sono disponibili criteri collegamenti sicuri o allegati sicuri predefiniti che proteggano automaticamente tutti i destinatari nell'organizzazione. Per ottenere le protezioni, è necessario creare almeno un criterio collegamenti sicuri e allegati sicuri.
>
> - [Gli allegati sicuri per la protezione di SharePoint, OneDrive e Microsoft Teams](atp-for-spo-odb-and-teams.md) e la protezione dei documenti sicuri non hanno dipendenze dai criteri collegamenti sicuri. [](safe-docs.md)

Se l'abbonamento include Microsoft Defender per Office 365 o se è stato acquistato Defender per Office 365 come componente aggiuntivo, impostare le configurazioni Standard o Strict seguenti.

### <a name="anti-phishing-policy-settings-in-microsoft-defender-for-office-365"></a>Impostazioni dei criteri anti-phishing in Microsoft Defender per Office 365

I clienti EOP ottengono anti-phishing di base come descritto in precedenza, ma Microsoft Defender per Office 365 include più funzionalità e controllo per prevenire, rilevare e correggere gli attacchi. Per creare e configurare questi criteri, vedere [Configurare i criteri anti-phishing in Defender per Office 365.](configure-atp-anti-phishing-policies.md)

#### <a name="impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Impostazioni di rappresentazione nei criteri anti-phishing in Microsoft Defender per Office 365

Per ulteriori informazioni su queste impostazioni, vedere Impostazioni di rappresentazione [nei criteri anti-phishing in Microsoft Defender per Office 365.](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) Per configurare queste impostazioni, vedere [Configurare i criteri anti-phishing in Defender per Office 365.](configure-atp-anti-phishing-policies.md)

****

|Nome caratteristica di sicurezza|Predefiniti|Standard|Strict|Commento|
|---|:---:|:---:|:---:|---|
|Utenti protetti: **aggiungere utenti da proteggere** <p> _EnableTargetedUserProtection_ <p> _TargetedUsersToProtect_|Off <p> `$false` <p> nessuno|Attivato <p> `$true` <p> \<list of users\>|Attivato <p> `$true` <p> \<list of users\>|A seconda dell'organizzazione, è consigliabile aggiungere utenti (mittenti dei messaggi) in ruoli chiave. Internamente, i mittenti protetti potrebbero essere il CEO, il CFO e altri responsabili senior. Esternamente, i mittenti protetti possono includere membri del consiglio o il consiglio di amministrazione.|
|Domini protetti: **includi automaticamente i domini di cui sono proprietario** <p> _EnableOrganizationDomainsProtection_|Disattivato <p> `$false`|Attivato <p> `$true`|Attivato <p> `$true`||
|Domini protetti: **includere domini personalizzati** <p> _EnableTargetedDomainsProtection_ <p> _TargetedDomainsToProtect_|Off <p> `$false` <p> nessuno|Attivato <p> `$true` <p> \<list of domains\>|Attivato <p> `$true` <p> \<list of domains\>|A seconda dell'organizzazione, è consigliabile aggiungere domini (domini mittente) di cui non si è proprietari, ma con cui si interagisce frequentemente.|
|Utenti protetti: **se la posta elettronica viene inviata da un utente rappresentato** <p> _TargetedUserProtectionAction_|**Non applicare alcuna azione** <p> `NoAction`|**Mettere in quarantena il messaggio** <p> `Quarantine`|**Mettere in quarantena il messaggio** <p> `Quarantine`||
|Domini protetti: **se la posta elettronica viene inviata da un dominio rappresentato** <p> _TargetedDomainProtectionAction_|**Non applicare alcuna azione** <p> `NoAction`|**Mettere in quarantena il messaggio** <p> `Quarantine`|**Mettere in quarantena il messaggio** <p> `Quarantine`||
|**Mostra suggerimento per gli utenti rappresentati** <p> _EnableSimilarUsersSafetyTips_|Disattivato <p> `$false`|Attivato <p> `$true`|Attivato <p> `$true`||
|**Mostra suggerimento per i domini rappresentati** <p> _EnableSimilarDomainsSafetyTips_|Disattivato <p> `$false`|Attivato <p> `$true`|Attivato <p> `$true`||
|**Mostra suggerimento per caratteri insoliti** <p> _EnableUnusualCharactersSafetyTips_|Disattivato <p> `$false`|Attivato <p> `$true`|Attivato <p> `$true`||
|**Abilitare l'intelligence per le cassette postali?** <p> _EnableMailboxIntelligence_|Attivato <p> `$true`|Attivato <p> `$true`|Attivato <p> `$true`||
|**Abilitare la protezione della rappresentazione basata sull'intelligence delle cassette postali?** <p> _EnableMailboxIntelligenceProtection_|Disattivato <p> `$false`|Attivato <p> `$true`|Attivato <p> `$true`||
|**Se la posta elettronica viene inviata da un utente rappresentato protetto dall'intelligence della cassetta postale** <p> _MailboxIntelligenceProtectionAction_|**Non applicare alcuna azione** <p> `NoAction`|**Spostare il messaggio nelle cartelle Posta indesiderata dei destinatari** <p> `MoveToJmf`|**Mettere in quarantena il messaggio** <p> `Quarantine`||
|**Mittenti attendibili** <p> _ExcludedSenders_|Nessuno|Nessuno|Nessuno|A seconda dell'organizzazione, è consigliabile aggiungere utenti che vengono erroneamente contrassegnati come phishing a causa solo della rappresentazione e non di altri filtri.|
|**Domini attendibili** <p> _ExcludedDomains_|Nessuno|Nessuno|Nessuno|A seconda dell'organizzazione, è consigliabile aggiungere domini che vengono erroneamente contrassegnati come phishing a causa solo della rappresentazione e non di altri filtri.|
|

#### <a name="spoof-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Impostazioni di spoofing nei criteri anti-phishing in Microsoft Defender per Office 365

Si noti che si tratta delle stesse impostazioni disponibili nelle impostazioni dei criteri di protezione da posta [indesiderata in EOP.](#eop-anti-spam-policy-settings)

****

|Nome caratteristica di sicurezza|Predefiniti|Standard|Strict|Commento|
|---|---|---|---|---|
|**Abilitare la protezione anti-spoofing** <p> _EnableSpoofIntelligence_|Attivato <p> `$true`|Attivato <p> `$true`|Attivato <p> `$true`||
|**Abilita mittente non autenticato** <p> _EnableUnauthenticatedSender_|Attivato <p> `$true`|Attivato <p> `$true`|Attivato <p> `$true`|Aggiunge un punto interrogativo (?) alla foto del mittente in Outlook per mittenti falsificati non identificati. Per ulteriori informazioni, vedere [Impostazioni di spoofing nei criteri anti-phishing.](set-up-anti-phishing-policies.md)|
|**Se la posta elettronica viene inviata da un utente a cui non è consentito effettuare lo spoofing del dominio** <p> _AuthenticationFailAction_|**Spostare il messaggio nelle cartelle Posta indesiderata dei destinatari** <p> `MoveToJmf`|**Spostare il messaggio nelle cartelle Posta indesiderata dei destinatari** <p> `MoveToJmf`|**Mettere in quarantena il messaggio** <p> `Quarantine`|Questa impostazione si applica ai mittenti bloccati in [spoof intelligence.](learn-about-spoof-intelligence.md)|
|

#### <a name="advanced-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Impostazioni avanzate nei criteri anti-phishing in Microsoft Defender per Office 365

Per ulteriori informazioni su questa impostazione, vedere [Soglie di phishing avanzate nei criteri anti-phishing in Microsoft Defender per Office 365.](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365) Per configurare questa impostazione, vedere [Configurare i criteri anti-phishing in Defender per Office 365.](configure-atp-anti-phishing-policies.md)

****

|Nome caratteristica di sicurezza|Predefiniti|Standard|Strict|Commento|
|---|:---:|:---:|:---:|---|
|**Soglie di phishing avanzate** <p> _PhishThresholdLevel_|**1 - Standard** <p> `1`|**2 - Aggressivo** <p> `2`|**3 - Più aggressivo** <p> `3`||
|

### <a name="safe-links-settings"></a>Impostazioni collegamenti sicuri

Collegamenti sicuri in Defender per Office 365 include impostazioni globali che si applicano a tutti gli utenti inclusi nei criteri collegamenti sicuri attivi e impostazioni specifiche per ogni criterio collegamenti sicuri. Per altre informazioni, vedere [Collegamenti sicuri in Defender per Office 365.](atp-safe-links.md)

#### <a name="global-settings-for-safe-links"></a>Impostazioni globali per i collegamenti sicuri

Per configurare queste impostazioni, vedere [Configurare le impostazioni globali per i collegamenti sicuri in Defender per Office 365.](configure-global-settings-for-safe-links.md)

In PowerShell, si utilizza il cmdlet [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365) per queste impostazioni.

****

|Nome caratteristica di sicurezza|Predefiniti|Standard|Strict|Commento|
|---|:---:|:---:|:---:|---|
|**Usare collegamenti sicuri in: Applicazioni di Office 365** <p> _EnableSafeLinksForO365Clients_|Attivato <p> `$true`|Attivato <p> `$true`|Attivato <p> `$true`|Usare collegamenti sicuri nelle app desktop e mobili di Office 365 supportate (iOS e Android). Per altre informazioni, vedere [Impostazioni dei collegamenti sicuri per le app di Office 365.](atp-safe-links.md#safe-links-settings-for-office-365-apps)|
|**Non tenere traccia quando gli utenti fanno clic su Collegamenti sicuri** <p> _TrackClicks_|Attivato <p> `$false`|Disattivato <p> `$true`|Off <p> `$true`|La disattivazione di questa impostazione _(impostando TrackClicks su_ ) tiene traccia dei clic degli `$true` utenti nelle app di Office 365 supportate.|
|**Non consentire agli utenti di fare clic su Collegamenti sicuri all'URL originale** <p> _AllowClickThrough_|Attivato <p> `$false`|Attivato <p> `$false`|Attivato <p> `$false`|L'attivazione di questa impostazione (impostando _AllowClickThrough_ su ) impedisce di passare `$false` all'URL originale nelle app di Office 365 supportate.|
|

#### <a name="safe-links-policy-settings"></a>Impostazioni dei criteri collegamenti sicuri

Per configurare queste impostazioni, vedere [Configurare i criteri collegamenti sicuri in Microsoft Defender per Office 365.](set-up-atp-safe-links-policies.md)

In PowerShell, si utilizzano i cmdlet [New-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safelinkspolicy) e [Set-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy) per queste impostazioni.

> [!NOTE]
> Come descritto in precedenza, non esiste alcun criterio collegamenti sicuri predefinito. I valori nella colonna Default sono i valori predefiniti nei nuovi criteri collegamenti sicuri creati.

****

|Nome caratteristica di sicurezza|Predefiniti|Standard|Strict|Commento|
|---|:---:|:---:|:---:|---|
|**Selezionare l'azione per URL sconosciuti potenzialmente dannosi nei messaggi** <p> _IsEnabled_|Disattivato <p> `$false`|Attivato <p> `$true`|Attivato <p> `$true`||
|**Selezionare l'azione per URL sconosciuti o potenzialmente dannosi in Microsoft Teams** <p> _EnableSafeLinksForTeams_|Disattivato <p> `$false`|Attivato <p> `$true`|Attivato <p> `$true`||
|**Applicare l'analisi degli URL in tempo reale per i collegamenti sospetti e i collegamenti che puntano ai file** <p> _ScanUrls_|Disattivato <p> `$false`|Attivato <p> `$true`|Attivato <p> `$true`||
|**Attendere il completamento dell'analisi degli URL prima di recapitare il messaggio** <p> _DeliverMessageAfterScan_|Disattivato <p> `$false`|Attivato <p> `$true`|Attivato <p> `$true`||
|**Applicare collegamenti sicuri ai messaggi di posta elettronica inviati all'interno dell'organizzazione** <p> _EnableForInternalSenders_|Disattivato <p> `$false`|Attivato <p> `$true`|Attivato <p> `$true`||
|**Non tenere traccia dei clic degli utenti** <p> _DoNotTrackUserClicks_|Off <p> `$false`|Off <p> `$false`|Off <p> `$false`|La disattivazione di questa impostazione _(impostando DoNotTrackUserClicks su_ ) tiene `$false` traccia dei clic degli utenti.|
|**Non consentire agli utenti di passare all'URL originale** <p> _DoNotAllowClickThrough_|Disattivato <p> `$false`|Attivato <p> `$true`|Attivato <p> `$true`|L'attivazione di questa impostazione (impostando _DoNotAllowClickThrough su_ ) impedisce di passare `$true` all'URL originale.|
|

### <a name="safe-attachments-settings"></a>Impostazioni allegati sicuri

Allegati sicuri in Microsoft Defender per Office 365 include impostazioni globali che non hanno alcuna relazione con i criteri allegati sicuri e impostazioni specifiche per ogni criterio collegamenti sicuri. Per altre informazioni, vedere [Allegati sicuri in Defender per Office 365.](atp-safe-attachments.md)

#### <a name="global-settings-for-safe-attachments"></a>Impostazioni globali per allegati sicuri

Per configurare queste impostazioni, vedere Attivare allegati sicuri per [SharePoint, OneDrive e Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md) e Documenti sicuri [in Microsoft 365 E5.](safe-docs.md)

In PowerShell, si utilizza il cmdlet [Set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365) per queste impostazioni.

****

|Nome caratteristica di sicurezza|Predefiniti|Standard|Strict|Commento|
|---|:---:|:---:|:---:|---|
|**Per altre informazioni, vedere Attivare Microsoft Defender per Office 365 per SharePoint, OneDrive e Microsoft Teams.** <p> _EnableATPForSPOTeamsODB_|Attivato <p> `$true`|Attivato <p> `$true`||
|**Attivare Documenti sicuri per i client di Office** <p> _EnableSafeDocs_|Attivato <p> `$true`|Attivato <p> `$true`|Questa impostazione è disponibile solo con le licenze Di sicurezza di Microsoft 365 E5 o Microsoft 365 E5. Per altre informazioni, vedere [Documenti sicuri in Microsoft Defender per Office 365.](safe-docs.md)|
|**Consentire agli utenti di fare clic su Visualizzazione protetta anche se Documenti sicuri ha identificato il file come dannoso** <p> _AllowSafeDocsOpen_|Off <p> `$false`|Off <p> `$false`|Questa impostazione è correlata a Documenti sicuri.|
|

#### <a name="safe-attachments-policy-settings"></a>Impostazioni dei criteri allegati sicuri

Per configurare queste impostazioni, vedere [Configurare i criteri allegati sicuri in Defender per Office 365.](set-up-atp-safe-attachments-policies.md)

In PowerShell, si utilizzano i cmdlet [New-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentpolicy) e [Set-SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy) per queste impostazioni.

> [!NOTE]
> Come descritto in precedenza, non esiste un criterio predefinito per gli allegati sicuri. I valori nella colonna Default sono i valori predefiniti nei nuovi criteri allegati sicuri creati.

****

|Nome caratteristica di sicurezza|Predefiniti|Standard|Strict|Commento|
|---|:---:|:---:|:---:|---|
|**Risposta malware sconosciuto allegati sicuri** <p> _Azione_|Blocca <p> `Block`|Blocca <p> `Block`|Blocca <p> `Block`||
|**Reindirizzare l'allegato al rilevamento** : **Abilita reindirizzamento** <p> _Reindirizza_ <p> _RedirectAddress_|Disattivato e nessun indirizzo di posta elettronica specificato. <p> `$true` <p> nessuno|On e specificare un indirizzo di posta elettronica. <p> `$true` <p> un indirizzo di posta elettronica|On e specificare un indirizzo di posta elettronica. <p> `$true` <p> un indirizzo di posta elettronica|Reindirizzare i messaggi a un amministratore della sicurezza per la revisione.|
|**Applicare la selezione precedente se si verifica il timeout o l'errore dell'analisi antimalware per gli allegati.** <p> _ActionOnError_|Attivato <p> `$true`|Attivato <p> `$true`|Attivato <p> `$true`||
|

## <a name="related-articles"></a>Articoli correlati

- Si cercano le procedure consigliate per le regole del flusso di **posta di Exchange (note anche come regole di trasporto)?** Vedere [Procedure consigliate per la configurazione delle regole del flusso di posta in Exchange Online.](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/configuration-best-practices)

- Gli amministratori e gli utenti possono inviare falsi positivi (buona posta elettronica contrassegnata come non buona) e falsi negativi (posta elettronica non consentita) a Microsoft per l'analisi. Per altre informazioni, vedere [Segnalazione di messaggi e file a Microsoft](report-junk-email-messages-to-microsoft.md).

- Usare questi collegamenti per informazioni su come **configurare** il servizio [EOP](set-up-your-eop-service.md)e **configurare** [Microsoft Defender per Office 365.](office-365-atp.md) Non dimenticare le indicazioni utili in "[Protezione dalle minacce in Office 365".](protect-against-threats.md)

- Le linee di base della sicurezza per **Windows** sono disponibili qui: Dove è possibile ottenere le linee di base della [sicurezza?](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines#where-can-i-get-the-security-baselines) per le opzioni degli oggetti Criteri di gruppo/locali e Usare le linee di base della sicurezza per configurare i dispositivi [Windows 10 in Intune](https://docs.microsoft.com/intune/protect/security-baselines) per la sicurezza basata su Intune. Infine, un confronto tra le linee di base della sicurezza di Microsoft Defender per Endpoint e Microsoft Intune è disponibile in Confronto tra Microsoft Defender per Endpoint e le linee di base della sicurezza [di Windows Intune.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-machines-security-baseline#compare-the-microsoft-defender-atp-and-the-windows-intune-security-baselines)
