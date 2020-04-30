---
title: Consigli di Microsoft per le impostazioni di sicurezza di EOP e Office 365 ATP, consigli, Sender Policy Framework, Reporting e conformità dei messaggi basati su dominio, DomainKeys identificata, procedure, modalità di funzionamento, linee di base per la sicurezza, linee di base per EOP, linee di base per ATP, Setup ATP, Setup EOP, Configure ATP, Configure EOP, Security Configuration
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.date: 12/12/2019
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
description: Quali sono le procedure consigliate per le impostazioni di sicurezza di Exchange Online Protection (EOP) e Advanced Threat Protection (ATP)? Quali sono le raccomandazioni aggiornate per la protezione standard? Che cosa dovrebbe essere utilizzato se si desidera essere più severi? Quali sono gli extra che si ottengono se si utilizza anche Advanced Threat Protection (ATP)?
ms.openlocfilehash: a88d58db68816cd6aeb9173c36b964f3f97653db
ms.sourcegitcommit: f5cecd77e63ae8b47743d4f6dc3135f5decaf28b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/30/2020
ms.locfileid: "43949226"
---
# <a name="recommended-settings-for-eop-and-office-365-atp-security"></a>Impostazioni consigliate per la sicurezza ATP di EOP e Office 365

**Exchange Online Protection (EOP)** è il fulcro della sicurezza per le sottoscrizioni di Microsoft 365 e consente di evitare che i messaggi di posta elettronica dannosi raggiungano la posta in arrivo del dipendente. Tuttavia, con attacchi nuovi e sofisticati che emergono ogni giorno, sono spesso necessarie protezioni migliorate. **Office 365 Advanced Threat Protection (ATP)** ATP piano 1 o ATP piano 2 contengono funzionalità aggiuntive che forniscono agli amministratori più livelli di sicurezza, controllo ed indagini.

Anche se si autorizza gli amministratori della sicurezza a personalizzare le impostazioni di sicurezza, esistono due livelli di sicurezza in EOP e Office 365 ATP che è consigliabile: **standard** e **strict**. L'ambiente e i bisogni di ogni cliente sono diversi, ma riteniamo che questi livelli di configurazioni del filtro della posta consentano di evitare che la posta indesiderata raggiunga la posta in arrivo dei dipendenti nella maggior parte delle situazioni.

> [!IMPORTANT]
> La regola di posta indesiderata deve essere abilitata su una cassetta postale per consentire il corretto funzionamento del filtro. È abilitata per impostazione predefinita, ma è consigliabile verificarla se il filtro non sembra funzionare. Per altre informazioni, vedere [Configurare le impostazioni della posta indesiderata nelle cassette postali di Exchange Online in Office 365](configure-junk-email-settings-on-exo-mailboxes.md).

In questo argomento vengono descritte le impostazioni consigliate da Microsoft per aiutare a proteggere gli utenti.

> [!TIP]
> È disponibile un nuovo modulo di PowerShell che può essere scaricato dall'analizzatore di configurazione di Office 365 Advanced Threat Protection recommended Configuration Analyzer (ORCA) che consente di determinare alcune di queste impostazioni. Quando viene eseguito come amministratore nel tenant, Get-ORCAReport contribuirà a generare una valutazione delle impostazioni di protezione da posta indesiderata, anti-phishing e altre informazioni di igiene dei messaggi. È possibile scaricare questo modulo all' https://www.powershellgallery.com/packages/ORCA/indirizzo.

## <a name="anti-spam-anti-malware-and-anti-phishing-protection-in-eop"></a>Protezione da posta indesiderata, anti-malware e anti-phishing in EOP

Le funzionalità di protezione da posta indesiderata, anti-malware e anti-phishing sono caratteristiche di EOP che possono essere configurate dagli amministratori. Si consiglia di eseguire le seguenti configurazioni.

### <a name="eop-anti-spam-policy-settings"></a>Impostazioni dei criteri di protezione da posta indesiderata di EOP

