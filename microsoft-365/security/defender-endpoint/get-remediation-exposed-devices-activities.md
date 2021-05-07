---
title: Elencare i dispositivi esposti a un'attività correttiva
description: Restituisce informazioni sui dispositivi esposti per l'attività di correzione specificata.
keywords: api, correzione, api di correzione, ottenere, attività di correzione, correggere dispositivi esposti
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-jweston
author: jweston-1
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 92b5a93e86a20f36469d2b5cb606a8ddc2e97077
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2021
ms.locfileid: "52241713"
---
# <a name="list-exposed-devices-of-one-remediation-activity"></a><span data-ttu-id="c340b-104">Elencare i dispositivi esposti a un'attività correttiva</span><span class="sxs-lookup"><span data-stu-id="c340b-104">List exposed devices of one remediation activity</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c340b-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="c340b-105">**Applies to:**</span></span>

- [<span data-ttu-id="c340b-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="c340b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c340b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c340b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="c340b-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="c340b-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="c340b-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="c340b-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a><span data-ttu-id="c340b-110">Descrizione API</span><span class="sxs-lookup"><span data-stu-id="c340b-110">API Description</span></span>

<span data-ttu-id="c340b-111">Restituisce informazioni sui dispositivi esposti per l'attività di correzione specificata.</span><span class="sxs-lookup"><span data-stu-id="c340b-111">Returns information about exposed devices for the specified remediation task.</span></span>

<span data-ttu-id="c340b-112">[Ulteriori informazioni sulle attività di correzione.](tvm-remediation.md)</span><span class="sxs-lookup"><span data-stu-id="c340b-112">[Learn more about remediation activities](tvm-remediation.md).</span></span>

## <a name="list-exposed-devices-associated-with-a-remediation-task-id"></a><span data-ttu-id="c340b-113">Elencare i dispositivi esposti associati a un'attività di correzione (id)</span><span class="sxs-lookup"><span data-stu-id="c340b-113">List exposed devices associated with a remediation task (id)</span></span>

<span data-ttu-id="c340b-114">**URL:** GET: /api/remediationTasks/ \{ id \} /machineReferences</span><span class="sxs-lookup"><span data-stu-id="c340b-114">**URL:** GET: /api/remediationTasks/\{id\}/machineReferences</span></span>

## <a name="permissions"></a><span data-ttu-id="c340b-115">Autorizzazioni</span><span class="sxs-lookup"><span data-stu-id="c340b-115">Permissions</span></span>

<span data-ttu-id="c340b-116">Per chiamare questa API è necessaria una delle autorizzazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="c340b-116">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="c340b-117">Per altre informazioni, inclusa la scelta delle autorizzazioni, vedi Usare Le API di [Microsoft Defender per endpoint per i dettagli.](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="c340b-117">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="c340b-118">Tipo di autorizzazione</span><span class="sxs-lookup"><span data-stu-id="c340b-118">Permission type</span></span> | <span data-ttu-id="c340b-119">Autorizzazione</span><span class="sxs-lookup"><span data-stu-id="c340b-119">Permission</span></span> | <span data-ttu-id="c340b-120">Nome visualizzato autorizzazione</span><span class="sxs-lookup"><span data-stu-id="c340b-120">Permission display name</span></span>
:---|:---|:---
<span data-ttu-id="c340b-121">Applicazione</span><span class="sxs-lookup"><span data-stu-id="c340b-121">Application</span></span> | <span data-ttu-id="c340b-122">RemediationTask.Read.All</span><span class="sxs-lookup"><span data-stu-id="c340b-122">RemediationTask.Read.All</span></span> | <span data-ttu-id="c340b-123">\'Leggere informazioni sulla vulnerabilità di Gestione minacce e vulnerabilità\'</span><span class="sxs-lookup"><span data-stu-id="c340b-123">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="c340b-124">Delegato (account aziendale o dell'istituto di istruzione)</span><span class="sxs-lookup"><span data-stu-id="c340b-124">Delegated (work or school account)</span></span> | <span data-ttu-id="c340b-125">RemediationTask.Read.Read</span><span class="sxs-lookup"><span data-stu-id="c340b-125">RemediationTask.Read.Read</span></span> | <span data-ttu-id="c340b-126">\'Leggere informazioni sulla vulnerabilità di Gestione minacce e vulnerabilità\'</span><span class="sxs-lookup"><span data-stu-id="c340b-126">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

## <a name="properties-details"></a><span data-ttu-id="c340b-127">Dettagli proprietà</span><span class="sxs-lookup"><span data-stu-id="c340b-127">Properties details</span></span>

<span data-ttu-id="c340b-128">Proprietà (id)</span><span class="sxs-lookup"><span data-stu-id="c340b-128">Property (id)</span></span> | <span data-ttu-id="c340b-129">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="c340b-129">Data type</span></span> | <span data-ttu-id="c340b-130">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c340b-130">Description</span></span> | <span data-ttu-id="c340b-131">Esempio</span><span class="sxs-lookup"><span data-stu-id="c340b-131">Example</span></span>
:---|:---|:---|:---
<span data-ttu-id="c340b-132">id</span><span class="sxs-lookup"><span data-stu-id="c340b-132">id</span></span> | <span data-ttu-id="c340b-133">Stringa</span><span class="sxs-lookup"><span data-stu-id="c340b-133">String</span></span> | <span data-ttu-id="c340b-134">ID dispositivo</span><span class="sxs-lookup"><span data-stu-id="c340b-134">Device ID</span></span> | <span data-ttu-id="c340b-135">w2957837fwda8w9ae7f023dba081059dw8d94503</span><span class="sxs-lookup"><span data-stu-id="c340b-135">w2957837fwda8w9ae7f023dba081059dw8d94503</span></span>
<span data-ttu-id="c340b-136">computerDnsName</span><span class="sxs-lookup"><span data-stu-id="c340b-136">computerDnsName</span></span> | <span data-ttu-id="c340b-137">Stringa</span><span class="sxs-lookup"><span data-stu-id="c340b-137">String</span></span> | <span data-ttu-id="c340b-138">Nome dispositivo</span><span class="sxs-lookup"><span data-stu-id="c340b-138">Device name</span></span> | <span data-ttu-id="c340b-139">PC-SRV2012R2Foo.UserNameVldNet.local</span><span class="sxs-lookup"><span data-stu-id="c340b-139">PC-SRV2012R2Foo.UserNameVldNet.local</span></span>
<span data-ttu-id="c340b-140">osPlatform</span><span class="sxs-lookup"><span data-stu-id="c340b-140">osPlatform</span></span> | <span data-ttu-id="c340b-141">Stringa</span><span class="sxs-lookup"><span data-stu-id="c340b-141">String</span></span> | <span data-ttu-id="c340b-142">Sistema operativo del dispositivo</span><span class="sxs-lookup"><span data-stu-id="c340b-142">Device operating system</span></span> | <span data-ttu-id="c340b-143">WindowsServer2012R2</span><span class="sxs-lookup"><span data-stu-id="c340b-143">WindowsServer2012R2</span></span>
<span data-ttu-id="c340b-144">rbacGroupName</span><span class="sxs-lookup"><span data-stu-id="c340b-144">rbacGroupName</span></span> | <span data-ttu-id="c340b-145">Stringa</span><span class="sxs-lookup"><span data-stu-id="c340b-145">String</span></span> | <span data-ttu-id="c340b-146">Nome del gruppo di dispositivi a cui è associato questo dispositivo</span><span class="sxs-lookup"><span data-stu-id="c340b-146">Name of the device group this device is associated with</span></span> | <span data-ttu-id="c340b-147">Server</span><span class="sxs-lookup"><span data-stu-id="c340b-147">Servers</span></span>

## <a name="example"></a><span data-ttu-id="c340b-148">Esempio</span><span class="sxs-lookup"><span data-stu-id="c340b-148">Example</span></span>

### <a name="request-example"></a><span data-ttu-id="c340b-149">Esempio di richiesta</span><span class="sxs-lookup"><span data-stu-id="c340b-149">Request example</span></span>

```http
GET https://api-luna.securitycenter.windows.com/api/remediationtasks/03942ef5-aecb-4c6e-b555-d6a97013844c/machinereferences
```

### <a name="response-example"></a><span data-ttu-id="c340b-150">Esempio di risposta</span><span class="sxs-lookup"><span data-stu-id="c340b-150">Response example</span></span>

```json
{
    "@odata.context": "https://wpatdadi-luna-stg.cloudapp.net/api/$metadata#MachineReferences",
    "value": [
        {
            "id": "3cb5df6bb3640a2d37ad09fcd357b182d684fafc",
            "computerDnsName": "ComputerPII_2ea21b2d97c9df23c143ad9e3e454cb674232529.DomainPII_21eed80b086e79bdfa178eabfa25e8be9acfa346.corp.contoso.com",
            "osPlatform": "WindowsServer2016",
            "rbacGroupName": "UnassignedGroup",
            
        },
        {
            "id": "3d9b1ca53e8f077199c7dcbfc9dbfa78f9bf1918",
            "computerDnsName": "ComputerPII_001d606fc149567c192747f48fae304b43c0ddba.DomainxPII_21eed80b086e79bdfa178eabfa25e8be9acfa346.corp.contoso.com",
            "osPlatform": "WindowsServer2012R2",
            "rbacGroupName": "UnassignedGroup",
            
        },
        {
            "id": "3db8b27e6172951d7ea2e2d75945abec56feaf82",
            "computerDnsName": "ComputerPII_ce60cfbjj4b82a091deb5eae560332bba99a9bd7.DomainPII_0bc1aee0fa396d175e514bd61a9e7a5b2b07ee8e.corp.contoso.com",
            "osPlatform": "WindowsServer2016",
            "rbacGroupName": "UnassignedGroup",
            
        },
        {
            "id": "3bad326dcda5b53fab47408cd4a7080f3f3cc8ab",
            "computerDnsName": "ComputerPII_b6b35960dd6539d1d1cef5ada02e235e7b357408.DomainPII_21eed80b089e76bdfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "WindowsServer2012R2",
            "rbacGroupName": "UnassignedGroup",
            
        }
]
}
```

## <a name="see-also"></a><span data-ttu-id="c340b-151">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c340b-151">See also</span></span>

- [<span data-ttu-id="c340b-152">Metodi e proprietà di correzione</span><span class="sxs-lookup"><span data-stu-id="c340b-152">Remediation methods and properties</span></span>](get-remediation-methods-properties.md)

- [<span data-ttu-id="c340b-153">Ottenere un'attività correttiva per ID</span><span class="sxs-lookup"><span data-stu-id="c340b-153">Get one remediation activity by Id</span></span>](get-remediation-one-activity.md)

- [<span data-ttu-id="c340b-154">Elencare tutte le attività correttive</span><span class="sxs-lookup"><span data-stu-id="c340b-154">List all remediation activities</span></span>](get-remediation-all-activities.md)

- [<span data-ttu-id="c340b-155">Rischio basato sulle minacce & gestione delle vulnerabilità</span><span class="sxs-lookup"><span data-stu-id="c340b-155">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="c340b-156">Vulnerabilità nell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="c340b-156">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
