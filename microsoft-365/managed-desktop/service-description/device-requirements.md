---
title: Requisiti dei dispositivi
description: Riepilogo dei requisiti hardware e software minimi per i dispositivi per l'utilizzo con Microsoft Managed Desktop
keywords: Microsoft Managed Desktop, Microsoft 365, servizi, documentazione
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 88b1ba657b4823d90a41b28b01362760676410ba
ms.sourcegitcommit: b3bb5bf5efa197ef8b16a33401b0b4f5663d3aa0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2021
ms.locfileid: "50032692"
---
# <a name="device-requirements"></a>Requisiti dei dispositivi

Microsoft Managed Desktop valuta regolarmente i requisiti del dispositivo da includere nel servizio. In questo articolo vengono descritti i requisiti hardware e software che un dispositivo deve soddisfare per poter lavorare con Microsoft Managed Desktop. È possibile esaminare un elenco di [dispositivi specifici già approvati](device-list.md) per l'utilizzo con il servizio in base a questi requisiti.

> [!NOTE]
> Questi requisiti possono variare in qualsiasi momento, ma verranno forniti 90 giorni di preavviso per tali modifiche. I requisiti modificati più di recente sono contrassegnati con **\*** . 

## <a name="check-hardware-requirements"></a>Controllare i requisiti hardware

Oltre a esaminare le specifiche del dispositivo, è anche possibile utilizzare lo strumento di [valutazione della conformità](../get-ready/readiness-assessment-downloadable.md) scaricabile per verificare che un determinato dispositivo soddisfi i requisiti necessari. Questo strumento consente di controllare anche le impostazioni di rete e gli endpoint necessari anche per il funzionamento del servizio.

## <a name="minimum-requirements"></a>Requisiti minimi

Per essere registrato in Microsoft Managed Desktop, un dispositivo deve soddisfare o superare tutti questi requisiti.

### <a name="manufacturer"></a>Produttore

Il dispositivo deve essere stato eseguito da uno di questi produttori:

- Dell
- HP
- Lenovo
- Microsoft


### <a name="installed-software"></a>Software installato

Il dispositivo deve disporre di questo software preinstallato:

- Windows 10 Enterprise, Pro o Pro Workstation Edition
- {la versione a 64 bit di Office a portata di clic {controllo doppio nome w/Office colleghe]}
- Tutti i driver di dispositivo applicabili


### <a name="physical-features"></a>Caratteristiche fisiche

I dispositivi devono avere queste funzionalità:

- Abilitata per l'avvio sicuro UEFI 
- Modulo Trusted Platform 2,0 
- In grado di sicurezza basata sulla virtualizzazione 
- Supporta l'integrità del codice protetto dall'hypervisor 

Per ulteriori informazioni su queste funzionalità e sulle tecnologie relative ai servizi utilizzati dal servizio, vedere [Microsoft Managed Desktop Technologies](../intro/technologies.md).

> [!NOTE]
> I processori ARM non sono supportati.

I dispositivi devono rispettare o superare i limiti seguenti per l'archiviazione e la memoria:

- L'unità di avvio deve essere di qualsiasi tipo diversa da un disco rigido. Ad esempio, le unità SSD, NVMe e eMMC sono tutte scelte valide.
- L'unità di avvio deve avere una capacità di almeno 128 GB.

Se il dispositivo è stato eseguito dopo il 1 ° luglio 2020, dovrebbe avere anche una telecamera IR, un lettore di impronte digitali o entrambi, per supportare [Windows Hello](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello-enhanced-sign-in-security).

## <a name="recommended-requirements"></a>Requisiti consigliati

Anche se non sono requisiti assoluti, gli utenti avranno un'esperienza molto migliore se si scelgono dispositivi con queste caratteristiche:

- Processore Intel vPro-Platform o processore AMD Ryzen Pro
- Unità di avvio del tipo SSD con una capacità di almeno 256 GB
- Supporto per la modalità standby moderna
- Il dispositivo è di tipo PC con protezione di base
- Supporta la protezione DMA del kernel