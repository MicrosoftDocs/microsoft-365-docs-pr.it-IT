---
title: 'Passaggio 4: configurare la gestione degli accessi con privilegi per Office 365'
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 9/19/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Comprendere e configurare la gestione degli accessi con privilegi per Office 365.
ms.openlocfilehash: 0de9e5cd602a48f31f48618026b0564146a57d73
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868451"
---
# <a name="step-4-configure-privileged-access-management-for-office-365"></a>Passaggio 4: configurare la gestione degli accessi con privilegi per Office 365

*Questo passaggio è facoltativo e si applica solo alle versioni E5 e Advanced Compliance di Microsoft 365 Enterprise*

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

La gestione degli accessi con privilegi è abilitata mediante la configurazione di criteri che specificano l'accesso just-in-time per le operazioni basate sulle attività nel tenant di Office 365. Può aumentare il livello di protezione dell'organizzazione da violazioni che possono usare account di amministratore privilegiato esistenti con accesso permanente a dati riservati o con accesso a impostazioni di configurazione cruciali. Ad esempio, è possibile configurare un criterio di gestione degli accessi con privilegi che richiede l'approvazione esplicita per accedere e modificare le impostazioni delle cassette postali dell'organizzazione nel tenant di Office 365.

In questo passaggio verrà abilitata la gestione degli accessi con privilegi nel tenant di Office 365 e verranno configurati i criteri di accesso con privilegi che garantiscono una maggiore protezione per gli accessi basati sulle attività a impostazioni dati e configurazione di Office 365 dell’organizzazione. Esistono tre passaggi di base per iniziare a usare gli accessi con privilegi nell'organizzazione di Office 365:
- Creazione di un gruppo responsabile dell'approvazione
- Abilitazione dell’accesso con privilegi
- Creazione di criteri per l'approvazione

Una volta configurata, la gestione degli accessi con privilegi consentirà all'organizzazione di operare con privilegi permanenti uguali a zero e di fornire un livello di protezione contro vulnerabilità che si verificano a causa di questo tipo di accesso amministrativo permanente. L’accesso con privilegi richiede l'approvazione per l'esecuzione di tutte le attività associate a un criterio di approvazione definito. Gli utenti che necessitano di eseguire attività incluse nei criteri di approvazione devono richiedere e ottenere l'approvazione di accesso per disporre delle autorizzazioni necessarie a eseguire le attività definite nel criterio.

Per abilitare la gestione degli accessi con privilegi di Office 365, vedere l’argomento [Configurare la gestione degli accessi con privilegi in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration).

Per ulteriori informazioni, vedere l’argomento [Gestione degli accessi con privilegi in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview).

## <a name="results"></a>Risultati

Il risultato di questo passaggio è un aumento della protezione di Office 365 grazie all’abilitazione del controllo di accesso just-in-time per i dati chiave e le impostazioni di configurazione dell'organizzazione.

Come checkpoint provvisorio, vedere i [criteri uscita](infoprotect-exit-criteria.md#crit-infoprotect-step5) che corrispondono a questo passaggio.

## <a name="next-step"></a>Passaggio successivo

[Criteri uscita dell'infrastruttura di protezione delle informazioni](infoprotect-exit-criteria.md)