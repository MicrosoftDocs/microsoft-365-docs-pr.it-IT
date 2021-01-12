---
title: Simulatore di attacco in Microsoft Defender per Office 365
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
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Gli amministratori possono imparare a usare Attack Simulator per eseguire attacchi simulati di phishing e password nelle organizzazioni di Microsoft 365 E5 o Microsoft Defender per Office 365 piano 2.
ms.openlocfilehash: 2ffec891f7b1021f3c6c51b003c78aacb0ec0d6a
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794533"
---
# <a name="attack-simulator-in-microsoft-defender-for-office-365"></a><span data-ttu-id="82fcf-103">Simulatore di attacco in Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="82fcf-103">Attack Simulator in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="82fcf-104">Se l'organizzazione dispone di Microsoft Defender per Office 365 piano 2, in cui sono incluse le [funzionalità di ricerca e di risposta alle minacce](office-365-ti.md), è possibile utilizzare Attack Simulator nel centro sicurezza & conformità per eseguire scenari di attacco realistici nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="82fcf-104">If your organization has Microsoft Defender for Office 365 Plan 2, which includes [Threat Investigation and Response capabilities](office-365-ti.md), you can use Attack Simulator in the Security & Compliance Center to run realistic attack scenarios in your organization.</span></span> <span data-ttu-id="82fcf-105">Questi attacchi simulati consentono di identificare e individuare gli utenti vulnerabili prima che un attacco reale impatti la linea di base.</span><span class="sxs-lookup"><span data-stu-id="82fcf-105">These simulated attacks can help you identify and find vulnerable users before a real attack impacts your bottom line.</span></span> <span data-ttu-id="82fcf-106">Leggere questo articolo per ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="82fcf-106">Read this article to learn more.</span></span>

> [!NOTE]
> <span data-ttu-id="82fcf-107">I dati relativi alla simulazione e all'addestramento degli attacchi vengono archiviati con altri dati dei clienti per i servizi Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="82fcf-107">Attack simulation and training related data is stored with other customer data for Microsoft 365 services.</span></span> <span data-ttu-id="82fcf-108">Per ulteriori informazioni, vedere [Microsoft 365 data locations](/microsoft-365/enterprise/o365-data-locations).</span><span class="sxs-lookup"><span data-stu-id="82fcf-108">For more information see [Microsoft 365 data locations](/microsoft-365/enterprise/o365-data-locations).</span></span>

> [!TIP]
> <span data-ttu-id="82fcf-109">La formazione sulla simulazione degli attacchi è disponibile per l'anteprima pubblica nel centro sicurezza Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="82fcf-109">Attack simulation training is available for public preview in the Microsoft 365 security center.</span></span> <span data-ttu-id="82fcf-110">Per ulteriori informazioni, vedere [simulare un attacco di phishing con Microsoft Defender per Office 365](attack-simulation-training.md) .</span><span class="sxs-lookup"><span data-stu-id="82fcf-110">Check out [Simulate a phishing attack with Microsoft Defender for Office 365](attack-simulation-training.md) to learn more.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="82fcf-111">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="82fcf-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="82fcf-112">Per aprire il Centro sicurezza e conformità, passare a <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="82fcf-112">To open the Security & Compliance Center, go to <https://protection.office.com/>.</span></span> <span data-ttu-id="82fcf-113">Simulatore di attacco è disponibile in **Threat Management** \> **Attack Simulator**.</span><span class="sxs-lookup"><span data-stu-id="82fcf-113">Attack simulator is available at **Threat management** \> **Attack simulator**.</span></span> <span data-ttu-id="82fcf-114">Andare direttamente a attacco simulatore, aprire <https://protection.office.com/attacksimulator> .</span><span class="sxs-lookup"><span data-stu-id="82fcf-114">Go go directly to attack simulator, open <https://protection.office.com/attacksimulator>.</span></span>

