---
title: Eseguire l'acquisizione di un amministratore interno
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
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
description: Informazioni su come verificare la proprietà della posta elettronica e del dominio per assumere il controllo di un tenant non gestito creato da un utente in modalità self-service Microsoft 365.
ms.openlocfilehash: c37bf153edf39f53b5c10f020b0cbb8d630eb4a6
ms.sourcegitcommit: b0d3abbccf4dd37e32d69664d3ebc9ab8dea760d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2021
ms.locfileid: "52593934"
---
# <a name="perform-an-internal-admin-takeover"></a><span data-ttu-id="c1af4-103">Eseguire l'acquisizione di un amministratore interno</span><span class="sxs-lookup"><span data-stu-id="c1af4-103">Perform an internal admin takeover</span></span>

 <span data-ttu-id="c1af4-104">Se non si trova ciò che si sta cercando, **[vedere le domande frequenti sui domini](../setup/domains-faq.yml)**.</span><span class="sxs-lookup"><span data-stu-id="c1af4-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 

<span data-ttu-id="c1af4-105">Se sei un amministratore e vuoi assumere un tenant non gestito creato da un'iscrizione utente self-service, puoi farlo con un'acquisizione da parte di un amministratore interno.</span><span class="sxs-lookup"><span data-stu-id="c1af4-105">If you are an admin and want to take over an unmanaged tenant created by a self-service user signup, you can do this with an internal admin takeover.</span></span>

> [!NOTE]
> <span data-ttu-id="c1af4-106">Una registrazione self-service per qualsiasi servizio cloud che usa Azure AD aggiungerà l'utente a una directory azure AD non gestita o "shadow" e creerà un tenant non gestito.</span><span class="sxs-lookup"><span data-stu-id="c1af4-106">A self-service sign up for any cloud service that uses Azure AD will add the user to an unmanaged or "shadow" Azure AD directory and create an unmanaged tenant.</span></span> <span data-ttu-id="c1af4-107">Un tenant non gestito è una directory senza un amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="c1af4-107">An unmanaged tenant is a directory without a global administrator.</span></span> <span data-ttu-id="c1af4-108">Per determinare se un tenant è gestito o non gestito, vedere [Determining Tenant Type](/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type).</span><span class="sxs-lookup"><span data-stu-id="c1af4-108">To determine whether a tenant is managed or unmanaged, please see [Determining Tenant Type](/power-platform/admin/powerapps-gdpr-dsr-guide-systemlogs#determining-tenant-type).</span></span> 
  
## <a name="step-1-verify-your-email-address"></a><span data-ttu-id="c1af4-109">Passaggio 1: Verificare l'indirizzo di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="c1af4-109">Step 1: Verify your email address</span></span>

> [!NOTE]
> <span data-ttu-id="c1af4-110">Se il servizio self-service è abilitato nel tenant, gli utenti possono sottoscrivere servizi gratuiti, ad esempio Power BI, autonomamente.</span><span class="sxs-lookup"><span data-stu-id="c1af4-110">If self-service is enabled in your tenant, users can subscribe to free services, such as Power BI, on their own.</span></span> <span data-ttu-id="c1af4-111">Questi passaggi presuppongono che una sottoscrizione utente in modalità self-service abbia creato il tenant non gestito che si desidera assumere come amministratore. Nel primo passaggio viene creato un contesto utente nel tenant non gestito, usando Power BI per illustrare il percorso di acquisizione dell'amministratore.</span><span class="sxs-lookup"><span data-stu-id="c1af4-111">These steps assume that a self-service user subscription has created the unmanaged tenant you want to take over as admin. In the first step you create a user context in the unmanaged tenant, using Power BI to illustrate the admin takeover path.</span></span>

