---
title: Rilevare e bloccare applicazioni potenzialmente indesiderate con Microsoft Defender ATP per Linux
description: Rilevare e bloccare le applicazioni potenzialmente indesiderate usando Microsoft Defender ATP per Linux.
keywords: microsoft, defender, atp, linux, pua, pus
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: a6f2e2057ca78cb0e1114ed86829cd931dc1cd2b
ms.sourcegitcommit: 987f70e44e406ab6b1dd35f336a9d0c228032794
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/05/2021
ms.locfileid: "51587552"
---
# <a name="detect-and-block-potentially-unwanted-applications-with-microsoft-defender-for-endpoint-for-linux"></a>Rilevare e bloccare le applicazioni potenzialmente indesiderate con Microsoft Defender for Endpoint per Linux

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

La funzionalità di protezione delle applicazioni potenzialmente indesiderate in Defender for Endpoint per Linux può rilevare e bloccare i file PUA negli endpoint della rete.

Queste applicazioni non sono considerate virus, malware o altri tipi di minacce, ma possono eseguire azioni sugli endpoint che influiscono negativamente sulle prestazioni o sull'uso. PuA può anche fare riferimento ad applicazioni considerate di scarsa reputazione.

Queste applicazioni possono aumentare il rischio che la rete sia infettata da malware, causare infezioni da malware più difficili da identificare e può sprecare risorse IT nella pulizia delle applicazioni.

## <a name="how-it-works"></a>Funzionamento

Defender for Endpoint per Linux può rilevare e segnalare i file PUA. Se configurati in modalità di blocco, i file PUA vengono spostati in quarantena.

Quando viene rilevata una puA in un endpoint, Defender for Endpoint per Linux mantiene un record dell'infezione nella cronologia delle minacce. La cronologia può essere visualizzato dal portale di Microsoft Defender Security Center o tramite lo `mdatp` strumento da riga di comando. Il nome della minaccia conterrà la parola "Applicazione".

## <a name="configure-pua-protection"></a>Configurare la protezione puA

È possibile configurare la protezione puA in Defender for Endpoint per Linux in uno dei modi seguenti:

- **Disattivato:** la protezione dell'applicazione può essere disabilitata.
- **Controllo:** i file PUA vengono riportati nei log del prodotto, ma non in Microsoft Defender Security Center. Nella cronologia delle minacce non viene archiviato alcun record dell'infezione e non viene eseguita alcuna azione da parte del prodotto.
- **Blocca:** i file PUA vengono segnalati nei log del prodotto e in Microsoft Defender Security Center. Un record dell'infezione viene archiviato nella cronologia delle minacce e l'azione viene eseguita dal prodotto.

>[!WARNING]
>Per impostazione predefinita, la protezione puA è configurata in **modalità** di controllo.

È possibile configurare la modalità di gestione dei file PUA dalla riga di comando o dalla console di gestione.

### <a name="use-the-command-line-tool-to-configure-pua-protection"></a>Utilizzare lo strumento da riga di comando per configurare la protezione da accesso basato su account utente:

In Terminale, eseguire il comando seguente per configurare la protezione puA:

```bash
mdatp threat policy set --type potentially_unwanted_application --action [off|audit|block]
```

### <a name="use-the-management-console-to-configure-pua-protection"></a>Utilizzare la console di gestione per configurare la protezione dell'account di accesso alla posta elettronica:Use the management console to configure PUA protection:

Nella tua azienda puoi configurare la protezione puA da una console di gestione, ad esempio Pupazzo o Ansible, in modo analogo alla configurazione di altre impostazioni del prodotto. Per altre informazioni, vedi la sezione [Impostazioni del tipo di](linux-preferences.md#threat-type-settings) minaccia dell'articolo Impostare le preferenze per Defender per Endpoint per [Linux.](linux-preferences.md)

## <a name="related-articles"></a>Articoli correlati

- [Impostare le preferenze per Defender per Endpoint per Linux](linux-preferences.md)
