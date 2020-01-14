---
title: Revocare un messaggio di posta elettronica crittografato da Office 365 Advanced Message Encryption
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 10/8/2019
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: In qualità di amministratore di Office 365, è possibile revocare alcuni messaggi di posta elettronica crittografati con la crittografia avanzata dei messaggi di Office 365.
ms.openlocfilehash: d3d449c969b2fa5d21042779ebad11e3807d1d3e
ms.sourcegitcommit: 39bd4be7e8846770f060b5dd7d895fc8040b18f5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/14/2020
ms.locfileid: "41112520"
---
# <a name="revoke-email-encrypted-by-office-365-advanced-message-encryption"></a><span data-ttu-id="38820-103">Revocare un messaggio di posta elettronica crittografato da Office 365 Advanced Message Encryption</span><span class="sxs-lookup"><span data-stu-id="38820-103">Revoke email encrypted by Office 365 Advanced Message Encryption</span></span>

<span data-ttu-id="38820-104">La revoca del messaggio di posta elettronica viene offerta come parte della crittografia avanzata dei messaggi di Office 365.</span><span class="sxs-lookup"><span data-stu-id="38820-104">Email revocation is offered as part of Office 365 Advanced Message Encryption.</span></span> <span data-ttu-id="38820-105">La crittografia avanzata dei messaggi di Office 365 è inclusa in [microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (nonprofit staff pricing), Office 365 Enterprise E5 (nonprofit staff pricing) e Office 365 Education a5.</span><span class="sxs-lookup"><span data-stu-id="38820-105">Office 365 Advanced Message Encryption is included in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (Nonprofit Staff Pricing), Office 365 Enterprise E5 (Nonprofit Staff Pricing), and Office 365 Education A5.</span></span> <span data-ttu-id="38820-106">Se l'organizzazione dispone di un abbonamento che non include la crittografia dei messaggi avanzata di Office 365, è possibile acquistarla con il componente aggiuntivo Microsoft 365 E5 Compliance SKU per Microsoft 365 E3, Microsoft 365 E3 (nonprofit staff pricing) o Office 365 Advanced Componente aggiuntivo SKU di conformità per Microsoft 365 E3, Microsoft 365 E3 (nonprofit staff pricing) o SKU di Office 365.</span><span class="sxs-lookup"><span data-stu-id="38820-106">If your organization has a subscription that does not include Office 365 Advanced Message Encryption, you can purchase it with the Microsoft 365 E5 Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or the Office 365 Advanced Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or Office 365 SKUs.</span></span>

<span data-ttu-id="38820-107">Questo articolo fa parte di una serie più ampia di articoli sulla [crittografia dei messaggi di Office 365](ome.md).</span><span class="sxs-lookup"><span data-stu-id="38820-107">This article is part of a larger series of articles about [Office 365 Message Encryption](ome.md).</span></span>

<span data-ttu-id="38820-108">Se un messaggio è stato crittografato utilizzando la crittografia avanzata dei messaggi di Office 365 e si è un amministratore di Office 365, è possibile revocare il messaggio in determinate condizioni.</span><span class="sxs-lookup"><span data-stu-id="38820-108">If a message was encrypted using Office 365 Advanced Message Encryption, and you are an Office 365 admin, you can do revoke the message under certain conditions.</span></span> <span data-ttu-id="38820-109">In questo articolo vengono descritte le circostanze in cui la revoca è possibile e come procedere.</span><span class="sxs-lookup"><span data-stu-id="38820-109">This article describes the circumstances under which revocation is possible and how to do it.</span></span>
  
## <a name="encrypted-emails-that-you-can-revoke"></a><span data-ttu-id="38820-110">Messaggi di posta elettronica crittografati che è possibile revocare</span><span class="sxs-lookup"><span data-stu-id="38820-110">Encrypted emails that you can revoke</span></span>

<span data-ttu-id="38820-111">È possibile revocare i messaggi di posta elettronica crittografati se il destinatario ha ricevuto una e-mail crittografata basata sul collegamento.</span><span class="sxs-lookup"><span data-stu-id="38820-111">You can revoke encrypted emails if the recipient received a link-based, branded encrypted email.</span></span> <span data-ttu-id="38820-112">Se il destinatario ha ricevuto un'esperienza nativa in linea in un client di Outlook supportato, tali messaggi di posta elettronica non possono essere revocati.</span><span class="sxs-lookup"><span data-stu-id="38820-112">If the recipient received a native inline experience in a supported Outlook client, then those emails cannot be revoked.</span></span>

<span data-ttu-id="38820-113">Se un destinatario riceve un'esperienza basata sul collegamento o un'esperienza in linea dipende dal tipo di identità del destinatario: Office 365 e destinatari dell'account Microsoft (ad esempio, gli utenti di outlook.com) ricevono un'esperienza in linea nei client Outlook supportati.</span><span class="sxs-lookup"><span data-stu-id="38820-113">Whether a recipient receives a link-based experience or an inline experience depends on the recipient identity type: Office 365 and Microsoft Account recipients (for example, outlook.com users) get an inline experience in supported Outlook clients.</span></span> <span data-ttu-id="38820-114">Tutti gli altri tipi di destinatari, ad esempio i destinatari Gmail, ricevono un'esperienza basata sul collegamento.</span><span class="sxs-lookup"><span data-stu-id="38820-114">All other recipient types, such as Gmail recipients, get a link-based experience.</span></span>

## <a name="recipient-experience-for-revoked-encrypted-emails"></a><span data-ttu-id="38820-115">Esperienza dei destinatari per i messaggi di posta elettronica crittografati</span><span class="sxs-lookup"><span data-stu-id="38820-115">Recipient experience for revoked encrypted emails</span></span>

<span data-ttu-id="38820-116">Dopo che un messaggio di posta elettronica è stato revocato, il destinatario riceve un errore quando accede alla posta elettronica crittografata tramite il portale di crittografia dei messaggi di Office 365: "il messaggio è stato revocato dal mittente".</span><span class="sxs-lookup"><span data-stu-id="38820-116">Once an email has been revoked, the recipient receives an error when they access the encrypted email through the Office 365 Message Encryption portal: “The message has been revoked by the sender”.</span></span>

![Schermata che visualizza un messaggio di posta elettronica crittografato revocato.](media/revoked-encrypted-email.png)

## <a name="how-to-revoke-an-encrypted-email"></a><span data-ttu-id="38820-118">Come revocare un messaggio di posta elettronica crittografato</span><span class="sxs-lookup"><span data-stu-id="38820-118">How to revoke an encrypted email</span></span>

### <a name="step-1-obtain-the-message-id-of-the-email"></a><span data-ttu-id="38820-119">Passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="38820-119">Step 1.</span></span> <span data-ttu-id="38820-120">Ottenere l'ID del messaggio di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="38820-120">Obtain the Message ID of the email</span></span>

<span data-ttu-id="38820-121">Prima di poter revocare un messaggio crittografato, è necessario raccogliere l'ID della posta.</span><span class="sxs-lookup"><span data-stu-id="38820-121">Before you can revoke an encrypted mail you gather the Message ID of the mail.</span></span> <span data-ttu-id="38820-122">Il MessageId è in genere del formato seguente:</span><span class="sxs-lookup"><span data-stu-id="38820-122">The MessageId is usually of the format:</span></span>

`<xxxxxxxxxxxxxxxxxxxxxxx@xxxxxx.xxxx.prod.outlook.com>`  

<span data-ttu-id="38820-123">Sono disponibili diversi modi per individuare l'ID del messaggio di posta elettronica che si desidera revocare.</span><span class="sxs-lookup"><span data-stu-id="38820-123">There are multiple ways to find the Message ID of the email that you want to revoke.</span></span> <span data-ttu-id="38820-124">In questa sezione vengono descritte alcune opzioni, ma è possibile utilizzare qualsiasi metodo che fornisca l'ID.</span><span class="sxs-lookup"><span data-stu-id="38820-124">This section describes a couple of options, but you can use any method that provides the ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-message-trace-in-the-security-amp-compliance-center"></a><span data-ttu-id="38820-125">Per identificare l'ID del messaggio di posta elettronica che si desidera revocare tramite la traccia dei messaggi nel &amp; Centro sicurezza e conformità</span><span class="sxs-lookup"><span data-stu-id="38820-125">To identify the Message ID of the email you want to revoke by using Message Trace in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="38820-126">Cercare il messaggio di posta elettronica in base al mittente o al destinatario utilizzando la [nuova traccia dei messaggi in Office 365 Security & Compliance Center](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/).</span><span class="sxs-lookup"><span data-stu-id="38820-126">Search for the email by sender or recipient using [New Message Trace in Office 365 Security & Compliance Center](https://blogs.technet.microsoft.com/exchange/2018/05/02/new-message-trace-in-office-365-security-compliance-center/).</span></span>

2. <span data-ttu-id="38820-127">Dopo aver individuato il messaggio di posta elettronica, selezionarlo per visualizzare il riquadro **Dettagli traccia dei messaggi** .</span><span class="sxs-lookup"><span data-stu-id="38820-127">Once you've located the email, select it to bring up the **Message trace details** pane.</span></span> <span data-ttu-id="38820-128">Espandere **ulteriori informazioni** per individuare l'ID del messaggio.</span><span class="sxs-lookup"><span data-stu-id="38820-128">Expand **More Information** to locate the Message ID.</span></span>

#### <a name="to-identify-the-message-id-of-the-email-you-want-to-revoke-by-using-office-message-encryption-reports-in-the-security-amp-compliance-center"></a><span data-ttu-id="38820-129">Per identificare l'ID del messaggio di posta elettronica che si desidera revocare utilizzando i rapporti di crittografia dei messaggi di &amp; Office nel centro sicurezza e conformità</span><span class="sxs-lookup"><span data-stu-id="38820-129">To identify the Message ID of the email you want to revoke by using Office Message Encryption reports in the Security &amp; Compliance Center</span></span>

1. <span data-ttu-id="38820-130">Nel centro sicurezza &amp; e conformità, passare al **rapporto di crittografia dei messaggi**.</span><span class="sxs-lookup"><span data-stu-id="38820-130">In the Security &amp; Compliance Center, navigate to the **Message encryption report**.</span></span> <span data-ttu-id="38820-131">Per informazioni su questo report, vedere [visualizzare i report di sicurezza della posta &amp; elettronica nel centro sicurezza e conformità](../security/office-365-security/view-email-security-reports.md).</span><span class="sxs-lookup"><span data-stu-id="38820-131">For information on this report, see [View email security reports in the Security &amp; Compliance Center](../security/office-365-security/view-email-security-reports.md).</span></span>

2. <span data-ttu-id="38820-132">Scegliere la tabella **Visualizza dettagli** e identificare il messaggio che si desidera revocare.</span><span class="sxs-lookup"><span data-stu-id="38820-132">Choose the **View details** table and identify the message that you want to revoke.</span></span>

3. <span data-ttu-id="38820-133">Fare doppio clic sul messaggio per visualizzare i dettagli che includono l'ID del messaggio.</span><span class="sxs-lookup"><span data-stu-id="38820-133">Double-click the message to view details that include the Message ID.</span></span>

### <a name="step-2-verify-that-the-mail-is-revocable"></a><span data-ttu-id="38820-134">Passaggio 2.</span><span class="sxs-lookup"><span data-stu-id="38820-134">Step 2.</span></span> <span data-ttu-id="38820-135">Verificare che la posta sia revocabile</span><span class="sxs-lookup"><span data-stu-id="38820-135">Verify that the mail is revocable</span></span>

<span data-ttu-id="38820-136">Per verificare se è possibile revocare un messaggio, controllare se il campo stato revoca è visibile nel rapporto di crittografia, nella tabella **Details** del Centro sicurezza &amp; e conformità.</span><span class="sxs-lookup"><span data-stu-id="38820-136">To verify whether you can revoke a message, check whether the Revocation Status field is visible in the Encryption report, in the **Details** table in the Security &amp; Compliance Center.</span></span>

<span data-ttu-id="38820-137">Per verificare se è possibile revocare un messaggio di posta elettronica specifico utilizzando Windows PowerShell, eseguire la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="38820-137">To verify whether you can revoke a particular email message by using Windows Powershell, complete these steps.</span></span>

1. <span data-ttu-id="38820-138">Utilizzo di un account aziendale o dell'Istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione di Office 365, avviare una sessione di Windows PowerShell e connettersi a Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="38820-138">Using a work or school account that has global administrator permissions in your Office 365 organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="38820-139">Per istruzioni, vedere [Connettersi a PowerShell di Exchange Online](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="38820-139">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="38820-140">Eseguire il cmdlet Get-OMEMessageStatus nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="38820-140">Run the Get-OMEMessageStatus cmdlet as follows:</span></span>

     ```powershell
     Get-OMEMessageStatus -MessageId "<message id>" | ft -a  Subject, IsRevocable
     ```

   <span data-ttu-id="38820-141">Restituisce l'oggetto del messaggio e indica se il messaggio è revocabile.</span><span class="sxs-lookup"><span data-stu-id="38820-141">This returns the subject of the message and whether the message is revocable.</span></span> <span data-ttu-id="38820-142">For example,</span><span class="sxs-lookup"><span data-stu-id="38820-142">For example,</span></span>

     ```text
     Subject IsRevocable
     ------- -----------
     “Test message”  True
     ```

### <a name="step-3-revoke-the-mail"></a><span data-ttu-id="38820-143">Passaggio 3:</span><span class="sxs-lookup"><span data-stu-id="38820-143">Step 3.</span></span> <span data-ttu-id="38820-144">Revocare la posta elettronica</span><span class="sxs-lookup"><span data-stu-id="38820-144">Revoke the mail</span></span>

<span data-ttu-id="38820-145">Una volta che si conosce l'ID del messaggio di posta elettronica che si desidera revocare ed è stato verificato che il messaggio è revocabile, è possibile revocare la posta &amp; elettronica utilizzando il Centro sicurezza e conformità di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="38820-145">Once you know the Message ID of the email you want to revoke, and you have verified that the message is revocable, you can revoke the email using the Security &amp; Compliance Center or Windows Powershell.</span></span>

<span data-ttu-id="38820-146">Per revocare il messaggio utilizzando il centro &amp; sicurezza e conformità</span><span class="sxs-lookup"><span data-stu-id="38820-146">To revoke the message using the Security &amp; Compliance Center</span></span>

<span data-ttu-id="38820-147">Per revocare la posta elettronica nel centro &amp; sicurezza e conformità, nel rapporto di crittografia, nella tabella **Details** del messaggio, scegliere **revoca messaggio**.</span><span class="sxs-lookup"><span data-stu-id="38820-147">To revoke the email in the Security &amp; Compliance Center, in the Encryption report, in the **Details** table for the message, choose **Revoke message**.</span></span>

<span data-ttu-id="38820-148">È possibile revocare un messaggio di posta elettronica utilizzando Windows PowerShell utilizzando il cmdlet Set-OMEMessageRevocation.</span><span class="sxs-lookup"><span data-stu-id="38820-148">You can revoke an email by using Windows Powershell by using the Set-OMEMessageRevocation cmdlet.</span></span>

1. <span data-ttu-id="38820-149">[Connettersi a Exchange Online PowerShell](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="38820-149">[Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="38820-150">Eseguire il cmdlet Set-OMEMessageRevocation come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="38820-150">Run the Set-OMEMessageRevocation cmdlet as follows:</span></span>

    ```powershell
    Set-OMEMessageRevocation -Revoke $true -MessageId "<messageId>"
    ```

3. <span data-ttu-id="38820-151">Per verificare se il messaggio di posta elettronica è stato revocato, eseguire il cmdlet Get-OMEMessageStatus come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="38820-151">To check whether the email was revoked, run the Get-OMEMessageStatus cmdlet as follows:</span></span>

    ```powershell
    Get-OMEMessageStatus -MessageId "<messageId>" | ft -a  Subject, Revoked
    ```

    <span data-ttu-id="38820-152">Se la revoca ha avuto esito positivo, il cmdlet restituisce il risultato seguente:</span><span class="sxs-lookup"><span data-stu-id="38820-152">If revocation was successful, the cmdlet returns the following result:</span></span>  

     ```text
     Revoked: True
     ```

## <a name="more-information-about-office-365-advanced-message-encryption"></a><span data-ttu-id="38820-153">Ulteriori informazioni sulla crittografia avanzata dei messaggi di Office 365</span><span class="sxs-lookup"><span data-stu-id="38820-153">More information about Office 365 Advanced Message Encryption</span></span>

- [<span data-ttu-id="38820-154">Office 365 Advanced Message Encryption</span><span class="sxs-lookup"><span data-stu-id="38820-154">Office 365 Advanced Message Encryption</span></span>](ome-advanced-message-encryption.md)

- [<span data-ttu-id="38820-155">Crittografia messaggi avanzata di Office 365-scadenza del messaggio di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="38820-155">Office 365 Advanced Message Encryption - email expiration</span></span>](ome-advanced-expiration.md)

- [<span data-ttu-id="38820-156">Descrizione del servizio criteri di conformità e del messaggio</span><span class="sxs-lookup"><span data-stu-id="38820-156">Message policy and compliance service description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)
