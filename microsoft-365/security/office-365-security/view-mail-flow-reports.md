---
title: Visualizzare i report del flusso di posta nel dashboard report
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Gli amministratori possono ottenere informazioni sui report del flusso di posta disponibili nel dashboard Report nel Centro sicurezza & conformità.
ms.custom: ''
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d1fea50ff0eaa5ed7d671485483ecb297b404db9
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50906553"
---
# <a name="view-mail-flow-reports-in-the-reports-dashboard-in-security--compliance-center"></a>Visualizzare i report del flusso di posta nel dashboard report nel Centro sicurezza & conformità

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Oltre ai report del flusso di posta disponibili nel [dashboard](mail-flow-insights-v2.md) del flusso di posta nel Centro sicurezza e conformità di &, nel dashboard report sono disponibili diversi report aggiuntivi sul flusso di posta per monitorare l'organizzazione di Microsoft 365.

Se si dispone delle [autorizzazioni necessarie,](#what-permissions-are-needed-to-view-these-reports)è possibile visualizzare questi report nel Centro [sicurezza & conformità](https://protection.office.com) andando a Dashboard  \> **report.** Per passare direttamente al dashboard dei report, aprire <https://protection.office.com/insightdashboard> .

![Dashboard dei report nel Centro sicurezza & conformità](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="connector-report"></a>Report connettore

Il **report Connettore** mostra l'attività del flusso di posta sui connettori in ingresso [e](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) in uscita configurati per l'organizzazione.

Per visualizzare il report, aprire il [Centro sicurezza & conformità,](https://protection.office.com)passare **a** \> **Dashboard report** e selezionare **Report connettore.** Per passare direttamente al report, aprire <https://protection.office.com/reportv2?id=ConnectorReport> .

![Widget report connettore nel dashboard report](../../media/connector-report-widget.png)

### <a name="report-view-for-the-connector-report"></a>Visualizzazione report per il report Connettore

Nella visualizzazione report sono disponibili i grafici seguenti:

- **View data by: Mail flow**: This chart shows the number of inbound and outbound messages organized by:

  - **Totale**
  - **Da Internet senza connettore**
  - **A Internet senza connettore**
  - Un connettore specifico configurato.

  Per isolare i dati nel grafico, utilizzare il **controllo Mostra dati** per selezionare una di queste opzioni o Tutto il flusso di **posta.**

  ![Visualizzare i dati in base al flusso di posta nel report Connettore](../../media/connector-report-view-data-by-mail-flow.png)

- **Visualizzare i dati per: utilizzo di TLS**: Questo grafico mostra la percentuale di utilizzo della versione TLS (Transport Layer Security) per il flusso di posta.

  Per isolare i dati nel grafico, utilizzare il **controllo Mostra dati** per selezionare una delle opzioni seguenti:

  - **Tutto il flusso di posta**
  - **Da Internet senza connettore**
  - **A Internet senza connettore**
  - Un connettore specifico configurato.

  ![Visualizzare i dati in base all'utilizzo di TLS nel report Connettore](../../media/connector-report-view-data-by-tls-usage.png)

Se si fa **clic su Filtri** in una visualizzazione report, è possibile specificare un intervallo di date con Data di **inizio** e **Data fine.**

### <a name="details-table-view-for-the-connector-report"></a>Visualizzazione tabella dettagli per il report Connettore

Se si fa **clic su Visualizza tabella dettagli** in una visualizzazione report, vengono visualizzate le informazioni seguenti:

- **Data**
- **Direzione e nome del connettore**
- **Tipo di connettore**
- **TLS forzato?**: Il **valore True** o **False**.
- **Nessun TLS** (percentuale)
- **TLS 1.0** (percentuale)
- **TLS 1.1** (percentuale)
- **TLS 1.2** (percentuale)
- **Volume**: numero di messaggi.

Se si fa **clic su Filtri** in una visualizzazione tabella dei dettagli, è possibile specificare un intervallo di date con Data di **inizio** e **Data fine.**

Per tornare alla visualizzazione report, fare clic su **Visualizza report.**

## <a name="exchange-transport-rule-report"></a>Report delle regole di trasporto di Exchange

Il **rapporto sulle regole di trasporto** di Exchange mostra l'effetto delle regole del flusso di posta (note anche come regole di trasporto) sui messaggi in arrivo e in uscita nell'organizzazione.

Per visualizzare il report, aprire il [Centro sicurezza & conformità,](https://protection.office.com)passare **a** \> **Dashboard report** e selezionare **Regola di trasporto di Exchange.** Per passare direttamente al report, aprire <https://protection.office.com/reportv2?id=ETRRuleReport> .

![Widget delle regole di trasporto di Exchange nel dashboard dei report](../../media/transport-rule-report-widget.png)

### <a name="report-view-for-the-exchange-transport-rule-report"></a>Visualizzazione dei report per il report delle regole di trasporto di Exchange

Nella visualizzazione report sono disponibili i grafici seguenti:

- **Visualizzare i dati per: regole di trasporto di Exchange** \> **Scomporsi per: Direzione**: questo grafico  mostra il numero di **messaggi in** ingresso e in uscita interessati dalle regole di trasporto.

- **Visualizzare i dati per: regole di trasporto di Exchange** \> **Scomporsi per: Gravità**: questo grafico mostra il numero **di** messaggi Di gravità elevata e Gravità media e **Gravità** bassa. Il livello di gravità viene impostato come azione nella regola **(** Controlla questa regola con livello di gravità o _SetAuditSeverity_). Per ulteriori informazioni, vedere [Mail flow rule actions in Exchange Online](//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).

- **Visualizzare i dati per: regole di trasporto** \> di Exchange DLP **Scomporsi per: Direzione**: questo grafico  mostra il numero di messaggi **in** ingresso e in uscita interessati dalle regole di trasporto dlp (Data Loss Prevention). È possibile perfezionare ulteriormente il grafico selezionando una delle opzioni seguenti:

  - **Mostra dati per: Tutte le regole di trasporto DLP**
  - **Mostra dati per: utenti compromessi**
  - **Mostra dati per: Basso volume di contenuto rilevato U.S. Patriot Act**

- **Visualizzare i dati per: regole di trasporto** \> di Exchange DLP **Scomporsi per: Direzione**:  questa visualizzazione mostra il numero  di messaggi di gravità alta e media **e** di gravità bassa interessati dalle regole di trasporto DLP. È possibile perfezionare ulteriormente il grafico selezionando una delle opzioni seguenti:

  - **Mostra dati per: Tutte le regole di trasporto DLP**
  - **Mostra dati per: utenti compromessi**
  - **Mostra dati per: Basso volume di contenuto rilevato U.S. Patriot Act**

Se si fa **clic su Filtri** in una visualizzazione report, è possibile modificare i risultati con i filtri seguenti:

- **Data di inizio** e **Data fine**
- Valori di direzione
- Valori di gravità

![Visualizzazione dei report nel report delle regole di trasporto di Exchange](../../media/transport-rule-report-report-view.png)

### <a name="details-table-view-for-the-exchange-transport-rule-report"></a>Visualizzazione tabella dettagli per il report sulle regole di trasporto di Exchange

Se si fa **clic su Visualizza tabella** dettagli , le informazioni visualizzate dipendono dal grafico visualizzato:

- **Visualizzare i dati per: Regole di trasporto di Exchange**:

  - **Data**
  - **Regola di trasporto**
  - **Oggetto**
  - **Indirizzo del mittente**
  - **Indirizzo destinatario**
  - **Gravità**
  - **Direzione**

- **Visualizzare i dati per: regole di trasporto di Exchange DLP**:

  - **Data**
  - **Criteri DLP**
  - **Regola di trasporto**
  - **Oggetto**
  - **Indirizzo del mittente**
  - **Indirizzo destinatario**
  - **Gravità**
  - **Direzione**

Se si fa **clic su Filtri** in una visualizzazione tabella dei dettagli, è possibile modificare i risultati con i filtri seguenti:

- **Data di inizio** e **Data fine**
- Valori di direzione
- Valori di gravità

Per tornare alla visualizzazione report, fare clic su **Visualizza report.**

## <a name="forwarding-report"></a>Rapporto di inoltro

Il **rapporto Inoltro mostra** i messaggi inoltrati automaticamente dall'organizzazione ai domini esterni dalle cassette postali di Exchange Online. I messaggi inoltrati possono rappresentare un rischio per la sicurezza o la conformità e possono indicare un account compromesso.

Per visualizzare il report, aprire il [Centro sicurezza & conformità,](https://protection.office.com)passare a Dashboard report  \>  e selezionare Report **di inoltro.** Per passare direttamente al report, aprire <https://protection.office.com/reportv2?id=MailFlowForwarding> .

![Widget Di report di inoltro nel dashboard report](../../media/forwarding-report-widget.png)

### <a name="report-view-for-the-forwarding-report"></a>Visualizzazione report per il report di inoltro

Nella visualizzazione report sono disponibili i grafici seguenti:

- **Mostra dati per: Metodi di inoltro**: Vengono visualizzati i metodi seguenti:

  - **Regola di trasporto**: nota anche come [regole del flusso di posta](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).
  - **Regola cassetta postale**: nota anche come [regole di Posta in arrivo.](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59)

  ![Visualizzazione dei metodi di inoltro nel report di inoltro](../../media/forwarding-report-forwarding-methods.png)

- **Show data for: Forwarding domains**: Questa visualizzazione mostra i domini dei destinatari che sono le destinazioni per l'inoltro.

  ![Visualizzazione domini di inoltro nel report di inoltro](../../media/forwarding-report-forwarding-domains.png)

- **Mostra dati per: Server d'inoltro**: Vengono visualizzati i seguenti server d'inoltro:

  - **Regola di trasporto**
  - Cassetta postale che contiene la regola di posta in arrivo di inoltro.

  ![Visualizzazione server d'inoltro nel report di inoltro](../../media/forwarding-report-forwarders.png)

Se si fa **clic su Filtri** in una visualizzazione report, è possibile specificare un intervallo di date con Data di **inizio** e **Data fine.**

### <a name="details-table-view-for-the-forwarding-report"></a>Visualizzazione tabella dettagli per il report di inoltro

Se si fa **clic su Visualizza tabella dettagli** in una visualizzazione report, vengono visualizzate le informazioni seguenti:

- **Server d'inoltro**: valore **Regola di trasporto** o cassetta postale che contiene la regola di posta in arrivo di inoltro.
- **Tipo di inoltro**: Valore **Regola cassetta postale o** Regola di **trasporto.**
- **Nome del destinatario**
- **Dominio destinatario**
- **Dettagli:** si tratta del valore GUID della regola del flusso di posta o del valore RuleIdentity della regola di Posta in arrivo.
- **Numero**
- **Prima data di inoltro**

Se si fa **clic su Filtri** in una visualizzazione tabella dei dettagli, è possibile specificare un intervallo di date con Data di **inizio** e **Data fine.**

Per tornare alla visualizzazione report, fare clic su **Visualizza report.**

## <a name="mailflow-status-report"></a>Rapporto sullo stato del flusso di posta

La **relazione sullo stato del flusso di** posta è simile al [rapporto](#sent-and-received-email-report)Posta inviata e ricevuta, con ulteriori informazioni sulla posta elettronica consentita o bloccata sul perimetro. Questo è l'unico report che contiene informazioni sulla protezione perimetrale e mostra la quantità di posta elettronica bloccata prima di essere consentita al servizio per la valutazione da Parte di Exchange Online Protection (EOP). È importante comprendere che se un messaggio viene inviato a cinque destinatari, viene conteggiato come cinque messaggi diversi e non un messaggio.
Per visualizzare il report, aprire il [Centro sicurezza & conformità,](https://protection.office.com)passare a Dashboard report e  \>  selezionare Report stato flusso **di posta**. Per passare direttamente alla relazione **sullo stato del flusso di posta,** aprire <https://protection.office.com/mailflowStatusReport> .

![Widget rapporto sullo stato del flusso di posta nel dashboard report](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a>Visualizzazione tipo per la relazione sullo stato del flusso di posta

Quando si apre il report, la **scheda Tipo** è selezionata per impostazione predefinita. Per impostazione predefinita, questa visualizzazione contiene un grafico e una tabella dati configurata con i filtri seguenti:

- **Date**: Ultimi 7 giorni.
- **Direzione**:

  - **In ingresso**
  - **In uscita**
  - **Intra-org:** questo conteggio è per i messaggi all'interno di un tenant, ad esempio mittente abc@domain.com invia al destinatario xyz@domain.com (conteggiato separatamente da **In ingresso** e **In uscita)**

- **Digitare**:

  - **Posta buona**
  - **Malware**
  - **Posta indesiderata**
  - **Protezione edge**
  - **Messaggi delle regole**
  - **Posta di phishing**

Il grafico è organizzato in base ai **valori Type.**

È possibile modificare questi filtri facendo clic **su Filtro** o su un valore nella legenda del grafico.

La tabella dati contiene le informazioni seguenti:

- **Direzione**
- **Type**
- **24 ore**
- **3 giorni**
- **7 giorni**
- **15 giorni**
- **30 giorni**

Se si fa **clic su Scegli una categoria per ulteriori dettagli,** è possibile selezionare uno dei valori seguenti:

- **Posta elettronica di phishing**: questa selezione consente di visualizzare il [rapporto sullo stato di Protezione dalle minacce.](view-email-security-reports.md#threat-protection-status-report)
- **Malware nella posta elettronica**: questa selezione consente di visualizzare il [rapporto sullo stato di Protezione dalle minacce.](view-email-security-reports.md#threat-protection-status-report)
- **Rilevamenti di posta indesiderata:** questa selezione consente di accedere al [report Rilevamenti posta indesiderata.](view-email-security-reports.md#spam-detections-report)
- **Posta indesiderata bloccata** perimetrali : questa selezione consente di accedere al [report Rilevamenti posta indesiderata.](view-email-security-reports.md#spam-detections-report)

**Esporta**:

Per la visualizzazione dettagli, è possibile esportare i dati solo per un giorno. Pertanto, se si desidera esportare i dati per 7 giorni, è necessario eseguire 7 diverse azioni di esportazione.

Ogni file CSV esportato è limitato a 150.000 righe. Se i dati di quel giorno contengono più di 150.000 righe, verranno creati più file CSV.

![Visualizzazione tipo nella relazione sullo stato del flusso di posta ](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a>Visualizzazione della direzione per la relazione sullo stato del flusso di posta

Se si fa clic **sulla scheda Direzione,** vengono utilizzati gli stessi filtri predefiniti della **visualizzazione** Tipo.

Il grafico è organizzato in base **ai valori di** Direzione.

È possibile modificare questi filtri facendo clic **su Filtro** o su un valore nella legenda del grafico. Vengono utilizzati gli stessi filtri **della** visualizzazione Tipo.

La tabella dati contiene le stesse informazioni della **visualizzazione Tipo.**

**L'opzione Scegliere una categoria per ulteriori dettagli** le selezioni e il comportamento disponibili sono gli stessi della visualizzazione **Tipo.**

**Esporta**:

Per la visualizzazione dettagli, è possibile esportare i dati solo per un giorno. Pertanto, se si desidera esportare i dati per 7 giorni, è necessario eseguire 7 diverse azioni di esportazione.

Ogni file CSV esportato è limitato a 150.000 righe. Se i dati di quel giorno contengono più di 150.000 righe, verranno creati più file CSV.

![Visualizzazione direzione nella relazione sullo stato del flusso di posta ](../../media/mail-flow-status-report-direction-view.png)

### <a name="funnel-view-for-the-mailflow-status-report"></a>Visualizzazione imbuto per la relazione sullo stato del flusso di posta

La **visualizzazione Imbuto** mostra come le funzionalità di protezione dalle minacce di posta elettronica di Microsoft filtrano la posta elettronica in arrivo e in uscita nell'organizzazione. Fornisce informazioni dettagliate sul conteggio totale della posta elettronica e sul modo in cui le funzionalità di protezione dalle minacce configurate, tra cui protezione perimetrale, antimalware, anti-phishing, protezione da posta indesiderata e anti-spoofing influiscono su questo conteggio.

Se si fa clic sulla scheda **Imbuto,** per impostazione predefinita, questa visualizzazione contiene un grafico e una tabella dati configurata con i filtri seguenti:

- **Date**: Ultimi 7 giorni.

- **Direzione**:

  - **In ingresso**
  - **In uscita**
  - **Intra-org:** questo conteggio è per i messaggi inviati all'interno di un tenant; Ad esempio, il mittente abc@domain.com inviato al destinatario xyz@domain.com (conteggiato separatamente da Inbound e Outbound).

La visualizzazione aggregata e la visualizzazione tabella dati consentono 90 giorni di filtro.

Se si fa **clic su Filtro**, è possibile filtrare sia il grafico che la tabella dati.

Questo grafico mostra il numero di messaggi di posta elettronica organizzati per:

- **Totale posta elettronica**
- **Posta elettronica dopo la protezione edge**
- **Posta elettronica dopo antimalware, reputazione file, blocco del tipo di file**
- **Email after anti-phish, URL reputation, brand impersonation, anti-spoof**
- **Posta elettronica dopo la posta indesiderata, filtro posta in blocco**
- **Posta elettronica dopo la rappresentazione di dominio e utente**<sup>1</sup>
- **Posta elettronica dopo la detonazione di file e URL**<sup>1</sup>
- **Email detected as benign after post-delivery protection (URL click time protection)**

<sup>1</sup> Defender solo per Office 365

Per visualizzare separatamente il messaggio di posta elettronica filtrato da EOP o Defender per Office 365, fare clic sul valore nella legenda del grafico.

La tabella dei dati contiene le informazioni seguenti, visualizzate in ordine di data decrescente:

- **Data**
- **Totale posta elettronica**
- **Protezione edge**
- **Antimalware, reputazione file, blocco del tipo di file**:
  - **Reputazione file:** messaggi filtrati a causa dell'identificazione di un file allegato da parte di altri clienti Microsoft.
  - **Blocco del tipo di** file : Messaggi filtrati a causa del tipo di file dannoso identificato nel messaggio.
- **Anti-phish, reputazione URL, rappresentazione del marchio, anti-spoofing**:
  - **Reputazione URL**: Messaggi filtrati a causa dell'identificazione dell'URL da parte di altri clienti Microsoft.
  - **Rappresentazione del marchio**: messaggi filtrati a causa del messaggio proveniente da mittenti noti che rappresentano il marchio.
  - **Anti-spoof**: messaggi filtrati a causa del tentativo di spoofing di un dominio a cui appartiene il destinatario o di un dominio di cui il mittente non è proprietario.
- **Protezione da posta indesiderata, filtro posta in blocco**:
  - **Filtro posta in blocco**: Messaggi filtrati a causa di un tentativo di recapitare la posta in blocco ai destinatari.
- **Rappresentazione utente e dominio (Defender per Office 365)**:
  - **Rappresentazione utente**: messaggi filtrati a causa di un tentativo di rappresentazione di un utente (mittente del messaggio) definito nelle impostazioni di protezione della rappresentazione di un criterio anti-phishing.
  - **Rappresentazione di dominio**: messaggi filtrati a causa di un tentativo di rappresentare un dominio definito nelle impostazioni di protezione della rappresentazione di un criterio anti-phishing.
- **Detonazione di file e URL (Defender per Office 365)**:
  - **Detonazione file:** messaggi filtrati in base a un criterio Allegati sicuri.
  - **Detonazione URL:** messaggio filtrato in base a un criterio collegamenti sicuri.
- **Protezione post-recapito e ZAP (ATP) o ZAP (EOP):** ZAP indica l'eliminazione automatica a zero ore.

Se si seleziona una riga nella tabella dati, nel riquadro a comparsa viene visualizzata un'ulteriore suddivisione dei conteggi dei messaggi di posta elettronica.

**Esporta**:

Dopo aver fatto **clic su** Esporta **in Opzioni,** è possibile selezionare uno dei valori seguenti:

- **Riepilogo (con i dati degli ultimi 90 giorni al massimo)**
- **Dettagli (con dati degli ultimi 30 giorni al massimo)**

In **Data** scegliere un intervallo e quindi fare clic su **Applica.** I dati per i filtri correnti verranno esportati in un file CSV.

Ogni file CSV esportato è limitato a 150.000 righe. Se i dati contengono più di 150.000 righe, verranno creati più file CSV.

 ![Visualizzazione Imbuto nella relazione sullo stato del flusso di posta ](../../media/mail-flow-status-report-funnel-view.png)

### <a name="tech-view-for-the-mailflow-status-report"></a>Visualizzazione tecnica per la relazione sullo stato del flusso di posta

La **visualizzazione Tech** è simile alla visualizzazione **Imbuto,** fornendo dettagli più dettagliati per le funzionalità di protezione dalle minacce configurate. Dal grafico è possibile vedere come i messaggi vengono categorizzati nelle diverse fasi della protezione dalle minacce.

Se si fa clic **sulla scheda Visualizzazione tecnica,** per impostazione predefinita, questa visualizzazione contiene un grafico e una tabella dati configurata con i filtri seguenti:

- **Date**: Ultimi 7 giorni.

- **Direzione**:

  - **In ingresso**
  - **In uscita**
  - **Intra-org:** questo conteggio è per i messaggi all'interno di un tenant, ad esempio mittente abc@domain.com invia al destinatario xyz@domain.com (conteggiato separatamente da in ingresso e in uscita)

La visualizzazione aggregata e la visualizzazione tabella dati consentono 90 giorni di filtro.

Se si fa **clic su Filtro**, è possibile filtrare sia il grafico che la tabella dati.

Questo grafico mostra i messaggi organizzati nelle categorie seguenti:

- **Totale posta elettronica**
- **Edge allow** e **Edge filtered**
- **Non malware,** **Rilevamento allegati sicuri,** <sup>\*</sup> Rilevamento motore **antimalware** e **Messaggi delle regole**
- **Not phish,** **DMARC failure,** **Impersonation detection,** **Spoof detection** e **Phish detection**
- **Nessun rilevamento con detonazione URL e** **rilevamento detonazione URL**<sup>\*</sup>
- **Non posta indesiderata** e  **posta indesiderata**
- **Posta elettronica non dannosa,** **rilevamento collegamenti sicuri** e <sup>\*</sup> **ZAP**

<sup>\*</sup> Defender per Office 365

Quando si passa il mouse su una categoria nel grafico, è possibile visualizzare il numero di messaggi in tale categoria.

La tabella dei dati contiene le informazioni seguenti, visualizzate in ordine di data decrescente:

- **Data**
- **Totale posta elettronica**
- **Edge filtrato**
- **Motore antimalware, Allegati sicuri, regola filtrata:**
  - **Regola filtrata**: Messaggi filtrati a causa delle regole del flusso di posta (note anche come regole di trasporto).
- **DMARC, rappresentazione, spoofing, phish filtrato**:
  - **DMARC**: Messaggi filtrati a causa dell'errore del messaggio nel controllo di autenticazione DMARC.
- **Rilevamento detonazione URL**
- **Protezione da posta indesiderata filtrata**
- **ZAP rimosso**
- **Rilevamento tramite collegamenti sicuri**

Se si seleziona una riga nella tabella dati, nel riquadro a comparsa viene visualizzata un'ulteriore suddivisione dei conteggi dei messaggi di posta elettronica.

**Esporta**:

Facendo clic **su Esporta,** in **Opzioni** è possibile selezionare uno dei valori seguenti:

- **Riepilogo (con i dati degli ultimi 90 giorni al massimo)**
- **Dettagli (con dati degli ultimi 30 giorni al massimo)**

In **Data** scegliere un intervallo e quindi fare clic su **Applica.** I dati per i filtri correnti verranno esportati in un file CSV.

Ogni file CSV esportato è limitato a 150.000 righe. Se i dati contengono più di 150.000 righe, verranno creati più file CSV.

 ![Visualizzazione tecnica nella relazione sullo stato del flusso di posta ](../../media/mail-flow-status-report-Tech-view.png)

## <a name="sent-and-received-email-report"></a>Rapporto di posta elettronica inviato e ricevuto

Il **report Posta inviata e** ricevuta è un report intelligente che mostra le informazioni sulla posta elettronica in arrivo e in uscita, inclusi i rilevamenti di posta indesiderata, il malware e la posta elettronica identificata come "buona". La differenza tra questo report e la relazione sullo stato [del flusso](#mailflow-status-report) di posta è che non include i dati sui messaggi bloccati dalla protezione perimetrale. È importante comprendere che se un messaggio viene inviato a cinque destinatari viene conteggiato come un unico messaggio.

La visualizzazione aggregata e la visualizzazione dettagli del report consentono 90 giorni di filtro.

Per visualizzare il report, aprire il [Centro sicurezza & conformità,](https://protection.office.com)passare a Dashboard report e selezionare Posta elettronica inviata  \>  **e ricevuta.** Per passare direttamente al report, aprire <https://protection.office.com/reportv2?id=SentAndReceivedMailATP> .

![Widget Posta elettronica inviata e ricevuta nel dashboard report](../../media/sent-and-received-email-report-widget.png)

### <a name="report-view-for-the-sent-and-received-email-report"></a>Visualizzazione report per il report Di posta elettronica inviato e ricevuto

Nella visualizzazione report sono disponibili i grafici seguenti:

- **Scomporsi per: Tipo**: Il grafico mostra tutte le categorie disponibili:

  - **Totale**
  - **Posta buona**
  - **Malware (antimalware)** (EOP)
  - **Rilevamenti di posta indesiderata**
  - **Messaggi delle regole**
  - **Malware avanzato** (Microsoft Defender per Office 365)

  Quando si passa il mouse su un giorno (punto dati) nel grafico, è possibile visualizzare i dettagli per tale giorno.

  ![Digitare la visualizzazione nel report Posta elettronica inviata e ricevuta](../../media/sent-and-received-email-report-type-view.png)

- **Scomporsi per: Direzione**: il grafico mostra **i dati totali,** in **ingresso** **e in** uscita. Quando si passa il mouse su un giorno (punto dati) nel grafico, è possibile visualizzare i dettagli per tale giorno.

  ![Visualizzazione della direzione nel report Posta inviata e ricevuta](../../media/sent-and-received-email-report-direction-view.png)

- **Drill-down per** \> **Malware (antimalware):** questa selezione consente di accedere ai rilevamenti [di malware nel report di posta elettronica.](view-email-security-reports.md#malware-detections-in-email-report)

- **Drill-down per** \> **Rilevamenti posta indesiderata):** questa selezione consente di accedere al [report Rilevamenti posta indesiderata.](view-email-security-reports.md#spam-detections-report)

Se si fa **clic su Filtri** in una visualizzazione report, è possibile modificare i risultati con i filtri seguenti:

- **Data di inizio** e **Data fine**
- Valori di direzione
- Valori di tipo

Per tornare alla visualizzazione report, fare clic su **Visualizza report.**

### <a name="details-table-view-for-the-sent-and-received-email-report"></a>Visualizzazione tabella dettagli per il report Posta inviata e ricevuta

Se si fa **clic su Visualizza tabella dettagli** nella visualizzazione Scomposi **per: Direzione** o Scomparti **per:** Direzione, vengono visualizzate le informazioni seguenti:

- **Data (UTC)**
- **Type**
- **Direzione**
- **Conteggio messaggi**

Se si fa **clic su Filtri** in una visualizzazione tabella dei dettagli, è possibile modificare i risultati con i filtri seguenti:

- **Data di inizio** e **Data fine**
- Valori di direzione
- Valori di tipo

Per tornare alla visualizzazione report, fare clic su **Visualizza report.**

## <a name="top-senders-and-recipients-report"></a>Rapporto Mittenti e destinatari principali

Il **report Mittenti e destinatari** principali è un grafico a torta che mostra i mittenti e i destinatari di posta elettronica principali.

Per visualizzare il report, aprire il Centro [sicurezza & conformità,](https://protection.office.com)passare a Dashboard report e  \>  selezionare **Mittenti e destinatari principali.** Per passare direttamente al report, aprire <https://protection.office.com/reportv2?id=TopSenderRecipientsATP> .

![Widget Mittenti e destinatari principali nel dashboard dei report](../../media/top-senders-and-recipients-widget.png)

### <a name="report-view-for-the-top-senders-and-recipient-report"></a>Visualizzazione report per il rapporto Mittenti principali e destinatari

Nella visualizzazione report sono disponibili i grafici seguenti:

- **Mostra i dati per \> i principali mittenti di posta**
- **Visualizzare i dati per \> i destinatari di posta elettronica principali**
- **Visualizzare i dati per \> i destinatari principali della posta indesiderata**
- **Mostra dati per \> Principali destinatari di malware** (EOP)
- **Visualizzare i dati \> per i destinatari principali di malware (Defender per Office 365)**

La composizione del grafico a torta cambia in base a queste selezioni.

Quando si passa il mouse su un cuneo nel grafico a torta, è possibile visualizzare un conteggio dei messaggi inviati o ricevuti.

Se si fa **clic su Filtri** in una visualizzazione report, è possibile specificare un intervallo di date con Data di **inizio** e **Data fine.**

![Grafico a torta nella visualizzazione Report nel report Mittenti e destinatari principali](../../media/top-senders-and-recipients-report-view.png)

### <a name="details-table-view-for-the-top-senders-and-recipient-report"></a>Visualizzazione tabella dettagli per il rapporto Mittenti principali e destinatari

Se si fa **clic su Visualizza tabella** dettagli , le informazioni visualizzate dipendono dal grafico visualizzato:

- **Mostra i dati per \> i principali mittenti di posta**

  - **Principali mittenti di posta**
  - **Numero**

- **Visualizzare i dati per \> i destinatari di posta elettronica principali**

  - **Destinatari di posta elettronica principali**
  - **Numero**

- **Visualizzare i dati per \> i destinatari principali della posta indesiderata**

  - **Principali destinatari di posta indesiderata**
  - **Numero**

- **Mostra dati per \> Principali destinatari di malware** (EOP)

  - **Principali destinatari di malware**
  - **Numero**

- **Visualizzare i dati \> per i destinatari principali di malware (Defender per Office 365)**

  - **Principali destinatari di malware (Defender per Office 365)**
  - **Numero**

Se si fa **clic su Filtri** in una visualizzazione tabella dei dettagli, è possibile specificare un intervallo di date con Data di **inizio** e **Data fine.**

Per tornare alla visualizzazione report, fare clic su **Visualizza report.**

## <a name="what-permissions-are-needed-to-view-these-reports"></a>Quali autorizzazioni sono necessarie per visualizzare questi report?

Per visualizzare e utilizzare i report descritti in questo articolo, è necessario essere membri di uno dei gruppi di ruoli seguenti nel Centro sicurezza & conformità:

- **Gestione organizzazione**
- **Amministratore della sicurezza**
- **Lettore sicurezza**
- **Lettore globale**

Per altre informazioni, vedere [Autorizzazioni nel Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).

> [!NOTE]
> L'aggiunta di utenti al ruolo di Azure Active Directory corrispondente nell'interfaccia di amministrazione di Microsoft 365 fornisce agli utenti le autorizzazioni necessarie nel centro Sicurezza e conformità _e_ le autorizzazioni per altre funzionalità di Microsoft 365. Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](../../admin/add-users/about-admin-roles.md).

## <a name="related-topics"></a>Argomenti correlati

[Report intelligenti e informazioni dettagliate nel Centro sicurezza e conformità](reports-and-insights-in-security-and-compliance.md)

[Approfondimenti sul flusso di posta nel Centro sicurezza e conformità](mail-flow-insights-v2.md)

[Visualizzare i report sulla sicurezza della posta elettronica nel Centro sicurezza e conformità](view-email-security-reports.md)

[Visualizzare i report per Microsoft Defender per Office 365](view-reports-for-atp.md)