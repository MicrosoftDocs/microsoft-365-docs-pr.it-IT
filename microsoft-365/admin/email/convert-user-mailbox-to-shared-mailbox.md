---
title: Convertire una cassetta postale utente in una cassetta postale condivisa
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 2e122487-e1f5-4f26-ba41-5689249d93ba
description: 'Informazioni su come convertire una cassetta postale privata in una cassetta postale condivisa a cui è possibile accedere da più utenti. '
ms.openlocfilehash: 7e652dc77218be44caa56515e4b21efb692cbaa3
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43628892"
---
# <a name="convert-a-user-mailbox-to-a-shared-mailbox"></a>Convertire una cassetta postale utente in una cassetta postale condivisa

Quando si converte la cassetta postale di un utente in cassetta condivisa, vengono mantenuti tutti gli elementi di posta elettronica e del calendario esistenti. L'unica differenza è che ora si trovano in una cassetta postale condivisa, cui potranno accedere diversi utenti invece di uno solo. In un secondo momento, è possibile convertire una cassetta postale condivisa di nuovo in una cassetta postale utente (privata).

**Di seguito sono riportate alcune informazioni importanti che è necessario conoscere:**

- La cassetta postale utente che si sta convertendo richiede una licenza assegnata prima di convertirla in una cassetta postale condivisa. In caso contrario, l'opzione per convertire la cassetta postale non sarà visualizzata. Se la licenza è stata rimossa, aggiungerla di nuovo in modo da poter convertire la cassetta postale. Dopo aver convertito la cassetta postale in una condivisa, è possibile rimuovere la licenza dall'account dell'utente.

- Le cassette postali condivise possono contenere fino a 50 GB di dati senza alcuna licenza assegnata. Perché possano contenere ancora più dati, è necessario assegnarvi una licenza. Potrebbe essere necessario eliminare diversi messaggi di posta elettronica di grandi dimensioni, ad esempio quelli con allegati, dalla cassetta postale condivisa per ridurne le dimensioni e rimuovere la licenza.

