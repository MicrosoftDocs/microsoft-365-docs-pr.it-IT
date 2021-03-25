---
title: Visualizzazioni della campagna in Microsoft Defender per Office 365 Plan
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: mcostea
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Informazioni sulle visualizzazioni campagna in Microsoft Defender per Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e3c84b9e6253dd813ff930314fc2c1d0a947e94e
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205085"
---
# <a name="campaign-views-in-microsoft-defender-for-office-365"></a>Visualizzazioni della campagna in Microsoft Defender per Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Microsoft Defender per Office 365 Piano 2](defender-for-office-365.md)

Visualizzazioni campagna è una funzionalità di Microsoft Defender per Office 365 Piano 2 (ad esempio Microsoft 365 E5 o organizzazioni con un componente aggiuntivo Defender per Office 365 Piano 2). Visualizzazioni campagna nel Centro sicurezza & conformità identifica e categorizza gli attacchi di phishing nel servizio. Visualizzazione campagne consente di:

- Analizzare e rispondere in modo efficiente agli attacchi di phishing.
- Comprendere meglio la portata dell'attacco.
- Visualizzare i dettagli dell'attacco.

Visualizzazione campagne fornisce una visione d'insieme di un attacco in maniera più rapida e completa rispetto a un processo manuale.

## <a name="what-is-a-campaign"></a>Cos'è una campagna?

Una campagna è un attacco coordinato perpetrato tramite posta elettronica contro una o più organizzazioni. Gli attacchi tramite posta elettronica che rubano credenziali e dati aziendali sono un settore di grandi dimensioni e lucrativo. Con l'aumentare delle tecnologie nel tentativo di arrestare gli attacchi, gli utenti malintenzionati modificano i propri metodi per garantire il successo continuo.

Microsoft sfrutta le grandi quantità di dati anti-phishing, posta indesiderata e antimalware nell'intero servizio per identificare le campagne. Analizziamo e classifichiamo le informazioni sugli attacchi in base a diversi fattori. Ad esempio:

- **Origine dell'attacco:** gli indirizzi IP di origine e i domini di posta elettronica del mittente.
- **Proprietà messaggio**: contenuto, stile e tono dei messaggi.
- **Destinatari del** messaggio: come sono correlati i destinatari. Ad esempio, domini destinatario, funzioni di lavoro dei destinatari (amministratori, dirigenti e così via), tipi di società (grandi, piccoli, pubblici, privati e così via) e settori.
- **Payload di** attacco: collegamenti dannosi, allegati o altri payload nei messaggi.

Una campagna può essere di breve durata o può estendersi per diversi giorni, settimane o mesi con periodi attivi e inattivi. È possibile che venga avviata una campagna per l'organizzazione specifica oppure che l'organizzazione sia parte di una campagna più ampia tra più società.

## <a name="campaign-views-in-the-security--compliance-center"></a>Visualizzazioni della campagna nel Centro sicurezza & conformità

