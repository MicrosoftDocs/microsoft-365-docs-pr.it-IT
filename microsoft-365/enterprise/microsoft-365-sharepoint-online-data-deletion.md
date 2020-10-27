---
title: Eliminazione dei dati di Microsoft 365 SharePoint Online
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
f1.keywords:
- NOCSH
description: Informazioni su come funziona l'eliminazione dei dati in SharePoint Online, ad esempio la posizione in cui è archiviato il contenuto eliminato e per quanto tempo.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 888ee807e6cd4ddc435c1df86a63502a617d6cb8
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769043"
---
# <a name="sharepoint-online-data-deletion-in-microsoft-365"></a><span data-ttu-id="f86b3-103">Eliminazione dei dati di SharePoint online in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f86b3-103">SharePoint Online Data Deletion in Microsoft 365</span></span>

<span data-ttu-id="f86b3-104">SharePoint Online archivia gli oggetti come codice astratto all'interno dei database dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f86b3-104">SharePoint Online stores objects as abstracted code within application databases.</span></span> <span data-ttu-id="f86b3-105">Quando un utente carica un file in SharePoint Online, tale file viene disassemblato e convertito in codice dell'applicazione e archiviato in più tabelle tra più database.</span><span class="sxs-lookup"><span data-stu-id="f86b3-105">When a user uploads a file to SharePoint Online, that file is disassembled and translated into application code and stored in multiple tables across multiple databases.</span></span> <span data-ttu-id="f86b3-106">In SharePoint Online, tutto il contenuto del caricamento di un cliente è suddiviso in blocchi, crittografato (con una o più chiavi AES 256 bit) e distribuito in tutto il centro dati.</span><span class="sxs-lookup"><span data-stu-id="f86b3-106">In SharePoint Online, all content that a customer uploads is broken into chunks, encrypted (with one or more AES 256-bit keys), and distributed across the datacenter.</span></span> 

