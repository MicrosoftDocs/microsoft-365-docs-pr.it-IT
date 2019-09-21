---
title: Utilizzare le regole del flusso di posta per configurare il filtro della posta elettronica in blocco in Exchange Online Protection
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 2889c82e-fab0-4e85-87b0-b001b2ccd4f7
ms.collection:
- M365-security-compliance
description: Gli amministratori possono scoprire come utilizzare le regole del flusso di posta in Exchange Online Protection per il filtro della posta elettronica in blocco.
ms.openlocfilehash: e354bb137e114a7d11bff97be0c1109becb54f84
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37084563"
---
# <a name="use-mail-flow-rules-to-configure-bulk-email-filtering-in-exchange-online-protection"></a><span data-ttu-id="abed8-103">Utilizzare le regole del flusso di posta per configurare il filtro della posta elettronica in blocco in Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="abed8-103">Use mail flow rules to configure bulk email filtering in Exchange Online Protection</span></span>

<span data-ttu-id="abed8-104">È possibile impostare filtri di contenuto a livello aziendale per la posta indesiderata e i messaggi in blocco utilizzando i criteri di filtro contenuto spam predefiniti.</span><span class="sxs-lookup"><span data-stu-id="abed8-104">You can set company-wide content filters for spam and bulk email using the default spam content-filter policies.</span></span> <span data-ttu-id="abed8-105">Vedere [configurare i criteri di filtro della posta indesiderata](configure-your-spam-filter-policies.md) e [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/Set-HostedContentFilterPolicy?view=exchange-ps) su come impostare i criteri di filtro dei contenuti.</span><span class="sxs-lookup"><span data-stu-id="abed8-105">Check out [Configure your spam filter policies](configure-your-spam-filter-policies.md) and [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/Set-HostedContentFilterPolicy?view=exchange-ps) on how to set the content filter policies.</span></span> 
  
<span data-ttu-id="abed8-106">Se si desiderano ulteriori opzioni per filtrare i messaggi in blocco, è possibile creare regole del flusso di posta (note anche come regole di trasporto) per cercare modelli di testo o frasi che si trovano di frequente nei messaggi di posta elettronica in blocco.</span><span class="sxs-lookup"><span data-stu-id="abed8-106">If you want to more options to filter bulk messages, you can create mail flow rules (also known as transport rules) to search for text patterns or phrases frequently found in bulk emails.</span></span> <span data-ttu-id="abed8-107">Tutti i messaggi che contengono queste caratteristiche verranno contrassegnati come posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="abed8-107">Any message containing these characteristics will be marked as spam.</span></span> <span data-ttu-id="abed8-108">L'utilizzo di queste regole consente di ridurre la quantità di posta indesiderata ricevuta dall'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="abed8-108">Using these rules can help reduce the amount of unwanted bulk email your organization receives.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="abed8-109">Prima di creare le regole del flusso di posta documentate questo argomento, si consiglia di leggere innanzitutto [Qual è la differenza tra posta elettronica indesiderata e posta elettronica in blocco](what-s-the-difference-between-junk-email-and-bulk-email.md) e [valori a livello di reclamo in blocco](bulk-complaint-level-values.md).</span><span class="sxs-lookup"><span data-stu-id="abed8-109">Before creating the mail flow rules documented this topic, we recommend that you first read [What's the difference between junk email and bulk email?](what-s-the-difference-between-junk-email-and-bulk-email.md) and [Bulk Complaint Level values](bulk-complaint-level-values.md).</span></span><br> <span data-ttu-id="abed8-110">Le procedure indicate di seguito consentono di contrassegnare un messaggio come posta indesiderata per l'intera organizzazione.</span><span class="sxs-lookup"><span data-stu-id="abed8-110">The following procedures mark a message as spam for your entire organization.</span></span> <span data-ttu-id="abed8-111">Tuttavia, è possibile aggiungere un'altra condizione per applicare queste regole esclusivamente a destinatari specifici nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="abed8-111">However, you can add another condition to apply these rules only to specific recipients in your organization.</span></span> <span data-ttu-id="abed8-112">In questo modo, le impostazioni di filtro della posta elettronica in blocco aggressive possono essere applicate a pochi utenti fortemente mirati, mentre gli altri utenti (che per lo più ricevono la posta elettronica di massa a cui hanno effettuato l'iscrizione) non sono interessati.</span><span class="sxs-lookup"><span data-stu-id="abed8-112">This way, the aggressive bulk email filtering settings can apply to a few users who are highly targeted, while the rest of your users (who mostly get the bulk email they signed up for) aren't impacted.</span></span> 
  
