---
title: Microsoft 365 Prerequisiti di Defender
description: Informazioni sulle licenze, i requisiti hardware e software e altre impostazioni di configurazione per Microsoft 365 Defender
keywords: requisiti, prerequisiti, hardware, software, browser, Microsoft 365 Defender, M365, licenza, E5, A5, EMS, acquisto
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: f3fd597181d73c1768057ea7740ab111e5af2068
ms.sourcegitcommit: 82a4d74020cd93ba444006317cfecc178c6d41dc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2021
ms.locfileid: "52689158"
---
# <a name="microsoft-365-defender-prerequisites"></a>Microsoft 365 Prerequisiti di Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender

Informazioni sulle licenze e altri requisiti per il provisioning e [l'uso di Microsoft 365 Defender.](microsoft-365-defender.md)

## <a name="licensing-requirements"></a>Requisiti di licenza
Una di queste licenze consente di accedere alle Microsoft 365 Defender nel centro sicurezza Microsoft 365 senza costi aggiuntivi:

- Microsoft 365 E5 o A5
- Microsoft 365 E3 con il Microsoft 365 E5 Security aggiuntivo
- Microsoft 365 A3 con il Microsoft 365 A5 Security
- Windows 10 Enterprise E5 o A5
- Enterprise Mobility + Security (EMS) E5 o A5 
- Office 365 E5 o A5
- Microsoft Defender per endpoint
- Microsoft Defender per identità 
- Microsoft Cloud App Security
- Defender per Office 365 (Piano 2)

Per ulteriori informazioni, [visualizzare i piani Microsoft 365 Enterprise servizio.](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise)

> Non hai ancora la licenza? [Provare o acquistare un abbonamento a Microsoft 365](../../commerce/try-or-buy-microsoft-365.md)

### <a name="check-your-existing--licenses"></a>Controllare le licenze esistenti
Passare a Microsoft 365 di amministrazione ([admin.microsoft.com](https://admin.microsoft.com/)) per visualizzare le licenze esistenti. Nell'interfaccia di amministrazione, andare in **Fatturazione** > **Licenze**.

>[!NOTE]
> Per poter visualizzare le informazioni  sulla licenza, devi essere assegnato al ruolo **Amministratore** fatturazione o Lettore globale [in Azure AD.](/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) Se si verificano problemi di accesso, rivolgersi a un amministratore globale.

## <a name="required-permissions"></a>Autorizzazioni necessarie
Devi essere un **amministratore globale o** un amministratore della sicurezza in Azure Active Directory per attivare Microsoft 365 Defender.  Per l'elenco dei ruoli necessari per usare Microsoft 365 Defender e informazioni su come viene regolamentato l'accesso ai dati, vedere Gestione dell'accesso [a Microsoft 365 Defender](m365d-permissions.md).

## <a name="browser-requirements"></a>Requisiti per il browser
Accedi Microsoft 365 Defender nel centro sicurezza Microsoft 365 usando Microsoft Edge, Internet Explorer 11 o qualsiasi Web browser conforme a HTML 5.

## <a name="availability-to-us-gcc-gcc-high-and-other-us-government-institutions"></a>Disponibilità per le GCC, GCC High e altre istituzioni governative degli Stati Uniti
Attualmente, Microsoft 365 Defender *non è* disponibile per:
- Us Government Community Cloud (GCC)
- Us Government Community Cloud High (GCC High)
- US Department of Defense
- Tutte le istituzioni governative statunitensi con licenze commerciali


Attualmente, l'integrazione di Microsoft Defender per Office 365 nelle funzionalità unificate di Microsoft 365 Defender non è disponibile per i clienti nelle seguenti posizioni Office 365 datacenter:

- Brasile 
- Germania 
- Norvegia 
- Singapore 
- Sudafrica
- Svizzera 
- Emirati Arabi Uniti 


## <a name="related-topics"></a>Argomenti correlati
- [Microsoft 365 Panoramica di Defender](microsoft-365-defender.md)
- [Attivare Microsoft 365 Defender](m365d-enable.md)
- [Gestire l'accesso e le autorizzazioni](m365d-permissions.md)
