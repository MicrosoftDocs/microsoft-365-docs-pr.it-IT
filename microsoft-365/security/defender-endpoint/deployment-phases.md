---
title: Fasi di distribuzione
description: Scopri come distribuire Microsoft Defender for Endpoint preparando, configurando e onboarding gli endpoint a tale servizio
keywords: distribuire, preparare, configurare, onboarding, fase, distribuzione, distribuzione, adozione, configurazione
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-endpointprotect
- m365solution-overview
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 3f0527192a55d67df7e23507bed46df446f8b2b7
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165166"
---
# <a name="deployment-phases"></a>Fasi di distribuzione

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender ATP](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

Scopri come distribuire Microsoft Defender for Endpoint in modo che l'azienda possa sfruttare la protezione preventiva, il rilevamento post-violazione, l'indagine automatizzata e la risposta. 


Questa guida consente di lavorare tra le parti interessate per preparare l'ambiente e quindi eseguire l'onboardboard dei dispositivi in modo metodico, passando dalla valutazione a un progetto pilota significativo, alla distribuzione completa.

Ogni sezione corrisponde a un articolo separato in questa soluzione.

![Immagine delle fasi di distribuzione con dettagli dalla tabella](images/deployment-guide-phases.png)


![Riepilogo delle fasi di distribuzione: preparazione, installazione, onboard](images/phase-diagrams/deployment-phases.png)

|Fase | Descrizione | 
|:-------|:-----|
| [Fase 1: preparare](prepare-deployment.md)| Informazioni su cosa è necessario considerare quando si distribuisce Defender per Endpoint, ad esempio le approvazioni delle parti interessate, le considerazioni sull'ambiente, le autorizzazioni di accesso e l'ordine di adozione delle funzionalità. 
| [Fase 2: installazione](production-deployment.md)|  Ottieni indicazioni sui passaggi iniziali da eseguire per accedere al portale, ad esempio la convalida delle licenze, il completamento dell'installazione guidata e la configurazione di rete. 
| [Fase 3: onboard](onboarding.md) | Scopri come usare gli anelli di distribuzione, gli strumenti di onboarding supportati in base al tipo di endpoint e la configurazione delle funzionalità disponibili. 


Dopo aver completato questa guida, verrà impostata con le autorizzazioni di accesso appropriate, gli endpoint verranno onboarding e verranno segnalati i dati dei sensori al servizio e saranno disponibili funzionalità quali la protezione di nuova generazione e la riduzione della superficie di attacco.



Indipendentemente dall'architettura dell'ambiente e dal metodo di distribuzione scelto in Plan [deployment](deployment-strategy.md) guidance, questa guida ti supporterà negli endpoint di onboarding. 








## <a name="key-capabilities"></a>Caratteristiche chiave

Mentre Microsoft Defender for Endpoint offre molte funzionalità, lo scopo principale di questa guida alla distribuzione è iniziare a usare i dispositivi di onboarding. Oltre all'onboarding, questa guida ti consente di iniziare con le funzionalità seguenti.



Funzionalità | Descrizione 
:---|:---
Rilevamento endpoint e risposta | Vengono messe in atto funzionalità di rilevamento e risposta degli endpoint per rilevare, analizzare e rispondere ai tentativi di intrusione e alle violazioni attive.
Protezione di nuova generazione | Per rafforzare ulteriormente il perimetro di sicurezza della rete, Microsoft Defender for Endpoint usa una protezione di nuova generazione progettata per rilevare tutti i tipi di minacce emergenti.
Riduzione della superficie d'attacco |  Fornire la prima linea di difesa nello stack. Assicurandosi che le impostazioni di configurazione siano impostate correttamente e che le tecniche di mitigazione degli exploit siano applicate, questo set di funzionalità resiste agli attacchi e allo sfruttamento.

Tutte queste funzionalità sono disponibili per i titolari della licenza di Microsoft Defender per Endpoint. Per ulteriori informazioni, vedere [Requisiti di licenza.](minimum-requirements.md#licensing-requirements)

## <a name="scope"></a>Scope

### <a name="in-scope"></a>Nell'ambito

-   Utilizzo di Microsoft Endpoint Manager e Microsoft Endpoint Manager per eseguire l'onboarding degli endpoint nel servizio e configurare le funzionalità

-   Abilitazione delle funzionalità di defender per il rilevamento e la risposta degli endpoint (EDR)

-   Abilitazione delle funzionalità di Defender per Endpoint Endpoint Protection Platform (EPP)

    -   Protezione di nuova generazione

    -   Riduzione della superficie d'attacco


### <a name="out-of-scope"></a>Esclusioni

Gli elementi seguenti non sono nell'ambito di questa guida alla distribuzione:

-   Configurazione di soluzioni di terze parti che potrebbero integrarsi con Defender for Endpoint

-   Test di penetrazione nell'ambiente di produzione




## <a name="see-also"></a>Vedere anche
- [Fase 1: preparare](prepare-deployment.md)
- [Fase 2: configurazione](production-deployment.md)
- [Fase 3: onboard](onboarding.md)
- [Pianificare la distribuzione](deployment-strategy.md)