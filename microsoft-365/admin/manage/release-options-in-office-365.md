---
title: Configurare le opzioni di rilascio standard o di destinazione
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
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 3b3adfa4-1777-4ff0-b606-fb8732101f47
description: Informazioni su come configurare l'opzione di rilascio per gli aggiornamenti di nuovi prodotti e funzionalità nell'interfaccia di amministrazione di Microsoft 365.
ms.openlocfilehash: fc931893e95ff053cd251b6c1b12bfdbaadf49ae
ms.sourcegitcommit: 7ff75a0f45371b247d975fc61cfa286f5b6f42f6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2020
ms.locfileid: "44139650"
---
# <a name="set-up-the-standard-or-targeted-release-options"></a><span data-ttu-id="7de14-103">Configurare le opzioni di rilascio standard o di destinazione</span><span class="sxs-lookup"><span data-stu-id="7de14-103">Set up the Standard or Targeted release options</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="7de14-104">L'interfaccia di amministrazione cambia.</span><span class="sxs-lookup"><span data-stu-id="7de14-104">The admin center is changing.</span></span> <span data-ttu-id="7de14-105">Se l'esperienza non corrisponde ai dettagli presentati, vedere [About The New Microsoft 365 Admin Center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="7de14-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="7de14-106">Con Microsoft 365, vengono visualizzati nuovi aggiornamenti e funzionalità del prodotto quando diventano disponibili invece di effettuare aggiornamenti costosi ogni pochi anni.</span><span class="sxs-lookup"><span data-stu-id="7de14-106">With Microsoft 365, you receive new product updates and features as they become available instead of doing costly updates every few years.</span></span> <span data-ttu-id="7de14-107">È possibile gestire la modalità di ricezione degli aggiornamenti da parte dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="7de14-107">You can manage how your organization receives these updates.</span></span> <span data-ttu-id="7de14-108">Ad esempio, è possibile iscriversi per una versione anticipata in modo che l'organizzazione riceva prima gli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="7de14-108">For example, you can sign up for an early release so that your organization receives updates first.</span></span> <span data-ttu-id="7de14-109">È possibile indicare che solo alcuni utenti ricevono gli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="7de14-109">You can designate that only certain individuals receive the updates.</span></span> <span data-ttu-id="7de14-110">In alternativa, è possibile rimanere nella pianificazione di rilascio predefinita e ricevere gli aggiornamenti in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="7de14-110">Or, you can remain on the default release schedule and receive the updates later.</span></span> <span data-ttu-id="7de14-111">In questo articolo vengono illustrate le diverse opzioni di rilascio e come è possibile utilizzarle per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="7de14-111">This article explain the different release options and how you can use them for your organization.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="7de14-112">Gli aggiornamenti di Microsoft 365 descritti in questo articolo si applicano a Microsoft 365, SharePoint Online ed Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="7de14-112">The Microsoft 365 updates described in this article apply to Microsoft 365, SharePoint Online, and Exchange Online.</span></span> <span data-ttu-id="7de14-113">Non si applicano a Skype for business e ai servizi correlati.</span><span class="sxs-lookup"><span data-stu-id="7de14-113">They do not apply to Skype for Business and related services.</span></span> <span data-ttu-id="7de14-114">Queste opzioni di rilascio sono mirate, le migliori modalità per rilasciare le modifiche a Microsoft 365 ma non possono essere garantite in qualsiasi momento o per tutti gli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="7de14-114">These release options are targeted, best effort ways to release changes to Microsoft 365 but cannot be guaranteed at all times or for all updates.</span></span> 
  
## <a name="how-it-works---release-validation"></a><span data-ttu-id="7de14-115">Funzionamento - Convalida dei rilasci</span><span class="sxs-lookup"><span data-stu-id="7de14-115">How it works - release validation</span></span>

