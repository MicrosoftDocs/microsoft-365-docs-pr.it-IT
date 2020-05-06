---
title: Integrazione del server SIEM con i servizi e le applicazioni di Microsoft 365
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 11/18/2019
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.custom:
- Ent_Solutions
- SIEM
- seo-marvel-apr2020
description: Ottenere una panoramica delle informazioni di sicurezza e dell'integrazione del server di gestione eventi (SIEM) con i servizi e le applicazioni cloud di Microsoft 365
ms.openlocfilehash: c52f24c6260c890b1f6d8612efacb78f9b08be86
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035261"
---
# <a name="security-information-and-event-management-siem-server-integration-with-microsoft-365-services-and-applications"></a>Integrazione del server di sicurezza e di gestione eventi (SIEM) con i servizi e le applicazioni Microsoft 365

## <a name="summary"></a>Riepilogo

L'organizzazione utilizza o pianifica la pianificazione per ottenere un server di gestione eventi e informazioni di sicurezza (SIEM)? Potrebbe essere utile sapere come si integra con Microsoft 365 o Office 365. In questo articolo viene fornito un elenco delle risorse che è possibile utilizzare per integrare il server SIEM con i servizi e le applicazioni di Microsoft 365.

> [!TIP]
> Se non si dispone ancora di un server SIEM e si esplorano le opzioni, prendere in considerazione **[Microsoft Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview)**.

## <a name="do-i-need-a-siem-server"></a>È necessario un server SIEM?

Se è necessario un server SIEM dipende da molti fattori, ad esempio i requisiti di sicurezza dell'organizzazione e il luogo in cui si trovano i dati. Microsoft 365 include una vasta gamma di funzionalità di sicurezza che soddisfano le esigenze di sicurezza di molte organizzazioni senza server aggiuntivi, ad esempio un server SIEM. Alcune organizzazioni presentano circostanze speciali che richiedono l'utilizzo di un server SIEM. Ecco alcuni esempi:

- In *Fabrikam* sono disponibili contenuto e applicazioni in locale e alcuni nel cloud (dispongono di una distribuzione di cloud ibrido). Per ottenere i rapporti sulla sicurezza tra tutti i contenuti e le applicazioni, Fabrikam ha implementato un server SIEM.

- *Contoso* è un'organizzazione per i servizi finanziari con requisiti di sicurezza particolarmente severi. Sono stati aggiunti un server SIEM all'ambiente per usufruire della protezione di sicurezza aggiuntiva necessaria.

## <a name="siem-server-integration-with-microsoft-365"></a>Integrazione del server SIEM con Microsoft 365

Un server SIEM può ricevere dati da un'ampia gamma di servizi e applicazioni di Microsoft 365. Nella tabella seguente sono elencati diversi servizi e applicazioni di Microsoft 365, oltre a fattori di input e risorse del server SIEM per ulteriori informazioni.

||||
|---|---|---|
|**Servizio o applicazione Microsoft 365**|**Input/metodi del server SIEM**|**Risorse per approfondire**|
|[Office 365 Advanced Threat Protection](office-365-atp.md)|Registri di controllo|[Integrazione di SIEM con Office 365 Advanced Threat Protection](siem-integration-with-office-365-ti.md)|
|[Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/)|Endpoint HTTPS ospitato in Azure <br/>API REST|[Tirare gli avvisi agli strumenti di SIEM](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-siem)|
|[Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)|Integrazione del registro|[Integrazione di SIEM con Microsoft cloud app Security](https://docs.microsoft.com/cloud-app-security/siem)|
|

> [!TIP]
> Dai un'occhiata a [Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview). Azure Sentinel è dotato di connettori per le soluzioni Microsoft. Questi connettori sono disponibili "fuori dalla scatola" e forniscono l'integrazione in tempo reale. È possibile utilizzare Azure Sentinel con le soluzioni Microsoft Threat Protection e Microsoft 365 Services, tra cui Office 365, Azure AD, Azure ATP, Microsoft cloud app Security e altro ancora.

### <a name="audit-logging-must-be-turned-on"></a>La registrazione di controllo deve essere attivata

Verificare che la registrazione di controllo sia attivata prima di configurare l'integrazione del server SIEM.

- Per SharePoint Online, OneDrive for business e Azure Active Directory, [la registrazione di controllo è attivata nel centro sicurezza & conformità](../../compliance/turn-audit-log-search-on-or-off.md).

- Per Exchange Online, vedere [gestire il controllo delle cassette postali](../../compliance/enable-mailbox-auditing.md).

## <a name="more-resources"></a>Altre risorse

[Integrare soluzioni di sicurezza nel centro sicurezza di Azure](https://docs.microsoft.com/azure/security-center/security-center-partner-integration#exporting-data-to-a-siem)

[Integrare gli avvisi dell'API di sicurezza di Microsoft Graph con un SIEM](https://docs.microsoft.com/graph/security-integration)
