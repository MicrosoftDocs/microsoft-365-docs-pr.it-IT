---
title: Differenza tra posta elettronica indesiderata e posta elettronica in blocco
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 1/7/2015
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 8079f193-1b40-4081-9e5d-d0e50dfbcc59
ms.collection:
- M365-security-compliance
description: I clienti a volte askwhat è la differenza tra posta elettronica indesiderata e messaggi di posta elettronica in blocco? Lo scopo di questo argomento è spiegare la differenza e fornire informazioni sulle diverse opzioni disponibili per entrambi in Exchange Online e Exchange Online Protection (EOP).
ms.openlocfilehash: a427fd7a37ec4a5b9828a0f78a32d6e5fd54d69b
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "41597983"
---
# <a name="whats-the-difference-between-junk-email-and-bulk-email"></a><span data-ttu-id="37e86-103">Differenza tra posta elettronica indesiderata e posta elettronica in blocco</span><span class="sxs-lookup"><span data-stu-id="37e86-103">What's the difference between junk email and bulk email?</span></span>

<span data-ttu-id="37e86-p101">Talvolta i clienti chiedono quale sia la differenza tra posta elettronica indesiderata e messaggi di posta elettronica in blocco. L'obiettivo di questo argomento è di spiegare la differenza e fornire informazioni sulle diverse opzioni disponibili per entrambi in Exchange Online e Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="37e86-p101">Customers sometimes ask "what's the difference between junk email and bulk email messages?" The purpose of this topic is to explain the difference and to provide information about the different options that are available for both in Exchange Online and Exchange Online Protection (EOP).</span></span>
  
 <span data-ttu-id="37e86-106">**Cos'è la posta elettronica indesiderata**</span><span class="sxs-lookup"><span data-stu-id="37e86-106">**What's junk email?**</span></span>
  
