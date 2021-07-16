---
title: Microsoft 365 Ottica di connettività
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- BCS160
ms.assetid: f5ee6c33-bcd7-4b0b-b0f8-dc1d9fb8d132
description: In questo articolo sono contenute informazioni Microsoft 365 ottica di connettività.
ms.openlocfilehash: 952990a63d4ad064b2027c6f2364e8082342fa34
ms.sourcegitcommit: 2abc6bf9939b14a427647e88f319dbb70de49ca6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/16/2021
ms.locfileid: "53455978"
---
# <a name="microsoft-365-connectivity-optics"></a>Microsoft 365 Ottica di connettività

Questo documento descrive alcune delle ottiche di connettività che Microsoft raccoglie in genere dai dispositivi dei clienti e descrive alcuni dei modi in cui Microsoft usa tali dati per analizzare e ottimizzare la distribuzione dei servizi e per valutare e garantire la migliore esperienza utente finale possibile.

Le ottiche di connettività vengono in genere raccolte da applicazioni Microsoft, che possono essere installate nei dispositivi degli utenti finali o accessibili da browser. A differenza della raccolta dei dati facoltativa all'interno dei servizi Microsoft 365, molte delle ottiche di connettività descritte qui sono parte integrante per garantire che Microsoft soddisfi il nostro impegno in termini di disponibilità e prestazioni per i clienti. Queste ottiche consentono a Microsoft di rilevare e rispondere rapidamente a eventuali problemi nel percorso di connettività tra gli utenti finali e gli endpoint del servizio Microsoft. Alcune di queste ottiche vengono usate anche per abilitare funzionalità come Connettività di [rete nel Amministrazione Microsoft 365 Center.](office-365-network-mac-perf-overview.md)

## <a name="optics-collected-from-microsoft-365-applications"></a>Ottica raccolta da Microsoft 365 applicazioni

L'ottica viene attualmente raccolta usando il campionamento poco frequenti in tutti i dispositivi. In generale, il set specifico di ottica e destinazioni (endpoint di servizio) che devono essere misurati in una particolare iterazione vengono configurati da Microsoft in base ai requisiti di servizio e randomizzati per scopi di campionamento.
A ogni intervallo di raccolta dell'ottica, è possibile raccogliere una o più delle misurazioni seguenti utilizzando il dispositivo dell'utente finale come origine di misura e un endpoint del servizio Microsoft 365 come destinazione di misurazione:

| Misurazione | Descrizione |
| --- | --- |
| Latenza | Tempo impiegato per recuperare un file di piccole dimensioni tramite HTTP |
| Velocità effettiva | Tempo impiegato per recuperare un file di dimensioni maggiori tramite HTTP, misurato raramente per evitare un consumo eccessivo di larghezza di banda |
| Tempo di andata e ritorno (RTT) | Ping ICMP |
| Traceroute | Traceroute ICMP |

Ogni misura è in genere associata a informazioni aggiuntive, che possono includere gli elementi seguenti:

| Elemento | Descrizione |
| --- | --- |
| Tenant ID | Identificatore univoco per il tenant Azure Active Directory del cliente associato al dispositivo dell'utente finale. |
| ID monitoraggio | Identificatore dell'applicazione che genera la richiesta ,ad esempio Outlook, OneDrive e così via), fornita dall'applicazione client che esegue la misurazione. |
| ID richiesta | Identificatore della richiesta di misurazione, specificata nella configurazione di misurazione fornita da Microsoft. |
| IP remoto | IP di origine mascherato associato alla richiesta dal client all'endpoint del servizio, fornito dal server che ha ricevuto la richiesta di misurazione e calcolato in base all'indirizzo IP di origine del client visibile a Microsoft. Gli indirizzi IP sono mascherati a una subnet /24 per gli indirizzi IPv4 o a una subnet /48 per gli indirizzi IPv6 per garantire che Microsoft non possa identificare singoli dispositivi o utenti. |
| Front-end | Microsoft 365 identificatore front-end del servizio, fornito dal server che ha ricevuto la richiesta di misurazione. |
| Endpoint | Microsoft 365 endpoint del servizio, fornito dal server che ha ricevuto la richiesta di misurazione. |
| Certificato emesso da | Proprietà "certificato rilasciato da" del certificato SSL presentato durante la connessione all'endpoint del servizio, che indica l'autorità di certificazione che ha emesso il certificato all'endpoint del servizio. |
| Identificazione personale certificato | La proprietà "identificazione personale del certificato" del certificato SSL presentata durante la connessione all'endpoint del servizio, che è un identificatore univoco accessibile pubblicamente del certificato. |
| Latitudine/Longitudine | Latitudine e longitudine astratte del dispositivo dell'utente finale. Questo viene raccolto solo per i tenant che hanno abilitato il servizio di posizione di Windows nei dispositivi degli utenti finali e hanno abilitato anche la raccolta di queste informazioni nel portale di amministrazione di [Microsoft 365](office-365-network-mac-perf-overview.md#1-enable-windows-location-services). |

## <a name="measurement-process"></a>Processo di misurazione

Ogni dispositivo dell'utente finale in genere esegue una misurazione su base pianificata (per le applicazioni installate) o in base all'azione di caricamento delle pagine del browser (per le applicazioni basate sul Web). Le attività di misurazione vengono eseguite come operazioni in background e non influiscono sull'esperienza dell'applicazione per gli utenti. Poiché i tipi di misurazione e le destinazioni che verranno utilizzati per una particolare iterazione di questo processo vengono randomizzati, i clienti possono notare richieste agli endpoint di servizio Microsoft nella loro area geografica simili alle richieste tipiche effettuate dai dispositivi degli utenti finali per la normale connettività delle applicazioni. Inoltre, i clienti possono notare le richieste agli endpoint di servizio Microsoft ben al di fuori dell'area geografica locale. Queste misurazioni vengono spesso utilizzate per garantire un routing ottimale delle richieste dei clienti all'endpoint del servizio migliore, poiché le modifiche apportate all'infrastruttura di clienti e ISP potrebbero richiedere a Microsoft di modificare i criteri di instradamento delle richieste su base continuativa. Per ulteriori informazioni su come Microsoft instrada il traffico all'endpoint del servizio migliore e su come ottimizzare la connettività ai servizi di Microsoft 365, vedere panoramica Microsoft 365 [connettività di rete.](microsoft-365-networking-overview.md)

## <a name="service-endpoints"></a>Endpoint di servizio

Gli endpoint del servizio Microsoft utilizzati come destinazioni per queste misurazioni sono contenuti negli URL Office 365 e negli intervalli [di indirizzi IP pubblicati.](urls-and-ip-address-ranges.md) L'accesso ad altri endpoint di servizio non è necessario per la raccolta di queste ottiche di connettività.
