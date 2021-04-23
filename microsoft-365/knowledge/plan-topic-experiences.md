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
ms.openlocfilehash: d64e4b341fe96d7aa3636f58bffe3dd8f388838e
ms.sourcegitcommit: b6763a8ab240fbdd56078a7c9452445d0c4b9545
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2021
ms.locfileid: "51957540"
---
# <a name="plan-for-microsoft-viva-topics"></a><span data-ttu-id="70c17-103">Pianificare gli argomenti di Microsoft Viva</span><span class="sxs-lookup"><span data-stu-id="70c17-103">Plan for Microsoft Viva Topics</span></span>

<span data-ttu-id="70c17-104">L'utente ha il controllo dell'esperienza degli argomenti nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="70c17-104">You're in control of how topics are experienced in your organization.</span></span> <span data-ttu-id="70c17-105">Le decisioni di pianificazione per Gli argomenti assicurano che gli utenti siano in grado di visualizzare argomenti di alta qualità e di disporre delle autorizzazioni appropriate per l'utilizzo e il contributo delle conoscenze.</span><span class="sxs-lookup"><span data-stu-id="70c17-105">Your planning decisions for Topics ensures that high quality topics are shown to your users and they have the right permissions to consume and contribute knowledge.</span></span>

<span data-ttu-id="70c17-106">In questo articolo verranno esaminate queste decisioni di pianificazione:</span><span class="sxs-lookup"><span data-stu-id="70c17-106">In this article we'll examine these planning decisions:</span></span>

- <span data-ttu-id="70c17-107">Siti di SharePoint di cui eseguire la ricerca per indicizzazione per gli argomenti</span><span class="sxs-lookup"><span data-stu-id="70c17-107">Which SharePoint sites you want to crawl for topics</span></span>
- <span data-ttu-id="70c17-108">Quali argomenti, se presenti, si desidera escludere dalle esperienze degli argomenti</span><span class="sxs-lookup"><span data-stu-id="70c17-108">Which topics, if any, you want to exclude from topic experiences</span></span>
- <span data-ttu-id="70c17-109">Utenti a cui si desidera rendere visibili gli argomenti</span><span class="sxs-lookup"><span data-stu-id="70c17-109">Which users you want to make topics visible to</span></span>
- <span data-ttu-id="70c17-110">Quali utenti si desidera concedere le autorizzazioni per gestire gli argomenti nel Centro argomenti</span><span class="sxs-lookup"><span data-stu-id="70c17-110">Which users you want to give permissions to manage topics in the topic center</span></span>
- <span data-ttu-id="70c17-111">Utenti a cui si desidera concedere le autorizzazioni per creare o modificare argomenti nel Centro argomenti</span><span class="sxs-lookup"><span data-stu-id="70c17-111">Which users you want to give permissions to create or edit topics in the topic center</span></span>
- <span data-ttu-id="70c17-112">Nome da assegnare al centro argomenti</span><span class="sxs-lookup"><span data-stu-id="70c17-112">What name you want to give your topic center</span></span>

<span data-ttu-id="70c17-113">La sicurezza e la privacy dei dati vengono rispettate e le esperienze degli argomenti non concedono agli utenti l'accesso aggiuntivo ai file a cui non hanno diritti.</span><span class="sxs-lookup"><span data-stu-id="70c17-113">Security and privacy of your data is respected, and topic experiences does not grant users additional access to files they don’t have rights to.</span></span> <span data-ttu-id="70c17-114">È consigliabile leggere anche [La sicurezza e la privacy](topic-experiences-security-privacy.md) di Microsoft Viva Topics nell'ambito del processo di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="70c17-114">We recommend you also read [Microsoft Viva Topics security and privacy](topic-experiences-security-privacy.md) as part of your planning process.</span></span>

## <a name="requirements"></a><span data-ttu-id="70c17-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="70c17-115">Requirements</span></span>

