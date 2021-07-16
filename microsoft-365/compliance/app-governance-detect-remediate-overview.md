---
title: Informazioni sul rilevamento e la correzione delle minacce di app
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: Informazioni sul rilevamento e la correzione delle minacce di app.
ms.openlocfilehash: 26cd8501fdd8bd828357f8adb7d4e90f96e70114
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420328"
---
# <a name="learn-about-app-threat-detection-and-remediation"></a>Informazioni sul rilevamento e la correzione delle minacce di app

>*[Indicazioni sulle licenze di Microsoft 365 per la sicurezza e la conformità](https://aka.ms/ComplianceSD).*

Con la governance delle app di Microsoft, è possibile:

- Monitorare con facilità gli avvisi delle minacce generati dai metodi predefiniti di rilevamento della governance per le attività dannose delle app e per avvisi basati su criteri generati dai criteri attivi delle app creati dall'utente. Questi avvisi possono indicare anomalie nell'attività dell'app e l’utilizzo di app non conformi, dannose o rischiose.  È anche possibile usare modelli negli avvisi per creare nuovi criteri delle app o modificare le impostazioni dei criteri esistenti per azioni più restrittive.
- Correggi facilmente gli avvisi manualmente dopo l’analisi o automaticamente tramite le impostazioni delle azioni sui criteri delle app attive.


>[!Note]
>Le attività anomale delle app esclusive di Azure, a cui non sono concesse le autorizzazioni necessarie per accedere alle risorse Microsoft 365, non vengono incluse nel rilevamento e invio degli avvisi della governance delle app.
>

Vedere i [ruoli di amministratore](app-governance-get-started.md#administrator-roles) per sapere quali ruoli possono accedere alle pagine di governance delle app.


## <a name="app-governance-integration-with-azure-active-directory-and-microsoft-cloud-app-security"></a>Integrazione della governance delle app con Azure Active Directory e Microsoft Cloud App Security

Governance delle app, Azure Active Directory (Azure AD) e Microsoft Cloud App Security raccolgono e forniscono insiemi di dati diversi:

- Azure AD fornisce metadati di base dell’app e informazioni dettagliate sugli accessi alle app.
- La governance delle app fornisce informazioni dettagliate sull'attività di un'app a livello di API.
- Microsoft Cloud App Security fornisce informationi sul rischio dell’app.

Condividendo le informazioni tra governance delle app, Azure AD e Microsoft Cloud App Security, è possibile visualizzare informazioni aggregate in un portale e collegarsi facilmente a un altro portale per altre informazioni. Ecco alcuni esempi:

- Informazioni di accesso alle app nella governance delle app:

  Dal portale di governance delle app è possibile visualizzare l’attività di accesso aggregata per ogni app e collegarsi all’interfaccia di amministrazione di Azure Active Directory per i dettagli degli eventi di accesso.

- Informazioni di utilizzo all’API dell’app nell'interfaccia di amministrazione di Azure Active Directory:

  Dall’interfaccia di amministrazione di Azure Active Directory è possibile visualizzare le informazioni aggregate sull’utilizzo delle app e collegarsi al portale di governance delle app per i dettagli sull’utilizzo delle applicazioni.

- Informazioni sull’utilizzo dell'API nel portale di Microsoft Cloud App Security: 

  Dal portale di Microsoft Cloud App Security è possibile visualizzare il livello di utilizzo dell'API e aggregare il trasferimento dei dati e collegarsi al portale di governance delle app per i dettagli.

Di seguito è riportato un riepilogo dell’integrazione.

![Integrazione della governance delle app con Azure Active Directory e Microsoft Cloud App Security](..\media\manage-app-protection-governance\mapg-integration.png)

Inoltre, la governance delle app invia i propri avvisi come segnali a Microsoft Cloud App Security e Microsoft 365 Defender per un'analisi più dettagliata degli eventi imprevisti di sicurezza basati su app.

<!--

CFA #3 Scenario 1:  As an admin, I can investigate alerts associated to my M365 apps through MAPG.
CFA #3 Scenario 2: As an admin, I can manually remediate 
CFA #3 Scenario 3: As an admin, I can configure policies to perform automatic 
--> 

## <a name="next-step"></a>Passaggio successivo

[Introduzione al rilevamento e alla correzione delle minacce dell'app.](app-governance-detect-remediate-get-started.md)
