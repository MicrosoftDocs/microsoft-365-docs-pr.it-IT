---
title: Visualizzazione report di Microsoft Defender per Office 365
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
description: Gli amministratori possono scoprire come trovare e usare Defender per Office 365 report disponibili nel portale Microsoft 365 Defender.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f7eab856f22ac1c2282e83897db6e3f93d4d97e6
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083513"
---
# <a name="view-defender-for-office-365-reports-in-the-microsoft-365-defender-portal"></a>Visualizzare i report di Defender Office 365 nel Microsoft 365 Defender portale

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Microsoft Defender per Office 365 piano 1 e piano 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Microsoft Defender per le organizzazioni Office 365 (ad esempio, abbonamenti Microsoft 365 E5 o Microsoft Defender per Office 365 Piano 1 o componenti aggiuntivi Microsoft Defender per Office 365 Piano 2) contengono una serie di report relativi alla sicurezza. Se si dispone [delle](#what-permissions-are-needed-to-view-the-defender-for-office-365-reports)autorizzazioni necessarie, è possibile visualizzare questi  report nel portale di Microsoft 365 Defender andando a Rapporti e-mail & \> **collaborazione** \> **E-mail**& rapporti di collaborazione . Per passare direttamente alla pagina Rapporti di **collaborazione &** e-mail, aprire <https://security.microsoft.com/emailandcollabreport> .

![Pagina dei & di collaborazione tramite posta elettronica nel portale Microsoft 365 Defender posta elettronica](../../media/email-collaboration-reports.png)

> [!NOTE]
>
> I report di sicurezza della posta elettronica che non richiedono Defender per Office 365 sono descritti in [View email security reports in the Microsoft 365 Defender portal](view-email-security-reports.md).
>
> I report correlati al flusso di posta sono ora disponibili nell'interfaccia di amministrazione di Exchange (EAC). Per ulteriori informazioni su questi report, vedere [Mail flow reports in the new Exchange admin center](/exchange/monitoring/mail-flow-reports/mail-flow-reports).

## <a name="safe-attachments-file-types-report"></a>Cassaforte Report Tipi di file allegati

> [!NOTE]
> Il **Cassaforte dei tipi di file allegati** alla fine andrà via. Le stesse informazioni sono disponibili nella relazione [sullo stato di Threat Protection.](#threat-protection-status-report)

## <a name="safe-attachments-message-disposition-report"></a>Cassaforte Rapporto eliminazione messaggi allegati

> [!NOTE]
> Il **Cassaforte di eliminazione dei messaggi** allegati alla fine andrà via. Le stesse informazioni sono disponibili nella relazione [sullo stato di Threat Protection.](#threat-protection-status-report)

## <a name="mail-latency-report"></a>Rapporto latenza della posta

Il **report Latenza della posta** mostra una visualizzazione aggregata della latenza di recapito e detonazione della posta riscontrata all'interno dell'organizzazione. I tempi di recapito della posta nel servizio sono influenzati da una serie di fattori e il tempo di recapito assoluto in secondi spesso non è un buon indicatore di esito positivo o di un problema. Un tempo di recapito lento in un giorno può essere considerato un tempo medio di recapito in un altro giorno o viceversa. In questo modo si tenta di qualificare il recapito dei messaggi in base ai dati statistici relativi ai tempi di recapito osservati di altri messaggi.

Il lato client e la latenza di rete non sono inclusi.

Per visualizzare il report, aprire il portale [Microsoft 365 Defender,](https://security.microsoft.com)passare **a** Report e-mail & \> **collaborazione** \> **E-mail & collaborazione.** Nella pagina **Rapporti di collaborazione &** posta elettronica individuare Rapporto **latenza posta** e quindi fare clic su Visualizza **dettagli.** Per passare direttamente al report, aprire <https://security.microsoft.com/mailLatencyReport> .

![Widget report di latenza della posta nella pagina Report & e-mail](../../media/mail-latency-report-widget.png)

Nella pagina **Rapporto latenza posta** sono disponibili le schede seguenti nella pagina **Rapporto latenza posta:**

- **50° percentile**: indica i tempi di recapito dei messaggi. È possibile considerare questo valore come un tempo medio di recapito. Questa scheda è selezionata per impostazione predefinita.
- **90° percentile**: indica un'elevata latenza per il recapito dei messaggi. Solo il 10% dei messaggi ha impiegato più tempo di questo valore per il recapito.
- **99° percentile:** indica la latenza massima per il recapito dei messaggi.

Indipendentemente dalla scheda selezionata, il grafico mostra i messaggi organizzati nelle categorie seguenti:

- **Latenza recapito posta**
- **Detonazioni**

Quando si passa il mouse su una categoria nel grafico, è possibile visualizzare una suddivisione della latenza in ogni categoria.

![50° percentile del rapporto latenza della posta](../../media/mail-latency-report-50th-percentile-view.png)

Se si fa **clic su Filtro**, è possibile filtrare sia il grafico che la tabella dei dettagli in base ai valori seguenti:

- **Data (UTC)**: **Data inizio e** Data **fine**
- **Visualizzazione messaggio:** uno dei valori seguenti:
  - **Tutti i messaggi**
  - **Messaggi che contengono allegati o URL**
  - **Messaggi detonati**

Al termine della configurazione dei filtri, fare clic **su Applica,** **Annulla** o **Cancella filtri.**

Nella tabella dei dettagli sotto il grafico sono disponibili le informazioni seguenti:

- **Data (UTC)**
- **Percentili**: **50,** **90** o **99**
- **Conteggio messaggi**
- **Latenza complessiva**

## <a name="threat-protection-status-report"></a>Report dello stato di protezione dalle minacce

Il **rapporto sullo stato di** Protezione dalle minacce è un'unica visualizzazione che riunisce informazioni sul contenuto dannoso e sulla posta elettronica dannosa rilevata e bloccata da [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) e Microsoft Defender per Office 365. Per ulteriori informazioni, vedere [Rapporto sullo stato di Protezione dalle minacce](view-email-security-reports.md#threat-protection-status-report).

## <a name="url-threat-protection-report"></a>Report di protezione dalle minacce URL

Il **report di protezione dalle minacce URL** fornisce visualizzazioni di riepilogo e tendenze per le minacce rilevate e le azioni eseguite sui clic sugli URL nell'ambito Cassaforte [collegamenti.](safe-links.md) In questo report non saranno disponibili dati sui clic degli utenti a cui è stato applicato il criterio collegamenti Cassaforte clic utente è selezionata l'opzione Non tenere traccia **dei** clic degli utenti.

Per visualizzare il report, aprire il portale [Microsoft 365 Defender,](https://security.microsoft.com)passare **a** Report e-mail & \> **collaborazione** \> **E-mail & collaborazione.** Nella pagina **Rapporti di collaborazione &** posta elettronica individuare la pagina Protezione **URL** e quindi fare clic su **Visualizza dettagli.** Per passare direttamente al report, aprire <https://security.microsoft.com/reports/URLProtectionActionReport> .

![Widget report protezione URL nella pagina Report di collaborazione & e-mail](../../media/url-protection-report-widget.png)

Le visualizzazioni disponibili nella pagina **del report di protezione** dalle minacce URL sono descritte nelle sezioni seguenti.

> [!NOTE]
> Si tratta di un *report sulle tendenze di protezione,* ovvero i dati rappresentano le tendenze in un set di dati più grande. Di conseguenza, i dati nei grafici non sono disponibili in tempo reale qui, ma i dati nella tabella dei dettagli sono, quindi potresti vedere una leggera discrepanza tra i due. I grafici vengono aggiornati una volta ogni quattro ore e contengono dati per gli ultimi 90 giorni.

### <a name="view-data-by-url-click-protection-action"></a>Visualizzare i dati in base all'azione di protezione del clic dell'URL

![Url Click Protection action view in the URL threat protection report](../../media/url-threat-protection-report-url-click-protection-action-view.png)

La visualizzazione azione Visualizza dati in base **all'URL** consente di visualizzare il numero di clic sull'URL da parte degli utenti nell'organizzazione e i risultati del clic:

- **Consentito**: all'utente è stato consentito passare all'URL.
- **Bloccato:** all'utente è stato impedito di passare all'URL.
- **Bloccato e su cui è stato fatto clic:** l'utente ha scelto di continuare a passare all'URL.
- **Fatto clic durante l'analisi**: l'utente ha fatto clic sul collegamento prima del completamento dell'analisi.

Un clic indica che l'utente ha fatto clic attraverso la pagina di blocco al sito Web dannoso (gli amministratori possono disabilitare il click-through nei Cassaforte dei collegamenti).

Se si fa **clic su Filtri**, è possibile modificare il report e la tabella dei dettagli selezionando uno o più dei valori seguenti nel riquadro a comparsa visualizzato:

- **Data (UTC)**: **Data inizio e** Data **fine**
- **Rilevamento**:
  - **Consentito**
  - **Bloccato**
  - **Bloccato e su cui è stato fatto clic**
  - **Fatto clic durante l'analisi**
- **Domini**: domini URL elencati nei risultati del report.
- **Destinatari**

Al termine della configurazione dei filtri, fare clic **su Applica,** **Annulla** o **Cancella filtri.**

La tabella dei dettagli sotto il grafico fornisce la seguente visualizzazione quasi in tempo reale di tutti i clic che si sono verificato nell'organizzazione negli ultimi 7 giorni:

- **Ora clic**
- **Utente**
- **URL**
- **Azione**
- **App**

### <a name="view-data-by-url-click-by-application"></a>Visualizzare i dati in base all'URL facendo clic per applicazione

![Url click by application view in the URL threat protection report](../../media/url-threat-protection-report-url-click-by-application-view.png)

La **visualizzazione Visualizza dati in base all'URL** in base all'applicazione mostra il numero di clic sull'URL da parte delle app che supportano Cassaforte collegamenti:

- **Client di posta elettronica**
- **PowerPoint**
- **Word**
- **Excel**
- **OneNote**
- **Visio**
- **Teams**
- **Altri**

Se si fa **clic su Filtri**, è possibile modificare il report e la tabella dei dettagli selezionando uno o più dei valori seguenti nel riquadro a comparsa visualizzato:

- **Data (UTC)**: **Data inizio e** Data **fine**
- **Rilevamento:** app disponibili nel grafico.
- **Domini**: domini URL elencati nei risultati del report.
- **Destinatari**

Al termine della configurazione dei filtri, fare clic **su Applica,** **Annulla** o **Cancella filtri.**

La tabella dei dettagli sotto il grafico fornisce la seguente visualizzazione quasi in tempo reale di tutti i clic che si sono verificato nell'organizzazione negli ultimi 7 giorni:

- **Ora clic**
- **Utente**
- **URL**
- **Azione**
- **App**

## <a name="additional-reports-to-view"></a>Report aggiuntivi da visualizzare

Oltre ai report descritti in questo articolo, sono disponibili diversi altri report, come descritto nella tabella seguente:

<br>

****

|Report|Argomento|
|---|---|
|**Explorer** (Microsoft Defender per Office 365 Piano 2) o rilevamenti in tempo reale **(Microsoft** Defender per Office 365 Piano 1)|[Esplora minacce (e rilevamenti in tempo reale)](threat-explorer.md)|
|**Report di sicurezza della** posta elettronica, ad esempio il report Mittenti e destinatari principali, il rapporto Spoofing della posta elettronica e il report Rilevamenti posta indesiderata.|[Visualizzare i report di sicurezza della posta elettronica nel portale Microsoft 365 Defender posta elettronica](view-email-security-reports.md)|
|**Rapporti del flusso di** posta, ad esempio il rapporto inoltro, il rapporto sullo stato del flusso di posta e il rapporto Mittenti e destinatari principali.|[Rapporti del flusso di posta nella nuova Exchange di amministrazione](/exchange/monitoring/mail-flow-reports/mail-flow-reports)|
|**Traccia URL per Cassaforte collegamenti** (solo PowerShell). L'output di questo cmdlet mostra i risultati delle azioni Cassaforte collegamenti negli ultimi sette giorni.|[Get-UrlTrace](/powershell/module/exchange/get-urltrace)|
|**Risultati del traffico di posta per EOP e Microsoft Defender per Office 365** (solo PowerShell). L'output di questo cmdlet contiene informazioni su Domain, Date, Event Type, Direction, Action e Message Count.|[Get-MailTrafficATPReport](/powershell/module/exchange/get-mailtrafficatpreport)|
|**Rapporti dettagli posta per EOP e Defender per Office 365** di posta elettronica (solo PowerShell). L'output di questo cmdlet contiene dettagli su file o URL dannosi, tentativi di phishing, rappresentazione e altre potenziali minacce nei messaggi di posta elettronica o nei file.|[Get-MailDetailATPReport](/powershell/module/exchange/get-maildetailatpreport)|
|

## <a name="what-permissions-are-needed-to-view-the-defender-for-office-365-reports"></a>Quali autorizzazioni sono necessarie per visualizzare defender per Office 365 report?

Per visualizzare e utilizzare i report descritti in questo articolo, è necessario essere membri di uno dei gruppi di ruoli seguenti nel portale di Microsoft 365 Defender:

- **Gestione organizzazione**
- **Amministratore della sicurezza**
- **Lettore sicurezza**
- **Lettore globale**

Per altre informazioni, vedere [Autorizzazioni nel portale di Microsoft 365 Defender](permissions-microsoft-365-security-center.md).

**Nota:** l'aggiunta di utenti al ruolo Azure Active Directory corrispondente nel interfaccia di amministrazione di Microsoft 365 offre agli utenti le  autorizzazioni necessarie nel portale di Microsoft 365 Defender e le autorizzazioni per altre funzionalità di Microsoft 365. Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](../../admin/add-users/about-admin-roles.md).

## <a name="what-if-the-reports-arent-showing-data"></a>Cosa succede se i report non mostrano dati?

Se non vedi i dati nel tuo Defender per i Office 365, verifica che i criteri siano configurati correttamente. L'organizzazione deve [disporre Cassaforte](set-up-safe-links-policies.md) dei collegamenti e [Cassaforte dei](set-up-safe-attachments-policies.md) criteri allegati per poter disporre di Defender Office 365 protezione. Vedere anche [Protezione da posta indesiderata e antimalware](anti-spam-and-anti-malware-protection.md).

## <a name="related-topics"></a>Argomenti correlati

[Report e informazioni dettagliate intelligenti nel portale Microsoft 365 Defender dati](reports-and-insights-in-security-and-compliance.md)

[Autorizzazioni ruolo (Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#role-permissions)
