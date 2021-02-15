---
title: Convertire una cassetta postale utente in una cassetta postale condivisa
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 2e122487-e1f5-4f26-ba41-5689249d93ba
description: 'Informazioni su come convertire una cassetta postale privata in una cassetta postale condivisa accessibile da più utenti. '
ms.openlocfilehash: f716bbd16be9f67189b19358ddf16a289f57f8e7
ms.sourcegitcommit: a8f3c633714e934f9ad026c3bc72157ed535dcfc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/29/2020
ms.locfileid: "49737966"
---
# <a name="convert-a-user-mailbox-to-a-shared-mailbox"></a>Convertire una cassetta postale utente in una cassetta postale condivisa

Quando si converte la cassetta postale di un utente in cassetta condivisa, vengono mantenuti tutti gli elementi di posta elettronica e del calendario esistenti. L'unica differenza è che ora si trovano in una cassetta postale condivisa, cui potranno accedere diversi utenti invece di uno solo. In un secondo momento, è possibile riconvertire una cassetta postale condivisa in una cassetta postale utente (privata).

**Ecco alcune cose molto importanti che devi sapere:**

- La cassetta postale utente che si sta convertendo necessita di una licenza assegnata prima di convertirla in una cassetta postale condivisa. In caso contrario, l'opzione per convertire la cassetta postale non sarà visualizzata. Se la licenza è stata rimossa, aggiungerla di nuovo in modo da poter convertire la cassetta postale. Dopo aver convertito la cassetta postale in una condivisa, è possibile rimuovere la licenza dall'account dell'utente.

- Le cassette postali condivise possono avere fino a 50 GB di dati senza una licenza assegnata. Perché possano contenere ancora più dati, è necessario assegnarvi una licenza. Potrebbe essere necessario eliminare diversi messaggi di posta elettronica di grandi dimensioni, ad esempio quelli con allegati, dalla cassetta postale condivisa per ridurne le dimensioni e rimuovere la licenza.

