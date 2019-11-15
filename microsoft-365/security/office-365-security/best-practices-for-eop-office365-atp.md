---
title: Procedure consigliate per le impostazioni di sicurezza ATP EOP e Office 365, consigli, Sender Policy Framework, Reporting e conformità dei messaggi basati su dominio, DomainKeys identificata, procedure, modalità di funzionamento e così via.
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 10/23/2019
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
ms.openlocfilehash: 6f9d38f7f6200083983f42d74a54163566585a90
ms.sourcegitcommit: 2c2248b03f7753d64490f2f7e56ec644a235b65a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/15/2019
ms.locfileid: "38640795"
---
# <a name="best-practices-for-eop-and-office-365-atp-security"></a>Procedure consigliate per la sicurezza ATP di EOP e Office 365

**Exchange Online Protection (EOP)** è il fulcro della sicurezza per le sottoscrizioni di Office 365 e consente ai messaggi di posta elettronica dannosi di raggiungere le cassette postali dei dipendenti. Tuttavia, con attacchi nuovi e sofisticati che emergono ogni giorno, sono spesso necessarie protezioni migliorate. **Office 365 Advanced Threat Protection (ATP)** ATP piano 1 o ATP piano 2 contengono funzionalità aggiuntive che forniscono agli amministratori più livelli di sicurezza, controllo ed indagini. 

Anche se si autorizza gli amministratori della sicurezza a personalizzare le impostazioni di sicurezza, esistono due livelli di sicurezza in EOP e Office 365 ATP che è consigliabile: **standard** e **strict**. L'ambiente e i bisogni di ogni cliente sono diversi, ma riteniamo che questi livelli di configurazioni del filtro della posta consentano di evitare che la posta indesiderata raggiunga la posta in arrivo dei dipendenti nella maggior parte delle situazioni. 

In questo argomento vengono descritte le impostazioni consigliate da Microsoft per proteggere gli utenti di Office 365.

## <a name="anti-spam-anti-malware-and-anti-phishing-protection-in-eop"></a>Protezione da posta indesiderata, anti-malware e anti-phishing in EOP
Le funzionalità di protezione da posta indesiderata, anti-malware e anti-phishing sono caratteristiche di EOP che possono essere configurate dagli amministratori. Si consiglia di eseguire le seguenti configurazioni.

### <a name="anti-spam-policy"></a>Criteri di protezione da posta indesiderata

|Nome della funzionalità di sicurezza|Standard|Rigorosa|Aggiungere commenti|
|---------|---------|---------|---------|
|Azione di rilevamento della posta indesiderata|Sposta messaggio nella cartella Posta indesiderata|Metti in quarantena messaggio||
|Azione di rilevamento di posta indesiderata con elevata sicurezza|Metti in quarantena messaggio|Metti in quarantena messaggio||
|Azione di rilevamento della posta elettronica di phishing|Metti in quarantena messaggio|Metti in quarantena messaggio||
|Azione di rilevamento della posta elettronica phishing con elevata sicurezza|Metti in quarantena messaggio|Metti in quarantena messaggio||
|Azione di rilevamento della posta elettronica in blocco|Sposta messaggio nella cartella Posta indesiderata|Metti in quarantena messaggio||
|Impostare la soglia di posta elettronica in blocco su|6|4||
|Periodo di conservazione della quarantena|30 giorni|30 giorni||
|Suggerimenti per la sicurezza|Attivato|Attivato||
|Mittenti consentiti|Nessuna|Nessuna||
|Domini di mittenti consentiti|Nessuna|Nessuna|Non è necessario aggiungere domini proprietari (noti anche come _domini accettati_) all'elenco dei mittenti consentiti. In effetti, è considerato un rischio elevato poiché crea opportunità per gli attori cattivi di inviare messaggi di posta elettronica che altrimenti verrebbero filtrati. Utilizzare l' [Intelligence spoof](learn-about-spoof-intelligence.md) nel centro sicurezza & Compliance nella pagina impostazioni di protezione da **posta indesiderata** per esaminare tutti i mittenti che eseguono lo spoofing dei domini che fanno parte dell'organizzazione o lo spoofing di domini esterni.|
|Mittenti bloccati|Nessuna|Nessuna||
|Domini mittenti bloccati|Nessuna|Nessuna||
|Frequenza della notifica di posta indesiderata dell'utente finale|Abilitato|Abilitato|3 giorni|
|Spurgo automatico di zero ore|Attivato|Attivato|Sia per la posta indesiderata che per phishing ZAP|
|MarkAsSpamBulkMail|Attivato|Attivato|Questa impostazione è disponibile solo in PowerShell|

