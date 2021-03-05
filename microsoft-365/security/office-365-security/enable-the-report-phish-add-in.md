---
title: Abilitare il componente aggiuntivo Report Phish
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4250c4bc-6102-420b-9e0a-a95064837676
ms.collection:
- M365-security-compliance
description: Informazioni su come abilitare il componente aggiuntivo Segnala phishing per Outlook e Outlook sul Web, per singoli utenti o per l'intera organizzazione.
ms.openlocfilehash: 12543364943321689d0efa2c2942351b3d3ec6f9
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/04/2021
ms.locfileid: "50453766"
---
# <a name="enable-the-report-phishing-add-in"></a>Abilitare il componente aggiuntivo Segnala phishing

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> Gli amministratori di un'organizzazione di Microsoft 365 con cassette postali di Exchange Online consigliano di usare il portale Invii nel Centro sicurezza & conformità. Per altre informazioni, vedi Usare l'invio dell'amministratore per inviare posta [indesiderata, phish, URL e file sospetti a Microsoft.](admin-submission.md)

I componenti aggiuntivi Segnala messaggio e Segnala phishing per Outlook e Outlook sul Web (in precedenza noto come Outlook Web App) consentono di segnalare facilmente falsi positivi (messaggi di posta elettronica non consentiti) o falsi negativi (posta elettronica non consentita) a Microsoft e alle relative consociati per l'analisi.

Microsoft usa questi invii per migliorare l'efficacia delle tecnologie di protezione della posta elettronica. Si supponga, ad esempio, che gli utenti segnalano molti messaggi utilizzando il componente aggiuntivo Segnala phishing. Queste informazioni vengono visualizzate nel [dashboard di sicurezza](security-dashboard.md) e in altri report. Il team di sicurezza dell'organizzazione può utilizzare queste informazioni per indicare che potrebbe essere necessario aggiornare i criteri anti-phishing.

È possibile installare il componente aggiuntivo Segnala messaggio o Segnala phishing. Se si desidera che gli utenti segnalano messaggi di posta indesiderata e di phishing, distribuire il componente aggiuntivo Segnala messaggio nell'organizzazione. Per ulteriori informazioni, vedere [Abilitare il componente aggiuntivo Segnala messaggio.](enable-the-report-message-add-in.md)

Il componente aggiuntivo Segnala phishing consente di segnalare solo i messaggi di phishing. Gli amministratori possono abilitare il componente aggiuntivo Segnala phishing per l'organizzazione e i singoli utenti possono installarlo automaticamente.

