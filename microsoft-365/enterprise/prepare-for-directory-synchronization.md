---
title: Preparare la sincronizzazione della directory con Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/25/2019
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365p_AddUsersWithDirSync
- O365M_AddUsersWithDirSync
- O365E_HRCSetupAADConnectAboutLM617031
- O365E_AddUsersWithDirSync
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOP150
- MOE150
- MBS150
ms.assetid: 01920974-9e6f-4331-a370-13aea4e82b3e
description: Descrive come prepararsi a eseguire il provisioning degli utenti a Microsoft 365 utilizzando la sincronizzazione della directory e i vantaggi a lungo termine dell'utilizzo di questo metodo.
ms.openlocfilehash: c9d4368d1939b9c6feedf5146f9d168f18d5d5b1
ms.sourcegitcommit: 96b4593becc9450af136c528844e858c6e88b5a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2020
ms.locfileid: "48269418"
---
# <a name="prepare-for-directory-synchronization-to-microsoft-365"></a><span data-ttu-id="33ee3-103">Preparare la sincronizzazione della directory con Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="33ee3-103">Prepare for directory synchronization to Microsoft 365</span></span>

<span data-ttu-id="33ee3-104">*Questo articolo si applica sia a Microsoft 365 Enterprise che a Office 365 Enterprise*.</span><span class="sxs-lookup"><span data-stu-id="33ee3-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="33ee3-105">I vantaggi dell'identità ibrida e della sincronizzazione della directory dell'organizzazione includono:</span><span class="sxs-lookup"><span data-stu-id="33ee3-105">The benefits to hybrid identity and directory synchronization your organization include:</span></span>

- <span data-ttu-id="33ee3-106">Riduzione dei programmi amministrativi nell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="33ee3-106">Reducing the administrative programs in your organization</span></span>
- <span data-ttu-id="33ee3-107">Opzione che consente di abilitare lo scenario Single Sign-on</span><span class="sxs-lookup"><span data-stu-id="33ee3-107">Optionally enabling single sign-on scenario</span></span>
- <span data-ttu-id="33ee3-108">Automatizzare le modifiche degli account in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="33ee3-108">Automating account changes in Microsoft 365</span></span>

<span data-ttu-id="33ee3-109">Per ulteriori informazioni sui vantaggi derivanti dall'utilizzo della sincronizzazione della directory, vedere [Directory Synchronization roadmap]( https://go.microsoft.com/fwlink/p/?LinkId=525398) and [Hybrid identity for Microsoft 365](plan-for-directory-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="33ee3-109">For more information about the advantages of using directory synchronization, see [Directory synchronization roadmap]( https://go.microsoft.com/fwlink/p/?LinkId=525398) and [Hybrid identity for Microsoft 365](plan-for-directory-synchronization.md).</span></span>

<span data-ttu-id="33ee3-110">Tuttavia, la sincronizzazione della directory richiede la pianificazione e la preparazione per garantire che i servizi di dominio Active Directory vengano sincronizzati con il tenant di Azure Active Directory (Azure AD) dell'abbonamento a Microsoft 365 con un minimo di errori.</span><span class="sxs-lookup"><span data-stu-id="33ee3-110">However, directory synchronization requires planning and preparation to ensure that your Active Directory Domain Services (AD DS) synchronizes to the Azure Active Directory (Azure AD) tenant of your Microsoft 365 subscription with a minimum of errors.</span></span>

<span data-ttu-id="33ee3-111">Seguire questi passaggi per ottenere risultati ottimali.</span><span class="sxs-lookup"><span data-stu-id="33ee3-111">Follow these steps in order for the best results.</span></span>

## <a name="1-directory-cleanup-tasks"></a><span data-ttu-id="33ee3-112">1. attività di pulizia della directory</span><span class="sxs-lookup"><span data-stu-id="33ee3-112">1. Directory cleanup tasks</span></span>

<span data-ttu-id="33ee3-113">Prima di sincronizzare servizi di dominio Active Directory con il tenant di Azure AD, è necessario eseguire la pulizia di servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="33ee3-113">Before you synchronize your AD DS to your Azure AD tenant, you need to clean up your AD DS.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="33ee3-114">Se non si esegue la pulizia di servizi di dominio Active Directory prima di eseguire la sincronizzazione, il processo di distribuzione può avere un effetto negativo significativo.</span><span class="sxs-lookup"><span data-stu-id="33ee3-114">If you don't perform AD DS cleanup before you synchronize, there can be a significant negative effect on the deployment process.</span></span> <span data-ttu-id="33ee3-115">Potrebbero essere necessari giorni o persino settimane per eseguire il ciclo di sincronizzazione della directory, l'identificazione dei relativi errori e la ripetizione della sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="33ee3-115">It might take days, or even weeks, to go through the cycle of directory synchronization, identifying errors, and re-synchronization.</span></span>

