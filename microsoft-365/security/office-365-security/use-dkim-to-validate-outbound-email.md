---
title: Come usare DKIM per la posta elettronica nel dominio personalizzato
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 04/05/2021
audience: ITPro
ms.topic: article
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 56fee1c7-dc37-470e-9b09-33fff6d94617
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Informazioni su come usare DomainKeys Identified Mail (DKIM) insieme a Microsoft 365 per garantire che i sistemi di posta elettronica di destinazione ritengano attendibili i messaggi inviati dal dominio personalizzato.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5b5122984969113ec0c0533952ea3bf18bff5e5c
ms.sourcegitcommit: e0a96e08b7dc29e074065e69a2a86fc3cf0dad01
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/06/2021
ms.locfileid: "51592109"
---
# <a name="use-dkim-to-validate-outbound-email-sent-from-your-custom-domain"></a><span data-ttu-id="5f6ee-103">Usare DKIM per convalidare la posta elettronica in uscita inviata dal dominio personalizzato</span><span class="sxs-lookup"><span data-stu-id="5f6ee-103">Use DKIM to validate outbound email sent from your custom domain</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="5f6ee-104">**Si applica a**</span><span class="sxs-lookup"><span data-stu-id="5f6ee-104">**Applies to**</span></span>
- [<span data-ttu-id="5f6ee-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="5f6ee-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="5f6ee-106">Microsoft Defender per Office 365 piano 1 e piano 2</span><span class="sxs-lookup"><span data-stu-id="5f6ee-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="5f6ee-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5f6ee-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

 <span data-ttu-id="5f6ee-108">**Riepilogo:** in questo articolo viene illustrato come usare DomainKeys Identified Mail (DKIM) insieme a Microsoft 365 per garantire che i sistemi di posta elettronica di destinazione ritengano attendibili i messaggi in uscita inviati dal dominio personalizzato.</span><span class="sxs-lookup"><span data-stu-id="5f6ee-108">**Summary:** This article describes how you use DomainKeys Identified Mail (DKIM) with Microsoft 365 to ensure that destination email systems trust messages sent outbound from your custom domain.</span></span>

<span data-ttu-id="5f6ee-109">È necessario utilizzare DKIM in aggiunta a SPF e DMARC per impedire agli spoofer di inviare messaggi che sembrano provenire dal proprio dominio.</span><span class="sxs-lookup"><span data-stu-id="5f6ee-109">You should use DKIM in addition to SPF and DMARC to help prevent spoofers from sending messages that look like they are coming from your domain.</span></span> <span data-ttu-id="5f6ee-110">DKIM consente di aggiungere una firma digitale nell'intestazione dei messaggi di posta elettronica in uscita.</span><span class="sxs-lookup"><span data-stu-id="5f6ee-110">DKIM lets you add a digital signature to outbound email messages in the message header.</span></span> <span data-ttu-id="5f6ee-111">Non è complicato come sembra.</span><span class="sxs-lookup"><span data-stu-id="5f6ee-111">It may sound complicated, but it's really not.</span></span> <span data-ttu-id="5f6ee-112">Quando si configura DKIM, il dominio viene autorizzato ad associare (oppure firmare) il proprio nome ai messaggi di posta elettronica utilizzando l'autenticazione di crittografia.</span><span class="sxs-lookup"><span data-stu-id="5f6ee-112">When you configure DKIM, you authorize your domain to associate, or sign, its name to an email message by using cryptographic authentication.</span></span> <span data-ttu-id="5f6ee-113">I sistemi di posta elettronica che ricevono messaggi dal dominio dell'utente possono utilizzare questa firma digitale per stabilire la legittimità del messaggio ricevuto.</span><span class="sxs-lookup"><span data-stu-id="5f6ee-113">Email systems that receive email from your domain can use this digital signature to help determine if incoming email that they receive is legitimate.</span></span>

<span data-ttu-id="5f6ee-114">In sostanza, si utilizza una chiave privata per crittografare l'intestazione nel messaggio di posta elettronica in uscita dal proprio dominio.</span><span class="sxs-lookup"><span data-stu-id="5f6ee-114">Basically, you use a private key to encrypt the header in your domain's outgoing email.</span></span> <span data-ttu-id="5f6ee-115">Nei record DNS del dominio viene pubblicata una chiave pubblica utilizzata dai server di ricezione per decodificare la firma.</span><span class="sxs-lookup"><span data-stu-id="5f6ee-115">You publish a public key to your domain's DNS records that receiving servers can then use to decode the signature.</span></span> <span data-ttu-id="5f6ee-116">La chiave pubblica viene usata per verificare che i messaggi provengano realmente dall'utente e non da qualche operazione di *spoofing* in atto nel dominio.</span><span class="sxs-lookup"><span data-stu-id="5f6ee-116">They use the public key to verify that the messages are really coming from you and not coming from someone *spoofing* your domain.</span></span>

<span data-ttu-id="5f6ee-117">Microsoft 365 configura automaticamente DKIM per i domini "onmicrosoft.com" iniziali.</span><span class="sxs-lookup"><span data-stu-id="5f6ee-117">Microsoft 365 automatically sets up DKIM for its initial 'onmicrosoft.com' domains.</span></span> <span data-ttu-id="5f6ee-118">Questo vuol dire che non è necessario eseguire alcuna operazione per configurare DKIM per il nome di dominio iniziale, ad esempio litware.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="5f6ee-118">That means you don't need to do anything to set up DKIM for any initial domain names (for example, litware.onmicrosoft.com).</span></span> <span data-ttu-id="5f6ee-119">Per ulteriori informazioni sui domini, vedere [Domande frequenti sui domini](../../admin/setup/domains-faq.yml#why-do-i-have-an--onmicrosoft-com--domain).</span><span class="sxs-lookup"><span data-stu-id="5f6ee-119">For more information about domains, see [Domains FAQ](../../admin/setup/domains-faq.yml#why-do-i-have-an--onmicrosoft-com--domain).</span></span>

<span data-ttu-id="5f6ee-120">È possibile scegliere di non eseguire nessuna operazione su DKIM anche per il dominio personalizzato.</span><span class="sxs-lookup"><span data-stu-id="5f6ee-120">You can choose to do nothing about DKIM for your custom domain too.</span></span> <span data-ttu-id="5f6ee-121">Se non si configura DKIM per il dominio personalizzato, Microsoft 365 crea una coppia di chiavi pubblica e privata, abilita la firma DKIM e configura il criterio predefinito di Microsoft 365 per il dominio personalizzato.</span><span class="sxs-lookup"><span data-stu-id="5f6ee-121">If you don't set up DKIM for your custom domain, Microsoft 365 creates a private and public key pair, enables DKIM signing, and then configures the Microsoft 365 default policy for your custom domain.</span></span> <span data-ttu-id="5f6ee-122">Sebbene questa configurazione sia sufficiente per la maggior parte dei clienti, è necessario configurare manualmente la chiave DKIM per il dominio personalizzato nei casi seguenti:</span><span class="sxs-lookup"><span data-stu-id="5f6ee-122">While this is sufficient coverage for most customers, you should manually configure DKIM for your custom domain in the following circumstances:</span></span>

- <span data-ttu-id="5f6ee-123">Sono disponibili più domini personalizzati in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5f6ee-123">You have more than one custom domain in Microsoft 365</span></span>

- <span data-ttu-id="5f6ee-124">Si intende configurare anche DMARC (consigliato)</span><span class="sxs-lookup"><span data-stu-id="5f6ee-124">You're going to set up DMARC too (recommended)</span></span>

- <span data-ttu-id="5f6ee-125">Si desidera gestire la chiave privata</span><span class="sxs-lookup"><span data-stu-id="5f6ee-125">You want control over your private key</span></span>

- <span data-ttu-id="5f6ee-126">Si desidera personalizzare i record CNAME</span><span class="sxs-lookup"><span data-stu-id="5f6ee-126">You want to customize your CNAME records</span></span>

- <span data-ttu-id="5f6ee-127">Si configurano le chiavi DKIM per la posta elettronica creata da un dominio di terze parti, ad esempio, un mailer di massa di terze parti.</span><span class="sxs-lookup"><span data-stu-id="5f6ee-127">You want to set up DKIM keys for email originating out of a third-party domain, for example, if you use a third-party bulk mailer.</span></span>

<span data-ttu-id="5f6ee-128">Contenuto dell'articolo:</span><span class="sxs-lookup"><span data-stu-id="5f6ee-128">In this article:</span></span>

- [<span data-ttu-id="5f6ee-129">In che modo DKIM è più efficace della sola estensione SPF nel prevenire lo spoofing dannoso</span><span class="sxs-lookup"><span data-stu-id="5f6ee-129">How DKIM works better than SPF alone to prevent malicious spoofing</span></span>](use-dkim-to-validate-outbound-email.md#HowDKIMWorks)

- [<span data-ttu-id="5f6ee-130">Procedura per aggiornare manualmente le chiavi a 1024 bit in chiavi di crittografia DKIM a 2048 bit</span><span class="sxs-lookup"><span data-stu-id="5f6ee-130">Steps to manually upgrade your 1024-bit keys to 2048-bit DKIM encryption keys</span></span>](use-dkim-to-validate-outbound-email.md#1024to2048DKIM)

- [<span data-ttu-id="5f6ee-131">Procedura necessaria per configurare manualmente DKIM</span><span class="sxs-lookup"><span data-stu-id="5f6ee-131">Steps you need to do to manually set up DKIM</span></span>](use-dkim-to-validate-outbound-email.md#SetUpDKIMO365)

- [<span data-ttu-id="5f6ee-132">Procedura per configurare DKIM per più domini personalizzati</span><span class="sxs-lookup"><span data-stu-id="5f6ee-132">Steps to configure DKIM for more than one custom domain</span></span>](use-dkim-to-validate-outbound-email.md#DKIMMultiDomain)

- [<span data-ttu-id="5f6ee-133">Disabilitazione del criterio di firma DKIM per un dominio personalizzato</span><span class="sxs-lookup"><span data-stu-id="5f6ee-133">Disabling the DKIM signing policy for a custom domain</span></span>](use-dkim-to-validate-outbound-email.md#DisableDKIMSigningPolicy)

- [<span data-ttu-id="5f6ee-134">Comportamento predefinito per DKIM e Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5f6ee-134">Default behavior for DKIM and Microsoft 365</span></span>](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior)

- [<span data-ttu-id="5f6ee-135">Configurare DKIM in modo che un servizio di terze parti possa inviare la posta elettronica o effettuarne lo spoofing per conto del dominio personalizzato dell'utente</span><span class="sxs-lookup"><span data-stu-id="5f6ee-135">Set up DKIM so that a third-party service can send, or spoof, email on behalf of your custom domain</span></span>](use-dkim-to-validate-outbound-email.md#SetUp3rdPartyspoof)

- [<span data-ttu-id="5f6ee-136">Passaggi successivi: dopo aver configurato DKIM per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5f6ee-136">Next steps: After you set up DKIM for Microsoft 365</span></span>](use-dkim-to-validate-outbound-email.md#DKIMNextSteps)

## <a name="how-dkim-works-better-than-spf-alone-to-prevent-malicious-spoofing"></a><span data-ttu-id="5f6ee-137">In che modo DKIM è più efficace della sola estensione SPF nel prevenire lo spoofing dannoso</span><span class="sxs-lookup"><span data-stu-id="5f6ee-137">How DKIM works better than SPF alone to prevent malicious spoofing</span></span>
<span data-ttu-id="5f6ee-138"><a name="HowDKIMWorks"> </a></span><span class="sxs-lookup"><span data-stu-id="5f6ee-138"><a name="HowDKIMWorks"> </a></span></span>

<span data-ttu-id="5f6ee-p105">SPF consente di aggiungere informazioni alla busta del messaggio, ma DKIM esegue la crittografia di una firma all'interno dell'intestazione del messaggio. Quando si inoltra un messaggio, alcune parti della busta possono essere eliminate dal server di inoltro. Dal momento che la firma digitale rimane unita al messaggio di posta elettronica perché fa parte dell'intestazione, DKIM funziona anche quando un messaggio è stato inoltrato come mostrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="5f6ee-p105">SPF adds information to a message envelope but DKIM actually encrypts a signature within the message header. When you forward a message, portions of that message's envelope can be stripped away by the forwarding server. Since the digital signature stays with the email message because it's part of the email header, DKIM works even when a message has been forwarded as shown in the following example.</span></span>

![Diagramma che mostra il messaggio inoltrato che supera l'autenticazione DKIM anche se il controllo SPF ha esito negativo](../../media/28f93b4c-97e7-4309-acc4-fd0d2e0e3377.jpg)

<span data-ttu-id="5f6ee-p106">In questo esempio, se è stato pubblicato soltanto un record SPF TXT per il dominio, il server di posta del mittente avrebbe potuto contrassegnare la posta come indesiderata e generare un risultato falso positivo. L'aggiunta di DKIM in questo scenario riduce i rapporti spam falsi positivi. Dal momento che DKIM si affida alla crittografia della chiave pubblica per eseguire l'autenticazione e non soltanto agli indirizzi IP, la chiave DKIM è considerata come una forma di autenticazione più affidabile rispetto a SPF. È opportuno utilizzare sia SPF che DKIM e DMARC nella propria distribuzione.</span><span class="sxs-lookup"><span data-stu-id="5f6ee-p106">In this example, if you had only published an SPF TXT record for your domain, the recipient's mail server could have marked your email as spam and generated a false positive result. The addition of DKIM in this scenario reduces false positive spam reporting. Because DKIM relies on public key cryptography to authenticate and not just IP addresses, DKIM is considered a much stronger form of authentication than SPF. We recommend using both SPF and DKIM, as well as DMARC in your deployment.</span></span>

<span data-ttu-id="5f6ee-p107">In sostanza, DKIM utilizza una chiave privata per inserire una firma crittografata all'interno delle intestazioni dei messaggi. Il dominio di firma o dominio di uscita viene inserito come valore del campo **d=** nell'intestazione. Il dominio di verifica o dominio del destinatario utilizza il campo **d=** per cercare la chiave pubblica dal DNS ed esegue l'autenticazione del messaggio. Se il messaggio viene verificato, i controlli DKIM hanno esito positivo.</span><span class="sxs-lookup"><span data-stu-id="5f6ee-p107">The nitty gritty: DKIM uses a private key to insert an encrypted signature into the message headers. The signing domain, or outbound domain, is inserted as the value of the **d=** field in the header. The verifying domain, or recipient's domain, then use the **d=** field to look up the public key from DNS and authenticate the message. If the message is verified, the DKIM check passes.</span></span>

## <a name="steps-to-manually-upgrade-your-1024-bit-keys-to-2048-bit-dkim-encryption-keys"></a><span data-ttu-id="5f6ee-151">Procedura per aggiornare manualmente le chiavi a 1024 bit in chiavi di crittografia DKIM a 2048 bit</span><span class="sxs-lookup"><span data-stu-id="5f6ee-151">Steps to manually upgrade your 1024-bit keys to 2048-bit DKIM encryption keys</span></span>
<span data-ttu-id="5f6ee-152"><a name="1024to2048DKIM"> </a></span><span class="sxs-lookup"><span data-stu-id="5f6ee-152"><a name="1024to2048DKIM"> </a></span></span>

<span data-ttu-id="5f6ee-153">Dal momento che sono supportate le chiavi di crittografia DKIM sia a 1024 che a 2048 bit, queste indicazioni sono per l'aggiornamento da 1024 bit a 2048 in [PowerShell per Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="5f6ee-153">Since both 1024 and 2048 bitness are supported for DKIM keys, these directions will tell you how to upgrade your 1024-bit key to 2048 in [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="5f6ee-154">La procedure seguenti si riferiscono a due casi di utilizzo, scegliere quella più idonea alla configurazione in uso.</span><span class="sxs-lookup"><span data-stu-id="5f6ee-154">The steps below are for two use-cases, please choose the one that best fits your configuration.</span></span>

- <span data-ttu-id="5f6ee-155">Quando **DKIM è già configurato**, per modificare (ruotare) il numero di bit eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="5f6ee-155">When you **already have DKIM configured**, you rotate bitness by running the following command:</span></span>

  ```powershell
  Rotate-DkimSigningConfig -KeySize 2048 -Identity {Guid of the existing Signing Config}
  ```

  <span data-ttu-id="5f6ee-156">**oppure**</span><span class="sxs-lookup"><span data-stu-id="5f6ee-156">**or**</span></span>

- <span data-ttu-id="5f6ee-157">Per una **nuova implementazione di DKIM**, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="5f6ee-157">For a **new implementation of DKIM**, run the following command:</span></span>

  ```powershell
  New-DkimSigningConfig -DomainName <Domain for which config is to be created> -KeySize 2048 -Enabled $true
  ```

<span data-ttu-id="5f6ee-158">Rimanere connessi a PowerShell per Exchange Online per *verificare* la configurazione eseguendo il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="5f6ee-158">Stay connected to Exchange Online PowerShell to *verify* the configuration by running the following command:</span></span>

```powershell
Get-DkimSigningConfig -Identity <Domain for which the configuration was set> | Format-List
```

> [!TIP]
> <span data-ttu-id="5f6ee-159">Questa nuova chiave a 2048 bit verrà applicata in data RotateOnDate e, nel frattempo, i messaggi di posta elettronica verranno inviati con la chiave a 1024 bit.</span><span class="sxs-lookup"><span data-stu-id="5f6ee-159">This new 2048-bit key takes effect on the RotateOnDate, and will send emails with the 1024-bit key in the interim.</span></span> <span data-ttu-id="5f6ee-160">Dopo quattro giorni, ossia dopo l'applicazione della modifica al secondo selettore, è possibile eseguire di nuovo il test con la chiave a 2048 bit.</span><span class="sxs-lookup"><span data-stu-id="5f6ee-160">After four days, you can test again with the 2048-bit key (that is, once the rotation takes effect to the second selector).</span></span>

<span data-ttu-id="5f6ee-161">Se si vuole ruotare il secondo selettore, le possibilità sono due. La prima è lasciare che sia il servizio di Microsoft 365 a ruotare il selettore ed eseguire l'aggiornamento ai 2048 bit nei 6 mesi successivi. La seconda è, dopo 4 giorni e dopo aver verificato che sia in uso la chiave a 2048 bit, ruotare manualmente il secondo selettore usando l'appropriato cmdlet sopra elencato.</span><span class="sxs-lookup"><span data-stu-id="5f6ee-161">If you want to rotate to the second selector, your options are a) let the Microsoft 365 service rotate the selector and upgrade to 2048-bitness within the next 6 months, or b) after 4 days and confirming that 2048-bitness is in use, manually rotate the second selector key by using the appropriate cmdlet listed above.</span></span>

<span data-ttu-id="5f6ee-162">Per informazioni dettagliate sulla sintassi e sui parametri, vedere gli articoli seguenti: [Rotate-DkimSigningConfig](/powershell/module/exchange/rotate-dkimsigningconfig), [New-DkimSigningConfig](/powershell/module/exchange/new-dkimsigningconfig) e [Get-DkimSigningConfig](/powershell/module/exchange/get-dkimsigningconfig).</span><span class="sxs-lookup"><span data-stu-id="5f6ee-162">For detailed syntax and parameter information, see the following articles: [Rotate-DkimSigningConfig](/powershell/module/exchange/rotate-dkimsigningconfig), [New-DkimSigningConfig](/powershell/module/exchange/new-dkimsigningconfig), and [Get-DkimSigningConfig](/powershell/module/exchange/get-dkimsigningconfig).</span></span>

## <a name="steps-you-need-to-do-to-manually-set-up-dkim"></a><span data-ttu-id="5f6ee-163">Procedura necessaria per configurare manualmente DKIM</span><span class="sxs-lookup"><span data-stu-id="5f6ee-163">Steps you need to do to manually set up DKIM</span></span>
<span data-ttu-id="5f6ee-164"><a name="SetUpDKIMO365"> </a></span><span class="sxs-lookup"><span data-stu-id="5f6ee-164"><a name="SetUpDKIMO365"> </a></span></span>

<span data-ttu-id="5f6ee-165">Per configurare DKIM, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="5f6ee-165">To configure DKIM, you will complete these steps:</span></span>

- [<span data-ttu-id="5f6ee-166">Pubblicare due record CNAME per il dominio personalizzato in DNS</span><span class="sxs-lookup"><span data-stu-id="5f6ee-166">Publish two CNAME records for your custom domain in DNS</span></span>](use-dkim-to-validate-outbound-email.md#Publish2CNAME)

- [<span data-ttu-id="5f6ee-167">Abilitare la firma DKIM per il dominio personalizzato</span><span class="sxs-lookup"><span data-stu-id="5f6ee-167">Enable DKIM signing for your custom domain</span></span>](use-dkim-to-validate-outbound-email.md#EnableDKIMinO365)

### <a name="publish-two-cname-records-for-your-custom-domain-in-dns"></a><span data-ttu-id="5f6ee-168">Pubblicare due record CNAME per il dominio personalizzato in DNS</span><span class="sxs-lookup"><span data-stu-id="5f6ee-168">Publish two CNAME records for your custom domain in DNS</span></span>
<span data-ttu-id="5f6ee-169"><a name="Publish2CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="5f6ee-169"><a name="Publish2CNAME"> </a></span></span>

<span data-ttu-id="5f6ee-170">Per ogni dominio al quale si intende aggiungere una firma DKIM in DNS è necessario pubblicare due record CNAME.</span><span class="sxs-lookup"><span data-stu-id="5f6ee-170">For each domain for which you want to add a DKIM signature in DNS, you need to publish two CNAME records.</span></span>

> [!NOTE]
> <span data-ttu-id="5f6ee-171">Se non si è letto l'articolo completo, probabilmente si sono perse le informazioni rapide sulla connessione a PowerShell: [Connettersi a PowerShell per Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="5f6ee-171">If you haven't read the full article, you may have missed this time-saving PowerShell connection information: [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

<span data-ttu-id="5f6ee-172">Eseguire i comandi seguenti in PowerShell per Exchange Online per creare i record dei selettori:</span><span class="sxs-lookup"><span data-stu-id="5f6ee-172">Run the following commands in Exchange Online PowerShell to create the selector records:</span></span>

```powershell
New-DkimSigningConfig -DomainName <domain> -Enabled $false
Get-DkimSigningConfig -Identity <domain> | Format-List Selector1CNAME, Selector2CNAME
```

<span data-ttu-id="5f6ee-173">Se è stato eseguito il provisioning di domini personalizzati oltre al dominio iniziale in Microsoft 365, è necessario pubblicare due record CNAME per ogni dominio aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="5f6ee-173">If you have provisioned custom domains in addition to the initial domain in Microsoft 365, you must publish two CNAME records for each additional domain.</span></span> <span data-ttu-id="5f6ee-174">Pertanto, se sono disponibili due domini, è necessario pubblicare altri due record CNAME e così via.</span><span class="sxs-lookup"><span data-stu-id="5f6ee-174">So, if you have two domains, you must publish two additional CNAME records, and so on.</span></span>

<span data-ttu-id="5f6ee-175">Per i record CNAME, usare il formato seguente.</span><span class="sxs-lookup"><span data-stu-id="5f6ee-175">Use the following format for the CNAME records.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5f6ee-176">Per i clienti di GCC High, il _domainGuid_ viene calcolato in modo diverso.</span><span class="sxs-lookup"><span data-stu-id="5f6ee-176">If you are one of our GCC High customers, we calculate _domainGuid_ differently!</span></span> <span data-ttu-id="5f6ee-177">Per calcolare il _domainGuid_ non viene più cercato il record MX di _initialDomain_ ma viene calcolato direttamente dal dominio personalizzato.</span><span class="sxs-lookup"><span data-stu-id="5f6ee-177">Instead of looking up the MX record for your _initialDomain_ to calculate _domainGuid_, instead we calculate it directly from the customized domain.</span></span> <span data-ttu-id="5f6ee-178">Ad esempio, se il dominio personalizzato è "contoso.com" il domainGuid diventerà "contoso-com", ovvero i punti verranno sostituiti da un trattino.</span><span class="sxs-lookup"><span data-stu-id="5f6ee-178">For example, if your customized domain is "contoso.com" your domainGuid becomes "contoso-com", any periods are replaced with a dash.</span></span> <span data-ttu-id="5f6ee-179">Per questo motivo, indipendentemente dal record MX a cui punta initialDomain, si userà sempre il metodo riportato sopra per calcolare il domainGuid da usare nei record CNAME.</span><span class="sxs-lookup"><span data-stu-id="5f6ee-179">So, regardless of what MX record your initialDomain points to, you'll always use the above method to calculate the domainGuid to use in your CNAME records.</span></span>

```console
Host name:            selector1._domainkey
Points to address or value:    selector1-<domainGUID>._domainkey.<initialDomain>
TTL:                3600

Host name:            selector2._domainkey
Points to address or value:    selector2-<domainGUID>._domainkey.<initialDomain>
TTL:                3600
```

<span data-ttu-id="5f6ee-180">Dove:</span><span class="sxs-lookup"><span data-stu-id="5f6ee-180">Where:</span></span>

- <span data-ttu-id="5f6ee-181">Per Microsoft 365, i selettori saranno sempre "selector1" o "selector2".</span><span class="sxs-lookup"><span data-stu-id="5f6ee-181">For Microsoft 365, the selectors will always be "selector1" or "selector2".</span></span>

- <span data-ttu-id="5f6ee-182">_domainGUID_ corrisponde al _domainGUID_ nel record MX personalizzato del dominio personalizzato visualizzato prima di mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="5f6ee-182">_domainGUID_ is the same as the _domainGUID_ in the customized MX record for your custom domain that appears before mail.protection.outlook.com.</span></span> <span data-ttu-id="5f6ee-183">Ad esempio, nel seguente record MX per il dominio contoso.com, il _domainGUID_ è contoso-com:</span><span class="sxs-lookup"><span data-stu-id="5f6ee-183">For example, in the following MX record for the domain contoso.com, the _domainGUID_ is contoso-com:</span></span>

  > <span data-ttu-id="5f6ee-184">contoso.com.</span><span class="sxs-lookup"><span data-stu-id="5f6ee-184">contoso.com.</span></span>  <span data-ttu-id="5f6ee-185">3600  IN  MX   5 contoso-com.mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="5f6ee-185">3600  IN  MX   5 contoso-com.mail.protection.outlook.com</span></span>

- <span data-ttu-id="5f6ee-186">_initialDomain_ è il dominio usato al momento dell'iscrizione a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5f6ee-186">_initialDomain_ is the domain that you used when you signed up for Microsoft 365.</span></span> <span data-ttu-id="5f6ee-187">I domini iniziali terminano sempre con onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="5f6ee-187">Initial domains always end in onmicrosoft.com.</span></span> <span data-ttu-id="5f6ee-188">Per informazioni su come determinare il dominio iniziale, vedere [Domande frequenti sui domini](../../admin/setup/domains-faq.yml#why-do-i-have-an--onmicrosoft-com--domain).</span><span class="sxs-lookup"><span data-stu-id="5f6ee-188">For information about determining your initial domain, see [Domains FAQ](../../admin/setup/domains-faq.yml#why-do-i-have-an--onmicrosoft-com--domain).</span></span>

<span data-ttu-id="5f6ee-189">Ad esempio, se si dispone di un dominio iniziale di cohovineyardandwinery.onmicrosoft.com e di due domini personalizzati cohovineyard.com e cohowinery.com, è necessario configurare due record CNAME per ogni dominio aggiuntivo, per un totale di quattro record CNAME.</span><span class="sxs-lookup"><span data-stu-id="5f6ee-189">For example, if you have an initial domain of cohovineyardandwinery.onmicrosoft.com, and two custom domains cohovineyard.com and cohowinery.com, you would need to set up two CNAME records for each additional domain, for a total of four CNAME records.</span></span>

```console
Host name:            selector1._domainkey
Points to address or value:    selector1-cohovineyard-com._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600

Host name:            selector2._domainkey
Points to address or value:    selector2-cohovineyard-com._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600

Host name:            selector1._domainkey
Points to address or value:    selector1-cohowinery-com._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600

Host name:            selector2._domainkey
Points to address or value:    selector2-cohowinery-com._domainkey.cohovineyardandwinery.onmicrosoft.com
TTL:                3600
```

> [!NOTE]
> <span data-ttu-id="5f6ee-190">È importante creare il secondo record, ma solo uno dei selettori può essere disponibile al momento della creazione.</span><span class="sxs-lookup"><span data-stu-id="5f6ee-190">It's important to create the second record, but only one of the selectors may be available at the time of creation.</span></span> <span data-ttu-id="5f6ee-191">In sostanza, il secondo selettore potrebbe puntare a un indirizzo che non è ancora stato creato.</span><span class="sxs-lookup"><span data-stu-id="5f6ee-191">In essence, the second selector might point to an address that hasn't been created yet.</span></span> <span data-ttu-id="5f6ee-192">È comunque consigliabile creare il secondo record CNAME, perché la rotazione delle chiavi non venga interrotta.</span><span class="sxs-lookup"><span data-stu-id="5f6ee-192">We still recommended that you create the second CNAME record, because your key rotation will be seamless.</span></span>


### <a name="steps-to-enable-dkim-signing-for-your-custom-domain"></a><span data-ttu-id="5f6ee-193">Procedura per abilitare la firma DKIM per il dominio personalizzato</span><span class="sxs-lookup"><span data-stu-id="5f6ee-193">Steps to enable DKIM signing for your custom domain</span></span>
<span data-ttu-id="5f6ee-194"><a name="EnableDKIMinO365"> </a></span><span class="sxs-lookup"><span data-stu-id="5f6ee-194"><a name="EnableDKIMinO365"> </a></span></span>

<span data-ttu-id="5f6ee-195">Dopo aver pubblicato i record CNAME in DNS, è possibile abilitare la firma DKIM tramite Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5f6ee-195">Once you have published the CNAME records in DNS, you are ready to enable DKIM signing through Microsoft 365.</span></span> <span data-ttu-id="5f6ee-196">È possibile eseguire questa operazione tramite l'interfaccia di amministrazione di Microsoft 365 oppure con PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5f6ee-196">You can do this either through the Microsoft 365 admin center or by using PowerShell.</span></span>

#### <a name="to-enable-dkim-signing-for-your-custom-domain-through-the-admin-center"></a><span data-ttu-id="5f6ee-197">Per abilitare la firma DKIM del dominio personalizzato tramite l'interfaccia di amministrazione</span><span class="sxs-lookup"><span data-stu-id="5f6ee-197">To enable DKIM signing for your custom domain through the admin center</span></span>

1. <span data-ttu-id="5f6ee-198">[Accedere a Microsoft 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4) con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="5f6ee-198">[Sign in to Microsoft 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4) with your work or school account.</span></span>

2. <span data-ttu-id="5f6ee-199">Passare a [protection.office.com](https://protection.office.com) o [security.microsoft.com](https://security.microsoft.com) a seconda del portale in uso e seguire il percorso seguente.</span><span class="sxs-lookup"><span data-stu-id="5f6ee-199">Go to [protection.office.com](https://protection.office.com) or [security.microsoft.com](https://security.microsoft.com) depending on which portal you use, and follow the path below.</span></span>

|<span data-ttu-id="5f6ee-200">protection.office.com</span><span class="sxs-lookup"><span data-stu-id="5f6ee-200">protection.office.com</span></span>  |<span data-ttu-id="5f6ee-201">security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="5f6ee-201">security.microsoft.com</span></span>  |
|---------|---------|
| <span data-ttu-id="5f6ee-202">Gestione delle minacce > Criteri > Criteri aggiuntivi > DKIM</span><span class="sxs-lookup"><span data-stu-id="5f6ee-202">Threat Management > Policy > Additional Policies > DKIM</span></span>     | <span data-ttu-id="5f6ee-203">E-mail e collaborazione > Criteri e regole > Criteri di minaccia > Altri criteri > DKIM</span><span class="sxs-lookup"><span data-stu-id="5f6ee-203">Email & Collaboration > Policies & rules > Threat policies > Additional policies > DKIM</span></span>        | 

3. <span data-ttu-id="5f6ee-p117">Selezionare il dominio per il quale si desidera abilitare DKIM, quindi, in **Firma i messaggi per questo dominio con firme DKIM** scegliere **Abilita**. Ripetere questo passaggio per ogni dominio personalizzato.</span><span class="sxs-lookup"><span data-stu-id="5f6ee-p117">Select the domain for which you want to enable DKIM and then, for **Sign messages for this domain with DKIM signatures**, choose **Enable**. Repeat this step for each custom domain.</span></span>

#### <a name="to-enable-dkim-signing-for-your-custom-domain-by-using-powershell"></a><span data-ttu-id="5f6ee-206">Per abilitare la firma DKIM del dominio personalizzato usando PowerShell</span><span class="sxs-lookup"><span data-stu-id="5f6ee-206">To enable DKIM signing for your custom domain by using PowerShell</span></span>

> [!IMPORTANT]
>:::image type="content" source="../../media/DKIMNoKeysSavedForThisDomain.PNG" alt-text="L'errore &quot;Nessuna chiave DKIM salvata per il dominio&quot;.":::
> <span data-ttu-id="5f6ee-208">Se si configura DKIM per la prima volta e viene visualizzato l'errore "Nessuna chiave DKIM salvata per il dominio".</span><span class="sxs-lookup"><span data-stu-id="5f6ee-208">If you are configuring DKIM for the first time and see the error 'No DKIM keys saved for this domain.'</span></span> <span data-ttu-id="5f6ee-209">completare il comando del passaggio 2 seguente (ad esempio, *Set-DkimSigningConfig -Identity contoso.com -Enabled $true*) per visualizzare la chiave.</span><span class="sxs-lookup"><span data-stu-id="5f6ee-209">complete the command in step 2, below (for example, *Set-DkimSigningConfig -Identity contoso.com -Enabled $true*) to see the key.</span></span>

1. <span data-ttu-id="5f6ee-210">[Connettersi a PowerShell per Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="5f6ee-210">[Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="5f6ee-211">Eseguire il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="5f6ee-211">Run the following command:</span></span>

   ```powershell
   Set-DkimSigningConfig -Identity <domain> -Enabled $true
   ```

   <span data-ttu-id="5f6ee-212">Dove _domain_ è il nome del dominio personalizzato per cui si vuole abilitare la firma DKIM.</span><span class="sxs-lookup"><span data-stu-id="5f6ee-212">Where _domain_ is the name of the custom domain that you want to enable DKIM signing for.</span></span>

   <span data-ttu-id="5f6ee-213">Ad esempio, per domain contoso.com:</span><span class="sxs-lookup"><span data-stu-id="5f6ee-213">For example, for the domain contoso.com:</span></span>

   ```powershell
   Set-DkimSigningConfig -Identity contoso.com -Enabled $true
   ```

#### <a name="to-confirm-dkim-signing-is-configured-properly-for-microsoft-365"></a><span data-ttu-id="5f6ee-214">Per confermare che la firma DKIM sia configurata in modo corretto in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5f6ee-214">To Confirm DKIM signing is configured properly for Microsoft 365</span></span>

<span data-ttu-id="5f6ee-p119">Attendere qualche minuto prima di effettuare i passaggi seguenti e confermare di aver configurato DKIM in modo corretto. In questo modo, le informazioni DKIM sul dominio possono essere distribuite nella rete.</span><span class="sxs-lookup"><span data-stu-id="5f6ee-p119">Wait a few minutes before you follow these steps to confirm that you have properly configured DKIM. This allows time for the DKIM information about the domain to be spread throughout the network.</span></span>

- <span data-ttu-id="5f6ee-217">Inviare un messaggio da un account incluso nel dominio di Microsoft 365 con DKIM abilitato a un altro account di posta elettronica, ad esempio, outlook.com o Hotmail.com.</span><span class="sxs-lookup"><span data-stu-id="5f6ee-217">Send a message from an account within your Microsoft 365 DKIM-enabled domain to another email account such as outlook.com or Hotmail.com.</span></span>

- <span data-ttu-id="5f6ee-p120">Non utilizzare un account aol.com per effettuare test. AOL potrebbe ignorare il controllo DKIM se la verifica SPF ha esito positivo. In questo modo, il test verrebbe annullato.</span><span class="sxs-lookup"><span data-stu-id="5f6ee-p120">Do not use an aol.com account for testing purposes. AOL may skip the DKIM check if the SPF check passes. This will nullify your test.</span></span>

- <span data-ttu-id="5f6ee-p121">Aprire il messaggio e osservare l’intestazione. Le istruzioni per visualizzare l’intestazione del messaggio variano in base al client di messaggistica usato. Per istruzioni sulla visualizzazione delle intestazioni dei messaggi in Outlook, vedere [Visualizzare le intestazioni dei messaggi ricevuti tramite internet in Outlook](https://support.microsoft.com/office/cd039382-dc6e-4264-ac74-c048563d212c).</span><span class="sxs-lookup"><span data-stu-id="5f6ee-p121">Open the message and look at the header. Instructions for viewing the header for the message will vary depending on your messaging client. For instructions on viewing message headers in Outlook, see [View internet message headers in Outlook](https://support.microsoft.com/office/cd039382-dc6e-4264-ac74-c048563d212c).</span></span>

  <span data-ttu-id="5f6ee-p122">Il messaggio con firma DKIM conterrà il nome host e il dominio definiti durante la pubblicazione delle voci CNAME. Il messaggio avrà un aspetto analogo a quello riportato nell'esempio:</span><span class="sxs-lookup"><span data-stu-id="5f6ee-p122">The DKIM-signed message will contain the host name and domain you defined when you published the CNAME entries. The message will look something like this example:</span></span>

  ```console
    From: Example User <example@contoso.com>
    DKIM-Signature: v=1; a=rsa-sha256; q=dns/txt; c=relaxed/relaxed;
        s=selector1; d=contoso.com; t=1429912795;
        h=From:To:Message-ID:Subject:MIME-Version:Content-Type;
        bh=<body hash>;
        b=<signed field>;
  ```

- <span data-ttu-id="5f6ee-p123">Cercare l'intestazione Authentication-Results. Anche se ogni servizio di ricezione utilizza un formato differente per indicare la posta in arrivo, il risultato deve includere **DKIM=pass** o **DKIM=OK**.</span><span class="sxs-lookup"><span data-stu-id="5f6ee-p123">Look for the Authentication-Results header. While each receiving service uses a slightly different format to stamp the incoming mail, the result should include something like **DKIM=pass** or **DKIM=OK**.</span></span>

## <a name="to-configure-dkim-for-more-than-one-custom-domain"></a><span data-ttu-id="5f6ee-228">Per configurare DKIM per più domini personalizzati</span><span class="sxs-lookup"><span data-stu-id="5f6ee-228">To configure DKIM for more than one custom domain</span></span>
<span data-ttu-id="5f6ee-229"><a name="DKIMMultiDomain"> </a></span><span class="sxs-lookup"><span data-stu-id="5f6ee-229"><a name="DKIMMultiDomain"> </a></span></span>

<span data-ttu-id="5f6ee-230">Se in futuro si decide di aggiungere un altro dominio personalizzato e di abilitare DKIM, è necessario eseguire la procedura indicata in questo articolo per ogni dominio.</span><span class="sxs-lookup"><span data-stu-id="5f6ee-230">If at some point in the future you decide to add another custom domain and you want to enable DKIM for the new domain, you must complete the steps in this article for each domain.</span></span> <span data-ttu-id="5f6ee-231">In particolare, completare tutti i passaggi elencati in [Procedura necessaria per configurare manualmente DKIM](use-dkim-to-validate-outbound-email.md#SetUpDKIMO365).</span><span class="sxs-lookup"><span data-stu-id="5f6ee-231">Specifically, complete all steps in [What you need to do to manually set up DKIM](use-dkim-to-validate-outbound-email.md#SetUpDKIMO365).</span></span>

## <a name="disabling-the-dkim-signing-policy-for-a-custom-domain"></a><span data-ttu-id="5f6ee-232">Disabilitazione del criterio di firma DKIM per un dominio personalizzato</span><span class="sxs-lookup"><span data-stu-id="5f6ee-232">Disabling the DKIM signing policy for a custom domain</span></span>
<span data-ttu-id="5f6ee-233"><a name="DisableDKIMSigningPolicy"> </a></span><span class="sxs-lookup"><span data-stu-id="5f6ee-233"><a name="DisableDKIMSigningPolicy"> </a></span></span>

<span data-ttu-id="5f6ee-234">La disabilitazione del criterio di firma non disattiva completamente DKIM.</span><span class="sxs-lookup"><span data-stu-id="5f6ee-234">Disabling the signing policy does not completely disable DKIM.</span></span> <span data-ttu-id="5f6ee-235">Dopo un determinato periodo di tempo, Microsoft 365 applicherà automaticamente il criterio predefinito per il dominio.</span><span class="sxs-lookup"><span data-stu-id="5f6ee-235">After a period of time, Microsoft 365 will automatically apply the default policy for your domain.</span></span> <span data-ttu-id="5f6ee-236">Per ulteriori informazioni, vedere [Comportamento predefinito per DKIM e Microsoft 365](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior).</span><span class="sxs-lookup"><span data-stu-id="5f6ee-236">For more information, see [Default behavior for DKIM and Microsoft 365](use-dkim-to-validate-outbound-email.md#DefaultDKIMbehavior).</span></span>

### <a name="to-disable-the-dkim-signing-policy-by-using-windows-powershell"></a><span data-ttu-id="5f6ee-237">Per disabilitare il criterio di firma DKIM usando Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5f6ee-237">To disable the DKIM signing policy by using Windows PowerShell</span></span>

1. <span data-ttu-id="5f6ee-238">[Connettersi a PowerShell per Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="5f6ee-238">[Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="5f6ee-239">Eseguire uno dei comandi seguenti per ogni dominio per il quale si desidera disabilitare la firma DKIM.</span><span class="sxs-lookup"><span data-stu-id="5f6ee-239">Run one of the following commands for each domain for which you want to disable DKIM signing.</span></span>

   ```powershell
   $p = Get-DkimSigningConfig -Identity <domain>
   $p[0] | Set-DkimSigningConfig -Enabled $false
   ```

   <span data-ttu-id="5f6ee-240">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="5f6ee-240">For example:</span></span>

   ```powershell
   $p = Get-DkimSigningConfig -Identity contoso.com
   $p[0] | Set-DkimSigningConfig -Enabled $false
   ```

   <span data-ttu-id="5f6ee-241">Oppure</span><span class="sxs-lookup"><span data-stu-id="5f6ee-241">Or</span></span>

   ```powershell
   Set-DkimSigningConfig -Identity $p[<number>].Identity -Enabled $false
   ```

   <span data-ttu-id="5f6ee-242">Dove _number_ è l'indice del criterio.</span><span class="sxs-lookup"><span data-stu-id="5f6ee-242">Where _number_ is the index of the policy.</span></span> <span data-ttu-id="5f6ee-243">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="5f6ee-243">For example:</span></span>

   ```powershell
   Set-DkimSigningConfig -Identity $p[0].Identity -Enabled $false
   ```

## <a name="default-behavior-for-dkim-and-microsoft-365"></a><span data-ttu-id="5f6ee-244">Comportamento predefinito per DKIM e Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5f6ee-244">Default behavior for DKIM and Microsoft 365</span></span>
<span data-ttu-id="5f6ee-245"><a name="DefaultDKIMbehavior"> </a></span><span class="sxs-lookup"><span data-stu-id="5f6ee-245"><a name="DefaultDKIMbehavior"> </a></span></span>

<span data-ttu-id="5f6ee-246">Se non si abilita DKIM, Microsoft 365 crea automaticamente una chiave pubblica DKIM da 1024 bit per il dominio predefinito e la chiave privata associata, la quale viene archiviata internamente nel data center di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5f6ee-246">If you do not enable DKIM, Microsoft 365 automatically creates a 1024-bit DKIM public key for your default domain and the associated private key which we store internally in our datacenter.</span></span> <span data-ttu-id="5f6ee-247">Per impostazione predefinita, Microsoft 365 utilizza una configurazione di firma predefinita per i domini che non dispongono di un criterio.</span><span class="sxs-lookup"><span data-stu-id="5f6ee-247">By default, Microsoft 365 uses a default signing configuration for domains that do not have a policy in place.</span></span> <span data-ttu-id="5f6ee-248">Ciò significa che se l'utente non configura DKIM, Microsoft 365 utilizza il criterio predefinito e le chiavi create per abilitare DKIM nel dominio.</span><span class="sxs-lookup"><span data-stu-id="5f6ee-248">This means that if you do not set up DKIM yourself, Microsoft 365 will use its default policy and keys it creates to enable DKIM for your domain.</span></span>

<span data-ttu-id="5f6ee-249">Inoltre, se si disabilita la firma DKIM dopo l'abilitazione, Microsoft 365 applica automaticamente (dopo un determinato periodo di tempo) il criterio predefinito per il dominio.</span><span class="sxs-lookup"><span data-stu-id="5f6ee-249">Also, if you disable DKIM signing after enabling it, after a period of time, Microsoft 365 will automatically apply the default policy for your domain.</span></span>

<span data-ttu-id="5f6ee-250">Nell'esempio seguente, considerare che la chiave DKIM per fabrikam.com sia stata abilitata da Microsoft 365 e non dall'amministratore del dominio.</span><span class="sxs-lookup"><span data-stu-id="5f6ee-250">In the following example, suppose that DKIM for fabrikam.com was enabled by Microsoft 365, not by the administrator of the domain.</span></span> <span data-ttu-id="5f6ee-251">Questo errore indica che i record CNAME necessari non sono presenti nel sistema DNS.</span><span class="sxs-lookup"><span data-stu-id="5f6ee-251">This means that the required CNAMEs do not exist in DNS.</span></span> <span data-ttu-id="5f6ee-252">Le firme DKIM per i messaggi di posta elettronica provenienti dal dominio avranno un aspetto analogo al seguente:</span><span class="sxs-lookup"><span data-stu-id="5f6ee-252">DKIM signatures for email from this domain will look something like this:</span></span>

```console
From: Second Example <second.example@fabrikam.com>
DKIM-Signature: v=1; a=rsa-sha256; q=dns/txt; c=relaxed/relaxed;
    s=selector1-fabrikam-com; d=contoso.onmicrosoft.com; t=1429912795;
    h=From:To:Message-ID:Subject:MIME-Version:Content-Type;
    bh=<body hash>;
    b=<signed field>;
```

<span data-ttu-id="5f6ee-253">In questo caso, il nome host e il dominio includono i valori a cui dovrebbe puntare CNAME se la firma DKIM per fabrikam.com fosse stata abilitata dall'amministratore di dominio.</span><span class="sxs-lookup"><span data-stu-id="5f6ee-253">In this example, the host name and domain contain the values to which the CNAME would point if DKIM-signing for fabrikam.com had been enabled by the domain administrator.</span></span> <span data-ttu-id="5f6ee-254">Infine, ogni messaggio inviato da Microsoft 365 sarà firmato con la chiave DKIM.</span><span class="sxs-lookup"><span data-stu-id="5f6ee-254">Eventually, every single message sent from Microsoft 365 will be DKIM-signed.</span></span> <span data-ttu-id="5f6ee-255">Se la chiave DKIM è stata abilitata dall'utente, il dominio sarà identico a quello dell'indirizzo "Da:", in questo caso, fabrikam.com.</span><span class="sxs-lookup"><span data-stu-id="5f6ee-255">If you enable DKIM yourself, the domain will be the same as the domain in the From: address, in this case fabrikam.com.</span></span> <span data-ttu-id="5f6ee-256">In caso contrario, non verrà allineato e utilizzerà il dominio iniziale dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="5f6ee-256">If you don't, it will not align and instead will use your organization's initial domain.</span></span> <span data-ttu-id="5f6ee-257">Per informazioni su come determinare il dominio iniziale, vedere [Domande frequenti sui domini](../../admin/setup/domains-faq.yml#why-do-i-have-an--onmicrosoft-com--domain).</span><span class="sxs-lookup"><span data-stu-id="5f6ee-257">For information about determining your initial domain, see [Domains FAQ](../../admin/setup/domains-faq.yml#why-do-i-have-an--onmicrosoft-com--domain).</span></span>

## <a name="set-up-dkim-so-that-a-third-party-service-can-send-or-spoof-email-on-behalf-of-your-custom-domain"></a><span data-ttu-id="5f6ee-258">Configurare DKIM in modo che un servizio di terze parti possa inviare la posta elettronica o effettuarne lo spoofing per conto del dominio personalizzato dell'utente</span><span class="sxs-lookup"><span data-stu-id="5f6ee-258">Set up DKIM so that a third-party service can send, or spoof, email on behalf of your custom domain</span></span>
<span data-ttu-id="5f6ee-259"><a name="SetUp3rdPartyspoof"> </a></span><span class="sxs-lookup"><span data-stu-id="5f6ee-259"><a name="SetUp3rdPartyspoof"> </a></span></span>

<span data-ttu-id="5f6ee-260">Alcuni provider di servizi di posta di blocco o di software come servizio consentono di configurare le chiavi DKIM per la posta elettronica originata dal servizio.</span><span class="sxs-lookup"><span data-stu-id="5f6ee-260">Some bulk email service providers, or software-as-a-service providers, let you set up DKIM keys for email that originates from their service.</span></span> <span data-ttu-id="5f6ee-261">Per configurare i record DNS necessari, l'utente e la terza parte devono essere coordinati.</span><span class="sxs-lookup"><span data-stu-id="5f6ee-261">This requires coordination between yourself and the third-party in order to set up the necessary DNS records.</span></span> <span data-ttu-id="5f6ee-262">Alcuni server di terze parti possono avere propri record CNAME con selettori diversi.</span><span class="sxs-lookup"><span data-stu-id="5f6ee-262">Some third-party servers can have their own CNAME records with different selectors.</span></span> <span data-ttu-id="5f6ee-263">Nessuna organizzazione esegue questa operazione nello stesso modo.</span><span class="sxs-lookup"><span data-stu-id="5f6ee-263">No two organizations do it exactly the same way.</span></span> <span data-ttu-id="5f6ee-264">Al contrario, il processo dipende interamente dall'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="5f6ee-264">Instead, the process depends entirely on the organization.</span></span>

<span data-ttu-id="5f6ee-265">Messaggio di esempio che mostra come potrebbe essere una chiave DKIM correttamente configurata per contoso.com e bulkemailprovider.com:</span><span class="sxs-lookup"><span data-stu-id="5f6ee-265">An example message showing a properly configured DKIM for contoso.com and bulkemailprovider.com might look like this:</span></span>

```console
Return-Path: <communication@bulkemailprovider.com>
 From: <sender@contoso.com>
 DKIM-Signature: s=s1024; d=contoso.com
 Subject: Here is a message from Bulk Email Provider's infrastructure, but with a DKIM signature authorized by contoso.com
```

<span data-ttu-id="5f6ee-266">In questo esempio, per raggiungere il risultato:</span><span class="sxs-lookup"><span data-stu-id="5f6ee-266">In this example, in order to achieve this result:</span></span>

1. <span data-ttu-id="5f6ee-267">Il provider di posta elettronica di massa ha fornito a Contoso una chiave DKIM pubblica.</span><span class="sxs-lookup"><span data-stu-id="5f6ee-267">Bulk Email Provider gave Contoso a public DKIM key.</span></span>

2. <span data-ttu-id="5f6ee-268">Contoso ha pubblicato la chiave DKIM nel suo record DNS.</span><span class="sxs-lookup"><span data-stu-id="5f6ee-268">Contoso published the DKIM key to its DNS record.</span></span>

3. <span data-ttu-id="5f6ee-p131">Durante l'invio della posta elettronica, il provider della posta elettronica inviata in blocco firma la chiave con quella privata corrispondente. In questo modo, il provider della posta elettronica inviata in blocco ha allegato la firma DKIM all'intestazione del messaggio.</span><span class="sxs-lookup"><span data-stu-id="5f6ee-p131">When sending email, Bulk Email Provider signs the key with the corresponding private key. By doing so, Bulk Email Provider attached the DKIM signature to the message header.</span></span>

4. <span data-ttu-id="5f6ee-271">I sistemi di ricezione della posta elettronica eseguono un confronto tra il valore DKIM-Signature d=\<domain\> della chiave DKIM firmata e il dominio nell'indirizzo Da: (5322.From) del messaggio.</span><span class="sxs-lookup"><span data-stu-id="5f6ee-271">Receiving email systems perform a DKIM check by authenticating the DKIM-Signature d=\<domain\> value against the domain in the From: (5322.From) address of the message.</span></span> <span data-ttu-id="5f6ee-272">In questo esempio, i valori corrispondono a:</span><span class="sxs-lookup"><span data-stu-id="5f6ee-272">In this example, the values match:</span></span>

   > <span data-ttu-id="5f6ee-273">sender@**contoso.com**</span><span class="sxs-lookup"><span data-stu-id="5f6ee-273">sender@**contoso.com**</span></span>

   > <span data-ttu-id="5f6ee-274">d=**contoso.com**</span><span class="sxs-lookup"><span data-stu-id="5f6ee-274">d=**contoso.com**</span></span>

## <a name="identify-domains-that-do-not-send-email"></a><span data-ttu-id="5f6ee-275">Identificare i domini che non inviano messaggi di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="5f6ee-275">Identify domains that do not send email</span></span>

<span data-ttu-id="5f6ee-276">Le organizzazioni devono dichiarare esplicitamente se un dominio non invia messaggi di posta elettronica specificando `v=DKIM1; p=` nel record DKIM per tali domini.</span><span class="sxs-lookup"><span data-stu-id="5f6ee-276">Organizations should explicitly state if a domain does not send email by specifying `v=DKIM1; p=` in the DKIM record for those domains.</span></span> <span data-ttu-id="5f6ee-277">In questo caso, la ricezione dei server di posta elettronica non contiene chiavi pubbliche valide per il dominio e gli eventuali messaggi di posta elettronica che rivendicano il dominio devono essere rifiutati.</span><span class="sxs-lookup"><span data-stu-id="5f6ee-277">This advises receiving email servers that there are no valid public keys for the domain, and any email claiming to be from that domain should be rejected.</span></span> <span data-ttu-id="5f6ee-278">Questa operazione deve essere eseguita per ogni dominio e sottodominio usando un carattere jolly DKIM.</span><span class="sxs-lookup"><span data-stu-id="5f6ee-278">You should do this for each domain and subdomain using a wildcard DKIM.</span></span>

<span data-ttu-id="5f6ee-279">Ad esempio, il record DKIM avrà un aspetto simile al seguente:</span><span class="sxs-lookup"><span data-stu-id="5f6ee-279">For example, the DKIM record would look like this:</span></span>

```console
*._domainkey.SubDomainThatShouldntSendMail.contoso.com. TXT "v=DKIM1; p="
```

## <a name="next-steps-after-you-set-up-dkim-for-microsoft-365"></a><span data-ttu-id="5f6ee-280">Passaggi successivi: dopo aver configurato DKIM per Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5f6ee-280">Next steps: After you set up DKIM for Microsoft 365</span></span>
<span data-ttu-id="5f6ee-281"><a name="DKIMNextSteps"> </a></span><span class="sxs-lookup"><span data-stu-id="5f6ee-281"><a name="DKIMNextSteps"> </a></span></span>

<span data-ttu-id="5f6ee-282">Sebbene la chiave DKIM sia stata realizzata per impedire lo spoofing, è più efficace se utilizzata con SPF e DMARC.</span><span class="sxs-lookup"><span data-stu-id="5f6ee-282">Although DKIM is designed to help prevent spoofing, DKIM works better with SPF and DMARC.</span></span> <span data-ttu-id="5f6ee-283">Dopo aver configurato DKIM, impostare SPF, se non è stato già fatto.</span><span class="sxs-lookup"><span data-stu-id="5f6ee-283">Once you have set up DKIM, if you have not already set up SPF you should do so.</span></span> <span data-ttu-id="5f6ee-284">Per una rapida introduzione a SPF e le istruzioni di configurazione, vedere [Configurare SPF in Microsoft 365 per prevenire lo spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span><span class="sxs-lookup"><span data-stu-id="5f6ee-284">For a quick introduction to SPF and to get it configured quickly, see [Set up SPF in Microsoft 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span></span> <span data-ttu-id="5f6ee-285">Per informazioni più dettagliate su come Microsoft 365 utilizza SPF oppure per risolvere i problemi o per eseguire distribuzioni non standard (ad esempio, le distribuzioni ibride), consultare innanzitutto [Come Microsoft 365 utilizza Sender Policy Framework (SPF) per prevenire lo spoofing](how-office-365-uses-spf-to-prevent-spoofing.md).</span><span class="sxs-lookup"><span data-stu-id="5f6ee-285">For a more in-depth understanding of how Microsoft 365 uses SPF, or for troubleshooting or non-standard deployments such as hybrid deployments, start with [How Microsoft 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md).</span></span> <span data-ttu-id="5f6ee-286">Successivamente, vedere [Usare DMARC per convalidare la posta elettronica](use-dmarc-to-validate-email.md).</span><span class="sxs-lookup"><span data-stu-id="5f6ee-286">Next, see [Use DMARC to validate email](use-dmarc-to-validate-email.md).</span></span> <span data-ttu-id="5f6ee-287">[Intestazioni dei messaggi della protezione da posta indesiderata](anti-spam-message-headers.md) include la sintassi e i campi di intestazione usati da Microsoft 365 per i controlli DKIM.</span><span class="sxs-lookup"><span data-stu-id="5f6ee-287">[Anti-spam message headers](anti-spam-message-headers.md) includes the syntax and header fields used by Microsoft 365 for DKIM checks.</span></span>

## <a name="more-information"></a><span data-ttu-id="5f6ee-288">Altre informazioni</span><span class="sxs-lookup"><span data-stu-id="5f6ee-288">More information</span></span>

<span data-ttu-id="5f6ee-289">Rotazione delle chiavi tramite PowerShell [Rotate-DkimSigningConfig](/powershell/module/exchange/rotate-dkimsigningconfig)</span><span class="sxs-lookup"><span data-stu-id="5f6ee-289">Key rotation via PowerShell [Rotate-DkimSigningConfig](/powershell/module/exchange/rotate-dkimsigningconfig)</span></span>