Per creare e configurare criteri di protezione dalla posta indesiderata, vedere [configurare i criteri di protezione dalla posta indesiderata in Office 365](configure-your-spam-filter-policies.md).

|Nome della funzionalità di sicurezza|Standard|Rigorosa|Comment|
|---|---|---|---|
|Azione di rilevamento della **posta indesiderata** <br/><br/> _SpamAction_|**Sposta messaggio nella cartella Posta indesiderata** <br/><br/> `MoveToJmf`|**Metti in quarantena messaggio** <br/><br/> `Quarantine`||
|Azione di rilevamento di **posta indesiderata con elevata sicurezza** <br/><br/> _HighConfidenceSpamAction_|**Metti in quarantena messaggio** <br/><br/> `Quarantine`|**Metti in quarantena messaggio** <br/><br/> `Quarantine`||
|Azione di rilevamento della **posta elettronica di phishing** <br/><br/> _PhishSpamAction_|**Metti in quarantena messaggio** <br/><br/> `Quarantine`|**Metti in quarantena messaggio** <br/><br/> `Quarantine`||
|Azione di rilevamento della **posta elettronica di phishing con elevata sicurezza** <br/><br/> _HighConfidencePhishAction_|**Metti in quarantena messaggio** <br/><br/> `Quarantine`|**Metti in quarantena messaggio** <br/><br/> `Quarantine`||
|Azione di rilevamento della **posta elettronica in blocco** <br/><br/> _BulkSpamAction_|**Sposta messaggio nella cartella Posta indesiderata** <br/><br/> `MoveToJmf`|**Metti in quarantena messaggio** <br/><br/> `Quarantine`||
|Soglia di posta elettronica in blocco <br/><br/> _BulkThreshold_|6 |4 |Il valore predefinito è attualmente 7, ma è consigliabile modificarlo su 6. Per informazioni dettagliate, vedere [bulk lamentel Level (BCL) in Office 365](bulk-complaint-level-values.md).|
|Periodo di conservazione della quarantena <br/><br/> _QuarantineRetentionPeriod_|30 giorni|30 giorni||
|**Suggerimenti per la sicurezza** <br/><br/> _InlineSafetyTipsEnabled_|Attivato <br/><br/> `$true`|Attivato <br/><br/> `$true`||
|Mittenti consentiti <br/><br/> _AllowedSenders_|Nessuna|Nessuna||
|Domini mittenti consentiti <br/><br/> _AllowedSenderDomains_|Nessuna|Nessuna|Non è necessario aggiungere domini proprietari (noti anche come _domini accettati_) all'elenco dei mittenti consentiti. In effetti, è considerato un rischio elevato poiché crea opportunità per gli attori cattivi di inviare messaggi di posta elettronica che altrimenti verrebbero filtrati. Utilizzare l' [Intelligence spoof](learn-about-spoof-intelligence.md) nel centro sicurezza & Compliance nella pagina impostazioni di protezione da **posta indesiderata** per esaminare tutti i mittenti che eseguono lo spoofing degli indirizzi di posta elettronica del mittente nei domini di posta elettronica dell'organizzazione o nello spoofing degli indirizzi di posta elettronica del mittente nei domini esterni.|
|Mittenti bloccati <br/><br/> _BlockedSenders_|Nessuna|Nessuna||
|Domini mittenti bloccati <br/><br/> _BlockedSenderDomains_|Nessuna|Nessuna||
|**Abilita le notifiche di spam all'utente finale** <br/><br/> _EnableEndUserSpamNotifications_|Abilitato <br/><br/> `$true`|Abilitato <br/><br/> `$true`||
|**Invia notifiche di spam agli utenti finali ogni (giorni)** <br/><br/> _EndUserSpamNotificationFrequency_|3 giorni|3 giorni||
|**Spam ZAP** <br/><br/> _SpamZapEnabled_|Abilitato <br/><br/> `$true`|Abilitato <br/><br/> `$true`||
|**Phishing ZAP** <br/><br/> _PhishZapEnabled_|Abilitato <br/><br/> `$true`|Abilitato <br/><br/> `$true`||
|_MarkAsSpamBulkMail_|Attivato|Attivato|Questa impostazione è disponibile solo in PowerShell.|

