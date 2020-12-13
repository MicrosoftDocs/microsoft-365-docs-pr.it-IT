---
title: Aggiungere record DNS per connettere il dominio
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
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
ms.openlocfilehash: 01fd78033afb6add41975826ed8daddf052826b2
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2020
ms.locfileid: "49655601"
---
# <a name="add-dns-records-to-connect-your-domain"></a><span data-ttu-id="23438-103">Aggiungere record DNS per connettere il dominio</span><span class="sxs-lookup"><span data-stu-id="23438-103">Add DNS records to connect your domain</span></span>

<span data-ttu-id="23438-104">Se è stato acquistato un dominio presso un provider di hosting di terze parti, è possibile connetterlo a Microsoft 365 aggiornando i record DNS nell'account del registrar.</span><span class="sxs-lookup"><span data-stu-id="23438-104">If you purchased a domain from a third-party hosting provider, you can connect it to Microsoft 365 by updating the DNS records in your registrar’s account.</span></span>

<span data-ttu-id="23438-105">Alla fine di questa procedura, il dominio rimarrà registrato con l'host da cui è stato acquistato, ma Microsoft 365 potrà usarlo per gli indirizzi di posta elettronica, ad esempio utente@dominio.com, e altri servizi.</span><span class="sxs-lookup"><span data-stu-id="23438-105">At the end of these steps, your domain will stay registered with the host that you purchased the domain from, but Microsoft 365 can use it for your email addresses (like user@yourdomain.com) and other services.</span></span>

<span data-ttu-id="23438-106">Finché non verrà aggiunto un dominio, gli utenti dell'organizzazione useranno onmicrosoft.com per gli indirizzi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="23438-106">If you don't add a domain, people in your organization will use the onmicrosoft.com domain for their email addresses until you do.</span></span> <span data-ttu-id="23438-107">È importante aggiungere il dominio prima di aggiungere utenti, per evitare una doppia configurazione.</span><span class="sxs-lookup"><span data-stu-id="23438-107">It's important to add your domain before you add users, so you don't have to set them up twice.</span></span>

<span data-ttu-id="23438-108">Se non si trova ciò che si sta cercando, [vedere le domande frequenti sui domini](../setup/domains-faq.yml).</span><span class="sxs-lookup"><span data-stu-id="23438-108">[Check the Domains FAQ](../setup/domains-faq.yml) if you don't find what you're looking for below.</span></span>

## <a name="step-1-add-a-txt-or-mx-record-to-verify-you-own-the-domain"></a><span data-ttu-id="23438-109">Passaggio 1: Aggiungere un record TXT o MX per verificare la proprietà del dominio</span><span class="sxs-lookup"><span data-stu-id="23438-109">Step 1: Add a TXT or MX record to verify you own the domain</span></span>

### <a name="recommended-verify-with-a-txt-record"></a><span data-ttu-id="23438-110">Consigliato: Verificare con un record TXT</span><span class="sxs-lookup"><span data-stu-id="23438-110">Recommended: Verify with a TXT record</span></span>

<span data-ttu-id="23438-111">Prima di tutto, è necessario dimostrare di essere proprietari del dominio che si vuole aggiungere a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="23438-111">First, you need to prove you own the domain you want to add to Microsoft 365.</span></span>

1. <span data-ttu-id="23438-112">Accedere all'[interfaccia di amministrazione di Microsoft 365](https://admin.microsoft.com/) e selezionare **Mostra tutto** > **Impostazioni** > **Domini**.</span><span class="sxs-lookup"><span data-stu-id="23438-112">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com/) and select **Show all** > **Settings** > **Domains**.</span></span>
2. <span data-ttu-id="23438-113">In una nuova scheda o finestra del browser accedere al proprio provider di hosting DNS, quindi individuare il percorso da cui gestire le impostazioni DNS (ad esempio, le impostazioni dei file di zona, Gestione domini, Gestione dominio, Gestore DNS).</span><span class="sxs-lookup"><span data-stu-id="23438-113">In a new browser tab or window, sign in to your DNS hosting provider, and then find where you manage your DNS settings (e.g., Zone File Settings, Manage Domains, Domain Manager, DNS Manager).</span></span>
3. <span data-ttu-id="23438-114">Passare alla pagina Gestore DNS del provider e aggiungere il record TXT indicato nell'interfaccia di amministrazione al dominio.</span><span class="sxs-lookup"><span data-stu-id="23438-114">Go to your provider's DNS Manager page, and add the TXT record indicated in the admin center to your domain.</span></span>