## <a name="create-a-mail-flow-rule-to-filter-bulk-email-messages-based-on-text-patterns"></a><span data-ttu-id="abed8-113">Creare una regola del flusso di posta per filtrare i messaggi di posta elettronica in blocco in base ai modelli di testo</span><span class="sxs-lookup"><span data-stu-id="abed8-113">Create a mail flow rule to filter bulk email messages based on text patterns</span></span>

1. <span data-ttu-id="abed8-114">Nell'interfaccia di amministrazione di Exchange accedere a **Flusso di posta** \> **Regole**.</span><span class="sxs-lookup"><span data-stu-id="abed8-114">In the Exchange admin center (EAC), go to **Mail flow** \> **Rules**.</span></span>
    
2. <span data-ttu-id="abed8-115">Fare \*\*\*\* ![clic su Aggiungi](../media/ITPro-EAC-AddIcon.gif) icona e quindi selezionare **Crea una nuova regola**.</span><span class="sxs-lookup"><span data-stu-id="abed8-115">Click **Add** ![Add Icon](../media/ITPro-EAC-AddIcon.gif) and then select **Create a new rule**.</span></span>
    
3. <span data-ttu-id="abed8-116">Specificare un nome per la regola.</span><span class="sxs-lookup"><span data-stu-id="abed8-116">Specify a name for the rule.</span></span>
    
4. <span data-ttu-id="abed8-117">Fare clic su **Altre opzioni**.</span><span class="sxs-lookup"><span data-stu-id="abed8-117">Click **More options**.</span></span> <span data-ttu-id="abed8-118">In **applica la regola se**, selezionare **l'** \> oggetto o il corpo o l'oggetto corpo **corrisponde a questi modelli di testo**.</span><span class="sxs-lookup"><span data-stu-id="abed8-118">Under **Apply this rule if**, select **The subject or body** \> **subject or body matches these text patterns**.</span></span>
    
