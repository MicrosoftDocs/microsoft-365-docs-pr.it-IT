---
title: Abilitare il componente aggiuntivo phishing report
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
description: Informazioni su come abilitare il componente aggiuntivo per il phishing dei report per Outlook e Outlook sul Web, per singoli utenti o per l'intera organizzazione.
ms.openlocfilehash: 6d86fdc710539bc3c74eb94f8931ca48a0c992c1
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029139"
---
# <a name="enable-the-report-phishing-add-in"></a>Abilitare il componente aggiuntivo Segnala phishing

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> Se si è un amministratore in un'organizzazione di Microsoft 365 con cassette postali di Exchange Online, è consigliabile utilizzare il portale invii nel centro sicurezza & Compliance. Per ulteriori informazioni, vedere [utilizzare l'invio di amministratore per inviare messaggi di posta indesiderata, phishing, URL e file a Microsoft](admin-submission.md).

I componenti aggiuntivi per il report e i report di phishing per Outlook e Outlook sul Web (in precedenza noti come Outlook Web App) consentono agli utenti di segnalare facilmente i falsi positivi (messaggi di posta elettronica validi contrassegnati come negativi) o falsi negativi (messaggi di posta elettronica non consentiti) a Microsoft e ai suoi affiliati per l'analisi.

Microsoft utilizza questi invii per migliorare l'efficacia delle tecnologie di protezione della posta elettronica. Si supponga, ad esempio, che le persone stiano segnalando numerosi messaggi utilizzando il componente aggiuntivo di phishing dei report. Queste informazioni si riferiscono al [dashboard di sicurezza](security-dashboard.md) e ad altri report. Il team di sicurezza dell'organizzazione può utilizzare queste informazioni per indicare che potrebbe essere necessario aggiornare i criteri di protezione anti-phishing.

È possibile installare il messaggio di report o il componente aggiuntivo di phishing del report. Se si desidera che gli utenti riportino messaggi di posta indesiderata e di phishing, distribuire il componente aggiuntivo per i messaggi di report nell'organizzazione. Per ulteriori informazioni, vedere [Enable the report Message Add-in](enable-the-report-message-add-in.md).

Il componente aggiuntivo per il phishing dei report consente di segnalare solo i messaggi di phishing. Gli amministratori possono abilitare il componente aggiuntivo per il phishing dei rapporti per l'organizzazione e i singoli utenti possono installarlo personalmente.

