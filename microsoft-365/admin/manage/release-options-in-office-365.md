---
title: Configurare le opzioni di rilascio Standard o Mirato
f1.keywords:
- CSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 3b3adfa4-1777-4ff0-b606-fb8732101f47
description: Informazioni su come configurare l'opzione di rilascio per gli aggiornamenti di nuovi prodotti e funzionalità nell'interfaccia di amministrazione di Microsoft 365.
ms.openlocfilehash: e909cdf35ba9dd8282540783f7c362e5ae49212e
ms.sourcegitcommit: 8998f70d3f7bd673f93f8d1cf12ce981b1b771c3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51034080"
---
# <a name="set-up-the-standard-or-targeted-release-options"></a><span data-ttu-id="9d2ef-103">Configurare le opzioni di rilascio Standard o Mirato</span><span class="sxs-lookup"><span data-stu-id="9d2ef-103">Set up the Standard or Targeted release options</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="9d2ef-104">L'interfaccia di amministrazione sta cambiando.</span><span class="sxs-lookup"><span data-stu-id="9d2ef-104">The admin center is changing.</span></span> <span data-ttu-id="9d2ef-105">Se alcuni dettagli non corrispondono a quelli presentati qui, vedere [Informazioni sulla nuova interfaccia di amministrazione di Microsoft 365](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="9d2ef-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span></span>

::: moniker-end

> [!IMPORTANT]
> <span data-ttu-id="9d2ef-106">Gli aggiornamenti di Microsoft 365 descritti in questo articolo si applicano a Microsoft 365, SharePoint Online ed Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="9d2ef-106">The Microsoft 365 updates described in this article apply to Microsoft 365, SharePoint Online, and Exchange Online.</span></span> <span data-ttu-id="9d2ef-107">Queste opzioni di rilascio sono modi mirati e più efficaci per rilasciare le modifiche a Microsoft 365, ma non possono essere garantite in qualsiasi momento o per tutti gli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="9d2ef-107">These release options are targeted, best effort ways to release changes to Microsoft 365 but cannot be guaranteed at all times or for all updates.</span></span> <span data-ttu-id="9d2ef-108">Non si applicano alle app di Microsoft 365, Skype for Business, Microsoft Teams e ai servizi correlati.</span><span class="sxs-lookup"><span data-stu-id="9d2ef-108">They do not apply to Microsoft 365 Apps, Skype for Business, Microsoft Teams, and related services.</span></span> <span data-ttu-id="9d2ef-109">Per informazioni sulle opzioni di rilascio per Microsoft 365 Apps, vedere Panoramica dei canali di [aggiornamento per Microsoft 365 Apps.](/deployoffice/overview-update-channels)</span><span class="sxs-lookup"><span data-stu-id="9d2ef-109">For information about release options for Microsoft 365 Apps, see [Overview of update channels for Microsoft 365 Apps](/deployoffice/overview-update-channels).</span></span>

<span data-ttu-id="9d2ef-110">Con Microsoft 365, si ricevono nuovi aggiornamenti di prodotti e funzionalità non appena diventano disponibili invece di eseguire aggiornamenti costosi ogni pochi anni.</span><span class="sxs-lookup"><span data-stu-id="9d2ef-110">With Microsoft 365, you receive new product updates and features as they become available instead of doing costly updates every few years.</span></span> <span data-ttu-id="9d2ef-111">È possibile gestire il modo in cui l'organizzazione riceve questi aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="9d2ef-111">You can manage how your organization receives these updates.</span></span> <span data-ttu-id="9d2ef-112">Ad esempio, è possibile iscriversi a un rilascio anticipato in modo che l'organizzazione riceva prima gli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="9d2ef-112">For example, you can sign up for an early release so that your organization receives updates first.</span></span> <span data-ttu-id="9d2ef-113">È possibile specificare che solo determinati utenti ricevano gli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="9d2ef-113">You can designate that only certain individuals receive the updates.</span></span> <span data-ttu-id="9d2ef-114">In caso contrario, è possibile rimanere in base alla pianificazione di rilascio predefinita e ricevere gli aggiornamenti in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="9d2ef-114">Or, you can remain on the default release schedule and receive the updates later.</span></span> <span data-ttu-id="9d2ef-115">In questo articolo vengono illustrate le diverse opzioni di rilascio e viene spiegato come utilizzarle per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="9d2ef-115">This article explains the different release options and how you can use them for your organization.</span></span>

