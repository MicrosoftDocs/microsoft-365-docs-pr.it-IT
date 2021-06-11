---
title: Invii di amministratori
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Gli amministratori possono imparare a usare il portale invii nel centro sicurezza Microsoft 365 per inviare messaggi di posta elettronica sospetti, messaggi di phishing sospetti, posta indesiderata e altri messaggi, URL e allegati di posta elettronica potenzialmente dannosi a Microsoft per la nuova analisi.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6de6a018a96407a5690249bea15e90c2f5a0d1ed
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878689"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a>Usare l'Invio dell'amministratore per inviare posta indesiderata sospetta, phishing, URL e file a Microsoft

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](defender-for-office-365.md)


Nelle Microsoft 365 con cassette postali in Exchange Online, gli amministratori possono utilizzare il portale invii nel Centro sicurezza & conformità per inviare messaggi di posta elettronica, URL e allegati a Microsoft per l'analisi.

Quando invii un messaggio di posta elettronica, ottieni:

1. **Controllo dell'autenticazione della** posta elettronica : Dettagli sul fatto che l'autenticazione della posta elettronica sia stata superata o meno al momento del recapito.
2. **Riscontri criteri:** informazioni su eventuali criteri che potrebbero aver consentito o bloccato la posta elettronica in arrivo nel tenant, ignorando i verdetti del filtro del servizio.
3. **Reputazione/detonazione del payload**: esame di eventuali URL e allegati nel messaggio.
4. **Analisi grader**: Revisione eseguita dai grader umani per verificare se i messaggi sono dannosi.

> [!IMPORTANT]
> La reputazione/detonazione del payload e l'analisi del grado non vengono eseguite in tutti i tenant. Le informazioni non possono uscire dall'organizzazione quando i dati non devono uscire dal limite del tenant per motivi di conformità.

Per altri modi per inviare messaggi di posta elettronica, URL e allegati a Microsoft, vedere [Segnalare messaggi e file a Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare

- Si apre il centro Microsoft 365 sicurezza all'indirizzo <https://security.microsoft.com/> . Per passare direttamente alla **pagina Invii,** usa <https://security.microsoft.com/reportsubmission> .

- Per inviare messaggi e file a Microsoft, è necessario essere membri di uno dei gruppi di ruoli seguenti:

  - **Gestione dell'organizzazione** **o Lettore sicurezza** [nel centro sicurezza Microsoft 365 sicurezza](permissions-microsoft-365-security-center.md).

  - **Gestione organizzazione** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups).

    Si noti che l'appartenenza a questo gruppo di ruoli è necessaria per [visualizzare gli](#view-user-submissions-to-the-custom-mailbox) invii degli utenti alla cassetta postale personalizzata, come descritto più avanti in questo articolo.

