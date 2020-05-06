---
title: Monitoraggio delle app & Reporting-Centro sicurezza
description: Informazioni su come è possibile ottenere ulteriori informazioni sull'utilizzo delle app Cloud nell'organizzazione, inclusi i tipi di app, il livello di rischio e gli avvisi.
keywords: sicurezza, malware, Microsoft 365, M365, Centro sicurezza, monitoraggio, report, app
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: cd7a86751ac58f60051891544c9fd68c51b439e1
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034023"
---
# <a name="app-monitoring-and-reporting-in-the-microsoft-365-security-center"></a>Monitoraggio e creazione di report delle app nel centro sicurezza Microsoft 365

Questi rapporti offrono maggiori informazioni su come vengono utilizzate le app Cloud nell'organizzazione, inclusi i tipi di app, il livello di rischio e gli avvisi.

## <a name="monitor-email-accounts-at-risk"></a>Monitorare gli account di posta elettronica a rischio

La **protezione della posta** elettronica Visualizza gli account di posta elettronica a rischio. È possibile fare clic su un account per esaminare ulteriormente il Centro sicurezza di Microsoft Defender.

![Scheda di protezione della posta elettronica](../../media/email-protection.png)

## <a name="monitor-app-permissions-granted-by-users"></a>Monitorare le autorizzazioni delle app concesse dagli utenti

**Cloud app Security-OAuth Apps** elenca le app scoperte dalla protezione delle app cloud alle quali sono state concesse le autorizzazioni per gli utenti. Il catalogo rischi di cloud app Security include oltre 16.000 app valutate con oltre 70 fattori di rischio.

I fattori di rischio partono da informazioni generali, ad esempio l'editore app, per le misure di sicurezza e i controlli, ad esempio se l'app supporta la crittografia a riposo o fornisce un registro di controllo delle attività degli utenti.

![Cloud app Security OAuth Apps Card](../../media/cloud-app-security-oauth-apps.png)

## <a name="monitor-cloud-app-user-accounts"></a>Monitorare gli account utente delle app Cloud

Gli **account delle app cloud per gli elenchi di revisione** possono richiedere attenzione.

![Account app cloud per la scheda di Revisione](../../media/cloud-app-accounts-for-review.png)

## <a name="understand-which-cloud-apps-are-used"></a>Informazioni sulle app Cloud utilizzate

Le **app del cloud scoperte (categorie)** mostrano quali tipi di app vengono utilizzate nell'organizzazione e si collegano al dashboard di individuazione cloud in cloud app Security. Per ulteriori informazioni, vedere [Guida introduttiva: lavorare con le app scoperte](https://docs.microsoft.com/cloud-app-security/discovered-apps).  

![Scheda categorie di applicazioni cloud scoperte](../../media/discovered-cloud-apps-categories.png)

## <a name="monitor-where-users-access-cloud-apps"></a>Monitorare la posizione in cui gli utenti accedono alle app Cloud

Le **posizioni delle attività delle app Cloud** mostrano dove gli utenti accedono alle app cloud.

![Scheda percorsi attività app Cloud](../../media/cloud-app-activity-locations.png)

## <a name="monitor-health-for-infrastructure-workloads"></a>Monitorare l'integrità dei carichi di lavoro dell'infrastruttura

L' **integrità dell'infrastruttura** Visualizza gli avvisi sullo stato dell'integrità per i carichi di lavoro dell'infrastruttura in Azure Security Center.

Azure Security Center fornisce la gestione della sicurezza unificata e la protezione avanzata dalle minacce tra carichi di lavoro locali e cloud. È possibile raccogliere, ricercare e analizzare i dati di sicurezza provenienti da un'ampia gamma di origini, tra cui i firewall e altre soluzioni partner.

Per ulteriori informazioni, vedere [documentazione relativa al centro sicurezza di Azure](https://docs.microsoft.com/azure/security-center/).

![Scheda di integrità dell'infrastruttura](../../media/infrastructure-health.png)
