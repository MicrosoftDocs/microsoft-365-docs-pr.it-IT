---
title: Notifica di esempio quando a un mittente viene impedito di inviare posta indesiderata in uscita.
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/02/2017
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c33fd406-a4c8-4ac8-ad85-123996c5cded
ms.collection:
- M365-security-compliance
description: "Quando un mittente viene bloccato dal servizio a causa dell'invio di posta indesiderata in uscita, l'amministratore del dominio specificato quando si configura il criterio di posta indesiderata in uscita riceverà un messaggio di posta elettronica di notifica simile al seguente:"
ms.openlocfilehash: 537e97fe952ad9a5b2ca854c44fe6c53b642e3ac
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "41598503"
---
# <a name="sample-notification-when-a-sender-is-blocked-sending-outbound-spam"></a><span data-ttu-id="01446-103">Notifica di esempio quando a un mittente viene impedito di inviare posta indesiderata in uscita.</span><span class="sxs-lookup"><span data-stu-id="01446-103">Sample notification when a sender is blocked sending outbound spam</span></span>

<span data-ttu-id="01446-104">Quando un mittente viene bloccato dal servizio a causa dell'invio di posta indesiderata in uscita, l'amministratore del dominio specificato quando si [Configura il criterio di posta indesiderata in uscita](configure-the-outbound-spam-policy.md) riceverà un messaggio di posta elettronica di notifica simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="01446-104">When a sender is blocked from the service due to sending outbound spam, the domain admin specified when you [Configure the outbound spam policy](configure-the-outbound-spam-policy.md) will receive a notification email similar to the following:</span></span> 
  
 <span data-ttu-id="01446-105">**Indirizzo mittente:** spamalerts@microsoft.com</span><span class="sxs-lookup"><span data-stu-id="01446-105">**Sender address:** spamalerts@microsoft.com</span></span> 
  
 <span data-ttu-id="01446-106">**Oggetto:** Notifica posta indesiderata in uscita - a \<  *account name*  \> è stato impedito di inviare posta indesiderata in uscita</span><span class="sxs-lookup"><span data-stu-id="01446-106">**Subject:** Outbound spam notification - \<  *account name*  \> blocked from sending outbound mail</span></span> 
  
 <span data-ttu-id="01446-107">**Corpo:** Si tratta di una risposta automatica del sistema di analisi di posta indesiderata di Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="01446-107">**Body:** This is an automated reply from the Exchange Online Protection Spam Analysis System.</span></span> 
  
<span data-ttu-id="01446-p101">Sono stati rilevati volumi elevati di posta elettronica contrassegnata come posta indesiderata o altro comportamento sospetto da parte di questa organizzazione. Ai seguenti account di posta elettronica è stato impedito di inviare posta elettronica (continueranno a ricevere messaggi di posta elettronica):</span><span class="sxs-lookup"><span data-stu-id="01446-p101">You are being contacted because we have detected high volumes of email marked as spam, or other suspicious behavior, originating from your organization. The following email accounts have been blocked from sending email (they can still receive email):</span></span>
  
<span data-ttu-id="01446-110">\< *account name*  \></span><span class="sxs-lookup"><span data-stu-id="01446-110">\< *account name*  \></span></span> 
  
<span data-ttu-id="01446-p102">È probabile che questo account di posta elettronica sia stato compromesso. Attenersi alla seguente procedura:</span><span class="sxs-lookup"><span data-stu-id="01446-p102">It is likely that this email account has been compromised. Please follow these steps:</span></span>
  
1. <span data-ttu-id="01446-113">Risolvere questo problema internamente effettuando le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="01446-113">Resolve this issue on your side by:</span></span>
    
  - <span data-ttu-id="01446-114">Modificare la password dell'account.</span><span class="sxs-lookup"><span data-stu-id="01446-114">Changing the password of the account.</span></span>
    
  - <span data-ttu-id="01446-115">Determinare la modalità con cui l'account è stato compromesso.</span><span class="sxs-lookup"><span data-stu-id="01446-115">Determining how the account was compromised.</span></span>
    
  - <span data-ttu-id="01446-116">Adottare precauzioni per garantire che tale vulnerabilità non venga sfruttata di nuovo.</span><span class="sxs-lookup"><span data-stu-id="01446-116">Taking precautions to ensure that this vulnerability will not be exploited again.</span></span>
    
  - <span data-ttu-id="01446-117">Confermare che nella coda della posta in uscita siano stati cancellati tutti i messaggi incriminati.</span><span class="sxs-lookup"><span data-stu-id="01446-117">Confirming that your outbound mail queue has been cleared of all offending messages.</span></span>
    
2. <span data-ttu-id="01446-118">Contattare il supporto tecnico Microsoft tramite il consueto canale di contatto.</span><span class="sxs-lookup"><span data-stu-id="01446-118">Contact Microsoft support by using your regular contact channel.</span></span>
    
3. <span data-ttu-id="01446-119">Spiegare che a un utente è stato impedito di inviare posta elettronica e che il problema è stato gestito.</span><span class="sxs-lookup"><span data-stu-id="01446-119">Explain that you have a user that is blocked from sending mail and that the problem has been dealt with.</span></span>
    
4. <span data-ttu-id="01446-120">L'agente creerà un ticket di supporto con le informazioni fornite e riassegnerà la pratica per sbloccare il dominio o l'indirizzo di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="01446-120">The agent will create a support ticket with the information that you provide and escalate it to have the email address or domain unblocked.</span></span>
    
5. <span data-ttu-id="01446-121">Dopo che l'indirizzo è stato sbloccato e non ci sono altri problemi in sospeso, si verrà informati e avvisati dello sblocco.</span><span class="sxs-lookup"><span data-stu-id="01446-121">After the address has been unblocked, and pending no other issues, you will be contacted and alerted to the unblocking.</span></span>
    
<span data-ttu-id="01446-122">Grazie per l'aiuto offerto nel controllo della posta elettronica indesiderata.</span><span class="sxs-lookup"><span data-stu-id="01446-122">Thank you for assisting us in controlling unwanted email.</span></span>
  
<span data-ttu-id="01446-123">Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="01446-123">Exchange Online Protection.</span></span>
  
<span data-ttu-id="01446-124">\*\*NOTA - Non rispondere a questo messaggio, in quanto è stato inviato da un indirizzo di posta elettronica che non viene controllato.\*\*</span><span class="sxs-lookup"><span data-stu-id="01446-124">\*\*NOTE - Please do not respond to this email as it is sent from an unmonitored address\*\*</span></span>
  
> [!TIP]
> <span data-ttu-id="01446-125">È inoltre possibile contattare il supporto tramite le opzioni descritte in [Help and Support for EOP](help-and-support-for-eop.md).</span><span class="sxs-lookup"><span data-stu-id="01446-125">You can also contact support via the options documented at [Help and support for EOP](help-and-support-for-eop.md).</span></span> 
  

