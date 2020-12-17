---
title: Interrompere l'inoltro automatico di messaggi di posta elettronica
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
description: Informazioni su come interrompere l'inoltro automatico di messaggi di posta elettronica.
ms.openlocfilehash: 0683e133f6c261dc19cc098b13be298cd8086001
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/17/2020
ms.locfileid: "49702021"
---
# <a name="stop-email-auto-forward"></a><span data-ttu-id="b7333-103">Interrompere l'inoltro automatico della posta elettronica</span><span class="sxs-lookup"><span data-stu-id="b7333-103">Stop email auto-forward</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2W6kS?autoplay=false]

<span data-ttu-id="b7333-104">Se un pirata informatico accede alla cassetta postale di un utente, può inoltrare automaticamente la posta elettronica dell'utente a un indirizzo esterno e rubare informazioni proprietarie.</span><span class="sxs-lookup"><span data-stu-id="b7333-104">If a hacker gains access to a user's mailbox, they can auto-forward the user's email to an outside address and steal proprietary information.</span></span> <span data-ttu-id="b7333-105">Questa operazione può essere interrotta creando una regola del flusso di posta.</span><span class="sxs-lookup"><span data-stu-id="b7333-105">You can stop this by creating a mail flow rule.</span></span>

## <a name="try-it"></a><span data-ttu-id="b7333-106">Perché non provarlo?</span><span class="sxs-lookup"><span data-stu-id="b7333-106">Try it!</span></span>

1. <span data-ttu-id="b7333-107">Nell'interfaccia di amministrazione di Microsoft 365 selezionare **Exchange**, **flusso di posta** e nella scheda **regole** selezionare il segno più e scegliere **Crea nuova regola**.</span><span class="sxs-lookup"><span data-stu-id="b7333-107">From the Microsoft 365 admin center, select **Exchange**, **mail flow**, and on the **rules** tab, select the plus sign and choose **create a new rule**.</span></span>
1. <span data-ttu-id="b7333-108">Selezionare **altre opzioni**.</span><span class="sxs-lookup"><span data-stu-id="b7333-108">Select **More options**.</span></span> <span data-ttu-id="b7333-109">Assegnare un nome alla nuova regola.</span><span class="sxs-lookup"><span data-stu-id="b7333-109">Name your new rule.</span></span>
1. <span data-ttu-id="b7333-110">Aprire quindi il menu a discesa per **applicare la regola se**, selezionare **il mittente** e quindi **interno esterno**.</span><span class="sxs-lookup"><span data-stu-id="b7333-110">Then open the drop-down for **apply this rule if**, select **the sender**, and then **is external internal**.</span></span>
1. <span data-ttu-id="b7333-111">Selezionare **all'interno dell'organizzazione** e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="b7333-111">Select **Inside the organization**, and then **OK**.</span></span>
1. <span data-ttu-id="b7333-112">Scegliere **Aggiungi condizione**, aprire l'elenco a discesa, selezionare **le proprietà del messaggio** e quindi **includere il tipo di messaggio**.</span><span class="sxs-lookup"><span data-stu-id="b7333-112">Choose **add condition**, open the drop-down, select **The message properties**, then **include the message type**.</span></span>
1. <span data-ttu-id="b7333-113">Aprire l'elenco a discesa **Seleziona tipo di messaggio** , scegliere **inoltro automatico** e quindi **OK**.</span><span class="sxs-lookup"><span data-stu-id="b7333-113">Open the **select message type** drop-down, choose **Auto-forward**, then **OK**.</span></span>
1. <span data-ttu-id="b7333-114">Aprire l'elenco a discesa **procedere come segue** , selezionare **blocca il messaggio**, quindi **rifiutare il messaggio e includere una spiegazione**.</span><span class="sxs-lookup"><span data-stu-id="b7333-114">Open the **Do the following** drop-down, select **Block the message**, then **reject the message and include an explanation**.</span></span>
1. <span data-ttu-id="b7333-115">Immettere il testo del messaggio per la spiegazione, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="b7333-115">Enter the message text for your explanation, then select **OK**.</span></span>
1. <span data-ttu-id="b7333-116">Scorrere fino alla fine e selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="b7333-116">Scroll to the bottom and select **Save**.</span></span>

    <span data-ttu-id="b7333-117">La regola è stata creata e gli hacker non saranno più in grado di inoltrare automaticamente i messaggi.</span><span class="sxs-lookup"><span data-stu-id="b7333-117">Your rule has been created, and hackers will no longer be able to auto-forward messages.</span></span>