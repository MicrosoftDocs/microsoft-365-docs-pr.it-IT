---
title: Ripristinare un gruppo di Office 365 eliminato
ms.reviewer: arvaradh
f1.keywords:
- CSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b7c66b59-657a-4e1a-8aa0-8163b1f4eb54
description: "Informazioni su come ripristinare un gruppo di Office 365 eliminato utilizzando l'interfaccia di amministrazione di Exchange. "
ms.openlocfilehash: c88f10df27e5f3a0af79c93c7d0e347c5646abc9
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/02/2020
ms.locfileid: "42352437"
---
# <a name="restore-a-deleted-office-365-group"></a>Ripristinare un gruppo di Office 365 eliminato

Se si è il proprietario di un gruppo di Office 365, è possibile ripristinare il gruppo manualmente attenendosi alla procedura seguente.

1. Nella [pagina Gruppi eliminati](https://outlook.office.com/people/group/deleted)selezionare l'opzione **Gestisci gruppi** nel nodo **gruppi** e quindi scegliere **eliminata**.
2. Fare clic sulla scheda **Ripristina** accanto al gruppo che si desidera ripristinare.

Se il gruppo eliminato non viene visualizzato, contattare un amministratore.
  
Se sei un utente che vuole ripristinare un gruppo di Office 365, Chiedi a un amministratore di eseguire questi passaggi per te o contattare l'help desk.  
   
Se si è eliminato un gruppo, questo verrà mantenuto per 30 giorni per impostazione predefinita. Questo periodo di 30 giorni è considerato "soft-delete" perché è ancora possibile ripristinare il gruppo. Dopo 30 giorni, il gruppo e il relativo contenuto associato vengono eliminati definitivamente e non possono essere ripristinati.
  
Durante il periodo di "eliminazione temporanea", se un utente tenta di accedere al sito riceverà un messaggio 404 _Forbidden_ . Dopo questo periodo, se un utente tenta di accedere al sito, riceverà un messaggio di 404 _non trovato_ .
  
Quando si ripristina un gruppo, vengono ripristinati anche i contenuti seguenti:
  
- Gli oggetti, le proprietà e i membri di Azure Active Directory (AD) Office 365 gruppi.
    
- Indirizzi di posta elettronica del gruppo.
    
- Posta in arrivo condivisa e calendario di Exchange Online.
    
- Sito e file del team di SharePoint Online.
    
- Blocco appunti di OneNote
    
- Planner
    
- Teams

- Gruppo di Yammer e contenuto del gruppo (se il gruppo di Office 365 è stato creato da Yammer)
    
Si può anche [Eliminare definitivamente un gruppo di Office 365](#permanently-delete-an-office-365-group) se non si può aspettare che scadano i 30 giorni del periodo di conservazione e che il contenuto venga quindi eliminato definitivamente. 

> [!NOTE]
> Anche il proprietario del gruppo di Office 365 eliminato è in grado di ripristinare il gruppo. Per ripristinare un gruppo di Office 365 utilizzando l'autorizzazione proprietario senza autorizzazione di amministratore, vedere [ripristino di un gruppo di office 365 tramite PowerShell](#restore-an-office-365-group-using-powershell).

## <a name="restore-an-office-365-group-using-the-exchange-admin-center"></a>Ripristinare un gruppo di Office 365 tramite l'interfaccia di amministrazione di Exchange

È necessario disporre delle autorizzazioni di amministratore globale di Office 365.

1. Accedere all'<a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">interfaccia di amministrazione di Exchange</a>.
    
2. Nell'interfaccia di amministrazione di Exchange selezionare **destinatari** e quindi scegliere **gruppi**. È possibile visualizzare se il gruppo è attivo o è stato eliminato temporaneamente. Se il gruppo è stato eliminato definitivamente, non sarà incluso nell'elenco.
  
3. Per visualizzare l'ora esatta in cui il gruppo è stato eliminato temporaneamente, selezionare il gruppo e visualizzare le informazioni nel riquadro destro.
      
4. Selezionare il gruppo che si desidera ripristinare, quindi selezionare l'icona Ripristina.
    
    ![Scegliere il gruppo che si desidera ripristinare, quindi selezionare l'icona Ripristina.](../../media/restore-group.png)
  
5. Selezionare Aggiorna ![Icona Aggiorna](../../media/6464df90-2a91-4c1f-92a6-9a38c7696ac3.gif) per aggiornare le informazioni della pagina. Lo stato del gruppo sarà ora attivo. Verranno ripristinate anche le forme e i dati del modulo associati al gruppo.
    
## <a name="restore-an-office-365-group-using-powershell"></a>Ripristinare un gruppo di Office 365 tramite PowerShell

È necessario disporre delle autorizzazioni di amministratore globale di Office 365 o essere un ex proprietario del gruppo di Office 365 eliminato.

> [!IMPORTANT]
> Se si utilizza il file Remove-MsolGroup in PowerShell per eliminare un gruppo, questo eliminerà definitivamente il gruppo. Quando si usa PowerShell per l'eliminazione di gruppi, è buona pratica usare **Remove-AzureADMSGroup** per eliminare il gruppo di Office 365 temporaneamente. In questo modo sarà possibile ripristinarlo, se necessario. 
  
### <a name="install-the-preview-version-of-the-azure-active-directory-powershell-for-graph"></a>Installare la versione in anteprima di Azure Active Directory PowerShell for Graph

> [!IMPORTANT]
> Non è possibile installare contemporaneamente entrambe le versioni di anteprima e di GA nello stesso computer.
  
Come procedura consigliata, è consigliabile rimanere *sempre* aggiornati, ovvero disinstallare la versione Old AzureADPreview o Old AzureAD e ottenere quella più recente. 
  
 
1. Nella barra di ricerca digitare Windows PowerShell.
    
2. Fare clic con il pulsante destro del mouse su **Windows PowerShell** e quindi scegliere **Esegui come amministratore**.
  
2. Esaminare i moduli installati:
    
  ```
  Get-InstalledModule -Name "AzureAD*"
  ```

3. Per disinstallare una versione precedente di AzureADPreview o AzureAD, eseguire questo comando:
  
```
   Uninstall-Module AzureADPreview
```

oppure
  
```
   Uninstall-Module AzureAD
```

4. To install the latest version of AzureADPreview, run this command:
  
```
   Install-Module AzureADPreview
```



At the message about an untrusted repository, type **Y**. It will take a minute or so for the new module to install. 
  
### <a name="restore-the-deleted-group"></a>Ripristinare il gruppo eliminato
  
1. È stato installato il modulo **AzureADPreview** , come indicato nella sezione previoius "installare la versione di anteprima del modulo di Azure Active Directory per Windows PowerShell"?  La causa principale del mancato funzionamento di questa procedura è l'assenza della versione **in anteprima** più recente. 
    
2. Se non è già aperta, aprire una finestra Windows PowerShell nel computer. Non importa se è una finestra Windows PowerShell normale o una aperta selezionando **Esegui come amministratore**.
    
3. Per eseguire i comandi seguenti, premere **invio** dopo ognuno: 
    
  ```
  Import-Module AzureADPreview
  ```

  ```
  Connect-AzureAD
  ```



  Nella schermata **accedi al tuo account** che si apre, immettere il nome utente e la password dell'account amministrativo per connettersi al servizio Azure ad e selezionare **Accedi**.
  
4. Eseguire questo comando per visualizzare tutti i gruppi di Office 365 con eliminazione temporanea nell'organizzazione che sono ancora entro il periodo di cancellazione di 30 giorni:
    
  ```
  Get-AzureADMSDeletedGroup
  ```

5. Annotare l'ID oggetto del gruppo o dei gruppi da ripristinare. Se non si Visualizza il gruppo che si sta cercando in questo elenco, è probabile che sia già stato eliminato definitivamente.
    
    > [!CAUTION]
    > Se è stato creato un nuovo gruppo con lo stesso indirizzo SMTP del gruppo eliminato, occorre eliminare il nuovo gruppo per poter ripristinare quello eliminato. 
  
6. Per ripristinare il gruppo, eseguire il comando seguente:
    
  ```
  Restore-AzureADMSDeletedDirectoryObject -Id <objectId>
  ```

7. Questo processo in genere richiede solo pochi minuti, ma in alcuni casi rari può richiedere fino a 24 ore per essere completamente ripristinato. Per verificare che il gruppo sia stato ripristinato correttamente, eseguire questo comando in PowerShell:
    
  ```
  Get-AzureADGroup -ObjectId <objectId>
  ```

Una volta completato il ripristino, il gruppo dovrebbe ricomparire nel riquadro di spostamento in Outlook e in Outlook sul Web. Tutti i contenuti ripristinati, tra cui quelli di SharePoint e Planner, dovrebbero essere di nuovo disponibili per i membri del gruppo.
  
## <a name="permanently-delete-an-office-365-group"></a>Eliminare definitivamente un gruppo di Office 365

A volte è possibile che si desideri eliminare definitivamente un gruppo senza attendere la scadenza del periodo di cancellazione di 30 giorni. A tale scopo, avviare PowerShell ed eseguire questo comando per ottenere l'ID oggetto del gruppo:
  
```
Get-AzureADMSDeletedGroup
```

Prendere nota dell'ID oggetto del gruppo o dei gruppi che si desidera eliminare definitivamente.
  
> [!CAUTION]
> Il gruppo e i dati che contiene vengono eliminati in modo definitivo. 
  
Per eliminare il gruppo, eseguire questo comando in PowerShell:
  
```
Remove-AzureADMSDeletedDirectoryObject -Id <objectId>
```

Per verificare che il gruppo sia stato eliminato correttamente, eseguire di nuovo il cmdlet  *Get-AzureADMSDeletedGroup*  per controllare che il gruppo non compaia più nell'elenco dei gruppi eliminati temporaneamente. In alcuni casi l'eliminazione definitiva del gruppo e di tutti i suoi dati può richiedere fino a 24 ore. 
  
## <a name="got-questions-about-office-365-groups"></a>Domande su Gruppi di Office 365?

Visitare la [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) per inviare domande e partecipare a conversazioni sui gruppi di Office 365. 
  
## <a name="related-articles"></a>Articoli correlati

[Gestire Gruppi di Office 365 con PowerShell](https://support.office.com/article/aeb669aa-1770-4537-9de2-a82ac11b0540)
  
[Eliminare gruppi usando il cmdlet Remove-UnifiedGroup](https://technet.microsoft.com/library/mt238270%28v=exchg.160%29.aspx)
  
[Gestire le impostazioni del sito del team connesso al gruppo](https://support.office.com/article/8376034d-d0c7-446e-9178-6ab51c58df42.aspx)
  
[Eliminare un gruppo in Outlook](https://support.office.com/article/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f.aspx)
