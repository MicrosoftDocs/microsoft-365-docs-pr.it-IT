---
title: Risolvere i problemi relativi alle cassette postali condivise
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Provare queste soluzioni se si verificano problemi con le cassette postali condivise.
ms.openlocfilehash: 5d6de9ac66b11f0e50b259cdca0b1bb50b8326ee
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400017"
---
# <a name="resolve-issues-with-shared-mailboxes"></a>Risolvere i problemi relativi alle cassette postali condivise

Se viene visualizzato un messaggio di errore durante la creazione o l'utilizzo di una cassetta postale condivisa, provare queste possibili soluzioni. 

## <a name="error-when-creating-shared-mailboxes"></a>Errore durante la creazione di cassette postali condivise
<a name="bkmk_Fix"> </a>

Se viene visualizzato il messaggio di errore, **l'indirizzo proxy "SMTP: <nome della cassetta postale condivisa \> " è già utilizzato dagli indirizzi proxy o legacyExchangeDN di " \<name> ". Scegliere un altro indirizzo proxy**, significa che si sta tentando di assegnare alla cassetta postale condivisa un nome già in uso. Ad esempio, supponiamo di voler assegnare a due cassette postali condivise i nomi info@dominio1 e info@dominio2. Questa operazione può essere eseguita in due modi:

  - Usare Windows PowerShell. Per istruzioni, vedere questo post di Blog: [creare cassette postali condivise con lo stesso alias in domini diversi](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365)
    
  - Denominare la seconda cassetta postale condivisa qualcosa di diverso dall'inizio per aggirare l'errore. Quindi, nell'interfaccia di amministrazione, rinominare la cassetta postale condivisa in quello che si vuole che sia.

## <a name="error-about-not-having-send-permissions-when-using-a-shared-mailbox"></a>Errore relativo all'utilizzo di autorizzazioni di invio quando si utilizza una cassetta postale condivisa

Se è stata creata una cassetta postale condivisa e quindi si tenta di inviare un messaggio, è possibile che venga visualizzato quanto segue:

**Non è stato possibile inviare il messaggio. Non si dispone dell'autorizzazione per l'invio del messaggio per conto dell'utente specificato.**

Questo messaggio viene visualizzato quando si verifica un problema di latenza della replica in Microsoft 365. Se le informazioni sulla nuova cassetta postale condivisa (o aggiunta di un utente) vengono replicate in tutti i Data Center, il testo dovrebbe scomparire tra un'ora. Attendere un'ora e quindi riprovare per inviare un messaggio.

## <a name="related-articles"></a>Articoli correlati

[Informazioni sulle cassette postali condivise](about-shared-mailboxes.md)

[Creare una cassetta postale condivisa](create-a-shared-mailbox.md)

[Configurare una cassetta postale condivisa](configure-a-shared-mailbox.md)

[Convertire una cassetta postale utente in una cassetta postale condivisa](convert-user-mailbox-to-shared-mailbox.md)

[Rimuovere una licenza da una cassetta postale condivisa](remove-license-from-shared-mailbox.md)


    