<span data-ttu-id="f86b3-107">In SharePoint Online, gli elementi vengono conservati per 93 giorni dal momento in cui vengono eliminati dal percorso originale.</span><span class="sxs-lookup"><span data-stu-id="f86b3-107">In SharePoint Online, items are retained for 93 days from the time you delete them from their original location.</span></span> <span data-ttu-id="f86b3-108">Rimangono nel cestino del sito per tutto il tempo, a meno che qualcuno non li elimini o svuoti quel cestino.</span><span class="sxs-lookup"><span data-stu-id="f86b3-108">They stay in the site Recycle Bin the entire time, unless someone deletes them from there or empties that Recycle Bin.</span></span> <span data-ttu-id="f86b3-109">In tal caso, gli elementi passano al cestino della raccolta siti, in cui restano per il resto dei 93 giorni.</span><span class="sxs-lookup"><span data-stu-id="f86b3-109">In that case, the items go to the site collection Recycle Bin, where they stay for the remainder of the 93 days.</span></span> <span data-ttu-id="f86b3-110">Per informazioni su come ripristinare gli elementi eliminati, vedere [ripristinare gli elementi nel cestino di un sito di SharePoint](https://support.office.com/article/6df466b6-55f2-4898-8d6e-c0dff851a0be#ID0EAADAAA=Online
) e [ripristinare gli elementi eliminati dal cestino della raccolta siti](https://support.office.com/article/5fa924ee-16d7-487b-9a0a-021b9062d14b).</span><span class="sxs-lookup"><span data-stu-id="f86b3-110">For info about restoring deleted items, see [Restore items in the Recycle Bin of a SharePoint site](https://support.office.com/article/6df466b6-55f2-4898-8d6e-c0dff851a0be#ID0EAADAAA=Online
) and [Restore deleted items from the site collection recycle bin](https://support.office.com/article/5fa924ee-16d7-487b-9a0a-021b9062d14b).</span></span> <span data-ttu-id="f86b3-111">Il tempo di conservazione del cestino non è configurabile in SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="f86b3-111">The Recycle Bin retention time is not configurable in SharePoint Online.</span></span>

<span data-ttu-id="f86b3-112">Quando si elimina una raccolta siti, si elimina anche la gerarchia dei siti nell'insieme e tutto il contenuto all'interno di essi:</span><span class="sxs-lookup"><span data-stu-id="f86b3-112">When you delete a site collection, you're also deleting the hierarchy of sites in the collection, and all content within them:</span></span>

- <span data-ttu-id="f86b3-113">Documenti e raccolte documenti</span><span class="sxs-lookup"><span data-stu-id="f86b3-113">Documents and document libraries</span></span>
- <span data-ttu-id="f86b3-114">Elenchi e dati di elenco</span><span class="sxs-lookup"><span data-stu-id="f86b3-114">Lists and list data</span></span>
- <span data-ttu-id="f86b3-115">Impostazioni di configurazione del sito</span><span class="sxs-lookup"><span data-stu-id="f86b3-115">Site configuration settings</span></span>
- <span data-ttu-id="f86b3-116">Informazioni sul ruolo e sulla sicurezza correlate al sito o ai relativi siti secondari</span><span class="sxs-lookup"><span data-stu-id="f86b3-116">Role and security information that is related to the site or its subsites</span></span>
- <span data-ttu-id="f86b3-117">Siti secondari del sito Web principale, del relativo contenuto e delle informazioni utente</span><span class="sxs-lookup"><span data-stu-id="f86b3-117">Subsites of the top-level website, their contents, and user information</span></span>

<span data-ttu-id="f86b3-118">Se si elimina accidentalmente una raccolta siti, è possibile ripristinarla da un amministratore globale o di SharePoint utilizzando l'interfaccia di amministrazione di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="f86b3-118">If you accidentally delete a site collection, it can be restored by a global or SharePoint admin using the SharePoint admin center.</span></span>

<span data-ttu-id="f86b3-119">Le raccolte siti eliminate vengono conservate per 93 giorni.</span><span class="sxs-lookup"><span data-stu-id="f86b3-119">Deleted site collections are retained for 93 days.</span></span> <span data-ttu-id="f86b3-120">Dopo 93 giorni, i siti e tutto il relativo contenuto e le impostazioni vengono eliminati definitivamente, inclusi elenchi, raccolte, pagine e siti secondari.</span><span class="sxs-lookup"><span data-stu-id="f86b3-120">After 93 days, sites and all their content and settings are permanently deleted, including lists, libraries, pages, and any subsites.</span></span>

<span data-ttu-id="f86b3-121">L'eliminazione non consentita si verifica quando un utente elimina gli elementi eliminati dal cestino della raccolta siti, quando scade il periodo di conservazione e di backup oppure quando un amministratore Elimina definitivamente una raccolta siti utilizzando il [cmdlet Remove-SPODeletedSite](/powershell/module/sharepoint-online/Remove-SPODeletedSite?view=sharepoint-ps).</span><span class="sxs-lookup"><span data-stu-id="f86b3-121">Hard deletion occurs when a user purges deleted items from the site collection Recycle Bin, when the retention and backup periods expire, or when an administrator permanently deletes a site collection using the [Remove-SPODeletedSite cmdlet](/powershell/module/sharepoint-online/Remove-SPODeletedSite?view=sharepoint-ps).</span></span> <span data-ttu-id="f86b3-122">Quando un utente Elimina (Elimina definitivamente o Elimina in modo definitivo) contenuto da SharePoint Online, vengono eliminate anche tutte le chiavi di crittografia per i blocchi eliminati.</span><span class="sxs-lookup"><span data-stu-id="f86b3-122">When a user hard deletes (permanently deletes, or purges) content from SharePoint Online, all encryption keys for the deleted chunks are also deleted.</span></span> <span data-ttu-id="f86b3-123">I blocchi nei dischi che in precedenza sono stati memorizzati nei blocchi eliminati vengono contrassegnati come inutilizzati e disponibili per il riutilizzo.</span><span class="sxs-lookup"><span data-stu-id="f86b3-123">The blocks on the disks that previously stored the deleted chunks are marked as unused and available for re-use.</span></span>
