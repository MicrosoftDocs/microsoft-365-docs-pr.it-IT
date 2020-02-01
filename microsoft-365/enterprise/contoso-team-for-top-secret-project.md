---
title: Team per un progetto interno di Contoso Corporation
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/18/2019
audience: ITPro
ms.topic: overview
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: Ent_Architecture
description: 'Riepilogo: in che modo Contoso ha utilizzato un team per i dati altamente regolamentati per un progetto Top-Secret per sviluppare una nuova famiglia di prodotti e servizi.'
ms.openlocfilehash: 794fb5cfb6f3011724d37a6a3c42c39dacacc270
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "41597073"
---
# <a name="team-for-a-top-secret-project-of-the-contoso-corporation"></a><span data-ttu-id="449a6-103">Team per un progetto interno di Contoso Corporation</span><span class="sxs-lookup"><span data-stu-id="449a6-103">Team for a top-secret project of the Contoso Corporation</span></span>

<span data-ttu-id="449a6-104">Dopo un Executive fuori sede, il CEO di Contoso ha ordinato lo sviluppo di una nuova famiglia di prodotti e servizi che potrebbe raddoppiare gli utili di Contoso nei prossimi cinque anni.</span><span class="sxs-lookup"><span data-stu-id="449a6-104">After an executive offsite, Contoso’s CEO ordered the development of a new suite of products and services that could double Contoso’s profits in the next five years.</span></span> <span data-ttu-id="449a6-105">Il progetto Top-Secret per sviluppare il piano aziendale, ingegneristico e di mercato è stato denominato **Project 2x** e il personale chiave in tutta la società sono stati reclutati.</span><span class="sxs-lookup"><span data-stu-id="449a6-105">The top-secret project to develop the business, engineering, and market plan was named **Project 2X** and key staff across the company were recruited.</span></span> 

<span data-ttu-id="449a6-106">Le sequenze temporali per la ricerca e lo sviluppo sono state rigorose, il che significa che la collaborazione deve essere efficiente e fornire riunioni sicure, conversazioni e archiviazione dei file.</span><span class="sxs-lookup"><span data-stu-id="449a6-106">The timelines for research and development were tight, which meant that collaboration had to be efficient and provide for secure meetings, ongoing conversations, and file storage.</span></span>

<span data-ttu-id="449a6-107">I risultati finali risultanti per Project 2X sono stati piani aziendali, specifiche di prodotti e di ingegneria e materiali di marketing e pianificazioni in formato Word, Excel e PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="449a6-107">The resulting deliverables for Project 2X were business plans, product and engineering specifications, and marketing materials and schedules in the form of Word, Excel, and PowerPoint files.</span></span> 

<span data-ttu-id="449a6-108">A causa della loro natura sensibile, l'accesso a questi file è stato:</span><span class="sxs-lookup"><span data-stu-id="449a6-108">Due to their sensitive nature, access to these files were:</span></span>

- <span data-ttu-id="449a6-109">Limitato ai membri del team di Project 2X.</span><span class="sxs-lookup"><span data-stu-id="449a6-109">Restricted to Project 2X team members.</span></span>
- <span data-ttu-id="449a6-110">Protetto con un criterio di prevenzione della perdita di dati (DLP) per impedire ai membri del team di Project 2X di condividerli all'esterno del team.</span><span class="sxs-lookup"><span data-stu-id="449a6-110">Protected with a Data Loss Prevention (DLP) policy to prevent Project 2X team members from sharing them outside the team.</span></span>
- <span data-ttu-id="449a6-111">Crittografati e protetti con le autorizzazioni per consentire l'accesso solo ai membri del team di Project 2X, anche se i file sono stati distribuiti all'esterno di contoso.</span><span class="sxs-lookup"><span data-stu-id="449a6-111">Encrypted and protected with permissions to allow access only to Project 2X team members, even if the files were distributed outside of Contoso.</span></span>

<span data-ttu-id="449a6-112">Il personale IT di Contoso ha utilizzato un [team per i dati altamente regolamentati](secure-teams-highly-regulated-data-scenario.md) per Project 2x e questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="449a6-112">Contoso IT staff used a [team for highly-regulated data](secure-teams-highly-regulated-data-scenario.md) for Project 2X and these steps.</span></span>

