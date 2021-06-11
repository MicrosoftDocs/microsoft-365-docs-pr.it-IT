---
title: Revisione amministratore per i messaggi segnalati
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: Admin
ms.topic: how-to
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: Informazioni su come esaminare i messaggi segnalati e inviare commenti e suggerimenti agli utenti.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 217f5ebb1692d68b5dc70988888bf78d4bd36a0c
ms.sourcegitcommit: d0c160e89e17f451199bc4a85699effd2d935213
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/11/2021
ms.locfileid: "52893729"
---
# <a name="admin-review-for-reported-messages"></a><span data-ttu-id="deaa2-103">Revisione amministratore per i messaggi segnalati</span><span class="sxs-lookup"><span data-stu-id="deaa2-103">Admin review for reported messages</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!NOTE]
> <span data-ttu-id="deaa2-104">Le informazioni contenute in questo articolo si riferiscono a un prodotto di anteprima che potrebbe essere sostanzialmente modificato prima che venga rilasciato commercialmente.</span><span class="sxs-lookup"><span data-stu-id="deaa2-104">The information in this article relates to a preview product that may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="deaa2-105">Questo documento viene fornito solo a scopo di valutazione ed esplorazione.</span><span class="sxs-lookup"><span data-stu-id="deaa2-105">This document is provided for evaluation and exploration purposes only.</span></span>

