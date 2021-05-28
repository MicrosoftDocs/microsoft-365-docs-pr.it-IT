---
title: Microsoft Information Protection in Microsoft 365.
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ms.collection:
- m365solution-mip
- m365initiative-compliance
recommendations: false
description: Implementare Microsoft Information Protection (MIP) per proteggere le informazioni sensibili ovunque ci si trovi.
ms.openlocfilehash: 2de9b1e4a3901477df883287a1ee350885de5513
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2021
ms.locfileid: "52683692"
---
# <a name="microsoft-information-protection-in-microsoft-365"></a>Microsoft Information Protection in Microsoft 365.

>*[Licenze per sicurezza e conformità di Microsoft 365](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*

Implementare Microsoft Information Protection (MIP) per individuare, classificare e proteggere le informazioni sensibili, ovunque ci si trovi.

Le funzionalità MIP sono incluse nella conformità di Microsoft 365 ed è possibile usare gli strumenti per [conoscere i dati](#know-your-data), [proteggere i dati](#protect-your-data)e [impedire la perdita di dati](#prevent-data-loss).

![Immagine di come MIP consente di individuare, classificare e proteggere i dati sensibili](../media/powered-by-intelligent-platform.png)

Per informazioni su come gestire i dati, vedere [Microsoft Information Governance in Microsoft 365](manage-Information-governance.md).

## <a name="know-your-data"></a>Riconoscere i propri dati

> [!NOTE]
> Per informazioni su come classificare ed etichettare i dati in Azure Purview, attualmente in anteprima, vedere  [Etichettare contenuto in Azure Purview](/azure/purview/create-sensitivity-label).

Per comprendere l’insieme dei dati e identificare i dati importanti nell'ambiente ibrido, usare le funzionalità seguenti:
 
|Funzionalità|Che problemi risolve?|Per iniziare|
|:------|:------------|:--------------------|
|[Tipi di informazioni sensibili](sensitive-information-type-learn-about.md)| Identifica i dati sensibili usando espressioni regolari predefinite o personalizzate o una funzione. Le evidenze corroborative includono parole chiave, livelli di confidenza e prossimità.| [Personalizzare un tipo di informazioni sensibili predefinito](customize-a-built-in-sensitive-information-type.md)|
|[Classificatori sottoponibili a training](classifier-learn-about.md)| Identifica i dati sensibili usando esempi di dati a cui si è interessati, anziché identificare gli elementi (criteri di ricerca). È possibile usare classificatori predefiniti o eseguire il training di un classificatore con contenuti propri.| [Introduzione ai classificatori sottoponibili a training](classifier-get-started-with.md) |
|[Classificazione dei dati](data-classification-overview.md) | Identificazione grafica degli elementi dell'organizzazione che dispongono di un'etichetta di riservatezza, un'etichetta di conservazione oppure che sono stati classificati. È inoltre possibile usare queste informazioni per ottenere dati analitici sulle azioni intraprese dagli utenti su tali elementi. | [Introduzione a Esplora contenuto](data-classification-content-explorer.md)<br /><br /> [Introduzione a Esplora attività](data-classification-activity-explorer.md) |

## <a name="protect-your-data"></a>Proteggere i propri dati

Applicare azioni di protezione flessibili che includono crittografia, restrizioni di accesso e contrassegni visivi, usare le funzionalità seguenti:

|Funzionalità|Che problemi risolve?|Per iniziare|
|:------|:------------|---------------------|
|[Etichette di riservatezza](sensitivity-labels.md)| Una soluzione singola nelle app, servizi e dispositivi per etichettare e proteggere i dati mentre si spostano all'interno e all'esterno dell'organizzazione. <br /><br />Scenari di esempio: <br /> [Gestire le etichette di riservatezza per le app Office](sensitivity-labels-office-apps.md)<br /> [Crittografare documenti e messaggi di posta elettronica](encryption-sensitivity-labels.md )<br /> [Applicare e visualizzare etichette in Power BI](/power-bi/admin/service-security-apply-data-sensitivity-labels) <br /><br /> Per un elenco completo degli scenari relativi alle etichette di riservatezza, vedere la documentazione introduttiva.|[Iniziare a usare le etichette di riservatezza](get-started-with-sensitivity-labels.md) |
|[Client di etichettatura unificata di Azure Information Protection ](/azure/information-protection/rms-client/aip-clientv2)| Per i computer Windows, estende le etichette di riservatezza per altre caratteristiche e funzionalità che includono l'etichettatura e la protezione di tutti i tipi di file da Esplora file e PowerShell<br /><br /> Esempio di funzionalità supplementari: [Configurazioni personalizzate per il client di etichettatura unificato di Azure Information Protection](/azure/information-protection/rms-client/clientv2-admin-guide-customizations)| [Guida dell’amministratore client per l’etichettatura unificata di Azure Information Protection](/azure/information-protection/rms-client/clientv2-admin-guide)|
|[Crittografia a chiave doppia](double-key-encryption.md)| In tutti i casi, solo l’organizzazione può decrittografare il contenuto protetto o, in base a i requisiti normativi, l’utente deve essere in possesso di chiave di crittografia in base a un confine geografico. | [Crittografia a chiave doppia](double-key-encryption.md#deploy-dke)|
|[Office 365 Message Encryption (OME)](ome.md)| Consente di crittografare i messaggi di posta elettronica e i documenti allegati inviati a qualsiasi utente da qualsiasi dispositivo, in modo che solo i destinatari autorizzati possano leggere le informazioni di posta elettronica.  <br /><br />Scenario esemplificativo: [Revocare un'e-mail crittografata da Advanced Message Encryption](revoke-ome-encrypted-mail.md) | [Configurare le nuove funzionalità di Message Encryption](set-up-new-message-encryption-capabilities.md)|
|[Crittografia del servizio con Customer Key](customer-key-overview.md) | Protegge dalla visualizzazione dei dati da parte di sistemi o personale non autorizzato e integra la crittografia disco BitLocker nei Data Center Microsoft. | [Configurare Customer Key per Office 365](customer-key-set-up.md)|
|[Information Rights Management (IRM)](set-up-irm-in-sp-admin-center.md#irm-enable-sharepoint-document-libraries-and-lists)|Protegge gli elenchi e le raccolte di SharePoint in modo che, quando un utente estrae un documento, il file scaricato sia protetto e che solo gli utenti autorizzati possano visualizzare e usare il file in base ai criteri specificati. | [Configurare Information Rights Management (IRM) nell'interfaccia di amministrazione di SharePoint](set-up-irm-in-sp-admin-center.md)|
[Connettore Rights Management](/azure/information-protection/deploy-rms-connector) |Protezione solo per le distribuzioni locali esistenti che usano Exchange o SharePoint Server oppure file server che eseguono Windows Server e un'infrastruttura di classificazione file (FCI) | [Procedura per distribuire il connettore RMS](/azure/information-protection/deploy-rms-connector#steps-to-deploy-the-rms-connector)
|[Scanner per l’etichettatura unificata di Azure Information Protection](/azure/information-protection/deploy-aip-scanner)| Consente di individuare, etichettare e proteggere le informazioni riservate che risiedono negli archivi dati locali. | [Configurazione e installazione dello scanner di etichettatura unificata di Azure Information Protection.r](/azure/information-protection/deploy-aip-scanner-configure-install)|
|[Microsoft Cloud App Security](/cloud-app-security/what-is-cloud-app-security)| Consente di individuare, etichettare e proteggere le informazioni riservate che si trovano negli archivi dati nel cloud. | [Individuare, classificare, etichettare e proteggere i dati regolamentati e sensibili archiviati nel cloud](/cloud-app-security/best-practices#discover-classify-label-and-protect-regulated-and-sensitive-data-stored-in-the-cloud)|
|[SDK di Microsoft Information Protection](/information-protection/develop/overview#microsoft-information-protection-sdk)|Estende le etichette di riservatezza ad app e servizi di terze parti.  <br /><br /> Scenario esemplificativo: [impostare e ottenere un'etichetta di riservatezza ( C++ )](/information-protection/develop/quick-file-set-get-label-cpp) |[Installazione e configurazione del kit SDK di Microsoft Information Protection (MIP)](/information-protection/develop/setup-configure-mip)|


## <a name="prevent-data-loss"></a>Prevenire la perdita di dati

Per evitare la condivisione accidentale di informazioni riservate, usare le funzionalità seguenti:


|Funzionalità|Che problemi risolve?|Per iniziare|
|:------|:------------|:---------------------|
|[Prevenzione della perdita dei dati](dlp-learn-about-dlp.md)| Evita la condivisione involontaria di elementi riservati. | [Cominciare con il criterio di prevenzione della perdita dei dati predefinito](get-started-with-the-default-dlp-policy.md)|
|[Prevenzione della perdita dei dati degli endpoint ](endpoint-dlp-learn-about.md)| Consente di estendere le funzionalità DLP agli elementi usati e condivisi nei computer con Windows 10. | [Introduzione alla prevenzione della perdita di dati degli endpoint](endpoint-dlp-getting-started.md)|
|[Estensione della conformità Microsoft (anteprima)](dlp-chrome-learn-about.md) | Estende le funzionalità DLP al browser Chrome | [Introduzione all'estensione della Conformità Microsoft (anteprima)](dlp-chrome-get-started.md)|
|[Scanner locale per la prevenzione della perdita dei dati di Microsoft 365 (anteprima)](dlp-on-premises-scanner-learn.md)|Estende il monitoraggio DLP delle attività sui file e le azioni di protezione per tali file nelle condivisioni di file locali, cartelle e raccolte documenti di SharePoint.|[Introduzione allo scanner locale per la prevenzione della perdita dei dati di Microsoft 365 (anteprima)](dlp-on-premises-scanner-get-started.md)|
|[Proteggere le informazioni riservate nella chat e nei messaggi di canale di Microsoft Teams](dlp-microsoft-teams.md) | Estende alcune funzionalità DLP alla chat e ai messaggi di canale di Teams | [Informazioni sul criterio predefinito per la prevenzione della perdita di dati in Microsoft Teams (anteprima)](dlp-teams-default-policy.md)|

## <a name="licensing-requirements"></a>Requisiti di licenza

I requisiti di licenza per Microsoft Information Protection dipendono dagli scenari e dalle funzionalità in uso, invece che dall'impostazione dei requisiti di licenza per ogni funzionalità elencata in questa pagina. Per informazioni sui requisiti e le opzioni di licenza per Microsoft Information Protection, vedere la sezione [Protezione delle informazioni](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection) della documentazione sulle licenze di Microsoft 365 e scaricare il relativo PDF o Excel.
