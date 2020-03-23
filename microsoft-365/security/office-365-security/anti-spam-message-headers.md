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
ms.openlocfilehash: 55ba5435b181506cd39314275a9d8c8c6b459b28
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/21/2020
ms.locfileid: "42894183"
---
# <a name="anti-spam-message-headers-in-office-365"></a>Intestazioni messaggi della protezione da posta indesiderata in Office 365

Quando Exchange Online Protection (EOP) analizza un messaggio di posta elettronica in ingresso, inserisce l'intestazione **X-Forefront-Antispam-Report** nel messaggio. I campi di questa intestazione consentono agli amministratori di ottenere informazioni relative al messaggio e a come è stato elaborato. I campi nell'intestazione **X-Microsoft-Antispam** forniscono informazioni aggiuntive sulla posta inviata in massa e sul phishing. Oltre a queste due intestazioni, Exchange Online Protection inserisce anche i risultati dell'autenticazione della posta elettronica per ogni messaggio che elabora nell'intestazione **Authentication-results**.

Per informazioni sulla visualizzazione dell'intestazione di un messaggio di posta elettronica in diversi client di posta elettronica, vedere [Visualizzare le intestazioni dei messaggi Internet in Outlook](https://support.office.com/article/cd039382-dc6e-4264-ac74-c048563d212c).

> [!TIP]
> È possibile copiare e incollare il contenuto di un'intestazione di messaggio nello strumento [Analizzatore messaggi](https://testconnectivity.microsoft.com/?tabid=mha). Questo strumento consente di analizzare le intestazioni e di inserirle in un formato più leggibile.

## <a name="x-forefront-antispam-report-message-header-fields"></a>Campi di intestazione del messaggio X-Forefront-Antispam-Report

Dopo aver effettuato l'accesso alle informazioni relative all'intestazione del messaggio, cercare **X-Forefront-Antispam-Report**, quindi cercare i campi seguenti. L'utilizzo degli altri campi dell'intestazione è riservato al team di protezione dalla posta indesiderata di Microsoft per scopi di diagnostica.