Se si è un singolo utente, è possibile abilitare il componente aggiuntivo Segnala phishing [per se stessi.](#get-the-report-phishing-add-in-for-yourself)

Se si è un amministratore globale o un amministratore di Exchange Online ed Exchange è configurato per l'utilizzo dell'autenticazione OAuth, è possibile abilitare il componente aggiuntivo [Segnala phishing per l'organizzazione.](#get-and-enable-the-report-phishing-add-in-for-your-organization) Il report phishing Add-In è ora disponibile tramite [la distribuzione centralizzata.](../../admin/manage/centralized-deployment-of-add-ins.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare

- Il componente aggiuntivo Segnala phishing funziona con la maggior parte degli abbonamenti a Microsoft 365 e dei prodotti seguenti:

  - Outlook sul Web
  - Outlook 2013 SP1 o versione successiva
  - Outlook 2016 per Mac o versione successiva
  - Outlook incluso nelle app di Microsoft 365 per le aziende
  - App Outlook per iOS e Android

- Il componente aggiuntivo Segnala phishing non è disponibile per le cassette postali condivise o le cassette postali nelle organizzazioni Exchange locali.

- È possibile configurare i messaggi segnalati da copiare o reindirizzare a una cassetta postale specificata. Per altre informazioni, vedi [Criteri di invio degli utenti.](user-submission.md)

- Il Web browser esistente dovrebbe funzionare con il componente aggiuntivo Segnala phishing. Tuttavia, se si nota che il componente aggiuntivo non è disponibile o non funziona come previsto, provare un browser diverso.

- Per le installazioni dell'organizzazione, l'organizzazione deve essere configurata per l'utilizzo dell'autenticazione OAuth. Per ulteriori informazioni, vedere [Determine if Centralized Deployment of add-ins works for your organization.](../../admin/manage/centralized-deployment-of-add-ins.md)

- Gli amministratori devono essere membri del gruppo di ruoli Amministratori globali. Per altre informazioni, vedere [Autorizzazioni nel Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).

## <a name="get-the-report-phishing-add-in-for-yourself"></a>Ottenere il componente aggiuntivo Segnala phishing

1. Passare a Microsoft AppSource e cercare il componente aggiuntivo <https://appsource.microsoft.com/marketplace/apps> Segnala phishing.

2. Fare **clic su GET IT NOW**.

3. Nella finestra di dialogo visualizzata esaminare le condizioni per l'utilizzo e l'informativa sulla privacy e quindi fare clic su **Continua.**

4. Accedi usando l'account aziendale o dell'istituto di istruzione (per uso aziendale) o l'account Microsoft (per uso personale).

Dopo aver installato e abilitato il componente aggiuntivo, verranno visualizzate le icone seguenti:

- In Outlook l'icona è simile alla seguente:

  ![Segnala l'icona del componente aggiuntivo phishing per Outlook](../../media/Outlook-ReportPhishing.png)

- In Outlook sul Web, l'icona è simile alla seguente:

  ![Icona del componente aggiuntivo Di phishing per i report di Outlook sul Web](../../media/OWA-ReportPhishing.png)

## <a name="get-and-enable-the-report-phishing-add-in-for-your-organization"></a>Ottenere e abilitare il componente aggiuntivo Segnala phishing per l'organizzazione

> [!NOTE]
> La visualizzazione del componente aggiuntivo nell'organizzazione potrebbe richiedere fino a 12 ore.

1. Nell'interfaccia di amministrazione di Microsoft 365  passare alla pagina Componenti aggiuntivi impostazioni \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> all'indirizzo  ,  Se la pagina del componente aggiuntivo non è visualizzata, passare al collegamento Impostazioni componenti aggiuntivi app integrate nella parte superiore della pagina App \>  \>  integrate. 

2. Selezionare **Distribuisci componente aggiuntivo** nella parte superiore della pagina e quindi fare clic su **Avanti.**

   ![Pagina Servizi e componenti aggiuntivi nell'interfaccia di amministrazione di Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. Nel riquadro **a comparsa Distribuisci un** nuovo componente aggiuntivo visualizzato, esaminare le informazioni e quindi fare clic su **Avanti.**

4. Nella pagina successiva fai clic su **Scegli dallo Store.**

   ![Distribuire una nuova pagina del componente aggiuntivo](../../media/NewAddInScreen2.png)

5. Nella pagina **Seleziona componente aggiuntivo visualizzata,** fare clic nella casella **di** ricerca, immettere **Segnala phishing** e quindi fare clic **sull'icona** ![ ](../../media/search-icon.png) Cerca. Nell'elenco dei risultati, trovare **Segnala phishing** e quindi fare clic su **Aggiungi.**

6. Nella finestra di dialogo visualizzata esaminare le informazioni sulla licenza e sulla privacy e quindi fare clic su **Continua.**

7. Nella pagina **Configura componente** aggiuntivo visualizzata configurare le impostazioni seguenti:

   - **Utenti assegnati:** selezionare uno dei seguenti valori:

     - **Tutti** (impostazione predefinita)
     - **Utenti/gruppi specifici**
     - **Solo io**

   - **Metodo di distribuzione:** selezionare uno dei valori seguenti:

     - **Risolto (impostazione predefinita):** il componente aggiuntivo viene distribuito automaticamente agli utenti specificati e non può essere rimosso.
     - **Disponibile:** gli utenti possono installare il componente aggiuntivo in **Home** \> **Get add-ins** \> **Gestito dall'amministratore.**
     - **Facoltativo:** il componente aggiuntivo viene distribuito automaticamente agli utenti specificati, ma può scegliere di rimuoverlo.

   Al termine, fare clic su **Distribuisci.**

8. Nella pagina **Deploy Report Phishing** visualizzata verrà visualizzato un rapporto sullo stato seguito da una conferma della distribuzione del componente aggiuntivo. Dopo aver letto le informazioni, fare clic su **Avanti.**

9. Nella pagina **Annuncia componente aggiuntivo visualizzata** esaminare le informazioni e quindi fare clic su **Chiudi.**

## <a name="learn-how-to-use-the-report-phishing-add-in"></a>Informazioni su come usare il componente aggiuntivo Segnala phishing

Gli utenti a cui è assegnato il componente aggiuntivo visualizzano le icone seguenti:

- In Outlook l'icona è simile alla seguente:

  ![Segnala l'icona del componente aggiuntivo phishing per Outlook](../../media/Outlook-ReportPhishing.png)

- In Outlook sul Web, l'icona è simile alla seguente:

  ![Icona del componente aggiuntivo di phishing per i report di Outlook sul Web](../../media/OWA-ReportPhishing.png)

## <a name="review-or-edit-settings-for-the-report-phishing-add-in"></a>Rivedere o modificare le impostazioni per il componente aggiuntivo Segnala phishing

1. Nell'interfaccia di amministrazione di Microsoft 365  passare alla pagina Componenti aggiuntivi impostazioni \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> all'indirizzo  ,  Se la pagina del componente aggiuntivo non è visualizzata, passare al collegamento Impostazioni componenti aggiuntivi app integrate nella parte superiore della pagina App \>  \>  integrate. 

2. Trovare e selezionare il **componente aggiuntivo Segnala** phishing.

3. Nel riquadro **a comparsa Modifica** rapporto phishing visualizzato, rivedere e modificare le impostazioni in base alle esigenze dell'organizzazione. Al termine, scegliere **Salva**.

## <a name="view-and-review-reported-messages"></a>Visualizzare ed esaminare i messaggi segnalati

Per esaminare i messaggi che gli utenti segnalano a Microsoft, sono disponibili le opzioni seguenti:

- Usa il portale invii di amministratori. Per altre informazioni, vedi [Visualizzare gli invii degli utenti a Microsoft.](admin-submission.md#view-user-submissions-to-microsoft)

- Creare una regola del flusso di posta (nota anche come regola di trasporto) per inviare copie dei messaggi segnalati. Per istruzioni, vedere [Usare le regole del flusso di posta per vedere cosa segnalano gli](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)utenti a Microsoft.
