---
title: Aggiungere il marchio dell'organizzazione ai messaggi crittografati
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 4/1/2020
search.appverid:
- MET150
- MOE150
ms.assetid: 7a29260d-2959-42aa-8916-feceff6ee51d
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
description: Informazioni su come gli amministratori globali di Office 365 possono applicare la personalizzazione dell'organizzazione ai messaggi di posta elettronica & contenuti del portale di crittografia.
ms.openlocfilehash: 56b948fc941da4fb221d929ecd59c5300b135e39
ms.sourcegitcommit: c0495e224f12c448bfc162ef2e4b33b82f064ac8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/17/2020
ms.locfileid: "49709498"
---
# <a name="add-your-organizations-brand-to-your-microsoft-365-for-business-message-encryption-encrypted-messages"></a><span data-ttu-id="70f6e-103">Aggiungere il marchio dell'organizzazione ai messaggi crittografati di Crittografia messaggi di Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="70f6e-103">Add your organization's brand to your Microsoft 365 for business Message Encryption encrypted messages</span></span>

<span data-ttu-id="70f6e-104">È possibile applicare la personalizzazione della società per personalizzare l'aspetto dei messaggi di posta elettronica dell'organizzazione e del portale di crittografia.</span><span class="sxs-lookup"><span data-stu-id="70f6e-104">You can apply your company branding to customize the look of your organization's email messages and the encryption portal.</span></span> <span data-ttu-id="70f6e-105">È necessario applicare le autorizzazioni di amministratore globale all'account aziendale o dell'istituto di istruzione prima di iniziare.</span><span class="sxs-lookup"><span data-stu-id="70f6e-105">You'll need to apply global administrator permissions to your work or school account before you can get started.</span></span> <span data-ttu-id="70f6e-106">Dopo aver creato queste autorizzazioni, utilizzare i cmdlet Get-OMEConfiguration e Set-OMEConfiguration Windows PowerShell per personalizzare queste parti dei messaggi di posta elettronica crittografati:</span><span class="sxs-lookup"><span data-stu-id="70f6e-106">Once you have these permissions, use the Get-OMEConfiguration and Set-OMEConfiguration Windows PowerShell cmdlets to customize these parts of encrypted email messages:</span></span>
  
- <span data-ttu-id="70f6e-107">Testo introduttivo</span><span class="sxs-lookup"><span data-stu-id="70f6e-107">Introductory text</span></span>

- <span data-ttu-id="70f6e-108">Disclaimer text</span><span class="sxs-lookup"><span data-stu-id="70f6e-108">Disclaimer text</span></span>

- <span data-ttu-id="70f6e-109">URL dell'informativa sulla privacy dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="70f6e-109">URL for Your organization's privacy statement</span></span>

- <span data-ttu-id="70f6e-110">Testo nel portale OME</span><span class="sxs-lookup"><span data-stu-id="70f6e-110">Text in the OME portal</span></span>

- <span data-ttu-id="70f6e-111">Logo visualizzato nel messaggio di posta elettronica e nel portale OME o se usare o meno un logo</span><span class="sxs-lookup"><span data-stu-id="70f6e-111">Logo that appears in the email message and OME portal, or whether to use a logo at all</span></span>

- <span data-ttu-id="70f6e-112">Colore di sfondo nel messaggio di posta elettronica e nel portale OME</span><span class="sxs-lookup"><span data-stu-id="70f6e-112">Background color in the email message and OME portal</span></span>

<span data-ttu-id="70f6e-113">È anche possibile ripristinare l'aspetto predefinito in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="70f6e-113">You can also revert back to the default look and feel at any time.</span></span>

<span data-ttu-id="70f6e-114">Se si desidera un maggiore controllo, usare Office 365 Advanced Message Encryption per creare più modelli per i messaggi di posta elettronica crittografati provenienti dall'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="70f6e-114">If you'd like more control, use Office 365 Advanced Message Encryption to create multiple templates for encrypted emails originating from your organization.</span></span> <span data-ttu-id="70f6e-115">Utilizzare questi modelli per controllare le parti dell'esperienza dell'utente finale.</span><span class="sxs-lookup"><span data-stu-id="70f6e-115">Use these templates to control parts of the end-user experience.</span></span> <span data-ttu-id="70f6e-116">Ad esempio, specificare se i destinatari possono utilizzare Google, Yahoo e Account Microsoft per accedere al portale di crittografia.</span><span class="sxs-lookup"><span data-stu-id="70f6e-116">For example, specify whether recipients can use Google, Yahoo, and Microsoft Accounts to sign in to the encryption portal.</span></span> <span data-ttu-id="70f6e-117">Usa i modelli per soddisfare diversi casi d'uso, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="70f6e-117">Use templates to fulfill several use cases, such as:</span></span>

- <span data-ttu-id="70f6e-118">Singoli reparti, ad esempio Finanza, Vendite e così via.</span><span class="sxs-lookup"><span data-stu-id="70f6e-118">Individual departments, such as Finance, Sales, and so on.</span></span>

- <span data-ttu-id="70f6e-119">Prodotti diversi</span><span class="sxs-lookup"><span data-stu-id="70f6e-119">Different products</span></span>

- <span data-ttu-id="70f6e-120">Aree geografiche o paesi diversi</span><span class="sxs-lookup"><span data-stu-id="70f6e-120">Different geographical regions or countries</span></span>

- <span data-ttu-id="70f6e-121">Se si desidera consentire la revoca dei messaggi di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="70f6e-121">Whether you want to allow emails to be revoked</span></span>

- <span data-ttu-id="70f6e-122">Se si desidera che i messaggi di posta elettronica inviati a destinatari esterni scadono dopo un numero di giorni specificato.</span><span class="sxs-lookup"><span data-stu-id="70f6e-122">Whether you want emails sent to external recipients to expire after a specified number of days.</span></span>

<span data-ttu-id="70f6e-123">Dopo aver creato i modelli, è possibile applicarli ai messaggi di posta elettronica crittografati utilizzando le regole del flusso di posta di Exchange.</span><span class="sxs-lookup"><span data-stu-id="70f6e-123">Once you've created the templates, you can apply them to encrypted emails by using Exchange mail flow rules.</span></span> <span data-ttu-id="70f6e-124">If you have Office 365 Advanced Message Encryption, you can revoke any email that you've branded by using these templates.</span><span class="sxs-lookup"><span data-stu-id="70f6e-124">If you have Office 365 Advanced Message Encryption, you can revoke any email that you've branded by using these templates.</span></span>

## <a name="work-with-ome-branding-templates"></a><span data-ttu-id="70f6e-125">Usare i modelli di personalizzazione di OME</span><span class="sxs-lookup"><span data-stu-id="70f6e-125">Work with OME branding templates</span></span>

<span data-ttu-id="70f6e-126">È possibile modificare diverse caratteristiche all'interno di un modello di personalizzazione.</span><span class="sxs-lookup"><span data-stu-id="70f6e-126">You can modify several features within a branding template.</span></span> <span data-ttu-id="70f6e-127">È possibile modificare, ma non rimuovere, il modello predefinito.</span><span class="sxs-lookup"><span data-stu-id="70f6e-127">You can modify, but not remove, the default template.</span></span> <span data-ttu-id="70f6e-128">Se si dispone di Advanced Message Encryption, è anche possibile creare, modificare e rimuovere modelli personalizzati.</span><span class="sxs-lookup"><span data-stu-id="70f6e-128">If you have Advanced Message Encryption, you can also create, modify, and remove custom templates.</span></span> <span data-ttu-id="70f6e-129">Usa Windows PowerShell per usare un modello di personalizzazione alla volta.</span><span class="sxs-lookup"><span data-stu-id="70f6e-129">Use Windows PowerShell to work with one branding template at a time.</span></span>

