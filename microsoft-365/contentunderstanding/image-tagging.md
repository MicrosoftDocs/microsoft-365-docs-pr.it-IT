---
title: Aggiunta di tag alle immagini in SharePoint Syntex
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
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Informazioni sull’aggiunta di tag alle immagini in SharePoint Syntex
ms.openlocfilehash: 0fba54db6a16a9a8571c7e1ced61b7620cf5113e
ms.sourcegitcommit: 162c01dfaa2fdb3225ce4c24964c1065ce22ed5d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/25/2021
ms.locfileid: "49975866"
---
# <a name="image-tagging-in-sharepoint-syntex"></a><span data-ttu-id="42fab-103">Aggiunta di tag alle immagini in SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="42fab-103">Image tagging in SharePoint Syntex</span></span>

<span data-ttu-id="42fab-104">(Presto disponibile)</span><span class="sxs-lookup"><span data-stu-id="42fab-104">(Coming soon)</span></span>

<span data-ttu-id="42fab-105">Con l'aggiunta di tag di immagini in SharePoint Syntex, gli utenti possono trovare immagini attraverso la ricerca per tag di immagine e creare flussi di lavoro in base ai tag di immagine.</span><span class="sxs-lookup"><span data-stu-id="42fab-105">With image tagging in SharePoint Syntex, users can find images through search by searching on image tags, and create workflows based on image tags.</span></span> <span data-ttu-id="42fab-106">Per impostazione predefinita, l’opzione di base dell’aggiunta di tag alle immagini è attivata per SharePoint e OneDrive.</span><span class="sxs-lookup"><span data-stu-id="42fab-106">By default, basic image tagging is turned on for SharePoint and OneDrive.</span></span> <span data-ttu-id="42fab-107">Le immagini caricate nelle due posizioni vengono analizzate e aggiunti i tag automaticamente, se disponibili, da un elenco di 37 tag di base.</span><span class="sxs-lookup"><span data-stu-id="42fab-107">Images uploaded to either location are automatically scanned and applicable tags are applied, if available, from a list of 37 basic tags.</span></span> <span data-ttu-id="42fab-108">Gli utenti possono trovare le immagini tramite la ricerca in base al tag di un’immagine.</span><span class="sxs-lookup"><span data-stu-id="42fab-108">Users can find images through search by searching on the image tags.</span></span>

<span data-ttu-id="42fab-109">Quando un utente carica un'immagine, il processo di aggiunta di tag viene eseguito automaticamente.</span><span class="sxs-lookup"><span data-stu-id="42fab-109">When a user uploads an image, the  tagging process runs automatically.</span></span> <span data-ttu-id="42fab-110">Se si modifica un'immagine, il processo viene eseguito di nuovo per aggiornare i tag.</span><span class="sxs-lookup"><span data-stu-id="42fab-110">If an image is edited, the tagging process runs again to update the tags.</span></span>

<span data-ttu-id="42fab-111">Gli utenti con autorizzazioni di accesso al file di immagine possono visualizzare e modificare i tag nel riquadro delle informazioni del file o nella pagina dei risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="42fab-111">Users with permissions to the image file can see and edit the tags in the file information panel or in the search results page.</span></span> <span data-ttu-id="42fab-112">Dopo che un utente ha modificato i tag di immagine, il sistema non esegue più l'aggiunta automatica di tag su tale immagine, anche se è stata modificata.</span><span class="sxs-lookup"><span data-stu-id="42fab-112">Once a user edits an image's tags, the system no longer auto-tags that image, even if it's edited.</span></span>

<span data-ttu-id="42fab-113">Se si disattiva l’aggiunta di tag, alle immagini non verranno più applicati tag automaticamente.</span><span class="sxs-lookup"><span data-stu-id="42fab-113">If you turn tagging off, images will no longer be automatically tagged.</span></span> <span data-ttu-id="42fab-114">I tag esistenti non verranno rimossi.</span><span class="sxs-lookup"><span data-stu-id="42fab-114">Existing tags won't be removed.</span></span>

> [!NOTE]
> <span data-ttu-id="42fab-115">I tag generati dai sistemi potrebbero cambiare con gli aggiornamenti dell'immagine o con la tecnologia dei tag.</span><span class="sxs-lookup"><span data-stu-id="42fab-115">System generated tags may change with updates to the image or our tag technology.</span></span>


## <a name="configure-image-tagging"></a><span data-ttu-id="42fab-116">Configurare l’aggiunta di tag alle immagini</span><span class="sxs-lookup"><span data-stu-id="42fab-116">Configure image tagging</span></span>

<span data-ttu-id="42fab-117">Dopo aver [configurato SharePoint Syntex](set-up-content-understanding.md), è possibile configurare l’aggiunta di tag alle immagini nell'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="42fab-117">After you [set up SharePoint Syntex](set-up-content-understanding.md), you can configure image tagging in the Microsoft 365 admin center.</span></span>  

<span data-ttu-id="42fab-118">Per attivare o disattivare l’aggiunta di tag</span><span class="sxs-lookup"><span data-stu-id="42fab-118">To turn image tagging on or off</span></span>

1. <span data-ttu-id="42fab-119">Nell'interfaccia di amministrazione di Microsoft 365, fare clic su **Configurazione**.</span><span class="sxs-lookup"><span data-stu-id="42fab-119">In the Microsoft 365 admin center, click **Setup**.</span></span>

2. <span data-ttu-id="42fab-120">In **Conoscenza organizzativa**, fare clic su **Automatizza la comprensione dei contenuti**.</span><span class="sxs-lookup"><span data-stu-id="42fab-120">Under **Organizational knowledge**, click **Automate content understanding**.</span></span>

3. <span data-ttu-id="42fab-121">Fare clic su **Gestisci**.</span><span class="sxs-lookup"><span data-stu-id="42fab-121">Click **Manage**.</span></span>

4. <span data-ttu-id="42fab-122">Nella scheda **Aggiunta di tag alle immagini** fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="42fab-122">On the **Image tagging** tab, click **Edit**.</span></span>

5. <span data-ttu-id="42fab-123">Scegliere **Aggiunta di tag di base** o **Disattiva**.</span><span class="sxs-lookup"><span data-stu-id="42fab-123">Choose to allow **Basic tagging** or turn tagging **Off**.</span></span>

6. <span data-ttu-id="42fab-124">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="42fab-124">Click **Save**.</span></span>

    ![Schermata di controllo dell’aggiunta di tag alle immagini](../media/content-understanding/sharepoint-syntex-image-tagging-control.png)
