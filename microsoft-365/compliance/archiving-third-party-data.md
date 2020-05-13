---
title: Archiviare i dati di terze parti
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
search.appverid:
- MOE150
- MET150
ms.assetid: 0ce338d5-3666-4a18-86ab-c6910ff408cc
ms.custom:
- seo-marvel-apr2020
description: Informazioni su come importare i dati di terze parti dalle piattaforme per i social media, dalle piattaforme di messaggistica istantanea e dalle piattaforme di collaborazione documenti alle cassette postali di Microsoft 365.
ms.openlocfilehash: 2d011fcb63e0ec9804ade62f9fdcd1dd95fbf798
ms.sourcegitcommit: ab0a944159d9349fbc7adc2f51c7f881254d7782
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "44210537"
---
# <a name="archive-third-party-data"></a><span data-ttu-id="c1696-103">Archiviare i dati di terze parti</span><span class="sxs-lookup"><span data-stu-id="c1696-103">Archive third-party data</span></span>

<span data-ttu-id="c1696-104">Microsoft 365 consente agli amministratori di importare e archiviare i dati di terze parti dalle piattaforme per i social media, dalle piattaforme di messaggistica istantanea e dalle piattaforme di collaborazione documenti, alle cassette postali nell'organizzazione Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c1696-104">Microsoft 365 lets administrators import and archive third-party data from social media platforms, instant messaging platforms, and document collaboration platforms, to mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="c1696-105">Di seguito sono riportati alcuni esempi di origini dati di terze parti che è possibile importare in Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="c1696-105">Examples of third-party data sources that you can import to Microsoft 365 include the following services:</span></span> 
  
- <span data-ttu-id="c1696-106">**Social Networking:** Facebook, LinkedIn, Twitter e Yammer</span><span class="sxs-lookup"><span data-stu-id="c1696-106">**Social:** Facebook, LinkedIn, Twitter, and Yammer</span></span>

- <span data-ttu-id="c1696-107">**Messaggistica immediata:** Yahoo Messenger e GoogleTalk</span><span class="sxs-lookup"><span data-stu-id="c1696-107">**Instant messaging:** Yahoo Messenger and GoogleTalk</span></span>

- <span data-ttu-id="c1696-108">**Collaborazione documenti:** Casella e DropBox</span><span class="sxs-lookup"><span data-stu-id="c1696-108">**Document collaboration:** Box and DropBox</span></span>

- <span data-ttu-id="c1696-109">**Settori verticali:** Gestione delle relazioni con i clienti (come Salesforce Chatter) e servizi finanziari (come Bloomberg e Thomson Reuters)</span><span class="sxs-lookup"><span data-stu-id="c1696-109">**Vertical industries:** Customer Relationship Management (such as Salesforce Chatter) and Financial Services (such as Bloomberg and Thomson Reuters)</span></span>

- <span data-ttu-id="c1696-110">**Messaggi SMS/di testo:** BlackBerry</span><span class="sxs-lookup"><span data-stu-id="c1696-110">**SMS/text messaging:** BlackBerry</span></span>

<span data-ttu-id="c1696-111">Dopo aver importato i dati di terze parti, è possibile applicare le funzionalità di conformità di Microsoft 365, ad esempio conservazione per controversia legale, eDiscovery, archiviazione sul posto, controllo, conformità alla comunicazione e criteri di mantenimento a questi dati.</span><span class="sxs-lookup"><span data-stu-id="c1696-111">After third-party data is imported, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, In-Place Archiving, Auditing, Communication compliance, and retention policies to this data.</span></span> <span data-ttu-id="c1696-112">Ad esempio, quando una cassetta postale viene inserita nella conservazione per controversia legale, vengono conservati i dati di terze parti.</span><span class="sxs-lookup"><span data-stu-id="c1696-112">For example, when a mailbox is placed on Litigation Hold, third-party data is preserved.</span></span> <span data-ttu-id="c1696-113">È possibile eseguire la ricerca di dati di terze parti tramite gli strumenti di Microsoft eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="c1696-113">You can search third-party data by using Microsoft eDiscovery tools.</span></span> <span data-ttu-id="c1696-114">In alternativa, è possibile applicare i criteri di archiviazione e conservazione ai dati di terze parti, esattamente come è possibile per i dati di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c1696-114">Or you can apply archiving and retention policies to third-party data just like you can for Microsoft data.</span></span> <span data-ttu-id="c1696-115">In breve, l'archiviazione dei dati di terze parti in Microsoft 365 può aiutare l'organizzazione a rimanere conforme ai criteri governativi e normativi.</span><span class="sxs-lookup"><span data-stu-id="c1696-115">In short, archiving third-party data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

<span data-ttu-id="c1696-116">Esistono due modi per importare e archiviare i dati di terze parti in Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="c1696-116">There are two ways to import and archive third-party data in Microsoft 365:</span></span>

