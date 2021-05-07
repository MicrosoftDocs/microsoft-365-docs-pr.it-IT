---
title: Informazioni sull'estensione per la conformità Microsoft (anteprima)
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: L'estensione per la conformità Microsoft estende il monitoraggio e il controllo delle attività sui file e delle azioni di protezione nel browser Google Chrome
ms.openlocfilehash: c8a5795b3be8b393fd3a934504449bf6db0c2f01
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/30/2021
ms.locfileid: "52113382"
---
# <a name="learn-about-the-microsoft-compliance-extension-preview"></a>Informazioni sull'estensione per la conformità Microsoft (anteprima)

[Prevenzione della perdita di dati degli endpoint (Endpoint DLP)](endpoint-dlp-learn-about.md) estende le funzionalità di monitoraggio e protezione delle attività della [Prevenzione della perdita di dati di Microsoft 365 (DPL)](dlp-learn-about-dlp.md) agli elementi sensibili presenti nei dispositivi Windows 10. Dopo aver eseguito l'onboarding dei dispositivi nelle soluzioni del Centro conformità Microsoft 365, le informazioni sulle azioni che gli utenti stanno eseguendo sugli elementi sensibili sono rese visibili in [Esplora attività](data-classification-activity-explorer.md) ed è possibile applicare azioni di protezione su tali elementi tramite [criteri DLP](create-test-tune-dlp-policy.md).

Dopo l'installazione dell'estensione per la conformità Microsoft in un dispositivo Windows 10, le organizzazioni possono monitorare quando un utente prova ad accedere o caricare un elemento sensibile in un servizio cloud tramite Google Chrome e applicare azioni di protezione tramite DLP.  

## <a name="activities-you-can-monitor-and-take-action-on"></a>Attività che è possibile monitorare e su cui è possibile intervenire

L'estensione per la conformità Microsoft consente di controllare e gestire i tipi di attività seguenti che gli utenti possono eseguire su elementi sensibili nei dispositivi che eseguono Windows 10.

attività |descrizione  | azioni dei criteri supportate|
|---------|---------|---------|
|file copiato nel cloud  | Rileva quando un utente tenta di caricare un elemento sensibile in un dominio di servizio con restrizioni tramite il browser Chrome |audit, blocco|
|file stampato  |Rileva quando un utente cerca di stampare un elemento sensibile aperto nel browser Chrome in una stampante locale o di rete |audit, blocco con override, blocco|
|file copiato negli Appunti |Rileva quando un utente tenta di copiare le informazioni da un elemento sensibile visualizzato nel browser Chrome per incollarle in un'altra applicazione, processo o elemento. |audit, blocco con override, blocco|
|file copiato su archivio rimovibile    | Rileva quando un utente prova a copiare elementi o informazioni sensibili da un elemento sensibile aperto nel browser Chrome in un supporto rimovibile o un dispositivo USB |audit, blocco con override, blocco|
|file copiato in una condivisione di rete  |Rileva quando un utente prova a copiare elementi o informazioni sensibili da un elemento sensibile aperto nel browser Chrome in una condivisione di rete o un'unità di rete mappata.|audit, blocco con override, blocco |

## <a name="deployment-process"></a>Processo di distribuzione
1. [Introduzione alla prevenzione della perdita di dati degli endpoint](endpoint-dlp-getting-started.md)
2. [Strumenti e metodi di onboarding per i dispositivi Windows 10](dlp-configure-endpoints.md)
3. [Installare l'estensione nei dispositivi Windows 10](dlp-chrome-get-started.md)
4. [Creare o modificare criteri DLP](create-test-tune-dlp-policy.md) che limitano il caricamento nel servizio cloud o l'accesso da azioni del browser non consentite e l'applicazione ai dispositivi Windows 10

## <a name="next-steps"></a>Passaggi successivi

Per le procedure e gli scenari di distribuzione completi, vedere [Introduzione all'estensione per la conformità Microsoft](dlp-chrome-get-started.md).

## <a name="see-also"></a>Vedere anche

- [Introduzione all'estensione per la conformità Microsoft (anteprima)](dlp-chrome-get-started.md)
- [Informazioni sulla prevenzione della perdita di dati degli endpoint di Microsoft 365](endpoint-dlp-learn-about.md)
- [Introduzione alla prevenzione della perdita di dati degli endpoint Microsoft](endpoint-dlp-getting-started.md)
- [Uso della prevenzione della perdita di dati degli endpoint Microsoft](endpoint-dlp-using.md)
- [Informazioni sulla prevenzione della perdita di dati](dlp-learn-about-dlp.md)
- [Creare, testare e ottimizzare un criterio di prevenzione della perdita dei dati](create-test-tune-dlp-policy.md)
- [Introduzione a Esplora attività](data-classification-activity-explorer.md)
- [Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/)
- [Gestione dei rischi Insider](insider-risk-management.md)
