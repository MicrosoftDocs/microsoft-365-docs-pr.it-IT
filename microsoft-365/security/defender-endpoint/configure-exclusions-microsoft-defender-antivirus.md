---
title: Configurare le esclusioni per le analisi di Microsoft Defender Antivirus
description: Puoi escludere i file (inclusi i file modificati da processi specificati) e le cartelle dall'analisi da Parte di Microsoft Defender Antivirus. Convalidare le esclusioni con PowerShell.
keywords: ''
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ksarens
manager: dansimp
ms.technology: mde
ms.audience: ITPro
ms.topic: how-to
ms.openlocfilehash: 7065aa7cd1975b2f5a38e79da8618ba3efdcdac5
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275121"
---
# <a name="configure-and-validate-exclusions-for-microsoft-defender-antivirus-scans"></a>Configurare e convalidare le esclusioni per le analisi di Microsoft Defender Antivirus

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**

- [Microsoft Defender per endpoint](/microsoft-365/security/defender-endpoint/)

Puoi escludere determinati file, cartelle, processi e file aperti dal processo dalle analisi di Microsoft Defender Antivirus. Tali esclusioni si applicano [](run-scan-microsoft-defender-antivirus.md)alle analisi [pianificate,](scheduled-catch-up-scans-microsoft-defender-antivirus.md)alle analisi su richiesta e alla protezione e al monitoraggio sempre in tempo [reale.](configure-real-time-protection-microsoft-defender-antivirus.md) Le esclusioni per i file aperti dal processo si applicano solo alla protezione in tempo reale.

## <a name="configure-and-validate-exclusions"></a>Configurare e convalidare le esclusioni

Per configurare e convalidare le esclusioni, vedere quanto segue:

- [Configurare e convalidare le esclusioni in base al nome file, all'estensione e al percorso della cartella.](configure-extension-file-exclusions-microsoft-defender-antivirus.md) Puoi escludere i file dalle analisi di Microsoft Defender Antivirus in base all'estensione, al nome file o al percorso.

- [Configurare e convalidare le esclusioni per i file aperti dai processi](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md). È possibile escludere i file dalle analisi aperte da un processo specifico.

## <a name="recommendations-for-defining-exclusions"></a>Suggerimenti per la definizione delle esclusioni

> [!IMPORTANT]
> Microsoft Defender Antivirus include molte esclusioni automatiche basate su comportamenti noti del sistema operativo e file di gestione tipici, ad esempio quelli utilizzati nella gestione aziendale, nella gestione dei database e in altri scenari e situazioni aziendali.  
> 
> La definizione delle esclusioni riduce la protezione offerta da Microsoft Defender Antivirus. È consigliabile valutare sempre i rischi associati all'implementazione delle esclusioni e escludere solo i file che si è certi non siano dannosi.

Quando si definiscono le esclusioni, tenere presente quanto segue:  

- Le esclusioni sono tecnicamente un gap di protezione. Considerare sempre le mitigazioni quando si definiscono le esclusioni. Altre misure di prevenzione possono essere semplici come assicurarsi che la posizione esclusa abbia gli elenchi di controllo di accesso (ACL) appropriati, i criteri di controllo, sia elaborato da un software aggiornato e così via.

- Esaminare periodicamente le esclusioni. Ricontrollare e applicare di nuovo le mitigazioni nell'ambito del processo di revisione.

- Idealmente, evitare di definire esclusioni che intendono essere proattive. Ad esempio, non escludere qualcosa solo perché si pensa che potrebbe essere un problema in futuro. Utilizzare le esclusioni solo per problemi specifici, ad esempio quelli relativi alle prestazioni o alla compatibilità delle applicazioni che le esclusioni potrebbero ridurre.

- Controllare le modifiche all'elenco di esclusione. L'amministratore della sicurezza deve conservare un contesto sufficiente per il motivo per cui è stata aggiunta una determinata esclusione. Dovresti essere in grado di rispondere con un ragionamento specifico sul motivo per cui un determinato percorso è stato escluso.

## <a name="related-articles"></a>Articoli correlati

- [Esclusioni di Microsoft Defender Antivirus in Windows Server 2016](configure-server-exclusions-microsoft-defender-antivirus.md)
- [Errori comuni da evitare quando si definiscono le esclusioni](common-exclusion-mistakes-microsoft-defender-antivirus.md)
