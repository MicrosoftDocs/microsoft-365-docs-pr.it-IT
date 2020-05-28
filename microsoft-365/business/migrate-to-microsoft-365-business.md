---
title: Eseguire l'aggiornamento a Microsoft 365 Business Premium da Microsoft 365 business standard
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
description: Scoprite la differenza tra Microsoft 365 business standard e Microsoft 365 Business Premium e come è possibile eseguire l'aggiornamento a Microsoft 365 Business Premium.
ms.openlocfilehash: bdab8165623170926b17efa4cae9408b78a2f5f5
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "44401383"
---
# <a name="upgrade-to-microsoft-365-business-premium-from-microsoft-365-business-standard"></a><span data-ttu-id="15023-103">Eseguire l'aggiornamento a Microsoft 365 Business Premium da Microsoft 365 business standard</span><span class="sxs-lookup"><span data-stu-id="15023-103">Upgrade to Microsoft 365 Business Premium from Microsoft 365 Business Standard</span></span>

<span data-ttu-id="15023-104">Se si dispone di un [abbonamento a microsoft 365 for business](https://products.office.com/compare-all-microsoft-office-products-4-column?activetab=tab:primaryr2), ad esempio Microsoft 365 business standard, è possibile eseguire facilmente l'aggiornamento a Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="15023-104">If you have a [Microsoft 365 for business subscription](https://products.office.com/compare-all-microsoft-office-products-4-column?activetab=tab:primaryr2), for example, Microsoft 365 Business Standard, you can easily upgrade to Microsoft 365 Business Premium.</span></span> <span data-ttu-id="15023-105">Eseguire l'aggiornamento a Microsoft 365 Business Premium se si desidera aggiungere:</span><span class="sxs-lookup"><span data-stu-id="15023-105">Upgrade to Microsoft 365 Business Premium if you want to add:</span></span>

- <span data-ttu-id="15023-106">Windows 10 Pro (per i computer che eseguono Windows 8 o versioni successive)</span><span class="sxs-lookup"><span data-stu-id="15023-106">Windows 10 Pro (to PCs running Windows 8 or later)</span></span>

- <span data-ttu-id="15023-107">Controlli semplici che gestiscono i dati business nei dispositivi</span><span class="sxs-lookup"><span data-stu-id="15023-107">Simple controls that manage business data on devices</span></span>

- <span data-ttu-id="15023-108">Funzionalità di sicurezza avanzate.</span><span class="sxs-lookup"><span data-stu-id="15023-108">Advanced security capabilities.</span></span>
<span data-ttu-id="15023-109">Per ulteriori informazioni su Microsoft 365 Business Premium, vedere [Microsoft.com](https://www.microsoft.com/microsoft-365/business)</span><span class="sxs-lookup"><span data-stu-id="15023-109">Find out more about Microsoft 365 Business Premium at [Microsoft.com](https://www.microsoft.com/microsoft-365/business)</span></span>

## <a name="whats-the-difference-between-microsoft-365-business-standard-and-microsoft-365-business-premium"></a><span data-ttu-id="15023-110">Qual è la differenza tra Microsoft 365 business standard e Microsoft 365 Business Premium?</span><span class="sxs-lookup"><span data-stu-id="15023-110">What's the difference between Microsoft 365 Business Standard and Microsoft 365 Business Premium?</span></span>

<span data-ttu-id="15023-111">È stato aggiunto un confronto affiancato di questi due piani alla [Descrizione del servizio Microsoft 365 Business Premium](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-business-service-description).</span><span class="sxs-lookup"><span data-stu-id="15023-111">We've added a side-by-side comparison of these two plans to the [Microsoft 365 Business Premium Service Description](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-business-service-description).</span></span> 

## <a name="before-you-get-started"></a><span data-ttu-id="15023-112">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="15023-112">Before you get started</span></span>

- <span data-ttu-id="15023-113">**Quando si sceglie di eseguire l'aggiornamento?**</span><span class="sxs-lookup"><span data-stu-id="15023-113">**When should I choose to upgrade?**</span></span> <span data-ttu-id="15023-114">L'aggiornamento è la scelta giusta quando si desidera aggiornare **tutti gli utenti** assegnati a un singolo piano.</span><span class="sxs-lookup"><span data-stu-id="15023-114">Upgrade is the right choice when you want to upgrade **all users** assigned to a single plan.</span></span> <span data-ttu-id="15023-115">Quando si sceglie l'opzione di aggiornamento, tutti i piani di utenti vengono passati a un altro piano contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="15023-115">When you choose upgrade, all plan users get switched to another plan at the same time.</span></span> <span data-ttu-id="15023-116">Se non si desidera aggiornare tutti gli utenti assegnati a un singolo piano, acquistare le licenze per il nuovo piano (in questo caso Microsoft 365 Business Premium) e [assegnare tali licenze singolarmente](../admin/manage/assign-licenses-to-users.md) a ogni utente che si desidera aggiornare.</span><span class="sxs-lookup"><span data-stu-id="15023-116">If you don't want to upgrade everyone assigned to a single plan, buy licenses for the new plan (in this case Microsoft 365 Business Premium), and [assign those licenses individually](../admin/manage/assign-licenses-to-users.md) to each user that you want to upgrade.</span></span>

- <span data-ttu-id="15023-117">**Alcuni componenti aggiuntivi potrebbero impedire l'aggiornamento** Se si tenta di avviare un aggiornamento e si dispone di un componente aggiuntivo che impedisce di continuare, è possibile rimuovere il componente aggiuntivo e quindi aggiungerlo in un secondo momento, se necessario.</span><span class="sxs-lookup"><span data-stu-id="15023-117">**Some add-ons might prevent the upgrade** If you try to start an upgrade and you have an add-on that prevents you from continuing, you can remove the add-on first, and then add it back later if you still need it.</span></span>

- <span data-ttu-id="15023-118">**Se il piano è stato prepagato** Non esiste un percorso di aggiornamento semplice per i piani prepagati.</span><span class="sxs-lookup"><span data-stu-id="15023-118">**If you prepaid your plan** There isn't a straightforward upgrade path for prepaid plans.</span></span> <span data-ttu-id="15023-119">È possibile sapere se si dispone di un piano prepagato perché si configura il piano utilizzando un ID prodotto che potrebbe essere stato acquistato in un archivio.</span><span class="sxs-lookup"><span data-stu-id="15023-119">You'll know if you have a prepaid plan because you set up your plan using a product ID that you might have purchased in a store.</span></span> <span data-ttu-id="15023-120">Contattare un partner, accedere a Microsoft Store oppure attendere che il piano prepagato SCADA per passare a un nuovo piano.</span><span class="sxs-lookup"><span data-stu-id="15023-120">Contact a partner, go to the Microsoft Store, or wait until your prepaid plan expires to switch to a new plan.</span></span>

## <a name="upgrade-to-microsoft-365-business-premium"></a><span data-ttu-id="15023-121">Eseguire l'aggiornamento a Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="15023-121">Upgrade to Microsoft 365 Business Premium</span></span>

1. <span data-ttu-id="15023-122">Accedere all'interfaccia di amministrazione all'indirizzo <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> .</span><span class="sxs-lookup"><span data-stu-id="15023-122">Sign into the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="15023-123">Passare al riquadro di spostamento e selezionare **fatturazione** dei \> **prodotti**.</span><span class="sxs-lookup"><span data-stu-id="15023-123">Go to the navigation pane and select **Billing** \> **Your products**.</span></span> <span data-ttu-id="15023-124">Individuare la sottoscrizione corrente e selezionarla per visualizzare i dettagli.</span><span class="sxs-lookup"><span data-stu-id="15023-124">Find your current subscription and select it to view the details.</span></span>

3. <span data-ttu-id="15023-125">Nella pagina successiva, selezionare **Aggiorna**.</span><span class="sxs-lookup"><span data-stu-id="15023-125">On the next page, select **Upgrade**.</span></span>

  > [!NOTE]
  > <span data-ttu-id="15023-126">Se viene visualizzato un messaggio che indica che **l'aggiornamento dell'abbonamento non è supportato con la gestione delle licenze basate su gruppo in Azure Active Directory**, è possibile ignorare questa operazione a meno che non si disponga di un'organizzazione di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="15023-126">If you see a message that says **Upgrading your subscription is not supported with group-based licensing in Azure Active Directory**, you can safely ignore this unless you have a very large organization.</span></span> <span data-ttu-id="15023-127">Le organizzazioni che hanno selezionato questa opzione sapranno di usare le licenze basate su gruppo.</span><span class="sxs-lookup"><span data-stu-id="15023-127">Organizations who have selected this option will be aware that they're using group-based licensing.</span></span>

4. <span data-ttu-id="15023-128">Successivamente, è possibile visualizzare un elenco di piani a cui è possibile eseguire l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="15023-128">Next, you can view a list of plans that you can upgrade to.</span></span> <span data-ttu-id="15023-129">In questo caso, trovare il piano Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="15023-129">In this case, find the Microsoft 365 Business Premium plan.</span></span> <span data-ttu-id="15023-130">È possibile scorrere verso il basso se si desidera visualizzare tutte le app e i servizi inclusi in questo piano.</span><span class="sxs-lookup"><span data-stu-id="15023-130">You can scroll down if you want to see all the apps and services that are included with this plan.</span></span> <span data-ttu-id="15023-131">In **microsoft 365 Business Premium**selezionare **upgrade** per aggiungere Microsoft 365 Business Premium al carrello.</span><span class="sxs-lookup"><span data-stu-id="15023-131">Under **Microsoft 365 Business Premium**, select **Upgrade** to add Microsoft 365 Business Premium to your cart.</span></span>

5. <span data-ttu-id="15023-132">Nel carrello:</span><span class="sxs-lookup"><span data-stu-id="15023-132">In the cart:</span></span>

    1. <span data-ttu-id="15023-133">Verranno incluse automaticamente le licenze per tutti gli utenti correnti.</span><span class="sxs-lookup"><span data-stu-id="15023-133">We'll automatically include licenses for all your current users.</span></span> <span data-ttu-id="15023-134">Se sono necessarie più o meno licenze, è necessario [acquistare e assegnare tali licenze singolarmente](../admin/manage/assign-licenses-to-users.md).</span><span class="sxs-lookup"><span data-stu-id="15023-134">If you need more or fewer licenses, you need to [buy and assign those licenses individually](../admin/manage/assign-licenses-to-users.md).</span></span>  
    2. <span data-ttu-id="15023-135">È possibile modificare la modalità di pagamento: mensile o annuale.</span><span class="sxs-lookup"><span data-stu-id="15023-135">You can adjust how you'd like to pay: monthly or yearly.</span></span> <span data-ttu-id="15023-136">Selezionare il menu a discesa per scegliere.</span><span class="sxs-lookup"><span data-stu-id="15023-136">Select the drop-down menu to make your choice.</span></span>

6. <span data-ttu-id="15023-137">Selezionare **Vai a checkout in** cui verrà visualizzato un riepilogo dell'acquisto, incluso il metodo di pagamento per questo account.</span><span class="sxs-lookup"><span data-stu-id="15023-137">Select **Go to Checkout** where you'll see a summary of your purchase, including the payment method for this account.</span></span> <span data-ttu-id="15023-138">È anche possibile aggiungere un codice promozionale qui se si dispone di uno.</span><span class="sxs-lookup"><span data-stu-id="15023-138">You can also add a promo code here if you have one.</span></span>

7. <span data-ttu-id="15023-139">Selezionare l' **ordine** di esecuzione per completare l'acquisto. </span><span class="sxs-lookup"><span data-stu-id="15023-139">Select **Place order** to complete your purchase.</span></span>\
<span data-ttu-id="15023-140">Microsoft impiega alcuni minuti per configurare i nuovi piani di servizio.</span><span class="sxs-lookup"><span data-stu-id="15023-140">It takes Microsoft a few minutes to set up your new service plans.</span></span> <span data-ttu-id="15023-141">Per verificare lo stato di avanzamento, selezionare **Controlla stato aggiornamento**.</span><span class="sxs-lookup"><span data-stu-id="15023-141">To check on progress, select **Check upgrade status**.</span></span>

8. <span data-ttu-id="15023-142">Quando il piano è pronto, potrebbe essere necessario completare alcuni passaggi di installazione aggiuntivi nell'interfaccia di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="15023-142">When your plan is ready, you might need to complete some additional setup steps in the admin center.</span></span> <span data-ttu-id="15023-143">Nel riquadro di spostamento, selezionare **Home** per completare i passaggi di installazione aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="15023-143">In the navigation pane, select **Home** to complete any additional setup steps.</span></span>

> [!NOTE]
> <span data-ttu-id="15023-144">Si riceverà un rimborso proporzionale per le licenze Microsoft 365 che non è più necessario.</span><span class="sxs-lookup"><span data-stu-id="15023-144">You'll receive a prorated refund for the Microsoft 365 licenses that you no longer need.</span></span> <span data-ttu-id="15023-145">Il conto corrente bancario o la carta di credito viene addebitata circa due giorni dopo la configurazione del nuovo piano.</span><span class="sxs-lookup"><span data-stu-id="15023-145">Your bank account or credit card will be charged about two days after you set up the new plan.</span></span>
  
## <a name="protect-user-devices-and-files"></a><span data-ttu-id="15023-146">Protezione dei dispositivi e dei file utente</span><span class="sxs-lookup"><span data-stu-id="15023-146">Protect user devices and files</span></span>

<span data-ttu-id="15023-147">Ora che sono state assegnate licenze Microsoft 365 Business Premium, completare i passaggi per avviare la protezione di dispositivi e file.</span><span class="sxs-lookup"><span data-stu-id="15023-147">Now that Microsoft 365 Business Premium licenses have been assigned, complete steps to start protecting devices and files.</span></span> <span data-ttu-id="15023-148">Verranno utilizzate alcune nuove opzioni incluse nel riquadro di spostamento dell'interfaccia di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="15023-148">You'll use some new options included in the admin center navigation pane.</span></span>
  
1. <span data-ttu-id="15023-149">Nell'interfaccia di amministrazione, nel riquadro di spostamento, passare ai **Devices** \> **criteri**dei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="15023-149">In the admin center, in the navigation pane, go to **Devices** \> **Policies**.</span></span>

2. <span data-ttu-id="15023-150">Nella pagina **Criteri dispositivo** selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="15023-150">On the **Device policies** page, select **Add**.</span></span>

3. <span data-ttu-id="15023-151">Nel riquadro **Aggiungi criterio** assegnare un nome al criterio (ad esempio, proteggere i file di lavoro) e quindi scegliere un **tipo di criterio** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="15023-151">In the **Add policy** pane give the policy a name (for example, Protect work files), and then choose a **Policy type** from the drop-down list.</span></span>

    <span data-ttu-id="15023-152">È possibile configurare i criteri di applicazione per la protezione dei file su dispositivi Android e iPhone, oltre a Windows 10, ed è possibile configurare i criteri di configurazione del dispositivo per i dispositivi Windows 10 di proprietà dell'azienda.</span><span class="sxs-lookup"><span data-stu-id="15023-152">You can set up application policies for protecting files on Android and iPhone devices, as well as Windows 10, and you can set up device configuration policies for company owned Windows 10 devices.</span></span> <span data-ttu-id="15023-153">Per informazioni dettagliate, vedere i seguenti collegamenti:</span><span class="sxs-lookup"><span data-stu-id="15023-153">See the following links for details:</span></span>

    - [<span data-ttu-id="15023-154">Configurare le impostazioni di protezione delle app per i dispositivi Android o iOS</span><span class="sxs-lookup"><span data-stu-id="15023-154">Set app protection settings for Android or iOS devices</span></span>](app-protection-settings-for-android-and-ios.md)

    - [<span data-ttu-id="15023-155">Configurare le impostazioni di protezione delle app per i dispositivi Windows 10</span><span class="sxs-lookup"><span data-stu-id="15023-155">Set application protection settings for Windows 10 devices</span></span>](protection-settings-for-windows-10-devices.md)

    - [<span data-ttu-id="15023-156">Impostazione delle impostazioni di protezione dei dispositivi per PC Windows 10</span><span class="sxs-lookup"><span data-stu-id="15023-156">Set device protection settings for Windows 10 PCs</span></span>](protection-settings-for-windows-10-pcs.md)

4. <span data-ttu-id="15023-157">Dopo aver configurato i criteri, gli utenti e i dipendenti possono configurare i dispositivi:</span><span class="sxs-lookup"><span data-stu-id="15023-157">After you set up policies, you and your employees can set up devices:</span></span>

    - <span data-ttu-id="15023-158">Se i dispositivi Windows non utilizzano già l'aggiornamento di Windows Pro Creator, è necessario aggiornarli [a Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span><span class="sxs-lookup"><span data-stu-id="15023-158">If your Windows devices aren't already using the Windows Pro Creator update, you'll need to [upgrade them to Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span></span>

    - <span data-ttu-id="15023-159">Per i dispositivi Windows, vedere [configurare i dispositivi Windows per gli utenti di Microsoft 365 Business Premium](set-up-windows-devices.md) .</span><span class="sxs-lookup"><span data-stu-id="15023-159">See [Set up Windows devices for Microsoft 365 Business Premium users](set-up-windows-devices.md) for steps for Windows devices.</span></span>

    - <span data-ttu-id="15023-160">Per i passaggi per telefoni Android e iPhone, vedere [configurare i dispositivi mobili per gli utenti di Microsoft 365 Business Premium](set-up-mobile-devices.md) .</span><span class="sxs-lookup"><span data-stu-id="15023-160">See [Set up mobile devices for Microsoft 365 Business Premium users](set-up-mobile-devices.md) for steps for Android phones and iPhones.</span></span>