<span data-ttu-id="23438-115">L'aggiunta di questo record non influirà sulla posta elettronica o su altri servizi esistenti, inoltre il record potrà essere rimosso una volta connesso il dominio a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="23438-115">Adding this record won't affect your existing email or other services and you can safely remove it once your domain is connected to Microsoft 365.</span></span>

<span data-ttu-id="23438-116">Esempio:</span><span class="sxs-lookup"><span data-stu-id="23438-116">Example:</span></span>
- <span data-ttu-id="23438-117">Nome TXT: `@`</span><span class="sxs-lookup"><span data-stu-id="23438-117">TXT Name: `@`</span></span>
- <span data-ttu-id="23438-118">Valore TXT: MS=ms######## (ID univoco dall'interfaccia di amministrazione)</span><span class="sxs-lookup"><span data-stu-id="23438-118">TXT Value: MS=ms######## (unique ID from the admin center)</span></span>
- <span data-ttu-id="23438-119">TTL: `3600‎` (o il provider predefinito)</span><span class="sxs-lookup"><span data-stu-id="23438-119">TTL: `3600‎` (or your provider default)</span></span>

4. <span data-ttu-id="23438-120">Salvare il record, tornare nell'interfaccia di amministrazione, quindi selezionare **Verifica**.</span><span class="sxs-lookup"><span data-stu-id="23438-120">Save the record, go back to the admin center, and then select **Verify**.</span></span> <span data-ttu-id="23438-121">In genere occorrono circa 15 minuti prima che le modifiche apportate al record vengano registrate, ma a volte può essere necessario più tempo.</span><span class="sxs-lookup"><span data-stu-id="23438-121">It typically takes around 15 minutes for record changes to register, but sometimes it can take longer.</span></span> <span data-ttu-id="23438-122">Attendere il tempo richiesto ed effettuare i tentativi necessari per rilevare la modifica.</span><span class="sxs-lookup"><span data-stu-id="23438-122">Give it some time and a few tries to pick up the change.</span></span>

<span data-ttu-id="23438-123">Quando Microsoft trova il record TXT corretto, il dominio è verificato.</span><span class="sxs-lookup"><span data-stu-id="23438-123">When Microsoft finds the correct TXT record, your domain is verified.</span></span>

### <a name="verify-with-an-mx-record"></a><span data-ttu-id="23438-124">Verificare con un record MX</span><span class="sxs-lookup"><span data-stu-id="23438-124">Verify with an MX record</span></span>

<span data-ttu-id="23438-125">Se il registrar non supporta l'aggiunta di record TXT, è possibile verificare aggiungendo un record MX.</span><span class="sxs-lookup"><span data-stu-id="23438-125">If your registrar doesn't support adding TXT records, you can verify by adding an MX record.</span></span>

1. <span data-ttu-id="23438-126">Accedere all'[interfaccia di amministrazione di Microsoft 365](https://admin.microsoft.com/) e selezionare **Mostra tutto** > **Impostazioni** > **Domini**.</span><span class="sxs-lookup"><span data-stu-id="23438-126">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com/) and select **Show all** > **Settings** > **Domains**.</span></span>
2. <span data-ttu-id="23438-127">In una nuova scheda o finestra del browser accedere al proprio provider di hosting DNS, quindi individuare il percorso da cui gestire le impostazioni DNS (ad esempio, le impostazioni dei file di zona, Gestione domini, Gestione dominio, Gestore DNS).</span><span class="sxs-lookup"><span data-stu-id="23438-127">In a new browser tab or window, sign in to your DNS hosting provider, and then find where you manage your DNS settings (e.g., Zone File Settings, Manage Domains, Domain Manager, DNS Manager).</span></span>
3. <span data-ttu-id="23438-128">Passare alla pagina Gestore DNS del provider e aggiungere il record MX indicato nell'interfaccia di amministrazione al dominio.</span><span class="sxs-lookup"><span data-stu-id="23438-128">Go to your provider's DNS Manager page, and add the MX record indicated in the admin center to your domain.</span></span>

