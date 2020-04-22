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
description: ''
ms.openlocfilehash: 4b740b07b59b7500b8f57584767796b7f31ae87d
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43635976"
---
# <a name="create-a-search"></a>Creare una ricerca

Nella scheda **ricerche** del caso, è possibile creare una nuova ricerca facendo clic su **nuova ricerca** e seguendo la procedura guidata.

![La procedura guidata di ricerca in un caso avanzato di eDiscovery](../media/AeDSearch1.png)

## <a name="name-the-search-and-give-it-a-description"></a>Denominare la ricerca e assegnarle una descrizione

Ogni ricerca con un caso deve avere un nome univoco. Facoltativamente, è possibile fornire una descrizione per la ricerca. 

## <a name="choose-the-custodians-and-custodial-locations-to-search"></a>Scegliere i depositari e le posizioni di custodia per la ricerca

Scegliere posizioni di contenuto custode per la ricerca specificando i depositari che sono stati aggiunti al caso. Selezionando un custode, verrà eseguita la ricerca in tutte le origini dati mappate al custode. È inoltre possibile limitare la ricerca a origini dati selezionate per ogni custode. Per ulteriori informazioni su come aggiungere depositari e gestire le origini dati, vedere [lavorare con i depositari](managing-custodians.md).

## <a name="choose-non-custodial-locations"></a>Scegliere le posizioni non detentive

In alcuni casi, è possibile che si desideri cercare origini dati che non sono associate a un custode. In questo caso, è possibile specificare i percorsi che si desidera ricercare oppure scegliere di cercare tutti i percorsi di contenuto per uno specifico servizio Microsoft, ad esempio la ricerca in tutte le cassette postali di Exchange o di tutti i siti di SharePoint e gli account di OneDrive.

## <a name="define-the-search-query-and-conditions"></a>Definire la query di ricerca e le condizioni

È possibile definire la query di parole chiave e tutte le condizioni per la ricerca utilizzando le schede delle condizioni predefinite o utilizzando KQL (Keyword Query Language). Per ulteriori informazioni, vedere [creazione di query di ricerca](building-search-queries.md).
