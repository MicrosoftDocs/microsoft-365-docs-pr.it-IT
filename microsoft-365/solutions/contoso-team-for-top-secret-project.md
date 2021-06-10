---
title: Team isolato per un progetto top-secret di Contoso Corporation
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: dansimp
ms.date: 08/14/2020
audience: ITPro
ms.topic: overview
ms.prod: microsoft-365-enterprise
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom: Ent_Architecture
description: 'Riepilogo: in che modo Contoso ha usato un team con isolamento della sicurezza per un progetto top-secret per sviluppare una nuova famiglia di prodotti e servizi.'
ms.openlocfilehash: 751bf3972d148219a6cc341067c0bf34cd581447
ms.sourcegitcommit: e02cf5702af178ddd2968877a808874ecb49ed2c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/26/2021
ms.locfileid: "52029017"
---
# <a name="isolated-team-for-a-top-secret-project-of-the-contoso-corporation"></a><span data-ttu-id="64967-103">Team isolato per un progetto top-secret di Contoso Corporation</span><span class="sxs-lookup"><span data-stu-id="64967-103">Isolated team for a top-secret project of the Contoso Corporation</span></span>

<span data-ttu-id="64967-104">Dopo un executive offsite, il CEO di Contoso ha ordinato lo sviluppo di una nuova famiglia di prodotti e servizi che potrebbe raddoppiare i profitti di Contoso nei prossimi cinque anni.</span><span class="sxs-lookup"><span data-stu-id="64967-104">After an executive offsite, Contoso’s CEO ordered the development of a new suite of products and services that could double Contoso’s profits in the next five years.</span></span> <span data-ttu-id="64967-105">Il progetto top-secret per sviluppare il piano aziendale, ingegneristico e di mercato è stato denominato **Project 2X** e sono stati assunti personale chiave in tutta l'azienda.</span><span class="sxs-lookup"><span data-stu-id="64967-105">The top-secret project to develop the business, engineering, and market plan was named **Project 2X** and key staff across the company were recruited.</span></span> 

<span data-ttu-id="64967-106">Le tempistiche per la ricerca e lo sviluppo erano rigide, il che significava che la collaborazione doveva essere efficiente e garantire riunioni sicure, conversazioni in corso e archiviazione di file.</span><span class="sxs-lookup"><span data-stu-id="64967-106">The timelines for research and development were tight, which meant that collaboration had to be efficient and provide for secure meetings, ongoing conversations, and file storage.</span></span>

<span data-ttu-id="64967-107">I risultati finali risultanti per Project 2X sono i piani aziendali, le specifiche di prodotto e di progettazione, i materiali e le pianificazioni di marketing sotto forma di file di word, Excel e PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="64967-107">The resulting deliverables for Project 2X were business plans, product and engineering specifications, and marketing materials and schedules in the form of Word, Excel, and PowerPoint files.</span></span> 

<span data-ttu-id="64967-108">A causa della loro natura sensibile, l'accesso a questi file è stato:</span><span class="sxs-lookup"><span data-stu-id="64967-108">Due to their sensitive nature, access to these files were:</span></span>

- <span data-ttu-id="64967-109">Limitato a Project membri del team 2X e ai dirigenti senior.</span><span class="sxs-lookup"><span data-stu-id="64967-109">Restricted to Project 2X team members and senior leadership.</span></span>
- <span data-ttu-id="64967-110">Crittografato e protetto con autorizzazioni per consentire l'accesso solo Project membri del team 2X e dirigenti senior, anche se i file sono stati distribuiti all'esterno delle cartelle protette.</span><span class="sxs-lookup"><span data-stu-id="64967-110">Encrypted and protected with permissions to allow access only to Project 2X team members and senior leadership, even if the files were distributed outside of their secured folders.</span></span>

<span data-ttu-id="64967-111">Il personale IT di Contoso ha utilizzato [un team](secure-teams-security-isolation.md) con isolamento della sicurezza Project 2X e questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="64967-111">Contoso IT staff used a [team with security isolation](secure-teams-security-isolation.md) for Project 2X and these steps.</span></span>