Visualizzazioni campagna è disponibile nel [Centro sicurezza & conformità](https://protection.office.com) in **Campagne** di gestione delle \> **minacce** o direttamente all'indirizzo <https://protection.office.com/campaigns> .

![Panoramica della campagna nel Centro sicurezza e conformità](../../media/campaigns-overview.png)

Puoi anche accedere a Visualizzazioni campagna da:

- **Gestione delle minacce** \> **Explorer** \> **Visualizza** \> **Campagne**
- **Gestione delle minacce** \> **Explorer** \> **Visualizza** \> **Tutti i messaggi di posta elettronica** \> **Scheda** Campagna
- **Gestione delle minacce** \> **Explorer** \> **Visualizza** \> **Phish** \> **Scheda** Campagna
- **Gestione delle minacce** \> **Explorer** \> **Visualizza** \> **Malware** \> **Scheda** Campagna

Per accedere a Visualizzazioni campagna, è necessario essere membri  dei gruppi di ruoli Gestione **organizzazione,** Amministratore sicurezza o Lettore sicurezza nel Centro sicurezza & conformità. Per altre informazioni, vedere [Autorizzazioni nel Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).

## <a name="campaigns-overview"></a>Panoramica delle campagne

La pagina di panoramica mostra informazioni su tutte le campagne.

Nella scheda **campagna predefinita,** l'area **Tipo di** campagna mostra un grafico a barre che mostra il numero di destinatari al giorno. Per impostazione predefinita, il grafico mostra **sia i dati phish** che **i dati di malware.**

> [!TIP]
> Se non vengono visualizzati dati della campagna, provare a modificare l'intervallo di date o i [filtri](#filters-and-settings).

Il resto della pagina di panoramica mostra le informazioni seguenti nella **scheda** Campagna:

- **Nome**

- **Esempio di oggetto**: oggetto di uno dei messaggi della campagna. Tieni presente che tutti i messaggi della campagna non avranno necessariamente lo stesso oggetto.

- **Mirato**: percentuale calcolata da: (il numero di destinatari della campagna nell'organizzazione) / (il numero totale di destinatari nella campagna in tutte le organizzazioni nel servizio). Questo valore indica il grado in cui la campagna viene indirizzata solo all'organizzazione (un valore superiore) e anche ad altre organizzazioni nel servizio (un valore inferiore).

- **Type**: Questo valore è **Phish** o **Malware.**

- **Sottotipo:** questo valore contiene ulteriori dettagli sulla campagna. Ad esempio:
  - **Phish:** se disponibile, il marchio che viene phished da questa campagna. Ad esempio, `Microsoft` , , , o `365` `Unknown` `Outlook` `DocuSign` .
  - **Malware**: ad esempio, `HTML/PHISH` o `HTML/<MalwareFamilyName>` .

  Se disponibile, il marchio di cui viene fatto phishing da questa campagna. Quando il rilevamento è guidato dalla tecnologia Defender per Office 365, il prefisso **ATP-** viene aggiunto al valore del sottotipo.

- **Destinatari**: il numero di utenti oggetti dell'attacco della campagna.

- **Posta in** arrivo : Numero di utenti che hanno ricevuto messaggi da questa campagna nella posta in arrivo (non recapitati nella cartella Posta indesiderata).

- **Clicked**: Numero di utenti che hanno fatto clic sull'URL o hanno aperto l'allegato nel messaggio di phishing.

- **Frequenza clic**: percentuale calcolata da " Posta in arrivo su cui **è stato fatto** clic  /  ". Questo valore è un indicatore dell'efficacia della campagna. In altre parole, se i destinatari sono stati in grado di identificare il messaggio come phishing e se non hanno fatto clic sull'URL del payload.

  Tieni presente **che la frequenza** di clic non viene usata nelle campagne di malware.

- **Visitato**: numero di utenti che hanno effettivamente effettuato l'accesso al sito Web del payload. Se sono presenti **valori Clicked,** ma collegamenti sicuri bloccano l'accesso al sito Web, questo valore sarà zero.

La **scheda Origine** campagna mostra le origini dei messaggi su una mappa del mondo.

### <a name="filters-and-settings"></a>Filtri e impostazioni

Nella parte superiore della pagina Visualizzazioni campagna sono disponibili diverse impostazioni di filtro e query che consentono di individuare e isolare campagne specifiche.

![Filtri campagna](../../media/campaign-filters-and-settings.png)

Il filtro di base che è possibile eseguire è data/ora di inizio e data/ora di fine.

Per filtrare ulteriormente la visualizzazione, è possibile eseguire un'unica proprietà con più valori filtrando facendo clic sul pulsante **Tipo** di campagna, effettuando la selezione e quindi facendo clic su **Aggiorna.**

Le proprietà filtrabili della campagna disponibili nel pulsante **Tipo di** campagna sono descritte nell'elenco seguente:

- **Basic**:
  - **Tipo di campagna:** selezionare **Malware** **o Phish.** La cancellazione delle selezioni ha lo stesso risultato della selezione di entrambe.
  - **Nome campagna**
  - **Sottotipo campagna**
  - **Mittente**
  - **Destinatari**
  - **Dominio del mittente**
  - **Oggetto**
  - **Nome file allegato**
  - **Famiglia di malware**
  - **Tag**: utenti o gruppi a cui è stato applicato il tag utente specificato (inclusi gli account di priorità). Per ulteriori informazioni sui tag utente, vedere [Tag utente](user-tags.md).
  - **Sostituzioni di sistema**
  - **Azione di recapito**
  - **Azione aggiuntiva**
  - **Direzionalità**
  - **Tecnologia di rilevamento**
  - **Percorso di recapito originale**
  - **Posizione di recapito più recente**
  - **Sostituzioni di sistema**

- **Avanzate**:
  - **ID messaggio Internet**: Disponibile nel **campo di intestazione Message-ID** nell'intestazione del messaggio. Un valore di esempio è `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (si notino le parentesi angolari).
  - **ID messaggio di** rete : valore GUID disponibile nel campo di intestazione **X-MS-Exchange-Organization-Network-Message-Id** nell'intestazione del messaggio.
  - **Indirizzo IP mittente**
  - **Allegato SHA256**: Per trovare il valore hash SHA256 di un file in Windows, eseguire il comando seguente in un prompt dei comandi: `certutil.exe -hashfile "<Path>\<Filename>" SHA256` .
  - **Cluster ID**
  - **ID criterio avviso**
  - **Segnale URL ZAP**

- **URL**:
  - **Dominio URL**
  - **Percorso e dominio URL**
  - **URL**
  - **Percorso URL**
  - **Fare clic su verdetto**

Per un filtro più avanzato, incluso il filtro in base a più proprietà, è possibile fare clic sul **pulsante Filtro** avanzato per creare una query. Sono disponibili le stesse proprietà della campagna, ma con i miglioramenti seguenti:

- È possibile fare **clic su Aggiungi una condizione** per selezionare più condizioni.
- È possibile scegliere **l'operatore And** **o Or** tra le condizioni.
- È possibile selezionare **l'elemento Gruppo di** condizioni nella parte inferiore dell'elenco delle condizioni per formare condizioni composte complesse.

Al termine, fare clic sul **pulsante Query.**

Dopo aver creato un filtro di base o avanzato, è possibile salvarlo utilizzando **Salva query** o Salva query **con nome.** In seguito, quando si torna a Visualizzazioni campagna, è possibile caricare un filtro salvato facendo clic su **Impostazioni query salvate.**

Per esportare il grafico o l'elenco delle campagne, fare clic **su** Esporta e selezionare **Esporta dati grafico** o Esporta elenco **campagne.**

Se si dispone di un abbonamento a Microsoft Defender for Endpoint, è possibile fare clic su **Impostazioni MDE** per connettere o disconnettere le informazioni sulle campagne con Microsoft Defender for Endpoint. Per ulteriori informazioni, vedere [Integrare Microsoft Defender per Office 365 con Microsoft Defender for Endpoint.](integrate-office-365-ti-with-mde.md)

## <a name="campaign-details"></a>Dettagli campagna

Quando fai clic sul nome di una campagna, i dettagli della campagna vengono visualizzati in un riquadro a comparsa.

### <a name="campaign-information"></a>Informazioni campagna

Nella parte superiore della visualizzazione dei dettagli della campagna sono disponibili le informazioni seguenti:

- **ID**: Identificatore univoco della campagna.

- **Inizio** e **Fine**: data di inizio e data di fine della campagna. Si noti che queste date potrebbero estendersi oltre le date di filtro selezionate nella pagina di panoramica.

- **Impatto**: questa sezione contiene i dati seguenti per il filtro dell'intervallo di date selezionato (o selezionato nella sequenza temporale):
  - Numero totale di destinatari.
  - Il numero di messaggi che sono stati "posta in arrivo" (ovvero recapitati nella posta in arrivo, non nella cartella Posta indesiderata).
  - Numero di utenti che hanno fatto clic sul payload dell'URL nel messaggio di phishing.
  - Numero di utenti che hanno visitato l'URL.

- **Mirato**: percentuale calcolata da: (il numero di destinatari della campagna nell'organizzazione) / (il numero totale di destinatari nella campagna in tutte le organizzazioni nel servizio). Tieni presente che questo valore viene calcolato per l'intera durata della campagna e non cambia in base ai filtri di data.

- Una sequenza temporale interattiva dell'attività della campagna: la sequenza temporale mostra l'attività per l'intera durata della campagna. Per impostazione predefinita, l'area ombreggiata include il filtro dell'intervallo di date selezionato nella panoramica. È possibile fare clic e trascinare per selezionare un punto iniziale e un punto finale specifici, che modificheranno i dati visualizzati <u>nell'area  </u>Impatto e nel resto della pagina, come descritto nelle sezioni successive.

Nella barra del titolo è  possibile fare clic sul pulsante Scarica scrittura campagna Icona di scrittura campagna per scaricare i dettagli della campagna in un documento di Word (per impostazione ![ ](../../media/download-campaign-write-up-button.png) predefinita, denominato CampaignReport.docx). Tieni presente che il download contiene dettagli per l'intera durata della campagna (non solo le date di filtro selezionate).

![Informazioni campagna](../../media/campaign-details-campaign-info.png)

### <a name="campaign-flow"></a>Flusso della campagna

Nella parte centrale della visualizzazione dei dettagli della campagna vengono presentati dettagli importanti sulla campagna nella sezione **Flusso** di un diagramma di flusso orizzontale (noto come _diagramma di Sankey)._ Questi dettagli aiuteranno a comprendere gli elementi della campagna e il potenziale impatto sull'organizzazione.

> [!TIP]
> Le informazioni visualizzate nel diagramma  di flusso sono controllate dall'intervallo di date ombreggiato nella sequenza temporale, come descritto nella sezione precedente.

![Dettagli della campagna che non contengono clic sull'URL da parte dell'utente](../../media/campaign-details-no-recipient-actions.png)

Se si passa il mouse su una fascia orizzontale nel diagramma, viene visualizzato il numero di messaggi correlati (ad esempio i messaggi provenienti da un determinato IP di origine, i messaggi provenienti dall'IP di origine con il dominio del mittente specificato e così via).

Il diagramma include le seguenti informazioni:

- **Indirizzi IP mittenti**
- **Domini mittenti**
- **Verdetti del filtro**: I valori verditti sono correlati ai verdetti disponibili per il filtro di phishing e posta indesiderata, come descritto in Intestazioni dei messaggi di [posta indesiderata.](anti-spam-message-headers.md) I valori disponibili sono descritti nella tabella seguente:

  ****

  |Valore|Verdetto del filtro posta indesiderata|Descrizione|
  |---|---|---|
  |**Consentito**|`SFV:SKN` <p> `SFV:SKI`|Il messaggio è stato contrassegnato come non posta indesiderata e/o è stato ignorato prima di essere valutato dal filtro posta indesiderata. Ad esempio, il messaggio è stato contrassegnato come non posta indesiderata da una regola del flusso di posta (nota anche come regola di trasporto). <p> Il messaggio ha ignorato il filtro posta indesiderata per altri motivi. Ad esempio, il mittente e il destinatario sembrano essere nella stessa organizzazione.|
  |**Bloccato**|`SFV:SKS`|Il messaggio è stato contrassegnato come posta indesiderata prima di essere valutato dal filtro posta indesiderata. Ad esempio, tramite una regola del flusso di posta.|
  |**Rilevato**|`SFV:SPM`|Il messaggio è stato contrassegnato come posta indesiderata dal filtro della posta indesiderata.|
  |**Non rilevato**|`SFV:NSPM`|Il messaggio è stato contrassegnato come non posta indesiderata dal filtro posta indesiderata.|
  |**Rilasciato**|`SFV:SKQ`|Il messaggio ha ignorato il filtro posta indesiderata perché è stato rilasciato dalla quarantena.|
  |**Tenant Allow**<sup>\*</sup>|`SFV:SKA`|Il messaggio ha ignorato il filtro posta indesiderata a causa delle impostazioni di un criterio di protezione da posta indesiderata. Ad esempio, il mittente era nell'elenco dei mittenti consentiti o nell'elenco dei domini consentiti.|
  |**Blocco tenant**<sup>\*\*</sup>|`SFV:SKA`|Il messaggio è stato bloccato dal filtro posta indesiderata a causa delle impostazioni di un criterio di protezione da posta indesiderata. Ad esempio, il mittente era nell'elenco dei mittenti consentiti o nell'elenco dei domini consentiti.|
  |**Consenti utente**<sup>\*</sup>|`SFV:SFE`|Il messaggio ha ignorato il filtro posta indesiderata perché il mittente era in un elenco Mittenti attendibili di un utente.|
  |**Blocco utente**<sup>\*\*</sup>|`SFV:BLK`|Il messaggio è stato bloccato dal filtro posta indesiderata perché il mittente era in un elenco Mittenti bloccati di un utente.|
  |**ZAP**|n/d|L'eliminazione automatica di zero [ore (ZAP)](zero-hour-auto-purge.md) ha spostato il messaggio recapitato nella cartella Posta indesiderata o in quarantena. L'azione viene configurata nei criteri di protezione da posta indesiderata.|
  |

  <sup>\*</sup> Esaminare i criteri di protezione da posta indesiderata, perché il messaggio consentito sarebbe stato probabilmente bloccato dal servizio.

  <sup>\*\*</sup> Esaminare i criteri di protezione da posta indesiderata, perché questi messaggi devono essere messi in quarantena, non recapitati.

- **Percorsi di** recapito : è probabile che si desideri analizzare i messaggi recapitati ai destinatari (nella cartella Posta in arrivo o Posta indesiderata), anche se gli utenti non hanno fatto clic sull'URL del payload nel messaggio. È inoltre possibile rimuovere i messaggi in quarantena dalla quarantena. Per ulteriori informazioni, vedere [Quarantined email messages in EOP](quarantine-email-messages.md).
  - **Cartella eliminata**
  - **Rilasciato**
  - **Esterno**: il destinatario si trova nell'organizzazione di posta elettronica locale in ambienti ibridi.
  - **Operazione non riuscita**
  - **Inoltrato**
  - **Posta in arrivo**
  - **Posta indesiderata**
  - **Quarantena**
  - **Unknown**

- **Clic url:** questi valori sono descritti nella sezione successiva.

> [!NOTE]
> In tutti i layer che contengono più di 10 elementi, vengono visualizzati i primi 10 elementi, mentre gli altri sono raggruppati in **Altri**.

#### <a name="url-clicks"></a>Clic URL

Quando un messaggio di phishing viene recapitato nella cartella Posta in arrivo o Posta indesiderata di un destinatario, è sempre possibile che l'utente clic sull'URL del payload. Non fare clic sull'URL è una piccola misura di successo, ma è necessario determinare perché il messaggio di phishing è stato persino recapitato alla cassetta postale.

Se un utente ha fatto clic sull'URL del payload nel messaggio di phishing, le azioni vengono visualizzate nell'area dei clic **sull'URL** del diagramma nella visualizzazione dei dettagli della campagna.

- **Consentito**
- **BlockPage**: il destinatario ha fatto clic sull'URL del payload, ma l'accesso al sito Web dannoso è stato bloccato da un criterio [Collegamenti](safe-links.md) sicuri nell'organizzazione.
- **BlockPageOverride:** il destinatario ha fatto clic sull'URL del payload nel messaggio, i collegamenti sicuri hanno tentato di interromperli, ma gli è stato consentito ignorare il blocco. Esaminare i [criteri collegamenti sicuri](set-up-safe-links-policies.md) per vedere perché agli utenti è consentito ignorare il verdetto Collegamenti sicuri e continuare con il sito Web dannoso.
- **PendingDetonationPage:** allegati sicuri in Microsoft Defender per Office 365 è in corso di apertura e analisi dell'URL del payload in un ambiente di computer virtuale.
- **PendingDetonationPageOverride**: al destinatario è stato consentito eseguire l'override del processo di detonazione del payload e aprire l'URL senza attendere i risultati.

### <a name="tabs"></a>Schede

Le schede nella visualizzazione dei dettagli della campagna consentono di analizzare ulteriormente la campagna.

> [!TIP]
> Le informazioni visualizzate nelle schede sono controllate dall'intervallo di date ombreggiato nella sequenza temporale, come descritto nella [sezione Informazioni sulla](#campaign-information) campagna.

- **Clic url:** se gli utenti non hanno fatto clic sull'URL del payload nel messaggio, questa sezione sarà vuota. Se un utente è stato in grado di fare clic sull'URL, verranno popolati i valori seguenti:
  - **Utente:**<sup>\*</sup>
  - **URL**<sup>\*</sup>
  - **Ora clic**
  - **Fare clic su verdetto**

- **Indirizzi IP mittenti**
  - **Indirizzo IP mittente**<sup>\*</sup>
  - **Conteggio totale**
  - **Posta in arrivo**
  - **Non in arrivo**
  - **SPF superato:** il mittente è stato autenticato da [Sender Policy Framework (SPF).](how-office-365-uses-spf-to-prevent-spoofing.md) Un mittente che non supera la convalida SPF indica un mittente non autenticato o il messaggio sta falsificando un mittente legittimo.

- **Mittenti**
  - **Sender**: Si tratta dell'indirizzo effettivo del mittente nel comando SMTP MAIL FROM, che non è necessariamente l'indirizzo di posta elettronica From: visualizzato dagli utenti nei client di posta elettronica.
  - **Conteggio totale**
  - **Posta in arrivo**
  - **Non in arrivo**
  - **DKIM superato:** il mittente è stato autenticato da [Domain Keys Identified Mail (DKIM).](support-for-validation-of-dkim-signed-messages.md) Un mittente che non supera la convalida DKIM indica un mittente non autenticato o il messaggio sta effettuando lo spoofing di un mittente legittimo.
  - **DMARC superato:** il mittente è stato autenticato da [DMARC (Domain-based Message Authentication, Reporting, and Conformance)](use-dmarc-to-validate-email.md). Un mittente che non supera la convalida DMARC indica un mittente non autenticato o il messaggio sta effettuando lo spoofing di un mittente legittimo.

- **Allegati**
  - **Filename**
  - **SHA256**
  - **Famiglia di malware**
  - **Conteggio totale**

- **URL**
  - **URL**<sup>\*</sup>
  - **Conteggio totale**

<sup>\*</sup> Se si fa clic su questo valore, viene aperto un nuovo riquadro a comparsa che contiene altri dettagli sulla voce specificata (utente, URL e così via) nella parte superiore della visualizzazione dei dettagli della campagna. Per tornare alla visualizzazione dei dettagli della campagna, fare clic su **Chiudi** nel nuovo riquadro a comparsa.

### <a name="buttons"></a>Pulsanti

I pulsanti nella visualizzazione dei dettagli della campagna consentono di usare la potenza di Esplora minacce per approfondire la campagna.

- **Esplora minacce**: apre una nuova scheda di ricerca in Esplora minacce usando il valore **ID campagna** come filtro di ricerca.
- **Esplora i messaggi in arrivo**: apre una nuova scheda di ricerca di Threat Explorer usando **l'ID campagna** e la posizione di **recapito: Posta** in arrivo come filtro di ricerca.
