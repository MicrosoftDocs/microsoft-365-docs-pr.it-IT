---
title: Criteri di denominazione dei gruppi di Office 365
ms.reviewer: arvaradh
f1.keywords:
- NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
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
- MST160
- MET150
- MOE150
ms.assetid: 6ceca4d3-cad1-4532-9f0f-d469dfbbb552
description: Informazioni su come creare un criterio di denominazione per i gruppi di Office 365.
ms.openlocfilehash: 50ea076e22680a444cb9acf04466a7e7d052bb7a
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/24/2020
ms.locfileid: "42241393"
---
# <a name="office-365-groups-naming-policy"></a><span data-ttu-id="95631-103">Criteri di denominazione dei gruppi di Office 365</span><span class="sxs-lookup"><span data-stu-id="95631-103">Office 365 Groups naming policy</span></span>

<span data-ttu-id="95631-104">Per applicare una strategia di denominazione coerente per i gruppi creati dagli utenti dell'organizzazione, è possibile utilizzare un criterio di denominazione del gruppo.</span><span class="sxs-lookup"><span data-stu-id="95631-104">You use a group naming policy to enforce a consistent naming strategy for groups created by users in your organization.</span></span> <span data-ttu-id="95631-105">I criteri di denominazione consentono all'utente e agli utenti di identificare la funzione del gruppo, dell'appartenenza, dell'area geografica o di chi ha creato il gruppo.</span><span class="sxs-lookup"><span data-stu-id="95631-105">A naming policy can help you and your users identify the function of the group, membership, geographic region, or who created the group.</span></span> <span data-ttu-id="95631-106">Il criterio di denominazione può anche contribuire alla categorizzazione dei gruppi nella rubrica.</span><span class="sxs-lookup"><span data-stu-id="95631-106">The naming policy can also help categorize groups in the address book.</span></span> <span data-ttu-id="95631-107">È possibile utilizzare il criterio per bloccare le parole specifiche che vengono utilizzate nei nomi e negli alias di gruppo.</span><span class="sxs-lookup"><span data-stu-id="95631-107">You can use the policy to block specific words from being used in group names and aliases.</span></span>

<span data-ttu-id="95631-108">I criteri di denominazione vengono applicati ai gruppi creati in tutti i carichi di lavoro dei gruppi (come Outlook, Microsoft teams, SharePoint, planner, Yammer e così via).</span><span class="sxs-lookup"><span data-stu-id="95631-108">The naming policy is applied to groups that are created across all groups workloads (like Outlook, Microsoft Teams, SharePoint, Planner, Yammer, etc).</span></span> <span data-ttu-id="95631-109">Viene applicato sia al nome del gruppo sia all'alias di gruppo.</span><span class="sxs-lookup"><span data-stu-id="95631-109">It gets applied to both the group name and group alias.</span></span> <span data-ttu-id="95631-110">Viene applicato quando un utente crea un gruppo e quando viene modificato il nome o l'alias del gruppo per un gruppo esistente.</span><span class="sxs-lookup"><span data-stu-id="95631-110">It gets applied when a user creates a group and when group name or alias is edited for an existing group.</span></span>

> [!TIP]
> <span data-ttu-id="95631-111">I criteri di denominazione del gruppo di Office 365 si applicano solo ai gruppi di Office 365.</span><span class="sxs-lookup"><span data-stu-id="95631-111">An Office 365 group naming policy only applies to Office 365 Groups.</span></span> <span data-ttu-id="95631-112">Non si applica ai gruppi di distribuzione creati in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="95631-112">It doesn't apply to distribution groups created in Exchange Online.</span></span> <span data-ttu-id="95631-113">Per creare un criterio di denominazione per i gruppi di distribuzione, vedere [Create a Distribution Group Naming Policy](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/create-group-naming-policy).</span><span class="sxs-lookup"><span data-stu-id="95631-113">To create a naming policy for distribution groups, see [Create a distribution group naming policy](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/create-group-naming-policy).</span></span>

<span data-ttu-id="95631-114">I criteri di denominazione del gruppo sono composti dalle funzionalità seguenti:</span><span class="sxs-lookup"><span data-stu-id="95631-114">The group naming policy consists of the following features:</span></span>

- <span data-ttu-id="95631-115">**Criteri di denominazione dei suffissi**: è possibile utilizzare prefissi o suffissi per definire la convenzione di denominazione di gruppi (ad esempio,\_"\_GRP US\_My Group Engineering").</span><span class="sxs-lookup"><span data-stu-id="95631-115">**Prefix-Suffix naming policy**: You can use prefixes or suffixes to define the naming convention of groups (for example: "GRP\_US\_My Group\_Engineering").</span></span> <span data-ttu-id="95631-116">I prefissi o suffissi possono essere stringhe fisse o attributi utente come [Department] che verranno sostituiti in base all'utente che crea il gruppo.</span><span class="sxs-lookup"><span data-stu-id="95631-116">The prefixes/suffixes can either be fixed strings or user attributes like [Department] that will get substituted based on the user who is creating the group.</span></span>

- <span data-ttu-id="95631-117">**Parole bloccate personalizzate**: è possibile caricare una serie di parole bloccate specifiche per la propria organizzazione che verrebbero bloccate nei gruppi creati dagli utenti.</span><span class="sxs-lookup"><span data-stu-id="95631-117">**Custom Blocked Words**: You can upload a set of blocked words specific to their organization that would be blocked in groups created by users.</span></span> <span data-ttu-id="95631-118">Ad esempio: ""CEO, Payroll, HR" (CEO, Buste paga, RU)".</span><span class="sxs-lookup"><span data-stu-id="95631-118">(For example: "CEO, Payroll, HR").</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="95631-119">Requisiti per la licenza</span><span class="sxs-lookup"><span data-stu-id="95631-119">Licensing requirements</span></span>

