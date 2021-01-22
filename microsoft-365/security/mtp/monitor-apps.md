---
title: Monitoraggio delle app & report - Centro sicurezza
description: Scopri come ottenere maggiori informazioni sull'uso delle app cloud nella tua organizzazione. Include diversi tipi di app, il relativo livello di rischio e avvisi.
keywords: sicurezza, malware, Microsoft 365, M365, centro sicurezza, monitorare, report, app
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
search.appverid: met150
ms.custom: seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: ed5fcfc16c08272a6a1d55af210ab48528538048
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930523"
---
# <a name="app-monitoring-and-reporting-in-the-microsoft-365-security-center"></a>Monitoraggio e creazione di report delle app nel Centro sicurezza Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


Questi report forniscono maggiori informazioni su come vengono usate le app cloud nell'organizzazione. Include diversi tipi di app, il relativo livello di rischio e avvisi.

## <a name="monitor-email-accounts-at-risk"></a>Monitorare gli account di posta elettronica a rischio

**La protezione della posta** elettronica mostra gli account di posta elettronica a rischio. Puoi selezionare un account da analizzare ulteriormente in Microsoft Defender Security Center.

![Scheda di protezione della posta elettronica](../../media/email-protection.png)

## <a name="monitor-app-permissions-granted-by-users"></a>Monitorare le autorizzazioni dell'app concesse dagli utenti

**Cloud App Security: le app OAuth** elencano le app individuate da Cloud App Security a cui sono state concesse autorizzazioni dagli utenti. Il catalogo dei rischi di Cloud App Security include oltre 16.000 app valutate utilizzando oltre 70 fattori di rischio.

I fattori di rischio partono dalle informazioni generali, ad esempio l'autore dell'app. Passa quindi a misure e controlli di sicurezza, ad esempio se l'app supporta la crittografia in stato attivo o fornisce un log di controllo dell'attività dell'utente.

![Scheda app OAuth di Cloud App Security](../../media/cloud-app-security-oauth-apps.png)

## <a name="monitor-cloud-app-user-accounts"></a>Monitorare gli account utente delle app cloud

**Gli account delle app cloud per la revisione** elencano gli account che potrebbero richiedere attenzione.

![Account dell'app cloud per la scheda da rivedere](../../media/cloud-app-accounts-for-review.png)

## <a name="understand-which-cloud-apps-are-used"></a>Comprendere quali app cloud vengono usate

**Le app cloud individuate (categorie)** mostrano i tipi di app in uso nell'organizzazione. Si collega al dashboard di Cloud Discovery in Cloud App Security. Per altre informazioni, vedi [Guida introduttiva: Usare le app individuate.](https://docs.microsoft.com/cloud-app-security/discovered-apps)  

![Scheda categorie app cloud individuate](../../media/discovered-cloud-apps-categories.png)

## <a name="monitor-where-users-access-cloud-apps"></a>Monitorare dove gli utenti accedono alle app cloud

**I percorsi di attività delle app** cloud mostrano dove gli utenti accedono alle app cloud.

![Scheda posizioni attività app cloud](../../media/cloud-app-activity-locations.png)

## <a name="monitor-health-for-infrastructure-workloads"></a>Monitorare l'integrità per i carichi di lavoro dell'infrastruttura

**Integrità dell'infrastruttura** mostra gli avvisi sullo stato di integrità per i carichi di lavoro dell'infrastruttura in Azure Defender.

Azure Defender fornisce la gestione unificata della sicurezza e Defender per Office 365 nei carichi di lavoro locali e cloud. È possibile raccogliere, cercare e analizzare i dati di sicurezza provenienti da origini diverse, inclusi firewall e altre soluzioni partner.

Per ulteriori informazioni, vedere la [documentazione di Azure Defender.](https://docs.microsoft.com/azure/security-center/)

![Scheda integrità dell'infrastruttura](../../media/infrastructure-health.png)
