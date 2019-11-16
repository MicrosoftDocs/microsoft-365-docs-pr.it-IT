---
title: Integrazione del server SIEM con i servizi e le applicazioni di Microsoft 365
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 11/15/2019
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.custom:
- Ent_Solutions
- SIEM
description: Leggere questo articolo per ottenere una panoramica dell'integrazione del server SIEM con Microsoft 365.
ms.openlocfilehash: bea6141022fef1275a7e291217f698f52613f170
ms.sourcegitcommit: d8d001c03c28c10bea005d1c9b5f4a8f393af706
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/16/2019
ms.locfileid: "38677509"
---
# <a name="siem-server-integration-with-microsoft-365-services-and-applications"></a>Integrazione del server SIEM con i servizi e le applicazioni di Microsoft 365

## <a name="summary"></a>Riepilogo

Se l'organizzazione utilizza un server di gestione eventi e informazioni di sicurezza (SIEM) o se si prevede di ottenere un server SIEM al più presto, potrebbe essere utile sapere come si integrerà con Microsoft 365 o Office 365. In questo articolo viene fornito un elenco delle risorse che è possibile utilizzare per configurare l'integrazione dei server SIEM con i servizi e le applicazioni di Microsoft 365.

> [!TIP]
> Se non si dispone ancora di un server SIEM e si esplorano le opzioni, prendere in considerazione **[Microsoft Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview)**.

## <a name="do-i-need-a-siem-server"></a>È necessario un server SIEM?

Se è necessario un server SIEM dipende da molti fattori, ad esempio i requisiti di sicurezza dell'organizzazione e il luogo in cui si trovano i dati. Microsoft 365 include una vasta gamma di funzionalità di sicurezza che soddisfano le esigenze di sicurezza di molte organizzazioni senza server aggiuntivi, ad esempio un server SIEM. Alcune organizzazioni presentano circostanze speciali che richiedono l'utilizzo di un server SIEM. Ecco alcuni esempi:

- In *Fabrikam* sono disponibili contenuto e applicazioni in locale e alcuni nel cloud (dispongono di una distribuzione di cloud ibrido). Per ottenere i rapporti sulla sicurezza tra tutti i contenuti e le applicazioni, Fabrikam ha implementato un server SIEM. 

- *Contoso* è un'organizzazione per i servizi finanziari con requisiti di sicurezza particolarmente severi. Sono stati aggiunti un server SIEM all'ambiente per usufruire della protezione di sicurezza aggiuntiva necessaria.

## <a name="siem-server-integration-with-microsoft-365"></a>Integrazione del server SIEM con Microsoft 365

Un server SIEM può ricevere dati da un'ampia gamma di servizi e applicazioni di Microsoft 365. Nella tabella seguente sono elencati diversi servizi e applicazioni di Microsoft 365 insieme agli input del server SIEM e risorse per ulteriori informazioni sull'integrazione del server SIEM. 

| Servizio o applicazione Microsoft 365 | Input del server SIEM | Risorse per approfondire |
| --- | --- | --- |
| [Office 365 Advanced Threat Protection](office-365-atp.md)  | Registri di controllo | [Integrazione di SIEM con Office 365 Advanced Threat Protection](siem-integration-with-office-365-ti.md) |
| [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/) | Endpoint HTTPS ospitato in Azure <br/>API REST| [Tirare gli avvisi agli strumenti di SIEM](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-siem) |
| [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) | Integrazione del registro | [Integrazione di SIEM con Microsoft cloud app Security](https://docs.microsoft.com/cloud-app-security/siem) |

> [!TIP]
> Dai un'occhiata a [Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview), che include un numero di connettori per le soluzioni Microsoft, disponibile fuori dalla scatola e fornendo integrazione in tempo reale, incluse le soluzioni Microsoft Threat Protection e Microsoft 365 Sources, tra cui Office 365, Azure ad, Azure ATP e Microsoft cloud app Security e altro ancora.

### <a name="audit-logging-must-be-turned-on"></a>La registrazione di controllo deve essere attivata

Verificare che la registrazione di controllo sia attivata prima di configurare l'integrazione del server SIEM. 

- Per SharePoint Online, OneDrive for business e Azure Active Directory, [la registrazione di controllo è attivata nel centro sicurezza & conformità](https://docs.microsoft.com/office365/securitycompliance/turn-audit-log-search-on-or-off).

- Per Exchange Online, la [registrazione di controllo è attivata con Windows PowerShell](https://docs.microsoft.com/office365/securitycompliance/enable-mailbox-auditing).
 
## <a name="additional-resources"></a>Risorse aggiuntive

[Integrare soluzioni di sicurezza nel centro sicurezza di Azure](https://docs.microsoft.com/azure/security-center/security-center-partner-integration#exporting-data-to-a-siem)

[Integrare gli avvisi dell'API di sicurezza di Microsoft Graph con un SIEM](https://docs.microsoft.com/graph/security-integration)