<span data-ttu-id="37e86-p102">I messaggi di posta elettronica indesiderati sono messaggi di posta indesiderata non richiesti (e di solito non desiderati) che vengono filtrati dal servizio. Per impostazione predefinita, il servizio rifiuta il messaggio in base alla reputazione dell'indirizzo IP di invio. Tuttavia, se supera l'ispezione dell'IP ma viene classificato come posta indesiderata dai filtri del contenuto, il messaggio viene inviato alla cartella Posta indesiderata dei destinatari previsti.</span><span class="sxs-lookup"><span data-stu-id="37e86-p102">Junk email messages are "spam" messages, which are unsolicited (and typically unwanted) email messages that are filtered by the service. By default, the service rejects the spam message based on the reputation of the sending IP address. However, if it passes IP inspection but is classified as spam by the content filters, the message is sent to the Junk Email folder of the intended recipients.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="37e86-p103">L'azione eseguita sui messaggi con filtro del contenuto può essere configurata tramite i criteri filtro contenuto nell'interfaccia di amministrazione di Exchange, come descritto in [Configurare i criteri di filtro della posta indesiderata](configure-your-spam-filter-policies.md). Inoltre, se non si è d'accordo con la classificazione della posta indesiderata, è possibile segnalare i messaggi che si considera posta indesiderata o non indesiderata a Microsoft in vari modi, come descritto in [Invio di messaggi di posta indesiderata e non e tentativi di phishing a Microsoft per l'analisi](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md).</span><span class="sxs-lookup"><span data-stu-id="37e86-p103">The action performed on content-filtered messages is configurable via content filter policies in the Exchange admin center (EAC), as described in [Configure your spam filter policies](configure-your-spam-filter-policies.md). Also, if you disagree with the spam classification, you can report messages that you consider to be spam or non-spam to Microsoft in several ways, as described in [Submit spam, non-spam, and phishing scam messages to Microsoft for analysis](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md).</span></span> 
  
 <span data-ttu-id="37e86-112">**Cos'è la posta elettronica in blocco**</span><span class="sxs-lookup"><span data-stu-id="37e86-112">**What's bulk email?**</span></span>
  
<span data-ttu-id="37e86-p104">La posta in blocco, altrimenti denominata, posta grigia, è un tipo di messaggio di posta elettronica più difficile da classificare. Mentre la posta elettronica indesiderata è una minaccia costante, la posta elettronica in blocco in genere include un messaggio pubblicitario o di marketing che non viene inviato continuamente. La posta in blocco è desiderata da alcuni utenti, che potrebbero aver sottoscritto intenzionalmente la ricezione di questi messaggi, mentre altri utenti potrebbero considerare come posta indesiderata questo tipo di messaggi. Ad esempio, alcuni utenti desiderano ricevere messaggi di posta elettronica pubblicitari da Contoso Corporation o inviti a una conferenza imminente sulla sicurezza IT, mentre altri utenti considerano posta indesiderata questi messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="37e86-p104">Bulk email, also referred to as gray mail, is a type of email message that's more difficult to classify. Whereas junk email is a constant threat, bulk email is typically comprised of an advertisement or marketing message that's not likely to get sent repeatedly. Bulk email is wanted by some users, and in fact they may have deliberately signed up to receive these messages, while other users may consider these types of messages to be spam. For example, some users want to receive advertising emails from the Contoso Corporation or invitations to an upcoming conference on cyber security, while other users consider such emails to be spam.</span></span>
  
## <a name="how-to-manage-bulk-email"></a><span data-ttu-id="37e86-117">Come gestire la posta elettronica in blocco</span><span class="sxs-lookup"><span data-stu-id="37e86-117">How to manage bulk email</span></span>

<span data-ttu-id="37e86-p105">Il modo in cui gestire la posta elettronica in blocco non è una decisione chiara, in quanto se tutta la posta in blocco viene classificata come spam, gli utenti che invece desiderano riceverla potrebbero reclamare e inviarla come messaggio falso positivo (non di posta indesiderata) erroneamente contrassegnato come posta indesiderata. D'altra parte, se si consente il passaggio di tutta la posta elettronica in blocco, gli utenti che non la desiderano potrebbero reclamare e inviarla come messaggio di posta elettronica indesiderata (falso negativo) arrivato per errore nella propria Posta in arrivo.</span><span class="sxs-lookup"><span data-stu-id="37e86-p105">How to manage bulk email isn't a clear cut decision, because if all bulk email is classified as spam, the users that want it may complain and submit it as a false positive (non-spam) message that was wrongly marked as spam. On the other hand, if all bulk email is let through, the users that don't want it may complain and submit it as a missed spam message (false negative) that wrongly arrived in their inbox.</span></span>
  
### <a name="enable-bulk-mail-sensitivity-control-in-the-content-filter-policy"></a><span data-ttu-id="37e86-120">Abilitare il controllo della riservatezza sulla posta inviata in massa nel criterio filtro del contenuto</span><span class="sxs-lookup"><span data-stu-id="37e86-120">Enable bulk mail sensitivity control in the content filter policy</span></span>

<span data-ttu-id="37e86-121">A seconda del criterio aziendale sui messaggi di posta elettronica inviati in massa, gli amministratori possono selezionare una soglia da assegnare alla posta inviata in massa.</span><span class="sxs-lookup"><span data-stu-id="37e86-121">Depending on your company's policy on bulk email messages, admins can select a threshold to assign the bulk email.</span></span> <span data-ttu-id="37e86-122">L'impostazione è configurabile tramite i criteri di filtro dei contenuti nell'interfaccia di amministrazione di Exchange.</span><span class="sxs-lookup"><span data-stu-id="37e86-122">The setting is configurable via content filter policies in the EAC.</span></span> <span data-ttu-id="37e86-123">Per la procedura, vedere [configurare i criteri di filtro della posta indesiderata](configure-your-spam-filter-policies.md) .</span><span class="sxs-lookup"><span data-stu-id="37e86-123">Check out [Configure your spam filter policies](configure-your-spam-filter-policies.md) for the steps.</span></span> <span data-ttu-id="37e86-124">È possibile scegliere un'impostazione di soglia da 1-9, dove 1 contrassegna la maggior parte della posta elettronica come posta indesiderata e 9 consente di recapitare la maggior parte della posta elettronica in blocco.</span><span class="sxs-lookup"><span data-stu-id="37e86-124">You can choose a threshold setting from 1-9, where 1 marks most bulk email as spam, and 9 allows most bulk email to be delivered.</span></span> <span data-ttu-id="37e86-125">Il servizio quindi esegue l'azione configurata, ad esempio, l'invio del messaggio alla cartella Posta indesiderata del destinatario.</span><span class="sxs-lookup"><span data-stu-id="37e86-125">The service then performs the configured action, such as sending the message to the recipient's Junk Email folder.</span></span> 
  

