---
title: Informazioni sulle impostazioni dei profili AutoPilot
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: conceptual
f1_keywords:
- ZTDProfileSettings
- O365E_ZTDProfileSettings
- BCS365_ZTDProfileSettings
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 99bfbf81-e719-4630-9b0f-c187edfa1f8a
description: I profili AutoPilot consentono di controllare la modalità di installazione di Windows nei dispositivi degli utenti. I profili contengono impostazioni predefinite e facoltative come ignorare l'installazione di Cortana.
ms.openlocfilehash: 86f8718131f0a0b93e18e65e39e02e7d65aded1a
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578508"
---
# <a name="about-autopilot-profile-settings"></a><span data-ttu-id="6dde0-104">Informazioni sulle impostazioni dei profili AutoPilot</span><span class="sxs-lookup"><span data-stu-id="6dde0-104">About AutoPilot Profile settings</span></span>

## <a name="autopilot-profile-settings"></a><span data-ttu-id="6dde0-105">Impostazioni del profilo AutoPilot</span><span class="sxs-lookup"><span data-stu-id="6dde0-105">AutoPilot profile settings</span></span>

<span data-ttu-id="6dde0-106">Puoi usare i profili AutoPilot per controllare la modalità di installazione di Windows nei dispositivi degli utenti.</span><span class="sxs-lookup"><span data-stu-id="6dde0-106">You can use AutoPilot profiles to control how Windows is installed on user devices.</span></span> <span data-ttu-id="6dde0-107">I profili contengono le impostazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="6dde0-107">The profiles contain the following settings.</span></span>
  
 <span data-ttu-id="6dde0-108">**Funzionalità predefinite di AutoPilot (obbligatorie) impostate automaticamente:**</span><span class="sxs-lookup"><span data-stu-id="6dde0-108">**AutoPilot default features (required) that are set automatically:**</span></span>
  
|<span data-ttu-id="6dde0-109">**Impostazione**</span><span class="sxs-lookup"><span data-stu-id="6dde0-109">**Setting**</span></span>|<span data-ttu-id="6dde0-110">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="6dde0-110">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="6dde0-111">Ignorare la registrazione di Cortana, OneDrive e OEM</span><span class="sxs-lookup"><span data-stu-id="6dde0-111">Skip Cortana, OneDrive, and OEM registration</span></span>  <br/> |<span data-ttu-id="6dde0-112">Ignora l'installazione di app consumer come Cortana e OneDrive personale.</span><span class="sxs-lookup"><span data-stu-id="6dde0-112">Skips the installation of consumer apps like Cortana and personal OneDrive.</span></span> <span data-ttu-id="6dde0-113">L'utente del dispositivo può installarlo in un secondo momento, purché l'utente sia un amministratore locale nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="6dde0-113">The device user can install these later as long as the user is a local admin on the device.</span></span> <span data-ttu-id="6dde0-114">La registrazione originale del produttore viene ignorata perché il dispositivo verrà gestito da Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="6dde0-114">The original manufacturer registration is skipped because the device will be managed by Microsoft 365 Business Premium.</span></span>  <br/> |
|<span data-ttu-id="6dde0-115">Esperienza di accesso con il tuo marchio aziendale</span><span class="sxs-lookup"><span data-stu-id="6dde0-115">Sign in experience with your company brand</span></span>  <br/> |<span data-ttu-id="6dde0-116">Se l'azienda ha una pagina Aggiungi il marchio aziendale alla pagina di accesso a [Microsoft 365,](../admin/setup/customize-sign-in-page.md)l'utente del dispositivo riceverà tale esperienza all'accesso.</span><span class="sxs-lookup"><span data-stu-id="6dde0-116">If your company has a [Add your company branding to Microsoft 365 Sign In page](../admin/setup/customize-sign-in-page.md), the device user will get that experience when signing in.</span></span>  <br/> |
|<span data-ttu-id="6dde0-117">Registrazione automatica in MDM con account AAD configurati.</span><span class="sxs-lookup"><span data-stu-id="6dde0-117">MDM auto-enrollment with configured AAD accounts.</span></span>  <br/> |<span data-ttu-id="6dde0-118">L'identità utente verrà gestita da Azure Active Directory e gli utenti accederanno a Windows e Microsoft 365 con le credenziali di Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="6dde0-118">The user identity will be managed by Azure Active Directory, and users will sign in to Windows and Microsoft 365 with their Microsoft 365 Business Premium credentials.</span></span>  <br/> |
   
 <span data-ttu-id="6dde0-119">**Impostazioni facoltative:**</span><span class="sxs-lookup"><span data-stu-id="6dde0-119">**Optional settings:**</span></span>
  
|<span data-ttu-id="6dde0-120">**Impostazione**</span><span class="sxs-lookup"><span data-stu-id="6dde0-120">**Setting**</span></span>|<span data-ttu-id="6dde0-121">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="6dde0-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="6dde0-122">Ignora impostazioni della privacy (disattivato per impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="6dde0-122">Skip privacy settings (Off by default)</span></span>  <br/> |<span data-ttu-id="6dde0-123">Se questa opzione è impostata su **attivato**, l'utente del dispositivo non vedrà il contratto di licenza per il dispositivo e Windows al primo accesso.</span><span class="sxs-lookup"><span data-stu-id="6dde0-123">If this option is set to **On**, the device user will not see the license agreement for the device and Windows when he or she first signs in.</span></span>  <br/> |
|<span data-ttu-id="6dde0-124">Non consentire all'utente di diventare l'amministratore locale</span><span class="sxs-lookup"><span data-stu-id="6dde0-124">Don't allow the user to become the local admin</span></span>  <br/> |<span data-ttu-id="6dde0-125">Se questa opzione è impostata su **attivato**, l'utente del dispositivo non potrà installare le app personali, ad esempio Cortana.</span><span class="sxs-lookup"><span data-stu-id="6dde0-125">If this option is set to **On**, the device user will not be able to install any personal apps, such as Cortana.</span></span><br/> |
