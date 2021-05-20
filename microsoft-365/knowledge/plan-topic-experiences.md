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
ms.openlocfilehash: de7534ce58a7888ac822826ef4ef1b4934ed8cb1
ms.sourcegitcommit: 9541d5e6720a06327dc785e3ad7e8fb11246fd72
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2021
ms.locfileid: "52583113"
---
# <a name="plan-for-microsoft-viva-topics"></a><span data-ttu-id="5f1c9-103">Pianificare gli argomenti di Microsoft Viva</span><span class="sxs-lookup"><span data-stu-id="5f1c9-103">Plan for Microsoft Viva Topics</span></span>

<span data-ttu-id="5f1c9-104">L'utente ha il controllo dell'esperienza degli argomenti nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-104">You're in control of how topics are experienced in your organization.</span></span> <span data-ttu-id="5f1c9-105">Le decisioni di pianificazione per Gli argomenti assicurano che gli utenti siano in grado di visualizzare argomenti di alta qualità e di disporre delle autorizzazioni appropriate per l'utilizzo e il contributo delle conoscenze.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-105">Your planning decisions for Topics ensures that high quality topics are shown to your users and they have the right permissions to consume and contribute knowledge.</span></span>

<span data-ttu-id="5f1c9-106">In questo articolo verranno esaminate queste decisioni di pianificazione:</span><span class="sxs-lookup"><span data-stu-id="5f1c9-106">In this article we'll examine these planning decisions:</span></span>

- <span data-ttu-id="5f1c9-107">Quali SharePoint di ricerca per indicizzazione per gli argomenti</span><span class="sxs-lookup"><span data-stu-id="5f1c9-107">Which SharePoint sites you want to crawl for topics</span></span>
- <span data-ttu-id="5f1c9-108">Quali argomenti, se presenti, si desidera escludere dalle esperienze degli argomenti</span><span class="sxs-lookup"><span data-stu-id="5f1c9-108">Which topics, if any, you want to exclude from topic experiences</span></span>
- <span data-ttu-id="5f1c9-109">Utenti a cui si desidera rendere visibili gli argomenti</span><span class="sxs-lookup"><span data-stu-id="5f1c9-109">Which users you want to make topics visible to</span></span>
- <span data-ttu-id="5f1c9-110">Quali utenti si desidera concedere le autorizzazioni per gestire gli argomenti nel Centro argomenti</span><span class="sxs-lookup"><span data-stu-id="5f1c9-110">Which users you want to give permissions to manage topics in the topic center</span></span>
- <span data-ttu-id="5f1c9-111">Utenti a cui si desidera concedere le autorizzazioni per creare o modificare argomenti nel Centro argomenti</span><span class="sxs-lookup"><span data-stu-id="5f1c9-111">Which users you want to give permissions to create or edit topics in the topic center</span></span>
- <span data-ttu-id="5f1c9-112">Nome da assegnare al centro argomenti</span><span class="sxs-lookup"><span data-stu-id="5f1c9-112">What name you want to give your topic center</span></span>

<span data-ttu-id="5f1c9-113">La sicurezza e la privacy dei dati vengono rispettate e le esperienze degli argomenti non concedono agli utenti l'accesso aggiuntivo ai file a cui non hanno diritti.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-113">Security and privacy of your data is respected, and topic experiences does not grant users additional access to files they don’t have rights to.</span></span> <span data-ttu-id="5f1c9-114">È consigliabile leggere anche [La sicurezza e la privacy](topic-experiences-security-privacy.md) di Microsoft Viva Topics nell'ambito del processo di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-114">We recommend you also read [Microsoft Viva Topics security and privacy](topic-experiences-security-privacy.md) as part of your planning process.</span></span>

