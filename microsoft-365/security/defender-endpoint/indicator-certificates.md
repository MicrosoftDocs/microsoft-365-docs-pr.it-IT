---
title: Creare indicatori in base ai certificati
ms.reviewer: ''
description: Creare indicatori in base ai certificati che definiscono il rilevamento, la prevenzione e l'esclusione delle entità.
keywords: ioc, certificato, certificati, gestire, consentito, bloccato, bloccare, pulito, dannoso, hash file, indirizzo IP, URL, dominio
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: b75a8cf1d2681281555a3b7bb80deadfc11ee44c
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845452"
---
# <a name="create-indicators-based-on-certificates"></a><span data-ttu-id="4bc8a-104">Creare indicatori in base ai certificati</span><span class="sxs-lookup"><span data-stu-id="4bc8a-104">Create indicators based on certificates</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="4bc8a-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="4bc8a-105">**Applies to:**</span></span>
- [<span data-ttu-id="4bc8a-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="4bc8a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="4bc8a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4bc8a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="4bc8a-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="4bc8a-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="4bc8a-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="4bc8a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

<span data-ttu-id="4bc8a-110">È possibile creare indicatori per i certificati.</span><span class="sxs-lookup"><span data-stu-id="4bc8a-110">You can create indicators for certificates.</span></span> <span data-ttu-id="4bc8a-111">Alcuni casi d'uso comuni includono:</span><span class="sxs-lookup"><span data-stu-id="4bc8a-111">Some common use cases include:</span></span>

- <span data-ttu-id="4bc8a-112">Scenari in cui è necessario distribuire [](attack-surface-reduction.md) tecnologie di [](controlled-folders.md) blocco, come le regole di riduzione della superficie di attacco e l'accesso controllato alle cartelle, ma è necessario consentire i comportamenti delle applicazioni firmate aggiungendo il certificato nell'elenco consenti.</span><span class="sxs-lookup"><span data-stu-id="4bc8a-112">Scenarios when you need to deploy blocking technologies, such as [attack surface reduction rules](attack-surface-reduction.md) and [controlled folder access](controlled-folders.md) but need to allow behaviors from signed applications by adding the certificate in the allow list.</span></span>
- <span data-ttu-id="4bc8a-113">Blocco dell'utilizzo di un'applicazione firmata specifica nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="4bc8a-113">Blocking the use of a specific signed application across your organization.</span></span> <span data-ttu-id="4bc8a-114">Creando un indicatore per bloccare il certificato dell'applicazione, Windows Defender AV impedirà le esecuzioni di file (blocco e correzione) e il comportamento di Analisi e correzione automatizzata è lo stesso.</span><span class="sxs-lookup"><span data-stu-id="4bc8a-114">By creating an indicator to block the certificate of the application, Windows Defender AV will prevent file executions (block and remediate) and the Automated Investigation and Remediation behave the same.</span></span>


### <a name="before-you-begin"></a><span data-ttu-id="4bc8a-115">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="4bc8a-115">Before you begin</span></span>

<span data-ttu-id="4bc8a-116">Prima di creare indicatori per i certificati, è importante comprendere i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="4bc8a-116">It's important to understand the following requirements prior to creating indicators for certificates:</span></span>

- <span data-ttu-id="4bc8a-117">Questa funzionalità è disponibile se l'organizzazione usa Windows Defender Antivirus e la protezione basata su cloud è abilitata.</span><span class="sxs-lookup"><span data-stu-id="4bc8a-117">This feature is available if your organization uses Windows Defender Antivirus and Cloud-based protection is enabled.</span></span> <span data-ttu-id="4bc8a-118">Per ulteriori informazioni, vedere [Manage cloud-based protection](/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus).</span><span class="sxs-lookup"><span data-stu-id="4bc8a-118">For more information, see [Manage cloud-based protection](/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus).</span></span>
- <span data-ttu-id="4bc8a-119">La versione del client Antimalware deve essere 4.18.1901.x o successiva.</span><span class="sxs-lookup"><span data-stu-id="4bc8a-119">The Antimalware client version must be  4.18.1901.x or later.</span></span>
- <span data-ttu-id="4bc8a-120">Supportato nei computer Windows 10 versione 1703 o successiva, Windows server 2016 e 2019.</span><span class="sxs-lookup"><span data-stu-id="4bc8a-120">Supported on machines on Windows 10, version 1703 or later, Windows server 2016 and 2019.</span></span>
- <span data-ttu-id="4bc8a-121">Le definizioni di protezione da virus e minacce devono essere aggiornate.</span><span class="sxs-lookup"><span data-stu-id="4bc8a-121">The virus and threat protection definitions must be up to date.</span></span>
- <span data-ttu-id="4bc8a-122">Questa funzionalità attualmente supporta l'immissione di . CER o . Estensioni di file PEM.</span><span class="sxs-lookup"><span data-stu-id="4bc8a-122">This feature currently supports entering .CER or .PEM file extensions.</span></span>

>[!IMPORTANT]
> - <span data-ttu-id="4bc8a-123">Un certificato foglia valido è un certificato di firma con un percorso di certificazione valido e che deve essere concatenato all'Autorità di certificazione radice (CA) attendibile da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4bc8a-123">A valid leaf certificate is a signing certificate that has a valid certification path and must be chained to the Root Certificate Authority (CA) trusted by Microsoft.</span></span>  <span data-ttu-id="4bc8a-124">In alternativa, è possibile utilizzare un certificato personalizzato (autofirmato) purché sia considerato attendibile dal client (il certificato CA radice è installato nel computer locale 'Autorità di certificazione radice attendibili').</span><span class="sxs-lookup"><span data-stu-id="4bc8a-124">Alternatively, a custom (self-signed) certificate can be used as long as it's trusted by the client (Root CA certificate is installed under the Local Machine 'Trusted Root Certification Authorities').</span></span>
>- <span data-ttu-id="4bc8a-125">Gli elementi figlio o padre delle operazioni di I/O del certificato consenti/blocca non sono inclusi nella funzionalità IoC consenti/blocca, ma sono supportati solo i certificati foglia.</span><span class="sxs-lookup"><span data-stu-id="4bc8a-125">The children or parent of the allow/block certificate IOCs are not included in the allow/block IoC functionality, only leaf certificates are supported.</span></span>
>- <span data-ttu-id="4bc8a-126">I certificati firmati Microsoft non possono essere bloccati.</span><span class="sxs-lookup"><span data-stu-id="4bc8a-126">Microsoft signed certificates cannot be blocked.</span></span>

#### <a name="create-an-indicator-for-certificates-from-the-settings-page"></a><span data-ttu-id="4bc8a-127">Creare un indicatore per i certificati dalla pagina delle impostazioni:</span><span class="sxs-lookup"><span data-stu-id="4bc8a-127">Create an indicator for certificates from the settings page:</span></span>

>[!IMPORTANT]
> <span data-ttu-id="4bc8a-128">La creazione e la rimozione di un certificato IoC possono richiedere fino a 3 ore.</span><span class="sxs-lookup"><span data-stu-id="4bc8a-128">It can take up to 3 hours to create and remove a certificate IoC.</span></span>

1. <span data-ttu-id="4bc8a-129">Nel riquadro di spostamento selezionare **Impostazioni**  >  **indicatori**.</span><span class="sxs-lookup"><span data-stu-id="4bc8a-129">In the navigation pane, select **Settings** > **Indicators**.</span></span>  

2. <span data-ttu-id="4bc8a-130">Selezionare la **scheda** Certificato.</span><span class="sxs-lookup"><span data-stu-id="4bc8a-130">Select the **Certificate** tab.</span></span>

3. <span data-ttu-id="4bc8a-131">Selezionare **Aggiungi indicatore**.</span><span class="sxs-lookup"><span data-stu-id="4bc8a-131">Select **Add indicator**.</span></span>

4. <span data-ttu-id="4bc8a-132">Specificare i dettagli seguenti:</span><span class="sxs-lookup"><span data-stu-id="4bc8a-132">Specify the following details:</span></span>
   - <span data-ttu-id="4bc8a-133">Indicatore: specificare i dettagli dell'entità e definire la scadenza dell'indicatore.</span><span class="sxs-lookup"><span data-stu-id="4bc8a-133">Indicator - Specify the entity details and define the expiration of the indicator.</span></span>
   - <span data-ttu-id="4bc8a-134">Azione: specificare l'azione da eseguire e fornire una descrizione.</span><span class="sxs-lookup"><span data-stu-id="4bc8a-134">Action - Specify the action to be taken and provide a description.</span></span>
   - <span data-ttu-id="4bc8a-135">Ambito: definire l'ambito del gruppo di computer.</span><span class="sxs-lookup"><span data-stu-id="4bc8a-135">Scope - Define the scope of the machine group.</span></span>

5. <span data-ttu-id="4bc8a-136">Esaminare i dettagli nella scheda Riepilogo, quindi fare clic su **Salva.**</span><span class="sxs-lookup"><span data-stu-id="4bc8a-136">Review the details in the Summary tab, then click **Save**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="4bc8a-137">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="4bc8a-137">Related topics</span></span>
- [<span data-ttu-id="4bc8a-138">Creare indicatori</span><span class="sxs-lookup"><span data-stu-id="4bc8a-138">Create indicators</span></span>](manage-indicators.md)
- <span data-ttu-id="4bc8a-139">[Creare indicatori per file](indicator-file.md).</span><span class="sxs-lookup"><span data-stu-id="4bc8a-139">[Create indicators for files](indicator-file.md)</span></span>
- [<span data-ttu-id="4bc8a-140">Creare indicatori per IP e URL/domini</span><span class="sxs-lookup"><span data-stu-id="4bc8a-140">Create indicators for IPs and URLs/domains</span></span>](indicator-ip-domain.md)
- [<span data-ttu-id="4bc8a-141">Gestire indicatori</span><span class="sxs-lookup"><span data-stu-id="4bc8a-141">Manage indicators</span></span>](indicator-manage.md)
