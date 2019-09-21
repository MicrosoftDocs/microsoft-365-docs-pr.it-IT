---
title: Tipi di informazioni sensibili per DLP
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: 04/23/2019
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Panoramica dei tipi di informazioni sensibili per DLP.
ms.openlocfilehash: b73f0d51e57106cbcc6f0986261faabb26cc5b4a
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37083025"
---
# <a name="custom-sensitive-information-types"></a><span data-ttu-id="9a621-103">Tipi di informazioni sensibili personalizzati</span><span class="sxs-lookup"><span data-stu-id="9a621-103">Custom sensitive information types</span></span>

## <a name="overview"></a><span data-ttu-id="9a621-104">Panoramica</span><span class="sxs-lookup"><span data-stu-id="9a621-104">Overview</span></span>

<span data-ttu-id="9a621-105">Office 365 include molti tipi di informazioni sensibili predefinite pronte per l'uso nell'organizzazione, ad esempio per la [prevenzione della perdita dei dati](data-loss-prevention-policies.md) (DLP) o con [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security).</span><span class="sxs-lookup"><span data-stu-id="9a621-105">Office 365 includes many built-in sensitive information types that are ready for you to use in your organization, such as for [data loss prevention](data-loss-prevention-policies.md) (DLP), or with [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security).</span></span> <span data-ttu-id="9a621-106">I tipi di informazioni sensibili integrati consentono di identificare e proteggere i numeri di carata di credito, di conto corrente, di passaporto e altro, in base agli schemi che sono definiti da un'espressione regolare (regex) o da una funzione.</span><span class="sxs-lookup"><span data-stu-id="9a621-106">Built-in sensitive information types can help identify and protect credit card numbers, bank account numbers, passport numbers, and more, based on patterns that are defined by a regular expression (regex) or a function.</span></span> <span data-ttu-id="9a621-107">Per altre informazioni, vedere [Elementi cercati dai tipi di informazioni sensibili](what-the-sensitive-information-types-look-for.md).</span><span class="sxs-lookup"><span data-stu-id="9a621-107">To learn more, see [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>

<span data-ttu-id="9a621-108">Tuttavia, cosa accade se è necessario identificare e proteggere un tipo diverso di informazioni sensibili, ad esempio gli ID dei dipendenti o i numeri di progetto che usano un formato specifico dell'organizzazione?</span><span class="sxs-lookup"><span data-stu-id="9a621-108">But what if you need to identify and protect a different type of sensitive information, such as for employee IDs or project numbers, using a format that's specific to your organization?</span></span> <span data-ttu-id="9a621-109">Per farlo, è possibile creare un tipo di informazioni sensibili personalizzato.</span><span class="sxs-lookup"><span data-stu-id="9a621-109">To do this, you can create a custom sensitive information type.</span></span>

<span data-ttu-id="9a621-110">Le parti fondamentali di un tipo di informazioni sensibili personalizzato sono:</span><span class="sxs-lookup"><span data-stu-id="9a621-110">The fundamental parts of a custom sensitive information type are:</span></span>

- <span data-ttu-id="9a621-111">**Criterio principale**: ID dipendente, numeri di progetto e così via. In genere è identificato da un'espressione regolare (RegEx), ma può anche essere un elenco di parole chiave.</span><span class="sxs-lookup"><span data-stu-id="9a621-111">**Primary pattern**: employee ID numbers, project numbers, etc. This is typically identified by a regular expression (RegEx), but it can also be a list of keywords.</span></span>

- <span data-ttu-id="9a621-p103">**Evidenza aggiuntiva**: si supponga di cercare un numero ID dipendente di nove cifre. Non tutti i numeri di nove cifre sono numeri ID dipendente, quindi è possibile cercare testo aggiuntivo: parole chiave come "dipendente", "badge", "ID" o altri criteri di testo basati su ulteriori espressioni regolari. Questa evidenza di supporto (denominata anche evidenza__ _corroborativa_) consente di aumentare la probabilità che il numero di nove cifre individuato nel contenuto sia davvero un numero ID dipendente.</span><span class="sxs-lookup"><span data-stu-id="9a621-p103">**Additional evidence**: Suppose you're looking for a nine-digit employee ID number. Not all nine-digit numbers are employee ID numbers, so you can look for additional text: keywords like "employee", "badge", "ID", or other text patterns based on additional regular expressions. This supporting evidence (also known as _supporting_ or _corroborative_ evidence) increases the likelihood that nine-digit number found in content is really an employee ID number.</span></span>

