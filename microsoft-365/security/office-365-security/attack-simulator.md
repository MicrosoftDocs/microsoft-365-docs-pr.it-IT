---
title: Simulatore di attacchi in Office 365
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: da5845db-c578-4a41-b2cb-5a09689a551b
ms.collection:
- M365-security-compliance
description: In qualità di amministratore globale di Office 365, è possibile utilizzare Attack Simulator per eseguire scenari di attacco realistici nell'organizzazione. Questo può essere utile per identificare e individuare gli utenti vulnerabili prima che un attacco reale colpisca la propria azienda.
ms.openlocfilehash: e5f304a7c706875216c58330b1225d341b2b59df
ms.sourcegitcommit: 5710ce729c55d95b8b452d99ffb7ea92b5cb254a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2019
ms.locfileid: "39971934"
---
# <a name="attack-simulator-in-office-365"></a><span data-ttu-id="8c547-104">Simulatore di attacchi in Office 365</span><span class="sxs-lookup"><span data-stu-id="8c547-104">Attack Simulator in Office 365</span></span>

<span data-ttu-id="8c547-105">**Riepilogo** Se si è un amministratore globale di Office 365 o un amministratore della sicurezza e l'organizzazione dispone di Office 365 Advanced Threat Protection Plan 2, che include le [funzionalità di analisi e di risposta alle minacce](office-365-ti.md), è possibile utilizzare Attack Simulator per eseguire scenari di attacco realistici nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="8c547-105">**Summary** If you are an Office 365 global administrator or a security administrator and your organization has Office 365 Advanced Threat Protection Plan 2, which includes [Threat Investigation and Response capabilities](office-365-ti.md), you can use Attack Simulator to run realistic attack scenarios in your organization.</span></span> <span data-ttu-id="8c547-106">Questo può essere utile per identificare e individuare gli utenti vulnerabili prima che un attacco reale impatti la linea di base.</span><span class="sxs-lookup"><span data-stu-id="8c547-106">This can help you identify and find vulnerable users before a real attack impacts your bottom line.</span></span> <span data-ttu-id="8c547-107">Leggere questo articolo per ulteriori informazioni.</span><span class="sxs-lookup"><span data-stu-id="8c547-107">Read this article to learn more.</span></span>

## <a name="the-attacks"></a><span data-ttu-id="8c547-108">Gli attacchi</span><span class="sxs-lookup"><span data-stu-id="8c547-108">The Attacks</span></span>

<span data-ttu-id="8c547-109">Sono attualmente disponibili tre tipi di simulazioni di attacco:</span><span class="sxs-lookup"><span data-stu-id="8c547-109">Three kinds of attack simulations are currently available:</span></span>

