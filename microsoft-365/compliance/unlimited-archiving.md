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
description: Informazioni sull'archiviazione con espansione automatica, che fornisce spazio di archiviazione illimitato per le cassette postali di Exchange Online.
ms.openlocfilehash: 9692ba27c64f41ac584bb4008a8b860daab031f5
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029432"
---
# <a name="overview-of-unlimited-archiving"></a>Panoramica dell'archiviazione illimitata

In Office 365, le cassette postali di archiviazione forniscono agli utenti ulteriore spazio di archiviazione delle cassette postali. Dopo aver abilitato la cassetta postale di archiviazione di un utente, sono disponibili fino a 100 GB di spazio di archiviazione aggiuntivo. In passato, quando è stata raggiunta la quota di archiviazione di 100 GB, le organizzazioni hanno dovuto contattare Microsoft per richiedere ulteriore spazio di archiviazione per una cassetta postale di archiviazione. Non è più così.

La funzionalità di archiviazione illimitata di Microsoft 365 (denominata archiviazione con espansione *automatica)* offre ulteriore spazio di archiviazione nelle cassette postali di archiviazione. Quando viene raggiunta la quota di archiviazione nella cassetta postale di archiviazione, Microsoft 365 aumenta automaticamente le dimensioni dell'archivio, il che significa che gli utenti non eseguono lo spazio di archiviazione delle cassette postali e gli amministratori non devono richiedere ulteriore spazio di archiviazione per le cassette postali di archiviazione.

Per istruzioni dettagliate su come attivare l'archiviazione con espansione automatica, vedere [Abilitare l'archiviazione illimitata.](enable-unlimited-archiving.md)

> [!NOTE]
> L'espansione automatica dell'archivio supporta anche le cassette postali condivise. Per abilitare l'archivio per una cassetta postale condivisa, è necessaria una licenza di Exchange Online Piano 2 o una licenza di Exchange Online Piano 1 con una Archiviazione Exchange Online condivisa.

## <a name="how-auto-expanding-archiving-works"></a>Funzionamento dell'archiviazione con espansione automatica

Come spiegato in precedenza, viene creato ulteriore spazio di archiviazione delle cassette postali quando la cassetta postale di archiviazione di un utente è abilitata. Quando l'archiviazione con espansione automatica è abilitata, Microsoft 365 controlla periodicamente le dimensioni della cassetta postale di archiviazione. Quando una cassetta postale di archiviazione si avvicina al limite di archiviazione, Microsoft 365 crea automaticamente ulteriore spazio di archiviazione per l'archivio. Se l'utente esauri lo spazio di archiviazione aggiuntivo, Microsoft 365 aggiunge ulteriore spazio di archiviazione all'archivio dell'utente. Questo processo si verifica automaticamente, il che significa che gli amministratori non devono richiedere ulteriore spazio di archiviazione o gestire l'archiviazione con espansione automatica.

Ecco una rapida panoramica del processo.

![Panoramica del processo di archiviazione con espansione automatica](../media/74355385-d990-44fe-8a87-6c3639d1f63f.png)

1. L'archiviazione è abilitata per una cassetta postale utente o una cassetta postale condivisa. Viene creata una cassetta postale di archiviazione con 100 GB di spazio di archiviazione e la quota di avviso per la cassetta postale di archiviazione è impostata su 90 GB.

2. Un amministratore abilita l'archiviazione con espansione automatica per la cassetta postale. Quando la cassetta postale di archiviazione (inclusa la cartella Elementi ripristinabili) raggiunge i 90 GB, viene convertita in un archivio con espansione automatica e Microsoft 365 aggiunge spazio di archiviazione all'archivio. Il provisioning dello spazio di archiviazione aggiuntivo può richiedere fino a 30 giorni.

   > [!NOTE]
   > Se una cassetta postale viene messa in attesa o assegnata a un criterio di conservazione, la quota di archiviazione per la cassetta postale di archiviazione viene aumentata a 110 GB quando l'archiviazione con espansione automatica è abilitata. Analogamente, la quota di avviso per l'archiviazione viene aumentata a 100 GB.

3. Microsoft 365 aggiunge automaticamente più spazio di archiviazione quando necessario.

> [!IMPORTANT]
> L'espansione automatica dell'archivio è supportata solo per le cassette postali utilizzate per singoli utenti (o cassette postali condivise) con una frequenza di crescita che non supera 1 GB al giorno. Una cassetta postale di archiviazione di un utente è destinata esclusivamente a quell'utente. L'utilizzo dell'inserimento nel journal, delle regole di trasporto o delle regole di inoltro automatico per copiare i messaggi in una cassetta postale di archiviazione non è consentito. Microsoft si riserva il diritto di negare l'archiviazione illimitata nei casi in cui la cassetta postale di archiviazione di un utente viene utilizzata per archiviare i dati per altri utenti o in altri casi di uso inappropriato.

## <a name="what-gets-moved-to-the-additional-archive-storage-space"></a>Cosa viene spostato nello spazio di archiviazione aggiuntivo?

Per utilizzare in modo efficiente l'archiviazione di archiviazione con espansione automatica, le cartelle potrebbero essere spostate. Microsoft 365 determina quali cartelle vengono spostate quando viene aggiunto ulteriore spazio di archiviazione all'archivio. A volte, quando una cartella viene spostata, vengono create automaticamente una o più sottocartelle e gli elementi della cartella originale vengono distribuiti a tali cartelle per facilitare il processo di spostamento. Quando si visualizza la parte di archivio dell'elenco delle cartelle in Outlook, queste sottocartelle vengono visualizzate nella cartella originale.  La convenzione di denominazione utilizzata da Microsoft 365 per denominare queste sottocartelle è _yyyy (Creata in **\<folder name\> mmm dd, aaaa h_mm)**, dove:

