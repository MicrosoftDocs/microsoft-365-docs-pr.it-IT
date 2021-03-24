---
title: Connettere il proprio dominio a Microsoft 365
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
ROBOTS: NOINDEX, NOFOLLOW
description: Informazioni su come verificare il dominio e creare record DNS con Microsoft 365.
ms.custom:
- AdminSurgePortfolio
ms.openlocfilehash: 95b1caadfe0e5b331b2bd777263bd86a88bb581f
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51050655"
---
# <a name="connect-your-domain-to-microsoft-365"></a><span data-ttu-id="4b794-103">Connettere il proprio dominio a Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4b794-103">Connect your domain to Microsoft 365</span></span>

> [!NOTE]
> <span data-ttu-id="4b794-104">Finché non verrà aggiunto un dominio, gli utenti dell'organizzazione useranno onmicrosoft.com per gli indirizzi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="4b794-104">If you don't add a domain, people in your organization will use the onmicrosoft.com domain for their email addresses until you do.</span></span> <span data-ttu-id="4b794-105">È importante aggiungere il dominio prima di aggiungere utenti, per evitare una doppia configurazione.</span><span class="sxs-lookup"><span data-stu-id="4b794-105">It's important to add your domain before you add users, so you don't have to set them up twice.</span></span>

<span data-ttu-id="4b794-106">Se non si trova ciò che si sta cercando, [vedere le domande frequenti sui domini](../setup/domains-faq.yml).</span><span class="sxs-lookup"><span data-stu-id="4b794-106">[Check the Domains FAQ](../setup/domains-faq.yml) if you don't find what you're looking for below.</span></span>

## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="4b794-107">Aggiungere un record MX in modo che la posta elettronica del dominio venga recapitata in Microsoft</span><span class="sxs-lookup"><span data-stu-id="4b794-107">Add an MX record so email for your domain will come to Microsoft</span></span>

<span data-ttu-id="4b794-108">Le informazioni per il record MX saranno disponibili durante la configurazione dominio guidata dell'interfaccia di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="4b794-108">You'll get the information for the MX record from the admin center domain setup wizard.</span></span>

<span data-ttu-id="4b794-109">Nel sito Web del provider di hosting, aggiungere un nuovo record MX.</span><span class="sxs-lookup"><span data-stu-id="4b794-109">On your hosting provider's website, add a new MX record.</span></span>
<span data-ttu-id="4b794-110">Verificare che i campi siano impostati sui valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="4b794-110">Make sure that the fields are set to the following values:</span></span>

- <span data-ttu-id="4b794-111">Tipo di record: `MX`</span><span class="sxs-lookup"><span data-stu-id="4b794-111">Record Type: `MX`</span></span>
- <span data-ttu-id="4b794-112">Priorità: impostare sul valore massimo disponibile, in genere `0`.</span><span class="sxs-lookup"><span data-stu-id="4b794-112">Priority: Set to the highest value available, typically `0`.</span></span>
- <span data-ttu-id="4b794-113">Nome host: `@`</span><span class="sxs-lookup"><span data-stu-id="4b794-113">Host Name: `@`</span></span>
- <span data-ttu-id="4b794-114">Indirizzo di puntamento: copiare il valore dall'interfaccia di amministrazione e incollarlo qui.</span><span class="sxs-lookup"><span data-stu-id="4b794-114">Points to address: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="4b794-115">TTL: `3600‎` (o il provider predefinito)</span><span class="sxs-lookup"><span data-stu-id="4b794-115">TTL: `3600‎` (or your provider default)</span></span>

<span data-ttu-id="4b794-116">Salvare il record, quindi rimuovere qualsiasi altro record MX.</span><span class="sxs-lookup"><span data-stu-id="4b794-116">Save the record, and then remove any other MX records.</span></span>

## <a name="add-a-cname-record-to-connect-users-to-their-mailboxes"></a><span data-ttu-id="4b794-117">Aggiungere un record CNAME per connettere gli utenti alle rispettive cassette postali</span><span class="sxs-lookup"><span data-stu-id="4b794-117">Add a CNAME record to connect users to their mailboxes</span></span>
<span data-ttu-id="4b794-118">Le informazioni per i record CNAME saranno disponibili durante la configurazione dominio guidata dell'interfaccia di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="4b794-118">You'll get the information for the CNAME records from the admin center domain setup wizard.</span></span>

<span data-ttu-id="4b794-119">Nel sito Web del provider di hosting, aggiungere il record CNAME seguente.</span><span class="sxs-lookup"><span data-stu-id="4b794-119">On your hosting provider's website, add the following CNAME record.</span></span> <span data-ttu-id="4b794-120">Verificare che i campi siano impostati sui valori seguenti per ciascun:</span><span class="sxs-lookup"><span data-stu-id="4b794-120">Make sure that the fields are set to the following values for each:</span></span>

