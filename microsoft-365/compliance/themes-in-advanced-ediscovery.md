---
title: Temi-eDiscovery
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
description: Utilizzare i temi in Advanced eDiscovery per organizzare i set di revisione individuando il tema dominante in ciascun documento.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 3dfc0dca0c6ed62e3ce8384efa2fd3ea407c3ce8
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285532"
---
# <a name="themes-in-advanced-ediscovery"></a>Temi in Advanced eDiscovery

In che modo una persona scrive un documento? In genere iniziano con una o più idee che vogliono trasmettere nel documento e compongono l'utilizzo di parole che si allineano con le idee. Più è prevalente un'idea, più le parole che sono correlate a quell'idea tendono ad essere. In questo modo si informa come gli utenti utilizzano i documenti. La cosa importante da capire dalla lettura di un documento è l'idea che il documento sta cercando di trasmettere, quali sono le idee in cui vengono visualizzate e quali sono le relazioni tra le idee.

Questo può essere esteso a come una persona desidera utilizzare un insieme di documenti. Desiderano vedere quali idee sono presenti nei set e quali documenti si riferiscono a queste idee. Inoltre, se trovano un particolare documento di interesse, vogliono essere in grado di visualizzare i documenti che discutono di idee simili.

La funzionalità temi in Advanced eDiscovery tenta di simulare il modo in cui gli umani ragionano sui documenti, analizzando i *temi* discussi in un set di revisione e assegnando un tema ai documenti nel set di revisione. In Advanced eDiscovery, i temi fanno un ulteriore passo avanti e identificano il *tema dominante* in ciascun documento. Il tema dominante è quello che viene visualizzato più spesso in un documento.

## <a name="how-does-themes-work"></a>Modalità di funzionamento dei temi

La funzionalità temi analizza i documenti con testo in un set di revisione per analizzare i temi comuni visualizzati in tutti i documenti del set di revisione. Advanced eDiscovery assegna tali temi ai documenti in cui vengono visualizzati. Contrassegna inoltre ogni tema con le parole utilizzate nei documenti rappresentativi del tema. Poiché un documento può contenere diversi tipi di argomenti, Advanced eDiscovery spesso assegna più temi ai documenti. Il tema più prominente in un documento è designato come tema dominante.
