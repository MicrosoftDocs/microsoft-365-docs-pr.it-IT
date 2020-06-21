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
ms.openlocfilehash: f63c59403e84e79d1a4a5cf2b8a5544f5646781c
ms.sourcegitcommit: 51e47ca4b355436a2ad3deb154060eb1927428e6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2020
ms.locfileid: "44773852"
---
# <a name="microsoft-threat-protection-prerequisites"></a>Prerequisiti di Microsoft Threat Protection

**Si applica a:**
- Microsoft Threat Protection

Informazioni sulla gestione delle licenze e di altri requisiti per il provisioning e l'utilizzo di [Microsoft Threat Protection](microsoft-threat-protection.md).

## <a name="licensing-requirements"></a>Requisiti per la licenza
Una qualsiasi di queste licenze consente di accedere alle funzionalità di Microsoft Threat Protection in Microsoft 365 Security Center senza costi aggiuntivi:

- Microsoft 365 E5 o a5
- Sicurezza di Microsoft 365 E5 o sicurezza a5
- Windows 10 Enterprise E5 o a5
- Enterprise Mobility + Security (EMS) E5 o a5 
- Office 365 E5 o a5
- Microsoft Defender Advanced Threat Protection
- Azure Advanced Threat Protection 
- Microsoft Cloud App Security
- Protezione avanzata dalle minacce di Office 365 (piano 2)

> [!NOTE]
> Le licenze di valutazione per Office 365 attualmente non consentono l'accesso a Microsoft Threat Protection.

Per ulteriori informazioni, [vedere i piani del servizio Microsoft 365 Enterprise](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).

> Non si dispone ancora di una licenza? [Provare o acquistare un abbonamento a Microsoft 365](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide)

### <a name="check-your-existing--licenses"></a>Controllare le licenze esistenti
Accedere a Microsoft 365 Admin Center ([admin.Microsoft.com](https://admin.microsoft.com/)) per visualizzare le licenze esistenti. Nell'interfaccia di amministrazione, andare in **Fatturazione** > **Licenze**.

>[!NOTE]
> Per poter visualizzare le informazioni sulla licenza, è necessario essere assegnati al ruolo di **amministratore di fatturazione** o **lettore globale** [in Azure ad](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) . Se si verificano problemi di accesso, rivolgersi a un amministratore globale.

## <a name="required-permissions"></a>Autorizzazioni necessarie
Per l'elenco dei ruoli necessari e per la modalità di regolamentazione dell'accesso ai dati, leggere informazioni sulla [gestione dell'accesso a Microsoft Threat Protection](mtp-permissions.md).

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
- [Gestire l'accesso e le autorizzazioni](mtp-permissions.md)
