---
title: 'Passaggio 2: configurare le connessioni Internet locali per ogni sede'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Comprendere e configurare la risoluzione DNS per migliorare le prestazioni.
ms.openlocfilehash: 2b3c38a9bf259f453121f7878992d1dc50f2ce97
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "34073266"
---
# <a name="step-2-configure-local-internet-connections-for-each-office"></a>Passaggio 2: configurare le connessioni Internet locali per ogni sede

*Questo passaggio è obbligatorio e si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*

![](./media/deploy-foundation-infrastructure/networking_icon-small.png)

Nel Passaggio 2, verificare che ogni sede abbia connessioni Internet locali e usi server DNS locali. Entrambi questi elementi sono obbligatori per ridurre la latenza della connessione e verificare che i computer client locali effettuino connessioni al punto di ingresso più vicino ai servizi basati sul cloud di Microsoft 365.

Nelle reti tradizionali per organizzazioni di grandi dimensioni, il traffico su Internet attraversa il backbone di rete fino a una connessione Internet centrale. Questo non funziona correttamente per l'ottimizzazione delle prestazioni per un'infrastruttura SaaS (Software-as-a-Service) distribuita in modo globale, che include i prodotti di Office 365 ed Enterprise Mobility + Security (EMS) in Microsoft 365.

La rete Microsoft Global Network include server front-end per il set di servizi cloud per Microsoft 365 a livello globale. Per prestazioni ottimali, i client locali devono accedere al server front-end più vicino a livello geografico, anziché inoltrare il traffico tramite un backbone di rete e al server front-end più vicino alla connessione Internet centrale dell'organizzazione.

Per indirizzare una richiesta client al server front-end più vicino a livello geografico, i server DNS di Microsoft usano le query DNS corrispondenti alla richiesta di connessione iniziale del client. Pertanto, per la latenza di rete inferiore:

- Tutte le sedi dell'organizzazione devvono avere connessioni Internet locali per il traffico di rete della categoria [Ottimizzazione](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#new-office-365-endpoint-categories).
- Ogni connessione Internet locale deve usare un server DNS locale per il traffico Internet in uscita da tale posizione.

Per ulteriori informazioni, vedere [Uscire dalle connessione di rete a livello locale](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#egress-network-connections-locally). 

Come checkpoint provvisorio, è possibile vedere i [criteri uscita](networking-exit-criteria.md#crit-networking-step2) per questo passaggio.

## <a name="next-step"></a>Passaggio successivo

|||
|:-------|:-----|
|![](./media/stepnumbers/Step3.png)|[Evitare fenomeni di "hairpinning" di rete](networking-avoid-network-hairpins.md)|
