---
title: Impostare una data di scadenza per un messaggio di posta elettronica crittografato da Office 365 Advanced Message Encryption
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 4/30/2019
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.assetid: f87cb016-7876-4317-ae3c-9169b311ff8a
description: Con le funzionalità di crittografia dei messaggi avanzate di Office 365 in cima a Office 365 Message Encryption (OME), è possibile estendere la sicurezza della posta elettronica impostando una data di scadenza nei messaggi di posta elettronica tramite un modello personalizzato.
ms.openlocfilehash: 7c4ad1fb4a91bd62569edc5db9042dfbd2dbd9fe
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37084450"
---
# <a name="set-an-expiration-date-for-email-encrypted-by-office-365-advanced-message-encryption"></a><span data-ttu-id="ed81e-103">Impostare una data di scadenza per un messaggio di posta elettronica crittografato da Office 365 Advanced Message Encryption</span><span class="sxs-lookup"><span data-stu-id="ed81e-103">Set an expiration date for email encrypted by Office 365 Advanced Message Encryption</span></span>

<span data-ttu-id="ed81e-104">La crittografia avanzata dei messaggi di Office 365 è disponibile nella parte superiore della crittografia messaggi di Office 365 in alcuni abbonamenti.</span><span class="sxs-lookup"><span data-stu-id="ed81e-104">Office 365 Advanced Message Encryption is available on top of Office 365 Message Encryption in certain subscriptions.</span></span> <span data-ttu-id="ed81e-105">La crittografia avanzata dei messaggi è inclusa in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 Enterprise E5 e Office 365 Education a5.</span><span class="sxs-lookup"><span data-stu-id="ed81e-105">Advanced Message Encryption is included in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 Enterprise E5, and Office 365 Education A5.</span></span> <span data-ttu-id="ed81e-106">Se l'organizzazione dispone di un abbonamento a Office 365 che non include la crittografia avanzata dei messaggi di Office 365, è possibile acquistare la crittografia avanzata del messaggio come componente aggiuntivo con la conformità E5 della SKU per la conformità avanzata.</span><span class="sxs-lookup"><span data-stu-id="ed81e-106">If your organization has an Office 365 subscription that doesn't include Office 365 Advanced Message Encryption, you can purchase Advanced Message Encryption as an add-on with E5 Compliance of the Advanced Compliance SKU.</span></span>

<span data-ttu-id="ed81e-107">È possibile utilizzare la scadenza dei messaggi nei messaggi di posta elettronica inviati dagli utenti ai destinatari esterni che utilizzano il portale OME per accedere ai messaggi di posta elettronica crittografati.</span><span class="sxs-lookup"><span data-stu-id="ed81e-107">You can use message expiration on emails that your users send to external recipients who use the OME Portal to access encrypted emails.</span></span> <span data-ttu-id="ed81e-108">È possibile forzare i destinatari a utilizzare il portale OME per visualizzare e rispondere ai messaggi di posta elettronica crittografati inviati dall'organizzazione utilizzando un modello personalizzato che specifichi una data di scadenza in Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ed81e-108">You force recipients to use the OME portal to view and reply to encrypted emails sent by your organization by using a custom branded template that specifies an expiration date in Windows Powershell.</span></span>

<span data-ttu-id="ed81e-109">In qualità di amministratore globale di O365, quando si applica il marchio dell'azienda per personalizzare l'aspetto dei messaggi di posta elettronica dell'organizzazione di Office 365, è anche possibile specificare una scadenza per i messaggi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="ed81e-109">As an O365 global administrator, when you apply your company brand to customize the look of your Office 365 organization's email messages, you can also specify an expiration for these email messages.</span></span> <span data-ttu-id="ed81e-110">Grazie alla crittografia avanzata dei messaggi di Office 365, è possibile creare più modelli per i messaggi di posta elettronica crittografati provenienti dall'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ed81e-110">With Office 365 Advanced Message Encryption, you can create multiple templates for encrypted emails that originate from your organization.</span></span> <span data-ttu-id="ed81e-111">Se si utilizza un modello, è possibile controllare la durata di accesso dei destinatari alla posta inviata dagli utenti.</span><span class="sxs-lookup"><span data-stu-id="ed81e-111">Using a template, you can control how long recipients have access to mail sent by your users.</span></span>

<span data-ttu-id="ed81e-112">Quando un utente finale riceve la posta con un set di date di scadenza, l'utente Visualizza la data di scadenza nel messaggio di posta elettronica del wrapper.</span><span class="sxs-lookup"><span data-stu-id="ed81e-112">When an end user receives mail that has an expiration date set, the user sees the expiration date in the wrapper email.</span></span> <span data-ttu-id="ed81e-113">Se un utente tenta di aprire un messaggio di posta elettronica scaduto, viene visualizzato un messaggio di errore nel portale OME.</span><span class="sxs-lookup"><span data-stu-id="ed81e-113">If a user tries to open an expired mail, an error appears in the OME portal.</span></span>

