---
title: Intestazioni messaggi della protezione da posta indesiderata
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 2e3fcfc5-5604-4b88-ac0a-c5c45c03f1db
ms.collection:
- M365-security-compliance
description: Informazioni sui campi e sui valori di intestazione aggiunti ai messaggi da Exchange Online Protection.
ms.openlocfilehash: 02588c8d2423d8925931ddf00a0c7bd8504e0de0
ms.sourcegitcommit: 4986032867b8664a215178b5e095cbda021f3450
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/12/2020
ms.locfileid: "41957241"
---
# <a name="anti-spam-message-headers"></a>Intestazioni messaggi della protezione da posta indesiderata

Quando Exchange Online Protection analizza un messaggio di posta elettronica in ingresso, inserisce l'intestazione **X-Forefront-Antispam-Report** nel messaggio. I campi di questa intestazione consentono agli amministratori di ottenere informazioni relative al messaggio e a come è stato elaborato. I campi nell'intestazione **X-Microsoft-Antispam** forniscono informazioni aggiuntive sulla posta inviata in massa e sul phishing. Oltre a queste due intestazioni, Exchange Online Protection inserisce anche i risultati dell'autenticazione della posta elettronica per ogni messaggio che elabora nell'intestazione **Authentication-results**.

Per informazioni sulla visualizzazione dell'intestazione di un messaggio di posta elettronica in diversi client di posta elettronica, vedere [Visualizzare le intestazioni dei messaggi Internet in Outlook](https://support.office.com/article/cd039382-dc6e-4264-ac74-c048563d212c).

> [!TIP]
> È possibile copiare e incollare il contenuto di un'intestazione di messaggio nello strumento [Analizzatore messaggi](https://testconnectivity.microsoft.com/?tabid=mha). Questo strumento consente di analizzare le intestazioni e di inserirle in un formato più leggibile.

## <a name="x-forefront-antispam-report-message-header-fields"></a>Campi di intestazione del messaggio X-Forefront-Antispam-Report

Dopo aver effettuato l'accesso alle informazioni relative all'intestazione del messaggio, cercare **X-Forefront-Antispam-Report**, quindi cercare i campi seguenti. L'utilizzo degli altri campi dell'intestazione è riservato al team di protezione dalla posta indesiderata di Microsoft per scopi di diagnostica.

