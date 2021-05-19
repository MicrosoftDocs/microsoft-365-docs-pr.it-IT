---
title: Ridurre le vulnerabilità zero-day - gestione di minacce e vulnerabilità
description: Informazioni su come individuare e ridurre le vulnerabilità zero-day nell'ambiente tramite gestione di minacce e vulnerabilità.
keywords: Microsoft Defender for Endpoint tvm zero day vulnerabilities, tvm, threat & gestione delle vulnerabilità, zero day, 0-day, mitigate 0 day vulnerabilities, vulnerable CVE
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 2c746a74899a34827e089f4c9c2f6ecc396bb69c
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538772"
---
# <a name="mitigate-zero-day-vulnerabilities---threat-and-vulnerability-management"></a>Ridurre le vulnerabilità zero-day - gestione di minacce e vulnerabilità

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**

- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Minaccia e gestione delle vulnerabilità](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

Una vulnerabilità zero-day è una vulnerabilità divulgata pubblicamente per la quale non sono state rilasciate patch ufficiali o aggiornamenti della sicurezza. Le vulnerabilità zero-day spesso hanno livelli di gravità elevati e vengono attivamente sfruttate.

Minacce e gestione delle vulnerabilità verranno visualizzate solo vulnerabilità zero-day su cui sono disponibili informazioni.

## <a name="find-information-about-zero-day-vulnerabilities"></a>Informazioni sulle vulnerabilità zero-day

Una volta trovata una vulnerabilità zero-day, le informazioni su di essa verranno trasmesse tramite le esperienze seguenti nel Microsoft Defender Security Center.

>[!NOTE]
> La funzionalità di 0 giorni non è attualmente disponibile per i prodotti non Windows (Mac, Linux); verrà tuttavia aggiunto in futuro.

### <a name="threat-and-vulnerability-management-dashboard"></a>Dashboard delle minacce gestione delle vulnerabilità sicurezza

Cerca i suggerimenti con un tag zero-day nella scheda "Suggerimenti per la sicurezza principali".

![Suggerimenti principali con tag zero-day.](images/tvm-zero-day-top-security-recommendations.png)

Trova il software principale con il tag zero-day nella scheda "Software più vulnerabile".

![Software più vulnerabile con tag zero-day.](images/tvm-zero-day-top-software.png)

### <a name="weaknesses-page"></a>Pagina Punti deboli

Cercare la vulnerabilità denominata zero-day insieme a una descrizione e dettagli.

- Se a questa vulnerabilità è assegnato un ID CVE, verrà visualizzata l'etichetta zero-day accanto al nome CVE.

- Se a questa vulnerabilità non è assegnato un CVE-ID, si troverà sotto un nome temporaneo interno simile a "TVM-XXXX-XXXX". Il nome verrà aggiornato dopo l'assegnazione di un CVE-ID ufficiale, ma il nome interno precedente sarà comunque disponibile per la ricerca e verrà trovato nel pannello laterale.

![Esempio di zero giorni per CVE-2020-17087 nella pagina dei punti deboli.](images/tvm-zero-day-weakness-name.png)

### <a name="software-inventory-page"></a>Pagina Inventario software

Cercare software con il tag zero-day. Filtrare in base al tag "zero day" per visualizzare solo il software con vulnerabilità zero-day.

![Esempio zero giorno di Windows Server 2016 nella pagina dell'inventario software.](images/tvm-zero-day-software-inventory.png)

### <a name="software-page"></a>Pagina Software

Cercare un tag zero-day per ogni software interessato dalla vulnerabilità zero-day.

![Esempio di zero giorni per Windows Server 2016 software.](images/tvm-zero-day-software-page.png)

### <a name="security-recommendations-page"></a>Pagina Suggerimenti per la sicurezza

Visualizzare suggerimenti chiari sulle opzioni di correzione e mitigazione, incluse le soluzioni alternative, se esistenti. Filtrare in base al tag "zero day" per visualizzare solo i suggerimenti per la sicurezza che affrontano le vulnerabilità zero-day.

Se è presente un software con una vulnerabilità zero-day e vulnerabilità aggiuntive da risolvere, si otterrà un consiglio su tutte le vulnerabilità.

![Zero day example of Windows Server 2016 nella pagina degli elementi consigliati per la sicurezza.](images/tvm-zero-day-security-recommendation.png)

## <a name="addressing-zero-day-vulnerabilities"></a>Affrontare le vulnerabilità zero-day

Vai alla pagina dei suggerimenti per la sicurezza e seleziona un suggerimento con zero-day. Verrà aperto un riquadro a comparsa con informazioni sulla zero-day e altre vulnerabilità per tale software.

Se disponibili, sarà disponibile un collegamento alle opzioni di mitigazione e alle soluzioni alternative. Le soluzioni alternative possono contribuire a ridurre il rischio rappresentato da questa vulnerabilità zero-day fino a quando non è possibile distribuire una patch o un aggiornamento della sicurezza.

Apri le opzioni di correzione e scegli il tipo di attenzione. È consigliabile un'opzione di correzione "attenzione necessaria" per le vulnerabilità zero-day, poiché un aggiornamento non è stato ancora rilasciato. Non sarà possibile selezionare una data di scadenza, poiché non è disponibile alcuna azione specifica da eseguire. Se sono presenti vulnerabilità meno recenti per questo software che si desidera correggere, è possibile ignorare l'opzione di correzione "attenzione necessaria" e scegliere "aggiorna".

![Esempio di riquadro a comparsa zero Windows Server 2016 nella pagina dei suggerimenti per la sicurezza.](images/tvm-zero-day-recommendation-flyout400.png)

## <a name="track-zero-day-remediation-activities"></a>Tenere traccia delle attività di correzione zero-day

Passare alla pagina gestione di minacce e vulnerabilità [correzione per](tvm-remediation.md) visualizzare l'elemento attività di correzione. Se hai scelto l'opzione di correzione "attenzione necessaria", non ci saranno barre di avanzamento, stato del ticket o data di scadenza poiché non è possibile monitorare alcuna azione effettiva. È possibile filtrare in base al tipo di correzione, ad esempio "aggiornamento software" o "attenzione necessaria", per visualizzare tutti gli elementi attività nella stessa categoria.

## <a name="patching-zero-day-vulnerabilities"></a>Applicazione di patch alle vulnerabilità zero-day

Quando viene rilasciata una patch per il giorno zero, il suggerimento verrà modificato in "Aggiornamento" e accanto a essa verrà visualizzato un'etichetta blu che indica "Nuovo aggiornamento della sicurezza per zero giorno". Non verrà più utilizzato come zero-day, il tag zero-day verrà rimosso da tutte le pagine.

![Suggerimento per "Aggiornare Microsoft Windows 10" con la nuova etichetta di patch.](images/tvm-zero-day-patch.jpg)

## <a name="related-articles"></a>Articoli correlati

- [Panoramica delle minacce gestione delle vulnerabilità sicurezza](next-gen-threat-and-vuln-mgt.md)
- [Dashboard](tvm-dashboard-insights.md)
- [Consigli sulla sicurezza](tvm-security-recommendation.md)
- [Inventario software](tvm-software-inventory.md)
- [Vulnerabilità nell'organizzazione](tvm-weaknesses.md)
