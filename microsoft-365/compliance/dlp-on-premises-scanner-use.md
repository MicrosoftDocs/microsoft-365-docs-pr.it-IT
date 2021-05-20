---
title: Usare lo scanner locale per la prevenzione della perdita dei dati di Microsoft 365 (anteprima)
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
description: Informazioni su come usare la prevenzione della perdita dei dati di Microsoft 365 nello scanner locale per analizzare i dati inattivi e implementare azioni di protezione per le condivisioni di file locali e le cartelle e raccolte documenti di SharePoint locali.
ms.openlocfilehash: e81b48560a8011e955e6508daf27e96f9fdb70fa
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538088"
---
# <a name="use-the-microsoft-365-data-loss-prevention-on-premises-scanner-preview"></a>Usare lo scanner locale per la prevenzione della perdita dei dati di Microsoft 365 (anteprima)

Per acquisire familiarità con le funzionalità locali di prevenzione della perdita dei dati (DPL) e su come vengono visualizzate nei criteri DLP, sono stati predisposti alcuni scenari da seguire.

> [!IMPORTANT]
> Questi scenari locali DLP non costituiscono le procedure ufficiali per la creazione e l'ottimizzazione di criteri DLP. Vedere gli argomenti seguenti quando è necessario usare i criteri di prevenzione della perdita dei dati in situazioni generiche:
>- [Informazioni sulla prevenzione della perdita di dati](dlp-learn-about-dlp.md)
>- [Cominciare con il criterio di prevenzione della perdita dei dati predefinito](get-started-with-the-default-dlp-policy.md)
>- [Creare un criterio di prevenzione della perdita dei dati da un modello](create-a-dlp-policy-from-a-template.md)
>- [Creare, testare e ottimizzare un criterio di prevenzione della perdita dei dati](create-test-tune-dlp-policy.md)

### <a name="scenario-discover-files-matching-dlp-rules"></a>Scenario: individuare i file che corrispondono alle regole di prevenzione della perdita dei dati

I dati dello scanner locale DPL vengono visualizzati in diverse aree

#### <a name="activity-explorer"></a>Esplora attività

 La prevenzione della perdita dei dati Microsoft per le soluzioni locali rileva le corrispondenze DPL e le segnala a [Esplora attività](https://compliance.microsoft.com/dataclassification?viewid=activitiesexplorer). 
 
#### <a name="microsoft-365-audit-log"></a>Log di audit Microsoft 365

Durante l'anteprima pubblica, le corrispondenze delle regole DPL sono disponibili nell'interfaccia utente del log di audit, vedere [Individuare i log di audit nel Centro conformità](search-the-audit-log-in-security-and-compliance.md) o accessibili tramite PowerShell [Search UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog?view=exchange-ps).

#### <a name="aip"></a>AIP

I dati di individuazione sono disponibili in un report locale in formato CSV archiviato in:

**%localappdata%\Microsoft\MSIP\Scanner\Reports\DetailedReport_%timestamp%.csv report**.

 Cercare le colonne seguenti:
- Modalità DPL
- Stato DPL
- Commento DPL
- Nome delle regole DPL per azioni DPL
- Proprietario
- Autorizzazioni NTFS correnti (SDDL)
- Autorizzazioni NTFS applicate (SDDL)
- Tipo di autorizzazioni NTFS
 
### <a name="scenario-enforce-dlp-rule"></a>Scenario: applicazione delle regole di prevenzione della perdita dei dati 

Per applicare le regole DPL ai file analizzati, occorre abilitare l'applicazione sia nel processo di analisi dei contenuti in AIP che a livello di criteri in DLP.


#### <a name="configure-dlp-to-enforce-policy-actions"></a>Configurare la prevenzione della perdita dei dati per l'applicazione delle azioni dei criteri

1. Aprire la [pagina della Prevenzione della perdita dei dati](https://compliance.microsoft.com/datalossprevention?viewid=policies) e selezionare i criteri DPL destinati ai repository delle posizioni locali configurati in AIP. 
2. Modificare il criterio.
3. Nella pagina **Testare o abilitare il criterio** selezionare **Sì, abilitalo immediatamente**. 

## <a name="see-also"></a>Vedere anche

- [Informazioni sullo scanner locale per la prevenzione della perdita dei dati (anteprima)](dlp-on-premises-scanner-learn.md)
- [Introduzione allo scanner DPL locale (anteprima)](dlp-on-premises-scanner-get-started.md)
- [Informazioni sulla prevenzione della perdita dei dati](dlp-learn-about-dlp.md)
- [Creare, testare e ottimizzare un criterio di prevenzione della perdita dei dati](create-test-tune-dlp-policy.md)
- [Introduzione a Esplora attività](data-classification-activity-explorer.md)