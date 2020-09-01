---
title: Aggiungere app all'icona di avvio delle app degli utenti
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.collection:
- Adm_O365
- M365-subscription-management
ms.service: o365-administration
localization_priority: Normal
description: In qualità di amministratore globale è possibile aggiungere fino a tre app all'icona di avvio delle app degli utenti.
ms.openlocfilehash: d9b95a20f332a9b1f2f6b0ebba28a70c58677b58
ms.sourcegitcommit: 87449335d9a1124ee82fa2e95e4745155a95a62f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/29/2020
ms.locfileid: "47310876"
---
# <a name="pin-apps-to-your-users-app-launcher"></a><span data-ttu-id="78020-103">Aggiungere app all'icona di avvio delle app degli utenti</span><span class="sxs-lookup"><span data-stu-id="78020-103">Pin apps to your users' app launcher</span></span>

<span data-ttu-id="78020-104">È possibile utilizzare i controlli nel portale di Azure Active Directory per aggiungere fino a tre app a Office.com e l'icona di avvio delle app per tutti gli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="78020-104">You can use controls in the Azure Active Directory portal to pin up to three apps to Office.com and the app launcher for all the users in your organization.</span></span> <span data-ttu-id="78020-105">È anche possibile organizzare gruppi di applicazioni.</span><span class="sxs-lookup"><span data-stu-id="78020-105">You can also organize groups of applications.</span></span> <span data-ttu-id="78020-106">Qualsiasi applicazione aggiunta può successivamente essere sbloccata dall'utente in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="78020-106">Any app you add can later be unpinned by the user at any time.</span></span> <span data-ttu-id="78020-107">Per aggiungere un'app per gli utenti, è necessario essere un amministratore dell'applicazione cloud o un amministratore dell'applicazione in Azure Active Directory o un amministratore globale in Office 365.</span><span class="sxs-lookup"><span data-stu-id="78020-107">To pin an app for your users, you must be a Cloud application administrator, or Application administrator in Azure Active Directory, or a Global administrator in Office 365.</span></span> <span data-ttu-id="78020-108">Per ulteriori informazioni sui ruoli di amministratore, vedere ruoli [di amministratore in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) e [ruoli di amministratore in Microsoft 365](../add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="78020-108">For more information about admin roles, see [admin roles in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) and [admin roles in Microsoft 365](../add-users/about-admin-roles.md).</span></span> 

<span data-ttu-id="78020-109">Per ulteriori informazioni sull'icona di avvio delle app e Office.com, vedere [Meet the App Launcher](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a) and [updates to Office.com and the-Office 365 App Launcher](https://techcommunity.microsoft.com/t5/office-365-blog/updates-to-office-com-and-the-office-365-app-launcher/ba-p/1150503) Blog article.</span><span class="sxs-lookup"><span data-stu-id="78020-109">For more information about the app launcher and Office.com, see [meet the app launcher](https://support.microsoft.com/office/79f12104-6fed-442f-96a0-eb089a3f476a) and [updates to office.com and the-Office 365 app launcher](https://techcommunity.microsoft.com/t5/office-365-blog/updates-to-office-com-and-the-office-365-app-launcher/ba-p/1150503) blog article.</span></span>

## <a name="use-the-azure-active-directory-portal-to-pin-apps"></a><span data-ttu-id="78020-110">Utilizzare il portale di Azure Active Directory per aggiungere le app</span><span class="sxs-lookup"><span data-stu-id="78020-110">Use the Azure Active Directory portal to pin apps</span></span>

1. <span data-ttu-id="78020-111">Accedere all'interfaccia di amministrazione di Microsoft 365 all'indirizzo <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .</span><span class="sxs-lookup"><span data-stu-id="78020-111">Go to the Microsoft 365 admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>
2. <span data-ttu-id="78020-112">Nella barra di spostamento sinistra fare clic su **Mostra tutto**e in interfaccia di **Amministrazione**, scegliere **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="78020-112">In the left nav, choose **Show all**, and under **Admin centers**, choose **Azure Active Directory**.</span></span>
3. <span data-ttu-id="78020-113">In **Azure Active Directory**, scegliere **Enterprise applications**  >  **impostazioni utente**applicazioni Enterprise.</span><span class="sxs-lookup"><span data-stu-id="78020-113">In **Azure Active Directory**, choose **Enterprise applications** > **User settings**.</span></span>
4. <span data-ttu-id="78020-114">Nella sezione **impostazioni di Office 365** scegliere **Aggiungi applicazione**.</span><span class="sxs-lookup"><span data-stu-id="78020-114">In the **Office 365 Settings** section, choose **Add application**.</span></span>
5. <span data-ttu-id="78020-115">Scegliere le applicazioni che si desidera aggiungere all'icona di avvio delle app degli utenti e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="78020-115">Choose the applications you want to pin to the users' app launcher, and then choose **Add**.</span></span>

