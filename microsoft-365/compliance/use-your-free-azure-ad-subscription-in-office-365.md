---
title: Utilizzare la sottoscrizione di Azure Active Directory gratuita in Office 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: d104fb44-1c42-4541-89a6-1f67be22e4ad
description: Informazioni su come accedere ad Azure Active Directory, incluso nell'abbonamento a Office 365 a pagamento dell'organizzazione.
ms.openlocfilehash: fe3829d349e5721ebdcf0688c1f5b2bd3c9f7f45
ms.sourcegitcommit: 21338a9287017a66298e0ff557e80051946ebf13
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/11/2020
ms.locfileid: "42604093"
---
# <a name="use-your-free-azure-active-directory-subscription-in-office-365"></a><span data-ttu-id="50ac0-103">Utilizzare la sottoscrizione di Azure Active Directory gratuita in Office 365</span><span class="sxs-lookup"><span data-stu-id="50ac0-103">Use your free Azure Active Directory subscription in Office 365</span></span>

<span data-ttu-id="50ac0-p101">Se l'organizzazione ha una sottoscrizione a pagamento a Office 365, Microsoft Dynamics CRM Online, Enterprise Mobility Suite o altri servizi Microsoft, si dispone di una sottoscrizione gratuita a Microsoft Azure Active Directory. Gli amministratori possono usare Azure AD per creare e gestire account utente e di gruppo. Per usare Azure AD, basta andare al portale di Azure e accedere utilizzando il tuo account Office 365.</span><span class="sxs-lookup"><span data-stu-id="50ac0-p101">If your organization has a paid subscription to Office 365, Microsoft Dynamics CRM Online, Enterprise Mobility Suite, or other Microsoft services, you have a free subscription to Microsoft Azure Active Directory. You and other admins can use Azure AD to create and manage user and group accounts. To use Azure AD, just go to the Azure portal and sign in using your Office 365 account.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="50ac0-107">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="50ac0-107">Before you begin</span></span>

<span data-ttu-id="50ac0-p102">Usare una sessione di esplorazione privata (non una sessione normale) per accedere al portale di Azure (nel passaggio 1 in basso) poiché in questo modo si evita di comunicare ad Azure le credenziali usate per accedere. Per aprire una sessione InPrivate Browsing in Microsoft Edge, Internet Explorer o Mozilla FireFox, basta premere CTRL+MAIUSC+P. Per aprire una sessione di esplorazione privata in Google Chrome (chiamata finestra di navigazione in incognito), premere CTRL+MAIUSC+N.</span><span class="sxs-lookup"><span data-stu-id="50ac0-p102">Use a private browsing session (not a regular session) to access the Azure portal (in step 1 below) because this will prevent the credential that you are currently logged on with from being passed to Azure. To open an InPrivate Browsing session in Microsoft Edge, Internet Explorer, or Mozilla FireFox, just press CTRL+SHIFT+P. To open a private browsing session in Google Chrome (called an incognito window), press CTRL+SHIFT+N.</span></span>

## <a name="access-azure-active-directory"></a><span data-ttu-id="50ac0-111">Accedere ad Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="50ac0-111">Access Azure Active Directory</span></span>

1. <span data-ttu-id="50ac0-112">Andare a [portal.azure.com](https://portal.azure.com) e accedere con il proprio account professionale o studente di Office 365.</span><span class="sxs-lookup"><span data-stu-id="50ac0-112">Go to [portal.azure.com](https://portal.azure.com) and sign in with your Office 365 work or student account.</span></span>

2. <span data-ttu-id="50ac0-113">Nel riquadro di spostamento a sinistra nel portale di Azure, fare clic su **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="50ac0-113">In the left navigation pane in the Azure portal, click **Azure Active Directory**.</span></span>

    ![Fare clic su Azure Active Directory nel riquadro di spostamento a sinistra nel portale di Azure.](../media/97d2d72f-ac20-46ab-898c-851f6009b453.png)

    <span data-ttu-id="50ac0-115">Viene visualizzata l'interfaccia di amministrazione di **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="50ac0-115">The **Azure Active Directory** admin center is displayed.</span></span>

## <a name="more-information"></a><span data-ttu-id="50ac0-116">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="50ac0-116">More information</span></span>

- <span data-ttu-id="50ac0-117">Un abbonamento gratuito ad Azure Active Directory non include il report delle attività di accesso.</span><span class="sxs-lookup"><span data-stu-id="50ac0-117">A free Azure Active Directory subscription does not include the Sign-ins activity report.</span></span> <span data-ttu-id="50ac0-118">Per registrare l'attività di accesso (che può essere utile in caso di violazione dei dati), è necessario un abbonamento ad Azure Active Directory Premium.</span><span class="sxs-lookup"><span data-stu-id="50ac0-118">To record sign-in activity (which can be useful in the event of a data breach), you need an Azure Active Directory Premium subscription.</span></span> <span data-ttu-id="50ac0-119">Per altre informazioni, vedere [Per quanto tempo Azure AD archivia i dati?](https://docs.microsoft.com/azure/active-directory/reports-monitoring/reference-reports-data-retention#how-long-does-azure-ad-store-the-data)</span><span class="sxs-lookup"><span data-stu-id="50ac0-119">For more information, see [How long does Azure AD store the data?](https://docs.microsoft.com/azure/active-directory/reports-monitoring/reference-reports-data-retention#how-long-does-azure-ad-store-the-data).</span></span>

- <span data-ttu-id="50ac0-120">È anche possibile accedere all'interfaccia di amministrazione di **Azure Active Directory** dall'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="50ac0-120">You can also access the **Azure Active Directory** admin center from the Microsoft 365 admin center.</span></span> <span data-ttu-id="50ac0-121">Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft 365 fare clic su **Interfacce di amministrazione** \> **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="50ac0-121">In the left navigation pane of the Microsoft 365 admin center, click **Admin centers** \> **Azure Active Directory**.</span></span>

- <span data-ttu-id="50ac0-122">Per informazioni sulla gestione degli utenti e dei gruppi e sull'esecuzione di altre attività di gestione delle directory, vedere [Gestione della directory di Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-administer).</span><span class="sxs-lookup"><span data-stu-id="50ac0-122">For information about managing users and groups and performing other directory management tasks, see [Manage your Azure AD directory](https://docs.microsoft.com/azure/active-directory/active-directory-administer).</span></span>
