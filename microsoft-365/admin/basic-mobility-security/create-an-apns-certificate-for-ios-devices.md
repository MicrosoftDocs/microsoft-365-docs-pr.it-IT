---
title: Creare un certificato APNs per i dispositivi iOS
f1.keywords: NOCSH
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
ms.custom: AdminSurgePortfolio
description: Gestire i dispositivi iOS in Dispositivi mobili e sicurezza di base.
ms.openlocfilehash: 85baef2defa79255d560f848e57120353fd4fa2e
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "49877081"
---
# <a name="create-an-apns-certificate-for-ios-devices"></a>Creare un certificato APNs per i dispositivi iOS

Per gestire i dispositivi iOS come iPad e iPhone in Basic Mobility and Security, crea un certificato APNs.

1. Accedere a Microsoft 365 con l'account di amministratore globale.

2. Nel browser digitare  [https://protection.office.com](https://protection.office.com/) .

3. Selezionare  **Gestione dispositivi per la prevenzione della** perdita dei dati e scegliere Il certificato   >  **** **APNs per i dispositivi iOS.**

4. Nella pagina Impostazioni certificato notifica Push Apple scegliere **Avanti.**

5. Selezionare Download your CSR file and save the certificate signing request to somewhere on your computer that you'll remember. Selezionare  **Avanti.**

6. Nella pagina Crea un certificato APNs:  

    1. Seleziona Apple APNS Portal per aprire il portale dei certificati Push Apple.

    2. Sign in with an Apple ID.

    >[!IMPORTANT]
    >Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.

    3. Selezionare  **Crea un certificato** e accettare le Condizioni per   l'utilizzo.

    4. Passare alla richiesta di firma del certificato scaricata nel computer da Microsoft 365 e selezionare **Carica.**

        Scarica il certificato APNs creato dal portale dei certificati Push Apple nel computer.

       >[!TIP]
       >If you're having trouble downloading the certificate, refresh your browser.

7. Tornare a Microsoft 365  e selezionare Avanti per accedere alla pagina   Carica certificato  **APNS.**  

8.  Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.

9. Selezionare  **Fine.**

Per completare la configurazione, tornare al Centro sicurezza & conformità > **Criteri** di sicurezza   >  **Gestione dispositivi**   >  **Gestire le impostazioni.**
