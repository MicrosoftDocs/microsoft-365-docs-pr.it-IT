---
title: Obsoleto TLS 1,0 e 1,1 in Office 365 GCC High e DoD
description: Viene descritto in che modo Microsoft trasferisce la data in avanti per interrompere il supporto per TLS 1,1 e 1,0 negli ambienti GCC High e DoD in Office 365 e prepararsi per l'utilizzo di TLS 1,2.
author: simonxjx
manager: dcscontentpm
localization_priority: Normal
search.appverid:
- MET150
audience: ITPro
ms.service: O365-seccomp
ms.topic: article
ms.author: v-six
ms.reviewer: lobrion
appliesto:
- Office 365 Business
ms.openlocfilehash: f61c0a809c4666981ee0f2d67eea21474b83a675
ms.sourcegitcommit: 51a9f34796535309b8ca8b52da92da0a3621327b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2020
ms.locfileid: "45024826"
---
# <a name="deprecating-tls-10-and-11-in-office-365-gcc-high-and-dod"></a>Obsoleto TLS 1,0 e 1,1 in Office 365 GCC High e DoD

> [!IMPORTANT]
> Il mondo è nel bel mezzo di una pandemia e in Microsoft siamo consapevoli dell'impatto che questa pandemia ha sui nostri clienti e sui nostri partner. Per alleggerire la pressione sui nostri clienti commerciali, abbiamo temporaneamente interrotto qualsiasi deprecazione di TLS 1.0 e 1.1. Dopo che la crisi attuale si sarà stabilizzata, invieremo un aggiornamento sulla nuova tempistica. (Questo articolo è stato modificato per includere tale modifica.)

## <a name="summary"></a>Riepilogo

Per essere conformi agli standard di conformità più recenti per il programma di gestione delle autorizzazioni e dei rischi federali (FedRAMP), è possibile procedere con le versioni 1,1 e 1,0 di Microsoft Office 365 per gli ambienti GCC High e DoD. Questa modifica è stata precedentemente annunciata tramite il supporto tecnico Microsoft [per la preparazione all'uso obbligatorio di TLS 1,2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).

Si capisce che la sicurezza dei dati è importante e si è impegnati per la trasparenza in merito alle modifiche che potrebbero influire sull'utilizzo del servizio.

Anche se l' [implementazione di Microsoft TLS 1,0](https://support.microsoft.com/help/3117336) non ha vulnerabilità di sicurezza note, è necessario rimanere impegnati negli standard di conformità di FedRAMP. Di conseguenza, gli ambienti TLS 1,1 e 1,0 in Office 365 sono obsoleti nell'ambiente GCC High e DoD, a partire dal 15 gennaio 2020. Per informazioni su come rimuovere le dipendenze TLS 1,1 e 1,0, vedere il white paper seguente:

[Risoluzione del problema di TLS 1,0](https://www.microsoft.com/download/details.aspx?id=55266)

Durante la preparazione di questa modifica per TLS 1,1 e 1,0, è consigliabile utilizzare TLS versione 1,2. Per ulteriori informazioni, vedere [preparazione per l'utilizzo obbligatorio di TLS 1,2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).

## <a name="more-information"></a>Altre informazioni

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
