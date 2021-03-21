---
title: Limitare l'esposizione accidentale
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- m365solution-3tiersprotection
- m365solution-securecollab
- m365initiative-externalcollab
ms.custom: ''
localization_priority: Priority
f1.keywords: NOCSH
description: Informazioni su come limitare l'esposizione accidentale di informazioni quando si condividono file con persone esterne all'organizzazione.
ms.openlocfilehash: 952337790ce2f0418dd5ab637435f1523b27b562
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928413"
---
# <a name="limit-accidental-exposure-to-files-when-sharing-with-people-outside-your-organization"></a><span data-ttu-id="f2395-103">Limitare l'esposizione accidentale ai file durante la condivisione con persone esterne all'organizzazione</span><span class="sxs-lookup"><span data-stu-id="f2395-103">Limit accidental exposure to files when sharing with people outside your organization</span></span>

<span data-ttu-id="f2395-104">Quando si condividono file e cartelle con persone esterne all'organizzazione sono disponibili varie opzioni per ridurre le possibilità di condivisione accidentale di informazioni sensibili.</span><span class="sxs-lookup"><span data-stu-id="f2395-104">When sharing files and folders with people outside your organization, there are a variety of options to reduce the chances of accidentally sharing sensitive information.</span></span> <span data-ttu-id="f2395-105">È possibile scegliere tra le opzioni disponibili in questo articolo per soddisfare al meglio le esigenze dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f2395-105">You can choose from the options in this article to best meet the needs of your organization.</span></span>

## <a name="use-best-practices-for-anyone-links"></a><span data-ttu-id="f2395-106">Usare le procedure consigliate per i collegamenti di tipo “Chiunque”</span><span class="sxs-lookup"><span data-stu-id="f2395-106">Use best practices for Anyone links</span></span>

<span data-ttu-id="f2395-107">Se le persone dell'organizzazione devono eseguire la condivisione non autenticata, ma si teme che il contenuto venga modificato da utenti non autenticati, vedere [Procedure consigliate per la condivisione non autenticata](best-practices-anonymous-sharing.md) per istruzioni su come gestire la condivisione non autenticata nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f2395-107">If people in your organization need to do unauthenticated sharing, but you're concerned about unauthenticated people modifying content, read [Best practices for unauthenticated sharing](best-practices-anonymous-sharing.md) for guidance on how to work with unauthenticated sharing in your organization.</span></span>

## <a name="turn-off-anyone-links"></a><span data-ttu-id="f2395-108">Disattivare i collegamenti di tipo “Chiunque”</span><span class="sxs-lookup"><span data-stu-id="f2395-108">Turn off Anyone links</span></span>

<span data-ttu-id="f2395-109">È consigliabile lasciare abilitati i collegamenti di tipo *Chiunque* per il contenuto appropriato, perché è il modo più semplice per condividere informazioni e contribuisce a ridurre il rischio che gli utenti cerchino altre soluzioni fuori dal controllo del reparto IT.</span><span class="sxs-lookup"><span data-stu-id="f2395-109">We recommend leaving *Anyone* links enabled for appropriate content because it's the easiest way to share and can help reduce the risk of users seeking other solutions that are outside the control of your IT department.</span></span> <span data-ttu-id="f2395-110">I collegamenti di tipo *Chiunque* possono essere inoltrati ad altri, ma l'accesso ai file è disponibile solo per gli utenti che dispongono del collegamento.</span><span class="sxs-lookup"><span data-stu-id="f2395-110">*Anyone* links can be forwarded to others, but file access is only available to those who have the link.</span></span>

<span data-ttu-id="f2395-111">Se si vuole che le persone esterne all'organizzazione eseguano sempre l'autenticazione per accedere al contenuto di SharePoint, Groups o Teams, è possibile disattivare la condivisione *Chiunque*.</span><span class="sxs-lookup"><span data-stu-id="f2395-111">If you always want people outside your organization to authenticate when accessing content in SharePoint, Groups, or Teams, you can turn off *Anyone* sharing.</span></span> <span data-ttu-id="f2395-112">In questo modo si impedisce agli utenti di condividere il contenuto senza autenticazione.</span><span class="sxs-lookup"><span data-stu-id="f2395-112">This will prevent users from unauthenticated sharing of content.</span></span>

<span data-ttu-id="f2395-113">Se si disabilitano i collegamenti di tipo *Chiunque*, gli utenti potranno comunque condividerli facilmente con gli utenti guest utilizzando i collegamenti di tipo *Persone specifiche*.</span><span class="sxs-lookup"><span data-stu-id="f2395-113">If you disable *Anyone* links, users can still easily share with guests using *Specific people* links.</span></span> <span data-ttu-id="f2395-114">In questo caso, per poter accedere al contenuto condiviso, tutte le persone esterne all'organizzazione dovranno eseguire l'autenticazione.</span><span class="sxs-lookup"><span data-stu-id="f2395-114">In this case, all people outside your organization will be required to authenticate before they can access the shared content.</span></span>