1. <span data-ttu-id="c1af4-112">Per iscriverti Power BI, vai al sito [di Power BI](https://powerbi.com) e seleziona Avvia la versione di valutazione gratuita di Start gratuito (nella casella Condividi  >   con Power BI Pro).</span><span class="sxs-lookup"><span data-stu-id="c1af4-112">To sign up for Power BI, go to the [Power BI site](https://powerbi.com) and select **Start Free** > **Start free trial** (in Share with Power BI Pro box).</span></span> 

2. <span data-ttu-id="c1af4-113">Iscriversi con un account utente che utilizza il nome di dominio dell'organizzazione (ad esempio `powerbiadmin@contoso.com` ).</span><span class="sxs-lookup"><span data-stu-id="c1af4-113">Sign up with a user account that uses the domain name of your organization (like `powerbiadmin@contoso.com`).</span></span> <span data-ttu-id="c1af4-114">Se l'account è già in uso, accedere utilizzando la password corrente.</span><span class="sxs-lookup"><span data-stu-id="c1af4-114">If your account is already in use, sign in using your current password.</span></span>

3. <span data-ttu-id="c1af4-115">Controllare il codice di verifica nel messaggio di posta **elettronica** e immettere il codice per convalidare l'indirizzo di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="c1af4-115">Check your email for the **verification code** and enter the code to validate your email address.</span></span>
    
## <a name="step-2-create-a-new-account"></a><span data-ttu-id="c1af4-116">Passaggio 2: Creare un nuovo account</span><span class="sxs-lookup"><span data-stu-id="c1af4-116">Step 2: Create a new account</span></span>

1. <span data-ttu-id="c1af4-117">Quando immetti il codice di verifica, verrà visualizzata una pagina in cui puoi creare un nuovo account.</span><span class="sxs-lookup"><span data-stu-id="c1af4-117">When you enter the verification code, you'll be brought to a page where you can create a new account.</span></span> 
    
2. <span data-ttu-id="c1af4-118">Compilare i campi nome utente e password con l'account che si desidera utilizzare, quindi selezionare **Avvia**.</span><span class="sxs-lookup"><span data-stu-id="c1af4-118">Fill in the user name and password fields with the account that you want to use, then select **Start**.</span></span> 
    
## <a name="step-3-verify-domain-ownership-and-become-the-admin"></a><span data-ttu-id="c1af4-119">Passaggio 3: verificare la proprietà del dominio e diventare l'amministratore</span><span class="sxs-lookup"><span data-stu-id="c1af4-119">Step 3: Verify domain ownership and become the admin</span></span>

1. <span data-ttu-id="c1af4-120">Verrà **aperta la procedura guidata** Diventa amministratore.</span><span class="sxs-lookup"><span data-stu-id="c1af4-120">The **Become the admin** wizard will open.</span></span> <span data-ttu-id="c1af4-121">Se la procedura guidata non viene avviata, cerca il riquadro **Amministratore** e selezionalo.</span><span class="sxs-lookup"><span data-stu-id="c1af4-121">If the wizard doesn't start, look for the **Admin** tile and select it.</span></span> 

2. <span data-ttu-id="c1af4-122">Selezionare **Sì, voglio essere l'amministratore.**</span><span class="sxs-lookup"><span data-stu-id="c1af4-122">Select **Yes, I want to be the admin**.</span></span>

3. <span data-ttu-id="c1af4-123">Verificare di essere proprietari del dominio che si desidera assumere aggiungendo un record TXT al registrar.</span><span class="sxs-lookup"><span data-stu-id="c1af4-123">Verify that you own the domain you want to take over by adding a TXT record to your domain registrar.</span></span> <span data-ttu-id="c1af4-124">La procedura guidata fornirà il record TXT da aggiungere, nonché un collegamento al sito Web del registrar e un collegamento a istruzioni dettagliate.</span><span class="sxs-lookup"><span data-stu-id="c1af4-124">The wizard will give you the TXT record to add, as well as provide a link to your registrar's website, and a link to step-by-step instructions.</span></span>
    
4. <span data-ttu-id="c1af4-125">Dopo aver aggiunto il record TXT al sito del registrar, tornare alla procedura guidata e selezionare Ok, il **record è stato aggiunto.**</span><span class="sxs-lookup"><span data-stu-id="c1af4-125">Once you've added the TXT record to your registrar site, return to the wizard and select **Okay, I've added the record**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="c1af4-126">L'assunzione del tenant shadow non inciderà sulle informazioni o sui servizi esistenti.</span><span class="sxs-lookup"><span data-stu-id="c1af4-126">Taking over the shadow tenant will not impact any existing information or services.</span></span> <span data-ttu-id="c1af4-127">Tuttavia, se tutti gli utenti del dominio si sono registrati per i servizi che richiedono una licenza, ti verrà chiesto di acquistare licenze per loro come parte dell'assunzione del ruolo di amministratore.</span><span class="sxs-lookup"><span data-stu-id="c1af4-127">However, if any users in the domain have signed up for services that require a license, you'll be asked to buy licenses for them as part of taking over the admin role.</span></span> <span data-ttu-id="c1af4-128">Puoi acquistare o rimuovere licenze al termine del processo di configurazione dell'amministratore.</span><span class="sxs-lookup"><span data-stu-id="c1af4-128">You can buy or remove licenses once the admin setup process is finished.</span></span>
  
## <a name="related-content"></a><span data-ttu-id="c1af4-129">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="c1af4-129">Related content</span></span>

<span data-ttu-id="c1af4-130">YouTube: [3 passaggi per eseguire l'acquisizione](https://www.youtube.com/watch?v=xt5EsrQBZZk) di un amministratore IT per Power BI e Microsoft 365 (video)</span><span class="sxs-lookup"><span data-stu-id="c1af4-130">YouTube: [3 steps to do an IT Admin Takeover for Power BI and Microsoft 365](https://www.youtube.com/watch?v=xt5EsrQBZZk) (video)</span></span>

<span data-ttu-id="c1af4-131">[Acquisizione dell'amministratore in Azure AD](/azure/active-directory/users-groups-roles/domains-admin-takeover) (articolo)</span><span class="sxs-lookup"><span data-stu-id="c1af4-131">[Admin takeover in Azure AD](/azure/active-directory/users-groups-roles/domains-admin-takeover) (article)</span></span>

<span data-ttu-id="c1af4-132">[Uso dell'iscrizione in modalità self-service nell'organizzazione](self-service-sign-up.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="c1af4-132">[Using self-service sign up in your organization](self-service-sign-up.md) (article)</span></span>
  
<span data-ttu-id="c1af4-133">[Informazioni sul ruolo Power BI amministratore del servizio](/power-bi/service-admin-role) (articolo)</span><span class="sxs-lookup"><span data-stu-id="c1af4-133">[Understanding the Power BI service administrator role](/power-bi/service-admin-role) (article)</span></span>