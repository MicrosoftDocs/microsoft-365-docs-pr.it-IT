---
title: Note sulla versione per le indagini sui dati (Preview) in Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: In questo articolo viene descritto il nuovo strumento di analisi dei dati (Preview) in Microsoft 365.
ms.openlocfilehash: 57605566a8847a3630e1c4656f98f71ebb414f86
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "41595413"
---
# <a name="release-notes-for-data-investigations-preview-in-microsoft-365"></a>Note sulla versione per le indagini sui dati (Preview) in Microsoft 365

È possibile utilizzare lo strumento nuovo data Investigation (Preview) in in Microsoft 365 per valutare, esaminare e correggere gli incidenti correlati ai dati, ad esempio un evento di fuoriuscita dei dati o un'indagine interna. L'anteprima pubblica delle indagini sui dati fornisce l'accesso tempestivo alle funzionalità e agli aggiornamenti imminenti. Per ottenere un accesso rapido alle funzionalità più recenti, creare una nuova indagine in indagini sui dati (Preview) nel centro sicurezza & conformità. Per informazioni, vedere [gestire un problema di fuoriuscita dei dati in Microsoft 365](manage-data-spillage-incidents.md).

## <a name="whats-new"></a>Novità 

- **Indagini** : è possibile raggruppare le ricerche e gli eventi imprevisti creando un'indagine. Gestire gli utenti che possono accedere all'indagine aggiungendo o rimuovendo membri.  È inoltre possibile selezionare e contrassegnare le indagini preferite. Tenere conto e monitorare le attività all'interno e nelle indagini con i nuovi dashboard. Dopo aver completato le indagini, è possibile chiuderlo o eliminarlo.

- **Persone di interesse** : quando si aggiungono gli utenti alle indagini come persone di interesse, è possibile visualizzare i siti di cassette postali, OneDrive for business e Microsoft teams. È possibile utilizzarli per l'ambito delle ricerche di contenuto investigativo. Per indagare ulteriormente su una persona interessata, è anche possibile visualizzare i record di controllo relativi alle attività in Office 365 e in altri servizi Microsoft.

- **Ricerche** – creare una ricerca a livello di organizzazione utilizzando varie condizioni di ricerca. Se si conoscono gli utenti o i siti che si desidera cercare, è possibile farlo aggiungendoli come persone di interesse o specificando le posizioni del sito nella procedura guidata per la creazione della ricerca. 

- **Evidence** : creare un nuovo set di evidenze e aggiungere i risultati della ricerca che si desidera esaminare. È possibile esaminare singoli documenti, annotare per lasciare note di indagine ed esportare i risultati in modo che vengano spostati in un ambiente diverso. 

- **Recensione** : utilizzare una visualizzazione nativa, di testo e quasi nativa per esaminare i documenti aggiunti a un evento imprevisto. È inoltre possibile applicare analisi ai documenti per raggruppare gli elementi in base ai duplicati, ai thread di posta elettronica e ai temi, che possono essere utili per assistere la revisione dell'evento. 

- **Redigere, tag e annotazioni** – testo di redigere, applicare i tag e creare annotazioni durante la revisione dei documenti.
  
- **Indicizzazione avanzata** – se sono presenti elementi parzialmente indicizzati, verranno reindicizzati su richiesta in modo che tutti i dati siano disponibili per la ricerca.

- Correzione degli errori: correzione o download di un **errore** di elaborazione. Questo include il supporto per la correzione di tipi di file di grandi dimensioni, file protetti da password e altri problemi relativi agli errori di indicizzazione. 

- **Jobs** – verifica lo stato dei processi con esecuzione prolungata.

- **Eliminare definitivamente gli elementi della cassetta postale** -in situazioni urgenti, potrebbe essere necessario eliminare in modo definitivo gli elementi fuori luogo. A tale scopo, è possibile eseguire il comando **New-ComplianceSearchAction-Purge-PurgeType HardDelete** nel centro sicurezza & Compliance Center PowerShell per rimuovere definitivamente gli elementi dalle cassette postali. Per altre informazioni, vedere [New-ComplianceSearchAction](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/new-compliancesearchaction).
