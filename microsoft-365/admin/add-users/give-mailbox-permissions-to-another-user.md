---
title: Assegnare le autorizzazioni della cassetta postale a un altro utente - Guida per l'amministratore
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1dbcf12f-a9de-4d1d-b0b3-a227f8a736d8
description: "Informazioni su come assegnare a un utente il diritto di accedere alla cassetta postale di un altro utente. In questo modo l'utente potrà leggere i messaggi di posta elettronica e inviare messaggi dalla cassetta postale dell'altro utente. "
ms.openlocfilehash: dafe0f8c8f7d65b2721b70f6c132d179c461a89b
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780602"
---
# <a name="give-mailbox-permissions-to-another-user---admin-help"></a>Assegnare le autorizzazioni della cassetta postale a un altro utente - Guida per l'amministratore

In base ai requisiti aziendali, l'amministratore può consentire ad alcuni utenti di accedere alla cassetta postale di un altro utente. Ad esempio, è possibile consentire a un assistente di inviare o leggere posta elettronica dalla cassetta postale del suo manager oppure permettere a un utente di inviare messaggi per conto di un altro utente. Questo argomento illustra le procedure da eseguire.
  
Se si cercano informazioni su come creare e gestire cassette postali condivise, vedere [Creare una cassetta postale condivisa](../email/create-a-shared-mailbox.md).
    
## <a name="looking-to-set-up-mailbox-permissions"></a>Configurare le autorizzazioni per le cassette postali

Le autorizzazioni per le cassette postali consentono di concedere a un altro utente l'accesso in lettura/scrittura a una cassetta postale. Gli articoli elencati di seguito potrebbero fornire l'aiuto necessario per configurare e usare questa funzionalità:
  
 **Configurazione delle autorizzazioni:**
  
Il primo passaggio del processo di configurazione delle autorizzazioni consiste nel decidere quali azioni potranno essere eseguite dall'altro utente nella cassetta postale specifica. È possibile consentire a un utente di leggere i messaggi di posta elettronica contenuti nella cassetta postale, inviare messaggi per conto di un altro utente oppure inviarli con la cassetta postale come mittente. Per informazioni su come configurare ogni tipo di autorizzazione, vedere gli articoli seguenti:
  
