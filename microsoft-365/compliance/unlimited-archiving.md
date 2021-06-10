---
title: Panoramica dell'archiviazione illimitata
f1.keywords:
- NOCSH
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
description: Informazioni sull'archiviazione con espansione automatica, che fornisce un'archiviazione illimitata per Exchange Online cassette postali.
ms.openlocfilehash: d61d3649ed65a93298928cced21180bbeca6aa95
ms.sourcegitcommit: 7b8104015a76e02bc215e1cf08069979c70650ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/31/2021
ms.locfileid: "51476267"
---
# <a name="overview-of-unlimited-archiving"></a>Panoramica dell'archiviazione illimitata

In Office 365 cassette postali di archiviazione forniscono agli utenti ulteriore spazio di archiviazione delle cassette postali. Dopo aver abilitato la cassetta postale di archiviazione di un utente, sono disponibili fino a 100 GB di spazio di archiviazione aggiuntivo. In passato, quando è stata raggiunta la quota di archiviazione da 100 GB, le organizzazioni hanno dovuto contattare Microsoft per richiedere ulteriore spazio di archiviazione per una cassetta postale di archiviazione. Non è più così.

La funzionalità di archiviazione illimitata in Microsoft 365 (denominata archiviazione con espansione *automatica)* offre ulteriore spazio di archiviazione nelle cassette postali di archiviazione. Quando viene raggiunta la quota di archiviazione nella cassetta postale di archiviazione, Microsoft 365 aumenta automaticamente le dimensioni dell'archivio, il che significa che gli utenti non eseguono lo spazio di archiviazione delle cassette postali e gli amministratori non devono richiedere ulteriore spazio di archiviazione per le cassette postali di archiviazione.

Per istruzioni dettagliate sull'attivazione dell'archiviazione con espansione automatica, vedere [Enable unlimited archiving](enable-unlimited-archiving.md).

> [!NOTE]
> L'espansione automatica dell'archivio supporta anche le cassette postali condivise. Per abilitare l'archivio per una cassetta postale condivisa, è necessaria una licenza di Exchange Online Piano 2 o una licenza di Exchange Online Piano 1 con una licenza Archiviazione Exchange Online condivisa.

## <a name="how-auto-expanding-archiving-works"></a>Funzionamento dell'archiviazione con espansione automatica

Come spiegato in precedenza, viene creato ulteriore spazio di archiviazione delle cassette postali quando è abilitata la cassetta postale di archiviazione di un utente. Quando l'archiviazione con espansione automatica è abilitata, Microsoft 365 verifica periodicamente le dimensioni della cassetta postale di archiviazione. Quando una cassetta postale di archiviazione si avvicina al limite di archiviazione, Microsoft 365 automaticamente spazio di archiviazione aggiuntivo per l'archivio. Se l'utente esaurirà questo spazio di archiviazione aggiuntivo, Microsoft 365 spazio di archiviazione all'archivio dell'utente. Questo processo si verifica automaticamente, il che significa che gli amministratori non devono richiedere ulteriore archiviazione o gestire l'archiviazione con espansione automatica.

Ecco una breve panoramica del processo.

![Panoramica del processo di archiviazione con espansione automatica](../media/74355385-d990-44fe-8a87-6c3639d1f63f.png)

1. L'archiviazione è abilitata per una cassetta postale utente o una cassetta postale condivisa. Viene creata una cassetta postale di archiviazione con 100 GB di spazio di archiviazione e la quota di avviso per la cassetta postale di archiviazione è impostata su 90 GB.

