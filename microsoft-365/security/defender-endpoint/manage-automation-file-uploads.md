---
title: Gestire i caricamenti di file di automazione
description: Abilitare l'analisi del contenuto e configurare l'estensione di file e le estensioni degli allegati di posta elettronica che verranno inviate per l'analisi
keywords: automazione, file, caricamenti, contenuto, analisi, file, estensione, posta elettronica, allegato
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
ms.openlocfilehash: 72405ad7500bf5d672f66ea64634e60c29ad1704
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51068874"
---
# <a name="manage-automation-file-uploads"></a><span data-ttu-id="4bb75-104">Gestire i caricamenti di file di automazione</span><span class="sxs-lookup"><span data-stu-id="4bb75-104">Manage automation file uploads</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="4bb75-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="4bb75-105">**Applies to:**</span></span>
- [<span data-ttu-id="4bb75-106">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="4bb75-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="4bb75-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4bb75-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="4bb75-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="4bb75-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="4bb75-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="4bb75-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-automationefileuploads-abovefoldlink)

<span data-ttu-id="4bb75-110">Abilita la funzionalità di analisi del contenuto in modo che determinati file e allegati di posta elettronica possano essere caricati automaticamente nel cloud per un'ulteriore ispezione nell'indagine automatizzata.</span><span class="sxs-lookup"><span data-stu-id="4bb75-110">Enable the content analysis capability so that certain files and email attachments can automatically be uploaded to the cloud for additional inspection in Automated investigation.</span></span>

<span data-ttu-id="4bb75-111">Identificare i file e gli allegati di posta elettronica specificando i nomi delle estensioni di file e i nomi delle estensioni degli allegati di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="4bb75-111">Identify the files and email attachments by specifying the file extension names and email attachment extension names.</span></span> 

<span data-ttu-id="4bb75-112">Ad esempio, se si aggiungono *exe* e *bat* come nomi di estensione di file o allegati, tutti i file o gli allegati con tali estensioni verranno inviati automaticamente al cloud per un'ulteriore ispezione durante l'indagine automatizzata.</span><span class="sxs-lookup"><span data-stu-id="4bb75-112">For example, if you add *exe* and *bat* as file or attachment extension names, then all files or attachments with those extensions will automatically be sent to the cloud for additional inspection during Automated investigation.</span></span> 

## <a name="add-file-extension-names-and-attachment-extension-names"></a><span data-ttu-id="4bb75-113">Aggiungere i nomi delle estensioni di file e i nomi delle estensioni degli allegati.</span><span class="sxs-lookup"><span data-stu-id="4bb75-113">Add file extension names and attachment extension names.</span></span>

1. <span data-ttu-id="4bb75-114">Nel riquadro di spostamento selezionare **Impostazioni**  >  **Caricamenti file di automazione**.</span><span class="sxs-lookup"><span data-stu-id="4bb75-114">In the navigation pane, select **Settings** > **Automation file uploads**.</span></span> 

2. <span data-ttu-id="4bb75-115">Attiva e disattiva l'impostazione **di** analisi **del contenuto.**</span><span class="sxs-lookup"><span data-stu-id="4bb75-115">Toggle the content analysis setting between **On** and **Off**.</span></span>

3. <span data-ttu-id="4bb75-116">Configurare i nomi di estensione seguenti e separare i nomi delle estensioni con una virgola:</span><span class="sxs-lookup"><span data-stu-id="4bb75-116">Configure the following extension names and separate extension names with a comma:</span></span>
   - <span data-ttu-id="4bb75-117">**Nomi delle estensioni di file:** i file sospetti, ad eccezione degli allegati di posta elettronica, verranno inviati per un'ulteriore ispezione</span><span class="sxs-lookup"><span data-stu-id="4bb75-117">**File extension names** -  Suspicious files except email attachments will be submitted for additional inspection</span></span>
  

## <a name="related-topics"></a><span data-ttu-id="4bb75-118">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="4bb75-118">Related topics</span></span>
- [<span data-ttu-id="4bb75-119">Gestire le esclusioni delle cartelle di automazione</span><span class="sxs-lookup"><span data-stu-id="4bb75-119">Manage automation folder exclusions</span></span>](manage-automation-folder-exclusions.md)
