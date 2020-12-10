---
title: Concedere agli utenti l'accesso al Centro sicurezza e conformità
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
f1_keywords:
- ms.o365.cc.PermissionsHelp
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 2cfce2c8-20c5-47f9-afc4-24b059c1bd76
description: Gli utenti devono disporre delle autorizzazioni nel centro conformità di sicurezza & Microsoft 365 prima di poter gestire qualsiasi funzionalità di sicurezza o conformità.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1bf8da85a0e090a9d74934ea5084f547d6a8794f
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616609"
---
# <a name="give-users-access-to-the-security--compliance-center"></a><span data-ttu-id="b399f-103">Concedere agli utenti l'accesso al Centro sicurezza e conformità</span><span class="sxs-lookup"><span data-stu-id="b399f-103">Give users access to the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="b399f-104">Gli utenti devono disporre delle autorizzazioni nel centro sicurezza & compliance prima di poter gestire qualsiasi funzionalità di sicurezza o conformità.</span><span class="sxs-lookup"><span data-stu-id="b399f-104">Users need to be assigned permissions in the Security & Compliance Center before they can manage any of its security or compliance features.</span></span> <span data-ttu-id="b399f-105">In qualità di amministratore globale o membro del gruppo di ruoli OrganizationManagement nel centro sicurezza & conformità, è possibile concedere queste autorizzazioni agli utenti.</span><span class="sxs-lookup"><span data-stu-id="b399f-105">As a global admin or member of the OrganizationManagement role group in the Security & Compliance Center, you can give these permissions to users.</span></span> <span data-ttu-id="b399f-106">Gli utenti potranno solo gestire le funzionalità di sicurezza o conformità per le quali è stato concesso loro l'accesso.</span><span class="sxs-lookup"><span data-stu-id="b399f-106">Users will only be able to manage the security or compliance features that you give them access to.</span></span>

