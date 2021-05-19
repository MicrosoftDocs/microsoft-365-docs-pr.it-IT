---
title: Consenti ai membri di inviare come o inviare per conto di un gruppo
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- m365solution-collabgovernance
search.appverid:
- MET150
ms.assetid: 0ad41414-0cc6-4b97-90fb-06bec7bcf590
recommendations: false
description: Informazioni su come consentire ai membri del gruppo di inviare posta elettronica come Microsoft 365 o inviare messaggi di posta elettronica per conto di un Microsoft 365 gruppo.
ms.openlocfilehash: 07db8f415da46e6235c051e262237de79e61c8b9
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538256"
---
# <a name="allow-members-to-send-as-or-send-on-behalf-of-a-group"></a><span data-ttu-id="05da6-103">Consenti ai membri di inviare come o inviare per conto di un gruppo</span><span class="sxs-lookup"><span data-stu-id="05da6-103">Allow members to send as or send on behalf of a group</span></span>

<span data-ttu-id="05da6-104">Un membro di un Microsoft 365 a cui  sono  state concesse le autorizzazioni Invia come o Invia per conto di può inviare messaggi di posta elettronica come gruppo o per conto del gruppo.</span><span class="sxs-lookup"><span data-stu-id="05da6-104">A member of a Microsoft 365 group who has been granted **Send as** or **Send on behalf** permissions can send email as the group, or on behalf of the group.</span></span> <span data-ttu-id="05da6-105">Non è possibile concedere queste autorizzazioni agli utenti guest del gruppo.</span><span class="sxs-lookup"><span data-stu-id="05da6-105">(Guests in the group cannot be granted these permissions.)</span></span>

<span data-ttu-id="05da6-106">In questo articolo viene illustrato come un amministratore globale o Exchange può impostare queste autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="05da6-106">This article explains how a global or Exchange administrator can set these permissions.</span></span>
  
<span data-ttu-id="05da6-107">Ad esempio, se Megan Bowen fa parte del gruppo  **Training** Microsoft 365 e dispone delle autorizzazioni Invia come per il  gruppo, se invia un messaggio di posta elettronica come gruppo, sarà simile al gruppo Formazione che ha inviato il messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="05da6-107">For example, if Megan Bowen is part of the **Training** Microsoft 365 group, and has **Send as** permissions on the group, if she sends an email as the group, it will look like the **Training** group sent the email.</span></span> 
  
<span data-ttu-id="05da6-108">**L'autorizzazione Invia per conto di** consente a un utente di inviare messaggi di posta elettronica per conto di un Microsoft 365 gruppo.</span><span class="sxs-lookup"><span data-stu-id="05da6-108">The **Send on Behalf** permission lets a user send email on behalf of a Microsoft 365 group.</span></span> <span data-ttu-id="05da6-109">Ad esempio, se Alex Wilber fa parte del gruppo **Marketing** Microsoft 365 e dispone delle autorizzazioni Invia per conto di e invia un messaggio di posta elettronica come gruppo, il messaggio di posta elettronica sembra essere stato inviato da **Alex Wilber** per conto di Marketing. </span><span class="sxs-lookup"><span data-stu-id="05da6-109">For example, if Alex Wilber is a part of the **Marketing** Microsoft 365 group, and has **Send on Behalf** permissions and sends an email as the group, the email looks like it was sent by **Alex Wilber on behalf of Marketing**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="05da6-110">È possibile configurare **Invia come** o Invia per **conto di** un determinato utente, ma non entrambi.</span><span class="sxs-lookup"><span data-stu-id="05da6-110">You can configure **Send as** or **Send on behalf** for a given user, but not both.</span></span> <span data-ttu-id="05da6-111">Se si configurano entrambi, per impostazione predefinita verrà **utilizzato Invia come**.</span><span class="sxs-lookup"><span data-stu-id="05da6-111">If you configure both, it will default to **Send as**.</span></span>

> [!TIP]
> <span data-ttu-id="05da6-112">Vedere [Send email from or on behalf of a Microsoft 365 group](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b) to learn how to use Outlook and Outlook on the Web to send email from a group.</span><span class="sxs-lookup"><span data-stu-id="05da6-112">See [Send email from or on behalf of a Microsoft 365 group](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b) to learn how to use Outlook and Outlook on the Web to send email from a group.</span></span>
    
## <a name="allow-members-to-send-email-as-a-group"></a><span data-ttu-id="05da6-113">Consentire ai membri di inviare messaggi di posta elettronica come gruppo</span><span class="sxs-lookup"><span data-stu-id="05da6-113">Allow members to send email as a group</span></span>

<span data-ttu-id="05da6-114">In questa sezione viene illustrato come consentire agli utenti di inviare messaggi di posta elettronica come gruppo nell'interfaccia di amministrazione di [Exchange](https://go.microsoft.com/fwlink/p/?linkid=2059104) (EAC) in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="05da6-114">This section explains how to allow users to send email as a group in the [Exchange admin center](https://go.microsoft.com/fwlink/p/?linkid=2059104) (EAC) in Exchange Online.</span></span>
  
