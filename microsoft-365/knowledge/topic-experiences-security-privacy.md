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
ms.openlocfilehash: b8c82b1914df739ea9086a4ce1585733a7b6d854
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925492"
---
# <a name="microsoft-viva-topics-security-and-privacy"></a>Sicurezza e privacy di Microsoft Viva Topics

Gli argomenti utilizzano le funzionalità di sicurezza del contenuto esistenti in Microsoft 365, insieme ai controlli amministrativi, per controllare quale contenuto generato dall'IA viene visualizzato agli utenti dell'organizzazione. È la combinazione di Microsoft 365 di sicurezza (autorizzazioni per siti, file e cartelle) e impostazioni di amministrazione degli argomenti che determinano cosa può vedere un determinato utente negli argomenti.

La configurazione di Argomenti non modifica i controlli di accesso esistenti per il contenuto dell’organizzazione. Gli utenti possono visualizzare solo quelli a cui si ha già accesso.

In questo articolo viene descritto il funzionamento degli argomenti dal punto di vista della sicurezza e le opzioni che gli amministratori della knowledge base e i responsabili della conoscenza hanno per controllare la visibilità degli argomenti. Leggere questo articolo come parte della pianificazione [per Argomenti](plan-topic-experiences.md).

Prima di leggere [questo](topic-experiences-overview.md)articolo, [](topic-center-overview.md)è consigliabile [](manage-topics.md) avere familiarità con gli argomenti, il Centro argomenti e come utilizzare gli argomenti del Centro argomenti.

## <a name="what-users-can-see-in-topics"></a>Cosa possono vedere gli utenti negli argomenti

Per visualizzare gli argomenti, un utente deve:

