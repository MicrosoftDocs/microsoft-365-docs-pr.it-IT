---
title: Visualizzare i report sulla sicurezza della posta elettronica nel Centro sicurezza e conformità
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 3a137e28-1174-42d5-99af-f18868b43e86
ms.collection:
- M365-security-compliance
description: Informazioni su come trovare e utilizzare i report sulla sicurezza della posta elettronica per l'organizzazione. I report sulla sicurezza della posta elettronica sono disponibili nel centro sicurezza & conformità.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 36d7fde77ae8a6280dae26e5a0f7a75537bf28d4
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "48841873"
---
# <a name="view-email-security-reports-in-the-security--compliance-center"></a>Visualizzare i report sulla sicurezza della posta elettronica nel Centro sicurezza e conformità

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Nel [Centro sicurezza & conformità](https://protection.office.com) è disponibile un'ampia gamma di report che consentono di visualizzare in che modo le funzionalità di sicurezza della posta elettronica, ad esempio la protezione da posta indesiderata, l'antimalware e la crittografia in Microsoft 365, proteggono l'organizzazione. Se si dispone delle [autorizzazioni necessarie](#what-permissions-are-needed-to-view-these-reports), è possibile visualizzare i report nel centro sicurezza & Compliance accedendo al **Reports** \> **Dashboard** report. Per accedere direttamente al dashboard dei report, aprire <https://protection.office.com/insightdashboard> .

![Dashboard dei report nel centro sicurezza & Compliance](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="compromised-users-report"></a>Report utenti compromessi

> [!NOTE]
> Questo report è disponibile nelle organizzazioni Microsoft 365 con le cassette postali di Exchange Online. Non è disponibile nelle organizzazioni standalone di Exchange Online Protection (EOP).

Nel rapporto **utenti compromessi** viene mostrato il numero di account utente contrassegnati come **sospetti** o **limitati** negli ultimi 7 giorni. Gli account in uno di questi Stati sono problematici o addirittura compromessi. Con uso frequente, è possibile utilizzare il report per individuare picchi e persino tendenze, in account sospetti o limitati. Per ulteriori informazioni sugli utenti compromessi, vedere [risposta a un account di posta elettronica compromesso](responding-to-a-compromised-email-account.md).

![Widget utenti compromessi nel dashboard dei report](../../media/compromised-users-report-widget.png)

La visualizzazione aggregazione Mostra i dati per gli ultimi 90 giorni e la visualizzazione dettagli Mostra i dati per gli ultimi 30 giorni.

Per visualizzare il report, aprire il [Centro sicurezza & conformità](https://protection.office.com), accedere al **Reports** \> **Dashboard** dei report e selezionare **utenti compromessi**. Per passare direttamente al report, aprire <https://protection.office.com/reportv2?id=CompromisedUsers> .

È possibile filtrare sia il grafico che la tabella Details facendo clic su **filtri** e selezionando uno o più dei seguenti valori:

- Data di **inizio** e **Data di fine**

- **Sospetti** : l'account utente ha inviato messaggi di posta elettronica sospetti ed è a rischio di essere limitato dall'invio di messaggi di posta elettronica.

- **Limitato** : l'account utente è stato limitato dall'invio di messaggi di posta elettronica a causa di modelli estremamente sospetti.

![Visualizzazione report nel report utenti compromessi](../../media/compromised-users-report-activity-view.png)

Se si fa clic su **Visualizza tabella dettagli** , è possibile visualizzare i dettagli seguenti:

- **Ora di creazione**
- **ID utente**
- **Azione**

Per tornare alla visualizzazione report, fare clic su **Visualizza report**.

## <a name="encryption-report"></a>Rapporto di crittografia

Il **rapporto di crittografia** è disponibile in EOP (abbonamenti con cassette postali in Exchange Online o EOP autonomo senza cassette postali di Exchange Online). Il team di sicurezza dell'organizzazione può utilizzare le informazioni contenute in questo report per identificare modelli e applicare o modificare in modo proattivo i criteri per i messaggi di posta elettronica sensibili. Ad esempio:

- Se viene visualizzato un numero elevato di messaggi di posta elettronica crittografati dagli utenti, potrebbe essere necessario aggiungere un criterio di crittografia per automatizzare la crittografia per alcuni casi di utilizzo. Per ulteriori informazioni, vedere [definire le regole del flusso di posta per crittografare i messaggi di posta elettronica in Microsoft 365](../../compliance/define-mail-flow-rules-to-encrypt-email.md).

- Se si dispone di un numero di modelli di crittografia disponibili ma nessuno li utilizza, è possibile esaminare se gli utenti hanno bisogno di una formazione delle funzionalità.

La visualizzazione aggregazione consente il filtro per gli ultimi 90 giorni, mentre la visualizzazione dettagli consente il filtraggio per 10 giorni.

Per visualizzare il report, aprire il [Centro sicurezza & conformità](https://protection.office.com), accedere al **Reports** \> **Dashboard** dei report e selezionare **rapporto di crittografia**. Per passare direttamente al report, aprire <https://protection.office.com/reportv2?id=EncryptionReport> .

Per ulteriori informazioni sulla crittografia, vedere la [crittografia della posta elettronica in Microsoft 365](../../compliance/email-encryption.md).

### <a name="report-view-for-the-encryption-report"></a>Visualizzazione report per il rapporto di crittografia

Nel grafico è possibile utilizzare i seguenti filtri:

- **Visualizzare i dati in base a: rapporto di crittografia dei messaggi** e **scomposizione in base a: metodo di** crittografia: sono disponibili i seguenti metodi di crittografia:

  - **Crittografia per utente**
  - **Crittografia per criterio**

  Se si fa clic su **filtri** , è possibile modificare il grafico con i filtri seguenti:

  - Data di **inizio** e **Data di fine**
  - Metodo di crittografia.
  - Modello di crittografia.

- **Visualizzare i dati in base a: rapporto di crittografia dei messaggi** e **scomposizione in base a: modello di crittografia** : sono disponibili i seguenti metodi di crittografia:

  - **Non inoltrare**
  - **Solo crittografia**
  - **OME precedente**
  - **Personalizzata**

  Se si fa clic su **filtri** , è possibile modificare il grafico con i filtri seguenti:

  - Data di **inizio** e **Data di fine**
  - Metodo di crittografia
  - Modello di crittografia

- **Visualizzare i dati per: Top 5 Domains Recipient** : questa visualizzazione Mostra un grafico a torta con i conteggi dei messaggi inviati per i primi 5 domini dei destinatari.

  Se si fa clic su **filtri** , è possibile selezionare una data di **inizio** e una **Data di fine**.

### <a name="details-table-view-for-the-encryption-report"></a>Visualizzazione della tabella dei dettagli per il rapporto di crittografia

Se si fa clic su **Visualizza tabella dettagli** , le informazioni visualizzate dipendono dal grafico che si sta esaminando:

- **Scomposizione per: metodo di crittografia** o **scomposizione in base a: modello di crittografia** : vengono visualizzate le informazioni seguenti:

  - **Data**
  - **Indirizzo del mittente**
  - **Modello di crittografia**
  - **Metodo di crittografia**
  - **Indirizzo del destinatario**
  - **Oggetto**

- **Visualizzare i dati per: Top 5 Domains Recipient** :

  - **Data**
  - **Dominio del destinatario**
  - **Numero di messaggi**
  
Se si fa clic su **filtri** in una visualizzazione tabella dettagli, è possibile modificare i risultati con i filtri seguenti:

- Data di **inizio** e **Data di fine**
- Metodo di crittografia
- Modello di crittografia

Per tornare alla visualizzazione report, fare clic su **Visualizza report**.

## <a name="mailflow-status-report"></a>Rapporto sullo stato del flusso di posta

Il **rapporto di stato del flusso** di lavoro contiene informazioni su malware, posta indesiderata, phishing e messaggi bloccati Edge. Per ulteriori informazioni, vedere [rapporto sullo stato del flusso](view-mail-flow-reports.md#mailflow-status-report)di posta.

## <a name="malware-detections-in-email-report"></a>Rilevamenti di malware nel rapporto di posta elettronica

I rilevamenti di **malware nel rapporto di posta elettronica** mostrano informazioni sui rilevamenti di malware nei messaggi di posta elettronica in arrivo e in uscita (malware rilevati da Exchange Online Protection o EOP). Per ulteriori informazioni sulla protezione antimalware in EOP, vedere [anti-malware Protection in EOP](anti-malware-protection.md).

 Il filtro visualizzazione aggregazione consente 90 giorni, mentre il filtro tabella Dettagli consente solo 10 giorni.

Per visualizzare il report, aprire il [Centro sicurezza & conformità](https://protection.office.com), accedere al **Reports** \> **Dashboard** dei report e selezionare **rilevamenti di malware nel messaggio di posta elettronica**. Per passare direttamente al report, aprire <https://protection.office.com/reportv2?id=MalwareDetections> .

![Rilevamenti di malware nel widget di posta elettronica nel dashboard report](../../media/malware-detections-widget.png)

È possibile filtrare sia il grafico che la tabella Details facendo clic su **filtri** e selezionando:

- Data di **inizio** e **Data di fine**
- **Inbound**
- **In uscita**

![Visualizzazione report nel rapporto di rilevamento di malware nel messaggio di posta elettronica](../../media/malware-detections-report-view.png)

Se si fa clic su **Visualizza tabella dettagli** , è possibile visualizzare i dettagli seguenti:

- **Data**
- **Indirizzo del mittente**
- **Indirizzo del destinatario**
- **ID messaggio** : disponibile nel campo di intestazione **Message-ID** nell'intestazione del messaggio e deve essere univoco. Un valore di esempio è `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (si notino le parentesi angolari).
- **Oggetto**
- **Filename**
- **Nome malware**

Per tornare alla visualizzazione report, fare clic su **Visualizza report**.

## <a name="sent-and-received-email-report"></a>Report di posta elettronica inviati e ricevuti

Il rapporto **messaggi di posta elettronica inviati e ricevuti** contiene informazioni su malware, posta indesiderata, regole del flusso di posta (note anche come regole di trasporto) e rilevamenti di malware avanzati dopo che la posta elettronica entra nel servizio. Per ulteriori informazioni, vedere [report di posta elettronica inviata e ricevuta](view-mail-flow-reports.md#sent-and-received-email-report).

## <a name="spam-detections-report"></a>Report sui rilevamenti della posta indesiderata

Il rapporto sui **rilevamenti di posta indesiderata** Visualizza messaggi di posta indesiderata bloccati da EOP. I messaggi vengono conteggiati singolarmente e non per destinatario. Ad esempio, se lo stesso messaggio di posta indesiderata è stato inviato a 100 destinatari nell'organizzazione, viene conteggiato come un solo messaggio.

La visualizzazione aggregazione consente il filtraggio di 90 giorni, mentre la tabella Details consente il filtraggio di 10 giorni.

Per visualizzare il report, aprire il [Centro sicurezza & conformità](https://protection.office.com), accedere al **Reports** \> **Dashboard** dei report e selezionare **rilevamenti di posta indesiderata**. Per passare direttamente al report, aprire <https://protection.office.com/reportv2?id=SpamDetections> .

![Widget per i rilevamenti di posta indesiderata nel dashboard report](../../media/spam-detections-report-widget.png)

Per ulteriori informazioni sulla protezione da posta indesiderata, vedere [protezione da posta](anti-spam-protection.md)indesiderata in EOP.

### <a name="report-view-for-the-spam-detections-report"></a>Visualizzazione report per il rapporto rilevamento posta indesiderata

Nella visualizzazione report sono disponibili i grafici seguenti:

- **Scomposizione per: azione** : vengono visualizzati i tipi di evento seguenti:

  - **Contenuto di posta indesiderata filtrato**
  - **Blocco IP di posta indesiderata**
  - **Blocco busta posta indesiderata**
  - **Filtro per la posta indesiderata DBEB** : blocco Edge basato su directory (DBEB)

  Quando si posiziona il puntatore del mouse su un giorno (punto dati) nel grafico, è possibile vedere quanti elementi sono stati bloccati in quel giorno, nonché come tali elementi sono categorizzati.

  ![Visualizzazione azione nel rapporto rilevamento posta indesiderata](../../media/spam-detections-report-action-view.png)

- **Scomposizione per: direzione** : vengono visualizzate le indicazioni seguenti:

  - **Inbound**
  - **In uscita**

  ![Visualizzazione direzione nel rapporto rilevamento posta indesiderata](../../media/spam-detections-report-direction-view.png)

Se si fa clic su **filtri** in una visualizzazione report, è possibile modificare i risultati con i filtri seguenti:

- Data di **inizio** e **Data di fine**
- Valori di direzione
- Valori del tipo di evento

### <a name="details-table-view-for-the-spam-detections-report"></a>Visualizzazione tabella dettagli per il rapporto rilevamento posta indesiderata

Se si fa clic su **Visualizza tabella dettagli** in qualsiasi visualizzazione report, vengono visualizzate le informazioni seguenti:

- **Data**
- **Indirizzo del mittente**
- **Indirizzo del destinatario**
- **Tipo evento**
- **Azione**
- **Oggetto**

Se si fa clic su **filtri** in una tabella Details, è possibile modificare i risultati con i filtri seguenti:

- Data di **inizio** e **Data di fine**
- Valori di direzione
- Valori del tipo di evento

Per tornare alla visualizzazione report, fare clic su **Visualizza report**.

## <a name="spoof-detections-report"></a>Rapporto rilevamenti spoof

Il rapporto sui rilevamenti **spoof** indica il numero di messaggi di posta elettronica contraffatti individuati e di quelli che sono stati considerati "buoni" (la posta contraffatta è stata realizzata per motivi aziendali legittimi). Per ulteriori informazioni sullo spoofing, vedere [protezione anti-spoofing in EOP](anti-spoofing-protection.md).

La visualizzazione aggregazione del report consente 90 giorni di filtraggio, mentre la visualizzazione dettagli consente solo dieci giorni di filtraggio.

Per visualizzare il report, aprire il [Centro sicurezza & conformità](https://protection.office.com), accedere al **Reports** \> **Dashboard** dei report e selezionare **rilevamenti spoof**. Per passare direttamente al report, aprire <https://protection.office.com/reportv2?id=SpoofMailReport> .

![Widget spoofing detections nel dashboard report](../../media/spoof-detections-widget.png)

Quando si posiziona il puntatore del mouse su un giorno (punto dati) nel grafico, è possibile visualizzare il numero di messaggi di posta elettronica contraffatti.

È possibile filtrare sia il grafico che la tabella Details facendo clic su **filtri** e selezionando uno o più dei seguenti valori:

- Data di **inizio** e **Data di fine**

- **Posta elettronica buona**

- **Catturato come posta indesiderata**

![Visualizzazione report nel rapporto rilevamenti spoof](../../media/spoof-detections-report-view.png)

Se si fa clic su **Visualizza tabella dettagli** , è possibile visualizzare i dettagli seguenti:

- **Data**
- **Mittente falsificato**
- **Mittente vero**
- **Indirizzo IP mittente**
- **Azione**
- **Numero di messaggi**

Per tornare alla visualizzazione report, fare clic su **Visualizza report**.

## <a name="threat-protection-status-report"></a>Report dello stato di protezione dalle minacce

Il rapporto **sullo stato della protezione dalle minacce** è disponibile sia in EOP che in Microsoft Defender per Office 365; Tuttavia, i report contengono dati diversi. Ad esempio, i clienti di EOP possono visualizzare informazioni sui malware rilevati tramite posta elettronica, ma non informazioni sui [file dannosi rilevati da ATP per SharePoint, OneDrive o Microsoft teams](atp-for-spo-odb-and-teams.md).

Il rapporto fornisce il numero di messaggi di posta elettronica con contenuti dannosi, ad esempio i file o gli indirizzi del sito Web (URL) bloccati dal motore antimalware, da [zero-hour auto Purge (ZAP)](zero-hour-auto-purge.md)e Defender per Office 365 caratteristiche come [collegamenti sicuri](atp-safe-links.md), [allegati sicuri](atp-safe-attachments.md)e [anti-phishing](set-up-anti-phishing-policies.md). È possibile utilizzare queste informazioni per identificare le tendenze o determinare se i criteri dell'organizzazione devono essere rettificati. È importante comprendere che se un messaggio viene inviato a cinque destinatari, è necessario contarlo come cinque messaggi diversi e non con un solo messaggio.

Per visualizzare il report, aprire il [Centro sicurezza & conformità](https://protection.office.com), accedere al **Reports** \> **Dashboard** dei report e selezionare **lo stato di protezione dalle minacce**. Per passare direttamente al report, aprire uno degli URL seguenti:

- Microsoft Defender per Office 365: <https://protection.office.com/reportv2?id=TPSAggregateReportATP>
- EOP <https://protection.office.com/reportv2?id=TPSAggregateReport>

![Widget dello stato di protezione dalle minacce nel dashboard dei report](../../media/threat-protection-status-report-widget.png)

Per impostazione predefinita, il grafico Visualizza i dati negli ultimi 7 giorni. Se si fa clic su **filtri** , è possibile selezionare un intervallo di date di 90 giorni (gli abbonamenti di valutazione potrebbero essere limitati a 30 giorni). La visualizzazione tabella Dettagli consente di filtrare per 30 giorni.

### <a name="report-view-for-the-threat-protection-status-report"></a>Visualizzazione report per il rapporto sullo stato di protezione dalle minacce

Sono disponibili le visualizzazioni seguenti:

- **Visualizzare i dati in base a: Panoramica** : vengono visualizzate le informazioni di rilevamento seguenti:

  - **Malware per la posta elettronica**
  - **Phishing di posta elettronica**
  - **Malware contenuto**

  ![Visualizzazione panoramica nel rapporto sullo stato di protezione di minacce](../../media/threat-protection-status-report-overview-view.png)

- **Visualizzare i dati in base a: content \> Malware**<sup>1</sup>: vengono visualizzate le seguenti informazioni per Microsoft Defender per le organizzazioni di Office 365:

  - **Motore antimalware** : intercettazioni di file dannosi in SharePoint Online, OneDrive e teams da anti-malware.
  - **Detonazione dei file** : detonazione di file dannosi in SharePoint Online, OneDrive e teams da allegati sicuri.

  ![Visualizzazione malware contenuto nel rapporto sullo stato della protezione dalle minacce](../../media/threat-protection-status-report-content-malware-view.png)

- **Visualizzare i dati in base a: override del messaggio** : vengono visualizzate le informazioni relative al motivo di sostituzione seguenti:

  - **Ignora locale**
  - **Consenti IP**
  - **Regola del flusso di posta**
  - **Consenti mittente**
  - **Consenti dominio**
  - **ZAP non abilitato**
  - **Cartella posta indesiderata non abilitata**
  - **Mittente sicuro dell'utente**
  - **Dominio sicuro dell'utente**

  ![Visualizzazione di sostituzione dei messaggi nel rapporto sullo stato della protezione dalle minacce](../../media/threat-protection-status-report-message-override-view.png)

- **Scomposizione per: tecnologia di rilevamento** e **visualizzazione dei dati in base a: e-mail \> phishing** : vengono visualizzate le informazioni seguenti:

  - **Reputazione URL generata dal trifosfato di adenosina**<sup>1</sup>: reputazione di URL dannosi generata dal difensore per le detonazioni di Office 365 in altri difensori per i clienti di Office 365.
  - **Filtro Advanced phishing** : segnali di phishing basati sull'apprendimento automatico.
  - **Errore di anti-spoofing-DMARC** : errore di autenticazione di DMARC nei messaggi.
  - **Anti-spoofing-intra-org** : il mittente sta tentando di falsificare il dominio del destinatario.
  - **Anti-spoofing-dominio esterno** : il mittente sta provando a falsificare un altro dominio.
  - **Rappresentazione del marchio** : rappresentazione di marche ben note basate su mittenti.
  - **Rappresentazione di dominio**<sup>1</sup>: rappresentazione dei domini posseduti o definiti dal cliente.
  - **Reputazione URL EOP** : reputazione URL dannosi.
  - **Filtro generale phishing** : segnali di phishing basati sulle regole dell'analista. 
  - **Altri**
  - Messaggi di phishing di **phishing zap**<sup>2</sup>: zero hour.
  - **Detonazione URL**<sup>1</sup>
  - **Rappresentazione utente**<sup>1</sup>: rappresentazione degli utenti definiti dall'amministratore o appresa tramite Intelligence delle cassette postali.

  ![Visualizzazione della tecnologia di rilevamento per la posta elettronica di phishing nel rapporto sullo stato della protezione dalle minacce](../../media/threat-protection-status-report-phishing-detection-tech-view.png)

- **Scomposizione per: tecnologia di rilevamento** e **visualizzazione dei dati in base a: posta elettronica \> malware** : vengono visualizzate le informazioni seguenti:

  - **Reputazione dei file generati dal trifosfato di adenosina**<sup>1</sup>: la reputazione di tutti i file dannosi generati da detonazioni ATP.
  - **Motore anti-malware**<sup>1</sup>: rilevamento da motori antimalware.
  - **Blocco dei tipi di file di criteri antimalware** : si tratta di messaggi di posta elettronica filtrati a causa del tipo di file dannoso identificato nel messaggio.
  - **Detonazione file**<sup>1</sup>: la detonazione dei file viene intercettata da allegati sicuri.  
  - **Reputazione di file dannosi**
  - **Malware zap**<sup>2</sup>
  - **Altri**

  ![Visualizzazione della tecnologia di rilevamento per malware nel rapporto sullo stato della protezione dalle minacce](../../media/threat-protection-status-report-malware-detection-tech-view.png)

- **Scomposizione per: tipo di criterio** e **visualizzazione dei dati in base a: posta elettronica \> phishing** o **visualizzazione dati per: posta elettronica \> malware** : vengono visualizzate le informazioni seguenti:

  - **Anti-malware**
  - **Allegato sicuro**<sup>1</sup>
  - **Anti-phishing**
  - **Protezione da posta indesiderata**
  - **Regola del flusso di posta** (nota anche come regola di trasporto)
  - **Altri**

  ![Visualizzazione dei tipi di criteri per la posta elettronica di phishing nel rapporto sullo stato di protezione di minacce](../../media/threat-protection-status-report-phishing-policy-type-view.png)

- **Scomposizione per: stato di recapito** e **visualizzazione dei dati in base a: posta elettronica \> phishing** oppure **visualizzare i dati per: posta elettronica \> malware** : vengono visualizzate le informazioni seguenti:

  - **Recapito non riuscito**
  - **Interrotte**
  - **Inoltrato**
  - **Cassetta postale ospitata: cartella personalizzata**
  - **Cassetta postale ospitata: elementi eliminati**
  - **Cassetta postale ospitata: posta in arrivo**
  - **Cassetta postale ospitata: posta indesiderata**
  - **Server locale: recapitato**
  - **Quarantena**

  ![Visualizzazione stato di recapito per il messaggio di posta elettronica di phishing nel rapporto sullo stato di protezione](../../media/threat-protection-status-report-phishing-delivery-status-view.png)

<sup>1</sup> difensore solo per Office 365

<sup>2</sup> zero-hour auto Purge (ZAP) non è disponibile in EOP autonomo (funziona solo nelle cassette postali di Exchange Online).

Se si fa clic su **filtri** , i filtri disponibili dipendono dal grafico che si sta cercando:

Per **il \> malware contenuto** , è possibile modificare il rapporto in base alla data di **inizio** e di **fine** e il valore di **rilevamento** .

Per la **sostituzione dei messaggi** , è possibile modificare il report con i filtri seguenti:

- Data di **inizio** e **Data di fine**
- **Motivo dell'override**
- **Tag** : filtrare in base al tag per restituire gli utenti o i gruppi a cui è stato applicato un tag specifico. Per ulteriori informazioni sui tag degli utenti, vedere [tag utente](user-tags.md).
- **Dominio**

Per tutte le altre visualizzazioni, è possibile modificare il report con i filtri seguenti:

- Data di **inizio** e **Data di fine**
- **Rilevamento**
- **Protetto da** : **ATP** o **EOP**
- **Tag** : filtrare in base al tag per restituire gli utenti o i gruppi a cui è stato applicato un tag specifico. Per ulteriori informazioni sui tag degli utenti, vedere [tag utente](user-tags.md).
- **Dominio**

### <a name="details-table-view-for-the-threat-protection-status-report"></a>Visualizzazione della tabella dei dettagli per il rapporto sullo stato della protezione dalle minacce

Se si fa clic su **Visualizza tabella dettagli** , le informazioni visualizzate dipendono dal grafico che si sta esaminando:

- **Visualizzare i dati in base a: content \> Malware** :

  - **Data**
  - **Posizione**
  - **Diretto da**
  - **Nome malware**

Se si fa clic su **filtri** in questa visualizzazione, è possibile modificare il rapporto per data di **inizio** e **Data di fine** e il valore di **rilevamento** .

- **Visualizzare i dati in base a: override del messaggio** :

  - **Data**
  - **Oggetto**
  - **Mittente**
  - **Destinatari**
  - **Rilevato da**
  - **Motivo dell'override**
  - **Origine del compromesso**
  - **Tag**

Se si fa clic su **filtri** in questa visualizzazione, è possibile modificare il report con i filtri seguenti:

- Data di **inizio** e **Data di fine**
- **Motivo dell'override**
- **Tag** : filtrare in base al tag per restituire gli utenti o i gruppi a cui è stato applicato un tag specifico. Per ulteriori informazioni sui tag degli utenti, vedere [tag utente](user-tags.md).
- **Dominio**
- **Destinatari** (si noti che questa proprietà filtrabile è disponibile solo nella visualizzazione tabella Dettagli)

**Visualizzazione dei dati per: Panoramica** : non è disponibile alcun pulsante **Visualizza dettagli tabella** .

- Tutti gli altri grafici:

  - **Data**
  - **Oggetto**
  - **Mittente**
  - **Destinatari**
  - **Rilevato da**
  - **Stato del recapito**
  - **Origine del compromesso**
  - **Tag**

Se si fa clic su **filtri** , è possibile modificare il report con i filtri seguenti:

- Data di **inizio** e **Data di fine**
- **Rilevamento**
- **Protetto da** : **difensore per Office 365** o **EOP**
- **Tag** : filtrare in base al tag per restituire gli utenti o i gruppi a cui è stato applicato un tag specifico. Per ulteriori informazioni sui tag degli utenti, vedere [tag utente](user-tags.md).
- **Dominio**
- **Destinatari** (si noti che questa proprietà filtrabile è disponibile solo nella visualizzazione tabella Dettagli)

## <a name="top-malware-report"></a>Rapporto malware principale

Il rapporto **malware principale** illustra i diversi tipi di malware rilevati dalla [protezione antimalware in EOP](anti-malware-protection.md).

Per visualizzare il report, aprire il [Centro sicurezza & conformità](https://protection.office.com), accedere al **Reports** \> **Dashboard** dei report e selezionare **malware principale**. Per passare direttamente al report, aprire <https://protection.office.com/reportv2?id=TopMalware> .

![Widget malware principale nel dashboard report](../../media/top-malware-report-widget.png)

Quando si posiziona il puntatore del mouse su un cuneo nel grafico a torta, è possibile visualizzare il nome di un tipo di malware e il numero di messaggi che sono stati rilevati come aventi quel malware.

![Visualizzazione del rapporto di malware principale](../../media/top-malware-report-view.png)

Se si fa clic su **Visualizza tabella dettagli** , è possibile visualizzare i dettagli seguenti:

- **Malware principale**
- **Numero**

Se si fa clic su **filtri** nella visualizzazione visualizzazione report o tabella dettagli, è possibile specificare un intervallo di date con data di **inizio** e **Data di fine**.

## <a name="url-threat-protection-report"></a>Report sulla protezione dalle minacce URL

Il **rapporto sulla protezione delle minacce URL** è disponibile in Microsoft Defender per Office 365. Per ulteriori informazioni, vedere [URL Threat Protection report](view-reports-for-atp.md#url-threat-protection-report).

## <a name="user-reported-messages-report"></a>Report dei messaggi segnalati dall'utente

Il rapporto **messaggi segnalati dall'utente** Visualizza informazioni sui messaggi di posta elettronica segnalati dagli utenti come posta indesiderata, tentativi di phishing o una buona corrispondenza tramite il [componente aggiuntivo segnala messaggio](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in).

I dettagli sono disponibili per ogni messaggio, incluso il motivo del recapito, una regola di protezione da posta indesiderata o un flusso di posta configurata per l'organizzazione. Per visualizzare i dettagli, selezionare un elemento nell'elenco User-Reports e quindi visualizzare le informazioni nelle schede **Riepilogo** e **Dettagli** .

![Il rapporto messaggi di User-Reported Visualizza i messaggi che gli utenti sono contrassegnati come posta indesiderata, non indesiderata o tentativi di phishing.](../../media/ad5e9a3d-b833-419c-bcc9-3425d9604ead.png)

Per visualizzare il report, nel [Centro sicurezza & Compliance](https://protection.office.com)eseguire una delle operazioni seguenti:

- Accedere a **Threat management** \> **Dashboard** \> **messaggi segnalati dall'utente** del dashboard di gestione delle minacce.

- Passare a **gestione minacce** \> **esaminare** \> **i messaggi segnalati dall'utente**.

![Nel centro sicurezza & conformità, scegliere \> \> messaggi segnalati dall'utente di Threat Management Review](../../media/e372c57c-1414-4616-957b-bc933b8c8711.png)

> [!IMPORTANT]
> Affinché il rapporto messaggi segnalati dall'utente funzioni correttamente, **è necessario che la registrazione di controllo sia attivata** per l'ambiente Office 365. Questa operazione viene in genere fatta da una persona a cui è stato assegnato il ruolo registri di controllo in Exchange Online. Per ulteriori informazioni, vedere [attivazione o disattivazione della ricerca del registro di controllo di Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off).

## <a name="what-permissions-are-needed-to-view-these-reports"></a>Quali autorizzazioni sono necessarie per visualizzare i rapporti?

Per visualizzare e utilizzare i report, è necessario essere membri del gruppo di ruoli specificato nel centro sicurezza & conformità **e** in Exchange Online.

- Nel centro sicurezza & conformità è necessario essere membri di uno dei gruppi di ruoli seguenti:

  -Organization Management-Security Administrator (è possibile farlo anche nell'interfaccia di [amministrazione di Azure Active Directory](https://aad.portal.azure.com) -Security Reader

  Per altre informazioni, vedere [Autorizzazioni nel Centro sicurezza e conformità](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).

- In Exchange Online, è necessario essere membri di uno dei gruppi di ruoli seguenti:

  -Gestione organizzazione-solo visualizzazione organizzazione-destinatari di sola visualizzazione-gestione della conformità

Per ulteriori informazioni, vedere [autorizzazioni in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) e [gestire i gruppi di ruoli in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).

## <a name="what-if-the-reports-arent-showing-data"></a>Cosa succede se i rapporti non mostrano dati?

Se i dati non vengono visualizzati nei rapporti, verificare che i criteri siano configurati correttamente. Per ulteriori informazioni, vedere [protezione dalle minacce](protect-against-threats.md).

## <a name="related-topics"></a>Argomenti correlati

[Protezione da posta indesiderata e anti-malware in EOP](anti-spam-and-anti-malware-protection.md)

[Report intelligenti e informazioni dettagliate nel Centro sicurezza e conformità](reports-and-insights-in-security-and-compliance.md)

[Visualizzare i report sul flusso di posta elettronica nel centro sicurezza & Compliance](view-mail-flow-reports.md)

[Visualizzare i report per il difensore per Office 365](view-reports-for-atp.md)
