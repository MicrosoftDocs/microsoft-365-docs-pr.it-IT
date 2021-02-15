---
title: Gestire i dispositivi registrati in Gestione dispositivi mobili in Microsoft 365
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
description: La mobilità e la sicurezza di base consentono di proteggere e gestire i dispositivi mobili.
ms.openlocfilehash: 4954da0ff44276d9bd46cabc78bc52c7879e5e26
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "49876961"
---
# <a name="manage-devices-enrolled-in-mobile-device-management-in-microsoft-365"></a>Gestire i dispositivi registrati in Gestione dispositivi mobili in Microsoft 365

La gestione dei dispositivi mobili integrata per Microsoft 365 consente di proteggere e gestire i dispositivi mobili degli utenti come iPhone, iPad, Android e telefoni Windows. Il primo passaggio consiste nell'accedere a Microsoft 365 e configurare Sicurezza e mobilità di base. Per altre info, vedi [Configurare dispositivi mobili e sicurezza di base.](set-up.md)

Dopo la configurazione, gli utenti dell'organizzazione devono registrare i propri dispositivi nel servizio. Per altre info, vedi [Registrare il dispositivo mobile con Dispositivi mobili e sicurezza di base.](enroll-your-mobile-device.md)È quindi possibile utilizzare Basic Mobility and Security per gestire i dispositivi all'interno dell'organizzazione. Ad esempio, puoi usare i criteri di sicurezza dei dispositivi per limitare l'accesso alla posta elettronica o altri servizi, visualizzare i report sui dispositivi e cancellare in remoto un dispositivo. In genere si passa al Centro sicurezza & conformità per eseguire queste attività. Per altre informazioni, vedere Centro [conformità Microsoft 365.](https://support.microsoft.com/office/7e696a40-b86b-4a20-afcc-559218b7b1b8)

## <a name="device-management-tasks"></a>Attività di gestione dei dispositivi

Per accedere al pannello di gestione dei dispositivi, segui questi passaggi:

1. Passare all'interfaccia di amministrazione di [Microsoft 365.](https://support.microsoft.com/office/758befc4-0888-4009-9f14-0d147402fd23)

2. Digita Gestione dispositivi mobili nel campo di ricerca e seleziona **Gestione dispositivi** mobili   nell'elenco dei risultati.

    :::image type="content" source="../../media/basic-mobility-security/bms-6-mobile-device-management-option.png" alt-text="Opzione di gestione dei dispositivi mobili":::

3. Selezionare  **Iniziamo.**

## <a name="manage-mobile-devices"></a>Gestire i dispositivi mobili

Dopo aver configurato Basic Mobility and Security, ecco alcuni modi per gestire i dispositivi mobili nell'organizzazione.

|**A tale scopo**|**Eseguire l'operazione seguente**|
|:----------------|:------------------------------------------------------------------------------|
|Cancellare un dispositivo |Nel pannello Gestione dispositivi seleziona il  **** nome del *dispositivo,* quindi Cancella tutto per eliminare tutte le informazioni o Cancellazione selettiva per eliminare solo le informazioni     ****   dell'organizzazione nel dispositivo. Per altre info, vedi [Cancellare un dispositivo mobile in Dispositivi mobili e sicurezza di base.](wipe-mobile-device.md)|
|Bloccare l'accesso dei dispositivi non supportati alla posta elettronica di Exchange tramite Exchange ActiveSync |Nel pannello Gestione dispositivi seleziona  **Blocca.** |
|Configurare i criteri dei dispositivi come i requisiti delle password e le impostazioni di sicurezza |Nel pannello Gestione dispositivi seleziona Criteri **di sicurezza dei dispositivi** Aggiungi   >  **+**. Per altre info, vedi [Creare criteri di sicurezza dei dispositivi in Dispositivi mobili e sicurezza di base.](create-device-security-policies.md)|
|Visualizzare l'elenco dei dispositivi bloccati  |Nel pannello Gestione dispositivi, in  **Selezionare una visualizzazione, selezionare**     **Bloccato.** |
|Sbloccare un dispositivo non conforme o non supportato per un utente o un gruppo di utenti  |Seleziona una delle opzioni seguenti per sbloccare i dispositivi:<br/>- Rimuovere l'utente o gli utenti dal gruppo di sicurezza a cui è stato applicato il criterio. Passare all'interfaccia di amministrazione di Microsoft 365 > **gruppi** e quindi selezionare il nome del gruppo. Selezionare **Modifica membri e amministratori.**<br/>- Rimuovere il gruppo di sicurezza di cui gli utenti sono membri dai criteri del dispositivo. Passare a Criteri di sicurezza & Conformità > **criteri di** sicurezza   >  **dei dispositivi.** Seleziona il nome del criterio del dispositivo e quindi **seleziona Modifica**  >  **distribuzione.**<br/>- Sblocca tutti i dispositivi non conformi per un criterio dispositivo. Passare a Criteri di sicurezza & Conformità > **criteri di** sicurezza   >  **dei dispositivi.** Selezionare il nome del criterio del dispositivo e quindi **selezionare Modifica requisiti** di  >  **accesso.** Selezionare  **Consenti accesso e segnalare la violazione.**<br/>- Per sbloccare un dispositivo non conforme o non supportato per un utente o un gruppo di utenti, passare a Centro sicurezza & conformità > **Criteri** di sicurezza Gestione dispositivi Gestire le impostazioni di accesso ai   >  ****   >  **dispositivi.** Aggiungere un gruppo di sicurezza con i membri che si desidera escludere dal blocco dell'accesso a Microsoft 365. Per altre informazioni, vedere Creare, modificare o eliminare un gruppo di sicurezza nell'interfaccia di amministrazione di [Microsoft 365.](https://support.microsoft.com/office/55c96b32-e086-4c9e-948b-a018b44510cb)|
|Rimuovere gli utenti in modo che i dispositivi non siano più gestiti da Dispositivi mobili e sicurezza di base |Per rimuovere l'utente, modificare il gruppo di sicurezza con criteri di gestione dei dispositivi per dispositivi mobili e sicurezza di base. Per altre informazioni, vedere Creare, modificare o eliminare un gruppo di sicurezza nell'interfaccia di amministrazione di  [Microsoft 365.](https://support.microsoft.com/office/55c96b32-e086-4c9e-948b-a018b44510cb)<br/>Per rimuovere La mobilità e la sicurezza di base da tutti gli utenti di Microsoft 365, vedere Disattivare La mobilità [e la sicurezza di base.](turn-off.md)|

Live (v14)