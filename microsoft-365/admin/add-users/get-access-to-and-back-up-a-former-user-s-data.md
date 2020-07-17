---
title: Accedere ai dati di un ex utente ed eseguirne il backup
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- SPO_Content
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: a6f7f9ad-e3f5-43de-ade5-e5a0d7531604
description: Informazioni su come conservare i file e i messaggi di posta elettronica di un dipendente quando la persona lascia l'organizzazione.
ms.openlocfilehash: 32f64efb30acb5438e5add8bcb897200951e6362
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780614"
---
# <a name="get-access-to-and-back-up-a-former-users-data"></a>Accedere ai dati di un ex utente ed eseguirne il backup


Quando un dipendente lascia l'organizzazione, è probabile che si desideri accedere ai propri dati (documenti e messaggi di posta elettronica) e rivederla, eseguirne il backup o darla a un nuovo dipendente.
  
    
## <a name="access-a-former-users-onedrive-documents"></a>Accedere ai documenti di OneDrive di un utente precedente

Se si rimuove la licenza di un utente, ma non si elimina l'account, è possibile accedere al contenuto del OneDrive dell'utente. Se si elimina l'account dell'utente, per impostazione predefinita sono presenti 30 giorni per accedere ai dati di OneDrive dell'utente precedente. [Informazioni su come impostare la conservazione di OneDrive per gli utenti eliminati](/onedrive/set-retention). Se non si [Ripristina un account utente](/office365/admin/add-users/restore-user) entro questo intervallo di tempo, viene eliminato il contenuto di OneDrive. 

Per conservare i file di OneDrive di un utente precedente, è necessario accedere al proprio OneDrive e quindi spostare i file che si desidera mantenere. 

::: moniker range="o365-worldwide"

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.  
    
2. Selezionare un utente.

3. Nel riquadro a destra, selezionare **OneDrive**. In **Accedi ai file**, selezionare **Crea collegamento ai file**.

4. Selezionare il collegamento per aprire il percorso del file. Scaricare i file nel computer in uso oppure selezionare **Sposta in** o **copia** in per spostarli o copiarli nel proprio OneDrive o in una raccolta condivisa. 

> [!NOTE]
> È possibile spostare o copiare fino a 500 MB di file e cartelle alla volta.<br/>
> Quando si spostano o si copiano documenti con cronologia delle versioni, viene spostata solo la versione più recente.  

::: moniker-end

::: moniker range="o365-germany"

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Utenti attivi</a>.  

2. Selezionare un utente.

3. Nel riquadro destro espandere Impostazioni di **OneDrive**e quindi fare **clic su Access** **file**.

4. Selezionare il collegamento per aprire il percorso del file. Scaricare i file nel computer in uso oppure selezionare **Sposta in** o **copia** in per spostarli o copiarli nel proprio OneDrive o in una raccolta condivisa. 

> [!NOTE]
> È possibile spostare o copiare fino a 500 MB di file e cartelle alla volta.<br/>
> Quando si spostano o si copiano documenti con cronologia delle versioni, viene spostata solo la versione più recente.  

::: moniker-end

::: moniker range="o365-21vianet"

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Utenti attivi</a>. 

2. Selezionare un utente.

3. Nel riquadro destro espandere Impostazioni di **OneDrive**e quindi fare **clic su Access** **file**.

4. Selezionare il collegamento per aprire il percorso del file. Scaricare i file nel computer in uso oppure selezionare **Sposta in** o **copia** in per spostarli o copiarli nel proprio OneDrive o in una raccolta condivisa.  

> [!NOTE]
> È possibile spostare o copiare fino a 500 MB di file e cartelle alla volta.<br/>
> Quando si spostano o si copiano documenti con cronologia delle versioni, viene spostata solo la versione più recente.  

::: moniker-end
    


## <a name="revoke-admin-access-to-a-users-onedrive"></a>Revocare l'accesso dell'amministratore all'OneDrive di un utente

In qualità di amministratore globale, è possibile accedere al contenuto del OneDrive di un utente, ma potrebbe essere opportuno rimuovere l'accesso quando non è più necessario. 

::: moniker range="o365-worldwide"

1. Accedere all'interfaccia di <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Amministrazione</a> come amministratore globale o amministratore di SharePoint. 

    Se viene visualizzato un messaggio che non dispone dell'autorizzazione necessaria per accedere all'interfaccia di amministrazione, non si dispone delle autorizzazioni di amministratore nell'organizzazione.

