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
description: Potrebbero verificarsi errori durante la configurazione delle cassette postali condivise. Provare queste soluzioni se si verificano problemi con le cassette postali condivise.
ms.openlocfilehash: 89cdfbe29ab035b1eb6c3a0183629eef59d67477
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706131"
---
# <a name="resolve-issues-with-shared-mailboxes"></a>Risolvere i problemi relativi alle cassette postali condivise

Se vengono visualizzati messaggi di errore durante la creazione o l'utilizzo di una cassetta postale condivisa, provare queste possibili soluzioni. 

## <a name="error-when-creating-shared-mailboxes"></a>Errore durante la creazione di cassette postali condivise
<a name="bkmk_Fix"> </a>

Se viene visualizzato il messaggio di errore, l'indirizzo proxy "smtp:<shared mailbox name " è già utilizzato dagli indirizzi proxy o **\> LegacyExchangeDN di " \<name> ". Scegliere un altro indirizzo proxy** significa che si sta tentando di assegnare alla cassetta postale condivisa un nome già in uso. Ad esempio, supponiamo di voler assegnare a due cassette postali condivise i nomi info@dominio1 e info@dominio2. È possibile eseguire questa operazione in due modi:

  - Usare Windows PowerShell. Vedere questo post di blog per istruzioni: [Creare cassette postali condivise con lo stesso alias in domini diversi](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365)
    
  - Assegnare alla seconda cassetta postale condivisa un nome diverso dall'inizio per aggirare l'errore. Nell'interfaccia di amministrazione rinominare quindi la cassetta postale condivisa in base alle impostazioni desiderate.

## <a name="error-about-not-having-send-permissions-when-using-a-shared-mailbox"></a>Errore di non disporre delle autorizzazioni di invio quando si utilizza una cassetta postale condivisa

Se è stata creata una cassetta postale condivisa e quindi si tenta di inviare un messaggio da essa, è possibile ottenere quanto seguente:

**Impossibile inviare il messaggio. Non si dispone dell'autorizzazione per inviare il messaggio per conto dell'utente specificato.**

Questo messaggio viene visualizzato quando Microsoft 365 si verifica un problema di latenza di replica. Dovrebbe andare via tra circa un'ora, quando le informazioni sulla nuova cassetta postale condivisa (o sull'utente aggiunto) vengono replicate in tutti i data center. Attendere un'ora e quindi riprovare a inviare un messaggio.

## <a name="related-content"></a>Contenuto correlato

[Informazioni sulle cassette postali condivise](about-shared-mailboxes.md) (articolo)\
[Creare una cassetta postale condivisa](create-a-shared-mailbox.md) (articolo)\
[Configurare una cassetta postale condivisa](configure-a-shared-mailbox.md) (articolo)\
[Convertire una cassetta postale utente in una cassetta postale condivisa](convert-user-mailbox-to-shared-mailbox.md) (articolo)\
[Rimuovere una licenza da una cassetta postale condivisa](remove-license-from-shared-mailbox.md) (articolo)


    

