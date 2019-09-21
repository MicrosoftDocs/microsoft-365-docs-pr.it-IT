---
title: Panoramica dell'archiviazione illimitata in Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 37cdbb02-a24a-4093-8bdb-2a7f0b3a19ee
description: Informazioni sull'espansione automatica dell'archiviazione in Office 365, che fornisce un archivio di archiviazione illimitato per le cassette postali di Exchange Online.
ms.openlocfilehash: 475bf53304be55bbac085693788cff4b5522bb14
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37084746"
---
# <a name="overview-of-unlimited-archiving-in-office-365"></a>Panoramica dell'archiviazione illimitata in Office 365

In Office 365, le cassette postali di archiviazione offrono agli utenti un ulteriore spazio di archiviazione. Dopo aver abilitato la cassetta postale di archiviazione di un utente, sono disponibili fino a 100 GB di spazio di archiviazione aggiuntivo. In passato, quando è stata raggiunta la quota di archiviazione 100 GB, le organizzazioni hanno dovuto contattare Microsoft per richiedere ulteriore spazio di archiviazione per una cassetta postale di archiviazione. Questo non è più il caso.

La funzionalità di archiviazione illimitata in Office 365 (chiamata *archiviazione in espansione automatica*) fornisce fino a 1 TB di spazio di archiviazione aggiuntivo nelle cassette postali di archiviazione. Quando viene raggiunta la quota di archiviazione nella cassetta postale di archivio, Office 365 aumenta automaticamente le dimensioni dell'archivio, il che significa che gli utenti non finiscono nello spazio di archiviazione delle cassette postali e gli amministratori non dovranno richiedere l'archiviazione aggiuntiva per le cassette postali di archiviazione.
  
Per istruzioni dettagliate per l'attivazione dell'archiviazione in espansione automatica, vedere [Enable Unlimited Archiving in Office 365](enable-unlimited-archiving.md).
  
> [!NOTE]
> L'espansione automatica dell'archivio supporta anche le cassette postali condivise. Per abilitare l'archivio per una cassetta postale condivisa, è necessaria una licenza di Exchange Online piano 2 o una licenza di Exchange Online piano 1 con una licenza di archiviazione Exchange Online. 
  
## <a name="how-auto-expanding-archiving-works"></a>Funzionamento dell'archiviazione con espansione automatica

Come spiegato in precedenza, viene creato ulteriore spazio di archiviazione delle cassette postali quando la cassetta postale di archiviazione di un utente è abilitata. Quando l'archiviazione in espansione automatica è abilitata, Office 365 verifica periodicamente le dimensioni della cassetta postale di archiviazione. Quando una cassetta postale di archiviazione si avvicina al limite di spazio di memorizzazione, Office 365 crea automaticamente ulteriore spazio di archiviazione per la cassetta postale di archiviazione. Questo spazio aggiuntivo è denominato *Archivio ausiliario*. Se l'utente si esaurisce nello spazio di archiviazione in un archivio ausiliario, Office 365 aggiungerà automaticamente un nuovo archivio ausiliario. Office 365 aggiunge un massimo di 20 archivi ausiliari per un totale di 1 TB di spazio di archiviazione aggiuntivo. Questo processo si verifica automaticamente, il che significa che gli amministratori non devono gestire l'archiviazione in espansione automatica. 
  
Ecco una breve panoramica del processo.
  
![Panoramica del processo di archiviazione in espansione automatica](media/74355385-d990-44fe-8a87-6c3639d1f63f.png)
  
1. L'archiviazione è abilitata per una cassetta postale utente o una cassetta postale condivisa. Viene creata una cassetta postale di archiviazione con 100 GB di spazio di memorizzazione e la quota di avviso per la cassetta postale di archiviazione è impostata su 90 GB.
    
2. Un amministratore consente di abilitare l'espansione automatica dell'archiviazione per la cassetta postale. Quando la cassetta postale di archiviazione (inclusa la cartella elementi ripristinabili) raggiunge 90 GB, viene convertita in un archivio in espansione automatica e Office 365 aggiunge lo spazio di archiviazione all'archivio. Possono essere necessari fino a 30 giorni per il provisioning dello spazio di archiviazione aggiuntivo.

   > [!NOTE]
   > Se una cassetta postale viene conservata o assegnata a un criterio di conservazione di Office 365, la quota di archiviazione per l'archivio Maibox viene aumentata a 110 GB quando l'archiviazione in espansione automatica è abilitata. Analogamente, la quota di avviso per l'archiviazione viene aumentata a 100 GB.
    
3. Office 365 aggiunge automaticamente ulteriore spazio di archiviazione, se necessario. Come indicato in precedenza, Office 365 aggiunge fino a 20 archivi ausiliari, per un massimo di 1 TB di spazio di archiviazione aggiuntivo.
  
> [!IMPORTANT]
> L'espansione automatica dell'archivio è supportata solo per le cassette postali utilizzate per singoli utenti (o per le cassette postali condivise) con un tasso di crescita non superiore a 1 GB al giorno. Una cassetta postale di archiviazione di un utente è destinata esclusivamente a quell'utente. L'utilizzo dell'inserimento nel journal, delle regole di trasporto o delle regole di inoltro automatico per copiare i messaggi in una cassetta postale di archiviazione non è consentito. Microsoft si riserva il diritto di non consentire uno spazio di archiviazione illimitato nei casi in cui una cassetta postale di archiviazione dell'utente sia utilizzata per l'archiviazione di dati di altri utenti.

## <a name="what-gets-moved-to-the-additional-archive-storage-space"></a>Cosa viene spostato nello spazio di archiviazione aggiuntivo dell'archivio?