<span data-ttu-id="95631-120">L'utilizzo dei criteri di denominazione di Azure AD per i gruppi di Office 365 richiede che siano in possesso, ma non necessariamente, di una licenza di Azure Active Directory Premium P1 o di una licenza di Azure AD Basic EDU per ogni utente univoco (compresi gli ospiti) che sia membro di uno o più gruppi di Office 365.</span><span class="sxs-lookup"><span data-stu-id="95631-120">Using Azure AD naming policy for Office 365 groups requires that you possess but not necessarily assign an Azure Active Directory Premium P1 license or Azure AD Basic EDU license for each unique user (including guests) that is a member of one or more Office 365 groups.</span></span>
<span data-ttu-id="95631-121">Questa operazione è necessaria anche per l'amministratore che crea i criteri di denominazione dei gruppi.</span><span class="sxs-lookup"><span data-stu-id="95631-121">This is also required for the administrator that creates the Groups naming policy.</span></span>

## <a name="prefix-suffix-naming-policy"></a><span data-ttu-id="95631-122">Prefisso-suffisso Naming Policy</span><span class="sxs-lookup"><span data-stu-id="95631-122">Prefix-Suffix naming policy</span></span>

<span data-ttu-id="95631-123">I prefissi e i suffissi possono essere stringhe fisse o attributi utente.</span><span class="sxs-lookup"><span data-stu-id="95631-123">Prefixes and suffixes can either be fixed strings or user attributes.</span></span>

### <a name="fixed-strings"></a><span data-ttu-id="95631-124">Stringhe fisse</span><span class="sxs-lookup"><span data-stu-id="95631-124">Fixed strings</span></span>

<span data-ttu-id="95631-125">È possibile utilizzare stringhe brevi che consentono di differenziare i gruppi nell'elenco indirizzi globale e nel NAV sinistro dei carichi di lavoro di gruppo.</span><span class="sxs-lookup"><span data-stu-id="95631-125">You can use short strings that can help you differentiate groups in the GAL and Left nav of the group workloads.</span></span> <span data-ttu-id="95631-126">Alcuni dei suffissi comuni prefissi sono parole chiave come "GRP\_Name", "\#Name", "\_Name"</span><span class="sxs-lookup"><span data-stu-id="95631-126">Some of the common prefixes suffixes are Keywords like 'Grp\_Name' , '\#Name', '\_Name'</span></span>

### <a name="attributes"></a><span data-ttu-id="95631-127">Attributi</span><span class="sxs-lookup"><span data-stu-id="95631-127">Attributes</span></span>

<span data-ttu-id="95631-128">È possibile utilizzare gli attributi che consentono di identificare chi ha creato il gruppo come [Department] e dove è stato creato da like [Country].</span><span class="sxs-lookup"><span data-stu-id="95631-128">You can use attributes that can help identify who created the group like [Department] and where it was created from like [Country].</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="95631-129">**Esempi**</span><span class="sxs-lookup"><span data-stu-id="95631-129">**Examples**</span></span>|<span data-ttu-id="95631-130">Criterio = "GRP [GroupName] [Department]"</span><span class="sxs-lookup"><span data-stu-id="95631-130">Policy = "GRP [GroupName] [Department]"</span></span>|
||<span data-ttu-id="95631-131">Reparto dell'utente = Progettazione</span><span class="sxs-lookup"><span data-stu-id="95631-131">User's department = Engineering</span></span>|
||<span data-ttu-id="95631-132">Nome del gruppo creato = "GRP Mio gruppo Progettazione"</span><span class="sxs-lookup"><span data-stu-id="95631-132">Created group name = "GRP My Group Engineering"</span></span>|

<span data-ttu-id="95631-133">Gli attributi di Azure Active Directory (Azure AD) supportati sono [Department], [Company], [Office], [StateOrProvince], [CountryOrRegion], [title]</span><span class="sxs-lookup"><span data-stu-id="95631-133">Supported Azure Active Directory (Azure AD) attributes are [Department], [Company], [Office], [StateOrProvince], [CountryOrRegion], [Title]</span></span>

- <span data-ttu-id="95631-p108">Gli attributi utente non supportati sono considerati stringhe fisse. Ad esempio, [Codicepostale]"</span><span class="sxs-lookup"><span data-stu-id="95631-p108">Unsupported user attributes are considered as fixed strings. E.g. "[postalCode]"</span></span>

- <span data-ttu-id="95631-137">Gli attributi di estensione e gli attributi personalizzati non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="95631-137">Extension attributes and custom attributes aren't supported.</span></span>

<span data-ttu-id="95631-138">È consigliabile usare attributi contenenti valori compilati per tutti gli utenti dell'organizzazione e non usare attributi con valori lunghi.</span><span class="sxs-lookup"><span data-stu-id="95631-138">It's recommended that you use attributes that have values filled in for all users in your organization and don't use attributes that have longer values.</span></span>

### <a name="things-to-look-out-for"></a><span data-ttu-id="95631-139">Elementi di cui eseguire la ricerca</span><span class="sxs-lookup"><span data-stu-id="95631-139">Things to look out for</span></span>

