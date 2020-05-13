---
title: Messaggi di posta indesiderata e di phishing di RReport in Outlook sul Web
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
ms.assetid: 758822b5-0126-463a-9d08-7366bb2a807d
ms.collection:
- M365-security-compliance
description: Gli amministratori possono ottenere informazioni sulle opzioni di creazione di report di posta indesiderata, non di posta indesiderata e di phishing in Outlook sul Web (Outlook Web App) in Exchange Online, nonché su come disabilitare tali opzioni di creazione dei rapporti per gli utenti.
ms.openlocfilehash: 1ec226259ccb3dac9a01ee8d4c5fc635c0fc5702
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "44206479"
---
# <a name="report-junk-and-phishing-email-in-outlook-on-the-web-in-exchange-online"></a>Segnalare messaggi di posta indesiderata e di phishing in Outlook sul Web in Exchange Online

In Microsoft 365 organizzazioni con cassette postali in Exchange Online, è possibile utilizzare le opzioni predefinite per la creazione di report in Outlook sul Web (in precedenza noto come Outlook Web App) per inviare falsi positivi (buon messaggio di posta indesiderata), falsi negativi (posta elettronica non consentita) e messaggi di phishing a Exchange Online Protection (EOP).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare

- Se si è un amministratore di un'organizzazione con cassette postali di Exchange Online, è consigliabile utilizzare il portale degli invii nel centro sicurezza & Compliance. Per ulteriori informazioni, vedere [utilizzare l'invio di amministratore per inviare messaggi di posta indesiderata, phishing, URL e file a Microsoft](admin-submission.md).

- Gli amministratori possono disabilitare o abilitare la possibilità per gli utenti di segnalare i messaggi a Microsoft in Outlook sul Web. Per informazioni dettagliate, vedere la sezione [disabilitare o abilitare la creazione di report di posta indesiderata in Outlook sul Web](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) più avanti in questo argomento.

- È possibile configurare i messaggi segnalati in modo che vengano copiati o reindirizzati a una cassetta postale specificata. Per ulteriori informazioni, vedere [specificare una cassetta postale per l'invio di messaggi di posta indesiderata e di phishing in Exchange Online](user-submission.md).

- Per ulteriori informazioni sul reporting dei messaggi a Microsoft, vedere [segnalare i messaggi e i file a Microsoft](report-junk-email-messages-to-microsoft.md).

## <a name="report-spam-and-phishing-messages-in-outlook-on-the-web"></a>Segnalare messaggi di posta indesiderata e di phishing in Outlook sul Web

1. Per i messaggi nella cartella posta in arrivo o in altre cartelle di posta elettronica, ad eccezione della posta indesiderata, utilizzare uno dei metodi seguenti per segnalare messaggi di posta indesiderata

   - Selezionare il messaggio, fare clic su **posta indesiderata** sulla barra degli strumenti, quindi selezionare **posta indesiderata** o **phishing**.

     ![Segnalare messaggi di posta indesiderata o di phishing dalla barra multifunzione](../../media/owa-report-junk.png)

   - Selezionare uno o più messaggi, fare clic con il pulsante destro del mouse, quindi selezionare **Segna come posta indesiderata**.

2. Nella finestra di dialogo visualizzata fare clic su **segnala**. Se si cambia idea, fare clic su **non segnalare**.

   ![Segnala come finestra di dialogo indesiderata](../../media/owa-report-as-junk-dialog.png)

   ![Segnala come finestra di dialogo di phishing](../../media/owa-report-as-phishing-dialog.png)

3. I messaggi selezionati verranno inviati a Microsoft per l'analisi. Per verificare che i messaggi siano stati inviati, aprire la cartella **Posta inviata** per visualizzare i messaggi inviati.

## <a name="report-non-spam-and-phishing-messages-from-the-junk-email-folder-in-outlook-on-the-web"></a>Segnalare messaggi non di posta indesiderata e di phishing dalla cartella posta indesiderata in Outlook sul Web

1. Nella cartella posta indesiderata, utilizzare uno dei metodi seguenti per segnalare la posta indesiderata o i messaggi di phishing:

   - Selezionare il messaggio, fare clic su **non indesiderato** sulla barra degli strumenti, quindi selezionare **non indesiderato** o **phishing**.

     ![Segnalare messaggi di posta indesiderata o di phishing dalla barra multifunzione](../../media/owa-report-not-junk.png)

   - Selezionare uno o più messaggi, fare clic con il pulsante destro del mouse, quindi selezionare **Segna come non indesiderato**.

2. Nella finestra di dialogo che viene visualizzata, leggere le informazioni e fare clic su **segnala**. Se si cambia idea, fare clic su **non segnalare**.

   ![Segnala come finestra di dialogo non indesiderata](../../media/owa-report-as-not-junk-dialog.png)

   ![Segnala come finestra di dialogo di phishing](../../media/owa-report-as-phishing-dialog.png)

3. I messaggi selezionati verranno inviati a Microsoft per l'analisi. Per verificare che i messaggi siano stati inviati, aprire la cartella **Posta inviata** per visualizzare i messaggi inviati.

## <a name="disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a>Disabilitare o abilitare la segnalazione della posta indesiderata in Outlook sul Web

Per impostazione predefinita, gli utenti possono segnalare messaggi di posta indesiderata falsi positivi, falsi negativi e phishing a Microsoft per l'analisi in Outlook sul Web. Gli amministratori possono configurare i criteri cassetta postale di Outlook sul Web in Exchange Online PowerShell per impedire agli utenti di segnalare la posta indesiderata falsi positivi e falsi negativi di posta indesiderata a Microsoft. Non è possibile disabilitare la possibilità per gli utenti di segnalare i messaggi di phishing a Microsoft.

### <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare

- Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).

