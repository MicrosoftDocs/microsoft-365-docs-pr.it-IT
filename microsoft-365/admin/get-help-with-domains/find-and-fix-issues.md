---
title: Individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 40398b0b-bdd0-4afd-ab5e-b5ae6b7990bf
description: Informazioni su come individuare i problemi che si sono verificati durante la configurazione di un dominio personalizzato assicurandosi che i record DNS siano configurati correttamente.
ms.openlocfilehash: 0a315be243395940146479e05de2c7044a5a36ab
ms.sourcegitcommit: d988faa292c2661ffea43c7161aef92b2b4b99bc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "46560252"
---
# <a name="find-and-fix-issues-after-adding-your-domain-or-dns-records"></a><span data-ttu-id="a752f-103">Individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS</span><span class="sxs-lookup"><span data-stu-id="a752f-103">Find and fix issues after adding your domain or DNS records</span></span>

 <span data-ttu-id="a752f-104">Se non si trova ciò che si sta cercando, **[vedere le domande frequenti sui domini](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="a752f-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="a752f-105">Ottenere il dominio configurato per l'uso con Microsoft 365 può essere difficile.</span><span class="sxs-lookup"><span data-stu-id="a752f-105">Getting your domain set up to work with Microsoft 365 can be challenging.</span></span> <span data-ttu-id="a752f-106">Il sistema DNS non è facile da usare e la configurazione del DNS per il dominio influisce su attività aziendali importanti, come la posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="a752f-106">The DNS system is nitpicky to work with, and the DNS setup for your domain affects important business activities, like email!</span></span>

> [!NOTE]
> <span data-ttu-id="a752f-107">È possibile verificare se si verificano problemi con il dominio verificando il relativo stato.</span><span class="sxs-lookup"><span data-stu-id="a752f-107">You can check for problems with your domain by checking its status.</span></span> <span data-ttu-id="a752f-108">Accedere a **Setup**  >  **domini** di installazione e visualizzare le notifiche nella colonna **stato** .</span><span class="sxs-lookup"><span data-stu-id="a752f-108">Go to **Setup** > **Domains** and view the notifications in the **Status** column.</span></span> <span data-ttu-id="a752f-109">Se viene visualizzato un problema, selezionare altre azioni (tre punti) e quindi fare clic su **Controlla integrità**.</span><span class="sxs-lookup"><span data-stu-id="a752f-109">If you see an issue, select More actions (three dots), and then choose **Check health**.</span></span> <span data-ttu-id="a752f-110">Il riquadro che si apre descriverà tutti i problemi che si verificano con il dominio.</span><span class="sxs-lookup"><span data-stu-id="a752f-110">The pane that opens will describe any issues occurring with your domain.</span></span>
  
## <a name="whats-going-on"></a><span data-ttu-id="a752f-111">Per quale motivo?</span><span class="sxs-lookup"><span data-stu-id="a752f-111">What's going on?</span></span>

- [<span data-ttu-id="a752f-112">Non è possibile verificare il dominio?</span><span class="sxs-lookup"><span data-stu-id="a752f-112">Can't verify your domain?</span></span>](#cant-verify-your-domain)
    
- [<span data-ttu-id="a752f-113">Outlook non funziona?</span><span class="sxs-lookup"><span data-stu-id="a752f-113">Outlook isn't working?</span></span>](#outlook-isnt-working)
    
- [<span data-ttu-id="a752f-114">LA posta elettronica di tutti è stata commutata in Microsoft 365 e si voleva solo che la posta elettronica cambiasse?</span><span class="sxs-lookup"><span data-stu-id="a752f-114">Everyone's email got switched to Microsoft 365 and you only wanted YOUR email to switch?</span></span>](#everyones-email-got-switched-to-microsoft-365-and-you-only-wanted-your-email-to-switch)

- [<span data-ttu-id="a752f-115">Non è possibile verificare lo stato di un account non profit o School?</span><span class="sxs-lookup"><span data-stu-id="a752f-115">Can't confirm non-profit or school account status?</span></span>](#cant-confirm-non-profit-or-school-account-status)

- [<span data-ttu-id="a752f-116">Servizi che non utilizzano il dominio?</span><span class="sxs-lookup"><span data-stu-id="a752f-116">Services not working with your domain?</span></span>](#services-not-working-with-your-domain)
    
- [<span data-ttu-id="a752f-117">L'accesso al sito Web non funziona?</span><span class="sxs-lookup"><span data-stu-id="a752f-117">Accessing your website isn't working?</span></span>](#accessing-your-website-isnt-working)

## <a name="cant-verify-your-domain"></a><span data-ttu-id="a752f-118">Non si riesce a verificare il dominio?</span><span class="sxs-lookup"><span data-stu-id="a752f-118">Can't verify your domain?</span></span>
<span data-ttu-id="a752f-119"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="a752f-119"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="a752f-120">La verifica del dominio potrebbe non funzionare in alcuni scenari comuni:</span><span class="sxs-lookup"><span data-stu-id="a752f-120">There are a couple of common reasons that domain verification doesn't work as it should:</span></span>
  
1. <span data-ttu-id="a752f-p103">**Il valore del record di verifica non è corretto.** Controllare di aver copiato e incollato il valore esatto nel record di verifica TXT presso l'host DNS. Un problema comune è l'omissione della parte "MS =" del record, che invece è necessaria.</span><span class="sxs-lookup"><span data-stu-id="a752f-p103">**The verification record value isn't quite correct.** Doublecheck that you've copied and pasted the exact value into the TXT verification record at your DNS host. One common issue is not including the "MS=" part of the record. We need that too!</span></span> 
    
2. <span data-ttu-id="a752f-125">**Il record non è stato salvato.**</span><span class="sxs-lookup"><span data-stu-id="a752f-125">**The record hasn't been saved.**</span></span> <span data-ttu-id="a752f-126">Presso alcuni host DNS è necessario eseguire un ulteriore passaggio per salvare il file di zona (in cui è archiviato il record DNS) in modo che venga aggiornato su Internet.</span><span class="sxs-lookup"><span data-stu-id="a752f-126">At some DNS hosts, you have to take an extra step to save the zone file (where the DNS record is stored) so that it will update across the Internet.</span></span> <span data-ttu-id="a752f-127">Assicurarsi di aver salvato le modifiche in modo che Microsoft 365 possa visualizzare e verificare il record.</span><span class="sxs-lookup"><span data-stu-id="a752f-127">Make sure you've saved your changes so Microsoft 365 can see and verify the record.</span></span> 
    
3. <span data-ttu-id="a752f-128">**Il record non è stato aggiornato su Internet.**</span><span class="sxs-lookup"><span data-stu-id="a752f-128">**The record hasn't updated across the Internet.**</span></span> <span data-ttu-id="a752f-129">In genere, è necessario solo qualche minuto perché sia possibile visualizzare il nuovo record, ma a volte può richiedere fino a poche ore.</span><span class="sxs-lookup"><span data-stu-id="a752f-129">It typically only takes a few minutes for us to be able to see the new record, but occasionally it can take as long as a few hours.</span></span> 
    
## <a name="outlook-isnt-working"></a><span data-ttu-id="a752f-130">Outlook non funziona?</span><span class="sxs-lookup"><span data-stu-id="a752f-130">Outlook isn't working?</span></span>
<span data-ttu-id="a752f-131"><a name="BKMK_OutlookBroken"> </a></span><span class="sxs-lookup"><span data-stu-id="a752f-131"><a name="BKMK_OutlookBroken"> </a></span></span>

<span data-ttu-id="a752f-132">Se la configurazione del record MX e di altri record DNS per il dominio è stata eseguita correttamente ma la posta elettronica non funziona, contattare il supporto per la [risoluzione dei problemi di Outlook](https://docs.microsoft.com/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues).</span><span class="sxs-lookup"><span data-stu-id="a752f-132">If you've set up your MX record and other DNS records correctly for your domain, but mail doesn't work, let us help you [fix your Outlook problems](https://docs.microsoft.com/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues).</span></span>
  
## <a name="everyones-email-got-switched-to-microsoft-365-and-you-only-wanted-your-email-to-switch"></a><span data-ttu-id="a752f-133">LA posta elettronica di tutti è stata commutata in Microsoft 365 e si voleva solo che la posta elettronica cambiasse?</span><span class="sxs-lookup"><span data-stu-id="a752f-133">Everyone's email got switched to Microsoft 365 and you only wanted YOUR email to switch?</span></span>
<span data-ttu-id="a752f-134"><a name="BKMK_EmailSwitched"> </a></span><span class="sxs-lookup"><span data-stu-id="a752f-134"><a name="BKMK_EmailSwitched"> </a></span></span>

<span data-ttu-id="a752f-135">Quando si aggiunge il dominio a Microsoft 365, in genere il record MX del dominio viene aggiornato (dall'utente o da Microsoft 365) per puntare a Microsoft 365 e tutti i messaggi di posta elettronica inviati a tale dominio inizieranno a essere Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a752f-135">When you add your domain to Microsoft 365, typically your domain's MX record is updated (by you or Microsoft 365) to point to Microsoft 365, and ALL email sent to that domain will start coming to Microsoft 365.</span></span> <span data-ttu-id="a752f-136">Assicurarsi di aver creato le cassette postali in Microsoft 365 per tutti gli utenti che hanno un messaggio di posta elettronica nel dominio prima di modificare il record MX.</span><span class="sxs-lookup"><span data-stu-id="a752f-136">Make sure you've created mailboxes in Microsoft 365 for everyone who has email on your domain BEFORE you change the MX record.</span></span>
  
<span data-ttu-id="a752f-137">Che cosa fare se non si desidera spostare la posta elettronica per tutti gli utenti del dominio in Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="a752f-137">What if you don't want to move email for everyone on your domain to Microsoft 365?</span></span> <span data-ttu-id="a752f-138">È possibile eseguire la procedura per [pilotare Microsoft 365 con solo alcuni indirizzi di posta elettronica](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq).</span><span class="sxs-lookup"><span data-stu-id="a752f-138">You can take steps to [pilot Microsoft 365 with just a few email addresses instead](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq).</span></span>
  
## <a name="cant-confirm-non-profit-or-school-account-status"></a><span data-ttu-id="a752f-139">Non è possibile verificare lo stato di un account non profit o School?</span><span class="sxs-lookup"><span data-stu-id="a752f-139">Can't confirm non-profit or school account status?</span></span>
<span data-ttu-id="a752f-140"><a name="BKMK_validateAcct"> </a></span><span class="sxs-lookup"><span data-stu-id="a752f-140"><a name="BKMK_validateAcct"> </a></span></span>

<span data-ttu-id="a752f-141">Esistono due scenari in cui è solo necessario verificare il dominio dell'organizzazione e non configurare i servizi.</span><span class="sxs-lookup"><span data-stu-id="a752f-141">There are a couple of scenarios when you just need to verify your organization's domain and not set up any services.</span></span> <span data-ttu-id="a752f-142">Ad esempio, per dimostrare a Microsoft 365 che l'organizzazione è qualificata per un abbonamento scolastico.</span><span class="sxs-lookup"><span data-stu-id="a752f-142">For example, to prove to Microsoft 365 that your organization qualifies for a school subscription.</span></span>
  
<span data-ttu-id="a752f-143">Consultare le linee guida per [verificare il dominio Microsoft 365 per dimostrare la proprietà, l'organizzazione no profit o l'istruzione o per attivare Yammer](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) per assicurarsi di aver completato tutti i passaggi necessari.</span><span class="sxs-lookup"><span data-stu-id="a752f-143">Check out the guidance in [Verify your Microsoft 365 domain to prove ownership, nonprofit or education status, or to activate Yammer](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) to make sure you've completed all the required steps.</span></span> <span data-ttu-id="a752f-144">Si tratta di un po' diverso per ogni situazione.</span><span class="sxs-lookup"><span data-stu-id="a752f-144">It's a little different for each situation.</span></span> 
  
## <a name="services-not-working-with-your-domain"></a><span data-ttu-id="a752f-145">I servizi non funzionano con il proprio dominio?</span><span class="sxs-lookup"><span data-stu-id="a752f-145">Services not working with your domain?</span></span>
<span data-ttu-id="a752f-146"><a name="BKMK_Test"> </a></span><span class="sxs-lookup"><span data-stu-id="a752f-146"><a name="BKMK_Test"> </a></span></span>

<span data-ttu-id="a752f-147">Sono disponibili strumenti e informazioni per individuare i problemi relativi alla configurazione del DNS del dominio.</span><span class="sxs-lookup"><span data-stu-id="a752f-147">We can help you track down issues with your domain's DNS setup.</span></span> <span data-ttu-id="a752f-148">La risoluzione dei problemi relativi ai domini in Microsoft 365 mostrerà gli eventuali record che devono essere fissati e gli elementi di cui è necessario impostare i record.</span><span class="sxs-lookup"><span data-stu-id="a752f-148">The domains troubleshooter in Microsoft 365 will show you any records that need fixing, and exactly what the records need to be set to.</span></span> 

> [!TIP]
> <span data-ttu-id="a752f-149">Il DNS è configurato correttamente ma la posta elettronica non funziona in Outlook sul desktop?</span><span class="sxs-lookup"><span data-stu-id="a752f-149">Got your DNS set up correctly, but mail doesn't work in Outlook on your desktop?</span></span> <span data-ttu-id="a752f-150">Consultare i [diversi scenari del flusso di posta che è possibile avere con Microsoft 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/mail-flow-best-practices) per assicurarsi che siano configurati correttamente per la propria azienda.</span><span class="sxs-lookup"><span data-stu-id="a752f-150">Check out the [different mail flow scenarios you can have with Microsoft 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/mail-flow-best-practices) to make sure you've got things set up correctly for your business.</span></span> <span data-ttu-id="a752f-151">Oppure, per altre informazioni sulla risoluzione dei problemi di posta, vedere [Risolvere i problemi di Outlook](https://docs.microsoft.com/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues).</span><span class="sxs-lookup"><span data-stu-id="a752f-151">Or get more troubleshooting help with email here: [Fix Outlook problems](https://docs.microsoft.com/exchange/troubleshoot/outlook-connectivity/outlook-connection-issues).</span></span> 
  
## <a name="accessing-your-website-isnt-working"></a><span data-ttu-id="a752f-152">L'accesso al sito Web non funziona?</span><span class="sxs-lookup"><span data-stu-id="a752f-152">Accessing your website isn't working?</span></span>
<span data-ttu-id="a752f-153"><a name="BKMK_Website"> </a></span><span class="sxs-lookup"><span data-stu-id="a752f-153"><a name="BKMK_Website"> </a></span></span>

<span data-ttu-id="a752f-154">Se gli errori del DNS sono stati corretti ma si verificano ancora problemi, provare una della soluzioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="a752f-154">If you've fixed any DNS issues and you're still having trouble, try one of the following.</span></span>
  
- <span data-ttu-id="a752f-155">Le persone non riescono ad accedere al sito Web all'indirizzo www.mydomain.com: [Risolvere i problemi relativi al sito Web](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)</span><span class="sxs-lookup"><span data-stu-id="a752f-155">People can't get to your website at www.mydomain.com: [Track down website issues](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)</span></span>
    
- <span data-ttu-id="a752f-156">Non è possibile aggiornare il record a record o CNAME in modo che punti al sito Web: [aggiornare i record DNS personalizzati in Microsoft 365](../dns/add-or-edit-custom-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="a752f-156">You can't update your A record or CNAME record to point to your website: [Update custom DNS records in Microsoft 365](../dns/add-or-edit-custom-dns-records.md)</span></span>
    
