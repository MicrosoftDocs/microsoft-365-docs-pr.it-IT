---
title: Consenti ai membri di inviare messaggi o Invia per conto di un gruppo
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
description: Informazioni su come consentire ai membri di inviare messaggi di posta elettronica come gruppo di Microsoft 365 o di inviare messaggi di posta elettronica per conto di un gruppo di Microsoft 365.
ms.openlocfilehash: 2abf0668411ccd08db5bbd8408605dcd0aa2d832
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "49613573"
---
# <a name="allow-members-to-send-as-or-send-on-behalf-of-a-group"></a><span data-ttu-id="5cdbc-103">Consenti ai membri di inviare messaggi o Invia per conto di un gruppo</span><span class="sxs-lookup"><span data-stu-id="5cdbc-103">Allow members to send as or send on behalf of a group</span></span>

<span data-ttu-id="5cdbc-104">Un membro di un gruppo di Microsoft 365 a cui sono state concesse le autorizzazioni **Invia come** o **Invia per conto** di può inviare messaggi di posta elettronica come gruppo o per conto del gruppo.</span><span class="sxs-lookup"><span data-stu-id="5cdbc-104">A member of a Microsoft 365 group who has been granted **Send as** or **Send on behalf** permissions can send email as the group, or on behalf of the group.</span></span> <span data-ttu-id="5cdbc-105">In questo articolo viene illustrato in che modo un amministratore può impostare queste autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="5cdbc-105">This article explains how an admin can set these permissions.</span></span>
  
<span data-ttu-id="5cdbc-106">Ad esempio, se Megan Bowen fa parte del gruppo **Training** Microsoft 365 e ha l'autorizzazione **Invia come** per il gruppo, se invia un messaggio di posta elettronica come gruppo, avrà l'aspetto del gruppo di **formazione** inviato al messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="5cdbc-106">For example, if Megan Bowen is part of the **Training** Microsoft 365 group, and has **Send as** permissions on the group, if she sends an email as the group, it will look like the **Training** group sent the email.</span></span> 
  
<span data-ttu-id="5cdbc-107">L'autorizzazione **Invia per conto** di consente a un utente di inviare messaggi di posta elettronica per conto di un gruppo di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5cdbc-107">The **Send on Behalf** permission lets a user send email on behalf of a Microsoft 365 group.</span></span> <span data-ttu-id="5cdbc-108">Ad esempio, se Alex Wilber è parte del gruppo **Marketing** Microsoft 365 e ha l'autorizzazione **Invia per conto** di e invia un messaggio di posta elettronica come gruppo, il messaggio di posta elettronica è simile a quello inviato da **Alex Wilber per conto del marketing**.</span><span class="sxs-lookup"><span data-stu-id="5cdbc-108">For example, if Alex Wilber is a part of the **Marketing** Microsoft 365 group, and has **Send on Behalf** permissions and sends an email as the group, the email looks like it was sent by **Alex Wilber on behalf of Marketing**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5cdbc-109">È possibile configurare **Invia come** o **Invia per conto** di un utente specificato, ma non di entrambi.</span><span class="sxs-lookup"><span data-stu-id="5cdbc-109">You can configure **Send as** or **Send on behalf** for a given user, but not both.</span></span> <span data-ttu-id="5cdbc-110">Se si configurano entrambi, il valore predefinito sarà **Send As**.</span><span class="sxs-lookup"><span data-stu-id="5cdbc-110">If you configure both, it will default to **Send as**.</span></span>

> [!TIP]
> <span data-ttu-id="5cdbc-111">Vedere [inviare messaggi di posta elettronica da o per conto di un gruppo di Microsoft 365](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b) per informazioni su come utilizzare Outlook e Outlook sul Web per inviare messaggi di posta elettronica da un gruppo.</span><span class="sxs-lookup"><span data-stu-id="5cdbc-111">See [Send email from or on behalf of a Microsoft 365 group](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b) to learn how to use Outlook and Outlook on the Web to send email from a group.</span></span>
    
## <a name="allow-members-to-send-email-as-a-group"></a><span data-ttu-id="5cdbc-112">Consenti ai membri di inviare messaggi di posta elettronica come gruppo</span><span class="sxs-lookup"><span data-stu-id="5cdbc-112">Allow members to send email as a group</span></span>

<span data-ttu-id="5cdbc-113">In questa sezione viene descritto come consentire agli utenti di inviare messaggi di posta elettronica come gruppo nell'interfaccia di [amministrazione di Exchange](https://go.microsoft.com/fwlink/p/?linkid=2059104) (EAC) in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="5cdbc-113">This section explains how to allow users to send email as a group in the [Exchange admin center](https://go.microsoft.com/fwlink/p/?linkid=2059104) (EAC) in Exchange Online.</span></span>
  
1. <span data-ttu-id="5cdbc-114">Nell'interfaccia di <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">amministrazione di Exchange</a>, accedere a gruppi di **destinatari** \> .</span><span class="sxs-lookup"><span data-stu-id="5cdbc-114">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>, go to **Recipients** \> **Groups**.</span></span>
    
