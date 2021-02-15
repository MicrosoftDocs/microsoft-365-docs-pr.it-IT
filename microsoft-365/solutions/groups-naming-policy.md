---
title: Criteri di denominazione dei gruppi di Microsoft 365
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- m365solution-collabgovernance
search.appverid:
- MET150
ms.assetid: 6ceca4d3-cad1-4532-9f0f-d469dfbbb552
description: Informazioni su come creare criteri di denominazione per i gruppi di Microsoft 365.
ms.openlocfilehash: acf660375508760bd2e9874a07454709849929b0
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/06/2021
ms.locfileid: "49759825"
---
# <a name="microsoft-365-groups-naming-policy"></a><span data-ttu-id="0d654-103">Criteri di denominazione dei gruppi di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0d654-103">Microsoft 365 groups naming policy</span></span>

<span data-ttu-id="0d654-104">È possibile utilizzare i criteri di denominazione dei gruppi per applicare una strategia di denominazione coerente per i gruppi creati dagli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="0d654-104">You can use a group naming policy to enforce a consistent naming strategy for groups created by users in your organization.</span></span> <span data-ttu-id="0d654-105">I criteri di denominazione consentono all'utente e agli utenti di identificare la funzione del gruppo, dell'appartenenza, dell'area geografica o dell'utente che ha creato il gruppo.</span><span class="sxs-lookup"><span data-stu-id="0d654-105">A naming policy can help you and your users identify the function of the group, membership, geographic region, or who created the group.</span></span> <span data-ttu-id="0d654-106">I criteri di denominazione consentono inoltre di categorizzare i gruppi nella rubrica.</span><span class="sxs-lookup"><span data-stu-id="0d654-106">The naming policy can also help categorize groups in the address book.</span></span> <span data-ttu-id="0d654-107">È possibile utilizzare il criterio per impedire l'utilizzo di parole specifiche nei nomi di gruppo e negli alias.</span><span class="sxs-lookup"><span data-stu-id="0d654-107">You can use the policy to block specific words from being used in group names and aliases.</span></span>

<span data-ttu-id="0d654-108">I criteri di denominazione vengono applicati ai gruppi creati in tutti i carichi di lavoro dei gruppi (ad esempio Outlook, Microsoft Teams, SharePoint, Planner, Yammer e così via).</span><span class="sxs-lookup"><span data-stu-id="0d654-108">The naming policy is applied to groups that are created across all groups workloads (like Outlook, Microsoft Teams, SharePoint, Planner, Yammer, etc.).</span></span> <span data-ttu-id="0d654-109">Viene applicato sia al nome del gruppo che all'alias del gruppo.</span><span class="sxs-lookup"><span data-stu-id="0d654-109">It gets applied to both the group name and group alias.</span></span> <span data-ttu-id="0d654-110">Viene inoltre applicato quando un utente crea un gruppo e quando il nome, l'alias, la descrizione o l'avatar del gruppo viene modificato per un gruppo esistente.</span><span class="sxs-lookup"><span data-stu-id="0d654-110">It also gets applied when a user creates a group and when the group name, alias, description, or avatar is edited for an existing group.</span></span>

> [!TIP]
> <span data-ttu-id="0d654-111">I criteri di denominazione dei gruppi di Microsoft 365 si applicano solo ai gruppi di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0d654-111">A Microsoft 365 group naming policy only applies to Microsoft 365 groups.</span></span> <span data-ttu-id="0d654-112">Non si applica ai gruppi di distribuzione creati in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="0d654-112">It doesn't apply to distribution groups created in Exchange Online.</span></span> <span data-ttu-id="0d654-113">Per creare un criterio di denominazione per i gruppi di distribuzione, vedere [Creare un criterio di denominazione dei gruppi di distribuzione.](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/create-group-naming-policy)</span><span class="sxs-lookup"><span data-stu-id="0d654-113">To create a naming policy for distribution groups, see [Create a distribution group naming policy](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/create-group-naming-policy).</span></span>

<span data-ttu-id="0d654-114">I criteri di denominazione del gruppo sono composti dalle funzionalità seguenti:</span><span class="sxs-lookup"><span data-stu-id="0d654-114">The group naming policy consists of the following features:</span></span>

