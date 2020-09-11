---
title: Gestire i dispositivi registrati nella gestione dei dispositivi mobili in Microsoft 365
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
ms.openlocfilehash: e07ff0704afcb5bca1db4e2a5c2aff9c7d6008fd
ms.sourcegitcommit: aeb94601a81db3ead8610c2f36cff30eb9fe10e7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/10/2020
ms.locfileid: "47430197"
---
# <a name="manage-devices-enrolled-in-mobile-device-management-in-microsoft-365"></a>Gestire i dispositivi registrati nella gestione dei dispositivi mobili in Microsoft 365

La gestione dei dispositivi mobili incorporati per Microsoft 365 consente di proteggere e gestire i dispositivi mobili degli utenti come iPhone, iPad, Android e Windows Phone. Il primo passaggio consiste nell'accedere a Microsoft 365 e configurare la mobilità e la sicurezza di base. Per altre informazioni, vedere [configurare la sicurezza e la mobilità di base](set-up.md).

Dopo averla configurata, gli utenti dell'organizzazione devono registrare i propri dispositivi nel servizio. Per altre informazioni, vedere [registrazione del dispositivo mobile utilizzando la sicurezza e la mobilità di base](enroll-your-mobile-device.md).È quindi possibile utilizzare la sicurezza e la mobilità di base per facilitare la gestione dei dispositivi nell'organizzazione. Ad esempio, è possibile utilizzare i criteri di sicurezza dei dispositivi per limitare l'accesso alla posta elettronica o altri servizi, visualizzare i report dei dispositivi e cancellare in remoto un dispositivo. In genere si passa al centro sicurezza & conformità per eseguire queste attività. Per altre informazioni, vedere [centro conformità Microsoft 365](https://support.microsoft.com/office/7e696a40-b86b-4a20-afcc-559218b7b1b8).

## <a name="device-management-tasks"></a>Attività di gestione dei dispositivi

Per accedere al pannello di gestione dei dispositivi, eseguire la procedura seguente:

1. Accedere all'interfaccia di [amministrazione di Microsoft 365](https://support.microsoft.com/office/758befc4-0888-4009-9f14-0d147402fd23).
    
2. Digitare gestione dei dispositivi mobili nel campo di ricerca e selezionare **Gestione dispositivi mobili**   dall'elenco dei risultati.

    :::image type="content" source="../../media/basic-mobility-security/bms-6-mobile-device-management-option.png" alt-text="Opzione di gestione dei dispositivi mobili":::

3. Selezionare  **Gestisci dispositivi**.

## <a name="manage-mobile-devices"></a>Gestire i dispositivi mobili
    
Dopo aver configurato la sicurezza e la mobilità di base, ecco alcuni modi per gestire i dispositivi mobili nell'organizzazione.

|**Per eseguire questa operazione**|**Eseguire l'operazione seguente**|
|:----------------|:------------------------------------------------------------------------------|
|Cancellare un dispositivo |Nel pannello Gestione dispositivi, selezionare *nome dispositivo*, quindi  **Pulisci completo**   per eliminare tutte le informazioni o  **Pulisci in modo selettivo**   per eliminare solo le informazioni organizzative sul dispositivo. Per altre informazioni, vedere [Wipe a Mobile Device in Basic Mobility and Security](wipe-mobile-device.md).|
|Bloccare l'accesso dei dispositivi non supportati alla posta elettronica di Exchange tramite Exchange ActiveSync |Nel pannello Gestione dispositivi selezionare  **blocca**. |
|Impostare i criteri per i dispositivi come i requisiti di password e le impostazioni di sicurezza |Nel pannello Gestione dispositivi selezionare criteri di **sicurezza del dispositivo**   >  **Aggiungi +**. Per altre informazioni, vedere [creare criteri di sicurezza dei dispositivi in mobilità e sicurezza di base](create-device-security-policies.md).|
|Visualizzare l'elenco dei dispositivi bloccati  |Nel riquadro Gestione dispositivi, in  **Seleziona una visualizzazione**   selezionare  **bloccato**. |
|Sbloccare un dispositivo non conforme o non supportato per un utente o un gruppo di utenti  |Per sbloccare i dispositivi, scegliere una delle opzioni seguenti:<br/>-Rimuovere l'utente o gli utenti dal gruppo di sicurezza a cui è stato applicato il criterio. Andare a Microsoft 365 Admin Center > **gruppi**, quindi selezionare nome gruppo. Selezionare **Modifica membri e amministratori**.<br/>-Rimuovere il gruppo di sicurezza a cui fanno parte gli utenti dal criterio dispositivo. Accedere a Security & Compliance Center  **>criteri**di protezione del dispositivo criteri di sicurezza   >  **Device security policies**. Selezionare il nome del criterio di dispositivo, quindi selezionare **modifica**  >  **distribuzione**.<br/>-Sbloccare tutti i dispositivi non conformi per un criterio di dispositivo. Accedere a Security & Compliance Center  **>criteri**di protezione del dispositivo criteri di sicurezza   >  **Device security policies**. Selezionare il nome del criterio di dispositivo e quindi selezionare **modifica**  >  **requisiti di accesso**. Selezionare  **Consenti accesso e segnala violazione**.<br/>-Per sbloccare un dispositivo non conforme o non supportato per un utente o un gruppo di utenti, visitare il Centro sicurezza & conformità > **criteri di sicurezza**   >  **gestione dei**dispositivi per   >  **gestire le impostazioni di accesso al dispositivo**. Aggiungere un gruppo di sicurezza con i membri che si desidera escludere dall'accesso bloccato a Microsoft 365. Per altre informazioni, vedere [creare, modificare o eliminare un gruppo di sicurezza nell'interfaccia di amministrazione di Microsoft 365](https://support.microsoft.com/office/55c96b32-e086-4c9e-948b-a018b44510cb).|
|Rimuovere gli utenti in modo che i dispositivi non siano più gestiti da mobilità e sicurezza di base |Per rimuovere l'utente, modificare il gruppo di sicurezza che include i criteri di gestione dei dispositivi per la sicurezza e la mobilità di base. Per altre informazioni, vedere  [creare, modificare o eliminare un gruppo di sicurezza nell'interfaccia di amministrazione di Microsoft 365](https://support.microsoft.com/office/55c96b32-e086-4c9e-948b-a018b44510cb).<br/>Per rimuovere la sicurezza e la mobilità di base da tutti gli utenti di Microsoft 365, vedere [disattivare mobilità e sicurezza di base](turn-off.md).|

Live (V14)