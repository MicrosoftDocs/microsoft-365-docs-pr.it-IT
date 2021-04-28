---
title: Segnalare falsi positivi e falsi negativi in Outlook
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: Admin
ms.topic: how-to
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: Informazioni su come segnalare falsi positivi e falsi negativi in Outlook e abilitare i componenti aggiuntivi Segnala messaggio e Segnala phishing.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 38f940a98581c5678eef0c57c95f6349cdb41de8
ms.sourcegitcommit: ddb1bf56bcba4f03c803f79492e8cd0dc41a3d7a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2021
ms.locfileid: "52065175"
---
# <a name="report-false-positives-and-false-negatives-in-outlook"></a>Segnalare falsi positivi e falsi negativi in Outlook

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
> Se si è un amministratore in un'organizzazione di Microsoft 365 con cassette postali di Exchange Online, è consigliabile utilizzare il portale invii nel Centro sicurezza & conformità. Per ulteriori informazioni, vedere [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).

Nelle organizzazioni di Microsoft 365 con cassette postali in Exchange Online o nelle cassette postali locali che utilizzano l'autenticazione moderna ibrida, è possibile inviare falsi positivi (buona posta elettronica contrassegnata come posta indesiderata) e falsi negativi (posta elettronica non consentita e phish consentiti) a Exchange Online Protection (EOP).

## <a name="things-to-remember-before-you-use-the-report-message-feature"></a>Aspetti da ricordare prima di utilizzare la funzionalità Segnala messaggio

- Per una migliore esperienza di invio da parte dell'utente, usa il componente aggiuntivo Segnala messaggio o Segnala phishing.

- Si noti che questo componente aggiuntivo funziona per Outlook in tutte le piattaforme, ovvero sul Web, iOS, Android e Desktop.

- Se si è un amministratore di un'organizzazione con cassette postali di Exchange Online, utilizzare il portale invii nel Centro sicurezza & conformità. Per ulteriori informazioni, vedere [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).

- È possibile configurare l'invio dei messaggi direttamente a Microsoft, a una cassetta postale specificata o a entrambi. Per ulteriori informazioni, vedere [Criteri di invio degli utenti.](user-submission.md)

