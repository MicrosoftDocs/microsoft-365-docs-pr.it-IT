---
title: Trasferire un dominio da Microsoft a un altro host
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
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
description: 'Seguire questa procedura per trasferire un dominio da Microsoft a un altro registrar. '
ms.openlocfilehash: f34e9733ab53c8bdc6f4432c96e6232ecc26ee06
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126348"
---
# <a name="transfer-a-domain-from-microsoft-to-another-host"></a><span data-ttu-id="b151f-103">Trasferire un dominio da Microsoft a un altro host</span><span class="sxs-lookup"><span data-stu-id="b151f-103">Transfer a domain from Microsoft to another host</span></span>

<span data-ttu-id="b151f-104">Non è possibile trasferire un dominio di Microsoft 365 a un altro registrar per 60 giorni dopo l'acquisto del dominio da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b151f-104">You can't transfer a Microsoft 365 domain to another registrar for 60 days after you purchase the domain from Microsoft.</span></span>

> [!NOTE]
> <span data-ttu-id="b151f-105">Una query _Whois_   mostra un registrar acquistato da Microsoft come Wild West Domains LLC.</span><span class="sxs-lookup"><span data-stu-id="b151f-105">A _Whois_ query shows a Microsoft purchased domain registrar as Wild West Domains LLC.</span></span> <span data-ttu-id="b151f-106">Tuttavia, solo Microsoft deve essere contattato per quanto riguarda il dominio acquistato di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b151f-106">However, only Microsoft should be contacted regarding your Microsoft 365 purchased domain.</span></span>

<span data-ttu-id="b151f-107">Seguire questa procedura per ottenere un codice in Microsoft 365 e quindi passare all'altro sito Web del registrar per configurare il trasferimento del nome di dominio nel nuovo registrar.</span><span class="sxs-lookup"><span data-stu-id="b151f-107">Follow these steps to get a code at Microsoft 365, and then go to the other domain registrar website to set up transferring your domain name to the new registrar.</span></span>

## <a name="transfer-a-domain"></a><span data-ttu-id="b151f-108">Trasferire un dominio</span><span class="sxs-lookup"><span data-stu-id="b151f-108">Transfer a domain</span></span>

1. <span data-ttu-id="b151f-109">Nell'interfaccia di amministrazione passare a   **Impostazioni**   >  **domini.**</span><span class="sxs-lookup"><span data-stu-id="b151f-109">In the admin center, go to   **Settings** > **Domains**.</span></span>

2. <span data-ttu-id="b151f-110">Nella pagina **Domini** selezionare il dominio di Microsoft 365 che si desidera trasferire a un altro registrar e quindi selezionare **Controlla integrità.**</span><span class="sxs-lookup"><span data-stu-id="b151f-110">On the **Domains** page, select the Microsoft 365 domain that you want to transfer to another domain registrar, and then select **Check health**.</span></span>

3. <span data-ttu-id="b151f-111">Nella parte superiore della pagina selezionare **Trasferisci dominio.**</span><span class="sxs-lookup"><span data-stu-id="b151f-111">At the top of the page, select **Transfer domain**.</span></span>

4. <span data-ttu-id="b151f-112">Nella pagina **Scegliere dove trasferire il dominio** selezionare Un altro **registrar** e quindi fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="b151f-112">On the **Choose where to transfer your domain** page, select **A different registrar**, and then click **Next**.</span></span>

5. <span data-ttu-id="b151f-113">Nella pagina **Sblocca trasferimento dominio** selezionare **Sblocca  >** trasferimento per <dominio e quindi selezionare **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="b151f-113">On the **Unlock domain transfer** page, select **Unlock transfer for <_your domain_>**, and then select **Next**.</span></span>

6. <span data-ttu-id="b151f-114">Controllare le informazioni di contatto per il trasferimento del dominio e quindi selezionare **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="b151f-114">Check your domain transfer contact information, and then select **Next**.</span></span>

7. <span data-ttu-id="b151f-115">Copiare il codice di autorizzazione e attendere circa 30 minuti perché  lo stato del trasferimento del dominio cambi in **Sbloccato** per il trasferimento nella scheda Registrazione prima di procedere con i passaggi successivi.</span><span class="sxs-lookup"><span data-stu-id="b151f-115">Copy the authorization code and wait about 30 minutes for your domain transfer status to change to **Unlocked for transfer** on the **Registration** tab before you proceed with next steps.</span></span>

