---
title: App in Microsoft Managed Desktop
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, servizio, documentazione
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: bc7192cf82c825a13780567663695d96a760b3ef
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/30/2020
ms.locfileid: "46530104"
---
# <a name="apps-in-microsoft-managed-desktop"></a><span data-ttu-id="21cd4-103">App in Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="21cd4-103">Apps in Microsoft Managed Desktop</span></span>

<!--This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.-->

<!--Applications: supported/onboard/deployment -->
 
## <a name="apps-generally"></a><span data-ttu-id="21cd4-104">App in generale</span><span class="sxs-lookup"><span data-stu-id="21cd4-104">Apps generally</span></span>

<span data-ttu-id="21cd4-105">Microsoft include alcune app principali insieme alla licenza Microsoft 365 E3 o E5 necessaria per partecipare a Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="21cd4-105">Microsoft includes certain key apps along with the Microsoft 365 E3 or E5 license needed to participate in Microsoft Managed Desktop.</span></span> <span data-ttu-id="21cd4-106">Tuttavia, anche se vengono fornite queste app, sono ancora presenti determinate responsabilità e azioni da completare.</span><span class="sxs-lookup"><span data-stu-id="21cd4-106">However, even though we provide these apps, you still have certain responsibilities and actions to complete.</span></span>

<span data-ttu-id="21cd4-107">È inoltre possibile distribuire altre app non Microsoft agli utenti finali per il servizio self-service tramite il portale aziendale o un'installazione in background necessaria, tutti utilizzando la pipeline di distribuzione di Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="21cd4-107">You can also deploy additional non-Microsoft apps to your end users for self-service through the Company Portal or a required background installation, all using Microsoft Intune’s deployment pipeline.</span></span> <span data-ttu-id="21cd4-108">In caso di esperienza, è possibile eseguire la migrazione delle applicazioni necessarie. in alternativa, i Microsoft Consulting Services (MCS) o i fornitori non Microsoft saranno lieti di aiutarvi con un progetto di migrazione e di creazione di pacchetti.</span><span class="sxs-lookup"><span data-stu-id="21cd4-108">If you have the expertise, you can migrate those apps you need yourself; alternatively, Microsoft Consulting Services (MCS) or non-Microsoft vendors will be happy to help you with a packaging and migration project.</span></span> <span data-ttu-id="21cd4-109">Per ulteriori informazioni sull'utilizzo di MCS, vedere [Working with Microsoft Consulting Services](apps-MCS.md).</span><span class="sxs-lookup"><span data-stu-id="21cd4-109">For more information about working with MCS, see [Working with Microsoft Consulting Services](apps-MCS.md).</span></span>


## <a name="apps-provided-by-microsoft"></a><span data-ttu-id="21cd4-110">App fornite da Microsoft</span><span class="sxs-lookup"><span data-stu-id="21cd4-110">Apps provided by Microsoft</span></span>

<span data-ttu-id="21cd4-111">In dotazione con la licenza Microsoft Managed Desktop sono disponibili versioni a 64 bit delle app di Microsoft 365 Apps for Enterprise Standard Suite (Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype for business e OneNote). Le versioni a portata di clic di Microsoft Project e Visio *non* sono incluse per impostazione predefinita, ma è possibile richiederne l'aggiunta.</span><span class="sxs-lookup"><span data-stu-id="21cd4-111">Included with your Microsoft Managed Desktop license are 64-bit versions of the apps in the Microsoft 365 Apps for enterprise Standard Suite (Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype for Business, and OneNote.) Click-to-Run versions of Microsoft Project and Visio are *not* included by default, but you can request them to be added.</span></span> <span data-ttu-id="21cd4-112">Per ulteriori informazioni su queste app, vedere [Install Microsoft Project o Microsoft Visio su Microsoft Managed Desktop Devices](../get-started/project-visio.md).</span><span class="sxs-lookup"><span data-stu-id="21cd4-112">For more information about these apps, see [Install Microsoft Project or Microsoft Visio on Microsoft Managed Desktop devices](../get-started/project-visio.md).</span></span>

