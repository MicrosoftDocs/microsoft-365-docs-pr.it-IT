---
title: Requisiti dei dispositivi
description: Riepilogo dei requisiti hardware e software minimi per i dispositivi che funzionano con Microsoft Managed Desktop
keywords: Microsoft Managed Desktop, Microsoft 365, servizi, documentazione
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: b17585f7449f1151c7a5f5cd75d06b8e723fbe4b
ms.sourcegitcommit: 2fd60871975d61e60d4827b36cd689021fd2a4c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/15/2021
ms.locfileid: "53438013"
---
# <a name="device-requirements"></a>Requisiti dei dispositivi

Microsoft Managed Desktop valuta regolarmente i requisiti del dispositivo da includere nel servizio. Questo articolo descrive i requisiti hardware e software che un dispositivo deve soddisfare per poter lavorare con Microsoft Managed Desktop. Puoi esaminare un elenco di dispositivi specifici già approvati per l'uso con il servizio in base a questi requisiti. Filtrare i Microsoft Managed Desktop nel [sito Dei dispositivi Windows 10 Pro negozio](https://www.microsoft.com/windowsforbusiness/view-all-devices)

> [!NOTE]
> Questi requisiti possono cambiare in qualsiasi momento, ma microsoft fornirà 30 giorni di preavviso per eventuali modifiche dei requisiti hardware. I requisiti modificati più di recente sono contrassegnati con **\*** . 

## <a name="check-hardware-requirements"></a>Verificare i requisiti hardware

Oltre a esaminare le specifiche del dispositivo, [](../get-ready/readiness-assessment-downloadable.md) puoi anche usare lo strumento di verifica della preparazione scaricabile per verificare che un determinato dispositivo soddisfi i requisiti necessari. Questo strumento controlla anche le impostazioni di rete e gli endpoint necessari per il funzionamento del servizio.

## <a name="minimum-requirements"></a>Requisiti minimi

Per essere registrato in Microsoft Managed Desktop, un dispositivo deve soddisfare o superare tutti questi requisiti.

### <a name="manufacturer"></a>Produttore

Il dispositivo deve essere stato creato da uno di questi produttori:

- Dell
- HP
- Lenovo
- Microsoft


### <a name="installed-software"></a>Software installato

Il dispositivo deve avere questo software preinstallato:

- Windows 10 Enterprise, Pro o Pro Workstation
- la versione a 64 bit di Microsoft 365 Apps for enterprise 
- Tutti i driver di dispositivo applicabili

> [!NOTE]
> Windows 11 sarà un'opzione aggiuntiva per il software preinstallato una volta raggiunta la disponibilità generale.
>
### <a name="physical-features"></a>Funzionalità fisiche

I dispositivi devono disporre di queste funzionalità:

- Abilitato per l'avvio protetto UEFI 
- Trusted Platform Module 2.0 
- In grado di eseguire la sicurezza basata su virtualizzazione 
- [Integrità del codice protetto da hypervisor](/windows-hardware/drivers/bringup/device-guard-and-credential-guard) supportata dal BIOS

Per ulteriori informazioni su queste funzionalità e sulle tecnologie correlate a esse utilizzate dal servizio, vedere [Microsoft Managed Desktop technologies](../intro/technologies.md).

> [!NOTE]
>- ARM processori non sono supportati.
>- Windows 11 ha requisiti [hardware aggiuntivi.](/windows/whats-new/windows-11-requirements)

I dispositivi devono soddisfare o superare i seguenti limiti per l'archiviazione e la memoria:

- L'unità di avvio deve essere di qualsiasi tipo diverso da un disco rigido. Ad esempio, le unità SSD, NVMe e eMMC sono tutte scelte valide.
- L'unità di avvio deve avere una capacità di almeno 128 GB.
- La memoria interna del dispositivo (RAM) deve essere uguale o superiore a 8 GB.

Se il dispositivo è stato creato dopo il 1° [luglio](/windows-hardware/design/device-experiences/windows-hello-enhanced-sign-in-security)2020, deve disporre anche di una fotocamera AR, di un lettore di impronte digitali o di entrambi i dispositivi, per supportare Windows Hello .

## <a name="recommended-features"></a>Funzionalità consigliate

Gli utenti avranno un'esperienza molto migliore se scegli dispositivi con queste funzionalità:

- Un processore Intel vPro platform o un processore AMD Ryzen Pro processore
- Unità di avvio del tipo SSD con una capacità di almeno 256 GB
- Memoria interna del dispositivo (RAM) di almeno 16 GB
- Supporto per lo standby moderno
- Il dispositivo è di tipo PC con core protetto
- Supporta la protezione DMA kernel