- [<span data-ttu-id="8c547-110">Nome visualizzato Spear-attacco di phishing</span><span class="sxs-lookup"><span data-stu-id="8c547-110">Display name spear-phishing attack</span></span>](#display-name-spear-phishing-attack)

- [<span data-ttu-id="8c547-111">Attacco spray per la password</span><span class="sxs-lookup"><span data-stu-id="8c547-111">Password-spray attack</span></span>](#password-spray-attack)

- [<span data-ttu-id="8c547-112">Attacco per la password con forza bruta</span><span class="sxs-lookup"><span data-stu-id="8c547-112">Brute-force password attack</span></span>](#brute-force-password-attack)

<span data-ttu-id="8c547-113">Affinché l'avvio di un attacco venga eseguito correttamente, verificare che l'account utilizzato per eseguire gli attacchi simulati utilizzi l'autenticazione a più fattori.</span><span class="sxs-lookup"><span data-stu-id="8c547-113">For an attack to be successfully launched, make sure that the account you are using to run simulated attacks is using multi-factor authentication.</span></span> <span data-ttu-id="8c547-114">Inoltre, è necessario essere un amministratore globale di Office 365 o un amministratore della sicurezza.</span><span class="sxs-lookup"><span data-stu-id="8c547-114">In addition, you must be an Office 365 global administrator or a security administrator.</span></span> <span data-ttu-id="8c547-115">Per ulteriori informazioni sui ruoli e le autorizzazioni, vedere [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="8c547-115">(To learn more about roles and permissions, see [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).)</span></span>

<span data-ttu-id="8c547-116">Per accedere a simulatore di attacco, &amp; nel centro sicurezza e conformità scegliere **Threat Management** \> **Attack Simulator**.</span><span class="sxs-lookup"><span data-stu-id="8c547-116">To access Attack Simulator, in the Security &amp; Compliance Center, choose **Threat management** \> **Attack simulator**.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="8c547-117">Prima di iniziare...</span><span class="sxs-lookup"><span data-stu-id="8c547-117">Before you begin...</span></span>

<span data-ttu-id="8c547-118">Assicurarsi che l'utente e l'organizzazione soddisfino i seguenti requisiti per il simulatore di attacco:</span><span class="sxs-lookup"><span data-stu-id="8c547-118">Make sure that you and your organization meet the following requirements for Attack Simulator:</span></span>

- <span data-ttu-id="8c547-119">La posta elettronica dell'organizzazione è ospitata in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="8c547-119">Your organization's email is hosted in Exchange Online.</span></span> <span data-ttu-id="8c547-120">(Attack Simulator non è disponibile per i server di posta elettronica locali.)</span><span class="sxs-lookup"><span data-stu-id="8c547-120">(Attack Simulator is not available for on-premises email servers.)</span></span>

- <span data-ttu-id="8c547-121">Si è un amministratore globale o un amministratore di sicurezza di Office 365</span><span class="sxs-lookup"><span data-stu-id="8c547-121">You are an Office 365 global administrator or security administrator</span></span>

- <span data-ttu-id="8c547-122">L'autenticazione a più fattori e l' [accesso condizionale](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication) sono attivati, almeno per l'account di amministratore globale di Office 365 e gli amministratori della sicurezza che utilizzeranno simulatore di attacco.</span><span class="sxs-lookup"><span data-stu-id="8c547-122">[Multi-factor authentication/Conditional Access](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication) is turned on, for at least the Office 365 global administrator account and security administrators who will be using Attack Simulator.</span></span> <span data-ttu-id="8c547-123">(Idealmente, l'autenticazione a più fattori e l'accesso condizionale sono attivati per tutti gli utenti dell'organizzazione.)</span><span class="sxs-lookup"><span data-stu-id="8c547-123">(Ideally, multi-factor authentication/conditional access is turned on for all users in your organization.)</span></span>

- <span data-ttu-id="8c547-124">L'organizzazione dispone [di Office 365 Advanced Threat Protection Plan 2](office-365-atp.md), con simulatore di attacco visibile &amp; nel centro sicurezza e conformità (andare a **Threat Management** \> **Attack Simulator**)</span><span class="sxs-lookup"><span data-stu-id="8c547-124">Your organization has [Office 365 Advanced Threat Protection Plan 2](office-365-atp.md), with Attack Simulator visible in the Security &amp; Compliance Center (go to **Threat management** \> **Attack simulator**)</span></span>

    ![Threat Management-simulatore d'attacco](../media/ThreatMgmt-AttackSimulator.png)

## <a name="display-name-spear-phishing-attack"></a><span data-ttu-id="8c547-126">Nome visualizzato Spear-attacco di phishing</span><span class="sxs-lookup"><span data-stu-id="8c547-126">Display name spear-phishing attack</span></span>

<span data-ttu-id="8c547-127">Il phishing è un termine generico per una vasta serie di attacchi classificati come un attacco stile di social engineering.</span><span class="sxs-lookup"><span data-stu-id="8c547-127">Phishing is a generic term for a broad suite of attacks classed as a social engineering style attack.</span></span> <span data-ttu-id="8c547-128">Questo attacco è concentrato sul phishing Spear, un attacco più mirato che si rivolge a un gruppo specifico di persone o di un'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="8c547-128">This attack is focused on spear phishing, a more targeted attack that is aimed at a specific group of individuals or an organization.</span></span> <span data-ttu-id="8c547-129">In genere, un attacco personalizzato con alcuni ricognizione eseguito e utilizzando un nome visualizzato che genererà la fiducia nel destinatario, ad esempio un messaggio di posta elettronica che sembra provenire da un dirigente all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="8c547-129">Typically, a customized attack with some reconnaissance performed and using a display name that will generate trust in the recipient, such as an email message that looks like it came from an executive within your organization.</span></span>

<span data-ttu-id="8c547-130">Questo attacco è incentrato sull'eventualità di modificare il messaggio a cui sembra abbia avuto origine cambiando il nome visualizzato e l'indirizzo di origine.</span><span class="sxs-lookup"><span data-stu-id="8c547-130">This attack focuses on letting you manipulate who the message appears to have originated from by changing the display name and source address.</span></span> <span data-ttu-id="8c547-131">Quando gli attacchi Spear-phishing hanno esito positivo, cyberattackers accedere alle credenziali degli utenti.</span><span class="sxs-lookup"><span data-stu-id="8c547-131">When spear-phishing attacks are successful, cyberattackers gain access to users' credentials.</span></span>

### <a name="to-simulate-a-spear-phishing-attack"></a><span data-ttu-id="8c547-132">Per simulare un attacco di Spear-phishing</span><span class="sxs-lookup"><span data-stu-id="8c547-132">To simulate a spear-phishing attack</span></span>

![Comporre il corpo della posta elettronica](../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)

<span data-ttu-id="8c547-134">È possibile creare l'editor HTML RTF direttamente nel campo **corpo del messaggio di posta elettronica** o collaborare con l'origine HTML.</span><span class="sxs-lookup"><span data-stu-id="8c547-134">You can craft the rich HTML editor directly in the **Email body** field itself or work with HTML source.</span></span>

1. <span data-ttu-id="8c547-135">Nel [Centro sicurezza &amp; e conformità](https://protection.office.com)scegliere **Threat Management** \> **Attack Simulator**.</span><span class="sxs-lookup"><span data-stu-id="8c547-135">In the [Security &amp; Compliance Center](https://protection.office.com), choose **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="8c547-136">Specificare un nome di campagna significativo per l'attacco o selezionare un modello.</span><span class="sxs-lookup"><span data-stu-id="8c547-136">Specify a meaningful campaign name for the attack or select a template.</span></span>

   ![Pagina iniziale di phishing](../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)

3. <span data-ttu-id="8c547-138">Specificare i destinatari di destinazione.</span><span class="sxs-lookup"><span data-stu-id="8c547-138">Specify the target recipients.</span></span> <span data-ttu-id="8c547-139">Può trattarsi di singoli o gruppi nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="8c547-139">This can be individuals or groups in your organization.</span></span> <span data-ttu-id="8c547-140">Ogni destinatario di destinazione deve disporre di una cassetta postale di Exchange online in modo che l'attacco abbia esito positivo.</span><span class="sxs-lookup"><span data-stu-id="8c547-140">Each targeted recipient must have an Exchange Online Mailbox in order for the attack to be successful.</span></span>

   ![Selezione destinatario](../media/faf8c2e0-6175-4cd7-8265-0c8e727f4d0f.jpg)

4. <span data-ttu-id="8c547-142">Configurare i dettagli di posta elettronica di phishing.</span><span class="sxs-lookup"><span data-stu-id="8c547-142">Configure the Phishing email details.</span></span>

   ![Configurare i dettagli della posta elettronica](../media/f043608f-f8ce-4aae-be28-86e8ecc524a9.jpg)

   <span data-ttu-id="8c547-144">La formattazione HTML può essere complessa o di base come necessario per la campagna.</span><span class="sxs-lookup"><span data-stu-id="8c547-144">The HTML formatting can be as complex or basic as your campaign needs.</span></span> <span data-ttu-id="8c547-145">Poiché il formato del messaggio di posta elettronica è HTML, è possibile inserire immagini e testo per migliorare la credibilità.</span><span class="sxs-lookup"><span data-stu-id="8c547-145">As the email format is HTML, you can insert images and text to enhance believability.</span></span> <span data-ttu-id="8c547-146">È possibile controllare l'aspetto del messaggio ricevuto nel client di posta elettronica di ricezione.</span><span class="sxs-lookup"><span data-stu-id="8c547-146">You have control on what the received message will look like in the receiving email client.</span></span>

5. <span data-ttu-id="8c547-147">Specificare il testo per il campo **from (Name)** .</span><span class="sxs-lookup"><span data-stu-id="8c547-147">Specify text for the **From (Name)** field.</span></span> <span data-ttu-id="8c547-148">Si tratta del campo che viene visualizzato nel **nome visualizzato** nel client di posta elettronica di ricezione.</span><span class="sxs-lookup"><span data-stu-id="8c547-148">This is the field that shows in the **Display Name** in the receiving email client.</span></span>

6. <span data-ttu-id="8c547-149">Specificare il testo o il campo **da** .</span><span class="sxs-lookup"><span data-stu-id="8c547-149">Specify text or the **From** field.</span></span> <span data-ttu-id="8c547-150">Si tratta del campo che viene visualizzato come indirizzo di posta elettronica del mittente nel client di posta elettronica di ricezione.</span><span class="sxs-lookup"><span data-stu-id="8c547-150">This is the field that shows as the email address of the sender in the receiving email client.</span></span>

   <span data-ttu-id="8c547-151">È possibile immettere uno spazio dei nomi di posta elettronica esistente all'interno dell'organizzazione (in questo modo l'indirizzo di posta elettronica viene effettivamente risolto nel client di ricezione, facilitando un modello di attendibilità molto elevato) oppure è possibile immettere un indirizzo di posta elettronica esterno.</span><span class="sxs-lookup"><span data-stu-id="8c547-151">You can enter an existing email namespace within your organization (doing this will make the email address actually resolve in the receiving client, facilitating a very high trust model), or you can enter an external email address.</span></span> <span data-ttu-id="8c547-152">L'indirizzo di posta elettronica specificato non deve esistere effettivamente, ma è necessario seguire il formato di un indirizzo SMTP valido, ad esempio `user@domainname.extension`.</span><span class="sxs-lookup"><span data-stu-id="8c547-152">The email address that you specify does not have to actually exist, but it does need to follow the format of a valid SMTP address, such as `user@domainname.extension`.</span></span>

7. <span data-ttu-id="8c547-153">Usando il selettore a discesa, selezionare un URL del server di accesso di phishing che rispecchi il tipo di contenuto che si avrà all'interno dell'attacco.</span><span class="sxs-lookup"><span data-stu-id="8c547-153">Using the drop-down selector, select a Phishing Login server URL that reflects the type of content you will have within your attack.</span></span> <span data-ttu-id="8c547-154">È possibile scegliere tra diversi URL a tema, ad esempio recapito dei documenti, tecnico, retribuzione e così via. Questo è effettivamente l'URL a cui gli utenti designati devono fare clic.</span><span class="sxs-lookup"><span data-stu-id="8c547-154">Several themed URLs are provided for you to choose from, such as document delivery, technical, payroll etc. This is effectively the URL that targeted users are asked to click.</span></span>

8. <span data-ttu-id="8c547-155">Specificare un URL della pagina di destinazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="8c547-155">Specify a custom landing page URL.</span></span> <span data-ttu-id="8c547-156">In questo modo gli utenti verranno reindirizzati a un URL specificato al termine di un attacco con esito positivo.</span><span class="sxs-lookup"><span data-stu-id="8c547-156">Using this will redirect users to a URL you specify at the end of a successful attack.</span></span> <span data-ttu-id="8c547-157">Se si dispone di un training di sensibilizzazione interno, ad esempio, è possibile specificarlo qui.</span><span class="sxs-lookup"><span data-stu-id="8c547-157">If you have internal awareness training, for example, you can specify that here.</span></span>

9. <span data-ttu-id="8c547-158">Specificare il testo per il campo **Subject** .</span><span class="sxs-lookup"><span data-stu-id="8c547-158">Specify text for the **Subject** field.</span></span> <span data-ttu-id="8c547-159">Si tratta del campo che viene visualizzato come **nome del soggetto** nel client di posta elettronica di ricezione.</span><span class="sxs-lookup"><span data-stu-id="8c547-159">This is the field that shows as the **Subject Name** in the receiving email client.</span></span>

10. <span data-ttu-id="8c547-160">Comporre il **corpo del messaggio di posta elettronica** che riceverà il destinatario.</span><span class="sxs-lookup"><span data-stu-id="8c547-160">Compose the **Email body** that the target will receive.</span></span>

    <span data-ttu-id="8c547-161">`${username}`inserisce il nome della destinazione nel corpo della posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="8c547-161">`${username}` inserts the targets name into the Email body.</span></span>

    <span data-ttu-id="8c547-162">`${loginserverurl}`inserisce l'URL in cui si desidera che gli utenti di destinazione clicchino</span><span class="sxs-lookup"><span data-stu-id="8c547-162">`${loginserverurl}` inserts the URL we want target users to click</span></span>

11. <span data-ttu-id="8c547-163">Fare clic su **Avanti,** quindi su **fine** per avviare l'attacco.</span><span class="sxs-lookup"><span data-stu-id="8c547-163">Choose **Next,** then **Finish** to launch the attack.</span></span> <span data-ttu-id="8c547-164">Il messaggio di posta elettronica di phishing Spear viene recapitato alle cassette postali dei destinatari.</span><span class="sxs-lookup"><span data-stu-id="8c547-164">The spear phishing email message is delivered to your target recipients' mailboxes.</span></span>

## <a name="password-spray-attack"></a><span data-ttu-id="8c547-165">Attacco spray per la password</span><span class="sxs-lookup"><span data-stu-id="8c547-165">Password-spray attack</span></span>

<span data-ttu-id="8c547-166">Un attacco di spruzzatura della password in un'organizzazione viene in genere utilizzato dopo che un attore cattivo ha acquisito un elenco di utenti validi dal tenant.</span><span class="sxs-lookup"><span data-stu-id="8c547-166">A password spray attack against an organization is typically used after a bad actor has successfully acquired a list of valid users from the tenant.</span></span> <span data-ttu-id="8c547-167">L'attore cattivo conosce le password comuni utilizzate dalle persone.</span><span class="sxs-lookup"><span data-stu-id="8c547-167">The bad actor knows about common passwords that people use.</span></span> <span data-ttu-id="8c547-168">Si tratta di un attacco ampiamente utilizzato, poiché si tratta di un attacco a basso costo da eseguire e più difficile da rilevare rispetto alla forza bruta.</span><span class="sxs-lookup"><span data-stu-id="8c547-168">This is a widely used attack, as it is a cheap attack to run, and harder to detect than brute force approaches.</span></span>

<span data-ttu-id="8c547-169">Questo attacco consente di specificare una password comune rispetto a una base di utenti di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="8c547-169">This attack focuses on letting you specify a common password against a large target base of users.</span></span>

### <a name="to-simulate-a-password-spray-attack"></a><span data-ttu-id="8c547-170">Per simulare un attacco spray per la password</span><span class="sxs-lookup"><span data-stu-id="8c547-170">To simulate a password-spray attack</span></span>

1. <span data-ttu-id="8c547-171">Nel [Centro sicurezza &amp; e conformità](https://protection.office.com)scegliere **Threat Management** \> **Attack Simulator**.</span><span class="sxs-lookup"><span data-stu-id="8c547-171">In the [Security &amp; Compliance Center](https://protection.office.com), choose **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="8c547-172">Specificare il nome di una campagna significativa per l'attacco.</span><span class="sxs-lookup"><span data-stu-id="8c547-172">Specify a meaningful campaign name for the attack.</span></span>

3. <span data-ttu-id="8c547-173">Specificare i destinatari di destinazione.</span><span class="sxs-lookup"><span data-stu-id="8c547-173">Specify the target recipients.</span></span> <span data-ttu-id="8c547-174">Può trattarsi di singoli o gruppi nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="8c547-174">This can be individuals or groups in your organization.</span></span> <span data-ttu-id="8c547-175">Un destinatario di destinazione deve disporre di una cassetta postale di Exchange online in modo che l'attacco abbia esito positivo.</span><span class="sxs-lookup"><span data-stu-id="8c547-175">A targeted recipient must have an Exchange Online mailbox in order for the attack to be successful.</span></span>

4. <span data-ttu-id="8c547-176">Specificare una password da utilizzare per l'attacco.</span><span class="sxs-lookup"><span data-stu-id="8c547-176">Specify a password to use for the attack.</span></span> <span data-ttu-id="8c547-177">Ad esempio, una password comune e pertinente che è possibile `Summer2019`provare è.</span><span class="sxs-lookup"><span data-stu-id="8c547-177">For example, one common, relevant password you could try is `Summer2019`.</span></span> <span data-ttu-id="8c547-178">Un altro potrebbe `Fall2019`essere, `Password1`o.</span><span class="sxs-lookup"><span data-stu-id="8c547-178">Another might be `Fall2019`, or `Password1`.</span></span>

5. <span data-ttu-id="8c547-179">Scegliere **fine** per avviare l'attacco.</span><span class="sxs-lookup"><span data-stu-id="8c547-179">Choose **Finish** to launch the attack.</span></span>

## <a name="brute-force-password-attack"></a><span data-ttu-id="8c547-180">Attacco per la password con forza bruta</span><span class="sxs-lookup"><span data-stu-id="8c547-180">Brute-force password attack</span></span>

<span data-ttu-id="8c547-181">Un attacco di password con forza bruta nei confronti di un'organizzazione viene in genere utilizzato dopo che un attore non valido ha acquisito un elenco di utenti chiave dal tenant.</span><span class="sxs-lookup"><span data-stu-id="8c547-181">A brute-force password attack against an organization is typically used after a bad actor has successfully acquired a list of key users from the tenant.</span></span> <span data-ttu-id="8c547-182">Questo attacco si concentra sul tentativo di un set di password su un singolo account utente.</span><span class="sxs-lookup"><span data-stu-id="8c547-182">This attack focuses on trying a set of passwords on a single user's account.</span></span>

### <a name="to-simulate-a-brute-force-password-attack"></a><span data-ttu-id="8c547-183">Per simulare un attacco di password con forza bruta</span><span class="sxs-lookup"><span data-stu-id="8c547-183">To simulate a brute-force password attack</span></span>

1. <span data-ttu-id="8c547-184">Nel [Centro sicurezza &amp; e conformità](https://protection.office.com)scegliere **Threat Management** \> **Attack Simulator**.</span><span class="sxs-lookup"><span data-stu-id="8c547-184">In the [Security &amp; Compliance Center](https://protection.office.com), choose **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="8c547-185">Specificare il nome di una campagna significativa per l'attacco.</span><span class="sxs-lookup"><span data-stu-id="8c547-185">Specify a meaningful campaign name for the attack.</span></span>

3. <span data-ttu-id="8c547-186">Specificare il destinatario di destinazione.</span><span class="sxs-lookup"><span data-stu-id="8c547-186">Specify the target recipient.</span></span> <span data-ttu-id="8c547-187">Un destinatario di destinazione deve disporre di una cassetta postale di Exchange online in modo che l'attacco abbia esito positivo.</span><span class="sxs-lookup"><span data-stu-id="8c547-187">A targeted recipient must have an Exchange Online mailbox in order for the attack to be successful.</span></span>

4. <span data-ttu-id="8c547-188">Specificare un set di password da utilizzare per l'attacco.</span><span class="sxs-lookup"><span data-stu-id="8c547-188">Specify a set of passwords to use for the attack.</span></span> <span data-ttu-id="8c547-189">A tale scopo, è possibile utilizzare un file di testo (con estensione txt) per l'elenco delle password.</span><span class="sxs-lookup"><span data-stu-id="8c547-189">To do this, you can use a text (.txt) file for your list of passwords.</span></span> <span data-ttu-id="8c547-190">Il file di testo non può superare i 10 MB nelle dimensioni dei file.</span><span class="sxs-lookup"><span data-stu-id="8c547-190">The text file cannot exceed 10 MB in file size.</span></span> <span data-ttu-id="8c547-191">Utilizzare una password per riga e assicurarsi di includere un ritorno a capo dopo l'ultima password dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="8c547-191">Use one password per line, and make sure to include a hard return after the last password in your list.</span></span>

5. <span data-ttu-id="8c547-192">Scegliere **fine** per avviare l'attacco.</span><span class="sxs-lookup"><span data-stu-id="8c547-192">Choose **Finish** to launch the attack.</span></span>

## <a name="new-features-in-attack-simulator"></a><span data-ttu-id="8c547-193">Nuove funzionalità in Attack Simulator</span><span class="sxs-lookup"><span data-stu-id="8c547-193">New features in Attack Simulator</span></span>

<span data-ttu-id="8c547-194">Nuove funzionalità sono state aggiunte di recente a Attack Simulator.</span><span class="sxs-lookup"><span data-stu-id="8c547-194">New features have recently been added to Attack Simulator.</span></span> <span data-ttu-id="8c547-195">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="8c547-195">These include:</span></span>

- <span data-ttu-id="8c547-196">Funzionalità di creazione di report avanzate.</span><span class="sxs-lookup"><span data-stu-id="8c547-196">Advanced reporting capabilities.</span></span> <span data-ttu-id="8c547-197">La possibilità di visualizzare dati quali il tempo più rapido (o più lento) per aprire un messaggio di posta elettronica di simulazione di attacco, il tempo più rapido (o più lento) per fare clic su un collegamento nel messaggio e altre visualizzazioni.</span><span class="sxs-lookup"><span data-stu-id="8c547-197">The ability to see data such as the fastest (or slowest) time to open an attack simulation email message, the fastest (or slowest) time to click a link in the message, and more visualizations.</span></span>

- <span data-ttu-id="8c547-198">Editor modelli di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="8c547-198">Email template editor.</span></span> <span data-ttu-id="8c547-199">La possibilità di creare un modello di posta elettronica personalizzato e riutilizzabile che è possibile utilizzare per simulazioni di attacco future.</span><span class="sxs-lookup"><span data-stu-id="8c547-199">The ability to create a custom, reusable email template's that you can use for future attack simulations.</span></span>

- <span data-ttu-id="8c547-200">Importazione del destinatario CSV.</span><span class="sxs-lookup"><span data-stu-id="8c547-200">CSV Recipient Import.</span></span> <span data-ttu-id="8c547-201">La possibilità di utilizzare un file. csv per importare l'elenco dei destinatari di destinazione invece di usare lo strumento di selezione Rubrica.</span><span class="sxs-lookup"><span data-stu-id="8c547-201">The ability to use a .csv file to import your target recipient list instead of using the address book picker.</span></span>

<span data-ttu-id="8c547-202">Altre nuove caratteristiche stanno per essere attaccate al simulatore d'attacco.</span><span class="sxs-lookup"><span data-stu-id="8c547-202">More new features are coming soon to Attack Simulator.</span></span> <span data-ttu-id="8c547-203">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="8c547-203">These include:</span></span>

- <span data-ttu-id="8c547-204">Simulazione di phishing del payload degli allegati.</span><span class="sxs-lookup"><span data-stu-id="8c547-204">Attachment payload phishing simulation.</span></span> <span data-ttu-id="8c547-205">La possibilità di utilizzare un allegato come payload per la simulazione di phishing al posto di un URL.</span><span class="sxs-lookup"><span data-stu-id="8c547-205">The ability to use an attachment as the payload for phishing simulation in place of a URL.</span></span>

<span data-ttu-id="8c547-206">Visitare la Guida di [orientamento di Microsoft 365](https://www.microsoft.com/microsoft-365/roadmap) per vedere cosa c'è in sviluppo, cosa è in uscita e cosa è già stato avviato.</span><span class="sxs-lookup"><span data-stu-id="8c547-206">Visit the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap) to see what's in development, what's rolling out, and what's already launched.</span></span>

## <a name="see-also"></a><span data-ttu-id="8c547-207">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8c547-207">See also</span></span>

[<span data-ttu-id="8c547-208">Descrizione del servizio Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="8c547-208">Office 365 Advanced Threat Protection Service Description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)

[<span data-ttu-id="8c547-209">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="8c547-209">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
