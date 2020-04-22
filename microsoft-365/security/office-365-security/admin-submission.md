---
title: Invii di amministratore, invii, problemi di posta indesiderata, false negative, inviare phishing, inviare messaggi di posta elettronica per l'analisi, messaggi di posta elettronica sospetti in Office 365, analizzare una posta elettronica, avere Microsoft Scan per phishing, avere Microsoft Scan per posta indesiderata, inviare messaggi di posta elettronica, inviare messaggi di posta elettronica, segnalare messaggi di posta elettronica ingannevoli a Microsoft , segnala malware nella posta elettronica a Microsoft, messaggi di posta indesiderata in posta in arrivo, virus nella posta elettronica
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
description: Informazioni su come inviare messaggi di posta elettronica sospetti, sospette mail di phishing, la posta indesiderata e altre potenzialmente dannose, URL e file dalla propria azienda a Microsoft per l'analisi.
ms.openlocfilehash: 2d86555854f9babd202764f1bad8b548daf52c70
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631382"
---
# <a name="use-admin-submission-to-submit-suspected-spam-phish-urls-and-files-to-microsoft"></a><span data-ttu-id="d64f0-103">Usare l'Invio dell'amministratore per inviare posta indesiderata sospetta, phishing, URL e file a Microsoft</span><span class="sxs-lookup"><span data-stu-id="d64f0-103">Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft</span></span>

<span data-ttu-id="d64f0-104">Se si è un amministratore di un'organizzazione Microsoft 365 con cassette postali in Exchange Online, è possibile utilizzare il portale invii nel centro sicurezza & Compliance per inviare messaggi di posta elettronica, URL e allegati a Microsoft per l'analisi.</span><span class="sxs-lookup"><span data-stu-id="d64f0-104">If you're an admin in a Microsoft 365 organization with mailboxes in Exchange Online, you can use the Submissions portal in the Security & Compliance Center to submit email messages, URLs and attachments to Microsoft for scanning.</span></span>

<span data-ttu-id="d64f0-105">Quando si invia un messaggio di posta elettronica, si ottengono informazioni su tutti i criteri che possono aver consentito la posta elettronica in arrivo nel tenant, nonché l'esame degli URL e degli allegati della posta.</span><span class="sxs-lookup"><span data-stu-id="d64f0-105">When you submit an email, you will get information about any policies that may have allowed the incoming email into your tenant, as well as examination of any URLs and attachments in the mail.</span></span> <span data-ttu-id="d64f0-106">I criteri che possono aver consentito a un messaggio di posta elettronica includono l'elenco dei mittenti attendibili di un singolo utente e i criteri di livello tenant, ad esempio le regole del flusso di posta di Exchange (note anche come regole di trasporto)</span><span class="sxs-lookup"><span data-stu-id="d64f0-106">Policies that may have allowed a mail include an individual user's safe sender list as well as tenant level policies such as Exchange mail flow rules (also known as transport rules).</span></span>

<span data-ttu-id="d64f0-107">Per altri modi per inviare messaggi di posta elettronica, URL e allegati a Microsoft, vedere</span><span class="sxs-lookup"><span data-stu-id="d64f0-107">For other ways to submit email messages, URLs, and attachments to Microsoft, see</span></span> 

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="d64f0-108">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="d64f0-108">What do you need to know before you begin?</span></span>

- <span data-ttu-id="d64f0-109">Aprire il Centro sicurezza e conformità in <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="d64f0-109">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="d64f0-110">Per passare direttamente alla pagina **invio** , utilizzare <https://protection.office.com/reportsubmission>.</span><span class="sxs-lookup"><span data-stu-id="d64f0-110">To go directly to the **Submission** page, use <https://protection.office.com/reportsubmission>.</span></span>

