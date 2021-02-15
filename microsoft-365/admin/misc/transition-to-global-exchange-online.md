---
title: Aggiornare i record MX per la transizione al servizio Exchange Online globale
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.custom: AdminSurgePortfolio
ROBOTS: NOINDEX, NOFOLLOW
description: Informazioni su come eseguire la transizione da Microsoft Cloud Germania Exchange Online al servizio Exchange Online globale
ms.openlocfilehash: 8de64e30205b07a0c20a8ae4f7cdedbf6cc6824f
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/21/2020
ms.locfileid: "48644856"
---
# <a name="update-your-mx-records-to-transition-to-the-global-exchange-online-service"></a><span data-ttu-id="b7734-103">Aggiornare i record MX per la transizione al servizio Exchange Online globale</span><span class="sxs-lookup"><span data-stu-id="b7734-103">Update your MX records to transition to the global Exchange Online service</span></span>

1. <span data-ttu-id="b7734-104">Accedere al portale di amministrazione di [Microsoft 365](https://admin.microsoft.com)e passare a **Domini**  >  **impostazioni**</span><span class="sxs-lookup"><span data-stu-id="b7734-104">Sign in to [Microsoft 365 admin portal](https://admin.microsoft.com), and go to **Settings** > **Domains**</span></span>

2. <span data-ttu-id="b7734-105">Lo stato verrà visualizzato sul lato destro di ogni dominio.</span><span class="sxs-lookup"><span data-stu-id="b7734-105">Status will be shown on the right side for each domain.</span></span> <span data-ttu-id="b7734-106">Se i domini dell'organizzazione puntano a Microsoft Cloud Germania Exchange Online, è necessario aggiornare il record MX.</span><span class="sxs-lookup"><span data-stu-id="b7734-106">If your organization’s domains point to Microsoft Cloud Germany Exchange Online, you'll need to update your MX record.</span></span>

3. <span data-ttu-id="b7734-107">Fare clic sul dominio, quindi fare **clic su Errori DNS rilevati, fare clic qui per visualizzare**.</span><span class="sxs-lookup"><span data-stu-id="b7734-107">Click the domain, then click **DNS errors detected, click here to view**.</span></span>

4. <span data-ttu-id="b7734-108">Questa pagina avrà istruzioni per mostrare come correggere il record MX.</span><span class="sxs-lookup"><span data-stu-id="b7734-108">This page will have instructions to show you how to fix the MX record.</span></span> <span data-ttu-id="b7734-109">Se il registrar del dominio usa [Domain Connect,](../setup/add-domain.md#registrars-with-domain-connect)è possibile fare clic su "Correggi i miei record" nella parte superiore.</span><span class="sxs-lookup"><span data-stu-id="b7734-109">If your domain’s registrar uses [Domain Connect](../setup/add-domain.md#registrars-with-domain-connect), you can click “Fix my records” on top.</span></span> <span data-ttu-id="b7734-110">In caso contrario, è possibile seguire il collegamento della procedura guidata alle **istruzioni dettagliate** per il registrar.</span><span class="sxs-lookup"><span data-stu-id="b7734-110">Otherwise you can follow the link in the wizard to **step-by-step instructions** for your registrar.</span></span>