<span data-ttu-id="b399f-107">Per ulteriori informazioni sulle diverse autorizzazioni che è possibile assegnare agli utenti nel centro sicurezza & conformità, vedere [autorizzazioni nel centro sicurezza & conformità](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="b399f-107">For more information about the different permissions you can give to users in the Security & Compliance Center, check out [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="b399f-108">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="b399f-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="b399f-109">Per completare la procedura descritta in questo articolo, è necessario essere un amministratore globale o un membro del gruppo di ruoli OrganizationManagement nel centro sicurezza & Compliance.</span><span class="sxs-lookup"><span data-stu-id="b399f-109">You need to be a global admin, or a member of the OrganizationManagement role group in the Security & Compliance Center, to complete the steps in this article.</span></span>

- <span data-ttu-id="b399f-110">I gruppi di ruoli per il Centro sicurezza & conformità potrebbero avere nomi simili ai gruppi di ruoli in Exchange Online, ma non sono gli stessi.</span><span class="sxs-lookup"><span data-stu-id="b399f-110">Role groups for the Security & Compliance Center might have similar names to the role groups in Exchange Online, but they're not the same.</span></span>

- <span data-ttu-id="b399f-111">Le appartenenze ai gruppi di ruoli non sono condivise tra Exchange Online e il Centro sicurezza & conformità.</span><span class="sxs-lookup"><span data-stu-id="b399f-111">Role group memberships aren't shared between Exchange Online and the Security & Compliance Center.</span></span>

- <span data-ttu-id="b399f-112">I partner di autorizzazione accesso delegato (DAP) con amministra per conto di (AOBO) le autorizzazioni non possono accedere al centro sicurezza & conformità.</span><span class="sxs-lookup"><span data-stu-id="b399f-112">Delegated Access Permission (DAP) partners with Administer On Behalf Of (AOBO) permissions can't access the Security & Compliance Center.</span></span>

## <a name="use-the-security--compliance-center-to-give-another-user-access-to-the-security--compliance-center"></a><span data-ttu-id="b399f-113">Utilizzare il Centro sicurezza & conformità per consentire a un altro utente di accedere al centro sicurezza & conformità</span><span class="sxs-lookup"><span data-stu-id="b399f-113">Use the Security & Compliance Center to give another user access to the Security & Compliance Center</span></span>

1. <span data-ttu-id="b399f-114">Aprire il Centro sicurezza & conformità <https://protection.office.com> e quindi andare a **autorizzazioni**.</span><span class="sxs-lookup"><span data-stu-id="b399f-114">Open the Security & Compliance Center at <https://protection.office.com> and then go to **Permissions**.</span></span> <span data-ttu-id="b399f-115">Per passare direttamente alla scheda **autorizzazioni** , Apri <https://protection.office.com/permissions> .</span><span class="sxs-lookup"><span data-stu-id="b399f-115">To go directly to the **Permissions** tab, open <https://protection.office.com/permissions>.</span></span>

2. <span data-ttu-id="b399f-116">Nell'elenco dei gruppi di ruoli, scegliere il gruppo di ruoli, quindi fare clic su **modifica** ![ icona modifica ](../../media/O365-MDM-CreatePolicy-EditIcon.gif) .</span><span class="sxs-lookup"><span data-stu-id="b399f-116">From the list of role groups, choose the role group, and then click **Edit** ![Edit icon](../../media/O365-MDM-CreatePolicy-EditIcon.gif).</span></span>

3. <span data-ttu-id="b399f-117">Nella pagina delle proprietà del gruppo di ruoli in **membri** fare clic su **Aggiungi** ![ icona ](../../media/ITPro-EAC-AddIcon.gif) e selezionare il nome dell'utente (o degli utenti) che si desidera aggiungere.</span><span class="sxs-lookup"><span data-stu-id="b399f-117">In the role group's properties page under **Members**, click **Add**![Add Icon](../../media/ITPro-EAC-AddIcon.gif) and select the name of the user (or users) you want to add.</span></span>

4. <span data-ttu-id="b399f-118">Dopo aver selezionato tutti gli utenti che si desidera aggiungere al gruppo di ruoli, fare clic su **Aggiungi \>** e quindi su **OK**.</span><span class="sxs-lookup"><span data-stu-id="b399f-118">When you've selected all of the users you want to add to the role group, click **add-\>** and then **OK**.</span></span>

5. <span data-ttu-id="b399f-119">Al termine, scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="b399f-119">When you're finished, click **Save**.</span></span>

## <a name="use-security--compliance-center-powershell-to-give-another-user-access-to-the-security--compliance-center"></a><span data-ttu-id="b399f-120">Utilizzare la sicurezza & Compliance Center PowerShell per concedere a un altro utente l'accesso al centro sicurezza & conformità</span><span class="sxs-lookup"><span data-stu-id="b399f-120">Use Security & Compliance Center PowerShell to give another user access to the Security & Compliance Center</span></span>

1. <span data-ttu-id="b399f-121">[Connettersi a PowerShell in Centro sicurezza e conformità](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="b399f-121">[Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="b399f-122">Utilizzare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="b399f-122">Use the following syntax:</span></span>

   ```powershell
   Add-RoleGroupMember -Identity <RoleGroup> -Member <UserIdentity>

   - _Identity_ is the role group.
   - _Member_ is the user or universal security group (USG). You can specify only one member at a time.

   This example adds MatildaS to the Organization Management role group.

   ```PowerShell
   Add-RoleGroupMember -Identity "Organization Management" -Member MatildaS
   ```

<span data-ttu-id="b399f-123">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Add-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/add-rolegroupmember)</span><span class="sxs-lookup"><span data-stu-id="b399f-123">For detailed syntax and parameter issues, see [Add-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/add-rolegroupmember)</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="b399f-124">Come verificare se l'operazione ha avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="b399f-124">How do you know this worked?</span></span>

<span data-ttu-id="b399f-125">Per verificare di aver correttamente concesso l'accesso al centro sicurezza & Compliance, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b399f-125">To verify that you've successfully granted access to the Security & Compliance Center, do either of the following steps:</span></span>

- <span data-ttu-id="b399f-126">Nel centro sicurezza & conformità, accedere a **autorizzazioni** e selezionare il gruppo di ruoli.</span><span class="sxs-lookup"><span data-stu-id="b399f-126">In the Security & Compliance Center, go to **Permissions** and select the role group.</span></span> <span data-ttu-id="b399f-127">Nel riquadro a comparsa dettagli che si apre, verificare i membri del gruppo di ruoli.</span><span class="sxs-lookup"><span data-stu-id="b399f-127">In the details flyout that opens, verify the members of the role group.</span></span>

- <span data-ttu-id="b399f-128">In PowerShell Centro sicurezza & conformità, sostituire \<RoleGroupName\> con il nome del gruppo di ruolo ed eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="b399f-128">In Security & Compliance Center PowerShell, replace \<RoleGroupName\> with the name of the role group, and run the following command:</span></span>

  ```powershell
  Get-RoleGroupMember -Identity "<RoleGroupName>"
  ```

  <span data-ttu-id="b399f-129">Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Get-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroupMember).</span><span class="sxs-lookup"><span data-stu-id="b399f-129">For detailed syntax and parameter information, see [Get-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroupMember).</span></span>
