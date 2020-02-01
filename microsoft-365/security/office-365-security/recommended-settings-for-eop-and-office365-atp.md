---
title: Consigli di Microsoft per le impostazioni di sicurezza ATP di EOP e Office 365, suggerimenti, Sender Policy Framework, Reporting e conformità dei messaggi basati su dominio, DomainKeys identificata, procedure, modalità di funzionamento, linee di base per la sicurezza, linee di base per EOP, linee di base per ATP, Setup ATP, Setup EOP, Configure ATP, Configure EOP, Security Configuration
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
ms.openlocfilehash: fd2b1fdbb0356cfc2cea080f15bf696d8073fc10
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598643"
---
# <a name="recommended-settings-for-eop-and-office-365-atp-security"></a>Impostazioni consigliate per la sicurezza ATP di EOP e Office 365

**Exchange Online Protection (EOP)** è il fulcro della sicurezza per le sottoscrizioni di Office 365 e consente ai messaggi di posta elettronica dannosi di raggiungere le cassette postali dei dipendenti. Tuttavia, con attacchi nuovi e sofisticati che emergono ogni giorno, sono spesso necessarie protezioni migliorate. **Office 365 Advanced Threat Protection (ATP)** ATP piano 1 o ATP piano 2 contengono funzionalità aggiuntive che forniscono agli amministratori più livelli di sicurezza, controllo ed indagini.

Anche se si autorizza gli amministratori della sicurezza a personalizzare le impostazioni di sicurezza, esistono due livelli di sicurezza in EOP e Office 365 ATP che è consigliabile: **standard** e **strict**. L'ambiente e i bisogni di ogni cliente sono diversi, ma riteniamo che questi livelli di configurazioni del filtro della posta consentano di evitare che la posta indesiderata raggiunga la posta in arrivo dei dipendenti nella maggior parte delle situazioni.

> [!IMPORTANT]
> La configurazione della posta indesiderata deve essere abilitata sulla cassetta postale per consentire il corretto funzionamento del filtro. Questo è abilitato per impostazione predefinita, ma dovrebbe essere controllato se il filtro non sembra funzionare. Per ulteriori informazioni, vedere [Set-MailboxJunkEmailConfiguration](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-mailboxjunkemailconfiguration) . 

In questo argomento vengono descritte le impostazioni consigliate da Microsoft per proteggere gli utenti di Office 365.

> [!TIP]
> È disponibile un nuovo modulo di PowerShell che può essere scaricato dall'analizzatore di configurazione di Office 365 Advanced Threat Protection recommended Configuration Analyzer (ORCA) che consente di determinare alcune di queste impostazioni. Quando viene eseguito come amministratore nel tenant, Get-ORCAReport contribuirà a generare una valutazione delle impostazioni di protezione da posta indesiderata, anti-phishing e altre informazioni di igiene dei messaggi. È possibile scaricare questo modulo all' https://www.powershellgallery.com/packages/ORCA/indirizzo.

## <a name="anti-spam-anti-malware-and-anti-phishing-protection-in-eop"></a>Protezione da posta indesiderata, anti-malware e anti-phishing in EOP

Le funzionalità di protezione da posta indesiderata, anti-malware e anti-phishing sono caratteristiche di EOP che possono essere configurate dagli amministratori. Si consiglia di eseguire le seguenti configurazioni.

### <a name="eop-anti-spam-policy-settings"></a>Impostazioni dei criteri di protezione da posta indesiderata di EOP

