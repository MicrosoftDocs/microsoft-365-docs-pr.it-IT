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
ms.openlocfilehash: 7747f5a0905a9477e9d3fd17b00eae740d76f640
ms.sourcegitcommit: 78fa107271252d902e600196a75cfa746bca73e6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/19/2019
ms.locfileid: "37050297"
---
# <a name="step-6-configure-email-encryption"></a><span data-ttu-id="439be-103">Passaggio 6: configurare la crittografia della posta elettronica</span><span class="sxs-lookup"><span data-stu-id="439be-103">Step 6: Configure email encryption</span></span>

<span data-ttu-id="439be-104">*Questo passaggio è facoltativo e si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*</span><span class="sxs-lookup"><span data-stu-id="439be-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="439be-105">Sono disponibili tre tipi di crittografia della posta elettronica in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="439be-105">There are three types of email encryption in Microsoft 365.</span></span>

|||
|:-------|:-----|
| <span data-ttu-id="439be-106">Crittografia messaggi di Office (OME)</span><span class="sxs-lookup"><span data-stu-id="439be-106">Office Message Encryption (OME)</span></span> | <span data-ttu-id="439be-107">Crittografia per la posta elettronica di Exchange Online inviata all'esterno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="439be-107">Encryption for Exchange Online email sent outside your organization.</span></span> |
| <span data-ttu-id="439be-108">Information Rights Management (IRM)</span><span class="sxs-lookup"><span data-stu-id="439be-108">Information Rights Management (IRM)</span></span> | <span data-ttu-id="439be-109">Crittografia e autorizzazioni che viaggiano con il messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="439be-109">Encryption and permissions that travel with the email.</span></span> |
| <span data-ttu-id="439be-110">Secure/Multipurpose Internet Mail Extensions (S/MIME)</span><span class="sxs-lookup"><span data-stu-id="439be-110">Secure/Multipurpose Internet Mail Extensions (S/MIME)</span></span> | <span data-ttu-id="439be-111">Protezione della posta elettronica con crittografia e firme digitali.</span><span class="sxs-lookup"><span data-stu-id="439be-111">Email protection with encryption and digital signatures.</span></span> |
|||

## <a name="office-365-message-encryption"></a><span data-ttu-id="439be-112">Crittografia dei messaggi di Office 365</span><span class="sxs-lookup"><span data-stu-id="439be-112">Office 365 Message Encryption</span></span>

<span data-ttu-id="439be-113">Con OME, l'organizzazione può inviare e ricevere messaggi di posta elettronica crittografati tra persone all'interno e all'esterno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="439be-113">With OME, your organization can send and receive encrypted email messages between people inside and outside your organization.</span></span> <span data-ttu-id="439be-114">OME è compatibile con Outlook.com, Yahoo!, Gmail e altri servizi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="439be-114">OME works with Outlook.com, Yahoo!, Gmail, and other email services.</span></span> <span data-ttu-id="439be-115">La crittografia dei messaggi di posta elettronica aiuta a garantire che solo i destinatari previsti possano visualizzare il messaggio.</span><span class="sxs-lookup"><span data-stu-id="439be-115">Email message encryption helps ensure that only intended recipients can view the message.</span></span>

![Crittografia OME dei messaggi di posta elettronica](./media/infoprotect-email-encryption/ome-encryption.png)

<span data-ttu-id="439be-117">Si configurano le regole di trasporto che definiscono le condizioni per la crittografia.</span><span class="sxs-lookup"><span data-stu-id="439be-117">You set up transport rules that define the conditions for encryption.</span></span> <span data-ttu-id="439be-118">Quando un utente invia un messaggio che corrisponde a una regola, la crittografia viene applicata automaticamente.</span><span class="sxs-lookup"><span data-stu-id="439be-118">When a user sends a message that matches a rule, encryption is applied automatically.</span></span>

