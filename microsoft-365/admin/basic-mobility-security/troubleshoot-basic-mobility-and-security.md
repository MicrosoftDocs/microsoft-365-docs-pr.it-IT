---
title: Risoluzione dei problemi relativi a mobilità e sicurezza di base
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
description: Provare a eseguire questa procedura per individuare i problemi di sicurezza e mobilità di base
ms.openlocfilehash: a199252c04796d5aa8c4d82a2411ccd6317f6f60
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/02/2020
ms.locfileid: "47336936"
---
# <a name="troubleshoot-basic-mobility-and-security"></a>Risoluzione dei problemi relativi a mobilità e sicurezza di base

Se si verificano problemi durante il tentativo di registrazione di un dispositivo in mobilità e sicurezza di base, provare a eseguire i passaggi seguenti per individuare il problema. Se la procedura generale non risolve il problema, vedere una delle sezioni successive con passaggi specifici per il tipo di dispositivo.

## <a name="steps-to-try-first"></a>Passaggi da provare per primo

Per iniziare, controllare quanto segue:

- Verificare che il dispositivo non sia già stato registrato con un altro provider di gestione dei dispositivi mobili, ad esempio Intune.
    
- Verificare che il dispositivo sia impostato sulla data e l'ora corrette.
    
- Passare a una rete Wi-Fi o cellulare diversa nel dispositivo.
    
- Per i dispositivi Android o iOS, disinstallare e reinstallare l'app portale aziendale di Intune nel dispositivo. 

## <a name="ios-phone-or-tablet"></a>telefono o tablet iOS

- Assicurarsi di aver configurato un certificato di APNs. Per altre informazioni, vedere [Create an APNs certificate for iOS Devices](create-an-apns-certificate-for-ios-devices.md).
    
- In **Impostazioni**   >  **General**   >  **profilo generale (o gestione dispositivi)** verificare che un profilo di gestione non sia già installato. In tal caso, rimuoverla.
    
- Se viene visualizzato il messaggio di errore "il dispositivo non è in grado di eseguire la registrazione", accedere a Microsoft 365 e verificare che sia stata assegnata una licenza che include Exchange Online all'utente che ha eseguito l'accesso al dispositivo.
    
- Se viene visualizzato il messaggio di errore "profilo non riuscito per l'installazione", provare a eseguire una delle operazioni seguenti:
    
    - Verificare che Safari sia il browser predefinito del dispositivo e che i cookie non siano disabilitati.
    
    - Riavviare il dispositivo, quindi passare a portal.manage.microsoft.com. Accedere con l'ID utente e la password Microsoft 365 e tentare di installare il profilo manualmente.    

## <a name="windows-rt"></a>Windows RT

- Verificare che il dominio sia configurato in Microsoft 365 per funzionare con la sicurezza e la mobilità di base. Per altre informazioni, vedere [configurare la sicurezza e la mobilità di base](set-up-basic-mobility-and-security.md).
    
- Assicurarsi che l'utente abbia scelto **attiva**   invece di scegliere **join**.    

## <a name="windows-10-pc"></a>PC con Windows 10

- Verificare che il dominio sia configurato in Microsoft 365 per funzionare con la sicurezza e la mobilità di base. Per altre informazioni, vedere [configurare la sicurezza e la mobilità di base](set-up-basic-mobility-and-security.md).
    
- Se non si dispone di Azure Active Directory Premium, assicurarsi che l'utente stia scegliendo **registrazione in gestione dispositivi solo**   anziché scegliere **Connetti**.

## <a name="android-phone-or-tablet"></a>Telefono o tablet Android

- Verificare che il dispositivo esegua Android 4,4 o versione successiva.
    
- Verificare che Chrome sia aggiornato e che sia impostato come browser predefinito.
    
- Se viene visualizzato il messaggio di errore "non è stato possibile registrare il dispositivo", accedere a Microsoft 365 e verificare che sia stata assegnata una licenza che include Exchange Online all'utente che ha eseguito l'accesso al dispositivo.
    
- Controllare l'area di notifica del dispositivo per verificare se le azioni dell'utente finale devono essere in sospeso e, se lo sono, completare le azioni.