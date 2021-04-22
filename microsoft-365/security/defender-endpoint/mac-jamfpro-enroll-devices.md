---
title: Registrare Microsoft Defender per Endpoint nei dispositivi macOS in Jamf Pro
description: Registrare Microsoft Defender per Endpoint nei dispositivi macOS in Jamf Pro
keywords: microsoft, defender, Microsoft Defender for Endpoint, mac, installazione, distribuzione, disinstallazione, intune, jamfpro, macos, catalina, mojave, high sierra
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
ms.openlocfilehash: 0fa0db3ba85ff003d91b43d06c709ab66c37ce02
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933098"
---
# <a name="enroll-microsoft-defender-for-endpoint-on-macos-devices-into-jamf-pro"></a><span data-ttu-id="87543-104">Registrare Microsoft Defender per Endpoint nei dispositivi macOS in Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="87543-104">Enroll Microsoft Defender for Endpoint on macOS devices into Jamf Pro</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="87543-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="87543-105">**Applies to:**</span></span>
- [<span data-ttu-id="87543-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="87543-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="87543-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="87543-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="87543-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="87543-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="87543-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="87543-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="enroll-macos-devices"></a><span data-ttu-id="87543-110">Registrare dispositivi macOS</span><span class="sxs-lookup"><span data-stu-id="87543-110">Enroll macOS devices</span></span>

<span data-ttu-id="87543-111">Esistono diversi metodi per la registrazione a JamF.</span><span class="sxs-lookup"><span data-stu-id="87543-111">There are multiple methods of getting enrolled to JamF.</span></span>

<span data-ttu-id="87543-112">Questo articolo ti guiderà su due metodi:</span><span class="sxs-lookup"><span data-stu-id="87543-112">This article will guide you on two methods:</span></span>

- [<span data-ttu-id="87543-113">Metodo 1: Inviti di registrazione</span><span class="sxs-lookup"><span data-stu-id="87543-113">Method 1:  Enrollment Invitations</span></span>](#enrollment-method-1-enrollment-invitations)
- [<span data-ttu-id="87543-114">Metodo 2: Registrazioni prestage</span><span class="sxs-lookup"><span data-stu-id="87543-114">Method 2:  Prestage Enrollments</span></span>](#enrollment-method-2-prestage-enrollments)

<span data-ttu-id="87543-115">Per un elenco completo, vedere [About Computer Enrollment.](https://docs.jamf.com/9.9/casper-suite/administrator-guide/About_Computer_Enrollment.html)</span><span class="sxs-lookup"><span data-stu-id="87543-115">For a complete list, see [About Computer Enrollment](https://docs.jamf.com/9.9/casper-suite/administrator-guide/About_Computer_Enrollment.html).</span></span>


## <a name="enrollment-method-1-enrollment-invitations"></a><span data-ttu-id="87543-116">Metodo di registrazione 1: inviti alla registrazione</span><span class="sxs-lookup"><span data-stu-id="87543-116">Enrollment Method 1: Enrollment Invitations</span></span>

1. <span data-ttu-id="87543-117">Nel dashboard di Jamf Pro, accedere a **Inviti di registrazione.**</span><span class="sxs-lookup"><span data-stu-id="87543-117">In the Jamf Pro dashboard, navigate to **Enrollment invitations**.</span></span>

    ![Immagine delle impostazioni di configurazione1](images/a347307458d6a9bbfa88df7dbe15398f.png)

2. <span data-ttu-id="87543-119">Selezionare **+ Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="87543-119">Select **+ New**.</span></span>

    ![Primo a comparsa di un logo Descrizione generata automaticamente](images/b6c7ad56d50f497c38fc14c1e315456c.png)

3. <span data-ttu-id="87543-121">In **Specificare i destinatari per il >** in Indirizzi di posta **elettronica** immettere gli indirizzi di posta elettronica dei destinatari.</span><span class="sxs-lookup"><span data-stu-id="87543-121">In **Specify Recipients for the Invitation** > under **Email Addresses** enter the e-mail address(es) of the recipients.</span></span>

    ![Immagine delle impostazioni di configurazione2](images/718b9d609f9f77c8b13ba88c4c0abe5d.png)

    ![Immagine delle impostazioni di configurazione3](images/ae3597247b6bc7c5347cf56ab1e820c0.png)

    <span data-ttu-id="87543-124">Ad esempio: janedoe@contoso.com</span><span class="sxs-lookup"><span data-stu-id="87543-124">For example: janedoe@contoso.com</span></span>

    ![Immagine delle impostazioni di configurazione4](images/4922c0fcdde4c7f73242b13bf5e35c19.png)

4. <span data-ttu-id="87543-126">Configurare il messaggio per l'invito.</span><span class="sxs-lookup"><span data-stu-id="87543-126">Configure the message for the invitation.</span></span>

    ![Immagine delle impostazioni di configurazione5](images/ce580aec080512d44a37ff8e82e5c2ac.png)

    ![Immagine delle impostazioni di configurazione6](images/5856b765a6ce677caacb130ca36b1a62.png)

    ![Immagine delle impostazioni di configurazione7](images/3ced5383a6be788486d89d407d042f28.png)

    ![Immagine delle impostazioni di configurazione8](images/54be9c6ed5b24cebe628dc3cd9ca4089.png)

## <a name="enrollment-method-2-prestage-enrollments"></a><span data-ttu-id="87543-131">Enrollment Method 2: Prestage Enrollments</span><span class="sxs-lookup"><span data-stu-id="87543-131">Enrollment Method 2: Prestage Enrollments</span></span>

1. <span data-ttu-id="87543-132">Nel dashboard di Jamf Pro, passare a **Registrazioni prestage**.</span><span class="sxs-lookup"><span data-stu-id="87543-132">In the Jamf Pro dashboard, navigate to **Prestage enrollments**.</span></span>

    ![Immagine delle impostazioni di configurazione9](images/6fd0cb2bbb0e60a623829c91fd0826ab.png)

2. <span data-ttu-id="87543-134">Seguire le istruzioni in [Computer PreStage Enrollments](https://docs.jamf.com/9.9/casper-suite/administrator-guide/Computer_PreStage_Enrollments.html).</span><span class="sxs-lookup"><span data-stu-id="87543-134">Follow the instructions in [Computer PreStage Enrollments](https://docs.jamf.com/9.9/casper-suite/administrator-guide/Computer_PreStage_Enrollments.html).</span></span>

## <a name="enroll-macos-device"></a><span data-ttu-id="87543-135">Registrare un dispositivo macOS</span><span class="sxs-lookup"><span data-stu-id="87543-135">Enroll macOS device</span></span>

1. <span data-ttu-id="87543-136">Seleziona **Continua** e installa il certificato CA da una **finestra Preferenze di** sistema.</span><span class="sxs-lookup"><span data-stu-id="87543-136">Select **Continue** and install the CA certificate from a **System Preferences** window.</span></span>

    ![Immagine di Jamf Pro enrollment1](images/jamfpro-ca-certificate.png)

2. <span data-ttu-id="87543-138">Dopo aver installato il certificato CA, torna alla finestra del browser e seleziona **Continua** e installa il profilo MDM.</span><span class="sxs-lookup"><span data-stu-id="87543-138">Once CA certificate is installed, return to the browser window and select **Continue** and install the MDM profile.</span></span> 

    ![Immagine di Jamf Pro enrollment2](images/jamfpro-install-mdm-profile.png)

3. <span data-ttu-id="87543-140">Seleziona **Consenti** download da JAMF.</span><span class="sxs-lookup"><span data-stu-id="87543-140">Select **Allow** to downloads from JAMF.</span></span>

    ![Immagine di Jamf Pro enrollment3](images/jamfpro-download.png)

4. <span data-ttu-id="87543-142">Seleziona **Continua per** procedere con l'installazione del profilo MDM.</span><span class="sxs-lookup"><span data-stu-id="87543-142">Select **Continue** to proceed with the MDM Profile installation.</span></span> 

    ![Immagine di Jamf Pro enrollment4](images/jamfpro-install-mdm.png)

5. <span data-ttu-id="87543-144">Seleziona **Continua** per installare il profilo MDM.</span><span class="sxs-lookup"><span data-stu-id="87543-144">Select **Continue** to install the MDM Profile.</span></span>

    ![Immagine di Jamf Pro enrollment5](images/jamfpro-mdm-unverified.png)

6. <span data-ttu-id="87543-146">Selezionare **Continua**  per completare la configurazione.</span><span class="sxs-lookup"><span data-stu-id="87543-146">Select **Continue**  to complete the configuration.</span></span> 

    ![Immagine di Jamf Pro enrollment6](images/jamfpro-mdm-profile.png)
