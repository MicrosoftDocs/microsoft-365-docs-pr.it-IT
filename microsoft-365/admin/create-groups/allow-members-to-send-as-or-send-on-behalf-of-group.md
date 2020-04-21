---
title: Consenti ai membri di inviare messaggi o Invia per conto di un gruppo
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0ad41414-0cc6-4b97-90fb-06bec7bcf590
description: Informazioni su come consentire ai membri di inviare messaggi di posta elettronica come gruppo di Microsoft 365 o di inviare messaggi di posta elettronica per conto di un gruppo di Microsoft 365.
ms.openlocfilehash: 4492c929fbd30ad77d9ddb23c37299e8734162df
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43630670"
---
# <a name="allow-members-to-send-as-or-send-on-behalf-of-a-group"></a><span data-ttu-id="4c1bb-103">Consenti ai membri di inviare messaggi o Invia per conto di un gruppo</span><span class="sxs-lookup"><span data-stu-id="4c1bb-103">Allow members to send as or send on behalf of a Group</span></span>

<span data-ttu-id="4c1bb-104">Un membro di un gruppo di Microsoft 365 a cui sono state concesse le autorizzazioni **Invia come** o **Invia per conto** di può inviare messaggi di posta elettronica come gruppo o per conto del gruppo.</span><span class="sxs-lookup"><span data-stu-id="4c1bb-104">A member of a Microsoft 365 group who has been granted **Send as** or **Send on behalf** permissions can send email as the group, or on behalf of the group.</span></span> <span data-ttu-id="4c1bb-105">In questo argomento viene illustrato in che modo un amministratore può impostare queste autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="4c1bb-105">This topic explains how an admin can set these permissions.</span></span>
  
<span data-ttu-id="4c1bb-106">Ad esempio, se Megan Bowen fa parte del gruppo **Training** Microsoft 365 e ha l'autorizzazione **Invia come** per il gruppo, se invia un messaggio di posta elettronica come gruppo, avrà l'aspetto del gruppo di **formazione** inviato al messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="4c1bb-106">For example, if Megan Bowen is part of the **Training** Microsoft 365 group, and has **Send as** permissions on the group, if she sends an email as the group, it will look like the **Training** group sent the email.</span></span> 
  
<span data-ttu-id="4c1bb-107">L'autorizzazione **Invia per conto** di consente a un utente di inviare messaggi di posta elettronica per conto di un gruppo di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4c1bb-107">The **Send on Behalf** permission lets a user send email on behalf of a Microsoft 365 group.</span></span> <span data-ttu-id="4c1bb-108">Ad esempio, se Alex Wilber è parte del gruppo **Marketing** Microsoft 365 e ha l'autorizzazione **Invia per conto** di e invia un messaggio di posta elettronica come gruppo, il messaggio di posta elettronica è simile a quello inviato da **Alex Wilber per conto del marketing**.</span><span class="sxs-lookup"><span data-stu-id="4c1bb-108">For example, if Alex Wilber is a part of the **Marketing** Microsoft 365 group, and has **Send on Behalf** permissions and sends an email as the group, the email looks like it was sent by **Alex Wilber on behalf of Marketing**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4c1bb-109">È possibile configurare **Invia come** o **Invia per conto** di un utente specificato, ma non di entrambi.</span><span class="sxs-lookup"><span data-stu-id="4c1bb-109">You can configure **Send as** or **Send on behalf** for a given user, but not both.</span></span> <span data-ttu-id="4c1bb-110">Se si configurano entrambi, il valore predefinito sarà **Send As**.</span><span class="sxs-lookup"><span data-stu-id="4c1bb-110">If you configure both, it will default to **Send as**.</span></span>