Se si è un singolo utente, è possibile [abilitare il componente aggiuntivo per il phishing dei report](#get-the-report-phishing-add-in-for-yourself).

Se si è un amministratore globale o un amministratore di Exchange Online ed Exchange è configurato per l'utilizzo dell'autenticazione OAuth, è possibile [abilitare il componente aggiuntivo per il phishing dei rapporti per l'organizzazione](#get-and-enable-the-report-phishing-add-in-for-your-organization). Il Add-In di phishing dei report è ora disponibile tramite la [distribuzione centralizzata](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare

- Il componente aggiuntivo di phishing dei rapporti è compatibile con la maggior parte delle sottoscrizioni Microsoft 365 e i prodotti seguenti:

  - Outlook sul Web
  - Outlook 2013 SP1 o versione successiva
  - Outlook 2016 per Mac
  - Outlook incluso con Microsoft 365 Apps for Enterprise

- Il componente aggiuntivo di phishing dei report non è disponibile per le cassette postali nelle organizzazioni Exchange locali.

- È possibile configurare i messaggi segnalati in modo che vengano copiati o reindirizzati a una cassetta postale specificata. Per ulteriori informazioni, vedere [criteri degli invii degli utenti](user-submission.md).

- Il Web browser esistente dovrebbe funzionare con il componente aggiuntivo di phishing dei report. Tuttavia, se si nota che il componente aggiuntivo non è disponibile o non funziona come previsto, provare con un altro browser.

- Per le installazioni organizzative, l'organizzazione deve essere configurata per l'utilizzo dell'autenticazione OAuth. Per ulteriori informazioni, vedere [determinare se la distribuzione centralizzata dei componenti aggiuntivi funziona per l'organizzazione](../../admin/manage/centralized-deployment-of-add-ins.md).

- Gli amministratori devono essere membri del gruppo di ruoli Global Admins. Per altre informazioni, vedere [Autorizzazioni nel Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).

## <a name="get-the-report-phishing-add-in-for-yourself"></a>Ottenere il componente aggiuntivo di phishing del rapporto per se stessi

1. Accedere a Microsoft AppSource <https://appsource.microsoft.com/marketplace/apps> e cercare il componente aggiuntivo di phishing del report.

2. Fare clic su **Ottieni subito**.

3. Nella finestra di dialogo che viene visualizzata, esaminare le condizioni di utilizzo e i criteri di privacy, quindi fare clic su **continua**.

4. Accedere con l'account aziendale o dell'Istituto di istruzione (per uso commerciale) o con il proprio account Microsoft (per uso personale).

Dopo aver installato e abilitato il componente aggiuntivo, vengono visualizzate le icone seguenti:

- In Outlook l'icona è simile alla seguente:

  ![Icona del componente aggiuntivo per il phishing dei rapporti per Outlook](../../media/Outlook-ReportPhishing.png)

- In Outlook sul Web, l'icona è simile alla seguente:

  ![Icona del componente aggiuntivo di phishing del rapporto di Outlook sul Web](../../media/OWA-ReportPhishing.png)

## <a name="get-and-enable-the-report-phishing-add-in-for-your-organization"></a>Ottenere e attivare il componente aggiuntivo per il phishing dei rapporti per l'organizzazione

> [!NOTE]
> La visualizzazione del componente aggiuntivo nell'organizzazione potrebbe richiedere fino a 12 ore.

1. Nell'interfaccia di amministrazione di Microsoft 365 passare alla pagina Vai alla pagina dei componenti aggiuntivi per le **Impostazioni** , \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> se la pagina del **componente aggiuntivo** non è visualizzata, passare al collegamento **Impostazioni** \> componenti aggiuntivi delle **app integrate** \>  nella parte superiore della pagina delle **app integrate** .

2. Selezionare **Distribuisci componente aggiuntivo nella** parte superiore della pagina e quindi fare clic su **Avanti**.

   ![Pagina Servizi e componenti aggiuntivi nell'interfaccia di amministrazione di Microsoft 365](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. Nel riquadro a comparsa **Distribuisci un nuovo componente aggiuntivo** che viene visualizzato, esaminare le informazioni e quindi fare clic su **Avanti**.

4. Nella pagina successiva fare clic su **Scegli nell'archivio**.

   ![Distribuire una nuova pagina del componente aggiuntivo](../../media/NewAddInScreen2.png)

5. Nella pagina **Seleziona componente aggiuntivo** visualizzata, fare clic nella casella di **ricerca** , immettere il **rapporto di phishing** e quindi fare clic su icona ricerca ricerca  ![ ](../../media/search-icon.png) . Nell'elenco dei risultati, trovare il **rapporto di phishing** e quindi fare clic su **Aggiungi**.

6. Nella finestra di dialogo che viene visualizzata, esaminare la gestione delle licenze e le informazioni sulla privacy, quindi fare clic su **continua**.

7. Nella pagina **Configura componente aggiuntivo** che viene visualizzata, configurare le seguenti impostazioni:

   - **Utenti assegnati**: selezionare uno dei valori seguenti:

     - **Tutti** (impostazione predefinita)
     - **Utenti/gruppi specifici**
     - **Solo io**

   - **Metodo di distribuzione**: selezionare uno dei valori seguenti:

     - **Fixed (impostazione predefinita)**: il componente aggiuntivo viene distribuito automaticamente agli utenti specificati e non è possibile rimuoverlo.
     - **Disponibile**: gli utenti possono installare il componente aggiuntivo in **casa** per \> **ottenere i componenti** aggiuntivi gestiti dall' \> **amministratore**.
     - **Facoltativo**: il componente aggiuntivo viene distribuito automaticamente agli utenti specificati, ma è possibile sceglierlo per rimuoverlo.

   Al termine, fare clic su **Distribuisci**.

8. Nella pagina **Distribuisci rapporto di phishing** che viene visualizzata, verrà visualizzato un rapporto sullo stato seguito da una conferma che il componente aggiuntivo è stato distribuito. Dopo aver letto le informazioni, fare clic su **Avanti**.

9. Nella pagina del **componente aggiuntivo annunciare** che viene visualizzata, esaminare le informazioni e quindi fare clic su **Chiudi**.

## <a name="learn-how-to-use-the-report-phishing-add-in"></a>Informazioni su come utilizzare il componente aggiuntivo per il phishing dei report

Gli utenti a cui è assegnato il componente aggiuntivo vedranno le icone seguenti:

- In Outlook l'icona è simile alla seguente:

  ![Icona del componente aggiuntivo per il phishing dei rapporti per Outlook](../../media/Outlook-ReportPhishing.png)

- In Outlook sul Web, l'icona è simile alla seguente:

  ![Icona del componente aggiuntivo di phishing del rapporto di Outlook sul Web](../../media/OWA-ReportPhishing.png)

## <a name="review-or-edit-settings-for-the-report-phishing-add-in"></a>Esaminare o modificare le impostazioni per il componente aggiuntivo di phishing dei report

1. Nell'interfaccia di amministrazione di Microsoft 365 passare alla pagina Vai alla pagina dei componenti aggiuntivi per le **Impostazioni** , \>  <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> se la pagina del **componente aggiuntivo** non è visualizzata, passare al collegamento **Impostazioni** \> componenti aggiuntivi delle **app integrate** \>  nella parte superiore della pagina delle **app integrate** .

2. Individuare e selezionare il componente aggiuntivo per il **phishing dei report** .

3. Nel riquadro a comparsa del **rapporto di modifica** che viene visualizzato, esaminare e modificare le impostazioni appropriate per l'organizzazione. Al termine, scegliere **Salva**.

## <a name="view-and-review-reported-messages"></a>Visualizzazione e revisione dei messaggi segnalati

Per esaminare i messaggi che gli utenti riferiscono a Microsoft, sono disponibili le seguenti opzioni:

- Utilizzare il portale degli invii di amministratore. Per ulteriori informazioni, vedere [visualizzare gli invii degli utenti a Microsoft](admin-submission.md#view-user-submissions-to-microsoft).

- Creare una regola del flusso di posta (nota anche come regola di trasporto) per inviare copie dei messaggi segnalati. Per istruzioni, vedere [utilizzo delle regole del flusso di posta per vedere cosa gli utenti stanno segnalando a Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md).