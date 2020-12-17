---
title: Creare regole di posta elettronica per ransomware
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
description: Informazioni su come creare regole di posta elettronica per impedire il ransomware.
ms.openlocfilehash: 85898480438225848fc09db9a9c507045f8a182c
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/17/2020
ms.locfileid: "49701932"
---
# <a name="create-email-rules-to-prevent-ransomware"></a><span data-ttu-id="c3d43-103">Creare regole di posta elettronica per impedire ransomware</span><span class="sxs-lookup"><span data-stu-id="c3d43-103">Create email rules to prevent ransomware</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWrWGt?autoplay=false]

<span data-ttu-id="c3d43-104">Microsoft 365 aiuta a proteggere la propria azienda dal ransomware impedendo l'apertura di file potenzialmente pericolosi, come JavaScript, batch e eseguibili, in Outlook.</span><span class="sxs-lookup"><span data-stu-id="c3d43-104">Microsoft 365 helps protect your business against ransomware by preventing potentially dangerous files, like JavaScript, batch, and executables, from being opened in Outlook.</span></span> <span data-ttu-id="c3d43-105">Per aumentare questo livello di protezione aggiungendo regole che bloccano o avvertono altri tipi di file, attenersi alla seguente procedura.</span><span class="sxs-lookup"><span data-stu-id="c3d43-105">To increase this level of protection by adding rules that block or warn you of additional types of files, follow these steps.</span></span>

## <a name="try-it"></a><span data-ttu-id="c3d43-106">Perché non provarlo?</span><span class="sxs-lookup"><span data-stu-id="c3d43-106">Try it!</span></span>

1. <span data-ttu-id="c3d43-107">Nell'interfaccia di amministrazione [https://admin.microsoft.com](https://admin.microsoft.com) scegliere **Exchange** in interfaccia di **Amministrazione**.</span><span class="sxs-lookup"><span data-stu-id="c3d43-107">From the admin center at [https://admin.microsoft.com](https://admin.microsoft.com), choose **Exchange** under **Admin centers**.</span></span>
1. <span data-ttu-id="c3d43-108">Scegliere **flusso di posta** dal menu a sinistra.</span><span class="sxs-lookup"><span data-stu-id="c3d43-108">From the menu on the left, choose **mail flow**.</span></span>
1. <span data-ttu-id="c3d43-109">Nella scheda regole scegliere la freccia accanto al simbolo più (+) e quindi fare clic su **Crea una nuova regola**.</span><span class="sxs-lookup"><span data-stu-id="c3d43-109">On the rules tab, choose the arrow next to the plus (+) symbol, and then choose **Create a new rule**.</span></span>
1. <span data-ttu-id="c3d43-110">Nella pagina **nuova regola** , immettere un nome per la regola, scorrere fino alla fine e quindi scegliere **altre opzioni**.</span><span class="sxs-lookup"><span data-stu-id="c3d43-110">On the **new rule** page, enter a name for your rule, scroll to the bottom, and then choose **More options**.</span></span>
1. <span data-ttu-id="c3d43-111">In **applica la regola se**, selezionare **qualsiasi allegato**, quindi selezionare **estensione file include queste parole**.</span><span class="sxs-lookup"><span data-stu-id="c3d43-111">Under **Apply this rule if**, select **Any attachment**, and then select **file extension includes these words**.</span></span>
1. <span data-ttu-id="c3d43-112">Nella casella in **specificare parole o frasi**, immettere le estensioni di file a cui si desidera applicare la regola, ad esempio le estensioni di file che possono contenere macro.</span><span class="sxs-lookup"><span data-stu-id="c3d43-112">In the box under **specify words or phrases**, enter the file extensions that you want the rule to be applied to, such as file extensions that can contain macros.</span></span> <span data-ttu-id="c3d43-113">Utilizzare il segno più (+) per aggiungerne uno alla volta.</span><span class="sxs-lookup"><span data-stu-id="c3d43-113">Use the plus (+) symbol to add them one at a time.</span></span>

    <span data-ttu-id="c3d43-114">Per ulteriori informazioni sui tipi di file, leggere [Protect Against ransomware](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/secure-your-business-data#ransomware).</span><span class="sxs-lookup"><span data-stu-id="c3d43-114">Learn more about file types by reading [Protect against ransomware](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/secure-your-business-data#ransomware).</span></span>

1. <span data-ttu-id="c3d43-115">Scorrere verso il basso per esaminare l'elenco e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="c3d43-115">Scroll down to review your list, and then choose **OK**.</span></span>
1. <span data-ttu-id="c3d43-116">Nella pagina **nuova regola** scegliere **Aggiungi condizione** e quindi fare clic su una condizione in **eseguire le operazioni seguenti**.</span><span class="sxs-lookup"><span data-stu-id="c3d43-116">On the **new rule** page, choose **add condition**, and then choose a condition under **Do the following**.</span></span>
1. <span data-ttu-id="c3d43-117">È possibile scegliere tra molte opzioni di regola, ma in questo esempio si sceglie di **notificare al destinatario un messaggio**.</span><span class="sxs-lookup"><span data-stu-id="c3d43-117">You have many rule options to choose from, but in this example we'll choose to **Notify the recipient with a message**.</span></span>
1. <span data-ttu-id="c3d43-118">Immettere il testo del messaggio per la notifica e quindi scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="c3d43-118">Enter message text for your notification, and then chose **OK**.</span></span>
1. <span data-ttu-id="c3d43-119">Facoltativo: nella pagina **nuova regola** scegliere **Aggiungi eccezione** e immettere tutti i dettagli relativi alle eccezioni alla regola, ad esempio i messaggi provenienti da mittenti attendibili.</span><span class="sxs-lookup"><span data-stu-id="c3d43-119">Optional: On the **new rule** page, choose **add exception**, and enter any details for exceptions to your rule, such as messages from trusted senders.</span></span>
1. <span data-ttu-id="c3d43-120">Nella pagina nuova regola scegliere **Salva** ed esaminare le informazioni di riepilogo delle regole fornite.</span><span class="sxs-lookup"><span data-stu-id="c3d43-120">On the new rule page, choose **Save**, and review the rule summary information provided.</span></span>