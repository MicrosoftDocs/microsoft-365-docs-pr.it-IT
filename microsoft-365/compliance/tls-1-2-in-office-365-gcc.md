---
title: Disabilitazione di TLS 1.0 e 1.1 in Microsoft 365 GCC High e DoD
description: Illustra come Microsoft disabilita il supporto per TLS 1.1 e 1.0 in ambienti GCC High e DoD in Microsoft 365.
author: kccross
manager: laurawi
localization_priority: Normal
search.appverid:
- MET150
audience: ITPro
ms.collection: M365-security-compliance
ms.service: information-protection
ms.topic: article
ms.reviewer: krowley
ms.author: krowley
appliesto:
- Office 365 Business
ms.openlocfilehash: 16a02985107c5f578d6d6c21bf2efc6e80297951
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919342"
---
# <a name="disabling-tls-10-and-11-in-microsoft-365-gcc-high-and-dod"></a>Disabilitazione di TLS 1.0 e 1.1 in Microsoft 365 GCC High e DoD

## <a name="summary"></a>Riepilogo

Per rispettare gli standard di conformità più recenti per il Federal Risk and Authorization Management Program (FedRAMP), stiamo disabilitando Transport Layer Security (TLS) versioni 1.1 e 1.0 in Microsoft 365 per ambienti GCC High e DoD. Questa modifica è stata annunciata in precedenza tramite il supporto Microsoft in [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).

La sicurezza dei dati è importante e ci impegniamo per la trasparenza sulle modifiche che potrebbero influire sull'utilizzo del servizio.

Anche se [l'implementazione di Microsoft TLS 1.0](https://support.microsoft.com/help/3117336) non presenta vulnerabilità di sicurezza note, microsoft si impegna a mantenere gli standard di conformità FedRAMP. Pertanto, è stato disabilitato TLS 1.1 e 1.0 in Microsoft 365 in ambienti GCC High e DoD il 15 gennaio 2020. Per informazioni su come rimuovere le dipendenze TLS 1.1 e 1.0, vedere il white paper seguente:

[Risoluzione del problema di TLS 1.0](https://www.microsoft.com/download/details.aspx?id=55266)

## <a name="more-information"></a>Ulteriori informazioni

A partire dal 15 gennaio 2020, Microsoft 365 negli ambienti GCC High e DoD disabiliterà TLS 1.1 e 1.0.

Entro il 15 gennaio 2020, tutte le combinazioni di server client e server browser devono utilizzare TLS versione 1.2 (o versione successiva) per assicurarsi che tutte le connessioni possano essere effettuate senza problemi con Microsoft 365. Ciò potrebbe richiedere aggiornamenti a determinate combinazioni di server client e server browser.

Per SharePoint e OneDrive, è necessario aggiornare e configurare .NET per supportare TLS 1.2. Per informazioni, vedere [Come abilitare TLS 1.2 nei client.](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)

È necessario aggiornare i computer client per assicurarsi di mantenere l'accesso ininterrotta a Office 365 GCC High e DoD.

Dovrai aggiornare le applicazioni che chiamano le API di Microsoft 365 su TLS 1.0 o TLS 1.1 per usare TLS 1.2. .NET 4.5 per impostazione predefinita è TLS 1.1. Per aggiornare la configurazione .NET, vedere [How to enable Transport Layer Security (TLS) 1.2 on clients](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client). Per ulteriori informazioni, vedere [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).

Sappiamo che le applicazioni client seguenti non possono utilizzare TLS 1.2:

- Android 4.3 e versioni precedenti
- Firefox versione 5.0 e versioni precedenti
- Internet Explorer 8-10 in Windows 7 e versioni precedenti
- Internet Explorer 10 in Windows Phone 8.0
- Safari 6.0.4/OS X 10.8.4 e versioni precedenti

Anche se l'analisi corrente delle connessioni ai servizi Microsoft Online mostra che la maggior parte dei servizi e degli endpoint vede un utilizzo di TLS 1.1 e 1.0 molto scarso, stiamo fornendo un avviso di questa modifica in modo da poter aggiornare i client o i server interessati in base alle esigenze prima che il supporto per TLS 1.1 e 1.0 termini. Se si utilizza un'infrastruttura locale per scenari ibridi o Active Directory Federation Services (AD FS), verificare che l'infrastruttura sia in grado di supportare connessioni in ingresso e in uscita che utilizzano TLS 1.2 (o versione successiva).

Oltre alle interruzioni che potrebbero verificarsi se si utilizzano i client elencati che non possono utilizzare TLS 1.2, la rimozione di TLS 1.1 e 1.0 impedirà di utilizzare il prodotto Microsoft seguente:

- Telefono Lync

## <a name="references"></a>Riferimenti

Per indicazioni e riferimenti per assicurarsi che i client utilizzino TLS 1.2, vedere [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).