- **aaaa è** l'anno in cui sono stati ricevuti i messaggi nella cartella.

- **mmm d, aaaa h_m** è la data e l'ora in cui la sottocartella è stata creata da Office 365, in formato UTC, in base alle impostazioni internazionali e del fuso orario dell'utente in Outlook.

Gli screenshot seguenti mostrano un elenco di cartelle prima e dopo che i messaggi vengono spostati in un archivio espanso automaticamente.

 **Prima dell'aggiunta di ulteriore spazio di archiviazione**

![Elenco di cartelle della cassetta postale di archiviazione prima del provisioning dell'archivio con espansione automatica](../media/5d6d6420-e562-4912-aaab-1c111762b3f6.png)

 **Dopo l'aggiunta di ulteriore spazio di archiviazione**

![Elenco cartelle della cassetta postale di archiviazione dopo il provisioning dell'archivio con espansione automatica](../media/c03c5f51-23fa-4fc2-b887-7e7e5cce30da.png)

> [!NOTE]
> Come descritto in precedenza, Microsoft 365 sposta gli elementi in sottocartelle (e li denomina usando la convenzione di denominazione descritta in precedenza) per distribuire il contenuto in un archivio ausiliario. Tuttavia, lo spostamento di elementi in sottocartelle potrebbe non essere sempre il caso. A volte un'intera cartella può essere spostata in un archivio ausiliario. In questo caso, la cartella manterrà il nome originale.  Nell'elenco delle cartelle di Outlook non sarà evidente che la cartella è stata spostata in un archivio ausiliario.

## <a name="outlook-requirements-for-accessing-items-in-an-auto-expanded-archive"></a>Requisiti di Outlook per l'accesso agli elementi in un archivio espanso automaticamente

Per accedere ai messaggi archiviati in un archivio espanso automaticamente, gli utenti devono utilizzare uno dei client Outlook seguenti:

- Outlook 2016 o Outlook 2019 per Windows

- Outlook sul Web

- Outlook 2016 o Outlook 2019 per Mac

Ecco alcuni aspetti da considerare quando si utilizza Outlook o Outlook sul Web per accedere ai messaggi archiviati in un archivio espanso automaticamente.

- È possibile accedere a qualsiasi cartella della cassetta postale di archiviazione, incluse quelle spostate nell'area di archiviazione espansa automaticamente.

- La ricerca per l'archiviazione espansa automaticamente è disponibile in Outlook per il Web. Analogamente all'archivio online, è possibile cercare gli elementi spostati in un'area di archiviazione aggiuntiva solo eseguendo una ricerca nella cartella corrente. Ciò significa che è necessario selezionare la cartella di archiviazione nell'elenco delle cartelle e quindi selezionare una singola cartella come ambito di ricerca. Analogamente, se una cartella in un'area di archiviazione espansa automaticamente contiene sottocartelle, è necessario cercare ogni sottocartella separatamente.
- La ricerca di archiviazione espansa automaticamente è disponibile in Outlook Desktop nel Canale corrente (anteprima). In questa anteprima è disponibile l'ambito Cassetta postale corrente, che consente di cercare nell'archivio espanso automaticamente. Per ulteriori informazioni su questa e altre funzionalità di supporto di Microsoft Search, vedere Come Outlook per Windows connesso a [Exchange Online utilizza Microsoft Search.](https://techcommunity.microsoft.com/t5/outlook-global-customer-service/how-outlook-for-windows-connected-to-exchange-online-utilizes/ba-p/1715045) 

- Il conteggio degli elementi in Outlook e i conteggi di lettura/lettura (in Outlook e Outlook sul Web) in un archivio espanso automaticamente potrebbero non essere accurati.

- È possibile eliminare elementi in una sottocartella che punta a un'area di archiviazione espansa automaticamente, ma la cartella stessa non può essere eliminata.

- Non è possibile utilizzare la funzionalità Recupera elementi eliminati per recuperare un elemento eliminato da un'area di archiviazione espansa automaticamente.

## <a name="auto-expanding-archiving-and-other-compliance-features"></a>Espansione automatica dell'archiviazione e altre funzionalità di conformità

In questa sezione viene illustrata la funzionalità tra l'archiviazione con espansione automatica e altre funzionalità di conformità e governance dei dati.

- **eDiscovery:** Quando si utilizza uno strumento di eDiscovery, ad esempio Ricerca contenuto o In-Place eDiscovery, vengono cercate anche le aree di archiviazione aggiuntive in un archivio espanso automaticamente.

- **Conservazione:** Quando si archivia una cassetta postale utilizzando strumenti come il blocco per controversia legale in Exchange Online o i blocchi dei casi di eDiscovery e i criteri di conservazione nel Centro sicurezza e conformità, anche il contenuto che si trova in un archivio espanso automaticamente viene messo in attesa.

- **Gestione record di messaggistica (MRM):** Se si utilizzano i criteri di eliminazione di Gestione record di messaggistica in Exchange Online per eliminare definitivamente gli elementi scaduti della cassetta postale, verranno eliminati anche gli elementi scaduti che si trovano nell'archivio espanso automaticamente.

- **Import service:** È possibile utilizzare il servizio di importazione di Office 365 per importare i file PST nell'archivio espanso automaticamente di un utente. È possibile importare fino a 100 GB di dati dai file PST nella cassetta postale di archiviazione dell'utente.

## <a name="more-information"></a>Altre informazioni

Per ulteriori dettagli tecnici sull'espansione automatica dell'archiviazione, vedere [Microsoft 365: Domande](https://techcommunity.microsoft.com/t5/exchange-team-blog/office-365-auto-expanding-archives-faq/ba-p/607784)frequenti sull'espansione automatica degli archivi.
