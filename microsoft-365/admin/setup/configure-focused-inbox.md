---
title: Configurare Posta in arrivo evidenziata per tutti gli utenti nell'organizzazione
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 613a845c-4b71-41de-b331-acdcf5b6625d
description: "Informazioni su come configurare Posta in arrivo evidenziata per tutti gli utenti o per utenti specifici dell'organizzazione. "
ms.openlocfilehash: e6c77bdff00e7cd98f5034267699e19d8582db27
ms.sourcegitcommit: 38d828ae8d4350ae774a939c8decf30cb36c3bea
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/02/2020
ms.locfileid: "49551902"
---
# <a name="configure-focused-inbox-for-everyone-in-your-organization"></a><span data-ttu-id="f9d8b-103">Configurare Posta in arrivo evidenziata per tutti gli utenti nell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="f9d8b-103">Configure Focused Inbox for everyone in your organization</span></span>

  <span data-ttu-id="f9d8b-104">Se si è responsabili della configurazione della posta elettronica per TUTTI gli utenti di un'azienda, questo articolo contiene tutte le informazioni necessarie.</span><span class="sxs-lookup"><span data-stu-id="f9d8b-104">If you're responsible for configuring how email works for EVERYONE in a business this article is for you!</span></span> <span data-ttu-id="f9d8b-105">Spiega come personalizzare o disattivare l'opzione per l'azienda e risponde alle [domande frequenti](#faq-for-focused-inbox).</span><span class="sxs-lookup"><span data-stu-id="f9d8b-105">It explains how to customize it or turn it off for your business, and answers [frequently asked questions](#faq-for-focused-inbox).</span></span>  <br/> <span data-ttu-id="f9d8b-106">Se si vuole disattivare la Posta in arrivo evidenziata solo per il proprio account, vedere [Disattivare Posta in arrivo evidenziata](https://support.microsoft.com/office/f714d94d-9e63-4217-9ccb-6cb2986aa1b2).</span><span class="sxs-lookup"><span data-stu-id="f9d8b-106">If you would like to turn off Focused Inbox for just yourself, please see [Turn off Focused Inbox](https://support.microsoft.com/office/f714d94d-9e63-4217-9ccb-6cb2986aa1b2).</span></span>  

<span data-ttu-id="f9d8b-p102">Per essere certi che gli utenti ricevano specifici messaggi di posta elettronica aziendali, ad esempio dal reparto Risorse umane o Paghe e stipendi, è possibile configurare Posta in arrivo evidenziata in modo che questi messaggi siano inclusi nella visualizzazione Evidenziata. È anche possibile scegliere se consentire agli utenti dell'organizzazione di visualizzare Posta in arrivo evidenziata nella propria cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="f9d8b-p102">If you want to be sure that your users receive business-specific email messages, for example, from HR or payroll, you can configure Focused Inbox so these messages reach the Focused view. You can also control whether users in your organization see the Focused Inbox in their mailbox.</span></span>
  
## <a name="turn-focused-inbox-on-or-off-in-your-organization"></a><span data-ttu-id="f9d8b-109">Attivare o disattivare Posta in arrivo evidenziata nell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="f9d8b-109">Turn Focused Inbox On or Off in your organization</span></span>

<span data-ttu-id="f9d8b-110">Per attivare o disattivare Posta in arrivo evidenziata per tutti gli utenti dell'organizzazione, si usa PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f9d8b-110">You use PowerShell to turn Focused Inbox on or off for everyone in your organization.</span></span> <span data-ttu-id="f9d8b-111">Si vuole eseguire questa operazione nell'interfaccia di amministrazione di Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="f9d8b-111">Do you want to do this in the Microsoft 365 admin center?</span></span> <span data-ttu-id="f9d8b-112">È possibile comunicarlo al team di progettazione Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f9d8b-112">Let our Engineering team know.</span></span> <span data-ttu-id="f9d8b-113">**[Votare qui.](https://go.microsoft.com/fwlink/?linkid=862489)**</span><span class="sxs-lookup"><span data-stu-id="f9d8b-113">**[Vote here!](https://go.microsoft.com/fwlink/?linkid=862489)**</span></span>
  
 <span data-ttu-id="f9d8b-114">**Per disattivare la Posta in arrivo evidenziata:**</span><span class="sxs-lookup"><span data-stu-id="f9d8b-114">**To turn off Focused Inbox:**</span></span>
  
<span data-ttu-id="f9d8b-p104">L'esempio di PowerShell seguente **disattiva** la Posta in arrivo evidenziata nell'organizzazione. La funzionalità rimane comunque disponibile per gli utenti, che, se vogliono, possono riabilitarla in ciascuno dei propri client.</span><span class="sxs-lookup"><span data-stu-id="f9d8b-p104">The following PowerShell example turns Focused Inbox **Off** in your organization. However, it doesn't block the availability of the feature for your users. If they want, they can still re-enable Focused Inbox again on each of their clients.</span></span> 
  
1. <span data-ttu-id="f9d8b-118">[Connettersi a Exchange Online tramite la sessione remota di PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span><span class="sxs-lookup"><span data-stu-id="f9d8b-118">[Connect to Exchange Online using remote PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span>

2. <span data-ttu-id="f9d8b-p105">Per poter eseguire queste procedure occorre aver ricevuto le autorizzazioni appropriate. Per informazioni sulle autorizzazioni necessarie, vedere la voce "Regole di trasporto" in [Criteri di messaggistica e autorizzazioni di conformità](https://go.microsoft.com/fwlink/p/?LinkId=829796).</span><span class="sxs-lookup"><span data-stu-id="f9d8b-p105">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Transport rules" entry in [Messaging policy and compliance permissions](https://go.microsoft.com/fwlink/p/?LinkId=829796).</span></span>

3. <span data-ttu-id="f9d8b-121">Eseguire il cmdlet **Get-OrganizationConfig**.</span><span class="sxs-lookup"><span data-stu-id="f9d8b-121">Run the **Get-OrganizationConfig** cmdlet.</span></span> 

 ``` PowerShell
Get-OrganizationConfig
 ```

4. <span data-ttu-id="f9d8b-122">Cercare **FocusedInboxOn** per visualizzare l'impostazione corrente:</span><span class="sxs-lookup"><span data-stu-id="f9d8b-122">Look for **FocusedInboxOn** to view its current setting:</span></span> 

    ![Risposta di PowerShell sullo stato della Posta in arrivo evidenziata.](../../media/419d8caa-89b9-45c5-91d9-8c023297456e.png)
  
5. <span data-ttu-id="f9d8b-124">Eseguire il cmdlet seguente per disattivare la Posta in arrivo evidenziata.</span><span class="sxs-lookup"><span data-stu-id="f9d8b-124">Run the following cmdlet to turn Focused Inbox off.</span></span>

 ``` PowerShell
 Set-OrganizationConfig -FocusedInboxOn $false
 ```

6. <span data-ttu-id="f9d8b-125">Eseguire di nuovo il cmdlet **Get-OrganizationConfig**. Si vedrà che FocusedInboxOn è impostato su $false, che indica che è disattivato.</span><span class="sxs-lookup"><span data-stu-id="f9d8b-125">Run the **Get-OrganizationConfig** cmdlet again and you'll see that FocusedInboxOn is set to $false, which means it's been turned off.</span></span> 

 <span data-ttu-id="f9d8b-126">**Per attivare la Posta in arrivo evidenziata:**</span><span class="sxs-lookup"><span data-stu-id="f9d8b-126">**To turn on Focused Inbox:**</span></span>
  
- <span data-ttu-id="f9d8b-127">Nel passaggio 5 precedente eseguire il cmdlet seguente per attivare la Posta in arrivo evidenziata.</span><span class="sxs-lookup"><span data-stu-id="f9d8b-127">In Step 5 above, run the following cmdlet to turn Focused Inbox on.</span></span>

 ``` PowerShell
 Set-OrganizationConfig -FocusedInboxOn $true
 ```

## <a name="what-do-users-see-after-i-turn-on-focused-inbox"></a><span data-ttu-id="f9d8b-128">Cosa vedono gli utenti dopo l'attivazione della Posta in arrivo evidenziata? </span><span class="sxs-lookup"><span data-stu-id="f9d8b-128">What do users see after I turn on Focused Inbox?</span></span>

<span data-ttu-id="f9d8b-p106">Per accedere alla visualizzazione Evidenziata, gli utenti devono chiudere e riavviare Outlook. Dopo il riavvio di Outlook, nell'interfaccia utente di Outlook vedranno una descrizione comando che consentirà loro di usare la nuova Posta in arrivo evidenziata.</span><span class="sxs-lookup"><span data-stu-id="f9d8b-p106">Your users will see the Focused view only after they close and restart Outlook. When they restart Outlook, they'll see a Tip in the Outlook user interface giving them to the option to use the new Focused Inbox.</span></span>
  
![Come appare la funzionalità Posta in arrivo evidenziata quando un utente apre Outlook sul Web per la prima volta.](../../media/f6ef79e7-0f4c-4a23-b6f0-7c15d927b5f0.png)
  
<span data-ttu-id="f9d8b-p107">Se si passa da Messaggi secondari a Posta in arrivo evidenziata, è possibile scegliere se abilitare ("Prova") o ignorare la funzionalità. Se l'utente ha più client (supportati), può abilitare o disabilitare la Posta in arrivo evidenziata sui singoli client. Il suggerimento è simile a quanto segue:</span><span class="sxs-lookup"><span data-stu-id="f9d8b-p107">If you're switching from Clutter to Focused Inbox, they can decide to enable it ("Try it") or dismiss the feature. If the user has multiple (supported) clients, they can enable/disable Focused Inbox individually on each one. The tip looks like this:</span></span>
  
![Come appare la funzionalità Posta in arrivo evidenziata quando viene distribuita agli utenti e Outlook viene riaperto.](../../media/c034f969-d650-4333-88f1-dd10ade0a94c.png)
  
<span data-ttu-id="f9d8b-p108">Quando un utente decide di iniziare a usare la Posta in arrivo evidenziata, la funzionalità Messaggi secondari viene disabilitata automaticamente. La cartella Messaggi secondari viene convertita in una cartella standard, che può essere rinominata o eliminata.</span><span class="sxs-lookup"><span data-stu-id="f9d8b-p108">When a user decides to start using Focused Inbox, Clutter gets disabled automatically. The Clutter folder gets converted into a standard folder, that allows the user to rename or delete it.</span></span>
  
## <a name="turn-focused-inbox-on-or-off-for-specific-users"></a><span data-ttu-id="f9d8b-138">Attivare o disattivare la Posta in arrivo evidenziata per utenti specifici</span><span class="sxs-lookup"><span data-stu-id="f9d8b-138">Turn Focused Inbox On or Off for specific users</span></span>

<span data-ttu-id="f9d8b-p109">Questo esempio **disattiva** la Posta in arrivo evidenziata per Tim Matthews nell'organizzazione Contoso. La funzionalità rimarrà comunque disponibile per questo utente, che, se vuole, può abilitare di nuovo la Posta in arrivo evidenziata in ognuno dei suoi client.</span><span class="sxs-lookup"><span data-stu-id="f9d8b-p109">This example turns Focused Inbox **Off** for Tim Matthews in the Contoso organization. However, it doesn't block the availability of the feature to him. If his wants, he can still re-enable Focused Inbox again on each of his clients.</span></span> 
  
1. <span data-ttu-id="f9d8b-142">[Connettersi a Exchange Online tramite la sessione remota di PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span><span class="sxs-lookup"><span data-stu-id="f9d8b-142">[Connect to Exchange Online using remote PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span>

2. <span data-ttu-id="f9d8b-p110">Prima di eseguire queste procedure, è necessario che siano assegnate le autorizzazioni. Per informazioni sulle autorizzazioni necessarie, vedere la voce "Regole di trasporto" nell'argomento Criteri di messaggistica e autorizzazioni di conformità.</span><span class="sxs-lookup"><span data-stu-id="f9d8b-p110">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Transport rules" entry in the Messaging policy and compliance permissions topic.</span></span>

3. <span data-ttu-id="f9d8b-145">Eseguire il cmdlet **Get-FocusedInbox**, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="f9d8b-145">Run the **Get-FocusedInbox** cmdlet, for example:</span></span> 

 ``` PowerShell
 Get-FocusedInbox -Identity <tim@contoso.com>
 ```

4. <span data-ttu-id="f9d8b-146">Cercare FocusedInboxOn per visualizzare l'impostazione corrente:</span><span class="sxs-lookup"><span data-stu-id="f9d8b-146">Look for FocusedInboxOn to view its current setting:</span></span>

    ![Risposta di PowerShell sullo stato della Posta in arrivo evidenziata.](../../media/419d8caa-89b9-45c5-91d9-8c023297456e.png)
  
5. <span data-ttu-id="f9d8b-148">Eseguire il cmdlet seguente per disattivare la Posta in arrivo evidenziata:</span><span class="sxs-lookup"><span data-stu-id="f9d8b-148">Run the following cmdlet to turn Focused Inbox off:</span></span>

 ``` PowerShell
 Set-FocusedInbox -Identity <tim@contoso.com> -FocusedInboxOn $false
 ```

6. <span data-ttu-id="f9d8b-149">OPPURE, eseguire il cmdlet seguente per attivarla:</span><span class="sxs-lookup"><span data-stu-id="f9d8b-149">OR, run the following cmdlet to turn it on:</span></span>

 ``` PowerShell
 Set-FocusedInbox -Identity <tim@contoso.com> -FocusedInboxOn $true
 ```

## <a name="use-the-ui-to-create-a-transport-rule-to-direct-email-messages-to-the-focused-view-for-all-your-users"></a><span data-ttu-id="f9d8b-150">Usare l'interfaccia utente per creare una regola di trasporto che indirizzi i messaggi di posta elettronica alla visualizzazione Evidenziata per tutti gli utenti</span><span class="sxs-lookup"><span data-stu-id="f9d8b-150">Use the UI to create a transport rule to direct email messages to the Focused view for all your users</span></span>

1. <span data-ttu-id="f9d8b-151">Accedere all'<a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">interfaccia di amministrazione di Exchange</a>.</span><span class="sxs-lookup"><span data-stu-id="f9d8b-151">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>

2. <span data-ttu-id="f9d8b-152">Passare a **Flusso di posta** \> **Regole**.</span><span class="sxs-lookup"><span data-stu-id="f9d8b-152">Navigate to **mail flow** \> **Rules**.</span></span> <span data-ttu-id="f9d8b-153">Selezionare l'![icona Aggiungi dell'interfaccia di amministrazione di Exchange](../../media/795e5bdd-48bb-433f-8e07-3c7a19f8eca2.gif) e quindi selezionare **Crea nuova regola...**.</span><span class="sxs-lookup"><span data-stu-id="f9d8b-153">Select ![EAC Add icon](../../media/795e5bdd-48bb-433f-8e07-3c7a19f8eca2.gif) and then select **Create a new rule...**.</span></span> 

3. <span data-ttu-id="f9d8b-154">Dopo aver creato la nuova regola, selezionare **Salva** per avviarla.</span><span class="sxs-lookup"><span data-stu-id="f9d8b-154">After you're done creating the new rule, select **Save** to start the rule.</span></span>

    <span data-ttu-id="f9d8b-155">L'immagine seguente mostra un esempio in cui tutti i messaggi inviati da "Reparto Retribuzioni" devono essere recapitati in Posta in arrivo evidenziata.</span><span class="sxs-lookup"><span data-stu-id="f9d8b-155">The following image shows an example where all messages From "Payroll Department" are to be delivered to the Focused Inbox.</span></span>

    ![retribuzioni focusedinbox](../../media/focusedinbox-transport-rule.PNG)

> [!NOTE]
> <span data-ttu-id="f9d8b-157">Il testo del valore dell’intestazione del messaggio in questo esempio è **X-MS-Exchange-Organization-BypassFocusedInbox**.</span><span class="sxs-lookup"><span data-stu-id="f9d8b-157">The message header value text in this example is, **X-MS-Exchange-Organization-BypassFocusedInbox**.</span></span>
  
## <a name="use-powershell-to-create-a-transport-rule-to-direct-email-messages-to-the-focused-view-for-all-your-users"></a><span data-ttu-id="f9d8b-158">Usare PowerShell per creare una regola di trasporto che indirizzi i messaggi di posta elettronica alla visualizzazione Evidenziata per tutti gli utenti</span><span class="sxs-lookup"><span data-stu-id="f9d8b-158">Use PowerShell to create a transport rule to direct email messages to the Focused view for all your users</span></span>

1. <span data-ttu-id="f9d8b-159">[Connettersi a Exchange Online tramite la sessione remota di PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span><span class="sxs-lookup"><span data-stu-id="f9d8b-159">[Connect to Exchange Online using remote PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span>

2. <span data-ttu-id="f9d8b-p112">Per poter eseguire queste procedure occorre aver ricevuto le autorizzazioni appropriate. Per informazioni sulle autorizzazioni necessarie, vedere la voce "Regole di trasporto" in [Criteri di messaggistica e autorizzazioni di conformità](https://go.microsoft.com/fwlink/p/?LinkId=829796).</span><span class="sxs-lookup"><span data-stu-id="f9d8b-p112">You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Transport rules" entry in [Messaging policy and compliance permissions](https://go.microsoft.com/fwlink/p/?LinkId=829796).</span></span>

3. <span data-ttu-id="f9d8b-162">Eseguire questo comando per consentire il recapito di tutti i messaggi inviati, ad esempio, da "Reparto Retribuzioni" alla Posta in arrivo evidenziata.</span><span class="sxs-lookup"><span data-stu-id="f9d8b-162">Run the following command to allow all messages from "Payroll Department," for example, to be delivered to the Focused Inbox.</span></span>

 ``` PowerShell
 New-TransportRule -Name <name_of_the_rule> -From "Payroll Department" -SetHeaderName "X-MS-Exchange-Organization-BypassFocusedInbox" -SetHeaderValue "true"
 ```

> [!IMPORTANT]
> <span data-ttu-id="f9d8b-163">In questo esempio sia "X-MS-Exchange-Organization-BypassFocusedInbox" che "true" fanno distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="f9d8b-163">In this example, both "X-MS-Exchange-Organization-BypassFocusedInbox" and "true" are case sensitive.</span></span>
> <span data-ttu-id="f9d8b-164">Inoltre, Posta in arrivo evidenziata rispetterà l'intestazione X per evitare i messaggi secondari, pertanto se si usa questa impostazione in Messaggi secondari, verrà usata anche in Posta in arrivo evidenziata.</span><span class="sxs-lookup"><span data-stu-id="f9d8b-164">Also, Focused Inbox will honor the X-header that bypasses Clutter, so if you use this setting in Clutter, it will be used in Focused Inbox.</span></span> <span data-ttu-id="f9d8b-165">Per informazioni dettagliate su sintassi e parametri, vedere [New-TransportRule](https://go.microsoft.com/fwlink/p/?LinkId=830194).</span><span class="sxs-lookup"><span data-stu-id="f9d8b-165">For detailed syntax and parameter information, see [New-TransportRule](https://go.microsoft.com/fwlink/p/?LinkId=830194).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="f9d8b-166">Come verificare se l'operazione ha avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="f9d8b-166">How do you know this worked?</span></span>

<span data-ttu-id="f9d8b-167">È possibile controllare le intestazioni dei messaggi di posta elettronica per vedere se i messaggi vengono spostati nella Posta in arrivo in seguito all'applicazione del bypass della regola di trasporto di Posta in arrivo evidenziata.</span><span class="sxs-lookup"><span data-stu-id="f9d8b-167">You can check email message headers to see if the email messages are landing in the Inbox due to the Focused Inbox transport rule bypass.</span></span> <span data-ttu-id="f9d8b-168">Selezionare un messaggio di posta elettronica da una cassetta postale dell'organizzazione a cui è applicata la regola di trasporto Posta in arrivo evidenziata.</span><span class="sxs-lookup"><span data-stu-id="f9d8b-168">Pick an email message from a mailbox in your organization that has the Focused Inbox transport rule applied.</span></span> <span data-ttu-id="f9d8b-169">Nelle intestazioni del messaggio cercare **X-MS-Exchange-Organization-BypassFocusedInbox: true**.</span><span class="sxs-lookup"><span data-stu-id="f9d8b-169">Look at the headers stamped on the message, and you should see the **X-MS-Exchange-Organization-BypassFocusedInbox: true** header.</span></span> <span data-ttu-id="f9d8b-170">Se è visualizzato, il bypass è stato applicato.</span><span class="sxs-lookup"><span data-stu-id="f9d8b-170">This means the bypass is working.</span></span> <span data-ttu-id="f9d8b-171">Per informazioni su come trovare le informazioni sull'intestazione, consultare l'articolo [Visualizzare le informazioni di intestazione Internet per un messaggio di posta elettronica](https://go.microsoft.com/fwlink/p/?LinkId=822530).</span><span class="sxs-lookup"><span data-stu-id="f9d8b-171">Check out the [View the Internet header information for an email message](https://go.microsoft.com/fwlink/p/?LinkId=822530) article for info on how to find the header information.</span></span>

## <a name="turn-onoff-clutter"></a><span data-ttu-id="f9d8b-172">Attivare/disattivare Messaggi secondari</span><span class="sxs-lookup"><span data-stu-id="f9d8b-172">Turn on/off Clutter</span></span>

<span data-ttu-id="f9d8b-p115">Alcuni utenti hanno segnalato che la funzionalità Messaggi secondari ha smesso improvvisamente di funzionare. In questo caso, è possibile abilitarla nuovamente per utenti specifici. Vedere [Configurare Messaggi secondari per l'organizzazione](../email/configure-clutter.md).</span><span class="sxs-lookup"><span data-stu-id="f9d8b-p115">We've received reports that Clutter suddenly stopped working for some users. If this happens, you can enable it again for specific users. See [Configure Clutter for your organization](../email/configure-clutter.md).</span></span>

## <a name="faq-for-focused-inbox"></a><span data-ttu-id="f9d8b-176">Domande frequenti su Posta in arrivo evidenziata</span><span class="sxs-lookup"><span data-stu-id="f9d8b-176">FAQ for Focused Inbox</span></span>

<span data-ttu-id="f9d8b-177">Ecco le risposte ad alcune domande frequenti su Posta in arrivo evidenziata.</span><span class="sxs-lookup"><span data-stu-id="f9d8b-177">Here are answers to Frequently Asked Questions about Focused Inbox.</span></span>

### <a name="can-i-control-how-i-roll-out-focused-inbox-in-my-organization"></a><span data-ttu-id="f9d8b-178">Si può controllare la distribuzione di Posta in arrivo evidenziata nell'organizzazione?</span><span class="sxs-lookup"><span data-stu-id="f9d8b-178">Can I control how I roll out Focused Inbox in my organization?</span></span>

<span data-ttu-id="f9d8b-p116">Sì. È possibile attivare o disattivare Posta in arrivo evidenziata per l'intera organizzazione oppure per utenti specifici. Vedere sopra.</span><span class="sxs-lookup"><span data-stu-id="f9d8b-p116">Yes. You can turn Focused Inbox on or off for your entire organization, or you can turn it on or off for specified users. See above.</span></span>
  
### <a name="is-the-focused-inbox-feature-only-available-for-office-2016-clients"></a><span data-ttu-id="f9d8b-182">La funzionalità Posta in arrivo evidenziata è disponibile SOLO per i clienti di Office 2016?</span><span class="sxs-lookup"><span data-stu-id="f9d8b-182">Is the Focused Inbox feature ONLY available for Office 2016 clients?</span></span>

<span data-ttu-id="f9d8b-183">Sì, solo gli utenti di Office 2016 sono interessati.</span><span class="sxs-lookup"><span data-stu-id="f9d8b-183">Yes, only users with Office 2016 are affected.</span></span> <span data-ttu-id="f9d8b-184">Questa funzionalità non sarà inserita in Outlook 2013 o versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="f9d8b-184">The feature is not going to be backported to Outlook 2013 or earlier.</span></span>
  
### <a name="how-long-does-it-take-for-focused-inbox-changes-to-take-place-in-outlook"></a><span data-ttu-id="f9d8b-185">Quanto tempo richiede l'applicazione delle modifiche di Posta in arrivo evidenziata in Outlook?</span><span class="sxs-lookup"><span data-stu-id="f9d8b-185">How long does it take for Focused Inbox changes to take place in Outlook?</span></span>

<span data-ttu-id="f9d8b-186">Dopo avere attivato o disattivato Posta in arrivo evidenziata, le impostazioni diverranno effettive quando gli utenti chiudono e riavviano Outlook.</span><span class="sxs-lookup"><span data-stu-id="f9d8b-186">Once you turn on or turn off Focused Inbox, the settings will take effect once your users close and restart Outlook.</span></span>
  
### <a name="what-happens-to-clutter-once-i-turn-on-focused-inbox"></a><span data-ttu-id="f9d8b-187">Che cosa succede a Messaggi secondari dopo l'attivazione di Posta in arrivo evidenziata?</span><span class="sxs-lookup"><span data-stu-id="f9d8b-187">What happens to Clutter once I turn on Focused Inbox?</span></span>

<span data-ttu-id="f9d8b-p118">Dopo il passaggio, la posta elettronica meno interattiva non verrà più recapitata nella cartella Messaggi secondari, ma verrà invece suddivisa tra le schede Evidenziata e Altra nella Posta in arrivo. Lo stesso algoritmo di spostamento degli elementi nella cartella Messaggi secondari è ora alla base di Posta in arrivo evidenziata, vale a dire che tutti i messaggi che sono stati impostati per essere spostati in Messaggi secondari verranno ora spostati nella scheda Altra. Tutti i messaggi già presenti nella cartella Messaggi secondari vi rimarranno fino a quando non si decide di eliminarli o spostarli.</span><span class="sxs-lookup"><span data-stu-id="f9d8b-p118">After switching, you'll no longer receive less actionable email in the Clutter folder. Instead, email will be split between the Focused and Other tabs in your inbox. The same algorithm that moved items to the Clutter folder now powers Focused Inbox, meaning that any emails that were set to move to Clutter will now be moved to Other. Any messages already in your Clutter folder will remain there until you decide to delete or move them.</span></span>
  
<span data-ttu-id="f9d8b-192">Vedere questo post di [Tony Redmond](https://www.petri.com/author/tony-redmond), MVP Microsoft: [How the Focused Inbox Replaces Clutter Inside Office 365](https://www.petri.com/focused-inbox-office-365) (Sostituzione di Messaggi secondari con Posta in arrivo evidenziata in Office 365).</span><span class="sxs-lookup"><span data-stu-id="f9d8b-192">Check out this post by [Tony Redmond](https://www.petri.com/author/tony-redmond), Microsoft MVP: [How the Focused Inbox Replaces Clutter Inside Office 365](https://www.petri.com/focused-inbox-office-365).</span></span>
  
### <a name="can-i-keep-users-on-clutter-what-is-microsofts-recommendation-when-it-comes-to-using-clutter-vs-focused-inbox"></a><span data-ttu-id="f9d8b-193">È possibile mantenere gli utenti in Messaggi secondari?</span><span class="sxs-lookup"><span data-stu-id="f9d8b-193">Can I keep users on Clutter?</span></span> <span data-ttu-id="f9d8b-194">Che cosa consiglia Microsoft in relazione all'uso di Messaggi secondari e Posta in arrivo evidenziata?</span><span class="sxs-lookup"><span data-stu-id="f9d8b-194">What is Microsoft's recommendation when it comes to using Clutter vs Focused Inbox?</span></span>

<span data-ttu-id="f9d8b-p120">Sì, è possibile mantenere gli utenti in Messaggi secondari e disabilitare Posta in arrivo evidenziata, anche se alla fine la funzionalità Messaggi secondari verrà completamente sostituita da Posta in arrivo evidenziata. Di conseguenza Microsoft consiglia di passare subito a Posta in arrivo evidenziata. Per altre informazioni su come usare Messaggi secondari con Exchange Online, vedere il post di blog di [aggiornamento su Posta in arrivo evidenziata e sul destino di Messaggi secondari](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448).</span><span class="sxs-lookup"><span data-stu-id="f9d8b-p120">Yes, you can keep users on Clutter and disable Focused Inbox, however, eventually Clutter will be fully replaced with Focused Inbox so Microsoft's recommends moving to Focused Inbox now. To learn more about when you use Clutter with Exchange Online, see this blog post: [Update on Focused Inbox and our plans for Clutter](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448).</span></span>
  
### <a name="should-i-disable-clutter-for-my-end-users-if-we-are-going-to-move-everyone-to-focused-inbox"></a><span data-ttu-id="f9d8b-197">È necessario disabilitare Messaggi secondari per gli utenti finali se si intende attivare Posta in arrivo evidenziata per tutti gli utenti?</span><span class="sxs-lookup"><span data-stu-id="f9d8b-197">Should I disable Clutter for my end users if we are going to move everyone to Focused Inbox?</span></span>

<span data-ttu-id="f9d8b-p121">No. È possibile disabilitare esplicitamente Messaggi secondari per una cassetta postale eseguendo il cmdlet Set-Clutter. Se però si esegue questa operazione, il proprietario della cassetta postale noterà che i messaggi reindirizzati in precedenza a Messaggi secondari rimarranno in Posta in arrivo e dovrà elaborare manualmente tali messaggi finché il proprio client non viene aggiornato a una versione che supporta Posta in arrivo evidenziata. È quindi consigliabile non disabilitare Messaggi secondari finché non sono disponibili i client aggiornati.</span><span class="sxs-lookup"><span data-stu-id="f9d8b-p121">No. It's possible to disable Clutter for a mailbox explicitly by running the Set-Clutter cmdlet. However, if you do this, the mailbox owner will see messages that were previously redirected to the Clutter folder remain in the Inbox and they'll have to process those messages until their client is upgraded to a version that supports the Focused Inbox. It's therefore best not to disable Clutter until the upgraded clients are available.</span></span>
  
### <a name="why-are-there-two-different-cmdlets-for-managing-focused-inbox"></a><span data-ttu-id="f9d8b-202">Perché sono presenti due diversi cmdlet per la gestione di Posta in arrivo evidenziata?</span><span class="sxs-lookup"><span data-stu-id="f9d8b-202">Why are there two different cmdlets for managing Focused Inbox?</span></span>

<span data-ttu-id="f9d8b-203">A Posta in arrivo evidenziata sono associati due stati.</span><span class="sxs-lookup"><span data-stu-id="f9d8b-203">There are two states associated with Focused Inbox.</span></span>
  
- <span data-ttu-id="f9d8b-204">**Livello organizzazione**: Stato di Posta in arrivo evidenziata con timestamp dell'ultimo aggiornamento associato.</span><span class="sxs-lookup"><span data-stu-id="f9d8b-204">**Organization Level**: Focused Inbox state, and an associated last update time-stamp.</span></span>

- <span data-ttu-id="f9d8b-205">**Livello cassetta postale**: Stato di Posta in arrivo evidenziata con timestamp dell'ultimo aggiornamento associato</span><span class="sxs-lookup"><span data-stu-id="f9d8b-205">**Mailbox Level**: Focused Inbox state, and an associated last update time-stamp</span></span> 

### <a name="how-does-outlook-decide-to-show-the-focused-inbox-experience-with-these-two-states"></a><span data-ttu-id="f9d8b-206">In che modo Outlook sceglie la visualizzazione di Posta in arrivo evidenziata con questi due stati?</span><span class="sxs-lookup"><span data-stu-id="f9d8b-206">How does Outlook decide to show the Focused Inbox experience with these two states?</span></span>

<span data-ttu-id="f9d8b-p122">Outlook decide di mostrare la Posta in arrivo evidenziata con il timestamp più recente. Per impostazione predefinita, entrambi i timestamp sono "null" e, in questo caso, la funzionalità è abilitata.</span><span class="sxs-lookup"><span data-stu-id="f9d8b-p122">Outlook decides to show the experience by choosing which cmdlet has the latest time stamp. By default, both time stamps are "null" and in this case, the feature is enabled.</span></span>
  
### <a name="why-does-the-get-focusedinbox-cmdlet-return-true-when-ive-turned-focused-inbox-off-in-my-organization"></a><span data-ttu-id="f9d8b-209">Perché il cmdlet Get-FocusedInbox restituisce "true" quando la Posta in arrivo evidenziata dell'organizzazione viene disattivata?</span><span class="sxs-lookup"><span data-stu-id="f9d8b-209">Why does the Get-FocusedInbox cmdlet return "true", when I've turned Focused Inbox off in my organization?</span></span>

<span data-ttu-id="f9d8b-p123">Sono disponibili due cmdlet per il controllo di Posta in arrivo evidenziata. Quando si esegue il cmdlet Get-FocusedInbox per una cassetta postale, restituisce lo stato della funzionalità a livello della cassetta postale. L'esperienza in Outlook viene scelta in base allo stato del cmdlet modificato per ultimo.</span><span class="sxs-lookup"><span data-stu-id="f9d8b-p123">There are two cmdlets for controlling Focused Inbox. When you run Get-FocusedInbox for a mailbox, it returns the mailbox level state of the feature. The experience in Outlook is chosen based on which cmdlet state was last modified.</span></span>
  
### <a name="can-i-run-a-script-to-see-who-has-turned-on-focused-inbox"></a><span data-ttu-id="f9d8b-213">È possibile eseguire uno script per vedere chi ha attivato la Posta in arrivo evidenziata?</span><span class="sxs-lookup"><span data-stu-id="f9d8b-213">Can I run a script to see who has turned on Focused Inbox?</span></span>

<span data-ttu-id="f9d8b-p124">No e si tratta di un comportamento da progettazione. L'abilitazione della Posta in arrivo evidenziata è un'impostazione sul lato client, quindi il cmdlet può solo indicare se la cassetta postale dell'utente è idonea per l'esperienza client. Questa funzionalità potrebbe essere abilitata in alcuni client e disabilitata in altri allo stesso momento, ad esempio abilitata nell'app Outlook e in Outlook Mobile, ma disabilitata in Outlook sul Web.</span><span class="sxs-lookup"><span data-stu-id="f9d8b-p124">No, and this is by design. Focused Inbox enablement is a client side setting, so all the cmdlet can do is tell you if the user's mailbox is eligible for the client experience. It is possible for it to be simultaneously enabled in some clients and disabled in others, for example, enabled in Outlook app and Outlook Mobile but disabled in Outlook on the web.</span></span>