- È necessario disporre delle autorizzazioni prima di poter eseguire queste procedure. In particolare, è necessario che i **criteri destinatario** o i **destinatari di posta elettronica** in Exchange Online, assegnati ai gruppi di ruoli Gestione **organizzazione** **e destinatari** per impostazione predefinita. Per ulteriori informazioni sui gruppi di ruoli in Exchange Online, vedere [Modify role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups).

- Ogni organizzazione ha un criterio predefinito denominato OwaMailboxPolicy-Default, ma è possibile creare criteri personalizzati. I criteri personalizzati vengono applicati agli utenti con ambito prima del criterio predefinito. Per ulteriori informazioni sui criteri cassetta postale di Outlook sul Web, vedere [criteri cassetta postale di Outlook sul Web in Exchange Online](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies).

- La disattivazione della segnalazione della posta indesiderata non rimuove la possibilità di contrassegnare un messaggio come posta indesiderata o non indesiderata in Outlook sul Web. Selezionando un messaggio nella cartella posta indesiderata e facendo clic su **non** \> **indesiderata** , il messaggio viene spostato di nuovo nella posta in arrivo. Selezionando un messaggio in qualsiasi altra cartella di posta elettronica **e facendo clic su posta** indesiderata, \> **Junk** il messaggio viene spostato nella cartella posta indesiderata. Ciò che non è più disponibile è l'opzione per segnalare il messaggio a Microsoft.

### <a name="use-exchange-online-powershell-to-disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a>Utilizzo di PowerShell di Exchange Online per disabilitare o abilitare la segnalazione della posta indesiderata in Outlook sul Web

1. Per trovare i criteri cassetta postale di Outlook sul Web e lo stato della segnalazione della posta indesiderata, utilizzare il seguente comando:

   ```powershell
   Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
   ```

2. Per disabilitare o abilitare la segnalazione della posta indesiderata in Outlook sul Web, utilizzare la sintassi seguente:

   ```powershell
   Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
   ```

   In questo esempio viene disabilitata la segnalazione della posta indesiderata nel criterio predefinito.

   ```powershell
   Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
   ```

   In questo esempio viene abilitata la segnalazione della posta indesiderata nel criterio personalizzato denominato contoso managers.

   ```powershell
   Set-OwaMailboxPolicy -Identity "Contoso Managers" -ReportJunkEmailEnabled $true
   ```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Get-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/get-owamailboxpolicy) e [Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy).

### <a name="how-do-you-know-this-worked"></a>Come verificare se l'operazione ha avuto esito positivo

Per verificare la corretta abilitazione o disabilitazione della creazione di report di posta indesiderata in Outlook sul Web, eseguire una delle operazioni seguenti:

- In PowerShell di Exchange Online, eseguire il comando riportato di seguito e verificare il valore della proprietà **ReportJunkEmailEnabled** :

  ```powershell
  Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
  ```

- Aprire una cassetta postale di un utente in questione in Outlook sul Web, selezionare un messaggio nella posta in arrivo **, fare clic** su posta indesiderata e verificare che la \> **Junk** richiesta di segnalazione del messaggio a Microsoft sia o non sia visualizzata.<sup>\*</sup>

- Aprire una cassetta postale di un utente in questione in Outlook sul Web, selezionare un messaggio nella cartella posta indesiderata **, fare clic su posta** indesiderata \> **Junk** e verificare che la richiesta di segnalazione del messaggio a Microsoft sia o non sia visualizzata.<sup>\*</sup>

<sup>\*</sup>Gli utenti possono nascondere il prompt per segnalare il messaggio mentre segnalano il messaggio. Per controllare questa impostazione in Outlook sul Web:

1. Fare clic su **Impostazioni** ![ di Outlook sull'icona Impostazioni Web ](../../media/owa-settings-icon.png) \> **Visualizza tutte le impostazioni** di \> **posta indesiderata**di Outlook.
2. Nella sezione **report** verificare il valore: Chiedi a **me prima di inviare un rapporto**.

   ![Impostazioni di segnalazione della posta indesiderata di Outlook sul Web](../../media/owa-junk-email-reporting-options.png)
