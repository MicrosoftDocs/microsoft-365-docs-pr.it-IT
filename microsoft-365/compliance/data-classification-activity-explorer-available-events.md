---
title: Azioni di etichettatura segnalate in Esplora attività
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: elenco delle azioni di etichettatura disponibili in Esplora attività.
ms.openlocfilehash: ed51c908d6968e3aeae0adbe06d9ba55887bcf83
ms.sourcegitcommit: 1c53f114a810e7aaa2dc876b84d66348492ea36c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/20/2021
ms.locfileid: "51902947"
---
# <a name="labeling-activities-that-are-available-in-activity-explorer"></a>Attività di etichettatura disponibili in Esplora attività

## <a name="sensitivity-label-applied"></a>Etichetta di riservatezza applicata

Questo evento viene generato ogni volta che un documento senza etichetta viene etichettato o viene inviato un messaggio di posta elettronica con un'etichetta. 

- Viene acquisito al momento del salvataggio nelle applicazioni native di Office e nelle applicazioni Web. 
- Viene acquisita al momento dell'occorrenza nei componenti aggiuntivi di Azure Information Protection. 
- Le azioni di aggiornamento e downgrade delle etichette possono essere monitorate anche tramite il *campo e* il filtro del tipo di evento Label.   


|Origine  |Segnalato in Esplora attività | Nota  |
|---------|---------|---------|
| Word, Excel, PowerPoint|sì |
|Outlook| sì |da Win 32 |
|SharePoint online, OneDrive|sì | |
|Exchange        |sì         | |
|Client unificato di Azure Information Protection (AIP) e scanner unificato AIP |sì |l'azione *nuova etichetta* AIP viene mappata *all'etichetta applicata* in Esplora attività   |
|Microsoft information protection (MIP) SDK         |sì|l'azione *nuova etichetta* AIP viene mappata *all'etichetta applicata* in Esplora attività|
|Rights Management Service (RMS)         |non applicabile         | |
|Power BI desktop e Web        | no| accessibile nei log di controllo di Microsoft 365         |
|Microsoft Cloud App Security (MCAS)         |no|         |

## <a name="sensitivity-label-changed"></a>Etichetta di riservatezza modificata

Questo evento viene generato ogni volta che un'etichetta viene aggiornata nel documento o nel messaggio di posta elettronica.

- Per le origini client unificato AIP, Scanner unificato e SDK MIP, l'etichetta di aggiornamento *AIP* e le azioni di *downgrade* dell'etichetta sono mappate all'etichetta esplora *attività modificata*

- Viene acquisito al momento del salvataggio nelle applicazioni native di Office e nelle applicazioni Web. 
- Viene acquisito al momento dell'occorrenza in Azure Information Protection componenti aggiuntivi client unificati e imposizioni dello scanner
- Le azioni di aggiornamento e downgrade delle etichette possono essere monitorate anche tramite il *campo e* il filtro del tipo di evento Label. Il *testo di giustificazione* viene acquisito anche ad eccezione di SharePoint Online e OneDrive.
- L'etichettatura di riservatezza eseguita nelle app native di Office in Outlook raccoglie l'ultima azione generata prima delle azioni di salvataggio/invio tramite posta elettronica dei file. Ad esempio, se l'utente modifica l'etichetta di un messaggio di posta elettronica più volte prima dell'invio, l'ultima etichetta trovata nel messaggio di posta elettronica al momento dell'invio viene acquisita nel log di controllo e quindi segnalata in Esplora attività. 


|Origine  |Segnalato in Esplora attività|Nota  |
|---------|---------|---------| 
|Word, Excel, PowerPoint         |sì         |
|Outlook         |sì         |Win 32|
|SharePoint Online, OneDrive         |sì         |
|Exchange         |sì         |
|Client unificato AIP         |sì         |
|Scanner unificato AIP         |sì         |
|MIP SDK         |sì         |
|Servizio RMS         |non applicabile         |
|Power BI desktop e Web         |no         |accessibile nei log di controllo di Microsoft 365 |
|MCAS     |no         |         |

## <a name="sensitivity-label-removed"></a>Etichetta di riservatezza rimossa

Questo evento viene generato ogni volta che un'etichetta viene rimossa da un file o da un documento.

- Questo evento viene acquisito al momento del salvataggio nelle applicazioni Native di Office e nelle applicazioni Web.
- Viene acquisita al momento dell'occorrenza nei componenti aggiuntivi di Azure Information Protection. 
- L'etichetta di riservatezza, con l'etichetta MIP nativa di Office, in Outlook raccoglie l'ultimo evento di etichettatura generato prima delle azioni di salvataggio/invio tramite posta elettronica dei file.

