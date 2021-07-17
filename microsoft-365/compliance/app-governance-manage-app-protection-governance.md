---
title: Governance delle app in Microsoft 365
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: Implementare le funzionalità di governance delle app di Microsoft per gestire le app.
ms.openlocfilehash: 63bd6684bc041c3c82ba6b8ddcc28c2600182b26
ms.sourcegitcommit: 997a21b83795789cda0a6b4a77f9985a3233d0c0
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2021
ms.locfileid: "53430697"
---
# <a name="app-governance-add-on-to-microsoft-cloud-app-security-in-preview"></a>Componente aggiuntivo di governance delle app a Microsoft Cloud App Security (in anteprima)

>*[Indicazioni per l'assegnazione di licenze di Microsoft 365 per sicurezza e conformità](https://aka.ms/ComplianceSD).*

Gli attacchi informatici sono diventati sempre più sofisticati nei modi in cui sfruttano le app distribuite nelle infrastrutture locali e cloud, stabilendo un punto di partenza per l'escalation dei privilegi, lo spostamento laterale e l'esfiltrazione dei dati. Per comprendere i potenziali rischi e arrestare questi tipi di attacchi, è necessario ottenere una visibilità chiara sul comportamento di conformità delle app dell'organizzazione per identificare rapidamente quando un'app presenta comportamenti anomali e per rispondere quando questi comportamenti presentano rischi per l'ambiente, i dati e gli utenti.

La funzionalità del componente aggiuntivo della governance delle app per Microsoft Cloud App Security è una funzionalità di gestione della sicurezza e dei criteri progettata per le app abilitate per OAuth che accedono ai dati Microsoft 365 tramite l’API di Microsoft Graph. La governance delle app offre visibilità, correzione e governance complete su come queste app e i relativi utenti accedono, utilizzano e condividono i dati sensibili archiviati in Microsoft 365 tramite informazioni dettagliate di utilità pratica e avvisi e azioni automatizzati dei criteri.

<!--
The scale of ongoing cybersecurity incidents affecting large enterprises and smaller businesses highlights the dangers of supply chain attacks and the need to strengthen the security and compliance posture of every organization. Accelerated cloud adoption with Microsoft 365 and its rich application ecosystem are constantly growing. Attackers are gaining organizational footholds through applications because:

- Users are typically unaware of the risks when consenting to the use of applications. 
- App developers and independent software vendors (ISVs) do not yet have Security Development Lifecycle (SDL) best practices in place to address attacker techniques.
-->

La governance delle app offre funzionalità complete:

- **Insights**: consultare una visualizzazione di tutte le app di terze parti per la piattaforma di Microsoft 365 nel tenant in un unico dashboard. È possibile visualizzare lo stato di tutte le app e le attività di avviso, e reagire o rispondere a queste.
- **Governance**: creare criteri proattivi o reattivi per i modelli e i comportamenti delle app e utenti, e proteggere gli utenti dall'uso di app non conformi o dannose e limitare l'accesso delle app rischiose ai dati.
- **Rilevamento**: ricevere avvisi e notifiche quando si verificano anomalie nell'attività dell'app e quando vengono utilizzare app non conformi, dannose o rischiose.
- **Correzione**: oltre alle funzionalità di correzione automatica, usare i controlli di correzione in modo tempestivo per rispondere ai rilevamenti anomali delle attività delle app.

La governance delle app è una soluzione basata su piattaforma che è parte integrante dell'ecosistema di app di Microsoft 365. La governance delle app supervisiona e gestisce le app abilitate per OAuth registrate con Azure Active Directory (Azure AD) e accede ai dati tramite l'API di Microsoft Graph. La governance delle app offre controlli del comportamento delle applicazioni per rafforzare il comportamento di sicurezza e conformità dell'infrastruttura IT.

<!--
Unlike other application governance products in the marketplace, MAPG is a platform-based solution that is an integral part of the Microsoft 365 application ecosystem. MAPG's initial focus is on OAuth-enabled apps published to the Microsoft 365 platform that are registered with Azure AD and access data through the Graph API. For the initial release, MAPG does not support other, non-OAuth-enabled M365 apps, add-ins (such as PowerBI), or other app vendor ecosystems such as Google, Facebook, Amazon Web Services, Workplace, and Salesforce. MAPG’s focus is on third-party published apps for the Microsoft 365 application platform.

Microsoft allows developers to build cloud applications using Azure Active Directory (Azure AD), Microsoft’s cloud identity platform, and other resources and access to tenant data through the Microsoft Graph. Because of MAPG's visibility, insights, and control capabilities, app developers have the incentive to comply with publisher verification, self-attestation, and Microsoft certification, and can build high-quality productivity apps that are secure and compliant.
-->

## <a name="a-first-glimpse-at-app-governance"></a>Primo sguardo alla governance delle app

Per visualizzare il dashboard di governance delle app, passare a [https://aka.ms/appgovernance](https://aka.ms/appgovernance). Tenere presente che l'account di accesso deve disporre di uno dei [ ruoli di amministratore](app-governance-get-started.md#administrator-roles) per visualizzare i dati di governance.

## <a name="app-governance-integration-with-azure-ad-and-microsoft-cloud-app-security"></a>Integrazione della governance delle app con Azure AD e Microsoft Cloud App Security

Governance delle app, Azure AD e Microsoft Cloud App Security raccolgono e forniscono insiemi di dati diversi:

- La governance delle app fornisce informazioni dettagliate sull'attività di un'app a livello di API.
- Azure AD fornisce metadati di base dell’app e informazioni dettagliate sugli accessi alle app.
- Microsoft Cloud App Security fornisce informazioni sul rischio dell’app.

Condividendo le informazioni tra governance delle app, Azure AD e Microsoft Cloud App Security, è possibile visualizzare informazioni aggregate in un portale e collegarsi facilmente a un altro portale per altre informazioni. Ecco alcuni esempi:

- Informazioni di accesso alle app nella governance delle app:

  Dal portale di governance delle app è possibile visualizzare l’attività di accesso aggregata per ogni app e collegarsi all’interfaccia di amministrazione di Azure Active Directory per i dettagli degli eventi di accesso.

<!--
- App API usage information in the Azure Active Directory admin center:

  From the Azure Active Directory admin center, you can see the aggregated app usage information and link to the app governance portal for the details of app usage.
-->
- Informazioni sull’utilizzo dell'API nel portale di Microsoft Cloud App Security:

  Dal portale di Microsoft Cloud App Security è possibile visualizzare il livello di utilizzo dell'API e aggregare il trasferimento dei dati e collegarsi al portale di governance delle app per i dettagli.

Di seguito è riportato un riepilogo dell’integrazione.

![Integrazione della governance delle app con Azure Active Directory e Microsoft Cloud App Security](..\media\manage-app-protection-governance\mapg-integration.png)

Inoltre, la governance delle app invia i propri avvisi come segnali a Microsoft Cloud App Security e Microsoft 365 Defender, e riceve avvisi da Microsoft Cloud App Security per abilitare un'analisi più dettagliata degli eventi imprevisti di sicurezza basati su app.

<!--
Integration of alerts with MCAS and M365 Defender
Azure AD IP detections in progress to surface in M365 Defender

## Integration with Azure AD

**Feedback from Anand:** We should add some details on how MAPG works with M365 Defender (previously MTP). Also, we should highlight the integration with MCAS and AAD.

Key cross-reference resources:

- [What is application management in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-application-management)
- [Common application management scenarios for Azure Active Directory (especially scenarios 3-4)](https://docs.microsoft.com/cloud-app-security/monitor-alerts)
- [Azure Active Directory Identity Governance documentation](https://docs.microsoft.com/azure/active-directory/governance/)
- [Managing access to apps using Azure AD](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-access-management)

## Integration with Microsoft Cloud App Security

Key cross-reference resources:

- [Cloud App Security anomaly detection alerts investigation guide](https://docs.microsoft.com/cloud-app-security/investigate-anomaly-alerts#unusual-addition-of-credentials-to-an-oauth-app)
- [Monitor alerts raised in Cloud App Security](https://docs.microsoft.com/cloud-app-security/monitor-alerts)
- [Control which third-party cloud OAuth apps get permissions](https://docs.microsoft.com/cloud-app-security/manage-app-permissions)

-->

## <a name="using-app-governance"></a>Uso della governance delle app

L'uso della governance delle app per proteggere il tenant e i relativi dati da app potenzialmente dannose o con un comportamento non corretto rientra in queste tre funzionalità principali:

| Funzionalità | Descrizione |
|:-------|:-----|
| [Visibilità e dati analitici delle app](app-governance-visibility-insights-overview.md) | Ottenere una visualizzazione a 360° del traffico e dell'attività delle applicazioni di Microsoft 365 nel tenant. |
| [Criteri delle app per governance più avanzata](app-governance-app-policies-overview.md) | Creare criteri proattivi o reattivi per le app, che consentiranno di applicare la governance per le app di Microsoft 3635. |
| [Rilevamento e correzione](app-governance-detect-remediate-overview.md) | In base agli avvisi di rilevamento della piattaforma o agli avvisi di rilevamento generati dai criteri, monitorare le app per rilevare comportamenti anomali e correggerli automaticamente in base alle impostazioni dei criteri delle app o manualmente. |
|||
