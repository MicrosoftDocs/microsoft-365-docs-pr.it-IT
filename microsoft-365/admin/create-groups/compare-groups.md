---
title: Confrontare i gruppi
ms.reviewer: arvaradh
f1.keywords: CSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 758759ad-63ee-4ea9-90a3-39f941897b7d
description: I membri di un gruppo di Microsoft 365 ottengono un indirizzo e-mail di gruppo e un'area di lavoro condivisa per conversazioni, file ed eventi del calendario, Stream e un Planner.
ms.openlocfilehash: 038c4b9f6d9d28e62c0fb9b8f117db96ac42ddfb
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/11/2021
ms.locfileid: "52903841"
---
# <a name="compare-groups"></a>Confrontare i gruppi

Nella sezione **Gruppi** dell'interfaccia di amministrazione di Microsoft 365 è possibile gestire questi tipi di gruppi: 

- **I gruppi di Microsoft 365** (noti in precedenza come “gruppi di Office 365”) vengono usati per la collaborazione tra gli utenti, sia all’interno che all’esterno dell’azienda.
- I **gruppi di distribuzione** vengono usati per inviare notifiche tramite posta elettronica a un gruppo di persone.
- **I gruppi di sicurezza** vengono usati per concedere l'accesso a risorse come i siti di SharePoint.
- **I gruppi di sicurezza abilitati alla posta elettronica** vengono usati per concedere l'accesso a risorse come SharePoint e per inviare notifiche a tali utenti tramite posta elettronica.
- **Le cassette postali condivise** vengono usate quando più persone devono accedere alla stessa cassetta postale, ad esempio un'informazione aziendale o un indirizzo di posta elettronica di supporto.

## <a name="microsoft-365-groups"></a>Gruppi di Microsoft 365

I gruppi di Microsoft 365 vengono usati per la collaborazione tra gli utenti, sia all'interno che all'esterno dell'azienda. Con ciascun gruppo di Microsoft 365, i membri ottengono un indirizzo e-mail di gruppo e un'area di lavoro condivisa per conversazioni, file e eventi del calendario, Stream e un Planner.

È possibile aggiungere persone esterne alla propria organizzazione a un gruppo, purché questo sia stato [abilitato dall'amministratore](manage-guest-access-in-groups.md). È inoltre possibile consentire ai mittenti esterni di inviare messaggi di posta elettronica all'indirizzo di posta elettronica del gruppo.

I gruppi di Microsoft 365 possono essere [configurati per l'appartenenza dinamica in Azure Active Directory](/azure/active-directory/users-groups-roles/groups-change-type), consentendo l'aggiunta o la rimozione dei membri del gruppo in base agli attributi degli utenti, ad esempio reparto, posizione, titolo e così via.

È possibile accedere ai gruppi di Microsoft 365 tramite le app per dispositivi mobili come Outlook per iOS e Outlook per Android.

I membri del gruppo possono inviare o inviare per conto dell'indirizzo di posta elettronica del gruppo se l'opzione è stata [abilitata dall'amministratore](../../solutions/allow-members-to-send-as-or-send-on-behalf-of-group.md).

## <a name="distribution-groups"></a>Gruppi di distribuzione

[I gruppi di distribuzione](/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups) vengono usati per inviare notifiche a un gruppo di persone. Queste persone possono ricevere messaggi di posta elettronica esterni se abilitati dall'amministratore.

I gruppi di distribuzione sono ideali per quelle situazioni in cui è necessario trasmettere informazioni a un gruppo di persone, ad esempio agli "utenti dell'edificio A" o "tutti gli utenti di Contoso".

I gruppi di distribuzione possono essere [aggiornati ai gruppi di Microsoft 365](../manage/upgrade-distribution-lists.md).

È possibile aggiungere gruppi di distribuzione a un team in Microsoft Teams.

## <a name="security-groups"></a>Gruppi di sicurezza

[I gruppi di sicurezza](../email/create-edit-or-delete-a-security-group.md) vengono usati per concedere l'accesso alle risorse di Microsoft 365, ad esempio SharePoint. Consentono di semplificare l'amministrazione perché è necessario gestire solo il gruppo anziché aggiungere utenti a ogni risorsa singolarmente.

I gruppi di sicurezza possono contenere utenti o dispositivi. La creazione di un gruppo di sicurezza per i dispositivi può essere usata con i servizi di gestione dei dispositivi mobili, ad esempio Intune.

I gruppi di sicurezza possono essere [configurati per l'appartenenza dinamica in Azure Active Directory](/azure/active-directory/users-groups-roles/groups-change-type), consentendo l'aggiunta o la rimozione dei membri o dei dispositivi del gruppo in base agli attributi degli utenti, ad esempio reparto, posizione o titolo oppure gli attributi del dispositivo come la versione del sistema operativo.

I gruppi di sicurezza possono essere aggiunti a un team.

## <a name="mail-enabled-security-groups"></a>Gruppi di sicurezza abilitati alla posta elettronica

I gruppi di sicurezza abilitati alla posta elettronica sono identici ai normali gruppi di sicurezza, con la differenza che non possono essere gestiti in modo dinamico tramite Azure Active Directory e non possono contenere dispositivi.

Includono la possibilità di inviare messaggi di posta elettronica a tutti i membri del gruppo.

I gruppi di sicurezza abilitati alla posta elettronica possono essere aggiunti a un team.

## <a name="shared-mailboxes"></a>Cassette postali condivise

[Le cassette postali condivise](../email/create-a-shared-mailbox.md) vengono usate quando più persone devono accedere alla stessa cassetta postale, ad esempio un'informazione aziendale o un indirizzo di posta elettronica di supporto, una reception o un'altra funzione che potrebbe essere condivisa da più persone.

Le cassette postali condivise possono ricevere messaggi esterni se abilitati dall'amministratore.

Le cassette postali condivise includono un calendario che può essere usato per la collaborazione.

Gli utenti che dispongono delle autorizzazioni per la cassetta postale del gruppo possono inviare o inviare per conto dell'indirizzo di posta elettronica della cassetta postale, se l'amministratore ha concesso tali autorizzazioni. Questa funzione è particolarmente utile per le cassette postali dell'assistenza e del supporto, perché gli utenti possono inviare messaggi di posta elettronica dal "supporto tecnico Contoso" o dalla "reception dell'edificio A".

Non è possibile eseguire la migrazione di una cassetta postale condivisa a un gruppo di Microsoft 365. 

## <a name="related-content"></a>Contenuto correlato

[Informazioni sui gruppi di Microsoft 365](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2) (articolo)\
[Perché è consigliabile eseguire l'aggiornamento delle liste di distribuzione ai gruppi di Outlook](https://support.microsoft.com/office/7fb3d880-593b-4909-aafa-950dd50ce188) (articoli)
