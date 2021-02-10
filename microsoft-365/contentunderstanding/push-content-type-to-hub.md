---
title: Spostare i tipi di contenuto in un hub
description: Informazioni su come spostare i tipi di contenuto in un hub
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
ms.openlocfilehash: 22d146b1d376bab134e82ad7d1313cb7881ca45b
ms.sourcegitcommit: 005028af7c5a6b2e95f17a0037958131484d9e73
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/08/2021
ms.locfileid: "50144972"
---
# <a name="push-content-types-to-a-hub"></a><span data-ttu-id="50ff4-103">Spostare i tipi di contenuto in un hub</span><span class="sxs-lookup"><span data-stu-id="50ff4-103">Push content types to a hub</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GyeV]  

</br>


<span data-ttu-id="50ff4-104">Per rendere i tipi di contenuto importanti disponibili in modo più coerente nelle raccolte e negli elenchi di SharePoint, è possibile scegliere gli hub in cui spostarli.</span><span class="sxs-lookup"><span data-stu-id="50ff4-104">To make important content types more consistently available to SharePoint libraries and lists, you can push them to the hubs that you choose.</span></span> <span data-ttu-id="50ff4-105">Quando si esegue il push, i tipi di contenuto vengono aggiunti ai nuovi elenchi e alle nuove raccolte creati nei siti associati all'hub e a qualsiasi altro nuovo sito aggiunto.</span><span class="sxs-lookup"><span data-stu-id="50ff4-105">Pushing the content types automatically adds them to any new lists and libraries created on the sites associated with the hub, and to any new sites added to the hub.</span></span> <span data-ttu-id="50ff4-106">Con questa funzionalità è richiesta una licenza di [SharePoint Syntex](index.md).</span><span class="sxs-lookup"><span data-stu-id="50ff4-106">This feature requires a [SharePoint Syntex](index.md) license.</span></span>

<span data-ttu-id="50ff4-107">Per usare questa funzionalità, i tipi di contenuto da spostare devono essere già pubblicati.</span><span class="sxs-lookup"><span data-stu-id="50ff4-107">For this feature to work, the content types being pushed must already be published.</span></span>

<span data-ttu-id="50ff4-108">Per spostare i tipi di contenuto in un hub</span><span class="sxs-lookup"><span data-stu-id="50ff4-108">To push content types to hubs</span></span>

1. <span data-ttu-id="50ff4-109">Nell'interfaccia di amministrazione di SharePoint, espandere **Servizi per contenuti** e quindi selezionare **Raccolta tipi di contenuto**.</span><span class="sxs-lookup"><span data-stu-id="50ff4-109">In the SharePoint admin center, expand **Content services**, and then select **Content type gallery**.</span></span>
2. <span data-ttu-id="50ff4-110">Selezionare il tipo di contenuto che si vuole spostare negli hub.</span><span class="sxs-lookup"><span data-stu-id="50ff4-110">Select the content type that you want to push to hubs.</span></span>
3. <span data-ttu-id="50ff4-111">Selezionare **Modifica** nella barra dei comandi.</span><span class="sxs-lookup"><span data-stu-id="50ff4-111">Select **Edit** in the command bar.</span></span>
4. <span data-ttu-id="50ff4-112">Selezionare **Scegli siti hub**.</span><span class="sxs-lookup"><span data-stu-id="50ff4-112">Select **Choose hub sites**.</span></span>
5. <span data-ttu-id="50ff4-113">Selezionare i siti hub desiderati e quindi e quindi scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="50ff4-113">Select the hub sites you want and then choose **OK**.</span></span>
6. <span data-ttu-id="50ff4-114">Scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="50ff4-114">Choose **Save**.</span></span>

<span data-ttu-id="50ff4-115">Quando si esegue per la prima volta il push di un tipo di contenuto in un hub esistente e nei relativi siti associati, l'aggiornamento delle impostazioni nel sito può richiedere fino a un'ora dal momento in cui l'hub o i siti associati vengono visitati.</span><span class="sxs-lookup"><span data-stu-id="50ff4-115">When you push a content type to an existing hub & its existing associated sites for the first time, it can take up to an hour from when the hub or associated sites are visited, for the settings to update in the site.</span></span> <span data-ttu-id="50ff4-116">Qualsiasi nuova associazione all'hub non richiederà un'attesa tanto lunga perché le impostazioni verranno applicate in pochi minuti.</span><span class="sxs-lookup"><span data-stu-id="50ff4-116">Any new associations to the hub won't require this wait and will have the settings reflected in a few minutes.</span></span>

<span data-ttu-id="50ff4-117">Dopo l'aggiornamento delle impostazioni, il tipo di contenuto con queste impostazioni sarà disponibile nel sito appena associato all'hub entro pochi minuti.</span><span class="sxs-lookup"><span data-stu-id="50ff4-117">After the settings are updated, the content type with these settings will be available in any newly associated site with the hub in a few minutes.</span></span> <span data-ttu-id="50ff4-118">In seguito, qualsiasi nuovo elenco o raccolta verrà aggiunto automaticamente al tipo di contenuto entro pochi minuti dalla creazione.</span><span class="sxs-lookup"><span data-stu-id="50ff4-118">Then, any new list or library created will have the content type automatically added to it within a few minutes of creation.</span></span> <span data-ttu-id="50ff4-119">Un tipo di contenuto spostato verrà aggiunto a una raccolta documenti solo se deriva direttamente o indirettamente dal tipo di contenuto del documento, mentre un tipo di contenuto verrà aggiunto a un elenco solo se non deriva direttamente o indirettamente dal tipo di contenuto del documento.</span><span class="sxs-lookup"><span data-stu-id="50ff4-119">A pushed content type will be added to a document library only if it derives directly or indirectly from the Document content type, and a content type will be added to a list only if it does not derive from the Document content type directly or indirectly.</span></span>

## <a name="see-also"></a><span data-ttu-id="50ff4-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="50ff4-120">See also</span></span>
