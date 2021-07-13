---
title: Passaggio 4 - Concedere a un altro dipendente l'accesso OneDrive e Outlook dati
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
description: Seguire i passaggi descritti in questo articolo per concedere a un altro dipendente l'accesso ai dati OneDrive e Outlook dell'ex dipendente.
ms.openlocfilehash: b5868ab1622fea68cc3dabb54a3d06208ccaa165
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/12/2021
ms.locfileid: "53394304"
---
# <a name="step-4---give-another-employee-access-to-onedrive-and-outlook-data"></a>Passaggio 4 - Concedere a un altro dipendente l'accesso OneDrive e Outlook dati

Quando un dipendente lascia l'organizzazione, è necessario accedere ai dati OneDrive e Outlook, eseguire il backup e scegliere se assegnarlo a un altro dipendente.
  
## <a name="access-a-former-users-onedrive-documents"></a>Accedere ai documenti di un OneDrive precedente

Se si rimuove la licenza di un utente ma non si elimina l'account, è possibile concedere a se stessi l'accesso al contenuto nel OneDrive. Se elimini l'account dell'utente, per impostazione predefinita hai 30 giorni per accedere ai dati OneDrive'utente precedente. [Informazioni su come impostare la conservazione OneDrive per gli utenti eliminati.](/onedrive/set-retention) Se non si ripristina [un account utente entro](/office365/admin/add-users/restore-user) questo periodo di tempo, il relativo OneDrive viene eliminato.

Per conservare i file di OneDrive di un utente precedente, concedere innanzitutto l'accesso al OneDrive e quindi spostare i file che si desidera mantenere.

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.  

2. Selezionare un utente.

3. Nel riquadro destro selezionare **OneDrive**. In **Ottieni accesso ai file** seleziona Crea collegamento ai **file**.

4. Selezionare il collegamento per aprire il percorso del file. Scaricare i file nel computer oppure  selezionare Sposta **in** o Copia in per spostarli o copiarli nel proprio OneDrive o in una raccolta condivisa.

> [!NOTE]
> È possibile spostare o copiare fino a 500 MB di file e cartelle alla volta.<br/>
> Quando si spostano o copiano documenti con cronologia delle versioni, viene spostata solo la versione più recente.  

È inoltre possibile concedere l'accesso a un altro utente per accedere alla OneDrive di un ex dipendente.

1. Accedi <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">all'interfaccia di amministrazione</a> come amministratore globale o amministratore SharePoint amministratore.

    Se viene visualizzato un messaggio che indica che non si dispone dell'autorizzazione per accedere all'interfaccia di amministrazione, non si dispone delle autorizzazioni di amministratore nell'organizzazione.

2. Nel riquadro sinistro selezionare **Interfaccia di amministrazione** \> **SharePoint**. Potrebbe essere necessario selezionare **Mostra tutto** per vedere l'elenco di interfacce di amministrazione.

3. Se viene visualizzata SharePoint'interfaccia di  amministrazione classica, selezionare Apri ora nella parte superiore della pagina per aprire l'SharePoint di amministrazione.

4. Nel riquadro sinistro selezionare **Altre funzionalità.**

5. In **Profili utente** selezionare **Apri.**

6. In **Utenti** selezionare **Gestisci profili utente.**

7. Immettere il nome dell'ex dipendente e selezionare **Trova**.

8. Fare clic con il pulsante destro del mouse sull'utente e quindi **scegliere Gestisci proprietari raccolta siti**.

9. Aggiungere l'utente agli **amministratori della raccolta siti** e selezionare **OK.**

10. L'utente potrà ora accedere alla OneDrive dell'ex dipendente usando l'URL OneDrive lavoro. 

### <a name="revoke-admin-access-to-a-users-onedrive"></a>Revocare l'accesso dell'amministratore alla OneDrive

È possibile concedere l'accesso al contenuto nel OneDrive di un utente, ma è possibile rimuovere l'accesso quando non è più necessario.

