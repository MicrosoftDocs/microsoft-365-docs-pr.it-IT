---
title: Funzionamento della prevenzione della perdita dei dati con il Centro sicurezza & conformità &'interfaccia di amministrazione di Exchange
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 04/19/2019
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
description: Informazioni su come DLP nel Centro sicurezza & conformità funziona con dlp e regole del flusso di posta (regole di trasporto) nell'interfaccia di amministrazione di Exchange.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: cd8a3eb0e7bb859ab9e10551fadd22cc7dcb2a39
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905938"
---
# <a name="how-dlp-works-between-the-security--compliance-center-and-exchange-admin-center"></a><span data-ttu-id="48e40-103">Funzionamento della prevenzione della perdita dei dati tra il Centro sicurezza e conformità e l'interfaccia di amministrazione di Exchange</span><span class="sxs-lookup"><span data-stu-id="48e40-103">How DLP works between the Security & Compliance Center and Exchange admin center</span></span>

<span data-ttu-id="48e40-104">In Office 365, è possibile creare un criterio di prevenzione della perdita dei dati (DLP) in due diverse aree di amministrazione:</span><span class="sxs-lookup"><span data-stu-id="48e40-104">In Office 365, you can create a data loss prevention (DLP) policy in two different admin centers:</span></span>
  
- <span data-ttu-id="48e40-105">Nel **Centro sicurezza &** conformità è possibile creare un singolo criterio DLP per proteggere il contenuto in SharePoint, OneDrive, Exchange e ora Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="48e40-105">In the **Security & Compliance Center**, you can create a single DLP policy to help protect content in SharePoint, OneDrive, Exchange, and now Microsoft Teams.</span></span> <span data-ttu-id="48e40-106">Se possibile, è consigliabile creare un criterio DLP qui.</span><span class="sxs-lookup"><span data-stu-id="48e40-106">When possible, we recommend that you create a DLP policy here.</span></span> <span data-ttu-id="48e40-107">Per ulteriori informazioni, vedere [DLP nel Centro sicurezza & conformità](data-loss-prevention-policies.md).</span><span class="sxs-lookup"><span data-stu-id="48e40-107">For more information, see [DLP in the Security & Compliance Center](data-loss-prevention-policies.md).</span></span>
    
- <span data-ttu-id="48e40-108">**Nell'interfaccia di amministrazione di Exchange,** è possibile creare un criterio DLP per proteggere il contenuto solo in Exchange.</span><span class="sxs-lookup"><span data-stu-id="48e40-108">In the **Exchange admin center**, you can create a DLP policy to help protect content only in Exchange.</span></span> <span data-ttu-id="48e40-109">Questo criterio può utilizzare le regole del flusso di posta di Exchange (note anche come regole di trasporto), quindi ha più opzioni specifiche per la gestione della posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="48e40-109">This policy can use Exchange mail flow rules (also known as transport rules), so it has more options specific to handling email.</span></span> <span data-ttu-id="48e40-110">Per ulteriori informazioni, vedere [DLP nell'interfaccia di amministrazione di Exchange.](/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention)</span><span class="sxs-lookup"><span data-stu-id="48e40-110">For more information, see [DLP in the Exchange admin center](/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention).</span></span>
    
<span data-ttu-id="48e40-111">I criteri DLP creati in queste centri di amministrazione lavorano affiancati: in questo argomento viene illustrato come.</span><span class="sxs-lookup"><span data-stu-id="48e40-111">DLP polices created in these admin centers work side by side - this topic explains how.</span></span>
  
![Pagine DLP in Centro sicurezza e conformità e interfaccia di amministrazione di Exchange](../media/d3eaa7e7-3b16-457b-bd9c-26707f7b584f.png)
  
## <a name="how-dlp-in-the-security--compliance-center-works-with-dlp-and-mail-flow-rules-in-the-exchange-admin-center"></a><span data-ttu-id="48e40-113">Funzionamento di DLP nel Centro sicurezza & conformità con dlp e regole del flusso di posta nell'interfaccia di amministrazione di Exchange</span><span class="sxs-lookup"><span data-stu-id="48e40-113">How DLP in the Security & Compliance Center works with DLP and mail flow rules in the Exchange admin center</span></span>

<span data-ttu-id="48e40-114">Dopo aver creato un criterio DLP nel Centro sicurezza & conformità, il criterio viene distribuito in tutte le posizioni incluse nel criterio.</span><span class="sxs-lookup"><span data-stu-id="48e40-114">After you create a DLP policy in the Security & Compliance Center, the policy is deployed to all of the locations included in the policy.</span></span> <span data-ttu-id="48e40-115">Se il criterio include Exchange Online, il criterio viene sincronizzato e applicato esattamente allo stesso modo di un criterio DLP creato nell'interfaccia di amministrazione di Exchange.</span><span class="sxs-lookup"><span data-stu-id="48e40-115">If the policy includes Exchange Online, the policy's synced there and enforced in exactly the same way as a DLP policy created in the Exchange admin center.</span></span> 
  
