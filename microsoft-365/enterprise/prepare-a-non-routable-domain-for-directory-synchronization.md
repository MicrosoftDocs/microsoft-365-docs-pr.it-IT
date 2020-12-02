---
title: Preparare un dominio non instradabile per la sincronizzazione della directory
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365E_SetupDirSyncLocalDir
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: e7968303-c234-46c4-b8b0-b5c93c6d57a7
description: Informazioni su cosa fare se si dispone di un dominio non routale associato agli utenti locali prima di eseguire la sincronizzazione con Microsoft 365.
ms.openlocfilehash: f38f6143b6e26b2849c174f74c94d009ddea73cd
ms.sourcegitcommit: 4cbb4ec26f022f5f9d9481f55a8a6ee8406968d2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/01/2020
ms.locfileid: "49527722"
---
# <a name="prepare-a-non-routable-domain-for-directory-synchronization"></a><span data-ttu-id="53dc3-103">Preparare un dominio non instradabile per la sincronizzazione della directory</span><span class="sxs-lookup"><span data-stu-id="53dc3-103">Prepare a non-routable domain for directory synchronization</span></span>
<span data-ttu-id="53dc3-104">Quando si sincronizza la directory locale con Microsoft 365, è necessario disporre di un dominio verificato in Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="53dc3-104">When you synchronize your on-premises directory with Microsoft 365 you have to have a verified domain in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="53dc3-105">Vengono sincronizzati solo i nomi dell'entità utente (UPN, User Principal Name) associati al dominio locale.</span><span class="sxs-lookup"><span data-stu-id="53dc3-105">Only the User Principal Names (UPN) that are associated with the on-premises domain are synchronized.</span></span> <span data-ttu-id="53dc3-106">Tuttavia, qualsiasi UPN che contiene un dominio non instradabile, ad esempio Local (come billa@contoso. local), verrà sincronizzato con un dominio. onmicrosoft.com (come billa@contoso.onmicrosoft.com).</span><span class="sxs-lookup"><span data-stu-id="53dc3-106">However, any UPN that contains an non-routable domain, for example .local (like billa@contoso.local), will be synchronized to an .onmicrosoft.com domain (like billa@contoso.onmicrosoft.com).</span></span> 

<span data-ttu-id="53dc3-107">Se attualmente si utilizza un dominio. local per gli account utente in servizi di dominio Active Directory, si consiglia di modificarli in modo da utilizzare un dominio verificato (come billa@contoso.com) per sincronizzarlo correttamente con il dominio Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="53dc3-107">If you currently use a .local domain for your user accounts in Active Directory Domain Services (AD DS) it's recommended that you change them to use a verified domain (like billa@contoso.com) in order to properly sync with your Microsoft 365 domain.</span></span>
  
## <a name="what-if-i-only-have-a-local-on-premises-domain"></a><span data-ttu-id="53dc3-108">Cosa succede se si dispone di un solo dominio locale?</span><span class="sxs-lookup"><span data-stu-id="53dc3-108">What if I only have a .local on-premises domain?</span></span>

