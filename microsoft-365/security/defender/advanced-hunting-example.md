---
title: Esempio di ricerca avanzata per Microsoft Defender per Office 365
description: Introduzione alla ricerca di minacce tramite posta elettronica tramite ricerca avanzata
keywords: ricerca avanzata, ricerca delle minacce, ricerca di minacce informatiche, Microsoft 365 Defender, Microsoft 365, m365, ricerca, query, telemetria, rilevamenti personalizzati, schema, kusto
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: d3ac49b4afde0951e7a034c5c11114afbc52c293
ms.sourcegitcommit: 1c11035dd4432e34603022740baef0c8f7ff4425
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2021
ms.locfileid: "52965145"
---
# <a name="advanced-hunting-example-for-microsoft-defender-for-office-365"></a><span data-ttu-id="36fd9-104">Esempio di ricerca avanzata per Microsoft Defender per Office 365</span><span class="sxs-lookup"><span data-stu-id="36fd9-104">Advanced hunting example for Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="36fd9-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="36fd9-105">**Applies to:**</span></span>
- <span data-ttu-id="36fd9-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="36fd9-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="36fd9-107">Iniziare a cercare le minacce tramite posta elettronica con la ricerca avanzata?</span><span class="sxs-lookup"><span data-stu-id="36fd9-107">Want to get started searching for email threats using advanced hunting?</span></span> <span data-ttu-id="36fd9-108">Provare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="36fd9-108">Try this:</span></span>

