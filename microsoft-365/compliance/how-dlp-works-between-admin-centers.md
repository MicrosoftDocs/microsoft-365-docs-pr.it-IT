---
title: Funzionamento di DLP con centro & sicurezza & Exchange'interfaccia di amministrazione
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a7e4342a-a0a1-4b43-b166-3d7eecf5d2fd
description: Informazioni su come DLP nel Centro sicurezza & conformità funziona con dlp e regole del flusso di posta (regole di trasporto) nell'Exchange di amministrazione.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d71c45e5483bc73afbe2598415e30b84e97c2539
ms.sourcegitcommit: 46b77a41dfcc0ee80e2b89a7aa49e9bbe5deae5a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/26/2021
ms.locfileid: "53149143"
---
# <a name="how-dlp-works-between-the-microsoft-365-compliance-center-and-exchange-admin-center"></a><span data-ttu-id="a9889-103">Funzionamento di DLP tra il Centro Microsoft 365 conformità e l Exchange intervanza di amministrazione</span><span class="sxs-lookup"><span data-stu-id="a9889-103">How DLP works between the Microsoft 365 Compliance Center and Exchange admin center</span></span>

<span data-ttu-id="a9889-104">In Microsoft 365, è possibile creare un criterio di prevenzione della perdita dei dati (DLP) in due diverse aree di amministrazione:</span><span class="sxs-lookup"><span data-stu-id="a9889-104">In Microsoft 365, you can create a data loss prevention (DLP) policy in two different admin centers:</span></span>
  
- <span data-ttu-id="a9889-105">Nel Centro conformità **Microsoft 365**, è possibile creare un singolo criterio DLP per proteggere il contenuto in SharePoint, OneDrive, Exchange, Teams e ora Dispositivi endpoint.</span><span class="sxs-lookup"><span data-stu-id="a9889-105">In the **Microsoft 365 Compliance Center**, you can create a single DLP policy to help protect content in SharePoint, OneDrive, Exchange, Teams, and now Endpoint Devices.</span></span> <span data-ttu-id="a9889-106">È consigliabile creare un criterio DLP qui.</span><span class="sxs-lookup"><span data-stu-id="a9889-106">We recommend that you create a DLP policy here.</span></span> <span data-ttu-id="a9889-107">Per ulteriori informazioni, vedere [Informazioni di riferimento sulla prevenzione della perdita di dati.](data-loss-prevention-policies.md)</span><span class="sxs-lookup"><span data-stu-id="a9889-107">For more information, see [Data Loss Prevention reference](data-loss-prevention-policies.md).</span></span>
    
- <span data-ttu-id="a9889-108">**Nell'Exchange di amministrazione,** è possibile creare un criterio DLP per proteggere il contenuto solo in Exchange.</span><span class="sxs-lookup"><span data-stu-id="a9889-108">In the **Exchange admin center**, you can create a DLP policy to help protect content only in Exchange.</span></span> <span data-ttu-id="a9889-109">Questo criterio può usare regole Exchange del flusso di posta (note anche come regole di trasporto), quindi ha più opzioni specifiche per la gestione della posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="a9889-109">This policy can use Exchange mail flow rules (also known as transport rules), so it has more options specific to handling email.</span></span> <span data-ttu-id="a9889-110">Per ulteriori informazioni, vedere [DLP nell'Exchange di amministrazione.](/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention)</span><span class="sxs-lookup"><span data-stu-id="a9889-110">For more information, see [DLP in the Exchange admin center](/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention).</span></span>
    
<span data-ttu-id="a9889-111">I criteri DLP creati in queste centri di amministrazione lavorano affiancati: in questo argomento viene illustrato come.</span><span class="sxs-lookup"><span data-stu-id="a9889-111">DLP polices created in these admin centers work side by side - this topic explains how.</span></span>
  
