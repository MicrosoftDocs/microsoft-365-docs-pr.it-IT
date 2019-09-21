---
title: Invii di amministratore in Office 365, O365 invii, Office 365 spam problem, O365 false negative, Submit phishing in Office 365, inviare la posta elettronica per l'analisi, la posta elettronica sospetti in Office 365, analizzare una posta elettronica, avere Microsoft Scan per phishing, avere Microsoft Scan per la posta indesiderata, invio posta elettronica, inviare messaggi di posta elettronica
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 08/06/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Informazioni su come inviare messaggi di posta elettronica sospetti, sospette mail di phishing, spam e altre potenzialmente nocive, URL e file dal tenant di Office 365 a Microsoft per l'analisi.
ms.openlocfilehash: 5ca5eab2feab1243a83eb60c9320fd48dfb59f12
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37084932"
---
# <a name="how-to-submit-suspected-spam-phish-urls-and-files-to-microsoft-for-office-365-scanning"></a><span data-ttu-id="1e703-103">Come inviare messaggi di posta indesiderata, phishing, URL e file sospetti a Microsoft per l'analisi di Office 365</span><span class="sxs-lookup"><span data-stu-id="1e703-103">How to submit suspected spam, phish, URLs, and files to Microsoft for Office 365 scanning</span></span>

<span data-ttu-id="1e703-104">Gli amministratori possono inviare messaggi di posta elettronica utilizzando il file o l'ID del messaggio di rete, gli URL e i file per l'analisi da parte di Microsoft in Office 365.</span><span class="sxs-lookup"><span data-stu-id="1e703-104">Admins can send emails by using file or network message ID, URLs, and files for scanning by Microsoft in Office 365.</span></span> <span data-ttu-id="1e703-105">La sezione aggiornamenti aggiornati include ancora i messaggi segnalati dall'utente e disponibili per tutti i clienti che utilizzano EOP.</span><span class="sxs-lookup"><span data-stu-id="1e703-105">The updated submissions section still includes user reported messages and available to all customers using EOP.</span></span>

<span data-ttu-id="1e703-106">Quando si invia un messaggio di posta elettronica, si ottengono informazioni su tutti i criteri che possono aver consentito la posta elettronica in arrivo nel tenant, nonché l'esame degli URL e degli allegati della posta.</span><span class="sxs-lookup"><span data-stu-id="1e703-106">When you submit an email, you will get information about any policies that may have allowed the incoming email into your tenant, as well as examination of any URLs and attachments in the mail.</span></span> <span data-ttu-id="1e703-107">I criteri che possono aver consentito a un messaggio di posta elettronica includono l'elenco dei mittenti attendibili di un singolo utente e i criteri di livello tenant, ad esempio le regole di ETR.</span><span class="sxs-lookup"><span data-stu-id="1e703-107">Policies that may have allowed a mail include an individual user's safe sender list as well as tenant level policies such as ETR rules.</span></span> 

## <a name="how-to-submit-content-to-microsoft-for-office-365-scanning"></a><span data-ttu-id="1e703-108">Come inviare contenuti a Microsoft per l'analisi di Office 365</span><span class="sxs-lookup"><span data-stu-id="1e703-108">How to submit content to Microsoft for Office 365 scanning</span></span>

<span data-ttu-id="1e703-109">Per inviare contenuto a Microsoft fare clic sul pulsante **nuovo invio** nella parte superiore sinistra della pagina invii.</span><span class="sxs-lookup"><span data-stu-id="1e703-109">To submit content to Microsoft click the **New submission** button in the top left hand side of the submissions page.</span></span> <span data-ttu-id="1e703-110">Viene visualizzato un riquadro a comparsa sul lato destro della pagina con l'opzione per inviare un messaggio di posta elettronica, un URL o un file.</span><span class="sxs-lookup"><span data-stu-id="1e703-110">A flyout on the right side of the page appears with the option to submit either an email, URL, or file.</span></span> 

### <a name="submit-an-email-to-microsoft"></a><span data-ttu-id="1e703-111">Inviare un messaggio di posta elettronica a Microsoft</span><span class="sxs-lookup"><span data-stu-id="1e703-111">Submit an email to Microsoft</span></span>
![Esempio di invio tramite posta elettronica](../media/submission-flyout-email.PNG)
1. <span data-ttu-id="1e703-113">Per inviare un messaggio di posta elettronica, selezionare **posta elettronica** e specificare l' **ID della rete** di posta elettronica o caricare il file di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="1e703-113">To submit an email, select **email** and specify the email **network message ID** or upload the email file.</span></span> 

2. <span data-ttu-id="1e703-114">Specificare il destinatario o i destinatari a cui si desidera eseguire il controllo dei criteri.</span><span class="sxs-lookup"><span data-stu-id="1e703-114">Specify the recipient(s) that you would like to run the policy check against.</span></span> <span data-ttu-id="1e703-115">Il controllo dei criteri determina se l'analisi del messaggio di posta elettronica è stata ignorata a causa dei criteri a livello di utente o tenant.</span><span class="sxs-lookup"><span data-stu-id="1e703-115">The policy check will determine if the email bypassed scanning due to user or tenant level policies.</span></span> 