## <a name="step-1-created-a-private-team"></a><span data-ttu-id="64967-112">Passaggio 1: Creare un team privato</span><span class="sxs-lookup"><span data-stu-id="64967-112">Step 1: Created a private team</span></span>

<span data-ttu-id="64967-113">Innanzitutto, per proteggere l'accesso al sito SharePoint sottostante per il team, gli amministratori IT di Contoso hanno configurato i criteri di SharePoint [di accesso.](../security/office-365-security/sharepoint-file-access-policies.md)</span><span class="sxs-lookup"><span data-stu-id="64967-113">First, to protect access to the underlying SharePoint site for the team, Contoso IT administrators configured the [recommended SharePoint access policies](../security/office-365-security/sharepoint-file-access-policies.md).</span></span>

<span data-ttu-id="64967-114">Successivamente, un amministratore IT di Contoso ha creato un nuovo team privato denominato Project 2X e aggiunto gli account utente di Project 2X come membri.</span><span class="sxs-lookup"><span data-stu-id="64967-114">Next, a Contoso IT administrator created a new private team named Project 2X and added the user accounts of Project 2X staff as members.</span></span> <span data-ttu-id="64967-115">Hanno anche configurato il team in modo che solo Project proprietari del team 2X possano creare canali privati.</span><span class="sxs-lookup"><span data-stu-id="64967-115">They also configured the team so that only Project 2X team owners can create private channels.</span></span>

