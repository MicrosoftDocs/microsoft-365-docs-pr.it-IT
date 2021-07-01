---
title: Configurare l'inoltro della posta elettronica
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
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: ab5eb117-0f22-4fa7-a662-3a6bdb0add74
description: L'inoltro della posta elettronica consente di inoltrare i messaggi di posta elettronica inviati a una Microsoft 365 utente a un'altra cassetta postale all'interno o all'esterno dell'organizzazione.
ms.openlocfilehash: e0043fe75eefe224c63fd23f352d4bd3ddf2c326
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228052"
---
# <a name="configure-email-forwarding-in-microsoft-365"></a>Configurare l'inoltro della posta elettronica in Microsoft 365

L'amministratore di un'organizzazione potrebbe avere requisiti aziendali per configurare l'inoltro della posta elettronica per la cassetta postale di un utente. L'inoltro della posta elettronica consente di inoltrare i messaggi inviati alla cassetta postale di un utente a quella di un altro utente all'interno o all'esterno dell'organizzazione.

> [!IMPORTANT]
> È possibile utilizzare i criteri di filtro della posta indesiderata in uscita per controllare l'inoltro automatico ai destinatari esterni. Per ulteriori informazioni, vedere [Control automatic external email forwarding in Microsoft 365](/microsoft-365/security/office-365-security/external-email-forwarding#how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls).

## <a name="configure-email-forwarding"></a>Configurare l'inoltro della posta elettronica

Prima di configurare l'inoltro della posta elettronica, tenere presente quanto segue:

- Consenti l'invio automatico dei messaggi inoltrati agli utenti del dominio remoto. Per [informazioni dettagliate, vedere](/exchange/mail-flow-best-practices/remote-domains/manage-remote-domains) Manage remote domains.

- Dopo aver configurato l'inoltro della posta elettronica, **verranno** inoltrati solo i nuovi messaggi di posta elettronica inviati alla cassetta postale di origine. 

- L'inoltro della posta elettronica richiede che  *l'account from*  abbia una licenza. Se si sta configurando l'inoltro della posta elettronica perché l'utente ha lasciato l'organizzazione, un'altra opzione è convertire la cassetta postale [in una cassetta postale condivisa.](convert-user-mailbox-to-shared-mailbox.md) In questo modo diverse persone possono accedervi. Tuttavia, una cassetta postale condivisa non può superare i 50 GB.

Per eseguire questa Microsoft 365, è necessario essere un amministratore Exchange o un amministratore globale. Per ulteriori informazioni, vedere l'argomento [Informazioni sui ruoli di amministratore.](../add-users/about-admin-roles.md)

1. Nell'interfaccia di amministrazione passare alla **pagina Utenti** \> **[utenti](https://go.microsoft.com/fwlink/p/?linkid=834822)** attivi.

2. Selezionare il nome dell'utente di cui si desidera inoltrare la posta elettronica, quindi aprire la pagina delle proprietà.

3. Nella scheda **Posta** selezionare Gestisci **inoltro posta elettronica**.

4. Nella pagina inoltro della posta elettronica, selezionare Inoltra tutti i messaggi di posta elettronica inviati a questa cassetta **postale,** immettere l'indirizzo di inoltro e scegliere se si desidera conservare una copia dei messaggi di posta elettronica inoltrati. Se non vedi questa opzione, assicurati che all'account utente sia assegnata una licenza. Selezionare **Salva modifiche**.

    **Per inoltrare a più indirizzi di** posta elettronica, è possibile chiedere all'utente di configurare una regola in Outlook inoltrare agli indirizzi. 
    
    1.  Aprire **Regole home** di Outlook  >    >   **>** **Selezionare Gestisci regole & avvisi**
    1. Selezionare **Nuova regola** Selezionare Applica regola al messaggio ricevuto che si trova nella parte inferiore dell'elenco, quindi fare clic su  >   **Avanti.**
    1. Fare **clic su Sì** quando richiesto Questa regola verrà applicata a ogni messaggio ricevuto. 
    1. Nell'elenco successivo selezionare le azioni **reindirizzarlo a utenti o gruppi pubblici** e interrompere **l'elaborazione di altre regole**
    1. Fare clic sulla frase sottolineata **persone o gruppi pubblici** nella parte inferiore della finestra.
    1. Digitare **l'indirizzo di posta** elettronica a cui inoltrare la posta nel campo A, quindi fare clic su **OK.**
    1. Seleziona **Fine**
    

     Oppure, nell'interfaccia di amministrazione, crea un gruppo di [distribuzione,](add-user-or-contact-to-distribution-list.md)aggiungi gli indirizzi e quindi configura l'inoltro in modo che punti [alla](../setup/create-distribution-lists.md)DL usando le istruzioni in questo articolo.

