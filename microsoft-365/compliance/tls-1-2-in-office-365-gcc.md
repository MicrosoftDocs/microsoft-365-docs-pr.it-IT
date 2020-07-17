---
title: Obsoleto TLS 1,0 e 1,1 in Office 365 GCC High e DoD
description: Viene descritto in che modo Microsoft trasferisce la data in avanti per interrompere il supporto per TLS 1,1 e 1,0 negli ambienti GCC High e DoD in Office 365 e prepararsi per l'utilizzo di TLS 1,2.
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
ms.openlocfilehash: 76e9b203e58ba7fa23942ea42810456e3bee377d
ms.sourcegitcommit: 42b618231e9f608f3ae7226a313b0366601d0ea2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/17/2020
ms.locfileid: "45158881"
---
# <a name="deprecating-tls-10-and-11-in-office-365-gcc-high-and-dod"></a>Obsoleto TLS 1,0 e 1,1 in Office 365 GCC High e DoD

## <a name="summary"></a>Riepilogo

Per essere conformi agli standard di conformità più recenti per il programma di gestione delle autorizzazioni e dei rischi federali (FedRAMP), sono deprecati i modelli TLS (Transport Layer Security) 1,1 e 1,0 in Microsoft Office 365 per ambienti GCC High e DoD. Questa modifica è stata precedentemente annunciata tramite il supporto tecnico Microsoft [per la preparazione all'uso obbligatorio di TLS 1,2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).

La sicurezza dei dati è importante e siamo impegnati nella trasparenza sulle modifiche che potrebbero influire sull'utilizzo del servizio.

Anche se l' [implementazione di Microsoft TLS 1,0](https://support.microsoft.com/help/3117336) non ha vulnerabilità di sicurezza note, è necessario rimanere impegnati negli standard di conformità di FedRAMP. Di conseguenza, gli ambienti TLS 1,1 e 1,0 in Office 365 sono obsoleti nell'ambiente GCC High e DoD, a partire dal 15 gennaio 2020. Per informazioni su come rimuovere le dipendenze TLS 1,1 e 1,0, vedere il white paper seguente:

[Risoluzione del problema di TLS 1,0](https://www.microsoft.com/download/details.aspx?id=55266)

Durante la preparazione di questa modifica per TLS 1,1 e 1,0, è consigliabile utilizzare TLS versione 1,2. Per ulteriori informazioni, vedere [preparazione per l'utilizzo obbligatorio di TLS 1,2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).

## <a name="more-information"></a>Ulteriori informazioni

A partire da gennaio 15, 2020, Office 365 nell'ambiente GCC High e DoD diventeranno obsoleti TLS 1,1 e 1,0.

Entro il 15 gennaio 2020, tutte le combinazioni di server client e server browser devono utilizzare TLS versione 1,2 (o versione successiva) per assicurarsi che tutte le connessioni possano essere eseguite senza problemi per i servizi di Office 365. Questo potrebbe richiedere aggiornamenti a determinate combinazioni di server client e server browser.

Se non si esegue l'aggiornamento a TLS versione 1,2 (o versione successiva) entro il 15 gennaio 2020, si verificheranno problemi quando si tenta di connettersi a Office 365. Sarà inoltre necessario eseguire l'aggiornamento a TLS 1,2 (o versione successiva) come parte della risoluzione.

Sappiamo che i client seguenti non possono utilizzare TLS 1,2:

- Android 4.3 e versioni precedenti
- Firefox versione 5.0 e versioni precedenti
- Internet Explorer 8 – 10 in Windows 7 e versioni precedenti
- Internet Explorer 10 su Windows Phone 8,0
- Safari 6.0.4/OS X 10.8.4 e versioni precedenti

Si consiglia di aggiornare i client per assicurarsi di mantenere l'accesso ininterrotto a Office 365 GCC High e DoD.

Anche se l'analisi corrente delle connessioni ai servizi Microsoft online dimostra che la maggior parte dei servizi e degli endpoint Visualizza pochissimo utilizzo di TLS 1,1 e 1,0, viene fornito un avviso di questa modifica, in modo da poter aggiornare i client o i server coinvolti come necessario prima che il supporto per TLS 1,1 e 1,0 termini. Se si utilizza un'infrastruttura locale per gli scenari ibridi o Active Directory Federation Services (AD FS), verificare che l'infrastruttura sia in grado di supportare le connessioni in ingresso e in uscita che utilizzano TLS 1,2 (o versione successiva).

Oltre alle interruzioni che è possibile riscontrare se si utilizzano i client elencati che non possono utilizzare TLS 1,2, la rimozione di TLS 1,1 e 1,0 impedirà l'utilizzo del prodotto Microsoft seguente:

- Lync Phone

## <a name="references"></a>Riferimenti

L'articolo di supporto seguente descrive le linee guida e i riferimenti per assicurarsi che i client utilizzino TLS 1,2:

[Preparazione per l'utilizzo obbligatorio di TLS 1,2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)