<span data-ttu-id="33ee3-116">In servizi di dominio Active Directory, completare le seguenti attività di pulizia per ogni account utente a cui viene assegnata una licenza Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="33ee3-116">In your AD DS, complete the following clean-up tasks for each user account that will be assigned a Microsoft 365 license:</span></span>

1. <span data-ttu-id="33ee3-117">Verificare l'indirizzo di posta elettronica valido e univoco nell'attributo **proxyAddresses** .</span><span class="sxs-lookup"><span data-stu-id="33ee3-117">Ensure a valid and unique email address in the **proxyAddresses** attribute.</span></span>

2. <span data-ttu-id="33ee3-118">Rimuovere tutti i valori duplicati nell'attributo **proxyAddresses**.</span><span class="sxs-lookup"><span data-stu-id="33ee3-118">Remove any duplicate values in the **proxyAddresses** attribute.</span></span>

3. <span data-ttu-id="33ee3-119">Se possibile, garantire un valore valido e univoco per l'attributo **userPrincipalName** nell'oggetto **utente** dell'utente.</span><span class="sxs-lookup"><span data-stu-id="33ee3-119">If possible, ensure a valid and unique value for the **userPrincipalName** attribute in the user's **user** object.</span></span> <span data-ttu-id="33ee3-120">Per un'esperienza di sincronizzazione ottimale, verificare che l'UPN di servizi di dominio Active Directory corrisponda all'UPN di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="33ee3-120">For the best synchronization experience, ensure that the AD DS UPN matches the Azure AD UPN.</span></span> <span data-ttu-id="33ee3-121">Se un utente non dispone di un valore per l'attributo **userPrincipalName**, l'oggetto **user** deve contenere un valore univoco e valido per l'attributo **sAMAccountName**.</span><span class="sxs-lookup"><span data-stu-id="33ee3-121">If a user does not have a value for the **userPrincipalName** attribute, then the **user** object must contain a valid and unique value for the **sAMAccountName** attribute.</span></span> <span data-ttu-id="33ee3-122">Rimuovere tutti i valori duplicati nell'attributo **userPrincipalName**.</span><span class="sxs-lookup"><span data-stu-id="33ee3-122">Remove any duplicate values in the **userPrincipalName** attribute.</span></span>

4. <span data-ttu-id="33ee3-123">Per un utilizzo ottimale dell'elenco indirizzi globale (GAL, Global Address List), assicurarsi che le informazioni contenute nei seguenti attributi dell'account utente di servizi di dominio Active Directory siano corrette:</span><span class="sxs-lookup"><span data-stu-id="33ee3-123">For optimal use of the global address list (GAL), ensure the information in the following attributes of the AD DS user account is correct:</span></span>

   - <span data-ttu-id="33ee3-124">givenName</span><span class="sxs-lookup"><span data-stu-id="33ee3-124">givenName</span></span>
   - <span data-ttu-id="33ee3-125">Cognome</span><span class="sxs-lookup"><span data-stu-id="33ee3-125">surname</span></span>
   - <span data-ttu-id="33ee3-126">displayName</span><span class="sxs-lookup"><span data-stu-id="33ee3-126">displayName</span></span>
   - <span data-ttu-id="33ee3-127">Professione</span><span class="sxs-lookup"><span data-stu-id="33ee3-127">Job Title</span></span>
   - <span data-ttu-id="33ee3-128">Reparto</span><span class="sxs-lookup"><span data-stu-id="33ee3-128">Department</span></span>
   - <span data-ttu-id="33ee3-129">Ufficio</span><span class="sxs-lookup"><span data-stu-id="33ee3-129">Office</span></span>
   - <span data-ttu-id="33ee3-130">Telefono ufficio</span><span class="sxs-lookup"><span data-stu-id="33ee3-130">Office Phone</span></span>
   - <span data-ttu-id="33ee3-131">Cellulare</span><span class="sxs-lookup"><span data-stu-id="33ee3-131">Mobile Phone</span></span>
   - <span data-ttu-id="33ee3-132">Numero fax</span><span class="sxs-lookup"><span data-stu-id="33ee3-132">Fax Number</span></span>
   - <span data-ttu-id="33ee3-133">Via e numero civico</span><span class="sxs-lookup"><span data-stu-id="33ee3-133">Street Address</span></span>
   - <span data-ttu-id="33ee3-134">Città</span><span class="sxs-lookup"><span data-stu-id="33ee3-134">City</span></span>
   - <span data-ttu-id="33ee3-135">Stato o provincia</span><span class="sxs-lookup"><span data-stu-id="33ee3-135">State or Province</span></span>
   - <span data-ttu-id="33ee3-136">CAP</span><span class="sxs-lookup"><span data-stu-id="33ee3-136">Zip or Postal Code</span></span>
   - <span data-ttu-id="33ee3-137">Paese</span><span class="sxs-lookup"><span data-stu-id="33ee3-137">Country or Region</span></span>