- [Leggere messaggi di posta elettronica dalla cassetta postale di un altro utente](give-mailbox-permissions-to-another-user.md#read-email-in-another-users-mailbox)
    
- [Inviare messaggi di posta elettronica dalla cassetta postale di un altro utente](give-mailbox-permissions-to-another-user.md#send-email-from-another-users-mailbox)

- [Inviare e-mail per conto di un altro utente](give-mailbox-permissions-to-another-user.md#send-email-on-behalf-of-another-user)
    
 **Propagazione delle modifiche:**
  
Dopo la configurazione delle autorizzazioni, la loro propagazione e applicazione nell'intero sistema può richiedere fino a 60 minuti.
  
 **Come usare la funzionalità dopo la configurazione delle autorizzazioni:**
  
Dopo la concessione dell'accesso, è possibile accedere a una cassetta postale in alcuni modi diversi. Per altre informazioni, vedere l'articolo [Accedere alla cassetta postale di un'altra persona](https://support.microsoft.com/office/A909AD30-E413-40B5-A487-0EA70B763081).
  
## <a name="send-email-from-another-users-mailbox"></a>Inviare messaggi di posta elettronica dalla cassetta postale di un altro utente

::: moniker range="o365-worldwide"

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.  
    
2. Selezionare il nome dell'utente da cui si vuole concedere l'autorizzazione di invio per aprire il riquadro delle proprietà.
    
3. Nella scheda **Posta** selezionare **Gestire le autorizzazioni della cassetta postale**.

4. Accanto a **Invia come** selezionare **Modifica**. 

5. Selezionare **Aggiungi autorizzazioni**, quindi scegliere il nome della persona con cui si vuole che questo utente invii un messaggio. 
    
6. Selezionare **Salva**.
 
::: moniker-end

::: moniker range="o365-germany"

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Utenti attivi</a>.  

2. Selezionare l'utente desiderato, espandere **Impostazioni della posta** e quindi selezionare **Modifica** accanto a **Autorizzazioni cassetta postale**.

3. Accanto a **Invia come** selezionare **Modifica**. 

4. Selezionare **Aggiungi autorizzazioni**, quindi scegliere il nome della persona con cui si vuole che questo utente invii un messaggio. 
    
5. Selezionare **Salva**.

::: moniker-end

::: moniker range="o365-21vianet"

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Utenti attivi</a>. 

2. Selezionare l'utente desiderato, espandere **Impostazioni della posta** e quindi selezionare **Modifica** accanto a **Autorizzazioni cassetta postale**.

3. Accanto a **Invia come** selezionare **Modifica**. 

4. Selezionare **Aggiungi autorizzazioni**, quindi scegliere il nome della persona con cui si vuole che questo utente invii un messaggio. 
    
5. Selezionare **Salva**.

::: moniker-end
  
## <a name="read-email-in-another-users-mailbox"></a>Leggere messaggi di posta elettronica nella cassetta postale di un altro utente

::: moniker range="o365-worldwide"

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.  
    
2. Selezionare il nome dell'utente (di cui si vuole consentire la lettura della cassetta postale) per aprire il riquadro delle proprietà.
    
3. Nella scheda **Posta** selezionare **Gestire le autorizzazioni della cassetta postale**.
    
4. Accanto a **Lettura e gestione**, selezionare **Modifica**. 
    
5. Selezionare **Aggiungi autorizzazioni** e quindi scegliere il nome dell'utente o degli utenti a cui si vuole consentire la lettura dei messaggi di posta elettronica da questa cassetta postale.

6. Selezionare **Salva**.

::: moniker-end

::: moniker range="o365-germany"

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Utenti attivi</a>.  
  
2. Selezionare l'utente desiderato, espandere **Impostazioni della posta** e quindi selezionare **Modifica** accanto a **Autorizzazioni cassetta postale**.
    
3. Accanto a **Lettura e gestione**, selezionare **Modifica**. 
    
4. Selezionare **Aggiungi autorizzazioni** e quindi scegliere il nome dell'utente o degli utenti a cui si vuole consentire la lettura dei messaggi di posta elettronica da questa cassetta postale.

5. Selezionare **Salva**.

::: moniker-end

::: moniker range="o365-21vianet"

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Utenti attivi</a>. 
  
2. Selezionare l'utente desiderato, espandere **Impostazioni della posta** e quindi selezionare **Modifica** accanto a **Autorizzazioni cassetta postale**.
    
3. Accanto a **Lettura e gestione**, selezionare **Modifica**. 
    
4. Selezionare **Aggiungi autorizzazioni** e quindi scegliere il nome dell'utente o degli utenti a cui si vuole consentire la lettura dei messaggi di posta elettronica da questa cassetta postale.

5. Selezionare **Salva**.

::: moniker-end


## <a name="send-email-on-behalf-of-another-user"></a>Inviare messaggi di posta elettronica per conto di un altro utente

::: moniker range="o365-worldwide"

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.  

2. Selezionare il nome dell'utente da cui si vuole concedere l'autorizzazione **Invia per conto di** per aprire il riquadro delle proprietà.
    
3. Nella scheda **Posta** selezionare **Gestire le autorizzazioni della cassetta postale**.
    
4. Accanto a **Invia per conto di** selezionare **Modifica**.

5. Selezionare **Aggiungi autorizzazioni** e quindi scegliere il nome dell'utente o degli utenti a cui si vuole consentire l'invio di messaggi di posta elettronica per conto di questa cassetta postale.

6. Selezionare **Salva**.

::: moniker-end

::: moniker range="o365-germany"

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Utenti attivi</a>.  

2. Selezionare l'utente desiderato, espandere **Impostazioni della posta** e quindi selezionare **Modifica** accanto a **Autorizzazioni cassetta postale**.

3. Accanto a **Invia per conto di** selezionare **Modifica**.
    
4. Selezionare **Aggiungi autorizzazioni** e quindi scegliere il nome dell'utente o degli utenti a cui si vuole consentire l'invio di messaggi di posta elettronica per conto di questa cassetta postale.

5. Selezionare **Salva**.

::: moniker-end

::: moniker range="o365-21vianet"

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Utenti attivi</a>. 

2. Selezionare l'utente desiderato, espandere **Impostazioni della posta** e quindi selezionare **Modifica** accanto a **Autorizzazioni cassetta postale**.

3. Accanto a **Invia per conto di** selezionare **Modifica**.
    
4. Selezionare **Aggiungi autorizzazioni** e quindi scegliere il nome dell'utente o degli utenti a cui si vuole consentire l'invio di messaggi di posta elettronica per conto di questa cassetta postale.

5. Selezionare **Salva**.

::: moniker-end


## <a name="send-and-read-from-outlook-and-outlook-on-the-web-for-business"></a>Inviare e leggere messaggi da Outlook e Outlook sul Web per le aziende


Per informazioni su come inviare messaggi di posta elettronica dalla cassetta postale di un altro utente, vedere gli argomenti seguenti:
  
- [Gestire gli elementi di posta e di calendario di un altro utente](https://support.microsoft.com/office/afb79d6b-2967-43b9-a944-a6b953190af5)
    
- [Inviare un messaggio di posta elettronica da un altro utente o gruppo](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b)
