---
title: Configurare un elenco di URL bloccati personalizzato utilizzando i collegamenti sicuri di ATP
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: Admin
ms.topic: article
ms.date: 02/06/2019
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 896a7efb-1683-465e-a394-261349e5d866
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Informazioni su come configurare un elenco di URL bloccati per l'organizzazione utilizzando Office 365 Advanced Threat Protection.
ms.openlocfilehash: 5f863a3ba61278d0bec5304034ed75d343f93c77
ms.sourcegitcommit: fa8e488936a36e4b56e1252cb4061b5bd6c0eafc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/13/2020
ms.locfileid: "46656648"
---
# <a name="set-up-a-custom-blocked-urls-list-using-atp-safe-links"></a><span data-ttu-id="ddcfa-103">Configurare un elenco di URL bloccati personalizzato utilizzando i collegamenti sicuri di ATP</span><span class="sxs-lookup"><span data-stu-id="ddcfa-103">Set up a custom blocked URLs list using ATP Safe Links</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ddcfa-104">Questo articolo è rivolto ai clienti aziendali di [Office 365 Advanced Threat Protection](office-365-atp.md).</span><span class="sxs-lookup"><span data-stu-id="ddcfa-104">This article is intended for business customers who have [Office 365 Advanced Threat Protection](office-365-atp.md).</span></span> <span data-ttu-id="ddcfa-105">Se si è un utente di casa che cerca informazioni sui collegamenti sicuri in Outlook, vedere [Advanced Outlook.com Security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span><span class="sxs-lookup"><span data-stu-id="ddcfa-105">If you are a home user looking for information about Safe Links in Outlook, see [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).</span></span>

<span data-ttu-id="ddcfa-106">Con [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP), l'organizzazione può disporre di un elenco personalizzato di indirizzi Web (URL) bloccati.</span><span class="sxs-lookup"><span data-stu-id="ddcfa-106">With [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP), your organization can have a custom list of website addresses (URLs) that are blocked.</span></span> <span data-ttu-id="ddcfa-107">Quando viene bloccato un URL, gli utenti che fanno clic sui collegamenti all'URL bloccato vengono indirizzati a una [pagina di avviso](atp-safe-links-warning-pages.md) simile all'immagine seguente:</span><span class="sxs-lookup"><span data-stu-id="ddcfa-107">When a URL is blocked, people who click on links to the blocked URL are taken to a [warning page](atp-safe-links-warning-pages.md) that resembles the following image:</span></span>

![Questo sito è bloccato](../../media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)

<span data-ttu-id="ddcfa-109">L'elenco degli URL bloccati è definito dal team di sicurezza Microsoft 365 for business dell'organizzazione e questo elenco si applica a tutti gli utenti dell'organizzazione interessati dai criteri dei collegamenti sicuri ATP di Office 365.</span><span class="sxs-lookup"><span data-stu-id="ddcfa-109">The blocked URLs list is defined by your organization's Microsoft 365 for business security team, and that list applies to everyone in the organization who is covered by Office 365 ATP Safe Links policies.</span></span>

<span data-ttu-id="ddcfa-110">Leggere questo articolo per informazioni su come configurare l'elenco degli URL bloccati personalizzati dell'organizzazione per i [collegamenti sicuri di ATP in Office 365](atp-safe-links.md).</span><span class="sxs-lookup"><span data-stu-id="ddcfa-110">Read this article to learn how to set up your organization's custom blocked URLs list for [ATP Safe Links in Office 365](atp-safe-links.md).</span></span>

## <a name="view-or-edit-a-custom-list-of-blocked-urls"></a><span data-ttu-id="ddcfa-111">Visualizzazione o modifica di un elenco personalizzato di URL bloccati</span><span class="sxs-lookup"><span data-stu-id="ddcfa-111">View or edit a custom list of blocked URLs</span></span>

<span data-ttu-id="ddcfa-112">I [collegamenti sicuri di ATP in Office 365](atp-safe-links.md) utilizzano diversi elenchi, tra cui l'elenco URL bloccati personalizzato dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ddcfa-112">[ATP Safe Links in Office 365](atp-safe-links.md) uses several lists, including your organization's custom blocked URLs list.</span></span> <span data-ttu-id="ddcfa-113">Se si dispone delle autorizzazioni necessarie, è possibile configurare l'elenco personalizzato dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ddcfa-113">If you have the necessary permissions, you can set up your organization's custom list.</span></span> <span data-ttu-id="ddcfa-114">A tale scopo, modificare il criterio collegamenti sicuri predefinito dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ddcfa-114">You do this by editing your organization's default Safe Links policy.</span></span>

