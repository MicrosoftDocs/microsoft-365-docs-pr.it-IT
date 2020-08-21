---
title: Specificare una cassetta postale per l'invio di messaggi di posta indesiderata e di phishing da un utente
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Gli amministratori possono imparare a configurare una cassetta postale per raccogliere messaggi di posta indesiderata e di phishing segnalati dagli utenti.
ms.openlocfilehash: 76264801820b6a41ee744a8adcc3b3b48a8e9479
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826742"
---
# <a name="specify-a-mailbox-for-user-submissions-of-spam-and-phishing-messages-in-exchange-online"></a><span data-ttu-id="819fa-103">Specificare una cassetta postale per l'invio di messaggi di posta indesiderata e di phishing in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="819fa-103">Specify a mailbox for user submissions of spam and phishing messages in Exchange Online</span></span>

<span data-ttu-id="819fa-104">In Microsoft 365 organizzazioni con cassette postali di Exchange Online, è possibile specificare una cassetta postale per ricevere i messaggi che gli utenti segnalano come dannosi o non dannosi.</span><span class="sxs-lookup"><span data-stu-id="819fa-104">In Microsoft 365 organizations with Exchange Online mailboxes, you can specify a mailbox to receive messages that users report as malicious or not malicious.</span></span> <span data-ttu-id="819fa-105">Quando gli utenti inviano messaggi utilizzando le diverse opzioni per la creazione di report, è possibile utilizzare questa cassetta postale per intercettare i messaggi (solo per l'invio alla cassetta postale personalizzata) oppure per ricevere copie dei messaggi (Invia alla cassetta postale personalizzata e Microsoft).</span><span class="sxs-lookup"><span data-stu-id="819fa-105">When users submit messages using the various reporting options, you can use this mailbox to intercept messages (send to the custom mailbox only) or receive copies of messages (send to the custom mailbox and Microsoft).</span></span> <span data-ttu-id="819fa-106">Questa funzionalità è compatibile con le opzioni di segnalazione dei messaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="819fa-106">This feature works with the following message reporting options:</span></span>

- [<span data-ttu-id="819fa-107">Componente aggiuntivo per i messaggi di report</span><span class="sxs-lookup"><span data-stu-id="819fa-107">The Report Message add-in</span></span>](enable-the-report-message-add-in.md)

- <span data-ttu-id="819fa-108">[Creazione di report incorporati in Outlook sul Web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (in precedenza noto come Outlook Web App)</span><span class="sxs-lookup"><span data-stu-id="819fa-108">[Built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (formerly known as Outlook Web App)</span></span>

- <span data-ttu-id="819fa-109">Reporting incorporato in Outlook per iOS e Android</span><span class="sxs-lookup"><span data-stu-id="819fa-109">Built-in reporting in Outlook for iOS and Android</span></span>

  > [!NOTE]
  > <span data-ttu-id="819fa-110">Se la segnalazione è stata [disabilitata in Outlook sul Web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web), l'abilitazione degli invii degli utenti qui sostituirà tale impostazione e consentirà agli utenti di segnalare di nuovo i messaggi in Outlook sul Web.</span><span class="sxs-lookup"><span data-stu-id="819fa-110">If reporting has been [disabled in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web), enabling user submissions here will override that setting and enable users to report messages in Outlook on the web again.</span></span>

<span data-ttu-id="819fa-111">È inoltre possibile configurare gli strumenti di Reporting dei messaggi di terze parti per inoltrare i messaggi alla cassetta postale specificata.</span><span class="sxs-lookup"><span data-stu-id="819fa-111">You can also configure third-party message reporting tools to forward messages to the mailbox that you specify.</span></span>

<span data-ttu-id="819fa-112">La distribuzione di messaggi segnalati dall'utente a una cassetta postale personalizzata invece che direttamente a Microsoft consente agli amministratori di segnalare selettivamente e manualmente i messaggi a Microsoft tramite l' [invio di amministratore](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="819fa-112">Delivering user reported messages to a custom mailbox instead of directly to Microsoft allows your admins to selectively and manually report messages to Microsoft using [Admin submission](admin-submission.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="819fa-113">Che cosa è necessario sapere prima di iniziare?</span><span class="sxs-lookup"><span data-stu-id="819fa-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="819fa-114">Aprire il Centro sicurezza e conformità in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="819fa-114">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="819fa-115">Per passare direttamente alla pagina degli **invii degli utenti** , utilizzare <https://protection.office.com/userSubmissionsReportMessage> .</span><span class="sxs-lookup"><span data-stu-id="819fa-115">To go directly to the **User submissions** page, use <https://protection.office.com/userSubmissionsReportMessage>.</span></span>

- <span data-ttu-id="819fa-116">È necessario disporre delle autorizzazioni per eseguire le procedure di questo argomento:</span><span class="sxs-lookup"><span data-stu-id="819fa-116">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="819fa-117">Per modificare la configurazione per gli invii degli utenti, è necessario essere membri di uno dei gruppi di ruoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="819fa-117">To modify the configuration for User submissions, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="819fa-118">**Gestione organizzazione** o **Amministratore sicurezza** nel [Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="819fa-118">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="819fa-119">**Gestione organizzazione** o **Gestione igiene** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="819fa-119">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="819fa-120">Per l'accesso in sola lettura agli invii degli utenti, è necessario essere membri di uno dei gruppi di ruoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="819fa-120">For read-only access to User submissions, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="819fa-121">**Lettore sicurezza** nel [Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="819fa-121">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="819fa-122">**Gestione organizzazione in sola lettura** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="819fa-122">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

## <a name="use-the-security--compliance-center-to-configure-the-user-submissions-mailbox"></a><span data-ttu-id="819fa-123">Utilizzare il Centro sicurezza & conformità per configurare la cassetta postale per gli invii degli utenti</span><span class="sxs-lookup"><span data-stu-id="819fa-123">Use the Security & Compliance Center to configure the user submissions mailbox</span></span>

1. <span data-ttu-id="819fa-124">Nel centro sicurezza & conformità, accedere a invii di criteri di **gestione delle minacce** \> **Policy** \> **User submissions**.</span><span class="sxs-lookup"><span data-stu-id="819fa-124">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **User submissions**.</span></span>

2. <span data-ttu-id="819fa-125">Nella pagina **invii utente** che viene visualizzata, selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="819fa-125">In the **User submissions** page that appears, select one of the following options:</span></span>

   <span data-ttu-id="819fa-126">a.</span><span class="sxs-lookup"><span data-stu-id="819fa-126">a.</span></span> <span data-ttu-id="819fa-127">**Abilitare la caratteristica messaggio di report per Outlook (scelta consigliata)**: selezionare questa opzione se si utilizza il componente aggiuntivo per i messaggi di report o la creazione di report incorporati in Outlook sul Web e quindi configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="819fa-127">**Enable the Report Message feature for Outlook (Recommended)**: Select this option if you use the Report Message add-in or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>

      - <span data-ttu-id="819fa-128">**Personalizzare il messaggio di conferma dell'utente finale**: fare clic su questo collegamento.</span><span class="sxs-lookup"><span data-stu-id="819fa-128">**Customize the end-user confirmation message**: Click this link.</span></span> <span data-ttu-id="819fa-129">Nel riquadro a comparsa **Personalizza messaggio di conferma** che viene visualizzata, configurare le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="819fa-129">In the **Customize confirmation message** flyout that appears, configure the following settings:</span></span>

      - <span data-ttu-id="819fa-130">**Prima dell'invio**: nelle caselle del **messaggio di conferma** e del **titolo** immettere il testo descrittivo visualizzato dagli utenti prima di segnalare un messaggio utilizzando il componente aggiuntivo segnala messaggio.</span><span class="sxs-lookup"><span data-stu-id="819fa-130">**Before submission**: In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see before they report a message using the Report Message add-in.</span></span> <span data-ttu-id="819fa-131">È possibile utilizzare la variabile% Type% per includere il tipo di invio (posta indesiderata, non indesiderata, phishing e così via).</span><span class="sxs-lookup"><span data-stu-id="819fa-131">You can use the variable %type% to include the submission type (junk, not junk, phish, etc.).</span></span>

        <span data-ttu-id="819fa-132">Come indicato, se si seleziona un'opzione che consente di inviare i messaggi segnalati a Microsoft, alla notifica viene aggiunto anche il testo seguente:</span><span class="sxs-lookup"><span data-stu-id="819fa-132">As noted, if you select an option that sends the reported messages to Microsoft, the following text is also added to the notification:</span></span>

        > <span data-ttu-id="819fa-133">Il messaggio di posta elettronica verrà inviato come è a Microsoft per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="819fa-133">Your email will be submitted as-is to Microsoft for analysis.</span></span> <span data-ttu-id="819fa-134">Alcuni messaggi di posta elettronica potrebbero contenere informazioni personali o riservate.</span><span class="sxs-lookup"><span data-stu-id="819fa-134">Some emails might contain personal or sensitive information.</span></span>

      - <span data-ttu-id="819fa-135">**Dopo l'invio**: fare clic su ![ Espandi icona ](../../media/scc-expand-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="819fa-135">**After submission**: Click ![Expand icon](../../media/scc-expand-icon.png).</span></span> <span data-ttu-id="819fa-136">Nelle caselle del messaggio **titolo** e di **conferma** , immettere il testo descrittivo visualizzato dagli utenti dopo aver segnalato un messaggio utilizzando il componente aggiuntivo segnala messaggio.</span><span class="sxs-lookup"><span data-stu-id="819fa-136">In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see after they report a message using the Report Message add-in.</span></span> <span data-ttu-id="819fa-137">È possibile utilizzare la variabile% Type% per includere il tipo di invio.</span><span class="sxs-lookup"><span data-stu-id="819fa-137">You can use the variable %type% to include the submission type.</span></span>

      <span data-ttu-id="819fa-138">Al termine, scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="819fa-138">When you're finished, click **Save**.</span></span> <span data-ttu-id="819fa-139">Per cancellare questi valori, fare clic su **Ripristina** di nuovo nella pagina **invii utente** .</span><span class="sxs-lookup"><span data-stu-id="819fa-139">To clear these values, click **Restore** back on the **User submissions** page.</span></span>

      - <span data-ttu-id="819fa-140">**Inviare i messaggi segnalati a**: effettuare una delle selezioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="819fa-140">**Send the reported messages to**: Make one of the following selections:</span></span>

        - <span data-ttu-id="819fa-141">**Microsoft (scelta consigliata)**: la cassetta postale per l'invio degli utenti non viene utilizzata (tutti i messaggi segnalati passano a Microsoft).</span><span class="sxs-lookup"><span data-stu-id="819fa-141">**Microsoft (Recommended)**: The user submissions mailbox isn't used (all reported messages go to Microsoft).</span></span>

        - <span data-ttu-id="819fa-142">**Microsoft e una cassetta postale personalizzata**: nella casella visualizzata, immettere l'indirizzo di posta elettronica di una cassetta postale di Exchange Online esistente.</span><span class="sxs-lookup"><span data-stu-id="819fa-142">**Microsoft and a custom mailbox**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span> <span data-ttu-id="819fa-143">I gruppi di distribuzione non sono consentiti.</span><span class="sxs-lookup"><span data-stu-id="819fa-143">Distribution groups are not allowed.</span></span> <span data-ttu-id="819fa-144">Gli invii degli utenti passeranno sia a Microsoft per l'analisi che alla cassetta postale personalizzata affinché l'amministratore o il team di operazioni di sicurezza analizzi.</span><span class="sxs-lookup"><span data-stu-id="819fa-144">User submissions will go to both Microsoft for analysis and to the custom mailbox for your admin or security operations team to analyze.</span></span>

        - <span data-ttu-id="819fa-145">**Cassetta postale personalizzata**: nella casella visualizzata, immettere l'indirizzo di posta elettronica di una cassetta postale di Exchange Online esistente.</span><span class="sxs-lookup"><span data-stu-id="819fa-145">**Custom mailbox**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span> <span data-ttu-id="819fa-146">I gruppi di distribuzione non sono consentiti.</span><span class="sxs-lookup"><span data-stu-id="819fa-146">Distribution groups are not allowed.</span></span> <span data-ttu-id="819fa-147">Utilizzare questa opzione se si desidera che il messaggio venga utilizzato solo da un amministratore o il team delle operazioni di sicurezza per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="819fa-147">Use this option if you want the message to only go to an admin or the security operations team for analysis first.</span></span> <span data-ttu-id="819fa-148">I messaggi non vengono inviati a Microsoft a meno che l'amministratore non lo inoltri direttamente.</span><span class="sxs-lookup"><span data-stu-id="819fa-148">Messages will not go to Microsoft unless the admin forwards it themselves.</span></span>

        > [!NOTE]
        > <span data-ttu-id="819fa-149">Le organizzazioni governative degli Stati Uniti (GCC, GCC-H e DoD) possono configurare solo la **cassetta postale personalizzata**.</span><span class="sxs-lookup"><span data-stu-id="819fa-149">U.S. Government organizations (GCC, GCC-H, and DoD) can only configure **Custom mailbox**.</span></span> <span data-ttu-id="819fa-150">Le altre due opzioni sono disattivate.</span><span class="sxs-lookup"><span data-stu-id="819fa-150">The other two options are disabled.</span></span> 

      <span data-ttu-id="819fa-151">Al termine, fare clic su **conferma**.</span><span class="sxs-lookup"><span data-stu-id="819fa-151">When you're finished, click **Confirm**.</span></span>

      > [!CAUTION]
      > <span data-ttu-id="819fa-152">Se è stata [disabilitata la segnalazione della posta indesiderata in Outlook sul Web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) utilizzando i criteri cassetta postale di Outlook sul Web, ma si configura una delle impostazioni precedenti per segnalare i messaggi a Microsoft, gli utenti saranno in grado di segnalare i messaggi a Microsoft in Outlook sul Web utilizzando il componente aggiuntivo segnala messaggio.</span><span class="sxs-lookup"><span data-stu-id="819fa-152">If you have [disabled junk email reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) using Outlook on the web mailbox policies, but you configure either of the previous settings to report messages to Microsoft, users will be able to report messages to Microsoft in Outlook on the web using the Report Message add-in.</span></span>

   - <span data-ttu-id="819fa-153">**Disattiva la caratteristica messaggio di report per Outlook**: selezionare questa opzione se si utilizzano gli strumenti di creazione di report di terze parti invece del componente aggiuntivo per i messaggi di report o la creazione di report incorporati in Outlook sul Web e quindi configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="819fa-153">**Disable the Report Message feature for Outlook**: Select this option if you use third-party reporting tools instead of the Report Message add-in or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>

      <span data-ttu-id="819fa-154">Selezionare **Usa questa cassetta postale personalizzata per ricevere invii segnalati dall'utente**.</span><span class="sxs-lookup"><span data-stu-id="819fa-154">Select **Use this custom mailbox to receive user reported submissions**.</span></span> <span data-ttu-id="819fa-155">Nella casella che viene visualizzata, immettere l'indirizzo di posta elettronica di una cassetta postale esistente già in Office 365.</span><span class="sxs-lookup"><span data-stu-id="819fa-155">In the box that appears, enter the email address of an existing mailbox that is already in Office 365.</span></span> <span data-ttu-id="819fa-156">Questa deve essere una cassetta postale esistente in Exchange Online che può ricevere posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="819fa-156">This has to be an existing mailbox in Exchange Online that can receive email.</span></span>

      <span data-ttu-id="819fa-157">Al termine, fare clic su **conferma**.</span><span class="sxs-lookup"><span data-stu-id="819fa-157">When you're finished, click **Confirm**.</span></span>

## <a name="message-submission-format"></a><span data-ttu-id="819fa-158">Formato di invio dei messaggi</span><span class="sxs-lookup"><span data-stu-id="819fa-158">Message submission format</span></span>

<span data-ttu-id="819fa-159">I messaggi inviati alle cassette postali personalizzate devono seguire un formato di posta elettronica di invio specifico.</span><span class="sxs-lookup"><span data-stu-id="819fa-159">Messages sent to custom mailboxes need to follow a specific submission mail format.</span></span> <span data-ttu-id="819fa-160">L'oggetto (titolo della busta) dell'invio deve essere nel formato seguente:</span><span class="sxs-lookup"><span data-stu-id="819fa-160">The Subject (Envelope Title) of the submission should be in this format:</span></span>

`SafetyAPIAction|NetworkMessageId|SenderIp|FromAddress|(Message Subject)`

<span data-ttu-id="819fa-161">Se SafetyAPIAction è uno dei valori integer seguenti:</span><span class="sxs-lookup"><span data-stu-id="819fa-161">were SafetyAPIAction is one of the following integer values:</span></span>

- <span data-ttu-id="819fa-162">1: posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="819fa-162">1: Junk</span></span>
- <span data-ttu-id="819fa-163">2: NotJunk</span><span class="sxs-lookup"><span data-stu-id="819fa-163">2: NotJunk</span></span>
- <span data-ttu-id="819fa-164">3: phishing</span><span class="sxs-lookup"><span data-stu-id="819fa-164">3: Phish</span></span>

<span data-ttu-id="819fa-165">Nell'esempio seguente:</span><span class="sxs-lookup"><span data-stu-id="819fa-165">In the following example:</span></span>

- <span data-ttu-id="819fa-166">Il messaggio è stato segnalato come phishing.</span><span class="sxs-lookup"><span data-stu-id="819fa-166">The message is being reported as Phish.</span></span>
- <span data-ttu-id="819fa-167">L'ID del messaggio di rete è 49871234-6dc6-43e8-ABCD-08d797f20abe.</span><span class="sxs-lookup"><span data-stu-id="819fa-167">The Network Message ID is 49871234-6dc6-43e8-abcd-08d797f20abe.</span></span>
- <span data-ttu-id="819fa-168">L'indirizzo IP del mittente è 167.220.232.101.</span><span class="sxs-lookup"><span data-stu-id="819fa-168">The Sender IP is 167.220.232.101.</span></span>
- <span data-ttu-id="819fa-169">L'indirizzo from è test@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="819fa-169">The From address is test@contoso.com.</span></span>
- <span data-ttu-id="819fa-170">La riga dell'oggetto del messaggio è "test phishing Submission"</span><span class="sxs-lookup"><span data-stu-id="819fa-170">The message's subject line is "test phish submission"</span></span>

`3|49871234-6dc6-43e8-abcd-08d797f20abe|167.220.232.101|test@contoso.com|(test phish submission)`

<span data-ttu-id="819fa-171">I messaggi che non seguono questo formato non verranno visualizzati correttamente nel portale degli invii.</span><span class="sxs-lookup"><span data-stu-id="819fa-171">Messages that do not follow this format will not display properly in the Submissions portal.</span></span>
