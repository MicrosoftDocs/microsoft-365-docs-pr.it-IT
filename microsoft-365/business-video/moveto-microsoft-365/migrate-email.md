---
title: Eseguire la migrazione della posta elettronica aziendale e del calendario da Google Workspace
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
description: Scopri come eseguire la migrazione di posta elettronica, contatti e calendario da Google Workspace a Microsoft 365 per le aziende.
ms.openlocfilehash: d6639032b379a2cd632b6ab6ee7e4082b1e7be0b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50913623"
---
# <a name="migrate-business-email-and-calendar-from-google-workspace"></a>Eseguire la migrazione della posta elettronica aziendale e del calendario da Google Workspace

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LPt6?autoplay=false]

Puoi usare una migrazione eseguita dall'amministratore per Exchange Online da Google Workspace. È possibile eseguire la migrazione della posta in una sola volta o in più fasi. La procedura seguente illustra come eseguire la migrazione dei dati di posta elettronica contemporaneamente. Per ulteriori informazioni, vedere [Perform a G Suite migration.](/exchange/mailbox-migration/perform-g-suite-migration)

Il processo di migrazione richiede diversi passaggi e può richiedere da diverse ore a un paio di giorni a seconda della quantità di dati di cui si sta eseguendo la migrazione.

## <a name="try-it"></a>Perché non provarlo?

### <a name="create-a-google-service-account"></a>Creare un account di servizio Google

