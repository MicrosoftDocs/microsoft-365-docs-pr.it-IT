---
title: Abilitare la funzionalità di analisi Antivirus Microsoft Defender periodico limitata
description: L'analisi periodica limitata consente di Antivirus Microsoft Defender oltre agli altri provider AV installati
keywords: lps, limited, periodic, scan, scanning, compatibility, 3rd party, other av, disable
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: ad49b08e687f4ba389616542bd607d4140e91132
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926692"
---
# <a name="use-limited-periodic-scanning-in-microsoft-defender-antivirus"></a><span data-ttu-id="35e83-104">Usare analisi periodiche limitate in Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="35e83-104">Use limited periodic scanning in Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="35e83-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="35e83-105">**Applies to:**</span></span>

- [<span data-ttu-id="35e83-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="35e83-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="35e83-107">L'analisi periodica limitata è un tipo speciale di rilevamento e correzione delle minacce che può essere abilitato quando è stato installato un altro prodotto antivirus in un Windows 10 dispositivo.</span><span class="sxs-lookup"><span data-stu-id="35e83-107">Limited periodic scanning is a special type of threat detection and remediation that can be enabled when you have installed another antivirus product on a Windows 10 device.</span></span>

<span data-ttu-id="35e83-108">Può essere abilitato solo in determinate situazioni.</span><span class="sxs-lookup"><span data-stu-id="35e83-108">It can only be enabled in certain situations.</span></span> <span data-ttu-id="35e83-109">Per ulteriori informazioni sull'analisi periodica limitata e sul Antivirus Microsoft Defender con altri prodotti antivirus, vedere [Antivirus Microsoft Defender compatibilità.](microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="35e83-109">For more information about limited periodic scanning and how Microsoft Defender Antivirus works with other antivirus products, see [Microsoft Defender Antivirus compatibility](microsoft-defender-antivirus-compatibility.md).</span></span>

<span data-ttu-id="35e83-110">**Microsoft non consiglia di utilizzare questa funzionalità in ambienti aziendali. Si tratta di una funzionalità destinata principalmente agli utenti.**</span><span class="sxs-lookup"><span data-stu-id="35e83-110">**Microsoft does not recommend using this feature in enterprise environments. This is a feature primarily intended for consumers.**</span></span> <span data-ttu-id="35e83-111">Questa funzionalità usa solo un sottoinsieme limitato delle funzionalità Antivirus Microsoft Defender per rilevare malware e non sarà in grado di rilevare la maggior parte del malware e software potenzialmente indesiderato.</span><span class="sxs-lookup"><span data-stu-id="35e83-111">This feature only uses a limited subset of the Microsoft Defender Antivirus capabilities to detect malware, and will not be able to detect most malware and potentially unwanted software.</span></span> <span data-ttu-id="35e83-112">Inoltre, le funzionalità di gestione e creazione di report saranno limitate.</span><span class="sxs-lookup"><span data-stu-id="35e83-112">Also, management and reporting capabilities will be limited.</span></span> <span data-ttu-id="35e83-113">Microsoft consiglia alle aziende di scegliere la soluzione antivirus principale e usarla esclusivamente.</span><span class="sxs-lookup"><span data-stu-id="35e83-113">Microsoft recommends enterprises choose their primary antivirus solution and use it exclusively.</span></span>

## <a name="how-to-enable-limited-periodic-scanning"></a><span data-ttu-id="35e83-114">Come abilitare l'analisi periodica limitata</span><span class="sxs-lookup"><span data-stu-id="35e83-114">How to enable limited periodic scanning</span></span>

<span data-ttu-id="35e83-115">Per impostazione predefinita, Antivirus Microsoft Defender si abilita su un dispositivo Windows 10 se non è installato alcun altro prodotto antivirus o se l'altro prodotto non è aggiornato, è scaduto o non funziona correttamente.</span><span class="sxs-lookup"><span data-stu-id="35e83-115">By default, Microsoft Defender Antivirus will enable itself on a Windows 10 device if there is no other antivirus product installed, or if the other product is out-of-date, expired, or not working correctly.</span></span>

<span data-ttu-id="35e83-116">Se Antivirus Microsoft Defender è abilitato, verranno visualizzate le opzioni consuete per configurarlo nel dispositivo:</span><span class="sxs-lookup"><span data-stu-id="35e83-116">If Microsoft Defender Antivirus is enabled, the usual options will appear to configure it on that device:</span></span>

![Sicurezza di Windows app che mostra le opzioni di Microsoft Defender AV, incluse le opzioni di analisi, le impostazioni e le opzioni di aggiornamento](images/vtp-wdav.png)

<span data-ttu-id="35e83-118">Se un altro prodotto antivirus è installato e funziona correttamente, Antivirus Microsoft Defender si disabiliterà.</span><span class="sxs-lookup"><span data-stu-id="35e83-118">If another antivirus product is installed and working correctly, Microsoft Defender Antivirus will disable itself.</span></span> <span data-ttu-id="35e83-119">L Sicurezza di Windows app modificherà la sezione **Protezione** dalle minacce & virus per mostrare lo stato del prodotto AV e fornirà un collegamento alle opzioni di configurazione del prodotto.</span><span class="sxs-lookup"><span data-stu-id="35e83-119">The Windows Security app will change the **Virus & threat protection** section to show status about the AV product, and provide a link to the product's configuration options.</span></span>

<span data-ttu-id="35e83-120">Sotto qualsiasi prodotto AV di terze parti, un nuovo collegamento verrà visualizzato **come Antivirus Microsoft Defender opzioni**.</span><span class="sxs-lookup"><span data-stu-id="35e83-120">Underneath any third party AV products, a new link will appear as **Microsoft Defender Antivirus options**.</span></span> <span data-ttu-id="35e83-121">Facendo clic su questo collegamento verrà visualizzato l'interruttore che consente una scansione periodica limitata.</span><span class="sxs-lookup"><span data-stu-id="35e83-121">Clicking this link will expand to show the toggle that enables limited periodic scanning.</span></span> <span data-ttu-id="35e83-122">Si noti che l'opzione periodica limitata è un interruttore per abilitare o disabilitare l'analisi periodica.</span><span class="sxs-lookup"><span data-stu-id="35e83-122">Note that the limited periodic option is a toggle to enable or disable periodic scanning.</span></span> 

<span data-ttu-id="35e83-123">Facendo scorrere l'interruttore **su On** verranno mostrate le opzioni standard di Microsoft Defender AV sotto il prodotto AV di terze parti.</span><span class="sxs-lookup"><span data-stu-id="35e83-123">Sliding the switch to **On** will show the standard Microsoft Defender AV options underneath the third party AV product.</span></span> <span data-ttu-id="35e83-124">L'opzione di scansione periodica limitata verrà visualizzata nella parte inferiore della pagina.</span><span class="sxs-lookup"><span data-stu-id="35e83-124">The limited periodic scanning option will appear at the bottom of the page.</span></span>

## <a name="related-articles"></a><span data-ttu-id="35e83-125">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="35e83-125">Related articles</span></span>

- [<span data-ttu-id="35e83-126">Configurare la protezione comportamentale, euristica e in tempo reale</span><span class="sxs-lookup"><span data-stu-id="35e83-126">Configure behavioral, heuristic, and real-time protection</span></span>](configure-protection-features-microsoft-defender-antivirus.md)
- [<span data-ttu-id="35e83-127">Antivirus Microsoft Defender in Windows 10</span><span class="sxs-lookup"><span data-stu-id="35e83-127">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)