#### <a name="outbound-spam-filter-policy"></a>Criteri di filtro della posta indesiderata in uscita

|Nome della funzionalità di sicurezza|Standard|Rigorosa|Aggiungere commenti|
|---------|---------|---------|---------|
|Limiti per i destinatari dei criteri di posta indesiderata in uscita-limite orario esterno|400|500||
|Limiti per i destinatari dei criteri di posta indesiderata in uscita-limite orario interno|800|1000||
|Limiti dei destinatari dei criteri di posta indesiderata in uscita-limite giornaliero|800|1000||
|Azione quando un utente supera i limiti|Impedire all'utente di inviare messaggi di posta elettronica|Impedire all'utente di inviare messaggi di posta elettronica||

### <a name="anti-malware-policy"></a>Criteri anti-malware

|Nome della funzionalità di sicurezza|Standard|Rigorosa|Aggiungere commenti|
|---------|---------|---------|---------|
|Risposta di rilevamento malware|No|No|Se il malware viene rilevato in un allegato di posta elettronica, il messaggio verrà messo in quarantena e può essere rilasciato solo da un amministratore.|
|"Filtro tipo di allegato comune" per il blocco dei tipi di file sospetti|Attivato|Attivato||
|Malware zero-hour auto Purge|Attivato|Attivato||
|Notifica ai mittenti interni del messaggio non recapitato|Disattivato|Disattivato||
|Notifica ai mittenti esterni del messaggio non recapitato|Disattivato|Disattivato||

### <a name="anti-phishing-policy"></a>Criteri di anti-phishing

|Nome della funzionalità di sicurezza|Standard|Rigorosa|Aggiungere commenti|
|---------|---------|---------|---------|
|Abilitare la protezione antispoofing|Attivato|Attivato||
|Abilitazione del mittente non autenticato (tagging)|Attivato|Attivato||
|Se il messaggio di posta elettronica viene inviato da un utente che non ha il diritto di falsificare il dominio|Spostare il messaggio nelle cartelle di posta indesiderata dei destinatari|Mettere in quarantena il messaggio||

## <a name="office-365-advanced-threat-protection-atp-security"></a>Sicurezza di Office 365 Advanced Threat Protection (ATP)
Ulteriori vantaggi per la sicurezza sono disponibili con una sottoscrizione di Office 365 Advanced Threat Protection. Per le notizie e le informazioni più recenti, è possibile visualizzare le [novità di Office 365 ATP](whats-new-in-office-365-atp.md). 

Office 365 ATP include i criteri per i collegamenti sicuri e gli allegati sicuri per evitare che la posta elettronica con allegati potenzialmente dannosi venga recapitata e per impedire agli utenti di fare clic su URL potenzialmente non sicuri.

> [!IMPORTANT]
> L'anti-phishing avanzato è uno dei vantaggi offerti da un abbonamento ATP di Office 365. Abilitata per impostazione predefinita, l'anti-phishing ***deve*** essere configurato utilizzando i criteri prima di iniziare a filtrare la posta. L'oblio di configurare i criteri di anti-phishing potrebbe espongono gli utenti a messaggi di posta elettronica rischiosi. Assicurarsi di configurare i criteri di anti-phishing dopo l'aggiunta di una sottoscrizione di Office 365 ATP.

Se è stata aggiunta una sottoscrizione di Office 365 ATP all'EOP, impostare le configurazioni seguenti.

### <a name="office-atp-anti-phishing-policy"></a>Criteri di anti-phishing ATP di Office
I clienti di EOP ottengono un set di criteri anti-phishing di base ma con Office 365 ATP, gli amministratori ottengono altre caratteristiche e controlli per prevenire, rilevare e remidiare gli attacchi.

|Nome della funzionalità di sicurezza della rappresentazione|Standard|Rigorosa|Aggiungere commenti|
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

|Nome della funzionalità di sicurezza spoof|Standard|Rigorosa|Aggiungere commenti|
|---------|---------|---------|---------|
|Abilitare la protezione antispoofing|Attivato|Attivato||
|Abilitazione del mittente non autenticato (tagging)|Attivato|Attivato||
|Se il messaggio di posta elettronica viene inviato da un utente che non ha il diritto di falsificare il dominio|Spostare il messaggio nelle cartelle di posta indesiderata dei destinatari|Mettere in quarantena il messaggio||
|EnableAuthenticationSafetyTip|True|True|Questa impostazione è disponibile solo in PowerShell|
|EnableAuthenticationSoftPassSafetyTip|False|True|Questa impostazione è disponibile solo in PowerShell|
|EnableSuspiciousSafetyTip|False|True|Questa impostazione è disponibile solo in PowerShell|
|TreatSoftPassAsAuthenticated|True|False|Questa impostazione è disponibile solo in PowerShell|

