---
title: Modificare l'accesso condizionale
description: Come escludere determinati account Microsoft
keywords: Microsoft Managed Desktop, Microsoft 365, servizio, documentazione
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 8844c50f5faba609b3f5f53adc5ab45ba1dbaa74
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2020
ms.locfileid: "46529684"
---
# <a name="adjust-conditional-access"></a><span data-ttu-id="65251-104">Modificare l'accesso condizionale</span><span class="sxs-lookup"><span data-stu-id="65251-104">Adjust conditional access</span></span>

<span data-ttu-id="65251-105">Se si utilizzano i criteri di [accesso condizionale](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) nell'organizzazione, sarà necessario impostarli in modo da escludere determinati account affinché Microsoft Managed Desktop possa funzionare correttamente.</span><span class="sxs-lookup"><span data-stu-id="65251-105">If you use [conditional access](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) policies in your organization, you'll have to set them to exclude certain accounts so that Microsoft Managed Desktop can work properly.</span></span>

<span data-ttu-id="65251-106">A tal fine, attenersi alla seguente procedura:</span><span class="sxs-lookup"><span data-stu-id="65251-106">To do this, follow these steps:</span></span>

1. <span data-ttu-id="65251-107">Fare riferimento alla sezione relativa ai passaggi di rollback [in procedura: pianificare la distribuzione di accesso condizionale in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access#rollback-steps).</span><span class="sxs-lookup"><span data-stu-id="65251-107">Refer to the "Rollback steps" section of [How To: Plan your Conditional Access deployment in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access#rollback-steps).</span></span>
2. <span data-ttu-id="65251-108">Attenersi alla procedura seguente per escludere il gruppo di *account del servizio di lavoro moderno* per tutti i criteri.</span><span class="sxs-lookup"><span data-stu-id="65251-108">Follow the steps there to exclude the *Modern Workplace Service Accounts* group for all policies.</span></span>


<span data-ttu-id="65251-109">In caso di problemi con l'accesso condizionale, contattare il [supporto](../working-with-managed-desktop/admin-support.md)dell'amministratore.</span><span class="sxs-lookup"><span data-stu-id="65251-109">If you have any difficulty with conditional access, contact admin [support](../working-with-managed-desktop/admin-support.md).</span></span>

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="65251-110">Passaggi per iniziare a utilizzare Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="65251-110">Steps to get started with Microsoft Managed Desktop</span></span>

1. [<span data-ttu-id="65251-111">Aggiungere e verificare i contatti degli amministratori nel portale di amministrazione</span><span class="sxs-lookup"><span data-stu-id="65251-111">Add and verify admin contacts in the Admin portal</span></span>](add-admin-contacts.md)
2. <span data-ttu-id="65251-112">Modificare l'accesso condizionale (questo argomento)</span><span class="sxs-lookup"><span data-stu-id="65251-112">Adjust conditional access (this topic)</span></span>
3. [<span data-ttu-id="65251-113">Assegnare licenze</span><span class="sxs-lookup"><span data-stu-id="65251-113">Assign licenses</span></span>](assign-licenses.md)
4. [<span data-ttu-id="65251-114">Distribuire il Portale aziendale Intune</span><span class="sxs-lookup"><span data-stu-id="65251-114">Deploy Intune Company Portal</span></span>](company-portal.md)
5. [<span data-ttu-id="65251-115">Abilitare Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="65251-115">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="65251-116">Configurare i dispositivi</span><span class="sxs-lookup"><span data-stu-id="65251-116">Set up devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="65251-117">Preparare gli utenti a usare i dispositivi</span><span class="sxs-lookup"><span data-stu-id="65251-117">Get your users ready to use devices</span></span>](get-started-devices.md)
8. [<span data-ttu-id="65251-118">Distribuire le app</span><span class="sxs-lookup"><span data-stu-id="65251-118">Deploy apps</span></span>](deploy-apps.md)