In criteri di protezione da posta indesiderata sono disponibili diverse altre impostazioni avanzate per il filtro di posta indesiderata. Altre informazioni sulle sequenze temporali per l'ammortamento di queste caratteristiche verranno comunicate al di fuori di questo argomento.

Si **consiglia di disattivare queste impostazioni ASF** sia per i livelli **standard** che per quelli **rigorosi** . Per ulteriori informazioni sulle impostazioni ASF, vedere [Advanced Spam Filter (ASF) Settings in Office 365](advanced-spam-filtering-asf-options.md).

|Nome della funzionalità di sicurezza|Commenti|
|----|---|
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

#### <a name="eop-outbound-spam-policy-settings"></a>Impostazioni di criteri di posta indesiderata in uscita di EOP

Per creare e configurare i criteri di posta indesiderata in uscita, vedere [Configure Outbound Spam Filtering in Office 365](configure-the-outbound-spam-policy.md).

|Nome della funzionalità di sicurezza|Standard|Rigorosa|Comment|
|---|---|---|---|
|**Numero massimo di destinatari per utente: limite orario esterno** <br/><br/> _RecipientLimitExternalPerHour_|500|400||
|**Numero massimo di destinatari per utente: limite orario interno** <br/><br/> _RecipientLimitInternalPerHour_|1000|800||
|**Numero massimo di destinatari per utente: limite giornaliero** <br/><br/> _RecipientLimitPerDay_|1000|800||
|**Azione quando un utente supera i limiti** <br/><br/> _ActionWhenThresholdReached_|**Impedire all'utente di inviare messaggi di posta elettronica** <br/><br/> `BlockUser`|**Impedire all'utente di inviare messaggi di posta elettronica** <br/><br/> `BlockUser`||

### <a name="eop-anti-malware-policy-settings"></a>Impostazioni dei criteri anti-malware di EOP

Per creare e configurare criteri anti-malware, vedere [Configure anti-malware Policies in Office 365](configure-anti-malware-policies.md).

|Nome della funzionalità di sicurezza|Standard|Rigorosa|Comment|
|---|---|---|---|
|**Si desidera inviare una notifica ai destinatari se i messaggi vengono messi in quarantena?** <br/><br/> _Azione_|No <br/><br/> _DeleteMessage_|No <br/><br/> _DeleteMessage_|Se il malware viene rilevato in un allegato di posta elettronica, il messaggio viene messo in quarantena e può essere rilasciato solo da un amministratore.|
|**Filtro di tipi di allegati comuni** <br/><br/> _EnableFileFilter_|Attivato <br/><br/> `$true`|Attivato <br/><br/> `$true`|Questa impostazione mette in quarantena i messaggi che contengono allegati eseguibili in base al tipo di file, indipendentemente dal contenuto degli allegati.|
|**Malware zero-hour auto Purge** <br/><br/> _ZapEnabled_|Attivato <br/><br/> `$true`|Attivato <br/><br/> `$true`||
|**Notifica ai mittenti interni** del messaggio non recapitato <br/><br/> _EnableInternalSenderNotifications_|Disattivato <br/><br/> `$false`|Disattivato <br/><br/> `$false`||
|**Notifica ai mittenti esterni** del messaggio non recapitato <br/><br/> _EnableExternalSenderNotifications_|Disattivato <br/><br/> `$false`|Disattivato <br/><br/> `$false`||

### <a name="eop-default-anti-phishing-policy-settings"></a>Impostazioni di criteri anti-phishing predefinite di EOP

