---
title: Informazioni sulla prevenzione della perdita di dati degli endpoint di Microsoft 365 (anteprima)
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/21/2020
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
description: 'La prevenzione della perdita di dati degli endpoint di Microsoft 365 estende il monitoraggio delle attività dei file e le azioni di protezione agli endpoint. I file vengono resi visibili nelle soluzioni di conformità di Microsoft 365 '
ms.openlocfilehash: 2423f45fefe994fbaf5704074c49ce862a59340e
ms.sourcegitcommit: df59c83174d845b8ddec48b9be2659fbfb58bb7f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/29/2020
ms.locfileid: "46517497"
---
# <a name="learn-about-microsoft-365-endpoint-data-loss-prevention-preview"></a>Informazioni sulla prevenzione della perdita di dati degli endpoint di Microsoft 365 (anteprima)

È possibile usare la prevenzione della perdita dei dati (DLP) di Microsoft 365 per monitorare le azioni intraprese sugli elementi che si considerano sensibili e per evitare la condivisione involontaria di tali elementi. Per altre informazioni, vedere [Panoramica sulla prevenzione della perdita dei dati](data-loss-prevention-policies.md).

La **prevenzione della perdita di dati degli endpoint** (Endpoint DLP) estende le funzionalità di monitoraggio e protezione delle attività di DLP agli elementi sensibili presenti nei dispositivi Windows 10. Dopo aver eseguito l'onboarding dei dispositivi nelle soluzioni del Centro conformità Microsoft 365, le informazioni sulle azioni che gli utenti stanno eseguendo sugli elementi sensibili sono rese visibili in [Esplora attività](data-classification-activity-explorer.md) ed è possibile applicare azioni di protezione su tali elementi tramite [criteri DLP](create-test-tune-dlp-policy.md).

## <a name="endpoint-activities-you-can-monitor-and-take-action-on"></a>Attività endpoint che è possibile monitorare e su cui si può intervenire

Microsoft Endpoint DLP consente di controllare e gestire i tipi di attività seguenti, che gli utenti possono eseguire sugli elementi sensibili nei dispositivi che eseguono Windows 10. Questo include:


|attività sull'elemento |controllabile/limitabile  |
|---------|---------|
|creazione    | controllabile      |
|ridenominazione    |  controllabile       |
|copia o creazione su supporti rimovibili     |     controllabile e limitabile|
|copia in condivisione di rete, ad esempio \\mio-server\fileshare   |     controllabile e limitabile    |
|stampa |    controllabile e limitabile       |
|copia nel cloud tramite Microsoft Edge Chromium    |   controllabile e limitabile        |
|accesso da app e browser non consentiti    |  controllabile e limitabile       |

## <a name="whats-different-in-endpoint-dlp"></a>Cosa distingue Endpoint DLP

Ci sono alcuni concetti aggiuntivi che è necessario conoscere prima di approfondire l'utilizzo di Endpoint DLP.

### <a name="enabling-device-management"></a>Abilitare la gestione dei dispositivi

La gestione dei dispositivi è la funzionalità che consente la raccolta di dati di telemetria dai dispositivi e la introduce nelle soluzioni di conformità di Microsoft 365, come Endpoint DLP e [Gestione dei rischi Insider](insider-risk-management.md). È necessario eseguire l'onboarding di tutti i dispositivi che si vogliono usare come posizioni nei criteri DLP.

![abilitare la gestione dei dispositivi](../media/endpoint-dlp-learn-about-1-enable-device-management.png)

Onboarding e offboarding vengono gestiti tramite script scaricati dal centro gestione dispositivi. Nel centro sono disponibili script personalizzati per ognuno di questi metodi di distribuzione:

- script locale (fino a 10 computer)
- Criteri di gruppo
- System Center Configuration Manager (versione 1610 o successiva)
- Gestione dispositivi mobili/Microsoft Intune
- Script di onboarding VDI per dispositivi non persistenti

![pagina di onboarding dispositivi](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)

 Seguire le procedure in [Introduzione a Microsoft 365 Endpoint DLP](endpoint-dlp-getting-started.md) per l'onboarding dei dispositivi.

Se si è già eseguito l'onboarding di dispositivi tramite [Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP)](https://docs.microsoft.com/windows/security/threat-protection/), verranno visualizzati automaticamente nell'elenco di dispositivi.

![elenco dispositivi gestiti](../media/endpoint-dlp-learn-about-2-device-list.png)

### <a name="viewing-endpoint-dlp-data"></a>Visualizzazione dei dati di Endpoint DLP

 Endpoint DLP monitora le attività in base al tipo MIME, in modo che le attività vengano acquisite anche se l'estensione del file viene cambiata. Nell'anteprima pubblica viene controllato tutto:

- File di Word
- File di PowerPoint
- File di Excel
- File PDF
- File CSV
- File TSV
- File C
- File di classe
- File CPP
- File CS
- File H
- File Java

> [!NOTE]
> I file TXT e di codice sorgente non vengono controllati per impostazione predefinita, DLP li valuta in base ai criteri applicati e le azioni utente vengono controllate o bloccate di conseguenza.

Dopo l'onboarding di un dispositivo, le informazioni sulle attività controllate fluiscono in Esplora attività anche prima che vengano configurati e distribuiti criteri di prevenzione della perdita dei dati che usano dispositivi come posizione.

![Eventi di Endpoint DLP in Esplora attività](../media/endpoint-dlp-learn-about-4-activity-explorer.png)

Endpoint DLP raccoglie informazioni complete sulle attività controllate.

Ad esempio, se un file viene copiato in un supporto USB rimovibile, nei dettagli attività vengono visualizzati questi attributi:

- tipo di attività
- IP client
- percorso file di destinazione
- timestamp dell'attività
- nome del file
- utente
- estensione del file
- dimensioni del file
- tipo di informazioni sensibili (se applicabile)
- valore SHA1
- valore SHA256
- nome file precedente
- posizione
- padre
- percorso file
- tipo di percorso di origine
- piattaforma
- nome dispositivo
- tipo di percorso di destinazione
- applicazione che ha eseguito la copia
- ID dispositivo MDATP (se applicabile)
- produttore del dispositivo multimediale rimovibile
- modello di dispositivo multimediale rimovibile
- numero di serie del dispositivo multimediale rimovibile

![attributi dell'attività di copia su USB](../media/endpoint-dlp-learn-about-5-activity-attributes.png)

## <a name="next-steps"></a>Passaggi successivi

Dopo avere acquisito familiarità con Endpoint DLP, è possibile proseguire con questi argomenti:

1) [Introduzione alla prevenzione della perdita di dati degli endpoint Microsoft (anteprima)](endpoint-dlp-getting-started.md)
2) [Uso della prevenzione della perdita di dati degli endpoint Microsoft (anteprima)](endpoint-dlp-using.md)

## <a name="see-also"></a>Vedere anche

- [Introduzione alla prevenzione della perdita di dati degli endpoint Microsoft (anteprima)](endpoint-dlp-getting-started.md)
- [Uso della prevenzione della perdita di dati degli endpoint Microsoft (anteprima)](endpoint-dlp-using.md)
- [Panoramica sulla prevenzione della perdita dei dati](data-loss-prevention-policies.md)
- [Creare, testare e ottimizzare un criterio di prevenzione della perdita dei dati](create-test-tune-dlp-policy.md)
- [Introduzione a Esplora attività](data-classification-activity-explorer.md)
- [Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP)](https://docs.microsoft.com/windows/security/threat-protection/)
- [Gestione dei rischi Insider](insider-risk-management.md)