---
title: Interrompere l'inoltro automatico dei messaggi di posta elettronica
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
description: Informazioni su come interrompere l'inoltro automatico dei messaggi di posta elettronica.
ms.openlocfilehash: ca4383a3f9d64a123955ebe005d0fad5819d3a5d
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/04/2021
ms.locfileid: "50421800"
---
# <a name="stop-email-auto-forward"></a><span data-ttu-id="fa07e-103">Arrestare l'inoltro automatico della posta elettronica</span><span class="sxs-lookup"><span data-stu-id="fa07e-103">Stop email auto-forward</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2W6kS?autoplay=false]

<span data-ttu-id="fa07e-104">Se un pirata informatico ottiene l'accesso alla cassetta postale di un utente, può inoltrare automaticamente la posta elettronica dell'utente a un indirizzo esterno e rubare informazioni proprietarie.</span><span class="sxs-lookup"><span data-stu-id="fa07e-104">If a hacker gains access to a user's mailbox, they can auto-forward the user's email to an outside address and steal proprietary information.</span></span> <span data-ttu-id="fa07e-105">È possibile interrompere questa operazione creando una regola del flusso di posta.</span><span class="sxs-lookup"><span data-stu-id="fa07e-105">You can stop this by creating a mail flow rule.</span></span>

## <a name="try-it"></a><span data-ttu-id="fa07e-106">Perché non provarlo?</span><span class="sxs-lookup"><span data-stu-id="fa07e-106">Try it!</span></span>

1. <span data-ttu-id="fa07e-107">Nell'interfaccia di amministrazione di Microsoft 365 selezionare  **Exchange,** flusso di posta e, nella scheda delle regole, selezionare il segno più e scegliere **crea una nuova regola.** </span><span class="sxs-lookup"><span data-stu-id="fa07e-107">From the Microsoft 365 admin center, select **Exchange**, **mail flow**, and on the **rules** tab, select the plus sign and choose **create a new rule**.</span></span>
1. <span data-ttu-id="fa07e-108">Selezionare **Altre opzioni.**</span><span class="sxs-lookup"><span data-stu-id="fa07e-108">Select **More options**.</span></span> <span data-ttu-id="fa07e-109">Assegnare un nome alla nuova regola.</span><span class="sxs-lookup"><span data-stu-id="fa07e-109">Name your new rule.</span></span>
1. <span data-ttu-id="fa07e-110">Aprire quindi l'elenco a discesa per **applicare questa regola se**, selezionare **il** mittente e quindi è **interno esterno.**</span><span class="sxs-lookup"><span data-stu-id="fa07e-110">Then open the drop-down for **apply this rule if**, select **the sender**, and then **is external internal**.</span></span>
1. <span data-ttu-id="fa07e-111">Selezionare **Interno all'organizzazione** e quindi **OK.**</span><span class="sxs-lookup"><span data-stu-id="fa07e-111">Select **Inside the organization**, and then **OK**.</span></span>
1. <span data-ttu-id="fa07e-112">Scegliere **aggiungi condizione,** aprire l'elenco a discesa, selezionare **Le proprietà del** messaggio, quindi includere il tipo di **messaggio.**</span><span class="sxs-lookup"><span data-stu-id="fa07e-112">Choose **add condition**, open the drop-down, select **The message properties**, then **include the message type**.</span></span>
1. <span data-ttu-id="fa07e-113">Aprire **l'elenco a** discesa Seleziona tipo di messaggio, scegliere **Inoltro automatico,** quindi **OK.**</span><span class="sxs-lookup"><span data-stu-id="fa07e-113">Open the **select message type** drop-down, choose **Auto-forward**, then **OK**.</span></span>
1. <span data-ttu-id="fa07e-114">Aprire **l'elenco** a discesa Fare quanto segue, selezionare **Blocca il messaggio,** **rifiutare il messaggio e includere una spiegazione.**</span><span class="sxs-lookup"><span data-stu-id="fa07e-114">Open the **Do the following** drop-down, select **Block the message**, then **reject the message and include an explanation**.</span></span>
1. <span data-ttu-id="fa07e-115">Immettere il testo del messaggio per la spiegazione, quindi selezionare **OK.**</span><span class="sxs-lookup"><span data-stu-id="fa07e-115">Enter the message text for your explanation, then select **OK**.</span></span>
1. <span data-ttu-id="fa07e-116">Scorrere verso il basso e selezionare **Salva.**</span><span class="sxs-lookup"><span data-stu-id="fa07e-116">Scroll to the bottom and select **Save**.</span></span>

    <span data-ttu-id="fa07e-117">La regola è stata creata e i pirati informatici non saranno più in grado di inoltrare automaticamente i messaggi.</span><span class="sxs-lookup"><span data-stu-id="fa07e-117">Your rule has been created, and hackers will no longer be able to auto-forward messages.</span></span>