2. <span data-ttu-id="5cdbc-115">Selezionare **modifica** ![ icona di modifica gruppo ](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) sul gruppo che si desidera consentire agli utenti di inviare.  </span><span class="sxs-lookup"><span data-stu-id="5cdbc-115">Select **Edit**  ![Edit group icon](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) on the group that you want to allow users to send as.</span></span> 
    
3. <span data-ttu-id="5cdbc-116">Selezionare **delega gruppo**.</span><span class="sxs-lookup"><span data-stu-id="5cdbc-116">Select **group delegation**.</span></span>
    
4. <span data-ttu-id="5cdbc-117">Nella sezione **Invia come** selezionare il **+** segno per aggiungere gli utenti che si desidera inviare come gruppo.</span><span class="sxs-lookup"><span data-stu-id="5cdbc-117">In the **Send As** section, select the **+** sign to add the users that you want to send as the Group.</span></span> 
    
    ![Schermata della finestra di dialogo Invia come](../media/1df167f6-1eff-4f98-9ecd-4230fab46557.png)
  
5. <span data-ttu-id="5cdbc-119">Digitare per cercare o selezionare un utente dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="5cdbc-119">Type to search or pick a user from the list.</span></span> <span data-ttu-id="5cdbc-120">Fare clic su **OK** e su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="5cdbc-120">Select **OK** and **Save**.</span></span>
    
    ![Digitare per cercare o selezionare un utente dall'elenco](../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)
  
## <a name="allow-members-to-send-email-on-behalf-of-a-group"></a><span data-ttu-id="5cdbc-122">Consenti ai membri di inviare messaggi di posta elettronica per conto di un gruppo</span><span class="sxs-lookup"><span data-stu-id="5cdbc-122">Allow members to send email on behalf of a group</span></span>

<span data-ttu-id="5cdbc-123">In questa sezione viene descritto come consentire agli utenti di inviare messaggi di posta elettronica per conto di un gruppo nell'interfaccia di amministrazione di Exchange (EAC) in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="5cdbc-123">This section explains how to allow users to send email on behalf of a group in the Exchange admin center (EAC) in Exchange Online.</span></span>
  
1. <span data-ttu-id="5cdbc-124">Nell'interfaccia di <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">amministrazione di Exchange</a>, accedere a gruppi di **destinatari** \> .</span><span class="sxs-lookup"><span data-stu-id="5cdbc-124">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>, go to **Recipients** \> **Groups**.</span></span>
    
2. <span data-ttu-id="5cdbc-125">Selezionare **modifica** ![ icona di modifica gruppo ](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) sul gruppo che si desidera consentire agli utenti di inviare.</span><span class="sxs-lookup"><span data-stu-id="5cdbc-125">Select **Edit** ![Edit group icon](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) on the group that you want to allow users to send as.</span></span> 
    
3. <span data-ttu-id="5cdbc-126">Selezionare **delega gruppo**.</span><span class="sxs-lookup"><span data-stu-id="5cdbc-126">Select **group delegation**.</span></span>
    
4. <span data-ttu-id="5cdbc-127">Nella sezione Invia per conto di selezionare il **+** segno per aggiungere gli utenti che si desidera inviare come gruppo.</span><span class="sxs-lookup"><span data-stu-id="5cdbc-127">In the Send on Behalf section, select the **+** sign to add the users that you want to send as the Group.</span></span> 
    
    ![Schermata di invio per conto della finestra di dialogo](../media/2bae0579-8907-4d6b-8920-ddd6555897b4.png)
  
5. <span data-ttu-id="5cdbc-129">Digitare per cercare o selezionare un utente dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="5cdbc-129">Type to search or pick a user from the list.</span></span> <span data-ttu-id="5cdbc-130">Fare clic su **OK** e su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="5cdbc-130">Select **OK** and **Save**.</span></span>
    
    ![Digitare per cercare o selezionare un utente dall'elenco](../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)

## <a name="related-articles"></a><span data-ttu-id="5cdbc-132">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="5cdbc-132">Related articles</span></span>

[<span data-ttu-id="5cdbc-133">Pianificazione della governance della collaborazione</span><span class="sxs-lookup"><span data-stu-id="5cdbc-133">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="5cdbc-134">Creare il piano di governance di collaborazione</span><span class="sxs-lookup"><span data-stu-id="5cdbc-134">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)

[<span data-ttu-id="5cdbc-135">Altre informazioni sui gruppi di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5cdbc-135">Learn more about Microsoft 365 groups</span></span>](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[<span data-ttu-id="5cdbc-136">Add-RecipientPermission</span><span class="sxs-lookup"><span data-stu-id="5cdbc-136">Add-RecipientPermission</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=723960)

[<span data-ttu-id="5cdbc-137">Set-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="5cdbc-137">Set-UnifiedGroup</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616189)
