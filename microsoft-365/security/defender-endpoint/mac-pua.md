---
title: Rilevare e bloccare applicazioni potenzialmente indesiderate con Microsoft Defender per Endpoint su Mac
description: Rilevare e bloccare le applicazioni potenzialmente indesiderate usando Microsoft Defender su Endpoint per Mac.
keywords: microsoft, defender, Microsoft Defender for Endpoint, mac, pua, pus
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 2d32dd96cd506ebf1752e48d2b7c66208b1abc11
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934538"
---
# <a name="detect-and-block-potentially-unwanted-applications-with-microsoft-defender-for-endpoint-on-macos"></a>Rilevare e bloccare le applicazioni potenzialmente indesiderate con Microsoft Defender per Endpoint in macOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


La funzionalità di protezione delle applicazioni potenzialmente indesiderate in Microsoft Defender for Endpoint su macOS può rilevare e bloccare i file PUA negli endpoint della rete.

Queste applicazioni non sono considerate virus, malware o altri tipi di minacce, ma possono eseguire azioni sugli endpoint che influiscono negativamente sulle prestazioni o sull'uso. PuA può anche fare riferimento ad applicazioni considerate di scarsa reputazione.

Queste applicazioni possono aumentare il rischio che la rete sia infettata da malware, causare infezioni da malware più difficili da identificare e può sprecare risorse IT nella pulizia delle applicazioni.

## <a name="how-it-works"></a>Come funziona

Microsoft Defender for Endpoint su macOS può rilevare e segnalare i file PUA. Se configurati in modalità di blocco, i file PUA vengono spostati in quarantena.

Quando viene rilevata una puA in un endpoint, Microsoft Defender for Endpoint su macOS presenta una notifica all'utente, a meno che le notifiche non siano state disabilitate. Il nome della minaccia conterrà la parola "Applicazione".

## <a name="configure-pua-protection"></a>Configurare la protezione puA

La protezione dell'applicazione di accesso pubblico in Microsoft Defender per Endpoint in macOS può essere configurata in uno dei modi seguenti:

- **Disattivato:** la protezione dell'applicazione può essere disabilitata.
- **Controllo:** i file PUA vengono riportati nei log del prodotto, ma non in Microsoft Defender Security Center. All'utente non viene presentata alcuna notifica e non viene eseguita alcuna azione da parte del prodotto.
- **Blocca:** i file PUA vengono riportati nei log del prodotto e Microsoft Defender Security Center. All'utente viene presentata una notifica e viene eseguita un'azione da parte del prodotto.

>[!WARNING]
>Per impostazione predefinita, la protezione puA è configurata in **modalità** di controllo.

È possibile configurare la modalità di gestione dei file PUA dalla riga di comando o dalla console di gestione.

### <a name="use-the-command-line-tool-to-configure-pua-protection"></a>Utilizzare lo strumento da riga di comando per configurare la protezione da accesso basato su account utente:

In Terminale, eseguire il comando seguente per configurare la protezione puA:

```bash
mdatp threat policy set --type potentially_unwanted_application --action [off|audit|block]
```

### <a name="use-the-management-console-to-configure-pua-protection"></a>Utilizzare la console di gestione per configurare la protezione dell'account di accesso alla posta elettronica:Use the management console to configure PUA protection:

Nell'organizzazione, è possibile configurare la protezione puA da una console di gestione, ad esempio JAMF o Intune, in modo analogo alla configurazione di altre impostazioni del prodotto. Per altre informazioni, vedi la sezione Impostazioni del [tipo di](mac-preferences.md#threat-type-settings) minaccia dell'argomento Impostare le preferenze per Microsoft Defender per Endpoint [su macOS.](mac-preferences.md)

## <a name="related-topics"></a>Argomenti correlati

- [Impostare le preferenze per Microsoft Defender per Endpoint in macOS](mac-preferences.md)