<span data-ttu-id="f2395-115">In base alle proprie esigenze, è possibile disabilitare i collegamenti di tipo *Chiunque* per siti specifici o per l'intera organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f2395-115">Depending on your needs, you can disable *Anyone* links for specific sites, or for your whole organization.</span></span>

<span data-ttu-id="f2395-116">Per disattivare i collegamenti di tipo *Chiunque* per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="f2395-116">To turn off *Anyone* links for your organization</span></span>
1. <span data-ttu-id="f2395-117">Nella parte sinistra dell'interfaccia di amministrazione di SharePoint, fare clic su **Condivisione**.</span><span class="sxs-lookup"><span data-stu-id="f2395-117">In the SharePoint admin center, in the left navigation, click **Sharing**.</span></span>
2. <span data-ttu-id="f2395-118">Impostare le impostazioni di condivisione esterna di SharePoint su **Utenti guest nuovi ed esistenti**.</span><span class="sxs-lookup"><span data-stu-id="f2395-118">Set the SharePoint external sharing settings to **New and existing guests**.</span></span>

   ![Screenshot delle impostazioni di condivisione esterna dei siti di SharePoint a livello di organizzazione](../media/sharepoint-organization-external-sharing-controls-new-users.png)

3. <span data-ttu-id="f2395-120">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="f2395-120">Click **Save**.</span></span>

<span data-ttu-id="f2395-121">Per disattivare i collegamenti di tipo *Chiunque* per un sito</span><span class="sxs-lookup"><span data-stu-id="f2395-121">To turn off *Anyone* links for a site</span></span>
1. <span data-ttu-id="f2395-122">Nella parte sinistra dell'interfaccia di amministrazione di SharePoint, espandere **Siti** e fare clic su **Siti attivi**.</span><span class="sxs-lookup"><span data-stu-id="f2395-122">In the SharePoint admin center, in the left navigation, expand **Sites** and click **Active sites**.</span></span>
2. <span data-ttu-id="f2395-123">Selezionare il sito che si vuole configurare.</span><span class="sxs-lookup"><span data-stu-id="f2395-123">Select the site that you want to configure.</span></span>
3. <span data-ttu-id="f2395-124">Sulla barra multifunzione fare clic su **Condivisione**.</span><span class="sxs-lookup"><span data-stu-id="f2395-124">In the ribbon, click **Sharing**.</span></span>
4. <span data-ttu-id="f2395-125">Verificare che la condivisione sia impostata su **Utenti guest nuovi ed esistenti**.</span><span class="sxs-lookup"><span data-stu-id="f2395-125">Ensure that sharing is set to **New and existing guests**.</span></span>

   ![Screenshot delle impostazioni di condivisione esterna dei siti di SharePoint a livello di sito](../media/sharepoint-site-external-sharing-settings.png)

5. <span data-ttu-id="f2395-127">Se si apportano modifiche, fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="f2395-127">If you made changes, click **Save**.</span></span>

## <a name="domain-filtering"></a><span data-ttu-id="f2395-128">Filtro domini</span><span class="sxs-lookup"><span data-stu-id="f2395-128">Domain filtering</span></span>

<span data-ttu-id="f2395-129">È possibile usare gli elenchi di domini consentiti o non consentiti per specificare i domini che gli utenti possono usare quando condividono con persone esterne all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f2395-129">You can use domain allow or deny lists to specify which domains your users can use when sharing with people outside your organization.</span></span>

<span data-ttu-id="f2395-130">Con un elenco di domini consentiti è possibile specificare un elenco di domini in cui gli utenti dell'organizzazione possono condividere con persone esterne all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f2395-130">With an allow list, you can specify a list of domains where users in your organization can share with people outside your organization.</span></span> <span data-ttu-id="f2395-131">La condivisione con altri domini è bloccata.</span><span class="sxs-lookup"><span data-stu-id="f2395-131">Sharing with to other domains is blocked.</span></span> <span data-ttu-id="f2395-132">Se l'organizzazione collabora solo con persone da un elenco di domini specifici, è possibile usare questa funzionalità per impedire la condivisione con altri domini.</span><span class="sxs-lookup"><span data-stu-id="f2395-132">If your organization only collaborates with people from a list of specific domains, you can use this feature to prevent sharing with other domains.</span></span>

