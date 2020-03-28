---
title: Archiviazione dei dati di terze parti
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid: MOE150
ms.assetid: 0ce338d5-3666-4a18-86ab-c6910ff408cc
description: Gli amministratori possono importare i dati di terze parti dalle piattaforme per i social media, dalle piattaforme di messaggistica istantanea e dalle piattaforme di collaborazione documenti alle cassette postali nell'organizzazione Microsoft 365. In questo modo è possibile archiviare i dati da Facebook, Twitter e altre origini dati di terze parti in Microsoft 365. È quindi possibile utilizzare e applicare le funzionalità di conformità di Microsoft 365 (come la conservazione legale, eDiscovery, l'archiviazione sul posto e i criteri di mantenimento) per i dati di terze parti.
ms.openlocfilehash: 72afb48f74a30bac2904e857a33487a83eba48cd
ms.sourcegitcommit: f9b5eca20e025acc36635cbd1786ff3407295857
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/27/2020
ms.locfileid: "43027656"
---
# <a name="archive-third-party-data"></a><span data-ttu-id="de099-105">Archiviazione dei dati di terze parti</span><span class="sxs-lookup"><span data-stu-id="de099-105">Archive third-party data</span></span>

<span data-ttu-id="de099-106">Microsoft 365 consente agli amministratori di importare e archiviare i dati di terze parti dalle piattaforme per i social media, dalle piattaforme di messaggistica istantanea e dalle piattaforme di collaborazione documenti, alle cassette postali nell'organizzazione Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="de099-106">Microsoft 365 lets administrators import and archive third-party data from social media platforms, instant messaging platforms, and document collaboration platforms, to mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="de099-107">Di seguito sono riportati alcuni esempi di origini dati di terze parti che è possibile importare in Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="de099-107">Examples of third-party data sources that you can import to Microsoft 365 include the following services:</span></span> 
  
- <span data-ttu-id="de099-108">**Social Networking:** Facebook, LinkedIn, Twitter e Yammer</span><span class="sxs-lookup"><span data-stu-id="de099-108">**Social:** Facebook, LinkedIn, Twitter, and Yammer</span></span>

- <span data-ttu-id="de099-109">**Messaggistica immediata:** Yahoo Messenger e GoogleTalk</span><span class="sxs-lookup"><span data-stu-id="de099-109">**Instant messaging:** Yahoo Messenger and GoogleTalk</span></span>

- <span data-ttu-id="de099-110">**Collaborazione documenti:** Casella e DropBox</span><span class="sxs-lookup"><span data-stu-id="de099-110">**Document collaboration:** Box and DropBox</span></span>

- <span data-ttu-id="de099-111">**Settori verticali:** Gestione delle relazioni con i clienti (come Salesforce Chatter) e servizi finanziari (come Bloomberg e Thomson Reuters)</span><span class="sxs-lookup"><span data-stu-id="de099-111">**Vertical industries:** Customer Relationship Management (such as Salesforce Chatter) and Financial Services (such as Bloomberg and Thomson Reuters)</span></span>

- <span data-ttu-id="de099-112">**Messaggi SMS/di testo:** BlackBerry</span><span class="sxs-lookup"><span data-stu-id="de099-112">**SMS/text messaging:** BlackBerry</span></span>

<span data-ttu-id="de099-113">Dopo aver importato i dati di terze parti, è possibile applicare le funzionalità di conformità di Microsoft 365, ad esempio conservazione per controversia legale, eDiscovery, archiviazione sul posto, controllo, conformità alla comunicazione e criteri di mantenimento a questi dati.</span><span class="sxs-lookup"><span data-stu-id="de099-113">After third-party data is imported, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, In-Place Archiving, Auditing, Communication compliance, and retention policies to this data.</span></span> <span data-ttu-id="de099-114">Ad esempio, quando una cassetta postale viene inserita nella conservazione per controversia legale, vengono conservati i dati di terze parti.</span><span class="sxs-lookup"><span data-stu-id="de099-114">For example, when a mailbox is placed on Litigation Hold, third-party data is preserved.</span></span> <span data-ttu-id="de099-115">È possibile eseguire la ricerca di dati di terze parti tramite gli strumenti di Microsoft eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="de099-115">You can search third-party data by using Microsoft eDiscovery tools.</span></span> <span data-ttu-id="de099-116">In alternativa, è possibile applicare i criteri di archiviazione e conservazione ai dati di terze parti, esattamente come è possibile per i dati di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="de099-116">Or you can apply archiving and retention policies to third-party data just like you can for Microsoft data.</span></span> <span data-ttu-id="de099-117">In breve, l'archiviazione dei dati di terze parti in Microsoft 365 può aiutare l'organizzazione a rimanere conforme ai criteri governativi e normativi.</span><span class="sxs-lookup"><span data-stu-id="de099-117">In short, archiving third-party data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

