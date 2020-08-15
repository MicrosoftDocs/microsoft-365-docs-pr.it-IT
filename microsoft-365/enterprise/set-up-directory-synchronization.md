---
title: Configurare la sincronizzazione della directory per Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 06/15/2020
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom: Adm_O365
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MED15
- MBS150
- BCS160
ms.assetid: 1b3b5318-6977-42ed-b5c7-96fa74b08846
description: Informazioni su come configurare la sincronizzazione delle directory tra Microsoft 365 e Active Directory locale.
ms.openlocfilehash: 3a846a6c558f221c1869dce6da27e3d34680f75d
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691011"
---
# <a name="set-up-directory-synchronization-for-microsoft-365"></a><span data-ttu-id="0d97e-103">Configurare la sincronizzazione della directory per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0d97e-103">Set up directory synchronization for Microsoft 365</span></span>

<span data-ttu-id="0d97e-104">*Questo articolo può essere applicato sia a Microsoft 365 Enterprise che a Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="0d97e-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="0d97e-105">Microsoft 365 utilizza un tenant di Azure Active Directory (Azure AD) per l'archiviazione e la gestione delle identità per l'autenticazione e le autorizzazioni per l'accesso alle risorse basate su cloud.</span><span class="sxs-lookup"><span data-stu-id="0d97e-105">Microsoft 365 uses an Azure Active Directory (Azure AD) tenant to store and manage identities for authentication and permissions to access cloud-based resources.</span></span> 

<span data-ttu-id="0d97e-106">Se si dispone di servizi di dominio Active Directory (AD DS) locali, è possibile sincronizzare gli account utente, i gruppi e i contatti di AD DS con il tenant di Azure AD della sottoscrizione Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0d97e-106">If you have an on-premises Active Directory Domain Services (AD DS), you can synchronize your AD DS user accounts, groups, and contacts with the Azure AD tenant of your Microsoft 365 subscription.</span></span> <span data-ttu-id="0d97e-107">Si tratta di una identità ibrida per Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0d97e-107">This is hybrid identity for Microsoft 365.</span></span> <span data-ttu-id="0d97e-108">i cui componenti sono descritti di seguito.</span><span class="sxs-lookup"><span data-stu-id="0d97e-108">Here are its components.</span></span>

![Componenti della sincronizzazione della directory per Microsoft 365](../media/about-microsoft-365-identity/hybrid-identity.png)

<span data-ttu-id="0d97e-110">Azure AD Connect viene eseguito in un server locale e consente di sincronizzare il servizio AD DS con il tenant di Azure AD.</span><span class="sxs-lookup"><span data-stu-id="0d97e-110">Azure AD Connect runs on an on-premises server and synchronizes your AD DS with the Azure AD tenant.</span></span> <span data-ttu-id="0d97e-111">Oltre alla sincronizzazione della directory, è anche possibile specificare le opzioni di autenticazione seguenti:</span><span class="sxs-lookup"><span data-stu-id="0d97e-111">Along with directory synchronization, you can also specify these authentication options:</span></span>

- <span data-ttu-id="0d97e-112">Sincronizzazione dell'hash delle password (PHS)</span><span class="sxs-lookup"><span data-stu-id="0d97e-112">Password hash synchronization (PHS)</span></span>

  <span data-ttu-id="0d97e-113">L'autenticazione viene eseguita direttamente da Azure AD.</span><span class="sxs-lookup"><span data-stu-id="0d97e-113">Azure AD performs the authentication itself.</span></span>

- <span data-ttu-id="0d97e-114">Autenticazione pass-through (PTA)</span><span class="sxs-lookup"><span data-stu-id="0d97e-114">Pass-through authentication (PTA)</span></span>

  <span data-ttu-id="0d97e-115">L'autenticazione di Azure AD viene eseguita da AD DS.</span><span class="sxs-lookup"><span data-stu-id="0d97e-115">Azure AD has AD DS perform the authentication.</span></span>

