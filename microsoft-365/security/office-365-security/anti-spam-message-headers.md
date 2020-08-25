---
title: Intestazioni messaggi della protezione da posta indesiderata
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 2e3fcfc5-5604-4b88-ac0a-c5c45c03f1db
ms.collection:
- M365-security-compliance
description: Gli amministratori possono ottenere informazioni sui campi e sui valori di intestazione aggiunti ai messaggi da Exchange Online Protection (EOP). Questi campi di intestazione forniscono informazioni sul messaggio e su come è stato elaborato.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a5423ccf658843ab22f30dcef99fe0a0c34d512f
ms.sourcegitcommit: 787b198765565d54ee73972f664bdbd5023d666b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/24/2020
ms.locfileid: "46867188"
---
# <a name="anti-spam-message-headers-in-microsoft-365"></a>Intestazioni dei messaggi della protezione da posta indesiderata in Microsoft 365

In tutte le organizzazioni Microsoft 365, Exchange Online Protection (EOP) analizza tutti i messaggi in arrivo per identificare posta indesiderata, malware e altre minacce. I risultati di queste analisi vengono aggiunti a questi campi di intestazione nei messaggi:

- **X-Forefront-Antispam-Report**: contiene informazioni sul messaggio e sul modo in cui è stato elaborato.

- **X-Microsoft-Antispam**: fornisce informazioni aggiuntive sulla posta inviata in massa e il phishing.

- **Authentication-results**: contiene informazioni sui risultati delle autenticazioni della posta elettronica SPF, DKIM e DMARC.

Questo articolo descrive le caratteristiche disponibili in questi campi di intestazione.

Per informazioni sulla visualizzazione dell'intestazione di un messaggio di posta elettronica in diversi client di posta elettronica, vedere [Visualizzare le intestazioni dei messaggi Internet in Outlook](https://support.microsoft.com/office/cd039382-dc6e-4264-ac74-c048563d212c).

