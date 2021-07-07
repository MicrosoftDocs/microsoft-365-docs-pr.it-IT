---
title: Test Base SDK for Python
description: Dettagli sulla comprensione dell'SDK di Test Base per Python
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: article
ms.date: 07/06/2021
ms.service: virtual-desktop
localization_priority: Normal
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: c7f2d4b7b600e84b2ed35cce320dcb7d7191ecfc
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/07/2021
ms.locfileid: "53323126"
---
# <a name="test-base-sdk-for-python"></a><span data-ttu-id="e779e-103">Test Base SDK for Python</span><span class="sxs-lookup"><span data-stu-id="e779e-103">Test Base SDK for Python</span></span>

## <a name="overview"></a><span data-ttu-id="e779e-104">Panoramica</span><span class="sxs-lookup"><span data-stu-id="e779e-104">Overview</span></span>
<span data-ttu-id="e779e-105">Test Base SDK può essere usato per interagire con la risorsa di base di test di Azure.</span><span class="sxs-lookup"><span data-stu-id="e779e-105">The Test Base SDK can be used to interact with the Azure test base resource.</span></span> <span data-ttu-id="e779e-106">(ad esempio, gestire il pacchetto dell'applicazione, includere creare il pacchetto, modificare il pacchetto ed eliminare il pacchetto)</span><span class="sxs-lookup"><span data-stu-id="e779e-106">(i.e. manage your application package, include create package, edit package and delete package)</span></span>

<span data-ttu-id="e779e-107">Con l'SDK, il riepilogo dei test e il risultato dell'analisi che possono essere ottenuto includono: scriptExecution, reliability, memoryUtilization, cpuUtilization, memoryRegression, cpuRegression.</span><span class="sxs-lookup"><span data-stu-id="e779e-107">With the SDK, the test summary and Analysis Result which can be gotten include : scriptExecution, reliability, memoryUtilization, cpuUtilization, memoryRegression, cpuRegression.</span></span>

<span data-ttu-id="e779e-108">Con Test Base SDK puoi integrare la base di test nella pipeline CI/CD.</span><span class="sxs-lookup"><span data-stu-id="e779e-108">With the Test Base SDK, you can integrate test base in your CI/CD pipeline.</span></span>

## <a name="client-library"></a><span data-ttu-id="e779e-109">Libreria client</span><span class="sxs-lookup"><span data-stu-id="e779e-109">Client Library</span></span>

<span data-ttu-id="e779e-110">Installare il pacchetto di base di test con pip.</span><span class="sxs-lookup"><span data-stu-id="e779e-110">Install the test base package with pip.</span></span>

~~~
pip install  Microsoft.Testbase
~~~
 
## <a name="example"></a><span data-ttu-id="e779e-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="e779e-111">Example</span></span>