## <a name="how-it-works---release-validation"></a><span data-ttu-id="9d2ef-116">Funzionamento - Convalida dei rilasci</span><span class="sxs-lookup"><span data-stu-id="9d2ef-116">How it works - release validation</span></span>

<span data-ttu-id="9d2ef-117">Qualsiasi nuova versione viene prima testata e convalidata dal team delle funzionalità, quindi dall'intero team delle funzionalità di Microsoft 365, seguito da tutti i microsoft.</span><span class="sxs-lookup"><span data-stu-id="9d2ef-117">Any new release is first tested and validated by the feature team, then by the entire Microsoft 365 feature team, followed by all of Microsoft.</span></span> <span data-ttu-id="9d2ef-118">Dopo il test e la convalida interni, il passaggio successivo è il rilascio **Targeted Release** (precedentemente noto come First Release) per i clienti che hanno acconsentito esplicitamente.</span><span class="sxs-lookup"><span data-stu-id="9d2ef-118">After internal testing and validation, the next step is a **Targeted release** (formerly known as First release) to customers who opt in.</span></span> <span data-ttu-id="9d2ef-119">A ogni anello di rilascio, Microsoft raccoglie feedback dagli utenti e convalida ulteriormente la qualità monitorando le metriche di utilizzo principali.</span><span class="sxs-lookup"><span data-stu-id="9d2ef-119">At each release ring, Microsoft collects feedback and further validates quality by monitoring key usage metrics.</span></span> <span data-ttu-id="9d2ef-120">Questa serie di convalide progressive viene applicata per garantire che la versione risulti quanto più stabile possibile in tutto il mondo.</span><span class="sxs-lookup"><span data-stu-id="9d2ef-120">This series of progressive validation is in place to make sure the worldwide-release is as robust as possible.</span></span> <span data-ttu-id="9d2ef-121">I rilasci sono illustrati nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="9d2ef-121">The releases are pictured in the following figure.</span></span> 
  
![Rilasciare gli anelli di convalida per Microsoft 365](../../media/73611ed3-2d8c-4e7b-8074-9f03b239f9ed.png)
  
