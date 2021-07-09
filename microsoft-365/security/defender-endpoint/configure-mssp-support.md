---
title: Configurare il supporto dei provider di servizi di sicurezza gestiti
description: Eseguire le operazioni necessarie per configurare l'integrazione di MSSP con Microsoft Defender for Endpoint
keywords: provider di servizi di sicurezza gestiti, mssp, configurare, integrazione
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: d82bffd6eea54256f2c6773f843030a19e27275d
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339359"
---
# <a name="configure-managed-security-service-provider-integration"></a>Configurazione integrazione con il provider di servizi di sicurezza gestita

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)
 
[!include[Prerelease information](../../includes/prerelease.md)]

Per abilitare l'integrazione mssp (Managed Security Service Provider) è necessario eseguire la procedura di configurazione seguente.

>[!NOTE]
>In questo articolo vengono utilizzati i termini seguenti per distinguere tra il provider di servizi e l'utente del servizio:
> - MSSP: organizzazioni di sicurezza che offrono di monitorare e gestire i dispositivi di sicurezza per un'organizzazione.
> - Clienti MSSP: organizzazioni che si impegnano nei servizi di MSSP.

L'integrazione consentirà agli MSSP di eseguire le azioni seguenti:

- Ottenere l'accesso al portale Microsoft 365 Defender clienti MSSP
- Ricevere notifiche tramite posta elettronica e 
- Recuperare gli avvisi tramite gli strumenti di gestione degli eventi e delle informazioni di sicurezza

Prima che gli MSSP possano eseguire queste azioni, il cliente di MSSP dovrà concedere l'accesso al tenant Defender for Endpoint in modo che possa accedere al portale. 
 

In genere, i clienti MSSP esereranno la procedura di configurazione iniziale per concedere agli MSSP l'accesso al tenant Windows Defender Security Central. Dopo aver concesso l'accesso, il cliente MSSP o il provider mssp può eseguire altri passaggi di configurazione.


In generale, è necessario eseguire i passaggi di configurazione seguenti:


- **Concedere al provider mssp l'accesso Microsoft 365 Defender** <br>
Questa azione deve essere eseguita dal cliente MSSP. Concede al provider mssp l'accesso al tenant Defender for Endpoint del cliente MSSP.
 

- **Configurare le notifiche di avviso inviate a MSSP** <br>
Questa azione può essere eseguita dal cliente MSSP o da MSSP. In questo modo gli MSSP possono sapere quali avvisi devono essere indirizzati al cliente MSSP.

- **Recuperare gli avvisi dal tenant del cliente MSSP nel sistema SIEM** <br> Questa azione viene eseguita dal provider di servizi condivisi. Consente agli MSSP di recuperare gli avvisi negli strumenti SIEM.

- **Recuperare gli avvisi dal tenant del cliente MSSP usando le API** <br>
Questa azione viene eseguita dal provider di servizi condivisi. Consente agli MSSP di recuperare gli avvisi usando le API.

## <a name="multi-tenant-access-for-mssps"></a>Accesso multi-tenant per mssp
Per informazioni su come implementare un accesso delegato multi-tenant, vedere [Accesso multi-tenant per i provider di servizi di sicurezza gestiti.](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/multi-tenant-access-for-managed-security-service-providers/ba-p/1533440)



## <a name="related-topics"></a>Argomenti correlati
- [Concedere a MSSP l'accesso al portale](grant-mssp-access.md)
- [Accedere al portale clienti MSSP](access-mssp-portal.md)
- [Configurare le notifiche di avviso](configure-mssp-notifications.md)
- [Recuperare gli avvisi dal tenant del cliente](fetch-alerts-mssp.md)