<span data-ttu-id="7de14-116">Tutte le nuove versioni sono state testate e convalidate dal team di funzionalità, quindi da tutto il team Microsoft 365 feature, seguito da tutti Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7de14-116">Any new release is first tested and validated by the feature team, then by the entire Microsoft 365 feature team, followed by all of Microsoft.</span></span> <span data-ttu-id="7de14-117">Dopo il test e la convalida interni, il passaggio successivo è il rilascio **Targeted Release** (precedentemente noto come First Release) per i clienti che hanno acconsentito esplicitamente.</span><span class="sxs-lookup"><span data-stu-id="7de14-117">After internal testing and validation, the next step is a **Targeted release** (formerly known as First release) to customers who opt in.</span></span> <span data-ttu-id="7de14-118">A ogni anello di rilascio, Microsoft raccoglie feedback dagli utenti e convalida ulteriormente la qualità monitorando le metriche di utilizzo principali.</span><span class="sxs-lookup"><span data-stu-id="7de14-118">At each release ring, Microsoft collects feedback and further validates quality by monitoring key usage metrics.</span></span> <span data-ttu-id="7de14-119">Questa serie di convalide progressive viene applicata per garantire che la versione risulti quanto più stabile possibile in tutto il mondo.</span><span class="sxs-lookup"><span data-stu-id="7de14-119">This series of progressive validation is in place to make sure the worldwide-release is as robust as possible.</span></span> <span data-ttu-id="7de14-120">I rilasci sono illustrati nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="7de14-120">The releases are pictured in the following figure.</span></span> 
  
![Rilasci gli anelli di convalida per Microsoft 365](../../media/73611ed3-2d8c-4e7b-8074-9f03b239f9ed.png)
  
