---
title: Argomenti sicurezza e privacy
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: nkokoye, cjtan
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: MET150
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Informazioni su come pianificare la sicurezza e la privacy di un argomento in Microsoft 365
ms.openlocfilehash: 7b88e5bbc8158ebd7dea65b2ecbf77085651b439
ms.sourcegitcommit: 1a9f0f878c045e1ddd59088ca2a94397605a242a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/14/2020
ms.locfileid: "49668248"
---
# <a name="topic-experiences-security-and-privacy"></a>Argomenti sicurezza e privacy

L'argomento Experiences utilizza le funzionalità di sicurezza del contenuto esistenti in Microsoft 365, insieme ai controlli di rete della Knowledge base, per controllare cosa viene mostrato ai contenuti generati da ai utenti dell'organizzazione. È la combinazione delle impostazioni di sicurezza di Microsoft 365 (autorizzazioni per siti, file e cartelle) e le impostazioni di amministrazione degli argomenti che determinano le operazioni che un utente specifico può visualizzare in un argomento.

Se si configura la rete della Knowledge base, non vengono modificati i controlli di accesso esistenti per il contenuto dell'organizzazione. Gli utenti vedranno solo quello a cui hanno già accesso.

In questo articolo viene illustrato il funzionamento delle esperienze di argomento da un punto di vista della sicurezza e le opzioni che gli amministratori della conoscenza e i Knowledge Manager devono controllare la visibilità degli argomenti. Leggere questo articolo come parte della [pianificazione per le esperienze di argomento](plan-topic-experiences.md).

