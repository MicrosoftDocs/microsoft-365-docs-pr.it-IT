---
title: Installare e utilizzare il componente aggiuntivo per la segnalazione della posta indesiderata per Microsoft Outlook
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 4650fec1-4ee3-4659-abbc-bf091718cb26
ms.collection:
- M365-security-compliance
description: Informazioni su come installare e utilizzare il componente aggiuntivo per la segnalazione della posta indesiderata di Microsoft per segnalare messaggi di posta indesiderata, non indesiderata e phishing a Microsoft.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e22a1364e8d7a1447bbcf518cc339a681c57a8af
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286622"
---
# <a name="install-and-use-the-junk-email-reporting-add-in-for-microsoft-outlook"></a>Installare e utilizzare il componente aggiuntivo per la segnalazione della posta indesiderata per Microsoft Outlook

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

> [!NOTE]
> Se attualmente non si utilizza il componente aggiuntivo per la [](enable-the-report-message-add-in.md) segnalazione della posta indesiderata, è consigliabile utilizzare il componente aggiuntivo Segnala messaggio o Segnala [phishing.](enable-the-report-phish-add-in.md) Per altre informazioni, vedere [Segnalazione di messaggi e file a Microsoft](report-junk-email-messages-to-microsoft.md).

Il componente aggiuntivo per la segnalazione della posta indesiderata per Microsoft Outlook consente agli utenti di inviare falsi positivi (buona posta elettronica contrassegnata come posta indesiderata), falsi negativi (posta elettronica non consentita) e messaggi di phishing a Microsoft. Se l'organizzazione non utilizza Exchange Online Protection (ad esempio, exchange locale o servizi di posta elettronica diversi da Exchange Online), l'invio del rapporto di posta indesiderata non influirà sul filtro della posta indesiderata.

In questo argomento viene illustrato come installare e utilizzare il componente aggiuntivo per la segnalazione della posta indesiderata.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare?

