---
title: 'Passaggio 6: configurare la crittografia della posta elettronica'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
ms.custom: ''
description: Comprendere e configurare la gestione degli accessi con privilegi per Office 365.
ms.openlocfilehash: ef9da1d6aea20ef965b56006d91c4da3c0ad18ab
ms.sourcegitcommit: 8bcd76e5c8749a5670fbc3356957a089454c03d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/02/2019
ms.locfileid: "37370433"
---
# <a name="step-6-configure-email-encryption"></a><span data-ttu-id="6e738-103">Passaggio 6: configurare la crittografia della posta elettronica</span><span class="sxs-lookup"><span data-stu-id="6e738-103">Step 6: Configure email encryption</span></span>

<span data-ttu-id="6e738-104">*Questo passaggio è facoltativo e si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="6e738-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![Fase 6: protezione delle informazioni](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="6e738-106">Sono disponibili tre tipi di crittografia della posta elettronica in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6e738-106">There are three types of email encryption in Microsoft 365.</span></span>

|||
|:-------|:-----|
| <span data-ttu-id="6e738-107">Crittografia messaggi di Office (OME)</span><span class="sxs-lookup"><span data-stu-id="6e738-107">Office Message Encryption (OME)</span></span> | <span data-ttu-id="6e738-108">Crittografia per la posta elettronica di Exchange Online inviata all'esterno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="6e738-108">Encryption for Exchange Online email sent outside your organization.</span></span> |
| <span data-ttu-id="6e738-109">Information Rights Management (IRM)</span><span class="sxs-lookup"><span data-stu-id="6e738-109">Information Rights Management (IRM)</span></span> | <span data-ttu-id="6e738-110">Crittografia e autorizzazioni che viaggiano con il messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="6e738-110">Encryption and permissions that travel with the email.</span></span> |
| <span data-ttu-id="6e738-111">Secure/Multipurpose Internet Mail Extensions (S/MIME)</span><span class="sxs-lookup"><span data-stu-id="6e738-111">Secure/Multipurpose Internet Mail Extensions (S/MIME)</span></span> | <span data-ttu-id="6e738-112">Protezione della posta elettronica con crittografia e firme digitali.</span><span class="sxs-lookup"><span data-stu-id="6e738-112">Email protection with encryption and digital signatures.</span></span> |
|||

## <a name="office-365-message-encryption"></a><span data-ttu-id="6e738-113">Crittografia dei messaggi di Office 365</span><span class="sxs-lookup"><span data-stu-id="6e738-113">Office 365 Message Encryption</span></span>

<span data-ttu-id="6e738-114">Con OME, l'organizzazione può inviare e ricevere messaggi di posta elettronica crittografati tra persone all'interno e all'esterno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="6e738-114">With OME, your organization can send and receive encrypted email messages between people inside and outside your organization.</span></span> <span data-ttu-id="6e738-115">OME è compatibile con Outlook.com, Yahoo!, Gmail e altri servizi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="6e738-115">OME works with Outlook.com, Yahoo!, Gmail, and other email services.</span></span> <span data-ttu-id="6e738-116">La crittografia dei messaggi di posta elettronica aiuta a garantire che solo i destinatari previsti possano visualizzare il messaggio.</span><span class="sxs-lookup"><span data-stu-id="6e738-116">Email message encryption helps ensure that only intended recipients can view the message.</span></span>

![Crittografia OME dei messaggi di posta elettronica](./media/infoprotect-email-encryption/ome-encryption.png)

<span data-ttu-id="6e738-118">Si configurano le regole di trasporto che definiscono le condizioni per la crittografia.</span><span class="sxs-lookup"><span data-stu-id="6e738-118">You set up transport rules that define the conditions for encryption.</span></span> <span data-ttu-id="6e738-119">Quando un utente invia un messaggio che corrisponde a una regola, la crittografia viene applicata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="6e738-119">When a user sends a message that matches a rule, encryption is applied automatically.</span></span>