1. Accedi <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">all'interfaccia di amministrazione</a> come amministratore globale o amministratore SharePoint amministratore.

    Se viene visualizzato un messaggio che indica che non si dispone dell'autorizzazione per accedere all'interfaccia di amministrazione, non si dispone delle autorizzazioni di amministratore nell'organizzazione.

2. Nel riquadro sinistro selezionare **Interfaccia di amministrazione** \> **SharePoint**. Potrebbe essere necessario selezionare **Mostra tutto** per vedere l'elenco di interfacce di amministrazione.

3. Se viene visualizzata SharePoint'interfaccia di  amministrazione classica, selezionare Apri ora nella parte superiore della pagina per aprire l'SharePoint di amministrazione.

4. Nel riquadro sinistro selezionare **Altre funzionalità.**

5. In **Profili utente** selezionare **Apri.**

6. In **Utenti** selezionare **Gestisci profili utente.**

7. Immettere il nome dell'utente e selezionare **Trova**.

8. Fare clic con il pulsante destro del mouse sull'utente e quindi **scegliere Gestisci proprietari raccolta siti**.

9. Rimuovere la persona che non ha più bisogno di accedere ai dati dell'utente e quindi selezionare **OK.**

## <a name="access-the-outlook-data-of-a-former-user"></a>Accedere ai Outlook di un ex utente

Per salvare i messaggi di posta elettronica, il calendario, le attività e i contatti dell'ex dipendente, è possibile esportare le informazioni in un file di dati di Outlook (con estensione pst).
  
1. Aggiungere il messaggio di posta elettronica [dell'ex](https://support.microsoft.com/office/6e27792a-9267-4aa4-8bb6-c84ef146101b) dipendente al Outlook (se si reimposta la [password dell'utente,](reset-passwords.md)è possibile impostarlo su qualcosa che solo tu conosci).

