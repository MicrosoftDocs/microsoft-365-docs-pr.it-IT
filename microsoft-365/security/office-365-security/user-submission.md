---
title: Specificare una cassetta postale per l'invio di messaggi di posta indesiderata e di phishing da un utente
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Gli amministratori possono imparare a configurare una cassetta postale per raccogliere messaggi di posta indesiderata e di phishing segnalati dagli utenti.
ms.openlocfilehash: a3a175c3815c6750086526ec92d097fb7cbcefa3
ms.sourcegitcommit: d929fa32fc2dfb0749fa2420eddbc2251d8489dc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2020
ms.locfileid: "43922664"
---
# <a name="specify-a-mailbox-for-user-submissions-of-spam-and-phishing-messages-in-office-365"></a><span data-ttu-id="c2564-103">Specificare una cassetta postale per l'invio di messaggi di posta indesiderata e di phishing in Office 365</span><span class="sxs-lookup"><span data-stu-id="c2564-103">Specify a mailbox for user submissions of spam and phishing messages in Office 365</span></span>

<span data-ttu-id="c2564-104">Nelle organizzazioni di Office 365 con cassette postali di Exchange Online, è possibile specificare una cassetta postale per ricevere i messaggi che gli utenti segnalano come dannosi o non dannosi.</span><span class="sxs-lookup"><span data-stu-id="c2564-104">In Office 365 organizations with Exchange Online mailboxes, you can specify a mailbox to receive messages that users report as malicious or not malicious.</span></span> <span data-ttu-id="c2564-105">Quando gli utenti inviano messaggi utilizzando le diverse opzioni per la creazione di report, è possibile utilizzare questa cassetta postale per intercettare i messaggi (solo per l'invio alla cassetta postale personalizzata) oppure per ricevere copie dei messaggi (Invia alla cassetta postale personalizzata e Microsoft).</span><span class="sxs-lookup"><span data-stu-id="c2564-105">When users submit messages using the various reporting options, you can use this mailbox to intercept messages (send to the custom mailbox only) or receive copies of messages (send to the custom mailbox and Microsoft).</span></span> <span data-ttu-id="c2564-106">Questa funzionalità è compatibile con le opzioni di segnalazione dei messaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="c2564-106">This feature works with the following message reporting options:</span></span>

- [<span data-ttu-id="c2564-107">Componente aggiuntivo per i messaggi di report</span><span class="sxs-lookup"><span data-stu-id="c2564-107">The Report Message add-in</span></span>](enable-the-report-message-add-in.md)

- <span data-ttu-id="c2564-108">[Creazione di report incorporati in Outlook sul Web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (in precedenza noto come Outlook Web App)</span><span class="sxs-lookup"><span data-stu-id="c2564-108">[Built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (formerly known as Outlook Web App)</span></span>

<span data-ttu-id="c2564-109">È inoltre possibile configurare gli strumenti di Reporting dei messaggi di terze parti per inoltrare i messaggi alla cassetta postale specificata.</span><span class="sxs-lookup"><span data-stu-id="c2564-109">You can also configure third-party message reporting tools to forward messages to the mailbox that you specify.</span></span>

<span data-ttu-id="c2564-110">La distribuzione di messaggi segnalati dall'utente a una cassetta postale personalizzata invece che direttamente a Microsoft consente agli amministratori di segnalare selettivamente e manualmente i messaggi a Microsoft tramite l' [invio di amministratore](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="c2564-110">Delivering user reported messages to a custom mailbox instead of directly to Microsoft allows your admins to selectively and manually report messages to Microsoft using [Admin submission](admin-submission.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="c2564-111">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="c2564-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="c2564-112">Aprire il Centro sicurezza e conformità in<https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="c2564-112">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="c2564-113">Per passare direttamente alla pagina degli **invii degli utenti** , utilizzare <https://protection.office.com/userSubmissionsReportMessage>.</span><span class="sxs-lookup"><span data-stu-id="c2564-113">To go directly to the **User submissions** page, use <https://protection.office.com/userSubmissionsReportMessage>.</span></span>

- <span data-ttu-id="c2564-114">Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="c2564-114">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="c2564-115">Per connettersi a PowerShell per Exchange Online Protection autonomo, vedere [Connettersi a PowerShell per Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="c2564-115">To connect to standalone Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="c2564-116">È necessario disporre delle autorizzazioni prima di poter eseguire queste procedure.</span><span class="sxs-lookup"><span data-stu-id="c2564-116">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="c2564-117">Per configurare la cassetta postale per gli invii degli utenti, è necessario essere membri dei gruppi di ruoli **Gestione organizzazione** o **amministratore sicurezza** .</span><span class="sxs-lookup"><span data-stu-id="c2564-117">To configure the mailbox for user submissions, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="c2564-118">Per altre informazioni sui gruppi di ruoli nel Centro sicurezza e conformità, vedere [Autorizzazioni nel Centro sicurezza e conformità di Office 365](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="c2564-118">For more information about role groups in the Security & Compliance Center, see [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="use-the-security--compliance-center-to-configure-the-user-submissions-mailbox"></a><span data-ttu-id="c2564-119">Utilizzare il Centro sicurezza & conformità per configurare la cassetta postale per gli invii degli utenti</span><span class="sxs-lookup"><span data-stu-id="c2564-119">Use the Security & Compliance Center to configure the user submissions mailbox</span></span>

1. <span data-ttu-id="c2564-120">Nel centro sicurezza & conformità, accedere a **invii**di **criteri** \> di **gestione** \> delle minacce.</span><span class="sxs-lookup"><span data-stu-id="c2564-120">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **User submissions**.</span></span>

2. <span data-ttu-id="c2564-121">Nella pagina **invii utente** che viene visualizzata, selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c2564-121">In the **User submissions** page that appears, select one of the following options:</span></span>

   - <span data-ttu-id="c2564-122">**Abilitare la caratteristica messaggio di report per Outlook (scelta consigliata)**: selezionare questa opzione se si utilizza il componente aggiuntivo per i messaggi di report o la creazione di report incorporati in Outlook sul Web e quindi configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c2564-122">**Enable the Report Message feature for Outlook (Recommended)**: Select this option if you use the Report Message add-in or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>

     - <span data-ttu-id="c2564-123">**Personalizzare il messaggio di conferma dell'utente finale**: fare clic su questo collegamento.</span><span class="sxs-lookup"><span data-stu-id="c2564-123">**Customize the end-user confirmation message**: Click this link.</span></span> <span data-ttu-id="c2564-124">Nel riquadro a comparsa **Personalizza messaggio di conferma** che viene visualizzata, configurare le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="c2564-124">In the **Customize confirmation message** flyout that appears, configure the following settings:</span></span>

       - <span data-ttu-id="c2564-125">**Prima dell'invio**: nelle caselle del **messaggio di conferma** e del **titolo** immettere il testo descrittivo visualizzato dagli utenti prima di segnalare un messaggio utilizzando il componente aggiuntivo segnala messaggio.</span><span class="sxs-lookup"><span data-stu-id="c2564-125">**Before submission**: In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see before they report a message using the Report Message add-in.</span></span> <span data-ttu-id="c2564-126">È possibile utilizzare la variabile% Type% per includere il tipo di invio (posta indesiderata, non indesiderata, phishing e così via).</span><span class="sxs-lookup"><span data-stu-id="c2564-126">You can use the variable %type% to include the submission type (junk, not junk, phish, etc.).</span></span>

         <span data-ttu-id="c2564-127">Come indicato, anche il testo seguente viene aggiunto alla notifica:</span><span class="sxs-lookup"><span data-stu-id="c2564-127">As noted, the following text is also added to the notification:</span></span>

         > <span data-ttu-id="c2564-128">Il messaggio di posta elettronica verrà inviato come è a Microsoft per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="c2564-128">Your email will be submitted as-is to Microsoft for analysis.</span></span> <span data-ttu-id="c2564-129">Alcuni messaggi di posta elettronica potrebbero contenere informazioni personali o riservate.</span><span class="sxs-lookup"><span data-stu-id="c2564-129">Some emails might contain personal or sensitive information.</span></span>

       - <span data-ttu-id="c2564-130">**Dopo l'invio**: ![fare clic](../../media/scc-expand-icon.png)su Espandi icona.</span><span class="sxs-lookup"><span data-stu-id="c2564-130">**After submission**: Click ![Expand icon](../../media/scc-expand-icon.png).</span></span> <span data-ttu-id="c2564-131">Nelle caselle del messaggio **titolo** e di **conferma** , immettere il testo descrittivo visualizzato dagli utenti dopo aver segnalato un messaggio utilizzando il componente aggiuntivo segnala messaggio.</span><span class="sxs-lookup"><span data-stu-id="c2564-131">In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see after they report a message using the Report Message add-in.</span></span> <span data-ttu-id="c2564-132">È possibile utilizzare la variabile% Type% per includere il tipo di invio.</span><span class="sxs-lookup"><span data-stu-id="c2564-132">You can use the variable %type% to include the submission type.</span></span>

      <span data-ttu-id="c2564-133">Al termine, scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="c2564-133">When you're finished, click **Save**.</span></span> <span data-ttu-id="c2564-134">Per cancellare questi valori, fare clic su **Ripristina** di nuovo nella pagina **invii utente** .</span><span class="sxs-lookup"><span data-stu-id="c2564-134">To clear these values, click **Restore** back on the **User submissions** page.</span></span>

   - <span data-ttu-id="c2564-135">**Inviare i messaggi segnalati a**: effettuare una delle selezioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c2564-135">**Send the reported messages to**: Make one of the following selections:</span></span>

     - <span data-ttu-id="c2564-136">**Microsoft (scelta consigliata)**: la cassetta postale per l'invio degli utenti non viene utilizzata (tutti i messaggi segnalati passano a Microsoft).</span><span class="sxs-lookup"><span data-stu-id="c2564-136">**Microsoft (Recommended)**: The user submissions mailbox isn't used (all reported messages go to Microsoft).</span></span>

     - <span data-ttu-id="c2564-137">**Microsoft e una cassetta postale personalizzata**: nella casella visualizzata, immettere l'indirizzo di posta elettronica di una cassetta postale di Exchange Online esistente.</span><span class="sxs-lookup"><span data-stu-id="c2564-137">**Microsoft and a custom mailbox**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span>

     - <span data-ttu-id="c2564-138">**Cassetta postale personalizzata**: nella casella visualizzata, immettere l'indirizzo di posta elettronica di una cassetta postale di Exchange Online esistente.</span><span class="sxs-lookup"><span data-stu-id="c2564-138">**Custom mailbox**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span>

     <span data-ttu-id="c2564-139">Al termine, fare clic su **conferma**.</span><span class="sxs-lookup"><span data-stu-id="c2564-139">When you're finished, click **Confirm**.</span></span>

     ![Inviare messaggi segnalati a Microsoft e a una cassetta postale personalizzata](../../media/user-submission-enable-outlook-report-message.png)

   - <span data-ttu-id="c2564-141">**Disattiva la caratteristica messaggio di report per Outlook**: selezionare questa opzione se si utilizzano gli strumenti di creazione di report di terze parti invece del componente aggiuntivo per i messaggi di report o la creazione di report incorporati in Outlook sul Web e quindi configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c2564-141">**Disable the Report Message feature for Outlook**: Select this option if you use third-party reporting tools instead of the Report Message add-in or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>

     <span data-ttu-id="c2564-142">Selezionare **Usa questa cassetta postale personalizzata per ricevere invii segnalati dall'utente**.</span><span class="sxs-lookup"><span data-stu-id="c2564-142">Select **Use this custom mailbox to receive user reported submissions**.</span></span> <span data-ttu-id="c2564-143">Nella casella che viene visualizzata, immettere l'indirizzo di posta elettronica di una cassetta postale esistente o l'indirizzo di posta elettronica della cassetta postale che si desidera creare.</span><span class="sxs-lookup"><span data-stu-id="c2564-143">In the box that appears, enter the email address of an existing mailbox, or the email address of the mailbox that you want to create.</span></span>

     <span data-ttu-id="c2564-144">Al termine, fare clic su **conferma**.</span><span class="sxs-lookup"><span data-stu-id="c2564-144">When you're finished, click **Confirm**.</span></span>

     ![Inviare messaggi segnalati a una cassetta postale personalizzata utilizzando strumenti di terze parti](../../media/user-submission-disable-outlook-report-message.png)
