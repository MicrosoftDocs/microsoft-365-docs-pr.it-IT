---
title: Microsoft Information Protection in Microsoft 365
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: High
search.appverid:
- MOE150
- MET150
ms.collection:
- m365solution-mip
- m365initiative-compliance
ms.assetid: a6ef28a4-2447-4b43-aae2-f5af6d53c68e
description: Implementare Microsoft Information Protection (MIP) per proteggere le informazioni riservate ovunque si trovino in vita o in viaggio.
ms.openlocfilehash: 639f41f5d06e78e39071c60d6de0386a87536672
ms.sourcegitcommit: 9bf6a4f77f9af5fd988f6795bad3b240213a51fc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/10/2020
ms.locfileid: "48951129"
---
# <a name="microsoft-information-protection-in-microsoft-365"></a>Microsoft Information Protection in Microsoft 365

>*[Licensing for Microsoft 365 Security & Compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*

Implementare Microsoft Information Protection (MIP) per facilitare l'individuazione, la classificazione e la protezione delle informazioni riservate in qualsiasi luogo o viaggio.

Le funzionalità MIP sono incluse in Microsoft 365 compliance e offrono gli strumenti necessari per [conoscere i dati](#know-your-data), [proteggere i dati](#protect-your-data)e [prevenire la perdita di dati](#prevent-data-loss).

![Immagine del modo in cui MIP consente di individuare, classificare e proteggere i dati sensibili](../media/powered-by-intelligent-platform.png)

Per informazioni sulla governance dei dati, vedere [Microsoft Information Governance in microsoft 365](manage-Information-governance.md).

## <a name="know-your-data"></a>Riconoscere i propri dati

Per comprendere il paesaggio dei dati e identificare i dati importanti nell'ambiente ibrido, utilizzare le funzionalità seguenti:
 
|Funzionalità|Quali sono i problemi risolti?|Per iniziare|
|:------|:------------|:--------------------|:-----------------------------|
|[Tipi di informazioni riservate](sensitive-information-type-entity-definitions.md)| Identifica i dati sensibili mediante l'utilizzo di espressioni regolari predefinite o personalizzate o di una funzione, insieme a elementi probatori che includono parole chiave, livelli di sicurezza e prossimità.| [Personalizzare una tipologia integrata di informazioni sensibili](customize-a-built-in-sensitive-information-type.md)|
|[Classificatori addestrabili (anteprima)](classifier-learn-about.md)| Consente di classificare i dati per l'utente utilizzando uno dei classificatori incorporati o di formare un classificatore con il proprio contenuto. | [Introduzione ai classificatori sottoponibili a training (anteprima)](classifier-get-started-with.md) |
|[Classificazione dei dati](data-classification-overview.md) | Identifica gli elementi che dispongono di un'etichetta di riservatezza, di un'etichetta di conservazione o che sono stati classificati come un tipo di informazioni riservate nell'organizzazione e le azioni che gli utenti stanno assumendo.  | [Introduzione a Esplora contenuto](data-classification-content-explorer.md)<br /><br /> [Introduzione all'attività Esplora risorse](data-classification-activity-explorer.md) |

## <a name="protect-your-data"></a>Proteggere i propri dati

Per applicare operazioni di protezione flessibili che includono crittografia, restrizioni di accesso e segni visivi, utilizzare le seguenti funzionalità:

|Funzionalità|Quali sono i problemi risolti?|Per iniziare|
|:------|:------------|---------------------|:----------------------------|
|[Etichette di riservatezza](sensitivity-labels.md)| Una singola soluzione tra le app, i servizi e i dispositivi per etichettare e proteggere i dati in viaggio all'interno e all'esterno dell'organizzazione <br /><br />Scenario di esempio: [applicare e visualizzare le etichette di riservatezza in Power bi e proteggere i dati quando vengono esportati](https://docs.microsoft.com/power-bi/admin/service-security-apply-data-sensitivity-labels)|[ Introduzione alle etichette di riservatezza](get-started-with-sensitivity-labels.md) |
|[Client di etichettatura unificata di Azure Information Protection](https://docs.microsoft.com/azure/information-protection/rms-client/aip-clientv2)| Per i computer Windows, estende le etichette di riservatezza per caratteristiche e funzionalità aggiuntive che includono l'etichettatura e la protezione di tutti i tipi di file da Esplora file e PowerShell<br /><br /> Esempi di funzionalità aggiuntive: [configurazioni personalizzate per il client di etichettatura unificata di Azure Information Protection](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations)| [Guida dell'amministratore di Azure Information Protection Unified Labeling client](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide)|
|[Crittografia a chiave doppia](double-key-encryption.md)| In tutti i casi, solo è possibile decrittografare il contenuto protetto o per i requisiti normativi è necessario mantenere le chiavi di crittografia all'interno di un limite geografico | [Distribuire la crittografia a chiave doppia](double-key-encryption.md#deploy-dke)|
|[Crittografia dei messaggi di Office 365 (OEM)](ome.md)| Consente di crittografare i messaggi di posta elettronica e i documenti allegati inviati a qualsiasi utente su qualsiasi dispositivo, in modo che solo i destinatari autorizzati possano leggere le informazioni inviate tramite posta elettronica  <br /><br />Scenario di esempio: [revocare la posta elettronica crittografata dalla crittografia avanzata dei messaggi](revoke-ome-encrypted-mail.md) | [Configurare le nuove funzionalità di Message Encryption](set-up-new-message-encryption-capabilities.md)|
|[Crittografia del servizio con la chiave del cliente](customer-key-overview.md) | Protegge dalla visualizzazione dei dati da parte di sistemi o personale non autorizzato e complementa la crittografia del disco di BitLocker nei Data Center Microsoft | [Configurare Customer Key per Office 365](customer-key-set-up.md)|
|[Information Rights Management (IRM) di SharePoint](set-up-irm-in-sp-admin-center.md#irm-enable-sharepoint-document-libraries-and-lists)|Protegge gli elenchi e le raccolte di SharePoint in modo che quando un utente estrae un documento, il file scaricato sia protetto in modo che solo le persone autorizzate possano visualizzare e utilizzare il file in base ai criteri specificati | [Set up Information Rights Management (IRM) in SharePoint admin center](set-up-irm-in-sp-admin-center.md)|
[Connettore Rights Management](https://docs.microsoft.com/azure/information-protection/deploy-rms-connector) |Protezione: solo per le distribuzioni locali esistenti che utilizzano Exchange o SharePoint Server o file server che eseguono Windows Server e l'infrastruttura di classificazione dei file (FCI) | [Passaggi per la distribuzione del connettore RMS](https://docs.microsoft.com/azure/information-protection/deploy-rms-connector#steps-to-deploy-the-rms-connector)
|[Scanner di etichette unificato di Azure Information Protection](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner)| Consente di individuare, contrassegnare e proteggere le informazioni riservate che si trovano negli archivi dati presenti in locale. | [Configurazione e installazione di Azure Information Protection Unified Labeling scanner](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner-configure-install)|
|[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)| Consente di individuare, contrassegnare e proteggere le informazioni riservate che si trovano negli archivi dati presenti nel cloud. | [Individuare, classificare, etichettare e proteggere i dati regolamentati e sensibili archiviati nel cloud](https://docs.microsoft.com/cloud-app-security/best-practices#discover-classify-label-and-protect-regulated-and-sensitive-data-stored-in-the-cloud)|
|[SDK di Microsoft Information Protection](https://docs.microsoft.com/information-protection/develop/overview#microsoft-information-protection-sdk)|Estende le etichette di riservatezza a applicazioni e servizi di terze parti  <br /><br /> Scenario di esempio: [impostare e ottenere un'etichetta di riservatezza (C++)](https://docs.microsoft.com/information-protection/develop/quick-file-set-get-label-cpp) |[Installazione e configurazione del kit SDK di Microsoft Information Protection (MIP)](https://docs.microsoft.com/information-protection/develop/setup-configure-mip)|

## <a name="prevent-data-loss"></a>Prevenire la perdita di dati

Per evitare la condivisione accidentale di informazioni riservate, utilizzare le funzionalità seguenti:


|Funzionalità|Quali sono i problemi risolti?|Per iniziare|
|:------|:------------|:---------------------|:-----------------------------|
|[Data loss prevention (DLP)](data-loss-prevention-policies.md)| Consente di evitare la condivisione involontaria degli elementi sensibili <br /><br />Scenario di esempio: [proteggere le informazioni riservate in Microsoft teams chat and Channel messages](dlp-microsoft-teams.md) | [Cominciare con il criterio di prevenzione della perdita dei dati predefinito](get-started-with-the-default-dlp-policy.md)|
|[Prevenzione della perdita di dati di endpoint (anteprima)](endpoint-dlp-learn-about.md)| Estende le funzionalità DLP agli elementi utilizzati e condivisi nei computer Windows 10 | [Introduzione alla prevenzione della perdita di dati degli endpoint (anteprima)](endpoint-dlp-getting-started.md)|
