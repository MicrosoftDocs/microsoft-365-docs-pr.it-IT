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
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 3a137e28-1174-42d5-99af-f18868b43e86
ms.collection:
- M365-security-compliance
description: Informazioni su come trovare e utilizzare i report di sicurezza della posta elettronica per l'organizzazione. I report di sicurezza della posta elettronica sono disponibili nel Centro sicurezza & conformità.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f6d9f149c9e1c71532018e6b43a6e9e31eb04607
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290800"
---
# <a name="view-email-security-reports-in-the-security--compliance-center"></a>Visualizzare i report sulla sicurezza della posta elettronica nel Centro sicurezza e conformità

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Nel Centro sicurezza e conformità sono disponibili diversi report che consentono di vedere in che modo le funzionalità di sicurezza della posta elettronica, ad esempio la protezione da posta indesiderata, antimalware e crittografia in Microsoft 365, proteggono l'organizzazione. [&](https://protection.office.com) Se si dispone delle [autorizzazioni necessarie,](#what-permissions-are-needed-to-view-these-reports)è possibile visualizzare questi report nel Centro sicurezza & conformità selezionando **Dashboard** \> **report.** Per passare direttamente al dashboard dei report, aprire <https://protection.office.com/insightdashboard> .

![Dashboard report nel Centro sicurezza & conformità](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="compromised-users-report"></a>Report degli utenti compromessi

> [!NOTE]
> Questo report è disponibile nelle organizzazioni di Microsoft 365 con cassette postali di Exchange Online. Non è disponibile nelle organizzazioni Exchange Online Protection (EOP) autonome.

Il **report Utenti compromessi** mostra il numero di  account  utente contrassegnati come sospetti o con restrizioni negli ultimi 7 giorni. Gli account in uno di questi stati sono problematici o addirittura compromessi. Con un uso frequente, puoi usare il report per individuare picchi e persino tendenze in account sospetti o con restrizioni. Per ulteriori informazioni sugli utenti compromessi, vedere [Risposta a un account di posta elettronica compromesso.](responding-to-a-compromised-email-account.md)

![Widget Utenti compromessi nel dashboard report](../../media/compromised-users-report-widget.png)

La visualizzazione aggregata mostra i dati degli ultimi 90 giorni e la visualizzazione dettagli mostra i dati degli ultimi 30 giorni.

Per visualizzare il report, aprire il [Centro sicurezza & conformità,](https://protection.office.com)passare **al** dashboard dei report e \>  selezionare **Utenti compromessi.** Per passare direttamente al report, aprire <https://protection.office.com/reportv2?id=CompromisedUsers> .

È possibile filtrare sia il grafico che la tabella dei dettagli facendo clic su **Filtri** e selezionando uno o più dei valori seguenti:

- **Data di inizio** **e data di fine**

- **Sospetto:** l'account utente ha inviato messaggi di posta elettronica sospetti e rischia di essere limitato all'invio di posta elettronica.

- **Con restrizioni:** all'account utente è stato limitato l'invio di posta elettronica a causa di modelli altamente sospetti.

![Visualizzazione report nel report Utenti compromessi](../../media/compromised-users-report-activity-view.png)

Se si fa **clic su Visualizza tabella dettagli,** è possibile visualizzare i dettagli seguenti:

- **Ora creazione**
- **ID utente**
- **Azione**

Per tornare alla visualizzazione report, fare clic su **Visualizza report.**

## <a name="encryption-report"></a>Report Crittografia

Il **rapporto crittografia** è disponibile in EOP (sottoscrizioni con cassette postali in Exchange Online o EOP autonomo senza cassette postali di Exchange Online). Il team di sicurezza dell'organizzazione può utilizzare le informazioni contenute in questo report per identificare i modelli e applicare o modificare in modo proattivo i criteri per i messaggi di posta elettronica sensibili. Ad esempio:

- Se viene visualizzato un numero elevato di messaggi di posta elettronica crittografati dagli utenti, è possibile aggiungere un criterio di crittografia per automatizzare la crittografia per determinati casi d'uso. Per ulteriori informazioni, vedere [Definire le regole del flusso di posta per crittografare i messaggi di posta elettronica in Microsoft 365.](../../compliance/define-mail-flow-rules-to-encrypt-email.md)

- Se sono disponibili diversi modelli di crittografia, ma nessuno li sta utilizzando, è possibile decidere se gli utenti necessitano di formazione delle funzionalità.

La visualizzazione aggregata consente il filtro per gli ultimi 90 giorni, mentre la visualizzazione dettagli consente il filtro per 10 giorni.

Per visualizzare il report, aprire il [Centro sicurezza & conformità,](https://protection.office.com)passare **al** \> **dashboard dei report** e selezionare **Report di crittografia.** Per passare direttamente al report, aprire <https://protection.office.com/reportv2?id=EncryptionReport> .

Per ulteriori informazioni sulla crittografia, vedere [Crittografia della posta elettronica in Microsoft 365.](../../compliance/email-encryption.md)

### <a name="report-view-for-the-encryption-report"></a>Visualizzazione report per il report Crittografia

Nel grafico è possibile utilizzare i filtri seguenti:

- **Visualizzare i dati in base a: Rapporto crittografia** messaggi e Scomposi **per: Metodo di crittografia**: Sono disponibili i seguenti metodi di crittografia:

  - **Crittografia per utente**
  - **Crittografia in base ai criteri**

  Se si fa **clic su Filtri,** è possibile modificare il grafico con i filtri seguenti:

  - **Data di inizio** **e data di fine**
  - Metodo di crittografia.
  - Modello di crittografia.

- **Visualizzare i dati in base a: Rapporto crittografia** messaggi e Scomposi **per: Modello di crittografia:** sono disponibili i seguenti metodi di crittografia:

  - **Non inoltrare**
  - **Solo crittografia**
  - **OME precedente**
  - **Personalizzato**

  Se si fa **clic su Filtri,** è possibile modificare il grafico con i filtri seguenti:

  - **Data di inizio** **e data di fine**
  - Metodo di crittografia
  - Modello di crittografia

- **Visualizzare i dati per: Primi 5** domini destinatario : questa visualizzazione mostra un grafico a torta con i conteggi dei messaggi inviati per i primi 5 domini destinatario.

  Se si fa **clic su Filtri,** è possibile selezionare una **data di inizio e** una di **fine.**

### <a name="details-table-view-for-the-encryption-report"></a>Visualizzazione della tabella dei dettagli per il report Crittografia

Se si **fa clic su Visualizza tabella dettagli,** le informazioni visualizzate dipendono dal grafico visualizzato:

- **Scomporsi per: metodo di crittografia** o **scomporsi per: modello di crittografia**: vengono visualizzate le informazioni seguenti:

  - **Data**
  - **Indirizzo del mittente**
  - **Modello di crittografia**
  - **Metodo di crittografia**
  - **Indirizzo destinatario**
  - **Oggetto**

- **Visualizzare i dati in base a: 5 domini destinatario principali:**

  - **Data**
  - **Dominio destinatario**
  - **Numero messaggi**

Se si fa **clic su Filtri** in una visualizzazione tabella dei dettagli, è possibile modificare i risultati con i filtri seguenti:

- **Data di inizio** **e data di fine**
- Metodo di crittografia
- Modello di crittografia

Per tornare alla visualizzazione report, fare clic su **Visualizza report.**

## <a name="mailflow-status-report"></a>Rapporto sullo stato del flusso di posta

Il **rapporto sullo stato del flusso di posta** contiene informazioni sui messaggi bloccati di malware, posta indesiderata, phishing e edge. Per ulteriori dettagli, vedere [Mailflow status report.](view-mail-flow-reports.md#mailflow-status-report)

## <a name="malware-detections-in-email-report"></a>Rilevamenti di malware nel report di posta elettronica

I **rilevamenti di malware nel** rapporto di posta elettronica mostrano informazioni sui rilevamenti di malware nei messaggi di posta elettronica in arrivo e in uscita (malware rilevato da Exchange Online Protection o EOP). Per ulteriori informazioni sulla protezione antimalware in EOP, vedere [Protezione antimalware in EOP.](anti-malware-protection.md)

 Il filtro di visualizzazione aggregata consente 90 giorni, mentre il filtro della tabella dei dettagli consente solo 10 giorni.

Per visualizzare il report, aprire il [Centro sicurezza & conformità,](https://protection.office.com)passare al dashboard dei report e selezionare  \>  **Rilevamenti malware nella posta elettronica.** Per passare direttamente al report, aprire <https://protection.office.com/reportv2?id=MalwareDetections> .

![Rilevamenti di malware nel widget di posta elettronica nel dashboard dei report](../../media/malware-detections-widget.png)

È possibile filtrare sia il grafico che la tabella dei dettagli facendo clic **su Filtri** e selezionando:

- **Data di inizio** **e data di fine**
- **In ingresso**
- **In uscita**

![Visualizzazione report nel report rilevamento malware nel report di posta elettronica](../../media/malware-detections-report-view.png)

Se si fa **clic su Visualizza tabella dettagli,** è possibile visualizzare i dettagli seguenti:

- **Data**
- **Indirizzo del mittente**
- **Indirizzo destinatario**
- **ID messaggio:** disponibile nel campo **di intestazione Message-ID** nell'intestazione del messaggio e deve essere univoco. Un valore di esempio è `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (si notino le parentesi uncinate).
- **Oggetto**
- **Filename**
- **Nome malware**

Per tornare alla visualizzazione report, fare clic su **Visualizza report.**

## <a name="mail-latency-report"></a>Rapporto latenza posta

Il **rapporto latenza della posta** contiene informazioni sulla latenza di recapito e detonazione della posta riscontrata all'interno dell'organizzazione. Per ulteriori informazioni, vedere [Mail latency report.](view-reports-for-atp.md#mail-latency-report)

## <a name="sent-and-received-email-report"></a>Rapporto di posta elettronica inviato e ricevuto

Il **rapporto di posta elettronica** inviato e ricevuto contiene informazioni su malware, posta indesiderata, regole del flusso di posta (note anche come regole di trasporto) e rilevamenti di malware avanzati dopo l'ingresso della posta elettronica nel servizio. Per ulteriori informazioni, vedere [Report di posta elettronica inviati e ricevuti.](view-mail-flow-reports.md#sent-and-received-email-report)

## <a name="spam-detections-report"></a>Report sui rilevamenti della posta indesiderata

Il **rapporto rilevamenti posta indesiderata** mostra i messaggi di posta indesiderata bloccati da EOP. I messaggi vengono conteggiati singolarmente, non per destinatario. Ad esempio, se lo stesso messaggio di posta indesiderata è stato inviato a 100 destinatari nell'organizzazione, viene conteggiato come un unico messaggio.

La visualizzazione aggregata consente un filtro di 90 giorni, mentre la tabella dei dettagli consente un filtro di 10 giorni.

Per visualizzare il report, aprire il [Centro sicurezza & conformità,](https://protection.office.com)passare al dashboard dei report  \> **e** selezionare **Rilevamenti posta indesiderata.** Per passare direttamente al report, aprire <https://protection.office.com/reportv2?id=SpamDetections> .

![Widget Rilevamenti posta indesiderata nel dashboard report](../../media/spam-detections-report-widget.png)

Per ulteriori informazioni sulla protezione da posta indesiderata, vedere Protezione da posta [indesiderata in EOP.](anti-spam-protection.md)

### <a name="report-view-for-the-spam-detections-report"></a>Visualizzazione rapporto per il rapporto rilevamenti di posta indesiderata

Nella visualizzazione report sono disponibili i grafici seguenti:

- **Scomporsi per: Azione**: vengono visualizzati i tipi di evento seguenti:

  - **Contenuto di posta indesiderata filtrato**
  - **Blocco IP di posta indesiderata**
  - **Blocco di buste di posta indesiderata**
  - **Filtro DBEB di posta indesiderata**: Blocco edge basato su directory (DBEB)

  Quando si passa il puntatore del mouse su un giorno (punto dati) nel grafico, è possibile vedere quanti elementi sono stati bloccati quel giorno e come tali elementi vengono categorizzati.

  ![Visualizzazione azioni nel rapporto rilevamenti posta indesiderata](../../media/spam-detections-report-action-view.png)

- **Scomporsi per: Direzione**: vengono visualizzate le seguenti indicazioni:

  - **In ingresso**
  - **In uscita**

  ![Visualizzazione della direzione nel rapporto rilevamenti posta indesiderata](../../media/spam-detections-report-direction-view.png)

Se si fa **clic su Filtri** in una visualizzazione report, è possibile modificare i risultati con i filtri seguenti:

- **Data di inizio** **e data di fine**
- Valori di direzione
- Valori del tipo di evento

### <a name="details-table-view-for-the-spam-detections-report"></a>Visualizzazione della tabella dei dettagli per il rapporto sui rilevamenti di posta indesiderata

Se si fa **clic su Visualizza tabella dettagli** in qualsiasi visualizzazione report, vengono visualizzate le informazioni seguenti:

- **Data**
- **Indirizzo del mittente**
- **Indirizzo destinatario**
- **Tipo evento**
- **Azione**
- **Oggetto**

Se si fa **clic su Filtri** in una tabella dei dettagli, è possibile modificare i risultati con i filtri seguenti:

- **Data di inizio** **e data di fine**
- Valori di direzione
- Valori del tipo di evento

Per tornare alla visualizzazione report, fare clic su **Visualizza report.**

## <a name="spoof-detections-report"></a>Report rilevamenti spoof

Il **report falsificazioni** mostra quanti messaggi di posta falsificati sono stati rilevati e di quelli considerati "buoni" (falsificati per motivi aziendali legittimi). Per ulteriori informazioni sullo spoofing, vedere [Protezione anti-spoofing in EOP.](anti-spoofing-protection.md)

La visualizzazione aggregata del report consente 90 giorni di filtro, mentre la visualizzazione dettagli consente solo dieci giorni di filtro.

Per visualizzare il report, aprire il [Centro sicurezza & conformità,](https://protection.office.com)passare **al** \> **dashboard dei report e** selezionare **Rilevamenti spoofing.** Per passare direttamente al report, aprire <https://protection.office.com/reportv2?id=SpoofMailReport> .

![Widget Falsificazioni nel dashboard report](../../media/spoof-detections-widget.png)

Quando si passa il puntatore del mouse su un giorno (punto dati) nel grafico, è possibile vedere quanti messaggi di posta falsificati sono stati ricevuti.

È possibile filtrare sia il grafico che la tabella dei dettagli facendo clic su **Filtri** e selezionando uno o più dei valori seguenti:

- **Data di inizio** **e data di fine**

- **Posta buona**

- **Intercettato come posta indesiderata**

![Visualizzazione report nel report Rilevamenti spoofing](../../media/spoof-detections-report-view.png)

Se si fa **clic su Visualizza tabella dettagli,** è possibile visualizzare i dettagli seguenti:

- **Data**
- **Mittente falsificato**
- **Mittente vero**
- **Indirizzo IP mittente**
- **Azione**
- **Numero messaggi**

Per tornare alla visualizzazione report, fare clic su **Visualizza report.**

## <a name="threat-protection-status-report"></a>Report dello stato di protezione dalle minacce

La **relazione sullo stato di** Protezione dalle minacce è disponibile sia in EOP che in Microsoft Defender per Office 365; Tuttavia, i report contengono dati diversi. Ad esempio, i clienti EOP possono visualizzare informazioni sul malware rilevato nella posta elettronica, ma non informazioni sui file dannosi rilevati da Allegati sicuri [per SharePoint, OneDrive e Microsoft Teams.](atp-for-spo-odb-and-teams.md)

Il report fornisce il conteggio dei messaggi di posta elettronica con contenuti dannosi, ad esempio file o indirizzi di siti Web (URL) bloccati dal motore antimalware, [zero-hour auto purge (ZAP)](zero-hour-auto-purge.md)e le funzionalità di Defender per Office 365 come collegamenti sicuri, allegati sicuri e [anti-phishing.](set-up-anti-phishing-policies.md) [](atp-safe-links.md) [](atp-safe-attachments.md) È possibile utilizzare queste informazioni per identificare le tendenze o determinare se i criteri dell'organizzazione devono essere rettificati.

**Nota:** è importante comprendere che se un messaggio viene inviato a cinque destinatari, viene conteggiato come cinque messaggi diversi e non un messaggio.

Per visualizzare il report, aprire il [Centro sicurezza & conformità,](https://protection.office.com)passare al dashboard dei report  \> **e** selezionare Lo **stato di Protezione dalle minacce.** Per passare direttamente al report, aprire uno degli URL seguenti:

- Microsoft Defender per Office 365: <https://protection.office.com/reportv2?id=TPSAggregateReportATP>
- EOP: <https://protection.office.com/reportv2?id=TPSAggregateReport>

![Widget stato di protezione dalle minacce nel dashboard report](../../media/threat-protection-status-report-widget.png)

Per impostazione predefinita, il grafico mostra i dati degli ultimi 7 giorni. Se si fa **clic su Filtri,** è possibile selezionare un intervallo di date di 90 giorni (le sottoscrizioni di valutazione potrebbero essere limitate a 30 giorni). La visualizzazione della tabella dei dettagli consente il filtro per 30 giorni.

### <a name="report-view-for-the-threat-protection-status-report"></a>Visualizzazione report per il rapporto sullo stato di Protezione dalle minacce

Sono disponibili le visualizzazioni seguenti:

- **Visualizzare i dati in base a: Panoramica:** vengono visualizzate le seguenti informazioni di rilevamento:

  - **Malware di posta elettronica**
  - **E-mail phish**
  - **Malware contenuto**

  ![Visualizzazione Panoramica nel rapporto sullo stato di Protezione dalle minacce](../../media/threat-protection-status-report-overview-view.png)

- **Visualizzare i dati per: contenuto \> Malware**<sup>1:</sup>vengono visualizzate le seguenti informazioni per Microsoft Defender per le organizzazioni di Office 365:

  - **Motore antimalware:** file dannosi rilevati in Sharepoint, OneDrive e Microsoft Teams dal rilevamento di [virus predefinito in Microsoft 365.](virus-detection-in-spo.md)
  - **Detonazione file:** file dannosi rilevati [da Allegati sicuri per SharePoint, OneDrive e Microsoft Teams.](atp-for-spo-odb-and-teams.md)

  ![Visualizzazione malware del contenuto nel rapporto sullo stato di Protezione dalle minacce](../../media/threat-protection-status-report-content-malware-view.png)

- **Visualizzare i dati in base a: Sostituzione messaggio**: vengono visualizzate le seguenti informazioni sul motivo della sostituzione:

  - **Ignora locale**
  - **IP consentiti**
  - **Regola del flusso di posta**
  - **Mittente consentito**
  - **Dominio consentito**
  - **ZAP non abilitato**
  - **Cartella Posta indesiderata non abilitata**
  - **Mittente sicuro dell'utente**
  - **Dominio sicuro dell'utente**

  ![Visualizzazione sostituzione messaggio nel rapporto sullo stato di Protezione dalle minacce](../../media/threat-protection-status-report-message-override-view.png)

- **Scomporsi per: tecnologia di rilevamento** **e visualizzazione dei dati per: e-mail \> phish**: Vengono visualizzate le seguenti informazioni:

  - **Reputazione URL generata da ATP**<sup>1:</sup>reputazione degli URL dannosi generata dalle detonazioni di Defender per Office 365 in altri clienti di Microsoft 365.
  - **Filtro phishing avanzato:** segnali di phishing basati sull'apprendimento automatico.
  - **Anti-spoofing - Errore DMARC:** errore di autenticazione DMARC nei messaggi.
  - **Anti-spoofing - intra-org:** il mittente sta tentando di effettuare lo spoofing del dominio del destinatario.
  - **Anti-spoofing - dominio esterno:** il mittente sta tentando di effettuare lo spoofing di un altro dominio.
  - **Rappresentazione del marchio**: rappresentazione di marchi noti in base ai mittenti.
  - **Rappresentazione del dominio**<sup>1</sup>: Rappresentazione dei domini che il cliente possiede o definisce.
  - **Reputazione URL EOP**: reputazione URL dannoso.
  - **Filtro phishing generale:** segnali di phishing basati sulle regole dell'analista.
  - **Altri**
  - **Phishing ZAP**<sup>2:</sup>eliminazione automatica dei messaggi di phishing a zero ore.
  - **Detonazione URL**<sup>1</sup>
  - **Rappresentazione utente**<sup>1</sup>: Rappresentazione degli utenti definiti dall'amministratore o appresi tramite l'intelligence delle cassette postali.

  ![Visualizzazione della tecnologia di rilevamento per la posta elettronica di phishing nel rapporto sullo stato di Protezione dalle minacce](../../media/threat-protection-status-report-phishing-detection-tech-view.png)

- **Scomporsi per: tecnologia di rilevamento** **e visualizzazione dei dati per: \> Malware** di posta elettronica : vengono visualizzate le seguenti informazioni:

  - **Reputazione file generata da ATP**<sup>1:</sup>tutta la reputazione dei file dannosi generata da Defender per le detonazioni di Office 365.
  - **Motore antimalware**<sup>1:</sup>rilevamento da motori antimalware.
  - **Blocco del tipo di file dei** criteri antimalware: si tratta di messaggi di posta elettronica filtrati a causa del tipo di file dannoso identificato nel messaggio.
  - **Detonazione del file**<sup>1:</sup>rilevamento tramite allegati sicuri.
  - **Reputazione di file dannosi**
  - **Malware ZAP**<sup>2</sup>
  - **Altri**

  ![Visualizzazione della tecnologia di rilevamento per il malware nel rapporto sullo stato di Protezione dalle minacce](../../media/threat-protection-status-report-malware-detection-tech-view.png)

- **Scomporsi per: Tipo** di criterio e Visualizza dati **per: Email \> Phish** or **View data by: Email \> Malware**: The following information is shown:

  - **Antimalware**
  - **Allegati sicuri**<sup>1</sup>
  - **Anti-phish**
  - **Protezione da posta indesiderata**
  - **Regola del flusso di** posta (nota anche come regola di trasporto)
  - **Altri**

  ![Visualizzazione del tipo di criterio per la posta elettronica di phishing nel rapporto sullo stato di Protezione dalle minacce](../../media/threat-protection-status-report-phishing-policy-type-view.png)

- **Scomporsi per: Stato del recapito** e Visualizza dati **per: \> E-mail Phish** o **View data by: Email \> Malware**: The following information is shown:

  - **Recapito non riuscito**
  - **Rilasciato**
  - **Inoltrato**
  - **Cassetta postale ospitata: cartella personalizzata**
  - **Cassetta postale ospitata: elementi eliminati**
  - **Cassetta postale ospitata: Posta in arrivo**
  - **Cassetta postale ospitata: Posta indesiderata**
  - **Server locale: recapitato**
  - **Quarantena**

  ![Visualizzazione dello stato del recapito per la posta elettronica di phishing nel rapporto sullo stato di Protezione dalle minacce](../../media/threat-protection-status-report-phishing-delivery-status-view.png)

<sup>1</sup> Defender solo per Office 365

<sup>2</sup> Zero-hour auto purge (ZAP) isn't available in standalone EOP (it only works in Exchange Online mailboxes).

Se si fa **clic su Filtri,** i filtri disponibili dipendono dal grafico che si stava osservando:

- Per **Visualizzare i dati in base a: \> Malware** contenuto, è possibile modificare il report in base alla data di inizio **e** alla data **di fine** e al **valore di** rilevamento.

- Per **Visualizza dati in base a: Sostituzione messaggio,** è possibile modificare il report con i filtri seguenti:

  - **Data di inizio** **e data di fine**
  - **Motivo sostituzione**
  - **Tag:** filtra i risultati in base a utenti o gruppi a cui è stato applicato il tag utente specificato (inclusi gli account di priorità). Per ulteriori informazioni sui tag utente, vedere [Tag utente.](user-tags.md)
  - **Dominio**

- Per tutte le altre visualizzazioni, è possibile modificare il report con i filtri seguenti:

  - **Data di inizio** **e data di fine**
  - **Rilevamento**
  - **Protetto da**: **ATP** o **EOP**
  - **Tag:** filtra i risultati in base a utenti o gruppi a cui è stato applicato il tag utente specificato (inclusi gli account di priorità). Per ulteriori informazioni sui tag utente, vedere [Tag utente.](user-tags.md)
  - **Dominio**

### <a name="details-table-view-for-the-threat-protection-status-report"></a>Visualizzazione della tabella dei dettagli per il rapporto sullo stato di Protezione dalle minacce

Se si **fa clic su Visualizza tabella dettagli,** le informazioni visualizzate dipendono dal grafico visualizzato:

- **Visualizza dati in base a: Panoramica:** non **è disponibile** il pulsante Visualizza tabella dettagli.

- **Visualizzare i dati per: contenuto \> Malware:**

  - **Data**
  - **Posizione**
  - **Diretto da**
  - **Nome malware**

  Se si fa **clic su** Filtri in questa visualizzazione, è possibile modificare il report in base alla data di inizio **e** alla data **di fine** e al **valore di** rilevamento.

- **Visualizzare i dati in base a: Sostituzione messaggio:**

  - **Data**
  - **Oggetto**
  - **Mittente**
  - **Destinatari**
  - **Rilevato da**
  - **Motivo sostituzione**
  - **Origine della compromissione**
  - **Tag**

  Se si fa **clic su** Filtri in questa visualizzazione, è possibile modificare il report con i filtri seguenti:

  - **Data di inizio** **e data di fine**
  - **Motivo sostituzione**
  - **Tag:** filtra i risultati in base a utenti o gruppi a cui è stato applicato il tag utente specificato (inclusi gli account di priorità). Per ulteriori informazioni sui tag utente, vedere [Tag utente.](user-tags.md)
  - **Dominio**
  - **Destinatari** (si noti che questa proprietà filtrabile è disponibile solo nella visualizzazione tabella dei dettagli)

- Tutti gli altri grafici:

  - **Data**
  - **Oggetto**
  - **Mittente**
  - **Destinatari**
  - **Rilevato da**
  - **Stato recapito**
  - **Origine della compromissione**
  - **Tag**

  Se si fa **clic su Filtri,** è possibile modificare il report con i filtri seguenti:

  - **Data di inizio** **e data di fine**
  - **Rilevamento**
  - **Protetto da**: **Defender per Office 365** o **EOP**
  - **Tag:** filtra i risultati in base a utenti o gruppi a cui è stato applicato il tag utente specificato (inclusi gli account di priorità). Per ulteriori informazioni sui tag utente, vedere [Tag utente.](user-tags.md)
  - **Dominio**
  - **Destinatari** (si noti che questa proprietà filtrabile è disponibile solo nella visualizzazione tabella dei dettagli)

## <a name="top-malware-report"></a>Report principale sul malware

Il **report malware** principale mostra i vari tipi di malware rilevati dalla protezione [antimalware in EOP.](anti-malware-protection.md)

Per visualizzare il report, aprire il [Centro sicurezza & conformità,](https://protection.office.com)passare **al** \> **dashboard dei report e** selezionare **Malware principale.** Per passare direttamente al report, aprire <https://protection.office.com/reportv2?id=TopMalware> .

![Widget malware principale nel dashboard report](../../media/top-malware-report-widget.png)

Quando si passa il mouse su un cuneo nel grafico a torta, è possibile visualizzare il nome di un tipo di malware e il numero di messaggi rilevati come malware.

![Visualizzazione principale del report antimalware](../../media/top-malware-report-view.png)

Se si fa **clic su Visualizza tabella dettagli,** è possibile visualizzare i dettagli seguenti:

- **Malware principale**
- **Numero**

Se si fa **clic su Filtri** nella visualizzazione report o nella visualizzazione tabella dei dettagli, è possibile specificare un intervallo di date con Data di **inizio** e Data **di fine.**

## <a name="url-threat-protection-report"></a>Report di protezione dalle minacce URL

Il **report di protezione dalle minacce URL** è disponibile in Microsoft Defender per Office 365. Per ulteriori informazioni, vedere il [report di protezione dalle minacce URL.](view-reports-for-atp.md#url-threat-protection-report)

## <a name="user-reported-messages-report"></a>Rapporto messaggi segnalati dall'utente

Il **rapporto** Messaggi segnalati dall'utente mostra informazioni sui messaggi di posta elettronica segnalati [](enable-the-report-message-add-in.md) dagli utenti come posta indesiderata, tentativi di phishing o buona posta utilizzando il componente aggiuntivo Segnala messaggio o Il componente aggiuntivo Segnala [phishing.](enable-the-report-phish-add-in.md)

Sono disponibili dettagli per ogni messaggio, incluso il motivo del recapito, ad esempio un'eccezione del criterio di posta indesiderata o una regola del flusso di posta configurata per l'organizzazione. Per visualizzare i dettagli, selezionare un elemento nell'elenco dei report utente e quindi visualizzare le informazioni nelle schede **Riepilogo** **e** Dettagli.

![Il User-Reported messaggi di posta elettronica mostra i messaggi etichettati come posta indesiderata, non posta indesiderata o tentativi di phishing.](../../media/ad5e9a3d-b833-419c-bcc9-3425d9604ead.png)

Per visualizzare questo report, nel [Centro sicurezza & conformità](https://protection.office.com)eseguire una delle operazioni seguenti:

- Passare a **Messaggi segnalati dall'utente** nel \> **dashboard** \> **di gestione delle minacce.**

- Passare a **Verifica messaggi segnalati** \>  \> **dall'utente nella gestione delle minacce.**

![Nel Centro sicurezza & conformità scegliere Gestione minacce \> Esaminare i messaggi segnalati \> dall'utente](../../media/e372c57c-1414-4616-957b-bc933b8c8711.png)

> [!IMPORTANT]
> Per il corretto funzionamento del rapporto Messaggi  segnalati dall'utente, è necessario che la registrazione di controllo sia attivata per l'ambiente di Office 365. Questa operazione viene in genere eseguita da un utente a cui è assegnato il ruolo Registri di controllo in Exchange Online. Per ulteriori informazioni, vedere Attivare o disattivare la ricerca nel log di [controllo di Microsoft 365.](../../compliance/turn-audit-log-search-on-or-off.md)

## <a name="what-permissions-are-needed-to-view-these-reports"></a>Quali autorizzazioni sono necessarie per visualizzare questi report?

Per visualizzare e utilizzare i report descritti in questo articolo, è necessario essere membri di uno dei gruppi di ruoli seguenti nel Centro sicurezza & conformità:

- **Gestione organizzazione**
- **Amministratore della sicurezza**
- **Lettore di sicurezza**
- **Lettore globale**

Per altre informazioni, vedere [Autorizzazioni nel Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).

**Nota:** l'aggiunta di utenti al ruolo Azure Active Directory corrispondente nell'interfaccia di amministrazione di Microsoft  365 offre agli utenti le autorizzazioni necessarie nel Centro sicurezza & e conformità e le autorizzazioni per altre funzionalità di Microsoft 365. Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](../../admin/add-users/about-admin-roles.md).

## <a name="what-if-the-reports-arent-showing-data"></a>Cosa succede se i report non mostrano dati?

Se i dati nei report non vengono visualizzati, verificare che i criteri siano configurati correttamente. Per ulteriori informazioni, vedere [Protezione dalle minacce.](protect-against-threats.md)

## <a name="related-topics"></a>Argomenti correlati

[Protezione antispam e antimalware in EOP](anti-spam-and-anti-malware-protection.md)

[Report intelligenti e informazioni dettagliate nel Centro sicurezza e conformità](reports-and-insights-in-security-and-compliance.md)

[Visualizzare i report del flusso di posta nel Centro sicurezza & conformità](view-mail-flow-reports.md)

[Visualizzare i report per Defender per Office 365](view-reports-for-atp.md)