8. <span data-ttu-id="b151f-116">Passare al sito Web del registrar che si desidera gestire il nome di dominio in futuro.</span><span class="sxs-lookup"><span data-stu-id="b151f-116">Go to the website of the domain registrar you want to manage your domain name going forward.</span></span> <span data-ttu-id="b151f-117">Seguire le istruzioni per il trasferimento di un dominio (cercare la Guida nel sito Web).</span><span class="sxs-lookup"><span data-stu-id="b151f-117">Follow directions for transferring a domain (search for help on their website).</span></span> <span data-ttu-id="b151f-118">Questo in genere significa pagare le tariffe di trasferimento e fornire l'Authcode al nuovo registrar in modo che possa avviare il trasferimento.</span><span class="sxs-lookup"><span data-stu-id="b151f-118">This usually means paying transfer fees and giving the Authcode to the new registrar so they can initiate the transfer.</span></span> <span data-ttu-id="b151f-119">Microsoft ti invia un'e-mail per confermare che abbiamo ricevuto la richiesta di trasferimento e che il dominio verrà trasferito entro 5 giorni.</span><span class="sxs-lookup"><span data-stu-id="b151f-119">Microsoft will email you to confirm we’ve received the transfer request, and the domain will transfer within 5 days.</span></span>

    <span data-ttu-id="b151f-120">È possibile trovare la scheda registrazione **del** codice di autorizzazione nella  **pagina Domini** in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b151f-120">You can find the authorization code **Registration** tab on the  **Domains** page in Microsoft 365.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="b151f-121">I domini .uk richiedono una procedura diversa.</span><span class="sxs-lookup"><span data-stu-id="b151f-121">.uk domains require a different procedure.</span></span> <span data-ttu-id="b151f-122">Contattare il supporto tecnico Microsoft e richiedere una **modifica del tag IPS** in modo che corrisponda al registrar che si desidera gestire in futuro.</span><span class="sxs-lookup"><span data-stu-id="b151f-122">Contact Microsoft Support and request an **IPS Tag change** to match the registrar you want to manage your domain going forward.</span></span> <span data-ttu-id="b151f-123">Una volta modificato il tag, il dominio viene immediatamente trasferimento al nuovo registrar.</span><span class="sxs-lookup"><span data-stu-id="b151f-123">Once the tag changes, the domain immediately transfers to the new registrar.</span></span> <span data-ttu-id="b151f-124">Dovrai quindi collaborare con il nuovo registrar per completare il trasferimento, probabilmente pagando le tariffe di trasferimento e aggiungendo il dominio trasferito al tuo account con il nuovo registrar.</span><span class="sxs-lookup"><span data-stu-id="b151f-124">You will then need to work with the new registrar to complete the transfer, likely paying transfer fees and adding the transferred domain to your account with your new registrar.</span></span>

9. <span data-ttu-id="b151f-125">Al termine del trasferimento, il dominio verrà rinnovato presso il nuovo registrar.</span><span class="sxs-lookup"><span data-stu-id="b151f-125">After the transfer is complete, you'll renew your domain at the new domain registrar.</span></span>

10. <span data-ttu-id="b151f-126">Per completare il processo, tornare alla pagina **Domini** nell'interfaccia di amministrazione, quindi selezionare   **Completa trasferimento dominio.**</span><span class="sxs-lookup"><span data-stu-id="b151f-126">To finish the process, go back to the **Domains** page in the admin center, and then select  **Complete domain transfer**.</span></span> <span data-ttu-id="b151f-127">Questo contrassegnerà il dominio come non più acquistato da Microsoft 365 e disabiliterà l'abbonamento al dominio.</span><span class="sxs-lookup"><span data-stu-id="b151f-127">This will mark the domain as no longer purchased from Microsoft 365, and will disable the domain subscription.</span></span> <span data-ttu-id="b151f-128">Non rimuoverà il dominio dal tenant e non influirà sugli utenti e le cassette postali esistenti nel dominio.</span><span class="sxs-lookup"><span data-stu-id="b151f-128">It will not remove the domain from the tenant, and will not affect existing users and mailboxes on the domain.</span></span>

> [!NOTE]
> <span data-ttu-id="b151f-129">I domini acquistati da Microsoft 365 non sono idonei per le modifiche ai server dei nomi o per il trasferimento del dominio tra organizzazioni di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b151f-129">Microsoft 365 purchased domains are not eligible for nameserver changes or transferring the domain between Microsoft 365 organizations.</span></span> <span data-ttu-id="b151f-130">Se uno di questi è obbligatorio, la registrazione del dominio deve essere trasferita a un altro registrar.</span><span class="sxs-lookup"><span data-stu-id="b151f-130">If either of these are required, the domain registration must be transferred to another registrar.</span></span>
