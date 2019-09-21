---
title: Introduzione ai criteri di gestione delle informazioni
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 5/16/2014
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- WSU150
- SPO160
- OSU150
- MET150
ms.assetid: 63a0b501-ba59-44b7-a35c-999f3be057b2
ms.collection:
- M365-security-compliance
description: Per criterio di gestione delle informazioni si intende un set di regole per un tipo di contenuto. I criteri di gestione delle informazioni consentono alle organizzazioni di controllare e registrare, ad esempio, il periodo di conservazione del contenuto e le azioni che gli utenti possono eseguire sul contenuto. I criteri di gestione delle informazioni possono essere utili per consentire alle organizzazioni di applicare la conformità con le norme statali o legali o semplicemente i processi aziendali interni.
ms.openlocfilehash: a5cf571b22b7d698daf8a70f8565b250e2388a1a
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37083734"
---
# <a name="introduction-to-information-management-policies"></a>Introduzione ai criteri di gestione delle informazioni

Per criterio di gestione delle informazioni si intende un set di regole per un tipo di contenuto. I criteri di gestione delle informazioni consentono alle organizzazioni di controllare e registrare, ad esempio, il periodo di conservazione del contenuto e le azioni che gli utenti possono eseguire sul contenuto. I criteri di gestione delle informazioni possono essere utili per consentire alle organizzazioni di applicare la conformità con le norme statali o legali o semplicemente i processi aziendali interni. 
  
Si supponga, ad esempio, che un'organizzazione sia tenuta a rispettare alcune norme statali in base alle quali è necessario dimostrare che le relazioni finanziarie vengono sottoposte a controlli appropriati. In questo caso, potrà creare uno o più criteri di gestione delle informazioni per controllare azioni specifiche eseguite durante il processo di creazione e approvazione per tutti i documenti correlati alle archiviazioni delle informazioni finanziarie.
  
Per informazioni e procedure, vedere [Creare e applicare criteri di gestione delle informazioni](create-info-mgmt-policies.md).
  
## <a name="features-of-information-management-policies"></a>Caratteristiche dei criteri di gestione delle informazioni
<a name="__top"> </a>

Esistono quattro categorie di base di caratteristiche dei criteri predefinite che le organizzazioni possono usare singolarmente o in combinazione per la gestione di contenuti e processi. 
  
![Tipi di criteri del contenuto](media/19fcb8a3-974b-40d3-a13f-b76088d122f8.png)
  
La caratteristica dei criteri di controllo consente alle organizzazioni di analizzare l'uso dei sistemi di gestione dei contenuti tramite la registrazione di eventi e di operazioni eseguiti su documenti e su elementi degli elenchi. È possibile configurare questa caratteristica in modo da registrare eventi specifici, ad esempio il momento in cui un documento o un elemento viene modificato, visualizzato, archiviato, estratto o eliminato oppure ne vengono modificate le autorizzazioni. Tutte le informazioni di controllo vengono archiviate nel server, in un singolo log di controllo in cui gli amministratori del sito possono eseguire report. 
  
La caratteristica dei criteri di scadenza consente alle organizzazioni di eliminare o rimuovere dai siti il contenuto non aggiornato in base a una procedura uniforme di cui è possibile tenere traccia, nonché di gestire i costi e i rischi associati alla conservazione di contenuto non aggiornato. È possibile configurare criteri di scadenza in modo da specificare che alcuni tipi di contenuto scadono a una data stabilita o entro un periodo specificato dopo la creazione o la modifica del documento.
  
Per soddisfare esigenze specifiche, le organizzazioni possono creare e implementare caratteristiche dei criteri personalizzate. Si supponga, ad esempio, che una società del settore manifatturiero voglia definire criteri di gestione delle informazioni per tutte le bozze di documenti che contengono le specifiche di prodotto, in modo da impedire agli utenti di stampare copie di tali documenti in stampanti non sicure. A questo scopo, è possibile creare e distribuire una caratteristica dei criteri di restrizione della stampa e aggiungerla ai criteri di gestione delle informazioni pertinenti per il tipo di contenuto relativo alle specifiche di progettazione dei prodotti.
  
## <a name="locations-to-use-an-information-management-policy"></a>Posizioni dei criteri di gestione delle informazioni
<a name="__toc340213528"> </a>

Per implementare i criteri di gestione delle informazioni, è necessario aggiungerli a un elenco, a una raccolta o a un tipo di contenuto in un sito. Le posizioni in cui vengono creati o aggiunti i criteri di gestione delle informazioni influiscono sul loro ambito di applicazione o di utilizzo. È possibile eseguire le operazioni seguenti:
  
 **Creare criteri per la raccolta siti e quindi aggiungerli a un tipo di contenuto, a un elenco o a una raccolta** È possibile creare criteri per la raccolta siti nell'elenco Criteri nel sito principale della raccolta. Dopo aver creato criteri per la raccolta siti, è possibile esportarli per consentire agli amministratori di altre raccolte siti di importarli nel proprio elenco Criteri. La creazione di criteri esportabili per la raccolta siti consente di standardizzare i criteri di gestione delle informazioni in tutti i siti dell'organizzazione. 
  