<span data-ttu-id="9d2ef-123">Per gli aggiornamenti significativi, i clienti vengono inizialmente informati dalla roadmap di [Microsoft 365.](https://products.office.com/business/office-365-roadmap)</span><span class="sxs-lookup"><span data-stu-id="9d2ef-123">For significant updates, customers are initially notified by the [Microsoft 365 Roadmap](https://products.office.com/business/office-365-roadmap).</span></span> <span data-ttu-id="9d2ef-124">Quando un aggiornamento si avvicina alla distribuzione, viene comunicato tramite il Centro messaggi di [Microsoft 365.](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter)</span><span class="sxs-lookup"><span data-stu-id="9d2ef-124">As an update gets closer to rolling out, it is communicated through your [Microsoft 365 Message center](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter).</span></span>

> [!NOTE]
> <span data-ttu-id="9d2ef-125">È necessario un account Microsoft 365 o Azure AD per accedere al Centro messaggi tramite [l'interfaccia di amministrazione.](/office365/admin/admin-overview/about-the-admin-center)</span><span class="sxs-lookup"><span data-stu-id="9d2ef-125">You need a Microsoft 365 or Azure AD account to access your Message center through the [admin center](/office365/admin/admin-overview/about-the-admin-center).</span></span> <span data-ttu-id="9d2ef-126">Gli utenti del piano home di Microsoft 365 non dispongono di un'interfaccia di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="9d2ef-126">Microsoft 365 home plan users do not have an admin center.</span></span>


## <a name="standard-release"></a><span data-ttu-id="9d2ef-127">Standard Release</span><span class="sxs-lookup"><span data-stu-id="9d2ef-127">Standard release</span></span>

<span data-ttu-id="9d2ef-128">Questa è l'opzione predefinita in cui l'utente e gli utenti ricevono gli aggiornamenti più recenti quando vengono rilasciati su larga base a tutti i clienti.</span><span class="sxs-lookup"><span data-stu-id="9d2ef-128">This is the default option where you and your users receive the latest updates when they're released broadly to all customers.</span></span>
  
<span data-ttu-id="9d2ef-129">Una buona pratica consiste nel lasciare la maggior parte degli utenti nel rilascio **Standard** e professionisti IT e power users in **Rilascio** mirato per valutare nuove funzionalità e preparare i team a supportare gli utenti aziendali e i dirigenti.</span><span class="sxs-lookup"><span data-stu-id="9d2ef-129">A good practice is to leave the majority of users in **Standard release** and IT Pros and power users in **Targeted release** to evaluate new features and prepare teams to support business users and executives.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="9d2ef-130">Se si passa dalla versione Targeted Release alla versione Standard Release, gli utenti potrebbero perdere l'accesso alle funzionalità non ancora incluse in Standard Release.</span><span class="sxs-lookup"><span data-stu-id="9d2ef-130">If you switch from targeted release back to standard release track, your users may lose access to features that haven't reached standard release yet.</span></span> 
  
## <a name="targeted-release"></a><span data-ttu-id="9d2ef-131">Rilascio assegnato</span><span class="sxs-lookup"><span data-stu-id="9d2ef-131">Targeted release</span></span>

<span data-ttu-id="9d2ef-p107">Questa opzione consente di ricevere per primi gli aggiornamenti più recenti e di contribuire a migliorare il prodotto fornendo un riscontro precoce. È possibile specificare singole persone o l'intera organizzazione come destinatari degli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="9d2ef-p107">With this option, you and your users can be the first to see the latest updates and help shape the product by providing early feedback. You can choose to have individuals or the entire organization receive updates early.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="9d2ef-p108">Gli aggiornamenti di grandi dimensioni o complessi possono richiedere più tempo di altri per evitare un impatto negativo sugli utenti. L'esatta tempistica per un rilascio non è garantita in alcun modo.</span><span class="sxs-lookup"><span data-stu-id="9d2ef-p108">Large or complex updates may take longer than others so that no users are adversely affected. There is no guarantee on the exact timeline of a release.</span></span> 
  
### <a name="targeted-release-for-entire-organization"></a><span data-ttu-id="9d2ef-136">Targeted Release per l'intera organizzazione</span><span class="sxs-lookup"><span data-stu-id="9d2ef-136">Targeted release for entire organization</span></span>

<span data-ttu-id="9d2ef-137">Se si [configura l'opzione di rilascio nell'interfaccia di amministrazione](#set-up-the-release-option-in-the-admin-center) per questa opzione, tutti gli utenti otterrà l'esperienza di rilascio mirato.</span><span class="sxs-lookup"><span data-stu-id="9d2ef-137">If you [Set up the release option in the admin center](#set-up-the-release-option-in-the-admin-center) for this option, all your users will get the Targeted release experience.</span></span> <span data-ttu-id="9d2ef-138">Per le organizzazioni con più di 300 utenti, è consigliabile usare un abbonamento di test per questa opzione.</span><span class="sxs-lookup"><span data-stu-id="9d2ef-138">For organizations with more than 300 users, we recommend using a test subscription for this option.</span></span> <span data-ttu-id="9d2ef-139">Per informazioni sull'abbonamento di test, contattare il proprio referente Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9d2ef-139">For test subscription information, please reach out to your Microsoft contact.</span></span> 
  
### <a name="targeted-release-for-selected-users"></a><span data-ttu-id="9d2ef-140">Targeted Release per utenti selezionati</span><span class="sxs-lookup"><span data-stu-id="9d2ef-140">Targeted release for selected users</span></span>

<span data-ttu-id="9d2ef-141">Se si [configura l'opzione di](#set-up-the-release-option-in-the-admin-center) rilascio nell'interfaccia di amministrazione per questa opzione, è possibile definire utenti specifici, in genere utenti esperti, per ricevere l'accesso anticipato a funzionalità e funzionalità.</span><span class="sxs-lookup"><span data-stu-id="9d2ef-141">If you [Set up the release option in the admin center](#set-up-the-release-option-in-the-admin-center) for this option, you can define specific users, usually power users, to receive early access to features and functionality.</span></span> 
  
## <a name="benefits-of-targeted-release"></a><span data-ttu-id="9d2ef-142">Vantaggi della versione Targeted Release</span><span class="sxs-lookup"><span data-stu-id="9d2ef-142">Benefits of Targeted release</span></span>

<span data-ttu-id="9d2ef-143">Il rilascio mirato consente agli amministratori, ai responsabili delle modifiche o a chiunque altro responsabile degli aggiornamenti di Microsoft 365 di prepararsi per le modifiche future consentendo loro di:</span><span class="sxs-lookup"><span data-stu-id="9d2ef-143">Targeted release allows admins, change managers, or anyone else responsible for Microsoft 365 updates to prepare for the upcoming changes by letting them:</span></span>
  
- <span data-ttu-id="9d2ef-144">Testare e convalidare i nuovi aggiornamenti prima che vengano rilasciate a tutti gli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="9d2ef-144">Test and validate new updates before they are released to all the users in the organization.</span></span>
    
- <span data-ttu-id="9d2ef-145">Preparare la documentazione e le notifiche utente prima del rilascio degli aggiornamenti in tutto il mondo.</span><span class="sxs-lookup"><span data-stu-id="9d2ef-145">Prepare user notification and documentation before updates are released worldwide.</span></span>
    
- <span data-ttu-id="9d2ef-146">Preparare l'help desk interno per le modifiche future.</span><span class="sxs-lookup"><span data-stu-id="9d2ef-146">Prepare internal help-desk for upcoming changes.</span></span>
    
- <span data-ttu-id="9d2ef-147">Controllare le revisioni relative a sicurezza e conformità.</span><span class="sxs-lookup"><span data-stu-id="9d2ef-147">Go through compliance and security reviews.</span></span>
    
- <span data-ttu-id="9d2ef-148">Usare i controlli delle funzionalità, se applicabili, per controllare il rilascio degli aggiornamenti agli utenti finali.</span><span class="sxs-lookup"><span data-stu-id="9d2ef-148">Use feature controls, where applicable, to control the release of updates to end users.</span></span>
    
## <a name="set-up-the-release-option-in-the-admin-center"></a><span data-ttu-id="9d2ef-149">Configurare l'opzione di rilascio nell'interfaccia di amministrazione</span><span class="sxs-lookup"><span data-stu-id="9d2ef-149">Set up the release option in the admin center</span></span>

<span data-ttu-id="9d2ef-150">È possibile modificare il modo in cui l'organizzazione riceve gli aggiornamenti di Microsoft 365 seguendo questa procedura.</span><span class="sxs-lookup"><span data-stu-id="9d2ef-150">You can change how your organization receives Microsoft 365 updates by following these steps.</span></span> <span data-ttu-id="9d2ef-151">Devi essere un amministratore globale in Microsoft 365 per acconsentire esplicitamente.</span><span class="sxs-lookup"><span data-stu-id="9d2ef-151">You have to be a global admin in Microsoft 365 to opt in.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="9d2ef-152">L'applicazione delle modifiche seguenti in Microsoft 365 può richiedere fino a 24 ore.</span><span class="sxs-lookup"><span data-stu-id="9d2ef-152">It can take up to 24 hours for the below changes to take effect in Microsoft 365.</span></span> <span data-ttu-id="9d2ef-153">Se si disattiva l'opzione Targeted Release dopo averla abilitata, è possibile che gli utenti non possano più accedere alle funzionalità non ancora inserite nel rilascio pianificato.</span><span class="sxs-lookup"><span data-stu-id="9d2ef-153">If you opt out of targeted release after enabling it, your users may lose access to features that haven't reached the scheduled release yet.</span></span> 
  
1. <span data-ttu-id="9d2ef-154">Nell'interfaccia di amministrazione passare a Impostazioni Impostazione organizzazione e nella scheda  >   **Profilo organizzazione** scegliere Preferenze **di rilascio.**</span><span class="sxs-lookup"><span data-stu-id="9d2ef-154">In the admin center, go to the **Settings** > **Org Setting**, and under the **Organization profile** tab, choose **Release preferences**.</span></span>

5. <span data-ttu-id="9d2ef-155">Per disabilitare la versione di destinazione, selezionare **Rilascio standard,** quindi **selezionare Salva modifiche.**</span><span class="sxs-lookup"><span data-stu-id="9d2ef-155">To disable targeted release, select **Standard release**, then select **Save changes**.</span></span> 
    
6. <span data-ttu-id="9d2ef-156">Per abilitare il rilascio mirato per tutti gli utenti dell'organizzazione, selezionare **Rilascio mirato per tutti,** quindi selezionare **Salva modifiche.**</span><span class="sxs-lookup"><span data-stu-id="9d2ef-156">To enable targeted release for all users in your organization, select **Targeted release for everyone**, then select **Save changes**.</span></span> 
    
7. <span data-ttu-id="9d2ef-157">Per abilitare il rilascio mirato per alcune persone dell'organizzazione, selezionare **Rilascio mirato per** gli utenti selezionati, quindi selezionare Salva **modifiche.**</span><span class="sxs-lookup"><span data-stu-id="9d2ef-157">To enable targeted release for some people in your organization, select **Targeted release for selected users**, then select **Save changes**.</span></span> 
    
8. <span data-ttu-id="9d2ef-158">Scegliere **Seleziona utenti** per aggiungere gli utenti uno alla volta oppure Carica **utenti** per aggiungerli in blocco.</span><span class="sxs-lookup"><span data-stu-id="9d2ef-158">Choose **Select users** to add users one at a time, or **Upload users** to add them in bulk.</span></span>
    
9. <span data-ttu-id="9d2ef-159">Dopo aver aggiunto gli utenti, selezionare **Salva modifiche.**</span><span class="sxs-lookup"><span data-stu-id="9d2ef-159">When you're done adding users, select **Save changes**.</span></span>


  
## <a name="learn-more"></a><span data-ttu-id="9d2ef-160">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="9d2ef-160">Learn more</span></span>

<span data-ttu-id="9d2ef-161">Scopri come gestire [i messaggi nel](/office365/admin/manage/message-center) centro messaggi di Microsoft [365](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter) per ricevere notifiche sui prossimi aggiornamenti e rilasci di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9d2ef-161">Discover how to [manage messages](/office365/admin/manage/message-center) in your [Microsoft 365 Message center](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter) to get notifications about upcoming Microsoft 365 updates and releases.</span></span>

## <a name="related-articles"></a><span data-ttu-id="9d2ef-162">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="9d2ef-162">Related Articles</span></span>

[<span data-ttu-id="9d2ef-163">Office Insider</span><span class="sxs-lookup"><span data-stu-id="9d2ef-163">Office Insider</span></span>](https://insider.office.com/join/windows)
