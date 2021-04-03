---
title: Aggiungere un dominio
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Informazioni su come aggiungere un altro dominio all'abbonamento.
ms.openlocfilehash: 8899cb9667ffa080746ca9173b61897f9c5db399
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579002"
---
# <a name="add-another-domain"></a><span data-ttu-id="95597-103">Aggiungere un altro dominio</span><span class="sxs-lookup"><span data-stu-id="95597-103">Add another domain</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4dN8c?autoplay=false]

<span data-ttu-id="95597-104">L'azienda potrebbe avere bisogno di più nomi di dominio per scopi diversi.</span><span class="sxs-lookup"><span data-stu-id="95597-104">Your company might need multiple domain names for different purposes.</span></span> <span data-ttu-id="95597-105">Ad esempio, potresti voler aggiungere un'ortografia diversa del nome della società perché i clienti lo stanno già usando e le loro comunicazioni non sono riuscite a raggiungere l'utente.</span><span class="sxs-lookup"><span data-stu-id="95597-105">For example, you might want to add a different spelling of your company name because customers are already using it and their communications have failed to reach you.</span></span>

## <a name="try-it"></a><span data-ttu-id="95597-106">Perché non provarlo?</span><span class="sxs-lookup"><span data-stu-id="95597-106">Try it!</span></span>

1. <span data-ttu-id="95597-107">Nell'interfaccia di amministrazione di Microsoft 365 scegliere **Installazione**.</span><span class="sxs-lookup"><span data-stu-id="95597-107">In the Microsoft 365 admin center, choose **Setup**.</span></span>
1. <span data-ttu-id="95597-108">In **Configurare il dominio personalizzato** selezionare **Visualizza.**</span><span class="sxs-lookup"><span data-stu-id="95597-108">Under **Get your custom domain set up**, select **View**.</span></span>
1. <span data-ttu-id="95597-109">Scegliere **Gestisci** e quindi **Aggiungi dominio**.</span><span class="sxs-lookup"><span data-stu-id="95597-109">Choose **Manage**, and then **Add domain**.</span></span>
1. <span data-ttu-id="95597-110">Immettere il nuovo nome di dominio che si desidera aggiungere e quindi selezionare **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="95597-110">Enter the new domain name that you want to add, and then select **Next**.</span></span>
1. <span data-ttu-id="95597-111">Accedi al registrar, in questo caso GoDaddy, quindi seleziona **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="95597-111">Sign in to your domain registrar, in this case GoDaddy, and then select **Next**.</span></span>
1. <span data-ttu-id="95597-112">Se richiesto, accedere al registrar e quindi scegliere **Autorizza**.</span><span class="sxs-lookup"><span data-stu-id="95597-112">If prompted, sign in to your registrar, and then choose **Authorize**.</span></span>
1. <span data-ttu-id="95597-113">Scegliere **Add the DNS records for me** e quindi selezionare **Next**.</span><span class="sxs-lookup"><span data-stu-id="95597-113">Choose **Add the DNS records for me**, and then select **Next**.</span></span>
1. <span data-ttu-id="95597-114">Scegliere i servizi per il nuovo dominio e deselezionare le caselle di controllo per tutti i servizi che verranno gestiti da un dominio diverso.</span><span class="sxs-lookup"><span data-stu-id="95597-114">Choose the services for your new domain and clear the check boxes for any services that will be handled by a different domain.</span></span> <span data-ttu-id="95597-115">Ad esempio, se si desidera solo usare il nuovo dominio per la posta elettronica, scegliere **Exchange** e deselezionare le caselle di controllo per **Skype for Business** e Gestione dispositivi mobili per Office **365.**</span><span class="sxs-lookup"><span data-stu-id="95597-115">For example, if you just want to use the new domain for email, choose **Exchange**, and clear the check boxes for **Skype for Business** and **Mobile Device Management for Office 365**.</span></span>
1. <span data-ttu-id="95597-116">Selezionare **Avanti**, **Autorizza**, **Avanti** e quindi **Fine**.</span><span class="sxs-lookup"><span data-stu-id="95597-116">Select **Next**, **Authorize**, **Next**,and then **Finish**.</span></span> <span data-ttu-id="95597-117">Il nuovo dominio è stato aggiunto.</span><span class="sxs-lookup"><span data-stu-id="95597-117">Your new domain has been added.</span></span>

<span data-ttu-id="95597-118">Per ricevere posta elettronica nel nuovo dominio, è necessario aggiungere un nuovo alias di posta elettronica per ogni utente:</span><span class="sxs-lookup"><span data-stu-id="95597-118">To receive email at your new domain, you'll need to add a new email alias for each user:</span></span>

1. <span data-ttu-id="95597-119">Selezionare **Utenti**, **Utenti attivi** e quindi selezionare l'utente a cui verrà assegnato il nuovo alias.</span><span class="sxs-lookup"><span data-stu-id="95597-119">Select **Users**, **Active users**, and then select the user who will be assigned the new alias.</span></span>
1. <span data-ttu-id="95597-120">Scegliere **Gestisci alias di posta** elettronica e quindi Aggiungi un **alias.**</span><span class="sxs-lookup"><span data-stu-id="95597-120">Choose **Manage email aliases**, and then **Add an alias**.</span></span>
1. <span data-ttu-id="95597-121">Immetti il nome utente e quindi scegli il nuovo dominio nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="95597-121">Enter the username, and then choose the new domain from the drop-down list.</span></span>
1. <span data-ttu-id="95597-122">Selezionare **Salva modifiche** e quindi chiudere la finestra.</span><span class="sxs-lookup"><span data-stu-id="95597-122">Select **Save changes**, and then close the window.</span></span>
1. <span data-ttu-id="95597-123">Ripetere questi passaggi per ogni utente che deve ricevere posta elettronica nel nuovo dominio.</span><span class="sxs-lookup"><span data-stu-id="95597-123">Repeat these steps for each user who should receive email at the new domain.</span></span>