::: moniker-end

::: moniker range="o365-germany"

1. Accedere all'interfaccia di <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Amministrazione</a> come amministratore globale o amministratore di SharePoint.

    Se viene visualizzato un messaggio che non dispone dell'autorizzazione necessaria per accedere all'interfaccia di amministrazione, non si dispone delle autorizzazioni di amministratore nell'organizzazione.

::: moniker-end

::: moniker range="o365-21vianet"

1. Accedere all'interfaccia di <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Amministrazione</a> come amministratore globale o amministratore di SharePoint.

    Se viene visualizzato un messaggio che non dispone dell'autorizzazione necessaria per accedere all'interfaccia di amministrazione, non si dispone delle autorizzazioni di amministratore nell'organizzazione.

::: moniker-end

2. Nel riquadro sinistro, selezionare interfaccia di **Amministrazione** di \> **SharePoint**. Potrebbe essere necessario selezionare **Mostra tutto** per vedere l'elenco di interfacce di amministrazione.

3. Se viene visualizzato l'interfaccia di amministrazione di SharePoint classica, seleziona **Aprilo ora** nella parte superiore della pagina per aprire l'interfaccia di amministrazione di SharePoint.

4. Nel riquadro sinistro, selezionare **altre caratteristiche**.

5. In **profili utente**selezionare **Apri**.

6. In **utenti**selezionare **Gestisci profili utente**.

7. Immettere il nome dell'utente e selezionare **trova**.

8. Fare clic con il pulsante destro del mouse sull'utente, quindi scegliere **Gestisci proprietari raccolta siti**.

9. Rimuovere la persona che non ha più bisogno di accedere ai dati dell'utente e quindi selezionare **OK**.

    
## <a name="access-the-outlook-data-of-a-former-user"></a>Accedere ai dati di Outlook di un utente precedente

Per salvare i messaggi di posta elettronica, il calendario, le attività e i contatti dell'ex dipendente, è possibile esportare le informazioni in un file di dati di Outlook (con estensione pst).
  
1. [Aggiungere il messaggio di posta elettronica dell'ex dipendente](https://support.microsoft.com/office/6e27792a-9267-4aa4-8bb6-c84ef146101b) al proprio Outlook (se si [Reimposta la password dell'utente](reset-passwords.md), è possibile impostarla su una cosa che si conosce solo).
    
