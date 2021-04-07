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
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 2cfce2c8-20c5-47f9-afc4-24b059c1bd76
description: Gli utenti devono disporre delle autorizzazioni nel Centro sicurezza & e conformità di Microsoft 365 prima di poter gestire qualsiasi funzionalità di sicurezza o conformità.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7cd36ac0dec20851a423acd58e5ad7d38cb65d93
ms.sourcegitcommit: 7ee50882cb4ed37794a3cd82dac9b2f9e0a1f14a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/06/2021
ms.locfileid: "51599924"
---
# <a name="give-users-access-to-the-security--compliance-center"></a><span data-ttu-id="e781a-103">Concedere agli utenti l'accesso al Centro sicurezza e conformità</span><span class="sxs-lookup"><span data-stu-id="e781a-103">Give users access to the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="e781a-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="e781a-104">**Applies to**</span></span>
- [<span data-ttu-id="e781a-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="e781a-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="e781a-106">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="e781a-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="e781a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e781a-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="e781a-108">Gli utenti devono disporre delle autorizzazioni nel Centro sicurezza & conformità prima di poter gestire qualsiasi funzionalità di sicurezza o conformità.</span><span class="sxs-lookup"><span data-stu-id="e781a-108">Users need to be assigned permissions in the Security & Compliance Center before they can manage any of its security or compliance features.</span></span> <span data-ttu-id="e781a-109">In quanto amministratore globale o membro del gruppo di ruoli OrganizationManagement nel Centro sicurezza & conformità, è possibile concedere queste autorizzazioni agli utenti.</span><span class="sxs-lookup"><span data-stu-id="e781a-109">As a global admin or member of the OrganizationManagement role group in the Security & Compliance Center, you can give these permissions to users.</span></span> <span data-ttu-id="e781a-110">Gli utenti potranno solo gestire le funzionalità di sicurezza o conformità per le quali è stato concesso loro l'accesso.</span><span class="sxs-lookup"><span data-stu-id="e781a-110">Users will only be able to manage the security or compliance features that you give them access to.</span></span>

<span data-ttu-id="e781a-111">Per ulteriori informazioni sulle diverse autorizzazioni che è possibile concedere agli utenti nel Centro sicurezza & conformità, vedere Autorizzazioni nel [Centro sicurezza & conformità.](permissions-in-the-security-and-compliance-center.md)</span><span class="sxs-lookup"><span data-stu-id="e781a-111">For more information about the different permissions you can give to users in the Security & Compliance Center, check out [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="e781a-112">Che cosa è necessario sapere prima di iniziare?</span><span class="sxs-lookup"><span data-stu-id="e781a-112">What do you need to know before you begin?</span></span>

- <span data-ttu-id="e781a-113">Per completare i passaggi descritti in questo articolo, è necessario essere un amministratore globale o un membro del gruppo di ruoli OrganizationManagement nel Centro sicurezza & conformità.</span><span class="sxs-lookup"><span data-stu-id="e781a-113">You need to be a global admin, or a member of the OrganizationManagement role group in the Security & Compliance Center, to complete the steps in this article.</span></span>

- <span data-ttu-id="e781a-114">I gruppi di ruoli per il Centro sicurezza & conformità potrebbero avere nomi simili ai gruppi di ruoli in Exchange Online, ma non sono uguali.</span><span class="sxs-lookup"><span data-stu-id="e781a-114">Role groups for the Security & Compliance Center might have similar names to the role groups in Exchange Online, but they're not the same.</span></span>

- <span data-ttu-id="e781a-115">Le appartenenze ai gruppi di ruoli non vengono condivise tra Exchange Online e il Centro sicurezza & conformità.</span><span class="sxs-lookup"><span data-stu-id="e781a-115">Role group memberships aren't shared between Exchange Online and the Security & Compliance Center.</span></span>

- <span data-ttu-id="e781a-116">I partner con autorizzazioni di accesso delegato (DAP) con autorizzazioni Amministra per conto di (AOBO) non possono accedere al Centro sicurezza & conformità.</span><span class="sxs-lookup"><span data-stu-id="e781a-116">Delegated Access Permission (DAP) partners with Administer On Behalf Of (AOBO) permissions can't access the Security & Compliance Center.</span></span>

## <a name="use-the-security--compliance-center-to-give-another-user-access-to-the-security--compliance-center"></a><span data-ttu-id="e781a-117">Usare il Centro sicurezza & conformità per concedere a un altro utente l'accesso al Centro sicurezza & conformità</span><span class="sxs-lookup"><span data-stu-id="e781a-117">Use the Security & Compliance Center to give another user access to the Security & Compliance Center</span></span>

1. <span data-ttu-id="e781a-118">Aprire il Centro sicurezza & conformità <https://protection.office.com> in e quindi passare a **Autorizzazioni**.</span><span class="sxs-lookup"><span data-stu-id="e781a-118">Open the Security & Compliance Center at <https://protection.office.com> and then go to **Permissions**.</span></span> <span data-ttu-id="e781a-119">Per passare direttamente alla **scheda Autorizzazioni,** aprire <https://protection.office.com/permissions> .</span><span class="sxs-lookup"><span data-stu-id="e781a-119">To go directly to the **Permissions** tab, open <https://protection.office.com/permissions>.</span></span>

2. <span data-ttu-id="e781a-120">Nell'elenco dei gruppi di ruoli scegliere il gruppo di ruoli e quindi fare clic su **Modifica** ![ icona ](../../media/O365-MDM-CreatePolicy-EditIcon.gif) Modifica.</span><span class="sxs-lookup"><span data-stu-id="e781a-120">From the list of role groups, choose the role group, and then click **Edit** ![Edit icon](../../media/O365-MDM-CreatePolicy-EditIcon.gif).</span></span>

3. <span data-ttu-id="e781a-121">Nella pagina delle proprietà del gruppo di ruoli **in** Membri fare clic su Aggiungi Icona Aggiungi e selezionare il nome dell'utente (o degli ![ ](../../media/ITPro-EAC-AddIcon.gif) utenti) che si desidera aggiungere.</span><span class="sxs-lookup"><span data-stu-id="e781a-121">In the role group's properties page under **Members**, click **Add**![Add Icon](../../media/ITPro-EAC-AddIcon.gif) and select the name of the user (or users) you want to add.</span></span>

4. <span data-ttu-id="e781a-122">Dopo aver selezionato tutti gli utenti che si desidera aggiungere al gruppo di ruoli, fare clic su **aggiungi- \>** e quindi **su OK.**</span><span class="sxs-lookup"><span data-stu-id="e781a-122">When you've selected all of the users you want to add to the role group, click **add-\>** and then **OK**.</span></span>

5. <span data-ttu-id="e781a-123">Al termine, fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="e781a-123">When you're finished, click **Save**.</span></span>

## <a name="use-security--compliance-center-powershell-to-give-another-user-access-to-the-security--compliance-center"></a><span data-ttu-id="e781a-124">Usare PowerShell & Centro sicurezza e conformità per concedere a un altro utente l'accesso al Centro sicurezza & conformità</span><span class="sxs-lookup"><span data-stu-id="e781a-124">Use Security & Compliance Center PowerShell to give another user access to the Security & Compliance Center</span></span>

1. <span data-ttu-id="e781a-125">[Connettersi a PowerShell in Centro sicurezza e conformità](/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="e781a-125">[Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="e781a-126">Usare la sintassi seguente:</span><span class="sxs-lookup"><span data-stu-id="e781a-126">Use the following syntax:</span></span>

   ```powershell
   Add-RoleGroupMember -Identity <RoleGroup> -Member <UserIdentity>

   - _Identity_ is the role group.
   - _Member_ is the user or universal security group (USG). You can specify only one member at a time.

   This example adds MatildaS to the Organization Management role group.

   ```PowerShell
   Add-RoleGroupMember -Identity "Organization Management" -Member MatildaS
   ```

<span data-ttu-id="e781a-127">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Add-RoleGroupMember](/powershell/module/exchange/add-rolegroupmember)</span><span class="sxs-lookup"><span data-stu-id="e781a-127">For detailed syntax and parameter issues, see [Add-RoleGroupMember](/powershell/module/exchange/add-rolegroupmember)</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="e781a-128">Come verificare se l'operazione ha avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="e781a-128">How do you know this worked?</span></span>

<span data-ttu-id="e781a-129">Per verificare di aver concesso correttamente l'accesso al Centro sicurezza & conformità, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e781a-129">To verify that you've successfully granted access to the Security & Compliance Center, do either of the following steps:</span></span>

- <span data-ttu-id="e781a-130">Nel Centro sicurezza & conformità passare a **Autorizzazioni** e selezionare il gruppo di ruoli.</span><span class="sxs-lookup"><span data-stu-id="e781a-130">In the Security & Compliance Center, go to **Permissions** and select the role group.</span></span> <span data-ttu-id="e781a-131">Nel riquadro a comparsa dei dettagli che si apre, verificare i membri del gruppo di ruoli.</span><span class="sxs-lookup"><span data-stu-id="e781a-131">In the details flyout that opens, verify the members of the role group.</span></span>

- <span data-ttu-id="e781a-132">In PowerShell & Centro sicurezza e conformità sostituire con il nome del gruppo di ruoli \<RoleGroupName\> ed eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="e781a-132">In Security & Compliance Center PowerShell, replace \<RoleGroupName\> with the name of the role group, and run the following command:</span></span>

  ```powershell
  Get-RoleGroupMember -Identity "<RoleGroupName>"
  ```

  <span data-ttu-id="e781a-133">Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Get-RoleGroupMember](/powershell/module/exchange/Get-RoleGroupMember).</span><span class="sxs-lookup"><span data-stu-id="e781a-133">For detailed syntax and parameter information, see [Get-RoleGroupMember](/powershell/module/exchange/Get-RoleGroupMember).</span></span>