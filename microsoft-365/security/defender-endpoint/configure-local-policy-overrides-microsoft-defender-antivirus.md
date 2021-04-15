---
title: Configurare sostituzioni locali per le impostazioni di Microsoft Defender AV
description: Abilitare o disabilitare gli utenti dalla modifica locale delle impostazioni in Microsoft Defender AV.
keywords: sostituzione locale, criteri locali, criteri di gruppo, criteri di gruppo, blocco, unione, elenchi
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 02/13/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: f3c2b7ae70f42cb7ffc2deef1786ad43e65f33b6
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764640"
---
# <a name="prevent-or-allow-users-to-locally-modify-microsoft-defender-antivirus-policy-settings"></a>Impedire o consentire agli utenti di modificare localmente le impostazioni dei criteri di Microsoft Defender Antivirus

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**

- [Microsoft Defender per endpoint](/microsoft-365/security/defender-endpoint/)

Per impostazione predefinita, le impostazioni di Microsoft Defender Antivirus distribuite tramite un oggetto Criteri di gruppo agli endpoint della rete impediranno agli utenti di modificare localmente le impostazioni. È possibile modificare questa impostazione in alcuni casi.

Ad esempio, potrebbe essere necessario consentire a determinati gruppi di utenti (ad esempio ricercatori della sicurezza e investigatori delle minacce) un ulteriore controllo sulle singole impostazioni negli endpoint che usano.

## <a name="configure-local-overrides-for-microsoft-defender-antivirus-settings"></a>Configurare sostituzioni locali per le impostazioni di Microsoft Defender Antivirus

L'impostazione predefinita per questi criteri è **Disabled**.

Se sono impostati su **Abilitato,** gli utenti degli endpoint possono apportare modifiche all'impostazione associata all'app Sicurezza di [Windows,](microsoft-defender-security-center-antivirus.md) alle impostazioni di Criteri di gruppo locali e ai cmdlet di PowerShell (se appropriato).

Nella tabella seguente sono elencate tutte le impostazioni dei criteri di sostituzione e le istruzioni di configurazione per la caratteristica o l'impostazione associata.

Per configurare queste impostazioni:

