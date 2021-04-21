---
title: Interrompere l'inoltro automatico dei messaggi di posta elettronica
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
ms.openlocfilehash: f8bd599c7c8bca8d4789188acbcd3574b7473dcb
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/20/2021
ms.locfileid: "51903683"
---
# <a name="stop-email-auto-forward"></a><span data-ttu-id="55693-103">Arrestare l'inoltro automatico della posta elettronica</span><span class="sxs-lookup"><span data-stu-id="55693-103">Stop email auto-forward</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2W6kS?autoplay=false]

<span data-ttu-id="55693-104">Se un pirata informatico ottiene l'accesso alla cassetta postale di un utente, può inoltrare automaticamente la posta elettronica dell'utente a un indirizzo esterno e rubare informazioni proprietarie.</span><span class="sxs-lookup"><span data-stu-id="55693-104">If a hacker gains access to a user's mailbox, they can auto-forward the user's email to an outside address and steal proprietary information.</span></span> <span data-ttu-id="55693-105">È possibile interrompere questa operazione creando una regola del flusso di posta.</span><span class="sxs-lookup"><span data-stu-id="55693-105">You can stop this by creating a mail flow rule.</span></span>

## <a name="try-it"></a><span data-ttu-id="55693-106">Perché non provarlo?</span><span class="sxs-lookup"><span data-stu-id="55693-106">Try it!</span></span>

1. <span data-ttu-id="55693-107">Nell'interfaccia di amministrazione di Microsoft 365 selezionare  **Exchange,** flusso di posta **e** nella scheda regole selezionare il segno più e scegliere crea una **nuova regola.**</span><span class="sxs-lookup"><span data-stu-id="55693-107">From the Microsoft 365 admin center, select **Exchange**, **mail flow**, and on the **rules** tab, select the plus sign and choose **create a new rule**.</span></span>
1. <span data-ttu-id="55693-108">Selezionare **Altre opzioni.**</span><span class="sxs-lookup"><span data-stu-id="55693-108">Select **More options**.</span></span> <span data-ttu-id="55693-109">Assegnare un nome alla nuova regola.</span><span class="sxs-lookup"><span data-stu-id="55693-109">Name your new rule.</span></span>
1. <span data-ttu-id="55693-110">Aprire quindi l'elenco a discesa per **applicare questa regola se**, selezionare **il** mittente e quindi è **interno esterno.**</span><span class="sxs-lookup"><span data-stu-id="55693-110">Then open the drop-down for **apply this rule if**, select **the sender**, and then **is external internal**.</span></span>
1. <span data-ttu-id="55693-111">Selezionare **All'interno dell'organizzazione** e quindi **OK.**</span><span class="sxs-lookup"><span data-stu-id="55693-111">Select **Inside the organization**, and then **OK**.</span></span>
1. <span data-ttu-id="55693-112">Scegliere **aggiungi condizione,** aprire l'elenco a discesa, selezionare **Le proprietà del messaggio,** **quindi includere il tipo di messaggio**.</span><span class="sxs-lookup"><span data-stu-id="55693-112">Choose **add condition**, open the drop-down, select **The message properties**, then **include the message type**.</span></span>
1. <span data-ttu-id="55693-113">Aprire **l'elenco a** discesa Seleziona tipo di messaggio, scegliere **Inoltro automatico,** quindi **OK.**</span><span class="sxs-lookup"><span data-stu-id="55693-113">Open the **select message type** drop-down, choose **Auto-forward**, then **OK**.</span></span>
1. <span data-ttu-id="55693-114">Aprire **l'elenco** a discesa Eseguire le operazioni seguenti, selezionare **Blocca il messaggio,** quindi **rifiutare il messaggio e includere una spiegazione.**</span><span class="sxs-lookup"><span data-stu-id="55693-114">Open the **Do the following** drop-down, select **Block the message**, then **reject the message and include an explanation**.</span></span>
1. <span data-ttu-id="55693-115">Immetti il testo del messaggio per la spiegazione, quindi seleziona **OK.**</span><span class="sxs-lookup"><span data-stu-id="55693-115">Enter the message text for your explanation, then select **OK**.</span></span>
1. <span data-ttu-id="55693-116">Scorrere verso il basso e selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="55693-116">Scroll to the bottom and select **Save**.</span></span>

    <span data-ttu-id="55693-117">La regola è stata creata e gli hacker non saranno più in grado di inoltrare automaticamente i messaggi.</span><span class="sxs-lookup"><span data-stu-id="55693-117">Your rule has been created, and hackers will no longer be able to auto-forward messages.</span></span>

## <a name="related-content"></a><span data-ttu-id="55693-118">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="55693-118">Related content</span></span>

<span data-ttu-id="55693-119">[Aggiungere un altro alias](https://docs.microsoft.com/microsoft-365/admin/email/add-another-email-alias-for-a-user) di posta elettronica per un utente (articolo) Configurare l'inoltro della posta [elettronica in Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/email/configure-email-forwarding) (articolo) Trovare e risolvere i problemi di recapito della posta elettronica come amministratore di [Office 365 per le](https://docs.microsoft.com/exchange/troubleshoot/email-delivery/email-delivery-issues) aziende (articolo)</span><span class="sxs-lookup"><span data-stu-id="55693-119">[Add another email alias for a user](https://docs.microsoft.com/microsoft-365/admin/email/add-another-email-alias-for-a-user) (article) [Configure email forwarding in Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/email/configure-email-forwarding) (article) [Find and fix email delivery issues as an Office 365 for business admin](https://docs.microsoft.com/exchange/troubleshoot/email-delivery/email-delivery-issues) (article)</span></span>