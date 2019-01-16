---
title: Informazioni sulle impostazioni dei profili AutoPilot
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: overview
f1_keywords:
- ZTDProfileSettings
- O365E_ZTDProfileSettings
- BCS365_ZTDProfileSettings
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_O365
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 99bfbf81-e719-4630-9b0f-c187edfa1f8a
description: Profili autoPilot consentono di controllare la modalità Windows Ottiene installazione nei dispositivi utente. I profili contengono predefinito e impostazioni facoltative come annullare l'installazione Cortana.
ms.openlocfilehash: 5440286f1363780c87ab60514584c4addfeea0b2
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2019
ms.locfileid: "26868305"
---
# <a name="about-autopilot-profile-settings"></a><span data-ttu-id="b6d46-104">Informazioni sulle impostazioni dei profili AutoPilot</span><span class="sxs-lookup"><span data-stu-id="b6d46-104">About AutoPilot Profile settings</span></span>

## <a name="autopilot-profile-settings"></a><span data-ttu-id="b6d46-105">Impostazioni dei profili AutoPilot</span><span class="sxs-lookup"><span data-stu-id="b6d46-105">AutoPilot profile settings</span></span>

<span data-ttu-id="b6d46-p102">È possibile controllare come Windows Ottiene installato nei dispositivi utente mediante i profili AutoPilot. I profili contengono le impostazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="b6d46-p102">You can control how Windows gets installed on user devices by using the AutoPilot profiles. The profiles contain the following settings.</span></span>
  
 <span data-ttu-id="b6d46-108">**AutoPilot le funzionalità predefinite (obbligatoria) che vengono impostate automaticamente:**</span><span class="sxs-lookup"><span data-stu-id="b6d46-108">**AutoPilot default features (required) that are set automatically:**</span></span>
  
|<span data-ttu-id="b6d46-109">**Impostazione**</span><span class="sxs-lookup"><span data-stu-id="b6d46-109">**Setting**</span></span>|<span data-ttu-id="b6d46-110">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="b6d46-110">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b6d46-111">Ignora Cortana, OneDrive e la registrazione OEM</span><span class="sxs-lookup"><span data-stu-id="b6d46-111">Skip Cortana, OneDrive and OEM registration</span></span>  <br/> |<span data-ttu-id="b6d46-p103">Ignora l'installazione delle App consumer come Cortana e OneDrive personale. Utente del dispositivo può installare questi successive purché è un amministratore locale nel dispositivo. Registrazione produttore originale viene ignorata in quanto il dispositivo verrà gestito da Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="b6d46-p103">Skips the installation of consumer apps like Cortana and personal OneDrive. The device user can install these later as long as he or she is a local admin on the device. The original manufacturer registration is skipped because the device will be managed by Microsoft 365 Business.</span></span>  <br/> |
|<span data-ttu-id="b6d46-115">Esperienza di accesso con il tuo marchio aziendale</span><span class="sxs-lookup"><span data-stu-id="b6d46-115">Sign in experience with your company brand</span></span>  <br/> |<span data-ttu-id="b6d46-116">Se la società dispone di una [personalizzazione in aggiunta all'azienda a Office 365 pagina di accesso](https://support.office.com/article/a1229cdb-ce19-4da5-90c7-2b9b146aef0a), l'utente dispositivo otterrà tale esperienza durante l'accesso.</span><span class="sxs-lookup"><span data-stu-id="b6d46-116">If your company has a [Add your company branding to Office 365 Sign In page](https://support.office.com/article/a1229cdb-ce19-4da5-90c7-2b9b146aef0a), the device user will get that experience when signing in.</span></span>  <br/> |
|<span data-ttu-id="b6d46-117">Registrazione automatica in MDM con account AAD configurati.</span><span class="sxs-lookup"><span data-stu-id="b6d46-117">MDM auto-enrollment with configured AAD accounts.</span></span>  <br/> |<span data-ttu-id="b6d46-118">L'identità dell'utente verrà gestita da Azure Active Directory e l'utente eseguirà l'accesso a Windows e Office 365 con le proprie credenziali di Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="b6d46-118">The user identity will be managed by Azure Active directory, and the users will sign into Windows and Office 365 with their Microsoft 365 Business credentials.</span></span>  <br/> |
   
 <span data-ttu-id="b6d46-119">**Impostazioni facoltative:**</span><span class="sxs-lookup"><span data-stu-id="b6d46-119">**Optional settings:**</span></span>
  
|<span data-ttu-id="b6d46-120">**Impostazione**</span><span class="sxs-lookup"><span data-stu-id="b6d46-120">**Setting**</span></span>|<span data-ttu-id="b6d46-121">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="b6d46-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b6d46-122">Ignora impostazioni della privacy (disattivato per impostazione predefinita)</span><span class="sxs-lookup"><span data-stu-id="b6d46-122">Skip privacy settings (Off by default)</span></span>  <br/> |<span data-ttu-id="b6d46-123">Se questa opzione è impostata su **attivato**, l'utente del dispositivo non vedrà il contratto di licenza per il dispositivo e Windows al primo accesso.</span><span class="sxs-lookup"><span data-stu-id="b6d46-123">If this option is set to **On**, the device user will not see the license agreement for the device and Windows when he or she first signs in.</span></span>  <br/> |
|<span data-ttu-id="b6d46-124">Non consentire all'utente di diventare l'amministratore locale</span><span class="sxs-lookup"><span data-stu-id="b6d46-124">Don't allow the user to become the local admin</span></span>  <br/> |<span data-ttu-id="b6d46-125">Se questa opzione è impostata su **attivato**, l'utente del dispositivo non potrà installare le app personali, ad esempio Cortana.</span><span class="sxs-lookup"><span data-stu-id="b6d46-125">If this option is set to **On**, the device user will not be able to install any personal apps, such as Cortana.</span></span>  <br/> |
   
