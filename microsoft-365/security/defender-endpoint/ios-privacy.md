---
title: Informazioni sulla privacy - Microsoft Defender for Endpoint per iOS
ms.reviewer: ''
description: Descrive le informazioni sulla privacy per Microsoft Defender for Endpoint per iOS
keywords: microsoft, defender, atp, ios, criteri, panoramica
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
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 97d22cd8ff1c651bdab5c3613567b2a4778ec9d6
ms.sourcegitcommit: 987f70e44e406ab6b1dd35f336a9d0c228032794
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/05/2021
ms.locfileid: "51587576"
---
# <a name="privacy-information---microsoft-defender-for-endpoint-for-ios"></a>Informazioni sulla privacy - Microsoft Defender for Endpoint per iOS

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

> [!NOTE]
> Defender for Endpoint per iOS usa una VPN per fornire la funzionalità Di protezione Web. Non si tratta di una VPN normale ed è una VPN locale o con looping che non porta traffico all'esterno del dispositivo. **Microsoft o l'organizzazione non visualizza l'attività di esplorazione.**

Defender for Endpoint per iOS raccoglie informazioni dai dispositivi iOS configurati e le archivia nello stesso tenant in cui si dispone di Defender per Endpoint. Le informazioni vengono raccolte per mantenere Defender for Endpoint per iOS sicuro, aggiornato, che funzioni come previsto e supportare il servizio.

Per altre informazioni sull'archiviazione dei dati, vedi [Microsoft Defender per l'archiviazione e la privacy dei dati degli endpoint.](data-storage-privacy.md)

## <a name="required-data"></a>Dati obbligatori 

I dati necessari sono costituiti dai dati necessari per far funzionare Defender for Endpoint per iOS come previsto. Questi dati sono essenziali per il funzionamento del servizio e possono includere dati relativi all'utente finale, all'organizzazione, al dispositivo e alle app. 

Ecco un elenco dei tipi di dati raccolti: 

### <a name="web-page-or-network-information"></a>Pagina Web o Informazioni di rete 

- Nome di dominio del sito Web solo quando viene rilevata una connessione o una pagina Web dannosa. 

### <a name="device-and-account-information"></a>Informazioni su dispositivi e account 

- Informazioni sul dispositivo, ad esempio data &, versione iOS, informazioni sulla CPU e identificatore del dispositivo, dove Identificatore dispositivo è uno dei seguenti: 

    - Wi-Fi mac della scheda di rete 

    - Identificatore univoco globale (GUID) generato in modo casuale 

- Informazioni su tenant, dispositivo e utente 

    - ID dispositivo di Azure Active Directory (AD) e ID utente di Azure - Identifica in modo univoco il dispositivo, rispettivamente Utente in Azure Active Directory. 

    - ID tenant di Azure - GUID che identifica l'organizzazione all'interno di Azure Active Directory. 

    - ID organizzazione di Microsoft Defender for Endpoint - Identificatore univoco associato all'organizzazione a cui appartiene il dispositivo. Consente a Microsoft di identificare se vi sono problemi che interessano un set selezionato di aziende e il numero di aziende che ne sono state influenzate. 

    - Nome entità utente - ID posta elettronica dell'utente. 

### <a name="product-and-service-usage-data"></a>Dati sull'utilizzo di prodotti e servizi 

Le informazioni seguenti vengono raccolte solo per l'app Microsoft Defender for Endpoint installata nel dispositivo. 

- Informazioni sul pacchetto dell'app, tra cui nome, versione e stato dell'aggiornamento dell'app. 

- Azioni eseguite nell'app. 

- Log dei rapporti di arresto anomalo generati da iOS. 

- Dati sull'utilizzo della memoria. 

## <a name="optional-data"></a>Dati facoltativi 

I dati facoltativi includono dati di diagnostica e dati di feedback dal client. Dati di diagnostica facoltativi sono i dati aggiuntivi che contribuiscono a migliorare i prodotti e forniscono ulteriori informazioni per facilitare il rilevamento, la diagnostica e la risoluzione dei problemi. Questi dati sono solo a scopo diagnostico e non sono necessari per il servizio stesso. 

I dati di diagnostica facoltativi includono: 

- Utilizzo di app, CPU e rete per Defender for Endpoint. 

- Funzionalità configurate dall'amministratore per Defender per Endpoint. 

Feedback I dati vengono raccolti tramite il feedback in-app fornito dall'utente. 

- L'indirizzo di posta elettronica dell'utente, se sceglie di fornirlo.

- Tipo di feedback (smile, cipiglio, idea) ed eventuali commenti di feedback inviati dall'utente. 

Per ulteriori informazioni, vedere [More on Privacy.](https://aka.ms/mdatpiosprivacystatement)


