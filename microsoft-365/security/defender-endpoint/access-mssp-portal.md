---
title: Accedere al portale Microsoft 365 Defender clienti MSSP
description: Accedere al portale Microsoft 365 Defender clienti MSSP
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
ms.openlocfilehash: 8583b28adecd892ec6875faa934fd7ab08e5db11
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339587"
---
# <a name="access-the-microsoft-365-defender-mssp-customer-portal"></a>Accedere al portale Microsoft 365 Defender clienti MSSP

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**

- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

>Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)




>[!NOTE] 
>Questi set di passaggi sono indirizzati al provider di servizi condivisi. 

Per impostazione predefinita, i clienti MSSP accedono al proprio tenant Microsoft Defender Security Center tramite l'URL seguente: `https://securitycenter.windows.com` .
 

Gli MSSP, tuttavia, dovranno utilizzare un URL specifico del tenant nel formato seguente:  `https://securitycenter.windows.com?tid=customer_tenant_id` per accedere al portale dei clienti MSSP. 

In generale, gli MSSP dovranno essere aggiunti a ogni Azure AD del cliente MSSP che intende gestire.


Utilizzare la procedura seguente per ottenere l'ID tenant del cliente MSSP e quindi utilizzare l'ID per accedere all'URL specifico del tenant:

1. Come provider di servizi condivisi, accedi ad Azure AD con le tue credenziali. 

2. Passare dalla directory al tenant del cliente MSSP.

3.  Selezionare **Azure Active Directory > proprietà.** L'ID tenant è presente nel campo ID directory. 

4. Accedere al portale del cliente MSSP sostituendo il `customer_tenant_id` valore nell'URL seguente: `https://securitycenter.windows.com?tid=customer_tenant_id` .


## <a name="related-topics"></a>Argomenti correlati
- [Concedere a MSSP l'accesso al portale](grant-mssp-access.md)
- [Configurare le notifiche di avviso](configure-mssp-notifications.md)
- [Recuperare gli avvisi dal tenant del cliente](fetch-alerts-mssp.md)
