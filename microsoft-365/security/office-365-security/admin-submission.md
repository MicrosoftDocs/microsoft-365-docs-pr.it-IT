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
description: Gli amministratori possono imparare a usare il portale invii nel portale di Microsoft 365 Defender per inviare messaggi di posta elettronica sospetti, messaggi di phishing sospetti, posta indesiderata e altri messaggi, URL e allegati di posta elettronica potenzialmente dannosi a Microsoft per la nuova analisi.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5e2fc859ea7df5e85ef65d1ad6f2a09f8806dd58
ms.sourcegitcommit: d0c160e89e17f451199bc4a85699effd2d935213
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/11/2021
ms.locfileid: "52893753"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a>Usare l'Invio dell'amministratore per inviare posta indesiderata sospetta, phishing, URL e file a Microsoft

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](defender-for-office-365.md)


Nelle Microsoft 365 con cassette postali di Exchange Online, gli amministratori possono utilizzare il portale invii nel portale di Microsoft 365 Defender per inviare messaggi di posta elettronica, URL e allegati a Microsoft per l'analisi.

Quando invii un messaggio di posta elettronica, ottieni:

- **Controllo dell'autenticazione della** posta elettronica : Dettagli sul fatto che l'autenticazione della posta elettronica sia stata superata o meno al momento del recapito.
- **Riscontri criteri:** informazioni su eventuali criteri che potrebbero aver consentito o bloccato la posta elettronica in arrivo nel tenant, ignorando i verdetti del filtro del servizio.
- **Reputazione/detonazione del payload**: esame di eventuali URL e allegati nel messaggio.
- **Analisi grader**: Revisione eseguita dai grader umani per verificare se i messaggi sono dannosi.

> [!IMPORTANT]
> La reputazione/detonazione del payload e l'analisi del grado non vengono eseguite in tutti i tenant. Le informazioni non possono uscire dall'organizzazione quando i dati non devono uscire dal limite del tenant per motivi di conformità.

Per altri modi per inviare messaggi di posta elettronica, URL e allegati a Microsoft, vedere [Segnalare messaggi e file a Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare

- Aprire il portale Microsoft 365 Defender all'indirizzo <https://security.microsoft.com/> . Per passare direttamente alla **pagina Invii,** usa <https://security.microsoft.com/reportsubmission> .

- Per inviare messaggi e file a Microsoft, è necessario essere membri di uno dei gruppi di ruoli seguenti:
  - **Gestione dell'organizzazione** **o Lettore sicurezza** [nel portale Microsoft 365 Defender](permissions-microsoft-365-security-center.md).
  - **Gestione organizzazione** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups).

    Si noti che l'appartenenza a questo gruppo di ruoli è necessaria per [visualizzare gli](#view-user-submissions-to-microsoft) invii degli utenti alla cassetta postale personalizzata, come descritto più avanti in questo articolo.

