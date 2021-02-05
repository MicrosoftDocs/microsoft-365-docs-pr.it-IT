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
ms.openlocfilehash: a6b5cbbcb2f48797130b080d9d1dd1e6427d4fb8
ms.sourcegitcommit: fa5659cb66d84dcfeebc03b47bd9d38017d8934d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2021
ms.locfileid: "50110052"
---
# <a name="device-requirements"></a>Requisiti dei dispositivi

Microsoft Managed Desktop valuta regolarmente i requisiti dei dispositivi da includere nel servizio. Questo articolo descrive i requisiti hardware e software che un dispositivo deve soddisfare per poter utilizzare Microsoft Managed Desktop. Puoi esaminare un elenco di dispositivi [specifici già approvati](device-list.md) per l'uso con il servizio in base a questi requisiti.

> [!NOTE]
> Questi requisiti possono cambiare in qualsiasi momento, ma forniremo 30 giorni di preavviso per eventuali modifiche ai requisiti hardware. I requisiti modificati più di recente sono contrassegnati con **\*** . 

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

- Windows 10 Enterprise, Pro o Pro Workstation Edition
- la versione a 64 bit di Microsoft Office a click-to-run 
- Tutti i driver di dispositivo applicabili


### <a name="physical-features"></a>Funzionalità fisiche

I dispositivi devono avere queste funzionalità:

- Abilitato per l'avvio protetto UEFI 
- Trusted Platform Module 2.0 
- Capacità di sicurezza basata su virtualizzazione 
- Supporta l'integrità del codice protetto da Hypervisor 

Per ulteriori informazioni su queste funzionalità e sulle tecnologie ad esse correlate utilizzate dal servizio, vedere [Tecnologie Microsoft Managed Desktop.](../intro/technologies.md)

> [!NOTE]
> ARM processori non sono supportati.

I dispositivi devono soddisfare o superare i limiti seguenti per l'archiviazione e la memoria:

- L'unità di avvio deve essere di qualsiasi tipo diverso da un disco rigido. Ad esempio, le unità SSD, NVMe e eMMC sono tutte scelte valide.
- L'unità di avvio deve avere una capacità di almeno 128 GB.

Se il dispositivo è stato creato dopo il 1° luglio 2020, deve avere anche una fotocamera A/D, un lettore di impronta digitale o entrambi per supportare [Windows Hello.](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello-enhanced-sign-in-security)

## <a name="recommended-requirements"></a>Requisiti consigliati

Anche se non sono requisiti assoluti, gli utenti avranno un'esperienza molto migliore se scegli dispositivi con queste funzionalità:

- Processore Intel vPro o AMD Ryzen Pro
- Unità di avvio del tipo SSD con una capacità di almeno 256 GB
- Supporto per lo standby moderno
- Il dispositivo è di tipo PC con chiave protetta
- Supporta la protezione DMA kernel
