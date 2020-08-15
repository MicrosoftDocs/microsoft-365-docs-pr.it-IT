---
title: Microsoft 365 gestione del danneggiamento dei dati
ms.author: josephd
author: JoeDavies-MSFT
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
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
description: In questo articolo viene illustrato il danneggiamento dei dati in Microsoft 365 e gli sforzi compiuti da Microsoft per impedire e recuperare i dati.
ms.openlocfilehash: fabecf8e368813e2f895669edc19c3f74e305c35
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46691141"
---
# <a name="dealing-with-data-corruption-in-microsoft-365"></a>Gestione del danneggiamento dei dati in Microsoft 365

Uno degli aspetti impegnativi dell'esecuzione di un servizio cloud su vasta scala consiste nel gestire il danneggiamento dei dati, in base all'elevato volume di dati e ai sistemi indipendenti. Il danneggiamento dei dati può essere causato da:

- Bug dell'infrastruttura o dell'applicazione che danneggiano alcuni o tutti lo stato dell'applicazione
- Problemi relativi all'hardware che determinano la perdita di dati o l'impossibilità di leggere i dati
- Errori operativi umani
- Hacker maligni e dipendenti scontenti
- Eventi imprevisti nei servizi esterni che causano una perdita di dati

Poiché una maggiore resilienza nell'integrità dei dati comporta meno incidenti di danneggiamento dei dati, Microsoft ha incorporato i meccanismi di protezione di Microsoft 365 per evitare che si verifichino danneggiamenti, nonché sistemi e processi che consentono di recuperare i dati in caso di problemi. I controlli e i processi sono presenti nelle varie fasi del processo di rilascio ingegneristico per aumentare la resilienza rispetto al danneggiamento dei dati, tra cui:

- Progettazione del sistema
- Organizzazione e struttura del codice
- Revisione del codice
- Unit test, test di integrazione e test di sistema
- Test/cancelli per cavi di viaggio

Negli ambienti di produzione Microsoft 365, la replica peer tra i datacenter garantisce che siano sempre presenti più copie live di tutti i dati. Le immagini e gli script standard vengono utilizzati per recuperare i server persi e i dati replicati vengono utilizzati per ripristinare i dati dei clienti. Grazie ai controlli e ai processi di resilienza dei dati incorporati, Microsoft mantiene solo i backup della documentazione del sistema di informazioni di Microsoft 365 (inclusa la documentazione relativa alla sicurezza), utilizzando la replica incorporata in SharePoint Online e lo strumento di repository del codice interno, Source Depot. La documentazione del sistema è archiviata in SharePoint Online e Source Depot contiene immagini di sistema e applicazioni. Sia SharePoint Online che Source Depot utilizzano il controllo delle versioni e vengono replicati in tempo quasi reale.