<span data-ttu-id="439be-119">Per visualizzare i messaggi crittografati, i destinatari possono ottenere un codice di accesso una tantum, accedere con un account Microsoft o accedere con un account aziendale o dell'Istituto di istruzione associato a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="439be-119">To view encrypted messages, recipients can either get a one-time passcode, sign in with a Microsoft account, or sign in with a work or school account associated with Microsoft 365.</span></span> <span data-ttu-id="439be-120">I destinatari possono inoltre inviare risposte crittografate.</span><span class="sxs-lookup"><span data-stu-id="439be-120">Recipients can also send encrypted replies.</span></span> <span data-ttu-id="439be-121">Non è necessario che la propria sottoscrizione Microsoft 365 venga visualizzata per visualizzare i messaggi crittografati o inviare risposte crittografate.</span><span class="sxs-lookup"><span data-stu-id="439be-121">They don't need their own Microsoft 365 subscription to view encrypted messages or send encrypted replies.</span></span>

<span data-ttu-id="439be-122">Per ulteriori informazioni, vedere [Crittografia dei messaggi di Office 365](https://docs.microsoft.com/Office365/SecurityCompliance/ome).</span><span class="sxs-lookup"><span data-stu-id="439be-122">For more information, see [Office 365 Message Encryption](https://docs.microsoft.com/Office365/SecurityCompliance/ome).</span></span>

## <a name="irm"></a><span data-ttu-id="439be-123">IRM</span><span class="sxs-lookup"><span data-stu-id="439be-123">IRM</span></span>

<span data-ttu-id="439be-124">IRM in Microsoft 365 consente di proteggere le informazioni con la crittografia aggiuntiva e applicando un criterio intelligente che specifichi chi ha accesso a ciò che può fare.</span><span class="sxs-lookup"><span data-stu-id="439be-124">IRM in Microsoft 365 helps you secure your information with additional encryption and by applying an intelligent policy that specifies who has access what they can do.</span></span> <span data-ttu-id="439be-125">Per i messaggi di posta elettronica, è possibile utilizzare IRM per la crittografia e applicare restrizioni di utilizzo.</span><span class="sxs-lookup"><span data-stu-id="439be-125">For email messages, you can use IRM for encryption and to apply usage restrictions.</span></span> <span data-ttu-id="439be-126">Ad esempio, è possibile specificare che alcuni destinatari hanno tutte le capacità di gestire il messaggio di posta elettronica e alcuni utenti non hanno la possibilità di stampare o inoltrare il messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="439be-126">For example, you can specify that some recipients have all abilities to manage the email and some do not have the ability to print or forward the email.</span></span> 

<span data-ttu-id="439be-127">I criteri IRM sono configurati all'interno di Microsoft 365 e possono essere applicati ai documenti in SharePoint Online e nei messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="439be-127">IRM policies are configured within Microsoft 365 and can apply to documents in SharePoint Online and email messages.</span></span> <span data-ttu-id="439be-128">Un messaggio di posta elettronica protetto da IRM include le impostazioni dei criteri applicate e viaggia con esso.</span><span class="sxs-lookup"><span data-stu-id="439be-128">An IRM-protected email includes the applied policy settings applied and travel with it.</span></span> 

![Protezione IRM dei messaggi di posta elettronica](./media/infoprotect-email-encryption/irm-protection.png)

<span data-ttu-id="439be-130">Quando il destinatario apre la posta elettronica con il criterio incluso, le impostazioni dei criteri vengono utilizzate per decrittografare il messaggio e determinare cosa può fare il destinatario.</span><span class="sxs-lookup"><span data-stu-id="439be-130">When the recipient opens the email with the included policy, the policy settings are used to decrypt the message and determine what the recipient can do with it.</span></span> 

<span data-ttu-id="439be-131">Per ulteriori informazioni, vedere [Information Rights Management in Exchange Online]( https://docs.microsoft.com/office365/SecurityCompliance/information-rights-management-in-exchange-online).</span><span class="sxs-lookup"><span data-stu-id="439be-131">For more information, see [Information Rights Management in Exchange Online]( https://docs.microsoft.com/office365/SecurityCompliance/information-rights-management-in-exchange-online).</span></span>

## <a name="smime"></a><span data-ttu-id="439be-132">S/MIME</span><span class="sxs-lookup"><span data-stu-id="439be-132">S/MIME</span></span>

<span data-ttu-id="439be-133">S/MIME è una soluzione di protezione basata sulla posta elettronica basata su certificato digitale che consente di crittografare e firmare digitalmente un messaggio.</span><span class="sxs-lookup"><span data-stu-id="439be-133">S/MIME is a digital certificate-based email-based protection solution that allows you to both encrypt and digitally sign a message.</span></span> <span data-ttu-id="439be-134">La crittografia dei messaggi consente di garantire che solo il destinatario previsto riesca ad aprire e leggere il messaggio.</span><span class="sxs-lookup"><span data-stu-id="439be-134">The message encryption helps ensure that only the intended recipient can open and read the message.</span></span> <span data-ttu-id="439be-135">Una firma digitale consente al destinatario di convalidare l'identità del mittente e di determinare che solo il mittente potrebbe averlo inviato.</span><span class="sxs-lookup"><span data-stu-id="439be-135">A digital signature helps the recipient validate the identity of the sender and determine that only the sender could have sent it.</span></span>

![Protezione S/MIME dei messaggi di posta elettronica](./media/infoprotect-email-encryption/smime-protection.png)

<span data-ttu-id="439be-137">S/MIME può essere utilizzato per la posta elettronica ad altre cassette postali nell'abbonamento a Microsoft 365 o a utenti esterni.</span><span class="sxs-lookup"><span data-stu-id="439be-137">S/MIME can be used for email to other mailboxes in your Microsoft 365 subscription or to external users.</span></span>
<span data-ttu-id="439be-138">Sia la crittografia dei messaggi che le firme digitali sono rese possibili mediante l'utilizzo di certificati digitali che contengono le chiavi pubbliche e private per la crittografia o la decrittografia dei messaggi e la creazione e la verifica delle firme digitali.</span><span class="sxs-lookup"><span data-stu-id="439be-138">Both message encryption and digital signatures are made possible through the use of digital certificates that contain the public and private keys for encrypting or decrypting messages and creating and verifying digital signatures.</span></span>
<span data-ttu-id="439be-139">Per utilizzare S/MIME, è necessario disporre delle chiavi pubbliche per ogni destinatario.</span><span class="sxs-lookup"><span data-stu-id="439be-139">To use S/MIME, you must have the public keys for each recipient.</span></span> <span data-ttu-id="439be-140">I destinatari mantengono le proprie chiavi private, che devono rimanere sicure.</span><span class="sxs-lookup"><span data-stu-id="439be-140">Recipients maintain their own private keys, which must remain secure.</span></span> <span data-ttu-id="439be-141">Se la chiave privata è compromessa, è necessario ottenere un nuovo certificato digitale e ridistribuire le chiavi pubbliche a tutti i potenziali mittenti.</span><span class="sxs-lookup"><span data-stu-id="439be-141">If your private key is compromised, you need to get a new digital certificate and redistribute public keys to all potential senders.</span></span>

<span data-ttu-id="439be-142">Per ulteriori informazioni, vedere [S/MIME per la firma e la crittografia dei messaggi](https://docs.microsoft.com/Exchange/policy-and-compliance/smime).</span><span class="sxs-lookup"><span data-stu-id="439be-142">For more information, see [S/MIME for message signing and encryption](https://docs.microsoft.com/Exchange/policy-and-compliance/smime).</span></span>


<span data-ttu-id="439be-143">Come checkpoint provvisorio, vedere i [criteri uscita](infoprotect-exit-criteria.md#crit-infoprotect-step6) che corrispondono a questo passaggio.</span><span class="sxs-lookup"><span data-stu-id="439be-143">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step6) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="439be-144">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="439be-144">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step7.png)|[<span data-ttu-id="439be-145">Configurare la gestione degli accessi con privilegi per Office 365</span><span class="sxs-lookup"><span data-stu-id="439be-145">Configure privileged access management for Office 365</span></span>](infoprotect-configure-privileged-access-management.md)|