<span data-ttu-id="48e40-116">Se sono stati creati criteri DLP nell'interfaccia di amministrazione di Exchange, tali criteri continueranno a funzionare affiancati a tutti i criteri per la posta elettronica creati nel Centro sicurezza & conformità.</span><span class="sxs-lookup"><span data-stu-id="48e40-116">If you've created DLP policies in the Exchange admin center, those policies will continue to work side by side with any policies for email that you create in the Security & Compliance Center.</span></span> <span data-ttu-id="48e40-117">Si noti tuttavia che le regole create nell'interfaccia di amministrazione di Exchange hanno la precedenza.</span><span class="sxs-lookup"><span data-stu-id="48e40-117">But note that rules created in the Exchange admin center take precedence.</span></span> <span data-ttu-id="48e40-118">Tutte le regole del flusso di posta di Exchange vengono elaborate prima e quindi vengono elaborate le regole DLP del Centro sicurezza & conformità.</span><span class="sxs-lookup"><span data-stu-id="48e40-118">All Exchange mail flow rules are processed first, and then the DLP rules from the Security & Compliance Center are processed.</span></span>
  
<span data-ttu-id="48e40-119">Ciò significa che:</span><span class="sxs-lookup"><span data-stu-id="48e40-119">This means that:</span></span>
  
- <span data-ttu-id="48e40-120">I messaggi bloccati dalle regole del flusso di posta di Exchange non verranno analizzati dalle regole DLP create nel Centro sicurezza & conformità.</span><span class="sxs-lookup"><span data-stu-id="48e40-120">Messages that are blocked by Exchange mail flow rules won't get scanned by DLP rules created in the Security & Compliance Center.</span></span>
    
- <span data-ttu-id="48e40-121">Se una regola del flusso di posta di Exchange modifica un messaggio in modo che corrisponda a un criterio DLP nel Centro sicurezza & conformità, ad esempio aggiungendo utenti esterni, le regole DLP lo rilevano e applicano il criterio in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="48e40-121">If an Exchange mail flow rule modifies a message in a way that causes it to match a DLP policy in the Security & Compliance Center - such as adding external users - then the DLP rules will detect this and enforce the policy as needed.</span></span>
    
<span data-ttu-id="48e40-122">Tenere inoltre presente che le regole del flusso di posta di Exchange che utilizzano l'azione "interrompi elaborazione" non influiscono sull'elaborazione delle regole DLP nel Centro sicurezza e conformità di &, che verranno comunque elaborate.</span><span class="sxs-lookup"><span data-stu-id="48e40-122">Also note that Exchange mail flow rules that use the "stop processing" action don't affect the processing of DLP rules in the Security & Compliance Center - they'll still be processed.</span></span>
  
## <a name="policy-tips-in-the-security--compliance-center-vs-the-exchange-admin-center"></a><span data-ttu-id="48e40-123">Suggerimenti per i criteri nel Centro sicurezza & conformità e nell'interfaccia di amministrazione di Exchange</span><span class="sxs-lookup"><span data-stu-id="48e40-123">Policy tips in the Security & Compliance Center vs. the Exchange admin center</span></span>

<span data-ttu-id="48e40-124">I suggerimenti per i criteri possono funzionare con i criteri DLP e le regole del flusso di posta creati nell'interfaccia di amministrazione di Exchange oppure con i criteri DLP creati nel Centro sicurezza & Conformità, ma non con entrambi.</span><span class="sxs-lookup"><span data-stu-id="48e40-124">Policy tips can work either with DLP policies and mail flow rules created in the Exchange admin center, or with DLP policies created in the Security & Compliance Center, but not both.</span></span> <span data-ttu-id="48e40-125">Questo perché questi criteri sono archiviati in posizioni diverse, ma i suggerimenti per i criteri possono essere attingere solo da un'unica posizione.</span><span class="sxs-lookup"><span data-stu-id="48e40-125">This is because these policies are stored in different locations, but policy tips can draw only from a single location.</span></span>
  
<span data-ttu-id="48e40-126">Se sono stati configurati suggerimenti per i criteri nell'interfaccia di amministrazione di Exchange, tutti i suggerimenti per i criteri configurati nel Centro sicurezza & conformità non verranno visualizzati agli utenti in Outlook sul Web e Outlook 2013 e versioni successive fino a quando non si disattivano i suggerimenti nell'interfaccia di amministrazione di Exchange.</span><span class="sxs-lookup"><span data-stu-id="48e40-126">If you've configured policy tips in the Exchange admin center, any policy tips that you configure in the Security & Compliance Center won't appear to users in Outlook on the web and Outlook 2013 and later until you turn off the tips in the Exchange admin center.</span></span> <span data-ttu-id="48e40-127">In questo modo, le regole correnti del flusso di posta di Exchange continueranno a funzionare fino a quando non si sceglie di passare al Centro sicurezza & conformità.</span><span class="sxs-lookup"><span data-stu-id="48e40-127">This ensures that your current Exchange mail flow rules will continue to work until you choose to switch over to the Security & Compliance Center.</span></span>
  
<span data-ttu-id="48e40-128">Si noti che, anche se i suggerimenti per i criteri possono essere attingere solo da un'unica posizione, le notifiche di posta elettronica vengono sempre inviate, anche se si utilizzano i criteri DLP sia nel Centro sicurezza & Conformità che nell'interfaccia di amministrazione di Exchange.</span><span class="sxs-lookup"><span data-stu-id="48e40-128">Note that while policy tips can draw only from a single location, email notifications are always sent, even if you're using DLP policies in both the Security & Compliance Center and the Exchange admin center.</span></span>
