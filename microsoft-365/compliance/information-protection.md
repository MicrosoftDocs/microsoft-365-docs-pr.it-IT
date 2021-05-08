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
ms.openlocfilehash: 5b9484826f0d3a297dae47c7d140d93297473023
ms.sourcegitcommit: 5a1cb7d95070eef47d401a4693cc137a90550a5e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2021
ms.locfileid: "52259299"
---
# <a name="microsoft-information-protection-in-microsoft-365"></a>Microsoft Information Protection in Microsoft 365.

>*[Licenze per sicurezza e conformità di Microsoft 365](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*

Implementare Microsoft Information Protection (MIP) per individuare, classificare e proteggere le informazioni sensibili, ovunque ci si trovi.

Le funzionalità MIP sono incluse nella conformità di Microsoft 365 ed è possibile usare gli strumenti per [conoscere i dati](#know-your-data), [proteggere i dati](#protect-your-data)e [impedire la perdita di dati](#prevent-data-loss).

![Immagine di come MIP consente di individuare, classificare e proteggere i dati sensibili](../media/powered-by-intelligent-platform.png)

:::image type="content" source="../media/data-table1-4638524-new.png" alt-text="Riconoscere i propri dati":::

Per informazioni su come gestire i dati, vedere [Microsoft Information Governance in Microsoft 365](manage-Information-governance.md).

## <a name="know-your-data"></a>Riconoscere i propri dati

> [!NOTE]
> Per informazioni su come classificare ed etichettare i dati in Azure Purview, attualmente in anteprima, vedere  [Etichettare contenuto in Azure Purview](/azure/purview/create-sensitivity-label).
> 
> Per gli annunci di rilascio di Azure Purview, vedere i post di blog seguenti: [Microsoft Information Protection e Microsoft Azure Purview: l'unione fa la forza](https://techcommunity.microsoft.com/t5/microsoft-security-and/microsoft-information-protection-and-microsoft-azure-purview/ba-p/1957481) and [Azure Purview at Spring Ignite 2021](https://techcommunity.microsoft.com/t5/azure-purview/azure-purview-at-spring-ignite-2021/ba-p/2175919).

Per comprendere l’insieme dei dati e identificare i dati importanti nell'ambiente ibrido, usare le funzionalità seguenti:

:::image type="content" source="../media/knowyourdata-new.png" alt-text="Riconoscere i propri dati"::: 


|**Funzionalità**|**Che problemi risolve?**|**Introduzione**|**Licenze**|
|--|--|--|--|
|[Tipi di informazioni sensibili](sensitive-information-type-entity-definitions.md)| Identifica i dati sensibili usando espressioni regolari predefinite o personalizzate o una funzione, insieme a prove corroborative che includono parole chiave, livelli di confidenza e prossimità. Usa i tipi di informazioni riservate per identificare tipi specifici di dati nella tua organizzazione. Usa i tipi di informazioni riservate predefiniti per trovare tipi di dati standard, ad esempio i numeri di passaporto. Crea un tipo di informazioni personalizzato per identificare informazioni univoche per il tuo ambiente, ad esempio i numeri di parte. | [Personalizzare una tipologia integrata di informazioni sensibili](customize-a-built-in-sensitive-information-type.md)| |
|[Classificatori sottoponibili a training (anteprima)](classifier-learn-about.md)| Classifica i dati automaticamente, usando uno dei classificatori predefiniti o sottoponendo a training un classificatore con il proprio contenuto | [Introduzione ai classificatori sottoponibili a training (anteprima)](classifier-get-started-with.md)| |
|[Classificazione dei dati](data-classification-overview.md) | Identifica elementi che hanno un'etichetta di riservatezza, un'etichetta di conservazione o sono stati classificati come tipo di informazioni sensibili nell'organizzazione e le azioni degli utenti su di esse.  | [Introduzione a Esplora contenuto](data-classification-content-explorer.md)<br /><br /> [Introduzione a Esplora attività](data-classification-activity-explorer.md)| |



## <a name="protect-your-data"></a>Proteggere i propri dati

Applicare azioni di protezione flessibili che includono crittografia, restrizioni di accesso e contrassegni visivi, usare le funzionalità seguenti:


:::image type="content" source="../media/protectyourdata-4638524-new.png" alt-text="Proteggere i propri dati":::

|**Funzionalità**|**Che problemi risolve?**|**Introduzione**|**Licenze**|
|--|--|--|--|
|[Etichette di riservatezza](sensitivity-labels.md)| Una singola soluzione tra app, servizi e dispositivi per etichettare e proteggere i dati mentre viaggiano all'interno e all'esterno dell'organizzazione <br /><br />Scenario esemplificativo: [Applicare e visualizzare le etichette di riservatezza in Power BI e proteggere i dati durante l'esportazione](/power-bi/admin/service-security-apply-data-sensitivity-labels)|[Iniziare a usare le etichette di riservatezza](get-started-with-sensitivity-labels.md) |
|[Microsoft Cloud App Security](/cloud-app-security/what-is-cloud-app-security)| Individua, etichetta e protegge le informazioni riservate che si trovano negli archivi dati nel cloud. | [Individuare, classificare, etichettare e proteggere i dati regolamentati e riservati archiviati nel cloud](/cloud-app-security/best-practices#discover-classify-label-and-protect-regulated-and-sensitive-data-stored-in-the-cloud)|
|[Scanner per l’etichettatura unificata di Azure Information Protection](/azure/information-protection/deploy-aip-scanner)| Consente di individuare, etichettare e proteggere le informazioni riservate che risiedono negli archivi dati locali | [Configurazione e installazione dello scanner di etichettatura unificata di Azure Information Protection.r](/azure/information-protection/deploy-aip-scanner-configure-install)|
|[Esplora attività]()||||


## <a name="transition-from-aip-to-mip"></a>Transizione da AIP a MIP
L'esperienza utente e il client classici di Azure Information Protection sono in fase di deprecazione all'inizio del prossimo anno. Consigliamo passare a Microsoft Information Protection. Ciò comporta la migrazione di tutte le etichette e i criteri esistenti. 

:::image type="content" source="../media/transition-aip2mip-4638524-new.png" alt-text="Transizione da AIP a MIP":::

## <a name="additional-capabilities"></a>Funzionalità aggiuntive
Microsoft 365 include queste funzionalità per proteggere i dati:

|**Funzionalità**|**Che problemi risolve?**|**Introduzione**|
|--|--|--|
| Office 365 Message Encryption (OME) | Consente di crittografare i messaggi di posta elettronica e i documenti allegati inviati a qualsiasi utente da qualsiasi dispositivo, in modo che solo i destinatari autorizzati possano leggere le informazioni di posta elettronica. <br /><br /> Scenario esemplificativo: Revocare un'e-mail crittografata da Advanced Message Encryption | Configurare le nuove funzionalità di Message Encryption |
| Crittografia a chiave doppia | Ad ogni modo, solo tu puoi decrittografare il contenuto protetto o, in base a i requisiti normativi, devi essere in possesso di chiave di crittografia in base a un confine geografico. | Implementa la Crittografia a chiave doppia |  
| Crittografia del servizio con Customer Key | Protegge dalla visualizzazione dei dati da parte di sistemi o personale non autorizzato e integra la crittografia del disco BitLocker nei centri dati di Microsoft. | Configurare il Customer Key per Office 365 |
| Information Rights Management di SharePoint (IRM) | Protegge gli elenchi e le raccolte di SharePoint in modo che, quando un utente estrae un documento, il file scaricato sia protetto e che solo l’utente autorizzato possa visualizzare e usare il file in base ai criteri specificati. | Configurare Information Rights Management (IRM) nell'interfaccia di amministrazione di SharePoint |
| Connettore Rights Management | Protezione solo per le distribuzioni locali esistenti che usano Exchange o SharePoint Server e un'infrastruttura di classificazione file (FCI) | Procedura per distribuire il connettore RMS |



## <a name="prevent-data-loss"></a>Prevenire la perdita di dati

Per evitare la condivisione accidentale di informazioni riservate, usare le funzionalità seguenti:

:::image type="content" source="../media/dlp-4638524-new.png" alt-text="Prevenire la perdita di dati":::

|**Passaggio**|**Descrizione**|**Ulteriori informazioni**|
|--|--|--|
|[Progettare criteri di prevenzione della perdita dei dati](data-loss-prevention-policies.md)| Pianifica la modalità di identificazione delle informazioni (tipo di informazioni riservate, etichetta, altro) <br /><br /> Pianifica la destinazione dei criteri(servizi, client, app di terze parti). <br /><br /> Pianifica i suggerimenti per i criteri, altri||
||||




|**Funzionalità**|**Che problemi risolve?**|**Introduzione**|
|--|--|--|
|[Informazioni sulla prevenzione della perdita dei dati](dlp-learn-about-dlp.md)| Evita la condivisione involontaria di elementi riservati. | [Cominciare con il criterio di prevenzione della perdita dei dati predefinito](get-started-with-the-default-dlp-policy.md)|
|[Informazioni sulla prevenzione della perdita di dati degli endpoint](endpoint-dlp-learn-about.md)| Consente di estendere le funzionalità DLP agli elementi usati e condivisi nei computer con Windows 10. | [Introduzione alla prevenzione della perdita di dati degli endpoint](endpoint-dlp-getting-started.md)|
|[Informazioni sull'Estensione della conformità Microsoft (anteprima)](dlp-chrome-learn-about.md) | Estende le funzionalità DLP al browser Chrome | [Introduzione all'estensione della Conformità Microsoft (anteprima)](dlp-chrome-get-started.md)|
|[Informazioni sullo scanner locale per la prevenzione della perdita dei dati di Microsoft 365 (anteprima)](dlp-on-premises-scanner-learn.md)|Estende il monitoraggio DLP delle attività sui file e le azioni di protezione per tali file nelle condivisioni di file locali, cartelle e raccolte documenti di SharePoint.|[Introduzione allo scanner locale per la prevenzione della perdita dei dati di Microsoft 365 (anteprima)](dlp-on-premises-scanner-get-started.md)|
|[Proteggere le informazioni riservate nella chat e nei messaggi di canale di Microsoft Teams](dlp-microsoft-teams.md) | Estende alcune funzionalità DLP alla chat e ai messaggi di canale di Teams | [Informazioni sul criterio predefinito per la prevenzione della perdita di dati in Microsoft Teams (anteprima)](dlp-teams-default-policy.md)| 


## <a name="additional-resources"></a>Risorse aggiuntive

Molte organizzazioni usano queste funzionalità di protezione delle informazioni per conformarsi alle normative sulla privacy dei dati. A tale scopo, è stato progettato un flusso di lavoro che fornisce una guida attraverso il processo end-to end di pianificazione e implementazione delle funzionalità in Microsoft 365, tra cui accesso sicuro, protezione dalla minacce, protezione delle informazioni e governance dei dati. Per ulteriori informazioni, vedere [Distribuire la protezione delle informazioni per le normative sulla privacy dei dati con Microsoft 365](../solutions/information-protection-deploy.md) (aka.ms/m365dataprivacy). 

Inoltre, per pianificare una strategia integrata per l'implementazione delle funzionalità di protezione delle informazioni, scaricare *Funzionalità di conformità e protezione delle informazioni di Microsoft 365*.  Queste illustrazioni possono essere personalizzate.

| Elemento | Descrizione |
|:-----|:------------|
|[![Modello poster: Capacità della Conformità e protezione delle informazioni di Microsoft 365](../media/solutions-architecture-center/m365-compliance-illustrations-thumb.png)](https://download.microsoft.com/download/3/a/6/3a6ab1a3-feb0-4ee2-8e77-62415a772e53/m365-compliance-illustrations.pdf) <br/> [Scarica come PDF](https://download.microsoft.com/download/3/a/6/3a6ab1a3-feb0-4ee2-8e77-62415a772e53/m365-compliance-illustrations.pdf)  \| [Scarica come Visio](https://download.microsoft.com/download/3/a/6/3a6ab1a3-feb0-4ee2-8e77-62415a772e53/m365-compliance-illustrations.vsdx) <br/> Giapponese: [Scarica come PDF](https://download.microsoft.com/download/6/f/1/6f1a7d0e-dd8e-442e-b073-8e94327ae4f8/m365-compliance-illustrations.pdf)  \| [Scarica come Visio](https://download.microsoft.com/download/6/f/1/6f1a7d0e-dd8e-442e-b073-8e94327ae4f8/m365-compliance-illustrations.vsdx) <br/> Ultimo aggiornamento: ottobre 2020|Include: <ul><li>  Protezione dell’informazione e prevenzione della perdita dei dati di Microsoft</li><li>Criteri di conservazione ed etichette di conservazione. </li><li>Barriere informative</li><li>Conformità delle comunicazioni</li><li>Gestione dei rischi Insider</li><li>Inserimento dei dati di terze parti</li>|

