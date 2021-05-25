---
title: Gestire gli argomenti nel Centro argomenti in Microsoft Viva Topics
description: Come gestire gli argomenti nel Centro argomenti.
author: chuckedmonson
ms.author: chucked
manager: pamgreen
ms.reviewer: ergradel
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-topics
localization_priority: None
ms.openlocfilehash: f2429b0ffdd4a238bc9322ae9199eebbbfd407b5
ms.sourcegitcommit: 07e536f1a6e335f114da55048844e4a866fe731b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2021
ms.locfileid: "52651159"
---
# <a name="manage-topics-in-the-topic-center-in-microsoft-viva-topics"></a>Gestire gli argomenti nel Centro argomenti in Microsoft Viva Topics

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LxDx]  

</br>

Nel Centro argomenti Viva, un responsabile  della knowledge base può visualizzare la pagina Gestisci argomenti per esaminare gli argomenti identificati nelle posizioni di origine come specificato dall'amministratore della knowledge base.  

   ![Centro argomenti](../media/knowledge-management/topic-center.png)  

## <a name="topic-stages"></a>Fasi dell'argomento

I knowledge manager aiutano a guidare gli argomenti individuati nelle varie fasi del ciclo di vita degli argomenti: **Suggerite,** **Confermate,** **Pubblicate** e **Rimosse.**

   ![Grafico ciclo di vita degli argomenti](../media/knowledge-management/topic-lifecycle.png) 

- **Consigliati**: un argomento è stato identificato dall'IA e ha risorse di supporto, connessioni e proprietà sufficienti. Questi argomenti sono contrassegnati come **argomento consigliato** nell'interfaccia utente.

