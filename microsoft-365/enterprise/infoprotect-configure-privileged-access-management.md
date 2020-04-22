---
title: 'Passaggio 7: configurare la gestione degli accessi con privilegi'
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
ms.custom: ''
description: Comprendere e configurare la gestione degli accessi con privilegi.
ms.openlocfilehash: 4fed4daacc17a34563825bf0575880ce06ec6ebd
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636989"
---
# <a name="step-7-configure-privileged-access-management"></a>Passaggio 7: configurare la gestione degli accessi con privilegi

*Questo passaggio è facoltativo e si applica solo alle versioni E5 e Advanced Compliance di Microsoft 365 Enterprise*

![Fase 6: protezione delle informazioni](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

La gestione degli accessi con privilegi è abilitata configurando i criteri che specificano l'accesso just-in-time per le attività basate sulle attività nel tenant. Può aiutare a proteggere l'organizzazione da violazioni che possono utilizzare gli account amministratore privilegiati esistenti con accesso permanente ai dati sensibili o l'accesso alle impostazioni di configurazione critiche. Ad esempio, è possibile configurare un criterio di gestione degli accessi con privilegi che richiede l'approvazione esplicita per accedere e modificare le impostazioni delle cassette postali dell'organizzazione nel tenant.

In questo passaggio, è possibile abilitare la gestione degli accessi con privilegi nel tenant e configurare i criteri di accesso privilegiato che forniscono ulteriore sicurezza per l'accesso basato sulle attività ai dati e alle impostazioni di configurazione per l'organizzazione. Per iniziare a utilizzare l'accesso con privilegi nell'organizzazione, è necessario eseguire tre operazioni di base:
- Creazione di un gruppo responsabile dell'approvazione
- Abilitazione dell’accesso con privilegi
- Creazione di criteri per l'approvazione

Una volta configurata, la gestione degli accessi con privilegi consentirà all'organizzazione di operare con privilegi permanenti uguali a zero e di fornire un livello di protezione contro vulnerabilità che si verificano a causa di questo tipo di accesso amministrativo permanente. L’accesso con privilegi richiede l'approvazione per l'esecuzione di tutte le attività associate a un criterio di approvazione definito. Gli utenti che necessitano di eseguire attività incluse nei criteri di approvazione devono richiedere e ottenere l'approvazione di accesso per disporre delle autorizzazioni necessarie a eseguire le attività definite nel criterio.

Per abilitare la gestione degli accessi con privilegi, vedere l'argomento [Configure Privileged Access Management](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) .

Per ulteriori informazioni, vedere l'argomento relativo alla [gestione degli accessi con privilegi](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview) .


|||
|:-------|:-----|
|![Guide al lab di test per il cloud Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)|  Per eseguire questa procedura in un ambiente di testing, vedere la [Guida al lab di test gestione degli accessi privilegiati](privileged-access-microsoft-365-enterprise-dev-test-environment.md). |
|||

Come checkpoint provvisorio, vedere i [criteri uscita](infoprotect-exit-criteria.md#crit-infoprotect-step7) che corrispondono a questo passaggio.

## <a name="next-step"></a>Passaggio successivo

[Criteri uscita dell'infrastruttura di protezione delle informazioni](infoprotect-exit-criteria.md)