- Per installare il componente aggiuntivo per [](#install-the-junk-email-reporting-add-in) la segnalazione della posta indesiderata, vedere la sezione Installare il componente aggiuntivo per la segnalazione della posta indesiderata più avanti in questo articolo.

- Il componente aggiuntivo per la segnalazione della posta indesiderata funziona con le seguenti versioni di Outlook:

  - Outlook 2013 o versione successiva
  - Outlook incluso in Microsoft 365 Apps for enterprise

- Per ulteriori informazioni sulla segnalazione dei messaggi a Microsoft, vedere [Segnalare messaggi e file a Microsoft.](report-junk-email-messages-to-microsoft.md)

## <a name="use-the-junk-email-reporting-add-in-to-report-spam-and-phishing-messages"></a>Utilizzare il componente aggiuntivo per la segnalazione della posta indesiderata per segnalare messaggi di posta indesiderata e phishing

1. Per i messaggi nella Cartella Posta in arrivo o in qualsiasi altra cartella di posta elettronica ad eccezione della posta indesiderata, utilizzare uno dei metodi seguenti per segnalare messaggi di posta indesiderata e di phishing:

   - Selezionare il messaggio o aprirlo. Nella scheda Home **o** **Messaggio** della barra multifunzione  fare clic su Posta indesiderata **e** quindi selezionare Segnala come posta indesiderata o Segnala **come phishing.**

     ![Segnalare posta indesiderata o phishing dalla barra multifunzione](../../media/junk-email-reporting-ribbon.png)

   - Fare clic con il pulsante destro del  mouse sul messaggio, scegliere **Posta** indesiderata e quindi Segnala come posta indesiderata o Segnala **come phishing.**

     ![Segnalare posta indesiderata o phishing dal clic con il pulsante destro del mouse](../../media/junk-email-reporting-right-click.png)

   - Selezionare più messaggi, fare clic  con il pulsante destro del mouse e quindi scegliere Segnala come posta indesiderata **o Segnala come phishing.**

     ![Segnalare più messaggi di posta indesiderata o di phishing dal clic con il pulsante destro del mouse](../../media/junk-email-reporting-right-click-multiple.png)

2. Nella finestra di dialogo visualizzata leggere le informazioni e fare clic su **Report.** Se si cambia idea, fare clic **su Non segnalare.**

   ![Segnala come finestra di dialogo posta indesiderata](../../media/junk-email-reporting-report-as-junk-dialog.png)

   ![Finestra di dialogo Segnala come phishing](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. I messaggi selezionati verranno inviati a Microsoft per l'analisi e:

   - Spostato nella cartella Posta indesiderata se è stato segnalato come posta indesiderata.
   - Eliminato se è stato segnalato come phishing.

   Per verificare che i messaggi siano stati inviati, aprire la cartella **Posta inviata** per visualizzare i messaggi inviati.

## <a name="use-the-junk-email-reporting-add-in-to-report-non-spam-and-phishing-messages-from-the-junk-email-folder"></a>Utilizzare il componente aggiuntivo per la segnalazione della posta indesiderata per segnalare messaggi di posta non indesiderata e di phishing dalla cartella Posta indesiderata

1. Nella cartella Posta indesiderata, utilizzare uno dei metodi seguenti per segnalare falsi positivi o messaggi di phishing della posta indesiderata:

   - Selezionare il messaggio o aprirlo. Nella scheda **Home o** **Messaggio** della barra multifunzione fare clic su Non indesiderato **e** quindi selezionare Segnala come non indesiderato **o** Segnala come **phishing.**

     ![Segnalare messaggi di posta elettronica non indesiderati o di phishing dalla barra multifunzione nella cartella Posta indesiderata](../../media/junk-email-reporting-junk-folder-ribbon.png)

   - Fare clic con il pulsante destro del mouse sul messaggio, scegliere **Posta** indesiderata e selezionare Segnala come non indesiderato **o** **Segnala come phishing.**

     ![Segnalazione di messaggi di posta elettronica non indesiderati o di phishing da clic con il pulsante destro del mouse nella cartella Posta indesiderata](../../media/junk-email-reporting-junk-folder-right-click.png)

   - Selezionare più messaggi, fare clic con il pulsante destro del mouse e quindi scegliere Segnala come non indesiderato **o** Segnala **come phishing.**

     ![Segnalare più messaggi di posta elettronica non indesiderati o di phishing da clic con il pulsante destro del mouse nella cartella Posta indesiderata](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

2. Nella finestra di dialogo visualizzata leggere le informazioni e fare clic su **Report.** Se si cambia idea, fare clic **su Non segnalare.**

   ![Segnala come non indesiderato finestra di dialogo](../../media/junk-email-reporting-report-as-not-junk-dialog.png)

   ![Finestra di dialogo Segnala come phishing](../../media/junk-email-reporting-report-as-phishing-dialog.png)

3. I messaggi selezionati verranno inviati a Microsoft per l'analisi e:

   - Spostato nella cartella Posta indesiderata se è stato segnalato come posta indesiderata.
   - Eliminato se è stato segnalato come phishing.

   Per verificare che i messaggi siano stati inviati, aprire la cartella **Posta inviata** per visualizzare i messaggi inviati.

## <a name="install-the-junk-email-reporting-add-in"></a>Installare il componente aggiuntivo per la segnalazione della posta indesiderata

- È necessario disporre dei privilegi di amministratore nel computer in cui si sta installando il componente aggiuntivo.

- Passare a e scaricare il file MSI appropriato per la versione di Office in un <https://www.microsoft.com/download/details.aspx?id=18275> percorso facile da trovare:

  - **32 bit:**`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`
  - **64 bit:**`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`

- Per Outlook 2013 o versione successiva, l'unico prerequisito è Microsoft .NET Framework 2.0. In Windows 10 non installi .NET Framework 2.0 da un download.

### <a name="install-the-junk-email-reporting-add-in-using-the-setup-wizard"></a>Installare il componente aggiuntivo per la segnalazione della posta indesiderata tramite l'installazione guidata

1. Chiudere Outlook nel proprio computer.

2. In Windows 10 verifica che .NET Framework 2.0 sia abilitato. Per istruzioni, vedi [Abilitare .NET Framework 3.5 nel Pannello di controllo.](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10#enable-the-net-framework-35-in-control-panel)

3. Individuare il file MSI scaricato e fare doppio clic su di esso.

4. Nella pagina **Installazione del componente aggiuntivo per la segnalazione della posta indesiderata** fare clic su **Avanti**.

5. Rivedere il contratto di licenza, **fare** clic su Accetto i termini del Contratto di Licenza se si accettano le condizioni e quindi fare clic su **Avanti.**

6. Al termine della procedura guidata, fare clic su **Fine**.

Avviare Outlook.

Cerare il pulsante **Posta indesiderata** sulla barra multifunzione di Outlook. A questo punto sarà possibile segnalare i messaggi di posta indesiderata a Microsoft, selezionandoli nella Posta in arrivo e facendo clic sul pulsante **Segnala posta indesiderata**.

Scegliere la freccia in giù accanto a **Posta indesiderata** per visualizzare altre opzioni, ad esempio **Segnala come phishing** per segnalare tentativi di phishing a Microsoft. Nella cartella della posta indesiderata, è inoltre possibile selezionare **Segnala come attendibile** se un messaggio di posta elettronica è stato identificato erroneamente come posta indesiderata.

### <a name="install-the-junk-email-reporting-add-in-using-silent-mode"></a>Installazione del componente aggiuntivo di report di posta indesiderata in modalità invisibile

1. Chiudere Outlook nel proprio computer.

2. In Windows 10 installa .NET Framework 2.0 eseguendo il comando seguente:

   ```dos
   DISM /Online /Enable-Feature /FeatureName:NetFx3 /All
   ```

3. Per installare il componente aggiuntivo senza alcuna interazione dell'utente, aprire un prompt dei comandi e utilizzare la sintassi seguente:

   ```dos
   msiexec /qn /i "<PathToMSIFile>\<MSIFile>" [MaxMessageSelection=<1-50>] [BccEmailAddress="<EmailAddress1>; <EmailAddress2>"...]
   ```

   - `MaxMessageSelection` specifica il numero massimo di messaggi che è possibile selezionare per un singolo invio. I valori validi sono da 1 a 50. Il valore predefinito è 15.

   - `BccEmailAddress` specifica altri destinatari Ccn che riceveranno una copia di tutti gli invii di utenti. Il valore predefinito è vuoto (nessun destinatario Ccn aggiuntivo).

   In questo esempio viene installata la versione a 64 bit del componente aggiuntivo dal percorso specificato con le impostazioni predefinite.

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi"
   ```

   In questo esempio viene installata la versione a 32 bit del componente aggiuntivo dal percorso specificato con le impostazioni aggiuntive seguenti:

   - In un singolo invio è possibile selezionare fino a 20 messaggi.
   - junkreports@contoso.com e hollyd@treyresearch.net ricevere copie Ccn di tutti gli invii.

   ```dos
   msiexec /qn /i "C:\Downloads\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" MaxMessageSelection=20 BccEmailAddress="junkreports@contoso.com; hollyd@treyresearch.net"
   ```

### <a name="how-do-you-know-this-worked"></a>Come verificare se l'operazione ha avuto esito positivo

Per verificare la corretta installazione del componente aggiuntivo per la segnalazione della posta indesiderata, eseguire una delle operazioni seguenti in Outlook:

- Selezionare il messaggio o aprirlo. Nella scheda **Home** o **Messaggio** della barra multifunzione fare clic **su** Posta indesiderata e verificare che siano disponibili le opzioni seguenti:

  - **Segnala come posta indesiderata**
  - **Segnala come phishing**
  - **Opzioni di segnalazione della posta indesiderata**
  - **Segnalazione della Guida in linea per la posta indesiderata**

  ![Segnalare posta indesiderata o phishing dalla barra multifunzione](../../media/junk-email-reporting-ribbon.png)

- Fare clic con il pulsante destro del mouse sul messaggio, selezionare **Posta** indesiderata e verificare che siano disponibili le opzioni seguenti:

  - **Segnala come posta indesiderata**
  - **Segnala come phishing**
  - **Opzioni di segnalazione della posta indesiderata**
  - **Segnalazione della Guida in linea per la posta indesiderata**

  ![Segnalare posta indesiderata o phishing dal clic con il pulsante destro del mouse](../../media/junk-email-reporting-right-click.png)

- Selezionare più messaggi, fare clic con il pulsante destro del mouse e verificare che siano disponibili le opzioni seguenti:

  - **Segnala come posta indesiderata**
  - **Segnala come phishing**

  ![Segnalare più messaggi di posta indesiderata o di phishing dal clic con il pulsante destro del mouse](../../media/junk-email-reporting-right-click-multiple.png)

- Eseguire le azioni precedenti nella cartella **Posta** indesiderata e verificare che le **opzioni** di segnalazione della posta indesiderata precedenti siano ora Non **indesiderate.**

  ![Segnalare messaggi di posta elettronica non indesiderati o di phishing dalla barra multifunzione nella cartella Posta indesiderata](../../media/junk-email-reporting-junk-folder-ribbon.png)

  ![Segnalazione di messaggi di posta elettronica non indesiderati o di phishing da clic con il pulsante destro del mouse nella cartella Posta indesiderata](../../media/junk-email-reporting-junk-folder-right-click.png)

  ![Segnalare più messaggi di posta elettronica non indesiderati o di phishing da clic con il pulsante destro del mouse nella cartella Posta indesiderata](../../media/junk-email-reporting-junk-folder-right-click-multiple.png)

## <a name="uninstall-the-junk-email-reporting-add-in"></a>Disinstallazione del componente aggiuntivo per la segnalazione della posta indesiderata

Dopo aver chiuso Outlook, utilizzare una delle procedure seguenti per disinstallare il componente aggiuntivo per la segnalazione della posta indesiderata:

- **Pannello di** controllo: premere il tasto Windows + R. Nella finestra **di** dialogo Esegui visualizzata, immettere `control appwiz.cpl` e quindi fare clic su **OK.**

  Individuare e selezionare **il componente aggiuntivo per la segnalazione della** posta indesiderata di Microsoft nell'elenco e quindi fare clic su **Disinstalla.**

- **Pacchetto di Windows Installer:** trova o scarica il file MSI appropriato e fai doppio clic su di esso.

  - **32 bit:**`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi`

  - **64 bit:**`Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi`

  Nella finestra di dialogo visualizzata selezionare Rimuovi componente aggiuntivo per la segnalazione della posta indesiderata di **Microsoft per Outlook** e quindi fare clic su **Avanti.**

- **Modalità invisibile** all'utente: trova o scarica il file MSI appropriato. In una finestra del prompt dei comandi sostituire con il percorso del \<PathToFile\> file MSI ed eseguire uno dei comandi seguenti:

  - **32 bit:**

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (32-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

  - **64 bit:**

    ```dos
    msiexec /x "<PathToFile>\Junk Reporting Add-in for Office 2007, 2010, 2013, and 2016 (64-bit).msi" /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"
    ```

Quando si apre Outlook dopo la disinstallazione, le opzioni di segnalazione della posta indesiderata, non indesiderata e di phishing non dovrebbero più essere disponibili.

## <a name="troubleshooting-the-junk-email-reporting-add-in"></a>Risoluzione dei problemi del componente aggiuntivo per la segnalazione della posta indesiderata

In alcuni casi, potrebbero verificarsi problemi con Outlook dopo l'aggiunta del componente aggiuntivo per la segnalazione della posta indesiderata. In questa sezione vengono descritti i problemi che possono verificarsi, insieme ai suggerimenti per risolverli.

### <a name="troubleshooting-for-users"></a>Risoluzione dei problemi per gli utenti

Si verificano uno o più dei seguenti problemi:

- Non accade nulla quando si fa clic su **Segnala posta indesiderata**
- Outlook si blocca dopo la selezione di un messaggio di posta elettronica
- La posta indesiderata segnalata non viene recapitata perché "non recapitabile"

Per risolvere il problema, eseguire la procedura seguente:

1. Chiudere e riavviare Outlook.
2. Creare e inviare un messaggio di prova e verificare che il destinatario lo ha ricevuto.
3. Se il problema persiste, contattare l'amministratore.

Per altri metodi che è possibile utilizzare per inviare messaggi a Microsoft, vedere [Segnalare messaggi e file a Microsoft.](report-junk-email-messages-to-microsoft.md)

### <a name="troubleshooting-for-admins"></a>Risoluzione dei problemi per gli amministratori

#### <a name="problem-an-error-message-continually-appears-that-asks-users-to-contact-their-system-administrator"></a>Problema: viene visualizzato un messaggio di errore che chiede agli utenti di contattare l'amministratore di sistema

1. Verificare o impostare la chiave `LoggingLevel` del Registro di sistema sul valore "Verbose":

   - **Outlook a 32 bit in Windows a 32 bit:**

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk Email Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

   - **Outlook a 32 bit in Windows a 64 bit:**

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Wow6432Node\Microsoft\Junk Email Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

   - **Outlook a 64 bit:**

     ```text
     Windows Registry Editor Version 5.00

     [HKEY_LOCAL_MACHINE\Software\Microsoft\Junk E-mail Reporting\Addins]
     "LoggingLevel"="Verbose"
     ```

2. Riavviare Outlook e chiedere agli utenti di segnalare quando visualizzano il messaggio di errore.

3. Raccogliere i registri nei percorsi seguenti:

   `%LOCALAPPDATA%\Microsoft\Junk Email Reporting Add-in\SpamReporterAddinLog.txt`

4. Contattare il supporto tecnico di Exchange Online Protection per fornire i registri.

#### <a name="problem-users-selected-not-to-receive-a-confirmation-prompt-when-they-report-messages-and-now-they-want-the-prompt-back"></a>Problema: gli utenti hanno selezionato di non ricevere una richiesta di conferma quando segnalano i messaggi e ora desiderano che la richiesta venga visualizzata nuovamente

1. Creare la `ConfirmReportJunk` chiave del Registro di sistema con il valore "True":

   ```text
   Windows Registry Editor Version 5.00

   HKEY_CURRENT_USER\Software\Microsoft\Junk E-mail Reporting\Preferences]
   "ConfirmReportJunk"="True"
   ```

2. Riavviare Outlook.
