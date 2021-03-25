---
title: Configurare le notifiche di avviso inviate a MSSP
description: Configurare le notifiche di avviso inviate a MSSP
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
ms.openlocfilehash: 67f7081e72b5ecc8bdb077f0537cf0cf92df38b9
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166054"
---
# <a name="configure-alert-notifications-that-are-sent-to-mssps"></a>Configurare le notifiche di avviso inviate a MSSP 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender ATP](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-mssp-support-abovefoldlink)


>[!NOTE]
>Questo passaggio può essere eseguito dal cliente MSSP o da MSSP. Agli MSSP devono essere concesse le autorizzazioni appropriate per configurarlo per conto del cliente MSSP.

Dopo aver concesso l'accesso al portale, è possibile creare regole di notifica degli avvisi in modo che i messaggi di posta elettronica siano inviati agli MSSP quando vengono creati avvisi associati al tenant e vengono soddisfatte le condizioni impostate.

 
Per ulteriori informazioni, vedere [Creare regole per le notifiche di avviso.](configure-email-notifications.md#create-rules-for-alert-notifications)
 

Queste caselle di controllo devono essere selezionate:
- **Includi nome organizzazione** - Il nome del cliente verrà aggiunto alle notifiche di posta elettronica
- **Includi collegamento al portale specifico del tenant** - L'URL del collegamento avviso avrà un parametro specifico del tenant (tid=target_tenant_id) che consente l'accesso diretto al portale tenant di destinazione


## <a name="related-topics"></a>Argomenti correlati
- [Concedere a MSSP l'accesso al portale](grant-mssp-access.md)
- [Accedere al portale dei clienti MSSP](access-mssp-portal.md)
- [Recuperare gli avvisi dal tenant del cliente](fetch-alerts-mssp.md)
