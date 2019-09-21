---
title: Monitoraggio e creazione di report delle app in Microsoft 365 Security Center
description: Descrive come è possibile ottenere ulteriori informazioni sull'utilizzo delle app Cloud nell'organizzazione
keywords: sicurezza, malware, Microsoft 365, M365, Centro sicurezza, monitoraggio, report, app
ms.prod: w10
ms.mktglfcycl: deploy
ms.localizationpriority: medium
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.openlocfilehash: 29dd1f4ebb8d65bb6079cdc4467f1aa5e33ae906
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37084956"
---
# <a name="app-monitoring-and-reporting-in-microsoft-365-security-center"></a>Monitoraggio e creazione di report delle app in Microsoft 365 Security Center

Questi rapporti offrono maggiori informazioni su come vengono utilizzate le app Cloud nell'organizzazione, inclusi i tipi di app, il livello di rischio e gli avvisi.

## <a name="monitor-email-accounts-at-risk"></a>Monitorare gli account di posta elettronica a rischio

La **protezione della posta** elettronica Visualizza gli account di posta elettronica a rischio. È possibile fare clic su un account per esaminare ulteriormente il Centro sicurezza di Microsoft Defender.

![Scheda di protezione della posta elettronica](../media/security-docs/email-protection.png)

## <a name="monitor-app-permissions-granted-by-users"></a>Monitorare le autorizzazioni delle app concesse dagli utenti

**Cloud app Security-OAuth Apps** elenca le app scoperte dalla protezione delle app cloud alle quali sono state concesse le autorizzazioni per gli utenti. Il catalogo rischi di cloud app Security include oltre 16.000 app valutate con oltre 70 fattori di rischio.

I fattori di rischio partono da informazioni generali, ad esempio l'editore app, per le misure di sicurezza e i controlli, ad esempio se l'app supporta la crittografia a riposo o fornisce un registro di controllo delle attività degli utenti.

![Cloud app Security OAuth Apps Card](../media/security-docs/cloud-app-security-oauth-apps.png)

## <a name="monitor-cloud-app-user-accounts"></a>Monitorare gli account utente delle app Cloud

Gli **account delle app cloud per gli elenchi di revisione** possono richiedere attenzione.

![Account app cloud per la scheda di Revisione](../media/security-docs/cloud-app-accounts-for-review.png)

## <a name="understand-which-cloud-apps-are-used"></a>Informazioni sulle app Cloud utilizzate

Le **app del cloud scoperte (categorie)** mostrano quali tipi di app vengono utilizzate nell'organizzazione e si collegano al dashboard di individuazione cloud in cloud app Security. Per ulteriori informazioni, vedere [Guida introduttiva: lavorare con le app scoperte](https://docs.microsoft.com/cloud-app-security/discovered-apps).  

![Scheda categorie di applicazioni cloud scoperte](../media/security-docs/discovered-cloud-apps-categories.png)

## <a name="monitor-where-users-access-cloud-apps"></a>Monitorare la posizione in cui gli utenti accedono alle app Cloud

Le **posizioni delle attività delle app Cloud** mostrano dove gli utenti accedono alle app cloud.

![Scheda percorsi attività app Cloud](../media/security-docs/cloud-app-activity-locations.png)

## <a name="monitor-health-for-infrastructure-workloads"></a>Monitorare l'integrità dei carichi di lavoro dell'infrastruttura

L' **integrità dell'infrastruttura** Visualizza gli avvisi sullo stato dell'integrità per i carichi di lavoro dell'infrastruttura in Azure Security Center.

Azure Security Center fornisce la gestione della sicurezza unificata e la protezione avanzata dalle minacce tra carichi di lavoro locali e cloud. È possibile raccogliere, ricercare e analizzare i dati di sicurezza provenienti da un'ampia gamma di origini, tra cui i firewall e altre soluzioni partner.

Per ulteriori informazioni, vedere [documentazione relativa al centro sicurezza di Azure](https://docs.microsoft.com/azure/security-center/).

![Scheda di integrità dell'infrastruttura](../media/security-docs/infrastructure-health.png)
