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
description: L'organizzazione potrebbe avere bisogno di più domini in modo che i clienti possano trovarti. Informazioni su come aggiungere un altro dominio all'abbonamento.
ms.openlocfilehash: 13fc3cf73a112945db4372231cce70c1837c1321
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706431"
---
# <a name="add-another-domain"></a><span data-ttu-id="65507-104">Aggiungere un altro dominio</span><span class="sxs-lookup"><span data-stu-id="65507-104">Add another domain</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4dN8c?autoplay=false]

<span data-ttu-id="65507-105">L'azienda potrebbe avere bisogno di più nomi di dominio per scopi diversi.</span><span class="sxs-lookup"><span data-stu-id="65507-105">Your company might need multiple domain names for different purposes.</span></span> <span data-ttu-id="65507-106">Ad esempio, potresti voler aggiungere un'ortografia diversa del nome della società perché i clienti lo stanno già usando e le loro comunicazioni non sono riuscite a raggiungere l'utente.</span><span class="sxs-lookup"><span data-stu-id="65507-106">For example, you might want to add a different spelling of your company name because customers are already using it and their communications have failed to reach you.</span></span>

## <a name="try-it"></a><span data-ttu-id="65507-107">Perché non provarlo?</span><span class="sxs-lookup"><span data-stu-id="65507-107">Try it!</span></span>

1. <span data-ttu-id="65507-108">Nell'Microsoft 365 di amministrazione scegliere **Installazione**.</span><span class="sxs-lookup"><span data-stu-id="65507-108">In the Microsoft 365 admin center, choose **Setup**.</span></span>
1. <span data-ttu-id="65507-109">In **Configurare il dominio personalizzato** selezionare **Visualizza.**</span><span class="sxs-lookup"><span data-stu-id="65507-109">Under **Get your custom domain set up**, select **View**.</span></span>
1. <span data-ttu-id="65507-110">Scegliere **Gestisci** e quindi **Aggiungi dominio**.</span><span class="sxs-lookup"><span data-stu-id="65507-110">Choose **Manage**, and then **Add domain**.</span></span>
1. <span data-ttu-id="65507-111">Immettere il nuovo nome di dominio che si desidera aggiungere e quindi selezionare **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="65507-111">Enter the new domain name that you want to add, and then select **Next**.</span></span>
1. <span data-ttu-id="65507-112">Accedi al registrar, in questo caso GoDaddy, quindi seleziona **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="65507-112">Sign in to your domain registrar, in this case GoDaddy, and then select **Next**.</span></span>
1. <span data-ttu-id="65507-113">Se richiesto, accedere al registrar e quindi scegliere **Autorizza**.</span><span class="sxs-lookup"><span data-stu-id="65507-113">If prompted, sign in to your registrar, and then choose **Authorize**.</span></span>
1. <span data-ttu-id="65507-114">Scegliere **Add the DNS records for me** e quindi selezionare **Next**.</span><span class="sxs-lookup"><span data-stu-id="65507-114">Choose **Add the DNS records for me**, and then select **Next**.</span></span>
1. <span data-ttu-id="65507-115">Scegliere i servizi per il nuovo dominio e deselezionare le caselle di controllo per tutti i servizi che verranno gestiti da un dominio diverso.</span><span class="sxs-lookup"><span data-stu-id="65507-115">Choose the services for your new domain and clear the check boxes for any services that will be handled by a different domain.</span></span> <span data-ttu-id="65507-116">Ad esempio, se si desidera solo utilizzare il nuovo dominio per la posta elettronica, scegliere **Exchange** e deselezionare le caselle di controllo per Skype for Business **e** **Gestione dispositivi mobili per Office 365**.</span><span class="sxs-lookup"><span data-stu-id="65507-116">For example, if you just want to use the new domain for email, choose **Exchange**, and clear the check boxes for **Skype for Business** and **Mobile Device Management for Office 365**.</span></span>
1. <span data-ttu-id="65507-117">Selezionare **Avanti**, **Autorizza**, **Avanti** e quindi **Fine**.</span><span class="sxs-lookup"><span data-stu-id="65507-117">Select **Next**, **Authorize**, **Next**,and then **Finish**.</span></span> <span data-ttu-id="65507-118">Il nuovo dominio è stato aggiunto.</span><span class="sxs-lookup"><span data-stu-id="65507-118">Your new domain has been added.</span></span>

<span data-ttu-id="65507-119">Per ricevere posta elettronica nel nuovo dominio, è necessario aggiungere un nuovo alias di posta elettronica per ogni utente:</span><span class="sxs-lookup"><span data-stu-id="65507-119">To receive email at your new domain, you'll need to add a new email alias for each user:</span></span>

1. <span data-ttu-id="65507-120">Selezionare **Utenti**, **Utenti attivi** e quindi selezionare l'utente a cui verrà assegnato il nuovo alias.</span><span class="sxs-lookup"><span data-stu-id="65507-120">Select **Users**, **Active users**, and then select the user who will be assigned the new alias.</span></span>
1. <span data-ttu-id="65507-121">Scegliere **Gestisci alias di posta** elettronica e quindi Aggiungi un **alias.**</span><span class="sxs-lookup"><span data-stu-id="65507-121">Choose **Manage email aliases**, and then **Add an alias**.</span></span>
1. <span data-ttu-id="65507-122">Immetti il nome utente e quindi scegli il nuovo dominio nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="65507-122">Enter the username, and then choose the new domain from the drop-down list.</span></span>
1. <span data-ttu-id="65507-123">Selezionare **Salva modifiche** e quindi chiudere la finestra.</span><span class="sxs-lookup"><span data-stu-id="65507-123">Select **Save changes**, and then close the window.</span></span>
1. <span data-ttu-id="65507-124">Ripetere questi passaggi per ogni utente che deve ricevere posta elettronica nel nuovo dominio.</span><span class="sxs-lookup"><span data-stu-id="65507-124">Repeat these steps for each user who should receive email at the new domain.</span></span>

## <a name="related-content"></a><span data-ttu-id="65507-125">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="65507-125">Related content</span></span>

<span data-ttu-id="65507-126">[Aggiungere un dominio a Microsoft 365](../admin/setup/add-domain.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="65507-126">[Add a domain to Microsoft 365](../admin/setup/add-domain.md) (article)</span></span>\
<span data-ttu-id="65507-127">[Aggiungere record DNS per connettere il dominio](../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="65507-127">[Add DNS records to connect your domain](../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md) (article)</span></span>\
<span data-ttu-id="65507-128">[Modificare i server dei nomi per configurare Microsoft 365 con qualsiasi registrar del dominio](../admin/get-help-with-domains/change-nameservers-at-any-domain-registrar.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="65507-128">[Change nameservers to set up Microsoft 365 with any domain registrar](../admin/get-help-with-domains/change-nameservers-at-any-domain-registrar.md) (article)</span></span>\
<span data-ttu-id="65507-129">[Domande frequenti sui domini](../admin/setup/domains-faq.yml) (articolo)</span><span class="sxs-lookup"><span data-stu-id="65507-129">[Domains FAQ](../admin/setup/domains-faq.yml) (article)</span></span>