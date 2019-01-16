---
title: Eseguire la risoluzione dei problemi del dispositivo AutoPilot
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: troubleshooting
f1_keywords:
- ZTDTroubleshootDeviceErrors
- O365E_ZTDTroubleshootDeviceErrors
- BCS365_ZTDTroubleshootDeviceErrors
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1f468690-530c-47ea-918f-fede24607c53
description: Informazioni su come risolvere gli errori file AutoPilot dispositivo.
ms.openlocfilehash: 9b8d8ab424dd3189ff5c228dab8f5c513ff5dafc
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2019
ms.locfileid: "26868459"
---
# <a name="troubleshoot-autopilot-device-errors"></a><span data-ttu-id="afb3d-103">Eseguire la risoluzione dei problemi del dispositivo AutoPilot</span><span class="sxs-lookup"><span data-stu-id="afb3d-103">Troubleshoot AutoPilot device errors</span></span>

## <a name="device-file-error-messages"></a><span data-ttu-id="afb3d-104">Messaggi di errore file dispositivo</span><span class="sxs-lookup"><span data-stu-id="afb3d-104">Device file error messages</span></span>

<span data-ttu-id="afb3d-105">Info Ecco su alcuni degli errori che potrebbero venire visualizzati durante l'utilizzo dei file dei dispositivi AutoPilot in Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="afb3d-105">Here's info on some of the errors you might see while working with AutoPilot device files in Microsoft 365 Business.</span></span> 
  
|<span data-ttu-id="afb3d-106">**Codice di errore**</span><span class="sxs-lookup"><span data-stu-id="afb3d-106">**Error code**</span></span>|<span data-ttu-id="afb3d-107">**Correggere i tentativi**</span><span class="sxs-lookup"><span data-stu-id="afb3d-107">**Fix to try**</span></span>|
|:-----|:-----|
|<span data-ttu-id="afb3d-108">Corpo della richiesta non valida</span><span class="sxs-lookup"><span data-stu-id="afb3d-108">Invalid request body</span></span>  <br/> |<span data-ttu-id="afb3d-109">Questo errore dovrebbe avvenire raramente, se viene visualizzato questo errore, ritentare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="afb3d-109">This error should happen rarely, if you see this error, try the operation again.</span></span>  <br/> |
|<span data-ttu-id="afb3d-110">Il valore hash hardware per un dispositivo non è corretto.</span><span class="sxs-lookup"><span data-stu-id="afb3d-110">Hardware hash value for a device isn't correct.</span></span>  <br/> |<span data-ttu-id="afb3d-p101">Se viene visualizzato questo errore, significa che il valore specificato nel file CSV per l'hash hardware di un dispositivo non è corretto. Innanzitutto, verificare che il valore è stato digitato correttamente. Se si ritiene che il valore sia corretto, ma questo errore si verifica ancora, rivolgersi al fornitore dell'hardware del.</span><span class="sxs-lookup"><span data-stu-id="afb3d-p101">If you see this error, it means that the value you provided in your CSV file for the hardware hash of one device isn't correct. First, verify that the value was typed correctly. If you think that the value is correct, but this error is still happening, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="afb3d-114">Dispositivo assegnato a un altro tenant</span><span class="sxs-lookup"><span data-stu-id="afb3d-114">Device assigned to another tenant</span></span>  <br/> |<span data-ttu-id="afb3d-p102">Se viene visualizzato questo errore, significa che il valore specificato nel file CSV per il numero di serie o il codice product key di uno o più dispositivi non è corretto. Innanzitutto, verificare che il valore è stato digitato correttamente. Se si ritiene che il valore sia corretto, ma questo errore si verifica ancora, rivolgersi al fornitore dell'hardware del.</span><span class="sxs-lookup"><span data-stu-id="afb3d-p102">If you see this error, it means that the value you provided in your CSV file for either the serial number or the product key of one or more devices isn't correct. First, verify that the value was typed correctly. If you think that the value is correct, but this error is still happening, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="afb3d-118">Il file CSV contiene un numero di serie non valido o il codice product key</span><span class="sxs-lookup"><span data-stu-id="afb3d-118">The CSV file contains an invalid serial number or product key</span></span>  <br/> |<span data-ttu-id="afb3d-p103">Se viene visualizzato questo errore indica che il dispositivo che è durante il tentativo di effettuare la registrazione è già registrato da un'altra organizzazione. Per risolvere questo problema, rivolgersi al fornitore dell'hardware del.</span><span class="sxs-lookup"><span data-stu-id="afb3d-p103">If you see this error it means that the device you are tyring to register is already registered by an other organization. To fix this, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="afb3d-121">Il dispositivo non è supportato per l'installazione utilizzando AutoPilot</span><span class="sxs-lookup"><span data-stu-id="afb3d-121">This device is not supported for setup by using AutoPilot</span></span>  <br/> | <span data-ttu-id="afb3d-p104">Questo errore indica che il dispositivo non soddisfa i requisiti di distribuzione AutoPilot. I dispositivi devono soddisfare questi requisiti:</span><span class="sxs-lookup"><span data-stu-id="afb3d-p104">This error means the device does not meet AutoPilot deployment requirements. Devices need to meet these requirements:</span></span>  <br/>  <span data-ttu-id="afb3d-124">Devono eseguire Windows 10 1703 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="afb3d-124">Windows 10, version 1703 or later.</span></span>  <br/>  <span data-ttu-id="afb3d-125">Devono essere nuovi dispositivi per i quali non è stata eseguita la Configurazione guidata di Windows.</span><span class="sxs-lookup"><span data-stu-id="afb3d-125">New devices that have not been through Windows out-of-box experience.</span></span>  <br/> |
|<span data-ttu-id="afb3d-126">Dispositivo non trovato</span><span class="sxs-lookup"><span data-stu-id="afb3d-126">Device not found</span></span>  <br/> |<span data-ttu-id="afb3d-p105">Questo errore indica che non è registrato uno o più dispositivi nel file CSV per l'organizzazione. Per risolvere questo problema, rivolgersi al fornitore dell'hardware del.</span><span class="sxs-lookup"><span data-stu-id="afb3d-p105">This error means that one or more devices in your CSV file is not registered to your organization. To fix this, ask your hardware vendor for help.</span></span>  <br/> |
   
