---
title: Confrontare i gruppi
ms.reviewer: arvaradh
f1.keywords: CSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 758759ad-63ee-4ea9-90a3-39f941897b7d
description: Informazioni sui tipi di gruppi che è possibile usare.
ms.openlocfilehash: 333d929e72647421951eefa50508c23dddc196ac
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780458"
---
# <a name="compare-groups"></a><span data-ttu-id="b95d4-103">Confrontare i gruppi</span><span class="sxs-lookup"><span data-stu-id="b95d4-103">Compare groups</span></span>

<span data-ttu-id="b95d4-104">Nella sezione **Gruppi** dell'interfaccia di amministrazione di Microsoft 365 è possibile gestire questi tipi di gruppi:</span><span class="sxs-lookup"><span data-stu-id="b95d4-104">In the **Groups** section of the Microsoft 365 admin center, you can create and manage these types of groups:</span></span> 

- <span data-ttu-id="b95d4-105">**I gruppi di Microsoft 365** (noti in precedenza come “gruppi di Office 365”) vengono usati per la collaborazione tra gli utenti, sia all’interno che all’esterno dell’azienda.</span><span class="sxs-lookup"><span data-stu-id="b95d4-105">**Microsoft 365 groups** (formerly Office 365 groups) are used for collaboration between users, both inside and outside your company.</span></span>
- <span data-ttu-id="b95d4-106">**I gruppi di distribuzione** vengono usati per inviare notifiche a un gruppo di persone.</span><span class="sxs-lookup"><span data-stu-id="b95d4-106">**Distribution groups** are used for sending notifications to a group of people.</span></span>
- <span data-ttu-id="b95d4-107">**I gruppi di sicurezza** vengono usati per concedere l'accesso a risorse come i siti di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="b95d4-107">**Security groups** are used for granting access to resources such as SharePoint sites.</span></span>
- <span data-ttu-id="b95d4-108">**I gruppi di sicurezza abilitati alla posta elettronica** vengono usati per concedere l'accesso a risorse come SharePoint e per inviare notifiche a tali utenti tramite posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="b95d4-108">**Mail-enabled security groups** are used for granting access to resources such as SharePoint, and emailing notifications to those users.</span></span>
- <span data-ttu-id="b95d4-109">**Le cassette postali condivise** vengono usate quando più persone devono accedere alla stessa cassetta postale, ad esempio un'informazione aziendale o un indirizzo di posta elettronica di supporto.</span><span class="sxs-lookup"><span data-stu-id="b95d4-109">**Shared mailboxes** are used when multiple people need access to the same mailbox, such as a company information or support email address.</span></span>

## <a name="microsoft-365-groups"></a><span data-ttu-id="b95d4-110">Gruppi di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b95d4-110">Microsoft 365 groups</span></span>

<span data-ttu-id="b95d4-111">I gruppi di Microsoft 365 vengono usati per la collaborazione tra gli utenti, sia all'interno che all'esterno dell'azienda.</span><span class="sxs-lookup"><span data-stu-id="b95d4-111">Microsoft 365 groups are used for collaboration between users, both inside and outside your company.</span></span> <span data-ttu-id="b95d4-112">Con ciascun gruppo di Microsoft 365, i membri ottengono un indirizzo e-mail di gruppo e un'area di lavoro condivisa per conversazioni, file e eventi del calendario, oltre a Planner.</span><span class="sxs-lookup"><span data-stu-id="b95d4-112">With each Microsoft 365 group, members get a group email and shared workspace for conversations, files, and calendar events, and a Planner.</span></span>

