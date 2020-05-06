---
title: Gestione di destinatari in EOP
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/17/2014
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 2921f544-8257-4bae-8e3a-ce9250e9f162
ms.custom:
- seo-marvel-apr2020
description: In questo articolo vengono fornite informazioni sui destinatari di posta elettronica supportati da Microsoft Exchange Online Protection (EOP).
ms.openlocfilehash: eb2855f93083c88725492be2691799c3521bbf8f
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "44036150"
---
# <a name="manage-recipients-in-eop"></a><span data-ttu-id="76cc9-103">Gestire destinatari in Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="76cc9-103">Manage recipients in EOP</span></span>

<span data-ttu-id="76cc9-104">Microsoft Exchange Online Protection (EOP) offre diversi modi per gestire i destinatari della posta.</span><span class="sxs-lookup"><span data-stu-id="76cc9-104">Microsoft Exchange Online Protection (EOP) offers several ways to manage your mail recipients.</span></span> <span data-ttu-id="76cc9-105">In qualità di amministratore, è possibile eseguire alcune attività di gestione all'interno dell'interfaccia di amministrazione di Exchange (EAC) o tramite Windows PowerShell remoto e verificare altre attività di gestione eseguite nell'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="76cc9-105">As an administrator, you can perform certain management tasks within the Exchange admin center (EAC) or using remote Windows PowerShell, and verify other management tasks performed in the Microsoft 365 admin center.</span></span>

<span data-ttu-id="76cc9-106">EOP supporta i seguenti tipi di destinatari:</span><span class="sxs-lookup"><span data-stu-id="76cc9-106">EOP supports the following types of recipients:</span></span>

- <span data-ttu-id="76cc9-107">**Utenti di posta elettronica**: gli utenti di posta elettronica sono destinatari nei domini gestiti di EOP.</span><span class="sxs-lookup"><span data-stu-id="76cc9-107">**Mail Users**: Mail users are recipients in your EOP managed domains.</span></span> <span data-ttu-id="76cc9-108">Questi destinatari dispongono di credenziali di accesso all'interno dell'organizzazione, ma dispongono di indirizzi di posta elettronica esterni, ovvero le cassette postali dei destinatari sono situate all'esterno dell'organizzazione cloud.</span><span class="sxs-lookup"><span data-stu-id="76cc9-108">These recipients have logon credentials in your organization, but they have external email addresses, meaning that their recipient mailboxes are located outside of your cloud organization.</span></span>

  <span data-ttu-id="76cc9-109">È possibile aggiungere utenti di posta elettronica in modo che possano ricevere messaggi di posta elettronica ed è anche possibile creare regole del flusso di posta (note anche come regole di trasporto) per utenti specifici.</span><span class="sxs-lookup"><span data-stu-id="76cc9-109">You can add mail users so that they can receive mail and you can also create mail flow rules (also known as transport rules) for specific users.</span></span> <span data-ttu-id="76cc9-110">È inoltre possibile assegnare ruoli agli utenti di posta elettronica nell'organizzazione. Gli utenti con privilegi del gruppo di ruoli di gestione possono accedere all'interfaccia di amministrazione di Exchange (EAC) ed eseguire determinate attività di gestione.</span><span class="sxs-lookup"><span data-stu-id="76cc9-110">You can also assign roles to mail users in your organization; users with management role group privileges can access the Exchange admin center (EAC) and perform certain management tasks.</span></span> <span data-ttu-id="76cc9-111">Per ulteriori informazioni sui ruoli utente e sulla modalità di assegnazione dei ruoli utente in EOP, vedere [Manage admin Group Role Permissions in EOP](manage-admin-role-group-permissions-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="76cc9-111">To learn more about user roles and how to assign user roles in EOP, see [Manage admin role group permissions in EOP](manage-admin-role-group-permissions-in-eop.md).</span></span>

  <span data-ttu-id="76cc9-112">Per ulteriori informazioni sulla gestione degli utenti di posta elettronica in EOP, vedere [Gestione utenti di posta in EOP](manage-mail-users-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="76cc9-112">For more information about managing mail users in EOP, see [Manage mail users in EOP](manage-mail-users-in-eop.md).</span></span>

- <span data-ttu-id="76cc9-113">**Gruppi**: gli utenti di posta elettronica possono essere raggruppati in gruppi di distribuzione o gruppi di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="76cc9-113">**Groups**: Mail users can be grouped together into distribution groups or security groups.</span></span>

<span data-ttu-id="76cc9-114">Per ulteriori informazioni sulla gestione dei gruppi in EOP, vedere [Gestione di gruppi in EOP](manage-groups-in-eop.md).</span><span class="sxs-lookup"><span data-stu-id="76cc9-114">For more information about managing groups in EOP, see [Manage groups in EOP](manage-groups-in-eop.md).</span></span>
