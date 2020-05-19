---
title: Prerequisiti di Microsoft Threat Protection
description: Informazioni sui requisiti di licenza, hardware e software e altre impostazioni di configurazione per Microsoft Threat Protection
keywords: requisiti, prerequisiti, hardware, software, browser, MTP, M365, License, E5, a5, EMS, Purchase
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
ms.openlocfilehash: 71e7b532e046015dd64e51fd422d276433d65b3a
ms.sourcegitcommit: 6ea9a910a8106a5f1aa589c55d166bfa67fd12a8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/18/2020
ms.locfileid: "44280535"
---
# <a name="microsoft-threat-protection-prerequisites"></a>Prerequisiti di Microsoft Threat Protection

**Si applica a:**
- Microsoft Threat Protection

Informazioni sui requisiti di licenza, hardware e software e altre impostazioni di configurazione per il provisioning e l'utilizzo di Microsoft Threat Protection.

## <a name="licensing-requirements"></a>Requisiti per la licenza

>[!IMPORTANT]
>A partire dal 12 maggio 2020, Microsoft eseguirà gradualmente nuove esperienze ottimizzate in merito ai requisiti di licenza e [all'attivazione di Microsoft Threat Protection](mtp-enable.md). Per alcune settimane durante questo periodo, alcuni clienti inizieranno a visualizzare le modifiche apportate alle esperienze del portale. Le informazioni sulle nuove esperienze sono state contrassegnate come **nuova esperienza** in questo articolo.

Per utilizzare Microsoft Threat Protection, è necessaria una singola licenza o una combinazione di licenze. Queste licenze o combinazioni di licenze consentono di accedere alle funzionalità di protezione dalle minacce di Microsoft senza costi aggiuntivi.

### <a name="single-license"></a>Licenza singola
È possibile utilizzare *una* delle licenze seguenti:

- Microsoft 365 E5 o a5
- Sicurezza di Microsoft 365 E5 o sicurezza a5

### <a name="combination-of-licenses"></a>Combinazione di licenze
È inoltre possibile utilizzare una combinazione di licenze per gli abbonamenti E5 o a5 a Office 365, *Enterprise Mobility + Security (EMS)* e Windows. La combinazione di licenze deve includere *tutte* le licenze seguenti:

- Office 365 E5 o a5
- *Enterprise Mobility + Security (EMS)* E5 o a5
- Windows 10 Enterprise E5 o a5

Per ulteriori informazioni, [vedere i piani del servizio Microsoft 365 Enterprise](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).

> Non si dispone ancora di una licenza? [Provare o acquistare un abbonamento a Microsoft 365](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide)


**Nuova esperienza:** A partire dal 12 maggio 2020, i clienti riceveranno gradualmente le modifiche apportate a questa esperienza. Per gli utenti con la nuova esperienza, la possibilità di abilitare Microsoft Threat Protection sarà disponibile per *tutti* i clienti con una delle licenze seguenti:

- Microsoft 365 E5 o a5
- Sicurezza di Microsoft 365 E5 o sicurezza a5
- Windows 10 Enterprise E5 o a5
- Enterprise Mobility + Security (EMS) E5 o a5 
- Office 365 E5 o a5
- Microsoft Defender Advanced Threat Protection 
- Azure Advanced Threat Protection 
- Microsoft Cloud App Security 
- Protezione avanzata dalle minacce di Office 365 (piano 2) 

### <a name="check-your-existing--licenses"></a>Controllare le licenze esistenti
Accedere a Microsoft 365 Admin Center ([admin.Microsoft.com](https://admin.microsoft.com/)) per visualizzare le licenze esistenti. Nell'interfaccia di amministrazione, andare in **Fatturazione** > **Licenze**.

>[!NOTE]
> Per poter visualizzare le informazioni sulla licenza, è necessario essere assegnati al ruolo di **amministratore di fatturazione** o **lettore globale** [in Azure ad](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) . Se si verificano problemi di accesso, rivolgersi a un amministratore globale.

## <a name="browser-requirements"></a>Requisiti per il browser
Accedere a Microsoft Threat Protection nel centro sicurezza Microsoft 365 utilizzando Microsoft Edge, Internet Explorer 11 o qualsiasi Web browser compatibile con HTML 5.

## <a name="availability-to-us-gcc-gcc-high-and-other-us-government-institutions"></a>Disponibilità a noi GCC, GCC High e altre istituzioni governative degli Stati Uniti
Attualmente, Microsoft Threat Protection *non* è disponibile per:
- Cloud (GCC) del governo degli Stati Uniti
- Cloud degli Stati Uniti nube alto (GCC High)
- Dipartimento della difesa degli Stati Uniti
- Tutte le istituzioni governative degli Stati Uniti con licenze commerciali

## <a name="related-topics"></a>Argomenti correlati
- [Panoramica su Microsoft Threat Protection](microsoft-threat-protection.md)
- [Attivare Microsoft Threat Protection](mtp-enable.md)