3. <span data-ttu-id="1e703-116">Specificare se il messaggio di posta elettronica deve essere stato bloccato o meno.</span><span class="sxs-lookup"><span data-stu-id="1e703-116">Specify if the email should have been blocked or not.</span></span> <span data-ttu-id="1e703-117">Se il messaggio di posta elettronica deve essere stato bloccato, specificare se deve essere stato bloccato come posta indesiderata, phishing o malware.</span><span class="sxs-lookup"><span data-stu-id="1e703-117">If the email should have been blocked, specify if it should have been blocked as Spam, Phishing, or Malware.</span></span> <span data-ttu-id="1e703-118">Se non si è certi di quale tipo potrebbe essere, utilizzare il giudizio migliore.</span><span class="sxs-lookup"><span data-stu-id="1e703-118">If you are not sure what type it might be, use your best judgement.</span></span>  

* <span data-ttu-id="1e703-119">Se il filtro è stato ignorato a causa di criteri al momento dell'invio, verranno visualizzate le informazioni relative a tale criterio.</span><span class="sxs-lookup"><span data-stu-id="1e703-119">If the filter was bypassed due to policies upon submission, you'll see information about that policy.</span></span>

* <span data-ttu-id="1e703-120">Se il filtro non è stato bypassato a causa di uno o più criteri, l'analisi verrà completata in alcuni minuti.</span><span class="sxs-lookup"><span data-stu-id="1e703-120">If the filter was not bypassed due to one or more policies, the scan will complete in several minutes.</span></span> <span data-ttu-id="1e703-121">Vedrai altre informazioni sull'invio facendo clic sul collegamento di stato.</span><span class="sxs-lookup"><span data-stu-id="1e703-121">You'll see additional information about the submission by clicking on the status link.</span></span> <span data-ttu-id="1e703-122">Questo include i risultati del controllo dei criteri e il verdetto di rianalisi.</span><span class="sxs-lookup"><span data-stu-id="1e703-122">This includes the results of the policy check and the rescan verdict.</span></span> <span data-ttu-id="1e703-123">Si noti che non viene eseguito di nuovo il messaggio di posta elettronica tramite lo stack filtro completo ATP di Office 365 ma viene eseguita una nuova analisi parziale in base a determinati attributi di posta, URL o file.</span><span class="sxs-lookup"><span data-stu-id="1e703-123">Note this does not run the email through the Office 365 ATP full filtering stack again but runs a partial rescan based on certain attributes of the mail, URL, or file.</span></span> 

4. <span data-ttu-id="1e703-124">Fare clic sul pulsante **Invia** .</span><span class="sxs-lookup"><span data-stu-id="1e703-124">Click the **Submit** button.</span></span>

### <a name="submit-a-url-to-microsoft"></a><span data-ttu-id="1e703-125">Invio di un URL a Microsoft</span><span class="sxs-lookup"><span data-stu-id="1e703-125">Submit a URL to Microsoft</span></span>
![Esempio di invio tramite posta elettronica](../media/submission-url-flyout.png)
1. <span data-ttu-id="1e703-127">Per inviare un **URL selezionare URL dal riquadro a comparsa** .</span><span class="sxs-lookup"><span data-stu-id="1e703-127">To submit a URL select **URL** from the flyout.</span></span> <span data-ttu-id="1e703-128">Digitare l'URL completo, incluso il protocollo (**https://**).</span><span class="sxs-lookup"><span data-stu-id="1e703-128">Type in the full URL including the protocol (**https://**).</span></span> 

* <span data-ttu-id="1e703-129">Se è **stato selezionato deve essere stato filtrato**, specificare se l'URL è phishing o malware.</span><span class="sxs-lookup"><span data-stu-id="1e703-129">If you selected **Should have been filtered**, specify if the URL is phishing or malware.</span></span>

2. <span data-ttu-id="1e703-130">Fare clic sul pulsante **Invia** .</span><span class="sxs-lookup"><span data-stu-id="1e703-130">Click the **Submit** button.</span></span> 


### <a name="submit-a-file-to-microsoft"></a><span data-ttu-id="1e703-131">Inviare un file a Microsoft</span><span class="sxs-lookup"><span data-stu-id="1e703-131">Submit a file to Microsoft</span></span>
![Esempio di invio tramite posta elettronica](../media/submission-file-flyout.PNG)
1. <span data-ttu-id="1e703-133">Per inviare un file seleziona **file** dal riquadro a comparsa e caricare il file che si desidera analizzare.</span><span class="sxs-lookup"><span data-stu-id="1e703-133">To submit a file select **File** from the flyout and upload the file you would like to scan.</span></span> 

2. <span data-ttu-id="1e703-134">Fare clic sul pulsante **Invia** .</span><span class="sxs-lookup"><span data-stu-id="1e703-134">Click the **Submit** button.</span></span>


## <a name="related-topics"></a><span data-ttu-id="1e703-135">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="1e703-135">Related topics</span></span>

[<span data-ttu-id="1e703-136">Office 365 Advanced Threat Protection piano 2</span><span class="sxs-lookup"><span data-stu-id="1e703-136">Office 365 Advanced Threat Protection Plan 2</span></span>](office-365-ti.md)
  
[<span data-ttu-id="1e703-137">Protezione dalle minacce in Office 365</span><span class="sxs-lookup"><span data-stu-id="1e703-137">Protect against threats in Office 365</span></span>](protect-against-threats.md)
  
[<span data-ttu-id="1e703-138">Visualizzare i report per Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="1e703-138">View reports for Office 365 Advanced Threat Protection</span></span>](view-reports-for-atp.md)
  