## <a name="step-1-created-a-private-team-and-locked-down-the-underlying-sharepoint-site"></a><span data-ttu-id="449a6-113">Passaggio 1: creazione di un team privato e blocco del sito di SharePoint sottostante</span><span class="sxs-lookup"><span data-stu-id="449a6-113">Step 1: Created a private team and locked down the underlying SharePoint site</span></span>

<span data-ttu-id="449a6-114">Per proteggere l'accesso al sito di SharePoint sottostante per il team, gli amministratori IT di Contoso hanno configurato i [criteri di accesso di SharePoint consigliati](sharepoint-file-access-policies.md).</span><span class="sxs-lookup"><span data-stu-id="449a6-114">To protect access to the underlying SharePoint site for the team, Contoso IT administrators configured the [recommended SharePoint access policies](sharepoint-file-access-policies.md).</span></span>

<span data-ttu-id="449a6-115">Successivamente, un amministratore IT di Contoso ha creato un nuovo team privato denominato Project 2X e aggiunto gli account utente del personale di Project 2X come membri.</span><span class="sxs-lookup"><span data-stu-id="449a6-115">Next, a Contoso IT administrator created a new private team named Project 2X and added the user accounts of Project 2X staff as members.</span></span>

<span data-ttu-id="449a6-116">Successivamente, sono state configurate le impostazioni di autorizzazione aggiuntive per il sito per impedire che Project 2X condivida l'accesso al sito e impedire ad altri utenti di richiedere l'accesso al sito.</span><span class="sxs-lookup"><span data-stu-id="449a6-116">Next, they configured additional permission settings for the site to prevent Project 2X from sharing access to the site and to prevent other from requesting access to the site.</span></span>