Quando si aggiungono criteri per la raccolta siti a un tipo di contenuto del sito e un'istanza di quest'ultimo a un elenco o a una raccolta, il proprietario dell'elenco o della raccolta non può modificare i criteri per la raccolta siti per l'elenco o la raccolta in questione. Se si aggiungono criteri per la raccolta siti a un tipo di contenuto del sito, i criteri vengono applicati a ogni livello della gerarchia del sito.
  
![Collegamento Modelli di criteri tipo di contenuto nella pagina Impostazioni sito](media/26d3466a-23ec-443f-88f0-2aaff38e992b.png)
  
 **Creare criteri di gestione delle informazioni per un tipo di contenuto del sito nella raccolta dei tipi di contenuto del sito principale e quindi aggiungere il tipo di contenuto a uno o più elenchi o raccolte** È anche possibile creare criteri di gestione delle informazioni direttamente per un tipo di contenuto del sito e quindi associare un'istanza di questo tipo di contenuto del sito a più elenchi o raccolte. Se i criteri di gestione delle informazioni vengono creati in questo modo, vengono applicati a ogni elemento della raccolta siti associato al tipo di contenuto specificato o a un tipo di contenuto che eredita da questo. Se si creano criteri di gestione delle informazioni direttamente per un tipo di contenuto del sito, tuttavia, è più difficile riutilizzarli in altre raccolte siti, in quanto i criteri creati in questo modo non possono essere esportati. 
  
![Collegamento Tipi di contenuto del sito nella pagina Impostazioni sito](media/6f6fa51f-15d7-4782-b06f-a7b36e874cd3.png)
  
![Collegamento ai criteri gestione informazioni nella pagina di impostazioni per un tipo di contenuto del sito](media/15d83a34-6c8f-4b6e-b6ee-e9b0a70cbb4b.png)
  
Nota Per tenere sotto controllo i criteri usati in una raccolta siti, gli amministratori della raccolta siti possono disabilitare la funzionalità che consente di impostare le caratteristiche dei criteri direttamente in un tipo di contenuto. Quando viene applicata questa restrizione, gli utenti che creano i tipi di contenuto possono selezionare i criteri solo nell'elenco Criteri della raccolta siti.
  
 **Creare criteri di gestione delle informazioni per un elenco o una raccolta** Se l'organizzazione deve applicare criteri di gestione delle informazioni a un insieme limitato di contenuti, è possibile creare criteri validi per un unico elenco o per un'unica raccolta. Questa modalità di creazione è caratterizzata da un basso livello di flessibilità perché i criteri così creati vengono applicati in una sola posizione e non possono essere esportati né riutilizzati per altre posizioni. Può tuttavia essere necessario creare criteri di gestione delle informazioni univoci di applicabilità limitata per gestire situazioni specifiche. 
  
![Collegamento ai criteri gestione informazioni nella pagina di impostazioni per una raccolta documenti](media/9fa6d366-6aab-49e1-a05c-898ac6f536e6.png)
  
Note 
  
È possibile creare criteri di gestione delle informazioni per un elenco o una raccolta solo se tale elenco o raccolta non supporta più tipi di contenuto. In caso contrario, è necessario definire criteri di gestione delle informazioni per ogni singolo tipo di contenuto di elenco associato a tale elenco o raccolta. Vengono definite come tipi di contenuto di elenco le istanze di un tipo di contenuto del sito associate a una raccolta o a un elenco specifico.
  
Per tenere sotto controllo i criteri usati in una raccolta siti, gli amministratori della raccolta siti possono disabilitare la funzionalità che consente di impostare le caratteristiche dei criteri direttamente in un elenco o in una raccolta. Quando viene applicata questa restrizione, gli utenti che gestiscono elenchi o raccolte possono selezionare i criteri solo nell'elenco Criteri della raccolta siti.
  
[Per criterio di gestione delle informazioni si intende un set di regole per un tipo di contenuto. I criteri di gestione delle informazioni consentono alle organizzazioni di controllare e registrare, ad esempio, il periodo di conservazione del contenuto e le azioni che gli utenti possono eseguire sul contenuto. I criteri di gestione delle informazioni possono essere utili per consentire alle organizzazioni di applicare la conformità con le norme statali o legali o semplicemente i processi aziendali interni.Si supponga, ad esempio, che un'organizzazione sia tenuta a rispettare alcune norme statali in base alle quali è necessario dimostrare che le relazioni finanziarie vengono sottoposte a controlli appropriati. In questo caso, potrà creare uno o più criteri di gestione delle informazioni per controllare azioni specifiche eseguite durante il processo di creazione e approvazione per tutti i documenti correlati alle archiviazioni delle informazioni finanziarie.Per informazioni e procedure, vedere Creare e applicare criteri di gestione delle informazioni.](intro-to-info-mgmt-policies.md#__top)
  

