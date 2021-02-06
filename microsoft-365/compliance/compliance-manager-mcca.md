---
title: Analizzatore configurazione di conformità Microsoft per Compliance Manager
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Informazioni su come usare Microsoft Compliance Configuration Analyzer per iniziare rapidamente a usare Microsoft Compliance Manager.
ms.openlocfilehash: 86c4b04deb8313f3013a6d9ad349c0f4112db773
ms.sourcegitcommit: 719b89baca1bae14455acf2e517ec18fc473636c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2021
ms.locfileid: "50122396"
---
# <a name="microsoft-compliance-configuration-analyzer-for-compliance-manager-preview"></a>Analizzatore configurazione di conformità Microsoft per Compliance Manager (anteprima)

**In questo articolo:** Informazioni su come installare ed eseguire lo strumento Microsoft Compliance Configure Analyzer per iniziare rapidamente a usare Microsoft Compliance Manger.

## <a name="microsoft-compliance-configuration-analyzer-mcca-preview-overview"></a>Panoramica di Microsoft Compliance Configuration Analyzer (MCCA) (anteprima)

Microsoft Compliance Configuration Analyzer (MCCA) è uno strumento di anteprima che consente di iniziare a usare [Microsoft Compliance Manager.](compliance-manager.md) MCCA è un'utilità basata su PowerShell che recupera le configurazioni correnti dell'organizzazione e le convalida in base alle procedure consigliate di Microsoft 365. Queste procedure consigliate si basano su un insieme di controlli che includono normative e standard chiave per la protezione dei dati e la governance dei dati.

MCCA consente di vedere rapidamente quali azioni di miglioramento in Compliance Manger si applicano all'ambiente Microsoft 365 corrente. Ogni azione identificata da MCCA ti offrirà consigli per l'implementazione, con collegamenti diretti a Compliance Manager e alla soluzione applicabile per avviare l'azione correttiva.