<span data-ttu-id="7de14-122">Per gli aggiornamenti significativi, i clienti di Office vengono inizialmente informati dalla [Roadmap di Microsoft 365](https://products.office.com/business/office-365-roadmap).</span><span class="sxs-lookup"><span data-stu-id="7de14-122">For significant updates, Office customers are initially notified by the [Microsoft 365 Roadmap](https://products.office.com/business/office-365-roadmap).</span></span> <span data-ttu-id="7de14-123">Man mano che un aggiornamento si avvicina all'implementazione, viene comunicato tramite il [centro messaggi di Microsoft 365](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter).</span><span class="sxs-lookup"><span data-stu-id="7de14-123">As an update gets closer to rolling out, it is communicated through your [Microsoft 365 Message center](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter).</span></span>

> [!NOTE]
> <span data-ttu-id="7de14-124">Per accedere al centro messaggi tramite l'interfaccia di [Amministrazione](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center), è necessario un account di Microsoft 365 o Azure ad.</span><span class="sxs-lookup"><span data-stu-id="7de14-124">You need a Microsoft 365 or Azure AD account to access your Message center through the [admin center](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center).</span></span> <span data-ttu-id="7de14-125">Microsoft 365 Home Plan gli utenti non dispongono di un centro di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="7de14-125">Microsoft 365 home plan users do not have an admin center.</span></span>


## <a name="standard-release"></a><span data-ttu-id="7de14-126">Standard Release</span><span class="sxs-lookup"><span data-stu-id="7de14-126">Standard release</span></span>

<span data-ttu-id="7de14-127">Questa è l'opzione predefinita in cui l'utente e gli utenti ricevono gli aggiornamenti più recenti quando vengono rilasciati in generale a tutti i clienti.</span><span class="sxs-lookup"><span data-stu-id="7de14-127">This is the default option where you and your users receive the latest updates when they're released broadly to all customers.</span></span>
  
<span data-ttu-id="7de14-128">Una buona prassi è quella di lasciare la maggior parte degli utenti in **versione standard** e i professionisti IT e gli utenti di Power in **Release mirate** per valutare nuove funzionalità e preparare i team per supportare gli utenti e i dirigenti aziendali.</span><span class="sxs-lookup"><span data-stu-id="7de14-128">A good practice is to leave the majority of users in **Standard release** and IT Pros and power users in **Targeted release** to evaluate new features and prepare teams to support business users and executives.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="7de14-129">Se si passa dalla versione Targeted Release alla versione Standard Release, gli utenti potrebbero perdere l'accesso alle funzionalità non ancora incluse in Standard Release.</span><span class="sxs-lookup"><span data-stu-id="7de14-129">If you switch from targeted release back to standard release track, your users may lose access to features that haven't reached standard release yet.</span></span> 
  
## <a name="targeted-release"></a><span data-ttu-id="7de14-130">Rilascio assegnato</span><span class="sxs-lookup"><span data-stu-id="7de14-130">Targeted release</span></span>

<span data-ttu-id="7de14-p107">Questa opzione consente di ricevere per primi gli aggiornamenti più recenti e di contribuire a migliorare il prodotto fornendo un riscontro precoce. È possibile specificare singole persone o l'intera organizzazione come destinatari degli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="7de14-p107">With this option, you and your users can be the first to see the latest updates and help shape the product by providing early feedback. You can choose to have individuals or the entire organization receive updates early.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="7de14-p108">Gli aggiornamenti di grandi dimensioni o complessi possono richiedere più tempo di altri per evitare un impatto negativo sugli utenti. L'esatta tempistica per un rilascio non è garantita in alcun modo.</span><span class="sxs-lookup"><span data-stu-id="7de14-p108">Large or complex updates may take longer than others so that no users are adversely affected. There is no guarantee on the exact timeline of a release.</span></span> 
  
### <a name="targeted-release-for-entire-organization"></a><span data-ttu-id="7de14-135">Targeted Release per l'intera organizzazione</span><span class="sxs-lookup"><span data-stu-id="7de14-135">Targeted release for entire organization</span></span>

<span data-ttu-id="7de14-136">Se si [Configura l'opzione di rilascio nell'](#set-up-the-release-option-in-the-admin-center) interfaccia di amministrazione per questa opzione, tutti gli utenti riceveranno l'esperienza di rilascio mirata.</span><span class="sxs-lookup"><span data-stu-id="7de14-136">If you [Set up the release option in the admin center](#set-up-the-release-option-in-the-admin-center) for this option, all your users will get the Targeted release experience.</span></span> <span data-ttu-id="7de14-137">Per le organizzazioni con più di 300 utenti, è consigliabile usare un abbonamento di test per questa opzione.</span><span class="sxs-lookup"><span data-stu-id="7de14-137">For organizations with more than 300 users, we recommend using a test subscription for this option.</span></span> <span data-ttu-id="7de14-138">Per informazioni sull'abbonamento di test, contattare il proprio referente Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7de14-138">For test subscription information, please reach out to your Microsoft contact.</span></span> 
  
### <a name="targeted-release-for-selected-users"></a><span data-ttu-id="7de14-139">Targeted Release per utenti selezionati</span><span class="sxs-lookup"><span data-stu-id="7de14-139">Targeted release for selected users</span></span>

<span data-ttu-id="7de14-140">Se si [Configura l'opzione di rilascio nell'](#set-up-the-release-option-in-the-admin-center) interfaccia di amministrazione per questa opzione, è possibile definire gli utenti specifici, in genere gli utenti di alimentazione, per ricevere l'accesso precoce alle caratteristiche e alle funzionalità.</span><span class="sxs-lookup"><span data-stu-id="7de14-140">If you [Set up the release option in the admin center](#set-up-the-release-option-in-the-admin-center) for this option, you can define specific users, usually power users, to receive early access to features and functionality.</span></span> 
  
## <a name="benefits-of-targeted-release"></a><span data-ttu-id="7de14-141">Vantaggi della versione Targeted Release</span><span class="sxs-lookup"><span data-stu-id="7de14-141">Benefits of Targeted release</span></span>

<span data-ttu-id="7de14-142">La versione mirata consente agli amministratori, ai responsabili delle modifiche o a chiunque altro responsabile degli aggiornamenti di Microsoft 365 di prepararsi per le modifiche imminenti, lasciandole:</span><span class="sxs-lookup"><span data-stu-id="7de14-142">Targeted release allows admins, change managers, or anyone else responsible for Microsoft 365 updates to prepare for the upcoming changes by letting them:</span></span>
  
- <span data-ttu-id="7de14-143">Testare e convalidare i nuovi aggiornamenti prima che vengano rilasciate a tutti gli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="7de14-143">Test and validate new updates before they are released to all the users in the organization.</span></span>
    
- <span data-ttu-id="7de14-144">Preparare la documentazione e le notifiche utente prima del rilascio degli aggiornamenti in tutto il mondo.</span><span class="sxs-lookup"><span data-stu-id="7de14-144">Prepare user notification and documentation before updates are released worldwide.</span></span>
    
- <span data-ttu-id="7de14-145">Preparare l'help desk interno per le modifiche future.</span><span class="sxs-lookup"><span data-stu-id="7de14-145">Prepare internal help-desk for upcoming changes.</span></span>
    
- <span data-ttu-id="7de14-146">Controllare le revisioni relative a sicurezza e conformità.</span><span class="sxs-lookup"><span data-stu-id="7de14-146">Go through compliance and security reviews.</span></span>
    
- <span data-ttu-id="7de14-147">Usare i controlli delle funzionalità, se applicabili, per controllare il rilascio degli aggiornamenti agli utenti finali.</span><span class="sxs-lookup"><span data-stu-id="7de14-147">Use feature controls, where applicable, to control the release of updates to end users.</span></span>
    
## <a name="set-up-the-release-option-in-the-admin-center"></a><span data-ttu-id="7de14-148">Configurare l'opzione di rilascio nell'interfaccia di amministrazione</span><span class="sxs-lookup"><span data-stu-id="7de14-148">Set up the release option in the admin center</span></span>

<span data-ttu-id="7de14-149">È possibile modificare il modo in cui l'organizzazione riceve gli aggiornamenti di Microsoft 365 attenendosi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="7de14-149">You can change how your organization receives Microsoft 365 updates by following these steps.</span></span> <span data-ttu-id="7de14-150">È necessario essere un amministratore globale in Microsoft 365 per l'opt-in.</span><span class="sxs-lookup"><span data-stu-id="7de14-150">You have to be a global admin in Microsoft 365 to opt in.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="7de14-151">È possibile richiedere fino a 24 ore per rendere effettive le modifiche riportate di seguito in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7de14-151">It can take up to 24 hours for the below changes to take effect in Microsoft 365.</span></span> <span data-ttu-id="7de14-152">Se si disattiva l'opzione Targeted Release dopo averla abilitata, è possibile che gli utenti non possano più accedere alle funzionalità non ancora inserite nel rilascio pianificato.</span><span class="sxs-lookup"><span data-stu-id="7de14-152">If you opt out of targeted release after enabling it, your users may lose access to features that haven't reached the scheduled release yet.</span></span> 
  
1. <span data-ttu-id="7de14-153">Nell'interfaccia di amministrazione, passare all'impostazione **Impostazioni** > **Setting**e nella scheda **profilo organizzazione** scegliere **Preferenze di rilascio**.</span><span class="sxs-lookup"><span data-stu-id="7de14-153">In the admin center, go to the **Settings** > **Setting**, and under the **Organization profile** tab, choose **Release preferences**.</span></span>

5. <span data-ttu-id="7de14-154">Per disabilitare la versione di destinazione, selezionare **versione standard**, quindi fare clic su **Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="7de14-154">To disable targeted release, select **Standard release**, then select **Save changes**.</span></span> 
    
6. <span data-ttu-id="7de14-155">Per abilitare la versione di destinazione per tutti gli utenti dell'organizzazione, selezionare **rilasci mirati per tutti**, quindi selezionare **Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="7de14-155">To enable targeted release for all users in your organization, select **Targeted release for everyone**, then select **Save changes**.</span></span> 
    
7. <span data-ttu-id="7de14-156">Per abilitare la versione di destinazione per alcuni utenti dell'organizzazione, selezionare **rilasci mirati per i clienti selezionati**, quindi selezionare **Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="7de14-156">To enable targeted release for some people in your organization, select **Targeted release for selected users**, then select **Save changes**.</span></span> 
    
8. <span data-ttu-id="7de14-157">Scegliere **selezionare gli** utenti per aggiungere gli utenti uno alla volta oppure **caricare gli utenti** per aggiungerli in blocco.</span><span class="sxs-lookup"><span data-stu-id="7de14-157">Choose **Select users** to add users one at a time, or **Upload users** to add them in bulk.</span></span>
    
9. <span data-ttu-id="7de14-158">Dopo aver completato l'aggiunta di utenti, selezionare **Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="7de14-158">When you're done adding users, select **Save changes**.</span></span>



## <a name="get-the-targeted-release-version-of-office"></a><span data-ttu-id="7de14-159">Ottenere la versione finale di Office</span><span class="sxs-lookup"><span data-stu-id="7de14-159">Get the Targeted release version of Office</span></span>

<span data-ttu-id="7de14-p112">Per installare una build Targeted Release di Office, [eseguire questa procedura](https://support.office.com/article/4dd8ba40-73c0-4468-b778-c7b744d03ead). Questa build consente di accedere in anteprima alle nuove funzionalità di Office 2016 per desktop Windows.</span><span class="sxs-lookup"><span data-stu-id="7de14-p112">To install a targeted release build of Office, [follow these steps](https://support.office.com/article/4dd8ba40-73c0-4468-b778-c7b744d03ead). This gives you early access to the new features of Office 2016 for Windows desktops.</span></span>
  
## <a name="learn-more"></a><span data-ttu-id="7de14-162">Scopri di più</span><span class="sxs-lookup"><span data-stu-id="7de14-162">Learn more</span></span>

<span data-ttu-id="7de14-163">Informazioni su come [gestire i messaggi](https://docs.microsoft.com/office365/admin/manage/message-center) nel [centro messaggi di Microsoft 365](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter) per ottenere notifiche relative agli aggiornamenti e rilasci imminenti di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7de14-163">Discover how to [manage messages](https://docs.microsoft.com/office365/admin/manage/message-center) in your [Microsoft 365 Message center](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter) to get notifications about upcoming Microsoft 365 updates and releases.</span></span>
