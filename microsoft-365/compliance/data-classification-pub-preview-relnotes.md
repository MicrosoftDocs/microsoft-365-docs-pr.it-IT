---
title: Note sulla versione della classificazione dei dati
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: normal
recommendations: false
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Note sulla versione per la classificazione dei dati.
ms.openlocfilehash: bbce01555367c6151a7b16b551d5580ebcaf9d43
ms.sourcegitcommit: 1206319a5d3fed8d52a2581b8beafc34ab064b1c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/29/2021
ms.locfileid: "52086707"
---
# <a name="data-classification-release-notes"></a><span data-ttu-id="b4f13-103">Note sulla versione della classificazione dei dati</span><span class="sxs-lookup"><span data-stu-id="b4f13-103">Data classification release notes</span></span>


## <a name="exchange-mailbox-count"></a><span data-ttu-id="b4f13-104">Numero di cassette postali di Exchange</span><span class="sxs-lookup"><span data-stu-id="b4f13-104">Exchange mailbox count</span></span>

<span data-ttu-id="b4f13-105">Quando si esegue l'analisi delle cassette postali di Exchange, viene visualizzata una piccola descrizione comando.</span><span class="sxs-lookup"><span data-stu-id="b4f13-105">You will notice a small tool tip appear when you drill into Exchange mailboxes.</span></span> <span data-ttu-id="b4f13-106">Questo per evidenziare che il totale visualizzato per il tipo di informazioni riservate, l'etichetta di riservatezza e l'etichetta di conservazione potrebbe non corrispondere esattamente al numero di elementi presenti nella cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="b4f13-106">This is to call out the fact that the aggregate count displayed for sensitive information type, sensitivity label and retention label may not exactly match the number of items that you will find inside the mailbox.</span></span> <span data-ttu-id="b4f13-107">Ciò avviene perché il drill-down nella cartella recupera la visualizzazione in tempo reale del contenuto, che è classificato, mentre viene calcolato il totale.</span><span class="sxs-lookup"><span data-stu-id="b4f13-107">This is because the drill-down into the folder fetches the live view of content, which is classified, while the aggregated count is calculated.</span></span>


## <a name="rendering-of-encrypted-documents"></a><span data-ttu-id="b4f13-108">Rendering di documenti crittografati</span><span class="sxs-lookup"><span data-stu-id="b4f13-108">Rendering of encrypted documents</span></span>

<span data-ttu-id="b4f13-109">I file di SharePoint, Exchange e OneDrive crittografati non vengono visualizzati in Esplora contenuto.</span><span class="sxs-lookup"><span data-stu-id="b4f13-109">SharePoint, Exchange, and OneDrive files that are encrypted don't render in the content explorer.</span></span> <span data-ttu-id="b4f13-110">Si tratta di un problema delicato che richiede un equilibrio tra la necessità di visualizzare il contenuto del file in Esplora contenuto e la necessità di mantenere crittografato il contenuto.</span><span class="sxs-lookup"><span data-stu-id="b4f13-110">This is a sensitive issue that requires a balance between the need to see file contents in content explorer and the need to keep the contents encrypted.</span></span> <span data-ttu-id="b4f13-111">Con le autorizzazioni concesse dai gruppi di ruoli **Visualizzatore elenco di Esplora contenuto** e **Visualizzatore contenuto di Esplora contenuto**, si potrà vedere una visualizzazione elenco dei file, i metadati del file e un collegamento che è possibile usare per accedere al contenuto tramite il client Web.</span><span class="sxs-lookup"><span data-stu-id="b4f13-111">With the permissions granted by **Content Explorer List Viewer**, and **Content Explorer Content Viewer** role groups, you will see a list view of the files, the file  metadata, and a link you can use to access the content via the web client.</span></span>

