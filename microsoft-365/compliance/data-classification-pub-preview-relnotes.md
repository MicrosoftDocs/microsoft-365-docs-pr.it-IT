---
title: Note sulla versione della classificazione dei dati
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Note sulla versione per la classificazione dei dati.
ms.openlocfilehash: bbef6729680db2c9a6aec4caa9036ec23fad6949
ms.sourcegitcommit: f6840dfcfdbcadc53cda591fd6cf9ddcb749d303
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "44327609"
---
# <a name="data-classification-release-notes"></a><span data-ttu-id="7b794-103">Note sulla versione della classificazione dei dati</span><span class="sxs-lookup"><span data-stu-id="7b794-103">Data classification release notes</span></span>

<span data-ttu-id="7b794-104">Per un'esperienza ottimale con la classificazione dei dati, leggere le note sulla versione.</span><span class="sxs-lookup"><span data-stu-id="7b794-104">Please review these release notes so that you have the best experience with data classification.</span></span>

## <a name="exchange-mailbox-count"></a><span data-ttu-id="7b794-105">Numero di cassette postali di Exchange</span><span class="sxs-lookup"><span data-stu-id="7b794-105">Exchange mailbox count</span></span>

<span data-ttu-id="7b794-106">Quando si esegue l'analisi delle cassette postali di Exchange, viene visualizzata una piccola descrizione comando.</span><span class="sxs-lookup"><span data-stu-id="7b794-106">You will notice a small tool tip appear when you drill into Exchange mailboxes.</span></span> <span data-ttu-id="7b794-107">Questo per evidenziare che il totale visualizzato per il tipo di informazioni riservate, l'etichetta di riservatezza e l'etichetta di conservazione potrebbe non corrispondere esattamente al numero di elementi presenti nella cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="7b794-107">This is to call out the fact that the aggregate count displayed for sensitive information type, sensitivity label and retention label may not exactly match the number of items that you will find inside the mailbox.</span></span> <span data-ttu-id="7b794-108">Ciò avviene perché il drill-down nella cartella recupera la visualizzazione in tempo reale del contenuto, che è classificato, mentre viene calcolato il totale.</span><span class="sxs-lookup"><span data-stu-id="7b794-108">This is because the drill down into the folder fetches the live view of content, which is classified, while the aggregated count is calculated.</span></span>


## <a name="rendering-of-encrypted-documents"></a><span data-ttu-id="7b794-109">Rendering di documenti crittografati</span><span class="sxs-lookup"><span data-stu-id="7b794-109">Rendering of encrypted documents</span></span>

<span data-ttu-id="7b794-110">I file di SharePoint, Exchange e OneDrive crittografati non verranno visualizzati in Esplora contenuto.</span><span class="sxs-lookup"><span data-stu-id="7b794-110">SharePoint, Exchange, and OneDrive files that are encrypted will not render in the content explorer.</span></span> <span data-ttu-id="7b794-111">Si tratta di un problema delicato che richiede un equilibrio tra la necessità di visualizzare il contenuto del file in Esplora contenuto e la necessità di mantenere crittografato il contenuto.</span><span class="sxs-lookup"><span data-stu-id="7b794-111">This is a sensitive issue that requires a balance between the need to see file contents in content explorer and the need to keep the contents encrypted.</span></span> <span data-ttu-id="7b794-112">Con le autorizzazioni concesse dai gruppi di ruoli **Visualizzatore elenco di Esplora contenuto** e **Visualizzatore contenuto di Esplora contenuto**, si potrà vedere una visualizzazione elenco dei file, i metadati del file e un collegamento che è possibile usare per accedere al contenuto tramite il client Web.</span><span class="sxs-lookup"><span data-stu-id="7b794-112">With the permissions granted by **Content Explorer List Viewer**, and **Content Explorer Content Viewer** role groups, you will see a list view of the files, the file  metadata, and a link you can use to access the content via the web client.</span></span>