<span data-ttu-id="23438-129">La **Priorità** di questo record MX deve essere più elevata di tutti i record MX esistenti per il dominio.</span><span class="sxs-lookup"><span data-stu-id="23438-129">This MX record's **Priority** must be the highest of all existing MX records for the domain.</span></span> <span data-ttu-id="23438-130">In caso contrario, può interferire con l'invio e la ricezione di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="23438-130">Otherwise, it can interfere with sending and receiving email.</span></span> <span data-ttu-id="23438-131">È necessario eliminare questo record non appena la verifica del dominio viene completata.</span><span class="sxs-lookup"><span data-stu-id="23438-131">You should delete this records as soon as domain verification is complete.</span></span>

<span data-ttu-id="23438-132">Verificare che i campi siano impostati sui valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="23438-132">Make sure that the fields are set to the following values:</span></span>

- <span data-ttu-id="23438-133">Tipo di record: `MX`</span><span class="sxs-lookup"><span data-stu-id="23438-133">Record Type: `MX`</span></span>
- <span data-ttu-id="23438-134">Priorità: impostare sul valore massimo disponibile, in genere `0`.</span><span class="sxs-lookup"><span data-stu-id="23438-134">Priority: Set to the highest value available, typically `0`.</span></span>
- <span data-ttu-id="23438-135">Nome host: `@`</span><span class="sxs-lookup"><span data-stu-id="23438-135">Host Name: `@`</span></span>
- <span data-ttu-id="23438-136">Indirizzo di puntamento: copiare il valore dall'interfaccia di amministrazione e incollarlo qui.</span><span class="sxs-lookup"><span data-stu-id="23438-136">Points to address: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="23438-137">TTL: `3600‎` (o il provider predefinito)</span><span class="sxs-lookup"><span data-stu-id="23438-137">TTL: `3600‎` (or your provider default)</span></span>

<span data-ttu-id="23438-138">Quando Microsoft trova il record MX corretto, il dominio è verificato.</span><span class="sxs-lookup"><span data-stu-id="23438-138">When Microsoft finds the correct MX record, your domain is verified.</span></span>

## <a name="step-2-add-dns-records-to-connect-microsoft-services"></a><span data-ttu-id="23438-139">Passaggio 2: Aggiungere record DNS per connettere servizi Microsoft</span><span class="sxs-lookup"><span data-stu-id="23438-139">Step 2: Add DNS records to connect Microsoft services</span></span>

<span data-ttu-id="23438-140">In una nuova scheda o finestra del browser accedere al proprio provider di hosting DNS, quindi individuare il percorso da cui gestire le impostazioni DNS (ad esempio, le impostazioni dei file di zona, Gestione domini, Gestione dominio, Gestore DNS).</span><span class="sxs-lookup"><span data-stu-id="23438-140">In a new browser tab or window, sign in to your DNS hosting provider, and find where you manage your DNS settings (e.g., Zone File Settings, Manage Domains, Domain Manager, DNS Manager).</span></span>

<span data-ttu-id="23438-141">Verranno aggiunti diversi tipi di record DNS in base ai servizi da abilitare.</span><span class="sxs-lookup"><span data-stu-id="23438-141">You'll be adding several different types of DNS records depending on the services you want to enable.</span></span> 

