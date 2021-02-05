---
title: Panoramica di Microsoft Viva Topics
ms.author: efrene
author: efrene
manager: pamgreen
ms.reviewer: cjtan
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-topics
localization_priority: None
description: Panoramica degli argomenti viva.
ms.openlocfilehash: f45e0f7c6090d4584526aa9c2abb5ec98213d635
ms.sourcegitcommit: a048fefb081953aefa7747c08da52a7722e77288
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2021
ms.locfileid: "50107640"
---
# <a name="microsoft-viva-topics-overview"></a>Panoramica di Microsoft Viva Topics 

Viva Topics usa la tecnologia Microsoft AI, Microsoft 365, Microsoft Graph, Search e altri componenti e servizi per mettere a conoscenza gli utenti nelle app di Microsoft 365 che usano tutti i giorni, a partire dalle pagine moderne di SharePoint e Microsoft Search.

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LhZP]  

</br>

Viva Topics consente di risolvere un problema aziendale chiave in molte aziende, fornendo le informazioni agli utenti quando ne hanno bisogno. Ad esempio, i nuovi dipendenti devono imparare rapidamente molte nuove informazioni e trovare termini di cui non conoscono nulla durante la lettura delle informazioni aziendali. Per saperne di più, l'utente potrebbe dover allontanarsi da ciò che sta facendo e dedicare tempo prezioso alla ricerca di dettagli, ad esempio informazioni su cosa sia il termine, chi nell'organizzazione è un esperto in materia e forse siti e documenti correlati al termine.

Viva Topics usa l'intelligenza artificiale per cercare e identificare **automaticamente gli argomenti** nell'organizzazione. Vengono compilate informazioni su di esse, ad esempio una breve descrizione, persone che lavorano all'argomento e siti, file e pagine ad esso correlati. Un responsabile o un collaboratore può scegliere di aggiornare le informazioni sull'argomento in base alle esigenze. Gli argomenti sono disponibili per gli utenti, il che significa che per ogni istanza dell'argomento visualizzata in un sito di SharePoint moderno nelle notizie e nelle pagine, il testo verrà evidenziato. Gli utenti possono scegliere di selezionare l'argomento per saperne di più nei dettagli dell'argomento. Gli argomenti sono disponibili anche nel servizio di ricerca di SharePoint.


## <a name="how-topics-are-displayed-to-users"></a>Modalità di visualizzazione degli argomenti agli utenti

Quando un argomento viene menzionato nel contenuto delle notizie e delle pagine di SharePoint, viene evidenziato. Puoi aprire il riepilogo dell'argomento dall'evidenziazione. Aprire i dettagli dell'argomento dal titolo del riepilogo. L'argomento menzionato potrebbe essere identificato automaticamente o essere stato aggiunto alla pagina con un riferimento diretto all'argomento dall'autore della pagina. 

   ![Evidenziazioni degli argomenti](../media/knowledge-management/saturn.png) </br> 


## <a name="knowledge-indexing"></a>Indicizzazione delle informazioni

Viva Topics usa la tecnologia microsoft ai per **identificare gli** argomenti nell'ambiente Microsoft 365.

Un argomento è una frase o un termine che è importante o significativo a livello di organizzazione. Ha un significato specifico per l'organizzazione e ha risorse ad essa correlate che possono aiutare gli utenti a capire cos'è e trovare ulteriori informazioni su di esso. Esistono molti tipi diversi di argomenti che saranno importanti per l'organizzazione. Inizialmente, la tecnologia IA Di Microsoft si concentra sui seguenti tipi:
- Project
- Evento
- Organizzazione
- Posizione
- Prodotto
- Lavoro creativo
- Campo di studio


Quando un argomento viene identificato e l'intelligenza artificiale determina che dispone  di informazioni sufficienti per essere un argomento consigliato, una pagina dell'argomento visualizza le informazioni raccolte tramite l'indicizzazione dell'argomento, ad esempio:

- Nomi alternativi e acronimi.
- Breve descrizione dell'argomento.
- Persone che potrebbero essere a conoscenza dell'argomento.
- File, pagine e siti correlati all'argomento.

Gli amministratori della knowledge base possono scegliere di eseguire la ricerca per indicizzazione in tutti i siti di SharePoint nel tenant per argomenti o di selezionare solo determinati siti.

Vedere [Individuazione e cura degli argomenti](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery-curation)

## <a name="roles"></a>Ruoli

Quando si usano Viva Topics nell'ambiente Microsoft 365, gli utenti avranno i ruoli seguenti:

- Visualizzatori di argomenti: utenti che possono vedere gli argomenti  principali nei siti moderni di SharePoint a cui hanno almeno accesso in lettura e in Microsoft Search. Possono selezionare le evidenziazioni degli argomenti per visualizzare i dettagli degli argomenti nelle pagine degli argomenti. I visualizzatori di argomenti possono fornire feedback sull'utilità di un argomento per loro.

