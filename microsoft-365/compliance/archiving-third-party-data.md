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
# <a name="archive-third-party-data"></a>Archiviare i dati di terze parti

Microsoft 365 consente agli amministratori di importare e archiviare i dati di terze parti dalle piattaforme per i social media, dalle piattaforme di messaggistica istantanea e dalle piattaforme di collaborazione documenti, alle cassette postali nell'organizzazione Microsoft 365. Di seguito sono riportati alcuni esempi di origini dati di terze parti che è possibile importare in Microsoft 365: 
  
- **Social Networking:** Facebook, LinkedIn, Twitter e Yammer

- **Messaggistica immediata:** Yahoo Messenger e GoogleTalk

- **Collaborazione documenti:** Casella e DropBox

- **Settori verticali:** Gestione delle relazioni con i clienti (come Salesforce Chatter) e servizi finanziari (come Bloomberg e Thomson Reuters)

- **Messaggi SMS/di testo:** BlackBerry

Dopo aver importato i dati di terze parti, è possibile applicare le funzionalità di conformità di Microsoft 365, ad esempio conservazione per controversia legale, eDiscovery, archiviazione sul posto, controllo, conformità alla comunicazione e criteri di mantenimento a questi dati. Ad esempio, quando una cassetta postale viene inserita nella conservazione per controversia legale, vengono conservati i dati di terze parti. È possibile eseguire la ricerca di dati di terze parti tramite gli strumenti di Microsoft eDiscovery. In alternativa, è possibile applicare i criteri di archiviazione e conservazione ai dati di terze parti, esattamente come è possibile per i dati di Microsoft. In breve, l'archiviazione dei dati di terze parti in Microsoft 365 può aiutare l'organizzazione a rimanere conforme ai criteri governativi e normativi.

Esistono due modi per importare e archiviare i dati di terze parti in Microsoft 365:

- **Utilizzare un connettore di dati di terze parti nel centro sicurezza & Compliance:** Utilizzare un connettore di dati personalizzato disponibile nel centro conformità di Microsoft 365. Dopo aver configurato e configurato il connettore, si connette all'origine dati di terze parti, converte il contenuto di un elemento in un formato di messaggio di posta elettronica e quindi importa l'elemento in una cassetta postale in Microsoft 365. Attualmente, è possibile implementare i connettori per importare e archiviare i dati da pagine business di Facebook, account Twitter aziendali, LinkedIn, Instant Bloomberg e i dati delle risorse umane (HR) dell'organizzazione. Per istruzioni dettagliate sulla configurazione di uno di questi connettori, vedere:

   - **Facebook:** [utilizzare un connettore per archiviare i dati di Facebook (anteprima)](archive-facebook-data-with-sample-connector.md)

   - **Twitter:** [utilizzare un connettore per archiviare i dati di Twitter (anteprima)](archive-twitter-data-with-sample-connector.md)

   - **LinkedIn:** [configurare un connettore per archiviare i dati di LinkedIn](archive-linkedin-data.md)

   - **Instant Bloomberg:** [impostare un connettore per archiviare i dati di Bloomberg istantanei](archive-instant-bloomberg-data.md)

   - **Dati HR:** [impostare un connettore per importare i dati HR (anteprima)](import-hr-data.md)

- **Collaborare con un partner Microsoft:** L'organizzazione collabora con un partner Microsoft che fornirà un connettore personalizzato che verrà configurato per estrarre periodicamente elementi dall'origine dati di terze parti e quindi connettersi a Microsoft Cloud da un'API di terze parti e importare tali elementi in Microsoft 365. Il connettore partner converte anche il contenuto di un elemento dall'origine dati di terze parti a un messaggio di posta elettronica e quindi lo importa in una cassetta postale in Microsoft 365. Per un elenco di partner che è possibile utilizzare e il processo dettagliato per questo metodo, vedere [collaborare con un partner per archiviare i dati di terze parti in Microsoft 365](work-with-partner-to-archive-third-party-data.md).