- Non eliminare il vecchio account utente. Sarà necessario per l'ancoraggio della cassetta postale condivisa. Se l'account utente è già stato eliminato, vedere [Convertire la cassetta postale di un utente eliminato](#convert-the-mailbox-of-a-deleted-user).

- Le regole sono intatte dopo la conversione della cassetta postale in una cassetta postale condivisa.

## <a name="use-the-exchange-admin-center-to-convert-a-mailbox"></a>Utilizzare l'interfaccia di amministrazione di Exchange per convertire una cassetta postale
 
1. Accedere all'<a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">interfaccia di amministrazione di Exchange</a>.

2. Selezionare le **cassette postali** **destinatari** \> .

3. Selezionare la cassetta postale utente. In **Converti in cassetta postale condivisa**, selezionare **Converti**.

4. Se la cassetta postale è più piccola di 50 GB, è possibile rimuovere la [licenza dall'utente](../manage/remove-licenses-from-users.md) e smettere di pagarne i costi associati. Non eliminare la vecchia cassetta postale dell'utente. Sarà necessaria come ancoraggio per la cassetta postale condivisa. Se si converte la cassetta postale di un dipendente che lascia l'organizzazione, è necessario eseguire ulteriori passaggi per verificare che non siano più in grado di eseguire l'accesso. Per ulteriori informazioni, vedere [rimuovere un ex dipendente da Microsoft 365](../add-users/remove-former-employee.md).
    
5. Per tutti gli altri elementi necessari per conoscere le cassette postali condivise, vedere [informazioni sulle cassette postali condivise](about-shared-mailboxes.md) e [creare una cassetta postale condivisa](create-a-shared-mailbox.md).

## <a name="use-the-microsoft-365-admin-center-to-convert-a-mailbox"></a>Utilizzare l'interfaccia di amministrazione di Microsoft 365 per convertire una cassetta postale

::: moniker range="o365-worldwide"

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.

2. Selezionare il nome dell'utente di cui si desidera convertire la cassetta postale.

3. Reimpostare la password dell'utente.

> [!NOTE]
> Non è necessario reimpostare la password dell'utente durante la conversione delle cassette postali. Tuttavia, se la password non viene reimpostata, **il nome utente e la password originali continuano a funzionare** dopo che la conversione della cassetta postale è terminata.

4. Nella scheda **posta** , in **altre azioni**, selezionare **Converti in cassetta postale condivisa**. 

::: moniker-end

::: moniker range="o365-germany"

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Utenti attivi</a>.

2. Selezionare l'utente di cui si desidera convertire la cassetta postale.

3. Nel riquadro destro espandere Impostazioni di **posta elettronica**. Accanto a **altre impostazioni**, selezionare **Converti in cassetta postale condivisa**.

::: moniker-end

::: moniker range="o365-21vianet"

1. Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Utenti attivi</a>.

2. Selezionare l'utente di cui si desidera convertire la cassetta postale.

3. Nel riquadro destro espandere Impostazioni di **posta elettronica**. Accanto a **altre impostazioni**, selezionare **Converti in cassetta postale condivisa**.

::: moniker-end


Se la cassetta postale è più piccola di 50 GB, è possibile [rimuovere la licenza dall'utente](../manage/remove-licenses-from-users.md)e smettere di pagarla. Non eliminare la vecchia cassetta postale dell'utente. Sarà necessaria come ancoraggio per la cassetta postale condivisa. Se si converte la cassetta postale di un dipendente che lascia l'organizzazione, è necessario eseguire ulteriori passaggi per verificare che non siano più in grado di eseguire l'accesso. Vedere [rimuovere un ex dipendente da Microsoft 365](../add-users/remove-former-employee.md).
    
Per tutti gli altri elementi necessari per conoscere le cassette postali condivise, vedere [informazioni sulle cassette postali condivise](about-shared-mailboxes.md) e [creare una cassetta postale condivisa](create-a-shared-mailbox.md).


## <a name="convert-the-mailbox-of-a-deleted-user"></a>Convertire la cassetta postale di un utente eliminato

Si supponga di aver eliminato un account utente e di volerne convertire la vecchia cassetta postale in cassetta postale condivisa. Ecco cosa fare:

1. [Ripristinare l'account dell'utente](../add-users/restore-user.md).

2. Assicurarsi che sia assegnata una licenza di Microsoft 365.

3. Reimpostare la password dell'utente.
    
4. Attendere 20-30 minuti perché la cassetta postale venga ricreata.
    
5. Seguire ora le istruzioni in questa pagina per convertire la cassetta postale dell'account utente in cassetta postale condivisa.
    
6. Al termine, è possibile rimuovere la licenza dalla cassetta postale dell'utente. Non eliminare la vecchia cassetta postale dell'utente. Sarà necessaria come ancoraggio per la cassetta postale condivisa.
    
7. Aggiungere membri alla cassetta postale condivisa.

## <a name="convert-a-shared-mailbox-back-to-a-users-private-mailbox"></a>Convertire di nuovo una cassetta postale condivisa in una cassetta postale (privata) dell'utente

1. Accedere all'<a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">interfaccia di amministrazione di Exchange</a>.
   
2. Selezionare i **destinatari** \> **condivisi**.

3. Selezionare la cassetta postale condivisa. In **Converti in cassetta postale normale**selezionare **Converti**.

4. Tornare all'interfaccia di amministrazione. In **Utenti** scegliere l'account utente associato alla vecchia cassetta postale utente. Assegnare una licenza all'account e reimpostare la password.

   Saranno necessari alcuni minuti prima che la cassetta postale venga configurata, ma al termine, l'utente che usa l'account sarà pronto per iniziare. All'accesso, l'utente visualizzerà gli elementi di posta elettronica e del calendario che erano presenti nella cassetta postale condivisa.

## <a name="convert-a-users-mailbox-in-a-hybrid-environment"></a>Convertire la cassetta postale di un utente in un ambiente ibrido

Se questa cassetta postale condivisa si trova in un ambiente ibrido, è **consigliabile** (è quasi necessario) riportare la cassetta postale dell'utente in locale, convertire la cassetta postale utente in una cassetta postale condivisa e quindi riportare la cassetta postale condivisa nel cloud.

Ecco perché: se si converte la cassetta postale nel cloud, è possibile convertirla, ma la cassetta postale è ancora in uso, in quanto la nuova realtà non viene sincronizzata di nuovo in locale.

In genere, non si tratta di un problema, ma ci sono alcuni scenari in cui gli attributi locali (che pensano che la cassetta postale è la cassetta postale dell'utente) possono sovrascrivere le nuove versioni cloud di tali attributi e, di conseguenza, la cassetta postale potrebbe riconvertirsi. Questo è un problema perché le cassette postali degli utenti richiedono licenze **o sono eliminate temporaneamente dopo 30 giorni**.

Sono state affrontate la maggior parte dei motivi per cui questo accade ma può comunque verificarsi, anche se raramente. È consigliabile essere sicuri e riportare la cassetta postale in locale.

> [!NOTE]
> Se si è parte di gestione organizzazione o Gestione destinatari, è possibile utilizzare Exchange Management Shell per modificare una cassetta postale utente in una cassetta postale condivisa locale. Ad esempio, `Set-Mailbox -Identity mailbox1@contoso.onmicrosoft.com -Type Shared`.

> [!TIP]
> Per le istanze in cui le [cassette postali condivise sono inaspettatamente convertite nelle cassette postali degli utenti](https://support.microsoft.com/help/2710029/shared-mailboxes-are-unexpectedly-converted-to-user-mailboxes-after-di) , vedere la soluzione alternativa
  
## <a name="related-articles"></a>Articoli correlati

[Informazioni sulle cassette postali condivise](about-shared-mailboxes.md)

[Creare una cassetta postale condivisa](create-a-shared-mailbox.md)

[Configurare una cassetta postale condivisa](configure-a-shared-mailbox.md)

[Rimuovere una licenza da una cassetta postale condivisa](remove-license-from-shared-mailbox.md)

[Risolvere i problemi relativi alle cassette postali condivise](resolve-issues-with-shared-mailboxes.md)
