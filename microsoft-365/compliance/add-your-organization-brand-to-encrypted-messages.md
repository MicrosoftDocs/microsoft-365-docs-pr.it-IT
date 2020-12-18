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
description: Informazioni su come gli amministratori globali di Office 365 possono applicare il marchio dell'organizzazione ai messaggi di posta elettronica crittografati & contenuto del portale di crittografia.
ms.openlocfilehash: 56b948fc941da4fb221d929ecd59c5300b135e39
ms.sourcegitcommit: c0495e224f12c448bfc162ef2e4b33b82f064ac8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/17/2020
ms.locfileid: "49709498"
---
# <a name="add-your-organizations-brand-to-your-microsoft-365-for-business-message-encryption-encrypted-messages"></a><span data-ttu-id="5e5fc-103">Aggiungere il marchio dell'organizzazione ai messaggi crittografati per la crittografia dei messaggi di Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="5e5fc-103">Add your organization's brand to your Microsoft 365 for business Message Encryption encrypted messages</span></span>

<span data-ttu-id="5e5fc-104">È possibile applicare il marchio dell'azienda per personalizzare l'aspetto dei messaggi di posta elettronica dell'organizzazione e del portale di crittografia.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-104">You can apply your company branding to customize the look of your organization's email messages and the encryption portal.</span></span> <span data-ttu-id="5e5fc-105">Prima di iniziare, è necessario applicare le autorizzazioni di amministratore globale all'account aziendale o dell'Istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-105">You'll need to apply global administrator permissions to your work or school account before you can get started.</span></span> <span data-ttu-id="5e5fc-106">Quando si dispone di queste autorizzazioni, utilizzare i cmdlet Get-OMEConfiguration e Set-OMEConfiguration Windows PowerShell per personalizzare queste parti dei messaggi di posta elettronica crittografati:</span><span class="sxs-lookup"><span data-stu-id="5e5fc-106">Once you have these permissions, use the Get-OMEConfiguration and Set-OMEConfiguration Windows PowerShell cmdlets to customize these parts of encrypted email messages:</span></span>
  
- <span data-ttu-id="5e5fc-107">Testo introduttivo</span><span class="sxs-lookup"><span data-stu-id="5e5fc-107">Introductory text</span></span>

- <span data-ttu-id="5e5fc-108">Disclaimer text</span><span class="sxs-lookup"><span data-stu-id="5e5fc-108">Disclaimer text</span></span>

- <span data-ttu-id="5e5fc-109">URL per l'informativa sulla privacy dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="5e5fc-109">URL for Your organization's privacy statement</span></span>

- <span data-ttu-id="5e5fc-110">Testo nel portale OME</span><span class="sxs-lookup"><span data-stu-id="5e5fc-110">Text in the OME portal</span></span>

- <span data-ttu-id="5e5fc-111">Logo visualizzato nel messaggio di posta elettronica e nel portale OME o se utilizzare un logo</span><span class="sxs-lookup"><span data-stu-id="5e5fc-111">Logo that appears in the email message and OME portal, or whether to use a logo at all</span></span>

- <span data-ttu-id="5e5fc-112">Colore di sfondo nel messaggio di posta elettronica e nel portale OME</span><span class="sxs-lookup"><span data-stu-id="5e5fc-112">Background color in the email message and OME portal</span></span>

<span data-ttu-id="5e5fc-113">È anche possibile ripristinare l'aspetto predefinito in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-113">You can also revert back to the default look and feel at any time.</span></span>

<span data-ttu-id="5e5fc-114">Se si desidera un maggiore controllo, utilizzare la crittografia avanzata dei messaggi di Office 365 per creare più modelli per i messaggi di posta elettronica crittografati provenienti dall'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-114">If you'd like more control, use Office 365 Advanced Message Encryption to create multiple templates for encrypted emails originating from your organization.</span></span> <span data-ttu-id="5e5fc-115">Utilizzare questi modelli per controllare le parti dell'esperienza dell'utente finale.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-115">Use these templates to control parts of the end-user experience.</span></span> <span data-ttu-id="5e5fc-116">Ad esempio, specificare se i destinatari possono utilizzare gli account Google, Yahoo e Microsoft per accedere al portale di crittografia.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-116">For example, specify whether recipients can use Google, Yahoo, and Microsoft Accounts to sign in to the encryption portal.</span></span> <span data-ttu-id="5e5fc-117">Utilizzare i modelli per soddisfare diversi casi di utilizzo, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="5e5fc-117">Use templates to fulfill several use cases, such as:</span></span>

- <span data-ttu-id="5e5fc-118">Singoli reparti, ad esempio finanza, vendite e così via.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-118">Individual departments, such as Finance, Sales, and so on.</span></span>

- <span data-ttu-id="5e5fc-119">Prodotti diversi</span><span class="sxs-lookup"><span data-stu-id="5e5fc-119">Different products</span></span>

- <span data-ttu-id="5e5fc-120">Diverse aree geografiche o paesi</span><span class="sxs-lookup"><span data-stu-id="5e5fc-120">Different geographical regions or countries</span></span>

- <span data-ttu-id="5e5fc-121">Se si desidera consentire la revoca di messaggi di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="5e5fc-121">Whether you want to allow emails to be revoked</span></span>

- <span data-ttu-id="5e5fc-122">Se si desidera che i messaggi di posta elettronica inviati a destinatari esterni scadano dopo un determinato numero di giorni.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-122">Whether you want emails sent to external recipients to expire after a specified number of days.</span></span>

<span data-ttu-id="5e5fc-123">Dopo aver creato i modelli, è possibile applicarli ai messaggi di posta elettronica crittografati utilizzando le regole del flusso di messaggi di Exchange.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-123">Once you've created the templates, you can apply them to encrypted emails by using Exchange mail flow rules.</span></span> <span data-ttu-id="5e5fc-124">Se si dispone della crittografia avanzata dei messaggi di Office 365, è possibile revocare tutti i messaggi di posta elettronica che sono stati creati utilizzando questi modelli.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-124">If you have Office 365 Advanced Message Encryption, you can revoke any email that you've branded by using these templates.</span></span>

## <a name="work-with-ome-branding-templates"></a><span data-ttu-id="5e5fc-125">Utilizzo dei modelli di personalizzazione OME</span><span class="sxs-lookup"><span data-stu-id="5e5fc-125">Work with OME branding templates</span></span>

<span data-ttu-id="5e5fc-126">È possibile modificare diverse funzionalità all'interno di un modello di branding.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-126">You can modify several features within a branding template.</span></span> <span data-ttu-id="5e5fc-127">È possibile modificare, ma non rimuovere, il modello predefinito.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-127">You can modify, but not remove, the default template.</span></span> <span data-ttu-id="5e5fc-128">Se si dispone di una crittografia avanzata dei messaggi, è anche possibile creare, modificare e rimuovere modelli personalizzati.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-128">If you have Advanced Message Encryption, you can also create, modify, and remove custom templates.</span></span> <span data-ttu-id="5e5fc-129">Utilizzare Windows PowerShell per l'utilizzo di un modello di personalizzazione alla volta.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-129">Use Windows PowerShell to work with one branding template at a time.</span></span>

- <span data-ttu-id="5e5fc-130">[Set-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-omeconfiguration) : consente di modificare il modello di personalizzazione predefinito o un modello personalizzato di personalizzazione creato.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-130">[Set-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-omeconfiguration) - Modify the default branding template or a custom branding template that you created.</span></span>
- <span data-ttu-id="5e5fc-131">[New-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/new-omeconfiguration) -creare un nuovo modello di branding, solo crittografia avanzata dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-131">[New-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/new-omeconfiguration) - Create a new branding template, Advanced Message Encryption only.</span></span>
- <span data-ttu-id="5e5fc-132">[Remove-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/remove-omeconfiguration) -rimuove un modello di personalizzazione personalizzato, solo la crittografia avanzata dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-132">[Remove-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/remove-omeconfiguration) - Remove a custom branding template, Advanced Message Encryption only.</span></span> <span data-ttu-id="5e5fc-133">Non è possibile eliminare il modello di personalizzazione predefinito.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-133">You can't delete the default branding template.</span></span>
  
