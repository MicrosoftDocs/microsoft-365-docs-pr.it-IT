---
title: "Passaggio 2: configurare la classificazione dell'ambiente"
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Comprendere e configurare i diversi modi per classificare i dati all'interno dell'organizzazione.
ms.openlocfilehash: bee0885eb3f8899560532895d1558723b281ab02
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868477"
---
# <a name="step-2-configure-classification-for-your-environment"></a>Passaggio 2: configurare la classificazione dell'ambiente

*Questo passaggio è facoltativo e si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

In questo passaggio, si lavora con i team di conformità e legali per definire uno schema di classificazione dei dati dell'organizzazione.

## <a name="microsoft-classifications"></a>Classificazioni Microsoft

Microsoft 365 include tre tipi di classificazione:

- Tipi di informazioni riservate di Office 365
- Etichette di Office 365
- Le etichette e protezione di Azure Information Protection

### <a name="sensitive-information-types-for-office-365"></a>Tipi di informazioni riservate di Office 365

I tipi di informazioni riservate di Office 365 definiscono in che modo i processi automatizzati come la ricerca di tipi di informazioni specifici riconosciuti quali i numeri di previdenza sociale e di carte di credito. I tipi di informazioni riservate si usano per trovare dati riservati e applicare regole e criteri per la prevenzione della perdita di dati per proteggere tali dati. Per ulteriori informazioni, vedere [Panoramica dei criteri di prevenzione della perdita dei dati](https://support.office.com/article/overview-of-data-loss-prevention-policies-1966b2a7-d1e2-4d92-ab61-42efbb137f5e). Ad esempio, i tipi di informazioni riservate sono particolarmente utili per soddisfare requisiti di conformità e normativi, come il Regolamento generale sulla protezione dei dati (GDPR).

### <a name="office-365-labels"></a>Etichette di Office 365
È possibile utilizzare le etichette di Office 365 per i dati personali e per i file con segreti commerciali soggetti a normative in SharePoint Online e OneDrive for Business. Per ulteriori informazioni, anche su come crearle, vedere [Panoramica delle etichette](https://support.office.com/article/overview-of-labels-af398293-c69d-465e-a249-d74561552d30).

Se si decide di usare le etichette di Office 365, è necessario configurarne almeno una per ogni livello di protezione. Ad esempio, creare tre etichette per:

- Protezione di base
- Dati sensibili
- Protezione per ambienti altamente regolamentati

### <a name="azure-information-protection-labels-and-protection"></a>Le etichette e protezione di Azure Information Protection

È possibile usare le etichette di Azure Information Protection per classificare e facoltativamente proteggere documenti e messaggi di posta elettronica dell'organizzazione. Le etichette si possono applicare ai documenti archiviati all'esterno di Office 365. Le etichette possono essere applicate automaticamente dagli amministratori che definiscono le regole e condizioni, manualmente dagli utenti o in modo combinato in cui agli utenti vengono fornite indicazioni.

Per pianificare e distribuire le etichette e la protezione di Azure Information Protection, eseguire quanto segue:

1. Esaminare i [requisiti di Azure Information Protection](https://docs.microsoft.com/information-protection/get-started/requirements).
2. Seguire la [guida di orientamento per la distribuzione delle funzionalità di classificazione, assegnazione di etichette e protezione](https://docs.microsoft.com/information-protection/plan-design/deployment-roadmap#deployment-roadmap-for-classification-labeling-and-protection).

Per ulteriori informazioni, vedere la [raccolta della documentazione di Azure Information Protection](https://docs.microsoft.com/information-protection/).

## <a name="classification-for-gdpr"></a>Classificazione del GDPR

Per uno schema di classificazione di esempio contenente dati personali in base al GDPR, vedere [Progettare uno schema di classificazione per i dati personali](https://docs.microsoft.com/office365/enterprise/architect-a-classification-schema-for-personal-data).

|||
|:-------|:-----|
|![Guide al lab di test per il cloud Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Guida del laboratorio di testing: classificazione dei dati](data-classification-microsoft-365-enterprise-dev-test-environment.md) |
|||

Come checkpoint provvisorio, vedere i [criteri uscita](infoprotect-exit-criteria.md#crit-infoprotect-step3) che corrispondono a questo passaggio.

## <a name="next-step"></a>Passaggio successivo

|||
|:-------|:-----|
|![](./media/stepnumbers/Step3.png)|[Configurare un livello di sicurezza maggiore per Office 365](infoprotect-configure-increased-security-office-365.md)|

