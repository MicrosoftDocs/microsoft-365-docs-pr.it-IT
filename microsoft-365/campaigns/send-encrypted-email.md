---
title: Inviare messaggi di posta elettronica crittografati
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.date: 9/20/2018
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-Campaigns
- m365solution-smb
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 496e690b-b75d-4ff5-bf34-cc32905d0364
description: Informazioni su come inviare messaggi di posta elettronica crittografati con Outlook.
ms.openlocfilehash: d17abccd645b4dfdf933906dc90175be51f95c9a
ms.sourcegitcommit: 1b30ac6e05906c8a014b1fed33fc71e1821f6ad2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2021
ms.locfileid: "50044217"
---
# <a name="encrypt-or-label-your-sensitive-email"></a><span data-ttu-id="d9bd8-103">Crittografare o etichettare le comunicazioni di posta elettronica sensibili</span><span class="sxs-lookup"><span data-stu-id="d9bd8-103">Encrypt or label your sensitive email</span></span>

<span data-ttu-id="d9bd8-104">I dati e le informazioni della campagna sono importanti e spesso riservati.</span><span class="sxs-lookup"><span data-stu-id="d9bd8-104">Your data and campaign information is important and often confidential.</span></span> <span data-ttu-id="d9bd8-105">Proteggere queste informazioni riservate utilizzando le etichette di crittografia e riservatezza, in modo che l'utente e i destinatari di posta elettronica trattino le informazioni con la riservatezza necessaria.</span><span class="sxs-lookup"><span data-stu-id="d9bd8-105">Help protect this sensitive information by using encryption and sensitivity labels so you and your email recipients treat the information with the sensitivity it requires.</span></span>

## <a name="best-practices"></a><span data-ttu-id="d9bd8-106">Procedure consigliate</span><span class="sxs-lookup"><span data-stu-id="d9bd8-106">Best practices</span></span>

<span data-ttu-id="d9bd8-107">Prima di inviare messaggi di posta elettronica con informazioni riservate o riservate, è consigliabile attivare:</span><span class="sxs-lookup"><span data-stu-id="d9bd8-107">Before you send email with confidential or sensitive information, consider turning on:</span></span>

- <span data-ttu-id="d9bd8-108">**Crittografia:** È possibile crittografare la posta elettronica per proteggere la privacy delle informazioni nel messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="d9bd8-108">**Encryption:** You can encrypt your email to protect the privacy of the information in the email.</span></span> <span data-ttu-id="d9bd8-109">Quando si crittografa un messaggio di posta elettronica, questo viene convertito da testo normale leggibile in testo crittografato.</span><span class="sxs-lookup"><span data-stu-id="d9bd8-109">When you encrypt an email message, it's converted from readable plain text into scrambled cypher text.</span></span> <span data-ttu-id="d9bd8-110">Solo il destinatario che dispone della chiave privata corrispondente alla chiave pubblica utilizzata per crittografare il messaggio può decifrare il messaggio per la lettura.</span><span class="sxs-lookup"><span data-stu-id="d9bd8-110">Only the recipient who has the private key that matches the public key used to encrypt the message can decipher the message for reading.</span></span> <span data-ttu-id="d9bd8-111">Qualsiasi destinatario senza la chiave privata corrispondente, tuttavia, visualizza testo indecifrabile.</span><span class="sxs-lookup"><span data-stu-id="d9bd8-111">Any recipient without the corresponding private key, however, sees indecipherable text.</span></span> <span data-ttu-id="d9bd8-112">L'amministratore può definire regole per crittografare automaticamente i messaggi che soddisfano determinati criteri.</span><span class="sxs-lookup"><span data-stu-id="d9bd8-112">Your admin can define rules to automatically encrypt messages that meet certain criteria.</span></span> <span data-ttu-id="d9bd8-113">Ad esempio, l'amministratore può creare una regola che crittografa tutti i messaggi inviati all'esterno dell'organizzazione o tutti i messaggi che menzionano parole o frasi specifiche.</span><span class="sxs-lookup"><span data-stu-id="d9bd8-113">For instance, your admin can create a rule that encrypts all messages sent outside your organization or all messages that mention specific words or phrases.</span></span> <span data-ttu-id="d9bd8-114">Tutte le regole di crittografia verranno applicate automaticamente.</span><span class="sxs-lookup"><span data-stu-id="d9bd8-114">Any encryption rules will be applied automatically.</span></span>
- <span data-ttu-id="d9bd8-115">**Etichette di riservatezza:** La campagna può anche configurare etichette di riservatezza che è possibile applicare ai file e ai messaggi di posta elettronica per mantenerli conformi ai criteri di protezione delle informazioni della campagna.</span><span class="sxs-lookup"><span data-stu-id="d9bd8-115">**Sensitivity labels:** Your campaign can also set up sensitivity labels that you can apply to your files and email to keep them compliant with your campaign's information protection policies.</span></span> <span data-ttu-id="d9bd8-116">Quando si imposta un'etichetta, l'etichetta persiste con la posta elettronica, anche quando viene inviata, ad esempio, apparendo come intestazione del messaggio.</span><span class="sxs-lookup"><span data-stu-id="d9bd8-116">When you set a label, the label persists with your email, even when it's sent - for example, by appearing as a header to your message.</span></span>