## <a name="2-directory-object-and-attribute-preparation"></a><span data-ttu-id="33ee3-138">2. la preparazione degli attributi e degli oggetti directory</span><span class="sxs-lookup"><span data-stu-id="33ee3-138">2. Directory object and attribute preparation</span></span>

<span data-ttu-id="33ee3-139">La corretta sincronizzazione della directory tra il servizio AD DS e Microsoft 365 richiede la corretta preparazione degli attributi di AD DS.</span><span class="sxs-lookup"><span data-stu-id="33ee3-139">Successful directory synchronization between your AD DS and Microsoft 365 requires that your AD DS attributes are properly prepared.</span></span> <span data-ttu-id="33ee3-140">Ad esempio, è necessario assicurarsi che i caratteri specifici non vengano utilizzati in alcuni attributi sincronizzati con l'ambiente Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="33ee3-140">For example, you need to ensure that specific characters aren't used in certain attributes that are synchronized with the Microsoft 365 environment.</span></span> <span data-ttu-id="33ee3-141">I caratteri imprevisti non determinano il failover della sincronizzazione della directory ma potrebbero restituire un avviso.</span><span class="sxs-lookup"><span data-stu-id="33ee3-141">Unexpected characters do not cause directory synchronization to fail but might return a warning.</span></span> <span data-ttu-id="33ee3-142">I caratteri non validi sono responsabili dell'esito negativo della sincronizzazione della directory.</span><span class="sxs-lookup"><span data-stu-id="33ee3-142">Invalid characters will cause directory synchronization to fail.</span></span>

<span data-ttu-id="33ee3-143">La sincronizzazione della directory avrà esito negativo anche se alcuni degli utenti di AD DS dispongono di uno o più attributi duplicati.</span><span class="sxs-lookup"><span data-stu-id="33ee3-143">Directory synchronization will also fail if some of your AD DS users have one or more duplicate attributes.</span></span> <span data-ttu-id="33ee3-144">Ogni utente deve disporre di attributi univoci.</span><span class="sxs-lookup"><span data-stu-id="33ee3-144">Each user must have unique attributes.</span></span>

<span data-ttu-id="33ee3-145">Gli attributi necessari per la preparazione sono elencati di seguito:</span><span class="sxs-lookup"><span data-stu-id="33ee3-145">The attributes that you need to prepare are listed here:</span></span>

- <span data-ttu-id="33ee3-146">**displayName**</span><span class="sxs-lookup"><span data-stu-id="33ee3-146">**displayName**</span></span>

  - <span data-ttu-id="33ee3-147">Se l'attributo è presente nell'oggetto utente, verrà sincronizzato con Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="33ee3-147">If the attribute exists in the user object, it will be synchronized with Microsoft 365.</span></span>
  - <span data-ttu-id="33ee3-148">A un attributo presente nell'oggetto utente deve corrispondere un valore.</span><span class="sxs-lookup"><span data-stu-id="33ee3-148">If this attribute exists in the user object, there must be a value for it.</span></span> <span data-ttu-id="33ee3-149">Ovvero, l'attributo non deve essere vuoto.</span><span class="sxs-lookup"><span data-stu-id="33ee3-149">That is, the attribute must not be blank.</span></span>
  - <span data-ttu-id="33ee3-150">Numero massimo di caratteri: 256</span><span class="sxs-lookup"><span data-stu-id="33ee3-150">Maximum number of characters: 256</span></span>

- <span data-ttu-id="33ee3-151">**givenName**</span><span class="sxs-lookup"><span data-stu-id="33ee3-151">**givenName**</span></span>

  - <span data-ttu-id="33ee3-152">Se l'attributo è presente nell'oggetto utente, verrà sincronizzato con Microsoft 365, ma Microsoft 365 non lo richiede o lo utilizza.</span><span class="sxs-lookup"><span data-stu-id="33ee3-152">If the attribute exists in the user object, it will be synchronized with Microsoft 365, but Microsoft 365 does not require or use it.</span></span>
  - <span data-ttu-id="33ee3-153">Numero massimo di caratteri: 64</span><span class="sxs-lookup"><span data-stu-id="33ee3-153">Maximum number of characters: 64</span></span>