<span data-ttu-id="449a6-117">Per informazioni dettagliate sulla configurazione, vedere [impostazioni di SharePoint per un team fortemente regolato](https://docs.microsoft.com/microsoft-365/security/office-365-security/deploy-teams-three-tiers#highly-confidential-teams).</span><span class="sxs-lookup"><span data-stu-id="449a6-117">For the configuration details, see [SharePoint settings for a highly regulated team](https://docs.microsoft.com/microsoft-365/security/office-365-security/deploy-teams-three-tiers#highly-confidential-teams).</span></span>

## <a name="step-2-configured-a-dlp-policy-and-the-underlying-site-for-a-retention-label"></a><span data-ttu-id="449a6-118">Passaggio 2: configurazione di un criterio DLP e del sito sottostante per un'etichetta di conservazione</span><span class="sxs-lookup"><span data-stu-id="449a6-118">Step 2: Configured a DLP policy and the underlying site for a retention label</span></span> 

<span data-ttu-id="449a6-119">Per prima cosa, gli amministratori di Contoso hanno applicato l'etichetta di conservazione di Office 365 **molto riservata** esistente alla sezione **Documents** del sito di SharePoint sottostante del team di Project 2x.</span><span class="sxs-lookup"><span data-stu-id="449a6-119">First, Contoso admins applied the existing **Highly Confidential** Office 365 retention label to the **Documents** section of the underlying SharePoint site of the Project 2X team.</span></span>

<span data-ttu-id="449a6-120">Successivamente, è stato creato un nuovo criterio DLP di Office 365 denominato **Project 2x** che:</span><span class="sxs-lookup"><span data-stu-id="449a6-120">Next, they created a new Office 365 DLP policy named **Project 2X** that:</span></span>

- <span data-ttu-id="449a6-121">Utilizza l'etichetta di conservazione di Office 365 estremamente riservata.</span><span class="sxs-lookup"><span data-stu-id="449a6-121">Uses the Highly Confidential Office 365 retention label.</span></span>
- <span data-ttu-id="449a6-122">Blocca gli utenti quando tentano di condividere un file nel team di Project 2X all'esterno di contoso.</span><span class="sxs-lookup"><span data-stu-id="449a6-122">Blocks users when they attempt to share a file in the Project 2X team outside of Contoso.</span></span>

<span data-ttu-id="449a6-123">Per informazioni dettagliate sulla configurazione, vedere [Protect Files in teams with retention labels and DLP](https://docs.microsoft.com/microsoft-365/security/office-365-security/deploy-teams-retention-dlp).</span><span class="sxs-lookup"><span data-stu-id="449a6-123">For the configuration details, see [Protect files in teams with retention labels and DLP](https://docs.microsoft.com/microsoft-365/security/office-365-security/deploy-teams-retention-dlp).</span></span>

## <a name="step-3-created-an-office-365-sensitivity-label-for-the-project-2x-team"></a><span data-ttu-id="449a6-124">Passaggio 3: creazione di un'etichetta di riservatezza di Office 365 per il team di Project 2X</span><span class="sxs-lookup"><span data-stu-id="449a6-124">Step 3: Created an Office 365 sensitivity label for the Project 2X team</span></span>

<span data-ttu-id="449a6-125">Gli amministratori di Contoso hanno creato una nuova etichetta di riservatezza di Office 365 denominata **Project 2x** che:</span><span class="sxs-lookup"><span data-stu-id="449a6-125">Contoso admins created a new Office 365 sensitivity label named **Project 2X** that:</span></span>

- <span data-ttu-id="449a6-126">Richiede la crittografia.</span><span class="sxs-lookup"><span data-stu-id="449a6-126">Requires encryption.</span></span>
- <span data-ttu-id="449a6-127">Consente le autorizzazioni di creazione condivisa per il gruppo Project 2X Office 365.</span><span class="sxs-lookup"><span data-stu-id="449a6-127">Allows Co-Author permissions for the Project 2X Office 365 group.</span></span>

<span data-ttu-id="449a6-128">Ecco la configurazione risultante del team di Project 2X.</span><span class="sxs-lookup"><span data-stu-id="449a6-128">Here is the resulting configuration of the Project 2X team.</span></span>

![La configurazione risultante del team di Project 2X](./media/contoso-team-for-highly-confidential-assets/final-config.png)
 
<span data-ttu-id="449a6-130">I file nella sezione Documents del progetto sottostante 2X sito di SharePoint sono stati protetti da:</span><span class="sxs-lookup"><span data-stu-id="449a6-130">Files in the Documents section of the underlying Project 2X SharePoint site were protected by:</span></span>

- <span data-ttu-id="449a6-131">Le autorizzazioni per il sito, che consentono l'accesso solo ai membri del gruppo Project 2X Office 365.</span><span class="sxs-lookup"><span data-stu-id="449a6-131">The site permissions, which only allow access to members of the Project 2X Office 365 group.</span></span>
- <span data-ttu-id="449a6-132">L'etichetta di conservazione estremamente riservata, che viene assegnata automaticamente ai nuovi file.</span><span class="sxs-lookup"><span data-stu-id="449a6-132">The  Highly Confidential retention label, which is automatically assigned to new files.</span></span>
- <span data-ttu-id="449a6-133">Un criterio DLP che utilizza l'etichetta di conservazione e le impostazioni estremamente riservate che impediscono la condivisione dei file con gli utenti esterni.</span><span class="sxs-lookup"><span data-stu-id="449a6-133">A DLP policy that uses the Highly Confidential retention label and settings that block the file from being shared with external users.</span></span>
- <span data-ttu-id="449a6-134">L'etichetta di riservatezza del progetto 2X, con la crittografia e le autorizzazioni che viaggiano con il file se sono state spostate o copiate dal sito.</span><span class="sxs-lookup"><span data-stu-id="449a6-134">The Project 2X sensitivity label, with encryption and permissions that travel with the file if it is moved or copied from the site.</span></span>

<span data-ttu-id="449a6-135">Di seguito è riportato un esempio di un file archiviato nel sito di progetto 2X sottostante con l'etichetta di conservazione fortemente regolamentata e l'etichetta di riservatezza del progetto 2X assegnata.</span><span class="sxs-lookup"><span data-stu-id="449a6-135">Here is an example of a file stored in the underlying Project 2X site with the Highly Regulated retention label and the Project 2X sensitivity label assigned.</span></span>

![Un esempio di un file archiviato nel sito di progetto 2X sottostante](./media/contoso-team-for-highly-confidential-assets/final-config-example-file.png)
 
## <a name="step-4-trained-project-2x-team-members"></a><span data-ttu-id="449a6-137">Passaggio 4: formazione dei membri del team di Project 2X</span><span class="sxs-lookup"><span data-stu-id="449a6-137">Step 4: Trained Project 2X team members</span></span>

<span data-ttu-id="449a6-138">Il personale di sicurezza Contoso ha preparato i membri del team del progetto 2X in un corso obbligatorio che ha eseguito i seguenti controlli:</span><span class="sxs-lookup"><span data-stu-id="449a6-138">Contoso security staff trained the Project 2X team members in a mandatory course that stepped them through:</span></span>

- <span data-ttu-id="449a6-139">Come accedere al nuovo team di Project 2X, utilizzare riunioni e chat e come collaborare ai file del team.</span><span class="sxs-lookup"><span data-stu-id="449a6-139">How to access the new Project 2X team, use meetings and chats, and how to collaborate on team files.</span></span>
- <span data-ttu-id="449a6-140">Come creare nuovi file nel team e caricare nuovi file creati localmente.</span><span class="sxs-lookup"><span data-stu-id="449a6-140">How to create new files in the team and upload new files created locally.</span></span>
- <span data-ttu-id="449a6-141">Dimostrazione del modo in cui il criterio DLP blocca la condivisione esterna dei file.</span><span class="sxs-lookup"><span data-stu-id="449a6-141">A demonstration of how the DLP policy blocks files from being shared externally.</span></span>
- <span data-ttu-id="449a6-142">Come assegnare etichette ai file con l'etichetta di sensitivity di Project 2X.</span><span class="sxs-lookup"><span data-stu-id="449a6-142">How to label files with the Project 2X sensitivity label.</span></span>
- <span data-ttu-id="449a6-143">Dimostrazione del modo in cui l'etichetta del progetto 2X protegge un file anche quando lascia il team.</span><span class="sxs-lookup"><span data-stu-id="449a6-143">A demonstration of how the Project 2X  label protects a file even when it leaves the team.</span></span>

<span data-ttu-id="449a6-144">Il risultato finale è un ambiente sicuro in cui i membri del team di Project 2X hanno collaborato in un ambiente sicuro per chat, riunioni e file.</span><span class="sxs-lookup"><span data-stu-id="449a6-144">The end result was a secure environment in which Project 2X team members collaborated in a secure environment for chats, meetings, and files.</span></span>

<span data-ttu-id="449a6-145">In una coppia di istanze, Project 2X membri del team hanno scaricato i file protetti dall'etichetta Project 2X su un'unità locale per il lavoro offline.</span><span class="sxs-lookup"><span data-stu-id="449a6-145">In a couple of instances, Project 2X team members downloaded files protected by the Project 2X label to a local drive for offline work.</span></span> <span data-ttu-id="449a6-146">Tuttavia, dopo che sono state richieste le credenziali per l'apertura, si sono accorti del loro errore e li hanno eliminati.</span><span class="sxs-lookup"><span data-stu-id="449a6-146">However, after being prompted for credentials when opening them, they realized their mistake and deleted them.</span></span>

<span data-ttu-id="449a6-147">A causa dell'ambiente di collaborazione dei team e delle funzionalità di sicurezza di Microsoft 365, i dettagli di Project 2X sono stati mantenuti segreti per tutta la durata del progetto.</span><span class="sxs-lookup"><span data-stu-id="449a6-147">Because of the collaboration environment of Teams and the security features of Microsoft 365, the details of Project 2X were kept secret for the duration of the project.</span></span> <span data-ttu-id="449a6-148">Contoso ha annunciato i propri piani ed è in fase di implementazione dei nuovi prodotti e servizi per la gioia dei suoi clienti e investitori e per il disappunto dei suoi concorrenti.</span><span class="sxs-lookup"><span data-stu-id="449a6-148">Contoso announced its plans and is in the process of rolling out the new products and services to the delight of its customers and investors and the chagrin of its competitors.</span></span>

## <a name="next-step"></a><span data-ttu-id="449a6-149">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="449a6-149">Next step</span></span>

<span data-ttu-id="449a6-150">[Distribuzione](deploy-microsoft-365-enterprise.md) Microsoft 365 Enterprise nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="449a6-150">[Deploy](deploy-microsoft-365-enterprise.md) Microsoft 365 Enterprise in your organization.</span></span>

## <a name="see-also"></a><span data-ttu-id="449a6-151">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="449a6-151">See also</span></span>

<span data-ttu-id="449a6-152">[Raccolta di produttività di Microsoft 365](https://aka.ms/productivitylibrary)https://aka.ms/productivitylibrary)</span><span class="sxs-lookup"><span data-stu-id="449a6-152">[Microsoft 365 Productivity Library](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)</span></span>