:::image type="content" source="../../media/add-apps.png" alt-text="Microsoft 365 Settings to pin Apps.":::

### <a name="pin-a-custom-app"></a><span data-ttu-id="78020-117">Aggiungere un'app personalizzata</span><span class="sxs-lookup"><span data-stu-id="78020-117">Pin a custom app</span></span>

> [!NOTE]
> <span data-ttu-id="78020-118">L'interfaccia utente indicherà se è necessario acquistare altre licenze di Azure ad per l'utilizzo di questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="78020-118">The user interface will indicate if you need need to purchase additional Azure AD licenses to use this feature.</span></span> <span data-ttu-id="78020-119">Per ulteriori informazioni, vedere [Azure Active Directory pricing](https://azure.microsoft.com/pricing/details/active-directory/).</span><span class="sxs-lookup"><span data-stu-id="78020-119">For more information see [Azure Active Directory pricing](https://azure.microsoft.com/pricing/details/active-directory/).</span></span>

1. <span data-ttu-id="78020-120">In **Azure Active Directory**, scegliere **applicazioni Enterprise**  >  **nuova applicazione** nella parte superiore della pagina **tutte le applicazioni** .</span><span class="sxs-lookup"><span data-stu-id="78020-120">In **Azure Active Directory**, choose **Enterprise applications** > **New application** on the top of the **All applications** page.</span></span>
2. <span data-ttu-id="78020-121">Nella pagina **Aggiungi applicazione** scegliere **applicazione non raccolta** o **creare un'applicazione personalizzata** se si è nella versione di anteprima di Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="78020-121">On the **Add an application** page, choose **Non-gallery application** or **Create your own application** if you are in the preview version of Azure Active Directory.</span></span> 
3. <span data-ttu-id="78020-122">Digitare un nome per l'applicazione e quindi assegnare l'utente nella scheda **utenti e gruppi** .</span><span class="sxs-lookup"><span data-stu-id="78020-122">Type a name for the application and then assign user in the **Users and groups** tab.</span></span>
4. <span data-ttu-id="78020-123">Utilizzare la scheda **Proprietà** per caricare un'icona per l'app.</span><span class="sxs-lookup"><span data-stu-id="78020-123">Use the **Properties** tab to upload an icon for the app.</span></span>
5. <span data-ttu-id="78020-124">Per assegnare un URL all'app, nella scheda **Single Sign-on** scegliere **collegato** e quindi immettere un URL.</span><span class="sxs-lookup"><span data-stu-id="78020-124">To assign a URL to the app, in the **Single sign-on** tab, choose **Linked** and then enter a URL.</span></span>
6. <span data-ttu-id="78020-125">Scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="78020-125">Choose **Save**.</span></span>

## <a name="create-application-collections"></a><span data-ttu-id="78020-126">Creare raccolte applicazioni</span><span class="sxs-lookup"><span data-stu-id="78020-126">Create application collections</span></span>

<span data-ttu-id="78020-127">È inoltre possibile creare raccolte applicazioni per gli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="78020-127">You can also create application collections for the users in your organization.</span></span> <span data-ttu-id="78020-128">Per istruzioni, vedere [create Collections on the My Apps Portal nel portale di Azure](https://docs.microsoft.com/azure/active-directory/manage-apps/access-panel-collections).</span><span class="sxs-lookup"><span data-stu-id="78020-128">For instructions, see [create collections on the My Apps portal in the Azure portal](https://docs.microsoft.com/azure/active-directory/manage-apps/access-panel-collections).</span></span>