---
title: 'Passaggio 2: configurare le connessioni Internet locali per ogni sede'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/20/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Comprendere e configurare la risoluzione DNS per migliorare le prestazioni.
ms.openlocfilehash: bc1460ec40cda26d4784c7af5e909e4dca3c1f24
ms.sourcegitcommit: d818828c66cf98b0b0037ba8b3cb790c940281b7
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43583438"
---
# <a name="step-2-configure-local-internet-connections-for-each-office"></a>Passaggio 2: configurare le connessioni Internet locali per ogni sede

*Questo passaggio è obbligatorio e si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*

![Fase 1: collegamento in rete](../media/deploy-foundation-infrastructure/networking_icon-small.png)

Nel Passaggio 2, verificare che ogni sede abbia connessioni Internet locali e usi server DNS locali. Entrambi questi elementi sono obbligatori per ridurre la latenza della connessione e verificare che i computer client locali effettuino connessioni al punto di ingresso più vicino ai servizi basati sul cloud di Microsoft 365.

Nelle reti tradizionali per le aziende il traffico Internet viaggia lungo il backbone della rete verso una connessione Internet centrale. Questo comportamento non è ideale per ottimizzare le prestazioni di un'infrastruttura SaaS (Software-as-a-Service) distribuita a livello globale, che include i prodotti Office 365 e Intune in Microsoft 365.

La rete globale di Microsoft include un'infrastruttura *frontdoor di servizi distribuiti*, un server perimetrale di rete a disponibilità e scalabilità elevata con posizioni geograficamente distribuite. Tale infrastruttura termina le connessioni degli utenti finali presso un server frontdoor e instrada in modo efficiente il traffico degli utenti finali all'interno della rete globale Microsoft.

![Rete globale Microsoft](../media/networking-dns-resolution-same-location/microsoft-global-network.png)

Per prestazioni ottimali, i client locali devono accedere a una posizione di frontdoor più vicina a livello geografico, anziché inoltrare il traffico tramite un backbone di rete e al frontdoor più vicino alla connessione Internet centrale dell'organizzazione.

Ecco un esempio.

![Esempio di utilizzo della rete globale Microsoft](../media/networking-dns-resolution-same-location/microsoft-global-network-example.png)

Quando un utente della filiale di Parigi vuole accedere a un sito di SharePoint Online:

1. Invia una query DNS per risolvere un nome, ad esempio contoso.sharepoint.com. 
2. Il server DNS fornito dall'ISP inoltra tale query a un server DNS Microsoft.
3. I server DNS Microsoft abbinano l'indirizzo IP di origine della query DNS inoltrata all'area geografica assegnata all'indirizzo. Il server DNS Microsoft risponde con l'indirizzo IP del frontdoor della rete Microsoft più vicino in Europa.
4. Il server DNS ISP invia tale indirizzo IP all'utente.
5. L'utente avvia una connessione al server di SharePoint tramite il frontdoor europeo.

Per indirizzare una richiesta client al frontdoor più vicino a livello geografico, i server DNS di Microsoft usano le query DNS corrispondenti alla richiesta di connessione iniziale del client. Pertanto, per la latenza di rete inferiore:

- Tutte le sedi dell'organizzazione devvono avere connessioni Internet locali per il traffico di rete della categoria [Ottimizzazione](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#new-office-365-endpoint-categories).
- Ogni connessione Internet locale deve usare un server DNS locale per il traffico Internet in uscita da tale posizione.

Per ulteriori informazioni, vedere [Uscire dalle connessione di rete a livello locale](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#egress-network-connections-locally). 

Per testare la vicinanza a un punto di ingresso per la rete globale di Microsoft e quanto si è vicini al punto in cui la rete aziendale si collega all'ISP, usare lo [strumento di onboarding della rete di Office 365](https://connectivity.office.com/).

Come checkpoint provvisorio, è possibile vedere i [criteri uscita](networking-exit-criteria.md#crit-networking-step2) per questo passaggio.

## <a name="next-step"></a>Passaggio successivo

|||
|:-------|:-----|
|![Passaggio 3](../media/stepnumbers/Step3.png)|[Evitare fenomeni di "hairpinning" di rete](networking-avoid-network-hairpins.md)|