1. Usando un browser Chrome, accedi alla console di amministrazione di Google Workspace [all'admin.google.com](https://admin.google.com). 
1. In una nuova scheda o finestra passare alla pagina [Account di](https://console.developers.google.com/iam-admin/serviceaccounts) servizio. 
1. Selezionare **Crea progetto**, assegnare un nome al progetto e scegliere **Crea**. 
1. Selezionare **Crea account di servizio,** immettere un nome, scegliere **Crea** e quindi **Fine.** 
1. Aprire il menu **Azioni,** selezionare **Modifica** e prendere nota dell'ID univoco. Questo ID sarà necessario più avanti nel processo. 
1. Aprire la **sezione Mostra delega a livello di** dominio. 
1. Seleziona **Abilita delega a livello di dominio G Suite,** immetti un nome di prodotto per la schermata di consenso e scegli **Salva**. 

    > [!NOTE]
> Il nome del prodotto non viene utilizzato dal processo di migrazione, ma è necessario per salvarlo nella finestra di dialogo.     

1. Apri di **nuovo il** menu Azioni e seleziona **Crea chiave.** 
1. Scegli **JSON,** quindi **Crea**. 

     La chiave privata viene salvata nella cartella di download del dispositivo.
 
1. Selezionare **Chiudi**. 

### <a name="enable-api-usage-for-the-project"></a>Abilitare l'utilizzo delle API per il progetto

1. Passare alla [pagina API](https://console.developers.google.com/apis/library). 
1. Nella barra di ricerca immetti **GMAIL API.**
1. Selezionarlo e quindi scegliere **Abilita.**
1. Ripeti questo processo per l'API di Google Calendar e l'API Contatti. 

### <a name="grant-access-to-the-service-account"></a>Concedere l'accesso all'account del servizio

1. Torna alla console di amministrazione di Google Workspace. 
1. Seleziona **Sicurezza,** scorri verso il basso e apri i **controlli API.** 
1. Scorrere verso il basso e **selezionare Gestisci delega a livello di dominio**.
1. Seleziona **Aggiungi nuovo** e immetti l'ID client di cui hai preso nota in precedenza.
1. Immetti quindi gli ambiti OAuth per le API Google. Questi sono disponibili al [aka.ms/GoogleWorkspaceMigration](/exchange/mailbox-migration/perform-g-suite-migration#grant-access-to-the-service-account-for-your-google-tenant) passaggio 5 e sono:

    `https://mail.google.com/,https://www.googleapis.com/auth/calendar,https://www.google.com/m8/feeds/,https://www.googleapis.com/auth/gmail.settings.sharing`
 
1. Scegliere **Autorizza**. 

### <a name="create-a-sub-domain-for-mail-going-to-microsoft-365"></a>Creare un sottodominio per la posta da Microsoft 365

1. Torna alla **console di amministrazione di Google Workspace.**
1. Selezionare **Domini**, **Gestisci domini**, quindi Aggiungi un alias di **dominio**. 
1. Immettere un alias di dominio come `m365.contoso.com` .
1. Selezionare quindi **Continua e verificare la proprietà del dominio.** 

    La verifica del dominio in genere richiede solo pochi minuti, ma può richiedere fino a 48 ore.

1. Passare [all'Microsoft 365 di amministrazione .](https://admin.microsoft.com)
1. **Nell'Microsoft 365 di amministrazione,** nel riquadro di spostamento sinistro, selezionare **Mostra** tutto , **Impostazioni**, **Domini** e quindi **Aggiungi dominio**. 
1. Immetti il sottodominio creato in precedenza, quindi seleziona **Usa questo dominio.** 
1. Per connettere il dominio, selezionare **Continua.** 
1. Scorrere verso il basso e prendere nota dei record MX, CNAME e TXT. 
1. Torna alla **console di amministrazione di Google.**
1. Seleziona **Domini,** seleziona **Gestisci domini,** **Verifica dettagli** e quindi **Gestisci dominio.** 
1. Nel riquadro di spostamento sinistro scegliere **DNS** e scorrere verso il basso fino **a Record di risorse personalizzati.** 
1. Aprire l'elenco a discesa del tipo di record e selezionare **MX**, immettere o copiare e incollare le informazioni sul record MX precedentemente indicato, quindi scegliere **Aggiungi**. 
1. Ripetere il processo per il record CNAME e il record TXT. 

    L'applicazione di queste modifiche potrebbe richiedere del tempo.  

1. Tornare al punto in cui è stato lasciato **Microsoft 365'interfaccia di amministrazione** e selezionare **Continua.** 

Il dominio è ora configurato.  

### <a name="create-email-aliases-in-microsoft-365"></a>Creare alias di posta elettronica in Microsoft 365

Prima di iniziare la migrazione, è necessario creare alias di posta elettronica per gli utenti con il nuovo sottodominio. 

1. Per avviare il passaggio successivo, nella **procedura** guidata Aggiungi domini nell'Microsoft 365 di amministrazione selezionare Vai a **Utenti attivi**. 
1. Seleziona un utente, quindi Gestisci nome **utente e posta elettronica**. 
1. **Nell'elenco a** discesa Domini selezionare il sottodominio creato in precedenza. 
1. Immetti un nome utente, seleziona **Aggiungi,** **Salva modifiche** e chiudi la finestra. 

    Ripetere questo processo per ogni utente. 

### <a name="start-the-migration-process"></a>Avviare il processo di migrazione

Al termine, è possibile eseguire la migrazione. 

1. Nel riquadro di spostamento sinistro **dell'interfaccia di** Microsoft 365, scorrere verso il basso fino a **Interfaccia di amministrazione** e selezionare **Exchange**. 
1. In **destinatari** **scegliere migrazione,** selezionare **Nuovo,** Migra **a Exchange Online,** scegliere **Migrazione G Suite** e quindi **Avanti**. 
1. Creare un file CSV con un elenco delle cassette postali di cui si desidera eseguire la migrazione. Assicurarsi che il file segue questo formato: 

    ```CSV
    EmailAddress
    will@fabrikaminc.net
    user123@fabrikaminc.net
    ```

      Per informazioni [dettagliate, vedere aka.ms/GoogleWorkspaceMigration](/exchange/mailbox-migration/perform-g-suite-migration#start-a-g-suite-migration-batch-with-the-exchange-admin-center-eac). 

1. Seleziona **Scegli file,** passa al file CSV, sceglilo, seleziona **Apri**, quindi **Avanti**. 
1. Verificare l'indirizzo di posta elettronica dell'amministratore che si desidera utilizzare per i test. 
1. Seleziona **Scegli file,** passa al file JSON creato in precedenza (in genere nella cartella Download nel computer), sceglilo, seleziona **Apri**, quindi **Avanti**. 
1. Immettere un nome nel **campo Nuovo nome batch di migrazione**.
1. Immettere il sottodominio creato nel **campo Dominio di recapito di** destinazione, selezionare **Avanti** e quindi **Nuovo**. 
1. Dopo aver salvato le informazioni, selezionare **OK.** 

    È ora possibile visualizzare lo stato della migrazione. 

1. Dopo un certo periodo di tempo, a seconda del numero di utenti di cui si sta eseguendo la migrazione, selezionare **Aggiorna**. 
1. Dopo aver modificato lo stato **in Sincronizzato,** selezionare **Completa il batch di migrazione,** quindi **Sì.** 
1. Al termine del processo, lo stato verrà modificato in **Completato**. 
1. Se si desidera, è possibile selezionare **Visualizza dettagli** per ulteriori informazioni sulla migrazione. 
1. Selezionare **Chiudi**. 
1. Apri Outlook per verificare che la migrazione di tutti i messaggi di posta elettronica da Google Workspace sia stata eseguita correttamente.
È possibile ripetere questa operazione anche per gli elementi del calendario e i contatti.