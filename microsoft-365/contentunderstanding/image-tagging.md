---
title: Aggiunta di tag alle immagini in SharePoint Syntex
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Priority
description: Informazioni sull’aggiunta di tag alle immagini in SharePoint Syntex
ms.openlocfilehash: 38b9ad6823aa5f63a4ddec87bab7fec52a37f163
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/28/2020
ms.locfileid: "48296092"
---
# <a name="image-tagging-in-sharepoint-syntex"></a><span data-ttu-id="87a82-103">Aggiunta di tag alle immagini in SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="87a82-103">Image tagging in SharePoint Syntex</span></span>

<span data-ttu-id="87a82-104">Per impostazione predefinita, l’opzione di base dell’aggiunta di tag alle immagini è attivata per SharePoint e OneDrive.</span><span class="sxs-lookup"><span data-stu-id="87a82-104">By default, basic image tagging is turned on for SharePoint and OneDrive.</span></span> <span data-ttu-id="87a82-105">Le immagini caricate nelle due posizioni vengono analizzate e aggiunti i tag automaticamente, se disponibili, da un elenco di 37 tag di base.</span><span class="sxs-lookup"><span data-stu-id="87a82-105">Images uploaded to either location are automatically scanned and applicable tags are applied, if available, from a list of 37 basic tags.</span></span> <span data-ttu-id="87a82-106">Gli utenti possono trovare le immagini tramite la ricerca in base al tag di un’immagine.</span><span class="sxs-lookup"><span data-stu-id="87a82-106">Users can find images through search by searching on the image tags.</span></span>

<span data-ttu-id="87a82-107">Quando un utente carica un'immagine, il processo di aggiunta di tag viene eseguito automaticamente.</span><span class="sxs-lookup"><span data-stu-id="87a82-107">When a user uploads an image, the  tagging process runs automatically.</span></span> <span data-ttu-id="87a82-108">Se si modifica un'immagine, il processo viene eseguito di nuovo per aggiornare i tag.</span><span class="sxs-lookup"><span data-stu-id="87a82-108">If an image is edited, the tagging process runs again to update the tags.</span></span>

<span data-ttu-id="87a82-109">Gli utenti con autorizzazioni di accesso al file di immagine possono visualizzare e modificare i tag nel riquadro delle informazioni del file o nella pagina dei risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="87a82-109">Users with permissions to the image file can see and edit the tags in the file information panel or in the search results page.</span></span> <span data-ttu-id="87a82-110">Dopo che un utente ha modificato i tag di un'immagine, il sistema non esegue più l’aggiunta automatica di tag su tale immagine, anche se è stata modificata.</span><span class="sxs-lookup"><span data-stu-id="87a82-110">Once a user edits an image's tags, the system no longer performs auto-tagging on that image, even if it is edited.</span></span>

<span data-ttu-id="87a82-111">Se si disattiva l’aggiunta di tag, alle immagini non verranno più applicati tag automaticamente.</span><span class="sxs-lookup"><span data-stu-id="87a82-111">If you turn tagging off, images will no longer be automatically tagged.</span></span> <span data-ttu-id="87a82-112">I tag esistenti non verranno rimossi.</span><span class="sxs-lookup"><span data-stu-id="87a82-112">Existing tags will not be removed.</span></span>

## <a name="configure-image-tagging"></a><span data-ttu-id="87a82-113">Configurare l’aggiunta di tag alle immagini</span><span class="sxs-lookup"><span data-stu-id="87a82-113">Configure image tagging</span></span>

<span data-ttu-id="87a82-114">È possibile configurare l’aggiunta di tag alle immagini nell'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="87a82-114">You can configure image tagging in the Microsoft 365 admin center.</span></span>  

<span data-ttu-id="87a82-115">Per attivare o disattivare l’aggiunta di tag</span><span class="sxs-lookup"><span data-stu-id="87a82-115">To turn image tagging on or off</span></span>

1. <span data-ttu-id="87a82-116">Nell'interfaccia di amministrazione di Microsoft 365, fare clic su **Configurazione**.</span><span class="sxs-lookup"><span data-stu-id="87a82-116">In the Microsoft 365 admin center, click **Setup**.</span></span>

2. <span data-ttu-id="87a82-117">In **Conoscenza organizzativa**, fare clic su **Automatizza la comprensione dei contenuti**.</span><span class="sxs-lookup"><span data-stu-id="87a82-117">Under **Organizational knowledge**, click **Automate content understanding**.</span></span>

3. <span data-ttu-id="87a82-118">Fare clic su **Gestisci**.</span><span class="sxs-lookup"><span data-stu-id="87a82-118">Click **Manage**.</span></span>

4. <span data-ttu-id="87a82-119">Nella scheda **Aggiunta di tag alle immagini** fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="87a82-119">On the **Image tagging** tab, click **Edit**.</span></span>

5. <span data-ttu-id="87a82-120">Scegliere **Aggiunta di tag di base** o **Disattiva**.</span><span class="sxs-lookup"><span data-stu-id="87a82-120">Choose to allow **Basic tagging** or turn tagging **Off**.</span></span>

6. <span data-ttu-id="87a82-121">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="87a82-121">Click **Save**.</span></span>

    ![Schermata di controllo dell’aggiunta di tag alle immagini](../media/content-understanding/sharepoint-syntex-image-tagging-control.png)

## <a name="see-also"></a><span data-ttu-id="87a82-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="87a82-123">See also</span></span>

<span data-ttu-id="87a82-124">[Configurare la comprensione dei contenuti](set-up-content-understanding.md).</span><span class="sxs-lookup"><span data-stu-id="87a82-124">[Set up content understanding](set-up-content-understanding.md)</span></span>