- <span data-ttu-id="0d654-115">**Criterio di denominazione prefisso-suffisso:** è possibile utilizzare prefissi o suffissi per definire la convenzione di denominazione dei gruppi (ad esempio: "US \_ My Group \_ Engineering").</span><span class="sxs-lookup"><span data-stu-id="0d654-115">**Prefix-Suffix naming policy**: You can use prefixes or suffixes to define the naming convention of groups (for example: "US\_My Group\_Engineering").</span></span> <span data-ttu-id="0d654-116">I prefissi o suffissi possono essere stringhe fisse o attributi utente come [Department] che verranno sostituiti in base all'utente che crea il gruppo.</span><span class="sxs-lookup"><span data-stu-id="0d654-116">The prefixes/suffixes can either be fixed strings or user attributes like [Department] that will get substituted based on the user who is creating the group.</span></span>

- <span data-ttu-id="0d654-117">**Parole bloccate personalizzate:** è possibile caricare un set di parole bloccate specifiche per l'organizzazione che verrebbero bloccate nei gruppi creati dagli utenti.</span><span class="sxs-lookup"><span data-stu-id="0d654-117">**Custom Blocked Words**: You can upload a set of blocked words specific to your organization that would be blocked in groups created by users.</span></span> <span data-ttu-id="0d654-118">Ad esempio: ""CEO, Payroll, HR" (CEO, Buste paga, RU)".</span><span class="sxs-lookup"><span data-stu-id="0d654-118">(For example: "CEO, Payroll, HR").</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="0d654-119">Requisiti per la licenza</span><span class="sxs-lookup"><span data-stu-id="0d654-119">Licensing requirements</span></span>

<span data-ttu-id="0d654-120">L'uso dei criteri di denominazione di Azure AD per i gruppi di Microsoft 365 richiede che tu possieda, ma non necessariamente assegni una licenza Azure Active Directory Premium P1 o una licenza EDU di base di Azure AD per ogni utente univoco (inclusi gli utenti guest) membro di uno o più gruppi di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0d654-120">Using Azure AD naming policy for Microsoft 365 Groups requires that you possess but not necessarily assign an Azure Active Directory Premium P1 license or Azure AD Basic EDU license for each unique user (including guests) that is a member of one or more Microsoft 365 groups.</span></span>

<span data-ttu-id="0d654-121">Questa operazione è necessaria anche per l'amministratore che crea i criteri di denominazione dei gruppi.</span><span class="sxs-lookup"><span data-stu-id="0d654-121">This is also required for the administrator that creates the groups naming policy.</span></span>

## <a name="prefix-suffix-naming-policy"></a><span data-ttu-id="0d654-122">Prefix-Suffix di denominazione</span><span class="sxs-lookup"><span data-stu-id="0d654-122">Prefix-Suffix naming policy</span></span>

<span data-ttu-id="0d654-123">I prefissi e i suffissi possono essere stringhe fisse o attributi utente.</span><span class="sxs-lookup"><span data-stu-id="0d654-123">Prefixes and suffixes can either be fixed strings or user attributes.</span></span>

### <a name="fixed-strings"></a><span data-ttu-id="0d654-124">Stringhe fisse</span><span class="sxs-lookup"><span data-stu-id="0d654-124">Fixed strings</span></span>

<span data-ttu-id="0d654-125">È possibile utilizzare stringhe brevi che consentono di distinguere i gruppi nell'elenco indirizzi globale e lo spostamento a sinistra dei carichi di lavoro del gruppo.</span><span class="sxs-lookup"><span data-stu-id="0d654-125">You can use short strings that can help you differentiate groups in the GAL and left navigation of the group workloads.</span></span> <span data-ttu-id="0d654-126">Alcuni dei suffissi prefissi comuni sono parole chiave come "Grp \_ Name", \# "Name", \_ "Name"</span><span class="sxs-lookup"><span data-stu-id="0d654-126">Some of the common prefixes suffixes are keywords like 'Grp\_Name' , '\#Name', '\_Name'</span></span>

### <a name="attributes"></a><span data-ttu-id="0d654-127">Attributi</span><span class="sxs-lookup"><span data-stu-id="0d654-127">Attributes</span></span>

<span data-ttu-id="0d654-128">È possibile utilizzare attributi che consentono di identificare chi ha creato il gruppo come [Reparto] e da dove è stato creato, ad esempio [Paese].</span><span class="sxs-lookup"><span data-stu-id="0d654-128">You can use attributes that can help identify who created the group like [Department] and where it was created from like [Country].</span></span>

