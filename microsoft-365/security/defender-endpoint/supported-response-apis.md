---
title: API di risposta di Microsoft Defender for Endpoint supportate
description: Informazioni sulle specifiche chiamate API di Microsoft Defender for Endpoint correlate alla risposta.
keywords: api di risposta, api del grafico, api supportate, attore, avvisi, dispositivo, utente, dominio, ip, file
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.openlocfilehash: 36ed1f624fda7ae413ffbbf807925cf00e0a23ca
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933770"
---
# <a name="supported-microsoft-defender-for-endpoint-query-apis"></a><span data-ttu-id="b8623-104">API di query di Microsoft Defender for Endpoint supportate</span><span class="sxs-lookup"><span data-stu-id="b8623-104">Supported Microsoft Defender for Endpoint query APIs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="b8623-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="b8623-105">**Applies to:**</span></span>
- [<span data-ttu-id="b8623-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="b8623-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> [!TIP]
> <span data-ttu-id="b8623-107">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="b8623-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b8623-108">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="b8623-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-supported-response-apis-abovefoldlink) 

<span data-ttu-id="b8623-109">Informazioni sulle chiamate API correlate alla risposta supportate che puoi eseguire e dettagli quali le intestazioni di richiesta necessarie e la risposta prevista dalle chiamate.</span><span class="sxs-lookup"><span data-stu-id="b8623-109">Learn about the supported response-related API calls you can run and details such as the required request headers, and expected response from the calls.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="b8623-110">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="b8623-110">In this section</span></span>
<span data-ttu-id="b8623-111">Argomento</span><span class="sxs-lookup"><span data-stu-id="b8623-111">Topic</span></span> | <span data-ttu-id="b8623-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b8623-112">Description</span></span>
:---|:---
<span data-ttu-id="b8623-113">Raccogliere un pacchetto di indagini</span><span class="sxs-lookup"><span data-stu-id="b8623-113">Collect investigation package</span></span> | <span data-ttu-id="b8623-114">Esegui questa API per raccogliere un pacchetto di indagine da un dispositivo.</span><span class="sxs-lookup"><span data-stu-id="b8623-114">Run this API to collect an investigation package from a device.</span></span>
<span data-ttu-id="b8623-115">Isola dispositivo</span><span class="sxs-lookup"><span data-stu-id="b8623-115">Isolate device</span></span> | <span data-ttu-id="b8623-116">Esegui questa API per isolare un dispositivo dalla rete.</span><span class="sxs-lookup"><span data-stu-id="b8623-116">Run this API to isolate a device from the network.</span></span>
<span data-ttu-id="b8623-117">Dispositivo unisolate</span><span class="sxs-lookup"><span data-stu-id="b8623-117">Unisolate device</span></span> | <span data-ttu-id="b8623-118">Rimuovere un dispositivo dall'isolamento.</span><span class="sxs-lookup"><span data-stu-id="b8623-118">Remove a device from isolation.</span></span> 
<span data-ttu-id="b8623-119">Limitare l'esecuzione del codice</span><span class="sxs-lookup"><span data-stu-id="b8623-119">Restrict code execution</span></span> | <span data-ttu-id="b8623-120">Esegui questa API per contenere un attacco arrestando processi dannosi.</span><span class="sxs-lookup"><span data-stu-id="b8623-120">Run this API to contain an attack by stopping malicious processes.</span></span> <span data-ttu-id="b8623-121">Puoi anche bloccare un dispositivo e impedire l'esecuzione di successivi tentativi di programmi potenzialmente dannosi.</span><span class="sxs-lookup"><span data-stu-id="b8623-121">You can also lock down a device and prevent subsequent attempts of potentially malicious programs from running.</span></span>
<span data-ttu-id="b8623-122">Annullamento dell'esecuzione del codice</span><span class="sxs-lookup"><span data-stu-id="b8623-122">Unrestrict code execution</span></span> | <span data-ttu-id="b8623-123">Esegui questa operazione per annullare i criteri di restrizione delle applicazioni dopo aver verificato che il dispositivo compromesso è stato corretti.</span><span class="sxs-lookup"><span data-stu-id="b8623-123">Run this to reverse the restriction of applications policy after you have verified that the compromised device has been remediated.</span></span>
<span data-ttu-id="b8623-124">Eseguire ricerca del virus</span><span class="sxs-lookup"><span data-stu-id="b8623-124">Run antivirus scan</span></span> | <span data-ttu-id="b8623-125">Avviare in remoto un'analisi antivirus per identificare e correggere il malware che potrebbe essere presente in un dispositivo compromesso.</span><span class="sxs-lookup"><span data-stu-id="b8623-125">Remotely initiate an antivirus scan to help identify and remediate malware that might be present on a compromised device.</span></span>
<span data-ttu-id="b8623-126">Arrestare e mettere in quarantena un file</span><span class="sxs-lookup"><span data-stu-id="b8623-126">Stop and quarantine file</span></span> |  <span data-ttu-id="b8623-127">Eseguire questa chiamata per interrompere l'esecuzione di processi, file in quarantena ed eliminare la persistenza, ad esempio le chiavi del Registro di sistema.</span><span class="sxs-lookup"><span data-stu-id="b8623-127">Run this call to stop running processes, quarantine  files, and delete persistency such as registry keys.</span></span>
<span data-ttu-id="b8623-128">Esempio di richiesta</span><span class="sxs-lookup"><span data-stu-id="b8623-128">Request sample</span></span> | <span data-ttu-id="b8623-129">Esegui questa chiamata per richiedere un esempio di file da un dispositivo specifico.</span><span class="sxs-lookup"><span data-stu-id="b8623-129">Run this call to request a sample of a file from a specific device.</span></span> <span data-ttu-id="b8623-130">Il file verrà raccolto dal dispositivo e caricato in un archivio sicuro.</span><span class="sxs-lookup"><span data-stu-id="b8623-130">The file will be collected from the device and uploaded to a secure storage.</span></span>
<span data-ttu-id="b8623-131">Blocca file</span><span class="sxs-lookup"><span data-stu-id="b8623-131">Block file</span></span> | <span data-ttu-id="b8623-132">Eseguire questa API per impedire l'ulteriore propagazione di un attacco nell'organizzazione vietando file potenzialmente dannosi o malware sospetto.</span><span class="sxs-lookup"><span data-stu-id="b8623-132">Run this API to prevent further propagation of an attack in your organization by banning potentially malicious files or suspected malware.</span></span> 
<span data-ttu-id="b8623-133">Sblocca file</span><span class="sxs-lookup"><span data-stu-id="b8623-133">Unblock file</span></span> | <span data-ttu-id="b8623-134">Consentire l'esecuzione di un file nell'organizzazione usando Antivirus Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="b8623-134">Allow a file run in the organization using Microsoft Defender Antivirus.</span></span>
<span data-ttu-id="b8623-135">Ottenere l'URI di firma di accesso condiviso del pacchetto</span><span class="sxs-lookup"><span data-stu-id="b8623-135">Get package SAS URI</span></span> | <span data-ttu-id="b8623-136">Esegui questa API per ottenere un URI che consenta il download di un pacchetto di analisi.</span><span class="sxs-lookup"><span data-stu-id="b8623-136">Run this API to get a URI that allows downloading an investigation package.</span></span>
<span data-ttu-id="b8623-137">Get MachineAction object</span><span class="sxs-lookup"><span data-stu-id="b8623-137">Get MachineAction object</span></span> | <span data-ttu-id="b8623-138">Esegui questa API per ottenere l'oggetto MachineAction.</span><span class="sxs-lookup"><span data-stu-id="b8623-138">Run this API to get MachineAction object.</span></span>
<span data-ttu-id="b8623-139">Get MachineActions collection</span><span class="sxs-lookup"><span data-stu-id="b8623-139">Get MachineActions collection</span></span> | <span data-ttu-id="b8623-140">Esegui questa operazione per ottenere la raccolta MachineAction.</span><span class="sxs-lookup"><span data-stu-id="b8623-140">Run this to get MachineAction collection.</span></span>
<span data-ttu-id="b8623-141">Get FileActions collection</span><span class="sxs-lookup"><span data-stu-id="b8623-141">Get FileActions collection</span></span> | <span data-ttu-id="b8623-142">Esegui questa API per ottenere la raccolta FileActions.</span><span class="sxs-lookup"><span data-stu-id="b8623-142">Run this API to get FileActions collection.</span></span>
<span data-ttu-id="b8623-143">Get FileMachineAction object</span><span class="sxs-lookup"><span data-stu-id="b8623-143">Get FileMachineAction object</span></span> | <span data-ttu-id="b8623-144">Esegui questa API per ottenere l'oggetto FileMachineAction.</span><span class="sxs-lookup"><span data-stu-id="b8623-144">Run this API to get FileMachineAction object.</span></span>
<span data-ttu-id="b8623-145">Get FileMachineActions collection</span><span class="sxs-lookup"><span data-stu-id="b8623-145">Get FileMachineActions collection</span></span> | <span data-ttu-id="b8623-146">Esegui questa API per ottenere la raccolta FileMachineAction.</span><span class="sxs-lookup"><span data-stu-id="b8623-146">Run this API to get FileMachineAction collection.</span></span>