|||
|---|---|
|**Campo di intestazione**|**Descrizione**|
|ARC|Le intestazioni del protocollo ARC sono le seguenti: <ul><li>AAR: registra il contenuto dell'intestazione Authentication results da DMARC.</li><li>AMS: questa intestazione contiene le firme crittografiche del messaggio.</li><li>AS: contiene le firme crittografiche delle intestazioni dei messaggi. Questa intestazione contiene il tag di convalida della catena denominata "cv=" e include il risultato della convalida della catena, ad esempio **nessuna**, **superata** oppure **non riuscita**.</li></ul>|
|CAT:|categoria dei criteri di protezione applicati al messaggio: <ul><li>BULK: posta inviata in blocco</li><li>DIMP: imitazione del dominio</li><li>GIMP: intelligence della cassetta postale</li><li>HPHSH o HPHISH : alta probabilità di phishing </li><li>HSPM: alta probabilità di posta indesiderata</li><li>MALW: malware</li><li>PHSH: phishing</li><li>SPM: posta indesiderata</li><li>SPOOF: spoofing</li><li>UIMP: imitazione dell'utente</li></ul><br/>Un messaggio in ingresso potrebbe essere contrassegnato in base a più forme di protezione e a più analisi di rilevamento. Ai criteri sono assegnate diverse priorità e il criterio con la priorità più alta viene applicato per primo. Per altre informazioni, vedere [Criteri applicabili ai messaggi di posta elettronica quando vengono usati più metodi di protezione e analisi di rilevamento](how-policies-and-protections-are-combined.md).|
|CIP: \[indirizzo IP\]|L'indirizzo IP che si connette. È possibile usare questo indirizzo IP nell'elenco Consenti indirizzi IP o nell'elenco Blocca indirizzi IP. Per ulteriori informazioni, vedere [Configurare il filtraggio delle connessioni in Office 365](configure-the-connection-filter-policy.md).|
|CTRY|Il paese o l’area geografica di origine come determinato dall'indirizzo IP di connessione, il quale potrebbe non essere uguale all'indirizzo IP di invio di origine.|
|H:\[helostring\]|Stringa HELO o EHLO del server della posta connesso.|
|IPV:CAL|Il messaggio è stato ignorato dal filtro della posta indesiderata perché l'indirizzo IP di origine era riportato nell'elenco Consenti indirizzi IP. Per ulteriori informazioni, vedere [Configurare il filtraggio delle connessioni in Office 365](configure-the-connection-filter-policy.md).|
|IPV:NLI|L'indirizzo IP non è stato elencato in nessuno degli elenchi di reputazione IP.|
|LANG|LANG:   la lingua in cui è scritto il messaggio, come specificato dal codice paese (ad esempio, ru_RU per la Russia).|
|PTR:\[ReverseDNS\]|Il record PTR, noto anche come record "Pointer" o indirizzo DNS inverso, dell’indirizzo IP del mittente.|
|SCL|Il livello di probabilità di posta indesiderata (SCL) del messaggio. Più alto è il valore, maggiore è la probabilità che si tratti di un messaggio di posta indesiderata. Per ulteriori informazioni, vedere [Livello di probabilità di posta indesiderata (SCL) in Office 365](spam-confidence-levels.md).|
|SFTY|Il messaggio è stato identificato come phishing e sarà anche contrassegnato con uno dei valori seguenti: <ul><li>9.1: valore predefinito. Il messaggio contiene un URL di phishing, potrebbe contenere altri contenuti di phishing o potrebbe essere stato contrassegnato come phishing da un altro filtro della posta elettronica, ad esempio una versione locale di Exchange Server prima dell'inoltro del messaggio a Office 365.</li><li>9.11: il messaggio non ha superato i controlli anti-spoofing, in cui il dominio di origine nell'intestazione Da: è uguale a, o è allineato con o fa parte della stessa organizzazione del dominio di destinazione. Questo indica che al messaggio verrà aggiunto un suggerimento per la sicurezza anti-spoofing intra-organizzazione.</li><li>9.19: il messaggio non ha superato i controlli di imitazione del dominio, in cui il dominio di origine prova a imitare un dominio di proprietà del destinatario o un dominio personalizzato protetto dai criteri anti-phishing. Questo indica che al messaggio verrà aggiunto un suggerimento per la sicurezza dell'imitazione, se abilitato tramite i criteri anti-phishing.</li><li>9.20: il messaggio non ha superato i controlli di imitazione utente, in cui l'utente di origine prova a imitare un utente all'interno dell'organizzazione dei destinatari oppure un utente personalizzato protetto dai criteri anti-phishing. Questo indica che al messaggio verrà aggiunto un suggerimento per la sicurezza dell'imitazione, se abilitato tramite i criteri anti-phishing.</li><li>9.21: il messaggio non ha superato i controlli anti-spoofing e il dominio di origine nell'intestazione Da: non viene autenticato e proviene da un dominio esterno. Usato in combinazione con CompAuth (vedere Authentication-Results).</li><li>9.22: uguale a 9.21, ad eccezione del fatto che l'utente ha un mittente attendibile che è stato sovrascritto.</li><li>9.23: uguale a 9.22, ad eccezione del fatto che l'organizzazione ha un mittente o un dominio consentito che è stato sovrascritto.</li><li>9.24: uguale a 9.23, ad eccezione del fatto che l'utente ha una regola del flusso di posta di Exchange, nota anche come regola di trasporto, che è stata sovrascritta.</li></ul>|
|SFV:BLK|Il filtro è stato ignorato e il messaggio è stato bloccato perché è stato inviato da un indirizzo presente tra i Mittenti bloccati di Outlook di un utente (l’elenco dei mittenti bloccati dell’utente).<br/></br> Per altre informazioni sul modo in cui gli amministratori possono gestire l'elenco dei mittenti bloccati di un utente, vedere [Configurare le impostazioni di posta indesiderata nelle cassette postali di Exchange Online in Office 365](configure-junk-email-settings-on-exo-mailboxes.md).|
|SFV:NSPM|Il filtro posta indesiderata ha contrassegnato il messaggio come non indesiderato e il messaggio è stato inviato al destinatario.|
|SFV:SFE|Il filtro è stato ignorato e il messaggio è stato lasciato passare perché è stato inviato da un indirizzo presente tra i Mittenti attendibili di Outlook di un utente (l’elenco dei mittenti attendibili dell’utente).<br/></br> Per altre informazioni sul modo in cui gli amministratori possono gestire l'elenco dei mittenti attendibili di un utente, vedere [Configurare le impostazioni di posta indesiderata nelle cassette postali di Exchange Online in Office 365](configure-junk-email-settings-on-exo-mailboxes.md).|
|SFV:SKA|Il messaggio è stato ignorato dal filtro posta indesiderata ed è stato recapitato nella posta in arrivo perché corrisponde a una voce di un elenco di mittenti consentiti o di un elenco di domini consentiti in un criterio di protezione dalla posta indesiderata. Per altre informazioni, vedere [Configurare i criteri di protezione dalla posta indesiderata in Office 365](configure-your-spam-filter-policies.md).|
|SFV:SKB|Il messaggio è stato contrassegnato come posta indesiderata perché corrisponde a una voce di un elenco di mittenti bloccati o di domini bloccati in un criterio di protezione dalla posta indesiderata. Per altre informazioni, vedere [Configurare i criteri di protezione dalla posta indesiderata in Office 365](configure-your-spam-filter-policies.md).|
|SFV:SKI|Come per SFV:SKN, il messaggio ha ignorato il filtro posta indesiderata per un altro motivo, ad esempio perché si tratta di posta elettronica tra organizzazioni all'interno di un tenant.|
|SFV:SKN|Il messaggio è stato contrassegnato come posta non indesiderata prima di essere elaborato con il filtro posta indesiderata, ad esempio il messaggio è stato contrassegnato come SCL -1 o **Ignora il filtro posta indesiderata** da una regola del flusso di posta.|
|SFV:SKQ|Il messaggio è stato rilasciato dalla quarantena ed è stato inviato al destinatario.|
|SFV:SKS|Il messaggio è stato contrassegnato come posta indesiderata prima di essere elaborato con il filtro posta indesiderata, ad esempio il messaggio è stato contrassegnato come SCL 5-9 da una regola del flusso di posta.|
|SFV:SPM|Il messaggio è stato contrassegnato come posta indesiderata dal filtro posta indesiderata.|
|SRV:BULK|Il messaggio è stato identificato come posta elettronica in blocco dal filtro posta indesiderata e dalla soglia del livello di reclamo in blocco. Se il parametro _MarkAsSpamBulkMail_ è `On`, ed è attivato per impostazione predefinita, un messaggio di posta elettronica in blocco viene contrassegnato come alta probabilità di posta indesiderata (SCL 9). Per altre informazioni, vedere [Configurare i criteri di protezione dalla posta indesiderata in Office 365](configure-your-spam-filter-policies.md).|
|X-CustomSpam: \[ASFOption\]|Il messaggio corrisponde a un'impostazione di filtro avanzato della posta indesiderata (ASF). Per vedere il valore X-header per ogni impostazione ASF, consultare le [Impostazioni di filtro avanzato della posta indesiderata (ASF) in Office 365](advanced-spam-filtering-asf-options.md).|
|