> [!TIP]
> <span data-ttu-id="4c1bb-111">Vedere [inviare messaggi di posta elettronica da o per conto di un gruppo di Microsoft 365](https://support.office.com/article/0f4964af-aec6-484b-a65c-0434df8cdb6b.aspx) per informazioni su come utilizzare Outlook e Outlook sul Web per inviare messaggi di posta elettronica da un gruppo.</span><span class="sxs-lookup"><span data-stu-id="4c1bb-111">See [Send email from or on behalf of a Microsoft 365 group](https://support.office.com/article/0f4964af-aec6-484b-a65c-0434df8cdb6b.aspx) to learn how to use Outlook and Outlook on the Web to send email from a group.</span></span>
    
## <a name="allow-members-to-send-email-as-a-group"></a><span data-ttu-id="4c1bb-112">Consenti ai membri di inviare messaggi di posta elettronica come gruppo</span><span class="sxs-lookup"><span data-stu-id="4c1bb-112">Allow members to send email as a group</span></span>

<span data-ttu-id="4c1bb-113">In questa sezione viene descritto come consentire agli utenti di inviare messaggi di posta elettronica come gruppo nell'interfaccia di [amministrazione di Exchange](https://go.microsoft.com/fwlink/p/?linkid=2059104) (EAC) in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="4c1bb-113">This section explains how to allow users to send email as a group in the [Exchange admin center](https://go.microsoft.com/fwlink/p/?linkid=2059104) (EAC) in Exchange Online.</span></span>
  
1. <span data-ttu-id="4c1bb-114">Nell'interfaccia <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">di amministrazione di Exchange</a>, accedere a **gruppi**di **destinatari** \> .</span><span class="sxs-lookup"><span data-stu-id="4c1bb-114">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>, go to **Recipients** \> **Groups**.</span></span>
    
2. <span data-ttu-id="4c1bb-115">Selezionare **modifica**![icona](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) gruppo modifica sul gruppo che si desidera consentire agli utenti di inviare.  </span><span class="sxs-lookup"><span data-stu-id="4c1bb-115">Select **Edit**  ![Edit group icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) on Group that you want to allow users to send as.</span></span> 
    
3. <span data-ttu-id="4c1bb-116">Selezionare **delega gruppo**.</span><span class="sxs-lookup"><span data-stu-id="4c1bb-116">Select **group delegation**.</span></span>
    
4. <span data-ttu-id="4c1bb-117">Nella sezione **Invia come** selezionare il **+** segno per aggiungere gli utenti che si desidera inviare come gruppo.</span><span class="sxs-lookup"><span data-stu-id="4c1bb-117">In the **Send As** section, select the **+** sign to add the users that you want to send as the Group.</span></span> 
    
    ![Selezionare il segno più per aggiungere gli utenti che si desidera inviare come gruppo Microsoft 365](../../media/1df167f6-1eff-4f98-9ecd-4230fab46557.png)
  
5. <span data-ttu-id="4c1bb-119">Digitare per cercare o selezionare un utente dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="4c1bb-119">Type to search or pick a user from the list.</span></span> <span data-ttu-id="4c1bb-120">Fare clic su **OK** e su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="4c1bb-120">Select **OK** and **Save**.</span></span>
    
    ![Digitare per cercare o selezionare un utente dall'elenco](../../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)
  
## <a name="allow-members-to-send-email-on-behalf-of-a-group"></a><span data-ttu-id="4c1bb-122">Consenti ai membri di inviare messaggi di posta elettronica per conto di un gruppo</span><span class="sxs-lookup"><span data-stu-id="4c1bb-122">Allow members to send email on behalf of a group</span></span>

<span data-ttu-id="4c1bb-123">In questa sezione viene descritto come consentire agli utenti di inviare messaggi di posta elettronica per conto di un gruppo nell'interfaccia di amministrazione di Exchange (EAC) in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="4c1bb-123">This section explains how to allow users to send email on behalf of a group in the Exchange admin center (EAC) in Exchange Online.</span></span>
  
1. <span data-ttu-id="4c1bb-124">Nell'interfaccia <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">di amministrazione di Exchange</a>, accedere a **gruppi**di **destinatari** \> .</span><span class="sxs-lookup"><span data-stu-id="4c1bb-124">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>, go to **Recipients** \> **Groups**.</span></span>
    
2. <span data-ttu-id="4c1bb-125">Selezionare **modifica** ![icona](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) di modifica gruppo sul gruppo che si desidera consentire agli utenti di inviare.</span><span class="sxs-lookup"><span data-stu-id="4c1bb-125">Select **Edit** ![Edit group icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) on the Group that you want to allow users to send as.</span></span> 
    
3. <span data-ttu-id="4c1bb-126">Selezionare **delega gruppo**.</span><span class="sxs-lookup"><span data-stu-id="4c1bb-126">Select **group delegation**.</span></span>
    
4. <span data-ttu-id="4c1bb-127">Nella sezione Invia per conto di selezionare il **+** segno per aggiungere gli utenti che si desidera inviare come gruppo.</span><span class="sxs-lookup"><span data-stu-id="4c1bb-127">In the Send on Behalf section, select the **+** sign to add the users that you want to send as the Group.</span></span> 
    
    ![Selezionare il segno più per aggiungere gli utenti che si desidera inviare come gruppo Microsoft 365](../../media/2bae0579-8907-4d6b-8920-ddd6555897b4.png)
  
5. <span data-ttu-id="4c1bb-129">Digitare per cercare o selezionare un utente dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="4c1bb-129">Type to search or pick a user from the list.</span></span> <span data-ttu-id="4c1bb-130">Fare clic su **OK** e su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="4c1bb-130">Select **OK** and **Save**.</span></span>
    
    ![Digitare per cercare o selezionare un utente dall'elenco](../../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)

## <a name="related-articles"></a><span data-ttu-id="4c1bb-132">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="4c1bb-132">Related articles</span></span>

[<span data-ttu-id="4c1bb-133">Altre informazioni sui gruppi di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4c1bb-133">Learn more about Microsoft 365 groups</span></span>](https://support.office.com/article/3f780e8e-61aa-4287-830d-ff6209cbc192.aspx)

[<span data-ttu-id="4c1bb-134">Add-RecipientPermission</span><span class="sxs-lookup"><span data-stu-id="4c1bb-134">Add-RecipientPermission</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=723960)

[<span data-ttu-id="4c1bb-135">Set-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="4c1bb-135">Set-UnifiedGroup</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616189)
