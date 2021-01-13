---
title: Controllo app
description: Come utilizzare il controllo delle app e la relazione di trust con le applicazioni
keywords: Microsoft Managed Desktop, Microsoft 365, servizi, documentazione
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 6f5cc923b5a18b1f45dd186e88228db8c3a891cc
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841304"
---
# <a name="app-control"></a><span data-ttu-id="6d5e3-104">Controllo app</span><span class="sxs-lookup"><span data-stu-id="6d5e3-104">App control</span></span>

<span data-ttu-id="6d5e3-105">App Control è una procedura di sicurezza facoltativa in Microsoft Managed Desktop che limita l'esecuzione del codice sui dispositivi client.</span><span class="sxs-lookup"><span data-stu-id="6d5e3-105">App control is an optional security practice in Microsoft Managed Desktop that restricts the execution of code on client devices.</span></span> <span data-ttu-id="6d5e3-106">Questo controllo consente di ridurre il rischio di malware o script dannosi richiedendo che sia possibile eseguire solo il codice firmato da un elenco di editori approvati dal cliente.</span><span class="sxs-lookup"><span data-stu-id="6d5e3-106">This control mitigates the risk of malware or malicious scripts by requiring that only code signed by a customer-approved list of publishers can run.</span></span> <span data-ttu-id="6d5e3-107">Esistono numerosi vantaggi per la sicurezza di questo controllo, ma si tratta principalmente di proteggere i dati e l'identità da exploit basati su client.</span><span class="sxs-lookup"><span data-stu-id="6d5e3-107">There are many security benefits from this control, but it primarily aims to protect data and identity from client-based exploits.</span></span>

<span data-ttu-id="6d5e3-108">Microsoft Managed Desktop semplifica la gestione dei criteri di controllo delle app creando un criterio di base che consente di creare scenari di produttività core.</span><span class="sxs-lookup"><span data-stu-id="6d5e3-108">Microsoft Managed Desktop simplifies the management of app control policies by creating a base policy that enables core productivity scenarios.</span></span> <span data-ttu-id="6d5e3-109">È possibile estendere la relazione di trust ad altri firmatari specifici delle app e degli script nell'ambiente in uso.</span><span class="sxs-lookup"><span data-stu-id="6d5e3-109">You can extend trust to other signers that are specific to the apps and scripts in your environment.</span></span> 


<span data-ttu-id="6d5e3-110">Qualsiasi tecnologia di sicurezza richiede un equilibrio tra esperienza utente, sicurezza e costo.</span><span class="sxs-lookup"><span data-stu-id="6d5e3-110">Any security technology requires a balance among user experience, security, and cost.</span></span> <span data-ttu-id="6d5e3-111">Il controllo app riduce la minaccia del software dannoso nell'ambiente, ma ci sono conseguenze per l'utente e altre azioni per l'amministratore IT.</span><span class="sxs-lookup"><span data-stu-id="6d5e3-111">App control reduces the threat of malicious software in your environment, but there are consequences to the user and further actions for your IT administrator.</span></span>

<span data-ttu-id="6d5e3-112">**Sicurezza aggiuntiva:**</span><span class="sxs-lookup"><span data-stu-id="6d5e3-112">**Additional security:**</span></span>

<span data-ttu-id="6d5e3-113">Le app o gli script che non sono considerati attendibili dai criteri di controllo dell'app sono bloccati dall'esecuzione nei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="6d5e3-113">Apps or scripts that are not trusted by the app control policy are blocked from running on devices.</span></span>

<span data-ttu-id="6d5e3-114">**Responsabilità aggiuntive:**</span><span class="sxs-lookup"><span data-stu-id="6d5e3-114">**Your additional responsibilities:**</span></span>

- <span data-ttu-id="6d5e3-115">L'utente è responsabile del test delle app per identificare se verrebbe bloccato dal criterio di controllo dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="6d5e3-115">You are responsible for testing your apps to identify whether they would be blocked by the application control policy.</span></span>
- <span data-ttu-id="6d5e3-116">Se un'app è (o verrebbe) bloccata, è responsabile dell'identificazione dei dettagli del firmatario necessari e della richiesta di una modifica tramite il portale di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="6d5e3-116">If an app is (or would be) blocked, you are responsible for identifying the needed signer details and requesting a change through the Admin portal.</span></span>

<span data-ttu-id="6d5e3-117">**Responsabilità di Microsoft Managed Desktop:**</span><span class="sxs-lookup"><span data-stu-id="6d5e3-117">**Microsoft Managed Desktop responsibilities:**</span></span>