|Nome della funzionalità di sicurezza delle impostazioni avanzate|Standard|Rigorosa|Aggiungere commenti|
|---------|---------|---------|---------|
|Soglie di phishing avanzate|2-aggressivo|3-maggiore aggressività||

### <a name="safe-links-settings"></a>Impostazioni collegamenti attendibili

|Nome della funzionalità di sicurezza|Standard|Rigorosa|Aggiungere commenti|
|---------|---------|---------|---------|
|Usare i collegamenti sicuri di ATP nelle app di Office 365, Office per iOS e Android|Abilitato|Abilitato|Questo rientra nei criteri dei collegamenti sicuri ATP che si applicano all'intera organizzazione|
Non monitorare quando gli utenti fanno clic su collegamenti sicuri|Disattivato|Disattivato|Questo rientra nei criteri dei collegamenti sicuri ATP che si applicano all'intera organizzazione|
|Non consentire agli utenti di fare clic su collegamenti sicuri all'URL originale|Abilitato|Abilitato|Questo rientra nei criteri dei collegamenti sicuri ATP che si applicano all'intera organizzazione|
|Azione per gli URL potenzialmente dannosi sconosciuti nei messaggi|Attivato|Attivato||
|Applicazione dell'analisi degli URL in tempo reale per collegamenti e collegamenti sospetti che puntano a file|Abilitato|Abilitato||
|Attendere il completamento dell'analisi degli URL prima di recapitare il messaggio|Abilitato|Abilitato||
|Applicazione di collegamenti sicuri ai messaggi di posta elettronica inviati all'interno dell'organizzazione|Abilitato|Abilitato||

### <a name="safe-attachments"></a>Allegati sicuri

|Nome della funzionalità di sicurezza|Standard|Rigorosa|Aggiungere commenti|
|---------|---------|---------|---------|
|Attivare ATP per SharePoint, OneDrive e Microsoft Teams|Abilitato|Abilitato||
|Risposta malware per gli allegati sicuri ATP|Blocco|Blocco||
|Reindirizza l'allegato sul rilevamento|Abilitato|Abilitato|Reindirizzare l'indirizzo di posta elettronica per un amministratore della sicurezza che sa come determinare se l'allegato è un malware o meno|
|Risposta agli allegati sicuri ATP se si verifica un errore durante l'analisi di malware per gli allegati|Abilitato|Abilitato||

## <a name="miscellaneous-settings-for-eop-or-office-365-atp"></a>Impostazioni varie per EOP o Office 365 ATP

Queste impostazioni riguardano una serie di caratteristiche che non si adattano necessariamente alle categorie specifiche sopra riportate. Alcune di queste impostazioni sono esterne al centro sicurezza & conformità.

Nome della funzionalità di sicurezza|Standard|Rigorosa|Aggiungere commenti|
|---------|---------|---------|---------|
|[Configurazione di SPF in Office 365 per evitare lo spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md)|Sì|Sì||
|[Utilizzare DKIM per convalidare la posta elettronica in uscita inviata dal dominio personalizzato in Office 365](use-dkim-to-validate-outbound-email.md)|Sì|Sì||
|[Utilizzare DMARC per convalidare la posta elettronica in Office 365](use-dmarc-to-validate-email.md)|Sì|Sì|Utilizzare Action = Quarantine per standard e Action = Reject per strict.|
|Distribuire il componente aggiuntivo dei messaggi di report per migliorare la segnalazione degli utenti finali di messaggi di posta elettronica sospetti|Sì|Sì||
|Pianificare i report di malware e posta indesiderata|Sì|Sì||
|L'inoltro automatico ai domini esterni deve essere non consentito o monitorato|Sì|Sì||
|Il controllo unificato dovrebbe essere abilitato|Sì|Sì||
|Connettività IMAP alla cassetta postale|Disattivato|Disattivato||
|Connettività POP alla cassetta postale|Disattivato|Disattivato||
|Invio con autenticazione SMTP alla cassetta postale|Disattivato|Disattivato||
|Connettività EWS alla cassetta postale|Disattivato|Disattivato||
|Connettività di PowerShell|Disattivato|Disattivato||
|Utilizzare l'intelligence spoof per i mittenti whitelist quando possibile|Sì|Sì||
|Blocco Edge basato su directory (DBEB)|Abilitato|Abilitato|Tipo di dominio = autorevole|
|[Configurare l'autenticazione a più fattori per tutti gli account di amministrazione](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication)|Abilitato|Abilitato||