Per configurare queste impostazioni, vedere [Configure anti-phishing Policies in EOP](configure-anti-phishing-policies-eop.md).

|Nome della funzionalità di sicurezza|Standard|Rigorosa|Comment|
|---|---|---|---|
|**Abilitare la protezione anti-spoofing** <br/><br/> _EnableAntispoofEnforcement_|Attivato <br/><br/> `$true`|Attivato <br/><br/> `$true`||
|**Abilitazione del mittente non autenticato** <br/><br/> _EnableUnauthenticatedSender_|Attivato <br/><br/> `$true`|Attivato <br/><br/> `$true`|Aggiunge un punto interrogativo (?) alla foto del mittente in Outlook per i mittenti non identificati falsificati. Per ulteriori informazioni, vedere [spoofing Settings in anti-phishing Policies](set-up-anti-phishing-policies.md).|
|**Se il messaggio di posta elettronica viene inviato da un utente che non ha il diritto di falsificare il dominio** <br/><br/> _AuthenticationFailAction_|**Spostare il messaggio nelle cartelle di posta indesiderata dei destinatari** <br/><br/> `MoveToJmf`|**Mettere in quarantena il messaggio** <br/><br/> `Quarantine`|Questo vale per i mittenti bloccati in [Intelligence spoof](learn-about-spoof-intelligence.md).|

## <a name="office-365-advanced-threat-protection-security"></a>Protezione avanzata dalle minacce di Office 365

Ulteriori vantaggi per la sicurezza sono disponibili con una sottoscrizione di Office 365 Advanced Threat Protection (ATP). Per le notizie e le informazioni più recenti, è possibile visualizzare le [novità di Office 365 ATP](whats-new-in-office-365-atp.md).

Office 365 ATP include i criteri per i collegamenti sicuri e gli allegati sicuri per evitare che la posta elettronica con allegati potenzialmente dannosi venga recapitata e per impedire agli utenti di fare clic su URL potenzialmente non sicuri.

> [!IMPORTANT]
> L'anti-phishing avanzato è uno dei vantaggi offerti da un abbonamento ATP di Office 365. Anche se è abilitato per impostazione predefinita, è ***necessario*** configurare almeno un criterio anti-phishing prima che possa iniziare a filtrare la posta. L'oblio di configurare i criteri di anti-phishing potrebbe espongono gli utenti a messaggi di posta elettronica rischiosi. Assicurarsi di configurare i criteri di anti-phishing dopo l'aggiunta di una sottoscrizione di Office 365 ATP.

Se è stata aggiunta una sottoscrizione di Office 365 ATP all'EOP, impostare le configurazioni seguenti.

### <a name="office-atp-anti-phishing-policy-settings"></a>Impostazioni dei criteri di anti-phishing di Office ATP

I clienti di EOP ottengono un anti-phishing di base come descritto in precedenza, ma Office 365 ATP include altre funzionalità e controlli che consentono di prevenire, rilevare e correggere gli attacchi. Per creare e configurare questi criteri, vedere [configurare i criteri di anti-phishing ATP in Office 365](configure-atp-anti-phishing-policies.md).