<span data-ttu-id="0d654-129">Esempi:</span><span class="sxs-lookup"><span data-stu-id="0d654-129">Examples:</span></span>

- <span data-ttu-id="0d654-130">Criterio = "GRP [GroupName] [Department]"</span><span class="sxs-lookup"><span data-stu-id="0d654-130">Policy = "GRP [GroupName] [Department]"</span></span>
- <span data-ttu-id="0d654-131">Reparto dell'utente = Progettazione</span><span class="sxs-lookup"><span data-stu-id="0d654-131">User's department = Engineering</span></span>
- <span data-ttu-id="0d654-132">Nome del gruppo creato = "GRP Mio gruppo Progettazione"</span><span class="sxs-lookup"><span data-stu-id="0d654-132">Created group name = "GRP My Group Engineering"</span></span>

<span data-ttu-id="0d654-133">Gli attributi di Azure Active Directory (Azure AD) supportati sono [Department], [Company], [Office], [StateOrProvince], [CountryOrRegion] e [Title].</span><span class="sxs-lookup"><span data-stu-id="0d654-133">Supported Azure Active Directory (Azure AD) attributes are [Department], [Company], [Office], [StateOrProvince], [CountryOrRegion], and [Title].</span></span>

- <span data-ttu-id="0d654-134">Gli attributi utente non supportati vengono considerati come stringhe fisse, ad esempio [postalCode].</span><span class="sxs-lookup"><span data-stu-id="0d654-134">Unsupported user attributes are considered as fixed strings, for example [postalCode].</span></span>

- <span data-ttu-id="0d654-135">Gli attributi di estensione e gli attributi personalizzati non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="0d654-135">Extension attributes and custom attributes aren't supported.</span></span>

<span data-ttu-id="0d654-136">È consigliabile usare attributi contenenti valori compilati per tutti gli utenti dell'organizzazione e non usare attributi con valori lunghi.</span><span class="sxs-lookup"><span data-stu-id="0d654-136">It's recommended that you use attributes that have values filled in for all users in your organization and don't use attributes that have longer values.</span></span>

### <a name="things-to-look-out-for"></a><span data-ttu-id="0d654-137">Aspetti da cercare</span><span class="sxs-lookup"><span data-stu-id="0d654-137">Things to look out for</span></span>

- <span data-ttu-id="0d654-138">Durante la creazione dei criteri, la lunghezza totale delle stringhe di prefisso e suffisso è limitata a 53 caratteri.</span><span class="sxs-lookup"><span data-stu-id="0d654-138">During policy creation, the total prefixes and suffixes string length is restricted to 53 characters.</span></span>

- <span data-ttu-id="0d654-139">Prefissi e suffissi possono contenere caratteri speciali supportati nel nome e nell'alias del gruppo.</span><span class="sxs-lookup"><span data-stu-id="0d654-139">Prefixes and suffixes can contain special characters supported in group name and group alias.</span></span> <span data-ttu-id="0d654-140">Quando i prefissi e i suffissi contengono caratteri speciali non consentiti nell'alias di gruppo, vengono applicati solo al nome del gruppo.</span><span class="sxs-lookup"><span data-stu-id="0d654-140">When the prefixes and suffixes contain special characters that are not allowed in the group alias, they are only applied to the group name.</span></span> <span data-ttu-id="0d654-141">In questo caso, quindi, i prefissi e suffissi applicati al nome del gruppo sarebbero diversi da quelli applicati all'alias del gruppo.</span><span class="sxs-lookup"><span data-stu-id="0d654-141">So in this case, the prefixes and suffixes applied to group name would be different from the ones applied to the group alias.</span></span>

  > [!NOTE]
  > <span data-ttu-id="0d654-142">Un punto (.) o un trattino (-) è consentito in qualsiasi punto del nome del gruppo, tranne all'inizio o alla fine del nome.</span><span class="sxs-lookup"><span data-stu-id="0d654-142">A period (.) or a hyphen (-) is permitted anywhere in the group name, except at the beginning or end of the name.</span></span> <span data-ttu-id="0d654-143">Un carattere di sottolineatura (_) è consentito in qualsiasi punto del nome del gruppo, incluso all'inizio o alla fine del nome.</span><span class="sxs-lookup"><span data-stu-id="0d654-143">An underscore (_) is permitted anywhere in the group name, including at the beginning or end of the name.</span></span>