- Per ulteriori informazioni su come gli utenti possono inviare messaggi e file a Microsoft, vedere [Segnalare messaggi e file a Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="report-suspicious-content-to-microsoft"></a>Segnalare contenuti sospetti a Microsoft

1. Nel centro [Microsoft 365](../defender/overview-security-center.md)sicurezza, passare **a** Invii e verificare  di essere nella scheda Inviato per l'analisi e quindi fare clic su Invia a **Microsoft per la revisione.**

2. Usa il **riquadro a comparsa Invia** a Microsoft per la revisione che viene visualizzato per inviare il messaggio, l'URL o l'allegato di posta elettronica, come descritto nelle sezioni seguenti.

### <a name="submit-a-questionable-email-to-microsoft"></a>Inviare un messaggio di posta elettronica discutibile a Microsoft

1. Nella sezione **Seleziona il tipo di invio** seleziona Posta **elettronica.** Nella sezione **Aggiungere l'ID del messaggio di rete o caricare il file di posta** elettronica, utilizzare una delle opzioni seguenti:

   - **Aggiungere l'ID** del messaggio di rete di posta elettronica : si tratta di un valore GUID disponibile nell'intestazione **X-MS-Exchange-Organization-Network-Message-Id** nel messaggio o nell'intestazione **X-MS-Office365-Filtering-Correlation-Id** nei messaggi in quarantena.

   - **Upload il file di posta elettronica**: fare clic su Sfoglia **file**. Nella finestra di dialogo visualizzata individuare e selezionare il file con estensione eml o msg e quindi fare clic su **Apri**.

   > [!NOTE]
   > La possibilità di inviare messaggi vecchi di 30 giorni è stata temporaneamente sospesa per Defender per Office 365 clienti. Gli amministratori potranno tornare indietro di 7 giorni.

2. Nella sezione **Scegliere un destinatario con un problema** specificare il destinatario per cui si desidera eseguire un controllo dei criteri. Il controllo dei criteri determinerà se l'analisi dei messaggi di posta elettronica è stata ignorata a causa dei criteri dell'utente o dell'organizzazione.

3. Nella sezione **Selezionare un motivo per l'invio a Microsoft** selezionare una delle opzioni seguenti:

   - **Non dovrebbe essere stato bloccato**

   - **Dovrebbe essere stato bloccato:** Selezionare **Posta indesiderata,** **Phishing** o **Malware.** Se non sei sicuro, usa il tuo miglior giudizio.

4. Al termine, fare clic sul **pulsante** Invia.

   ![Esempio di invio di un nuovo URL](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a>Inviare un URL sospetto a Microsoft

1. Nella sezione **Seleziona il tipo di invio** seleziona **URL.** Nella casella visualizzata immettere l'URL completo, ad esempio `https://www.fabrikam.com/marketing.html` .

2. Nella sezione **Motivo invio** selezionare una delle opzioni seguenti:

   - **Non dovrebbe essere stato bloccato**

   - **Should have been blocked**: Select **Phishing** or **Malware**.

3. Al termine, fare clic sul **pulsante** Invia.

   ![Esempio di nuovo invio di posta elettronica](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-email-attachment-to-microsoft"></a>Inviare un allegato di posta elettronica sospetto a Microsoft

1. Nella sezione **Selezionare il tipo di invio** selezionare Allegato di posta **elettronica.**

2. Fare **clic su Scegli file**. Nella finestra di dialogo visualizzata individuare e selezionare il file e quindi fare clic su **Apri.**

3. Nella sezione **Motivo invio** selezionare una delle opzioni seguenti:

   - **Non dovrebbe essere stato bloccato**

   - **Dovrebbe essere stato bloccato:** **il malware** è l'unica scelta e viene selezionato automaticamente.

4. Al termine, fare clic sul **pulsante** Invia.

   ![Esempio di nuovo invio allegato](../../media/submission-file-flyout.PNG)

## <a name="view-items-submitted-for-analysis"></a>Visualizzare gli elementi inviati per l'analisi

Nel centro Microsoft 365 sicurezza, passare **a** Invii e verificare di essere nella **scheda Inviato per l'analisi**

Nella barra dei comandi al centro della pagina è possibile immettere una data di inizio, una data di fine e, per impostazione predefinita, è possibile filtrare in base **all'ID** invio (un valore GUID assegnato a ogni invio) immettendo un valore nella casella e facendo clic sul pulsante ![ Aggiorna ](../../media/scc-quarantine-refresh.png) . È possibile immettere più valori separati da virgole.

Per modificare i criteri di filtro, fare clic **sul pulsante Filtro** e scegliere uno dei valori seguenti:

- **Mittente**
- **Subject/URL/File name**
- **Inviato da**
- **Tipo di invio**
- **Stato**

![Nuove opzioni di filtro per gli invii di amministratori](../../media/admin-submission-email-filter-options.png)

Per esportare i risultati, fare clic **su Esporta** nella parte superiore della pagina e selezionare **Dati grafico** o **Tabella.** Nella finestra di dialogo visualizzata, salvare il file .csv file.

Sotto il grafico sono disponibili tre schede: **Posta** elettronica (impostazione predefinita), **URL** e **Allegato di posta elettronica.**

### <a name="view-admin-email-submissions"></a>Visualizzare gli invii di posta elettronica dell'amministratore

È possibile fare clic **sul pulsante Personalizza** colonne nella parte inferiore della pagina per aggiungere o rimuovere colonne dalla visualizzazione:

- **Data**
- **ID invio:** valore GUID assegnato a ogni invio.
- **Inviato da**<sup>\*</sup>
- **Oggetto**<sup>\*</sup>
- **Mittente**
- **Indirizzo IP mittente**<sup>\*</sup>
- **Tipo di invio**
- **Motivo recapito**
- **Stato**<sup>\*</sup>

  <sup>\*</sup> Se si fa clic su questo valore, le informazioni dettagliate vengono visualizzate in un riquadro a comparsa.

#### <a name="admin-submission-rescan-details"></a>Dettagli dell'analisi dell'invio dell'amministratore

I messaggi inviati negli invii di amministratori vengono sottoposti a nuova analisi e i risultati vengono visualizzati nel riquadro a comparsa dei dettagli degli invii:

- Se si è verificato un errore nell'autenticazione della posta elettronica del mittente al momento del recapito.
- Informazioni su eventuali riscontri dei criteri che potrebbero aver influenzato o sostituito il verdetto di un messaggio.
- Risultati della detonazione correnti per verificare se gli URL o i file contenuti nel messaggio erano dannosi o meno.
- Feedback dei gradi.

Se è stata trovata una sostituzione, la nuova analisi dovrebbe essere completata dopo alcuni minuti. Se non si è verificato un problema nell'autenticazione della posta elettronica o il recapito non è stato influenzato da una sostituzione, il feedback dei voti potrebbe richiedere fino a un giorno.

### <a name="view-admin-url-submissions"></a>Visualizzare gli invii di URL di amministratore

Fare clic **sulla scheda URL.**

È possibile fare clic **sul pulsante Opzioni** colonna nella parte inferiore della pagina per aggiungere o rimuovere colonne dalla visualizzazione:

- **Data**
- **ID invio**
- **Inviato da**<sup>\*</sup>
- **URL**<sup>\*</sup>
- **Tipo di invio**
- **Stato**<sup>\*</sup>

  <sup>\*</sup> Se si fa clic su questo valore, le informazioni dettagliate vengono visualizzate in un riquadro a comparsa.

### <a name="view-email-attachment-submissions"></a>Visualizzare gli invii di allegati di posta elettronica

Fare clic **sulla scheda** Allegati.

È possibile fare clic **sul pulsante Opzioni** colonna nella parte inferiore della pagina per aggiungere o rimuovere colonne dalla visualizzazione:

- **Data**
- **ID invio**
- **Inviato da**<sup>\*</sup>
- **Nome file**<sup>\*</sup>
- **Tipo di invio**
- **Stato**<sup>\*</sup>

  <sup>\*</sup> Se si fa clic su questo valore, le informazioni dettagliate vengono visualizzate in un riquadro a comparsa.

## <a name="view-user-submissions-to-microsoft"></a>Visualizzare gli invii degli utenti a Microsoft

Se è stato distribuito il componente aggiuntivo Segnala [messaggio,](enable-the-report-message-add-in.md)il componente aggiuntivo Segnala [phishing](enable-the-report-phish-add-in.md)o gli utenti utilizzano la creazione di report  incorporati in [Outlook sul Web,](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)è possibile visualizzare i report degli utenti nella scheda Invii utente.

1. Nel Centro sicurezza & conformità passare a **Gestione minacce** \> **Invii**.

2. Seleziona la **scheda Invii utente** e quindi fai clic su **Nuovo invio.**

È possibile fare clic **sul pulsante Opzioni** colonna nella parte inferiore della pagina per aggiungere o rimuovere colonne dalla visualizzazione:

- **Inviato il**
- **Inviato da**<sup>\*</sup>
- **Oggetto**<sup>\*</sup>
- **Mittente**
- **Indirizzo IP mittente**<sup>\*</sup>
- **Tipo di invio**

<sup>\*</sup> Se si fa clic su questo valore, le informazioni dettagliate vengono visualizzate in un riquadro a comparsa.

Nella parte superiore della pagina è possibile immettere una data di inizio, una  data di fine e, per impostazione predefinita, è possibile filtrare in base al mittente immettendo un valore nella casella e facendo clic sul ![ pulsante Aggiorna ](../../media/scc-quarantine-refresh.png) . È possibile immettere più valori separati da virgole.

Per modificare i criteri di filtro, fare clic **sul pulsante Mittente** e scegliere uno dei valori seguenti:

- **Dominio del mittente**
- **Oggetto**
- **Inviato da**
- **Tipo di invio**
- **Indirizzo IP mittente**

![Nuove opzioni di filtro per gli invii degli utenti](../../media/user-submissions-filter-options.png)

Per esportare i risultati, fare clic **su Esporta** nella parte superiore della pagina e selezionare **Dati grafico** o **Tabella.** Nella finestra di dialogo visualizzata, salvare il file .csv file.

## <a name="view-user-submissions-to-the-custom-mailbox"></a>Visualizzare gli invii utente alla cassetta postale personalizzata

**Se** è stata [configurata una cassetta](user-submission.md) postale personalizzata per ricevere i messaggi segnalati dall'utente, è possibile visualizzare e inviare i messaggi recapitati alla cassetta postale di segnalazione.

1. Nel Centro sicurezza & conformità passare a **Gestione minacce** \> **Invii**.

2. Selezionare la **scheda Cassetta postale** personalizzata.

È possibile fare clic **sul pulsante Opzioni** colonna nella parte inferiore della pagina per aggiungere o rimuovere colonne dalla visualizzazione:

- **Inviato il**
- **Inviato da**<sup>\*</sup>
- **Oggetto**<sup>\*</sup>
- **Mittente**
- **Indirizzo IP mittente**<sup>\*</sup>
- **Tipo di invio**

Nella parte superiore della pagina è possibile immettere una data di inizio, una data di fine e filtrare in base a **Inviato** immettendo un valore nella casella e facendo clic sul ![ pulsante Aggiorna ](../../media/scc-quarantine-refresh.png) . È possibile immettere più valori separati da virgole.

Per esportare i risultati, fare clic **su Esporta** nella parte superiore della pagina e selezionare **Dati grafico** o **Tabella.** Nella finestra di dialogo visualizzata, salvare il file .csv file.

> [!NOTE]
> Se le organizzazioni sono configurate per l'invio solo alla cassetta postale personalizzata, i messaggi segnalati non verranno inviati per la nuova analisi e i risultati nel portale Messaggi segnalati dall'utente saranno sempre vuoti.

## <a name="undo-user-submissions"></a>Annullare gli invii utente

Una volta che un utente invia un messaggio di posta elettronica sospetto alla cassetta postale personalizzata, l'utente e l'amministratore non hanno la possibilità di annullare l'invio. Se l'utente desidera recuperare la posta elettronica, sarà disponibile per il ripristino nelle cartelle Posta eliminata o Posta indesiderata.

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a>Inviare messaggi a Microsoft dalla cassetta postale personalizzata

Se la cassetta postale personalizzata è stata configurata per intercettare i messaggi segnalati dall'utente senza inviare i messaggi a Microsoft, è possibile trovare e inviare messaggi specifici a Microsoft per l'analisi. Questo sposta in modo efficace un invio utente a un invio da amministratore.

Nella scheda **Messaggi segnalati dall'utente** selezionare un messaggio nell'elenco, fare clic sul pulsante **Azione** ed effettuare una delle seguenti selezioni:

- **Segnala pulito**
- **Segnalare phishing**
- **Segnalare malware**
- **Segnalare posta indesiderata**

![Nuove opzioni sul pulsante Azione](../../media/user-submission-custom-mailbox-action-button.png)