|Nome della funzionalità di sicurezza della rappresentazione|Standard|Rigorosa|Comment|
|---------|---------|---------|---------|
|(Modifica criteri di rappresentazione) Aggiungere gli utenti a Protect|Attivato|Attivato|Dipende dall'organizzazione, ma è consigliabile aggiungere gli utenti nei ruoli chiave. Internamente, potrebbe trattarsi del CEO, del CFO e di altri leader senior. Esternamente, questi potrebbero includere i membri del Consiglio o il Consiglio di amministrazione.|
|(Modifica criteri di rappresentazione) Includi automaticamente i domini che possiedo|Attivato|Attivato||
|(Modifica criteri di rappresentazione) Includere domini personalizzati|Attivato|Attivato|Dipende dall'organizzazione, ma è consigliabile aggiungere domini che interagiscono con la maggior parte dei quali non si è proprietari.|
|Se il messaggio di posta elettronica viene inviato da un utente rappresentato specificato|Mettere in quarantena il messaggio|Mettere in quarantena il messaggio||
|Se il messaggio di posta elettronica viene inviato da un dominio rappresentato specificato|Mettere in quarantena il messaggio|Mettere in quarantena il messaggio||
|Mostrare il suggerimento per gli utenti rappresentati|Attivato|Attivato||
|Mostrare il suggerimento per i domini rappresentati|Attivato|Attivato||
|Mostra suggerimento per i caratteri insoliti|Attivato|Attivato||
|Abilitazione dell'Intelligence delle cassette postali|Attivato|Attivato||
|Abilitare la protezione della rappresentazione basata sull'Intelligence delle cassette postali|Attivato|Attivato||
|Se il messaggio di posta elettronica viene inviato da un utente rappresentato protetto dalla funzionalità di intelligence delle cassette postali|Spostare il messaggio nelle cartelle di posta indesiderata dei destinatari|Mettere in quarantena il messaggio||
|(Modifica criteri di rappresentazione) Aggiungere mittenti e domini attendibili|Nessuna|Nessuna|Dipende dall'organizzazione, ma è consigliabile aggiungere utenti o domini che vengono contrassegnati erroneamente come phishing a causa solo della rappresentazione e non di altri filtri.|

|Nome della funzionalità di sicurezza spoof|Standard|Rigorosa|Comment|
|---------|---------|---------|---------|
|Abilitare la protezione anti-spoofing|Attivato|Attivato||
|Abilitazione del mittente non autenticato (tagging)|Attivato|Attivato||
|Se il messaggio di posta elettronica viene inviato da un utente che non ha il diritto di falsificare il dominio|Spostare il messaggio nelle cartelle di posta indesiderata dei destinatari|Mettere in quarantena il messaggio||

#### <a name="impersonation-settings-in-atp-anti-phishing-policies"></a>Impostazioni di rappresentazione nei criteri di anti-phishing ATP