<span data-ttu-id="ed81e-114">È possibile impostare le date di scadenza solo per i messaggi di posta elettronica a destinatari esterni.</span><span class="sxs-lookup"><span data-stu-id="ed81e-114">You can only set expiration dates for emails to external recipients.</span></span>

<span data-ttu-id="ed81e-115">Con la crittografia avanzata dei messaggi di Office 365, ogni volta che si applica il marchio personalizzato, Office 365 applica il wrapper alla posta elettronica adatta alla regola del flusso di posta a cui viene applicato il modello.</span><span class="sxs-lookup"><span data-stu-id="ed81e-115">With Office 365 Advanced Message Encryption, anytime you apply custom branding, the Office 365 applies the wrapper to email that fits the mail flow rule to which you apply the template.</span></span> <span data-ttu-id="ed81e-116">Inoltre, è possibile utilizzare la scadenza solo se si utilizza il marchio personalizzato.</span><span class="sxs-lookup"><span data-stu-id="ed81e-116">In addition, you can only use expiration if you use custom branding.</span></span>

## <a name="create-a-custom-branding-template-to-force-mail-expiration-by-using-powershell"></a><span data-ttu-id="ed81e-117">Creare un modello di personalizzazione personalizzato per forzare la scadenza della posta tramite PowerShell</span><span class="sxs-lookup"><span data-stu-id="ed81e-117">Create a custom branding template to force mail expiration by using PowerShell</span></span>

1. <span data-ttu-id="ed81e-118">[Connettersi a PowerShell di Exchange Online](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) con un account che disponga delle autorizzazioni di amministratore globale nell'organizzazione di Office 365.</span><span class="sxs-lookup"><span data-stu-id="ed81e-118">[Connect to Exchange Online PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) with an account that has global administrator permissions in your Office 365 organization.</span></span>

2. <span data-ttu-id="ed81e-119">Eseguire il cmdlet New-OMEConfiguration.</span><span class="sxs-lookup"><span data-stu-id="ed81e-119">Run the New-OMEConfiguration cmdlet.</span></span>

     ```powershell
     New-OMEConfiguration -Identity "Expire in 7 days" -ExternalMailExpiryInDays 7
     ```

<span data-ttu-id="ed81e-120">Dove:</span><span class="sxs-lookup"><span data-stu-id="ed81e-120">Where:</span></span>

- <span data-ttu-id="ed81e-121">`Identity`è il nome del modello personalizzato.</span><span class="sxs-lookup"><span data-stu-id="ed81e-121">`Identity` is the name of the custom template.</span></span>

- <span data-ttu-id="ed81e-122">`ExternalMailExpiryInDays`identifica il numero di giorni in cui i destinatari possono mantenere la posta prima della scadenza.</span><span class="sxs-lookup"><span data-stu-id="ed81e-122">`ExternalMailExpiryInDays` identifies the number of days that recipients can keep mail before it expires.</span></span> <span data-ttu-id="ed81e-123">È possibile utilizzare qualsiasi valore compreso tra 1 e 730 giorni.</span><span class="sxs-lookup"><span data-stu-id="ed81e-123">You can use any value between 1–730 days.</span></span>

## <a name="more-information-about-office-365-advanced-message-encryption"></a><span data-ttu-id="ed81e-124">Ulteriori informazioni sulla crittografia avanzata dei messaggi di Office 365</span><span class="sxs-lookup"><span data-stu-id="ed81e-124">More information about Office 365 Advanced Message Encryption</span></span>

- [<span data-ttu-id="ed81e-125">Office 365 Advanced Message Encryption</span><span class="sxs-lookup"><span data-stu-id="ed81e-125">Office 365 Advanced Message Encryption</span></span>](ome-advanced-message-encryption.md)

- [<span data-ttu-id="ed81e-126">Revocare un messaggio di posta elettronica crittografato da Office 365 Advanced Message Encryption</span><span class="sxs-lookup"><span data-stu-id="ed81e-126">Revoke email encrypted by Office 365 Advanced Message Encryption</span></span>](revoke-ome-encrypted-mail.md)

- [<span data-ttu-id="ed81e-127">Descrizione del servizio criteri di conformità e del messaggio</span><span class="sxs-lookup"><span data-stu-id="ed81e-127">Message policy and compliance service description</span></span>](https://docs.microsoft.com/en-us/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)
