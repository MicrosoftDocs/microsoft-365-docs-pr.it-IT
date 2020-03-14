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
ms.openlocfilehash: 40ed5808f6e921a3649af408ee078dba64167bb3
ms.sourcegitcommit: dcea75af89f5f80ec6670346ee176407e043de54
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "42610593"
---
# <a name="use-your-free-azure-active-directory-subscription-in-office-365"></a><span data-ttu-id="111a0-103">Utilizzare la sottoscrizione di Azure Active Directory gratuita in Office 365</span><span class="sxs-lookup"><span data-stu-id="111a0-103">Use your free Azure Active Directory subscription in Office 365</span></span>

<span data-ttu-id="111a0-p101">Se l'organizzazione ha una sottoscrizione a pagamento a Office 365, Microsoft Dynamics CRM Online, Enterprise Mobility Suite o altri servizi Microsoft, si dispone di una sottoscrizione gratuita a Microsoft Azure Active Directory. Gli amministratori possono usare Azure AD per creare e gestire account utente e di gruppo. Per usare Azure AD, basta andare al portale di Azure e accedere utilizzando il tuo account Office 365.</span><span class="sxs-lookup"><span data-stu-id="111a0-p101">If your organization has a paid subscription to Office 365, Microsoft Dynamics CRM Online, Enterprise Mobility Suite, or other Microsoft services, you have a free subscription to Microsoft Azure Active Directory. You and other admins can use Azure AD to create and manage user and group accounts. To use Azure AD, just go to the Azure portal and sign in using your Office 365 account.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="111a0-107">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="111a0-107">Before you begin</span></span>

<span data-ttu-id="111a0-p102">Usare una sessione di esplorazione privata invece di una normale per accedere al portale di Azure (nel passaggio 1 seguente), per impedire che le credenziali con cui si è attualmente connessi vengano passate ad Azure. Per aprire una sessione di esplorazione privata:</span><span class="sxs-lookup"><span data-stu-id="111a0-p102">Use a private browsing session (not a regular session) to access the Azure portal (in step 1 below) because this will prevent the credential that you are currently logged on with from being passed to Azure. To open an private browsing session:</span></span>

- <span data-ttu-id="111a0-110">In Microsoft Edge (versione legacy), Internet Explorer o Mozilla FireFox premere `CTRL+SHIFT+P`.</span><span class="sxs-lookup"><span data-stu-id="111a0-110">In Microsoft Edge (legacy version), Internet Explorer, or Mozilla FireFox, press `CTRL+SHIFT+P`.</span></span>

- <span data-ttu-id="111a0-111">In Microsoft Edge (versione più recente) o Google Chrome premere `CTRL+SHIFT+N`.</span><span class="sxs-lookup"><span data-stu-id="111a0-111">In Microsoft Edge (newest version) or Google Chrome, press `CTRL+SHIFT+N`.</span></span>

## <a name="access-azure-active-directory"></a><span data-ttu-id="111a0-112">Accedere ad Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="111a0-112">Access Azure Active Directory</span></span>

1. <span data-ttu-id="111a0-113">Andare a [portal.azure.com](https://portal.azure.com) e accedere con il proprio account professionale o studente di Office 365.</span><span class="sxs-lookup"><span data-stu-id="111a0-113">Go to [portal.azure.com](https://portal.azure.com) and sign in with your Office 365 work or student account.</span></span>

2. <span data-ttu-id="111a0-114">Nel riquadro di spostamento a sinistra nel portale di Azure, fare clic su **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="111a0-114">In the left navigation pane in the Azure portal, click **Azure Active Directory**.</span></span>

    ![Fare clic su Azure Active Directory nel riquadro di spostamento a sinistra nel portale di Azure.](../media/97d2d72f-ac20-46ab-898c-851f6009b453.png)

    <span data-ttu-id="111a0-116">Viene visualizzata l'interfaccia di amministrazione di **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="111a0-116">The **Azure Active Directory** admin center is displayed.</span></span>

## <a name="more-information"></a><span data-ttu-id="111a0-117">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="111a0-117">More information</span></span>

- <span data-ttu-id="111a0-118">Un abbonamento gratuito ad Azure Active Directory non include il report delle attività di accesso.</span><span class="sxs-lookup"><span data-stu-id="111a0-118">A free Azure Active Directory subscription does not include the Sign-ins activity report.</span></span> <span data-ttu-id="111a0-119">Per registrare l'attività di accesso (che può essere utile in caso di violazione dei dati), è necessario un abbonamento ad Azure Active Directory Premium.</span><span class="sxs-lookup"><span data-stu-id="111a0-119">To record sign-in activity (which can be useful in the event of a data breach), you need an Azure Active Directory Premium subscription.</span></span> <span data-ttu-id="111a0-120">Per altre informazioni, vedere [Per quanto tempo Azure AD archivia i dati?](https://docs.microsoft.com/azure/active-directory/reports-monitoring/reference-reports-data-retention#how-long-does-azure-ad-store-the-data)</span><span class="sxs-lookup"><span data-stu-id="111a0-120">For more information, see [How long does Azure AD store the data?](https://docs.microsoft.com/azure/active-directory/reports-monitoring/reference-reports-data-retention#how-long-does-azure-ad-store-the-data).</span></span>

- <span data-ttu-id="111a0-121">È anche possibile accedere all'interfaccia di amministrazione di **Azure Active Directory** dall'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="111a0-121">You can also access the **Azure Active Directory** admin center from the Microsoft 365 admin center.</span></span> <span data-ttu-id="111a0-122">Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft 365 fare clic su **Interfacce di amministrazione** \> **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="111a0-122">In the left navigation pane of the Microsoft 365 admin center, click **Admin centers** \> **Azure Active Directory**.</span></span>

- <span data-ttu-id="111a0-123">Per informazioni sulla gestione degli utenti e dei gruppi e sull'esecuzione di altre attività di gestione delle directory, vedere [Gestione della directory di Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-administer).</span><span class="sxs-lookup"><span data-stu-id="111a0-123">For information about managing users and groups and performing other directory management tasks, see [Manage your Azure AD directory](https://docs.microsoft.com/azure/active-directory/active-directory-administer).</span></span>