|Origine  |Segnalato in Esplora attività | Nota  |
|---------|---------|---------| 
|Word, Excel, PowerPoint         |sì         |
|Outlook         |sì         |Win 32|
|SharePoint Online, OneDrive         |sì         |
|Exchange         |sì         |
|Client unificato AIP         |sì         |l'azione rimuovi *etichetta* AIP viene mappata all'azione *rimossa dall'etichetta* in Esplora attività|
|Scanner unificato AIP         |sì         |l'azione rimuovi *etichetta* AIP viene mappata all'azione *rimossa dall'etichetta* in Esplora attività |
|MIP SDK         |sì         |l'azione rimuovi *etichetta* AIP viene mappata all'azione *rimossa dall'etichetta* in Esplora attività |
|Servizio RMS         |non applicabile         |
|Power BI desktop e Web         |no         |accessibile nei log di controllo di Microsoft 365 |
|MCAS     |no         |         |
 

## <a name="sensitivity-label-file-read"></a>File di etichette di riservatezza letto

Questo evento viene generato ogni volta che viene aperto un documento con etichetta o protetto.

|Origine  |Segnalato in Esplora attività | Nota  |
|---------|---------|---------| 
|Word, Excel, PowerPoint         |sì         |
|Outlook         |no         |
|SharePoint Online, OneDrive         |no         |
|Exchange         |no         |
|Client unificato AIP         |sì         |l'azione di *accesso* AIP è mappata all'azione *di lettura dei file* in Esplora attività|
|Scanner unificato AIP         |sì         |l'azione di *accesso* AIP è mappata all'azione *di lettura dei file* in Esplora attività|
|MIP SDK         |sì         |l'azione di *accesso* AIP è mappata all'azione *di lettura dei file* in Esplora attività|
|Servizio RMS         |sì         |*l'azione* di accesso viene mappata all'azione *di lettura dei file* in Esplora attività |
|Power BI desktop e Web         |no         |accessibile nei log di controllo di Microsoft 365 |
|MCAS     |no         |         |


## <a name="sensitivity-label-files-discovered"></a>File di etichette di riservatezza individuati

Questo evento viene generato ogni volta che i file vengono individuati quando AIP Scanner viene utilizzato per l'analisi dei dati sensibili in diverse posizioni e trova i file.

|Origine  |Segnalato in Esplora attività | Nota  |
|---------|---------|---------| 
|Word, Excel, PowerPoint         |non applicabile         |
|Outlook         |non applicabile         |
|SharePoint Online, OneDrive         |non applicabile         |
|Exchange         |non applicabile         |
|Client unificato AIP         |non applicabile       |
|Scanner unificato AIP         |sì         |l'azione *di* individuazione AIP è mappata all'azione *individuata dei file* in Esplora attività|
|MIP SDK         |sì         |l'azione *di* individuazione AIP è mappata all'azione *individuata nel file* in Esplora attività|
|Servizio RMS         |non applicabile         |
|Power BI desktop e Web         |non applicabile         |
|MCAS     |non applicabile         |         |


## <a name="sensitivity-label-file-renamed"></a>File di etichette di riservatezza rinominato

Questo evento viene generato ogni volta che un documento con un'etichetta di riservatezza viene rinominato. 

|Origine  | Segnalato in Esplora attività | Nota  |
|---------|---------|---------| 
|Word, Excel, PowerPoint         |sì         |
|Outlook         |non applicabile         |
|SharePoint Online, OneDrive         |no        |
|Exchange         |non applicabile         |
|Client unificato AIP         |no         |
|Scanner unificato AIP         |no         |
|MIP SDK         |no         |
|Servizio RMS         |no      |
|Power BI desktop e Web         |no         |
|MCAS     |no         |         |


## <a name="sensitivity-label-file-removed"></a>File dell'etichetta di riservatezza rimosso

Questo evento viene generato ogni volta che lo scanner AIP rileva che un file analizzato in precedenza è stato rimosso.

|Origine  |Segnalato in Esplora attività | Nota  |
|---------|---------|---------| 
|Word, Excel, PowerPoint         |non applicabile         |
|Outlook         |non applicabile         |
|SharePoint Online, OneDrive         |non applicabile           |
|Exchange         |non applicabile         |
|Client unificato AIP         |non applicabile            |
|Scanner unificato AIP         |sì         |
|MIP SDK         |non applicabile            |
|Servizio RMS         |non applicabile         |
|Power BI desktop e Web         |non applicabile  |
|MCAS     |non applicabile        |         |

### <a name="sensitivity-label-protection-applied"></a>Protezione dell'etichetta di riservatezza applicata

Questo evento viene generato la prima volta che la protezione viene aggiunta manualmente a un elemento che non dispone di un'etichetta.

