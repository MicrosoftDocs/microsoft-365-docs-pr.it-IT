---
title: Informazioni sui concetti di intelligence per le minacce in Microsoft Defender for Endpoint
description: Creare avvisi di minacce personalizzati per l'organizzazione e apprendere i concetti relativi all'intelligence per le minacce in Microsoft Defender for Endpoint
keywords: threat intelligence, definizioni di avviso, indicatori di compromissione, ioc
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: bb82634c8c2ef11131a43e8e479bf88d5626ed03
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51066082"
---
# <a name="understand-threat-intelligence-concepts"></a>Informazioni sui concetti di Threat Intelligence

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)



>Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-threatindicator-abovefoldlink) 

Gli attacchi di cybersecurity avanzati includono più eventi dannosi complessi, attributi e informazioni contestuali. Identificare e decidere quale di queste attività può essere sospetta può essere un'attività complessa. La conoscenza degli attributi noti e delle attività anomale specifiche del settore è fondamentale per sapere quando chiamare un comportamento osservato come sospetto.

Con Microsoft Defender for Endpoint, puoi creare avvisi di minacce personalizzati che consentono di tenere traccia delle possibili attività di attacco nell'organizzazione. Puoi contrassegnare eventi sospetti per riunire indizi ed eventualmente arrestare una catena di attacchi. Questi avvisi personalizzati per le minacce verranno visualizzati solo nell'organizzazione e contrassegneranno gli eventi di cui è stata impostata la traccia.

Prima di creare avvisi di minacce personalizzati, è importante conoscere i concetti alla base delle definizioni di avviso e degli indicatori di compromissione (IOC) e della relazione tra di essi.

## <a name="alert-definitions"></a>Definizioni di avviso
Le definizioni di avviso sono attributi contestuali che possono essere usati collettivamente per identificare gli indizi iniziali su un possibile attacco di cybersecurity. Questi indicatori sono in genere una combinazione di attività, caratteristiche e azioni intraprese da un utente malintenzionato per raggiungere correttamente l'obiettivo di un attacco. Il monitoraggio di queste combinazioni di attributi è fondamentale per ottenere un punto di vista contro gli attacchi ed eventualmente interferire con la catena di eventi prima che venga raggiunto l'obiettivo di un utente malintenzionato.

## <a name="indicators-of-compromise-ioc"></a>Indicatori di compromissione (IOC)
Le operazioni di I/O sono eventi dannosi noti singolarmente che indicano che una rete o un dispositivo è già stato violato. A differenza delle definizioni di avviso, questi indicatori sono considerati come prova di una violazione. Vengono spesso visti dopo che un attacco è già stato eseguito e l'obiettivo è stato raggiunto, ad esempio l'esfiltrazione. Tenere traccia delle operazioni di I/O è importante anche durante le indagini forensi. Anche se potrebbe non offrire la possibilità di intervenire con una catena di attacchi, la raccolta di questi indicatori può essere utile per creare difese migliori per possibili attacchi futuri.

## <a name="relationship-between-alert-definitions-and-iocs"></a>Relazione tra definizioni di avviso e I/O
Nel contesto di Microsoft Defender per Endpoint, le definizioni di avviso sono contenitori per le operazioni di I/O e definiscono l'avviso, inclusi i metadati generati in caso di corrispondenza IOC specifica. Nell'ambito delle definizioni di avviso vengono forniti diversi metadati. I metadati, ad esempio il nome della definizione dell'avviso di attacco, gravità e descrizione, vengono forniti insieme ad altre opzioni.

Ogni IOC definisce la logica di rilevamento concreto in base al tipo e al valore, nonché alla relativa azione, che determina la modalità di corrispondenza. È associato a una definizione di avviso specifica che definisce la modalità di visualizzazione di un rilevamento come avviso nella console di Microsoft Defender for Endpoint.

Ecco un esempio di IOC:
- Tipo: Sha1
- Valore: 92cfceb39d57d914ed8b14d0e37643de0797ae56
- Azione: Uguale a

Le operazioni di I/O hanno una relazione molti-a-uno con le definizioni di avviso in modo che una definizione di avviso possa avere molte operazioni di I/O corrispondenti.

## <a name="in-this-section"></a>Contenuto della sezione

Argomento | Descrizione
:---|:---
[Eseguire il pull dei rilevamenti agli strumenti SIEM](configure-siem.md)| Informazioni sui diversi modi per eseguire il pull dei rilevamenti.
[Abilitare l'integrazione SIEM in Microsoft Defender for Endpoint](enable-siem-integration.md)| Informazioni sull'abilitazione della funzionalità  di integrazione SIEM nella pagina Impostazioni del portale in modo da poter utilizzare e generare le informazioni necessarie per configurare gli strumenti SIEM supportati.
[Configurare Splunk per eseguire il pull di Microsoft Defender per i rilevamenti degli endpoint](configure-siem.md)| Scopri come installare l'app di input modulare dell'API REST e altre impostazioni di configurazione per consentire a Splunk di eseguire il pull di Microsoft Defender per i rilevamenti degli endpoint.
[Configurare HP ArcSight per eseguire il pull dei rilevamenti di Microsoft Defender for Endpoint](configure-arcsight.md)| Informazioni sull'installazione del pacchetto HP ArcSight REST FlexConnector e sui file necessari per configurare ArcSight per eseguire il pull di Microsoft Defender per i rilevamenti degli endpoint.
[Campi di Microsoft Defender per il rilevamento degli endpoint](api-portal-mapping.md) | Comprendere quali campi dati vengono esposti come parte dell'API degli avvisi e come vengono mappati Microsoft Defender Security Center.
[Eseguire il pull dei rilevamenti di Microsoft Defender per endpoint con l'API REST](pull-alerts-using-rest-api.md) | Usa il flusso OAuth 2.0 delle credenziali client per estrarre i rilevamenti da Microsoft Defender for Endpoint usando l'API REST.
[Risolvere i problemi di integrazione degli strumenti SIEM](troubleshoot-siem.md) | Risolvere i problemi che possono verificarsi quando si utilizza la funzionalità di integrazione SIEM.



## <a name="related-topics"></a>Argomenti correlati
- [Gestire indicatori](manage-indicators.md)
