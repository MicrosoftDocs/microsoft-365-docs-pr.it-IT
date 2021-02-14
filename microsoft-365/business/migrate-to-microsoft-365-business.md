---
title: Eseguire l'aggiornamento a Microsoft 365 Business Premium da Microsoft 365 Business Standard
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 5b4ba843-24b8-4526-8e1f-f9b9eab89d06
description: Informazioni sulla differenza tra Microsoft 365 Business Standard e Microsoft 365 Business Premium e su come eseguire l'aggiornamento a Microsoft 365 Business Premium.
ms.openlocfilehash: bdab8165623170926b17efa4cae9408b78a2f5f5
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "44401383"
---
# <a name="upgrade-to-microsoft-365-business-premium-from-microsoft-365-business-standard"></a><span data-ttu-id="59262-103">Eseguire l'aggiornamento a Microsoft 365 Business Premium da Microsoft 365 Business Standard</span><span class="sxs-lookup"><span data-stu-id="59262-103">Upgrade to Microsoft 365 Business Premium from Microsoft 365 Business Standard</span></span>

<span data-ttu-id="59262-104">Se si dispone di un abbonamento a [Microsoft 365 per](https://products.office.com/compare-all-microsoft-office-products-4-column?activetab=tab:primaryr2)le aziende, ad esempio Microsoft 365 Business Standard, è possibile eseguire facilmente l'aggiornamento a Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="59262-104">If you have a [Microsoft 365 for business subscription](https://products.office.com/compare-all-microsoft-office-products-4-column?activetab=tab:primaryr2), for example, Microsoft 365 Business Standard, you can easily upgrade to Microsoft 365 Business Premium.</span></span> <span data-ttu-id="59262-105">Eseguire l'aggiornamento a Microsoft 365 Business Premium se si desidera aggiungere:</span><span class="sxs-lookup"><span data-stu-id="59262-105">Upgrade to Microsoft 365 Business Premium if you want to add:</span></span>

- <span data-ttu-id="59262-106">Windows 10 Pro (per PC che eseguono Windows 8 o versione successiva)</span><span class="sxs-lookup"><span data-stu-id="59262-106">Windows 10 Pro (to PCs running Windows 8 or later)</span></span>

- <span data-ttu-id="59262-107">Controlli semplici che gestiscono i dati business nei dispositivi</span><span class="sxs-lookup"><span data-stu-id="59262-107">Simple controls that manage business data on devices</span></span>

- <span data-ttu-id="59262-108">Funzionalità di sicurezza avanzate.</span><span class="sxs-lookup"><span data-stu-id="59262-108">Advanced security capabilities.</span></span>
<span data-ttu-id="59262-109">Per altre informazioni su Microsoft 365 Business Premium, [vedere Microsoft.com](https://www.microsoft.com/microsoft-365/business)</span><span class="sxs-lookup"><span data-stu-id="59262-109">Find out more about Microsoft 365 Business Premium at [Microsoft.com](https://www.microsoft.com/microsoft-365/business)</span></span>

## <a name="whats-the-difference-between-microsoft-365-business-standard-and-microsoft-365-business-premium"></a><span data-ttu-id="59262-110">Qual è la differenza tra Microsoft 365 Business Standard e Microsoft 365 Business Premium?</span><span class="sxs-lookup"><span data-stu-id="59262-110">What's the difference between Microsoft 365 Business Standard and Microsoft 365 Business Premium?</span></span>

<span data-ttu-id="59262-111">È stato aggiunto un confronto affiancato di questi due piani alla descrizione del servizio [Microsoft 365 Business Premium.](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-business-service-description)</span><span class="sxs-lookup"><span data-stu-id="59262-111">We've added a side-by-side comparison of these two plans to the [Microsoft 365 Business Premium Service Description](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-business-service-description).</span></span> 

## <a name="before-you-get-started"></a><span data-ttu-id="59262-112">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="59262-112">Before you get started</span></span>

- <span data-ttu-id="59262-113">**Quando devo scegliere di eseguire l'aggiornamento?**</span><span class="sxs-lookup"><span data-stu-id="59262-113">**When should I choose to upgrade?**</span></span> <span data-ttu-id="59262-114">L'aggiornamento è la scelta giusta quando si desidera aggiornare **tutti gli utenti** assegnati a un singolo piano.</span><span class="sxs-lookup"><span data-stu-id="59262-114">Upgrade is the right choice when you want to upgrade **all users** assigned to a single plan.</span></span> <span data-ttu-id="59262-115">Quando si sceglie l'aggiornamento, tutti gli utenti del piano passano contemporaneamente a un altro piano.</span><span class="sxs-lookup"><span data-stu-id="59262-115">When you choose upgrade, all plan users get switched to another plan at the same time.</span></span> <span data-ttu-id="59262-116">Se non si desidera aggiornare tutti gli utenti assegnati a un singolo piano, acquistare le licenze per [](../admin/manage/assign-licenses-to-users.md) il nuovo piano (in questo caso Microsoft 365 Business Premium) e assegnare tali licenze singolarmente a ogni utente che si desidera aggiornare.</span><span class="sxs-lookup"><span data-stu-id="59262-116">If you don't want to upgrade everyone assigned to a single plan, buy licenses for the new plan (in this case Microsoft 365 Business Premium), and [assign those licenses individually](../admin/manage/assign-licenses-to-users.md) to each user that you want to upgrade.</span></span>

- <span data-ttu-id="59262-117">**Alcuni componenti aggiuntivi potrebbero impedire l'aggiornamento** Se si tenta di avviare un aggiornamento e si dispone di un componente aggiuntivo che impedisce di continuare, è possibile rimuovere prima il componente aggiuntivo e quindi aggiungerlo di nuovo in un secondo momento, se necessario.</span><span class="sxs-lookup"><span data-stu-id="59262-117">**Some add-ons might prevent the upgrade** If you try to start an upgrade and you have an add-on that prevents you from continuing, you can remove the add-on first, and then add it back later if you still need it.</span></span>

- <span data-ttu-id="59262-118">**Se il piano è stato prepagato** Non esiste un semplice percorso di aggiornamento per i piani prepagati.</span><span class="sxs-lookup"><span data-stu-id="59262-118">**If you prepaid your plan** There isn't a straightforward upgrade path for prepaid plans.</span></span> <span data-ttu-id="59262-119">Saprai se hai un piano prepagato perché hai configurato il piano con un ID prodotto che potresti aver acquistato in uno Store.</span><span class="sxs-lookup"><span data-stu-id="59262-119">You'll know if you have a prepaid plan because you set up your plan using a product ID that you might have purchased in a store.</span></span> <span data-ttu-id="59262-120">Contatta un partner, passa a Microsoft Store o attendi la scadenza del piano prepagato per passare a un nuovo piano.</span><span class="sxs-lookup"><span data-stu-id="59262-120">Contact a partner, go to the Microsoft Store, or wait until your prepaid plan expires to switch to a new plan.</span></span>

## <a name="upgrade-to-microsoft-365-business-premium"></a><span data-ttu-id="59262-121">Eseguire l'aggiornamento a Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="59262-121">Upgrade to Microsoft 365 Business Premium</span></span>

1. <span data-ttu-id="59262-122">Accedere all'interfaccia di amministrazione all'indirizzo <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> .</span><span class="sxs-lookup"><span data-stu-id="59262-122">Sign into the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="59262-123">Vai al riquadro di spostamento e seleziona **Fatturazione** \> **i tuoi prodotti.**</span><span class="sxs-lookup"><span data-stu-id="59262-123">Go to the navigation pane and select **Billing** \> **Your products**.</span></span> <span data-ttu-id="59262-124">Trovare l'abbonamento corrente e selezionarlo per visualizzare i dettagli.</span><span class="sxs-lookup"><span data-stu-id="59262-124">Find your current subscription and select it to view the details.</span></span>

3. <span data-ttu-id="59262-125">Nella pagina successiva selezionare **Aggiorna.**</span><span class="sxs-lookup"><span data-stu-id="59262-125">On the next page, select **Upgrade**.</span></span>

  > [!NOTE]
  > <span data-ttu-id="59262-126">Se viene visualizzato un messaggio che indica che l'aggiornamento dell'abbonamento non è supportato con le licenze basate su gruppo **in Azure Active Directory,** è possibile ignorarlo a meno che non si abbia un'organizzazione di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="59262-126">If you see a message that says **Upgrading your subscription is not supported with group-based licensing in Azure Active Directory**, you can safely ignore this unless you have a very large organization.</span></span> <span data-ttu-id="59262-127">Le organizzazioni che hanno selezionato questa opzione saranno consapevoli del fatto che usano le licenze basate su gruppo.</span><span class="sxs-lookup"><span data-stu-id="59262-127">Organizations who have selected this option will be aware that they're using group-based licensing.</span></span>

4. <span data-ttu-id="59262-128">Successivamente, è possibile visualizzare un elenco di piani a cui è possibile eseguire l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="59262-128">Next, you can view a list of plans that you can upgrade to.</span></span> <span data-ttu-id="59262-129">In questo caso, trovare il piano Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="59262-129">In this case, find the Microsoft 365 Business Premium plan.</span></span> <span data-ttu-id="59262-130">Puoi scorrere verso il basso se vuoi visualizzare tutte le app e i servizi inclusi in questo piano.</span><span class="sxs-lookup"><span data-stu-id="59262-130">You can scroll down if you want to see all the apps and services that are included with this plan.</span></span> <span data-ttu-id="59262-131">In **Microsoft 365 Business Premium** selezionare **Aggiorna** per aggiungere Microsoft 365 Business Premium al carrello.</span><span class="sxs-lookup"><span data-stu-id="59262-131">Under **Microsoft 365 Business Premium**, select **Upgrade** to add Microsoft 365 Business Premium to your cart.</span></span>

5. <span data-ttu-id="59262-132">Nel carrello:</span><span class="sxs-lookup"><span data-stu-id="59262-132">In the cart:</span></span>

    1. <span data-ttu-id="59262-133">Verranno incluse automaticamente le licenze per tutti gli utenti correnti.</span><span class="sxs-lookup"><span data-stu-id="59262-133">We'll automatically include licenses for all your current users.</span></span> <span data-ttu-id="59262-134">Se sono necessarie più o meno licenze, è necessario acquistare e [assegnare tali licenze singolarmente.](../admin/manage/assign-licenses-to-users.md)</span><span class="sxs-lookup"><span data-stu-id="59262-134">If you need more or fewer licenses, you need to [buy and assign those licenses individually](../admin/manage/assign-licenses-to-users.md).</span></span>  
    2. <span data-ttu-id="59262-135">Puoi modificare la modalità di pagamento: mensile o annuale.</span><span class="sxs-lookup"><span data-stu-id="59262-135">You can adjust how you'd like to pay: monthly or yearly.</span></span> <span data-ttu-id="59262-136">Seleziona il menu a discesa per effettuare la scelta.</span><span class="sxs-lookup"><span data-stu-id="59262-136">Select the drop-down menu to make your choice.</span></span>

6. <span data-ttu-id="59262-137">Seleziona **Vai alla cassa,** dove vedrai un riepilogo dell'acquisto, inclusa la modalità di pagamento per questo account.</span><span class="sxs-lookup"><span data-stu-id="59262-137">Select **Go to Checkout** where you'll see a summary of your purchase, including the payment method for this account.</span></span> <span data-ttu-id="59262-138">Puoi anche aggiungere un codice promozionale qui, se disponibile.</span><span class="sxs-lookup"><span data-stu-id="59262-138">You can also add a promo code here if you have one.</span></span>

7. <span data-ttu-id="59262-139">Seleziona **Effettuare l'ordine** per completare l'acquisto.</span><span class="sxs-lookup"><span data-stu-id="59262-139">Select **Place order** to complete your purchase.</span></span>\
<span data-ttu-id="59262-140">La configurazione dei nuovi piani di servizio richiede alcuni minuti a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="59262-140">It takes Microsoft a few minutes to set up your new service plans.</span></span> <span data-ttu-id="59262-141">Per verificare lo stato dell'aggiornamento, selezionare **Controlla stato aggiornamento.**</span><span class="sxs-lookup"><span data-stu-id="59262-141">To check on progress, select **Check upgrade status**.</span></span>

8. <span data-ttu-id="59262-142">Quando il piano è pronto, potrebbe essere necessario completare alcuni passaggi di configurazione aggiuntivi nell'interfaccia di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="59262-142">When your plan is ready, you might need to complete some additional setup steps in the admin center.</span></span> <span data-ttu-id="59262-143">Nel riquadro di spostamento, selezionare **Home per** completare eventuali passaggi di configurazione aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="59262-143">In the navigation pane, select **Home** to complete any additional setup steps.</span></span>

> [!NOTE]
> <span data-ttu-id="59262-144">Si riceverà un rimborso ri diverse per le licenze di Microsoft 365 non più necessarie.</span><span class="sxs-lookup"><span data-stu-id="59262-144">You'll receive a prorated refund for the Microsoft 365 licenses that you no longer need.</span></span> <span data-ttu-id="59262-145">L'addebito sul conto corrente bancario o sulla carta di credito verrà addebitato circa due giorni dopo la configurazione del nuovo piano.</span><span class="sxs-lookup"><span data-stu-id="59262-145">Your bank account or credit card will be charged about two days after you set up the new plan.</span></span>
  
## <a name="protect-user-devices-and-files"></a><span data-ttu-id="59262-146">Proteggere i dispositivi e i file degli utenti</span><span class="sxs-lookup"><span data-stu-id="59262-146">Protect user devices and files</span></span>

<span data-ttu-id="59262-147">Dopo aver assegnato le licenze di Microsoft 365 Business Premium, completare la procedura per iniziare a proteggere dispositivi e file.</span><span class="sxs-lookup"><span data-stu-id="59262-147">Now that Microsoft 365 Business Premium licenses have been assigned, complete steps to start protecting devices and files.</span></span> <span data-ttu-id="59262-148">Verranno utilizzate alcune nuove opzioni incluse nel riquadro di spostamento dell'interfaccia di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="59262-148">You'll use some new options included in the admin center navigation pane.</span></span>
  
1. <span data-ttu-id="59262-149">Nel riquadro di spostamento dell'interfaccia di amministrazione passare a **Criteri** \> **dispositivi.**</span><span class="sxs-lookup"><span data-stu-id="59262-149">In the admin center, in the navigation pane, go to **Devices** \> **Policies**.</span></span>

2. <span data-ttu-id="59262-150">Nella pagina **Criteri dispositivo** selezionare **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="59262-150">On the **Device policies** page, select **Add**.</span></span>

3. <span data-ttu-id="59262-151">Nel riquadro **Aggiungi criterio** assegnare un nome al criterio ,ad esempio Proteggi file di lavoro, e quindi scegliere un tipo di criterio nell'elenco **a** discesa.</span><span class="sxs-lookup"><span data-stu-id="59262-151">In the **Add policy** pane give the policy a name (for example, Protect work files), and then choose a **Policy type** from the drop-down list.</span></span>

    <span data-ttu-id="59262-152">Puoi configurare criteri di applicazione per proteggere i file nei dispositivi Android e iPhone, nonché in Windows 10, e puoi configurare i criteri di configurazione dei dispositivi per i dispositivi Windows 10 di proprietà dell'azienda.</span><span class="sxs-lookup"><span data-stu-id="59262-152">You can set up application policies for protecting files on Android and iPhone devices, as well as Windows 10, and you can set up device configuration policies for company owned Windows 10 devices.</span></span> <span data-ttu-id="59262-153">Per informazioni dettagliate, vedere i collegamenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="59262-153">See the following links for details:</span></span>

    - [<span data-ttu-id="59262-154">Configurare le impostazioni di protezione delle app per i dispositivi Android o iOS</span><span class="sxs-lookup"><span data-stu-id="59262-154">Set app protection settings for Android or iOS devices</span></span>](app-protection-settings-for-android-and-ios.md)

    - [<span data-ttu-id="59262-155">Configurare le impostazioni di protezione delle app per i dispositivi Windows 10</span><span class="sxs-lookup"><span data-stu-id="59262-155">Set application protection settings for Windows 10 devices</span></span>](protection-settings-for-windows-10-devices.md)

    - [<span data-ttu-id="59262-156">Configurare le impostazioni di protezione dei dispositivi per i PC Windows 10</span><span class="sxs-lookup"><span data-stu-id="59262-156">Set device protection settings for Windows 10 PCs</span></span>](protection-settings-for-windows-10-pcs.md)

4. <span data-ttu-id="59262-157">Dopo aver configurato i criteri, l'utente e i dipendenti possono configurare i dispositivi:</span><span class="sxs-lookup"><span data-stu-id="59262-157">After you set up policies, you and your employees can set up devices:</span></span>

    - <span data-ttu-id="59262-158">Se i dispositivi Windows non usano già l'aggiornamento di Windows Pro Creator, dovrai aggiornarli a [Windows Pro Creators Update.](upgrade-to-windows-pro-creators-update.md)</span><span class="sxs-lookup"><span data-stu-id="59262-158">If your Windows devices aren't already using the Windows Pro Creator update, you'll need to [upgrade them to Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span></span>

    - <span data-ttu-id="59262-159">Per la procedura per i dispositivi Windows, vedere Configurare i dispositivi Windows per gli utenti di [Microsoft 365 Business](set-up-windows-devices.md) Premium.</span><span class="sxs-lookup"><span data-stu-id="59262-159">See [Set up Windows devices for Microsoft 365 Business Premium users](set-up-windows-devices.md) for steps for Windows devices.</span></span>

    - <span data-ttu-id="59262-160">Vedere [Configurare i dispositivi mobili per gli utenti di Microsoft 365 Business Premium](set-up-mobile-devices.md) per la procedura per telefoni Android e iPhone.</span><span class="sxs-lookup"><span data-stu-id="59262-160">See [Set up mobile devices for Microsoft 365 Business Premium users](set-up-mobile-devices.md) for steps for Android phones and iPhones.</span></span>