|Nome della funzionalità di sicurezza|Standard|Rigorosa|Comment|
|---|---|---|---|
|Utenti protetti: **aggiungere utenti a Protect** <br/><br/> _È impostato enabletargeteduserprotection_ <br/><br/> _TargetedUsersToProtect_|Attivato <br/><br/> `$true` <br/><br/> \<elenco di utenti\>|Attivato <br/><br/> `$true` <br/><br/> \<elenco di utenti\>|Dipende dall'organizzazione, ma è consigliabile aggiungere gli utenti nei ruoli chiave. Internamente, potrebbe trattarsi del CEO, del CFO e di altri leader senior. Esternamente, questi potrebbero includere i membri del Consiglio o il Consiglio di amministrazione.|
|Domini protetti: **includono automaticamente i domini che possiedo** <br/><br/> _EnableOrganizationDomainsProtection_|Attivato <br/><br/> `$true`|Attivato <br/><br/> `$true`||
|Domini protetti: **includere domini personalizzati** <br/><br/> _EnableTargetedDomainsProtection_ <br/><br/> _TargetedDomainsToProtect_|Attivato <br/><br/> `$true` <br/><br/> \<elenco dei domini\>|Attivato <br/><br/> `$true` <br/><br/> \<elenco dei domini\>|Dipende dall'organizzazione, ma è consigliabile aggiungere domini che spesso interagiscono con quelli che non possiedono.|
|Utenti protetti: **se il messaggio di posta elettronica viene inviato da un utente rappresentato** <br/><br/> _TargetedUserProtectionAction_|**Mettere in quarantena il messaggio** <br/><br/> `Quarantine`|**Mettere in quarantena il messaggio** <br/><br/> `Quarantine`||
|Domini protetti: **se il messaggio di posta elettronica viene inviato da un dominio rappresentato** <br/><br/> _TargetedUserProtectionAction_|**Mettere in quarantena il messaggio** <br/><br/> `Quarantine`|**Mettere in quarantena il messaggio** <br/><br/> `Quarantine`||
|**Mostrare il suggerimento per gli utenti rappresentati** <br/><br/> _EnableSimilarUsersSafetyTips_|Attivato <br/><br/> `$true`|Attivato <br/><br/> `$true`||
|**Mostrare il suggerimento per i domini rappresentati** <br/><br/> _EnableSimilarDomainsSafetyTips_|Attivato <br/><br/> `$true`|Attivato <br/><br/> `$true`||
|**Mostra suggerimento per i caratteri insoliti** <br/><br/> _EnableUnusualCharactersSafetyTips_|Attivato <br/><br/> `$true`|Attivato <br/><br/> `$true`||
|**Abilitare l'intelligence delle cassette postali?** <br/><br/> _EnableMailboxIntelligence_|Attivato <br/><br/> `$true`|Attivato <br/><br/> `$true`||
|**Abilitare la protezione della rappresentazione basata sull'Intelligence delle cassette postali?** <br/><br/> _EnableMailboxIntelligenceProtection_|Attivato <br/><br/> `$true`|Attivato <br/><br/> `$true`||
|**Se il messaggio di posta elettronica viene inviato da un utente rappresentato protetto dalla funzionalità di intelligence delle cassette postali** <br/><br/> _MailboxIntelligenceProtectionAction_|**Spostare il messaggio nelle cartelle di posta indesiderata dei destinatari** <br/><br/> `MoveToJmf`|**Mettere in quarantena il messaggio** <br/><br/> `Quarantine`||
|**Mittenti attendibili** <br/><br/> _ExcludedSenders_|Nessuna|Nessuna|Dipende dall'organizzazione, ma è consigliabile aggiungere gli utenti che vengono erroneamente contrassegnati come phishing a causa solo della rappresentazione e non di altri filtri.|
|**Domini attendibili** <br/><br/> _ExcludedDomains_|Nessuna|Nessuna|Dipende dall'organizzazione, ma è consigliabile aggiungere domini che vengono erroneamente contrassegnati come phishing a causa solo della rappresentazione e non di altri filtri.|

#### <a name="spoof-settings-in-atp-anti-phishing-policies"></a>Impostazioni di spoofing nei criteri di anti-phishing ATP

