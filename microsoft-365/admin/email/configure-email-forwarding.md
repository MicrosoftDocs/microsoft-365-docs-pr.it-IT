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
description: Configurare l'inoltro della posta elettronica a uno o più account di posta elettronica tramite Office365.
ms.openlocfilehash: cdefab3df59f1c57abbc221943b58c978ff582a9
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51050715"
---
# <a name="configure-email-forwarding-in-microsoft-365"></a>Configurare l'inoltro della posta elettronica in Microsoft 365

::: moniker range="o365-21vianet"

> [!NOTE]
> L'interfaccia di amministrazione sta cambiando. Se alcuni dettagli non corrispondono a quelli presentati qui, vedere [Informazioni sulla nuova interfaccia di amministrazione di Microsoft 365](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).

::: moniker-end

L'amministratore di un'organizzazione potrebbe avere requisiti aziendali per configurare l'inoltro della posta elettronica per la cassetta postale di un utente. L'inoltro della posta elettronica consente di inoltrare i messaggi inviati alla cassetta postale di un utente a quella di un altro utente all'interno o all'esterno dell'organizzazione.

> [!IMPORTANT]
> È possibile utilizzare i criteri di filtro della posta indesiderata in uscita per controllare l'inoltro automatico ai destinatari esterni. Per ulteriori informazioni, vedere [Control automatic external email forwarding in Microsoft 365](https://docs.microsoft.com/microsoft-365/security/defender-365-security/external-email-forwarding?view=o365-worldwide&preserve-view=true#how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls).

## <a name="configure-email-forwarding"></a>Configurare l'inoltro della posta elettronica

Prima di configurare l'inoltro della posta elettronica, tenere presente quanto segue:

- Dopo aver configurato l'inoltro della posta elettronica, **verranno** inoltrati solo i nuovi messaggi di posta elettronica inviati alla cassetta postale di origine. 

- L'inoltro della posta elettronica richiede che  *l'account from*  abbia una licenza. Se si sta configurando l'inoltro della posta elettronica perché l'utente ha lasciato l'organizzazione, un'altra opzione è convertire la cassetta postale [in una cassetta postale condivisa.](convert-user-mailbox-to-shared-mailbox.md) In questo modo diverse persone possono accedervi. Tuttavia, una cassetta postale condivisa non può superare i 50 GB.

Per eseguire questa procedura, è necessario essere un amministratore di Exchange o un amministratore globale in Microsoft 365. Per ulteriori informazioni, vedere l'argomento [Informazioni sui ruoli di amministratore.](../add-users/about-admin-roles.md)

::: moniker range="o365-worldwide"

1. Nell'interfaccia di amministrazione passare alla **pagina Utenti** \> **[utenti](https://go.microsoft.com/fwlink/p/?linkid=834822)** attivi.

2. Selezionare il nome dell'utente di cui si desidera inoltrare il messaggio di posta elettronica per aprire la pagina delle proprietà.

3. Nella scheda **Posta** selezionare Gestisci **inoltro posta elettronica**.

4. Nella pagina inoltro della posta elettronica, selezionare Inoltra tutti i messaggi di posta elettronica inviati a questa cassetta **postale,** immettere l'indirizzo di inoltro e scegliere se si desidera conservare una copia dei messaggi di posta elettronica inoltrati. Se non vedi questa opzione, assicurati che all'account utente sia assegnata una licenza. Selezionare **Salva modifiche**.

    **Per inoltrare a più indirizzi di** posta elettronica, è possibile chiedere all'utente di configurare una regola in Outlook per l'inoltro agli indirizzi. Per ulteriori informazioni, vedere [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).

     Oppure, nell'interfaccia di amministrazione, crea un gruppo di [distribuzione,](add-user-or-contact-to-distribution-list.md)aggiungi gli indirizzi e quindi configura l'inoltro in modo che punti [alla](../setup/create-distribution-lists.md)DL usando le istruzioni in questo articolo.

5. Non eliminare l'account dell'utente che sta inoltrando o rimuovendo la licenza.  In caso contrario, l'inoltro della posta elettronica verrà interrotta.

::: moniker-end

::: moniker range="o365-germany"

1. Nell'interfaccia di amministrazione passare alla **pagina Utenti** \> **[utenti](https://go.microsoft.com/fwlink/p/?linkid=847686)** attivi.

2. Selezionare il nome dell'utente di cui si desidera inoltrare il messaggio di posta elettronica per aprire la pagina delle proprietà.

3. Espandere **Impostazioni posta** e quindi nella sezione Inoltro **posta** elettronica selezionare **Modifica.**

4. Nella pagina inoltro della posta elettronica, impostare l'interruttore su **Attivato,** immettere l'indirizzo di inoltro e scegliere se si desidera conservare una copia dei messaggi di posta elettronica inoltrati. Se non vedi questa opzione, assicurati che all'account utente sia assegnata una licenza. Selezionare **Salva**.

   **Per inoltrare a più indirizzi di** posta elettronica, è possibile chiedere all'utente di configurare una regola in Outlook per l'inoltro agli indirizzi. Per ulteriori informazioni, vedere [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).

   Oppure, nell'interfaccia di amministrazione, crea un gruppo di [distribuzione,](add-user-or-contact-to-distribution-list.md)aggiungi gli indirizzi e quindi configura l'inoltro in modo che punti [alla](../setup/create-distribution-lists.md)DL usando le istruzioni in questo articolo.

5. Non eliminare l'account dell'utente che sta inoltrando o rimuovendo la licenza.  In caso contrario, l'inoltro della posta elettronica verrà interrotta.

::: moniker-end

::: moniker range="o365-21vianet"

1. Nell'interfaccia di amministrazione passare alla **pagina Utenti** \> **[utenti](https://go.microsoft.com/fwlink/p/?linkid=850628)** attivi.

2. Selezionare il nome dell'utente di cui si desidera inoltrare il messaggio di posta elettronica per aprire la pagina delle proprietà.

3. Espandere **Impostazioni posta** e quindi nella sezione Inoltro **posta** elettronica selezionare **Modifica.**

4. Nella pagina inoltro della posta elettronica, impostare l'interruttore su **Attivato,** immettere l'indirizzo di inoltro e scegliere se si desidera conservare una copia dei messaggi di posta elettronica inoltrati. Se non vedi questa opzione, assicurati che all'account utente sia assegnata una licenza. Selezionare **Salva**.

   **Per inoltrare a più indirizzi di** posta elettronica, è possibile chiedere all'utente di configurare una regola in Outlook per l'inoltro agli indirizzi. Per ulteriori informazioni, vedere [Use rules to automatically forward messages](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).

   Oppure, nell'interfaccia di amministrazione, crea un gruppo di [distribuzione,](add-user-or-contact-to-distribution-list.md)aggiungi gli indirizzi e quindi configura l'inoltro in modo che punti [alla](../setup/create-distribution-lists.md)DL usando le istruzioni in questo articolo.

5. Non eliminare l'account dell'utente che sta inoltrando o rimuovendo la licenza.  In caso contrario, l'inoltro della posta elettronica verrà interrotta.

::: moniker-end