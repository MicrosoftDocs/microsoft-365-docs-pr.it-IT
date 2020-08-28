---
title: Trasferire un dominio da Microsoft a un altro host
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
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
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
description: 'Individuare i passaggi riportati di seguito per trasferire un dominio da Microsoft a un altro registrar. '
ms.openlocfilehash: c5c1e98ed14c3ac975e55aadbff65e52165a6f8b
ms.sourcegitcommit: abf63669daf12993ad3353e4b578f41c8910b20f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2020
ms.locfileid: "47289172"
---
# <a name="transfer-a-domain-from-microsoft-to-another-host"></a><span data-ttu-id="86329-103">Trasferire un dominio da Microsoft a un altro host</span><span class="sxs-lookup"><span data-stu-id="86329-103">Transfer a domain from Microsoft to another host</span></span>

<span data-ttu-id="86329-104">Non è possibile trasferire un dominio Microsoft 365 a un altro registrar per 60 giorni dopo l'acquisto del dominio da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="86329-104">You can't transfer a Microsoft 365 domain to another registrar for 60 days after you purchase the domain from Microsoft.</span></span>

> [!NOTE]
> <span data-ttu-id="86329-105">Una query _Whois_   Visualizza un registrar Microsoft acquistato come Wild West Domains LLC.</span><span class="sxs-lookup"><span data-stu-id="86329-105">A _Whois_ query shows a Microsoft purchased domain registrar as Wild West Domains LLC.</span></span> <span data-ttu-id="86329-106">Tuttavia, solo Microsoft dovrebbe essere contattato per quanto riguarda il dominio acquistato Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="86329-106">However, only Microsoft should be contacted regarding your Microsoft 365 purchased domain.</span></span>

<span data-ttu-id="86329-107">Seguire questa procedura per ottenere un codice in Microsoft 365, quindi passare all'altro sito Web registrar per impostare il trasferimento del nome di dominio nel nuovo registrar.</span><span class="sxs-lookup"><span data-stu-id="86329-107">Follow these steps to get a code at Microsoft 365, and then go to the other domain registrar website to set up transferring your domain name to the new registrar.</span></span>

## <a name="transfer-a-domain"></a><span data-ttu-id="86329-108">Trasferire un dominio</span><span class="sxs-lookup"><span data-stu-id="86329-108">Transfer a domain</span></span>

1. <span data-ttu-id="86329-109">Nell'interfaccia di amministrazione, andare a  **Settings**   >  **Domains**Settings.</span><span class="sxs-lookup"><span data-stu-id="86329-109">In the admin center, go to  **Settings** > **Domains**.</span></span>

2. <span data-ttu-id="86329-110">Nella pagina **Domains** selezionare il dominio Microsoft 365 che si desidera trasferire a un altro registrar, quindi selezionare **Verifica integrità**.</span><span class="sxs-lookup"><span data-stu-id="86329-110">On the **Domains** page, select the Microsoft 365 domain that you want to transfer to another domain registrar, and then select **Check health**.</span></span>

3. <span data-ttu-id="86329-111">Nella parte superiore della pagina, selezionare **trasferimento dominio**.</span><span class="sxs-lookup"><span data-stu-id="86329-111">At the top of the page, select **Transfer domain**.</span></span>

4. <span data-ttu-id="86329-112">Nella pagina **scegliere il percorso di trasferimento del dominio** selezionare **un registrar diverso**e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="86329-112">On the **Choose where to transfer your domain** page, select **A different registrar**, and then click **Next**.</span></span>

5. <span data-ttu-id="86329-113">Nella pagina **sblocco del dominio** , selezionare \*\*Sblocca trasferimento per <_il dominio_ > \*\*, quindi selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="86329-113">On the **Unlock domain transfer** page, select **Unlock transfer for <_your domain_>**, and then select **Next**.</span></span>

6. <span data-ttu-id="86329-114">Controllare le informazioni di contatto del trasferimento del dominio, quindi selezionare **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="86329-114">Check your domain transfer contact information, and then select **Next**.</span></span>

7. <span data-ttu-id="86329-115">Copiare il codice di autorizzazione e attendere circa 30 minuti perché lo stato di trasferimento del dominio venga modificato in **sbloccato per il trasferimento** nella scheda **registrazione** prima di procedere con i passaggi successivi.</span><span class="sxs-lookup"><span data-stu-id="86329-115">Copy the authorization code and wait about 30 minutes for your domain transfer status to change to **Unlocked for transfer** on the **Registration** tab before you proceed with next steps.</span></span>

8. <span data-ttu-id="86329-116">Passare al sito Web del registrar che si desidera gestire il nome di dominio in futuro.</span><span class="sxs-lookup"><span data-stu-id="86329-116">Go to the website of the domain registrar you want to manage your domain name going forward.</span></span> <span data-ttu-id="86329-117">Seguire le istruzioni per il trasferimento di un dominio (cercare assistenza sul proprio sito Web).</span><span class="sxs-lookup"><span data-stu-id="86329-117">Follow directions for transferring a domain (search for help on their website).</span></span>

<span data-ttu-id="86329-118">È possibile trovare la scheda di **registrazione** del codice di autorizzazione nella pagina  **Domains** in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="86329-118">You can find the authorization code **Registration** tab on the  **Domains** page in Microsoft 365.</span></span>

9. <span data-ttu-id="86329-119">Una volta completato il trasferimento, si rinnoverà il dominio presso il nuovo registrar.</span><span class="sxs-lookup"><span data-stu-id="86329-119">After the transfer is complete, you'll renew your domain at the new domain registrar.</span></span>

10. <span data-ttu-id="86329-120">Per completare il processo, tornare alla pagina **Domains** nell'interfaccia di amministrazione, quindi selezionare  **completa trasferimento del dominio**.</span><span class="sxs-lookup"><span data-stu-id="86329-120">To finish the process, go back to the **Domains** page in the admin center, and then select  **Complete domain transfer**.</span></span>

> [!NOTE]
> <span data-ttu-id="86329-121">I domini acquistati da Microsoft 365 non sono idonei per le modifiche ai server dei nomi o per il trasferimento del dominio tra organizzazioni Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="86329-121">Microsoft 365 purchased domains are not eligible for nameserver changes or transferring the domain between Microsoft 365 organizations.</span></span> <span data-ttu-id="86329-122">Se uno di questi due requisiti è necessario, la registrazione del dominio deve essere trasferita a un altro registrar.</span><span class="sxs-lookup"><span data-stu-id="86329-122">If either of these are required, the domain registration must be transferred to another registrar.</span></span>
