---
title: Visualizzazioni delle campagne in ATP
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
ms.openlocfilehash: 69b11319ffb033b628e59abac931b6a3f30d082c
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43637819"
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

- **Origine dell'attacco**: indirizzi IP origine e domini di posta elettronica del mittente.

- **Caratteristiche del messaggio di attacco**: il contenuto, lo stile e il tono dei messaggi di attacco.

- **Destinatari dell'attacco**: domini dei destinatari, funzione aziendale dei destinatari (amministratori, dirigenti e così via), tipi di azienda (grandi, piccole, pubbliche, private e così via) e settori.

- **Attacco payload**: collegamenti malevoli, allegati o altri payload nei messaggi di attacco.

Una campagna potrebbe essere di breve durata, o potrebbe interferire tra diversi giorni, settimane o mesi con periodi attivi e inattivi. Una campagna potrebbe essere avviata con l'organizzazione specifica oppure l'organizzazione potrebbe far parte di una campagna più estesa tra più società.

## <a name="campaign-views-the-security--compliance-center"></a>Visualizzazione della campagna il Centro sicurezza & Compliance

Le visualizzazioni campagna sono disponibili nel [Centro sicurezza & conformità](https://protection.office.com) nelle **Threat management** \> **campagne**di gestione delle minacce.

![Panoramica della campagna nel Centro sicurezza e conformità](../../media/campaigns-overview.png)

È inoltre possibile accedere alla visualizzazione campagne da:

- **Campagne** di **Explorer** \> **View** visualizzazione \> di **gestione delle minacce** \>

- **Gestione delle** \> minacce **Esplora** \> **View** **All email** \> **Campaign** tutte le campagne di posta elettronica \>

> [!TIP]
> Se i dati della campagna non sono visibili, provare a modificare l'intervallo di date.

La pagina di panoramica visualizza le seguenti informazioni sulla campagna:

- **Nome**

- **Esempio di oggetto**: oggetto di uno dei messaggi della campagna. Tenere presente che tutti i messaggi nella campagna non avranno necessariamente lo stesso oggetto.

- **Tipo**: attualmente, questo valore è sempre **phishing**.

- **Sottotipo**: se disponibile, il marchio oggetto dell'attacco di phishing dalla campagna. Quando il rilevamento è guidato dalla tecnologia ATP, il prefisso **ATP-** viene aggiunto al valore del sottotipo.

- **Destinatari**: il numero di utenti oggetti dell'attacco della campagna.

- **Posta in arrivo**: il numero di utenti che hanno ricevuto messaggi da questa campagna nella cartella posta in arrivo (non recapitati alla posta indesiderata).

- **Fare clic**su: il numero di utenti che hanno fatto clic sull'URL nel messaggio di phishing.

- **Fare clic su rate**: la percentuale calcolata da "**fare clic su** / **posta in arrivo**". Questo valore è un indicatore dell'efficacia della campagna e indica se i destinatari sono stati in grado di identificare il messaggio come phishing ed evitare di fare clic sull'URL del payload.

- **Visitato**: numero di utenti effettivamente apportati al sito Web payload. Se sono presenti valori **cliccati** , ma i collegamenti sicuri impediscono l'accesso al sito Web, questo valore sarà zero.

Quando si fa clic sul nome di una campagna, i dettagli della campagna sono visualizzati in un riquadro a comparsa.

## <a name="campaign-details"></a>Dettagli campagna

Nella visualizzazione dei dettagli della campagna sono disponibili numerose informazioni:

- Informazioni sulla campagna:

  - **ID**: l'identificatore della campagna univoco.

  - **Iniziata** e **Terminata**: l'intervallo di date scelto come filtro.

  - **Impatto**: i dati seguenti per il filtro intervallo di date selezionato:
  
    - Numero totale di destinatari.

    - Il numero di messaggi che sono stati "ricevuti" (ovvero, recapitati nella posta in arrivo, non per la posta indesiderata).

    - Il numero di utenti che hanno fatto clic sul payload URL nel messaggio di phishing.

    - Howe molti utenti hanno visitato l'URL.

  - Una sequenza temporale delle attività delle campagne: quando è iniziata e terminata la campagna e il volume di messaggi nel corso del tempo.

### <a name="campaign-flow"></a>Flusso della campagna

I dettagli importanti sulla campagna sono presentati in un diagramma di flusso orizzontale (noto come diagramma di _Sankey_) nella sezione **Flusso**. Questi dettagli aiuteranno a comprendere gli elementi della campagna e il potenziale impatto sull'organizzazione.

![Dettagli della campagna che non contengono clic sull'URL da parte dell'utente](../../media/campaign-details-no-recipient-actions.png)

Se si passa il mouse su una fascia orizzontale nel diagramma, viene visualizzato il numero di messaggi correlati (ad esempio i messaggi provenienti da un determinato IP di origine, i messaggi provenienti dall'IP di origine con il dominio del mittente specificato e così via).

Il diagramma include le seguenti informazioni:

- **Indirizzi IP mittenti**

- **Domini mittenti**

- **Verdetti del filtro**: i valori qui sono correlati ai verdetti del filtro di phishing e di posta indesiderata disponibili come descritto nelle intestazioni dei messaggi di protezione da [posta indesiderata](anti-spam-message-headers.md). I valori disponibili sono descritti nella tabella seguente:

  |Valore|Verdetto del filtro posta indesiderata|Descrizione|
  |:-----|:-----|:-----|
  | **Consentiti**|`SFV:SKN` <br/><br/> `SFV:SKI`|Il messaggio è stato contrassegnato come non indesiderato e/o il filtro saltato prima di essere valutato tramite il filtro posta indesiderata, ad esempio tramite una regola del flusso di posta, nota anche come regola di trasporto.<br/><br/>Il messaggio ha ignorato il filtro per la posta indesiderata per altri motivi (ad esempio, il mittente e il destinatario sono presenti nella stessa organizzazione).|
  |**Bloccati**|`SFV:SKS`|Il messaggio è stato contrassegnato come posta indesiderata prima di essere valutato tramite il filtro posta indesiderata, ad esempio tramite una regola del flusso di posta.|
  |**Rilevato**|`SFV:SPM`|Il messaggio è stato contrassegnato come posta indesiderata dal filtro posta indesiderata.|
  |**Non rilevato**|`SFV:NSPM`|Il messaggio è stato contrassegnato come non indesiderato dal filtro posta indesiderata.|
  |**Rilasciato**|`SFV:SKQ`|Il messaggio ha ignorato il filtro della posta indesiderata perché è stato rilasciato dalla quarantena.|
  |**Consenti tenant**<sup>\*</sup>|`SFV:SKA`|Il messaggio ha ignorato il filtro della posta indesiderata a causa delle impostazioni dei criteri di protezione dalla posta indesiderata (ad esempio, il mittente è nell'elenco dei mittenti consentito o nel dominio consentito).|
  |**Blocco tenant**<sup>\*\*</sup>|`SFV:SKA`|Il messaggio è stato bloccato dal filtro posta indesiderata a causa delle impostazioni dei criteri di protezione da posta indesiderata (ad esempio, il mittente è nell'elenco dei mittenti consentiti o nel dominio consentito).|
  |**Consenti utente**<sup>\*</sup>|`SFV:SFE`|Il messaggio ha ignorato il filtro della posta indesiderata perché il mittente si trovava nell'elenco Mittenti attendibili di un utente in Outlook.|
  |**Blocco utenti**<sup>\*\*</sup>|`SFV:BLK`|Il messaggio è stato bloccato dal filtro posta indesiderata perché il mittente si trovava nell'elenco Mittenti bloccati di un utente in Outlook.|
  |**ZAP**|n/d|[Zero-hour auto Purge (ZAP)](zero-hour-auto-purge.md) ha eseguito un'azione sul messaggio recapitato in base alle impostazioni dei criteri di protezione da posta indesiderata (spostati nella cartella posta indesiderata o in quarantena).|

  <sup>\*</sup>Esaminare i criteri di protezione da posta indesiderata, poiché il servizio potrebbe essere stato bloccato.

  <sup>\*\*</sup>Esaminare i criteri di protezione da posta indesiderata, poiché tali messaggi devono essere messi in quarantena, non recapitati.

- **Posizioni di recapito**: è consigliabile esaminare i messaggi che sono stati effettivamente recapitati ai destinatari (nella cartella posta in arrivo o posta indesiderata), anche se gli utenti non hanno fatto clic sull'URL del payload nel messaggio. È inoltre possibile rimuovere i messaggi in quarantena dalla quarantena. For more information, see [Quarantine email messages in Office 365](quarantine-email-messages.md).

  - **Cartella eliminata**

  - **Interrotte**

  - **External**: il destinatario si trova nell'organizzazione di posta elettronica locale.

  - **Operazione non riuscita**

  - **Inoltrato**

  - **Posta in arrivo**

  - **Posta indesiderata**

  - **Quarantena**

  - **Unknown**

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

Nella visualizzazione dei dettagli della campagna sono disponibili diverse schede che consentono di esaminare la campagna in maniera più approfondita.

- **Clic URL**: se gli utenti non hanno fatto clic sull'URL payload nel messaggio di phishing, questa sezione sarà vuota. Se un utente è stato in grado di fare clic sull'URL, verranno inseriti i valori seguenti:

  - **Utente:**<sup>\*</sup>

  - **URL**<sup>\*</sup>

  - **Ora clic**

  - **Azione clic**

- **Indirizzi IP mittenti**

  - **Indirizzo IP mittente**<sup>\*</sup>

  - **Conteggio totale**

  - **Conteggio messaggi in posta in arrivo**

  - **Conteggio bloccati**

  - **SPF superato**: il mittente è stato autenticato da [Sender Policy Framework (SPF)](how-office-365-uses-spf-to-prevent-spoofing.md). Un mittente che non supera la convalida SPF indica che il mittente non è autenticato o che il messaggio è spoofing di un mittente legittimo.

- **Mittenti**

  - **Sender**: questo è l'indirizzo effettivo del mittente nel comando SMTP mail from, che non è necessariamente l'indirizzo di posta elettronica da: che gli utenti visualizzano nei client di posta elettronica.

  - **Conteggio totale**

  - **Posta in arrivo**

  - **Non ricevuti**

  - **DKIM superato**: il mittente è stato autenticato da [Key Domain identificated mail (DKIM)](support-for-validation-of-dkim-signed-messages.md). Un mittente che non supera la convalida di DKIM indica che il mittente non è autenticato o che il messaggio è spoofing di un mittente legittimo.

  - **DMARC superato**: il mittente è stato autenticato da [autenticazione dei messaggi basata sul dominio, Reporting e conformità (DMARC)](use-dmarc-to-validate-email.md). Un mittente che non supera la convalida di DMARC indica che il mittente non è autenticato o che il messaggio è spoofing di un mittente legittimo.

- **Payload**

  - **URL**<sup>\*</sup>

  - **Conteggio totale**

<sup>\*</sup> Se si fa clic su questo valore, viene aperto un nuovo riquadro a comparsa che contiene altri dettagli sulla voce specificata (utente, URL e così via) nella parte superiore della visualizzazione dei dettagli della campagna. Per tornare alla visualizzazione dei dettagli della campagna, fare clic su **Chiudi** nel nuovo riquadro a comparsa.

### <a name="buttons"></a>Pulsanti

I pulsanti nella visualizzazione dei dettagli della campagna consentono di usare la potenza di Esplora minacce per approfondire la campagna.

- **Esplora minacce**: apre una nuova scheda di ricerca in Esplora minacce usando il valore **ID campagna** come filtro di ricerca.

- **Esplorare i messaggi in arrivo**: apre una nuova scheda di ricerca di Esplora minacce utilizzando l' **ID della campagna** e il **percorso di recapito: posta in arrivo** come filtro di ricerca.
