---
title: Allineamento avanzato di eDiscovery con EDRM
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-aed
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Il flusso di lavoro incorporato di Advanced eDiscovery in Microsoft 365 è allineato al processo eDiscovery delineato dal modello di riferimento di Electronic Discovery (EDRM).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4ca94baf1fc57ac014a32a80ddc5705feeb2c842
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841634"
---
# <a name="advanced-ediscovery-alignment-with-the-electronic-discovery-reference-model"></a>Allineamento avanzato di eDiscovery con il modello di riferimento per l'individuazione elettronica

Il flusso di lavoro incorporato di Advanced eDiscovery in Microsoft 365 è allineato al processo eDiscovery delineato dal modello di riferimento di Electronic Discovery (EDRM).

![EDRM (Electronic Discovery Reference Model)](../media/EDRMv1.png)

(Fonte di immagini per gentile concessione di edrm.net. L'immagine di origine è stata resa disponibile nella licenza Creative Commons Attribution 3,0 Unported.

A livello elevato, ecco come Advanced eDiscovery supporta il flusso di lavoro di EDRM:

- **Identificazione.** Dopo aver identificato potenziali persone di interesse in un'indagine, è possibile aggiungerle come depositari (denominate anche *depositari dei dati*, in quanto potrebbero essere in possesso di informazioni rilevanti per l'indagine) in un caso di eDiscovery avanzato. Dopo che gli utenti vengono aggiunti come depositari, è facile conservare, raccogliere e rivedere i documenti del custode.

- **Conservazione.** Per conservare e proteggere i dati rilevanti per un'indagine, Advanced eDiscovery consente di inserire una conservazione legale sulle origini dati associate ai depositari in un caso. È inoltre possibile inserire i dati non detentivi in attesa. Advanced eDiscovery dispone anche di un flusso di lavoro di comunicazione incorporato in modo da poter inviare notifiche di archiviazione legale ai depositari e tenere conto dei loro ringraziamenti.

- **Raccolta.** Dopo aver identificato (e conservato) le origini dati rilevanti per l'analisi, è possibile utilizzare lo strumento di ricerca incorporato in Advanced eDiscovery Search for and Collect Live Data from the detenzione Data Sources (e le origini dati non detentive, se applicabile) che potrebbero essere rilevanti per il caso.

- **Elaborazione.** Dopo aver raccolto tutti i dati rilevanti per il caso, il passaggio successivo consiste nel processo per ulteriori riesami e analisi. In Advanced eDiscovery, i dati sul posto identificati nella fase di raccolta vengono copiati in un percorso di archiviazione di Azure (denominato *set di revisione*), in cui viene fornita una visualizzazione statica dei dati del caso. 

- **Recensione.** Dopo aver aggiunto i dati a un set di revisione, è possibile visualizzare documenti specifici ed eseguire query aggiuntive per ridurre i dati a ciò che è più pertinente per il caso. Inoltre, è possibile annotare e contrassegnare documenti specifici.

- **Analisi.** Advanced eDiscovery fornisce uno strumento di analisi integrata che consente di eliminare i dati dall'insieme di revisione che si determina non è pertinente per l'indagine. Oltre a ridurre il volume dei dati rilevanti, Advance eDiscovery aiuta anche a salvare i costi di revisione legale, consentendo di organizzare il contenuto per semplificare e rendere più efficiente il processo di revisione.

- **Produzione** e **presentazione.** Quando si è pronti, è possibile esportare i documenti da un set di revisione per la revisione legale. È possibile esportare documenti nel formato nativo o in un formato specificato per EDRM in modo che possano essere importati in applicazioni di revisione di terze parti.

## <a name="more-information"></a>Ulteriori informazioni

Per iniziare a utilizzare Advanced eDiscovery, vedere:

- [Configurare Advanced eDiscovery](get-started-with-advanced-ediscovery.md)

- [Creazione e gestione di un caso di eDiscovery avanzato](create-and-manage-advanced-ediscoveryv2-case.md)