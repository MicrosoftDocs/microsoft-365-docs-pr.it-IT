---
title: Visualizzare defender per Office 365 report nel dashboard report
f1.keywords:
- CSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e47e838c-d99e-4c0b-b9aa-e66c4fae902f
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Trovare e usare i report per Microsoft Defender per Office 365 nel Centro sicurezza & conformità.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0b3e1ddf48ccd74b36c594d232c6761b921dee8c
ms.sourcegitcommit: 7ee50882cb4ed37794a3cd82dac9b2f9e0a1f14a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/06/2021
ms.locfileid: "51599900"
---
# <a name="view-defender-for-office-365-reports-in-the-reports-dashboard-in-the-security--compliance-center"></a>Visualizzare Defender per Office 365 report nel dashboard Report nel Centro sicurezza & conformità

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Microsoft Defender per Office 365 piano 1 e piano 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Microsoft Defender per le organizzazioni Office 365 (ad esempio, abbonamenti Microsoft 365 E5 o Microsoft Defender per Office 365 Piano 1 o componenti aggiuntivi Microsoft Defender per Office 365 Piano 2) contengono una serie di report relativi alla sicurezza. Se si dispone delle [autorizzazioni necessarie,](#what-permissions-are-needed-to-view-the-defender-for-office-365-reports)è possibile visualizzare questi report nel Centro sicurezza & conformità andando a **Dashboard** \> **report.** Per passare direttamente al dashboard dei report, aprire <https://protection.office.com/insightdashboard> .

![Dashboard Report nel Centro sicurezza & conformità](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="defender-for-office-365-file-types-report"></a>Report tipi di file per Defender per Office 365

Il **report Defender per Office 365 tipi di file** mostra il tipo di file rilevati come dannosi dagli allegati [sicuri.](safe-attachments.md)

 La visualizzazione aggregata del report consente 90 giorni di filtro, mentre la visualizzazione dettagli consente solo 10 giorni di filtro.

Per visualizzare il report, aprire il Centro [sicurezza & conformità,](https://protection.office.com)passare a Dashboard report e selezionare Defender per Office 365  \>  tipi **di file.** Per passare direttamente al report, aprire <https://protection.office.com/reportv2?id=ATPFileReport> .

![Widget Defender per Office 365 tipi di file nel dashboard report](../../media/atp-file-types-report-widget.png)

> [!NOTE]
> Le informazioni contenute in questo report sono disponibili anche nel report defender per l Office 365 [di eliminazione dei messaggi.](#defender-for-office-365-message-disposition-report)

### <a name="report-view-for-the-defender-for-office-365-file-types-report"></a>Visualizzazione report per il report Defender per Office 365 tipi di file

Sono disponibili le visualizzazioni seguenti:

- **Visualizza dati per: File**: Il grafico contiene le informazioni seguenti:

  - **Allegati Excel dannosi**
  - **Allegati Flash dannosi**
  - **Allegati PDF dannosi**
  - **Allegati PowerPoint dannosi**
  - **URL dannosi**
  - **Allegati di Word dannosi**
  - **Allegati eseguibili dannosi**
  - **Altri**

  Quando si passa il mouse su un determinato giorno (punto dati), è [](safe-attachments.md) possibile visualizzare la suddivisione dei tipi di file dannosi rilevati dagli allegati sicuri e dalla protezione [antimalware in EOP.](anti-malware-protection.md)

  ![Visualizzazione file nel report Defender per Office 365 tipi di file](../../media/atp-file-types-report-file-view.png)

  Se si fa **clic su Filtri**, è possibile modificare il report con i filtri seguenti:

  - **Data di inizio** e **Data fine**
  - Gli stessi valori del tipo di file visibili nel grafico.

- **Visualizza dati per: Messaggio**: Il grafico contiene le informazioni seguenti:

  - **Blocca accesso**
  - **Messaggi sostituiti**
  - **Messaggi monitorati**
  - **Sostituito da Recapito dinamico della** posta elettronica : per ulteriori informazioni, vedere Recapito dinamico nei criteri allegati [sicuri.](safe-attachments.md#dynamic-delivery-in-safe-attachments-policies)

  ![Visualizzazione dei messaggi nel report Defender per Office 365 tipi di file](../../media/atp-file-types-report-message-view.png)

  Se si fa **clic su Filtri**, è possibile modificare il report con i filtri seguenti:

  - **Data di inizio** e **Data fine**
  - Gli stessi valori di eliminazione dei messaggi disponibili nel grafico e il valore **aggiuntivo Messaggi passati.**

### <a name="details-table-view-for-the-defender-for-office-365-file-types-report"></a>Visualizzazione tabella dettagli per il report Defender per Office 365 tipi di file

Se si fa clic **su** Visualizza tabella dettagli , il report offre una visualizzazione quasi in tempo reale di tutti i clic che si verificano all'interno dell'organizzazione negli ultimi 10 giorni. Le informazioni visualizzate dipendono dal grafico visualizzato:

- **Visualizza dati per: File**:

  - **Data**
  - **Indirizzo destinatario**
  - **Indirizzo del mittente**
  - **ID messaggio**: Disponibile nel **campo di intestazione Message-ID** nell'intestazione del messaggio e deve essere univoco. Un valore di esempio è `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (si notino le parentesi angolari).
  - **File**

  Se si fa **clic su Filtri**, è possibile modificare il report con i filtri seguenti:

  - **Data di inizio** e **Data fine**
  - Gli stessi valori del tipo di file visibili nel grafico.

- **Visualizza dati per: Messaggio**:

  - **Data**
  - **Indirizzo destinatario**
  - **Indirizzo del mittente**
  - **ID messaggio**
  - **File**
  - **Oggetto**

  Se si fa **clic su Filtri**, è possibile modificare i risultati con i filtri seguenti:

  - **Data di inizio** e **Data fine**
  - Gli stessi valori di eliminazione dei messaggi disponibili nel grafico e il valore **aggiuntivo Messaggi passati.**

Per tornare alla visualizzazione report, fare clic su **Visualizza report.**

## <a name="defender-for-office-365-message-disposition-report"></a>Report disposizione messaggi di Defender per Office 365

Il **report Eliminazione messaggi ATP** mostra le azioni intraprese per i messaggi di posta elettronica che sono stati rilevati come contenuti dannosi.

Per visualizzare il report, aprire il Centro [sicurezza &](https://protection.office.com)conformità, passare a Dashboard report e selezionare Defender per l'eliminazione Office 365  \>  **messaggio.** Per passare direttamente al report, aprire <https://protection.office.com/reportv2?id=ATPMessageReport> .

![Defender per Office 365 widget di eliminazione dei messaggi nel dashboard dei report](../../media/atp-message-disposition-report-widget.png)

> [!NOTE]
> Le informazioni contenute in questo report sono disponibili anche nel [report Defender per Office 365 tipi di file.](#defender-for-office-365-file-types-report)

### <a name="report-view-for-the-defender-for-office-365-message-disposition-report"></a>Visualizzazione report per defender per Office 365 di eliminazione dei messaggi

Sono disponibili le visualizzazioni seguenti:

- **Visualizza dati per: Messaggio**: Il grafico contiene le informazioni seguenti:

  - **Blocca accesso**
  - **Messaggi sostituiti**
  - **Messaggi monitorati**
  - **Sostituito da Recapito dinamico della** posta elettronica : per ulteriori informazioni, vedere Recapito dinamico nei criteri allegati [sicuri.](safe-attachments.md#dynamic-delivery-in-safe-attachments-policies)

  ![Visualizzazione dei messaggi nel report Defender per Office 365 tipi di file](../../media/atp-file-types-report-message-view.png)

  Se si fa **clic su Filtri**, è possibile modificare il report con i filtri seguenti:

  - **Data di inizio** e **Data fine**
  - Gli stessi valori di eliminazione dei messaggi disponibili nel grafico e il valore **aggiuntivo Messaggi passati.**

- **Visualizza dati per: File**: Il grafico contiene le informazioni seguenti:

  - **Allegati Excel dannosi**
  - **Allegati Flash dannosi**
  - **Allegati PDF dannosi**
  - **Allegati PowerPoint dannosi**
  - **URL dannosi**
  - **Allegati di Word dannosi**
  - **Allegati eseguibili dannosi**
  - **Altri**

  Quando si passa il mouse su un determinato giorno (punto dati), è [](safe-attachments.md) possibile visualizzare la suddivisione dei tipi di file dannosi rilevati dagli allegati sicuri e dalla protezione [antimalware in EOP.](anti-malware-protection.md)

  ![Visualizzazione file nel report Defender per Office 365 tipi di file](../../media/atp-file-types-report-file-view.png)

  Se si fa **clic su Filtri**, è possibile modificare il report con i filtri seguenti:

  - **Data di inizio** e **Data fine**
  - Gli stessi valori del tipo di file visibili nel grafico.

### <a name="details-table-view-for-the-defender-for-office-365-message-disposition-report"></a>Visualizzazione tabella dei dettagli per il report sull'eliminazione Office 365 defender per i messaggi

Se si fa clic **su** Visualizza tabella dettagli , il report offre una visualizzazione quasi in tempo reale di tutti i clic che si verificano all'interno dell'organizzazione negli ultimi 10 giorni. Le informazioni visualizzate dipendono dal grafico visualizzato:

- **Visualizza dati per: Messaggio**:

  - **Data**
  - **Indirizzo destinatario**
  - **Indirizzo del mittente**
  - **ID messaggio**
  - **File**
  - **Oggetto**

  Se si fa **clic su Filtri**, è possibile modificare i risultati con i filtri seguenti:

  - **Data di inizio** e **Data fine**
  - Gli stessi valori di eliminazione dei messaggi disponibili nel grafico e il valore **aggiuntivo Messaggi passati.**

- **Visualizza dati per: File**:

  - **Data**
  - **Indirizzo destinatario**
  - **Indirizzo del mittente**
  - **ID messaggio**
  - **File**

  Se si fa **clic su Filtri**, è possibile modificare il report con i filtri seguenti:

  - **Data di inizio** e **Data fine**
  - Gli stessi valori del tipo di file visibili nel grafico.

Per tornare alla visualizzazione report, fare clic su **Visualizza report.**

## <a name="mail-latency-report"></a>Rapporto latenza della posta

Il **report Latenza della posta** mostra una visualizzazione aggregata della latenza di recapito e detonazione della posta riscontrata all'interno dell'organizzazione. I tempi di recapito della posta nel servizio sono influenzati da una serie di fattori e il tempo di recapito assoluto in secondi spesso non è un buon indicatore di esito positivo o di un problema. Un tempo di recapito lento in un giorno può essere considerato un tempo medio di recapito in un altro giorno o viceversa. Il **rapporto Latenza posta** tenta di qualificare il recapito dei messaggi in base ai dati statistici relativi ai tempi di recapito osservati di altri messaggi:

- **50° percentile**: indica i tempi di recapito dei messaggi. È possibile considerare questo valore come un tempo medio di recapito.
- **90° percentile**: indica un'elevata latenza per il recapito dei messaggi. Solo il 10% dei messaggi ha impiegato più tempo di questo valore per il recapito.
- **99° percentile:** indica la latenza massima per il recapito dei messaggi.

Il lato client e la latenza di rete non sono inclusi.

Per visualizzare il report, aprire il [Centro sicurezza & conformità,](https://protection.office.com)passare a Dashboard  \> **report** e selezionare Report **latenza della posta**. Per passare direttamente al report, aprire <https://protection.office.com/mailLatencyReport?viewid=P50> .

![Widget report latenza della posta nel dashboard report](../../media/mail-latency-report-widget.png)

### <a name="report-view-for-the-mail-latency-report"></a>Visualizzazione report per il report Latenza posta

Quando si apre il report, la **scheda 50° percentile è** selezionata per impostazione predefinita.

Per impostazione predefinita, questa visualizzazione contiene un grafico configurato con i filtri seguenti:

- **Date**: Ultimi 7 giorni
- **Visualizzazione messaggio**:
  - Messaggi detonati

Questo grafico mostra i messaggi organizzati nelle categorie seguenti:

- **Latenza recapito posta**
- **Latenza detonazione**

Quando si passa il mouse su una categoria nel grafico, è possibile visualizzare una suddivisione della latenza in ogni categoria.

![Rapporto latenza della posta](../../media/mail-latency-report.png)

Se si fa **clic su Filtro** nella visualizzazione report, è possibile modificare i risultati con i filtri seguenti:

- Tutti i messaggi
- Messaggi che contengono allegati o URL

Se si fa clic sulla **scheda 90° percentile o** **sul 99° percentile,** verranno utilizzati gli stessi filtri predefiniti della **visualizzazione 50° percentile.**

### <a name="details-table-view-for-the-mail-latency-report"></a>Visualizzazione tabella dettagli per il report Latenza posta

Nella visualizzazione tabella dei dettagli vengono visualizzate le informazioni seguenti:

- **Data**
- **Percentili**
- **Conteggio messaggi**
- **Latenza complessiva**

![Dettagli del rapporto sulla latenza della posta](../../media/mail-latency-report-details.png)

Quanto sopra mostra che il 14 novembre la latenza media riscontrata per tutti i messaggi recapitati e detonati è stata **di 108.033** secondi.

La tabella dei dettagli contiene le stesse informazioni in ogni scheda.

## <a name="threat-protection-status-report"></a>Report dello stato di protezione dalle minacce

Il **rapporto sullo stato di** Protezione dalle minacce è un'unica visualizzazione che riunisce informazioni sul contenuto dannoso e sulla posta elettronica dannosa rilevata e bloccata da [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) e Microsoft Defender per Office 365. Per ulteriori informazioni, vedere [Rapporto sullo stato di Protezione dalle minacce](view-email-security-reports.md#threat-protection-status-report).

## <a name="url-threat-protection-report"></a>Report di protezione dalle minacce URL

Il **report di protezione dalle minacce URL** fornisce visualizzazioni di riepilogo e tendenze per le minacce rilevate e le azioni eseguite sui clic sugli URL come parte di Collegamenti [sicuri.](safe-links.md) A questo report non saranno applicati i dati dei clic degli utenti a cui è applicato il criterio Collegamenti sicuri. L'opzione Non tenere traccia **dei clic degli utenti** è selezionata.

Per visualizzare il report, aprire [il Centro sicurezza & conformità,](https://protection.office.com)passare a Dashboard  \> **report** e selezionare **Report protezione URL.** Per passare direttamente al report, aprire <https://protection.office.com/reportv2?id=URLProtectionActionReport> .

![Widget report protezione URL nel dashboard report](../../media/url-protection-report-widget.png)

> [!NOTE]
> Si tratta di un *report sulle tendenze di protezione,* ovvero i dati rappresentano le tendenze in un set di dati più grande. Di conseguenza, i dati nella visualizzazione aggregata non sono disponibili in tempo reale qui, ma i dati nella visualizzazione della tabella dei dettagli sono, quindi potrebbe verificarsi una leggera discrepanza tra le due visualizzazioni.

### <a name="report-view-for-the-url-threat-protection-report"></a>Visualizzazione report per il report di protezione dalle minacce URL

Il **report di protezione dalle** minacce URL include due visualizzazioni aggregate che vengono aggiornate una volta ogni quattro ore che mostra i dati degli ultimi 90 giorni:

- **Azione di protezione clic URL**: Mostra il numero di clic sull'URL da parte degli utenti nell'organizzazione e i risultati del clic:

  - **Bloccato** (all'utente è stato impedito di passare all'URL)
  - **Bloccato e su cui è stato fatto clic** (l'utente ha scelto di continuare a passare all'URL)
  - **Fatto clic durante l'analisi** (l'utente ha fatto clic sul collegamento prima del completamento dell'analisi)

  Un clic indica che l'utente ha fatto clic attraverso la pagina di blocco al sito Web dannoso (gli amministratori possono disabilitare il clic nei criteri collegamenti sicuri).

  Se si fa **clic su Filtri**, è possibile modificare il report con i filtri seguenti:

  - **Data di inizio** e **Data fine**
  - Le azioni di protezione dei clic disponibili, oltre al valore **Consentito** (all'utente è stato consentito passare all'URL).

  ![Url Click Protection action view in the URL threat protection report](../../media/url-threat-protection-report-url-click-protection-action-view.png)

- **Url click by application**: Mostra il numero di clic sull'URL da parte delle applicazioni che supportano collegamenti sicuri:

  - **Client di posta elettronica**
  - **PowerPoint**
  - **Word**
  - **Excel**
  - **OneNote**
  - **Visio**
  - **Teams**
  - **Altro**

  Se si fa **clic su Filtri**, è possibile modificare il report con i filtri seguenti:

  - **Data di inizio** e **Data fine**
  - Applicazioni disponibili.

### <a name="details-table-view-for-the-url-threat-protection-report"></a>Visualizzazione tabella dettagli per il report di protezione dalle minacce URL

Se si **fa** clic su Visualizza tabella dettagli , il report offre una visualizzazione quasi in tempo reale di tutti i clic che si verificano nell'organizzazione negli ultimi 7 giorni con i dettagli seguenti:

- **Ora clic**
- **Utente**
- **URL**
- **Azione**
- **App**

Se si fa **clic su** Filtri nella visualizzazione tabella dei dettagli, è possibile  filtrare in base allo stesso criterio della visualizzazione report e anche in base ai domini o ai destinatari separati da virgole. 

> [!NOTE]
> Il **filtro Domini** fa riferimento al dominio URL elencato nei risultati del report. 

Per tornare alla visualizzazione report, fare clic su **Visualizza report.**

## <a name="additional-reports-to-view"></a>Report aggiuntivi da visualizzare

Oltre ai report descritti in questo articolo, sono disponibili diversi altri report, come descritto nella tabella seguente:

****

|Report|Argomento|
|---|---|
|**Explorer** (Microsoft Defender per Office 365 Piano 2) o rilevamenti in tempo reale **(Microsoft** Defender per Office 365 Piano 1)|[Esplora minacce (e rilevamenti in tempo reale)](threat-explorer.md)|
|**Report di sicurezza della** posta elettronica, ad esempio il report Mittenti e destinatari principali, il rapporto Spoofing della posta elettronica e il report Rilevamenti posta indesiderata.|[Visualizzare i report sulla sicurezza della posta elettronica nel Centro sicurezza e conformità](view-email-security-reports.md)|
|**Rapporti del flusso di** posta, ad esempio il rapporto inoltro, il rapporto sullo stato del flusso di posta e il rapporto Mittenti e destinatari principali.|[Visualizzare i report del flusso di posta nel Centro sicurezza & conformità](view-mail-flow-reports.md)|
|**Traccia URL per collegamenti sicuri** (solo PowerShell). L'output di questo cmdlet mostra i risultati delle azioni collegamenti sicuri degli ultimi sette giorni.|[Get-UrlTrace](/powershell/module/exchange/get-urltrace)|
|**Risultati del traffico di posta per EOP e Microsoft Defender per Office 365** (solo PowerShell). L'output di questo cmdlet contiene informazioni su Domain, Date, Event Type, Direction, Action e Message Count.|[Get-MailTrafficATPReport](/powershell/module/exchange/get-mailtrafficatpreport)|
|**Rapporti dettagli posta per EOP e Defender per Office 365** di posta elettronica (solo PowerShell). L'output di questo cmdlet contiene dettagli su file o URL dannosi, tentativi di phishing, rappresentazione e altre potenziali minacce nei messaggi di posta elettronica o nei file.|[Get-MailDetailATPReport](/powershell/module/exchange/get-maildetailatpreport)|
|

## <a name="what-permissions-are-needed-to-view-the-defender-for-office-365-reports"></a>Quali autorizzazioni sono necessarie per visualizzare defender per Office 365 report?

Per visualizzare e utilizzare i report descritti in questo articolo, è necessario essere membri di uno dei gruppi di ruoli seguenti nel Centro sicurezza & conformità:

- **Gestione organizzazione**
- **Amministratore della sicurezza**
- **Lettore sicurezza**
- **Lettore globale**

Per altre informazioni, vedere [Autorizzazioni nel Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).

**Nota:** l'aggiunta di utenti al ruolo Azure Active Directory corrispondente nell'interfaccia di amministrazione di Microsoft 365 offre  agli utenti le autorizzazioni necessarie nel Centro sicurezza e conformità di & e le autorizzazioni per altre funzionalità di Microsoft 365. Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](../../admin/add-users/about-admin-roles.md).

## <a name="what-if-the-reports-arent-showing-data"></a>Cosa succede se i report non mostrano dati?

Se non vedi i dati nel tuo Defender per i Office 365, verifica che i criteri siano configurati correttamente. L'organizzazione deve disporre [](set-up-safe-attachments-policies.md) [di](set-up-safe-links-policies.md) criteri collegamenti sicuri e allegati sicuri definiti per poter Office 365 protezione dei dati. Vedere anche [Protezione da posta indesiderata e antimalware](anti-spam-and-anti-malware-protection.md).

## <a name="related-topics"></a>Argomenti correlati

[Report intelligenti e informazioni dettagliate nel Centro sicurezza e conformità](reports-and-insights-in-security-and-compliance.md)

[Autorizzazioni ruolo (Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#role-permissions)
