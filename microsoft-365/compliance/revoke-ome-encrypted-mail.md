---
title: Revoca della posta elettronica crittografata tramite crittografia avanzata dei messaggi
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
description: Come amministratore e come mittente del messaggio, è possibile revocare alcuni messaggi di posta elettronica crittografati con la crittografia avanzata dei messaggi di Office 365.
ms.openlocfilehash: 79ab3ef801d4d19317cbf1416d858de74d9f1393
ms.sourcegitcommit: 22dab0f7604cc057a062698005ff901d40771692
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/25/2020
ms.locfileid: "46868948"
---
# <a name="revoke-email-encrypted-by-advanced-message-encryption"></a><span data-ttu-id="b54b1-103">Revoca della posta elettronica crittografata tramite crittografia avanzata dei messaggi</span><span class="sxs-lookup"><span data-stu-id="b54b1-103">Revoke email encrypted by Advanced Message Encryption</span></span>

<span data-ttu-id="b54b1-104">La revoca del messaggio di posta elettronica viene offerta come parte della crittografia avanzata dei messaggi di Office 365.</span><span class="sxs-lookup"><span data-stu-id="b54b1-104">Email revocation is offered as part of Office 365 Advanced Message Encryption.</span></span> <span data-ttu-id="b54b1-105">La crittografia avanzata dei messaggi di Office 365 è inclusa in [microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (nonprofit staff pricing), Office 365 Enterprise E5 (nonprofit staff pricing) e Office 365 Education a5.</span><span class="sxs-lookup"><span data-stu-id="b54b1-105">Office 365 Advanced Message Encryption is included in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (Nonprofit Staff Pricing), Office 365 Enterprise E5 (Nonprofit Staff Pricing), and Office 365 Education A5.</span></span> <span data-ttu-id="b54b1-106">Se l'organizzazione dispone di un abbonamento che non include la crittografia dei messaggi avanzata di Office 365, è possibile acquistarla con il componente aggiuntivo SKU Microsoft 365 E5 Compliance per Microsoft 365 E3, Microsoft 365 E3 (nonprofit staff pricing) o il componente aggiuntivo Office 365 Advanced Compliance SKU per Microsoft 365 E3, Microsoft 365 E3 (nonprofit staff pricing) o Office 365 SKU.</span><span class="sxs-lookup"><span data-stu-id="b54b1-106">If your organization has a subscription that does not include Office 365 Advanced Message Encryption, you can purchase it with the Microsoft 365 E5 Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or the Office 365 Advanced Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or Office 365 SKUs.</span></span>

<span data-ttu-id="b54b1-107">Questo articolo fa parte di una serie più ampia di articoli sulla [crittografia dei messaggi di Office 365](ome.md).</span><span class="sxs-lookup"><span data-stu-id="b54b1-107">This article is part of a larger series of articles about [Office 365 Message Encryption](ome.md).</span></span>

<span data-ttu-id="b54b1-108">Se un messaggio è stato crittografato utilizzando la crittografia avanzata dei messaggi di Office 365 e si è un amministratore di Microsoft 365 o si è il mittente del messaggio, è possibile revocare il messaggio in determinate condizioni.</span><span class="sxs-lookup"><span data-stu-id="b54b1-108">If a message was encrypted using Office 365 Advanced Message Encryption, and you are a Microsoft 365 admin or you are the sender of the message, you can revoke the message under certain conditions.</span></span> <span data-ttu-id="b54b1-109">Gli amministratori revocano i messaggi tramite PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b54b1-109">Admins revoke messages using PowerShell.</span></span> <span data-ttu-id="b54b1-110">Come mittente, è possibile revocare un messaggio inviato direttamente da Outlook sul Web.</span><span class="sxs-lookup"><span data-stu-id="b54b1-110">As a sender, you revoke a message that you sent directly from Outlook on the web.</span></span> <span data-ttu-id="b54b1-111">In questo articolo vengono descritte le circostanze in cui la revoca è possibile e come procedere.</span><span class="sxs-lookup"><span data-stu-id="b54b1-111">This article describes the circumstances under which revocation is possible and how to do it.</span></span>
  
## <a name="encrypted-emails-that-you-can-revoke"></a><span data-ttu-id="b54b1-112">Messaggi di posta elettronica crittografati che è possibile revocare</span><span class="sxs-lookup"><span data-stu-id="b54b1-112">Encrypted emails that you can revoke</span></span>

<span data-ttu-id="b54b1-113">Gli amministratori e i mittenti dei messaggi possono revocare i messaggi di posta elettronica crittografati se il destinatario ha ricevuto una e-mail crittografata basata sul collegamento.</span><span class="sxs-lookup"><span data-stu-id="b54b1-113">Admins and message senders can revoke encrypted emails if the recipient received a link-based, branded encrypted email.</span></span> <span data-ttu-id="b54b1-114">Se il destinatario ha ricevuto un'esperienza nativa in linea in un client di Outlook supportato, non è possibile revocare il messaggio.</span><span class="sxs-lookup"><span data-stu-id="b54b1-114">If the recipient received a native inline experience in a supported Outlook client, then you can't revoke the message.</span></span>

<span data-ttu-id="b54b1-115">Se un destinatario riceve un'esperienza basata sul collegamento o un'esperienza in linea dipende dal tipo di identità del destinatario: Office 365 e destinatari dell'account Microsoft (ad esempio, gli utenti di outlook.com) ricevono un'esperienza in linea nei client Outlook supportati.</span><span class="sxs-lookup"><span data-stu-id="b54b1-115">Whether a recipient receives a link-based experience or an inline experience depends on the recipient identity type: Office 365 and Microsoft account recipients (for example, outlook.com users) get an inline experience in supported Outlook clients.</span></span> <span data-ttu-id="b54b1-116">Tutti gli altri tipi di destinatari, ad esempio i destinatari di Gmail e Yahoo, ricevono un'esperienza basata sul collegamento.</span><span class="sxs-lookup"><span data-stu-id="b54b1-116">All other recipient types, such as Gmail and Yahoo recipients, get a link-based experience.</span></span>

<span data-ttu-id="b54b1-117">Gli amministratori e i mittenti dei messaggi possono revocare i messaggi crittografati utilizzando la crittografia applicata direttamente da Outlook sul Web.</span><span class="sxs-lookup"><span data-stu-id="b54b1-117">Admins and message senders can revoke messages that are encrypted using encryption applied directly from Outlook on the web.</span></span> <span data-ttu-id="b54b1-118">Ad esempio, i messaggi vengono crittografati con l'opzione solo crittografia.</span><span class="sxs-lookup"><span data-stu-id="b54b1-118">For example, messages encrypted with the Encrypt Only option.</span></span>

:::image type="content" source="../media/adhocencryptionrevoke.png" alt-text="Schermata che mostra solo l'opzione Crittografa solo in Outlook sul Web.":::

## <a name="recipient-experience-for-revoked-encrypted-emails"></a><span data-ttu-id="b54b1-120">Esperienza dei destinatari per i messaggi di posta elettronica crittografati</span><span class="sxs-lookup"><span data-stu-id="b54b1-120">Recipient experience for revoked encrypted emails</span></span>

<span data-ttu-id="b54b1-121">Dopo che un messaggio di posta elettronica è stato revocato, il destinatario riceve un errore quando accede alla posta elettronica crittografata tramite il portale di crittografia dei messaggi di Office 365: "il messaggio è stato revocato dal mittente".</span><span class="sxs-lookup"><span data-stu-id="b54b1-121">Once an email has been revoked, the recipient receives an error when they access the encrypted email through the Office 365 Message Encryption portal: "The message has been revoked by the sender".</span></span>

![Schermata che visualizza un messaggio di posta elettronica crittografato revocato.](../media/revoked-encrypted-email.png)

## <a name="how-to-revoke-an-encrypted-message-that-you-sent"></a><span data-ttu-id="b54b1-123">Come revocare un messaggio crittografato inviato</span><span class="sxs-lookup"><span data-stu-id="b54b1-123">How to revoke an encrypted message that you sent</span></span>

<span data-ttu-id="b54b1-124">Per revocare un messaggio crittografato inviato, eseguire la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="b54b1-124">To revoke an encrypted message that you sent, complete these steps</span></span>

1. <span data-ttu-id="b54b1-125">In Outlook sul Web, nella cartella **inviata** , passare al messaggio che si desidera revocare.</span><span class="sxs-lookup"><span data-stu-id="b54b1-125">In Outlook on the web, in your **Sent** folder, browse to the message you want to revoke.</span></span>

   <span data-ttu-id="b54b1-126">Se la posta è revocabile, vedrai il collegamento "Rimuovi accesso esterno" nella parte superiore del messaggio.</span><span class="sxs-lookup"><span data-stu-id="b54b1-126">If the mail is revocable, you'll see the "Remove external access" link at the top of the message.</span></span>

    :::image type="content" source="../media/infoprotect-email-encryption/adhocencryptionrevokesentmsg.png" alt-text="Schermata che mostra il messaggio crittografato che si desidera revocare in Outlook sul Web.":::

2. <span data-ttu-id="b54b1-128">Fare clic su **Rimuovi accesso esterno** per revocare il messaggio.</span><span class="sxs-lookup"><span data-stu-id="b54b1-128">Click **Remove external access** to revoke the message.</span></span>

   <span data-ttu-id="b54b1-129">Il messaggio indica che lo stato è stato revocato.</span><span class="sxs-lookup"><span data-stu-id="b54b1-129">The message shows that its status is revoked.</span></span>

   :::image type="content" source="../media/adhocencryptionrevokedmsg.png" alt-text="Schermata in cui viene visualizzato il messaggio crittografato revocato in Outlook sul Web.":::

## <a name="how-to-revoke-an-encrypted-message-as-an-administrator"></a><span data-ttu-id="b54b1-131">Come revocare un messaggio crittografato come amministratore</span><span class="sxs-lookup"><span data-stu-id="b54b1-131">How to revoke an encrypted message as an administrator</span></span>

<span data-ttu-id="b54b1-132">Gli amministratori di Microsoft 365 seguono queste procedure generali per revocare un messaggio di posta elettronica crittografato idoneo:</span><span class="sxs-lookup"><span data-stu-id="b54b1-132">Microsoft 365 administrators follow these general steps to revoke an eligible encrypted email:</span></span>

- <span data-ttu-id="b54b1-133">Ottenere l'ID del messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="b54b1-133">Get the Message ID of the email.</span></span>
- <span data-ttu-id="b54b1-134">Verificare che sia possibile revocare il messaggio.</span><span class="sxs-lookup"><span data-stu-id="b54b1-134">Verify that you can revoke the message.</span></span>
- <span data-ttu-id="b54b1-135">Revocare la posta.</span><span class="sxs-lookup"><span data-stu-id="b54b1-135">Revoke the mail.</span></span>

### <a name="step-1-obtain-the-message-id-of-the-email"></a><span data-ttu-id="b54b1-136">Passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="b54b1-136">Step 1.</span></span> <span data-ttu-id="b54b1-137">Ottenere l'ID del messaggio di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="b54b1-137">Obtain the Message ID of the email</span></span>

<span data-ttu-id="b54b1-138">Prima di poter revocare una posta crittografata, raccogliere l'ID del messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="b54b1-138">Before you can revoke an encrypted mail, gather the Message ID of the mail.</span></span> <span data-ttu-id="b54b1-139">Il MessageId è in genere del formato seguente:</span><span class="sxs-lookup"><span data-stu-id="b54b1-139">The MessageId is usually of the format:</span></span>

`<xxxxxxxxxxxxxxxxxxxxxxx@xxxxxx.xxxx.prod.outlook.com>`  

<span data-ttu-id="b54b1-140">Sono disponibili diversi modi per individuare l'ID del messaggio di posta elettronica che si desidera revocare.</span><span class="sxs-lookup"><span data-stu-id="b54b1-140">There are multiple ways to find the Message ID of the email that you want to revoke.</span></span> <span data-ttu-id="b54b1-141">In questa sezione vengono descritte alcune opzioni, ma è possibile utilizzare qualsiasi metodo che fornisca l'ID.</span><span class="sxs-lookup"><span data-stu-id="b54b1-141">This section describes a couple of options, but you can use any method that provides the ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-message-trace-in-the-security-amp-compliance-center"></a><span data-ttu-id="b54b1-142">Per identificare l'ID del messaggio di posta elettronica che si desidera revocare tramite la traccia dei messaggi nel &amp; Centro sicurezza e conformità</span><span class="sxs-lookup"><span data-stu-id="b54b1-142">To identify the Message ID of the email you want to revoke by using Message Trace in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="b54b1-143">Cercare il messaggio di posta elettronica dal mittente o dal destinatario utilizzando la [nuova traccia dei messaggi nel centro sicurezza & conformità](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/).</span><span class="sxs-lookup"><span data-stu-id="b54b1-143">Search for the email by sender or recipient using [New Message Trace in Security & Compliance Center](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/).</span></span>

2. <span data-ttu-id="b54b1-144">Dopo aver individuato il messaggio di posta elettronica, selezionarlo per visualizzare il riquadro **Dettagli traccia dei messaggi** .</span><span class="sxs-lookup"><span data-stu-id="b54b1-144">Once you've located the email, select it to bring up the **Message trace details** pane.</span></span> <span data-ttu-id="b54b1-145">Espandere **ulteriori informazioni** per individuare l'ID del messaggio.</span><span class="sxs-lookup"><span data-stu-id="b54b1-145">Expand **More Information** to locate the Message ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-office-message-encryption-reports-in-the-security-amp-compliance-center"></a><span data-ttu-id="b54b1-146">Per identificare l'ID del messaggio di posta elettronica che si desidera revocare utilizzando i rapporti di crittografia dei messaggi di Office nel centro sicurezza e &amp; conformità</span><span class="sxs-lookup"><span data-stu-id="b54b1-146">To identify the Message ID of the email you want to revoke by using Office Message Encryption reports in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="b54b1-147">Nel centro sicurezza &amp; e conformità, passare al **rapporto di crittografia dei messaggi**.</span><span class="sxs-lookup"><span data-stu-id="b54b1-147">In the Security &amp; Compliance Center, navigate to the **Message encryption report**.</span></span> <span data-ttu-id="b54b1-148">Per informazioni su questo report, vedere [visualizzare i report di sicurezza della posta elettronica nel &amp; Centro sicurezza e conformità](../security/office-365-security/view-email-security-reports.md).</span><span class="sxs-lookup"><span data-stu-id="b54b1-148">For information on this report, see [View email security reports in the Security &amp; Compliance Center](../security/office-365-security/view-email-security-reports.md).</span></span>

2. <span data-ttu-id="b54b1-149">Scegliere la tabella **Visualizza dettagli** e identificare il messaggio che si desidera revocare.</span><span class="sxs-lookup"><span data-stu-id="b54b1-149">Choose the **View details** table and identify the message that you want to revoke.</span></span>

3. <span data-ttu-id="b54b1-150">Fare doppio clic sul messaggio per visualizzare i dettagli che includono l'ID del messaggio.</span><span class="sxs-lookup"><span data-stu-id="b54b1-150">Double-click the message to view details that include the Message ID.</span></span>

### <a name="step-2-verify-that-the-mail-is-revocable"></a><span data-ttu-id="b54b1-151">Passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="b54b1-151">Step 2.</span></span> <span data-ttu-id="b54b1-152">Verificare che la posta sia revocabile</span><span class="sxs-lookup"><span data-stu-id="b54b1-152">Verify that the mail is revocable</span></span>

<span data-ttu-id="b54b1-153">Per verificare se è possibile revocare un messaggio, controllare se il campo stato revoca è visibile nel rapporto di crittografia, nella tabella **Details** del Centro sicurezza e &amp; conformità.</span><span class="sxs-lookup"><span data-stu-id="b54b1-153">To verify whether you can revoke a message, check whether the Revocation Status field is visible in the Encryption report, in the **Details** table in the Security &amp; Compliance Center.</span></span>

<span data-ttu-id="b54b1-154">Per verificare se è possibile revocare un messaggio di posta elettronica specifico utilizzando Windows PowerShell, eseguire la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="b54b1-154">To verify whether you can revoke a particular email message by using Windows PowerShell, complete these steps.</span></span>

1. <span data-ttu-id="b54b1-155">Utilizzo di un account aziendale o dell'Istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione, avviare una sessione di Windows PowerShell e connettersi a Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="b54b1-155">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="b54b1-156">Per istruzioni, vedere [Connettersi a PowerShell di Exchange Online](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="b54b1-156">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="b54b1-157">Eseguire il cmdlet Get-OMEMessageStatus nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="b54b1-157">Run the Get-OMEMessageStatus cmdlet as follows:</span></span>

     ```powershell
     Get-OMEMessageStatus -MessageId "<message id>" | ft -a  Subject, IsRevocable
     ```

   <span data-ttu-id="b54b1-158">Questo comando restituisce l'oggetto del messaggio e indica se il messaggio è revocabile.</span><span class="sxs-lookup"><span data-stu-id="b54b1-158">This command returns the subject of the message and whether the message is revocable.</span></span> <span data-ttu-id="b54b1-159">Ad esempio,</span><span class="sxs-lookup"><span data-stu-id="b54b1-159">For example,</span></span>

     ```text
     Subject        IsRevocable
     -------        -----------
     "Test message" True
     ```

### <a name="step-3-revoke-the-mail"></a><span data-ttu-id="b54b1-160">Passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="b54b1-160">Step 3.</span></span> <span data-ttu-id="b54b1-161">Revocare la posta elettronica</span><span class="sxs-lookup"><span data-stu-id="b54b1-161">Revoke the mail</span></span>

<span data-ttu-id="b54b1-162">Una volta che si conosce l'ID del messaggio di posta elettronica che si desidera revocare ed è stato verificato che il messaggio è revocabile, è possibile revocare la posta elettronica utilizzando il &amp; Centro sicurezza e conformità di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b54b1-162">Once you know the Message ID of the email you want to revoke, and you have verified that the message is revocable, you can revoke the email using the Security &amp; Compliance Center or Windows PowerShell.</span></span>

<span data-ttu-id="b54b1-163">Per revocare il messaggio utilizzando il Centro sicurezza e &amp; conformità</span><span class="sxs-lookup"><span data-stu-id="b54b1-163">To revoke the message using the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="b54b1-164">Se si utilizza un account aziendale o dell'Istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione, connettersi al centro sicurezza & Compliance.</span><span class="sxs-lookup"><span data-stu-id="b54b1-164">Using a work or school account that has global administrator permissions in your organization, connect to the Security & Compliance Center.</span></span>

2. <span data-ttu-id="b54b1-165">Nel **rapporto di crittografia**, nella tabella **Details** del messaggio, scegliere **revoca messaggio**.</span><span class="sxs-lookup"><span data-stu-id="b54b1-165">In the **Encryption report**, in the **Details** table for the message, choose **Revoke message**.</span></span>

<span data-ttu-id="b54b1-166">Per revocare un messaggio di posta elettronica utilizzando Windows PowerShell, utilizzare il cmdlet Set-OMEMessageRevocation.</span><span class="sxs-lookup"><span data-stu-id="b54b1-166">To revoke an email by using Windows PowerShell, use the Set-OMEMessageRevocation cmdlet.</span></span>

1. <span data-ttu-id="b54b1-167">Se si utilizza un account aziendale o dell'Istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione, [connettersi a PowerShell di Exchange Online](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="b54b1-167">Using a work or school account that has global administrator permissions in your organization, [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="b54b1-168">Eseguire il cmdlet Set-OMEMessageRevocation come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="b54b1-168">Run the Set-OMEMessageRevocation cmdlet as follows:</span></span>

    ```powershell
    Set-OMEMessageRevocation -Revoke $true -MessageId "<messageId>"
    ```

3. <span data-ttu-id="b54b1-169">Per verificare se il messaggio di posta elettronica è stato revocato, eseguire il cmdlet Get-OMEMessageStatus come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="b54b1-169">To check whether the email was revoked, run the Get-OMEMessageStatus cmdlet as follows:</span></span>

    ```powershell
    Get-OMEMessageStatus -MessageId "<messageId>" | ft -a  Subject, Revoked
    ```

    <span data-ttu-id="b54b1-170">Se la revoca ha avuto esito positivo, il cmdlet restituisce il risultato seguente:</span><span class="sxs-lookup"><span data-stu-id="b54b1-170">If revocation was successful, the cmdlet returns the following result:</span></span>  

     ```text
     Revoked: True
     ```

## <a name="more-information-about-office-365-advanced-message-encryption"></a><span data-ttu-id="b54b1-171">Ulteriori informazioni sulla crittografia avanzata dei messaggi di Office 365</span><span class="sxs-lookup"><span data-stu-id="b54b1-171">More information about Office 365 Advanced Message Encryption</span></span>

- [<span data-ttu-id="b54b1-172">Office 365 Advanced Message Encryption</span><span class="sxs-lookup"><span data-stu-id="b54b1-172">Office 365 Advanced Message Encryption</span></span>](ome-advanced-message-encryption.md)

- [<span data-ttu-id="b54b1-173">Crittografia messaggi avanzata di Office 365-scadenza del messaggio di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="b54b1-173">Office 365 Advanced Message Encryption - email expiration</span></span>](ome-advanced-expiration.md)

- [<span data-ttu-id="b54b1-174">Descrizione del servizio criteri di conformità e del messaggio</span><span class="sxs-lookup"><span data-stu-id="b54b1-174">Message policy and compliance service description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)
