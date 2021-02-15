---
title: Controllo app
description: Come usare il controllo delle app e considerare attendibile le applicazioni
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
# <a name="app-control"></a><span data-ttu-id="0c3a1-104">Controllo app</span><span class="sxs-lookup"><span data-stu-id="0c3a1-104">App control</span></span>

<span data-ttu-id="0c3a1-105">Il controllo delle app è una procedura di sicurezza facoltativa in Microsoft Managed Desktop che limita l'esecuzione del codice nei dispositivi client.</span><span class="sxs-lookup"><span data-stu-id="0c3a1-105">App control is an optional security practice in Microsoft Managed Desktop that restricts the execution of code on client devices.</span></span> <span data-ttu-id="0c3a1-106">Questo controllo riduce il rischio di malware o script dannosi richiedendo l'esecuzione solo del codice firmato da un elenco di editori approvato dal cliente.</span><span class="sxs-lookup"><span data-stu-id="0c3a1-106">This control mitigates the risk of malware or malicious scripts by requiring that only code signed by a customer-approved list of publishers can run.</span></span> <span data-ttu-id="0c3a1-107">Questo controllo offre numerosi vantaggi in termini di sicurezza, ma mira principalmente a proteggere i dati e l'identità dagli exploit basati su client.</span><span class="sxs-lookup"><span data-stu-id="0c3a1-107">There are many security benefits from this control, but it primarily aims to protect data and identity from client-based exploits.</span></span>

<span data-ttu-id="0c3a1-108">Microsoft Managed Desktop semplifica la gestione dei criteri di controllo delle app creando criteri di base che consentono scenari di produttività di base.</span><span class="sxs-lookup"><span data-stu-id="0c3a1-108">Microsoft Managed Desktop simplifies the management of app control policies by creating a base policy that enables core productivity scenarios.</span></span> <span data-ttu-id="0c3a1-109">Puoi estendere l'attendibilità ad altri firmatari specifici delle app e degli script nel tuo ambiente.</span><span class="sxs-lookup"><span data-stu-id="0c3a1-109">You can extend trust to other signers that are specific to the apps and scripts in your environment.</span></span> 


<span data-ttu-id="0c3a1-110">Qualsiasi tecnologia di sicurezza richiede un equilibrio tra esperienza utente, sicurezza e costi.</span><span class="sxs-lookup"><span data-stu-id="0c3a1-110">Any security technology requires a balance among user experience, security, and cost.</span></span> <span data-ttu-id="0c3a1-111">Il controllo delle app riduce la minaccia di software dannoso nell'ambiente, ma esistono conseguenze per l'utente e ulteriori azioni per l'amministratore IT.</span><span class="sxs-lookup"><span data-stu-id="0c3a1-111">App control reduces the threat of malicious software in your environment, but there are consequences to the user and further actions for your IT administrator.</span></span>

<span data-ttu-id="0c3a1-112">**Sicurezza aggiuntiva:**</span><span class="sxs-lookup"><span data-stu-id="0c3a1-112">**Additional security:**</span></span>

<span data-ttu-id="0c3a1-113">L'esecuzione di app o script non attendibili dai criteri di controllo delle app viene bloccata nei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="0c3a1-113">Apps or scripts that are not trusted by the app control policy are blocked from running on devices.</span></span>

<span data-ttu-id="0c3a1-114">**Responsabilità aggiuntive:**</span><span class="sxs-lookup"><span data-stu-id="0c3a1-114">**Your additional responsibilities:**</span></span>

- <span data-ttu-id="0c3a1-115">Sei responsabile del test delle tue app per determinare se verrebbero bloccate dai criteri di controllo delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="0c3a1-115">You are responsible for testing your apps to identify whether they would be blocked by the application control policy.</span></span>
- <span data-ttu-id="0c3a1-116">Se un'app è (o verrebbe) bloccata, sei responsabile dell'identificazione dei dettagli del firmatario necessari e della richiesta di una modifica tramite il portale di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="0c3a1-116">If an app is (or would be) blocked, you are responsible for identifying the needed signer details and requesting a change through the Admin portal.</span></span>

<span data-ttu-id="0c3a1-117">**Responsabilità di Microsoft Managed Desktop:**</span><span class="sxs-lookup"><span data-stu-id="0c3a1-117">**Microsoft Managed Desktop responsibilities:**</span></span>

