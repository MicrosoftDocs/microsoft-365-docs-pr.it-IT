---
title: Microsoft 365 gestione del danneggiamento dei dati
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
description: In questo articolo viene illustrato il danneggiamento dei dati in Microsoft 365 e gli sforzi compiuti da Microsoft per impedire e recuperare i dati.
ms.openlocfilehash: fabecf8e368813e2f895669edc19c3f74e305c35
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691141"
---
# <a name="dealing-with-data-corruption-in-microsoft-365"></a><span data-ttu-id="5fd26-103">Gestione del danneggiamento dei dati in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5fd26-103">Dealing with Data Corruption in Microsoft 365</span></span>

<span data-ttu-id="5fd26-104">Uno degli aspetti impegnativi dell'esecuzione di un servizio cloud su vasta scala consiste nel gestire il danneggiamento dei dati, in base all'elevato volume di dati e ai sistemi indipendenti.</span><span class="sxs-lookup"><span data-stu-id="5fd26-104">One of the challenging aspects of running a large-scale cloud service is how to handle data corruption, given the large volume of data and independent systems.</span></span> <span data-ttu-id="5fd26-105">Il danneggiamento dei dati può essere causato da:</span><span class="sxs-lookup"><span data-stu-id="5fd26-105">Data corruption can be caused by:</span></span>

- <span data-ttu-id="5fd26-106">Bug dell'infrastruttura o dell'applicazione che danneggiano alcuni o tutti lo stato dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="5fd26-106">Application or infrastructure bugs, corrupting some or all of the application state</span></span>
- <span data-ttu-id="5fd26-107">Problemi relativi all'hardware che determinano la perdita di dati o l'impossibilità di leggere i dati</span><span class="sxs-lookup"><span data-stu-id="5fd26-107">Hardware issues that result in lost data or an inability to read data</span></span>
- <span data-ttu-id="5fd26-108">Errori operativi umani</span><span class="sxs-lookup"><span data-stu-id="5fd26-108">Human operational errors</span></span>
- <span data-ttu-id="5fd26-109">Hacker maligni e dipendenti scontenti</span><span class="sxs-lookup"><span data-stu-id="5fd26-109">Malicious hackers and disgruntled employees</span></span>
- <span data-ttu-id="5fd26-110">Eventi imprevisti nei servizi esterni che causano una perdita di dati</span><span class="sxs-lookup"><span data-stu-id="5fd26-110">Incidents in external services that result in some loss of data</span></span>

<span data-ttu-id="5fd26-111">Poiché una maggiore resilienza nell'integrità dei dati comporta meno incidenti di danneggiamento dei dati, Microsoft ha incorporato i meccanismi di protezione di Microsoft 365 per evitare che si verifichino danneggiamenti, nonché sistemi e processi che consentono di recuperare i dati in caso di problemi.</span><span class="sxs-lookup"><span data-stu-id="5fd26-111">Because greater resiliency in data integrity means fewer data corruption incidents, Microsoft has built into Microsoft 365 protection mechanisms to prevent corruption from happening, as well as systems and processes that enable us to recover data if it does.</span></span> <span data-ttu-id="5fd26-112">I controlli e i processi sono presenti nelle varie fasi del processo di rilascio ingegneristico per aumentare la resilienza rispetto al danneggiamento dei dati, tra cui:</span><span class="sxs-lookup"><span data-stu-id="5fd26-112">Checks and processes exist within the various stages of the engineering release process to increase resiliency against data corruption, including:</span></span>

- <span data-ttu-id="5fd26-113">Progettazione del sistema</span><span class="sxs-lookup"><span data-stu-id="5fd26-113">System Design</span></span>
- <span data-ttu-id="5fd26-114">Organizzazione e struttura del codice</span><span class="sxs-lookup"><span data-stu-id="5fd26-114">Code organization and structure</span></span>
- <span data-ttu-id="5fd26-115">Revisione del codice</span><span class="sxs-lookup"><span data-stu-id="5fd26-115">Code review</span></span>
- <span data-ttu-id="5fd26-116">Unit test, test di integrazione e test di sistema</span><span class="sxs-lookup"><span data-stu-id="5fd26-116">Unit tests, integration tests, and system tests</span></span>
- <span data-ttu-id="5fd26-117">Test/cancelli per cavi di viaggio</span><span class="sxs-lookup"><span data-stu-id="5fd26-117">Trip wires tests/gates</span></span>

<span data-ttu-id="5fd26-118">Negli ambienti di produzione Microsoft 365, la replica peer tra i datacenter garantisce che siano sempre presenti più copie live di tutti i dati.</span><span class="sxs-lookup"><span data-stu-id="5fd26-118">Within Microsoft 365 production environments, peer replication between datacenters ensures that there are always multiple live copies of any data.</span></span> <span data-ttu-id="5fd26-119">Le immagini e gli script standard vengono utilizzati per recuperare i server persi e i dati replicati vengono utilizzati per ripristinare i dati dei clienti.</span><span class="sxs-lookup"><span data-stu-id="5fd26-119">Standard images and scripts are used to recover lost servers, and replicated data is used to restore customer data.</span></span> <span data-ttu-id="5fd26-120">Grazie ai controlli e ai processi di resilienza dei dati incorporati, Microsoft mantiene solo i backup della documentazione del sistema di informazioni di Microsoft 365 (inclusa la documentazione relativa alla sicurezza), utilizzando la replica incorporata in SharePoint Online e lo strumento di repository del codice interno, Source Depot.</span><span class="sxs-lookup"><span data-stu-id="5fd26-120">Because of the built-in data resiliency checks and processes, Microsoft maintains backups only of Microsoft 365 information system documentation (including security-related documentation), using built-in replication in SharePoint Online and our internal code repository tool, Source Depot.</span></span> <span data-ttu-id="5fd26-121">La documentazione del sistema è archiviata in SharePoint Online e Source Depot contiene immagini di sistema e applicazioni.</span><span class="sxs-lookup"><span data-stu-id="5fd26-121">System documentation is stored in SharePoint Online, and Source Depot contains system and application images.</span></span> <span data-ttu-id="5fd26-122">Sia SharePoint Online che Source Depot utilizzano il controllo delle versioni e vengono replicati in tempo quasi reale.</span><span class="sxs-lookup"><span data-stu-id="5fd26-122">Both SharePoint Online and Source Depot use versioning and are replicated in near real time.</span></span>
