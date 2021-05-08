---
title: Panoramica di Microsoft Viva Topics
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-topics
localization_priority: None
description: Panoramica di Viva Topics.
ms.openlocfilehash: b37572087794055724cb9533246f83794d88fb93
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275199"
---
# <a name="microsoft-viva-topics-overview"></a>Panoramica di Microsoft Viva Topics 

Viva Topics utilizza la tecnologia Microsoft AI, Microsoft 365, Microsoft Graph, Search e altri componenti e servizi per portare la conoscenza ai tuoi utenti nelle app Microsoft 365 che usano tutti i giorni, a partire dalle pagine moderne di SharePoint e Microsoft Search.

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LhZP]  

</br>

Viva Topics aiuta ad affrontare un problema aziendale chiave in molte aziende: fornire le informazioni agli utenti quando ne hanno bisogno. Ad esempio, i nuovi dipendenti devono apprendere rapidamente molte nuove informazioni e incontrano termini di cui non sanno nulla quando leggono le informazioni aziendali. Per saperne di più, l'utente potrebbe dover allontanarsi da ciò che sta facendo e dedicare tempo prezioso alla ricerca di dettagli, come informazioni su quale sia il termine, chi nell'organizzazione è un esperto in materia e forse siti e documenti relativi al termine.

Viva Topics utilizza l'intelligenza artificiale per cercare e identificare automaticamente **argomenti** nell’organizzazione. Compila informazioni su di essi, come una breve descrizione, persone che lavorano sull'argomento e siti, file e pagine ad esso correlati. Un responsabile informazioni o un collaboratore può scegliere di aggiornare le informazioni sull'argomento secondo necessità. Gli argomenti sono disponibili per gli utenti, il che significa che per ogni istanza dell'argomento che appare in un sito moderno di SharePoint nelle notizie e nelle pagine, il testo verrà evidenziato. Gli utenti possono scegliere di selezionare l'argomento per saperne di più attraverso i dettagli dell'argomento. Gli argomenti sono disponibili anche in SharePoint Search.


## <a name="how-topics-are-displayed-to-users"></a>Come vengono visualizzati gli argomenti agli utenti

Quando un argomento viene menzionato nel contenuto delle notizie e delle pagine di SharePoint, lo vedrai evidenziato. È possibile aprire il riepilogo dell'argomento dagli highlight. Apri i dettagli dell'argomento dal titolo del riepilogo. L'argomento menzionato potrebbe essere identificato automaticamente o essere stato aggiunto alla pagina con un riferimento diretto all'argomento dall'autore della pagina. 

   ![Highlight degli argomenti](../media/knowledge-management/saturn.png) 


   ![Screenshot che mostra la ricerca in Word tramite la casella di ricerca.](../media/knowledge-management/word-search-2.png)

   ![Screenshot che mostra la ricerca in Word tramite il menu di scelta rapida Ricerca.](../media/knowledge-management/word-search-1.png)

## <a name="knowledge-indexing"></a>Indicizzazione informazioni

Viva Topics utilizza la tecnologia Microsoft AI per identificare **argomenti** nell’ambiente Microsoft 365.

Un argomento è una frase o un termine significativo o importante dal punto di vista organizzativo. Ha un significato specifico per l'organizzazione e dispone di risorse ad essa correlate che possono aiutare le persone a capire di cosa si tratta e trovare maggiori informazioni al riguardo. Ci sono molti tipi di argomenti importanti per la tua organizzazione. Inizialmente, la tecnologia Microsoft AI si concentra sui seguenti tipi:
- Project
- Evento
- Organizzazione
- Posizione
- Prodotto
- Lavoro creativo
- Campo di studio


Quando un argomento viene identificato e l'IA determina di avere informazioni sufficienti perché esso sia un argomento suggerito, una **pagina dell’argomento** visualizza le informazioni raccolte tramite l'indicizzazione dell'argomento, come ad esempio:

- Nomi e acronimi alternativi.
- Una breve descrizione dell'argomento.
- Persone che potrebbero essere informate sull'argomento.
- File, pagine e siti correlati all'argomento.

Gli amministratori delle informazioni possono scegliere di eseguire la ricerca per indicizzazione di tutti i siti di SharePoint nel tenant o di selezionarne solo alcuni.

