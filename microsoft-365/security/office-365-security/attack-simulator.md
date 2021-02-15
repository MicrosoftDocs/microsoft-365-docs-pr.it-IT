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
ms.openlocfilehash: 9d3d55c17e5d77ee18bd822899fea2f64136e1a3
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233601"
---
# <a name="attack-simulator-in-microsoft-defender-for-office-365"></a><span data-ttu-id="15fab-103">Simulatore di attacchi in Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="15fab-103">Attack Simulator in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="15fab-104">**Si applica a** [Microsoft Defender per Office 365 piano 2](https://go.microsoft.com/fwlink/?linkid=2148715)</span><span class="sxs-lookup"><span data-stu-id="15fab-104">**Applies to** [Microsoft Defender for Office 365 plan 2](https://go.microsoft.com/fwlink/?linkid=2148715)</span></span>

<span data-ttu-id="15fab-105">Se l'organizzazione dispone di Microsoft Defender per Office 365 Piano 2, che include funzionalità di analisi e risposta alle [minacce,](office-365-ti.md)è possibile utilizzare il simulatore di attacchi nel Centro sicurezza & e conformità per eseguire scenari di attacco realistici nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="15fab-105">If your organization has Microsoft Defender for Office 365 Plan 2, which includes [Threat Investigation and Response capabilities](office-365-ti.md), you can use Attack Simulator in the Security & Compliance Center to run realistic attack scenarios in your organization.</span></span> <span data-ttu-id="15fab-106">Questi attacchi simulati consentono di identificare e individuare gli utenti vulnerabili prima che un attacco reale influisca sulla linea di fondo.</span><span class="sxs-lookup"><span data-stu-id="15fab-106">These simulated attacks can help you identify and find vulnerable users before a real attack impacts your bottom line.</span></span> <span data-ttu-id="15fab-107">Leggi questo articolo per altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="15fab-107">Read this article to learn more.</span></span>

> [!NOTE]
> <span data-ttu-id="15fab-108">L'esperienza del simulatore di attacchi v1 è stata passata alla modalità di sola lettura e sostituita dal training del simulatore di attacco descritto in Introduzione all'uso della formazione per la simulazione [degli attacchi.](attack-simulation-training-get-started.md)</span><span class="sxs-lookup"><span data-stu-id="15fab-108">Attack Simulator v1 experience has been switched to read-only mode and replaced by Attack simulator training that's described in [Get started using Attack simulation training](attack-simulation-training-get-started.md).</span></span>
> <span data-ttu-id="15fab-109">La possibilità di avviare nuove simulazioni da questo sito è stata disabilitata.</span><span class="sxs-lookup"><span data-stu-id="15fab-109">The ability to launch new simulations from this site has been disabled.</span></span> <span data-ttu-id="15fab-110">Tuttavia, è comunque possibile accedere ai report per le simulazioni eseguite per un periodo di 90 giorni dal 24 gennaio 2021.</span><span class="sxs-lookup"><span data-stu-id="15fab-110">However, you can still access reports for simulations run for a period of 90 days from January 24, 2021.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="15fab-111">Che cosa è necessario sapere prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="15fab-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="15fab-112">Per aprire il Centro sicurezza e conformità, passare a <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="15fab-112">To open the Security & Compliance Center, go to <https://protection.office.com/>.</span></span> <span data-ttu-id="15fab-113">Il simulatore  di attacco è disponibile nel \> **simulatore di attacco per la gestione delle minacce.**</span><span class="sxs-lookup"><span data-stu-id="15fab-113">Attack simulator is available at **Threat management** \> **Attack simulator**.</span></span> <span data-ttu-id="15fab-114">Vai direttamente al simulatore di attacco, apri <https://protection.office.com/attacksimulator> .</span><span class="sxs-lookup"><span data-stu-id="15fab-114">Go go directly to attack simulator, open <https://protection.office.com/attacksimulator>.</span></span>