<span data-ttu-id="de099-118">Esistono due modi per importare e archiviare i dati di terze parti in Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="de099-118">There are two ways to import and archive third-party data in Microsoft 365:</span></span>

- <span data-ttu-id="de099-119">**Utilizzare un connettore di dati di terze parti nel centro sicurezza & Compliance:** Utilizzare un connettore di dati personalizzato disponibile nel centro conformità di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="de099-119">**Use a third-party data connector in the Security & Compliance Center:** Use a custom data connector that's available in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="de099-120">Dopo aver configurato e configurato il connettore, si connette all'origine dati di terze parti, converte il contenuto di un elemento in un formato di messaggio di posta elettronica e quindi importa l'elemento in una cassetta postale in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="de099-120">After you set up and configure the connector, it connects to the third-party data source, converts the content of an item to an email message format, and then imports the item to a mailbox in Microsoft 365.</span></span> <span data-ttu-id="de099-121">Attualmente, è possibile implementare i connettori per importare e archiviare i dati da pagine business di Facebook, account Twitter aziendali, LinkedIn, Instant Bloomberg e i dati delle risorse umane (HR) dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="de099-121">Currently, you can implement connectors to import and archive data from Facebook Business pages, corporate Twitter accounts, LinkedIn, Instant Bloomberg, and your organization's human resources (HR) data.</span></span> <span data-ttu-id="de099-122">Per istruzioni dettagliate sulla configurazione di uno di questi connettori, vedere:</span><span class="sxs-lookup"><span data-stu-id="de099-122">For the step-by-step instructions to set up one of these connectors, see:</span></span>

   - <span data-ttu-id="de099-123">**Facebook:** [utilizzare un connettore per archiviare i dati di Facebook](archive-facebook-data-with-sample-connector.md)</span><span class="sxs-lookup"><span data-stu-id="de099-123">**Facebook:** [Use a connector to archive Facebook data](archive-facebook-data-with-sample-connector.md)</span></span>

   - <span data-ttu-id="de099-124">**Twitter:** [utilizzare un connettore per archiviare i dati di Twitter](archive-twitter-data-with-sample-connector.md)</span><span class="sxs-lookup"><span data-stu-id="de099-124">**Twitter:** [Use a connector to archive Twitter data](archive-twitter-data-with-sample-connector.md)</span></span>

   - <span data-ttu-id="de099-125">**LinkedIn:** [configurare un connettore per archiviare i dati di LinkedIn](archive-linkedin-data.md)</span><span class="sxs-lookup"><span data-stu-id="de099-125">**LinkedIn:** [Set up a connector to archive LinkedIn data](archive-linkedin-data.md)</span></span>

   - <span data-ttu-id="de099-126">**Instant Bloomberg:** [impostare un connettore per archiviare i dati di Bloomberg istantanei](archive-instant-bloomberg-data.md)</span><span class="sxs-lookup"><span data-stu-id="de099-126">**Instant Bloomberg:** [Set up a connector to archive Instant Bloomberg data](archive-instant-bloomberg-data.md)</span></span>

   - <span data-ttu-id="de099-127">**Dati HR:** [impostare un connettore per importare i dati HR](import-hr-data.md)</span><span class="sxs-lookup"><span data-stu-id="de099-127">**HR data:** [Set up a connector to import HR data](import-hr-data.md)</span></span>

- <span data-ttu-id="de099-128">**Collaborare con un partner Microsoft:** L'organizzazione collabora con un partner Microsoft che fornirà un connettore personalizzato che verrà configurato per estrarre periodicamente elementi dall'origine dati di terze parti e quindi connettersi a Microsoft Cloud da un'API di terze parti e importare tali elementi in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="de099-128">**Work with a Microsoft partner:** Your organization works with a Microsoft Partner who will provide a custom connector that will be configured to extract items from the third-party data source on a regular basis and then connect to the Microsoft cloud by a third-party API and import those items to Microsoft 365.</span></span> <span data-ttu-id="de099-129">Il connettore partner converte anche il contenuto di un elemento dall'origine dati di terze parti a un messaggio di posta elettronica e quindi lo importa in una cassetta postale in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="de099-129">The partner connector also converts the content of an item from the third-party data source to an email message and then imports it to a mailbox in Microsoft 365.</span></span> <span data-ttu-id="de099-130">Per un elenco di partner che è possibile utilizzare e il processo dettagliato per questo metodo, vedere [collaborare con un partner per archiviare i dati di terze parti in Microsoft 365](work-with-partner-to-archive-third-party-data.md).</span><span class="sxs-lookup"><span data-stu-id="de099-130">For a list of partners that you can work with and the step-by-step process for this method, see [Work with a partner to archive third-party data in Microsoft 365](work-with-partner-to-archive-third-party-data.md).</span></span>
