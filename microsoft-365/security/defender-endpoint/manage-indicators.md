---
title: Creare indicatori
ms.reviewer: ''
description: Creare indicatori per un hash di file, un indirizzo IP, url o domini che definiscono il rilevamento, la prevenzione e l'esclusione delle entità.
keywords: gestire, consentito, bloccato, bloccare, pulito, dannoso, hash file, indirizzo IP, URL, dominio
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
ms.openlocfilehash: fb87f36c5289d622df2615046c5bb2fd8fad9543
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842243"
---
# <a name="create-indicators"></a>Creare indicatori

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> [!TIP]
> Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

La corrispondenza degli indicatori di compromissione (IoC) è una funzionalità essenziale in ogni soluzione di protezione degli endpoint. Questa funzionalità offre a SecOps la possibilità di impostare un elenco di indicatori per il rilevamento e il blocco (prevenzione e risposta).

Creare indicatori che definiscono il rilevamento, la prevenzione e l'esclusione delle entità. Puoi definire l'azione da eseguire, nonché la durata per l'applicazione dell'azione e l'ambito del gruppo di dispositivi a cui applicarla.

Le origini attualmente supportate sono il motore di rilevamento cloud di Defender for Endpoint, il motore di analisi e correzione automatizzato e il motore di prevenzione degli endpoint (Antivirus Microsoft Defender).

**Motore di rilevamento cloud**<br>
Il motore di rilevamento cloud di Defender for Endpoint analizza regolarmente i dati raccolti e cerca di corrispondere agli indicatori impostati. In caso di corrispondenza, verrà eseguita un'azione in base alle impostazioni specificate per l'IoC.

**Motore di prevenzione degli endpoint**<br>
Lo stesso elenco di indicatori viene rispettato dall'agente di prevenzione. Ciò significa che se Microsoft Defender AV è l'av principale configurato, gli indicatori corrispondenti verranno trattati in base alle impostazioni. Ad esempio, se l'azione è "Avviso e blocco", Microsoft Defender AV impedirà le esecuzioni di file (blocco e correzione) e verrà generato un avviso corrispondente. D'altra parte, se l'azione è impostata su "Consenti", Microsoft Defender AV non rileva né blocca l'esecuzione del file.

**Motore di analisi e correzione automatizzato**<BR>
L'analisi e la correzione automatizzate si comportano allo stesso modo. Se un indicatore è impostato su "Consenti", l'analisi e la correzione automatizzate ignoreranno un verdetto "negativo". Se impostato su "Blocca", l'analisi e la correzione automatizzate lo tratteranno come "non corretti".

> [!NOTE]
> L'impostazione EnableFileHashComputation calcola l'hash del file per il certificato e il file IoC durante le analisi dei file. Supporta l'imposizione IoC di hash e certificati appartenenti ad applicazioni attendibili. Verrà abilitato e disabilitato contemporaneamente con l'impostazione Consenti o blocca file. EnableFileHashComputation viene abilitato manualmente tramite Criteri di gruppo ed è disabilitato per impostazione predefinita.


Le azioni attualmente supportate sono:
- Consenti
- Solo avviso
- Avviso e blocco


È possibile creare un indicatore per:
- [File](indicator-file.md)
- [Indirizzi IP, URL/domini](indicator-ip-domain.md)
- [Certificati](indicator-certificates.md)


> [!NOTE]
> Esiste un limite di 15.000 indicatori per tenant. Gli indicatori di file e certificati non [bloccano le esclusioni definite per Antivirus Microsoft Defender](/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus). Gli indicatori non sono supportati in Antivirus Microsoft Defender quando è in modalità passiva. 


## <a name="related-topics"></a>Argomenti correlati

- [Creare ioC contestuali](respond-file-alerts.md#add-indicator-to-block-or-allow-a-file)
- [Usare l'API Microsoft Defender for Endpoint indicators](ti-indicator.md)
- [Usare soluzioni integrate per i partner](partner-applications.md)
