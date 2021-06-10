---
title: Microsoft 365 Security for Business Decision Makers (BDM)
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: johmar
audience: Admin
ms.topic: tutorial
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: gli scenari di minaccia e attacco più comuni attualmente affrontati dalle organizzazioni per i Microsoft 365 e le azioni consigliate per attenuare questi rischi.
ms.openlocfilehash: 056e1e64a992f12f3bf9a4b76c29f723ac1b5f3a
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "51930174"
---
# <a name="microsoft-365-security-for-business-decision-makers-bdms"></a>Microsoft 365 Security for Business Decision Makers (BDM)

In questo articolo vengono illustrati alcuni degli scenari di minaccia e attacco più comuni attualmente affrontati dalle organizzazioni per i propri ambienti Microsoft 365 e vengono consigliate le azioni per attenuare questi rischi. Sebbene Microsoft 365 sia dotato di un'ampia gamma di funzionalità di sicurezza preconfigurati, è anche necessario che il cliente si asseri la responsabilità di proteggere le proprie identità, i dati e i dispositivi utilizzati per accedere ai servizi cloud. Questa guida è stata sviluppata da Kozeta Beam (Microsoft Cloud Security Architect) e Thiagaraj Sundararajan (Microsoft Senior Consultant).

Questo articolo è organizzato per priorità di lavoro, a partire dalla protezione degli account utilizzati per amministrare i servizi e gli asset più critici, ad esempio tenant, posta elettronica e SharePoint. Offre un modo metodico per affrontare la sicurezza e collabora con il foglio di calcolo seguente, in modo da poter tenere traccia dei progressi con le parti interessate e i team dell'organizzazione: Microsoft 365 sicurezza per i [BDM](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Microsoft-365-BDM-security-recommendations-spreadsheet.xlsx)foglio di calcolo . 

