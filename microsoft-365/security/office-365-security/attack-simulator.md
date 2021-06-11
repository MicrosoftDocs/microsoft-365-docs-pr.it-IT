---
title: Simulatore di attacco in Microsoft Defender per Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: da5845db-c578-4a41-b2cb-5a09689a551b
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Gli amministratori possono imparare a usare Il simulatore di attacco per eseguire attacchi simulati di phishing e password nelle organizzazioni Microsoft 365 E5 o Microsoft Defender per Office 365 Piano 2.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 03e6c0077f13c85bfd20ac0583b64ce29e2535a1
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878677"
---
# <a name="attack-simulator-in-microsoft-defender-for-office-365"></a><span data-ttu-id="95aba-103">Simulatore di attacco in Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="95aba-103">Attack Simulator in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="95aba-104">**Si applica a** [Microsoft Defender per Office 365 piano 2](defender-for-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="95aba-104">**Applies to** [Microsoft Defender for Office 365 plan 2](defender-for-office-365.md)</span></span>

<span data-ttu-id="95aba-105">Se l'organizzazione dispone di Microsoft Defender per Office 365 Piano 2, che include funzionalità di analisi delle minacce e [risposta,](office-365-ti.md)è possibile utilizzare Simulatore di attacco nel Centro sicurezza & conformità per eseguire scenari di attacco realistici nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="95aba-105">If your organization has Microsoft Defender for Office 365 Plan 2, which includes [Threat Investigation and Response capabilities](office-365-ti.md), you can use Attack Simulator in the Security & Compliance Center to run realistic attack scenarios in your organization.</span></span> <span data-ttu-id="95aba-106">Questi attacchi simulati consentono di identificare e individuare gli utenti vulnerabili prima che un attacco reale influisca sulla linea di fondo.</span><span class="sxs-lookup"><span data-stu-id="95aba-106">These simulated attacks can help you identify and find vulnerable users before a real attack impacts your bottom line.</span></span> <span data-ttu-id="95aba-107">Leggi questo articolo per altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="95aba-107">Read this article to learn more.</span></span>

> [!NOTE]
>
> <span data-ttu-id="95aba-108">Il simulatore di attacco come descritto in questo articolo è ora di sola lettura ed è stato sostituito dal **training** di simulazione degli attacchi nel nodo di collaborazione **Email &** nel portale di Microsoft 365 Defender all'indirizzo <https://security.microsoft.com> .</span><span class="sxs-lookup"><span data-stu-id="95aba-108">Attack Simulator as described in this article is now read-only and has been replaced by **Attack simulation training** in the **Email & collaboration** node in the Microsoft 365 Defender portal at <https://security.microsoft.com>.</span></span> <span data-ttu-id="95aba-109">Per ulteriori informazioni, vedere [Introduzione all'uso del training di simulazione degli attacchi.](attack-simulation-training-get-started.md)</span><span class="sxs-lookup"><span data-stu-id="95aba-109">For more information, see [Get started using Attack simulation training](attack-simulation-training-get-started.md).</span></span>
>
> <span data-ttu-id="95aba-110">La possibilità di avviare nuove simulazioni da questa versione di Attack Simulator è stata disabilitata.</span><span class="sxs-lookup"><span data-stu-id="95aba-110">The ability to launch new simulations from this version of Attack Simulator has been disabled.</span></span> <span data-ttu-id="95aba-111">È comunque possibile accedere ai report fino al 24 aprile 2021.</span><span class="sxs-lookup"><span data-stu-id="95aba-111">However, you can still access reports until April 24, 2021.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="95aba-112">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="95aba-112">What do you need to know before you begin?</span></span>

- <span data-ttu-id="95aba-113">Per aprire il Centro sicurezza e conformità, passare a <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="95aba-113">To open the Security & Compliance Center, go to <https://protection.office.com/>.</span></span> <span data-ttu-id="95aba-114">Il simulatore di attacco è disponibile **in Threat management** Attack \> **simulator**.</span><span class="sxs-lookup"><span data-stu-id="95aba-114">Attack simulator is available at **Threat management** \> **Attack simulator**.</span></span> <span data-ttu-id="95aba-115">Per passare direttamente al simulatore di attacco, apri <https://protection.office.com/attacksimulator> .</span><span class="sxs-lookup"><span data-stu-id="95aba-115">To go directly to attack simulator, open <https://protection.office.com/attacksimulator>.</span></span>

