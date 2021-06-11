---
title: Pianificare analisi antivirus tramite Criteri di gruppo
description: Utilizzare Criteri di gruppo per configurare le analisi antivirus
keywords: analisi rapida, analisi completa, pianificazione, criteri di gruppo, antivirus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/09/2021
ms.reviewer: pauhijbr, ksarens
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 6f6018ec8b514234ab4f98e3d5416b472ff88739
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879746"
---
# <a name="schedule-antivirus-scans-using-group-policy"></a>Pianificare analisi antivirus tramite Criteri di gruppo

**Si applica a:**

- [Microsoft Defender per endpoint](/microsoft-365/security/defender-endpoint/)

In questo articolo viene descritto come configurare le analisi pianificate tramite Criteri di gruppo. Per ulteriori informazioni sulla pianificazione delle analisi e sui tipi di analisi, vedere [Configure scheduled quick or full Antivirus Microsoft Defender scans](schedule-antivirus-scans.md). 

## <a name="configure-antivirus-scans-using-group-policy"></a>Configurare le analisi antivirus tramite Criteri di gruppo

1. Nel computer di gestione di Criteri di gruppo, nell'Editor Criteri di gruppo, passare **a** Configurazione computer Modelli amministrativi  >    >  **Windows Componenti**  >  **Antivirus Microsoft Defender**  >  **Analisi**.

2. Fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e quindi scegliere **Modifica**.

3. Specificare le impostazioni per l'oggetto Criteri di gruppo e quindi selezionare **OK.** 

4. Ripetere i passaggi da 1 a 4 per ogni impostazione che si desidera configurare.

5. Distribuire l'oggetto Criteri di gruppo come si fa normalmente. Per assistenza con gli oggetti Criteri di gruppo, vedere [Create a Group Policy Object.](/windows/security/threat-protection/windows-firewall/create-a-group-policy-object)

> [!TIP]
> Vedere gli [argomenti Gestire quando scaricare e](manage-protection-update-schedule-microsoft-defender-antivirus.md) applicare gli aggiornamenti della protezione e Impedire o consentire agli utenti di modificare [localmente le impostazioni dei](configure-local-policy-overrides-microsoft-defender-antivirus.md) criteri.

## <a name="group-policy-settings-for-scheduling-scans"></a>Impostazioni di Criteri di gruppo per la pianificazione delle analisi

| Posizione | Impostazione | Descrizione | Impostazione predefinita (se non configurata) |
|:---|:---|:---|:---|
| Analisi | Specificare il tipo di analisi da utilizzare per un'analisi pianificata | Analisi rapida |
| Analisi | Specificare il giorno della settimana per l'esecuzione di un'analisi pianificata | Specificare il giorno (o mai) in cui eseguire un'analisi. | Mai |
| Analisi | Specificare l'ora del giorno per l'esecuzione di un'analisi pianificata | Specificare il numero di minuti dopo la mezzanotte (ad esempio, **immettere 60** per l'1 di notte). | 02.00 |
| Radice | Tempo attività programmato casuale |In Antivirus Microsoft Defender, randomizzare l'ora di inizio dell'analisi a qualsiasi intervallo da 0 a 4 ore. <p>In [SCEP,](/mem/intune/protect/certificates-scep-configure)esegui analisi casuali a qualsiasi intervallo più o meno 30 minuti. Ciò può essere utile nelle macchine virtuali o nelle distribuzioni VDI. | Abilitato |

## <a name="group-policy-settings-for-scheduling-scans-for-when-an-endpoint-is-not-in-use"></a>Impostazioni di Criteri di gruppo per la pianificazione delle analisi quando un endpoint non è in uso

| Posizione | Impostazione | Descrizione | Impostazione predefinita (se non configurata) |
|:---|:---|:---|:---|
| Analisi | Avviare l'analisi pianificata solo quando il computer è in uso ma non è in uso | Le analisi pianificate non verranno eseguite, a meno che il computer non sia in uso | Abilitato |

> [!NOTE]
> Quando si pianificano analisi per i periodi in cui gli endpoint non sono in uso, le analisi non rispettano la configurazione della limitazione della CPU e sfruttano al meglio le risorse disponibili per completare l'analisi il più velocemente possibile.

## <a name="group-policy-settings-for-scheduling-remediation-required-scans"></a>Impostazioni di Criteri di gruppo per la pianificazione delle analisi necessarie per la correzione

| Posizione | Impostazione | Descrizione | Impostazione predefinita (se non configurata) |
|---|---|---|---|
| Correzione | Specificare il giorno della settimana in cui eseguire un'analisi completa pianificata per completare la correzione | Specificare il giorno (o mai) in cui eseguire un'analisi. | Mai |
| Correzione | Specificare l'ora del giorno in cui eseguire un'analisi completa pianificata per completare la correzione | Specificare il numero di minuti dopo la mezzanotte (ad esempio, **immettere 60** per le 13.00) | 02.00 |

## <a name="group-policy-settings-for-scheduling-daily-scans"></a>Impostazioni di Criteri di gruppo per la pianificazione delle analisi giornaliere

| Posizione | Impostazione | Descrizione | Impostazione predefinita (se non configurata) |
|:---|:---|:---|:---|
| Analisi | Specificare l'intervallo per l'esecuzione di analisi rapide al giorno | Specificare il numero di ore che devono trascorrere prima della successiva analisi rapida. Ad esempio, per eseguire ogni due ore, immettere **2**, per una volta al giorno, **immettere 24**. Immettere **0 per** non eseguire mai un'analisi rapida giornaliera. | Mai |
| Analisi | Specificare l'ora per un'analisi rapida giornaliera | Specificare il numero di minuti dopo la mezzanotte (ad esempio, **immettere 60** per le 13.00) | 02.00 |

## <a name="group-policy-settings-for-scheduling-scans-after-protection-updates"></a>Impostazioni di Criteri di gruppo per la pianificazione delle analisi dopo gli aggiornamenti della protezione

| Posizione | Impostazione | Descrizione | Impostazione predefinita (se non configurata)|
|:---|:---|:---|:---|
| Aggiornamenti delle firme | Attivare l'analisi dopo l'aggiornamento di Security Intelligence | Un'analisi verrà eseguita immediatamente dopo il download di un nuovo aggiornamento della protezione | Abilitato |