## <a name="modify-an-ome-branding-template"></a><span data-ttu-id="5e5fc-134">Modificare un modello di branding OME</span><span class="sxs-lookup"><span data-stu-id="5e5fc-134">Modify an OME branding template</span></span>

<span data-ttu-id="5e5fc-135">Utilizzare Windows PowerShell per modificare un modello di branding alla volta.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-135">Use Windows PowerShell to modify one branding template at a time.</span></span> <span data-ttu-id="5e5fc-136">Se si dispone di una crittografia avanzata dei messaggi, è anche possibile creare, modificare e rimuovere modelli personalizzati.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-136">If you have Advanced Message Encryption, you can also create, modify, and remove custom templates.</span></span>

1. <span data-ttu-id="5e5fc-137">Utilizzo di un account aziendale o dell'Istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione, avviare una sessione di Windows PowerShell e connettersi a Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-137">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="5e5fc-138">Per istruzioni, vedere [Connettersi a PowerShell di Exchange Online](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="5e5fc-138">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="5e5fc-139">Utilizzare il cmdlet Set-OMEConfiguration come descritto in [set-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/Set-OMEConfiguration) oppure utilizzare la seguente tabella grafica e le relative istruzioni.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-139">Use the Set-OMEConfiguration cmdlet as described in [Set-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/Set-OMEConfiguration) or use the following graphic and table for guidance.</span></span>

![Parti di posta elettronica personalizzabili](../media/ome-template-breakout.png)

|<span data-ttu-id="5e5fc-141">**Per personalizzare questa funzionalità dell'esperienza di crittografia**</span><span class="sxs-lookup"><span data-stu-id="5e5fc-141">**To customize this feature of the encryption experience**</span></span>|<span data-ttu-id="5e5fc-142">**Utilizzare questi comandi**</span><span class="sxs-lookup"><span data-stu-id="5e5fc-142">**Use these commands**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5e5fc-143">Colore di sfondo</span><span class="sxs-lookup"><span data-stu-id="5e5fc-143">Background color</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -BackgroundColor "<#RRGGBB hexadecimal color code or name value>"` <br/> <span data-ttu-id="5e5fc-144">**Esempio:**</span><span class="sxs-lookup"><span data-stu-id="5e5fc-144">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -BackgroundColor "#ffffff"` <br/> <span data-ttu-id="5e5fc-145">Per ulteriori informazioni sui colori di sfondo, vedere la sezione [colori di sfondo](#background-color-reference) più avanti in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-145">For more information about background colors, see the [Background colors](#background-color-reference) section later in this article.</span></span>|
|<span data-ttu-id="5e5fc-146">Logo</span><span class="sxs-lookup"><span data-stu-id="5e5fc-146">Logo</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -Image <Byte[]>` <br/> <span data-ttu-id="5e5fc-147">**Esempio:**</span><span class="sxs-lookup"><span data-stu-id="5e5fc-147">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -Image (Get-Content "C:\Temp\contosologo.png" -Encoding byte)` <br/> <span data-ttu-id="5e5fc-148">Formati di file supportati: png, jpg, bmp o tiff</span><span class="sxs-lookup"><span data-stu-id="5e5fc-148">Supported file formats: .png, .jpg, .bmp, or .tiff</span></span>  <br/> <span data-ttu-id="5e5fc-149">Dimensione ottimale relativa al file del logo: inferiore a 40 KB</span><span class="sxs-lookup"><span data-stu-id="5e5fc-149">Optimal size of logo file: less than 40 KB</span></span>  <br/> <span data-ttu-id="5e5fc-150">Dimensioni ottimali dell'immagine del logo: 170x70 pixel.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-150">Optimal size of logo image: 170x70 pixels.</span></span> <span data-ttu-id="5e5fc-151">Se l'immagine supera queste dimensioni, il logo viene ridimensionato per essere visualizzato nel portale.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-151">If your image exceeds these dimensions, the service resizes your logo for display in the portal.</span></span> <span data-ttu-id="5e5fc-152">Il servizio non modifica il file grafico stesso.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-152">The service doesn't modify the graphic file itself.</span></span> <span data-ttu-id="5e5fc-153">Per ottenere risultati ottimali, utilizzare le dimensioni ottimali.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-153">For best results, use the optimal size.</span></span>|
|<span data-ttu-id="5e5fc-154">Testo accanto al nome e all'indirizzo di posta elettronica del mittente</span><span class="sxs-lookup"><span data-stu-id="5e5fc-154">Text next to the sender's name and email address</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -IntroductionText "<String up to 1024 characters>"` <br/> <span data-ttu-id="5e5fc-155">**Esempio:**</span><span class="sxs-lookup"><span data-stu-id="5e5fc-155">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -IntroductionText "has sent you a secure message."`|
|<span data-ttu-id="5e5fc-156">Testo visualizzato sul pulsante "Leggi messaggio"</span><span class="sxs-lookup"><span data-stu-id="5e5fc-156">Text that appears on the "Read Message" button</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -ReadButtonText "<String up to 1024 characters>"` <br/> <span data-ttu-id="5e5fc-157">**Esempio:**</span><span class="sxs-lookup"><span data-stu-id="5e5fc-157">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -ReadButtonText "Read Secure Message."`|
|<span data-ttu-id="5e5fc-158">Testo visualizzato sotto il pulsante "Leggi messaggio"</span><span class="sxs-lookup"><span data-stu-id="5e5fc-158">Text that appears below the "Read Message" button</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -EmailText "<String up to 1024 characters>"` <br/> <span data-ttu-id="5e5fc-159">**Esempio:**</span><span class="sxs-lookup"><span data-stu-id="5e5fc-159">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText "Encrypted message from ContosoPharma secure messaging system."`|
|<span data-ttu-id="5e5fc-160">URL del collegamento all'informativa sulla privacy</span><span class="sxs-lookup"><span data-stu-id="5e5fc-160">URL for the Privacy Statement link</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PrivacyStatementURL "<URL>"` <br/> <span data-ttu-id="5e5fc-161">**Esempio:**</span><span class="sxs-lookup"><span data-stu-id="5e5fc-161">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -PrivacyStatementURL "https://contoso.com/privacystatement.html"`|
|<span data-ttu-id="5e5fc-162">dichiarazione di non responsabilità nella posta elettronica che contiene il messaggio crittografato</span><span class="sxs-lookup"><span data-stu-id="5e5fc-162">Disclaimer statement in the email that contains the encrypted message</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -DisclaimerText "<Disclaimer statement. String of up to 1024 characters.>"` <br/> <span data-ttu-id="5e5fc-163">**Esempio:**</span><span class="sxs-lookup"><span data-stu-id="5e5fc-163">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -DisclaimerText "This message is confidential for the use of the addressee only."`|
|<span data-ttu-id="5e5fc-164">testo visualizzato nella parte superiore del portale di visualizzazione del messaggio crittografato</span><span class="sxs-lookup"><span data-stu-id="5e5fc-164">Text that appears at the top of the encrypted mail viewing portal</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PortalText "<Text for your portal. String of up to 128 characters.>"` <br/> <span data-ttu-id="5e5fc-165">**Esempio:**</span><span class="sxs-lookup"><span data-stu-id="5e5fc-165">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText "ContosoPharma secure email portal."`|
|<span data-ttu-id="5e5fc-166">Per abilitare o disabilitare l'autenticazione con un codice Pass una tantum per questo modello personalizzato</span><span class="sxs-lookup"><span data-stu-id="5e5fc-166">To enable or disable authentication with a one-time pass code for this custom template</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -OTPEnabled <$true|$false>` <br/> <span data-ttu-id="5e5fc-167">**Esempi:**</span><span class="sxs-lookup"><span data-stu-id="5e5fc-167">**Examples:**</span></span> <br/><span data-ttu-id="5e5fc-168">Per abilitare i codici di accesso una tantum per questo modello personalizzato</span><span class="sxs-lookup"><span data-stu-id="5e5fc-168">To enable one-time passcodes for this custom template</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $true` <br/> <span data-ttu-id="5e5fc-169">Per disabilitare i codici di accesso una tantum per questo modello personalizzato</span><span class="sxs-lookup"><span data-stu-id="5e5fc-169">To disable one-time passcodes for this custom template</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -OTPEnabled $false`|
|<span data-ttu-id="5e5fc-170">Per abilitare o disabilitare l'autenticazione con identità Microsoft, Google o Yahoo per questo modello personalizzato</span><span class="sxs-lookup"><span data-stu-id="5e5fc-170">To enable or disable authentication with Microsoft, Google, or Yahoo identities for this custom template</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -SocialIdSignIn <$true|$false>` <br/> <span data-ttu-id="5e5fc-171">**Esempi:**</span><span class="sxs-lookup"><span data-stu-id="5e5fc-171">**Examples:**</span></span> <br/><span data-ttu-id="5e5fc-172">Per abilitare gli ID di social networking per questo modello personalizzato</span><span class="sxs-lookup"><span data-stu-id="5e5fc-172">To enable social IDs for this custom template</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $true` <br/> <span data-ttu-id="5e5fc-173">Per disabilitare gli ID di social networking per questo modello personalizzato</span><span class="sxs-lookup"><span data-stu-id="5e5fc-173">To disable social IDs for this custom template</span></span> <br/>  `Set-OMEConfiguration -Identity "Branding Template 1" -SocialIdSignIn $false`|

