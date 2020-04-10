---
title: Aggiornare le liste di distribuzione a Gruppi di Office 365 in Outlook
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 787d7a75-e201-46f3-a242-f698162ff09f
description: Informazioni su come eseguire l'aggiornamento di una o più liste di distribuzione a gruppi di Office 365 in Outlook e sull'utilizzo di PowerShell per aggiornare contemporaneamente diverse liste di distribuzione.
ms.openlocfilehash: c3acf1d47a37d79d666b1b951bea704c273ccf09
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2020
ms.locfileid: "43212282"
---
# <a name="upgrade-distribution-lists-to-office-365-groups-in-outlook"></a><span data-ttu-id="cc1f5-103">Aggiornare le liste di distribuzione a Gruppi di Office 365 in Outlook</span><span class="sxs-lookup"><span data-stu-id="cc1f5-103">Upgrade distribution lists to Office 365 Groups in Outlook</span></span>

<span data-ttu-id="cc1f5-104">È possibile aggiornare le liste di distribuzione a gruppi di Office 365 con Outlook.</span><span class="sxs-lookup"><span data-stu-id="cc1f5-104">You can upgrade distribution lists to Office 365 Groups with Outlook.</span></span> <span data-ttu-id="cc1f5-105">Si tratta di un ottimo metodo per aggiungere alle liste di distribuzione tutte le caratteristiche e funzionalità dei gruppi di Office 365.</span><span class="sxs-lookup"><span data-stu-id="cc1f5-105">This is a great way to give your organization's distribution lists all the features and functionality of Office 365 groups.</span></span> [<span data-ttu-id="cc1f5-106">Perché è consigliabile eseguire l'aggiornamento delle liste di distribuzione ai gruppi di Outlook</span><span class="sxs-lookup"><span data-stu-id="cc1f5-106">Why you should upgrade your distribution lists to groups in Outlook</span></span>](https://support.office.com/article/7fb3d880-593b-4909-aafa-950dd50ce188.aspx)

<span data-ttu-id="cc1f5-107">È possibile aggiornare le liste di distribuzione una per volta oppure diverse contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="cc1f5-107">You can upgrade DLs one at a time, or several at the same time.</span></span>

## <a name="upgrade-one-or-many-distribution-lists-to-office-365-groups-in-outlook"></a><span data-ttu-id="cc1f5-108">Aggiornare una o più liste di distribuzione a Gruppi di Office 365 in Outlook</span><span class="sxs-lookup"><span data-stu-id="cc1f5-108">Upgrade one or many distribution lists to Office 365 Groups in Outlook</span></span>

<span data-ttu-id="cc1f5-109">Per aggiornare una lista di distribuzione, è necessario essere un amministratore globale di Office 365 o un amministratore di Exchange.</span><span class="sxs-lookup"><span data-stu-id="cc1f5-109">You must be an Office 365 global admin or Exchange admin to upgrade a distribution list.</span></span> <span data-ttu-id="cc1f5-110">Per eseguire l'aggiornamento a gruppi di Office 365, un gruppo di distribuzione deve disporre di un proprietario con una cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="cc1f5-110">To upgrade to Office 365 groups, a distribution group must have an owner with a mailbox.</span></span> 

1. <span data-ttu-id="cc1f5-111">Accedere all'<a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">interfaccia di amministrazione di Exchange</a>.</span><span class="sxs-lookup"><span data-stu-id="cc1f5-111">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>

2. <span data-ttu-id="cc1f5-112">Nell'interfaccia di amministrazione di Exchange, accedere a **gruppi**di **destinatari** \> .</span><span class="sxs-lookup"><span data-stu-id="cc1f5-112">In the Exchange admin center, go to **Recipients** \> **Groups**.</span></span><br/><span data-ttu-id="cc1f5-113">Verrà visualizzato un avviso che indica che sono presenti liste di distribuzione (chiamate anche **gruppi di distribuzione** ) idonee per l'aggiornamento a Gruppi di Office 365.</span><span class="sxs-lookup"><span data-stu-id="cc1f5-113">You'll see a notice indicating you have distribution lists (also called **distribution groups** ) that are eligible to be upgraded to Office 365 groups.</span></span><br/> <span data-ttu-id="cc1f5-114">![Selezionare il pulsante inizia](../../media/8cf838b4-2644-401f-a366-08c1eea183eb.png)</span><span class="sxs-lookup"><span data-stu-id="cc1f5-114">![Select the Get started button](../../media/8cf838b4-2644-401f-a366-08c1eea183eb.png)</span></span>

3. <span data-ttu-id="cc1f5-115">Selezionare una o più liste di distribuzione (chiamate anche **gruppo di distribuzione** ) nella pagina **Gruppi**.</span><span class="sxs-lookup"><span data-stu-id="cc1f5-115">Select one or more distribution lists (also called a **distribution group** ) from the **groups** page.</span></span><br/><span data-ttu-id="cc1f5-116">![Selezionare un gruppo di distribuzione](../../media/2c303433-d60b-4100-a6ae-5809b03a8cdb.png)</span><span class="sxs-lookup"><span data-stu-id="cc1f5-116">![Select a distribution group](../../media/2c303433-d60b-4100-a6ae-5809b03a8cdb.png)</span></span>

4. <span data-ttu-id="cc1f5-117">Selezionare l'icona di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="cc1f5-117">Select the upgrade icon.</span></span><br/>![Icona di aggiornamento a gruppi di Office 365](../../media/1e28cb3d-bff3-4be3-8329-1902d2d54720.png)

5. <span data-ttu-id="cc1f5-119">Nella finestra di dialogo informazioni selezionare **Sì** per confermare l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="cc1f5-119">On the information dialog, select **Yes** to confirm the upgrade.</span></span> <span data-ttu-id="cc1f5-120">Il processo inizia immediatamente.</span><span class="sxs-lookup"><span data-stu-id="cc1f5-120">The process begins immediately.</span></span> <span data-ttu-id="cc1f5-121">A seconda delle dimensioni e del numero di DLs che si sta aggiornando, il processo può richiedere minuti o ore.</span><span class="sxs-lookup"><span data-stu-id="cc1f5-121">Depending on the size and number of DLs you're upgrading, the process can take minutes or hours.</span></span><br/><span data-ttu-id="cc1f5-122">Se la lista di distribuzione non può essere aggiornata, viene visualizzata una finestra di dialogo che indica questo problema.</span><span class="sxs-lookup"><span data-stu-id="cc1f5-122">If the distribution list can't be upgraded, a dialog appears saying so.</span></span> <span data-ttu-id="cc1f5-123">Visualizzare le [liste di distribuzione che non possono essere aggiornate](#which-distribution-lists-cannot-be-upgraded).</span><span class="sxs-lookup"><span data-stu-id="cc1f5-123">See [Which distribution lists cannot be upgraded?](#which-distribution-lists-cannot-be-upgraded).</span></span>

6. <span data-ttu-id="cc1f5-124">Se si esegue l'aggiornamento di più liste di distribuzione, utilizzare l'elenco a discesa per filtrare le liste di distribuzione che sono state aggiornate.</span><span class="sxs-lookup"><span data-stu-id="cc1f5-124">If you're upgrading multiple distribution lists, use the drop-down list to filter which distribution lists have been upgraded.</span></span> <span data-ttu-id="cc1f5-125">Se l'elenco non è completo, attendere un po' di tempo e quindi selezionare **Aggiorna** per vedere cosa è stato aggiornato correttamente.</span><span class="sxs-lookup"><span data-stu-id="cc1f5-125">If the list isn't complete, wait a while longer and then select **Refresh** to see what's been successfully upgraded.</span></span><br/><span data-ttu-id="cc1f5-p106">Al termine del processo di aggiornamento per tutte le liste di distribuzione selezionate, non viene visualizzato alcun avviso. Per ottenere questa informazione, è possibile esaminare le liste di distribuzione elencate in **Disponibili per l'aggiornamento** o **Liste di distribuzione aggiornate**.</span><span class="sxs-lookup"><span data-stu-id="cc1f5-p106">There's no notice that tells you when the upgrade process has completed for all DLs you selected. You can figure this out by looking to see what's listed under **Available for upgrade** or **Upgraded DLs**.</span></span>

7. <span data-ttu-id="cc1f5-p107">Se è stata selezionata una lista di distribuzione per l'aggiornamento, ma questa viene ancora visualizzata nella pagina in Disponibili per l'aggiornamento, l'aggiornamento non è riuscito. Vedere [Che cosa fare se l'aggiornamento non riesce](#what-to-do-if-the-upgrade-doesnt-work).</span><span class="sxs-lookup"><span data-stu-id="cc1f5-p107">If you selected a DL for upgrade, but it's still appears on the page as Available to upgrade, then it failed to upgrade. See [What to do if the upgrade doesn't work](#what-to-do-if-the-upgrade-doesnt-work).</span></span>

> [!NOTE]
> <span data-ttu-id="cc1f5-p108">Se si ricevono messaggi di posta elettronica di riepilogo dei gruppi, si potrebbe notare nella parte inferiore una notifica che offre di aggiornare tutte le liste di distribuzione idonee di cui si è proprietari. Per altre informazioni sui messaggi di posta elettronica di riepilogo, vedere [Avviare una conversazione di gruppo in Outlook](https://support.office.com/article/a0482e24-a769-4e39-a5ba-a7c56e828b22.aspx).</span><span class="sxs-lookup"><span data-stu-id="cc1f5-p108">If you're getting the groups digest emails you may notice at the bottom that it will sometimes offer to let you upgrade any eligible distribution lists that you're the owner of. See [Have a group conversation in Outlook](https://support.office.com/article/a0482e24-a769-4e39-a5ba-a7c56e828b22.aspx) for more information about digest emails.</span></span>


## <a name="what-to-do-if-the-upgrade-doesnt-work"></a><span data-ttu-id="cc1f5-132">Che cosa fare se l'aggiornamento non riesce</span><span class="sxs-lookup"><span data-stu-id="cc1f5-132">What to do if the upgrade doesn't work</span></span>

<span data-ttu-id="cc1f5-133">Le liste di distribuzione il cui aggiornamento non riesce restano inalterate.</span><span class="sxs-lookup"><span data-stu-id="cc1f5-133">Distribution lists that fail to upgrade remain unchanged.</span></span>

<span data-ttu-id="cc1f5-p109">Se l'aggiornamento di una o più liste di distribuzione **idonee** non riesce, aprire un [ticket di supporto](../contact-support-for-business-products.md). Il problema dovrà essere inoltrato al team dei tecnici dei gruppi, perché indaghi sul problema.</span><span class="sxs-lookup"><span data-stu-id="cc1f5-p109">If one or more **eligible** distribution lists fail to be upgraded, open a [Support ticket](../contact-support-for-business-products.md). The issue will need to be escalated to the Groups Engineering team for them to figure out the problem.</span></span>

<span data-ttu-id="cc1f5-p110">È possibile che la lista di distribuzione non sia stata aggiornata a causa di un'interruzione del servizio, ma questo è piuttosto improbabile. È possibile attendere ancora e quindi riprovare ad aggiornare la lista di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="cc1f5-p110">It's possible that the distribution list didn't get upgraded because of a service outage, but pretty unlikely. If you want, wait a while and then try to upgrade the DL again.</span></span>

## <a name="how-to-use-powershell-to-upgrade-several-distribution-lists-at-the-same-time"></a><span data-ttu-id="cc1f5-138">Come usare PowerShell per aggiornare diverse liste di distribuzione contemporaneamente</span><span class="sxs-lookup"><span data-stu-id="cc1f5-138">How to use PowerShell to upgrade several distribution lists at the same time</span></span>

<span data-ttu-id="cc1f5-139">Se si ha esperienza nell'uso di PowerShell, potrebbe essere utile scegliere questo strumento invece dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="cc1f5-139">If you're experienced at using PowerShell, you might want to go this route instead of using the UI.</span></span> <span data-ttu-id="cc1f5-140">È presente un insieme di cmdlet che consentono di aggiornare le liste di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="cc1f5-140">We have a set of cmdlets that will help you upgrade distribution lists.</span></span> <span data-ttu-id="cc1f5-141">Vedere di seguito.</span><span class="sxs-lookup"><span data-stu-id="cc1f5-141">See below.</span></span>

### <a name="upgrade-a-single-dl"></a><span data-ttu-id="cc1f5-142">Aggiornare un singolo DL</span><span class="sxs-lookup"><span data-stu-id="cc1f5-142">Upgrade a single DL</span></span>

<span data-ttu-id="cc1f5-143">Per aggiornare un singolo DL, eseguire il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="cc1f5-143">To upgrade a single DL run the following command:</span></span>

`Upgrade-DistributionGroup -DlIdentities \<Dl SMTP address\>`

<span data-ttu-id="cc1f5-144">Ad esempio, se si desidera aggiornare un DLs con l'indirizzo SMTP dl1@contoso.com, eseguire il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="cc1f5-144">For example, if you want to upgrade a DLs with SMTP address dl1@contoso.com, run the following command:</span></span>

`Upgrade-DistributionGroup -DlIdentities dl1@contoso.com`

> [!NOTE]
> <span data-ttu-id="cc1f5-145">È inoltre possibile aggiornare una singola lista di distribuzione a un gruppo di Office 365 utilizzando il cmdlet [New-UnifiedGroup](https://go.microsoft.com/fwlink/?LinkID=786379) di PowerShell</span><span class="sxs-lookup"><span data-stu-id="cc1f5-145">You can also upgrade a single distribution list to an Office 365 group using the [New-UnifiedGroup](https://go.microsoft.com/fwlink/?LinkID=786379) PowerShell cmdlet</span></span>

### <a name="upgrade-multiple-dls-in-a-batch"></a><span data-ttu-id="cc1f5-146">Aggiornare più DLs in un batch</span><span class="sxs-lookup"><span data-stu-id="cc1f5-146">Upgrade multiple DLs in a batch</span></span>

<span data-ttu-id="cc1f5-147">È inoltre possibile passare più DLs come batch e aggiornarli insieme:</span><span class="sxs-lookup"><span data-stu-id="cc1f5-147">You can also pass multiple DLs as a batch and upgrade them together:</span></span>

```
Upgrade-DistributionGroup -DlIdentities \<DL SMTP address1\>, \< DL SMTP address2\>,

\< DL SMTP address3\>, \< DL SMTP address 4\>
```

<span data-ttu-id="cc1f5-148">Ad esempio, se si desidera aggiornare cinque DLS `dl1@contoso.com` con indirizzo SMTP e `dl2@contoso.com` `dl3@contoso.com`, `dl4@contoso.com` e `dl5@contoso.com`, eseguire il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="cc1f5-148">For example, if you want to upgrade five DLs with SMTP address `dl1@contoso.com` and `dl2@contoso.com`, `dl3@contoso.com`, `dl4@contoso.com` and `dl5@contoso.com`, run the following command:</span></span>

`Upgrade-DistributionGroup -DlIdentities dl1@contoso.com, dl2@contoso.com, dl3@contoso.com, dl4@contoso.com, dl5@contoso.com`

### <a name="upgrade-all-eligible-dls"></a><span data-ttu-id="cc1f5-149">Aggiornare tutti i DLs idonei</span><span class="sxs-lookup"><span data-stu-id="cc1f5-149">Upgrade all eligible DLs</span></span>

<span data-ttu-id="cc1f5-150">Esistono due modi in cui è possibile aggiornare tutti i DLs idonei.</span><span class="sxs-lookup"><span data-stu-id="cc1f5-150">There are two ways in which you can upgrade all the eligible DLs.</span></span>

> [!NOTE]
> <span data-ttu-id="cc1f5-151">Il cmdlet Upgrade-DistributionGroup non riceve i dati dalla pipeline, per questo motivo è necessario utilizzare l'operatore "foreach-{}Object" per eseguire correttamente.</span><span class="sxs-lookup"><span data-stu-id="cc1f5-151">The Upgrade-DistributionGroup cmdlet doesn't receive data from the pipeline, for this reason it's required to use "foreach-object{}" operator to run successfully.</span></span>

1. <span data-ttu-id="cc1f5-152">Ottenere il DLs idoneo nel tenant e aggiornarlo utilizzando il comando di aggiornamento:</span><span class="sxs-lookup"><span data-stu-id="cc1f5-152">Get the eligible DLs in the tenant and upgrade them using the upgrade command:</span></span>

```
Get-EligibleDistributionGroupForMigration | Foreach-Object{
    Upgrade-DistributionGroup -DlIdentities $_.PrimarySMTPAddress
}
```

2. <span data-ttu-id="cc1f5-153">Ottenere l'elenco di tutti i DLs e aggiornare solo il DLs idoneo:</span><span class="sxs-lookup"><span data-stu-id="cc1f5-153">Get the list of all DLs and upgrade only the eligible DLs:</span></span>

```
Get-DistributionGroup| Foreach-Object{
    Upgrade-DistributionGroup -DlIdentities $_.PrimarySMTPAddress
}
```

## <a name="faq-about-upgrading-distribution-lists-to-office-365-groups-in-outlook"></a><span data-ttu-id="cc1f5-154">Domande frequenti sull'aggiornamento delle liste di distribuzione a Gruppi di Office 365 in Outlook</span><span class="sxs-lookup"><span data-stu-id="cc1f5-154">FAQ about upgrading distribution lists to Office 365 Groups in Outlook</span></span>

### <a name="which-distribution-lists-cannot-be-upgraded"></a><span data-ttu-id="cc1f5-155">Quali sono le liste di distribuzione che non è possibile aggiornare?</span><span class="sxs-lookup"><span data-stu-id="cc1f5-155">Which distribution lists cannot be upgraded?</span></span>

<span data-ttu-id="cc1f5-156">È possibile aggiornare solo liste di distribuzione semplici, gestite nel cloud e non annidate.</span><span class="sxs-lookup"><span data-stu-id="cc1f5-156">You can only upgrade cloud-managed, simple, non-nested distribution lists.</span></span> <span data-ttu-id="cc1f5-157">Nella tabella seguente sono elencate le liste di distribuzione che **non possono** essere aggiornate.</span><span class="sxs-lookup"><span data-stu-id="cc1f5-157">The table below lists distribution lists that **CANNOT** be upgraded.</span></span>

|<span data-ttu-id="cc1f5-158">**Proprietà**</span><span class="sxs-lookup"><span data-stu-id="cc1f5-158">**Property**</span></span>|<span data-ttu-id="cc1f5-159">**Idonea?**</span><span class="sxs-lookup"><span data-stu-id="cc1f5-159">**Eligible?**</span></span>|
|:-----|:-----|
|<span data-ttu-id="cc1f5-160">Lista di distribuzione gestita in locale</span><span class="sxs-lookup"><span data-stu-id="cc1f5-160">On-premises managed distribution list.</span></span>  <br/> |<span data-ttu-id="cc1f5-161">No</span><span class="sxs-lookup"><span data-stu-id="cc1f5-161">No</span></span>  <br/> |
|<span data-ttu-id="cc1f5-p113">Liste di distribuzione annidate. La lista di distribuzione ha gruppi figlio o è membro di un altro gruppo.</span><span class="sxs-lookup"><span data-stu-id="cc1f5-p113">Nested distribution lists. Distribution list either has child groups or is a member of another group.</span></span>  <br/> |<span data-ttu-id="cc1f5-164">No</span><span class="sxs-lookup"><span data-stu-id="cc1f5-164">No</span></span>  <br/> |
|<span data-ttu-id="cc1f5-165">Liste di distribuzione con **RecipientTypeDetails** membri diverse da **UserMailbox**, **SharedMailbox**, **TeamMailbox**, **MailUser**</span><span class="sxs-lookup"><span data-stu-id="cc1f5-165">Distribution lists with member **RecipientTypeDetails** other than **UserMailbox**, **SharedMailbox**, **TeamMailbox**, **MailUser**</span></span>  <br/> |<span data-ttu-id="cc1f5-166">No</span><span class="sxs-lookup"><span data-stu-id="cc1f5-166">No</span></span>  <br/> |
|<span data-ttu-id="cc1f5-167">Lista di distribuzione che ha più di 100 proprietari</span><span class="sxs-lookup"><span data-stu-id="cc1f5-167">Distribution list which has more than 100 owners</span></span>  <br/> |<span data-ttu-id="cc1f5-168">No</span><span class="sxs-lookup"><span data-stu-id="cc1f5-168">No</span></span>  <br/> |
|<span data-ttu-id="cc1f5-169">Lista di distribuzione che ha solo membri, ma nessun proprietario</span><span class="sxs-lookup"><span data-stu-id="cc1f5-169">Distribution list which only has members but no owner</span></span>  <br/> |<span data-ttu-id="cc1f5-170">No</span><span class="sxs-lookup"><span data-stu-id="cc1f5-170">No</span></span>  <br/> |
|<span data-ttu-id="cc1f5-171">Lista di distribuzione che ha un alias contenente caratteri speciali</span><span class="sxs-lookup"><span data-stu-id="cc1f5-171">Distribution list which has alias containing special characters</span></span>  <br/> |<span data-ttu-id="cc1f5-172">No</span><span class="sxs-lookup"><span data-stu-id="cc1f5-172">No</span></span>  <br/> |
|<span data-ttu-id="cc1f5-173">Lista di distribuzione configurata come indirizzo di inoltro per la cassetta postale condivisa</span><span class="sxs-lookup"><span data-stu-id="cc1f5-173">If the distribution list is configured to be a forwarding address for Shared Mailbox</span></span>  <br/> |<span data-ttu-id="cc1f5-174">No</span><span class="sxs-lookup"><span data-stu-id="cc1f5-174">No</span></span>  <br/> |
|<span data-ttu-id="cc1f5-175">Se il DL fa parte della **restrizione del mittente** in un altro DL.</span><span class="sxs-lookup"><span data-stu-id="cc1f5-175">If the DL is part of **Sender Restriction** in another DL.</span></span>  <br/> |<span data-ttu-id="cc1f5-176">No</span><span class="sxs-lookup"><span data-stu-id="cc1f5-176">No</span></span>  <br/> |
|<span data-ttu-id="cc1f5-177">Gruppi di sicurezza</span><span class="sxs-lookup"><span data-stu-id="cc1f5-177">Security groups</span></span>  <br/> |<span data-ttu-id="cc1f5-178">No</span><span class="sxs-lookup"><span data-stu-id="cc1f5-178">No</span></span>  <br/> |
|<span data-ttu-id="cc1f5-179">Liste di distribuzione dinamiche</span><span class="sxs-lookup"><span data-stu-id="cc1f5-179">Dynamic Distribution lists</span></span>  <br/> |<span data-ttu-id="cc1f5-180">No</span><span class="sxs-lookup"><span data-stu-id="cc1f5-180">No</span></span>  <br/> |
|<span data-ttu-id="cc1f5-181">Liste di distribuzione che sono state convertite in **RoomLists**</span><span class="sxs-lookup"><span data-stu-id="cc1f5-181">Distribution lists which were converted to **RoomLists**</span></span>  <br/> |<span data-ttu-id="cc1f5-182">No</span><span class="sxs-lookup"><span data-stu-id="cc1f5-182">No</span></span>  <br/> |
|<span data-ttu-id="cc1f5-183">Liste di distribuzione in cui **MemberJoinRestriction** e/o **MemberDepartRestriction** è **chiuso**</span><span class="sxs-lookup"><span data-stu-id="cc1f5-183">Distribution lists where **MemberJoinRestriction** and/or **MemberDepartRestriction** is **Closed**</span></span>  <br/> |<span data-ttu-id="cc1f5-184">No</span><span class="sxs-lookup"><span data-stu-id="cc1f5-184">No</span></span>  <br/> |

### <a name="how-do-i-check-which-dls-are-eligible-for-upgrade"></a><span data-ttu-id="cc1f5-185">Come si verifica quale DLs è idoneo per l'aggiornamento?</span><span class="sxs-lookup"><span data-stu-id="cc1f5-185">How do I check which DLs are eligible for upgrade?</span></span>

<span data-ttu-id="cc1f5-186">Se si desidera verificare se un DL è idoneo o meno, è possibile eseguire il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="cc1f5-186">If you want to check whether a DL is eligible or not, you can run the below command:</span></span>

`Get-DistributionGroup \<DL SMTP address\> | Get-EligibleDistributionGroupForMigration`

<span data-ttu-id="cc1f5-187">Se si desidera verificare quali DLs sono idonei per l'aggiornamento, eseguire il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="cc1f5-187">If you want to check which DLs are eligible for upgrade just run the following command:</span></span>

`Get-EligibleDistributionGroupForMigration`

### <a name="who-can-run-the-upgrade-scripts"></a><span data-ttu-id="cc1f5-188">Chi può eseguire gli script di aggiornamento?</span><span class="sxs-lookup"><span data-stu-id="cc1f5-188">Who can run the upgrade scripts?</span></span>

<span data-ttu-id="cc1f5-189">Utenti che dispongono di diritti di amministratore globale di Office 365 o Exchange.</span><span class="sxs-lookup"><span data-stu-id="cc1f5-189">People with Office 365 global admin or Exchange admin rights.</span></span>

### <a name="why-is-the-contact-card-still-showing-a-distribution-list-what-should-i-do-to-prevent-a-upgraded-distribution-list-from-showing-up-in-my-auto-suggest-list"></a><span data-ttu-id="cc1f5-190">Perché la scheda contatto mostra ancora una lista di distribuzione?</span><span class="sxs-lookup"><span data-stu-id="cc1f5-190">Why is the contact card still showing a distribution list?</span></span> <span data-ttu-id="cc1f5-191">Come si impedisce la visualizzazione di una lista di distribuzione aggiornata nell'elenco dei suggerimenti automatici?</span><span class="sxs-lookup"><span data-stu-id="cc1f5-191">What should I do to prevent a upgraded distribution list from showing up in my auto suggest list?</span></span>

- <span data-ttu-id="cc1f5-192">Per Outlook: quando un utente tenta di inviare un messaggio di posta elettronica in Outlook digitando il nome del gruppo di Office 365 dopo la migrazione, il destinatario viene risolto come la lista di distribuzione invece del gruppo.</span><span class="sxs-lookup"><span data-stu-id="cc1f5-192">For Outlook: When someone tries to send an email in Outlook by typing the Office 365 group name after migration, the recipient will be resolved as the distribution list instead of the group.</span></span> <span data-ttu-id="cc1f5-193">La scheda contatto del destinatario sarà la scheda contatto degli elenchi di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="cc1f5-193">The contact card of the recipient will be the distribution lists contact card.</span></span> <span data-ttu-id="cc1f5-194">Questo dipende dalla cache dei destinatari o dalla cache dei nomi alternativi in Outlook.</span><span class="sxs-lookup"><span data-stu-id="cc1f5-194">This is because of the recipient cache or nick name cache in Outlook.</span></span> <span data-ttu-id="cc1f5-195">Il messaggio di posta elettronica verrà inviato correttamente al gruppo, ma potrebbe creare confusione per il mittente.</span><span class="sxs-lookup"><span data-stu-id="cc1f5-195">The email will be sent successfully to the group, but might cause confusion to the sender.</span></span><br/><span data-ttu-id="cc1f5-196">È possibile eseguire i passaggi descritti in questo argomento, [Informazioni relative all'elenco di completamento automatico di Outlook](https://go.microsoft.com/fwlink/?LinkID=798736) per reimpostare la cache e risolvere il problema.</span><span class="sxs-lookup"><span data-stu-id="cc1f5-196">You can perform the steps in this topic, [Information about the Outlook AutoComplete list](https://go.microsoft.com/fwlink/?LinkID=798736) to reset the cache, which will fix this issue.</span></span>

- <span data-ttu-id="cc1f5-197">Per Outlook sul Web: in caso di Outlook sul Web, il destinatario della lista di distribuzione rimarrà ancora nella cache.</span><span class="sxs-lookup"><span data-stu-id="cc1f5-197">For Outlook on the web: In case of Outlook on the web, the distribution list recipient will still remain in the cache.</span></span> <span data-ttu-id="cc1f5-198">È possibile seguire la procedura descritta in [rimuovere il nome o l'indirizzo di posta elettronica suggerito dall'elenco di completamento automatico](https://support.office.com/article/9E1419D9-E88F-445B-B07F-F558B8A37C58.aspx) per aggiornare la cache per visualizzare la scheda contatto di gruppo.</span><span class="sxs-lookup"><span data-stu-id="cc1f5-198">You can follow the steps in [Remove suggested name or email address from the Auto-Complete List](https://support.office.com/article/9E1419D9-E88F-445B-B07F-F558B8A37C58.aspx) to refresh the cache to see the group contact card.</span></span>

### <a name="do-new-group-members-get-a-welcome-email-in-their-inbox"></a><span data-ttu-id="cc1f5-199">I nuovi membri del gruppo ricevono un messaggio di posta elettronica di benvenuto nella propria posta in arrivo?</span><span class="sxs-lookup"><span data-stu-id="cc1f5-199">Do new group members get a welcome email in their inbox?</span></span>

<span data-ttu-id="cc1f5-p117">No. L'impostazione per abilitare i messaggi di benvenuto è impostata su false per impostazione predefinita. Questa impostazione interessa i nuovi membri del gruppo e quelli esistenti che potrebbero aggiungersi al termine dell'aggiornamento. Se successivamente il proprietario del gruppo consente utenti guest, questi non riceveranno un messaggio di posta elettronica di benvenuto nella propria posta in arrivo. I membri guest possono continuare a lavorare con il gruppo.</span><span class="sxs-lookup"><span data-stu-id="cc1f5-p117">No. The setting to enable welcome messages is set to false by default. This setting affects both existing and new group members who may join after the migration is complete. If the group owner later allows guest users, guest users won't receive a welcome email in their inbox. Guest members can continue working with the group.</span></span>

### <a name="what-if-one-or-some-of-the-dls-are-not-upgraded"></a><span data-ttu-id="cc1f5-205">Cosa succede se uno o più dei DLs non vengono aggiornati?</span><span class="sxs-lookup"><span data-stu-id="cc1f5-205">What if one or some of the DLs are not upgraded?</span></span>

<span data-ttu-id="cc1f5-206">Esistono alcuni casi in cui se DL è idoneo ma non è stato possibile aggiornarlo.</span><span class="sxs-lookup"><span data-stu-id="cc1f5-206">There are some cases in which though DL is eligible but could not be upgraded.</span></span> <span data-ttu-id="cc1f5-207">Il DL non viene aggiornato e rimane come un DL.</span><span class="sxs-lookup"><span data-stu-id="cc1f5-207">The DL does not get upgraded and remains as a DL.</span></span>

- <span data-ttu-id="cc1f5-208">Dove admin ha applicato il **criterio degli indirizzi di posta elettronica del gruppo** per i gruppi in un'organizzazione e tentano di aggiornare DLS che non soddisfa i criteri, il DL non viene aggiornato</span><span class="sxs-lookup"><span data-stu-id="cc1f5-208">Where admin has applied **Group Email Address Policy** for the groups in an organization and they try to upgrade DLs which doesn't fulfill the criteria, the DL does not get upgraded</span></span>

- <span data-ttu-id="cc1f5-209">DLs con **MemberJoinRestriction** o **MemberDepartRestriction** impostato su **chiuso**, non è stato possibile aggiornare</span><span class="sxs-lookup"><span data-stu-id="cc1f5-209">DLs with **MemberJoinRestriction** or **MemberDepartRestriction** set to **Closed**, could not be upgraded</span></span>

### <a name="what-happens-to-the-dl-if-the-upgrade-from-eac-fails"></a><span data-ttu-id="cc1f5-210">Che cosa succede alla lista di distribuzione se l'aggiornamento dall'interfaccia di amministrazione di Exchange non riesce?</span><span class="sxs-lookup"><span data-stu-id="cc1f5-210">What happens to the DL if the upgrade from EAC fails?</span></span>

<span data-ttu-id="cc1f5-p119">L'aggiornamento viene completato solo quando la chiamata viene inviata al server. Se l'aggiornamento non riesce, le liste di distribuzione restano inalterate e funzionano come prima.</span><span class="sxs-lookup"><span data-stu-id="cc1f5-p119">The upgrade will happen only when the call is submitted to the server. If the upgrade fails, your DLs will be intact. They will work like they used to.</span></span>


