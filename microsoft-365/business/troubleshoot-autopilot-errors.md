---
title: Risolvere i problemi relativi ai dispositivi AutoPilot
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
f1_keywords:
- ZTDTroubleshootDeviceErrors
- O365E_ZTDTroubleshootDeviceErrors
- BCS365_ZTDTroubleshootDeviceErrors
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
- seo-marvel-mar
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1f468690-530c-47ea-918f-fede24607c53
description: Informazioni su come risolvere i problemi che potrebbero essere visualizzati durante l'utilizzo dei file del dispositivo Autopilot in Microsoft 365 Business Premium.
ms.openlocfilehash: 0c0742e5bf17c85cedfb421cabfd87c0e2184ba5
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43635045"
---
# <a name="troubleshoot-autopilot-device-errors"></a><span data-ttu-id="d84e5-103">Risolvere i problemi relativi ai dispositivi AutoPilot</span><span class="sxs-lookup"><span data-stu-id="d84e5-103">Troubleshoot AutoPilot device errors</span></span>

## <a name="device-file-error-messages"></a><span data-ttu-id="d84e5-104">Messaggi di errore del file del dispositivo</span><span class="sxs-lookup"><span data-stu-id="d84e5-104">Device file error messages</span></span>

<span data-ttu-id="d84e5-105">Di seguito sono riportate alcune informazioni sugli errori che potrebbero verificarsi durante l'utilizzo dei file del dispositivo Autopilot in Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="d84e5-105">Here's info on some of the errors you might see while working with AutoPilot device files in Microsoft 365 Business Premium.</span></span> 
  
|<span data-ttu-id="d84e5-106">**Codice di errore**</span><span class="sxs-lookup"><span data-stu-id="d84e5-106">**Error code**</span></span>|<span data-ttu-id="d84e5-107">**Correzione da provare**</span><span class="sxs-lookup"><span data-stu-id="d84e5-107">**Fix to try**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d84e5-108">Corpo richiesta non valida</span><span class="sxs-lookup"><span data-stu-id="d84e5-108">Invalid request body</span></span>  <br/> |<span data-ttu-id="d84e5-109">Questo errore dovrebbe verificarsi raramente, se viene visualizzato questo errore, provare a eseguire di nuovo l'operazione.</span><span class="sxs-lookup"><span data-stu-id="d84e5-109">This error should happen rarely, if you see this error, try the operation again.</span></span>  <br/> |
|<span data-ttu-id="d84e5-110">Il valore hash hardware per un dispositivo non è corretto.</span><span class="sxs-lookup"><span data-stu-id="d84e5-110">Hardware hash value for a device isn't correct.</span></span>  <br/> |<span data-ttu-id="d84e5-111">Se viene visualizzato questo errore, significa che il valore specificato nel file CSV per l'hash hardware di un dispositivo non è corretto.</span><span class="sxs-lookup"><span data-stu-id="d84e5-111">If you see this error, it means that the value you provided in your CSV file for the hardware hash of one device isn't correct.</span></span> <span data-ttu-id="d84e5-112">Verificare innanzitutto che il valore sia stato digitato correttamente.</span><span class="sxs-lookup"><span data-stu-id="d84e5-112">First, verify that the value was typed correctly.</span></span> <span data-ttu-id="d84e5-113">Se si ritiene che il valore sia corretto, ma questo errore è ancora in corso, chiedere assistenza al fornitore dell'hardware.</span><span class="sxs-lookup"><span data-stu-id="d84e5-113">If you think that the value is correct, but this error is still happening, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="d84e5-114">Dispositivo assegnato a un altro tenant</span><span class="sxs-lookup"><span data-stu-id="d84e5-114">Device assigned to another tenant</span></span>  <br/> |<span data-ttu-id="d84e5-115">Se viene visualizzato questo errore, significa che il valore specificato nel file CSV sia per il numero di serie che per il codice Product Key di uno o più dispositivi non è corretto.</span><span class="sxs-lookup"><span data-stu-id="d84e5-115">If you see this error, it means that the value you provided in your CSV file for either the serial number or the product key of one or more devices isn't correct.</span></span> <span data-ttu-id="d84e5-116">Verificare innanzitutto che il valore sia stato digitato correttamente.</span><span class="sxs-lookup"><span data-stu-id="d84e5-116">First, verify that the value was typed correctly.</span></span> <span data-ttu-id="d84e5-117">Se si ritiene che il valore sia corretto, ma questo errore è ancora in corso, chiedere assistenza al fornitore dell'hardware.</span><span class="sxs-lookup"><span data-stu-id="d84e5-117">If you think that the value is correct, but this error is still happening, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="d84e5-118">Il file CSV contiene un numero di serie o un codice Product Key non valido</span><span class="sxs-lookup"><span data-stu-id="d84e5-118">The CSV file contains an invalid serial number or product key</span></span>  <br/> |<span data-ttu-id="d84e5-119">Se viene visualizzato questo errore, significa che il dispositivo che si sta tentando di registrare è già registrato da un'altra organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d84e5-119">If you see this error, it means that the device you are trying to register is already registered by another organization.</span></span> <span data-ttu-id="d84e5-120">Per correggere l'errore, chiedere assistenza al fornitore dell'hardware.</span><span class="sxs-lookup"><span data-stu-id="d84e5-120">To fix this error, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="d84e5-121">Questo dispositivo non è supportato per il programma di installazione tramite Autopilot</span><span class="sxs-lookup"><span data-stu-id="d84e5-121">This device is not supported for setup by using AutoPilot</span></span>  <br/> | <span data-ttu-id="d84e5-122">Questo errore indica che il dispositivo non soddisfa i requisiti di distribuzione del pilota automatico.</span><span class="sxs-lookup"><span data-stu-id="d84e5-122">This error means the device doesn't meet AutoPilot deployment requirements.</span></span> <span data-ttu-id="d84e5-123">I dispositivi devono soddisfare questi requisiti:</span><span class="sxs-lookup"><span data-stu-id="d84e5-123">Devices need to meet these requirements:</span></span>  <br/>  <span data-ttu-id="d84e5-124">Devono eseguire Windows 10 1703 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="d84e5-124">Windows 10, version 1703 or later.</span></span>  <br/>  <span data-ttu-id="d84e5-125">Nuovi dispositivi che non sono stati eseguiti tramite Windows.</span><span class="sxs-lookup"><span data-stu-id="d84e5-125">New devices that haven't been through Windows out-of-box experience.</span></span>  <br/> |
|<span data-ttu-id="d84e5-126">Dispositivo non trovato</span><span class="sxs-lookup"><span data-stu-id="d84e5-126">Device not found</span></span>  <br/> |<span data-ttu-id="d84e5-127">Questo errore indica che uno o più dispositivi nel file CSV non sono registrati nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d84e5-127">This error means that one or more devices in your CSV file isn't registered to your organization.</span></span> <span data-ttu-id="d84e5-128">Per risolvere il riguardo, chiedere assistenza al fornitore dell'hardware.</span><span class="sxs-lookup"><span data-stu-id="d84e5-128">To fix this, ask your hardware vendor for help.</span></span>  <br/> |
