---
title: Visualizzazioni della campagna in ATP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: mcostea
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Informazioni su Visualizzazione campagne in Office 365 Advanced Threat Protection.
ms.openlocfilehash: fe443c43fa5cea8ec6e3e1c0bc5ee5307b5c28f6
ms.sourcegitcommit: 9ee1261c405f82b49c62390a25dfdea23340d644
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/06/2020
ms.locfileid: "45039483"
---
# <a name="campaign-views-in-atp"></a>Visualizzazioni della campagna in ATP

La visualizzazione della campagna è una funzionalità di Advanced Threat Protection (ATP) nel centro sicurezza & Compliance che identifica e categorizza gli attacchi di phishing nel servizio. Visualizzazione campagne consente di:

- Analizzare e rispondere in modo efficiente agli attacchi di phishing.

- Comprendere meglio la portata dell'attacco.

- Visualizzare i dettagli dell'attacco.

Visualizzazione campagne fornisce una visione d'insieme di un attacco in maniera più rapida e completa rispetto a un processo manuale.

## <a name="what-is-a-campaign"></a>Cos'è una campagna?

Una campagna è un attacco coordinato perpetrato tramite posta elettronica contro una o più organizzazioni. Gli attacchi tramite posta elettronica che rubano le credenziali e i dati aziendali rappresentano un settore importante e redditizio. Man mano che le tecnologie aumentano nel tentativo di arrestare gli attacchi, gli aggressori modificano i propri metodi nel tentativo di garantire il successo continuativo.

Microsoft sfrutta la vasta quantità di dati antiphishing, di protezione dalla posta indesiderata e antimalware in tutto il servizio per facilitare l'identificazione delle campagne. Vengono analizzate e classificate le informazioni sull'attacco in base a diversi fattori. Ad esempio:

- **Origine attacco**: gli indirizzi IP di origine e i domini di posta elettronica del mittente.

- **Proprietà del messaggio di attacco**: contenuto, stile e tono dei messaggi.

- **Destinatari dell'attacco**: domini dei destinatari, funzione aziendale dei destinatari (amministratori, dirigenti e così via), tipi di azienda (grandi, piccole, pubbliche, private e così via) e settori.

- **Payload di attacco**: collegamenti dannosi, allegati o altri payload nei messaggi.

Una campagna potrebbe essere di breve durata, o potrebbe interferire tra diversi giorni, settimane o mesi con periodi attivi e inattivi. Una campagna potrebbe essere avviata con l'organizzazione specifica oppure l'organizzazione potrebbe far parte di una campagna più estesa tra più società.

## <a name="campaign-views-the-security--compliance-center"></a>Visualizzazione della campagna il Centro sicurezza & Compliance

