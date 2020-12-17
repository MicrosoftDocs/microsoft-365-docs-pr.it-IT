---
title: Creare una firma a livello di società
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
description: Informazioni su come creare una firma di posta elettronica a livello aziendale.
ms.openlocfilehash: 64c269abd25cab74ec5b0836975902e46a611c8c
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/17/2020
ms.locfileid: "49703027"
---
# <a name="create-a-company-wide-email-signature"></a><span data-ttu-id="e85d8-103">Creare una firma di posta elettronica a livello aziendale</span><span class="sxs-lookup"><span data-stu-id="e85d8-103">Create a company-wide email signature</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1IEWf?autoplay=false]

<span data-ttu-id="e85d8-104">Una firma di posta elettronica a livello aziendale viene visualizzata su tutti i messaggi di posta elettronica inviati da persone dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e85d8-104">A company-wide email signature appears on every email sent by people in your organization.</span></span> <span data-ttu-id="e85d8-105">È possibile utilizzarlo per visualizzare i dettagli importanti, come le informazioni di contatto dell'azienda o una dichiarazione di non responsabilità legale.</span><span class="sxs-lookup"><span data-stu-id="e85d8-105">You can use it to display important details, like your company contact information or a legal disclaimer.</span></span> 

## <a name="try-it"></a><span data-ttu-id="e85d8-106">Perché non provarlo?</span><span class="sxs-lookup"><span data-stu-id="e85d8-106">Try it!</span></span>

1. <span data-ttu-id="e85d8-107">Nell'interfaccia di amministrazione di Microsoft 365 selezionare **Exchange**.</span><span class="sxs-lookup"><span data-stu-id="e85d8-107">In the Microsoft 365 admin center, select **Exchange**.</span></span>
1. <span data-ttu-id="e85d8-108">Selezionare **flusso di posta**.</span><span class="sxs-lookup"><span data-stu-id="e85d8-108">Select **Mail flow**.</span></span>
1. <span data-ttu-id="e85d8-109">Selezionare **Aggiungi +**, quindi fare clic su **applica dichiarazioni** di non responsabilità.</span><span class="sxs-lookup"><span data-stu-id="e85d8-109">Select **Add +**, and then select **Apply disclaimers**.</span></span>
1. <span data-ttu-id="e85d8-110">Nella pagina **nuova regola** :</span><span class="sxs-lookup"><span data-stu-id="e85d8-110">On the **New rule** page:</span></span>
    1. <span data-ttu-id="e85d8-111">Immettere un nome per la regola.</span><span class="sxs-lookup"><span data-stu-id="e85d8-111">Enter a name for the rule.</span></span>
    1. <span data-ttu-id="e85d8-112">Nell'elenco a discesa **applica questa regola** , selezionare **applica a tutti i messaggi**.</span><span class="sxs-lookup"><span data-stu-id="e85d8-112">From the **Apply this rule if** drop-down list, select **Apply to all messages**.</span></span>
    1. <span data-ttu-id="e85d8-113">Nell'elenco a discesa **procedere come segue** , verificare che venga visualizzata **la dichiarazione** di non responsabilità.</span><span class="sxs-lookup"><span data-stu-id="e85d8-113">In the **Do the following** drop-down list, verify that **Append the disclaimer** is displayed.</span></span>
    1. <span data-ttu-id="e85d8-114">Nella parte destra della pagina, selezionare **Immetti testo** e quindi immettere il testo per la firma di posta elettronica nella casella di testo **specifica dichiarazione** di non responsabilità.</span><span class="sxs-lookup"><span data-stu-id="e85d8-114">On the right side of the page, select **Enter text**, and then enter the text for your email signature in the **Specify disclaimer** text box.</span></span> <span data-ttu-id="e85d8-115">È possibile migliorare l'aspetto della firma formattando il testo in formato HTML.</span><span class="sxs-lookup"><span data-stu-id="e85d8-115">You can improve the look of your signature by formatting the text with HTML.</span></span>
    1. <span data-ttu-id="e85d8-116">Se si desidera che un'immagine venga visualizzata nella firma, è necessario utilizzare un URL pubblico disponibile per l'immagine.</span><span class="sxs-lookup"><span data-stu-id="e85d8-116">If you want an image to appear in your signature, you'll need to use a publicly available URL for that image.</span></span> <span data-ttu-id="e85d8-117">Passare all'immagine sul Web, fare clic con il pulsante destro del mouse su di essa e scegliere **Copia indirizzo immagine**.</span><span class="sxs-lookup"><span data-stu-id="e85d8-117">Browse to the image on the web, right-click it, and select **Copy image address**.</span></span> <span data-ttu-id="e85d8-118">Incollare l'indirizzo nella casella di testo **specifica dichiarazione** di non responsabilità.</span><span class="sxs-lookup"><span data-stu-id="e85d8-118">Paste the address into the **Specify disclaimer** text box.</span></span> <span data-ttu-id="e85d8-119">Selezionare **OK**, quindi scorrere verso il basso.</span><span class="sxs-lookup"><span data-stu-id="e85d8-119">Select **OK**, then scroll down.</span></span>
    1. <span data-ttu-id="e85d8-120">Per assicurarsi che la firma funzioni con i messaggi di posta elettronica crittografati, aggiungere un'opzione di fallback.</span><span class="sxs-lookup"><span data-stu-id="e85d8-120">To make sure the signature works with encrypted emails, add a fallback option.</span></span> <span data-ttu-id="e85d8-121">Nella parte destra della pagina scegliere **Seleziona uno**, quindi seleziona a **capo** e quindi **OK**.</span><span class="sxs-lookup"><span data-stu-id="e85d8-121">On the right of the page, choose **Select one**, choose **Wrap**, and then select **OK**.</span></span>
    1. <span data-ttu-id="e85d8-122">Scorrere verso il basso e lasciare la modalità impostata su **applica**, quindi selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="e85d8-122">Scroll down and leave the mode set to **Enforce**, and then select **Save**.</span></span>
1. <span data-ttu-id="e85d8-123">Verrà visualizzato un messaggio di avviso.</span><span class="sxs-lookup"><span data-stu-id="e85d8-123">A warning message will appear.</span></span> <span data-ttu-id="e85d8-124">Selezionare **Sì** per applicare la regola a tutti i messaggi futuri.</span><span class="sxs-lookup"><span data-stu-id="e85d8-124">Select **Yes** to apply the rule to all future messages.</span></span>

    <span data-ttu-id="e85d8-125">La firma è stata creata.</span><span class="sxs-lookup"><span data-stu-id="e85d8-125">Your signature has been created.</span></span> <span data-ttu-id="e85d8-126">Quando si invia un messaggio di posta elettronica successivo, non verrà visualizzata la firma appena creata, ma verranno visualizzati i destinatari della posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="e85d8-126">When you send your next email, you won't see the signature you just created, but the email recipients will see it.</span></span>