<span data-ttu-id="b95d4-113">È possibile aggiungere persone esterne alla propria organizzazione a un gruppo, purché questo sia stato [abilitato dall'amministratore](manage-guest-access-in-groups.md).</span><span class="sxs-lookup"><span data-stu-id="b95d4-113">You can add people from outside your organization to a group as long as this has been [enabled by the administrator](manage-guest-access-in-groups.md).</span></span> <span data-ttu-id="b95d4-114">È inoltre possibile consentire ai mittenti esterni di inviare messaggi di posta elettronica all'indirizzo di posta elettronica del gruppo.</span><span class="sxs-lookup"><span data-stu-id="b95d4-114">You can also allow external senders to send email to the group email address.</span></span>

<span data-ttu-id="b95d4-115">I gruppi di Microsoft 365 possono essere [configurati per l'appartenenza dinamica in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type), consentendo l'aggiunta o la rimozione dei membri del gruppo in base agli attributi degli utenti, ad esempio reparto, posizione, titolo e così via.</span><span class="sxs-lookup"><span data-stu-id="b95d4-115">Microsoft 365 groups can be [configured for dynamic membership in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type), allowing group members to be added or removed automatically based on user attributes such as department, location, title, etc.</span></span>

<span data-ttu-id="b95d4-116">È possibile accedere ai gruppi di Microsoft 365 tramite le app per dispositivi mobili come Outlook per iOS e Outlook per Android.</span><span class="sxs-lookup"><span data-stu-id="b95d4-116">Microsoft 365 groups can be accessed through mobile apps such as Outlook for iOS and Outlook for Android.</span></span>

<span data-ttu-id="b95d4-117">I membri del gruppo possono inviare o inviare per conto dell'indirizzo di posta elettronica del gruppo se l'opzione è stata [abilitata dall'amministratore](allow-members-to-send-as-or-send-on-behalf-of-group.md).</span><span class="sxs-lookup"><span data-stu-id="b95d4-117">Group members can send as or send on behalf of the group email address if this has been [enabled by the administrator](allow-members-to-send-as-or-send-on-behalf-of-group.md).</span></span>

## <a name="distribution-groups"></a><span data-ttu-id="b95d4-118">Gruppi di distribuzione</span><span class="sxs-lookup"><span data-stu-id="b95d4-118">Distribution groups</span></span>

<span data-ttu-id="b95d4-119">[I gruppi di distribuzione](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups) vengono usati per inviare notifiche a un gruppo di persone.</span><span class="sxs-lookup"><span data-stu-id="b95d4-119">[Distribution groups](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups) are used for sending notifications to a group of people.</span></span> <span data-ttu-id="b95d4-120">Queste persone possono ricevere messaggi di posta elettronica esterni se abilitati dall'amministratore.</span><span class="sxs-lookup"><span data-stu-id="b95d4-120">They can receive external email if enabled by the administrator.</span></span>

<span data-ttu-id="b95d4-121">I gruppi di distribuzione sono ideali per quelle situazioni in cui è necessario trasmettere informazioni a un gruppo di persone, ad esempio agli "utenti dell'edificio A" o "tutti gli utenti di Contoso".</span><span class="sxs-lookup"><span data-stu-id="b95d4-121">Distribution groups are best for situations where you need to broadcast information to a set group of people, such as "People in Building A" or "Everyone at Contoso."</span></span>

## <a name="security-groups"></a><span data-ttu-id="b95d4-122">Gruppi di sicurezza</span><span class="sxs-lookup"><span data-stu-id="b95d4-122">Security groups</span></span>

<span data-ttu-id="b95d4-123">[I gruppi di sicurezza](../email/create-edit-or-delete-a-security-group.md) vengono usati per concedere l'accesso alle risorse di Microsoft 365, ad esempio SharePoint.</span><span class="sxs-lookup"><span data-stu-id="b95d4-123">[Security groups](../email/create-edit-or-delete-a-security-group.md) are used for granting access to Microsoft 365 resources, such as SharePoint.</span></span> <span data-ttu-id="b95d4-124">Consentono di semplificare l'amministrazione perché è necessario gestire solo il gruppo anziché aggiungere utenti a ogni risorsa singolarmente.</span><span class="sxs-lookup"><span data-stu-id="b95d4-124">They can make administration easier because you need only administer the group rather than adding users to each resource individually.</span></span>

<span data-ttu-id="b95d4-125">I gruppi di sicurezza possono contenere utenti o dispositivi.</span><span class="sxs-lookup"><span data-stu-id="b95d4-125">Security groups can contain users or devices.</span></span> <span data-ttu-id="b95d4-126">La creazione di un gruppo di sicurezza per i dispositivi può essere usata con i servizi di gestione dei dispositivi mobili, ad esempio Intune.</span><span class="sxs-lookup"><span data-stu-id="b95d4-126">Creating a security group for devices can be used with mobile device management services, such as Intune.</span></span>

<span data-ttu-id="b95d4-127">I gruppi di sicurezza possono essere [configurati per l'appartenenza dinamica in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type), consentendo l'aggiunta o la rimozione dei membri o dei dispositivi del gruppo in base agli attributi degli utenti, ad esempio reparto, posizione o titolo oppure gli attributi del dispositivo come la versione del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="b95d4-127">Security groups can be [configured for dynamic membership in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type), allowing group members or devices to be added or removed automatically based on user attributes such as department, location, or title; or device attributes such as operating system version.</span></span>

## <a name="mail-enabled-security-groups"></a><span data-ttu-id="b95d4-128">Gruppi di sicurezza abilitati alla posta elettronica</span><span class="sxs-lookup"><span data-stu-id="b95d4-128">Mail-enabled security groups</span></span>

<span data-ttu-id="b95d4-129">I gruppi di sicurezza abilitati alla posta elettronica sono identici ai normali gruppi di sicurezza, con la differenza che non possono essere gestiti in modo dinamico tramite Azure Active Directory e non possono contenere dispositivi.</span><span class="sxs-lookup"><span data-stu-id="b95d4-129">Mail-enabled security groups function the same as regular security groups, except that they cannot be dynamically managed through Azure Active Directory and cannot contain devices.</span></span>

<span data-ttu-id="b95d4-130">Includono la possibilità di inviare messaggi di posta elettronica a tutti i membri del gruppo.</span><span class="sxs-lookup"><span data-stu-id="b95d4-130">They include the ability to send mail to all the members of the group.</span></span>

## <a name="shared-mailboxes"></a><span data-ttu-id="b95d4-131">Cassette postali condivise</span><span class="sxs-lookup"><span data-stu-id="b95d4-131">Shared mailboxes</span></span>

<span data-ttu-id="b95d4-132">[Le cassette postali condivise](../email/create-a-shared-mailbox.md) vengono usate quando più persone devono accedere alla stessa cassetta postale, ad esempio un'informazione aziendale o un indirizzo di posta elettronica di supporto, una reception o un'altra funzione che potrebbe essere condivisa da più persone.</span><span class="sxs-lookup"><span data-stu-id="b95d4-132">[Shared mailboxes](../email/create-a-shared-mailbox.md) are used when multiple people need access to the same mailbox, such as a company information or support email address, reception desk, or other function that might be shared by multiple people.</span></span>

<span data-ttu-id="b95d4-133">Le cassette postali condivise possono ricevere messaggi esterni se abilitati dall'amministratore.</span><span class="sxs-lookup"><span data-stu-id="b95d4-133">Shared mailboxes can receive external emails if the administrator has enabled this.</span></span>

<span data-ttu-id="b95d4-134">Gli utenti che dispongono delle autorizzazioni per la cassetta postale del gruppo possono inviare o inviare per conto dell'indirizzo di posta elettronica della cassetta postale, se l'amministratore ha concesso tali autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="b95d4-134">Users with permissions to the group mailbox can send as or send on behalf of the mailbox email address if the administrator has given that user permissions to do that.</span></span> <span data-ttu-id="b95d4-135">Questa funzione è particolarmente utile per le cassette postali dell'assistenza e del supporto, perché gli utenti possono inviare messaggi di posta elettronica dal "supporto tecnico Contoso" o dalla "reception dell'edificio A".</span><span class="sxs-lookup"><span data-stu-id="b95d4-135">This is particularly useful for help and support mailboxes because users can send emails from "Contoso Support" or "Building A Reception Desk."</span></span>

<span data-ttu-id="b95d4-136">Attualmente non è possibile eseguire la migrazione di una cassetta postale condivisa a un gruppo di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b95d4-136">Currently it's not possible to migrate a shared mailbox to a Microsoft 365 group.</span></span> <span data-ttu-id="b95d4-137">L'argomento trattato è interessante?</span><span class="sxs-lookup"><span data-stu-id="b95d4-137">Is this something you want?</span></span> <span data-ttu-id="b95d4-138">Grazie per la segnalazione.</span><span class="sxs-lookup"><span data-stu-id="b95d4-138">Let us know.</span></span> <span data-ttu-id="b95d4-139">**[Votare qui](https://go.microsoft.com/fwlink/?linkid=871518)**</span><span class="sxs-lookup"><span data-stu-id="b95d4-139">**[Vote here](https://go.microsoft.com/fwlink/?linkid=871518)**.</span></span>

## <a name="related-articles"></a><span data-ttu-id="b95d4-140">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="b95d4-140">Related articles</span></span>

[<span data-ttu-id="b95d4-141">Informazioni sui gruppi di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b95d4-141">Learn about Microsoft 365 groups</span></span>](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)
