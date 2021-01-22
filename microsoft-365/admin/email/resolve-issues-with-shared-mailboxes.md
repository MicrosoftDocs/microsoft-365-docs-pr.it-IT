---
title: Risolvere i problemi relativi alle cassette postali condivise
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
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
description: Provare queste soluzioni se si verificano problemi con le cassette postali condivise.
ms.openlocfilehash: ba62db76edff6e4ab3d738ed0af8db2a40c18394
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926487"
---
# <a name="resolve-issues-with-shared-mailboxes"></a>Risolvere i problemi relativi alle cassette postali condivise

Se vengono visualizzati messaggi di errore durante la creazione o l'utilizzo di una cassetta postale condivisa, provare queste possibili soluzioni. 

## <a name="error-when-creating-shared-mailboxes"></a>Errore durante la creazione di cassette postali condivise
<a name="bkmk_Fix"> </a>

Se viene visualizzato il messaggio di errore, l'indirizzo proxy "smtp:<shared mailbox name " è già utilizzato dagli indirizzi proxy o **\> LegacyExchangeDN di " \<name> ". Scegliere un altro indirizzo proxy,** significa che si sta tentando di assegnare alla cassetta postale condivisa un nome già in uso. Ad esempio, supponiamo di voler assegnare a due cassette postali condivise i nomi info@dominio1 e info@dominio2. Questa operazione può essere eseguita in due modi:

  - Usare Windows PowerShell. Vedere questo post di blog per istruzioni: [Creare cassette postali condivise con lo stesso alias in domini diversi](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365)
    
  - Assegnare alla seconda cassetta postale condivisa un nome diverso dall'inizio per aggirare l'errore. Quindi, nell'interfaccia di amministrazione, rinominare la cassetta postale condivisa in quello che si desidera.

## <a name="error-about-not-having-send-permissions-when-using-a-shared-mailbox"></a>Errore di non disporre delle autorizzazioni di invio quando si utilizza una cassetta postale condivisa

Se è stata creata una cassetta postale condivisa e quindi si tenta di inviare un messaggio da essa, è possibile che venga visualizzato questo messaggio:

**Impossibile inviare il messaggio. Non si dispone dell'autorizzazione per inviare il messaggio per conto dell'utente specificato.**

Questo messaggio viene visualizzato quando si verifica un problema di latenza di replica in Microsoft 365. Dovrebbe andare via tra circa un'ora, quando le informazioni sulla nuova cassetta postale condivisa (o sull'utente aggiunto) vengono replicate in tutti i data center. Attendere un'ora e quindi riprovare a inviare un messaggio.

## <a name="related-articles"></a>Articoli correlati

[Informazioni sulle cassette postali condivise](about-shared-mailboxes.md)

[Creare una cassetta postale condivisa](create-a-shared-mailbox.md)

[Configurare una cassetta postale condivisa](configure-a-shared-mailbox.md)

[Convertire una cassetta postale utente in una cassetta postale condivisa](convert-user-mailbox-to-shared-mailbox.md)

[Rimuovere una licenza da una cassetta postale condivisa](remove-license-from-shared-mailbox.md)


    