### <a name="add-an-mx-record-for-email-outlook-exchange-online"></a><span data-ttu-id="23438-142">Aggiungere un record MX per la posta elettronica (Outlook, Exchange Online)</span><span class="sxs-lookup"><span data-stu-id="23438-142">Add an MX record for email (Outlook, Exchange Online)</span></span>
<span data-ttu-id="23438-143">**Prima di iniziare:** se gli utenti hanno già un'e-mail con il proprio dominio (ad esempio utente@dominio.com), creare gli account nell'interfaccia di amministrazione prima di configurare i record MX.</span><span class="sxs-lookup"><span data-stu-id="23438-143">**Before you begin:** If users already have email with your domain (such as user@yourdomain.com), create their accounts in the admin center before you set up your MX records.</span></span> <span data-ttu-id="23438-144">In questo modo potranno continuare a ricevere messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="23438-144">That way, they’ll continue to receive email.</span></span> <span data-ttu-id="23438-145">Quando si aggiorna il record MX del dominio, tutti i nuovi messaggi di posta elettronica indirizzati a chiunque usi il dominio verranno recapitati in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="23438-145">When you update your domain's MX record, all new email for anyone who uses your domain will now come to Microsoft 365.</span></span> <span data-ttu-id="23438-146">I messaggi già disponibili rimarranno nell'attuale host di posta elettronica, a meno che non si decida di [eseguire la migrazione di posta elettronica e contatti](../setup/migrate-email-and-contacts-admin.md) a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="23438-146">Any email you already have will stay at your current email host, unless you decide to [migrate email and contacts to Microsoft 365.](../setup/migrate-email-and-contacts-admin.md)</span></span>

<span data-ttu-id="23438-147">Le informazioni per il record MX saranno disponibili durante la configurazione dominio guidata dell'interfaccia di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="23438-147">You'll get the information for the MX record from the admin center domain setup wizard.</span></span>

<span data-ttu-id="23438-148">Nel sito Web del provider di hosting, aggiungere un nuovo record MX.</span><span class="sxs-lookup"><span data-stu-id="23438-148">On your hosting provider's website, add a new MX record.</span></span>
<span data-ttu-id="23438-149">Verificare che i campi siano impostati sui valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="23438-149">Make sure that the fields are set to the following values:</span></span>

- <span data-ttu-id="23438-150">Tipo di record: `MX`</span><span class="sxs-lookup"><span data-stu-id="23438-150">Record Type: `MX`</span></span>
- <span data-ttu-id="23438-151">Priorità: impostare sul valore massimo disponibile, in genere `0`.</span><span class="sxs-lookup"><span data-stu-id="23438-151">Priority: Set to the highest value available, typically `0`.</span></span>
- <span data-ttu-id="23438-152">Nome host: `@`</span><span class="sxs-lookup"><span data-stu-id="23438-152">Host Name: `@`</span></span>
- <span data-ttu-id="23438-153">Indirizzo di puntamento: copiare il valore dall'interfaccia di amministrazione e incollarlo qui.</span><span class="sxs-lookup"><span data-stu-id="23438-153">Points to address: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="23438-154">TTL: `3600‎` (o il provider predefinito)</span><span class="sxs-lookup"><span data-stu-id="23438-154">TTL: `3600‎` (or your provider default)</span></span>

<span data-ttu-id="23438-155">Salvare il record, quindi rimuovere qualsiasi altro record MX.</span><span class="sxs-lookup"><span data-stu-id="23438-155">Save the record, and then remove any other MX records.</span></span>

### <a name="add-cname-records-to-connect-other-services-teams-exchange-online-aad-mdm"></a><span data-ttu-id="23438-156">Aggiungere record CNAME per connettere altri servizi (Teams, Exchange Online, AAD, MDM)</span><span class="sxs-lookup"><span data-stu-id="23438-156">Add CNAME records to connect other services (Teams, Exchange Online, AAD, MDM)</span></span>
<span data-ttu-id="23438-157">Le informazioni per i record CNAME saranno disponibili durante la configurazione dominio guidata dell'interfaccia di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="23438-157">You'll get the information for the CNAME records from the admin center domain setup wizard.</span></span>

<span data-ttu-id="23438-158">Nel sito Web del provider di hosting, aggiungere i record CNAME per ogni servizio che si vuole connettere.</span><span class="sxs-lookup"><span data-stu-id="23438-158">On your hosting provider's website, add CNAME records for each service that you want to connect.</span></span>
<span data-ttu-id="23438-159">Verificare che i campi siano impostati sui valori seguenti per ciascun:</span><span class="sxs-lookup"><span data-stu-id="23438-159">Make sure that the fields are set to the following values for each:</span></span>

