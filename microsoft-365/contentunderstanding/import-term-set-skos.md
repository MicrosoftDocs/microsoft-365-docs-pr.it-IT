---
title: Importare un set di termini con un formato basato su SKOS
description: Scopri come importare un set di termini con un formato basato su SKOS
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.service: ''
ms.collection: enabler-strategic
search.appverid: ''
localization_priority: Priority
ms.openlocfilehash: 8a1b61088d0a1594bf1a71542158ade389cce2ab
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288516"
---
# <a name="import-a-term-set-using-a-skos-based-format"></a>Importare un set di termini con un formato basato su SKOS

È possibile importare un set di termini con un formato basato su SKOS. Per informazioni dettagliate sul formato, vedere [Riferimenti sul formato SKOS per la tassonomia di SharePoint.](skos-format-reference.md) Con questa funzionalità è richiesta una licenza di [SharePoint Syntex](index.md).

Si consiglia di mantenere meno di 20.000 termini nei file di importazione. I file più grandi possono aumentare il tempo necessario per la convalida e l'importazione.

1. Nell'interfaccia di amministrazione di SharePoint espandere i **Servizi per contenuti**, quindi fare clic su **Archivio termini**.

2. Selezionare il gruppo di termini in cui si desidera importare il set di termini.

3. Nella barra dei comandi, fare clic su **Importa set di termini**. 

4. Se si vuole desidera scaricare un file di esempio da usare come modello, fare clic su **sample-metadata.ttl** per ottenere un file di esempio che usa il formato basato su SKOS.

5. Creare il file di importazione contenente i set di termini e i termini che si desidera importare.

6. In **Formato file**, selezionare **SKOS (*.ttl)**.

7. Fare clic su **Sfoglia**, raggiungere e aggiungere il file di importazione.

8. Fare clic su **Importa**. Non chiudere il pannello fino al completamento dell'importazione.

Dopo l'importazione del file, viene visualizzato un messaggio di esito positivo, l'archivio termini viene aggiornato e sarà possibile passare al set di termini appena creato.

## <a name="see-also"></a>Vedere anche

[Introduzione ai metadati gestiti](/sharepoint/managed-metadata)

[Panoramica sull'interpretazione del documento](document-understanding-overview.md)

[Importare set di termini (a livello di sito)](https://support.microsoft.com/office/168fbc86-7fce-4288-9a1f-b83fc3921c18)