- <span data-ttu-id="82fcf-115">Per ulteriori informazioni sulla disponibilità di simulatori di attacco in diverse sottoscrizioni di Microsoft 365, vedere [Descrizione del servizio Microsoft Defender per Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span><span class="sxs-lookup"><span data-stu-id="82fcf-115">For more information about the availability of Attack Simulator across different Microsoft 365 subscriptions, see [Microsoft Defender for Office 365 service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

- <span data-ttu-id="82fcf-116">È necessario essere membri dei gruppi di ruoli **Gestione organizzazione** o **amministratore sicurezza** .</span><span class="sxs-lookup"><span data-stu-id="82fcf-116">You need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="82fcf-117">Per altre informazioni sui gruppi di ruoli nel Centro sicurezza e conformità, vedere [Autorizzazioni nel Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="82fcf-117">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="82fcf-118">L'account deve essere configurato per l'autenticazione a più fattori (AMF) per creare e gestire le campagne in Attack Simulator.</span><span class="sxs-lookup"><span data-stu-id="82fcf-118">Your account needs to be configured for multi-factor authentication (MFA) to create and manage campaigns in Attack Simulator.</span></span> <span data-ttu-id="82fcf-119">Per istruzioni, vedere [configurare l'autenticazione](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication)a più fattori.</span><span class="sxs-lookup"><span data-stu-id="82fcf-119">For instructions, see [Set up multi-factor authentication](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication).</span></span>

- <span data-ttu-id="82fcf-120">Le campagne di phishing raccolgono ed elaborano gli eventi per 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="82fcf-120">Phishing campaigns will collect and process events for 30 days.</span></span> <span data-ttu-id="82fcf-121">I dati della campagna cronologica saranno disponibili fino a 90 giorni dopo l'avvio della campagna.</span><span class="sxs-lookup"><span data-stu-id="82fcf-121">Historical campaign data will be available for up to 90 days after you launch the campaign.</span></span>

- <span data-ttu-id="82fcf-122">Non sono disponibili i cmdlet di PowerShell corrispondenti per il simulatore di attacco.</span><span class="sxs-lookup"><span data-stu-id="82fcf-122">There are no corresponding PowerShell cmdlets for Attack Simulator.</span></span>

## <a name="spear-phishing-campaigns"></a><span data-ttu-id="82fcf-123">Campagne di phishing Spear</span><span class="sxs-lookup"><span data-stu-id="82fcf-123">Spear phishing campaigns</span></span>

<span data-ttu-id="82fcf-124">Il *phishing* è un termine generico per gli attacchi di posta elettronica che tentano di rubare informazioni sensibili nei messaggi che sembrano provenire da mittenti legittimi o attendibili.</span><span class="sxs-lookup"><span data-stu-id="82fcf-124">*Phishing* is a generic term for email attacks that try to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="82fcf-125">*Spear phishing* è un attacco di phishing mirato che utilizza contenuti mirati e personalizzati appositamente personalizzati per i destinatari mirati (in genere, dopo la ricognizione dei destinatari da parte dell'utente malintenzionato).</span><span class="sxs-lookup"><span data-stu-id="82fcf-125">*Spear phishing* is a targeted phishing attack that uses focused and customized content that's specifically tailored to the targeted recipients (typically, after reconnaissance on the recipients by the attacker).</span></span>

<span data-ttu-id="82fcf-126">In Attack Simulator sono disponibili due diversi tipi di campagne di phishing Spear:</span><span class="sxs-lookup"><span data-stu-id="82fcf-126">In Attack Simulator, two different types of spear phishing campaigns are available:</span></span>

- <span data-ttu-id="82fcf-127">**Spear phishing (Harvest Credentials)**: l'attacco tenta di convincere i destinatari a fare clic su un URL nel messaggio.</span><span class="sxs-lookup"><span data-stu-id="82fcf-127">**Spear phishing (credentials harvest)**: The attack tries to convince the recipients to click a URL in the message.</span></span> <span data-ttu-id="82fcf-128">Se si fa clic sul collegamento, viene richiesto di immettere le proprie credenziali.</span><span class="sxs-lookup"><span data-stu-id="82fcf-128">If they click the link, they're asked to enter their credentials.</span></span> <span data-ttu-id="82fcf-129">In caso contrario, vengono eseguite in una delle posizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="82fcf-129">If they do, they're taken to one of the following locations:</span></span>

  - <span data-ttu-id="82fcf-130">Una pagina predefinita che spiega che si tratta di un semplice test e fornisce suggerimenti per il riconoscimento dei messaggi di phishing.</span><span class="sxs-lookup"><span data-stu-id="82fcf-130">A default page that explains that this was a just a test, and gives tips for recognizing phishing messages.</span></span>

    ![Cosa vedranno gli utenti se fanno clic sul collegamento di phishing e immettono le proprie credenziali](../../media/attack-simulator-phishing-result.png)

  - <span data-ttu-id="82fcf-132">Una pagina personalizzata (URL) specificata.</span><span class="sxs-lookup"><span data-stu-id="82fcf-132">A custom page (URL) that you specify.</span></span>

- <span data-ttu-id="82fcf-133">**Spear phishing (Attachment)**: l'attacco tenta di convincere i destinatari ad aprire un allegato. docx o. pdf nel messaggio.</span><span class="sxs-lookup"><span data-stu-id="82fcf-133">**Spear phishing (attachment)**: The attack tries to convince the recipients to open a .docx or .pdf attachment in the message.</span></span> <span data-ttu-id="82fcf-134">L'allegato contiene lo stesso contenuto del collegamento di phishing predefinito, ma la prima frase inizia con " \<Display Name\> , si sta vedendo questo messaggio come un messaggio di posta elettronica recente è stato aperto...".</span><span class="sxs-lookup"><span data-stu-id="82fcf-134">The attachment contains the same content from the default phishing link, but the first sentence starts with "\<Display Name\>, you are seeing this message as a recent email message you opened...".</span></span>

> [!NOTE]
> <span data-ttu-id="82fcf-135">Attualmente, le campagne di phishing Spear in Attack Simulator non scadono.</span><span class="sxs-lookup"><span data-stu-id="82fcf-135">Currently, spear phishing campaigns in Attack Simulator don't expire.</span></span>

### <a name="create-a-spear-phishing-campaign"></a><span data-ttu-id="82fcf-136">Creare una campagna di phishing di Spear</span><span class="sxs-lookup"><span data-stu-id="82fcf-136">Create a spear phishing campaign</span></span>

<span data-ttu-id="82fcf-137">Una parte importante di qualsiasi campagna di phishing Spear è l'aspetto del messaggio di posta elettronica inviato ai destinatari mirati.</span><span class="sxs-lookup"><span data-stu-id="82fcf-137">An important part of any spear phishing campaign is the look and feel of the email message that's sent to the targeted recipients.</span></span> <span data-ttu-id="82fcf-138">Per creare e configurare il messaggio di posta elettronica, sono disponibili le seguenti opzioni:</span><span class="sxs-lookup"><span data-stu-id="82fcf-138">To create and configure the email message, you have these options:</span></span>

- <span data-ttu-id="82fcf-139">**Utilizzo di un modello di posta elettronica incorporato**: sono disponibili due modelli incorporati: **Giveaway Prize** and **Payroll Update**.</span><span class="sxs-lookup"><span data-stu-id="82fcf-139">**Use a built-in email template**: Two built-in templates are available: **Prize Giveaway** and **Payroll Update**.</span></span> <span data-ttu-id="82fcf-140">È possibile personalizzare ulteriormente alcune, tutte o nessuna delle proprietà di posta elettronica dal modello quando si crea e si avvia la campagna.</span><span class="sxs-lookup"><span data-stu-id="82fcf-140">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="82fcf-141">**Creare un modello di posta elettronica riutilizzabile**: dopo aver creato e salvato il modello di posta elettronica, è possibile utilizzarlo nuovamente nelle future campagne di phishing Spear.</span><span class="sxs-lookup"><span data-stu-id="82fcf-141">**Create a reusable email template**: After you create and save the email template, you can use it again in future spear phishing campaigns.</span></span> <span data-ttu-id="82fcf-142">È possibile personalizzare ulteriormente alcune, tutte o nessuna delle proprietà di posta elettronica dal modello quando si crea e si avvia la campagna.</span><span class="sxs-lookup"><span data-stu-id="82fcf-142">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="82fcf-143">**Creare il messaggio di posta elettronica nella procedura guidata**: è possibile creare il messaggio di posta elettronica direttamente nella procedura guidata quando si crea e si avvia la campagna di phishing Spear.</span><span class="sxs-lookup"><span data-stu-id="82fcf-143">**Create the email message in the wizard**: You can create the email message directly in the wizard as you create and launch the spear phishing campaign.</span></span>

#### <a name="step-1-optional-create-a-custom-email-template"></a><span data-ttu-id="82fcf-144">Passaggio 1 (facoltativo): creare un modello di posta elettronica personalizzato</span><span class="sxs-lookup"><span data-stu-id="82fcf-144">Step 1 (Optional): Create a custom email template</span></span>

<span data-ttu-id="82fcf-145">Se si intende utilizzare uno dei modelli incorporati o creare il messaggio di posta elettronica direttamente nella procedura guidata, è possibile ignorare questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="82fcf-145">If you're going to use one of the built-in templates or create the email message directly in the wizard, you can skip this step.</span></span>

1. <span data-ttu-id="82fcf-146">Nel centro sicurezza & conformità, accedere a **Threat Management** \> **Attack Simulator**.</span><span class="sxs-lookup"><span data-stu-id="82fcf-146">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="82fcf-147">Nella pagina **simula attacchi** , nella sezione **spear phishing (credentials Harvest)** o **spear phishing (Attachment)** , fare clic su **Attack Details**.</span><span class="sxs-lookup"><span data-stu-id="82fcf-147">On the **Simulate attacks** page, in either the **Spear Phishing (Credentials Harvest)** or **Spear Phishing (Attachment)** sections, click **Attack Details**.</span></span>

   <span data-ttu-id="82fcf-148">Non importa dove creare il modello.</span><span class="sxs-lookup"><span data-stu-id="82fcf-148">It doesn't matter where you create the template.</span></span> <span data-ttu-id="82fcf-149">Le opzioni disponibili nel modello sono uguali per entrambi i tipi di attacchi di phishing.</span><span class="sxs-lookup"><span data-stu-id="82fcf-149">The available options in the template are the same for both types of phishing attacks.</span></span>

3. <span data-ttu-id="82fcf-150">Nella pagina dei **Dettagli sull'attacco** visualizzata, nella sezione **modelli di phishing** , nell'area **Crea modelli** fare clic su **nuovo modello**.</span><span class="sxs-lookup"><span data-stu-id="82fcf-150">In the **Attack details** page that opens, in the **Phishing Templates** section, in the **Create Templates** area, click **New Template**.</span></span>

4. <span data-ttu-id="82fcf-151">La procedura guidata **Configura modello di phishing** viene avviata in un nuovo riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="82fcf-151">The **Configure Phishing Template** wizard starts in a new flyout.</span></span> <span data-ttu-id="82fcf-152">Nel passaggio **iniziale** , immettere un nome visualizzato univoco per il modello e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="82fcf-152">In the **Start** step, enter a unique display name for the template, and then click **Next**.</span></span>

5. <span data-ttu-id="82fcf-153">Nel passaggio **Configure email details** , configurare le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="82fcf-153">In the **Configure email details** step, configure the following settings:</span></span>

   - <span data-ttu-id="82fcf-154">**From (Name)**: il nome visualizzato utilizzato per il mittente del messaggio.</span><span class="sxs-lookup"><span data-stu-id="82fcf-154">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="82fcf-155">**From (posta elettronica)**: l'indirizzo di posta elettronica del mittente.</span><span class="sxs-lookup"><span data-stu-id="82fcf-155">**From (Email)**: The sender's email address.</span></span>

   - <span data-ttu-id="82fcf-156">**URL del server di accesso di phishing**: fare clic sul menu a discesa e selezionare uno degli URL disponibili nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="82fcf-156">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="82fcf-157">Questo è l'URL a cui gli utenti saranno tentati di fare clic.</span><span class="sxs-lookup"><span data-stu-id="82fcf-157">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="82fcf-158">Le opzioni disponibili sono:</span><span class="sxs-lookup"><span data-stu-id="82fcf-158">The choices are:</span></span>

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
     > <span data-ttu-id="82fcf-159">Un servizio di reputazione URL potrebbe identificare uno o più di questi URL come non sicuri.</span><span class="sxs-lookup"><span data-stu-id="82fcf-159">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="82fcf-160">Controllare la disponibilità dell'URL nei Web browser supportati prima di utilizzare l'URL in una campagna di phishing.</span><span class="sxs-lookup"><span data-stu-id="82fcf-160">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span>

   - <span data-ttu-id="82fcf-161">**URL della pagina di destinazione personalizzata**: immettere una pagina di destinazione facoltativa in cui gli utenti vengono eseguiti se fanno clic sul collegamento di phishing e immettono le proprie credenziali.</span><span class="sxs-lookup"><span data-stu-id="82fcf-161">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="82fcf-162">Questo collegamento sostituisce la pagina di destinazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="82fcf-162">This link replaces the default landing page.</span></span> <span data-ttu-id="82fcf-163">Ad esempio, se si dispone di un training di sensibilizzazione interno, è possibile specificare l'URL qui.</span><span class="sxs-lookup"><span data-stu-id="82fcf-163">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="82fcf-164">**Categoria**: attualmente, questa impostazione non viene utilizzata (qualsiasi elemento immesso viene ignorato).</span><span class="sxs-lookup"><span data-stu-id="82fcf-164">**Category**: Currently, this setting isn't used (anything you enter is ignored).</span></span>

   - <span data-ttu-id="82fcf-165">**Subject**: il campo **Subject** del messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="82fcf-165">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="82fcf-166">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="82fcf-166">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="82fcf-167">Nel passaggio di creazione della **posta elettronica** creare il corpo del messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="82fcf-167">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="82fcf-168">È possibile utilizzare la scheda **posta elettronica** (un editor HTML RTF) oppure la scheda **origine** (codice HTML non elaborato).</span><span class="sxs-lookup"><span data-stu-id="82fcf-168">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="82fcf-169">La formattazione HTML può essere semplice o complessa come è necessario.</span><span class="sxs-lookup"><span data-stu-id="82fcf-169">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="82fcf-170">È possibile inserire immagini e testo per migliorare la credibilità del messaggio nel client di posta elettronica del destinatario.</span><span class="sxs-lookup"><span data-stu-id="82fcf-170">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="82fcf-171">`${username}` inserisce il nome del destinatario.</span><span class="sxs-lookup"><span data-stu-id="82fcf-171">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="82fcf-172">`${loginserverurl}` inserisce il valore dell' **URL del server di accesso di phishing** dal passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="82fcf-172">`${loginserverurl}` inserts the **Phishing Login Server URL** value from the previous step.</span></span>

   <span data-ttu-id="82fcf-173">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="82fcf-173">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="82fcf-174">Nel passaggio **conferma** fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="82fcf-174">In the **Confirm** step, click **Finish**.</span></span>

#### <a name="step-2-create-and-launch-the-spear-phishing-campaign"></a><span data-ttu-id="82fcf-175">Passaggio 2: creare e avviare la campagna di phishing Spear</span><span class="sxs-lookup"><span data-stu-id="82fcf-175">Step 2: Create and launch the spear phishing campaign</span></span>

1. <span data-ttu-id="82fcf-176">Nel centro sicurezza & conformità, accedere a **Threat Management** \> **Attack Simulator**.</span><span class="sxs-lookup"><span data-stu-id="82fcf-176">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="82fcf-177">Nella pagina **simula attacchi** fare una delle selezioni seguenti in base al tipo di campagna che si desidera creare:</span><span class="sxs-lookup"><span data-stu-id="82fcf-177">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="82fcf-178">Nella sezione **spear phishing (raccolta credenziali)** fare clic su **Launch Attack** o fare clic su Attack **Details** \> **Launch Attack**.</span><span class="sxs-lookup"><span data-stu-id="82fcf-178">In the **Spear Phishing (Credentials Harvest)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="82fcf-179">Nella sezione **spear phishing (Attachment)** , fare clic su **Launch Attack** o fare clic su Attack **Details** \> **Launch Attack**.</span><span class="sxs-lookup"><span data-stu-id="82fcf-179">In the **Spear Phishing (Attachment)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="82fcf-180">La procedura guidata **Configura attacco di phishing** viene avviata in un nuovo riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="82fcf-180">The **Configure Phishing Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="82fcf-181">Nel passaggio **iniziale** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="82fcf-181">In the **Start** step, do one of the following steps:</span></span>

   - <span data-ttu-id="82fcf-182">Nella casella **nome** immettere un nome visualizzato univoco per la campagna.</span><span class="sxs-lookup"><span data-stu-id="82fcf-182">In the **Name** box, enter a unique display name for the campaign.</span></span> <span data-ttu-id="82fcf-183">Non fare clic su **Usa modello** perché verrà creato il messaggio di posta elettronica in un secondo momento nella procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="82fcf-183">Don't click **Use Template**, because you'll create the email message later in the wizard.</span></span>

   - <span data-ttu-id="82fcf-184">Fare clic su **Usa modello** e selezionare un modello di posta elettronica incorporato o personalizzato.</span><span class="sxs-lookup"><span data-stu-id="82fcf-184">Click **Use Template** and select a built-in or custom email template.</span></span> <span data-ttu-id="82fcf-185">Dopo aver selezionato il modello, la casella **nome** viene riempita automaticamente in base al modello, ma è possibile modificarne il nome.</span><span class="sxs-lookup"><span data-stu-id="82fcf-185">After you select the template, the **Name** box is automatically filled based on the template, but you can change the name.</span></span>

   ![Pagina iniziale di phishing](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)

   <span data-ttu-id="82fcf-187">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="82fcf-187">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="82fcf-188">Nel passaggio **destinatari di destinazione** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="82fcf-188">In the **Target recipients** step, do one of the following steps:</span></span>

   - <span data-ttu-id="82fcf-189">Fare **clic su Rubrica per** selezionare i destinatari (utenti o gruppi) per la campagna.</span><span class="sxs-lookup"><span data-stu-id="82fcf-189">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="82fcf-190">Ogni destinatario di destinazione deve disporre di una cassetta postale di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="82fcf-190">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="82fcf-191">Se si fa clic su **Filtra** e **applica** senza immettere un criterio di ricerca, tutti i destinatari vengono restituiti e aggiunti alla campagna.</span><span class="sxs-lookup"><span data-stu-id="82fcf-191">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="82fcf-192">Fare clic su **Importa** quindi **importazione file** per importare un valore separato da virgole (CSV) o un file di indirizzi di posta elettronica separato da una riga.</span><span class="sxs-lookup"><span data-stu-id="82fcf-192">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="82fcf-193">Ogni riga deve contenere l'indirizzo di posta elettronica del destinatario.</span><span class="sxs-lookup"><span data-stu-id="82fcf-193">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="82fcf-194">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="82fcf-194">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="82fcf-195">Nel passaggio **Configure email details** , configurare le seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="82fcf-195">In the **Configure email details** step, configure the following settings:</span></span>

   <span data-ttu-id="82fcf-196">Se nel passaggio **iniziale** è stato selezionato un modello, la maggior parte di questi valori è già configurata, ma è possibile modificarli.</span><span class="sxs-lookup"><span data-stu-id="82fcf-196">If you selected a template in the **Start** step, most of these values are already configured, but you can change them.</span></span>

   - <span data-ttu-id="82fcf-197">**From (Name)**: il nome visualizzato utilizzato per il mittente del messaggio.</span><span class="sxs-lookup"><span data-stu-id="82fcf-197">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="82fcf-198">**From (posta elettronica)**: l'indirizzo di posta elettronica del mittente.</span><span class="sxs-lookup"><span data-stu-id="82fcf-198">**From (Email)**: The sender's email address.</span></span> <span data-ttu-id="82fcf-199">È possibile immettere un indirizzo di posta elettronica reale o fasullo dal dominio di posta elettronica dell'organizzazione oppure è possibile immettere un indirizzo di posta elettronica esterno reale o fasullo.</span><span class="sxs-lookup"><span data-stu-id="82fcf-199">You can enter a real or fake email address from your organization's email domain, or you can enter a real or fake external email address.</span></span> <span data-ttu-id="82fcf-200">Un indirizzo di posta elettronica del mittente valido dell'organizzazione verrà effettivamente risolto nel client di posta elettronica del destinatario.</span><span class="sxs-lookup"><span data-stu-id="82fcf-200">A valid sender email address from your organization will actually resolve in the recipient's email client.</span></span>

   - <span data-ttu-id="82fcf-201">**URL del server di accesso di phishing**: fare clic sul menu a discesa e selezionare uno degli URL disponibili nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="82fcf-201">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="82fcf-202">Questo è l'URL a cui gli utenti saranno tentati di fare clic.</span><span class="sxs-lookup"><span data-stu-id="82fcf-202">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="82fcf-203">Le opzioni disponibili sono:</span><span class="sxs-lookup"><span data-stu-id="82fcf-203">The choices are:</span></span>

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
     > - <span data-ttu-id="82fcf-204">Tutti gli URL sono intenzionalmente http, non HTTPS.</span><span class="sxs-lookup"><span data-stu-id="82fcf-204">All of the URLs are intentionally http, not https.</span></span>
     >
     > - <span data-ttu-id="82fcf-205">Un servizio di reputazione URL potrebbe identificare uno o più di questi URL come non sicuri.</span><span class="sxs-lookup"><span data-stu-id="82fcf-205">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="82fcf-206">Controllare la disponibilità dell'URL nei Web browser supportati prima di utilizzare l'URL in una campagna di phishing.</span><span class="sxs-lookup"><span data-stu-id="82fcf-206">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span>
     >
     > - <span data-ttu-id="82fcf-207">È necessario selezionare un URL.</span><span class="sxs-lookup"><span data-stu-id="82fcf-207">You are required to select a URL.</span></span> <span data-ttu-id="82fcf-208">Per le campagne di **phishing (Attachment)** , è possibile rimuovere il collegamento dal corpo del messaggio nel passaggio successivo (in caso contrario, il messaggio conterrà sia un collegamento **che** un allegato).</span><span class="sxs-lookup"><span data-stu-id="82fcf-208">For **Spear Phishing (Attachment)** campaigns, you can remove the link from the body of the message in the next step (otherwise, the message will contain both a link **and** an attachment).</span></span>

   - <span data-ttu-id="82fcf-209">**Tipo di allegato**: questa impostazione è disponibile solo nelle campagne di **phishing (allegato) di Spear** .</span><span class="sxs-lookup"><span data-stu-id="82fcf-209">**Attachment Type**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="82fcf-210">Fare clic sull'elenco a discesa e selezionare **. DOCX** o **. File PDF** dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="82fcf-210">Click the drop down and select **.DOCX** or **.PDF** from the list.</span></span>

   - <span data-ttu-id="82fcf-211">**Nome allegato**: questa impostazione è disponibile solo nelle campagne di **phishing (allegato) di Spear** .</span><span class="sxs-lookup"><span data-stu-id="82fcf-211">**Attachment Name**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="82fcf-212">Immettere un nome di file per l'allegato. docx o. pdf.</span><span class="sxs-lookup"><span data-stu-id="82fcf-212">Enter a filename for the .docx or .pdf attachment.</span></span>

   - <span data-ttu-id="82fcf-213">**URL della pagina di destinazione personalizzata**: immettere una pagina di destinazione facoltativa in cui gli utenti vengono eseguiti se fanno clic sul collegamento di phishing e immettono le proprie credenziali.</span><span class="sxs-lookup"><span data-stu-id="82fcf-213">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="82fcf-214">Questo collegamento sostituisce la pagina di destinazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="82fcf-214">This link replaces the default landing page.</span></span> <span data-ttu-id="82fcf-215">Ad esempio, se si dispone di un training di sensibilizzazione interno, è possibile specificare l'URL qui.</span><span class="sxs-lookup"><span data-stu-id="82fcf-215">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="82fcf-216">**Subject**: il campo **Subject** del messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="82fcf-216">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="82fcf-217">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="82fcf-217">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="82fcf-218">Nel passaggio di creazione della **posta elettronica** creare il corpo del messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="82fcf-218">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="82fcf-219">Se nel passaggio **iniziale** è stato selezionato un modello, il corpo del messaggio è già configurato, ma è possibile personalizzarlo.</span><span class="sxs-lookup"><span data-stu-id="82fcf-219">If you selected a template in the **Start** step, the message body is already configured, but you can customize it.</span></span> <span data-ttu-id="82fcf-220">È possibile utilizzare la scheda **posta elettronica** (un editor HTML RTF) oppure la scheda **origine** (codice HTML non elaborato).</span><span class="sxs-lookup"><span data-stu-id="82fcf-220">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="82fcf-221">La formattazione HTML può essere semplice o complessa come è necessario.</span><span class="sxs-lookup"><span data-stu-id="82fcf-221">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="82fcf-222">È possibile inserire immagini e testo per migliorare la credibilità del messaggio nel client di posta elettronica del destinatario.</span><span class="sxs-lookup"><span data-stu-id="82fcf-222">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="82fcf-223">`${username}` inserisce il nome del destinatario.</span><span class="sxs-lookup"><span data-stu-id="82fcf-223">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="82fcf-224">`${loginserverurl}` inserisce il valore dell' **URL del server di accesso di phishing** .</span><span class="sxs-lookup"><span data-stu-id="82fcf-224">`${loginserverurl}` inserts the **Phishing Login Server URL** value.</span></span>

   <span data-ttu-id="82fcf-225">Per le campagne di **phishing (allegato)** , è necessario rimuovere il collegamento dal corpo del messaggio (in caso contrario, il messaggio conterrà sia un collegamento **che** un allegato e i collegamenti non vengono registrati in una campagna di allegato).</span><span class="sxs-lookup"><span data-stu-id="82fcf-225">For **Spear Phishing (Attachment)** campaigns, you should remove the link from the body of the message (otherwise, the message will contain both a link **and** an attachment, and link clicks aren't tracked in an attachment campaign).</span></span>

   ![Comporre il corpo della posta elettronica](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)

   <span data-ttu-id="82fcf-227">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="82fcf-227">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="82fcf-228">Nel passaggio **conferma** fare clic su **fine** per avviare la campagna.</span><span class="sxs-lookup"><span data-stu-id="82fcf-228">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="82fcf-229">Il messaggio di phishing viene recapitato ai destinatari mirati.</span><span class="sxs-lookup"><span data-stu-id="82fcf-229">The phishing message is delivered to the targeted recipients.</span></span>

## <a name="password-attack-campaigns"></a><span data-ttu-id="82fcf-230">Campagne di attacco tramite password</span><span class="sxs-lookup"><span data-stu-id="82fcf-230">Password attack campaigns</span></span>

<span data-ttu-id="82fcf-231">Un *attacco* per la password cerca di indovinare le password per gli account utente di un'organizzazione, in genere dopo che l'utente malintenzionato ha identificato uno o più account validi.</span><span class="sxs-lookup"><span data-stu-id="82fcf-231">A *password attack* tries to guess passwords for user accounts in an organization, typically after the attacker has identified one or more valid user accounts.</span></span>

<span data-ttu-id="82fcf-232">In Attack Simulator, sono disponibili due diversi tipi di campagne di attacco per la password per testare la complessità delle password degli utenti:</span><span class="sxs-lookup"><span data-stu-id="82fcf-232">In Attack Simulator, two different types of password attack campaigns are available for you to test the complexity of your users' passwords:</span></span>

- <span data-ttu-id="82fcf-233">**Password forza bruta (attacco dizionario)**: una *forza bruta* o un attacco del *dizionario* utilizza un file di dizionario di parole chiave di grandi dimensioni in un account utente con la speranza che uno di essi funzioni (molte password su un account).</span><span class="sxs-lookup"><span data-stu-id="82fcf-233">**Brute force password (dictionary attack)**: A *brute force* or *dictionary* attack uses a large dictionary file of passwords on a user account with the hope that one of them will work (many passwords against one account).</span></span> <span data-ttu-id="82fcf-234">Gli errori di blocco delle password non corretti consentono di scoraggiare gli attacchi di password Brute.</span><span class="sxs-lookup"><span data-stu-id="82fcf-234">Incorrect password lock-outs help deter brute force password attacks.</span></span>

  <span data-ttu-id="82fcf-235">Per l'attacco del dizionario, è possibile specificare una o più password da provare (immessa manualmente o in un file caricato) ed è possibile specificare uno o più utenti.</span><span class="sxs-lookup"><span data-stu-id="82fcf-235">For the dictionary attack, you can specify one or many passwords to try (manually entered or in an uploaded file), and you can specify one or many users.</span></span>

- <span data-ttu-id="82fcf-236">**Attacco spray** per la password: un attacco *spray* per la password utilizza la stessa password accuratamente considerata rispetto A un elenco di account utente (una password per molti account).</span><span class="sxs-lookup"><span data-stu-id="82fcf-236">**Password spray attack**: A *password spray* attack uses the same carefully considered password against a list of user accounts (one password against many accounts).</span></span> <span data-ttu-id="82fcf-237">Gli attacchi spray per la password sono più difficili da rilevare rispetto agli attacchi delle password per la forza bruta (la probabilità che il successo aumenti quando un utente malintenzionato cerca una password tra decine o centinaia di account senza il rischio di inciampare nel blocco della password errata dell'utente).</span><span class="sxs-lookup"><span data-stu-id="82fcf-237">Password spray attacks are harder to detect than brute force password attacks (the probability of success increases when an attacker tries one password across dozens or hundreds of accounts without the risk of tripping the user's incorrect password lock-out).</span></span>

  <span data-ttu-id="82fcf-238">Per l'attacco spray per la password, è possibile specificare solo una password da provare ed è possibile specificare uno o più utenti.</span><span class="sxs-lookup"><span data-stu-id="82fcf-238">For the password spray attack, you can only specify one password to try, and you can specify one or many users.</span></span>

> [!NOTE]
> <span data-ttu-id="82fcf-239">Gli attacchi tramite password in Attack Simulator passano il nome utente e le richieste di autenticazione di base delle password a un endpoint, in modo che funzionino anche con gli altri metodi (AD FS, sincronizzazione hash delle password, pass-through, PingFederate e così via).</span><span class="sxs-lookup"><span data-stu-id="82fcf-239">The password attacks in Attack Simulator pass username and password Basic auth requests to an endpoint, so they also work with other authentication methods (AD FS, password hash sync, pass-through, PingFederate, etc.).</span></span> <span data-ttu-id="82fcf-240">Per gli utenti che dispongono di un Master abilitato, anche se l'attacco della password tenta la password effettiva, il tentativo si registrerà sempre come un errore (in altre parole, gli utenti dell'AMF non verranno mai visualizzati nel conteggio dei **tentativi riusciti** della campagna).</span><span class="sxs-lookup"><span data-stu-id="82fcf-240">For users that have MFA enabled, even if the password attack tries their actual password, the attempt will always register as a failure (in other words, MFA users will never appear in the **Successful attempts** count of the campaign).</span></span> <span data-ttu-id="82fcf-241">Questo è il risultato previsto.</span><span class="sxs-lookup"><span data-stu-id="82fcf-241">This is the expected result.</span></span> <span data-ttu-id="82fcf-242">L'AMF è un metodo principale che consente di proteggere gli attacchi delle password.</span><span class="sxs-lookup"><span data-stu-id="82fcf-242">MFA is a primary method to help protect against password attacks.</span></span>

### <a name="create-and-launch-a-password-attack-campaign"></a><span data-ttu-id="82fcf-243">Creare e avviare una campagna di attacco tramite password</span><span class="sxs-lookup"><span data-stu-id="82fcf-243">Create and launch a password attack campaign</span></span>

1. <span data-ttu-id="82fcf-244">Nel centro sicurezza & conformità, accedere a **Threat Management** \> **Attack Simulator**.</span><span class="sxs-lookup"><span data-stu-id="82fcf-244">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="82fcf-245">Nella pagina **simula attacchi** fare una delle selezioni seguenti in base al tipo di campagna che si desidera creare:</span><span class="sxs-lookup"><span data-stu-id="82fcf-245">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="82fcf-246">Nella sezione **password forza bruta (attacco dizionario)** fare clic su **Avvia attacco** o fare clic su Attack **Details** \> **Launch Attack**.</span><span class="sxs-lookup"><span data-stu-id="82fcf-246">In the **Brute Force Password (Dictionary Attack)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="82fcf-247">nella sezione **attacco spray password** fare clic su **Launch Attack** o su Attack **Details** \> **Launch Attack**.</span><span class="sxs-lookup"><span data-stu-id="82fcf-247">in the **Password spray attack** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="82fcf-248">La procedura guidata **Configura attacco password** viene avviata in un nuovo riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="82fcf-248">The **Configure Password Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="82fcf-249">Nel passaggio **iniziale** , immettere un nome visualizzato univoco per la campagna e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="82fcf-249">In the **Start** step, enter a unique display name for the campaign, and then click **Next**.</span></span>

4. <span data-ttu-id="82fcf-250">Nel passaggio **degli utenti di destinazione** , eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="82fcf-250">In the **Target users** step, do one of the following steps:</span></span>

   - <span data-ttu-id="82fcf-251">Fare **clic su Rubrica per** selezionare i destinatari (utenti o gruppi) per la campagna.</span><span class="sxs-lookup"><span data-stu-id="82fcf-251">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="82fcf-252">Ogni destinatario di destinazione deve disporre di una cassetta postale di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="82fcf-252">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="82fcf-253">Se si fa clic su **Filtra** e **applica** senza immettere un criterio di ricerca, tutti i destinatari vengono restituiti e aggiunti alla campagna.</span><span class="sxs-lookup"><span data-stu-id="82fcf-253">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="82fcf-254">Fare clic su **Importa** quindi **importazione file** per importare un valore separato da virgole (CSV) o un file di indirizzi di posta elettronica separato da una riga.</span><span class="sxs-lookup"><span data-stu-id="82fcf-254">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="82fcf-255">Ogni riga deve contenere l'indirizzo di posta elettronica del destinatario.</span><span class="sxs-lookup"><span data-stu-id="82fcf-255">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="82fcf-256">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="82fcf-256">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="82fcf-257">Nel passaggio **scegliere le impostazioni di attacco** scegliere le operazioni da eseguire in base al tipo di campagna:</span><span class="sxs-lookup"><span data-stu-id="82fcf-257">In the **Choose attack settings** step, choose what to do based on the campaign type:</span></span>

   - <span data-ttu-id="82fcf-258">**Password forza bruta (attacco dizionario)**: eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="82fcf-258">**Brute Force Password (Dictionary Attack)**: Do either of the following steps:</span></span>

     - <span data-ttu-id="82fcf-259">**Immettere le password manualmente**: nella casella **premere INVIO per aggiungere una password** digitare una password e quindi premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="82fcf-259">**Enter passwords manually**: In the **Press enter to add a password** box, type a password and then press ENTER.</span></span> <span data-ttu-id="82fcf-260">Ripetere questo passaggio tutte le volte necessarie.</span><span class="sxs-lookup"><span data-stu-id="82fcf-260">Repeat this step as many times as necessary.</span></span>

     - <span data-ttu-id="82fcf-261">**Caricare password da un file di dizionario**: fare clic su **carica** per importare un file di testo esistente che contiene una password su ogni riga e un'ultima riga vuota.</span><span class="sxs-lookup"><span data-stu-id="82fcf-261">**Upload passwords from a dictionary file**: Click **Upload** to import an existing text file that contains one password on each line and a blank last line.</span></span> <span data-ttu-id="82fcf-262">Il file di testo deve avere una dimensione di 10 MB o inferiore e non può contenere più di 30000 password.</span><span class="sxs-lookup"><span data-stu-id="82fcf-262">The text file must be 10 MB or less in size, and can't contain more than 30000 passwords.</span></span>

   - <span data-ttu-id="82fcf-263">**Attacco spray** per la password: nelle **password da utilizzare nella casella attacco** , immettere una password.</span><span class="sxs-lookup"><span data-stu-id="82fcf-263">**Password spray attack**: In **The password(s) to use in the attack** box, enter one password.</span></span>

   <span data-ttu-id="82fcf-264">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="82fcf-264">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="82fcf-265">Nel passaggio **conferma** fare clic su **fine** per avviare la campagna.</span><span class="sxs-lookup"><span data-stu-id="82fcf-265">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="82fcf-266">Le password specificate sono state provate per gli utenti specificati.</span><span class="sxs-lookup"><span data-stu-id="82fcf-266">The passwords you specified are tried on users you specified.</span></span>

## <a name="view-campaign-results"></a><span data-ttu-id="82fcf-267">Visualizzare i risultati della campagna</span><span class="sxs-lookup"><span data-stu-id="82fcf-267">View campaign results</span></span>

<span data-ttu-id="82fcf-268">Dopo aver avviato una campagna, è possibile controllare lo stato e i risultati della pagina principale degli **attacchi simulati** .</span><span class="sxs-lookup"><span data-stu-id="82fcf-268">After you launch a campaign, you can check the progress and results on the main **Simulate attacks** page.</span></span>

<span data-ttu-id="82fcf-269">Le campagne attive visualizzeranno una barra di stato, un valore percentuale completato e il numero "(utenti completati) di (utenti totali)".</span><span class="sxs-lookup"><span data-stu-id="82fcf-269">Active campaigns will show a status bar, a completed percentage value and "(completed users) of (total users)" count.</span></span> <span data-ttu-id="82fcf-270">Se si fa clic sul pulsante **Aggiorna** , verrà aggiornato lo stato di avanzamento di qualsiasi campagna attiva.</span><span class="sxs-lookup"><span data-stu-id="82fcf-270">Clicking the **Refresh** button will update the progress of any active campaigns.</span></span> <span data-ttu-id="82fcf-271">È inoltre possibile fare clic su **termina** per arrestare una campagna attiva.</span><span class="sxs-lookup"><span data-stu-id="82fcf-271">You can also click **Terminate** to stop an active campaign.</span></span>

<span data-ttu-id="82fcf-272">Al termine della campagna, lo stato cambia in **attacco completato**.</span><span class="sxs-lookup"><span data-stu-id="82fcf-272">When the campaign is finished, the status changes to **Attack completed**.</span></span> <span data-ttu-id="82fcf-273">È possibile visualizzare i risultati della campagna eseguendo una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="82fcf-273">You can view the results of the campaign by doing either of the following actions:</span></span>

- <span data-ttu-id="82fcf-274">Nella pagina simulazione principale degli **attacchi** , fare clic su **Visualizza report** sotto il nome della campagna.</span><span class="sxs-lookup"><span data-stu-id="82fcf-274">On the main **Simulate attacks** page, click **View Report** under the name of the campaign.</span></span>

- <span data-ttu-id="82fcf-275">Nella pagina simulazione principale degli **attacchi** , fare clic su **attacco dettagli** nella sezione relativa al tipo di attacco.</span><span class="sxs-lookup"><span data-stu-id="82fcf-275">On the main **Simulate attacks** page, click **Attack Details** in the section for the type of attack.</span></span> <span data-ttu-id="82fcf-276">Nella pagina dei **Dettagli sull'attacco** che viene visualizzata, selezionare la campagna nella sezione cronologia degli **attacchi** .</span><span class="sxs-lookup"><span data-stu-id="82fcf-276">On the **Attack details** page that opens, select the campaign in the **Attack History** section.</span></span>

<span data-ttu-id="82fcf-277">Una delle azioni precedenti consentirà di utilizzare una pagina denominata **Dettagli attacco**.</span><span class="sxs-lookup"><span data-stu-id="82fcf-277">Either of the previous actions will take you to a page named **Attack details**.</span></span> <span data-ttu-id="82fcf-278">Le informazioni disponibili in questa pagina per ogni tipo di campagna sono descritte nelle sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="82fcf-278">The information that's available on this page for each type of campaign is described in the following sections.</span></span>

### <a name="spear-phishing-credentials-harvest-campaign-results"></a><span data-ttu-id="82fcf-279">Risultati della campagna Spear phishing (Harvest Credentials)</span><span class="sxs-lookup"><span data-stu-id="82fcf-279">Spear Phishing (Credentials Harvest) campaign results</span></span>

<span data-ttu-id="82fcf-280">Le informazioni seguenti sono disponibili nella pagina dei **Dettagli sull'attacco** per ogni campagna:</span><span class="sxs-lookup"><span data-stu-id="82fcf-280">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="82fcf-281">Durata (data/ora di inizio e data/ora di fine) della campagna.</span><span class="sxs-lookup"><span data-stu-id="82fcf-281">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="82fcf-282">**Totale utenti designati**</span><span class="sxs-lookup"><span data-stu-id="82fcf-282">**Total users targeted**</span></span>

- <span data-ttu-id="82fcf-283">**Tentativi riusciti**: il numero di utenti che hanno fatto clic sul collegamento **e** hanno immesso le proprie credenziali (*qualsiasi* nome utente e valore password).</span><span class="sxs-lookup"><span data-stu-id="82fcf-283">**Successful attempts**: The number of users who clicked the link **and** entered their credentials (*any* username and password value).</span></span>

- <span data-ttu-id="82fcf-284">**Tasso di successo globale**: percentuale calcolata con **esito positivo dei tentativi**  /  **totali degli utenti mirati**.</span><span class="sxs-lookup"><span data-stu-id="82fcf-284">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="82fcf-285">Più **veloce fare clic su**: quanto tempo è stato necessario per il primo utente per fare clic sul collegamento dopo aver avviato la campagna.</span><span class="sxs-lookup"><span data-stu-id="82fcf-285">**Fastest Click**: How long it took the first user to click the link after you launched the campaign.</span></span>

- <span data-ttu-id="82fcf-286">**Media clic**: la somma del tempo impiegato da tutti per fare clic sul collegamento diviso per il numero di utenti che hanno fatto clic sul collegamento.</span><span class="sxs-lookup"><span data-stu-id="82fcf-286">**Average Click**: The sum of how long it took everyone to click the link divided by the number of users who clicked the link.</span></span>

- <span data-ttu-id="82fcf-287">**Fare clic su velocità di successo**: percentuale calcolata da (numero di utenti che hanno fatto clic sul collegamento)/ **Totale utenti designati**.</span><span class="sxs-lookup"><span data-stu-id="82fcf-287">**Click Success Rate**: A percentage that's calculated by (number of users who clicked the link) / **Total users targeted**.</span></span>

- <span data-ttu-id="82fcf-288">**Credenziali più veloci**: il tempo impiegato dal primo utente per immettere le credenziali dopo aver avviato la campagna.</span><span class="sxs-lookup"><span data-stu-id="82fcf-288">**Fastest Credentials**: How long it took the first user to enter their credentials after you launched the campaign.</span></span>

- <span data-ttu-id="82fcf-289">**Credenziali medie**: somma del tempo impiegato da tutti per immettere le proprie credenziali diviso per il numero di utenti che hanno immesso le proprie credenziali.</span><span class="sxs-lookup"><span data-stu-id="82fcf-289">**Average Credentials**: The sum of how long it took everyone to enter their credentials divided by the number of users who entered their credentials.</span></span>

- <span data-ttu-id="82fcf-290">**Tasso di successo della credenziale**: percentuale calcolata da (numero di utenti che hanno immesso le proprie credenziali)/ **Totale utenti designati**.</span><span class="sxs-lookup"><span data-stu-id="82fcf-290">**Credential Success Rate**: A percentage that's calculated by (number of users who entered their credentials) / **Total users targeted**.</span></span>

- <span data-ttu-id="82fcf-291">Grafico a barre che Visualizza il **collegamento selezionato** e i numeri di **credenziale forniti** al giorno.</span><span class="sxs-lookup"><span data-stu-id="82fcf-291">A bar graph that shows the **Link clicked** and **Credential supplied** numbers per day.</span></span>

- <span data-ttu-id="82fcf-292">Grafico a cerchio che Visualizza il **collegamento fatto clic**, **credenziali fornite** e **Nessuna** percentuale per la campagna.</span><span class="sxs-lookup"><span data-stu-id="82fcf-292">A circle graph that shows the **Link clicked**, **Credential supplied**, and **None** percentages for the campaign.</span></span>

- <span data-ttu-id="82fcf-293">Nella sezione **utenti compromessi** sono elencati i dettagli degli utenti che hanno fatto clic sul collegamento:</span><span class="sxs-lookup"><span data-stu-id="82fcf-293">The **Compromised Users** section lists the details of the users who clicked the link:</span></span>

  - <span data-ttu-id="82fcf-294">L'indirizzo di posta elettronica dell'utente</span><span class="sxs-lookup"><span data-stu-id="82fcf-294">The user's email address</span></span>

  - <span data-ttu-id="82fcf-295">La data e l'ora in cui si è fatto clic sul collegamento.</span><span class="sxs-lookup"><span data-stu-id="82fcf-295">The date/time when they clicked the link.</span></span>

  - <span data-ttu-id="82fcf-296">L'indirizzo IP del client.</span><span class="sxs-lookup"><span data-stu-id="82fcf-296">The client IP address.</span></span>

  - <span data-ttu-id="82fcf-297">Dettagli sulla versione dell'utente di Windows e del Web browser.</span><span class="sxs-lookup"><span data-stu-id="82fcf-297">Details about the user's version of Windows and web browser.</span></span>

  <span data-ttu-id="82fcf-298">È possibile fare clic su **Esporta** per esportare i risultati in un file CSV.</span><span class="sxs-lookup"><span data-stu-id="82fcf-298">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="spear-phishing-attachment-campaign-results"></a><span data-ttu-id="82fcf-299">Risultati della campagna di phishing (allegato) Spear</span><span class="sxs-lookup"><span data-stu-id="82fcf-299">Spear Phishing (Attachment) campaign results</span></span>

<span data-ttu-id="82fcf-300">Le informazioni seguenti sono disponibili nella pagina dei **Dettagli sull'attacco** per ogni campagna:</span><span class="sxs-lookup"><span data-stu-id="82fcf-300">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="82fcf-301">Durata (data/ora di inizio e data/ora di fine) della campagna.</span><span class="sxs-lookup"><span data-stu-id="82fcf-301">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="82fcf-302">**Totale utenti designati**</span><span class="sxs-lookup"><span data-stu-id="82fcf-302">**Total users targeted**</span></span>

- <span data-ttu-id="82fcf-303">**Tentativi riusciti**: il numero di utenti che hanno aperto o scaricato e aperto l'allegato (l'anteprima non conta).</span><span class="sxs-lookup"><span data-stu-id="82fcf-303">**Successful attempts**: The number of users who opened or downloaded and opened the attachment (preview doesn't count).</span></span>

- <span data-ttu-id="82fcf-304">**Tasso di successo globale**: percentuale calcolata con **esito positivo dei tentativi**  /  **totali degli utenti mirati**.</span><span class="sxs-lookup"><span data-stu-id="82fcf-304">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="82fcf-305">**Intervallo di tempo di apertura più rapido**: il tempo impiegato dal primo utente per aprire l'allegato dopo aver avviato la campagna.</span><span class="sxs-lookup"><span data-stu-id="82fcf-305">**Fastest attachment open time**: How long it took the first user to open the attachment after you launched the campaign.</span></span>

- <span data-ttu-id="82fcf-306">**Intervallo di tempo di apertura medio**: la somma di quanto tempo ha impiegato tutti per aprire l'allegato diviso per il numero di utenti che hanno aperto l'allegato.</span><span class="sxs-lookup"><span data-stu-id="82fcf-306">**Average attachment open time**: The sum of how long it took everyone to open the attachment divided by the number of users who opened the attachment.</span></span>

- <span data-ttu-id="82fcf-307">**Tasso di successo Open Attachment**: percentuale calcolata da (numero di utenti che hanno aperto l'allegato)/ **Totale utenti designati**.</span><span class="sxs-lookup"><span data-stu-id="82fcf-307">**Attachment open success rate**: A percentage that's calculated by (number of users who opened the attachment) / **Total users targeted**.</span></span>

### <a name="brute-force-password-dictionary-attack-campaign-results"></a><span data-ttu-id="82fcf-308">Risultati della campagna password forza bruta (attacco dizionario)</span><span class="sxs-lookup"><span data-stu-id="82fcf-308">Brute Force Password (Dictionary Attack) campaign results</span></span>

<span data-ttu-id="82fcf-309">Le informazioni seguenti sono disponibili nella pagina dei **Dettagli sull'attacco** per ogni campagna:</span><span class="sxs-lookup"><span data-stu-id="82fcf-309">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="82fcf-310">Durata (data/ora di inizio e data/ora di fine) della campagna.</span><span class="sxs-lookup"><span data-stu-id="82fcf-310">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="82fcf-311">**Totale utenti designati**</span><span class="sxs-lookup"><span data-stu-id="82fcf-311">**Total users targeted**</span></span>

- <span data-ttu-id="82fcf-312">**Tentativi riusciti**: il numero di utenti che hanno trovato l'utilizzo di una delle password specificate.</span><span class="sxs-lookup"><span data-stu-id="82fcf-312">**Successful attempts**: The number of users who were found to be using one of the specified passwords.</span></span>

- <span data-ttu-id="82fcf-313">**Tasso di successo globale**: percentuale calcolata con **esito positivo dei tentativi**  /  **totali degli utenti mirati**.</span><span class="sxs-lookup"><span data-stu-id="82fcf-313">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="82fcf-314">La sezione **utenti compromessi** elenca gli indirizzi di posta elettronica degli utenti coinvolti.</span><span class="sxs-lookup"><span data-stu-id="82fcf-314">The **Compromised Users** section lists the email addresses of the affected users.</span></span> <span data-ttu-id="82fcf-315">È possibile fare clic su **Esporta** per esportare i risultati in un file CSV.</span><span class="sxs-lookup"><span data-stu-id="82fcf-315">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="password-spray-attack-campaign-results"></a><span data-ttu-id="82fcf-316">Risultati della campagna di attacco a spruzzo di password</span><span class="sxs-lookup"><span data-stu-id="82fcf-316">Password spray attack campaign results</span></span>

<span data-ttu-id="82fcf-317">Le informazioni seguenti sono disponibili nella pagina dei **Dettagli sull'attacco** per ogni campagna:</span><span class="sxs-lookup"><span data-stu-id="82fcf-317">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="82fcf-318">Durata (data/ora di inizio e data/ora di fine) della campagna.</span><span class="sxs-lookup"><span data-stu-id="82fcf-318">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="82fcf-319">**Totale utenti designati**</span><span class="sxs-lookup"><span data-stu-id="82fcf-319">**Total users targeted**</span></span>

- <span data-ttu-id="82fcf-320">**Tentativi riusciti**: il numero di utenti che sono stati trovati a utilizzare la password specificata.</span><span class="sxs-lookup"><span data-stu-id="82fcf-320">**Successful attempts**: The number of users who were found to be using the specified password.</span></span>

- <span data-ttu-id="82fcf-321">**Tasso di successo globale**: percentuale calcolata con **esito positivo dei tentativi**  /  **totali degli utenti mirati**.</span><span class="sxs-lookup"><span data-stu-id="82fcf-321">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>