- <span data-ttu-id="4b794-121">Tipo di record: `CNAME (Alias)`</span><span class="sxs-lookup"><span data-stu-id="4b794-121">Record Type: `CNAME (Alias)`</span></span>
- <span data-ttu-id="4b794-122">Host: incollare qui i valori copiati dall'interfaccia di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="4b794-122">Host: Paste the values you copy from the admin center here.</span></span>
- <span data-ttu-id="4b794-123">Indirizzo di puntamento: copiare il valore dall'interfaccia di amministrazione e incollarlo qui.</span><span class="sxs-lookup"><span data-stu-id="4b794-123">Points to address: Copy the value from the admin center and paste it here.</span></span>
- <span data-ttu-id="4b794-124">TTL: `3600‎` (o il provider predefinito)</span><span class="sxs-lookup"><span data-stu-id="4b794-124">TTL: `3600‎` (or your provider default)</span></span>

## <a name="add-a-txt-record-to-help-prevent-spam"></a><span data-ttu-id="4b794-125">Aggiungere un record TXT per evitare di ricevere posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="4b794-125">Add a TXT record to help prevent spam</span></span>
<span data-ttu-id="4b794-126">**Prima di iniziare:** se si dispone già di un record SPF per il dominio, non crearne uno nuovo per Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4b794-126">**Before you begin:** If you already have an SPF record for your domain, don't create a new one for Microsoft 365.</span></span> <span data-ttu-id="4b794-127">Aggiungere invece i valori di Microsoft 365 necessari al record corrente nel sito Web del provider di hosting, in modo da ottenere un *unico* record SPF che includa entrambi i set di valori.</span><span class="sxs-lookup"><span data-stu-id="4b794-127">Instead, add the required Microsoft 365 values to the current record on your hosting providers website so that you have a *single* SPF record that includes both sets of values.</span></span>

<span data-ttu-id="4b794-128">Nel sito Web del provider di hosting, creare un record SPF o modificarne uno esistente.</span><span class="sxs-lookup"><span data-stu-id="4b794-128">On your hosting provider's website, edit the existing SPF record or create an SPF record.</span></span>
<span data-ttu-id="4b794-129">Verificare che i campi siano impostati sui valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="4b794-129">Make sure that the fields are set to the following values:</span></span>

- <span data-ttu-id="4b794-130">Tipo di record: `TXT (Text)`</span><span class="sxs-lookup"><span data-stu-id="4b794-130">Record Type: `TXT (Text)`</span></span>
- <span data-ttu-id="4b794-131">Host: `@`</span><span class="sxs-lookup"><span data-stu-id="4b794-131">Host: `@`</span></span>
- <span data-ttu-id="4b794-132">Valore TXT: `v=spf1 include:spf.protection.outlook.com -all`</span><span class="sxs-lookup"><span data-stu-id="4b794-132">TXT Value: `v=spf1 include:spf.protection.outlook.com -all`</span></span>
- <span data-ttu-id="4b794-133">TTL: `3600‎` (o il provider predefinito)</span><span class="sxs-lookup"><span data-stu-id="4b794-133">TTL: `3600‎` (or your provider default)</span></span>

<span data-ttu-id="4b794-134">Salvare il record.</span><span class="sxs-lookup"><span data-stu-id="4b794-134">Save the record.</span></span>

<span data-ttu-id="4b794-135">Convalidare il record SPF usando uno di questi [strumenti di convalida SPF](/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain)</span><span class="sxs-lookup"><span data-stu-id="4b794-135">Validate your SPF record by using one of these [SPF validation tools](/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain)</span></span>

<span data-ttu-id="4b794-136">SPF è progettata per prevenire spoofing, ma esistono tecniche spoofing che SPF non è in grado di evitare.</span><span class="sxs-lookup"><span data-stu-id="4b794-136">SPF is designed to help prevent spoofing, but there are spoofing techniques that SPF cannot protect against.</span></span> <span data-ttu-id="4b794-137">Per proteggersi da queste minacce, dopo aver configurato SPF è consigliabile impostare anche DKIM e DMARC per Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4b794-137">To protect against these, once you've set up SPF, you should also set up DKIM and DMARC for Microsoft 365.</span></span>

<span data-ttu-id="4b794-138">Per iniziare, vedere [Usare DKIM per convalidare la posta elettronica in uscita inviata dal proprio dominio in Microsoft 365](../../security/defender-365-security/use-dkim-to-validate-outbound-email.md) e [Usare DKIM per convalidare la posta elettronica in Microsoft 365](../../security/defender-365-security/use-dmarc-to-validate-email.md).</span><span class="sxs-lookup"><span data-stu-id="4b794-138">To get started, see [Use DKIM to validate outbound email sent from your domain in Microsoft 365](../../security/defender-365-security/use-dkim-to-validate-outbound-email.md) and [Use DMARC to validate email in Microsoft 365](../../security/defender-365-security/use-dmarc-to-validate-email.md).</span></span>

<span data-ttu-id="4b794-139">Infine, tornare configurazione dominio guidata dell'interfaccia di amministrazione per completare la configurazione.</span><span class="sxs-lookup"><span data-stu-id="4b794-139">Finally, head back to the admin center domain setup wizard to complete your setup.</span></span>