- <span data-ttu-id="0d654-144">Se si usano i gruppi connessi a Yammer Office 365, evitare di utilizzare i caratteri seguenti nei criteri di denominazione: @, \# \[ , , , \] \<, and \> .</span><span class="sxs-lookup"><span data-stu-id="0d654-144">If you are using Yammer Office 365 connected groups, avoid using the following characters in your naming policy: @, \#, \[, \], \<, and \>.</span></span> <span data-ttu-id="0d654-145">Se questi caratteri sono nel criterio di denominazione, gli utenti regolari di Yammer non saranno in grado di creare gruppi.</span><span class="sxs-lookup"><span data-stu-id="0d654-145">If these characters are in the naming policy, regular Yammer users will not be able to create groups.</span></span>

> [!Tip]
> - <span data-ttu-id="0d654-146">Usa stringhe brevi come suffisso.</span><span class="sxs-lookup"><span data-stu-id="0d654-146">Use short strings as suffix.</span></span>
> - <span data-ttu-id="0d654-147">Utilizzare gli attributi con i valori.</span><span class="sxs-lookup"><span data-stu-id="0d654-147">Use attributes with values.</span></span>
> - <span data-ttu-id="0d654-148">Non essere troppo creativo, la lunghezza totale del nome ha un massimo di 264 caratteri.</span><span class="sxs-lookup"><span data-stu-id="0d654-148">Don't be too creative, total name length has a maximum of 264 characters.</span></span>
> - <span data-ttu-id="0d654-149">Caricare parole bloccate specifiche dell'organizzazione per limitare l'utilizzo.</span><span class="sxs-lookup"><span data-stu-id="0d654-149">Upload your organization specific blocked words to restrict usage.</span></span>

## <a name="custom-blocked-words"></a><span data-ttu-id="0d654-150">Parole bloccate personalizzate</span><span class="sxs-lookup"><span data-stu-id="0d654-150">Custom blocked words</span></span>

<span data-ttu-id="0d654-151">È possibile immettere un elenco delimitato da virgole di parole bloccate che verranno bloccate nei nomi di gruppo e negli alias.</span><span class="sxs-lookup"><span data-stu-id="0d654-151">You can enter a comma separated list of blocked words that will be blocked in group names and aliases.</span></span>

<span data-ttu-id="0d654-152">Non vengono eseguite ricerche di sottostringa; in particolare, è necessaria una corrispondenza esatta tra il nome immesso dall'utente e le parole bloccate personalizzate per attivare un errore.</span><span class="sxs-lookup"><span data-stu-id="0d654-152">No sub-string searches are carried out; specifically, an exact match between the user entered name and the custom blocked words is required to trigger a failure.</span></span>

<span data-ttu-id="0d654-153">**Aspetti da cercare:**</span><span class="sxs-lookup"><span data-stu-id="0d654-153">**Things to look out for**:</span></span>

- <span data-ttu-id="0d654-154">Per le parole bloccate non viene fatta distinzione tra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="0d654-154">The blocked words are case-insensitive.</span></span>

- <span data-ttu-id="0d654-155">Quando si immette una parola bloccata, il client del gruppo mostrerà un messaggio di errore con la parola bloccata.</span><span class="sxs-lookup"><span data-stu-id="0d654-155">When a user enters a blocked word, the group client will show an error message with the blocked word.</span></span>

- <span data-ttu-id="0d654-156">Per le parole bloccate usate non sono previste limitazioni sul limite di caratteri.</span><span class="sxs-lookup"><span data-stu-id="0d654-156">There are no character restrictions in the blocked words used.</span></span>

- <span data-ttu-id="0d654-157">Esiste un limite di 5.000 parole che possono essere impostate come parole bloccate.</span><span class="sxs-lookup"><span data-stu-id="0d654-157">There is a limit of 5000 words that can be set as blocked words.</span></span>

## <a name="admin-override"></a><span data-ttu-id="0d654-158">Override per gli amministratori</span><span class="sxs-lookup"><span data-stu-id="0d654-158">Admin override</span></span>

