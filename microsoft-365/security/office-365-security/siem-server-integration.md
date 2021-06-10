---
title: Integrazione del server SIEM con Microsoft 365 applicazioni
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 11/18/2019
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.custom:
- Ent_Solutions
- SIEM
- seo-marvel-apr2020
description: Panoramica dell'integrazione del server SiEM (Security Information and Event Management) con i servizi cloud Microsoft 365 e le applicazioni
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: bea8aa3914da4b813f3928eddbb6df9c98ef6605
ms.sourcegitcommit: 7ee50882cb4ed37794a3cd82dac9b2f9e0a1f14a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/06/2021
ms.locfileid: "51599948"
---
# <a name="security-information-and-event-management-siem-server-integration-with-microsoft-365-services-and-applications"></a>Integrazione del server SiEM (Security Information and Event Management) con Microsoft 365 applicazioni e servizi di sicurezza

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

## <a name="summary"></a>Riepilogo

L'organizzazione utilizza o pianifica di ottenere un server SiEM (Security Information and Event Management) Potrebbe essere necessario chiedersi come si integra con Microsoft 365 o Office 365. In questo articolo viene fornito un elenco delle risorse che è possibile utilizzare per integrare il server SIEM con Microsoft 365 e applicazioni.

> [!TIP]
> Se non hai ancora un server SIEM e stai esplorando le opzioni, prendi **[in considerazione Microsoft Azure Sentinel.](/azure/sentinel/overview)**

## <a name="do-i-need-a-siem-server"></a>È necessario un server SIEM?

La necessità di un server SIEM dipende da molti fattori, ad esempio i requisiti di sicurezza dell'organizzazione e la posizione dei dati. Microsoft 365 include un'ampia gamma di funzionalità di sicurezza che soddisfano le esigenze di sicurezza di molte organizzazioni senza server aggiuntivi, ad esempio un server SIEM. Alcune organizzazioni hanno circostanze particolari che richiedono l'utilizzo di un server SIEM. Di seguito vengono descritti alcuni esempi:

- *Fabrikam* ha alcuni contenuti e applicazioni in locale e alcuni nel cloud (hanno una distribuzione cloud ibrida). Per ottenere report sulla sicurezza in tutto il contenuto e le applicazioni, Fabrikam ha implementato un server SIEM.

- *Contoso* è un'organizzazione di servizi finanziari con requisiti di sicurezza particolarmente stringenti. Hanno aggiunto un server SIEM al proprio ambiente per sfruttare la protezione di sicurezza aggiuntiva necessaria.

## <a name="siem-server-integration-with-microsoft-365"></a>Integrazione del server SIEM con Microsoft 365

Un server SIEM può ricevere dati da un'ampia gamma di Microsoft 365 e applicazioni. Nella tabella seguente sono elencati diversi Microsoft 365 e applicazioni, insieme agli input e alle risorse del server SIEM per ulteriori informazioni.

****

|Microsoft 365 Servizio o applicazione|Input/metodi del server SIEM|Risorse per approfondire|
|---|---|---|
|[Microsoft Defender per Office 365](defender-for-office-365.md)|Log di controllo|[Integrazione SIEM con Microsoft Defender per Office 365](siem-integration-with-office-365-ti.md)|
|[Microsoft Defender per endpoint](/windows/security/threat-protection/)|Endpoint HTTPS ospitato in Azure <p> API REST|[Pull degli avvisi agli strumenti SIEM](../defender-endpoint/configure-siem.md)|
|[Microsoft Cloud App Security](/cloud-app-security/what-is-cloud-app-security)|Integrazione dei log|[Integrazione SIEM con Microsoft Cloud App Security](/cloud-app-security/siem)|
|

> [!TIP]
> Dai un'occhiata [ad Azure Sentinel.](/azure/sentinel/overview) Azure Sentinel include connettori per soluzioni Microsoft. Questi connettori sono disponibili "out-of-the-box" e consentono l'integrazione in tempo reale. È possibile usare Azure Sentinel con le soluzioni Microsoft 365 Defender e i servizi Microsoft 365, tra cui Office 365, Azure AD, Microsoft Defender for Identity, Microsoft Cloud App Security e altro ancora.

### <a name="audit-logging-must-be-turned-on"></a>La registrazione di controllo deve essere attivata

Verificare che la registrazione di controllo sia attivata prima di configurare l'integrazione del server SIEM.

- Per SharePoint Online, OneDrive for Business e Azure Active Directory, la registrazione di controllo è [attivata nel Centro sicurezza & conformità](../../compliance/turn-audit-log-search-on-or-off.md).

- Per Exchange Online, vedere [Manage mailbox auditing](../../compliance/enable-mailbox-auditing.md).

## <a name="more-resources"></a>Altre risorse

[Integrare soluzioni di sicurezza in Azure Defender](/azure/security-center/security-center-partner-integration#exporting-data-to-a-siem)

[Integrare gli avvisi delle API di sicurezza di Microsoft Graph con un SIEM](/graph/security-integration)