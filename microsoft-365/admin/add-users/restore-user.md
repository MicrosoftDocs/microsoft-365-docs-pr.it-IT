---
title: Ripristinare un utente
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
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 2c261e42-5dd1-48b0-845f-2a016d29cfc1
description: Informazioni su come ripristinare gli account utente eliminati e tutti i dati associati.
ms.openlocfilehash: 9cdc4100f963ed450b50caa0f07a3863bc87992d
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244033"
---
# <a name="restore-a-user"></a>Ripristinare un utente
   
Se si ripristina un account utente entro 30 giorni dalla sua eliminazione, vengono ripristinati l'account stesso e tutti i dati associati. L'utente può accedere con lo stesso account aziendale o dell'istituto di istruzione. La cassetta postale dell'utente verrà completamente ripristinata. Per scoprire quanto tempo rimane prima che non sia più possibile ripristinare un account utente specifico, [contattare il supporto tecnico](../contact-support-for-business-products.md).
  
Ecco un paio di suggerimenti:
  
- Assicurati che le licenze siano disponibili per l'assegnazione all'account.
    
- Se l'azienda usa Active Directory, vedere [Risoluzione dei problemi relativi agli account utente eliminati in Office 365](/office365/troubleshoot/active-directory/restore-deleted-user-accounts.md) per istruzioni sul ripristino di un account utente. 
    
## <a name="restore-one-or-more-user-accounts"></a>Ripristinare uno o più account utente

Per eseguire questa procedura, Microsoft 365 amministratore globale o amministratore di gestione utenti. 

1. Nell'interfaccia di amministrazione passare alla **pagina Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">utenti eliminati.</a>

2. Nella pagina **Utenti eliminati** selezionare i nomi degli utenti che si desidera ripristinare e quindi selezionare **Ripristina**.
    
3. Seguire le istruzioni visualizzate per impostare la password e quindi selezionare **Ripristina**.
    
4. Se l'utente viene ripristinato correttamente, selezionare **Invia messaggio di posta elettronica e chiudi**. Se si riscontra un conflitto tra nomi o indirizzi proxy, vedere le istruzioni di seguito per ripristinare questi account.
    
Dopo aver ripristinato un utente, assicurati di avvisarlo che la password è cambiata e di seguirli.
  
## <a name="restore-a-user-that-has-a-user-name-conflict"></a>Ripristinare un utente con conflitto relativo al nome utente

I conflitti relativi al nome utente si verificano quando l'amministratore elimina un account utente, ne crea uno nuovo con lo stesso nome utente (per lo stesso utente o per un altro utente con nome simile) e successivamente cerca di ripristinare l'account eliminato.
  
Per risolvere i conflitti di questo tipo, sostituire l'account utente attivo con quello da ripristinare oppure assegnare un altro nome utente a quest'ultimo account, in modo da evitare che esistano due account con lo stesso nome utente. Ecco come fare.

1. Nell'interfaccia di amministrazione passare alla **pagina Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">utenti eliminati.</a>
  
2. Nella pagina **Utenti eliminati** selezionare i nomi degli utenti che si desidera ripristinare e quindi selezionare **Ripristina**.
    
    > [!NOTE]
    > Se non si riesce a ripristinare due o più utenti, verrà visualizzato un messaggio di errore che comunica che l'operazione di ripristino non è riuscita per alcuni utenti. Per sapere quali utenti non sono stati ripristinati, visualizzare il log. Gli account che non è stato possibile ripristinare dovranno essere ripristinati uno alla volta. 
  
3. Seguire le istruzioni visualizzate per impostare la password e selezionare **Ripristina**.
    
4. Un messaggio popup informa che si è verificato un problema durante il ripristino dell'account. Eseguire una delle operazioni seguenti:
    
  - Annullare il ripristino e rinominare l'utente attivo corrente. Provare quindi a eseguire di nuovo il ripristino.
    
  - OPPURE, digitare un nuovo indirizzo di posta elettronica principale per l'utente e selezionare **Ripristina**.
    
5. Esaminare i risultati e quindi scegliere **Chiudi**.
    
## <a name="restore-a-user-that-has-a-proxy-address-conflict"></a>Ripristinare un utente che ha un conflitto tra indirizzi proxy

I conflitti relativi all'indirizzo proxy si verificano quando l'amministratore elimina un account utente contenente un indirizzo proxy, assegna lo stesso indirizzo proxy a un altro account, quindi cerca di ripristinare l'account eliminato. Eseguire la procedura seguente per risolvere il problema.
  
A tale [scopo,](about-admin-roles.md) è necessario disporre Microsoft 365 autorizzazioni di amministratore. 

1. Nell'interfaccia di amministrazione passare alla **pagina Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2071581" target="_blank">utenti eliminati.</a>

2. Nella pagina **Utenti eliminati** selezionare l'utente da ripristinare e quindi scegliere **Ripristina**. 
    
3. Nella pagina **Ripristina** seguire le istruzioni per impostare la password e selezionare **Ripristina**. Gli eventuali indirizzi proxy in conflitto vengono rimossi automaticamente dall'utente che si sta ripristinando.
    
4. Esaminare i risultati e quindi scegliere **Chiudi**.

## <a name="related-articles"></a>Articoli correlati

[Eliminare un utente](delete-a-user.md)
