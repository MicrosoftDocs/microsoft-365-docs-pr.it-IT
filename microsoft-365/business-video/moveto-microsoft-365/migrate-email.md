---
title: Eseguire la migrazione della posta elettronica e del calendario aziendale da Google Workspace
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
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Informazioni su come eseguire la migrazione di posta elettronica, contatti e calendario da Google Workspace a Microsoft 365 for business.
ms.openlocfilehash: ab70a43fb7c26c23ebc9024b1cd2803c164a0aa4
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794646"
---
# <a name="migrate-business-email-and-calendar-from-google-workspace"></a>Eseguire la migrazione della posta elettronica e del calendario aziendale da Google Workspace

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LPt6?autoplay=false]

È possibile utilizzare una migrazione con l'amministratore eseguito a Exchange Online da Google Workspace. È possibile eseguire la migrazione della posta elettronica in una sola volta o in fasi. Nei passaggi seguenti viene illustrato come eseguire la migrazione dei dati di posta elettronica in una sola volta. Per ulteriori informazioni, vedere [eseguire la migrazione di un gruppo G](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration).

Il processo di migrazione richiede diversi passaggi e può richiedere da diverse ore a un paio di giorni a seconda della quantità di dati di cui si esegue la migrazione.

## <a name="try-it"></a>Perché non provarlo?

### <a name="create-a-google-service-account"></a>Creare un account di servizio di Google