- <span data-ttu-id="6d5e3-118">Microsoft Managed Desktop gestisce i criteri di base che consentono ai prodotti Microsoft principali come M365 Apps, Windows, teams, OneDrive e così via.</span><span class="sxs-lookup"><span data-stu-id="6d5e3-118">Microsoft Managed Desktop maintains the base policy that enables core Microsoft products like M365 Apps, Windows, Teams, OneDrive, and so on.</span></span>
- <span data-ttu-id="6d5e3-119">Microsoft Managed Desktop inserisce i propri firmatari attendibili e distribuisce i criteri aggiornati ai propri dispositivi.</span><span class="sxs-lookup"><span data-stu-id="6d5e3-119">Microsoft Managed Desktop inserts your trusted signers and deploys the updated policy to your devices.</span></span>


## <a name="managing-trust-in-applications"></a><span data-ttu-id="6d5e3-120">Gestione della relazione di trust nelle applicazioni</span><span class="sxs-lookup"><span data-stu-id="6d5e3-120">Managing trust in applications</span></span>

<span data-ttu-id="6d5e3-121">Microsoft Managed Desktop gestisce un criterio di base che considera attendibili i componenti principali delle tecnologie Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6d5e3-121">Microsoft Managed Desktop curates a base policy that trusts the core components of Microsoft technologies.</span></span> <span data-ttu-id="6d5e3-122">È quindi possibile *aggiungere* attendibilità per le proprie applicazioni e gli script informando Microsoft Managed Desktop di cui si ha già fiducia.</span><span class="sxs-lookup"><span data-stu-id="6d5e3-122">You then *add* trust for your own applications and scripts by informing Microsoft Managed Desktop which of them you already trust.</span></span>

### <a name="base-policy"></a><span data-ttu-id="6d5e3-123">Criteri di base</span><span class="sxs-lookup"><span data-stu-id="6d5e3-123">Base policy</span></span>

<span data-ttu-id="6d5e3-124">Microsoft Managed Desktop, in collaborazione con esperti di Microsoft Cybersecurity, crea e gestisce un criterio standard che consente la maggior parte delle app distribuite tramite Microsoft Intune durante il blocco di attività pericolose come la compilazione del codice o l'esecuzione di file non attendibili.</span><span class="sxs-lookup"><span data-stu-id="6d5e3-124">Microsoft Managed Desktop, in collaboration with Microsoft cybersecurity experts, creates, and maintains a standard policy that enables most apps deployed through Microsoft Intune while blocking dangerous activities like code compilation or execution of untrusted files.</span></span>

<span data-ttu-id="6d5e3-125">Il criterio di base assume il seguente approccio per limitare l'esecuzione del software:</span><span class="sxs-lookup"><span data-stu-id="6d5e3-125">The base policy takes the following approach to restricting software execution:</span></span>

- <span data-ttu-id="6d5e3-126">I file eseguiti dagli amministratori saranno autorizzati a essere eseguiti.</span><span class="sxs-lookup"><span data-stu-id="6d5e3-126">Files run by administrators will be allowed to run.</span></span>
- <span data-ttu-id="6d5e3-127">I file in posizioni *non* presenti nelle directory scrivibili dall'utente saranno autorizzati all'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="6d5e3-127">Files in locations that are *not* in user-writable directories will be allowed to run.</span></span>
- <span data-ttu-id="6d5e3-128">I file sono firmati da un [firmatario attendibile](#signer-requests).</span><span class="sxs-lookup"><span data-stu-id="6d5e3-128">Files are signed by a [trusted signer](#signer-requests).</span></span>
- <span data-ttu-id="6d5e3-129">La maggior parte dei file firmati da Microsoft verrà eseguita, ma alcuni sono bloccati per impedire azioni ad alto rischio come la compilazione del codice.</span><span class="sxs-lookup"><span data-stu-id="6d5e3-129">Most files signed by Microsoft will run, however some are blocked to prevent high-risk actions like code compilation.</span></span>


<span data-ttu-id="6d5e3-130">Se un utente diverso da un amministratore può aver aggiunto un'app o uno script a un dispositivo (ovvero si trova in una directory scrivibile dall'utente), non è possibile eseguirne l'esecuzione, a meno che non sia stato già esplicitamente consentito da un amministratore.</span><span class="sxs-lookup"><span data-stu-id="6d5e3-130">If a user other than an administrator could have added an app or script to a device (that is, it's in a user-writable directory), we won't allow it to execute unless it has already been specifically allowed by an administrator.</span></span> <span data-ttu-id="6d5e3-131">Se un utente è indotto a tentare di installare malware, se una vulnerabilità in un'app che l'utente esegue tenta di installare malware o se un utente tenta intenzionalmente di eseguire un'applicazione o uno script non autorizzato, il criterio interrompe l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="6d5e3-131">If a user is tricked into trying to install malware, if a vulnerability in an app the user runs attempts to install malware, or if a user intentionally tries to run an unauthorized app or script, our policy will stop execution.</span></span>

