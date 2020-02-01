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
ms.openlocfilehash: ab57bcd3cd21d691e8c2dc669a55588dbcaa886b
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "41595553"
---
# <a name="create-a-search"></a>Creare una ricerca

Nella scheda **ricerche** del caso, è possibile creare una nuova ricerca facendo clic su **nuova ricerca** e seguendo la procedura guidata.

## <a name="name-your-search-and-give-it-a-description"></a>Denominare la ricerca e dargli una descrizione

Ogni ricerca con un caso deve avere un nome univoco. Facoltativamente, è possibile fornire una descrizione per la ricerca. 

## <a name="define-your-search-query-and-conditions"></a>Definire la query di ricerca e le condizioni

È possibile definire la query di parole chiave e tutte le condizioni per la ricerca utilizzando le schede delle condizioni predefinite o utilizzando KQL (Keyword Query Language). Per ulteriori informazioni, vedere [creazione di query di ricerca](building-search-queries.md).

## <a name="choose-the-custodians-to-search-from"></a>Scegliere i depositari da cui eseguire la ricerca

Dopo aver definito le condizioni, è necessario scegliere quali posizioni si desidera ricercare. Un modo per farlo è specificare quali depositari sono già stati aggiunti al caso in cui si desidera eseguire la ricerca. Selezionando un custode, verrà eseguita la ricerca in tutte le origini dati mappate al custode. Per ulteriori informazioni su come aggiungere depositari al caso e gestire le origini dati, vedere [collaborare con i depositari](managing-custodians.md) .

## <a name="choose-non-custodial-locations"></a>Scegliere le posizioni non detentive

In alcuni casi, è possibile cercare le origini dati che non vengono mappate a un custode. In questo caso, è possibile specificare i percorsi che si desidera ricercare oppure scegliere di cercare tutti i percorsi di contenuto per uno specifico servizio di Office 365, ad esempio la ricerca in tutte le cassette postali di Exchange o in tutti i siti di SharePoint e OneDrive for business.