2. Un amministratore abilita l'archiviazione con espansione automatica per la cassetta postale. Quando la cassetta postale di archiviazione (inclusa la cartella Elementi ripristinabili) raggiunge i 90 GB, viene convertita in un archivio con espansione automatica e Microsoft 365 aggiunge spazio di archiviazione all'archivio. Il provisioning dello spazio di archiviazione aggiuntivo può richiedere fino a 30 giorni.

   > [!NOTE]
   > Se una cassetta postale viene messa in attesa o assegnata a un criterio di conservazione, la quota di archiviazione per la cassetta postale di archiviazione viene aumentata a 110 GB quando è abilitata l'archiviazione con espansione automatica. Analogamente, la quota di avviso di archiviazione viene aumentata a 100 GB.

3. Microsoft 365 aggiunge automaticamente più spazio di archiviazione quando necessario.

> [!IMPORTANT]
> L'espansione automatica dell'archivio è supportata solo per le cassette postali utilizzate per singoli utenti (o cassette postali condivise) con un tasso di crescita che non supera 1 GB al giorno. Una cassetta postale di archiviazione di un utente è destinata esclusivamente a quell'utente. L'utilizzo dell'inserimento nel journal, delle regole di trasporto o delle regole di inoltro automatico per copiare i messaggi in una cassetta postale di archiviazione non è consentito. Microsoft si riserva il diritto di negare l'archiviazione illimitata nei casi in cui la cassetta postale di archiviazione di un utente viene utilizzata per archiviare i dati di archiviazione per altri utenti o in altri casi di utilizzo inappropriato.

## <a name="what-gets-moved-to-the-additional-archive-storage-space"></a>Cosa viene spostato nello spazio di archiviazione di archiviazione aggiuntivo?

Per utilizzare in modo efficiente l'archiviazione di archiviazione con espansione automatica, le cartelle potrebbero essere spostate. Microsoft 365 determina quali cartelle vengono spostate quando viene aggiunto ulteriore spazio di archiviazione all'archivio. A volte, quando una cartella viene spostata, vengono create automaticamente una o più sottocartelle e gli elementi della cartella originale vengono distribuiti a queste cartelle per facilitare il processo di spostamento. Quando si visualizza la parte di archivio dell'elenco di cartelle in Outlook, queste sottocartelle vengono visualizzate nella cartella originale.  La convenzione di denominazione Microsoft 365 utilizzata per denominare queste sottocartelle è _yyyy (Creato in **\<folder name\> mmm dd, yyyy h_mm)**, dove:

- **aaaa** è l'anno in cui sono stati ricevuti i messaggi nella cartella.

- **mmm dd, yyyy h_m** è la data e l'ora in cui la sottocartella è stata creata da Office 365, in formato UTC, in base al fuso orario e alle impostazioni internazionali dell'utente in Outlook.

Gli screenshot seguenti mostrano un elenco di cartelle prima e dopo che i messaggi vengono spostati in un archivio espanso automaticamente.

 **Prima dell'aggiunta di ulteriore spazio di archiviazione**

