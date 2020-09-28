---
title: Tassonomia dell'archivio termini di sfruttamento durante la creazione di un estrattore
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 10/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Tassonomia dei termini di sfruttamento dei dati durante la creazione di un estrattore nel modello di comprensione del documento in Microsoft SharePoint Syntex.
ms.openlocfilehash: 94f7a0389d2f06e0f8c1a60a341a02e43dfb2071
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/28/2020
ms.locfileid: "48296014"
---
# <a name="leverage-term-store-taxonomy-when-creating-an-extractor"></a>Tassonomia dell'archivio termini di sfruttamento durante la creazione di un estrattore


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

Quando si crea un estrattore nel modello di comprensione dei documenti in SharePoint Syntex, è possibile utilizzare la tassonomia archivio termini di [servizi metadati gestiti](https://docs.microsoft.com/sharepoint/managed-metadata#terms) per visualizzare le condizioni preferite per i dati estratti.  

Ad esempio, il modello identifica e classifica tutti i documenti del **contratto** caricati nella raccolta documenti.  Inoltre, il modello estrae un valore del **servizio contratto** da ogni contratto e lo Visualizza in una colonna della visualizzazione libreria. Tra i vari valori dei servizi contratto nei contratti, esistono diversi valori precedenti che la società non utilizza più e che sono stati rinominati. Ad esempio, tutti i riferimenti ai termini *progettazione*, *grafica*o servizi contratto di *topografia* dovrebbero ora essere chiamati *creativi*. Ogni volta che il modello estrae uno dei termini obsoleti da un documento del contratto, si desidera che visualizzi il termine-creatività corrente nella visualizzazione libreria. Nell'esempio riportato di seguito, durante l'addestramento del modello viene visualizzato che un documento di esempio contiene il termine obsoleto di *progettazione*.

   ![Archivio termini](../media/content-understanding/design.png)</br>


## <a name="term-set-synonyms"></a>Sinonimi set di termini 

I set di termini sono configurati nell'archivio termini dei servizi metadati gestiti nell'interfaccia di amministrazione di SharePoint. Nell'esempio riportato di seguito, il [set](https://docs.microsoft.com/sharepoint/managed-metadata#term-set) di termini *Servizi contratto* è configurato per includere una serie di condizioni, tra cui la *creatività*.  I dettagli indicano che il termine ha tre sinonimi (*progettazione*, *grafica*e *topografia*) e che i sinonimi devono essere tradotti in *creatività*.

   ![Term set](../media/content-understanding/term-store.png)</br>

<Mike, ecco dove non sono sicuro su come descriverlo.  Azione indica al modello che quando si crea un estrattore per estrarre e visualizzare una colonna di servizi contratto, come viene indicata la colonna "contrassegnato" per l'utilizzo del set di termini per i metadati gestiti per i servizi creativi? >

## <a name="configure-your-document-library-site-column-for-a-managed-metadata-field"></a>Configurare la colonna del sito della raccolta documenti per un campo metadati gestiti


   ![Creare metadati gestiti](../media/content-understanding/creative.png)</br>

## <a name="see-also"></a>Vedere anche
[Introduzione ai metadati gestiti](https://docs.microsoft.com/sharepoint/managed-metadata#terms)</br>
[Creare un estrattore](create-an-extractor.md)</br>
[Creare una colonna di metadati gestiti](https://support.microsoft.com/office/create-a-managed-metadata-column-8fad9e35-a618-4400-b3c7-46f02785d27f?redirectSourcePath=%252farticle%252fc2a06717-8105-4aea-890d-3082853ab7b7&ui=en-US&rs=en-US&ad=US)</br>





