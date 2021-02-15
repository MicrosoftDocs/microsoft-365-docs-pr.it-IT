---
title: Informazioni sul ruolo di amministratore di Exchange Online
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 097ae285-c4af-4319-9770-e2559d66e4c8
description: "Gli amministratori di Exchange Online gestiscono la posta elettronica e le cassette postali dell'organizzazione. Ad esempio, recuperano gli elementi eliminati nella cassetta postale di un utente. "
ms.openlocfilehash: 8e332e886ca25221fefbbc5d1bb790bd4f513f00
ms.sourcegitcommit: 4cbb4ec26f022f5f9d9481f55a8a6ee8406968d2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/01/2020
ms.locfileid: "49527514"
---
# <a name="about-the-exchange-online-admin-role"></a><span data-ttu-id="3cf9c-104">Informazioni sul ruolo di amministratore di Exchange Online</span><span class="sxs-lookup"><span data-stu-id="3cf9c-104">About the Exchange Online admin role</span></span>

<span data-ttu-id="3cf9c-105">Per facilitare l'amministrazione di Microsoft [](assign-admin-roles.md) 365, è possibile assegnare agli utenti le autorizzazioni per gestire la posta elettronica e le cassette postali dell'organizzazione dall'interfaccia [di amministrazione di Exchange.](https://go.microsoft.com/fwlink/p/?LinkID=271807)</span><span class="sxs-lookup"><span data-stu-id="3cf9c-105">To help you administer Microsoft 365, you can [assign](assign-admin-roles.md) users permissions to manage your organization's email and mailboxes from the [Exchange admin center](https://go.microsoft.com/fwlink/p/?LinkID=271807).</span></span> <span data-ttu-id="3cf9c-106">Per farlo, assegnare il ruolo di amministratore di Exchange.</span><span class="sxs-lookup"><span data-stu-id="3cf9c-106">You do this by assigning them to the Exchange admin role.</span></span>
  
 <span data-ttu-id="3cf9c-107">**Suggerimento**: Quando si assegna il ruolo di amministratore di Exchange a un utente, assegnare anche il ruolo di amministratore dei servizi.</span><span class="sxs-lookup"><span data-stu-id="3cf9c-107">**Tip**: When you assign someone to the Exchange admin role, also assign them to the Service admin role.</span></span> <span data-ttu-id="3cf9c-108">In questo modo possono visualizzare informazioni importanti nell'interfaccia di amministrazione di Microsoft 365, ad esempio l'integrità del servizio Exchange Online, nonché le notifiche di modifica e rilascio.</span><span class="sxs-lookup"><span data-stu-id="3cf9c-108">This way they can see important information in the Microsoft 365 admin center, such as the health of the Exchange Online service, and change and release notifications.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="3cf9c-109">Informazioni preliminari</span><span class="sxs-lookup"><span data-stu-id="3cf9c-109">Before you begin</span></span>

<span data-ttu-id="3cf9c-110">Ecco alcune delle principali attività che possono eseguire gli utenti a cui è stato assegnato il ruolo di amministratore di Exchange:</span><span class="sxs-lookup"><span data-stu-id="3cf9c-110">Here are some of the key tasks users can do when they are assigned to the Exchange admin role:</span></span>
  
- [<span data-ttu-id="3cf9c-111">Recuperare gli elementi eliminati nella cassetta postale di un utente</span><span class="sxs-lookup"><span data-stu-id="3cf9c-111">Recover deleted items in a user mailbox - Admin Help</span></span>](https://docs.microsoft.com/microsoft-365/enterprise/recover-deleted-items-in-a-mailbox)

- <span data-ttu-id="3cf9c-112">[Configurare un criterio di archiviazione ed eliminazione per le cassette postali nell'organizzazione.](https://docs.microsoft.com/microsoft-365/compliance/set-up-an-archive-and-deletion-policy-for-mailboxes)</span><span class="sxs-lookup"><span data-stu-id="3cf9c-112">[Set up an archive and deletion policy for mailboxes in your organization](https://docs.microsoft.com/microsoft-365/compliance/set-up-an-archive-and-deletion-policy-for-mailboxes).</span></span>

- <span data-ttu-id="3cf9c-113">Impostare le caratteristiche delle cassette postali, ad esempio i criteri di condivisione della cassetta postale: con che modalità gli utenti possono condividere le informazioni su calendario e contatti con altri utenti all'esterno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3cf9c-113">Set up mailbox features such as the mailbox sharing policy: how users can share calendar and contacts information with others outside of your organization.</span></span>

- <span data-ttu-id="3cf9c-114">Configurare i delegati "[Invia come](give-mailbox-permissions-to-another-user.md#send-email-from-another-users-mailbox)" e " Invia per[conto](give-mailbox-permissions-to-another-user.md#send-email-on-behalf-of-another-user)di " per la cassetta postale di un utente.</span><span class="sxs-lookup"><span data-stu-id="3cf9c-114">Set up "[Send as](give-mailbox-permissions-to-another-user.md#send-email-from-another-users-mailbox)" and "[Send on behalf](give-mailbox-permissions-to-another-user.md#send-email-on-behalf-of-another-user)" delegates for someone's mailbox.</span></span> <span data-ttu-id="3cf9c-115">Ad esempio, un dirigente potrebbe richiedere che il proprio assistente possa inviare messaggi di posta elettronica per conto suo.</span><span class="sxs-lookup"><span data-stu-id="3cf9c-115">For example, an executive may want their assistant to have the ability to send mail on their behalf.</span></span>

- <span data-ttu-id="3cf9c-116">[Creare una cassetta postale condivisa in modo](../email/create-a-shared-mailbox.md) che un gruppo di persone possa monitorare e inviare messaggi di posta elettronica da un indirizzo di posta elettronica comune.</span><span class="sxs-lookup"><span data-stu-id="3cf9c-116">[Create a shared mailbox](../email/create-a-shared-mailbox.md) so a group of people can monitor and send email from a common email address.</span></span>

- <span data-ttu-id="3cf9c-117">[Filtri antispam e antimalware](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spam-protection) per la posta elettronica per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3cf9c-117">[Email anti-spam protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spam-protection) and malware filters for the organization.</span></span>

- <span data-ttu-id="3cf9c-118">Gestire gruppi di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3cf9c-118">Manage Microsoft 365 groups</span></span>

## <a name="exchange-online-role-groups"></a><span data-ttu-id="3cf9c-119">Gruppi di ruoli di Exchange Online</span><span class="sxs-lookup"><span data-stu-id="3cf9c-119">Exchange Online role groups</span></span>

<span data-ttu-id="3cf9c-p105">Se si ha un'organizzazione di grandi dimensioni, l'amministratore di Exchange può scegliere di assegnare gli utenti a gruppi di ruoli di Exchange. Quando un amministratore aggiunge un utente a un gruppo di ruoli, l'utente riceve le autorizzazioni per eseguire alcune funzioni aziendali consentite solo ai membri del gruppo.</span><span class="sxs-lookup"><span data-stu-id="3cf9c-p105">If you have a large organization, the Exchange admin might want to assign users to Exchange role groups. When an admin adds a user to a role group, the user gets permissions to perform certain business functions only members of that group can do.</span></span>
  
 <span data-ttu-id="3cf9c-p106">Ad esempio, l'amministratore di Exchange può assegnare un utente al gruppo di ruoli Gestione individuazione in modo che possa eseguire ricerche nelle cassette postali per i dati che soddisfano determinati criteri. Per altre informazioni, vedere [Autorizzazioni in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) e [Gestire gruppi di ruoli](https://docs.microsoft.com/exchange/manage-role-groups-exchange-2013-help).</span><span class="sxs-lookup"><span data-stu-id="3cf9c-p106">For example, the Exchange admin might assign someone to the Discovery Management role group so they can perform searches of mailboxes for data that meets certain criteria. To learn more, see [Permissions in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) and [Manage Role Groups](https://docs.microsoft.com/exchange/manage-role-groups-exchange-2013-help).</span></span>
  
## <a name="learn-about-other-admin-roles"></a><span data-ttu-id="3cf9c-124">Informazioni su altri ruoli di amministratore</span><span class="sxs-lookup"><span data-stu-id="3cf9c-124">Learn about other admin roles</span></span>

- [<span data-ttu-id="3cf9c-125">Informazioni sui ruoli di amministratore di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3cf9c-125">About Microsoft 365 admin roles</span></span>](about-admin-roles.md)

- [<span data-ttu-id="3cf9c-126">Informazioni sul ruolo di amministratore di SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="3cf9c-126">About the SharePoint Online admin role</span></span>](https://docs.microsoft.com/sharepoint/sharepoint-admin-role)

- [<span data-ttu-id="3cf9c-127">Informazioni sul ruolo di amministratore di Skype for Business</span><span class="sxs-lookup"><span data-stu-id="3cf9c-127">About the Skype for Business admin role</span></span>](https://docs.microsoft.com/skypeforbusiness/skype-for-business-online)

- [<span data-ttu-id="3cf9c-128">Usare il ruolo di amministratore di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3cf9c-128">Use Microsoft Teams admin role</span></span>](https://docs.microsoft.com/MicrosoftTeams/using-admin-roles) 
