---
title: Reindirizzare gli utenti Office 365 centro sicurezza e conformità alla Centro conformità Microsoft 365
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
ms.service: O365-seccomp
audience: ITPro
ms.topic: article
localization_priority: Normal
description: Informazioni sul reindirizzamento automatico Office 365 utenti del Centro sicurezza e conformità al Centro conformità Microsoft 365..
ms.collection: M365-security-compliance
ms.openlocfilehash: 62fc302f9f065ac7bb0475a6e72dc240a56a1fe1
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339407"
---
# <a name="redirect-users-from-the-office-365-security-and-compliance-center-to-the-microsoft-365-compliance-center"></a><span data-ttu-id="b9534-103">Reindirizzare gli utenti Office 365 centro sicurezza e conformità alla Centro conformità Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b9534-103">Redirect users from the Office 365 Security and Compliance center to the Microsoft 365 compliance center</span></span>

<span data-ttu-id="b9534-104">In questo articolo viene illustrato il funzionamento del reindirizzamento automatico per gli utenti che accedono alle soluzioni di conformità dal Centro sicurezza e conformità di Office 365 (protection.office.com) al Centro conformità Microsoft 365 (compliance.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="b9534-104">This article explains how automatic redirection works for users accessing compliance solutions from the Office 365 Security and Compliance Center (protection.office.com) to the Microsoft 365 compliance center (compliance.microsoft.com).</span></span>

## <a name="what-to-expect"></a><span data-ttu-id="b9534-105">Cosa aspettarsi</span><span class="sxs-lookup"><span data-stu-id="b9534-105">What to expect</span></span>

<span data-ttu-id="b9534-106">Il reindirizzamento automatico è abilitato per impostazione predefinita per tutti gli utenti che accedono alle soluzioni correlate alla conformità seguenti in Office 365 Security and Compliance (protection.office.com):</span><span class="sxs-lookup"><span data-stu-id="b9534-106">Automatic redirection is enabled by default for all users accessing the following compliance-related solutions in Office 365 Security and Compliance (protection.office.com):</span></span>

- <span data-ttu-id="b9534-107">Prevenzione della perdita di dati (DLP)</span><span class="sxs-lookup"><span data-stu-id="b9534-107">Data loss prevention (DLP)</span></span>
- <span data-ttu-id="b9534-108">Classificazione</span><span class="sxs-lookup"><span data-stu-id="b9534-108">Classification</span></span>
- <span data-ttu-id="b9534-109">Governance delle informazioni</span><span class="sxs-lookup"><span data-stu-id="b9534-109">Information governance</span></span>
- <span data-ttu-id="b9534-110">Gestione dei record</span><span class="sxs-lookup"><span data-stu-id="b9534-110">Records management</span></span>
- <span data-ttu-id="b9534-111">Conformità delle comunicazioni (in precedenza "Supervisione")Communication compliance (formerly 'Supervision')</span><span class="sxs-lookup"><span data-stu-id="b9534-111">Communication compliance (formerly 'Supervision')</span></span>

<span data-ttu-id="b9534-112">Gli utenti vengono instradati automaticamente alle stesse soluzioni di conformità nel Centro conformità Microsoft 365 (compliance.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="b9534-112">Users are automatically routed to the same compliance solutions in the Microsoft 365 compliance center (compliance.microsoft.com).</span></span>

> [!NOTE]
> <span data-ttu-id="b9534-113">Per altre soluzioni di conformità incluse nel Centro sicurezza e conformità di Office 365, gli utenti continueranno a gestire queste soluzioni nel Centro conformità Microsoft 365 o nel Centro sicurezza e conformità di Office 365.</span><span class="sxs-lookup"><span data-stu-id="b9534-113">For other compliance solutions included in the Office 365 Security and Compliance Center, users will continue to manage these solutions in either the Microsoft 365 compliance center or the Office 365 Security and Compliance Center.</span></span> <span data-ttu-id="b9534-114">Il reindirizzamento automatico per queste soluzioni di conformità sarà disponibile a breve.</span><span class="sxs-lookup"><span data-stu-id="b9534-114">The automatic redirection for these compliance solutions will be available soon.</span></span>

<span data-ttu-id="b9534-115">Questa funzionalità e i controlli associati non abilitano il reindirizzamento automatico delle funzionalità di sicurezza per Microsoft Defender per Office 365.</span><span class="sxs-lookup"><span data-stu-id="b9534-115">This feature and associated controls does not enable the automatic redirection of Security features for Microsoft Defender for Office 365.</span></span> <span data-ttu-id="b9534-116">Per abilitare il reindirizzamento per le funzionalità di sicurezza, vedi Reindirizzamento degli account da [Microsoft Defender per Office 365](/microsoft-365/security/defender/microsoft-365-security-mdo-redirection) al Centro sicurezza Microsoft 365 per informazioni dettagliate.</span><span class="sxs-lookup"><span data-stu-id="b9534-116">To enable the redirection for security features, see [Redirecting accounts from Microsoft Defender for Office 365 to the Microsoft 365 security center](/microsoft-365/security/defender/microsoft-365-security-mdo-redirection) for details.</span></span>

## <a name="can-i-go-back-to-using-the-former-portal"></a><span data-ttu-id="b9534-117">È possibile tornare a usare il portale precedente?</span><span class="sxs-lookup"><span data-stu-id="b9534-117">Can I go back to using the former portal?</span></span>

<span data-ttu-id="b9534-118">Se qualcosa non funziona o se non è possibile completare un'operazione tramite il portale di Centro conformità Microsoft 365, è possibile disabilitare temporaneamente il reindirizzamento automatico per tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="b9534-118">If something isn't working for you or if there's anything you're unable to complete through the Microsoft 365 compliance center portal, you can temporarily disable the automatic redirection for all users.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b9534-119">Il Centro conformità Microsoft 365 è il portale di gestione sostitutivo per le soluzioni di conformità attualmente gestite nel Centro sicurezza e conformità Office 365 sicurezza.</span><span class="sxs-lookup"><span data-stu-id="b9534-119">The Microsoft 365 compliance center is the replacement management portal for compliance solutions currently managed in the Office 365 Security and Compliance center.</span></span> <span data-ttu-id="b9534-120">Tutte Microsoft 365 soluzioni di conformità verranno gestite esclusivamente nell'Centro conformità Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b9534-120">All Microsoft 365 compliance solutions will be managed solely in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="b9534-121">La disabilitazione del reindirizzamento al Centro conformità Microsoft 365 dovrebbe essere una soluzione a breve termine.</span><span class="sxs-lookup"><span data-stu-id="b9534-121">Disabling redirection to the Microsoft 365 compliance center should be a short-term solution.</span></span>

<span data-ttu-id="b9534-122">Per tornare al Centro sicurezza Office 365 conformità (protection.microsoft.com) per tutti gli utenti, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="b9534-122">To switch back to the Office 365 Security and Compliance center (protection.microsoft.com) for all users, complete the following steps:</span></span>

1. <span data-ttu-id="b9534-123">Accedere al Centro conformità Microsoft 365 [come](https://compliance.microsoft.com) amministratore globale o usando qualsiasi account con autorizzazioni di amministratore di conformità in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b9534-123">Sign in to the [Microsoft 365 compliance center](https://compliance.microsoft.com) as a global administrator or using any account with compliance administrator permissions in Azure Active directory.</span></span>
2. <span data-ttu-id="b9534-124">Passare **a** Impostazioni  >  **reindirizzamento del Centro conformità**.</span><span class="sxs-lookup"><span data-stu-id="b9534-124">Navigate to **Settings** > **Compliance center redirection**.</span></span>
3. <span data-ttu-id="b9534-125">Attivare o disattivare l'impostazione Reindirizzamento **automatico**.</span><span class="sxs-lookup"><span data-stu-id="b9534-125">Toggle the Automatic redirection setting to **Off**.</span></span>
4. <span data-ttu-id="b9534-126">Seleziona **Disattiva e** condividi feedback quando richiesto.</span><span class="sxs-lookup"><span data-stu-id="b9534-126">Select **Turn off** and share feedback when prompted.</span></span>

<span data-ttu-id="b9534-127">Una volta disabilitati, gli utenti non verranno più instradati a compliance.microsoft.com e verranno indirizzati al Centro sicurezza e conformità di Office 365 (protection.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="b9534-127">Once disabled, users will no longer be routed to compliance.microsoft.com and they will be directed to the Office 365 Security and Compliance center (protection.microsoft.com).</span></span> <span data-ttu-id="b9534-128">Questa impostazione può essere nuovamente abilitata in qualsiasi momento dagli amministratori globali o di conformità.</span><span class="sxs-lookup"><span data-stu-id="b9534-128">This setting can be enabled again at any time by Global or Compliance admins.</span></span>

## <a name="related-information"></a><span data-ttu-id="b9534-129">Informazioni correlate</span><span class="sxs-lookup"><span data-stu-id="b9534-129">Related information</span></span>

- [<span data-ttu-id="b9534-130">Centro conformità Microsoft 365 panoramica</span><span class="sxs-lookup"><span data-stu-id="b9534-130">Microsoft 365 compliance center overview</span></span>](/microsoft-365/compliance/microsoft-365-compliance-center)