## <a name="supported-characters-in-retention-label-names-in-sharepoint-search"></a><span data-ttu-id="b4f13-112">Caratteri supportati nei nomi delle etichette di conservazione nel servizio di ricerca di SharePoint</span><span class="sxs-lookup"><span data-stu-id="b4f13-112">Supported characters in retention label names in SharePoint search</span></span>

<span data-ttu-id="b4f13-113">Il servizio di ricerca di SharePoint non supporta nomi delle etichette di conservazione contenenti `-` o `_`.</span><span class="sxs-lookup"><span data-stu-id="b4f13-113">SharePoint search doesn't support retention label names with `-`, or `_` in them.</span></span> <span data-ttu-id="b4f13-114">Ad esempio, non supporta `Label-MIP` e `Label_MIP`.</span><span class="sxs-lookup"><span data-stu-id="b4f13-114">For example, `Label-MIP` and `Label_MIP` aren't supported.</span></span> <span data-ttu-id="b4f13-115">Il servizio di ricerca di SharePoint non supporta tali caratteri nei nomi delle etichette di riservatezza e nei nomi dei tipi di informazioni riservate.</span><span class="sxs-lookup"><span data-stu-id="b4f13-115">SharePoint search does support those characters in sensitivity label names and sensitive information type names.</span></span>

## <a name="onedrive-remains-in-preview"></a><span data-ttu-id="b4f13-116">OneDrive rimane disponibile in anteprima</span><span class="sxs-lookup"><span data-stu-id="b4f13-116">OneDrive remains in preview</span></span>

<span data-ttu-id="b4f13-117">Grazie per i preziosi feedback degli utenti sull'integrazione di OneDrive durante il programma di anteprima.</span><span class="sxs-lookup"><span data-stu-id="b4f13-117">Thanks for your valuable feedback on OneDrive integration during our preview program.</span></span> <span data-ttu-id="b4f13-118">Poiché lavoriamo sulle specifiche, potrebbero verificarsi flussi o dati incoerenti.</span><span class="sxs-lookup"><span data-stu-id="b4f13-118">As we work through the specifics, you may run into inconsistent data / flows.</span></span> <span data-ttu-id="b4f13-119">Continueremo a presentare OneDrive in anteprima finché non saranno applicate tutte le correzioni.</span><span class="sxs-lookup"><span data-stu-id="b4f13-119">We'll continue to showcase OneDrive in preview until all fixes are in place.</span></span> <span data-ttu-id="b4f13-120">Apprezziamo molto il continuo supporto degli utenti.</span><span class="sxs-lookup"><span data-stu-id="b4f13-120">We appreciate your continued support.</span></span>


## <a name="see-also"></a><span data-ttu-id="b4f13-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b4f13-121">See also</span></span>

- [<span data-ttu-id="b4f13-122">Introduzione alla classificazione dei dati (anteprima)</span><span class="sxs-lookup"><span data-stu-id="b4f13-122">Get started with data classification (preview)</span></span>](data-classification-overview.md)
- [<span data-ttu-id="b4f13-123">Visualizzazione delle attività con etichette (anteprima)</span><span class="sxs-lookup"><span data-stu-id="b4f13-123">View label activity (preview)</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="b4f13-124">Visualizzare il contenuto con etichetta (anteprima)</span><span class="sxs-lookup"><span data-stu-id="b4f13-124">View labeled content (preview)</span></span>](data-classification-content-explorer.md)
- [<span data-ttu-id="b4f13-125">Informazioni sulle etichette di riservatezza</span><span class="sxs-lookup"><span data-stu-id="b4f13-125">Learn about sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="b4f13-126">Informazioni sui criteri e sulle etichette di conservazione</span><span class="sxs-lookup"><span data-stu-id="b4f13-126">Learn about retention policies and retention labels</span></span>](retention.md)
- [<span data-ttu-id="b4f13-127">Definizioni delle entità tipo di informazioni sensibili</span><span class="sxs-lookup"><span data-stu-id="b4f13-127">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)