2. In Outlook selezionare **File**.

    ![Questo è l'aspetto della barra multifunzione in Outlook 2016.](../../media/d7f66ed3-9861-4521-b410-e86a58ab15a7.png)
  
3. Selezionare **Apri &amp; esporta** \> **Importazione/Esportazione**.

    ![Comando Importa/esporta nella visualizzazione Backstage](../../media/6013919e-d8ce-4902-b7b4-78ff4260a2f8.jpg)
  
4. Selezionare **Esporta in un file** e quindi fare clic su **Avanti.**

    ![Opzione Esporta in un file nell'Importazione/Esportazione guidata](../../media/458466a0-366b-4fbf-a2db-1919412c6527.jpg)
  
5. Selezionare **Outlook file di dati (.pst)** e quindi selezionare **Avanti.**

6. Selezionare l'account che si desidera esportare selezionando il nome o l'indirizzo di posta elettronica, ad esempio Cassetta postale - Anne Weiler o anne@contoso.com. Se si vuole esportare tutto il contenuto dell'account, inclusi i messaggi di posta elettronica, il calendario, i contatti, le attività e le note, verificare che sia selezionata la casella di controllo **Includi sottocartelle**.

    > [!NOTE]
    > È possibile esportare un solo account alla volta. Se si desidera esportare più account, ripetere questi passaggi per ognuno di essi.
  
    ![Finestra di dialogo Esporta file di dati di Outlook con la cartella principale e l'opzione Includi sottocartelle selezionate](../../media/ce36616f-d76d-4ce2-b517-8ac4874e0971.jpg)
  
7. Selezionare **Avanti**.

8. Selezionare **Sfoglia** per selezionare la posizione in cui salvare Outlook file di dati (pst). Digitare un  *nome di file* e quindi scegliere **OK** per continuare.

    > [!NOTE]
    > Se l'esportazione è già stata usata, verranno visualizzati il nome del file e il percorso della cartella precedenti. Digitare un *nome di file diverso* prima di selezionare **OK.**
  
9. Se si esegue l'esportazione in un File di dati di Outlook (.pst) esistente, in **Opzioni** specificare come procedere per l'esportazione di elementi già esistenti nel file.

10. Seleziona **Fine**.

Outlook avvia immediatamente l'esportazione, a meno che non venga creato un nuovo File di dati di Outlook (pst) o non venga usato un file protetto da password.
  
- Se si crea un nuovo File di dati di Outlook (pst), è possibile impostare una password facoltativa per proteggerlo. Quando viene visualizzata Outlook finestra di **dialogo Crea file** di dati, digitare la *password* nelle caselle **Password** e Verifica **password** e quindi selezionare **OK.** Nella finestra **Outlook password del file** di dati digitare la *password* e quindi selezionare **OK.**

- Se si sta esportando in un file di dati di Outlook esistente (pst) protetto da password, nella finestra di dialogo **Password file** di dati di Outlook digitare la *password* e quindi fare clic su **OK.**

Vedere come [esportare o eseguire il backup](https://support.microsoft.com/office/14252b52-3075-4e9b-be4e-ff9ef1068f91) di posta elettronica, contatti e calendario in Outlook file pst in Outlook 2010.

  > [!NOTE]
  > Per impostazione predefinita, la posta elettronica è disponibile offline per un periodo di 12 mesi. Se necessario, vedere come aumentare [i dati disponibili offline.](/outlook/troubleshoot/mailboxes/only-subset-items-synchronized)

### <a name="give-another-user-access-to-a-former-users-email"></a>Concedere a un altro utente l'accesso alla posta elettronica di un ex utente

Per concedere l'accesso ai messaggi di posta elettronica, al calendario, alle attività e ai contatti dell'ex dipendente a un altro dipendente, importare le informazioni nella posta in arrivo di un altro Outlook dipendente.

> [!NOTE]
> È inoltre possibile [convertire la cassetta postale dell'ex](/office365/admin/email/convert-user-mailbox-to-shared-mailbox) utente in una cassetta postale condivisa o inoltrare la posta elettronica di un ex dipendente a un altro [dipendente.](/office365/admin/add-users/remove-former-employee#forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox)

1. In Outlook, andare a **Apri file** \> **&amp; Esporta** \> **Importazione/Esportazione**.

    Viene avviata l'Importazione/Esportazione guidata.

2. Selezionare **Importa da un altro programma o file** e quindi fare clic su **Avanti.**

    ![Importazione/Esportazione guidata](../../media/15cdd674-cd7b-492c-8e93-992cfa890f26.jpg)
  
3. Selezionare **Outlook file di dati (.pst)** e selezionare **Avanti.**

4. Passare al file PST che si vuole importare.

5. In **Opzioni** scegliere come si vuole gestire i duplicati.

6. Selezionare **Avanti**.

7. Se al file di dati Outlook (.pst) è stata assegnata una password, immettere la password e quindi selezionare **OK.**

8. Impostare le opzioni per l'importazione degli elementi. Solitamente, non è necessario modificare le impostazioni predefinite.

9. Seleziona **Fine**.

> [!NOTE]
> I passaggi rimangono gli stessi per accedere ai dati di posta elettronica e OneDrive di un utente esistente.

> [!TIP]
> Se si desidera importare o ripristinare solo alcuni elementi da un file di dati di Outlook (.pst), è possibile aprire il Outlook File di dati. Nel riquadro di spostamento trascinare quindi gli elementi dalle Outlook file di dati alle cartelle Outlook esistenti. 

## <a name="related-content"></a>Contenuto correlato

[Aggiungere e rimuovere amministratori in un account OneDrive](/sharepoint/manage-user-profiles#add-and-remove-admins-for-a-users-onedrive) (articolo)\
[Ripristinare un OneDrive](/onedrive/restore-deleted-onedrive) eliminato (articolo)\
[OneDrive conservazione ed eliminazione (articolo)](/onedrive/retention-and-deletion)