<span data-ttu-id="f2395-133">Con un elenco di domini non consentiti è possibile specificare un elenco di domini da cui gli utenti dell'organizzazione non possono condividere con persone esterne all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f2395-133">With a deny list, you can specify a list of domains from which users in your organization cannot share with people outside your organization.</span></span> <span data-ttu-id="f2395-134">La condivisione con i domini elencati è bloccata.</span><span class="sxs-lookup"><span data-stu-id="f2395-134">Sharing with the listed domains is blocked.</span></span> <span data-ttu-id="f2395-135">Questa opzione può essere utile, ad esempio, se si vuole impedire che alcuni concorrenti possano accedere a contenuto della propria organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f2395-135">This can be useful if you have competitors, for example, who you want to prevent from accessing content in your organization.</span></span>

<span data-ttu-id="f2395-136">Gli elenchi di domini consentiti e non consentiti influiscono solo sulle condivisioni con utenti guest.</span><span class="sxs-lookup"><span data-stu-id="f2395-136">The allow and deny lists only affect sharing with guests.</span></span> <span data-ttu-id="f2395-137">Gli utenti possono continuare a condividere contenuti con persone da domini non consentiti tramite i collegamenti di tipo *Chiunque*, se questi non sono stati disabilitati.</span><span class="sxs-lookup"><span data-stu-id="f2395-137">Users can still share with people from prohibited domains by using *Anyone* links if you haven't disabled them.</span></span> <span data-ttu-id="f2395-138">Per ottenere risultati ottimali con gli elenchi di domini consentiti e non consentiti, è consigliabile disabilitare i collegamenti di tipo *Chiunque* come descritto sopra.</span><span class="sxs-lookup"><span data-stu-id="f2395-138">For best results with domain allow and deny lists, consider disabling *Anyone* links as described above.</span></span>

<span data-ttu-id="f2395-139">Per creare un elenco di domini consentiti o non consentiti</span><span class="sxs-lookup"><span data-stu-id="f2395-139">To set up a domain allow or deny list</span></span>
1. <span data-ttu-id="f2395-140">Nella parte sinistra dell'interfaccia di amministrazione di SharePoint, fare clic su **Condivisione**.</span><span class="sxs-lookup"><span data-stu-id="f2395-140">In the SharePoint admin center, in the left navigation, click **Sharing**.</span></span>
2. <span data-ttu-id="f2395-141">In **Impostazioni avanzate per la condivisione esterna** selezionare la casella di controllo **Limitare la condivisione esterna in base al dominio**.</span><span class="sxs-lookup"><span data-stu-id="f2395-141">Under **Advanced settings for external sharing**, select the **Limit external sharing by domain** check box.</span></span>
3. <span data-ttu-id="f2395-142">Fare clic su **Aggiungi domini**.</span><span class="sxs-lookup"><span data-stu-id="f2395-142">Click **Add domains**.</span></span>
4. <span data-ttu-id="f2395-143">Selezionare se si vogliono bloccare i domini, digitare i domini e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="f2395-143">Select whether you want to block domains, type the domains, and click **OK**.</span></span>

   ![Screenshot dell’impostazione di SharePoint Limitare la condivisione esterna in base al dominio](../media/sharepoint-sharing-block-domain.png)

5. <span data-ttu-id="f2395-145">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="f2395-145">Click **Save**.</span></span>

<span data-ttu-id="f2395-146">Se si vuole limitare la condivisione in base al dominio a un livello superiore rispetto a SharePoint e OneDrive, è possibile [consentire o bloccare gli inviti agli utenti B2B da organizzazioni specifiche](/azure/active-directory/b2b/allow-deny-list) in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f2395-146">If you want to limit sharing by domain at a higher level than SharePoint and OneDrive, you can [allow or block invitations to B2B users from specific organizations](/azure/active-directory/b2b/allow-deny-list) in Azure Active Directory.</span></span> <span data-ttu-id="f2395-147">(È necessario configurare l’[anteprima dell'integrazione di SharePoint e OneDrive con Azure AD B2B](/sharepoint/sharepoint-azureb2b-integration-preview) perché queste impostazioni influiscano su SharePoint e OneDrive.)</span><span class="sxs-lookup"><span data-stu-id="f2395-147">(You must configure the [SharePoint and OneDrive integration with Azure AD B2B Preview](/sharepoint/sharepoint-azureb2b-integration-preview) for these settings to affect SharePoint and OneDrive.)</span></span>

## <a name="limit-sharing-of-files-folders-and-sites-with-people-outside-your-organization-to-specified-security-groups"></a><span data-ttu-id="f2395-148">Limitare la condivisione di file, cartelle e siti con persone esterne all'organizzazione a gruppi di sicurezza specifici</span><span class="sxs-lookup"><span data-stu-id="f2395-148">Limit sharing of files, folders, and sites with people outside your organization to specified security groups</span></span>