- <span data-ttu-id="0c3a1-118">Microsoft Managed Desktop mantiene i criteri di base che consentono prodotti Microsoft di base come App M365, Windows, Teams, OneDrive e così via.</span><span class="sxs-lookup"><span data-stu-id="0c3a1-118">Microsoft Managed Desktop maintains the base policy that enables core Microsoft products like M365 Apps, Windows, Teams, OneDrive, and so on.</span></span>
- <span data-ttu-id="0c3a1-119">Microsoft Managed Desktop inserisce i firmatari attendibili e distribuisce i criteri aggiornati nei dispositivi.</span><span class="sxs-lookup"><span data-stu-id="0c3a1-119">Microsoft Managed Desktop inserts your trusted signers and deploys the updated policy to your devices.</span></span>


## <a name="managing-trust-in-applications"></a><span data-ttu-id="0c3a1-120">Gestione dell'attendibilità nelle applicazioni</span><span class="sxs-lookup"><span data-stu-id="0c3a1-120">Managing trust in applications</span></span>

<span data-ttu-id="0c3a1-121">Microsoft Managed Desktop cura un criterio di base che considera attendibili i componenti principali delle tecnologie Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0c3a1-121">Microsoft Managed Desktop curates a base policy that trusts the core components of Microsoft technologies.</span></span> <span data-ttu-id="0c3a1-122">È quindi *possibile aggiungere* l'attendibilità per le proprie applicazioni e script informando Microsoft Managed Desktop di quali di essi si considera già attendibile.</span><span class="sxs-lookup"><span data-stu-id="0c3a1-122">You then *add* trust for your own applications and scripts by informing Microsoft Managed Desktop which of them you already trust.</span></span>

### <a name="base-policy"></a><span data-ttu-id="0c3a1-123">Criteri di base</span><span class="sxs-lookup"><span data-stu-id="0c3a1-123">Base policy</span></span>

<span data-ttu-id="0c3a1-124">Microsoft Managed Desktop, in collaborazione con esperti di sicurezza informatica Microsoft, crea e gestisce criteri standard che consentono la maggior parte delle app distribuite tramite Microsoft Intune, bloccando al contempo attività pericolose come la compilazione del codice o l'esecuzione di file non attendibili.</span><span class="sxs-lookup"><span data-stu-id="0c3a1-124">Microsoft Managed Desktop, in collaboration with Microsoft cybersecurity experts, creates, and maintains a standard policy that enables most apps deployed through Microsoft Intune while blocking dangerous activities like code compilation or execution of untrusted files.</span></span>

<span data-ttu-id="0c3a1-125">Il criterio di base adotta l'approccio seguente per limitare l'esecuzione del software:</span><span class="sxs-lookup"><span data-stu-id="0c3a1-125">The base policy takes the following approach to restricting software execution:</span></span>

- <span data-ttu-id="0c3a1-126">L'esecuzione dei file eseguiti dagli amministratori sarà consentita.</span><span class="sxs-lookup"><span data-stu-id="0c3a1-126">Files run by administrators will be allowed to run.</span></span>
- <span data-ttu-id="0c3a1-127">L'esecuzione dei file in *percorsi* non presenti in directory scrivibili dall'utente sarà consentita.</span><span class="sxs-lookup"><span data-stu-id="0c3a1-127">Files in locations that are *not* in user-writable directories will be allowed to run.</span></span>
- <span data-ttu-id="0c3a1-128">I file sono firmati da [un firmatario attendibile.](#signer-requests)</span><span class="sxs-lookup"><span data-stu-id="0c3a1-128">Files are signed by a [trusted signer](#signer-requests).</span></span>
- <span data-ttu-id="0c3a1-129">La maggior parte dei file firmati da Microsoft verrà eseguita, ma alcuni sono bloccati per evitare azioni ad alto rischio come la compilazione del codice.</span><span class="sxs-lookup"><span data-stu-id="0c3a1-129">Most files signed by Microsoft will run, however some are blocked to prevent high-risk actions like code compilation.</span></span>


<span data-ttu-id="0c3a1-130">Se un utente diverso da un amministratore potrebbe aver aggiunto un'app o uno script a un dispositivo (ovvero si trova in una directory scrivibile dall'utente), l'esecuzione non verrà consentita a meno che non sia già stata espressamente consentita da un amministratore.</span><span class="sxs-lookup"><span data-stu-id="0c3a1-130">If a user other than an administrator could have added an app or script to a device (that is, it's in a user-writable directory), we won't allow it to execute unless it has already been specifically allowed by an administrator.</span></span> <span data-ttu-id="0c3a1-131">Se un utente viene ingannato nel tentativo di installare malware, se una vulnerabilità in un'app viene eseguita tenta di installare malware o se un utente tenta intenzionalmente di eseguire un'app o uno script non autorizzato, l'esecuzione dei criteri verrà interrotta.</span><span class="sxs-lookup"><span data-stu-id="0c3a1-131">If a user is tricked into trying to install malware, if a vulnerability in an app the user runs attempts to install malware, or if a user intentionally tries to run an unauthorized app or script, our policy will stop execution.</span></span>