### <a name="signer-requests"></a><span data-ttu-id="6d5e3-132">Richieste del firmatario</span><span class="sxs-lookup"><span data-stu-id="6d5e3-132">Signer requests</span></span>

<span data-ttu-id="6d5e3-133">Informazioni su quali app sono fornite dai publisher di software di cui si ha fiducia archiviando una *richiesta di firmatario*.</span><span class="sxs-lookup"><span data-stu-id="6d5e3-133">You inform us of which apps are provided by software publishers you trust by filing a *signer request*.</span></span> <span data-ttu-id="6d5e3-134">In questo modo, si aggiungono le informazioni di attendibilità nel criterio di controllo dell'applicazione di base e si consente a qualsiasi software firmato con il certificato di tale editore di essere eseguito sui dispositivi.</span><span class="sxs-lookup"><span data-stu-id="6d5e3-134">By doing so, we add that trust information into the baseline application control policy and allow any software signed with that publisher's certificate to run on your devices.</span></span>

## <a name="audit-and-enforced-policies"></a><span data-ttu-id="6d5e3-135">Criteri di controllo e applicati</span><span class="sxs-lookup"><span data-stu-id="6d5e3-135">Audit and Enforced policies</span></span>

<span data-ttu-id="6d5e3-136">Microsoft Managed Desktop utilizza due criteri di Microsoft Intune per fornire il controllo app:</span><span class="sxs-lookup"><span data-stu-id="6d5e3-136">Microsoft Managed Desktop uses two Microsoft Intune policies to provide app control:</span></span>

### <a name="audit-policy"></a><span data-ttu-id="6d5e3-137">Criteri di controllo</span><span class="sxs-lookup"><span data-stu-id="6d5e3-137">Audit policy</span></span>
<span data-ttu-id="6d5e3-138">Questo criterio consente di creare registri per registrare se un'app o uno script verrebbe bloccato dal criterio applicato.</span><span class="sxs-lookup"><span data-stu-id="6d5e3-138">This policy creates logs to record whether an app or script would be blocked by the Enforced policy.</span></span> <span data-ttu-id="6d5e3-139">I criteri di controllo non applicano le regole per i controlli delle app e sono destinati ai test per identificare se un'applicazione richiede un'esenzione dall'editore.</span><span class="sxs-lookup"><span data-stu-id="6d5e3-139">Audit policies don't enforce app control rules and are meant for testing purposes to identify whether an application will require a publisher exemption.</span></span> <span data-ttu-id="6d5e3-140">Registra gli avvisi (8003 o 8006) nel Visualizzatore eventi invece di bloccare l'esecuzione o l'installazione delle app o degli script specificati.</span><span class="sxs-lookup"><span data-stu-id="6d5e3-140">It logs warnings (8003 or 8006 events) in Event Viewer instead of blocking the execution or installation of specified apps or script.</span></span>

### <a name="enforced-policy"></a><span data-ttu-id="6d5e3-141">Criteri applicati</span><span class="sxs-lookup"><span data-stu-id="6d5e3-141">Enforced policy</span></span>
<span data-ttu-id="6d5e3-142">Questo criterio blocca le app e gli script non attendibili dall'esecuzione e crea registri ogni volta che un'app o uno script è bloccato.</span><span class="sxs-lookup"><span data-stu-id="6d5e3-142">This policy blocks untrusted apps and scripts from running and creates logs whenever an app or script is blocked.</span></span> <span data-ttu-id="6d5e3-143">I criteri applicati impediscono agli utenti standard di eseguire le app o gli script archiviati nelle directory scrivibili dall'utente.</span><span class="sxs-lookup"><span data-stu-id="6d5e3-143">Enforced policies prevent standard users from executing apps or scripts stored in user-writable directories.</span></span>

<span data-ttu-id="6d5e3-144">I dispositivi del gruppo di test dispongono di un criterio di controllo applicato in modo che sia possibile utilizzarli per convalidare se qualsiasi applicazione provocherà problemi.</span><span class="sxs-lookup"><span data-stu-id="6d5e3-144">Devices in the Test group have an Audit policy applied so that you can use them to validate whether any applications will cause issues.</span></span> <span data-ttu-id="6d5e3-145">Tutti gli altri gruppi (First, Fast e Broad) utilizzano un criterio applicato, in modo che gli utenti di tali gruppi non siano in grado di eseguire le app o gli script non attendibili.</span><span class="sxs-lookup"><span data-stu-id="6d5e3-145">All other groups (First, Fast, and Broad) use an Enforced policy, so users in those groups won't be able to run untrusted apps or scripts.</span></span>







