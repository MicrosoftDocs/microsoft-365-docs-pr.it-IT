---
title: Rivedere le minacce individuate e intervenire
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid: MET150
description: Scopri come esaminare e gestire le minacce rilevate da Microsoft Defender Antivirus nei dispositivi Windows 10.
ms.openlocfilehash: 15e99fb75e4a3ac1af842ca7d0b900e02cbc6bd4
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50912787"
---
# <a name="review-detected-threats-and-take-action"></a>Rivedere le minacce individuate e intervenire

Non appena viene rilevato un file o un software dannoso, Microsoft Defender Antivirus lo blocca e ne impedisce l'esecuzione. E con la protezione consegnata nel cloud attivata, le minacce appena rilevate vengono aggiunte al motore antivirus e antimalware in modo che anche gli altri dispositivi e utenti siano protetti.

Microsoft Defender Antivirus rileva e protegge dai seguenti tipi di minacce:

- Virus, malware e minacce basate sul Web nei dispositivi
- Tentativi di phishing
- Tentativi di furto di dati

Come professionista/amministratore IT, puoi visualizzare le informazioni sui rilevamenti delle minacce nei dispositivi [Windows 10](/mem/intune/enrollment/device-enrollment) registrati in Intune nell'interfaccia di amministrazione di Microsoft 365. Verranno visualizzate informazioni di riepilogo, ad esempio:

- Numero di dispositivi che necessitano di protezione antivirus
- Numero di dispositivi non conformi ai criteri di sicurezza
- Numero di minacce attualmente attive, attenuate o risolte

Sono disponibili diverse opzioni per visualizzare informazioni specifiche sui rilevamenti di minacce e sui dispositivi:

- Pagina **Dispositivi attivi** nell'interfaccia di amministrazione di Microsoft <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">365.</a> Vedi [Gestire i rilevamenti delle minacce nella pagina Dispositivi attivi](#manage-threat-detections-on-the-active-devices-page) in questo articolo.
- Pagina **Minacce attive** nell'interfaccia di amministrazione di Microsoft <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">365.</a> Vedere [Gestire i rilevamenti delle minacce nella pagina Minacce attive](#manage-threat-detections-on-the-active-threats-page) in questo articolo.
- Pagina **Antivirus** in <a href="https://go.microsoft.com/fwlink/p/?linkid=2150463" target="_blank">Microsoft Endpoint Manager</a>. Vedere [Gestire i rilevamenti delle minacce in Microsoft Endpoint Manager](#manage-threat-detections-in-microsoft-endpoint-manager) in questo articolo.

Per altre informazioni, vedi [Minacce rilevate da Microsoft Defender Antivirus.](threats-detected-defender-av.md)

## <a name="manage-threat-detections-on-the-active-devices-page"></a>Gestire i rilevamenti delle minacce nella **pagina Dispositivi** attivi

La procedura seguente si applica ai clienti con Microsoft 365 Business Premium.

1. Accedere all'interfaccia di amministrazione di Microsoft 365 e <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> accedere.

2. Nella pagina di spostamento seleziona **Dispositivi**  >  **Dispositivi dispositivi attivi.** Vedrai un elenco di dispositivi attivi e dettagli, ad esempio lo stato di protezione, lo stato di protezione antivirus (AV) e il numero di minacce attive rilevate.

3. Seleziona un dispositivo per visualizzare altri dettagli sul dispositivo e sulle azioni disponibili. Viene visualizzato un riquadro a comparsa con suggerimenti e azioni disponibili, ad esempio Criteri di **aggiornamento,** **Aggiorna antivirus,** Esegui analisi **rapida,** Esegui analisi **completa** e altro ancora.

## <a name="manage-threat-detections-on-the-active-threats-page"></a>Gestire i rilevamenti delle minacce nella **pagina Minacce** attive

La procedura seguente si applica ai clienti con Microsoft 365 Business Premium. [I dispositivi Windows 10 devono essere protetti](./secure-win-10-pcs.md) e [registrati in Intune.](/mem/intune/enrollment/windows-enrollment-methods)

> [!NOTE]
> La **scheda Microsoft Defender Antivirus** e la pagina **Minacce** attive sono in fase di implementazione, quindi potresti non avere accesso immediato ad esse.

1. Accedere all'interfaccia di amministrazione di Microsoft 365 e <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> accedere.

2. Nella scheda **Microsoft Defender Antivirus** seleziona Visualizza minacce **attive.** In alternativa, nel riquadro di spostamento selezionare **Integrità**  >  **Minacce & antivirus**.)

3. Nella pagina **Minacce attive** selezionare una minaccia rilevata per ulteriori informazioni. Viene visualizzato un riquadro a comparsa con informazioni dettagliate su tale minaccia, inclusi i dispositivi interessati.

4. Nel riquadro a comparsa selezionare un dispositivo per visualizzare le azioni disponibili, ad esempio Criteri di **aggiornamento,** **Aggiorna antivirus,** **Esegui analisi rapida** e altro ancora.

## <a name="actions-you-can-take"></a>Azioni che è possibile eseguire

Quando si visualizzano i dettagli su minacce o dispositivi specifici, vengono visualizzati suggerimenti e una o più azioni che è possibile eseguire. Nella tabella seguente vengono descritte le azioni che è possibile visualizzare.<br><br>

