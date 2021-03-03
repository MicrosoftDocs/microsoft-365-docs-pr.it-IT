---
title: Simulatore di attacchi in Microsoft Defender per Office 365
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
description: Gli amministratori possono imparare a usare il simulatore di attacchi per eseguire attacchi simulati di phishing e password nelle organizzazioni di Microsoft 365 E5 o Microsoft Defender per Office 365 Piano 2.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 85b376701ffa0c567fd66aa629371e9f69b354e9
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/03/2021
ms.locfileid: "50407474"
---
# <a name="attack-simulator-in-microsoft-defender-for-office-365"></a><span data-ttu-id="0d896-103">Simulatore di attacchi in Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="0d896-103">Attack Simulator in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="0d896-104">**Si applica a** [Microsoft Defender per Office 365 piano 2](office-365-atp.md)</span><span class="sxs-lookup"><span data-stu-id="0d896-104">**Applies to** [Microsoft Defender for Office 365 plan 2](office-365-atp.md)</span></span>

<span data-ttu-id="0d896-105">Se l'organizzazione dispone di Microsoft Defender per Office 365 Piano 2, che include funzionalità di analisi e risposta alle [minacce,](office-365-ti.md)è possibile utilizzare il simulatore di attacchi nel Centro sicurezza & e conformità per eseguire scenari di attacco realistici nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="0d896-105">If your organization has Microsoft Defender for Office 365 Plan 2, which includes [Threat Investigation and Response capabilities](office-365-ti.md), you can use Attack Simulator in the Security & Compliance Center to run realistic attack scenarios in your organization.</span></span> <span data-ttu-id="0d896-106">Questi attacchi simulati consentono di identificare e individuare gli utenti vulnerabili prima che un attacco reale influisca sui tuoi utili.</span><span class="sxs-lookup"><span data-stu-id="0d896-106">These simulated attacks can help you identify and find vulnerable users before a real attack impacts your bottom line.</span></span> <span data-ttu-id="0d896-107">Leggi questo articolo per altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="0d896-107">Read this article to learn more.</span></span>

> [!NOTE]
> <span data-ttu-id="0d896-108">L'esperienza del simulatore di attacchi v1 è stata passata alla modalità di sola lettura e sostituita dal training del simulatore di attacco descritto in Introduzione all'uso della formazione per la simulazione [degli attacchi.](attack-simulation-training-get-started.md)</span><span class="sxs-lookup"><span data-stu-id="0d896-108">Attack Simulator v1 experience has been switched to read-only mode and replaced by Attack simulator training that's described in [Get started using Attack simulation training](attack-simulation-training-get-started.md).</span></span>
> <span data-ttu-id="0d896-109">La possibilità di avviare nuove simulazioni da questo sito è stata disabilitata.</span><span class="sxs-lookup"><span data-stu-id="0d896-109">The ability to launch new simulations from this site has been disabled.</span></span> <span data-ttu-id="0d896-110">Tuttavia, è comunque possibile accedere ai report per le simulazioni eseguite per un periodo di 90 giorni dal 24 gennaio 2021.</span><span class="sxs-lookup"><span data-stu-id="0d896-110">However, you can still access reports for simulations run for a period of 90 days from January 24, 2021.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="0d896-111">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="0d896-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="0d896-112">Per aprire il Centro sicurezza e conformità, passare a <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="0d896-112">To open the Security & Compliance Center, go to <https://protection.office.com/>.</span></span> <span data-ttu-id="0d896-113">Il simulatore  di attacco è disponibile nel \> **simulatore di attacco per la gestione delle minacce.**</span><span class="sxs-lookup"><span data-stu-id="0d896-113">Attack simulator is available at **Threat management** \> **Attack simulator**.</span></span> <span data-ttu-id="0d896-114">Vai direttamente al simulatore di attacco, apri <https://protection.office.com/attacksimulator> .</span><span class="sxs-lookup"><span data-stu-id="0d896-114">Go go directly to attack simulator, open <https://protection.office.com/attacksimulator>.</span></span>