### <a name="what-microsoft-does-to-support-the-apps-we-provide"></a><span data-ttu-id="21cd4-113">Cosa fa Microsoft per supportare le app che forniamo</span><span class="sxs-lookup"><span data-stu-id="21cd4-113">What Microsoft does to support the apps we provide</span></span>

<span data-ttu-id="21cd4-114">Microsoft fornirà il servizio completo per la distribuzione, l'aggiornamento e il supporto per le app di Microsoft 365 incluse per Enterprise Apps.</span><span class="sxs-lookup"><span data-stu-id="21cd4-114">Microsoft will provide full service for the deployment, update, and support for the included Microsoft 365 Apps for enterprise apps.</span></span> <span data-ttu-id="21cd4-115">Le versioni a portata di clic di Microsoft Project e Visio *non* sono incluse per impostazione predefinita, ma Microsoft Managed Desktop fornirà ai gruppi di distribuzione che consentono all'amministratore IT di gestire le licenze e distribuirle in modo appropriato per la propria organizzazione.</span><span class="sxs-lookup"><span data-stu-id="21cd4-115">Click-to-Run versions of Microsoft Project and Visio are *not* included by default, but Microsoft Managed Desktop will provide deployment groups allowing your IT administrator to manage licenses and deploy these applications appropriately for your organization.</span></span> <span data-ttu-id="21cd4-116">Microsoft sosterrà gli utenti finali di queste applicazioni tramite i canali di supporto di Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="21cd4-116">Microsoft will support end users of these applications through the Microsoft Managed Desktop support channels.</span></span>

### <a name="what-you-need-to-do-to-support-the-apps-we-provide"></a><span data-ttu-id="21cd4-117">Cosa devi fare per supportare le app che fornisci</span><span class="sxs-lookup"><span data-stu-id="21cd4-117">What you need to do to support the apps we provide</span></span>

<span data-ttu-id="21cd4-118">Sono ancora necessarie alcune operazioni da eseguire con queste app:</span><span class="sxs-lookup"><span data-stu-id="21cd4-118">There are still certain things you need to do with these apps:</span></span>

- <span data-ttu-id="21cd4-119">**Assegnare le licenze** : si è responsabili dell'ottenimento e dell'assegnazione delle licenze appropriate agli utenti finali per le app Microsoft 365 per Enterprise.</span><span class="sxs-lookup"><span data-stu-id="21cd4-119">**Assign licenses** - You are responsible for obtaining and assigning the appropriate licenses to end users for Microsoft 365 Apps for enterprise.</span></span>
- <span data-ttu-id="21cd4-120">**Aggiungere utenti ai gruppi di sicurezza** : se si utilizza Microsoft Project o Visio, l'amministratore IT deve aggiungere tali utenti ai gruppi di distribuzione corretti.</span><span class="sxs-lookup"><span data-stu-id="21cd4-120">**Add users to security groups** - If you're using Microsoft Project or Visio, your IT administrator must add those users to the appropriate deployment groups.</span></span> <span data-ttu-id="21cd4-121">Gli amministratori IT sono anche responsabili del recupero delle licenze da tali utenti se lasciano la società.</span><span class="sxs-lookup"><span data-stu-id="21cd4-121">IT administrators are also responsible for reclaiming licenses from those users if they leave the company.</span></span>
- <span data-ttu-id="21cd4-122">**Distribuire i componenti aggiuntivi di microsoft 365** -se sono necessari componenti aggiuntivi per qualsiasi app di Microsoft 365 per le applicazioni Enterprise, distribuire le app in modo centralizzato come qualsiasi altra applicazione Windows 32.</span><span class="sxs-lookup"><span data-stu-id="21cd4-122">**Deploy Microsoft 365 Add-ons** - If you need any Add-ons for any of the Microsoft 365 Apps for enterprise apps, deploy them centrally like any other Windows 32 app.</span></span> 