Vedere [Scoperta e conservazione dell'argomento](./topic-experiences-discovery-curation.md)

## <a name="roles"></a>Ruoli

Quando utilizzi Viva Topics nel tuo ambiente Microsoft 365, gli utenti avranno i seguenti ruoli:

- Visualizzatori di argomenti: utenti che possono vedere gli highlights degli argomenti nei siti moderni di SharePoint a cui hanno almeno accesso in *Lettura* e in Microsoft Search. Possono selezionare gli highlights dell'argomento per visualizzarne i dettagli nelle pagine degli argomenti. I visualizzatori di argomenti possono fornire feedback sull'utilità di un argomento.

- Collaboratori: utenti che dispongono dei diritti per modificare argomenti esistenti o crearne di nuovi. Gli amministratori delle informazioni autorizzano gli utenti a collaborare tramite le impostazioni di Viva Topics nell'interfaccia di amministrazione di Microsoft 365. Si noti che è possibile anche concedere a tutti i visualizzatori di argomenti l'autorizzazione a modificare e creare argomenti in modo che tutti possano contribuire agli argomenti che vedono.

- Responsabili informazioni: utenti che guidano gli argomenti attraverso il ciclo di vita degli argomenti. I responsabili delle informazioni utilizzano la pagina **Gestisci Argomenti** nel Centro argomenti per confermare gli argomenti suggeriti dall'IA, rimuovere gli argomenti non più rilevanti, nonché modificare gli argomenti esistenti o crearne di nuovi, e sono gli unici utenti che possono accedervi. Gli amministratori delle informazioni autorizzano i responsabili delle informazioni a collaborare tramite le impostazioni di Viva Topics nell'interfaccia di amministrazione di Microsoft 365. 

- Amministratori delle informazioni: gli amministratori delle informazioni configurano Viva Topics e lo gestiscono tramite i controlli di amministrazione nell'interfaccia di amministrazione di Microsoft 365. Attualmente, un amministratore globale di Microsoft 365 o di SharePoint può fungere da amministratore delle informazioni.

Vedere [Ruoli Viva Topics](topic-experiences-roles.md) per ulteriori informazioni.

## <a name="topic-management"></a>Gestione degli argomenti

La gestione degli argomenti avviene sulla pagina **Gestisci argomenti** nel **Centro argomenti** dell’organizzazione. Il Centro argomenti viene creato durante la configurazione e funge da centro informazioni per l’organizzazione. 

Sebbene tutti gli utenti con licenza possano visualizzare gli argomenti a cui sono connessi nel Centro argomenti, solo gli utenti con autorizzazioni *Gestisci argomenti* (responsabili informazioni) possono visualizzare e utilizzare la pagina Gestisci argomenti.

I responsabili informazioni possono:

- Confermare o rimuovere gli argomenti rilevati nel tuo tenant.
- Creare nuovi argomenti manualmente in base alle necessità (ad esempio, se non sono state fornite informazioni sufficienti per scoprirlo tramite IA).
- Modificare le pagine degli argomenti esistenti.</br>

Vedere [Gestisci argomenti nel Centro argomenti](manage-topics.md) per ulteriori informazioni.  


## <a name="admin-controls"></a>Controlli amministratore

I controlli di amministrazione nell'Microsoft 365 di amministrazione consentono di gestire Viva Topics. Consentono a un amministratore globale di Microsoft 365 o di SharePoint di:

- Controllare quali utenti dell'organizzazione possono visualizzare gli argomenti nelle pagine moderne di SharePoint o nei risultati della ricerca di SharePoint.
- Controllare quali siti di SharePoint verranno sottoposti a ricerca per indicizzazione per identificare gli argomenti.
- Escludere argomenti specifici dalla ricerca.
- Controllare quali utenti possono gestire gli argomenti nel Centro argomenti.
- Controllare quali utenti possono creare e modificare gli argomenti.
- Controllare quale utente può visualizzare gli argomenti.

Vedere [assegnare autorizzazioni utente](./plan-topic-experiences.md#user-permissions), [gestire visibilità argomento](./topic-experiences-knowledge-rules.md), e [gestire individuazione argomento](./topic-experiences-discovery.md) per ulteriori informazioni sui controlli amministratore.

## <a name="topic-curation--feedback"></a>Cura degli argomenti e feedback

L'IA lavorerà continuamente per fornirti suggerimenti per migliorare gli argomenti man mano che si verificano cambiamenti nel tuo ambiente. 

Gli utenti con autorizzazioni di modifica o creazione di argomenti possono aggiornare direttamente le pagine degli argomenti se desiderano apportare correzioni o aggiungere ulteriori informazioni. Possono anche aggiungere nuovi argomenti che l'IA non è stato in grado di identificare. Se ci sono abbastanza informazioni su questi argomenti aggiunti manualmente e l'IA è in grado di identificare questo tipo di argomento, ulteriori suggerimenti dall'IA potrebbero migliorare gli argomenti aggiunti manualmente 

Agli utenti a cui consenti l'accesso per visualizzare gli argomenti nel lavoro quotidiano potrebbe essere chiesto se l'argomento gli è stato utile. Il sistema esamina queste risposte e le utilizza per migliorare gli highlight dell'argomento e aiutare a determinare cosa viene mostrato nei riepiloghi degli argomenti e nei dettagli dell'argomento.

Inoltre, gli utenti con le autorizzazioni appropriate possono taggare elementi come conversazioni di Yammer che sono rilevanti per un argomento e aggiungerli a un argomento specifico. 

Vedere [Scoperta e conservazione dell'argomento](./topic-experiences-discovery-curation.md)


## <a name="see-also"></a>Vedere anche