> [!TIP]
> È possibile copiare e incollare il contenuto dell’intestazione di un messaggio nello strumento [Analizzatore intestazione messaggio](https://mha.azurewebsites.net/). Questo strumento consente di analizzare le intestazioni e di inserirle in un formato più leggibile.

## <a name="x-forefront-antispam-report-message-header-fields"></a>Campi di intestazione del messaggio X-Forefront-Antispam-Report

Dopo aver trovato le informazioni sull’intestazione del messaggio, trovare l’intestazione **X-Forefront-Antispam-Report**. Nell'intestazione sono presenti più coppie di campi e di valori, separate da punti e virgola (;). Ad esempio:

`...CTRY:;LANG:hr;SCL:1;SRV:;IPV:NLI;SFV:NSPM;PTR:;CAT:NONE;SFTY:;...`

I campi e i valori sono descritti nel dettaglio nella tabella seguente.

> [!NOTE]
> L’intestazione **X-Forefront-Antispam-Report** contiene molti campi e valori. L'utilizzo dei campi non descritti nella tabella è riservato al team di protezione dalla posta indesiderata di Microsoft per finalità diagnostiche.

****

|Campo|Descrizione|
|---|---|
|`ARC`|I campi del protocollo `ARC` sono i seguenti: <ul><li>`AAR`: registra il contenuto dell'intestazione **Authentication-results** da DMARC.</li><li>`AMS`: contiene le firme crittografiche delle intestazioni dei messaggi.</li><li>`AS`: contiene le firme crittografiche delle intestazioni dei messaggi. Questo campo contiene il tag di convalida della catena denominata `"cv="` e include il risultato della convalida della catena, ad esempio **nessuna**, **superata**, o **non riuscita**.</li></ul>|
|`CAT:`|categoria dei criteri di protezione applicati al messaggio: <ul><li>`BULK`: invio in blocco</li><li>`DIMP`: imitazione del dominio</li><li>`GIMP`: [imitazione dell’utente basata su intercettazione della cassetta di posta](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies)</li><li>`HPHSH` o `HPHISH`: phishing con alta confidenza</li><li>`HSPM`: posta indesiderata con alta confidenza</li><li>`MALW`:malware</li><li>`PHSH`: phishing</li><li>`SPM`: posta indesiderata</li><li>`SPOOF`: spoofing</li><li>`UIMP`: imitazione dell'utente</li><li>`AMP`: antimalware</li><li>`SAP`: allegati sicuri</li><li>`OSPM`: posta indesiderata in uscita</li></ul><br/>Un messaggio in ingresso potrebbe essere contrassegnato in base a più forme di protezione e a più analisi di rilevamento. Ai criteri sono assegnate diverse priorità e il criterio con la priorità più alta viene applicato per primo. Per altre informazioni, vedere [Criteri applicabili ai messaggi di posta elettronica quando vengono usati più metodi di protezione e analisi di rilevamento](how-policies-and-protections-are-combined.md).|
|`CIP:[IP address]`|L'indirizzo IP che si connette. È possibile usare questo indirizzo IP nell'elenco Consenti indirizzi IP o nell'elenco Blocca indirizzi IP. Per ulteriori informazioni, vedere [Configurare il filtraggio delle connessioni](configure-the-connection-filter-policy.md).|
|`CTRY`|Il paese o l’area geografica di origine come determinato dall'indirizzo IP di connessione, il quale potrebbe non essere uguale all'indirizzo IP di invio di origine.|
|`H:[helostring]`|Stringa HELO o EHLO del server di posta elettronica connesso.|
|`IPV:CAL`|Il messaggio è stato ignorato dal filtro della posta indesiderata perché l'indirizzo IP di origine era riportato nell'elenco Consenti indirizzi IP. Per ulteriori informazioni, vedere [Configurare il filtraggio delle connessioni](configure-the-connection-filter-policy.md).|
|`IPV:NLI`|L'indirizzo IP non è stato trovato in nessuno degli elenchi di reputazione IP.|
|`LANG`|La lingua in cui è scritto il messaggio, come specificato dal codice paese (ad esempio, ru_RU per russo).|
|`PTR:[ReverseDNS]`|Il record PTR (noto anche come ricerca DNS inversa) dell'indirizzo IP di origine.|
|`SCL`|Il livello di probabilità di posta indesiderata (SCL) del messaggio. Più alto è il valore, maggiore è la probabilità che si tratti di un messaggio di posta indesiderata. Per ulteriori informazioni, vedere [Livello di probabilità di posta indesiderata (SCL)](spam-confidence-levels.md).|
|`SFTY`|Il messaggio è stato identificato come phishing e sarà anche contrassegnato con uno dei valori seguenti: <ul><li>9.1: valore predefinito. Il messaggio contiene alcuni o tutti gli elementi seguenti: un URL di phishing o altri contenuti di phishing, oppure è stato contrassegnato come phishing dalla distribuzione locale di Exchange.</li><li>9.11: [Spoofing interaziendale o self-to-self](anti-spoofing-protection.md#different-types-of-spoofing). Al messaggio verrà aggiunto il suggerimento per la sicurezza anti-spoofing intra-organizzazione.</li><li>9.19: imitazione del dominio. Il dominio di invio sta tentando di [sostituirsi a un dominio protetto](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies). Il suggerimento di sicurezza per l'imitazione dei domini viene aggiunto al messaggio (se abilitato).</li><li>9.20: imitazione dell'utente. Il mittente sta provando a imitare un utente nell'organizzazione del destinatario o un utente protetto specificato in un criterio anti-phishing di ATP. Il suggerimento di sicurezza per l'imitazione degli utenti viene aggiunto al messaggio (se abilitato).</li><li>9.21: [Spoofing tra domini](anti-spoofing-protection.md#different-types-of-spoofing). Il messaggio non ha superato i controlli anti-spoofing. Il dominio del mittente nell'intestazione Da non viene autenticato ed è un dominio esterno. Usato in combinazione con l'[autenticazione composita](#authentication-results-message-header-fields).</li><li>9.22: uguale a 9.21, ad eccezione del fatto che l'utente ha un mittente attendibile che è stato sovrascritto.</li><li>9.23: uguale a 9.22, ad eccezione del fatto che l'organizzazione ha un mittente o un dominio consentito che è stato sovrascritto.</li><li>9.24: uguale a 9.23, ad eccezione del fatto che l'utente ha una regola del flusso di posta di Exchange, nota anche come regola di trasporto, che è stata sovrascritta.</li></ul>|
|`SFV:BLK`|Il filtro è stato ignorato e il messaggio è stato bloccato, perché è stato inviato da un utente presente nell'elenco Mittenti bloccati di un utente.<br/></br> Per altre informazioni sul modo in cui gli amministratori possono gestire l'elenco dei mittenti bloccati di un utente, vedere [Configurare le impostazioni della posta indesiderata nelle cassette postali di Exchange Online](configure-junk-email-settings-on-exo-mailboxes.md).|
|`SFV:NSPM`|Il filtro della posta indesiderata ha contrassegnato il messaggio come non indesiderato, e il messaggio è stato inviato al destinatario.|
|`SFV:SFE`Il filtro è stato ignorato e il messaggio è stato lasciato passare, perché è stato inviato da un utente presente nell'elenco Mittenti attendibili di un utente.<br/></br> Per altre informazioni sul modo in cui gli amministratori possono gestire l'elenco dei mittenti attendibili di un utente, vedere [Configurare le impostazioni di posta indesiderata nelle cassette postali di Exchange Online](configure-junk-email-settings-on-exo-mailboxes.md).|
|`SFV:SKA`|Il messaggio è stato ignorato dal filtro della posta indesiderata ed è stato recapitato alla posta in arivo, perché il mittente era presente in un elenco di mittenti consentiti o di domini consentiti di un criterio di protezione dalla posta indesiderata. Per altre informazioni, vedere [Configurare i criteri di protezione dalla posta indesiderata](configure-your-spam-filter-policies.md).|
|`SFV:SKB`|Il messaggio è stato contrassegnato come posta indesiderata perché corrisponde a un mittente presente in un elenco di mittenti o domini bloccati in un criterio di protezione dalla posta indesiderata. Per altre informazioni, vedere [Configurare i criteri di protezione dalla posta indesiderata](configure-your-spam-filter-policies.md).|
|`SFV:SKI`|Come per SFV:SKN, il messaggio ha ignorato il filtro posta indesiderata per un altro motivo, ad esempio perché si tratta di posta elettronica tra organizzazioni all'interno di un tenant.|
|`SFV:SKN`|Il messaggio è stato contrassegnato come posta non indesiderata prima di essere elaborato dal filtro della posta indesiderata. Ad esempio, il messaggio è stato contrassegnato come SCL -1 o **Ignora filtro posta indesiderata** da una regola del flusso di posta.|
|`SFV:SKQ`|Il messaggio è stato rilasciato dalla quarantena ed è stato inviato al destinatario.|
|`SFV:SKS`|Il messaggio è stato contrassegnato come posta indesiderata prima di essere elaborato dal filtro della posta indesiderata. Ad esempio, il messaggio è stato contrassegnato come SCL 5-9 da una regola del flusso di posta.|
|`SFV:SPM`|Il messaggio è stato contrassegnato come posta indesiderata dal filtro della posta indesiderata.|
|`SRV:BULK`|Il messaggio è stato identificato come posta elettronica in blocco dal filtro posta indesiderata e dalla soglia del livello di reclamo in blocco. Se il parametro _MarkAsSpamBulkMail_ è `On`, ed è attivato per impostazione predefinita, un messaggio di posta elettronica in blocco viene contrassegnato come alta probabilità di posta indesiderata (SCL 9). Per altre informazioni, vedere [Configurare i criteri di protezione dalla posta indesiderata](configure-your-spam-filter-policies.md).|
|`X-CustomSpam: [ASFOption]`|Il messaggio corrisponde a un'impostazione di filtro avanzato della posta indesiderata (ASF). Per vedere il valore X-header per ogni impostazione ASF, consultare le [Impostazioni di filtro avanzato della posta indesiderata (ASF)](advanced-spam-filtering-asf-options.md).|
|

## <a name="x-microsoft-antispam-message-header-fields"></a>Campi di intestazione del messaggio X-Microsoft-Antispam

Nella tabella seguente vengono descritti i campi utili nell'intestazione del messaggio **X-Microsoft-Antispam**. L'utilizzo degli altri campi dell'intestazione è riservato al team di protezione dalla posta indesiderata di Microsoft per scopi di diagnostica.

****

|Campo|Descrizione|
|---|---|
|`BCL`|Il Livello di reclamo in blocco (BCL) del messaggio. Più il BCL è elevato, maggiore è la probabilità che un messaggio di posta elettronica in blocco generi reclami, ed è quindi più probabile che si tratti di posta indesiderata. Per ulteriori informazioni, vedere [Livello di reclamo in blocco (BCL)](bulk-complaint-level-values.md).|
|

## <a name="authentication-results-message-header"></a>Intestazione del messaggio Authentication-results

I risultati dei controlli dell'autenticazione della posta elettronica per SPF, DKIM e DMARC sono registrati (stampati) nell'intestazione **Authentication-results** dei messaggi in ingresso.

L'elenco che segue descrive il testo che viene aggiunto all'intestazione **Authentication-Results** per ogni tipo di controllo dell'autenticazione:

- SPF utilizza la sintassi seguente:

  ```text
  spf=<pass (IP address)|fail (IP address)|softfail (reason)|neutral|none|temperror|permerror> smtp.mailfrom=<domain>
  ```

  Ad esempio:

  ```text
  spf=pass (sender IP is 192.168.0.1) smtp.mailfrom=contoso.com
  spf=fail (sender IP is 127.0.0.1) smtp.mailfrom=contoso.com
  ```

- DKIM utilizza la sintassi seguente:

  ```text
  dkim=<pass|fail (reason)|none> header.d=<domain>
  ```

  Ad esempio:

  ```text
  dkim=pass (signature was verified) header.d=contoso.com
  dkim=fail (body hash did not verify) header.d=contoso.com
  ```

- DMARC utilizza la sintassi seguente:

  ```text
  dmarc=<pass|fail|bestguesspass|none> action=<permerror|temperror|oreject|pct.quarantine|pct.reject> header.from=<domain>
  ```

  Ad esempio:

  ```text
  dmarc=pass action=none header.from=contoso.com
  dmarc=bestguesspass action=none header.from=contoso.com
  dmarc=fail action=none header.from=contoso.com
  dmarc=fail action=oreject header.from=contoso.com
  ```

### <a name="authentication-results-message-header-fields"></a>Campi dell'intestazione del messaggio Authentication-results

Nella tabella seguente vengono descritti i campi e i valori possibili per il controllo di autenticazione di ogni messaggio di posta elettronica.

****

|Campo|Descrizione|
|---|---|
|`action`|Indica l'azione eseguita dal filtro posta indesiderata in base ai risultati del controllo DMARC. Ad esempio: <ul><li>**oreject** o **o.reject**: abbreviazione di override reject (rifiuto override). In questo caso, Microsoft 365 usa questa azione quando riceve un messaggio che non supera il controllo DMARC da un dominio il cui record TXT DMARC ha un criterio di p=reject. Anziché eliminare o rifiutare il messaggio, Microsoft 365 lo contrassegna come posta indesiderata. Per ulteriori informazioni sul motivo per cui Microsoft 365 è configurato in questo modo, vedere [Come viene gestita la posta elettronica in ingresso che non supera il controllo DMARC in Microsoft 365](use-dmarc-to-validate-email.md#how-microsoft-365-handles-inbound-email-that-fails-dmarc).</li><li>**pct.quarantine**: indica che una percentuale inferiore al 100% di messaggi che non superano il controllo DMARC verrà recapitata comunque. Ciò significa che il messaggio non ha superato il controllo DMARC e il criterio è stato impostato su quarantine, ma il campo pct non è stato impostato su 100% e il sistema ha determinato in modo casuale di non applicare l'azione DMARC, in base al criterio del dominio specificato.</li><li>**pct.reject**: indica che una percentuale inferiore al 100% di messaggi che non superano il controllo DMARC verrà recapitata comunque. Ciò significa che il messaggio non ha superato il controllo DMARC e il criterio è stato impostato su reject, ma il campo pct non è stato impostato su 100% e il sistema ha determinato in modo casuale di non applicare l'azione DMARC, in base al criterio del dominio specificato.</li><li>**permerror**: si è verificato un errore permanente durante la valutazione DMARC, ad esempio è stato trovato un record TXT DMARC con formato non valido in DNS. Tentando di inviare di nuovo questo messaggio, probabilmente si otterrebbe un risultato diverso. Al contrario, potrebbe essere necessario contattare il proprietario del dominio per risolvere il problema.</li><li>**temperror**: si è verificato un errore temporaneo durante la valutazione DMARC. Potrebbe essere possibile richiedere che il mittente invii il messaggio in un secondo momento per elaborare il messaggio correttamente.</li></ul>|
|`compauth`|Risultato autenticazione composita. Viene usato da Microsoft 365 per combinare più tipi di autenticazione, come SPF, DKIM, DMARC o qualsiasi altra parte del messaggio, per determinare se il messaggio è stato autenticato o meno. Usa il dominio Da: come base per la valutazione.|
|`dkim`|Descrive i risultati del controllo DKIM per il messaggio. Tra i possibili valori sono inclusi:<ul><li>**pass**: indica che il controllo DKIM per il messaggio è stato superato.</li><li>**fail (motivo)**: indica che il controllo DKIM per il messaggio non è stato superato e include il motivo, ad esempio se il messaggio non è stato firmato o se la firma non è stata verificata.</li><li>**none**: indica che il messaggio non è stato firmato. Ciò potrebbe indicare o meno che il dominio dispone di un record DKIM o che il record DKIM non restituisce un risultato, solo che il messaggio non è stato firmato.</li></ul>|
|`dmarc`|Descrive i risultati del controllo DMARC per il messaggio. Tra i possibili valori sono inclusi:<ul><li>**pass**: indica che il controllo DMARC per il messaggio è stato superato.</li><li>**fail**: indica che il controllo DMARC per il messaggio non è stato superato.</li><li>**bestguesspass**: indica che non esistono record TXT DMARC per il dominio, ma che se ne esistesse uno, il controllo DMARC per il messaggio sarebbe stato superato. Questo è dovuto al fatto che il dominio nell'indirizzo `5321.MailFrom`, noto anche come indirizzo posta mittente, mittente P1 o mittente della busta, corrisponde al dominio nell'indirizzo `5322.From`, anche noto come indirizzo mittente o mittente P2.</li><li>**none**: indica che non esistono record TXT DMARC per il dominio di invio in DNS.|
|`header.d`|Dominio identificato nella firma DKIM, se presente. Questo è il dominio sottoposto a query per la chiave pubblica.|
|`header.from`|Il dominio dell'indirizzo `5322.From` nell'intestazione del messaggio di posta elettronica, anche noto come indirizzo mittente o mittente P2. Il destinatario vede l'indirizzo mittente nei client di posta elettronica.|
|`reason`|Il motivo per cui l'autenticazione composita è stata superata o meno. Il valore è un codice a 3 cifre. Ad esempio: <ul><li>**000**: il messaggio non ha superato l'autenticazione esplicita (`compauth=fail`). Ad esempio, il messaggio ha ricevuto un errore di DMARC con un'azione di quarantena o rifiuto.</li><li>**001** il messaggio non ha superato l'autenticazione implicita (`compauth=fail`). Questo significa che il dominio mittente non aveva record di posta elettronica pubblicati o, se li aveva, i criteri di errore erano meno stringenti (SPF softfail o neutro, criterio DMARC `p=none`).</li><li>**002**: l'organizzazione ha un criterio per la coppia mittente/dominio che vieta esplicitamente l'invio di messaggi di posta elettronica contraffatti. Questa impostazione viene impostata manualmente da un amministratore.</li><li>**010**: il messaggio non ha superato la verifica DMARC con un'azione di rifiuto o quarantena e il dominio di invio è uno dei domini accettati dell'organizzazione (questo fa parte dello spoofing self-to-self o intra-organizzazione).</li><li>**1xx** o **7xx**: il messaggio ha superato l'autenticazione (`compauth=pass`). Le ultime due cifre sono codici interni usati da Microsoft 365.</li><li>**2xx**: il messaggio ha superato l'autenticazione implicita (`compauth=softpass`). Le ultime due cifre sono codici interni usati da Microsoft 365.</li><li>**3xx**: il messaggio non è stato controllato per l'autenticazione composita (`compauth=none`).</li><li>**4xx** o **9xx**: il messaggio ha ignorato l'autenticazione composita (`compauth=none`). Le ultime due cifre sono codici interni usati da Microsoft 365.</li><li>**6xx**: il messaggio non ha superato l'autenticazione implicita della posta elettronica e il dominio di invio è uno dei domini accettati dell'organizzazione (questo fa parte dello spoofing self-to-self o intra-organizzazione).</li></ul>|
|`smtp.mailfrom`|Il dominio dell'indirizzo `5321.MailFrom`, anche noto come indirizzo posta mittente, mittente P1 o mittente della busta. Si tratta dell'indirizzo di posta elettronica usato per i report di mancato recapito, noti anche come NDR o notifiche di mancato recapito.|
|`spf`|Descrive i risultati del controllo SPF per il messaggio. I valori possibili includono: <ul><li>`pass (IP address)`: il controllo SPF per il messaggio è stato superato e include l'indirizzo IP del mittente. Il client è autorizzato a inviare o inoltrare la posta elettronica per conto del dominio del mittente.</li><li>`fail (IP address)`: indica che il controllo SPF per il messaggio non è stato superato e include l'indirizzo IP del mittente. Talvolta viene definito controllo di tipo _hard fail_.</li><li>`softfail (reason)`: indica che il record SPF ha designato l'host come non autorizzato all'invio ma in transizione.</li><li>`neutral`: il record SPF indica esplicitamente che non afferma se l'indirizzo IP sia autorizzato a inviare.</li><li>`none`: il dominio non ha un record SPF, o il record SPF non restituisce un risultato.</li><li>`temperror`: si è verificato un errore temporaneo. Ad esempio, un errore DNS. Il medesimo controllo potrebbe avere esito positivo in seguito.</li><li>`permerror`: si è verificato un errore permanente. Ad esempio, il dominio presenta un record SPF con formato non valido.</li></ul>|
|