- <span data-ttu-id="0d97e-116">Autenticazione federata</span><span class="sxs-lookup"><span data-stu-id="0d97e-116">Federated authentication</span></span>

  <span data-ttu-id="0d97e-117">Azure AD reindirizza il computer client richiedendo l'autenticazione per contattare un altro provider di identità.</span><span class="sxs-lookup"><span data-stu-id="0d97e-117">Azure AD redirects the client computer requesting authentication to contact another identity provider.</span></span>

<span data-ttu-id="0d97e-118">Per altre informazioni, vedere [Identità ibride](plan-for-directory-synchronization.md).</span><span class="sxs-lookup"><span data-stu-id="0d97e-118">See [Hybrid identities](plan-for-directory-synchronization.md) for more information.</span></span>
  
## <a name="1-review-prerequisites-for-azure-ad-connect"></a><span data-ttu-id="0d97e-119">1. Esaminare i prerequisiti per Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="0d97e-119">1. Review prerequisites for Azure AD Connect</span></span>

<span data-ttu-id="0d97e-120">È possibile ottenere una sottoscrizione gratuita AD Azure AD con l'abbonamento a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0d97e-120">You get a free Azure AD subscription with your Microsoft 365 subscription.</span></span> <span data-ttu-id="0d97e-121">Quando si configura la sincronizzazione della directory, si installa Azure AD Connect in uno dei server locali.</span><span class="sxs-lookup"><span data-stu-id="0d97e-121">When you set up directory synchronization, you will install Azure AD Connect on one of your on-premises servers.</span></span>
  
<span data-ttu-id="0d97e-122">Per Microsoft 365 è necessario:</span><span class="sxs-lookup"><span data-stu-id="0d97e-122">For Microsoft 365 you'll need to:</span></span>
  
- <span data-ttu-id="0d97e-123">Verificare il dominio locale.</span><span class="sxs-lookup"><span data-stu-id="0d97e-123">Verify your on-premises domain.</span></span> <span data-ttu-id="0d97e-124">La procedura guidata di Azure AD Connect illustra i passaggi necessari per questa operazione.</span><span class="sxs-lookup"><span data-stu-id="0d97e-124">The Azure AD Connect wizard guides you through this.</span></span>
- <span data-ttu-id="0d97e-125">Ottenere i nomi utente e le password per gli account di amministrazione del tenant di Microsoft 365 e di servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="0d97e-125">Obtain the user names and passwords for the admin accounts of your Microsoft 365 tenant and AD DS.</span></span>

<span data-ttu-id="0d97e-126">Per il server locale in cui si installa Azure AD Connect, sono necessari:</span><span class="sxs-lookup"><span data-stu-id="0d97e-126">For your on-premises server on which you install Azure AD Connect, you'll need:</span></span>
  
