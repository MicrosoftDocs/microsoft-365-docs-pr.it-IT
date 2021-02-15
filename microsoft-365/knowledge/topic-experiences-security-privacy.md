---
title: Sicurezza e privacy di Microsoft Viva Topics
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye, cjtan
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
description: Informazioni su come pianificare la sicurezza e la privacy di Microsoft Viva Topics
ms.openlocfilehash: be5be01bce117a80bd95ee268c193889eccea67f
ms.sourcegitcommit: a048fefb081953aefa7747c08da52a7722e77288
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2021
ms.locfileid: "50107793"
---
# <a name="microsoft-viva-topics-security-and-privacy"></a>Sicurezza e privacy di Microsoft Viva Topics

Gli argomenti utilizzano le funzionalità di sicurezza del contenuto esistenti in Microsoft 365, insieme ai controlli amministrativi, per controllare il contenuto generato dall'IA visualizzato agli utenti dell'organizzazione. È la combinazione di impostazioni di sicurezza di Microsoft 365 (autorizzazioni per siti, file e cartelle) e impostazioni di amministrazione degli argomenti che determinano cosa può vedere un determinato utente negli argomenti.

La configurazione degli argomenti non modifica i controlli di accesso esistenti nel contenuto dell'organizzazione. Gli utenti potranno vedere solo a cosa hanno già accesso.

In questo articolo viene descritto il funzionamento degli argomenti dal punto di vista della sicurezza e le opzioni che gli amministratori delle conoscenze e i responsabili della conoscenza hanno per controllare la visibilità degli argomenti. Leggere questo articolo come parte della pianificazione [degli argomenti.](plan-topic-experiences.md)

Prima di leggere questo [articolo,](topic-experiences-overview.md)è consigliabile [](manage-topics.md) conoscere gli argomenti, il Centro argomenti e come utilizzare gli argomenti del Centro argomenti. [](topic-center-overview.md)

## <a name="what-users-can-see-in-topics"></a>Cosa possono vedere gli utenti negli argomenti

Per visualizzare gli argomenti, un utente deve:

- Avere una licenza Viva Topics
- Essere un [visualizzatore di argomenti,](topic-experiences-knowledge-rules.md#change-who-can-see-topics-in-your-organization) [un collaboratore o un responsabile delle conoscenze](topic-experiences-user-permissions.md)

Questi due elementi consentono agli utenti di visualizzare l'accesso al Centro argomenti e di visualizzare le evidenziazioni e le schede degli argomenti.

I collaboratori di argomenti dispongono inoltre di autorizzazioni di [creazione](topic-experiences-user-permissions.md) e modifica per gli argomenti e i knowledge manager possono confermare o rimuovere gli argomenti.

Quando un argomento viene individuato per la prima volta, i knowledge manager possono vedere l'argomento nel centro argomenti. A seconda della completezza e della pertinenza dell'argomento, i visualizzatori di argomenti possono o meno vedere l'argomento presentato nelle schede argomento.

Gli argomenti possono contenere informazioni generate dall'intelligenza artificiale e informazioni aggiunte o modificate da collaboratori di argomenti o responsabili delle conoscenze.

- Le informazioni in un argomento aggiunto dall'intelligenza artificiale sono visibili solo agli utenti che hanno accesso al contenuto di origine.
- Il testo aggiunto o modificato manualmente da un collaboratore o un responsabile della conoscenza è visibile a tutti gli utenti che possono visualizzare l'argomento.

I visualizzatori di argomenti e i collaboratori possono visualizzare l'elenco degli argomenti confermati e pubblicati nel Centro argomenti, ma i dettagli dell'argomento che una determinata persona può visualizzare dipendono dalle autorizzazioni che hanno per il materiale di origine e dal fatto che l'argomento sia stato modificato manualmente.

Nella tabella seguente vengono descritti gli utenti, i visualizzatori di argomenti, i collaboratori e i responsabili delle conoscenze, che possono visualizzare in un determinato argomento in base alle relative autorizzazioni.

|Elemento dell'argomento|Cosa possono vedere gli utenti|
|:---------|:------------------|
|Nome argomento|Gli utenti possono visualizzare il nome dell'argomento di tutti gli argomenti nel Centro argomenti. Alcuni argomenti potrebbero non essere visibili se hanno una pertinenza bassa per l'utente.|
|Descrizione dell'argomento|Le descrizioni generate dall'intelligenza artificiale sono visibili solo agli utenti che dispongono delle autorizzazioni per il contenuto di origine. Le descrizioni immesse o modificate manualmente sono visibili a tutti gli utenti.|
|Persone|Gli utenti aggiunti sono visibili a tutti gli utenti. Gli utenti suggeriti sono visibili solo agli utenti che dispongono delle autorizzazioni per il contenuto di origine.|
|File|I file sono visibili solo agli utenti che dispongono delle autorizzazioni per il contenuto di origine.|
|Pagine|Le pagine sono visibili solo per gli utenti che dispongono delle autorizzazioni per il contenuto di origine.|
|Siti|I siti sono visibili solo per gli utenti che dispongono delle autorizzazioni per il contenuto di origine.|

## <a name="best-practices"></a>Procedure consigliate

Negli argomenti vengono presentate informazioni agli utenti in base alle autorizzazioni esistenti per il contenuto. Microsoft 365 offre diversi modi per garantire che i contenuti sensibili siano limitati agli utenti appropriati. Oltre alle autorizzazioni standard del team o [](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies) del sito, è possibile [](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview) utilizzare le etichette di riservatezza o la prevenzione della perdita dei dati per limitare l'accesso al contenuto e alle revisioni degli accessi per esaminare periodicamente l'accesso degli utenti alle informazioni riservate. [](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels)

È consigliabile utilizzare questi strumenti per garantire che le autorizzazioni per il contenuto siano impostate in modo appropriato all'interno dell'organizzazione. Le esperienze degli argomenti possono quindi fornire informazioni utili e appropriate agli utenti.

Se sono presenti argomenti che si desidera escludere completamente dalle esperienze degli argomenti, è anche possibile:

- [Escludere i siti di SharePoint sensibili dall'individuazione degli argomenti.](topic-experiences-discovery.md#select-sharepoint-topic-sources) Il contenuto di questi siti non verrà visualizzato nelle esperienze degli argomenti.

- [Escludere gli argomenti in base al nome.](topic-experiences-discovery.md#exclude-topics-by-name) Gli argomenti esclusi esplicitamente non verranno visualizzati nelle esperienze degli argomenti.

- Fare in modo che i knowledge manager rimuovono gli argomenti nel Centro argomenti.

È inoltre consigliabile eseguire queste procedure consigliate:

- Selezionare i responsabili della conoscenza da diverse aree dell'organizzazione. Avere knowledge manager con una vasta gamma di competenze e l'accesso ai contenuti sottostanti usati dall'intelligenza artificiale può aiutarti a curarti delle conoscenze più utili per i tuoi utenti e rimuovere le informazioni riservate se trovate.

- Impostare un flusso di lavoro per la richiesta di modifiche. I responsabili delle conoscenze o i proprietari del team o del sito devono disporre di un processo tramite il quale possono richiedere l'esclusione di argomenti o siti quando vengono avviati nuovi progetti all'interno dell'organizzazione o se trovano contenuto con impostazioni di autorizzazioni inappropriate.

- Tenere presente il gruppo di destinatari e la riservatezza delle informazioni durante la creazione delle descrizioni degli argomenti. Queste descrizioni possono essere visibili agli utenti che non dispongono delle autorizzazioni per il contenuto di origine per l'argomento.

Sebbene sia possibile modificare le autorizzazioni nelle singole pagine degli argomenti per limitare l'accesso a un gruppo specifico di utenti, questo approccio non è consigliato a causa dell'elevato impegno amministrativo richiesto.

## <a name="see-also"></a>Vedere anche

[Configurare Teams con tre livelli di protezione](../solutions/configure-teams-three-tiers-protection.md)

[Pianificare le esperienze dell'argomento](plan-topic-experiences.md)

[Configurare le esperienze dell'argomento](set-up-topic-experiences.md)
