---
title: Revocare la posta elettronica crittografata da Advanced Message Encryption
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 06/11/2020
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: Come amministratore e come mittente del messaggio, è possibile revocare determinati messaggi di posta elettronica crittografati con Office 365 Advanced Message Encryption.
ms.openlocfilehash: 67582917dd483f6090f5cd369af8faf6cf8a4ea8
ms.sourcegitcommit: b88ffaf3409e02a9847f030f8468f96d36efa398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2021
ms.locfileid: "50105141"
---
# <a name="revoke-email-encrypted-by-advanced-message-encryption"></a><span data-ttu-id="00243-103">Revocare la posta elettronica crittografata da Advanced Message Encryption</span><span class="sxs-lookup"><span data-stu-id="00243-103">Revoke email encrypted by Advanced Message Encryption</span></span>

<span data-ttu-id="00243-104">La revoca della posta elettronica viene offerta come parte della crittografia avanzata dei messaggi di Office 365.</span><span class="sxs-lookup"><span data-stu-id="00243-104">Email revocation is offered as part of Office 365 Advanced Message Encryption.</span></span> <span data-ttu-id="00243-105">Office 365 Advanced Message Encryption è incluso in [Microsoft 365 Enterprise E5,](https://www.microsoft.com/microsoft-365/enterprise/home)Office 365 E5, Microsoft 365 E5 (Noprofit Staff Pricing), Office 365 Enterprise E5 (Noprofit Staff Pricing) e Office 365 Education A5.</span><span class="sxs-lookup"><span data-stu-id="00243-105">Office 365 Advanced Message Encryption is included in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (Nonprofit Staff Pricing), Office 365 Enterprise E5 (Nonprofit Staff Pricing), and Office 365 Education A5.</span></span> <span data-ttu-id="00243-106">Se l'organizzazione ha un abbonamento che non include Office 365 Advanced Message Encryption, è possibile acquistarlo con il componente aggiuntivo SKU conformità Microsoft 365 E5 per Microsoft 365 E3, Microsoft 365 E3 (Prezzi per il personale no profit) o il componente aggiuntivo SKU Office 365 Advanced Compliance per Microsoft 365 E3, Microsoft 365 E3 (Prezzi per il personale no profit) o SKU di Office 365.</span><span class="sxs-lookup"><span data-stu-id="00243-106">If your organization has a subscription that does not include Office 365 Advanced Message Encryption, you can purchase it with the Microsoft 365 E5 Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or the Office 365 Advanced Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or Office 365 SKUs.</span></span>

<span data-ttu-id="00243-107">Questo articolo fa parte di una più ampia serie di articoli sulla crittografia dei messaggi di [Office 365.](ome.md)</span><span class="sxs-lookup"><span data-stu-id="00243-107">This article is part of a larger series of articles about [Office 365 Message Encryption](ome.md).</span></span>

<span data-ttu-id="00243-108">Se un messaggio è stato crittografato con Office 365 Advanced Message Encryption e si è un amministratore di Microsoft 365 o si è il mittente del messaggio, è possibile revocare il messaggio in determinate condizioni.</span><span class="sxs-lookup"><span data-stu-id="00243-108">If a message was encrypted using Office 365 Advanced Message Encryption, and you are a Microsoft 365 admin or you are the sender of the message, you can revoke the message under certain conditions.</span></span> <span data-ttu-id="00243-109">Gli amministratori revocano i messaggi tramite PowerShell.</span><span class="sxs-lookup"><span data-stu-id="00243-109">Admins revoke messages using PowerShell.</span></span> <span data-ttu-id="00243-110">Come mittente, si revoca un messaggio inviato direttamente da Outlook sul Web.</span><span class="sxs-lookup"><span data-stu-id="00243-110">As a sender, you revoke a message that you sent directly from Outlook on the web.</span></span> <span data-ttu-id="00243-111">In questo articolo vengono descritte le circostanze in cui è possibile revocare e come farlo.</span><span class="sxs-lookup"><span data-stu-id="00243-111">This article describes the circumstances under which revocation is possible and how to do it.</span></span>
  
## <a name="encrypted-emails-that-you-can-revoke"></a><span data-ttu-id="00243-112">Messaggi di posta elettronica crittografati che è possibile revocare</span><span class="sxs-lookup"><span data-stu-id="00243-112">Encrypted emails that you can revoke</span></span>

<span data-ttu-id="00243-113">Gli amministratori e i mittenti dei messaggi possono revocare i messaggi di posta elettronica crittografati se il destinatario ha ricevuto un messaggio di posta elettronica crittografato personalizzato basato su collegamento.</span><span class="sxs-lookup"><span data-stu-id="00243-113">Admins and message senders can revoke encrypted emails if the recipient received a link-based, branded encrypted email.</span></span> <span data-ttu-id="00243-114">Se il destinatario ha ricevuto un'esperienza in linea nativa in un client Di Outlook supportato, non è possibile revocare il messaggio.</span><span class="sxs-lookup"><span data-stu-id="00243-114">If the recipient received a native inline experience in a supported Outlook client, then you can't revoke the message.</span></span>

<span data-ttu-id="00243-115">Il fatto che un destinatario riceva un'esperienza basata su collegamento o un'esperienza in linea dipende dal tipo di identità del destinatario: i destinatari dell'account Di Office 365 e Microsoft (ad esempio, gli utenti di outlook.com) ottengono un'esperienza in linea nei client Outlook supportati.</span><span class="sxs-lookup"><span data-stu-id="00243-115">Whether a recipient receives a link-based experience or an inline experience depends on the recipient identity type: Office 365 and Microsoft account recipients (for example, outlook.com users) get an inline experience in supported Outlook clients.</span></span> <span data-ttu-id="00243-116">Tutti gli altri tipi di destinatari, ad esempio i destinatari Gmail e Yahoo, ottengono un'esperienza basata su collegamenti.</span><span class="sxs-lookup"><span data-stu-id="00243-116">All other recipient types, such as Gmail and Yahoo recipients, get a link-based experience.</span></span>

<span data-ttu-id="00243-117">Gli amministratori e i mittenti dei messaggi possono revocare i messaggi crittografati utilizzando la crittografia applicata direttamente da Outlook sul Web.</span><span class="sxs-lookup"><span data-stu-id="00243-117">Admins and message senders can revoke messages that are encrypted using encryption applied directly from Outlook on the web.</span></span> <span data-ttu-id="00243-118">Ad esempio, i messaggi crittografati con l'opzione Solo crittografia.</span><span class="sxs-lookup"><span data-stu-id="00243-118">For example, messages encrypted with the Encrypt Only option.</span></span>

:::image type="content" source="../media/adhocencryptionrevoke.png" alt-text="Screenshot showing Encrypt Only option in Outlook on the web.":::

## <a name="recipient-experience-for-revoked-encrypted-emails"></a><span data-ttu-id="00243-120">Esperienza del destinatario per i messaggi di posta elettronica crittografati revocati</span><span class="sxs-lookup"><span data-stu-id="00243-120">Recipient experience for revoked encrypted emails</span></span>

<span data-ttu-id="00243-121">Dopo che un messaggio di posta elettronica è stato revocato, il destinatario riceve un errore quando accede alla posta elettronica crittografata tramite il portale di crittografia dei messaggi di Office 365: "Il messaggio è stato revocato dal mittente".</span><span class="sxs-lookup"><span data-stu-id="00243-121">Once an email has been revoked, the recipient receives an error when they access the encrypted email through the Office 365 Message Encryption portal: "The message has been revoked by the sender".</span></span>

![Screenshot che mostra un messaggio di posta elettronica crittografato revocato.](../media/revoked-encrypted-email.png)

## <a name="how-to-revoke-an-encrypted-message-that-you-sent"></a><span data-ttu-id="00243-123">Come revocare un messaggio crittografato inviato</span><span class="sxs-lookup"><span data-stu-id="00243-123">How to revoke an encrypted message that you sent</span></span>

<span data-ttu-id="00243-124">È possibile revocare un messaggio inviato a un singolo destinatario che utilizza un account di social gmail.com o yahoo.com.</span><span class="sxs-lookup"><span data-stu-id="00243-124">You can revoke a mail that you sent to a single recipient that uses a social account such as gmail.com or yahoo.com.</span></span> <span data-ttu-id="00243-125">In altre parole, è possibile revocare un messaggio di posta elettronica inviato a un singolo destinatario che ha ricevuto l'esperienza basata su collegamento.</span><span class="sxs-lookup"><span data-stu-id="00243-125">In other words, you can revoke an email sent to a single recipient that received the link-based experience.</span></span>

<span data-ttu-id="00243-126">Non è possibile revocare un messaggio di posta elettronica inviato a un destinatario che usa un account aziendale o dell'istituto di istruzione da Office 365 o Microsoft 365 o un utente che usa un account Microsoft, ad esempio un account outlook.com.</span><span class="sxs-lookup"><span data-stu-id="00243-126">You cannot revoke a mail that you sent to a recipient that uses a work or school account from Office 365 or Microsoft 365 or a user that uses a Microsoft account, for example, an outlook.com account.</span></span> 

<span data-ttu-id="00243-127">Per revocare un messaggio crittografato inviato, eseguire la procedura seguente</span><span class="sxs-lookup"><span data-stu-id="00243-127">To revoke an encrypted message that you sent, complete these steps</span></span>

1. <span data-ttu-id="00243-128">In Outlook sul Web, nella **cartella Posta** inviata, passare al messaggio che si desidera revocare.</span><span class="sxs-lookup"><span data-stu-id="00243-128">In Outlook on the web, in your **Sent** folder, browse to the message you want to revoke.</span></span>

   <span data-ttu-id="00243-129">Se la posta è revocabile, nella parte superiore del messaggio verrà visualizzato il collegamento "Rimuovi accesso esterno".</span><span class="sxs-lookup"><span data-stu-id="00243-129">If the mail is revocable, you'll see the "Remove external access" link at the top of the message.</span></span>

    :::image type="content" source="../media/infoprotect-email-encryption/adhocencryptionrevokesentmsg.png" alt-text="Screenshot showing encrypted mail that you want to revoke in Outlook on the web.":::

2. <span data-ttu-id="00243-131">Fare **clic su Rimuovi accesso esterno** per revocare il messaggio.</span><span class="sxs-lookup"><span data-stu-id="00243-131">Click **Remove external access** to revoke the message.</span></span>

   <span data-ttu-id="00243-132">Il messaggio mostra che il suo stato è stato revocato.</span><span class="sxs-lookup"><span data-stu-id="00243-132">The message shows that its status is revoked.</span></span>

   :::image type="content" source="../media/adhocencryptionrevokedmsg.png" alt-text="Screenshot showing revoked encrypted message in Outlook on the web.":::

## <a name="how-to-revoke-an-encrypted-message-as-an-administrator"></a><span data-ttu-id="00243-134">Come revocare un messaggio crittografato come amministratore</span><span class="sxs-lookup"><span data-stu-id="00243-134">How to revoke an encrypted message as an administrator</span></span>

<span data-ttu-id="00243-135">Gli amministratori di Microsoft 365 seguono questi passaggi generali per revocare un messaggio di posta elettronica crittografato idoneo:</span><span class="sxs-lookup"><span data-stu-id="00243-135">Microsoft 365 administrators follow these general steps to revoke an eligible encrypted email:</span></span>

- <span data-ttu-id="00243-136">Ottenere l'ID messaggio del messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="00243-136">Get the Message ID of the email.</span></span>
- <span data-ttu-id="00243-137">Verificare che sia possibile revocare il messaggio.</span><span class="sxs-lookup"><span data-stu-id="00243-137">Verify that you can revoke the message.</span></span>
- <span data-ttu-id="00243-138">Revocare il messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="00243-138">Revoke the mail.</span></span>

### <a name="step-1-obtain-the-message-id-of-the-email"></a><span data-ttu-id="00243-139">Passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="00243-139">Step 1.</span></span> <span data-ttu-id="00243-140">Ottenere l'ID messaggio del messaggio di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="00243-140">Obtain the Message ID of the email</span></span>

<span data-ttu-id="00243-141">Prima di poter revocare un messaggio crittografato, raccogliere l'ID del messaggio.</span><span class="sxs-lookup"><span data-stu-id="00243-141">Before you can revoke an encrypted mail, gather the Message ID of the mail.</span></span> <span data-ttu-id="00243-142">MessageId è in genere nel formato seguente:</span><span class="sxs-lookup"><span data-stu-id="00243-142">The MessageId is usually of the format:</span></span>

`<xxxxxxxxxxxxxxxxxxxxxxx@xxxxxx.xxxx.prod.outlook.com>`  

<span data-ttu-id="00243-143">Esistono diversi modi per trovare l'ID messaggio del messaggio di posta elettronica che si desidera revocare.</span><span class="sxs-lookup"><span data-stu-id="00243-143">There are multiple ways to find the Message ID of the email that you want to revoke.</span></span> <span data-ttu-id="00243-144">In questa sezione vengono descritte due opzioni, ma è possibile utilizzare qualsiasi metodo che fornisce l'ID.</span><span class="sxs-lookup"><span data-stu-id="00243-144">This section describes a couple of options, but you can use any method that provides the ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-message-trace-in-the-security-amp-compliance-center"></a><span data-ttu-id="00243-145">Per identificare l'ID messaggio del messaggio di posta elettronica che si desidera revocare utilizzando Traccia messaggio nel Centro &amp; sicurezza e conformità</span><span class="sxs-lookup"><span data-stu-id="00243-145">To identify the Message ID of the email you want to revoke by using Message Trace in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="00243-146">Cercare il messaggio di posta elettronica in base al mittente o al destinatario usando Traccia nuovo [messaggio nel Centro sicurezza & conformità.](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/)</span><span class="sxs-lookup"><span data-stu-id="00243-146">Search for the email by sender or recipient using [New Message Trace in Security & Compliance Center](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/).</span></span>

2. <span data-ttu-id="00243-147">Dopo aver individuato il messaggio di posta elettronica, selezionarlo per visualizzare il riquadro dei dettagli **di Traccia messaggio.**</span><span class="sxs-lookup"><span data-stu-id="00243-147">Once you've located the email, select it to bring up the **Message trace details** pane.</span></span> <span data-ttu-id="00243-148">Espandere **Ulteriori informazioni per** individuare l'ID messaggio.</span><span class="sxs-lookup"><span data-stu-id="00243-148">Expand **More Information** to locate the Message ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-office-message-encryption-reports-in-the-security-amp-compliance-center"></a><span data-ttu-id="00243-149">Per identificare l'ID messaggio del messaggio di posta elettronica che si desidera revocare utilizzando i report di Crittografia messaggi di Office nel Centro &amp; sicurezza e conformità</span><span class="sxs-lookup"><span data-stu-id="00243-149">To identify the Message ID of the email you want to revoke by using Office Message Encryption reports in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="00243-150">Nel Centro sicurezza &amp; e conformità passare al report crittografia dei **messaggi.**</span><span class="sxs-lookup"><span data-stu-id="00243-150">In the Security &amp; Compliance Center, navigate to the **Message encryption report**.</span></span> <span data-ttu-id="00243-151">Per informazioni su questo report, vedere Visualizzare i report [di sicurezza della posta elettronica nel Centro sicurezza e &amp; conformità.](../security/office-365-security/view-email-security-reports.md)</span><span class="sxs-lookup"><span data-stu-id="00243-151">For information on this report, see [View email security reports in the Security &amp; Compliance Center](../security/office-365-security/view-email-security-reports.md).</span></span>

2. <span data-ttu-id="00243-152">Scegliere la **tabella Visualizza dettagli** e identificare il messaggio che si desidera revocare.</span><span class="sxs-lookup"><span data-stu-id="00243-152">Choose the **View details** table and identify the message that you want to revoke.</span></span>

3. <span data-ttu-id="00243-153">Fare doppio clic sul messaggio per visualizzare i dettagli che includono l'ID messaggio.</span><span class="sxs-lookup"><span data-stu-id="00243-153">Double-click the message to view details that include the Message ID.</span></span>

### <a name="step-2-verify-that-the-mail-is-revocable"></a><span data-ttu-id="00243-154">Passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="00243-154">Step 2.</span></span> <span data-ttu-id="00243-155">Verificare che la posta sia revocabile</span><span class="sxs-lookup"><span data-stu-id="00243-155">Verify that the mail is revocable</span></span>

<span data-ttu-id="00243-156">Per verificare se è possibile revocare un messaggio, verificare se il campo  Stato revoca è visibile nel report Crittografia, nella tabella Dettagli del Centro &amp; sicurezza e conformità.</span><span class="sxs-lookup"><span data-stu-id="00243-156">To verify whether you can revoke a message, check whether the Revocation Status field is visible in the Encryption report, in the **Details** table in the Security &amp; Compliance Center.</span></span>

<span data-ttu-id="00243-157">Per verificare se è possibile revocare un determinato messaggio di posta elettronica utilizzando Windows PowerShell, completare questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="00243-157">To verify whether you can revoke a particular email message by using Windows PowerShell, complete these steps.</span></span>

1. <span data-ttu-id="00243-158">Utilizzando un account aziendale o dell'istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione, avviare una sessione Windows PowerShell e connettersi a Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="00243-158">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="00243-159">Per istruzioni, vedere [Connettersi a PowerShell di Exchange Online](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="00243-159">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="00243-160">Eseguire il cmdlet Get-OMEMessageStatus seguente:</span><span class="sxs-lookup"><span data-stu-id="00243-160">Run the Get-OMEMessageStatus cmdlet as follows:</span></span>

     ```powershell
     Get-OMEMessageStatus -MessageId "<message id>" | ft -a  Subject, IsRevocable
     ```

   <span data-ttu-id="00243-161">Questo comando restituisce l'oggetto del messaggio e indica se il messaggio è revocabile.</span><span class="sxs-lookup"><span data-stu-id="00243-161">This command returns the subject of the message and whether the message is revocable.</span></span> <span data-ttu-id="00243-162">Ad esempio,</span><span class="sxs-lookup"><span data-stu-id="00243-162">For example,</span></span>

     ```console
     Subject        IsRevocable
     -------        -----------
     "Test message" True
     ```

### <a name="step-3-revoke-the-mail"></a><span data-ttu-id="00243-163">Passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="00243-163">Step 3.</span></span> <span data-ttu-id="00243-164">Revocare la posta</span><span class="sxs-lookup"><span data-stu-id="00243-164">Revoke the mail</span></span>

<span data-ttu-id="00243-165">Una volta che si conosce l'ID del messaggio di posta elettronica che si desidera revocare ed è stato verificato che il messaggio è revocabile, è possibile revocare il messaggio di posta elettronica utilizzando il Centro sicurezza conformità o &amp; Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="00243-165">Once you know the Message ID of the email you want to revoke, and you have verified that the message is revocable, you can revoke the email using the Security &amp; Compliance Center or Windows PowerShell.</span></span>

<span data-ttu-id="00243-166">Per revocare il messaggio tramite il Centro &amp; sicurezza e conformità</span><span class="sxs-lookup"><span data-stu-id="00243-166">To revoke the message using the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="00243-167">Usando un account aziendale o dell'istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione, connettersi al Centro sicurezza & conformità.</span><span class="sxs-lookup"><span data-stu-id="00243-167">Using a work or school account that has global administrator permissions in your organization, connect to the Security & Compliance Center.</span></span>

2. <span data-ttu-id="00243-168">Nel report **Crittografia,** nella **tabella Dettagli** per il messaggio, scegliere **Revoca messaggio.**</span><span class="sxs-lookup"><span data-stu-id="00243-168">In the **Encryption report**, in the **Details** table for the message, choose **Revoke message**.</span></span>

<span data-ttu-id="00243-169">Per revocare un messaggio di posta elettronica Windows PowerShell, utilizzare il cmdlet Set-OMEMessageRevocation seguente.</span><span class="sxs-lookup"><span data-stu-id="00243-169">To revoke an email by using Windows PowerShell, use the Set-OMEMessageRevocation cmdlet.</span></span>

1. <span data-ttu-id="00243-170">Utilizzando un account aziendale o dell'istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione, [connettersi a PowerShell di Exchange Online.](https://aka.ms/exopowershell)</span><span class="sxs-lookup"><span data-stu-id="00243-170">Using a work or school account that has global administrator permissions in your organization, [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="00243-171">Eseguire il cmdlet Set-OMEMessageRevocation seguente:</span><span class="sxs-lookup"><span data-stu-id="00243-171">Run the Set-OMEMessageRevocation cmdlet as follows:</span></span>

    ```powershell
    Set-OMEMessageRevocation -Revoke $true -MessageId "<messageId>"
    ```

3. <span data-ttu-id="00243-172">Per verificare se il messaggio di posta elettronica è stato revocato, eseguire il cmdlet Get-OMEMessageStatus seguente:</span><span class="sxs-lookup"><span data-stu-id="00243-172">To check whether the email was revoked, run the Get-OMEMessageStatus cmdlet as follows:</span></span>

    ```powershell
    Get-OMEMessageStatus -MessageId "<messageId>" | ft -a  Subject, Revoked
    ```

    <span data-ttu-id="00243-173">Se la revoca ha avuto esito positivo, il cmdlet restituisce il risultato seguente:</span><span class="sxs-lookup"><span data-stu-id="00243-173">If revocation was successful, the cmdlet returns the following result:</span></span>  

     ```console
     Revoked: True
     ```

## <a name="more-information-about-office-365-advanced-message-encryption"></a><span data-ttu-id="00243-174">Ulteriori informazioni sulla crittografia avanzata dei messaggi di Office 365</span><span class="sxs-lookup"><span data-stu-id="00243-174">More information about Office 365 Advanced Message Encryption</span></span>

- [<span data-ttu-id="00243-175">Office 365 Advanced Message Encryption</span><span class="sxs-lookup"><span data-stu-id="00243-175">Office 365 Advanced Message Encryption</span></span>](ome-advanced-message-encryption.md)

- [<span data-ttu-id="00243-176">Office 365 Advanced Message Encryption - Scadenza della posta elettronica</span><span class="sxs-lookup"><span data-stu-id="00243-176">Office 365 Advanced Message Encryption - email expiration</span></span>](ome-advanced-expiration.md)

- [<span data-ttu-id="00243-177">Criteri dei messaggi e descrizione del servizio di conformità</span><span class="sxs-lookup"><span data-stu-id="00243-177">Message policy and compliance service description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)
