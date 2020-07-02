---
title: Eseguire l'acquisizione di un amministratore interno
f1.keywords:
- CSH
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b9707ec8-2247-4e25-9bad-f11ddbc686e4
description: Informazioni su come verificare la posta elettronica e la proprietà del dominio in modo da assumere un tenant non gestito in Microsoft 365
ms.openlocfilehash: 1eb54a6c34c9700bda09a660c71d2b1222fcdb8c
ms.sourcegitcommit: 3ddcf08e8deec087df1fe524147313f1cb12a26d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2020
ms.locfileid: "45022158"
---
# <a name="perform-an-internal-admin-takeover"></a><span data-ttu-id="8168f-103">Eseguire l'acquisizione di un amministratore interno</span><span class="sxs-lookup"><span data-stu-id="8168f-103">Perform an internal admin takeover</span></span>

 <span data-ttu-id="8168f-104">Se non si trova ciò che si sta cercando, **[vedere le domande frequenti sui domini](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="8168f-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 

<span data-ttu-id="8168f-105">Se si è un amministratore e si vuole assumere un tenant non gestito creato da un utente in modalità self-service, è possibile eseguire questa operazione con l'acquisizione di un amministratore interno.</span><span class="sxs-lookup"><span data-stu-id="8168f-105">If you are an admin and want to take over an unmanaged tenant created by a self-service user signup, you can do this with an internal admin takeover.</span></span>

> [!NOTE]
> <span data-ttu-id="8168f-106">Una registrazione in modalità self-service per qualsiasi servizio cloud che utilizza Azure AD aggiunge l'utente a una directory di Azure AD non gestita o "Shadow" e crea un tenant non gestito.</span><span class="sxs-lookup"><span data-stu-id="8168f-106">A self-service sign up for any cloud service that uses Azure AD will add the user to an unmanaged or "shadow" Azure AD directory and create an unmanaged tenant.</span></span> <span data-ttu-id="8168f-107">Un tenant non gestito è una directory senza un amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="8168f-107">An unmanaged tenant is a directory without a global administrator.</span></span> <span data-ttu-id="8168f-108">Per determinare se un tenant è gestito o non gestito, vedere determinare il [tipo di tenant](https://docs.microsoft.com/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type).</span><span class="sxs-lookup"><span data-stu-id="8168f-108">To determine whether a tenant is managed or unmanaged, please see [Determining Tenant Type](https://docs.microsoft.com/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type).</span></span> 
  
## <a name="step-1-verify-your-email-address"></a><span data-ttu-id="8168f-109">Passaggio 1: verificare l'indirizzo di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="8168f-109">Step 1: Verify your email address</span></span>

> [!NOTE]
> <span data-ttu-id="8168f-110">Se il servizio self-service è abilitato nel tenant, gli utenti possono iscriversi a servizi gratuiti, ad esempio Power BI, per conto proprio.</span><span class="sxs-lookup"><span data-stu-id="8168f-110">If self-service is enabled in your tenant, users can subscribe to free services, such as Power BI, on their own.</span></span> <span data-ttu-id="8168f-111">In questa procedura si presuppone che la sottoscrizione di un utente in modalità self-service abbia creato il tenant non gestito che si desidera sottoporre a amministratore. Nel primo passaggio viene creato un contesto utente nel tenant non gestito, utilizzando Power BI per illustrare il percorso di acquisizione dell'amministratore.</span><span class="sxs-lookup"><span data-stu-id="8168f-111">These steps assume that a self-service user subscription has created the unmanaged tenant you want to take over as admin. In the first step you create a user context in the unmanaged tenant, using Power BI to illustrate the admin takeover path.</span></span>

1. <span data-ttu-id="8168f-112">Per iscriversi a Power bi, passare al [sito Power bi](https://powerbi.com) e selezionare **Avvia**versione di valutazione gratuita di avvio gratuito  >  **Start free trial** (in Condividi con Power bi Pro box).</span><span class="sxs-lookup"><span data-stu-id="8168f-112">To sign up for Power BI, go to the [Power BI site](https://powerbi.com) and select **Start Free** > **Start free trial** (in Share with Power BI Pro box).</span></span> 

2. <span data-ttu-id="8168f-113">Iscriversi con un account utente che utilizza il nome di dominio dell'organizzazione (come `powerbiadmin@contoso.com` ).</span><span class="sxs-lookup"><span data-stu-id="8168f-113">Sign up with a user account that uses the domain name of your organization (like `powerbiadmin@contoso.com`).</span></span> <span data-ttu-id="8168f-114">Se l'account è già in uso, accedere utilizzando la password corrente.</span><span class="sxs-lookup"><span data-stu-id="8168f-114">If your account is already in use, sign in using your current password.</span></span>

3. <span data-ttu-id="8168f-115">Controllare la posta elettronica per il **codice di verifica** e immettere il codice per convalidare l'indirizzo di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="8168f-115">Check your email for the **verification code** and enter the code to validate your email address.</span></span>
    
## <a name="step-2-create-a-new-account"></a><span data-ttu-id="8168f-116">Passaggio 2: creare un nuovo account</span><span class="sxs-lookup"><span data-stu-id="8168f-116">Step 2: Create a new account</span></span>

1. <span data-ttu-id="8168f-117">Quando si immette il codice di verifica, viene visualizzata una pagina in cui è possibile creare un nuovo account.</span><span class="sxs-lookup"><span data-stu-id="8168f-117">When you enter the verification code, you'll be brought to a page where you can create a new account.</span></span> 
    
2. <span data-ttu-id="8168f-118">Inserire i campi nome utente e password con l'account che si desidera utilizzare, quindi selezionare **Avvia**.</span><span class="sxs-lookup"><span data-stu-id="8168f-118">Fill in the user name and password fields with the account that you want to use, then select **Start**.</span></span> 
    
## <a name="step-3-verify-domain-ownership-and-become-the-admin"></a><span data-ttu-id="8168f-119">Passaggio 3: verificare la proprietà del dominio e divenire l'amministratore</span><span class="sxs-lookup"><span data-stu-id="8168f-119">Step 3: Verify domain ownership and become the admin</span></span>

1. <span data-ttu-id="8168f-120">Verrà aperta la procedura guidata di **amministratore** .</span><span class="sxs-lookup"><span data-stu-id="8168f-120">The **Become the admin** wizard will open.</span></span> <span data-ttu-id="8168f-121">Se la procedura guidata non viene avviata, cercare il riquadro **amministratore** e selezionarlo.</span><span class="sxs-lookup"><span data-stu-id="8168f-121">If the wizard doesn't start, look for the **Admin** tile and select it.</span></span> 

2. <span data-ttu-id="8168f-122">Selezionare **Sì, voglio essere l'amministratore**.</span><span class="sxs-lookup"><span data-stu-id="8168f-122">Select **Yes, I want to be the admin**.</span></span>

3. <span data-ttu-id="8168f-123">Verificare di essere proprietari del dominio di cui si desidera eseguire l'aggiunta di un record TXT al registrar.</span><span class="sxs-lookup"><span data-stu-id="8168f-123">Verify that you own the domain you want to take over by adding a TXT record to your domain registrar.</span></span> <span data-ttu-id="8168f-124">La procedura guidata fornirà il record TXT da aggiungere, oltre a fornire un collegamento al sito Web del registrar e un collegamento a istruzioni dettagliate.</span><span class="sxs-lookup"><span data-stu-id="8168f-124">The wizard will give you the TXT record to add, as well as provide a link to your registrar's website, and a link to step-by-step instructions.</span></span>
    
4. <span data-ttu-id="8168f-125">Dopo aver aggiunto il record TXT al sito di registrazione, tornare alla procedura guidata e selezionare **OK, ho aggiunto il record**.</span><span class="sxs-lookup"><span data-stu-id="8168f-125">Once you've added the TXT record to your registrar site, return to the wizard and select **Okay, I've added the record**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="8168f-126">La presa in considerazione del tenant shadow non avrà alcun impatto sulle informazioni o sui servizi esistenti.</span><span class="sxs-lookup"><span data-stu-id="8168f-126">Taking over the shadow tenant will not impact any existing information or services.</span></span> <span data-ttu-id="8168f-127">Tuttavia, se gli utenti del dominio hanno effettuato l'iscrizione per i servizi che richiedono una licenza, ti verrà richiesto di acquistare licenze per il ruolo di amministratore.</span><span class="sxs-lookup"><span data-stu-id="8168f-127">However, if any users in the domain have signed up for services that require a license, you'll be asked to buy licenses for them as part of taking over the admin role.</span></span> <span data-ttu-id="8168f-128">Dopo aver completato il processo di configurazione dell'amministratore, è possibile acquistare o rimuovere licenze.</span><span class="sxs-lookup"><span data-stu-id="8168f-128">You can buy or remove licenses once the admin setup process is finished.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="8168f-129">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="8168f-129">Related articles</span></span>

<span data-ttu-id="8168f-130">YouTube: [3 passaggi per eseguire l'acquisizione di un amministratore IT per Power bi e Microsoft 365](https://www.youtube.com/watch?v=xt5EsrQBZZk)</span><span class="sxs-lookup"><span data-stu-id="8168f-130">YouTube: [3 steps to do an IT Admin Takeover for Power BI and Microsoft 365](https://www.youtube.com/watch?v=xt5EsrQBZZk)</span></span>

[<span data-ttu-id="8168f-131">Acquisizione dell'amministratore in Azure AD</span><span class="sxs-lookup"><span data-stu-id="8168f-131">Admin takeover in Azure AD</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/domains-admin-takeover)

[<span data-ttu-id="8168f-132">Ottenere assistenza per i domini</span><span class="sxs-lookup"><span data-stu-id="8168f-132">Get help with domains</span></span>](../get-help-with-domains/get-help-with-domains.md)

[<span data-ttu-id="8168f-133">Utilizzo dell'iscrizione in modalità self-service nell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="8168f-133">Using self-service sign up in your organization</span></span>](self-service-sign-up.md)
  
[<span data-ttu-id="8168f-134">Informazioni sul ruolo di amministratore del servizio Power BI</span><span class="sxs-lookup"><span data-stu-id="8168f-134">Understanding the Power BI service administrator role</span></span>](https://docs.microsoft.com/power-bi/service-admin-role)