<span data-ttu-id="deaa2-106">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="deaa2-106">**Applies to**</span></span>
- [<span data-ttu-id="deaa2-107">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="deaa2-107">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="deaa2-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="deaa2-108">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="deaa2-109">Nelle Microsoft 365 con cassette postali di Exchange Online e Microsoft Defender per Office 365, gli amministratori possono ora inviare messaggi modello agli utenti finali dopo aver esaminato i messaggi segnalati.</span><span class="sxs-lookup"><span data-stu-id="deaa2-109">In Microsoft 365 organizations with Exchange Online mailboxes and Microsoft Defender for Office 365, admins can now send templated messages back to end users after they review reported messages.</span></span> <span data-ttu-id="deaa2-110">Questo può essere personalizzato per l'organizzazione e in base al verdetto dell'amministratore.</span><span class="sxs-lookup"><span data-stu-id="deaa2-110">This can be customized for your organization and based on your admin's verdict as well.</span></span>

<span data-ttu-id="deaa2-111">Questa funzionalità è progettata per fornire feedback agli utenti, ma non modifica i verdetti dei messaggi nel sistema.</span><span class="sxs-lookup"><span data-stu-id="deaa2-111">This feature is designed to give feedback to your users but does not change the verdicts of messages in the system.</span></span> <span data-ttu-id="deaa2-112">Per consentire a Microsoft di aggiornare e migliorare i filtri, è necessario inviare messaggi per l'analisi tramite [l'invio dell'amministratore.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="deaa2-112">To help Microsoft update and improve its filters, you will need to submit messages for analysis using [Admin submission](admin-submission.md).</span></span>

<span data-ttu-id="deaa2-113">Sarà possibile contrassegnare e notificare agli utenti i risultati della revisione solo se il messaggio è stato segnalato come [falso positivo o falso negativo.](report-false-positives-and-false-negatives.md)</span><span class="sxs-lookup"><span data-stu-id="deaa2-113">You will only be able to mark and notify users of review results if the message was reported as a [false positives or false negatives](report-false-positives-and-false-negatives.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="deaa2-114">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="deaa2-114">What do you need to know before you begin?</span></span>

- <span data-ttu-id="deaa2-115">Aprire il portale Microsoft 365 Defender all'indirizzo <https://security.microsoft.com/> .</span><span class="sxs-lookup"><span data-stu-id="deaa2-115">You open the Microsoft 365 Defender portal at <https://security.microsoft.com/>.</span></span> <span data-ttu-id="deaa2-116">Per passare direttamente alla **pagina Invii,** usa <https://security.microsoft.com/reportsubmission> .</span><span class="sxs-lookup"><span data-stu-id="deaa2-116">To go directly to the **Submissions** page, use <https://security.microsoft.com/reportsubmission>.</span></span>

- <span data-ttu-id="deaa2-117">Per modificare la configurazione per gli invii di utenti, è necessario essere membri di uno dei gruppi di ruoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="deaa2-117">To modify the configuration for User submissions, you need to be a member of one of the following role groups:</span></span>
  - <span data-ttu-id="deaa2-118">Gestione dell'organizzazione o amministratore della sicurezza [nel portale Microsoft 365 Defender](permissions-microsoft-365-security-center.md).</span><span class="sxs-lookup"><span data-stu-id="deaa2-118">Organization Management or Security Administrator in the [Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md).</span></span>
  - <span data-ttu-id="deaa2-119">Gestione organizzazione in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="deaa2-119">Organization Management in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="deaa2-120">Sarà inoltre necessario accedere a Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="deaa2-120">You'll also need access to Exchange Online PowerShell.</span></span> <span data-ttu-id="deaa2-121">Se l'account che si sta tentando di usare non ha accesso Exchange Online PowerShell, verrà visualizzato un errore che indica Specificare un indirizzo di posta elettronica nel *dominio.*</span><span class="sxs-lookup"><span data-stu-id="deaa2-121">If the account that you're trying to use doesn't have access to Exchange Online PowerShell, you'll receive an error that says *Specify an email address in your domain*.</span></span> <span data-ttu-id="deaa2-122">Per ulteriori informazioni sull'abilitazione o disabilitazione dell'accesso Exchange Online PowerShell, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="deaa2-122">For more information about enabling or disabling access to Exchange Online PowerShell, see the following topics:</span></span>
  - [<span data-ttu-id="deaa2-123">Abilitare o disabilitare l'accesso Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="deaa2-123">Enable or disable access to Exchange Online PowerShell</span></span>](/powershell/exchange/disable-access-to-exchange-online-powershell)
  - [<span data-ttu-id="deaa2-124">Regole di Accesso client in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="deaa2-124">Client Access Rules in Exchange Online</span></span>](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)

## <a name="configure-the-messages-used-to-notify-users"></a><span data-ttu-id="deaa2-125">Configurare i messaggi utilizzati per inviare notifiche agli utenti</span><span class="sxs-lookup"><span data-stu-id="deaa2-125">Configure the messages used to notify users</span></span>

1. <span data-ttu-id="deaa2-126">Nel portale di Microsoft 365 Defender, andare a **Email & collaboration** Policies & \> **Threat** \> **policies** \> **Others** section User \> **reported message settings**.</span><span class="sxs-lookup"><span data-stu-id="deaa2-126">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Policies & rules** \> **Threat policies** \> **Others** section \> **User reported message settings**.</span></span>

2. <span data-ttu-id="deaa2-127">Nella  pagina Invii utente, se si desidera specificare il nome visualizzato del mittente, selezionare la casella specificare l'indirizzo di posta elettronica di **Office 365** da utilizzare come mittente nella sezione **Notifiche** di posta elettronica per i risultati della revisione dell'amministratore e immettere il nome che si desidera utilizzare.</span><span class="sxs-lookup"><span data-stu-id="deaa2-127">On the **User submissions** page, if you want to specify the sender display name, check the box for **Specify Office 365 email address to use as sender** under the **Email notifications for admin review results** section, and enter in the name you wish to use.</span></span> <span data-ttu-id="deaa2-128">Questo è l'indirizzo di posta elettronica che sarà visibile Outlook e a cui verranno indirizzate le risposte.</span><span class="sxs-lookup"><span data-stu-id="deaa2-128">This is the email address that will be visible in Outlook and where replies will go to.</span></span>

3. <span data-ttu-id="deaa2-129">Se si desidera personalizzare uno dei modelli, fare clic su **Personalizza notifica tramite posta elettronica.**</span><span class="sxs-lookup"><span data-stu-id="deaa2-129">If you want to customize any of the templates, click **Customize email notification**.</span></span> <span data-ttu-id="deaa2-130">In questo riquadro a comparsa sarà possibile personalizzare solo gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="deaa2-130">In this flyout, you will be able to customize only the following:</span></span>
    - <span data-ttu-id="deaa2-131">Phishing</span><span class="sxs-lookup"><span data-stu-id="deaa2-131">Phishing</span></span>
    - <span data-ttu-id="deaa2-132">Posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="deaa2-132">Junk</span></span>
    - <span data-ttu-id="deaa2-133">Nessuna minaccia trovata</span><span class="sxs-lookup"><span data-stu-id="deaa2-133">No threats found</span></span>
    - <span data-ttu-id="deaa2-134">Formazione sulla sensibilizzazione</span><span class="sxs-lookup"><span data-stu-id="deaa2-134">Awareness training</span></span>
    - <span data-ttu-id="deaa2-135">Piè di pagina</span><span class="sxs-lookup"><span data-stu-id="deaa2-135">Footer</span></span>

4. <span data-ttu-id="deaa2-136">Al termine, scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="deaa2-136">When you're finished, click **Save**.</span></span> <span data-ttu-id="deaa2-137">Per cancellare questi valori, fare clic **su Ignora** nella pagina Invii utente.</span><span class="sxs-lookup"><span data-stu-id="deaa2-137">To clear these values, click **Discard** on the User submissions page.</span></span>