## <a name="x-microsoft-antispam-message-header-fields"></a>Campi di intestazione del messaggio X-Microsoft-Antispam

Nella tabella seguente vengono descritti i campi utili nell'intestazione del messaggio **X-Microsoft-Antispam**. L'utilizzo degli altri campi dell'intestazione è riservato al team di protezione dalla posta indesiderata di Microsoft per scopi di diagnostica.

|||
|---|---|
|**Campo di intestazione**|**Descrizione**|
|BCL|Il Livello di reclamo in blocco (BCL) del messaggio. Più il BCL è elevato, maggiore è la probabilità che un messaggio di posta elettronica in blocco, anche nota come _posta grigia_, generi reclami, ed è quindi più probabile che si tratti di posta indesiderata. Per ulteriori informazioni, vedere [Livello di reclamo in blocco (BLC) in Office 365](bulk-complaint-level-values.md).|
|

## <a name="authentication-results-message-header"></a>Intestazione del messaggio Authentication-results

I risultati dei controlli su SPF, DKIM e DMARC vengono registrati (o contrassegnati) da Office 365 nell'intestazione del messaggio **Authentication-results** quando i server di posta ricevono un messaggio di posta elettronica.

### <a name="check-stamp-syntax-and-examples"></a>Esempi e sintassi del timbro segno di spunta

I seguenti esempi di sintassi mostrano una porzione del "contrassegno" che Office 365 applica all'intestazione di ogni messaggio di posta elettronica che viene sottoposto a una verifica dell'autenticazione della posta elettronica quando viene ricevuto dai server della posta. Il contrassegno viene aggiunto all'intestazione **Authentication-Results**.

#### <a name="syntax-spf-check-stamp"></a>Sintassi: timbro segno di spunta SPF

Per SPF, si applica la sintassi seguente.

