---
title: Invii di amministratore
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
description: Gli amministratori possono imparare a usare il portale per gli invii nel centro sicurezza & Compliance per inviare messaggi di posta elettronica sospetti, sospette mail di phishing, posta indesiderata e altre informazioni potenzialmente nocive, URL e file a Microsoft per l'analisi.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ed417db93bc2f3efa6b85b0ef97c10b5941cd8eb
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029515"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a>Usare l'Invio dell'amministratore per inviare posta indesiderata sospetta, phishing, URL e file a Microsoft

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


In Microsoft 365 organizzazioni con cassette postali in Exchange Online, gli amministratori possono utilizzare il portale degli invii nel centro sicurezza & Compliance per inviare messaggi di posta elettronica, URL e allegati a Microsoft per l'analisi.

Quando si invia un messaggio di posta elettronica, si otterrà quanto segue:

1. **Verifica dell'autenticazione della posta elettronica**: informazioni sull'autenticazione del messaggio di posta elettronica superato o meno quando è stato recapitato.
2. **Hit dei criteri**: informazioni su tutti i criteri che possono aver consentito o bloccato la posta elettronica in arrivo nel tenant, sovrascrivendo i verdetti del filtro di servizio.
3. **Reputazione payload/detonazione**: esame degli URL e degli allegati del messaggio.
4. **Analisi del Grader**: recensione condotta dai selezionatori umani per confermare se i messaggi sono dannosi o meno.

> [!IMPORTANT]
> La reputazione payload/la detonazione e l'analisi del selezionatore non vengono eseguite in tutti i tenant. Le informazioni vengono bloccate all'esterno dell'organizzazione quando i dati non dovrebbero lasciare il limite del tenant ai fini della conformità.

