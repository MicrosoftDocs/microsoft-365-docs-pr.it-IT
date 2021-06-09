---
title: Risolvere i problemi relativi alla mobilità e alla sicurezza di base
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
description: Provare questi passaggi per tenere traccia dei problemi di sicurezza e mobilità di base
ms.openlocfilehash: b8df8c17f3a2fc5b7b6cce21769ca20742dbd397
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/15/2021
ms.locfileid: "49876853"
---
# <a name="troubleshoot-basic-mobility-and-security"></a>Risolvere i problemi relativi alla mobilità e alla sicurezza di base

Se si verificano problemi quando si tenta di registrare un dispositivo in Dispositivi mobili e sicurezza di base, provare la procedura qui per rilevare il problema. Se la procedura generale non consente di risolvere il problema, vedi una delle sezioni successive con passaggi specifici per il tipo di dispositivo.

## <a name="steps-to-try-first"></a>Passaggi da provare per primi

Per iniziare, controllare quanto segue:

- Assicurati che il dispositivo non sia già registrato con un altro provider di gestione dei dispositivi mobili, ad esempio Intune.

- Assicurati che il dispositivo sia impostato sulla data e sull'ora corrette.

- Passare a una rete WIFI o cellulare diversa nel dispositivo.

- Per i dispositivi Android o iOS, disinstalla e reinstalla l Portale aziendale Intune app nel dispositivo. 

## <a name="ios-phone-or-tablet"></a>Telefono o tablet iOS

- Assicurati di aver configurato un certificato APNs. Per altre info, vedi [Creare un certificato APNs per i dispositivi iOS.](create-an-apns-certificate-for-ios-devices.md)

- In **Impostazioni**   >  **profilo**   >  **generale (o Gestione dispositivi)** assicurati che un profilo di gestione non sia già installato. In caso contrario, rimuoverlo.

- Se viene visualizzato il messaggio di errore "Impossibile registrare il dispositivo", accedere a Microsoft 365 e assicurarsi che all'utente che ha eseguito l'accesso al dispositivo sia stata assegnata una licenza che include Exchange Online.

- Se viene visualizzato il messaggio di errore "Impossibile installare il profilo", provare a eseguire una delle operazioni seguenti:

    - Assicurati che Safari sia il browser predefinito nel dispositivo e che i cookie non siano disabilitati.

    - Riavvia il dispositivo e quindi passa a portal.manage.microsoft.com. Accedi con l'ID Microsoft 365 utente e la password e prova a installare il profilo manualmente.

## <a name="windows-rt"></a>Windows RT

- Assicurati che il dominio sia configurato in Microsoft 365 per l'utilizzo con Dispositivi mobili e sicurezza di base. Per altre info, vedi [Configurare dispositivi mobili e sicurezza di base.](set-up.md)
    
- Assicurati che l'utente scegli **Attiva invece** di   scegliere **Partecipa.**

## <a name="windows-10-pc"></a>Windows 10 PC

- Assicurati che il dominio sia configurato in Microsoft 365 per l'utilizzo con Dispositivi mobili e sicurezza di base. Per altre info, vedi [Configurare dispositivi mobili e sicurezza di base.](set-up.md)
    
- A meno che non Azure Active Directory Premium, assicurati che l'utente scegli Registra **solo in** Gestione dispositivi invece di   scegliere **Connessione**.

## <a name="android-phone-or-tablet"></a>Telefono o tablet Android

- Assicurati che il dispositivo eserciti Android 4.4 o versione successiva.

- Assicurati che Chrome sia aggiornato e sia impostato come browser predefinito.

- Se viene visualizzato il messaggio di errore "Impossibile registrare questo dispositivo", accedere a Microsoft 365 e assicurarsi che all'utente che ha eseguito l'accesso al dispositivo sia stata assegnata una licenza che include Exchange Online.

- Controlla l'area di notifica nel dispositivo per verificare se sono in sospeso eventuali azioni dell'utente finale necessarie e, in caso contrario, completa le azioni.