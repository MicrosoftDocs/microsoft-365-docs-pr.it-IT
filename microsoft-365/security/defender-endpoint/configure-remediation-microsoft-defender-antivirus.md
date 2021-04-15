---
title: Configurare la correzione per i rilevamenti di Microsoft Defender Antivirus
description: Configurare l'operazione che Microsoft Defender Antivirus deve eseguire quando rileva una minaccia e per quanto tempo i file in quarantena devono essere conservati nella cartella di quarantena
keywords: correzione, correzione, rimozione, minacce, quarantena, analisi, ripristino
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 03/16/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 98bc079bcfd772ada52d699d5f873a187d4ab4c1
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765060"
---
# <a name="configure-remediation-for-microsoft-defender-antivirus-detections"></a>Configurare la correzione per i rilevamenti di Microsoft Defender Antivirus

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**

- [Microsoft Defender per endpoint](/microsoft-365/security/defender-endpoint/)

Quando Microsoft Defender Antivirus esegue un'analisi, tenta di correggere o rimuovere le minacce rilevate. Puoi configurare il modo in cui Microsoft Defender Antivirus deve affrontare determinate minacce, se deve essere creato un punto di ripristino prima della correzione e quando le minacce devono essere rimosse.

In questo articolo viene descritto come configurare queste impostazioni utilizzando Criteri di gruppo, ma è anche possibile usare [Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies#threat-overrides-settings) e Microsoft [Intune.](/intune/device-restrictions-configure) 

È inoltre possibile utilizzare il [ `Set-MpPreference` cmdlet PowerShell o](/powershell/module/defender/set-mppreference) la classe [ `MSFT_MpPreference` WMI](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal) per configurare queste impostazioni.

## <a name="configure-remediation-options"></a>Configurare le opzioni di correzione

1. Nel computer di gestione di Criteri di gruppo, aprire console Gestione Criteri di [gruppo,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e scegliere **Modifica**.

2. **Nell'Editor Gestione Criteri di gruppo** passare a Configurazione **computer** e selezionare **Modelli amministrativi.**

3. Espandere l'albero fino **ai componenti di Windows** Microsoft Defender  >  **Antivirus.** 

4. Usando la tabella seguente, selezionare un percorso e quindi modificare il criterio in base alle esigenze. 

5. Selezionare **OK**.

|Posizione | Impostazione | Descrizione | Impostazione predefinita (se non configurata) |
|:---|:---|:---|:---|
|Analisi | Creare un punto di ripristino del sistema | Verrà creato un punto di ripristino del sistema ogni giorno prima del tentativo di pulizia o analisi | Disabilitato|
|Analisi | Attivare la rimozione di elementi dalla cartella cronologia analisi | Specificare il numero di giorni in cui gli elementi devono essere conservati nella cronologia dell'analisi | 30 giorni |
|Radice | Disattivare la correzione di routine | Puoi specificare se Microsoft Defender Antivirus consente di correggere automaticamente le minacce o se deve chiedere all'utente dell'endpoint cosa fare. | Disabilitato (le minacce vengono corretti automaticamente) |
|Quarantena | Configurare la rimozione degli elementi dalla cartella quarantena | Specificare per quanti giorni gli elementi devono essere mantenuti in quarantena prima di essere rimossi | 90 giorni |
|Minacce | Specificare i livelli di avviso per le minacce a cui non deve essere eseguita l'azione predefinita quando viene rilevata | A ogni minaccia rilevata da Microsoft Defender Antivirus viene assegnato un livello di minaccia (basso, medio, alto o grave). È possibile utilizzare questa impostazione per definire la modalità di correzione di tutte le minacce per ognuno dei livelli di minaccia (in quarantena, rimosse o ignorate) | Non applicabile |
|Minacce | Specificare le minacce su cui non deve essere eseguita l'azione predefinita quando viene rilevata | Specificare la modalità di correzione delle minacce specifiche (usando il relativo ID minaccia). È possibile specificare se la minaccia specifica deve essere messo in quarantena, rimossa o ignorata | Non applicabile |

> [!IMPORTANT]
> Microsoft Defender Antivirus rileva e correggere i file in base a molti fattori. A volte, il completamento di una correzione richiede un riavvio. Anche se il rilevamento viene successivamente determinato come falso positivo, è necessario completare il riavvio per assicurarsi che tutti i passaggi di correzione aggiuntivi siano stati completati.
>
> Se si è certi che Microsoft Defender Antivirus ha messo in quarantena un file in base a un falso positivo, è possibile ripristinare il file dalla quarantena dopo il riavvio del dispositivo. Vedi [Ripristinare i file in quarantena in Microsoft Defender Antivirus.](restore-quarantined-files-microsoft-defender-antivirus.md)
> 
> Per evitare questo problema in futuro, è possibile escludere i file dalle analisi. Vedi [Configurare e convalidare le esclusioni per le analisi di Microsoft Defender Antivirus.](configure-exclusions-microsoft-defender-antivirus.md)

Vedi anche Configurare le analisi complete di [Microsoft Defender Antivirus](scheduled-catch-up-scans-microsoft-defender-antivirus.md#remed) pianificate necessarie per la correzione per altre impostazioni correlate alla correzione.

## <a name="see-also"></a>Vedere anche

- [Configurare le opzioni di analisi di Microsoft Defender Antivirus](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [Configurare le analisi pianificate di Microsoft Defender Antivirus](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [Configurare ed eseguire analisi di Microsoft Defender Antivirus su richiesta](run-scan-microsoft-defender-antivirus.md)
- [Configurare le notifiche visualizzate sugli endpoint](configure-notifications-microsoft-defender-antivirus.md)
- [Configurare l'interazione di Microsoft Defender Antivirus per l'utente finale](configure-end-user-interaction-microsoft-defender-antivirus.md)
- [Personalizzare, avviare ed esaminare i risultati delle analisi e delle correzioni di Microsoft Defender Antivirus](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)