- <span data-ttu-id="23438-160">Tipo di record: `CNAME (Alias)`</span><span class="sxs-lookup"><span data-stu-id="23438-160">Record Type: `CNAME (Alias)`</span></span>
- <span data-ttu-id="23438-161">Host: incollare qui i valori copiati dall'interfaccia di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="23438-161">Host: Paste the values you copy from the admin center here.</span></span>
- <span data-ttu-id="23438-162">Indirizzo di puntamento: copiare il valore dall'interfaccia di amministrazione e incollarlo qui.</span><span class="sxs-lookup"><span data-stu-id="23438-162">Points to address: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="23438-163">TTL: `3600‎` (o il provider predefinito)</span><span class="sxs-lookup"><span data-stu-id="23438-163">TTL: `3600‎` (or your provider default)</span></span>


### <a name="add-or-edit-an-spf-txt-record-to-help-prevent-email-spam-outlook-exchange-online"></a><span data-ttu-id="23438-164">Aggiungere o modificare un record TXT SPF per evitare di ricevere posta indesiderata (Outlook, Exchange Online)</span><span class="sxs-lookup"><span data-stu-id="23438-164">Add or edit an SPF TXT record to help prevent email spam (Outlook, Exchange Online)</span></span>
<span data-ttu-id="23438-165">**Prima di iniziare:** se si dispone già di un record SPF per il dominio, non crearne uno nuovo per Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="23438-165">**Before you begin:** If you already have an SPF record for your domain, don't create a new one for Microsoft 365.</span></span> <span data-ttu-id="23438-166">Aggiungere invece i valori di Microsoft 365 necessari al record corrente nel sito Web del provider di hosting, in modo da ottenere un *unico* record SPF che includa entrambi i set di valori.</span><span class="sxs-lookup"><span data-stu-id="23438-166">Instead, add the required Microsoft 365 values to the current record on your hosting providers website so that you have a *single* SPF record that includes both sets of values.</span></span>

<span data-ttu-id="23438-167">Nel sito Web del provider di hosting, creare un record SPF o modificarne uno esistente.</span><span class="sxs-lookup"><span data-stu-id="23438-167">On your hosting provider's website, edit the existing SPF record or create an SPF record.</span></span>
<span data-ttu-id="23438-168">Verificare che i campi siano impostati sui valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="23438-168">Make sure that the fields are set to the following values:</span></span>

- <span data-ttu-id="23438-169">Tipo di record: `TXT (Text)`</span><span class="sxs-lookup"><span data-stu-id="23438-169">Record Type: `TXT (Text)`</span></span>
- <span data-ttu-id="23438-170">Host: `@`</span><span class="sxs-lookup"><span data-stu-id="23438-170">Host: `@`</span></span>
- <span data-ttu-id="23438-171">Valore TXT: `v=spf1 include:spf.protection.outlook.com -all`</span><span class="sxs-lookup"><span data-stu-id="23438-171">TXT Value: `v=spf1 include:spf.protection.outlook.com -all`</span></span>
- <span data-ttu-id="23438-172">TTL: `3600‎` (o il provider predefinito)</span><span class="sxs-lookup"><span data-stu-id="23438-172">TTL: `3600‎` (or your provider default)</span></span>

<span data-ttu-id="23438-173">Salvare il record.</span><span class="sxs-lookup"><span data-stu-id="23438-173">Save the record.</span></span>

