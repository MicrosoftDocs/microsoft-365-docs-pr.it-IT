---
title: Creare record DNS in Yahoo! Small Business per Microsoft
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 034bd7bc-b098-4c4d-8a93-4d74ff24532a
description: Informazioni su come verificare il dominio e configurare i record DNS per la posta elettronica, Skype for business online e altri servizi su Yahoo! Small Business per Microsoft.
ms.openlocfilehash: c44ad1cde79fdc401f1cd7411a4019d31ade6d02
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "44400281"
---
# <a name="create-dns-records-at-yahoo-small-business-for-microsoft"></a><span data-ttu-id="1855c-105">Creare record DNS in Yahoo!</span><span class="sxs-lookup"><span data-stu-id="1855c-105">Create DNS records at Yahoo!</span></span> <span data-ttu-id="1855c-106">Small Business per Microsoft</span><span class="sxs-lookup"><span data-stu-id="1855c-106">Small Business for Microsoft</span></span>

 <span data-ttu-id="1855c-107">**Se non si trova ciò che si sta cercando, [vedere le domande frequenti sui domini](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="1855c-107">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="1855c-p104">Se il proprio provider di hosting DNS era Yahoo! Small Business, occorre sapere che il nuovo provider è ora Aabaco Small Business.</span><span class="sxs-lookup"><span data-stu-id="1855c-p104">If Yahoo! Small Business has been your DNS hosting provider, you should be aware that your provider is now Aabaco Small Business.</span></span>
  
<span data-ttu-id="1855c-110">Seguire i passaggi in questo articolo per creare un account su Aabaco, in cui è possibile apportare le modifiche DNS e rinnovare il dominio o i domini.</span><span class="sxs-lookup"><span data-stu-id="1855c-110">Follow the steps in this article to create an account at Aabaco, where you can make DNS changes and renew your domain or domains.</span></span>
  
<span data-ttu-id="1855c-111">È necessario creare un account Aabaco prima di poter [creare record DNS](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span><span class="sxs-lookup"><span data-stu-id="1855c-111">You must create your Aabaco account before you can [create DNS records](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span>

  
## <a name="create-an-aabaco-small-business-account"></a><span data-ttu-id="1855c-112">Creare un account di Aabaco Small Business</span><span class="sxs-lookup"><span data-stu-id="1855c-112">Create an Aabaco Small Business account</span></span>

1. <span data-ttu-id="1855c-113">Per iniziare, passare alla propria pagina dei domini su Aabaco usando [questo collegamento](https://www.luminate.com/services/)e selezionare **setup your Aabaco Small Business account**.</span><span class="sxs-lookup"><span data-stu-id="1855c-113">To get started, go to your domains page at Aabaco by using [this link](https://www.luminate.com/services/), and select **Setup your Aabaco Small Business account**.</span></span>
    
    ![Selezionare setup your Aabaco Small Business account](../../media/d708f272-d42f-40a1-9aaf-d05d8cfd55cf.png)
  
2. <span data-ttu-id="1855c-115">Fornire il proprio indirizzo e-mail/ID Yahoo di Yahoo!</span><span class="sxs-lookup"><span data-stu-id="1855c-115">Provide your Yahoo!</span></span> <span data-ttu-id="1855c-116">Small Business **e-mail/Yahoo ID**, quindi selezionare **io non sono un robot**.</span><span class="sxs-lookup"><span data-stu-id="1855c-116">Small Business **Email/Yahoo ID**, and then select **I'm not a robot**.</span></span>
    
    ![Select I am not a robot](../../media/ded4b5dd-4e04-4baa-ae31-8426b5799151.png)
  
3. <span data-ttu-id="1855c-118">Selezionare **inizia**.</span><span class="sxs-lookup"><span data-stu-id="1855c-118">Select **Get started**.</span></span>
    
    ![Seleziona inizia](../../media/6674707d-c222-4f0d-bec4-229d39ab2499.png)
  
4. <span data-ttu-id="1855c-p106">Eseguire l'accesso all'account e-mail Yahoo! Small Business e aprire la nuova e-mail inviata da Aabaco Small Business.</span><span class="sxs-lookup"><span data-stu-id="1855c-p106">Sign in to your Yahoo! Small Business email account and open the new email from Aabaco Small Business.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="1855c-122">Inviare di nuovo il messaggio, se necessario, scegliendo il collegamento **resend the email** nella pagina **You've got mail**.</span><span class="sxs-lookup"><span data-stu-id="1855c-122">Resend the message, if necessary, by choosing the **resend the email link** on the **You've got mail** page.</span></span> 
  
    ![The You've got mail page](../../media/2e02fc30-6cca-40d6-bb64-131a41b4a369.png)
  
5. <span data-ttu-id="1855c-124">Nella Aabaco **confermare il proprio indirizzo di posta elettronica per continuare a configurare il messaggio di** posta elettronica, selezionare **conferma posta elettronica**.</span><span class="sxs-lookup"><span data-stu-id="1855c-124">In the Aabaco **Confirm your email address to continue setup** email message, select **Confirm email**.</span></span>
    
    ![Seleziona conferma messaggio di posta elettronica](../../media/eb5f5526-6f90-4a10-83a7-5249a1ebd562.png)
  
6. <span data-ttu-id="1855c-126">Nella pagina **Choose your password** digitare oppure copiare e incollare la password che si vuole usare per il proprio account di Aabaco.</span><span class="sxs-lookup"><span data-stu-id="1855c-126">On the **Choose your password** page, type or copy and paste the password that you want to use for your Aabaco account.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="1855c-p107">È possibile usare la stessa password usata con l'account di Yahoo! Small Business.</span><span class="sxs-lookup"><span data-stu-id="1855c-p107">You can use the same password that you used with your Yahoo! Small Business account.</span></span> 
  
    ![The Choose your password page](../../media/cc592345-72d1-4a41-9410-a1f3345cfd1d.png)
  
7. <span data-ttu-id="1855c-130">Selezionare Accetto **i termini e le condizioni**e quindi selezionare **Crea password**.</span><span class="sxs-lookup"><span data-stu-id="1855c-130">Select **I agree to the terms and conditions**, and then select **Create password**.</span></span>
    
    ![Selezionare Crea password](../../media/434aa6a3-076e-4abf-a9cf-31145786e819.png)
  
8. <span data-ttu-id="1855c-p108">Eseguire l'accesso all'account e-mail Yahoo! Small Business e quindi aprire la nuova e-mail inviata da Aabaco Small Business.</span><span class="sxs-lookup"><span data-stu-id="1855c-p108">Sign in to your Yahoo! Small Business email account, and then open the new email from Aabaco Small Business.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="1855c-p109">Inviare di nuovo il messaggio, se necessario, scegliendo il collegamento **resend the email** nella pagina **You're almost done!**.</span><span class="sxs-lookup"><span data-stu-id="1855c-p109">Resend the message, if necessary, by choosing the **resend the email link** on the **You're almost done!** page.</span></span> 
  
    ![The You're almost done page](../../media/1a4142a3-e140-48a8-9c80-aa126ff08179.png)
  
9. <span data-ttu-id="1855c-137">In Aabaco **ci sono quasi** messaggi di posta elettronica, selezionare **Attiva account personale**.</span><span class="sxs-lookup"><span data-stu-id="1855c-137">In the Aabaco **You're almost there** email message, select **Activate my account**.</span></span>
    
    ![Selezionare Attiva il mio account](../../media/e76d5edc-d8ba-4d8d-872d-d916716c3618.png)
  
10. <span data-ttu-id="1855c-139">Accedere al proprio account di Aabaco Small Business.</span><span class="sxs-lookup"><span data-stu-id="1855c-139">Sign in to your Aabaco Small Business account.</span></span>
    
    ![The sign-in page for Aabaco Small Business](../../media/4ef3cfc3-26da-4e03-932b-9346ef217848.png)
  
<span data-ttu-id="1855c-141">Dopo aver creato l'account Aabaco, è possibile [creare record DNS in Aabaco Small Business per Microsoft](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span><span class="sxs-lookup"><span data-stu-id="1855c-141">Now that you have created your Aabaco account, you can [Create DNS records at Aabaco Small Business for Microsoft](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span>
  