<span data-ttu-id="36fd9-109">La [guida introduttiva](/microsoft-365/security/office-365-security/defender-for-office-365#getting-started) dell'articolo [Microsoft Defender per Office 365](/microsoft-365/security/office-365-security/defender-for-office-365) include blocchi di configurazione iniziali logici simili ai seguenti:</span><span class="sxs-lookup"><span data-stu-id="36fd9-109">The [Getting Started](/microsoft-365/security/office-365-security/defender-for-office-365#getting-started) section of the [Microsoft Defender for Office 365 article](/microsoft-365/security/office-365-security/defender-for-office-365) has logical early configuration chunks that look like this:</span></span>

1. <span data-ttu-id="36fd9-110">Configura tutto con "Anti" nel nome.</span><span class="sxs-lookup"><span data-stu-id="36fd9-110">Configure everything with 'Anti' in the name.</span></span>
   - <span data-ttu-id="36fd9-111">Antimalware</span><span class="sxs-lookup"><span data-stu-id="36fd9-111">Anti-malware</span></span>
   - <span data-ttu-id="36fd9-112">Anti-phishing</span><span class="sxs-lookup"><span data-stu-id="36fd9-112">Anti-phishing</span></span>
   - <span data-ttu-id="36fd9-113">Protezione da posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="36fd9-113">Anti-spam</span></span>
2. <span data-ttu-id="36fd9-114">Configura tutto con "Safe" nel nome.</span><span class="sxs-lookup"><span data-stu-id="36fd9-114">Set up everything with 'Safe' in the name.</span></span>
   - <span data-ttu-id="36fd9-115">Collegamenti sicuri</span><span class="sxs-lookup"><span data-stu-id="36fd9-115">Safe Links</span></span>
   - <span data-ttu-id="36fd9-116">Allegati sicuri</span><span class="sxs-lookup"><span data-stu-id="36fd9-116">Safe Attachments</span></span>
3. <span data-ttu-id="36fd9-117">Difendere i carichi di lavoro (ad esempio</span><span class="sxs-lookup"><span data-stu-id="36fd9-117">Defend the workloads (ex.</span></span> <span data-ttu-id="36fd9-118">SharePoint Online, OneDrive e Teams).</span><span class="sxs-lookup"><span data-stu-id="36fd9-118">SharePoint Online, OneDrive, and Teams).</span></span>
4. <span data-ttu-id="36fd9-119">Proteggi con eliminazione automatica a zero ore.</span><span class="sxs-lookup"><span data-stu-id="36fd9-119">Protect with zero-Hour auto purge.</span></span>

<span data-ttu-id="36fd9-120">Oltre a un [collegamento](../office-365-security/protect-against-threats.md) per iniziare subito a eseguire la configurazione il primo giorno.</span><span class="sxs-lookup"><span data-stu-id="36fd9-120">Along with a [link](../office-365-security/protect-against-threats.md) to jump right in and get configuration going on Day 1.</span></span>

<span data-ttu-id="36fd9-121">L'ultimo passaggio in **guida introduttiva** consiste nella protezione degli utenti con la **Zero-Hour Auto Purge**, anche nota come ZAP.</span><span class="sxs-lookup"><span data-stu-id="36fd9-121">The last step in **Getting Started** is protecting users with **Zero-Hour auto purge**, also known as ZAP.</span></span> <span data-ttu-id="36fd9-122">Sapere se i provvedimenti per rimuovere con ZAP un messaggio sospetto o pericoloso dopo il recapito hanno avuto successo è molto importante.</span><span class="sxs-lookup"><span data-stu-id="36fd9-122">Knowing if your efforts to ZAP a suspicious or malicious mail, post-delivery, were successful can be very important.</span></span>

<span data-ttu-id="36fd9-123">Il passaggio rapido al linguaggio di query Kusto per rilevare problemi è un vantaggio derivante dalla convergenza di questi due centri sicurezza.</span><span class="sxs-lookup"><span data-stu-id="36fd9-123">Quickly navigating to Kusto query language to hunt for issues is an advantage of converging these two security centers.</span></span> <span data-ttu-id="36fd9-124">I team di sicurezza possono monitorare i mancati problemi zap facendo i loro passi successivi [qui,](https://security.microsoft.com/advanced-hunting)sotto **Ricerca** \> **avanzata**.</span><span class="sxs-lookup"><span data-stu-id="36fd9-124">Security teams can monitor ZAP misses by taking their next steps [here](https://security.microsoft.com/advanced-hunting), under **Hunting** \> **Advanced Hunting**.</span></span>

1. <span data-ttu-id="36fd9-125">Nella pagina Ricerca avanzata fare clic su **Query.**</span><span class="sxs-lookup"><span data-stu-id="36fd9-125">On the Advanced Hunting page, click **Query**.</span></span>
1. <span data-ttu-id="36fd9-126">Copiare la query seguente nella finestra Query.</span><span class="sxs-lookup"><span data-stu-id="36fd9-126">Copy the query below into the query window.</span></span>
1. <span data-ttu-id="36fd9-127">Selezionare **Esegui query**.</span><span class="sxs-lookup"><span data-stu-id="36fd9-127">Select **Run query**.</span></span>

```kusto
EmailPostDeliveryEvents 
| where Timestamp > ago(7d)
//List malicious emails that were not zapped successfullyconverge-2-endpoints-new.png
| where ActionType has "ZAP" and ActionResult == "Error"
| project ZapTime = Timestamp, ActionType, NetworkMessageId , RecipientEmailAddress 
//Get logon activity of recipients using RecipientEmailAddress and AccountUpn
| join kind=inner IdentityLogonEvents on $left.RecipientEmailAddress == $right.AccountUpn
| where Timestamp between ((ZapTime-24h) .. (ZapTime+24h))
//Show only pertinent info, such as account name, the app or service, protocol, the target device, and type of logon
| project ZapTime, ActionType, NetworkMessageId , RecipientEmailAddress, AccountUpn, 
LogonTime = Timestamp, AccountDisplayName, Application, Protocol, DeviceName, LogonType
```

:::image type="content" source="../../media/converge-13-advanced-hunt-an-email-zap-new.png" alt-text="La pagina Ricerca avanzata (in Ricerca) con query selezionata nella parte superiore del pannello di query ed esecuzione di una query Kusto per acquisire le azioni ZAP negli ultimi 7 giorni.":::

<span data-ttu-id="36fd9-129">I dati di questa query verranno visualizzati nel pannello Risultati sotto la query stessa.</span><span class="sxs-lookup"><span data-stu-id="36fd9-129">The data from this query will appear in the results panel below the query itself.</span></span> <span data-ttu-id="36fd9-130">I risultati includono informazioni come 'DeviceName', 'AccountDisplayName' e 'ZapTime' in un set di risultati personalizzabile.</span><span class="sxs-lookup"><span data-stu-id="36fd9-130">Results include information like 'DeviceName', 'AccountDisplayName', and 'ZapTime' in a customizable result set.</span></span> <span data-ttu-id="36fd9-131">È anche possibile esportare i risultati per i record.</span><span class="sxs-lookup"><span data-stu-id="36fd9-131">Results can also be exported for your records.</span></span> <span data-ttu-id="36fd9-132">Se la query è di nuovo necessaria, selezionare **Salva** > **Salva con nome** e aggiungere la query all'elenco di query, condivise o della community.</span><span class="sxs-lookup"><span data-stu-id="36fd9-132">If the query is one you'll need again, select **Save** > **Save As** and add the query to your list of queries, shared, or community queries.</span></span>

## <a name="related-information"></a><span data-ttu-id="36fd9-133">Informazioni correlate</span><span class="sxs-lookup"><span data-stu-id="36fd9-133">Related information</span></span>
- [<span data-ttu-id="36fd9-134">Procedure consigliate per la ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="36fd9-134">Advanced hunting best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="36fd9-135">Panoramica - Ricerca avanzata</span><span class="sxs-lookup"><span data-stu-id="36fd9-135">Overview - Advanced hunting</span></span>](advanced-hunting-overview.md)