- Collaboratori: utenti che dispongono dei diritti per modificare gli argomenti esistenti o crearne di nuovi. Gli amministratori della knowledge base assegnano autorizzazioni di collaboratore agli utenti tramite le impostazioni Viva Topics nell'interfaccia di amministrazione di Microsoft 365. Tieni presente che puoi anche scegliere di concedere a tutti i visualizzatori di argomenti l'autorizzazione per modificare e creare argomenti in modo che tutti possano contribuire agli argomenti visualizzati.

- Responsabili della conoscenza: utenti che guidano gli argomenti nel ciclo di vita dell'argomento. I knowledge  manager utilizzano la pagina Gestisci argomenti nel Centro argomenti per confermare gli argomenti suggeriti dall'intelligenza artificiale, rimuovere gli argomenti non più pertinenti, nonché modificare gli argomenti esistenti o crearne di nuovi e sono gli unici utenti ad accedervi. Gli amministratori della knowledge base assegnano le autorizzazioni di knowledge manager agli utenti tramite le impostazioni di amministrazione viva topics nell'interfaccia di amministrazione di Microsoft 365. 

- Amministratori della knowledge base: gli amministratori della knowledge base configurano Viva Topics e lo gestiscono tramite i controlli di amministrazione nell'interfaccia di amministrazione di Microsoft 365. Attualmente, un amministratore globale o di SharePoint di Microsoft 365 può fungere da amministratore della knowledge base.

Per [ulteriori informazioni, vedere i](topic-experiences-roles.md) ruoli di Viva Topics.

## <a name="topic-management"></a>Gestione degli argomenti

La gestione degli argomenti viene eseguita nella **pagina Gestisci** argomenti nel Centro argomenti **dell'organizzazione.** Il Centro argomenti viene creato durante la configurazione e funge da centro di conoscenza per l'organizzazione. 

Mentre tutti gli utenti con licenza possono visualizzare gli argomenti  a cui sono connessi nel Centro argomenti, solo gli utenti con autorizzazioni Gestione argomenti (responsabili della knowledge base) possono visualizzare e usare la pagina Gestisci argomenti.

I responsabili della conoscenza possono:

- Confermare o rimuovere gli argomenti individuati nel tenant.
- Crea nuovi argomenti manualmente in base alle esigenze (ad esempio, se non sono disponibili informazioni sufficienti per individuarlo tramite IA).
- Modificare le pagine degli argomenti esistenti.</br>

Per [ulteriori informazioni, vedere](manage-topics.md) Gestire gli argomenti nel Centro argomenti.  


## <a name="admin-controls"></a>Controlli di amministrazione

I controlli dell'amministratore nell'interfaccia di amministrazione di Microsoft 365 consentono di gestire la rete di conoscenze. Consentono a un amministratore globale o di SharePoint di Microsoft 365 di:

- Controllare gli utenti dell'organizzazione autorizzati a visualizzare gli argomenti nelle pagine moderne di SharePoint o nei risultati della ricerca di SharePoint.
- Controllare quali siti di SharePoint verranno sottoposti a ricerca per indicizzazione per identificare gli argomenti.
- Escludere argomenti specifici dall'essere trovati.
- Controllare quali utenti possono gestire gli argomenti nel Centro argomenti.
- Controllare quali utenti possono creare e modificare gli argomenti.
- Controllare l'utente che può visualizzare gli argomenti.

Per ulteriori informazioni sui controlli [](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery) [di amministrazione,](https://docs.microsoft.com/microsoft-365/knowledge/plan-topic-experiences#user-permissions)vedere assegnare autorizzazioni [utente,](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-knowledge-rules)gestire la visibilità degli argomenti e gestire l'individuazione degli argomenti.

## <a name="topic-curation--feedback"></a>Cura dell'argomento & feedback

L'intelligenza artificiale continuerà a lavorare per fornire suggerimenti per migliorare i tuoi argomenti quando si verificano modifiche nell'ambiente. 

Gli utenti con autorizzazioni per la modifica o la creazione di argomenti possono apportare aggiornamenti direttamente alle pagine degli argomenti se desiderano apportare correzioni o aggiungere ulteriori informazioni. Possono anche aggiungere nuovi argomenti che l'intelligenza artificiale non è stata in grado di identificare. Se sono disponibili informazioni sufficienti su questi argomenti aggiunti manualmente e l'intelligenza artificiale è in grado di identificare questo tipo di argomento, ulteriori suggerimenti dell'intelligenza artificiale potrebbero migliorare questi argomenti aggiunti manualmente 

Agli utenti a cui si consente l'accesso di visualizzare gli argomenti nel loro lavoro quotidiano potrebbe essere richiesto se l'argomento era utile per loro. Il sistema esamina queste risposte e le usa per migliorare l'evidenziazione dell'argomento e determinare cosa viene visualizzato nei riepiloghi degli argomenti e nei dettagli degli argomenti.

Inoltre, gli utenti con autorizzazioni appropriate possono contrassegnare elementi come una conversazione di Yammer rilevanti per un argomento e aggiungerli a un argomento specifico. 

Vedere [Individuazione e cura degli argomenti](https://docs.microsoft.com/microsoft-365/knowledge/topic-experiences-discovery-curation)


## <a name="see-also"></a>Vedere anche

