---
title: Visualizzare i report per Advanced Threat Protection
f1.keywords:
- CSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e47e838c-d99e-4c0b-b9aa-e66c4fae902f
ms.collection:
- M365-security-compliance
description: Trovare e utilizzare i report per Office 365 Advanced Threat Protection nel centro sicurezza e &amp; conformità.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 90da02c8aa3d50f62bdf4be8c466962da828b23d
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2020
ms.locfileid: "48196586"
---
# <a name="view-reports-for-office-365-advanced-threat-protection"></a>Visualizzare i report per Office 365 Advanced Threat Protection

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Le organizzazioni di Office 365 Advanced Threat Protection (ATP) (ad esempio, gli abbonamenti Microsoft 365 E5 o i componenti aggiuntivi ATP Plan 1 o ATP Plan 2) contengono una serie di report relativi alla sicurezza. Se si dispone delle [autorizzazioni necessarie](#what-permissions-are-needed-to-view-the-atp-reports), è possibile visualizzare i report nel centro sicurezza & Compliance accedendo al **Reports** \> **Dashboard**report. Per accedere direttamente al dashboard dei report, aprire <https://protection.office.com/insightdashboard> .

![Dashboard dei report nel centro sicurezza & Compliance](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="advanced-threat-protection-file-types-report"></a>Report sui tipi di file di protezione avanzata delle minacce

Il rapporto sui **tipi di file Advanced Threat Protection** report Visualizza il tipo di file rilevati come dannosi per gli [allegati sicuri di ATP](atp-safe-attachments.md).

 La visualizzazione aggregazione del report consente 90 giorni di filtraggio, mentre la visualizzazione dettagli consente solo 10 giorni di filtraggio.

Per visualizzare il report, aprire il [Centro sicurezza & conformità](https://protection.office.com), accedere al **Reports** \> **Dashboard** dei report e selezionare **tipi di file ATP di Office**. Per passare direttamente al report, aprire <https://protection.office.com/reportv2?id=ATPFileReport> .

![Widget tipi di file ATP di Office nel dashboard dei report](../../media/atp-file-types-report-widget.png)

> [!NOTE]
> Le informazioni contenute in questo report sono disponibili anche nel [report Advanced Threat Protection Message Disposition](#advanced-threat-protection-message-disposition-report).

### <a name="report-view-for-the-advanced-threat-protection-file-types-report"></a>Visualizzazione report per il rapporto tipi di file di protezione avanzata dalle minacce

Sono disponibili le visualizzazioni seguenti:

- **Visualizzare i dati per: file**: il grafico contiene le informazioni seguenti:

  - **Allegati di Excel dannosi**
  - **Allegati Flash dannosi**
  - **Allegati PDF dannosi**
  - **Allegati di PowerPoint dannosi**
  - **URL dannosi**
  - **Allegati di Word dannosi**
  - **Allegati eseguibili dannosi**
  - **Altri**

  Quando si posiziona il puntatore del mouse su un determinato giorno (punto dati), è possibile visualizzare la ripartizione dei tipi di file dannosi rilevati dagli [allegati sicuri di ATP](atp-safe-attachments.md) e dalla [protezione antimalware in EOP](anti-malware-protection.md).

  ![Visualizzazione file nel rapporto tipi di file ATP](../../media/atp-file-types-report-file-view.png)

  Se si fa clic su **filtri**, è possibile modificare il report con i filtri seguenti:

  - Data di **inizio** e **Data di fine**
  - Gli stessi valori del tipo di file che sono visibili nel grafico.

- **Visualizzazione dei dati per: messaggio**: il grafico contiene le informazioni seguenti:

  - **Blocca accesso**
  - **Messaggi sostituiti**
  - **Messaggi monitorati**
  - **Sostituito da un recapito dinamico della posta elettronica**: per ulteriori informazioni, vedere [Dynamic Delivery and outviewing with ATP Safe Attachments](dynamic-delivery-and-previewing.md).

  ![Visualizzazione dei messaggi nel rapporto tipi di file ATP](../../media/atp-file-types-report-message-view.png)

  Se si fa clic su **filtri**, è possibile modificare il report con i filtri seguenti:

  - Data di **inizio** e **Data di fine**
  - Gli stessi valori di disposizione del messaggio che sono disponibili nel grafico e i messaggi aggiuntivi che hanno **superato** il valore.

### <a name="details-table-view-for-the-advanced-threat-protection-file-types-report"></a>Visualizzazione tabella dettagli per il rapporto tipi di file di protezione avanzata dalle minacce

Se si fa clic su **Visualizza tabella dettagli**, il rapporto fornisce una visualizzazione quasi in tempo reale di tutti i clic che si verificano all'interno dell'organizzazione negli ultimi 10 giorni. Le informazioni visualizzate dipendono dal grafico che si sta esaminando:

- **Visualizzare i dati in base a: file**:

  - **Data**
  - **Indirizzo del destinatario**
  - **Indirizzo del mittente**
  - **ID messaggio**: disponibile nel campo di intestazione **Message-ID** nell'intestazione del messaggio e deve essere univoco. Un valore di esempio è `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (si notino le parentesi angolari).
  - **File**

  Se si fa clic su **filtri**, è possibile modificare il report con i filtri seguenti:

  - Data di **inizio** e **Data di fine**
  - Gli stessi valori del tipo di file che sono visibili nel grafico.

- **Visualizzare i dati per: messaggio**:

  - **Data**
  - **Indirizzo del destinatario**
  - **Indirizzo del mittente**
  - **ID messaggio**
  - **File**
  - **Oggetto**

  Se si fa clic su **filtri**, è possibile modificare i risultati con i filtri seguenti:

  - Data di **inizio** e **Data di fine**
  - Gli stessi valori di disposizione del messaggio che sono disponibili nel grafico e i messaggi aggiuntivi che hanno **superato** il valore.

Per tornare alla visualizzazione report, fare clic su **Visualizza report**.

## <a name="advanced-threat-protection-message-disposition-report"></a>Report eliminazione messaggi di protezione avanzata delle minacce

Il rapporto di **disposizione dei messaggi ATP** indica le azioni eseguite per i messaggi di posta elettronica rilevati come contenuti dannosi.

Per visualizzare il report, aprire il [Centro sicurezza & conformità](https://protection.office.com), accedere al **Reports** \> **Dashboard** report e selezionare **disposizione dei messaggi ATP di Office**. Per passare direttamente al report, aprire <https://protection.office.com/reportv2?id=ATPMessageReport> .

![Widget disposizione dei messaggi ATP di Office 365 nel dashboard report](../../media/atp-message-disposition-report-widget.png)

> [!NOTE]
> Le informazioni contenute in questo report sono disponibili anche nel [rapporto sui tipi di file di protezione avanzata dalle minacce](#advanced-threat-protection-file-types-report).

### <a name="report-view-for-the-advanced-threat-protection-message-disposition-report"></a>Visualizzazione report per il rapporto di disposizione dei messaggi per la protezione avanzata dalle minacce

Sono disponibili le visualizzazioni seguenti:

- **Visualizzazione dei dati per: messaggio**: il grafico contiene le informazioni seguenti:

  - **Blocca accesso**
  - **Messaggi sostituiti**
  - **Messaggi monitorati**
  - **Sostituito da un recapito dinamico della posta elettronica**: per ulteriori informazioni, vedere [Dynamic Delivery and outviewing with ATP Safe Attachments](dynamic-delivery-and-previewing.md).

  ![Visualizzazione dei messaggi nel rapporto tipi di file ATP](../../media/atp-file-types-report-message-view.png)

  Se si fa clic su **filtri**, è possibile modificare il report con i filtri seguenti:

  - Data di **inizio** e **Data di fine**
  - Gli stessi valori di disposizione del messaggio che sono disponibili nel grafico e i messaggi aggiuntivi che hanno **superato** il valore.

- **Visualizzare i dati per: file**: il grafico contiene le informazioni seguenti:

  - **Allegati di Excel dannosi**
  - **Allegati Flash dannosi**
  - **Allegati PDF dannosi**
  - **Allegati di PowerPoint dannosi**
  - **URL dannosi**
  - **Allegati di Word dannosi**
  - **Allegati eseguibili dannosi**
  - **Altri**

  Quando si posiziona il puntatore del mouse su un determinato giorno (punto dati), è possibile visualizzare la ripartizione dei tipi di file dannosi rilevati dagli [allegati sicuri di ATP](atp-safe-attachments.md) e dalla [protezione antimalware in EOP](anti-malware-protection.md).

  ![Visualizzazione file nel rapporto tipi di file ATP](../../media/atp-file-types-report-file-view.png)

  Se si fa clic su **filtri**, è possibile modificare il report con i filtri seguenti:

  - Data di **inizio** e **Data di fine**
  - Gli stessi valori del tipo di file che sono visibili nel grafico.

### <a name="details-table-view-for-the-advanced-threat-protection-message-disposition-report"></a>Visualizzazione della tabella Details per il rapporto disposizione dei messaggi per la protezione avanzata dalle minacce

Se si fa clic su **Visualizza tabella dettagli**, il rapporto fornisce una visualizzazione quasi in tempo reale di tutti i clic che si verificano all'interno dell'organizzazione negli ultimi 10 giorni. Le informazioni visualizzate dipendono dal grafico che si sta esaminando:

- **Visualizzare i dati per: messaggio**:

  - **Data**
  - **Indirizzo del destinatario**
  - **Indirizzo del mittente**
  - **ID messaggio**
  - **File**
  - **Oggetto**

  Se si fa clic su **filtri**, è possibile modificare i risultati con i filtri seguenti:

  - Data di **inizio** e **Data di fine**
  - Gli stessi valori di disposizione del messaggio che sono disponibili nel grafico e i messaggi aggiuntivi che hanno **superato** il valore.

- **Visualizzare i dati in base a: file**:

  - **Data**
  - **Indirizzo del destinatario**
  - **Indirizzo del mittente**
  - **ID messaggio**
  - **File**

  Se si fa clic su **filtri**, è possibile modificare il report con i filtri seguenti:

  - Data di **inizio** e **Data di fine**
  - Gli stessi valori del tipo di file che sono visibili nel grafico.

Per tornare alla visualizzazione report, fare clic su **Visualizza report**.

## <a name="threat-protection-status-report"></a>Report dello stato di protezione dalle minacce

Il rapporto **sullo stato della protezione dalle minacce** è una singola visualizzazione che raggruppa informazioni su contenuto dannoso e messaggi di posta elettronica dannosi rilevati e bloccati da [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) e Office 365 ATP. Per ulteriori informazioni, vedere [rapporto sullo stato della protezione dalle minacce](view-email-security-reports.md#threat-protection-status-report).

## <a name="url-threat-protection-report"></a>Report sulla protezione dalle minacce URL

Il **rapporto di protezione** da minacce URL fornisce le visualizzazioni di riepilogo e di tendenza per i rischi rilevati e le azioni eseguite nei clic URL come parte dei [collegamenti sicuri di ATP](atp-safe-links.md). Questo report non displicherà i dati da parte degli utenti a cui è stato applicato il criterio collegamenti sicuri ha l'opzione non **registrare i clic utente** selezionati.

Per visualizzare il report, aprire il [Centro sicurezza & conformità](https://protection.office.com), accedere al **Reports** \> **Dashboard** report e selezionare **rapporto protezione URL**. Per passare direttamente al report, aprire <https://protection.office.com/reportv2?id=URLProtectionActionReport> .

![Widget report di protezione URL nel dashboard report](../../media/url-protection-report-widget.png)

> [!NOTE]
> Si tratta di un *report di tendenza di protezione*, in cui i dati rappresentano le tendenze di un DataSet più grande. Di conseguenza, i dati nella visualizzazione aggregata non sono disponibili in tempo reale qui, ma i dati nella visualizzazione tabella dettagli sono, pertanto è possibile che si verifichi una leggera discrepanza tra le due visualizzazioni.

### <a name="report-view-for-the-url-threat-protection-report"></a>Visualizzazione report per il report di protezione dalle minacce URL

Il report di **protezione dalle minacce URL** contiene due visualizzazioni aggregate aggiornate ogni quattro ore che mostrano i dati per gli ultimi 90 giorni:

- **Azione di protezione clic su URL**: Visualizza il numero di clic URL degli utenti nell'organizzazione e i risultati del clic:

  - **Bloccato** (l'utente è stato bloccato dall'esplorazione all'URL)
  - **Bloccato e selezionato tramite**
  - **Fare clic su di esso durante l'analisi**

  Un clic indica che l'utente ha fatto clic sulla pagina blocca nel sito Web dannoso (gli amministratori possono disabilitare il clic nei criteri collegamenti sicuri).

  Se si fa clic su **filtri**, è possibile modificare il report con i filtri seguenti:

  - Data di **inizio** e **Data di fine**
  - Le azioni di protezione clic disponibili, oltre al valore **consentito** (è stato consentito all'utente di passare all'URL).

  ![URL fare clic su Protection Action View nel rapporto di protezione delle minacce URL](../../media/url-threat-protection-report-url-click-protection-action-view.png)

- **URL fare clic su applicazione**: consente di visualizzare il numero di clic URL per le applicazioni che supportano i collegamenti sicuri di Office 365 ATP:

  - **Client di posta elettronica**
  - **PowerPoint**
  - **Word**
  - **Excel**
  - **OneNote**
  - **Visio**
  - **Teams**
  - **Altro**

  Se si fa clic su **filtri**, è possibile modificare il report con i filtri seguenti:

  - Data di **inizio** e **Data di fine**
  - Le applicazioni disponibili.

### <a name="details-table-view-for-the-url-threat-protection-report"></a>Visualizzazione della tabella dei dettagli per il report sulla protezione dalle minacce URL

Se si fa clic su **Visualizza tabella dettagli**, il rapporto fornisce una visualizzazione quasi in tempo reale di tutti i clic che si verificano all'interno dell'organizzazione negli ultimi 7 giorni con i seguenti dettagli:

- **Fare clic su tempo**
- **Utente**
- **URL**
- **Azione**
- **App**

Se si fa clic su **filtri** nella visualizzazione tabella dettagli, è possibile filtrare in base agli stessi criteri della visualizzazione report, nonché ai **domini** o ai **destinatari** separati da virgole.

Per tornare alla visualizzazione report, fare clic su **Visualizza report**.

## <a name="additional-reports-to-view"></a>Report aggiuntivi da visualizzare

Oltre ai report ATP descritti in questo argomento, sono disponibili diversi altri report, come descritto nella tabella seguente:

****

|Report|Argomento|
|---|---|
|**Explorer** (ATP piano 2) o **rilevamenti in tempo reale** (ATP piano 1)|[Esplora minacce (e rilevamenti in tempo reale)](threat-explorer.md)|
|Report di **protezione della posta elettronica**, ad esempio il report mittenti e destinatari principali, il report di posta indesiderata e il rapporto rilevamenti di spam.|[Visualizzare i report sulla sicurezza della posta elettronica nel Centro sicurezza e conformità](view-email-security-reports.md)|
|**Rapporti sul flusso di posta**, ad esempio il rapporto di inoltro, il rapporto sullo stato del flusso di messaggi e il report mittenti e destinatari principali.|[Visualizzare i report sul flusso di posta elettronica nel centro sicurezza & Compliance](view-mail-flow-reports.md)|
|**Traccia URL per i collegamenti sicuri di ATP** (solo PowerShell). L'output di questo cmdlet consente di visualizzare i risultati delle azioni di collegamenti sicuri ATP negli ultimi sette giorni.|[Get-UrlTrace](https://docs.microsoft.com/powershell/module/exchange/get-urltrace)|
|**Risultati del traffico di posta elettronica per EOP e ATP** (solo PowerShell). L'output di questo cmdlet contiene informazioni sul dominio, la data, il tipo di evento, la direzione, l'azione e il numero di messaggi.|[Get-MailTrafficATPReport](https://docs.microsoft.com/powershell/module/exchange/get-mailtrafficatpreport)|
|**Report Dettagli posta per i rilevamenti di EOP e ATP** (solo PowerShell). L'output di questo cmdlet contiene informazioni dettagliate su file o URL dannosi, tentativi di phishing, rappresentazione e altre potenziali minacce nei messaggi di posta elettronica o nei file.|[Get-MailDetailATPReport](https://docs.microsoft.com/powershell/module/exchange/get-maildetailatpreport)|
|

## <a name="what-permissions-are-needed-to-view-the-atp-reports"></a>Quali autorizzazioni sono necessarie per visualizzare i report ATP?

Per visualizzare e utilizzare i report descritti in questo argomento, **è necessario che sia assegnato un ruolo appropriato per il &amp; Centro sicurezza e l'interfaccia di amministrazione di Exchange**.

- Per il Centro sicurezza & conformità, è necessario che sia assegnato uno dei ruoli seguenti:

  - Gestione organizzazione
  - Amministratore della sicurezza (è possibile assegnarlo nell'interfaccia di amministrazione di Azure Active Directory ( [https://aad.portal.azure.com](https://aad.portal.azure.com) ))
  - Operatore di sicurezza (che può essere assegnato nell'interfaccia di amministrazione di Azure Active Directory ( [https://aad.portal.azure.com](https://aad.portal.azure.com) ))
  - Ruolo con autorizzazioni di lettura per la sicurezza

- Per Exchange Online, è necessario che sia assegnato uno dei ruoli seguenti nell'interfaccia di amministrazione di Exchange ( [https://outlook.office365.com/ecp](https://outlook.office365.com/ecp) ) o con i cmdlet di PowerShell (vedere [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)):

  - Gestione organizzazione
  - Gestione organizzazione in sola visualizzazione
  - Ruolo Destinatari di sola lettura
  - Gestione della conformità

Per altre informazioni, vedere le risorse seguenti:

- [Autorizzazioni nel Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md)

- [Autorizzazioni funzionalità in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)

## <a name="what-if-the-reports-arent-showing-data"></a>Cosa succede se i rapporti non mostrano dati?

Se i dati non vengono visualizzati nei rapporti ATP, verificare che i criteri siano configurati correttamente. L'organizzazione deve disporre di [criteri dei collegamenti sicuri ATP](set-up-atp-safe-links-policies.md) e di criteri per gli [allegati sicuri ATP](set-up-atp-safe-attachments-policies.md) definiti in modo che la protezione da ATP sia sul posto. Vedere anche [protezione da posta indesiderata e anti-malware in Office 365](anti-spam-and-anti-malware-protection.md).

## <a name="related-topics"></a>Argomenti correlati

[Report intelligenti e informazioni dettagliate nel Centro sicurezza e conformità](reports-and-insights-in-security-and-compliance.md)
  
[Autorizzazioni ruolo (Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#role-permissions)
