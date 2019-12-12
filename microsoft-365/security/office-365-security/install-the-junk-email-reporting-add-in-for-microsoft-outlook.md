---
title: Installazione del componente aggiuntivo di report di posta indesiderata per Microsoft Outlook
ms.author: MSFTTracyP
author: tracyp
manager: dansimp
ms.date: 12/9/2016
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 8dcc752f-e22e-44ce-a104-4cc4d7e439f3
ms.collection:
- M365-security-compliance
description: In questa articleSupported LanguagesInstall la segnalazione della posta indesiderata Add-inuninstall the junk email Reporting Add-inFor more information
ms.openlocfilehash: 14c3914601ab8a6b3273b56a3915df9c909fc06c
ms.sourcegitcommit: 5710ce729c55d95b8b452d99ffb7ea92b5cb254a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2019
ms.locfileid: "39970392"
---
# <a name="install-the-junk-email-reporting-add-in-for-microsoft-outlook"></a>Installazione del componente aggiuntivo di report di posta indesiderata per Microsoft Outlook

In questo argomento viene descritto come installare e disinstallare il componente aggiuntivo di report di posta indesiderata per Outlook nei computer client dell'organizzazione. La versione corrente del componente aggiuntivo (gennaio 2016) include il supporto per Outlook 2016, Outlook 2013 e Outlook 2010.

Il componente aggiuntivo (per tutte le lingue supportate) consente di segnalare la posta elettronica indesiderata direttamente dalla barra multifunzione di Outlook. La versione inglese del componente aggiuntivo include altre opzioni per segnalare i problemi di posta elettronica a Microsoft, direttamente dalla barra multifunzione:

- Segnalazione dei messaggi di posta elettronica ricevuti che rappresentano tentativi di phishing

- Segnalazione di messaggi di posta elettronica identificati erroneamente come posta indesiderata.

## <a name="supported-languages"></a>Lingue supportate
<a name="sectionSection0"> </a>

Il componente aggiuntivo per la segnalazione della posta indesiderata supporta le lingue seguenti:

- Cinese semplificato

- Cinese tradizionale

- Olandese

- Inglese

- Francese

- Tedesco

- Italiano

- Giapponese

- Coreano

- Portoghese

- Portoghese (Brasile)

- Spagnolo

## <a name="install-the-junk-email-reporting-add-in"></a>Installazione del componente aggiuntivo per la segnalazione della posta indesiderata

È possibile installare il componente aggiuntivo di report di posta indesiderata:

- Tramite l'esecuzione del pacchetto di Windows Installer come per qualsiasi altro file .msi. Durante l'installazione del componente aggiuntivo, un'interfaccia GUI consente di aprire i prompt nelle schermate di installazione. Per ulteriori informazioni, vedere [Installazione del componente aggiuntivo di report di posta indesiderata tramite l'Installazione guidata](#install-the-junk-email-reporting-add-in-using-the-setup-wizard).

O

- Tramite l'esecuzione di un'installazione invisibile che elimina l'interfaccia utente dell'installazione, consentendo di specificare le opzioni della riga di comando che eseguono uno script di installazione. Durante l'installazione del componente aggiuntivo, sono disponibili ulteriori opzioni di configurazione che non sono presenti nell'interfaccia GUI. Per ulteriori informazioni, vedere [Installazione del componente aggiuntivo di report di posta indesiderata in modalità invisibile](#install-the-junk-email-reporting-add-in-using-silent-mode).

### <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare

- Vedere i **requisiti di sistema** per il componente aggiuntivo per la segnalazione della [https://www.microsoft.com/download/details.aspx?id=18275](https://www.microsoft.com/download/details.aspx?id=18275)posta indesiderata all'indirizzo.

> [!NOTE]
> È necessario disporre dei privilegi di amministratore del computer su cui si installa il componente aggiuntivo.

### <a name="install-the-junk-email-reporting-add-in-using-the-setup-wizard"></a>Installazione del componente aggiuntivo per la segnalazione della posta indesiderata tramite l'installazione guidata

1. Chiudere Outlook nel proprio computer.

2. Nella sezione **Dettagli** del [componente aggiuntivo per la segnalazione della posta indesiderata per Microsoft Outlook](https://www.microsoft.com/download/details.aspx?id=18275), scaricare il file. msi appropriato per la versione di Office in uso.

3. Fare doppio clic sul file .msi.

4. Nella pagina **Installazione del componente aggiuntivo per la segnalazione della posta indesiderata** fare clic su **Avanti**.

5. Leggere il contratto di licenza, quindi fare clic su **Accetto i termini del contratto di licenza** se si accettano i termini dell'installazione (opzione necessaria per continuare l'installazione). Fare clic su **Avanti** per continuare.

6. Al termine della procedura guidata, fare clic su **Fine**.

7. Avviare Outlook.

8. Cerare il pulsante **Posta indesiderata** sulla barra multifunzione di Outlook. A questo punto sarà possibile segnalare i messaggi di posta indesiderata a Microsoft, selezionandoli nella Posta in arrivo e facendo clic sul pulsante **Segnala posta indesiderata**.

9. Scegliere la freccia in giù accanto a **Posta indesiderata** per visualizzare altre opzioni, ad esempio **Segnala come phishing** per segnalare tentativi di phishing a Microsoft. Nella cartella della posta indesiderata, è inoltre possibile selezionare **Segnala come attendibile** se un messaggio di posta elettronica è stato identificato erroneamente come posta indesiderata.

### <a name="install-the-junk-email-reporting-add-in-using-silent-mode"></a>Installazione del componente aggiuntivo di report di posta indesiderata in modalità invisibile

1. Chiudere Outlook nel proprio computer.

2. Aprire la finestra del prompt dei comandi.

3. Per eseguire l'installazione del componente aggiuntivo in modo semplice, senza parametri opzionali, specificare quanto segue:

   - Computer che eseguono Outlook x86:`msiexec /qn /i JunkReportingAdd-in.x86-en.msi`

   - Computer in esecuzione sulla piattaforma x64 Outlook:  `msiexec /qn /i JunkReportingAdd-in.x64-en.msi`

    È inoltre possibile specificare i parametri opzionali MaxMessageSelection e BccEmailAddress:

   - MaxMessageSelection Consente agli amministratori di stabilire il numero massimo dei messaggi che possono essere selezionati dagli utenti per l'invio con un solo clic. L'intervallo previsto è compreso tra 1 e 50 messaggi e il valore predefinito è 10.

     Esempio: Per impostare il numero massimo di messaggi che possono essere selezionati dagli utenti per l'invio con un solo clic su 16, utilizzare l'opzione seguente come parte del comando di installazione:  `MaxMessageSelection=16`

   - BccEmailAddress Consente agli amministratori di impostare una cassetta postale per ricevere una copia di tutti gli invii dell'utente, impostando un indirizzo di posta elettronica Ccn. Una volta impostata la cassetta postale, verrà inviata una copia di tutti i messaggi di posta elettronica inviati a BccEmailAddress. In caso contrario, l'impostazione predefinita prevede che non sia impostato alcun indirizzo di posta elettronica Ccn.

     Esempio: Per utilizzare junkReports@contoso.com come indirizzo di posta elettronica Ccn per tutti gli invii, utilizzare il comando seguente:  `BccEmailAddress="junkReports@contoso.com"`

     > [!NOTE]
     > È possibile impostare più indirizzi di posta elettronica Ccn, inserendoli separati da punto e virgola. Esempio:  `BccEmailAddress="junkReports@contoso.com; hollyd@treyresearch.net"`

     Per aggiungere entrambi i parametri facoltativi in base agli esempi precedenti, è necessario eseguire il comando riportato di seguito in un computer che esegue x86 Outlook:

     ```
     msiexec /qn /i JunkReportingAdd-in.x86-en.msi. MaxMessageSelection=16 BccEmailAddress="junkReports@contoso.com; hollyd@treyresearch.net"
     ```

4. Al termine dell'installazione, avviare Outlook.

5. Cerare il pulsante **Posta indesiderata** sulla barra multifunzione di Outlook. A questo punto sarà possibile segnalare i messaggi di posta indesiderata a Microsoft, selezionandoli nella Posta in arrivo e facendo clic sul pulsante **Segnala posta indesiderata**.

6. Scegliere la freccia in giù accanto a **Posta indesiderata** per visualizzare altre opzioni, ad esempio **Segnala come phishing** per segnalare tentativi di phishing a Microsoft. Nella cartella della posta indesiderata, è inoltre possibile selezionare **Segnala come attendibile** se un messaggio di posta elettronica è stato identificato erroneamente come posta indesiderata.

## <a name="uninstall-the-junk-email-reporting-add-in"></a>Disinstallazione del componente aggiuntivo per la segnalazione della posta indesiderata

Utilizzare una delle opzioni descritte in questa opzione per disinstallare il componente aggiuntivo per la segnalazione della posta indesiderata:

- Rimuovendo il componente aggiuntivo mediante il Pannello di controllo di Windows.

- Eseguire il pacchetto di Windows Installer e selezionare l'opzione di disinstallazione.

- Eseguendo un'installazione invisibile mediante l'opzione di disinstallazione.

> [!NOTE]
> È necessario disporre dei privilegi di amministratore del computer su cui si disinstalla il componente aggiuntivo.

### <a name="uninstall-the-junk-email-reporting-add-in-from-control-panel"></a>Disinstallazione del componente aggiuntivo per la segnalazione della posta indesiderata dal Pannello di controllo

1. Chiudere Outlook nel proprio computer.

2. Dal menu Start del computer, selezionare **Pannello di controllo**.

3. Selezionare **Programmi e funzionalità**.

4. Selezionare **Componente aggiuntivo per la segnalazione della posta indesiderata per Microsoft Office Outlook**.

5. Selezionare **Disinstalla**.

6. Avviare nuovamente Outlook per verificare che il componente aggiuntivo non sia più presente nella barra multifunzione di Outlook.

### <a name="uninstall-the-junk-email-reporting-add-in-by-running-the-windows-installer-package"></a>Disinstallazione del componente aggiuntivo per la segnalazione della posta indesiderata eseguendo il pacchetto di Windows Installer

1. Chiudere Outlook nel proprio computer.

   > [!NOTE]
   > Se Outlook è in esecuzione durante il processo di disinstallazione, sarà necessario riavviarlo per completare la disinstallazione del componente aggiuntivo.

2. Eseguire nuovamente il file .msi precedentemente eseguito per installare il componente aggiuntivo.

   Nella sezione **Dettagli** del [componente aggiuntivo per la segnalazione della posta indesiderata per Microsoft Outlook](https://www.microsoft.com/download/details.aspx?id=18275), scaricare il file con estensione msi appropriato per la versione di Office e quindi fare doppio clic sul file con estensione msi.

3. Per disinstallare il componente aggiuntivo, seguire le istruzioni visualizzate.

4. Avviare nuovamente Outlook per verificare che il componente aggiuntivo non sia più presente nella barra multifunzione di Outlook.

### <a name="uninstall-the-junk-email-reporting-add-in-in-silent-mode"></a>Disinstallazione del componente aggiuntivo per la segnalazione della posta indesiderata in modalità invisibile

1. Chiudere Outlook nel proprio computer.

   > [!NOTE]
   > Se Outlook è in esecuzione durante il processo di disinstallazione, sarà necessario riavviarlo per completare la disinstallazione del componente aggiuntivo.

2. Aprire una finestra con il prompt dei comandi.

3. Specificare il seguente parametro della riga di comando:

   Outlook x86:`msiexec /x JunkReportingAdd-in.x86-en.msi /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"`

   Outlook x64:`msiexec /x JunkReportingAdd-in.x64-en.msi /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"`

4. Avviare nuovamente Outlook per verificare che il componente aggiuntivo non sia più presente nella barra multifunzione di Outlook.

## <a name="for-more-information"></a>Ulteriori informazioni

[Segnalazione di messaggi indesiderati a Microsoft](report-junk-email-messages-to-microsoft.md)

[Supporto tecnico e risoluzione dei problemi](troubleshooting-and-support-information.md)