Una risorsa aggiuntiva per comprendere MCCA è visitare le istruzioni [README su GitHub.](https://github.com/OfficeDev/MCCA#overview) In questa pagina vengono fornite informazioni dettagliate sui prerequisiti e vengono fornite istruzioni di installazione complete. Non è necessario un account GitHub per accedere a questa pagina.

**Disponibilità:** MCCA è disponibile per tutte le organizzazioni con licenze di Office 365 e Microsoft 365 e clienti moderati della US Government Community (GCC), con piani in corso per espandere il servizio ai clienti GCC High.

## <a name="install-mcca-and-run-a-report"></a>Installare MCCA ed eseguire un report

Puoi installare lo strumento MCCA usando Windows PowerShell. Dopo aver scaricato e installato lo strumento, non è necessario ripetere questi passaggi per eseguire i report. Ogni volta che apri MCCA, ti chiederà le credenziali di accesso e genererà un nuovo report aggiornato.

#### <a name="step-1-install-windows-powershell"></a>Passaggio 1: installare Windows PowerShell
Per iniziare, è necessario il modulo PowerShell di Exchange Online (v2.0.3 o versione successiva) disponibile nella raccolta PowerShell. [Ottenere le istruzioni di installazione.](https://www.powershellgallery.com/packages/ExchangeOnlineManagement/2.0.3)

#### <a name="step-2-install-mcca"></a>Passaggio 2: installare MCCA

Per installare MCCA, iniziare usando PowerShell in modalità amministratore. Seguire i passaggi seguenti:

1. Seleziona il pulsante **Start di** Windows.
2. Digitare **PowerShell,** fare clic con il pulsante destro **del Windows PowerShell** e quindi scegliere Esegui come **amministratore.**
1. Al prompt dei comandi digitare:

    ```powershell
    Install-Module -Name MCCAPreview
    ```

#### <a name="step-3-run-a-report"></a>Passaggio 3: Eseguire un report

Dopo aver installato MCCA, è possibile eseguire MCCA e generare un report. Per eseguire un report:

1. Aprire PowerShell
2. Eseguire il cmdlet:

    ```powershell
    Get-MCCAReport
    ```
3. Dopo l'esecuzione di MCCA, esegue un controllo della versione iniziale e richiede le credenziali. Al prompt Input the user name, sign in with your Microsoft 365 account email address ([view the roles eligible to create reports](#role-based-reporting)). Immettere quindi la password al prompt della password.

La generazione del report richiederà circa 2-5 minuti. Al termine, viene visualizzata una finestra del browser in cui viene visualizzato il report HTML. Ogni volta che esegui lo strumento, ti chiederà le credenziali e genererà un nuovo report. Questo report viene archiviato localmente nella directory seguente:

C:\Users \<username> \AppData\Local\Microsoft\MCCA. 

Da questa directory è possibile accedere ai report generati in precedenza.

## <a name="understanding-your-report"></a>Informazioni sul report

Il report riflette i dati in base alla data e all'ora in cui è stato generato. Nella sezione superiore sono disponibili informazioni dettagliate su quando è stata generata, sul nome dell'organizzazione e sull'ID tenant.

#### <a name="geolocation-based-reporting"></a>Report basati sulla georilevazione

La **sezione** Nota mostra che il report è personalizzato in base alla posizione geografica del tenant. Gli elementi consigliati elencati nello strumento saranno specifici del proprio paese o area geografica.

La selezione della georilevazione viene usata per valutare i tipi di informazioni sensibili (SIT) rilevanti per tale georilevazione e generare un report allineato al proprio paese o area geografica. Scegliere le georilevazioni in base ai dati presenti nel tenant.

Per modificare le informazioni sulla posizione del report, è necessario fornire un parametro di input di georilevazione (-Geo). È possibile scegliere una o più georilevazioni applicabili per il tenant.

Seguire queste istruzioni per eseguire un report in base a un percorso specifico:

1. Aprire PowerShell
2. Per specificare una determinata area geografica, eseguire un cmdlet utilizzando i numeri della tabella seguente corrispondenti al paese o all'area geografica. Immettere più numeri separandoli con una virgola. Ad esempio, il cmdlet seguente eseguirà un report personalizzato per Asia-Pacific Giappone:

    ```powershell
    Get-MCCAReport -Geo @(1,7)
    ```
  | Input |  Paese | 
  | :------------- | :------------: |
  | 1  | Asia-Pacifico |
  | 2  | Australia |
  | 3  | Canada |
  | 4  | Europa (Francia esclusa) / Medio Oriente /Africa |
  | 5  | Francia |
  | 6  | India |
  | 7  | Giappone |
  | 8  | Corea del Sud |
  | 9  | Nord America (canada escluso) |
  | 10  | Sud America |
  | 11  | Sudafrica |
  | 12  | Svizzera |
  | 13  | Emirati Arabi Uniti |
  | 14  | Regno Unito |


 > [!NOTE]
> Il report includerà sempre i tipi di informazioni sensibili internazionali supportati da MCCA, ad esempio codice SWIFT, numero di carta di credito e così via.

#### <a name="role-based-reporting"></a>Creazione di report basati sui ruoli

Il report verrà inoltre personalizzato in base al ruolo dell'utente.

La tabella seguente mostra quali ruoli hanno accesso a quali sezioni del report. Altri ruoli all'interno dell'organizzazione (non elencati nella tabella seguente) potrebbero non essere in grado di eseguire lo strumento oppure potrebbero eseguire lo strumento e avere accesso limitato alle informazioni nel report finale.

![MCCA - ruoli](../media/compliance-manager-mcca-roles.png "Ruoli MCCA")

Eccezioni:
1. L'utente non sarà in grado di generare report per IP a parte la sezione "Utilizzare IRM per Exchange Online".
2. L'utente sarà in grado di generare un rapporto per IP a parte la sezione "Utilizzare IRM per Exchange Online".
3. L'utente sarà in grado di generare un report per IP a parte la sezione "Abilitare la conformità delle comunicazioni in O365".
4. L'utente non sarà in grado di generare report per IP a parte la sezione "Abilitare il controllo in Office 365".
5. L'utente sarà in grado di generare report per IP a parte la sezione "Abilitare il controllo in Office 365".

#### <a name="solutions-summary-section"></a>Sezione Riepilogo soluzioni

Nella **sezione Riepilogo soluzioni** del report viene fornita una panoramica delle azioni di miglioramento che l'organizzazione può eseguire in Compliance Manager per migliorare la conformità.

![MCCA - Riepilogo delle soluzioni](../media/compliance-manager-mcca-solutions.png "Schermata di riepilogo delle soluzioni MCCA")

MCCA valuta le configurazioni correnti in base alle azioni di miglioramento consigliate in Compliance Manager. Tutte le azioni di miglioramento identificate dallo strumento MCCA che necessitano attenzione verranno elencate in questa sezione.

Accanto a ogni soluzione Microsoft sono presenti caselle con codice a colori che indicano il numero di elementi che corrispondono alle azioni di miglioramento in Compliance Manager. Le azioni sono suddivise in tre stati di stato:

- **OK:** le azioni che soddisfano le condizioni consigliate e che non necessitano di attenzione in questo momento
- **Miglioramento:** azioni che necessitano attenzione
- **Suggerimento:** azioni che non necessitano di attenzione, ma per le quali si consigliano le procedure consigliate
 
Selezionare una casella per visualizzare miglioramenti e suggerimenti.

**Elementi con stato Miglioramento**

Selezionare l'elenco a discesa accanto **all'etichetta Miglioramento** a destra dell'azione di miglioramento. Verranno visualizzati un breve riepilogo e informazioni dettagliate sulle impostazioni correnti e sulle azioni di miglioramento consigliate. Il riepilogo include collegamenti diretti a Compliance Manager, la soluzione applicabile nel Centro conformità Microsoft 365 e la documentazione pertinente.

Facendo clic sul collegamento di Compliance Manager si visualizza una visualizzazione filtrata di tutte le azioni di miglioramento all'interno della soluzione non ancora implementate. Da qui è possibile vedere il numero di punti che è possibile raggiungere per aumentare il punteggio di conformità [e](compliance-score-calculation.md)le valutazioni a cui si applicano e le normative e le certificazioni applicabili.

Per DLP, è  presente un pulsante Script di correzione che fornisce uno script di PowerShell pre-generato in base a quanto consigliato. È possibile copiarlo e incollarlo direttamente nella console di PowerShell. Verrà creato un criterio DLP in modalità test

**Elementi con stato Elementi consigliati**

Selezionare l'elenco a discesa accanto **all'etichetta** Elementi consigliati a destra dell'azione di miglioramento. Verrà visualizzato un riepilogo dell'ambiente Microsoft 365 corrente dell'organizzazione relativo all'azione di miglioramento, insieme alle procedure consigliate.

## <a name="resources"></a>Risorse

Per informazioni più dettagliate sull'installazione, la configurazione e l'uso di MCCA, vedi le istruzioni README su [GitHub](https://github.com/OfficeDev/MCCA#overview) (non è necessario alcun account GitHub).

Per altre informazioni su Windows PowerShell, inizia dalla documentazione [di PowerShell.](https://docs.microsoft.com/powershell/scripting/how-to-use-docs?view=powershell-7) Vedere anche [Starting Windows PowerShell](https://docs.microsoft.com/powershell/scripting/windows-powershell/starting-windows-powershell?view=powershell-7).
