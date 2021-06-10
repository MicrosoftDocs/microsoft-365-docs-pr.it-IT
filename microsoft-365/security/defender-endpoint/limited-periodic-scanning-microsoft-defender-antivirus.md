---
title: Abilitare la funzionalità di analisi Antivirus Microsoft Defender periodico limitata
description: L'analisi periodica limitata consente di Antivirus Microsoft Defender oltre agli altri provider AV installati
keywords: lps, limited, periodic, scan, scanning, compatibility, 3rd party, other av, disable
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: b2ae56c0f67501eb8603d5d28c4ed0c4af01a8c9
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274596"
---
# <a name="use-limited-periodic-scanning-in-microsoft-defender-antivirus"></a>Usare analisi periodiche limitate in Microsoft Defender Antivirus

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**

- [Microsoft Defender per endpoint](/microsoft-365/security/defender-endpoint/)

L'analisi periodica limitata è un tipo speciale di rilevamento e correzione delle minacce che può essere abilitato quando è stato installato un altro prodotto antivirus in un Windows 10 dispositivo.

Può essere abilitato solo in determinate situazioni. Per ulteriori informazioni sull'analisi periodica limitata e sul Antivirus Microsoft Defender con altri prodotti antivirus, vedere [Antivirus Microsoft Defender compatibilità.](microsoft-defender-antivirus-compatibility.md)

**Microsoft non consiglia di utilizzare questa funzionalità in ambienti aziendali. Si tratta di una funzionalità destinata principalmente agli utenti.** Questa funzionalità usa solo un sottoinsieme limitato delle funzionalità Antivirus Microsoft Defender per rilevare malware e non sarà in grado di rilevare la maggior parte del malware e software potenzialmente indesiderato. Inoltre, le funzionalità di gestione e creazione di report saranno limitate. Microsoft consiglia alle aziende di scegliere la soluzione antivirus principale e usarla esclusivamente.

## <a name="how-to-enable-limited-periodic-scanning"></a>Come abilitare l'analisi periodica limitata

Per impostazione predefinita, Antivirus Microsoft Defender si abilita su un dispositivo Windows 10 se non è installato alcun altro prodotto antivirus o se l'altro prodotto non è aggiornato, è scaduto o non funziona correttamente.

Se Antivirus Microsoft Defender è abilitato, verranno visualizzate le opzioni consuete per configurarlo nel dispositivo:

![Sicurezza di Windows app che mostra le opzioni di Microsoft Defender AV, incluse le opzioni di analisi, le impostazioni e le opzioni di aggiornamento](images/vtp-wdav.png)

Se un altro prodotto antivirus è installato e funziona correttamente, Antivirus Microsoft Defender si disabiliterà. L Sicurezza di Windows app modificherà la sezione **Protezione** dalle minacce & virus per mostrare lo stato del prodotto AV e fornirà un collegamento alle opzioni di configurazione del prodotto.

Sotto qualsiasi prodotto AV di terze parti, un nuovo collegamento verrà visualizzato **come Antivirus Microsoft Defender opzioni**. Facendo clic su questo collegamento verrà visualizzato l'interruttore che consente una scansione periodica limitata. Si noti che l'opzione periodica limitata è un interruttore per abilitare o disabilitare l'analisi periodica. 

Facendo scorrere l'interruttore **su On** verranno mostrate le opzioni standard di Microsoft Defender AV sotto il prodotto AV di terze parti. L'opzione di scansione periodica limitata verrà visualizzata nella parte inferiore della pagina.

## <a name="related-articles"></a>Articoli correlati

- [Configurare la protezione comportamentale, euristica e in tempo reale](configure-protection-features-microsoft-defender-antivirus.md)
- [Antivirus Microsoft Defender in Windows 10](microsoft-defender-antivirus-in-windows-10.md)