## <a name="apps-you-provide"></a><span data-ttu-id="21cd4-123">App fornite</span><span class="sxs-lookup"><span data-stu-id="21cd4-123">Apps you provide</span></span>

<span data-ttu-id="21cd4-124">Naturalmente, è probabile che si disponga di una serie di altre app necessarie per le operazioni aziendali.</span><span class="sxs-lookup"><span data-stu-id="21cd4-124">Of course, you probably have a number of other apps you need for your business operations.</span></span> <span data-ttu-id="21cd4-125">Questi possono essere distribuiti solo ai dispositivi Microsoft Managed Desktop mediante la pipeline di distribuzione di Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="21cd4-125">These can only be deployed to Microsoft Managed Desktop devices by using Microsoft Intune’s deployment pipeline.</span></span> <span data-ttu-id="21cd4-126">Se l'applicazione ne ha bisogno, è possibile farli impacchettare da un fornitore (che potrebbe essere un fornitore non Microsoft o Microsoft Consulting Services (MCS)) oppure se si dispone dei mezzi necessari, è possibile imballarli personalmente.</span><span class="sxs-lookup"><span data-stu-id="21cd4-126">If the app needs it you can have them packaged by a vendor (which could be a non-Microsoft vendor or Microsoft Consulting Services (MCS)) or if you have the means, you can package them yourself.</span></span> <span data-ttu-id="21cd4-127">Successivamente, aggiungere questi pacchetti al portale Microsoft Managed Desktop e assegnarli ai gruppi di Azure Active Directory per attivare la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="21cd4-127">You then add these packages to the Microsoft Managed Desktop portal and assign them to Azure Active Directory groups to trigger the deployment.</span></span> 

<span data-ttu-id="21cd4-128">Se le app vengono attualmente distribuite tramite Microsoft endpoint Configuration Manager, Microsoft Managed Desktop può fornire una query per valutare le app e individuare quelle pronte per la migrazione a Microsoft Intune e quali potrebbero essere necessarie per la rettifica.</span><span class="sxs-lookup"><span data-stu-id="21cd4-128">If you currently deploy your apps by using Microsoft Endpoint Configuration Manager, Microsoft Managed Desktop can provide you with a query to assess your apps and discover which ones are ready for to migrate to Microsoft Intune and which ones might require some adjustment.</span></span>


### <a name="preparing-your-own-apps-for-inclusion-in-microsoft-managed-desktop"></a><span data-ttu-id="21cd4-129">Preparare le proprie app per l'inclusione in Microsoft Managed Desktop</span><span class="sxs-lookup"><span data-stu-id="21cd4-129">Preparing your own apps for inclusion in Microsoft Managed Desktop</span></span>
<span data-ttu-id="21cd4-130">Esaminare le app, verificando:</span><span class="sxs-lookup"><span data-stu-id="21cd4-130">Review your apps, checking:</span></span>