|<span data-ttu-id="0d97e-127">**Sistema operativo server**</span><span class="sxs-lookup"><span data-stu-id="0d97e-127">**Server OS**</span></span>|<span data-ttu-id="0d97e-128">**Altro software**</span><span class="sxs-lookup"><span data-stu-id="0d97e-128">**Other software**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0d97e-129">Windows Server 2012 R2 e versioni successive</span><span class="sxs-lookup"><span data-stu-id="0d97e-129">Windows Server 2012 R2 and later</span></span> | <span data-ttu-id="0d97e-130">- PowerShell viene installato per impostazione predefinita, pertanto non è richiesta alcuna azione.</span><span class="sxs-lookup"><span data-stu-id="0d97e-130">- PowerShell is installed by default, no action is required.</span></span>  <br> <span data-ttu-id="0d97e-131">- .NET 4.5.1 e versioni successive sono disponibili tramite Windows Update.</span><span class="sxs-lookup"><span data-stu-id="0d97e-131">- Net 4.5.1 and later releases are offered through Windows Update.</span></span> <span data-ttu-id="0d97e-132">Assicurarsi di aver installato gli aggiornamenti più recenti di Windows Server nel Pannello di controllo.</span><span class="sxs-lookup"><span data-stu-id="0d97e-132">Make sure you have installed the latest updates to Windows Server in the Control Panel.</span></span> |
|<span data-ttu-id="0d97e-133">Windows Server 2008 R2 con Service Pack 1 (SP1)\*\* o Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="0d97e-133">Windows Server 2008 R2 with Service Pack 1 (SP1)\*\* or Windows Server 2012</span></span> | <span data-ttu-id="0d97e-134">- La versione più recente di PowerShell è disponibile in Windows Management Framework 4.0.</span><span class="sxs-lookup"><span data-stu-id="0d97e-134">- The latest version of PowerShell is available in Windows Management Framework 4.0.</span></span> <span data-ttu-id="0d97e-135">Cercarla nell'[Area download Microsoft](https://go.microsoft.com/fwlink/p/?LinkId=717996).</span><span class="sxs-lookup"><span data-stu-id="0d97e-135">Search for it on [Microsoft Download Center](https://go.microsoft.com/fwlink/p/?LinkId=717996).</span></span>  <br> <span data-ttu-id="0d97e-136">- .NET 4.5.1 e versioni successive sono disponibili nell'[Area download Microsoft](https://go.microsoft.com/fwlink/p/?LinkId=717996).</span><span class="sxs-lookup"><span data-stu-id="0d97e-136">- .Net 4.5.1 and later releases are available on [Microsoft Download Center](https://go.microsoft.com/fwlink/p/?LinkId=717996).</span></span> |
|<span data-ttu-id="0d97e-137">Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="0d97e-137">Windows Server 2008</span></span> | <span data-ttu-id="0d97e-138">- La versione supportata più recente di PowerShell è disponibile in Windows Management Framework 3.0, scaricabile dall'[Area download Microsoft](https://go.microsoft.com/fwlink/p/?LinkId=717996).</span><span class="sxs-lookup"><span data-stu-id="0d97e-138">- The latest supported version of PowerShell is available in Windows Management Framework 3.0, available on [Microsoft Download Center](https://go.microsoft.com/fwlink/p/?LinkId=717996).</span></span>  <br> <span data-ttu-id="0d97e-139">- .NET 4.5.1 e versioni successive sono disponibili nell'[Area download Microsoft](https://go.microsoft.com/fwlink/p/?LinkId=717996).</span><span class="sxs-lookup"><span data-stu-id="0d97e-139">- .Net 4.5.1 and later releases are available on [Microsoft Download Center](https://go.microsoft.com/fwlink/p/?LinkId=717996).</span></span> |

<span data-ttu-id="0d97e-140">Per informazioni dettagliate sui requisiti hardware, software, per account e autorizzazioni e certificati SSL e sui limiti degli oggetti per Azure AD Connect, vedere [Prerequisiti di Azure Active Directory Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites).</span><span class="sxs-lookup"><span data-stu-id="0d97e-140">See [Prerequisites for Azure Active Directory Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites) for the details of hardware, software, account and permissions requirements, SSL certificate requirements, and object limits for Azure AD Connect.</span></span>
  
<span data-ttu-id="0d97e-141">È anche possibile esaminare la [cronologia di rilascio delle versioni](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-version-history) di Azure AD Connect per vedere cosa include e quali problemi sono stati risolti in ogni versione.</span><span class="sxs-lookup"><span data-stu-id="0d97e-141">You can also review the Azure AD Connect [version release history](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-version-history) to see what is included and fixed in each release.</span></span>

## <a name="2-install-azure-ad-connect-and-configure-directory-synchronization"></a><span data-ttu-id="0d97e-142">2. Installare Azure AD Connect e configurare la sincronizzazione della directory</span><span class="sxs-lookup"><span data-stu-id="0d97e-142">2. Install Azure AD Connect and configure directory synchronization</span></span>

<span data-ttu-id="0d97e-143">Prima di iniziare, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0d97e-143">Before you begin, make sure you have:</span></span>

- <span data-ttu-id="0d97e-144">Il nome utente e la password di un amministratore globale di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0d97e-144">The user name and password of a Microsoft 365 global admin</span></span>
- <span data-ttu-id="0d97e-145">Assicurarsi di disporre del nome utente e della password di un amministratore del dominio di AD DS</span><span class="sxs-lookup"><span data-stu-id="0d97e-145">The user name and password of an AD DS domain administrator</span></span>
- <span data-ttu-id="0d97e-146">Scegliere il metodo di autenticazione, tra PHS, PTA e federata</span><span class="sxs-lookup"><span data-stu-id="0d97e-146">Which authentication method (PHS, PTA, federated)</span></span>
- <span data-ttu-id="0d97e-147">Indicare se si intende usare [Accesso Single Sign-On facile di Azure AD](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sso)</span><span class="sxs-lookup"><span data-stu-id="0d97e-147">Whether you want to use [Azure AD Seamless Single Sign-on (SSO)](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sso)</span></span>

<span data-ttu-id="0d97e-148">Eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="0d97e-148">Follow these steps:</span></span>

1. <span data-ttu-id="0d97e-149">Accedere all'[interfaccia di amministrazione di Microsoft 365](https://admin.microsoft.com) (https://admin.microsoft.com) e scegliere **Utenti** \> **Utenti attivi** nel riquadro di spostamento sinistro.</span><span class="sxs-lookup"><span data-stu-id="0d97e-149">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) (https://admin.microsoft.com) and choose **Users** \> **Active Users** on the left navigation.</span></span>
2. <span data-ttu-id="0d97e-150">Nella pagina **utenti attivi** , scegliere **altro** (tre punti) \> **sincronizzazione della directory**.</span><span class="sxs-lookup"><span data-stu-id="0d97e-150">On the **Active users** page, choose **More** (three dots) \> **Directory synchronization**.</span></span>
  
3. <span data-ttu-id="0d97e-151">Nella pagina **preparazione di Azure Active Directory** selezionare l' **area download per ottenere il collegamento dello strumento Azure ad Connect** per iniziare.</span><span class="sxs-lookup"><span data-stu-id="0d97e-151">On the **Azure Active Directory preparation** page, select the **Go to the Download center to get the Azure AD Connect tool** link to get started.</span></span> 
4. <span data-ttu-id="0d97e-152">Seguire la procedura in [Roadmap di installazione di Azure AD Connect e Azure AD Connect Health](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-roadmap).</span><span class="sxs-lookup"><span data-stu-id="0d97e-152">Follow the steps in [Azure AD Connect and Azure AD Connect Health installation roadmap](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-roadmap).</span></span>

## <a name="3-finish-setting-up-domains"></a><span data-ttu-id="0d97e-153">3. Completare la configurazione dei domini</span><span class="sxs-lookup"><span data-stu-id="0d97e-153">3. Finish setting up domains</span></span>

<span data-ttu-id="0d97e-154">Seguire la procedura descritta in [create DNS Records for Microsoft 365 quando si gestiscono i record DNS](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) per completare la configurazione dei domini.</span><span class="sxs-lookup"><span data-stu-id="0d97e-154">Follow the steps in [Create DNS records for Microsoft 365 when you manage your DNS records](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) to finish setting up your domains.</span></span>

## <a name="next-step"></a><span data-ttu-id="0d97e-155">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="0d97e-155">Next step</span></span>

<span data-ttu-id="0d97e-156">[Assegnare licenze agli account utente](assign-licenses-to-user-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="0d97e-156">[Assign licenses to user accounts](assign-licenses-to-user-accounts.md)</span></span>