![Diagramma di un messaggio di posta elettronica con callout per etichette e crittografia](../media/m365-campaign-email-encrypt.png)

## <a name="set-it-up"></a><span data-ttu-id="d9bd8-118">Configurazione</span><span class="sxs-lookup"><span data-stu-id="d9bd8-118">Set it up</span></span>

<span data-ttu-id="d9bd8-119">Se si desidera crittografare un messaggio che non soddisfa una regola predefinita o se l'amministratore non ha configurato alcuna regola, è possibile applicare una serie di regole di crittografia diverse prima di inviare il messaggio.</span><span class="sxs-lookup"><span data-stu-id="d9bd8-119">If you want to encrypt a message that doesn't meet a pre-defined rule or your admin hasn't set up any rules, you can apply a variety of different encryption rules before you send the message.</span></span> <span data-ttu-id="d9bd8-120">Per inviare un messaggio crittografato da Outlook 2013 o 2016 o Outlook 2016 per Mac, selezionare Opzioni **> Autorizzazioni,** quindi selezionare l'opzione di protezione necessaria.</span><span class="sxs-lookup"><span data-stu-id="d9bd8-120">To send an encrypted message from Outlook 2013 or 2016, or Outlook 2016 for Mac, select **Options > Permissions**, then select the protection option you need.</span></span> <span data-ttu-id="d9bd8-121">È inoltre possibile inviare un messaggio crittografato selezionando il **pulsante Proteggi** in Outlook sul Web.</span><span class="sxs-lookup"><span data-stu-id="d9bd8-121">You can also send an encrypted message by selecting the **Protect** button in Outlook on the web.</span></span> <span data-ttu-id="d9bd8-122">Per ulteriori informazioni, vedere [Inviare, visualizzare e rispondere ai messaggi crittografati in Outlook per PC.](https://support.microsoft.com/en-us/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)</span><span class="sxs-lookup"><span data-stu-id="d9bd8-122">For more information, see [Send, view, and reply to encrypted messages in Outlook for PC](https://support.microsoft.com/en-us/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980).</span></span>

## <a name="admin-settings"></a><span data-ttu-id="d9bd8-123">Impostazioni amministratore</span><span class="sxs-lookup"><span data-stu-id="d9bd8-123">Admin settings</span></span>

<span data-ttu-id="d9bd8-124">Per informazioni sulla configurazione della crittografia della posta elettronica, vedere [Crittografia della posta elettronica in Microsoft 365.](https://docs.microsoft.com/microsoft-365/compliance/email-encryption)</span><span class="sxs-lookup"><span data-stu-id="d9bd8-124">You can learn all about setting up email encryption at [Email encryption in Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/email-encryption).</span></span>

### <a name="automatically-encrypt-email-messages"></a><span data-ttu-id="d9bd8-125">Crittografare automaticamente i messaggi di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="d9bd8-125">Automatically encrypt email messages</span></span>

<span data-ttu-id="d9bd8-126">Gli amministratori possono creare regole del flusso di posta per proteggere automaticamente i messaggi di posta elettronica inviati e ricevuti dalla campagna.</span><span class="sxs-lookup"><span data-stu-id="d9bd8-126">Admins can create mail flow rules to automatically protect email messages that are sent and received from your campaign.</span></span> <span data-ttu-id="d9bd8-127">Configurare le regole per crittografare i messaggi di posta elettronica in uscita e rimuovere la crittografia dai messaggi crittografati provenienti dall'interno dell'organizzazione o dalle risposte ai messaggi crittografati inviati dall'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d9bd8-127">Set up rules to encrypt any outgoing email messages, and remove encryption from encrypted messages coming from inside your organization or from replies to encrypted messages sent from your organization.</span></span>

<span data-ttu-id="d9bd8-128">È possibile creare regole del flusso di posta per crittografare i messaggi di posta elettronica con le nuove funzionalità di crittografia dei messaggi di Office 365.</span><span class="sxs-lookup"><span data-stu-id="d9bd8-128">You create mail flow rules to encrypt email messages with the new Office 365 Message Encryption (OME) capabilities.</span></span> <span data-ttu-id="d9bd8-129">Definire le regole del flusso di posta per attivare la crittografia dei messaggi con le nuove funzionalità di OME utilizzando l'interfaccia di amministrazione di Exchange ( EAC).</span><span class="sxs-lookup"><span data-stu-id="d9bd8-129">Define mail flow rules for triggering message encryption with the new OME capabilities by using the Exchange Admin Center (EAC).</span></span> 

1. <span data-ttu-id="d9bd8-130">In un Web browser, utilizzando un account aziendale o dell'istituto di istruzione a cui sono state concesse autorizzazioni di amministratore globale, accedere.</span><span class="sxs-lookup"><span data-stu-id="d9bd8-130">In a web browser, using a work or school account that has been granted global administrator permissions, sign in.</span></span>
2. <span data-ttu-id="d9bd8-131">Scegliere il riquadro Amministrazione.</span><span class="sxs-lookup"><span data-stu-id="d9bd8-131">Choose the Admin tile.</span></span>
3. <span data-ttu-id="d9bd8-132">In the admin center, choose **Admin centers > Exchange.**</span><span class="sxs-lookup"><span data-stu-id="d9bd8-132">In the admin center, choose **Admin centers > Exchange**.</span></span>

<span data-ttu-id="d9bd8-133">Per ulteriori informazioni, vedere Definire le regole [del flusso di posta per crittografare i messaggi di posta elettronica.](https://docs.microsoft.com/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email)</span><span class="sxs-lookup"><span data-stu-id="d9bd8-133">For more information, see [Define mail flow rules to encrypt email messages](https://docs.microsoft.com/microsoft-365/compliance/define-mail-flow-rules-to-encrypt-email).</span></span>

### <a name="brand-your-encryption-messages"></a><span data-ttu-id="d9bd8-134">Personalizzazione dei messaggi di crittografia</span><span class="sxs-lookup"><span data-stu-id="d9bd8-134">Brand your encryption messages</span></span>

<span data-ttu-id="d9bd8-135">Puoi anche applicare la personalizzazione della campagna per personalizzare l'aspetto e il testo nei messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="d9bd8-135">You can also apply your campaign branding to customize the look and the text in the email messages.</span></span> <span data-ttu-id="d9bd8-136">Per ulteriori informazioni, vedere [Aggiungere il marchio dell'organizzazione ai messaggi crittografati.](https://docs.microsoft.com/microsoft-365/compliance/email-encryption)</span><span class="sxs-lookup"><span data-stu-id="d9bd8-136">For more information, see [Add your organization's brand to your encrypted messages](https://docs.microsoft.com/microsoft-365/compliance/email-encryption).</span></span>