| Azione | Descrizione |
|--|--|
| Configurare la protezione | I criteri di protezione dalle minacce devono essere configurati. Selezionare il collegamento per passare alla pagina di configurazione dei criteri.<br><br>Hai bisogno di assistenza? Vedi [Gestire la sicurezza dei dispositivi con i criteri di sicurezza degli endpoint in Microsoft Intune.](/mem/intune/protect/endpoint-security-policy) |
| Aggiornare i criteri | I criteri di protezione antivirus e in tempo reale devono essere aggiornati o configurati. Selezionare il collegamento per passare alla pagina di configurazione dei criteri.<br><br>Hai bisogno di assistenza? Vedi [Gestire la sicurezza dei dispositivi con i criteri di sicurezza degli endpoint in Microsoft Intune.](/mem/intune/protect/endpoint-security-policy) |
| Eseguire un'analisi rapida | Avvia una rapida analisi antivirus nel dispositivo, concentrandosi sulle posizioni comuni in cui potrebbe essere registrato malware, ad esempio chiavi del Registro di sistema e cartelle di avvio di Windows note. |
| Eseguire l'analisi completa | Avvia un'analisi antivirus completa nel dispositivo, concentrandosi sulle posizioni comuni in cui potrebbe essere registrato il malware e includendo ogni file e cartella nel dispositivo. I risultati vengono inviati a [Microsoft Endpoint Manager.](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager) |
| Aggiornare antivirus | Richiede al dispositivo di ottenere aggiornamenti [di intelligence per la sicurezza](https://go.microsoft.com/fwlink/?linkid=2149926) per la protezione antivirus e antimalware. |
| Riavvia dispositivo | Forza il riavvio di un dispositivo Windows 10 entro cinque minuti.<br><br>**IMPORTANTE:** Il proprietario o l'utente del dispositivo non viene avvisato automaticamente del riavvio e potrebbe perdere il lavoro non salvato. |

## <a name="manage-threat-detections-in-microsoft-endpoint-manager"></a>Gestire i rilevamenti delle minacce in Microsoft Endpoint Manager

È possibile utilizzare Microsoft Endpoint Manager per gestire i rilevamenti delle minacce. I dispositivi Windows 10 devono [essere registrati in Intune](/mem/intune/enrollment/windows-enrollment-methods) (parte di Microsoft Endpoint Manager).

1. Accedere all'interfaccia di amministrazione di Microsoft Endpoint Manager e <a href="https://go.microsoft.com/fwlink/p/?linkid=2150463" target="_blank">https://endpoint.microsoft.com</a> accedere.

2. Nel riquadro di spostamento selezionare **Sicurezza endpoint**.

3. In **Gestisci** selezionare **Antivirus.** Vedrai diverse schede, ad esempio **Riepilogo,** Endpoint non **integri di Windows 10** e Malware rilevato **da Windows 10.**

4. Esaminare le informazioni nelle schede disponibili e quindi eseguire le azioni necessarie.

Ad esempio, si supponga che i dispositivi siano elencati nella scheda Malware rilevato **da Windows 10.** Quando si seleziona un dispositivo, sono disponibili determinate azioni, ad esempio  **Riavvia,** Analisi **rapida,** Analisi **completa,** Sincronizzazione o **Aggiorna firme.** Seleziona un'azione per il dispositivo.

Nella tabella seguente vengono descritte le azioni che è possibile visualizzare in Microsoft Endpoint Manager.<br><br>

| Azione | Descrizione |
|--|--|
| Riavvia | Forza il riavvio di un dispositivo Windows 10 entro cinque minuti.<br><br>**IMPORTANTE:** Il proprietario o l'utente del dispositivo non viene avvisato automaticamente del riavvio e potrebbe perdere il lavoro non salvato. |
| Analisi rapida | Avvia una rapida analisi antivirus nel dispositivo, concentrandosi sulle posizioni comuni in cui potrebbe essere registrato malware, ad esempio chiavi del Registro di sistema e cartelle di avvio di Windows note. I risultati vengono inviati a [Microsoft Endpoint Manager.](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager) |
| Analisi completa | Avvia un'analisi antivirus completa nel dispositivo, concentrandosi sulle posizioni comuni in cui potrebbe essere registrato il malware e includendo ogni file e cartella nel dispositivo. I risultati vengono inviati a [Microsoft Endpoint Manager.](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager) |
| Sincronizza | Richiede un dispositivo per l'archiviazione con Intune (parte di Microsoft Endpoint Manager). Quando il dispositivo esegue l'archiviazione, il dispositivo riceve eventuali azioni o criteri in sospeso assegnati al dispositivo. |
| Aggiornare le firme | Richiede al dispositivo di ottenere aggiornamenti [di intelligence per la sicurezza](https://go.microsoft.com/fwlink/?linkid=2149926) per la protezione antivirus e antimalware. |

> [!TIP]
> Per altre informazioni, vedi [Azioni remote per i dispositivi.](/mem/intune/protect/endpoint-security-manage-devices#remote-actions-for-devices)

## <a name="how-to-submit-a-file-for-malware-analysis"></a>Come inviare un file per l'analisi malware

Se si dispone di un file che si pensa sia stato perso o erroneamente classificato come malware, è possibile inviare tale file a Microsoft per l'analisi del malware. Gli utenti e gli amministratori IT possono inviare un file per l'analisi. Visitare [https://www.microsoft.com/wdsi/filesubmission](https://www.microsoft.com/wdsi/filesubmission) .