## <a name="create-an-ome-branding-template-advanced-message-encryption"></a><span data-ttu-id="5e5fc-174">Creare un modello di branding OME (Advanced Message Encryption)</span><span class="sxs-lookup"><span data-stu-id="5e5fc-174">Create an OME branding template (Advanced Message Encryption)</span></span>

<span data-ttu-id="5e5fc-175">Se si dispone della crittografia dei messaggi avanzata di Office 365, è possibile creare modelli di personalizzazione personalizzati per l'organizzazione utilizzando il cmdlet [New-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/new-omeconfiguration) .</span><span class="sxs-lookup"><span data-stu-id="5e5fc-175">If you have Office 365 Advanced Message Encryption, you can create custom branding templates for your organization by using the [New-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/new-omeconfiguration) cmdlet.</span></span> <span data-ttu-id="5e5fc-176">Dopo aver creato il modello, è possibile modificare il modello utilizzando il cmdlet Set-OMEConfiguration come descritto in [Modify an ome branding template](#modify-an-ome-branding-template).</span><span class="sxs-lookup"><span data-stu-id="5e5fc-176">Once you've created the template, you modify the template by using the Set-OMEConfiguration cmdlet as described in [Modify an OME branding template](#modify-an-ome-branding-template).</span></span> <span data-ttu-id="5e5fc-177">È possibile creare più modelli.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-177">You can create multiple templates.</span></span>

<span data-ttu-id="5e5fc-178">Per creare un nuovo modello di personalizzazione personalizzato:</span><span class="sxs-lookup"><span data-stu-id="5e5fc-178">To create a new custom branding template:</span></span>

1. <span data-ttu-id="5e5fc-179">Utilizzo di un account aziendale o dell'Istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione, avviare una sessione di Windows PowerShell e connettersi a Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-179">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="5e5fc-180">Per istruzioni, vedere [Connettersi a PowerShell di Exchange Online](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="5e5fc-180">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="5e5fc-181">Utilizzare il cmdlet [New-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/new-omeconfiguration) per creare un nuovo modello.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-181">Use the [New-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/new-omeconfiguration) cmdlet to create a new template.</span></span>

   ```powershell
   New-OMEConfiguration -Identity "<OMEConfigurationName>"
   ```

   <span data-ttu-id="5e5fc-182">Ad esempio,</span><span class="sxs-lookup"><span data-stu-id="5e5fc-182">For example,</span></span>

   ```powershell
   New-OMEConfiguration -Identity "Custom branding template"
   ```

## <a name="return-the-default-branding-template-to-its-original-values"></a><span data-ttu-id="5e5fc-183">Ripristinare i valori originali del modello di personalizzazione predefinito</span><span class="sxs-lookup"><span data-stu-id="5e5fc-183">Return the default branding template to its original values</span></span>

<span data-ttu-id="5e5fc-184">Per rimuovere tutte le modifiche dal modello predefinito, incluse le personalizzazioni del marchio e così via, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="5e5fc-184">To remove all modifications from the default template, including brand customizations, and so on, complete these steps:</span></span>
  
1. <span data-ttu-id="5e5fc-185">Utilizzo di un account aziendale o dell'Istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione, avviare una sessione di Windows PowerShell e connettersi a Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-185">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="5e5fc-186">Per istruzioni, vedere [Connettersi a PowerShell di Exchange Online](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="5e5fc-186">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="5e5fc-187">Utilizzare il cmdlet **set-OMEConfiguration** come descritto in [set-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/Set-OMEConfiguration).</span><span class="sxs-lookup"><span data-stu-id="5e5fc-187">Use the **Set-OMEConfiguration** cmdlet as described in [Set-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/Set-OMEConfiguration).</span></span> <span data-ttu-id="5e5fc-188">Per rimuovere le personalizzazioni personalizzate dell'organizzazione dai valori DisclaimerText, EmailText e PortalText, impostare il valore su una stringa vuota `""` .</span><span class="sxs-lookup"><span data-stu-id="5e5fc-188">To remove your organization's branded customizations from the DisclaimerText, EmailText, and PortalText values, set the value to an empty string, `""`.</span></span> <span data-ttu-id="5e5fc-189">Per tutti i valori di immagine, ad esempio logo, impostare il valore su  `"$null"` .</span><span class="sxs-lookup"><span data-stu-id="5e5fc-189">For all image values, such as Logo, set the value to  `"$null"`.</span></span>

   <span data-ttu-id="5e5fc-190">Nella tabella seguente vengono descritte le impostazioni predefinite dell'opzione di personalizzazione della crittografia.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-190">The following table describes the encryption customization option defaults.</span></span>

   <span data-ttu-id="5e5fc-191">**Per ripristinare il testo e l'immagine predefiniti per questa funzionalità dell'esperienza di crittografia**</span><span class="sxs-lookup"><span data-stu-id="5e5fc-191">**To revert this feature of the encryption experience back to the default text and image**</span></span>|<span data-ttu-id="5e5fc-192">**Utilizzare questi comandi**</span><span class="sxs-lookup"><span data-stu-id="5e5fc-192">**Use these commands**</span></span>|
   |:-----|:-----|
   |<span data-ttu-id="5e5fc-193">Testo predefinito fornito con i messaggi di posta elettronica crittografati</span><span class="sxs-lookup"><span data-stu-id="5e5fc-193">Default text that comes with encrypted email messages</span></span>  <br/> <span data-ttu-id="5e5fc-194">Il testo predefinito viene visualizzato sopra le istruzioni per la visualizzazione di messaggi crittografati</span><span class="sxs-lookup"><span data-stu-id="5e5fc-194">The default text appears above the instructions for viewing encrypted messages</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -EmailText "<empty string>"` <br/> <span data-ttu-id="5e5fc-195">**Esempio:**</span><span class="sxs-lookup"><span data-stu-id="5e5fc-195">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -EmailText ""`|
   |<span data-ttu-id="5e5fc-196">dichiarazione di non responsabilità nella posta elettronica che contiene il messaggio crittografato</span><span class="sxs-lookup"><span data-stu-id="5e5fc-196">Disclaimer statement in the email that contains the encrypted message</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" DisclaimerText "<empty string>"` <br/> <span data-ttu-id="5e5fc-197">**Esempio:**</span><span class="sxs-lookup"><span data-stu-id="5e5fc-197">**Example:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -DisclaimerText ""`|
   |<span data-ttu-id="5e5fc-198">testo visualizzato nella parte superiore del portale di visualizzazione del messaggio crittografato</span><span class="sxs-lookup"><span data-stu-id="5e5fc-198">Text that appears at the top of the encrypted mail viewing portal</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -PortalText "<empty string>"` <br/> <span data-ttu-id="5e5fc-199">**Esempio ripristinando il valore predefinito:**</span><span class="sxs-lookup"><span data-stu-id="5e5fc-199">**Example reverting back to default:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME Configuration" -PortalText ""`|
   |<span data-ttu-id="5e5fc-200">Logo</span><span class="sxs-lookup"><span data-stu-id="5e5fc-200">Logo</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -Image <"$null">` <br/> <span data-ttu-id="5e5fc-201">**Esempio ripristinando il valore predefinito:**</span><span class="sxs-lookup"><span data-stu-id="5e5fc-201">**Example reverting back to default:**</span></span> <br/>  `Set-OMEConfiguration -Identity "OME configuration" -Image $null`|
   |<span data-ttu-id="5e5fc-202">Colore di sfondo</span><span class="sxs-lookup"><span data-stu-id="5e5fc-202">Background color</span></span>|`Set-OMEConfiguration -Identity "<OMEConfigurationName>" -BackgroundColor "$null">` <br/> <span data-ttu-id="5e5fc-203">**Esempio ripristinando il valore predefinito:**</span><span class="sxs-lookup"><span data-stu-id="5e5fc-203">**Example reverting back to default:**</span></span> <br/> `Set-OMEConfiguration -Identity "OME configuration" -BackgroundColor $null`|
   |

## <a name="remove-a-custom-branding-template-advanced-message-encryption"></a><span data-ttu-id="5e5fc-204">Rimuovere un modello di personalizzazione personalizzato (Advanced Message Encryption)</span><span class="sxs-lookup"><span data-stu-id="5e5fc-204">Remove a custom branding template (Advanced Message Encryption)</span></span>

<span data-ttu-id="5e5fc-205">È possibile rimuovere o eliminare solo i modelli di personalizzazione che sono stati apportati.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-205">You can only remove or delete branding templates that you've made.</span></span> <span data-ttu-id="5e5fc-206">Non è possibile rimuovere il modello di personalizzazione predefinito.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-206">You can't remove the default branding template.</span></span>

<span data-ttu-id="5e5fc-207">Per rimuovere un modello di personalizzazione personalizzato:</span><span class="sxs-lookup"><span data-stu-id="5e5fc-207">To remove a custom branding template:</span></span>
  
1. <span data-ttu-id="5e5fc-208">Utilizzo di un account aziendale o dell'Istituto di istruzione con autorizzazioni di amministratore globale nell'organizzazione, avviare una sessione di Windows PowerShell e connettersi a Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-208">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="5e5fc-209">Per istruzioni, vedere [Connettersi a PowerShell di Exchange Online](https://aka.ms/exopowershell).</span><span class="sxs-lookup"><span data-stu-id="5e5fc-209">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span>

2. <span data-ttu-id="5e5fc-210">Utilizzare il cmdlet **Remove-OMEConfiguration** come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="5e5fc-210">Use the **Remove-OMEConfiguration** cmdlet as follows:</span></span>

   ```powershell
   Remove-OMEConfiguration -Identity ""<OMEConfigurationName>"
   ```

   <span data-ttu-id="5e5fc-211">Ad esempio,</span><span class="sxs-lookup"><span data-stu-id="5e5fc-211">For example,</span></span>

   ```powershell
   Remove-OMEConfiguration -Identity "Branding template 1"
   ```

   <span data-ttu-id="5e5fc-212">Per ulteriori informazioni, vedere [Remove-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/remove-omeconfiguration).</span><span class="sxs-lookup"><span data-stu-id="5e5fc-212">For more information, see [Remove-OMEConfiguration](https://docs.microsoft.com/powershell/module/exchange/remove-omeconfiguration).</span></span>

## <a name="create-an-exchange-mail-flow-rule-that-applies-your-custom-branding-to-encrypted-emails"></a><span data-ttu-id="5e5fc-213">Creare una regola del flusso di posta di Exchange che applica il branding personalizzato ai messaggi di posta elettronica crittografati</span><span class="sxs-lookup"><span data-stu-id="5e5fc-213">Create an Exchange mail flow rule that applies your custom branding to encrypted emails</span></span>

<span data-ttu-id="5e5fc-214">Dopo aver modificato il modello predefinito o creato nuovi modelli di branding, è possibile creare le regole del flusso di posta di Exchange per applicare il marchio personalizzato in base a determinate condizioni.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-214">After you've either modified the default template or created new branding templates, you can create Exchange mail flow rules to apply your custom branding based on certain conditions.</span></span> <span data-ttu-id="5e5fc-215">Una regola di questo tipo applicherà il marchio personalizzato negli scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="5e5fc-215">Such a rule will apply custom branding in the following scenarios:</span></span>

- <span data-ttu-id="5e5fc-216">Se il messaggio di posta elettronica è stato crittografato manualmente dall'utente finale utilizzando Outlook o Outlook sul Web, in precedenza Outlook Web App</span><span class="sxs-lookup"><span data-stu-id="5e5fc-216">If the email was manually encrypted by the end user using Outlook or Outlook on the web, formerly Outlook Web App</span></span>

- <span data-ttu-id="5e5fc-217">Se il messaggio di posta elettronica è stato crittografato automaticamente da una regola del flusso di posta di Exchange o da un criterio di prevenzione</span><span class="sxs-lookup"><span data-stu-id="5e5fc-217">If the email was automatically encrypted by an Exchange mail flow rule or Data Loss Prevention policy</span></span>

<span data-ttu-id="5e5fc-218">Per informazioni su come creare una regola del flusso di posta di Exchange che applica la crittografia, vedere [definire le regole del flusso di posta per crittografare i messaggi di posta elettronica in Office 365](define-mail-flow-rules-to-encrypt-email.md).</span><span class="sxs-lookup"><span data-stu-id="5e5fc-218">For information on how to create an Exchange mail flow rule that applies encryption, see [Define mail flow rules to encrypt email messages in Office 365](define-mail-flow-rules-to-encrypt-email.md).</span></span>

1. <span data-ttu-id="5e5fc-219">In un Web browser, utilizzando un account aziendale o dell'Istituto di istruzione a cui sono state concesse le autorizzazioni di amministratore globale, [accedere a Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).</span><span class="sxs-lookup"><span data-stu-id="5e5fc-219">In a web browser, using a work or school account that has been granted global administrator permissions, [sign in to Office 365](https://support.office.com/article/b9582171-fd1f-4284-9846-bdd72bb28426#ID0EAABAAA=Web_browser).</span></span>

2. <span data-ttu-id="5e5fc-220">Scegliere il riquadro **amministratore** .</span><span class="sxs-lookup"><span data-stu-id="5e5fc-220">Choose the **Admin** tile.</span></span>

3. <span data-ttu-id="5e5fc-221">Nell'interfaccia di amministrazione di Microsoft 365 fare clic su interfaccia di **Amministrazione** di \> **Exchange**.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-221">In the Microsoft 365 admin center, choose **Admin centers** \> **Exchange**.</span></span>

4. <span data-ttu-id="5e5fc-222">Nell'interfaccia di amministrazione di Exchange, andare a regole del **flusso di posta** \>  e selezionare **nuova** nuova ![ icona ](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **creare una nuova regola**.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-222">In the EAC, go to **Mail flow** \> **Rules** and select **New** ![New icon](../media/457cd93f-22c2-4571-9f83-1b129bcfb58e.gif) \> **Create a new rule**.</span></span> <span data-ttu-id="5e5fc-223">Per ulteriori informazioni sull'utilizzo di EAC, vedere interfaccia [di amministrazione di Exchange in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).</span><span class="sxs-lookup"><span data-stu-id="5e5fc-223">For more information about using the EAC, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).</span></span>

5. <span data-ttu-id="5e5fc-224">In **nome** Digitare un nome per la regola, ad esempio branding per il reparto vendite.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-224">In **Name**, type a name for the rule, such as Branding for sales department.</span></span>

6. <span data-ttu-id="5e5fc-225">In **applica questa regola se**, selezionare la condizione in cui **il mittente si trova all'interno dell'organizzazione** e altre condizioni desiderate nell'elenco delle condizioni disponibili.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-225">In **Apply this rule if**, select the condition **The sender is located inside the organization** and other conditions you want from the list of available conditions.</span></span> <span data-ttu-id="5e5fc-226">Ad esempio, potrebbe essere necessario applicare un modello di branding specifico a:</span><span class="sxs-lookup"><span data-stu-id="5e5fc-226">For example, you might want to apply a particular branding template to:</span></span>

   - <span data-ttu-id="5e5fc-227">Tutti i messaggi di posta elettronica crittografati inviati dai membri del reparto Finanze</span><span class="sxs-lookup"><span data-stu-id="5e5fc-227">All encrypted emails sent from members of the finance department</span></span>
   - <span data-ttu-id="5e5fc-228">Messaggi di posta elettronica crittografati inviati con una determinata parola chiave, ad esempio "esterno" o "partner"</span><span class="sxs-lookup"><span data-stu-id="5e5fc-228">Encrypted emails sent with a certain keyword such as "External" or "Partner"</span></span>
   - <span data-ttu-id="5e5fc-229">Messaggi di posta elettronica crittografati inviati a un dominio specifico</span><span class="sxs-lookup"><span data-stu-id="5e5fc-229">Encrypted emails sent to a particular domain</span></span>

7. <span data-ttu-id="5e5fc-230">Da **procedere come segue**, selezionare **modifica la sicurezza dei** messaggi \> **applicare il marchio personalizzato ai messaggi ome**.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-230">From **Do the following**, select **Modify the message security** \> **Apply custom branding to OME messages**.</span></span> <span data-ttu-id="5e5fc-231">Successivamente, dal menu a discesa, selezionare un modello di personalizzazione.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-231">Next, from the drop-down, select a branding template.</span></span>

8. <span data-ttu-id="5e5fc-232">Optional È possibile configurare la regola del flusso di posta per applicare la crittografia e il marchio personalizzato.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-232">(Optional) You can configure the mail flow rule to apply encryption and custom branding.</span></span> <span data-ttu-id="5e5fc-233">Da **procedere come segue**, selezionare **modifica la sicurezza dei messaggi**, quindi fare clic su **applica la crittografia dei messaggi di Office 365 e Rights Protection**.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-233">From **Do the following**, select **Modify the message security**, and then choose **Apply Office 365 Message Encryption and rights protection**.</span></span> <span data-ttu-id="5e5fc-234">Selezionare un modello RMS nell'elenco, scegliere **Salva** e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-234">Select an RMS template from the list, choose **Save**, and then choose **OK**.</span></span>
  
   <span data-ttu-id="5e5fc-235">L'elenco dei modelli include modelli e opzioni predefiniti e tutti i modelli personalizzati creati.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-235">The list of templates includes default templates and options and any custom templates you create.</span></span> <span data-ttu-id="5e5fc-236">Se l'elenco è vuoto, verificare di aver configurato la crittografia dei messaggi di Office 365 con le nuove funzionalità.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-236">If the list is empty, ensure that you have set up Office 365 Message Encryption with the new capabilities.</span></span> <span data-ttu-id="5e5fc-237">Per istruzioni, vedere [configurare le nuove funzionalità di crittografia dei messaggi di Office 365](set-up-new-message-encryption-capabilities.md).</span><span class="sxs-lookup"><span data-stu-id="5e5fc-237">For instructions, see [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md).</span></span> <span data-ttu-id="5e5fc-238">Per informazioni sui modelli predefiniti, vedere [Configuring and Managing templates for Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates).</span><span class="sxs-lookup"><span data-stu-id="5e5fc-238">For information about the default templates, see [Configuring and managing templates for Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates).</span></span> <span data-ttu-id="5e5fc-239">Per informazioni sull'opzione non **inoltrare** , vedere non [inoltrare l'opzione per i messaggi di posta elettronica](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails).</span><span class="sxs-lookup"><span data-stu-id="5e5fc-239">For information about the **Do Not Forward** option, see [Do Not Forward option for emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails).</span></span> <span data-ttu-id="5e5fc-240">Per informazioni sull'opzione **solo crittografia** , vedere [opzione di crittografia solo per i messaggi di posta elettronica](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).</span><span class="sxs-lookup"><span data-stu-id="5e5fc-240">For information about the **encrypt only** option, see [Encrypt Only option for emails](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails).</span></span>

   <span data-ttu-id="5e5fc-241">Fare clic su **Aggiungi azione** se si desidera specificare un'altra azione.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-241">Choose **add action** if you want to specify another action.</span></span>

## <a name="background-color-reference"></a><span data-ttu-id="5e5fc-242">Riferimento al colore di sfondo</span><span class="sxs-lookup"><span data-stu-id="5e5fc-242">Background color reference</span></span>

<span data-ttu-id="5e5fc-243">I nomi di colore che è possibile utilizzare per il colore di sfondo sono limitati.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-243">The color names that you can use for the background color are limited.</span></span> <span data-ttu-id="5e5fc-244">Invece del nome di un colore, è possibile utilizzare un valore di codice esadecimale (#RRGGBB).</span><span class="sxs-lookup"><span data-stu-id="5e5fc-244">Instead of a color name, you can use a hex code value (#RRGGBB).</span></span> <span data-ttu-id="5e5fc-245">È possibile utilizzare un valore di codice esadecimale corrispondente a un nome di colore oppure è possibile utilizzare un valore di codice esadecimale personalizzato.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-245">You can use a hex code value that corresponds to a color name, or you can use a custom hex code value.</span></span> <span data-ttu-id="5e5fc-246">Tenere presente che il valore del codice esadecimale viene racchiuso tra virgolette (ad esempio, `"#f0f8ff"` ).</span><span class="sxs-lookup"><span data-stu-id="5e5fc-246">Be sure to enclose the hex code value in quotation marks (for example, `"#f0f8ff"`).</span></span>

<span data-ttu-id="5e5fc-247">Nella tabella seguente sono descritti i nomi dei colori di sfondo disponibili e i valori del codice esadecimale corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="5e5fc-247">The available background color names and their corresponding hex code values are described in the following table.</span></span>

|<span data-ttu-id="5e5fc-248">**Nome colore**</span><span class="sxs-lookup"><span data-stu-id="5e5fc-248">**Color name**</span></span>|<span data-ttu-id="5e5fc-249">**Codice colore**</span><span class="sxs-lookup"><span data-stu-id="5e5fc-249">**Color code**</span></span>|
|---|---|
|`aliceblue`|<span data-ttu-id="5e5fc-250">#f0f8ff</span><span class="sxs-lookup"><span data-stu-id="5e5fc-250">#f0f8ff</span></span>|
|`antiquewhite`|<span data-ttu-id="5e5fc-251">#faebd7</span><span class="sxs-lookup"><span data-stu-id="5e5fc-251">#faebd7</span></span>|
|`aqua`|<span data-ttu-id="5e5fc-252">#00ffff</span><span class="sxs-lookup"><span data-stu-id="5e5fc-252">#00ffff</span></span>|
|`aquamarine`|<span data-ttu-id="5e5fc-253">#7fffd4</span><span class="sxs-lookup"><span data-stu-id="5e5fc-253">#7fffd4</span></span>|
|`azure`|<span data-ttu-id="5e5fc-254">#f0ffff</span><span class="sxs-lookup"><span data-stu-id="5e5fc-254">#f0ffff</span></span>|
|`beige`|<span data-ttu-id="5e5fc-255">#f5f5dc</span><span class="sxs-lookup"><span data-stu-id="5e5fc-255">#f5f5dc</span></span>|
|`bisque`|<span data-ttu-id="5e5fc-256">#ffe4c4</span><span class="sxs-lookup"><span data-stu-id="5e5fc-256">#ffe4c4</span></span>|
|`black`|<span data-ttu-id="5e5fc-257">#000000</span><span class="sxs-lookup"><span data-stu-id="5e5fc-257">#000000</span></span>|
|`blanchedalmond`|<span data-ttu-id="5e5fc-258">#ffebcd</span><span class="sxs-lookup"><span data-stu-id="5e5fc-258">#ffebcd</span></span>|
|`blue`|<span data-ttu-id="5e5fc-259">#0000ff</span><span class="sxs-lookup"><span data-stu-id="5e5fc-259">#0000ff</span></span>|
|`blueviolet`|<span data-ttu-id="5e5fc-260">#8a2be2</span><span class="sxs-lookup"><span data-stu-id="5e5fc-260">#8a2be2</span></span>|
|`brown`|<span data-ttu-id="5e5fc-261">#a52a2a</span><span class="sxs-lookup"><span data-stu-id="5e5fc-261">#a52a2a</span></span>|
|`burlywood`|<span data-ttu-id="5e5fc-262">#deb887</span><span class="sxs-lookup"><span data-stu-id="5e5fc-262">#deb887</span></span>|
|`cadetblue`|<span data-ttu-id="5e5fc-263">#5f9ea0</span><span class="sxs-lookup"><span data-stu-id="5e5fc-263">#5f9ea0</span></span>|
|`chartreuse`|<span data-ttu-id="5e5fc-264">#7fff00</span><span class="sxs-lookup"><span data-stu-id="5e5fc-264">#7fff00</span></span>|
|`chocolate`|<span data-ttu-id="5e5fc-265">#d2691e</span><span class="sxs-lookup"><span data-stu-id="5e5fc-265">#d2691e</span></span>|
|`coral`|<span data-ttu-id="5e5fc-266">#ff7f50</span><span class="sxs-lookup"><span data-stu-id="5e5fc-266">#ff7f50</span></span>|
|`cornflowerblue`|<span data-ttu-id="5e5fc-267">#6495ed</span><span class="sxs-lookup"><span data-stu-id="5e5fc-267">#6495ed</span></span>|
|`cornsilk`|<span data-ttu-id="5e5fc-268">#fff8dc</span><span class="sxs-lookup"><span data-stu-id="5e5fc-268">#fff8dc</span></span>|
|`crimson`|<span data-ttu-id="5e5fc-269">#dc143c</span><span class="sxs-lookup"><span data-stu-id="5e5fc-269">#dc143c</span></span>|
|`cyan`|<span data-ttu-id="5e5fc-270">#00ffff</span><span class="sxs-lookup"><span data-stu-id="5e5fc-270">#00ffff</span></span>|
|`darkblue`|<span data-ttu-id="5e5fc-271">#00008b</span><span class="sxs-lookup"><span data-stu-id="5e5fc-271">#00008b</span></span>|
|`darkcyan`|<span data-ttu-id="5e5fc-272">#008b8b</span><span class="sxs-lookup"><span data-stu-id="5e5fc-272">#008b8b</span></span>|
|`darkgoldenrod`|<span data-ttu-id="5e5fc-273">#b8860b</span><span class="sxs-lookup"><span data-stu-id="5e5fc-273">#b8860b</span></span>|
|`darkgray`|<span data-ttu-id="5e5fc-274">#a9a9a9</span><span class="sxs-lookup"><span data-stu-id="5e5fc-274">#a9a9a9</span></span>|
|`darkgreen`|<span data-ttu-id="5e5fc-275">#006400</span><span class="sxs-lookup"><span data-stu-id="5e5fc-275">#006400</span></span>|
|`darkkhaki`|<span data-ttu-id="5e5fc-276">#bdb76b</span><span class="sxs-lookup"><span data-stu-id="5e5fc-276">#bdb76b</span></span>|
|`darkmagenta`|<span data-ttu-id="5e5fc-277">#8b008b</span><span class="sxs-lookup"><span data-stu-id="5e5fc-277">#8b008b</span></span>|
|`darkolivegreen`|<span data-ttu-id="5e5fc-278">#556b2f</span><span class="sxs-lookup"><span data-stu-id="5e5fc-278">#556b2f</span></span>|
|`darkorange`|<span data-ttu-id="5e5fc-279">#ff8c00</span><span class="sxs-lookup"><span data-stu-id="5e5fc-279">#ff8c00</span></span>|
|`darkorchid`|<span data-ttu-id="5e5fc-280">#9932cc</span><span class="sxs-lookup"><span data-stu-id="5e5fc-280">#9932cc</span></span>|
|`darkred`|<span data-ttu-id="5e5fc-281">#8b0000</span><span class="sxs-lookup"><span data-stu-id="5e5fc-281">#8b0000</span></span>|
|`darksalmon`|<span data-ttu-id="5e5fc-282">#e9967a</span><span class="sxs-lookup"><span data-stu-id="5e5fc-282">#e9967a</span></span>|
|`darkseagreen`|<span data-ttu-id="5e5fc-283">#8fbc8f</span><span class="sxs-lookup"><span data-stu-id="5e5fc-283">#8fbc8f</span></span>|
|`darkslateblue`|<span data-ttu-id="5e5fc-284">#483d8b</span><span class="sxs-lookup"><span data-stu-id="5e5fc-284">#483d8b</span></span>|
|`darkslategray`|<span data-ttu-id="5e5fc-285">#2f4f4f</span><span class="sxs-lookup"><span data-stu-id="5e5fc-285">#2f4f4f</span></span>|
|`darkturquoise`|<span data-ttu-id="5e5fc-286">#00ced1</span><span class="sxs-lookup"><span data-stu-id="5e5fc-286">#00ced1</span></span>|
|`darkviolet`|<span data-ttu-id="5e5fc-287">#9400d3</span><span class="sxs-lookup"><span data-stu-id="5e5fc-287">#9400d3</span></span>|
|`deeppink`|<span data-ttu-id="5e5fc-288">#ff1493</span><span class="sxs-lookup"><span data-stu-id="5e5fc-288">#ff1493</span></span>|
|`deepskyblue`|<span data-ttu-id="5e5fc-289">#00bfff</span><span class="sxs-lookup"><span data-stu-id="5e5fc-289">#00bfff</span></span>|
|`dimgray`|<span data-ttu-id="5e5fc-290">#696969</span><span class="sxs-lookup"><span data-stu-id="5e5fc-290">#696969</span></span>|
|`dodgerblue`|<span data-ttu-id="5e5fc-291">#1e90ff</span><span class="sxs-lookup"><span data-stu-id="5e5fc-291">#1e90ff</span></span>|
|`firebrick`|<span data-ttu-id="5e5fc-292">#b22222</span><span class="sxs-lookup"><span data-stu-id="5e5fc-292">#b22222</span></span>|
|`floralwhite`|<span data-ttu-id="5e5fc-293">#fffaf0</span><span class="sxs-lookup"><span data-stu-id="5e5fc-293">#fffaf0</span></span>|
|`forestgreen`|<span data-ttu-id="5e5fc-294">#228b22</span><span class="sxs-lookup"><span data-stu-id="5e5fc-294">#228b22</span></span>|
|`fuchsia`|<span data-ttu-id="5e5fc-295">#ff00ff</span><span class="sxs-lookup"><span data-stu-id="5e5fc-295">#ff00ff</span></span>|
|`gainsboro`|<span data-ttu-id="5e5fc-296">#dcdcdc</span><span class="sxs-lookup"><span data-stu-id="5e5fc-296">#dcdcdc</span></span>|
|`ghostwhite`|<span data-ttu-id="5e5fc-297">#f8f8ff</span><span class="sxs-lookup"><span data-stu-id="5e5fc-297">#f8f8ff</span></span>|
|`gold`|<span data-ttu-id="5e5fc-298">#ffd700</span><span class="sxs-lookup"><span data-stu-id="5e5fc-298">#ffd700</span></span>|
|`goldenrod`|<span data-ttu-id="5e5fc-299">#daa520</span><span class="sxs-lookup"><span data-stu-id="5e5fc-299">#daa520</span></span>|
|`gray`|<span data-ttu-id="5e5fc-300">#808080</span><span class="sxs-lookup"><span data-stu-id="5e5fc-300">#808080</span></span>|
|`green`|<span data-ttu-id="5e5fc-301">#008000</span><span class="sxs-lookup"><span data-stu-id="5e5fc-301">#008000</span></span>|
|`greenyellow`|<span data-ttu-id="5e5fc-302">#adff2f</span><span class="sxs-lookup"><span data-stu-id="5e5fc-302">#adff2f</span></span>|
|`honeydew`|<span data-ttu-id="5e5fc-303">#f0fff0</span><span class="sxs-lookup"><span data-stu-id="5e5fc-303">#f0fff0</span></span>|
|`hotpink`|<span data-ttu-id="5e5fc-304">#ff69b4</span><span class="sxs-lookup"><span data-stu-id="5e5fc-304">#ff69b4</span></span>|
|`indianred`|<span data-ttu-id="5e5fc-305">#cd5c5c</span><span class="sxs-lookup"><span data-stu-id="5e5fc-305">#cd5c5c</span></span>|
|`indigo`|<span data-ttu-id="5e5fc-306">#4b0082</span><span class="sxs-lookup"><span data-stu-id="5e5fc-306">#4b0082</span></span>|
|`ivory`|<span data-ttu-id="5e5fc-307">#fffff0</span><span class="sxs-lookup"><span data-stu-id="5e5fc-307">#fffff0</span></span>|
|`khaki`|<span data-ttu-id="5e5fc-308">#f0e68c</span><span class="sxs-lookup"><span data-stu-id="5e5fc-308">#f0e68c</span></span>|
|`lavender`|<span data-ttu-id="5e5fc-309">#e6e6fa</span><span class="sxs-lookup"><span data-stu-id="5e5fc-309">#e6e6fa</span></span>|
|`lavenderblush`|<span data-ttu-id="5e5fc-310">#fff0f5</span><span class="sxs-lookup"><span data-stu-id="5e5fc-310">#fff0f5</span></span>|
|`lawngreen`|<span data-ttu-id="5e5fc-311">#7cfc00</span><span class="sxs-lookup"><span data-stu-id="5e5fc-311">#7cfc00</span></span>|
|`lemonchiffon`|<span data-ttu-id="5e5fc-312">#fffacd</span><span class="sxs-lookup"><span data-stu-id="5e5fc-312">#fffacd</span></span>|
|`lightblue`|<span data-ttu-id="5e5fc-313">#add8e6</span><span class="sxs-lookup"><span data-stu-id="5e5fc-313">#add8e6</span></span>|
|`lightcoral`|<span data-ttu-id="5e5fc-314">#f08080</span><span class="sxs-lookup"><span data-stu-id="5e5fc-314">#f08080</span></span>|
|`lightcyan`|<span data-ttu-id="5e5fc-315">#e0ffff</span><span class="sxs-lookup"><span data-stu-id="5e5fc-315">#e0ffff</span></span>|
|`lightgoldenrodyellow`|<span data-ttu-id="5e5fc-316">#fafad2</span><span class="sxs-lookup"><span data-stu-id="5e5fc-316">#fafad2</span></span>|
|`lightgray`|<span data-ttu-id="5e5fc-317">#d3d3d3</span><span class="sxs-lookup"><span data-stu-id="5e5fc-317">#d3d3d3</span></span>|
|`lightgrey`|<span data-ttu-id="5e5fc-318">#d3d3d3</span><span class="sxs-lookup"><span data-stu-id="5e5fc-318">#d3d3d3</span></span>|
|`lightgreen`|<span data-ttu-id="5e5fc-319">#90ee90</span><span class="sxs-lookup"><span data-stu-id="5e5fc-319">#90ee90</span></span>|
|`lightpink`|<span data-ttu-id="5e5fc-320">#ffb6c1</span><span class="sxs-lookup"><span data-stu-id="5e5fc-320">#ffb6c1</span></span>|
|`lightsalmon`|<span data-ttu-id="5e5fc-321">#ffa07a</span><span class="sxs-lookup"><span data-stu-id="5e5fc-321">#ffa07a</span></span>|
|`lightseagreen`|<span data-ttu-id="5e5fc-322">#20b2aa</span><span class="sxs-lookup"><span data-stu-id="5e5fc-322">#20b2aa</span></span>|
|`lightskyblue`|<span data-ttu-id="5e5fc-323">#87cefa</span><span class="sxs-lookup"><span data-stu-id="5e5fc-323">#87cefa</span></span>|
|`lightslategray`|<span data-ttu-id="5e5fc-324">#778899</span><span class="sxs-lookup"><span data-stu-id="5e5fc-324">#778899</span></span>|
|`lightsteelblue`|<span data-ttu-id="5e5fc-325">#b0c4de</span><span class="sxs-lookup"><span data-stu-id="5e5fc-325">#b0c4de</span></span>|
|`lightyellow`|<span data-ttu-id="5e5fc-326">#ffffe0</span><span class="sxs-lookup"><span data-stu-id="5e5fc-326">#ffffe0</span></span>|
|`lime`|<span data-ttu-id="5e5fc-327">#00ff00</span><span class="sxs-lookup"><span data-stu-id="5e5fc-327">#00ff00</span></span>|
|`limegreen`|<span data-ttu-id="5e5fc-328">#32cd32</span><span class="sxs-lookup"><span data-stu-id="5e5fc-328">#32cd32</span></span>|
|`linen`|<span data-ttu-id="5e5fc-329">#faf0e6</span><span class="sxs-lookup"><span data-stu-id="5e5fc-329">#faf0e6</span></span>|
|`magenta`|<span data-ttu-id="5e5fc-330">#ff00ff</span><span class="sxs-lookup"><span data-stu-id="5e5fc-330">#ff00ff</span></span>|
|`maroon`|<span data-ttu-id="5e5fc-331">#800000</span><span class="sxs-lookup"><span data-stu-id="5e5fc-331">#800000</span></span>|
|`mediumaquamarine`|<span data-ttu-id="5e5fc-332">#66cdaa</span><span class="sxs-lookup"><span data-stu-id="5e5fc-332">#66cdaa</span></span>|
|`mediumblue`|<span data-ttu-id="5e5fc-333">#0000cd</span><span class="sxs-lookup"><span data-stu-id="5e5fc-333">#0000cd</span></span>|
|`mediumorchid`|<span data-ttu-id="5e5fc-334">#ba55d3</span><span class="sxs-lookup"><span data-stu-id="5e5fc-334">#ba55d3</span></span>|
|`mediumpurple`|<span data-ttu-id="5e5fc-335">#9370db</span><span class="sxs-lookup"><span data-stu-id="5e5fc-335">#9370db</span></span>|
|`mediumseagreen`|<span data-ttu-id="5e5fc-336">#3cb371</span><span class="sxs-lookup"><span data-stu-id="5e5fc-336">#3cb371</span></span>|
|`mediumslateblue`|<span data-ttu-id="5e5fc-337">#7b68ee</span><span class="sxs-lookup"><span data-stu-id="5e5fc-337">#7b68ee</span></span>|
|`mediumspringgreen`|<span data-ttu-id="5e5fc-338">#00fa9a</span><span class="sxs-lookup"><span data-stu-id="5e5fc-338">#00fa9a</span></span>|
|`mediumturquoise`|<span data-ttu-id="5e5fc-339">#48d1cc</span><span class="sxs-lookup"><span data-stu-id="5e5fc-339">#48d1cc</span></span>|
|`mediumvioletred`|<span data-ttu-id="5e5fc-340">#c71585</span><span class="sxs-lookup"><span data-stu-id="5e5fc-340">#c71585</span></span>|
|`midnightblue`|<span data-ttu-id="5e5fc-341">#191970</span><span class="sxs-lookup"><span data-stu-id="5e5fc-341">#191970</span></span>|
|`mintcream`|<span data-ttu-id="5e5fc-342">#f5fffa</span><span class="sxs-lookup"><span data-stu-id="5e5fc-342">#f5fffa</span></span>|
|`mistyrose`|<span data-ttu-id="5e5fc-343">#ffe4e1</span><span class="sxs-lookup"><span data-stu-id="5e5fc-343">#ffe4e1</span></span>|
|`moccasin`|<span data-ttu-id="5e5fc-344">#ffe4b5</span><span class="sxs-lookup"><span data-stu-id="5e5fc-344">#ffe4b5</span></span>|
|`navajowhite`|<span data-ttu-id="5e5fc-345">#ffdead</span><span class="sxs-lookup"><span data-stu-id="5e5fc-345">#ffdead</span></span>|
|`navy`|<span data-ttu-id="5e5fc-346">#000080</span><span class="sxs-lookup"><span data-stu-id="5e5fc-346">#000080</span></span>|
|`oldlace`|<span data-ttu-id="5e5fc-347">#fdf5e6</span><span class="sxs-lookup"><span data-stu-id="5e5fc-347">#fdf5e6</span></span>|
|`olive`|<span data-ttu-id="5e5fc-348">#808000</span><span class="sxs-lookup"><span data-stu-id="5e5fc-348">#808000</span></span>|
|`olivedrab`|<span data-ttu-id="5e5fc-349">#6b8e23</span><span class="sxs-lookup"><span data-stu-id="5e5fc-349">#6b8e23</span></span>|
|`orange`|<span data-ttu-id="5e5fc-350">#ffa500</span><span class="sxs-lookup"><span data-stu-id="5e5fc-350">#ffa500</span></span>|
|`orangered`|<span data-ttu-id="5e5fc-351">#ff4500</span><span class="sxs-lookup"><span data-stu-id="5e5fc-351">#ff4500</span></span>|
|`orchid`|<span data-ttu-id="5e5fc-352">#da70d6</span><span class="sxs-lookup"><span data-stu-id="5e5fc-352">#da70d6</span></span>|
|`palegoldenrod`|<span data-ttu-id="5e5fc-353">#eee8aa</span><span class="sxs-lookup"><span data-stu-id="5e5fc-353">#eee8aa</span></span>|
|`palegreen`|<span data-ttu-id="5e5fc-354">#98fb98</span><span class="sxs-lookup"><span data-stu-id="5e5fc-354">#98fb98</span></span>|
|`paleturquoise`|<span data-ttu-id="5e5fc-355">#afeeee</span><span class="sxs-lookup"><span data-stu-id="5e5fc-355">#afeeee</span></span>|
|`palevioletred`|<span data-ttu-id="5e5fc-356">#db7093</span><span class="sxs-lookup"><span data-stu-id="5e5fc-356">#db7093</span></span>|
|`papayawhip`|<span data-ttu-id="5e5fc-357">#ffefd5</span><span class="sxs-lookup"><span data-stu-id="5e5fc-357">#ffefd5</span></span>|
|`peachpuff`|<span data-ttu-id="5e5fc-358">#ffdab9</span><span class="sxs-lookup"><span data-stu-id="5e5fc-358">#ffdab9</span></span>|
|`peru`|<span data-ttu-id="5e5fc-359">#cd853f</span><span class="sxs-lookup"><span data-stu-id="5e5fc-359">#cd853f</span></span>|
|`pink`|<span data-ttu-id="5e5fc-360">#ffc0cb</span><span class="sxs-lookup"><span data-stu-id="5e5fc-360">#ffc0cb</span></span>|
|`plum`|<span data-ttu-id="5e5fc-361">#dda0dd</span><span class="sxs-lookup"><span data-stu-id="5e5fc-361">#dda0dd</span></span>|
|`powderblue`|<span data-ttu-id="5e5fc-362">#b0e0e6</span><span class="sxs-lookup"><span data-stu-id="5e5fc-362">#b0e0e6</span></span>|
|`purple`|<span data-ttu-id="5e5fc-363">#800080</span><span class="sxs-lookup"><span data-stu-id="5e5fc-363">#800080</span></span>|
|`red`|<span data-ttu-id="5e5fc-364">#ff0000</span><span class="sxs-lookup"><span data-stu-id="5e5fc-364">#ff0000</span></span>|
|`rosybrown`|<span data-ttu-id="5e5fc-365">#bc8f8f</span><span class="sxs-lookup"><span data-stu-id="5e5fc-365">#bc8f8f</span></span>|
|`royalblue`|<span data-ttu-id="5e5fc-366">#4169e1</span><span class="sxs-lookup"><span data-stu-id="5e5fc-366">#4169e1</span></span>|
|`saddlebrown`|<span data-ttu-id="5e5fc-367">#8b4513</span><span class="sxs-lookup"><span data-stu-id="5e5fc-367">#8b4513</span></span>|
|`salmon`|<span data-ttu-id="5e5fc-368">#fa8072</span><span class="sxs-lookup"><span data-stu-id="5e5fc-368">#fa8072</span></span>|
|`sandybrown`|<span data-ttu-id="5e5fc-369">#f4a460</span><span class="sxs-lookup"><span data-stu-id="5e5fc-369">#f4a460</span></span>|
|`seagreen`|<span data-ttu-id="5e5fc-370">#00ff00</span><span class="sxs-lookup"><span data-stu-id="5e5fc-370">#00ff00</span></span>|
|`seashell`|<span data-ttu-id="5e5fc-371">#fff5ee</span><span class="sxs-lookup"><span data-stu-id="5e5fc-371">#fff5ee</span></span>|
|`sienna`|<span data-ttu-id="5e5fc-372">#a0522d</span><span class="sxs-lookup"><span data-stu-id="5e5fc-372">#a0522d</span></span>|
|`silver`|<span data-ttu-id="5e5fc-373">#c0c0c0</span><span class="sxs-lookup"><span data-stu-id="5e5fc-373">#c0c0c0</span></span>|
|`skyblue`|<span data-ttu-id="5e5fc-374">#87ceeb</span><span class="sxs-lookup"><span data-stu-id="5e5fc-374">#87ceeb</span></span>|
|`slateblue`|<span data-ttu-id="5e5fc-375">#6a5acd</span><span class="sxs-lookup"><span data-stu-id="5e5fc-375">#6a5acd</span></span>|
|`slategray`|<span data-ttu-id="5e5fc-376">#708090</span><span class="sxs-lookup"><span data-stu-id="5e5fc-376">#708090</span></span>|
|`snow`|<span data-ttu-id="5e5fc-377">#fffafa</span><span class="sxs-lookup"><span data-stu-id="5e5fc-377">#fffafa</span></span>|
|`springgreen`|<span data-ttu-id="5e5fc-378">#00ff7f</span><span class="sxs-lookup"><span data-stu-id="5e5fc-378">#00ff7f</span></span>|
|`steelblue`|<span data-ttu-id="5e5fc-379">#4682b4</span><span class="sxs-lookup"><span data-stu-id="5e5fc-379">#4682b4</span></span>|
|`tan`|<span data-ttu-id="5e5fc-380">#d2b48c</span><span class="sxs-lookup"><span data-stu-id="5e5fc-380">#d2b48c</span></span>|
|`teal`|<span data-ttu-id="5e5fc-381">#008080</span><span class="sxs-lookup"><span data-stu-id="5e5fc-381">#008080</span></span>|
|`thistle`|<span data-ttu-id="5e5fc-382">#d8bfd8</span><span class="sxs-lookup"><span data-stu-id="5e5fc-382">#d8bfd8</span></span>|
|`tomato`|<span data-ttu-id="5e5fc-383">#ff6347</span><span class="sxs-lookup"><span data-stu-id="5e5fc-383">#ff6347</span></span>|
|`turquoise`|<span data-ttu-id="5e5fc-384">#40e0d0</span><span class="sxs-lookup"><span data-stu-id="5e5fc-384">#40e0d0</span></span>|
|`violet`|<span data-ttu-id="5e5fc-385">#ee82ee</span><span class="sxs-lookup"><span data-stu-id="5e5fc-385">#ee82ee</span></span>|
|`wheat`|<span data-ttu-id="5e5fc-386">#f5deb3</span><span class="sxs-lookup"><span data-stu-id="5e5fc-386">#f5deb3</span></span>|
|`white`|<span data-ttu-id="5e5fc-387">#ffffff</span><span class="sxs-lookup"><span data-stu-id="5e5fc-387">#ffffff</span></span>|
|`whitesmoke`|<span data-ttu-id="5e5fc-388">#f5f5f5</span><span class="sxs-lookup"><span data-stu-id="5e5fc-388">#f5f5f5</span></span>|
|`yellow`|<span data-ttu-id="5e5fc-389">#ffff00</span><span class="sxs-lookup"><span data-stu-id="5e5fc-389">#ffff00</span></span>|
|`yellowgreen`|<span data-ttu-id="5e5fc-390">#9acd32</span><span class="sxs-lookup"><span data-stu-id="5e5fc-390">#9acd32</span></span>|