<span data-ttu-id="23438-174">Convalidare il record SPF usando uno di questi [strumenti di convalida SPF](https://docs.microsoft.com/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain)</span><span class="sxs-lookup"><span data-stu-id="23438-174">Validate your SPF record by using one of these [SPF validation tools](https://docs.microsoft.com/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain)</span></span>

<span data-ttu-id="23438-175">SPF è progettata per prevenire spoofing, ma esistono tecniche spoofing che SPF non è in grado di evitare.</span><span class="sxs-lookup"><span data-stu-id="23438-175">SPF is designed to help prevent spoofing, but there are spoofing techniques that SPF cannot protect against.</span></span> <span data-ttu-id="23438-176">Per proteggersi da queste minacce, dopo aver configurato SPF è consigliabile impostare anche DKIM e DMARC per Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="23438-176">To protect against these, once you've set up SPF, you should also set up DKIM and DMARC for Microsoft 365.</span></span> 

<span data-ttu-id="23438-177">Per iniziare, vedere [Usare DKIM per convalidare la posta elettronica in uscita inviata dal proprio dominio in Microsoft 365](https://technet.microsoft.com/library/mt695945%28v=exchg.150%29.aspx) e [Usare DKIM per convalidare la posta elettronica in Microsoft 365](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="23438-177">To get started, see [Use DKIM to validate outbound email sent from your domain in Microsoft 365](https://technet.microsoft.com/library/mt695945%28v=exchg.150%29.aspx) and [Use DMARC to validate email in Microsoft 365](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx).</span></span>

### <a name="add-srv-records-for-communications-services-teams-skype-for-business"></a><span data-ttu-id="23438-178">Aggiungere record SRV per servizi di comunicazione (Teams, Skype for Business)</span><span class="sxs-lookup"><span data-stu-id="23438-178">Add SRV records for communications services (Teams, Skype for Business)</span></span>

<span data-ttu-id="23438-179">Nel sito Web del provider di hosting, aggiungere i record SRV per ogni servizio che si vuole connettere.</span><span class="sxs-lookup"><span data-stu-id="23438-179">On your hosting provider's website, add SRV records for each service you want to connect.</span></span>
<span data-ttu-id="23438-180">Verificare che i campi siano impostati sui valori seguenti per ciascun:</span><span class="sxs-lookup"><span data-stu-id="23438-180">Make sure that the fields are set to the following values for each:</span></span>

- <span data-ttu-id="23438-181">Tipo di record: `SRV (Service)`</span><span class="sxs-lookup"><span data-stu-id="23438-181">Record Type: `SRV (Service)`</span></span>
- <span data-ttu-id="23438-182">Nome: `@`</span><span class="sxs-lookup"><span data-stu-id="23438-182">Name: `@`</span></span>
- <span data-ttu-id="23438-183">Destinazione: copiare il valore dall'interfaccia di amministrazione e incollarlo qui.</span><span class="sxs-lookup"><span data-stu-id="23438-183">Target: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="23438-184">Protocollo: copiare il valore dall'interfaccia di amministrazione e incollarlo qui.</span><span class="sxs-lookup"><span data-stu-id="23438-184">Protocol: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="23438-185">Servizio: copiare il valore dall'interfaccia di amministrazione e incollarlo qui.</span><span class="sxs-lookup"><span data-stu-id="23438-185">Service: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="23438-186">Priorità: `100`</span><span class="sxs-lookup"><span data-stu-id="23438-186">Priority: `100`</span></span>
- <span data-ttu-id="23438-187">Peso: `1`</span><span class="sxs-lookup"><span data-stu-id="23438-187">Weight: `1`</span></span>
- <span data-ttu-id="23438-188">Porta: copiare il valore dall'interfaccia di amministrazione e incollarlo qui.</span><span class="sxs-lookup"><span data-stu-id="23438-188">Port: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="23438-189">TTL: `3600‎` (o il provider predefinito)</span><span class="sxs-lookup"><span data-stu-id="23438-189">TTL: `3600‎` (or your provider default)</span></span>

<span data-ttu-id="23438-190">Salvare il record.</span><span class="sxs-lookup"><span data-stu-id="23438-190">Save the record.</span></span>

#### <a name="srv-record-field-restrictions-and-workarounds"></a><span data-ttu-id="23438-191">Restrizioni del campo SRV e soluzioni alternative</span><span class="sxs-lookup"><span data-stu-id="23438-191">SRV record field restrictions and workarounds</span></span>
<span data-ttu-id="23438-192">Alcuni provider di hosting impongono restrizioni sui valori dei campi all'interno dei record SRV.</span><span class="sxs-lookup"><span data-stu-id="23438-192">Some hosting providers impose restrictions on field values within SRV records.</span></span> <span data-ttu-id="23438-193">Di seguito sono riportate alcune soluzioni alternative comuni per queste restrizioni.</span><span class="sxs-lookup"><span data-stu-id="23438-193">Here are some common workarounds for these restrictions.</span></span>

##### <a name="name"></a><span data-ttu-id="23438-194">Nome</span><span class="sxs-lookup"><span data-stu-id="23438-194">Name</span></span>
<span data-ttu-id="23438-195">Se il provider di hosting non consente di configurare questo campo per **@**, lasciarlo vuoto.</span><span class="sxs-lookup"><span data-stu-id="23438-195">If your hosting provider doesn't allow setting this field to **@**, leave it blank.</span></span> <span data-ttu-id="23438-196">Usare questo approccio *solo* quando il provider di hosting ha campi distinti per i valori Servizio e Protocollo.</span><span class="sxs-lookup"><span data-stu-id="23438-196">Use this approach *only* when your hosting provider has separate fields for the Service and Protocol values.</span></span> <span data-ttu-id="23438-197">Altrimenti, vedere la nota sui valori Servizio e Protocollo di seguito.</span><span class="sxs-lookup"><span data-stu-id="23438-197">Otherwise, see the Service and Protocol notes below.</span></span>

##### <a name="service-and-protocol"></a><span data-ttu-id="23438-198">Servizio e Protocollo</span><span class="sxs-lookup"><span data-stu-id="23438-198">Service and Protocol</span></span>
<span data-ttu-id="23438-199">Se presso il provider di hosting non sono disponibili questi campi per i record SRV, è necessario specificare i valori **Servizio** e **Protocollo** nel campo **Nome** del record.</span><span class="sxs-lookup"><span data-stu-id="23438-199">If your hosting provider doesn't provide these fields for SRV records, you must specify the **Service** and **Protocol** values in the record's **Name** field.</span></span> <span data-ttu-id="23438-200">Nota: a seconda del provider di hosting, il campo **Nome** potrebbe avere una denominazione diversa, ad esempio **Host**, **Nome host** o **Sottodominio**. Per aggiungere questi valori, creare una singola stringa, separando i valori con un punto.</span><span class="sxs-lookup"><span data-stu-id="23438-200">(Note: Depending on your hosting provider, the **Name** field might be called something else, like: **Host**, **Hostname**, or **Subdomain**.) To add these values, you create a single string, separating the values with a dot.</span></span> 

<span data-ttu-id="23438-201">Esempio: `_sip._tls`</span><span class="sxs-lookup"><span data-stu-id="23438-201">Example: `_sip._tls`</span></span>

##### <a name="priority-weight-and-port-br"></a><span data-ttu-id="23438-202">Priorità, Peso e Porta</span><span class="sxs-lookup"><span data-stu-id="23438-202">Priority, Weight, and Port</span></span> <br>
<span data-ttu-id="23438-203">Se presso il provider di hosting non sono disponibili questi campi per i record SRV, è necessario specificarli nel campo **Destinazione** del record.</span><span class="sxs-lookup"><span data-stu-id="23438-203">If your hosting provider doesn't provide these fields for SRV records, you must specify them in the record's **Target** field.</span></span> <span data-ttu-id="23438-204">Nota: a seconda del provider di hosting, il campo **Destinazione** potrebbe avere una denominazione diversa, ad esempio **Contenuto**, **Indirizzo IP** o **Host di destinazione**.</span><span class="sxs-lookup"><span data-stu-id="23438-204">(Note: Depending on your hosting provider, the **Target** field might be called something else, like: **Content**, **IP Address**, or **Target Host**.)</span></span> 

<span data-ttu-id="23438-205">Per aggiungere questi valori, creare una singola stringa, separando i valori con spazi e *a volte terminando con un punto* (rivolgersi al provider in caso di dubbi).</span><span class="sxs-lookup"><span data-stu-id="23438-205">To add these values, create a single string, separating the values with spaces and *sometimes ending with a dot* (check with your provider if you are unsure).</span></span> <span data-ttu-id="23438-206">I valori devono essere inclusi in questo ordine: Priorità, Peso, Porta, Destinazione.</span><span class="sxs-lookup"><span data-stu-id="23438-206">The values must be included in this order: Priority, Weight, Port, Target.</span></span> 

- <span data-ttu-id="23438-207">Esempio 1: `100 1 443 sipdir.online.lync.com.`</span><span class="sxs-lookup"><span data-stu-id="23438-207">Example 1: `100 1 443 sipdir.online.lync.com.`</span></span>
- <span data-ttu-id="23438-208">Esempio 2: `100 1 443 sipdir.online.lync.com`</span><span class="sxs-lookup"><span data-stu-id="23438-208">Example 2: `100 1 443 sipdir.online.lync.com`</span></span>
