---
title: Creare regole di posta elettronica per i ransomware
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
description: Informazioni su come creare regole di posta elettronica per impedire ransomware.
ms.openlocfilehash: 34590945b13408cf3521f000d703bd37e04ba73f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50913551"
---
# <a name="create-email-rules-to-prevent-ransomware"></a><span data-ttu-id="2b6f4-103">Creare regole di posta elettronica per impedire ransomware</span><span class="sxs-lookup"><span data-stu-id="2b6f4-103">Create email rules to prevent ransomware</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWrWGt?autoplay=false]

<span data-ttu-id="2b6f4-104">Microsoft 365 consente di proteggere l'azienda da ransomware impedendo l'apertura di file potenzialmente pericolosi, come JavaScript, batch ed eseguibili, in Outlook.</span><span class="sxs-lookup"><span data-stu-id="2b6f4-104">Microsoft 365 helps protect your business against ransomware by preventing potentially dangerous files, like JavaScript, batch, and executables, from being opened in Outlook.</span></span> <span data-ttu-id="2b6f4-105">Per aumentare questo livello di protezione aggiungendo regole che bloccano o avvisano l'utente di altri tipi di file, eseguire la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="2b6f4-105">To increase this level of protection by adding rules that block or warn you of additional types of files, follow these steps.</span></span>

## <a name="try-it"></a><span data-ttu-id="2b6f4-106">Perché non provarlo?</span><span class="sxs-lookup"><span data-stu-id="2b6f4-106">Try it!</span></span>

1. <span data-ttu-id="2b6f4-107">Nell'interfaccia di amministrazione di [https://admin.microsoft.com](https://admin.microsoft.com) , scegliere **Exchange** in Interfaccia **di amministrazione**.</span><span class="sxs-lookup"><span data-stu-id="2b6f4-107">From the admin center at [https://admin.microsoft.com](https://admin.microsoft.com), choose **Exchange** under **Admin centers**.</span></span>
1. <span data-ttu-id="2b6f4-108">Scegliere Flusso di posta dal menu **a sinistra.**</span><span class="sxs-lookup"><span data-stu-id="2b6f4-108">From the menu on the left, choose **mail flow**.</span></span>
1. <span data-ttu-id="2b6f4-109">Nella scheda regole scegliere la freccia accanto al simbolo più (+), quindi scegliere **Crea una nuova regola.**</span><span class="sxs-lookup"><span data-stu-id="2b6f4-109">On the rules tab, choose the arrow next to the plus (+) symbol, and then choose **Create a new rule**.</span></span>
1. <span data-ttu-id="2b6f4-110">Nella pagina **nuova regola** immettere un nome per la regola, scorrere verso il basso e quindi scegliere **Altre opzioni.**</span><span class="sxs-lookup"><span data-stu-id="2b6f4-110">On the **new rule** page, enter a name for your rule, scroll to the bottom, and then choose **More options**.</span></span>
1. <span data-ttu-id="2b6f4-111">In **Applica questa regola se**, selezionare Qualsiasi **allegato** e quindi selezionare **Estensione file include queste parole.**</span><span class="sxs-lookup"><span data-stu-id="2b6f4-111">Under **Apply this rule if**, select **Any attachment**, and then select **file extension includes these words**.</span></span>
1. <span data-ttu-id="2b6f4-112">Nella casella in **specificare parole** o frasi immettere le estensioni di file a cui si desidera applicare la regola, ad esempio le estensioni di file che possono contenere macro.</span><span class="sxs-lookup"><span data-stu-id="2b6f4-112">In the box under **specify words or phrases**, enter the file extensions that you want the rule to be applied to, such as file extensions that can contain macros.</span></span> <span data-ttu-id="2b6f4-113">Usa il simbolo più (+) per aggiungerli uno alla volta.</span><span class="sxs-lookup"><span data-stu-id="2b6f4-113">Use the plus (+) symbol to add them one at a time.</span></span>

    <span data-ttu-id="2b6f4-114">Per ulteriori informazioni sui tipi di file, vedere [Protezione da ransomware.](../admin/security-and-compliance/secure-your-business-data.md#ransomware)</span><span class="sxs-lookup"><span data-stu-id="2b6f4-114">Learn more about file types by reading [Protect against ransomware](../admin/security-and-compliance/secure-your-business-data.md#ransomware).</span></span>

1. <span data-ttu-id="2b6f4-115">Scorrere verso il basso per esaminare l'elenco e quindi scegliere **OK.**</span><span class="sxs-lookup"><span data-stu-id="2b6f4-115">Scroll down to review your list, and then choose **OK**.</span></span>
1. <span data-ttu-id="2b6f4-116">Nella pagina **nuova regola** scegliere **aggiungi condizione** e quindi una condizione in Eseguire le **operazioni seguenti.**</span><span class="sxs-lookup"><span data-stu-id="2b6f4-116">On the **new rule** page, choose **add condition**, and then choose a condition under **Do the following**.</span></span>
1. <span data-ttu-id="2b6f4-117">Sono disponibili molte opzioni tra cui scegliere, ma in questo esempio si sceglie di inviare una notifica al destinatario **con un messaggio.**</span><span class="sxs-lookup"><span data-stu-id="2b6f4-117">You have many rule options to choose from, but in this example we'll choose to **Notify the recipient with a message**.</span></span>
1. <span data-ttu-id="2b6f4-118">Immettere il testo del messaggio per la notifica e quindi scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="2b6f4-118">Enter message text for your notification, and then chose **OK**.</span></span>
1. <span data-ttu-id="2b6f4-119">Facoltativo: nella **pagina** nuova regola scegliere Aggiungi eccezione e immettere eventuali dettagli per le eccezioni alla regola, ad esempio i messaggi provenienti da mittenti attendibili.</span><span class="sxs-lookup"><span data-stu-id="2b6f4-119">Optional: On the **new rule** page, choose **add exception**, and enter any details for exceptions to your rule, such as messages from trusted senders.</span></span>
1. <span data-ttu-id="2b6f4-120">Nella pagina nuova regola scegliere **Salva** ed esaminare le informazioni di riepilogo della regola fornite.</span><span class="sxs-lookup"><span data-stu-id="2b6f4-120">On the new rule page, choose **Save**, and review the rule summary information provided.</span></span>