---
title: Creare una ricerca
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
description: Informazioni su come creare, definire e scegliere i responsabile e le posizioni dei depositario per una ricerca in un caso di Advanced eDiscovery.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 1d9051824ff3f28484d0750b982edd70334a9b88
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035768"
---
# <a name="create-a-search"></a>Creare una ricerca

Nella scheda **Ricerche** del caso è possibile creare una nuova ricerca facendo clic su Nuova ricerca **e** seguendo la procedura guidata.

![Ricerca guidata in un caso di Advanced eDiscovery](../media/AeDSearch1.png)

## <a name="name-the-search-and-give-it-a-description"></a>Assegnare un nome alla ricerca e assegnargli una descrizione

Ogni ricerca con un caso deve avere un nome univoco. Facoltativamente, è possibile fornire una descrizione per la ricerca. 

## <a name="choose-the-custodians-and-custodial-locations-to-search"></a>Scegliere i responsabile e le posizioni dei depositario in cui eseguire la ricerca

Scegliere i percorsi di contenuto dei depositario in cui eseguire la ricerca specificando i responsabile aggiunti al caso. Selezionando un responsabile, la ricerca verrà eseguita su tutte le origini dati mappate al responsabile. È inoltre possibile limitare la ricerca alle origini dati selezionate per ogni responsabile. Per ulteriori informazioni su come aggiungere i responsabile e gestire le origini dati, vedere [Collaborare con i responsabile.](managing-custodians.md)

## <a name="choose-non-custodial-locations"></a>Choose non-custodial locations

In alcuni casi, è possibile cercare origini dati non associate a un responsabile. In questo caso, è possibile specificare i percorsi in cui si desidera eseguire la ricerca oppure scegliere di cercare in tutti i percorsi di contenuto un servizio Microsoft specifico (ad esempio, la ricerca in tutte le cassette postali di Exchange o in tutti i siti di SharePoint e gli account di OneDrive).

## <a name="define-the-search-query-and-conditions"></a>Definire la query di ricerca e le condizioni

È possibile definire la query con parole chiave e qualsiasi condizione per la ricerca utilizzando le schede condizione predefinite o il linguaggio KQL (Keyword Query Language). Per ulteriori informazioni, vedere [Creare query di ricerca.](building-search-queries.md)
