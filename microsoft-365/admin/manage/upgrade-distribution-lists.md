---
title: Aggiornare le liste di distribuzione ai gruppi di Microsoft 365 in Outlook
f1.keywords:
- NOCSH
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
ms.assetid: 787d7a75-e201-46f3-a242-f698162ff09f
description: Informazioni su come eseguire l'aggiornamento di una o più liste di distribuzione ai gruppi di Microsoft 365 in Outlook e sull'utilizzo di PowerShell per l'aggiornamento simultaneo di più liste di distribuzione.
ms.openlocfilehash: f5748c293d18943c94c3610c0e3c5c33848eb521
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780026"
---
# <a name="upgrade-distribution-lists-to-microsoft-365-groups-in-outlook"></a><span data-ttu-id="e588b-103">Aggiornare le liste di distribuzione ai gruppi di Microsoft 365 in Outlook</span><span class="sxs-lookup"><span data-stu-id="e588b-103">Upgrade distribution lists to Microsoft 365 Groups in Outlook</span></span>

<span data-ttu-id="e588b-104">È possibile aggiornare le liste di distribuzione ai gruppi di Microsoft 365 con Outlook.</span><span class="sxs-lookup"><span data-stu-id="e588b-104">You can upgrade distribution lists to Microsoft 365 Groups with Outlook.</span></span> <span data-ttu-id="e588b-105">Questo è un ottimo modo per fornire alle liste di distribuzione dell'organizzazione tutte le caratteristiche e le funzionalità dei gruppi di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e588b-105">This is a great way to give your organization's distribution lists all the features and functionality of Microsoft 365 Groups.</span></span> [<span data-ttu-id="e588b-106">Perché è consigliabile eseguire l'aggiornamento delle liste di distribuzione ai gruppi di Outlook</span><span class="sxs-lookup"><span data-stu-id="e588b-106">Why you should upgrade your distribution lists to groups in Outlook</span></span>](https://support.microsoft.com/office/7fb3d880-593b-4909-aafa-950dd50ce188)

<span data-ttu-id="e588b-107">È possibile aggiornare le liste di distribuzione una per volta oppure diverse contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="e588b-107">You can upgrade DLs one at a time, or several at the same time.</span></span>

## <a name="upgrade-one-or-many-distribution-lists-to-microsoft-365-groups-in-outlook"></a><span data-ttu-id="e588b-108">Aggiornare una o più liste di distribuzione ai gruppi di Microsoft 365 in Outlook</span><span class="sxs-lookup"><span data-stu-id="e588b-108">Upgrade one or many distribution lists to Microsoft 365 Groups in Outlook</span></span>

<span data-ttu-id="e588b-109">Per aggiornare una lista di distribuzione, è necessario essere un amministratore globale o un amministratore di Exchange.</span><span class="sxs-lookup"><span data-stu-id="e588b-109">You must be a global admin or Exchange admin to upgrade a distribution list.</span></span> <span data-ttu-id="e588b-110">Per eseguire l'aggiornamento ai gruppi di Microsoft 365, un gruppo di distribuzione deve disporre di un proprietario con una cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="e588b-110">To upgrade to Microsoft 365 Groups, a distribution group must have an owner with a mailbox.</span></span> 

1. <span data-ttu-id="e588b-111">Accedere all'<a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">interfaccia di amministrazione di Exchange</a>.</span><span class="sxs-lookup"><span data-stu-id="e588b-111">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>

2. <span data-ttu-id="e588b-112">Nell'interfaccia di amministrazione di Exchange, accedere a gruppi di **destinatari** \> **Groups**.</span><span class="sxs-lookup"><span data-stu-id="e588b-112">In the Exchange admin center, go to **Recipients** \> **Groups**.</span></span><br/><span data-ttu-id="e588b-113">Verrà visualizzato un avviso che indica che sono presenti liste di distribuzione (denominate anche **gruppi di distribuzione** ) idonee per l'aggiornamento ai gruppi di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e588b-113">You'll see a notice indicating you have distribution lists (also called **distribution groups** ) that are eligible to be upgraded to Microsoft 365 Groups.</span></span><br/> <span data-ttu-id="e588b-114">![Selezionare il pulsante inizia](../../media/8cf838b4-2644-401f-a366-08c1eea183eb.png)</span><span class="sxs-lookup"><span data-stu-id="e588b-114">![Select the Get started button](../../media/8cf838b4-2644-401f-a366-08c1eea183eb.png)</span></span>

3. <span data-ttu-id="e588b-115">Selezionare una o più liste di distribuzione (chiamate anche **gruppo di distribuzione** ) nella pagina **Gruppi**.</span><span class="sxs-lookup"><span data-stu-id="e588b-115">Select one or more distribution lists (also called a **distribution group** ) from the **groups** page.</span></span><br/><span data-ttu-id="e588b-116">![Selezionare un gruppo di distribuzione](../../media/2c303433-d60b-4100-a6ae-5809b03a8cdb.png)</span><span class="sxs-lookup"><span data-stu-id="e588b-116">![Select a distribution group](../../media/2c303433-d60b-4100-a6ae-5809b03a8cdb.png)</span></span>

4. <span data-ttu-id="e588b-117">Selezionare l'icona di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="e588b-117">Select the upgrade icon.</span></span><br/>![Icona aggiornamento a Microsoft 365 gruppi](../../media/1e28cb3d-bff3-4be3-8329-1902d2d54720.png)

5. <span data-ttu-id="e588b-119">Nella finestra di dialogo informazioni selezionare **Sì** per confermare l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="e588b-119">On the information dialog, select **Yes** to confirm the upgrade.</span></span> <span data-ttu-id="e588b-120">Il processo inizia immediatamente.</span><span class="sxs-lookup"><span data-stu-id="e588b-120">The process begins immediately.</span></span> <span data-ttu-id="e588b-121">A seconda delle dimensioni e del numero di DLs che si sta aggiornando, il processo può richiedere minuti o ore.</span><span class="sxs-lookup"><span data-stu-id="e588b-121">Depending on the size and number of DLs you're upgrading, the process can take minutes or hours.</span></span><br/><span data-ttu-id="e588b-122">Se la lista di distribuzione non può essere aggiornata, viene visualizzata una finestra di dialogo che indica questo problema.</span><span class="sxs-lookup"><span data-stu-id="e588b-122">If the distribution list can't be upgraded, a dialog appears saying so.</span></span> <span data-ttu-id="e588b-123">Visualizzare le [liste di distribuzione che non possono essere aggiornate](#which-distribution-lists-cannot-be-upgraded).</span><span class="sxs-lookup"><span data-stu-id="e588b-123">See [Which distribution lists cannot be upgraded?](#which-distribution-lists-cannot-be-upgraded).</span></span>

6. <span data-ttu-id="e588b-124">Se si esegue l'aggiornamento di più liste di distribuzione, utilizzare l'elenco a discesa per filtrare le liste di distribuzione che sono state aggiornate.</span><span class="sxs-lookup"><span data-stu-id="e588b-124">If you're upgrading multiple distribution lists, use the drop-down list to filter which distribution lists have been upgraded.</span></span> <span data-ttu-id="e588b-125">Se l'elenco non è completo, attendere un po' di tempo e quindi selezionare **Aggiorna** per vedere cosa è stato aggiornato correttamente.</span><span class="sxs-lookup"><span data-stu-id="e588b-125">If the list isn't complete, wait a while longer and then select **Refresh** to see what's been successfully upgraded.</span></span><br/><span data-ttu-id="e588b-126">There's no notice that tells you when the upgrade process has completed for all DLs you selected.</span><span class="sxs-lookup"><span data-stu-id="e588b-126">There's no notice that tells you when the upgrade process has completed for all DLs you selected.</span></span> <span data-ttu-id="e588b-127">You can figure this out by looking to see what's listed under **Available for upgrade** or **Upgraded DLs**.</span><span class="sxs-lookup"><span data-stu-id="e588b-127">You can figure this out by looking to see what's listed under **Available for upgrade** or **Upgraded DLs**.</span></span>

7. <span data-ttu-id="e588b-128">If you selected a DL for upgrade, but it's still appears on the page as Available to upgrade, then it failed to upgrade.</span><span class="sxs-lookup"><span data-stu-id="e588b-128">If you selected a DL for upgrade, but it's still appears on the page as Available to upgrade, then it failed to upgrade.</span></span> <span data-ttu-id="e588b-129">See [What to do if the upgrade doesn't work](#what-to-do-if-the-upgrade-doesnt-work).</span><span class="sxs-lookup"><span data-stu-id="e588b-129">See [What to do if the upgrade doesn't work](#what-to-do-if-the-upgrade-doesnt-work).</span></span>

> [!NOTE]
> <span data-ttu-id="e588b-130">If you're getting the groups digest emails you may notice at the bottom that it will sometimes offer to let you upgrade any eligible distribution lists that you're the owner of.</span><span class="sxs-lookup"><span data-stu-id="e588b-130">If you're getting the groups digest emails you may notice at the bottom that it will sometimes offer to let you upgrade any eligible distribution lists that you're the owner of.</span></span> <span data-ttu-id="e588b-131">See [Have a group conversation in Outlook](https://support.microsoft.com/office/a0482e24-a769-4e39-a5ba-a7c56e828b22) for more information about digest emails.</span><span class="sxs-lookup"><span data-stu-id="e588b-131">See [Have a group conversation in Outlook](https://support.microsoft.com/office/a0482e24-a769-4e39-a5ba-a7c56e828b22) for more information about digest emails.</span></span>


## <a name="what-to-do-if-the-upgrade-doesnt-work"></a><span data-ttu-id="e588b-132">Che cosa fare se l'aggiornamento non riesce</span><span class="sxs-lookup"><span data-stu-id="e588b-132">What to do if the upgrade doesn't work</span></span>

<span data-ttu-id="e588b-133">Le liste di distribuzione il cui aggiornamento non riesce restano inalterate.</span><span class="sxs-lookup"><span data-stu-id="e588b-133">Distribution lists that fail to upgrade remain unchanged.</span></span>

<span data-ttu-id="e588b-134">If one or more **eligible** distribution lists fail to be upgraded, open a [Support ticket](../contact-support-for-business-products.md).</span><span class="sxs-lookup"><span data-stu-id="e588b-134">If one or more **eligible** distribution lists fail to be upgraded, open a [Support ticket](../contact-support-for-business-products.md).</span></span> <span data-ttu-id="e588b-135">The issue will need to be escalated to the Groups Engineering team for them to figure out the problem.</span><span class="sxs-lookup"><span data-stu-id="e588b-135">The issue will need to be escalated to the Groups Engineering team for them to figure out the problem.</span></span>

<span data-ttu-id="e588b-136">It's possible that the distribution list didn't get upgraded because of a service outage, but pretty unlikely.</span><span class="sxs-lookup"><span data-stu-id="e588b-136">It's possible that the distribution list didn't get upgraded because of a service outage, but pretty unlikely.</span></span> <span data-ttu-id="e588b-137">If you want, wait a while and then try to upgrade the DL again.</span><span class="sxs-lookup"><span data-stu-id="e588b-137">If you want, wait a while and then try to upgrade the DL again.</span></span>

## <a name="how-to-use-powershell-to-upgrade-several-distribution-lists-at-the-same-time"></a><span data-ttu-id="e588b-138">Come usare PowerShell per aggiornare diverse liste di distribuzione contemporaneamente</span><span class="sxs-lookup"><span data-stu-id="e588b-138">How to use PowerShell to upgrade several distribution lists at the same time</span></span>

<span data-ttu-id="e588b-139">Se si ha esperienza nell'uso di PowerShell, potrebbe essere utile scegliere questo strumento invece dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="e588b-139">If you're experienced at using PowerShell, you might want to go this route instead of using the UI.</span></span> <span data-ttu-id="e588b-140">È presente un insieme di cmdlet che consentono di aggiornare le liste di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="e588b-140">We have a set of cmdlets that will help you upgrade distribution lists.</span></span> <span data-ttu-id="e588b-141">Vedere di seguito.</span><span class="sxs-lookup"><span data-stu-id="e588b-141">See below.</span></span>

### <a name="upgrade-a-single-dl"></a><span data-ttu-id="e588b-142">Aggiornare un singolo DL</span><span class="sxs-lookup"><span data-stu-id="e588b-142">Upgrade a single DL</span></span>

<span data-ttu-id="e588b-143">Per aggiornare un singolo DL, eseguire il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="e588b-143">To upgrade a single DL run the following command:</span></span>

`Upgrade-DistributionGroup -DlIdentities \<Dl SMTP address\>`

<span data-ttu-id="e588b-144">Ad esempio, se si desidera aggiornare un DLs con l'indirizzo SMTP dl1@contoso.com, eseguire il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="e588b-144">For example, if you want to upgrade a DLs with SMTP address dl1@contoso.com, run the following command:</span></span>

`Upgrade-DistributionGroup -DlIdentities dl1@contoso.com`

> [!NOTE]
> <span data-ttu-id="e588b-145">È inoltre possibile aggiornare una singola lista di distribuzione a un gruppo di Microsoft 365 utilizzando il cmdlet [New-UnifiedGroup](https://go.microsoft.com/fwlink/?LinkID=786379) di PowerShell</span><span class="sxs-lookup"><span data-stu-id="e588b-145">You can also upgrade a single distribution list to a Microsoft 365 group using the [New-UnifiedGroup](https://go.microsoft.com/fwlink/?LinkID=786379) PowerShell cmdlet</span></span>

### <a name="upgrade-multiple-dls-in-a-batch"></a><span data-ttu-id="e588b-146">Aggiornare più DLs in un batch</span><span class="sxs-lookup"><span data-stu-id="e588b-146">Upgrade multiple DLs in a batch</span></span>

<span data-ttu-id="e588b-147">È inoltre possibile passare più DLs come batch e aggiornarli insieme:</span><span class="sxs-lookup"><span data-stu-id="e588b-147">You can also pass multiple DLs as a batch and upgrade them together:</span></span>

```
Upgrade-DistributionGroup -DlIdentities \<DL SMTP address1\>, \< DL SMTP address2\>,

\< DL SMTP address3\>, \< DL SMTP address 4\>
```

<span data-ttu-id="e588b-148">Ad esempio, se si desidera aggiornare cinque DLS con indirizzo SMTP `dl1@contoso.com` e, `dl2@contoso.com` e `dl3@contoso.com` , `dl4@contoso.com` `dl5@contoso.com` eseguire il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="e588b-148">For example, if you want to upgrade five DLs with SMTP address `dl1@contoso.com` and `dl2@contoso.com`, `dl3@contoso.com`, `dl4@contoso.com` and `dl5@contoso.com`, run the following command:</span></span>

`Upgrade-DistributionGroup -DlIdentities dl1@contoso.com, dl2@contoso.com, dl3@contoso.com, dl4@contoso.com, dl5@contoso.com`

### <a name="upgrade-all-eligible-dls"></a><span data-ttu-id="e588b-149">Aggiornare tutti i DLs idonei</span><span class="sxs-lookup"><span data-stu-id="e588b-149">Upgrade all eligible DLs</span></span>

<span data-ttu-id="e588b-150">Esistono due modi in cui è possibile aggiornare tutti i DLs idonei.</span><span class="sxs-lookup"><span data-stu-id="e588b-150">There are two ways in which you can upgrade all the eligible DLs.</span></span>

> [!NOTE]
> <span data-ttu-id="e588b-151">Il cmdlet Upgrade-DistributionGroup non riceve i dati dalla pipeline, per questo motivo è necessario utilizzare l'operatore "foreach-Object {} " per eseguire correttamente.</span><span class="sxs-lookup"><span data-stu-id="e588b-151">The Upgrade-DistributionGroup cmdlet doesn't receive data from the pipeline, for this reason it's required to use "foreach-object{}" operator to run successfully.</span></span>

1. <span data-ttu-id="e588b-152">Ottenere il DLs idoneo nel tenant e aggiornarlo utilizzando il comando di aggiornamento:</span><span class="sxs-lookup"><span data-stu-id="e588b-152">Get the eligible DLs in the tenant and upgrade them using the upgrade command:</span></span>

```
Get-EligibleDistributionGroupForMigration | Foreach-Object{
    Upgrade-DistributionGroup -DlIdentities $_.PrimarySMTPAddress
}
```

2. <span data-ttu-id="e588b-153">Ottenere l'elenco di tutti i DLs e aggiornare solo il DLs idoneo:</span><span class="sxs-lookup"><span data-stu-id="e588b-153">Get the list of all DLs and upgrade only the eligible DLs:</span></span>

```
Get-DistributionGroup| Foreach-Object{
    Upgrade-DistributionGroup -DlIdentities $_.PrimarySMTPAddress
}
```

## <a name="faq-about-upgrading-distribution-lists-to-microsoft-365-groups-in-outlook"></a><span data-ttu-id="e588b-154">Domande frequenti sull'aggiornamento delle liste di distribuzione ai gruppi di Microsoft 365 in Outlook</span><span class="sxs-lookup"><span data-stu-id="e588b-154">FAQ about upgrading distribution lists to Microsoft 365 Groups in Outlook</span></span>

### <a name="which-distribution-lists-cannot-be-upgraded"></a><span data-ttu-id="e588b-155">Quali sono le liste di distribuzione che non è possibile aggiornare?</span><span class="sxs-lookup"><span data-stu-id="e588b-155">Which distribution lists cannot be upgraded?</span></span>

<span data-ttu-id="e588b-156">È possibile aggiornare solo liste di distribuzione semplici, gestite nel cloud e non annidate.</span><span class="sxs-lookup"><span data-stu-id="e588b-156">You can only upgrade cloud-managed, simple, non-nested distribution lists.</span></span> <span data-ttu-id="e588b-157">Nella tabella seguente sono elencate le liste di distribuzione che **non possono** essere aggiornate.</span><span class="sxs-lookup"><span data-stu-id="e588b-157">The table below lists distribution lists that **CANNOT** be upgraded.</span></span>

|<span data-ttu-id="e588b-158">**Proprietà**</span><span class="sxs-lookup"><span data-stu-id="e588b-158">**Property**</span></span>|<span data-ttu-id="e588b-159">**Idonea?**</span><span class="sxs-lookup"><span data-stu-id="e588b-159">**Eligible?**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e588b-160">Lista di distribuzione gestita in locale</span><span class="sxs-lookup"><span data-stu-id="e588b-160">On-premises managed distribution list.</span></span>  <br/> |<span data-ttu-id="e588b-161">No</span><span class="sxs-lookup"><span data-stu-id="e588b-161">No</span></span>  <br/> |
|<span data-ttu-id="e588b-162">Nested distribution lists.</span><span class="sxs-lookup"><span data-stu-id="e588b-162">Nested distribution lists.</span></span> <span data-ttu-id="e588b-163">Distribution list either has child groups or is a member of another group.</span><span class="sxs-lookup"><span data-stu-id="e588b-163">Distribution list either has child groups or is a member of another group.</span></span>  <br/> |<span data-ttu-id="e588b-164">No</span><span class="sxs-lookup"><span data-stu-id="e588b-164">No</span></span>  <br/> |
|<span data-ttu-id="e588b-165">Liste di distribuzione con **RecipientTypeDetails** membri diverse da **UserMailbox**, **SharedMailbox**, **TeamMailbox**, **MailUser**</span><span class="sxs-lookup"><span data-stu-id="e588b-165">Distribution lists with member **RecipientTypeDetails** other than **UserMailbox**, **SharedMailbox**, **TeamMailbox**, **MailUser**</span></span>  <br/> |<span data-ttu-id="e588b-166">No</span><span class="sxs-lookup"><span data-stu-id="e588b-166">No</span></span>  <br/> |
|<span data-ttu-id="e588b-167">Lista di distribuzione che ha più di 100 proprietari</span><span class="sxs-lookup"><span data-stu-id="e588b-167">Distribution list which has more than 100 owners</span></span>  <br/> |<span data-ttu-id="e588b-168">No</span><span class="sxs-lookup"><span data-stu-id="e588b-168">No</span></span>  <br/> |
|<span data-ttu-id="e588b-169">Lista di distribuzione che ha solo membri, ma nessun proprietario</span><span class="sxs-lookup"><span data-stu-id="e588b-169">Distribution list which only has members but no owner</span></span>  <br/> |<span data-ttu-id="e588b-170">No</span><span class="sxs-lookup"><span data-stu-id="e588b-170">No</span></span>  <br/> |
|<span data-ttu-id="e588b-171">Lista di distribuzione che ha un alias contenente caratteri speciali</span><span class="sxs-lookup"><span data-stu-id="e588b-171">Distribution list which has alias containing special characters</span></span>  <br/> |<span data-ttu-id="e588b-172">No</span><span class="sxs-lookup"><span data-stu-id="e588b-172">No</span></span>  <br/> |
|<span data-ttu-id="e588b-173">Lista di distribuzione configurata come indirizzo di inoltro per la cassetta postale condivisa</span><span class="sxs-lookup"><span data-stu-id="e588b-173">If the distribution list is configured to be a forwarding address for Shared Mailbox</span></span>  <br/> |<span data-ttu-id="e588b-174">No</span><span class="sxs-lookup"><span data-stu-id="e588b-174">No</span></span>  <br/> |
|<span data-ttu-id="e588b-175">Se il DL fa parte della **restrizione del mittente** in un altro DL.</span><span class="sxs-lookup"><span data-stu-id="e588b-175">If the DL is part of **Sender Restriction** in another DL.</span></span>  <br/> |<span data-ttu-id="e588b-176">No</span><span class="sxs-lookup"><span data-stu-id="e588b-176">No</span></span>  <br/> |
|<span data-ttu-id="e588b-177">Gruppi di sicurezza</span><span class="sxs-lookup"><span data-stu-id="e588b-177">Security groups</span></span>  <br/> |<span data-ttu-id="e588b-178">No</span><span class="sxs-lookup"><span data-stu-id="e588b-178">No</span></span>  <br/> |
|<span data-ttu-id="e588b-179">Liste di distribuzione dinamiche</span><span class="sxs-lookup"><span data-stu-id="e588b-179">Dynamic Distribution lists</span></span>  <br/> |<span data-ttu-id="e588b-180">No</span><span class="sxs-lookup"><span data-stu-id="e588b-180">No</span></span>  <br/> |
|<span data-ttu-id="e588b-181">Liste di distribuzione che sono state convertite in **RoomLists**</span><span class="sxs-lookup"><span data-stu-id="e588b-181">Distribution lists which were converted to **RoomLists**</span></span>  <br/> |<span data-ttu-id="e588b-182">No</span><span class="sxs-lookup"><span data-stu-id="e588b-182">No</span></span>  <br/> |
|<span data-ttu-id="e588b-183">Liste di distribuzione in cui **MemberJoinRestriction** e/o **MemberDepartRestriction** è **chiuso**</span><span class="sxs-lookup"><span data-stu-id="e588b-183">Distribution lists where **MemberJoinRestriction** and/or **MemberDepartRestriction** is **Closed**</span></span>  <br/> |<span data-ttu-id="e588b-184">No</span><span class="sxs-lookup"><span data-stu-id="e588b-184">No</span></span>  <br/> |

### <a name="how-do-i-check-which-dls-are-eligible-for-upgrade"></a><span data-ttu-id="e588b-185">Come si verifica quale DLs è idoneo per l'aggiornamento?</span><span class="sxs-lookup"><span data-stu-id="e588b-185">How do I check which DLs are eligible for upgrade?</span></span>

<span data-ttu-id="e588b-186">Se si desidera verificare se un DL è idoneo o meno, è possibile eseguire il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="e588b-186">If you want to check whether a DL is eligible or not, you can run the below command:</span></span>

`Get-DistributionGroup \<DL SMTP address\> | Get-EligibleDistributionGroupForMigration`

<span data-ttu-id="e588b-187">Se si desidera verificare quali DLs sono idonei per l'aggiornamento, eseguire il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="e588b-187">If you want to check which DLs are eligible for upgrade just run the following command:</span></span>

`Get-EligibleDistributionGroupForMigration`

### <a name="who-can-run-the-upgrade-scripts"></a><span data-ttu-id="e588b-188">Chi può eseguire gli script di aggiornamento?</span><span class="sxs-lookup"><span data-stu-id="e588b-188">Who can run the upgrade scripts?</span></span>

<span data-ttu-id="e588b-189">Utenti con diritti di amministratore globale o di amministrazione di Exchange.</span><span class="sxs-lookup"><span data-stu-id="e588b-189">People with global admin or Exchange admin rights.</span></span>

### <a name="why-is-the-contact-card-still-showing-a-distribution-list-what-should-i-do-to-prevent-a-upgraded-distribution-list-from-showing-up-in-my-auto-suggest-list"></a><span data-ttu-id="e588b-190">Perché la scheda contatto mostra ancora una lista di distribuzione?</span><span class="sxs-lookup"><span data-stu-id="e588b-190">Why is the contact card still showing a distribution list?</span></span> <span data-ttu-id="e588b-191">Come si impedisce la visualizzazione di una lista di distribuzione aggiornata nell'elenco dei suggerimenti automatici?</span><span class="sxs-lookup"><span data-stu-id="e588b-191">What should I do to prevent a upgraded distribution list from showing up in my auto suggest list?</span></span>

- <span data-ttu-id="e588b-192">Per Outlook: quando un utente tenta di inviare un messaggio di posta elettronica in Outlook digitando il nome del gruppo Microsoft 365 dopo la migrazione, il destinatario viene risolto come la lista di distribuzione invece del gruppo.</span><span class="sxs-lookup"><span data-stu-id="e588b-192">For Outlook: When someone tries to send an email in Outlook by typing the Microsoft 365 group name after migration, the recipient will be resolved as the distribution list instead of the group.</span></span> <span data-ttu-id="e588b-193">La scheda contatto del destinatario sarà la scheda contatto degli elenchi di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="e588b-193">The contact card of the recipient will be the distribution lists contact card.</span></span> <span data-ttu-id="e588b-194">Questo dipende dalla cache dei destinatari o dalla cache dei nomi alternativi in Outlook.</span><span class="sxs-lookup"><span data-stu-id="e588b-194">This is because of the recipient cache or nick name cache in Outlook.</span></span> <span data-ttu-id="e588b-195">Il messaggio di posta elettronica verrà inviato correttamente al gruppo, ma potrebbe creare confusione per il mittente.</span><span class="sxs-lookup"><span data-stu-id="e588b-195">The email will be sent successfully to the group, but might cause confusion to the sender.</span></span><br/><span data-ttu-id="e588b-196">È possibile eseguire i passaggi descritti in questo argomento, [Informazioni relative all'elenco di completamento automatico di Outlook](https://go.microsoft.com/fwlink/?LinkID=798736) per reimpostare la cache e risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="e588b-196">You can perform the steps in this topic, [Information about the Outlook AutoComplete list](https://go.microsoft.com/fwlink/?LinkID=798736) to reset the cache, which will fix this issue.</span></span>

- <span data-ttu-id="e588b-197">Per Outlook sul Web: in caso di Outlook sul Web, il destinatario della lista di distribuzione rimarrà ancora nella cache.</span><span class="sxs-lookup"><span data-stu-id="e588b-197">For Outlook on the web: In case of Outlook on the web, the distribution list recipient will still remain in the cache.</span></span> <span data-ttu-id="e588b-198">È possibile seguire la procedura descritta in [rimuovere il nome o l'indirizzo di posta elettronica suggerito dall'elenco di completamento automatico](https://support.microsoft.com/office/9E1419D9-E88F-445B-B07F-F558B8A37C58) per aggiornare la cache per visualizzare la scheda contatto di gruppo.</span><span class="sxs-lookup"><span data-stu-id="e588b-198">You can follow the steps in [Remove suggested name or email address from the Auto-Complete List](https://support.microsoft.com/office/9E1419D9-E88F-445B-B07F-F558B8A37C58) to refresh the cache to see the group contact card.</span></span>

### <a name="do-new-group-members-get-a-welcome-email-in-their-inbox"></a><span data-ttu-id="e588b-199">I nuovi membri del gruppo ricevono un messaggio di posta elettronica di benvenuto nella propria posta in arrivo?</span><span class="sxs-lookup"><span data-stu-id="e588b-199">Do new group members get a welcome email in their inbox?</span></span>

<span data-ttu-id="e588b-200">No.</span><span class="sxs-lookup"><span data-stu-id="e588b-200">No.</span></span> <span data-ttu-id="e588b-201">The setting to enable welcome messages is set to false by default.</span><span class="sxs-lookup"><span data-stu-id="e588b-201">The setting to enable welcome messages is set to false by default.</span></span> <span data-ttu-id="e588b-202">This setting affects both existing and new group members who may join after the migration is complete.</span><span class="sxs-lookup"><span data-stu-id="e588b-202">This setting affects both existing and new group members who may join after the migration is complete.</span></span> <span data-ttu-id="e588b-203">If the group owner later allows guest users, guest users won't receive a welcome email in their inbox.</span><span class="sxs-lookup"><span data-stu-id="e588b-203">If the group owner later allows guest users, guest users won't receive a welcome email in their inbox.</span></span> <span data-ttu-id="e588b-204">Guest members can continue working with the group.</span><span class="sxs-lookup"><span data-stu-id="e588b-204">Guest members can continue working with the group.</span></span>

### <a name="what-if-one-or-some-of-the-dls-are-not-upgraded"></a><span data-ttu-id="e588b-205">Cosa succede se uno o più dei DLs non vengono aggiornati?</span><span class="sxs-lookup"><span data-stu-id="e588b-205">What if one or some of the DLs are not upgraded?</span></span>

<span data-ttu-id="e588b-206">Esistono alcuni casi in cui se DL è idoneo ma non è stato possibile aggiornarlo.</span><span class="sxs-lookup"><span data-stu-id="e588b-206">There are some cases in which though DL is eligible but could not be upgraded.</span></span> <span data-ttu-id="e588b-207">Il DL non viene aggiornato e rimane come un DL.</span><span class="sxs-lookup"><span data-stu-id="e588b-207">The DL does not get upgraded and remains as a DL.</span></span>

- <span data-ttu-id="e588b-208">Dove admin ha applicato il **criterio degli indirizzi di posta elettronica del gruppo** per i gruppi in un'organizzazione e tentano di aggiornare DLS che non soddisfa i criteri, il DL non viene aggiornato</span><span class="sxs-lookup"><span data-stu-id="e588b-208">Where admin has applied **Group Email Address Policy** for the groups in an organization and they try to upgrade DLs which doesn't fulfill the criteria, the DL does not get upgraded</span></span>

- <span data-ttu-id="e588b-209">DLs con **MemberJoinRestriction** o **MemberDepartRestriction** impostato su **chiuso**, non è stato possibile aggiornare</span><span class="sxs-lookup"><span data-stu-id="e588b-209">DLs with **MemberJoinRestriction** or **MemberDepartRestriction** set to **Closed**, could not be upgraded</span></span>

### <a name="what-happens-to-the-dl-if-the-upgrade-from-eac-fails"></a><span data-ttu-id="e588b-210">Che cosa succede alla lista di distribuzione se l'aggiornamento dall'interfaccia di amministrazione di Exchange non riesce?</span><span class="sxs-lookup"><span data-stu-id="e588b-210">What happens to the DL if the upgrade from EAC fails?</span></span>

<span data-ttu-id="e588b-211">The upgrade will happen only when the call is submitted to the server.</span><span class="sxs-lookup"><span data-stu-id="e588b-211">The upgrade will happen only when the call is submitted to the server.</span></span> <span data-ttu-id="e588b-212">If the upgrade fails, your DLs will be intact.</span><span class="sxs-lookup"><span data-stu-id="e588b-212">If the upgrade fails, your DLs will be intact.</span></span> <span data-ttu-id="e588b-213">They will work like they used to.</span><span class="sxs-lookup"><span data-stu-id="e588b-213">They will work like they used to.</span></span>


