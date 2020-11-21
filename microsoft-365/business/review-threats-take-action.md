---
title: Esaminare le minacce rilevate e intervenire
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
description: Informazioni su come esaminare e gestire le minacce rilevate da Microsoft Defender antivirus nei dispositivi Windows 10.
ms.openlocfilehash: 21830b91bfbb88fdd5d5139ee07c4dfb35f5b875
ms.sourcegitcommit: 20d1158c54a5058093eb8aac23d7e4dc68054688
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2020
ms.locfileid: "49376703"
---
# <a name="review-detected-threats-and-take-action"></a>Esaminare le minacce rilevate e intervenire

Non appena viene rilevato un file o un software dannoso, Microsoft Defender antivirus lo blocca e ne impedisce l'esecuzione. E con la protezione fornita dal cloud attivata, le minacce appena rilevate vengono aggiunte al motore antivirus e antimalware in modo che anche gli altri dispositivi e gli altri utenti siano protetti.

Microsoft Defender Antivirus rileva e protegge i tipi di minacce seguenti:

- Virus, malware e minacce basate sul Web sui dispositivi
- Tentativi di phishing
- Tentativi di furto dei dati

Come un professionista IT/amministratore, è possibile visualizzare le informazioni sui rilevamenti di minacce nei [dispositivi Windows 10 registrati in Intune](/mem/intune/enrollment/device-enrollment) nell'interfaccia di amministrazione di Microsoft 365. Verranno visualizzate informazioni di riepilogo, ad esempio:

- Il numero di dispositivi necessari per la protezione antivirus
- Numero di dispositivi non conformi ai criteri di sicurezza
- Quante minacce sono attualmente attive, attenuate o risolte

Sono disponibili diverse opzioni per visualizzare informazioni specifiche sui dispositivi e sui rilevamenti di minacce:

- La pagina **dispositivi attivi** nell'interfaccia di <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">amministrazione di Microsoft 365</a>. Vedere [gestire i rilevamenti di minacce nella pagina dispositivi attivi](#manage-threat-detections-on-the-active-devices-page) in questo articolo.
- La pagina **minacce attive** nell'interfaccia di <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">amministrazione di Microsoft 365</a>. Vedere [gestire i rilevamenti di minacce nella pagina minacce attive](#manage-threat-detections-on-the-active-threats-page) in questo articolo.
- La pagina **antivirus** in <a href="https://endpoint.microsoft.com" target="_blank">Microsoft Endpoint Manager</a>. Vedere [gestire i rilevamenti di minacce in Microsoft Endpoint Manager](#manage-threat-detections-in-microsoft-endpoint-manager) in questo articolo.

Per ulteriori informazioni, vedere [minacce rilevate da Microsoft Defender Antivirus](threats-detected-defender-av.md).

## <a name="manage-threat-detections-on-the-active-devices-page"></a>Gestire i rilevamenti di minacce nella pagina **dispositivi attivi**

La procedura seguente si applica ai clienti che dispongono di Microsoft 365 Business Premium.

1. Accedere all'interfaccia di amministrazione di Microsoft 365 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> ed eseguire l'accesso.

2. Nella pagina navigazione selezionare **dispositivi**  >  **attivi**. Verrà visualizzato un elenco di dispositivi attivi e dettagli, ad esempio lo stato di protezione, lo stato di protezione antivirus (AV) e il numero di minacce attive rilevate.

3. Selezionare un dispositivo per visualizzare ulteriori dettagli sul dispositivo e sulle azioni disponibili. Viene aperto un riquadro a comparsa con suggerimenti e azioni disponibili, ad esempio **criteri di aggiornamento**, **aggiornamento antivirus**, **esecuzione di analisi rapida**, **esecuzione dell'analisi completa** e altro ancora.

## <a name="manage-threat-detections-on-the-active-threats-page"></a>Gestire i rilevamenti di minacce nella pagina **minacce attive**

La procedura seguente si applica ai clienti che dispongono di Microsoft 365 business. I [dispositivi Windows 10 devono essere protetti](/microsoft-365/business/secure-win-10-pcs) e [registrati in Intune](/mem/intune/enrollment/windows-enrollment-methods).

> [!NOTE]
> La pagina **Microsoft Defender Antivirus** e le **minacce attive** vengono distribuite in fasi, pertanto non è possibile accedervi immediatamente.

1. Accedere all'interfaccia di amministrazione di Microsoft 365 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> ed eseguire l'accesso.

2. Nella scheda **Microsoft Defender Antivirus** selezionare **Visualizza minacce attive**. In alternativa, nel riquadro di spostamento selezionare **integrità**  >  **Minacce & antivirus**.)

3. Nella pagina **minacce attive** selezionare una minaccia rilevata per ulteriori informazioni su di esso. Verrà aperto un riquadro a comparsa con informazioni dettagliate su tale minaccia, inclusi i dispositivi coinvolti.

4. Nel riquadro a comparsa, selezionare un dispositivo per visualizzare le azioni disponibili, ad esempio **criteri di aggiornamento**, **aggiornamento antivirus**, **esecuzione di analisi rapida** e altro ancora.

## <a name="actions-you-can-take"></a>Azioni che è possibile eseguire

Quando si visualizzano i dettagli relativi a minacce o dispositivi specifici, verranno visualizzati suggerimenti e una o più azioni che è possibile eseguire. Nella tabella seguente vengono descritte le azioni che è possibile visualizzare.<br><br>