Prima di leggere questo articolo, è consigliabile avere familiarità con le [esperienze](knowledge-management-overview.md)sugli argomenti, il [centro](topic-center-overview.md)argomenti e le modalità di [utilizzo dei temi nell'argomento centro](work-with-topics.md) .

## <a name="what-users-can-see-in-topics"></a>Elementi che gli utenti possono visualizzare negli argomenti

Per visualizzare gli argomenti, un utente deve:

- Avere una licenza per l'argomento experiences
- Essere un [Visualizzatore di argomenti](topic-experiences-knowledge-rules.md#change-who-can-see-topics-in-your-organization), un [collaboratore o un responsabile della conoscenza](topic-experiences-user-permissions.md)

Queste due cose offrono agli utenti l'accesso al centro dell'argomento e gli consentono di visualizzare i punti salienti e le schede degli argomenti.

I collaboratori degli argomenti hanno inoltre la possibilità di [creare e modificare](topic-experiences-user-permissions.md#change-who-has permissions-to-update-topic-details) le autorizzazioni per i temi e i Knowledge Manager possono confermare o rimuovere gli argomenti.

Quando un argomento viene individuato per la prima volta, i Knowledge Manager possono visualizzarlo nell'argomento centro. A seconda della completezza e della pertinenza dell'argomento, è possibile che gli utenti possano o meno vedere l'argomento presentato nelle schede degli argomenti.

Gli argomenti possono contenere informazioni generate da AI e informazioni aggiunte o modificate da parte di collaboratori o responsabili della conoscenza.

- Le informazioni contenute in un argomento aggiunto da AI sono visibili solo agli utenti che hanno accesso al contenuto di origine.
- Il testo che è stato aggiunto o modificato manualmente da un collaboratore dell'argomento o Knowledge Manager è visibile a tutti gli utenti che possono visualizzare l'argomento.

L'argomento visualizzatori e collaboratori può visualizzare l'elenco degli argomenti confermati e pubblicati nel centro argomenti, ma l'argomento dettagli che può essere visualizzato da una determinata persona dipende dalle autorizzazioni necessarie per il materiale di origine e dal fatto che l'argomento sia stato modificato manualmente.

Nella tabella seguente vengono descritti gli utenti, ovvero i visualizzatori di argomenti, i collaboratori e i Knowledge Manager, che possono essere visualizzati in un argomento specifico in base alle autorizzazioni.

|Elemento dell'argomento|Cosa possono vedere gli utenti|
|:---------|:------------------|
|Nome dell'argomento|Gli utenti possono visualizzare il nome dell'argomento di tutti gli argomenti nel centro argomenti. Alcuni argomenti potrebbero non essere visibili se l'utente ha una scarsa pertinenza.|
|Descrizione argomento|Le descrizioni generate AI sono visibili solo per gli utenti che dispongono delle autorizzazioni per il contenuto di origine. Le descrizioni inserite o modificate manualmente sono visibili a tutti gli utenti.|
|Persone|Le persone bloccate sono visibili a tutti gli utenti. Le persone suggerite sono visibili solo agli utenti che dispongono delle autorizzazioni per il contenuto di origine.|
|File|I file sono visibili solo agli utenti che dispongono delle autorizzazioni per il contenuto di origine.|
|Pagine|Le pagine sono visibili solo agli utenti che dispongono delle autorizzazioni per il contenuto di origine.|
|Siti|I siti sono visibili solo agli utenti che dispongono delle autorizzazioni per il contenuto di origine.|

## <a name="best-practices"></a>Procedure consigliate

L'argomento experiences fornisce informazioni agli utenti in base alle autorizzazioni esistenti per il contenuto. Microsoft 365 offre una vasta gamma di modi per garantire che il contenuto riservato sia limitato agli utenti più idonei. Oltre alle autorizzazioni del sito o del team standard, è possibile utilizzare le [etichette di riservatezza](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) o la [prevenzione della perdita di dati](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies) per limitare l'accesso al contenuto e accedere alle [recensioni](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview) per esaminare periodicamente l'accesso degli utenti alle informazioni riservate

È consigliabile utilizzare questi strumenti per assicurarsi che le autorizzazioni per il contenuto siano impostate in modo appropriato all'interno dell'organizzazione. L'argomento Experience può quindi fornire informazioni utili e appropriate per gli utenti.

Se sono presenti argomenti che si desidera escludere completamente dalle esperienze di argomento, è possibile anche:

- [Escludere i siti di SharePoint sensibili dall'individuazione degli argomenti](topic-experiences-discovery.md#select-sharepoint-topic-sources). Il contenuto di tali siti non verrà visualizzato nelle esperienze degli argomenti.

- [Escludi argomenti per nome](topic-experiences-discovery.md#exclude-topics-by-name). Gli argomenti esclusi in modo esplicito non verranno visualizzati nelle esperienze di argomento.

- I responsabili della conoscenza rimuovono gli argomenti nel centro argomenti.

È inoltre consigliabile eseguire le procedure consigliate seguenti:

- Reclutare Knowledge Manager provenienti da diverse aree dell'organizzazione. L'utilizzo di Knowledge Manager con una vasta gamma di competenze e l'accesso al contenuto sottostante utilizzato dall'AI può aiutare a curare le conoscenze più utili per gli utenti e a rimuovere le informazioni riservate se trovate.

- Impostare un flusso di lavoro per la richiesta di modifiche. I Knowledge Manager o i proprietari del sito o del team devono disporre di un processo tramite il quale è possibile richiedere l'esclusione di argomenti o siti quando i nuovi progetti vengono avviati all'interno dell'organizzazione o se trovano contenuto con le impostazioni delle autorizzazioni inappropriate.

- Tenere presente il gruppo di destinatari e la riservatezza delle informazioni durante la creazione di descrizioni degli argomenti. Queste descrizioni possono essere visibili agli utenti che non dispongono delle autorizzazioni per il contenuto di origine per l'argomento.

Anche se è possibile modificare le autorizzazioni per le pagine di singoli argomenti per limitare l'accesso a un gruppo specifico di utenti, non è consigliabile questo approccio a causa dell'elevato grado di sforzo amministrativo necessario.

## <a name="see-also"></a>Vedere anche

[Configurare Teams con tre livelli di protezione](../solutions/configure-teams-three-tiers-protection.md)

[Pianificare le esperienze sugli argomenti](plan-topic-experiences.md)

[Configurare le esperienze degli argomenti](set-up-topic-experiences.md)
