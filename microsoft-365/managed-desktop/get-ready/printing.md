---
title: Preparare risorse di stampa per Microsoft Managed Desktop
description: Passaggi importanti per assicurarsi che la stampa funzioni senza problemi
keywords: Microsoft Managed Desktop, Microsoft 365, servizio, documentazione
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 3f77074aa11e9dc82c8fac9763fdebfd2fc49d99
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287210"
---
# <a name="prepare-printing-resources-for-microsoft-managed-desktop"></a><span data-ttu-id="79cfb-104">Preparare risorse di stampa per Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="79cfb-104">Prepare printing resources for Microsoft Managed Desktop</span></span>

<span data-ttu-id="79cfb-105">Quando si è pronti per la registrazione a Microsoft Managed Desktop, è consigliabile valutare i requisiti di stampa e determinare l'approccio giusto per l'ambiente.</span><span class="sxs-lookup"><span data-stu-id="79cfb-105">As you get ready to enroll in Microsoft Managed Desktop, you should evaluate your printing requirements and determine the right approach for your environment.</span></span> <span data-ttu-id="79cfb-106">Sono disponibili tre opzioni:</span><span class="sxs-lookup"><span data-stu-id="79cfb-106">You have three options:</span></span>

- <span data-ttu-id="79cfb-107">Distribuire la soluzione Microsoft Universal Print per semplificare l'individuazione delle stampanti Microsoft Managed Desktop dispositivi.</span><span class="sxs-lookup"><span data-stu-id="79cfb-107">Deploy the Microsoft Universal Print solution to make it easy for Microsoft Managed Desktop devices to discover printers.</span></span> <span data-ttu-id="79cfb-108">Per ulteriori informazioni, vedere [What is Universal Print.](/universal-print/fundamentals/universal-print-whatis)</span><span class="sxs-lookup"><span data-stu-id="79cfb-108">For more information, see [What is Universal Print](/universal-print/fundamentals/universal-print-whatis).</span></span>
- <span data-ttu-id="79cfb-109">Distribuire le stampanti direttamente utilizzando uno script di PowerShell personalizzato.</span><span class="sxs-lookup"><span data-stu-id="79cfb-109">Deploy printers directly by using a custom PowerShell script.</span></span> <span data-ttu-id="79cfb-110">Seguire i passaggi descritti nella [sezione Configurare le stampanti](#set-up-local-printers) locali.</span><span class="sxs-lookup"><span data-stu-id="79cfb-110">Follow the steps in the [Set up local printers](#set-up-local-printers) section.</span></span>
- <span data-ttu-id="79cfb-111">Usa una soluzione di stampa cloud non Microsoft compatibile con i dispositivi Windows 10 aggiunti a un Azure Active Directory dominio.</span><span class="sxs-lookup"><span data-stu-id="79cfb-111">Use a non-Microsoft cloud printing solution that is compatible with Windows 10 devices that are joined to an Azure Active Directory domain.</span></span> <span data-ttu-id="79cfb-112">La soluzione deve soddisfare i requisiti software per Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="79cfb-112">The solution must meet the software requirements for Microsoft Managed Desktop.</span></span> <span data-ttu-id="79cfb-113">Per altre informazioni, vedi requisiti [Microsoft Managed Desktop'app](../service-description/mmd-app-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="79cfb-113">For more information, see [Microsoft Managed Desktop app requirements](../service-description/mmd-app-requirements.md).</span></span>
 
<span data-ttu-id="79cfb-114">In tutti i casi, se i driver della stampante non sono disponibili da Microsoft Update o dal Microsoft Store, dovrai ottenerli manualmente e averli in pacchetto per la distribuzione nei dispositivi Microsoft Managed Desktop con Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="79cfb-114">In all cases, if the printer drivers are not available from Microsoft Update or the Microsoft Store, you'll have to obtain them yourself and have them packaged for deployment to your Microsoft Managed Desktop devices with Microsoft Intune.</span></span> <span data-ttu-id="79cfb-115">Per altre informazioni, vedere [Intune Autonomo - Gestione app Win32](/mem/intune/apps/apps-win32-app-management)</span><span class="sxs-lookup"><span data-stu-id="79cfb-115">For more, see [Intune Standalone - Win32 app management](/mem/intune/apps/apps-win32-app-management)</span></span>

## <a name="set-up-local-printers"></a><span data-ttu-id="79cfb-116">Configurare stampanti locali</span><span class="sxs-lookup"><span data-stu-id="79cfb-116">Set up local printers</span></span>

<span data-ttu-id="79cfb-117">Se si è deciso di distribuire le stampanti utilizzando uno script di PowerShell personalizzato e si sono preparate le risorse di stampa, eseguire la procedura seguente per distribuire le stampanti condivise:</span><span class="sxs-lookup"><span data-stu-id="79cfb-117">If you've decided to deploy printers by using a custom PowerShell script and have prepared the printing resources, follow these steps to have shared printers deployed:</span></span>

1. <span data-ttu-id="79cfb-118">Passare al portale Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="79cfb-118">Navigate to the Microsoft Managed Desktop portal.</span></span>
2. <span data-ttu-id="79cfb-119">Inviare una richiesta con etichetta *Distribuzione* stampante nella sezione **Richieste >** supporto tecnico del portale di amministrazione, fornendo questi dettagli:</span><span class="sxs-lookup"><span data-stu-id="79cfb-119">Submit a request labeled *Printer deployment* in the **Support > Support requests** section of the Admin Portal, providing these details:</span></span>
    - <span data-ttu-id="79cfb-120">Tutti i percorsi UNC per i percorsi delle stampanti condivise che dovranno essere distribuiti per Microsoft Managed Desktop dispositivi</span><span class="sxs-lookup"><span data-stu-id="79cfb-120">All UNC paths to shared printer locations that will need to be deployed for Microsoft Managed Desktop devices</span></span>
    - <span data-ttu-id="79cfb-121">Gruppi di utenti che richiedono l'accesso a queste stampanti condivise</span><span class="sxs-lookup"><span data-stu-id="79cfb-121">User groups that require access to these shared printers</span></span>
3. <span data-ttu-id="79cfb-122">Usando il portale di amministrazione, ti inseriamo quando la richiesta è stata completata.</span><span class="sxs-lookup"><span data-stu-id="79cfb-122">Using the Admin Portal, we'll let you know when the request has been completed.</span></span> <span data-ttu-id="79cfb-123">Inizialmente la configurazione verrà distribuita solo nei dispositivi nel gruppo di distribuzione Test.</span><span class="sxs-lookup"><span data-stu-id="79cfb-123">Initially we'll only deploy the configuration to devices in the Test deployment group.</span></span>
4. <span data-ttu-id="79cfb-124">È necessario verificare e verificare se la configurazione funziona come previsto.</span><span class="sxs-lookup"><span data-stu-id="79cfb-124">You must test and confirm whether the configuration works as you expect.</span></span> <span data-ttu-id="79cfb-125">Rispondi usando la **scheda Discussione** nella richiesta di supporto per far sapere quando hai completato il test.</span><span class="sxs-lookup"><span data-stu-id="79cfb-125">Reply by using the **Discussion** tab in the Support request to let us know when you've completed your testing.</span></span>
5. <span data-ttu-id="79cfb-126">La configurazione verrà quindi distribuita agli altri gruppi di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="79cfb-126">We'll then deploy the configuration to the other deployment groups.</span></span>

## <a name="steps-to-get-ready"></a><span data-ttu-id="79cfb-127">Passaggi per prepararsi</span><span class="sxs-lookup"><span data-stu-id="79cfb-127">Steps to get ready</span></span>

1. <span data-ttu-id="79cfb-128">Esaminare [i prerequisiti per Microsoft Managed Desktop](prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="79cfb-128">Review [Prerequisites for Microsoft Managed Desktop](prerequisites.md).</span></span>
2. <span data-ttu-id="79cfb-129">Utilizzare [gli strumenti di valutazione della conformità](readiness-assessment-tool.md).</span><span class="sxs-lookup"><span data-stu-id="79cfb-129">Use [Readiness assessment tools](readiness-assessment-tool.md).</span></span>
3. [<span data-ttu-id="79cfb-130">Prerequisiti per gli account Guest</span><span class="sxs-lookup"><span data-stu-id="79cfb-130">Prerequisites for guest accounts</span></span>](guest-accounts.md)
4. [<span data-ttu-id="79cfb-131">Configurazione rete in Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="79cfb-131">Network configuration for Microsoft Managed Desktop</span></span>](network.md)
5. [<span data-ttu-id="79cfb-132">Preparare certificati e profili di rete per Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="79cfb-132">Prepare certificates and network profiles for Microsoft Managed Desktop</span></span>](certs-wifi-lan.md)
6. [<span data-ttu-id="79cfb-133">Preparare l'accesso alle risorse locali per Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="79cfb-133">Prepare on-premises resources access for Microsoft Managed Desktop</span></span>](authentication.md)
7. [<span data-ttu-id="79cfb-134">App in Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="79cfb-134">Apps in Microsoft Managed Desktop</span></span>](apps.md)
8. [<span data-ttu-id="79cfb-135">Preparare unità mappate per Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="79cfb-135">Prepare mapped drives for Microsoft Managed Desktop</span></span>](mapped-drives.md)
9. <span data-ttu-id="79cfb-136">[Preparare le risorse di stampa per Microsoft Managed Desktop](printing.md) (questo articolo)</span><span class="sxs-lookup"><span data-stu-id="79cfb-136">[Prepare printing resources for Microsoft Managed Desktop](printing.md) (This article)</span></span>