|**Campo di intestazione**|**Descrizione**|
|:-----|:-----|
|CIP: \[indirizzo IP\]|L'indirizzo IP che si connette. È possibile specificare l'indirizzo IP quando si crea un elenco di indirizzi IP consentiti o un elenco di indirizzi IP bloccati nel filtro di connessione. Per ulteriori informazioni, vedere [Configurare i criteri di filtro delle connessioni](configure-the-connection-filter-policy.md).|
|CTRY|Il paese dal quale il messaggio è stato connesso al servizio. Questo è determinato dall'indirizzo IP di connessione, il quale potrebbe non essere uguale all'indirizzo IP di invio di origine.|
|LANG|LANG:   la lingua in cui è scritto il messaggio, come specificato dal codice paese (ad esempio, ru_RU per la Russia).|
|SCL|Il valore del livello di probabilità di posta indesiderata (SCL) del messaggio. Per ulteriori informazioni sull'interpretazione di questi valori, vedere [Livelli di sicurezza della protezione contro la posta indesiderata](spam-confidence-levels.md).  |
|SRV:BULK|Il messaggio è stato identificato come un messaggio di posta elettronica in blocco. Se l'**opzione avanzata di filtro della posta indesiderata Blocca tutti i messaggi di posta in blocco** è abilitata, il messaggio verrà contrassegnato come posta indesiderata. Se l'opzione è disabilitata, il messaggio verrà contrassegnato come posta indesiderata solo se il resto delle regole del filtro stabiliscono che è indesiderato.|
|SFV:SFE|Il filtro è stato ignorato e il messaggio è stato lasciato passare perché è stato inviato da un indirizzo presente in un singolo elenco dei mittenti attendibili.|
|SFV:BLK|Il filtro è stato ignorato e il messaggio è stato bloccato perché è stato inviato da un indirizzo presente in un singolo elenco dei mittenti bloccati.  <br/> **Suggerimento:** per ulteriori informazioni su come gli utenti finali possono creare elenchi di mittenti attendibili e bloccati, vedere [Filtrare la posta indesiderata in Outlook sul web](https://support.office.com/article/db786e79-54e2-40cc-904f-d89d57b7f41d) e [ Informazioni generali sul filtro per la posta indesiderata](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089) (Outlook).|
|IPV:CAL|Il messaggio è stato consentito tramite il filtro da posta indesiderata poiché l'indirizzo IP è stato specificato in un elenco di indirizzi IP bloccati nel filtro di connessione.|
|IPV:NLI|L'indirizzo IP non è stato elencato in nessuno degli elenchi di reputazione IP.|
|SFV:SPM|Il messaggio è stato contrassegnato come posta indesiderata dal filtro contenuto.|
|SFV:SKS|Il messaggio è stato contrassegnato come posta indesiderata prima di essere elaborato dal filtro contenuto. Questo include i messaggi che corrispondono alla regola del flusso di posta (nota anche come regola di trasporto) per contrassegnarlo automaticamente come indesiderato e ignorare tutte le regole del filtro aggiuntive.|
|SFV:SKA|Il messaggio ha ignorato il filtro ed è stato recapitato nella posta in arrivo perché è stata trovata una corrispondenza con un elenco Consenti nei criteri di filtro posta indesiderata, come l'**Elenco mittenti consentiti**.|
|SFV:SKB|Il messaggio è stato contrassegnato come posta indesiderata perché è stata trovata una corrispondenza con un elenco Blocca nei criteri di filtro posta indesiderata, come l'**Elenco mittenti bloccati**.|
|SFV:SKN|Il messaggio è stato contrassegnato come posta non indesiderata prima di essere elaborato dal filtro contenuto. Questo include i messaggi che corrispondono alla regola del flusso di posta per contrassegnarlo automaticamente come non indesiderato e ignorare tutte le regole del filtro aggiuntive.|
|SFV:SKN|Come per SFV:SKN, il messaggio ha ignorato il filtro per un altro motivo, ad esempio perché si tratta di posta elettronica tra organizzazioni all'interno di un tenant.|
|SFV:SKQ|Il messaggio è stato rilasciato dalla quarantena ed è stato inviato al destinatario.|
|SFV:NSPM|Il messaggio è stato contrassegnato come non indesiderato ed è stato inviato al destinatario.|
|H:\[helostring\]|La stringa HELO or EHLO del server di posta elettronica di connessione.|
|PTR:\[ReverseDNS\]|Il record PTR o record "Pointer" dell'indirizzo IP del mittente, noto anche come indirizzo DNS inverso.|
|ARC|Le intestazioni del protocollo ARC sono le seguenti: <br/>• AAR: registra il contenuto dell'intestazione Authentication results da DMARC. <br/>• AMS: questa intestazione contiene le firme crittografiche del messaggio. <br/>• AS: contiene le firme crittografiche delle intestazioni dei messaggi. Questa intestazione contiene il tag di convalida della catena denominata "cv=" e include il risultato della convalida della catena, ad esempio **nessuna**, **superata** oppure **non riuscita**.|
|CAT:|categoria dei criteri di protezione applicati al messaggio: <br/>MALW: malware <br/>HPHSH: phishing con alta confidenza <br/>PHSH: phishing <br/>HSPM: posta indesiderata con alta confidenza <br/>SPOOF: spoofing <br/>SPM: posta indesiderata <br/>BULK: posta inviata in blocco <br/>DIMP: imitazione del dominio <br/>UIMP: imitazione dell'utente <br/>GIMP: intelligence della cassetta postale<br/>Potenzialmente un messaggio in arrivo potrebbe essere contrassegnato in base a più forme di protezione e a più analisi di rilevamento. Ai criteri sono assegnate diverse priorità e verrà applicato il criterio con la priorità più alta. Vedere [Criteri applicabili ai messaggi di posta elettronica quando vengono usati più metodi di protezione e analisi di rilevamento](how-policies-and-protections-are-combined.md).|
|SFTY|Il messaggio è stato identificato come phishing e sarà anche contrassegnato con uno dei valori seguenti: <br/>9.1: valore predefinito. Il messaggio contiene un URL di phishing, potrebbe contenere altri contenuti di phishing o potrebbe essere stato contrassegnato come phishing da un altro filtro della posta elettronica, ad esempio una versione locale di Exchange Server prima dell'inoltro del messaggio a Office 365. <br/>9.11: il messaggio non ha superato i controlli anti-spoofing, in cui il dominio di origine nell'intestazione Da: è uguale a, o è allineato con o fa parte della stessa organizzazione del dominio di destinazione. Questo indica che al messaggio verrà aggiunto un suggerimento per la sicurezza anti-spoofing intra-organizzazione. <br/>9.19: il messaggio non ha superato i controlli di imitazione del dominio, in cui il dominio di origine prova a imitare un dominio di proprietà del destinatario o un dominio personalizzato protetto dai criteri anti-phishing. Questo indica che al messaggio verrà aggiunto un suggerimento per la sicurezza dell'imitazione, se abilitato tramite i criteri anti-phishing. <br/>9.20: il messaggio non ha superato i controlli di imitazione utente, in cui l'utente di origine prova a imitare un utente all'interno dell'organizzazione dei destinatari oppure un utente personalizzato protetto dai criteri anti-phishing. Questo indica che al messaggio verrà aggiunto un suggerimento per la sicurezza dell'imitazione, se abilitato tramite i criteri anti-phishing. <br/>9.21: il messaggio non ha superato i controlli anti-spoofing e il dominio di origine nell'intestazione Da: non viene autenticato e proviene da un dominio esterno. Usato in combinazione con CompAuth (vedere Authentication-Results). <br/>9.22: uguale a 9.21, ad eccezione del fatto che l'utente ha un mittente attendibile che è stato sovrascritto. <br/>9.23: uguale a 9.22, ad eccezione del fatto che l'organizzazione ha un mittente o un dominio consentito che è stato sovrascritto. <br/>9.24: uguale a 9.23, ad eccezione del fatto che l'utente ha una regola del flusso di posta di Exchange che è stata sovrascritta.|
|X-CustomSpam: \[ASFOption\]|Il messaggio corrisponde a un'opzione di filtro avanzato della posta indesiderata. Ad esempio, **X-CustomSpam: i collegamenti immagini a siti remoti** indicano che l'opzione ASF dei **collegamenti immagini a siti remoti** ha trovato una corrispondenza. Per scoprire quale testo X-header viene aggiunto per ogni opzione ASF specifica, vedere [Opzioni avanzate per il filtraggio della posta indesiderata](advanced-spam-filtering-asf-options.md).|
|

## <a name="x-microsoft-antispam-message-header-fields"></a>Campi di intestazione del messaggio X-Microsoft-Antispam

Nella tabella seguente vengono descritti i campi utili nell'intestazione del messaggio **X-Microsoft-Antispam**. L'utilizzo degli altri campi dell'intestazione è riservato al team di protezione dalla posta indesiderata di Microsoft per scopi di diagnostica.

|**Campo di intestazione**|**Descrizione**|
|:-----|:-----|
|BCL|Il Livello di reclamo in blocco (BCL) del messaggio consente di distinguere i diversi tipi di mittenti di posta inviata in massa. È rappresentato come valore compreso tra 0 e 9. Per i valori e altre informazioni su BCL, vedere [Valori del Livello di reclamo in blocco](bulk-complaint-level-values.md).|

## <a name="authentication-results-message-header"></a>Intestazione del messaggio Authentication-results

I risultati dei controlli su SPF, DKIM e DMARC vengono registrati (o contrassegnati) da Office 365 nell'intestazione del messaggio **Authentication-results** quando i server di posta ricevono un messaggio di posta elettronica.

### <a name="check-stamp-syntax-and-examples"></a>Esempi e sintassi del timbro segno di spunta

I seguenti esempi di sintassi mostrano una porzione del "contrassegno" che Office 365 applica all'intestazione di ogni messaggio di posta elettronica che viene sottoposto a una verifica dell'autenticazione della posta elettronica quando viene ricevuto dai server della posta. Il contrassegno viene aggiunto all'intestazione **Authentication-Results**.

#### <a name="syntax-spf-check-stamp"></a>Sintassi: timbro segno di spunta SPF

Per SPF, si applica la sintassi seguente.

```text
spf=<pass (IP address)|fail (IP address)|softfail (reason)|neutral|none|temperror|permerror> smtp.mailfrom=<domain>
```

**Esempi: timbro segno di spunta SPF

```text
spf=pass (sender IP is 192.168.0.1) smtp.mailfrom=contoso.com
spf=fail (sender IP is 127.0.0.1) smtp.mailfrom=contoso.com
```

#### <a name="syntax-dkim-check-stamp"></a>Sintassi: timbro segno di spunta DKIM

Per DKIM, si applica la sintassi seguente.

```text
dkim=<pass|fail (reason)|none> header.d=<domain>
```

**Esempi: timbro segno di spunta DKIM

```text
dkim=pass (signature was verified) header.d=contoso.com
dkim=fail (body hash did not verify) header.d=contoso.com
```

#### <a name="syntax-dmarc-check-stamp"></a>Sintassi: timbro segno di spunta DMARC

Per DMARC, si applica la sintassi seguente.

```text
dmarc=<pass|fail|bestguesspass|none> action=<permerror|temperror|oreject|pct.quarantine|pct.reject> header.from=<domain>
```

#### <a name="examples-dmarc-check-stamp"></a>Esempi: timbro segno di spunta DMARC

```text
dmarc=pass action=none header.from=contoso.com
dmarc=bestguesspass action=none header.from=contoso.com
dmarc=fail action=none header.from=contoso.com
dmarc=fail action=oreject header.from=contoso.com
```

### <a name="authentication-results-message-header-fields-used-by-office-365-email-authentication"></a>Campi di intestazione del messaggio Authentication-results utilizzati dall'autenticazione della posta elettronica di Office 365

Nella tabella seguente vengono descritti i campi e i valori possibili per il controllo di autenticazione di ogni messaggio di posta elettronica.

|**Campo di intestazione**|**Descrizione**|
|:-----|:-----|
|spf|Descrive i risultati del controllo SPF per il messaggio. Tra i possibili valori sono inclusi:<br/>**pass (indirizzo IP)**: indica che il controllo SPF per il messaggio è stato superato e include l'indirizzo IP del mittente. Il client è autorizzato a inviare o inoltrare la posta elettronica per conto del dominio del mittente. <br/>**fail (indirizzo IP)**: indica che il controllo SPF per il messaggio non è stato superato e include l'indirizzo IP del mittente. Talvolta viene definito controllo di tipo _hard fail_. <br/>**softfail (motivo)**: indica che il record SPF ha designato l'host come non autorizzato all'invio ma in transizione. <br/>**neutral**: indica che il record SPF ha dichiarato in modo esplicito che non afferma se l'indirizzo IP è autorizzato. <br/>**none**: indica che il dominio non dispone di un record SPF o che il record SPF non restituisce un risultato. <br/>**temperror**: indica che si è verificato un errore che potrebbe essere di natura temporanea, ad esempio un errore DNS. Riprovare più tardi per verificare se il problema viene risolto senza alcun intervento dell'amministratore. <br/>**permerror**: indica che si è verificato un errore permanente. Ciò accade quando, ad esempio, il dominio presenta un record SPF con formato non valido.|
|smtp.mailfrom|Contiene il dominio di origine da cui proviene il messaggio. Gli errori relativi a tale messaggio di posta elettronica verranno inviati al postmaster o all'entità responsabile del dominio. A volte viene chiamato indirizzo 5321.MailFrom o indirizzo reverse-path address sulla busta del messaggio.|
|dkim|Descrive i risultati del controllo DKIM per il messaggio. Tra i possibili valori sono inclusi:<br/>**pass**: indica che il controllo DKIM per il messaggio è stato superato. <br/>**fail (motivo)**: indica che il controllo DKIM per il messaggio non è stato superato e include il motivo, ad esempio se il messaggio non è stato firmato o se la firma non è stata verificata. <br/>**none**: indica che il messaggio non è stato firmato. Ciò potrebbe indicare o meno che il dominio dispone di un record DKIM o che il record DKIM non restituisce un risultato, solo che il messaggio non è stato firmato.|
|header.d|Dominio identificato nella firma DKIM, se presente. Questo è il dominio sottoposto a query per la chiave pubblica.|
|dmarc|Descrive i risultati del controllo DMARC per il messaggio. Tra i possibili valori sono inclusi:<br/>**pass**: indica che il controllo DMARC per il messaggio è stato superato. <br/>**fail**: indica che il controllo DMARC per il messaggio non è stato superato. <br/>**bestguesspass**: indica che non esistono record TXT DMARC per il dominio, ma che se ne esistesse uno, il controllo DMARC per il messaggio sarebbe stato superato. Questo problema dipende dal fatto che il dominio nell'indirizzo 5321.MailFrom corrisponde al dominio nell'indirizzo 5322.From. <br/>**none**: indica che non esistono record TXT DKIM per il dominio di invio in DNS.|
|action|Indica l'azione eseguita dal filtro posta indesiderata in base ai risultati del controllo DMARC. Ad esempio:<br/>**permerror**: si è verificato un errore permanente durante la valutazione DMARC, ad esempio è stato trovato un record TXT DMARC con formato non valido in DNS. Tentando di inviare di nuovo questo messaggio, probabilmente si otterrebbe un risultato diverso. Al contrario, potrebbe essere necessario contattare il proprietario del dominio per risolvere il problema. <br/>**temperror**: si è verificato un errore temporaneo durante la valutazione DMARC. Potrebbe essere possibile richiedere che il mittente invii il messaggio in un secondo momento per elaborare il messaggio correttamente. <br/>**oreject** o **o.reject**: abbreviazione di override reject (rifiuto override). In questo caso, Office 365 usa questa azione quando riceve un messaggio che non supera il controllo DMARC da un dominio il cui record TXT DMARC ha un criterio di p=reject. Anziché eliminare o rifiutare il messaggio, Office 365 lo contrassegna come posta indesiderata. Per ulteriori informazioni sul motivo per cui Office 365 è configurato in questo modo, vedere [Come viene gestita la posta elettronica in ingresso che non supera il controllo DMARC in Office 365](use-dmarc-to-validate-email.md#inbounddmarcfail). <br/>**pct.quarantine**: indica che una percentuale inferiore al 100% di messaggi che non superano il controllo DMARC verrà recapitata comunque. Ciò significa che il messaggio non ha superato il controllo DMARC e il criterio è stato impostato su quarantine, ma il campo pct non è stato impostato su 100% e il sistema ha determinato in modo casuale di non applicare l'azione DMARC, in base al criterio del dominio specificato. <br/>**pct.reject**: indica che una percentuale inferiore al 100% di messaggi che non superano il controllo DMARC verrà recapitata comunque. Ciò significa che il messaggio non ha superato il controllo DMARC e il criterio è stato impostato su reject, ma il campo pct non è stato impostato su 100% e il sistema ha determinato in modo casuale di non applicare l'azione DMARC, in base al criterio del dominio specificato.|
|header.from|Il dominio dell'indirizzo mittente nell'intestazione del messaggio di posta elettronica. A volte viene chiamato indirizzo _5322.From_.|
|compauth|Risultato autenticazione composita. Viene usato da Office 365 per combinare più tipi di autenticazione, come SPF, DKIM, DMARC o qualsiasi altra parte del messaggio, per determinare se il messaggio è stato autenticato o meno. Usa il dominio Da: come base per la valutazione.|
|motivo|Il motivo per cui l'autenticazione composita è stata superata o meno. Il valore relativo al motivo è costituito da tre cifre: <br/>**000**: il messaggio non ha superato in modo esplicito l'autenticazione. Ad esempio, il messaggio ha ricevuto un errore di DMARC con un'azione di quarantena o rifiuto. <br/>**001**: il messaggio non ha superato in modo esplicito l'autenticazione e il dominio di origine non ha pubblicato criteri di autenticazione. Ad esempio, un criterio DMARC p=none. <br/>**1xx** o **7xx**: il messaggio ha superato l'autenticazione. Le seconde due cifre sono codici interni usati da Office 365. <br/>**2xx**: il messaggio ha superato l'autenticazione. Le seconde due cifre sono codici interni usati da Office 365. <br/>**3xx**: il messaggio non è stato controllato per l'autenticazione composita. <br/>**4xx** o **9xx**: il messaggio ha ignorato l'autenticazione composita. Le seconde due cifre sono codici interni usati da Office 365.|
|