5. <span data-ttu-id="abed8-119">Nella finestra di dialogo **specificare parole o frasi**, aggiungere le seguenti espressioni regolari che si trovano di solito nei messaggi di posta elettronica in blocco, una per volta, e fare clic su **OK** al termine:</span><span class="sxs-lookup"><span data-stu-id="abed8-119">In the **specify words or phrases** dialog box, add the following regular expressions commonly found in bulk emails, one at a time, and click **ok** when you're done:</span></span> 
    
   - `If you are unable to view the content of this email\, please`
    
   - `\>(safe )?unsubscribe( here)?\</a\>`
    
   - `If you do not wish to receive further communications like this\, please`
    
   - `\<img height\="?1"? width\="?1"? sr\c=.?http\://`
    
   - `To stop receiving these+emails\:http\://`
    
   - `To unsubscribe from \w+ (e\-?letter|e?-?mail|newsletter)`
    
   - `no longer (wish )?(to )?(be sent|receive) w+ email`
    
   - `If you are unable to view the content of this email\, please click here`
    
   - `To ensure you receive (your daily deals|our e-?mails)\, add`
    
   - `If you no longer wish to receive these emails`
    
   - `to change your (subscription preferences|preferences or unsubscribe)`
    
   - `click (here to|the) unsubscribe`
    
   <span data-ttu-id="abed8-120">L'elenco di cui sopra non è un insieme esaustivo di espressioni regolari presenti nei messaggi di posta elettronica in blocco; Altre informazioni possono essere aggiunte o rimosse in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="abed8-120">The above list isn't an exhaustive set of regular expressions found in bulk emails; more can be added or removed as needed.</span></span> <span data-ttu-id="abed8-121">Tuttavia, si tratta di un buon punto di partenza.</span><span class="sxs-lookup"><span data-stu-id="abed8-121">However, it's a good starting point.</span></span><br><span data-ttu-id="abed8-122">La ricerca di parole o di modelli di testo nell'oggetto o in altri campi di intestazione del messaggio si verifica *dopo* la decodifica del messaggio dal metodo MIME Content Transfer Encoding utilizzato per la trasmissione del messaggio binario tra i server SMTP in testo ASCII.</span><span class="sxs-lookup"><span data-stu-id="abed8-122">The search for words or text patterns in the subject or other header fields in the message occurs  *after*  the message has been decoded from the MIME content transfer encoding method that was used to transmit the binary message between SMTP servers in ASCII text.</span></span> <span data-ttu-id="abed8-123">Non è possibile utilizzare condizioni o eccezioni per cercare i valori codificati non elaborati (in genere, Base64) dell'oggetto o di altri campi dell'intestazione dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="abed8-123">You can't use conditions or exceptions to search for the raw (typically, Base64) encoded values of the subject or other header fields in messages.</span></span> 
    
6. <span data-ttu-id="abed8-124">In **Fai quanto segue**, selezionare **Modifica le proprietà del messaggio** \> **Imposta il livello di probabilità di posta indesiderata**.</span><span class="sxs-lookup"><span data-stu-id="abed8-124">Under **Do the following**, select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span>
    
