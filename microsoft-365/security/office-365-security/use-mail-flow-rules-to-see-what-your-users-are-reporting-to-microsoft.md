---
title: Utilizzare le regole del flusso di posta elettronica per vedere quali utenti inviano segnalazioni a Microsoft
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8401f520-8e7c-467b-9e06-4a9fdb2ba548
ms.collection:
- M365-security-compliance
description: È possibile creare una regola del flusso di posta di Exchange per impedire agli utenti di inviare messaggi di posta elettronica a Microsoft per l'analisi e utilizzarli nei propri processi di sicurezza
ms.openlocfilehash: 16075605892bcb6d7b99269a64c9c6acd0d3254e
ms.sourcegitcommit: cbf117a4cd92a907115c9f10752f3c557361e586
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/10/2019
ms.locfileid: "37441163"
---
# <a name="use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft"></a><span data-ttu-id="44f4f-103">Usare le regole del flusso di posta per vedere quali segnalazioni gli utenti inviano a Microsoft</span><span class="sxs-lookup"><span data-stu-id="44f4f-103">Use mail flow rules to see what your users are reporting to Microsoft</span></span>

<span data-ttu-id="44f4f-104">Sono disponibili differenti modalità per inviare messaggi falsi positivi e falsi negativi a Microsoft per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="44f4f-104">There are multiple ways you can send false positive and false negative messages to Microsoft for analysis.</span></span> <span data-ttu-id="44f4f-105">Come amministratore, è possibile utilizzare le regole del flusso di posta elettronica per vedere quali utenti inviano segnalazioni a Microsoft su posta indesiderata, non indesiderata e tentativi di phishing.</span><span class="sxs-lookup"><span data-stu-id="44f4f-105">As an administrator, you can use mail flow rules to see what your users are reporting to Microsoft as spam, non-spam, and phishing scams.</span></span> <span data-ttu-id="44f4f-106">Per ulteriori informazioni, vedere [Invio di messaggi di posta indesiderata e non e tentativi di phishing a Microsoft per l'analisi](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md).</span><span class="sxs-lookup"><span data-stu-id="44f4f-106">For more information, see [Submit spam, non-spam, and phishing scam messages to Microsoft for analysis](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md).</span></span> <span data-ttu-id="44f4f-107">Al contrario, è possibile creare una regola del flusso di posta di Exchange (nota anche come regola di trasporto) per impedire agli utenti di inviare messaggi di posta elettronica a Microsoft per l'analisi e utilizzarli nei propri processi di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="44f4f-107">Conversely, you can create an Exchange mail flow rule (also known as a transport rule) to prevent your users from sending email messages to Microsoft for analysis and use them in your own security processes.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="44f4f-108">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="44f4f-108">What do you need to know before you begin?</span></span>

<span data-ttu-id="44f4f-109">Tempo stimato per il completamento: 5 minuti</span><span class="sxs-lookup"><span data-stu-id="44f4f-109">Estimated time to complete: 5 minutes</span></span>

<span data-ttu-id="44f4f-110">Per eseguire queste procedure, è necessario disporre delle autorizzazioni appropriate.</span><span class="sxs-lookup"><span data-stu-id="44f4f-110">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="44f4f-111">Per sapere quali autorizzazioni sono necessarie, vedere la voce "regole del flusso di posta" nell'argomento [criteri di messaggistica e autorizzazioni di conformità](http://technet.microsoft.com/library/ec4d3b9f-b85a-4cb9-95f5-6fc149c3899b.aspx) e "criteri cassetta postale di Outlook sul Web" nell'argomento [autorizzazioni per client e dispositivi mobili](http://technet.microsoft.com/library/57eca42a-5a7f-4c65-89f0-7a84f2dbea19.aspx) .</span><span class="sxs-lookup"><span data-stu-id="44f4f-111">To see what permissions you need, see the "Mail flow rules" entry in the [Messaging policy and compliance permissions](http://technet.microsoft.com/library/ec4d3b9f-b85a-4cb9-95f5-6fc149c3899b.aspx) topic and the "Outlook on the web mailbox policies" entry in the [Clients and mobile devices permissions](http://technet.microsoft.com/library/57eca42a-5a7f-4c65-89f0-7a84f2dbea19.aspx) topic.</span></span>

<span data-ttu-id="44f4f-112">Per informazioni sui tasti di scelta rapida che possono essere applicati alle procedure descritte in questo argomento, vedere tasti [di scelta rapida per l'interfaccia di amministrazione di Exchange in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span><span class="sxs-lookup"><span data-stu-id="44f4f-112">For information about keyboard shortcuts that may apply to the procedures in this topic, see [Keyboard shortcuts for the Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).</span></span>

## <a name="use-the-eac-to-create-a-mail-flow-rule-to-view-users-manual-junk-phishing-and-not-junk-reports"></a><span data-ttu-id="44f4f-113">Utilizzare l'interfaccia di amministrazione di Exchange per creare una regola del flusso di posta per visualizzare report manuali dell'utente su posta indesiderata, phishing e posta non indesiderata.</span><span class="sxs-lookup"><span data-stu-id="44f4f-113">Use the EAC to create a mail flow rule to view users' manual junk, phishing, and not junk reports</span></span>

1. <span data-ttu-id="44f4f-114">Nell'interfaccia di amministrazione di Exchange, accedere a **Flusso di posta** \> **Regole**.</span><span class="sxs-lookup"><span data-stu-id="44f4f-114">In the EAC, navigate to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="44f4f-115">Fare clic su ![Icona Aggiungi](../media/ITPro-EAC-AddIcon.gif) e selezionare **Creare una nuova regola**.</span><span class="sxs-lookup"><span data-stu-id="44f4f-115">Click ![Add Icon](../media/ITPro-EAC-AddIcon.gif) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="44f4f-116">Assegnare un nome alla regola, quindi fare clic su **Altre opzioni**.</span><span class="sxs-lookup"><span data-stu-id="44f4f-116">Give the rule a name and then click **More options**.</span></span>

4. <span data-ttu-id="44f4f-117">In **Applica questa regola se**, selezionare **Il destinatario** e scegliere **l'indirizzo include una di queste parole**.</span><span class="sxs-lookup"><span data-stu-id="44f4f-117">Under **Apply this rule if**, select **The recipient** and then choose **address includes any of these words**.</span></span>

5. <span data-ttu-id="44f4f-118">Nella casella **specifica parole o frasi** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="44f4f-118">In the **specify words or phrases** box, do the following steps:</span></span>

   - <span data-ttu-id="44f4f-119">Digitare `abuse@messaging.microsoft.com`, fare \*\*\*\* ![clic su Aggiungi](../media/ITPro-EAC-AddIcon.gif)icona, `junk@office365.microsoft.com` digitare e quindi fare clic su](../media/ITPro-EAC-AddIcon.gif) **Aggiungi** ![icona Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="44f4f-119">Type `abuse@messaging.microsoft.com`, click **Add** ![Add Icon](../media/ITPro-EAC-AddIcon.gif), type `junk@office365.microsoft.com` and then click **Add** ![Add Icon](../media/ITPro-EAC-AddIcon.gif).</span></span> <span data-ttu-id="44f4f-120">Questi indirizzi di posta elettronica vengono utilizzati per inviare messaggi negativi falsi a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="44f4f-120">These email addresses are used to submit false negative messages to Microsoft.</span></span>

   - <span data-ttu-id="44f4f-121">Digitare `phish@office365.microsoft.com` e quindi fare \*\*\*\* ![clic su Aggiungi](../media/ITPro-EAC-AddIcon.gif)icona.</span><span class="sxs-lookup"><span data-stu-id="44f4f-121">Type `phish@office365.microsoft.com` and then click **Add** ![Add Icon](../media/ITPro-EAC-AddIcon.gif).</span></span> <span data-ttu-id="44f4f-122">Questo indirizzo di posta elettronica viene utilizzato per inviare messaggi di phishing non letti a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="44f4f-122">This email address is used to submit missed phishing messages to Microsoft.</span></span>

   - <span data-ttu-id="44f4f-123">Digitare `false_positive@messaging.microsoft.com`, fare \*\*\*\* ![clic su Aggiungi](../media/ITPro-EAC-AddIcon.gif)icona, `not_junk@office365.microsoft.com`digitare e quindi fare clic su **Aggiungi** ![icona](../media/ITPro-EAC-AddIcon.gif)Aggiungi.</span><span class="sxs-lookup"><span data-stu-id="44f4f-123">Type `false_positive@messaging.microsoft.com`, click **Add** ![Add Icon](../media/ITPro-EAC-AddIcon.gif), type `not_junk@office365.microsoft.com`, and then click **Add** ![Add Icon](../media/ITPro-EAC-AddIcon.gif).</span></span> <span data-ttu-id="44f4f-124">Questi indirizzi di posta elettronica vengono utilizzati per inviare messaggi falsi positivi a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="44f4f-124">These email addresses are used to submit false positive messages to Microsoft.</span></span>

   - <span data-ttu-id="44f4f-125">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="44f4f-125">Click **OK**.</span></span>

6. <span data-ttu-id="44f4f-126">In **Eseguire le operazioni seguenti** selezionare **Invia il messaggio in Ccn a...**, quindi selezionare le cassette postali in cui si desidera ricevere i messaggi.</span><span class="sxs-lookup"><span data-stu-id="44f4f-126">Under **Do the following**, select **Bcc the message to...** and then and then select the mailboxes where you'd like to receive the messages.</span></span>

7. <span data-ttu-id="44f4f-127">Se lo si desidera, è possibile effettuare le selezioni per controllare la regola, testare la regola, attivare la regola per un periodo di tempo specifico e altre selezioni.</span><span class="sxs-lookup"><span data-stu-id="44f4f-127">If you'd like, you can make selections to audit the rule, test the rule, activate the rule during a specific time period, and other selections.</span></span> <span data-ttu-id="44f4f-128">È consigliabile testare la regola per un periodo prima di applicarlo.</span><span class="sxs-lookup"><span data-stu-id="44f4f-128">We recommend testing the rule for a period before you enforce it.</span></span> <span data-ttu-id="44f4f-129">Vedere [procedure per le regole del flusso di posta](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures).</span><span class="sxs-lookup"><span data-stu-id="44f4f-129">See [Procedures for mail flow rules](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures).</span></span>

8. <span data-ttu-id="44f4f-p107">Fare clic sul pulsante **salva** per salvare la regola. Viene visualizzata nell'elenco delle regole.</span><span class="sxs-lookup"><span data-stu-id="44f4f-p107">Click the **save** button to save the rule. It appears in your list of rules.</span></span>

<span data-ttu-id="44f4f-132">Dopo aver creato e impostato la regola, eventuali messaggi inviati dall'organizzazione agli indirizzi di posta elettronica specificati verranno copiati alla cassetta postale specificata.</span><span class="sxs-lookup"><span data-stu-id="44f4f-132">After you create and enforce the rule, any messages that are sent from your organization to specified email addresses will be copied to the specified mailbox.</span></span>
