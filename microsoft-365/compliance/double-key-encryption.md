---
title: Crittografia a chiave doppia (DKE)
description: DKE consente di proteggere i dati altamente riservati mantenendo il controllo completo della chiave.
author: kccross
ms.author: krowley
manager: laurawi
ms.date: 07/21/2020
ms.topic: conceptual
ms.service: information-protection
audience: Admin
ms.reviewer: esaggese
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.openlocfilehash: f36eeeb1f228bff48088cbbf3241d6866d0b3a21
ms.sourcegitcommit: 234726a1795d984c4659da68f852d30a4dda5711
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/18/2020
ms.locfileid: "46794165"
---
# <a name="double-key-encryption-dke"></a><span data-ttu-id="6abaa-103">Crittografia a chiave doppia (DKE)</span><span class="sxs-lookup"><span data-stu-id="6abaa-103">Double Key Encryption (DKE)</span></span>

> <span data-ttu-id="6abaa-104">*Si applica a: crittografia a chiave doppia per Microsoft 365 Public Preview, [microsoft 365 Compliance](https://www.microsoft.com/microsoft-365/business/compliance-management), [Azure Information Protection](https://azure.microsoft.com/pricing/details/information-protection)*</span><span class="sxs-lookup"><span data-stu-id="6abaa-104">*Applies to: Double Key Encryption for Microsoft 365 public preview, [Microsoft 365 Compliance](https://www.microsoft.com/microsoft-365/business/compliance-management), [Azure Information Protection](https://azure.microsoft.com/pricing/details/information-protection)*</span></span>
>
> <span data-ttu-id="6abaa-105">*Istruzioni per: [client di etichettatura unificata di Azure Information Protection per Windows](https://docs.microsoft.com/azure/information-protection/faqs#whats-the-difference-between-the-azure-information-protection-classic-and-unified-labeling-clients)*</span><span class="sxs-lookup"><span data-stu-id="6abaa-105">*Instructions for: [Azure Information Protection unified labeling client for Windows](https://docs.microsoft.com/azure/information-protection/faqs#whats-the-difference-between-the-azure-information-protection-classic-and-unified-labeling-clients)*</span></span>
>
> <span data-ttu-id="6abaa-106">*Descrizione del servizio per: [conformità di Microsoft 365](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*</span><span class="sxs-lookup"><span data-stu-id="6abaa-106">*Service description for: [Microsoft 365 Compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*</span></span>

<span data-ttu-id="6abaa-107">La crittografia a chiave doppia (DKE) utilizza due tasti insieme per accedere al contenuto protetto.</span><span class="sxs-lookup"><span data-stu-id="6abaa-107">Double Key Encryption (DKE) uses two keys together to access protected content.</span></span> <span data-ttu-id="6abaa-108">Si archivia una chiave in Microsoft Azure e si tiene premuto l'altro tasto.</span><span class="sxs-lookup"><span data-stu-id="6abaa-108">You store one key in Microsoft Azure, and you hold the other key.</span></span> <span data-ttu-id="6abaa-109">Il client Azure Information Protection Unified Labeling protegge i contenuti estremamente riservati quando si mantiene il controllo completo di una delle chiavi.</span><span class="sxs-lookup"><span data-stu-id="6abaa-109">The Azure Information Protection unified labeling client protects highly sensitive content while you maintain full control of one of your keys.</span></span>

<span data-ttu-id="6abaa-110">La crittografia a chiave doppia supporta sia le distribuzioni cloud che quelle locali.</span><span class="sxs-lookup"><span data-stu-id="6abaa-110">Double Key Encryption supports both cloud and on-premises deployments.</span></span> <span data-ttu-id="6abaa-111">Queste distribuzioni contribuiscono a garantire che i dati crittografati rimangano opachi ovunque vengano archiviati i dati protetti.</span><span class="sxs-lookup"><span data-stu-id="6abaa-111">These deployments help to ensure that encrypted data remains opaque wherever you store the protected data.</span></span>

<span data-ttu-id="6abaa-112">Per ulteriori informazioni sulle chiavi radice tenant basate su cloud predefinite, vedere [Planning and implementing your Azure Information Protection tenant Key](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key).</span><span class="sxs-lookup"><span data-stu-id="6abaa-112">For more information about the default, cloud-based tenant root keys, see [Planning and implementing your Azure Information Protection tenant key](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key).</span></span>

<!--
The following video shows how Double Key Encryption works to secure your content.

> [!VIDEO https://msit.microsoftstream.com/embed/video/f466a1ff-0400-a936-221c-f1eab45dc756]
-->

<span data-ttu-id="6abaa-113">Se le organizzazioni hanno uno dei requisiti seguenti, è possibile utilizzare DKE per proteggere il contenuto:</span><span class="sxs-lookup"><span data-stu-id="6abaa-113">If your organizations have any of the following requirements, you can use DKE to help secure your content:</span></span>

- <span data-ttu-id="6abaa-114">Si desidera garantire che sia possibile decrittografare il contenuto protetto *solo* in tutte le circostanze.</span><span class="sxs-lookup"><span data-stu-id="6abaa-114">You want to ensure that *only you* can ever decrypt protected content, under all circumstances.</span></span>
- <span data-ttu-id="6abaa-115">Non si desidera che Microsoft abbia accesso ai dati protetti da solo.</span><span class="sxs-lookup"><span data-stu-id="6abaa-115">You don't want Microsoft to have access to protected data on its own.</span></span>
- <span data-ttu-id="6abaa-116">Sono necessari requisiti normativi per mantenere le chiavi all'interno di un limite geografico.</span><span class="sxs-lookup"><span data-stu-id="6abaa-116">You have regulatory requirements to hold keys within a geographical boundary.</span></span> <span data-ttu-id="6abaa-117">Tutte le chiavi conservate per la crittografia e la decrittografia dei dati vengono mantenute nel Data Center.</span><span class="sxs-lookup"><span data-stu-id="6abaa-117">All of the keys that you hold for data encryption and decryption are maintained in your data center.</span></span>

## <a name="system-and-licensing-requirements-for-dke"></a><span data-ttu-id="6abaa-118">Requisiti di sistema e licenze per DKE</span><span class="sxs-lookup"><span data-stu-id="6abaa-118">System and licensing requirements for DKE</span></span>

<span data-ttu-id="6abaa-119">La crittografia a chiave doppia per Microsoft 365 è disponibile con Microsoft 365 E5 e Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="6abaa-119">Double Key Encryption for Microsoft 365 comes with Microsoft 365 E5 and Office 365 E5.</span></span> <span data-ttu-id="6abaa-120">Se non si dispone di una licenza Microsoft 365 E5, è possibile iscriversi per una [versione di valutazione](https://aka.ms/M365E5ComplianceTrial).</span><span class="sxs-lookup"><span data-stu-id="6abaa-120">If you don’t have a Microsoft 365 E5 license, you can sign up for a [trial](https://aka.ms/M365E5ComplianceTrial).</span></span> <span data-ttu-id="6abaa-121">Per ulteriori informazioni su queste licenze, vedere [Microsoft 365 Licensing Guidance for security & Compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span><span class="sxs-lookup"><span data-stu-id="6abaa-121">For more information about these licenses, see [Microsoft 365 licensing guidance for security & compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span></span>

<span data-ttu-id="6abaa-122">**Office Insider** Per utilizzare l'anteprima pubblica, è necessario essere membri del programma Office Insider.</span><span class="sxs-lookup"><span data-stu-id="6abaa-122">**Office Insider** To use the public preview, you must be a member of the Office Insider program.</span></span> <span data-ttu-id="6abaa-123">Per partecipare a Office Insider, accedere a [https://insider.office.com](https://insider.office.com) .</span><span class="sxs-lookup"><span data-stu-id="6abaa-123">To join Office Insider, go to [https://insider.office.com](https://insider.office.com).</span></span> <span data-ttu-id="6abaa-124">Una volta che si è membri, preparare l'ambiente per la distribuzione di Office Insider Builds scegliendo il metodo di distribuzione appropriato per la propria organizzazione.</span><span class="sxs-lookup"><span data-stu-id="6abaa-124">Once you're a member, prepare your environment to deploy Office Insider builds by choosing the right deployment method for your organization.</span></span> <span data-ttu-id="6abaa-125">Per istruzioni, vedere [Guida introduttiva alla distribuzione di Office Insider Builds](https://insider.office.com/business/deploy).</span><span class="sxs-lookup"><span data-stu-id="6abaa-125">For instructions, see [Getting started on deploying Office Insider builds](https://insider.office.com/business/deploy).</span></span>

<span data-ttu-id="6abaa-126">**Azure Information Protection**.</span><span class="sxs-lookup"><span data-stu-id="6abaa-126">**Azure Information Protection**.</span></span> <span data-ttu-id="6abaa-127">DKE funziona con le etichette di riservatezza e richiede la protezione delle informazioni di Azure.</span><span class="sxs-lookup"><span data-stu-id="6abaa-127">DKE works with sensitivity labels and requires Azure Information Protection.</span></span>

## <a name="supported-environments-for-storing-and-viewing-dke-protected-content"></a><span data-ttu-id="6abaa-128">Ambienti supportati per l'archiviazione e la visualizzazione di contenuto protetto da DKE</span><span class="sxs-lookup"><span data-stu-id="6abaa-128">Supported environments for storing and viewing DKE-protected content</span></span>

<span data-ttu-id="6abaa-129">**Applicazioni supportate**.</span><span class="sxs-lookup"><span data-stu-id="6abaa-129">**Supported applications**.</span></span> <span data-ttu-id="6abaa-130">[Microsoft 365 Apps for Enterprise](https://www.microsoft.com/microsoft-365/business/microsoft-365-apps-for-enterprise-product) clients on Windows, tra cui Word, Excel e PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="6abaa-130">[Microsoft 365 Apps for enterprise](https://www.microsoft.com/microsoft-365/business/microsoft-365-apps-for-enterprise-product) clients on Windows, including Word, Excel, and PowerPoint.</span></span>

<span data-ttu-id="6abaa-131">**Supporto per i contenuti online**.</span><span class="sxs-lookup"><span data-stu-id="6abaa-131">**Online content support**.</span></span> <span data-ttu-id="6abaa-132">Sono supportati i documenti e i file archiviati online in Microsoft SharePoint e OneDrive for business.</span><span class="sxs-lookup"><span data-stu-id="6abaa-132">Documents and files stored online in both Microsoft SharePoint and OneDrive for Business are supported.</span></span> <span data-ttu-id="6abaa-133">È possibile condividere il contenuto crittografato tramite posta elettronica, ma non è possibile visualizzare i documenti e i file crittografati online.</span><span class="sxs-lookup"><span data-stu-id="6abaa-133">You can share encrypted content by email, but you can't view encrypted documents and files online.</span></span> <span data-ttu-id="6abaa-134">Al contrario, è necessario visualizzare il contenuto protetto utilizzando le app desktop del computer locale.</span><span class="sxs-lookup"><span data-stu-id="6abaa-134">Instead, you must view protected content using the desktop apps on your local computer.</span></span>

## <a name="about-this-public-preview-article"></a><span data-ttu-id="6abaa-135">Informazioni sull'articolo relativo all'anteprima pubblica</span><span class="sxs-lookup"><span data-stu-id="6abaa-135">About this public preview article</span></span>

<span data-ttu-id="6abaa-136">Sono disponibili diversi modi per completare alcuni passaggi per la distribuzione della crittografia a chiave doppia.</span><span class="sxs-lookup"><span data-stu-id="6abaa-136">There are several ways you can complete some of the steps to deploy Double Key Encryption.</span></span> <span data-ttu-id="6abaa-137">In questo articolo vengono fornite istruzioni dettagliate per consentire agli amministratori meno esperti di distribuire correttamente il servizio.</span><span class="sxs-lookup"><span data-stu-id="6abaa-137">This article provides detailed instructions so that less experienced admins successfully deploy the service.</span></span> <span data-ttu-id="6abaa-138">Se si ha familiarità con questo metodo, è possibile scegliere di utilizzare i propri metodi.</span><span class="sxs-lookup"><span data-stu-id="6abaa-138">If you're comfortable doing so, you can choose to use your own methods.</span></span>

<span data-ttu-id="6abaa-139">In questo articolo sono incluse istruzioni dettagliate su come distribuire il servizio di crittografia a chiave doppia in Azure.</span><span class="sxs-lookup"><span data-stu-id="6abaa-139">This article includes step-by-step instructions on how to deploy the Double Key Encryption service to Azure.</span></span> <span data-ttu-id="6abaa-140">Questo scenario non è qualcosa che si potrebbe fare in produzione.</span><span class="sxs-lookup"><span data-stu-id="6abaa-140">This scenario isn't something you'd likely do in production.</span></span> <span data-ttu-id="6abaa-141">Per l'anteprima pubblica, l'utilizzo di Azure rappresenta una soluzione rapida per la distribuzione di DKE.</span><span class="sxs-lookup"><span data-stu-id="6abaa-141">For public preview, using Azure is a quick way to deploy DKE.</span></span> <span data-ttu-id="6abaa-142">La distribuzione in Azure consente di iniziare a usare la crittografia a chiave doppia immediatamente.</span><span class="sxs-lookup"><span data-stu-id="6abaa-142">Deploying to Azure lets you get started using Double Key Encryption right away.</span></span>

<span data-ttu-id="6abaa-143">È possibile distribuire il servizio localmente sulla rete o con un altro provider.</span><span class="sxs-lookup"><span data-stu-id="6abaa-143">You can deploy the service locally on your network or with another provider.</span></span> <span data-ttu-id="6abaa-144">Sarà necessario pubblicare l'archivio chiavi utilizzando metodi adatti per tale percorso.</span><span class="sxs-lookup"><span data-stu-id="6abaa-144">You'll need to publish the key store using methods that are appropriate for that location.</span></span>

## <a name="deploy-double-key-encryption"></a><span data-ttu-id="6abaa-145">Distribuire la crittografia a chiave doppia</span><span class="sxs-lookup"><span data-stu-id="6abaa-145">Deploy Double Key Encryption</span></span>

<span data-ttu-id="6abaa-146">Questo articolo e il video sulla distribuzione utilizzano Azure come destinazione di distribuzione per il servizio DKE.</span><span class="sxs-lookup"><span data-stu-id="6abaa-146">This article and the deployment video use Azure as the deployment destination for the DKE service.</span></span> <span data-ttu-id="6abaa-147">Se si esegue la distribuzione in un'altra posizione, è necessario fornire i propri valori.</span><span class="sxs-lookup"><span data-stu-id="6abaa-147">If you're deploying to another location, you'll need to provide your own values.</span></span>

<span data-ttu-id="6abaa-148">Guardare il [video sulla distribuzione di crittografia a chiave doppia](https://youtu.be/vDWfHN_kygg) per visualizzare la panoramica dettagliata dei concetti nell'articolo.</span><span class="sxs-lookup"><span data-stu-id="6abaa-148">Watch the [Double Key Encryption deployment video](https://youtu.be/vDWfHN_kygg) to see step-by-step overview of concepts in the article.</span></span> <span data-ttu-id="6abaa-149">Il video richiede circa 18 minuti per il completamento.</span><span class="sxs-lookup"><span data-stu-id="6abaa-149">The video takes about 18 minutes to complete.</span></span>

<span data-ttu-id="6abaa-150">Seguire questi passaggi generali per configurare la crittografia a chiave doppia per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="6abaa-150">You'll follow these general steps to set up Double Key Encryption for your organization.</span></span>

1. [<span data-ttu-id="6abaa-151">Installare i prerequisiti software</span><span class="sxs-lookup"><span data-stu-id="6abaa-151">Install software prerequisites</span></span>](#install-software-prerequisites)
1. [<span data-ttu-id="6abaa-152">Clonare il repository di crittografia GitHub a doppio tasto</span><span class="sxs-lookup"><span data-stu-id="6abaa-152">Clone the Double Key Encryption GitHub repository</span></span>](#clone-the-dke-github-repository)
1. [<span data-ttu-id="6abaa-153">Modificare le impostazioni dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="6abaa-153">Modify application settings</span></span>](#modify-application-settings)
1. [<span data-ttu-id="6abaa-154">Generare i tasti di testing</span><span class="sxs-lookup"><span data-stu-id="6abaa-154">Generate test keys</span></span>](#generate-test-keys)
1. [<span data-ttu-id="6abaa-155">Generare il progetto</span><span class="sxs-lookup"><span data-stu-id="6abaa-155">Build the project</span></span>](#build-the-project)
1. [<span data-ttu-id="6abaa-156">Pubblicare l'archivio delle chiavi</span><span class="sxs-lookup"><span data-stu-id="6abaa-156">Publish the key store</span></span>](#publish-the-key-store)
1. [<span data-ttu-id="6abaa-157">Convalidare la distribuzione</span><span class="sxs-lookup"><span data-stu-id="6abaa-157">Validate your deployment</span></span>](#validate-your-deployment)
1. [<span data-ttu-id="6abaa-158">Registrare il proprio archivio delle chiavi</span><span class="sxs-lookup"><span data-stu-id="6abaa-158">Register your key store</span></span>](#register-your-key-store)
1. [<span data-ttu-id="6abaa-159">Creare etichette di riservatezza</span><span class="sxs-lookup"><span data-stu-id="6abaa-159">Create sensitivity labels</span></span>](#create-labels-using-dke)

<span data-ttu-id="6abaa-160">Al termine, è possibile crittografare documenti e file utilizzando DKE.</span><span class="sxs-lookup"><span data-stu-id="6abaa-160">When you're done, you can encrypt documents and files using DKE.</span></span> <span data-ttu-id="6abaa-161">Per informazioni, vedere [applicare etichette di riservatezza ai propri file e messaggi di posta elettronica in Office](https://support.microsoft.com/office/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9).</span><span class="sxs-lookup"><span data-stu-id="6abaa-161">For information, see [Apply sensitivity labels to your files and email in Office](https://support.microsoft.com/office/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9).</span></span>

### <a name="install-software-prerequisites"></a><span data-ttu-id="6abaa-162">Installare i prerequisiti software</span><span class="sxs-lookup"><span data-stu-id="6abaa-162">Install software prerequisites</span></span>

<span data-ttu-id="6abaa-163">Esistono due tipi di prerequisiti software per la crittografia a chiave doppia</span><span class="sxs-lookup"><span data-stu-id="6abaa-163">There are two types of software prerequisites for Double Key Encryption</span></span>

- [<span data-ttu-id="6abaa-164">Prerequisiti del servizio di crittografia a doppia chiave</span><span class="sxs-lookup"><span data-stu-id="6abaa-164">Double Key Encryption service prerequisites</span></span>](#double-key-encryption-service-prerequisites)
- [<span data-ttu-id="6abaa-165">Prerequisiti per la crittografia a chiave doppia per i computer client</span><span class="sxs-lookup"><span data-stu-id="6abaa-165">Double Key Encryption prerequisites for client computers</span></span>](#double-key-encryption-prerequisites-for-client-computers)

#### <a name="double-key-encryption-service-prerequisites"></a><span data-ttu-id="6abaa-166">Prerequisiti del servizio di crittografia a doppia chiave</span><span class="sxs-lookup"><span data-stu-id="6abaa-166">Double Key Encryption service prerequisites</span></span>

<span data-ttu-id="6abaa-167">Installare questi prerequisiti nel computer in cui si desidera installare il servizio DKE.</span><span class="sxs-lookup"><span data-stu-id="6abaa-167">Install these prerequisites on the computer where you want to install the DKE service.</span></span>

<span data-ttu-id="6abaa-168">**.NET Core 3,1 SDK**.</span><span class="sxs-lookup"><span data-stu-id="6abaa-168">**.NET Core 3.1 SDK**.</span></span> <span data-ttu-id="6abaa-169">Scaricare e installare l'SDK da [download .NET Core 3,1](https://dotnet.microsoft.com/download/dotnet-core/3.1).</span><span class="sxs-lookup"><span data-stu-id="6abaa-169">Download and install the SDK from [Download .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1).</span></span>

<span data-ttu-id="6abaa-170">**Codice Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="6abaa-170">**Visual Studio Code**.</span></span> <span data-ttu-id="6abaa-171">Scaricare il codice di Visual Studio da [https://code.visualstudio.com/](https://code.visualstudio.com) .</span><span class="sxs-lookup"><span data-stu-id="6abaa-171">Download Visual Studio Code from [https://code.visualstudio.com/](https://code.visualstudio.com).</span></span> <span data-ttu-id="6abaa-172">Una volta installato, eseguire codice Visual Studio e selezionare **Visualizza** \> **estensioni**.</span><span class="sxs-lookup"><span data-stu-id="6abaa-172">Once installed, run Visual Studio Code and select **View** \> **Extensions**.</span></span> <span data-ttu-id="6abaa-173">Installare queste estensioni.</span><span class="sxs-lookup"><span data-stu-id="6abaa-173">Install these extensions.</span></span>

- <span data-ttu-id="6abaa-174">C# per Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="6abaa-174">C# for Visual Studio Code</span></span>

- <span data-ttu-id="6abaa-175">Gestione pacchetti NuGet</span><span class="sxs-lookup"><span data-stu-id="6abaa-175">NuGet Package Manager</span></span>

<span data-ttu-id="6abaa-176">**Microsoft Office Insider**.</span><span class="sxs-lookup"><span data-stu-id="6abaa-176">**Microsoft Office Insider**.</span></span> <span data-ttu-id="6abaa-177">Configurare almeno un metodo di [distribuzione](https://insider.office.com/business/deploy).</span><span class="sxs-lookup"><span data-stu-id="6abaa-177">Set up at least one [deployment method](https://insider.office.com/business/deploy).</span></span>

<span data-ttu-id="6abaa-178">**Risorse git**.</span><span class="sxs-lookup"><span data-stu-id="6abaa-178">**Git resources**.</span></span> <span data-ttu-id="6abaa-179">Scaricare e installare una delle opzioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="6abaa-179">Download and install one of the following.</span></span>

- [<span data-ttu-id="6abaa-180">Git</span><span class="sxs-lookup"><span data-stu-id="6abaa-180">Git</span></span>](https://git-scm.com/downloads)

- [<span data-ttu-id="6abaa-181">GitHub desktop</span><span class="sxs-lookup"><span data-stu-id="6abaa-181">GitHub Desktop</span></span>](https://desktop.github.com/)

- [<span data-ttu-id="6abaa-182">GitHub Enterprise</span><span class="sxs-lookup"><span data-stu-id="6abaa-182">GitHub Enterprise</span></span>](https://github.com/enterprise)

<span data-ttu-id="6abaa-183">**Openssl** È necessario avere installato [openssl](https://slproweb.com/products/Win32OpenSSL.html) per [generare le chiavi di test](#generate-test-keys) dopo la distribuzione di DKE.</span><span class="sxs-lookup"><span data-stu-id="6abaa-183">**OpenSSL** You must have [OpenSSL](https://slproweb.com/products/Win32OpenSSL.html) installed to [generate test keys](#generate-test-keys) after you deploy DKE.</span></span> <span data-ttu-id="6abaa-184">Assicurarsi di richiamarlo correttamente dal percorso delle variabili di ambiente.</span><span class="sxs-lookup"><span data-stu-id="6abaa-184">Make sure you're invoking it correctly from your environment variables path.</span></span> <span data-ttu-id="6abaa-185">Ad esempio, vedere la sezione "aggiungere la directory di installazione al percorso" https://www.osradar.com/install-openssl-windows/ per informazioni dettagliate.</span><span class="sxs-lookup"><span data-stu-id="6abaa-185">For example, see "Add the installation directory to PATH" at https://www.osradar.com/install-openssl-windows/ for details.</span></span>

#### <a name="double-key-encryption-prerequisites-for-client-computers"></a><span data-ttu-id="6abaa-186">Prerequisiti per la crittografia a chiave doppia per i computer client</span><span class="sxs-lookup"><span data-stu-id="6abaa-186">Double Key Encryption prerequisites for client computers</span></span>

<span data-ttu-id="6abaa-187">Installare questi prerequisiti su ogni computer client in cui si desidera proteggere e utilizzare documenti protetti.</span><span class="sxs-lookup"><span data-stu-id="6abaa-187">Install these prerequisites on each client computer where you want to protect and consume protected documents.</span></span>

<span data-ttu-id="6abaa-188">**Microsoft Office** Version \*. 12711 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="6abaa-188">**Microsoft Office** version \*.12711 or later.</span></span>

<span data-ttu-id="6abaa-189">**Azure Information Protection Unified Labeling client** Versions 2.7.93.0 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="6abaa-189">**Azure Information Protection Unified Labeling Client** versions 2.7.93.0 or later.</span></span> <span data-ttu-id="6abaa-190">Scaricare e installare il client Unified Labeling da [Microsoft](https://www.microsoft.com/download/details.aspx?id=53018).</span><span class="sxs-lookup"><span data-stu-id="6abaa-190">Download and install the Unified Labeling client from [Microsoft](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>

### <a name="clone-the-dke-github-repository"></a><span data-ttu-id="6abaa-191">Clonare il repository di DKE GitHub</span><span class="sxs-lookup"><span data-stu-id="6abaa-191">Clone the DKE GitHub repository</span></span>

<span data-ttu-id="6abaa-192">Microsoft fornisce i file di origine di DKE in un repository GitHub.</span><span class="sxs-lookup"><span data-stu-id="6abaa-192">Microsoft supplies the DKE source files in a GitHub repository.</span></span> <span data-ttu-id="6abaa-193">È possibile clonare il repository per creare il progetto localmente per l'utilizzo dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="6abaa-193">You clone the repository to build the project locally for your organization's use.</span></span> <span data-ttu-id="6abaa-194">L'archivio di DKE GitHub si trova in [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService) .</span><span class="sxs-lookup"><span data-stu-id="6abaa-194">The DKE GitHub repository is located at [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService).</span></span>

<span data-ttu-id="6abaa-195">Le istruzioni riportate di seguito sono destinate agli utenti di codice git o Visual Studio inesperti:</span><span class="sxs-lookup"><span data-stu-id="6abaa-195">The following instructions are intended for inexperienced git or Visual Studio Code users:</span></span>

1. <span data-ttu-id="6abaa-196">Nel browser, vai a: [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService)</span><span class="sxs-lookup"><span data-stu-id="6abaa-196">In your browser, go to: [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService)</span></span>

1. <span data-ttu-id="6abaa-197">Verso il lato destro dello schermo, selezionare **codice**.</span><span class="sxs-lookup"><span data-stu-id="6abaa-197">Towards the right side of the screen, select **Code**.</span></span> <span data-ttu-id="6abaa-198">La versione dell'interfaccia utente potrebbe mostrare un pulsante **Clone o download** .</span><span class="sxs-lookup"><span data-stu-id="6abaa-198">Your version of the UI might show a **Clone or download** button.</span></span> <span data-ttu-id="6abaa-199">Quindi, nell'elenco a discesa che viene visualizzato, selezionare l'icona copia per copiare l'URL negli Appunti.</span><span class="sxs-lookup"><span data-stu-id="6abaa-199">Then, in the dropdown that appears, select the copy icon to copy the URL to your clipboard.</span></span>

    <span data-ttu-id="6abaa-200">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="6abaa-200">For example:</span></span>

   ![Clonare il repository del servizio di crittografia a chiave doppia da GitHub](../media/dke-clone.png)

3. <span data-ttu-id="6abaa-202">In Visual Studio Code, selezionare **Visualizza** \> **tavolozza dei comandi** e selezionare **git: Clone**.</span><span class="sxs-lookup"><span data-stu-id="6abaa-202">In Visual Studio Code, select **View** \> **Command Palette** and select **Git: Clone**.</span></span> <span data-ttu-id="6abaa-203">Per passare all'opzione nell'elenco, iniziare `git: clone` a digitare per filtrare le voci e quindi selezionarla dal menu a discesa.</span><span class="sxs-lookup"><span data-stu-id="6abaa-203">To jump to the option in the list, start typing `git: clone` to filter the entries and then select it from the drop-down.</span></span> <span data-ttu-id="6abaa-204">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="6abaa-204">For example:</span></span>

   ![Codice Visual Studio GIT: opzione Clone](../media/dke-vscode-clone.png)

4. <span data-ttu-id="6abaa-206">Nella casella di testo incollare l'URL copiato da git e selezionare **Clone da GitHub**.</span><span class="sxs-lookup"><span data-stu-id="6abaa-206">In the text box, paste the URL that you copied from Git and select **Clone from GitHub**.</span></span>

5. <span data-ttu-id="6abaa-207">Nella finestra di dialogo **Seleziona cartella** visualizzata passare a e selezionare un percorso in cui archiviare il repository.</span><span class="sxs-lookup"><span data-stu-id="6abaa-207">In the **Select Folder** dialog that appears, browse to and select a location to store the repository.</span></span> <span data-ttu-id="6abaa-208">Al prompt dei comandi, selezionare **Apri**.</span><span class="sxs-lookup"><span data-stu-id="6abaa-208">At the prompt, select **Open**.</span></span>

    <span data-ttu-id="6abaa-209">L'archivio viene aperto in Visual Studio Code e visualizza il ramo git corrente in basso a sinistra.</span><span class="sxs-lookup"><span data-stu-id="6abaa-209">The repository is opened in Visual Studio Code, and displays the current Git branch at the bottom left.</span></span> <span data-ttu-id="6abaa-210">La succursale deve essere **Master**.</span><span class="sxs-lookup"><span data-stu-id="6abaa-210">The branch should be **master**.</span></span>

    <span data-ttu-id="6abaa-211">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="6abaa-211">For example:</span></span>

   ![Branch Master di Visual Studio Code](../media/dke-vscode-master.png)

6. <span data-ttu-id="6abaa-213">Selezionare il **Master** di Word e quindi selezionare **public_preview** nell'elenco dei rami.</span><span class="sxs-lookup"><span data-stu-id="6abaa-213">Select the word **master,** and then select **public_preview** from the list of branches.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="6abaa-214">Selezionando il ramo public_preview si garantisce che siano presenti i file corretti per la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="6abaa-214">Selecting the public_preview branch ensures that you have the correct files to build the project.</span></span> <span data-ttu-id="6abaa-215">Se non si sceglie la succursale corretta, la distribuzione avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="6abaa-215">If you do not choose the correct branch your deployment will fail.</span></span>

<span data-ttu-id="6abaa-216">È ora necessario configurare l'archivio di origine di DKE localmente.</span><span class="sxs-lookup"><span data-stu-id="6abaa-216">You now have your DKE source repository set up locally.</span></span> <span data-ttu-id="6abaa-217">Successivamente, [modificare le impostazioni dell'applicazione](#modify-application-settings) per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="6abaa-217">Next, [modify application settings](#modify-application-settings) for your organization.</span></span>

### <a name="modify-application-settings"></a><span data-ttu-id="6abaa-218">Modificare le impostazioni dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="6abaa-218">Modify application settings</span></span>

<span data-ttu-id="6abaa-219">Per distribuire il servizio DKE, è necessario modificare i tipi di impostazioni dell'applicazione seguenti:</span><span class="sxs-lookup"><span data-stu-id="6abaa-219">To deploy the DKE service, you must modify the following types of application settings:</span></span>

- [<span data-ttu-id="6abaa-220">Impostazioni di accesso alle chiavi</span><span class="sxs-lookup"><span data-stu-id="6abaa-220">Key access settings</span></span>](#key-access-settings)
- [<span data-ttu-id="6abaa-221">Impostazioni del tenant e delle chiavi</span><span class="sxs-lookup"><span data-stu-id="6abaa-221">Tenant and key settings</span></span>](#tenant-and-key-settings)

<span data-ttu-id="6abaa-222">È possibile modificare le impostazioni dell'applicazione nel appsettings.jssu file.</span><span class="sxs-lookup"><span data-stu-id="6abaa-222">You modify application settings in the appsettings.json file.</span></span> <span data-ttu-id="6abaa-223">Questo file si trova nel repo di DoubleKeyEncryptionService clonato localmente in DoubleKeyEncryptionService\src\customer-key-store.</span><span class="sxs-lookup"><span data-stu-id="6abaa-223">This file is located in the DoubleKeyEncryptionService repo you cloned locally under DoubleKeyEncryptionService\src\customer-key-store.</span></span> <span data-ttu-id="6abaa-224">Ad esempio, in Visual Studio Code è possibile passare al file come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="6abaa-224">For example, in Visual Studio Code, you can browse to the file as shown in the following picture.</span></span>

![Individuazione del appsettings.jssu file per DKE.](../media/dke-appsettingsjson.png)

#### <a name="key-access-settings"></a><span data-ttu-id="6abaa-226">Impostazioni di accesso alle chiavi</span><span class="sxs-lookup"><span data-stu-id="6abaa-226">Key access settings</span></span>

<span data-ttu-id="6abaa-227">Scegliere se utilizzare la posta elettronica o l'autorizzazione di ruolo.</span><span class="sxs-lookup"><span data-stu-id="6abaa-227">Choose whether to use email or role authorization.</span></span> <span data-ttu-id="6abaa-228">DKE supporta solo uno di questi metodi di autenticazione alla volta.</span><span class="sxs-lookup"><span data-stu-id="6abaa-228">DKE supports only one of these authentication methods at a time.</span></span>

- <span data-ttu-id="6abaa-229">**Autorizzazione per la posta elettronica**.</span><span class="sxs-lookup"><span data-stu-id="6abaa-229">**Email authorization**.</span></span> <span data-ttu-id="6abaa-230">Consente all'organizzazione di autorizzare l'accesso alle chiavi solo in base agli indirizzi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="6abaa-230">Allows your organization to authorize access to keys based on email addresses only.</span></span>

- <span data-ttu-id="6abaa-231">**Autorizzazione ruolo**.</span><span class="sxs-lookup"><span data-stu-id="6abaa-231">**Role authorization**.</span></span> <span data-ttu-id="6abaa-232">Consente all'organizzazione di autorizzare l'accesso ai tasti basati su gruppi di Active Directory e richiede che il servizio Web possa eseguire query su LDAP.</span><span class="sxs-lookup"><span data-stu-id="6abaa-232">Allows your organization to authorize access to keys based on Active Directory groups, and requires that the web service can query LDAP.</span></span>

<span data-ttu-id="6abaa-233">**Per impostare le impostazioni di accesso alle chiavi per DKE utilizzando l'autorizzazione per la posta elettronica**</span><span class="sxs-lookup"><span data-stu-id="6abaa-233">**To set key access settings for DKE using email authorization**</span></span>

1. <span data-ttu-id="6abaa-234">Aprire il **appsettings.jssu** file e individuare l' `AuthorizedEmailAddress` impostazione.</span><span class="sxs-lookup"><span data-stu-id="6abaa-234">Open the **appsettings.json** file and locate the `AuthorizedEmailAddress` setting.</span></span>

2. <span data-ttu-id="6abaa-235">Aggiungere l'indirizzo o gli indirizzi di posta elettronica che si desidera autorizzare.</span><span class="sxs-lookup"><span data-stu-id="6abaa-235">Add the email address or addresses that you want to authorize.</span></span> <span data-ttu-id="6abaa-236">Separare più indirizzi di posta elettronica con virgolette doppie e virgole.</span><span class="sxs-lookup"><span data-stu-id="6abaa-236">Separate multiple email addresses with double quotes and commas.</span></span> <span data-ttu-id="6abaa-237">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="6abaa-237">For example:</span></span>

   ```json
   "AuthorizedEmailAddress": ["email1@company.com", "email2@company.com ", "email3@company.com"]
   ```

3. <span data-ttu-id="6abaa-238">Individuare l' `LDAPPath` impostazione e rimuovere il testo `If role authorization is used then this is the LDAP path` tra virgolette doppie.</span><span class="sxs-lookup"><span data-stu-id="6abaa-238">Locate the `LDAPPath` setting and remove the text `If role authorization is used then this is the LDAP path` between the double quotes.</span></span> <span data-ttu-id="6abaa-239">Lasciare le virgolette doppie sul posto.</span><span class="sxs-lookup"><span data-stu-id="6abaa-239">Leave the double quotes in place.</span></span> <span data-ttu-id="6abaa-240">Al termine, l'impostazione dovrebbe essere simile alla seguente.</span><span class="sxs-lookup"><span data-stu-id="6abaa-240">When you're finished, the setting should look like this.</span></span>

   ```json
   "LDAPPath": ""
   ```

4. <span data-ttu-id="6abaa-241">Individuare l' `AuthorizedRoles` impostazione ed eliminare l'intera riga.</span><span class="sxs-lookup"><span data-stu-id="6abaa-241">Locate the `AuthorizedRoles` setting and delete the entire line.</span></span>

<span data-ttu-id="6abaa-242">Questa immagine Visualizza il **appsettings.jssu** file formattato correttamente per l'autorizzazione della posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="6abaa-242">This image shows the **appsettings.json** file correctly formatted for email authorization.</span></span>

   ![Il appsettings.jsnel file che mostra il metodo di autorizzazione della posta elettronica](../media/dke-email-accesssetting.png)

<span data-ttu-id="6abaa-244">**Per impostare le impostazioni di accesso alle chiavi per DKE utilizzando l'autorizzazione ruolo**</span><span class="sxs-lookup"><span data-stu-id="6abaa-244">**To set key access settings for DKE using role authorization**</span></span>

1. <span data-ttu-id="6abaa-245">Aprire il **appsettings.jssu** file e individuare l' `AuthorizedRoles` impostazione.</span><span class="sxs-lookup"><span data-stu-id="6abaa-245">Open the **appsettings.json** file and locate the `AuthorizedRoles` setting.</span></span>

2. <span data-ttu-id="6abaa-246">Aggiungere i nomi dei gruppi di Active Directory che si desidera autorizzare.</span><span class="sxs-lookup"><span data-stu-id="6abaa-246">Add the Active Directory group names you want to authorize.</span></span> <span data-ttu-id="6abaa-247">Separare più nomi di gruppi con virgolette doppie e virgole.</span><span class="sxs-lookup"><span data-stu-id="6abaa-247">Separate multiple group names with double quotes and commas.</span></span> <span data-ttu-id="6abaa-248">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="6abaa-248">For example:</span></span>

   ```json
   "AuthorizedRoles": ["group1", "group2", "group3"]
   ```

3. <span data-ttu-id="6abaa-249">Individuare l' `LDAPPath` impostazione e aggiungere il dominio di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="6abaa-249">Locate the `LDAPPath` setting and add the Active Directory domain.</span></span> <span data-ttu-id="6abaa-250">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="6abaa-250">For example:</span></span>

   ```json
   "LDAPPath": "contoso.com"
   ```

4. <span data-ttu-id="6abaa-251">Individuare l' `AuthorizedEmailAddress` impostazione ed eliminare l'intera riga.</span><span class="sxs-lookup"><span data-stu-id="6abaa-251">Locate the `AuthorizedEmailAddress` setting and delete the entire line.</span></span>

<span data-ttu-id="6abaa-252">Questa immagine Visualizza il **appsettings.jssu** file formattato correttamente per l'autorizzazione di ruolo.</span><span class="sxs-lookup"><span data-stu-id="6abaa-252">This image shows the **appsettings.json** file correctly formatted for role authorization.</span></span>

   ![appsettings.jsnel file che mostra il metodo di autorizzazione ruolo](../media/dke-role-accesssetting.png)

#### <a name="tenant-and-key-settings"></a><span data-ttu-id="6abaa-254">Impostazioni del tenant e delle chiavi</span><span class="sxs-lookup"><span data-stu-id="6abaa-254">Tenant and key settings</span></span>

<span data-ttu-id="6abaa-255">Le impostazioni del tenant e delle chiavi di DKE si trovano nel **appsettings.jssu** file.</span><span class="sxs-lookup"><span data-stu-id="6abaa-255">DKE tenant and key settings are located in the **appsettings.json** file.</span></span>

<span data-ttu-id="6abaa-256">**Per configurare le impostazioni relative a tenant e chiavi per DKE**</span><span class="sxs-lookup"><span data-stu-id="6abaa-256">**To configure tenant and key settings for DKE**</span></span>

1. <span data-ttu-id="6abaa-257">Aprire la **appsettings.jssu** file.</span><span class="sxs-lookup"><span data-stu-id="6abaa-257">Open the **appsettings.json** file.</span></span>

2. <span data-ttu-id="6abaa-258">Individuare l' `ValidIssuers` impostazione e sostituirla `<tenantid>` con l'ID tenant.</span><span class="sxs-lookup"><span data-stu-id="6abaa-258">Locate the `ValidIssuers` setting and replace `<tenantid>` with your tenant ID.</span></span> <span data-ttu-id="6abaa-259">È possibile individuare l'ID tenant accedendo al portale di Azure e visualizzando le [proprietà del tenant](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span><span class="sxs-lookup"><span data-stu-id="6abaa-259">You can locate your tenant ID by going to the Azure portal and viewing the [tenant properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span> <span data-ttu-id="6abaa-260">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="6abaa-260">For example:</span></span>

   ```json
   "ValidIssuers": [
     "https://sts.windows.net/9c99431e-b513-44be-a7d9-e7b500002d4b/"
   ]
   ```

<span data-ttu-id="6abaa-261">Individuare il `JwtAudience` .</span><span class="sxs-lookup"><span data-stu-id="6abaa-261">Locate the `JwtAudience`.</span></span> <span data-ttu-id="6abaa-262">Sostituire `<yourhostname>` con il nome host del computer in cui verrà eseguito il servizio DKE.</span><span class="sxs-lookup"><span data-stu-id="6abaa-262">Replace `<yourhostname>` with the hostname of the machine where the DKE service will run.</span></span> <span data-ttu-id="6abaa-263">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="6abaa-263">For example:</span></span>



  > [!IMPORTANT]
  > <span data-ttu-id="6abaa-264">Il valore per `JwtAudience` deve corrispondere *esattamente*al nome dell'host.</span><span class="sxs-lookup"><span data-stu-id="6abaa-264">The value for `JwtAudience` must match the name of your host *exactly*.</span></span> <span data-ttu-id="6abaa-265">È possibile utilizzare **localhost: 5001** durante il debug.</span><span class="sxs-lookup"><span data-stu-id="6abaa-265">You may use **localhost:5001** while debugging.</span></span> <span data-ttu-id="6abaa-266">Tuttavia, al termine del debug, aggiornare questo valore al nome host del server.</span><span class="sxs-lookup"><span data-stu-id="6abaa-266">However, When you're done debugging, make sure to update this value to the server's hostname.</span></span>

- <span data-ttu-id="6abaa-267">`TestKeys:Name`.</span><span class="sxs-lookup"><span data-stu-id="6abaa-267">`TestKeys:Name`.</span></span> <span data-ttu-id="6abaa-268">Immettere un nome per la chiave.</span><span class="sxs-lookup"><span data-stu-id="6abaa-268">Enter a name for your key.</span></span> <span data-ttu-id="6abaa-269">Ad esempio: `TestKey1`</span><span class="sxs-lookup"><span data-stu-id="6abaa-269">For example: `TestKey1`</span></span>
- <span data-ttu-id="6abaa-270">`TestKeys:Id`.</span><span class="sxs-lookup"><span data-stu-id="6abaa-270">`TestKeys:Id`.</span></span> <span data-ttu-id="6abaa-271">Creare un GUID e immetterlo come `TestKeys:ID` valore.</span><span class="sxs-lookup"><span data-stu-id="6abaa-271">Create a GUID and enter it as the `TestKeys:ID` value.</span></span> <span data-ttu-id="6abaa-272">Ad esempio, `DCE1CC21-FF9B-4424-8FF4-9914BD19A1BE`.</span><span class="sxs-lookup"><span data-stu-id="6abaa-272">For example, `DCE1CC21-FF9B-4424-8FF4-9914BD19A1BE`.</span></span> <span data-ttu-id="6abaa-273">È possibile utilizzare un sito come [Generatore di GUID online](https://guidgenerator.com/) per generare casualmente un GUID.</span><span class="sxs-lookup"><span data-stu-id="6abaa-273">You can use a site like [Online GUID Generator](https://guidgenerator.com/) to randomly generate a GUID.</span></span>

<span data-ttu-id="6abaa-274">Questa immagine Visualizza il formato corretto per le impostazioni dei tenant e delle chiavi in **appsettings.jsattiva**.</span><span class="sxs-lookup"><span data-stu-id="6abaa-274">This image shows the correct format for tenant and keys settings in **appsettings.json**.</span></span> <span data-ttu-id="6abaa-275">`LDAPPath` è configurata per l'autorizzazione di ruolo.</span><span class="sxs-lookup"><span data-stu-id="6abaa-275">`LDAPPath` is configured for role authorization.</span></span>

![Visualizza le impostazioni relative ai tenant e ai tasti corretti per DKE nel appsettings.jssu file.](../media/dke-appsettingsjson-tenantkeysettings.png)

### <a name="generate-test-keys"></a><span data-ttu-id="6abaa-277">Generare i tasti di testing</span><span class="sxs-lookup"><span data-stu-id="6abaa-277">Generate test keys</span></span>

<span data-ttu-id="6abaa-278">Una volta definite le impostazioni dell'applicazione, si è pronti a generare chiavi di test pubbliche e private.</span><span class="sxs-lookup"><span data-stu-id="6abaa-278">Once you have your application settings defined, you're ready to generate public and private test keys.</span></span>

<span data-ttu-id="6abaa-279">Per generare chiavi:</span><span class="sxs-lookup"><span data-stu-id="6abaa-279">To generate keys:</span></span>

1. <span data-ttu-id="6abaa-280">Dal menu Start di Windows, eseguire il prompt dei comandi di OpenSSL.</span><span class="sxs-lookup"><span data-stu-id="6abaa-280">From the Windows Start menu, run the OpenSSL Command Prompt.</span></span>

1. <span data-ttu-id="6abaa-281">Passare alla cartella in cui si desidera salvare i tasti di test.</span><span class="sxs-lookup"><span data-stu-id="6abaa-281">Change to the folder where you want to save the test keys.</span></span> <span data-ttu-id="6abaa-282">I file creati eseguendo la procedura descritta in questa attività sono archiviati nella stessa cartella.</span><span class="sxs-lookup"><span data-stu-id="6abaa-282">The files you create by completing the steps in this task are stored in the same folder.</span></span>

1. <span data-ttu-id="6abaa-283">Generare il nuovo tasto di test.</span><span class="sxs-lookup"><span data-stu-id="6abaa-283">Generate the new test key.</span></span>

   ```dos
   openssl req -x509 -newkey rsa:2048 -keyout key.pem -out cert.pem -days 365
   ```

2. <span data-ttu-id="6abaa-284">Generare la chiave privata.</span><span class="sxs-lookup"><span data-stu-id="6abaa-284">Generate the private key.</span></span>

   ```dos
   openssl rsa -in key.pem -out privkeynopass.pem
   ```

1. <span data-ttu-id="6abaa-285">Generare la chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="6abaa-285">Generate the public key.</span></span>

   ```dos
   openssl rsa -in key.pem -pubout > pubkeyonly.pem
   ```

1. <span data-ttu-id="6abaa-286">In un editor di testo aprire **pubkeyonly. pem**.</span><span class="sxs-lookup"><span data-stu-id="6abaa-286">In a text editor, open **pubkeyonly.pem**.</span></span> <span data-ttu-id="6abaa-287">Copiare tutto il contenuto del file **pubkeyonly. pem** , tranne la prima e l'ultima riga, nella `PublicPem` sezione del **appsettings.jssu** file.</span><span class="sxs-lookup"><span data-stu-id="6abaa-287">Copy all of the content in the **pubkeyonly.pem** file, except the first and last lines, into the `PublicPem` section of the **appsettings.json** file.</span></span>

1. <span data-ttu-id="6abaa-288">In un editor di testo aprire **privkeynopass. pem**.</span><span class="sxs-lookup"><span data-stu-id="6abaa-288">In a text editor, open **privkeynopass.pem**.</span></span> <span data-ttu-id="6abaa-289">Copiare tutto il contenuto del file **privkeynopass. pem** , tranne la prima e l'ultima riga, nella `PrivatePem` sezione del **appsettings.jssu** file.</span><span class="sxs-lookup"><span data-stu-id="6abaa-289">Copy all of the content in the **privkeynopass.pem** file, except the first and last lines, into the `PrivatePem` section of the **appsettings.json** file.</span></span>

1. <span data-ttu-id="6abaa-290">Rimuovere tutti gli spazi vuoti e le nuove righe in entrambe le `PublicPem` `PrivatePem` sezioni e.</span><span class="sxs-lookup"><span data-stu-id="6abaa-290">Remove all blank spaces and newlines in both the `PublicPem` and `PrivatePem` sections.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="6abaa-291">Quando si copia questo contenuto, non eliminare i dati PEM.</span><span class="sxs-lookup"><span data-stu-id="6abaa-291">When you copy this content, do not delete any of the PEM data.</span></span>

1. <span data-ttu-id="6abaa-292">In Visual Studio Code passare al file **Startup.cs** .</span><span class="sxs-lookup"><span data-stu-id="6abaa-292">In Visual Studio Code, browse to the **Startup.cs** file.</span></span> <span data-ttu-id="6abaa-293">Questo file si trova nel repo di DoubleKeyEncryptionService clonato localmente in DoubleKeyEncryptionService\src\customer-key-store\.</span><span class="sxs-lookup"><span data-stu-id="6abaa-293">This file is located in the DoubleKeyEncryptionService repo you cloned locally under DoubleKeyEncryptionService\src\customer-key-store\.</span></span>

2. <span data-ttu-id="6abaa-294">Individuare le righe seguenti:</span><span class="sxs-lookup"><span data-stu-id="6abaa-294">Locate the following lines:</span></span>

   ```c#
        #if USE_TEST_KEYS
        #error !!!!!!!!!!!!!!!!!!!!!! Use of test keys is only supported for testing,
        DO NOT USE  FOR PRODUCTION !!!!!!!!!!!!!!!!!!!!!!!!!!!!!
        services.AddSingleton<ippw.IKeyStore, ippw.TestKeyStore>();
        #endif
   ```

3. <span data-ttu-id="6abaa-295">Sostituire queste righe con il testo seguente:</span><span class="sxs-lookup"><span data-stu-id="6abaa-295">Replace these lines with the following text:</span></span>

   ```csharp
   services.AddSingleton<ippw.IKeyStore, ippw.TestKeyStore>();
   ```

   <span data-ttu-id="6abaa-296">I risultati finali devono essere simili al seguente.</span><span class="sxs-lookup"><span data-stu-id="6abaa-296">The end results should look similar to the following.</span></span>

   ![file di startup.cs per l'anteprima pubblica](../media/dke-startupcs-usetestkeys.png)

<span data-ttu-id="6abaa-298">A questo punto si è pronti per [creare il progetto di DKE](#build-the-project).</span><span class="sxs-lookup"><span data-stu-id="6abaa-298">Now you're ready to [build your DKE project](#build-the-project).</span></span>

### <a name="build-the-project"></a><span data-ttu-id="6abaa-299">Generare il progetto</span><span class="sxs-lookup"><span data-stu-id="6abaa-299">Build the project</span></span>

<span data-ttu-id="6abaa-300">Utilizzare le istruzioni seguenti per creare localmente il progetto DKE:</span><span class="sxs-lookup"><span data-stu-id="6abaa-300">Use the following instructions to build the DKE project locally:</span></span>

1. <span data-ttu-id="6abaa-301">In Visual Studio Code, nell'archivio dei servizi di DKE, selezionare **Visualizza** \> **tavolozza dei comandi** e quindi digitare **Compila** al prompt.</span><span class="sxs-lookup"><span data-stu-id="6abaa-301">In Visual Studio Code, in the DKE service repository, select **View** \> **Command Palette** and then type **build** at the prompt.</span></span>

1. <span data-ttu-id="6abaa-302">Nell'elenco scegliere **attività: Esegui attività di compilazione**.</span><span class="sxs-lookup"><span data-stu-id="6abaa-302">From the list, choose **Tasks: Run build task**.</span></span>

   <span data-ttu-id="6abaa-303">Se non sono state trovate attività di compilazione, selezionare **Configura attività di compilazione** e crearne una per .NET Core come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="6abaa-303">If there are no build tasks found, select **Configure Build Task** and create one for .NET core as follows.</span></span>

   ![Configurare l'attività di compilazione mancante per .NET](../media/dke-configurebuildtask.png)

   1. <span data-ttu-id="6abaa-305">Scegliere **crea tasks.jssu da modello**.</span><span class="sxs-lookup"><span data-stu-id="6abaa-305">Choose **Create tasks.json from template**.</span></span>

   ![Creare tasks.jssu file da modello per DKE](../media/dke-createtasksjsonfromtemplate.png)

   2. <span data-ttu-id="6abaa-307">Nell'elenco dei tipi di modello selezionare **.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="6abaa-307">From the list of template types, select **.NET Core**.</span></span>

   ![Creare tasks.jssu file da modello per DKE](../media/dke-tasksjsontemplate.png)

   3. <span data-ttu-id="6abaa-309">Nella sezione generazione individuare il percorso del file **customerkeystore. csproj** .</span><span class="sxs-lookup"><span data-stu-id="6abaa-309">In the build section, locate the path to the **customerkeystore.csproj** file.</span></span> <span data-ttu-id="6abaa-310">Se non è presente, aggiungere la riga seguente:</span><span class="sxs-lookup"><span data-stu-id="6abaa-310">If it's not there, add the following line:</span></span>

      ```json
      "${workspaceFolder}/src/customer-key-store/customerkeystore.csproj",
      ```

  4. <span data-ttu-id="6abaa-311">Eseguire di nuovo la Build.</span><span class="sxs-lookup"><span data-stu-id="6abaa-311">Run the build again.</span></span>

1. <span data-ttu-id="6abaa-312">Verificare che non vi siano errori rossi nella finestra di output.</span><span class="sxs-lookup"><span data-stu-id="6abaa-312">Verify that there are no red errors in the output window.</span></span>

   <span data-ttu-id="6abaa-313">Se sono presenti errori rossi, controllare l'output della console.</span><span class="sxs-lookup"><span data-stu-id="6abaa-313">If there are red errors, check the console output.</span></span> <span data-ttu-id="6abaa-314">Verificare che siano stati completati correttamente tutti i passaggi precedenti e che siano presenti le versioni di compilazione corrette.</span><span class="sxs-lookup"><span data-stu-id="6abaa-314">Ensure that you completed all the previous steps correctly and the correct build versions are present.</span></span>

2. <span data-ttu-id="6abaa-315">Selezionare **Esegui** \> **debug avvio** per eseguire il debug del processo.</span><span class="sxs-lookup"><span data-stu-id="6abaa-315">Select **Run** \> **Start Debugging** to debug the process.</span></span> <span data-ttu-id="6abaa-316">Se viene richiesto di selezionare un ambiente, selezionare **.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="6abaa-316">If you're prompted to select an environment, select **.NET core**.</span></span>

<span data-ttu-id="6abaa-317">Il debugger di base di .NET in genere viene avviato in '' https://localhost:5001 `. To view your test key, go to ` https://localhost:5001 ' e aggiunge una barra (/) e il nome della chiave.</span><span class="sxs-lookup"><span data-stu-id="6abaa-317">The .NET core debugger typically launches to \`\`https://localhost:5001`. To view your test key, go to `https://localhost:5001\` and append a forward slash (/) and the name of your key.</span></span> <span data-ttu-id="6abaa-318">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="6abaa-318">For example:</span></span>

```https
https://localhost:5001/TestKey1
```

<span data-ttu-id="6abaa-319">Il tasto dovrebbe essere visualizzato in formato JSON.</span><span class="sxs-lookup"><span data-stu-id="6abaa-319">The key should display in JSON format.</span></span>

<span data-ttu-id="6abaa-320">La configurazione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="6abaa-320">Your setup is now complete.</span></span> <span data-ttu-id="6abaa-321">Prima di pubblicare il keystore, in appsettings.jssu, per l'impostazione JwtAudience, assicurarsi che il valore di hostname corrisponda esattamente al nome host del servizio app.</span><span class="sxs-lookup"><span data-stu-id="6abaa-321">Before you publish the keystore, in appsettings.json, for the JwtAudience setting, ensure the value for hostname exactly matches your App Service host name.</span></span> <span data-ttu-id="6abaa-322">Potrebbe essere stata modificata in localhost per risolvere i problemi relativi alla generazione.</span><span class="sxs-lookup"><span data-stu-id="6abaa-322">You may have changed it to localhost to troubleshoot the build.</span></span>

### <a name="publish-the-key-store"></a><span data-ttu-id="6abaa-323">Pubblicare l'archivio delle chiavi</span><span class="sxs-lookup"><span data-stu-id="6abaa-323">Publish the key store</span></span>

<span data-ttu-id="6abaa-324">Per pubblicare l'archivio delle chiavi, è possibile creare un'istanza del servizio app di Azure per ospitare la distribuzione di DKE.</span><span class="sxs-lookup"><span data-stu-id="6abaa-324">To publish the key store, you'll create an Azure App Service instance to host your DKE deployment.</span></span> <span data-ttu-id="6abaa-325">Successivamente, verranno pubblicate le chiavi generate in Azure.</span><span class="sxs-lookup"><span data-stu-id="6abaa-325">Next, you'll publish your generated keys to Azure.</span></span>

<span data-ttu-id="6abaa-326">**Per creare un'istanza di Azure Web App per ospitare la distribuzione di DKE**</span><span class="sxs-lookup"><span data-stu-id="6abaa-326">**To create an Azure Web App instance to host your DKE deployment**</span></span>

1. <span data-ttu-id="6abaa-327">Nel browser, accedere al [portale di Microsoft Azure](https://ms.portal.azure.com)e passare a **app Services**  >  **Add**.</span><span class="sxs-lookup"><span data-stu-id="6abaa-327">In your browser, sign in to the [Microsoft Azure portal](https://ms.portal.azure.com), and go to **App Services** > **Add**.</span></span>

1. <span data-ttu-id="6abaa-328">Selezionare l'abbonamento e il gruppo di risorse e definire i dettagli dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="6abaa-328">Select your subscription and resource group and define your instance details.</span></span>

    - <span data-ttu-id="6abaa-329">Immettere il nome host del computer in cui si desidera installare il servizio DKE.</span><span class="sxs-lookup"><span data-stu-id="6abaa-329">Enter the hostname of the computer where you want to install the DKE service.</span></span> <span data-ttu-id="6abaa-330">Verificare che sia lo stesso nome di quello definito per l'impostazione JwtAudience nel [**appsettings.jssu**](#tenant-and-key-settings) file.</span><span class="sxs-lookup"><span data-stu-id="6abaa-330">Make sure it's the same name as the one defined for the JwtAudience setting in the [**appsettings.json**](#tenant-and-key-settings) file.</span></span> <span data-ttu-id="6abaa-331">Il valore specificato per il nome è anche WebAppInstanceName.</span><span class="sxs-lookup"><span data-stu-id="6abaa-331">The value you provide for the name is also the WebAppInstanceName.</span></span>

    - <span data-ttu-id="6abaa-332">Per la **pubblicazione**, selezionare **codice**e per **stack di Runtime**, selezionare **.NET Core 3,1**.</span><span class="sxs-lookup"><span data-stu-id="6abaa-332">For **Publish**, select **code**, and for **Runtime stack**, select **.NET Core 3.1**.</span></span>

    <span data-ttu-id="6abaa-333">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="6abaa-333">For example:</span></span>

   ![Aggiungere il servizio app](../media/dke-azure-add-app-service.png)

1. <span data-ttu-id="6abaa-335">Nella parte inferiore della pagina, selezionare **revisione + crea**e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="6abaa-335">At the bottom of the page, select **Review + create**, and then select **Add**.</span></span>

1. <span data-ttu-id="6abaa-336">Per pubblicare le chiavi generate in Azure, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="6abaa-336">Do one of the following to publish your generated keys to Azure:</span></span>

    - [<span data-ttu-id="6abaa-337">Pubblicare tramite ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="6abaa-337">Publish via ZipDeployUI</span></span>](#publish-via-zipdeployui)
    - [<span data-ttu-id="6abaa-338">Pubblicare tramite FTP</span><span class="sxs-lookup"><span data-stu-id="6abaa-338">Publish via FTP</span></span>](#publish-via-ftp)
    - [<span data-ttu-id="6abaa-339">Pubblicare tramite Visual Studio 2019 o versione successiva</span><span class="sxs-lookup"><span data-stu-id="6abaa-339">Publish via Visual Studio 2019 or later</span></span>](https://docs.microsoft.com/aspnet/core/tutorials/)
    - [<span data-ttu-id="6abaa-340">Pubblicare in un sistema locale</span><span class="sxs-lookup"><span data-stu-id="6abaa-340">Publish to an on-premises system</span></span>](https://docs.microsoft.com/aspnet/core/tutorials/publish-to-iis?view=aspnetcore-3.1&tabs=netcore-cli)

    > [!NOTE]
    > <span data-ttu-id="6abaa-341">È possibile preferire altri metodi per distribuire le chiavi.</span><span class="sxs-lookup"><span data-stu-id="6abaa-341">You may prefer other methods to deploy your keys.</span></span> <span data-ttu-id="6abaa-342">Selezionare il metodo più adatto per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="6abaa-342">Select the method that works best for your organization.</span></span>

    > [!TIP]
    > <span data-ttu-id="6abaa-343">La [pubblicazione tramite Visual Studio](https://docs.microsoft.com/aspnet/core/tutorials/) e un [sistema locale](https://docs.microsoft.com/aspnet/core/tutorials/publish-to-iis?view=aspnetcore-3.1&tabs=netcore-cli) è descritta nella [documentazione ASP .NET](https://docs.microsoft.com/aspnet/core/).</span><span class="sxs-lookup"><span data-stu-id="6abaa-343">[Publishing via Visual Studio](https://docs.microsoft.com/aspnet/core/tutorials/) and to an [on-premises system](https://docs.microsoft.com/aspnet/core/tutorials/publish-to-iis?view=aspnetcore-3.1&tabs=netcore-cli) is described in the [ASP .NET documentation](https://docs.microsoft.com/aspnet/core/).</span></span> <span data-ttu-id="6abaa-344">Se si utilizza uno di questi metodi, aprire le istruzioni in una scheda separata in modo che sia possibile tornare facilmente al termine.</span><span class="sxs-lookup"><span data-stu-id="6abaa-344">If you use one of these methods, open the instructions in a separate tab so that you can return here easily when you're done.</span></span>

#### <a name="publish-via-zipdeployui"></a><span data-ttu-id="6abaa-345">Pubblicare tramite ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="6abaa-345">Publish via ZipDeployUI</span></span>

1. <span data-ttu-id="6abaa-346">Passare a `https://<WebAppInstanceName>.scm.azurewebsites.net/ZipDeployUI`.</span><span class="sxs-lookup"><span data-stu-id="6abaa-346">Go to `https://<WebAppInstanceName>.scm.azurewebsites.net/ZipDeployUI`.</span></span>

    <span data-ttu-id="6abaa-347">Ad esempio: https://customerkeystoreforpublicpreview.scm.azurewebsites.net/ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="6abaa-347">For example: https://customerkeystoreforpublicpreview.scm.azurewebsites.net/ZipDeployUI</span></span>

1. <span data-ttu-id="6abaa-348">Nella codebase per l'archivio delle chiavi passare alla cartella **Customer-Key-store\src\customer-Key-Store** e verificare che la cartella contenga il file **customerkeystore. csproj** .</span><span class="sxs-lookup"><span data-stu-id="6abaa-348">In the codebase for the key store, go to the **customer-key-store\src\customer-key-store** folder, and verify that this folder contains the **customerkeystore.csproj** file.</span></span>

1. <span data-ttu-id="6abaa-349">Esegui: **pubblicazione di DotNet**</span><span class="sxs-lookup"><span data-stu-id="6abaa-349">Run: **dotnet publish**</span></span>

     <span data-ttu-id="6abaa-350">La finestra di output Visualizza la directory in cui è stata distribuita la pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="6abaa-350">The output window displays the directory where the publish was deployed.</span></span>

    <span data-ttu-id="6abaa-351">Ad esempio: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span><span class="sxs-lookup"><span data-stu-id="6abaa-351">For example: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span></span>

1. <span data-ttu-id="6abaa-352">Inviare tutti i file nella directory di pubblicazione a un file con estensione zip.</span><span class="sxs-lookup"><span data-stu-id="6abaa-352">Send all files in the publish directory to a .zip file.</span></span> <span data-ttu-id="6abaa-353">Quando si crea il file con estensione zip, verificare che tutti i file presenti nella directory si trovino nel livello radice del file. zip.</span><span class="sxs-lookup"><span data-stu-id="6abaa-353">When creating the .zip file, make sure that all files in the directory are at the root level of the .zip file.</span></span>

1. <span data-ttu-id="6abaa-354">Trascinare e rilasciare il file con estensione zip creato nel sito di ZipDeployUI che è stato aperto.</span><span class="sxs-lookup"><span data-stu-id="6abaa-354">Drag and drop the .zip file you create to the ZipDeployUI site you opened above.</span></span> <span data-ttu-id="6abaa-355">Ad esempio: https://customerkeystoreforpublicpreview.scm.azurewebsites.net/ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="6abaa-355">For example: https://customerkeystoreforpublicpreview.scm.azurewebsites.net/ZipDeployUI</span></span>

<span data-ttu-id="6abaa-356">DKE è distribuito ed è possibile passare alle chiavi di test create.</span><span class="sxs-lookup"><span data-stu-id="6abaa-356">DKE is deployed and you can browse to the test keys you've created.</span></span> <span data-ttu-id="6abaa-357">Continuare a [convalidare la distribuzione](#validate-your-deployment) seguente.</span><span class="sxs-lookup"><span data-stu-id="6abaa-357">Continue to [Validate your deployment](#validate-your-deployment) below.</span></span>

#### <a name="publish-via-ftp"></a><span data-ttu-id="6abaa-358">Pubblicare tramite FTP</span><span class="sxs-lookup"><span data-stu-id="6abaa-358">Publish via FTP</span></span>

1. <span data-ttu-id="6abaa-359">Connettersi al servizio app creato [precedentemente](#publish-the-key-store).</span><span class="sxs-lookup"><span data-stu-id="6abaa-359">Connect to the App Service you created [above](#publish-the-key-store).</span></span>

    <span data-ttu-id="6abaa-360">Nel browser passare a: **Azure portal**  >  **App Service**  >  **Deployment Center**  >  **Manual Deployment**  >  **FTP**  >  **Dashboard**FTP Deployment Center di distribuzione manuale di Azure Portal app.</span><span class="sxs-lookup"><span data-stu-id="6abaa-360">In your browser, go to: **Azure portal** > **App Service** > **Deployment Center** > **Manual Deployment** > **FTP** > **Dashboard**.</span></span>

1. <span data-ttu-id="6abaa-361">Copiare le stringhe di connessione visualizzate in un file locale.</span><span class="sxs-lookup"><span data-stu-id="6abaa-361">Copy the connection strings displayed to a local file.</span></span> <span data-ttu-id="6abaa-362">Queste stringhe verranno utilizzate per la connessione al servizio Web App e per il caricamento dei file tramite FTP.</span><span class="sxs-lookup"><span data-stu-id="6abaa-362">You'll use these strings to connect to the Web App Service and upload files via FTP.</span></span>

    <span data-ttu-id="6abaa-363">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="6abaa-363">For example:</span></span>

   ![Copiare le stringhe di connessione dal dashboard FTP](../media/dke-ftp-dashboard.png)

1. <span data-ttu-id="6abaa-365">Nella codebase per l'archiviazione delle chiavi passare alla **directory Customer-Key-store\src\customer-Key-Store**</span><span class="sxs-lookup"><span data-stu-id="6abaa-365">In the codebase for the key storage, go to the **customer-key-store\src\customer-key-store directory**.</span></span>

1. <span data-ttu-id="6abaa-366">Verificare che la directory contenga il file **customerkeystore. csproj** .</span><span class="sxs-lookup"><span data-stu-id="6abaa-366">Verify that this directory contains the **customerkeystore.csproj** file.</span></span>

1. <span data-ttu-id="6abaa-367">Esegui: **pubblicazione di DotNet**</span><span class="sxs-lookup"><span data-stu-id="6abaa-367">Run: **dotnet publish**</span></span>

    <span data-ttu-id="6abaa-368">L'output contiene la directory in cui è stata distribuita la pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="6abaa-368">The output contains the directory where the publish was deployed.</span></span>

    <span data-ttu-id="6abaa-369">Ad esempio: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span><span class="sxs-lookup"><span data-stu-id="6abaa-369">For example: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span></span>

1. <span data-ttu-id="6abaa-370">Inviare tutti i file nella directory di pubblicazione in un file zip.</span><span class="sxs-lookup"><span data-stu-id="6abaa-370">Send all files in the publish directory to a zip file.</span></span> <span data-ttu-id="6abaa-371">Quando si crea il file con estensione zip, verificare che tutti i file presenti nella directory si trovino nel livello radice del file. zip.</span><span class="sxs-lookup"><span data-stu-id="6abaa-371">When creating the .zip file, make sure that all files in the directory are at the root level of the .zip file.</span></span>

1. <span data-ttu-id="6abaa-372">Dal client FTP, utilizzare le informazioni di connessione copiate per la connessione al servizio app.</span><span class="sxs-lookup"><span data-stu-id="6abaa-372">From your FTP client, use the connection information you copied to connect to your App Service.</span></span> <span data-ttu-id="6abaa-373">Caricare il file con estensione zip creato nel passaggio precedente alla directory radice dell'app Web.</span><span class="sxs-lookup"><span data-stu-id="6abaa-373">Upload the .zip file you created in the previous step to the root directory of your Web App.</span></span>

<span data-ttu-id="6abaa-374">DKE è distribuito ed è possibile passare alle chiavi di test create.</span><span class="sxs-lookup"><span data-stu-id="6abaa-374">DKE is deployed and you can browse to the test keys you'd created.</span></span> <span data-ttu-id="6abaa-375">Successivamente, [convalidare la distribuzione](#validate-your-deployment).</span><span class="sxs-lookup"><span data-stu-id="6abaa-375">Next, [Validate your deployment](#validate-your-deployment).</span></span>

### <a name="validate-your-deployment"></a><span data-ttu-id="6abaa-376">Convalidare la distribuzione</span><span class="sxs-lookup"><span data-stu-id="6abaa-376">Validate your deployment</span></span>

<span data-ttu-id="6abaa-377">Dopo aver distribuito DKE utilizzando uno dei metodi descritti in alto, convalidare la distribuzione e le impostazioni dell'archivio chiavi.</span><span class="sxs-lookup"><span data-stu-id="6abaa-377">After deploying DKE using one of the methods described above, validate the deployment and the key store settings.</span></span>

<span data-ttu-id="6abaa-378">Eseguire: </span><span class="sxs-lookup"><span data-stu-id="6abaa-378">Run:</span></span>

<span data-ttu-id="6abaa-379">src\customer-key-store\scripts\key_store_tester.ps1 mykeystoreurl/MyKey</span><span class="sxs-lookup"><span data-stu-id="6abaa-379">src\customer-key-store\scripts\key_store_tester.ps1 mykeystoreurl/mykey</span></span>

<span data-ttu-id="6abaa-380">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="6abaa-380">For example:</span></span>

<span data-ttu-id="6abaa-381">key_store_tester.ps1 https://mycustomerkeystore.com/mykey</span><span class="sxs-lookup"><span data-stu-id="6abaa-381">key_store_tester.ps1 https://mycustomerkeystore.com/mykey</span></span>

<span data-ttu-id="6abaa-382">Assicurarsi che non vengano visualizzati errori nell'output.</span><span class="sxs-lookup"><span data-stu-id="6abaa-382">Ensure that no errors appear in the output.</span></span> <span data-ttu-id="6abaa-383">Quando si è pronti, [registrare il proprio archivio delle chiavi](#register-your-key-store).</span><span class="sxs-lookup"><span data-stu-id="6abaa-383">When you're ready, [register your key store](#register-your-key-store).</span></span>

## <a name="register-your-key-store"></a><span data-ttu-id="6abaa-384">Registrare il proprio archivio delle chiavi</span><span class="sxs-lookup"><span data-stu-id="6abaa-384">Register your key store</span></span>

<span data-ttu-id="6abaa-385">La procedura seguente consente di registrare il proprio archivio chiavi.</span><span class="sxs-lookup"><span data-stu-id="6abaa-385">The following steps enable you to register your key store.</span></span> <span data-ttu-id="6abaa-386">La registrazione dell'archivio delle chiavi è l'ultimo passaggio della distribuzione di DKE prima di iniziare a creare etichette.</span><span class="sxs-lookup"><span data-stu-id="6abaa-386">Registering your key store is the last step in deploying DKE before you can start creating labels.</span></span>

<span data-ttu-id="6abaa-387">Per registrare l'archivio delle chiavi:</span><span class="sxs-lookup"><span data-stu-id="6abaa-387">To register your key store:</span></span>

1. <span data-ttu-id="6abaa-388">Nel browser aprire il portale di [Microsoft Azure](https://ms.portal.azure.com/)e passare a **tutte le** \> **Identity** \> **registrazioni delle app**di identità dei servizi.</span><span class="sxs-lookup"><span data-stu-id="6abaa-388">In your browser, open the [Microsoft Azure portal](https://ms.portal.azure.com/), and go to **All Services** \> **Identity** \> **App Registrations**.</span></span>

2. <span data-ttu-id="6abaa-389">Selezionare **nuova registrazione**e immettere un nome significativo.</span><span class="sxs-lookup"><span data-stu-id="6abaa-389">Select **New registration**, and enter a meaningful name.</span></span>

3. <span data-ttu-id="6abaa-390">Selezionare un tipo di account dalle opzioni visualizzate.</span><span class="sxs-lookup"><span data-stu-id="6abaa-390">Select an account type from the options displayed.</span></span>

    <span data-ttu-id="6abaa-391">Se si utilizza Microsoft Azure con un dominio non personalizzato, ad esempio **onmicrosoft.com**, selezionare solo gli **account nella directory dell'organizzazione (solo tenant di Microsoft).**</span><span class="sxs-lookup"><span data-stu-id="6abaa-391">If you're using Microsoft Azure with a non-custom domain, such as **onmicrosoft.com**, select **Accounts in this organizational directory only (Microsoft only - Single tenant).**</span></span>

    <span data-ttu-id="6abaa-392">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="6abaa-392">For example:</span></span>

   ![Nuova registrazione delle app](../media/dke-app-registration.png)

4. <span data-ttu-id="6abaa-394">Nella parte inferiore della pagina, selezionare **registra** per creare la nuova registrazione app.</span><span class="sxs-lookup"><span data-stu-id="6abaa-394">At the bottom of the page, select **Register** to create the new App Registration.</span></span>

5. <span data-ttu-id="6abaa-395">Nella nuova registrazione dell'app, nel riquadro sinistro, in **Gestisci**selezionare **autenticazione**.</span><span class="sxs-lookup"><span data-stu-id="6abaa-395">In your new App Registration, in the left pane, under **Manage**, select **Authentication**.</span></span>

6. <span data-ttu-id="6abaa-396">Selezionare **Aggiungi una piattaforma**.</span><span class="sxs-lookup"><span data-stu-id="6abaa-396">Select **Add a platform**.</span></span>
 
7. <span data-ttu-id="6abaa-397">Nel menu a comparsa **Configura piattaforme** selezionare **Web**.</span><span class="sxs-lookup"><span data-stu-id="6abaa-397">On the **Configure platforms** popup, select **Web**.</span></span>
 
8. <span data-ttu-id="6abaa-398">In **URI di reindirizzamento**, immettere l'URI del servizio di crittografia a chiave doppia.</span><span class="sxs-lookup"><span data-stu-id="6abaa-398">Under **Redirect URIs**, enter the URI of your double key encryption service.</span></span> <span data-ttu-id="6abaa-399">Immettere l'URL del servizio app, inclusi il nome host e il dominio.</span><span class="sxs-lookup"><span data-stu-id="6abaa-399">Enter the App Service URL, including both the hostname and domain.</span></span>

    <span data-ttu-id="6abaa-400">Ad esempio: https://mycustomerkeystoretest.com</span><span class="sxs-lookup"><span data-stu-id="6abaa-400">For example: https://mycustomerkeystoretest.com</span></span>

    - <span data-ttu-id="6abaa-401">L'URL immesso deve corrispondere al nome host in cui è distribuito l'archivio delle chiavi.</span><span class="sxs-lookup"><span data-stu-id="6abaa-401">The URL you enter must match the hostname where your key store is deployed.</span></span>
    - <span data-ttu-id="6abaa-402">Se si sta verificando localmente con Visual Studio, utilizzare **https://localhost:5001** .</span><span class="sxs-lookup"><span data-stu-id="6abaa-402">If you're testing locally with Visual Studio, use **https://localhost:5001**.</span></span>
    - <span data-ttu-id="6abaa-403">In tutti i casi, lo schema deve essere **https**.</span><span class="sxs-lookup"><span data-stu-id="6abaa-403">In all cases, the scheme must be **https**.</span></span>

    <span data-ttu-id="6abaa-404">Verificare che il nome dell'host corrisponda esattamente al cognome del servizio app.</span><span class="sxs-lookup"><span data-stu-id="6abaa-404">Ensure the hostname exactly matches your App Service host name.</span></span> <span data-ttu-id="6abaa-405">Potrebbe essere stato modificato per `localhost` risolvere i problemi relativi alla generazione.</span><span class="sxs-lookup"><span data-stu-id="6abaa-405">You may have changed it to `localhost` to troubleshoot the build.</span></span> <span data-ttu-id="6abaa-406">In **appsettings.js**, questo valore è il nome host impostato per `JwtAudience` .</span><span class="sxs-lookup"><span data-stu-id="6abaa-406">In **appsettings.json**, this value is the hostname you set for `JwtAudience`.</span></span>

6. <span data-ttu-id="6abaa-407">In **concessione implicita**selezionare la casella di controllo **token ID** .</span><span class="sxs-lookup"><span data-stu-id="6abaa-407">Under **Implicit grant**, select the **ID tokens** checkbox.</span></span>

1. <span data-ttu-id="6abaa-408">Selezionare **Salva** per salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="6abaa-408">Select **Save** to save your changes.</span></span>

7. <span data-ttu-id="6abaa-409">Nel riquadro sinistro, selezionare **esporre un'API**, quindi accanto a URI ID applicazione selezionare **imposta**.</span><span class="sxs-lookup"><span data-stu-id="6abaa-409">On the left pane, select **Expose an API**, then next to Application ID URI, select **Set**.</span></span>

9. <span data-ttu-id="6abaa-410">Sempre nella pagina **esporre un'API** , nell' **ambito definito dall'area API** Selezionare **Aggiungi un ambito**.</span><span class="sxs-lookup"><span data-stu-id="6abaa-410">Still on the **Expose an API** page, in the **Scopes defined by this API** area, select **Add a scope**.</span></span> <span data-ttu-id="6abaa-411">Nel nuovo ambito:</span><span class="sxs-lookup"><span data-stu-id="6abaa-411">In the new scope:</span></span>

    1. <span data-ttu-id="6abaa-412">Definire il nome dell'ambito come **user_impersonation**.</span><span class="sxs-lookup"><span data-stu-id="6abaa-412">Define the scope name as **user_impersonation**.</span></span>

    2. <span data-ttu-id="6abaa-413">Selezionare gli amministratori e gli utenti che possono acconsentire.</span><span class="sxs-lookup"><span data-stu-id="6abaa-413">Select the administrators and users who can consent.</span></span>

    3. <span data-ttu-id="6abaa-414">Definire i valori rimanenti richiesti.</span><span class="sxs-lookup"><span data-stu-id="6abaa-414">Define any remaining values required.</span></span>

    4. <span data-ttu-id="6abaa-415">Selezionare **Aggiungi ambito.**</span><span class="sxs-lookup"><span data-stu-id="6abaa-415">Select **Add scope.**</span></span>

    <span data-ttu-id="6abaa-416">Selezionare **Salva** nella parte superiore per salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="6abaa-416">Select **Save** at the top to save your changes.</span></span>

10. <span data-ttu-id="6abaa-417">Sempre nella pagina **esporre un'API** , nell'area **applicazioni client autorizzate** Selezionare **Aggiungi un'applicazione client**.</span><span class="sxs-lookup"><span data-stu-id="6abaa-417">Still on the **Expose an API** page, in the **Authorized client applications** area, select **Add a client application**.</span></span>

    <span data-ttu-id="6abaa-418">Nella nuova applicazione client:</span><span class="sxs-lookup"><span data-stu-id="6abaa-418">In the new client application:</span></span>

    1. <span data-ttu-id="6abaa-419">Definire l'ID client come **d3590ed6-52B3-4102-Aeff-aad2292ab01c**.</span><span class="sxs-lookup"><span data-stu-id="6abaa-419">Define the Client ID as **d3590ed6-52b3-4102-aeff-aad2292ab01c**.</span></span> <span data-ttu-id="6abaa-420">Questo valore è l'ID client di Microsoft Office e consente a Office di ottenere un token di accesso per l'archivio delle chiavi.</span><span class="sxs-lookup"><span data-stu-id="6abaa-420">This value is the Microsoft Office client ID, and enables Office to obtain an access token for your key store.</span></span>

    2. <span data-ttu-id="6abaa-421">In **ambiti autorizzati**selezionare l'ambito **user_impersonation** .</span><span class="sxs-lookup"><span data-stu-id="6abaa-421">Under **Authorized scopes**, select the **user_impersonation** scope.</span></span>

    3. <span data-ttu-id="6abaa-422">Selezionare **Aggiungi applicazione**.</span><span class="sxs-lookup"><span data-stu-id="6abaa-422">Select **Add application**.</span></span>

    4. <span data-ttu-id="6abaa-423">Selezionare **Salva** nella parte superiore per salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="6abaa-423">Select **Save** at the top to save your changes.</span></span>

<span data-ttu-id="6abaa-424">L'archivio delle chiavi di DKE è ora registrato.</span><span class="sxs-lookup"><span data-stu-id="6abaa-424">Your DKE key store is now registered.</span></span> <span data-ttu-id="6abaa-425">Continuare con la [creazione di etichette mediante DKE](#create-labels-using-dke).</span><span class="sxs-lookup"><span data-stu-id="6abaa-425">Continue by [creating labels using DKE](#create-labels-using-dke).</span></span>

## <a name="create-labels-using-dke"></a><span data-ttu-id="6abaa-426">Creare etichette utilizzando DKE</span><span class="sxs-lookup"><span data-stu-id="6abaa-426">Create labels using DKE</span></span>

<span data-ttu-id="6abaa-427">Nel centro conformità di Microsoft 365, creare una nuova etichetta di riservatezza e applicare la crittografia come si farebbe altrimenti.</span><span class="sxs-lookup"><span data-stu-id="6abaa-427">In the Microsoft 365 compliance center, create a new sensitivity label and apply encryption as you would otherwise.</span></span> <span data-ttu-id="6abaa-428">Selezionare **Use Double Key Encryption** e immettere l'URL dell'endpoint per la chiave.</span><span class="sxs-lookup"><span data-stu-id="6abaa-428">Select **Use Double Key Encryption** and enter the endpoint URL for your key.</span></span>

<span data-ttu-id="6abaa-429">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="6abaa-429">For example:</span></span>

![Selezionare Use Double Key Encryption in the Microsoft 365 Compliance Center](../media/dke-use-dke.png)

<span data-ttu-id="6abaa-431">Tutte le etichette di DKE aggiunte verranno visualizzate per gli utenti nelle versioni più recenti di Microsoft 365 Apps for Enterprise.</span><span class="sxs-lookup"><span data-stu-id="6abaa-431">Any DKE labels you add will start appearing for users in the latest versions of Microsoft 365 Apps for enterprise.</span></span>

> [!NOTE]
> <span data-ttu-id="6abaa-432">La possibilità di aggiornare i client con le nuove etichette potrebbe richiedere fino a 24 ore.</span><span class="sxs-lookup"><span data-stu-id="6abaa-432">It may take up to 24 hours for the clients to refresh with the new labels.</span></span>

### <a name="enable-dke-in-your-client"></a><span data-ttu-id="6abaa-433">Abilitare DKE nel client</span><span class="sxs-lookup"><span data-stu-id="6abaa-433">Enable DKE in your client</span></span>

<span data-ttu-id="6abaa-434">Abilitare DKE per il client aggiungendo le seguenti chiavi del registro di sistema:</span><span class="sxs-lookup"><span data-stu-id="6abaa-434">Enable DKE for your client by adding the following registry keys:</span></span>

```properties
    [HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIPC\flighting]
    "DoubleKeyProtection"=dword:00000001

    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\flighting]
    "DoubleKeyProtection"=dword:00000001
```