- <span data-ttu-id="9a621-p104">**Prossimità dei caratteri**: è logico che più il criterio principale e l'evidenza di supporto sono vicini tra loro, più è probabile che il contenuto rilevato sia quello che si sta cercando. È possibile specificare la distanza dei caratteri tra il criterio principale e l'evidenza di supporto (nota anche come _finestra di prossimità_) come mostrato nel diagramma seguente:</span><span class="sxs-lookup"><span data-stu-id="9a621-p104">**Character proximity**: It makes sense that the closer the primary pattern and the supporting evidence are to each other, the more likely the detected content is going to be what you're looking for. You can specify the character distance between the primary pattern and the supporting evidence (also known as the _proximity window_) as shown in the following diagram:</span></span>

    ![Diagramma dell'evidenza corroborativa e della finestra di prossimità](media/dc68e38e-dfa1-45b8-b204-89c8ba121f96.png)

- <span data-ttu-id="9a621-p105">**Livello di probabilità**: più evidenze di supporto si hanno, più alta è la probabilità che una corrispondenza contenga le informazioni sensibili che si stanno cercando. È possibile assegnare livelli di probabilità più elevati per le corrispondenze rilevate con altre evidenze.</span><span class="sxs-lookup"><span data-stu-id="9a621-p105">**Confidence level**: The more supporting evidence you have, the higher the likelihood that a match contains the sensitive information you're looking for. You can assign higher levels of confidence for matches that are detected by using more evidence.</span></span>

  <span data-ttu-id="9a621-p106">Quando viene soddisfatto, un criterio restituisce un numero e un livello di probabilità che è possibile utilizzare nelle condizioni nei criteri DLP. Quando si aggiunge una condizione per il rilevamento di un tipo di informazione riservata a un criterio DLP, è possibile modificare il numero e il livello di probabilità, come illustrato nel diagramma seguente:</span><span class="sxs-lookup"><span data-stu-id="9a621-p106">When satisfied, a pattern returns a count and confidence level, which you can use in the conditions in your DLP policies. When you add a condition for detecting a sensitive information type to a DLP policy, you can edit the count and confidence level as shown in the following diagram:</span></span>

    ![Numero di istanze e opzioni di precisione di corrispondenza](media/11d0b51e-7c3f-4cc6-96d8-b29bcdae1aeb.png)

## <a name="creating-custom-sensitive-information-types"></a><span data-ttu-id="9a621-123">Creazione dei tipi di informazioni sensibili personalizzati</span><span class="sxs-lookup"><span data-stu-id="9a621-123">Creating custom sensitive information types</span></span>

<span data-ttu-id="9a621-124">Per creare tipi di informazioni sensibili personalizzati nel Centro sicurezza e conformità, è possibile scegliere tra diverse opzioni:</span><span class="sxs-lookup"><span data-stu-id="9a621-124">To create custom sensitive information types in the Security & Compliance Center, you can choose from several options:</span></span>

- <span data-ttu-id="9a621-125">**Usare EDM** (novità!) È possibile configurare tipi di informazioni sensibili personalizzati tramite la classificazione basata su Exact Data Match (EDM).</span><span class="sxs-lookup"><span data-stu-id="9a621-125">**Use EDM** (NEW!) You can set up custom sensitive information types using Exact Data Match (EDM)-based classification.</span></span> <span data-ttu-id="9a621-126">Questo metodo consente di creare un tipo di informazioni sensibili dinamico usando un database protetto che è possibile aggiornare periodicamente.</span><span class="sxs-lookup"><span data-stu-id="9a621-126">This method enables you to create a dynamic sensitive information type using a secure database that you can refresh periodically.</span></span> <span data-ttu-id="9a621-127">Vedere [Creare un tipo di informazioni sensibili personalizzato con la classificazione basata su Exact Data Match ](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span><span class="sxs-lookup"><span data-stu-id="9a621-127">See [Create a custom sensitive information type with Exact Data Match based classification (Preview)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span></span>

- <span data-ttu-id="9a621-128">**Usare PowerShell** È possibile configurare tipi di informazioni riservate personalizzati con PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9a621-128">**Use PowerShell** You can set up custom sensitive information types using PowerShell.</span></span> <span data-ttu-id="9a621-129">Anche se questo metodo è più complesso rispetto all'utilizzo dell'interfaccia utente, offre più opzioni di configurazione.</span><span class="sxs-lookup"><span data-stu-id="9a621-129">Although this method is more complex than using the UI, you have more configuration options.</span></span> <span data-ttu-id="9a621-130">Vedere [Creare un tipo di informazioni sensibili personalizzato in PowerShell per Centro sicurezza e conformità](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="9a621-130">See [Create a custom sensitive information type in Security & Compliance Center PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span></span>

- <span data-ttu-id="9a621-131">**Usare l'interfaccia utente** È possibile configurare un tipo di informazioni sensibili personalizzato mediante l'interfaccia utente del Centro sicurezza e conformità.</span><span class="sxs-lookup"><span data-stu-id="9a621-131">**Use the UI** You can set up a custom sensitive information type using the Security & Compliance Center UI.</span></span> <span data-ttu-id="9a621-132">Con questo metodo, è possibile usare espressioni regolari, parole chiave e dizionari di parole chiave.</span><span class="sxs-lookup"><span data-stu-id="9a621-132">With this method, you can use regular expressions, keywords, and keyword dictionaries.</span></span> <span data-ttu-id="9a621-133">Per saperne di più, vedere [Creare un tipo di informazioni sensibili personalizzato](create-a-custom-sensitive-information-type.md).</span><span class="sxs-lookup"><span data-stu-id="9a621-133">To learn more, see [Create a custom sensitive information type](create-a-custom-sensitive-information-type.md).</span></span>



