---
title: Invii dell'amministratore in Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Informazioni su come inviare messaggi di posta elettronica sospetti, sospette mail di phishing, la posta indesiderata e altre potenzialmente dannose, URL e file dalla propria azienda a Microsoft per l'analisi.
ms.openlocfilehash: 79f200963655e5fb07a04b686c1dd8cc3bbd0873
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034201"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a>Usare l'Invio dell'amministratore per inviare posta indesiderata sospetta, phishing, URL e file a Microsoft

Se si è un amministratore in un'organizzazione di Microsoft 365 con cassette postali in Exchange Online, è possibile utilizzare il portale degli invii nel centro sicurezza & Compliance per inviare messaggi di posta elettronica, URL e allegati a Microsoft per l'analisi.

Quando si invia un messaggio di posta elettronica, si ottengono informazioni su tutti i criteri che possono aver consentito la posta elettronica in arrivo nel tenant, nonché l'esame degli URL e degli allegati della posta. I criteri che possono aver consentito a un messaggio di posta elettronica includono l'elenco dei mittenti attendibili di un singolo utente e i criteri di livello tenant, ad esempio le regole del flusso di posta di Exchange (note anche come regole di trasporto)

Per altri modi per inviare messaggi di posta elettronica, URL e allegati a Microsoft, vedere [segnalare i messaggi e i file a Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare

- Aprire il Centro sicurezza e conformità in<https://protection.office.com/>. Per passare direttamente alla pagina **invio** , utilizzare <https://protection.office.com/reportsubmission>.

- È necessario disporre delle autorizzazioni prima di poter eseguire queste procedure. Per aggiungere, modificare ed eliminare i criteri di protezione da posta indesiderata, è necessario essere membri dei gruppi di ruoli **Gestione organizzazione**, **amministratore sicurezza**o **lettore di sicurezza** . Per altre informazioni sui gruppi di ruoli nel Centro sicurezza e conformità, vedere [Autorizzazioni nel Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).

- Per ulteriori informazioni sul modo in cui gli utenti possono inviare messaggi e file a Microsoft, vedere [segnalare messaggi e file a Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="report-suspicious-content-to-microsoft"></a>Segnalare contenuti sospetti a Microsoft

1. Nel centro sicurezza & conformità, accedere ai **messaggi di invio dell'amministratore**di gestione **Review** \> \> delle **minacce** .

2. Nella pagina **invii** che viene visualizzata, fare clic sul pulsante **nuovo invio** .

3. Utilizzare il riquadro a comparsa **nuovo invio** che sembra inviare il messaggio, l'URL o l'allegato come descritto nelle sezioni seguenti.

### <a name="submit-a-questionable-email-to-microsoft"></a>Inviare un messaggio di posta elettronica discutibile a Microsoft

1. Nella sezione **tipo oggetto** selezionare **posta elettronica**. Nella sezione **formato invio** , utilizzare una delle seguenti opzioni:

   - **ID messaggio di rete**: questo è un valore GUID disponibile nell'intestazione **X-MS-Exchange-Organization-network-Message-ID** del messaggio.

   - **File**: fare clic su **Scegli file**. Nella finestra di dialogo che si apre, individuare e selezionare il file. eml o. msg, quindi fare clic su **Apri**.

2. Nella sezione **destinatari** specificare uno o più destinatari a cui si desidera eseguire il controllo dei criteri. Il controllo dei criteri determina se l'analisi del messaggio di posta elettronica è stata ignorata a causa di criteri dell'organizzazione o dell'utente.

3. Nella sezione **motivo della presentazione** selezionare una delle opzioni seguenti:

   - **Non deve essere stato bloccato**

   - **Avrebbe dovuto essere bloccato**: selezionare **posta indesiderata**, **phishing**o **malware**. Se non si è sicuri, utilizzare il miglior giudizio.

4. Se il filtro è stato ignorato a causa di criteri al momento dell'invio, verranno visualizzate le informazioni relative a tale criterio.

   Se il filtro non è stato bypassato a causa di uno o più criteri, l'analisi verrà completata in alcuni minuti. Vedrai altre informazioni sull'invio facendo clic sul collegamento di stato. Questo include i risultati del controllo dei criteri e il verdetto di rianalisi. Si noti che non viene eseguito di nuovo il messaggio di posta elettronica tramite lo stack filtro completo ATP di Office 365 ma viene eseguita una nuova analisi parziale in base a determinati attributi di posta, URL o file.

5. Al termine, fare clic sul pulsante **Invia** .

![Esempio di invio di URL](../../media/submission-flyout-email.PNG)

### <a name="send-a-suspect-url-to-microsoft"></a>Inviare un URL sospetto a Microsoft

1. Nella sezione **tipo oggetto** selezionare **URL**. Nella casella che viene visualizzata, immettere l'URL completo (ad esempio, <https://www.fabrikam.com/marketing.html>).

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

1. Nel centro sicurezza & conformità, accedere ai **messaggi di invio dell'amministratore**di gestione **Review** \> \> delle **minacce** .

2. Nella pagina **invii** che viene visualizzata, verificare che la scheda **invii amministratore** sia selezionata.

Vicino alla parte superiore della pagina, è possibile immettere una data di inizio, una data di fine e (per impostazione predefinita) è possibile filtrare in base all' **ID di invio** immettendo un ![valore nella](../../media/scc-quarantine-refresh.png)casella e facendo clic su Aggiorna. È possibile immettere più valori separati da virgole.

Per modificare i criteri di filtro, fare clic sul pulsante **ID invio** e scegliere uno dei seguenti valori:

- **Mittente**
- **Oggetto/URL/nome file**
- **Inviato da**
- **Tipo di invio**
- **Stato**

![Opzioni di filtro per invii di amministratore](../../media/admin-submission-email-filter-options.png)

Per esportare i risultati, fare clic su **Esporta** vicino alla parte superiore della pagina e selezionare **dati grafico** o **tabella**. Nella finestra di dialogo che viene visualizzata, salvare il file. csv.

Al di sotto del grafico sono disponibili tre schede: **posta elettronica** (impostazione predefinita), **URL**e **allegato**.

### <a name="view-admin-email-submissions"></a>Visualizzazione di invii di posta elettronica di amministratore

Fare clic sulla scheda **posta elettronica** .

È possibile fare clic sul pulsante **Opzioni colonna** vicino alla parte inferiore della pagina per aggiungere o rimuovere colonne dalla visualizzazione:

- **Data**
- **ID invio**
- **Inviato da**<sup>\*</sup>
- **Oggetto**<sup>\*</sup>
- **Mittente**
- **Indirizzo IP mittente**<sup>\*</sup>
- **Tipo di invio**
- **Motivo per il recapito**
- **Stato**<sup>\*</sup>
- **Tipo di controllo**
- **Origine di controllo**

  <sup>\*</sup>Se si fa clic su questo valore, le informazioni dettagliate vengono visualizzate in un riquadro a comparsa.

### <a name="view-admin-url-submissions"></a>Visualizzazione di invii di URL di amministrazione

Fare clic sulla scheda **URL** .

È possibile fare clic sul pulsante **Opzioni colonna** vicino alla parte inferiore della pagina per aggiungere o rimuovere colonne dalla visualizzazione:

- **Data**
- **ID invio**
- **Inviato da**<sup>\*</sup>
- **URL**<sup>\*</sup>
- **Tipo di invio**
- **Stato**<sup>\*</sup>

  <sup>\*</sup>Se si fa clic su questo valore, le informazioni dettagliate vengono visualizzate in un riquadro a comparsa.

### <a name="view-admin-attachment-submissions"></a>Visualizza invii degli allegati di amministratore

Fare clic sulla scheda **allegati** .

È possibile fare clic sul pulsante **Opzioni colonna** vicino alla parte inferiore della pagina per aggiungere o rimuovere colonne dalla visualizzazione:

- **Data**
- **ID invio**
- **Inviato da**<sup>\*</sup>
- **Nome file**<sup>\*</sup>
- **Tipo di invio**
- **Stato**<sup>\*</sup>

  <sup>\*</sup>Se si fa clic su questo valore, le informazioni dettagliate vengono visualizzate in un riquadro a comparsa.

## <a name="view-user-submissions-to-microsoft"></a>Visualizzazione degli invii degli utenti a Microsoft

Se è stato distribuito il [componente aggiuntivo](enable-the-report-message-add-in.md)per i messaggi di report o si utilizza la creazione di report [incorporati in Outlook sul Web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md), è possibile visualizzare gli utenti che segnalano nella scheda **invii utente** .

1. Nel centro sicurezza & conformità, accedere ai **messaggi di invio dell'amministratore**di gestione **Review** \> \> delle **minacce** .

2. Nella pagina **invii** che viene visualizzata, fare clic sulla scheda **invii utente** .

È possibile fare clic sul pulsante **Opzioni colonna** vicino alla parte inferiore della pagina per aggiungere o rimuovere colonne dalla visualizzazione:

- **Inviato il**
- **Inviato da**<sup>\*</sup>
- **Oggetto**<sup>\*</sup>
- **Mittente**
- **Indirizzo IP mittente**<sup>\*</sup>
- **Tipo di invio**

<sup>\*</sup>Se si fa clic su questo valore, le informazioni dettagliate vengono visualizzate in un riquadro a comparsa.

Nella parte superiore della pagina, è possibile immettere una data di inizio, una data di fine e (per impostazione predefinita) è possibile filtrare in base al **mittente** immettendo un valore nella ![casella e](../../media/scc-quarantine-refresh.png)facendo clic su Aggiorna. È possibile immettere più valori separati da virgole.

Per modificare i criteri di filtro, fare clic sul pulsante **mittente** e scegliere uno dei seguenti valori:

- **Dominio del mittente**
- **Oggetto**
- **Inviato da**
- **Tipo di invio**
- **Indirizzo IP mittente**

![Opzioni di filtro per gli invii degli utenti](../../media/user-submissions-filter-options.png)

Per esportare i risultati, fare clic su **Esporta** vicino alla parte superiore della pagina e selezionare **dati grafico** o **tabella**. Nella finestra di dialogo che viene visualizzata, salvare il file. csv.

## <a name="view-user-submissions-to-the-custom-mailbox"></a>Visualizzare gli invii degli utenti alla cassetta postale personalizzata

Se è stata [configurata una cassetta postale personalizzata](user-submission.md) per la ricezione di messaggi segnalati dall'utente, è possibile visualizzare e inviare anche messaggi che sono stati recapitati alla cassetta postale di Reporting.

1. Nel centro sicurezza & conformità, accedere ai **messaggi di invio dell'amministratore**di gestione **Review** \> \> delle **minacce** .

2. Nella pagina **invii** che viene visualizzata, fare clic sulla scheda **cassetta postale personalizzata** .

È possibile fare clic sul pulsante **Opzioni colonna** vicino alla parte inferiore della pagina per aggiungere o rimuovere colonne dalla visualizzazione:

- **Inviato il**
- **Inviato da**<sup>\*</sup>
- **Oggetto**<sup>\*</sup>
- **Mittente**
- **Indirizzo IP mittente**<sup>\*</sup>
- **Tipo di invio**

Nei pressi della parte superiore della pagina, è possibile immettere una data di inizio, una data di fine ed è possibile filtrare in base a quanto **inserito** inserendo un valore nella casella ![e facendo](../../media/scc-quarantine-refresh.png)clic su Aggiorna. È possibile immettere più valori separati da virgole.

Per esportare i risultati, fare clic su **Esporta** vicino alla parte superiore della pagina e selezionare **dati grafico** o **tabella**. Nella finestra di dialogo che viene visualizzata, salvare il file. csv.

### <a name="submit-messages-to-microsoft-from-the-custom-mailbox"></a>Inviare messaggi a Microsoft dalla cassetta postale personalizzata

Se è stata configurata la cassetta postale personalizzata per intercettare i messaggi segnalati dall'utente senza inviare i messaggi a Microsoft, è possibile trovare e inviare messaggi specifici a Microsoft per l'analisi. Questo consente di spostare efficacemente l'invio di un utente a un invio di amministratore.

Nella scheda **cassetta postale personalizzata** , selezionare un messaggio nell'elenco, fare clic sul pulsante **azione** ed eseguire una delle selezioni seguenti:

- **Relazione pulita**
- **Notifica di phishing**
- **Segnala malware**
- **Segnalare la posta indesiderata**

![Opzioni sul pulsante azione](../../media/user-submission-custom-mailbox-action-button.png)
