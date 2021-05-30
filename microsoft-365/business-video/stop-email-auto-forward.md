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
description: Scopri come interrompere l'inoltro automatico dei messaggi di posta elettronica creando una regola del flusso di posta per evitare il furto di informazioni proprietarie.
ms.openlocfilehash: 82e4c80b0edc501889e0fc4dc28f1ec1ad703568
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706475"
---
# <a name="stop-email-auto-forward"></a><span data-ttu-id="270e8-103">Arrestare l'inoltro automatico della posta elettronica</span><span class="sxs-lookup"><span data-stu-id="270e8-103">Stop email auto-forward</span></span>

## <a name="watch-stop-auto-forwarding-emails"></a><span data-ttu-id="270e8-104">Watch: Stop auto-forwarding emails</span><span class="sxs-lookup"><span data-stu-id="270e8-104">Watch: Stop auto-forwarding emails</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2W6kS?autoplay=false]

<span data-ttu-id="270e8-105">Se un pirata informatico ottiene l'accesso alla cassetta postale di un utente, può inoltrare automaticamente la posta elettronica dell'utente a un indirizzo esterno e rubare informazioni proprietarie.</span><span class="sxs-lookup"><span data-stu-id="270e8-105">If a hacker gains access to a user's mailbox, they can auto-forward the user's email to an outside address and steal proprietary information.</span></span> <span data-ttu-id="270e8-106">È possibile interrompere questa operazione creando una regola del flusso di posta.</span><span class="sxs-lookup"><span data-stu-id="270e8-106">You can stop this by creating a mail flow rule.</span></span>

## <a name="try-it"></a><span data-ttu-id="270e8-107">Perché non provarlo?</span><span class="sxs-lookup"><span data-stu-id="270e8-107">Try it!</span></span>

1. <span data-ttu-id="270e8-108">Nell'Microsoft 365 di amministrazione selezionare **Exchange ,** flusso di posta  **e** nella scheda regole selezionare il segno più e scegliere crea una nuova **regola**.</span><span class="sxs-lookup"><span data-stu-id="270e8-108">From the Microsoft 365 admin center, select **Exchange**, **mail flow**, and on the **rules** tab, select the plus sign and choose **create a new rule**.</span></span>
1. <span data-ttu-id="270e8-109">Selezionare **Altre opzioni.**</span><span class="sxs-lookup"><span data-stu-id="270e8-109">Select **More options**.</span></span> <span data-ttu-id="270e8-110">Assegnare un nome alla nuova regola.</span><span class="sxs-lookup"><span data-stu-id="270e8-110">Name your new rule.</span></span>
1. <span data-ttu-id="270e8-111">Aprire quindi l'elenco a discesa per **applicare questa regola se**, selezionare **il** mittente e quindi è **interno esterno.**</span><span class="sxs-lookup"><span data-stu-id="270e8-111">Then open the drop-down for **apply this rule if**, select **the sender**, and then **is external internal**.</span></span>
1. <span data-ttu-id="270e8-112">Selezionare **All'interno dell'organizzazione** e quindi **OK.**</span><span class="sxs-lookup"><span data-stu-id="270e8-112">Select **Inside the organization**, and then **OK**.</span></span>
1. <span data-ttu-id="270e8-113">Scegliere **aggiungi condizione,** aprire l'elenco a discesa, selezionare **Le proprietà del messaggio,** **quindi includere il tipo di messaggio**.</span><span class="sxs-lookup"><span data-stu-id="270e8-113">Choose **add condition**, open the drop-down, select **The message properties**, then **include the message type**.</span></span>
1. <span data-ttu-id="270e8-114">Aprire **l'elenco a** discesa Seleziona tipo di messaggio, scegliere **Inoltro automatico,** quindi **OK.**</span><span class="sxs-lookup"><span data-stu-id="270e8-114">Open the **select message type** drop-down, choose **Auto-forward**, then **OK**.</span></span>
1. <span data-ttu-id="270e8-115">Aprire **l'elenco** a discesa Eseguire le operazioni seguenti, selezionare **Blocca il messaggio,** quindi **rifiutare il messaggio e includere una spiegazione.**</span><span class="sxs-lookup"><span data-stu-id="270e8-115">Open the **Do the following** drop-down, select **Block the message**, then **reject the message and include an explanation**.</span></span>
1. <span data-ttu-id="270e8-116">Immetti il testo del messaggio per la spiegazione, quindi seleziona **OK.**</span><span class="sxs-lookup"><span data-stu-id="270e8-116">Enter the message text for your explanation, then select **OK**.</span></span>
1. <span data-ttu-id="270e8-117">Scorrere verso il basso e selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="270e8-117">Scroll to the bottom and select **Save**.</span></span>

    <span data-ttu-id="270e8-118">La regola è stata creata e gli hacker non saranno più in grado di inoltrare automaticamente i messaggi.</span><span class="sxs-lookup"><span data-stu-id="270e8-118">Your rule has been created, and hackers will no longer be able to auto-forward messages.</span></span>

## <a name="related-content"></a><span data-ttu-id="270e8-119">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="270e8-119">Related content</span></span>

<span data-ttu-id="270e8-120">[Aggiungere un altro alias di posta elettronica per un utente](../admin/email/add-another-email-alias-for-a-user.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="270e8-120">[Add another email alias for a user](../admin/email/add-another-email-alias-for-a-user.md) (article)</span></span>\
<span data-ttu-id="270e8-121">[Configurare l'inoltro della posta elettronica in Microsoft 365](../admin/email/configure-email-forwarding.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="270e8-121">[Configure email forwarding in Microsoft 365](../admin/email/configure-email-forwarding.md) (article)</span></span>\
<span data-ttu-id="270e8-122">[Trovare e risolvere i problemi di recapito della posta elettronica come Office 365 per le aziende](/exchange/troubleshoot/email-delivery/email-delivery-issues) (articolo)</span><span class="sxs-lookup"><span data-stu-id="270e8-122">[Find and fix email delivery issues as an Office 365 for business admin](/exchange/troubleshoot/email-delivery/email-delivery-issues) (article)</span></span>