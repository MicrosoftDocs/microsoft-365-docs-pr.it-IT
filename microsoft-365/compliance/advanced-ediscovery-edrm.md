---
title: Allineamento di Advanced eDiscovery con EDRM
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
description: Il flusso di lavoro predefinito di Advanced eDiscovery in Microsoft 365 è allineato al processo eDiscovery delineato dal modello di riferimento per l'individuazione elettronica (EDRM, Electronic Discovery Reference Model).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4ca94baf1fc57ac014a32a80ddc5705feeb2c842
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841634"
---
# <a name="advanced-ediscovery-alignment-with-the-electronic-discovery-reference-model"></a>Allineamento di Advanced eDiscovery con il modello di riferimento per l'individuazione elettronica

Il flusso di lavoro predefinito di Advanced eDiscovery in Microsoft 365 è allineato al processo eDiscovery delineato dal modello di riferimento per l'individuazione elettronica (EDRM, Electronic Discovery Reference Model).

![Electronic Discovery Reference Model (EDRM)](../media/EDRMv1.png)

(Origine immagine per gentile edrm.net. L'immagine di origine è stata resa disponibile in Creative Commons Attribution 3.0 Unported License.

A livello elevato, ecco come Advanced eDiscovery supporta il flusso di lavoro EDRM:

- **Identificazione.** Dopo aver identificato potenziali persone di interesse in un'indagine, è possibile aggiungerle come responsabili (detti anche responsabili dei *dati,* perché potrebbero disporre di informazioni rilevanti per l'indagine) a un caso di Advanced eDiscovery. Dopo l'aggiunta degli utenti come responsabile, è facile conservare, raccogliere ed esaminare i documenti dei revisori.

- **Conservazione.** Per conservare e proteggere i dati rilevanti per un'indagine, Advanced eDiscovery consente di conservare a livello legale le origini dati associate ai responsabile in un caso. È anche possibile mettere in attesa i dati non dei depositario. Advanced eDiscovery include anche un flusso di lavoro di comunicazione incorporato che consente di inviare notifiche di blocco a un responsabile e di tenere traccia dei loro riconoscimenti.

- **Insieme.** Dopo aver identificato (e conservato) le origini dati rilevanti per l'indagine, è possibile utilizzare lo strumento di ricerca incorporato in Advanced eDiscovery per cercare e raccogliere i dati in tempo reale dalle origini dati del responsabile (e da origini dati non di tipo depositario, se applicabile) che potrebbero essere rilevanti per il caso.

- **Elaborazione.** Dopo aver raccolto tutti i dati rilevanti per il caso, il passaggio successivo consiste nell'elaborarlo per un'ulteriore revisione e analisi. In Advanced eDiscovery, i dati sul posto identificati nella fase di raccolta vengono copiati in un percorso di archiviazione di Azure (denominato *insieme* da rivedere), che fornisce una visualizzazione statica dei dati del caso. 

- **Revisione.** Dopo aver aggiunto i dati a un insieme da rivedere, è possibile visualizzare documenti specifici ed eseguire query aggiuntive per ridurre i dati a ciò che è più rilevante per il caso. Inoltre, è possibile aggiungere annotazioni e contrassegnare documenti specifici.

- **Analisi.** Advanced eDiscovery fornisce uno strumento di analisi integrato che consente di aggiungere ulteriori dati dal set di recensioni che si determina non è rilevante per l'indagine. Oltre a ridurre il volume di dati pertinenti, Advance eDiscovery consente anche di risparmiare sui costi di revisione legale consentendo di organizzare il contenuto per rendere il processo di revisione più semplice ed efficiente.

- **Produzione** e **presentazione.** Quando si è pronti, è possibile esportare i documenti da un insieme di recensioni per la revisione legale. È possibile esportare i documenti nel formato nativo o in un formato specificato da EDRM in modo che possano essere importati in applicazioni di revisione di terze parti.

## <a name="more-information"></a>Altre informazioni

Per iniziare a usare Advanced eDiscovery, vedere:

- [Configurare Advanced eDiscovery](get-started-with-advanced-ediscovery.md)

- [Creare e gestire un caso di Advanced eDiscovery](create-and-manage-advanced-ediscoveryv2-case.md)