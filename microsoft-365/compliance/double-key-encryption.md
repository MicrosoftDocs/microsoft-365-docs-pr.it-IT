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
ms.openlocfilehash: 47fc4bc47831970ef7a7f2087cf6c86b6fefb8c2
ms.sourcegitcommit: fe20f5ed07f38786c63df0f73659ca472e69e478
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/21/2020
ms.locfileid: "45201728"
---
# <a name="double-key-encryption-dke"></a><span data-ttu-id="cce32-103">Crittografia a chiave doppia (DKE)</span><span class="sxs-lookup"><span data-stu-id="cce32-103">Double Key Encryption (DKE)</span></span>

> <span data-ttu-id="cce32-104">*Si applica a: [conformità di Microsoft 365](https://www.microsoft.com/microsoft-365/business/compliance-management), [Azure Information Protection](https://azure.microsoft.com/pricing/details/information-protection)*</span><span class="sxs-lookup"><span data-stu-id="cce32-104">*Applies to: [Microsoft 365 Compliance](https://www.microsoft.com/microsoft-365/business/compliance-management), [Azure Information Protection](https://azure.microsoft.com/pricing/details/information-protection)*</span></span>
>
> <span data-ttu-id="cce32-105">*Istruzioni per: [client di etichettatura unificata di Azure Information Protection per Windows](https://docs.microsoft.com/azure/information-protection/faqs.md#whats-the-difference-between-the-azure-information-protection-classic-and-unified-labeling-clients)*</span><span class="sxs-lookup"><span data-stu-id="cce32-105">*Instructions for: [Azure Information Protection unified labeling client for Windows](https://docs.microsoft.com/azure/information-protection/faqs.md#whats-the-difference-between-the-azure-information-protection-classic-and-unified-labeling-clients)*</span></span>
>
> <span data-ttu-id="cce32-106">*Descrizione del servizio per: [conformità di Microsoft 365](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*</span><span class="sxs-lookup"><span data-stu-id="cce32-106">*Service description for: [Microsoft 365 Compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*</span></span>

<span data-ttu-id="cce32-107">Questa versione di anteprima pubblica di Double Key Encryption (DKE) consente di utilizzare il client di etichettatura unificata di Azure Information Protection per proteggere i contenuti estremamente riservati mantenendo il controllo completo della chiave.</span><span class="sxs-lookup"><span data-stu-id="cce32-107">This public preview version of Double Key Encryption (DKE) enables you to use the Azure Information Protection Unified Labeling Client to protect highly sensitive content while maintaining full control of your key.</span></span>

<span data-ttu-id="cce32-108">La crittografia a chiave doppia richiede due tasti, utilizzati insieme, per accedere al contenuto protetto.</span><span class="sxs-lookup"><span data-stu-id="cce32-108">Double Key Encryption requires two keys, used together, to access protected content.</span></span> <span data-ttu-id="cce32-109">Si archivia una chiave in Microsoft Azure e si tiene premuto l'altro tasto.</span><span class="sxs-lookup"><span data-stu-id="cce32-109">You store one key in Microsoft Azure, and you hold the other key.</span></span>

<span data-ttu-id="cce32-110">La crittografia a chiave doppia supporta sia le distribuzioni cloud che quelle locali.</span><span class="sxs-lookup"><span data-stu-id="cce32-110">Double Key Encryption supports both cloud and on-premises deployments.</span></span> <span data-ttu-id="cce32-111">Queste distribuzioni contribuiscono a garantire che i dati crittografati rimangano opachi ovunque vengano archiviati i dati protetti.</span><span class="sxs-lookup"><span data-stu-id="cce32-111">These deployments help to ensure that encrypted data remains opaque wherever you store the protected data.</span></span>

<span data-ttu-id="cce32-112">Per ulteriori informazioni sulle chiavi radice tenant basate su cloud predefinite, vedere [Planning and implementing your Azure Information Protection tenant Key](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key).</span><span class="sxs-lookup"><span data-stu-id="cce32-112">For more information about the default, cloud-based tenant root keys, see [Planning and implementing your Azure Information Protection tenant key](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key).</span></span>

<span data-ttu-id="cce32-113">La crittografia a doppio tasto è simile a quella di una cassetta di sicurezza che richiede l'accesso sia a un tasto Bank che a una chiave del cliente.</span><span class="sxs-lookup"><span data-stu-id="cce32-113">Double Key Encryption is similar to a safety deposit box that requires both a bank key and a customer key to gain access.</span></span> <span data-ttu-id="cce32-114">Per decrittografare il contenuto protetto, è necessario utilizzare sia la chiave gestita Microsoft sia la chiave relativa al cliente.</span><span class="sxs-lookup"><span data-stu-id="cce32-114">To decrypt protected content, you must use both the Microsoft managed key and the customer-held key.</span></span>

<span data-ttu-id="cce32-115">Nel video seguente viene illustrato il funzionamento della crittografia a chiave doppia per proteggere il contenuto.</span><span class="sxs-lookup"><span data-stu-id="cce32-115">The following video shows how Double Key Encryption works to secure your content.</span></span>

<span data-ttu-id="cce32-116">Se le organizzazioni hanno uno dei requisiti seguenti, è possibile utilizzare DKE per proteggere il contenuto:</span><span class="sxs-lookup"><span data-stu-id="cce32-116">If your organizations have any of the following requirements, you can use DKE to help secure your content:</span></span>

- <span data-ttu-id="cce32-117">Si desidera garantire che sia possibile decrittografare il contenuto protetto *solo* in tutte le circostanze.</span><span class="sxs-lookup"><span data-stu-id="cce32-117">You want to ensure that *only you* can ever decrypt protected content, under all circumstances.</span></span>
- <span data-ttu-id="cce32-118">Non si desidera che Microsoft abbia accesso ai dati protetti da solo.</span><span class="sxs-lookup"><span data-stu-id="cce32-118">You don't want Microsoft to have access to protected data on its own.</span></span>
- <span data-ttu-id="cce32-119">Sono necessari requisiti normativi per mantenere le chiavi all'interno di un limite geografico.</span><span class="sxs-lookup"><span data-stu-id="cce32-119">You have regulatory requirements to hold keys within a geographical boundary.</span></span> <span data-ttu-id="cce32-120">Tutti i tasti gestiti dal cliente per la crittografia e la decrittografia dei dati vengono mantenuti nel Data Center.</span><span class="sxs-lookup"><span data-stu-id="cce32-120">All customer-held keys for data encryption and decryption are maintained in your data center.</span></span>

> [!VIDEO https://msit.microsoftstream.com/embed/video/f466a1ff-0400-a936-221c-f1eab45dc756]

## <a name="system-and-licensing-requirements-for-dke"></a><span data-ttu-id="cce32-121">Requisiti di sistema e licenze per DKE</span><span class="sxs-lookup"><span data-stu-id="cce32-121">System and licensing requirements for DKE</span></span>

<span data-ttu-id="cce32-122">Questa versione di anteprima pubblica di crittografia a chiave doppia per Microsoft 365 è disponibile come parte di Microsoft 365 E5 e Office 365 E5.</span><span class="sxs-lookup"><span data-stu-id="cce32-122">This public preview release of Double Key Encryption for Microsoft 365 is available as part of Microsoft 365 E5 and Office 365 E5.</span></span> <span data-ttu-id="cce32-123">Se non si dispone di una licenza Microsoft 365 E5, è possibile iscriversi per una [versione di valutazione](https://aka.ms/M365E5ComplianceTrial).</span><span class="sxs-lookup"><span data-stu-id="cce32-123">If you don’t have a Microsoft 365 E5 license, you can sign up for a [trial](https://aka.ms/M365E5ComplianceTrial).</span></span> <span data-ttu-id="cce32-124">Per ulteriori informazioni su queste licenze, vedere [Microsoft 365 Licensing Guidance for security & Compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span><span class="sxs-lookup"><span data-stu-id="cce32-124">For more information about these licenses, see [Microsoft 365 licensing guidance for security & compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span></span>

<span data-ttu-id="cce32-125">**Office Insider** Per utilizzare l'anteprima pubblica, è necessario essere membri del programma Office Insider.</span><span class="sxs-lookup"><span data-stu-id="cce32-125">**Office Insider** To use the public preview, you must be a member of the Office Insider program.</span></span> <span data-ttu-id="cce32-126">Per partecipare a Office Insider, accedere a [https://insider.office.com](https://insider.office.com) .</span><span class="sxs-lookup"><span data-stu-id="cce32-126">To join Office Insider, go to [https://insider.office.com](https://insider.office.com).</span></span> <span data-ttu-id="cce32-127">Una volta che si è membri, preparare l'ambiente per la distribuzione di Office Insider Builds scegliendo il metodo di distribuzione appropriato per la propria organizzazione.</span><span class="sxs-lookup"><span data-stu-id="cce32-127">Once you're a member, prepare your environment to deploy Office Insider builds by choosing the right deployment method for your organization.</span></span> <span data-ttu-id="cce32-128">Per istruzioni, vedere [Guida introduttiva alla distribuzione di Office Insider Builds](https://insider.office.com/business/deploy).</span><span class="sxs-lookup"><span data-stu-id="cce32-128">For instructions, see [Getting started on deploying Office Insider builds](https://insider.office.com/business/deploy).</span></span>

<span data-ttu-id="cce32-129">**Azure Information Protection**.</span><span class="sxs-lookup"><span data-stu-id="cce32-129">**Azure Information Protection**.</span></span> <span data-ttu-id="cce32-130">DKE funziona con le etichette di riservatezza e richiede la protezione delle informazioni di Azure.</span><span class="sxs-lookup"><span data-stu-id="cce32-130">DKE works with sensitivity labels and requires Azure Information Protection.</span></span>

## <a name="supported-environments-for-storing-and-viewing-dke-protected-content"></a><span data-ttu-id="cce32-131">Ambienti supportati per l'archiviazione e la visualizzazione di contenuto protetto da DKE</span><span class="sxs-lookup"><span data-stu-id="cce32-131">Supported environments for storing and viewing DKE-protected content</span></span>

<span data-ttu-id="cce32-132">**Applicazioni supportate**.</span><span class="sxs-lookup"><span data-stu-id="cce32-132">**Supported applications**.</span></span> <span data-ttu-id="cce32-133">[Microsoft 365 Apps for Enterprise](https://www.microsoft.com/microsoft-365/business/microsoft-365-apps-for-enterprise-product) clients on Windows, tra cui Word, Excel e PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="cce32-133">[Microsoft 365 Apps for enterprise](https://www.microsoft.com/microsoft-365/business/microsoft-365-apps-for-enterprise-product) clients on Windows, including Word, Excel, and PowerPoint.</span></span>

<span data-ttu-id="cce32-134">**Supporto per i contenuti online**.</span><span class="sxs-lookup"><span data-stu-id="cce32-134">**Online content support**.</span></span> <span data-ttu-id="cce32-135">Sono supportati i documenti e i file archiviati online in Microsoft SharePoint e OneDrive for business.</span><span class="sxs-lookup"><span data-stu-id="cce32-135">Documents and files stored online in both Microsoft SharePoint and OneDrive for Business are supported.</span></span> <span data-ttu-id="cce32-136">È possibile condividere il contenuto crittografato tramite posta elettronica, ma non è possibile visualizzare i documenti e i file crittografati online.</span><span class="sxs-lookup"><span data-stu-id="cce32-136">You can share encrypted content by email, but you can't view encrypted documents and files online.</span></span> <span data-ttu-id="cce32-137">Al contrario, è necessario visualizzare il contenuto protetto utilizzando le app desktop del computer locale.</span><span class="sxs-lookup"><span data-stu-id="cce32-137">Instead, you must view protected content using the desktop apps on your local computer.</span></span>

## <a name="about-this-public-preview-article"></a><span data-ttu-id="cce32-138">Informazioni sull'articolo relativo all'anteprima pubblica</span><span class="sxs-lookup"><span data-stu-id="cce32-138">About this public preview article</span></span>

<span data-ttu-id="cce32-139">Sono disponibili diversi modi per completare alcuni passaggi per la distribuzione della crittografia a chiave doppia.</span><span class="sxs-lookup"><span data-stu-id="cce32-139">There are several ways you can complete some of the steps to deploy Double Key Encryption.</span></span> <span data-ttu-id="cce32-140">In questo articolo vengono fornite istruzioni dettagliate per consentire agli amministratori meno esperti di distribuire correttamente il servizio.</span><span class="sxs-lookup"><span data-stu-id="cce32-140">This article provides detailed instructions so that less experienced admins successfully deploy the service.</span></span> <span data-ttu-id="cce32-141">Se si ha esperienza con le tecnologie comuni, ad esempio git, condivise con i metodi di distribuzione descritti in questo articolo, è possibile scegliere di utilizzare i propri metodi.</span><span class="sxs-lookup"><span data-stu-id="cce32-141">If you're experienced with the common technologies, such as git, shared by the deployment methods described in this article, you can choose to use your own methods.</span></span>

<span data-ttu-id="cce32-142">Per l'anteprima pubblica, sono state incluse istruzioni dettagliate su come distribuire il servizio di crittografia a chiave doppia in Azure.</span><span class="sxs-lookup"><span data-stu-id="cce32-142">For public preview, we've included step-by-step instructions on how to deploy the Double Key Encryption service to Azure.</span></span> <span data-ttu-id="cce32-143">Questo scenario non è qualcosa che si potrebbe fare in produzione.</span><span class="sxs-lookup"><span data-stu-id="cce32-143">This scenario isn't something you'd likely do in production.</span></span> <span data-ttu-id="cce32-144">Per l'anteprima pubblica utilizzando Azure è un modo rapido per la distribuzione che consente di iniziare a usare la crittografia a chiave doppia subito.</span><span class="sxs-lookup"><span data-stu-id="cce32-144">For public preview using Azure is a quick way to deploy that lets you get started using Double Key Encryption right away.</span></span>

<span data-ttu-id="cce32-145">È possibile scegliere di distribuire il servizio dovunque si desideri, che si tratti di una rete locale o di un altro provider.</span><span class="sxs-lookup"><span data-stu-id="cce32-145">You can choose to deploy the service wherever you want, whether it's locally on your network or with another provider.</span></span> <span data-ttu-id="cce32-146">Sarà necessario pubblicare l'archivio chiavi utilizzando metodi adatti per tale percorso.</span><span class="sxs-lookup"><span data-stu-id="cce32-146">You'll need to publish the key store using methods appropriate for that location.</span></span>

## <a name="deploy-double-key-encryption"></a><span data-ttu-id="cce32-147">Distribuire la crittografia a chiave doppia</span><span class="sxs-lookup"><span data-stu-id="cce32-147">Deploy Double Key Encryption</span></span>

<span data-ttu-id="cce32-148">Seguire questi passaggi generali per configurare la crittografia a chiave doppia per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="cce32-148">You'll follow these general steps to set up Double Key Encryption for your organization.</span></span> <span data-ttu-id="cce32-149">Nell'esempio riportato in questo articolo viene utilizzato Azure come destinazione di distribuzione per il servizio DKE.</span><span class="sxs-lookup"><span data-stu-id="cce32-149">The example in this article uses Azure as the deployment destination for the DKE service.</span></span> <span data-ttu-id="cce32-150">Se si esegue la distribuzione in un'altra posizione, è necessario fornire i propri valori.</span><span class="sxs-lookup"><span data-stu-id="cce32-150">If you're deploying to another location, you'll need to provide your own values.</span></span>

1. [<span data-ttu-id="cce32-151">Installare i prerequisiti software</span><span class="sxs-lookup"><span data-stu-id="cce32-151">Install software prerequisites</span></span>](#install-software-prerequisites)
1. [<span data-ttu-id="cce32-152">Clonare il repository di crittografia GitHub a doppio tasto</span><span class="sxs-lookup"><span data-stu-id="cce32-152">Clone the Double Key Encryption GitHub repository</span></span>](#clone-the-dke-github-repository)
1. [<span data-ttu-id="cce32-153">Modificare le impostazioni dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="cce32-153">Modify application settings</span></span>](#modify-application-settings)
1. [<span data-ttu-id="cce32-154">Generare i tasti di testing</span><span class="sxs-lookup"><span data-stu-id="cce32-154">Generate test keys</span></span>](#generate-test-keys)
1. [<span data-ttu-id="cce32-155">Generare il progetto</span><span class="sxs-lookup"><span data-stu-id="cce32-155">Build the project</span></span>](#build-the-project)
1. [<span data-ttu-id="cce32-156">Pubblicare l'archivio delle chiavi</span><span class="sxs-lookup"><span data-stu-id="cce32-156">Publish the key store</span></span>](#publish-the-key-store)
1. [<span data-ttu-id="cce32-157">Convalidare la distribuzione</span><span class="sxs-lookup"><span data-stu-id="cce32-157">Validate your deployment</span></span>](#validate-your-deployment)
1. [<span data-ttu-id="cce32-158">Registrare il proprio archivio delle chiavi</span><span class="sxs-lookup"><span data-stu-id="cce32-158">Register your key store</span></span>](#register-your-key-store)
1. [<span data-ttu-id="cce32-159">Creare etichette di riservatezza</span><span class="sxs-lookup"><span data-stu-id="cce32-159">Create sensitivity labels</span></span>](#create-labels-using-dke)

<span data-ttu-id="cce32-160">Al termine, è possibile crittografare documenti e file utilizzando DKE.</span><span class="sxs-lookup"><span data-stu-id="cce32-160">When you're done, you can encrypt documents and files using DKE.</span></span> <span data-ttu-id="cce32-161">Per informazioni, vedere [applicare etichette di riservatezza ai propri file e messaggi di posta elettronica in Office](https://support.microsoft.com/office/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9).</span><span class="sxs-lookup"><span data-stu-id="cce32-161">For information, see [Apply sensitivity labels to your files and email in Office](https://support.microsoft.com/office/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9).</span></span>

### <a name="install-software-prerequisites"></a><span data-ttu-id="cce32-162">Installare i prerequisiti software</span><span class="sxs-lookup"><span data-stu-id="cce32-162">Install software prerequisites</span></span>

<span data-ttu-id="cce32-163">Esistono due tipi di prerequisiti software per la crittografia a chiave doppia</span><span class="sxs-lookup"><span data-stu-id="cce32-163">There are two types of software prerequisites for Double Key Encryption</span></span>

- [<span data-ttu-id="cce32-164">Prerequisiti del servizio di crittografia a doppia chiave</span><span class="sxs-lookup"><span data-stu-id="cce32-164">Double Key Encryption service prerequisites</span></span>](#double-key-encryption-service-prerequisites)
- [<span data-ttu-id="cce32-165">Prerequisiti per la crittografia a chiave doppia per i computer client</span><span class="sxs-lookup"><span data-stu-id="cce32-165">Double Key Encryption prerequisites for client computers</span></span>](#double-key-encryption-prerequisites-for-client-computers)

#### <a name="double-key-encryption-service-prerequisites"></a><span data-ttu-id="cce32-166">Prerequisiti del servizio di crittografia a doppia chiave</span><span class="sxs-lookup"><span data-stu-id="cce32-166">Double Key Encryption service prerequisites</span></span>

<span data-ttu-id="cce32-167">Installare questi prerequisiti nel computer in cui si desidera installare il servizio DKE.</span><span class="sxs-lookup"><span data-stu-id="cce32-167">Install these prerequisites on the computer where you want to install the DKE service.</span></span>

<span data-ttu-id="cce32-168">**.NET Core 3,1 SDK**.</span><span class="sxs-lookup"><span data-stu-id="cce32-168">**.NET Core 3.1 SDK**.</span></span> <span data-ttu-id="cce32-169">Scaricare e installare l'SDK da [download .NET Core 3,1](https://dotnet.microsoft.com/download/dotnet-core/3.1).</span><span class="sxs-lookup"><span data-stu-id="cce32-169">Download and install the SDK from [Download .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1).</span></span>

<span data-ttu-id="cce32-170">**Codice Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="cce32-170">**Visual Studio Code**.</span></span> <span data-ttu-id="cce32-171">Scaricare il codice di Visual Studio da [https://code.visualstudio.com/](https://code.visualstudio.com) .</span><span class="sxs-lookup"><span data-stu-id="cce32-171">Download Visual Studio Code from [https://code.visualstudio.com/](https://code.visualstudio.com).</span></span> <span data-ttu-id="cce32-172">Una volta installato, eseguire codice Visual Studio e selezionare **Visualizza** \> **estensioni**.</span><span class="sxs-lookup"><span data-stu-id="cce32-172">Once installed, run Visual Studio Code and select **View** \> **Extensions**.</span></span> <span data-ttu-id="cce32-173">Installare queste estensioni.</span><span class="sxs-lookup"><span data-stu-id="cce32-173">Install these extensions.</span></span>

- <span data-ttu-id="cce32-174">C# per Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="cce32-174">C# for Visual Studio Code</span></span>

- <span data-ttu-id="cce32-175">Gestione pacchetti NuGet</span><span class="sxs-lookup"><span data-stu-id="cce32-175">NuGet Package Manager</span></span>

<span data-ttu-id="cce32-176">**Microsoft Office Insider**.</span><span class="sxs-lookup"><span data-stu-id="cce32-176">**Microsoft Office Insider**.</span></span> <span data-ttu-id="cce32-177">Configurare almeno un metodo di [distribuzione](https://insider.office.com/business/deploy).</span><span class="sxs-lookup"><span data-stu-id="cce32-177">Set up at least one [deployment method](https://insider.office.com/business/deploy).</span></span>

<span data-ttu-id="cce32-178">**Risorse git**.</span><span class="sxs-lookup"><span data-stu-id="cce32-178">**Git resources**.</span></span> <span data-ttu-id="cce32-179">Scaricare e installare una delle opzioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="cce32-179">Download and install one of the following.</span></span>

- [<span data-ttu-id="cce32-180">Git</span><span class="sxs-lookup"><span data-stu-id="cce32-180">Git</span></span>](https://git-scm.com/downloads)

- [<span data-ttu-id="cce32-181">GitHub desktop</span><span class="sxs-lookup"><span data-stu-id="cce32-181">GitHub Desktop</span></span>](https://desktop.github.com/)

- [<span data-ttu-id="cce32-182">GitHub Enterprise</span><span class="sxs-lookup"><span data-stu-id="cce32-182">GitHub Enterprise</span></span>](https://github.com/enterprise)

<span data-ttu-id="cce32-183">**Openssl** È necessario avere installato [openssl](https://slproweb.com/products/Win32OpenSSL.html) per [generare le chiavi di test](#generate-test-keys) dopo la distribuzione di DKE.</span><span class="sxs-lookup"><span data-stu-id="cce32-183">**OpenSSL** You must have [OpenSSL](https://slproweb.com/products/Win32OpenSSL.html) installed to [generate test keys](#generate-test-keys) after you deploy DKE.</span></span> <span data-ttu-id="cce32-184">Assicurarsi di richiamarlo correttamente dal percorso delle variabili di ambiente.</span><span class="sxs-lookup"><span data-stu-id="cce32-184">Make sure you're invoking it correctly from your environment variables path.</span></span> <span data-ttu-id="cce32-185">Ad esempio, vedere la sezione "aggiungere la directory di installazione al percorso" https://www.osradar.com/install-openssl-windows/ per informazioni dettagliate.</span><span class="sxs-lookup"><span data-stu-id="cce32-185">For example, see "Add the installation directory to PATH" at https://www.osradar.com/install-openssl-windows/ for details.</span></span>

#### <a name="double-key-encryption-prerequisites-for-client-computers"></a><span data-ttu-id="cce32-186">Prerequisiti per la crittografia a chiave doppia per i computer client</span><span class="sxs-lookup"><span data-stu-id="cce32-186">Double Key Encryption prerequisites for client computers</span></span>

<span data-ttu-id="cce32-187">Installare questi prerequisiti su ogni computer client in cui si desidera proteggere e utilizzare documenti protetti.</span><span class="sxs-lookup"><span data-stu-id="cce32-187">Install these prerequisites on each client computer where you want to protect and consume protected documents.</span></span>

<span data-ttu-id="cce32-188">**Microsoft Office** Version \*. 12711 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="cce32-188">**Microsoft Office** version \*.12711 or later.</span></span>

<span data-ttu-id="cce32-189">**Azure Information Protection Unified Labeling client** Versions 2.7.93.0 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="cce32-189">**Azure Information Protection Unified Labeling Client** versions 2.7.93.0 or later.</span></span> <span data-ttu-id="cce32-190">Scaricare e installare il client Unified Labeling da [Microsoft](https://www.microsoft.com/download/details.aspx?id=53018).</span><span class="sxs-lookup"><span data-stu-id="cce32-190">Download and install the Unified Labeling client from [Microsoft](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>

### <a name="clone-the-dke-github-repository"></a><span data-ttu-id="cce32-191">Clonare il repository di DKE GitHub</span><span class="sxs-lookup"><span data-stu-id="cce32-191">Clone the DKE GitHub repository</span></span>

<span data-ttu-id="cce32-192">Microsoft fornisce i file di origine di DKE in un repository GitHub.</span><span class="sxs-lookup"><span data-stu-id="cce32-192">Microsoft supplies the DKE source files in a GitHub repository.</span></span> <span data-ttu-id="cce32-193">È possibile clonare il repository per creare il progetto localmente per l'utilizzo dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="cce32-193">You clone the repository to build the project locally for your organization's use.</span></span> <span data-ttu-id="cce32-194">L'archivio di DKE GitHub si trova in [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService) .</span><span class="sxs-lookup"><span data-stu-id="cce32-194">The DKE GitHub repository is located at [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService).</span></span>

<span data-ttu-id="cce32-195">Le istruzioni riportate di seguito sono destinate agli utenti di codice git o Visual Studio inesperti:</span><span class="sxs-lookup"><span data-stu-id="cce32-195">The following instructions are intended for inexperienced git or Visual Studio Code users:</span></span>

1. <span data-ttu-id="cce32-196">Nel browser, vai a:[https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService)</span><span class="sxs-lookup"><span data-stu-id="cce32-196">In your browser, go to: [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService)</span></span>

1. <span data-ttu-id="cce32-197">Verso il lato destro dello schermo, selezionare **codice**.</span><span class="sxs-lookup"><span data-stu-id="cce32-197">Towards the right side of the screen, select **Code**.</span></span> <span data-ttu-id="cce32-198">La versione dell'interfaccia utente potrebbe mostrare un pulsante **Clone o download** .</span><span class="sxs-lookup"><span data-stu-id="cce32-198">Your version of the UI might show a **Clone or download** button.</span></span> <span data-ttu-id="cce32-199">Quindi, nell'elenco a discesa che viene visualizzato, selezionare l'icona copia per copiare l'URL negli Appunti.</span><span class="sxs-lookup"><span data-stu-id="cce32-199">Then, in the dropdown that appears, select the copy icon to copy the URL to your clipboard.</span></span>

    <span data-ttu-id="cce32-200">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="cce32-200">For example:</span></span>

    :::image type="content" source="../media/dke-clone.png" alt-text="Clonare il repository del servizio di crittografia a chiave doppia da GitHub":::

3. <span data-ttu-id="cce32-202">In Visual Studio Code, selezionare **Visualizza** \> **tavolozza dei comandi** e selezionare **git: Clone**.</span><span class="sxs-lookup"><span data-stu-id="cce32-202">In Visual Studio Code, select **View** \> **Command Palette** and select **Git: Clone**.</span></span> <span data-ttu-id="cce32-203">Per passare all'opzione nell'elenco, iniziare `git: clone` a digitare per filtrare le voci e quindi selezionarla dal menu a discesa.</span><span class="sxs-lookup"><span data-stu-id="cce32-203">To jump to the option in the list, start typing `git: clone` to filter the entries and then select it from the drop-down.</span></span> <span data-ttu-id="cce32-204">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="cce32-204">For example:</span></span>

    :::image type="content" source="../media/dke-vscode-clone.png" alt-text="Codice Visual Studio GIT: opzione Clone":::

4. <span data-ttu-id="cce32-206">Nella casella di testo incollare l'URL copiato da git e selezionare **Clone da GitHub**.</span><span class="sxs-lookup"><span data-stu-id="cce32-206">In the text box, paste the URL that you copied from Git and select **Clone from GitHub**.</span></span>

5. <span data-ttu-id="cce32-207">Nella finestra di dialogo **Seleziona cartella** visualizzata passare a e selezionare un percorso in cui archiviare il repository.</span><span class="sxs-lookup"><span data-stu-id="cce32-207">In the **Select Folder** dialog that appears, browse to and select a location to store the repository.</span></span> <span data-ttu-id="cce32-208">Al prompt dei comandi, selezionare **Apri**.</span><span class="sxs-lookup"><span data-stu-id="cce32-208">At the prompt, select **Open**.</span></span>

    <span data-ttu-id="cce32-209">L'archivio viene aperto in Visual Studio Code e visualizza il ramo git corrente in basso a sinistra.</span><span class="sxs-lookup"><span data-stu-id="cce32-209">The repository is opened in Visual Studio Code, and displays the current Git branch at the bottom left.</span></span> <span data-ttu-id="cce32-210">La succursale corrente deve essere **Master**.</span><span class="sxs-lookup"><span data-stu-id="cce32-210">Your current branch should be **master**.</span></span>

    <span data-ttu-id="cce32-211">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="cce32-211">For example:</span></span>

    :::image type="content" source="../media/dke-vscode-master.png" alt-text="Branch Master di Visual Studio Code":::

6. <span data-ttu-id="cce32-213">Selezionare il **Master** di Word e quindi selezionare **public_preview** nell'elenco dei rami.</span><span class="sxs-lookup"><span data-stu-id="cce32-213">Select the word **master,** and then select **public_preview** from the list of branches.</span></span> 

   > [!IMPORTANT]
   > <span data-ttu-id="cce32-214">Selezionando il ramo public_preview si garantisce che siano presenti i file corretti per la creazione del progetto.</span><span class="sxs-lookup"><span data-stu-id="cce32-214">Selecting the public_preview branch ensures that you have the correct files to build the project.</span></span> <span data-ttu-id="cce32-215">Se non si sceglie la succursale corretta, la distribuzione avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="cce32-215">If you do not choose the correct branch your deployment will fail.</span></span>

<span data-ttu-id="cce32-216">È ora necessario configurare l'archivio di origine di DKE localmente.</span><span class="sxs-lookup"><span data-stu-id="cce32-216">You now have your DKE source repository set up locally.</span></span> <span data-ttu-id="cce32-217">Successivamente, [modificare le impostazioni dell'applicazione](#modify-application-settings) per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="cce32-217">Next, [modify application settings](#modify-application-settings) for your organization.</span></span>

### <a name="modify-application-settings"></a><span data-ttu-id="cce32-218">Modificare le impostazioni dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="cce32-218">Modify application settings</span></span>

<span data-ttu-id="cce32-219">Per distribuire il servizio DKE, è necessario modificare i tipi di impostazioni dell'applicazione seguenti:</span><span class="sxs-lookup"><span data-stu-id="cce32-219">To deploy the DKE service, you must modify the following types of application settings:</span></span>

- [<span data-ttu-id="cce32-220">Impostazioni di accesso alle chiavi</span><span class="sxs-lookup"><span data-stu-id="cce32-220">Key access settings</span></span>](#key-access-settings)
- [<span data-ttu-id="cce32-221">Impostazioni del tenant e delle chiavi</span><span class="sxs-lookup"><span data-stu-id="cce32-221">Tenant and key settings</span></span>](#tenant-and-key-settings)

<span data-ttu-id="cce32-222">È possibile modificare le impostazioni dell'applicazione nel appsettings.jssu file.</span><span class="sxs-lookup"><span data-stu-id="cce32-222">You modify application settings in the appsettings.json file.</span></span> <span data-ttu-id="cce32-223">Questo file si trova nel repo di DoubleKeyEncryptionService clonato localmente in DoubleKeyEncryptionService\src\customer-key-store.</span><span class="sxs-lookup"><span data-stu-id="cce32-223">This file is located in the DoubleKeyEncryptionService repo you cloned locally under DoubleKeyEncryptionService\src\customer-key-store.</span></span> <span data-ttu-id="cce32-224">Ad esempio, in Visual Studio Code è possibile passare al file come illustrato nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="cce32-224">For example, in Visual Studio Code, you can browse to the file as shown in the following picture.</span></span>

:::image type="content" source="../media/dke-appsettingsjson.png" alt-text="Individuazione del appsettings.jssu file per DKE.":::

#### <a name="key-access-settings"></a><span data-ttu-id="cce32-226">Impostazioni di accesso alle chiavi</span><span class="sxs-lookup"><span data-stu-id="cce32-226">Key access settings</span></span>

<span data-ttu-id="cce32-227">Scegliere se utilizzare la posta elettronica o l'autorizzazione di ruolo.</span><span class="sxs-lookup"><span data-stu-id="cce32-227">Choose whether to use email or role authorization.</span></span> <span data-ttu-id="cce32-228">DKE supporta solo uno di questi metodi di autenticazione alla volta.</span><span class="sxs-lookup"><span data-stu-id="cce32-228">DKE supports only one of these authentication methods at a time.</span></span>

- <span data-ttu-id="cce32-229">**Autorizzazione per la posta elettronica**.</span><span class="sxs-lookup"><span data-stu-id="cce32-229">**Email authorization**.</span></span> <span data-ttu-id="cce32-230">Consente all'organizzazione di autorizzare l'accesso alle chiavi solo in base agli indirizzi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="cce32-230">Allows your organization to authorize access to keys based on email addresses only.</span></span>

- <span data-ttu-id="cce32-231">**Autorizzazione ruolo**.</span><span class="sxs-lookup"><span data-stu-id="cce32-231">**Role authorization**.</span></span> <span data-ttu-id="cce32-232">Consente all'organizzazione di autorizzare l'accesso ai tasti basati su gruppi di Active Directory e richiede che il servizio Web possa eseguire query su LDAP.</span><span class="sxs-lookup"><span data-stu-id="cce32-232">Allows your organization to authorize access to keys based on Active Directory groups, and requires that the web service can query LDAP.</span></span>

<span data-ttu-id="cce32-233">Per impostare le impostazioni di accesso alle chiavi per DKE:</span><span class="sxs-lookup"><span data-stu-id="cce32-233">To set key access settings for DKE:</span></span>

1. <span data-ttu-id="cce32-234">Nel **appsettings.jssu** file, definire solo una delle seguenti impostazioni:</span><span class="sxs-lookup"><span data-stu-id="cce32-234">In the **appsettings.json** file, define only one of these settings:</span></span>

   - <span data-ttu-id="cce32-235">Per l'autorizzazione alla posta elettronica, individuare l'impostazione **AuthorizedEmailAddresses** .</span><span class="sxs-lookup"><span data-stu-id="cce32-235">For email authorization, locate the **AuthorizedEmailAddresses** setting.</span></span> <span data-ttu-id="cce32-236">Aggiungere l'indirizzo di posta elettronica che si desidera autorizzare.</span><span class="sxs-lookup"><span data-stu-id="cce32-236">Add the email address that you want to authorize.</span></span> <span data-ttu-id="cce32-237">Separare più indirizzi di posta elettronica con virgolette doppie e virgole.</span><span class="sxs-lookup"><span data-stu-id="cce32-237">Separate multiple email addresses with double quotes and commas.</span></span> <span data-ttu-id="cce32-238">Ad esempio: **"' AuthorizedEmailAddresses '": ["email1@company.com", "email2@company.com", email3@company.com]**</span><span class="sxs-lookup"><span data-stu-id="cce32-238">For example: **" ‘AuthorizedEmailAddresses’ ": ["email1@company.com", "email2@company.com ", email3@company.com]**</span></span>

   :::image type="content" source="../media/dke-email-accesssetting.png" alt-text="appsettings.jsnel file che mostra il metodo di autorizzazione della posta elettronica":::

   - <span data-ttu-id="cce32-240">Per l'autorizzazione ruolo, individuare l'impostazione **AuthorizedRoles** .</span><span class="sxs-lookup"><span data-stu-id="cce32-240">For role authorization, locate the **AuthorizedRoles** setting.</span></span> <span data-ttu-id="cce32-241">Definire con i nomi dei gruppi di ActiveDirectory che si desidera autorizzare.</span><span class="sxs-lookup"><span data-stu-id="cce32-241">Define with the ActiveDirectory group names you want to authorize.</span></span> <span data-ttu-id="cce32-242">Ad esempio: **"AuthorizedRoles": ["group1", "group2", "Group3"]**</span><span class="sxs-lookup"><span data-stu-id="cce32-242">For example: **"AuthorizedRoles": ["group1", "group2", "group3"]**</span></span>

   :::image type="content" source="../media/dke-role-accesssetting.png" alt-text="appsettings.jsnel file che mostra il metodo di autorizzazione ruolo":::

2. <span data-ttu-id="cce32-244">Rimuovere l'impostazione che non è pertinente per il metodo di autorizzazione scelto.</span><span class="sxs-lookup"><span data-stu-id="cce32-244">Remove the setting that isn't relevant for your chosen authorization method.</span></span>

#### <a name="tenant-and-key-settings"></a><span data-ttu-id="cce32-245">Impostazioni del tenant e delle chiavi</span><span class="sxs-lookup"><span data-stu-id="cce32-245">Tenant and key settings</span></span>

<span data-ttu-id="cce32-246">Le impostazioni del tenant e della chiave di DKE si trovano nel **appsettings.jssu** file e nel file **Startup.cs** .</span><span class="sxs-lookup"><span data-stu-id="cce32-246">DKE tenant and key settings are located in the **appsettings.json** file and the **startup.cs** file.</span></span>

<span data-ttu-id="cce32-247">Nel file **appsettings.jssu** , modificare i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="cce32-247">In the **appsettings.json** file, modify the following values:</span></span>

- <span data-ttu-id="cce32-248">**ValidIssuers**.</span><span class="sxs-lookup"><span data-stu-id="cce32-248">**ValidIssuers**.</span></span> <span data-ttu-id="cce32-249">Sostituisci `<tenantid>` con il GUID del tenant.</span><span class="sxs-lookup"><span data-stu-id="cce32-249">Replace `<tenantid>` with your tenant GUID.</span></span>
- <span data-ttu-id="cce32-250">**JwtAudience**.</span><span class="sxs-lookup"><span data-stu-id="cce32-250">**JwtAudience**.</span></span> <span data-ttu-id="cce32-251">Sostituire `<yourhostname>` con il nome host del computer in cui verrà eseguito il servizio DKE.</span><span class="sxs-lookup"><span data-stu-id="cce32-251">Replace `<yourhostname>` with the hostname of the machine where the DKE service will run.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="cce32-252">Il valore di JwtAudience deve corrispondere *esattamente*al nome dell'host.</span><span class="sxs-lookup"><span data-stu-id="cce32-252">The value for JwtAudience must match the name of your host *exactly*.</span></span> <span data-ttu-id="cce32-253">È possibile utilizzare **localhost: 5000** durante il debug.</span><span class="sxs-lookup"><span data-stu-id="cce32-253">You may use **localhost:5000** while debugging.</span></span> <span data-ttu-id="cce32-254">Tuttavia, al termine del debug, aggiornare questo valore al nome host del server.</span><span class="sxs-lookup"><span data-stu-id="cce32-254">However, When you're done debugging, make sure to update this value to the server's hostname.</span></span>

- <span data-ttu-id="cce32-255">**LDAPPath**.</span><span class="sxs-lookup"><span data-stu-id="cce32-255">**LDAPPath**.</span></span> <span data-ttu-id="cce32-256">Impostare il valore come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="cce32-256">Set the value as follows:</span></span>

  - <span data-ttu-id="cce32-257">Se si sta utilizzando l'autorizzazione di ruolo, immettere il dominio LDAP.</span><span class="sxs-lookup"><span data-stu-id="cce32-257">If you're using role authorization, enter the LDAP domain.</span></span>
  - <span data-ttu-id="cce32-258">Se si utilizza l'autorizzazione per la posta elettronica, lasciare vuoto questo valore.</span><span class="sxs-lookup"><span data-stu-id="cce32-258">If you're using email authorization, leave this value empty.</span></span>

   <span data-ttu-id="cce32-259">Per ulteriori informazioni, vedere [Key Access Settings](#key-access-settings).</span><span class="sxs-lookup"><span data-stu-id="cce32-259">For more information, see [Key access settings](#key-access-settings).</span></span>

- <span data-ttu-id="cce32-260">**TestKeys: nome**.</span><span class="sxs-lookup"><span data-stu-id="cce32-260">**TestKeys:Name**.</span></span> <span data-ttu-id="cce32-261">Immettere un nome per la chiave.</span><span class="sxs-lookup"><span data-stu-id="cce32-261">Enter a name for your key.</span></span> <span data-ttu-id="cce32-262">Esempio: **testKey1**</span><span class="sxs-lookup"><span data-stu-id="cce32-262">Example: **TestKey1**</span></span>
- <span data-ttu-id="cce32-263">**TestKeys: ID**. Creare un GUID e immetterlo come valore **TestKeys: ID** .</span><span class="sxs-lookup"><span data-stu-id="cce32-263">**TestKeys:Id**. Create a GUID and enter it as the **TestKeys:ID** value.</span></span> <span data-ttu-id="cce32-264">Ad esempio, **DCE1CC21-FF9B-4424-8FF4-9914BD19A1BE**.</span><span class="sxs-lookup"><span data-stu-id="cce32-264">For example, **DCE1CC21-FF9B-4424-8FF4-9914BD19A1BE**.</span></span> <span data-ttu-id="cce32-265">È possibile utilizzare un sito come [Generatore di GUID online](https://guidgenerator.com/) per generare casualmente un GUID.</span><span class="sxs-lookup"><span data-stu-id="cce32-265">You can use a site like [Online GUID Generator](https://guidgenerator.com/) to randomly generate a GUID.</span></span>

### <a name="generate-test-keys"></a><span data-ttu-id="cce32-266">Generare i tasti di testing</span><span class="sxs-lookup"><span data-stu-id="cce32-266">Generate test keys</span></span>

<span data-ttu-id="cce32-267">Una volta definite le impostazioni dell'applicazione, si è pronti a generare chiavi di test pubbliche e private.</span><span class="sxs-lookup"><span data-stu-id="cce32-267">Once you have your application settings defined, you're ready to generate public and private test keys.</span></span>

<span data-ttu-id="cce32-268">Per generare chiavi:</span><span class="sxs-lookup"><span data-stu-id="cce32-268">To generate keys:</span></span>

1. <span data-ttu-id="cce32-269">Dal menu Start di Windows, eseguire il prompt dei comandi di OpenSSL.</span><span class="sxs-lookup"><span data-stu-id="cce32-269">From the Windows Start menu, run the OpenSSL Command Prompt.</span></span>

1. <span data-ttu-id="cce32-270">Passare alla cartella in cui si desidera salvare i tasti di test.</span><span class="sxs-lookup"><span data-stu-id="cce32-270">Change to the folder where you want to save the test keys.</span></span> <span data-ttu-id="cce32-271">I file creati eseguendo la procedura descritta in questa attività sono archiviati nella stessa cartella.</span><span class="sxs-lookup"><span data-stu-id="cce32-271">The files you create by completing the steps in this task are stored in the same folder.</span></span>

1. <span data-ttu-id="cce32-272">Generare il nuovo tasto di test.</span><span class="sxs-lookup"><span data-stu-id="cce32-272">Generate the new test key.</span></span>

   ```dos
   openssl req -x509 -newkey rsa:2048 -keyout key.pem -out cert.pem -days 365
   ```

2. <span data-ttu-id="cce32-273">Generare la chiave privata.</span><span class="sxs-lookup"><span data-stu-id="cce32-273">Generate the private key.</span></span>

   ```dos
   openssl rsa -in key.pem -out privkeynopass.pem
   ```

1. <span data-ttu-id="cce32-274">Generare la chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="cce32-274">Generate the public key.</span></span>

   ```dos
   openssl rsa -in key.pem -pubout > pubkeyonly.pem
   ```

1. <span data-ttu-id="cce32-275">In un editor di testo aprire **pubkeyonly. pem**.</span><span class="sxs-lookup"><span data-stu-id="cce32-275">In a text editor, open **pubkeyonly.pem**.</span></span> <span data-ttu-id="cce32-276">Copiare tutto il contenuto del file **pubkeyonly. pem** , tranne la prima e l'ultima riga, nella sezione **PublicPem** del **appsettings.jssu** file.</span><span class="sxs-lookup"><span data-stu-id="cce32-276">Copy all of the content in the **pubkeyonly.pem** file, except the first and last lines, into the **PublicPem** section of the **appsettings.json** file.</span></span>

1. <span data-ttu-id="cce32-277">In un editor di testo aprire **privkeynopass. pem**.</span><span class="sxs-lookup"><span data-stu-id="cce32-277">In a text editor, open **privkeynopass.pem**.</span></span> <span data-ttu-id="cce32-278">Copiare tutto il contenuto del file **privkeynopass. pem** , tranne la prima e l'ultima riga, nella sezione **PrivatePem** del **appsettings.jssu** file.</span><span class="sxs-lookup"><span data-stu-id="cce32-278">Copy all of the content in the **privkeynopass.pem** file, except the first and last lines, into the **PrivatePem** section of the **appsettings.json** file.</span></span>

1. <span data-ttu-id="cce32-279">Rimuovere tutti gli spazi vuoti e le nuove righe nelle sezioni **PublicPem** e **PrivatePem** .</span><span class="sxs-lookup"><span data-stu-id="cce32-279">Remove all blank spaces and newlines in both the **PublicPem** and **PrivatePem** sections.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="cce32-280">Quando si copia questo contenuto, non eliminare i dati PEM.</span><span class="sxs-lookup"><span data-stu-id="cce32-280">When you copy this content, do not delete any of the PEM data.</span></span>

1. <span data-ttu-id="cce32-281">Aprire il file **Startup.cs** e individuare le righe seguenti:</span><span class="sxs-lookup"><span data-stu-id="cce32-281">Open the **Startup.cs** file, and locate the following lines:</span></span>

   ```c#
        #if USE_TEST_KEYS
        #error !!!!!!!!!!!!!!!!!!!!!! Use of test keys is only supported for testing,
        DO NOT USE  FOR PRODUCTION !!!!!!!!!!!!!!!!!!!!!!!!!!!!!
        services.AddSingleton<ippw.IKeyStore, ippw.TestKeyStore>();
        #endif
   ```

1. <span data-ttu-id="cce32-282">Sostituire queste righe con il testo seguente:</span><span class="sxs-lookup"><span data-stu-id="cce32-282">Replace these lines with the following text:</span></span>

   ```csharp
   services.AddSingleton<ippw.IKeyStore, ippw.TestKeyStore>();
   ```

   <span data-ttu-id="cce32-283">I risultati finali devono essere simili all'immagine seguente.</span><span class="sxs-lookup"><span data-stu-id="cce32-283">The end results should look similar to the following picture.</span></span>

   :::image type="content" source="../media/dke-startupcs-usetestkeys.png" alt-text="file di startup.cs per l'anteprima pubblica":::

<span data-ttu-id="cce32-285">A questo punto si è pronti per [creare il progetto di DKE](#build-the-project).</span><span class="sxs-lookup"><span data-stu-id="cce32-285">Now you're ready to [build your DKE project](#build-the-project).</span></span>

### <a name="build-the-project"></a><span data-ttu-id="cce32-286">Generare il progetto</span><span class="sxs-lookup"><span data-stu-id="cce32-286">Build the project</span></span>

<span data-ttu-id="cce32-287">Utilizzare le istruzioni seguenti per creare localmente il progetto DKE:</span><span class="sxs-lookup"><span data-stu-id="cce32-287">Use the following instructions to build the DKE project locally:</span></span>

1. <span data-ttu-id="cce32-288">In Visual Studio Code, nell'archivio dei servizi di DKE, selezionare **Visualizza** \> **tavolozza dei comandi** e quindi digitare **Compila** al prompt.</span><span class="sxs-lookup"><span data-stu-id="cce32-288">In Visual Studio Code, in the DKE service repository, select **View** \> **Command Palette** and then type **build** at the prompt.</span></span>

1. <span data-ttu-id="cce32-289">Nell'elenco scegliere **attività: Esegui attività di compilazione**.</span><span class="sxs-lookup"><span data-stu-id="cce32-289">From the list, choose **Tasks: Run build task**.</span></span>

   <span data-ttu-id="cce32-290">Se non sono state trovate attività di compilazione, selezionare **Configura attività di compilazione** e crearne una per .NET Core come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="cce32-290">If there are no build tasks found, select **Configure Build Task** and create one for .NET core as follows.</span></span>

   :::image type="content" source="../media/dke-configurebuildtask.png" alt-text="Configurare l'attività di compilazione mancante per .NET":::

   1. <span data-ttu-id="cce32-292">Scegliere **crea tasks.jssu da modello**.</span><span class="sxs-lookup"><span data-stu-id="cce32-292">Choose **Create tasks.json from template**.</span></span>

   :::image type="content" source="../media/dke-createtasksjsonfromtemplate.png" alt-text="Creare tasks.jssu file da modello per DKE":::

   2. <span data-ttu-id="cce32-294">Nell'elenco dei tipi di modello selezionare **.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="cce32-294">From the list of template types, select **.NET Core**.</span></span>

   :::image type="content" source="../media/dke-tasksjsontemplate.png" alt-text="Creare tasks.jssu file da modello per DKE":::

   3. <span data-ttu-id="cce32-296">Nella sezione generazione individuare il percorso del file **customerkeystore. csproj** .</span><span class="sxs-lookup"><span data-stu-id="cce32-296">In the build section, locate the path to the **customerkeystore.csproj** file.</span></span> <span data-ttu-id="cce32-297">Se non è presente, aggiungere la riga seguente:</span><span class="sxs-lookup"><span data-stu-id="cce32-297">If it's not there, add the following line:</span></span>

      ```json
      "${workspaceFolder}/src/customer-key-store/customerkeystore.csproj",
      ```

  4. <span data-ttu-id="cce32-298">Eseguire di nuovo la Build.</span><span class="sxs-lookup"><span data-stu-id="cce32-298">Run the build again.</span></span>

1. <span data-ttu-id="cce32-299">Verificare che non vi siano errori rossi nella finestra di output.</span><span class="sxs-lookup"><span data-stu-id="cce32-299">Verify that there are no red errors in the output window.</span></span>

   <span data-ttu-id="cce32-300">Se sono presenti errori rossi, controllare l'output della console.</span><span class="sxs-lookup"><span data-stu-id="cce32-300">If there are red errors, check the console output.</span></span> <span data-ttu-id="cce32-301">Verificare che siano stati completati correttamente tutti i passaggi precedenti e che siano presenti le versioni di compilazione corrette.</span><span class="sxs-lookup"><span data-stu-id="cce32-301">Ensure that you completed all the previous steps correctly and the correct build versions are present.</span></span>

1. <span data-ttu-id="cce32-302">**Eseguire** \> **Avviare il debug** per eseguire il debug del processo.</span><span class="sxs-lookup"><span data-stu-id="cce32-302">**Run** \> **Start Debugging** to debug the process.</span></span> <span data-ttu-id="cce32-303">Se viene richiesto di selezionare un ambiente, selezionare **.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="cce32-303">If you're prompted to select an environment, select **.NET core**.</span></span>

<span data-ttu-id="cce32-304">Il debugger di base di .NET in genere viene avviato in **https://localhost:5001** .</span><span class="sxs-lookup"><span data-stu-id="cce32-304">The .NET core debugger typically launches to **https://localhost:5001**.</span></span> <span data-ttu-id="cce32-305">Per visualizzare la chiave di test, passare a **https://localhost:5001** e aggiungere una barra (/) e il nome della chiave.</span><span class="sxs-lookup"><span data-stu-id="cce32-305">To view your test key, go to **https://localhost:5001**, and append a forward slash (/) and the name of your key.</span></span>

<span data-ttu-id="cce32-306">Per esempio:**https://localhost:5001/TestKey1**</span><span class="sxs-lookup"><span data-stu-id="cce32-306">For example: **https://localhost:5001/TestKey1**</span></span>

<span data-ttu-id="cce32-307">Il tasto dovrebbe essere visualizzato in formato JSON.</span><span class="sxs-lookup"><span data-stu-id="cce32-307">The key should display in JSON format.</span></span>

<span data-ttu-id="cce32-308">La configurazione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="cce32-308">Your setup is now complete.</span></span> <span data-ttu-id="cce32-309">Prima di pubblicare il keystore, in appsettings.jssu, per l'impostazione JwtAudience, assicurarsi che il valore di hostname corrisponda esattamente al nome host del servizio app.</span><span class="sxs-lookup"><span data-stu-id="cce32-309">Before you publish the keystore, in appsettings.json, for the JwtAudience setting, ensure the value for hostname exactly matches your App Service host name.</span></span> <span data-ttu-id="cce32-310">Potrebbe essere stata modificata in localhost per risolvere i problemi relativi alla generazione.</span><span class="sxs-lookup"><span data-stu-id="cce32-310">You may have changed it to localhost to troubleshoot the build.</span></span>

### <a name="publish-the-key-store"></a><span data-ttu-id="cce32-311">Pubblicare l'archivio delle chiavi</span><span class="sxs-lookup"><span data-stu-id="cce32-311">Publish the key store</span></span>

<span data-ttu-id="cce32-312">Nella procedura seguente viene descritto come creare un'istanza del servizio app di Azure per ospitare la distribuzione di DKE e come pubblicare le chiavi generate in Azure.</span><span class="sxs-lookup"><span data-stu-id="cce32-312">The following steps describe how to create an Azure App Service instance to host your DKE deployment, and how to publish your generated keys to Azure.</span></span>

<span data-ttu-id="cce32-313">Per creare un'istanza di Azure Web App per ospitare la distribuzione di DKE:</span><span class="sxs-lookup"><span data-stu-id="cce32-313">To create an Azure Web App instance to host your DKE deployment:</span></span>

1. <span data-ttu-id="cce32-314">Nel browser, accedere al [portale di Microsoft Azure](https://ms.portal.azure.com)e passare a **app Services**  >  **Add**.</span><span class="sxs-lookup"><span data-stu-id="cce32-314">In your browser, sign in to the [Microsoft Azure portal](https://ms.portal.azure.com), and go to **App Services** > **Add**.</span></span>

1. <span data-ttu-id="cce32-315">Selezionare l'abbonamento e il gruppo di risorse e definire i dettagli dell'istanza.</span><span class="sxs-lookup"><span data-stu-id="cce32-315">Select your subscription and resource group and define your instance details.</span></span>

    - <span data-ttu-id="cce32-316">Immettere il nome host del computer in cui si desidera installare il servizio DKE.</span><span class="sxs-lookup"><span data-stu-id="cce32-316">Enter the hostname of the computer where you want to install the DKE service.</span></span> <span data-ttu-id="cce32-317">Verificare che sia lo stesso nome di quello definito per l'impostazione JwtAudience nel [**appsettings.jssu**](#tenant-and-key-settings) file.</span><span class="sxs-lookup"><span data-stu-id="cce32-317">Make sure it's the same name as the one defined for the JwtAudience setting in the [**appsettings.json**](#tenant-and-key-settings) file.</span></span> <span data-ttu-id="cce32-318">Il valore specificato per il nome è anche WebAppInstanceName.</span><span class="sxs-lookup"><span data-stu-id="cce32-318">The value you provide for the name is also the WebAppInstanceName.</span></span>

    - <span data-ttu-id="cce32-319">Per la **pubblicazione**, selezionare **codice**e per **stack di Runtime**, selezionare **.NET Core 3,1**.</span><span class="sxs-lookup"><span data-stu-id="cce32-319">For **Publish**, select **code**, and for **Runtime stack**, select **.NET Core 3.1**.</span></span>

    <span data-ttu-id="cce32-320">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="cce32-320">For example:</span></span>

    :::image type="content" source="../media/dke-azure-add-app-service.png" alt-text="Aggiungere il servizio app":::

1. <span data-ttu-id="cce32-322">Nella parte inferiore della pagina, selezionare **revisione + crea**e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="cce32-322">At the bottom of the page, select **Review + create**, and then select **Add**.</span></span>

1. <span data-ttu-id="cce32-323">Per pubblicare le chiavi generate in Azure, eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cce32-323">Do one of the following to publish your generated keys to Azure:</span></span>

    - [<span data-ttu-id="cce32-324">Pubblicare tramite ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="cce32-324">Publish via ZipDeployUI</span></span>](#publish-via-zipdeployui)
    - [<span data-ttu-id="cce32-325">Pubblicare tramite FTP</span><span class="sxs-lookup"><span data-stu-id="cce32-325">Publish via FTP</span></span>](#publish-via-ftp)
    - [<span data-ttu-id="cce32-326">Pubblicare tramite Visual Studio 2019 o versione successiva</span><span class="sxs-lookup"><span data-stu-id="cce32-326">Publish via Visual Studio 2019 or later</span></span>](https://docs.microsoft.com/aspnet/core/tutorials/)
    - [<span data-ttu-id="cce32-327">Pubblicare in un sistema locale</span><span class="sxs-lookup"><span data-stu-id="cce32-327">Publish to an on-premises system</span></span>](https://docs.microsoft.com/aspnet/core/tutorials/publish-to-iis?view=aspnetcore-3.1&tabs=netcore-cli)

    > [!NOTE]
    > <span data-ttu-id="cce32-328">È possibile preferire altri metodi per distribuire le chiavi.</span><span class="sxs-lookup"><span data-stu-id="cce32-328">You may prefer other methods to deploy your keys.</span></span> <span data-ttu-id="cce32-329">Selezionare il metodo più adatto per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="cce32-329">Select the method that works best for your organization.</span></span>

    > [!TIP]
    > <span data-ttu-id="cce32-330">La [pubblicazione tramite Visual Studio](https://docs.microsoft.com/aspnet/core/tutorials/) e un [sistema locale](https://docs.microsoft.com/aspnet/core/tutorials/publish-to-iis?view=aspnetcore-3.1&tabs=netcore-cli) è descritta nella [documentazione ASP .NET](https://docs.microsoft.com/aspnet/core/).</span><span class="sxs-lookup"><span data-stu-id="cce32-330">[Publishing via Visual Studio](https://docs.microsoft.com/aspnet/core/tutorials/) and to an [on-premises system](https://docs.microsoft.com/aspnet/core/tutorials/publish-to-iis?view=aspnetcore-3.1&tabs=netcore-cli) is described in the [ASP .NET documentation](https://docs.microsoft.com/aspnet/core/).</span></span> <span data-ttu-id="cce32-331">Se si utilizza uno di questi metodi, aprire le istruzioni in una scheda separata in modo che sia possibile tornare facilmente al termine.</span><span class="sxs-lookup"><span data-stu-id="cce32-331">If you use one of these methods, open the instructions in a separate tab so that you can return here easily when you're done.</span></span>

#### <a name="publish-via-zipdeployui"></a><span data-ttu-id="cce32-332">Pubblicare tramite ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="cce32-332">Publish via ZipDeployUI</span></span>

1. <span data-ttu-id="cce32-333">Passare a `https://<WebAppInstanceName>.scm.azurewebsites.net/ZipDeployUI`.</span><span class="sxs-lookup"><span data-stu-id="cce32-333">Go to `https://<WebAppInstanceName>.scm.azurewebsites.net/ZipDeployUI`.</span></span>

    <span data-ttu-id="cce32-334">Ad esempio: https://customerkeystoreforpublicpreview.scm.azurewebsites.net/ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="cce32-334">For example: https://customerkeystoreforpublicpreview.scm.azurewebsites.net/ZipDeployUI</span></span>

1. <span data-ttu-id="cce32-335">Nella codebase per l'archivio delle chiavi passare alla cartella **Customer-Key-store\src\customer-Key-Store** e verificare che la cartella contenga il file **customerkeystore. csproj** .</span><span class="sxs-lookup"><span data-stu-id="cce32-335">In the codebase for the key store, go to the **customer-key-store\src\customer-key-store** folder, and verify that this folder contains the **customerkeystore.csproj** file.</span></span>

1. <span data-ttu-id="cce32-336">Esegui: **pubblicazione di DotNet**</span><span class="sxs-lookup"><span data-stu-id="cce32-336">Run: **dotnet publish**</span></span>

     <span data-ttu-id="cce32-337">La finestra di output Visualizza la directory in cui è stata distribuita la pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="cce32-337">The output window displays the directory where the publish was deployed.</span></span>

    <span data-ttu-id="cce32-338">Ad esempio: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span><span class="sxs-lookup"><span data-stu-id="cce32-338">For example: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span></span>

1. <span data-ttu-id="cce32-339">Inviare tutti i file nella directory di pubblicazione a un file con estensione zip.</span><span class="sxs-lookup"><span data-stu-id="cce32-339">Send all files in the publish directory to a .zip file.</span></span> <span data-ttu-id="cce32-340">Quando si crea il file con estensione zip, verificare che tutti i file presenti nella directory si trovino nel livello radice del file. zip.</span><span class="sxs-lookup"><span data-stu-id="cce32-340">When creating the .zip file, make sure that all files in the directory are at the root level of the .zip file.</span></span>

1. <span data-ttu-id="cce32-341">Trascinare e rilasciare il file con estensione zip creato nel sito di ZipDeployUI che è stato aperto.</span><span class="sxs-lookup"><span data-stu-id="cce32-341">Drag and drop the .zip file you create to the ZipDeployUI site you opened above.</span></span> <span data-ttu-id="cce32-342">Ad esempio: https://customerkeystoreforpublicpreview.scm.azurewebsites.net/ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="cce32-342">For example: https://customerkeystoreforpublicpreview.scm.azurewebsites.net/ZipDeployUI</span></span>

<span data-ttu-id="cce32-343">DKE è distribuito ed è possibile passare alle chiavi di test create.</span><span class="sxs-lookup"><span data-stu-id="cce32-343">DKE is deployed and you can browse to the test keys you've created.</span></span> <span data-ttu-id="cce32-344">Continuare a [convalidare la distribuzione](#validate-your-deployment) seguente.</span><span class="sxs-lookup"><span data-stu-id="cce32-344">Continue to [Validate your deployment](#validate-your-deployment) below.</span></span>

#### <a name="publish-via-ftp"></a><span data-ttu-id="cce32-345">Pubblicare tramite FTP</span><span class="sxs-lookup"><span data-stu-id="cce32-345">Publish via FTP</span></span>

1. <span data-ttu-id="cce32-346">Connettersi al servizio app creato [precedentemente](#publish-the-key-store).</span><span class="sxs-lookup"><span data-stu-id="cce32-346">Connect to the App Service you created [above](#publish-the-key-store).</span></span>

    <span data-ttu-id="cce32-347">Nel browser passare a: **Azure portal**  >  **App Service**  >  **Deployment Center**  >  **Manual Deployment**  >  **FTP**  >  **Dashboard**FTP Deployment Center di distribuzione manuale di Azure Portal app.</span><span class="sxs-lookup"><span data-stu-id="cce32-347">In your browser, go to: **Azure portal** > **App Service** > **Deployment Center** > **Manual Deployment** > **FTP** > **Dashboard**.</span></span>

1. <span data-ttu-id="cce32-348">Copiare le stringhe di connessione visualizzate in un file locale.</span><span class="sxs-lookup"><span data-stu-id="cce32-348">Copy the connection strings displayed to a local file.</span></span> <span data-ttu-id="cce32-349">Queste stringhe verranno utilizzate per la connessione al servizio Web App e per il caricamento dei file tramite FTP.</span><span class="sxs-lookup"><span data-stu-id="cce32-349">You'll use these strings to connect to the Web App Service and upload files via FTP.</span></span>

    <span data-ttu-id="cce32-350">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="cce32-350">For example:</span></span>

    :::image type="content" source="../media/dke-ftp-dashboard.png" alt-text="Copiare le stringhe di connessione dal dashboard FTP":::

1. <span data-ttu-id="cce32-352">Nella codebase per l'archiviazione delle chiavi passare alla **directory Customer-Key-store\src\customer-Key-Store**</span><span class="sxs-lookup"><span data-stu-id="cce32-352">In the codebase for the key storage, go to the **customer-key-store\src\customer-key-store directory**.</span></span>

1. <span data-ttu-id="cce32-353">Verificare che la directory contenga il file **customerkeystore. csproj** .</span><span class="sxs-lookup"><span data-stu-id="cce32-353">Verify that this directory contains the **customerkeystore.csproj** file.</span></span>

1. <span data-ttu-id="cce32-354">Esegui: **pubblicazione di DotNet**</span><span class="sxs-lookup"><span data-stu-id="cce32-354">Run: **dotnet publish**</span></span>

    <span data-ttu-id="cce32-355">L'output contiene la directory in cui è stata distribuita la pubblicazione.</span><span class="sxs-lookup"><span data-stu-id="cce32-355">The output contains the directory where the publish was deployed.</span></span>

    <span data-ttu-id="cce32-356">Ad esempio: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span><span class="sxs-lookup"><span data-stu-id="cce32-356">For example: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span></span>

1. <span data-ttu-id="cce32-357">Inviare tutti i file nella directory di pubblicazione in un file zip.</span><span class="sxs-lookup"><span data-stu-id="cce32-357">Send all files in the publish directory to a zip file.</span></span> <span data-ttu-id="cce32-358">Quando si crea il file con estensione zip, verificare che tutti i file presenti nella directory si trovino nel livello radice del file. zip.</span><span class="sxs-lookup"><span data-stu-id="cce32-358">When creating the .zip file, make sure that all files in the directory are at the root level of the .zip file.</span></span>

1. <span data-ttu-id="cce32-359">Dal client FTP, utilizzare le informazioni di connessione copiate per la connessione al servizio app.</span><span class="sxs-lookup"><span data-stu-id="cce32-359">From your FTP client, use the connection information you copied to connect to your App Service.</span></span> <span data-ttu-id="cce32-360">Caricare il file con estensione zip creato nel passaggio precedente alla directory radice dell'app Web.</span><span class="sxs-lookup"><span data-stu-id="cce32-360">Upload the .zip file you created in the previous step to the root directory of your Web App.</span></span>

<span data-ttu-id="cce32-361">DKE è distribuito ed è possibile passare alle chiavi di test create.</span><span class="sxs-lookup"><span data-stu-id="cce32-361">DKE is deployed and you can browse to the test keys you'd created.</span></span> <span data-ttu-id="cce32-362">Successivamente, [convalidare la distribuzione](#validate-your-deployment).</span><span class="sxs-lookup"><span data-stu-id="cce32-362">Next, [Validate your deployment](#validate-your-deployment).</span></span>

### <a name="validate-your-deployment"></a><span data-ttu-id="cce32-363">Convalidare la distribuzione</span><span class="sxs-lookup"><span data-stu-id="cce32-363">Validate your deployment</span></span>

<span data-ttu-id="cce32-364">Dopo aver distribuito DKE utilizzando uno dei metodi descritti in alto, convalidare la distribuzione e le impostazioni dell'archivio chiavi.</span><span class="sxs-lookup"><span data-stu-id="cce32-364">After deploying DKE using one of the methods described above, validate the deployment and the key store settings.</span></span>

<span data-ttu-id="cce32-365">Eseguire: </span><span class="sxs-lookup"><span data-stu-id="cce32-365">Run:</span></span>

<span data-ttu-id="cce32-366">src\customer-key-store\scripts\key_store_tester.ps1 mykeystoreurl/MyKey</span><span class="sxs-lookup"><span data-stu-id="cce32-366">src\customer-key-store\scripts\key_store_tester.ps1 mykeystoreurl/mykey</span></span>

<span data-ttu-id="cce32-367">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="cce32-367">For example:</span></span>

<span data-ttu-id="cce32-368">key_store_tester.ps1https://mycustomerkeystore.com/mykey</span><span class="sxs-lookup"><span data-stu-id="cce32-368">key_store_tester.ps1 https://mycustomerkeystore.com/mykey</span></span>

<span data-ttu-id="cce32-369">Assicurarsi che non vengano visualizzati errori nell'output.</span><span class="sxs-lookup"><span data-stu-id="cce32-369">Ensure that no errors appear in the output.</span></span> <span data-ttu-id="cce32-370">Quando si è pronti, [registrare il proprio archivio delle chiavi](#register-your-key-store).</span><span class="sxs-lookup"><span data-stu-id="cce32-370">When you're ready, [register your key store](#register-your-key-store).</span></span>

## <a name="register-your-key-store"></a><span data-ttu-id="cce32-371">Registrare il proprio archivio delle chiavi</span><span class="sxs-lookup"><span data-stu-id="cce32-371">Register your key store</span></span>

<span data-ttu-id="cce32-372">La procedura seguente consente di registrare il proprio archivio chiavi.</span><span class="sxs-lookup"><span data-stu-id="cce32-372">The following steps enable you to register your key store.</span></span> <span data-ttu-id="cce32-373">La registrazione dell'archivio delle chiavi è l'ultimo passaggio della distribuzione di DKE prima di iniziare a creare etichette.</span><span class="sxs-lookup"><span data-stu-id="cce32-373">Registering your key store is the last step in deploying DKE before you can start creating labels.</span></span>

<span data-ttu-id="cce32-374">Per registrare l'archivio delle chiavi:</span><span class="sxs-lookup"><span data-stu-id="cce32-374">To register your key store:</span></span>

1. <span data-ttu-id="cce32-375">Nel browser aprire il portale di [Microsoft Azure](https://ms.portal.azure.com/)e passare a **tutte le** \> **Identity** \> **registrazioni delle app**di identità dei servizi.</span><span class="sxs-lookup"><span data-stu-id="cce32-375">In your browser, open the [Microsoft Azure portal](https://ms.portal.azure.com/), and go to **All Services** \> **Identity** \> **App Registrations**.</span></span>

2. <span data-ttu-id="cce32-376">Selezionare **nuova registrazione**e immettere un nome significativo.</span><span class="sxs-lookup"><span data-stu-id="cce32-376">Select **New registration**, and enter a meaningful name.</span></span>

3. <span data-ttu-id="cce32-377">Selezionare un tipo di account dalle opzioni visualizzate.</span><span class="sxs-lookup"><span data-stu-id="cce32-377">Select an account type from the options displayed.</span></span>

    <span data-ttu-id="cce32-378">Se si utilizza Microsoft Azure con un dominio non personalizzato, ad esempio **onmicrosoft.com**, selezionare solo gli **account nella directory dell'organizzazione (solo tenant di Microsoft).**</span><span class="sxs-lookup"><span data-stu-id="cce32-378">If you're using Microsoft Azure with a non-custom domain, such as **onmicrosoft.com**, select **Accounts in this organizational directory only (Microsoft only - Single tenant).**</span></span>

    <span data-ttu-id="cce32-379">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="cce32-379">For example:</span></span>

    :::image type="content" source="../media/dke-app-registration.png" alt-text="Nuova registrazione delle app":::

4. <span data-ttu-id="cce32-381">Nella parte inferiore della pagina, selezionare **registra** per creare la nuova registrazione app.</span><span class="sxs-lookup"><span data-stu-id="cce32-381">At the bottom of the page, select **Register** to create the new App Registration.</span></span>

5. <span data-ttu-id="cce32-382">Nella nuova registrazione dell'app, nel riquadro sinistro, in **Gestisci**selezionare **autenticazione**.</span><span class="sxs-lookup"><span data-stu-id="cce32-382">In your new App Registration, in the left pane, under **Manage**, select **Authentication**.</span></span>

6. <span data-ttu-id="cce32-383">Selezionare **Aggiungi una piattaforma**.</span><span class="sxs-lookup"><span data-stu-id="cce32-383">Select **Add a platform**.</span></span>
 
7. <span data-ttu-id="cce32-384">Nel menu Configura **popup SELECT** **Platforms** .</span><span class="sxs-lookup"><span data-stu-id="cce32-384">On the **Configure platforms** popup select **Web**.</span></span>
 
8. <span data-ttu-id="cce32-385">In **URI di reindirizzamento** immettere l'URI del servizio di crittografia a chiave doppia.</span><span class="sxs-lookup"><span data-stu-id="cce32-385">Under **Redirect URIs** enter the URI of your double key encryption service.</span></span> <span data-ttu-id="cce32-386">Immettere l'URL del servizio app, inclusi il nome host e il dominio.</span><span class="sxs-lookup"><span data-stu-id="cce32-386">Enter the App Service URL, including both the hostname and domain.</span></span>

    <span data-ttu-id="cce32-387">Ad esempio: https://mycustomerkeystoretest.com</span><span class="sxs-lookup"><span data-stu-id="cce32-387">For example: https://mycustomerkeystoretest.com</span></span>

    - <span data-ttu-id="cce32-388">L'URL immesso deve corrispondere al nome host in cui è distribuito l'archivio delle chiavi.</span><span class="sxs-lookup"><span data-stu-id="cce32-388">The URL you enter must match the hostname where your key store is deployed.</span></span>
    - <span data-ttu-id="cce32-389">Se si sta verificando localmente con Visual Studio, utilizzare **https://localhost:5001** .</span><span class="sxs-lookup"><span data-stu-id="cce32-389">If you're testing locally with Visual Studio, use **https://localhost:5001**.</span></span>
    - <span data-ttu-id="cce32-390">In tutti i casi, lo schema deve essere **https**.</span><span class="sxs-lookup"><span data-stu-id="cce32-390">In all cases, the scheme must be **https**.</span></span>

    <span data-ttu-id="cce32-391">Verificare che il nome dell'host corrisponda esattamente al cognome del servizio app.</span><span class="sxs-lookup"><span data-stu-id="cce32-391">Ensure the hostname exactly matches your App Service host name.</span></span> <span data-ttu-id="cce32-392">Potrebbe essere stata modificata in localhost per risolvere i problemi relativi alla generazione.</span><span class="sxs-lookup"><span data-stu-id="cce32-392">You may have changed it to localhost to troubleshoot the build.</span></span> <span data-ttu-id="cce32-393">In appsettings.js, si tratta del nome host identificato come valore per l'impostazione JwtAudience.</span><span class="sxs-lookup"><span data-stu-id="cce32-393">In appsettings.json, this is the hostname you identified as the value for the JwtAudience setting.</span></span>

6. <span data-ttu-id="cce32-394">In **concessione implicita**selezionare la casella di controllo **token ID** .</span><span class="sxs-lookup"><span data-stu-id="cce32-394">Under **Implicit grant**, select the **ID tokens** checkbox.</span></span>

1. <span data-ttu-id="cce32-395">Selezionare **Salva** per salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="cce32-395">Select **Save** to save your changes.</span></span>

7. <span data-ttu-id="cce32-396">Nel riquadro sinistro, selezionare **esporre un'API**, quindi accanto a URI ID applicazione selezionare **imposta**.</span><span class="sxs-lookup"><span data-stu-id="cce32-396">On the left pane, select **Expose an API**, then next to Application ID URI, select **Set**.</span></span>

9. <span data-ttu-id="cce32-397">Sempre nella pagina **esporre un'API** , nell' **ambito definito dall'area API** Selezionare **Aggiungi un ambito**.</span><span class="sxs-lookup"><span data-stu-id="cce32-397">Still on the **Expose an API** page, in the **Scopes defined by this API** area, select **Add a scope**.</span></span> <span data-ttu-id="cce32-398">Nel nuovo ambito:</span><span class="sxs-lookup"><span data-stu-id="cce32-398">In the new scope:</span></span>

    1. <span data-ttu-id="cce32-399">Definire il nome dell'ambito come **user_impersonation**.</span><span class="sxs-lookup"><span data-stu-id="cce32-399">Define the scope name as **user_impersonation**.</span></span>

    2. <span data-ttu-id="cce32-400">Selezionare gli amministratori e gli utenti che possono acconsentire.</span><span class="sxs-lookup"><span data-stu-id="cce32-400">Select the administrators and users who can consent.</span></span>

    3. <span data-ttu-id="cce32-401">Definire i valori rimanenti richiesti.</span><span class="sxs-lookup"><span data-stu-id="cce32-401">Define any remaining values required.</span></span>

    4. <span data-ttu-id="cce32-402">Selezionare **Aggiungi ambito.**</span><span class="sxs-lookup"><span data-stu-id="cce32-402">Select **Add scope.**</span></span>

    <span data-ttu-id="cce32-403">Selezionare **Salva** nella parte superiore per salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="cce32-403">Select **Save** at the top to save your changes.</span></span>

10. <span data-ttu-id="cce32-404">Sempre nella pagina **esporre un'API** , nell'area **applicazioni client autorizzate** Selezionare **Aggiungi un'applicazione client**.</span><span class="sxs-lookup"><span data-stu-id="cce32-404">Still on the **Expose an API** page, in the **Authorized client applications** area, select **Add a client application**.</span></span>

    <span data-ttu-id="cce32-405">Nella nuova applicazione client:</span><span class="sxs-lookup"><span data-stu-id="cce32-405">In the new client application:</span></span>

    1. <span data-ttu-id="cce32-406">Definire l'ID client come **d3590ed6-52B3-4102-Aeff-aad2292ab01c**.</span><span class="sxs-lookup"><span data-stu-id="cce32-406">Define the Client ID as **d3590ed6-52b3-4102-aeff-aad2292ab01c**.</span></span> <span data-ttu-id="cce32-407">Questo valore è l'ID client di Microsoft Office e consente a Office di ottenere un token di accesso per l'archivio delle chiavi.</span><span class="sxs-lookup"><span data-stu-id="cce32-407">This value is the Microsoft Office client ID, and enables Office to obtain an access token for your key store.</span></span>

    2. <span data-ttu-id="cce32-408">In **ambiti autorizzati**selezionare l'ambito **user_impersonation** .</span><span class="sxs-lookup"><span data-stu-id="cce32-408">Under **Authorized scopes**, select the **user_impersonation** scope.</span></span>

    3. <span data-ttu-id="cce32-409">Selezionare **Aggiungi applicazione**.</span><span class="sxs-lookup"><span data-stu-id="cce32-409">Select **Add application**.</span></span>

    4. <span data-ttu-id="cce32-410">Selezionare **Salva** nella parte superiore per salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="cce32-410">Select **Save** at the top to save your changes.</span></span>

<span data-ttu-id="cce32-411">L'archivio delle chiavi di DKE è ora registrato.</span><span class="sxs-lookup"><span data-stu-id="cce32-411">Your DKE key store is now registered.</span></span> <span data-ttu-id="cce32-412">Continuare con la [creazione di etichette mediante DKE](#create-labels-using-dke).</span><span class="sxs-lookup"><span data-stu-id="cce32-412">Continue  by [creating labels using DKE](#create-labels-using-dke).</span></span>

## <a name="create-labels-using-dke"></a><span data-ttu-id="cce32-413">Creare etichette utilizzando DKE</span><span class="sxs-lookup"><span data-stu-id="cce32-413">Create labels using DKE</span></span>

<span data-ttu-id="cce32-414">Dopo aver registrato l'archivio delle chiavi, configurare le etichette di sensibilità nel centro conformità di Microsoft 365 e applicare la crittografia a chiave doppia a tali etichette.</span><span class="sxs-lookup"><span data-stu-id="cce32-414">Once you've registered your key store, set up sensitivity labels in the Microsoft 365 compliance center and apply double key encryption to those labels.</span></span>

<span data-ttu-id="cce32-415">Nell'interfaccia utente per la creazione dell'etichetta selezionare l'opzione **Usa crittografia doppia chiave** e immettere l'URL dell'endpoint per la chiave.</span><span class="sxs-lookup"><span data-stu-id="cce32-415">In the label creation UI, select the **Use Double Key Encryption** option and enter the endpoint URL for your key.</span></span>

<span data-ttu-id="cce32-416">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="cce32-416">For example:</span></span>

:::image type="content" source="../media/dke-use-dke.png" alt-text="Selezionare Use Double Key Encryption in the Microsoft 365 Compliance Center":::

<span data-ttu-id="cce32-418">Tutte le etichette di DKE aggiunte verranno visualizzate per gli utenti nelle versioni più recenti di Microsoft 365 Apps for Enterprise.</span><span class="sxs-lookup"><span data-stu-id="cce32-418">Any DKE labels you add will start appearing for users in the latest versions of Microsoft 365 Apps for enterprise.</span></span>

> [!NOTE]
> <span data-ttu-id="cce32-419">La possibilità di aggiornare i client con le nuove etichette potrebbe richiedere fino a 24 ore.</span><span class="sxs-lookup"><span data-stu-id="cce32-419">It may take up to 24 hours for the clients to refresh with the new labels.</span></span>

### <a name="enable-dke-in-your-client"></a><span data-ttu-id="cce32-420">Abilitare DKE nel client</span><span class="sxs-lookup"><span data-stu-id="cce32-420">Enable DKE in your client</span></span>

<span data-ttu-id="cce32-421">Se le etichette di DKE non vengono visualizzate sotto la barra multifunzione di sensitivity in Microsoft Office, il client potrebbe non essere abilitato a DKE.</span><span class="sxs-lookup"><span data-stu-id="cce32-421">If your DKE labels don't appear under the Sensitivity ribbon in Microsoft Office, your client may not have DKE enabled.</span></span>

<span data-ttu-id="cce32-422">Abilitare DKE per il client aggiungendo le seguenti chiavi del registro di sistema:</span><span class="sxs-lookup"><span data-stu-id="cce32-422">Enable DKE for your client by adding the following registry keys:</span></span>

```ini
    [HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIPC\flighting]
    "DoubleKeyProtection"=dword:00000001

    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\flighting]
    "DoubleKeyProtection"=dword:00000001
```
