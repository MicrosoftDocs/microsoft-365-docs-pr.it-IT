---
title: Introduzione allo scanner per la prevenzione della perdita dei dati locali di Microsoft 365 (anteprima)
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: how-to
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
description: Configurare lo scanner per la prevenzione della perdita dei dati locali di Microsoft 365
ms.openlocfilehash: b21474f3a9e045bf353d62ef6c7c8d4174801a1b
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/24/2021
ms.locfileid: "52623834"
---
# <a name="get-started-with-the-data-loss-prevention-on-premises-scanner-preview"></a>Introduzione allo scanner per la prevenzione della perdita dei dati locali (anteprima)

Questo articolo illustra i prerequisiti e la configurazione dello scanner di Microsoft 365 per la prevenzione della perdita dei dati locali.

## <a name="before-you-begin"></a>Informazioni preliminari

### <a name="skusubscriptions-licensing"></a>Licenze per SKU/abbonamenti

Prima di iniziare a usare lo scanner per la prevenzione della perdita dei dati locali, è necessario confermare l'[abbonamento a Microsoft 365](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) e gli eventuali componenti aggiuntivi. Per partecipare all'anteprima, bisogna assegnare una delle seguenti licenze all'account amministratore che configura le regole per la prevenzione della perdita dei dati:

- Microsoft 365 E5
- Conformità Microsoft 365 E5
- Microsoft 365 E5 Information Protection & Governance 


Per altre informazioni sulle licenze complete, vedere [Indicazioni sulla gestione delle licenze di Microsoft 365 per la sicurezza e la conformità](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).

### <a name="permissions"></a>Autorizzazioni


I dati provenienti dallo scanner per la prevenzione della perdita dei dati locali possono essere visualizzati in [Esplora attività](data-classification-activity-explorer.md). Sono disponibili quattro ruoli che concedono l'autorizzazione per Esplora attività, l'account usato per accedere ai dati deve essere membro di uno di essi.

- Amministratore globale
- Amministratore di conformità
- Amministratore della sicurezza
- Amministratore dati di conformità

### <a name="dlp-on-premises-scanner-prerequisites"></a>Prerequisiti scanner per la prevenzione della perdita dei dati locali

- Lo scanner Azure Information Protection (AIP) implementa la corrispondenza e l’applicazione dei criteri di prevenzione della perdita dei dati. Lo scanner viene installato come parte del client AIP. Pertanto l'installazione deve soddisfare tutti i prerequisiti di AIP, del client AIP e dello scanner di etichette unificato AIP.
- Distribuire il client e lo scanner AIP. Per ulteriori informazioni vedere [Installare il client di etichettatura unificata AIP](/azure/information-protection/rms-client/install-unifiedlabelingclient-app) e [][Configurazione e installazione dello scanner di etichettatura unificata di Azure Information Protection](/azure/information-protection/deploy-aip-scanner-configure-install).
- È necessario che almeno un'etichetta e un criterio siano pubblicati nel tenant, anche se tutte le regole di rilevamento sono basate solo su tipi di informazioni riservate.

## <a name="deploy-the-dlp-on-premises-scanner"></a>Distribuire lo scanner per la prevenzione della perdita dei dati locali

1. Seguire le procedure descritte in [Installare il client di etichettatura unificato AIP](/azure/information-protection/rms-client/install-unifiedlabelingclient-app). 
2. Per completare l’installazione dello scanner, seguire le procedure descritte in [Configurazione e installazione dello scanner di etichettatura unificata Azure Information Protection](/azure/information-protection/deploy-aip-scanner-configure-install)
    1. La configurazione delle attività di individuazione della rete è un passaggio facoltativo. È possibile questo passaggio e definire archivi specifici da analizzare nel processo di analisi del contenuto.
    2. È necessario creare un processo di analisi del contenuto e specificare gli archivi che ospitano i file che devono essere valutati dal motore di prevenzione della perdita dei dati.
    3. Abilitare le regole per la prevenzione della perdita dei dati nel processo di analisi del contenuto creato e impostare l'opzione **Applica** su **Disattivato**, a meno che non si desideri procedere direttamente alla fase di applicazione di prevenzione della perdita dei dati.
3. Verificare che il processo di analisi del contenuto sia assegnato al cluster corretto. Se ancora non è stato creato un processo di analisi del contenuto, crearne uno nuovo e assegnarlo al cluster che contiene i nodi dello scanner che eseguono la versione di anteprima pubblica.

4. Connettersi all'[estensione Azure Information Protection nel portale di Azure](https://portal.azure.com/#blade/Microsoft_Azure_InformationProtection/DataClassGroupEditBlade/scannerProfilesBlade) e aggiungere gli archivi al processo di analisi del contenuto il quale eseguirà l'analisi.

5. Per avviate l'analisi, eseguire una delle seguenti operazioni:
    1. impostare la pianificazione dello scanner
    1. usare l'opzione presente nel portale **Analizza ora**
    1. o eseguire il cmdlet **Start-AIPScan** di PowerShell

   > [!IMPORTANT]
   > Bisogna tenere presente che lo scanner esegue per impostazione predefinita un'analisi delta dell’archivio e i file già analizzati nel ciclo di analisi precedente vengono ignorati, a meno che il file non sia stato modificato o non sia stata avviata una nuova analisi completa. È possibile eseguire una nuova analisi completa selezionando **Riesegui l’analisi di tutti i file** nell'interfaccia utente oppure eseguendo **Start-AIPScan-Reset**.

