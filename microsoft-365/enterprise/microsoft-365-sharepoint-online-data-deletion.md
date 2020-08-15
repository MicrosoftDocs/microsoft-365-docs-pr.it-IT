---
title: Eliminazione dei dati di Microsoft 365 SharePoint Online
ms.author: josephd
author: JoeDavies-MSFT
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
ms.openlocfilehash: 5cea1b797d078f6ae627700b28c6fb90cc005637
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691385"
---
# <a name="sharepoint-online-data-deletion-in-microsoft-365"></a><span data-ttu-id="0eaeb-103">Eliminazione dei dati di SharePoint online in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0eaeb-103">SharePoint Online Data Deletion in Microsoft 365</span></span>

<span data-ttu-id="0eaeb-104">SharePoint Online archivia gli oggetti come codice astratto all'interno dei database dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0eaeb-104">SharePoint Online stores objects as abstracted code within application databases.</span></span> <span data-ttu-id="0eaeb-105">Quando un utente carica un file in SharePoint Online, tale file viene disassemblato e convertito in codice dell'applicazione e archiviato in più tabelle tra più database.</span><span class="sxs-lookup"><span data-stu-id="0eaeb-105">When a user uploads a file to SharePoint Online, that file is disassembled and translated into application code and stored in multiple tables across multiple databases.</span></span> <span data-ttu-id="0eaeb-106">In SharePoint Online, tutto il contenuto utilizzato dai caricamenti dei clienti è suddiviso in blocchi, crittografato (potenzialmente con più chiavi AES 256 bit) e distribuito in tutto il datacenter.</span><span class="sxs-lookup"><span data-stu-id="0eaeb-106">In SharePoint Online, all content that a customer uploads is broken into chunks, encrypted (potentially with multiple AES 256-bit keys), and distributed across the datacenter.</span></span> <span data-ttu-id="0eaeb-107">Per informazioni dettagliate sul processo di blocco e la crittografia, vedere [crittografia nel cloud Microsoft](https://docs.microsoft.com/microsoft-365/compliance/office-365-encryption-in-the-microsoft-cloud-overview).</span><span class="sxs-lookup"><span data-stu-id="0eaeb-107">For specific details about the chunking and encryption process, see [Encryption in the Microsoft Cloud](https://docs.microsoft.com/microsoft-365/compliance/office-365-encryption-in-the-microsoft-cloud-overview).</span></span> 

<span data-ttu-id="0eaeb-108">In SharePoint Online, gli elementi vengono conservati per 93 giorni dal momento in cui vengono eliminati dal percorso originale.</span><span class="sxs-lookup"><span data-stu-id="0eaeb-108">In SharePoint Online, items are retained for 93 days from the time you delete them from their original location.</span></span> <span data-ttu-id="0eaeb-109">Rimangono nel cestino del sito per tutto il tempo, a meno che qualcuno non li elimini o svuoti quel cestino.</span><span class="sxs-lookup"><span data-stu-id="0eaeb-109">They stay in the site Recycle Bin the entire time, unless someone deletes them from there or empties that Recycle Bin.</span></span> <span data-ttu-id="0eaeb-110">In tal caso, gli elementi passano al cestino della raccolta siti, in cui restano per il resto dei 93 giorni.</span><span class="sxs-lookup"><span data-stu-id="0eaeb-110">In that case, the items go to the site collection Recycle Bin, where they stay for the remainder of the 93 days.</span></span> <span data-ttu-id="0eaeb-111">Per informazioni su come ripristinare gli elementi eliminati, vedere [ripristinare gli elementi nel cestino di un sito di SharePoint](https://support.office.com/article/6df466b6-55f2-4898-8d6e-c0dff851a0be#ID0EAADAAA=Online
) e [ripristinare gli elementi eliminati dal cestino della raccolta siti](https://support.office.com/article/5fa924ee-16d7-487b-9a0a-021b9062d14b).</span><span class="sxs-lookup"><span data-stu-id="0eaeb-111">For info about restoring deleted items, see [Restore items in the Recycle Bin of a SharePoint site](https://support.office.com/article/6df466b6-55f2-4898-8d6e-c0dff851a0be#ID0EAADAAA=Online
) and [Restore deleted items from the site collection recycle bin](https://support.office.com/article/5fa924ee-16d7-487b-9a0a-021b9062d14b).</span></span> <span data-ttu-id="0eaeb-112">Il tempo di conservazione del cestino non è configurabile in SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="0eaeb-112">The Recycle Bin retention time is not configurable in SharePoint Online.</span></span>

<span data-ttu-id="0eaeb-113">Quando si elimina una raccolta siti, si elimina anche la gerarchia dei siti nell'insieme e tutto il contenuto all'interno di essi:</span><span class="sxs-lookup"><span data-stu-id="0eaeb-113">When you delete a site collection, you're also deleting the hierarchy of sites in the collection, and all content within them:</span></span>

- <span data-ttu-id="0eaeb-114">Documenti e raccolte documenti</span><span class="sxs-lookup"><span data-stu-id="0eaeb-114">Documents and document libraries</span></span>
- <span data-ttu-id="0eaeb-115">Elenchi e dati di elenco</span><span class="sxs-lookup"><span data-stu-id="0eaeb-115">Lists and list data</span></span>
- <span data-ttu-id="0eaeb-116">Impostazioni di configurazione del sito</span><span class="sxs-lookup"><span data-stu-id="0eaeb-116">Site configuration settings</span></span>
- <span data-ttu-id="0eaeb-117">Informazioni sul ruolo e sulla sicurezza correlate al sito o ai relativi siti secondari</span><span class="sxs-lookup"><span data-stu-id="0eaeb-117">Role and security information that is related to the site or its subsites</span></span>
- <span data-ttu-id="0eaeb-118">Siti secondari del sito Web principale, del relativo contenuto e delle informazioni utente</span><span class="sxs-lookup"><span data-stu-id="0eaeb-118">Subsites of the top-level website, their contents, and user information</span></span>

<span data-ttu-id="0eaeb-119">Se si elimina accidentalmente una raccolta siti, è possibile ripristinarla da un amministratore globale o di SharePoint utilizzando l'interfaccia di amministrazione di SharePoint.</span><span class="sxs-lookup"><span data-stu-id="0eaeb-119">If you accidentally delete a site collection, it can be restored by a global or SharePoint admin using the SharePoint admin center.</span></span>

<span data-ttu-id="0eaeb-120">Le raccolte siti eliminate vengono conservate per 93 giorni.</span><span class="sxs-lookup"><span data-stu-id="0eaeb-120">Deleted site collections are retained for 93 days.</span></span> <span data-ttu-id="0eaeb-121">Dopo 93 giorni, i siti e tutto il relativo contenuto e le impostazioni vengono eliminati definitivamente, inclusi elenchi, raccolte, pagine e siti secondari.</span><span class="sxs-lookup"><span data-stu-id="0eaeb-121">After 93 days, sites and all their content and settings are permanently deleted, including lists, libraries, pages, and any subsites.</span></span>

<span data-ttu-id="0eaeb-122">L'eliminazione non consentita si verifica quando un utente elimina gli elementi eliminati dal cestino della raccolta siti, quando scade il periodo di conservazione e di backup oppure quando un amministratore Elimina definitivamente una raccolta siti utilizzando il [cmdlet Remove-SPODeletedSite](/powershell/module/sharepoint-online/Remove-SPODeletedSite?view=sharepoint-ps).</span><span class="sxs-lookup"><span data-stu-id="0eaeb-122">Hard deletion occurs when a user purges deleted items from the site collection Recycle Bin, when the retention and backup periods expire, or when an administrator permanently deletes a site collection using the [Remove-SPODeletedSite cmdlet](/powershell/module/sharepoint-online/Remove-SPODeletedSite?view=sharepoint-ps).</span></span> <span data-ttu-id="0eaeb-123">Quando un utente Elimina (Elimina definitivamente o Elimina in modo definitivo) contenuto da SharePoint Online, vengono eliminate anche tutte le chiavi di crittografia per i blocchi eliminati.</span><span class="sxs-lookup"><span data-stu-id="0eaeb-123">When a user hard deletes (permanently deletes, or purges) content from SharePoint Online, all encryption keys for the deleted chunks are also deleted.</span></span> <span data-ttu-id="0eaeb-124">I blocchi nei dischi che in precedenza sono stati memorizzati nei blocchi eliminati vengono contrassegnati come inutilizzati e disponibili per il riutilizzo.</span><span class="sxs-lookup"><span data-stu-id="0eaeb-124">The blocks on the disks that previously stored the deleted chunks are marked as unused and available for re-use.</span></span>
