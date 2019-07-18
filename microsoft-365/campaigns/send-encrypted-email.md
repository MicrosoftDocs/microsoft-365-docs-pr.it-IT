---
title: Inviare messaggi di posta elettronica crittografati
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
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 496e690b-b75d-4ff5-bf34-cc32905d0364
description: Informazioni su come inviare messaggi di posta elettronica crittografati tramite Outlook.
ms.openlocfilehash: 7420073ba768f0e5adba33d673d3ccd6369e306c
ms.sourcegitcommit: 2f4a61f02ea90102ded8e5d71c9b78a1f7f6b789
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/18/2019
ms.locfileid: "35778141"
---
# <a name="encrypt-or-label-your-sensitive-email"></a><span data-ttu-id="73a36-103">Crittografare o contrassegnare il messaggio di posta elettronica sensibile</span><span class="sxs-lookup"><span data-stu-id="73a36-103">Encrypt or label your sensitive email</span></span>

<span data-ttu-id="73a36-104">I dati e le informazioni sulla campagna sono importanti e spesso riservati.</span><span class="sxs-lookup"><span data-stu-id="73a36-104">Your data and campaign information is important and often confidential.</span></span> <span data-ttu-id="73a36-105">Proteggi queste informazioni riservate mediante la crittografia e le etichette di riservatezza affinché tu e i destinatari di posta elettronica trattiate le informazioni con la sensibilità necessaria.</span><span class="sxs-lookup"><span data-stu-id="73a36-105">Help protect this sensitive information by using encryption and sensitivity labels so you and your email recipients treat the information with the sensitivity it requires.</span></span>


## <a name="best-practices"></a><span data-ttu-id="73a36-106">Procedure consigliate</span><span class="sxs-lookup"><span data-stu-id="73a36-106">Best practices</span></span>

<span data-ttu-id="73a36-107">Prima di inviare messaggi di posta elettronica con informazioni riservate o sensibili, prendere in considerazione l'attivazione:</span><span class="sxs-lookup"><span data-stu-id="73a36-107">Before you send email with confidential or sensitive information, consider turning on:</span></span>

- <span data-ttu-id="73a36-108">**Crittografia:** È possibile crittografare il messaggio di posta elettronica per proteggere la privacy delle informazioni contenute nel messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="73a36-108">**Encryption:** You can encrypt your email to protect the privacy of the information in the email.</span></span> <span data-ttu-id="73a36-109">Quando si crittografa un messaggio di posta elettronica, viene convertito dal testo normale leggibile al testo cifrato criptato.</span><span class="sxs-lookup"><span data-stu-id="73a36-109">When you encrypt an email message, it's converted from readable plain text into scrambled cypher text.</span></span> <span data-ttu-id="73a36-110">Solo il destinatario che ha la chiave privata corrispondente alla chiave pubblica utilizzata per crittografare il messaggio può decifrare il messaggio per la lettura.</span><span class="sxs-lookup"><span data-stu-id="73a36-110">Only the recipient who has the private key that matches the public key used to encrypt the message can decipher the message for reading.</span></span> <span data-ttu-id="73a36-111">Qualsiasi destinatario senza la chiave privata corrispondente, tuttavia, Visualizza testo indecifrabile.</span><span class="sxs-lookup"><span data-stu-id="73a36-111">Any recipient without the corresponding private key, however, sees indecipherable text.</span></span> <span data-ttu-id="73a36-112">L'amministratore può definire regole per la crittografia automatica dei messaggi che soddisfano determinati criteri.</span><span class="sxs-lookup"><span data-stu-id="73a36-112">Your admin can define rules to automatically encrypt messages that meet certain criteria.</span></span> <span data-ttu-id="73a36-113">Ad esempio, l'amministratore può creare una regola che consente di crittografare tutti i messaggi inviati all'esterno dell'organizzazione o tutti i messaggi che citano parole o frasi specifiche.</span><span class="sxs-lookup"><span data-stu-id="73a36-113">For instance, your admin can create a rule that encrypts all messages sent outside your organization or all messages that mention specific words or phrases.</span></span> <span data-ttu-id="73a36-114">Tutte le regole di crittografia verranno applicate automaticamente.</span><span class="sxs-lookup"><span data-stu-id="73a36-114">Any encryption rules will be applied automatically.</span></span>
- <span data-ttu-id="73a36-115">**Etichette di riservatezza:** La campagna può anche configurare le etichette di riservatezza che è possibile applicare ai file e ai messaggi di posta elettronica per mantenerli conformi ai criteri di protezione delle informazioni della campagna.</span><span class="sxs-lookup"><span data-stu-id="73a36-115">**Sensitivity labels:** Your campaign can also set up sensitivity labels that you can apply to your files and email to keep them compliant with your campaign's information protection policies.</span></span> <span data-ttu-id="73a36-116">Quando si imposta un'etichetta, l'etichetta viene mantenuta con l'indirizzo di posta elettronica, anche quando viene inviata, ad esempio, come intestazione del messaggio.</span><span class="sxs-lookup"><span data-stu-id="73a36-116">When you set a label, the label persists with your email, even when it's sent - for example, by appearing as a header to your message.</span></span>

