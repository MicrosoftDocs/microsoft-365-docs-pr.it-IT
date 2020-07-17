---
title: Impostare una data di scadenza per un'e-mail crittografata da Office 365 Advanced Message Encryption
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/8/2019
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: Usare la crittografia avanzata dei messaggi di Office 365 per estendere la sicurezza della posta elettronica impostando una data di scadenza per i messaggi di posta elettronica tramite un modello personalizzato.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e929ce1d948a83a98cca6fa35a65b80a2fc9ef15
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818689"
---
# <a name="set-an-expiration-date-for-email-encrypted-by-office-365-advanced-message-encryption"></a><span data-ttu-id="ee8df-103">Impostare una data di scadenza per un'e-mail crittografata da Office 365 Advanced Message Encryption</span><span class="sxs-lookup"><span data-stu-id="ee8df-103">Set an expiration date for email encrypted by Office 365 Advanced Message Encryption</span></span>

<span data-ttu-id="ee8df-104">La crittografia avanzata dei messaggi di Office 365 è inclusa in [microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (nonprofit staff pricing), Office 365 Enterprise E5 (nonprofit staff pricing) e Office 365 Education a5.</span><span class="sxs-lookup"><span data-stu-id="ee8df-104">Office 365 Advanced Message Encryption is included in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (Nonprofit Staff Pricing), Office 365 Enterprise E5 (Nonprofit Staff Pricing), and Office 365 Education A5.</span></span> <span data-ttu-id="ee8df-105">Se l'organizzazione dispone di un abbonamento che non include la crittografia dei messaggi avanzata di Office 365, è possibile acquistarla con il componente aggiuntivo SKU Microsoft 365 E5 Compliance per Microsoft 365 E3, Microsoft 365 E3 (nonprofit staff pricing) o il componente aggiuntivo Office 365 Advanced Compliance SKU per Microsoft 365 E3, Microsoft 365 E3 (nonprofit staff pricing) o Office 365 SKU.</span><span class="sxs-lookup"><span data-stu-id="ee8df-105">If your organization has a subscription that does not include Office 365 Advanced Message Encryption, you can purchase it with the Microsoft 365 E5 Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or the Office 365 Advanced Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or Office 365 SKUs.</span></span>

<span data-ttu-id="ee8df-106">È possibile utilizzare la scadenza dei messaggi nei messaggi di posta elettronica inviati dagli utenti ai destinatari esterni che utilizzano il portale OME per accedere ai messaggi di posta elettronica crittografati.</span><span class="sxs-lookup"><span data-stu-id="ee8df-106">You can use message expiration on emails that your users send to external recipients who use the OME Portal to access encrypted emails.</span></span> <span data-ttu-id="ee8df-107">È possibile forzare i destinatari a utilizzare il portale OME per visualizzare e rispondere ai messaggi di posta elettronica crittografati inviati dall'organizzazione utilizzando un modello personalizzato che specifichi una data di scadenza in Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ee8df-107">You force recipients to use the OME portal to view and reply to encrypted emails sent by your organization by using a custom branded template that specifies an expiration date in Windows Powershell.</span></span>

<span data-ttu-id="ee8df-108">In qualità di amministratore globale di O365, quando si applica il marchio dell'azienda per personalizzare l'aspetto dei messaggi di posta elettronica dell'organizzazione, è anche possibile specificare una scadenza per i messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="ee8df-108">As an O365 global administrator, when you apply your company brand to customize the look of your organization's email messages, you can also specify an expiration for these email messages.</span></span> <span data-ttu-id="ee8df-109">Grazie alla crittografia avanzata dei messaggi di Office 365, è possibile creare più modelli per i messaggi di posta elettronica crittografati provenienti dall'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ee8df-109">With Office 365 Advanced Message Encryption, you can create multiple templates for encrypted emails that originate from your organization.</span></span> <span data-ttu-id="ee8df-110">Se si utilizza un modello, è possibile controllare la durata di accesso dei destinatari alla posta inviata dagli utenti.</span><span class="sxs-lookup"><span data-stu-id="ee8df-110">Using a template, you can control how long recipients have access to mail sent by your users.</span></span>

<span data-ttu-id="ee8df-111">Quando un utente finale riceve la posta con un set di date di scadenza, l'utente Visualizza la data di scadenza nel messaggio di posta elettronica del wrapper.</span><span class="sxs-lookup"><span data-stu-id="ee8df-111">When an end user receives mail that has an expiration date set, the user sees the expiration date in the wrapper email.</span></span> <span data-ttu-id="ee8df-112">Se un utente tenta di aprire un messaggio di posta elettronica scaduto, viene visualizzato un messaggio di errore nel portale OME.</span><span class="sxs-lookup"><span data-stu-id="ee8df-112">If a user tries to open an expired mail, an error appears in the OME portal.</span></span>

<span data-ttu-id="ee8df-113">È possibile impostare le date di scadenza solo per i messaggi di posta elettronica a destinatari esterni.</span><span class="sxs-lookup"><span data-stu-id="ee8df-113">You can only set expiration dates for emails to external recipients.</span></span>

<span data-ttu-id="ee8df-114">Con la crittografia avanzata dei messaggi di Office 365, ogni volta che si applica il marchio personalizzato, Office 365 applica il wrapper alla posta elettronica adatta alla regola del flusso di posta a cui viene applicato il modello.</span><span class="sxs-lookup"><span data-stu-id="ee8df-114">With Office 365 Advanced Message Encryption, anytime you apply custom branding, the Office 365 applies the wrapper to email that fits the mail flow rule to which you apply the template.</span></span> <span data-ttu-id="ee8df-115">Inoltre, è possibile utilizzare la scadenza solo se si utilizza il marchio personalizzato.</span><span class="sxs-lookup"><span data-stu-id="ee8df-115">In addition, you can only use expiration if you use custom branding.</span></span>

## <a name="create-a-custom-branding-template-to-force-mail-expiration-by-using-powershell"></a><span data-ttu-id="ee8df-116">Creare un modello di personalizzazione personalizzato per forzare la scadenza della posta tramite PowerShell</span><span class="sxs-lookup"><span data-stu-id="ee8df-116">Create a custom branding template to force mail expiration by using PowerShell</span></span>

1. <span data-ttu-id="ee8df-117">[Connettersi a PowerShell di Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) con un account che disponga delle autorizzazioni di amministratore globale nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ee8df-117">[Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) with an account that has global administrator permissions in your organization.</span></span>

2. <span data-ttu-id="ee8df-118">Eseguire il cmdlet New-OMEConfiguration.</span><span class="sxs-lookup"><span data-stu-id="ee8df-118">Run the New-OMEConfiguration cmdlet.</span></span>

     ```powershell
     New-OMEConfiguration -Identity "Expire in 7 days" -ExternalMailExpiryInDays 7
     ```

<span data-ttu-id="ee8df-119">Dove:</span><span class="sxs-lookup"><span data-stu-id="ee8df-119">Where:</span></span>

- <span data-ttu-id="ee8df-120">`Identity`è il nome del modello personalizzato.</span><span class="sxs-lookup"><span data-stu-id="ee8df-120">`Identity` is the name of the custom template.</span></span>

- <span data-ttu-id="ee8df-121">`ExternalMailExpiryInDays`identifica il numero di giorni in cui i destinatari possono mantenere la posta prima della scadenza.</span><span class="sxs-lookup"><span data-stu-id="ee8df-121">`ExternalMailExpiryInDays` identifies the number of days that recipients can keep mail before it expires.</span></span> <span data-ttu-id="ee8df-122">È possibile utilizzare qualsiasi valore compreso tra 1 e 730 giorni.</span><span class="sxs-lookup"><span data-stu-id="ee8df-122">You can use any value between 1–730 days.</span></span>

## <a name="more-information-about-office-365-advanced-message-encryption"></a><span data-ttu-id="ee8df-123">Ulteriori informazioni sulla crittografia avanzata dei messaggi di Office 365</span><span class="sxs-lookup"><span data-stu-id="ee8df-123">More information about Office 365 Advanced Message Encryption</span></span>

- [<span data-ttu-id="ee8df-124">Office 365 Advanced Message Encryption</span><span class="sxs-lookup"><span data-stu-id="ee8df-124">Office 365 Advanced Message Encryption</span></span>](ome-advanced-message-encryption.md)

- [<span data-ttu-id="ee8df-125">Revocare un messaggio di posta elettronica crittografato da Office 365 Advanced Message Encryption</span><span class="sxs-lookup"><span data-stu-id="ee8df-125">Revoke email encrypted by Office 365 Advanced Message Encryption</span></span>](revoke-ome-encrypted-mail.md)

- [<span data-ttu-id="ee8df-126">Descrizione del servizio criteri di conformità e del messaggio</span><span class="sxs-lookup"><span data-stu-id="ee8df-126">Message policy and compliance service description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)
