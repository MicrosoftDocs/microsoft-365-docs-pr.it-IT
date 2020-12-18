---
title: Microsoft Information Protection in Microsoft 365.
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ms.collection:
- m365solution-mip
- m365initiative-compliance
description: Implementare Microsoft Information Protection (MIP) per proteggere le informazioni sensibili ovunque ci si trovi.
ms.openlocfilehash: 2a1ec47ce888dc6d31868d65f9c4c113fa9b968c
ms.sourcegitcommit: c0495e224f12c448bfc162ef2e4b33b82f064ac8
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 12/17/2020
ms.locfileid: "49709508"
---
# <a name="microsoft-information-protection-in-microsoft-365"></a>Microsoft Information Protection in Microsoft 365.

>*[Licenze per sicurezza e conformità di Microsoft 365](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*

Implementare Microsoft Information Protection (MIP) per individuare, classificare e proteggere le informazioni sensibili, ovunque ci si trovi.

Le funzionalità MIP sono incluse nella conformità di Microsoft 365 ed è possibile usare gli strumenti per [conoscere i dati](#know-your-data), [proteggere i dati](#protect-your-data)e [impedire la perdita di dati](#prevent-data-loss).

![Immagine di come MIP consente di individuare, classificare e proteggere i dati sensibili](../media/powered-by-intelligent-platform.png)

Per informazioni su come gestire i dati, vedere [Microsoft Information Governance in Microsoft 365](manage-Information-governance.md).

## <a name="know-your-data"></a>Riconoscere i propri dati

> [!NOTE]
> Per informazioni su come classificare ed etichettare i dati in Azure Purview, attualmente in anteprima, vedere  [Etichettare contenuto in Azure Purview](https://docs.microsoft.com/azure/purview/create-sensitivity-label).
> 
> Per informazioni su questa nuova versione, vedere il post di blog [Microsoft Information Protection e Microsoft Azure competenza: insieme è meglio](https://techcommunity.microsoft.com/t5/microsoft-security-and/microsoft-information-protection-and-microsoft-azure-purview/ba-p/1957481).



Per comprendere l’insieme dei dati e identificare i dati importanti nell'ambiente ibrido, usare le funzionalità seguenti:
 
|Funzionalità|Che problemi risolve?|Per iniziare|
|:------|:------------|:--------------------|:-----------------------------|
|[Tipi di informazioni sensibili](sensitive-information-type-entity-definitions.md)| Identifica i dati sensibili usando espressioni regolari predefinite o personalizzate o una funzione, insieme a prove corroborative che includono parole chiave, livelli di confidenza e prossimità.| [Personalizzare una tipologia integrata di informazioni sensibili](customize-a-built-in-sensitive-information-type.md)|
|[Classificatori sottoponibili a training (anteprima)](classifier-learn-about.md)| Classifica i dati automaticamente, usando uno dei classificatori predefiniti o sottoponendo a training un classificatore con il proprio contenuto | [Introduzione ai classificatori sottoponibili a training (anteprima)](classifier-get-started-with.md) |
|[Classificazione dei dati](data-classification-overview.md) | Identifica elementi che hanno un'etichetta di riservatezza, un'etichetta di conservazione o sono stati classificati come tipo di informazioni sensibili nell'organizzazione e le azioni degli utenti su di esse.  | [Introduzione a Esplora contenuto](data-classification-content-explorer.md)<br /><br /> [Introduzione a Esplora attività](data-classification-activity-explorer.md) |

## <a name="protect-your-data"></a>Proteggere i propri dati

Applicare azioni di protezione flessibili che includono crittografia, restrizioni di accesso e contrassegni visivi, usare le funzionalità seguenti:

|Funzionalità|Che problemi risolve?|Per iniziare|
|:------|:------------|---------------------|:----------------------------|
|[Etichette di riservatezza](sensitivity-labels.md)| Una singola soluzione tra app, servizi e dispositivi per etichettare e proteggere i dati mentre viaggiano all'interno e all'esterno dell'organizzazione <br /><br />Scenario di esempio: [applicare e visualizzare le etichette in Power BI e proteggere i dati quando vengono salvati all'esterno del servizio](https://docs.microsoft.com/power-bi/admin/service-security-apply-data-sensitivity-labels)|[Iniziare a usare le etichette di riservatezza](get-started-with-sensitivity-labels.md) |
|[Client di etichettatura unificata di Azure Information Protection ](https://docs.microsoft.com/azure/information-protection/rms-client/aip-clientv2)| Per i computer Windows, estende le etichette di riservatezza per altre caratteristiche e funzionalità che includono l'etichettatura e la protezione di tutti i tipi di file da Esplora file e PowerShell<br /><br /> Esempio di funzionalità supplementari: [Configurazioni personalizzate per il client di etichettatura unificato di Azure Information Protection](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide-customizations)| [Guida dell’amministratore client per l’etichettatura unificata di Azure Information Protection](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-admin-guide)|
|[Crittografia a chiave doppia](double-key-encryption.md)| In tutti i casi, solo l’utente autorizzato può decrittografare il contenuto protetto o, in base a i requisiti normativi, l’utente deve essere in possesso di chiave di crittografia in base a un confine geografico. | [Crittografia a chiave doppia](double-key-encryption.md#deploy-dke)|
|[Office 365 Message Encryption (OME)](ome.md)| Consente di crittografare i messaggi di posta elettronica e i documenti allegati inviati a qualsiasi utente da qualsiasi dispositivo, in modo che solo i destinatari autorizzati possano leggere le informazioni di posta elettronica  <br /><br />Scenario esemplificativo: [Revocare un'e-mail crittografata da Advanced Message Encryption](revoke-ome-encrypted-mail.md) | [Configurare le nuove funzionalità di Message Encryption](set-up-new-message-encryption-capabilities.md)|
|[Crittografia del servizio con Customer Key](customer-key-overview.md) | Protegge dalla visualizzazione dei dati da parte di sistemi o personale non autorizzati e integra la crittografia disco BitLocker nei Data Center Microsoft. | [Configurare Customer Key per Office 365](customer-key-set-up.md)|
|[Information Rights Management (IRM)](set-up-irm-in-sp-admin-center.md#irm-enable-sharepoint-document-libraries-and-lists)|Protegge gli elenchi e le raccolte di SharePoint in modo che, quando un utente estrae un documento, il file scaricato sia protetto in modo che solo gli utenti autorizzati possano visualizzare e usare il file in base ai criteri specificati. | [Configurare Information Rights Management (IRM) nell'interfaccia di amministrazione di SharePoint](set-up-irm-in-sp-admin-center.md)|
[Connettore Rights Management](https://docs.microsoft.com/azure/information-protection/deploy-rms-connector) |Protezione-solo per le distribuzioni locali esistenti che usano Exchange o SharePoint Server o file server che eseguono Windows Server e un'infrastruttura di classificazione file (FCI) | [Procedura per distribuire il connettore RMS](https://docs.microsoft.com/azure/information-protection/deploy-rms-connector#steps-to-deploy-the-rms-connector)
|[Scanner per l’etichettatura unificata di Azure Information Protection](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner)| Consente di individuare, etichettare e proteggere le informazioni riservate che risiedono negli archivi dati locali | [Configurazione e installazione dello scanner di etichettatura unificata di Azure Information Protection.r](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner-configure-install)|
|[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)| Consente di individuare, etichettare e proteggere le informazioni riservate che si trovano negli archivi dati nel cloud | [Individuare, classificare, etichettare e proteggere i dati regolamentati e sensibili archiviati nel cloud](https://docs.microsoft.com/cloud-app-security/best-practices#discover-classify-label-and-protect-regulated-and-sensitive-data-stored-in-the-cloud)|
|[SDK di Microsoft Information Protection](https://docs.microsoft.com/information-protection/develop/overview#microsoft-information-protection-sdk)|Estendere le etichette di riservatezza ad app e servizi di terze parti  <br /><br /> Scenario esemplificativo: [impostare e ottenere un'etichetta di riservatezza ( C++ )](https://docs.microsoft.com/information-protection/develop/quick-file-set-get-label-cpp) |[Installazione e configurazione del kit SDK di Microsoft Information Protection (MIP)](https://docs.microsoft.com/information-protection/develop/setup-configure-mip)|


## <a name="prevent-data-loss"></a>Prevenire la perdita di dati

Per evitare la condivisione accidentale di informazioni riservate, usare le funzionalità seguenti:


|Funzionalità|Che problemi risolve?|Per iniziare|
|:------|:------------|:---------------------|:-----------------------------|
|[Data loss prevention (DLP)](data-loss-prevention-policies.md)| Prevenzione della condivisione involontaria di elementi riservati <br /><br />Scenario esemplificativo: [Proteggere le informazioni riservate nella chat e nei messaggi di canale di Microsoft Teams](dlp-microsoft-teams.md) | [Cominciare con il criterio di prevenzione della perdita dei dati predefinito](get-started-with-the-default-dlp-policy.md)|
|[Informazioni sulla prevenzione della perdita di dati degli endpoint](endpoint-dlp-learn-about.md)| Consente di estendere le funzionalità DLP agli elementi usati e condivisi nei computer con Windows 10 | [Introduzione alla prevenzione della perdita di dati degli endpoint](endpoint-dlp-getting-started.md)|
