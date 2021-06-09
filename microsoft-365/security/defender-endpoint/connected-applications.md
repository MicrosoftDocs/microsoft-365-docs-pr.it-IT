---
title: Applicazioni connesse in Microsoft Defender for Endpoint
ms.reviewer: ''
description: Visualizza le applicazioni partner connesse che usano il protocollo OAuth 2.0 standard per autenticare e fornire token da usare con Le API di Microsoft Defender for Endpoint.
keywords: partner, applicazioni, terze parti, connessioni, sentinelone, lookout, bitdefender, corrata, morphisec, paloalto, ziften, meglio mobile
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 06ef716e9deee7b20e8615bd22c93130ee18b77f
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845583"
---
# <a name="connected-applications-in-microsoft-defender-for-endpoint"></a>Applicazioni connesse in Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

Le applicazioni connesse si integrano con la piattaforma Defender for Endpoint usando le API. 

Le applicazioni usano il protocollo OAuth 2.0 standard per autenticare e fornire token da usare con le API di Microsoft Defender for Endpoint.  Inoltre, le Azure Active Directory (Azure AD) consentono agli amministratori tenant di impostare un controllo esplicito sulle API a cui è possibile accedere usando l'app corrispondente.
 
Dovrai seguire questi [passaggi](/microsoft-365/security/defender-endpoint/apis-intro) per usare le API con l'applicazione connessa.
 
## <a name="access-the-connected-application-page"></a>Accedere alla pagina dell'applicazione connessa
Nel menu di spostamento a sinistra seleziona **Partner & API Applicazioni**  >  **AAD connesse.**

 
## <a name="view-connected-application-details"></a>Visualizzare i dettagli dell'applicazione connessa
La pagina Applicazioni connesse fornisce informazioni sulle applicazioni di Azure AD connesse a Microsoft Defender for Endpoint nell'organizzazione. È possibile esaminare l'utilizzo delle applicazioni connesse: ultimo visto, numero di richieste nelle ultime 24 ore e tendenze delle richieste negli ultimi 30 giorni.

![Immagine delle app connesse](images/connected-apps.png)
 
## <a name="edit-reconfigure-or-delete-a-connected-application"></a>Modificare, riconfigurare o eliminare un'applicazione connessa
Il **collegamento Apri impostazioni applicazione** apre la pagina di gestione delle applicazioni di Azure AD corrispondente nel portale di Azure. Dal portale di Azure, è possibile gestire le autorizzazioni, riconfigurare o eliminare le applicazioni connesse.
