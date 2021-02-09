---
title: Pianificare gli argomenti di Microsoft Viva
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
description: Informazioni su come pianificare gli argomenti relativi alla pianificazione per Microsoft Viva
ms.openlocfilehash: 2f7b85399f0b1f49e25aae1f1d4627413594f618
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150479"
---
# <a name="plan-for-microsoft-viva-topics"></a><span data-ttu-id="58113-103">Pianificare gli argomenti di Microsoft Viva</span><span class="sxs-lookup"><span data-stu-id="58113-103">Plan for Microsoft Viva Topics</span></span>

<span data-ttu-id="58113-104">È possibile controllare la modalità di utilizzo degli argomenti nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="58113-104">You're in control of how topics are experienced in your organization.</span></span> <span data-ttu-id="58113-105">Le decisioni relative alla pianificazione per gli argomenti assicurano che gli argomenti di alta qualità siano visualizzati agli utenti e che gli utenti siano autorizzati a utilizzare e contribuire alle proprie conoscenze.</span><span class="sxs-lookup"><span data-stu-id="58113-105">Your planning decisions for Topics ensures that high quality topics are shown to your users and they have the right permissions to consume and contribute knowledge.</span></span>

<span data-ttu-id="58113-106">In questo articolo verranno esaminate queste decisioni di pianificazione:</span><span class="sxs-lookup"><span data-stu-id="58113-106">In this article we'll examine these planning decisions:</span></span>

- <span data-ttu-id="58113-107">Quali siti di SharePoint si desidera sotto ricercare per indicizzazione per gli argomenti</span><span class="sxs-lookup"><span data-stu-id="58113-107">Which SharePoint sites you want to crawl for topics</span></span>
- <span data-ttu-id="58113-108">Quali argomenti, se presenti, si desidera escludere dalle esperienze degli argomenti</span><span class="sxs-lookup"><span data-stu-id="58113-108">Which topics, if any, you want to exclude from topic experiences</span></span>
- <span data-ttu-id="58113-109">Utenti a cui si desidera rendere visibili gli argomenti</span><span class="sxs-lookup"><span data-stu-id="58113-109">Which users you want to make topics visible to</span></span>
- <span data-ttu-id="58113-110">Quali utenti si desidera concedere le autorizzazioni per gestire gli argomenti nel Centro argomenti</span><span class="sxs-lookup"><span data-stu-id="58113-110">Which users you want to give permissions to manage topics in the topic center</span></span>
- <span data-ttu-id="58113-111">Quali utenti si desidera concedere le autorizzazioni per creare o modificare argomenti nel Centro argomenti</span><span class="sxs-lookup"><span data-stu-id="58113-111">Which users you want to give permissions to create or edit topics in the topic center</span></span>
- <span data-ttu-id="58113-112">Nome da assegnare al Centro argomenti</span><span class="sxs-lookup"><span data-stu-id="58113-112">What name you want to give your topic center</span></span>

<span data-ttu-id="58113-113">La sicurezza e la privacy dei dati vengono rispettate e le esperienze degli argomenti non concedono agli utenti ulteriori accessi ai file per cui non hanno diritti.</span><span class="sxs-lookup"><span data-stu-id="58113-113">Security and privacy of your data is respected, and topic experiences does not grant users additional access to files they don’t have rights to.</span></span> <span data-ttu-id="58113-114">È consigliabile leggere anche [microsoft Viva Topics sulla sicurezza e la privacy](topic-experiences-security-privacy.md) nell'ambito del processo di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="58113-114">We recommend you also read [Microsoft Viva Topics security and privacy](topic-experiences-security-privacy.md) as part of your planning process.</span></span>

## <a name="requirements"></a><span data-ttu-id="58113-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="58113-115">Requirements</span></span>

