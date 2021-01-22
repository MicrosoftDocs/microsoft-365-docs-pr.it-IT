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
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
description: Le cassette postali condivise vengono utilizzate quando più persone devono accedere alla stessa cassetta postale. Informazioni su cosa è necessario sapere prima di creare una cassetta postale condivisa.
ms.openlocfilehash: 744c4fece24cf1fa5ee7259a0d722ff123ff2664
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926511"
---
# <a name="about-shared-mailboxes"></a>Informazioni sulle cassette postali condivise

Le cassette postali condivise vengono usate quando più persone devono accedere alla stessa cassetta postale, ad esempio un'informazione aziendale o un indirizzo di posta elettronica di supporto, una reception o un'altra funzione che potrebbe essere condivisa da più persone.

Gli utenti che dispongono delle autorizzazioni per la cassetta postale del gruppo possono inviare o inviare per conto dell'indirizzo di posta elettronica della cassetta postale, se l'amministratore ha concesso tali autorizzazioni. Questa funzione è particolarmente utile per le cassette postali dell'assistenza e del supporto, perché gli utenti possono inviare messaggi di posta elettronica dal "supporto tecnico Contoso" o dalla "reception dell'edificio A".

Prima di [creare una cassetta postale condivisa,](create-a-shared-mailbox.md)di seguito sono riportati alcuni aspetti da conoscere:

- **Licenze:** La cassetta postale condivisa può archiviare fino a 50 GB di dati senza assegnare una licenza. Per volumi più elevati, è necessario assegnare una licenza alla cassetta postale per archiviare più dati. Per ulteriori dettagli sulla gestione delle licenze per le cassette postali condivise, vedere [Limiti di Exchange Online.](https://technet.microsoft.com/library/exchange-online-limits.aspx#StorageLimits) Dopo che la cassetta postale condivisa raggiunge il limite di archiviazione, per un certo periodo sarà possibile ricevere messaggi di posta elettronica, ma non inviarli. Trascorso quel periodo anche la ricezione verrà disabilitata. I mittenti dei messaggi riceveranno un rapporto di mancato recapito.

- **Autorizzazioni utente:** È necessario concedere agli utenti le autorizzazioni (appartenenza) per utilizzare la cassetta postale condivisa. Solo le persone interne all'organizzazione possono usare una cassetta postale condivisa.

- **Utenti esterni:** Non è possibile concedere a persone esterne all'azienda (ad esempio persone con un account Gmail) l'accesso alla cassetta postale condivisa. Se si vuole farlo comunque, è consigliabile creare un gruppo di Outlook. Per altre informazioni, vedere [Creare un gruppo di Microsoft 365 nell'interfaccia di amministrazione.](../create-groups/create-groups.md)

- **Utilizzare con Outlook:** Oltre a utilizzare Outlook sul Web dal browser per accedere alle cassette postali condivise, è anche possibile utilizzare l'app Outlook per iOS o l'app Outlook per Android. Per ulteriori informazioni, vedere [Aggiungere una cassetta postale condivisa a Outlook Mobile.](https://support.microsoft.com/office/f866242c-81b2-472e-8776-6c49c5473c9f) Un'altra opzione è creare un gruppo per la cassetta postale condivisa. Per ulteriori informazioni, vedere [Confronto dei gruppi.](../create-groups/compare-groups.md)

- **Crittografia:** Non è possibile crittografare la posta elettronica inviata da una cassetta postale condivisa. Ciò è dovuto al fatto che una cassetta postale condivisa non dispone di un proprio contesto di protezione (nome utente/password) e pertanto non può essere assegnata a una chiave. Se più di una persona è un membro e invia/riceve messaggi di posta elettronica crittografati con le proprie chiavi, altri membri potrebbero essere in grado di leggere il messaggio di posta elettronica e altri potrebbero non esserne in grado, a seconda della chiave pubblica con cui è stato crittografato il messaggio.

- **Conversione delle cassette postali:** È possibile convertire le cassette postali degli utenti in cassette postali condivise. Vedere [Convertire una cassetta postale utente in una cassetta postale condivisa](convert-user-mailbox-to-shared-mailbox.md).

- **Ruoli di amministratore:** Gli utenti con ruoli di amministratore globale o di amministratore di Exchange possono creare cassette postali condivise.

- **Requisiti di sottoscrizione:** Per creare una cassetta postale condivisa, è necessario sottoscrivere un piano di Microsoft 365 per le aziende che includa la posta elettronica (il servizio Exchange Online). L'abbonamento a Microsoft 365 Apps for business non include la posta elettronica. Microsoft 365 Business Standard include la posta elettronica.

- **Accesso:** Una cassetta postale condivisa non è progettata per l'accesso diretto da parte dell'account utente associato. È consigliabile bloccare sempre l'accesso per l'account della cassetta postale condivisa e mantenerlo bloccato.

- **Troppi utenti:** Quando ci sono troppi utenti designati che accedono contemporaneamente a una cassetta postale condivisa, potrebbero non riuscire a connettersi a questa cassetta postale. In questo caso, è possibile ridurre il numero degli utenti o usare un carico di lavoro diverso, ad esempio un gruppo di Microsoft 365 o una cartella pubblica.

- **Eliminazione dei messaggi:** Purtroppo, non è possibile impedire agli utenti di eliminare i messaggi in una cassetta postale condivisa. L'unico modo per risolvere questo problema è creare un gruppo di Microsoft 365 anziché una cassetta postale condivisa. Un gruppo in Outlook è come una cassetta postale condivisa. Per un confronto tra i due, vedere [Confrontare gruppi.](../create-groups/compare-groups.md) Per altre informazioni sui gruppi, vedi [Altre informazioni sui gruppi.](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

## <a name="related-articles"></a>Articoli correlati

[Creare una cassetta postale condivisa](create-a-shared-mailbox.md)

[Configurare una cassetta postale condivisa](configure-a-shared-mailbox.md)

[Convertire una cassetta postale utente in una cassetta postale condivisa](convert-user-mailbox-to-shared-mailbox.md)

[Rimuovere una licenza da una cassetta postale condivisa](remove-license-from-shared-mailbox.md)

[Risolvere i problemi relativi alle cassette postali condivise](resolve-issues-with-shared-mailboxes.md)