- Per ulteriori informazioni sulla segnalazione dei messaggi a Microsoft, vedere [Segnalare messaggi e file a Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="use-the-report-message-feature"></a>Utilizzare la funzionalità Segnala messaggio

### <a name="report-junk-and-phishing-messages"></a>Segnalare messaggi di posta indesiderata e phishing

Per i messaggi in Posta in arrivo o qualsiasi altra cartella di posta elettronica ad eccezione della posta indesiderata, utilizzare il metodo seguente per segnalare messaggi di posta indesiderata e phishing:

1. Fare clic **sui puntini** di sospensione Altre azioni nell'angolo superiore destro del messaggio selezionato, fare clic su Segnala messaggio dal menu a discesa e quindi selezionare **Posta** indesiderata o **Phishing.** 
  
   > [!div class="mx-imgBorder"]
   > ![Report Message - More actions](../../media/report-message-more-actions.png)

   > [!div class="mx-imgBorder"]
   > ![Segnala messaggio - Posta indesiderata e phishing](../../media/report-message-junk-phishing.png)

2. I messaggi selezionati verranno inviati a Microsoft per l'analisi e:

   - Spostato nella cartella Posta indesiderata se è stato segnalato come posta indesiderata.

   - Eliminato se è stato segnalato come phishing.
   
### <a name="report-messages-that-are-not-junk"></a>Segnalare messaggi non indesiderati

1. Fare clic **sui puntini** di sospensione Altre azioni nell'angolo superiore destro del messaggio selezionato, scegliere Segnala messaggio dal menu a discesa e quindi fare clic su **Non indesiderato.**   

   > [!div class="mx-imgBorder"]
   > ![Report Message - More actions](../../media/report-message-more-actions.png)

   > [!div class="mx-imgBorder"]
   > ![Segnala messaggio - Non indesiderato](../../media/report-message-not-junk.png)

2. Il messaggio selezionato verrà inviato a Microsoft per l'analisi e spostato in Posta in arrivo o in qualsiasi altra cartella specificata.

## <a name="enable-the-report-message-and-report-phishing-add-ins"></a>Abilitare i componenti aggiuntivi Segnala messaggio e Segnala phishing

I componenti aggiuntivi Segnala messaggio e Segnala phishing per Outlook e Outlook sul Web (in precedenza noto come Outlook Web App) consentono agli utenti di segnalare facilmente falsi positivi (buona posta elettronica contrassegnata come non buona) o falsi negativi (posta elettronica non consentita) a Microsoft e alle sue affiliate per l'analisi. 

Microsoft usa questi invii per migliorare l'efficacia delle tecnologie di protezione della posta elettronica. Si supponga, ad esempio, che gli utenti segnalano molti messaggi utilizzando il componente aggiuntivo Segnala phishing. Queste informazioni vengono visualizzate nel dashboard di sicurezza e in altri report. Il team di sicurezza dell'organizzazione può utilizzare queste informazioni per indicare che potrebbe essere necessario aggiornare i criteri anti-phishing. 

È possibile installare il componente aggiuntivo Segnala messaggio o Segnala phishing. Se si desidera che gli utenti segnalano messaggi di posta indesiderata e di phishing, distribuire il componente aggiuntivo Segnala messaggio nell'organizzazione. Per ulteriori informazioni, vedere Enable the Report Message add-in. 

Il componente aggiuntivo Segnala messaggio consente di segnalare sia i messaggi di posta indesiderata che i messaggi di phishing. Gli amministratori possono abilitare il componente aggiuntivo Segnala messaggio per l'organizzazione e i singoli utenti possono installarlo automaticamente. 

Il componente aggiuntivo Segnala phishing consente di segnalare solo i messaggi di phishing. Gli amministratori possono abilitare il componente aggiuntivo Segnala phishing per l'organizzazione e i singoli utenti possono installarlo automaticamente. 

Se si è un singolo utente, è possibile abilitare entrambi i componenti aggiuntivi.

se si è un amministratore globale o un amministratore di Exchange Online ed Exchange è configurato per l'utilizzo dell'autenticazione OAuth, è possibile abilitare il componente aggiuntivo Segnala messaggio e il componente aggiuntivo Segnala phishing per l'organizzazione. Entrambi i componenti aggiuntivi sono ora disponibili tramite [distribuzione centralizzata.](../../admin/manage/centralized-deployment-of-add-ins.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare?

- Sia il componente aggiuntivo Segnala messaggio che il componente aggiuntivo Segnala phishing funzionano con la maggior parte delle sottoscrizioni di Microsoft 365 e i prodotti seguenti:

  - Outlook sul Web
  - Outlook 2013 SP1 o versione successiva
  - Outlook 2016 per Mac
  - Outlook incluso con le app di Microsoft 365 per le aziende
  - App Outlook per iOS e Android

- Entrambi i componenti aggiuntivi non sono disponibili per le cassette postali condivise o le cassette postali nelle organizzazioni exchange locali.

- Il Web browser esistente dovrebbe funzionare sia con i componenti aggiuntivi Segnala messaggio che Segnala phishing. Tuttavia, se si nota che il componente aggiuntivo non è disponibile o non funziona come previsto, provare un browser diverso.

- Per le installazioni dell'organizzazione, l'organizzazione deve essere configurata per l'utilizzo dell'autenticazione OAuth. Per ulteriori informazioni, vedere [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).

- Gli amministratori devono essere membri del gruppo di ruoli Amministratori globali. Per altre informazioni, vedere [Autorizzazioni nel Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).

## <a name="get-the-report-message-add-in"></a>Ottenere il componente aggiuntivo Segnala messaggio

### <a name="get-the-add-in-for-yourself"></a>Ottenere il componente aggiuntivo per se stessi

1. Passare a Microsoft AppSource <https://appsource.microsoft.com/marketplace/apps> all'indirizzo e cercare il componente aggiuntivo Segnala messaggio. Per passare direttamente al componente aggiuntivo Segnala messaggio, passare a <https://appsource.microsoft.com/product/office/wa104381180> .

2. Fai **clic su SCARICA ORA**.

   ![Segnala messaggio - Scaricalo subito](../../media/ReportMessageGETITNOW.png)

3. Nella finestra di dialogo visualizzata esaminare le condizioni per l'utilizzo e l'informativa sulla privacy e quindi fare clic su **Continua.**

4. Accedi usando l'account aziendale o dell'istituto di istruzione (per uso aziendale) o l'account Microsoft (per uso personale).

Dopo aver installato e abilitato il componente aggiuntivo, verranno visualizzate le icone seguenti:

- In Outlook l'icona è simile alla seguente:

  > [!div class="mx-imgBorder"]
  > ![Icona del componente aggiuntivo Segnala messaggio per Outlook](../../media/OutlookReportMessageIcon.png)

- In Outlook sul Web l'icona è simile alla seguente:

  > [!div class="mx-imgBorder"]
  > ![Icona del componente aggiuntivo Report di Outlook sul Web](../../media/owa-report-message-icon.png)

### <a name="get-the-add-in-for-your-organization"></a>Ottenere il componente aggiuntivo per l'organizzazione

> [!NOTE]
> La visualizzazione del componente aggiuntivo nell'organizzazione potrebbe richiedere fino a 12 ore.

1. Nell'interfaccia di amministrazione di Microsoft 365  passare alla pagina Impostazioni \> **componenti aggiuntivi all'indirizzo** <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> . Se la pagina componenti  aggiuntivi non è visualizzata, passare al collegamento Impostazioni Componenti aggiuntivi app integrate nella parte superiore  \>  \>  della **pagina App** integrate.

2. Selezionare **Distribuisci componente aggiuntivo** nella parte superiore della pagina e quindi selezionare **Avanti.**

   ![Pagina Servizi e componenti aggiuntivi nell'interfaccia di amministrazione di Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. Nel riquadro **a comparsa Distribuisci un** nuovo componente aggiuntivo visualizzato esaminare le informazioni e quindi fare clic su **Avanti.**

4. Nella pagina successiva fai clic su **Scegli dallo Store.**

   ![Distribuire una nuova pagina del componente aggiuntivo](../../media/NewAddInScreen2.png)

5. Nella pagina **Seleziona componente aggiuntivo visualizzata** fare clic nella casella **Di** ricerca, immettere **Segnala** messaggio e quindi fare clic su **Cerca** ![ icona ](../../media/search-icon.png) Ricerca. Nell'elenco dei risultati, trovare **Segnala messaggio e** quindi fare clic su **Aggiungi.**

   ![Selezionare i risultati della ricerca di componenti aggiuntivi](../../media/NewAddInScreen3.png)

6. Nella finestra di dialogo visualizzata esaminare le informazioni sulla licenza e sulla privacy e quindi fare clic su **Continua.**

7. Nella pagina **Configura componente aggiuntivo visualizzata** configurare le impostazioni seguenti:

   - **Utenti assegnati**: selezionare uno dei valori seguenti:

     - **Tutti** (impostazione predefinita)
     - **Utenti/gruppi specifici**
     - **Solo io**

   - **Metodo di distribuzione:** selezionare uno dei valori seguenti:

     - **Risolto (impostazione predefinita):** il componente aggiuntivo viene distribuito automaticamente agli utenti specificati e non può essere rimosso.
     - **Disponibile**: gli utenti possono installare il componente aggiuntivo in **Home** \> **Get add-ins** \> **Admin-managed**.
     - **Facoltativo:** il componente aggiuntivo viene distribuito automaticamente agli utenti specificati, ma può scegliere di rimuoverlo.

   ![Pagina Configura componente aggiuntivo](../../media/configure-add-in.png)

   Al termine, fare clic su **Distribuisci**.

8. Nella pagina **Deploy Report Message** visualizzata verrà visualizzato un rapporto sullo stato seguito da una conferma della distribuzione del componente aggiuntivo. Dopo aver letto le informazioni, fare clic su **Avanti.**

   ![Pagina Distribuisci messaggio di report](../../media/deploy-report-message-page.png)

9. Nella pagina **Annuncia componente aggiuntivo visualizzata** esaminare le informazioni e quindi fare clic su **Chiudi.**

   ![Pagina Annuncia componente aggiuntivo](../../media/announce-add-in-page.png)

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a>Rivedere o modificare le impostazioni per il componente aggiuntivo Segnala messaggio

1. Nell'interfaccia di amministrazione di Microsoft 365  passare alla pagina Impostazioni \> **componenti aggiuntivi all'indirizzo** <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> . Se la pagina componenti  aggiuntivi non è visualizzata, passare al collegamento Impostazioni Componenti aggiuntivi app integrate nella parte superiore  \>  \>  della **pagina App** integrate.

   ![Pagina Servizi e Add-Ins nella nuova interfaccia di amministrazione di Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. Individuare e selezionare il componente aggiuntivo **Segnala** messaggio.

3. Nel riquadro **a comparsa Modifica messaggio** rapporto visualizzato esaminare e modificare le impostazioni in base alle esigenze dell'organizzazione. Al termine, scegliere **Salva**.

   ![Impostazioni per il componente aggiuntivo Segnala messaggio](../../media/EditReportMessageAddIn.png)

## <a name="get-the-report-phishing-add-in"></a>Ottenere il componente aggiuntivo Segnala phishing

### <a name="get-the-add-in-for-yourself"></a>Ottenere il componente aggiuntivo per se stessi

1. Vai a Microsoft AppSource <https://appsource.microsoft.com/marketplace/apps> all'indirizzo e cerca il componente aggiuntivo Segnala phishing.

2. Fai **clic su SCARICA ORA**.

3. Nella finestra di dialogo visualizzata esaminare le condizioni per l'utilizzo e l'informativa sulla privacy e quindi fare clic su **Continua.**

4. Accedi usando l'account aziendale o dell'istituto di istruzione (per uso aziendale) o l'account Microsoft (per uso personale).

Dopo aver installato e abilitato il componente aggiuntivo, verranno visualizzate le icone seguenti:

- In Outlook l'icona è simile alla seguente:

  ![Segnalare l'icona del componente aggiuntivo phishing per Outlook](../../media/Outlook-ReportPhishing.png)

- In Outlook sul Web l'icona è simile alla seguente:

  > [!div class="mx-imgBorder"]
  > ![Icona del componente aggiuntivo Di phishing per i report di Outlook sul Web](../../media/OWA-ReportPhishing.png)

### <a name="get-the-add-in-for-your-organization"></a>Ottenere il componente aggiuntivo per l'organizzazione

> [!NOTE]
> La visualizzazione del componente aggiuntivo nell'organizzazione potrebbe richiedere fino a 12 ore.

1. Nell'interfaccia di amministrazione di Microsoft 365  passare alla pagina Impostazioni \> **componenti aggiuntivi all'indirizzo** <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> . Se la pagina componenti  aggiuntivi non è visualizzata, passare al collegamento Impostazioni Componenti aggiuntivi app integrate nella parte superiore  \>  \>  della **pagina App** integrate.

2. Selezionare **Distribuisci componente aggiuntivo** nella parte superiore della pagina e quindi selezionare **Avanti.**

   ![Pagina Servizi e componenti aggiuntivi nell'interfaccia di amministrazione di Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. Nel riquadro **a comparsa Distribuisci un** nuovo componente aggiuntivo visualizzato esaminare le informazioni e quindi fare clic su **Avanti.**

4. Nella pagina successiva fai clic su **Scegli dallo Store.**

   ![Distribuire una nuova pagina del componente aggiuntivo](../../media/NewAddInScreen2.png)

5. Nella pagina **Seleziona componente aggiuntivo visualizzata** fare clic nella casella **Di** ricerca, immettere **Segnala phishing** e quindi fare clic su **Cerca** ![ icona ](../../media/search-icon.png) Ricerca. Nell'elenco dei risultati, individuare **Segnala phishing** e quindi fare clic su **Aggiungi.**

6. Nella finestra di dialogo visualizzata esaminare le informazioni sulla licenza e sulla privacy e quindi fare clic su **Continua.**

7. Nella pagina **Configura componente aggiuntivo visualizzata** configurare le impostazioni seguenti:

   - **Utenti assegnati**: selezionare uno dei valori seguenti:

     - **Tutti** (impostazione predefinita)
     - **Utenti/gruppi specifici**
     - **Solo io**

   - **Metodo di distribuzione:** selezionare uno dei valori seguenti:

     - **Risolto (impostazione predefinita):** il componente aggiuntivo viene distribuito automaticamente agli utenti specificati e non può essere rimosso.
     - **Disponibile**: gli utenti possono installare il componente aggiuntivo in **Home** \> **Get add-ins** \> **Admin-managed**.
     - **Facoltativo:** il componente aggiuntivo viene distribuito automaticamente agli utenti specificati, ma può scegliere di rimuoverlo.

   Al termine, fare clic su **Distribuisci**.

8. Nella pagina **Distribuisci phishing** report visualizzata verrà visualizzato un rapporto sullo stato seguito da una conferma della distribuzione del componente aggiuntivo. Dopo aver letto le informazioni, fare clic su **Avanti.**

9. Nella pagina **Annuncia componente aggiuntivo visualizzata** esaminare le informazioni e quindi fare clic su **Chiudi.**

## <a name="review-or-edit-settings-for-the-report-phishing-add-in"></a>Rivedere o modificare le impostazioni per il componente aggiuntivo Segnala phishing

1. Nell'interfaccia di amministrazione di Microsoft 365  passare alla pagina Impostazioni \> **componenti aggiuntivi all'indirizzo** <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> . Se la pagina componenti  aggiuntivi non è visualizzata, passare al collegamento Impostazioni Componenti aggiuntivi app integrate nella parte superiore  \>  \>  della **pagina App** integrate.

2. Individuare e selezionare il **componente aggiuntivo Segnala** phishing.

3. Nel riquadro **a comparsa Modifica rapporto Phishing** visualizzato, esaminare e modificare le impostazioni in base alle esigenze dell'organizzazione. Al termine, scegliere **Salva**.

## <a name="view-and-review-reported-messages"></a>Visualizzare ed esaminare i messaggi segnalati

Per esaminare i messaggi che gli utenti segnalano a Microsoft, sono disponibili le opzioni seguenti:

- Usa il portale per gli invii di amministratori. Per ulteriori informazioni, vedere [View user submissions to Microsoft](admin-submission.md#view-user-submissions-to-microsoft).

- Creare una regola del flusso di posta (nota anche come regola di trasporto) per inviare copie dei messaggi segnalati. Per istruzioni, vedere [Use mail flow rules to see what your users are reporting to Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).