|Origine  |Segnalato in Esplora attività | Nota  |
|---------|---------|---------| 
|Word, Excel, PowerPoint         |no         |
|Outlook         |no         |
|SharePoint Online, OneDrive         |non applicabile           |
|Exchange         |no       |
|Client unificato AIP         |sì            |
|Scanner unificato AIP         |non applicabile         |
|MIP SDK         |sì            |
|Servizio RMS         |non applicabile         |
|Power BI desktop e Web         |non applicabile            |
|MCAS     |non applicabile        |         |

## <a name="sensitivity-label-protection-changed"></a>Protezione dell'etichetta di riservatezza modificata

Questo evento viene generato ogni volta che la protezione di un documento senza etichetta viene modificata manualmente.

|Origine  |Segnalato in Esplora attività |
|---------|---------| 
|Word, Excel, PowerPoint         |no         |
|Outlook         |no         |
|SharePoint Online, OneDrive         |non applicabile           |
|Exchange         |no       |
|Client unificato AIP         |sì            |
|Scanner unificato AIP         |non applicabile         |
|MIP SDK         |sì            |
|Servizio RMS         |non applicabile         |
|Power BI desktop e Web         |non applicabile            |
|MCAS     |non applicabile        |

## <a name="sensitivity-label-protection-removed"></a>Protezione dell'etichetta di riservatezza rimossa

Questo evento viene generato ogni volta che la protezione di un documento senza etichetta viene modificata manualmente.

|Origine  |Segnalato in Esplora attività |
|---------|---------| 
|Word, Excel, PowerPoint         |no         |
|Outlook         |no         |
|SharePoint Online, OneDrive         |non applicabile           |
|Exchange         |no       |
|Client unificato AIP         |sì            |
|Scanner unificato AIP         |non applicabile         |
|MIP SDK         |sì            |
|Servizio RMS         |non applicabile         |
|Power BI desktop e Web         |non applicabile            |
|MCAS     |non applicabile        |

## <a name="sensitivity-label-dlp-policy-matched"></a>Criterio DLP dell'etichetta di riservatezza corrispondente

Questo evento viene generato ogni volta che viene trovata una corrispondenza con un criterio DLP.

|Origine  |Segnalato in Esplora attività |
|---------|---------| 
|Exchange         |sì       |
|SharePoint Online|sì          |
|OneDrive |sì|
|Teams |sì   |
|Dispositivi Windows 10         |sì |
|MAC         |no     |
|locale         |no|
|MCAS     |no        | 

Gli eventi per i dispositivi Windows 10 (ENDPOINT DLP) sono:

- file eliminato
- file creato
- file copiato negli Appunti
- file modificato
- file letto
- file stampato
- file rinominato
- file copiato in una condivisione di rete
- file accessibile dall'app non consentita


## <a name="retention-label-applied"></a>Etichetta di conservazione applicata 

Questo evento viene generato ogni volta che un documento senza etichetta viene etichettato o viene inviato un messaggio di posta elettronica con un'etichetta.

- Viene acquisito al momento del salvataggio nelle applicazioni native di Office e nelle applicazioni Web.

|Origine  |Segnalato in Esplora attività |
|---------|---------| 
|Exchange         |no       |
|SharePoint Online|sì          |
|OneDrive |sì|

## <a name="retention-label-changed"></a>Etichetta di conservazione modificata

Questo evento viene generato ogni volta che un'etichetta viene aggiornata in un documento o in un messaggio di posta elettronica.

- Viene acquisita al momento del salvataggio.

|Origine  |Segnalato in Esplora attività |
|---------|---------| 
|Exchange         |no       |
|SharePoint Online|sì          |
|OneDrive |sì|
 
## <a name="retention-label-removed"></a>Etichetta di conservazione rimossa

Questo evento viene generato ogni volta che un'etichetta viene rimossa da un file o da un documento.

- Viene acquisita al momento del salvataggio.

|Origine  |Segnalato in Esplora attività |
|---------|---------| 
|Exchange         |no       |
|SharePoint Online|sì          |
|OneDrive |sì|


## <a name="known-issues"></a>Problemi noti
  
- Quando la descrizione comando dell'etichetta consigliata viene visualizzata a un utente finale, non viene acquisita. Tuttavia, se l'utente sceglie di applicare l'etichetta  consigliata, l'etichetta verrà visualizzata nel campo Come applicato come *consigliato*  

- Il testo di giustificazione non è attualmente disponibile nel downgrade dell'etichetta di riservatezza da Sharepoint e OneDrive.  

- I tipi di informazioni riservate non sono attualmente disponibili per le attività di etichettatura automatica da Word, Excel, PowerPoint e Outlook, nonché da SharePoint Online e OneDrive.