[![Foglio di calcolo suggerimenti per Microsoft 365 sicurezza BDM](../downloads/microsoft-365-bdm-security-recommendations-spreadsheet-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/Microsoft-365-BDM-security-recommendations-spreadsheet.xlsx)

Microsoft fornisce lo strumento Punteggio sicuro all'interno del tenant per analizzare automaticamente la posizione di sicurezza in base alle attività regolari, assegnare un punteggio e fornire suggerimenti per il miglioramento della sicurezza. Prima di eseguire le azioni consigliate in questo articolo, prendere nota del punteggio corrente e dei suggerimenti. Le azioni consigliate in questo articolo aumentano il punteggio. L'obiettivo non è raggiungere il punteggio massimo, ma essere consapevoli delle opportunità per proteggere l'ambiente in modo che non influisca negativamente sulla produttività degli utenti. Vedere [Microsoft Secure Score](defender/microsoft-secure-score.md).

![Seguire questa procedura per ridurre i rischi per l'azienda.](../media/security/security-for-bdms-overview.png)

Un'altra cosa prima di iniziare . . . assicurarsi di [attivare il registro di controllo](../compliance/search-the-audit-log-in-security-and-compliance.md). Questi dati saranno necessari in un secondo momento, nel caso in cui sia necessario analizzare un incidente o una violazione. 

## <a name="protect-privileged-accounts"></a>Proteggere gli account con privilegi

Come primo passaggio, è consigliabile garantire che agli account critici nell'ambiente venga assegnato un ulteriore livello di protezione, in quanto tali account dispongono di accesso e autorizzazioni per gestire e modificare i servizi e le risorse critici, che possono influire negativamente sull'intera organizzazione, se compromessi. La protezione degli account con privilegi è uno dei modi più efficaci per proteggersi da un utente malintenzionato che cerca di elevare le autorizzazioni di un account compromesso a un account amministrativo. 

|Consiglio  |E3 |E5  |
|---------|---------|---------|
|Applicare l'autenticazione a più fattori (MFA) per tutti gli account amministrativi.|![segno di spunta verde](../media/green-check-mark.png)|![segno di spunta verde](../media/green-check-mark.png)| 
|Implementare Azure Active Directory (Azure AD) Privileged Identity Management (PIM) per applicare l'accesso con privilegi just-in-time alle risorse di Azure AD e Azure. È inoltre possibile individuare chi ha accesso ed esaminare l'accesso con privilegi.|         | ![segno di spunta verde](../media/green-check-mark.png)|
|Implementare la gestione degli accessi con privilegi per gestire il controllo dell'accesso granulare sulle attività di amministrazione con privilegi in Office 365. |         | ![segno di spunta verde](../media/green-check-mark.png)|
|Configurare e utilizzare Le workstation con accesso privilegiato (PAW) per amministrare i servizi. Non utilizzare le stesse workstation per l'esplorazione di Internet e il controllo della posta elettronica non correlata all'account amministrativo.|  ![segno di spunta verde](../media/green-check-mark.png)|![segno di spunta verde](../media/green-check-mark.png) | 

Nel diagramma seguente vengono illustrate queste funzionalità.
![Funzionalità consigliate per la protezione degli account con privilegi](../media/m365-security-bdm-illustrations-privileged-accounts.png)

Suggerimenti aggiuntivi:
- Verificare che agli account sincronizzati da locale non siano assegnati ruoli di amministratore per i servizi cloud. Ciò consente di impedire a un utente malintenzionato di applicare account locali per ottenere l'accesso amministrativo ai servizi cloud. 
- Verificare che agli account di servizio non siano assegnati ruoli di amministratore. Questi account spesso non vengono monitorati e impostati con password che non scadono. Iniziare verificando che gli account dei servizi AADConnect e ADFS non siano amministratori globali per impostazione predefinita.
- Rimuovere le licenze dagli account di amministratore. A meno che non vi sia un caso di utilizzo specifico per assegnare licenze a specifici account di amministratore, rimuovere le licenze da questi account. 

## <a name="reduce-the-surface-of-attack"></a>Ridurre la superficie di attacco

L'area di messa a fuoco successiva è la riduzione della superficie di attacco. Questa operazione può essere eseguita con il minimo sforzo e impatto per gli utenti e i servizi. Riducendo la superficie di attacco, gli utenti malintenzionati hanno meno modi per lanciare un attacco contro l'organizzazione.

Di seguito vengono descritti alcuni esempi:
- Disabilitare i protocolli POP3, IMAP e SMTP. La maggior parte delle organizzazioni moderne non usa più questi protocolli precedenti. È possibile disabilitarli in modo sicuro e consentire le eccezioni solo in base alle esigenze. 
- Ridurre e mantenere il numero di amministratori globali nel tenant al minimo necessario. In questo modo si riduce direttamente l'area di attacco per tutte le applicazioni cloud. 
- Ritirare i server e le applicazioni non più utilizzati nell'ambiente. 
- Implementare un processo per la disabilitazione e l'eliminazione di account non più utilizzati. 

## <a name="protect-against-known-threats"></a>Protezione da minacce note

Le minacce note includono malware, account compromessi e phishing. Alcune protezioni contro queste minacce possono essere implementate rapidamente senza alcun impatto diretto per gli utenti, mentre altre richiedono più pianificazione e formazione degli utenti. 

|Consiglio  |E3  |E5  |
|---------|---------|---------|
|**Configurare l'autenticazione a più fattori e utilizzare i criteri di accesso condizionale consigliati, inclusi i criteri di rischio di accesso.** Microsoft consiglia e ha testato un set di criteri che funzionano insieme per proteggere tutte le app cloud, inclusi Office 365 e Microsoft 365 servizi. Vedi [Configurazioni di identità e accesso ai dispositivi.](./office-365-security/microsoft-365-policies-configurations.md) | |![segno di spunta verde](../media/green-check-mark.png)|
|**Richiedere l'autenticazione a più fattori per tutti gli utenti**. Se non si dispone delle licenze necessarie per implementare i criteri di accesso condizionale consigliati, è necessaria almeno l'autenticazione a più fattori per tutti gli utenti.|![segno di spunta verde](../media/green-check-mark.png)|![segno di spunta verde](../media/green-check-mark.png)|
|**Aumentare il livello di protezione dal malware nella posta**. L'Office 365 o Microsoft 365 include la protezione da malware, ma è possibile aumentare questa protezione bloccando gli allegati con tipi di file comunemente usati per malware.|![segno di spunta verde](../media/green-check-mark.png)|![segno di spunta verde](../media/green-check-mark.png)|
|**Proteggere la posta elettronica da attacchi di phishing mirati.** Se sono stati configurati uno o più domini personalizzati per l'ambiente Office 365 o Microsoft 365, è possibile configurare una protezione anti-phishing mirata. La protezione anti-phishing, che fa parte di Defender per Office 365, può aiutare a proteggere l'organizzazione da attacchi di phishing dannosi basati sulla rappresentazione e da altri attacchi di phishing. Se non è stato configurato un dominio personalizzato, non è necessario eseguire questa operazione.| |![segno di spunta verde](../media/green-check-mark.png)|
|**Proteggere da attacchi ransomware nella posta elettronica**. Ransomware consente di rimuovere l'accesso ai dati crittografando i file o bloccando gli schermi del computer. Tenta quindi di estorcere denaro alle vittime chiedendo "riscatto", in genere sotto forma di criptovalute come Bitcoin, in cambio di restituire l'accesso ai dati. Puoi aiutare a difenderti dal ransomware creando una o più regole del flusso di posta per bloccare le estensioni di file comunemente usate per ransomware o per avvisare gli utenti che ricevono questi allegati tramite posta elettronica.|![segno di spunta verde](../media/green-check-mark.png)|![segno di spunta verde](../media/green-check-mark.png)|
|**Bloccare le connessioni da paesi con cui non si fa business con**. Creare un criterio di accesso condizionale di Azure AD per bloccare le connessioni provenienti da questi paesi, creando in modo efficace un firewall geografico attorno al tenant.| |![segno di spunta verde](../media/green-check-mark.png)|

Nel diagramma seguente vengono illustrate queste funzionalità.
![Funzionalità consigliate per la protezione da minacce note](../media/m365-security-bdm-illustrations-known-threats.png)

## <a name="protect-against-unknown-threats"></a>Protezione da minacce sconosciute

Dopo aver aggiunto protezioni aggiuntive agli account con privilegi e aver protetto da attacchi noti, sposta l'attenzione sulla protezione da minacce sconosciute. Gli avversari più determinati e avanzati usano metodi innovativi e nuovi e sconosciuti per attaccare le organizzazioni. Con la vasta telemetria di Microsoft dei dati raccolti in più di miliardi di dispositivi, applicazioni e servizi, siamo in grado di eseguire Defender per Office 365 su Windows, Office 365 e Azure per evitare attacchi di Zero-Day, utilizzando ambienti sand box e controllando la validità prima di consentire l'accesso al contenuto. 


|Consiglio  |E3  |E5  |
|---------|---------|---------|
|**Configurare Microsoft Defender per Office 365**:<br>* Allegati sicuri<br>* Collegamenti sicuri<br>* Microsoft Defender for Endpoint per SharePoint, OneDrive e Microsoft Teams<br>* Anti-phishing in Defender per Office 365 protezione|         |![segno di spunta verde](../media/green-check-mark.png) |
|**Configurare Microsoft Defender per le funzionalità dell'endpoint**:<br>* Windows Defender Antivirus <br>* Protezione da exploit <br> * Riduzione della superficie di attacco <br> * Isolamento basato su hardware <br>* Accesso controllato alle cartelle     |         |![segno di spunta verde](../media/green-check-mark.png) |
|**Usa Microsoft Cloud App Security** per individuare le app SaaS e iniziare a usare l'analisi del comportamento e il rilevamento delle anomalie. |         |![segno di spunta verde](../media/green-check-mark.png) |

Nel diagramma seguente vengono illustrate queste funzionalità.
![Funzionalità consigliate per la protezione da minacce sconosciute](../media/m365-security-bdm-illustrations-unknown-threats.png)

Suggerimenti aggiuntivi:
- Proteggere le comunicazioni del canale partner come i messaggi di posta elettronica tramite TLS.
- Apri Teams federazione solo ai partner con cui comunichi.
- Non aggiungere domini mittente, singoli mittenti o indirizzi IP di origine all'elenco consenti, in quanto ciò consente loro di ignorare i controlli di posta indesiderata e malware. Una pratica comune con i clienti consiste nell'aggiungere i propri domini accettati o un certo numero di altri domini in cui potrebbero essere stati segnalati problemi del flusso di posta elettronica all'elenco consenti. Non aggiungere domini nell'elenco Filtro posta indesiderata e connessioni perché questa operazione potrebbe ignorare tutti i controlli della posta indesiderata. 
- Abilitare le notifiche di posta indesiderata in uscita : abilitare le notifiche di posta indesiderata in uscita a una lista di distribuzione internamente al team di supporto tecnico o di amministratore IT per segnalare se uno degli utenti interni invia messaggi di posta indesiderata esternamente. Potrebbe trattarsi di un indicatore che indica che l'account è stato compromesso.
- Disabilitare Remote PowerShell per tutti gli utenti: Remote PowerShell viene utilizzato principalmente dagli amministratori per accedere ai servizi per scopi amministrativi o per l'accesso alle API programmatiche. È consigliabile disabilitare questa opzione per gli utenti non amministratori per evitare ricognizioni, a meno che non abbia un requisito aziendale per accedervi. 
- Bloccare l'accesso Microsoft Azure portale di gestione a tutti gli utenti non amministratori. A tale scopo, è possibile creare una regola di accesso condizionale per bloccare tutti gli utenti, ad eccezione degli amministratori. 


## <a name="assume-breach"></a>Presupporre violazione

Mentre Microsoft adotta tutte le misure possibili per prevenire minacce e attacchi, ti consigliamo di lavorare sempre con la mentalità "Presupporre violazione". Anche se un utente malintenzionato è riuscito a intromettersi nell'ambiente, è necessario assicurarsi che non sia in grado di esfiltrare dati o informazioni sull'identità dall'ambiente. Per questo motivo, è consigliabile abilitare la protezione da perdite di dati sensibili, ad esempio numeri di previdenza sociale, numeri di carte di credito, informazioni personali aggiuntive e altre informazioni riservate a livello di organizzazione. 

La strategia "Presupporre violazione" richiede l'implementazione di una strategia di rete senza attendibilità, il che significa che gli utenti non sono completamente attendibili solo perché sono interni alla rete. Nell'ambito dell'autorizzazione delle operazioni che gli utenti possono eseguire, vengono invece specificati set di condizioni e, quando tali condizioni vengono soddisfatte, vengono applicati determinati controlli. Le condizioni possono includere lo stato di integrità del dispositivo, l'accesso all'applicazione, l'esecuzione delle operazioni e il rischio dell'utente. Ad esempio, un'azione di registrazione dei dispositivi deve sempre attivare l'autenticazione a più fattori per garantire che non siano stati aggiunti dispositivi rossi all'ambiente. 

Una strategia di rete zero trust richiede inoltre di sapere dove sono archiviate le informazioni e di applicare controlli appropriati per la classificazione, la protezione e la conservazione. Per proteggere in modo efficace gli asset più critici e sensibili, devi prima identificare dove si trovano e prendere l'inventario, il che può essere difficile. Successivamente, collaborare con l'organizzazione per definire una strategia di governance. La definizione di uno schema di classificazione per un'organizzazione e la configurazione di criteri, etichette e condizioni richiedono un'attenta pianificazione e preparazione. È importante tenere presente che non si tratta di un processo guidato dall'IT. Assicurarsi di collaborare con il team legale e di conformità per sviluppare uno schema di classificazione ed etichettatura appropriato per i dati dell'organizzazione.

Microsoft 365 funzionalità di protezione delle informazioni consentono di individuare le informazioni di cui si dispone, la posizione in cui sono archiviate e le informazioni che richiedono una protezione aggiuntiva. La protezione delle informazioni è un processo continuo e le funzionalità di Microsoft 365 offrono visibilità sul modo in cui gli utenti usano e distribuiscono le informazioni riservate, dove sono attualmente archiviate e dove fluisce. Puoi anche vedere come gli utenti gestendo le informazioni regolamentate per essere certi che siano applicate le etichette e le protezioni appropriate.


|Consiglio |E3|E5 |
|---------|---------|---------|
|**Esaminare e ottimizzare l'accesso condizionale e i criteri** correlati per allinearsi agli obiettivi per una rete senza attendibilità. La protezione dalle minacce note include l'implementazione di un set di [criteri consigliati.](./office-365-security/microsoft-365-policies-configurations.md) Esamina l'implementazione di questi criteri per assicurarti di proteggere le app e i dati da hacker che hanno ottenuto l'accesso alla rete. Il criterio di protezione delle app intune consigliato per Windows 10 abilita Windows Information Protection (WIP). WiP protegge da perdite accidentali dei dati dell'organizzazione tramite app e servizi, come la posta elettronica, i social media e il cloud pubblico. |         |![segno di spunta verde](../media/green-check-mark.png)|
|**Disabilitare l'inoltro esterno della posta elettronica**. Gli hacker che ottengono l'accesso alla cassetta postale di un utente possono rubare la posta impostando la cassetta postale per inoltrare automaticamente la posta elettronica. Questo può accadere anche senza la consapevolezza dell'utente. È possibile evitare questo problema configurando una regola del flusso di posta.|![segno di spunta verde](../media/green-check-mark.png) |![segno di spunta verde](../media/green-check-mark.png)|
|**Disabilitare la condivisione di calendari esterni anonimi**. Per impostazione predefinita, la condivisione di calendari anonimi esterni è consentita. [Disabilitare la condivisione del](/exchange/sharing/sharing-policies/modify-a-sharing-policy) calendario per ridurre potenziali perdite di informazioni riservate.|![segno di spunta verde](../media/green-check-mark.png) |![segno di spunta verde](../media/green-check-mark.png)|
|**Configurare i criteri di prevenzione della perdita dei dati per i dati sensibili**. Creare un criterio di prevenzione della perdita di dati nel Centro sicurezza e conformità per individuare e proteggere i dati sensibili, ad esempio numeri di carta di credito, numeri di previdenza sociale e numeri &amp; di conto corrente bancario. Microsoft 365 include molti tipi di informazioni riservate predefiniti che è possibile utilizzare nei criteri di prevenzione della perdita di dati. È inoltre possibile creare tipi di informazioni riservate personalizzati per l'ambiente. |![segno di spunta verde](../media/green-check-mark.png)|![segno di spunta verde](../media/green-check-mark.png)|
|**Implementare la classificazione dei dati e i criteri di protezione delle informazioni**. Implementare etichette di riservatezza e usarle per classificare e applicare la protezione ai dati sensibili. È inoltre possibile utilizzare queste etichette nei criteri di prevenzione della perdita di dati. Se si usano etichette di Azure Information Protection, è consigliabile evitare di creare nuove etichette in altre centri di amministrazione.|         |![segno di spunta verde](../media/green-check-mark.png)|
|**Proteggere i dati in app e servizi di** terze parti tramite Cloud App Security . Configurare Cloud App Security criteri per proteggere le informazioni riservate nelle app cloud di terze parti, ad esempio Salesforce, Box o Dropbox. Puoi usare i tipi di informazioni riservate e le etichette di riservatezza che hai creato nei criteri di Cloud App Security e applicarlo nelle app SaaS. <br><br>Microsoft Cloud App Security consente di applicare un'ampia gamma di processi automatizzati. I criteri possono essere impostati per fornire analisi di conformità continue, attività di eDiscovery legali, DLP per contenuti sensibili condivisi pubblicamente e altro ancora. Cloud App Security possibile monitorare qualsiasi tipo di file in base a più di 20 filtri di metadati (ad esempio, livello di accesso, tipo di file). |         |![segno di spunta verde](../media/green-check-mark.png)|
|**Usa [Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/information-protection-in-windows-overview) per identificare se gli utenti archiviano informazioni riservate nei Windows dispositivi**. |         |![segno di spunta verde](../media/green-check-mark.png)|
|**Utilizzare [AIP Scanner per](/azure/information-protection/deploy-aip-scanner) identificare e classificare le informazioni tra server e condivisioni file.** Usa lo strumento di creazione di report AIP per visualizzare i risultati ed eseguire le azioni appropriate.|         |![segno di spunta verde](../media/green-check-mark.png)|

Nel diagramma seguente vengono illustrate queste funzionalità.
![Funzionalità consigliate per la protezione da violazioni](../media/m365-security-bdm-illustrations-assume-breach.png)

## <a name="continuous-monitoring-and-auditing"></a>Monitoraggio e controllo continui

Infine, il monitoraggio continuo e il controllo dell'ambiente Microsoft 365 insieme a Windows e Dispositivi è fondamentale per assicurarsi di essere in grado di rilevare e correggere rapidamente eventuali intrusioni. Strumenti come Punteggio sicuro, Centro sicurezza e analisi avanzata di Microsoft Intelligent Graph forniscono informazioni errevoli nel tenant e collegano grandi quantità di dati di intelligence sulle minacce e di sicurezza per fornire protezione e rilevamento delle minacce senza precedenti.


|Consiglio |E3 |E5 |
|---------|---------|---------|
|Verificare che **il registro di controllo** sia attivato.|![segno di spunta verde](../media/green-check-mark.png)|![segno di spunta verde](../media/green-check-mark.png)|
|**Review Secure Score weekly** - Secure score is a central location to access the Security status of your company and take actions based on Secure score recommendations. È consigliabile eseguire questo controllo ogni settimana.|![segno di spunta verde](../media/green-check-mark.png)|![segno di spunta verde](../media/green-check-mark.png)|
|Usare **Microsoft Defender per Office 365** strumenti:<br>* Funzionalità di analisi e risposta alle minacce<br> * Analisi e risposta automatizzate |         |![segno di spunta verde](../media/green-check-mark.png)|
|Usa **Microsoft Defender per Endpoint**:<br> *    [Rilevamento e risposta degli endpoint](/windows/security/threat-protection/microsoft-defender-atp/overview-endpoint-detection-response) <br> * Analisi automatizzata e correzione Punteggio sicuro <br>*    [Ricerca avanzata](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview) <br>|         |![segno di spunta verde](../media/green-check-mark.png)|
|Usa **Microsoft Cloud App Security** per rilevare comportamenti insoliti tra le app cloud per identificare ransomware, utenti compromessi o applicazioni non autorizzate, analizzare l'utilizzo ad alto rischio e correggere automaticamente per limitare il rischio all'organizzazione.|         |![segno di spunta verde](../media/green-check-mark.png)|
|Usa **Microsoft Azure Sentinel** o lo strumento SIEM corrente per monitorare le minacce in tutto l'ambiente. |         |![segno di spunta verde](../media/green-check-mark.png)|
|**Distribuire [Microsoft Defender for Identity](/azure-advanced-threat-protection/what-is-atp)** per monitorare e proteggere dalle minacce destinate all'ambiente Active Directory locale.   |         |![segno di spunta verde](../media/green-check-mark.png) |
|Usare **Azure Defender** _ per monitorare le minacce nei carichi di lavoro ibridi e cloud. Azure Defender_ include un livello gratuito di funzionalità e un livello standard di funzionalità a pagamento in base alle ore di risorse o alle transazioni.|         |         |

Nel diagramma seguente vengono illustrate queste funzionalità.
![Funzionalità consigliate per il monitoraggio e il controllo continui](../media/m365-security-bdm-illustrations-monitoring-auditing.png)

Principali azioni di monitoraggio consigliate:
- **Review Microsoft Secure Score weekly** - Secure score is a central location to access the security status of your tenant and to take actions based on top recommendations. È consigliabile eseguire questo controllo ogni settimana. Secure Score include consigli su Azure AD, Intune, Cloud App Security e Microsoft Defender for Endpoint, oltre a Office 365. 
- **Esaminare gli accessi rischiosi** settimanalmente: usare l'interfaccia di amministrazione di Azure AD per esaminare gli accessi rischiosi settimanalmente. Il set di regole di identità e accesso al dispositivo consigliato include un criterio per applicare la modifica della password agli accessi rischiosi.  
- Esaminare i principali utenti di malware e **phished** settimanalmente: usare Microsoft Defender per Office 365 Threat Explorer per esaminare i principali utenti mirati con malware e phish e per scoprire la causa principale del motivo per cui questi utenti sono interessati.