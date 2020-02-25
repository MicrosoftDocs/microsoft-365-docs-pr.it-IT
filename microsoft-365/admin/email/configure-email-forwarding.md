---
title: Configurare l'inoltro della posta elettronica in Office 365
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: ab5eb117-0f22-4fa7-a662-3a6bdb0add74
description: Impostare l'inoltro della posta elettronica su uno o più account di posta elettronica utilizzando Office365.
ms.openlocfilehash: b6ad4032748c35db8e8c18b609915aef4231cb6c
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/24/2020
ms.locfileid: "42253058"
---
# <a name="configure-email-forwarding-in-office-365"></a>Configurare l'inoltro della posta elettronica in Office 365
  
L'amministratore di un'organizzazione di Office 365 può avere dei requisiti da rispettare per la configurazione dell'inoltro della posta elettronica della cassetta postale di un utente. L'inoltro della posta elettronica consente di inoltrare i messaggi inviati alla cassetta postale di un utente a quella di un altro utente all'interno o all'esterno dell'organizzazione.

  
## <a name="configure-email-forwarding"></a>Configurare l'inoltro della posta elettronica

 Prima di configurare l'inoltro della posta elettronica, tenere presente quanto segue: 

- Dopo aver configurato l'inoltro della posta elettronica, solo i **nuovi** messaggi di posta elettronica inviati alla cassetta postale *da* saranno fowarded. 
    
- L'inoltro della posta elettronica richiede che l'account *da* disponga di una licenza. Se si sta configurando l'inoltro della posta elettronica perché l'utente ha lasciato la propria organizzazione, un'altra opzione consiste nel [convertire la cassetta postale in una cassetta postale condivisa](convert-user-mailbox-to-shared-mailbox.md). In questo modo diverse persone possono accedervi. Tuttavia, una cassetta postale condivisa non può essere superiore a 50 GB. 
    
Per eseguire questa procedura è necessario essere un amministratore di Exchange o un amministratore globale di Office 365. Per ulteriori informazioni, vedere l'argomento [relativo ai ruoli di amministratore](../add-users/about-admin-roles.md).

::: moniker range="o365-worldwide"

> [!NOTE]
> Se non si usa la nuova interfaccia di amministrazione di Microsoft 365, è possibile attivarla selezionando l'opzione **Prova la nuova interfaccia di amministrazione** che si trova nella parte superiore della home page.

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.
    
2. Selezionare il nome dell'utente di cui si desidera inoltrare la posta elettronica per aprire la pagina delle proprietà. 
 
3. Nella scheda **posta** , selezionare **Gestisci inoltro della posta elettronica**. 
  
4. Nella pagina inoltro della posta elettronica, selezionare **inoltra tutti i messaggi di posta elettronica inviati a questa cassetta postale**, immettere l'indirizzo di inoltro e scegliere se si desidera mantenere una copia dei messaggi di posta elettronica inoltrati. Se non si vede questa opzione, assicurarsi che sia assegnata una licenza all'account utente. Selezionare **Salva modifiche**.
    
    **Per inoltrare a più indirizzi di posta elettronica**, è possibile chiedere all'utente di impostare una regola in Outlook per inoltrare agli indirizzi. Per ulteriori informazioni, vedere [utilizzare le regole per inoltrare automaticamente i messaggi](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746). 
    
     In alternativa, nell'interfaccia di amministrazione, [creare un gruppo di distribuzione](../setup/create-distribution-lists.md), [aggiungere gli indirizzi](add-user-or-contact-to-distribution-list.md)e quindi impostare l'inoltro in modo che punti al DL seguendo le istruzioni riportate in questo articolo.
    
5. Non eliminare l'account dell'utente che si sta inoltrando o rimuovere la propria licenza.  In caso contrario, l'inoltro della posta elettronica si arresterà. 

::: moniker-end

::: moniker range="o365-germany"
    
 1.   Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Utenti attivi</a>. 
    
2. Selezionare il nome dell'utente di cui si desidera inoltrare la posta elettronica per aprire la pagina delle proprietà. 

3. Espandere **impostazioni di posta elettronica**e quindi nella sezione **inoltro della posta elettronica** Selezionare **modifica**.

4. Nella pagina inoltro di posta elettronica, impostare l'interruttore **su**attivato, immettere l'indirizzo di inoltro e scegliere se si desidera mantenere una copia dei messaggi di posta elettronica inoltrati. Se non si vede questa opzione, assicurarsi che sia assegnata una licenza all'account utente. Selezionare **Salva**.
    
    **Per inoltrare a più indirizzi di posta elettronica**, è possibile chiedere all'utente di impostare una regola in Outlook per inoltrare agli indirizzi. Per ulteriori informazioni, vedere [utilizzare le regole per inoltrare automaticamente i messaggi](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746). 
    
     In alternativa, nell'interfaccia di amministrazione, [creare un gruppo di distribuzione](../setup/create-distribution-lists.md), [aggiungere gli indirizzi](add-user-or-contact-to-distribution-list.md)e quindi impostare l'inoltro in modo che punti al DL seguendo le istruzioni riportate in questo articolo.
    
5. Non eliminare l'account dell'utente che si sta inoltrando o rimuovere la propria licenza.  In caso contrario, l'inoltro della posta elettronica si arresterà.    

::: moniker-end

::: moniker range="o365-21vianet"

 1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Utenti attivi</a>. 
    
2. Selezionare il nome dell'utente di cui si desidera inoltrare la posta elettronica per aprire la pagina delle proprietà. 

3. Espandere **impostazioni di posta elettronica**e quindi nella sezione **inoltro della posta elettronica** Selezionare **modifica**.

4. Nella pagina inoltro di posta elettronica, impostare l'interruttore **su**attivato, immettere l'indirizzo di inoltro e scegliere se si desidera mantenere una copia dei messaggi di posta elettronica inoltrati. Se non si vede questa opzione, assicurarsi che sia assegnata una licenza all'account utente. Selezionare **Salva**.
    
    **Per inoltrare a più indirizzi di posta elettronica**, è possibile chiedere all'utente di impostare una regola in Outlook per inoltrare agli indirizzi. Per ulteriori informazioni, vedere [utilizzare le regole per inoltrare automaticamente i messaggi](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746). 
    
     In alternativa, nell'interfaccia di amministrazione, [creare un gruppo di distribuzione](../setup/create-distribution-lists.md), [aggiungere gli indirizzi](add-user-or-contact-to-distribution-list.md)e quindi impostare l'inoltro in modo che punti al DL seguendo le istruzioni riportate in questo articolo.
    
5. Non eliminare l'account dell'utente che si sta inoltrando o rimuovere la propria licenza.  In caso contrario, l'inoltro della posta elettronica si arresterà. 

::: moniker-end 