Per altri modi per inviare messaggi di posta elettronica, URL e allegati a Microsoft, vedere [segnalare i messaggi e i file a Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare

- Aprire il Centro sicurezza e conformità in<https://protection.office.com/>. Per passare direttamente alla pagina **invio** , utilizzare <https://protection.office.com/reportsubmission> .

- Per inviare messaggi e file a Microsoft, è necessario essere membri di uno dei gruppi di ruoli seguenti:

  - **Gestione organizzazione** o **Amministratore sicurezza** nel [Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).

  - **Gestione dell'organizzazione** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).

    Si noti che l'appartenenza a questo gruppo di ruoli è necessaria per [visualizzare gli invii degli utenti alla cassetta postale personalizzata](#view-user-submissions-to-the-custom-mailbox) come descritto più avanti in questo articolo.

- Per ulteriori informazioni sul modo in cui gli utenti possono inviare messaggi e file a Microsoft, vedere [segnalare messaggi e file a Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="report-suspicious-content-to-microsoft"></a>Segnalare contenuti sospetti a Microsoft

1. Nel centro sicurezza & conformità, accedere a invii di **gestione delle minacce** \> , verificare di essere nella scheda invii di **Amministrazione** e quindi fare clic su **nuovo invio**.

2. Utilizzare il riquadro a comparsa **nuovo invio** che sembra inviare il messaggio, l'URL o l'allegato come descritto nelle sezioni seguenti.

### <a name="submit-a-questionable-email-to-microsoft"></a>Inviare un messaggio di posta elettronica discutibile a Microsoft

1. Nella sezione **tipo oggetto** selezionare **posta elettronica**. Nella sezione **formato invio** , utilizzare una delle seguenti opzioni:

   - **ID messaggio di rete**: questo è un valore GUID disponibile nell'intestazione **x-MS-Exchange-Organization-network-Message-ID** del messaggio o nell'intestazione **x-ms-Office365-Filtering-Correlation-ID** nei messaggi in quarantena.

   - **File**: fare clic su **Scegli file**. Nella finestra di dialogo che si apre, individuare e selezionare il file. eml o. msg, quindi fare clic su **Apri**.

   > [!NOTE]
   > Gli amministratori con Defender per Office 365 piano 1 o piano 2 sono in grado di inviare messaggi vecchi come 30 giorni. Altri amministratori saranno in grado di tornare indietro di 7 giorni.

2. Nella sezione **destinatari** specificare uno o più destinatari a cui si desidera eseguire il controllo dei criteri. Il controllo dei criteri determina se l'analisi del messaggio di posta elettronica è stata ignorata a causa di criteri dell'organizzazione o dell'utente.

3. Nella sezione **motivo della presentazione** selezionare una delle opzioni seguenti:

   - **Non deve essere stato bloccato**

   - **Avrebbe dovuto essere bloccato**: selezionare **posta indesiderata**, **phishing** o **malware**. Se non si è sicuri, utilizzare il miglior giudizio.

4. Al termine, fare clic sul pulsante **Invia** .

   ![Esempio di invio di URL](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a>Inviare un URL sospetto a Microsoft

1. Nella sezione **tipo oggetto** selezionare **URL**. Nella casella che viene visualizzata, immettere l'URL completo (ad esempio, `https://www.fabrikam.com/marketing.html` ).

2. Nella sezione **motivo della presentazione** selezionare una delle opzioni seguenti:

   - **Non deve essere stato bloccato**

   - **Avrebbe dovuto essere bloccato**: selezionare **phishing** o **malware**.

3. Al termine, fare clic sul pulsante **Invia** .

   ![Esempio di invio tramite posta elettronica](../../media/submission-url-flyout.png)

### <a name="submit-a-suspected-file-to-microsoft"></a>Inviare un file sospetto a Microsoft

1. Nella sezione **tipo oggetto** selezionare **allegato**.

2. Fare clic su **Scegli file**. Nella finestra di dialogo che si apre, individuare e selezionare il file e quindi fare clic su **Apri**.

3. Nella sezione **motivo della presentazione** selezionare una delle opzioni seguenti:

   - **Non deve essere stato bloccato**

   - **Avrebbe dovuto essere bloccato**: il **malware** è l'unica scelta e viene selezionato automaticamente..

4. Al termine, fare clic sul pulsante **Invia** .

   ![Esempio di invio degli allegati](../../media/submission-file-flyout.PNG)

## <a name="view-admin-submissions"></a>Visualizzazione di invii di amministratore

Nel centro sicurezza & conformità, accedere a invii di **gestione delle minacce** \> , verificare di essere nella scheda invii di **Amministrazione** e quindi fare clic su **nuovo invio**.

Nei pressi della parte superiore della pagina, è possibile immettere una data di inizio, una data di fine e (per impostazione predefinita) è possibile filtrare per **ID invio** (un valore GUID assegnato a ogni invio) immettendo un valore nella casella e facendo clic su ![ Aggiorna ](../../media/scc-quarantine-refresh.png) . È possibile immettere più valori separati da virgole.

Per modificare i criteri di filtro, fare clic sul pulsante **ID invio** e scegliere uno dei seguenti valori:

- **Mittente**
- **Oggetto/URL/nome file**
- **Inviato da**
- **Tipo di invio**
- **Stato**

![Opzioni di filtro per invii di amministratore](../../media/admin-submission-email-filter-options.png)

Per esportare i risultati, fare clic su **Esporta** vicino alla parte superiore della pagina e selezionare **dati grafico** o **tabella**. Nella finestra di dialogo che viene visualizzata, salvare il file. csv.

Al di sotto del grafico sono disponibili tre schede: **posta elettronica** (impostazione predefinita), **URL** e **allegato**.

### <a name="view-admin-email-submissions"></a>Visualizzazione di invii di posta elettronica di amministratore

Fare clic sulla scheda **posta elettronica** .

È possibile fare clic sul pulsante **Opzioni colonna** vicino alla parte inferiore della pagina per aggiungere o rimuovere colonne dalla visualizzazione:

- **Data**
- **ID invio**: valore GUID assegnato a ogni invio.
- **Inviato da**<sup>\*</sup>
- **Oggetto**<sup>\*</sup>
- **Mittente**
- **Indirizzo IP mittente**<sup>\*</sup>
- **Tipo di invio**
- **Motivo per il recapito**
- **Stato**<sup>\*</sup>

  <sup>\*</sup> Se si fa clic su questo valore, le informazioni dettagliate vengono visualizzate in un riquadro a comparsa.

#### <a name="admin-submission-rescan-details"></a>Dettagli di rianalisi dell'invio dell'amministratore

I messaggi inviati in invii di amministratore vengono rianalizzati e i risultati vengono visualizzati nel riquadro a comparsa dei dettagli:

- Se si è verificato un errore nell'autenticazione della posta elettronica del mittente al momento del recapito.
- Informazioni su eventuali hit di criteri che potrebbero aver influenzato o ignorato il verdetto di un messaggio.
- Risultati di detonazione correnti per verificare se gli URL o i file contenuti nel messaggio sono stati dannosi o meno.
- Commenti e suggerimenti dei selezionatori.

Se è stata trovata una sostituzione, la rianalisi deve essere completata in alcuni minuti. Se non è stato riscontrato un problema nell'autenticazione della posta elettronica o se il recapito non è stato influenzato da una sostituzione, il feedback dei selezionatori potrebbe richiedere fino a un giorno.

### <a name="view-admin-url-submissions"></a>Visualizzazione di invii di URL di amministrazione

Fare clic sulla scheda **URL** .

È possibile fare clic sul pulsante **Opzioni colonna** vicino alla parte inferiore della pagina per aggiungere o rimuovere colonne dalla visualizzazione:

- **Data**
- **ID invio**
- **Inviato da**<sup>\*</sup>
- **URL**<sup>\*</sup>
- **Tipo di invio**
- **Stato**<sup>\*</sup>

  <sup>\*</sup> Se si fa clic su questo valore, le informazioni dettagliate vengono visualizzate in un riquadro a comparsa.

### <a name="view-admin-attachment-submissions"></a>Visualizza invii degli allegati di amministratore

Fare clic sulla scheda **allegati** .

È possibile fare clic sul pulsante **Opzioni colonna** vicino alla parte inferiore della pagina per aggiungere o rimuovere colonne dalla visualizzazione:

- **Data**
- **ID invio**
- **Inviato da**<sup>\*</sup>
- **Nome file**<sup>\*</sup>
- **Tipo di invio**
- **Stato**<sup>\*</sup>

  <sup>\*</sup> Se si fa clic su questo valore, le informazioni dettagliate vengono visualizzate in un riquadro a comparsa.

## <a name="view-user-submissions-to-microsoft"></a>Visualizzazione degli invii degli utenti a Microsoft

Se è stato distribuito il [componente](enable-the-report-message-add-in.md)aggiuntivo per i messaggi di report, il [componente aggiuntivo](enable-the-report-phish-add-in.md)per il phishing dei report o gli utenti che utilizzano la creazione di report [incorporati in Outlook sul Web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), è possibile visualizzare gli elementi segnalati nella scheda **invii utente** .

1. Nel centro sicurezza & conformità, accedere a invii di **gestione delle minacce** \> .

2. Selezionare la scheda **invii utente** e quindi fare clic su **nuovo invio**.

È possibile fare clic sul pulsante **Opzioni colonna** vicino alla parte inferiore della pagina per aggiungere o rimuovere colonne dalla visualizzazione:

- **Inviato il**
- **Inviato da**<sup>\*</sup>
- **Oggetto**<sup>\*</sup>
- **Mittente**
- **Indirizzo IP mittente**<sup>\*</sup>
- **Tipo di invio**

<sup>\*</sup> Se si fa clic su questo valore, le informazioni dettagliate vengono visualizzate in un riquadro a comparsa.

Nella parte superiore della pagina, è possibile immettere una data di inizio, una data di fine e (per impostazione predefinita) è possibile filtrare in base al **mittente** immettendo un valore nella casella e facendo clic su ![ Aggiorna ](../../media/scc-quarantine-refresh.png) . È possibile immettere più valori separati da virgole.

Per modificare i criteri di filtro, fare clic sul pulsante **mittente** e scegliere uno dei seguenti valori:

- **Dominio del mittente**
- **Oggetto**
- **Inviato da**
- **Tipo di invio**
- **Indirizzo IP mittente**

![Opzioni di filtro per gli invii degli utenti](../../media/user-submissions-filter-options.png)

Per esportare i risultati, fare clic su **Esporta** vicino alla parte superiore della pagina e selezionare **dati grafico** o **tabella**. Nella finestra di dialogo che viene visualizzata, salvare il file. csv.

## <a name="view-user-submissions-to-the-custom-mailbox"></a>Visualizzare gli invii degli utenti alla cassetta postale personalizzata

**Se** è stata [configurata una cassetta postale personalizzata](user-submission.md) per la ricezione di messaggi segnalati dall'utente, è possibile visualizzare e inviare anche messaggi che sono stati recapitati alla cassetta postale di Reporting.

1. Nel centro sicurezza & conformità, accedere a invii di **gestione delle minacce** \> .

2. Selezionare la scheda **cassetta postale personalizzata** .

È possibile fare clic sul pulsante **Opzioni colonna** vicino alla parte inferiore della pagina per aggiungere o rimuovere colonne dalla visualizzazione:

- **Inviato il**
- **Inviato da**<sup>\*</sup>
- **Oggetto**<sup>\*</sup>
- **Mittente**
- **Indirizzo IP mittente**<sup>\*</sup>
- **Tipo di invio**

Nei pressi della parte superiore della pagina, è possibile immettere una data di inizio, una data di fine ed è possibile filtrare in base a quanto **inserito** inserendo un valore nella casella e facendo clic su ![ Aggiorna ](../../media/scc-quarantine-refresh.png) . È possibile immettere più valori separati da virgole.

Per esportare i risultati, fare clic su **Esporta** vicino alla parte superiore della pagina e selezionare **dati grafico** o **tabella**. Nella finestra di dialogo che viene visualizzata, salvare il file. csv.

## <a name="undo-user-submissions"></a>Annullamento degli invii degli utenti

Dopo che un utente ha inviato un messaggio di posta elettronica sospetto alla cassetta postale personalizzata, l'utente e l'amministratore non dispongono di un'opzione per annullare l'invio. Se l'utente desidera recuperare il messaggio di posta elettronica, sarà disponibile per il ripristino negli elementi eliminati o nelle cartelle di posta indesiderata.

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a>Inviare messaggi a Microsoft dalla cassetta postale personalizzata

Se è stata configurata la cassetta postale personalizzata per intercettare i messaggi segnalati dall'utente senza inviare i messaggi a Microsoft, è possibile trovare e inviare messaggi specifici a Microsoft per l'analisi. Questo consente di spostare efficacemente l'invio di un utente a un invio di amministratore.

Nella scheda **cassetta postale personalizzata** , selezionare un messaggio nell'elenco, fare clic sul pulsante **azione** ed eseguire una delle selezioni seguenti:

- **Relazione pulita**
- **Notifica di phishing**
- **Segnala malware**
- **Segnalare la posta indesiderata**

![Opzioni sul pulsante azione](../../media/user-submission-custom-mailbox-action-button.png)
