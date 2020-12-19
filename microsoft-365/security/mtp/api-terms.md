---
title: Licenza e condizioni di utilizzo di Microsoft 365 Defender APIs
description: Descrizione della licenza e condizioni di utilizzo per le API in Microsoft 365 Defender
keywords: API, API, licenze, termini, API, legale, notifiche, codice di condotta
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: d9b3c48e4b9e89ef7648086b05c9fdd9f078f51e
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719299"
---
# <a name="microsoft-365-defender-apis-license-and-terms-of-use"></a>Licenza e condizioni di utilizzo di Microsoft 365 Defender APIs

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Si applica a:**

- Microsoft 365 Defender

> [!IMPORTANT]
> Alcune informazioni si riferiscono al prodotto prerilasciato che può essere modificato in modo sostanziale prima che venga rilasciato commercialmente. Microsoft makes no warranties, express or implied, with respect to the information provided here.

## <a name="official-terms"></a>Termini ufficiali

Le API Microsoft 365 Defender sono regolate dalla [licenza e dalle condizioni di utilizzo di Microsoft Apis](https://docs.microsoft.com/legal/microsoft-apis/terms-of-use).

## <a name="legal-notices"></a>Note legali

Microsoft e gli eventuali collaboratori conferiscono una licenza alla documentazione Microsoft e ad altri contenuti di [questo repository](https://github.com/MicrosoftDocs/microsoft-365-docs), sotto la licenza pubblica internazionale Creative Commons Attribution 4,0. Per ulteriori informazioni, vedere il file di [licenza](https://github.com/MicrosoftDocs/microsoft-365-docs/blob/public/LICENSE) .

Microsoft, Windows, Microsoft Azure e/o altri prodotti e servizi Microsoft a cui viene fatto riferimento nella documentazione possono essere marchi o marchi registrati di Microsoft negli Stati Uniti e/o negli altri paesi.

Le licenze per questo progetto non consentono di utilizzare i nomi, i loghi o i marchi di Microsoft. Le linee guida per i marchi Microsoft sono disponibili presso [Microsoft trademarks](https://go.microsoft.com/fwlink/?LinkID=254653).

Le informazioni sulla privacy sono reperibili alla [privacy in Microsoft](https://privacy.microsoft.com).

Microsoft e tutti i collaboratori predispongono tutti gli altri diritti, sia in base ai rispettivi diritti d'autore, brevetti o marchi, sia per implicazione, preclusione o altro.

## <a name="other-restrictions"></a>Altre limitazioni

L'API di ricerca avanzata ha alcune [limitazioni](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/run-advanced-query-api#limitations) sul numero di risultati restituiti e sui dati che possono essere sottoposti a query.

1. È possibile eseguire query solo sui dati degli ultimi 30 giorni.
1. I risultati includono un massimo di 100.000 righe.

### <a name="quotas-and-resource-allocation"></a>Quote e allocazione delle risorse

Le API di Microsoft 365 Defender presentano soglie di limitazione.

- **API Incidents**: fino a 50 chiamate al minuto o 1500 chiamate all'ora.
- **API di caccia avanzata**: fino a 15 chiamate al minuto, 10 minuti di tempo di esecuzione all'ora e 4 ore di tempo di esecuzione al giorno.

Il codice di stato della risposta HTTP che indica la limitazione è `429` .

Se la richiesta è stata sottoposta a limitazione, il corpo della risposta indicherà l'ora in cui è possibile iniziare a eseguire di nuovo le richieste.

## <a name="related-articles"></a>Articoli correlati

- [Panoramica delle API di Microsoft 365 Defender](api-overview.md)
- [API supportate di Microsoft 365 Defender](api-supported.md)
- [Accedere alle API di Microsoft 365 Defender](api-access.md)