|Nome della funzionalità di sicurezza|Standard|Rigorosa|Comment|
|---------|---------|---------|---------|
|Azione di rilevamento della posta indesiderata|Sposta messaggio nella cartella Posta indesiderata|Metti in quarantena messaggio||
|Azione di rilevamento di posta indesiderata con elevata sicurezza|Metti in quarantena messaggio|Metti in quarantena messaggio||
|Azione di rilevamento della posta elettronica di phishing|Metti in quarantena messaggio|Metti in quarantena messaggio||
|Azione di rilevamento della posta elettronica phishing con elevata sicurezza|Metti in quarantena messaggio|Metti in quarantena messaggio||
|Azione di rilevamento della posta elettronica in blocco|Sposta messaggio nella cartella Posta indesiderata|Metti in quarantena messaggio||
|Impostare la soglia di posta elettronica in blocco su|6 |4 |Il valore predefinito è attualmente 7, ma è consigliabile modificarlo su 6. Per ulteriori informazioni, vedere [valori dei livelli di reclamo in blocco](bulk-complaint-level-values.md).|
|Periodo di conservazione della quarantena|30 giorni|30 giorni||
|Suggerimenti per la sicurezza|Attivato|Attivato||
|Mittenti consentiti|Nessuna|Nessuna||
|Domini di mittenti consentiti|Nessuna|Nessuna|Non è necessario aggiungere domini proprietari (noti anche come _domini accettati_) all'elenco dei mittenti consentiti. In effetti, è considerato un rischio elevato poiché crea opportunità per gli attori cattivi di inviare messaggi di posta elettronica che altrimenti verrebbero filtrati. Utilizzare l' [Intelligence spoof](learn-about-spoof-intelligence.md) nel centro sicurezza & Compliance nella pagina impostazioni di protezione da **posta indesiderata** per esaminare tutti i mittenti che eseguono lo spoofing dei domini che fanno parte dell'organizzazione o lo spoofing di domini esterni.|
|Mittenti bloccati|Nessuna|Nessuna||
|Domini mittenti bloccati|Nessuna|Nessuna||
|Frequenza della notifica di posta indesiderata dell'utente finale|Abilitato|Abilitato|3 giorni|
|Spurgo automatico di zero ore|Attivato|Attivato|Sia per la posta indesiderata che per phishing ZAP|
|MarkAsSpamBulkMail|Attivato|Attivato|Questa impostazione è disponibile solo in PowerShell|

Nei criteri di protezione da posta indesiderata sono presenti diversi altri parametri denominati Advanced Spam Filter (ASF) in fase di divenire obsoleto. Altre informazioni sulle sequenze temporali per l'ammortamento di queste caratteristiche verranno comunicate al di fuori di questo argomento.
 
 Si consiglia di disattivare **queste impostazioni per i livelli** standard e rigorosi:

|Nome della funzionalità di sicurezza|Commenti|
|---------|---------|
|IncreaseScoreWithImageLinks||
|IncreaseScoreWithNumericIps||
|IncreaseScoreWithRedirectToOtherPort||
|IncreaseScoreWithBizOrInfoUrls||
|MarkAsSpamEmptyMessages||
|MarkAsSpamJavaScriptInHtml||
|MarkAsSpamFramesInHtml||
|MarkAsSpamObjectTagsInHtml||
|MarkAsSpamEmbedTagsInHtml||
|MarkAsSpamFormTagsInHtml||
|MarkAsSpamWebBugsInHtml||
|MarkAsSpamSensitiveWordList||
|MarkAsSpamFromAddressAuthFail||
|MarkAsSpamNdrBackscatter||
|MarkAsSpamSpfRecordHardFail||

#### <a name="eop-outbound-spam-filter-policy-settings"></a>Impostazioni del filtro per la posta indesiderata in uscita EOP

|Nome della funzionalità di sicurezza|Standard|Rigorosa|Comment|
|---------|---------|---------|---------|
|Limiti per i destinatari dei criteri di posta indesiderata in uscita-limite orario esterno|500|400||
|Limiti per i destinatari dei criteri di posta indesiderata in uscita-limite orario interno|1000|800||
|Limiti dei destinatari dei criteri di posta indesiderata in uscita-limite giornaliero|1000|800||
|Azione quando un utente supera i limiti|Impedire all'utente di inviare messaggi di posta elettronica|Impedire all'utente di inviare messaggi di posta elettronica||

### <a name="eop-anti-malware-policy-settings"></a>Impostazioni dei criteri anti-malware di EOP

|Nome della funzionalità di sicurezza|Standard|Rigorosa|Comment|
|---------|---------|---------|---------|
|Risposta di rilevamento malware|No|No|Se il malware viene rilevato in un allegato di posta elettronica, il messaggio verrà messo in quarantena e può essere rilasciato solo da un amministratore.|
|"Filtro tipo di allegato comune" per il blocco dei tipi di file sospetti|Attivato|Attivato||
|Malware zero-hour auto Purge|Attivato|Attivato||
|Notifica ai mittenti interni del messaggio non recapitato|Disattivato|Disattivato||
|Notifica ai mittenti esterni del messaggio non recapitato|Disattivato|Disattivato||