- <span data-ttu-id="d64f0-111">Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="d64f0-111">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="d64f0-112">Per connettersi a PowerShell per Exchange Online Protection autonomo, vedere [Connettersi a PowerShell per Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="d64f0-112">To connect to standalone Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="d64f0-113">È necessario disporre delle autorizzazioni prima di poter eseguire queste procedure.</span><span class="sxs-lookup"><span data-stu-id="d64f0-113">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="d64f0-114">Per aggiungere, modificare ed eliminare i criteri di protezione da posta indesiderata, è necessario essere membri dei gruppi di ruoli **Gestione organizzazione**, **amministratore sicurezza**o **lettore di sicurezza** .</span><span class="sxs-lookup"><span data-stu-id="d64f0-114">To add, modify, and delete anti-spam policies, you need to be a member of the **Organization Management**, **Security Administrator**, or **Security Reader** role groups.</span></span> <span data-ttu-id="d64f0-115">Per ulteriori informazioni sui gruppi di ruoli nel centro sicurezza & Compliance, vedere [Permissions in the security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="d64f0-115">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="d64f0-116">Per ulteriori informazioni sul modo in cui gli utenti possono inviare messaggi e file a Microsoft, vedere [segnala messaggi e file a Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="d64f0-116">For more information about how users can submit messages and files to Microsoft see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="how-to-direct-suspicious-content-to-microsoft-scanning"></a><span data-ttu-id="d64f0-117">Come indirizzare i contenuti sospetti all'analisi di Microsoft</span><span class="sxs-lookup"><span data-stu-id="d64f0-117">How to direct suspicious content to Microsoft scanning</span></span>

<span data-ttu-id="d64f0-118">Per inviare contenuto a Microsoft fare clic sul pulsante **nuovo invio** nella parte superiore sinistra della pagina invii.</span><span class="sxs-lookup"><span data-stu-id="d64f0-118">To submit content to Microsoft click the **New submission** button in the top left hand side of the submissions page.</span></span> <span data-ttu-id="d64f0-119">Viene visualizzato un riquadro a comparsa sul lato destro della pagina con l'opzione per inviare un messaggio di posta elettronica, un URL o un file.</span><span class="sxs-lookup"><span data-stu-id="d64f0-119">A flyout on the right side of the page appears with the option to submit either an email, URL, or file.</span></span>

### <a name="submit-a-questionable-email-to-microsoft"></a><span data-ttu-id="d64f0-120">Inviare un messaggio di posta elettronica discutibile a Microsoft</span><span class="sxs-lookup"><span data-stu-id="d64f0-120">Submit a questionable email to Microsoft</span></span>

![Esempio di invio tramite posta elettronica](../../media/submission-flyout-email.PNG)

1. <span data-ttu-id="d64f0-122">Per inviare un messaggio di posta elettronica, selezionare **posta elettronica** e specificare l' **ID della rete** di posta elettronica o caricare il file di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="d64f0-122">To submit an email, select **email** and specify the email **network message ID** or upload the email file.</span></span>

2. <span data-ttu-id="d64f0-123">Specificare il destinatario o i destinatari a cui si desidera eseguire il controllo dei criteri.</span><span class="sxs-lookup"><span data-stu-id="d64f0-123">Specify the recipient(s) that you would like to run the policy check against.</span></span> <span data-ttu-id="d64f0-124">Il controllo dei criteri determina se l'analisi del messaggio di posta elettronica è stata ignorata a causa dei criteri a livello di utente o tenant.</span><span class="sxs-lookup"><span data-stu-id="d64f0-124">The policy check will determine if the email bypassed scanning due to user or tenant level policies.</span></span>

3. <span data-ttu-id="d64f0-125">Specificare se il messaggio di posta elettronica deve essere stato bloccato o meno.</span><span class="sxs-lookup"><span data-stu-id="d64f0-125">Specify if the email should have been blocked or not.</span></span> <span data-ttu-id="d64f0-126">Se il messaggio di posta elettronica deve essere stato bloccato, specificare se deve essere stato bloccato come posta indesiderata, phishing o malware.</span><span class="sxs-lookup"><span data-stu-id="d64f0-126">If the email should have been blocked, specify if it should have been blocked as Spam, Phishing, or Malware.</span></span> <span data-ttu-id="d64f0-127">Se non si è certi di quale tipo potrebbe essere, utilizzare il miglior giudizio.</span><span class="sxs-lookup"><span data-stu-id="d64f0-127">If you are not sure what type it might be, use your best judgment.</span></span>

   - <span data-ttu-id="d64f0-128">Se il filtro è stato ignorato a causa di criteri al momento dell'invio, verranno visualizzate le informazioni relative a tale criterio.</span><span class="sxs-lookup"><span data-stu-id="d64f0-128">If the filter was bypassed due to policies upon submission, you'll see information about that policy.</span></span>

   - <span data-ttu-id="d64f0-129">Se il filtro non è stato bypassato a causa di uno o più criteri, l'analisi verrà completata in alcuni minuti.</span><span class="sxs-lookup"><span data-stu-id="d64f0-129">If the filter was not bypassed due to one or more policies, the scan will complete in several minutes.</span></span> <span data-ttu-id="d64f0-130">Vedrai altre informazioni sull'invio facendo clic sul collegamento di stato.</span><span class="sxs-lookup"><span data-stu-id="d64f0-130">You'll see additional information about the submission by clicking on the status link.</span></span> <span data-ttu-id="d64f0-131">Questo include i risultati del controllo dei criteri e il verdetto di rianalisi.</span><span class="sxs-lookup"><span data-stu-id="d64f0-131">This includes the results of the policy check and the rescan verdict.</span></span> <span data-ttu-id="d64f0-132">Si noti che non viene eseguito di nuovo il messaggio di posta elettronica tramite lo stack filtro completo ATP di Office 365 ma viene eseguita una nuova analisi parziale in base a determinati attributi di posta, URL o file.</span><span class="sxs-lookup"><span data-stu-id="d64f0-132">Note this does not run the email through the Office 365 ATP full filtering stack again but runs a partial rescan based on certain attributes of the mail, URL, or file.</span></span>

4. <span data-ttu-id="d64f0-133">Fare clic sul pulsante **Invia** .</span><span class="sxs-lookup"><span data-stu-id="d64f0-133">Click the **Submit** button.</span></span>

### <a name="send-a-suspect-url-to-microsoft"></a><span data-ttu-id="d64f0-134">Inviare un URL sospetto a Microsoft</span><span class="sxs-lookup"><span data-stu-id="d64f0-134">Send a suspect URL to Microsoft</span></span>

![Esempio di invio tramite posta elettronica](../../media/submission-url-flyout.png)

1. <span data-ttu-id="d64f0-136">Per inviare un **URL selezionare URL dal riquadro a comparsa** .</span><span class="sxs-lookup"><span data-stu-id="d64f0-136">To submit a URL select **URL** from the flyout.</span></span> <span data-ttu-id="d64f0-137">Digitare l'URL completo, incluso il protocollo (**https://**).</span><span class="sxs-lookup"><span data-stu-id="d64f0-137">Type in the full URL including the protocol (**https://**).</span></span>

   <span data-ttu-id="d64f0-138">Se è **stato selezionato deve essere stato filtrato**, specificare se l'URL è phishing o malware.</span><span class="sxs-lookup"><span data-stu-id="d64f0-138">If you selected **Should have been filtered**, specify if the URL is phishing or malware.</span></span>

2. <span data-ttu-id="d64f0-139">Fare clic sul pulsante **Invia** .</span><span class="sxs-lookup"><span data-stu-id="d64f0-139">Click the **Submit** button.</span></span>

### <a name="submit-a-suspected-file-to-microsoft"></a><span data-ttu-id="d64f0-140">Inviare un file sospetto a Microsoft</span><span class="sxs-lookup"><span data-stu-id="d64f0-140">Submit a suspected file to Microsoft</span></span>

![Esempio di invio tramite posta elettronica](../../media/submission-file-flyout.PNG)

1. <span data-ttu-id="d64f0-142">Per inviare un file seleziona **file** dal riquadro a comparsa e caricare il file che si desidera analizzare.</span><span class="sxs-lookup"><span data-stu-id="d64f0-142">To submit a file select **File** from the flyout and upload the file you would like to scan.</span></span>

2. <span data-ttu-id="d64f0-143">Fare clic sul pulsante **Invia** .</span><span class="sxs-lookup"><span data-stu-id="d64f0-143">Click the **Submit** button.</span></span>