6.  Aprire la [pagina Prevenzione della perdita dei dati](https://compliance.microsoft.com/datalossprevention?viewid=policies) nel centro conformità Microsoft 365.

7. Scegliere **Crea criterio** e creare un criterio di prevenzione della perdita dei dati di test. Vedere [Creare un criterio di prevenzione della perdita dei dati da un modello](create-a-dlp-policy-from-a-template.md) se occorre assistenza per la creazione di un criterio. Assicurarsi di eseguire questa funzionalità in un ambiente test finché non si ha piena familiarità. Usare questi parametri per i criteri:
    1. Impostare l'ambito della regola dello scanner locale dei criteri di prevenzione della perdita dei dati in posizioni specifiche, se necessario. Se l’ambito dei **percorsi** viene definito su **Tutti**, tutti i file analizzati saranno soggetti alla corrispondenza e all'applicazione delle regole di prevenzione della perdita dei dati.
    1. Quando si specificano i percorsi, è possibile usare l'elenco di esclusione o inclusione. Durante l'anteprima pubblica non è possibile impostarli entrambi. È possibile definire che la regola sia rilevante solo per i percorsi che corrispondono a uno dei modelli elencati nell'elenco di inclusione o, per tutti i file, ad eccezione dei file che corrispondono al modello elencato nell'elenco di inclusione. Non sono supportati percorsi locali. Ecco alcuni esempi di percorsi validi:
      - \\\server\share
      - \\\server\share\folder1\subfolderabc
      - \*\\folder1
      - \*secret\*.docx
      - \*secret\*.\*
      - https:// sp2010.local/sites/HR
      - https://\*/HR 
    3. Di seguito sono riportati alcuni esempi di valori non validi:
      - \*
      - \*\\a
      - Aaa
      - c:\
      - C:\test

> [!IMPORTANT]
> L'elenco di esclusione ha la precedenza sull'elenco di inclusione.

### <a name="viewing-dlp-on-premises-scanner-alerts-in-dlp-alerts-management-dashboard"></a>Visualizzazione degli avvisi dello scanner per la prevenzione della perdita dei dati locali nella dashboard di gestione degli avvisi prevenzione della perdita dei dati

1. Aprire la [pagina di Prevenzione della perdita dei dati](https://compliance.microsoft.com/datalossprevention?viewid=policies) nel centro conformità Microsoft 365 e scegliere **Avvisi**.

2. Fare riferimento alle procedure in [Come configurare e visualizzare gli avvisi per i criteri di prevenzione della perdita dei dati](dlp-configure-view-alerts-policies.md) per visualizzare gli avvisi per i criteri di prevenzione della perdita dei dati degli endpoint.

### <a name="viewing-dlp-on-premises-scanner-in-activity-explorer-and-audit-log"></a>Visualizzazione dello scanner dei criteri di prevenzione della perdita dei dati locali in Esplora attività e nel registro di controllo

> [!NOTE]
> Lo scanner locale richiede che il controllo sia abilitato. In Microsoft 365 il controllo è abilitato per impostazione predefinita.

1. Aprire la pagina [Classificazione dei dati](https://compliance.microsoft.com/dataclassification?viewid=overview) per il proprio dominio nel Centro conformità Microsoft 365 e scegliere Esplora attività.

2. Fare riferimento alle procedure in [Introduzione a Esplora attività](data-classification-activity-explorer.md) per accedere a tutti i dati relativi allo scanner per la prevenzione della perdita dei dati locale e filtrarli.

3. Aprire il [registro di controllo nel Centro conformità](https://security.microsoft.com/auditlogsearch). Durante l'anteprima pubblica, le corrispondenze alle regole di prevenzione della perdita dei dati sono disponibili nell'interfaccia utente del registro di controllo o sono accessibili da [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog?view=exchange-ps) di PowerShell 


## <a name="next-steps"></a>Passaggi successivi
Dopo aver distribuito i criteri di test per i percorsi di prevenzione della perdita dei dati locali e aver visualizzato i dati delle attività in Esplora attività, è possibile passare al passaggio successivo, in cui si creano i criteri di prevenzione della perdita dei dati per proteggere gli elementi sensibili.

- [Uso dei criteri di prevenzione della perdita dei dati locali (anteprima)](dlp-on-premises-scanner-use.md)

## <a name="see-also"></a>Vedere anche

- [Informazioni sullo scanner per la prevenzione della perdita dei dati locali (anteprima)](dlp-on-premises-scanner-learn.md)
- [Usare lo scanner per la prevenzione della perdita dei dati locali (anteprima)](dlp-on-premises-scanner-use.md)
- [Informazioni sulla prevenzione della perdita dei dati](dlp-learn-about-dlp.md)
- [Creare, testare e ottimizzare un criterio di prevenzione della perdita dei dati](create-test-tune-dlp-policy.md)
- [Introduzione a Esplora attività](data-classification-activity-explorer.md)
- [Abbonamento a Microsoft 365](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)