7. <span data-ttu-id="abed8-125">Nella finestra di dialogo **Specifica livello di probabilità di posta indesiderata**, impostare il valore SCL su **5**, **6** o **9**, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="abed8-125">In the **specify SCL** dialog box, set the SCL to **5**, **6**, or **9**, and click **ok**.</span></span>
    
   <span data-ttu-id="abed8-p107">L'impostazione di SCL su 5 o 6 consente di eseguire l'azione **Posta indesiderata**, mentre l'impostazione di SCL su 9 consente di effettuare l'azione **Alta probabilità di posta indesiderata**, come configurato nel criterio di filtro dei contenuti. Il servizio esegue l'azione impostata nel criterio di filtro dei contenuti. L'azione predefinita è quella di recapitare il messaggio nella cartella Posta indesiderata del destinatario, ma è possibile configurare azioni differenti, come descritto in [Configurare i criteri di filtro della posta indesiderata](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="abed8-p107">Setting the SCL to 5 or 6 takes the **Spam** action, while setting the SCL to 9 takes the **High confidence spam** action, as configured in the content filter policy. The service will perform the action set in the content filter policy. The default action is to deliver the message to the recipients' Junk Email folder, but different actions can be configured as described in [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>
    
   <span data-ttu-id="abed8-129">Se l'azione configurata è quella di mettere in quarantena il messaggio anziché inviarlo alla cartella posta indesiderata dei destinatari, il messaggio verrà inviato alla quarantena dell'amministratore come corrispondenza della regola del flusso di posta e non sarà disponibile nella quarantena della posta indesiderata dell'utente finale o tramite l'utente finale. notifiche di posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="abed8-129">If your configured action is to quarantine the message rather than send it to the recipients' Junk Email folder, the message will be sent to the administrator quarantine as a mail flow rule match, and it will not be available in the end user spam quarantine or via end-user spam notifications.</span></span> 
  
   <span data-ttu-id="abed8-130">Per ulteriori informazioni sui valori SCL del servizio, vedere [Livelli di sicurezza della protezione contro la posta indesiderata](spam-confidence-levels.md).</span><span class="sxs-lookup"><span data-stu-id="abed8-130">For more information about SCL values in the service, see [Spam confidence levels](spam-confidence-levels.md).</span></span>
    
8. <span data-ttu-id="abed8-131">Salvare la regola.</span><span class="sxs-lookup"><span data-stu-id="abed8-131">Save the rule.</span></span>
    
## <a name="create-a-mail-flow-rule-to-filter-bulk-email-messages-based-on-phrases"></a><span data-ttu-id="abed8-132">Creare una regola del flusso di posta per filtrare i messaggi di posta elettronica in blocco in base alle frasi</span><span class="sxs-lookup"><span data-stu-id="abed8-132">Create a mail flow rule to filter bulk email messages based on phrases</span></span>

1. <span data-ttu-id="abed8-133">Nell'interfaccia di amministrazione di Exchange, andare a **Flusso di posta** \> **Regole**.</span><span class="sxs-lookup"><span data-stu-id="abed8-133">In the EAC, go to **Mail flow** \> **Rules**.</span></span>
    
2. <span data-ttu-id="abed8-134">Fare \*\*\*\* ![clic su Aggiungi](../media/ITPro-EAC-AddIcon.gif) icona e quindi selezionare **Crea una nuova regola**.</span><span class="sxs-lookup"><span data-stu-id="abed8-134">Click **Add** ![Add Icon](../media/ITPro-EAC-AddIcon.gif) and then select **Create a new rule**.</span></span>
    
3. <span data-ttu-id="abed8-135">Specificare un nome per la regola.</span><span class="sxs-lookup"><span data-stu-id="abed8-135">Specify a name for the rule.</span></span>
    
4. <span data-ttu-id="abed8-136">Fare clic su **Altre opzioni**.</span><span class="sxs-lookup"><span data-stu-id="abed8-136">Click **More options**.</span></span> <span data-ttu-id="abed8-137">In **applica la regola se**, selezionare **l'** \> oggetto o il corpo del soggetto o **del corpo include una o più delle seguenti parole**.</span><span class="sxs-lookup"><span data-stu-id="abed8-137">Under **Apply this rule if**, select **The subject or body** \> **subject or body includes any of these words**.</span></span>
    
5. <span data-ttu-id="abed8-138">Nella finestra di dialogo **specificare parole o frasi**, aggiungere le seguenti frasi che si trovano di solito nei messaggi di posta elettronica in blocco, una per volta, e fare clic su **OK** al termine:</span><span class="sxs-lookup"><span data-stu-id="abed8-138">In the **specify words or phrases** dialog box, add the following phrases commonly found in bulk emails, one at a time, and click **ok** when you're done:</span></span> 
    
   - `to change your preferences or unsubscribe`
    
   - `Modify email preferences or unsubscribe`
    
   - `This is a promotional email`
    
   - `You are receiving this email because you requested a subscription`
    
   - `click here to unsubscribe`
    
   - `You have received this email because you are subscribed`
    
   - `If you no longer wish to receive our email newsletter`
    
   - `to unsubscribe from this newsletter`
    
   - `If you have trouble viewing this email`
    
   - `This is an advertisement`
    
   - `you would like to unsubscribe or change your`
    
   - `view this email as a webpage`
    
   - `You are receiving this email because you are subscribed`
    
   <span data-ttu-id="abed8-139">Questo elenco non è un insieme esaustivo di frasi trovate nei messaggi di posta elettronica in blocco; Altre informazioni possono essere aggiunte o rimosse in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="abed8-139">This list isn't an exhaustive set of phrases found in bulk emails; more can be added or removed as needed.</span></span> <span data-ttu-id="abed8-140">Tuttavia, si tratta di un buon punto di partenza.</span><span class="sxs-lookup"><span data-stu-id="abed8-140">However, it's a good starting point.</span></span>
    
6. <span data-ttu-id="abed8-141">In **Fai quanto segue**, selezionare **Modifica le proprietà del messaggio** \> **Imposta il livello di probabilità di posta indesiderata**.</span><span class="sxs-lookup"><span data-stu-id="abed8-141">Under **Do the following**, select **Modify the message properties** \> **set the spam confidence level (SCL)**.</span></span>
    
7. <span data-ttu-id="abed8-142">Nella finestra di dialogo **Specifica livello di probabilità di posta indesiderata**, impostare il valore SCL su **5**, **6** o **9**, quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="abed8-142">In the **specify SCL** dialog box, set the SCL to **5**, **6**, or **9**, and click **ok**.</span></span>
    
   <span data-ttu-id="abed8-p110">L'impostazione di SCL su 5 o 6 consente di eseguire l'azione **Posta indesiderata**, mentre l'impostazione di SCL su 9 consente di effettuare l'azione **Alta probabilità di posta indesiderata**, come configurato nel criterio di filtro dei contenuti. Il servizio esegue l'azione impostata nel criterio di filtro dei contenuti. L'azione predefinita è quella di recapitare il messaggio nella cartella Posta indesiderata del destinatario, ma è possibile configurare azioni differenti, come descritto in [Configurare i criteri di filtro della posta indesiderata](configure-your-spam-filter-policies.md).</span><span class="sxs-lookup"><span data-stu-id="abed8-p110">Setting the SCL to 5 or 6 takes the **Spam** action, while setting the SCL to 9 takes the **High confidence spam** action, as configured in the content filter policy. The service will perform the action set in the content filter policy. The default action is to deliver the message to the recipients' Junk Email folder, but different actions can be configured as described in [Configure your spam filter policies](configure-your-spam-filter-policies.md).</span></span>
    
   <span data-ttu-id="abed8-146">Se l'azione configurata è quella di mettere in quarantena il messaggio anziché inviarlo alla cartella posta indesiderata dei destinatari, il messaggio verrà inviato alla quarantena dell'amministratore come corrispondenza della regola del flusso di posta e non sarà disponibile nella quarantena della posta indesiderata dell'utente finale o tramite l'utente finale. notifiche di posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="abed8-146">If your configured action is to quarantine the message rather than send it to the recipients' Junk Email folder, the message will be sent to the administrator quarantine as a mail flow rule match, and it will not be available in the end user spam quarantine or via end-user spam notifications.</span></span> 
  
   <span data-ttu-id="abed8-147">Per ulteriori informazioni sui valori SCL del servizio, vedere [Livelli di sicurezza della protezione contro la posta indesiderata](spam-confidence-levels.md).</span><span class="sxs-lookup"><span data-stu-id="abed8-147">For more information about SCL values in the service, see [Spam confidence levels](spam-confidence-levels.md).</span></span>

8. <span data-ttu-id="abed8-148">Salvare la regola.</span><span class="sxs-lookup"><span data-stu-id="abed8-148">Save the rule.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="abed8-149">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="abed8-149">For more information</span></span>

[<span data-ttu-id="abed8-150">Differenza tra posta elettronica indesiderata e posta elettronica in blocco</span><span class="sxs-lookup"><span data-stu-id="abed8-150">What's the difference between junk email and bulk email?</span></span>](what-s-the-difference-between-junk-email-and-bulk-email.md)

[<span data-ttu-id="abed8-151">Valori di livello di reclamo in blocco</span><span class="sxs-lookup"><span data-stu-id="abed8-151">Bulk Complaint Level values</span></span>](bulk-complaint-level-values.md)

[<span data-ttu-id="abed8-152">Configurare i criteri di filtro della posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="abed8-152">Configure your spam filter policies</span></span>](configure-your-spam-filter-policies.md)

[<span data-ttu-id="abed8-153">Opzioni di filtro della posta indesiderata avanzate</span><span class="sxs-lookup"><span data-stu-id="abed8-153">Advanced spam filtering  options</span></span>](advanced-spam-filtering-asf-options.md)