- <span data-ttu-id="95631-140">Durante la creazione dei criteri, la lunghezza totale delle stringhe di prefisso e suffisso è limitata a 53 caratteri.</span><span class="sxs-lookup"><span data-stu-id="95631-140">During policy creation, the total prefixes and suffixes string length is restricted to 53 characters.</span></span>

- <span data-ttu-id="95631-p109">Prefissi e suffissi possono contenere caratteri speciali supportati nel nome e nell'alias del gruppo. Quando i prefissi e suffissi contengono caratteri speciali non consentiti nell'alias del gruppo, questi vengono rimossi e applicati all'alias del gruppo. In questo caso, quindi, i prefissi e suffissi applicati al nome del gruppo sarebbero diversi da quelli applicati all'alias del gruppo.</span><span class="sxs-lookup"><span data-stu-id="95631-p109">Prefixes and suffixes can contain special characters supported in group name and group alias. When the prefixes and suffixes contain special characters that are not allowed in the group alias, they are removed and applied to the group alias. So in this case, the prefixes and suffixes applied to group name would be different from the ones applied to the group alias.</span></span>

- <span data-ttu-id="95631-144">Se si utilizzano i gruppi connessi di Yammer Office 365, evitare di usare i seguenti caratteri nei criteri di denominazione: \#@ \[, \], \<,, \>e.</span><span class="sxs-lookup"><span data-stu-id="95631-144">If you are using Yammer Office 365 connected groups, avoid using the following characters in your naming policy: @, \#, \[, \], \<, and \>.</span></span> <span data-ttu-id="95631-145">Se questi caratteri sono inclusi nei criteri di denominazione, gli utenti di Yammer regolari non potranno creare gruppi.</span><span class="sxs-lookup"><span data-stu-id="95631-145">If these characters are in the naming policy, regular Yammer users will not be able to create groups.</span></span>

## <a name="custom-blocked-words"></a><span data-ttu-id="95631-146">Parole bloccate personalizzate</span><span class="sxs-lookup"><span data-stu-id="95631-146">Custom blocked words</span></span>

<span data-ttu-id="95631-147">È possibile immettere un elenco separato da virgole di parole bloccate che verranno bloccate nei nomi e negli alias di gruppo.</span><span class="sxs-lookup"><span data-stu-id="95631-147">You can enter a comma separated list of blocked words that will be blocked in group names and aliases.</span></span>

<span data-ttu-id="95631-148">Il controllo delle parole bloccate viene effettuato sul nome del gruppo immesso dall'utente.</span><span class="sxs-lookup"><span data-stu-id="95631-148">The blocked words check is done on the user entered group name.</span></span> <span data-ttu-id="95631-149">Pertanto, se l'utente immette ' darnit ' e\_' prefix ' è il criterio di denominazione\_,' prefix darnit ' avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="95631-149">So if user enters 'darnit' and 'Prefix\_' is the naming policy, 'Prefix\_darnit' will fail.</span></span>

<span data-ttu-id="95631-150">Non vengono eseguite ricerche in una stringa secondaria. in particolare, è necessaria una corrispondenza esatta tra il nome immesso dall'utente e le parole bloccate personalizzate per attivare un errore.</span><span class="sxs-lookup"><span data-stu-id="95631-150">No sub-string searches are carried out; specifically, an exact match between the user entered name and the custom blocked words is required to trigger a failure.</span></span> <span data-ttu-id="95631-151">La ricerca di sottostringhe non viene eseguita in modo che gli utenti possono usare parole normali come "rinculo" anche se "culo" è una parola bloccata.</span><span class="sxs-lookup"><span data-stu-id="95631-151">Sub-string search isn't done so that users can use some of the common words like 'Class' even if 'ass' is a blocked word.</span></span>

<span data-ttu-id="95631-152">**Aspetti da cercare**:</span><span class="sxs-lookup"><span data-stu-id="95631-152">**Things to look out for**:</span></span>

- <span data-ttu-id="95631-153">Per le parole bloccate non viene fatta distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="95631-153">The blocked words are case-insensitive.</span></span>

- <span data-ttu-id="95631-154">Quando si immette una parola bloccata, il client del gruppo mostrerà un messaggio di errore con la parola bloccata.</span><span class="sxs-lookup"><span data-stu-id="95631-154">When a user enters a blocked word, the group client will show an error message with the blocked word.</span></span>

- <span data-ttu-id="95631-155">Per le parole bloccate usate non sono previste limitazioni sul limite di caratteri.</span><span class="sxs-lookup"><span data-stu-id="95631-155">There are no character restrictions in the blocked words used.</span></span>

- <span data-ttu-id="95631-156">Vi è un limite superiore di 5000 parole che possono essere impostate come parole bloccate.</span><span class="sxs-lookup"><span data-stu-id="95631-156">There is an upper limit of 5000 words that can be set as blocked words.</span></span>

## <a name="admin-override"></a><span data-ttu-id="95631-157">Override per gli amministratori</span><span class="sxs-lookup"><span data-stu-id="95631-157">Admin override</span></span>

<span data-ttu-id="95631-p113">Alcuni amministratori non sono soggetti a questi criteri in tutti gli endpoint e i carichi di lavoro di gruppo, possono quindi creare gruppi con le parole bloccate e con le convenzioni di denominazione che preferiscono. L'elenco seguente contiene i ruoli di amministratore non soggetti ai criteri di denominazione del gruppo.</span><span class="sxs-lookup"><span data-stu-id="95631-p113">Selective administrators are exempted from these policies, across all group workloads and endpoints, so that they can create groups with these blocked words and with their desired naming conventions. The following are the list of administrator roles exempted from the group naming policy.</span></span>

