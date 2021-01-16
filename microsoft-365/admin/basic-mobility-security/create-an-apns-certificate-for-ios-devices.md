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
description: Gestire i dispositivi iOS in mobilità e sicurezza di base.
ms.openlocfilehash: 85baef2defa79255d560f848e57120353fd4fa2e
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "49877081"
---
# <a name="create-an-apns-certificate-for-ios-devices"></a>Creare un certificato APNs per i dispositivi iOS

Per gestire i dispositivi iOS, come iPads e iPhone, in mobilità e sicurezza di base, creare un certificato di APNs.

1. Accedere a Microsoft 365 con l'account di amministratore globale.

2. Nel browser digitare  [https://protection.office.com](https://protection.office.com/) .

3. Selezionare Gestione dei dispositivi per la prevenzione della perdita di  **dati**   >  **** e scegliere **APNs certificate for iOS Devices**.

4. Nella pagina impostazioni del certificato di notifica push di Apple scegliere **Avanti**.

5. Selezionare Scarica il file CSR e salvare la richiesta di firma del certificato in un punto qualsiasi del computer da ricordare. Selezionare  **Avanti**.

6. Nella pagina Create an APNs certificate:  

    1. Selezionare il portale Apple APNS per aprire il portale Apple Push Certificates.

    2. Sign in with an Apple ID.

    >[!IMPORTANT]
    >Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.

    3. Selezionare  **Create a certificate**   e accettate le condizioni per l'utilizzo.

    4. Passare alla richiesta di firma del certificato scaricata nel computer da Microsoft 365 e selezionare **carica**.

        Scaricare il certificato APNs creato dal portale Apple Push certificate nel computer in uso.

       >[!TIP]
       >If you're having trouble downloading the certificate, refresh your browser.

7. Tornare a Microsoft 365 e fare clic su **Avanti**   per accedere alla pagina   **carica APNs certificate**   .

8.  Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.

9. Selezionare  **fine**.

Per completare l'installazione, tornare al centro sicurezza & Compliance > **criteri di sicurezza**   >  **Gestione dispositivi**   >  **gestire le impostazioni**.