### <a name="signer-requests"></a><span data-ttu-id="0c3a1-132">Richieste firmatario</span><span class="sxs-lookup"><span data-stu-id="0c3a1-132">Signer requests</span></span>

<span data-ttu-id="0c3a1-133">L'utente ci informa delle app fornite da editori software di cui si considera attendibile l'utente, registrando una richiesta *di firmatario.*</span><span class="sxs-lookup"><span data-stu-id="0c3a1-133">You inform us of which apps are provided by software publishers you trust by filing a *signer request*.</span></span> <span data-ttu-id="0c3a1-134">In questo modo, aggiungiamo queste informazioni di attendibilità ai criteri di controllo delle applicazioni di base e consentiamo l'esecuzione nei dispositivi di qualsiasi software firmato con il certificato dell'autore.</span><span class="sxs-lookup"><span data-stu-id="0c3a1-134">By doing so, we add that trust information into the baseline application control policy and allow any software signed with that publisher's certificate to run on your devices.</span></span>

## <a name="audit-and-enforced-policies"></a><span data-ttu-id="0c3a1-135">Criteri di controllo e applicati</span><span class="sxs-lookup"><span data-stu-id="0c3a1-135">Audit and Enforced policies</span></span>

<span data-ttu-id="0c3a1-136">Microsoft Managed Desktop usa due criteri di Microsoft Intune per fornire il controllo delle app:</span><span class="sxs-lookup"><span data-stu-id="0c3a1-136">Microsoft Managed Desktop uses two Microsoft Intune policies to provide app control:</span></span>

### <a name="audit-policy"></a><span data-ttu-id="0c3a1-137">Criteri di controllo</span><span class="sxs-lookup"><span data-stu-id="0c3a1-137">Audit policy</span></span>
<span data-ttu-id="0c3a1-138">Questo criterio crea log per registrare se un'app o uno script verrebbe bloccato dal criterio Applicato.</span><span class="sxs-lookup"><span data-stu-id="0c3a1-138">This policy creates logs to record whether an app or script would be blocked by the Enforced policy.</span></span> <span data-ttu-id="0c3a1-139">I criteri di controllo non applicano regole di controllo delle app e sono destinati a scopi di test per determinare se un'applicazione richiederà un'esenzione dell'editore.</span><span class="sxs-lookup"><span data-stu-id="0c3a1-139">Audit policies don't enforce app control rules and are meant for testing purposes to identify whether an application will require a publisher exemption.</span></span> <span data-ttu-id="0c3a1-140">Registra gli avvisi (8003 o 8006 eventi) nel Visualizzatore eventi invece di bloccare l'esecuzione o l'installazione di app o script specificati.</span><span class="sxs-lookup"><span data-stu-id="0c3a1-140">It logs warnings (8003 or 8006 events) in Event Viewer instead of blocking the execution or installation of specified apps or script.</span></span>

### <a name="enforced-policy"></a><span data-ttu-id="0c3a1-141">Criteri applicati</span><span class="sxs-lookup"><span data-stu-id="0c3a1-141">Enforced policy</span></span>
<span data-ttu-id="0c3a1-142">Questo criterio blocca l'esecuzione di app e script non attendibili e crea log ogni volta che un'app o uno script viene bloccato.</span><span class="sxs-lookup"><span data-stu-id="0c3a1-142">This policy blocks untrusted apps and scripts from running and creates logs whenever an app or script is blocked.</span></span> <span data-ttu-id="0c3a1-143">I criteri applicati impediscono agli utenti standard di eseguire app o script archiviati in directory scrivibili dall'utente.</span><span class="sxs-lookup"><span data-stu-id="0c3a1-143">Enforced policies prevent standard users from executing apps or scripts stored in user-writable directories.</span></span>

<span data-ttu-id="0c3a1-144">Ai dispositivi nel gruppo Test è applicato un criterio di controllo in modo da poterli usare per verificare se eventuali applicazioni causeranno problemi.</span><span class="sxs-lookup"><span data-stu-id="0c3a1-144">Devices in the Test group have an Audit policy applied so that you can use them to validate whether any applications will cause issues.</span></span> <span data-ttu-id="0c3a1-145">Tutti gli altri gruppi (First, Fast e Broad) usano un criterio Applicato, in modo che gli utenti di tali gruppi non saranno in grado di eseguire app o script non attendibili.</span><span class="sxs-lookup"><span data-stu-id="0c3a1-145">All other groups (First, Fast, and Broad) use an Enforced policy, so users in those groups won't be able to run untrusted apps or scripts.</span></span>