1. <span data-ttu-id="05da6-115"><a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Nell'Exchange di amministrazione,</a>passare a **Destinatari** \> **Gruppi**.</span><span class="sxs-lookup"><span data-stu-id="05da6-115">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>, go to **Recipients** \> **Groups**.</span></span>
    
2. <span data-ttu-id="05da6-116">Selezionare **Modifica** ![ Icona modifica gruppo nel gruppo che si desidera consentire agli utenti ](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) di inviare come.  </span><span class="sxs-lookup"><span data-stu-id="05da6-116">Select **Edit**  ![Edit group icon](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) on the group that you want to allow users to send as.</span></span> 
    
3. <span data-ttu-id="05da6-117">Selezionare **delega gruppo**.</span><span class="sxs-lookup"><span data-stu-id="05da6-117">Select **group delegation**.</span></span>
    
4. <span data-ttu-id="05da6-118">Nella sezione **Invia come** selezionare il segno per aggiungere gli utenti che si **+** desidera inviare come gruppo.</span><span class="sxs-lookup"><span data-stu-id="05da6-118">In the **Send As** section, select the **+** sign to add the users that you want to send as the Group.</span></span> 
    
    ![Screenshot della finestra di dialogo Invia come](../media/1df167f6-1eff-4f98-9ecd-4230fab46557.png)
  
5. <span data-ttu-id="05da6-120">Digitare per cercare o selezionare un utente dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="05da6-120">Type to search or pick a user from the list.</span></span> <span data-ttu-id="05da6-121">Selezionare **OK** e **Salva**.</span><span class="sxs-lookup"><span data-stu-id="05da6-121">Select **OK** and **Save**.</span></span>
    
    ![Digitare per cercare o selezionare un utente dall'elenco](../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)
  
## <a name="allow-members-to-send-email-on-behalf-of-a-group"></a><span data-ttu-id="05da6-123">Consentire ai membri di inviare messaggi di posta elettronica per conto di un gruppo</span><span class="sxs-lookup"><span data-stu-id="05da6-123">Allow members to send email on behalf of a group</span></span>

<span data-ttu-id="05da6-124">In questa sezione viene illustrato come consentire agli utenti di inviare messaggi di posta elettronica per conto di un gruppo nell'interfaccia di amministrazione di Exchange (EAC) in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="05da6-124">This section explains how to allow users to send email on behalf of a group in the Exchange admin center (EAC) in Exchange Online.</span></span>
  
1. <span data-ttu-id="05da6-125"><a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Nell'Exchange di amministrazione,</a>passare a **Destinatari** \> **Gruppi**.</span><span class="sxs-lookup"><span data-stu-id="05da6-125">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>, go to **Recipients** \> **Groups**.</span></span>
    
2. <span data-ttu-id="05da6-126">Selezionare **Modifica** ![ Icona modifica gruppo nel gruppo che si desidera consentire agli utenti ](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) di inviare come.</span><span class="sxs-lookup"><span data-stu-id="05da6-126">Select **Edit** ![Edit group icon](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) on the group that you want to allow users to send as.</span></span> 
    
3. <span data-ttu-id="05da6-127">Selezionare **delega gruppo**.</span><span class="sxs-lookup"><span data-stu-id="05da6-127">Select **group delegation**.</span></span>
    
4. <span data-ttu-id="05da6-128">Nella sezione Invia per conto di selezionare il segno per aggiungere gli utenti **+** che si desidera inviare come gruppo.</span><span class="sxs-lookup"><span data-stu-id="05da6-128">In the Send on Behalf section, select the **+** sign to add the users that you want to send as the Group.</span></span> 
    
    ![Screenshot dell'invio per conto della finestra di dialogo](../media/2bae0579-8907-4d6b-8920-ddd6555897b4.png)
  
5. <span data-ttu-id="05da6-130">Digitare per cercare o selezionare un utente dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="05da6-130">Type to search or pick a user from the list.</span></span> <span data-ttu-id="05da6-131">Selezionare **OK** e **Salva**.</span><span class="sxs-lookup"><span data-stu-id="05da6-131">Select **OK** and **Save**.</span></span>
    
    ![Digitare per cercare o selezionare un utente dall'elenco](../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)

## <a name="related-articles"></a><span data-ttu-id="05da6-133">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="05da6-133">Related articles</span></span>

[<span data-ttu-id="05da6-134">Pianificazione dettagliata della governance della collaborazione</span><span class="sxs-lookup"><span data-stu-id="05da6-134">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="05da6-135">Creare il piano di governance della collaborazione</span><span class="sxs-lookup"><span data-stu-id="05da6-135">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)

[<span data-ttu-id="05da6-136">Ulteriori informazioni sui Microsoft 365 di lavoro</span><span class="sxs-lookup"><span data-stu-id="05da6-136">Learn more about Microsoft 365 groups</span></span>](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[<span data-ttu-id="05da6-137">Add-RecipientPermission</span><span class="sxs-lookup"><span data-stu-id="05da6-137">Add-RecipientPermission</span></span>](/powershell/module/exchange/add-recipientpermission)

[<span data-ttu-id="05da6-138">Set-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="05da6-138">Set-UnifiedGroup</span></span>](/powershell/module/exchange/set-unifiedgroup)