<span data-ttu-id="f2395-149">È possibile limitare la condivisione di file, cartelle e siti con persone esterne all'organizzazione ai membri di un gruppo di sicurezza specifico.</span><span class="sxs-lookup"><span data-stu-id="f2395-149">You can restrict sharing of files, folders, and sites with people outside your organization to members of a specific security group.</span></span> <span data-ttu-id="f2395-150">Questa opzione è utile se si vuole abilitare la condivisione esterna, ma con un flusso di lavoro di approvazione o un processo di richiesta.</span><span class="sxs-lookup"><span data-stu-id="f2395-150">This is useful if you want to enable external sharing, but with an approval workflow or request process.</span></span> <span data-ttu-id="f2395-151">In alternativa, è possibile richiedere agli utenti di completare un corso di formazione prima che vengano aggiunti al gruppo di sicurezza e sia consentita la condivisione esterna.</span><span class="sxs-lookup"><span data-stu-id="f2395-151">Alternatively, you might require your users to complete a training course before they're added to the security group and are allowed to share externally.</span></span>

<span data-ttu-id="f2395-152">Per limitare la condivisione esterna ai membri di un gruppo di sicurezza</span><span class="sxs-lookup"><span data-stu-id="f2395-152">To limit external sharing to members of a security group</span></span>
1. <span data-ttu-id="f2395-153">Nella parte sinistra dell'[interfaccia di amministrazione di SharePoint](https://admin.microsoft.com/sharepoint), in **Criteri**, fare clic su **Condivisione**.</span><span class="sxs-lookup"><span data-stu-id="f2395-153">In the [SharePoint admin center](https://admin.microsoft.com/sharepoint), in the left navigation, under **Policies**, click **Sharing**.</span></span>
2. <span data-ttu-id="f2395-154">In **Condivisione esterna**, espandere **Altre impostazioni condivisione esterna**.</span><span class="sxs-lookup"><span data-stu-id="f2395-154">Under **External sharing**, expand **More external sharing settings**.</span></span>

3. <span data-ttu-id="f2395-155">Selezionare **Consenti solo agli utenti di gruppi di sicurezza specifici di condividere esternamente** e quindi selezionare **Gestisci i gruppi di sicurezza**.</span><span class="sxs-lookup"><span data-stu-id="f2395-155">Select **Allow only users in specific security groups to share externally**, and then select **Manage security groups**.</span></span>

    ![Screenshot del riquadro Gestisci gruppi di sicurezza](/sharepoint/sharepointonline/media/manage-security-groups.png)

4. <span data-ttu-id="f2395-157">Nella casella **Aggiungi un gruppo di sicurezza** immettere un nome per un gruppo di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="f2395-157">In the **Add a security group** box, enter a name for a security group.</span></span> <span data-ttu-id="f2395-158">Viene visualizzata la finestra del gruppo di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="f2395-158">The security group box appears.</span></span>

5. <span data-ttu-id="f2395-159">Accanto al nome del gruppo di sicurezza, dall’elenco a discesa **Può condividere con** selezionare:</span><span class="sxs-lookup"><span data-stu-id="f2395-159">Next to the security group name, from the **Can share with** dropdown, select either:</span></span>

    - <span data-ttu-id="f2395-160">**Solo utenti autenticati** (impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="f2395-160">**Authenticated guests only** (default)</span></span>
    - <span data-ttu-id="f2395-161">**Chiunque**</span><span class="sxs-lookup"><span data-stu-id="f2395-161">**Anyone**</span></span>

6. <span data-ttu-id="f2395-162">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="f2395-162">Select **Save**.</span></span>

<span data-ttu-id="f2395-163">Si noti che questo influisce su file, cartelle e siti, ma non sui gruppi di Microsoft 365 o su Teams.</span><span class="sxs-lookup"><span data-stu-id="f2395-163">Note that this affects files, folders, and sites, but not Microsoft 365 groups or Teams.</span></span> <span data-ttu-id="f2395-164">Quando i membri invitano gli utenti guest a un gruppo di Microsoft 365 privato o a un team privato in Microsoft Teams, l'invito viene inviato al proprietario del gruppo o del team per l'approvazione.</span><span class="sxs-lookup"><span data-stu-id="f2395-164">When members invite guests to a private Microsoft 365 group or a private team in Microsoft Teams, the invitation is sent to the group or team owner for approval.</span></span>

## <a name="see-also"></a><span data-ttu-id="f2395-165">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f2395-165">See Also</span></span>

[<span data-ttu-id="f2395-166">Creare un ambiente di condivisione guest sicuro</span><span class="sxs-lookup"><span data-stu-id="f2395-166">Create a secure guest sharing environment</span></span>](create-secure-guest-sharing-environment.md)

[<span data-ttu-id="f2395-167">Procedure consigliate per la condivisione di file e cartelle con utenti anonimi</span><span class="sxs-lookup"><span data-stu-id="f2395-167">Best practices for sharing files and folders with anonymous users</span></span>](best-practices-anonymous-sharing.md)