- <span data-ttu-id="0d896-115">Per ulteriori informazioni sulla disponibilità del simulatore di attacchi tra diversi abbonamenti a Microsoft 365, vedere Descrizione del servizio [Microsoft Defender per Office 365.](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)</span><span class="sxs-lookup"><span data-stu-id="0d896-115">For more information about the availability of Attack Simulator across different Microsoft 365 subscriptions, see [Microsoft Defender for Office 365 service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

- <span data-ttu-id="0d896-116">È necessario essere membri dei gruppi di ruoli **Gestione organizzazione** o **Amministratore** sicurezza.</span><span class="sxs-lookup"><span data-stu-id="0d896-116">You need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="0d896-117">Per altre informazioni sui gruppi di ruoli nel Centro sicurezza e conformità, vedere [Autorizzazioni nel Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="0d896-117">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="0d896-118">Il tuo account deve essere configurato per l'autenticazione a più fattori (MFA) per creare e gestire campagne in Simulatore di attacchi.</span><span class="sxs-lookup"><span data-stu-id="0d896-118">Your account needs to be configured for multi-factor authentication (MFA) to create and manage campaigns in Attack Simulator.</span></span> <span data-ttu-id="0d896-119">Per istruzioni, vedere [Configurare l'autenticazione a più fattori.](../../admin/security-and-compliance/set-up-multi-factor-authentication.md)</span><span class="sxs-lookup"><span data-stu-id="0d896-119">For instructions, see [Set up multi-factor authentication](../../admin/security-and-compliance/set-up-multi-factor-authentication.md).</span></span>

- <span data-ttu-id="0d896-120">Il simulatore di attacchi funziona solo sulle cassette postali basate sul cloud.</span><span class="sxs-lookup"><span data-stu-id="0d896-120">Attack Simulator only works on cloud-based mailboxes.</span></span>

- <span data-ttu-id="0d896-121">Le campagne di phishing raccoglieranno ed eelaborare gli eventi per 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="0d896-121">Phishing campaigns will collect and process events for 30 days.</span></span> <span data-ttu-id="0d896-122">I dati cronologici della campagna saranno disponibili fino a 90 giorni dopo l'avvio della campagna.</span><span class="sxs-lookup"><span data-stu-id="0d896-122">Historical campaign data will be available for up to 90 days after you launch the campaign.</span></span>

- <span data-ttu-id="0d896-123">I dati correlati alla simulazione e alla formazione degli attacchi vengono archiviati con altri dati dei clienti per i servizi di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0d896-123">Attack simulation and training related data is stored with other customer data for Microsoft 365 services.</span></span> <span data-ttu-id="0d896-124">Per altre informazioni, vedere [Percorsi dei dati di Microsoft 365.](/microsoft-365/enterprise/o365-data-locations)</span><span class="sxs-lookup"><span data-stu-id="0d896-124">For more information see [Microsoft 365 data locations](/microsoft-365/enterprise/o365-data-locations).</span></span>

- <span data-ttu-id="0d896-125">Non sono disponibili cmdlet di PowerShell corrispondenti per il simulatore di attacchi.</span><span class="sxs-lookup"><span data-stu-id="0d896-125">There are no corresponding PowerShell cmdlets for Attack Simulator.</span></span>

## <a name="spear-phishing-campaigns"></a><span data-ttu-id="0d896-126">Campagne di phishing con phishing</span><span class="sxs-lookup"><span data-stu-id="0d896-126">Spear phishing campaigns</span></span>

<span data-ttu-id="0d896-127">*Il phishing* è un termine generico per gli attacchi di posta elettronica che tentano di rubare informazioni riservate nei messaggi che sembrano essere provenienti da mittenti legittimi o attendibili.</span><span class="sxs-lookup"><span data-stu-id="0d896-127">*Phishing* is a generic term for email attacks that try to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="0d896-128">*Il phishing* di phishing è un attacco di phishing mirato che utilizza contenuti mirati e personalizzati appositamente personalizzati per i destinatari di destinazione (in genere, dopo la ricognizione sui destinatari da parte dell'autore dell'attacco).</span><span class="sxs-lookup"><span data-stu-id="0d896-128">*Spear phishing* is a targeted phishing attack that uses focused and customized content that's specifically tailored to the targeted recipients (typically, after reconnaissance on the recipients by the attacker).</span></span>

<span data-ttu-id="0d896-129">Nel simulatore di attacchi sono disponibili due diversi tipi di campagne di phishing:</span><span class="sxs-lookup"><span data-stu-id="0d896-129">In Attack Simulator, two different types of spear phishing campaigns are available:</span></span>

- <span data-ttu-id="0d896-130">**Spear phishing (raccolta di credenziali):** l'attacco tenta di convincere i destinatari a fare clic su un URL nel messaggio.</span><span class="sxs-lookup"><span data-stu-id="0d896-130">**Spear phishing (credentials harvest)**: The attack tries to convince the recipients to click a URL in the message.</span></span> <span data-ttu-id="0d896-131">Se fa clic sul collegamento, viene richiesto di immettere le proprie credenziali.</span><span class="sxs-lookup"><span data-stu-id="0d896-131">If they click the link, they're asked to enter their credentials.</span></span> <span data-ttu-id="0d896-132">In caso contrario, vengono portati in una delle posizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0d896-132">If they do, they're taken to one of the following locations:</span></span>

  - <span data-ttu-id="0d896-133">Una pagina predefinita che spiega che si tratta di un semplice test e fornisce suggerimenti per il riconoscimento dei messaggi di phishing.</span><span class="sxs-lookup"><span data-stu-id="0d896-133">A default page that explains that this was a just a test, and gives tips for recognizing phishing messages.</span></span>

    ![Cosa viene visualizzato dagli utenti se fanno clic sul collegamento di phishing e immettono le proprie credenziali](../../media/attack-simulator-phishing-result.png)

  - <span data-ttu-id="0d896-135">Una pagina personalizzata (URL) specificata dall'utente.</span><span class="sxs-lookup"><span data-stu-id="0d896-135">A custom page (URL) that you specify.</span></span>

- <span data-ttu-id="0d896-136">**Spear phishing (allegato):** l'attacco tenta di convincere i destinatari ad aprire un allegato .docx o .pdf nel messaggio.</span><span class="sxs-lookup"><span data-stu-id="0d896-136">**Spear phishing (attachment)**: The attack tries to convince the recipients to open a .docx or .pdf attachment in the message.</span></span> <span data-ttu-id="0d896-137">L'allegato contiene lo stesso contenuto del collegamento di phishing predefinito, ma la prima frase inizia con " , il messaggio viene visualizzato come un messaggio di posta elettronica recente \<Display Name\> aperto...".</span><span class="sxs-lookup"><span data-stu-id="0d896-137">The attachment contains the same content from the default phishing link, but the first sentence starts with "\<Display Name\>, you are seeing this message as a recent email message you opened...".</span></span>

> [!NOTE]
> <span data-ttu-id="0d896-138">Attualmente, le campagne di spear phishing nel simulatore di attacchi non scadono.</span><span class="sxs-lookup"><span data-stu-id="0d896-138">Currently, spear phishing campaigns in Attack Simulator don't expire.</span></span>

### <a name="create-a-spear-phishing-campaign"></a><span data-ttu-id="0d896-139">Creare una campagna di phishing con phishing</span><span class="sxs-lookup"><span data-stu-id="0d896-139">Create a spear phishing campaign</span></span>

<span data-ttu-id="0d896-140">Una parte importante di qualsiasi campagna di phishing è l'aspetto del messaggio di posta elettronica inviato ai destinatari di destinazione.</span><span class="sxs-lookup"><span data-stu-id="0d896-140">An important part of any spear phishing campaign is the look and feel of the email message that's sent to the targeted recipients.</span></span> <span data-ttu-id="0d896-141">Per creare e configurare il messaggio di posta elettronica, sono disponibili le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0d896-141">To create and configure the email message, you have these options:</span></span>

- <span data-ttu-id="0d896-142">**Usa un modello di posta elettronica predefinito:** sono disponibili due modelli predefiniti: **Evaso** e Aggiornamento **paghe.**</span><span class="sxs-lookup"><span data-stu-id="0d896-142">**Use a built-in email template**: Two built-in templates are available: **Prize Giveaway** and **Payroll Update**.</span></span> <span data-ttu-id="0d896-143">Puoi personalizzare ulteriormente alcune, tutte o nessuna delle proprietà di posta elettronica del modello quando crei e avvii la campagna.</span><span class="sxs-lookup"><span data-stu-id="0d896-143">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="0d896-144">**Creare un modello di** posta elettronica riutilizzabile: dopo aver creato e salvato il modello di posta elettronica, è possibile usarlo di nuovo nelle future campagne di phishing di phishing.</span><span class="sxs-lookup"><span data-stu-id="0d896-144">**Create a reusable email template**: After you create and save the email template, you can use it again in future spear phishing campaigns.</span></span> <span data-ttu-id="0d896-145">Puoi personalizzare ulteriormente alcune, tutte o nessuna delle proprietà di posta elettronica del modello quando crei e avvii la campagna.</span><span class="sxs-lookup"><span data-stu-id="0d896-145">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="0d896-146">**Creare il messaggio di posta elettronica nella** procedura guidata: è possibile creare il messaggio di posta elettronica direttamente nella procedura guidata durante la creazione e l'avvio della campagna di phishing.</span><span class="sxs-lookup"><span data-stu-id="0d896-146">**Create the email message in the wizard**: You can create the email message directly in the wizard as you create and launch the spear phishing campaign.</span></span>

#### <a name="step-1-optional-create-a-custom-email-template"></a><span data-ttu-id="0d896-147">Passaggio 1 (facoltativo): Creare un modello di posta elettronica personalizzato</span><span class="sxs-lookup"><span data-stu-id="0d896-147">Step 1 (Optional): Create a custom email template</span></span>

<span data-ttu-id="0d896-148">Se si sta per utilizzare uno dei modelli predefiniti o creare il messaggio di posta elettronica direttamente nella procedura guidata, è possibile ignorare questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="0d896-148">If you're going to use one of the built-in templates or create the email message directly in the wizard, you can skip this step.</span></span>

1. <span data-ttu-id="0d896-149">Nel Centro sicurezza & conformità passare a Simulatore di **attacchi di gestione** delle \> **minacce.**</span><span class="sxs-lookup"><span data-stu-id="0d896-149">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="0d896-150">Nella pagina **Simulate attacks** fare clic su Attack **Details** nelle sezioni Spear **Phishing (Credentials Harvest)** o **Spear Phishing (Attachment).**</span><span class="sxs-lookup"><span data-stu-id="0d896-150">On the **Simulate attacks** page, in either the **Spear Phishing (Credentials Harvest)** or **Spear Phishing (Attachment)** sections, click **Attack Details**.</span></span>

   <span data-ttu-id="0d896-151">Non importa dove si crea il modello.</span><span class="sxs-lookup"><span data-stu-id="0d896-151">It doesn't matter where you create the template.</span></span> <span data-ttu-id="0d896-152">Le opzioni disponibili nel modello sono le stesse per entrambi i tipi di attacchi di phishing.</span><span class="sxs-lookup"><span data-stu-id="0d896-152">The available options in the template are the same for both types of phishing attacks.</span></span>

3. <span data-ttu-id="0d896-153">Nella pagina **Dettagli attacco** visualizzata, nell'area Crea  modelli della sezione Modelli di **phishing** fare clic su **Nuovo modello.**</span><span class="sxs-lookup"><span data-stu-id="0d896-153">In the **Attack details** page that opens, in the **Phishing Templates** section, in the **Create Templates** area, click **New Template**.</span></span>

4. <span data-ttu-id="0d896-154">La **procedura guidata Configura modello di** phishing viene avviata in un nuovo riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="0d896-154">The **Configure Phishing Template** wizard starts in a new flyout.</span></span> <span data-ttu-id="0d896-155">Nel passaggio **iniziale** immettere un nome visualizzato univoco per il modello e quindi fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="0d896-155">In the **Start** step, enter a unique display name for the template, and then click **Next**.</span></span>

5. <span data-ttu-id="0d896-156">Nel passaggio **Configura dettagli posta elettronica** configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0d896-156">In the **Configure email details** step, configure the following settings:</span></span>

   - <span data-ttu-id="0d896-157">**From (Nome):** nome visualizzato utilizzato per il mittente del messaggio.</span><span class="sxs-lookup"><span data-stu-id="0d896-157">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="0d896-158">**Da (Posta elettronica):** indirizzo di posta elettronica del mittente.</span><span class="sxs-lookup"><span data-stu-id="0d896-158">**From (Email)**: The sender's email address.</span></span>

   - <span data-ttu-id="0d896-159">**URL del server di accesso** phishing: fare clic sull'elenco a discesa e selezionare uno degli URL disponibili nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="0d896-159">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="0d896-160">Questo è l'URL su cui gli utenti saranno tentati di fare clic.</span><span class="sxs-lookup"><span data-stu-id="0d896-160">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="0d896-161">Le opzioni disponibili sono:</span><span class="sxs-lookup"><span data-stu-id="0d896-161">The choices are:</span></span>

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
     > <span data-ttu-id="0d896-162">Un servizio di reputazione URL può identificare uno o più url come non sicuri.</span><span class="sxs-lookup"><span data-stu-id="0d896-162">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="0d896-163">Verificare la disponibilità dell'URL nei Web browser supportati prima di utilizzarlo in una campagna di phishing.</span><span class="sxs-lookup"><span data-stu-id="0d896-163">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span>

   - <span data-ttu-id="0d896-164">**URL pagina di destinazione personalizzata:** immettere una pagina di destinazione facoltativa in cui gli utenti vengono presi se fanno clic sul collegamento di phishing e immettono le proprie credenziali.</span><span class="sxs-lookup"><span data-stu-id="0d896-164">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="0d896-165">Questo collegamento sostituisce la pagina di destinazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="0d896-165">This link replaces the default landing page.</span></span> <span data-ttu-id="0d896-166">Ad esempio, se hai una formazione di sensibilizzazione interna, puoi specificare questo URL qui.</span><span class="sxs-lookup"><span data-stu-id="0d896-166">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="0d896-167">**Categoria:** attualmente questa impostazione non viene utilizzata (tutto ciò che immetti viene ignorato).</span><span class="sxs-lookup"><span data-stu-id="0d896-167">**Category**: Currently, this setting isn't used (anything you enter is ignored).</span></span>

   - <span data-ttu-id="0d896-168">**Oggetto:** campo **Oggetto** del messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="0d896-168">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="0d896-169">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="0d896-169">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="0d896-170">Nel passaggio **Scrivi messaggio di posta** elettronica, creare il corpo del messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="0d896-170">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="0d896-171">È possibile utilizzare la **scheda Posta** elettronica (un editor HTML avanzato) o la scheda **Origine** (codice HTML non elaborato).</span><span class="sxs-lookup"><span data-stu-id="0d896-171">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="0d896-172">La formattazione HTML può essere semplice o complessa come necessario.</span><span class="sxs-lookup"><span data-stu-id="0d896-172">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="0d896-173">È possibile inserire immagini e testo per migliorare la credibilità del messaggio nel client di posta elettronica del destinatario.</span><span class="sxs-lookup"><span data-stu-id="0d896-173">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="0d896-174">`${username}` inserisce il nome del destinatario.</span><span class="sxs-lookup"><span data-stu-id="0d896-174">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="0d896-175">`${loginserverurl}` inserisce il valore **URL del server** di accesso phishing del passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="0d896-175">`${loginserverurl}` inserts the **Phishing Login Server URL** value from the previous step.</span></span>

   <span data-ttu-id="0d896-176">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="0d896-176">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="0d896-177">Nel passaggio **Conferma** fare clic su **Fine.**</span><span class="sxs-lookup"><span data-stu-id="0d896-177">In the **Confirm** step, click **Finish**.</span></span>

#### <a name="step-2-create-and-launch-the-spear-phishing-campaign"></a><span data-ttu-id="0d896-178">Passaggio 2: creare e avviare la campagna di phishing con phishing</span><span class="sxs-lookup"><span data-stu-id="0d896-178">Step 2: Create and launch the spear phishing campaign</span></span>

1. <span data-ttu-id="0d896-179">Nel Centro sicurezza & conformità passare a Simulatore di **attacchi di gestione** delle \> **minacce.**</span><span class="sxs-lookup"><span data-stu-id="0d896-179">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="0d896-180">Nella pagina **Simula attacchi** effettuare una delle seguenti selezioni in base al tipo di campagna che si desidera creare:</span><span class="sxs-lookup"><span data-stu-id="0d896-180">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="0d896-181">Nella sezione **Spear Phishing (Credentials Harvest)** fare clic su **Launch Attack** o su **Attack Details** \> **Launch Attack.**</span><span class="sxs-lookup"><span data-stu-id="0d896-181">In the **Spear Phishing (Credentials Harvest)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="0d896-182">Nella sezione **Spear Phishing (allegato),** fare clic su **Launch Attack** o su **Attack Details** \> **Launch Attack.**</span><span class="sxs-lookup"><span data-stu-id="0d896-182">In the **Spear Phishing (Attachment)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="0d896-183">La **procedura guidata Configura attacco di phishing** viene avviata in un nuovo riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="0d896-183">The **Configure Phishing Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="0d896-184">Nel passaggio **Start** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0d896-184">In the **Start** step, do one of the following steps:</span></span>

   - <span data-ttu-id="0d896-185">Nella casella **Nome** immettere un nome visualizzato univoco per la campagna.</span><span class="sxs-lookup"><span data-stu-id="0d896-185">In the **Name** box, enter a unique display name for the campaign.</span></span> <span data-ttu-id="0d896-186">Non fare clic su **Usa modello** perché il messaggio di posta elettronica verrà creato più avanti nella procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="0d896-186">Don't click **Use Template**, because you'll create the email message later in the wizard.</span></span>

   - <span data-ttu-id="0d896-187">Fare **clic su Usa** modello e selezionare un modello di posta elettronica predefinito o personalizzato.</span><span class="sxs-lookup"><span data-stu-id="0d896-187">Click **Use Template** and select a built-in or custom email template.</span></span> <span data-ttu-id="0d896-188">Dopo aver selezionato il modello, la **casella Nome** viene compilata automaticamente in base al modello, ma è possibile modificare il nome.</span><span class="sxs-lookup"><span data-stu-id="0d896-188">After you select the template, the **Name** box is automatically filled based on the template, but you can change the name.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="0d896-189">![Pagina iniziale phishing](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)</span><span class="sxs-lookup"><span data-stu-id="0d896-189">![Phishing Start Page](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)</span></span>

   <span data-ttu-id="0d896-190">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="0d896-190">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="0d896-191">Nel passaggio **Destinatari di** destinazione eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0d896-191">In the **Target recipients** step, do one of the following steps:</span></span>

   - <span data-ttu-id="0d896-192">Fare **clic su Rubrica** per selezionare i destinatari (utenti o gruppi) per la campagna.</span><span class="sxs-lookup"><span data-stu-id="0d896-192">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="0d896-193">Ogni destinatario di destinazione deve disporre di una cassetta postale di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="0d896-193">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="0d896-194">Se si fa **clic su Filtro** e **Applica** senza immettere un criterio di ricerca, tutti i destinatari vengono restituiti e aggiunti alla campagna.</span><span class="sxs-lookup"><span data-stu-id="0d896-194">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="0d896-195">Fare **clic su** Importa e quindi **importa** file per importare un valore con valori delimitati da virgole (CSV) o un file di indirizzi di posta elettronica separati da riga.</span><span class="sxs-lookup"><span data-stu-id="0d896-195">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="0d896-196">Ogni riga deve contenere l'indirizzo di posta elettronica del destinatario.</span><span class="sxs-lookup"><span data-stu-id="0d896-196">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="0d896-197">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="0d896-197">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="0d896-198">Nel passaggio **Configura dettagli posta elettronica** configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0d896-198">In the **Configure email details** step, configure the following settings:</span></span>

   <span data-ttu-id="0d896-199">Se è stato selezionato un modello nel **passaggio Start,** la maggior parte di questi valori è già configurata, ma è possibile modificarli.</span><span class="sxs-lookup"><span data-stu-id="0d896-199">If you selected a template in the **Start** step, most of these values are already configured, but you can change them.</span></span>

   - <span data-ttu-id="0d896-200">**From (Nome):** nome visualizzato utilizzato per il mittente del messaggio.</span><span class="sxs-lookup"><span data-stu-id="0d896-200">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="0d896-201">**Da (Posta elettronica):** indirizzo di posta elettronica del mittente.</span><span class="sxs-lookup"><span data-stu-id="0d896-201">**From (Email)**: The sender's email address.</span></span> <span data-ttu-id="0d896-202">È possibile immettere un indirizzo di posta elettronica reale o falso dal dominio di posta elettronica dell'organizzazione oppure un indirizzo di posta elettronica esterno reale o falso.</span><span class="sxs-lookup"><span data-stu-id="0d896-202">You can enter a real or fake email address from your organization's email domain, or you can enter a real or fake external email address.</span></span> <span data-ttu-id="0d896-203">Un indirizzo di posta elettronica del mittente valido dell'organizzazione verrà effettivamente risolto nel client di posta elettronica del destinatario.</span><span class="sxs-lookup"><span data-stu-id="0d896-203">A valid sender email address from your organization will actually resolve in the recipient's email client.</span></span>

   - <span data-ttu-id="0d896-204">**URL del server di accesso** phishing: fare clic sull'elenco a discesa e selezionare uno degli URL disponibili nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="0d896-204">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="0d896-205">Questo è l'URL su cui gli utenti saranno tentati di fare clic.</span><span class="sxs-lookup"><span data-stu-id="0d896-205">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="0d896-206">Le opzioni disponibili sono:</span><span class="sxs-lookup"><span data-stu-id="0d896-206">The choices are:</span></span>

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
     > - <span data-ttu-id="0d896-207">Tutti gli URL sono intenzionalmente http, non https.</span><span class="sxs-lookup"><span data-stu-id="0d896-207">All of the URLs are intentionally http, not https.</span></span>
     >
     > - <span data-ttu-id="0d896-208">Un servizio di reputazione URL può identificare uno o più url come non sicuri.</span><span class="sxs-lookup"><span data-stu-id="0d896-208">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="0d896-209">Verificare la disponibilità dell'URL nei Web browser supportati prima di utilizzarlo in una campagna di phishing.</span><span class="sxs-lookup"><span data-stu-id="0d896-209">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span>
     >
     > - <span data-ttu-id="0d896-210">È necessario selezionare un URL.</span><span class="sxs-lookup"><span data-stu-id="0d896-210">You are required to select a URL.</span></span> <span data-ttu-id="0d896-211">Per **le campagne di phishing** (allegato), è possibile rimuovere il collegamento dal corpo del messaggio nel passaggio successivo (in caso contrario, il messaggio conterrà sia un **collegamento** che un allegato).</span><span class="sxs-lookup"><span data-stu-id="0d896-211">For **Spear Phishing (Attachment)** campaigns, you can remove the link from the body of the message in the next step (otherwise, the message will contain both a link **and** an attachment).</span></span>

   - <span data-ttu-id="0d896-212">**Tipo di allegato:** questa impostazione è disponibile solo nelle campagne **di phishing (allegato).**</span><span class="sxs-lookup"><span data-stu-id="0d896-212">**Attachment Type**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="0d896-213">Fare clic sull'elenco a discesa e selezionare **. DOCX** o **. PDF** dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="0d896-213">Click the drop down and select **.DOCX** or **.PDF** from the list.</span></span>

   - <span data-ttu-id="0d896-214">**Nome allegato:** questa impostazione è disponibile solo nelle campagne **di phishing (allegato).**</span><span class="sxs-lookup"><span data-stu-id="0d896-214">**Attachment Name**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="0d896-215">Immettere un nome di file per l'allegato .docx o .pdf.</span><span class="sxs-lookup"><span data-stu-id="0d896-215">Enter a filename for the .docx or .pdf attachment.</span></span>

   - <span data-ttu-id="0d896-216">**URL pagina di destinazione personalizzata:** immettere una pagina di destinazione facoltativa in cui gli utenti vengono presi se fanno clic sul collegamento di phishing e immettono le proprie credenziali.</span><span class="sxs-lookup"><span data-stu-id="0d896-216">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="0d896-217">Questo collegamento sostituisce la pagina di destinazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="0d896-217">This link replaces the default landing page.</span></span> <span data-ttu-id="0d896-218">Ad esempio, se hai una formazione di sensibilizzazione interna, puoi specificare questo URL qui.</span><span class="sxs-lookup"><span data-stu-id="0d896-218">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="0d896-219">**Oggetto:** campo **Oggetto** del messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="0d896-219">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="0d896-220">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="0d896-220">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="0d896-221">Nel passaggio **Scrivi messaggio di posta** elettronica, creare il corpo del messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="0d896-221">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="0d896-222">Se è stato selezionato un modello nel **passaggio Start,** il corpo del messaggio è già configurato, ma è possibile personalizzarlo.</span><span class="sxs-lookup"><span data-stu-id="0d896-222">If you selected a template in the **Start** step, the message body is already configured, but you can customize it.</span></span> <span data-ttu-id="0d896-223">È possibile utilizzare la **scheda Posta** elettronica (un editor HTML avanzato) o la scheda **Origine** (codice HTML non elaborato).</span><span class="sxs-lookup"><span data-stu-id="0d896-223">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="0d896-224">La formattazione HTML può essere semplice o complessa come necessario.</span><span class="sxs-lookup"><span data-stu-id="0d896-224">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="0d896-225">È possibile inserire immagini e testo per migliorare la credibilità del messaggio nel client di posta elettronica del destinatario.</span><span class="sxs-lookup"><span data-stu-id="0d896-225">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="0d896-226">`${username}` inserisce il nome del destinatario.</span><span class="sxs-lookup"><span data-stu-id="0d896-226">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="0d896-227">`${loginserverurl}`inserisce il valore **URL del server di accesso phishing.**</span><span class="sxs-lookup"><span data-stu-id="0d896-227">`${loginserverurl}` inserts the **Phishing Login Server URL** value.</span></span>

   <span data-ttu-id="0d896-228">Per le campagne di **spear phishing (allegato),** è necessario rimuovere il collegamento dal corpo  del messaggio (in caso contrario, il messaggio conterrà sia un collegamento che un allegato e i clic sul collegamento non vengono monitorati in una campagna allegato).</span><span class="sxs-lookup"><span data-stu-id="0d896-228">For **Spear Phishing (Attachment)** campaigns, you should remove the link from the body of the message (otherwise, the message will contain both a link **and** an attachment, and link clicks aren't tracked in an attachment campaign).</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="0d896-229">![Comporre il corpo del messaggio di posta elettronica](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)</span><span class="sxs-lookup"><span data-stu-id="0d896-229">![Compose Email Body](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)</span></span>

   <span data-ttu-id="0d896-230">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="0d896-230">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="0d896-231">Nel passaggio **Conferma** fare clic su **Fine** per avviare la campagna.</span><span class="sxs-lookup"><span data-stu-id="0d896-231">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="0d896-232">Il messaggio di phishing viene recapitato ai destinatari di destinazione.</span><span class="sxs-lookup"><span data-stu-id="0d896-232">The phishing message is delivered to the targeted recipients.</span></span>

## <a name="password-attack-campaigns"></a><span data-ttu-id="0d896-233">Campagne di attacco con password</span><span class="sxs-lookup"><span data-stu-id="0d896-233">Password attack campaigns</span></span>

<span data-ttu-id="0d896-234">Un *attacco con password* tenta di indovinare le password per gli account utente in un'organizzazione, in genere dopo che l'utente malintenzionato ha identificato uno o più account utente validi.</span><span class="sxs-lookup"><span data-stu-id="0d896-234">A *password attack* tries to guess passwords for user accounts in an organization, typically after the attacker has identified one or more valid user accounts.</span></span>

<span data-ttu-id="0d896-235">Nel simulatore di attacchi sono disponibili due diversi tipi di campagne di attacco con password per testare la complessità delle password degli utenti:</span><span class="sxs-lookup"><span data-stu-id="0d896-235">In Attack Simulator, two different types of password attack campaigns are available for you to test the complexity of your users' passwords:</span></span>

- <span data-ttu-id="0d896-236">**Brute force password (attacco** con dizionario):  un attacco di forza *bruta* o dizionario usa un file di dizionario di grandi dimensioni di password su un account utente con la volontà che una di esse funzioni (molte password su un account).</span><span class="sxs-lookup"><span data-stu-id="0d896-236">**Brute force password (dictionary attack)**: A *brute force* or *dictionary* attack uses a large dictionary file of passwords on a user account with the hope that one of them will work (many passwords against one account).</span></span> <span data-ttu-id="0d896-237">I blocchi delle password non corretti consentono di dissuadere gli attacchi di forza bruta alle password.</span><span class="sxs-lookup"><span data-stu-id="0d896-237">Incorrect password lock-outs help deter brute force password attacks.</span></span>

  <span data-ttu-id="0d896-238">Per l'attacco con dizionario, è possibile specificare una o più password da provare (immesse manualmente o in un file caricato) e specificare uno o più utenti.</span><span class="sxs-lookup"><span data-stu-id="0d896-238">For the dictionary attack, you can specify one or many passwords to try (manually entered or in an uploaded file), and you can specify one or many users.</span></span>

- <span data-ttu-id="0d896-239">**Attacco di tipo password spray:** un attacco *di tipo password spray* utilizza la stessa password considerata con attenzione rispetto a un elenco di account utente (una password contro molti account).</span><span class="sxs-lookup"><span data-stu-id="0d896-239">**Password spray attack**: A *password spray* attack uses the same carefully considered password against a list of user accounts (one password against many accounts).</span></span> <span data-ttu-id="0d896-240">Gli attacchi con password spray sono più difficili da rilevare rispetto agli attacchi di forza bruta delle password (la probabilità di successo aumenta quando un utente malintenzionato tenta una password su decine o centinaia di account senza il rischio di inciampare nel blocco errato della password dell'utente).</span><span class="sxs-lookup"><span data-stu-id="0d896-240">Password spray attacks are harder to detect than brute force password attacks (the probability of success increases when an attacker tries one password across dozens or hundreds of accounts without the risk of tripping the user's incorrect password lock-out).</span></span>

  <span data-ttu-id="0d896-241">Per l'attacco di tipo password spray, è possibile specificare una sola password da provare e uno o più utenti.</span><span class="sxs-lookup"><span data-stu-id="0d896-241">For the password spray attack, you can only specify one password to try, and you can specify one or many users.</span></span>

> [!NOTE]
> <span data-ttu-id="0d896-242">Gli attacchi alle password in Attack Simulator passano le richieste di autenticazione di base di nome utente e password a un endpoint, quindi funzionano anche con altri metodi di autenticazione (AD FS, sincronizzazione hash delle password, pass-through, PingFederate e così via).</span><span class="sxs-lookup"><span data-stu-id="0d896-242">The password attacks in Attack Simulator pass username and password Basic auth requests to an endpoint, so they also work with other authentication methods (AD FS, password hash sync, pass-through, PingFederate, etc.).</span></span> <span data-ttu-id="0d896-243">Per gli utenti che hanno abilitato l'autenticazione a più fattori, anche se l'attacco con password tenta la  password effettiva, il tentativo verrà sempre registrato come errore (in altre parole, gli utenti MFA non verranno mai visualizzati nel conteggio tentativi riusciti della campagna).</span><span class="sxs-lookup"><span data-stu-id="0d896-243">For users that have MFA enabled, even if the password attack tries their actual password, the attempt will always register as a failure (in other words, MFA users will never appear in the **Successful attempts** count of the campaign).</span></span> <span data-ttu-id="0d896-244">Questo è il risultato previsto.</span><span class="sxs-lookup"><span data-stu-id="0d896-244">This is the expected result.</span></span> <span data-ttu-id="0d896-245">L'autenticazione a più fattori è un metodo principale per proteggere gli attacchi alle password.</span><span class="sxs-lookup"><span data-stu-id="0d896-245">MFA is a primary method to help protect against password attacks.</span></span>

### <a name="create-and-launch-a-password-attack-campaign"></a><span data-ttu-id="0d896-246">Creare e avviare una campagna di attacco con password</span><span class="sxs-lookup"><span data-stu-id="0d896-246">Create and launch a password attack campaign</span></span>

1. <span data-ttu-id="0d896-247">Nel Centro sicurezza & conformità passare a Simulatore di **attacchi di gestione** delle \> **minacce.**</span><span class="sxs-lookup"><span data-stu-id="0d896-247">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="0d896-248">Nella pagina **Simula attacchi** effettuare una delle seguenti selezioni in base al tipo di campagna che si desidera creare:</span><span class="sxs-lookup"><span data-stu-id="0d896-248">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="0d896-249">Nella sezione **Brute Force Password (Dictionary Attack)** fai clic su **Launch Attack** o su **Attack Details** Launch \> **Attack.**</span><span class="sxs-lookup"><span data-stu-id="0d896-249">In the **Brute Force Password (Dictionary Attack)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="0d896-250">nella sezione **Attacco con password spray** fare clic su Launch **Attack** o su **Attack Details** \> **Launch Attack.**</span><span class="sxs-lookup"><span data-stu-id="0d896-250">in the **Password spray attack** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="0d896-251">La **procedura guidata Configura attacco** password viene avviata in un nuovo riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="0d896-251">The **Configure Password Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="0d896-252">Nel passaggio **iniziale** immettere un nome visualizzato univoco per la campagna e quindi fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="0d896-252">In the **Start** step, enter a unique display name for the campaign, and then click **Next**.</span></span>

4. <span data-ttu-id="0d896-253">Nel passaggio **Utenti di** destinazione eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0d896-253">In the **Target users** step, do one of the following steps:</span></span>

   - <span data-ttu-id="0d896-254">Fare **clic su Rubrica** per selezionare i destinatari (utenti o gruppi) per la campagna.</span><span class="sxs-lookup"><span data-stu-id="0d896-254">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="0d896-255">Ogni destinatario di destinazione deve disporre di una cassetta postale di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="0d896-255">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="0d896-256">Se si fa **clic su Filtro** e **Applica** senza immettere un criterio di ricerca, tutti i destinatari vengono restituiti e aggiunti alla campagna.</span><span class="sxs-lookup"><span data-stu-id="0d896-256">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="0d896-257">Fare **clic su** Importa e quindi **importa** file per importare un valore con valori delimitati da virgole (CSV) o un file di indirizzi di posta elettronica separati da riga.</span><span class="sxs-lookup"><span data-stu-id="0d896-257">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="0d896-258">Ogni riga deve contenere l'indirizzo di posta elettronica del destinatario.</span><span class="sxs-lookup"><span data-stu-id="0d896-258">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="0d896-259">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="0d896-259">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="0d896-260">Nel passaggio **Scegliere le impostazioni di attacco** scegliere cosa fare in base al tipo di campagna:</span><span class="sxs-lookup"><span data-stu-id="0d896-260">In the **Choose attack settings** step, choose what to do based on the campaign type:</span></span>

   - <span data-ttu-id="0d896-261">**Brute Force Password (Dictionary Attack):** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0d896-261">**Brute Force Password (Dictionary Attack)**: Do either of the following steps:</span></span>

     - <span data-ttu-id="0d896-262">**Immettere manualmente le password:** nella casella Premere INVIO per aggiungere una **password,** digitare una password e quindi premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="0d896-262">**Enter passwords manually**: In the **Press enter to add a password** box, type a password and then press ENTER.</span></span> <span data-ttu-id="0d896-263">Ripetere questo passaggio tutte le volte necessarie.</span><span class="sxs-lookup"><span data-stu-id="0d896-263">Repeat this step as many times as necessary.</span></span>

     - <span data-ttu-id="0d896-264">**Caricare le password da un file di dizionario:** fare clic su Carica per importare un file di testo esistente contenente una password per ogni riga e un'ultima riga vuota. </span><span class="sxs-lookup"><span data-stu-id="0d896-264">**Upload passwords from a dictionary file**: Click **Upload** to import an existing text file that contains one password on each line and a blank last line.</span></span> <span data-ttu-id="0d896-265">Le dimensioni del file di testo devono essere pari o inferiori a 10 MB e non possono contenere più di 30000 password.</span><span class="sxs-lookup"><span data-stu-id="0d896-265">The text file must be 10 MB or less in size, and can't contain more than 30000 passwords.</span></span>

   - <span data-ttu-id="0d896-266">**Attacco con password spray:** nelle **password da** usare nella casella di attacco, immettere una password.</span><span class="sxs-lookup"><span data-stu-id="0d896-266">**Password spray attack**: In **The password(s) to use in the attack** box, enter one password.</span></span>

   <span data-ttu-id="0d896-267">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="0d896-267">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="0d896-268">Nel passaggio **Conferma** fare clic su **Fine** per avviare la campagna.</span><span class="sxs-lookup"><span data-stu-id="0d896-268">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="0d896-269">Le password specificate vengono tentate per gli utenti specificati.</span><span class="sxs-lookup"><span data-stu-id="0d896-269">The passwords you specified are tried on users you specified.</span></span>

## <a name="view-campaign-results"></a><span data-ttu-id="0d896-270">Visualizzare i risultati della campagna</span><span class="sxs-lookup"><span data-stu-id="0d896-270">View campaign results</span></span>

<span data-ttu-id="0d896-271">Dopo aver avviato una campagna, puoi controllare l'avanzamento e i risultati nella pagina principale **Simula attacchi.**</span><span class="sxs-lookup"><span data-stu-id="0d896-271">After you launch a campaign, you can check the progress and results on the main **Simulate attacks** page.</span></span>

<span data-ttu-id="0d896-272">Le campagne attive mostreranno una barra di stato, un valore percentuale completato e il conteggio "(utenti completati) di (utenti totali)".</span><span class="sxs-lookup"><span data-stu-id="0d896-272">Active campaigns will show a status bar, a completed percentage value and "(completed users) of (total users)" count.</span></span> <span data-ttu-id="0d896-273">Facendo clic **sul** pulsante Aggiorna viene aggiornato lo stato di avanzamento delle campagne attive.</span><span class="sxs-lookup"><span data-stu-id="0d896-273">Clicking the **Refresh** button will update the progress of any active campaigns.</span></span> <span data-ttu-id="0d896-274">Puoi anche fare clic su **Termina** per interrompere una campagna attiva.</span><span class="sxs-lookup"><span data-stu-id="0d896-274">You can also click **Terminate** to stop an active campaign.</span></span>

<span data-ttu-id="0d896-275">Al termine della campagna, lo stato cambia in **Attacco completato.**</span><span class="sxs-lookup"><span data-stu-id="0d896-275">When the campaign is finished, the status changes to **Attack completed**.</span></span> <span data-ttu-id="0d896-276">Puoi visualizzare i risultati della campagna eseguendo una delle azioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="0d896-276">You can view the results of the campaign by doing either of the following actions:</span></span>

- <span data-ttu-id="0d896-277">Nella pagina principale **Simulate attacks** fai clic **su View Report** sotto il nome della campagna.</span><span class="sxs-lookup"><span data-stu-id="0d896-277">On the main **Simulate attacks** page, click **View Report** under the name of the campaign.</span></span>

- <span data-ttu-id="0d896-278">Nella pagina principale **Simulate attacks** fare clic **su Attack Details** nella sezione relativa al tipo di attacco.</span><span class="sxs-lookup"><span data-stu-id="0d896-278">On the main **Simulate attacks** page, click **Attack Details** in the section for the type of attack.</span></span> <span data-ttu-id="0d896-279">Nella pagina **dei dettagli dell'attacco** che si apre, selezionare la campagna nella sezione **Cronologia** attacchi.</span><span class="sxs-lookup"><span data-stu-id="0d896-279">On the **Attack details** page that opens, select the campaign in the **Attack History** section.</span></span>

<span data-ttu-id="0d896-280">Una delle azioni precedenti consente di accedere a una pagina denominata **Dettagli attacco.**</span><span class="sxs-lookup"><span data-stu-id="0d896-280">Either of the previous actions will take you to a page named **Attack details**.</span></span> <span data-ttu-id="0d896-281">Le informazioni disponibili in questa pagina per ogni tipo di campagna sono descritte nelle sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="0d896-281">The information that's available on this page for each type of campaign is described in the following sections.</span></span>

### <a name="spear-phishing-credentials-harvest-campaign-results"></a><span data-ttu-id="0d896-282">Risultati della campagna spear phishing (Credentials Harvest)</span><span class="sxs-lookup"><span data-stu-id="0d896-282">Spear Phishing (Credentials Harvest) campaign results</span></span>

<span data-ttu-id="0d896-283">Le informazioni seguenti sono disponibili nella pagina dei dettagli **dell'attacco** per ogni campagna:</span><span class="sxs-lookup"><span data-stu-id="0d896-283">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="0d896-284">Durata (data/ora di inizio e data/ora di fine) della campagna.</span><span class="sxs-lookup"><span data-stu-id="0d896-284">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="0d896-285">**Totale utenti a cui è stata destinata**</span><span class="sxs-lookup"><span data-stu-id="0d896-285">**Total users targeted**</span></span>

- <span data-ttu-id="0d896-286">**Tentativi riusciti:** numero di utenti che hanno fatto clic sul **collegamento** e immesso le proprie credenziali *(qualsiasi valore* di nome utente e password).</span><span class="sxs-lookup"><span data-stu-id="0d896-286">**Successful attempts**: The number of users who clicked the link **and** entered their credentials (*any* username and password value).</span></span>

- <span data-ttu-id="0d896-287">**Tasso di successo complessivo**: percentuale calcolata dal numero totale di tentativi **riusciti**  /  **mirati.**</span><span class="sxs-lookup"><span data-stu-id="0d896-287">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="0d896-288">**Clic più rapido:** tempo impiegato dal primo utente per fare clic sul collegamento dopo l'avvio della campagna.</span><span class="sxs-lookup"><span data-stu-id="0d896-288">**Fastest Click**: How long it took the first user to click the link after you launched the campaign.</span></span>

- <span data-ttu-id="0d896-289">**Media clic**: somma del tempo impiegato da tutti gli utenti per fare clic sul collegamento diviso per il numero di utenti che hanno fatto clic sul collegamento.</span><span class="sxs-lookup"><span data-stu-id="0d896-289">**Average Click**: The sum of how long it took everyone to click the link divided by the number of users who clicked the link.</span></span>

- <span data-ttu-id="0d896-290">**Click Success Rate**: percentuale calcolata da (numero di utenti che hanno fatto clic sul collegamento) / **Totale utenti mirati.**</span><span class="sxs-lookup"><span data-stu-id="0d896-290">**Click Success Rate**: A percentage that's calculated by (number of users who clicked the link) / **Total users targeted**.</span></span>

- <span data-ttu-id="0d896-291">**Credenziali più veloci:** tempo impiegato dal primo utente per immettere le credenziali dopo l'avvio della campagna.</span><span class="sxs-lookup"><span data-stu-id="0d896-291">**Fastest Credentials**: How long it took the first user to enter their credentials after you launched the campaign.</span></span>

- <span data-ttu-id="0d896-292">**Credenziali medie**: somma del tempo impiegato da tutti per immettere le credenziali diviso per il numero di utenti che hanno immesso le credenziali.</span><span class="sxs-lookup"><span data-stu-id="0d896-292">**Average Credentials**: The sum of how long it took everyone to enter their credentials divided by the number of users who entered their credentials.</span></span>

- <span data-ttu-id="0d896-293">**Percentuale di successo delle** credenziali : percentuale calcolata da (numero di utenti che hanno immesso le credenziali) / **Totale utenti di destinazione.**</span><span class="sxs-lookup"><span data-stu-id="0d896-293">**Credential Success Rate**: A percentage that's calculated by (number of users who entered their credentials) / **Total users targeted**.</span></span>

- <span data-ttu-id="0d896-294">Grafico a barre che mostra i **numeri di collegamento** su cui è stato fatto clic e i numeri forniti per le **credenziali** al giorno.</span><span class="sxs-lookup"><span data-stu-id="0d896-294">A bar graph that shows the **Link clicked** and **Credential supplied** numbers per day.</span></span>

- <span data-ttu-id="0d896-295">Grafico a cerchi che mostra le **percentuali di** clic **sul** collegamento, credenziali fornite e **nessuna** per la campagna.</span><span class="sxs-lookup"><span data-stu-id="0d896-295">A circle graph that shows the **Link clicked**, **Credential supplied**, and **None** percentages for the campaign.</span></span>

- <span data-ttu-id="0d896-296">Nella **sezione Utenti compromessi** sono elencati i dettagli degli utenti che hanno fatto clic sul collegamento:</span><span class="sxs-lookup"><span data-stu-id="0d896-296">The **Compromised Users** section lists the details of the users who clicked the link:</span></span>

  - <span data-ttu-id="0d896-297">L'indirizzo di posta elettronica dell'utente</span><span class="sxs-lookup"><span data-stu-id="0d896-297">The user's email address</span></span>

  - <span data-ttu-id="0d896-298">Data/ora in cui hanno fatto clic sul collegamento.</span><span class="sxs-lookup"><span data-stu-id="0d896-298">The date/time when they clicked the link.</span></span>

  - <span data-ttu-id="0d896-299">L'indirizzo IP del client.</span><span class="sxs-lookup"><span data-stu-id="0d896-299">The client IP address.</span></span>

  - <span data-ttu-id="0d896-300">Dettagli sulla versione di Windows e web browser dell'utente.</span><span class="sxs-lookup"><span data-stu-id="0d896-300">Details about the user's version of Windows and web browser.</span></span>

  <span data-ttu-id="0d896-301">È possibile fare **clic su Esporta** per esportare i risultati in un file CSV.</span><span class="sxs-lookup"><span data-stu-id="0d896-301">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="spear-phishing-attachment-campaign-results"></a><span data-ttu-id="0d896-302">Risultati della campagna di phishing (allegato)</span><span class="sxs-lookup"><span data-stu-id="0d896-302">Spear Phishing (Attachment) campaign results</span></span>

<span data-ttu-id="0d896-303">Le informazioni seguenti sono disponibili nella pagina dei dettagli **dell'attacco** per ogni campagna:</span><span class="sxs-lookup"><span data-stu-id="0d896-303">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="0d896-304">Durata (data/ora di inizio e data/ora di fine) della campagna.</span><span class="sxs-lookup"><span data-stu-id="0d896-304">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="0d896-305">**Totale utenti a cui è stata destinata**</span><span class="sxs-lookup"><span data-stu-id="0d896-305">**Total users targeted**</span></span>

- <span data-ttu-id="0d896-306">**Tentativi riusciti**: numero di utenti che hanno aperto o scaricato e aperto l'allegato (l'anteprima non viene conteggiato).</span><span class="sxs-lookup"><span data-stu-id="0d896-306">**Successful attempts**: The number of users who opened or downloaded and opened the attachment (preview doesn't count).</span></span>

- <span data-ttu-id="0d896-307">**Tasso di successo complessivo**: percentuale calcolata dal numero totale di tentativi **riusciti**  /  **mirati.**</span><span class="sxs-lookup"><span data-stu-id="0d896-307">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="0d896-308">**Tempo di apertura dell'allegato** più rapido: tempo impiegato dal primo utente per aprire l'allegato dopo l'avvio della campagna.</span><span class="sxs-lookup"><span data-stu-id="0d896-308">**Fastest attachment open time**: How long it took the first user to open the attachment after you launched the campaign.</span></span>

- <span data-ttu-id="0d896-309">**Tempo medio di apertura** dell'allegato: somma del tempo impiegato da tutti gli utenti per aprire l'allegato diviso per il numero di utenti che hanno aperto l'allegato.</span><span class="sxs-lookup"><span data-stu-id="0d896-309">**Average attachment open time**: The sum of how long it took everyone to open the attachment divided by the number of users who opened the attachment.</span></span>

- <span data-ttu-id="0d896-310">**Percentuale di successo apertura** allegato : percentuale calcolata da (numero di utenti che hanno aperto l'allegato) / **Totale utenti destinatari.**</span><span class="sxs-lookup"><span data-stu-id="0d896-310">**Attachment open success rate**: A percentage that's calculated by (number of users who opened the attachment) / **Total users targeted**.</span></span>

### <a name="brute-force-password-dictionary-attack-campaign-results"></a><span data-ttu-id="0d896-311">Risultati della campagna Brute Force Password (attacco con dizionario)</span><span class="sxs-lookup"><span data-stu-id="0d896-311">Brute Force Password (Dictionary Attack) campaign results</span></span>

<span data-ttu-id="0d896-312">Le informazioni seguenti sono disponibili nella pagina dei dettagli **dell'attacco** per ogni campagna:</span><span class="sxs-lookup"><span data-stu-id="0d896-312">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="0d896-313">Durata (data/ora di inizio e data/ora di fine) della campagna.</span><span class="sxs-lookup"><span data-stu-id="0d896-313">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="0d896-314">**Totale utenti a cui è stata destinata**</span><span class="sxs-lookup"><span data-stu-id="0d896-314">**Total users targeted**</span></span>

- <span data-ttu-id="0d896-315">**Tentativi** riusciti: numero di utenti che hanno rilevato l'utilizzo di una delle password specificate.</span><span class="sxs-lookup"><span data-stu-id="0d896-315">**Successful attempts**: The number of users who were found to be using one of the specified passwords.</span></span>

- <span data-ttu-id="0d896-316">**Tasso di successo complessivo**: percentuale calcolata dal numero totale di tentativi **riusciti**  /  **mirati.**</span><span class="sxs-lookup"><span data-stu-id="0d896-316">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="0d896-317">Nella **sezione Utenti compromessi** sono elencati gli indirizzi di posta elettronica degli utenti interessati.</span><span class="sxs-lookup"><span data-stu-id="0d896-317">The **Compromised Users** section lists the email addresses of the affected users.</span></span> <span data-ttu-id="0d896-318">È possibile fare **clic su Esporta** per esportare i risultati in un file CSV.</span><span class="sxs-lookup"><span data-stu-id="0d896-318">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="password-spray-attack-campaign-results"></a><span data-ttu-id="0d896-319">Risultati della campagna di attacco con password spray</span><span class="sxs-lookup"><span data-stu-id="0d896-319">Password spray attack campaign results</span></span>

<span data-ttu-id="0d896-320">Le informazioni seguenti sono disponibili nella pagina dei dettagli **dell'attacco** per ogni campagna:</span><span class="sxs-lookup"><span data-stu-id="0d896-320">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="0d896-321">Durata (data/ora di inizio e data/ora di fine) della campagna.</span><span class="sxs-lookup"><span data-stu-id="0d896-321">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="0d896-322">**Totale utenti a cui è stata destinata**</span><span class="sxs-lookup"><span data-stu-id="0d896-322">**Total users targeted**</span></span>

- <span data-ttu-id="0d896-323">**Tentativi riusciti**: numero di utenti che hanno rilevato l'utilizzo della password specificata.</span><span class="sxs-lookup"><span data-stu-id="0d896-323">**Successful attempts**: The number of users who were found to be using the specified password.</span></span>

- <span data-ttu-id="0d896-324">**Tasso di successo complessivo**: percentuale calcolata dal numero totale di tentativi **riusciti**  /  **mirati.**</span><span class="sxs-lookup"><span data-stu-id="0d896-324">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>
