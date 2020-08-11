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
ms.openlocfilehash: e192ea19345da0c168b2bb09fd8ec51959ea47fb
ms.sourcegitcommit: 51f040a4edb8dd52521a5d7b0f7a975986a1af10
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/10/2020
ms.locfileid: "46608323"
---
# <a name="archive-third-party-data"></a>Archiviare i dati di terze parti

Microsoft 365 consente agli amministratori di utilizzare i connettori di dati per importare e archiviare i dati di terze parti dalle piattaforme di social networking, dalle piattaforme di messaggistica istantanea e dalle piattaforme di collaborazione documenti, alle cassette postali nell'organizzazione Microsoft 365. Un vantaggio principale dell'utilizzo dei connettori di dati per l'importazione e l'archiviazione dei dati di terze parti in Microsoft 365 è che è possibile applicare diverse soluzioni di conformità a Microsoft 365 dopo che è stato importato. In questo modo è possibile verificare che i dati non Microsoft dell'organizzazione siano conformi alle normative e agli standard che influiscono sull'organizzazione.

## <a name="third-party-data-connectors"></a>Connettori dati di terze parti

Nella tabella seguente sono elencati i connettori di dati di terze parti disponibili nel centro conformità di Microsoft 365. Nella tabella vengono riepilogate anche le soluzioni di conformità che è possibile applicare ai dati di terze parti dopo l'importazione e l'archiviazione in Microsoft 365. Vedere la [sezione successiva](#overview-of-compliance-solutions-that-support-third-party-data) per una descrizione più dettagliata di ogni soluzione di conformità e in che modo può trarre vantaggio dai dati di terze parti.

> [!TIP]
> Fare clic sul collegamento nella colonna di **dati di terze parti** per passare alle istruzioni dettagliate per la creazione di un connettore per il tipo di dati.

|Dati di terze parti  |Blocco per controversia legale|eDiscovery  |Criteri di conservazione  |Gestione dei record  |Conformità delle comunicazioni  |Gestione dei rischi Insider  |
|:---------|:---------|:---------|:---------|:---------|:---------|:---------|
|[Dati Android <sup>1</sup>](archive-android-archiver-data.md)     |![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|||
|[Nei dati di rete di&T <sup>1</sup>](archive-att-network-archiver-data.md)     |![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|||
|[Dati della rete Bell <sup>1</sup>](archive-bell-network-data.md)     |![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|||
|[Messaggio Bloomberg](archive-bloomberg-message-data.md)     |![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|[Dati numerici organizzazione <sup>1</sup>](archive-enterprise-number-data.md)     |![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|||
|[Facebook](archive-facebook-data-with-sample-connector.md)     |![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|||
|[Dati sulle risorse umane](import-hr-data.md) ||||||![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|[Chat di ghiaccio](archive-icechat-data.md)     |![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|[Bloomberg istantaneo](archive-instant-bloomberg-data.md)|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|[LinkedIn](archive-linkedin-data.md)   |![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|||
|[Dati di rete O2 <sup>1</sup>](archive-o2-network-data.md)     |![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|||
|[Dati di rete TELUS <sup>1</sup>](archive-telus-network-data.md)    |![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|||
|[Twitter](archive-twitter-data-with-sample-connector.md)     |![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|||
|[Dati di rete Verizon <sup>1</sup>](archive-verizon-network-data.md)     |![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|||
|[WhatsApp <sup>1</sup>](archive-whatsapp-data.md)     |![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![Segno di spunta](../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|||
||||||||

> [!NOTE]
> <sup>1</sup> connettore fornito da TeleMessage. Prima di poter archiviare i dati in Microsoft 365, è necessario collaborare con TeleMessage per configurare il servizio di archiviazione per l'organizzazione. Per ulteriori informazioni, vedere la sezione prerequisito nelle istruzioni dettagliate per questo tipo di dati.
>

I dati di terze parti elencati nella tabella precedente (ad eccezione dei dati HR) vengono importati nelle cassette postali degli utenti. Le corrispondenti soluzioni di conformità che supportano i dati di terze parti vengono applicate alla cassetta postale dell'utente in cui sono archiviati i dati.

## <a name="overview-of-compliance-solutions-that-support-third-party-data"></a>Panoramica delle soluzioni di conformità che supportano i dati di terze parti

Nelle sezioni seguenti vengono descritte alcune delle soluzioni di conformità di Microsoft 365 che consentono di gestire i dati di terze parti elencati nella tabella precedente.

### <a name="litigation-hold"></a>Blocco per controversia legale

Per mantenere i dati di terze parti, è necessario inserire un [blocco per controversia legale](create-a-litigation-hold.md) su una cassetta postale utente. Quando si crea un'esenzione, è possibile specificare una durata del blocco, denominata anche *blocco basato sul tempo*, in modo che i dati di terze parti eliminati e modificati vengano conservati per un periodo specificato e quindi eliminati definitivamente dalla cassetta postale. In alternativa, è possibile conservare il contenuto a tempo indeterminato (denominato *blocco infinito*) oppure fino a quando non viene rimosso il blocco per controversia legale.

### <a name="ediscovery"></a>eDiscovery

I tre strumenti principali di eDiscovery in Microsoft 365 sono content search, Core eDiscovery e Advanced eDiscovery.

- **[Ricerca contenuto](content-search.md).** È possibile utilizzare lo strumento di ricerca contenuto per cercare le cassette postali per i dati di terze parti importati. È possibile utilizzare le query di ricerca e le condizioni per restringere i risultati della ricerca e l'esportazione dei risultati della ricerca.

- **[EDiscovery di base](get-started-core-ediscovery.md).** Questo strumento si basa sulla funzionalità di ricerca e di esportazione di base, consentendo di creare casi che consentono di controllare chi può accedere ai dati del caso, inserire un'esenzione sulle cassette postali degli utenti o sul contenuto delle cassette postali che corrisponde ai criteri di ricerca. Questo significa che è possibile inserire un blocco eDiscovery sui dati di terze parti importati nelle cassette postali degli utenti.

- **[EDiscovery avanzato](overview-ediscovery-20.md).** Questo potente strumento espande la funzionalità dei casi di eDiscovery di base, consentendo di aggiungere i depositari a un caso, mettendo in attesa i dati del custode e quindi caricando i dati di terze parti di un custode in una recensione per ulteriori analisi quali temi e rilevamento duplicati. Dopo aver caricato i dati di terze parti in un set di revisione, è possibile eseguirne la query e filtrarli in un set di risultati stretto.

   Sia eDiscovery core che Advanced eDiscovery consentono di gestire i dati di terze parti che possono essere rilevanti per le indagini legali o interne dell'organizzazione.

### <a name="retention-policies"></a>Criteri di conservazione

È possibile applicare un [criterio di conservazione](retention.md) alle cassette postali degli utenti per conservare e quindi eliminare i dati di terze parti (e altri contenuti delle cassette postali) dopo la scadenza del periodo di conservazione. È inoltre possibile utilizzare i criteri di conservazione per eliminare i dati di terze parti di una determinata età o per attivare una revisione della disposizione al termine della scadenza del periodo di conservazione.

### <a name="records-management"></a>Gestione dei record

La funzionalità di [gestione dei record](records-management.md) in Microsoft 365 consente di dichiarare i dati di terze parti come record. Questa operazione può essere svolta manualmente dagli utenti che applicano un'etichetta di conservazione che consente di contrassegnare i dati di terze parti nella cassetta postale come record. In alternativa, è possibile applicare automaticamente le etichette di conservazione identificando informazioni riservate, parole chiave o tipi di contenuto in dati di terze parti.

### <a name="communication-compliance"></a>Conformità delle comunicazioni

È possibile utilizzare la [conformità della comunicazione](communication-compliance.md) per esaminare i dati di terze parti per assicurarsi che siano conformi agli standard dei dati dell'organizzazione. A tale scopo, è possibile rilevare, acquisire ed eseguire azioni correttive per i messaggi inopportuni nell'organizzazione. Ad esempio, è possibile monitorare i dati di terze parti che vengono importati per la lingua offensiva, le informazioni riservate e la conformità alle normative.

### <a name="insider-risk-management"></a>Gestione dei rischi Insider

I segnali provenienti da dati di terze parti, come i dati di tipo HR selettivo, possono essere utilizzati dalla soluzione di [gestione dei rischi Insider](insider-risk-management.md) per ridurre al minimo i rischi interni, consentendo di rilevare, indagare e agire su attività rischiose nell'organizzazione. Ad esempio, i dati importati dal connettore di dati HR vengono utilizzati come indicatori di rischio per individuare il furto dei dati derivanti dall'utilizzo della parte dipendente.

## <a name="working-with-a-microsoft-partner-to-archive-third-party-data"></a>Utilizzo di un partner Microsoft per l'archiviazione dei dati di terze parti

Un'altra opzione per l'importazione e l'archiviazione dei dati di terze parti consiste nell'utilizzo da parte dell'organizzazione di un partner Microsoft. Se un tipo di dati di terze parti non è supportato dai connettori dati disponibili nel centro conformità Microsoft, è possibile collaborare con un partner che può fornire un connettore personalizzato che verrà configurato per estrarre periodicamente gli elementi dall'origine dati di terze parti e quindi connettersi a Microsoft Cloud da un'API di terze parti e importare tali elementi in Microsoft 365. Il connettore partner converte anche il contenuto di un elemento dall'origine dati di terze parti a un messaggio di posta elettronica e quindi lo importa in una cassetta postale in Microsoft 365.

Per un elenco di partner che è possibile utilizzare e il processo dettagliato per questo metodo, vedere [collaborare con un partner per archiviare i dati di terze parti in Microsoft 365](work-with-partner-to-archive-third-party-data.md).
