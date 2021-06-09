---
title: Configurare le funzionalità di analisi e correzione automatizzate
description: Configurare le funzionalità di analisi e correzione automatizzate in Microsoft Defender per Endpoint.
keywords: configurare, configurare, automatizzato, indagine, rilevamento, avvisi, correzione, risposta
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: JoeDavies-MSFT
ms.author: josephd
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: how-to
ms.date: 01/27/2021
ms.reviewer: ramarom, evaldm, isco, mabraitm, chriggs
ms.openlocfilehash: bd86458749db4019bb247a3664748b9891965754
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841333"
---
# <a name="configure-automated-investigation-and-remediation-capabilities-in-microsoft-defender-for-endpoint"></a>Configurare le funzionalità di analisi e correzione automatizzate in Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

Se l'organizzazione usa [Microsoft Defender for Endpoint](/windows/security/threat-protection/) (Defender for Endpoint), le funzionalità di analisi e correzione automatizzate possono risparmiare tempo e fatica per il team delle operazioni di sicurezza. [](/microsoft-365/security/defender-endpoint/automated-investigations) Come descritto in questo [post di blog,](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/enhance-your-soc-with-microsoft-defender-atp-automatic/ba-p/848946)queste funzionalità simulano i passaggi ideali che un analista della sicurezza adotta per analizzare e correggere le minacce. [Ulteriori informazioni sull'analisi e la correzione automatizzate.](/microsoft-365/security/defender-endpoint/automated-investigations) 

Per configurare l'analisi e la correzione automatizzate,
1. [Attivare le funzionalità](#turn-on-automated-investigation-and-remediation); e 
2. [Configurare i gruppi di dispositivi](#set-up-device-groups).

## <a name="turn-on-automated-investigation-and-remediation"></a>Attivare l'analisi e la correzione automatizzate

1. Come amministratore globale o amministratore della sicurezza, passare alla Microsoft Defender Security Center ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ) ed eseguire l'accesso.
2. Nel riquadro di spostamento scegliere **Impostazioni**.
3. Nella sezione **Generale** selezionare **Funzionalità avanzate**.
4. Attivare sia **Analisi automatizzata che** Risolvi **automaticamente gli avvisi**.

## <a name="set-up-device-groups"></a>Configurare gruppi di dispositivi

1. Nella Microsoft Defender Security Center ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ), nella pagina **Impostazioni,** in **Autorizzazioni,** selezionare **Gruppi di dispositivi.**
2. Seleziona **+ Aggiungi gruppo di dispositivi**.
3. Creare almeno un gruppo di dispositivi, come indicato di seguito:
   - Specificare un nome e una descrizione per il gruppo di dispositivi.
   - **Nell'elenco Livello di automazione** selezionare un livello, ad esempio **Completo, per correggere automaticamente le minacce.** Il livello di automazione determina se le azioni di correzione vengono eseguite automaticamente o solo dopo l'approvazione. Per ulteriori informazioni, vedere Livelli di automazione in analisi e [correzione automatizzate.](automation-levels.md)
   - Nella sezione **Membri** usa una o più condizioni per identificare e includere i dispositivi.
   - Nella scheda **Accesso utente** [](/azure/active-directory/fundamentals/active-directory-manage-groups?context=azure/active-directory/users-groups-roles/context/ugr-context) seleziona i gruppi Azure Active Directory che devono avere accesso al gruppo di dispositivi che stai creando.
4. Seleziona **Fatto** al termine della configurazione del gruppo di dispositivi.

## <a name="next-steps"></a>Passaggi successivi

- [Visitare il Centro notifiche per visualizzare le azioni di correzione in sospeso e completate](/microsoft-365/security/defender-endpoint/auto-investigation-action-center#the-action-center)
- [Rivedere e approvare le azioni in sospeso](/microsoft-365/security/defender-endpoint/manage-auto-investigation)

## <a name="see-also"></a>Vedere anche

- [Indirizzare i falsi positivi/negativi in Microsoft Defender per Endpoint](defender-endpoint-false-positives-negatives.md)
