---
title: Definire la modalità di aggiornamento dei dispositivi mobili Antivirus Microsoft Defender
description: Gestire la modalità di aggiornamento dei dispositivi mobili, ad esempio i portatili, Antivirus Microsoft Defender aggiornamenti della protezione.
keywords: aggiornamenti, protezione, pianificazione degli aggiornamenti, batteria, dispositivo mobile, portatile, blocco appunti, consenso esplicito, microsoft update, wsus, override
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 809f4573c91f7f1882693cbd8c63d88b06b55c67
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926008"
---
# <a name="manage-updates-for-mobile-devices-and-virtual-machines-vms"></a>Gestire gli aggiornamenti per dispositivi mobili e macchine virtuali (VMS)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**

- [Microsoft Defender per endpoint](/microsoft-365/security/defender-endpoint/)

I dispositivi mobili e le macchine virtuali potrebbero richiedere una configurazione maggiore per garantire che le prestazioni non siano influenzate dagli aggiornamenti.

Esistono due impostazioni utili per questi dispositivi:

- Acconsentire esplicitamente a Microsoft Update nei computer mobili senza una connessione WSUS
- Impedisci aggiornamenti di Intelligence per la sicurezza durante l'esecuzione con alimentazione a batteria

Gli articoli seguenti possono essere utili anche in queste situazioni:
- [Configurazione delle analisi pianificate e di aggiornamento](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [Gestire gli aggiornamenti per gli endpoint non aggiornati](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [Guida alla distribuzione di Microsoft Defender Antivirus in un ambiente VDI (Virtual Desktop Infrastructure)](deployment-vdi-microsoft-defender-antivirus.md)

## <a name="opt-in-to-microsoft-update-on-mobile-computers-without-a-wsus-connection"></a>Acconsentire esplicitamente a Microsoft Update nei computer mobili senza una connessione WSUS

È possibile utilizzare Microsoft Update per mantenere aggiornata l'intelligence per la sicurezza nei dispositivi mobili che eseguono Antivirus Microsoft Defender quando non sono connessi alla rete aziendale o non dispongono altrimenti di una connessione WSUS. 

Ciò significa che gli aggiornamenti della protezione possono essere recapitati ai dispositivi (tramite Microsoft Update) anche se WSUS è stato impostato per sostituire Microsoft Update.

Puoi acconsentire esplicitamente a Microsoft Update nel dispositivo mobile in uno dei modi seguenti:

- Modificare l'impostazione con Criteri di gruppo.
- Utilizzare un VBScript per creare uno script, quindi eseguirlo in ogni computer della rete.
- Acconsentire manualmente a tutti i computer della rete **tramite Impostazioni** menu.

### <a name="use-group-policy-to-opt-in-to-microsoft-update"></a>Usare Criteri di gruppo per acconsentire esplicitamente a Microsoft Update

1. Nel computer di gestione di Criteri di gruppo, aprire console Gestione Criteri di [gruppo,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e scegliere **Modifica**.

2. **Nell'Editor Gestione Criteri di gruppo** passare a Configurazione **computer**.

3. Selezionare **Criteri** e **modelli amministrativi.**

4. Espandere l'albero per **Windows componenti**  >  **Antivirus Microsoft Defender**  >  **aggiornamenti delle firme**.

5. Impostare **Consenti aggiornamenti di intelligence per la sicurezza da Microsoft Update** su **Abilitato** e quindi selezionare **OK.**


### <a name="use-a-vbscript-to-opt-in-to-microsoft-update"></a>Usare un VBScript per acconsentire esplicitamente a Microsoft Update

1. Seguire le istruzioni nell'articolo MSDN [Acconsentire esplicitamente a Microsoft Update](/windows/win32/wua_sdk/opt-in-to-microsoft-update) per creare VBScript.

2. Eseguire vbScript creato in ogni computer della rete.

### <a name="manually-opt-in-to-microsoft-update"></a>Acconsentire manualmente a Microsoft Update

1. Aprire **Windows Update** in Update & di **sicurezza** nel computer in cui si desidera acconsentire esplicitamente.

2. Selezionare **Opzioni** avanzate.

3. Seleziona la casella di controllo Dammi aggiornamenti per altri prodotti Microsoft quando **aggiorno Windows**.

## <a name="prevent-security-intelligence-updates-when-running-on-battery-power"></a>Impedisci aggiornamenti di Intelligence per la sicurezza durante l'esecuzione con alimentazione a batteria

Puoi configurare il Antivirus Microsoft Defender solo per scaricare gli aggiornamenti di protezione quando il PC è connesso a una fonte di alimentazione cablata. 

### <a name="use-group-policy-to-prevent-security-intelligence-updates-on-battery-power"></a>Utilizzare Criteri di gruppo per impedire gli aggiornamenti delle funzionalità di intelligence per la sicurezza nell'alimentazione a batteria

1.  Nel computer di gestione di Criteri di gruppo, aprire la [Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))Gestione Criteri di gruppo, scegliere l'oggetto Criteri di gruppo che si desidera configurare e aprirlo per la modifica.

2.  **Nell'Editor Gestione Criteri di gruppo** passare a Configurazione **computer**.

3.  Selezionare **Criteri** e **modelli amministrativi.**

4.  Espandere l'albero per **Windows componenti** Antivirus Microsoft Defender aggiornamenti delle firme e quindi impostare Consenti aggiornamenti di intelligence per la sicurezza quando è in esecuzione l'alimentazione  >    >  a **batteria** su **Disabilitato.** Infine scegliere **OK**. 

Questa azione impedisce il download degli aggiornamenti di protezione quando il PC è alimentato a batteria.

## <a name="related-articles"></a>Articoli correlati

- [Gestire Antivirus Microsoft Defender aggiornamenti e applicare linee di base](manage-updates-baselines-microsoft-defender-antivirus.md)
- [Aggiornare e gestire Antivirus Microsoft Defender in Windows 10](deploy-manage-report-microsoft-defender-antivirus.md)