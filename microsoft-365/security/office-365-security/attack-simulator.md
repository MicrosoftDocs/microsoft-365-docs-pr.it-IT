---
title: Simulatore di attacco in ATP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: da5845db-c578-4a41-b2cb-5a09689a551b
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Gli amministratori possono imparare a usare Attack Simulator per eseguire attacchi simulati di phishing e password nelle organizzazioni di Microsoft 365 E5 o ATP Plan 2.
ms.openlocfilehash: 017376d8002811398fe3ce2d94f7c207cd718a78
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/20/2020
ms.locfileid: "46825834"
---
# <a name="attack-simulator-in-atp"></a><span data-ttu-id="b935b-103">Simulatore di attacco in ATP</span><span class="sxs-lookup"><span data-stu-id="b935b-103">Attack Simulator in ATP</span></span>

<span data-ttu-id="b935b-104">Se l'organizzazione dispone di Office 365 Advanced Threat Protection (ATP) piano 2, che include le [funzionalità di ricerca e di risposta alle minacce](office-365-ti.md), è possibile utilizzare Attack Simulator nel centro sicurezza & Compliance per eseguire scenari di attacco realistici nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b935b-104">If your organization has Office 365 Advanced Threat Protection (ATP) Plan 2, which includes [Threat Investigation and Response capabilities](office-365-ti.md), you can use Attack Simulator in the Security & Compliance Center to run realistic attack scenarios in your organization.</span></span> <span data-ttu-id="b935b-105">Questi attacchi simulati consentono di identificare e individuare gli utenti vulnerabili prima che un attacco reale impatti la linea di base.</span><span class="sxs-lookup"><span data-stu-id="b935b-105">These simulated attacks can help you identify and find vulnerable users before a real attack impacts your bottom line.</span></span> <span data-ttu-id="b935b-106">Leggere questo articolo per ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="b935b-106">Read this article to learn more.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="b935b-107">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="b935b-107">What do you need to know before you begin?</span></span>

- <span data-ttu-id="b935b-108">Per aprire il Centro sicurezza e conformità, passare a <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="b935b-108">To open the Security & Compliance Center, go to <https://protection.office.com/>.</span></span> <span data-ttu-id="b935b-109">Simulatore di attacco è disponibile in **Threat Management** \> **Attack Simulator**.</span><span class="sxs-lookup"><span data-stu-id="b935b-109">Attack simulator is available at **Threat management** \> **Attack simulator**.</span></span> <span data-ttu-id="b935b-110">Andare direttamente a attacco simulatore, aprire <https://protection.office.com/attacksimulator> .</span><span class="sxs-lookup"><span data-stu-id="b935b-110">Go go directly to attack simulator, open <https://protection.office.com/attacksimulator>.</span></span>

