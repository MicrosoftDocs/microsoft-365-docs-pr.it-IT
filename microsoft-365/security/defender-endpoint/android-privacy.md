---
title: Microsoft Defender per Endpoint su Android - Informazioni sulla privacy
description: Controlli sulla privacy, come configurare le impostazioni dei criteri che influiscono sulla privacy e informazioni sui dati di diagnostica raccolti in Microsoft Defender per Endpoint su Android.
keywords: microsoft, defender, Microsoft Defender for Endpoint, android, privacy, diagnostica
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: c72e9491303d3f14ddb184e6a302a518643f709d
ms.sourcegitcommit: 5377b00703b6f559092afe44fb61462e97968a60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2021
ms.locfileid: "52694342"
---
#  <a name="microsoft-defender-for-endpoint-on-android---privacy-information"></a>Microsoft Defender per Endpoint su Android - Informazioni sulla privacy

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


Defender per Endpoint su Android raccoglie le informazioni dai dispositivi Android configurati e le archivia nello stesso tenant in cui si dispone di Defender per Endpoint. Le informazioni vengono raccolte per mantenere Defender for Endpoint per Android sicuro, aggiornato, che funzioni come previsto e per supportare il servizio.

Per altre informazioni sull'archiviazione dei dati, vedi [Microsoft Defender per l'archiviazione e la privacy dei dati degli endpoint.](data-storage-privacy.md)

Vengono raccolte informazioni per mantenere Defender for Endpoint per Android sicuro, aggiornato, che funzioni come previsto e supporti il servizio.

Per altre informazioni sulle domande più comuni sulla privacy su Microsoft Defender per Endpoint su dispositivi mobili Android e iOS, vedi Microsoft Defender per Endpoint e la tua privacy su dispositivi mobili Android e [iOS.](https://support.microsoft.com/topic/microsoft-defender-for-endpoint-and-your-privacy-on-android-and-ios-mobile-devices-4109bc54-8ec5-4433-9c33-d359b75ac22a)

## <a name="required-data"></a>Dati obbligatori 

I dati necessari sono costituiti dai dati necessari per far funzionare Defender for Endpoint per Android come previsto. Questi dati sono essenziali per il funzionamento del servizio e possono includere dati relativi all'utente finale, all'organizzazione, al dispositivo e alle app. Ecco un elenco dei tipi di dati raccolti:

### <a name="app-information"></a>Informazioni sull'app

Informazioni sui **pacchetti di** applicazioni Android dannosi (APK) nel dispositivo, tra cui

-  Origine installazione
-  Archiviazione percorso (percorso file) dell'APK
-  Tempo di installazione, dimensioni di APK e autorizzazioni

### <a name="web-page--network-information"></a>Pagina Web / Informazioni di rete

- URL completo del sito Web solo quando viene rilevata una connessione o una pagina Web dannosa.
- Informazioni di connessione
- Tipo di protocollo (ad esempio HTTP, HTTPS e così via)


### <a name="device-and-account-information"></a>Informazioni su dispositivi e account

- Informazioni sul dispositivo, ad esempio data &, versione Android, modello OEM, informazioni sulla CPU e identificatore del dispositivo
- L'identificatore del dispositivo è uno dei seguenti:
    - Wi-Fi mac della scheda di rete
    - [ID Android](https://developer.android.com/reference/android/provider/Settings.Secure#ANDROID_ID) (generato da Android al momento del primo avvio del dispositivo)
    - Identificatore univoco globale (GUID) generato in modo casuale

- Informazioni su tenant, dispositivo e utente
    -   Azure Active Directory (AD) ID dispositivo e ID utente di Azure: identifica in modo univoco il dispositivo, rispettivamente Utente in Azure Active Directory.

    -   ID tenant di Azure - GUID che identifica l'organizzazione all'interno di Azure Active Directory

    -   ID organizzazione di Microsoft Defender for Endpoint - Identificatore univoco associato all'organizzazione a cui appartiene il dispositivo. Consente a Microsoft di identificare se i problemi influiscono su un set selezionato di aziende e su quante aziende sono influenzate 

    -   Nome entità utente - ID posta elettronica dell'utente

### <a name="product-and-service-usage-data"></a>Dati sull'utilizzo di prodotti e servizi

Le informazioni seguenti vengono raccolte solo per l'app Microsoft Defender for Endpoint installata nel dispositivo. 

-   Informazioni sul pacchetto dell'app, tra cui nome, versione e stato dell'aggiornamento dell'app

-   Azioni eseguite nell'app

-   Informazioni sul rilevamento delle minacce, ad esempio nome, categoria e così via.

-   Log dei rapporti di arresto anomalo generati da Android

## <a name="optional-data"></a>Dati facoltativi

I dati facoltativi includono i dati di diagnostica e i dati di feedback. Dati di diagnostica facoltativi sono i dati aggiuntivi che contribuiscono a migliorare i prodotti e forniscono ulteriori informazioni per facilitare il rilevamento, la diagnostica e la risoluzione dei problemi. I dati di diagnostica facoltativi includono:

-   Utilizzo di app, CPU e rete

-   Stato del dispositivo dal punto di vista dell'app, inclusi lo stato dell'analisi, gli intervalli di analisi, le autorizzazioni dell'app concesse e lo stato dell'aggiornamento

-   Funzionalità configurate dall'amministratore

-   Informazioni di base sui browser nel dispositivo

**Feedback I dati** vengono raccolti tramite il feedback in-app fornito dall'utente

-   Indirizzo di posta elettronica dell'utente, se sceglie di fornirlo

-   Tipo di feedback (smile, cipiglio, idea) ed eventuali commenti di feedback inviati dall'utente
