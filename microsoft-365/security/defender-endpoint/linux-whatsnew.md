---
title: Novità di Microsoft Defender per Endpoint per Linux
description: Elenco delle modifiche principali per Microsoft Defender ATP per Linux.
keywords: microsoft, defender, atp, linux, whatsnew, release
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: security
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 02a446f47ce4292b214c868e773802c53f7e3353
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2021
ms.locfileid: "51581003"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-for-linux"></a>Novità di Microsoft Defender per Endpoint per Linux

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

## <a name="1012563-30121022125630"></a>101.25.63 (30.121022.12563.0)

- Miglioramenti delle prestazioni & correzioni di bug

## <a name="1012364-30121021123640"></a>101.23.64 (30.121021.12364.0)

- Miglioramento delle prestazioni per la situazione in cui un intero punto di montaggio viene aggiunto all'elenco di esclusione antivirus. Prima di questa versione, l'attività dei file originata dal punto di montaggio era ancora elaborata dal prodotto. A partire da questa versione, l'attività dei file per i punti di montaggio esclusi viene eliminata, con un miglioramento delle prestazioni del prodotto
- È stata aggiunta una nuova opzione per lo strumento da riga di comando per visualizzare informazioni sull'ultima analisi su richiesta. Per visualizzare le informazioni sull'ultima analisi su richiesta, eseguire `mdatp health --details antivirus`
- Altri miglioramenti delle prestazioni & correzioni di bug

## <a name="1011853"></a>101.18.53

- EDR per Linux è [ora disponibile in genere](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)
- È stata aggiunta una nuova opzione della riga di comando ( `--ignore-exclusions` ) per ignorare le esclusioni av durante le analisi personalizzate ( `mdatp scan custom` )
- Esteso con un nuovo parametro ( ) che consente di salvare i `mdatp diagnostic create` log di diagnostica in una directory `--path [directory]` diversa
- Miglioramenti delle prestazioni & correzioni di bug

## <a name="1011299"></a>101.12.99

- Miglioramenti delle prestazioni & correzioni di bug

## <a name="1010476"></a>101.04.76

- Correzioni di bug

## <a name="1010348"></a>101.03.48

- Correzioni di bug

## <a name="1010255"></a>101.02.55

- È stato risolto un problema per cui il prodotto a volte non inizia dopo un riavvio/aggiornamento
- È stato risolto un problema per cui le impostazioni proxy non vengono salvate in modo permanente tra gli aggiornamenti del prodotto

## <a name="1010075"></a>101.00.75

- È stato aggiunto il supporto per i tipi di file system seguenti: `ecryptfs` , , , , , , , `fuse` , `fuseblk` `jfs` `nfs` `overlay` `ramfs` `reiserfs` `udf` e `vfat`
- Nuova sintassi per lo [strumento da riga di comando](linux-resources.md#configure-from-the-command-line).
- Miglioramenti delle prestazioni & correzioni di bug

## <a name="1009070"></a>100.90.70

> [!WARNING]
> Quando si aggiorna il pacchetto installato da una versione del prodotto precedente a 100.90.70, l'aggiornamento potrebbe non riuscire nelle distribuzioni basate su Red Hat e SLES. Ciò è dovuto a una modifica importante in un percorso di file. Una soluzione temporanea consiste nel rimuovere il pacchetto precedente e quindi installare quello più recente. Questo problema non esiste nelle versioni più recenti.

- Le [esclusioni antivirus ora supportano i caratteri jolly](linux-exclusions.md#supported-exclusion-types)
- Aggiunta della possibilità di [risolvere i problemi di prestazioni](linux-support-perf.md) tramite lo strumento da riga di `mdatp` comando
- Miglioramenti per rendere più affidabile l'installazione del pacchetto
- Miglioramenti delle prestazioni & correzioni di bug