<span data-ttu-id="0d654-159">Alcuni amministratori sono esenti da questi criteri, in tutti i carichi di lavoro e gli endpoint di gruppo, in modo che possano creare gruppi con queste parole bloccate e con le convenzioni di denominazione desiderate.</span><span class="sxs-lookup"><span data-stu-id="0d654-159">Some administrators are exempted from these policies, across all group workloads and endpoints, so that they can create groups with these blocked words and with their desired naming conventions.</span></span> <span data-ttu-id="0d654-160">L'elenco seguente contiene i ruoli di amministratore non soggetti ai criteri di denominazione del gruppo.</span><span class="sxs-lookup"><span data-stu-id="0d654-160">The following are the list of administrator roles exempted from the group naming policy.</span></span>

- <span data-ttu-id="0d654-161">Amministratore globale</span><span class="sxs-lookup"><span data-stu-id="0d654-161">Global admin</span></span>

- <span data-ttu-id="0d654-162">Supporto partner - Livello 1</span><span class="sxs-lookup"><span data-stu-id="0d654-162">Partner Tier 1 Support</span></span>

- <span data-ttu-id="0d654-163">Supporto partner - Livello 2</span><span class="sxs-lookup"><span data-stu-id="0d654-163">Partner Tier 2 Support</span></span>

- <span data-ttu-id="0d654-164">Amministratore degli account utente</span><span class="sxs-lookup"><span data-stu-id="0d654-164">User account admin</span></span>

## <a name="how-to-set-up-the-naming-policy"></a><span data-ttu-id="0d654-165">Come configurare i criteri di denominazione</span><span class="sxs-lookup"><span data-stu-id="0d654-165">How to set up the naming policy</span></span>

<span data-ttu-id="0d654-166">Per configurare un criterio di denominazione:</span><span class="sxs-lookup"><span data-stu-id="0d654-166">To set up a naming policy:</span></span>

1. <span data-ttu-id="0d654-167">In [Azure Active Directory,](https://aad.portal.azure.com)in **Gestisci,** fare clic su **Gruppi.**</span><span class="sxs-lookup"><span data-stu-id="0d654-167">In [Azure Active Directory](https://aad.portal.azure.com), under **Manage**, click **Groups**.</span></span>
2. <span data-ttu-id="0d654-168">In **Impostazioni** fare clic su **Criteri di denominazione.**</span><span class="sxs-lookup"><span data-stu-id="0d654-168">Under **Settings**, click **Naming policy**.</span></span>
3. <span data-ttu-id="0d654-169">Scegliere la scheda **Criteri di denominazione dei** gruppi.</span><span class="sxs-lookup"><span data-stu-id="0d654-169">Choose the **Group naming policy** tab.</span></span>
4. <span data-ttu-id="0d654-170">In **Criteri correnti** scegliere se si desidera richiedere un prefisso o un suffisso o entrambi e selezionare le caselle di controllo appropriate.</span><span class="sxs-lookup"><span data-stu-id="0d654-170">Under **Current policy**, choose if you want to require a prefix or suffix or both, and select the appropriate check boxes.</span></span>
5. <span data-ttu-id="0d654-171">Scegliere tra **Attributo** e **Stringa** per ogni riga e quindi specificare l'attributo o la stringa.</span><span class="sxs-lookup"><span data-stu-id="0d654-171">Choose between **Attribute** and **String** for each line and then specify the attribute or string.</span></span>
6. <span data-ttu-id="0d654-172">Dopo aver aggiunto i prefissi e i suffissi necessari, fare clic su **Salva.**</span><span class="sxs-lookup"><span data-stu-id="0d654-172">When you have added the prefixes and suffixes that you need, click **Save**.</span></span>

![Screenshot delle impostazioni dei criteri di denominazione dei gruppi in Azure Active Directory](../media/groups-naming-policy-azure.png)

## <a name="related-topics"></a><span data-ttu-id="0d654-174">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="0d654-174">Related topics</span></span>

[<span data-ttu-id="0d654-175">Procedura dettagliata per la pianificazione della governance della collaborazione</span><span class="sxs-lookup"><span data-stu-id="0d654-175">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="0d654-176">Creare il piano di governance della collaborazione</span><span class="sxs-lookup"><span data-stu-id="0d654-176">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)

[<span data-ttu-id="0d654-177">Cmdlet di Azure Active Directory per la configurazione delle impostazioni di gruppo</span><span class="sxs-lookup"><span data-stu-id="0d654-177">Azure Active Directory cmdlets for configuring group settings</span></span>](https://go.microsoft.com/fwlink/?linkid=868341)
