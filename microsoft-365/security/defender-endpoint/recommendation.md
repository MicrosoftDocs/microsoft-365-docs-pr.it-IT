---
title: Proprietà e metodi consigliati
description: Recupera gli avvisi recenti principali.
keywords: api, api del grafico, api supportate, ottenere, avvisi, recenti
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 6ab4d4e1acab0e4b837195f64c369057d7ceb417
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51198234"
---
# <a name="recommendation-resource-type"></a>Tipo di risorsa consigliata

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:** [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

> Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


[!include[Prerelease information](../../includes/prerelease.md)]

## <a name="methods"></a>Metodi
Metodo |Tipo restituito |Descrizione
:---|:---|:---
[Elencare tutti i suggerimenti](get-all-recommendations.md) | Raccolta elementi consigliati | Recupera un elenco di tutti i suggerimenti per la sicurezza che interessano l'organizzazione
[Ottenere suggerimenti tramite ID](get-recommendation-by-id.md) | Consiglio | Recupera un suggerimento di sicurezza in base al relativo ID
[Ottenere il software consigliato](get-recommendation-software.md)| [Software](software.md) | Recupera un suggerimento di sicurezza relativo a un software specifico
[Ottenere dispositivi consigliati](get-recommendation-machines.md)|Insieme MachineRef | Recupera un elenco di dispositivi associati al suggerimento per la sicurezza
[Ottenere vulnerabilità dei suggerimenti](get-recommendation-vulnerabilities.md) | [Raccolta di vulnerabilità](vulnerability.md) | Recupera un elenco di vulnerabilità associate al suggerimento per la sicurezza


## <a name="properties"></a>Proprietà
Proprietà |   Tipo   |   Descrizione
:---|:---|:---
id | Stringa | ID suggerimento
productName | Stringa | Nome software correlato  
recommendationName | Stringa | Nome suggerimento
Punti deboli | Long | Numero di vulnerabilità individuate
Fornitore | Stringa | Nome fornitore correlato
recommendedVersion | Stringa | Versione consigliata
recommendationCategory | Stringa | Categoria di raccomandazione. I valori possibili sono: "Accounts", "Application", "Network", "OS", "SecurityStack
subCategory | Stringa | Sottocatego tipo di raccomandazione
severityScore | Double | Potenziale impatto della configurazione sul punteggio Microsoft Secure Score per i dispositivi dell'organizzazione (1-10)
publicExploit | Booleano | Exploit pubblico disponibile 
activeAlert | Booleano | L'avviso attivo è associato a questo suggerimento
associatedThreats | Insieme String | Il report analisi delle minacce è associato a questo suggerimento
remediationType | Stringa | Tipo di correzione. I valori possibili sono: "ConfigurationChange","Update","Upgrade","Uninstall"
Stato | Enum | Stato dell'eccezione consigliata. I valori possibili sono: "Active" e "Exception"
configScoreImpact | Double | Impatto di Microsoft Secure Score per i dispositivi
exposureImpacte | Double | Impatto del punteggio di esposizione
totalMachineCount | Long | Numero di dispositivi installati
exposedMachinesCount | Long | Numero di dispositivi installati esposti a vulnerabilità
nonProductivityImpactedAssets | Long | Numero di dispositivi non interessati  
relatedComponent | Stringa |  Componente software correlato
