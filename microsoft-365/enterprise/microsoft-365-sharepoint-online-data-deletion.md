---
title: Eliminazione dei dati di Microsoft 365 SharePoint Online
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
f1.keywords:
- NOCSH
description: Informazioni su come funziona l'eliminazione dei dati in SharePoint Online, ad esempio la posizione in cui è archiviato il contenuto eliminato e per quanto tempo.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 888ee807e6cd4ddc435c1df86a63502a617d6cb8
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769043"
---
# <a name="sharepoint-online-data-deletion-in-microsoft-365"></a>Eliminazione dei dati di SharePoint online in Microsoft 365

SharePoint Online archivia gli oggetti come codice astratto all'interno dei database dell'applicazione. Quando un utente carica un file in SharePoint Online, tale file viene disassemblato e convertito in codice dell'applicazione e archiviato in più tabelle tra più database. In SharePoint Online, tutto il contenuto del caricamento di un cliente è suddiviso in blocchi, crittografato (con una o più chiavi AES 256 bit) e distribuito in tutto il centro dati. 

In SharePoint Online, gli elementi vengono conservati per 93 giorni dal momento in cui vengono eliminati dal percorso originale. Rimangono nel cestino del sito per tutto il tempo, a meno che qualcuno non li elimini o svuoti quel cestino. In tal caso, gli elementi passano al cestino della raccolta siti, in cui restano per il resto dei 93 giorni. Per informazioni su come ripristinare gli elementi eliminati, vedere [ripristinare gli elementi nel cestino di un sito di SharePoint](https://support.office.com/article/6df466b6-55f2-4898-8d6e-c0dff851a0be#ID0EAADAAA=Online
) e [ripristinare gli elementi eliminati dal cestino della raccolta siti](https://support.office.com/article/5fa924ee-16d7-487b-9a0a-021b9062d14b). Il tempo di conservazione del cestino non è configurabile in SharePoint Online.

Quando si elimina una raccolta siti, si elimina anche la gerarchia dei siti nell'insieme e tutto il contenuto all'interno di essi:

- Documenti e raccolte documenti
- Elenchi e dati di elenco
- Impostazioni di configurazione del sito
- Informazioni sul ruolo e sulla sicurezza correlate al sito o ai relativi siti secondari
- Siti secondari del sito Web principale, del relativo contenuto e delle informazioni utente

Se si elimina accidentalmente una raccolta siti, è possibile ripristinarla da un amministratore globale o di SharePoint utilizzando l'interfaccia di amministrazione di SharePoint.

Le raccolte siti eliminate vengono conservate per 93 giorni. Dopo 93 giorni, i siti e tutto il relativo contenuto e le impostazioni vengono eliminati definitivamente, inclusi elenchi, raccolte, pagine e siti secondari.

L'eliminazione non consentita si verifica quando un utente elimina gli elementi eliminati dal cestino della raccolta siti, quando scade il periodo di conservazione e di backup oppure quando un amministratore Elimina definitivamente una raccolta siti utilizzando il [cmdlet Remove-SPODeletedSite](/powershell/module/sharepoint-online/Remove-SPODeletedSite?view=sharepoint-ps). Quando un utente Elimina (Elimina definitivamente o Elimina in modo definitivo) contenuto da SharePoint Online, vengono eliminate anche tutte le chiavi di crittografia per i blocchi eliminati. I blocchi nei dischi che in precedenza sono stati memorizzati nei blocchi eliminati vengono contrassegnati come inutilizzati e disponibili per il riutilizzo.
