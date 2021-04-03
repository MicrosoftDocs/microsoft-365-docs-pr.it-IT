---
title: Risolvere i problemi relativi ai dispositivi AutoPilot
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1f468690-530c-47ea-918f-fede24607c53
description: Informazioni su come risolvere gli errori che potrebbero verificarsi durante l'utilizzo dei file del dispositivo AutoPilot in Microsoft 365 Business Premium.
ms.openlocfilehash: 1078ab74b07952e4bb565555a081b98ecce9db5c
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578088"
---
# <a name="troubleshoot-autopilot-device-errors"></a><span data-ttu-id="144b3-103">Risolvere i problemi relativi ai dispositivi AutoPilot</span><span class="sxs-lookup"><span data-stu-id="144b3-103">Troubleshoot AutoPilot device errors</span></span>

## <a name="device-file-error-messages"></a><span data-ttu-id="144b3-104">Messaggi di errore del file del dispositivo</span><span class="sxs-lookup"><span data-stu-id="144b3-104">Device file error messages</span></span>

<span data-ttu-id="144b3-105">Ecco informazioni su alcuni degli errori che potresti visualizzare quando lavori con i file del dispositivo AutoPilot in Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="144b3-105">Here's info on some of the errors you might see while working with AutoPilot device files in Microsoft 365 Business Premium.</span></span> 
  
|<span data-ttu-id="144b3-106">**Codice di errore**</span><span class="sxs-lookup"><span data-stu-id="144b3-106">**Error code**</span></span>|<span data-ttu-id="144b3-107">**Correzione da provare**</span><span class="sxs-lookup"><span data-stu-id="144b3-107">**Fix to try**</span></span>|
|:-----|:-----|
|<span data-ttu-id="144b3-108">Corpo della richiesta non valido</span><span class="sxs-lookup"><span data-stu-id="144b3-108">Invalid request body</span></span>  <br/> |<span data-ttu-id="144b3-109">Questo errore dovrebbe verificarsi raramente, se viene visualizzato questo errore, provare di nuovo l'operazione.</span><span class="sxs-lookup"><span data-stu-id="144b3-109">This error should happen rarely, if you see this error, try the operation again.</span></span>  <br/> |
|<span data-ttu-id="144b3-110">Il valore hash hardware per un dispositivo non è corretto.</span><span class="sxs-lookup"><span data-stu-id="144b3-110">Hardware hash value for a device isn't correct.</span></span>  <br/> |<span data-ttu-id="144b3-111">Se viene visualizzato questo errore, significa che il valore specificato nel file CSV per l'hash hardware di un dispositivo non è corretto.</span><span class="sxs-lookup"><span data-stu-id="144b3-111">If you see this error, it means that the value you provided in your CSV file for the hardware hash of one device isn't correct.</span></span> <span data-ttu-id="144b3-112">Verificare innanzitutto che il valore sia stato digitato correttamente.</span><span class="sxs-lookup"><span data-stu-id="144b3-112">First, verify that the value was typed correctly.</span></span> <span data-ttu-id="144b3-113">Se si pensa che il valore sia corretto, ma l'errore continua a verificarsi, chiedere assistenza al fornitore dell'hardware.</span><span class="sxs-lookup"><span data-stu-id="144b3-113">If you think that the value is correct, but this error is still happening, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="144b3-114">Dispositivo assegnato a un altro tenant</span><span class="sxs-lookup"><span data-stu-id="144b3-114">Device assigned to another tenant</span></span>  <br/> |<span data-ttu-id="144b3-115">Se viene visualizzato questo errore, significa che il valore specificato nel file CSV per il numero di serie o il codice Product Key di uno o più dispositivi non è corretto.</span><span class="sxs-lookup"><span data-stu-id="144b3-115">If you see this error, it means that the value you provided in your CSV file for either the serial number or the product key of one or more devices isn't correct.</span></span> <span data-ttu-id="144b3-116">Verificare innanzitutto che il valore sia stato digitato correttamente.</span><span class="sxs-lookup"><span data-stu-id="144b3-116">First, verify that the value was typed correctly.</span></span> <span data-ttu-id="144b3-117">Se si pensa che il valore sia corretto, ma l'errore continua a verificarsi, chiedere assistenza al fornitore dell'hardware.</span><span class="sxs-lookup"><span data-stu-id="144b3-117">If you think that the value is correct, but this error is still happening, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="144b3-118">Il file CSV contiene un numero di serie o un codice Product Key non valido</span><span class="sxs-lookup"><span data-stu-id="144b3-118">The CSV file contains an invalid serial number or product key</span></span>  <br/> |<span data-ttu-id="144b3-119">Se viene visualizzato questo errore, significa che il dispositivo che si sta tentando di registrare è già registrato da un'altra organizzazione.</span><span class="sxs-lookup"><span data-stu-id="144b3-119">If you see this error, it means that the device you are trying to register is already registered by another organization.</span></span> <span data-ttu-id="144b3-120">Per correggere l'errore, chiedere assistenza al fornitore dell'hardware.</span><span class="sxs-lookup"><span data-stu-id="144b3-120">To fix this error, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="144b3-121">Questo dispositivo non è supportato per la configurazione tramite AutoPilot</span><span class="sxs-lookup"><span data-stu-id="144b3-121">This device is not supported for setup by using AutoPilot</span></span>  <br/> | <span data-ttu-id="144b3-122">Questo errore indica che il dispositivo non soddisfa i requisiti di distribuzione di AutoPilot.</span><span class="sxs-lookup"><span data-stu-id="144b3-122">This error means the device doesn't meet AutoPilot deployment requirements.</span></span> <span data-ttu-id="144b3-123">I dispositivi devono soddisfare questi requisiti:</span><span class="sxs-lookup"><span data-stu-id="144b3-123">Devices need to meet these requirements:</span></span>  <br/>  <span data-ttu-id="144b3-124">Devono eseguire Windows 10 1703 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="144b3-124">Windows 10, version 1703 or later.</span></span>  <br/>  <span data-ttu-id="144b3-125">Nuovi dispositivi che non hanno mai visto l'esperienza di Windows.</span><span class="sxs-lookup"><span data-stu-id="144b3-125">New devices that haven't been through Windows out-of-box experience.</span></span>  <br/> |
|<span data-ttu-id="144b3-126">Dispositivo non trovato</span><span class="sxs-lookup"><span data-stu-id="144b3-126">Device not found</span></span>  <br/> |<span data-ttu-id="144b3-127">Questo errore indica che uno o più dispositivi nel file CSV non sono registrati nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="144b3-127">This error means that one or more devices in your CSV file isn't registered to your organization.</span></span> <span data-ttu-id="144b3-128">Per risolvere il problema, chiedere assistenza al fornitore dell'hardware.</span><span class="sxs-lookup"><span data-stu-id="144b3-128">To fix this, ask your hardware vendor for help.</span></span>  <br/> |
