---
title: Gestire le impostazioni di accesso ai dispositivi in mobilità e sicurezza di base
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: La sicurezza e la mobilità di base consentono di proteggere e gestire i dispositivi mobili.
ms.openlocfilehash: 0d8f4293c45bcc1dc2a71dbc749641cf3791337e
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/02/2020
ms.locfileid: "47336925"
---
# <a name="manage-device-access-settings-in-basic-mobility-and-security"></a>Gestire le impostazioni di accesso ai dispositivi in mobilità e sicurezza di base

Se si utilizza la sicurezza e la mobilità di base, è possibile che i dispositivi non siano in grado di gestire la mobilità e la sicurezza di base. In caso affermativo, è consigliabile bloccare l'accesso alle app di Exchange ActiveSync a Microsoft 365 per i dispositivi mobili che non sono supportati da mobilità e sicurezza di base. Questo consente di proteggere le informazioni dell'organizzazione su più dispositivi.

Attenersi alla seguente procedura:

1. Accedere a Microsoft 365 con l'account di amministratore globale.
    
2. Nel browser, digitare:  [https://protection.office.com](https://protection.office.com/) .    

    >[!IMPORTANT]
    >Se è la prima volta che si utilizza MDM per Microsoft 365 business standard, attivarlo qui: [attivare la gestione dei dispositivi mobili](https://admin.microsoft.com/EAdmin/Device/IntuneInventory.aspx). Dopo averlo attivato, gestire i dispositivi con [Office 365 Security & Compliance](https://protection.office.com/).

3. Passare a prevenzione della perdita di dati >i criteri per i dispositivi di  **gestione**dei dispositivi   >  **Device policies**e selezionare **Gestisci impostazioni di accesso ai dispositivi a livello dell'organizzazione**.
    
4. Selezionare **blocca**.

    :::image type="content" source="../../media/basic-mobility-security/bms-5-block-access.png" alt-text="Casella di controllo accesso ai blocchi di sicurezza e mobilità di base":::

5. Selezionare **Salva**. 

Per sapere quali dispositivi supportano la sicurezza e la mobilità di base, vedere [funzionalità di base per la sicurezza e la mobilità](capabilities-of-basic-mobility-and-secruity.md).