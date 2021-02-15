---
title: Disabilitazione di TLS 1.0 e 1.1 in Office 365 GCC High e DoD
description: Illustra in che modo Microsoft disabilita il supporto per TLS 1.1 e 1.0 negli ambienti GCC High e DoD in Microsoft 365.
author: workshay
manager: laurawi
localization_priority: Normal
search.appverid:
- MET150
audience: ITPro
ms.collection: M365-security-compliance
ms.service: information-protection
ms.topic: article
ms.reviewer: krowley
ms.author: shmehta
appliesto:
- Office 365 Business
ms.openlocfilehash: a0b1fecc9991cd7ba4ac915d3d684d43714014af
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233752"
---
# <a name="disabling-tls-10-and-11-in-office-365-gcc-high-and-dod"></a>Disabilitazione di TLS 1.0 e 1.1 in Office 365 GCC High e DoD

## <a name="summary"></a>Riepilogo

Per rispettare gli standard di conformità più recenti per il Federal Risk and Authorization Management Program (FedRAMP), microsoft sta disabilitando Transport Layer Security (TLS) versioni 1.1 e 1.0 in Microsoft 365 per ambienti GCC High e DoD. Questa modifica è stata annunciata in precedenza tramite il supporto tecnico Microsoft nella preparazione per l'uso obbligatorio di [TLS 1.2 in Office 365.](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)

La sicurezza dei dati è importante e ci impegniamo a trasparenza sulle modifiche che potrebbero influire sull'uso del servizio.

Anche se [l'implementazione di Microsoft TLS 1.0](https://support.microsoft.com/help/3117336) non presenta vulnerabilità di sicurezza note, microsoft si impegna a mantenere gli standard di conformità FedRAMP. Pertanto, TLS 1.1 e 1.0 sono stati disabilitati in Office 365 in ambienti GCC High e DoD il 15 gennaio 2020. Per informazioni su come rimuovere le dipendenze tls 1.1 e 1.0, vedere il white paper seguente:

[Risoluzione del problema di TLS 1.0](https://www.microsoft.com/download/details.aspx?id=55266)

## <a name="more-information"></a>Ulteriori informazioni

A partire dal 15 gennaio 2020, Office 365 negli ambienti GCC High e DoD deprecerà TLS 1.1 e 1.0.

Entro il 15 gennaio 2020, tutte le combinazioni di server client e server browser devono utilizzare TLS versione 1.2 (o versione successiva) per assicurarsi che tutte le connessioni possano essere effettuate senza problemi con i servizi di Office 365. Questa operazione potrebbe richiedere aggiornamenti a determinate combinazioni di server client e server browser.

If you do not update to TLS version 1.2 (or a later version) by January 15, 2020, you will experience issues when you try to connect to Office 365. Inoltre, sarà necessario eseguire l'aggiornamento a TLS 1.2 (o versione successiva) come parte della risoluzione.

È necessario aggiornare i computer client per assicurarsi di mantenere l'accesso senza interruzioni a Office 365 GCC High e DoD.

Dovrai aggiornare le applicazioni che chiamano le API di Microsoft 365 su TLS 1.0 o TLS 1.1 per usare TLS 1.2. .NET 4.5 per impostazione predefinita è TLS 1.1. Per aggiornare la configurazione di .NET, vedere [Come abilitare Transport Layer Security (TLS) 1.2 nei client.](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2-client) Per ulteriori informazioni, vedere [Preparazione per l'uso obbligatorio di TLS 1.2 in Office 365.](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)

Le applicazioni client seguenti non possono utilizzare TLS 1.2:

- Android 4.3 e versioni precedenti
- Firefox versione 5.0 e versioni precedenti
- Internet Explorer 8-10 in Windows 7 e versioni precedenti
- Internet Explorer 10 in Windows Phone 8.0
- Safari 6.0.4/OS X 10.8.4 e versioni precedenti

Anche se l'analisi corrente delle connessioni ai servizi online Microsoft mostra che la maggior parte dei servizi e degli endpoint vede un utilizzo molto scarso di TLS 1.1 e 1.0, stiamo fornendo un avviso di questa modifica in modo da poter aggiornare i client o i server interessati in base alle esigenze prima che il supporto per TLS 1.1 e 1.0 termini. Se si utilizza un'infrastruttura locale per scenari ibridi o Active Directory Federation Services (AD FS), assicurarsi che l'infrastruttura sia in grado di supportare connessioni in ingresso e in uscita che utilizzano TLS 1.2 (o una versione successiva).

Oltre alle interruzioni che possono verificarsi se si utilizzano i client elencati che non possono utilizzare TLS 1.2, la rimozione di TLS 1.1 e 1.0 impedisce di utilizzare il prodotto Microsoft seguente:

- Telefono Lync

## <a name="references"></a>Riferimenti

L'articolo di supporto seguente descrive le linee guida e i riferimenti per assicurarsi che i client utilizzino TLS 1.2:

[Preparazione per l'uso obbligatorio di TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)
