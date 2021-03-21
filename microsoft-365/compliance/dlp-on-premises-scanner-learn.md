---
title: Informazioni sullo scanner locale per la prevenzione della perdita dei dati di Microsoft 365 (anteprima)
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
description: La prevenzione della perdita dei dati di Microsoft 365 nello scanner locale estende il monitoraggio delle attività sui file e le azioni di protezione per tali file nelle condivisioni di file locali e cartelle e raccolte documenti di SharePoint locali. I file vengono analizzati e protetti tramite uno scanner di Azure Information Protection (AIP)
ms.openlocfilehash: fa1c14520c8ad0afa4856fdd8a1c59a0f71f400d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917812"
---
# <a name="learn-about-the-microsoft-365-data-loss-prevention-on-premises-scanner-preview"></a>Informazioni sullo scanner locale per la prevenzione della perdita dei dati di Microsoft 365 (anteprima)

Lo scanner locale per la prevenzione della perdita dei dati Microsoft fa parte della famiglia di funzionalità di prevenzione della perdita dei dati (DLP) di Microsoft 365 che è possibile usare per individuare e proteggere gli elementi sensibili nei servizi di Microsoft 365. Per altre informazioni su tutte le offerte DLP Microsoft, vedere [Panoramica della prevenzione della perdita dei dati](data-loss-prevention-policies.md).

Lo **scanner locale DPL** esegue una ricerca per indicizzazione dei dati locali in archivio nelle condivisioni file e nelle raccolte documenti e nelle cartelle di SharePoint per trovare elementi sensibili che, in caso di divulgazione, rappresentano un rischio per l'organizzazione o rappresentano un rischio di violazione dei criteri di conformità. In questo modo si ottengono la visibilità e il controllo necessari per assicurarsi che gli elementi sensibili vengano usati e protetti correttamente e per evitare comportamenti rischiosi che potrebbero comprometterli. Lo scanner DPL locale rileva le informazioni riservate usando [tipi di informazioni integrate](sensitive-information-type-entity-definitions.md) o [informazioni](create-a-custom-sensitive-information-type.md) riservate personalizzate, [etichette di riservatezza](sensitivity-labels.md) o proprietà dei file. Le informazioni sulle azioni che gli utenti stanno eseguendo sugli elementi sensibili sono rese visibili in [esplora attività](data-classification-activity-explorer.md) ed è possibile applicare azioni di protezione su tali elementi tramite [criteri DLP](create-test-tune-dlp-policy.md).

## <a name="the-dlp-on-premises-scanner-relies-on-azure-information-protection-scanner"></a>Lo scanner locale DPL si basa su uno scanner di Azure Information Protection

Lo scanner locale DPL si basa su un'implementazione completa dello scanner Azure Information Protection (AIP) per monitorare, etichettare e proteggere gli elementi sensibili. Se non si ha familiarità con lo scanner AIP, è consigliabile familiarizzare con esso. Vedere questi articoli:

