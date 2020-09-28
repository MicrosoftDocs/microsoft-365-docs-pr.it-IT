---
title: Importare un set di termini utilizzando un formato basato su SKOS
description: Informazioni su come importare un set di termini utilizzando un formato basato su SKOS
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: aaed88463f690853672780b48a8ee3857a956847
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/28/2020
ms.locfileid: "48296079"
---
# <a name="import-a-term-set-using-a-skos-based-format"></a>Importare un set di termini utilizzando un formato basato su SKOS

È possibile importare un set di termini utilizzando un formato basato su SKOS. Per informazioni dettagliate sul formato, vedere [SharePoint tassonomia SKOS format reference](skos-format-reference.md).

È consigliabile mantenere i file di importazione su un valore inferiore a 20.000 termini. I file di grandi dimensioni possono aumentare il tempo necessario per la convalida e l'importazione.

1. Nell'interfaccia di amministrazione di SharePoint espandere **servizi di contenuto**e quindi fare clic su **archivio termini**.

2. Selezionare il gruppo di termini in cui si desidera importare il set di termini.

3. Nella barra dei comandi, fare clic su **Importa set di termini**.
 
4.  Se si desidera scaricare un file di esempio da utilizzare come modello, fare clic su **Sample-Metadata. TTL** per ottenere un file di esempio che utilizza il formato basato su SKOS.
 
5.  Creare il file di importazione contenente i set di termini & condizioni che si desidera importare.

6.  In **formato file**selezionare **SKOS (*. TTL)**.

7.  Fare clic su **Sfoglia** e passare a e aggiungere il file di importazione.

8.  Fare clic su **Importa**. Non chiudere il pannello fino a quando non viene completata l'importazione.

Al termine dell'importazione del file verrà visualizzato un messaggio di esito positivo e l'archivio termini verrà aggiornato ed è possibile passare ai set di termini appena creati.

## <a name="see-also"></a>Vedere anche

[Introduzione ai metadati gestiti](https://docs.microsoft.com/sharepoint/managed-metadata)

[Panoramica della comprensione del documento](document-understanding-overview.md)

[Set di termini di importazione (livello di sito)](https://support.microsoft.com/office/168fbc86-7fce-4288-9a1f-b83fc3921c18)