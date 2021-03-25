---
title: Estendere la copertura di ricerca avanzata con le impostazioni giuste
description: Controlla le impostazioni di controllo nei dispositivi Windows e altre impostazioni per assicurarti di ottenere i dati più completi nella ricerca avanzata
keywords: ricerca avanzata, incidente, pivot, entità, impostazioni di controllo, gestione degli account utente, gestione dei gruppi di sicurezza, ricerca delle minacce, ricerca di minacce informatiche, ricerca, query, telemetria, mdatp, Microsoft Defender ATP, Microsoft Defender for Endpoint, Windows Defender, Windows Defender ATP, Windows Defender Advanced Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 10/10/2020
ms.technology: mde
ms.openlocfilehash: 60e8710415e328d06fac4c02e428094e5e4bcc92
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51067461"
---
# <a name="extend-advanced-hunting-coverage-with-the-right-settings"></a><span data-ttu-id="600d2-104">Estendere la copertura di ricerca avanzata con le impostazioni giuste</span><span class="sxs-lookup"><span data-stu-id="600d2-104">Extend advanced hunting coverage with the right settings</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="600d2-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="600d2-105">**Applies to:**</span></span>
- [<span data-ttu-id="600d2-106">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="600d2-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

<span data-ttu-id="600d2-107">[La ricerca avanzata](advanced-hunting-overview.md) si basa sui dati provenienti da tutta l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="600d2-107">[Advanced hunting](advanced-hunting-overview.md) relies on data coming from across your organization.</span></span> <span data-ttu-id="600d2-108">Per ottenere i dati più completi possibili, verificare di disporre delle impostazioni corrette nelle origini dati corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="600d2-108">To get the most comprehensive data possible, ensure that you have the correct settings in the corresponding data sources.</span></span>

## <a name="advanced-security-auditing-on-windows-devices"></a><span data-ttu-id="600d2-109">Controllo di sicurezza avanzato nei dispositivi Windows</span><span class="sxs-lookup"><span data-stu-id="600d2-109">Advanced security auditing on Windows devices</span></span>

<span data-ttu-id="600d2-110">Attiva queste impostazioni di controllo avanzate per assicurarti di ottenere dati sulle attività nei dispositivi, tra cui la gestione degli account locali, la gestione dei gruppi di sicurezza locali e la creazione dei servizi.</span><span class="sxs-lookup"><span data-stu-id="600d2-110">Turn on these advanced auditing settings to ensure you get data about activities on your devices, including local account management, local security group management, and service creation.</span></span>

<span data-ttu-id="600d2-111">Dati</span><span class="sxs-lookup"><span data-stu-id="600d2-111">Data</span></span> | <span data-ttu-id="600d2-112">Descrizione</span><span class="sxs-lookup"><span data-stu-id="600d2-112">Description</span></span> | <span data-ttu-id="600d2-113">Tabella schema</span><span class="sxs-lookup"><span data-stu-id="600d2-113">Schema table</span></span> | <span data-ttu-id="600d2-114">Configurazione</span><span class="sxs-lookup"><span data-stu-id="600d2-114">How to configure</span></span>
-|-|-|-
<span data-ttu-id="600d2-115">Gestione account</span><span class="sxs-lookup"><span data-stu-id="600d2-115">Account management</span></span> | <span data-ttu-id="600d2-116">Eventi acquisiti come vari valori che indicano la creazione, l'eliminazione e altre attività `ActionType` relative all'account locale</span><span class="sxs-lookup"><span data-stu-id="600d2-116">Events captured as various `ActionType` values indicating local account creation, deletion, and other account-related activities</span></span> | [<span data-ttu-id="600d2-117">DeviceEvents</span><span class="sxs-lookup"><span data-stu-id="600d2-117">DeviceEvents</span></span>](advanced-hunting-deviceevents-table.md) | <span data-ttu-id="600d2-118">- Distribuire un criterio di controllo di sicurezza avanzato: [Controlla gestione account utente](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-user-account-management)</span><span class="sxs-lookup"><span data-stu-id="600d2-118">- Deploy an advanced security audit policy: [Audit User Account Management](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-user-account-management)</span></span><br> <span data-ttu-id="600d2-119">- [Informazioni sui criteri di controllo di sicurezza avanzati](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)</span><span class="sxs-lookup"><span data-stu-id="600d2-119">- [Learn about advanced security audit policies](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)</span></span>
<span data-ttu-id="600d2-120">Gestione dei gruppi di sicurezza</span><span class="sxs-lookup"><span data-stu-id="600d2-120">Security group management</span></span> | <span data-ttu-id="600d2-121">Eventi acquisiti come vari `ActionType` valori che indicano la creazione di gruppi di sicurezza locali e altre attività di gestione dei gruppi locali</span><span class="sxs-lookup"><span data-stu-id="600d2-121">Events captured as various `ActionType` values indicating local security group creation and other local group management activities</span></span> | [<span data-ttu-id="600d2-122">DeviceEvents</span><span class="sxs-lookup"><span data-stu-id="600d2-122">DeviceEvents</span></span>](advanced-hunting-deviceevents-table.md) | <span data-ttu-id="600d2-123">- Distribuire un criterio di controllo di sicurezza avanzato: [Controlla Gestione gruppi di sicurezza](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-group-management)</span><span class="sxs-lookup"><span data-stu-id="600d2-123">- Deploy an advanced security audit policy: [Audit Security Group Management](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-group-management)</span></span><br> <span data-ttu-id="600d2-124">- [Informazioni sui criteri di controllo di sicurezza avanzati](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)</span><span class="sxs-lookup"><span data-stu-id="600d2-124">- [Learn about advanced security audit policies](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)</span></span>
<span data-ttu-id="600d2-125">Installazione del servizio</span><span class="sxs-lookup"><span data-stu-id="600d2-125">Service installation</span></span> | <span data-ttu-id="600d2-126">Eventi acquisiti con `ActionType` il valore , che indicano che è stato creato un `ServiceInstalled` servizio</span><span class="sxs-lookup"><span data-stu-id="600d2-126">Events captured with the `ActionType` value `ServiceInstalled`, indicating that a service has been created</span></span> | [<span data-ttu-id="600d2-127">DeviceEvents</span><span class="sxs-lookup"><span data-stu-id="600d2-127">DeviceEvents</span></span>](advanced-hunting-deviceevents-table.md) | <span data-ttu-id="600d2-128">- Distribuire un criterio di controllo di sicurezza avanzato: [Controlla estensione del sistema di sicurezza](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-system-extension)</span><span class="sxs-lookup"><span data-stu-id="600d2-128">- Deploy an advanced security audit policy: [Audit Security System Extension](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-system-extension)</span></span><br> <span data-ttu-id="600d2-129">- [Informazioni sui criteri di controllo di sicurezza avanzati](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)</span><span class="sxs-lookup"><span data-stu-id="600d2-129">- [Learn about advanced security audit policies](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)</span></span>

## <a name="related-topics"></a><span data-ttu-id="600d2-130">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="600d2-130">Related topics</span></span>

- [<span data-ttu-id="600d2-131">Panoramica della ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="600d2-131">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="600d2-132">Capire il linguaggio delle query</span><span class="sxs-lookup"><span data-stu-id="600d2-132">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="600d2-133">Comprendere lo schema</span><span class="sxs-lookup"><span data-stu-id="600d2-133">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="600d2-134">Usare i risultati delle query</span><span class="sxs-lookup"><span data-stu-id="600d2-134">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="600d2-135">Applicare le procedure consigliate per le query</span><span class="sxs-lookup"><span data-stu-id="600d2-135">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="600d2-136">Panoramica dei rilevamenti personalizzati</span><span class="sxs-lookup"><span data-stu-id="600d2-136">Custom detections overview</span></span>](overview-custom-detections.md)
