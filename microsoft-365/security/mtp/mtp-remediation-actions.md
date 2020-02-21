---
title: Azioni di correzione nelle funzionalità di analisi e risposta automatizzate in Microsoft Threat Protection
description: Panoramica delle funzionalità di indagine e reazione automatizzate in Microsoft Threat Protection
keywords: automatizzata, indagine, avviso, attivare, azione, correzione
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: 73bb90a0537df8e6f23e4e0e50a748aebda3a487
ms.sourcegitcommit: 2f117a6fd27a097ca25afa933dd088b69d483974
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/20/2020
ms.locfileid: "42175935"
---
# <a name="remediation-actions-in-automated-investigation-and-response-capabilities-in-microsoft-threat-protection"></a>Azioni di correzione nelle funzionalità di analisi e risposta automatizzate in Microsoft Threat Protection

**Si applica a:**
- Microsoft Threat Protection

Le funzionalità di ricerca e risposta automatizzate in Microsoft Threat Protection includono determinate azioni di correzione. Alcuni tipi di azioni di correzione vengono eseguiti nei dispositivi, detti anche endpoint. Altre azioni di correzione vengono eseguite sul contenuto della posta elettronica.

Nella tabella seguente sono riepilogate le azioni di correzione attualmente supportate in Microsoft Threat Protection: 

|Azioni correttive degli endpoint  |Azioni correttive della posta elettronica  |
|---------|---------|
|Quarantena del file<br/>Rimozione della chiave del Registro di sistema<br/>Termine del processo <br/>Interruzione del servizio <br/>Rimozione della chiave del Registro di sistema <br/>Disabilitazione del driver <br/>Rimozione di attività pianificate      |Eliminazione temporanea di messaggi di posta elettronica o cluster<br/>Blocco di URL (al momento del clic)<br/>Disattivazione dell'inoltro della posta elettronica esterna          |

Le azioni di correzione, sia che siano in attesa di approvazione o che sono già complete, possono essere visualizzate nel [Centro azioni](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).

## <a name="next-steps"></a>Passaggi successivi

- [Approvare o rifiutare le azioni relative all'indagine e reazione automatizzate](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)
- [Altre informazioni sul centro notifiche](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
