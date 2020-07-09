---
title: Aggiungere record DNS per connettere il dominio
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- MET150
description: Informazioni su come verificare il dominio e creare record DNS presso un provider di hosting DNS per Microsoft 365.
ms.custom:
- okr_smb
- AdminSurgePortfolio
ms.openlocfilehash: d3a9e3787afc30b33122edf91c1cf9e3dd84b847
ms.sourcegitcommit: 7c1b34205746ff0690ffc774a74bdfd434256cf5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/07/2020
ms.locfileid: "45049667"
---
# <a name="add-dns-records-to-connect-your-domain"></a><span data-ttu-id="fbd7c-103">Aggiungere record DNS per connettere il dominio</span><span class="sxs-lookup"><span data-stu-id="fbd7c-103">Add DNS records to connect your domain</span></span>

<span data-ttu-id="fbd7c-104">Se è stato acquistato un dominio presso un provider di hosting di terze parti, è possibile connetterlo a Microsoft 365 aggiornando i record DNS nell'account del registrar.</span><span class="sxs-lookup"><span data-stu-id="fbd7c-104">If you purchased a domain from a third-party hosting provider, you can connect it to Microsoft 365 by updating the DNS records in your registrar’s account.</span></span>

<span data-ttu-id="fbd7c-105">Alla fine di questa procedura, il dominio rimarrà registrato con l'host da cui è stato acquistato, ma Microsoft 365 potrà usarlo per gli indirizzi di posta elettronica, ad esempio utente@dominio.com, e altri servizi.</span><span class="sxs-lookup"><span data-stu-id="fbd7c-105">At the end of these steps, your domain will stay registered with the host that you purchased the domain from, but Microsoft 365 can use it for you email addresses (like user@yourdomain.com) and other services.</span></span>

<span data-ttu-id="fbd7c-106">Finché non verrà aggiunto un dominio, gli utenti dell'organizzazione useranno onmicrosoft.com per gli indirizzi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="fbd7c-106">If you don't add a domain, people in your organization will use the onmicrosoft.com domain for their email addresses until you do.</span></span> <span data-ttu-id="fbd7c-107">È importante aggiungere il dominio prima di aggiungere utenti, per evitare una doppia configurazione.</span><span class="sxs-lookup"><span data-stu-id="fbd7c-107">It's important to add your domain before you add users, so you don't have to set them up twice.</span></span>

