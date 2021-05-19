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
ms.openlocfilehash: 156ba100cb2c51d1e54a2ee82c45db20845931f9
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2021
ms.locfileid: "52535855"
---
# <a name="about-shared-mailboxes"></a>Informazioni sulle cassette postali condivise

Le cassette postali condivise vengono usate quando più persone devono accedere alla stessa cassetta postale, ad esempio un'informazione aziendale o un indirizzo di posta elettronica di supporto, una reception o un'altra funzione che potrebbe essere condivisa da più persone.

Gli utenti che dispongono delle autorizzazioni per la cassetta postale del gruppo possono inviare o inviare per conto dell'indirizzo di posta elettronica della cassetta postale, se l'amministratore ha concesso tali autorizzazioni. Questa funzione è particolarmente utile per le cassette postali dell'assistenza e del supporto, perché gli utenti possono inviare messaggi di posta elettronica dal "supporto tecnico Contoso" o dalla "reception dell'edificio A".

## <a name="before-you-begin"></a>Prima di iniziare

Prima di [creare una cassetta postale condivisa,](create-a-shared-mailbox.md)ecco alcuni aspetti da sapere:

- **Licenze:** La cassetta postale condivisa può archiviare fino a 50 GB di dati senza assegnare una licenza. Per volumi più elevati, è necessario assegnare una licenza alla cassetta postale per archiviare più dati. Per ulteriori dettagli sulle licenze delle cassette postali condivise, vedere [Exchange Online Limits](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#StorageLimits). Dopo che la cassetta postale condivisa raggiunge il limite di archiviazione, per un certo periodo sarà possibile ricevere messaggi di posta elettronica, ma non inviarli. Trascorso quel periodo anche la ricezione verrà disabilitata. I mittenti dei messaggi riceveranno un rapporto di mancato recapito.

- **Autorizzazioni utente:** È necessario concedere agli utenti le autorizzazioni (appartenenza) per utilizzare la cassetta postale condivisa. Solo le persone interne all'organizzazione possono usare una cassetta postale condivisa.

- **Utenti esterni:** Non è possibile concedere a persone esterne all'azienda (ad esempio persone con un account Gmail) l'accesso alla cassetta postale condivisa. Se si vuole farlo comunque, è consigliabile creare un gruppo di Outlook. Per ulteriori informazioni, vedere [Create a Microsoft 365 group in the admin center.](../create-groups/create-groups.md)

- **Da usare con Outlook:** Oltre a usare Outlook sul Web dal browser per accedere alle cassette postali condivise, puoi anche usare l'app Outlook per iOS o l'app Outlook per Android. Per ulteriori informazioni, vedere [Add a shared mailbox to Outlook mobile](https://support.microsoft.com/office/f866242c-81b2-472e-8776-6c49c5473c9f). Un'altra opzione è creare un gruppo per la cassetta postale condivisa. Per ulteriori informazioni, vedere [Compare Groups.](../create-groups/compare-groups.md)

- **Crittografia:** Non è possibile crittografare la posta elettronica inviata da una cassetta postale condivisa. Ciò è dovuto al fatto che una cassetta postale condivisa non dispone di un proprio contesto di sicurezza (nome utente/password), quindi non può essere assegnata a una chiave. Se più di una persona è membro e invia/riceve messaggi di posta elettronica crittografati con le proprie chiavi, altri membri potrebbero essere in grado di leggere il messaggio di posta elettronica e altri potrebbero non essere in grado di leggere il messaggio di posta elettronica, a seconda della chiave pubblica con cui è stato crittografato il messaggio.

- **Conversione delle cassette postali:** È possibile convertire le cassette postali degli utenti in cassette postali condivise. Vedere [Convertire una cassetta postale utente in una cassetta postale condivisa](convert-user-mailbox-to-shared-mailbox.md).

- **Ruoli di amministratore:** Gli utenti con ruoli di amministratore globale Exchange amministratore possono creare cassette postali condivise.

- **Requisiti di sottoscrizione:** Per creare una cassetta postale condivisa, è necessario sottoscrivere un piano Microsoft 365 per le aziende che include la posta elettronica (il Exchange Online servizio). La Microsoft 365 Apps for business non include la posta elettronica. Microsoft 365 Business Standard include la posta elettronica.

- **Accesso:** Una cassetta postale condivisa non è progettata per l'accesso diretto da parte dell'account utente associato. È consigliabile bloccare sempre l'accesso per l'account della cassetta postale condivisa e mantenerlo bloccato.

- **Troppi utenti:** Quando ci sono troppi utenti designati che accedono contemporaneamente a una cassetta postale condivisa, potrebbero non riuscire a connettersi a questa cassetta postale in modo intermittente. In questo caso, è possibile ridurre il numero di utenti o utilizzare un carico di lavoro diverso, ad esempio un gruppo Microsoft 365 o una cartella pubblica.

- **Eliminazione messaggio:** Purtroppo, non è possibile impedire agli utenti di eliminare i messaggi in una cassetta postale condivisa. L'unico modo per risolvere questo problema è quello di creare un Microsoft 365 invece di una cassetta postale condivisa. Un gruppo in Outlook è come una cassetta postale condivisa. Per un confronto tra i due, vedere [Compare groups](../create-groups/compare-groups.md). Per ulteriori informazioni sui gruppi, vedere [Ulteriori informazioni sui gruppi.](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)


> [!NOTE]
> Per accedere a una cassetta postale condivisa, un utente deve disporre di una licenza Exchange Online, ma la cassetta postale condivisa non richiede una licenza separata. Ogni cassetta postale condivisa ha un account utente corrispondente. Anche se non è stata richiesta una password al momento della creazione della cassetta postale condivisa, l'account dispone di una password, ma è generata dal sistema (sconosciuta). Non utilizzare l'account per accedere alla cassetta postale condivisa. Senza licenza, le cassette postali condivise sono limitate a 50 GB. Per aumentare il limite delle dimensioni a 100 GB, la cassetta postale condivisa deve essere assegnata a una licenza Exchange Online (Piano 2),oppure a una licenza Exchange Online (Piano 1) con una licenza per il componente aggiuntivo Archiviazione Exchange Online. In questo modo sarà anche possibile abilitare l'archiviazione a espansione automatica per una quantità illimitata di capacità di archiviazione. Analogamente, se si vuole mettere una cassetta postale condivisa in blocco per controversia legale, la cassetta postale condivisa deve essere assegnata a una licenza Exchange Online (Piano 2), oppure a una licenza Exchange Online (Piano 1) con una licenza per il componente aggiuntivo Archiviazione Exchange Online. Se si desidera applicare funzionalità avanzate come Microsoft Defender per Office 365, Advanced eDiscovery o criteri di conservazione automatica, la cassetta postale condivisa deve essere concessa in licenza per tali funzionalità.

## <a name="related-content"></a>Contenuto correlato

[Creare una cassetta postale condivisa](create-a-shared-mailbox.md) (articolo)

[Configurare una cassetta postale condivisa](configure-a-shared-mailbox.md) (articolo)

[Convertire una cassetta postale utente in una cassetta postale condivisa](convert-user-mailbox-to-shared-mailbox.md) (articolo)

[Rimuovere una licenza da una cassetta postale condivisa](remove-license-from-shared-mailbox.md) (articolo)

[Risolvere i problemi relativi alle cassette postali condivise](resolve-issues-with-shared-mailboxes.md) (articolo)