## <a name="supported-characters-in-retention-label-names-in-sharepoint-search"></a><span data-ttu-id="7b794-113">Caratteri supportati nei nomi delle etichette di conservazione nel servizio di ricerca di SharePoint</span><span class="sxs-lookup"><span data-stu-id="7b794-113">Supported characters in retention label names in SharePoint search</span></span>

<span data-ttu-id="7b794-114">Il servizio di ricerca di SharePoint non supporta nomi delle etichette di conservazione contenenti `-` o `_`.</span><span class="sxs-lookup"><span data-stu-id="7b794-114">SharePoint search does not support retention label names with `-`, or `_` in them.</span></span> <span data-ttu-id="7b794-115">Ad esempio, non supporta `Label-MIP` e `Label_MIP`.</span><span class="sxs-lookup"><span data-stu-id="7b794-115">For example `Label-MIP` and `Label_MIP` are not supported.</span></span> <span data-ttu-id="7b794-116">Il servizio di ricerca di SharePoint non supporta tali caratteri nei nomi delle etichette di riservatezza e nei nomi dei tipi di informazioni riservate.</span><span class="sxs-lookup"><span data-stu-id="7b794-116">SharePoint search does support those characters in sensitivity label names and sensitive information type names.</span></span>

## <a name="onedrive-remains-in-preview"></a><span data-ttu-id="7b794-117">OneDrive rimane disponibile in anteprima</span><span class="sxs-lookup"><span data-stu-id="7b794-117">OneDrive remains in preview</span></span>

<span data-ttu-id="7b794-118">Durante il programma di anteprima, abbiamo ascoltato i preziosi feedback degli utenti sull'integrazione di OneDrive.</span><span class="sxs-lookup"><span data-stu-id="7b794-118">We have listened to your valuable feedback on OneDrive integration during our preview program.</span></span> <span data-ttu-id="7b794-119">Mentre lavoriamo sulle specifiche, potrebbero verificarsi flussi o dati incoerenti.</span><span class="sxs-lookup"><span data-stu-id="7b794-119">As we work through the specifics, you may run into inconsistent data / flows.</span></span> <span data-ttu-id="7b794-120">Continueremo a presentare OneDrive in anteprima finché non saranno applicate tutte le correzioni.</span><span class="sxs-lookup"><span data-stu-id="7b794-120">We will continue to showcase OneDrive in preview till all fixes are in place.</span></span> <span data-ttu-id="7b794-121">Apprezziamo molto il continuo supporto degli utenti.</span><span class="sxs-lookup"><span data-stu-id="7b794-121">We appreciate your continued support on this.</span></span>


## <a name="see-also"></a><span data-ttu-id="7b794-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7b794-122">See also</span></span>

- [<span data-ttu-id="7b794-123">Introduzione alla classificazione dei dati (anteprima)</span><span class="sxs-lookup"><span data-stu-id="7b794-123">Get started with data classification (preview)</span></span>](data-classification-overview.md)
- [<span data-ttu-id="7b794-124">Visualizzazione delle attività con etichette (anteprima)</span><span class="sxs-lookup"><span data-stu-id="7b794-124">View label activity (preview)</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="7b794-125">Visualizzare il contenuto con etichetta (anteprima)</span><span class="sxs-lookup"><span data-stu-id="7b794-125">View labeled content (preview)</span></span>](data-classification-content-explorer.md)
- [<span data-ttu-id="7b794-126">Etichette di riservatezza</span><span class="sxs-lookup"><span data-stu-id="7b794-126">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="7b794-127">Etichette di conservazione</span><span class="sxs-lookup"><span data-stu-id="7b794-127">Retention labels</span></span>](labels.md)
- [<span data-ttu-id="7b794-128">Definizioni delle entità tipo di informazioni sensibili</span><span class="sxs-lookup"><span data-stu-id="7b794-128">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)