---
title: Ospitare la creazione di report dei firewall in Microsoft Defender per endpoint
description: Ospitare e visualizzare i report del firewall Microsoft 365 centro sicurezza.
keywords: windows defender, firewall
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
audience: ITPro
ms.topic: article
author: dansimp
ms.author: dansimp
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 0289d6f920fd6ff35fd446f9c2b8c5516883a4d2
ms.sourcegitcommit: e1e275eb88153bafddf93327adf8f82318913a8d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52809307"
---
# <a name="host-firewall-reporting-in-microsoft-defender-for-endpoint"></a>Ospitare la creazione di report dei firewall in Microsoft Defender per endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Se sei un amministratore, ora puoi ospitare la segnalazione del firewall [Microsoft 365 centro sicurezza](https://security.microsoft.com). Questa funzionalità consente di visualizzare i report Windows 10 e Windows server 2019 da una posizione centralizzata. 

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare? 

- È necessario eseguire Windows 10 o Windows Server 2019.
- Per eseguire l'onboard dei dispositivi nel servizio Microsoft Defender for Endpoint, vedi [qui](onboard-configure.md). 
- Per Microsoft 365 centro sicurezza per iniziare a ricevere  i dati, è necessario abilitare gli eventi di controllo per Windows Defender Firewall sicurezza avanzata: 
    - [Audit Filtering Platform Packet Drop](/windows/security/threat-protection/auditing/audit-filtering-platform-packet-drop)
    - [Audit Filtering Platform Connection](/windows/security/threat-protection/auditing/audit-filtering-platform-connection) 
- Abilitare questi eventi utilizzando Editor oggetti Criteri di gruppo, Criteri di sicurezza locali o i auditpol.exe comandi. Per ulteriori informazioni, vedere [qui](/windows/win32/fwp/auditing-and-logging). 
    - I due comandi di PowerShell sono:
        - **auditpol /set /subcategory:"Filtering Platform Packet Drop" /failure:enable** 
        - **auditpol /set /subcategory:"Filtering Platform Connection" /failure:enable** 

## <a name="the-process"></a>Processo
> [!NOTE]
> Assicurati di seguire le istruzioni della sezione precedente e configurare correttamente i dispositivi per la partecipazione all'anteprima anticipata.

- Dopo aver abilitato gli eventi, Microsoft 365 centro sicurezza inizierà a monitorare i dati.
    - IP remoto, porta remota, porta locale, IP locale, nome computer, processo attraverso connessioni in ingresso e in uscita.
- Gli amministratori possono ora visualizzare l Windows'attività del firewall host [qui](https://security.microsoft.com/firewall).
    - È possibile semplificare la creazione di report aggiuntivi scaricando lo [script per](https://github.com/microsoft/MDATP-PowerBI-Templates/tree/master/Firewall) la creazione di report personalizzati per monitorare le attività Windows Defender Firewall tramite Power BI. 
    - Possono essere necessario fino a 12 ore prima che i dati riflettano.

## <a name="supported-scenarios"></a>Scenari supportati
Durante Ring0 Preview sono supportati gli scenari seguenti. 

### <a name="firewall-reporting-in-security-center"></a>Creazione di report firewall nel Centro sicurezza

Ecco un paio di esempi delle pagine di report del firewall. Qui troverai un riepilogo delle attività in ingresso, in uscita e dell'applicazione. È possibile accedere a questa pagina direttamente da https://security.microsoft.com/firewall . 

> [!div class="mx-imgBorder"]
> ![Pagina di creazione di report del firewall host](\images\host-firewall-reporting-page.png)

È inoltre possibile accedere a questi report accedendo a Report Dispositivi report di sicurezza (sezione) nella parte inferiore della scheda Connessioni in ingresso  >    >   bloccate dal firewall. 

### <a name="from-computers-with-a-blocked-connection-to-device"></a>Da "Computer con una connessione bloccata" al dispositivo

Le schede supportano oggetti interattivi. Puoi analizzare l'attività di un dispositivo facendo clic sul nome del dispositivo, che verrà avviato in una nuova scheda, e passare direttamente alla https://securitycenter.microsoft.com **scheda Sequenza temporale** del dispositivo. 

> [!div class="mx-imgBorder"]
> ![Computer con una connessione bloccata](\images\firewall-reporting-blocked-connection.png)

Ora puoi selezionare la **scheda Sequenza** temporale, che ti darà un elenco di eventi associati al dispositivo. 

Dopo aver fatto clic **sul pulsante** Filtri nell'angolo superiore destro del riquadro di visualizzazione, selezionare il tipo di evento desiderato. In questo caso, selezionare **Eventi firewall** e il riquadro verrà filtrato in Eventi firewall. 

> [!div class="mx-imgBorder"]
> ![Pulsante Filtri](\images\firewall-reporting-filters-button.png)

### <a name="drill-into-advanced-hunting-preview-refresh"></a>Drill-into advanced hunting (preview refresh)

I report firewall supportano il drilling dalla scheda direttamente in **Ricerca avanzata** facendo clic sul pulsante **Apri ricerca** avanzata. La query verrà precompilato. 

> [!div class="mx-imgBorder"]
> ![Pulsante Apri ricerca avanzata](\images\firewall-reporting-advanced-hunting.png)

La query può ora essere eseguita e tutti gli eventi firewall correlati degli ultimi 30 giorni possono essere esplorati. 

Per ulteriori report o modifiche personalizzate, la query può essere esportata in Power BI per ulteriori analisi. I report personalizzati possono essere semplificati scaricando lo [script di](https://github.com/microsoft/MDATP-PowerBI-Templates/tree/master/Firewall) creazione di report personalizzati per monitorare le attività Windows Defender Firewall tramite Power BI. 

 