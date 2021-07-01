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
ms.openlocfilehash: 84f3589593ef26325397f5b6e90d5b21662d2352
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228244"
---
# <a name="create-an-apns-certificate-for-ios-devices"></a>Creare un certificato APNs per i dispositivi iOS

Per gestire dispositivi iOS come iPad e iPhone in Dispositivi mobili e sicurezza di base, crea un certificato APNs.

1. Accedi a Microsoft 365 con il tuo account amministratore globale.

2. Nel browser digitare  <https://protection.office.com/> .

3. Seleziona  **Prevenzione della perdita dei dati** Gestione   >  **dei** dispositivi e scegli Certificato **APNs per i dispositivi iOS.**

4. Nella pagina Apple Push Notification Certificate Impostazioni scegliere **Next**.

5. Selezionare Download your CSR file and save the certificate signing request to somewhere on your computer that you'll remember. Selezionare  **Avanti**.

6. Nella pagina Crea un certificato APNs:

    1. Seleziona Apple APNS Portal per aprire il portale dei certificati Push Apple.

    2. Sign in with an Apple ID.

       > [!IMPORTANT]
       > Use a company Apple ID associated with an email account that will remain with your organization even if the user who manages the account leaves. Save this ID because you'll need to use the same ID when it's time to renew the certificate.

    3. Selezionare  **Crea un certificato** e accettare le Condizioni per   l'utilizzo.

    4. Passare alla richiesta di firma del certificato scaricata nel computer da Microsoft 365 e selezionare **Upload**.

       Scarica il certificato APNs creato dal portale dei certificati Push Apple nel computer.

       > [!TIP]
       > If you're having trouble downloading the certificate, refresh your browser.

7. Torna a Microsoft 365 e seleziona **Avanti** per accedere alla pagina Upload     **certificato APNS.**  

8.  Browse to the APN certificate you downloaded from the Apple Push Certificates Portal.

9. Selezionare  **Fine.**

Per completare la configurazione, tornare al Centro sicurezza & conformità > **Criteri** di sicurezza   >  **Gestione dispositivi**   >  **Gestisci impostazioni**.