- **Confirmed**: Argomento che è stato individuato dall'IA ed è stato convalidato. La convalida degli argomenti si verifica quando:

   - Un responsabile della conoscenza conferma un argomento. Un responsabile [della knowledge base conferma un argomento](manage-topics.md#confirmed-topics) nella pagina **Gestisci** argomenti.

   - Più utenti confermano un argomento. Deve essere presente una rete di due voti positivi ricevuti dagli utenti che hanno votato usando il meccanismo di feedback nella scheda dell'argomento. Ad esempio, se un utente ha votato positivo e un utente ha votato negativo per un determinato argomento, sarebbero comunque necessari altri due voti positivi per confermare l'argomento.
 
- **Published**: Argomento che è stato curato. Sono state apportate modifiche manuali per migliorarne la qualità o sono state create da un utente.

- **Rimosso**: argomento rifiutato e non più visibile per i visualizzatori. Un argomento può essere rimosso in qualsiasi stato (suggerito, confermato o pubblicato). La rimozione degli argomenti si verifica quando:

   - Un responsabile della conoscenza rimuove un argomento. Un responsabile della knowledge base rimuove un argomento nella **pagina Gestisci** argomenti.

   - Più utenti votano negativamente usando il meccanismo di feedback nella scheda dell'argomento. Per rimuovere un argomento, deve essere presente una rete di due voti negativi ricevuti dagli utenti. Ad esempio, se un utente ha votato negativo e un utente ha votato positivo per un determinato argomento, sarebbero comunque necessari altri due voti negativi per rimuovere l'argomento.

  Quando un argomento pubblicato viene rimosso, la pagina con i dettagli curati dovrà essere eliminata manualmente tramite la raccolta pagine del Centro argomenti.

> [!Note] 
> Nella pagina **Gestisci argomenti,** ogni knowledge manager potrà visualizzare solo gli argomenti in cui hanno accesso ai file e alle pagine sottostanti connessi all'argomento. Questa limitazione delle autorizzazioni verrà riflessa nell'elenco degli argomenti visualizzati nelle schede Suggerite, **Confermate,** **Pubblicate** **e Rimosse.** Il conteggio degli argomenti, tuttavia, mostra i conteggi totali nell'organizzazione indipendentemente dalle autorizzazioni.

## <a name="requirements"></a>Requisiti

Per gestire gli argomenti nel Centro argomenti, è necessario:
- Avere una licenza di Viva Topics.

- Disporre [**dell'autorizzazione Who gestire gli argomenti.**](./topic-experiences-user-permissions.md) Gli amministratori delle informazioni possono assegnare questa autorizzazione nelle impostazioni delle autorizzazioni per gli argomenti di Viva Topics. 

Non sarà possibile visualizzare  la pagina Gestisci argomenti nel Centro argomenti a meno che non si dispone dell'autorizzazione Who **gestire gli** argomenti.

Nel Centro argomenti, un responsabile della conoscenza può esaminare gli argomenti identificati nelle posizioni di origine specificate e può confermarli o rimuoverli. Un responsabile della conoscenza può anche creare e pubblicare nuove pagine di argomento se non ne è stata trovata una nell'individuazione degli argomenti o modificare quelle esistenti se è necessario aggiornarne una.

## <a name="review-suggested-topics"></a>Esaminare gli argomenti suggeriti

Nella pagina **Gestisci argomenti** gli argomenti individuati nei percorsi di origine SharePoint specificati verranno elencati nella **scheda Suggeriti.** Se necessario, un responsabile della knowledge base può esaminare gli argomenti non confermati e scegliere di confermarli o rimuoverli.

   ![Argomenti suggeriti](../media/knowledge-management/quality-score.png) 

Per esaminare un argomento consigliato:

1. Nella pagina **Gestisci argomenti** selezionare la **scheda** Suggeriti e quindi selezionare l'argomento per aprire la pagina dell'argomento.

2. Nella pagina dell'argomento esaminare la pagina dell'argomento e selezionare **Modifica** se è necessario apportare modifiche alla pagina. La pubblicazione di eventuali modifiche sposterà questo argomento nella **scheda Published.**

3. Dopo aver esaminato l'argomento, tornare alla **pagina Gestisci** argomenti. Per l'argomento selezionato è possibile:

   - Selezionare il segno di spunta per confermare l'argomento.
    
   - Selezionare la **x** se si desidera rimuovere l'argomento.

    Gli argomenti confermati verranno rimossi **dall'elenco Suggeriti** e ora verranno visualizzati **nell'elenco** Confermati.

    Gli argomenti rimossi verranno rimossi **dall'elenco Suggeriti** e ora verranno visualizzati nella **scheda** Rimosso.

### <a name="quality-score"></a>Punteggio qualità

A ogni argomento visualizzato nella **pagina Argomenti** suggeriti è assegnato un punteggio di qualità. Il punteggio di qualità è un riflesso della quantità di informazioni che l'utente medio visualizza per le informazioni sull'argomento, tenendo presente che ogni utente potrebbe visualizzare più o meno informazioni a causa delle autorizzazioni che potrebbero o meno avere sulle informazioni in un argomento. 

Il punteggio di qualità può contribuire a fornire informazioni approfondite sugli argomenti con la maggior parte delle informazioni e può essere utile per trovare argomenti che potrebbero essere modificati manualmente. Ad esempio, un argomento con un punteggio di qualità inferiore potrebbe essere il risultato di alcuni utenti che non hanno autorizzazioni SharePoint per i file o i siti pertinenti inclusi nell'argomento. Un contributore potrebbe quindi modificare l'argomento in modo da includere le informazioni (se appropriato), che saranno poi visualizzabili a tutti gli utenti autorizzati a visualizzare l'argomento.

### <a name="impressions"></a>Impression

Nella **colonna Impressions** viene visualizzato il numero di volte in cui un argomento è stato visualizzato agli utenti finali. Sono incluse le visualizzazioni tramite le schede di risposta degli argomenti nella ricerca e le evidenziazioni degli argomenti. Non riflette il click-through su questi argomenti, ma che l'argomento è stato visualizzato. La **colonna Impressions** verrà visualizzata per gli argomenti nelle  schede **Suggerite,** Confermate, **Pubblicate** e Rimosse della **pagina Gestisci** argomenti. 

## <a name="confirmed-topics"></a>Argomenti confermati

Nella  pagina Gestisci argomenti, gli argomenti individuati nelle posizioni di origine SharePoint specificate e confermati da un responsabile della conoscenza o "crowdsourced" confermati da due o più persone nette (bilanciamento dei voti negativi degli utenti rispetto ai voti degli utenti positivi) tramite il meccanismo di feedback della scheda saranno elencati nella **scheda Confermata.** Se necessario, un utente con autorizzazioni per gestire gli argomenti può esaminare gli argomenti confermati e scegliere di rifiutarli.

Per rivedere un argomento confermato:

1. Nella scheda **Confermati** selezionare l'argomento per aprire la pagina dell'argomento.

2. Nella pagina dell'argomento esaminare la pagina dell'argomento e selezionare **Modifica** se è necessario apportare modifiche alla pagina.

Tieni presente che puoi comunque scegliere di rifiutare un argomento confermato. A tale scopo, passare all'argomento selezionato **nella** scheda Confermata e selezionare **la x** se si desidera rifiutare l'argomento.

## <a name="published-topics"></a>Argomenti pubblicati

Gli argomenti pubblicati sono stati modificati in modo che informazioni specifiche vengano sempre visualizzate a chiunque incontri la pagina. Qui sono elencati anche gli argomenti creati manualmente.

   ![Gestire gli argomenti](../media/knowledge-management/manage-topics-new.png)

## <a name="topic-count-dashboard"></a>Dashboard conteggio argomenti

Questo grafico nella visualizzazione dashboard consente di visualizzare il numero di argomenti nel centro argomenti Viva Topics. Il grafico mostra i conteggi degli argomenti per ogni fase del ciclo di vita dell'argomento e mostra anche l'andamento dei conteggi degli argomenti nel tempo. I knowledge manager possono monitorare visivamente la frequenza con cui i nuovi argomenti vengono individuati dall'IA e la frequenza con cui gli argomenti vengono confermati o pubblicati dal knowledge manager o dalle azioni degli utenti.

I knowledge manager potrebbero visualizzare un numero diverso di argomenti rappresentati nell'elenco degli argomenti nella pagina **Gestisci** argomenti rispetto a quelli visualizzati nel dashboard. Ciò è dovuto al fatto che un responsabile della conoscenza potrebbe non avere accesso a tutti gli argomenti. Il conteggio presentato nella visualizzazione dashboard viene effettuato prima di applicare la limitazione delle autorizzazioni. 

   ![Screenshot del dashboard per il conteggio degli argomenti](../media/knowledge-management/topic-count-dashboard.png)