1. Utilizzando un browser Chrome, accedere alla console di amministrazione di Google Workspace all' [admin.Google.com](https://admin.google.com). 
1. In una nuova scheda o finestra passare alla pagina [account di servizio](https://console.developers.google.com/iam-admin/serviceaccounts) . 
1. Selezionare **Crea progetto**, denominare il progetto e scegliere **Crea**. 
1. Selezionare **Crea account di servizio**, immettere un nome, fare clic su **Crea** e quindi su **fine**. 
1. Aprire il menu **azioni** , selezionare **modifica** e prendere nota dell'ID univoco. Questo ID sarà necessario in un secondo momento nel processo. 
1. Aprire la sezione **Mostra delega a livello di dominio** . 
1. Selezionare **Abilita delega a livello di dominio G Suite**, immettere un nome di prodotto per la schermata di consenso e fare clic su **Salva**. 

    > [!NOTE]
> Il nome del prodotto non viene utilizzato dal processo di migrazione, ma è necessario salvarlo nella finestra di dialogo.     

1. Aprire di nuovo il menu **azioni** e selezionare **Crea chiave**. 
1. Scegliere **JSON** e quindi **Crea**. 

     La chiave privata viene salvata nella cartella di download del dispositivo.
 
1. Selezionare **Chiudi**. 

### <a name="enable-api-usage-for-the-project"></a>Abilitazione dell'utilizzo delle API per il progetto

1. Passare alla [pagina Apis](https://console.developers.google.com/apis/library). 
1. Nella barra di ricerca, immettere **Gmail API**.
1. Selezionarlo e quindi fare clic su **Abilita**.
1. Ripetere questa procedura per API di Google Calendar e API dei contatti. 

### <a name="grant-access-to-the-service-account"></a>Concedere l'accesso all'account di servizio

1. Tornare alla console di amministrazione di Google Workspace. 
1. Selezionare **sicurezza**, scorrere verso il basso e aprire i **Controlli API**. 
1. Scorrere verso il basso e selezionare **Gestisci delega a livello di dominio**.
1. Selezionare **Aggiungi nuovo** e immettere l'ID client annotato in precedenza.
1. Immettere quindi gli ambiti OAuth per le API di Google. Sono disponibili in [aka.ms/GoogleWorkspaceMigration](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration#grant-access-to-the-service-account-for-your-google-tenant) nel passaggio 5 e sono:

    `https://mail.google.com/,https://www.googleapis.com/auth/calendar,https://www.google.com/m8/feeds/,https://www.googleapis.com/auth/gmail.settings.sharing`
 
1. Scegliere **autorizza**. 

### <a name="create-a-sub-domain-for-mail-going-to-microsoft-365"></a>Creare un sottodominio per la posta elettronica in Microsoft 365

1. Tornare alla console di **amministrazione di Google Workspace** .
1. Selezionare **domini**, **Manage** Domains e quindi **aggiungere un alias di dominio**. 
1. Immettere un alias di dominio come `m365.contoso.com` .
1. Quindi **, selezionare continua e verificare la proprietà del dominio**. 

    La verifica del dominio richiede solitamente solo pochi minuti, ma può richiedere fino a 48 ore.

1. Accedere all'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com).
1. Nell'interfaccia **di amministrazione di Microsoft 365**, nella barra di spostamento sinistra, selezionare **Mostra tutto**, **Impostazioni**, **domini** e quindi **Aggiungi dominio**. 
1. Immettere il sottodominio creato in precedenza, quindi selezionare **Usa questo dominio**. 
1. Per connettere il dominio, selezionare **continua**. 
1. Scorrere verso il basso e prendere nota dei record MX, record CNAME e TXT. 
1. Tornare alla **console di amministrazione di Google**.
1. Selezionare **domini**, selezionare **Manage** Domains, **Verify Details** e then, **Manage Domain**. 
1. Nel NAV sinistro, scegliere **DNS** e scorrere verso il basso fino a **record di risorse personalizzati**. 
1. Aprire la casella di riepilogo a discesa tipo di record e selezionare **MX**, immettere o copiare e incollare le informazioni del record MX precedentemente note, quindi scegliere **Aggiungi**. 
1. Ripetere il processo per il record CNAME e il record TXT. 

    Per rendere effettive le modifiche, potrebbe essere necessario un certo tempo.  

1. Tornare alla posizione in cui è stato interrotto nell'interfaccia di **amministrazione di Microsoft 365** e selezionare **continua**. 

Il dominio è ora configurato.  

### <a name="create-email-aliases-in-microsoft-365"></a>Creare alias di posta elettronica in Microsoft 365

Prima di iniziare la migrazione, è necessario creare alias di posta elettronica per gli utenti con il nuovo sottodominio. 

1. Per avviare il passaggio successivo, nella procedura guidata **Aggiungi domini** nell'interfaccia di amministrazione di Microsoft 365 selezionare **Vai a utenti attivi**. 
1. Selezionare un utente, quindi **gestire il nome utente e la posta elettronica**. 
1. Nell'elenco a discesa **domini** selezionare il sottodominio creato in precedenza. 
1. Immettere un nome utente, fare clic su **Aggiungi**, **salvare le modifiche** e chiudere la finestra. 

    Ripetere questa procedura per ogni utente. 

### <a name="start-the-migration-process"></a>Avviare il processo di migrazione

Dopo aver completato l'operazione, è possibile eseguire la migrazione. 

1. Nella barra di spostamento sinistra dell'interfaccia di **amministrazione di Microsoft 365**, scorrere verso il basso fino a interfacce di **Amministrazione** e selezionare **Exchange**. 
1. In **destinatari** fare clic su **migrazione**, selezionare **nuovo**, eseguire la migrazione **a Exchange Online**, scegliere **G Suite Migration** e quindi **Avanti**. 
1. Creare un file CSV con un elenco delle cassette postali di cui si desidera eseguire la migrazione. Verificare che il file segua il formato seguente: 

    ```CSV
    EmailAddress
    will@fabrikaminc.net
    user123@fabrikaminc.net
    ```

      Per informazioni dettagliate, vedere [aka.ms/GoogleWorkspaceMigration](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration#start-a-g-suite-migration-batch-with-the-exchange-admin-center-eac). 

1. Selezionare **Scegli file**, passare al file CSV, selezionarlo, fare clic su **Apri**, quindi su **Avanti**. 
1. Verificare l'indirizzo di posta elettronica dell'amministratore che si desidera utilizzare per il testing. 
1. Selezionare **Scegli file**, passare al file JSON creato in precedenza (in genere nella cartella Downloads del computer), selezionarlo, selezionare **Apri** e quindi **Avanti**. 
1. Immettere un nome nel **campo nuovo nome batch di migrazione**.
1. Immettere il sottodominio creato nel campo **dominio di recapito di destinazione** , selezionare **Avanti** e quindi **nuovo**. 
1. Dopo aver salvato le informazioni, seleziona **OK**. 

    È ora possibile visualizzare lo stato della migrazione. 

1. Dopo un determinato periodo di tempo, a seconda del numero di utenti che si desidera eseguire la migrazione, selezionare **Aggiorna**. 
1. Dopo che lo stato è stato modificato in **sincronizzato**, selezionare **completa il batch di migrazione**, quindi **Sì**. 
1. Al termine del processo, lo stato verrà modificato in **completato**. 
1. Se lo si desidera, è possibile selezionare **Visualizza dettagli** per ulteriori informazioni sulla migrazione. 
1. Selezionare **Chiudi**. 
1. Aprire Outlook per verificare che tutti i messaggi di posta elettronica provenienti da Google Workspace siano stati migrati correttamente.
È possibile ripetere questa operazione anche per gli elementi di calendario e i contatti.