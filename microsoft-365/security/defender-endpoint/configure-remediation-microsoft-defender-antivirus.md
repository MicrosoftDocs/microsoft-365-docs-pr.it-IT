---
title: Configurare la correzione per i rilevamenti di Microsoft Defender Antivirus
description: Configurare le Antivirus Microsoft Defender quando rileva una minaccia e per quanto tempo i file in quarantena devono essere conservati nella cartella di quarantena
keywords: correzione, correzione, rimozione, minacce, quarantena, analisi, ripristino
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.topic: article
ms.custom: nextgen
ms.date: 03/16/2021
ms.reviewer: ''
manager: dansimp
ms.openlocfilehash: 9b765d14e31d6c4890aeace41e4fe79bafdd889e
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925576"
---
# <a name="configure-remediation-for-microsoft-defender-antivirus-detections"></a>Configurare la correzione per i rilevamenti di Microsoft Defender Antivirus


**Si applica a:**

- [Microsoft Defender per endpoint](/microsoft-365/security/defender-endpoint/)

Quando Antivirus Microsoft Defender un'analisi, tenta di correggere o rimuovere le minacce rilevate. È possibile configurare il modo Antivirus Microsoft Defender affrontare determinate minacce, se deve essere creato un punto di ripristino prima della correzione e quando le minacce devono essere rimosse.

In questo articolo viene descritto come configurare queste impostazioni utilizzando Criteri di gruppo, ma è anche possibile utilizzare Microsoft Endpoint Configuration Manager [e](/configmgr/protect/deploy-use/endpoint-antimalware-policies#threat-overrides-settings) [Microsoft Intune](/intune/device-restrictions-configure). 

È inoltre possibile utilizzare il [ `Set-MpPreference` cmdlet PowerShell o](/powershell/module/defender/set-mppreference) la classe [ `MSFT_MpPreference` WMI](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) per configurare queste impostazioni.

## <a name="configure-remediation-options"></a>Configurare le opzioni di correzione

1. Nel computer di gestione di Criteri di gruppo, aprire console Gestione Criteri di [gruppo,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e scegliere **Modifica**.

2. **Nell'Editor Gestione Criteri di gruppo** passare a Configurazione **computer** e selezionare **Modelli amministrativi.**

3. Espandere l'albero per **Windows componenti**  >  **Antivirus Microsoft Defender**. 

4. Usando la tabella seguente, selezionare un percorso e quindi modificare il criterio in base alle esigenze. 

5. Selezionare **OK**.

|Posizione | Impostazione | Descrizione | Impostazione predefinita (se non configurata) |
|:---|:---|:---|:---|
|Analisi | Creare un punto di ripristino del sistema | Verrà creato un punto di ripristino del sistema ogni giorno prima del tentativo di pulizia o analisi | Disattivato|
|Analisi | Attivare la rimozione di elementi dalla cartella cronologia analisi | Specificare il numero di giorni in cui gli elementi devono essere conservati nella cronologia dell'analisi | 30 giorni |
|Radice | Disattivare la correzione di routine | È possibile specificare se Antivirus Microsoft Defender correggere automaticamente le minacce o se deve chiedere all'utente dell'endpoint cosa fare. | Disabilitato (le minacce vengono corretti automaticamente) |
|Quarantena | Configurare la rimozione degli elementi dalla cartella quarantena | Specificare per quanti giorni gli elementi devono essere mantenuti in quarantena prima di essere rimossi | 90 giorni |
|Minacce | Specificare i livelli di avviso per le minacce a cui non deve essere eseguita l'azione predefinita quando viene rilevata | A ogni minaccia rilevata da Antivirus Microsoft Defender viene assegnato un livello di minaccia (basso, medio, alto o grave). È possibile utilizzare questa impostazione per definire la modalità di correzione di tutte le minacce per ognuno dei livelli di minaccia (in quarantena, rimosse o ignorate) | Non applicabile |
|Minacce | Specificare le minacce su cui non deve essere eseguita l'azione predefinita quando viene rilevata | Specificare la modalità di correzione delle minacce specifiche (usando il relativo ID minaccia). È possibile specificare se la minaccia specifica deve essere messo in quarantena, rimossa o ignorata | Non applicabile |

> [!IMPORTANT]
> Antivirus Microsoft Defender consente di rilevare e correggere i file in base a molti fattori. A volte, il completamento di una correzione richiede un riavvio. Anche se il rilevamento viene successivamente determinato come falso positivo, è necessario completare il riavvio per assicurarsi che tutti i passaggi di correzione aggiuntivi siano stati completati.
>
> Se si è certi Antivirus Microsoft Defender messo in quarantena un file in base a un falso positivo, è possibile ripristinare il file dalla quarantena dopo il riavvio del dispositivo. Vedere [Restore quarantined files in Antivirus Microsoft Defender](restore-quarantined-files-microsoft-defender-antivirus.md).
> 
> Per evitare questo problema in futuro, è possibile escludere i file dalle analisi. Vedere [Configure and validate exclusions for Antivirus Microsoft Defender scans](configure-exclusions-microsoft-defender-antivirus.md).

Vedere anche [Configure remediation-required scheduled full Antivirus Microsoft Defender scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md#remed) for more remediation-related settings.

## <a name="see-also"></a>Vedere anche

- [Configurare le opzioni di analisi di Microsoft Defender Antivirus](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [Configurare le Antivirus Microsoft Defender pianificate](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [Configurare ed eseguire analisi di Microsoft Defender Antivirus su richiesta](run-scan-microsoft-defender-antivirus.md)
- [Configurare le notifiche che vengono visualizzate negli endpoint](configure-notifications-microsoft-defender-antivirus.md)
- [Configurare l'interazione degli utenti Antivirus Microsoft Defender finale](configure-end-user-interaction-microsoft-defender-antivirus.md)
- [Personalizzare, avviare ed esaminare i risultati di Antivirus Microsoft Defender analisi e correzione](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Antivirus Microsoft Defender in Windows 10](microsoft-defender-antivirus-in-windows-10.md)
