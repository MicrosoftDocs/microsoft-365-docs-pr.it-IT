---
title: Report di protezione dalle minacce in Microsoft Defender for Endpoint
description: Tenere traccia dei rilevamenti, delle categorie e della gravità degli avvisi tramite il report di protezione dalle minacce
keywords: rilevamento degli avvisi, origine, avviso per categoria, gravità degli avvisi, classificazione degli avvisi, determinazione
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: d32ab04f4acda60f65316719a4607c6c9bbd6447
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "51688982"
---
# <a name="threat-protection-report-in-microsoft-defender-for-endpoint"></a>Report di protezione dalle minacce in Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 

Il report sulla protezione dalle minacce fornisce informazioni di alto livello sugli avvisi generati nell'organizzazione. Il report include informazioni sulle tendenze che mostrano le origini di rilevamento, le categorie, le gravità, gli stati, le classificazioni e le determinazioni degli avvisi nel tempo.

Il dashboard è strutturato in due sezioni:

![Immagine del report sulla protezione dalle minacce](images/threat-protection-reports.png)

Sezione | Descrizione 
:---|:---
1 | Tendenze degli avvisi
2 | Riepilogo degli avvisi

## <a name="alert-trends"></a>Tendenze degli avvisi
Per impostazione predefinita, le tendenze degli avvisi visualizzano le informazioni sugli avvisi del periodo di 30 giorni che terminano con l'ultimo giorno completo. Per ottenere una prospettiva migliore sulle tendenze che si verificano nell'organizzazione, è possibile ottimizzare il periodo di reporting modificando il periodo di tempo visualizzato. Per regolare il periodo di tempo, selezionare un intervallo di tempo dalle opzioni a discesa:

- 30 giorni
- 3 mesi
- 6 mesi
- Personalizzato

>[!NOTE]
>Questi filtri vengono applicati solo nella sezione tendenze degli avvisi. Non influisce sulla sezione di riepilogo degli avvisi.


## <a name="alert-summary"></a>Riepilogo degli avvisi
Mentre le tendenze degli avvisi mostrano informazioni sugli avvisi di tendenza, il riepilogo dell'avviso mostra le informazioni sugli avvisi nell'ambito del giorno corrente.

 Il riepilogo degli avvisi consente di eseguire il drill-down in una particolare coda di avvisi a cui è applicato il filtro corrispondente. Ad esempio, facendo clic sulla barra EDR nella scheda Origini di rilevamento verrà visualizzata la coda degli avvisi con i risultati che mostrano solo gli avvisi generati dai rilevamenti EDR. 

>[!NOTE]
>L'ambito dei dati visualizzati nella sezione di riepilogo è 180 giorni prima della data corrente. Ad esempio, se la data odierna è il 5 novembre 2019, i dati nella sezione di riepilogo rifletteranno i numeri a partire dal 5 maggio 2019 al 5 novembre 2019.<br>
> Il filtro applicato alla sezione tendenze non viene applicato alla sezione di riepilogo. 

## <a name="alert-attributes"></a>Attributi degli avvisi
Il report è costituito da schede che visualizzano gli attributi di avviso seguenti:

- **Origini di** rilevamento: mostra informazioni sui sensori e sulle tecnologie di rilevamento che forniscono i dati utilizzati da Microsoft Defender for Endpoint per attivare gli avvisi.

- **Categorie di minacce**: mostra i tipi di attività di minaccia o di attacco che hanno attivato gli avvisi, indicando le possibili aree di interesse per le operazioni di sicurezza.

- **Gravità**: mostra il livello di gravità degli avvisi, che indica l'impatto potenziale collettivo delle minacce per l'organizzazione e il livello di risposta necessario per affrontarli.

- **Status**: mostra lo stato di risoluzione degli avvisi, che indica l'efficienza delle risposte agli avvisi manuali e della correzione automatica (se abilitata). 

- **Classificazione & determinazione**: mostra come sono stati classificati gli avvisi in base alla risoluzione, se sono stati classificati come minacce effettive (avvisi reali) o come rilevamenti non corretti (falsi avvisi). Queste schede mostrano anche la determinazione degli avvisi risolti, fornendo informazioni aggiuntive come i tipi di minacce effettive trovate o le attività legittime rilevate in modo errato.


 

## <a name="filter-data"></a>Filtrare i dati

Utilizzare i filtri forniti per includere o escludere avvisi con determinati attributi.

>[!NOTE]
>Questi filtri si **applicano a** tutte le schede del report.

Ad esempio, per visualizzare solo i dati relativi agli avvisi di gravità elevata:

1. In **Filtri > Gravità** selezionare **Alta**
2. Assicurati che tutte le altre opzioni in **Gravità** siano deselezionate.
3. Selezionare **Applica**. 

## <a name="related-topic"></a>Argomento correlato
- [Report integrità e conformità dei dispositivi](machine-reports.md)
