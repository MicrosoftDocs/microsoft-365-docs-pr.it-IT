---
title: Creare una firma a livello aziendale
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
- okr_smb
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Informazioni su come creare una firma di posta elettronica a livello aziendale.
ms.openlocfilehash: 3a9623837b3a68fa8cc0fb378293ec463d9bb789
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49928304"
---
# <a name="create-a-company-wide-email-signature"></a><span data-ttu-id="dadfd-103">Creare una firma di posta elettronica a livello aziendale</span><span class="sxs-lookup"><span data-stu-id="dadfd-103">Create a company-wide email signature</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1IEWf?autoplay=false]

<span data-ttu-id="dadfd-104">In ogni messaggio di posta elettronica inviato dagli utenti dell'organizzazione viene visualizzata una firma di posta elettronica a livello aziendale.</span><span class="sxs-lookup"><span data-stu-id="dadfd-104">A company-wide email signature appears on every email sent by people in your organization.</span></span> <span data-ttu-id="dadfd-105">È possibile utilizzarlo per visualizzare dettagli importanti, ad esempio le informazioni di contatto dell'azienda o una dichiarazione di non responsabilità legale.</span><span class="sxs-lookup"><span data-stu-id="dadfd-105">You can use it to display important details, like your company contact information or a legal disclaimer.</span></span> 

## <a name="try-it"></a><span data-ttu-id="dadfd-106">Perché non provarlo?</span><span class="sxs-lookup"><span data-stu-id="dadfd-106">Try it!</span></span>

1. <span data-ttu-id="dadfd-107">Nell'interfaccia di amministrazione di Microsoft 365 selezionare **Exchange.**</span><span class="sxs-lookup"><span data-stu-id="dadfd-107">In the Microsoft 365 admin center, select **Exchange**.</span></span>
1. <span data-ttu-id="dadfd-108">Selezionare **Flusso di posta**.</span><span class="sxs-lookup"><span data-stu-id="dadfd-108">Select **Mail flow**.</span></span>
1. <span data-ttu-id="dadfd-109">Selezionare **Aggiungi +** e quindi Applica dichiarazioni di non **responsabilità.**</span><span class="sxs-lookup"><span data-stu-id="dadfd-109">Select **Add +**, and then select **Apply disclaimers**.</span></span>
1. <span data-ttu-id="dadfd-110">Nella pagina **Nuova** regola:</span><span class="sxs-lookup"><span data-stu-id="dadfd-110">On the **New rule** page:</span></span>
    1. <span data-ttu-id="dadfd-111">Immettere un nome per la regola.</span><span class="sxs-lookup"><span data-stu-id="dadfd-111">Enter a name for the rule.</span></span>
    1. <span data-ttu-id="dadfd-112">**Nell'elenco a** discesa Applica questa regola se selezionare Applica a tutti i **messaggi.**</span><span class="sxs-lookup"><span data-stu-id="dadfd-112">From the **Apply this rule if** drop-down list, select **Apply to all messages**.</span></span>
    1. <span data-ttu-id="dadfd-113">**Nell'elenco** a discesa Fare quanto segue verificare che **sia** visualizzato Aggiungi dichiarazione di non responsabilità.</span><span class="sxs-lookup"><span data-stu-id="dadfd-113">In the **Do the following** drop-down list, verify that **Append the disclaimer** is displayed.</span></span>
    1. <span data-ttu-id="dadfd-114">Sul lato destro della pagina, selezionare Immetti testo **e** quindi immettere il testo per la firma di posta elettronica nella casella di testo Specifica dichiarazione **di** non responsabilità.</span><span class="sxs-lookup"><span data-stu-id="dadfd-114">On the right side of the page, select **Enter text**, and then enter the text for your email signature in the **Specify disclaimer** text box.</span></span> <span data-ttu-id="dadfd-115">È possibile migliorare l'aspetto della firma formattazione del testo con HTML.</span><span class="sxs-lookup"><span data-stu-id="dadfd-115">You can improve the look of your signature by formatting the text with HTML.</span></span>
    1. <span data-ttu-id="dadfd-116">Se vuoi che un'immagine venga visualizzata nella firma, dovrai usare un URL disponibile pubblicamente per tale immagine.</span><span class="sxs-lookup"><span data-stu-id="dadfd-116">If you want an image to appear in your signature, you'll need to use a publicly available URL for that image.</span></span> <span data-ttu-id="dadfd-117">Passare all'immagine sul Web, fare clic con il pulsante destro del mouse e scegliere **Copia indirizzo immagine.**</span><span class="sxs-lookup"><span data-stu-id="dadfd-117">Browse to the image on the web, right-click it, and select **Copy image address**.</span></span> <span data-ttu-id="dadfd-118">Incollare l'indirizzo nella **casella di testo** Specifica dichiarazione di non responsabilità.</span><span class="sxs-lookup"><span data-stu-id="dadfd-118">Paste the address into the **Specify disclaimer** text box.</span></span> <span data-ttu-id="dadfd-119">Selezionare **OK,** quindi scorrere verso il basso.</span><span class="sxs-lookup"><span data-stu-id="dadfd-119">Select **OK**, then scroll down.</span></span>
    1. <span data-ttu-id="dadfd-120">Per assicurarsi che la firma funzioni con i messaggi di posta elettronica crittografati, aggiungere un'opzione di fallback.</span><span class="sxs-lookup"><span data-stu-id="dadfd-120">To make sure the signature works with encrypted emails, add a fallback option.</span></span> <span data-ttu-id="dadfd-121">A destra della pagina scegliere **Seleziona** uno, **Scegliere** Ritorno a capo e quindi **OK.**</span><span class="sxs-lookup"><span data-stu-id="dadfd-121">On the right of the page, choose **Select one**, choose **Wrap**, and then select **OK**.</span></span>
    1. <span data-ttu-id="dadfd-122">Scorrere verso il basso e lasciare la modalità impostata **su Applica** e quindi selezionare **Salva.**</span><span class="sxs-lookup"><span data-stu-id="dadfd-122">Scroll down and leave the mode set to **Enforce**, and then select **Save**.</span></span>
1. <span data-ttu-id="dadfd-123">Verrà visualizzato un messaggio di avviso.</span><span class="sxs-lookup"><span data-stu-id="dadfd-123">A warning message will appear.</span></span> <span data-ttu-id="dadfd-124">Selezionare **Sì** per applicare la regola a tutti i messaggi futuri.</span><span class="sxs-lookup"><span data-stu-id="dadfd-124">Select **Yes** to apply the rule to all future messages.</span></span>

    <span data-ttu-id="dadfd-125">La firma è stata creata.</span><span class="sxs-lookup"><span data-stu-id="dadfd-125">Your signature has been created.</span></span> <span data-ttu-id="dadfd-126">When you send your next email, you won't see the signature you just created, but the email recipients will see it.</span><span class="sxs-lookup"><span data-stu-id="dadfd-126">When you send your next email, you won't see the signature you just created, but the email recipients will see it.</span></span>