- <span data-ttu-id="95631-160">Amministratore globale</span><span class="sxs-lookup"><span data-stu-id="95631-160">Global admin</span></span>

- <span data-ttu-id="95631-161">Supporto partner - Livello 1</span><span class="sxs-lookup"><span data-stu-id="95631-161">Partner Tier 1 Support</span></span>

- <span data-ttu-id="95631-162">Supporto partner - Livello 2</span><span class="sxs-lookup"><span data-stu-id="95631-162">Partner Tier 2 Support</span></span>

- <span data-ttu-id="95631-163">Amministratore degli account utente</span><span class="sxs-lookup"><span data-stu-id="95631-163">User account admin</span></span>

- <span data-ttu-id="95631-164">Ruoli con autorizzazioni di scrittura nella directory</span><span class="sxs-lookup"><span data-stu-id="95631-164">Directory writers</span></span>

## <a name="how-to-set-up-the-naming-policy"></a><span data-ttu-id="95631-165">Come configurare i criteri di denominazione</span><span class="sxs-lookup"><span data-stu-id="95631-165">How to set up the naming policy</span></span>

<span data-ttu-id="95631-166">Per impostare i criteri di denominazione:</span><span class="sxs-lookup"><span data-stu-id="95631-166">To set up a naming policy:</span></span>