- <span data-ttu-id="21cd4-131">Nessuna delle app è vietata o ha un comportamento limitato, come descritto in [Microsoft Managed Desktop App requirements](https://aka.ms/app-req).</span><span class="sxs-lookup"><span data-stu-id="21cd4-131">None of the apps are prohibited or have restricted behavior, as described in [Microsoft Managed Desktop app requirements](https://aka.ms/app-req).</span></span>
- <span data-ttu-id="21cd4-132">Le app devono essere pronte per la gestione da Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="21cd4-132">Apps must be ready for management by Microsoft Intune.</span></span> <span data-ttu-id="21cd4-133">Per ulteriori informazioni, vedere [distribuzione di app di Windows 10 con Microsoft Intune](https://docs.microsoft.com/intune/apps-windows-10-app-deploy) e [aggiungere app a Microsoft Intune](https://docs.microsoft.com/intune/apps-add).</span><span class="sxs-lookup"><span data-stu-id="21cd4-133">For more about this, see [Windows 10 app deployment using Microsoft Intune](https://docs.microsoft.com/intune/apps-windows-10-app-deploy) and [Add apps to Microsoft Intune](https://docs.microsoft.com/intune/apps-add).</span></span>
- <span data-ttu-id="21cd4-134">Altri requisiti di preconfezionamento, ad esempio la fornitura di codici di licenza, il contratto con le condizioni di licenza e la preimpostazione delle connessioni server.</span><span class="sxs-lookup"><span data-stu-id="21cd4-134">Other pre-packaging requirements such as providing license keys, agreement with license terms, and pre-setting server connections.</span></span>

### <a name="decide-how-to-package-apps"></a><span data-ttu-id="21cd4-135">Decidere come eseguire il pacchetto di app</span><span class="sxs-lookup"><span data-stu-id="21cd4-135">Decide how to package apps</span></span>

<span data-ttu-id="21cd4-136">Alcuni fornitori di software indipendenti potrebbero richiedere che le app siano inserite in un pacchetto prima di essere distribuite in modo centralizzato.</span><span class="sxs-lookup"><span data-stu-id="21cd4-136">Some independent software vendors might require that your apps are packaged before they are centrally deployed.</span></span> <span data-ttu-id="21cd4-137">"Packaging" indica che il programma di installazione dell'app è configurato con impostazioni come le chiavi di licenza, le posizioni dei server remoti o i collegamenti desktop in modo che sia possibile installare l'app in background.</span><span class="sxs-lookup"><span data-stu-id="21cd4-137">“Packaging” means that the app’s installer is configured with settings like license keys, remote server locations, or desktop shortcuts so that the app can be installed in the background.</span></span>

<span data-ttu-id="21cd4-138">Sono disponibili tre opzioni per ottenere i pacchetti delle app:</span><span class="sxs-lookup"><span data-stu-id="21cd4-138">There are three options to get your apps packaged:</span></span> 


- <span data-ttu-id="21cd4-139">È possibile creare pacchetti per le app</span><span class="sxs-lookup"><span data-stu-id="21cd4-139">You can package apps yourself</span></span>
- <span data-ttu-id="21cd4-140">È possibile collaborare con un fornitore non Microsoft</span><span class="sxs-lookup"><span data-stu-id="21cd4-140">You can work with a non-Microsoft vendor</span></span>
- <span data-ttu-id="21cd4-141">È possibile coinvolgere MCS per il pacchetto delle app.</span><span class="sxs-lookup"><span data-stu-id="21cd4-141">You can engage with MCS to package your apps.</span></span> <span data-ttu-id="21cd4-142">Collaborare con il proprio rappresentante dell'account Microsoft.</span><span class="sxs-lookup"><span data-stu-id="21cd4-142">Work with your Microsoft account representative.</span></span> <span data-ttu-id="21cd4-143">Per ulteriori informazioni, vedere [Working with Microsoft Consulting Services](apps-MCS.md).</span><span class="sxs-lookup"><span data-stu-id="21cd4-143">For more details, see [Working with Microsoft Consulting Services](apps-MCS.md).</span></span>







## <a name="deploying-apps"></a><span data-ttu-id="21cd4-144">Distribuzione di app</span><span class="sxs-lookup"><span data-stu-id="21cd4-144">Deploying apps</span></span>

<span data-ttu-id="21cd4-145">Indipendentemente dal metodo utilizzato per ottenere le app inserite, una volta completata, si è pronti a seguire la procedura descritta in [deploy Apps to Microsoft Managed Desktop Devices](../get-started/deploy-apps.md).</span><span class="sxs-lookup"><span data-stu-id="21cd4-145">Whatever method you use to get apps packaged, once that is complete, you're ready to follow the steps in [Deploy apps to Microsoft Managed Desktop devices](../get-started/deploy-apps.md).</span></span>