- Per ulteriori informazioni su come gli utenti possono inviare messaggi e file a Microsoft, vedere [Segnalare messaggi e file a Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="report-suspicious-content-to-microsoft"></a>Segnalare contenuti sospetti a Microsoft

1. Nel portale Microsoft 365 Defender passare a Invia tramite posta **elettronica & collaborazione** \> **Invii.**

2. Nella pagina **Invii** verificare  che la scheda Inviato per l'analisi sia selezionata e quindi fare clic su Icona Annuncio ![ Invia a Microsoft per ](../../media/m365-cc-sc-create-icon.png) **l'analisi.**

3. Usa il **riquadro a comparsa Invia** a Microsoft per la revisione che viene visualizzato per inviare il messaggio, l'URL o l'allegato di posta elettronica, come descritto nelle sezioni seguenti.

### <a name="submit-a-questionable-email-to-microsoft"></a>Inviare un messaggio di posta elettronica discutibile a Microsoft

1. Nella casella **Seleziona il tipo di invio,** verificare che l'opzione **Posta** elettronica sia selezionata nell'elenco a discesa.

2. Nella sezione **Aggiungere l'ID del messaggio di rete o caricare il file di posta** elettronica, utilizzare una delle opzioni seguenti:
   - **Aggiungere l'ID** del messaggio di rete di posta elettronica : si tratta di un valore GUID disponibile nell'intestazione **X-MS-Exchange-Organization-Network-Message-Id** nel messaggio o nell'intestazione **X-MS-Office365-Filtering-Correlation-Id** nei messaggi in quarantena.
   - **Upload il file di posta elettronica (con estensione msg o eml):** fare clic **su Sfoglia file**. Nella finestra di dialogo visualizzata individuare e selezionare il file con estensione eml o msg e quindi fare clic su **Apri**.

   > [!NOTE]
   > La possibilità di inviare messaggi vecchi di 30 giorni è stata temporaneamente sospesa per Defender per Office 365 clienti. Gli amministratori potranno tornare indietro di 7 giorni.

3. Nella casella **Scegliere un destinatario che ha avuto un** problema specificare il destinatario per cui si desidera eseguire un controllo dei criteri. Il controllo dei criteri determinerà se l'analisi dei messaggi di posta elettronica è stata ignorata a causa dei criteri dell'utente o dell'organizzazione.

4. Nella sezione **Selezionare un motivo per l'invio a Microsoft** selezionare una delle opzioni seguenti:
   - **Non dovrebbe essere stato bloccato (falso positivo)**
   - **Dovrebbe essere stato** bloccato: nella sezione Il messaggio di posta elettronica dovrebbe essere stato categorizzato come visualizzato, selezionare uno dei valori seguenti (se non si è sicuri, utilizzare la valutazione migliore): 
     - **Phishing**
     - **Posta indesiderata**
     - **Malware**

5. Al termine, fare clic sul **pulsante** Invia.

   ![Esempio di invio di un nuovo URL](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a>Inviare un URL sospetto a Microsoft

1. Nella casella **Seleziona il tipo di invio** seleziona **URL** nell'elenco a discesa.

2. Nella casella **URL** visualizzata immettere l'URL completo, ad esempio `https://www.fabrikam.com/marketing.html` .

3. Nella sezione **Selezionare un motivo per l'invio a Microsoft** selezionare una delle opzioni seguenti:
   - **Non dovrebbe essere stato bloccato (falso positivo)**
   - **Dovrebbe essere stato bloccato:** nella sezione **Questo URL** dovrebbe essere stato classificato come visualizzato, selezionare **Phish** o **Malware.**

4. Al termine, fare clic sul **pulsante** Invia.

   ![Esempio di nuovo invio di posta elettronica](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-email-attachment-to-microsoft"></a>Inviare un allegato di posta elettronica sospetto a Microsoft

1. Nella casella **Seleziona il tipo di invio** seleziona **File** nell'elenco a discesa.

2. Nella sezione **File** visualizzata fare clic su **Sfoglia file.** Nella finestra di dialogo visualizzata individuare e selezionare il file e quindi fare clic su **Apri.**

3. Nella sezione **Selezionare un motivo per l'invio a Microsoft** selezionare una delle opzioni seguenti:
   - **Non dovrebbe essere stato bloccato (falso positivo)**
   - **Dovrebbe essere stato bloccato:** nella sezione Questo **URL** dovrebbe essere stato classificato come visualizzato, **Malware** è l'unica scelta e viene selezionato automaticamente.

4. Al termine, fare clic sul **pulsante** Invia.

   ![Esempio di nuovo invio allegato](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions-to-microsoft"></a>Visualizzare gli invii di amministratori a Microsoft

1. Nel portale Microsoft 365 Defender passare a Invia tramite posta **elettronica & collaborazione** \> **Invii.**

2. Nella pagina **Invii** verificare che la scheda **Inviato per l'analisi** sia selezionata.

   - È possibile ordinare le voci facendo clic su un'intestazione di colonna disponibile. Fare **clic su Personalizza** colonne per visualizzare un massimo di sette colonne. I valori predefiniti sono contrassegnati da un asterisco (<sup>\*</sup>):
     - **Nome invio**<sup>\*</sup>
     - **Mittente**<su>\*</sup>
     - **Data di invio**<sup>\*</sup>
     - **Tipo di invio**<sup>\*</sup>
     - **Motivo dell'invio**<sup>\*</sup>
     - **Stato nuova analisi**<sup>\*</sup>
     - **Risultato dell'analisi**<sup>\*</sup>
     - **Verdetto filtro**
     - **Motivo recapito/blocco**
     - **ID invio**
     - **ID messaggio di rete/ID oggetto**
     - **Direzione**
     - **Indirizzo IP mittente**
     - **Livello di conformità in blocco (BCL)**
     - **Destinazione**
     - **Azione dei criteri**
     - **Inviato da**

     Al termine, fare clic su **Applica.**

   - Per filtrare le voci, fare clic su **Filtro.** I filtri disponibili sono:
     - **Date submitted**: **Start date e** End **date**.
     - **Tipo di invio:** **Posta** elettronica, **URL** o **File.**
     - **ID invio:** valore GUID assegnato a ogni invio.
     - **ID messaggio di rete**
     - **Mittente**

     Al termine, fare clic su **Applica.**

     ![Nuove opzioni di filtro per gli invii di amministratori](../../media/admin-submission-email-filter-options.png)

   - Per raggruppare le voci, fare clic **su Gruppo** e selezionare uno dei valori seguenti nell'elenco a discesa:
     - **Nessuna**
     - **Type**
     - **Motivo**
     - **Stato**
     - **Risultato dell'analisi**

   - Per esportare le voci, fare clic su **Esporta.** Nella finestra di dialogo visualizzata, salvare il file .csv file.

### <a name="admin-submission-rescan-details"></a>Dettagli dell'analisi dell'invio dell'amministratore

I messaggi inviati negli invii di amministratori vengono sottoposti a nuova analisi e i risultati vengono visualizzati nel riquadro a comparsa dei dettagli degli invii:

- Se si è verificato un errore nell'autenticazione della posta elettronica del mittente al momento del recapito.
- Informazioni su eventuali riscontri dei criteri che potrebbero aver influenzato o sostituito il verdetto di un messaggio.
- Risultati della detonazione correnti per verificare se gli URL o i file contenuti nel messaggio erano dannosi o meno.
- Feedback dei gradi.

Se è stata trovata una sostituzione, la nuova analisi dovrebbe essere completata dopo alcuni minuti. Se non si è verificato un problema nell'autenticazione della posta elettronica o il recapito non è stato influenzato da una sostituzione, il feedback dei voti potrebbe richiedere fino a un giorno.

## <a name="view-user-submissions-to-microsoft"></a>Visualizzare gli invii degli utenti a Microsoft

Se è stato distribuito il componente aggiuntivo Segnala [messaggio,](enable-the-report-message-add-in.md)Il componente aggiuntivo Segnala [phishing](enable-the-report-phish-add-in.md)o gli utenti utilizzano la segnalazione incorporata in Outlook [sul Web,](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)è possibile visualizzare le segnalazioni degli utenti nella scheda **Messaggio** segnalato dall'utente.

1. Nel portale Microsoft 365 Defender passare a Invia tramite posta **elettronica & collaborazione** \> **Invii.**

2. Nella pagina **Invii** seleziona la **scheda Messaggi segnalati dall'utente.**

   - È possibile ordinare le voci facendo clic su un'intestazione di colonna disponibile. Fare **clic su Personalizza** colonne per visualizzare un massimo di sette colonne. I valori predefiniti sono contrassegnati da un asterisco (<sup>\*</sup>):

     - **Oggetto del messaggio di posta elettronica**<sup>\*</sup>
     - **Segnalato da**<su>\*</sup>
     - **Data riportata**<sup>\*</sup>
     - **Mittente**<sup>\*</sup>
     - **Motivo segnalato**<sup>\*</sup>
     - **Risultato dell'analisi**<sup>\*</sup>
     - **ID segnalato messaggio**
     - **ID messaggio di rete**
     - **Indirizzo IP mittente**
     - **Simulazione phish**

     Al termine, fare clic su **Applica.**

   - Per filtrare le voci, fare clic su **Filtro.** I filtri disponibili sono:
     - **Data riportata**: **Data inizio** e **Data fine**.
     - **Segnalato da**
     - **Oggetto e-mail**
     - **ID segnalato messaggio**
     - **ID messaggio di rete**
     - **Mittente**
     - **Motivo segnalato**: **Non posta indesiderata,** **Phish** o **Posta indesiderata.**
     - **Simulazione phish**: **Sì** o **No**

     Al termine, fare clic su **Applica.**

    ![Nuove opzioni di filtro per gli invii degli utenti](../../media/user-submissions-filter-options.png)

   - Per raggruppare le voci, fare clic **su Gruppo** e selezionare uno dei valori seguenti nell'elenco a discesa:
     - **Nessuna**
     - **Motivo**
     - **Mittente**
     - **Segnalato da**
     - **Risultato dell'analisi**
     - **Simulazione phish**

   - Per esportare le voci, fare clic su **Esporta.** Nella finestra di dialogo visualizzata, salvare il file .csv file.

> [!NOTE]
> Se le organizzazioni sono configurate per inviare messaggi segnalati dall'utente solo alla cassetta postale personalizzata, i messaggi segnalati non verranno inviati per la nuova analisi e i risultati in **Messaggi** segnalati dall'utente saranno sempre vuoti.

### <a name="undo-user-submissions"></a>Annullare gli invii utente

Una volta che un utente invia un messaggio di posta elettronica sospetto alla cassetta postale personalizzata, l'utente e l'amministratore non hanno la possibilità di annullare l'invio. Se l'utente desidera recuperare la posta elettronica, sarà disponibile per il ripristino nelle cartelle Posta eliminata o Posta indesiderata.

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a>Inviare messaggi a Microsoft dalla cassetta postale personalizzata

Se la cassetta postale personalizzata è stata configurata per intercettare i messaggi segnalati dall'utente senza inviare i messaggi a Microsoft, è possibile trovare e inviare messaggi specifici a Microsoft per l'analisi. Questo sposta in modo efficace un invio utente a un invio da amministratore.

Nella scheda **Messaggi segnalati dall'utente** selezionare un messaggio nell'elenco, fare clic su Invia a **Microsoft** per l'analisi e quindi selezionare uno dei valori seguenti nell'elenco a discesa:

- **Segnala pulito**
- **Segnalare phishing**
- **Segnalare malware**
- **Segnalare posta indesiderata**
- **Attivare l'indagine**

![Nuove opzioni sul pulsante Azione](../../media/user-submission-custom-mailbox-action-button.png)