- <span data-ttu-id="70f6e-130">[Set-OMEConfiguration:](https://docs.microsoft.com/powershell/module/exchange/set-omeconfiguration) modificare il modello di personalizzazione predefinito o un modello di personalizzazione personalizzato creato.</span><span class="sxs-lookup"><span data-stu-id="70f6e-130">[Set-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-omeconfiguration) - Modify the default branding template or a custom branding template that you created.</span></span>
- <span data-ttu-id="70f6e-131">[New-OMEConfiguration:](https://docs.microsoft.com/powershell/module/exchange/new-omeconfiguration) crea un nuovo modello di personalizzazione, solo crittografia avanzata dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="70f6e-131">[New-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/new-omeconfiguration) - Create a new branding template, Advanced Message Encryption only.</span></span>
- <span data-ttu-id="70f6e-132">[Remove-OMEConfiguration:](https://docs.microsoft.com/powershell/module/exchange/remove-omeconfiguration) consente di rimuovere un modello di personalizzazione personalizzato, solo crittografia avanzata dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="70f6e-132">[Remove-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/remove-omeconfiguration) - Remove a custom branding template, Advanced Message Encryption only.</span></span> <span data-ttu-id="70f6e-133">Non è possibile eliminare il modello di personalizzazione predefinito.</span><span class="sxs-lookup"><span data-stu-id="70f6e-133">You can't delete the default branding template.</span></span>
  
## <a name="modify-an-ome-branding-template"></a><span data-ttu-id="70f6e-134">Modificare un modello di personalizzazione di OME</span><span class="sxs-lookup"><span data-stu-id="70f6e-134">Modify an OME branding template</span></span>

<span data-ttu-id="70f6e-135">Usa Windows PowerShell per modificare un modello di personalizzazione alla volta.</span><span class="sxs-lookup"><span data-stu-id="70f6e-135">Use Windows PowerShell to modify one branding template at a time.</span></span> <span data-ttu-id="70f6e-136">Se si dispone di Advanced Message Encryption, è anche possibile creare, modificare e rimuovere modelli personalizzati.</span><span class="sxs-lookup"><span data-stu-id="70f6e-136">If you have Advanced Message Encryption, you can also create, modify, and remove custom templates.</span></span>

1. <span data-ttu-id="70f6e-137">Utilizzando un account aziendale o dell'istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione, avviare una sessione Windows PowerShell e connettersi a Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="70f6e-137">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="70f6e-138">Per istruzioni, vedere [Connettersi a PowerShell di Exchange Online](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="70f6e-138">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="70f6e-139">Utilizzare il cmdlet Set-OMEConfiguration come descritto in [Set-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/Set-OMEConfiguration) oppure utilizzare la figura e la tabella seguenti per istruzioni.</span><span class="sxs-lookup"><span data-stu-id="70f6e-139">Use the Set-OMEConfiguration cmdlet as described in [Set-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/Set-OMEConfiguration) or use the following graphic and table for guidance.</span></span>

![Parti di posta elettronica personalizzabili](../media/ome-template-breakout.png)

|<span data-ttu-id="70f6e-141">**Per personalizzare questa funzionalità dell'esperienza di crittografia**</span><span class="sxs-lookup"><span data-stu-id="70f6e-141">**To customize this feature of the encryption experience**</span></span>|<span data-ttu-id="70f6e-142">**Usare questi comandi**</span><span class="sxs-lookup"><span data-stu-id="70f6e-142">**Use these commands**</span></span>|
|:-----|:-----|
|<span data-ttu-id="70f6e-143">Colore di sfondo</span><span class="sxs-lookup"><span data-stu-id="70f6e-143">Background color</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -BackgroundColor "<#RRGGBB hexadecimal color code or name value>"` <br/> <span data-ttu-id="70f6e-144">**Esempio:**</span><span class="sxs-lookup"><span data-stu-id="70f6e-144">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -BackgroundColor "#ffffff"` <br/> <span data-ttu-id="70f6e-145">Per altre informazioni sui colori di sfondo, vedi la sezione [Colori di](#background-color-reference) sfondo più avanti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="70f6e-145">For more information about background colors, see the [Background colors](#background-color-reference) section later in this article.</span></span>|
|<span data-ttu-id="70f6e-146">Logo</span><span class="sxs-lookup"><span data-stu-id="70f6e-146">Logo</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -Image <Byte[]>` <br/> <span data-ttu-id="70f6e-147">**Esempio:**</span><span class="sxs-lookup"><span data-stu-id="70f6e-147">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -Image (Get-Content "C:\Temp\contosologo.png" -Encoding byte)` <br/> <span data-ttu-id="70f6e-148">Formati di file supportati: png, jpg, bmp o tiff</span><span class="sxs-lookup"><span data-stu-id="70f6e-148">Supported file formats: .png, .jpg, .bmp, or .tiff</span></span>  <br/> <span data-ttu-id="70f6e-149">Dimensione ottimale relativa al file del logo: inferiore a 40 KB</span><span class="sxs-lookup"><span data-stu-id="70f6e-149">Optimal size of logo file: less than 40 KB</span></span>  <br/> <span data-ttu-id="70f6e-150">Dimensioni ottimali dell'immagine del logo: 170x70 pixel.</span><span class="sxs-lookup"><span data-stu-id="70f6e-150">Optimal size of logo image: 170x70 pixels.</span></span> <span data-ttu-id="70f6e-151">Se l'immagine supera queste dimensioni, il servizio ridimensiona il logo per la visualizzazione nel portale.</span><span class="sxs-lookup"><span data-stu-id="70f6e-151">If your image exceeds these dimensions, the service resizes your logo for display in the portal.</span></span> <span data-ttu-id="70f6e-152">Il servizio non modifica il file grafico stesso.</span><span class="sxs-lookup"><span data-stu-id="70f6e-152">The service doesn't modify the graphic file itself.</span></span> <span data-ttu-id="70f6e-153">Per ottenere risultati ottimali, utilizzare le dimensioni ottimali.</span><span class="sxs-lookup"><span data-stu-id="70f6e-153">For best results, use the optimal size.</span></span>|
|<span data-ttu-id="70f6e-154">Testo accanto al nome e all'indirizzo di posta elettronica del mittente</span><span class="sxs-lookup"><span data-stu-id="70f6e-154">Text next to the sender's name and email address</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -IntroductionText "<String up to 1024 characters>"` <br/> <span data-ttu-id="70f6e-155">**Esempio:**</span><span class="sxs-lookup"><span data-stu-id="70f6e-155">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -IntroductionText "has sent you a secure message."`|
|<span data-ttu-id="70f6e-156">Testo visualizzato sul pulsante "Leggi messaggio"</span><span class="sxs-lookup"><span data-stu-id="70f6e-156">Text that appears on the "Read Message" button</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -ReadButtonText "<String up to 1024 characters>"` <br/> <span data-ttu-id="70f6e-157">**Esempio:**</span><span class="sxs-lookup"><span data-stu-id="70f6e-157">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -ReadButtonText "Read Secure Message."`|
|<span data-ttu-id="70f6e-158">Testo visualizzato sotto il pulsante "Leggi messaggio"</span><span class="sxs-lookup"><span data-stu-id="70f6e-158">Text that appears below the "Read Message" button</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -EmailText "<String up to 1024 characters>"` <br/> <span data-ttu-id="70f6e-159">**Esempio:**</span><span class="sxs-lookup"><span data-stu-id="70f6e-159">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText "Encrypted message from ContosoPharma secure messaging system."`|
|<span data-ttu-id="70f6e-160">URL per il collegamento all'Informativa sulla privacy</span><span class="sxs-lookup"><span data-stu-id="70f6e-160">URL for the Privacy Statement link</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PrivacyStatementURL "<URL>"` <br/> <span data-ttu-id="70f6e-161">**Esempio:**</span><span class="sxs-lookup"><span data-stu-id="70f6e-161">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -PrivacyStatementURL "https://contoso.com/privacystatement.html"`|
|<span data-ttu-id="70f6e-162">dichiarazione di non responsabilità nella posta elettronica che contiene il messaggio crittografato</span><span class="sxs-lookup"><span data-stu-id="70f6e-162">Disclaimer statement in the email that contains the encrypted message</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -DisclaimerText "<Disclaimer statement. String of up to 1024 characters.>"` <br/> <span data-ttu-id="70f6e-163">**Esempio:**</span><span class="sxs-lookup"><span data-stu-id="70f6e-163">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -DisclaimerText "This message is confidential for the use of the addressee only."`|
|<span data-ttu-id="70f6e-164">testo visualizzato nella parte superiore del portale di visualizzazione del messaggio crittografato</span><span class="sxs-lookup"><span data-stu-id="70f6e-164">Text that appears at the top of the encrypted mail viewing portal</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PortalText "<Text for your portal. String of up to 128 characters.>"` <br/> <span data-ttu-id="70f6e-165">**Esempio:**</span><span class="sxs-lookup"><span data-stu-id="70f6e-165">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText "ContosoPharma secure email portal."`|
|<span data-ttu-id="70f6e-166">Per abilitare o disabilitare l'autenticazione con un pass code una sola volta per questo modello personalizzato</span><span class="sxs-lookup"><span data-stu-id="70f6e-166">To enable or disable authentication with a one-time pass code for this custom template</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -OTPEnabled <$true|$false>` <br/> <span data-ttu-id="70f6e-167">**Esempi:**</span><span class="sxs-lookup"><span data-stu-id="70f6e-167">**Examples:**</span></span> <br/><span data-ttu-id="70f6e-168">Per abilitare passcode una sola volta per questo modello personalizzato</span><span class="sxs-lookup"><span data-stu-id="70f6e-168">To enable one-time passcodes for this custom template</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $true` <br/> <span data-ttu-id="70f6e-169">Per disabilitare i passcode una sola volta per questo modello personalizzato</span><span class="sxs-lookup"><span data-stu-id="70f6e-169">To disable one-time passcodes for this custom template</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $false`|
|<span data-ttu-id="70f6e-170">Per abilitare o disabilitare l'autenticazione con le identità Microsoft, Google o Yahoo per questo modello personalizzato</span><span class="sxs-lookup"><span data-stu-id="70f6e-170">To enable or disable authentication with Microsoft, Google, or Yahoo identities for this custom template</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -SocialIdSignIn <$true|$false>` <br/> <span data-ttu-id="70f6e-171">**Esempi:**</span><span class="sxs-lookup"><span data-stu-id="70f6e-171">**Examples:**</span></span> <br/><span data-ttu-id="70f6e-172">Per abilitare gli ID di social network per questo modello personalizzato</span><span class="sxs-lookup"><span data-stu-id="70f6e-172">To enable social IDs for this custom template</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $true` <br/> <span data-ttu-id="70f6e-173">Per disabilitare gli ID di social network per questo modello personalizzato</span><span class="sxs-lookup"><span data-stu-id="70f6e-173">To disable social IDs for this custom template</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $false`|

## <a name="create-an-ome-branding-template-advanced-message-encryption"></a><span data-ttu-id="70f6e-174">Creare un modello di personalizzazione di OME (Advanced Message Encryption)</span><span class="sxs-lookup"><span data-stu-id="70f6e-174">Create an OME branding template (Advanced Message Encryption)</span></span>

<span data-ttu-id="70f6e-175">Se si dispone di Office 365 Advanced Message Encryption, è possibile creare modelli di personalizzazione personalizzati per l'organizzazione utilizzando il cmdlet [New-OMEConfiguration.](https://docs.microsoft.com/powershell/module/exchange/new-omeconfiguration)</span><span class="sxs-lookup"><span data-stu-id="70f6e-175">If you have Office 365 Advanced Message Encryption, you can create custom branding templates for your organization by using the [New-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/new-omeconfiguration) cmdlet.</span></span> <span data-ttu-id="70f6e-176">Dopo aver creato il modello, è possibile modificare il modello utilizzando il cmdlet Set-OMEConfiguration come descritto in [Modify an OME branding template.](#modify-an-ome-branding-template)</span><span class="sxs-lookup"><span data-stu-id="70f6e-176">Once you've created the template, you modify the template by using the Set-OMEConfiguration cmdlet as described in [Modify an OME branding template](#modify-an-ome-branding-template).</span></span> <span data-ttu-id="70f6e-177">È possibile creare più modelli.</span><span class="sxs-lookup"><span data-stu-id="70f6e-177">You can create multiple templates.</span></span>

<span data-ttu-id="70f6e-178">Per creare un nuovo modello di personalizzazione:</span><span class="sxs-lookup"><span data-stu-id="70f6e-178">To create a new custom branding template:</span></span>

1. <span data-ttu-id="70f6e-179">Utilizzando un account aziendale o dell'istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione, avviare una sessione Windows PowerShell e connettersi a Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="70f6e-179">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="70f6e-180">Per istruzioni, vedere [Connettersi a PowerShell di Exchange Online](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="70f6e-180">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="70f6e-181">Utilizzare il cmdlet [New-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/new-omeconfiguration) per creare un nuovo modello.</span><span class="sxs-lookup"><span data-stu-id="70f6e-181">Use the [New-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/new-omeconfiguration) cmdlet to create a new template.</span></span>

   ```powershell
   New-OMEConfiguration -Identity "<OMEConfigurationName>"
   ```

   <span data-ttu-id="70f6e-182">Ad esempio,</span><span class="sxs-lookup"><span data-stu-id="70f6e-182">For example,</span></span>

   ```powershell
   New-OMEConfiguration -Identity "Custom branding template"
   ```

## <a name="return-the-default-branding-template-to-its-original-values"></a><span data-ttu-id="70f6e-183">Ripristinare i valori originali del modello di personalizzazione predefinito</span><span class="sxs-lookup"><span data-stu-id="70f6e-183">Return the default branding template to its original values</span></span>

<span data-ttu-id="70f6e-184">Per rimuovere tutte le modifiche dal modello predefinito, incluse le personalizzazioni del marchio e così via, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="70f6e-184">To remove all modifications from the default template, including brand customizations, and so on, complete these steps:</span></span>
  
1. <span data-ttu-id="70f6e-185">Utilizzando un account aziendale o dell'istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione, avviare una sessione Windows PowerShell e connettersi a Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="70f6e-185">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="70f6e-186">Per istruzioni, vedere [Connettersi a PowerShell di Exchange Online](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="70f6e-186">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="70f6e-187">Utilizzare il cmdlet **Set-OMEConfiguration** come descritto in [Set-OMEConfiguration.](https://docs.microsoft.com/powershell/module/exchange/Set-OMEConfiguration)</span><span class="sxs-lookup"><span data-stu-id="70f6e-187">Use the **Set-OMEConfiguration** cmdlet as described in [Set-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/Set-OMEConfiguration).</span></span> <span data-ttu-id="70f6e-188">Per rimuovere le personalizzazioni dell'organizzazione dai valori DisclaimerText, EmailText e PortalText, impostare il valore su una stringa `""` vuota.</span><span class="sxs-lookup"><span data-stu-id="70f6e-188">To remove your organization's branded customizations from the DisclaimerText, EmailText, and PortalText values, set the value to an empty string, `""`.</span></span> <span data-ttu-id="70f6e-189">Per tutti i valori delle immagini, ad esempio Logo, imposta il valore su  `"$null"` .</span><span class="sxs-lookup"><span data-stu-id="70f6e-189">For all image values, such as Logo, set the value to  `"$null"`.</span></span>

   <span data-ttu-id="70f6e-190">Nella tabella seguente vengono descritte le impostazioni predefinite dell'opzione di personalizzazione della crittografia.</span><span class="sxs-lookup"><span data-stu-id="70f6e-190">The following table describes the encryption customization option defaults.</span></span>

   <span data-ttu-id="70f6e-191">**Per ripristinare il testo e l'immagine predefiniti per questa funzionalità dell'esperienza di crittografia**</span><span class="sxs-lookup"><span data-stu-id="70f6e-191">**To revert this feature of the encryption experience back to the default text and image**</span></span>|<span data-ttu-id="70f6e-192">**Usare questi comandi**</span><span class="sxs-lookup"><span data-stu-id="70f6e-192">**Use these commands**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="70f6e-193">Testo predefinito fornito con messaggi di posta elettronica crittografati</span><span class="sxs-lookup"><span data-stu-id="70f6e-193">Default text that comes with encrypted email messages</span></span>  <br/> <span data-ttu-id="70f6e-194">Il testo predefinito viene visualizzato sopra le istruzioni per la visualizzazione di messaggi crittografati</span><span class="sxs-lookup"><span data-stu-id="70f6e-194">The default text appears above the instructions for viewing encrypted messages</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -EmailText "<empty string>"` <br/> <span data-ttu-id="70f6e-195">**Esempio:**</span><span class="sxs-lookup"><span data-stu-id="70f6e-195">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText ""`|
   |<span data-ttu-id="70f6e-196">dichiarazione di non responsabilità nella posta elettronica che contiene il messaggio crittografato</span><span class="sxs-lookup"><span data-stu-id="70f6e-196">Disclaimer statement in the email that contains the encrypted message</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" DisclaimerText "<empty string>"` <br/> <span data-ttu-id="70f6e-197">**Esempio:**</span><span class="sxs-lookup"><span data-stu-id="70f6e-197">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText ""`|
   |<span data-ttu-id="70f6e-198">testo visualizzato nella parte superiore del portale di visualizzazione del messaggio crittografato</span><span class="sxs-lookup"><span data-stu-id="70f6e-198">Text that appears at the top of the encrypted mail viewing portal</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PortalText "<empty string>"` <br/> <span data-ttu-id="70f6e-199">**Esempio di ripristino dell'impostazione predefinita:**</span><span class="sxs-lookup"><span data-stu-id="70f6e-199">**Example reverting back to default:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText ""`|
   |<span data-ttu-id="70f6e-200">Logo</span><span class="sxs-lookup"><span data-stu-id="70f6e-200">Logo</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -Image <"$null">` <br/> <span data-ttu-id="70f6e-201">**Esempio di ripristino dell'impostazione predefinita:**</span><span class="sxs-lookup"><span data-stu-id="70f6e-201">**Example reverting back to default:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME configuration" -Image $null`|
   |<span data-ttu-id="70f6e-202">Colore di sfondo</span><span class="sxs-lookup"><span data-stu-id="70f6e-202">Background color</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -BackgroundColor "$null">` <br/> <span data-ttu-id="70f6e-203">**Esempio di ripristino dell'impostazione predefinita:**</span><span class="sxs-lookup"><span data-stu-id="70f6e-203">**Example reverting back to default:**</span></span> <br/> `Set-OMEConfiguration -Identity "OME configuration" -BackgroundColor $null`|
   |

## <a name="remove-a-custom-branding-template-advanced-message-encryption"></a><span data-ttu-id="70f6e-204">Rimuovere un modello di personalizzazione (Advanced Message Encryption)</span><span class="sxs-lookup"><span data-stu-id="70f6e-204">Remove a custom branding template (Advanced Message Encryption)</span></span>

<span data-ttu-id="70f6e-205">Puoi solo rimuovere o eliminare i modelli di personalizzazione che hai creato.</span><span class="sxs-lookup"><span data-stu-id="70f6e-205">You can only remove or delete branding templates that you've made.</span></span> <span data-ttu-id="70f6e-206">Non è possibile rimuovere il modello di personalizzazione predefinito.</span><span class="sxs-lookup"><span data-stu-id="70f6e-206">You can't remove the default branding template.</span></span>

<span data-ttu-id="70f6e-207">Per rimuovere un modello di personalizzazione personalizzato:</span><span class="sxs-lookup"><span data-stu-id="70f6e-207">To remove a custom branding template:</span></span>
  
1. <span data-ttu-id="70f6e-208">Utilizzando un account aziendale o dell'istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione, avviare una sessione Windows PowerShell e connettersi a Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="70f6e-208">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="70f6e-209">Per istruzioni, vedere [Connettersi a PowerShell di Exchange Online](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="70f6e-209">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="70f6e-210">Utilizzare il cmdlet **Remove-OMEConfiguration** nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="70f6e-210">Use the **Remove-OMEConfiguration** cmdlet as follows:</span></span>

   ```powershell
   Remove-OMEConfiguration -Identity ""<OMEConfigurationName>"
   ```

   <span data-ttu-id="70f6e-211">Ad esempio,</span><span class="sxs-lookup"><span data-stu-id="70f6e-211">For example,</span></span>

   ```powershell
   Remove-OMEConfiguration -Identity "Branding template 1"
   ```

   <span data-ttu-id="70f6e-212">Per ulteriori informazioni, vedere [Remove-OMEConfiguration.](https://docs.microsoft.com/powershell/module/exchange/remove-omeconfiguration)</span><span class="sxs-lookup"><span data-stu-id="70f6e-212">For more information, see [Remove-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/remove-omeconfiguration).</span></span>

## <a name="create-an-exchange-mail-flow-rule-that-applies-your-custom-branding-to-encrypted-emails"></a><span data-ttu-id="70f6e-213">Creare una regola del flusso di posta di Exchange che applica la personalizzazione ai messaggi di posta elettronica crittografati</span><span class="sxs-lookup"><span data-stu-id="70f6e-213">Create an Exchange mail flow rule that applies your custom branding to encrypted emails</span></span>

<span data-ttu-id="70f6e-214">Dopo aver modificato il modello predefinito o creato nuovi modelli di personalizzazione, è possibile creare regole del flusso di posta di Exchange per applicare la personalizzazione in base a determinate condizioni.</span><span class="sxs-lookup"><span data-stu-id="70f6e-214">After you've either modified the default template or created new branding templates, you can create Exchange mail flow rules to apply your custom branding based on certain conditions.</span></span> <span data-ttu-id="70f6e-215">Tale regola applica la personalizzazione negli scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="70f6e-215">Such a rule will apply custom branding in the following scenarios:</span></span>

- <span data-ttu-id="70f6e-216">Se il messaggio di posta elettronica è stato crittografato manualmente dall'utente finale utilizzando Outlook o Outlook sul Web, in precedenza Outlook Web App</span><span class="sxs-lookup"><span data-stu-id="70f6e-216">If the email was manually encrypted by the end user using Outlook or Outlook on the web, formerly Outlook Web App</span></span>

- <span data-ttu-id="70f6e-217">Se il messaggio di posta elettronica è stato crittografato automaticamente da una regola del flusso di posta di Exchange o da un criterio di prevenzione della perdita dei dati</span><span class="sxs-lookup"><span data-stu-id="70f6e-217">If the email was automatically encrypted by an Exchange mail flow rule or Data Loss Prevention policy</span></span>

<span data-ttu-id="70f6e-218">Per informazioni su come creare una regola del flusso di posta di Exchange che applica la crittografia, vedere Definire le regole del flusso di posta per crittografare i messaggi di posta [elettronica in Office 365.](define-mail-flow-rules-to-encrypt-email.md)</span><span class="sxs-lookup"><span data-stu-id="70f6e-218">For information on how to create an Exchange mail flow rule that applies encryption, see [Define mail flow rules to encrypt email messages in Office 365](define-mail-flow-rules-to-encrypt-email.md).</span></span>

1. <span data-ttu-id="70f6e-219">In un Web browser, usando un account aziendale o dell'istituto di istruzione a cui sono state concesse autorizzazioni di amministratore globale, accedere a [Office 365.](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser)</span><span class="sxs-lookup"><span data-stu-id="70f6e-219">In a web browser, using a work or school account that has been granted global administrator permissions, [sign in to Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).</span></span>

2. <span data-ttu-id="70f6e-220">Scegliere il **riquadro** Amministrazione.</span><span class="sxs-lookup"><span data-stu-id="70f6e-220">Choose the **Admin** tile.</span></span>

3. <span data-ttu-id="70f6e-221">Nell'interfaccia di amministrazione di Microsoft 365 scegliere **Interfaccia di** amministrazione di \> **Exchange.**</span><span class="sxs-lookup"><span data-stu-id="70f6e-221">In the Microsoft 365 admin center, choose **Admin centers** \> **Exchange**.</span></span>

4. <span data-ttu-id="70f6e-222">Nell'interfaccia di amministrazione di Exchange, andare a Regole del **flusso** di posta e \>  selezionare **Nuova** icona ![ Crea nuova ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **regola.**</span><span class="sxs-lookup"><span data-stu-id="70f6e-222">In the EAC, go to **Mail flow** \> **Rules** and select **New** ![New icon](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **Create a new rule**.</span></span> <span data-ttu-id="70f6e-223">Per ulteriori informazioni sull'utilizzo dell'interfaccia di amministrazione di Exchange, vedere Interfaccia di amministrazione [di Exchange in Exchange Online.](https://docs.microsoft.com/exchange/exchange-admin-center)</span><span class="sxs-lookup"><span data-stu-id="70f6e-223">For more information about using the EAC, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).</span></span>

5. <span data-ttu-id="70f6e-224">In **Nome** digitare un nome per la regola, ad esempio Personalizzazione per il reparto vendite.</span><span class="sxs-lookup"><span data-stu-id="70f6e-224">In **Name**, type a name for the rule, such as Branding for sales department.</span></span>

6. <span data-ttu-id="70f6e-225">In **Applica questa regola se**, selezionare la condizione Il mittente **si** trova all'interno dell'organizzazione e altre condizioni desiderate nell'elenco delle condizioni disponibili.</span><span class="sxs-lookup"><span data-stu-id="70f6e-225">In **Apply this rule if**, select the condition **The sender is located inside the organization** and other conditions you want from the list of available conditions.</span></span> <span data-ttu-id="70f6e-226">Ad esempio, potresti voler applicare un particolare modello di personalizzazione a:</span><span class="sxs-lookup"><span data-stu-id="70f6e-226">For example, you might want to apply a particular branding template to:</span></span>

   - <span data-ttu-id="70f6e-227">Tutti i messaggi di posta elettronica crittografati inviati dai membri del reparto finanze</span><span class="sxs-lookup"><span data-stu-id="70f6e-227">All encrypted emails sent from members of the finance department</span></span>
   - <span data-ttu-id="70f6e-228">Messaggi di posta elettronica crittografati inviati con una determinata parola chiave, ad esempio "Esterno" o "Partner"</span><span class="sxs-lookup"><span data-stu-id="70f6e-228">Encrypted emails sent with a certain keyword such as "External" or "Partner"</span></span>
   - <span data-ttu-id="70f6e-229">Messaggi di posta elettronica crittografati inviati a un dominio specifico</span><span class="sxs-lookup"><span data-stu-id="70f6e-229">Encrypted emails sent to a particular domain</span></span>

7. <span data-ttu-id="70f6e-230">In **Eseguire le operazioni seguenti** selezionare Modifica la **sicurezza** dei messaggi Applicare la \> **personalizzazione ai messaggi OME.**</span><span class="sxs-lookup"><span data-stu-id="70f6e-230">From **Do the following**, select **Modify the message security** \> **Apply custom branding to OME messages**.</span></span> <span data-ttu-id="70f6e-231">Nell'elenco a discesa selezionare quindi un modello di personalizzazione.</span><span class="sxs-lookup"><span data-stu-id="70f6e-231">Next, from the drop-down, select a branding template.</span></span>

8. <span data-ttu-id="70f6e-232">(Facoltativo) È possibile configurare la regola del flusso di posta per applicare la crittografia e la personalizzazione.</span><span class="sxs-lookup"><span data-stu-id="70f6e-232">(Optional) You can configure the mail flow rule to apply encryption and custom branding.</span></span> <span data-ttu-id="70f6e-233">In **Eseguire le operazioni seguenti,** selezionare Modifica **la** sicurezza dei messaggi e quindi scegliere Applica crittografia dei messaggi di **Office 365 e protezione dei diritti.**</span><span class="sxs-lookup"><span data-stu-id="70f6e-233">From **Do the following**, select **Modify the message security**, and then choose **Apply Office 365 Message Encryption and rights protection**.</span></span> <span data-ttu-id="70f6e-234">Selezionare un modello RMS nell'elenco, scegliere **Salva** e quindi **OK.**</span><span class="sxs-lookup"><span data-stu-id="70f6e-234">Select an RMS template from the list, choose **Save**, and then choose **OK**.</span></span>
  
   <span data-ttu-id="70f6e-235">L'elenco dei modelli include i modelli e le opzioni predefiniti e gli eventuali modelli personalizzati creati.</span><span class="sxs-lookup"><span data-stu-id="70f6e-235">The list of templates includes default templates and options and any custom templates you create.</span></span> <span data-ttu-id="70f6e-236">Se l'elenco è vuoto, assicurarsi di aver configurato la crittografia dei messaggi di Office 365 con le nuove funzionalità.</span><span class="sxs-lookup"><span data-stu-id="70f6e-236">If the list is empty, ensure that you have set up Office 365 Message Encryption with the new capabilities.</span></span> <span data-ttu-id="70f6e-237">Per istruzioni, vedere Configurare le nuove funzionalità di crittografia dei [messaggi di Office 365.](set-up-new-message-encryption-capabilities.md)</span><span class="sxs-lookup"><span data-stu-id="70f6e-237">For instructions, see [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md).</span></span> <span data-ttu-id="70f6e-238">Per informazioni sui modelli predefiniti, vedere Configurazione e gestione dei [modelli per Azure Information Protection.](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)</span><span class="sxs-lookup"><span data-stu-id="70f6e-238">For information about the default templates, see [Configuring and managing templates for Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates).</span></span> <span data-ttu-id="70f6e-239">Per informazioni **sull'opzione Non inoltrare,** vedere [Opzione Non inoltrare per i messaggi di posta elettronica.](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)</span><span class="sxs-lookup"><span data-stu-id="70f6e-239">For information about the **Do Not Forward** option, see [Do Not Forward option for emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails).</span></span> <span data-ttu-id="70f6e-240">Per informazioni sull'opzione **solo crittografia,** vedere [l'opzione Solo crittografia per i messaggi di posta elettronica.](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)</span><span class="sxs-lookup"><span data-stu-id="70f6e-240">For information about the **encrypt only** option, see [Encrypt Only option for emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).</span></span>

   <span data-ttu-id="70f6e-241">Scegliere **aggiungi azione** se si desidera specificare un'altra azione.</span><span class="sxs-lookup"><span data-stu-id="70f6e-241">Choose **add action** if you want to specify another action.</span></span>

## <a name="background-color-reference"></a><span data-ttu-id="70f6e-242">Informazioni di riferimento sul colore di sfondo</span><span class="sxs-lookup"><span data-stu-id="70f6e-242">Background color reference</span></span>

<span data-ttu-id="70f6e-243">I nomi dei colori che è possibile utilizzare per il colore di sfondo sono limitati.</span><span class="sxs-lookup"><span data-stu-id="70f6e-243">The color names that you can use for the background color are limited.</span></span> <span data-ttu-id="70f6e-244">Anziché un nome di colore, puoi usare un valore di codice esadecimale (#RRGGBB).</span><span class="sxs-lookup"><span data-stu-id="70f6e-244">Instead of a color name, you can use a hex code value (#RRGGBB).</span></span> <span data-ttu-id="70f6e-245">È possibile utilizzare un valore di codice esadecimale corrispondente a un nome di colore oppure un valore di codice esadecimale personalizzato.</span><span class="sxs-lookup"><span data-stu-id="70f6e-245">You can use a hex code value that corresponds to a color name, or you can use a custom hex code value.</span></span> <span data-ttu-id="70f6e-246">Assicurarsi di racchiudere il valore del codice esadecimale tra virgolette (ad esempio, `"#f0f8ff"` ).</span><span class="sxs-lookup"><span data-stu-id="70f6e-246">Be sure to enclose the hex code value in quotation marks (for example, `"#f0f8ff"`).</span></span>

<span data-ttu-id="70f6e-247">I nomi dei colori di sfondo disponibili e i valori del codice esadecimale corrispondenti sono descritti nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="70f6e-247">The available background color names and their corresponding hex code values are described in the following table.</span></span>

|<span data-ttu-id="70f6e-248">**Nome colore**</span><span class="sxs-lookup"><span data-stu-id="70f6e-248">**Color name**</span></span>|<span data-ttu-id="70f6e-249">**Codice colore**</span><span class="sxs-lookup"><span data-stu-id="70f6e-249">**Color code**</span></span>|
|---|---|
|`aliceblue`|<span data-ttu-id="70f6e-250">#f0f8ff</span><span class="sxs-lookup"><span data-stu-id="70f6e-250">#f0f8ff</span></span>|
|`antiquewhite`|<span data-ttu-id="70f6e-251">#faebd7</span><span class="sxs-lookup"><span data-stu-id="70f6e-251">#faebd7</span></span>|
|`aqua`|<span data-ttu-id="70f6e-252">#00ffff</span><span class="sxs-lookup"><span data-stu-id="70f6e-252">#00ffff</span></span>|
|`aquamarine`|<span data-ttu-id="70f6e-253">#7fffd4</span><span class="sxs-lookup"><span data-stu-id="70f6e-253">#7fffd4</span></span>|
|`azure`|<span data-ttu-id="70f6e-254">#f0ffff</span><span class="sxs-lookup"><span data-stu-id="70f6e-254">#f0ffff</span></span>|
|`beige`|<span data-ttu-id="70f6e-255">#f5f5dc</span><span class="sxs-lookup"><span data-stu-id="70f6e-255">#f5f5dc</span></span>|
|`bisque`|<span data-ttu-id="70f6e-256">#ffe4c4</span><span class="sxs-lookup"><span data-stu-id="70f6e-256">#ffe4c4</span></span>|
|`black`|<span data-ttu-id="70f6e-257">#000000</span><span class="sxs-lookup"><span data-stu-id="70f6e-257">#000000</span></span>|
|`blanchedalmond`|<span data-ttu-id="70f6e-258">#ffebcd</span><span class="sxs-lookup"><span data-stu-id="70f6e-258">#ffebcd</span></span>|
|`blue`|<span data-ttu-id="70f6e-259">#0000ff</span><span class="sxs-lookup"><span data-stu-id="70f6e-259">#0000ff</span></span>|
|`blueviolet`|<span data-ttu-id="70f6e-260">#8a2be2</span><span class="sxs-lookup"><span data-stu-id="70f6e-260">#8a2be2</span></span>|
|`brown`|<span data-ttu-id="70f6e-261">#a52a2a</span><span class="sxs-lookup"><span data-stu-id="70f6e-261">#a52a2a</span></span>|
|`burlywood`|<span data-ttu-id="70f6e-262">#deb887</span><span class="sxs-lookup"><span data-stu-id="70f6e-262">#deb887</span></span>|
|`cadetblue`|<span data-ttu-id="70f6e-263">#5f9ea0</span><span class="sxs-lookup"><span data-stu-id="70f6e-263">#5f9ea0</span></span>|
|`chartreuse`|<span data-ttu-id="70f6e-264">#7fff00</span><span class="sxs-lookup"><span data-stu-id="70f6e-264">#7fff00</span></span>|
|`chocolate`|<span data-ttu-id="70f6e-265">#d2691e</span><span class="sxs-lookup"><span data-stu-id="70f6e-265">#d2691e</span></span>|
|`coral`|<span data-ttu-id="70f6e-266">#ff7f50</span><span class="sxs-lookup"><span data-stu-id="70f6e-266">#ff7f50</span></span>|
|`cornflowerblue`|<span data-ttu-id="70f6e-267">#6495ed</span><span class="sxs-lookup"><span data-stu-id="70f6e-267">#6495ed</span></span>|
|`cornsilk`|<span data-ttu-id="70f6e-268">#fff8dc</span><span class="sxs-lookup"><span data-stu-id="70f6e-268">#fff8dc</span></span>|
|`crimson`|<span data-ttu-id="70f6e-269">#dc143c</span><span class="sxs-lookup"><span data-stu-id="70f6e-269">#dc143c</span></span>|
|`cyan`|<span data-ttu-id="70f6e-270">#00ffff</span><span class="sxs-lookup"><span data-stu-id="70f6e-270">#00ffff</span></span>|
|`darkblue`|<span data-ttu-id="70f6e-271">#00008b</span><span class="sxs-lookup"><span data-stu-id="70f6e-271">#00008b</span></span>|
|`darkcyan`|<span data-ttu-id="70f6e-272">#008b8b</span><span class="sxs-lookup"><span data-stu-id="70f6e-272">#008b8b</span></span>|
|`darkgoldenrod`|<span data-ttu-id="70f6e-273">#b8860b</span><span class="sxs-lookup"><span data-stu-id="70f6e-273">#b8860b</span></span>|
|`darkgray`|<span data-ttu-id="70f6e-274">#a9a9a9</span><span class="sxs-lookup"><span data-stu-id="70f6e-274">#a9a9a9</span></span>|
|`darkgreen`|<span data-ttu-id="70f6e-275">#006400</span><span class="sxs-lookup"><span data-stu-id="70f6e-275">#006400</span></span>|
|`darkkhaki`|<span data-ttu-id="70f6e-276">#bdb76b</span><span class="sxs-lookup"><span data-stu-id="70f6e-276">#bdb76b</span></span>|
|`darkmagenta`|<span data-ttu-id="70f6e-277">#8b008b</span><span class="sxs-lookup"><span data-stu-id="70f6e-277">#8b008b</span></span>|
|`darkolivegreen`|<span data-ttu-id="70f6e-278">#556b2f</span><span class="sxs-lookup"><span data-stu-id="70f6e-278">#556b2f</span></span>|
|`darkorange`|<span data-ttu-id="70f6e-279">#ff8c00</span><span class="sxs-lookup"><span data-stu-id="70f6e-279">#ff8c00</span></span>|
|`darkorchid`|<span data-ttu-id="70f6e-280">#9932cc</span><span class="sxs-lookup"><span data-stu-id="70f6e-280">#9932cc</span></span>|
|`darkred`|<span data-ttu-id="70f6e-281">#8b0000</span><span class="sxs-lookup"><span data-stu-id="70f6e-281">#8b0000</span></span>|
|`darksalmon`|<span data-ttu-id="70f6e-282">#e9967a</span><span class="sxs-lookup"><span data-stu-id="70f6e-282">#e9967a</span></span>|
|`darkseagreen`|<span data-ttu-id="70f6e-283">#8fbc8f</span><span class="sxs-lookup"><span data-stu-id="70f6e-283">#8fbc8f</span></span>|
|`darkslateblue`|<span data-ttu-id="70f6e-284">#483d8b</span><span class="sxs-lookup"><span data-stu-id="70f6e-284">#483d8b</span></span>|
|`darkslategray`|<span data-ttu-id="70f6e-285">#2f4f4f</span><span class="sxs-lookup"><span data-stu-id="70f6e-285">#2f4f4f</span></span>|
|`darkturquoise`|<span data-ttu-id="70f6e-286">#00ced1</span><span class="sxs-lookup"><span data-stu-id="70f6e-286">#00ced1</span></span>|
|`darkviolet`|<span data-ttu-id="70f6e-287">#9400d3</span><span class="sxs-lookup"><span data-stu-id="70f6e-287">#9400d3</span></span>|
|`deeppink`|<span data-ttu-id="70f6e-288">#ff1493</span><span class="sxs-lookup"><span data-stu-id="70f6e-288">#ff1493</span></span>|
|`deepskyblue`|<span data-ttu-id="70f6e-289">#00bfff</span><span class="sxs-lookup"><span data-stu-id="70f6e-289">#00bfff</span></span>|
|`dimgray`|<span data-ttu-id="70f6e-290">#696969</span><span class="sxs-lookup"><span data-stu-id="70f6e-290">#696969</span></span>|
|`dodgerblue`|<span data-ttu-id="70f6e-291">#1e90ff</span><span class="sxs-lookup"><span data-stu-id="70f6e-291">#1e90ff</span></span>|
|`firebrick`|<span data-ttu-id="70f6e-292">#b22222</span><span class="sxs-lookup"><span data-stu-id="70f6e-292">#b22222</span></span>|
|`floralwhite`|<span data-ttu-id="70f6e-293">#fffaf0</span><span class="sxs-lookup"><span data-stu-id="70f6e-293">#fffaf0</span></span>|
|`forestgreen`|<span data-ttu-id="70f6e-294">#228b22</span><span class="sxs-lookup"><span data-stu-id="70f6e-294">#228b22</span></span>|
|`fuchsia`|<span data-ttu-id="70f6e-295">#ff00ff</span><span class="sxs-lookup"><span data-stu-id="70f6e-295">#ff00ff</span></span>|
|`gainsboro`|<span data-ttu-id="70f6e-296">#dcdcdc</span><span class="sxs-lookup"><span data-stu-id="70f6e-296">#dcdcdc</span></span>|
|`ghostwhite`|<span data-ttu-id="70f6e-297">#f8f8ff</span><span class="sxs-lookup"><span data-stu-id="70f6e-297">#f8f8ff</span></span>|
|`gold`|<span data-ttu-id="70f6e-298">#ffd700</span><span class="sxs-lookup"><span data-stu-id="70f6e-298">#ffd700</span></span>|
|`goldenrod`|<span data-ttu-id="70f6e-299">#daa520</span><span class="sxs-lookup"><span data-stu-id="70f6e-299">#daa520</span></span>|
|`gray`|<span data-ttu-id="70f6e-300">#808080</span><span class="sxs-lookup"><span data-stu-id="70f6e-300">#808080</span></span>|
|`green`|<span data-ttu-id="70f6e-301">#008000</span><span class="sxs-lookup"><span data-stu-id="70f6e-301">#008000</span></span>|
|`greenyellow`|<span data-ttu-id="70f6e-302">#adff2f</span><span class="sxs-lookup"><span data-stu-id="70f6e-302">#adff2f</span></span>|
|`honeydew`|<span data-ttu-id="70f6e-303">#f0fff0</span><span class="sxs-lookup"><span data-stu-id="70f6e-303">#f0fff0</span></span>|
|`hotpink`|<span data-ttu-id="70f6e-304">#ff69b4</span><span class="sxs-lookup"><span data-stu-id="70f6e-304">#ff69b4</span></span>|
|`indianred`|<span data-ttu-id="70f6e-305">#cd5c5c</span><span class="sxs-lookup"><span data-stu-id="70f6e-305">#cd5c5c</span></span>|
|`indigo`|<span data-ttu-id="70f6e-306">#4b0082</span><span class="sxs-lookup"><span data-stu-id="70f6e-306">#4b0082</span></span>|
|`ivory`|<span data-ttu-id="70f6e-307">#fffff0</span><span class="sxs-lookup"><span data-stu-id="70f6e-307">#fffff0</span></span>|
|`khaki`|<span data-ttu-id="70f6e-308">#f0e68c</span><span class="sxs-lookup"><span data-stu-id="70f6e-308">#f0e68c</span></span>|
|`lavender`|<span data-ttu-id="70f6e-309">#e6e6fa</span><span class="sxs-lookup"><span data-stu-id="70f6e-309">#e6e6fa</span></span>|
|`lavenderblush`|<span data-ttu-id="70f6e-310">#fff0f5</span><span class="sxs-lookup"><span data-stu-id="70f6e-310">#fff0f5</span></span>|
|`lawngreen`|<span data-ttu-id="70f6e-311">#7cfc00</span><span class="sxs-lookup"><span data-stu-id="70f6e-311">#7cfc00</span></span>|
|`lemonchiffon`|<span data-ttu-id="70f6e-312">#fffacd</span><span class="sxs-lookup"><span data-stu-id="70f6e-312">#fffacd</span></span>|
|`lightblue`|<span data-ttu-id="70f6e-313">#add8e6</span><span class="sxs-lookup"><span data-stu-id="70f6e-313">#add8e6</span></span>|
|`lightcoral`|<span data-ttu-id="70f6e-314">#f08080</span><span class="sxs-lookup"><span data-stu-id="70f6e-314">#f08080</span></span>|
|`lightcyan`|<span data-ttu-id="70f6e-315">#e0ffff</span><span class="sxs-lookup"><span data-stu-id="70f6e-315">#e0ffff</span></span>|
|`lightgoldenrodyellow`|<span data-ttu-id="70f6e-316">#fafad2</span><span class="sxs-lookup"><span data-stu-id="70f6e-316">#fafad2</span></span>|
|`lightgray`|<span data-ttu-id="70f6e-317">#d3d3d3</span><span class="sxs-lookup"><span data-stu-id="70f6e-317">#d3d3d3</span></span>|
|`lightgrey`|<span data-ttu-id="70f6e-318">#d3d3d3</span><span class="sxs-lookup"><span data-stu-id="70f6e-318">#d3d3d3</span></span>|
|`lightgreen`|<span data-ttu-id="70f6e-319">#90ee90</span><span class="sxs-lookup"><span data-stu-id="70f6e-319">#90ee90</span></span>|
|`lightpink`|<span data-ttu-id="70f6e-320">#ffb6c1</span><span class="sxs-lookup"><span data-stu-id="70f6e-320">#ffb6c1</span></span>|
|`lightsalmon`|<span data-ttu-id="70f6e-321">#ffa07a</span><span class="sxs-lookup"><span data-stu-id="70f6e-321">#ffa07a</span></span>|
|`lightseagreen`|<span data-ttu-id="70f6e-322">#20b2aa</span><span class="sxs-lookup"><span data-stu-id="70f6e-322">#20b2aa</span></span>|
|`lightskyblue`|<span data-ttu-id="70f6e-323">#87cefa</span><span class="sxs-lookup"><span data-stu-id="70f6e-323">#87cefa</span></span>|
|`lightslategray`|<span data-ttu-id="70f6e-324">#778899</span><span class="sxs-lookup"><span data-stu-id="70f6e-324">#778899</span></span>|
|`lightsteelblue`|<span data-ttu-id="70f6e-325">#b0c4de</span><span class="sxs-lookup"><span data-stu-id="70f6e-325">#b0c4de</span></span>|
|`lightyellow`|<span data-ttu-id="70f6e-326">#ffffe0</span><span class="sxs-lookup"><span data-stu-id="70f6e-326">#ffffe0</span></span>|
|`lime`|<span data-ttu-id="70f6e-327">#00ff00</span><span class="sxs-lookup"><span data-stu-id="70f6e-327">#00ff00</span></span>|
|`limegreen`|<span data-ttu-id="70f6e-328">#32cd32</span><span class="sxs-lookup"><span data-stu-id="70f6e-328">#32cd32</span></span>|
|`linen`|<span data-ttu-id="70f6e-329">#faf0e6</span><span class="sxs-lookup"><span data-stu-id="70f6e-329">#faf0e6</span></span>|
|`magenta`|<span data-ttu-id="70f6e-330">#ff00ff</span><span class="sxs-lookup"><span data-stu-id="70f6e-330">#ff00ff</span></span>|
|`maroon`|<span data-ttu-id="70f6e-331">#800000</span><span class="sxs-lookup"><span data-stu-id="70f6e-331">#800000</span></span>|
|`mediumaquamarine`|<span data-ttu-id="70f6e-332">#66cdaa</span><span class="sxs-lookup"><span data-stu-id="70f6e-332">#66cdaa</span></span>|
|`mediumblue`|<span data-ttu-id="70f6e-333">#0000cd</span><span class="sxs-lookup"><span data-stu-id="70f6e-333">#0000cd</span></span>|
|`mediumorchid`|<span data-ttu-id="70f6e-334">#ba55d3</span><span class="sxs-lookup"><span data-stu-id="70f6e-334">#ba55d3</span></span>|
|`mediumpurple`|<span data-ttu-id="70f6e-335">#9370db</span><span class="sxs-lookup"><span data-stu-id="70f6e-335">#9370db</span></span>|
|`mediumseagreen`|<span data-ttu-id="70f6e-336">#3cb371</span><span class="sxs-lookup"><span data-stu-id="70f6e-336">#3cb371</span></span>|
|`mediumslateblue`|<span data-ttu-id="70f6e-337">#7b68ee</span><span class="sxs-lookup"><span data-stu-id="70f6e-337">#7b68ee</span></span>|
|`mediumspringgreen`|<span data-ttu-id="70f6e-338">#00fa9a</span><span class="sxs-lookup"><span data-stu-id="70f6e-338">#00fa9a</span></span>|
|`mediumturquoise`|<span data-ttu-id="70f6e-339">#48d1cc</span><span class="sxs-lookup"><span data-stu-id="70f6e-339">#48d1cc</span></span>|
|`mediumvioletred`|<span data-ttu-id="70f6e-340">#c71585</span><span class="sxs-lookup"><span data-stu-id="70f6e-340">#c71585</span></span>|
|`midnightblue`|<span data-ttu-id="70f6e-341">#191970</span><span class="sxs-lookup"><span data-stu-id="70f6e-341">#191970</span></span>|
|`mintcream`|<span data-ttu-id="70f6e-342">#f5fffa</span><span class="sxs-lookup"><span data-stu-id="70f6e-342">#f5fffa</span></span>|
|`mistyrose`|<span data-ttu-id="70f6e-343">#ffe4e1</span><span class="sxs-lookup"><span data-stu-id="70f6e-343">#ffe4e1</span></span>|
|`moccasin`|<span data-ttu-id="70f6e-344">#ffe4b5</span><span class="sxs-lookup"><span data-stu-id="70f6e-344">#ffe4b5</span></span>|
|`navajowhite`|<span data-ttu-id="70f6e-345">#ffdead</span><span class="sxs-lookup"><span data-stu-id="70f6e-345">#ffdead</span></span>|
|`navy`|<span data-ttu-id="70f6e-346">#000080</span><span class="sxs-lookup"><span data-stu-id="70f6e-346">#000080</span></span>|
|`oldlace`|<span data-ttu-id="70f6e-347">#fdf5e6</span><span class="sxs-lookup"><span data-stu-id="70f6e-347">#fdf5e6</span></span>|
|`olive`|<span data-ttu-id="70f6e-348">#808000</span><span class="sxs-lookup"><span data-stu-id="70f6e-348">#808000</span></span>|
|`olivedrab`|<span data-ttu-id="70f6e-349">#6b8e23</span><span class="sxs-lookup"><span data-stu-id="70f6e-349">#6b8e23</span></span>|
|`orange`|<span data-ttu-id="70f6e-350">#ffa500</span><span class="sxs-lookup"><span data-stu-id="70f6e-350">#ffa500</span></span>|
|`orangered`|<span data-ttu-id="70f6e-351">#ff4500</span><span class="sxs-lookup"><span data-stu-id="70f6e-351">#ff4500</span></span>|
|`orchid`|<span data-ttu-id="70f6e-352">#da70d6</span><span class="sxs-lookup"><span data-stu-id="70f6e-352">#da70d6</span></span>|
|`palegoldenrod`|<span data-ttu-id="70f6e-353">#eee8aa</span><span class="sxs-lookup"><span data-stu-id="70f6e-353">#eee8aa</span></span>|
|`palegreen`|<span data-ttu-id="70f6e-354">#98fb98</span><span class="sxs-lookup"><span data-stu-id="70f6e-354">#98fb98</span></span>|
|`paleturquoise`|<span data-ttu-id="70f6e-355">#afeeee</span><span class="sxs-lookup"><span data-stu-id="70f6e-355">#afeeee</span></span>|
|`palevioletred`|<span data-ttu-id="70f6e-356">#db7093</span><span class="sxs-lookup"><span data-stu-id="70f6e-356">#db7093</span></span>|
|`papayawhip`|<span data-ttu-id="70f6e-357">#ffefd5</span><span class="sxs-lookup"><span data-stu-id="70f6e-357">#ffefd5</span></span>|
|`peachpuff`|<span data-ttu-id="70f6e-358">#ffdab9</span><span class="sxs-lookup"><span data-stu-id="70f6e-358">#ffdab9</span></span>|
|`peru`|<span data-ttu-id="70f6e-359">#cd853f</span><span class="sxs-lookup"><span data-stu-id="70f6e-359">#cd853f</span></span>|
|`pink`|<span data-ttu-id="70f6e-360">#ffc0cb</span><span class="sxs-lookup"><span data-stu-id="70f6e-360">#ffc0cb</span></span>|
|`plum`|<span data-ttu-id="70f6e-361">#dda0dd</span><span class="sxs-lookup"><span data-stu-id="70f6e-361">#dda0dd</span></span>|
|`powderblue`|<span data-ttu-id="70f6e-362">#b0e0e6</span><span class="sxs-lookup"><span data-stu-id="70f6e-362">#b0e0e6</span></span>|
|`purple`|<span data-ttu-id="70f6e-363">#800080</span><span class="sxs-lookup"><span data-stu-id="70f6e-363">#800080</span></span>|
|`red`|<span data-ttu-id="70f6e-364">#ff0000</span><span class="sxs-lookup"><span data-stu-id="70f6e-364">#ff0000</span></span>|
|`rosybrown`|<span data-ttu-id="70f6e-365">#bc8f8f</span><span class="sxs-lookup"><span data-stu-id="70f6e-365">#bc8f8f</span></span>|
|`royalblue`|<span data-ttu-id="70f6e-366">#4169e1</span><span class="sxs-lookup"><span data-stu-id="70f6e-366">#4169e1</span></span>|
|`saddlebrown`|<span data-ttu-id="70f6e-367">#8b4513</span><span class="sxs-lookup"><span data-stu-id="70f6e-367">#8b4513</span></span>|
|`salmon`|<span data-ttu-id="70f6e-368">#fa8072</span><span class="sxs-lookup"><span data-stu-id="70f6e-368">#fa8072</span></span>|
|`sandybrown`|<span data-ttu-id="70f6e-369">#f4a460</span><span class="sxs-lookup"><span data-stu-id="70f6e-369">#f4a460</span></span>|
|`seagreen`|<span data-ttu-id="70f6e-370">#00ff00</span><span class="sxs-lookup"><span data-stu-id="70f6e-370">#00ff00</span></span>|
|`seashell`|<span data-ttu-id="70f6e-371">#fff5ee</span><span class="sxs-lookup"><span data-stu-id="70f6e-371">#fff5ee</span></span>|
|`sienna`|<span data-ttu-id="70f6e-372">#a0522d</span><span class="sxs-lookup"><span data-stu-id="70f6e-372">#a0522d</span></span>|
|`silver`|<span data-ttu-id="70f6e-373">#c0c0c0</span><span class="sxs-lookup"><span data-stu-id="70f6e-373">#c0c0c0</span></span>|
|`skyblue`|<span data-ttu-id="70f6e-374">#87ceeb</span><span class="sxs-lookup"><span data-stu-id="70f6e-374">#87ceeb</span></span>|
|`slateblue`|<span data-ttu-id="70f6e-375">#6a5acd</span><span class="sxs-lookup"><span data-stu-id="70f6e-375">#6a5acd</span></span>|
|`slategray`|<span data-ttu-id="70f6e-376">#708090</span><span class="sxs-lookup"><span data-stu-id="70f6e-376">#708090</span></span>|
|`snow`|<span data-ttu-id="70f6e-377">#fffafa</span><span class="sxs-lookup"><span data-stu-id="70f6e-377">#fffafa</span></span>|
|`springgreen`|<span data-ttu-id="70f6e-378">#00ff7f</span><span class="sxs-lookup"><span data-stu-id="70f6e-378">#00ff7f</span></span>|
|`steelblue`|<span data-ttu-id="70f6e-379">#4682b4</span><span class="sxs-lookup"><span data-stu-id="70f6e-379">#4682b4</span></span>|
|`tan`|<span data-ttu-id="70f6e-380">#d2b48c</span><span class="sxs-lookup"><span data-stu-id="70f6e-380">#d2b48c</span></span>|
|`teal`|<span data-ttu-id="70f6e-381">#008080</span><span class="sxs-lookup"><span data-stu-id="70f6e-381">#008080</span></span>|
|`thistle`|<span data-ttu-id="70f6e-382">#d8bfd8</span><span class="sxs-lookup"><span data-stu-id="70f6e-382">#d8bfd8</span></span>|
|`tomato`|<span data-ttu-id="70f6e-383">#ff6347</span><span class="sxs-lookup"><span data-stu-id="70f6e-383">#ff6347</span></span>|
|`turquoise`|<span data-ttu-id="70f6e-384">#40e0d0</span><span class="sxs-lookup"><span data-stu-id="70f6e-384">#40e0d0</span></span>|
|`violet`|<span data-ttu-id="70f6e-385">#ee82ee</span><span class="sxs-lookup"><span data-stu-id="70f6e-385">#ee82ee</span></span>|
|`wheat`|<span data-ttu-id="70f6e-386">#f5deb3</span><span class="sxs-lookup"><span data-stu-id="70f6e-386">#f5deb3</span></span>|
|`white`|<span data-ttu-id="70f6e-387">#ffffff</span><span class="sxs-lookup"><span data-stu-id="70f6e-387">#ffffff</span></span>|
|`whitesmoke`|<span data-ttu-id="70f6e-388">#f5f5f5</span><span class="sxs-lookup"><span data-stu-id="70f6e-388">#f5f5f5</span></span>|
|`yellow`|<span data-ttu-id="70f6e-389">#ffff00</span><span class="sxs-lookup"><span data-stu-id="70f6e-389">#ffff00</span></span>|
|`yellowgreen`|<span data-ttu-id="70f6e-390">#9acd32</span><span class="sxs-lookup"><span data-stu-id="70f6e-390">#9acd32</span></span>|
