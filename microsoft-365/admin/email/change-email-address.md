---
title: Cambiare l'indirizzo di posta elettronica per usare il dominio personalizzato
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
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- MSStore_Link
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: f4d8cae9-6d06-4c4b-b4e5-6581fd05ea82
description: "Modificare l'indirizzo di posta elettronica iniziale in un indirizzo di posta elettronica semplice come tom@fourthcoffee.com. A tale scopo, è necessario acquistare un nome di dominio e aggiungerlo a Office 365. "
ms.openlocfilehash: dc0ab64003b48eec50bf34e60d8a6df463b4fe89
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2020
ms.locfileid: "43212034"
---
# <a name="change-your-email-address-to-use-your-custom-domain"></a><span data-ttu-id="f60bd-104">Cambiare l'indirizzo di posta elettronica per usare il dominio personalizzato</span><span class="sxs-lookup"><span data-stu-id="f60bd-104">Change your email address to use your custom domain</span></span>

 <span data-ttu-id="f60bd-105">**Se non si trova ciò che si sta cercando, [vedere le domande frequenti sui domini](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="f60bd-105">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
::: moniker range="o365-worldwide"

<span data-ttu-id="f60bd-p102">L'indirizzo di posta elettronica iniziale in Office 365 include .onmicrosoft.com, ad esempio roby@fourthcoffee.onmicrosoft.com. È possibile modificarlo per ottenere un indirizzo più semplice come roby@fourthcoffee.com. Prima di tutto è necessario un nome di dominio personalizzato, ad esempio fourthcoffee.com. Se è già disponibile è possibile procedere. In caso contrario, vedere l'articolo su come [acquistarne uno da un registrar](../get-help-with-domains/buy-a-domain-name.md).</span><span class="sxs-lookup"><span data-stu-id="f60bd-p102">Your initial email address in Office 365 includes .onmicrosoft.com, like tom@fourthcoffee.onmicrosoft.com. You can change it to a friendlier address like tom@fourthcoffee.com. You'll need your own domain name, like fourthcoffee.com first. If you already have one, great! If not, you can learn how to [buy one from a domain registrar](../get-help-with-domains/buy-a-domain-name.md).</span></span>

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="f60bd-111">L'indirizzo di posta elettronica iniziale in Office 365 Germany include. onmicrosoft.de, come tom@fourthcoffee.onmicrosoft.de.</span><span class="sxs-lookup"><span data-stu-id="f60bd-111">Your initial email address in Office 365 Germany includes .onmicrosoft.de, like tom@fourthcoffee.onmicrosoft.de.</span></span> <span data-ttu-id="f60bd-112">È possibile modificarlo in un indirizzo più amichevole come tom@fourthcoffee.de.</span><span class="sxs-lookup"><span data-stu-id="f60bd-112">You can change it to a friendlier address like tom@fourthcoffee.de.</span></span> <span data-ttu-id="f60bd-113">È necessario un nome di dominio personalizzato, come fourthcoffee.de First.</span><span class="sxs-lookup"><span data-stu-id="f60bd-113">You'll need your own domain name, like fourthcoffee.de first.</span></span> <span data-ttu-id="f60bd-114">Se è già disponibile è possibile procedere.</span><span class="sxs-lookup"><span data-stu-id="f60bd-114">If you already have one, great!</span></span> <span data-ttu-id="f60bd-115">In caso contrario, vedere l'articolo su come [acquistarne uno da un registrar](../get-help-with-domains/buy-a-domain-name.md).</span><span class="sxs-lookup"><span data-stu-id="f60bd-115">If not, you can learn how to [buy one from a domain registrar](../get-help-with-domains/buy-a-domain-name.md).</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="f60bd-116">L'indirizzo di posta elettronica iniziale in Office 365 gestito da 21Vianet include partner.onmschina.cn, ad esempio tom@fourthcoffee.partner.onmschina.cn.</span><span class="sxs-lookup"><span data-stu-id="f60bd-116">Your initial email address in Office 365 operated by 21Vianet includes partner.onmschina.cn, like tom@fourthcoffee.partner.onmschina.cn.</span></span> <span data-ttu-id="f60bd-117">È possibile modificarlo in un indirizzo più amichevole come tom@fourthcoffee.cn.</span><span class="sxs-lookup"><span data-stu-id="f60bd-117">You can change it to a friendlier address like tom@fourthcoffee.cn.</span></span> <span data-ttu-id="f60bd-118">È necessario un nome di dominio personalizzato, come fourthcoffee.cn First.</span><span class="sxs-lookup"><span data-stu-id="f60bd-118">You'll need your own domain name, like fourthcoffee.cn first.</span></span> <span data-ttu-id="f60bd-119">Se è già disponibile è possibile procedere.</span><span class="sxs-lookup"><span data-stu-id="f60bd-119">If you already have one, great!</span></span> <span data-ttu-id="f60bd-120">In caso contrario, vedere l'articolo su come [acquistarne uno da un registrar](../get-help-with-domains/buy-a-domain-name.md).</span><span class="sxs-lookup"><span data-stu-id="f60bd-120">If not, you can learn how to [buy one from a domain registrar](../get-help-with-domains/buy-a-domain-name.md).</span></span>

::: moniker-end

<span data-ttu-id="f60bd-p105">Quando si cambia la posta elettronica del dominio in modo che venga recapitata in Office 365, aggiornando il record MX del dominio durante la configurazione, TUTTI i messaggi inviati al dominio inizieranno a essere recapitati in Office 365. Assicurarsi di aver aggiunto utenti e creato cassette postali in Office 365 per tutte le persone che hanno la posta elettronica nel dominio PRIMA di cambiare il record MD. Non si vuole spostare la posta di tutti gli utenti del dominio in Office 365? È possibile [eseguire una distribuzione pilota di Office 365 con solo alcuni indirizzi di posta elettronica](https://support.office.com/article/39cee536-6a03-40cf-b9c1-f301bb6001d7.aspx).</span><span class="sxs-lookup"><span data-stu-id="f60bd-p105">When you change your domain's email to come to Office 365, by updating your domain's MX record during setup, ALL email sent to that domain will start coming to Office 365. Make sure you've added users and created mailboxes in Office 365 for everyone who has email on your domain BEFORE you change the MX record. Don't want to move email for everyone on your domain to Office 365? You can take steps to [pilot Office 365 with just a few email addresses instead](https://support.office.com/article/39cee536-6a03-40cf-b9c1-f301bb6001d7.aspx).</span></span>
  
## <a name="change-your-email-address-to-use-your-custom-domain-using-the-microsoft-365-admin-center"></a><span data-ttu-id="f60bd-125">Modificare l'indirizzo di posta elettronica per usare il dominio personalizzato utilizzando l'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f60bd-125">Change your email address to use your custom domain using the Microsoft 365 admin center</span></span>

<span data-ttu-id="f60bd-126">Per eseguire questa procedura è necessario disporre di un account di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="f60bd-126">You must have a global admin account to perform these steps.</span></span> 

::: moniker range="o365-worldwide"

1. <span data-ttu-id="f60bd-127">Passare all'interfaccia di amministrazione all'indirizzo <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="f60bd-127">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span> 

::: moniker-end
   
::: moniker range="o365-germany"
    
1. <span data-ttu-id="f60bd-128">Passare all'interfaccia di amministrazione all'indirizzo <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span><span class="sxs-lookup"><span data-stu-id="f60bd-128">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span></span> 
    
::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="f60bd-129">Accedere all'interfaccia di amministrazione all' <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank"> https://portal.partner.microsoftonline.cn </a>indirizzo.</span><span class="sxs-lookup"><span data-stu-id="f60bd-129">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank"> https://portal.partner.microsoftonline.cn</a>.</span></span> 

::: moniker-end 

2. <span data-ttu-id="f60bd-130">Passare alla pagina **configurazione** > **domini** .</span><span class="sxs-lookup"><span data-stu-id="f60bd-130">Go to the **Setup** > **Domains** page.</span></span> 

3. <span data-ttu-id="f60bd-131">Nella pagina **Domains** selezionare **Aggiungi dominio**.</span><span class="sxs-lookup"><span data-stu-id="f60bd-131">On the **Domains** page, select **Add domain**.</span></span>
    
4. <span data-ttu-id="f60bd-132">Seguire i vari passaggi per confermare di essere proprietari del dominio e modificare l'indirizzo di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="f60bd-132">Follow the steps to confirm that you own your domain and to change your email address.</span></span>
    
<span data-ttu-id="f60bd-133">Sarà possibile eseguire in modo guidato tutte le operazioni necessarie per la corretta configurazione del dominio personale in Office 365.</span><span class="sxs-lookup"><span data-stu-id="f60bd-133">You'll be guided to get everything set up correctly with your domain in Office 365.</span></span>

> [!NOTE]
> <span data-ttu-id="f60bd-134">Se non si utilizza una licenza di Exchange, non è possibile utilizzare il dominio per inviare o ricevere messaggi di posta elettronica dal tenant di Office 365.</span><span class="sxs-lookup"><span data-stu-id="f60bd-134">If you are not using an Exchange license, you cannot use the domain to send or receive emails from the Office 365 tenant.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="f60bd-135">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="f60bd-135">Related articles</span></span>

[<span data-ttu-id="f60bd-136">Acquistare un dominio personalizzato usando Office 365</span><span class="sxs-lookup"><span data-stu-id="f60bd-136">Buy a custom domain using Office 365</span></span>](../get-help-with-domains/buy-a-domain-name.md)
 