- <span data-ttu-id="c1696-117">**Utilizzare un connettore di dati di terze parti nel centro sicurezza & Compliance:** Utilizzare un connettore di dati personalizzato disponibile nel centro conformità di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c1696-117">**Use a third-party data connector in the Security & Compliance Center:** Use a custom data connector that's available in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="c1696-118">Dopo aver configurato e configurato il connettore, si connette all'origine dati di terze parti, converte il contenuto di un elemento in un formato di messaggio di posta elettronica e quindi importa l'elemento in una cassetta postale in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c1696-118">After you set up and configure the connector, it connects to the third-party data source, converts the content of an item to an email message format, and then imports the item to a mailbox in Microsoft 365.</span></span> <span data-ttu-id="c1696-119">Attualmente, è possibile implementare i connettori per importare e archiviare i dati da pagine business di Facebook, account Twitter aziendali, LinkedIn, Instant Bloomberg e i dati delle risorse umane (HR) dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c1696-119">Currently, you can implement connectors to import and archive data from Facebook Business pages, corporate Twitter accounts, LinkedIn, Instant Bloomberg, and your organization's human resources (HR) data.</span></span> <span data-ttu-id="c1696-120">Per istruzioni dettagliate sulla configurazione di uno di questi connettori, vedere:</span><span class="sxs-lookup"><span data-stu-id="c1696-120">For the step-by-step instructions to set up one of these connectors, see:</span></span>

   - <span data-ttu-id="c1696-121">**Facebook:** [utilizzare un connettore per archiviare i dati di Facebook (anteprima)](archive-facebook-data-with-sample-connector.md)</span><span class="sxs-lookup"><span data-stu-id="c1696-121">**Facebook:** [Use a connector to archive Facebook data (preview)](archive-facebook-data-with-sample-connector.md)</span></span>

   - <span data-ttu-id="c1696-122">**Twitter:** [utilizzare un connettore per archiviare i dati di Twitter (anteprima)](archive-twitter-data-with-sample-connector.md)</span><span class="sxs-lookup"><span data-stu-id="c1696-122">**Twitter:** [Use a connector to archive Twitter data (preview)](archive-twitter-data-with-sample-connector.md)</span></span>

   - <span data-ttu-id="c1696-123">**LinkedIn:** [configurare un connettore per archiviare i dati di LinkedIn](archive-linkedin-data.md)</span><span class="sxs-lookup"><span data-stu-id="c1696-123">**LinkedIn:** [Set up a connector to archive LinkedIn data](archive-linkedin-data.md)</span></span>

   - <span data-ttu-id="c1696-124">**Instant Bloomberg:** [impostare un connettore per archiviare i dati di Bloomberg istantanei](archive-instant-bloomberg-data.md)</span><span class="sxs-lookup"><span data-stu-id="c1696-124">**Instant Bloomberg:** [Set up a connector to archive Instant Bloomberg data](archive-instant-bloomberg-data.md)</span></span>

   - <span data-ttu-id="c1696-125">**Dati HR:** [impostare un connettore per importare i dati HR (anteprima)](import-hr-data.md)</span><span class="sxs-lookup"><span data-stu-id="c1696-125">**HR data:** [Set up a connector to import HR data (preview)](import-hr-data.md)</span></span>

- <span data-ttu-id="c1696-126">**Collaborare con un partner Microsoft:** L'organizzazione collabora con un partner Microsoft che fornirà un connettore personalizzato che verrà configurato per estrarre periodicamente elementi dall'origine dati di terze parti e quindi connettersi a Microsoft Cloud da un'API di terze parti e importare tali elementi in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c1696-126">**Work with a Microsoft partner:** Your organization works with a Microsoft Partner who will provide a custom connector that will be configured to extract items from the third-party data source on a regular basis and then connect to the Microsoft cloud by a third-party API and import those items to Microsoft 365.</span></span> <span data-ttu-id="c1696-127">Il connettore partner converte anche il contenuto di un elemento dall'origine dati di terze parti a un messaggio di posta elettronica e quindi lo importa in una cassetta postale in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c1696-127">The partner connector also converts the content of an item from the third-party data source to an email message and then imports it to a mailbox in Microsoft 365.</span></span> <span data-ttu-id="c1696-128">Per un elenco di partner che è possibile utilizzare e il processo dettagliato per questo metodo, vedere [collaborare con un partner per archiviare i dati di terze parti in Microsoft 365](work-with-partner-to-archive-third-party-data.md).</span><span class="sxs-lookup"><span data-stu-id="c1696-128">For a list of partners that you can work with and the step-by-step process for this method, see [Work with a partner to archive third-party data in Microsoft 365](work-with-partner-to-archive-third-party-data.md).</span></span>