<span data-ttu-id="53dc3-109">Lo strumento più recente che è possibile utilizzare per la sincronizzazione di servizi di dominio Active Directory ad Azure AD è denominato Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="53dc3-109">The most recent tool you can use for synchronizing your AD DS to Azure AD is named Azure AD Connect.</span></span> <span data-ttu-id="53dc3-110">Per ulteriori informazioni, vedere [integrazione delle identità locali con Azure ad](https://docs.microsoft.com/azure/architecture/reference-architectures/identity/azure-ad).</span><span class="sxs-lookup"><span data-stu-id="53dc3-110">For more information, see [Integrating your on-premises identities with Azure AD](https://docs.microsoft.com/azure/architecture/reference-architectures/identity/azure-ad).</span></span>
  
<span data-ttu-id="53dc3-111">Azure AD Connect sincronizza l'UPN e la password degli utenti in modo che gli utenti possano accedere con le stesse credenziali che utilizzano in locale.</span><span class="sxs-lookup"><span data-stu-id="53dc3-111">Azure AD Connect synchronizes your users' UPN and password so that users can sign in with the same credentials they use on-premises.</span></span> <span data-ttu-id="53dc3-112">Tuttavia, Azure AD Connect sincronizza solo gli utenti nei domini che sono stati verificati da Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="53dc3-112">However, Azure AD Connect only synchronizes users to domains that are verified by Microsoft 365.</span></span> <span data-ttu-id="53dc3-113">Questo significa che il dominio è stato verificato anche da Azure AD, in quanto le identità di Microsoft 365 sono gestite da Azure AD.</span><span class="sxs-lookup"><span data-stu-id="53dc3-113">This means that the domain also is verified by Azure AD because Microsoft 365 identities are managed by Azure AD.</span></span> <span data-ttu-id="53dc3-114">In altre parole, il dominio deve essere un dominio Internet valido (ad esempio,. com,. org, .NET,. US, ecc.).</span><span class="sxs-lookup"><span data-stu-id="53dc3-114">In other words, the domain has to be a valid Internet domain (for example, .com, .org, .net, .us, etc.).</span></span> <span data-ttu-id="53dc3-115">Se in servizi di dominio Active Directory interno viene utilizzato solo un domini non instradabile (ad esempio,. local), questo non può corrispondere al dominio verificato in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="53dc3-115">If your internal AD DS only uses a non-routable domain (for example, .local), this can't possibly match the verified domain you have on Microsoft 365.</span></span> <span data-ttu-id="53dc3-116">È possibile risolvere il problema modificando il dominio principale nell'ambiente di servizio locale di AD DS oppure aggiungendo uno o più suffissi UPN.</span><span class="sxs-lookup"><span data-stu-id="53dc3-116">You can fix this issue by either changing your primary domain in your on premises AD DS, or by adding one or more UPN suffixes.</span></span>
  
### <a name="change-your-primary-domain"></a><span data-ttu-id="53dc3-117">**Modificare il dominio principale**</span><span class="sxs-lookup"><span data-stu-id="53dc3-117">**Change your primary domain**</span></span>

<span data-ttu-id="53dc3-118">Modificare il dominio principale in un dominio verificato in Microsoft 365, ad esempio contoso.com.</span><span class="sxs-lookup"><span data-stu-id="53dc3-118">Change your primary domain to a domain you have verified in Microsoft 365, for example, contoso.com.</span></span> <span data-ttu-id="53dc3-119">Ogni utente con il dominio contoso. local viene quindi aggiornato a contoso.com.</span><span class="sxs-lookup"><span data-stu-id="53dc3-119">Every user that has the domain contoso.local is then updated to contoso.com.</span></span> <span data-ttu-id="53dc3-120">Si tratta di un processo molto coinvolto, tuttavia, e una soluzione più semplice è descritta nella sezione seguente.</span><span class="sxs-lookup"><span data-stu-id="53dc3-120">This is a very involved process, however, and an easier solution is described in the following section.</span></span>
  
### <a name="add-upn-suffixes-and-update-your-users-to-them"></a><span data-ttu-id="53dc3-121">**Aggiungere suffissi UPN e aggiornare gli utenti**</span><span class="sxs-lookup"><span data-stu-id="53dc3-121">**Add UPN suffixes and update your users to them**</span></span>

<span data-ttu-id="53dc3-122">È possibile risolvere il problema. local registrando nuovi suffissi UPN o suffissi in servizi di dominio Active Directory in modo che corrispondano a quelli che sono stati verificati in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="53dc3-122">You can solve the .local problem by registering new UPN suffix or suffixes in AD DS to match the domain (or domains) you verified in Microsoft 365.</span></span> <span data-ttu-id="53dc3-123">Dopo aver registrato il nuovo suffisso, è possibile aggiornare l'utente UPN per sostituire il file. local con il nuovo nome di dominio, ad esempio in modo che un account utente sia simile a billa@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="53dc3-123">After you register the new suffix, you update the user UPNs to replace the .local with the new domain name for example so that a user account looks like billa@contoso.com.</span></span>
  
<span data-ttu-id="53dc3-124">Dopo aver aggiornato l'UPN per l'utilizzo del dominio verificato, si è pronti per sincronizzare AD DS locale con Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="53dc3-124">After you have updated the UPNs to use the verified domain, you are ready to synchronize your on-premises AD DS with Microsoft 365.</span></span>
  
 <span data-ttu-id="53dc3-125">**Passaggio 1: aggiungere il nuovo suffisso UPN**</span><span class="sxs-lookup"><span data-stu-id="53dc3-125">**Step 1: Add the new UPN suffix**</span></span>
  
1. <span data-ttu-id="53dc3-126">Nel controller di dominio ad DS, in Server Manager scegliere **gli strumenti** \> **domini e trust di Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="53dc3-126">On the AD DS domain controller, in the Server Manager choose **Tools** \> **Active Directory Domains and Trusts**.</span></span>
    
    <span data-ttu-id="53dc3-127">**In alternativa, se non si dispone di Windows Server 2012**</span><span class="sxs-lookup"><span data-stu-id="53dc3-127">**Or, if you don't have Windows Server 2012**</span></span>
    
    <span data-ttu-id="53dc3-128">Premere il **tasto Windows + R** per aprire la finestra di dialogo **Esegui** e quindi digitare Domain. msc e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="53dc3-128">Press **Windows key + R** to open the **Run** dialog, and then type in Domain.msc, and then choose **OK**.</span></span>
    
    ![Scegliere domini e trust di Active Directory.](../media/46b6e007-9741-44af-8517-6f682e0ac974.png)
  
2. <span data-ttu-id="53dc3-130">Nella finestra **domini e trust di Active Directory** fare clic con il pulsante destro del mouse su **domini e trust di Active Directory** e quindi scegliere **proprietà**.</span><span class="sxs-lookup"><span data-stu-id="53dc3-130">On the **Active Directory Domains and Trusts** window, right-click **Active Directory Domains and Trusts**, and then choose **Properties**.</span></span>
    
    ![Fare clic con il pulsante destro del mouse su domini e trust di Active Directory e scegliere Proprietà](../media/39d20812-ffb5-4ba9-8d7b-477377ac360d.png)
  
3. <span data-ttu-id="53dc3-132">Nella scheda **suffissi** UPN, nella casella **suffissi UPN alternativi** , digitare il nuovo suffisso UPN o suffissi, quindi fare clic su **Aggiungi** \> **applica**.</span><span class="sxs-lookup"><span data-stu-id="53dc3-132">On the **UPN Suffixes** tab, in the **Alternative UPN Suffixes** box, type your new UPN suffix or suffixes, and then choose **Add** \> **Apply**.</span></span>
    
    ![Aggiungere un nuovo suffisso UPN](../media/a4aaf919-7adf-469a-b93f-83ef284c0915.PNG)
  
    <span data-ttu-id="53dc3-134">Scegliere **OK** al termine dell'aggiunta di suffissi.</span><span class="sxs-lookup"><span data-stu-id="53dc3-134">Choose **OK** when you're done adding suffixes.</span></span> 
    
 <span data-ttu-id="53dc3-135">**Passaggio 2: modificare il suffisso UPN per gli utenti esistenti**</span><span class="sxs-lookup"><span data-stu-id="53dc3-135">**Step 2: Change the UPN suffix for existing users**</span></span>
  
1. <span data-ttu-id="53dc3-136">Nel controller di dominio ad DS, in Server Manager scegliere **strumenti** \> **e utenti di Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="53dc3-136">On the AD DS domain controller, in the Server Manager choose **Tools** \> **Active Directory Users and Computers**.</span></span>
    
    <span data-ttu-id="53dc3-137">**In alternativa, se non si dispone di Windows Server 2012**</span><span class="sxs-lookup"><span data-stu-id="53dc3-137">**Or, if you don't have Windows Server 2012**</span></span>
    
    <span data-ttu-id="53dc3-138">Premere il **tasto Windows + R** per aprire la finestra di dialogo **Esegui** e quindi digitare dsa. msc e quindi fare clic su **OK** .</span><span class="sxs-lookup"><span data-stu-id="53dc3-138">Press **Windows key + R** to open the **Run** dialog, and then type in Dsa.msc, and then click **OK**</span></span>
    
2. <span data-ttu-id="53dc3-139">Selezionare un utente, fare clic con il pulsante destro del mouse e quindi scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="53dc3-139">Select a user, right-click, and then choose **Properties**.</span></span>
    
3. <span data-ttu-id="53dc3-140">Nell'elenco a discesa suffisso UPN della scheda **account** scegliere il nuovo suffisso UPN e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="53dc3-140">On the **Account** tab, in the UPN suffix drop-down list, choose the new UPN suffix, and then choose **OK**.</span></span>
    
    ![Aggiungere un nuovo suffisso UPN per un utente](../media/54876751-49f0-48cc-b864-2623c4835563.png)
  
4. <span data-ttu-id="53dc3-142">Completare questa procedura per ogni utente.</span><span class="sxs-lookup"><span data-stu-id="53dc3-142">Complete these steps for every user.</span></span>
    
   
### <a name="you-can-also-use-windows-powershell-to-change-the-upn-suffix-for-all-users"></a><span data-ttu-id="53dc3-143">**È inoltre possibile utilizzare Windows PowerShell per modificare il suffisso UPN per tutti gli utenti**</span><span class="sxs-lookup"><span data-stu-id="53dc3-143">**You can also use Windows PowerShell to change the UPN suffix for all users**</span></span>

<span data-ttu-id="53dc3-144">Se si dispone di molti utenti da aggiornare, è più facile usare Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="53dc3-144">If you have a lot of users to update, it is easier to use Windows PowerShell.</span></span> <span data-ttu-id="53dc3-145">Nell'esempio seguente vengono utilizzati i cmdlet [Get-ADUser](https://go.microsoft.com/fwlink/p/?LinkId=624312) e [set-aduser](https://go.microsoft.com/fwlink/p/?LinkId=624313) per modificare tutti i suffissi contoso. local in contoso.com.</span><span class="sxs-lookup"><span data-stu-id="53dc3-145">The following example uses the cmdlets [Get-ADUser](https://go.microsoft.com/fwlink/p/?LinkId=624312) and [Set-ADUser](https://go.microsoft.com/fwlink/p/?LinkId=624313) to change all contoso.local suffixes to contoso.com.</span></span> 

<span data-ttu-id="53dc3-146">Ad esempio, è possibile eseguire i seguenti comandi di Windows PowerShell per aggiornare tutti i suffissi contoso. local a contoso.com:</span><span class="sxs-lookup"><span data-stu-id="53dc3-146">For example, you could run the following Windows PowerShell commands to update all contoso.local suffixes to contoso.com:</span></span>
    
  ```powershell
  $LocalUsers = Get-ADUser -Filter "UserPrincipalName -like '*contoso.local'" -Properties userPrincipalName -ResultSetSize $null
  $LocalUsers | foreach {$newUpn = $_.UserPrincipalName.Replace("@contoso.local","@contoso.com"); $_ | Set-ADUser -UserPrincipalName $newUpn}
  ```

<span data-ttu-id="53dc3-147">Per ulteriori informazioni sull'utilizzo di Windows PowerShell in servizi di dominio Active Directory, vedere il [modulo di Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=624314) .</span><span class="sxs-lookup"><span data-stu-id="53dc3-147">See [Active Directory Windows PowerShell module](https://go.microsoft.com/fwlink/p/?LinkId=624314) to learn more about using Windows PowerShell in AD DS.</span></span> 