<span data-ttu-id="6e738-120">Per visualizzare i messaggi crittografati, i destinatari possono ottenere un codice di accesso una tantum, accedere con un account Microsoft o accedere con un account aziendale o dell'Istituto di istruzione associato a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6e738-120">To view encrypted messages, recipients can either get a one-time passcode, sign in with a Microsoft account, or sign in with a work or school account associated with Microsoft 365.</span></span> <span data-ttu-id="6e738-121">I destinatari possono inoltre inviare risposte crittografate.</span><span class="sxs-lookup"><span data-stu-id="6e738-121">Recipients can also send encrypted replies.</span></span> <span data-ttu-id="6e738-122">Non è necessario che la propria sottoscrizione Microsoft 365 venga visualizzata per visualizzare i messaggi crittografati o inviare risposte crittografate.</span><span class="sxs-lookup"><span data-stu-id="6e738-122">They don't need their own Microsoft 365 subscription to view encrypted messages or send encrypted replies.</span></span>

<span data-ttu-id="6e738-123">Per ulteriori informazioni, vedere [Crittografia dei messaggi di Office 365](https://docs.microsoft.com/Office365/SecurityCompliance/ome).</span><span class="sxs-lookup"><span data-stu-id="6e738-123">For more information, see [Office 365 Message Encryption](https://docs.microsoft.com/Office365/SecurityCompliance/ome).</span></span>

## <a name="irm"></a><span data-ttu-id="6e738-124">IRM</span><span class="sxs-lookup"><span data-stu-id="6e738-124">IRM</span></span>

<span data-ttu-id="6e738-125">IRM in Microsoft 365 consente di proteggere le informazioni con la crittografia aggiuntiva e applicando un criterio intelligente che specifichi chi ha accesso a ciò che può fare.</span><span class="sxs-lookup"><span data-stu-id="6e738-125">IRM in Microsoft 365 helps you secure your information with additional encryption and by applying an intelligent policy that specifies who has access what they can do.</span></span> <span data-ttu-id="6e738-126">Per i messaggi di posta elettronica, è possibile utilizzare IRM per la crittografia e applicare restrizioni di utilizzo.</span><span class="sxs-lookup"><span data-stu-id="6e738-126">For email messages, you can use IRM for encryption and to apply usage restrictions.</span></span> <span data-ttu-id="6e738-127">Ad esempio, è possibile specificare che alcuni destinatari hanno tutte le capacità di gestire il messaggio di posta elettronica e alcuni utenti non hanno la possibilità di stampare o inoltrare il messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="6e738-127">For example, you can specify that some recipients have all abilities to manage the email and some do not have the ability to print or forward the email.</span></span> 

<span data-ttu-id="6e738-128">I criteri IRM sono configurati all'interno di Microsoft 365 e possono essere applicati ai documenti in SharePoint Online e nei messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="6e738-128">IRM policies are configured within Microsoft 365 and can apply to documents in SharePoint Online and email messages.</span></span> <span data-ttu-id="6e738-129">Un messaggio di posta elettronica protetto da IRM include le impostazioni dei criteri applicate e viaggia con esso.</span><span class="sxs-lookup"><span data-stu-id="6e738-129">An IRM-protected email includes the applied policy settings applied and travel with it.</span></span> 

![Protezione IRM dei messaggi di posta elettronica](./media/infoprotect-email-encryption/irm-protection.png)

<span data-ttu-id="6e738-131">Quando il destinatario apre la posta elettronica con il criterio incluso, le impostazioni dei criteri vengono utilizzate per decrittografare il messaggio e determinare cosa può fare il destinatario.</span><span class="sxs-lookup"><span data-stu-id="6e738-131">When the recipient opens the email with the included policy, the policy settings are used to decrypt the message and determine what the recipient can do with it.</span></span> 

<span data-ttu-id="6e738-132">Per ulteriori informazioni, vedere [Information Rights Management in Exchange Online]( https://docs.microsoft.com/office365/SecurityCompliance/information-rights-management-in-exchange-online).</span><span class="sxs-lookup"><span data-stu-id="6e738-132">For more information, see [Information Rights Management in Exchange Online]( https://docs.microsoft.com/office365/SecurityCompliance/information-rights-management-in-exchange-online).</span></span>

## <a name="smime"></a><span data-ttu-id="6e738-133">S/MIME</span><span class="sxs-lookup"><span data-stu-id="6e738-133">S/MIME</span></span>

<span data-ttu-id="6e738-134">S/MIME è una soluzione di protezione basata sulla posta elettronica basata su certificato digitale che consente di crittografare e firmare digitalmente un messaggio.</span><span class="sxs-lookup"><span data-stu-id="6e738-134">S/MIME is a digital certificate-based email-based protection solution that allows you to both encrypt and digitally sign a message.</span></span> <span data-ttu-id="6e738-135">La crittografia dei messaggi consente di garantire che solo il destinatario previsto riesca ad aprire e leggere il messaggio.</span><span class="sxs-lookup"><span data-stu-id="6e738-135">The message encryption helps ensure that only the intended recipient can open and read the message.</span></span> <span data-ttu-id="6e738-136">Una firma digitale consente al destinatario di convalidare l'identità del mittente e di determinare che solo il mittente potrebbe averlo inviato.</span><span class="sxs-lookup"><span data-stu-id="6e738-136">A digital signature helps the recipient validate the identity of the sender and determine that only the sender could have sent it.</span></span>

![Protezione S/MIME dei messaggi di posta elettronica](./media/infoprotect-email-encryption/smime-protection.png)

<span data-ttu-id="6e738-138">S/MIME può essere utilizzato per la posta elettronica ad altre cassette postali nell'abbonamento a Microsoft 365 o a utenti esterni.</span><span class="sxs-lookup"><span data-stu-id="6e738-138">S/MIME can be used for email to other mailboxes in your Microsoft 365 subscription or to external users.</span></span>
<span data-ttu-id="6e738-139">Sia la crittografia dei messaggi che le firme digitali sono rese possibili mediante l'utilizzo di certificati digitali che contengono le chiavi pubbliche e private per la crittografia o la decrittografia dei messaggi e la creazione e la verifica delle firme digitali.</span><span class="sxs-lookup"><span data-stu-id="6e738-139">Both message encryption and digital signatures are made possible through the use of digital certificates that contain the public and private keys for encrypting or decrypting messages and creating and verifying digital signatures.</span></span>
<span data-ttu-id="6e738-140">Per utilizzare S/MIME, è necessario disporre delle chiavi pubbliche per ogni destinatario.</span><span class="sxs-lookup"><span data-stu-id="6e738-140">To use S/MIME, you must have the public keys for each recipient.</span></span> <span data-ttu-id="6e738-141">I destinatari mantengono le proprie chiavi private, che devono rimanere sicure.</span><span class="sxs-lookup"><span data-stu-id="6e738-141">Recipients maintain their own private keys, which must remain secure.</span></span> <span data-ttu-id="6e738-142">Se la chiave privata è compromessa, è necessario ottenere un nuovo certificato digitale e ridistribuire le chiavi pubbliche a tutti i potenziali mittenti.</span><span class="sxs-lookup"><span data-stu-id="6e738-142">If your private key is compromised, you need to get a new digital certificate and redistribute public keys to all potential senders.</span></span>

<span data-ttu-id="6e738-143">Per ulteriori informazioni, vedere [S/MIME per la firma e la crittografia dei messaggi](https://docs.microsoft.com/Exchange/policy-and-compliance/smime).</span><span class="sxs-lookup"><span data-stu-id="6e738-143">For more information, see [S/MIME for message signing and encryption](https://docs.microsoft.com/Exchange/policy-and-compliance/smime).</span></span>


<span data-ttu-id="6e738-144">Come checkpoint provvisorio, vedere i [criteri uscita](infoprotect-exit-criteria.md#crit-infoprotect-step6) che corrispondono a questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="6e738-144">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step6) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="6e738-145">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="6e738-145">Next step</span></span>

|||
|:-------|:-----|
|![Passaggio 7](./media/stepnumbers/Step7.png)|[<span data-ttu-id="6e738-147">Configurare la gestione degli accessi con privilegi per Office 365</span><span class="sxs-lookup"><span data-stu-id="6e738-147">Configure privileged access management for Office 365</span></span>](infoprotect-configure-privileged-access-management.md)|