1. <span data-ttu-id="95631-167">In [Azure Active Directory](https://aad.portal.azure.com), in **gestione**, fare clic su **gruppi**.</span><span class="sxs-lookup"><span data-stu-id="95631-167">In [Azure Active Directory](https://aad.portal.azure.com), under **Manage**, click **Groups**.</span></span>
2. <span data-ttu-id="95631-168">In **Impostazioni**fare clic su **criteri di denominazione**.</span><span class="sxs-lookup"><span data-stu-id="95631-168">Under **Settings**, click **Naming policy**.</span></span>
3. <span data-ttu-id="95631-169">Scegliere la scheda **criteri di denominazione dei gruppi** .</span><span class="sxs-lookup"><span data-stu-id="95631-169">Choose the **Group naming policy** tab.</span></span>
4. <span data-ttu-id="95631-170">In **criterio corrente**scegliere se si desidera richiedere un prefisso o un suffisso o entrambi, quindi selezionare le caselle di controllo appropriate.</span><span class="sxs-lookup"><span data-stu-id="95631-170">Under **Current policy**, choose if you want to require a prefix or suffix or both, and select the appropriate check boxes.</span></span>
5. <span data-ttu-id="95631-171">Scegliere tra l' **attributo** e la **stringa** per ogni riga e quindi specificare l'attributo o la stringa.</span><span class="sxs-lookup"><span data-stu-id="95631-171">Choose between **Attribute** and **String** for each line and then specify the attribute or string.</span></span>
6. <span data-ttu-id="95631-172">Dopo aver aggiunto i prefissi e i suffissi necessari, fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="95631-172">When you have added the prefixes and suffixes that you need, click **Save**.</span></span>

![Schermata delle impostazioni dei criteri di denominazione del gruppo in Azure Active Directory](../media/groups-naming-policy-azure.png)

## <a name="naming-policy-experiences-across-office-365-apps"></a><span data-ttu-id="95631-174">Esperienza dei criteri di denominazione nelle app di Office 365</span><span class="sxs-lookup"><span data-stu-id="95631-174">Naming policy experiences across Office 365 apps</span></span>

<span data-ttu-id="95631-p114">Le app di Office 365 sono state aggiornate in modo da mostrare un'anteprima del nome di gruppo in base ai criteri di denominazione (con prefissi e suffissi) quando un utente digita il nome e l'alias di gruppo. Quando l'utente immette parole bloccate visualizza un messaggio di errore e può rimuoverle.</span><span class="sxs-lookup"><span data-stu-id="95631-p114">The Office 365 apps have been updated to show a preview of the naming policy group name (with prefixes and suffixes) when the user types in the group name and alias. When the user enters blocked words, they'll see an error message so they can remove the blocked words.</span></span>

## <a name="outlook-on-the-web"></a><span data-ttu-id="95631-177">Outlook sul web</span><span class="sxs-lookup"><span data-stu-id="95631-177">Outlook on the web</span></span>

<span data-ttu-id="95631-178">Outlook sul Web (in precedenza noto come Outlook Web App o OWA) Visualizza il nome decorato dei criteri di denominazione quando l'utente digita un nome di gruppo o un alias di gruppo.</span><span class="sxs-lookup"><span data-stu-id="95631-178">Outlook on the web (formerly known as Outlook Web App or OWA) shows the naming policy decorated name when the user types a group name or group alias.</span></span> <span data-ttu-id="95631-179">Quando un utente immette una parola bloccata personalizzata, nell'interfaccia utente viene visualizzato un messaggio di errore insieme alla parola, in modo che l'utente possa rimuoverla.</span><span class="sxs-lookup"><span data-stu-id="95631-179">When an user enters a custom blocked word, an error message is shown in the UI along with the blocked word so that the user can remove it.</span></span> <span data-ttu-id="95631-180">Di seguito sono illustrati gli snapshot di Outlook sul Web.</span><span class="sxs-lookup"><span data-stu-id="95631-180">Outlook on the web experience snapshots are shown below.</span></span>

![Visualizzazione affiancata dei criteri di denominazione del gruppo nei gruppi di Office 365](../media/1a21657a-c542-4d9e-ac7d-887ac542a9d9.png)

## <a name="outlook-desktop"></a><span data-ttu-id="95631-182">Outlook desktop</span><span class="sxs-lookup"><span data-stu-id="95631-182">Outlook Desktop</span></span>

<span data-ttu-id="95631-183">I gruppi creati in Outlook desktop sono conformi ai criteri di denominazione.</span><span class="sxs-lookup"><span data-stu-id="95631-183">Groups created in Outlook desktop are compliant with naming policy.</span></span> <span data-ttu-id="95631-184">L'app desktop Outlook non mostra ancora l'anteprima dei criteri di denominazione e non restituisce errori relativi alle parole bloccate personalizzate quando l'utente immette il nome del gruppo.</span><span class="sxs-lookup"><span data-stu-id="95631-184">Outlook desktop app doesn't yet show the preview of the naming policy and doesn't return the custom blocked word errors, when the user enters the group name.</span></span> <span data-ttu-id="95631-185">Tuttavia, i criteri di denominazione verranno applicati automaticamente alla selezione di creazione/modifica e gli utenti verranno presentati con errori se sono presenti parole bloccate personalizzate nel nome o nell'alias del gruppo.</span><span class="sxs-lookup"><span data-stu-id="95631-185">However, naming policy will be automatically applied on selecting create/edit and users will be presented with errors if there are custom blocked words in the group name or alias.</span></span>

## <a name="microsoft-teams"></a><span data-ttu-id="95631-186">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="95631-186">Microsoft Teams</span></span>

<span data-ttu-id="95631-187">Microsoft teams Visualizza il nome decorato dei criteri di denominazione quando l'utente digita il nome di un team.</span><span class="sxs-lookup"><span data-stu-id="95631-187">Microsoft Teams shows the naming policy decorated name when the user types a team name.</span></span> <span data-ttu-id="95631-188">Quando un utente immette una parola bloccata personalizzata, viene visualizzato un messaggio di errore insieme alla parola bloccata in modo che l'utente possa rimuoverla.</span><span class="sxs-lookup"><span data-stu-id="95631-188">When a user enters a custom blocked word, an error message is shown along with the blocked word so that the user can remove it.</span></span>

![Esempio di criteri di denominazione dei gruppi in Microsoft teams bloccato](../media/7c904546-5853-4642-949a-a55dbb004eca.png)

## <a name="sharepoint"></a><span data-ttu-id="95631-190">SharePoint</span><span class="sxs-lookup"><span data-stu-id="95631-190">SharePoint</span></span>

<span data-ttu-id="95631-191">SharePoint Visualizza il nome dei criteri di denominazione quando l'utente digita un nome di sito o un indirizzo di posta elettronica di gruppo.</span><span class="sxs-lookup"><span data-stu-id="95631-191">SharePoint shows the naming policy name when the user types a site name or group email address.</span></span> <span data-ttu-id="95631-192">Quando un utente immette una parola bloccata personalizzata, viene visualizzato un messaggio di errore insieme alla parola, in modo che l'utente possa rimuoverla.</span><span class="sxs-lookup"><span data-stu-id="95631-192">When an user enters a custom blocked word, an error message is shown, along with the blocked word so that the user can remove it.</span></span>

![Criteri di denominazione dei gruppi-nome bloccato del sito di SharePoint](../media/cf0d6158-fd32-4a93-ac24-2e037102c42c.png)

## <a name="microsoft-stream"></a><span data-ttu-id="95631-194">Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="95631-194">Microsoft Stream</span></span>

<span data-ttu-id="95631-p119">Microsoft Stream mostra il nome decorato dei criteri di denominazione quando l'utente digita il nome o l'alias di posta elettronica di un gruppo. Quando un utente immette una parola bloccata personalizzata, viene visualizzato un messaggio di errore con la parola, in modo che l'utente possa rimuoverla.</span><span class="sxs-lookup"><span data-stu-id="95631-p119">Microsoft Stream shows the naming policy decorated name when the user types a group name or group email alias. When an user enters a custom blocked word, an error message is shown with the blocked word so the user can remove it.</span></span>

![Esempio di criteri di denominazione dei gruppi bloccati per Microsoft Stream](../media/9748f52a-3814-41a6-9ac1-4e8cd4c91011.png)

## <a name="outlook-ios-and-android-app"></a><span data-ttu-id="95631-198">App Outlook per iOS e Android</span><span class="sxs-lookup"><span data-stu-id="95631-198">Outlook iOS and Android App</span></span>

<span data-ttu-id="95631-199">I gruppi creati nelle app Outlook sono conformi ai criteri di denominazione.</span><span class="sxs-lookup"><span data-stu-id="95631-199">Groups created in Outlook apps are compliant with naming policy.</span></span> <span data-ttu-id="95631-200">Outlook Mobile Visualizza l'anteprima dei criteri di denominazione quando si immette il nome del gruppo.</span><span class="sxs-lookup"><span data-stu-id="95631-200">Outlook mobile shows the naming policy preview when entering the Group name.</span></span> <span data-ttu-id="95631-201">Quando un utente immette una parola bloccata personalizzata, viene visualizzato un messaggio di errore per la creazione del gruppo, in modo che l'utente possa rimuovere la parola bloccata.</span><span class="sxs-lookup"><span data-stu-id="95631-201">When a user enters a custom blocked word, an error message is shown on creating the group, so the user can remove the blocked word.</span></span>

## <a name="planner"></a><span data-ttu-id="95631-202">Planner</span><span class="sxs-lookup"><span data-stu-id="95631-202">Planner</span></span>

<span data-ttu-id="95631-203">Planner è conforme ai criteri di denominazione.</span><span class="sxs-lookup"><span data-stu-id="95631-203">Planner is compliant with naming policy.</span></span> <span data-ttu-id="95631-204">Planner Visualizza l'anteprima dei criteri di denominazione quando si immette il nome del piano.</span><span class="sxs-lookup"><span data-stu-id="95631-204">Planner shows the naming policy preview when entering the Plan name.</span></span> <span data-ttu-id="95631-205">Quando un utente immette una parola bloccata personalizzata, viene visualizzato un messaggio di errore per la creazione del piano, in modo che l'utente possa rimuovere la parola bloccata.</span><span class="sxs-lookup"><span data-stu-id="95631-205">When a user enters a custom blocked word, an error message is shown on creating the plan, so the user can remove the blocked word.</span></span>

![Criteri di denominazione dei gruppi-esempio di creazione di un nuovo piano bloccato](../media/ea692b44-3a56-4e6d-bcb8-8444fe5bbc4f.png)

## <a name="dynamics-365-for-customer-engagement"></a><span data-ttu-id="95631-207">Dynamics 365 per l'impegno dei clienti</span><span class="sxs-lookup"><span data-stu-id="95631-207">Dynamics 365 for Customer Engagement</span></span>

<span data-ttu-id="95631-208">Dynamics 365 per l'impegno dei clienti è conforme ai criteri di denominazione.</span><span class="sxs-lookup"><span data-stu-id="95631-208">Dynamics 365 for Customer Engagement is compliant with naming policy.</span></span> <span data-ttu-id="95631-209">Dynamics 365 Visualizza il nome decorato dei criteri di denominazione quando l'utente digita un nome di gruppo o un alias di posta elettronica di gruppo.</span><span class="sxs-lookup"><span data-stu-id="95631-209">Dynamics 365 shows the naming policy decorated name when the user types a group name or group email alias.</span></span> <span data-ttu-id="95631-210">Quando l'utente immette una parola bloccata personalizzata, viene visualizzato un messaggio di errore con la parola bloccata in modo che l'utente possa rimuoverla.</span><span class="sxs-lookup"><span data-stu-id="95631-210">When the user enters a custom blocked word, an error message is shown with the blocked word so the user can remove it.</span></span>

![Dynamics 365](../media/8190331c-6779-42bd-a6b3-f7007428c8ae.png)

## <a name="school-data-sync-sds"></a><span data-ttu-id="95631-212">School Data Sync (SDS)</span><span class="sxs-lookup"><span data-stu-id="95631-212">School Data Sync (SDS)</span></span>

<span data-ttu-id="95631-p123">I gruppi creati tramite SDS sono conformi ai criteri di denominazione, ma i criteri non vengono applicati automaticamente. Gli amministratori di SDS devono aggiungere i prefissi e suffissi ai nomi delle classi per cui occorre creare gruppi e quindi caricarli in SDS. In caso contrario, la creazione o modifica di gruppi avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="95631-p123">Groups created through SDS comply with naming policy, but the naming policy isn't applied automatically. SDS administrators have to append the prefixes and suffixes to class names for which groups need to be created and then upload to SDS. Groups creation/edit would fail otherwise.</span></span>

## <a name="outlook-customer-manager-ocm"></a><span data-ttu-id="95631-216">Gestione dei clienti di Outlook (OCM)</span><span class="sxs-lookup"><span data-stu-id="95631-216">Outlook Customer Manager (OCM)</span></span>

<span data-ttu-id="95631-217">Outlook Customer Manager è conforme ai criteri di denominazione.</span><span class="sxs-lookup"><span data-stu-id="95631-217">Outlook Customer Manager is compliant with naming policy.</span></span> <span data-ttu-id="95631-218">I criteri di denominazione vengono applicati automaticamente al gruppo creato in gestione clienti di Outlook.</span><span class="sxs-lookup"><span data-stu-id="95631-218">The naming policy gets automatically applied to the group created in Outlook Customer Manager.</span></span> <span data-ttu-id="95631-219">Se una qualsiasi delle parole all'interno di "All Sales Team" è definita come una parola bloccata personalizzata, la creazione del gruppo in OCM verrà bloccata.</span><span class="sxs-lookup"><span data-stu-id="95631-219">If any of the words within "All Sales Team" is defined as a custom blocked word, the group creation in OCM will be blocked.</span></span> <span data-ttu-id="95631-220">L'utente non sarà in grado di creare il gruppo OCM e verrà bloccato utilizzando l'app OCM. "</span><span class="sxs-lookup"><span data-stu-id="95631-220">The user will not be able to create the OCM group and will be blocked from using the OCM app."</span></span>

## <a name="classroom-app"></a><span data-ttu-id="95631-221">App Classroom</span><span class="sxs-lookup"><span data-stu-id="95631-221">Classroom App</span></span>

<span data-ttu-id="95631-p125">I gruppi creati nell'app Classroom sono compatibili con i criteri di denominazione, ma i criteri non vengono applicati automaticamente e non viene mostrata un'anteprima dei criteri di denominazione quando gli utenti inseriscono il nome di un gruppo di classe. Gli utenti devono quindi immettere il nome decorato del gruppo di classe con prefissi e suffissi. In caso contrario, la creazione o modifica del gruppo di classe avrà esito negativo con errori.</span><span class="sxs-lookup"><span data-stu-id="95631-p125">Groups created in classroom app comply with naming policy, but the naming policy isn't applied automatically, and the naming policy preview isn't shown to the users while entering a classroom group name. So users would have to enter the decorated classroom group name with prefixes and suffixes. Otherwise the classroom group create or edit will fail with errors.</span></span>

## <a name="power-bi"></a><span data-ttu-id="95631-225">Power BI</span><span class="sxs-lookup"><span data-stu-id="95631-225">Power BI</span></span>

<span data-ttu-id="95631-226">I gruppi creati nelle aree di lavoro di Power BI sono conformi ai criteri di denominazione, ma il criterio di denominazione non viene applicato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="95631-226">Groups created in Power BI workspaces comply with the naming policy, but the naming policy isn't applied automatically.</span></span> <span data-ttu-id="95631-227">L'anteprima dei criteri di denominazione non viene visualizzata agli utenti quando si immette un nome dell'area di lavoro di Power BI.</span><span class="sxs-lookup"><span data-stu-id="95631-227">And, the naming policy preview isn't shown to users when they enter a Power BI workspace name.</span></span>

<span data-ttu-id="95631-228">Il nome consigliato, con il criterio di denominazione applicato, viene visualizzato nei dettagli dell'errore su Crea o modifica aree di lavoro.</span><span class="sxs-lookup"><span data-stu-id="95631-228">The recommended name - with the naming policy applied - is shown in the error details on create or edit workspaces.</span></span> <span data-ttu-id="95631-229">Questo significa che gli utenti devono immettere il nome dell'area di lavoro decorata con prefissi e suffissi.</span><span class="sxs-lookup"><span data-stu-id="95631-229">This means users have to enter the decorated workspace name with prefixes and suffixes.</span></span> <span data-ttu-id="95631-230">In caso contrario, l'area di lavoro creare o modificare avrà esito negativo con errori.</span><span class="sxs-lookup"><span data-stu-id="95631-230">Otherwise the workspace create or edit will fail with errors.</span></span>

## <a name="yammer"></a><span data-ttu-id="95631-231">Yammer</span><span class="sxs-lookup"><span data-stu-id="95631-231">Yammer</span></span>

<span data-ttu-id="95631-232">Quando un utente ha eseguito l'accesso a Yammer con il proprio account di Azure Active Directory crea un gruppo o modifica un nome di gruppo, il nome del gruppo sarà conforme ai criteri di denominazione.</span><span class="sxs-lookup"><span data-stu-id="95631-232">When a user signed in to Yammer with their Azure Active Directory account creates a group or edits a group name, the group name will comply with naming policy.</span></span> <span data-ttu-id="95631-233">Ciò vale sia per i gruppi di Office 365 connessi che per tutti gli altri gruppi di Yammer.</span><span class="sxs-lookup"><span data-stu-id="95631-233">This applies both to Office 365 connected groups and all other Yammer groups.</span></span>

<span data-ttu-id="95631-234">Se è stato creato un gruppo di Office 365 connesso prima che il criterio di denominazione sia sul posto, il nome del gruppo non seguirà automaticamente i criteri di denominazione.</span><span class="sxs-lookup"><span data-stu-id="95631-234">If an Office 365 connected group was created before the naming policy is in place, the group name will not automatically follow the naming policies.</span></span> <span data-ttu-id="95631-235">Quando un utente modifica il nome del gruppo, viene richiesto di aggiungere il prefisso e il suffisso.</span><span class="sxs-lookup"><span data-stu-id="95631-235">When a user edits the group name, they will be prompted to add the prefix and suffix.</span></span>

<span data-ttu-id="95631-236">Se i criteri di denominazione includono caratteri che non possono essere inclusi nei nomi dei gruppi di Yammer, solo gli amministratori saranno in grado di creare un gruppo connesso in Yammer.</span><span class="sxs-lookup"><span data-stu-id="95631-236">If the naming policy includes characters that can't be in Yammer group names, only admins will be able to create a connected group in Yammer.</span></span>

## <a name="staffhub"></a><span data-ttu-id="95631-237">StaffHub</span><span class="sxs-lookup"><span data-stu-id="95631-237">StaffHub</span></span>

<span data-ttu-id="95631-238">I team di StaffHub non seguono i criteri di denominazione, ma il gruppo di Office 365 sottostante.</span><span class="sxs-lookup"><span data-stu-id="95631-238">StaffHub teams do not follow the naming policy, but the underlying Office 365 group does.</span></span> <span data-ttu-id="95631-239">Al nome del team StaffHub non si applicano prefissi e suffissi e le parole bloccate personalizzate non vengono controllate.</span><span class="sxs-lookup"><span data-stu-id="95631-239">StaffHub team name does not apply the prefixes and suffixes and does not check for custom blocked words.</span></span> <span data-ttu-id="95631-240">Tuttavia, StaffHub applica i prefissi e i suffissi e rimuove le parole bloccate dal gruppo di Office 365 sottostante.</span><span class="sxs-lookup"><span data-stu-id="95631-240">But StaffHub does apply the prefixes and suffixes and removes blocked words from the underlying Office 365 group.</span></span>

## <a name="exchange-powershell"></a><span data-ttu-id="95631-241">PowerShell di Exchange</span><span class="sxs-lookup"><span data-stu-id="95631-241">Exchange PowerShell</span></span>

<span data-ttu-id="95631-p131">I cmdlet di Exchange PowerShell sono conformi ai criteri di denominazione. Se nei nomi e negli alias di gruppo non viene seguita la convenzione di denominazione, gli utenti ricevono messaggi di errore con i suffissi e prefissi suggeriti e per le parole bloccate personalizzate.</span><span class="sxs-lookup"><span data-stu-id="95631-p131">Exchange PowerShell cmdlets are compliant with naming policy. Users will get appropriate error messages with suggested prefixes and suffixes and for custom blocked words if naming convention isn't used in the group names and group alias.</span></span>

## <a name="azure-active-directory-powershell-cmdlets"></a><span data-ttu-id="95631-244">Cmdlet di Azure Active Directory PowerShell</span><span class="sxs-lookup"><span data-stu-id="95631-244">Azure Active Directory PowerShell cmdlets</span></span>

<span data-ttu-id="95631-245">I cmdlet di Azure Active Directory PowerShell sono conformi ai criteri di denominazione.</span><span class="sxs-lookup"><span data-stu-id="95631-245">Azure Active Directory PowerShell cmdlets are compliant with naming policy.</span></span> <span data-ttu-id="95631-246">Se nei nomi e negli alias di gruppo non viene seguita la convenzione di denominazione, gli utenti ricevono messaggi di errore con i suffissi e prefissi suggeriti e per le parole bloccate personalizzate.</span><span class="sxs-lookup"><span data-stu-id="95631-246">Users will get appropriate error messages with suggested prefixes and suffixes and for custom blocked words if naming convention isn't used in the group names and group alias.</span></span>

## <a name="exchange-admin-center"></a><span data-ttu-id="95631-247">Interfaccia di amministrazione di Exchange</span><span class="sxs-lookup"><span data-stu-id="95631-247">Exchange admin center</span></span>

<span data-ttu-id="95631-248">L'interfaccia di amministrazione di Exchange (EAC) è conforme ai criteri di denominazione.</span><span class="sxs-lookup"><span data-stu-id="95631-248">The Exchange admin center (EAC) is compliant with naming policy.</span></span> <span data-ttu-id="95631-249">Durante le azioni di creazione e modifica, se nei nomi e negli alias di gruppo non viene seguita la convenzione di denominazione, gli utenti ricevono messaggi di errore con i suffissi e prefissi suggeriti e per le parole bloccate personalizzate.</span><span class="sxs-lookup"><span data-stu-id="95631-249">On create or edit actions, users will get appropriate error messages with suggested prefixes and suffixes and for custom blocked words if naming convention isn't used in the group names and group alias.</span></span>

## <a name="microsoft-365-admin-center"></a><span data-ttu-id="95631-250">Interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="95631-250">Microsoft 365 admin center</span></span>

<span data-ttu-id="95631-251">L'interfaccia di amministrazione di Microsoft 365 è conforme ai criteri di denominazione.</span><span class="sxs-lookup"><span data-stu-id="95631-251">The Microsoft 365 admin center is compliant with naming policy.</span></span> <span data-ttu-id="95631-252">Durante le azioni di creazione e modifica, i criteri di denominazione vengono applicati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="95631-252">On create or edit actions, naming policy will automatically get applied.</span></span> <span data-ttu-id="95631-253">Se gli utenti immettono parole bloccate personalizzate, ricevono errori appropriati.</span><span class="sxs-lookup"><span data-stu-id="95631-253">Users will get appropriate errors when they enter custom blocked words.</span></span> <span data-ttu-id="95631-254">L'interfaccia di amministrazione di Microsoft 365 non mostra ancora l'anteprima dei criteri di denominazione e non restituisce gli errori di Word bloccati personalizzati, quando l'utente immette il nome del gruppo.</span><span class="sxs-lookup"><span data-stu-id="95631-254">The Microsoft 365 admin center doesn't yet show the preview of the naming policy and doesn't return the custom blocked word errors, when the user enters the group name.</span></span>

## <a name="azure-active-directory-portal"></a><span data-ttu-id="95631-255">Portale di Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="95631-255">Azure Active Directory portal</span></span>

<span data-ttu-id="95631-256">Il portale di Azure Active Directory è conforme ai criteri di denominazione.</span><span class="sxs-lookup"><span data-stu-id="95631-256">The Azure Active Directory portal is compliant with naming policy.</span></span> <span data-ttu-id="95631-257">Il portale di Azure Active Directory Visualizza l'anteprima dei criteri di denominazione quando si immette il nome del gruppo.</span><span class="sxs-lookup"><span data-stu-id="95631-257">Azure Active Directory portal shows the naming policy preview when entering the Group name.</span></span> <span data-ttu-id="95631-258">Quando un utente immette una parola bloccata personalizzata, viene visualizzato un messaggio di errore per la creazione del gruppo, in modo che l'utente possa rimuovere la parola bloccata.</span><span class="sxs-lookup"><span data-stu-id="95631-258">When a user enters a custom blocked word, an error message is shown on creating the group, so the user can remove the blocked word.</span></span>

## <a name="more-articles-on-naming-policy"></a><span data-ttu-id="95631-259">Altri articoli sui criteri di denominazione</span><span class="sxs-lookup"><span data-stu-id="95631-259">More articles on naming policy</span></span>

[<span data-ttu-id="95631-260">Applicazione di un criterio di denominazione per i gruppi di Office 365 in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="95631-260">Enforce a naming policy for Office 365 groups in Azure Active Directory</span></span>](https://go.microsoft.com/fwlink/?linkid=868340)

[<span data-ttu-id="95631-261">Cmdlet di Azure Active Directory per la configurazione delle impostazioni di gruppo</span><span class="sxs-lookup"><span data-stu-id="95631-261">Azure Active Directory cmdlets for configuring group settings</span></span>](https://go.microsoft.com/fwlink/?linkid=868341)
