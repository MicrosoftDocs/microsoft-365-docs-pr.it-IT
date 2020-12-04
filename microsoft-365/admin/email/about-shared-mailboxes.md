---
title: Informazioni sulle cassette postali condivise
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
search.appverid:
- BCS160
- MET150
- MOE150
description: Le cassette postali condivise vengono utilizzate quando più persone devono accedere alla stessa cassetta postale. Informazioni su ciò che è necessario sapere prima di creare una cassetta postale condivisa.
ms.openlocfilehash: cc94ae30edcc7a8307328230989dc4a883732b0e
ms.sourcegitcommit: 7e003ee0a06f61bfb9f80441c3479fa3148afafe
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/03/2020
ms.locfileid: "49568295"
---
# <a name="about-shared-mailboxes"></a>Informazioni sulle cassette postali condivise

Le cassette postali condivise vengono usate quando più persone devono accedere alla stessa cassetta postale, ad esempio un'informazione aziendale o un indirizzo di posta elettronica di supporto, una reception o un'altra funzione che potrebbe essere condivisa da più persone.

Gli utenti che dispongono delle autorizzazioni per la cassetta postale del gruppo possono inviare o inviare per conto dell'indirizzo di posta elettronica della cassetta postale, se l'amministratore ha concesso tali autorizzazioni. Questa funzione è particolarmente utile per le cassette postali dell'assistenza e del supporto, perché gli utenti possono inviare messaggi di posta elettronica dal "supporto tecnico Contoso" o dalla "reception dell'edificio A".

Prima [di creare una cassetta postale condivisa](create-a-shared-mailbox.md), ecco alcuni aspetti da sapere:

- **Licenze:** La cassetta postale condivisa può archiviare fino a 50 GB di dati senza che sia stata assegnata una licenza. Per volumi più elevati, è necessario assegnare una licenza alla cassetta postale per archiviare più dati. Per ulteriori informazioni sulla gestione delle licenze per le cassette postali condivise, vedere [limiti di Exchange Online](https://technet.microsoft.com/library/exchange-online-limits.aspx#StorageLimits). Dopo che la cassetta postale condivisa raggiunge il limite di archiviazione, per un certo periodo sarà possibile ricevere messaggi di posta elettronica, ma non inviarli. Trascorso quel periodo anche la ricezione verrà disabilitata. I mittenti dei messaggi riceveranno un rapporto di mancato recapito.

- **Autorizzazioni utente:** È necessario fornire agli utenti le autorizzazioni per l'utilizzo della cassetta postale condivisa. Solo le persone interne all'organizzazione possono usare una cassetta postale condivisa.

- **Utenti esterni:** Non è possibile concedere agli utenti esterni alla propria azienda (ad esempio persone con un account Gmail) l'accesso alla cassetta postale condivisa. Se si vuole farlo comunque, è consigliabile creare un gruppo di Outlook. Per ulteriori informazioni, vedere [creare un gruppo di Microsoft 365 nell'](../create-groups/create-groups.md)interfaccia di amministrazione.

- **Utilizzo con Outlook:** Oltre a utilizzare Outlook sul Web dal browser per accedere alle cassette postali condivise, è anche possibile usare l'app Outlook per iOS o l'app Outlook per Android. Per ulteriori informazioni, vedere [aggiungere una cassetta postale condivisa a Outlook Mobile](https://support.microsoft.com/office/f866242c-81b2-472e-8776-6c49c5473c9f). Un'altra opzione consiste nel creare un gruppo per la cassetta postale condivisa. Per ulteriori informazioni, vedere [confronto di gruppi](../create-groups/compare-groups.md).

- **Crittografia:** Non è possibile crittografare la posta elettronica inviata da una cassetta postale condivisa. Ciò è dovuto al fatto che una cassetta postale condivisa non dispone di un proprio contesto di sicurezza (nome utente/password) in modo che non possa essere assegnata una chiave. Se più di una persona è un membro e inviano/ricevono messaggi di posta elettronica crittografati con le proprie chiavi, altri membri potrebbero essere in grado di leggere il messaggio di posta elettronica e altri potrebbero non, a seconda di quale chiave pubblica il messaggio di posta elettronica è stato crittografato con.

- **Conversione delle cassette postali:** È possibile convertire le cassette postali degli utenti in cassette postali condivise. Vedere [Convertire una cassetta postale utente in una cassetta postale condivisa](convert-user-mailbox-to-shared-mailbox.md).

- **Ruoli di amministratore:** Gli utenti che dispongono di ruoli di amministratore globale o di amministrazione di Exchange possono creare cassette postali condivise.

- **Requisiti di sottoscrizione:** Per creare una cassetta postale condivisa, è necessario sottoscrivere un piano Microsoft 365 for business che includa la posta elettronica (il servizio Exchange Online). La sottoscrizione Microsoft 365 Apps for business non include la posta elettronica. Microsoft 365 business standard include la posta elettronica.

- **Accesso:** Una cassetta postale condivisa non è destinata all'accesso diretto dall'account utente associato. È sempre necessario bloccare l'accesso per l'account della cassetta postale condivisa e mantenerlo bloccato.

- **Troppi utenti:** Quando si verificano contemporaneamente troppi utenti designati che accedono a una cassetta postale condivisa, potrebbero non essere in grado di connettersi a questa cassetta postale. In questo caso, è possibile valutare la riduzione del numero di utenti o l'utilizzo di un carico di lavoro diverso, ad esempio un gruppo di Microsoft 365 o una cartella pubblica.

- **Eliminazione dei messaggi:** Purtroppo, non è possibile impedire agli utenti di eliminare i messaggi in una cassetta postale condivisa. In questo modo, è possibile creare un gruppo di Microsoft 365 anziché una cassetta postale condivisa. Un gruppo in Outlook è simile a una cassetta postale condivisa. Per un confronto tra i due, vedere [confrontare i gruppi](../create-groups/compare-groups.md). Per ulteriori informazioni sui gruppi, vedere ulteriori informazioni [sui gruppi](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2).

## <a name="related-articles"></a>Articoli correlati

[Creare una cassetta postale condivisa](create-a-shared-mailbox.md)

[Configurare una cassetta postale condivisa](configure-a-shared-mailbox.md)

[Convertire una cassetta postale utente in una cassetta postale condivisa](convert-user-mailbox-to-shared-mailbox.md)

[Rimuovere una licenza da una cassetta postale condivisa](remove-license-from-shared-mailbox.md)

[Risolvere i problemi relativi alle cassette postali condivise](resolve-issues-with-shared-mailboxes.md)