```text
spf=<pass (IP address)|fail (IP address)|softfail (reason)|neutral|none|temperror|permerror> smtp.mailfrom=<domain>
```

##### <a name="examples-spf-check-stamp"></a>Esempi: timbro segno di spunta SPF

```text
spf=pass (sender IP is 192.168.0.1) smtp.mailfrom=contoso.com
spf=fail (sender IP is 127.0.0.1) smtp.mailfrom=contoso.com
```

#### <a name="syntax-dkim-check-stamp"></a>Sintassi: timbro segno di spunta DKIM

Per DKIM, si applica la sintassi seguente.

```text
dkim=<pass|fail (reason)|none> header.d=<domain>
```

##### <a name="examples-dkim-check-stamp"></a>Esempi: timbro segno di spunta DKIM

```text
dkim=pass (signature was verified) header.d=contoso.com
dkim=fail (body hash did not verify) header.d=contoso.com
```

#### <a name="syntax-dmarc-check-stamp"></a>Sintassi: timbro segno di spunta DMARC

Per DMARC, si applica la sintassi seguente.

```text
dmarc=<pass|fail|bestguesspass|none> action=<permerror|temperror|oreject|pct.quarantine|pct.reject> header.from=<domain>
```

##### <a name="examples-dmarc-check-stamp"></a>Esempi: timbro segno di spunta DMARC

```text
dmarc=pass action=none header.from=contoso.com
dmarc=bestguesspass action=none header.from=contoso.com
dmarc=fail action=none header.from=contoso.com
dmarc=fail action=oreject header.from=contoso.com
```

### <a name="authentication-results-message-header-fields-used-by-office-365-email-authentication"></a>Campi di intestazione del messaggio Authentication-results utilizzati dall'autenticazione della posta elettronica di Office 365

Nella tabella seguente vengono descritti i campi e i valori possibili per il controllo di autenticazione di ogni messaggio di posta elettronica.