<span data-ttu-id="5f1c9-115">Per saperne di più sulla tecnologia IA alla base di Viva Topics, leggi [Alessandria in Microsoft Viva Topics: dai big data alle grandi conoscenze.](https://www.microsoft.com/research/blog/alexandria-in-microsoft-viva-topics-from-big-data-to-big-knowledge)</span><span class="sxs-lookup"><span data-stu-id="5f1c9-115">To learn more about the AI technology behind Viva Topics, read [Alexandria in Microsoft Viva Topics: from big data to big knowledge](https://www.microsoft.com/research/blog/alexandria-in-microsoft-viva-topics-from-big-data-to-big-knowledge).</span></span>

## <a name="requirements"></a><span data-ttu-id="5f1c9-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5f1c9-116">Requirements</span></span>

<span data-ttu-id="5f1c9-117">Devi essere [sottoscritto a Viva Topics](https://www.microsoft.com/microsoft-viva/topics) ed essere un amministratore globale o SharePoint amministratore per accedere all'interfaccia di amministrazione di Microsoft 365 e configurare Gli argomenti.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-117">You must be [subscribed to Viva Topics](https://www.microsoft.com/microsoft-viva/topics) and be a global administrator or SharePoint administrator to access the Microsoft 365 admin center and set up Topics.</span></span>

<span data-ttu-id="5f1c9-118">Tutti gli utenti che useranno Gli argomenti richiedono una **licenza esperienze di** argomento.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-118">All users who are going to use Topics require a **Topic Experiences** license.</span></span> <span data-ttu-id="5f1c9-119">L'assegnazione delle licenze è trattata in [Set up Microsoft Viva Topics.](set-up-topic-experiences.md)</span><span class="sxs-lookup"><span data-stu-id="5f1c9-119">Assigning licenses is covered in [Set up Microsoft Viva Topics](set-up-topic-experiences.md).</span></span>

## <a name="topic-discovery"></a><span data-ttu-id="5f1c9-120">Individuazione argomenti</span><span class="sxs-lookup"><span data-stu-id="5f1c9-120">Topic discovery</span></span>

<span data-ttu-id="5f1c9-121">Le impostazioni di individuazione degli argomenti specificano i siti di SharePoint da usare come origini per gli argomenti.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-121">The topic discovery settings specify which SharePoint sites are used as sources for topics.</span></span> <span data-ttu-id="5f1c9-122">È possibile scegliere di includere tutti i siti di SharePoint, uno specifico elenco di siti o nessun sito.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-122">You can choose to include all SharePoint sites, a specific list of sites, or no sites.</span></span> <span data-ttu-id="5f1c9-123">È consigliabile scegliere tutti i siti in modo che le esperienze degli argomenti possano individuare un gran numero di argomenti importanti per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-123">We recommend that you choose all sites so that topic experiences can discover a large number of good topics for your users.</span></span>

<span data-ttu-id="5f1c9-124">Quando si configurano gli argomenti è possibile scegliere uno dei seguenti comandi:</span><span class="sxs-lookup"><span data-stu-id="5f1c9-124">When you set up Topics, you can choose from the following options:</span></span>

- <span data-ttu-id="5f1c9-125">**Tutti i siti**: tutti i siti di SharePoint nell’organizzazione.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-125">**All sites**: All SharePoint sites in your organization.</span></span> <span data-ttu-id="5f1c9-126">Sono inclusi i siti correnti e futuri.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-126">This includes current and future sites.</span></span>
- <span data-ttu-id="5f1c9-127">**Tutti, ad eccezione dei siti specificati.**: tutti i siti ad eccezione di quelli specificati.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-127">**All, except selected sites**: All sites except for the ones you specify.</span></span> <span data-ttu-id="5f1c9-128">I siti creati in futuro verranno inclusi come origini per l'individuazione degli argomenti.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-128">Sites created in future will be included as sources for topic discovery.</span></span> 
- <span data-ttu-id="5f1c9-129">**Solo siti selezionati:** solo i siti specificati.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-129">**Only selected sites**: Only the sites that you specify.</span></span> <span data-ttu-id="5f1c9-130">I siti creati in futuro non verranno inclusi come origini per l’individuazione di argomenti.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-130">Sites created in the future will not be included as sources for topic discovery.</span></span>
- <span data-ttu-id="5f1c9-131">**Nessun sito**: non includere siti di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-131">**No sites**: Do not include any SharePoint sites.</span></span>

<span data-ttu-id="5f1c9-132">Se si sceglie **Tutti,** ad eccezione dei siti selezionati o Solo i siti **selezionati,** è possibile caricare un file .csv con un elenco di siti.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-132">If you choose either **All, except selected sites** or **Only selected sites**, you can upload a .csv file with a list of sites.</span></span> <span data-ttu-id="5f1c9-133">Queste opzioni sono utili se si sta eseguendo un progetto pilota e si desidera includere un numero limitato di siti da avviare.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-133">These options are useful if you're doing a pilot and you want to include a limited number of sites to start.</span></span>

<span data-ttu-id="5f1c9-134">Puoi copiare il modello .csv seguente:</span><span class="sxs-lookup"><span data-stu-id="5f1c9-134">You can copy the .csv template below:</span></span>

``` csv
Site name,URL
```

<span data-ttu-id="5f1c9-135">Non è consigliabile scegliere **Nessun sito perché** impedisce la creazione o l'aggiornamento automatico degli argomenti.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-135">We don't recommend choosing **No sites** because it prevents topics from being automatically created or updated.</span></span> <span data-ttu-id="5f1c9-136">È tuttavia possibile scegliere questa opzione se si desidera configurare Gli argomenti e quindi aggiungere siti in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-136">However, you can choose this option if you want to set up Topics and then add sites later.</span></span>

<span data-ttu-id="5f1c9-137">È consigliabile creare un processo per consentire agli utenti o ai knowledge manager di richiedere la rimozione di singoli siti dall'individuazione degli argomenti, se necessario nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-137">We recommend you create a process for users or knowledge managers to request individual sites be removed from topic discovery if needed in your organization.</span></span>

### <a name="multi-geo"></a><span data-ttu-id="5f1c9-138">Multi-Geo</span><span class="sxs-lookup"><span data-stu-id="5f1c9-138">Multi-geo</span></span>

<span data-ttu-id="5f1c9-139">Se l'organizzazione ha distribuito [Microsoft 365 Multi-Geo,](/microsoft-365/enterprise/microsoft-365-multi-geo)viene eseguito il provisioning del Centro argomenti nella posizione centrale e solo i siti di SharePoint nella posizione centrale sono disponibili per l'utilizzo come origini per gli argomenti.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-139">If your organization has deployed [Microsoft 365 Multi-Geo](/microsoft-365/enterprise/microsoft-365-multi-geo), the topic center is provisioned in the central location and only SharePoint sites in the central location are available to use as sources for topics.</span></span> <span data-ttu-id="5f1c9-140">Se si seleziona **Tutti i siti,** Viva Topics utilizzerà tutti i siti nella posizione centrale.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-140">(If you select **All sites**, Viva Topics will use all site in the central location.)</span></span>

<span data-ttu-id="5f1c9-141">Tutte le operazioni di elaborazione e archiviazione del contenuto vengono eseguite nella posizione centrale.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-141">All processing and storage of content is done in the central location.</span></span>

## <a name="user-permissions"></a><span data-ttu-id="5f1c9-142">Autorizzazioni utenti</span><span class="sxs-lookup"><span data-stu-id="5f1c9-142">User permissions</span></span>

<span data-ttu-id="5f1c9-143">Le autorizzazioni utente specificate determinano quali persone dell'organizzazione interagiscono con gli argomenti e cosa possono fare.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-143">The user permissions that you specify determine which people in your organization interact with topics and what they can do.</span></span>

> [!Note] 
> <span data-ttu-id="5f1c9-144">Al momento, Viva Topics non supporta la fornitura di licenze o autorizzazioni utente per gli utenti Guest (esterni).</span><span class="sxs-lookup"><span data-stu-id="5f1c9-144">At this time, Viva Topics doesn't support providing licenses or user permissions for Guest (External) users.</span></span> 

<span data-ttu-id="5f1c9-145">*Gestisci argomenti*</span><span class="sxs-lookup"><span data-stu-id="5f1c9-145">*Manage topics*</span></span>

<span data-ttu-id="5f1c9-146">I knowledge manager supervisionano la qualità delle informazioni, il modo in cui è strutturata e altre procedure consigliate nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-146">Knowledge managers oversee the quality of information, how its structured, and other best practices in your organization.</span></span> <span data-ttu-id="5f1c9-147">Possono confermare e rifiutare gli argomenti.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-147">They can confirm and reject topics.</span></span>

<span data-ttu-id="5f1c9-148">Sebbene sia possibile specificare singoli responsabili degli argomenti, è consigliabile creare un gruppo di sicurezza (o utilizzarne uno esistente) contenente le persone che si desidera siano responsabili della conoscenza.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-148">While you can specify individual topic managers, we recommend that you create a security group (or use an existing one) that contains the people who you want to be knowledge managers.</span></span> <span data-ttu-id="5f1c9-149">È possibile specificare questo gruppo di sicurezza durante il processo di installazione.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-149">You can specify this security group during the setup process.</span></span>

<span data-ttu-id="5f1c9-150">*Creare e modificare argomenti*</span><span class="sxs-lookup"><span data-stu-id="5f1c9-150">*Create and edit topics*</span></span>

<span data-ttu-id="5f1c9-151">I collaboratori degli argomenti sono i campioni e gli esperti in materia nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-151">Topic contributors are the champions and subject matter experts in your organization.</span></span> <span data-ttu-id="5f1c9-152">Possono creare e modificare argomenti.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-152">They can create and edit topics.</span></span> 

<span data-ttu-id="5f1c9-153">È consigliabile consentire a tutti gli utenti dell'organizzazione di creare e modificare argomenti perché le esperienze degli argomenti funzionano al meglio quando tutti gli utenti possono condividere informazioni.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-153">We recommend that you allow everyone in your organization to create and edit topics because topic experiences work best when all users can share information.</span></span>

<span data-ttu-id="5f1c9-154">Se si desidera limitare la creazione e la modifica di argomenti a utenti o gruppi specifici, creare un gruppo di sicurezza per loro e specificarlo durante il processo di installazione.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-154">If you want to limit creating and editing topics to specific people or groups, create a security group for them and specify it during the setup process.</span></span>

<span data-ttu-id="5f1c9-155">È possibile scegliere di non consentire a nessuno di contribuire agli argomenti, tuttavia non è consigliabile.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-155">You can choose to not allow anyone to contribute to topics, however this is not recommended.</span></span> <span data-ttu-id="5f1c9-156">Se si sceglie questa opzione, i knowledge manager potranno comunque modificare e creare argomenti.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-156">Knowledge managers will still be able to edit and create topics if you choose this option.</span></span>

<span data-ttu-id="5f1c9-157">*Visualizzatori dell'argomento*</span><span class="sxs-lookup"><span data-stu-id="5f1c9-157">*Topic viewers*</span></span>

<span data-ttu-id="5f1c9-158">I visualizzatori di argomenti possono visualizzare informazioni sulle pagine degli argomenti, nei risultati della ricerca e quando gli argomenti vengono evidenziati nel contenuto come SharePoint pagine.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-158">Topic viewers can see information on topic pages, in search results and when topics are highlighted in the content like SharePoint pages.</span></span> <span data-ttu-id="5f1c9-159">Gli utenti possono visualizzare gli argomenti individuati solo quando hanno accesso ai file e alle pagine in cui è stato individuato l'argomento.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-159">Users can only see discovered topics when they have access to the files and pages the topic was discovered in.</span></span>

<span data-ttu-id="5f1c9-160">Quando si configurano i visualizzatori di argomenti, è possibile scegliere tra:</span><span class="sxs-lookup"><span data-stu-id="5f1c9-160">When setting up topic viewers, you can choose from:</span></span>

- <span data-ttu-id="5f1c9-161">**Tutti gli utenti dell'organizzazione**</span><span class="sxs-lookup"><span data-stu-id="5f1c9-161">**Everyone in my organization**</span></span>
- <span data-ttu-id="5f1c9-162">**Solo utenti o gruppi di sicurezza selezionati**</span><span class="sxs-lookup"><span data-stu-id="5f1c9-162">**Only selected people or security groups**</span></span>
- <span data-ttu-id="5f1c9-163">**Nessuno**</span><span class="sxs-lookup"><span data-stu-id="5f1c9-163">**No one**</span></span>

<span data-ttu-id="5f1c9-164">Si consiglia **a Tutti gli** utenti dell'organizzazione, ma se si sta eseguendo un progetto pilota è consigliabile scegliere solo persone o gruppi di sicurezza selezionati.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-164">We recommend **Everyone in my organization**, but if you're doing a pilot you may want to choose only selected people or security groups.</span></span> <span data-ttu-id="5f1c9-165">È inoltre possibile scegliere **Nessuno** se si desidera configurare Gli argomenti, ma non consentire agli utenti di visualizzare gli argomenti.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-165">You can also choose **No one** if you want to set up Topics, but not allow people to see topics yet.</span></span> <span data-ttu-id="5f1c9-166">I knowledge manager avranno comunque accesso per consentire loro di visualizzare gli argomenti e di ottenere assistenza per la decisione di rendere gli argomenti ampiamente disponibili.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-166">(Knowledge managers will still have access to allow them view the topics and help with the decision to make Topics broadly available.)</span></span>

## <a name="knowledge-rules"></a><span data-ttu-id="5f1c9-167">Regole della knowledge base</span><span class="sxs-lookup"><span data-stu-id="5f1c9-167">Knowledge rules</span></span>

<span data-ttu-id="5f1c9-168">Gli amministratori possono escludere determinati argomenti dalle esperienze degli argomenti.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-168">As an administrator, you can exclude certain topics from topic experiences.</span></span> <span data-ttu-id="5f1c9-169">Ciò è utile se si desidera evitare che i dati sensibili appaiano negli argomenti.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-169">This is useful if you want to keep sensitive data from appearing in topics.</span></span> <span data-ttu-id="5f1c9-170">Anche se i knowledge manager possono escludere gli argomenti nel Centro argomenti, gli argomenti esclusi dall'amministratore non sono nemmeno visibili ai knowledge manager.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-170">While knowledge managers can exclude topics in the topic center, topics excluded by the administrator are not even visible to knowledge managers.</span></span> <span data-ttu-id="5f1c9-171">I responsabili della conoscenza possono anche rimuovere gli argomenti nel Centro argomenti dopo l'individuazione.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-171">(Knowledge managers can also remove topics in the topic center after discovery.)</span></span>

<span data-ttu-id="5f1c9-172">Se si desidera escludere gli argomenti a livello di amministratore, è necessario aggiungerli a un .csv file e caricare il file.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-172">If you want to exclude topics at the administrator level, you must add them to a .csv file and upload the file.</span></span> <span data-ttu-id="5f1c9-173">È possibile eseguire questa operazione durante l'installazione o in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-173">You can do this during setup or later.</span></span>

<span data-ttu-id="5f1c9-174">Il .csv file deve contenere i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="5f1c9-174">The .csv file must contain the following parameters:</span></span>

- <span data-ttu-id="5f1c9-175">**Nome**: digitare il nome dell’argomento da escludere.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-175">**Name**: Type the name of the topic you want to exclude.</span></span> <span data-ttu-id="5f1c9-176">È possibile eseguire questa operazione in due modi:</span><span class="sxs-lookup"><span data-stu-id="5f1c9-176">There are two ways to do this:</span></span>
- <span data-ttu-id="5f1c9-177">**MatchType-Exact/Partial**: Digitare se il nome immesso è un *tipo* di corrispondenza esatto *o* parziale.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-177">**MatchType-Exact/Partial**: Type whether the name you entered was an *exact* or *partial* match type.</span></span>
    - <span data-ttu-id="5f1c9-178">Corrispondenza esatta: è possibile includere il nome esatto o l'acronimo (ad esempio, *Contoso* o *ATL).*</span><span class="sxs-lookup"><span data-stu-id="5f1c9-178">Exact match: You can include the exact name or acronym (for example, *Contoso* or *ATL*).</span></span>
    - <span data-ttu-id="5f1c9-179">Corrispondenza parziale: è possibile escludere tutti gli argomenti che includono una parola specifica.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-179">Partial match: You can exclude all topics that have a specific word in it.</span></span>  <span data-ttu-id="5f1c9-180">Ad esempio, *arco* escluderà tutti gli argomenti con la parola arco *al* suo interno, ad esempio Cerchio *arco,* *Saldatura* arco di plasma o *Arco di formazione.* Si noti che non verranno esclusi gli argomenti in cui il testo è incluso come parte di una parola, ad esempio *Architettura*.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-180">For example, *arc* will exclude all topics with the word *arc* in it, such as *Arc circle*, *Plasma arc welding*, or *Training arc*. Note that it will not exclude topics in which the text is included as part of a word, such as *Architecture*.</span></span>
- <span data-ttu-id="5f1c9-181">**Sta per (facoltativo):**(noto anche come espansione *)* Se si desidera escludere un acronimo, digitare le parole che l'acronimo sta per.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-181">**Stands for (optional)**: (Also known as *expansion*) If you want to exclude an acronym, type the words the acronym stands for.</span></span>

    ![Escludere gli argomenti nel modello CSV](../media/exclude-topics-csv.png) 

<span data-ttu-id="5f1c9-183">È possibile copiare il modello csv seguente:</span><span class="sxs-lookup"><span data-stu-id="5f1c9-183">You can copy the csv template below:</span></span>

``` csv
Name (required),Expansion,MatchType- Exact/Partial (required)
```

## <a name="administration"></a><span data-ttu-id="5f1c9-184">Amministrazione</span><span class="sxs-lookup"><span data-stu-id="5f1c9-184">Administration</span></span>

<span data-ttu-id="5f1c9-185">Quando si configurano gli argomenti, come parte del processo di installazione, viene creato automaticamente un centro argomenti.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-185">When you set up Topics, as part of the setup process, a topic center is automatically created.</span></span> <span data-ttu-id="5f1c9-186">Pensa a cosa vuoi assegnare un nome al Centro argomenti e a cosa vuoi che sia l'URL.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-186">Think about what you want to name the topic center and what you want the URL to be.</span></span> <span data-ttu-id="5f1c9-187">È possibile impostare sia il nome che l'URL come parte del processo di installazione ed è possibile modificare il nome (ma non l'URL) in un secondo momento nell'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-187">You can set both the name and URL as part of the setup process, and you can change the name (but not URL) later in the Microsoft 365 admin center.</span></span> <span data-ttu-id="5f1c9-188">È possibile avere un solo centro argomenti.</span><span class="sxs-lookup"><span data-stu-id="5f1c9-188">You can only have one topic center.</span></span>

## <a name="setup-checklist"></a><span data-ttu-id="5f1c9-189">Elenco di controllo per l'installazione</span><span class="sxs-lookup"><span data-stu-id="5f1c9-189">Setup checklist</span></span>

<span data-ttu-id="5f1c9-190">Quando si configurano le esperienze degli argomenti, durante l'installazione guidata saranno necessari gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="5f1c9-190">When you set up topic experiences, you'll need the following items as you go through the setup wizard:</span></span>

> [!div class="checklist"]
> * <span data-ttu-id="5f1c9-191">Elenco dei siti da includere o escludere se non si includono tutti i siti per l'individuazione di argomenti</span><span class="sxs-lookup"><span data-stu-id="5f1c9-191">List of sites to include or exclude if not including all sites for topic discovery</span></span>
> * <span data-ttu-id="5f1c9-192">Gruppo di sicurezza per visualizzatori di argomenti se non si consente a tutti gli utenti di visualizzare gli argomenti</span><span class="sxs-lookup"><span data-stu-id="5f1c9-192">Security group for topic viewers if not allowing all users to view topics</span></span>
> * <span data-ttu-id="5f1c9-193">Gruppo di sicurezza per collaboratori di argomenti se non si consente a tutti gli utenti di creare e modificare gli argomenti</span><span class="sxs-lookup"><span data-stu-id="5f1c9-193">Security group for topic contributors if not allowing all users to create and edit topics</span></span>
> * <span data-ttu-id="5f1c9-194">Gruppo di sicurezza per responsabili delle informazioni di argomenti se non si consente a tutti gli utenti di gestire gli argomenti</span><span class="sxs-lookup"><span data-stu-id="5f1c9-194">Security group for topic knowledge managers if not allowing all users to manage topics</span></span>
> * <span data-ttu-id="5f1c9-195">Elenco di argomenti sensibili da escludere dall'individuazione degli argomenti</span><span class="sxs-lookup"><span data-stu-id="5f1c9-195">List of sensitive topics to exclude from topic discovery</span></span>
> * <span data-ttu-id="5f1c9-196">Nome del sito Centro argomenti</span><span class="sxs-lookup"><span data-stu-id="5f1c9-196">A name for your topic center site</span></span>

## <a name="see-also"></a><span data-ttu-id="5f1c9-197">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5f1c9-197">See also</span></span>

[<span data-ttu-id="5f1c9-198">Configurare le esperienze dell'argomento</span><span class="sxs-lookup"><span data-stu-id="5f1c9-198">Set up topic experiences</span></span>](set-up-topic-experiences.md)

[<span data-ttu-id="5f1c9-199">Gestire l'individuazione degli argomenti in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5f1c9-199">Manage topic discovery in Microsoft 365</span></span>](topic-experiences-discovery.md)

[<span data-ttu-id="5f1c9-200">Gestire la visibilità degli argomenti in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5f1c9-200">Manage topic visibility in Microsoft 365</span></span>](topic-experiences-knowledge-rules.md)

[<span data-ttu-id="5f1c9-201">Gestire le autorizzazioni per gli argomenti in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5f1c9-201">Manage topic permissions in Microsoft 365</span></span>](topic-experiences-user-permissions.md)

[<span data-ttu-id="5f1c9-202">Modificare il nome del centro argomenti in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5f1c9-202">Change the name of the topic center in Microsoft 365</span></span>](topic-experiences-administration.md)