![Pagine DLP nel Centro sicurezza e conformità e nell'Exchange di amministrazione](../media/d3eaa7e7-3b16-457b-bd9c-26707f7b584f.png)
  
## <a name="how-dlp-in-the-security--compliance-center-works-with-dlp-and-mail-flow-rules-in-the-exchange-admin-center"></a><span data-ttu-id="a9889-113">Funzionamento di DLP nel Centro sicurezza & conformità con dlp e regole del flusso di posta nell'Exchange di amministrazione</span><span class="sxs-lookup"><span data-stu-id="a9889-113">How DLP in the Security & Compliance Center works with DLP and mail flow rules in the Exchange admin center</span></span>

<span data-ttu-id="a9889-114">Dopo aver creato un criterio DLP nel Centro sicurezza & conformità, il criterio viene distribuito in tutte le posizioni incluse nel criterio.</span><span class="sxs-lookup"><span data-stu-id="a9889-114">After you create a DLP policy in the Security & Compliance Center, the policy is deployed to all of the locations included in the policy.</span></span> <span data-ttu-id="a9889-115">Se il criterio include Exchange Online, il criterio viene sincronizzato e applicato esattamente allo stesso modo di un criterio DLP creato nell'interfaccia di amministrazione di Exchange.</span><span class="sxs-lookup"><span data-stu-id="a9889-115">If the policy includes Exchange Online, the policy's synced there and enforced in exactly the same way as a DLP policy created in the Exchange admin center.</span></span> 
  
<span data-ttu-id="a9889-116">Se sono stati creati criteri DLP nell'interfaccia di amministrazione di Exchange, tali criteri continueranno a funzionare affiancati a tutti i criteri per la posta elettronica creati nel Centro sicurezza & conformità.</span><span class="sxs-lookup"><span data-stu-id="a9889-116">If you've created DLP policies in the Exchange admin center, those policies will continue to work side by side with any policies for email that you create in the Security & Compliance Center.</span></span> <span data-ttu-id="a9889-117">Tieni presente che le regole create nell'Exchange di amministrazione hanno la precedenza.</span><span class="sxs-lookup"><span data-stu-id="a9889-117">But note that rules created in the Exchange admin center take precedence.</span></span> <span data-ttu-id="a9889-118">Tutte Exchange le regole del flusso di posta vengono elaborate prima e quindi vengono elaborate le regole DLP del Centro sicurezza & conformità.</span><span class="sxs-lookup"><span data-stu-id="a9889-118">All Exchange mail flow rules are processed first, and then the DLP rules from the Security & Compliance Center are processed.</span></span>
  
<span data-ttu-id="a9889-119">Ciò significa che:</span><span class="sxs-lookup"><span data-stu-id="a9889-119">This means that:</span></span>
  
- <span data-ttu-id="a9889-120">I messaggi bloccati da Exchange flusso di posta elettronica non verranno analizzati dalle regole DLP create nel Centro sicurezza & conformità.</span><span class="sxs-lookup"><span data-stu-id="a9889-120">Messages that are blocked by Exchange mail flow rules won't get scanned by DLP rules created in the Security & Compliance Center.</span></span>
    
- <span data-ttu-id="a9889-121">Se una regola del flusso di posta di Exchange modifica un messaggio in modo che corrisponda a un criterio DLP nel Centro sicurezza & conformità, ad esempio l'aggiunta di utenti esterni, le regole DLP lo rileveranno e applichino il criterio in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="a9889-121">If an Exchange mail flow rule modifies a message in a way that causes it to match a DLP policy in the Security & Compliance Center - such as adding external users - then the DLP rules will detect this and enforce the policy as needed.</span></span>
    
<span data-ttu-id="a9889-122">Si noti inoltre che Exchange regole del flusso di posta che utilizzano l'azione "interrompi elaborazione" non influiscono sull'elaborazione delle regole DLP nel Centro sicurezza & conformità, che verranno comunque elaborate.</span><span class="sxs-lookup"><span data-stu-id="a9889-122">Also note that Exchange mail flow rules that use the "stop processing" action don't affect the processing of DLP rules in the Security & Compliance Center - they'll still be processed.</span></span>
  
## <a name="policy-tips-in-the-security--compliance-center-vs-the-exchange-admin-center"></a><span data-ttu-id="a9889-123">Suggerimenti per i criteri nel Centro sicurezza & conformità e nell Exchange intervanza di amministrazione</span><span class="sxs-lookup"><span data-stu-id="a9889-123">Policy tips in the Security & Compliance Center vs. the Exchange admin center</span></span>

<span data-ttu-id="a9889-124">I suggerimenti per i criteri possono funzionare con i criteri DLP e le regole del flusso di posta creati nell'interfaccia di amministrazione di Exchange oppure con i criteri DLP creati nel Centro sicurezza & Conformità, ma non entrambi.</span><span class="sxs-lookup"><span data-stu-id="a9889-124">Policy tips can work either with DLP policies and mail flow rules created in the Exchange admin center, or with DLP policies created in the Security & Compliance Center, but not both.</span></span> <span data-ttu-id="a9889-125">Questo perché questi criteri sono archiviati in posizioni diverse, ma i suggerimenti per i criteri possono essere attingere solo da un'unica posizione.</span><span class="sxs-lookup"><span data-stu-id="a9889-125">This is because these policies are stored in different locations, but policy tips can draw only from a single location.</span></span>
  
<span data-ttu-id="a9889-126">Se sono stati configurati suggerimenti per i criteri nell'interfaccia di amministrazione di Exchange, eventuali suggerimenti per i criteri configurati nel Centro sicurezza & conformità non verranno visualizzati agli utenti in Outlook sul web e Outlook 2013 e versioni successive fino a quando non si disattivano i suggerimenti nell'interfaccia di amministrazione di Exchange.</span><span class="sxs-lookup"><span data-stu-id="a9889-126">If you've configured policy tips in the Exchange admin center, any policy tips that you configure in the Security & Compliance Center won't appear to users in Outlook on the web and Outlook 2013 and later until you turn off the tips in the Exchange admin center.</span></span> <span data-ttu-id="a9889-127">Ciò garantisce che le regole correnti Exchange flusso di posta continueranno a funzionare fino a quando non si sceglie di passare al Centro sicurezza & conformità.</span><span class="sxs-lookup"><span data-stu-id="a9889-127">This ensures that your current Exchange mail flow rules will continue to work until you choose to switch over to the Security & Compliance Center.</span></span>
  
<span data-ttu-id="a9889-128">Tieni presente che, anche se i suggerimenti per i criteri possono essere attingere solo da un'unica posizione, le notifiche di posta elettronica vengono sempre inviate, anche se si usano i criteri DLP sia nel Centro sicurezza & Conformità che nell'interfaccia di amministrazione di Exchange.</span><span class="sxs-lookup"><span data-stu-id="a9889-128">Note that while policy tips can draw only from a single location, email notifications are always sent, even if you're using DLP policies in both the Security & Compliance Center and the Exchange admin center.</span></span>