- <span data-ttu-id="15fab-115">Per ulteriori informazioni sulla disponibilità del simulatore di attacchi tra diversi abbonamenti a Microsoft 365, vedere Descrizione del servizio [Microsoft Defender per Office 365.](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)</span><span class="sxs-lookup"><span data-stu-id="15fab-115">For more information about the availability of Attack Simulator across different Microsoft 365 subscriptions, see [Microsoft Defender for Office 365 service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

- <span data-ttu-id="15fab-116">È necessario essere membri dei gruppi di ruoli **Gestione organizzazione** o **Amministratore** sicurezza.</span><span class="sxs-lookup"><span data-stu-id="15fab-116">You need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="15fab-117">Per altre informazioni sui gruppi di ruoli nel Centro sicurezza e conformità, vedere [Autorizzazioni nel Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="15fab-117">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="15fab-118">Il tuo account deve essere configurato per l'autenticazione a più fattori (MFA) per creare e gestire campagne in Simulatore di attacchi.</span><span class="sxs-lookup"><span data-stu-id="15fab-118">Your account needs to be configured for multi-factor authentication (MFA) to create and manage campaigns in Attack Simulator.</span></span> <span data-ttu-id="15fab-119">Per istruzioni, vedere [Configurare l'autenticazione a più fattori.](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication)</span><span class="sxs-lookup"><span data-stu-id="15fab-119">For instructions, see [Set up multi-factor authentication](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication).</span></span>

- <span data-ttu-id="15fab-120">Le campagne di phishing raccoglieranno ed eelaborare gli eventi per 30 giorni.</span><span class="sxs-lookup"><span data-stu-id="15fab-120">Phishing campaigns will collect and process events for 30 days.</span></span> <span data-ttu-id="15fab-121">I dati cronologici della campagna saranno disponibili fino a 90 giorni dopo l'avvio della campagna.</span><span class="sxs-lookup"><span data-stu-id="15fab-121">Historical campaign data will be available for up to 90 days after you launch the campaign.</span></span>

- <span data-ttu-id="15fab-122">I dati correlati alla simulazione e alla formazione degli attacchi vengono archiviati con altri dati dei clienti per i servizi di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="15fab-122">Attack simulation and training related data is stored with other customer data for Microsoft 365 services.</span></span> <span data-ttu-id="15fab-123">Per ulteriori informazioni, vedere [Percorsi dei dati di Microsoft 365.](/microsoft-365/enterprise/o365-data-locations)</span><span class="sxs-lookup"><span data-stu-id="15fab-123">For more information see [Microsoft 365 data locations](/microsoft-365/enterprise/o365-data-locations).</span></span>

- <span data-ttu-id="15fab-124">Non sono disponibili cmdlet di PowerShell corrispondenti per il simulatore di attacchi.</span><span class="sxs-lookup"><span data-stu-id="15fab-124">There are no corresponding PowerShell cmdlets for Attack Simulator.</span></span>

## <a name="spear-phishing-campaigns"></a><span data-ttu-id="15fab-125">Campagne di phishing con phishing</span><span class="sxs-lookup"><span data-stu-id="15fab-125">Spear phishing campaigns</span></span>

<span data-ttu-id="15fab-126">*Il phishing* è un termine generico per gli attacchi di posta elettronica che tentano di rubare informazioni riservate nei messaggi che sembrano essere provenienti da mittenti legittimi o attendibili.</span><span class="sxs-lookup"><span data-stu-id="15fab-126">*Phishing* is a generic term for email attacks that try to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="15fab-127">*Il phishing* di phishing mirato è un attacco di phishing mirato che usa contenuti mirati e personalizzati appositamente personalizzati per i destinatari di destinazione (in genere, dopo la ricognizione sui destinatari da parte dell'autore dell'attacco).</span><span class="sxs-lookup"><span data-stu-id="15fab-127">*Spear phishing* is a targeted phishing attack that uses focused and customized content that's specifically tailored to the targeted recipients (typically, after reconnaissance on the recipients by the attacker).</span></span>

<span data-ttu-id="15fab-128">Nel simulatore di attacchi sono disponibili due diversi tipi di campagne di phishing:</span><span class="sxs-lookup"><span data-stu-id="15fab-128">In Attack Simulator, two different types of spear phishing campaigns are available:</span></span>

- <span data-ttu-id="15fab-129">**Spear phishing (raccolta di credenziali):** l'attacco tenta di convincere i destinatari a fare clic su un URL nel messaggio.</span><span class="sxs-lookup"><span data-stu-id="15fab-129">**Spear phishing (credentials harvest)**: The attack tries to convince the recipients to click a URL in the message.</span></span> <span data-ttu-id="15fab-130">Se fa clic sul collegamento, viene richiesto di immettere le proprie credenziali.</span><span class="sxs-lookup"><span data-stu-id="15fab-130">If they click the link, they're asked to enter their credentials.</span></span> <span data-ttu-id="15fab-131">In caso contrario, vengono portati in una delle posizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="15fab-131">If they do, they're taken to one of the following locations:</span></span>

  - <span data-ttu-id="15fab-132">Una pagina predefinita che spiega che si tratta di un semplice test e fornisce suggerimenti per il riconoscimento dei messaggi di phishing.</span><span class="sxs-lookup"><span data-stu-id="15fab-132">A default page that explains that this was a just a test, and gives tips for recognizing phishing messages.</span></span>

    ![Cosa viene visualizzato dagli utenti se fanno clic sul collegamento di phishing e immettono le proprie credenziali](../../media/attack-simulator-phishing-result.png)

  - <span data-ttu-id="15fab-134">Una pagina personalizzata (URL) specificata dall'utente.</span><span class="sxs-lookup"><span data-stu-id="15fab-134">A custom page (URL) that you specify.</span></span>

- <span data-ttu-id="15fab-135">**Spear phishing (allegato):** l'attacco tenta di convincere i destinatari ad aprire un allegato .docx o .pdf nel messaggio.</span><span class="sxs-lookup"><span data-stu-id="15fab-135">**Spear phishing (attachment)**: The attack tries to convince the recipients to open a .docx or .pdf attachment in the message.</span></span> <span data-ttu-id="15fab-136">L'allegato contiene lo stesso contenuto del collegamento di phishing predefinito, ma la prima frase inizia con " , il messaggio viene visualizzato come un messaggio di posta elettronica recente \<Display Name\> aperto...".</span><span class="sxs-lookup"><span data-stu-id="15fab-136">The attachment contains the same content from the default phishing link, but the first sentence starts with "\<Display Name\>, you are seeing this message as a recent email message you opened...".</span></span>

> [!NOTE]
> <span data-ttu-id="15fab-137">Attualmente, le campagne di spear phishing nel simulatore di attacchi non scadono.</span><span class="sxs-lookup"><span data-stu-id="15fab-137">Currently, spear phishing campaigns in Attack Simulator don't expire.</span></span>

### <a name="create-a-spear-phishing-campaign"></a><span data-ttu-id="15fab-138">Creare una campagna di phishing con phishing</span><span class="sxs-lookup"><span data-stu-id="15fab-138">Create a spear phishing campaign</span></span>

<span data-ttu-id="15fab-139">Una parte importante di qualsiasi campagna di phishing è l'aspetto del messaggio di posta elettronica inviato ai destinatari di destinazione.</span><span class="sxs-lookup"><span data-stu-id="15fab-139">An important part of any spear phishing campaign is the look and feel of the email message that's sent to the targeted recipients.</span></span> <span data-ttu-id="15fab-140">Per creare e configurare il messaggio di posta elettronica, sono disponibili le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="15fab-140">To create and configure the email message, you have these options:</span></span>

- <span data-ttu-id="15fab-141">**Usa un modello di posta elettronica predefinito:** sono disponibili due modelli predefiniti: **Evaso** e Aggiornamento **paghe.**</span><span class="sxs-lookup"><span data-stu-id="15fab-141">**Use a built-in email template**: Two built-in templates are available: **Prize Giveaway** and **Payroll Update**.</span></span> <span data-ttu-id="15fab-142">Puoi personalizzare ulteriormente alcune, tutte o nessuna delle proprietà di posta elettronica del modello quando crei e avvii la campagna.</span><span class="sxs-lookup"><span data-stu-id="15fab-142">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="15fab-143">**Creare un modello di** posta elettronica riutilizzabile: dopo aver creato e salvato il modello di posta elettronica, è possibile usarlo di nuovo nelle future campagne di phishing di phishing.</span><span class="sxs-lookup"><span data-stu-id="15fab-143">**Create a reusable email template**: After you create and save the email template, you can use it again in future spear phishing campaigns.</span></span> <span data-ttu-id="15fab-144">Puoi personalizzare ulteriormente alcune, tutte o nessuna delle proprietà di posta elettronica del modello quando crei e avvii la campagna.</span><span class="sxs-lookup"><span data-stu-id="15fab-144">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="15fab-145">**Creare il messaggio di posta elettronica nella** procedura guidata: è possibile creare il messaggio di posta elettronica direttamente nella procedura guidata durante la creazione e l'avvio della campagna di phishing.</span><span class="sxs-lookup"><span data-stu-id="15fab-145">**Create the email message in the wizard**: You can create the email message directly in the wizard as you create and launch the spear phishing campaign.</span></span>

#### <a name="step-1-optional-create-a-custom-email-template"></a><span data-ttu-id="15fab-146">Passaggio 1 (facoltativo): Creare un modello di posta elettronica personalizzato</span><span class="sxs-lookup"><span data-stu-id="15fab-146">Step 1 (Optional): Create a custom email template</span></span>

<span data-ttu-id="15fab-147">Se si desidera utilizzare uno dei modelli predefiniti o creare il messaggio di posta elettronica direttamente nella procedura guidata, è possibile ignorare questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="15fab-147">If you're going to use one of the built-in templates or create the email message directly in the wizard, you can skip this step.</span></span>

1. <span data-ttu-id="15fab-148">Nel Centro sicurezza & conformità passare a Simulatore di **attacchi di gestione** delle \> **minacce.**</span><span class="sxs-lookup"><span data-stu-id="15fab-148">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="15fab-149">Nella pagina **Simulate attacks** fare clic su Attack **Details** nelle sezioni Spear **Phishing (Credentials Harvest)** o **Spear Phishing (Attachment).**</span><span class="sxs-lookup"><span data-stu-id="15fab-149">On the **Simulate attacks** page, in either the **Spear Phishing (Credentials Harvest)** or **Spear Phishing (Attachment)** sections, click **Attack Details**.</span></span>

   <span data-ttu-id="15fab-150">Non importa dove si crea il modello.</span><span class="sxs-lookup"><span data-stu-id="15fab-150">It doesn't matter where you create the template.</span></span> <span data-ttu-id="15fab-151">Le opzioni disponibili nel modello sono le stesse per entrambi i tipi di attacchi di phishing.</span><span class="sxs-lookup"><span data-stu-id="15fab-151">The available options in the template are the same for both types of phishing attacks.</span></span>

3. <span data-ttu-id="15fab-152">Nella pagina **Dettagli attacco** visualizzata, nell'area Crea  modelli della sezione Modelli di **phishing** fare clic su **Nuovo modello.**</span><span class="sxs-lookup"><span data-stu-id="15fab-152">In the **Attack details** page that opens, in the **Phishing Templates** section, in the **Create Templates** area, click **New Template**.</span></span>

4. <span data-ttu-id="15fab-153">La **procedura guidata Configura modello di** phishing viene avviata in un nuovo riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="15fab-153">The **Configure Phishing Template** wizard starts in a new flyout.</span></span> <span data-ttu-id="15fab-154">Nel passaggio **iniziale** immettere un nome visualizzato univoco per il modello e quindi fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="15fab-154">In the **Start** step, enter a unique display name for the template, and then click **Next**.</span></span>

5. <span data-ttu-id="15fab-155">Nel passaggio **Configura dettagli posta elettronica** configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="15fab-155">In the **Configure email details** step, configure the following settings:</span></span>

   - <span data-ttu-id="15fab-156">**Da (nome):** nome visualizzato utilizzato per il mittente del messaggio.</span><span class="sxs-lookup"><span data-stu-id="15fab-156">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="15fab-157">**Da (posta elettronica):** indirizzo di posta elettronica del mittente.</span><span class="sxs-lookup"><span data-stu-id="15fab-157">**From (Email)**: The sender's email address.</span></span>

   - <span data-ttu-id="15fab-158">**URL del server di accesso** phishing: fare clic sull'elenco a discesa e selezionare uno degli URL disponibili nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="15fab-158">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="15fab-159">Questo è l'URL su cui gli utenti saranno tentati di fare clic.</span><span class="sxs-lookup"><span data-stu-id="15fab-159">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="15fab-160">Le opzioni disponibili sono:</span><span class="sxs-lookup"><span data-stu-id="15fab-160">The choices are:</span></span>

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
     > <span data-ttu-id="15fab-161">Un servizio di reputazione URL può identificare uno o più url come non sicuri.</span><span class="sxs-lookup"><span data-stu-id="15fab-161">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="15fab-162">Verificare la disponibilità dell'URL nei Web browser supportati prima di utilizzarlo in una campagna di phishing.</span><span class="sxs-lookup"><span data-stu-id="15fab-162">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span>

   - <span data-ttu-id="15fab-163">**URL pagina di destinazione personalizzata:** immettere una pagina di destinazione facoltativa in cui gli utenti vengono presi se fanno clic sul collegamento di phishing e immettono le proprie credenziali.</span><span class="sxs-lookup"><span data-stu-id="15fab-163">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="15fab-164">Questo collegamento sostituisce la pagina di destinazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="15fab-164">This link replaces the default landing page.</span></span> <span data-ttu-id="15fab-165">Ad esempio, se hai una formazione di sensibilizzazione interna, puoi specificare questo URL qui.</span><span class="sxs-lookup"><span data-stu-id="15fab-165">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="15fab-166">**Categoria:** attualmente questa impostazione non viene utilizzata (tutto ciò che immetti viene ignorato).</span><span class="sxs-lookup"><span data-stu-id="15fab-166">**Category**: Currently, this setting isn't used (anything you enter is ignored).</span></span>

   - <span data-ttu-id="15fab-167">**Oggetto:** campo **Oggetto** del messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="15fab-167">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="15fab-168">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="15fab-168">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="15fab-169">Nel passaggio **Componi messaggio di posta** elettronica, creare il corpo del messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="15fab-169">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="15fab-170">È possibile utilizzare la **scheda Posta** elettronica (un editor HTML avanzato) o la scheda **Origine** (codice HTML non elaborato).</span><span class="sxs-lookup"><span data-stu-id="15fab-170">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="15fab-171">La formattazione HTML può essere semplice o complessa come necessario.</span><span class="sxs-lookup"><span data-stu-id="15fab-171">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="15fab-172">È possibile inserire immagini e testo per migliorare la credibilità del messaggio nel client di posta elettronica del destinatario.</span><span class="sxs-lookup"><span data-stu-id="15fab-172">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="15fab-173">`${username}` inserisce il nome del destinatario.</span><span class="sxs-lookup"><span data-stu-id="15fab-173">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="15fab-174">`${loginserverurl}` inserisce il valore **URL del server** di accesso phishing del passaggio precedente.</span><span class="sxs-lookup"><span data-stu-id="15fab-174">`${loginserverurl}` inserts the **Phishing Login Server URL** value from the previous step.</span></span>

   <span data-ttu-id="15fab-175">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="15fab-175">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="15fab-176">Nel passaggio **Conferma** fare clic su **Fine.**</span><span class="sxs-lookup"><span data-stu-id="15fab-176">In the **Confirm** step, click **Finish**.</span></span>

#### <a name="step-2-create-and-launch-the-spear-phishing-campaign"></a><span data-ttu-id="15fab-177">Passaggio 2: creare e avviare la campagna di phishing con phishing</span><span class="sxs-lookup"><span data-stu-id="15fab-177">Step 2: Create and launch the spear phishing campaign</span></span>

1. <span data-ttu-id="15fab-178">Nel Centro sicurezza & conformità passare a Simulatore di **attacchi di gestione** delle \> **minacce.**</span><span class="sxs-lookup"><span data-stu-id="15fab-178">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="15fab-179">Nella pagina **Simula attacchi** effettuare una delle seguenti selezioni in base al tipo di campagna che si desidera creare:</span><span class="sxs-lookup"><span data-stu-id="15fab-179">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="15fab-180">Nella sezione **Spear Phishing (Credentials Harvest)** fare clic su **Launch Attack** o su **Attack Details** \> **Launch Attack.**</span><span class="sxs-lookup"><span data-stu-id="15fab-180">In the **Spear Phishing (Credentials Harvest)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="15fab-181">Nella sezione **Spear Phishing (allegato),** fare clic su **Launch Attack** o su **Attack Details** \> **Launch Attack.**</span><span class="sxs-lookup"><span data-stu-id="15fab-181">In the **Spear Phishing (Attachment)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="15fab-182">La **procedura guidata Configura attacco di phishing** viene avviata in un nuovo riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="15fab-182">The **Configure Phishing Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="15fab-183">Nel passaggio **Start** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="15fab-183">In the **Start** step, do one of the following steps:</span></span>

   - <span data-ttu-id="15fab-184">Nella casella **Nome** immettere un nome visualizzato univoco per la campagna.</span><span class="sxs-lookup"><span data-stu-id="15fab-184">In the **Name** box, enter a unique display name for the campaign.</span></span> <span data-ttu-id="15fab-185">Non fare clic su **Usa modello** perché il messaggio di posta elettronica verrà creato più avanti nella procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="15fab-185">Don't click **Use Template**, because you'll create the email message later in the wizard.</span></span>

   - <span data-ttu-id="15fab-186">Fare **clic su Usa** modello e selezionare un modello di posta elettronica predefinito o personalizzato.</span><span class="sxs-lookup"><span data-stu-id="15fab-186">Click **Use Template** and select a built-in or custom email template.</span></span> <span data-ttu-id="15fab-187">Dopo aver selezionato il modello, la **casella Nome** viene compilata automaticamente in base al modello, ma è possibile modificare il nome.</span><span class="sxs-lookup"><span data-stu-id="15fab-187">After you select the template, the **Name** box is automatically filled based on the template, but you can change the name.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="15fab-188">![Pagina iniziale phishing](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)</span><span class="sxs-lookup"><span data-stu-id="15fab-188">![Phishing Start Page](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)</span></span>

   <span data-ttu-id="15fab-189">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="15fab-189">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="15fab-190">Nel passaggio **Destinatari di** destinazione eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="15fab-190">In the **Target recipients** step, do one of the following steps:</span></span>

   - <span data-ttu-id="15fab-191">Fare **clic su Rubrica** per selezionare i destinatari (utenti o gruppi) per la campagna.</span><span class="sxs-lookup"><span data-stu-id="15fab-191">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="15fab-192">Ogni destinatario di destinazione deve disporre di una cassetta postale di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="15fab-192">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="15fab-193">Se si fa **clic su Filtro** e **Applica** senza immettere un criterio di ricerca, tutti i destinatari vengono restituiti e aggiunti alla campagna.</span><span class="sxs-lookup"><span data-stu-id="15fab-193">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="15fab-194">Fare **clic su** Importa e quindi **importa** file per importare un valore con valori delimitati da virgole (CSV) o un file di indirizzi di posta elettronica separati da riga.</span><span class="sxs-lookup"><span data-stu-id="15fab-194">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="15fab-195">Ogni riga deve contenere l'indirizzo di posta elettronica del destinatario.</span><span class="sxs-lookup"><span data-stu-id="15fab-195">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="15fab-196">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="15fab-196">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="15fab-197">Nel passaggio **Configura dettagli posta elettronica** configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="15fab-197">In the **Configure email details** step, configure the following settings:</span></span>

   <span data-ttu-id="15fab-198">Se è stato selezionato un modello nel **passaggio Start,** la maggior parte di questi valori è già configurata, ma è possibile modificarli.</span><span class="sxs-lookup"><span data-stu-id="15fab-198">If you selected a template in the **Start** step, most of these values are already configured, but you can change them.</span></span>

   - <span data-ttu-id="15fab-199">**Da (nome):** nome visualizzato utilizzato per il mittente del messaggio.</span><span class="sxs-lookup"><span data-stu-id="15fab-199">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="15fab-200">**Da (posta elettronica):** indirizzo di posta elettronica del mittente.</span><span class="sxs-lookup"><span data-stu-id="15fab-200">**From (Email)**: The sender's email address.</span></span> <span data-ttu-id="15fab-201">È possibile immettere un indirizzo di posta elettronica reale o falso dal dominio di posta elettronica dell'organizzazione oppure un indirizzo di posta elettronica esterno reale o falso.</span><span class="sxs-lookup"><span data-stu-id="15fab-201">You can enter a real or fake email address from your organization's email domain, or you can enter a real or fake external email address.</span></span> <span data-ttu-id="15fab-202">Un indirizzo di posta elettronica del mittente valido dell'organizzazione verrà effettivamente risolto nel client di posta elettronica del destinatario.</span><span class="sxs-lookup"><span data-stu-id="15fab-202">A valid sender email address from your organization will actually resolve in the recipient's email client.</span></span>

   - <span data-ttu-id="15fab-203">**URL del server di accesso** phishing: fare clic sull'elenco a discesa e selezionare uno degli URL disponibili nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="15fab-203">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="15fab-204">Questo è l'URL su cui gli utenti saranno tentati di fare clic.</span><span class="sxs-lookup"><span data-stu-id="15fab-204">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="15fab-205">Le opzioni disponibili sono:</span><span class="sxs-lookup"><span data-stu-id="15fab-205">The choices are:</span></span>

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
     > - <span data-ttu-id="15fab-206">Tutti gli URL sono intenzionalmente http, non https.</span><span class="sxs-lookup"><span data-stu-id="15fab-206">All of the URLs are intentionally http, not https.</span></span>
     >
     > - <span data-ttu-id="15fab-207">Un servizio di reputazione URL può identificare uno o più url come non sicuri.</span><span class="sxs-lookup"><span data-stu-id="15fab-207">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="15fab-208">Verificare la disponibilità dell'URL nei Web browser supportati prima di utilizzarlo in una campagna di phishing.</span><span class="sxs-lookup"><span data-stu-id="15fab-208">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span>
     >
     > - <span data-ttu-id="15fab-209">È necessario selezionare un URL.</span><span class="sxs-lookup"><span data-stu-id="15fab-209">You are required to select a URL.</span></span> <span data-ttu-id="15fab-210">Per **le campagne di phishing** (allegato), è possibile rimuovere il collegamento dal corpo del messaggio nel passaggio successivo (in caso contrario, il messaggio conterrà sia un **collegamento** che un allegato).</span><span class="sxs-lookup"><span data-stu-id="15fab-210">For **Spear Phishing (Attachment)** campaigns, you can remove the link from the body of the message in the next step (otherwise, the message will contain both a link **and** an attachment).</span></span>

   - <span data-ttu-id="15fab-211">**Tipo di allegato:** questa impostazione è disponibile solo nelle campagne **di phishing (allegato).**</span><span class="sxs-lookup"><span data-stu-id="15fab-211">**Attachment Type**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="15fab-212">Fare clic sull'elenco a discesa e selezionare **. DOCX** o **. PDF** dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="15fab-212">Click the drop down and select **.DOCX** or **.PDF** from the list.</span></span>

   - <span data-ttu-id="15fab-213">**Nome allegato:** questa impostazione è disponibile solo nelle campagne **di phishing (allegato).**</span><span class="sxs-lookup"><span data-stu-id="15fab-213">**Attachment Name**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="15fab-214">Immettere un nome di file per l'allegato .docx o .pdf.</span><span class="sxs-lookup"><span data-stu-id="15fab-214">Enter a filename for the .docx or .pdf attachment.</span></span>

   - <span data-ttu-id="15fab-215">**URL pagina di destinazione personalizzata:** immettere una pagina di destinazione facoltativa in cui gli utenti vengono presi se fanno clic sul collegamento di phishing e immettono le proprie credenziali.</span><span class="sxs-lookup"><span data-stu-id="15fab-215">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="15fab-216">Questo collegamento sostituisce la pagina di destinazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="15fab-216">This link replaces the default landing page.</span></span> <span data-ttu-id="15fab-217">Ad esempio, se hai una formazione di sensibilizzazione interna, puoi specificare questo URL qui.</span><span class="sxs-lookup"><span data-stu-id="15fab-217">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="15fab-218">**Oggetto:** campo **Oggetto** del messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="15fab-218">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="15fab-219">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="15fab-219">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="15fab-220">Nel passaggio **Componi messaggio di posta** elettronica, creare il corpo del messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="15fab-220">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="15fab-221">Se è stato selezionato un modello nel **passaggio Start,** il corpo del messaggio è già configurato, ma è possibile personalizzarlo.</span><span class="sxs-lookup"><span data-stu-id="15fab-221">If you selected a template in the **Start** step, the message body is already configured, but you can customize it.</span></span> <span data-ttu-id="15fab-222">È possibile utilizzare la **scheda Posta** elettronica (un editor HTML avanzato) o la scheda **Origine** (codice HTML non elaborato).</span><span class="sxs-lookup"><span data-stu-id="15fab-222">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="15fab-223">La formattazione HTML può essere semplice o complessa come necessario.</span><span class="sxs-lookup"><span data-stu-id="15fab-223">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="15fab-224">È possibile inserire immagini e testo per migliorare la credibilità del messaggio nel client di posta elettronica del destinatario.</span><span class="sxs-lookup"><span data-stu-id="15fab-224">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="15fab-225">`${username}` inserisce il nome del destinatario.</span><span class="sxs-lookup"><span data-stu-id="15fab-225">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="15fab-226">`${loginserverurl}`inserisce il valore **URL del server di accesso phishing.**</span><span class="sxs-lookup"><span data-stu-id="15fab-226">`${loginserverurl}` inserts the **Phishing Login Server URL** value.</span></span>

   <span data-ttu-id="15fab-227">Per le campagne di **spear phishing (allegato),** è necessario rimuovere il collegamento dal corpo  del messaggio (in caso contrario, il messaggio conterrà sia un collegamento che un allegato e i clic sul collegamento non vengono monitorati in una campagna allegato).</span><span class="sxs-lookup"><span data-stu-id="15fab-227">For **Spear Phishing (Attachment)** campaigns, you should remove the link from the body of the message (otherwise, the message will contain both a link **and** an attachment, and link clicks aren't tracked in an attachment campaign).</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="15fab-228">![Comporre il corpo del messaggio di posta elettronica](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)</span><span class="sxs-lookup"><span data-stu-id="15fab-228">![Compose Email Body](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)</span></span>

   <span data-ttu-id="15fab-229">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="15fab-229">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="15fab-230">Nel passaggio **Conferma** fare clic su **Fine** per avviare la campagna.</span><span class="sxs-lookup"><span data-stu-id="15fab-230">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="15fab-231">Il messaggio di phishing viene recapitato ai destinatari di destinazione.</span><span class="sxs-lookup"><span data-stu-id="15fab-231">The phishing message is delivered to the targeted recipients.</span></span>

## <a name="password-attack-campaigns"></a><span data-ttu-id="15fab-232">Campagne di attacco con password</span><span class="sxs-lookup"><span data-stu-id="15fab-232">Password attack campaigns</span></span>

<span data-ttu-id="15fab-233">Un *attacco con password* tenta di indovinare le password per gli account utente in un'organizzazione, in genere dopo che l'utente malintenzionato ha identificato uno o più account utente validi.</span><span class="sxs-lookup"><span data-stu-id="15fab-233">A *password attack* tries to guess passwords for user accounts in an organization, typically after the attacker has identified one or more valid user accounts.</span></span>

<span data-ttu-id="15fab-234">Nel simulatore di attacchi sono disponibili due diversi tipi di campagne di attacco con password per testare la complessità delle password degli utenti:</span><span class="sxs-lookup"><span data-stu-id="15fab-234">In Attack Simulator, two different types of password attack campaigns are available for you to test the complexity of your users' passwords:</span></span>

- <span data-ttu-id="15fab-235">**Brute force password (attacco** con dizionario):  un attacco di forza *bruta* o dizionario usa un file di dizionario di grandi dimensioni di password su un account utente con la volontà che una di esse funzioni (molte password su un account).</span><span class="sxs-lookup"><span data-stu-id="15fab-235">**Brute force password (dictionary attack)**: A *brute force* or *dictionary* attack uses a large dictionary file of passwords on a user account with the hope that one of them will work (many passwords against one account).</span></span> <span data-ttu-id="15fab-236">I blocchi delle password non corretti consentono di dissuadere gli attacchi di forza bruta alle password.</span><span class="sxs-lookup"><span data-stu-id="15fab-236">Incorrect password lock-outs help deter brute force password attacks.</span></span>

  <span data-ttu-id="15fab-237">Per l'attacco con dizionario, è possibile specificare una o più password da provare (immesse manualmente o in un file caricato) e specificare uno o più utenti.</span><span class="sxs-lookup"><span data-stu-id="15fab-237">For the dictionary attack, you can specify one or many passwords to try (manually entered or in an uploaded file), and you can specify one or many users.</span></span>

- <span data-ttu-id="15fab-238">**Attacco con password spray:** un attacco *di tipo password spray* utilizza la stessa password considerata con attenzione rispetto a un elenco di account utente (una password contro molti account).</span><span class="sxs-lookup"><span data-stu-id="15fab-238">**Password spray attack**: A *password spray* attack uses the same carefully considered password against a list of user accounts (one password against many accounts).</span></span> <span data-ttu-id="15fab-239">Gli attacchi di tipo password spray sono più difficili da rilevare rispetto agli attacchi di forza bruta delle password (la probabilità di successo aumenta quando un utente malintenzionato tenta una password su decine o centinaia di account senza il rischio di inciampare nel blocco non corretto della password dell'utente).</span><span class="sxs-lookup"><span data-stu-id="15fab-239">Password spray attacks are harder to detect than brute force password attacks (the probability of success increases when an attacker tries one password across dozens or hundreds of accounts without the risk of tripping the user's incorrect password lock-out).</span></span>

  <span data-ttu-id="15fab-240">Per l'attacco di tipo password spray, è possibile specificare una sola password da provare e uno o più utenti.</span><span class="sxs-lookup"><span data-stu-id="15fab-240">For the password spray attack, you can only specify one password to try, and you can specify one or many users.</span></span>

> [!NOTE]
> <span data-ttu-id="15fab-241">Gli attacchi alle password in Attack Simulator passano le richieste di autenticazione di base di nome utente e password a un endpoint, quindi funzionano anche con altri metodi di autenticazione (AD FS, sincronizzazione hash delle password, pass-through, PingFederate e così via).</span><span class="sxs-lookup"><span data-stu-id="15fab-241">The password attacks in Attack Simulator pass username and password Basic auth requests to an endpoint, so they also work with other authentication methods (AD FS, password hash sync, pass-through, PingFederate, etc.).</span></span> <span data-ttu-id="15fab-242">Per gli utenti che hanno abilitato l'autenticazione a più fattori, anche se l'attacco con password tenta la  password effettiva, il tentativo verrà sempre registrato come errore (in altre parole, gli utenti MFA non verranno mai visualizzati nel conteggio tentativi riusciti della campagna).</span><span class="sxs-lookup"><span data-stu-id="15fab-242">For users that have MFA enabled, even if the password attack tries their actual password, the attempt will always register as a failure (in other words, MFA users will never appear in the **Successful attempts** count of the campaign).</span></span> <span data-ttu-id="15fab-243">Questo è il risultato previsto.</span><span class="sxs-lookup"><span data-stu-id="15fab-243">This is the expected result.</span></span> <span data-ttu-id="15fab-244">L'autenticazione a più fattori è un metodo principale per la protezione da attacchi con password.</span><span class="sxs-lookup"><span data-stu-id="15fab-244">MFA is a primary method to help protect against password attacks.</span></span>

### <a name="create-and-launch-a-password-attack-campaign"></a><span data-ttu-id="15fab-245">Creare e avviare una campagna di attacco con password</span><span class="sxs-lookup"><span data-stu-id="15fab-245">Create and launch a password attack campaign</span></span>

1. <span data-ttu-id="15fab-246">Nel Centro sicurezza & conformità passare a Simulatore di **attacchi di gestione** delle \> **minacce.**</span><span class="sxs-lookup"><span data-stu-id="15fab-246">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="15fab-247">Nella pagina **Simula attacchi** effettuare una delle seguenti selezioni in base al tipo di campagna che si desidera creare:</span><span class="sxs-lookup"><span data-stu-id="15fab-247">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="15fab-248">Nella sezione **Brute Force Password (Dictionary Attack)** fai clic su **Launch Attack** o **su Attack Details** Launch \> **Attack.**</span><span class="sxs-lookup"><span data-stu-id="15fab-248">In the **Brute Force Password (Dictionary Attack)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="15fab-249">nella sezione **Attacco con password spray,** fare clic **su Launch Attack** o su **Attack Details** \> **Launch Attack.**</span><span class="sxs-lookup"><span data-stu-id="15fab-249">in the **Password spray attack** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="15fab-250">La **procedura guidata Configura attacco password** viene avviata in un nuovo riquadro a comparsa.</span><span class="sxs-lookup"><span data-stu-id="15fab-250">The **Configure Password Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="15fab-251">Nel passaggio **iniziale** immettere un nome visualizzato univoco per la campagna e quindi fare clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="15fab-251">In the **Start** step, enter a unique display name for the campaign, and then click **Next**.</span></span>

4. <span data-ttu-id="15fab-252">Nel passaggio **Utenti di** destinazione eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="15fab-252">In the **Target users** step, do one of the following steps:</span></span>

   - <span data-ttu-id="15fab-253">Fare **clic su Rubrica** per selezionare i destinatari (utenti o gruppi) per la campagna.</span><span class="sxs-lookup"><span data-stu-id="15fab-253">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="15fab-254">Ogni destinatario di destinazione deve disporre di una cassetta postale di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="15fab-254">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="15fab-255">Se si fa **clic su Filtro** e **Applica** senza immettere un criterio di ricerca, tutti i destinatari vengono restituiti e aggiunti alla campagna.</span><span class="sxs-lookup"><span data-stu-id="15fab-255">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="15fab-256">Fare **clic su** Importa e quindi **importa** file per importare un valore con valori delimitati da virgole (CSV) o un file di indirizzi di posta elettronica separati da riga.</span><span class="sxs-lookup"><span data-stu-id="15fab-256">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="15fab-257">Ogni riga deve contenere l'indirizzo di posta elettronica del destinatario.</span><span class="sxs-lookup"><span data-stu-id="15fab-257">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="15fab-258">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="15fab-258">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="15fab-259">Nel passaggio **Scegliere le impostazioni di attacco** scegliere cosa fare in base al tipo di campagna:</span><span class="sxs-lookup"><span data-stu-id="15fab-259">In the **Choose attack settings** step, choose what to do based on the campaign type:</span></span>

   - <span data-ttu-id="15fab-260">**Brute Force Password (Dictionary Attack):** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="15fab-260">**Brute Force Password (Dictionary Attack)**: Do either of the following steps:</span></span>

     - <span data-ttu-id="15fab-261">**Immettere manualmente le password:** nella casella Premere INVIO per aggiungere una **password,** digitare una password e quindi premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="15fab-261">**Enter passwords manually**: In the **Press enter to add a password** box, type a password and then press ENTER.</span></span> <span data-ttu-id="15fab-262">Ripetere questo passaggio tutte le volte necessarie.</span><span class="sxs-lookup"><span data-stu-id="15fab-262">Repeat this step as many times as necessary.</span></span>

     - <span data-ttu-id="15fab-263">**Caricare le password da un file di dizionario:** fare clic su Carica per importare un file di testo esistente contenente una password per ogni riga e un'ultima riga vuota. </span><span class="sxs-lookup"><span data-stu-id="15fab-263">**Upload passwords from a dictionary file**: Click **Upload** to import an existing text file that contains one password on each line and a blank last line.</span></span> <span data-ttu-id="15fab-264">Le dimensioni del file di testo devono essere pari o inferiori a 10 MB e non possono contenere più di 30000 password.</span><span class="sxs-lookup"><span data-stu-id="15fab-264">The text file must be 10 MB or less in size, and can't contain more than 30000 passwords.</span></span>

   - <span data-ttu-id="15fab-265">**Attacco con password spray:** nelle **password da** usare nella casella di attacco, immettere una password.</span><span class="sxs-lookup"><span data-stu-id="15fab-265">**Password spray attack**: In **The password(s) to use in the attack** box, enter one password.</span></span>

   <span data-ttu-id="15fab-266">Al termine dell'operazione, fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="15fab-266">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="15fab-267">Nel passaggio **Conferma** fare clic su **Fine** per avviare la campagna.</span><span class="sxs-lookup"><span data-stu-id="15fab-267">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="15fab-268">Le password specificate vengono tentate per gli utenti specificati.</span><span class="sxs-lookup"><span data-stu-id="15fab-268">The passwords you specified are tried on users you specified.</span></span>

## <a name="view-campaign-results"></a><span data-ttu-id="15fab-269">Visualizzare i risultati della campagna</span><span class="sxs-lookup"><span data-stu-id="15fab-269">View campaign results</span></span>

<span data-ttu-id="15fab-270">Dopo aver avviato una campagna, puoi controllare l'avanzamento e i risultati nella pagina principale **Simula attacchi.**</span><span class="sxs-lookup"><span data-stu-id="15fab-270">After you launch a campaign, you can check the progress and results on the main **Simulate attacks** page.</span></span>

<span data-ttu-id="15fab-271">Le campagne attive mostreranno una barra di stato, un valore percentuale completato e il conteggio "(utenti completati) di (utenti totali)".</span><span class="sxs-lookup"><span data-stu-id="15fab-271">Active campaigns will show a status bar, a completed percentage value and "(completed users) of (total users)" count.</span></span> <span data-ttu-id="15fab-272">Facendo clic **sul** pulsante Aggiorna viene aggiornato lo stato di avanzamento delle campagne attive.</span><span class="sxs-lookup"><span data-stu-id="15fab-272">Clicking the **Refresh** button will update the progress of any active campaigns.</span></span> <span data-ttu-id="15fab-273">Puoi anche fare clic su **Termina** per interrompere una campagna attiva.</span><span class="sxs-lookup"><span data-stu-id="15fab-273">You can also click **Terminate** to stop an active campaign.</span></span>

<span data-ttu-id="15fab-274">Al termine della campagna, lo stato cambia in **Attacco completato.**</span><span class="sxs-lookup"><span data-stu-id="15fab-274">When the campaign is finished, the status changes to **Attack completed**.</span></span> <span data-ttu-id="15fab-275">Puoi visualizzare i risultati della campagna eseguendo una delle azioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="15fab-275">You can view the results of the campaign by doing either of the following actions:</span></span>

- <span data-ttu-id="15fab-276">Nella pagina principale **Simulate attacks** fai clic **su View Report** sotto il nome della campagna.</span><span class="sxs-lookup"><span data-stu-id="15fab-276">On the main **Simulate attacks** page, click **View Report** under the name of the campaign.</span></span>

- <span data-ttu-id="15fab-277">Nella pagina principale **Simulate attacks** fare clic **su Attack Details** nella sezione relativa al tipo di attacco.</span><span class="sxs-lookup"><span data-stu-id="15fab-277">On the main **Simulate attacks** page, click **Attack Details** in the section for the type of attack.</span></span> <span data-ttu-id="15fab-278">Nella pagina **dei dettagli dell'attacco** che si apre, selezionare la campagna nella sezione **Cronologia** attacchi.</span><span class="sxs-lookup"><span data-stu-id="15fab-278">On the **Attack details** page that opens, select the campaign in the **Attack History** section.</span></span>

<span data-ttu-id="15fab-279">Una delle azioni precedenti consente di accedere a una pagina denominata **Dettagli attacco.**</span><span class="sxs-lookup"><span data-stu-id="15fab-279">Either of the previous actions will take you to a page named **Attack details**.</span></span> <span data-ttu-id="15fab-280">Le informazioni disponibili in questa pagina per ogni tipo di campagna sono descritte nelle sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="15fab-280">The information that's available on this page for each type of campaign is described in the following sections.</span></span>

### <a name="spear-phishing-credentials-harvest-campaign-results"></a><span data-ttu-id="15fab-281">Risultati della campagna spear phishing (Credentials Harvest)</span><span class="sxs-lookup"><span data-stu-id="15fab-281">Spear Phishing (Credentials Harvest) campaign results</span></span>

<span data-ttu-id="15fab-282">Le informazioni seguenti sono disponibili nella pagina dei dettagli **dell'attacco** per ogni campagna:</span><span class="sxs-lookup"><span data-stu-id="15fab-282">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="15fab-283">Durata (data/ora di inizio e data/ora di fine) della campagna.</span><span class="sxs-lookup"><span data-stu-id="15fab-283">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="15fab-284">**Totale utenti a cui è stata destinata**</span><span class="sxs-lookup"><span data-stu-id="15fab-284">**Total users targeted**</span></span>

- <span data-ttu-id="15fab-285">**Tentativi riusciti:** numero di utenti che hanno fatto clic sul **collegamento** e immesso le proprie credenziali *(qualsiasi valore* di nome utente e password).</span><span class="sxs-lookup"><span data-stu-id="15fab-285">**Successful attempts**: The number of users who clicked the link **and** entered their credentials (*any* username and password value).</span></span>

- <span data-ttu-id="15fab-286">**Tasso di successo complessivo**: percentuale calcolata dal numero totale di tentativi **riusciti**  /  **mirati.**</span><span class="sxs-lookup"><span data-stu-id="15fab-286">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="15fab-287">**Clic più rapido:** tempo impiegato dal primo utente per fare clic sul collegamento dopo l'avvio della campagna.</span><span class="sxs-lookup"><span data-stu-id="15fab-287">**Fastest Click**: How long it took the first user to click the link after you launched the campaign.</span></span>

- <span data-ttu-id="15fab-288">**Media clic**: somma del tempo impiegato da tutti gli utenti per fare clic sul collegamento diviso per il numero di utenti che hanno fatto clic sul collegamento.</span><span class="sxs-lookup"><span data-stu-id="15fab-288">**Average Click**: The sum of how long it took everyone to click the link divided by the number of users who clicked the link.</span></span>

- <span data-ttu-id="15fab-289">**Click Success Rate**: percentuale calcolata da (numero di utenti che hanno fatto clic sul collegamento) / **Totale utenti mirati.**</span><span class="sxs-lookup"><span data-stu-id="15fab-289">**Click Success Rate**: A percentage that's calculated by (number of users who clicked the link) / **Total users targeted**.</span></span>

- <span data-ttu-id="15fab-290">**Credenziali più veloci:** tempo impiegato dal primo utente per immettere le credenziali dopo l'avvio della campagna.</span><span class="sxs-lookup"><span data-stu-id="15fab-290">**Fastest Credentials**: How long it took the first user to enter their credentials after you launched the campaign.</span></span>

- <span data-ttu-id="15fab-291">**Media credenziali**: somma del tempo impiegato da tutti per immettere le credenziali diviso per il numero di utenti che hanno immesso le credenziali.</span><span class="sxs-lookup"><span data-stu-id="15fab-291">**Average Credentials**: The sum of how long it took everyone to enter their credentials divided by the number of users who entered their credentials.</span></span>

- <span data-ttu-id="15fab-292">**Percentuale di successo delle** credenziali : percentuale calcolata da (numero di utenti che hanno immesso le credenziali) / **Totale utenti di destinazione.**</span><span class="sxs-lookup"><span data-stu-id="15fab-292">**Credential Success Rate**: A percentage that's calculated by (number of users who entered their credentials) / **Total users targeted**.</span></span>

- <span data-ttu-id="15fab-293">Grafico a barre che mostra i **numeri di** collegamento su cui è stato fatto clic e i numeri forniti per le **credenziali** al giorno.</span><span class="sxs-lookup"><span data-stu-id="15fab-293">A bar graph that shows the **Link clicked** and **Credential supplied** numbers per day.</span></span>

- <span data-ttu-id="15fab-294">Grafico a cerchi che mostra le percentuali **di** clic **sul** collegamento, le credenziali fornite e **nessuna** percentuale per la campagna.</span><span class="sxs-lookup"><span data-stu-id="15fab-294">A circle graph that shows the **Link clicked**, **Credential supplied**, and **None** percentages for the campaign.</span></span>

- <span data-ttu-id="15fab-295">Nella **sezione Utenti compromessi** sono elencati i dettagli degli utenti che hanno fatto clic sul collegamento:</span><span class="sxs-lookup"><span data-stu-id="15fab-295">The **Compromised Users** section lists the details of the users who clicked the link:</span></span>

  - <span data-ttu-id="15fab-296">L'indirizzo di posta elettronica dell'utente</span><span class="sxs-lookup"><span data-stu-id="15fab-296">The user's email address</span></span>

  - <span data-ttu-id="15fab-297">Data/ora in cui hanno fatto clic sul collegamento.</span><span class="sxs-lookup"><span data-stu-id="15fab-297">The date/time when they clicked the link.</span></span>

  - <span data-ttu-id="15fab-298">L'indirizzo IP del client.</span><span class="sxs-lookup"><span data-stu-id="15fab-298">The client IP address.</span></span>

  - <span data-ttu-id="15fab-299">Dettagli sulla versione di Windows e del Web browser dell'utente.</span><span class="sxs-lookup"><span data-stu-id="15fab-299">Details about the user's version of Windows and web browser.</span></span>

  <span data-ttu-id="15fab-300">È possibile fare **clic su Esporta** per esportare i risultati in un file CSV.</span><span class="sxs-lookup"><span data-stu-id="15fab-300">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="spear-phishing-attachment-campaign-results"></a><span data-ttu-id="15fab-301">Risultati della campagna di phishing (allegato)</span><span class="sxs-lookup"><span data-stu-id="15fab-301">Spear Phishing (Attachment) campaign results</span></span>

<span data-ttu-id="15fab-302">Le informazioni seguenti sono disponibili nella pagina dei dettagli **dell'attacco** per ogni campagna:</span><span class="sxs-lookup"><span data-stu-id="15fab-302">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="15fab-303">Durata (data/ora di inizio e data/ora di fine) della campagna.</span><span class="sxs-lookup"><span data-stu-id="15fab-303">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="15fab-304">**Totale utenti a cui è stata destinata**</span><span class="sxs-lookup"><span data-stu-id="15fab-304">**Total users targeted**</span></span>

- <span data-ttu-id="15fab-305">**Tentativi riusciti**: numero di utenti che hanno aperto o scaricato e aperto l'allegato (l'anteprima non viene conteggiato).</span><span class="sxs-lookup"><span data-stu-id="15fab-305">**Successful attempts**: The number of users who opened or downloaded and opened the attachment (preview doesn't count).</span></span>

- <span data-ttu-id="15fab-306">**Tasso di successo complessivo**: percentuale calcolata dal numero totale di tentativi **riusciti**  /  **mirati.**</span><span class="sxs-lookup"><span data-stu-id="15fab-306">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="15fab-307">**Tempo di apertura dell'allegato** più rapido: tempo impiegato dal primo utente per aprire l'allegato dopo l'avvio della campagna.</span><span class="sxs-lookup"><span data-stu-id="15fab-307">**Fastest attachment open time**: How long it took the first user to open the attachment after you launched the campaign.</span></span>

- <span data-ttu-id="15fab-308">**Tempo medio di apertura** dell'allegato: somma del tempo impiegato da tutti gli utenti per aprire l'allegato diviso per il numero di utenti che hanno aperto l'allegato.</span><span class="sxs-lookup"><span data-stu-id="15fab-308">**Average attachment open time**: The sum of how long it took everyone to open the attachment divided by the number of users who opened the attachment.</span></span>

- <span data-ttu-id="15fab-309">**Percentuale di successo apertura** allegato : percentuale calcolata da (numero di utenti che hanno aperto l'allegato) / **Totale utenti destinatari.**</span><span class="sxs-lookup"><span data-stu-id="15fab-309">**Attachment open success rate**: A percentage that's calculated by (number of users who opened the attachment) / **Total users targeted**.</span></span>

### <a name="brute-force-password-dictionary-attack-campaign-results"></a><span data-ttu-id="15fab-310">Risultati della campagna Brute Force Password (attacco con dizionario)</span><span class="sxs-lookup"><span data-stu-id="15fab-310">Brute Force Password (Dictionary Attack) campaign results</span></span>

<span data-ttu-id="15fab-311">Le informazioni seguenti sono disponibili nella pagina dei dettagli **dell'attacco** per ogni campagna:</span><span class="sxs-lookup"><span data-stu-id="15fab-311">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="15fab-312">Durata (data/ora di inizio e data/ora di fine) della campagna.</span><span class="sxs-lookup"><span data-stu-id="15fab-312">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="15fab-313">**Totale utenti a cui è stata destinata**</span><span class="sxs-lookup"><span data-stu-id="15fab-313">**Total users targeted**</span></span>

- <span data-ttu-id="15fab-314">**Tentativi** riusciti: numero di utenti che hanno rilevato l'utilizzo di una delle password specificate.</span><span class="sxs-lookup"><span data-stu-id="15fab-314">**Successful attempts**: The number of users who were found to be using one of the specified passwords.</span></span>

- <span data-ttu-id="15fab-315">**Tasso di successo complessivo**: percentuale calcolata dal numero totale di tentativi **riusciti**  /  **mirati.**</span><span class="sxs-lookup"><span data-stu-id="15fab-315">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="15fab-316">Nella **sezione Utenti compromessi** sono elencati gli indirizzi di posta elettronica degli utenti interessati.</span><span class="sxs-lookup"><span data-stu-id="15fab-316">The **Compromised Users** section lists the email addresses of the affected users.</span></span> <span data-ttu-id="15fab-317">È possibile fare **clic su Esporta** per esportare i risultati in un file CSV.</span><span class="sxs-lookup"><span data-stu-id="15fab-317">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="password-spray-attack-campaign-results"></a><span data-ttu-id="15fab-318">Risultati della campagna di attacco con password spray</span><span class="sxs-lookup"><span data-stu-id="15fab-318">Password spray attack campaign results</span></span>

<span data-ttu-id="15fab-319">Le informazioni seguenti sono disponibili nella pagina dei dettagli **dell'attacco** per ogni campagna:</span><span class="sxs-lookup"><span data-stu-id="15fab-319">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="15fab-320">Durata (data/ora di inizio e data/ora di fine) della campagna.</span><span class="sxs-lookup"><span data-stu-id="15fab-320">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="15fab-321">**Totale utenti a cui è stata destinata**</span><span class="sxs-lookup"><span data-stu-id="15fab-321">**Total users targeted**</span></span>

- <span data-ttu-id="15fab-322">**Tentativi riusciti**: numero di utenti che hanno rilevato l'utilizzo della password specificata.</span><span class="sxs-lookup"><span data-stu-id="15fab-322">**Successful attempts**: The number of users who were found to be using the specified password.</span></span>

- <span data-ttu-id="15fab-323">**Tasso di successo complessivo**: percentuale calcolata dal numero totale di tentativi **riusciti**  /  **mirati.**</span><span class="sxs-lookup"><span data-stu-id="15fab-323">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>