<span data-ttu-id="58113-116">È necessario essere [iscritti ad Argomenti Viva](https://www.microsoft.com/microsoft-viva/topics) ed essere un amministratore globale o un amministratore di SharePoint per accedere all'interfaccia di amministrazione di Microsoft 365 e configurare Gli argomenti.</span><span class="sxs-lookup"><span data-stu-id="58113-116">You must be [subscribed to Viva Topics](https://www.microsoft.com/microsoft-viva/topics) and be a global administrator or SharePoint administrator to access the Microsoft 365 admin center and set up Topics.</span></span>

<span data-ttu-id="58113-117">Tutti gli utenti che useranno gli argomenti necessitano di **una licenza Per le esperienze di** argomento.</span><span class="sxs-lookup"><span data-stu-id="58113-117">All users who are going to use Topics require a **Topic Experiences** license.</span></span> <span data-ttu-id="58113-118">L'assegnazione delle licenze è trattata in [Configurare Microsoft Viva Topics.](set-up-topic-experiences.md)</span><span class="sxs-lookup"><span data-stu-id="58113-118">Assigning licenses is covered in [Set up Microsoft Viva Topics](set-up-topic-experiences.md).</span></span>

## <a name="topic-discovery"></a><span data-ttu-id="58113-119">Individuazione degli argomenti</span><span class="sxs-lookup"><span data-stu-id="58113-119">Topic discovery</span></span>

<span data-ttu-id="58113-120">Le impostazioni di individuazione degli argomenti specificano quali siti di SharePoint vengono utilizzati come origini per gli argomenti.</span><span class="sxs-lookup"><span data-stu-id="58113-120">The topic discovery settings specify which SharePoint sites are used as sources for topics.</span></span> <span data-ttu-id="58113-121">È possibile scegliere di includere tutti i siti di SharePoint, un elenco specifico di siti o nessun sito.</span><span class="sxs-lookup"><span data-stu-id="58113-121">You can choose to include all SharePoint sites, a specific list of sites, or no sites.</span></span> <span data-ttu-id="58113-122">È consigliabile scegliere tutti i siti in modo che le esperienze degli argomenti possano individuare un gran numero di argomenti per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="58113-122">We recommend that you choose all sites so that topic experiences can discover a large number of good topics for your users.</span></span>

<span data-ttu-id="58113-123">Quando si configurano gli argomenti, è possibile scegliere tra le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="58113-123">When you set up Topics, you can choose from the following options:</span></span>

- <span data-ttu-id="58113-124">**Tutti i siti:** tutti i siti di SharePoint nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="58113-124">**All sites**: All SharePoint sites in your organization.</span></span> <span data-ttu-id="58113-125">Sono inclusi i siti correnti e futuri.</span><span class="sxs-lookup"><span data-stu-id="58113-125">This includes current and future sites.</span></span>
- <span data-ttu-id="58113-126">**Tutti, ad eccezione dei siti selezionati:** tutti i siti ad eccezione di quelli specificati.</span><span class="sxs-lookup"><span data-stu-id="58113-126">**All, except selected sites**: All sites except for the ones you specify.</span></span> <span data-ttu-id="58113-127">I siti creati in futuro verranno inclusi come origini per l'individuazione degli argomenti.</span><span class="sxs-lookup"><span data-stu-id="58113-127">Sites created in future will be included as sources for topic discovery.</span></span> 
- <span data-ttu-id="58113-128">**Solo i siti selezionati:** solo i siti specificati.</span><span class="sxs-lookup"><span data-stu-id="58113-128">**Only selected sites**: Only the sites that you specify.</span></span> <span data-ttu-id="58113-129">I siti creati in futuro non verranno inclusi come origini per l'individuazione degli argomenti.</span><span class="sxs-lookup"><span data-stu-id="58113-129">Sites created in the future will not be included as sources for topic discovery.</span></span>
- <span data-ttu-id="58113-130">**Nessun sito:** non includere alcun sito di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="58113-130">**No sites**: Do not include any SharePoint sites.</span></span>

<span data-ttu-id="58113-131">Se si sceglie **Tutti, ad eccezione dei** siti selezionati o Solo i siti **selezionati,** è possibile caricare un file CSV con un elenco di siti.</span><span class="sxs-lookup"><span data-stu-id="58113-131">If you choose either **All, except selected sites** or **Only selected sites**, you can upload a .csv file with a list of sites.</span></span> <span data-ttu-id="58113-132">Queste opzioni sono utili se si sta eseguendo un progetto pilota e si desidera includere un numero limitato di siti da avviare.</span><span class="sxs-lookup"><span data-stu-id="58113-132">These options are useful if you're doing a pilot and you want to include a limited number of sites to start.</span></span>

<span data-ttu-id="58113-133">È possibile copiare il modello csv seguente:</span><span class="sxs-lookup"><span data-stu-id="58113-133">You can copy the .csv template below:</span></span>

``` csv
Site name,URL
```

<span data-ttu-id="58113-134">Non è consigliabile scegliere **Nessun sito perché** impedisce la creazione o l'aggiornamento automatico degli argomenti.</span><span class="sxs-lookup"><span data-stu-id="58113-134">We don't recommend choosing **No sites** because it prevents topics from being automatically created or updated.</span></span> <span data-ttu-id="58113-135">È tuttavia possibile scegliere questa opzione se si desidera configurare Argomenti e quindi aggiungere siti in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="58113-135">However, you can choose this option if you want to set up Topics and then add sites later.</span></span>

<span data-ttu-id="58113-136">È consigliabile creare un processo per consentire agli utenti o ai knowledge manager di richiedere la rimozione di singoli siti dall'individuazione degli argomenti, se necessario nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="58113-136">We recommend you create a process for users or knowledge managers to request individual sites be removed from topic discovery if needed in your organization.</span></span>

## <a name="user-permissions"></a><span data-ttu-id="58113-137">Autorizzazioni utenti</span><span class="sxs-lookup"><span data-stu-id="58113-137">User permissions</span></span>

<span data-ttu-id="58113-138">Le autorizzazioni utente specificate determinano quali persone nell'organizzazione interagiscono con gli argomenti e cosa possono fare.</span><span class="sxs-lookup"><span data-stu-id="58113-138">The user permissions that you specify determine which people in your organization interact with topics and what they can do.</span></span>

<span data-ttu-id="58113-139">*Gestire gli argomenti*</span><span class="sxs-lookup"><span data-stu-id="58113-139">*Manage topics*</span></span>

<span data-ttu-id="58113-140">I knowledge manager supervisionano la qualità delle informazioni, il modo in cui è strutturata e altre procedure consigliate nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="58113-140">Knowledge managers oversee the quality of information, how its structured, and other best practices in your organization.</span></span> <span data-ttu-id="58113-141">Possono confermare e rifiutare gli argomenti.</span><span class="sxs-lookup"><span data-stu-id="58113-141">They can confirm and reject topics.</span></span>

<span data-ttu-id="58113-142">Anche se è possibile specificare singoli responsabili degli argomenti, è consigliabile creare un gruppo di sicurezza (o utilizzarne uno esistente) contenente le persone che si desidera siano responsabili delle conoscenze.</span><span class="sxs-lookup"><span data-stu-id="58113-142">While you can specify individual topic managers, we recommend that you create a security group (or use an existing one) that contains the people who you want to be knowledge managers.</span></span> <span data-ttu-id="58113-143">È possibile specificare questo gruppo di sicurezza durante il processo di installazione.</span><span class="sxs-lookup"><span data-stu-id="58113-143">You can specify this security group during the setup process.</span></span>

<span data-ttu-id="58113-144">*Creare e modificare argomenti*</span><span class="sxs-lookup"><span data-stu-id="58113-144">*Create and edit topics*</span></span>

<span data-ttu-id="58113-145">I collaboratori degli argomenti sono i campioni e gli esperti in materia nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="58113-145">Topic contributors are the champions and subject matter experts in your organization.</span></span> <span data-ttu-id="58113-146">Possono creare e modificare argomenti.</span><span class="sxs-lookup"><span data-stu-id="58113-146">They can create and edit topics.</span></span> 

<span data-ttu-id="58113-147">È consigliabile consentire a tutti gli utenti dell'organizzazione di creare e modificare argomenti perché le esperienze degli argomenti funzionano al meglio quando tutti gli utenti possono condividere informazioni.</span><span class="sxs-lookup"><span data-stu-id="58113-147">We recommend that you allow everyone in your organization to create and edit topics because topic experiences work best when all users can share information.</span></span>

<span data-ttu-id="58113-148">Se si desidera limitare la creazione e la modifica di argomenti a utenti o gruppi specifici, creare un gruppo di sicurezza per loro e specificarlo durante il processo di installazione.</span><span class="sxs-lookup"><span data-stu-id="58113-148">If you want to limit creating and editing topics to specific people or groups, create a security group for them and specify it during the setup process.</span></span>

<span data-ttu-id="58113-149">È possibile scegliere di non consentire a nessuno di contribuire agli argomenti, ma non è consigliabile.</span><span class="sxs-lookup"><span data-stu-id="58113-149">You can choose to not allow anyone to contribute to topics, however this is not recommended.</span></span> <span data-ttu-id="58113-150">Se si sceglie questa opzione, i knowledge manager potranno comunque modificare e creare argomenti.</span><span class="sxs-lookup"><span data-stu-id="58113-150">Knowledge managers will still be able to edit and create topics if you choose this option.</span></span>

<span data-ttu-id="58113-151">*Visualizzatori di argomenti*</span><span class="sxs-lookup"><span data-stu-id="58113-151">*Topic viewers*</span></span>

<span data-ttu-id="58113-152">I visualizzatori di argomenti possono visualizzare informazioni sulle pagine degli argomenti, nei risultati della ricerca e quando gli argomenti vengono evidenziati nel contenuto come le pagine di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="58113-152">Topic viewers can see information on topic pages, in search results and when topics are highlighted in the content like SharePoint pages.</span></span> <span data-ttu-id="58113-153">Gli utenti possono visualizzare gli argomenti individuati solo quando hanno accesso ai file e alle pagine in cui è stato individuato l'argomento.</span><span class="sxs-lookup"><span data-stu-id="58113-153">Users can only see discovered topics when they have access to the files and pages the topic was discovered in.</span></span>

<span data-ttu-id="58113-154">Quando si configurano i visualizzatori di argomenti, è possibile scegliere tra:</span><span class="sxs-lookup"><span data-stu-id="58113-154">When setting up topic viewers, you can choose from:</span></span>

- <span data-ttu-id="58113-155">**Tutti gli utenti dell'organizzazione**</span><span class="sxs-lookup"><span data-stu-id="58113-155">**Everyone in my organization**</span></span>
- <span data-ttu-id="58113-156">**Solo utenti o gruppi di sicurezza selezionati**</span><span class="sxs-lookup"><span data-stu-id="58113-156">**Only selected people or security groups**</span></span>
- <span data-ttu-id="58113-157">**Nessuno**</span><span class="sxs-lookup"><span data-stu-id="58113-157">**No one**</span></span>

<span data-ttu-id="58113-158">È **consigliabile usare tutti gli** utenti dell'organizzazione, ma se si sta eseguendo un progetto pilota è consigliabile scegliere solo utenti o gruppi di sicurezza selezionati.</span><span class="sxs-lookup"><span data-stu-id="58113-158">We recommend **Everyone in my organization**, but if you're doing a pilot you may want to choose only selected people or security groups.</span></span> <span data-ttu-id="58113-159">È anche possibile scegliere **Nessuno** se si desidera configurare Gli argomenti, ma non consentire agli utenti di visualizzare ancora gli argomenti.</span><span class="sxs-lookup"><span data-stu-id="58113-159">You can also choose **No one** if you want to set up Topics, but not allow people to see topics yet.</span></span> <span data-ttu-id="58113-160">I responsabili della conoscenza avranno comunque accesso per consentire loro di visualizzare gli argomenti e ottenere assistenza per la decisione di rendere gli argomenti disponibili su vasta gamma.</span><span class="sxs-lookup"><span data-stu-id="58113-160">(Knowledge managers will still have access to allow them view the topics and help with the decision to make Topics broadly available.)</span></span>

## <a name="knowledge-rules"></a><span data-ttu-id="58113-161">Regole di conoscenza</span><span class="sxs-lookup"><span data-stu-id="58113-161">Knowledge rules</span></span>

<span data-ttu-id="58113-162">Gli amministratori possono escludere determinati argomenti dalle esperienze degli argomenti.</span><span class="sxs-lookup"><span data-stu-id="58113-162">As an administrator, you can exclude certain topics from topic experiences.</span></span> <span data-ttu-id="58113-163">Ciò è utile se si desidera evitare che i dati sensibili appaiano negli argomenti.</span><span class="sxs-lookup"><span data-stu-id="58113-163">This is useful if you want to keep sensitive data from appearing in topics.</span></span> <span data-ttu-id="58113-164">Anche se i knowledge manager possono escludere gli argomenti nel Centro argomenti, gli argomenti esclusi dall'amministratore non sono nemmeno visibili ai knowledge manager.</span><span class="sxs-lookup"><span data-stu-id="58113-164">While knowledge managers can exclude topics in the topic center, topics excluded by the administrator are not even visible to knowledge managers.</span></span> <span data-ttu-id="58113-165">I knowledge manager possono anche rimuovere gli argomenti nel Centro argomenti dopo l'individuazione.</span><span class="sxs-lookup"><span data-stu-id="58113-165">(Knowledge managers can also remove topics in the topic center after discovery.)</span></span>

<span data-ttu-id="58113-166">Se si desidera escludere gli argomenti a livello di amministratore, è necessario aggiungerli a un file CSV e caricarlo.</span><span class="sxs-lookup"><span data-stu-id="58113-166">If you want to exclude topics at the administrator level, you must add them to a .csv file and upload the file.</span></span> <span data-ttu-id="58113-167">È possibile eseguire questa operazione durante l'installazione o in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="58113-167">You can do this during setup or later.</span></span>

<span data-ttu-id="58113-168">Il file CSV deve contenere i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="58113-168">The .csv file must contain the following parameters:</span></span>

- <span data-ttu-id="58113-169">**Nome**: digitare il nome dell'argomento che si desidera escludere.</span><span class="sxs-lookup"><span data-stu-id="58113-169">**Name**: Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="58113-170">Questa operazione può essere eseguita in due modi:</span><span class="sxs-lookup"><span data-stu-id="58113-170">There are two ways to do this:</span></span>
- <span data-ttu-id="58113-171">**MatchType-Exact/Partial:** specificare se il nome immesso è un *tipo* di corrispondenza esatto *o* parziale.</span><span class="sxs-lookup"><span data-stu-id="58113-171">**MatchType-Exact/Partial**: Type whether the name you entered was an *exact* or *partial* match type.</span></span>
    - <span data-ttu-id="58113-172">Corrispondenza esatta: è possibile includere il nome esatto o l'acronimo (ad esempio, *Contoso* o *ATL).*</span><span class="sxs-lookup"><span data-stu-id="58113-172">Exact match: You can include the exact name or acronym (for example, *Contoso* or *ATL*).</span></span>
    - <span data-ttu-id="58113-173">Corrispondenza parziale: è possibile escludere tutti gli argomenti che includono una parola specifica.</span><span class="sxs-lookup"><span data-stu-id="58113-173">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="58113-174">Ad esempio, *l'arco* escluderà tutti gli argomenti con la parola arco *al* suo interno, ad esempio arco *circolare,* saldatura arco *di plasma* o arco *di formazione.* Si noti che non verranno esclusi gli argomenti in cui il testo è incluso come parte di una parola, ad esempio *Architecture.*</span><span class="sxs-lookup"><span data-stu-id="58113-174">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle*, *Plasma arc welding*, or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span>
- <span data-ttu-id="58113-175">**Acronimo di (facoltativo):**(noto anche come *espansione)* Se si desidera escludere un acronimo, digitare le parole che l'acronimo sta per.</span><span class="sxs-lookup"><span data-stu-id="58113-175">**Stands for (optional)**: (Also known as *expansion*) If you want to exclude an acronym, type the words the acronym stands for.</span></span>

    ![Escludere gli argomenti nel modello CSV](../media/exclude-topics-csv.png) 

<span data-ttu-id="58113-177">È possibile copiare il modello csv seguente:</span><span class="sxs-lookup"><span data-stu-id="58113-177">You can copy the csv template below:</span></span>

``` csv
Name (required),Expansion,MatchType- Exact/Partial (required)
```

## <a name="administration"></a><span data-ttu-id="58113-178">Amministrazione</span><span class="sxs-lookup"><span data-stu-id="58113-178">Administration</span></span>

<span data-ttu-id="58113-179">Quando si configurano gli argomenti, durante il processo di configurazione viene creato automaticamente un centro argomenti.</span><span class="sxs-lookup"><span data-stu-id="58113-179">When you set up Topics, as part of the setup process, a topic center is automatically created.</span></span> <span data-ttu-id="58113-180">Pensa a cosa vuoi assegnare un nome al Centro argomenti e a cosa vuoi che sia l'URL.</span><span class="sxs-lookup"><span data-stu-id="58113-180">Think about what you want to name the topic center and what you want the URL to be.</span></span> <span data-ttu-id="58113-181">È possibile impostare sia il nome che l'URL come parte del processo di configurazione e modificare il nome (ma non l'URL) in un secondo momento nell'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="58113-181">You can set both the name and URL as part of the setup process, and you can change the name (but not URL) later in the Microsoft 365 admin center.</span></span> <span data-ttu-id="58113-182">È possibile avere un solo centro argomenti.</span><span class="sxs-lookup"><span data-stu-id="58113-182">You can only have one topic center.</span></span>

## <a name="setup-checklist"></a><span data-ttu-id="58113-183">Elenco di controllo per l'installazione</span><span class="sxs-lookup"><span data-stu-id="58113-183">Setup checklist</span></span>

<span data-ttu-id="58113-184">Quando si configurano le esperienze degli argomenti, sono necessari gli elementi seguenti durante l'installazione guidata:</span><span class="sxs-lookup"><span data-stu-id="58113-184">When you set up topic experiences, you'll need the following items as you go through the setup wizard:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="58113-185">Elenco di siti da includere o escludere se non sono inclusi tutti i siti per l'individuazione degli argomenti</span><span class="sxs-lookup"><span data-stu-id="58113-185">List of sites to include or exclude if not including all sites for topic discovery</span></span>
> * <span data-ttu-id="58113-186">Gruppo di sicurezza per i visualizzatori di argomenti se non si consente a tutti gli utenti di visualizzare gli argomenti</span><span class="sxs-lookup"><span data-stu-id="58113-186">Security group for topic viewers if not allowing all users to view topics</span></span>
> * <span data-ttu-id="58113-187">Gruppo di sicurezza per i collaboratori di argomenti se non si consente a tutti gli utenti di creare e modificare argomenti</span><span class="sxs-lookup"><span data-stu-id="58113-187">Security group for topic contributors if not allowing all users to create and edit topics</span></span>
> * <span data-ttu-id="58113-188">Gruppo di sicurezza per i knowledge manager degli argomenti se non si consente a tutti gli utenti di gestire gli argomenti</span><span class="sxs-lookup"><span data-stu-id="58113-188">Security group for topic knowledge managers if not allowing all users to manage topics</span></span>
> * <span data-ttu-id="58113-189">Elenco di argomenti sensibili da escludere dall'individuazione degli argomenti</span><span class="sxs-lookup"><span data-stu-id="58113-189">List of sensitive topics to exclude from topic discovery</span></span>
> * <span data-ttu-id="58113-190">Un nome per il sito Centro argomenti</span><span class="sxs-lookup"><span data-stu-id="58113-190">A name for your topic center site</span></span>

## <a name="see-also"></a><span data-ttu-id="58113-191">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="58113-191">See also</span></span>

[<span data-ttu-id="58113-192">Configurare le esperienze dell'argomento</span><span class="sxs-lookup"><span data-stu-id="58113-192">Set up topic experiences</span></span>](set-up-topic-experiences.md)

[<span data-ttu-id="58113-193">Gestire l'individuazione degli argomenti in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="58113-193">Manage topic discovery in Microsoft 365</span></span>](topic-experiences-discovery.md)

[<span data-ttu-id="58113-194">Gestire la visibilità degli argomenti in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="58113-194">Manage topic visibility in Microsoft 365</span></span>](topic-experiences-knowledge-rules.md)

[<span data-ttu-id="58113-195">Gestire le autorizzazioni per gli argomenti in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="58113-195">Manage topic permissions in Microsoft 365</span></span>](topic-experiences-user-permissions.md)

[<span data-ttu-id="58113-196">Modificare il nome del Centro argomenti in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="58113-196">Change the name of the topic center in Microsoft 365</span></span>](topic-experiences-administration.md)