- <span data-ttu-id="33ee3-154">**posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="33ee3-154">**mail**</span></span>

  - <span data-ttu-id="33ee3-155">Il valore dell'attributo deve essere univoco all'interno della directory.</span><span class="sxs-lookup"><span data-stu-id="33ee3-155">The attribute value must be unique within the directory.</span></span>

    > [!NOTE]
    > <span data-ttu-id="33ee3-156">Se sono presenti valori duplicati, il primo utente con il valore è sincronizzato.</span><span class="sxs-lookup"><span data-stu-id="33ee3-156">If there are duplicate values, the first user with the value is synchronized.</span></span> <span data-ttu-id="33ee3-157">Gli utenti successivi non verranno visualizzati in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="33ee3-157">Subsequent users will not appear in Microsoft 365.</span></span> <span data-ttu-id="33ee3-158">È necessario modificare il valore in Microsoft 365 o modificare entrambi i valori in servizi di dominio Active Directory per consentire la visualizzazione di entrambi gli utenti in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="33ee3-158">You must modify either the value in Microsoft 365 or modify both of the values in AD DS in order for both users to appear in Microsoft 365.</span></span>

- <span data-ttu-id="33ee3-159">**mailNickname** (alias di Exchange)</span><span class="sxs-lookup"><span data-stu-id="33ee3-159">**mailNickname** (Exchange alias)</span></span>

  - <span data-ttu-id="33ee3-160">Il valore dell'attributo non può iniziare con un punto (.).</span><span class="sxs-lookup"><span data-stu-id="33ee3-160">The attribute value cannot begin with a period (.).</span></span>
  - <span data-ttu-id="33ee3-161">Il valore dell'attributo deve essere univoco all'interno della directory.</span><span class="sxs-lookup"><span data-stu-id="33ee3-161">The attribute value must be unique within the directory.</span></span>

    > [!NOTE]
    > <span data-ttu-id="33ee3-162">Carattere di sottolineatura ("_") nel nome sincronizzato indica che il valore originale di questo attributo contiene caratteri non validi.</span><span class="sxs-lookup"><span data-stu-id="33ee3-162">Underscores ("_") in the synchronized name indicates that the original value of this attribute contains invalid characters.</span></span> <span data-ttu-id="33ee3-163">Per ulteriori informazioni su questo attributo, vedere [attributo alias di Exchange](https://docs.microsoft.com/powershell/module/exchange/set-mailbox).</span><span class="sxs-lookup"><span data-stu-id="33ee3-163">For more information on this attribute, see [Exchange alias attribute](https://docs.microsoft.com/powershell/module/exchange/set-mailbox).</span></span>
    >

- <span data-ttu-id="33ee3-164">**proxyAddresses**</span><span class="sxs-lookup"><span data-stu-id="33ee3-164">**proxyAddresses**</span></span>

  - <span data-ttu-id="33ee3-165">Attributo con più valori</span><span class="sxs-lookup"><span data-stu-id="33ee3-165">Multiple-value attribute</span></span>
  - <span data-ttu-id="33ee3-166">Numero massimo di caratteri per valore: 256</span><span class="sxs-lookup"><span data-stu-id="33ee3-166">Maximum number of characters per value: 256</span></span>
  - <span data-ttu-id="33ee3-167">Il valore dell'attributo non deve contenere uno spazio.</span><span class="sxs-lookup"><span data-stu-id="33ee3-167">The attribute value must not contain a space.</span></span>
  - <span data-ttu-id="33ee3-168">Il valore dell'attributo deve essere univoco all'interno della directory.</span><span class="sxs-lookup"><span data-stu-id="33ee3-168">The attribute value must be unique within the directory.</span></span>
  - <span data-ttu-id="33ee3-169">Caratteri non validi: \< \> ();, [] "'</span><span class="sxs-lookup"><span data-stu-id="33ee3-169">Invalid characters: \< \> ( ) ; , [ ] " '</span></span>

    <span data-ttu-id="33ee3-170">Si noti che i caratteri non validi si applicano ai caratteri che seguono il delimitatore di tipo e ":", in modo che SMTP:User@contso.com sia consentita, ma SMTP:user:M@contoso.com non lo è.</span><span class="sxs-lookup"><span data-stu-id="33ee3-170">Note that the invalid characters apply to the characters following the type delimiter and ":", such that SMTP:User@contso.com is allowed, but SMTP:user:M@contoso.com is not.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="33ee3-171">Tutti gli indirizzi SMTP (Simple Mail Transport Protocol) devono essere conformi agli standard di messaggistica di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="33ee3-171">All Simple Mail Transport Protocol (SMTP) addresses should comply with email messaging standards.</span></span> <span data-ttu-id="33ee3-172">Se esistono indirizzi duplicati o indesiderati, vedere l'argomento della Guida relativo alla [rimozione di indirizzi proxy duplicati e indesiderati in Exchange](https://go.microsoft.com/fwlink/?LinkId=293860).</span><span class="sxs-lookup"><span data-stu-id="33ee3-172">If duplicate or unwanted addresses exist, see the Help topic [Removing duplicate and unwanted proxy addresses in Exchange](https://go.microsoft.com/fwlink/?LinkId=293860).</span></span>

- <span data-ttu-id="33ee3-173">**sAMAccountName**</span><span class="sxs-lookup"><span data-stu-id="33ee3-173">**sAMAccountName**</span></span>

  - <span data-ttu-id="33ee3-174">Numero massimo di caratteri: 20</span><span class="sxs-lookup"><span data-stu-id="33ee3-174">Maximum number of characters: 20</span></span>
  - <span data-ttu-id="33ee3-175">Il valore dell'attributo deve essere univoco all'interno della directory.</span><span class="sxs-lookup"><span data-stu-id="33ee3-175">The attribute value must be unique within the directory.</span></span>
  - <span data-ttu-id="33ee3-176">Caratteri non validi: [\ "|,/: \< \> + =;?</span><span class="sxs-lookup"><span data-stu-id="33ee3-176">Invalid characters: [ \ " | , / : \< \> + = ; ?</span></span> <span data-ttu-id="33ee3-177">\* ']</span><span class="sxs-lookup"><span data-stu-id="33ee3-177">\* ']</span></span>
  - <span data-ttu-id="33ee3-178">Se un utente ha un attributo **sAMAccountName** non valido, ma ha un attributo **userPrincipalName** valido, l'account utente verrà creato in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="33ee3-178">If a user has an invalid **sAMAccountName** attribute but has a valid **userPrincipalName** attribute, the user account is created in Microsoft 365.</span></span>
  - <span data-ttu-id="33ee3-179">Se **sAMAccountName** e **userPrincipalName** non sono validi, è necessario aggiornare l'attributo **userPrincipalName** di servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="33ee3-179">If both **sAMAccountName** and **userPrincipalName** are invalid, the AD DS **userPrincipalName** attribute must be updated.</span></span>

- <span data-ttu-id="33ee3-180">**sn** (cognome)</span><span class="sxs-lookup"><span data-stu-id="33ee3-180">**sn** (surname)</span></span>

  - <span data-ttu-id="33ee3-181">Se l'attributo è presente nell'oggetto utente, verrà sincronizzato con Microsoft 365, ma Microsoft 365 non lo richiede o lo utilizza.</span><span class="sxs-lookup"><span data-stu-id="33ee3-181">If the attribute exists in the user object, it will be synchronized with Microsoft 365, but Microsoft 365 does not require or use it.</span></span>

- <span data-ttu-id="33ee3-182">**targetAddress**</span><span class="sxs-lookup"><span data-stu-id="33ee3-182">**targetAddress**</span></span>

    <span data-ttu-id="33ee3-183">È necessario che l'attributo **targetAddress** , ad esempio SMTP:Tom@contoso.com, popolato per l'utente, venga visualizzato nell'elenco indirizzi globale di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="33ee3-183">It's required that the **targetAddress** attribute (for example, SMTP:tom@contoso.com) that's populated for the user must appear in the Microsoft 365 GAL.</span></span> <span data-ttu-id="33ee3-184">In scenari di migrazione della messaggistica di terze parti, ciò richiederebbe l'estensione dello schema Microsoft 365 per il servizio di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="33ee3-184">In third-party messaging migration scenarios, this would require the Microsoft 365 schema extension for the AD DS.</span></span> <span data-ttu-id="33ee3-185">L'estensione dello schema di Microsoft 365 aggiungerà anche altri attributi utili per gestire gli oggetti di Microsoft 365 che sono stati popolati utilizzando uno strumento di sincronizzazione della directory da AD DS.</span><span class="sxs-lookup"><span data-stu-id="33ee3-185">The Microsoft 365 schema extension would also add other useful attributes to manage Microsoft 365 objects that are populated by using a directory synchronization tool from AD DS.</span></span> <span data-ttu-id="33ee3-186">Verrebbe ad esempio aggiunto l'attributo **msExchHideFromAddressLists** per gestire i gruppi di distribuzione o le cassette postali nascoste.</span><span class="sxs-lookup"><span data-stu-id="33ee3-186">For example, the **msExchHideFromAddressLists** attribute to manage hidden mailboxes or distribution groups would be added.</span></span>

  - <span data-ttu-id="33ee3-187">Numero massimo di caratteri: 256</span><span class="sxs-lookup"><span data-stu-id="33ee3-187">Maximum number of characters: 256</span></span>
  - <span data-ttu-id="33ee3-188">Il valore dell'attributo non deve contenere uno spazio.</span><span class="sxs-lookup"><span data-stu-id="33ee3-188">The attribute value must not contain a space.</span></span>
  - <span data-ttu-id="33ee3-189">Il valore dell'attributo deve essere univoco all'interno della directory.</span><span class="sxs-lookup"><span data-stu-id="33ee3-189">The attribute value must be unique within the directory.</span></span>
  - <span data-ttu-id="33ee3-190">Caratteri non validi: \ \< \> ();, [] "</span><span class="sxs-lookup"><span data-stu-id="33ee3-190">Invalid characters: \ \< \> ( ) ; , [ ] "</span></span>
  - <span data-ttu-id="33ee3-191">Tutti gli indirizzi SMTP (Simple Mail Transport Protocol) devono essere conformi agli standard di messaggistica di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="33ee3-191">All Simple Mail Transport Protocol (SMTP) addresses should comply with email messaging standards.</span></span>

- <span data-ttu-id="33ee3-192">**userPrincipalName**</span><span class="sxs-lookup"><span data-stu-id="33ee3-192">**userPrincipalName**</span></span>

  - <span data-ttu-id="33ee3-193">L'attributo **userPrincipalName** deve trovarsi nel formato di accesso di tipo Internet, in cui il nome utente è seguito dal segno di chiocciola (@) e dal nome di dominio: ad esempio, user@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="33ee3-193">The **userPrincipalName** attribute must be in the Internet-style sign-in format where the user name is followed by the at sign (@) and a domain name: for example, user@contoso.com.</span></span> <span data-ttu-id="33ee3-194">Tutti gli indirizzi SMTP (Simple Mail Transport Protocol) devono essere conformi agli standard di messaggistica di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="33ee3-194">All Simple Mail Transport Protocol (SMTP) addresses should comply with email messaging standards.</span></span>
  - <span data-ttu-id="33ee3-p112">Il numero massimo di caratteri per l'attributo **userPrincipalName** è 113. È consentito un numero specifico di caratteri prima e dopo il simbolo di chiocciola (@), come riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="33ee3-p112">The maximum number of characters for the **userPrincipalName** attribute is 113. A specific number of characters are permitted before and after the at sign (@), as follows:</span></span>
  - <span data-ttu-id="33ee3-197">Numero massimo di caratteri per il nome utente che si trova di fronte al segno di chiocciola (@): 64</span><span class="sxs-lookup"><span data-stu-id="33ee3-197">Maximum number of characters for the username that is in front of the at sign (@): 64</span></span>
  - <span data-ttu-id="33ee3-198">Numero massimo di caratteri per il nome di dominio dopo il simbolo chiocciola (@): 48</span><span class="sxs-lookup"><span data-stu-id="33ee3-198">Maximum number of characters for the domain name following the at sign (@): 48</span></span>
  - <span data-ttu-id="33ee3-199">Caratteri non validi: \% &amp; \* +/=?</span><span class="sxs-lookup"><span data-stu-id="33ee3-199">Invalid characters: \ % &amp; \* + / = ?</span></span> <span data-ttu-id="33ee3-200">{ } | \< \> ( ) ; : , [ ] " '</span><span class="sxs-lookup"><span data-stu-id="33ee3-200">{ } | \< \> ( ) ; : , [ ] " '</span></span>
  - <span data-ttu-id="33ee3-201">Anche la dieresi è un carattere non valido.</span><span class="sxs-lookup"><span data-stu-id="33ee3-201">An umlaut is also an invalid character.</span></span>
  - <span data-ttu-id="33ee3-202">Il carattere @ è necessario in ogni valore **userPrincipalName**.</span><span class="sxs-lookup"><span data-stu-id="33ee3-202">The @ character is required in each **userPrincipalName** value.</span></span>
  - <span data-ttu-id="33ee3-203">Il carattere @ non può essere il primo carattere in ogni valore **userPrincipalName**.</span><span class="sxs-lookup"><span data-stu-id="33ee3-203">The @ character cannot be the first character in each **userPrincipalName** value.</span></span>
  - <span data-ttu-id="33ee3-204">Il nome utente non può terminare con un punto (.), una e commerciale ( &amp; ), uno spazio o un segno di chiocciola (@).</span><span class="sxs-lookup"><span data-stu-id="33ee3-204">The username cannot end with a period (.), an ampersand (&amp;), a space, or an at sign (@).</span></span>
  - <span data-ttu-id="33ee3-205">Il nome utente non può contenere spazi.</span><span class="sxs-lookup"><span data-stu-id="33ee3-205">The username cannot contain any spaces.</span></span>
  - <span data-ttu-id="33ee3-206">I domini instradabili devono essere utilizzati. ad esempio, non è possibile utilizzare i domini locali o interni.</span><span class="sxs-lookup"><span data-stu-id="33ee3-206">Routable domains must be used; for example, local or internal domains cannot be used.</span></span>
  - <span data-ttu-id="33ee3-207">Unicode viene convertito in caratteri di sottolineatura.</span><span class="sxs-lookup"><span data-stu-id="33ee3-207">Unicode is converted to underscore characters.</span></span>
  - <span data-ttu-id="33ee3-208">**userPrincipalName** non può contenere valori duplicati nella directory.</span><span class="sxs-lookup"><span data-stu-id="33ee3-208">**userPrincipalName** cannot contain any duplicate values in the directory.</span></span>

## <a name="3-prepare-the-userprincipalname-attribute"></a><span data-ttu-id="33ee3-209">3. preparare l'attributo userPrincipalName</span><span class="sxs-lookup"><span data-stu-id="33ee3-209">3. Prepare the userPrincipalName attribute</span></span>

<span data-ttu-id="33ee3-210">Active Directory è stato creato per consentire agli utenti finali dell'organizzazione di accedere alla directory tramite **sAMAccountName** o **userPrincipalName**.</span><span class="sxs-lookup"><span data-stu-id="33ee3-210">Active Directory is designed to allow the end users in your organization to sign in to your directory by using either **sAMAccountName** or **userPrincipalName**.</span></span> <span data-ttu-id="33ee3-211">Analogamente, gli utenti finali possono accedere a Microsoft 365 utilizzando il nome dell'entità utente (UPN) dell'account aziendale o dell'Istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="33ee3-211">Similarly, end users can sign in to Microsoft 365 by using the user principal name (UPN) of their work or school account.</span></span> <span data-ttu-id="33ee3-212">La sincronizzazione della directory tenta di creare nuovi utenti in Azure Active Directory utilizzando lo stesso UPN presente in servizi di dominio Active copia.</span><span class="sxs-lookup"><span data-stu-id="33ee3-212">Directory synchronization attempts to create new users in Azure Active Directory by using the same UPN that's in your AD DS.</span></span> <span data-ttu-id="33ee3-213">L'UPN viene formattato come un indirizzo di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="33ee3-213">The UPN is formatted like an email address.</span></span>

<span data-ttu-id="33ee3-214">In Microsoft 365, l'UPN è l'attributo predefinito utilizzato per generare l'indirizzo di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="33ee3-214">In Microsoft 365, the UPN is the default attribute that's used to generate the email address.</span></span> <span data-ttu-id="33ee3-215">È facile ottenere **userPrincipalName** (in servizi di dominio Active Directory e in Azure ad) e l'indirizzo di posta elettronica principale in **proxyAddresses** impostato su valori diversi.</span><span class="sxs-lookup"><span data-stu-id="33ee3-215">It's easy to get **userPrincipalName** (in AD DS and in Azure AD) and the primary email address in **proxyAddresses** set to different values.</span></span> <span data-ttu-id="33ee3-216">Quando sono impostati su valori diversi, possono generare confusione per amministratori e utenti finali.</span><span class="sxs-lookup"><span data-stu-id="33ee3-216">When they are set to different values, there can be confusion for administrators and end users.</span></span>

<span data-ttu-id="33ee3-217">È consigliabile allineare questi attributi per ridurre la confusione.</span><span class="sxs-lookup"><span data-stu-id="33ee3-217">It's best to align these attributes to reduce confusion.</span></span> <span data-ttu-id="33ee3-218">Per soddisfare i requisiti del servizio Single Sign-on con Active Directory Federation Services (AD FS) 2,0, è necessario assicurarsi che UPN in Azure Active Directory e la corrispondenza di AD DS e utilizzino uno spazio dei nomi di dominio valido.</span><span class="sxs-lookup"><span data-stu-id="33ee3-218">To meet the requirements of single sign-on with Active Directory Federation Services (AD FS) 2.0, you need to ensure that the UPNs in Azure Active Directory and your AD DS match and are using a valid domain namespace.</span></span>

## <a name="4-add-an-alternative-upn-suffix-to-ad-ds"></a><span data-ttu-id="33ee3-219">4. aggiungere un suffisso UPN alternativo a servizi di dominio Active Directory</span><span class="sxs-lookup"><span data-stu-id="33ee3-219">4. Add an alternative UPN suffix to AD DS</span></span>

<span data-ttu-id="33ee3-220">Potrebbe essere necessario aggiungere un suffisso UPN alternativo per associare le credenziali aziendali dell'utente all'ambiente Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="33ee3-220">You may need to add an alternative UPN suffix to associate the user's corporate credentials with the Microsoft 365 environment.</span></span> <span data-ttu-id="33ee3-221">Il suffisso UPN è la parte di un UPN che si trova a destra del carattere @.</span><span class="sxs-lookup"><span data-stu-id="33ee3-221">A UPN suffix is the part of a UPN to the right of the @ character.</span></span> <span data-ttu-id="33ee3-222">Gli UPN utilizzati per Single Sign-On possono includere lettere, numeri, punti, trattini e caratteri di sottolineatura, ma nessun altro tipo di carattere.</span><span class="sxs-lookup"><span data-stu-id="33ee3-222">UPNs that are used for single sign-on can contain letters, numbers, periods, dashes, and underscores, but no other types of characters.</span></span>

<span data-ttu-id="33ee3-223">Per ulteriori informazioni su come aggiungere un suffisso UPN alternativo ad Active Directory, vedere [Prepare for Directory Synchronization]( https://go.microsoft.com/fwlink/p/?LinkId=525430).</span><span class="sxs-lookup"><span data-stu-id="33ee3-223">For more information on how to add an alternative UPN suffix to Active Directory, see [Prepare for directory synchronization]( https://go.microsoft.com/fwlink/p/?LinkId=525430).</span></span>

## <a name="5-match-the-ad-ds-upn-with-the-microsoft-365-upn"></a><span data-ttu-id="33ee3-224">5. corrispondere all'UPN di servizi di dominio Active Directory con l'UPN di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="33ee3-224">5. Match the AD DS UPN with the Microsoft 365 UPN</span></span>

<span data-ttu-id="33ee3-225">Se è già stata configurata la sincronizzazione della directory, l'UPN dell'utente per Microsoft 365 potrebbe non corrispondere all'UPN di AD DS dell'utente definito in AD DS.</span><span class="sxs-lookup"><span data-stu-id="33ee3-225">If you've already set up directory synchronization, the user's UPN for Microsoft 365 may not match the user's AD DS UPN that's defined in your AD DS.</span></span> <span data-ttu-id="33ee3-226">Questa situazione può verificarsi quando a un utente viene assegnata una licenza prima della verifica del dominio.</span><span class="sxs-lookup"><span data-stu-id="33ee3-226">This can occur when a user was assigned a license before the domain was verified.</span></span> <span data-ttu-id="33ee3-227">Per risolvere questo risultato, utilizzare [PowerShell per correggere l'UPN duplicato](https://go.microsoft.com/fwlink/p/?LinkId=396730) per aggiornare l'UPN dell'utente per verificare che l'upn Microsoft 365 corrisponda al nome utente e al dominio dell'azienda.</span><span class="sxs-lookup"><span data-stu-id="33ee3-227">To fix this, use [PowerShell to fix duplicate UPN](https://go.microsoft.com/fwlink/p/?LinkId=396730) to update the user's UPN to ensure that the Microsoft 365 UPN matches the corporate user name and domain.</span></span> <span data-ttu-id="33ee3-228">Se si esegue l'aggiornamento dell'UPN in servizi di dominio Active Directory e si desidera che venga sincronizzato con l'identità di Azure, è necessario rimuovere la licenza dell'utente in Microsoft 365 prima di apportare le modifiche in AD DS.</span><span class="sxs-lookup"><span data-stu-id="33ee3-228">If you are updating the UPN in the AD DS and would like it to synchronize with the Azure Active Directory identity, you need to remove the user's license in Microsoft 365 prior to making the changes in AD DS.</span></span>

<span data-ttu-id="33ee3-229">Vedere anche [come preparare un dominio non instradabile (ad esempio, dominio locale) per la sincronizzazione della directory](prepare-a-non-routable-domain-for-directory-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="33ee3-229">Also see [How to prepare a non-routable domain (such as .local domain) for directory synchronization](prepare-a-non-routable-domain-for-directory-synchronization.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="33ee3-230">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="33ee3-230">Next steps</span></span>

<span data-ttu-id="33ee3-231">Se sono stati eseguiti i passaggi da 1 a 5, vedere [configurare la sincronizzazione della directory](set-up-directory-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="33ee3-231">If you have done steps 1 through 5 above, see [Set up directory synchronization](set-up-directory-synchronization.md).</span></span>