|||
|---|---|
|**Campo di intestazione**|**Descrizione**|
|action|Indica l'azione eseguita dal filtro posta indesiderata in base ai risultati del controllo DMARC. Ad esempio:<ul><li>**oreject** o **o.reject**: abbreviazione di override reject (rifiuto override). In questo caso, Office 365 usa questa azione quando riceve un messaggio che non supera il controllo DMARC da un dominio il cui record TXT DMARC ha un criterio di p=reject. Anziché eliminare o rifiutare il messaggio, Office 365 lo contrassegna come posta indesiderata. Per ulteriori informazioni sul motivo per cui Office 365 è configurato in questo modo, vedere [Come viene gestita la posta elettronica in ingresso che non supera il controllo DMARC in Office 365](use-dmarc-to-validate-email.md#inbounddmarcfail).</li><li>**pct.quarantine**: indica che una percentuale inferiore al 100% di messaggi che non superano il controllo DMARC verrà recapitata comunque. Ciò significa che il messaggio non ha superato il controllo DMARC e il criterio è stato impostato su quarantine, ma il campo pct non è stato impostato su 100% e il sistema ha determinato in modo casuale di non applicare l'azione DMARC, in base al criterio del dominio specificato.</li><li>**pct.reject**: indica che una percentuale inferiore al 100% di messaggi che non superano il controllo DMARC verrà recapitata comunque. Ciò significa che il messaggio non ha superato il controllo DMARC e il criterio è stato impostato su reject, ma il campo pct non è stato impostato su 100% e il sistema ha determinato in modo casuale di non applicare l'azione DMARC, in base al criterio del dominio specificato.</li><li>**permerror**: si è verificato un errore permanente durante la valutazione DMARC, ad esempio è stato trovato un record TXT DMARC con formato non valido in DNS. Tentando di inviare di nuovo questo messaggio, probabilmente si otterrebbe un risultato diverso. Al contrario, potrebbe essere necessario contattare il proprietario del dominio per risolvere il problema.</li><li>**temperror**: si è verificato un errore temporaneo durante la valutazione DMARC. Potrebbe essere possibile richiedere che il mittente invii il messaggio in un secondo momento per elaborare il messaggio correttamente.</li></ul>|
|compauth|Risultato autenticazione composita. Viene usato da Office 365 per combinare più tipi di autenticazione, come SPF, DKIM, DMARC o qualsiasi altra parte del messaggio, per determinare se il messaggio è stato autenticato o meno. Usa il dominio Da: come base per la valutazione.|
|dkim|Descrive i risultati del controllo DKIM per il messaggio. Tra i possibili valori sono inclusi:<ul><li>**pass**: indica che il controllo DKIM per il messaggio è stato superato.</li><li>**fail (motivo)**: indica che il controllo DKIM per il messaggio non è stato superato e include il motivo, ad esempio se il messaggio non è stato firmato o se la firma non è stata verificata.</li><li>**none**: indica che il messaggio non è stato firmato. Ciò potrebbe indicare o meno che il dominio dispone di un record DKIM o che il record DKIM non restituisce un risultato, solo che il messaggio non è stato firmato.</li></ul>|
|dmarc|Descrive i risultati del controllo DMARC per il messaggio. Tra i possibili valori sono inclusi:<ul><li>**pass**: indica che il controllo DMARC per il messaggio è stato superato.</li><li>**fail**: indica che il controllo DMARC per il messaggio non è stato superato.</li><li>**bestguesspass**: indica che non esistono record TXT DMARC per il dominio, ma che se ne esistesse uno, il controllo DMARC per il messaggio sarebbe stato superato. Questo è dovuto al fatto che il dominio nell'indirizzo `5321.MailFrom`, noto anche come indirizzo posta mittente, mittente P1 o mittente della busta, corrisponde al dominio nell'indirizzo `5322.From`, anche noto come indirizzo mittente o mittente P2.</li><li>**none**: indica che non esistono record TXT DKIM per il dominio di invio in DNS.|
|header.d|Dominio identificato nella firma DKIM, se presente. Questo è il dominio sottoposto a query per la chiave pubblica.|
|header.from|Il dominio dell'indirizzo `5322.From` nell'intestazione del messaggio di posta elettronica, anche noto come indirizzo mittente o mittente P2. Il destinatario vede l'indirizzo mittente nei client di posta elettronica.|
|motivo|Il motivo per cui l'autenticazione composita è stata superata o meno. Il valore relativo al motivo è costituito da tre cifre: <ul><li>**000**: il messaggio non ha superato in modo esplicito l'autenticazione. Ad esempio, il messaggio ha ricevuto un errore di DMARC con un'azione di quarantena o rifiuto.</li><li>**001**: il messaggio non ha superato in modo esplicito l'autenticazione e il dominio di origine non ha pubblicato criteri di autenticazione. Ad esempio, un criterio DMARC p=none.</li><li>**1xx** o **7xx**: il messaggio ha superato l'autenticazione. Le seconde due cifre sono codici interni usati da Office 365.</li><li>**2xx**: il messaggio ha superato l'autenticazione. Le seconde due cifre sono codici interni usati da Office 365.</li><li>**3xx**: il messaggio non è stato controllato per l'autenticazione composita.</li><li>**4xx** o **9xx**: il messaggio ha ignorato l'autenticazione composita. Le seconde due cifre sono codici interni usati da Office 365.</li></ul>|
|smtp.mailfrom|Il dominio dell'indirizzo `5321.MailFrom`, anche noto come indirizzo posta mittente, mittente P1 o mittente della busta. Si tratta dell'indirizzo di posta elettronica usato per i report di mancato recapito, noti anche come NDR o notifiche di mancato recapito.|
|spf|Descrive i risultati del controllo SPF per il messaggio. Tra i possibili valori sono inclusi:<ul><li>**pass (indirizzo IP)**: indica che il controllo SPF per il messaggio è stato superato e include l'indirizzo IP del mittente. Il client è autorizzato a inviare o inoltrare la posta elettronica per conto del dominio del mittente.</li><li>**fail (indirizzo IP)**: indica che il controllo SPF per il messaggio non è stato superato e include l'indirizzo IP del mittente. Talvolta viene definito controllo di tipo _hard fail_.</li><li>**softfail (motivo)**: indica che il record SPF ha designato l'host come non autorizzato all'invio ma in transizione.</li><li>**neutral**: indica che il record SPF ha dichiarato in modo esplicito che non afferma se l'indirizzo IP è autorizzato.</li><li>**none**: indica che il dominio non dispone di un record SPF o che il record SPF non restituisce un risultato.</li><li>**temperror**: indica che si è verificato un errore che potrebbe essere di natura temporanea, ad esempio un errore DNS. Riprovare più tardi per verificare se il problema viene risolto senza alcun intervento dell'amministratore.</li><li>**permerror**: indica che si è verificato un errore permanente. Ciò accade quando, ad esempio, il dominio presenta un record SPF con formato non valido.</li></ul>|
|
