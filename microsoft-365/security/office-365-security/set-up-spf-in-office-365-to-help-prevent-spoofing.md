---
title: Configurazione di SPF per evitare lo spoofing
f1.keywords:
- CSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/21/2019
audience: ITPro
ms.topic: how-to
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 71373291-83d2-466f-86ea-fc61493743a6
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Informazioni su come aggiornare un record DNS (Domain Name Service) per usare un Sender Policy Framework (SPF) con il dominio personalizzato in Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1d200c4cf17a3d42ddafca301fecbf18c249ac37
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245685"
---
# <a name="set-up-spf-to-help-prevent-spoofing"></a><span data-ttu-id="ea189-103">Configurazione di SPF per evitare lo spoofing</span><span class="sxs-lookup"><span data-stu-id="ea189-103">Set up SPF to help prevent spoofing</span></span>

- [<span data-ttu-id="ea189-104">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="ea189-104">Prerequisites</span></span>](#prerequisites)
- [<span data-ttu-id="ea189-105">Creare o aggiornare il record TXT SPF</span><span class="sxs-lookup"><span data-stu-id="ea189-105">Create or update your SPF TXT record</span></span>](#create-or-update-your-spf-txt-record)
- [<span data-ttu-id="ea189-106">Come gestire i sottodomini</span><span class="sxs-lookup"><span data-stu-id="ea189-106">How to handle subdomains?</span></span>](#how-to-handle-subdomains)
- [<span data-ttu-id="ea189-107">Risoluzione dei problemi relativi a SPF</span><span class="sxs-lookup"><span data-stu-id="ea189-107">Troubleshooting SPF</span></span>](#troubleshooting-spf)

<!--
[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Applies to**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 plan 1 and plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)
-->

<span data-ttu-id="ea189-108">In questo articolo viene descritto come aggiornare un record DNS (Domain Name Service) affinché sia possibile utilizzare l'autenticazione della posta elettronica di Sender Policy Framework (SPF) con il dominio personalizzato in Office 365.</span><span class="sxs-lookup"><span data-stu-id="ea189-108">This article describes how to update a Domain Name Service (DNS) record so that you can use Sender Policy Framework (SPF)  email authentication with your custom domain in Office 365.</span></span>

<span data-ttu-id="ea189-109">SPF consente di *convalidare* la posta elettronica in uscita inviata dal dominio personalizzato (proviene da chi dice di essere).</span><span class="sxs-lookup"><span data-stu-id="ea189-109">SPF helps *validate* outbound email sent from your custom domain (is coming from who it says it is).</span></span> <span data-ttu-id="ea189-110">Si tratta di un primo passaggio per configurare i metodi di autenticazione della posta elettronica consigliati completi di SPF, [DKIM](use-dkim-to-validate-outbound-email.md) e [DMARC](use-dmarc-to-validate-email.md).</span><span class="sxs-lookup"><span data-stu-id="ea189-110">It's a first step in setting up the full recommended email authentication methods of SPF, [DKIM](use-dkim-to-validate-outbound-email.md), and [DMARC](use-dmarc-to-validate-email.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ea189-111">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="ea189-111">Prerequisites</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ea189-112">Si consiglia alle **piccole imprese** e agli utenti che non hanno familiarità con gli indirizzi IP o la configurazione DNS di contattare il proprio gestore di domini internet (p. es.</span><span class="sxs-lookup"><span data-stu-id="ea189-112">If you are a **small business**, or are unfamiliar with IP addresses or DNS configuration, call your Internet domain registrar (ex.</span></span> <span data-ttu-id="ea189-113">GoDaddy, Bluehost, web.com), per ottenere assistenza con la *configurazione DNS di SPF* (e qualsiasi altro metodo di autenticazione della posta elettronica usato).</span><span class="sxs-lookup"><span data-stu-id="ea189-113">GoDaddy, Bluehost, web.com) & ask for help with *DNS configuration of SPF* (and any other email authentication method).</span></span> <p> <span data-ttu-id="ea189-114">**Se non si usa un URL personalizzato** (e l'URL usato per Office 365 termina con **onmicrosoft.com**), SPF è già stato configurato nel servizio Office 365.</span><span class="sxs-lookup"><span data-stu-id="ea189-114">**If you don't use a custom URL** (and the URL used for Office 365 ends in **onmicrosoft.com**), SPF has already been set up for you in the Office 365 service.</span></span>

<span data-ttu-id="ea189-115">Iniziamo.</span><span class="sxs-lookup"><span data-stu-id="ea189-115">Let's get started.</span></span>

<span data-ttu-id="ea189-116">Il record TXT SPF per Office 365 verrà creato nel DNS esterno per qualsiasi dominio o sottodominio personalizzato.</span><span class="sxs-lookup"><span data-stu-id="ea189-116">The SPF TXT record for Office 365 will be made in external DNS for any custom domains or subdomains.</span></span> <span data-ttu-id="ea189-117">Sono necessarie alcune informazioni per creare il record.</span><span class="sxs-lookup"><span data-stu-id="ea189-117">You need some information to make the record.</span></span> <span data-ttu-id="ea189-118">Raccogliere le seguenti informazioni:</span><span class="sxs-lookup"><span data-stu-id="ea189-118">Gather this information:</span></span>

- <span data-ttu-id="ea189-119">Il record TXT SPF per il proprio dominio personalizzato, se disponibile.</span><span class="sxs-lookup"><span data-stu-id="ea189-119">The SPF TXT record for your custom domain, if one exists.</span></span> <span data-ttu-id="ea189-120">Per le istruzioni, vedere [Raccogliere le informazioni necessarie per creare record DNS di Office 365](../../admin/get-help-with-domains/information-for-dns-records.md).</span><span class="sxs-lookup"><span data-stu-id="ea189-120">For instructions, see [Gather the information you need to create Office 365 DNS records](../../admin/get-help-with-domains/information-for-dns-records.md).</span></span>

- <span data-ttu-id="ea189-121">Passare ai server di messaggistica e individuare gli indirizzi IP esterni (necessari per tutti i server locali di messaggistica).</span><span class="sxs-lookup"><span data-stu-id="ea189-121">Go to your messaging server(s) and find out the External IP addresses (needed from all on-premises messaging servers).</span></span> <span data-ttu-id="ea189-122">Ad esempio, **131.107.2.200**.</span><span class="sxs-lookup"><span data-stu-id="ea189-122">For example, **131.107.2.200**.</span></span>

- <span data-ttu-id="ea189-p106">Nomi di dominio da utilizzare per tutti i domini di terze parti che è necessario includere nel record TXT SPF. In alcuni provider di posta inviata in massa sono impostati sottodomini da utilizzare per i clienti. Ad esempio, la società MailChimp ha configurato **servers.mcsv.net**.</span><span class="sxs-lookup"><span data-stu-id="ea189-p106">Domain names to use for all third-party domains that you need to include in your SPF TXT record. Some bulk mail providers have set up subdomains to use for their customers. For example, the company MailChimp has set up **servers.mcsv.net**.</span></span>

- <span data-ttu-id="ea189-126">Stabilire quale regola di imposizione utilizzare per il record TXT SPF.</span><span class="sxs-lookup"><span data-stu-id="ea189-126">Figure out what enforcement rule you want to use for your SPF TXT record.</span></span> <span data-ttu-id="ea189-127">La regola **-all** è raccomandata.</span><span class="sxs-lookup"><span data-stu-id="ea189-127">The **-all** rule is recommended.</span></span> <span data-ttu-id="ea189-128">Per informazioni dettagliate sulle altre opzioni di sintassi, vedere [Sintassi del record TXT SPF per Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#SPFSyntaxO365).</span><span class="sxs-lookup"><span data-stu-id="ea189-128">For detailed information about other syntax options, see [SPF TXT record syntax for Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#SPFSyntaxO365).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ea189-129">Per utilizzare un dominio personalizzato, Office 365 richiede l'aggiunta di un record TXT Sender Policy Framework (SPF) al record DNS per prevenire spoofing.</span><span class="sxs-lookup"><span data-stu-id="ea189-129">In order to use a custom domain, Office 365 requires that you add a Sender Policy Framework (SPF) TXT record to your DNS record to help prevent spoofing.</span></span>

## <a name="create-or-update-your-spf-txt-record"></a><span data-ttu-id="ea189-130">Creare o aggiornare il record TXT SPF</span><span class="sxs-lookup"><span data-stu-id="ea189-130">Create or update your SPF TXT record</span></span>

1. <span data-ttu-id="ea189-131">Assicurarsi di avere familiarità con la sintassi SFP nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="ea189-131">Ensure that you're familiar with the SPF syntax in the following table.</span></span>

   ****

   |<span data-ttu-id="ea189-132">Elemento</span><span class="sxs-lookup"><span data-stu-id="ea189-132">Element</span></span>|<span data-ttu-id="ea189-133">Se si sta utilizzando...</span><span class="sxs-lookup"><span data-stu-id="ea189-133">If you're using...</span></span>|<span data-ttu-id="ea189-134">Comune per i clienti?</span><span class="sxs-lookup"><span data-stu-id="ea189-134">Common for customers?</span></span>|<span data-ttu-id="ea189-135">Aggiungere...</span><span class="sxs-lookup"><span data-stu-id="ea189-135">Add this...</span></span>|
   |---|---|---|---|
   |<span data-ttu-id="ea189-136">1</span><span class="sxs-lookup"><span data-stu-id="ea189-136">1</span></span>|<span data-ttu-id="ea189-137">Qualsiasi sistema di posta elettronica (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="ea189-137">Any email system (required)</span></span>|<span data-ttu-id="ea189-p108">Comune. Tutti i record TXT SPF devono iniziare con questo valore</span><span class="sxs-lookup"><span data-stu-id="ea189-p108">Common. All SPF TXT records start with this value</span></span>|`v=spf1`|
   |<span data-ttu-id="ea189-140">2</span><span class="sxs-lookup"><span data-stu-id="ea189-140">2</span></span>|<span data-ttu-id="ea189-141">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="ea189-141">Exchange Online</span></span>|<span data-ttu-id="ea189-142">Comune</span><span class="sxs-lookup"><span data-stu-id="ea189-142">Common</span></span>|`include:spf.protection.outlook.com`|
   |<span data-ttu-id="ea189-143">3</span><span class="sxs-lookup"><span data-stu-id="ea189-143">3</span></span>|<span data-ttu-id="ea189-144">Solo per Exchange Online</span><span class="sxs-lookup"><span data-stu-id="ea189-144">Exchange Online dedicated only</span></span>|<span data-ttu-id="ea189-145">Non comune</span><span class="sxs-lookup"><span data-stu-id="ea189-145">Not common</span></span>|`ip4:23.103.224.0/19` <br> `ip4:206.191.224.0/19` <br> `ip4:40.103.0.0/16` <br> `include:spf.protection.outlook.com`|
   |<span data-ttu-id="ea189-146">4</span><span class="sxs-lookup"><span data-stu-id="ea189-146">4</span></span>|<span data-ttu-id="ea189-147">Office 365 Germania, solo Microsoft Cloud Germania</span><span class="sxs-lookup"><span data-stu-id="ea189-147">Office 365 Germany, Microsoft Cloud Germany only</span></span>|<span data-ttu-id="ea189-148">Non comune</span><span class="sxs-lookup"><span data-stu-id="ea189-148">Not common</span></span>|`include:spf.protection.outlook.de`|
   |<span data-ttu-id="ea189-149">5</span><span class="sxs-lookup"><span data-stu-id="ea189-149">5</span></span>|<span data-ttu-id="ea189-150">Un sistema di posta elettronica di terze parti</span><span class="sxs-lookup"><span data-stu-id="ea189-150">Third-party email system</span></span>|<span data-ttu-id="ea189-151">Non comune</span><span class="sxs-lookup"><span data-stu-id="ea189-151">Not common</span></span>|`include:<domain_name>` <p> <span data-ttu-id="ea189-152">\<domain_name\> è il dominio del sistema di posta elettronica di terze parti.</span><span class="sxs-lookup"><span data-stu-id="ea189-152">\<domain_name\> is the domain of the third-party email system.</span></span>|
   |<span data-ttu-id="ea189-153">6</span><span class="sxs-lookup"><span data-stu-id="ea189-153">6</span></span>|<span data-ttu-id="ea189-p109">Sistema di posta locale. Ad esempio, di Exchange Online Protection insieme a un altro sistema di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="ea189-p109">On-premises email system. For example, Exchange Online Protection plus another email system</span></span>|<span data-ttu-id="ea189-156">Non comune</span><span class="sxs-lookup"><span data-stu-id="ea189-156">Not common</span></span>|<span data-ttu-id="ea189-157">Utilizzarne uno per ogni sistema di posta elettronica aggiuntivo:</span><span class="sxs-lookup"><span data-stu-id="ea189-157">Use one of these for each additional mail system:</span></span> <p> `ip4:<IP_address>` <br> `ip6:<IP_address>` <br> `include:<domain_name>` <p> <span data-ttu-id="ea189-158">\<IP_address\> e \<domain_name\> sono l'indirizzo IP e il dominio dell'altro sistema di posta che invia i messaggi per conto del dominio.</span><span class="sxs-lookup"><span data-stu-id="ea189-158">\<IP_address\> and \<domain_name\> are the IP address and domain of the other email system that sends mail on behalf of your domain.</span></span>|
   |<span data-ttu-id="ea189-159">7</span><span class="sxs-lookup"><span data-stu-id="ea189-159">7</span></span>|<span data-ttu-id="ea189-160">Qualsiasi sistema di posta elettronica (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="ea189-160">Any email system (required)</span></span>|<span data-ttu-id="ea189-p110">Comune. Tutti i record TXT SPF finiscono con questo valore</span><span class="sxs-lookup"><span data-stu-id="ea189-p110">Common. All SPF TXT records end with this value</span></span>|`<enforcement rule>` <p> <span data-ttu-id="ea189-163">Può trattarsi di uno dei vari valori.</span><span class="sxs-lookup"><span data-stu-id="ea189-163">This can be one of several values.</span></span> <span data-ttu-id="ea189-164">Consigliamo il valore `-all`.</span><span class="sxs-lookup"><span data-stu-id="ea189-164">We recommend the value `-all`.</span></span>|
   |

2. <span data-ttu-id="ea189-165">Se non è già stato fatto, costituire il record TXT SPF utilizzando la sintassi della tabella.</span><span class="sxs-lookup"><span data-stu-id="ea189-165">If you haven't already done so, form your SPF TXT record by using the syntax from the table.</span></span>

   <span data-ttu-id="ea189-166">Ad esempio, se l'utente è completamente ospitato in Office 365, che significa che non sono presenti server di posta elettronica locali, il record TXT SPF includerà le righe 1, 2 e 7 e si otterrà un risultato simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="ea189-166">For example, if you are hosted entirely in Office 365, that is, you have no on-premises mail servers, your SPF TXT record would include rows 1, 2, and 7 and would look like this:</span></span>

   ```text
   v=spf1 include:spf.protection.outlook.com -all
   ```

   <span data-ttu-id="ea189-167">**L'esempio precedente è il record TXT SPF più comune**.</span><span class="sxs-lookup"><span data-stu-id="ea189-167">**The example above is the most common SPF TXT record**.</span></span> <span data-ttu-id="ea189-168">Questo record funziona praticamente per tutti, indipendentemente dal fatto che il datacenter di Microsoft si trovi negli Stati Uniti, in Europa (Germania inclusa) o in un'altra area geografica.</span><span class="sxs-lookup"><span data-stu-id="ea189-168">This record works for just about everyone, regardless of whether your Microsoft datacenter is located in the United States, or in Europe (including Germany), or in another location.</span></span>

   <span data-ttu-id="ea189-p113">Tuttavia, se è stato acquistato Office 365 Germania, parte di Microsoft Cloud Germania, è necessario utilizzare l'istruzione inclusa dalla riga 4 anziché dalla riga 2. Ad esempio, se l'utente è completamente ospitato in Office 365 Germania, che significa che non sono presenti server di posta elettronica locali, il record TXT SPF includerà le righe 1, 4 e 7 e si otterrà un risultato simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="ea189-p113">However, if you bought Office 365 Germany, part of Microsoft Cloud Germany, you should use the include statement from line 4 instead of line 2. For example, if you are hosted entirely in Office 365 Germany, that is, you have no on-premises mail servers, your SPF TXT record would include rows 1, 4, and 7 and would look like this:</span></span>

   ```text
   v=spf1 include:spf.protection.outlook.de -all
   ```

   <span data-ttu-id="ea189-171">Se l'utente è già distribuito in Office 365, dispone di record TXT SPF configurati per il dominio personalizzato e sta eseguendo la migrazione a Office 365 Germania, è necessario aggiornare il record TXT SPF.</span><span class="sxs-lookup"><span data-stu-id="ea189-171">If you're already deployed in Office 365 and have set up your SPF TXT records for your custom domain, and you're migrating to Office 365 Germany, you need to update your SPF TXT record.</span></span> <span data-ttu-id="ea189-172">Per farlo, cambiare `include:spf.protection.outlook.com` in `include:spf.protection.outlook.de`.</span><span class="sxs-lookup"><span data-stu-id="ea189-172">To do this, change `include:spf.protection.outlook.com` to `include:spf.protection.outlook.de`.</span></span>

3. <span data-ttu-id="ea189-173">Dopo aver creato il record TXT SPF, è necessario aggiornare il record in DNS.</span><span class="sxs-lookup"><span data-stu-id="ea189-173">Once you have formed your SPF TXT record, you need to update the record in DNS.</span></span> <span data-ttu-id="ea189-174">**È possibile avere un solo record TXT SPF per un dominio.**</span><span class="sxs-lookup"><span data-stu-id="ea189-174">**You can only have one SPF TXT record for a domain.**</span></span> <span data-ttu-id="ea189-175">Se esiste un record TXT SPF, anziché aggiungere un nuovo record, è necessario aggiornare quello esistente.</span><span class="sxs-lookup"><span data-stu-id="ea189-175">If an SPF TXT record exists, instead of adding a new record, you need to update the existing record.</span></span> <span data-ttu-id="ea189-176">Passare a [Creare record DNS per Office 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md) e quindi selezionare il collegamento relativo al proprio host DNS.</span><span class="sxs-lookup"><span data-stu-id="ea189-176">Go to [Create DNS records for Office 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md), and then select the link for your DNS host.</span></span>

4. <span data-ttu-id="ea189-177">Verificare il record TXT SPF.</span><span class="sxs-lookup"><span data-stu-id="ea189-177">Test your SPF TXT record.</span></span>

## <a name="how-to-handle-subdomains"></a><span data-ttu-id="ea189-178">Come gestire i sottodomini</span><span class="sxs-lookup"><span data-stu-id="ea189-178">How to handle subdomains?</span></span>

<span data-ttu-id="ea189-179">È importante tenere presente che *è necessario creare un record distinto per ogni sottodominio, in quanto i sottodomini non ereditano il record SPF del dominio di primo livello*.</span><span class="sxs-lookup"><span data-stu-id="ea189-179">It's important to note that *you need to create a separate record for each subdomain as subdomains don't inherit the SPF record of their top-level domain*.</span></span>

<span data-ttu-id="ea189-180">Per tutti i domini e sottodomini è necessario un record SPF jolly (`*.`) per impedire agli utenti malintenzionati di inviare messaggi di posta elettronica che provengano da sottodomini inesistenti.</span><span class="sxs-lookup"><span data-stu-id="ea189-180">A wildcard SPF record (`*.`) is required for every domain and subdomain to prevent attackers from sending email claiming to be from non-existent subdomains.</span></span> <span data-ttu-id="ea189-181">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="ea189-181">For example:</span></span>

```text
*.subdomain.contoso.com. IN TXT "v=spf1 -all"
```

## <a name="troubleshooting-spf"></a><span data-ttu-id="ea189-182">Risoluzione dei problemi relativi a SPF</span><span class="sxs-lookup"><span data-stu-id="ea189-182">Troubleshooting SPF</span></span>

<span data-ttu-id="ea189-p117">Se si hanno problemi con il record TXT SPF, vedere [Risoluzione dei problemi: procedure consigliate per SPF in Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#SPFTroubleshoot).</span><span class="sxs-lookup"><span data-stu-id="ea189-p117">Having trouble with your SPF TXT record? Read [Troubleshooting: Best practices for SPF in Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#SPFTroubleshoot).</span></span>


## <a name="what-does-spf-email-authentication-actually-do"></a><span data-ttu-id="ea189-185">Cosa fa effettivamente l'autenticazione SPF della posta elettronica?</span><span class="sxs-lookup"><span data-stu-id="ea189-185">What does SPF email authentication actually do?</span></span>

<span data-ttu-id="ea189-p118">SPF identifica quali server di posta elettronica sono autorizzati a inviare posta elettronica per conto dell'utente. In sostanza, SPF insieme a DKIM, DMARC e altre tecnologie supportate da Office 365 aiuta a prevenire spoofing e phishing. SPF viene aggiunto come un record TXT che viene utilizzato da DNS per identificare i server di posta elettronica che possono inviare posta elettronica per conto di un dominio personalizzato. I sistemi di posta elettronica del destinatario fanno riferimento al record TXT SPF per stabilire se un messaggio di un dominio personalizzato proviene da un server di messaggistica autorizzato.</span><span class="sxs-lookup"><span data-stu-id="ea189-p118">SPF identifies which mail servers are allowed to send mail on your behalf. Basically, SPF, along with DKIM, DMARC, and other technologies supported by Office 365, help prevent spoofing and phishing. SPF is added as a TXT record that is used by DNS to identify which mail servers can send mail on behalf of your custom domain. Recipient mail systems refer to the SPF TXT record to determine whether a message from your custom domain comes from an authorized messaging server.</span></span>

<span data-ttu-id="ea189-p119">Ad esempio, si supponga che il dominio personalizzato contoso.com utilizzi Office 365. Si aggiunge un record TXT SPF che elenca i server di messaggistica di Office 365 come server di posta elettronica legittimi per il dominio. Quando il server di messaggistica ricevente riceve un messaggio da joe@contoso.com, il server cerca il record TXT SPF per contoso.com e scopre se il messaggio è valido. Se il server di destinazione rileva che il messaggio proviene da un server di messaggistica di Office 365 diverso da quelli elencati nel record SPF, il server di posta di destinazione può scegliere di rifiutare il messaggio come posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="ea189-p119">For example, let's say that your custom domain contoso.com uses Office 365. You add an SPF TXT record that lists the Office 365 messaging servers as legitimate mail servers for your domain. When the receiving messaging server gets a message from joe@contoso.com, the server looks up the SPF TXT record for contoso.com and finds out whether the message is valid. If the receiving server finds out that the message comes from a server other than the Office 365 messaging servers listed in the SPF record, the receiving mail server can choose to reject the message as spam.</span></span>

<span data-ttu-id="ea189-p120">Inoltre, se nel dominio personalizzato non è presente un record TXT SPF, alcuni server di destinazione possono rifiutare il messaggio immediatamente. Ciò avviene perché il server di destinazione non può convalidare che il messaggio provenga da un server di messaggistica autorizzato.</span><span class="sxs-lookup"><span data-stu-id="ea189-p120">Also, if your custom domain does not have an SPF TXT record, some receiving servers may reject the message outright. This is because the receiving server cannot validate that the message comes from an authorized messaging server.</span></span>

<span data-ttu-id="ea189-p121">Se la posta di Office 365 è già stata sincronizzata, i server di messaggistica Microsoft sono già stati inclusi nel sistema DNS come record TXT SPF. Tuttavia, esistono alcuni casi in cui è necessario aggiornare il record TXT SPF nel sistema DNS. Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="ea189-p121">If you've already set up mail for Office 365, then you have already included Microsoft's messaging servers in DNS as an SPF TXT record. However, there are some cases where you may need to update your SPF TXT record in DNS. For example:</span></span>

- <span data-ttu-id="ea189-p122">In precedenza, era necessario aggiungere un record SPF o TXT diverso al dominio personalizzato se si utilizzava SharePoint Online. Ciò non è più necessario. Questa modifica dovrebbe ridurre il rischio che i messaggi di notifica di SharePoint Online finiscano nella cartella Posta indesiderata. Aggiornare il record SPF o TXT se si sta raggiungendo il limite di 10 ricerche e si stanno visualizzando errori del tipo "limite di ricerche superato" e "troppi hop".</span><span class="sxs-lookup"><span data-stu-id="ea189-p122">Previously, you had to add a different SPF TXT record to your custom domain if you were using SharePoint Online. This is no longer required. This change should reduce the risk of SharePoint Online notification messages ending up in the Junk Email folder. Update your SPF TXT record if you are hitting the 10 lookup limit and receiving errors that say things like, "exceeded the lookup limit" and "too many hops".</span></span>

- <span data-ttu-id="ea189-203">Se si dispone di un ambiente ibrido con Office 365 ed Exchange in locale.</span><span class="sxs-lookup"><span data-stu-id="ea189-203">If you have a hybrid environment with Office 365 and Exchange on-premises.</span></span>

- <span data-ttu-id="ea189-204">Si intende configurare DKIM e DMARC (scelta consigliata).</span><span class="sxs-lookup"><span data-stu-id="ea189-204">You intend to set up DKIM and DMARC (recommended).</span></span>

## <a name="more-information-about-spf"></a><span data-ttu-id="ea189-205">Per ulteriori informazioni su SPF</span><span class="sxs-lookup"><span data-stu-id="ea189-205">More information about SPF</span></span>

<span data-ttu-id="ea189-206">Per esempi avanzati e una descrizione dettagliata della sintassi SPF supportata, dello spoofing, della risoluzione dei problemi e di come Office 365 supporta SPF, vedere [Come funziona SPF per impedire spoofing e phishing in Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks).</span><span class="sxs-lookup"><span data-stu-id="ea189-206">For advanced examples, a more detailed discussion about supported SPF syntax, spoofing, troubleshooting, and how Office 365 supports SPF, see [How SPF works to prevent spoofing and phishing in Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks).</span></span>

## <a name="next-steps-dkim-and-dmarc"></a><span data-ttu-id="ea189-207">Passaggi successivi: DKIM e DMARC</span><span class="sxs-lookup"><span data-stu-id="ea189-207">Next Steps: DKIM and DMARC</span></span>

 <span data-ttu-id="ea189-208">SPF è progettato per prevenire spoofing, ma esistono tecniche di spoofing che SPF non è in grado di evitare.</span><span class="sxs-lookup"><span data-stu-id="ea189-208">SPF is designed to help prevent spoofing, but there are spoofing techniques that SPF can't protect against.</span></span> <span data-ttu-id="ea189-209">Per difendersi da queste minacce, dopo aver configurato SPF è consigliabile configurare anche DKIM e DMARC per Office 365.</span><span class="sxs-lookup"><span data-stu-id="ea189-209">To defend against these, once you've set up SPF, you should configure DKIM and DMARC for Office 365.</span></span>

<span data-ttu-id="ea189-210">L'obiettivo dell'autenticazione [DKIM](use-dkim-to-validate-outbound-email.md) della posta elettronica è dimostrare che il contenuto del messaggio non è stato manomesso.</span><span class="sxs-lookup"><span data-stu-id="ea189-210">[DKIM](use-dkim-to-validate-outbound-email.md) email authentication's goal is to prove the contents of the mail haven't been tampered with.</span></span>

<span data-ttu-id="ea189-211">L'obiettivo dell'autenticazione [DMARC](use-dmarc-to-validate-email.md) della posta elettronica è assicurare che le informazioni SPF e DKIM corrispondano all'indirizzo Da.</span><span class="sxs-lookup"><span data-stu-id="ea189-211">[DMARC](use-dmarc-to-validate-email.md) email authentication's goal is to make sure that SPF and DKIM information matches the From address.</span></span>

 <span data-ttu-id="ea189-212">Per esempi avanzati e una descrizione dettagliata della sintassi SPF supportata, vedere [Funzionamento di SPF per prevenire spoofing e phishing in Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks).</span><span class="sxs-lookup"><span data-stu-id="ea189-212">For advanced examples and a more detailed discussion about supported SPF syntax, see [How SPF works to prevent spoofing and phishing in Office 365](how-office-365-uses-spf-to-prevent-spoofing.md#HowSPFWorks).</span></span>

<span data-ttu-id="ea189-213">*Selezionare 'Questa pagina' in 'Feedback' se si ha un feedback su questa documentazione.*</span><span class="sxs-lookup"><span data-stu-id="ea189-213">*Select 'This page' under 'Feedback' if you have feedback on this documentation.*</span></span>
