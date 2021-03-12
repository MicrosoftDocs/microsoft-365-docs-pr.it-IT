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
- m365-security-compliance
search.appverid:
- MOE150
- MET150
description: Il flusso di lavoro predefinito di Advanced eDiscovery in Microsoft 365 si allinea al processo di eDiscovery descritto dal modello di riferimento per l'individuazione elettronica (EDRM).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f2e7886eb67a58b43e9fb638fafb358fd9ee832c
ms.sourcegitcommit: 3d48e198e706f22ac903b346cadda06b2368dd1e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/11/2021
ms.locfileid: "50727489"
---
# <a name="advanced-ediscovery-alignment-with-the-electronic-discovery-reference-model"></a>Allineamento avanzato di eDiscovery con il modello di riferimento per l'individuazione elettronica

Il flusso di lavoro predefinito di Advanced eDiscovery in Microsoft 365 si allinea al processo di eDiscovery descritto dal modello di riferimento per l'individuazione elettronica (EDRM).

![EdRM (Electronic Discovery Reference Model)](../media/EDRMv1.png)

(Origine immagine per gentile edrm.net. L'immagine di origine è stata resa disponibile in Creative Commons Attribution 3.0 Unported License.

A livello di alto livello, ecco come Advanced eDiscovery supporta il flusso di lavoro EDRM:

- **Identificazione.** Dopo aver identificato le potenziali persone di interesse per un'indagine, è possibile aggiungerle come responsabili (detti anche responsabili dei dati *,* perché potrebbero disporre di informazioni rilevanti per l'indagine) a un caso advanced eDiscovery. Dopo l'aggiunta degli utenti come custodi, è facile conservare, raccogliere ed esaminare i documenti depositario.

- **Conservazione.** Per conservare e proteggere i dati rilevanti per un'indagine, Advanced eDiscovery consente di conservare legalmente le origini dati associate ai custodi in un caso. È inoltre possibile mettere in attesa i dati non depositario. Advanced eDiscovery include anche un flusso di lavoro integrato per le comunicazioni, in modo da poter inviare notifiche di blocco legale ai custodi e tenere traccia dei loro riconoscimenti.

- **Insieme.** Dopo aver identificato (e conservato) le origini dati rilevanti per l'indagine, è possibile utilizzare lo strumento di ricerca incorporato in Advanced eDiscovery per cercare e raccogliere dati in tempo reale dalle origini dati di custodia (e da origini dati non depositate, se applicabile) che potrebbero essere rilevanti per il caso.

- **Elaborazione.** Dopo aver raccolto tutti i dati rilevanti per il caso, il passaggio successivo consiste nell'elaborarlo per un'ulteriore revisione e analisi. In Advanced eDiscovery, i dati sul posto identificati nella fase di raccolta vengono copiati in un percorso di archiviazione di Azure (denominato *set* di revisione), che fornisce una visualizzazione statica dei dati del caso. 

- **Revisione.** Dopo aver aggiunto i dati a un set di revisioni, è possibile visualizzare documenti specifici ed eseguire query aggiuntive per ridurre i dati a ciò che è più rilevante per il caso. Inoltre, è possibile aggiungere annotazioni e contrassegnare documenti specifici.

- **Analisi.** Advanced eDiscovery offre uno strumento di analisi integrato che consente di aggiungere ulteriori dati dal set di revisione che si determina non è rilevante per l'indagine. Oltre a ridurre il volume di dati rilevanti, Advance eDiscovery consente inoltre di risparmiare sui costi di revisione legale consentendo di organizzare il contenuto per semplificare ed efficienza il processo di revisione.

- **Produzione** e **presentazione.** Quando si è pronti, è possibile esportare i documenti da un set di recensioni per la revisione legale. È possibile esportare i documenti nel formato nativo o in un formato specificato da EDRM in modo che possano essere importati in applicazioni di revisione di terze parti.

## <a name="more-information"></a>Ulteriori informazioni

Per iniziare a usare Advanced eDiscovery, vedere:

- [Configurare Advanced eDiscovery](get-started-with-advanced-ediscovery.md)

- [Creare e gestire un caso advanced eDiscovery](create-and-manage-advanced-ediscoveryv2-case.md)