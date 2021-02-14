---
title: Temi - eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Utilizzare Temi in Advanced eDiscovery per organizzare i set di revisioni individuando il tema dominante in ogni documento.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 3dfc0dca0c6ed62e3ce8384efa2fd3ea407c3ce8
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285532"
---
# <a name="themes-in-advanced-ediscovery"></a>Temi in Advanced eDiscovery

In che modo una persona scrive un documento? In genere iniziano con una o più idee che vogliono trasmettere nel documento e mettono parole in linea con le idee. L'idea più diffusa è che più frequenti sono le parole correlate a tale idea. In questo modo si informa anche il modo in cui gli utenti utilizzano i documenti. La cosa importante da comprendere durante la lettura di un documento sono le idee che il documento sta cercando di trasmettere, quali idee appaiono dove e quali sono le relazioni tra le idee.

Questo può essere esteso al modo in cui un utente vuole usare un set di documenti. Vogliono vedere quali idee sono presenti nei set e quali documenti parlano di tali idee. Inoltre, se trovano un particolare documento di interesse, desiderano essere in grado di visualizzare documenti che discutono di idee simili.

La funzionalità Temi di Advanced eDiscovery tenta di simulare il  modo in cui l'utente fa ragione sui documenti, analizzando i temi descritti in un insieme da rivedere e assegnando un tema ai documenti nell'insieme da rivedere. In Advanced eDiscovery, i temi vanno oltre e identificano il *tema dominante* in ogni documento. Il tema dominante è quello che viene visualizzato più spesso in un documento.

## <a name="how-does-themes-work"></a>Come funzionano i temi?

La funzionalità Temi analizza i documenti con il testo in un insieme da rivedere per analizzare i temi comuni che vengono visualizzati in tutti i documenti del set di revisioni. Advanced eDiscovery assegna tali temi ai documenti in cui vengono visualizzati. Inoltre, ogni tema viene etichettato con le parole utilizzate nei documenti che sono rappresentative del tema. Poiché un documento può contenere vari tipi di materia, Advanced eDiscovery spesso assegna più temi ai documenti. Il tema che viene visualizzato in modo più evidente in un documento viene designato come tema dominante.