![Elenco cartelle della cassetta postale di archiviazione prima del provisioning dell'archivio con espansione automatica](../media/5d6d6420-e562-4912-aaab-1c111762b3f6.png)

 **Dopo l'aggiunta di ulteriore spazio di archiviazione**

![Elenco cartelle della cassetta postale di archiviazione dopo il provisioning dell'archivio con espansione automatica](../media/c03c5f51-23fa-4fc2-b887-7e7e5cce30da.png)

> [!NOTE]
> Come descritto in precedenza, Microsoft 365 gli elementi in sottocartelle (e li assegnano i nomi utilizzando la convenzione di denominazione descritta in precedenza) per distribuire il contenuto in un archivio ausiliario. Tuttavia, lo spostamento di elementi in sottocartelle potrebbe non essere sempre il caso. A volte un'intera cartella può essere spostata in un archivio ausiliario. In questo caso, la cartella manterrà il nome originale.  Non sarà evidente nell'elenco delle cartelle Outlook che la cartella sia stata spostata in un archivio ausiliario.

## <a name="outlook-requirements-for-accessing-items-in-an-auto-expanded-archive"></a>Outlook requisiti per l'accesso agli elementi in un archivio espanso automaticamente

Per accedere ai messaggi archiviati in un archivio espanso automaticamente, gli utenti devono utilizzare uno dei client Outlook seguenti:

- Outlook 2016 o Outlook 2019 per Windows

- Outlook sul Web

- Outlook 2016 o Outlook 2019 per Mac

Ecco alcuni aspetti da considerare quando si usa Outlook o Outlook sul Web per accedere ai messaggi archiviati in un archivio espanso automaticamente.

- È possibile accedere a qualsiasi cartella nella cassetta postale di archiviazione, incluse quelle spostate nell'area di archiviazione espansa automaticamente.

- La ricerca per l'archiviazione espansa automaticamente è disponibile in Outlook per il Web (OWA). Analogamente all'archivio online, è possibile cercare gli elementi spostati in un'area di archiviazione aggiuntiva. Quando l'archivio è selezionato come ambito di ricerca in OWA, verranno cercati tutti gli archivi (inclusi gli archivi espansi automaticamente) e le sottocartelle corrispondenti.

- La ricerca di archiviazione espansa automaticamente è disponibile in Outlook Desktop nel canale corrente (anteprima). All'interno di questa anteprima è disponibile l'ambito Cassetta postale corrente, che consente di eseguire ricerche nell'archivio espanso automaticamente. Per ulteriori informazioni su questa e altre funzionalità di supporto di Microsoft Search, vedere [How Outlook for Windows connected to Exchange Online utilizes Microsoft Search](https://techcommunity.microsoft.com/t5/outlook-global-customer-service/how-outlook-for-windows-connected-to-exchange-online-utilizes/ba-p/1715045). 

- I conteggi degli elementi in Outlook e i conteggi di lettura/lettura (in Outlook e Outlook sul Web) in un archivio espanso automaticamente potrebbero non essere accurati.

- È possibile eliminare elementi in una sottocartella che punta a un'area di archiviazione espansa automaticamente, ma la cartella stessa non può essere eliminata.

- Non è possibile utilizzare la funzionalità Recupera elementi eliminati per ripristinare un elemento eliminato da un'area di archiviazione espansa automaticamente.

## <a name="auto-expanding-archiving-and-other-compliance-features"></a>Archiviazione con espansione automatica e altre funzionalità di conformità

In questa sezione vengono illustrate le funzionalità tra l'archiviazione con espansione automatica e altre funzionalità di conformità e governance dei dati.

- **eDiscovery:** Quando si utilizza uno strumento di eDiscovery, ad esempio Ricerca contenuto o In-Place eDiscovery, vengono ricercate anche le aree di archiviazione aggiuntive in un archivio espanso automaticamente.

- **Conservazione:** Quando si archivia una cassetta postale utilizzando strumenti come il blocco per controversia legale in Exchange Online o i blocchi caso eDiscovery e i criteri di conservazione nel Centro sicurezza e conformità, viene messo in attesa anche il contenuto che si trova in un archivio espanso automaticamente.

- **Gestione record di messaggistica :Messaging records management (MRM):** Se si utilizzano i criteri di eliminazione di Gestione record di messaggistica in Exchange Online per eliminare definitivamente gli elementi delle cassette postali scaduti, verranno eliminati anche gli elementi scaduti che si trovano nell'archivio espanso automaticamente.

- **Servizio di importazione:** È possibile utilizzare il servizio Office 365 importare i file PST nell'archivio espanso automaticamente di un utente. È possibile importare fino a 100 GB di dati dai file PST nella cassetta postale di archiviazione dell'utente.

## <a name="more-information"></a>Ulteriori informazioni

Per ulteriori dettagli tecnici sull'espansione automatica dell'archiviazione, vedere Microsoft 365 domande frequenti sull'espansione automatica [degli archivi.](https://techcommunity.microsoft.com/t5/exchange-team-blog/office-365-auto-expanding-archives-faq/ba-p/607784)