| Azione | Descrizione |
|--|--|
| Configurare la protezione | I criteri di protezione dalle minacce devono essere configurati. Selezionare il collegamento per passare alla pagina di configurazione del criterio.<br><br>Hai bisogno di assistenza? Vedere [gestire la sicurezza dei dispositivi con i criteri di sicurezza di endpoint in Microsoft Intune](/mem/intune/protect/endpoint-security-policy). |
| Criteri di aggiornamento | I criteri di protezione antivirus e in tempo reale devono essere aggiornati o configurati. Selezionare il collegamento per passare alla pagina Configurazione dei criteri.<br><br>Hai bisogno di assistenza? Vedere [gestire la sicurezza dei dispositivi con i criteri di sicurezza di endpoint in Microsoft Intune](/mem/intune/protect/endpoint-security-policy). |
| Eseguire un'analisi rapida | Avvia un'analisi antivirus rapida sul dispositivo, concentrandosi su posizioni comuni in cui potrebbe essere registrato il malware, ad esempio le chiavi del registro di sistema e le cartelle di avvio di Windows note. |
| Eseguire l'analisi completa | Avvia un'analisi antivirus completa sul dispositivo, concentrandosi su posizioni comuni in cui potrebbe essere registrato il malware e includendo tutti i file e le cartelle presenti nel dispositivo. I risultati vengono inviati a [Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager). |
| Aggiornamento antivirus | Richiede il dispositivo per ottenere [gli aggiornamenti di sicurezza intelligence](https://go.microsoft.com/fwlink/?linkid=2149926) per la protezione antivirus e antimalware. |
| Riavvia il dispositivo | Forza il riavvio di un dispositivo Windows 10 entro cinque minuti.<br><br>**Importante:** Il proprietario o l'utente del dispositivo non viene automaticamente informato del riavvio e potrebbe perdere il lavoro non salvato. |

## <a name="manage-threat-detections-in-microsoft-endpoint-manager"></a>Gestire i rilevamenti di minacce in Microsoft Endpoint Manager

È possibile utilizzare Microsoft Endpoint Manager per gestire i rilevamenti di minacce. I dispositivi Windows 10 devono essere [registrati in Intune](/mem/intune/enrollment/windows-enrollment-methods) (parte di Microsoft Endpoint Manager).

1. Accedere all'interfaccia di amministrazione di Microsoft Endpoint Manager <a href="https://endpoint.microsoft.com" target="_blank">https://endpoint.microsoft.com</a> ed eseguire l'accesso.

2. Nel riquadro di spostamento selezionare **Endpoint Security**.

3. In **Gestisci** selezionare **antivirus**. Verranno visualizzate diverse schede, ad esempio **Riepilogo**, **endpoint non integri di Windows 10** e **malware rilevati da Windows 10**.

4. Rivedere le informazioni sulle schede disponibili e quindi eseguire tutte le operazioni necessarie.

Si supponga, ad esempio, che i dispositivi siano elencati nella scheda **malware rilevato di Windows 10** . Quando si seleziona un dispositivo, sono disponibili determinate azioni, ad esempio **riavvio**, **analisi rapida**, **analisi completa**, **sincronizzazione** o **aggiornamento**. Selezionare un'azione per il dispositivo.

Nella tabella seguente vengono descritte le azioni che è possibile visualizzare in Microsoft Endpoint Manager.<br><br>

| Azione | Descrizione |
|--|--|
| Riavvia | Forza il riavvio di un dispositivo Windows 10 entro cinque minuti.<br><br>**Importante:** Il proprietario o l'utente del dispositivo non viene automaticamente informato del riavvio e potrebbe perdere il lavoro non salvato. |
| Analisi rapida | Avvia un'analisi antivirus rapida sul dispositivo, concentrandosi su posizioni comuni in cui potrebbe essere registrato il malware, ad esempio le chiavi del registro di sistema e le cartelle di avvio di Windows note. I risultati vengono inviati a [Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager). |
| Analisi completa | Avvia un'analisi antivirus completa sul dispositivo, concentrandosi su posizioni comuni in cui potrebbe essere registrato il malware e includendo tutti i file e le cartelle presenti nel dispositivo. I risultati vengono inviati a [Microsoft Endpoint Manager](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager). |
| Sincronizza | Richiede l'archiviazione di un dispositivo con Intune (parte di Microsoft Endpoint Manager). Quando il dispositivo esegue la verifica, il dispositivo riceve eventuali azioni o criteri in sospeso assegnati al dispositivo. |
| Aggiornare le firme | Richiede il dispositivo per ottenere [gli aggiornamenti di sicurezza intelligence](https://go.microsoft.com/fwlink/?linkid=2149926) per la protezione antivirus e antimalware. |

> [!TIP]
> Per ulteriori informazioni, vedere [Remote actions for Devices](/mem/intune/protect/endpoint-security-manage-devices#remote-actions-for-devices).

## <a name="how-to-submit-a-file-for-malware-analysis"></a>Come inviare un file per l'analisi antimalware

Se si dispone di un file che si ritiene mancato o classificato erroneamente come malware, è possibile inviare tale file a Microsoft per l'analisi antimalware. Gli utenti e gli amministratori IT possono inviare un file per l'analisi. Visitare [https://www.microsoft.com/wdsi/filesubmission](https://www.microsoft.com/wdsi/filesubmission) .
