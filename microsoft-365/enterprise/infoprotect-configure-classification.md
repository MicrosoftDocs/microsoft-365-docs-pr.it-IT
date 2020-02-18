---
title: "Passaggio 2: configurare la classificazione dell'ambiente"
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Comprendere e configurare i diversi modi per classificare i dati all'interno dell'organizzazione.
ms.openlocfilehash: e8c40ca4c419edc2d59a060dfd4fe8918cf4e784
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42067253"
---
# <a name="step-2-configure-classification-for-your-environment"></a>Passaggio 2: configurare la classificazione dell'ambiente

*Questo passaggio è facoltativo e si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*

![Fase 6: protezione delle informazioni](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

In questo passaggio, si lavora con i team di conformità e legali per definire uno schema di classificazione dei dati dell'organizzazione.

## <a name="microsoft-365-classification-types"></a>Tipi di classificazione Microsoft 365

Microsoft 365 include quattro tipi di classificazione:

- Tipi di informazioni riservate
- Etichette di conservazione
- Etichette di riservatezza
- Etichette e protezione di Azure Information Protection

### <a name="sensitive-information-types"></a>Tipi di informazioni riservate

I tipi di informazioni riservate per Microsoft 365 definiscono come i processi automatici, quali ad esempio la ricerca, riconoscono i tipi di informazioni specifiche. Includono i dati riservati dei dipendenti o dei clienti, come ad esempio numeri del servizio sanitario e numeri di carta di credito. Utilizzare i tipi di informazioni riservate per trovare i dati riservati e applicare regole di prevenzione della perdita di dati (DLP) e criteri per proteggere i dati. Per ulteriori informazioni, vedere [Contenuto di un criterio DLP](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies#what-a-dlp-policy-contains). 

I tipi di informazioni riservate sono particolarmente utili per soddisfare i requisiti di conformità e delle normative, ad esempio per il GDPR (Regolamento generale sulla protezione dei dati)

### <a name="retention-labels"></a>Etichette di conservazione

Parte della definizione di una strategia di gestione dati è decidere il periodo di conservazione di specifici tipi di documenti o documenti con contenuti specifici in conformità con i criteri dell'organizzazione e le normative locali. Ad esempio, alcuni tipi di documento devono essere conservati per un determinato periodo di tempo e quindi eliminati e altri devono essere conservati a tempo indefinito.

Per i documenti archiviati in Microsoft 365, si definiscono e applicano le etichette di conservazione ai documenti e ai dati archiviati in posta elettronica di Exchange, SharePoint Online, OneDrive for Business e i messaggi di chat Teams e di canali. 

Se si usano le etichette di conservazione, è necessario configurare un'etichetta per ogni categoria di file a cui deve essere applicato un criterio di conservazione. All'interno dell'etichetta di conservazione è possibile specificare:

- Un insieme di descrittori per i file (ad esempio, per reparto aziendale, categoria file o normative).
- Le impostazioni di conservazione per i file con l'etichetta di conservazione, ad esempio gestione tempi e comportamenti una volta raggiunto il tempo di conservazione.

È anche possibile applicare un'etichetta di conservazione ai file automaticamente quando si configura un sito di SharePoint Online per applicare un'etichetta di conservazione predefinita per tutti i nuovi documenti del sito. 

Per ulteriori informazioni, vedere la [Panoramica delle etichette di conservazione](https://docs.microsoft.com/office365/securitycompliance/labels).

### <a name="sensitivity-labels"></a>Etichette di riservatezza

Parte della protezione e dell’implementazione della sicurezza per specifici tipi di documenti e documenti con contenuti specifici consiste nel contrassegnarli con un'etichetta in modo che possa essere applicata la sicurezza aggiuntiva. Con le etichette di riservatezza Microsoft 365 è possibile:

- Applicare le impostazioni di protezione, ad esempio la crittografia, le autorizzazioni o aggiungere una filigrana.
- Usare la protezione di endpoint Windows Information Protection (WIP) per impedire che un contenuto venga copiato da un'applicazione di terze parti, ad esempio Twitter o Gmail, o venga copiato su supporti rimovibili, ad esempio un'unità USB.
- Proteggere i contenuti in app e servizi di terze parti con Microsoft Cloud App Security (CAS). 
- Classificare il contenuto senza usare nessuna impostazione di protezione.

Se si usano le etichette di riservatezza, è necessario configurare un'etichetta per ogni livello di protezione di sicurezza e delle informazioni. Ad esempio, creare tre etichette di riservatezza per:

- Protezione di base
- Dati sensibili
- Riservatezza elevata

Se si archiviano file con dati a riservatezza elevata in un sito di SharePoint Online e si vuole che tali file presentino le stesse autorizzazioni del sito quando lasciano il sito, è necessario creare un'ulteriore etichetta di riservatezza le cui autorizzazioni siano identiche a quelle sito.

Per altre informazioni, vedere questa [Panoramica delle etichette di riservatezza](https://docs.microsoft.com/office365/securitycompliance/sensitivity-labels).

### <a name="azure-information-protection-labels-and-protection"></a>Le etichette e protezione di Azure Information Protection

È possibile usare le etichette di Azure Information Protection per classificare, e facoltativamente proteggere, documenti e messaggi di posta elettronica dell'organizzazione. Queste etichette possono essere applicate ai documenti archiviati all'esterno di Microsoft 365. Queste etichette possono essere applicate automaticamente dagli amministratori che definiscono regole e condizioni, manualmente dagli utenti oppure da entrambi, quando gli utenti ricevono raccomandazioni dagli amministratori.

Per pianificare e distribuire le etichette e la protezione di Azure Information Protection, eseguire quanto segue:

1. Esaminare i [requisiti di Azure Information Protection](https://docs.microsoft.com/information-protection/get-started/requirements).
2. Seguire la [guida di orientamento per la distribuzione delle funzionalità di classificazione, assegnazione di etichette e protezione](https://docs.microsoft.com/information-protection/plan-design/deployment-roadmap#deployment-roadmap-for-classification-labeling-and-protection).

Per ulteriori informazioni, vedere la [raccolta della documentazione di Azure Information Protection](https://docs.microsoft.com/information-protection/).

Le etichette esistenti di Azure Information Protection collaborano facilmente con le etichette di riservatezza. Ad esempio, è possibile mantenere le etichette di Azure Information Protection esistenti e le etichette applicate a documenti e posta elettronica.

Se sono presenti sia riservatezza sia le etichette di Azure Information Protection, è necessario [esegue la migrazione delle etichette di Azure Information Protection a etichette di riservatezza](https://docs.microsoft.com/office365/securitycompliance/sensitivity-labels#how-sensitivity-labels-work-with-existing-azure-information-protection-labels).

## <a name="example-classification-for-gdpr"></a>Esempio: Classificazione del GDPR

Per uno schema di classificazione di esempio contenente dati personali in base al GDPR, vedere [Progettare uno schema di classificazione per i dati personali](https://docs.microsoft.com/office365/enterprise/architect-a-classification-schema-for-personal-data).

## <a name="take-it-for-a-test-drive"></a>Va inteso come un test drive

|||
|:-------|:-----|
|![Guide al lab di test per il cloud Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Guida del laboratorio di testing: classificazione dei dati](data-classification-microsoft-365-enterprise-dev-test-environment.md) |
|||

Come checkpoint provvisorio, vedere i [criteri uscita](infoprotect-exit-criteria.md#crit-infoprotect-step2) che corrispondono a questo passaggio.

## <a name="next-step"></a>Passaggio successivo

|||
|:-------|:-----|
|![Passaggio 3](../media/stepnumbers/Step3.png)|[Configurare un livello di sicurezza maggiore per Office 365](infoprotect-configure-increased-security-office-365.md)|