2. In Outlook selezionare **file**.
    
    ![Questo è l'aspetto della barra multifunzione in Outlook 2016.](../../media/d7f66ed3-9861-4521-b410-e86a58ab15a7.png)
  
3. Selezionare **Open &amp; Export** \> **Import/Export**.
    
    ![Comando Importa/esporta nella visualizzazione Backstage](../../media/6013919e-d8ce-4902-b7b4-78ff4260a2f8.jpg)
  
4. Selezionare **Esporta in un file**e quindi fare clic su **Avanti**.
    
    ![Opzione Esporta in un file nell'Importazione/Esportazione guidata](../../media/458466a0-366b-4fbf-a2db-1919412c6527.jpg)
  
5. Selezionare **file di dati di Outlook (con estensione pst)** e quindi fare clic su **Avanti**.
    
6. Selezionare l'account che si desidera esportare selezionando il nome o l'indirizzo di posta elettronica, ad esempio Mailbox-Anne Weiler o anne@contoso.com. Se si vuole esportare tutto il contenuto dell'account, inclusi i messaggi di posta elettronica, il calendario, i contatti, le attività e le note, verificare che sia selezionata la casella di controllo **Includi sottocartelle**. 
    
    > [!NOTE]
    > È possibile esportare un solo account alla volta. Se si desidera esportare più account, ripetere questi passaggi per ognuno di essi. 
  
    ![Finestra di dialogo Esporta file di dati di Outlook con la cartella principale e l'opzione Includi sottocartelle selezionate](../../media/ce36616f-d76d-4ce2-b517-8ac4874e0971.jpg)
  
7. Selezionare **Avanti**.
    
8. Selezionare **Sfoglia** per selezionare il percorso in cui salvare il file di dati di Outlook (con estensione pst). Digitare un *nome di file*e quindi fare clic su **OK** per continuare. 
    
    > [!NOTE]
    > Se l'esportazione è già stata usata, verranno visualizzati il nome del file e il percorso della cartella precedenti. Digitare un *nome di file diverso* prima di selezionare **OK**. 
  
9. Se si esegue l'esportazione in un File di dati di Outlook (.pst) esistente, in **Opzioni** specificare come procedere per l'esportazione di elementi già esistenti nel file.
    
10. Select **Finish**.
    
Outlook avvia immediatamente l'esportazione, a meno che non venga creato un nuovo File di dati di Outlook (pst) o non venga usato un file protetto da password.
  
   - Se si crea un nuovo File di dati di Outlook (pst), è possibile impostare una password facoltativa per proteggerlo. Quando viene visualizzata la finestra di dialogo **Crea file di dati di Outlook** , digitare *la password nelle* caselle **password** e **Verifica password** e quindi fare clic su **OK**. Nella finestra di dialogo **password file di dati di Outlook** Digitare la *password*e quindi fare clic su **OK**.
    
  - Se si esporta in un file di dati di Outlook (con estensione pst) esistente protetto da password, nella finestra di dialogo **password file di dati di Outlook** Digitare la *password*e quindi fare clic su **OK**.
    
Vedere come [esportare o eseguire il backup di posta elettronica, contatti e calendario in un file PST](https://support.microsoft.com/office/14252b52-3075-4e9b-be4e-ff9ef1068f91) di Outlook in Outlook 2010. 
  
  
  > [!NOTE]
  > Per impostazione predefinita, il messaggio di posta elettronica è disponibile offline per un periodo di 12 mesi. Se necessario, vedere How to [increase the data available offline](Https://docs.microsoft.com/outlook/troubleshoot/mailboxes/only-subset-items-synchronized).
 
## <a name="give-another-user-access-to-a-former-users-email"></a>Concedere a un altro utente l'accesso alla posta elettronica di un utente precedente 

Per concedere l'accesso ai messaggi di posta elettronica, al calendario, alle attività e ai contatti dell'ex dipendente a un altro dipendente, importare le informazioni nella cartella posta in arrivo di Outlook di un altro dipendente.

> [!NOTE]
> È inoltre possibile [convertire la cassetta postale dell'utente precedente in una cassetta postale condivisa](https://docs.microsoft.com/office365/admin/email/convert-user-mailbox-to-shared-mailbox) o [inoltrare la posta elettronica di un ex dipendente a un altro dipendente](https://docs.microsoft.com/office365/admin/add-users/remove-former-employee#forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox).

  
1. In Outlook, passare a **file** \> **Open &amp; Export** \> **Import/Export**.
    
    Viene avviata l'Importazione/Esportazione guidata.
    
2. Selezionare **Importa da un altro programma o file**e quindi fare clic su **Avanti**.
    
    ![Importazione/Esportazione guidata](../../media/15cdd674-cd7b-492c-8e93-992cfa890f26.jpg)
  
3. Selezionare **file di dati di Outlook (con estensione pst)** e quindi selezionare **Avanti**.
    
4. Passare al file PST che si vuole importare.
    
5. In **Opzioni** scegliere come si vuole gestire i duplicati.
    
6. Selezionare **Avanti**.
    
7. Se al file di dati di Outlook (con estensione pst) è stata assegnata una password, immettere la password e quindi fare clic su **OK**.
    
8. Impostare le opzioni per l'importazione degli elementi. Solitamente, non è necessario modificare le impostazioni predefinite.
    
9. Select **Finish**.

> [!NOTE]
> La procedura resta invariata per l'accesso ai dati di posta elettronica e di OneDrive di un utente esistente.
    
> [!TIP]
> Se si desidera importare o ripristinare solo alcuni elementi da un file di dati di Outlook (con estensione pst), è possibile aprire il file di dati di Outlook. Nel riquadro di spostamento, quindi, trascinare gli elementi dalle cartelle dei file di dati di Outlook alle cartelle di Outlook esistenti. 
  
  
## <a name="related-articles"></a>Articoli correlati
[Rimuovere un ex dipendente da Office 365](remove-former-employee.md)

[Aggiungere e rimuovere gli amministratori in un account di OneDrive](/sharepoint/manage-user-profiles#add-and-remove-admins-for-a-users-onedrive)

[Ripristinare un OneDrive eliminato](/onedrive/restore-deleted-onedrive)
  
[Conservazione ed eliminazione di OneDrive](/onedrive/retention-and-deletion)
  