- <span data-ttu-id="95aba-116">Per altre informazioni sulla disponibilità di Attack Simulator tra diverse sottoscrizioni Microsoft 365, vedi [Microsoft Defender per](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)la descrizione Office 365 servizio .</span><span class="sxs-lookup"><span data-stu-id="95aba-116">For more information about the availability of Attack Simulator across different Microsoft 365 subscriptions, see [Microsoft Defender for Office 365 service description](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

- <span data-ttu-id="95aba-117">È necessario essere membri dei gruppi di ruoli **Gestione organizzazione** o **Amministratore** sicurezza.</span><span class="sxs-lookup"><span data-stu-id="95aba-117">You need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="95aba-118">Per altre informazioni sui gruppi di ruoli nel Centro sicurezza e conformità, vedere [Autorizzazioni nel Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="95aba-118">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="95aba-119">L'account deve essere configurato per l'autenticazione a più fattori (MFA) per creare e gestire campagne in Attack Simulator.</span><span class="sxs-lookup"><span data-stu-id="95aba-119">Your account needs to be configured for multi-factor authentication (MFA) to create and manage campaigns in Attack Simulator.</span></span> <span data-ttu-id="95aba-120">Per istruzioni, vedere [Configurare l'autenticazione a più fattori.](../../admin/security-and-compliance/set-up-multi-factor-authentication.md)</span><span class="sxs-lookup"><span data-stu-id="95aba-120">For instructions, see [Set up multi-factor authentication](../../admin/security-and-compliance/set-up-multi-factor-authentication.md).</span></span>

- <span data-ttu-id="95aba-121">Il simulatore di attacco funziona solo sulle cassette postali basate sul cloud.</span><span class="sxs-lookup"><span data-stu-id="95aba-121">Attack Simulator only works on cloud-based mailboxes.</span></span>

- <span data-ttu-id="95aba-122">Le campagne di phishing raccoglieranno ed eelaborare gli eventi per 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="95aba-122">Phishing campaigns will collect and process events for 30 days.</span></span> <span data-ttu-id="95aba-123">I dati cronologici della campagna saranno disponibili fino a 90 giorni dopo l'avvio della campagna.</span><span class="sxs-lookup"><span data-stu-id="95aba-123">Historical campaign data will be available for up to 90 days after you launch the campaign.</span></span>

- <span data-ttu-id="95aba-124">I dati correlati alla simulazione e alla formazione degli attacchi vengono archiviati con altri dati dei clienti Microsoft 365 servizi.</span><span class="sxs-lookup"><span data-stu-id="95aba-124">Attack simulation and training related data is stored with other customer data for Microsoft 365 services.</span></span> <span data-ttu-id="95aba-125">Per ulteriori informazioni, [vedere Microsoft 365 di dati](../../enterprise/o365-data-locations.md).</span><span class="sxs-lookup"><span data-stu-id="95aba-125">For more information see [Microsoft 365 data locations](../../enterprise/o365-data-locations.md).</span></span>

- <span data-ttu-id="95aba-126">Non sono disponibili cmdlet di PowerShell corrispondenti per Il simulatore di attacco.</span><span class="sxs-lookup"><span data-stu-id="95aba-126">There are no corresponding PowerShell cmdlets for Attack Simulator.</span></span>

## <a name="spear-phishing-campaigns"></a><span data-ttu-id="95aba-127">Campagne di spear phishing</span><span class="sxs-lookup"><span data-stu-id="95aba-127">Spear phishing campaigns</span></span>

<span data-ttu-id="95aba-128">*Il phishing* è un termine generico per gli attacchi di posta elettronica che tentano di rubare informazioni riservate nei messaggi che sembrano essere provenienti da mittenti legittimi o attendibili.</span><span class="sxs-lookup"><span data-stu-id="95aba-128">*Phishing* is a generic term for email attacks that try to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="95aba-129">*Il spear phishing* è un attacco di phishing mirato che usa contenuti mirati e personalizzati appositamente personalizzati per i destinatari di destinazione (in genere, dopo la ricognizione dei destinatari da parte dell'autore dell'attacco).</span><span class="sxs-lookup"><span data-stu-id="95aba-129">*Spear phishing* is a targeted phishing attack that uses focused and customized content that's specifically tailored to the targeted recipients (typically, after reconnaissance on the recipients by the attacker).</span></span>

<span data-ttu-id="95aba-130">In Attack Simulator sono disponibili due diversi tipi di campagne di spear phishing:</span><span class="sxs-lookup"><span data-stu-id="95aba-130">In Attack Simulator, two different types of spear phishing campaigns are available:</span></span>

- <span data-ttu-id="95aba-131">**Spear phishing (raccolta delle credenziali):** l'attacco tenta di convincere i destinatari a fare clic su un URL nel messaggio.</span><span class="sxs-lookup"><span data-stu-id="95aba-131">**Spear phishing (credentials harvest)**: The attack tries to convince the recipients to click a URL in the message.</span></span> <span data-ttu-id="95aba-132">Se fa clic sul collegamento, viene richiesto di immettere le proprie credenziali.</span><span class="sxs-lookup"><span data-stu-id="95aba-132">If they click the link, they're asked to enter their credentials.</span></span> <span data-ttu-id="95aba-133">In caso contrario, vengono portati in una delle posizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="95aba-133">If they do, they're taken to one of the following locations:</span></span>

  - <span data-ttu-id="95aba-134">Una pagina predefinita che spiega che si tratta di un semplice test e fornisce suggerimenti per riconoscere i messaggi di phishing.</span><span class="sxs-lookup"><span data-stu-id="95aba-134">A default page that explains that this was a just a test, and gives tips for recognizing phishing messages.</span></span>

    ![Cosa vedono gli utenti se fanno clic sul collegamento di phishing e immettono le proprie credenziali](../../media/attack-simulator-phishing-result.png)

  - <span data-ttu-id="95aba-136">Pagina personalizzata (URL) specificata.</span><span class="sxs-lookup"><span data-stu-id="95aba-136">A custom page (URL) that you specify.</span></span>

- <span data-ttu-id="95aba-137">**Spear phishing (allegato):** l'attacco tenta di convincere i destinatari ad aprire un .docx o .pdf allegato nel messaggio.</span><span class="sxs-lookup"><span data-stu-id="95aba-137">**Spear phishing (attachment)**: The attack tries to convince the recipients to open a .docx or .pdf attachment in the message.</span></span> <span data-ttu-id="95aba-138">L'allegato contiene lo stesso contenuto del collegamento di phishing predefinito, ma la prima frase inizia con " , questo messaggio viene visualizzato come un messaggio di posta elettronica recente \<Display Name\> aperto...".</span><span class="sxs-lookup"><span data-stu-id="95aba-138">The attachment contains the same content from the default phishing link, but the first sentence starts with "\<Display Name\>, you are seeing this message as a recent email message you opened...".</span></span>

> [!NOTE]
> <span data-ttu-id="95aba-139">Attualmente, le campagne di spear phishing in Attack Simulator non scadono.</span><span class="sxs-lookup"><span data-stu-id="95aba-139">Currently, spear phishing campaigns in Attack Simulator don't expire.</span></span>

### <a name="create-a-spear-phishing-campaign"></a><span data-ttu-id="95aba-140">Creare una campagna di spear phishing</span><span class="sxs-lookup"><span data-stu-id="95aba-140">Create a spear phishing campaign</span></span>

<span data-ttu-id="95aba-141">Una parte importante di qualsiasi campagna di spear phishing è l'aspetto del messaggio di posta elettronica inviato ai destinatari di destinazione.</span><span class="sxs-lookup"><span data-stu-id="95aba-141">An important part of any spear phishing campaign is the look and feel of the email message that's sent to the targeted recipients.</span></span> <span data-ttu-id="95aba-142">Per creare e configurare il messaggio di posta elettronica, sono disponibili le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="95aba-142">To create and configure the email message, you have these options:</span></span>

- <span data-ttu-id="95aba-143">**Usa un modello di posta elettronica predefinito:** sono disponibili due modelli predefiniti: **Giveaway per** premi e **aggiornamento delle buste paga.**</span><span class="sxs-lookup"><span data-stu-id="95aba-143">**Use a built-in email template**: Two built-in templates are available: **Prize Giveaway** and **Payroll Update**.</span></span> <span data-ttu-id="95aba-144">È possibile personalizzare ulteriormente alcune, tutte o nessuna delle proprietà di posta elettronica del modello quando si crea e si avvia la campagna.</span><span class="sxs-lookup"><span data-stu-id="95aba-144">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="95aba-145">**Creare un modello di posta** elettronica riutilizzabile: dopo aver creato e salvato il modello di posta elettronica, è possibile utilizzarlo di nuovo nelle future campagne di spear phishing.</span><span class="sxs-lookup"><span data-stu-id="95aba-145">**Create a reusable email template**: After you create and save the email template, you can use it again in future spear phishing campaigns.</span></span> <span data-ttu-id="95aba-146">È possibile personalizzare ulteriormente alcune, tutte o nessuna delle proprietà di posta elettronica del modello quando si crea e si avvia la campagna.</span><span class="sxs-lookup"><span data-stu-id="95aba-146">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="95aba-147">**Creare il messaggio di posta elettronica nella** procedura guidata: è possibile creare il messaggio di posta elettronica direttamente nella procedura guidata durante la creazione e l'avvio della campagna di spear phishing.</span><span class="sxs-lookup"><span data-stu-id="95aba-147">**Create the email message in the wizard**: You can create the email message directly in the wizard as you create and launch the spear phishing campaign.</span></span>

#### <a name="step-1-optional-create-a-custom-email-template"></a><span data-ttu-id="95aba-148">Passaggio 1 (facoltativo): creare un modello di posta elettronica personalizzato</span><span class="sxs-lookup"><span data-stu-id="95aba-148">Step 1 (Optional): Create a custom email template</span></span>

<span data-ttu-id="95aba-149">Se si desidera utilizzare uno dei modelli predefiniti o creare il messaggio di posta elettronica direttamente nella procedura guidata, è possibile ignorare questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="95aba-149">If you're going to use one of the built-in templates or create the email message directly in the wizard, you can skip this step.</span></span>

1. <span data-ttu-id="95aba-150">Nel Centro sicurezza & conformità passare a **Gestione delle** minacce \> **Simulatore di attacco.**</span><span class="sxs-lookup"><span data-stu-id="95aba-150">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="95aba-151">Nella sezione **Spear** **Phishing (Credentials Harvest)** o **Spear Phishing (allegato)** della pagina Simula attacchi fare clic su **Dettagli attacco.**</span><span class="sxs-lookup"><span data-stu-id="95aba-151">On the **Simulate attacks** page, in either the **Spear Phishing (Credentials Harvest)** or **Spear Phishing (Attachment)** sections, click **Attack Details**.</span></span>

   <span data-ttu-id="95aba-152">Non importa dove si crea il modello.</span><span class="sxs-lookup"><span data-stu-id="95aba-152">It doesn't matter where you create the template.</span></span> <span data-ttu-id="95aba-153">Le opzioni disponibili nel modello sono le stesse per entrambi i tipi di attacchi di phishing.</span><span class="sxs-lookup"><span data-stu-id="95aba-153">The available options in the template are the same for both types of phishing attacks.</span></span>

3. <span data-ttu-id="95aba-154">Nella pagina **Dettagli attacco** visualizzata, nell'area Crea  modelli della sezione Modelli di **phishing** fare clic su **Nuovo modello.**</span><span class="sxs-lookup"><span data-stu-id="95aba-154">In the **Attack details** page that opens, in the **Phishing Templates** section, in the **Create Templates** area, click **New Template**.</span></span>

4. <span data-ttu-id="95aba-155">La **procedura guidata Configura modello** di phishing viene avviata in un nuovo riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="95aba-155">The **Configure Phishing Template** wizard starts in a new flyout.</span></span> <span data-ttu-id="95aba-156">Nel passaggio **Start** immettere un nome visualizzato univoco per il modello e quindi fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="95aba-156">In the **Start** step, enter a unique display name for the template, and then click **Next**.</span></span>

5. <span data-ttu-id="95aba-157">Nel passaggio **Configura dettagli posta elettronica** configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="95aba-157">In the **Configure email details** step, configure the following settings:</span></span>

   - <span data-ttu-id="95aba-158">**From (Name):** nome visualizzato utilizzato per il mittente del messaggio.</span><span class="sxs-lookup"><span data-stu-id="95aba-158">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="95aba-159">**From (Email)**: Indirizzo di posta elettronica del mittente.</span><span class="sxs-lookup"><span data-stu-id="95aba-159">**From (Email)**: The sender's email address.</span></span>

   - <span data-ttu-id="95aba-160">**URL server di accesso phishing**: fare clic sull'elenco a discesa e selezionare uno degli URL disponibili nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="95aba-160">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="95aba-161">Questo è l'URL su cui gli utenti saranno tentati di fare clic.</span><span class="sxs-lookup"><span data-stu-id="95aba-161">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="95aba-162">Le opzioni disponibili sono:</span><span class="sxs-lookup"><span data-stu-id="95aba-162">The choices are:</span></span>

     - <http://portal.docdeliveryapp.com>
     - <http://portal.docdeliveryapp.net>
     - <http://portal.docstoreinternal.com>
     - <http://portal.docstoreinternal.net>
     - <http://portal.hardwarecheck.net>
     - <http://portal.hrsupportint.com>
     - <http://portal.payrolltooling.com>
     - <http://portal.payrolltooling.net>
     - <http://portal.prizegiveaway.net>
     - <http://portal.prizesforall.com>
     - <http://portal.salarytoolint.com>
     - <http://portal.salarytoolint.net>

     > [!NOTE]
     >
     > <span data-ttu-id="95aba-163">Un servizio di reputazione URL potrebbe identificare uno o più di questi URL come non sicuri.</span><span class="sxs-lookup"><span data-stu-id="95aba-163">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="95aba-164">Verificare la disponibilità dell'URL nei Web browser supportati prima di utilizzare l'URL in una campagna di phishing.</span><span class="sxs-lookup"><span data-stu-id="95aba-164">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span>

   - <span data-ttu-id="95aba-165">**URL pagina di destinazione personalizzato:** immettere una pagina di destinazione facoltativa in cui vengono presi gli utenti se fanno clic sul collegamento di phishing e immettono le proprie credenziali.</span><span class="sxs-lookup"><span data-stu-id="95aba-165">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="95aba-166">Questo collegamento sostituisce la pagina di destinazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="95aba-166">This link replaces the default landing page.</span></span> <span data-ttu-id="95aba-167">Ad esempio, se hai un training di sensibilizzazione interno, puoi specificare questo URL qui.</span><span class="sxs-lookup"><span data-stu-id="95aba-167">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="95aba-168">**Categoria**: attualmente questa impostazione non viene utilizzata (tutto ciò che viene immesso viene ignorato).</span><span class="sxs-lookup"><span data-stu-id="95aba-168">**Category**: Currently, this setting isn't used (anything you enter is ignored).</span></span>

   - <span data-ttu-id="95aba-169">**Subject**: Campo **Subject** del messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="95aba-169">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="95aba-170">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="95aba-170">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="95aba-171">Nel passaggio **Componi messaggio di** posta elettronica creare il corpo del messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="95aba-171">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="95aba-172">È possibile utilizzare la **scheda Posta** elettronica (un editor HTML avanzato) o la **scheda Origine** (codice HTML non elaborato).</span><span class="sxs-lookup"><span data-stu-id="95aba-172">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="95aba-173">La formattazione HTML può essere semplice o complessa come necessario.</span><span class="sxs-lookup"><span data-stu-id="95aba-173">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="95aba-174">È possibile inserire immagini e testo per migliorare la credibilità del messaggio nel client di posta elettronica del destinatario.</span><span class="sxs-lookup"><span data-stu-id="95aba-174">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="95aba-175">`${username}` inserisce il nome del destinatario.</span><span class="sxs-lookup"><span data-stu-id="95aba-175">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="95aba-176">`${loginserverurl}` inserisce il **valore URL del server** di accesso phishing del passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="95aba-176">`${loginserverurl}` inserts the **Phishing Login Server URL** value from the previous step.</span></span>

   <span data-ttu-id="95aba-177">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="95aba-177">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="95aba-178">Nel passaggio **Conferma** fare clic su **Fine.**</span><span class="sxs-lookup"><span data-stu-id="95aba-178">In the **Confirm** step, click **Finish**.</span></span>

#### <a name="step-2-create-and-launch-the-spear-phishing-campaign"></a><span data-ttu-id="95aba-179">Passaggio 2: creare e avviare la campagna di spear phishing</span><span class="sxs-lookup"><span data-stu-id="95aba-179">Step 2: Create and launch the spear phishing campaign</span></span>

1. <span data-ttu-id="95aba-180">Nel Centro sicurezza & conformità passare a **Gestione delle** minacce \> **Simulatore di attacco.**</span><span class="sxs-lookup"><span data-stu-id="95aba-180">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="95aba-181">Nella pagina **Simula attacchi** effettuare una delle selezioni seguenti in base al tipo di campagna che si desidera creare:</span><span class="sxs-lookup"><span data-stu-id="95aba-181">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="95aba-182">Nella sezione **Spear Phishing (Credentials Harvest)** fai clic su **Launch Attack** o fai clic su **Attack Details** Launch \> **Attack.**</span><span class="sxs-lookup"><span data-stu-id="95aba-182">In the **Spear Phishing (Credentials Harvest)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="95aba-183">Nella sezione **Spear Phishing (allegato)** fai clic su **Avvia attacco** o fai clic su **Dettagli attacco** Launch \> **Attack**.</span><span class="sxs-lookup"><span data-stu-id="95aba-183">In the **Spear Phishing (Attachment)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="95aba-184">La **procedura guidata Configura attacco di** phishing viene avviata in un nuovo riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="95aba-184">The **Configure Phishing Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="95aba-185">Nel passaggio **Start** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="95aba-185">In the **Start** step, do one of the following steps:</span></span>

   - <span data-ttu-id="95aba-186">Nella casella **Nome** immettere un nome visualizzato univoco per la campagna.</span><span class="sxs-lookup"><span data-stu-id="95aba-186">In the **Name** box, enter a unique display name for the campaign.</span></span> <span data-ttu-id="95aba-187">Non fare clic su **Usa modello** perché il messaggio di posta elettronica verrà creato più avanti nella procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="95aba-187">Don't click **Use Template**, because you'll create the email message later in the wizard.</span></span>

   - <span data-ttu-id="95aba-188">Fare **clic su Usa** modello e selezionare un modello di posta elettronica predefinito o personalizzato.</span><span class="sxs-lookup"><span data-stu-id="95aba-188">Click **Use Template** and select a built-in or custom email template.</span></span> <span data-ttu-id="95aba-189">Dopo aver selezionato il modello, la **casella Nome** viene compilata automaticamente in base al modello, ma è possibile modificare il nome.</span><span class="sxs-lookup"><span data-stu-id="95aba-189">After you select the template, the **Name** box is automatically filled based on the template, but you can change the name.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="95aba-190">![Pagina iniziale phishing](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)</span><span class="sxs-lookup"><span data-stu-id="95aba-190">![Phishing Start Page](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)</span></span>

   <span data-ttu-id="95aba-191">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="95aba-191">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="95aba-192">Nel passaggio **Destinatari di** destinazione eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="95aba-192">In the **Target recipients** step, do one of the following steps:</span></span>

   - <span data-ttu-id="95aba-193">Fare **clic su Rubrica** per selezionare i destinatari (utenti o gruppi) per la campagna.</span><span class="sxs-lookup"><span data-stu-id="95aba-193">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="95aba-194">Ogni destinatario di destinazione deve disporre di Exchange Online cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="95aba-194">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="95aba-195">Se si fa **clic su Filtro** e **Applica** senza immettere criteri di ricerca, tutti i destinatari vengono restituiti e aggiunti alla campagna.</span><span class="sxs-lookup"><span data-stu-id="95aba-195">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="95aba-196">Fare **clic su** **Importa, quindi su** Importazione file per importare un valore delimitato da virgole (CSV) o un file di indirizzi di posta elettronica separati da righe.</span><span class="sxs-lookup"><span data-stu-id="95aba-196">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="95aba-197">Ogni riga deve contenere l'indirizzo di posta elettronica del destinatario.</span><span class="sxs-lookup"><span data-stu-id="95aba-197">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="95aba-198">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="95aba-198">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="95aba-199">Nel passaggio **Configura dettagli posta elettronica** configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="95aba-199">In the **Configure email details** step, configure the following settings:</span></span>

   <span data-ttu-id="95aba-200">Se è stato selezionato un modello nel **passaggio Start,** la maggior parte di questi valori è già configurata, ma è possibile modificarli.</span><span class="sxs-lookup"><span data-stu-id="95aba-200">If you selected a template in the **Start** step, most of these values are already configured, but you can change them.</span></span>

   - <span data-ttu-id="95aba-201">**From (Name):** nome visualizzato utilizzato per il mittente del messaggio.</span><span class="sxs-lookup"><span data-stu-id="95aba-201">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="95aba-202">**From (Email)**: Indirizzo di posta elettronica del mittente.</span><span class="sxs-lookup"><span data-stu-id="95aba-202">**From (Email)**: The sender's email address.</span></span> <span data-ttu-id="95aba-203">È possibile immettere un indirizzo di posta elettronica reale o falso dal dominio di posta elettronica dell'organizzazione oppure un indirizzo di posta elettronica esterno reale o falso.</span><span class="sxs-lookup"><span data-stu-id="95aba-203">You can enter a real or fake email address from your organization's email domain, or you can enter a real or fake external email address.</span></span> <span data-ttu-id="95aba-204">Un indirizzo di posta elettronica del mittente valido dall'organizzazione verrà effettivamente risolto nel client di posta elettronica del destinatario.</span><span class="sxs-lookup"><span data-stu-id="95aba-204">A valid sender email address from your organization will actually resolve in the recipient's email client.</span></span>

   - <span data-ttu-id="95aba-205">**URL server di accesso phishing**: fare clic sull'elenco a discesa e selezionare uno degli URL disponibili nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="95aba-205">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="95aba-206">Questo è l'URL su cui gli utenti saranno tentati di fare clic.</span><span class="sxs-lookup"><span data-stu-id="95aba-206">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="95aba-207">Le opzioni disponibili sono:</span><span class="sxs-lookup"><span data-stu-id="95aba-207">The choices are:</span></span>

     - <http://portal.docdeliveryapp.com>
     - <http://portal.docdeliveryapp.net>
     - <http://portal.docstoreinternal.com>
     - <http://portal.docstoreinternal.net>
     - <http://portal.hardwarecheck.net>
     - <http://portal.hrsupportint.com>
     - <http://portal.payrolltooling.com>
     - <http://portal.payrolltooling.net>
     - <http://portal.prizegiveaway.net>
     - <http://portal.prizesforall.com>
     - <http://portal.salarytoolint.com>
     - <http://portal.salarytoolint.net>

     > [!NOTE]
     >
     > - <span data-ttu-id="95aba-208">Tutti gli URL sono intenzionalmente http, non https.</span><span class="sxs-lookup"><span data-stu-id="95aba-208">All of the URLs are intentionally http, not https.</span></span>
     >
     > - <span data-ttu-id="95aba-209">Un servizio di reputazione URL potrebbe identificare uno o più di questi URL come non sicuri.</span><span class="sxs-lookup"><span data-stu-id="95aba-209">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="95aba-210">Verificare la disponibilità dell'URL nei Web browser supportati prima di utilizzare l'URL in una campagna di phishing.</span><span class="sxs-lookup"><span data-stu-id="95aba-210">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span>
     >
     > - <span data-ttu-id="95aba-211">È necessario selezionare un URL.</span><span class="sxs-lookup"><span data-stu-id="95aba-211">You are required to select a URL.</span></span> <span data-ttu-id="95aba-212">Per **le campagne di spear phishing (allegato),** è possibile rimuovere il collegamento dal corpo del messaggio nel passaggio successivo (in caso contrario, il messaggio conterrà sia un **collegamento** che un allegato).</span><span class="sxs-lookup"><span data-stu-id="95aba-212">For **Spear Phishing (Attachment)** campaigns, you can remove the link from the body of the message in the next step (otherwise, the message will contain both a link **and** an attachment).</span></span>

   - <span data-ttu-id="95aba-213">**Tipo di allegato:** questa impostazione è disponibile solo nelle campagne **di spear phishing (allegato).**</span><span class="sxs-lookup"><span data-stu-id="95aba-213">**Attachment Type**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="95aba-214">Fare clic sull'elenco a **discesa e.DOCX** o **.PDF** dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="95aba-214">Click the drop down and select **.DOCX** or **.PDF** from the list.</span></span>

   - <span data-ttu-id="95aba-215">**Nome allegato**: questa impostazione è disponibile solo nelle campagne **di spear phishing (allegato).**</span><span class="sxs-lookup"><span data-stu-id="95aba-215">**Attachment Name**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="95aba-216">Immettere un nome di file per .docx o .pdf allegato.</span><span class="sxs-lookup"><span data-stu-id="95aba-216">Enter a filename for the .docx or .pdf attachment.</span></span>

   - <span data-ttu-id="95aba-217">**URL pagina di destinazione personalizzato:** immettere una pagina di destinazione facoltativa in cui vengono presi gli utenti se fanno clic sul collegamento di phishing e immettono le proprie credenziali.</span><span class="sxs-lookup"><span data-stu-id="95aba-217">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="95aba-218">Questo collegamento sostituisce la pagina di destinazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="95aba-218">This link replaces the default landing page.</span></span> <span data-ttu-id="95aba-219">Ad esempio, se hai un training di sensibilizzazione interno, puoi specificare questo URL qui.</span><span class="sxs-lookup"><span data-stu-id="95aba-219">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="95aba-220">**Subject**: Campo **Subject** del messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="95aba-220">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="95aba-221">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="95aba-221">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="95aba-222">Nel passaggio **Componi messaggio di** posta elettronica creare il corpo del messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="95aba-222">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="95aba-223">Se è stato selezionato un modello nel **passaggio Start,** il corpo del messaggio è già configurato, ma è possibile personalizzarlo.</span><span class="sxs-lookup"><span data-stu-id="95aba-223">If you selected a template in the **Start** step, the message body is already configured, but you can customize it.</span></span> <span data-ttu-id="95aba-224">È possibile utilizzare la **scheda Posta** elettronica (un editor HTML avanzato) o la **scheda Origine** (codice HTML non elaborato).</span><span class="sxs-lookup"><span data-stu-id="95aba-224">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="95aba-225">La formattazione HTML può essere semplice o complessa come necessario.</span><span class="sxs-lookup"><span data-stu-id="95aba-225">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="95aba-226">È possibile inserire immagini e testo per migliorare la credibilità del messaggio nel client di posta elettronica del destinatario.</span><span class="sxs-lookup"><span data-stu-id="95aba-226">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="95aba-227">`${username}` inserisce il nome del destinatario.</span><span class="sxs-lookup"><span data-stu-id="95aba-227">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="95aba-228">`${loginserverurl}` inserisce il valore **URL del server di accesso** phishing.</span><span class="sxs-lookup"><span data-stu-id="95aba-228">`${loginserverurl}` inserts the **Phishing Login Server URL** value.</span></span>

   <span data-ttu-id="95aba-229">Per le campagne **di spear phishing (allegato),** è consigliabile rimuovere il collegamento dal  corpo del messaggio (in caso contrario, il messaggio conterrà sia un collegamento che un allegato e i clic sui collegamenti non vengono monitorati in una campagna allegato).</span><span class="sxs-lookup"><span data-stu-id="95aba-229">For **Spear Phishing (Attachment)** campaigns, you should remove the link from the body of the message (otherwise, the message will contain both a link **and** an attachment, and link clicks aren't tracked in an attachment campaign).</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="95aba-230">![Componi corpo del messaggio di posta elettronica](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)</span><span class="sxs-lookup"><span data-stu-id="95aba-230">![Compose Email Body](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)</span></span>

   <span data-ttu-id="95aba-231">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="95aba-231">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="95aba-232">Nel passaggio **Conferma** fare clic su **Fine** per avviare la campagna.</span><span class="sxs-lookup"><span data-stu-id="95aba-232">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="95aba-233">Il messaggio di phishing viene recapitato ai destinatari di destinazione.</span><span class="sxs-lookup"><span data-stu-id="95aba-233">The phishing message is delivered to the targeted recipients.</span></span>

## <a name="password-attack-campaigns"></a><span data-ttu-id="95aba-234">Campagne di attacco con password</span><span class="sxs-lookup"><span data-stu-id="95aba-234">Password attack campaigns</span></span>

<span data-ttu-id="95aba-235">Un *attacco tramite password* tenta di indovinare le password per gli account utente in un'organizzazione, in genere dopo che l'utente malintenzionato ha identificato uno o più account utente validi.</span><span class="sxs-lookup"><span data-stu-id="95aba-235">A *password attack* tries to guess passwords for user accounts in an organization, typically after the attacker has identified one or more valid user accounts.</span></span>

<span data-ttu-id="95aba-236">In Attack Simulator sono disponibili due diversi tipi di campagne di attacco delle password per testare la complessità delle password degli utenti:</span><span class="sxs-lookup"><span data-stu-id="95aba-236">In Attack Simulator, two different types of password attack campaigns are available for you to test the complexity of your users' passwords:</span></span>

- <span data-ttu-id="95aba-237">**Brute force password (attacco dizionario):** un  attacco di forza *bruta* o dizionario usa un file di dizionario di grandi dimensioni di password su un account utente con la speranza che una di esse funzioni (molte password su un account).</span><span class="sxs-lookup"><span data-stu-id="95aba-237">**Brute force password (dictionary attack)**: A *brute force* or *dictionary* attack uses a large dictionary file of passwords on a user account with the hope that one of them will work (many passwords against one account).</span></span> <span data-ttu-id="95aba-238">I blocchi delle password non corretti consentono di scoraggiare gli attacchi di forza bruta delle password.</span><span class="sxs-lookup"><span data-stu-id="95aba-238">Incorrect password lock-outs help deter brute force password attacks.</span></span>

  <span data-ttu-id="95aba-239">Per l'attacco al dizionario, puoi specificare una o più password da provare (immesse manualmente o in un file caricato) e puoi specificare uno o più utenti.</span><span class="sxs-lookup"><span data-stu-id="95aba-239">For the dictionary attack, you can specify one or many passwords to try (manually entered or in an uploaded file), and you can specify one or many users.</span></span>

- <span data-ttu-id="95aba-240">**Attacco con spray per password**: un attacco con *spray* per password usa la stessa password attentamente considerata per un elenco di account utente (una password per molti account).</span><span class="sxs-lookup"><span data-stu-id="95aba-240">**Password spray attack**: A *password spray* attack uses the same carefully considered password against a list of user accounts (one password against many accounts).</span></span> <span data-ttu-id="95aba-241">Gli attacchi di tipo password spray sono più difficili da rilevare rispetto agli attacchi di forza bruta delle password (la probabilità di successo aumenta quando un utente malintenzionato tenta una password su decine o centinaia di account senza il rischio di inciampare nel blocco non corretto della password dell'utente).</span><span class="sxs-lookup"><span data-stu-id="95aba-241">Password spray attacks are harder to detect than brute force password attacks (the probability of success increases when an attacker tries one password across dozens or hundreds of accounts without the risk of tripping the user's incorrect password lock-out).</span></span>

  <span data-ttu-id="95aba-242">Per l'attacco con spray per le password, è possibile specificare una sola password da provare e uno o più utenti.</span><span class="sxs-lookup"><span data-stu-id="95aba-242">For the password spray attack, you can only specify one password to try, and you can specify one or many users.</span></span>

> [!NOTE]
> <span data-ttu-id="95aba-243">Gli attacchi alle password in Attack Simulator passano le richieste di autenticazione di base e nome utente a un endpoint, quindi funzionano anche con altri metodi di autenticazione (AD FS, sincronizzazione hash delle password, pass-through, PingFederate e così via).</span><span class="sxs-lookup"><span data-stu-id="95aba-243">The password attacks in Attack Simulator pass username and password Basic auth requests to an endpoint, so they also work with other authentication methods (AD FS, password hash sync, pass-through, PingFederate, etc.).</span></span> <span data-ttu-id="95aba-244">Per gli utenti con MFA abilitata, anche se l'attacco con password tenta la password effettiva, il tentativo  verrà sempre registrato come errore (in altre parole, gli utenti MFA non verranno mai visualizzati nel conteggio dei tentativi riusciti della campagna).</span><span class="sxs-lookup"><span data-stu-id="95aba-244">For users that have MFA enabled, even if the password attack tries their actual password, the attempt will always register as a failure (in other words, MFA users will never appear in the **Successful attempts** count of the campaign).</span></span> <span data-ttu-id="95aba-245">Questo è il risultato previsto.</span><span class="sxs-lookup"><span data-stu-id="95aba-245">This is the expected result.</span></span> <span data-ttu-id="95aba-246">L'autenticazione a più fattori è un metodo principale per proteggere dagli attacchi delle password.</span><span class="sxs-lookup"><span data-stu-id="95aba-246">MFA is a primary method to help protect against password attacks.</span></span>

### <a name="create-and-launch-a-password-attack-campaign"></a><span data-ttu-id="95aba-247">Creare e avviare una campagna di attacco tramite password</span><span class="sxs-lookup"><span data-stu-id="95aba-247">Create and launch a password attack campaign</span></span>

1. <span data-ttu-id="95aba-248">Nel Centro sicurezza & conformità passare a **Gestione delle** minacce \> **Simulatore di attacco.**</span><span class="sxs-lookup"><span data-stu-id="95aba-248">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="95aba-249">Nella pagina **Simula attacchi** effettuare una delle selezioni seguenti in base al tipo di campagna che si desidera creare:</span><span class="sxs-lookup"><span data-stu-id="95aba-249">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="95aba-250">Nella sezione **Brute Force Password (Dictionary Attack)** fai clic su **Launch Attack** o su **Attack Details** \> **Launch Attack.**</span><span class="sxs-lookup"><span data-stu-id="95aba-250">In the **Brute Force Password (Dictionary Attack)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="95aba-251">nella sezione **Attacco spray password** fare clic su Avvia **attacco** o su **Dettagli attacco** \> **Attacco.**</span><span class="sxs-lookup"><span data-stu-id="95aba-251">in the **Password spray attack** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="95aba-252">La **procedura guidata Configura attacco password** viene avviata in un nuovo riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="95aba-252">The **Configure Password Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="95aba-253">Nel passaggio **Start** immettere un nome visualizzato univoco per la campagna e quindi fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="95aba-253">In the **Start** step, enter a unique display name for the campaign, and then click **Next**.</span></span>

4. <span data-ttu-id="95aba-254">Nel passaggio **Utenti di** destinazione eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="95aba-254">In the **Target users** step, do one of the following steps:</span></span>

   - <span data-ttu-id="95aba-255">Fare **clic su Rubrica** per selezionare i destinatari (utenti o gruppi) per la campagna.</span><span class="sxs-lookup"><span data-stu-id="95aba-255">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="95aba-256">Ogni destinatario di destinazione deve disporre di Exchange Online cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="95aba-256">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="95aba-257">Se si fa **clic su Filtro** e **Applica** senza immettere criteri di ricerca, tutti i destinatari vengono restituiti e aggiunti alla campagna.</span><span class="sxs-lookup"><span data-stu-id="95aba-257">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="95aba-258">Fare **clic su** **Importa, quindi su** Importazione file per importare un valore delimitato da virgole (CSV) o un file di indirizzi di posta elettronica separati da righe.</span><span class="sxs-lookup"><span data-stu-id="95aba-258">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="95aba-259">Ogni riga deve contenere l'indirizzo di posta elettronica del destinatario.</span><span class="sxs-lookup"><span data-stu-id="95aba-259">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="95aba-260">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="95aba-260">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="95aba-261">Nel passaggio **Scegliere le impostazioni di** attacco scegliere l'operazione da eseguire in base al tipo di campagna:</span><span class="sxs-lookup"><span data-stu-id="95aba-261">In the **Choose attack settings** step, choose what to do based on the campaign type:</span></span>

   - <span data-ttu-id="95aba-262">**Brute Force Password (Dictionary Attack):** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="95aba-262">**Brute Force Password (Dictionary Attack)**: Do either of the following steps:</span></span>

     - <span data-ttu-id="95aba-263">**Immettere manualmente le password:** nella **casella Premere INVIO per aggiungere** una password digitare una password e quindi premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="95aba-263">**Enter passwords manually**: In the **Press enter to add a password** box, type a password and then press ENTER.</span></span> <span data-ttu-id="95aba-264">Ripetere questo passaggio tutte le volte necessarie.</span><span class="sxs-lookup"><span data-stu-id="95aba-264">Repeat this step as many times as necessary.</span></span>

     - <span data-ttu-id="95aba-265">**Upload password da** un file di  dizionario: fare clic su Upload per importare un file di testo esistente contenente una password in ogni riga e un'ultima riga vuota.</span><span class="sxs-lookup"><span data-stu-id="95aba-265">**Upload passwords from a dictionary file**: Click **Upload** to import an existing text file that contains one password on each line and a blank last line.</span></span> <span data-ttu-id="95aba-266">Le dimensioni del file di testo devono essere pari o inferiori a 10 MB e non possono contenere più di 30000 password.</span><span class="sxs-lookup"><span data-stu-id="95aba-266">The text file must be 10 MB or less in size, and can't contain more than 30000 passwords.</span></span>

   - <span data-ttu-id="95aba-267">**Attacco con spray per la** password : in Le password da usare nella casella **di** attacco immettere una password.</span><span class="sxs-lookup"><span data-stu-id="95aba-267">**Password spray attack**: In **The password(s) to use in the attack** box, enter one password.</span></span>

   <span data-ttu-id="95aba-268">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="95aba-268">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="95aba-269">Nel passaggio **Conferma** fare clic su **Fine** per avviare la campagna.</span><span class="sxs-lookup"><span data-stu-id="95aba-269">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="95aba-270">Le password specificate vengono tentate per gli utenti specificati.</span><span class="sxs-lookup"><span data-stu-id="95aba-270">The passwords you specified are tried on users you specified.</span></span>

## <a name="view-campaign-results"></a><span data-ttu-id="95aba-271">Visualizzare i risultati della campagna</span><span class="sxs-lookup"><span data-stu-id="95aba-271">View campaign results</span></span>

<span data-ttu-id="95aba-272">Dopo aver avviato una campagna, puoi controllare l'avanzamento e i risultati nella pagina **principale Simula attacchi.**</span><span class="sxs-lookup"><span data-stu-id="95aba-272">After you launch a campaign, you can check the progress and results on the main **Simulate attacks** page.</span></span>

<span data-ttu-id="95aba-273">Le campagne attive mostreranno una barra di stato, un valore percentuale completato e il conteggio "(utenti completati) di (utenti totali)".</span><span class="sxs-lookup"><span data-stu-id="95aba-273">Active campaigns will show a status bar, a completed percentage value and "(completed users) of (total users)" count.</span></span> <span data-ttu-id="95aba-274">Facendo clic **sul** pulsante Aggiorna verrà aggiornato lo stato di avanzamento di tutte le campagne attive.</span><span class="sxs-lookup"><span data-stu-id="95aba-274">Clicking the **Refresh** button will update the progress of any active campaigns.</span></span> <span data-ttu-id="95aba-275">Puoi anche fare clic **su Termina** per interrompere una campagna attiva.</span><span class="sxs-lookup"><span data-stu-id="95aba-275">You can also click **Terminate** to stop an active campaign.</span></span>

<span data-ttu-id="95aba-276">Al termine della campagna, lo stato viene modificato in **Attacco completato.**</span><span class="sxs-lookup"><span data-stu-id="95aba-276">When the campaign is finished, the status changes to **Attack completed**.</span></span> <span data-ttu-id="95aba-277">È possibile visualizzare i risultati della campagna eseguendo una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="95aba-277">You can view the results of the campaign by doing either of the following actions:</span></span>

- <span data-ttu-id="95aba-278">Nella pagina principale **Simula attacchi** fare clic su **Visualizza report** sotto il nome della campagna.</span><span class="sxs-lookup"><span data-stu-id="95aba-278">On the main **Simulate attacks** page, click **View Report** under the name of the campaign.</span></span>

- <span data-ttu-id="95aba-279">Nella pagina principale **Simula attacchi** fare clic su **Dettagli** attacco nella sezione relativa al tipo di attacco.</span><span class="sxs-lookup"><span data-stu-id="95aba-279">On the main **Simulate attacks** page, click **Attack Details** in the section for the type of attack.</span></span> <span data-ttu-id="95aba-280">Nella pagina **Dettagli attacco** visualizzata selezionare la campagna nella sezione **Cronologia** attacchi.</span><span class="sxs-lookup"><span data-stu-id="95aba-280">On the **Attack details** page that opens, select the campaign in the **Attack History** section.</span></span>

<span data-ttu-id="95aba-281">Una delle azioni precedenti consente di accedere a una pagina denominata **Dettagli attacco.**</span><span class="sxs-lookup"><span data-stu-id="95aba-281">Either of the previous actions will take you to a page named **Attack details**.</span></span> <span data-ttu-id="95aba-282">Le informazioni disponibili in questa pagina per ogni tipo di campagna sono descritte nelle sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="95aba-282">The information that's available on this page for each type of campaign is described in the following sections.</span></span>

### <a name="spear-phishing-credentials-harvest-campaign-results"></a><span data-ttu-id="95aba-283">Risultati della campagna Spear Phishing (Credentials Harvest)</span><span class="sxs-lookup"><span data-stu-id="95aba-283">Spear Phishing (Credentials Harvest) campaign results</span></span>

<span data-ttu-id="95aba-284">Nella pagina Dettagli attacco  per ogni campagna sono disponibili le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="95aba-284">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="95aba-285">Durata (data/ora di inizio e data/ora di fine) della campagna.</span><span class="sxs-lookup"><span data-stu-id="95aba-285">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="95aba-286">**Totale utenti di destinazione**</span><span class="sxs-lookup"><span data-stu-id="95aba-286">**Total users targeted**</span></span>

- <span data-ttu-id="95aba-287">**Tentativi riusciti**: numero di utenti che hanno fatto clic sul **collegamento** e hanno immesso le proprie credenziali *(qualsiasi valore* di nome utente e password).</span><span class="sxs-lookup"><span data-stu-id="95aba-287">**Successful attempts**: The number of users who clicked the link **and** entered their credentials (*any* username and password value).</span></span>

- <span data-ttu-id="95aba-288">**Tasso di successo complessivo**: percentuale calcolata in base ai tentativi **riusciti** Totale  /  **utenti mirati.**</span><span class="sxs-lookup"><span data-stu-id="95aba-288">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="95aba-289">**Clic più rapido:** tempo impiegato dal primo utente per fare clic sul collegamento dopo l'avvio della campagna.</span><span class="sxs-lookup"><span data-stu-id="95aba-289">**Fastest Click**: How long it took the first user to click the link after you launched the campaign.</span></span>

- <span data-ttu-id="95aba-290">**Media clic**: somma del tempo impiegato da tutti gli utenti per fare clic sul collegamento diviso per il numero di utenti che hanno fatto clic sul collegamento.</span><span class="sxs-lookup"><span data-stu-id="95aba-290">**Average Click**: The sum of how long it took everyone to click the link divided by the number of users who clicked the link.</span></span>

- <span data-ttu-id="95aba-291">**Click Success Rate**: Percentuale calcolata da (numero di utenti che hanno fatto clic sul collegamento) / **Totale utenti mirati**.</span><span class="sxs-lookup"><span data-stu-id="95aba-291">**Click Success Rate**: A percentage that's calculated by (number of users who clicked the link) / **Total users targeted**.</span></span>

- <span data-ttu-id="95aba-292">**Credenziali più veloci**: tempo impiegato dal primo utente per immettere le credenziali dopo l'avvio della campagna.</span><span class="sxs-lookup"><span data-stu-id="95aba-292">**Fastest Credentials**: How long it took the first user to enter their credentials after you launched the campaign.</span></span>

- <span data-ttu-id="95aba-293">**Credenziali medie**: somma del tempo impiegato da tutti per immettere le credenziali diviso per il numero di utenti che hanno immesso le proprie credenziali.</span><span class="sxs-lookup"><span data-stu-id="95aba-293">**Average Credentials**: The sum of how long it took everyone to enter their credentials divided by the number of users who entered their credentials.</span></span>

- <span data-ttu-id="95aba-294">**Percentuale di successo delle** credenziali : percentuale calcolata da (numero di utenti che hanno immesso le credenziali) / **Totale utenti di destinazione.**</span><span class="sxs-lookup"><span data-stu-id="95aba-294">**Credential Success Rate**: A percentage that's calculated by (number of users who entered their credentials) / **Total users targeted**.</span></span>

- <span data-ttu-id="95aba-295">Grafico a barre che mostra i **numeri di collegamento** su cui è stato fatto clic e i numeri forniti per le **credenziali** al giorno.</span><span class="sxs-lookup"><span data-stu-id="95aba-295">A bar graph that shows the **Link clicked** and **Credential supplied** numbers per day.</span></span>

- <span data-ttu-id="95aba-296">Grafico a cerchi che mostra **le** percentuali Collegamento fatto **clic,** Credenziali fornite e **Nessuna** per la campagna.</span><span class="sxs-lookup"><span data-stu-id="95aba-296">A circle graph that shows the **Link clicked**, **Credential supplied**, and **None** percentages for the campaign.</span></span>

- <span data-ttu-id="95aba-297">Nella **sezione Utenti compromessi** sono elencati i dettagli degli utenti che hanno fatto clic sul collegamento:</span><span class="sxs-lookup"><span data-stu-id="95aba-297">The **Compromised Users** section lists the details of the users who clicked the link:</span></span>

  - <span data-ttu-id="95aba-298">L'indirizzo di posta elettronica dell'utente</span><span class="sxs-lookup"><span data-stu-id="95aba-298">The user's email address</span></span>

  - <span data-ttu-id="95aba-299">Data/ora in cui è stato fatto clic sul collegamento.</span><span class="sxs-lookup"><span data-stu-id="95aba-299">The date/time when they clicked the link.</span></span>

  - <span data-ttu-id="95aba-300">L'indirizzo IP del client.</span><span class="sxs-lookup"><span data-stu-id="95aba-300">The client IP address.</span></span>

  - <span data-ttu-id="95aba-301">Dettagli sulla versione dell'utente di Windows web browser.</span><span class="sxs-lookup"><span data-stu-id="95aba-301">Details about the user's version of Windows and web browser.</span></span>

  <span data-ttu-id="95aba-302">È possibile fare **clic su Esporta** per esportare i risultati in un file CSV.</span><span class="sxs-lookup"><span data-stu-id="95aba-302">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="spear-phishing-attachment-campaign-results"></a><span data-ttu-id="95aba-303">Risultati della campagna spear phishing (allegato)</span><span class="sxs-lookup"><span data-stu-id="95aba-303">Spear Phishing (Attachment) campaign results</span></span>

<span data-ttu-id="95aba-304">Nella pagina Dettagli attacco  per ogni campagna sono disponibili le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="95aba-304">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="95aba-305">Durata (data/ora di inizio e data/ora di fine) della campagna.</span><span class="sxs-lookup"><span data-stu-id="95aba-305">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="95aba-306">**Totale utenti di destinazione**</span><span class="sxs-lookup"><span data-stu-id="95aba-306">**Total users targeted**</span></span>

- <span data-ttu-id="95aba-307">**Tentativi riusciti:** numero di utenti che hanno aperto o scaricato e aperto l'allegato (l'anteprima non viene conteggiato).</span><span class="sxs-lookup"><span data-stu-id="95aba-307">**Successful attempts**: The number of users who opened or downloaded and opened the attachment (preview doesn't count).</span></span>

- <span data-ttu-id="95aba-308">**Tasso di successo complessivo**: percentuale calcolata in base ai tentativi **riusciti** Totale  /  **utenti mirati.**</span><span class="sxs-lookup"><span data-stu-id="95aba-308">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="95aba-309">**Tempo di apertura dell'allegato** più rapido: tempo impiegato dal primo utente per aprire l'allegato dopo l'avvio della campagna.</span><span class="sxs-lookup"><span data-stu-id="95aba-309">**Fastest attachment open time**: How long it took the first user to open the attachment after you launched the campaign.</span></span>

- <span data-ttu-id="95aba-310">**Tempo medio di apertura degli allegati**: somma del tempo impiegato da tutti gli utenti per aprire l'allegato diviso per il numero di utenti che hanno aperto l'allegato.</span><span class="sxs-lookup"><span data-stu-id="95aba-310">**Average attachment open time**: The sum of how long it took everyone to open the attachment divided by the number of users who opened the attachment.</span></span>

- <span data-ttu-id="95aba-311">**Percentuale di esito positivo dell'apertura** degli allegati : percentuale calcolata da (numero di utenti che hanno aperto l'allegato) / **Totale utenti di destinazione.**</span><span class="sxs-lookup"><span data-stu-id="95aba-311">**Attachment open success rate**: A percentage that's calculated by (number of users who opened the attachment) / **Total users targeted**.</span></span>

### <a name="brute-force-password-dictionary-attack-campaign-results"></a><span data-ttu-id="95aba-312">Risultati della campagna Brute Force Password (Dictionary Attack)</span><span class="sxs-lookup"><span data-stu-id="95aba-312">Brute Force Password (Dictionary Attack) campaign results</span></span>

<span data-ttu-id="95aba-313">Nella pagina Dettagli attacco  per ogni campagna sono disponibili le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="95aba-313">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="95aba-314">Durata (data/ora di inizio e data/ora di fine) della campagna.</span><span class="sxs-lookup"><span data-stu-id="95aba-314">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="95aba-315">**Totale utenti di destinazione**</span><span class="sxs-lookup"><span data-stu-id="95aba-315">**Total users targeted**</span></span>

- <span data-ttu-id="95aba-316">**Tentativi** riusciti: numero di utenti che sono stati trovati che utilizzano una delle password specificate.</span><span class="sxs-lookup"><span data-stu-id="95aba-316">**Successful attempts**: The number of users who were found to be using one of the specified passwords.</span></span>

- <span data-ttu-id="95aba-317">**Tasso di successo complessivo**: percentuale calcolata in base ai tentativi **riusciti** Totale  /  **utenti mirati.**</span><span class="sxs-lookup"><span data-stu-id="95aba-317">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="95aba-318">Nella **sezione Utenti compromessi** sono elencati gli indirizzi di posta elettronica degli utenti interessati.</span><span class="sxs-lookup"><span data-stu-id="95aba-318">The **Compromised Users** section lists the email addresses of the affected users.</span></span> <span data-ttu-id="95aba-319">È possibile fare **clic su Esporta** per esportare i risultati in un file CSV.</span><span class="sxs-lookup"><span data-stu-id="95aba-319">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="password-spray-attack-campaign-results"></a><span data-ttu-id="95aba-320">Risultati della campagna di attacco con spray per password</span><span class="sxs-lookup"><span data-stu-id="95aba-320">Password spray attack campaign results</span></span>

<span data-ttu-id="95aba-321">Nella pagina Dettagli attacco  per ogni campagna sono disponibili le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="95aba-321">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="95aba-322">Durata (data/ora di inizio e data/ora di fine) della campagna.</span><span class="sxs-lookup"><span data-stu-id="95aba-322">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="95aba-323">**Totale utenti di destinazione**</span><span class="sxs-lookup"><span data-stu-id="95aba-323">**Total users targeted**</span></span>

- <span data-ttu-id="95aba-324">**Tentativi riusciti**: numero di utenti che sono stati trovati che utilizzano la password specificata.</span><span class="sxs-lookup"><span data-stu-id="95aba-324">**Successful attempts**: The number of users who were found to be using the specified password.</span></span>

- <span data-ttu-id="95aba-325">**Tasso di successo complessivo**: percentuale calcolata in base ai tentativi **riusciti** Totale  /  **utenti mirati.**</span><span class="sxs-lookup"><span data-stu-id="95aba-325">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>
