---
title: Revocare la posta elettronica crittografata dalla crittografia avanzata dei messaggi
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
description: Come amministratore e come mittente del messaggio, è possibile revocare determinati messaggi di posta elettronica crittografati con Crittografia avanzata messaggi di Office 365.
ms.openlocfilehash: 340a9e73dba50e28223ee561db749a089c649df6
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051718"
---
# <a name="revoke-email-encrypted-by-advanced-message-encryption"></a><span data-ttu-id="27db4-103">Revocare la posta elettronica crittografata dalla crittografia avanzata dei messaggi</span><span class="sxs-lookup"><span data-stu-id="27db4-103">Revoke email encrypted by Advanced Message Encryption</span></span>

<span data-ttu-id="27db4-104">La revoca della posta elettronica viene offerta come parte della crittografia avanzata dei messaggi di Office 365.</span><span class="sxs-lookup"><span data-stu-id="27db4-104">Email revocation is offered as part of Office 365 Advanced Message Encryption.</span></span> <span data-ttu-id="27db4-105">La crittografia avanzata dei messaggi di Office 365 è inclusa in [Microsoft 365 Enterprise E5,](https://www.microsoft.com/microsoft-365/enterprise/home)Office 365 E5, Microsoft 365 E5 (prezzi per il personale non profit), Office 365 Enterprise E5 (prezzi per il personale no profit) e Office 365 Education A5.</span><span class="sxs-lookup"><span data-stu-id="27db4-105">Office 365 Advanced Message Encryption is included in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (Nonprofit Staff Pricing), Office 365 Enterprise E5 (Nonprofit Staff Pricing), and Office 365 Education A5.</span></span> <span data-ttu-id="27db4-106">Se l'organizzazione ha una sottoscrizione che non include La crittografia avanzata dei messaggi di Office 365, è possibile acquistarla con il componente aggiuntivo SKU di conformità di Microsoft 365 E5 per Microsoft 365 E3, Microsoft 365 E3 (Prezzi per il personale non profit) o il componente aggiuntivo SKU conformità avanzata di Office 365 per Microsoft 365 E3, Microsoft 365 E3 (Prezzi del personale nonprofit) o SKU di Office 365.</span><span class="sxs-lookup"><span data-stu-id="27db4-106">If your organization has a subscription that does not include Office 365 Advanced Message Encryption, you can purchase it with the Microsoft 365 E5 Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or the Office 365 Advanced Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or Office 365 SKUs.</span></span>

<span data-ttu-id="27db4-107">Questo articolo fa parte di una serie più ampia di articoli sulla crittografia dei messaggi di [Office 365.](ome.md)</span><span class="sxs-lookup"><span data-stu-id="27db4-107">This article is part of a larger series of articles about [Office 365 Message Encryption](ome.md).</span></span>

<span data-ttu-id="27db4-108">Se un messaggio è stato crittografato utilizzando La crittografia avanzata dei messaggi di Office 365 e si è un amministratore di Microsoft 365 o si è il mittente del messaggio, è possibile revocare il messaggio in determinate condizioni.</span><span class="sxs-lookup"><span data-stu-id="27db4-108">If a message was encrypted using Office 365 Advanced Message Encryption, and you are a Microsoft 365 admin or you are the sender of the message, you can revoke the message under certain conditions.</span></span> <span data-ttu-id="27db4-109">Gli amministratori revocano i messaggi tramite PowerShell.</span><span class="sxs-lookup"><span data-stu-id="27db4-109">Admins revoke messages using PowerShell.</span></span> <span data-ttu-id="27db4-110">Come mittente, si revoca un messaggio inviato direttamente da Outlook sul Web.</span><span class="sxs-lookup"><span data-stu-id="27db4-110">As a sender, you revoke a message that you sent directly from Outlook on the web.</span></span> <span data-ttu-id="27db4-111">In questo articolo vengono descritte le circostanze in cui la revoca è possibile e come farlo.</span><span class="sxs-lookup"><span data-stu-id="27db4-111">This article describes the circumstances under which revocation is possible and how to do it.</span></span>
  
## <a name="encrypted-emails-that-you-can-revoke"></a><span data-ttu-id="27db4-112">Messaggi di posta elettronica crittografati che è possibile revocare</span><span class="sxs-lookup"><span data-stu-id="27db4-112">Encrypted emails that you can revoke</span></span>

<span data-ttu-id="27db4-113">Gli amministratori e i mittenti dei messaggi possono revocare i messaggi di posta elettronica crittografati se il destinatario ha ricevuto un messaggio di posta elettronica crittografato basato su collegamento e personalizzato.</span><span class="sxs-lookup"><span data-stu-id="27db4-113">Admins and message senders can revoke encrypted emails if the recipient received a link-based, branded encrypted email.</span></span> <span data-ttu-id="27db4-114">Se il destinatario ha ricevuto un'esperienza nativa in linea in un client Di Outlook supportato, non è possibile revocare il messaggio.</span><span class="sxs-lookup"><span data-stu-id="27db4-114">If the recipient received a native inline experience in a supported Outlook client, then you can't revoke the message.</span></span>

<span data-ttu-id="27db4-115">Se un destinatario riceve un'esperienza basata su collegamento o un'esperienza in linea dipende dal tipo di identità del destinatario: i destinatari dell'account Di Office 365 e Microsoft (ad esempio, gli utenti di outlook.com) ottengono un'esperienza in linea nei client di Outlook supportati.</span><span class="sxs-lookup"><span data-stu-id="27db4-115">Whether a recipient receives a link-based experience or an inline experience depends on the recipient identity type: Office 365 and Microsoft account recipients (for example, outlook.com users) get an inline experience in supported Outlook clients.</span></span> <span data-ttu-id="27db4-116">Tutti gli altri tipi di destinatari, ad esempio i destinatari Gmail e Yahoo, ottengono un'esperienza basata sui collegamenti.</span><span class="sxs-lookup"><span data-stu-id="27db4-116">All other recipient types, such as Gmail and Yahoo recipients, get a link-based experience.</span></span>

<span data-ttu-id="27db4-117">Gli amministratori e i mittenti dei messaggi possono revocare i messaggi crittografati utilizzando la crittografia applicata direttamente da Outlook sul Web.</span><span class="sxs-lookup"><span data-stu-id="27db4-117">Admins and message senders can revoke messages that are encrypted using encryption applied directly from Outlook on the web.</span></span> <span data-ttu-id="27db4-118">Ad esempio, i messaggi crittografati con l'opzione Solo crittografia.</span><span class="sxs-lookup"><span data-stu-id="27db4-118">For example, messages encrypted with the Encrypt Only option.</span></span>

:::image type="content" source="../media/adhocencryptionrevoke.png" alt-text="Screenshot che mostra l'opzione Crittografa solo in Outlook sul Web.":::

## <a name="recipient-experience-for-revoked-encrypted-emails"></a><span data-ttu-id="27db4-120">Esperienza del destinatario per i messaggi di posta elettronica crittografati revocati</span><span class="sxs-lookup"><span data-stu-id="27db4-120">Recipient experience for revoked encrypted emails</span></span>

<span data-ttu-id="27db4-121">Dopo la revoca di un messaggio di posta elettronica, il destinatario riceve un errore quando accede alla posta elettronica crittografata tramite il portale di crittografia dei messaggi di Office 365: "Il messaggio è stato revocato dal mittente".</span><span class="sxs-lookup"><span data-stu-id="27db4-121">Once an email has been revoked, the recipient receives an error when they access the encrypted email through the Office 365 Message Encryption portal: "The message has been revoked by the sender".</span></span>

![Screenshot che mostra un messaggio di posta elettronica crittografato revocato.](../media/revoked-encrypted-email.png)

## <a name="how-to-revoke-an-encrypted-message-that-you-sent"></a><span data-ttu-id="27db4-123">Come revocare un messaggio crittografato inviato</span><span class="sxs-lookup"><span data-stu-id="27db4-123">How to revoke an encrypted message that you sent</span></span>

<span data-ttu-id="27db4-124">È possibile revocare un messaggio inviato a un singolo destinatario che utilizza un account di social gmail.com o yahoo.com.</span><span class="sxs-lookup"><span data-stu-id="27db4-124">You can revoke a mail that you sent to a single recipient that uses a social account such as gmail.com or yahoo.com.</span></span> <span data-ttu-id="27db4-125">In altre parole, è possibile revocare un messaggio di posta elettronica inviato a un singolo destinatario che ha ricevuto l'esperienza basata su collegamento.</span><span class="sxs-lookup"><span data-stu-id="27db4-125">In other words, you can revoke an email sent to a single recipient that received the link-based experience.</span></span>

<span data-ttu-id="27db4-126">Non è possibile revocare un messaggio inviato a un destinatario che utilizza un account aziendale o dell'istituto di istruzione da Office 365 o Microsoft 365 o un utente che utilizza un account Microsoft, ad esempio un account outlook.com.</span><span class="sxs-lookup"><span data-stu-id="27db4-126">You cannot revoke a mail that you sent to a recipient that uses a work or school account from Office 365 or Microsoft 365 or a user that uses a Microsoft account, for example, an outlook.com account.</span></span> 

<span data-ttu-id="27db4-127">Per revocare un messaggio crittografato inviato, eseguire la procedura seguente</span><span class="sxs-lookup"><span data-stu-id="27db4-127">To revoke an encrypted message that you sent, complete these steps</span></span>

1. <span data-ttu-id="27db4-128">Nella cartella Posta inviata  di Outlook sul Web passare al messaggio che si desidera revocare.</span><span class="sxs-lookup"><span data-stu-id="27db4-128">In Outlook on the web, in your **Sent** folder, browse to the message you want to revoke.</span></span>

   <span data-ttu-id="27db4-129">Se la posta è revocabile, nella parte superiore del messaggio verrà visualizzato il collegamento "Rimuovi accesso esterno".</span><span class="sxs-lookup"><span data-stu-id="27db4-129">If the mail is revocable, you'll see the "Remove external access" link at the top of the message.</span></span>

    :::image type="content" source="../media/infoprotect-email-encryption/adhocencryptionrevokesentmsg.png" alt-text="Screenshot che mostra la posta crittografata che si desidera revocare in Outlook sul Web.":::

2. <span data-ttu-id="27db4-131">Fare **clic su Rimuovi accesso esterno** per revocare il messaggio.</span><span class="sxs-lookup"><span data-stu-id="27db4-131">Click **Remove external access** to revoke the message.</span></span>

   <span data-ttu-id="27db4-132">Il messaggio indica che il relativo stato è stato revocato.</span><span class="sxs-lookup"><span data-stu-id="27db4-132">The message shows that its status is revoked.</span></span>

   :::image type="content" source="../media/adhocencryptionrevokedmsg.png" alt-text="Screenshot che mostra il messaggio crittografato revocato in Outlook sul Web.":::

## <a name="how-to-revoke-an-encrypted-message-as-an-administrator"></a><span data-ttu-id="27db4-134">Come revocare un messaggio crittografato come amministratore</span><span class="sxs-lookup"><span data-stu-id="27db4-134">How to revoke an encrypted message as an administrator</span></span>

<span data-ttu-id="27db4-135">Gli amministratori di Microsoft 365 seguono questi passaggi generali per revocare un messaggio di posta elettronica crittografato idoneo:</span><span class="sxs-lookup"><span data-stu-id="27db4-135">Microsoft 365 administrators follow these general steps to revoke an eligible encrypted email:</span></span>

- <span data-ttu-id="27db4-136">Ottenere l'ID del messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="27db4-136">Get the Message ID of the email.</span></span>
- <span data-ttu-id="27db4-137">Verificare che sia possibile revocare il messaggio.</span><span class="sxs-lookup"><span data-stu-id="27db4-137">Verify that you can revoke the message.</span></span>
- <span data-ttu-id="27db4-138">Revocare la posta.</span><span class="sxs-lookup"><span data-stu-id="27db4-138">Revoke the mail.</span></span>

### <a name="step-1-obtain-the-message-id-of-the-email"></a><span data-ttu-id="27db4-139">Passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="27db4-139">Step 1.</span></span> <span data-ttu-id="27db4-140">Ottenere l'ID messaggio del messaggio di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="27db4-140">Obtain the Message ID of the email</span></span>

<span data-ttu-id="27db4-141">Prima di poter revocare un messaggio crittografato, raccogliere l'ID del messaggio.</span><span class="sxs-lookup"><span data-stu-id="27db4-141">Before you can revoke an encrypted mail, gather the Message ID of the mail.</span></span> <span data-ttu-id="27db4-142">MessageId è in genere nel formato seguente:</span><span class="sxs-lookup"><span data-stu-id="27db4-142">The MessageId is usually of the format:</span></span>

`<xxxxxxxxxxxxxxxxxxxxxxx@xxxxxx.xxxx.prod.outlook.com>`  

<span data-ttu-id="27db4-143">Esistono diversi modi per trovare l'ID messaggio del messaggio di posta elettronica che si desidera revocare.</span><span class="sxs-lookup"><span data-stu-id="27db4-143">There are multiple ways to find the Message ID of the email that you want to revoke.</span></span> <span data-ttu-id="27db4-144">In questa sezione vengono descritte due opzioni, ma è possibile utilizzare qualsiasi metodo che fornisce l'ID.</span><span class="sxs-lookup"><span data-stu-id="27db4-144">This section describes a couple of options, but you can use any method that provides the ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-message-trace-in-the-security-amp-compliance-center"></a><span data-ttu-id="27db4-145">Per identificare l'ID del messaggio di posta elettronica che si desidera revocare utilizzando Traccia messaggi nel Centro &amp; sicurezza e conformità</span><span class="sxs-lookup"><span data-stu-id="27db4-145">To identify the Message ID of the email you want to revoke by using Message Trace in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="27db4-146">Cercare il messaggio di posta elettronica in base al mittente o al destinatario usando Nuova traccia dei messaggi [nel Centro sicurezza & conformità](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/).</span><span class="sxs-lookup"><span data-stu-id="27db4-146">Search for the email by sender or recipient using [New Message Trace in Security & Compliance Center](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/).</span></span>

2. <span data-ttu-id="27db4-147">Dopo aver individuato il messaggio di posta elettronica, selezionarlo per visualizzare il riquadro **dei dettagli di Traccia** messaggio.</span><span class="sxs-lookup"><span data-stu-id="27db4-147">Once you've located the email, select it to bring up the **Message trace details** pane.</span></span> <span data-ttu-id="27db4-148">Espandere **Altre informazioni per** individuare l'ID messaggio.</span><span class="sxs-lookup"><span data-stu-id="27db4-148">Expand **More Information** to locate the Message ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-office-message-encryption-reports-in-the-security-amp-compliance-center"></a><span data-ttu-id="27db4-149">Per identificare l'ID del messaggio di posta elettronica che si desidera revocare utilizzando i report di Crittografia messaggi di Office nel Centro &amp; sicurezza e conformità</span><span class="sxs-lookup"><span data-stu-id="27db4-149">To identify the Message ID of the email you want to revoke by using Office Message Encryption reports in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="27db4-150">Nel Centro &amp; sicurezza e conformità passare al report Crittografia **messaggi**.</span><span class="sxs-lookup"><span data-stu-id="27db4-150">In the Security &amp; Compliance Center, navigate to the **Message encryption report**.</span></span> <span data-ttu-id="27db4-151">Per informazioni su questo report, vedere [View email security reports in the Security Compliance &amp; Center.](../security/defender-365-security/view-email-security-reports.md)</span><span class="sxs-lookup"><span data-stu-id="27db4-151">For information on this report, see [View email security reports in the Security &amp; Compliance Center](../security/defender-365-security/view-email-security-reports.md).</span></span>

2. <span data-ttu-id="27db4-152">Scegliere la **tabella Visualizza** dettagli e identificare il messaggio che si desidera revocare.</span><span class="sxs-lookup"><span data-stu-id="27db4-152">Choose the **View details** table and identify the message that you want to revoke.</span></span>

3. <span data-ttu-id="27db4-153">Fare doppio clic sul messaggio per visualizzare i dettagli che includono l'ID messaggio.</span><span class="sxs-lookup"><span data-stu-id="27db4-153">Double-click the message to view details that include the Message ID.</span></span>

### <a name="step-2-verify-that-the-mail-is-revocable"></a><span data-ttu-id="27db4-154">Passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="27db4-154">Step 2.</span></span> <span data-ttu-id="27db4-155">Verificare che la posta sia revocabile</span><span class="sxs-lookup"><span data-stu-id="27db4-155">Verify that the mail is revocable</span></span>

<span data-ttu-id="27db4-156">Per verificare se è possibile revocare un messaggio, verificare se il campo  Stato revoca è visibile nel report Crittografia nella tabella Dettagli del Centro &amp; sicurezza e conformità.</span><span class="sxs-lookup"><span data-stu-id="27db4-156">To verify whether you can revoke a message, check whether the Revocation Status field is visible in the Encryption report, in the **Details** table in the Security &amp; Compliance Center.</span></span>

<span data-ttu-id="27db4-157">Per verificare se è possibile revocare un determinato messaggio di posta elettronica utilizzando Windows PowerShell, completare questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="27db4-157">To verify whether you can revoke a particular email message by using Windows PowerShell, complete these steps.</span></span>

1. <span data-ttu-id="27db4-158">Utilizzando un account aziendale o dell'istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione, avviare una sessione Windows PowerShell e connettersi a Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="27db4-158">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="27db4-159">Per istruzioni, vedere [Connettersi a PowerShell di Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="27db4-159">For instructions, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="27db4-160">Eseguire il cmdlet Get-OMEMessageStatus seguente:</span><span class="sxs-lookup"><span data-stu-id="27db4-160">Run the Get-OMEMessageStatus cmdlet as follows:</span></span>

     ```powershell
     Get-OMEMessageStatus -MessageId "<message id>" | ft -a  Subject, IsRevocable
     ```

   <span data-ttu-id="27db4-161">Questo comando restituisce l'oggetto del messaggio e indica se il messaggio è revocabile.</span><span class="sxs-lookup"><span data-stu-id="27db4-161">This command returns the subject of the message and whether the message is revocable.</span></span> <span data-ttu-id="27db4-162">Ad esempio,</span><span class="sxs-lookup"><span data-stu-id="27db4-162">For example,</span></span>

     ```console
     Subject        IsRevocable
     -------        -----------
     "Test message" True
     ```

### <a name="step-3-revoke-the-mail"></a><span data-ttu-id="27db4-163">Passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="27db4-163">Step 3.</span></span> <span data-ttu-id="27db4-164">Revocare la posta</span><span class="sxs-lookup"><span data-stu-id="27db4-164">Revoke the mail</span></span>

<span data-ttu-id="27db4-165">Una volta che si conosce l'ID messaggio del messaggio di posta elettronica che si desidera revocare e si è verificato che il messaggio è revocabile, è possibile revocare il messaggio utilizzando il Centro sicurezza e conformità o &amp; Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="27db4-165">Once you know the Message ID of the email you want to revoke, and you have verified that the message is revocable, you can revoke the email using the Security &amp; Compliance Center or Windows PowerShell.</span></span>

<span data-ttu-id="27db4-166">Per revocare il messaggio tramite il Centro &amp; sicurezza e conformità</span><span class="sxs-lookup"><span data-stu-id="27db4-166">To revoke the message using the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="27db4-167">Utilizzando un account aziendale o dell'istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione, connettersi al Centro sicurezza & conformità.</span><span class="sxs-lookup"><span data-stu-id="27db4-167">Using a work or school account that has global administrator permissions in your organization, connect to the Security & Compliance Center.</span></span>

2. <span data-ttu-id="27db4-168">Nel report **Crittografia,** nella **tabella Dettagli** per il messaggio, scegliere **Revoca messaggio**.</span><span class="sxs-lookup"><span data-stu-id="27db4-168">In the **Encryption report**, in the **Details** table for the message, choose **Revoke message**.</span></span>

<span data-ttu-id="27db4-169">Per revocare un messaggio di posta elettronica Windows PowerShell, utilizzare il cmdlet Set-OMEMessageRevocation.</span><span class="sxs-lookup"><span data-stu-id="27db4-169">To revoke an email by using Windows PowerShell, use the Set-OMEMessageRevocation cmdlet.</span></span>

1. <span data-ttu-id="27db4-170">Utilizzando un account aziendale o dell'istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione, connettersi a [PowerShell di Exchange Online.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="27db4-170">Using a work or school account that has global administrator permissions in your organization, [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="27db4-171">Eseguire il cmdlet Set-OMEMessageRevocation seguente:</span><span class="sxs-lookup"><span data-stu-id="27db4-171">Run the Set-OMEMessageRevocation cmdlet as follows:</span></span>

    ```powershell
    Set-OMEMessageRevocation -Revoke $true -MessageId "<messageId>"
    ```

3. <span data-ttu-id="27db4-172">Per verificare se il messaggio di posta elettronica è stato revocato, eseguire il cmdlet Get-OMEMessageStatus seguente:</span><span class="sxs-lookup"><span data-stu-id="27db4-172">To check whether the email was revoked, run the Get-OMEMessageStatus cmdlet as follows:</span></span>

    ```powershell
    Get-OMEMessageStatus -MessageId "<messageId>" | ft -a  Subject, Revoked
    ```

    <span data-ttu-id="27db4-173">Se la revoca ha avuto esito positivo, il cmdlet restituisce il risultato seguente:</span><span class="sxs-lookup"><span data-stu-id="27db4-173">If revocation was successful, the cmdlet returns the following result:</span></span>  

     ```console
     Revoked: True
     ```

## <a name="more-information-about-office-365-advanced-message-encryption"></a><span data-ttu-id="27db4-174">Ulteriori informazioni sulla crittografia avanzata dei messaggi di Office 365</span><span class="sxs-lookup"><span data-stu-id="27db4-174">More information about Office 365 Advanced Message Encryption</span></span>

- [<span data-ttu-id="27db4-175">Office 365 Advanced Message Encryption</span><span class="sxs-lookup"><span data-stu-id="27db4-175">Office 365 Advanced Message Encryption</span></span>](ome-advanced-message-encryption.md)

- [<span data-ttu-id="27db4-176">Crittografia avanzata dei messaggi di Office 365 - Scadenza della posta elettronica</span><span class="sxs-lookup"><span data-stu-id="27db4-176">Office 365 Advanced Message Encryption - email expiration</span></span>](ome-advanced-expiration.md)

- [<span data-ttu-id="27db4-177">Criteri dei messaggi e descrizione del servizio di conformità</span><span class="sxs-lookup"><span data-stu-id="27db4-177">Message policy and compliance service description</span></span>](/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)