- Non eliminare il vecchio account utente. Sarà necessario per l'ancoraggio della cassetta postale condivisa. Se l'account utente è già stato eliminato, vedere [Convertire la cassetta postale di un utente eliminato](#convert-the-mailbox-of-a-deleted-user).

- Le regole sono intatte dopo la conversione della cassetta postale in una cassetta postale condivisa.

## <a name="use-the-exchange-admin-center-to-convert-a-mailbox"></a>Utilizzare l'interfaccia di amministrazione di Exchange per convertire una cassetta postale
 
1. Accedere all'<a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">interfaccia di amministrazione di Exchange</a>.

2. Selezionare **Cassette postali** dei \> **destinatari.**

3. Selezionare la cassetta postale utente. In **Converti in cassetta postale condivisa** selezionare **Converti.**

4. Se la cassetta postale è inferiore a 50 GB, è possibile rimuovere la licenza dall'utente [e](../manage/remove-licenses-from-users.md)smettere di pagarla. Non eliminare l'account dell'utente. Sarà necessaria come ancoraggio per la cassetta postale condivisa. Se si sta convertendo la cassetta postale di un dipendente che lascia l'organizzazione, è consigliabile eseguire ulteriori operazioni per assicurarsi che non siano più in grado di accedere. Vedere [Rimuovere un ex dipendente da Microsoft 365.](../add-users/remove-former-employee.md)
    
> [!NOTE]
> Non è necessario reimpostare la password dell'utente durante la conversione della cassetta postale. Tuttavia, se la password non viene reimpostata, il nome utente e la password originali **continuano** a funzionare al termine della conversione della cassetta postale.

Per tutte le altre informazioni necessarie sulle cassette postali condivise, vedere [Informazioni sulle cassette postali condivise](about-shared-mailboxes.md) e Creare una cassetta postale [condivisa.](create-a-shared-mailbox.md)

> [!NOTE]
> Le cassette postali condivise non richiedono una licenza separata. Tuttavia, se si desidera attivare un'archiviazione sul posto oppure sottoporre una cassetta postale a blocco sul posto o blocco per controversia legale, è necessario assegnare alla cassetta postale una licenza di Exchange Online, piano 1 con Archiviazione Exchange Online o Exchange Online, piano 2.


## <a name="convert-the-mailbox-of-a-deleted-user"></a>Convertire la cassetta postale di un utente eliminato

Si supponga di aver eliminato un account utente e di volerne convertire la vecchia cassetta postale in cassetta postale condivisa. Ecco cosa fare:

1. [Ripristinare l'account dell'utente.](../add-users/restore-user.md)

2. Assicurarsi che sia assegnata una licenza di Microsoft 365.

3. Reimpostare la password dell'utente.
    
4. Attendere 20-30 minuti perché la cassetta postale venga ricreata.
    
5. Seguire ora le istruzioni in questa pagina per convertire la cassetta postale dell'account utente in cassetta postale condivisa.
    
6. Al termine, è possibile rimuovere la licenza dalla cassetta postale dell'utente. Non eliminare la vecchia cassetta postale dell'utente. Sarà necessaria come ancoraggio per la cassetta postale condivisa.
    
7. Aggiungere membri alla cassetta postale condivisa.


## <a name="convert-a-shared-mailbox-back-to-a-users-private-mailbox"></a>Riconvertire una cassetta postale condivisa in una cassetta postale (privata) dell'utente

1. Accedere all'<a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">interfaccia di amministrazione di Exchange</a>.
   
2. Selezionare **Destinatari** \> **condivisi.**

3. Selezionare la cassetta postale condivisa. In **Converti in cassetta postale normale** selezionare **Converti.**

4. Tornare all'interfaccia di amministrazione. In **Utenti** scegliere l'account utente associato alla vecchia cassetta postale utente. Assegnare una licenza all'account e reimpostare la password.

   Saranno necessari alcuni minuti prima che la cassetta postale venga configurata, ma al termine, l'utente che usa l'account sarà pronto per iniziare. All'accesso, l'utente visualizzerà gli elementi di posta elettronica e del calendario che erano presenti nella cassetta postale condivisa.

## <a name="convert-a-users-mailbox-in-a-hybrid-environment"></a>Convertire la cassetta postale di un utente in un ambiente ibrido

Per ulteriori informazioni sulla conversione di una cassetta postale utente in una cassetta postale condivisa in un ambiente ibrido di Exchange, vedere:

 - [Cmdlet per creare o modificare una cassetta postale condivisa remota in un ambiente Exchange locale](https://support.microsoft.com/office/cmdlets-to-create-or-modify-a-remote-shared-mailbox-in-an-on-premises-exchange-environment-9e83fb59-c001-729c-a4c0-b2964c154b49)
 - [Le cassette postali condivise vengono convertite in modo imprevisto in cassette postali utente dopo l'esecuzione della sincronizzazione della directory in una distribuzione ibrida di Exchange](https://docs.microsoft.com/exchange/troubleshoot/user-and-shared-mailboxes/shared-mailboxes-unexpectedly-converted-to-user-mailboxes)
 

> [!NOTE]
> Se si è membri del gruppo di ruoli Gestione organizzazione o Gestione destinatari, è possibile utilizzare Exchange Management Shell per modificare una cassetta postale utente in una cassetta postale condivisa locale. Ad esempio, `Set-Mailbox -Identity mailbox1@contoso.com -Type Shared`.

## <a name="related-articles"></a>Articoli correlati

[Informazioni sulle cassette postali condivise](about-shared-mailboxes.md)

[Creare una cassetta postale condivisa](create-a-shared-mailbox.md)

[Configurare una cassetta postale condivisa](configure-a-shared-mailbox.md)

[Rimuovere una licenza da una cassetta postale condivisa](remove-license-from-shared-mailbox.md)

[Risolvere i problemi relativi alle cassette postali condivise](resolve-issues-with-shared-mailboxes.md)
