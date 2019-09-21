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
ms.openlocfilehash: 7f294ed78affba6e55f2372b81b517bbd25d3f08
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37083435"
---
# <a name="install-the-junk-email-reporting-add-in-for-microsoft-outlook"></a>Installazione del componente aggiuntivo di report di posta indesiderata per Microsoft Outlook
  
In questo argomento viene descritto come installare e disinstallare il componente aggiuntivo di report di posta indesiderata per Outlook nei computer client dell'organizzazione. La versione corrente del componente aggiuntivo (gennaio 2016) include il supporto per Outlook 2016, Outlook 2013, Outlook 2010 e Outlook 2007. 
  
Il componente aggiuntivo (per tutte le lingue supportate) consente di segnalare la posta elettronica indesiderata direttamente dalla barra multifunzione di Outlook. La versione inglese del componente aggiuntivo include altre opzioni per segnalare i problemi di posta elettronica a Microsoft, direttamente dalla barra multifunzione:
  
-  Segnalazione dei messaggi di posta elettronica ricevuti che rappresentano tentativi di phishing 
    
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
<a name="sectionSection1"> </a>

È possibile installare il componente aggiuntivo di report di posta indesiderata:
  
- Tramite l'esecuzione del pacchetto di Windows Installer come per qualsiasi altro file .msi. Durante l'installazione del componente aggiuntivo, un'interfaccia GUI consente di aprire i prompt nelle schermate di installazione. Per ulteriori informazioni, vedere [Installazione del componente aggiuntivo di report di posta indesiderata tramite l'Installazione guidata](install-the-junk-email-reporting-add-in-for-microsoft-outlook.md#BKMK_InstalltheJunkEmailReportingAdd-InUsingtheSetupWizard). O
    
- Tramite l'esecuzione di un'installazione invisibile che elimina l'interfaccia utente dell'installazione, consentendo di specificare le opzioni della riga di comando che eseguono uno script di installazione. Durante l'installazione del componente aggiuntivo, sono disponibili ulteriori opzioni di configurazione che non sono presenti nell'interfaccia GUI. Per ulteriori informazioni, vedere [Installazione del componente aggiuntivo di report di posta indesiderata in modalità invisibile](install-the-junk-email-reporting-add-in-for-microsoft-outlook.md#BKMK_InstalltheJunkEmailReportingAdd-IninSilentMode).
    
### <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare

L'installazione del componente aggiuntivo di report di posta indesiderata per Microsoft Outlook richiede:
  
- Uno dei seguenti sistemi operativi: Windows 10, Windows 8.1, Windows 8, Windows 7 Service Pack 1, Windows 10 Server, Windows Server 2012 R2, Windows Server 2012 o Windows Server 2008 R2
    
- Outlook 2016, Outlook 2013, Outlook 2010 o Outlook 2007 (Service Pack 2 o versione successiva)
    
- Assembly di interoperabilità primari di Microsoft Office: 
    
  - Per il download degli assembly di interoperabilità primari per Microsoft Office 2010 o versioni successive, accedere a [Microsoft Download Center](https://go.microsoft.com/fwlink/?LinkID=166026).
    
  - Per il download degli assembly di interoperabilità primari per Microsoft Office 2007, accedere all'[Area download Microsoft](https://go.microsoft.com/fwlink/?LinkId=72637).
    
- Microsoft .NET Framework [Version 2.0](https://go.microsoft.com/fwlink/?LinkID=208706).
    
> [!NOTE]
> È necessario disporre dei privilegi di amministratore del computer su cui si installa il componente aggiuntivo. 
  
### <a name="install-the-junk-email-reporting-add-in-using-the-setup-wizard"></a>Installazione del componente aggiuntivo di report di posta indesiderata tramite l'Installazione guidata
<a name="BKMK_InstalltheJunkEmailReportingAdd-InUsingtheSetupWizard"> </a>

1. Chiudere Outlook nel proprio computer.
    
2. Accedere alla pagina Area download Microsoft per trovare il componente aggiuntivo per la segnalazione della posta indesiderata per Microsoft Outlook [https://go.microsoft.com/fwlink/?LinkID=147248](https://go.microsoft.com/fwlink/?LinkID=147248) e scaricare il file .msi. 
    
3. Fare doppio clic sul file .msi. 
    
4. Nella pagina **Installazione del componente aggiuntivo per la segnalazione della posta indesiderata** fare clic su **Avanti**. 
    
5. Leggere il contratto di licenza, quindi fare clic su **Accetto i termini del contratto di licenza** se si accettano i termini dell'installazione (opzione necessaria per continuare l'installazione). Fare clic su **Avanti** per continuare. 
    
6. Al termine della procedura guidata, fare clic su **Fine**. 
    
7. Avviare Outlook.
    
8. Cerare il pulsante **Posta indesiderata** sulla barra multifunzione di Outlook. A questo punto sarà possibile segnalare i messaggi di posta indesiderata a Microsoft, selezionandoli nella Posta in arrivo e facendo clic sul pulsante **Segnala posta indesiderata**. 
    
9. Scegliere la freccia in giù accanto a **Posta indesiderata** per visualizzare altre opzioni, ad esempio **Segnala come phishing** per segnalare tentativi di phishing a Microsoft. Nella cartella della posta indesiderata, è inoltre possibile selezionare **Segnala come attendibile** se un messaggio di posta elettronica è stato identificato erroneamente come posta indesiderata. 
    
### <a name="install-the-junk-email-reporting-add-in-using-silent-mode"></a>Installazione del componente aggiuntivo di report di posta indesiderata in modalità invisibile
<a name="BKMK_InstalltheJunkEmailReportingAdd-IninSilentMode"> </a>

1. Chiudere Outlook nel proprio computer.
    
2. Aprire la finestra del prompt dei comandi.
    
3. Per eseguire l'installazione del componente aggiuntivo in modo semplice, senza parametri opzionali, specificare quanto segue:
    
  - Computer in esecuzione sulla piattaforma x86 Outlook:  `msiexec /qn /i JunkReportingAdd-in.x86-en.msi`
    
  - Computer in esecuzione sulla piattaforma x64 Outlook:  `msiexec /qn /i JunkReportingAdd-in.x64-en.msi`
    
    È inoltre possibile specificare i parametri opzionali MaxMessageSelection e BccEmailAddress:
    
  - MaxMessageSelection Consente agli amministratori di stabilire il numero massimo dei messaggi che possono essere selezionati dagli utenti per l'invio con un solo clic. L'intervallo previsto è compreso tra 1 e 50 messaggi e il valore predefinito è 10.
    
    Esempio: Per impostare il numero massimo di messaggi che possono essere selezionati dagli utenti per l'invio con un solo clic su 16, utilizzare l'opzione seguente come parte del comando di installazione:  `MaxMessageSelection=16`
    
  - BccEmailAddress Consente agli amministratori di impostare una cassetta postale per ricevere una copia di tutti gli invii dell'utente, impostando un indirizzo di posta elettronica Ccn. Una volta impostata la cassetta postale, verrà inviata una copia di tutti i messaggi di posta elettronica inviati a BccEmailAddress. In caso contrario, l'impostazione predefinita prevede che non sia impostato alcun indirizzo di posta elettronica Ccn.
    
    Esempio: Per utilizzare junkReports@contoso.com come indirizzo di posta elettronica Ccn per tutti gli invii, utilizzare il comando seguente:  `BccEmailAddress="junkReports@contoso.com"`
    
    > [!NOTE]
    > È possibile impostare più indirizzi di posta elettronica Ccn, inserendoli separati da punto e virgola. Esempio:  `BccEmailAddress="junkReports@contoso.com; hollyd@treyresearch.net"`
  
    Per aggiungere entrambi questi parametri opzionali in base agli esempi riportati, specificare quanto segue per un computer in esecuzione sulla piattaforma x86 Outlook: 
    
  ```
  msiexec /qn /i JunkReportingAdd-in.x86-en.msi. MaxMessageSelection=16 BccEmailAddress="junkReports@contoso.com; hollyd@treyresearch.net"
  ```

4. Al termine dell'installazione, avviare Outlook.
    
5. Cerare il pulsante **Posta indesiderata** sulla barra multifunzione di Outlook. A questo punto sarà possibile segnalare i messaggi di posta indesiderata a Microsoft, selezionandoli nella Posta in arrivo e facendo clic sul pulsante **Segnala posta indesiderata**. 
    
6. Scegliere la freccia in giù accanto a **Posta indesiderata** per visualizzare altre opzioni, ad esempio **Segnala come phishing** per segnalare tentativi di phishing a Microsoft. Nella cartella della posta indesiderata, è inoltre possibile selezionare **Segnala come attendibile** se un messaggio di posta elettronica è stato identificato erroneamente come posta indesiderata. 
    
## <a name="uninstall-the-junk-email-reporting-add-in"></a>Disinstallazione del componente aggiuntivo per la segnalazione della posta indesiderata
<a name="sectionSection2"> </a>

È possibile disinstallare il componente aggiuntivo di report di posta indesiderata seguendo uno dei metodi riportati di seguito:
  
- Rimuovendo il componente aggiuntivo mediante il Pannello di controllo di Windows. Per ulteriori informazioni, vedere [Disinstallazione del componente aggiuntivo per la segnalazione della posta indesiderata dal Pannello di controllo](install-the-junk-email-reporting-add-in-for-microsoft-outlook.md#BKMK_UninstalltheJunkEmailReportingAdd-infromControlPanel). O
    
- Eseguendo il pacchetto di Windows Installer e selezionando l'opzione di disinstallazione. Per ulteriori informazioni, vedere [Disinstallazione del componente aggiuntivo per la segnalazione della posta indesiderata eseguendo il pacchetto di Windows Installer](install-the-junk-email-reporting-add-in-for-microsoft-outlook.md#BKMK_UninstalltheJunkEmailReportingAddinbyRunningtheWindowsInstallerPackage). O
    
- Eseguendo un'installazione invisibile mediante l'opzione di disinstallazione. Per ulteriori informazioni, vedere [Disinstallazione del componente aggiuntivo per la segnalazione della posta indesiderata in modalità invisibile](install-the-junk-email-reporting-add-in-for-microsoft-outlook.md#MK_UninstalltheJunkEmailReportingAdd-ininSilentMode).
    
> [!NOTE]
> È necessario disporre dei privilegi di amministratore del computer su cui si disinstalla il componente aggiuntivo. 
  
### <a name="uninstall-the-junk-email-reporting-add-in-from-control-panel"></a>Disinstallazione del componente aggiuntivo per la segnalazione della posta indesiderata dal Pannello di controllo
<a name="BKMK_UninstalltheJunkEmailReportingAdd-infromControlPanel"> </a>

1. Chiudere Outlook nel proprio computer.
    
2. Dal menu Start del computer, selezionare **Pannello di controllo**.
    
3. Selezionare **Programmi e funzionalità**.
    
4. Selezionare **Componente aggiuntivo per la segnalazione della posta indesiderata per Microsoft Office Outlook**.
    
5. Selezionare **Disinstalla**.
    
6. Avviare nuovamente Outlook per verificare che il componente aggiuntivo non sia più presente nella barra multifunzione di Outlook.
    
### <a name="uninstall-the-junk-email-reporting-add-in-by-running-the-windows-installer-package"></a>Disinstallazione del componente aggiuntivo per la segnalazione della posta indesiderata eseguendo il pacchetto di Windows Installer
<a name="BKMK_UninstalltheJunkEmailReportingAddinbyRunningtheWindowsInstallerPackage"> </a>

1. Chiudere Outlook nel proprio computer.
    
    > [!NOTE]
    > Se Outlook è in esecuzione durante il processo di disinstallazione, sarà necessario riavviarlo per completare la disinstallazione del componente aggiuntivo. 
  
2. Eseguire nuovamente il file .msi precedentemente eseguito per installare il componente aggiuntivo. 
    
    Accedere alla pagina Area download Microsoft per trovare il componente aggiuntivo per la segnalazione della posta indesiderata per Microsoft Outlook [https://go.microsoft.com/fwlink/?LinkId=147248](https://go.microsoft.com/fwlink/?LinkId=147248), scaricare il file .msi, quindi fare doppio clic sul file .msi. 
    
3. Per disinstallare il componente aggiuntivo, seguire le istruzioni visualizzate.
    
4. Avviare nuovamente Outlook per verificare che il componente aggiuntivo non sia più presente nella barra multifunzione di Outlook.
    
### <a name="uninstall-the-junk-email-reporting-add-in-in-silent-mode"></a>Disinstallazione del componente aggiuntivo per la segnalazione della posta indesiderata in modalità invisibile
<a name="MK_UninstalltheJunkEmailReportingAdd-ininSilentMode"> </a>

1. Chiudere Outlook nel proprio computer.
    
    > [!NOTE]
    > Se Outlook è in esecuzione durante il processo di disinstallazione, sarà necessario riavviarlo per completare la disinstallazione del componente aggiuntivo. 
  
2. Aprire una finestra con il prompt dei comandi.
    
3. Specificare il seguente parametro della riga di comando:
    
    Computer in esecuzione sulla piattaforma x86 Outlook:  `msiexec /x JunkReportingAdd-in.x86-en.msi /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"`
    
    Computer in esecuzione sulla piattaforma x64 Outlook:  `msiexec /x JunkReportingAdd-in.x64-en.msi /qn MSIRESTARTMANAGERCONTROL="DisableShutdown"`
    
4. Avviare nuovamente Outlook per verificare che il componente aggiuntivo non sia più presente nella barra multifunzione di Outlook.
    
## <a name="for-more-information"></a>Ulteriori informazioni
<a name="sectionSection3"> </a>

[Segnalazione di messaggi indesiderati a Microsoft](report-junk-email-messages-to-microsoft.md)
  
[Supporto tecnico e risoluzione dei problemi](troubleshooting-and-support-information.md)
  