- <span data-ttu-id="b935b-111">Per ulteriori informazioni sulla disponibilità di simulatori di attacco in diverse sottoscrizioni di Microsoft 365, vedere [Descrizione del servizio Advanced Threat Protection di Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span><span class="sxs-lookup"><span data-stu-id="b935b-111">For more information about the availability of Attack Simulator across different Microsoft 365 subscriptions, see [Office 365 Advanced Threat Protection service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

- <span data-ttu-id="b935b-112">È necessario essere membri dei gruppi di ruoli **Gestione organizzazione** o **amministratore sicurezza** .</span><span class="sxs-lookup"><span data-stu-id="b935b-112">You need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="b935b-113">Per altre informazioni sui gruppi di ruoli nel Centro sicurezza e conformità, vedere [Autorizzazioni nel Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="b935b-113">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="b935b-114">L'account deve essere configurato per l'autenticazione a più fattori (AMF) per creare e gestire le campagne in Attack Simulator.</span><span class="sxs-lookup"><span data-stu-id="b935b-114">Your account needs to be configured for multi-factor authentication (MFA) to create and manage campaigns in Attack Simulator.</span></span> <span data-ttu-id="b935b-115">Per istruzioni, vedere [configurare l'autenticazione](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication)a più fattori.</span><span class="sxs-lookup"><span data-stu-id="b935b-115">For instructions, see [Set up multi-factor authentication](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication).</span></span>

- <span data-ttu-id="b935b-116">Le campagne di phishing raccolgono ed elaborano gli eventi per 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="b935b-116">Phishing campaigns will collect and process events for 30 days.</span></span> <span data-ttu-id="b935b-117">I dati della campagna cronologica saranno disponibili fino a 90 giorni dopo l'avvio della campagna.</span><span class="sxs-lookup"><span data-stu-id="b935b-117">Historical campaign data will be available for up to 90 days after you launch the campaign.</span></span>

- <span data-ttu-id="b935b-118">Non sono disponibili i cmdlet di PowerShell corrispondenti per il simulatore di attacco.</span><span class="sxs-lookup"><span data-stu-id="b935b-118">There are no corresponding PowerShell cmdlets for Attack Simulator.</span></span>

## <a name="spear-phishing-campaigns"></a><span data-ttu-id="b935b-119">Campagne di phishing Spear</span><span class="sxs-lookup"><span data-stu-id="b935b-119">Spear phishing campaigns</span></span>

<span data-ttu-id="b935b-120">Il *phishing* è un termine generico per gli attacchi di posta elettronica che tentano di rubare informazioni sensibili nei messaggi che sembrano provenire da mittenti legittimi o attendibili.</span><span class="sxs-lookup"><span data-stu-id="b935b-120">*Phishing* is a generic term for email attacks that try to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="b935b-121">*Spear phishing* è un attacco di phishing mirato che utilizza contenuti mirati e personalizzati appositamente personalizzati per i destinatari mirati (in genere, dopo la ricognizione dei destinatari da parte dell'utente malintenzionato).</span><span class="sxs-lookup"><span data-stu-id="b935b-121">*Spear phishing* is a targeted phishing attack that uses focused and customized content that's specifically tailored to the targeted recipients (typically, after reconnaissance on the recipients by the attacker).</span></span>

<span data-ttu-id="b935b-122">In Attack Simulator sono disponibili due diversi tipi di campagne di phishing Spear:</span><span class="sxs-lookup"><span data-stu-id="b935b-122">In Attack Simulator, two different types of spear phishing campaigns are available:</span></span>

- <span data-ttu-id="b935b-123">**Spear phishing (Harvest Credentials)**: l'attacco tenta di convincere i destinatari a fare clic su un URL nel messaggio.</span><span class="sxs-lookup"><span data-stu-id="b935b-123">**Spear phishing (credentials harvest)**: The attack tries to convince the recipients to click a URL in the message.</span></span> <span data-ttu-id="b935b-124">Se si fa clic sul collegamento, viene richiesto di immettere le proprie credenziali.</span><span class="sxs-lookup"><span data-stu-id="b935b-124">If they click the link, they're asked to enter their credentials.</span></span> <span data-ttu-id="b935b-125">In caso contrario, vengono eseguite in una delle posizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b935b-125">If they do, they're taken to one of the following locations:</span></span>

  - <span data-ttu-id="b935b-126">Una pagina predefinita che spiega che si tratta di un semplice test e fornisce suggerimenti per il riconoscimento dei messaggi di phishing.</span><span class="sxs-lookup"><span data-stu-id="b935b-126">A default page that explains that this was a just a test, and gives tips for recognizing phishing messages.</span></span>

    ![Cosa vedranno gli utenti se fanno clic sul collegamento di phishing e immettono le proprie credenziali](../../media/attack-simulator-phishing-result.png)

  - <span data-ttu-id="b935b-128">Una pagina personalizzata (URL) specificata.</span><span class="sxs-lookup"><span data-stu-id="b935b-128">A custom page (URL) that you specify.</span></span>

- <span data-ttu-id="b935b-129">**Spear phishing (Attachment)**: l'attacco tenta di convincere i destinatari ad aprire un allegato. docx o. pdf nel messaggio.</span><span class="sxs-lookup"><span data-stu-id="b935b-129">**Spear phishing (attachment)**: The attack tries to convince the recipients to open a .docx or .pdf attachment in the message.</span></span> <span data-ttu-id="b935b-130">L'allegato contiene lo stesso contenuto del collegamento di phishing predefinito, ma la prima frase inizia con " \<Display Name\> , si sta vedendo questo messaggio come un messaggio di posta elettronica recente è stato aperto...".</span><span class="sxs-lookup"><span data-stu-id="b935b-130">The attachment contains the same content from the default phishing link, but the first sentence starts with "\<Display Name\>, you are seeing this message as a recent email message you opened...".</span></span>

> [!NOTE]
> <span data-ttu-id="b935b-131">Attualmente, le campagne di phishing Spear in Attack Simulator non scadono.</span><span class="sxs-lookup"><span data-stu-id="b935b-131">Currently, spear phishing campaigns in Attack Simulator don't expire.</span></span>

### <a name="create-a-spear-phishing-campaign"></a><span data-ttu-id="b935b-132">Creare una campagna di phishing di Spear</span><span class="sxs-lookup"><span data-stu-id="b935b-132">Create a spear phishing campaign</span></span>

<span data-ttu-id="b935b-133">Una parte importante di qualsiasi campagna di phishing Spear è l'aspetto del messaggio di posta elettronica inviato ai destinatari mirati.</span><span class="sxs-lookup"><span data-stu-id="b935b-133">An important part of any spear phishing campaign is the look and feel of the email message that's sent to the targeted recipients.</span></span> <span data-ttu-id="b935b-134">Per creare e configurare il messaggio di posta elettronica, sono disponibili le seguenti opzioni:</span><span class="sxs-lookup"><span data-stu-id="b935b-134">To create and configure the email message, you have these options:</span></span>

- <span data-ttu-id="b935b-135">**Utilizzo di un modello di posta elettronica incorporato**: sono disponibili due modelli incorporati: **Giveaway Prize** and **Payroll Update**.</span><span class="sxs-lookup"><span data-stu-id="b935b-135">**Use a built-in email template**: Two built-in templates are available: **Prize Giveaway** and **Payroll Update**.</span></span> <span data-ttu-id="b935b-136">È possibile personalizzare ulteriormente alcune, tutte o nessuna delle proprietà di posta elettronica dal modello quando si crea e si avvia la campagna.</span><span class="sxs-lookup"><span data-stu-id="b935b-136">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="b935b-137">**Creare un modello di posta elettronica riutilizzabile**: dopo aver creato e salvato il modello di posta elettronica, è possibile utilizzarlo nuovamente nelle future campagne di phishing Spear.</span><span class="sxs-lookup"><span data-stu-id="b935b-137">**Create a reusable email template**: After you create and save the email template, you can use it again in future spear phishing campaigns.</span></span> <span data-ttu-id="b935b-138">È possibile personalizzare ulteriormente alcune, tutte o nessuna delle proprietà di posta elettronica dal modello quando si crea e si avvia la campagna.</span><span class="sxs-lookup"><span data-stu-id="b935b-138">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="b935b-139">**Creare il messaggio di posta elettronica nella procedura guidata**: è possibile creare il messaggio di posta elettronica direttamente nella procedura guidata quando si crea e si avvia la campagna di phishing Spear.</span><span class="sxs-lookup"><span data-stu-id="b935b-139">**Create the email message in the wizard**: You can create the email message directly in the wizard as you create and launch the spear phishing campaign.</span></span>

#### <a name="step-1-optional-create-a-custom-email-template"></a><span data-ttu-id="b935b-140">Passaggio 1 (facoltativo): creare un modello di posta elettronica personalizzato</span><span class="sxs-lookup"><span data-stu-id="b935b-140">Step 1 (Optional): Create a custom email template</span></span>

<span data-ttu-id="b935b-141">Se si intende utilizzare uno dei modelli incorporati o creare il messaggio di posta elettronica direttamente nella procedura guidata, è possibile ignorare questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="b935b-141">If you're going to use one of the built-in templates or create the email message directly in the wizard, you can skip this step.</span></span>

1. <span data-ttu-id="b935b-142">Nel centro sicurezza & conformità, accedere a **Threat Management** \> **Attack Simulator**.</span><span class="sxs-lookup"><span data-stu-id="b935b-142">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="b935b-143">Nella pagina **simula attacchi** , nella sezione **spear phishing (credentials Harvest)** o **spear phishing (Attachment)** , fare clic su **Attack Details**.</span><span class="sxs-lookup"><span data-stu-id="b935b-143">On the **Simulate attacks** page, in either the **Spear Phishing (Credentials Harvest)** or **Spear Phishing (Attachment)** sections, click **Attack Details**.</span></span>

   <span data-ttu-id="b935b-144">Non importa dove creare il modello.</span><span class="sxs-lookup"><span data-stu-id="b935b-144">It doesn't matter where you create the template.</span></span> <span data-ttu-id="b935b-145">Le opzioni disponibili nel modello sono uguali per entrambi i tipi di attacchi di phishing.</span><span class="sxs-lookup"><span data-stu-id="b935b-145">The available options in the template are the same for both types of phishing attacks.</span></span>

3. <span data-ttu-id="b935b-146">Nella pagina dei **Dettagli sull'attacco** visualizzata, nella sezione **modelli di phishing** , nell'area **Crea modelli** fare clic su **nuovo modello**.</span><span class="sxs-lookup"><span data-stu-id="b935b-146">In the **Attack details** page that opens, in the **Phishing Templates** section, in the **Create Templates** area, click **New Template**.</span></span>

4. <span data-ttu-id="b935b-147">La procedura guidata **Configura modello di phishing** viene avviata in un nuovo riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="b935b-147">The **Configure Phishing Template** wizard starts in a new flyout.</span></span> <span data-ttu-id="b935b-148">Nel passaggio **iniziale** , immettere un nome visualizzato univoco per il modello e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="b935b-148">In the **Start** step, enter a unique display name for the template, and then click **Next**.</span></span>

5. <span data-ttu-id="b935b-149">Nel passaggio **Configure email details** , configurare le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="b935b-149">In the **Configure email details** step, configure the following settings:</span></span>

   - <span data-ttu-id="b935b-150">**From (Name)**: il nome visualizzato utilizzato per il mittente del messaggio.</span><span class="sxs-lookup"><span data-stu-id="b935b-150">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="b935b-151">**From (posta elettronica)**: l'indirizzo di posta elettronica del mittente.</span><span class="sxs-lookup"><span data-stu-id="b935b-151">**From (Email)**: The sender's email address.</span></span>

   - <span data-ttu-id="b935b-152">**URL del server di accesso di phishing**: fare clic sul menu a discesa e selezionare uno degli URL disponibili nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="b935b-152">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="b935b-153">Questo è l'URL a cui gli utenti saranno tentati di fare clic.</span><span class="sxs-lookup"><span data-stu-id="b935b-153">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="b935b-154">Le opzioni disponibili sono:</span><span class="sxs-lookup"><span data-stu-id="b935b-154">The choices are:</span></span>

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
     > - <span data-ttu-id="b935b-155">Tutti gli URL sono intenzionalmente http, non HTTPS.</span><span class="sxs-lookup"><span data-stu-id="b935b-155">All of the URLs are intentionally http, not https.</span></span>
     >
     > - <span data-ttu-id="b935b-156">Un servizio di reputazione URL potrebbe identificare uno o più di questi URL come non sicuri.</span><span class="sxs-lookup"><span data-stu-id="b935b-156">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="b935b-157">Controllare la disponibilità dell'URL nei Web browser supportati prima di utilizzare l'URL in una campagna di phishing.</span><span class="sxs-lookup"><span data-stu-id="b935b-157">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span>

   - <span data-ttu-id="b935b-158">**URL della pagina di destinazione personalizzata**: immettere una pagina di destinazione facoltativa in cui gli utenti vengono eseguiti se fanno clic sul collegamento di phishing e immettono le proprie credenziali.</span><span class="sxs-lookup"><span data-stu-id="b935b-158">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="b935b-159">Questo collegamento sostituisce la pagina di destinazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="b935b-159">This link replaces the default landing page.</span></span> <span data-ttu-id="b935b-160">Ad esempio, se si dispone di un training di sensibilizzazione interno, è possibile specificare l'URL qui.</span><span class="sxs-lookup"><span data-stu-id="b935b-160">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="b935b-161">**Categoria**: attualmente, questa impostazione non viene utilizzata (qualsiasi elemento immesso viene ignorato).</span><span class="sxs-lookup"><span data-stu-id="b935b-161">**Category**: Currently, this setting isn't used (anything you enter is ignored).</span></span>

   - <span data-ttu-id="b935b-162">**Subject**: il campo **Subject** del messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="b935b-162">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="b935b-163">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="b935b-163">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="b935b-164">Nel passaggio di creazione della **posta elettronica** creare il corpo del messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="b935b-164">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="b935b-165">È possibile utilizzare la scheda **posta elettronica** (un editor HTML RTF) oppure la scheda **origine** (codice HTML non elaborato).</span><span class="sxs-lookup"><span data-stu-id="b935b-165">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="b935b-166">La formattazione HTML può essere semplice o complessa come è necessario.</span><span class="sxs-lookup"><span data-stu-id="b935b-166">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="b935b-167">È possibile inserire immagini e testo per migliorare la credibilità del messaggio nel client di posta elettronica del destinatario.</span><span class="sxs-lookup"><span data-stu-id="b935b-167">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="b935b-168">`${username}` inserisce il nome del destinatario.</span><span class="sxs-lookup"><span data-stu-id="b935b-168">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="b935b-169">`${loginserverurl}` inserisce il valore dell' **URL del server di accesso di phishing** dal passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="b935b-169">`${loginserverurl}` inserts the **Phishing Login Server URL** value from the previous step.</span></span>

   <span data-ttu-id="b935b-170">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="b935b-170">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="b935b-171">Nel passaggio **conferma** fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="b935b-171">In the **Confirm** step, click **Finish**.</span></span>

#### <a name="step-2-create-and-launch-the-spear-phishing-campaign"></a><span data-ttu-id="b935b-172">Passaggio 2: creare e avviare la campagna di phishing Spear</span><span class="sxs-lookup"><span data-stu-id="b935b-172">Step 2: Create and launch the spear phishing campaign</span></span>

1. <span data-ttu-id="b935b-173">Nel centro sicurezza & conformità, accedere a **Threat Management** \> **Attack Simulator**.</span><span class="sxs-lookup"><span data-stu-id="b935b-173">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="b935b-174">Nella pagina **simula attacchi** fare una delle selezioni seguenti in base al tipo di campagna che si desidera creare:</span><span class="sxs-lookup"><span data-stu-id="b935b-174">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="b935b-175">Nella sezione **spear phishing (raccolta credenziali)** fare clic su **Launch Attack** o fare clic su Attack **Details** \> **Launch Attack**.</span><span class="sxs-lookup"><span data-stu-id="b935b-175">In the **Spear Phishing (Credentials Harvest)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="b935b-176">Nella sezione **spear phishing (Attachment)** , fare clic su **Launch Attack** o fare clic su Attack **Details** \> **Launch Attack**.</span><span class="sxs-lookup"><span data-stu-id="b935b-176">In the **Spear Phishing (Attachment)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="b935b-177">La procedura guidata **Configura attacco di phishing** viene avviata in un nuovo riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="b935b-177">The **Configure Phishing Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="b935b-178">Nel passaggio **iniziale** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b935b-178">In the **Start** step, do one of the following steps:</span></span>

   - <span data-ttu-id="b935b-179">Nella casella **nome** immettere un nome visualizzato univoco per la campagna.</span><span class="sxs-lookup"><span data-stu-id="b935b-179">In the **Name** box, enter a unique display name for the campaign.</span></span> <span data-ttu-id="b935b-180">Non fare clic su **Usa modello**perché verrà creato il messaggio di posta elettronica in un secondo momento nella procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="b935b-180">Don't click **Use Template**, because you'll create the email message later in the wizard.</span></span>

   - <span data-ttu-id="b935b-181">Fare clic su **Usa modello** e selezionare un modello di posta elettronica incorporato o personalizzato.</span><span class="sxs-lookup"><span data-stu-id="b935b-181">Click **Use Template** and select a built-in or custom email template.</span></span> <span data-ttu-id="b935b-182">Dopo aver selezionato il modello, la casella **nome** viene riempita automaticamente in base al modello, ma è possibile modificarne il nome.</span><span class="sxs-lookup"><span data-stu-id="b935b-182">After you select the template, the **Name** box is automatically filled based on the template, but you can change the name.</span></span>

   ![Pagina iniziale di phishing](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)

   <span data-ttu-id="b935b-184">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="b935b-184">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="b935b-185">Nel passaggio **destinatari di destinazione** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b935b-185">In the **Target recipients** step, do one of the following steps:</span></span>

   - <span data-ttu-id="b935b-186">Fare **clic su Rubrica per** selezionare i destinatari (utenti o gruppi) per la campagna.</span><span class="sxs-lookup"><span data-stu-id="b935b-186">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="b935b-187">Ogni destinatario di destinazione deve disporre di una cassetta postale di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="b935b-187">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="b935b-188">Se si fa clic su **Filtra** e **applica** senza immettere un criterio di ricerca, tutti i destinatari vengono restituiti e aggiunti alla campagna.</span><span class="sxs-lookup"><span data-stu-id="b935b-188">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="b935b-189">Fare clic su **Importa** quindi **importazione file** per importare un valore separato da virgole (CSV) o un file di indirizzi di posta elettronica separato da una riga.</span><span class="sxs-lookup"><span data-stu-id="b935b-189">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="b935b-190">Ogni riga deve contenere l'indirizzo di posta elettronica del destinatario.</span><span class="sxs-lookup"><span data-stu-id="b935b-190">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="b935b-191">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="b935b-191">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="b935b-192">Nel passaggio **Configure email details** , configurare le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="b935b-192">In the **Configure email details** step, configure the following settings:</span></span>

   <span data-ttu-id="b935b-193">Se nel passaggio **iniziale** è stato selezionato un modello, la maggior parte di questi valori è già configurata, ma è possibile modificarli.</span><span class="sxs-lookup"><span data-stu-id="b935b-193">If you selected a template in the **Start** step, most of these values are already configured, but you can change them.</span></span>

   - <span data-ttu-id="b935b-194">**From (Name)**: il nome visualizzato utilizzato per il mittente del messaggio.</span><span class="sxs-lookup"><span data-stu-id="b935b-194">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="b935b-195">**From (posta elettronica)**: l'indirizzo di posta elettronica del mittente.</span><span class="sxs-lookup"><span data-stu-id="b935b-195">**From (Email)**: The sender's email address.</span></span> <span data-ttu-id="b935b-196">È possibile immettere un indirizzo di posta elettronica reale o fasullo dal dominio di posta elettronica dell'organizzazione oppure è possibile immettere un indirizzo di posta elettronica esterno reale o fasullo.</span><span class="sxs-lookup"><span data-stu-id="b935b-196">You can enter a real or fake email address from your organization's email domain, or you can enter a real or fake external email address.</span></span> <span data-ttu-id="b935b-197">Un indirizzo di posta elettronica del mittente valido dell'organizzazione verrà effettivamente risolto nel client di posta elettronica del destinatario.</span><span class="sxs-lookup"><span data-stu-id="b935b-197">A valid sender email address from your organization will actually resolve in the recipient's email client.</span></span>

   - <span data-ttu-id="b935b-198">**URL del server di accesso di phishing**: fare clic sul menu a discesa e selezionare uno degli URL disponibili nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="b935b-198">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="b935b-199">Questo è l'URL a cui gli utenti saranno tentati di fare clic.</span><span class="sxs-lookup"><span data-stu-id="b935b-199">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="b935b-200">Le opzioni disponibili sono:</span><span class="sxs-lookup"><span data-stu-id="b935b-200">The choices are:</span></span>

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
     > - <span data-ttu-id="b935b-201">Tutti gli URL sono intenzionalmente http, non HTTPS.</span><span class="sxs-lookup"><span data-stu-id="b935b-201">All of the URLs are intentionally http, not https.</span></span>
     >
     > - <span data-ttu-id="b935b-202">Un servizio di reputazione URL potrebbe identificare uno o più di questi URL come non sicuri.</span><span class="sxs-lookup"><span data-stu-id="b935b-202">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="b935b-203">Controllare la disponibilità dell'URL nei Web browser supportati prima di utilizzare l'URL in una campagna di phishing.</span><span class="sxs-lookup"><span data-stu-id="b935b-203">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span>
     >
     > - <span data-ttu-id="b935b-204">È necessario selezionare un URL.</span><span class="sxs-lookup"><span data-stu-id="b935b-204">You are required to select a URL.</span></span> <span data-ttu-id="b935b-205">Per le campagne di **phishing (Attachment)** , è possibile rimuovere il collegamento dal corpo del messaggio nel passaggio successivo (in caso contrario, il messaggio conterrà sia un collegamento **che** un allegato).</span><span class="sxs-lookup"><span data-stu-id="b935b-205">For **Spear Phishing (Attachment)** campaigns, you can remove the link from the body of the message in the next step (otherwise, the message will contain both a link **and** an attachment).</span></span>

   - <span data-ttu-id="b935b-206">**Tipo di allegato**: questa impostazione è disponibile solo nelle campagne di **phishing (allegato) di Spear** .</span><span class="sxs-lookup"><span data-stu-id="b935b-206">**Attachment Type**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="b935b-207">Fare clic sull'elenco a discesa e selezionare **. DOCX** o **. File PDF** dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="b935b-207">Click the drop down and select **.DOCX** or **.PDF** from the list.</span></span>

   - <span data-ttu-id="b935b-208">**Nome allegato**: questa impostazione è disponibile solo nelle campagne di **phishing (allegato) di Spear** .</span><span class="sxs-lookup"><span data-stu-id="b935b-208">**Attachment Name**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="b935b-209">Immettere un nome di file per l'allegato. docx o. pdf.</span><span class="sxs-lookup"><span data-stu-id="b935b-209">Enter a filename for the .docx or .pdf attachment.</span></span>

   - <span data-ttu-id="b935b-210">**URL della pagina di destinazione personalizzata**: immettere una pagina di destinazione facoltativa in cui gli utenti vengono eseguiti se fanno clic sul collegamento di phishing e immettono le proprie credenziali.</span><span class="sxs-lookup"><span data-stu-id="b935b-210">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="b935b-211">Questo collegamento sostituisce la pagina di destinazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="b935b-211">This link replaces the default landing page.</span></span> <span data-ttu-id="b935b-212">Ad esempio, se si dispone di un training di sensibilizzazione interno, è possibile specificare l'URL qui.</span><span class="sxs-lookup"><span data-stu-id="b935b-212">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="b935b-213">**Subject**: il campo **Subject** del messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="b935b-213">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="b935b-214">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="b935b-214">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="b935b-215">Nel passaggio di creazione della **posta elettronica** creare il corpo del messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="b935b-215">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="b935b-216">Se nel passaggio **iniziale** è stato selezionato un modello, il corpo del messaggio è già configurato, ma è possibile personalizzarlo.</span><span class="sxs-lookup"><span data-stu-id="b935b-216">If you selected a template in the **Start** step, the message body is already configured, but you can customize it.</span></span> <span data-ttu-id="b935b-217">È possibile utilizzare la scheda **posta elettronica** (un editor HTML RTF) oppure la scheda **origine** (codice HTML non elaborato).</span><span class="sxs-lookup"><span data-stu-id="b935b-217">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="b935b-218">La formattazione HTML può essere semplice o complessa come è necessario.</span><span class="sxs-lookup"><span data-stu-id="b935b-218">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="b935b-219">È possibile inserire immagini e testo per migliorare la credibilità del messaggio nel client di posta elettronica del destinatario.</span><span class="sxs-lookup"><span data-stu-id="b935b-219">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="b935b-220">`${username}` inserisce il nome del destinatario.</span><span class="sxs-lookup"><span data-stu-id="b935b-220">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="b935b-221">`${loginserverurl}` inserisce il valore dell' **URL del server di accesso di phishing** .</span><span class="sxs-lookup"><span data-stu-id="b935b-221">`${loginserverurl}` inserts the **Phishing Login Server URL** value.</span></span>

   <span data-ttu-id="b935b-222">Per le campagne di **phishing (allegato)** , è necessario rimuovere il collegamento dal corpo del messaggio (in caso contrario, il messaggio conterrà sia un collegamento **che** un allegato e i collegamenti non vengono registrati in una campagna di allegato).</span><span class="sxs-lookup"><span data-stu-id="b935b-222">For **Spear Phishing (Attachment)** campaigns, you should remove the link from the body of the message (otherwise, the message will contain both a link **and** an attachment, and link clicks aren't tracked in an attachment campaign).</span></span>

   ![Comporre il corpo della posta elettronica](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)

   <span data-ttu-id="b935b-224">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="b935b-224">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="b935b-225">Nel passaggio **conferma** fare clic su **fine** per avviare la campagna.</span><span class="sxs-lookup"><span data-stu-id="b935b-225">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="b935b-226">Il messaggio di phishing viene recapitato ai destinatari mirati.</span><span class="sxs-lookup"><span data-stu-id="b935b-226">The phishing message is delivered to the targeted recipients.</span></span>

## <a name="password-attack-campaigns"></a><span data-ttu-id="b935b-227">Campagne di attacco tramite password</span><span class="sxs-lookup"><span data-stu-id="b935b-227">Password attack campaigns</span></span>

<span data-ttu-id="b935b-228">Un *attacco* per la password cerca di indovinare le password per gli account utente di un'organizzazione, in genere dopo che l'utente malintenzionato ha identificato uno o più account validi.</span><span class="sxs-lookup"><span data-stu-id="b935b-228">A *password attack* tries to guess passwords for user accounts in an organization, typically after the attacker has identified one or more valid user accounts.</span></span>

<span data-ttu-id="b935b-229">In Attack Simulator, sono disponibili due diversi tipi di campagne di attacco per la password per testare la complessità delle password degli utenti:</span><span class="sxs-lookup"><span data-stu-id="b935b-229">In Attack Simulator, two different types of password attack campaigns are available for you to test the complexity of your users' passwords:</span></span>

- <span data-ttu-id="b935b-230">**Password forza bruta (attacco dizionario)**: una *forza bruta* o un attacco del *dizionario* utilizza un file di dizionario di parole chiave di grandi dimensioni in un account utente con la speranza che uno di essi funzioni (molte password su un account).</span><span class="sxs-lookup"><span data-stu-id="b935b-230">**Brute force password (dictionary attack)**: A *brute force* or *dictionary* attack uses a large dictionary file of passwords on a user account with the hope that one of them will work (many passwords against one account).</span></span> <span data-ttu-id="b935b-231">Gli errori di blocco delle password non corretti consentono di scoraggiare gli attacchi di password Brute.</span><span class="sxs-lookup"><span data-stu-id="b935b-231">Incorrect password lock-outs help deter brute force password attacks.</span></span>

  <span data-ttu-id="b935b-232">Per l'attacco del dizionario, è possibile specificare una o più password da provare (immessa manualmente o in un file caricato) ed è possibile specificare uno o più utenti.</span><span class="sxs-lookup"><span data-stu-id="b935b-232">For the dictionary attack, you can specify one or many passwords to try (manually entered or in an uploaded file), and you can specify one or many users.</span></span>

- <span data-ttu-id="b935b-233">**Attacco spray**per la password: un attacco *spray* per la password utilizza la stessa password accuratamente considerata rispetto A un elenco di account utente (una password per molti account).</span><span class="sxs-lookup"><span data-stu-id="b935b-233">**Password spray attack**: A *password spray* attack uses the same carefully considered password against a list of user accounts (one password against many accounts).</span></span> <span data-ttu-id="b935b-234">Gli attacchi spray per la password sono più difficili da rilevare rispetto agli attacchi delle password per la forza bruta (la probabilità che il successo aumenti quando un utente malintenzionato cerca una password tra decine o centinaia di account senza il rischio di inciampare nel blocco della password errata dell'utente).</span><span class="sxs-lookup"><span data-stu-id="b935b-234">Password spray attacks are harder to detect than brute force password attacks (the probability of success increases when an attacker tries one password across dozens or hundreds of accounts without the risk of tripping the user's incorrect password lock-out).</span></span>

  <span data-ttu-id="b935b-235">Per l'attacco spray per la password, è possibile specificare solo una password da provare ed è possibile specificare uno o più utenti.</span><span class="sxs-lookup"><span data-stu-id="b935b-235">For the password spray attack, you can only specify one password to try, and you can specify one or many users.</span></span>

> [!NOTE]
> <span data-ttu-id="b935b-236">Gli attacchi tramite password in Attack Simulator passano il nome utente e le richieste di autenticazione di base delle password a un endpoint, in modo che funzionino anche con gli altri metodi (AD FS, sincronizzazione hash delle password, pass-through, PingFederate e così via).</span><span class="sxs-lookup"><span data-stu-id="b935b-236">The password attacks in Attack Simulator pass username and password Basic auth requests to an endpoint, so they also work with other authentication methods (AD FS, password hash sync, pass-through, PingFederate, etc.).</span></span> <span data-ttu-id="b935b-237">Per gli utenti che dispongono di un Master abilitato, anche se l'attacco della password tenta la password effettiva, il tentativo si registrerà sempre come un errore (in altre parole, gli utenti dell'AMF non verranno mai visualizzati nel conteggio dei **tentativi riusciti** della campagna).</span><span class="sxs-lookup"><span data-stu-id="b935b-237">For users that have MFA enabled, even if the password attack tries their actual password, the attempt will always register as a failure (in other words, MFA users will never appear in the **Successful attempts** count of the campaign).</span></span> <span data-ttu-id="b935b-238">Questo è il risultato previsto.</span><span class="sxs-lookup"><span data-stu-id="b935b-238">This is the expected result.</span></span> <span data-ttu-id="b935b-239">L'AMF è un metodo principale che consente di proteggere gli attacchi delle password.</span><span class="sxs-lookup"><span data-stu-id="b935b-239">MFA is a primary method to help protect against password attacks.</span></span>

### <a name="create-and-launch-a-password-attack-campaign"></a><span data-ttu-id="b935b-240">Creare e avviare una campagna di attacco tramite password</span><span class="sxs-lookup"><span data-stu-id="b935b-240">Create and launch a password attack campaign</span></span>

1. <span data-ttu-id="b935b-241">Nel centro sicurezza & conformità, accedere a **Threat Management** \> **Attack Simulator**.</span><span class="sxs-lookup"><span data-stu-id="b935b-241">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="b935b-242">Nella pagina **simula attacchi** fare una delle selezioni seguenti in base al tipo di campagna che si desidera creare:</span><span class="sxs-lookup"><span data-stu-id="b935b-242">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="b935b-243">Nella sezione **password forza bruta (attacco dizionario)** fare clic su **Avvia attacco** o fare clic su Attack **Details** \> **Launch Attack**.</span><span class="sxs-lookup"><span data-stu-id="b935b-243">In the **Brute Force Password (Dictionary Attack)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="b935b-244">nella sezione **attacco spray password** fare clic su **Launch Attack** o su Attack **Details** \> **Launch Attack**.</span><span class="sxs-lookup"><span data-stu-id="b935b-244">in the **Password spray attack** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="b935b-245">La procedura guidata **Configura attacco password** viene avviata in un nuovo riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="b935b-245">The **Configure Password Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="b935b-246">Nel passaggio **iniziale** , immettere un nome visualizzato univoco per la campagna e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="b935b-246">In the **Start** step, enter a unique display name for the campaign, and then click **Next**.</span></span>

4. <span data-ttu-id="b935b-247">Nel passaggio **degli utenti di destinazione** , eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b935b-247">In the **Target users** step, do one of the following steps:</span></span>

   - <span data-ttu-id="b935b-248">Fare **clic su Rubrica per** selezionare i destinatari (utenti o gruppi) per la campagna.</span><span class="sxs-lookup"><span data-stu-id="b935b-248">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="b935b-249">Ogni destinatario di destinazione deve disporre di una cassetta postale di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="b935b-249">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="b935b-250">Se si fa clic su **Filtra** e **applica** senza immettere un criterio di ricerca, tutti i destinatari vengono restituiti e aggiunti alla campagna.</span><span class="sxs-lookup"><span data-stu-id="b935b-250">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="b935b-251">Fare clic su **Importa** quindi **importazione file** per importare un valore separato da virgole (CSV) o un file di indirizzi di posta elettronica separato da una riga.</span><span class="sxs-lookup"><span data-stu-id="b935b-251">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="b935b-252">Ogni riga deve contenere l'indirizzo di posta elettronica del destinatario.</span><span class="sxs-lookup"><span data-stu-id="b935b-252">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="b935b-253">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="b935b-253">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="b935b-254">Nel passaggio **scegliere le impostazioni di attacco** scegliere le operazioni da eseguire in base al tipo di campagna:</span><span class="sxs-lookup"><span data-stu-id="b935b-254">In the **Choose attack settings** step, choose what to do based on the campaign type:</span></span>

   - <span data-ttu-id="b935b-255">**Password forza bruta (attacco dizionario)**: eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b935b-255">**Brute Force Password (Dictionary Attack)**: Do either of the following steps:</span></span>

     - <span data-ttu-id="b935b-256">**Immettere le password manualmente**: nella casella **premere INVIO per aggiungere una password** digitare una password e quindi premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="b935b-256">**Enter passwords manually**: In the **Press enter to add a password** box, type a password and then press ENTER.</span></span> <span data-ttu-id="b935b-257">Ripetere questo passaggio tutte le volte necessarie.</span><span class="sxs-lookup"><span data-stu-id="b935b-257">Repeat this step as many times as necessary.</span></span>

     - <span data-ttu-id="b935b-258">**Caricare password da un file di dizionario**: fare clic su **carica** per importare un file di testo esistente che contiene una password su ogni riga e un'ultima riga vuota.</span><span class="sxs-lookup"><span data-stu-id="b935b-258">**Upload passwords from a dictionary file**: Click **Upload** to import an existing text file that contains one password on each line and a blank last line.</span></span> <span data-ttu-id="b935b-259">Il file di testo deve avere una dimensione di 10 MB o inferiore e non può contenere più di 30000 password.</span><span class="sxs-lookup"><span data-stu-id="b935b-259">The text file must be 10 MB or less in size, and can't contain more than 30000 passwords.</span></span>

   - <span data-ttu-id="b935b-260">**Attacco spray**per la password: nelle **password da utilizzare nella casella attacco** , immettere una password.</span><span class="sxs-lookup"><span data-stu-id="b935b-260">**Password spray attack**: In **The password(s) to use in the attack** box, enter one password.</span></span>

   <span data-ttu-id="b935b-261">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="b935b-261">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="b935b-262">Nel passaggio **conferma** fare clic su **fine** per avviare la campagna.</span><span class="sxs-lookup"><span data-stu-id="b935b-262">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="b935b-263">Le password specificate sono state provate per gli utenti specificati.</span><span class="sxs-lookup"><span data-stu-id="b935b-263">The passwords you specified are tried on users you specified.</span></span>

## <a name="view-campaign-results"></a><span data-ttu-id="b935b-264">Visualizzare i risultati della campagna</span><span class="sxs-lookup"><span data-stu-id="b935b-264">View campaign results</span></span>

<span data-ttu-id="b935b-265">Dopo aver avviato una campagna, è possibile controllare lo stato e i risultati della pagina principale degli **attacchi simulati** .</span><span class="sxs-lookup"><span data-stu-id="b935b-265">After you launch a campaign, you can check the progress and results on the main **Simulate attacks** page.</span></span>

<span data-ttu-id="b935b-266">Le campagne attive visualizzeranno una barra di stato, un valore percentuale completato e il numero "(utenti completati) di (utenti totali)".</span><span class="sxs-lookup"><span data-stu-id="b935b-266">Active campaigns will show a status bar, a completed percentage value and "(completed users) of (total users)" count.</span></span> <span data-ttu-id="b935b-267">Se si fa clic sul pulsante **Aggiorna** , verrà aggiornato lo stato di avanzamento di qualsiasi campagna attiva.</span><span class="sxs-lookup"><span data-stu-id="b935b-267">Clicking the **Refresh** button will update the progress of any active campaigns.</span></span> <span data-ttu-id="b935b-268">È inoltre possibile fare clic su **termina** per arrestare una campagna attiva.</span><span class="sxs-lookup"><span data-stu-id="b935b-268">You can also click **Terminate** to stop an active campaign.</span></span>

<span data-ttu-id="b935b-269">Al termine della campagna, lo stato cambia in **attacco completato**.</span><span class="sxs-lookup"><span data-stu-id="b935b-269">When the campaign is finished, the status changes to **Attack completed**.</span></span> <span data-ttu-id="b935b-270">È possibile visualizzare i risultati della campagna eseguendo una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b935b-270">You can view the results of the campaign by doing either of the following actions:</span></span>

- <span data-ttu-id="b935b-271">Nella pagina simulazione principale degli **attacchi** , fare clic su **Visualizza report** sotto il nome della campagna.</span><span class="sxs-lookup"><span data-stu-id="b935b-271">On the main **Simulate attacks** page, click **View Report** under the name of the campaign.</span></span>

- <span data-ttu-id="b935b-272">Nella pagina simulazione principale degli **attacchi** , fare clic su **attacco dettagli** nella sezione relativa al tipo di attacco.</span><span class="sxs-lookup"><span data-stu-id="b935b-272">On the main **Simulate attacks** page, click **Attack Details** in the section for the type of attack.</span></span> <span data-ttu-id="b935b-273">Nella pagina dei **Dettagli sull'attacco** che viene visualizzata, selezionare la campagna nella sezione cronologia degli **attacchi** .</span><span class="sxs-lookup"><span data-stu-id="b935b-273">On the **Attack details** page that opens, select the campaign in the **Attack History** section.</span></span>

<span data-ttu-id="b935b-274">Una delle azioni precedenti consentirà di utilizzare una pagina denominata **Dettagli attacco**.</span><span class="sxs-lookup"><span data-stu-id="b935b-274">Either of the previous actions will take you to a page named **Attack details**.</span></span> <span data-ttu-id="b935b-275">Le informazioni disponibili in questa pagina per ogni tipo di campagna sono descritte nelle sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="b935b-275">The information that's available on this page for each type of campaign is described in the following sections.</span></span>

### <a name="spear-phishing-credentials-harvest-campaign-results"></a><span data-ttu-id="b935b-276">Risultati della campagna Spear phishing (Harvest Credentials)</span><span class="sxs-lookup"><span data-stu-id="b935b-276">Spear Phishing (Credentials Harvest) campaign results</span></span>

<span data-ttu-id="b935b-277">Le informazioni seguenti sono disponibili nella pagina dei **Dettagli sull'attacco** per ogni campagna:</span><span class="sxs-lookup"><span data-stu-id="b935b-277">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="b935b-278">Durata (data/ora di inizio e data/ora di fine) della campagna.</span><span class="sxs-lookup"><span data-stu-id="b935b-278">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="b935b-279">**Totale utenti designati**</span><span class="sxs-lookup"><span data-stu-id="b935b-279">**Total users targeted**</span></span>

- <span data-ttu-id="b935b-280">**Tentativi riusciti**: il numero di utenti che hanno fatto clic sul collegamento **e** hanno immesso le proprie credenziali (*qualsiasi* nome utente e valore password).</span><span class="sxs-lookup"><span data-stu-id="b935b-280">**Successful attempts**: The number of users who clicked the link **and** entered their credentials (*any* username and password value).</span></span>

- <span data-ttu-id="b935b-281">**Tasso di successo globale**: percentuale calcolata con **esito positivo dei tentativi**  /  **totali degli utenti mirati**.</span><span class="sxs-lookup"><span data-stu-id="b935b-281">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="b935b-282">Più **veloce fare clic su**: quanto tempo è stato necessario per il primo utente per fare clic sul collegamento dopo aver avviato la campagna.</span><span class="sxs-lookup"><span data-stu-id="b935b-282">**Fastest Click**: How long it took the first user to click the link after you launched the campaign.</span></span>

- <span data-ttu-id="b935b-283">**Media clic**: la somma del tempo impiegato da tutti per fare clic sul collegamento diviso per il numero di utenti che hanno fatto clic sul collegamento.</span><span class="sxs-lookup"><span data-stu-id="b935b-283">**Average Click**: The sum of how long it took everyone to click the link divided by the number of users who clicked the link.</span></span>

- <span data-ttu-id="b935b-284">**Fare clic su velocità di successo**: percentuale calcolata da (numero di utenti che hanno fatto clic sul collegamento)/ **Totale utenti designati**.</span><span class="sxs-lookup"><span data-stu-id="b935b-284">**Click Success Rate**: A percentage that's calculated by (number of users who clicked the link) / **Total users targeted**.</span></span>

- <span data-ttu-id="b935b-285">**Credenziali più veloci**: il tempo impiegato dal primo utente per immettere le credenziali dopo aver avviato la campagna.</span><span class="sxs-lookup"><span data-stu-id="b935b-285">**Fastest Credentials**: How long it took the first user to enter their credentials after you launched the campaign.</span></span>

- <span data-ttu-id="b935b-286">**Credenziali medie**: somma del tempo impiegato da tutti per immettere le proprie credenziali diviso per il numero di utenti che hanno immesso le proprie credenziali.</span><span class="sxs-lookup"><span data-stu-id="b935b-286">**Average Credentials**: The sum of how long it took everyone to enter their credentials divided by the number of users who entered their credentials.</span></span>

- <span data-ttu-id="b935b-287">**Tasso di successo della credenziale**: percentuale calcolata da (numero di utenti che hanno immesso le proprie credenziali)/ **Totale utenti designati**.</span><span class="sxs-lookup"><span data-stu-id="b935b-287">**Credential Success Rate**: A percentage that's calculated by (number of users who entered their credentials) / **Total users targeted**.</span></span>

- <span data-ttu-id="b935b-288">Grafico a barre che Visualizza il **collegamento selezionato** e i numeri di **credenziale forniti** al giorno.</span><span class="sxs-lookup"><span data-stu-id="b935b-288">A bar graph that shows the **Link clicked** and **Credential supplied** numbers per day.</span></span>

- <span data-ttu-id="b935b-289">Grafico a cerchio che Visualizza il **collegamento fatto clic**, **credenziali fornite**e **Nessuna** percentuale per la campagna.</span><span class="sxs-lookup"><span data-stu-id="b935b-289">A circle graph that shows the **Link clicked**, **Credential supplied**, and **None** percentages for the campaign.</span></span>

- <span data-ttu-id="b935b-290">Nella sezione **utenti compromessi** sono elencati i dettagli degli utenti che hanno fatto clic sul collegamento:</span><span class="sxs-lookup"><span data-stu-id="b935b-290">The **Compromised Users** section lists the details of the users who clicked the link:</span></span>

  - <span data-ttu-id="b935b-291">L'indirizzo di posta elettronica dell'utente</span><span class="sxs-lookup"><span data-stu-id="b935b-291">The user's email address</span></span>

  - <span data-ttu-id="b935b-292">La data e l'ora in cui si è fatto clic sul collegamento.</span><span class="sxs-lookup"><span data-stu-id="b935b-292">The date/time when they clicked the link.</span></span>

  - <span data-ttu-id="b935b-293">L'indirizzo IP del client.</span><span class="sxs-lookup"><span data-stu-id="b935b-293">The client IP address.</span></span>

  - <span data-ttu-id="b935b-294">Dettagli sulla versione dell'utente di Windows e del Web browser.</span><span class="sxs-lookup"><span data-stu-id="b935b-294">Details about the user's version of Windows and web browser.</span></span>

  <span data-ttu-id="b935b-295">È possibile fare clic su **Esporta** per esportare i risultati in un file CSV.</span><span class="sxs-lookup"><span data-stu-id="b935b-295">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="spear-phishing-attachment-campaign-results"></a><span data-ttu-id="b935b-296">Risultati della campagna di phishing (allegato) Spear</span><span class="sxs-lookup"><span data-stu-id="b935b-296">Spear Phishing (Attachment) campaign results</span></span>

<span data-ttu-id="b935b-297">Le informazioni seguenti sono disponibili nella pagina dei **Dettagli sull'attacco** per ogni campagna:</span><span class="sxs-lookup"><span data-stu-id="b935b-297">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="b935b-298">Durata (data/ora di inizio e data/ora di fine) della campagna.</span><span class="sxs-lookup"><span data-stu-id="b935b-298">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="b935b-299">**Totale utenti designati**</span><span class="sxs-lookup"><span data-stu-id="b935b-299">**Total users targeted**</span></span>

- <span data-ttu-id="b935b-300">**Tentativi riusciti**: il numero di utenti che hanno aperto o scaricato e aperto l'allegato (l'anteprima non conta).</span><span class="sxs-lookup"><span data-stu-id="b935b-300">**Successful attempts**: The number of users who opened or downloaded and opened the attachment (preview doesn't count).</span></span>

- <span data-ttu-id="b935b-301">**Tasso di successo globale**: percentuale calcolata con **esito positivo dei tentativi**  /  **totali degli utenti mirati**.</span><span class="sxs-lookup"><span data-stu-id="b935b-301">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="b935b-302">**Intervallo di tempo di apertura più rapido**: il tempo impiegato dal primo utente per aprire l'allegato dopo aver avviato la campagna.</span><span class="sxs-lookup"><span data-stu-id="b935b-302">**Fastest attachment open time**: How long it took the first user to open the attachment after you launched the campaign.</span></span>

- <span data-ttu-id="b935b-303">**Intervallo di tempo di apertura medio**: la somma di quanto tempo ha impiegato tutti per aprire l'allegato diviso per il numero di utenti che hanno aperto l'allegato.</span><span class="sxs-lookup"><span data-stu-id="b935b-303">**Average attachment open time**: The sum of how long it took everyone to open the attachment divided by the number of users who opened the attachment.</span></span>

- <span data-ttu-id="b935b-304">**Tasso di successo Open Attachment**: percentuale calcolata da (numero di utenti che hanno aperto l'allegato)/ **Totale utenti designati**.</span><span class="sxs-lookup"><span data-stu-id="b935b-304">**Attachment open success rate**: A percentage that's calculated by (number of users who opened the attachment) / **Total users targeted**.</span></span>

### <a name="brute-force-password-dictionary-attack-campaign-results"></a><span data-ttu-id="b935b-305">Risultati della campagna password forza bruta (attacco dizionario)</span><span class="sxs-lookup"><span data-stu-id="b935b-305">Brute Force Password (Dictionary Attack) campaign results</span></span>

<span data-ttu-id="b935b-306">Le informazioni seguenti sono disponibili nella pagina dei **Dettagli sull'attacco** per ogni campagna:</span><span class="sxs-lookup"><span data-stu-id="b935b-306">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="b935b-307">Durata (data/ora di inizio e data/ora di fine) della campagna.</span><span class="sxs-lookup"><span data-stu-id="b935b-307">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="b935b-308">**Totale utenti designati**</span><span class="sxs-lookup"><span data-stu-id="b935b-308">**Total users targeted**</span></span>

- <span data-ttu-id="b935b-309">**Tentativi riusciti**: il numero di utenti che hanno trovato l'utilizzo di una delle password specificate.</span><span class="sxs-lookup"><span data-stu-id="b935b-309">**Successful attempts**: The number of users who were found to be using one of the specified passwords.</span></span>

- <span data-ttu-id="b935b-310">**Tasso di successo globale**: percentuale calcolata con **esito positivo dei tentativi**  /  **totali degli utenti mirati**.</span><span class="sxs-lookup"><span data-stu-id="b935b-310">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="b935b-311">La sezione **utenti compromessi** elenca gli indirizzi di posta elettronica degli utenti coinvolti.</span><span class="sxs-lookup"><span data-stu-id="b935b-311">The **Compromised Users** section lists the email addresses of the affected users.</span></span> <span data-ttu-id="b935b-312">È possibile fare clic su **Esporta** per esportare i risultati in un file CSV.</span><span class="sxs-lookup"><span data-stu-id="b935b-312">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="password-spray-attack-campaign-results"></a><span data-ttu-id="b935b-313">Risultati della campagna di attacco a spruzzo di password</span><span class="sxs-lookup"><span data-stu-id="b935b-313">Password spray attack campaign results</span></span>

<span data-ttu-id="b935b-314">Le informazioni seguenti sono disponibili nella pagina dei **Dettagli sull'attacco** per ogni campagna:</span><span class="sxs-lookup"><span data-stu-id="b935b-314">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="b935b-315">Durata (data/ora di inizio e data/ora di fine) della campagna.</span><span class="sxs-lookup"><span data-stu-id="b935b-315">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="b935b-316">**Totale utenti designati**</span><span class="sxs-lookup"><span data-stu-id="b935b-316">**Total users targeted**</span></span>

- <span data-ttu-id="b935b-317">**Tentativi riusciti**: il numero di utenti che sono stati trovati a utilizzare la password specificata.</span><span class="sxs-lookup"><span data-stu-id="b935b-317">**Successful attempts**: The number of users who were found to be using the specified password.</span></span>

- <span data-ttu-id="b935b-318">**Tasso di successo globale**: percentuale calcolata con **esito positivo dei tentativi**  /  **totali degli utenti mirati**.</span><span class="sxs-lookup"><span data-stu-id="b935b-318">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>