<span data-ttu-id="fbd7c-108">Se non si trova ciò che si sta cercando, [vedere le domande frequenti sui domini](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="fbd7c-108">[Check the Domains FAQ](../setup/domains-faq.md) if you don't find what you're looking for below.</span></span>

## <a name="step-1-add-a-txt-record-to-verify-you-own-the-domain"></a><span data-ttu-id="fbd7c-109">Passaggio 1: Aggiungere un record TXT per verificare la proprietà del dominio</span><span class="sxs-lookup"><span data-stu-id="fbd7c-109">Step 1: Add a TXT record to verify you own the domain</span></span>

<span data-ttu-id="fbd7c-110">Prima di tutto, è necessario dimostrare di essere proprietari del dominio che si vuole aggiungere a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fbd7c-110">First, you need to prove you own the domain you want to add to Microsoft 365.</span></span>

1. <span data-ttu-id="fbd7c-111">Accedere all'[interfaccia di amministrazione di Microsoft 365](https://admin.microsoft.com/) e selezionare **Mostra tutto** > **Impostazioni** > **Domini**.</span><span class="sxs-lookup"><span data-stu-id="fbd7c-111">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com/) and select **Show all** > **Settings** > **Domains**.</span></span>
2. <span data-ttu-id="fbd7c-112">In una nuova scheda o finestra del browser accedere al proprio provider di hosting DNS, quindi individuare il percorso da cui gestire le impostazioni DNS (ad esempio, le impostazioni dei file di zona, Gestione domini, Gestione dominio, Gestore DNS).</span><span class="sxs-lookup"><span data-stu-id="fbd7c-112">In a new browser tab or window, sign in to your DNS hosting provider, and then find where you manage your DNS settings (e.g., Zone File Settings, Manage Domains, Domain Manager, DNS Manager).</span></span>
3. <span data-ttu-id="fbd7c-113">Passare alla pagina Gestore DNS del provider e aggiungere il record TXT indicato nell'interfaccia di amministrazione al dominio.</span><span class="sxs-lookup"><span data-stu-id="fbd7c-113">Go to your provider's DNS Manager page, and add the TXT record indicated in the admin center to your domain.</span></span>

<span data-ttu-id="fbd7c-114">L'aggiunta di questo record non influirà sulla posta elettronica o su altri servizi esistenti, inoltre il record potrà essere rimosso una volta connesso il dominio a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fbd7c-114">Adding this record won't affect your existing email or other services and you can safely remove it once your domain is connected to Microsoft 365.</span></span>

<span data-ttu-id="fbd7c-115">Esempio:</span><span class="sxs-lookup"><span data-stu-id="fbd7c-115">Example:</span></span>
- <span data-ttu-id="fbd7c-116">Nome TXT: `@`</span><span class="sxs-lookup"><span data-stu-id="fbd7c-116">TXT Name: `@`</span></span>
- <span data-ttu-id="fbd7c-117">Valore TXT: MS=ms######## (ID univoco dall'interfaccia di amministrazione)</span><span class="sxs-lookup"><span data-stu-id="fbd7c-117">TXT Value: MS=ms######## (unique ID from the admin center)</span></span>
- <span data-ttu-id="fbd7c-118">TTL: `3600‎` (o il provider predefinito)</span><span class="sxs-lookup"><span data-stu-id="fbd7c-118">TTL: `3600‎` (or your provider default)</span></span>

4. <span data-ttu-id="fbd7c-119">Salvare il record, tornare nell'interfaccia di amministrazione, quindi selezionare **Verifica**.</span><span class="sxs-lookup"><span data-stu-id="fbd7c-119">Save the record, go back to the admin center, and then select **Verify**.</span></span> <span data-ttu-id="fbd7c-120">In genere occorrono circa 15 minuti prima che le modifiche apportate al record vengano registrate, ma a volte può essere necessario più tempo.</span><span class="sxs-lookup"><span data-stu-id="fbd7c-120">It typically takes around 15 minutes for record changes to register, but sometimes it can take longer.</span></span> <span data-ttu-id="fbd7c-121">Attendere il tempo richiesto ed effettuare i tentativi necessari per rilevare la modifica.</span><span class="sxs-lookup"><span data-stu-id="fbd7c-121">Give it some time and a few tries to pick up the change.</span></span>

<span data-ttu-id="fbd7c-122">Quando Microsoft trova il record TXT corretto, il dominio è verificato.</span><span class="sxs-lookup"><span data-stu-id="fbd7c-122">When Microsoft finds the correct TXT record, your domain is verified.</span></span>


## <a name="step-2-add-dns-records-to-connect-microsoft-services"></a><span data-ttu-id="fbd7c-123">Passaggio 2: Aggiungere record DNS per connettere servizi Microsoft</span><span class="sxs-lookup"><span data-stu-id="fbd7c-123">Step 2: Add DNS records to connect Microsoft services</span></span>

<span data-ttu-id="fbd7c-124">In una nuova scheda o finestra del browser accedere al proprio provider di hosting DNS, quindi individuare il percorso da cui gestire le impostazioni DNS (ad esempio, le impostazioni dei file di zona, Gestione domini, Gestione dominio, Gestore DNS).</span><span class="sxs-lookup"><span data-stu-id="fbd7c-124">In a new browser tab or window, sign in to your DNS hosting provider, and find where you manage your DNS settings (e.g., Zone File Settings, Manage Domains, Domain Manager, DNS Manager).</span></span>

<span data-ttu-id="fbd7c-125">Verranno aggiunti diversi tipi di record DNS in base ai servizi da abilitare.</span><span class="sxs-lookup"><span data-stu-id="fbd7c-125">You'll be adding several different types of DNS records depending on the services you want to enable.</span></span> 

### <a name="add-an-mx-record-for-email-outlook-exchange-online"></a><span data-ttu-id="fbd7c-126">Aggiungere un record MX per la posta elettronica (Outlook, Exchange Online)</span><span class="sxs-lookup"><span data-stu-id="fbd7c-126">Add an MX record for email (Outlook, Exchange Online)</span></span>
<span data-ttu-id="fbd7c-127">**Prima di iniziare:** se gli utenti hanno già un'e-mail con il proprio dominio (ad esempio utente@dominio.com), creare gli account nell'interfaccia di amministrazione prima di configurare i record MX.</span><span class="sxs-lookup"><span data-stu-id="fbd7c-127">**Before you begin:** If users already have email with your domain (such as user@yourdomain.com), create their accounts in the admin center before you set up your MX records.</span></span> <span data-ttu-id="fbd7c-128">In questo modo potranno continuare a ricevere messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="fbd7c-128">That way, they’ll continue to receive email.</span></span> <span data-ttu-id="fbd7c-129">Quando si aggiorna il record MX del dominio, tutti i nuovi messaggi di posta elettronica indirizzati a chiunque usi il dominio verranno recapitati in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fbd7c-129">When you update your domain's MX record, all new email for anyone who uses your domain will now come to Microsoft 365.</span></span> <span data-ttu-id="fbd7c-130">I messaggi già disponibili rimarranno nell'attuale host di posta elettronica, a meno che non si decida di [eseguire la migrazione di posta elettronica e contatti](../setup/migrate-email-and-contacts-admin.md) a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fbd7c-130">Any email you already have will stay at your current email host, unless you decide to [migrate email and contacts to Microsoft 365.](../setup/migrate-email-and-contacts-admin.md)</span></span>

<span data-ttu-id="fbd7c-131">Le informazioni per il record MX saranno disponibili durante la configurazione dominio guidata dell'interfaccia di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="fbd7c-131">You'll get the information for the MX record from the admin center domain setup wizard.</span></span>

<span data-ttu-id="fbd7c-132">Nel sito Web del provider di hosting, aggiungere un nuovo record MX.</span><span class="sxs-lookup"><span data-stu-id="fbd7c-132">On your hosting provider's website, add a new MX record.</span></span>
<span data-ttu-id="fbd7c-133">Verificare che i campi siano impostati sui valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="fbd7c-133">Make sure that the fields are set to the following values:</span></span>

- <span data-ttu-id="fbd7c-134">Tipo di record: `MX`</span><span class="sxs-lookup"><span data-stu-id="fbd7c-134">Record Type: `MX`</span></span>
- <span data-ttu-id="fbd7c-135">Priorità: impostare sul valore massimo disponibile, in genere `0`.</span><span class="sxs-lookup"><span data-stu-id="fbd7c-135">Priority: Set to the highest value available, typically `0`.</span></span>
- <span data-ttu-id="fbd7c-136">Nome host: `@`</span><span class="sxs-lookup"><span data-stu-id="fbd7c-136">Host Name: `@`</span></span>
- <span data-ttu-id="fbd7c-137">Indirizzo di puntamento: copiare il valore dall'interfaccia di amministrazione e incollarlo qui.</span><span class="sxs-lookup"><span data-stu-id="fbd7c-137">Points to address: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="fbd7c-138">TTL: `3600‎` (o il provider predefinito)</span><span class="sxs-lookup"><span data-stu-id="fbd7c-138">TTL: `3600‎` (or your provider default)</span></span>

<span data-ttu-id="fbd7c-139">Salvare il record, quindi rimuovere qualsiasi altro record MX.</span><span class="sxs-lookup"><span data-stu-id="fbd7c-139">Save the record, and then remove any other MX records.</span></span>

### <a name="add-cname-records-to-connect-other-services-teams-exchange-online-aad-mdm"></a><span data-ttu-id="fbd7c-140">Aggiungere record CNAME per connettere altri servizi (Teams, Exchange Online, AAD, MDM)</span><span class="sxs-lookup"><span data-stu-id="fbd7c-140">Add CNAME records to connect other services (Teams, Exchange Online, AAD, MDM)</span></span>
<span data-ttu-id="fbd7c-141">Le informazioni per i record CNAME saranno disponibili durante la configurazione dominio guidata dell'interfaccia di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="fbd7c-141">You'll get the information for the CNAME records from the admin center domain setup wizard.</span></span>

<span data-ttu-id="fbd7c-142">Nel sito Web del provider di hosting, aggiungere i record CNAME per ogni servizio che si vuole connettere.</span><span class="sxs-lookup"><span data-stu-id="fbd7c-142">On your hosting provider's website, add CNAME records for each service that you want to connect.</span></span>
<span data-ttu-id="fbd7c-143">Verificare che i campi siano impostati sui valori seguenti per ciascun:</span><span class="sxs-lookup"><span data-stu-id="fbd7c-143">Make sure that the fields are set to the following values for each:</span></span>

- <span data-ttu-id="fbd7c-144">Tipo di record: `CNAME (Alias)`</span><span class="sxs-lookup"><span data-stu-id="fbd7c-144">Record Type: `CNAME (Alias)`</span></span>
- <span data-ttu-id="fbd7c-145">Host: incollare qui i valori copiati dall'interfaccia di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="fbd7c-145">Host: Paste the values you copy from the admin center here.</span></span>
- <span data-ttu-id="fbd7c-146">Indirizzo di puntamento: copiare il valore dall'interfaccia di amministrazione e incollarlo qui.</span><span class="sxs-lookup"><span data-stu-id="fbd7c-146">Points to address: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="fbd7c-147">TTL: `3600‎` (o il provider predefinito)</span><span class="sxs-lookup"><span data-stu-id="fbd7c-147">TTL: `3600‎` (or your provider default)</span></span>


### <a name="add-or-edit-an-spf-txt-record-to-help-prevent-email-spam-outlook-exchange-online"></a><span data-ttu-id="fbd7c-148">Aggiungere o modificare un record TXT SPF per evitare di ricevere posta indesiderata (Outlook, Exchange Online)</span><span class="sxs-lookup"><span data-stu-id="fbd7c-148">Add or edit an SPF TXT record to help prevent email spam (Outlook, Exchange Online)</span></span>
<span data-ttu-id="fbd7c-149">**Prima di iniziare:** se si dispone già di un record SPF per il dominio, non crearne uno nuovo per Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fbd7c-149">**Before you begin:** If you already have an SPF record for your domain, don't create a new one for Microsoft 365.</span></span> <span data-ttu-id="fbd7c-150">Aggiungere invece i valori di Microsoft 365 necessari al record corrente nel sito Web del provider di hosting, in modo da ottenere un *unico* record SPF che includa entrambi i set di valori.</span><span class="sxs-lookup"><span data-stu-id="fbd7c-150">Instead, add the required Microsoft 365 values to the current record on your hosting providers website so that you have a *single* SPF record that includes both sets of values.</span></span>

<span data-ttu-id="fbd7c-151">Nel sito Web del provider di hosting, creare un record SPF o modificarne uno esistente.</span><span class="sxs-lookup"><span data-stu-id="fbd7c-151">On your hosting provider's website, edit the existing SPF record or create an SPF record.</span></span>
<span data-ttu-id="fbd7c-152">Verificare che i campi siano impostati sui valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="fbd7c-152">Make sure that the fields are set to the following values:</span></span>

- <span data-ttu-id="fbd7c-153">Tipo di record: `TXT (Text)`</span><span class="sxs-lookup"><span data-stu-id="fbd7c-153">Record Type: `TXT (Text)`</span></span>
- <span data-ttu-id="fbd7c-154">Host: `@`</span><span class="sxs-lookup"><span data-stu-id="fbd7c-154">Host: `@`</span></span>
- <span data-ttu-id="fbd7c-155">Valore TXT: `v=spf1 include:spf.protection.outlook.com -all`</span><span class="sxs-lookup"><span data-stu-id="fbd7c-155">TXT Value: `v=spf1 include:spf.protection.outlook.com -all`</span></span>
- <span data-ttu-id="fbd7c-156">TTL: `3600‎` (o il provider predefinito)</span><span class="sxs-lookup"><span data-stu-id="fbd7c-156">TTL: `3600‎` (or your provider default)</span></span>

<span data-ttu-id="fbd7c-157">Salvare il record.</span><span class="sxs-lookup"><span data-stu-id="fbd7c-157">Save the record.</span></span>

<span data-ttu-id="fbd7c-158">Convalidare il record SPF usando uno di questi [strumenti di convalida SPF](https://docs.microsoft.com/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain)</span><span class="sxs-lookup"><span data-stu-id="fbd7c-158">Validate your SPF record by using one of these [SPF validation tools](https://docs.microsoft.com/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain)</span></span>

<span data-ttu-id="fbd7c-159">SPF è progettata per prevenire spoofing, ma esistono tecniche spoofing che SPF non è in grado di evitare.</span><span class="sxs-lookup"><span data-stu-id="fbd7c-159">SPF is designed to help prevent spoofing, but there are spoofing techniques that SPF cannot protect against.</span></span> <span data-ttu-id="fbd7c-160">Per proteggersi da queste minacce, dopo aver configurato SPF è consigliabile impostare anche DKIM e DMARC per Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fbd7c-160">To protect against these, once you've set up SPF, you should also set up DKIM and DMARC for Microsoft 365.</span></span> 

<span data-ttu-id="fbd7c-161">Per iniziare, vedere [Usare DKIM per convalidare la posta elettronica in uscita inviata dal proprio dominio in Microsoft 365](https://technet.microsoft.com/library/mt695945%28v=exchg.150%29.aspx) e [Usare DKIM per convalidare la posta elettronica in Microsoft 365](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="fbd7c-161">To get started, see [Use DKIM to validate outbound email sent from your domain in Microsoft 365](https://technet.microsoft.com/library/mt695945%28v=exchg.150%29.aspx) and [Use DMARC to validate email in Microsoft 365](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx).</span></span>

### <a name="add-srv-records-for-communications-services-teams-skype-for-business"></a><span data-ttu-id="fbd7c-162">Aggiungere record SRV per servizi di comunicazione (Teams, Skype for Business)</span><span class="sxs-lookup"><span data-stu-id="fbd7c-162">Add SRV records for communications services (Teams, Skype for Business)</span></span>

<span data-ttu-id="fbd7c-163">Nel sito Web del provider di hosting, aggiungere i record SRV per ogni servizio che si vuole connettere.</span><span class="sxs-lookup"><span data-stu-id="fbd7c-163">On your hosting provider's website, add SRV records for each service you want to connect.</span></span>
<span data-ttu-id="fbd7c-164">Verificare che i campi siano impostati sui valori seguenti per ciascun:</span><span class="sxs-lookup"><span data-stu-id="fbd7c-164">Make sure that the fields are set to the following values for each:</span></span>

- <span data-ttu-id="fbd7c-165">Tipo di record: `SRV (Service)`</span><span class="sxs-lookup"><span data-stu-id="fbd7c-165">Record Type: `SRV (Service)`</span></span>
- <span data-ttu-id="fbd7c-166">Nome: `@`</span><span class="sxs-lookup"><span data-stu-id="fbd7c-166">Name: `@`</span></span>
- <span data-ttu-id="fbd7c-167">Destinazione: copiare il valore dall'interfaccia di amministrazione e incollarlo qui.</span><span class="sxs-lookup"><span data-stu-id="fbd7c-167">Target: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="fbd7c-168">Protocollo: copiare il valore dall'interfaccia di amministrazione e incollarlo qui.</span><span class="sxs-lookup"><span data-stu-id="fbd7c-168">Protocol: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="fbd7c-169">Servizio: copiare il valore dall'interfaccia di amministrazione e incollarlo qui.</span><span class="sxs-lookup"><span data-stu-id="fbd7c-169">Service: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="fbd7c-170">Priorità: `100`</span><span class="sxs-lookup"><span data-stu-id="fbd7c-170">Priority: `100`</span></span>
- <span data-ttu-id="fbd7c-171">Peso: `1`</span><span class="sxs-lookup"><span data-stu-id="fbd7c-171">Weight: `1`</span></span>
- <span data-ttu-id="fbd7c-172">Porta: copiare il valore dall'interfaccia di amministrazione e incollarlo qui.</span><span class="sxs-lookup"><span data-stu-id="fbd7c-172">Port: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="fbd7c-173">TTL: `3600‎` (o il provider predefinito)</span><span class="sxs-lookup"><span data-stu-id="fbd7c-173">TTL: `3600‎` (or your provider default)</span></span>

<span data-ttu-id="fbd7c-174">Salvare il record.</span><span class="sxs-lookup"><span data-stu-id="fbd7c-174">Save the record.</span></span>

#### <a name="srv-record-field-restrictions-and-workarounds"></a><span data-ttu-id="fbd7c-175">Restrizioni del campo SRV e soluzioni alternative</span><span class="sxs-lookup"><span data-stu-id="fbd7c-175">SRV record field restrictions and workarounds</span></span>
<span data-ttu-id="fbd7c-176">Alcuni provider di hosting impongono restrizioni sui valori dei campi all'interno dei record SRV.</span><span class="sxs-lookup"><span data-stu-id="fbd7c-176">Some hosting providers impose restrictions on field values within SRV records.</span></span> <span data-ttu-id="fbd7c-177">Di seguito sono riportate alcune soluzioni alternative comuni per queste restrizioni.</span><span class="sxs-lookup"><span data-stu-id="fbd7c-177">Here are some common workarounds for these restrictions.</span></span>

##### <a name="name"></a><span data-ttu-id="fbd7c-178">Nome</span><span class="sxs-lookup"><span data-stu-id="fbd7c-178">Name</span></span>
<span data-ttu-id="fbd7c-179">Se il provider di hosting non consente di configurare questo campo per **@**, lasciarlo vuoto.</span><span class="sxs-lookup"><span data-stu-id="fbd7c-179">If your hosting provider doesn't allow setting this field to **@**, leave it blank.</span></span> <span data-ttu-id="fbd7c-180">Usare questo approccio *solo* quando il provider di hosting ha campi distinti per i valori Servizio e Protocollo.</span><span class="sxs-lookup"><span data-stu-id="fbd7c-180">Use this approach *only* when your hosting provider has separate fields for the Service and Protocol values.</span></span> <span data-ttu-id="fbd7c-181">Altrimenti, vedere la nota sui valori Servizio e Protocollo di seguito.</span><span class="sxs-lookup"><span data-stu-id="fbd7c-181">Otherwise, see the Service and Protocol notes below.</span></span>

##### <a name="service-and-protocol"></a><span data-ttu-id="fbd7c-182">Servizio e Protocollo</span><span class="sxs-lookup"><span data-stu-id="fbd7c-182">Service and Protocol</span></span>
<span data-ttu-id="fbd7c-183">Se presso il provider di hosting non sono disponibili questi campi per i record SRV, è necessario specificare i valori **Servizio** e **Protocollo** nel campo **Nome** del record.</span><span class="sxs-lookup"><span data-stu-id="fbd7c-183">If your hosting provider doesn't provide these fields for SRV records, you must specify the **Service** and **Protocol** values in the record's **Name** field.</span></span> <span data-ttu-id="fbd7c-184">Nota: a seconda del provider di hosting, il campo **Nome** potrebbe avere una denominazione diversa, ad esempio **Host**, **Nome host** o **Sottodominio**. Per aggiungere questi valori, creare una singola stringa, separando i valori con un punto.</span><span class="sxs-lookup"><span data-stu-id="fbd7c-184">(Note: Depending on your hosting provider, the **Name** field might be called something else, like: **Host**, **Hostname**, or **Subdomain**.) To add these values, you create a single string, separating the values with a dot.</span></span> 

<span data-ttu-id="fbd7c-185">Esempio: `_sip._tls`</span><span class="sxs-lookup"><span data-stu-id="fbd7c-185">Example: `_sip._tls`</span></span>

##### <a name="priority-weight-and-port-br"></a><span data-ttu-id="fbd7c-186">Priorità, Peso e Porta</span><span class="sxs-lookup"><span data-stu-id="fbd7c-186">Priority, Weight, and Port</span></span> <br>
<span data-ttu-id="fbd7c-187">Se presso il provider di hosting non sono disponibili questi campi per i record SRV, è necessario specificarli nel campo **Destinazione** del record.</span><span class="sxs-lookup"><span data-stu-id="fbd7c-187">If your hosting provider doesn't provide these fields for SRV records, you must specify them in the record's **Target** field.</span></span> <span data-ttu-id="fbd7c-188">Nota: a seconda del provider di hosting, il campo **Destinazione** potrebbe avere una denominazione diversa, ad esempio **Contenuto**, **Indirizzo IP** o **Host di destinazione**.</span><span class="sxs-lookup"><span data-stu-id="fbd7c-188">(Note: Depending on your hosting provider, the **Target** field might be called something else, like: **Content**, **IP Address**, or **Target Host**.)</span></span> 

<span data-ttu-id="fbd7c-189">Per aggiungere questi valori, creare una singola stringa, separando i valori con spazi e *a volte terminando con un punto* (rivolgersi al provider in caso di dubbi).</span><span class="sxs-lookup"><span data-stu-id="fbd7c-189">To add these values, create a single string, separating the values with spaces and *sometimes ending with a dot* (check with your provider if you are unsure).</span></span> <span data-ttu-id="fbd7c-190">I valori devono essere inclusi in questo ordine: Priorità, Peso, Porta, Destinazione.</span><span class="sxs-lookup"><span data-stu-id="fbd7c-190">The values must be included in this order: Priority, Weight, Port, Target.</span></span> 

- <span data-ttu-id="fbd7c-191">Esempio 1: `100 1 443 sipdir.online.lync.com.`</span><span class="sxs-lookup"><span data-stu-id="fbd7c-191">Example 1: `100 1 443 sipdir.online.lync.com.`</span></span>
- <span data-ttu-id="fbd7c-192">Esempio 2: `100 1 443 sipdir.online.lync.com`</span><span class="sxs-lookup"><span data-stu-id="fbd7c-192">Example 2: `100 1 443 sipdir.online.lync.com`</span></span>