<span data-ttu-id="64967-116">Per informazioni dettagliate sulla configurazione, vedere [Create a private team](secure-teams-security-isolation.md#create-a-private-team).</span><span class="sxs-lookup"><span data-stu-id="64967-116">For the configuration details, see [Create a private team](secure-teams-security-isolation.md#create-a-private-team).</span></span>

## <a name="step-2-created-a-sensitivity-label-for-the-project-2x-team"></a><span data-ttu-id="64967-117">Passaggio 2: Creare un'etichetta di riservatezza per il team Project 2X</span><span class="sxs-lookup"><span data-stu-id="64967-117">Step 2: Created a sensitivity label for the Project 2X team</span></span>

<span data-ttu-id="64967-118">Gli amministratori di Contoso hanno creato una nuova etichetta di riservatezza denominata **Project 2X** che:</span><span class="sxs-lookup"><span data-stu-id="64967-118">Contoso admins created a new sensitivity label named **Project 2X** that:</span></span>

- <span data-ttu-id="64967-119">Crittografia abilitata.</span><span class="sxs-lookup"><span data-stu-id="64967-119">Enabled encryption.</span></span>
- <span data-ttu-id="64967-120">Autorizzazioni Co-Author per il gruppo Project 2X Microsoft 365 gruppo.</span><span class="sxs-lookup"><span data-stu-id="64967-120">Allowed Co-Author permissions for the Project 2X Microsoft 365 group.</span></span>
- <span data-ttu-id="64967-121">Autorizzazioni visualizzatore consentite per il gruppo Senior Leadership.</span><span class="sxs-lookup"><span data-stu-id="64967-121">Allowed Viewer permissions for the Senior Leadership group.</span></span>
- <span data-ttu-id="64967-122">Accesso bloccato ai dispositivi non gestiti.</span><span class="sxs-lookup"><span data-stu-id="64967-122">Blocked access to unmanaged devices.</span></span>

<span data-ttu-id="64967-123">I file nella **sezione Documents** del sito Project 2X SharePoint sono stati protetti da:</span><span class="sxs-lookup"><span data-stu-id="64967-123">Files in the **Documents** section of the underlying Project 2X SharePoint site were protected by:</span></span>

- <span data-ttu-id="64967-124">Autorizzazioni del sito, che consentono solo autorizzazioni complete per i membri del gruppo Project 2X Microsoft 365 e autorizzazioni di lettura per il gruppo Senior Leadership.</span><span class="sxs-lookup"><span data-stu-id="64967-124">The site permissions, which only allow full permissions to members of the Project 2X Microsoft 365 group and read permissions to the Senior Leadership group.</span></span>
- <span data-ttu-id="64967-125">L Project di riservatezza 2X, con crittografia e autorizzazioni che viaggiano con il file se viene spostato o copiato dal sito.</span><span class="sxs-lookup"><span data-stu-id="64967-125">The Project 2X sensitivity label, with encryption and permissions that travel with the file if it is moved or copied from the site.</span></span>

<span data-ttu-id="64967-126">Per i dettagli della configurazione, vedere [Create a sensitivity label](secure-teams-security-isolation.md#create-a-sensitivity-label).</span><span class="sxs-lookup"><span data-stu-id="64967-126">For the configuration details, see [Create a sensitivity label](secure-teams-security-isolation.md#create-a-sensitivity-label).</span></span>

## <a name="step-3-configured-the-underlying-sharepoint-site"></a><span data-ttu-id="64967-127">Passaggio 3: Configurare il sito SharePoint sottostante</span><span class="sxs-lookup"><span data-stu-id="64967-127">Step 3: Configured the underlying SharePoint site</span></span>

<span data-ttu-id="64967-128">Innanzitutto, per proteggere l'accesso al sito SharePoint sottostante per il team, gli amministratori IT di Contoso hanno configurato i criteri di SharePoint [di accesso.](../security/office-365-security/sharepoint-file-access-policies.md)</span><span class="sxs-lookup"><span data-stu-id="64967-128">First, to protect access to the underlying SharePoint site for the team, Contoso IT administrators configured the [recommended SharePoint access policies](../security/office-365-security/sharepoint-file-access-policies.md).</span></span>

<span data-ttu-id="64967-129">Successivamente, hanno configurato impostazioni di autorizzazione aggiuntive per il sito:</span><span class="sxs-lookup"><span data-stu-id="64967-129">Next, they configured additional permission settings for the site:</span></span>

- <span data-ttu-id="64967-130">Per impedire Project membri del gruppo 2X di condividere l'accesso al sito.</span><span class="sxs-lookup"><span data-stu-id="64967-130">To prevent Project 2X group members from sharing access to the site.</span></span> <span data-ttu-id="64967-131">Per i dettagli di configurazione, vedere [SharePoint per un team con isolamento della sicurezza.](secure-teams-security-isolation.md#sharepoint-settings)</span><span class="sxs-lookup"><span data-stu-id="64967-131">For the configuration details, see [SharePoint settings for a team with security isolation](secure-teams-security-isolation.md#sharepoint-settings).</span></span>
- <span data-ttu-id="64967-132">Per autorizzazioni di lettura per il gruppo Senior Leadership.</span><span class="sxs-lookup"><span data-stu-id="64967-132">For Read permissions for the Senior Leadership group.</span></span>

<span data-ttu-id="64967-133">Successivamente, hanno configurato impostazioni di autorizzazione aggiuntive per il sito per impedire Project membri del gruppo 2X di condividere l'accesso al sito.</span><span class="sxs-lookup"><span data-stu-id="64967-133">Next, they configured additional permission settings for the site to prevent Project 2X group members from sharing access to the site.</span></span> 

<span data-ttu-id="64967-134">Durante la creazione dei canali privati Project 2X, il proprietario del gruppo ha disabilitato la condivisione guest e ha impostato il collegamento di condivisione predefinito sul **valore Persone** specifiche.</span><span class="sxs-lookup"><span data-stu-id="64967-134">As private channels for the Project 2X were created, the group owner disabled guest sharing and set the default sharing link to the **Specific people** value.</span></span>

<span data-ttu-id="64967-135">Ecco la configurazione risultante del team Project 2X con isolamento della sicurezza.</span><span class="sxs-lookup"><span data-stu-id="64967-135">Here is the resulting configuration of the Project 2X team with security isolation.</span></span>

![La configurazione risultante del team Project 2X](../media/contoso-team-for-top-secret-project.png)

 ## <a name="step-4-trained-project-2x-team-members"></a><span data-ttu-id="64967-137">Passaggio 4: formazione Project membri del team 2X</span><span class="sxs-lookup"><span data-stu-id="64967-137">Step 4: Trained Project 2X team members</span></span>

<span data-ttu-id="64967-138">Il personale di sicurezza di Contoso ha formato Project membri del team 2X in un corso obbligatorio che li ha attraversati:</span><span class="sxs-lookup"><span data-stu-id="64967-138">Contoso security staff trained the Project 2X team members in a mandatory course that stepped them through:</span></span>

- <span data-ttu-id="64967-139">Come accedere al nuovo team Project 2X, usare riunioni e chat e come collaborare ai file del team.</span><span class="sxs-lookup"><span data-stu-id="64967-139">How to access the new Project 2X team, use meetings and chats, and how to collaborate on team files.</span></span>
- <span data-ttu-id="64967-140">Come creare nuovi file nel team e caricare nuovi file creati localmente.</span><span class="sxs-lookup"><span data-stu-id="64967-140">How to create new files in the team and upload new files created locally.</span></span>
- <span data-ttu-id="64967-141">Come etichettare i file con l Project di riservatezza 2X.</span><span class="sxs-lookup"><span data-stu-id="64967-141">How to label files with the Project 2X sensitivity label.</span></span>
- <span data-ttu-id="64967-142">Dimostrazione di come l Project etichetta 2X protegge un file anche quando lascia il team.</span><span class="sxs-lookup"><span data-stu-id="64967-142">A demonstration of how the Project 2X  label protects a file even when it leaves the team.</span></span>

<span data-ttu-id="64967-143">Il risultato finale è stato un ambiente sicuro in cui Project membri del team 2X hanno collaborato in un ambiente sicuro per chat, riunioni e file.</span><span class="sxs-lookup"><span data-stu-id="64967-143">The end result was a secure environment in which Project 2X team members collaborated in a secure environment for chats, meetings, and files.</span></span>

<span data-ttu-id="64967-144">Ecco un esempio di un file archiviato nel sito Project 2X sottostante con l'etichetta di riservatezza Project 2X assegnata.</span><span class="sxs-lookup"><span data-stu-id="64967-144">Here is an example of a file stored in the underlying Project 2X site with the Project 2X sensitivity label assigned.</span></span>

![Esempio di file archiviato nel sito Project 2X sottostante](../media/contoso-team-for-top-secret-project-example.png)

<span data-ttu-id="64967-146">In un paio di casi, Project membri del team 2X hanno scaricato file protetti dall'etichetta Project 2X in un'unità locale per il lavoro offline.</span><span class="sxs-lookup"><span data-stu-id="64967-146">In a couple of instances, Project 2X team members downloaded files protected by the Project 2X label to a local drive for offline work.</span></span> 

<span data-ttu-id="64967-147">Tuttavia, dopo aver richiesto le credenziali all'apertura, si sono resi conto dell'errore e le hanno eliminate.</span><span class="sxs-lookup"><span data-stu-id="64967-147">However, after being prompted for credentials when opening them, they realized their mistake and deleted them.</span></span>

<span data-ttu-id="64967-148">A causa dell'ambiente di collaborazione di Teams e delle funzionalità di sicurezza di Microsoft 365, i dettagli di Project 2X sono stati mantenuti segreti per tutta la durata del progetto.</span><span class="sxs-lookup"><span data-stu-id="64967-148">Because of the collaboration environment of Teams and the security features of Microsoft 365, the details of Project 2X were kept secret for the duration of the project.</span></span> <span data-ttu-id="64967-149">Contoso ha annunciato i propri piani ed è in corso l'implementazione dei nuovi prodotti e servizi per la soddisfazione dei clienti e degli investitori e il disappunto dei concorrenti.</span><span class="sxs-lookup"><span data-stu-id="64967-149">Contoso announced its plans and is in the process of rolling out the new products and services to the delight of its customers and investors and the chagrin of its competitors.</span></span>

## <a name="next-step"></a><span data-ttu-id="64967-150">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="64967-150">Next step</span></span>

<span data-ttu-id="64967-151">[Distribuire un team con isolamento della sicurezza](secure-teams-security-isolation.md) nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="64967-151">[Deploy a team with security isolation](secure-teams-security-isolation.md) in your organization.</span></span>

