---
title: Integrazione del server SIEM con applicazioni e servizi di Microsoft 365
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
description: Panoramica dell'integrazione del server SiEM (Security Information and Event Management) con le applicazioni e i servizi cloud di Microsoft 365
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 21aaad71f40a01a3bea2f9535d1c3256ae667bae
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50916587"
---
# <a name="security-information-and-event-management-siem-server-integration-with-microsoft-365-services-and-applications"></a>Integrazione del server SiEM (Security Information and Event Management) con applicazioni e servizi di Microsoft 365

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

## <a name="summary"></a>Riepilogo

L'organizzazione utilizza o pianifica di ottenere un server SiEM (Security Information and Event Management) Potrebbe essere necessario chiedersi come si integra con Microsoft 365 o Office 365. In questo articolo viene fornito un elenco delle risorse che è possibile utilizzare per integrare il server SIEM con i servizi e le applicazioni di Microsoft 365.

> [!TIP]
> Se non si dispone ancora di un server SIEM e si stanno esplorando le opzioni, prendere in considerazione **[Microsoft Azure Sentinel.](/azure/sentinel/overview)**

## <a name="do-i-need-a-siem-server"></a>È necessario un server SIEM?

La necessità di un server SIEM dipende da molti fattori, ad esempio i requisiti di sicurezza dell'organizzazione e la posizione dei dati. Microsoft 365 include un'ampia gamma di funzionalità di sicurezza che soddisfano le esigenze di sicurezza di molte organizzazioni senza server aggiuntivi, ad esempio un server SIEM. Alcune organizzazioni hanno circostanze particolari che richiedono l'utilizzo di un server SIEM. Ecco alcuni esempi:

- *Fabrikam* ha alcuni contenuti e applicazioni in locale e alcuni nel cloud (hanno una distribuzione cloud ibrida). Per ottenere report sulla sicurezza in tutto il contenuto e le applicazioni, Fabrikam ha implementato un server SIEM.

- *Contoso* è un'organizzazione di servizi finanziari con requisiti di sicurezza particolarmente stringenti. Hanno aggiunto un server SIEM al proprio ambiente per sfruttare la protezione di sicurezza aggiuntiva necessaria.

## <a name="siem-server-integration-with-microsoft-365"></a>Integrazione del server SIEM con Microsoft 365

Un server SIEM può ricevere dati da un'ampia gamma di applicazioni e servizi di Microsoft 365. Nella tabella seguente sono elencati diversi servizi e applicazioni di Microsoft 365, insieme agli input del server SIEM e alle risorse per saperne di più.

****

|Servizio o applicazione Microsoft 365|Input/metodi del server SIEM|Risorse per approfondire|
|---|---|---|
|[Microsoft Defender per Office 365](office-365-atp.md)|Log di controllo|[Integrazione SIEM con Microsoft Defender per Office 365](siem-integration-with-office-365-ti.md)|
|[Microsoft Defender ATP](/windows/security/threat-protection/)|Endpoint HTTPS ospitato in Azure <p> API REST|[Pull degli avvisi agli strumenti SIEM](/windows/security/threat-protection/microsoft-defender-atp/configure-siem)|
|[Microsoft Cloud App Security](/cloud-app-security/what-is-cloud-app-security)|Integrazione dei log|[Integrazione SIEM con Microsoft Cloud App Security](/cloud-app-security/siem)|
|

> [!TIP]
> Dai un'occhiata [ad Azure Sentinel.](/azure/sentinel/overview) Azure Sentinel include connettori per soluzioni Microsoft. Questi connettori sono disponibili "out-of-the-box" e consentono l'integrazione in tempo reale. È possibile usare Azure Sentinel con le soluzioni Microsoft 365 Defender e i servizi di Microsoft 365, tra cui Office 365, Azure AD, Microsoft Defender for Identity, Microsoft Cloud App Security e altro ancora.

### <a name="audit-logging-must-be-turned-on"></a>La registrazione di controllo deve essere attivata

Verificare che la registrazione di controllo sia attivata prima di configurare l'integrazione del server SIEM.

- Per SharePoint Online, OneDrive for Business e Azure Active Directory, la registrazione di controllo è attivata nel [Centro sicurezza & conformità](../../compliance/turn-audit-log-search-on-or-off.md).

- Per Exchange Online, vedere [Manage mailbox auditing](../../compliance/enable-mailbox-auditing.md).

## <a name="more-resources"></a>Altre risorse

[Integrare soluzioni di sicurezza in Azure Defender](/azure/security-center/security-center-partner-integration#exporting-data-to-a-siem)

[Integrare gli avvisi delle API di sicurezza di Microsoft Graph con un SIEM](/graph/security-integration)