- Avere una licenza Viva Topics
- Essere un [visualizzatore di argomenti,](topic-experiences-knowledge-rules.md#change-who-can-see-topics-in-your-organization) [un collaboratore o un responsabile della conoscenza](topic-experiences-user-permissions.md)

Questi due aspetti consentono agli utenti di visualizzare l'accesso al Centro argomenti e di visualizzare le evidenziazioni e le schede degli argomenti.

I collaboratori di argomenti dispongono inoltre di [autorizzazioni](topic-experiences-user-permissions.md) di creazione e modifica per gli argomenti e i knowledge manager possono confermare o rimuovere gli argomenti.

Quando un argomento viene individuato per la prima volta, i knowledge manager possono vederlo nel centro argomenti. A seconda della completezza e della pertinenza dell'argomento, i visualizzatori di argomenti possono o meno vedere l'argomento presentato nelle schede degli argomenti.

Gli argomenti possono contenere informazioni generate dall'IA e informazioni aggiunte o modificate da collaboratori o knowledge manager.

- Le informazioni in un argomento aggiunte dall'intelligenza artificiale sono visibili solo alle persone che hanno accesso al contenuto di origine.
- Il testo aggiunto o modificato manualmente da un collaboratore o da un responsabile della conoscenza è visibile a tutti gli utenti che possono visualizzare l'argomento.

I visualizzatori di argomenti e i collaboratori possono visualizzare l'elenco degli argomenti confermati e pubblicati nel Centro argomenti, ma i dettagli dell'argomento che una determinata persona può visualizzare dipendono dalle autorizzazioni di cui dispone per il materiale di origine e dal fatto che l'argomento sia stato modificato manualmente.

Nella tabella seguente vengono descritti gli elementi che gli utenti, i visualizzatori di argomenti, i collaboratori e i responsabili della conoscenza, possono visualizzare in un determinato argomento in base alle autorizzazioni.

|Oggetto dell'argomento|Argomenti che gli utenti possono visualizzare|
|:---------|:------------------|
|Nome dell'argomento|Gli utenti possono visualizzare il nome degli argomenti nel Centro argomenti. Alcuni argomenti potrebbero non essere visibili se gli utenti non dispongono delle autorizzazioni per il contenuto di origine o hanno una pertinenza bassa per l'utente.|
|Descrizione dell'argomento|Le descrizioni generate dall'IA sono visibili solo agli utenti che dispongono delle autorizzazioni per il contenuto di origine. Le descrizioni immesse o modificate manualmente sono visibili a tutti gli utenti.|
|Persone|Le persone bloccate sono visibili a tutti gli utenti. Le persone suggerite sono visibili solo agli utenti che dispongono delle autorizzazioni per il contenuto di origine.|
|File|I file sono visibili solo agli utenti che dispongono delle autorizzazioni per il contenuto di origine.|
|Pagine|Le pagine sono visibili solo agli utenti che dispongono delle autorizzazioni per il contenuto di origine.|
|Siti|I siti sono visibili solo agli utenti che dispongono delle autorizzazioni per il contenuto di origine.|

## <a name="users-personal-and-private-data"></a>Dati personali e privati degli utenti

Viva Topics consente di individuare solo gli argomenti SharePoint siti specificati. L'archiviazione personale degli utenti, ad esempio la posta OneDrive, non è inclusa.

## <a name="best-practices"></a>Procedure consigliate

Gli argomenti presentano informazioni agli utenti in base alle autorizzazioni esistenti per il contenuto. Microsoft 365 offre diversi modi per garantire che il contenuto riservato sia limitato agli utenti appropriati. Oltre alle autorizzazioni standard del team o [](../compliance/dlp-learn-about-dlp.md) del sito, è possibile [](/azure/active-directory/governance/access-reviews-overview) utilizzare le etichette di riservatezza o la prevenzione della perdita dei dati per limitare l'accesso al contenuto e le revisioni di accesso per esaminare periodicamente l'accesso degli utenti alle informazioni riservate. [](../compliance/sensitivity-labels.md)

È consigliabile utilizzare questi strumenti per assicurarsi che le autorizzazioni per il contenuto siano impostate in modo appropriato all'interno dell'organizzazione. Le esperienze con Topics potranno poi fornire agli utenti informazioni utili e appropriate.

Se sono presenti argomenti che si desidera escludere completamente dalle esperienze degli argomenti, è anche possibile:

- [Escludere i siti SharePoint sensibili dall'individuazione degli argomenti.](topic-experiences-discovery.md#select-sharepoint-topic-sources) I contenuti di questi siti non appariranno nelle esperienze con Topics.

- [Escludere gli argomenti in base al nome](topic-experiences-discovery.md#exclude-topics-by-name). Gli argomenti esplicitamente esclusi non appariranno nelle esperienze con Topics.

- Fare in modo che i knowledge manager rimuovono gli argomenti nel Centro argomenti.

Inoltre, è consigliabile eseguire le procedure consigliate seguenti:

- Reclutare knowledge manager da diverse aree dell'organizzazione. Avere knowledge manager con una vasta gamma di competenze e l'accesso al contenuto sottostante utilizzato dall'IA può aiutare a curarsi delle conoscenze più utili per gli utenti e rimuovere le informazioni riservate, se trovate.

- Configurare un flusso di lavoro per la richiesta di modifiche. I knowledge manager o i proprietari del team o del sito devono disporre di un processo in base al quale possono richiedere l'esclusione di argomenti o siti quando vengono avviati nuovi progetti all'interno dell'organizzazione o se trovano contenuto con impostazioni di autorizzazioni inappropriate.

- In fase di creazione delle descrizioni degli argomenti, è necessario essere consapevoli del gruppo di destinatari e della riservatezza delle informazioni. Tali descrizioni potrebbero risultare visibili a utenti che non dispongono di autorizzazione per l'accesso ai contenuti di origine dell'argomento.

Anche se è possibile limitare l'accesso a un gruppo di utenti specifico modificando le autorizzazioni nella pagina dedicata a un certo argomento, questo approccio non è consigliato per l'elevato grado di impegno amministrativo richiesto.

## <a name="see-also"></a>Vedere anche

[Configurare Teams con tre livelli di protezione](../solutions/configure-teams-three-tiers-protection.md)

[Pianificare le esperienze dell'argomento](plan-topic-experiences.md)

[Configurare le esperienze dell'argomento](set-up-topic-experiences.md)
