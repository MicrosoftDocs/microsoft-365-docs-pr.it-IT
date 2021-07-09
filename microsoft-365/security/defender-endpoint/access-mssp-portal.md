---
title: Accedere al portale Microsoft 365 Defender clienti MSSP
description: Accedere al portale Microsoft 365 Defender clienti MSSP
keywords: provider di servizi di sicurezza gestiti, mssp, configurare, integrazione
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 8583b28adecd892ec6875faa934fd7ab08e5db11
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339587"
---
# <a name="access-the-microsoft-365-defender-mssp-customer-portal"></a><span data-ttu-id="0eb45-104">Accedere al portale Microsoft 365 Defender clienti MSSP</span><span class="sxs-lookup"><span data-stu-id="0eb45-104">Access the Microsoft 365 Defender MSSP customer portal</span></span>

<span data-ttu-id="0eb45-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="0eb45-105">**Applies to:**</span></span>
- [<span data-ttu-id="0eb45-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="0eb45-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="0eb45-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0eb45-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="0eb45-108">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="0eb45-108">**Applies to:**</span></span>

- [<span data-ttu-id="0eb45-109">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="0eb45-109">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

><span data-ttu-id="0eb45-110">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="0eb45-110">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="0eb45-111">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="0eb45-111">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)




>[!NOTE] 
><span data-ttu-id="0eb45-112">Questi set di passaggi sono indirizzati al provider di servizi condivisi.</span><span class="sxs-lookup"><span data-stu-id="0eb45-112">These set of steps are directed towards the MSSP.</span></span> 

<span data-ttu-id="0eb45-113">Per impostazione predefinita, i clienti MSSP accedono al proprio tenant Microsoft Defender Security Center tramite l'URL seguente: `https://securitycenter.windows.com` .</span><span class="sxs-lookup"><span data-stu-id="0eb45-113">By default, MSSP customers access their Microsoft Defender Security Center tenant through the following URL: `https://securitycenter.windows.com`.</span></span>
 

<span data-ttu-id="0eb45-114">Gli MSSP, tuttavia, dovranno utilizzare un URL specifico del tenant nel formato seguente:  `https://securitycenter.windows.com?tid=customer_tenant_id` per accedere al portale dei clienti MSSP.</span><span class="sxs-lookup"><span data-stu-id="0eb45-114">MSSPs however, will need to use a tenant-specific URL in the following format:  `https://securitycenter.windows.com?tid=customer_tenant_id` to access the MSSP customer portal.</span></span> 

<span data-ttu-id="0eb45-115">In generale, gli MSSP dovranno essere aggiunti a ogni Azure AD del cliente MSSP che intende gestire.</span><span class="sxs-lookup"><span data-stu-id="0eb45-115">In general, MSSPs will need to be added to each of the MSSP customer's Azure AD that they intend to manage.</span></span>


<span data-ttu-id="0eb45-116">Utilizzare la procedura seguente per ottenere l'ID tenant del cliente MSSP e quindi utilizzare l'ID per accedere all'URL specifico del tenant:</span><span class="sxs-lookup"><span data-stu-id="0eb45-116">Use the following steps to obtain the MSSP customer tenant ID and then use the ID to access the tenant-specific URL:</span></span>

1. <span data-ttu-id="0eb45-117">Come provider di servizi condivisi, accedi ad Azure AD con le tue credenziali.</span><span class="sxs-lookup"><span data-stu-id="0eb45-117">As an MSSP, login to Azure AD with your credentials.</span></span> 

2. <span data-ttu-id="0eb45-118">Passare dalla directory al tenant del cliente MSSP.</span><span class="sxs-lookup"><span data-stu-id="0eb45-118">Switch directory to the MSSP customer's tenant.</span></span>

3.  <span data-ttu-id="0eb45-119">Selezionare **Azure Active Directory > proprietà.**</span><span class="sxs-lookup"><span data-stu-id="0eb45-119">Select **Azure Active Directory > Properties**.</span></span> <span data-ttu-id="0eb45-120">L'ID tenant è presente nel campo ID directory.</span><span class="sxs-lookup"><span data-stu-id="0eb45-120">You'll find the tenant ID in the Directory ID field.</span></span> 

4. <span data-ttu-id="0eb45-121">Accedere al portale del cliente MSSP sostituendo il `customer_tenant_id` valore nell'URL seguente: `https://securitycenter.windows.com?tid=customer_tenant_id` .</span><span class="sxs-lookup"><span data-stu-id="0eb45-121">Access the MSSP customer portal by replacing the `customer_tenant_id` value in the following URL: `https://securitycenter.windows.com?tid=customer_tenant_id`.</span></span>


## <a name="related-topics"></a><span data-ttu-id="0eb45-122">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="0eb45-122">Related topics</span></span>
- [<span data-ttu-id="0eb45-123">Concedere a MSSP l'accesso al portale</span><span class="sxs-lookup"><span data-stu-id="0eb45-123">Grant MSSP access to the portal</span></span>](grant-mssp-access.md)
- [<span data-ttu-id="0eb45-124">Configurare le notifiche di avviso</span><span class="sxs-lookup"><span data-stu-id="0eb45-124">Configure alert notifications</span></span>](configure-mssp-notifications.md)
- [<span data-ttu-id="0eb45-125">Recuperare gli avvisi dal tenant del cliente</span><span class="sxs-lookup"><span data-stu-id="0eb45-125">Fetch alerts from customer tenant</span></span>](fetch-alerts-mssp.md)