Per utilizzare in modo efficiente l'archiviazione di un archivio automatico, è possibile che le cartelle vengano spostate. Office 365 determina quali cartelle vengono spostate quando viene aggiunta un'ulteriore archiviazione all'archivio. Quando una cartella viene spostata, viene creata automaticamente una sottocartella nella cartella originale nella parte relativa all'archivio dell'elenco delle cartelle in Outlook. Questa nuova sottocartella punta agli elementi che sono stati spostati. La convenzione di denominazione utilizzata da Office 365 per assegnare un nome alla cartella è ** \<il nome\>della cartella _yyyy (creato in mmm gg, yyyy h_mm)**, dove: 
  
- **yyyy** è l'anno in cui sono stati ricevuti i messaggi nella cartella. 
    
- **mmm gg, yyyy h_m** è la data e l'ora in cui la sottocartella è stata creata da Office 365, in formato UTC, in base al fuso orario e alle impostazioni internazionali dell'utente in Outlook. 
    
Nelle schermate seguenti viene visualizzato un elenco di cartelle prima e dopo che i messaggi vengono spostati in un archivio con espansione automatica.
  
 **Prima dell'aggiunta dell'archiviazione aggiuntiva**
  
![Elenco delle cartelle della cassetta postale di archiviazione prima del provisioning dell'archivio con espansione automatica](media/5d6d6420-e562-4912-aaab-1c111762b3f6.png)
  
 **Dopo l'aggiunta dell'archiviazione aggiuntiva**
  
![Elenco delle cartelle della cassetta postale di archiviazione dopo il provisioning dell'archivio con espansione automatica](media/c03c5f51-23fa-4fc2-b887-7e7e5cce30da.png)
  
## <a name="outlook-requirements-for-accessing-items-in-an-auto-expanded-archive"></a>Requisiti di Outlook per l'accesso agli elementi in un archivio con espansione automatica

Per accedere ai messaggi archiviati in un archivio con espansione automatica, è necessario che gli utenti utilizzino uno dei client Outlook seguenti:
  
- Outlook 2016 o Outlook 2019 per Windows
    
- Outlook sul web 
    
- Outlook 2016 o Outlook 2019 per Mac 
    
> [!NOTE]
> Gli utenti di Outlook 2013 possono accedere solo agli elementi archiviati in origine nella cassetta postale di archiviazione. Non saranno in grado di accedere agli elementi spostati in un archivio di archiviazione aggiuntivo. 
  
Di seguito sono riportate alcune considerazioni da prendere in considerazione quando si utilizza Outlook o Outlook sul Web per accedere ai messaggi archiviati in un archivio con espansione automatica.
  
- È possibile accedere a qualsiasi cartella nella cassetta postale di archiviazione, incluse quelle che sono state spostate nell'area di archiviazione espansa automaticamente.
    
- È possibile cercare gli elementi spostati in un'area di archiviazione aggiuntiva solo eseguendo una ricerca nella cartella stessa. Questo significa che è necessario selezionare la cartella di archiviazione nell'elenco delle cartelle per selezionare l'opzione **cartella corrente** come ambito di ricerca. Analogamente, se una cartella in un'area di archiviazione espansa automaticamente contiene sottocartelle, è necessario eseguire la ricerca separatamente in ogni sottocartella. 
    
- I conteggi degli elementi in Outlook e i conteggi di lettura/non lettura (in Outlook e Outlook sul Web) in un archivio con espansione automatica potrebbero non essere accurati.
    
- È possibile eliminare gli elementi in una sottocartella che punta a un'area di archiviazione espansa automaticamente, ma la cartella stessa non può essere eliminata.
    
- Non è possibile utilizzare la funzionalità Recupera elementi eliminati per recuperare un elemento che è stato eliminato da un'area di archiviazione espansa automaticamente.
  
## <a name="auto-expanding-archiving-and-other-office-365-compliance-features"></a>Archiviazione in espansione automatica e altre funzionalità di conformità di Office 365

In questa sezione viene illustrata la funzionalità tra l'archiviazione in espansione automatica e altre funzionalità di conformità e governance dei dati di Office 365.
  
- **eDiscovery:** Quando si utilizza uno strumento di eDiscovery di Office 365, ad esempio la ricerca di contenuto o eDiscovery sul posto, vengono cercate anche le aree di archiviazione aggiuntive in un archivio con espansione automatica.
    
- **Conservazione**:* * quando si inserisce una cassetta postale in attesa utilizzando strumenti come il blocco per controversia legale in Exchange Online o eDiscovery e i criteri di conservazione nel centro sicurezza e conformità, anche il contenuto di un archivio con espansione automatica viene messo in attesa.
    
- **Gestione record di messaggistica:** Se si utilizzano i criteri di eliminazione di gestione record di messaggistica in Exchange Online per eliminare definitivamente gli elementi della cassetta postale scaduta, verranno eliminati anche gli elementi scaduti che si trovano nell'archivio automatico espanso.
    
- **Import service**:* * è possibile utilizzare il servizio di importazione di Office 365 per importare i file PST nell'archivio automatico espanso di un utente. È possibile importare fino a 100 GB di dati da file PST nella cassetta postale di archiviazione dell'utente. 

## <a name="more-information"></a>Ulteriori informazioni

Per ulteriori informazioni tecniche sull'archiviazione in espansione automatica, vedere [Office 365: auto-Expanding Archives FAQ](https://blogs.technet.microsoft.com/exchange/2018/04/09/office-365-auto-expanding-archives-faq/).
