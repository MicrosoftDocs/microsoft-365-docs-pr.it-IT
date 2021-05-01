---
title: Esempio di attacco tramite posta elettronica di phishing
description: Eseguire un'analisi di esempio di un attacco di phishing.
keywords: eventi, avvisi, analisi, correlazione, attacco, computer, dispositivi, utenti, identità, cassetta postale, posta elettronica, 365, Microsoft, M365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: fb3656a9d3f67d979c012d9cc316a10e65a72042
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114790"
---
# <a name="example-of-a-phishing-email-attack"></a>Esempio di attacco tramite posta elettronica di phishing

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Si applica a:**
- Microsoft 365 Defender

Microsoft 365 Defender può aiutare a rilevare gli allegati dannosi recapitati tramite posta elettronica. Poiché il Centro sicurezza e conformità di [Office 365](https://protection.office.com/) si integra con Microsoft 365 Defender, gli analisti della sicurezza possono avere visibilità sulle minacce provenienti da Office 365, ad esempio tramite allegati di posta elettronica.

Ad esempio, a un analista è stato assegnato un incidente in più fasi.
 
:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-incident.png" alt-text="Esempio di incidente in più fasi"::: 

Nella scheda **Avvisi** dell'evento imprevisto vengono visualizzati gli avvisi di Defender Office 365 e Microsoft Cloud App Security messaggi. L'analista può eseguire il drill-down in Defender per Office 365 avvisi selezionando gli avvisi dei messaggi di posta elettronica. I dettagli dell'avviso vengono visualizzati nel riquadro laterale.

:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-alerts.png" alt-text="Esempio di avviso tramite posta elettronica":::
 
Scorrendo ulteriormente verso il basso, vengono visualizzate ulteriori informazioni, che mostrano i file dannosi e l'utente che è stato tolto.

:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-impact.png" alt-text="Esempio di impatto su utenti e file di un avviso di posta elettronica":::
  
Selezionando **La pagina Apri avviso** si visualizza l'avviso specifico in cui è possibile visualizzare più informazioni in modo più dettagliato selezionando il collegamento. Il messaggio di posta elettronica effettivo può essere visualizzato selezionando **Visualizza messaggi in Esplora** risorse verso la parte inferiore del pannello.
 
:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-event-explorer.png" alt-text="Esempio dei dettagli di un avviso"::: 

In questo modo l'analista viene visualizzato nella pagina Gestione minacce in cui vengono visualizzati l'oggetto, il destinatario, il mittente e altre informazioni di posta elettronica. **ZAP** in **Azioni speciali indica** all'analista che è stata implementata la funzionalità di eliminazione automatica a zero ore. ZAP rileva e rimuove automaticamente i messaggi dannosi e di posta indesiderata dalle cassette postali dell'organizzazione. Per ulteriori informazioni, vedere [Zero-hour auto purge (ZAP) in Exchange Online](../office-365-security/zero-hour-auto-purge.md).

È possibile eseguire altre azioni su messaggi specifici selezionando **Azioni**. 
 
:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-actions.png" alt-text="Esempio di altre azioni che possono essere eseguite sui messaggi di posta elettronica"::: 

## <a name="next-step"></a>Passaggio successivo

Vedi il percorso [di analisi degli attacchi basati sull'identità.](first-incident-path-identity.md)

## <a name="see-also"></a>Vedere anche

- [Panoramica degli eventi imprevisti](incidents-overview.md)
- [Analizzare gli incidenti](investigate-incidents.md)
- [Gestire gli incidenti](manage-incidents.md)