Si noti che si tratta delle stesse impostazioni disponibili nelle impostazioni dei criteri di protezione [da posta indesiderata in EOP](#eop-anti-spam-policy-settings).

|Nome della funzionalità di sicurezza|Standard|Rigorosa|Comment|
|---|---|---|---|
|**Abilitare la protezione anti-spoofing** <br/><br/> _EnableAntispoofEnforcement_|Attivato <br/><br/> `$true`|Attivato <br/><br/> `$true`||
|**Abilitazione del mittente non autenticato** <br/><br/> _EnableUnauthenticatedSender_|Attivato <br/><br/> `$true`|Attivato <br/><br/> `$true`|Aggiunge un punto interrogativo (?) alla foto del mittente in Outlook per i mittenti non identificati falsificati. Per ulteriori informazioni, vedere [spoofing Settings in anti-phishing Policies](set-up-anti-phishing-policies.md).|
|**Se il messaggio di posta elettronica viene inviato da un utente che non ha il diritto di falsificare il dominio** <br/><br/> _AuthenticationFailAction_|**Spostare il messaggio nelle cartelle di posta indesiderata dei destinatari** <br/><br/> `MoveToJmf`|**Mettere in quarantena il messaggio** <br/><br/> `Quarantine`|Questo vale per i mittenti bloccati in [Intelligence spoof](learn-about-spoof-intelligence.md).|

#### <a name="advanced-settings-in-atp-anti-phishing-policies"></a>Impostazioni avanzate nei criteri di anti-phishing ATP

|Nome della funzionalità di sicurezza|Standard|Rigorosa|Comment|
|---|---|---|---|
|**Soglie di phishing avanzate** <br/><br/> _PhishThresholdLevel_|**2-aggressivo** <br/><br/> `2`|**3-maggiore aggressività** <br/><br/> `3`||

### <a name="safe-links-settings"></a>Impostazioni collegamenti attendibili

|Nome della funzionalità di sicurezza|Standard|Rigorosa|Comment|
|---------|---------|---------|---------|
|Usare i collegamenti sicuri di ATP nelle app di Office 365, Office per iOS e Android|Abilitato|Abilitato|Questo rientra nei criteri dei collegamenti sicuri ATP che si applicano all'intera organizzazione|
Non monitorare quando gli utenti fanno clic su collegamenti sicuri|Disattivato|Disattivato|Questo è per entrambi i criteri che si applicano all'intera organizzazione e tutti i criteri che si applicano a destinatari specifici|
|Non consentire agli utenti di fare clic su collegamenti sicuri all'URL originale|Abilitato|Abilitato|Questo è per i criteri che si applicano all'intera organizzazione e per tutti i criteri che si applicano a destinatari specifici|
|Azione per gli URL potenzialmente dannosi sconosciuti nei messaggi|Attivato|Attivato||
|Applicazione dell'analisi degli URL in tempo reale per collegamenti e collegamenti sospetti che puntano a file|Abilitato|Abilitato||
|Attendere il completamento dell'analisi degli URL prima di recapitare il messaggio|Abilitato|Abilitato||
|Applicazione di collegamenti sicuri ai messaggi di posta elettronica inviati all'interno dell'organizzazione|Abilitato|Abilitato||

### <a name="safe-attachments"></a>Allegati sicuri

|Nome della funzionalità di sicurezza|Standard|Rigorosa|Comment|
|---------|---------|---------|---------|
|Attivare ATP per SharePoint, OneDrive e Microsoft Teams|Abilitato|Abilitato||
|Risposta malware per gli allegati sicuri ATP|Blocco|Blocco||
|Reindirizza l'allegato sul rilevamento|Abilitato|Abilitato|Reindirizzare l'indirizzo di posta elettronica per un amministratore della sicurezza che sa come determinare se l'allegato è un malware o meno|
|Risposta agli allegati sicuri ATP se si verifica un errore durante l'analisi di malware per gli allegati|Abilitato|Abilitato||

## <a name="related-topics"></a>Argomenti correlati

- Per informazioni sulle procedure consigliate, vedere **Exchange Mail Flow/Exchange Transport Rules**? Per informazioni dettagliate, vedere [questo articolo](https://docs.microsoft.com/microsoft-365/security/office-365-security/best-practices-for-configuring-eop) .

- Gli amministratori e gli utenti possono inviare falsi positivi (buon messaggio di posta elettronica contrassegnato come cattivo) e falsi negativi (messaggi di posta elettronica non consentiti) a Microsoft per l'analisi. Per altre informazioni, vedere [Segnalazione di messaggi e file a Microsoft](report-junk-email-messages-to-microsoft.md).

- Utilizzare questi collegamenti per informazioni su come **configurare** il [servizio EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-your-eop-service)e **configurare** [Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp). (Non dimenticare di vedere le indicazioni utili in '[protezione contro le minacce in Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats)').

- Le **linee di base per la sicurezza per Windows** sono disponibili in [questa](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines#where-can-i-get-the-security-baselines) sezione per gli oggetti Criteri di gruppo/locali e per la sicurezza basata su [Intune.](https://docs.microsoft.com/intune/protect/security-baselines) Infine, è possibile trovare un confronto tra Microsoft Defender Advanced Threat Protection (ATP) e le previsioni di sicurezza di Windows [Intune.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-machines-security-baseline#compare-the-microsoft-defender-atp-and-the-windows-intune-security-baselines)