Le visualizzazioni della campagna sono disponibili nel [Centro sicurezza & conformità](https://protection.office.com) nelle campagne di **gestione delle minacce** \> **Campaigns**o direttamente su <https://protection.office.com/campaigns> .

![Panoramica della campagna nel Centro sicurezza e conformità](../../media/campaigns-overview.png)

È inoltre possibile accedere alle visualizzazioni della campagna da:

- **Gestione delle minacce** \> **Gestione risorse** \> **Visualizzazione** \> **Campagne**

- **Gestione delle minacce** \> **Gestione risorse** \> **Visualizzazione** \> **Tutti i messaggi di posta elettronica** \> Scheda **campagna**

- **Gestione delle minacce** \> **Gestione risorse** \> **Visualizzazione** \> **Phishing** \> Scheda **campagna**

- **Gestione delle minacce** \> **Gestione risorse** \> **Visualizzazione** \> **Malware** \> Scheda **campagna**

Per accedere alle visualizzazioni della campagna, è necessario essere membri dei gruppi di ruoli **Gestione organizzazione**, **amministratore sicurezza**o **lettore di sicurezza** nel centro sicurezza & conformità. Per altre informazioni, vedere [Autorizzazioni nel Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).

## <a name="campaigns-overview"></a>Panoramica delle campagne

La pagina Panoramica Visualizza informazioni su tutte le campagne.

Nella scheda **campagna** predefinita, l'area **tipo di campagna** Visualizza un grafico a barre che indica il numero di destinatari al giorno. Per impostazione predefinita, nel grafico vengono visualizzati i dati di **phishing** e di **malware** .

> [!TIP]
> Se non vengono visualizzati dati sulla campagna, provare a modificare l'intervallo di date o i [filtri](#filters-and-settings).

La parte restante della pagina Panoramica Visualizza le informazioni seguenti nella scheda **campagna** :

- **Nome**

- **Esempio di oggetto**: oggetto di uno dei messaggi della campagna. Tenere presente che tutti i messaggi nella campagna non avranno necessariamente lo stesso oggetto.

- **Targeted**: la percentuale calcolata da: (il numero di destinatari della campagna nell'organizzazione)/(il numero totale di destinatari nella campagna tra tutte le organizzazioni del servizio). Questo valore indica la misura in cui la campagna viene specificatamente indirizzata all'organizzazione (un valore superiore) e indirizzata ad altre organizzazioni del servizio (un valore più basso).

- **Type**: questo valore è **phishing** o **malware**.

- **Sottotipo**: questo valore contiene maggiori dettagli sulla campagna. Ad esempio:

  - **Phishing**: se disponibile, il marchio che viene phishing da questa campagna. Ad esempio,,,, `Microsoft` `365` `Unknown` `Outlook` o `DocuSign` .

  - **Malware**: ad esempio, `HTML/PHISH` o `HTML/<MalwareFamilyName>` .

Se disponibile, il marchio che viene phishing da questa campagna. Quando il rilevamento è guidato dalla tecnologia ATP, il prefisso **ATP-** viene aggiunto al valore del sottotipo.

- **Destinatari**: il numero di utenti oggetti dell'attacco della campagna.

- **Posta in arrivo**: il numero di utenti che hanno ricevuto messaggi da questa campagna nella posta in arrivo (non recapitati nella cartella posta indesiderata).

- **Fare clic**su: numero di utenti che hanno fatto clic sull'URL o che hanno aperto l'allegato nel messaggio di phishing.

- **Fare clic su rate**: la percentuale calcolata da "**fare clic su**  /  **posta in arrivo**". Questo valore è un indicatore dell'efficacia della campagna e indica se i destinatari sono stati in grado di identificare il messaggio come phishing ed evitare di fare clic sull'URL del payload.

  Si noti che questo valore non viene utilizzato nelle campagne antimalware.

- **Visitato**: numero di utenti effettivamente apportati al sito Web payload. Se sono presenti valori **cliccati** , ma i collegamenti sicuri impediscono l'accesso al sito Web, questo valore sarà zero.

La scheda **origine campagna** Visualizza le origini dei messaggi in una mappa del mondo.

### <a name="filters-and-settings"></a>Filtri e impostazioni

Nella parte superiore della pagina visualizzazioni campagna sono disponibili diverse impostazioni di filtro e query che consentono di individuare e isolare campagne specifiche.

![Filtri per la campagna](../../media/campaign-filters-and-settings.png)

La maggior parte dei filtri di base che è possibile eseguire è la data/ora di inizio e la data/ora di fine.

Per filtrare ulteriormente la visualizzazione, è possibile eseguire una singola proprietà con un filtro a più valori facendo clic sul pulsante **tipo di campagna** , effettuando la selezione e quindi facendo clic su **Aggiorna**.

Le proprietà della campagna disponibili sono descritte nell'elenco seguente:

- Base

  - **Tipo di campagna**: selezionare **malware** o **phishing**. La cancellazione delle selezioni ha lo stesso risultato della selezione di entrambi.
  - **Nome della campagna**
  - **Sottotipo di campagna**
  - **Mittente**
  - **Destinatari**
  - **Dominio mittente**
  - **Oggetto**
  - **Nome file allegato**
  - **Famiglia di malware**
  - **Azione per il recapito**
  - **Tecnologia di rilevamento**
  - **Categorie**
  - **Sostituzioni del sistema**

- Impostazioni avanzate

  - **ID messaggio Internet**: disponibile nel campo di intestazione **Message-ID** nell'intestazione del messaggio. Un valore di esempio è `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (si notino le parentesi angolari).
  
  - **ID messaggio di rete**: valore GUID disponibile nel campo di intestazione **X-MS-Exchange-Organization-network-Message-ID** nell'intestazione del messaggio.
  
  - **Indirizzo IP mittente**
  
  - **Attachment SHA256**: per trovare il valore hash SHA256 di un file in Windows, eseguire il comando seguente in un prompt dei comandi: `certutil.exe -hashfile "<Path>\<Filename>" SHA256` .
  
  - **ID cluster**
  
  - **ID criteri di avviso**

- URL

  - **Dominio URL**
  - **Dominio e percorso URL**
  - **URL**
  - **Percorso URL**
  - **Fare clic su verdetto**

Per un filtro più avanzato, tra cui il filtro in base a più proprietà, è possibile fare clic sul pulsante **filtro avanzato** per creare una query. Sono disponibili le stesse proprietà della campagna, ma con i miglioramenti seguenti:

- È possibile fare clic su **Aggiungi condizione** per selezionare più condizioni.
- È possibile scegliere l'operatore **and** o **or** tra le condizioni.
- È possibile selezionare l'elemento del **gruppo** di condizioni nella parte inferiore dell'elenco delle condizioni per formare condizioni composte complesse.

Al termine, fare clic sul pulsante **query** .

Dopo aver creato un filtro di base o avanzato, è possibile salvarlo tramite **Save Query** or **Save query As**. Successivamente, quando si torna alla visualizzazione della campagna, è possibile caricare un filtro salvato facendo clic su **Impostazioni query salvate**.

Per esportare il grafico o l'elenco delle campagne, fare clic su **Esporta** e selezionare **Esporta dati grafico** o **Esporta campagna**.

Se si dispone di un abbonamento a Microsoft Defender ATP, è possibile fare clic su **WDATP** per connettere o disconnettere le informazioni sulle campagne con Microsoft Defender ATP. Per ulteriori informazioni, vedere [integrazione di Office 365 ATP con Microsoft Defender ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/integrate-office-365-ti-with-wdatp).

## <a name="campaign-details"></a>Dettagli campagna

Quando si fa clic sul nome di una campagna, i dettagli della campagna vengono visualizzati in un riquadro a comparsa.

### <a name="campaign-information"></a>Informazioni sulla campagna

Nella parte superiore della visualizzazione dettagli campagna sono disponibili le informazioni sulla campagna seguenti:

- **ID**: l'identificatore della campagna univoco.

- **Started** and **ended**: la data di inizio e la data di fine della campagna. Si noti che queste date potrebbero essere estese oltre le date di filtro selezionate nella pagina panoramica.

- **Impatto**: in questa sezione sono contenuti i dati seguenti per il filtro intervallo di date selezionato (o che si seleziona nella sequenza temporale):
  
  - Numero totale di destinatari.
  - Il numero di messaggi che sono stati "ricevuti" (ovvero recapitati nella posta in arrivo, non nella cartella posta indesiderata).
  - Il numero di utenti che hanno fatto clic sul payload URL nel messaggio di phishing.
  - Howe molti utenti hanno visitato l'URL.

- **Targeted**: la percentuale calcolata da: (il numero di destinatari della campagna nell'organizzazione)/(il numero totale di destinatari nella campagna tra tutte le organizzazioni del servizio). Si noti che questo valore viene calcolato per tutta la durata della campagna e non modifica le date del filtro.

- Una cronologia interattiva delle attività della campagna: la sequenza temporale Visualizza le attività per l'intera durata della campagna. Per impostazione predefinita, l'area ombreggiata include il filtro dell'intervallo di date selezionato nella panoramica. È possibile fare clic e trascinare per selezionare un punto iniziale e un punto finale specifici, <u>che modificheranno i dati visualizzati nell'area di **impatto** e nel resto della pagina come descritto nelle sezioni successive</u>.

Nella barra del titolo, è possibile fare clic sull'icona **download campagna** write-up per scaricare la campagna ![ per scaricare ](../../media/download-campaign-write-up-button.png) i dettagli della campagna in un documento di Word (per impostazione predefinita, denominato CampaignReport.docx). Tenere presente che questo documento contiene informazioni dettagliate sull'intero ciclo di vita della campagna (non solo le date di filtro selezionate).

![Informazioni sulla campagna](../../media/campaign-details-campaign-info.png)

### <a name="campaign-flow"></a>Flusso della campagna

Al centro della visualizzazione dettagli campagna, i dettagli importanti sulla campagna sono presentati nella sezione **flusso** in un diagramma di flusso orizzontale (noto come diagramma di _Sankey_ ). Questi dettagli aiuteranno a comprendere gli elementi della campagna e il potenziale impatto sull'organizzazione.

> [!TIP]
> Le informazioni visualizzate nel diagramma di **flusso** sono controllate dall'intervallo di date ombreggiato nella sequenza temporale, come descritto nella sezione precedente.

![Dettagli della campagna che non contengono clic sull'URL da parte dell'utente](../../media/campaign-details-no-recipient-actions.png)

Se si passa il mouse su una fascia orizzontale nel diagramma, viene visualizzato il numero di messaggi correlati (ad esempio i messaggi provenienti da un determinato IP di origine, i messaggi provenienti dall'IP di origine con il dominio del mittente specificato e così via).

Il diagramma include le seguenti informazioni:

- **Indirizzi IP mittenti**

- **Domini mittenti**

- **Verdetti del filtro**: questi valori sono correlati ai verdetti di filtraggio della posta indesiderata e phishing disponibili come descritto nelle intestazioni dei messaggi di protezione dalla [posta indesiderata](anti-spam-message-headers.md). I valori disponibili sono descritti nella tabella seguente:

  ||||
  |---|---|---|
  |**Valore**|**Verdetto del filtro posta indesiderata**|**Descrizione**|
  |**Consentiti**|`SFV:SKN` <br/><br/> `SFV:SKI`|Il messaggio è stato contrassegnato come non indesiderato e/o il filtro saltato prima di essere valutato tramite il filtro posta indesiderata, ad esempio tramite una regola del flusso di posta, nota anche come regola di trasporto.<br/><br/>Il messaggio ha ignorato il filtro per la posta indesiderata per altri motivi (ad esempio, il mittente e il destinatario sono presenti nella stessa organizzazione).|
  |**Bloccati**|`SFV:SKS`|Il messaggio è stato contrassegnato come posta indesiderata prima di essere valutato tramite il filtro posta indesiderata, ad esempio tramite una regola del flusso di posta.|
  |**Rilevato**|`SFV:SPM`|Il messaggio è stato contrassegnato come posta indesiderata dal filtro posta indesiderata.|
  |**Non rilevato**|`SFV:NSPM`|Il messaggio è stato contrassegnato come non indesiderato dal filtro posta indesiderata.|
  |**Rilasciato**|`SFV:SKQ`|Il messaggio ha ignorato il filtro della posta indesiderata perché è stato rilasciato dalla quarantena.|
  |**Consenti tenant**<sup>\*</sup>|`SFV:SKA`|Il messaggio ha ignorato il filtro della posta indesiderata a causa delle impostazioni dei criteri di protezione dalla posta indesiderata (ad esempio, il mittente è nell'elenco dei mittenti consentito o nel dominio consentito).|
  |**Blocco tenant**<sup>\*\*</sup>|`SFV:SKA`|Il messaggio è stato bloccato dal filtro posta indesiderata a causa delle impostazioni dei criteri di protezione da posta indesiderata (ad esempio, il mittente è nell'elenco dei mittenti consentiti o nel dominio consentito).|
  |**Consenti utente**<sup>\*</sup>|`SFV:SFE`|Il messaggio ha ignorato il filtro della posta indesiderata perché il mittente si trovava nell'elenco Mittenti attendibili di un utente in Outlook.|
  |**Blocco utenti**<sup>\*\*</sup>|`SFV:BLK`|Il messaggio è stato bloccato dal filtro posta indesiderata perché il mittente si trovava nell'elenco Mittenti bloccati di un utente in Outlook.|
  |**ZAP**|n/d|[Zero-hour auto Purge (ZAP)](zero-hour-auto-purge.md) ha eseguito un'azione sul messaggio recapitato in base alle impostazioni dei criteri di protezione da posta indesiderata (spostati nella cartella posta indesiderata o in quarantena).|
  |

  <sup>\*</sup>Esaminare i criteri di protezione da posta indesiderata, poiché il servizio potrebbe essere stato bloccato.

  <sup>\*\*</sup>Esaminare i criteri di protezione da posta indesiderata, poiché tali messaggi devono essere messi in quarantena, non recapitati.

- **Posizioni di recapito**: è consigliabile esaminare i messaggi che sono stati effettivamente recapitati ai destinatari (nella cartella posta in arrivo o posta indesiderata), anche se gli utenti non hanno fatto clic sull'URL del payload nel messaggio. È inoltre possibile rimuovere i messaggi in quarantena dalla quarantena. Per ulteriori informazioni, vedere [messaggi di posta elettronica in quarantena in EOP](quarantine-email-messages.md).

  - **Cartella eliminata**
  - **Interrotte**
  - **External**: il destinatario si trova nell'organizzazione di posta elettronica locale in ambienti ibridi.
  - **Operazione non riuscita**
  - **Inoltrato**
  - **Posta in arrivo**
  - **Posta indesiderata**
  - **Quarantena**
  - **Unknown**

- **Clic URL**: sono descritti nella sezione successiva.

> [!NOTE]
> In tutti i layer che contengono più di 10 elementi vengono visualizzati i primi 10 elementi, mentre quelli restanti sono raggruppati in **altri**.

#### <a name="url-clicks"></a>Clic URL

Quando un messaggio di phishing viene recapitato a un destinatario (nella cartella posta in arrivo o posta indesiderata), è sempre possibile che l'utente clicchi sull'URL del payload. Non fare clic sull'URL in un messaggio recapitato è una piccola misura di esito positivo, ma è necessario determinare il motivo per cui il messaggio di phishing è stato recapitato alla propria cassetta postale in primo luogo.

Se un utente ha fatto clic sull'URL payload nel messaggio di phishing, le azioni vengono visualizzate nell'area **clic URL** del diagramma nella visualizzazione dettagli campagna.

- **Consentiti**

- **BlockPage**: il destinatario ha fatto clic sull'URL payload, ma l'accesso al sito Web dannoso è stato bloccato dai criteri dei [collegamenti sicuri ATP](atp-safe-links.md) nell'organizzazione.

- **BlockPageOverride**: il destinatario ha fatto clic sull'URL del payload nel messaggio, i collegamenti sicuri di ATP hanno provato a arrestarli, ma sono stati autorizzati a eseguire l'override del blocco. È necessario esaminare i criteri per i [collegamenti sicuri](set-up-atp-safe-links-policies.md) per capire perché gli utenti possono ignorare il verdetto dei collegamenti sicuri e continuare con il sito Web dannoso.

- **PendingDetonationPage**: gli allegati sicuri di ATP è in fase di apertura dell'URL di payload in un ambiente computer virtuale e di vedere cosa accade.

- **PendingDetonationPageOverride**: al destinatario è stato consentito di ignorare il processo di detonazione del payload e di aprire l'URL senza attendere i risultati.

### <a name="tabs"></a>Schede

Le schede nella visualizzazione dettagli campagna consentono di analizzare ulteriormente la campagna.

> [!TIP]
> Le informazioni visualizzate nelle schede sono controllate dall'intervallo di date ombreggiato nella sequenza temporale, come descritto nella sezione [informazioni sulla campagna](#campaign-information) .

- **Clic URL**: se gli utenti non hanno fatto clic sull'URL payload nel messaggio di phishing, questa sezione sarà vuota. Se un utente è stato in grado di fare clic sull'URL, verranno inseriti i valori seguenti:

  - **Utente:**<sup>\*</sup>
  - **URL**<sup>\*</sup>
  - **Fare clic su tempo**
  - **Fare clic su verdetto**

- **Indirizzi IP mittenti**

  - **Indirizzo IP mittente**<sup>\*</sup>
  - **Conteggio totale**
  - **Posta in arrivo**
  - **Non ricevuti**
  - **SPF superato**: il mittente è stato autenticato da [Sender Policy Framework (SPF)](how-office-365-uses-spf-to-prevent-spoofing.md). Un mittente che non supera la convalida SPF indica che il mittente non è autenticato o che il messaggio è spoofing di un mittente legittimo.

- **Mittenti**

  - **Sender**: questo è l'indirizzo effettivo del mittente nel comando SMTP mail from, che non è necessariamente l'indirizzo di posta elettronica da: che gli utenti visualizzano nei client di posta elettronica.
  - **Conteggio totale**
  - **Posta in arrivo**
  - **Non ricevuti**
  - **DKIM superato**: il mittente è stato autenticato da [Key Domain identificated mail (DKIM)](support-for-validation-of-dkim-signed-messages.md). Un mittente che non supera la convalida di DKIM indica che il mittente non è autenticato o che il messaggio è spoofing di un mittente legittimo.
  - **DMARC superato**: il mittente è stato autenticato da [autenticazione dei messaggi basata sul dominio, Reporting e conformità (DMARC)](use-dmarc-to-validate-email.md). Un mittente che non supera la convalida di DMARC indica che il mittente non è autenticato o che il messaggio è spoofing di un mittente legittimo.

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

- **Esplorare i messaggi in arrivo**: apre una nuova scheda di ricerca di Esplora minacce utilizzando l' **ID della campagna** e il **percorso di recapito: posta in arrivo** come filtro di ricerca.
