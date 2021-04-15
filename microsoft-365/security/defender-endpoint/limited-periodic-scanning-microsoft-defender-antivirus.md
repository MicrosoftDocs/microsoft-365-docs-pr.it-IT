---
title: Abilitare la funzionalità di analisi periodica limitata di Microsoft Defender Antivirus
description: L'analisi periodica limitata ti consente di usare Microsoft Defender Antivirus oltre agli altri provider av installati
keywords: lps, limited, periodic, scan, scanning, compatibility, 3rd party, other av, disable
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 82c4bc1feec1556dc864558a843ed5e911c3ef3d
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764484"
---
# <a name="use-limited-periodic-scanning-in-microsoft-defender-antivirus"></a>Usare un'analisi periodica limitata in Microsoft Defender Antivirus

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**

- [Microsoft Defender per endpoint](/microsoft-365/security/defender-endpoint/)

L'analisi periodica limitata è un tipo speciale di rilevamento e correzione delle minacce che può essere abilitato quando hai installato un altro prodotto antivirus in un dispositivo Windows 10.

Può essere abilitato solo in determinate situazioni. Per ulteriori informazioni sull'analisi periodica limitata e sul funzionamento di Microsoft Defender Antivirus con altri prodotti antivirus, vedere [Compatibilità con Microsoft Defender Antivirus.](microsoft-defender-antivirus-compatibility.md)

**Microsoft non consiglia di utilizzare questa funzionalità in ambienti aziendali. Si tratta di una funzionalità destinata principalmente agli utenti.** Questa funzionalità usa solo un sottoinsieme limitato delle funzionalità di Microsoft Defender Antivirus per rilevare malware e non sarà in grado di rilevare la maggior parte del malware e del software potenzialmente indesiderato. Inoltre, le funzionalità di gestione e creazione di report saranno limitate. Microsoft consiglia alle aziende di scegliere la soluzione antivirus principale e usarla esclusivamente.

## <a name="how-to-enable-limited-periodic-scanning"></a>Come abilitare l'analisi periodica limitata

Per impostazione predefinita, Microsoft Defender Antivirus si abilita su un dispositivo Windows 10 se non è installato alcun altro prodotto antivirus o se l'altro prodotto non è aggiornato, è scaduto o non funziona correttamente.

Se Microsoft Defender Antivirus è abilitato, verranno visualizzate le opzioni consuete per configurarlo nel dispositivo:

![App Sicurezza di Windows che mostra le opzioni di Microsoft Defender AV, incluse le opzioni di analisi, le impostazioni e le opzioni di aggiornamento](images/vtp-wdav.png)

Se un altro prodotto antivirus è installato e funziona correttamente, Microsoft Defender Antivirus si disabiliterà. L'app Sicurezza di Windows modificherà la sezione Protezione da **virus &** le minacce per mostrare lo stato del prodotto AV e fornirà un collegamento alle opzioni di configurazione del prodotto.

Sotto qualsiasi prodotto AV di terze parti, un nuovo collegamento verrà visualizzato come **Opzioni di Microsoft Defender Antivirus.** Facendo clic su questo collegamento verrà visualizzato l'interruttore che consente una scansione periodica limitata. Si noti che l'opzione periodica limitata è un interruttore per abilitare o disabilitare l'analisi periodica. 

Facendo scorrere l'interruttore **su On** verranno mostrate le opzioni standard di Microsoft Defender AV sotto il prodotto AV di terze parti. L'opzione di scansione periodica limitata verrà visualizzata nella parte inferiore della pagina.

## <a name="related-articles"></a>Articoli correlati

- [Configurare la protezione comportamentale, euristica e in tempo reale](configure-protection-features-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)