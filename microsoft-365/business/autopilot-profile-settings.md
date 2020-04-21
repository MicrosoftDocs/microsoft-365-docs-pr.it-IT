---
title: Informazioni sulle impostazioni dei profili AutoPilot
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 99bfbf81-e719-4630-9b0f-c187edfa1f8a
description: I profili Autopilot consentono di controllare il modo in cui viene installato Windows nei dispositivi utente. I profili contengono impostazioni predefinite e facoltative come l'installazione di Skip Cortana.
ms.openlocfilehash: 5c2ec3f4c3e0ebc4ea545d11f819c897f414ad52
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43627415"
---
# <a name="about-autopilot-profile-settings"></a><span data-ttu-id="43c83-104">Informazioni sulle impostazioni dei profili AutoPilot</span><span class="sxs-lookup"><span data-stu-id="43c83-104">About AutoPilot Profile settings</span></span>

## <a name="autopilot-profile-settings"></a><span data-ttu-id="43c83-105">Impostazioni del profilo Autopilot</span><span class="sxs-lookup"><span data-stu-id="43c83-105">AutoPilot profile settings</span></span>

<span data-ttu-id="43c83-106">È possibile utilizzare i profili Autopilot per controllare la modalità di installazione di Windows nei dispositivi utente.</span><span class="sxs-lookup"><span data-stu-id="43c83-106">You can use AutoPilot profiles to control how Windows is installed on user devices.</span></span> <span data-ttu-id="43c83-107">I profili contengono le impostazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="43c83-107">The profiles contain the following settings.</span></span>
  
 <span data-ttu-id="43c83-108">**Funzionalità predefinite del pilota automatico (obbligatorio) impostate automaticamente:**</span><span class="sxs-lookup"><span data-stu-id="43c83-108">**AutoPilot default features (required) that are set automatically:**</span></span>
  
|<span data-ttu-id="43c83-109">**Impostazione**</span><span class="sxs-lookup"><span data-stu-id="43c83-109">**Setting**</span></span>|<span data-ttu-id="43c83-110">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="43c83-110">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="43c83-111">Ignorare la registrazione di Cortana, OneDrive e OEM</span><span class="sxs-lookup"><span data-stu-id="43c83-111">Skip Cortana, OneDrive, and OEM registration</span></span>  <br/> |<span data-ttu-id="43c83-112">Ignora l'installazione delle app consumer come Cortana e Personal OneDrive.</span><span class="sxs-lookup"><span data-stu-id="43c83-112">Skips the installation of consumer apps like Cortana and personal OneDrive.</span></span> <span data-ttu-id="43c83-113">L'utente del dispositivo può installarli in un secondo momento, purché l'utente sia un amministratore locale del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="43c83-113">The device user can install these later as long as the user is a local admin on the device.</span></span> <span data-ttu-id="43c83-114">La registrazione del produttore originale viene ignorata perché il dispositivo sarà gestito da Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="43c83-114">The original manufacturer registration is skipped because the device will be managed by Microsoft 365 Business Premium.</span></span>  <br/> |
|<span data-ttu-id="43c83-115">Esperienza di accesso con il tuo marchio aziendale</span><span class="sxs-lookup"><span data-stu-id="43c83-115">Sign in experience with your company brand</span></span>  <br/> |<span data-ttu-id="43c83-116">Se l'azienda dispone [di un marchio Aggiungi la propria società alla pagina di accesso a Microsoft 365](https://support.office.com/article/a1229cdb-ce19-4da5-90c7-2b9b146aef0a), l'utente del dispositivo otterrà quell'esperienza al momento dell'accesso.</span><span class="sxs-lookup"><span data-stu-id="43c83-116">If your company has a [Add your company branding to Microsoft 365 Sign In page](https://support.office.com/article/a1229cdb-ce19-4da5-90c7-2b9b146aef0a), the device user will get that experience when signing in.</span></span>  <br/> |
|<span data-ttu-id="43c83-117">Registrazione automatica in MDM con account AAD configurati.</span><span class="sxs-lookup"><span data-stu-id="43c83-117">MDM auto-enrollment with configured AAD accounts.</span></span>  <br/> |<span data-ttu-id="43c83-118">L'identità dell'utente verrà gestita da Azure Active Directory e gli utenti accederanno a Windows e Microsoft 365 con le credenziali di Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="43c83-118">The user identity will be managed by Azure Active Directory, and users will sign in to Windows and Microsoft 365 with their Microsoft 365 Business Premium credentials.</span></span>  <br/> |
   
 <span data-ttu-id="43c83-119">**Impostazioni facoltative:**</span><span class="sxs-lookup"><span data-stu-id="43c83-119">**Optional settings:**</span></span>
  
|<span data-ttu-id="43c83-120">**Impostazione**</span><span class="sxs-lookup"><span data-stu-id="43c83-120">**Setting**</span></span>|<span data-ttu-id="43c83-121">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="43c83-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="43c83-122">Ignora impostazioni della privacy (disattivato per impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="43c83-122">Skip privacy settings (Off by default)</span></span>  <br/> |<span data-ttu-id="43c83-123">Se questa opzione è impostata su **attivato**, l'utente del dispositivo non vedrà il contratto di licenza per il dispositivo e Windows al primo accesso.</span><span class="sxs-lookup"><span data-stu-id="43c83-123">If this option is set to **On**, the device user will not see the license agreement for the device and Windows when he or she first signs in.</span></span>  <br/> |
|<span data-ttu-id="43c83-124">Non consentire all'utente di diventare l'amministratore locale</span><span class="sxs-lookup"><span data-stu-id="43c83-124">Don't allow the user to become the local admin</span></span>  <br/> |<span data-ttu-id="43c83-125">Se questa opzione è impostata su **attivato**, l'utente del dispositivo non potrà installare le app personali, ad esempio Cortana.</span><span class="sxs-lookup"><span data-stu-id="43c83-125">If this option is set to **On**, the device user will not be able to install any personal apps, such as Cortana.</span></span><br/> |
   