### <a name="eop-anti-phishing-policy-settings"></a>Impostazioni dei criteri di anti-phishing di EOP

|Nome della funzionalità di sicurezza|Standard|Rigorosa|Comment|
|---------|---------|---------|---------|
|Abilitare la protezione anti-spoofing|Attivato|Attivato||
|Abilitazione del mittente non autenticato (tagging)|Attivato|Attivato||
|Se il messaggio di posta elettronica viene inviato da un utente che non ha il diritto di falsificare il dominio|Spostare il messaggio nelle cartelle di posta indesiderata dei destinatari|Mettere in quarantena il messaggio||

## <a name="office-365-advanced-threat-protection-security"></a>Protezione avanzata dalle minacce di Office 365

Ulteriori vantaggi per la sicurezza sono disponibili con una sottoscrizione di Office 365 Advanced Threat Protection (ATP). Per le notizie e le informazioni più recenti, è possibile visualizzare le [novità di Office 365 ATP](whats-new-in-office-365-atp.md).

Office 365 ATP include i criteri per i collegamenti sicuri e gli allegati sicuri per evitare che la posta elettronica con allegati potenzialmente dannosi venga recapitata e per impedire agli utenti di fare clic su URL potenzialmente non sicuri.

> [!IMPORTANT]
> L'anti-phishing avanzato è uno dei vantaggi offerti da un abbonamento ATP di Office 365. Anche se è abilitato per impostazione predefinita, è ***necessario*** configurare almeno un criterio anti-phishing prima che possa iniziare a filtrare la posta. L'oblio di configurare i criteri di anti-phishing potrebbe espongono gli utenti a messaggi di posta elettronica rischiosi. Assicurarsi di configurare i criteri di anti-phishing dopo l'aggiunta di una sottoscrizione di Office 365 ATP.

Se è stata aggiunta una sottoscrizione di Office 365 ATP all'EOP, impostare le configurazioni seguenti.

### <a name="office-atp-anti-phishing-policy-settings"></a>Impostazioni dei criteri di anti-phishing di Office ATP

I clienti di EOP ottengono un anti-phishing di base come descritto in precedenza, ma Office 365 ATP include altre funzionalità e controlli che consentono di prevenire, rilevare e correggere gli attacchi.

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
|EnableAuthenticationSafetyTip|True|True|Questa impostazione è disponibile solo in PowerShell|
|EnableAuthenticationSoftPassSafetyTip|False|True|Questa impostazione è disponibile solo in PowerShell|
|EnableSuspiciousSafetyTip|False|True|Questa impostazione è disponibile solo in PowerShell|
|TreatSoftPassAsAuthenticated|True|False|Questa impostazione è disponibile solo in PowerShell|

|Nome della funzionalità di sicurezza delle impostazioni avanzate|Standard|Rigorosa|Comment|
|---------|---------|---------|---------|
|Soglie di phishing avanzate|2-aggressivo|3-maggiore aggressività||

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

- Inviare messaggi sospetti, la posta indesiderata, phishing o URL a Microsoft per l'analisi. Utilizzare le istruzioni relative agli **invii di amministratore** in [questo articolo](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission).

- Utilizzare questi collegamenti per informazioni su come **configurare** il [servizio EOP](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-your-eop-service)e **configurare** [Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp). (Non dimenticare di vedere le indicazioni utili in '[protezione contro le minacce in Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats)').

- Le **linee di base per la sicurezza per Windows** sono disponibili in [questa](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines#where-can-i-get-the-security-baselines) sezione per gli oggetti Criteri di gruppo/locali e per la sicurezza basata su [Intune.](https://docs.microsoft.com/intune/protect/security-baselines) Infine, è possibile trovare un confronto tra Microsoft Defender Advanced Threat Protection (ATP) e le previsioni di sicurezza di Windows [Intune.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-machines-security-baseline#compare-the-microsoft-defender-atp-and-the-windows-intune-security-baselines)
