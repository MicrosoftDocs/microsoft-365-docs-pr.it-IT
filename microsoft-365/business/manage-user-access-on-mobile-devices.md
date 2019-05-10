---
title: Gestire la modalità di accesso ai documenti di Office nei dispositivi mobili
ms.author: sirkkuw
author: sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: conceptual
f1_keywords:
- O365E_BCSSetup4OfficeMobile
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: aa31319c-9196-48c9-a90b-4057e0494c7a
description: Informazioni sui criteri di protezione che consentono di accedere in modo sicuro alle app di Office dai dispositivi mobili.
ms.openlocfilehash: b49ec33f4899a25f92ffd9d7a25d3e435016749e
ms.sourcegitcommit: db1dfb2df2c2f7beced3b57bc772d106c189e88a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2019
ms.locfileid: "33660337"
---
# <a name="manage-how-users-access-office-documents-on-mobile-devices"></a><span data-ttu-id="ba269-103">Gestire la modalità di accesso ai documenti di Office nei dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="ba269-103">Manage how users access Office documents on mobile devices</span></span>

 <span data-ttu-id="ba269-p101">Le impostazioni dei criteri che controllano la modalità di accesso degli utenti ai file di Office dai dispositivi mobili sono **disattivate** per impostazione predefinita. È consigliabile accettare i valori predefiniti durante l'installazione per creare criteri di applicazione per Android, iOS e Windows 10 applicabili a tutti gli utenti. È possibile creare altri criteri al termine dell'installazione.</span><span class="sxs-lookup"><span data-stu-id="ba269-p101">Policy settings that control how users access Office files from their mobile devices are **Off** by default. We recommend you accept the default values during setup to create application policies for Android, iOS, and Windows 10 that apply to all users. You can create more policies after setup completes.</span></span> 
  
## <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a><span data-ttu-id="ba269-107">Impostazioni che controllano la modalità di accesso degli utenti ai file di Office nei dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="ba269-107">Settings that control how users access Office files on mobile devices</span></span>

<span data-ttu-id="ba269-108">Le impostazioni seguenti sono disponibili per la gestione della modalità di accesso degli utenti ai file di lavoro di Office:</span><span class="sxs-lookup"><span data-stu-id="ba269-108">The following settings are available to manage how users access Office work files:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="ba269-109">Impostazione</span><span class="sxs-lookup"><span data-stu-id="ba269-109">Setting</span></span>  <br/> |<span data-ttu-id="ba269-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ba269-110">Description</span></span>  <br/> |
|<span data-ttu-id="ba269-111">Richiedi un PIN o l'impronta digitale per accedere alle app di Office</span><span class="sxs-lookup"><span data-stu-id="ba269-111">Require a PIN or fingerprint to access Office apps</span></span>  <br/> |<span data-ttu-id="ba269-112">Se questa impostazione è **attivata**, gli utenti devono fornire un'altra forma di autenticazione, oltre al nome utente e alla password, prima di potere usare le app di Office nel dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="ba269-112">If this settings is **On** users have to provide another form of authentication, in addition to their username and password, before they can use Office apps on their mobile device.</span></span>  <br/> |
|<span data-ttu-id="ba269-113">Reimposta il PIN dopo il numero di tentativi di accesso falliti seguente</span><span class="sxs-lookup"><span data-stu-id="ba269-113">Reset PIN when login fails this many times</span></span>  <br/> |<span data-ttu-id="ba269-114">Per impedire a un utente non autorizzato di indovinare casualmente un PIN, il PIN verrà reimpostato dopo il numero specificato di tentativi di immissione non riusciti.</span><span class="sxs-lookup"><span data-stu-id="ba269-114">To prevent an unauthorized user from randomly guessing a PIN, the PIN will reset after the number of wrong entries that you specify.</span></span>  <br/> |
|<span data-ttu-id="ba269-115">Richiedi agli utenti di accedere di nuovo dopo che le app di Office sono rimaste inattive per</span><span class="sxs-lookup"><span data-stu-id="ba269-115">Require users to sign in again after Office apps have been idle for</span></span>  <br/> |<span data-ttu-id="ba269-116">Questa impostazione determina per quanto tempo un utente può rimanere inattivo prima che venga richiesta la ripetizione dell'accesso.</span><span class="sxs-lookup"><span data-stu-id="ba269-116">This setting determines how long a user can be idle before they are prompted to sign in again.</span></span>  <br/> |
|<span data-ttu-id="ba269-117">Nega l'accesso ai file di lavoro nei dispositivi jailbroken o rooted</span><span class="sxs-lookup"><span data-stu-id="ba269-117">Deny access to work files on jailbroken or rooted devices</span></span>  <br/> |<span data-ttu-id="ba269-p102">È possibile che gli utenti esperti abbiano un dispositivo sottoposto a jailbreak o root. L'utente può quindi modificare il sistema operativo, rendendo il dispositivo più vulnerabile a malware. Questi dispositivi sono bloccati quando l'impostazione è **attivata**.  </span><span class="sxs-lookup"><span data-stu-id="ba269-p102">Clever users may have a device that is jailbroken or rooted. This means that the user can modify the operating system, which can make the device more subject to malware. These devices are blocked when this setting is **On**.  </span></span><br/> |
|<span data-ttu-id="ba269-121">Non consentire agli utenti di copiare il contenuto da app di Office in app personali</span><span class="sxs-lookup"><span data-stu-id="ba269-121">Don't allow users to copy content from Office apps into personal apps</span></span>  <br/> |<span data-ttu-id="ba269-122">Quando l'impostazione è **attiva**, l'utente non è in grado di copiare le informazioni in un file di lavoro in un file personale.</span><span class="sxs-lookup"><span data-stu-id="ba269-122">When the setting is **On**, the user can't copy information in a work file to a personal file.</span></span> <span data-ttu-id="ba269-123">Se l'impostazione è \*\*\*\* disattivata, l'utente può copiare informazioni da un file di lavoro a un'app personale o a un account personale.</span><span class="sxs-lookup"><span data-stu-id="ba269-123">If the setting is **Off**, the user can copy information from a work file to a personal app or personal account.</span></span>  <br/> |
   

