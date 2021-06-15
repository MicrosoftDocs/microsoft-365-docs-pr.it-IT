---
title: Gestire la modalità di accesso ai documenti di Office nei dispositivi mobili
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
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
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: aa31319c-9196-48c9-a90b-4057e0494c7a
description: Informazioni sui criteri di protezione che consentono di gestire il modo in cui gli utenti accedono alle Office e ai file di lavoro dai dispositivi mobili.
ms.openlocfilehash: 7602b712f2dfc3ba369fd76979baaaa8d5da5c5c
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925280"
---
# <a name="manage-how-users-access-office-documents-on-mobile-devices"></a><span data-ttu-id="7939a-103">Gestire la modalità di accesso ai documenti di Office nei dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="7939a-103">Manage how users access Office documents on mobile devices</span></span>

<span data-ttu-id="7939a-104">Questo articolo si applica a Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="7939a-104">This article applies to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="7939a-105">Le impostazioni dei criteri che controllano la modalità di accesso degli utenti ai file di Office dai dispositivi mobili sono **disattivate** per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="7939a-105">Policy settings that control how users access Office files from their mobile devices are **Off** by default.</span></span> <span data-ttu-id="7939a-106">Ti consigliamo di accettare i valori predefiniti durante l'installazione per creare criteri di applicazione per Android, iOS e Windows 10 che si applicano a tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="7939a-106">We recommend that you accept the default values during setup to create application policies for Android, iOS, and Windows 10 that apply to all users.</span></span> <span data-ttu-id="7939a-107">È possibile creare altri criteri al termine dell'installazione.</span><span class="sxs-lookup"><span data-stu-id="7939a-107">You can create more policies after setup completes.</span></span> 
  
## <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a><span data-ttu-id="7939a-108">Impostazioni che controllano la modalità di accesso degli utenti ai file di Office nei dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="7939a-108">Settings that control how users access Office files on mobile devices</span></span>

<span data-ttu-id="7939a-109">Le impostazioni seguenti sono disponibili per la gestione della modalità di accesso degli utenti ai file di lavoro di Office:</span><span class="sxs-lookup"><span data-stu-id="7939a-109">The following settings are available to manage how users access Office work files:</span></span>

|<span data-ttu-id="7939a-110">Impostazione</span><span class="sxs-lookup"><span data-stu-id="7939a-110">Setting</span></span>  <br/> |<span data-ttu-id="7939a-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7939a-111">Description</span></span>  <br/> |
|:-----|:-----|
|<span data-ttu-id="7939a-112">Richiedi un PIN o l'impronta digitale per accedere alle app di Office</span><span class="sxs-lookup"><span data-stu-id="7939a-112">Require a PIN or fingerprint to access Office apps</span></span>  <br/> |<span data-ttu-id="7939a-113">Se questa impostazione è **attivata,** gli utenti devono fornire un'altra forma di autenticazione, oltre al nome utente e alla password, prima di poter usare le app Office sul dispositivo mobile.</span><span class="sxs-lookup"><span data-stu-id="7939a-113">If this setting is **On**, users must provide another form of authentication, in addition to their username and password, before they can use Office apps on their mobile device.</span></span>  <br/> |
|<span data-ttu-id="7939a-114">Reimposta il PIN dopo il numero di tentativi di accesso falliti seguente</span><span class="sxs-lookup"><span data-stu-id="7939a-114">Reset PIN when login fails this many times</span></span>  <br/> |<span data-ttu-id="7939a-115">Per impedire a un utente non autorizzato di indovinare casualmente un PIN, il PIN verrà reimpostato dopo il numero specificato di tentativi di immissione non riusciti.</span><span class="sxs-lookup"><span data-stu-id="7939a-115">To prevent an unauthorized user from randomly guessing a PIN, the PIN will reset after the number of wrong entries that you specify.</span></span>  <br/> |
|<span data-ttu-id="7939a-116">Richiedi agli utenti di accedere di nuovo dopo che le app di Office sono rimaste inattive per</span><span class="sxs-lookup"><span data-stu-id="7939a-116">Require users to sign in again after Office apps have been idle for</span></span>  <br/> |<span data-ttu-id="7939a-117">Questa impostazione determina per quanto tempo un utente può essere inattivo prima che venga richiesto di eseguire di nuovo l'accesso.</span><span class="sxs-lookup"><span data-stu-id="7939a-117">This setting determines how long a user can be idle before they're prompted to sign in again.</span></span>  <br/> |
|<span data-ttu-id="7939a-118">Nega l'accesso ai file di lavoro nei dispositivi jailbroken o rooted</span><span class="sxs-lookup"><span data-stu-id="7939a-118">Deny access to work files on jailbroken or rooted devices</span></span>  <br/> |<span data-ttu-id="7939a-119">È possibile che gli utenti esperti abbiano un dispositivo sottoposto a jailbreak o root.</span><span class="sxs-lookup"><span data-stu-id="7939a-119">Clever users may have a device that is jailbroken or rooted.</span></span> <span data-ttu-id="7939a-120">Ciò significa che l'utente può modificare il sistema operativo, in modo da rendere il dispositivo più vulnerabile al malware.</span><span class="sxs-lookup"><span data-stu-id="7939a-120">This means that the user can modify the operating system, which can make the device more susceptible to malware.</span></span> <span data-ttu-id="7939a-121">Questi dispositivi sono bloccati quando l'impostazione è **attivata**.</span><span class="sxs-lookup"><span data-stu-id="7939a-121">These devices are blocked when this setting is **On**.</span></span>  <br/> |
|<span data-ttu-id="7939a-122">Non consentire agli utenti di copiare contenuto da Office app personali</span><span class="sxs-lookup"><span data-stu-id="7939a-122">Don't allow users to copy content from Office apps into personal apps</span></span>  <br/> |<span data-ttu-id="7939a-123">Quando l'impostazione è **attivata,** l'utente non può copiare le informazioni di un file di lavoro in un file personale.</span><span class="sxs-lookup"><span data-stu-id="7939a-123">When the setting is **On**, the user can't copy information in a work file to a personal file.</span></span> <span data-ttu-id="7939a-124">Se l'impostazione è **Disattivata,** l'utente può copiare le informazioni da un file di lavoro a un'app personale o a un account personale.</span><span class="sxs-lookup"><span data-stu-id="7939a-124">If the setting is **Off**, the user can copy information from a work file to a personal app or personal account.</span></span>  <br/> |
   

