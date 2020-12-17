---
title: Aggiungere un dominio
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
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
ms.openlocfilehash: 16f6c4e416ede560d69014e320eb32c4453fd3f5
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/17/2020
ms.locfileid: "49702166"
---
# <a name="add-another-domain"></a><span data-ttu-id="6b53b-103">Aggiungere un altro dominio</span><span class="sxs-lookup"><span data-stu-id="6b53b-103">Add another domain</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4dN8c?autoplay=false]

<span data-ttu-id="6b53b-104">La propria azienda potrebbe richiedere più nomi di dominio per scopi diversi.</span><span class="sxs-lookup"><span data-stu-id="6b53b-104">Your company might need multiple domain names for different purposes.</span></span> <span data-ttu-id="6b53b-105">Ad esempio, è possibile aggiungere un altro controllo ortografico del nome della società perché i clienti lo utilizzano già e le comunicazioni non sono state in grado di raggiungere l'utente.</span><span class="sxs-lookup"><span data-stu-id="6b53b-105">For example, you might want to add a different spelling of your company name because customers are already using it and their communications have failed to reach you.</span></span>

## <a name="try-it"></a><span data-ttu-id="6b53b-106">Perché non provarlo?</span><span class="sxs-lookup"><span data-stu-id="6b53b-106">Try it!</span></span>

1. <span data-ttu-id="6b53b-107">Nell'interfaccia di amministrazione di Microsoft 365 scegliere **Setup**.</span><span class="sxs-lookup"><span data-stu-id="6b53b-107">In the Microsoft 365 admin center, choose **Setup**.</span></span>
1. <span data-ttu-id="6b53b-108">In **Get your custom domain set up**, selezionare **View**.</span><span class="sxs-lookup"><span data-stu-id="6b53b-108">Under **Get your custom domain set up**, select **View**.</span></span>
1. <span data-ttu-id="6b53b-109">Scegliere **Gestisci** e quindi **Aggiungi dominio**.</span><span class="sxs-lookup"><span data-stu-id="6b53b-109">Choose **Manage**, and then **Add domain**.</span></span>
1. <span data-ttu-id="6b53b-110">Immettere il nuovo nome di dominio che si desidera aggiungere e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="6b53b-110">Enter the new domain name that you want to add, and then select **Next**.</span></span>
1. <span data-ttu-id="6b53b-111">Accedere al registrar, in questo caso GoDaddy, quindi selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="6b53b-111">Sign in to your domain registrar, in this case GoDaddy, and then select **Next**.</span></span>
1. <span data-ttu-id="6b53b-112">Se richiesto, accedere al servizio di registrazione e quindi scegliere **autorizza**.</span><span class="sxs-lookup"><span data-stu-id="6b53b-112">If prompted, sign in to your registrar, and then choose **Authorize**.</span></span>
1. <span data-ttu-id="6b53b-113">Scegliere **Add the DNS Records for me**, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="6b53b-113">Choose **Add the DNS records for me**, and then select **Next**.</span></span>
1. <span data-ttu-id="6b53b-114">Scegliere i servizi per il nuovo dominio e deselezionare le caselle di controllo per tutti i servizi che verranno gestiti da un dominio diverso.</span><span class="sxs-lookup"><span data-stu-id="6b53b-114">Choose the services for your new domain and clear the check boxes for any services that will be handled by a different domain.</span></span> <span data-ttu-id="6b53b-115">Ad esempio, se si desidera utilizzare il nuovo dominio per la posta elettronica, scegliere **Exchange** e deselezionare le caselle di controllo per **Skype for business** e **per la gestione dei dispositivi mobili per Office 365**.</span><span class="sxs-lookup"><span data-stu-id="6b53b-115">For example, if you just want to use the new domain for email, choose **Exchange**, and clear the check boxes for **Skype for Business** and **Mobile Device Management for Office 365**.</span></span>
1. <span data-ttu-id="6b53b-116">Fare clic su **Avanti**, su **autorizzare**, su **Avanti** e quindi su **fine**.</span><span class="sxs-lookup"><span data-stu-id="6b53b-116">Select **Next**, **Authorize**, **Next**,and then **Finish**.</span></span> <span data-ttu-id="6b53b-117">È stato aggiunto il nuovo dominio.</span><span class="sxs-lookup"><span data-stu-id="6b53b-117">Your new domain has been added.</span></span>

<span data-ttu-id="6b53b-118">Per ricevere la posta elettronica nel nuovo dominio, è necessario aggiungere un nuovo alias di posta elettronica per ogni utente:</span><span class="sxs-lookup"><span data-stu-id="6b53b-118">To receive email at your new domain, you'll need to add a new email alias for each user:</span></span>

1. <span data-ttu-id="6b53b-119">Selezionare **gli utenti**, **gli utenti attivi** e quindi selezionare l'utente a cui verrà assegnato il nuovo alias.</span><span class="sxs-lookup"><span data-stu-id="6b53b-119">Select **Users**, **Active users**, and then select the user who will be assigned the new alias.</span></span>
1. <span data-ttu-id="6b53b-120">Scegliere **Gestisci alias di posta elettronica** e quindi **aggiungere un alias**.</span><span class="sxs-lookup"><span data-stu-id="6b53b-120">Choose **Manage email aliases**, and then **Add an alias**.</span></span>
1. <span data-ttu-id="6b53b-121">Immettere il nome utente e quindi scegliere il nuovo dominio dall'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="6b53b-121">Enter the username, and then choose the new domain from the drop-down list.</span></span>
1. <span data-ttu-id="6b53b-122">Selezionare **Salva modifiche**, quindi chiudere la finestra.</span><span class="sxs-lookup"><span data-stu-id="6b53b-122">Select **Save changes**, and then close the window.</span></span>
1. <span data-ttu-id="6b53b-123">Ripetere questi passaggi per ogni utente che deve ricevere la posta elettronica nel nuovo dominio.</span><span class="sxs-lookup"><span data-stu-id="6b53b-123">Repeat these steps for each user who should receive email at the new domain.</span></span>