- [Che cos'è Azure Information Protection?](/azure/information-protection/what-is-information-protection)
- [Che cos’è lo scanner di etichettatura unificata di Azure Information Protection](/azure/information-protection/deploy-aip-scanner)
- [Requisiti per l’installazione e la distribuzione dello scanner di etichettatura unificata di Azure Information Protection](/azure/information-protection/deploy-aip-scanner-prereqs)
- [Esercitazione: installazione dello scanner di etichettatura unificata di Azure Information Protection](/azure/information-protection/tutorial-install-scanner)
- [Configurazione e installazione dello scanner di etichettatura unificata di Azure Information Protection](/azure/information-protection/deploy-aip-scanner-configure-install)
- [Client di etichettatura unificata di Azure Information Protection - Cronologia di rilascio delle versioni e criteri di supporto](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)

## <a name="dlp-on-premises-scanner-actions"></a>Azioni dello scanner locale DPL

Uno scanner locale DPL rileva i file con uno di questi quattro metodi:

- tipi di informazioni sensibili
- etichette di riservatezza
- estensione del file
- proprietà dei documenti personalizzati solo nei file di Office 

Quando un file rilevato rappresenta un potenziale rischio in caso di perdita o di violazione di criteri di conformità, lo scanner DPL locale può eseguire una di queste quattro azioni.

|Azione |Descrizione  |
|---------|---------|
|**Impedire a queste persone di accedere ai file archiviati nello scanner locale - Tutti** | Se applicata, questa azione blocca l'accesso a tutti gli account, a eccezione del proprietario del contenuto, dell'ultimo account che ha modificato l'elemento e dell'amministratore. Questo viene ottenuto rimuovendo tutti gli account dalle autorizzazioni NTFS/SharePoint a livello di file tranne il proprietario del file, il proprietario del repository (con 'impostazione [Imposta proprietario repository](/azure/information-protection/deploy-aip-scanner-configure-install#use-a-data-loss-prevention-dlp-policy-public-preview) nel processo di analisi del contenuto), l'ultimo modificatore (può essere identificato solo in SharePoint) e l'amministratore. All'account dello scanner vengono concessi anche i diritti FC sul file.|
|**Impedire a queste persone di accedere ai file archiviati nello scanner locale - bloccare l'accesso a livello di organizzazione (pubblico)**    |Se applicata, questa azione rimuove i SID **_Tutti gli_*_, _*_NT AUTHORITY\authenticated users_*_, e _*_Domain Users_** dall'elenco di controllo di accesso file (ACL). Solo gli utenti e i gruppi a cui sono stati esplicitamente concessi diritti per il file o la cartella padre potranno accedere al file.|
|**Impostare le autorizzazioni nel file**|Quando viene applicata, questa azione forza il file a ereditare le autorizzazioni della relativa cartella padre. Per impostazione predefinita, questa azione verrà applicata solo se le autorizzazioni nella cartella padre sono più restrittive rispetto alle autorizzazioni già presenti nel file. Ad esempio, se l'elenco ACL del file è impostato per consentire solo **_utenti specifici_*_ e la cartella padre è configurata per consentire _*_Domain Users_*_ group, le autorizzazioni per la cartella padre non vengono ereditate dal file. È possibile ignorare questo comportamento selezionando l'opzione _* Eredita anche se le autorizzazioni padre sono meno restrittive per**.|
|**Rimuovere il file da una posizione non corretta**|Se viene applicata, questa azione sostituisce il file originale con un file di stub con estensione txt e inserisce una copia del file originale in una cartella di quarantena. 

## <a name="whats-different-in-the-on-premises-scanner"></a>Cosa c'è di diverso nello scanner locale

Ci sono alcuni concetti aggiuntivi che è necessario conoscere prima di approfondire l'utilizzo dello scanner locale.

### <a name="aip-repositories-and-content-scan-jobs"></a>Archivi AIP e processi di analisi del contenuto

È necessario creare un processo di analisi del contenuto AIP e identificare gli archivi che ospitano i file che si desidera essere valutati dal motore DPL. Assicurarsi di abilitare le regole DLP nel processo di analisi del contenuto AIP creato.

### <a name="policy-tips"></a>Suggerimenti per i criteri

[I suggerimenti per i criteri](use-notifications-and-policy-tips.md) non sono disponibili nello scanner locale.


### <a name="viewing-dlp-on-premises-scanner-events"></a>Visualizzare eventi dello scanner locale DLP

È possibile visualizzare i dati dello scanner locale DPL nel Centro conformità M365 [esplora attività](data-classification-activity-explorer.md). 

## <a name="next-steps"></a>Passaggi successivi

Dopo avere acquisito familiarità con lo scanner locale DLP, è possibile proseguire con questi argomenti:

1. [Introduzione allo scanner locale DPL (anteprima)](dlp-on-premises-scanner-get-started.md)
2. [Usare lo scanner locale DLP](dlp-on-premises-scanner-use.md)

## <a name="see-also"></a>Vedere anche

- [Introduzione allo scanner locale per la prevenzione della perdita dei dati di Microsoft](dlp-on-premises-scanner-get-started.md)
- [Usare lo scanner locale per la prevenzione della perdita dei dati di Microsoft](dlp-on-premises-scanner-use.md) 
- [Panoramica sulla prevenzione della perdita dei dati](data-loss-prevention-policies.md)
- [Creare, testare e ottimizzare un criterio di prevenzione della perdita dei dati](create-test-tune-dlp-policy.md)
- [Introduzione a Esplora attività](data-classification-activity-explorer.md)