1. Nel computer di gestione di Criteri di gruppo, aprire console Gestione Criteri di [gruppo,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e scegliere **Modifica**.

2. **Nell'Editor Gestione Criteri di gruppo** passare a Configurazione computer **e** fare clic su **Modelli amministrativi.**

3. Espandi l'albero **fino ai componenti di Windows > Microsoft Defender Antivirus** e quindi alla **posizione** specificata nella tabella seguente.

4. Fai doppio clic **sull'impostazione del** criterio come specificato nella tabella seguente e imposta l'opzione sulla configurazione desiderata. Fare **clic su OK** e ripetere l'operazione per tutte le altre impostazioni.

5. Distribuire l'oggetto Criteri di gruppo come di consueto.

Posizione | Impostazione | Articolo
---|---|---|---
MAPPE | Configurare l'override delle impostazioni locali per la segnalazione a Microsoft MAPS | [Abilitare la protezione basata sul cloud](enable-cloud-protection-microsoft-defender-antivirus.md)
Quarantena | Configurare l'override dell'impostazione locale per la rimozione degli elementi dalla cartella quarantena | [Configurare la correzione per le analisi](configure-remediation-microsoft-defender-antivirus.md)
Protezione in tempo reale | Configurare l'override delle impostazioni locali per il monitoraggio dell'attività di file e programmi nel computer | [Abilitare e configurare la protezione e il monitoraggio always-on di Microsoft Defender Antivirus](configure-real-time-protection-microsoft-defender-antivirus.md)
Protezione in tempo reale | Configurare l'override delle impostazioni locali per il monitoraggio dell'attività dei file in ingresso e in uscita | [Abilitare e configurare la protezione e il monitoraggio always-on di Microsoft Defender Antivirus](configure-real-time-protection-microsoft-defender-antivirus.md)
Protezione in tempo reale | Configurare l'override delle impostazioni locali per l'analisi di tutti i file e gli allegati scaricati | [Abilitare e configurare la protezione e il monitoraggio always-on di Microsoft Defender Antivirus](configure-real-time-protection-microsoft-defender-antivirus.md)
Protezione in tempo reale | Configurare l'override delle impostazioni locali per attivare il monitoraggio del comportamento | [Abilitare e configurare la protezione e il monitoraggio always-on di Microsoft Defender Antivirus](configure-real-time-protection-microsoft-defender-antivirus.md)
Protezione in tempo reale | Configurare l'override delle impostazioni locali per attivare la protezione in tempo reale | [Abilitare e configurare la protezione e il monitoraggio always-on di Microsoft Defender Antivirus](configure-real-time-protection-microsoft-defender-antivirus.md)
Correzione | Configurare l'override delle impostazioni locali per l'ora del giorno per eseguire un'analisi completa pianificata per completare la correzione | [Configurare la correzione per le analisi](configure-remediation-microsoft-defender-antivirus.md)
Analisi | Configurare l'override dell'impostazione locale per la percentuale massima di utilizzo della CPU | [Configurare ed eseguire analisi](run-scan-microsoft-defender-antivirus.md)
Analisi | Configurare l'override delle impostazioni locali per pianificare il giorno dell'analisi | [Configurare le analisi pianificate](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
Analisi | Configurare l'override delle impostazioni locali per il tempo di analisi rapida pianificato | [Configurare le analisi pianificate](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
Analisi | Configurare l'override delle impostazioni locali per il tempo di analisi pianificato | [Configurare le analisi pianificate](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
Analisi | Configurare l'override dell'impostazione locale per il tipo di analisi da utilizzare per un'analisi pianificata | [Configurare le analisi pianificate](scheduled-catch-up-scans-microsoft-defender-antivirus.md)

<a id="merge-lists"></a>

## <a name="configure-how-locally-and-globally-defined-threat-remediation-and-exclusions-lists-are-merged"></a>Configurare la modalità di unione degli elenchi di correzione ed esclusioni delle minacce definite a livello locale e globale

È inoltre possibile configurare il modo in cui gli elenchi definiti localmente vengono combinati o uniti a elenchi definiti a livello globale. Questa impostazione si applica agli [elenchi di esclusione,](configure-exclusions-microsoft-defender-antivirus.md) [agli elenchi di correzione](configure-remediation-microsoft-defender-antivirus.md)specificati e alla riduzione della superficie di [attacco.](/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction)

Per impostazione predefinita, gli elenchi configurati in Criteri di gruppo locali e nell'app Sicurezza di Windows vengono uniti a elenchi definiti dall'oggetto Criteri di gruppo appropriato distribuito nella rete. In caso di conflitti, l'elenco definito a livello globale ha la precedenza.

È possibile disabilitare questa impostazione per garantire che siano utilizzati solo elenchi definiti a livello globale, ad esempio quelli di qualsiasi oggetto Criteri di gruppo distribuito.

### <a name="use-group-policy-to-disable-local-list-merging"></a>Utilizzare Criteri di gruppo per disabilitare l'unione di elenchi locali

1. Nel computer di gestione di Criteri di gruppo, aprire console Gestione Criteri di [gruppo,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e scegliere **Modifica**.

2. **Nell'Editor Gestione Criteri di gruppo** passare a Configurazione computer **e** fare clic su **Modelli amministrativi.**

3. Espandi l'albero **fino ai componenti di Windows > Microsoft Defender Antivirus.**

4. Fare doppio clic su **Configura comportamento di unione dell'amministratore locale per** gli elenchi e impostare l'opzione su **Disabilitato.** Fare clic su **OK**.

> [!NOTE]
> Se si disabilita l'unione di elenchi locali, verranno sovrascritte le impostazioni di accesso controllato alle cartelle. Sostituisce inoltre tutte le cartelle protette o le app consentite impostate dall'amministratore locale. Per altre informazioni sulle impostazioni di accesso controllato alle cartelle, vedi [Consentire un'app bloccata in Sicurezza di Windows.](https://support.microsoft.com/help/4046851/windows-10-allow-blocked-app-windows-security)

## <a name="related-topics"></a>Argomenti correlati

- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Configurare l'interazione dell'utente finale con Microsoft Defender Antivirus](configure-end-user-interaction-microsoft-defender-antivirus.md)