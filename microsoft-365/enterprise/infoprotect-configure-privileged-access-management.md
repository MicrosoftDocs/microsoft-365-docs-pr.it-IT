---
title: 'Passaggio 7: configurare la gestione degli accessi con privilegi per Office 365'
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
description: Comprendere e configurare la gestione degli accessi con privilegi per Office 365.
ms.openlocfilehash: f29b1e0934a4b9a6d4e3347584f39423d446ed58
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42067233"
---
# <a name="step-7-configure-privileged-access-management-for-office-365"></a>Passaggio 7: configurare la gestione degli accessi con privilegi per Office 365

*Questo passaggio è facoltativo e si applica solo alle versioni E5 e Advanced Compliance di Microsoft 365 Enterprise*

![Fase 6: protezione delle informazioni](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

La gestione degli accessi con privilegi è abilitata mediante la configurazione di criteri che specificano l'accesso just-in-time per le operazioni basate sulle attività nel tenant di Office 365. Può aumentare il livello di protezione dell'organizzazione da violazioni che possono usare account di amministratore privilegiato esistenti con accesso permanente a dati riservati o con accesso a impostazioni di configurazione cruciali. Ad esempio, è possibile configurare un criterio di gestione degli accessi con privilegi che richiede l'approvazione esplicita per accedere e modificare le impostazioni delle cassette postali dell'organizzazione nel tenant di Office 365.

In questo passaggio verrà abilitata la gestione degli accessi con privilegi nel tenant di Office 365 e verranno configurati i criteri di accesso con privilegi che garantiscono una maggiore protezione per gli accessi basati sulle attività a impostazioni dati e configurazione di Office 365 dell’organizzazione. Esistono tre passaggi di base per iniziare a usare gli accessi con privilegi nell'organizzazione di Office 365:
- Creazione di un gruppo responsabile dell'approvazione
- Abilitazione dell’accesso con privilegi
- Creazione di criteri per l'approvazione

Una volta configurata, la gestione degli accessi con privilegi consentirà all'organizzazione di operare con privilegi permanenti uguali a zero e di fornire un livello di protezione contro vulnerabilità che si verificano a causa di questo tipo di accesso amministrativo permanente. L’accesso con privilegi richiede l'approvazione per l'esecuzione di tutte le attività associate a un criterio di approvazione definito. Gli utenti che necessitano di eseguire attività incluse nei criteri di approvazione devono richiedere e ottenere l'approvazione di accesso per disporre delle autorizzazioni necessarie a eseguire le attività definite nel criterio.

Per abilitare la gestione degli accessi con privilegi di Office 365, vedere l’argomento [Configurare la gestione degli accessi con privilegi in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration).

Per ulteriori informazioni, vedere l’argomento [Gestione degli accessi con privilegi in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview).


|||
|:-------|:-----|
|![Guide al lab di test per il cloud Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)|  Per eseguire questa procedura in un ambiente di testing, vedere la [Guida al lab di test gestione degli accessi privilegiati](privileged-access-microsoft-365-enterprise-dev-test-environment.md). |
|||

Come checkpoint provvisorio, vedere i [criteri uscita](infoprotect-exit-criteria.md#crit-infoprotect-step7) che corrispondono a questo passaggio.

## <a name="next-step"></a>Passaggio successivo

[Criteri uscita dell'infrastruttura di protezione delle informazioni](infoprotect-exit-criteria.md)
