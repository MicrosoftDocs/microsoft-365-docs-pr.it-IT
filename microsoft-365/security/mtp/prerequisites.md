---
title: Prerequisiti di Microsoft 365 Defender
description: Informazioni sulle licenze, i requisiti hardware e software e altre impostazioni di configurazione per Microsoft 365 Defender
keywords: requisiti, prerequisiti, hardware, software, browser, MTP, M365, licenza, E5, A5, EMS, acquisto
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 0184b2c05121e1ea3bf365263df880548f1b9232
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918871"
---
# <a name="microsoft-365-defender-prerequisites"></a>Prerequisiti di Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender

Informazioni sulle licenze e altri requisiti per il provisioning e l'uso [di Microsoft 365 Defender.](microsoft-threat-protection.md)

## <a name="licensing-requirements"></a>Requisiti per la licenza
Una di queste licenze consente di accedere alle funzionalità di Microsoft 365 Defender nel Centro sicurezza Microsoft 365 senza costi aggiuntivi:

- Microsoft 365 E5 o A5
- Microsoft 365 E5 Security o A5 Security
- Windows 10 Enterprise E5 o A5
- Enterprise Mobility + Security (EMS) E5 o A5 
- Office 365 E5 o A5
- Microsoft Defender per endpoint
- Che cosa è Microsoft Defender per identità? 
- Microsoft Cloud App Security
- Defender per Office 365 (Piano 2)

Per ulteriori informazioni, visualizzare i piani di servizio di [Microsoft 365 Enterprise.](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise)

> Non hai ancora la licenza? [Provare o acquistare un abbonamento a Microsoft 365](../../commerce/try-or-buy-microsoft-365.md?view=o365-worldwide)

### <a name="check-your-existing--licenses"></a>Controllare le licenze esistenti
Passare all'interfaccia di amministrazione di Microsoft 365 ([admin.microsoft.com](https://admin.microsoft.com/)) per visualizzare le licenze esistenti. Nell'interfaccia di amministrazione, andare in **Fatturazione** > **Licenze**.

>[!NOTE]
> Per poter visualizzare le informazioni  sulla licenza, devi essere assegnato al ruolo **Amministratore** fatturazione o Lettore globale [in Azure AD.](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) Se si verificano problemi di accesso, rivolgersi a un amministratore globale.

## <a name="required-permissions"></a>Autorizzazioni necessarie
Per attivare Microsoft 365 **Defender,** è necessario essere un amministratore globale o un amministratore della sicurezza **in** Azure Active Directory. Per l'elenco dei ruoli necessari per l'utilizzo di Microsoft 365 Defender e per informazioni su come viene regolamentato l'accesso ai dati, leggere informazioni sulla gestione dell'accesso a [Microsoft 365 Defender.](mtp-permissions.md)

## <a name="browser-requirements"></a>Requisiti per il browser
Accedere a Microsoft 365 Defender nel Centro sicurezza Microsoft 365 usando Microsoft Edge, Internet Explorer 11 o qualsiasi web browser conforme a HTML 5.

## <a name="availability-to-us-gcc-gcc-high-and-other-us-government-institutions"></a>Disponibilità per US GCC, GCC High e altre istituzioni governative statunitensi
Attualmente, Microsoft 365 Defender *non è* disponibile per:
- US Government Community Cloud (GCC)
- US Government Community Cloud High (GCC High)
- US Department of Defense
- Tutte le istituzioni governative statunitensi con licenze commerciali

## <a name="related-topics"></a>Argomenti correlati
- [Panoramica di Microsoft 365 Defender](microsoft-threat-protection.md)
- [Attivare Microsoft 365 Defender](mtp-enable.md)
- [Gestire l'accesso e le autorizzazioni](mtp-permissions.md)