![Diagramma di un messaggio di posta elettronica con callout per le etichette e la crittografia](media/m365-campaign-email-encrypt.png)


## <a name="set-it-up"></a><span data-ttu-id="73a36-118">Configurazione</span><span class="sxs-lookup"><span data-stu-id="73a36-118">Set it up</span></span>

<span data-ttu-id="73a36-119">Se si desidera crittografare un messaggio che non soddisfa una regola predefinita o che l'amministratore non ha impostato regole, è possibile applicare una serie di regole di crittografia diverse prima di inviare il messaggio.</span><span class="sxs-lookup"><span data-stu-id="73a36-119">If you want to encrypt a message that doesn't meet a pre-defined rule or your admin hasn't set up any rules, you can apply a variety of different encryption rules before you send the message.</span></span> <span data-ttu-id="73a36-120">Per inviare un messaggio crittografato da Outlook 2013 o 2016 o Outlook 2016 per Mac, selezionare **opzioni > autorizzazioni**, quindi selezionare l'opzione di protezione necessaria.</span><span class="sxs-lookup"><span data-stu-id="73a36-120">To send an encrypted message from Outlook 2013 or 2016, or Outlook 2016 for Mac, select **Options > Permissions**, then select the protection option you need.</span></span> <span data-ttu-id="73a36-121">È anche possibile inviare un messaggio crittografato selezionando \*\*\*\* il pulsante Proteggi in Outlook sul Web.</span><span class="sxs-lookup"><span data-stu-id="73a36-121">You can also send an encrypted message by selecting the **Protect** button in Outlook on the web.</span></span> <span data-ttu-id="73a36-122">Per ulteriori informazioni, vedere [inviare, visualizzare e rispondere a messaggi crittografati in Outlook per PC](https://support.office.com/en-us/article/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980?ui=en-US&rs=en-US&ad=US).</span><span class="sxs-lookup"><span data-stu-id="73a36-122">For more information, see [Send, view, and reply to encrypted messages in Outlook for PC](https://support.office.com/en-us/article/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980?ui=en-US&rs=en-US&ad=US).</span></span>

## <a name="admin-settings"></a><span data-ttu-id="73a36-123">Impostazioni di amministratore</span><span class="sxs-lookup"><span data-stu-id="73a36-123">Admin settings</span></span>

<span data-ttu-id="73a36-124">È possibile ottenere informazioni su come configurare la crittografia della posta elettronica alla [crittografia della posta elettronica in Office 365](https://docs.microsoft.com/en-us/office365/securitycompliance/email-encryption).</span><span class="sxs-lookup"><span data-stu-id="73a36-124">You can learn all about setting up email encryption at [Email encryption in Office 365](https://docs.microsoft.com/en-us/office365/securitycompliance/email-encryption).</span></span>

### <a name="automatically-encrypt-email-messages"></a><span data-ttu-id="73a36-125">Crittografia automatica dei messaggi di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="73a36-125">Automatically encrypt email messages</span></span>

<span data-ttu-id="73a36-126">Gli amministratori possono creare regole del flusso di posta per proteggere automaticamente i messaggi di posta elettronica inviati e ricevuti dalla propria campagna.</span><span class="sxs-lookup"><span data-stu-id="73a36-126">Admins can create mail flow rules to automatically protect email messages that are sent and received from your campaign.</span></span> <span data-ttu-id="73a36-127">Configurare le regole per crittografare i messaggi di posta elettronica in uscita e rimuovere la crittografia dai messaggi crittografati provenienti dall'interno dell'organizzazione o dalle risposte ai messaggi crittografati inviati dall'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="73a36-127">Set up rules to encrypt any outgoing email messages, and remove encryption from encrypted messages coming from inside your organization or from replies to encrypted messages sent from your organization.</span></span> 

<span data-ttu-id="73a36-128">È possibile creare regole del flusso di posta per crittografare i messaggi di posta elettronica con le nuove funzionalità di crittografia dei messaggi di Office 365.</span><span class="sxs-lookup"><span data-stu-id="73a36-128">You create mail flow rules to encrypt email messages with the new Office 365 Message Encryption (OME) capabilities.</span></span> <span data-ttu-id="73a36-129">Definire le regole del flusso di posta per l'attivazione della crittografia dei messaggi con le nuove funzionalità OME utilizzando l'interfaccia di amministrazione di Exchange (EAC).</span><span class="sxs-lookup"><span data-stu-id="73a36-129">Define mail flow rules for triggering message encryption with the new OME capabilities by using the Exchange Admin Center (EAC).</span></span> 

1. <span data-ttu-id="73a36-130">In un Web browser, utilizzando un account aziendale o dell'Istituto di istruzione a cui sono state concesse le autorizzazioni di amministratore globale, accedere a Office 365.</span><span class="sxs-lookup"><span data-stu-id="73a36-130">In a web browser, using a work or school account that has been granted global administrator permissions, sign in to Office 365.</span></span> 
2. <span data-ttu-id="73a36-131">Scegliere il riquadro amministratore.</span><span class="sxs-lookup"><span data-stu-id="73a36-131">Choose the Admin tile.</span></span> 
3. <span data-ttu-id="73a36-132">Nell'interfaccia di amministrazione scegliere **admin centers > Exchange**.</span><span class="sxs-lookup"><span data-stu-id="73a36-132">In the admin center, choose **Admin centers > Exchange**.</span></span> 

<span data-ttu-id="73a36-133">Per ulteriori informazioni, vedere [definire le regole del flusso di posta per crittografare i messaggi di posta elettronica in Office 365](https://docs.microsoft.com/en-us/office365/securitycompliance/define-mail-flow-rules-to-encrypt-email).</span><span class="sxs-lookup"><span data-stu-id="73a36-133">For more information, see [Define mail flow rules to encrypt email messages in Office 365](https://docs.microsoft.com/en-us/office365/securitycompliance/define-mail-flow-rules-to-encrypt-email).</span></span>

### <a name="brand-your-encryption-messages"></a><span data-ttu-id="73a36-134">Personalizzare i messaggi di crittografia</span><span class="sxs-lookup"><span data-stu-id="73a36-134">Brand your encryption messages</span></span>

<span data-ttu-id="73a36-135">È anche possibile applicare la personalizzazione della campagna per personalizzare l'aspetto e il testo nei messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="73a36-135">You can also apply your campaign branding to customize the look and the text in the email messages.</span></span> <span data-ttu-id="73a36-136">Per ulteriori informazioni, vedere [aggiungere il marchio dell'organizzazione ai messaggi crittografati](https://docs.microsoft.com/en-us/office365/securitycompliance/email-encryption).</span><span class="sxs-lookup"><span data-stu-id="73a36-136">For more information, see [Add your organization's brand to your encrypted messages](https://docs.microsoft.com/en-us/office365/securitycompliance/email-encryption).</span></span>