5. Non eliminare l'account dell'utente che sta inoltrando o rimuovendo la licenza.  In caso contrario, l'inoltro della posta elettronica verrà interrotta.

::: moniker-end

::: moniker range="o365-germany"

1. Nell'interfaccia di amministrazione passare alla **pagina Utenti** \> **[utenti](https://go.microsoft.com/fwlink/p/?linkid=847686)** attivi.

2. Selezionare il nome dell'utente di cui si desidera inoltrare il messaggio di posta elettronica per aprire la pagina delle proprietà.

3. Espandere **Impostazioni posta** e quindi nella sezione Inoltro **posta** elettronica selezionare **Modifica.**

4. Nella pagina inoltro della posta elettronica, impostare l'interruttore su **Attivato,** immettere l'indirizzo di inoltro e scegliere se si desidera conservare una copia dei messaggi di posta elettronica inoltrati. Se non vedi questa opzione, assicurati che all'account utente sia assegnata una licenza. Selezionare **Salva**.

   **Per inoltrare a più indirizzi di** posta elettronica, è possibile chiedere all'utente di configurare una regola in Outlook inoltrare agli indirizzi. Per ulteriori informazioni, vedere [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).

   Oppure, nell'interfaccia di amministrazione, crea un gruppo di [distribuzione,](add-user-or-contact-to-distribution-list.md)aggiungi gli indirizzi e quindi configura l'inoltro in modo che punti [alla](../setup/create-distribution-lists.md)DL usando le istruzioni in questo articolo.

5. Non eliminare l'account dell'utente che sta inoltrando o rimuovendo la licenza.  In caso contrario, l'inoltro della posta elettronica verrà interrotta.

::: moniker-end

::: moniker range="o365-21vianet"

1. Nell'interfaccia di amministrazione passare alla **pagina Utenti** \> **[utenti](https://go.microsoft.com/fwlink/p/?linkid=850628)** attivi.

2. Selezionare il nome dell'utente di cui si desidera inoltrare il messaggio di posta elettronica per aprire la pagina delle proprietà.

3. Espandere **Impostazioni posta** e quindi nella sezione Inoltro **posta** elettronica selezionare **Modifica.**

4. Nella pagina inoltro della posta elettronica, impostare l'interruttore su **Attivato,** immettere l'indirizzo di inoltro e scegliere se si desidera conservare una copia dei messaggi di posta elettronica inoltrati. Se non vedi questa opzione, assicurati che all'account utente sia assegnata una licenza. Selezionare **Salva**.

   **Per inoltrare a più indirizzi di** posta elettronica, è possibile chiedere all'utente di configurare una regola in Outlook inoltrare agli indirizzi. Per ulteriori informazioni, vedere [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).

   Oppure, nell'interfaccia di amministrazione, crea un gruppo di [distribuzione,](add-user-or-contact-to-distribution-list.md)aggiungi gli indirizzi e quindi configura l'inoltro in modo che punti [alla](../setup/create-distribution-lists.md)DL usando le istruzioni in questo articolo.

5. Non eliminare l'account dell'utente che sta inoltrando o rimuovendo la licenza. In caso contrario, l'inoltro della posta elettronica verrà interrotta.

::: moniker-end

## <a name="related-content"></a>Contenuto correlato 

[Creare una cassetta postale condivisa](../email/create-a-shared-mailbox.md) (articolo)\
[Inviare messaggi di posta elettronica da un indirizzo diverso](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e) (articolo)\
[Modificare un nome utente e un indirizzo di posta elettronica](../add-users/change-a-user-name-and-email-address.md) (articolo)
