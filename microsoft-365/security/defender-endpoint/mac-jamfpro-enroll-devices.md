---
title: Registrare Microsoft Defender ATP per i dispositivi macOS in Jamf Pro
description: Registrare Microsoft Defender ATP per i dispositivi macOS in Jamf Pro
keywords: microsoft, defender, atp, mac, installazione, distribuire, disinstallazione, intune, jamfpro, macos, catalina, mojave, high sierra
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: ea71875dedf7e8706c9022420abd63bc5eb20c69
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689726"
---
# <a name="enroll-microsoft-defender-for-endpoint-on-macos-devices-into-jamf-pro"></a>Registrare Microsoft Defender per Endpoint nei dispositivi macOS in Jamf Pro 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="enroll-macos-devices"></a>Registrare dispositivi macOS

Esistono diversi metodi per la registrazione a JamF.

Questo articolo ti guiderà su due metodi:

- [Metodo 1: Inviti di registrazione](#enrollment-method-1-enrollment-invitations)
- [Metodo 2: Registrazioni prestage](#enrollment-method-2-prestage-enrollments)

Per un elenco completo, vedere [About Computer Enrollment.](https://docs.jamf.com/9.9/casper-suite/administrator-guide/About_Computer_Enrollment.html)


## <a name="enrollment-method-1-enrollment-invitations"></a>Metodo di registrazione 1: inviti alla registrazione

1. Nel dashboard di Jamf Pro, accedere a **Inviti di registrazione.**

    ![Immagine delle impostazioni di configurazione1](images/a347307458d6a9bbfa88df7dbe15398f.png)

2. Selezionare **+ Nuovo**.

    ![Primo a comparsa di un logo Descrizione generata automaticamente](images/b6c7ad56d50f497c38fc14c1e315456c.png)

3. In **Specificare i destinatari per il >** in Indirizzi di posta **elettronica** immettere gli indirizzi di posta elettronica dei destinatari.

    ![Immagine delle impostazioni di configurazione2](images/718b9d609f9f77c8b13ba88c4c0abe5d.png)

    ![Immagine delle impostazioni di configurazione3](images/ae3597247b6bc7c5347cf56ab1e820c0.png)

    Ad esempio: janedoe@contoso.com

    ![Immagine delle impostazioni di configurazione4](images/4922c0fcdde4c7f73242b13bf5e35c19.png)

4. Configurare il messaggio per l'invito.

    ![Immagine delle impostazioni di configurazione5](images/ce580aec080512d44a37ff8e82e5c2ac.png)

    ![Immagine delle impostazioni di configurazione6](images/5856b765a6ce677caacb130ca36b1a62.png)

    ![Immagine delle impostazioni di configurazione7](images/3ced5383a6be788486d89d407d042f28.png)

    ![Immagine delle impostazioni di configurazione8](images/54be9c6ed5b24cebe628dc3cd9ca4089.png)

## <a name="enrollment-method-2-prestage-enrollments"></a>Enrollment Method 2: Prestage Enrollments

1. Nel dashboard di Jamf Pro, passare a **Registrazioni prestage**.

    ![Immagine delle impostazioni di configurazione9](images/6fd0cb2bbb0e60a623829c91fd0826ab.png)

2. Seguire le istruzioni in [Computer PreStage Enrollments](https://docs.jamf.com/9.9/casper-suite/administrator-guide/Computer_PreStage_Enrollments.html).

## <a name="enroll-macos-device"></a>Registrare un dispositivo macOS

1. Seleziona **Continua** e installa il certificato CA da una **finestra Preferenze di** sistema.

    ![Immagine di Jamf Pro enrollment1](images/jamfpro-ca-certificate.png)

2. Dopo aver installato il certificato CA, torna alla finestra del browser e seleziona **Continua** e installa il profilo MDM. 

    ![Immagine di Jamf Pro enrollment2](images/jamfpro-install-mdm-profile.png)

3. Seleziona **Consenti** download da JAMF.

    ![Immagine di Jamf Pro enrollment3](images/jamfpro-download.png)

4. Seleziona **Continua per** procedere con l'installazione del profilo MDM. 

    ![Immagine di Jamf Pro enrollment4](images/jamfpro-install-mdm.png)

5. Seleziona **Continua** per installare il profilo MDM.

    ![Immagine di Jamf Pro enrollment5](images/jamfpro-mdm-unverified.png)

6. Selezionare **Continua**  per completare la configurazione. 

    ![Immagine di Jamf Pro enrollment6](images/jamfpro-mdm-profile.png)