<span data-ttu-id="70c17-116">È necessario essere [abbonati a Viva Topics](https://www.microsoft.com/microsoft-viva/topics) ed essere un amministratore globale o un amministratore di SharePoint per accedere all'interfaccia di amministrazione di Microsoft 365 e configurare Gli argomenti.</span><span class="sxs-lookup"><span data-stu-id="70c17-116">You must be [subscribed to Viva Topics](https://www.microsoft.com/microsoft-viva/topics) and be a global administrator or SharePoint administrator to access the Microsoft 365 admin center and set up Topics.</span></span>

<span data-ttu-id="70c17-117">Tutti gli utenti che useranno Gli argomenti richiedono una **licenza esperienze di** argomento.</span><span class="sxs-lookup"><span data-stu-id="70c17-117">All users who are going to use Topics require a **Topic Experiences** license.</span></span> <span data-ttu-id="70c17-118">L'assegnazione delle licenze è trattata in [Set up Microsoft Viva Topics.](set-up-topic-experiences.md)</span><span class="sxs-lookup"><span data-stu-id="70c17-118">Assigning licenses is covered in [Set up Microsoft Viva Topics](set-up-topic-experiences.md).</span></span>

## <a name="topic-discovery"></a><span data-ttu-id="70c17-119">Individuazione argomenti</span><span class="sxs-lookup"><span data-stu-id="70c17-119">Topic discovery</span></span>

<span data-ttu-id="70c17-120">Le impostazioni di individuazione degli argomenti specificano quali siti di SharePoint vengono utilizzati come origini per gli argomenti.</span><span class="sxs-lookup"><span data-stu-id="70c17-120">The topic discovery settings specify which SharePoint sites are used as sources for topics.</span></span> <span data-ttu-id="70c17-121">È possibile scegliere di includere tutti i siti di SharePoint, un elenco specifico di siti o nessun sito.</span><span class="sxs-lookup"><span data-stu-id="70c17-121">You can choose to include all SharePoint sites, a specific list of sites, or no sites.</span></span> <span data-ttu-id="70c17-122">È consigliabile scegliere tutti i siti in modo che le esperienze degli argomenti possano individuare un gran numero di argomenti importanti per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="70c17-122">We recommend that you choose all sites so that topic experiences can discover a large number of good topics for your users.</span></span>

<span data-ttu-id="70c17-123">Quando si configurano gli argomenti, è possibile scegliere tra le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="70c17-123">When you set up Topics, you can choose from the following options:</span></span>

- <span data-ttu-id="70c17-124">**Tutti i siti**: tutti i siti di SharePoint nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="70c17-124">**All sites**: All SharePoint sites in your organization.</span></span> <span data-ttu-id="70c17-125">Sono inclusi i siti correnti e futuri.</span><span class="sxs-lookup"><span data-stu-id="70c17-125">This includes current and future sites.</span></span>
- <span data-ttu-id="70c17-126">**Tutti, ad eccezione dei siti selezionati:** tutti i siti ad eccezione di quelli specificati.</span><span class="sxs-lookup"><span data-stu-id="70c17-126">**All, except selected sites**: All sites except for the ones you specify.</span></span> <span data-ttu-id="70c17-127">I siti creati in futuro verranno inclusi come origini per l'individuazione degli argomenti.</span><span class="sxs-lookup"><span data-stu-id="70c17-127">Sites created in future will be included as sources for topic discovery.</span></span> 
- <span data-ttu-id="70c17-128">**Solo siti selezionati:** solo i siti specificati.</span><span class="sxs-lookup"><span data-stu-id="70c17-128">**Only selected sites**: Only the sites that you specify.</span></span> <span data-ttu-id="70c17-129">I siti creati in futuro non verranno inclusi come origini per l'individuazione degli argomenti.</span><span class="sxs-lookup"><span data-stu-id="70c17-129">Sites created in the future will not be included as sources for topic discovery.</span></span>
- <span data-ttu-id="70c17-130">**Nessun sito:** non includere alcun sito di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="70c17-130">**No sites**: Do not include any SharePoint sites.</span></span>

<span data-ttu-id="70c17-131">Se si sceglie **Tutti, ad** eccezione dei siti selezionati o Solo i siti **selezionati,** è possibile caricare un file CSV con un elenco di siti.</span><span class="sxs-lookup"><span data-stu-id="70c17-131">If you choose either **All, except selected sites** or **Only selected sites**, you can upload a .csv file with a list of sites.</span></span> <span data-ttu-id="70c17-132">Queste opzioni sono utili se si sta eseguendo un progetto pilota e si desidera includere un numero limitato di siti da avviare.</span><span class="sxs-lookup"><span data-stu-id="70c17-132">These options are useful if you're doing a pilot and you want to include a limited number of sites to start.</span></span>

<span data-ttu-id="70c17-133">È possibile copiare il modello csv seguente:</span><span class="sxs-lookup"><span data-stu-id="70c17-133">You can copy the .csv template below:</span></span>

``` csv
Site name,URL
```

<span data-ttu-id="70c17-134">Non è consigliabile scegliere **Nessun sito perché** impedisce la creazione o l'aggiornamento automatico degli argomenti.</span><span class="sxs-lookup"><span data-stu-id="70c17-134">We don't recommend choosing **No sites** because it prevents topics from being automatically created or updated.</span></span> <span data-ttu-id="70c17-135">È tuttavia possibile scegliere questa opzione se si desidera configurare Gli argomenti e quindi aggiungere siti in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="70c17-135">However, you can choose this option if you want to set up Topics and then add sites later.</span></span>

<span data-ttu-id="70c17-136">È consigliabile creare un processo per consentire agli utenti o ai knowledge manager di richiedere la rimozione di singoli siti dall'individuazione degli argomenti, se necessario nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="70c17-136">We recommend you create a process for users or knowledge managers to request individual sites be removed from topic discovery if needed in your organization.</span></span>

### <a name="multi-geo"></a><span data-ttu-id="70c17-137">Multi-Geo</span><span class="sxs-lookup"><span data-stu-id="70c17-137">Multi-geo</span></span>

<span data-ttu-id="70c17-138">Se l'organizzazione ha distribuito [Microsoft 365 Multi-Geo,](/microsoft-365/enterprise/microsoft-365-multi-geo)viene eseguito il provisioning del Centro argomenti nella posizione centrale e solo i siti di SharePoint nella posizione centrale sono disponibili per l'utilizzo come origini per gli argomenti.</span><span class="sxs-lookup"><span data-stu-id="70c17-138">If your organization has deployed [Microsoft 365 Multi-Geo](/microsoft-365/enterprise/microsoft-365-multi-geo), the topic center is provisioned in the central location and only SharePoint sites in the central location are available to use as sources for topics.</span></span> <span data-ttu-id="70c17-139">Se si seleziona **Tutti i siti,** Viva Topics utilizzerà tutti i siti nella posizione centrale.</span><span class="sxs-lookup"><span data-stu-id="70c17-139">(If you select **All sites**, Viva Topics will use all site in the central location.)</span></span>

<span data-ttu-id="70c17-140">Tutte le operazioni di elaborazione e archiviazione del contenuto vengono eseguite nella posizione centrale.</span><span class="sxs-lookup"><span data-stu-id="70c17-140">All processing and storage of content is done in the central location.</span></span>

## <a name="user-permissions"></a><span data-ttu-id="70c17-141">Autorizzazioni utenti</span><span class="sxs-lookup"><span data-stu-id="70c17-141">User permissions</span></span>

<span data-ttu-id="70c17-142">Le autorizzazioni utente specificate determinano quali persone dell'organizzazione interagiscono con gli argomenti e cosa possono fare.</span><span class="sxs-lookup"><span data-stu-id="70c17-142">The user permissions that you specify determine which people in your organization interact with topics and what they can do.</span></span>

> [!Note] 
> <span data-ttu-id="70c17-143">Al momento, Viva Topics non supporta la fornitura di licenze o autorizzazioni utente per gli utenti Guest (esterni).</span><span class="sxs-lookup"><span data-stu-id="70c17-143">At this time, Viva Topics doesn't support providing licenses or user permissions for Guest (External) users.</span></span> 

<span data-ttu-id="70c17-144">*Gestisci argomenti*</span><span class="sxs-lookup"><span data-stu-id="70c17-144">*Manage topics*</span></span>

<span data-ttu-id="70c17-145">I knowledge manager supervisionano la qualità delle informazioni, il modo in cui è strutturata e altre procedure consigliate nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="70c17-145">Knowledge managers oversee the quality of information, how its structured, and other best practices in your organization.</span></span> <span data-ttu-id="70c17-146">Possono confermare e rifiutare gli argomenti.</span><span class="sxs-lookup"><span data-stu-id="70c17-146">They can confirm and reject topics.</span></span>

<span data-ttu-id="70c17-147">Sebbene sia possibile specificare singoli responsabili degli argomenti, è consigliabile creare un gruppo di sicurezza (o utilizzarne uno esistente) contenente le persone che si desidera siano responsabili della conoscenza.</span><span class="sxs-lookup"><span data-stu-id="70c17-147">While you can specify individual topic managers, we recommend that you create a security group (or use an existing one) that contains the people who you want to be knowledge managers.</span></span> <span data-ttu-id="70c17-148">È possibile specificare questo gruppo di sicurezza durante il processo di installazione.</span><span class="sxs-lookup"><span data-stu-id="70c17-148">You can specify this security group during the setup process.</span></span>

<span data-ttu-id="70c17-149">*Creare e modificare argomenti*</span><span class="sxs-lookup"><span data-stu-id="70c17-149">*Create and edit topics*</span></span>

<span data-ttu-id="70c17-150">I collaboratori degli argomenti sono i campioni e gli esperti in materia nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="70c17-150">Topic contributors are the champions and subject matter experts in your organization.</span></span> <span data-ttu-id="70c17-151">Possono creare e modificare argomenti.</span><span class="sxs-lookup"><span data-stu-id="70c17-151">They can create and edit topics.</span></span> 

<span data-ttu-id="70c17-152">È consigliabile consentire a tutti gli utenti dell'organizzazione di creare e modificare argomenti perché le esperienze degli argomenti funzionano al meglio quando tutti gli utenti possono condividere informazioni.</span><span class="sxs-lookup"><span data-stu-id="70c17-152">We recommend that you allow everyone in your organization to create and edit topics because topic experiences work best when all users can share information.</span></span>

<span data-ttu-id="70c17-153">Se si desidera limitare la creazione e la modifica di argomenti a utenti o gruppi specifici, creare un gruppo di sicurezza per loro e specificarlo durante il processo di installazione.</span><span class="sxs-lookup"><span data-stu-id="70c17-153">If you want to limit creating and editing topics to specific people or groups, create a security group for them and specify it during the setup process.</span></span>

<span data-ttu-id="70c17-154">È possibile scegliere di non consentire a nessuno di contribuire agli argomenti, tuttavia non è consigliabile.</span><span class="sxs-lookup"><span data-stu-id="70c17-154">You can choose to not allow anyone to contribute to topics, however this is not recommended.</span></span> <span data-ttu-id="70c17-155">Se si sceglie questa opzione, i knowledge manager potranno comunque modificare e creare argomenti.</span><span class="sxs-lookup"><span data-stu-id="70c17-155">Knowledge managers will still be able to edit and create topics if you choose this option.</span></span>

<span data-ttu-id="70c17-156">*Visualizzatori argomenti*</span><span class="sxs-lookup"><span data-stu-id="70c17-156">*Topic viewers*</span></span>

<span data-ttu-id="70c17-157">I visualizzatori di argomenti possono visualizzare informazioni sulle pagine degli argomenti, nei risultati della ricerca e quando gli argomenti vengono evidenziati nel contenuto come le pagine di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="70c17-157">Topic viewers can see information on topic pages, in search results and when topics are highlighted in the content like SharePoint pages.</span></span> <span data-ttu-id="70c17-158">Gli utenti possono visualizzare gli argomenti individuati solo quando hanno accesso ai file e alle pagine in cui è stato individuato l'argomento.</span><span class="sxs-lookup"><span data-stu-id="70c17-158">Users can only see discovered topics when they have access to the files and pages the topic was discovered in.</span></span>

<span data-ttu-id="70c17-159">Quando si configurano i visualizzatori di argomenti, è possibile scegliere tra:</span><span class="sxs-lookup"><span data-stu-id="70c17-159">When setting up topic viewers, you can choose from:</span></span>

- <span data-ttu-id="70c17-160">**Tutti gli utenti dell'organizzazione**</span><span class="sxs-lookup"><span data-stu-id="70c17-160">**Everyone in my organization**</span></span>
- <span data-ttu-id="70c17-161">**Solo utenti o gruppi di sicurezza selezionati**</span><span class="sxs-lookup"><span data-stu-id="70c17-161">**Only selected people or security groups**</span></span>
- <span data-ttu-id="70c17-162">**Nessuno**</span><span class="sxs-lookup"><span data-stu-id="70c17-162">**No one**</span></span>

<span data-ttu-id="70c17-163">Si consiglia **a Tutti gli** utenti dell'organizzazione, ma se si sta eseguendo un progetto pilota è consigliabile scegliere solo persone o gruppi di sicurezza selezionati.</span><span class="sxs-lookup"><span data-stu-id="70c17-163">We recommend **Everyone in my organization**, but if you're doing a pilot you may want to choose only selected people or security groups.</span></span> <span data-ttu-id="70c17-164">È inoltre possibile scegliere **Nessuno** se si desidera configurare Gli argomenti, ma non consentire agli utenti di visualizzare gli argomenti.</span><span class="sxs-lookup"><span data-stu-id="70c17-164">You can also choose **No one** if you want to set up Topics, but not allow people to see topics yet.</span></span> <span data-ttu-id="70c17-165">I knowledge manager avranno comunque accesso per consentire loro di visualizzare gli argomenti e di ottenere assistenza per la decisione di rendere gli argomenti ampiamente disponibili.</span><span class="sxs-lookup"><span data-stu-id="70c17-165">(Knowledge managers will still have access to allow them view the topics and help with the decision to make Topics broadly available.)</span></span>

## <a name="knowledge-rules"></a><span data-ttu-id="70c17-166">Regole della knowledge base</span><span class="sxs-lookup"><span data-stu-id="70c17-166">Knowledge rules</span></span>

<span data-ttu-id="70c17-167">Gli amministratori possono escludere determinati argomenti dalle esperienze degli argomenti.</span><span class="sxs-lookup"><span data-stu-id="70c17-167">As an administrator, you can exclude certain topics from topic experiences.</span></span> <span data-ttu-id="70c17-168">Ciò è utile se si desidera evitare che i dati sensibili appaiano negli argomenti.</span><span class="sxs-lookup"><span data-stu-id="70c17-168">This is useful if you want to keep sensitive data from appearing in topics.</span></span> <span data-ttu-id="70c17-169">Anche se i knowledge manager possono escludere gli argomenti nel Centro argomenti, gli argomenti esclusi dall'amministratore non sono nemmeno visibili ai knowledge manager.</span><span class="sxs-lookup"><span data-stu-id="70c17-169">While knowledge managers can exclude topics in the topic center, topics excluded by the administrator are not even visible to knowledge managers.</span></span> <span data-ttu-id="70c17-170">I responsabili della conoscenza possono anche rimuovere gli argomenti nel Centro argomenti dopo l'individuazione.</span><span class="sxs-lookup"><span data-stu-id="70c17-170">(Knowledge managers can also remove topics in the topic center after discovery.)</span></span>

<span data-ttu-id="70c17-171">Se si desidera escludere gli argomenti a livello di amministratore, è necessario aggiungerli a un file CSV e caricare il file.</span><span class="sxs-lookup"><span data-stu-id="70c17-171">If you want to exclude topics at the administrator level, you must add them to a .csv file and upload the file.</span></span> <span data-ttu-id="70c17-172">È possibile eseguire questa operazione durante l'installazione o in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="70c17-172">You can do this during setup or later.</span></span>

<span data-ttu-id="70c17-173">Il file CSV deve contenere i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="70c17-173">The .csv file must contain the following parameters:</span></span>

- <span data-ttu-id="70c17-174">**Nome**: digitare il nome dell'argomento che si desidera escludere.</span><span class="sxs-lookup"><span data-stu-id="70c17-174">**Name**: Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="70c17-175">Questa operazione può essere eseguita in due modi:</span><span class="sxs-lookup"><span data-stu-id="70c17-175">There are two ways to do this:</span></span>
- <span data-ttu-id="70c17-176">**MatchType-Exact/Partial**: Digitare se il nome immesso è un *tipo* di corrispondenza esatto *o* parziale.</span><span class="sxs-lookup"><span data-stu-id="70c17-176">**MatchType-Exact/Partial**: Type whether the name you entered was an *exact* or *partial* match type.</span></span>
    - <span data-ttu-id="70c17-177">Corrispondenza esatta: è possibile includere il nome esatto o l'acronimo (ad esempio, *Contoso* o *ATL).*</span><span class="sxs-lookup"><span data-stu-id="70c17-177">Exact match: You can include the exact name or acronym (for example, *Contoso* or *ATL*).</span></span>
    - <span data-ttu-id="70c17-178">Corrispondenza parziale: è possibile escludere tutti gli argomenti che includono una parola specifica.</span><span class="sxs-lookup"><span data-stu-id="70c17-178">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="70c17-179">Ad esempio, *arco* escluderà tutti gli argomenti con la parola arco *al* suo interno, ad esempio Cerchio *arco,* *Saldatura* arco di plasma o *Arco di formazione.* Si noti che non verranno esclusi gli argomenti in cui il testo è incluso come parte di una parola, ad esempio *Architettura*.</span><span class="sxs-lookup"><span data-stu-id="70c17-179">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle*, *Plasma arc welding*, or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span>
- <span data-ttu-id="70c17-180">**Sta per (facoltativo):**(noto anche come espansione *)* Se si desidera escludere un acronimo, digitare le parole che l'acronimo sta per.</span><span class="sxs-lookup"><span data-stu-id="70c17-180">**Stands for (optional)**: (Also known as *expansion*) If you want to exclude an acronym, type the words the acronym stands for.</span></span>

    ![Escludere gli argomenti nel modello CSV](../media/exclude-topics-csv.png) 

<span data-ttu-id="70c17-182">È possibile copiare il modello csv seguente:</span><span class="sxs-lookup"><span data-stu-id="70c17-182">You can copy the csv template below:</span></span>

``` csv
Name (required),Expansion,MatchType- Exact/Partial (required)
```

## <a name="administration"></a><span data-ttu-id="70c17-183">Amministrazione</span><span class="sxs-lookup"><span data-stu-id="70c17-183">Administration</span></span>

<span data-ttu-id="70c17-184">Quando si configurano gli argomenti, come parte del processo di installazione, viene creato automaticamente un centro argomenti.</span><span class="sxs-lookup"><span data-stu-id="70c17-184">When you set up Topics, as part of the setup process, a topic center is automatically created.</span></span> <span data-ttu-id="70c17-185">Pensa a cosa vuoi assegnare un nome al Centro argomenti e a cosa vuoi che sia l'URL.</span><span class="sxs-lookup"><span data-stu-id="70c17-185">Think about what you want to name the topic center and what you want the URL to be.</span></span> <span data-ttu-id="70c17-186">È possibile impostare sia il nome che l'URL come parte del processo di installazione e modificare il nome (ma non l'URL) in un secondo momento nell'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="70c17-186">You can set both the name and URL as part of the setup process, and you can change the name (but not URL) later in the Microsoft 365 admin center.</span></span> <span data-ttu-id="70c17-187">È possibile avere un solo centro argomenti.</span><span class="sxs-lookup"><span data-stu-id="70c17-187">You can only have one topic center.</span></span>

## <a name="setup-checklist"></a><span data-ttu-id="70c17-188">Elenco di controllo per l'installazione</span><span class="sxs-lookup"><span data-stu-id="70c17-188">Setup checklist</span></span>

<span data-ttu-id="70c17-189">Quando si configurano le esperienze degli argomenti, durante l'installazione guidata saranno necessari gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="70c17-189">When you set up topic experiences, you'll need the following items as you go through the setup wizard:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="70c17-190">Elenco di siti da includere o escludere se non si includono tutti i siti per l'individuazione degli argomenti</span><span class="sxs-lookup"><span data-stu-id="70c17-190">List of sites to include or exclude if not including all sites for topic discovery</span></span>
> * <span data-ttu-id="70c17-191">Gruppo di sicurezza per i visualizzatori di argomenti se non si consente a tutti gli utenti di visualizzare gli argomenti</span><span class="sxs-lookup"><span data-stu-id="70c17-191">Security group for topic viewers if not allowing all users to view topics</span></span>
> * <span data-ttu-id="70c17-192">Gruppo di sicurezza per i collaboratori di argomenti se non si consente a tutti gli utenti di creare e modificare argomenti</span><span class="sxs-lookup"><span data-stu-id="70c17-192">Security group for topic contributors if not allowing all users to create and edit topics</span></span>
> * <span data-ttu-id="70c17-193">Gruppo di sicurezza per i knowledge manager degli argomenti se non si consente a tutti gli utenti di gestire gli argomenti</span><span class="sxs-lookup"><span data-stu-id="70c17-193">Security group for topic knowledge managers if not allowing all users to manage topics</span></span>
> * <span data-ttu-id="70c17-194">Elenco di argomenti sensibili da escludere dall'individuazione degli argomenti</span><span class="sxs-lookup"><span data-stu-id="70c17-194">List of sensitive topics to exclude from topic discovery</span></span>
> * <span data-ttu-id="70c17-195">Nome del sito Centro argomenti</span><span class="sxs-lookup"><span data-stu-id="70c17-195">A name for your topic center site</span></span>

## <a name="see-also"></a><span data-ttu-id="70c17-196">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="70c17-196">See also</span></span>

[<span data-ttu-id="70c17-197">Configurare le esperienze dell'argomento</span><span class="sxs-lookup"><span data-stu-id="70c17-197">Set up topic experiences</span></span>](set-up-topic-experiences.md)

[<span data-ttu-id="70c17-198">Gestire l'individuazione degli argomenti in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="70c17-198">Manage topic discovery in Microsoft 365</span></span>](topic-experiences-discovery.md)

[<span data-ttu-id="70c17-199">Gestire la visibilità degli argomenti in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="70c17-199">Manage topic visibility in Microsoft 365</span></span>](topic-experiences-knowledge-rules.md)

[<span data-ttu-id="70c17-200">Gestire le autorizzazioni per gli argomenti in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="70c17-200">Manage topic permissions in Microsoft 365</span></span>](topic-experiences-user-permissions.md)

[<span data-ttu-id="70c17-201">Modificare il nome del Centro argomenti in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="70c17-201">Change the name of the topic center in Microsoft 365</span></span>](topic-experiences-administration.md)