<span data-ttu-id="ddcfa-115">Per modificare (o definire) i criteri ATP, è necessario essere assegnati a uno dei ruoli descritti nella tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="ddcfa-115">To edit (or define) ATP policies, you must be assigned one of the roles described in the following table:</span></span>

****

|<span data-ttu-id="ddcfa-116">Ruolo</span><span class="sxs-lookup"><span data-stu-id="ddcfa-116">Role</span></span>|<span data-ttu-id="ddcfa-117">Dove/come assegnato</span><span class="sxs-lookup"><span data-stu-id="ddcfa-117">Where/how assigned</span></span>|
|---|---|
|<span data-ttu-id="ddcfa-118">amministratore globale</span><span class="sxs-lookup"><span data-stu-id="ddcfa-118">global administrator</span></span>|<span data-ttu-id="ddcfa-119">La persona che si iscrive all'acquisto di Microsoft 365 è un amministratore globale per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="ddcfa-119">The person who signs up to buy Microsoft 365 is a global admin by default.</span></span> <span data-ttu-id="ddcfa-120">Per ulteriori informazioni, vedere [informazioni sui ruoli di amministratore di Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) .</span><span class="sxs-lookup"><span data-stu-id="ddcfa-120">(See [About Microsoft 365 admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) to learn more.)</span></span>|
|<span data-ttu-id="ddcfa-121">Amministratore della sicurezza</span><span class="sxs-lookup"><span data-stu-id="ddcfa-121">Security Administrator</span></span>|<span data-ttu-id="ddcfa-122">Interfaccia di amministrazione di Azure Active Directory ( [https://aad.portal.azure.com](https://aad.portal.azure.com) )</span><span class="sxs-lookup"><span data-stu-id="ddcfa-122">Azure Active Directory admin center ([https://aad.portal.azure.com](https://aad.portal.azure.com))</span></span>|
|<span data-ttu-id="ddcfa-123">Gestione organizzazione di Exchange Online</span><span class="sxs-lookup"><span data-stu-id="ddcfa-123">Exchange Online Organization Management</span></span>|<span data-ttu-id="ddcfa-124">Interfaccia di amministrazione di Exchange ( [https://outlook.office365.com/ecp](https://outlook.office365.com/ecp) )</span><span class="sxs-lookup"><span data-stu-id="ddcfa-124">Exchange admin center ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp))</span></span> <br><span data-ttu-id="ddcfa-125">oppure</span><span class="sxs-lookup"><span data-stu-id="ddcfa-125">or</span></span> <br>  <span data-ttu-id="ddcfa-126">Cmdlet di PowerShell (vedere [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell))</span><span class="sxs-lookup"><span data-stu-id="ddcfa-126">PowerShell cmdlets (See [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell))</span></span>|
|

> [!TIP]
> <span data-ttu-id="ddcfa-127">Per ulteriori informazioni sui ruoli e sulle autorizzazioni, vedere [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="ddcfa-127">To learn more about roles and permissions, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

### <a name="to-view-or-edit-a-custom-blocked-urls-list"></a><span data-ttu-id="ddcfa-128">Per visualizzare o modificare un elenco di URL bloccati personalizzato</span><span class="sxs-lookup"><span data-stu-id="ddcfa-128">To view or edit a custom blocked URLs list</span></span>

1. <span data-ttu-id="ddcfa-129">Accedere a [https://protection.office.com](https://protection.office.com) e accedere con l'account aziendale o dell'Istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="ddcfa-129">Go to [https://protection.office.com](https://protection.office.com) and sign in with your work or school account.</span></span>

2. <span data-ttu-id="ddcfa-130">Nella barra di spostamento a sinistra, in **gestione minacce**, scegliere **Policy** \> **collegamenti sicuri**per i criteri.</span><span class="sxs-lookup"><span data-stu-id="ddcfa-130">In the left navigation, under **Threat management**, choose **Policy** \> **Safe Links**.</span></span>

3. <span data-ttu-id="ddcfa-131">Nei **criteri che si applicano all'intera sezione organizzazione** selezionare **predefinita**e quindi fare clic su **modifica** (il pulsante modifica è simile a una matita).</span><span class="sxs-lookup"><span data-stu-id="ddcfa-131">In the **Policies that apply to the entire organization** section, select **Default**, and then choose **Edit** (the Edit button resembles a pencil).</span></span><br/><span data-ttu-id="ddcfa-132">![Fare clic su modifica per modificare il criterio predefinito per la protezione dei collegamenti sicuri](../../media/d08f9615-d947-4033-813a-d310ec2c8cca.png)</span><span class="sxs-lookup"><span data-stu-id="ddcfa-132">![Click Edit to edit your default policy for Safe Links protection](../../media/d08f9615-d947-4033-813a-d310ec2c8cca.png)</span></span><br/><span data-ttu-id="ddcfa-133">In questo modo è possibile visualizzare l'elenco degli URL bloccati.</span><span class="sxs-lookup"><span data-stu-id="ddcfa-133">This enables you to view your list of blocked URLs.</span></span> <span data-ttu-id="ddcfa-134">All'inizio, potrebbe non essere presente alcun URL.</span><span class="sxs-lookup"><span data-stu-id="ddcfa-134">At first, you might not have any URLs listed here.</span></span><br/><span data-ttu-id="ddcfa-135">![Elenco degli URL bloccati nel criterio collegamenti sicuri predefinito](../../media/575e1449-6191-40ac-b626-030a2fd3fb11.png)</span><span class="sxs-lookup"><span data-stu-id="ddcfa-135">![Blocked URLs list in the default Safe Links policy](../../media/575e1449-6191-40ac-b626-030a2fd3fb11.png)</span></span>

4. <span data-ttu-id="ddcfa-136">Selezionare la casella **immettere un URL valido** , digitare un URL e quindi scegliere il segno di addizione ( **+** ).</span><span class="sxs-lookup"><span data-stu-id="ddcfa-136">Select the **Enter a valid URL** box, type a URL, and then choose the plus sign (**+**).</span></span>

5. <span data-ttu-id="ddcfa-137">Dopo aver aggiunto gli URL, fare clic su **Salva**nell'angolo in basso a destra dello schermo.</span><span class="sxs-lookup"><span data-stu-id="ddcfa-137">When you are finished adding URLs, in the lower right corner of the screen, choose **Save**.</span></span>

## <a name="a-few-things-to-keep-in-mind"></a><span data-ttu-id="ddcfa-138">Alcuni aspetti da tenere presenti</span><span class="sxs-lookup"><span data-stu-id="ddcfa-138">A few things to keep in mind</span></span>

<span data-ttu-id="ddcfa-139">Quando si aggiungono URL all'elenco, tenere presente quanto segue:</span><span class="sxs-lookup"><span data-stu-id="ddcfa-139">While you add URLs to your list, keep the following points in mind:</span></span>

- <span data-ttu-id="ddcfa-140">Non includere una barra ( **/** ) alla fine dell'URL.</span><span class="sxs-lookup"><span data-stu-id="ddcfa-140">Do not include a forward slash ( **/**) at the end of the URL.</span></span> <span data-ttu-id="ddcfa-141">Ad esempio, invece di `https://www.contoso.com/` immettere, immetti `https://www.contoso.com` .</span><span class="sxs-lookup"><span data-stu-id="ddcfa-141">For example, instead of entering `https://www.contoso.com/`, enter `https://www.contoso.com`.</span></span>

- <span data-ttu-id="ddcfa-142">È possibile specificare un URL di solo dominio (come `contoso.com` or `tailspintoys.com` ).</span><span class="sxs-lookup"><span data-stu-id="ddcfa-142">You can specify a domain-only URL (like `contoso.com` or `tailspintoys.com`).</span></span> <span data-ttu-id="ddcfa-143">Questo bloccherà gli scatti su qualsiasi URL che contiene il dominio.</span><span class="sxs-lookup"><span data-stu-id="ddcfa-143">This will block clicks on any URL that contains the domain.</span></span>

- <span data-ttu-id="ddcfa-144">È possibile specificare un sottodominio (come `toys.contoso.com*` ) senza bloccare un dominio completo (come `contoso.com` ).</span><span class="sxs-lookup"><span data-stu-id="ddcfa-144">You can specify a subdomain (like `toys.contoso.com*`) without blocking a full domain (like `contoso.com`).</span></span> <span data-ttu-id="ddcfa-145">Questo blocco farà clic su qualsiasi URL contenente il sottodominio, ma non bloccherà i clic su un URL che contiene il dominio completo.</span><span class="sxs-lookup"><span data-stu-id="ddcfa-145">This will block clicks any URL that contains the subdomain, but it won't block clicks to a URL that contains the full domain.</span></span>

- <span data-ttu-id="ddcfa-146">È possibile includere fino a tre asterischi jolly ( \* ) per URL.</span><span class="sxs-lookup"><span data-stu-id="ddcfa-146">You can include up to three wildcard asterisks (\*) per URL.</span></span> <span data-ttu-id="ddcfa-147">Nella tabella seguente sono elencati alcuni esempi di elementi che è possibile immettere e quali sono gli effetti di tali voci.</span><span class="sxs-lookup"><span data-stu-id="ddcfa-147">The following table lists some examples of what you can enter and what effect those entries have.</span></span>

****

|<span data-ttu-id="ddcfa-148">Voce di esempio</span><span class="sxs-lookup"><span data-stu-id="ddcfa-148">Example Entry</span></span>|<span data-ttu-id="ddcfa-149">Cosa fa</span><span class="sxs-lookup"><span data-stu-id="ddcfa-149">What It Does</span></span>|
|---|---|
|<span data-ttu-id="ddcfa-150">`contoso.com` o `*contoso.com*`</span><span class="sxs-lookup"><span data-stu-id="ddcfa-150">`contoso.com` or `*contoso.com*`</span></span>|<span data-ttu-id="ddcfa-151">Blocca il dominio, i sottodomini e i percorsi, ad esempio `https://www.contoso.com` , `https://sub.contoso.com` e `https://contoso.com/abc`</span><span class="sxs-lookup"><span data-stu-id="ddcfa-151">Blocks the domain, subdomains, and paths, such as `https://www.contoso.com`, `https://sub.contoso.com`, and `https://contoso.com/abc`</span></span>|
|`https://contoso.com/a`|<span data-ttu-id="ddcfa-152">Blocca un sito, `https://contoso.com/a` ma non altri percorsi secondari come `https://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="ddcfa-152">Blocks a site `https://contoso.com/a` but not additional subpaths like `https://contoso.com/a/b`</span></span>|
|`https://contoso.com/a*`|<span data-ttu-id="ddcfa-153">Blocca un sito `https://contoso.com/a` e altri percorsi secondari come `https://contoso.com/a/b`</span><span class="sxs-lookup"><span data-stu-id="ddcfa-153">Blocks a site `https://contoso.com/a` and additional subpaths like `https://contoso.com/a/b`</span></span>|
|`https://toys.contoso.com*`|<span data-ttu-id="ddcfa-154">Blocca un sottodominio ("giocattoli" in questo caso), ma consente di fare clic su altri URL di dominio (come `https://contoso.com` or `https://home.contoso.com` ).</span><span class="sxs-lookup"><span data-stu-id="ddcfa-154">Blocks a subdomain ("toys" in this case) but allow clicks to other domain URLs (like `https://contoso.com` or `https://home.contoso.com`).</span></span>|
|

> [!NOTE]
> <span data-ttu-id="ddcfa-155">Per impostazione predefinita, è possibile aggiungere 500 URL all'elenco degli URL bloccati nel criterio predefinito dei collegamenti sicuri ATP di Office 365.</span><span class="sxs-lookup"><span data-stu-id="ddcfa-155">By default, you can only add 500 URLs to the blocked URL list in the Office 365 ATP Safe Links default policy.</span></span>

## <a name="how-to-define-exceptions-for-certain-users-in-an-organization"></a><span data-ttu-id="ddcfa-156">Come definire le eccezioni per alcuni utenti di un'organizzazione</span><span class="sxs-lookup"><span data-stu-id="ddcfa-156">How to define exceptions for certain users in an organization</span></span>

<span data-ttu-id="ddcfa-157">Se si desidera che alcuni gruppi siano in grado di visualizzare gli URL che potrebbero essere bloccati per gli altri utenti, è possibile specificare un criterio per i collegamenti sicuri ATP che si applica a destinatari specifici.</span><span class="sxs-lookup"><span data-stu-id="ddcfa-157">If you want certain groups to be able to view URLs that might be blocked for others, you can specify an ATP Safe Links policy that applies to specific recipients.</span></span> <span data-ttu-id="ddcfa-158">Vedere [configurare un elenco di URL "non riscrivere" personalizzato utilizzando i collegamenti sicuri di ATP](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md).</span><span class="sxs-lookup"><span data-stu-id="ddcfa-158">See [Set up a custom "do not rewrite" URLs list using ATP Safe Links](set-up-a-custom-do-not-rewrite-urls-list-with-atp.md).</span></span>
