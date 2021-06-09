---
title: Analizzatore configurazione conformità Microsoft per Compliance Manager
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
ms.openlocfilehash: 5d74d9980daf7f6ff7f013578cb11be83d18948e
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244637"
---
# <a name="microsoft-compliance-configuration-analyzer-for-compliance-manager-preview"></a>Analizzatore configurazione conformità Microsoft per Compliance Manager (anteprima)

**In questo articolo:** Informazioni su come installare ed eseguire lo strumento Microsoft Compliance Configure Analyzer per iniziare rapidamente a usare Microsoft Compliance Manger.

## <a name="microsoft-compliance-configuration-analyzer-mcca-preview-overview"></a>Panoramica di Microsoft Compliance Configuration Analyzer (MCCA) (anteprima)

Microsoft Compliance Configuration Analyzer (MCCA) è uno strumento di anteprima che consente di iniziare a usare [Microsoft Compliance Manager.](compliance-manager.md) MCCA è un'utilità basata su PowerShell che recupera le configurazioni correnti dell'organizzazione e le convalida Microsoft 365 consigliate. Queste procedure consigliate si basano su un set di controlli che includono normative e standard chiave per la protezione dei dati e la governance dei dati.

MCCA consente di vedere rapidamente quali azioni di miglioramento in Compliance Manager si applicano all'ambiente Microsoft 365 corrente. Ogni azione identificata da MCCA offrirà consigli per l'implementazione, con collegamenti diretti a Compliance Manager e alla soluzione applicabile per iniziare a prendere misure correttive.

Una risorsa aggiuntiva per comprendere MCCA è visitare le istruzioni [README su GitHub](https://github.com/OfficeDev/MCCA#overview). In questa pagina vengono fornite informazioni dettagliate sui prerequisiti e vengono fornite istruzioni complete per l'installazione. Non è necessario un account GitHub per accedere a questa pagina.

**Disponibilità**: MCCA è disponibile per tutte le organizzazioni con licenze di Office 365 e Microsoft 365 e per i clienti di US Government Community (GCC) Moderate, GCC High e Department of Defense (DoD).

## <a name="install-mcca-and-run-a-report"></a>Installare MCCA ed eseguire un report

Puoi installare lo strumento MCCA usando Windows PowerShell. Dopo aver scaricato e installato lo strumento, non è necessario ripetere questi passaggi per eseguire i report. Ogni volta che apri MCCA, ti chiederà le credenziali di accesso e genererà un nuovo report aggiornato.

#### <a name="step-1-install-windows-powershell"></a>Passaggio 1: installare Windows PowerShell
Per iniziare, è necessario il modulo Exchange Online PowerShell (v2.0.3 o versione successiva) disponibile nella raccolta PowerShell. [Ottenere le istruzioni di installazione](https://www.powershellgallery.com/packages/ExchangeOnlineManagement/2.0.3).

#### <a name="step-2-install-mcca"></a>Passaggio 2: installare MCCA

Per installare MCCA, iniziare usando PowerShell in modalità amministratore. Seguire la procedura seguente:

1. Seleziona il Windows **Start.**
2. Digitare **PowerShell,** fare clic con il pulsante destro **del mouse Windows PowerShell** e quindi scegliere Esegui come **amministratore.**
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

   Se sei un cliente GCC High, dovrai fornire un parametro di input aggiuntivo per eseguire il report:

    ```powershell
    Get-MCCAReport -ExchangeEnvironmentName O365USGovGCCHigh
    ```

3. Dopo l'esecuzione di MCCA, esegue un controllo della versione iniziale e richiede le credenziali. Al prompt Immettere il nome utente, accedere con l'indirizzo di posta elettronica dell Microsoft 365 account ( visualizzare i ruoli idonei per[la creazione di report).](#role-based-reporting) Immettere quindi la password al prompt della password.

La generazione del report richiederà circa 2-5 minuti. Al termine, viene aperta una finestra del browser che visualizza il report HTML. Ogni volta che esegui lo strumento, ti chiederà le credenziali e genererà un nuovo report. Questo report viene archiviato localmente nella directory seguente:

C:\Users \<username> \AppData\Local\Microsoft\MCCA. 

È possibile accedere ai report generati in precedenza da questa directory.

## <a name="understanding-your-report"></a>Informazioni sul report

Il report riflette i dati in base alla data e all'ora in cui è stato generato. Nella sezione superiore sono disponibili informazioni dettagliate su quando è stata generata, sul nome dell'organizzazione e sull'ID tenant.

#### <a name="geolocation-based-reporting"></a>Report basati sulla georilevazione

La **sezione Nota** mostra che il report è personalizzato in base alla posizione geografica del tenant. Consigli elencato nello strumento sarà specifico del proprio paese o area geografica.

La selezione di georilevazione viene utilizzata per valutare i tipi di informazioni riservate (SIT) rilevanti per tale georilevazione e generare un report allineato al proprio paese o area geografica. Scegliere le georilevazioni in base ai dati presenti nel tenant.

Per modificare le informazioni sulla posizione del report, è necessario fornire un parametro di input di georilevazione (-Geo). È possibile scegliere una o più georilevazioni applicabili al tenant.

Seguire queste istruzioni per eseguire un report in base a un percorso specifico:

1. Aprire PowerShell
2. Per specificare una determinata area geografica, verrà eseguito un cmdlet utilizzando i numeri della tabella seguente che corrispondono al paese o all'area geografica. Immettere più numeri separandoli con una virgola. Ad esempio, il cmdlet seguente eseguirà un report personalizzato per Asia-Pacific Giappone:

    ```powershell
    Get-MCCAReport -Geo @(1,7)
    ```
  | Input |  Paese | 
  | :------------- | :------------: |
  | 1 | Asia-Pacifico |
  | 2 | Australia |
  | 3 | Canada |
  | 4  | Europa (Francia esclusa) / Medio Oriente / Africa |
  | 5  | Francia |
  | 6  | India |
  | 7  | Giappone |
  | 8  | Corea del Sud |
  | 9  | Nord America (canada escluso) |
  | 10   | Sud America |
  | 11 | Sudafrica |
  | 12  | Svizzera |
  | 13 | Emirati Arabi Uniti |
  | 14  | Regno Unito |


 > [!NOTE]
> Il report includerà sempre i tipi di informazioni sensibili internazionali supportati da MCCA, ad esempio codice SWIFT, numero di carta di credito e così via.

#### <a name="role-based-reporting"></a>Report basati sui ruoli

Il report verrà inoltre personalizzato in base al ruolo dell'utente.

La tabella seguente mostra quali ruoli hanno accesso alle sezioni del report. Altri ruoli all'interno dell'organizzazione (non elencati nella tabella seguente) potrebbero non essere in grado di eseguire lo strumento oppure potrebbero eseguire lo strumento e avere accesso limitato alle informazioni nel report finale.

![MCCA - ruoli](../media/compliance-manager-mcca-roles.png "Ruoli MCCA")

Eccezioni:
1. Gli utenti non saranno in grado di generare report per IP a parte la sezione "Usare IRM per Exchange Online".
2. Gli utenti potranno generare report per IP oltre alla sezione "Usare IRM per Exchange Online".
3. Gli utenti saranno in grado di generare report per IP oltre alla sezione "Abilitare la conformità delle comunicazioni in O365".
4. Gli utenti non saranno in grado di generare report per IP oltre alla sezione "Abilita controllo in Office 365".
5. Gli utenti saranno in grado di generare report per IP a parte la sezione "Abilita controllo in Office 365".

#### <a name="solutions-summary-section"></a>Sezione Riepilogo soluzioni

Nella **sezione Riepilogo soluzioni** del report viene fornita una panoramica delle azioni di miglioramento che l'organizzazione può eseguire in Compliance Manager per migliorare la conformità.

![MCCA - Riepilogo delle soluzioni](../media/compliance-manager-mcca-solutions.png "Schermata di riepilogo delle soluzioni MCCA")

MCCA valuta le configurazioni correnti in base alle azioni di miglioramento consigliate in Compliance Manager. Tutte le azioni di miglioramento identificate dallo strumento MCCA come necessarie saranno elencate in questa sezione.

Accanto a ogni soluzione Microsoft sono presenti caselle con codice a colori che indicano il numero di elementi che corrispondono alle azioni di miglioramento in Compliance Manager. Le azioni sono suddivise in tre stati di stato:

- **OK**: le azioni che soddisfano le condizioni consigliate e non necessitano di attenzione in questo momento
- **Miglioramento**: azioni che necessitano di attenzione
- **Suggerimento**: azioni che non necessitano di attenzione, ma per le quali è consigliabile utilizzare le procedure consigliate
 
Selezionare una casella per visualizzare i miglioramenti e i suggerimenti.

**Elementi con stato Miglioramento**

Seleziona l'elenco a discesa **accanto** all'etichetta Miglioramento a destra dell'azione di miglioramento. Vedrai un breve riepilogo e dettagli sulle impostazioni correnti e sulle azioni di miglioramento consigliate. Il riepilogo include collegamenti diretti a Compliance Manager, alla soluzione applicabile nel Centro Microsoft 365 conformità e alla documentazione pertinente.

Facendo clic sul collegamento Compliance Manager viene visualizzata una visualizzazione filtrata di tutte le azioni di miglioramento all'interno della soluzione non ancora implementate. Da qui è possibile visualizzare il numero di punti che è possibile raggiungere per aumentare il punteggio di conformità [e](compliance-score-calculation.md)le valutazioni a cui si applicano e le normative e le certificazioni applicabili.

Per DLP, è presente un pulsante **Script** di correzione che fornisce uno script di PowerShell pre-generato in base a quanto consigliato. È possibile copiarlo e incollarlo direttamente nella console di PowerShell. Verrà creato un criterio DLP in modalità test

**Elementi con stato Consiglio**

Seleziona l'elenco a discesa accanto **all'etichetta** Raccomandazione a destra dell'azione di miglioramento. Verrà visualizzato un riepilogo dell'ambiente di Microsoft 365 dell'organizzazione correlato all'azione di miglioramento, insieme alle procedure consigliate.

## <a name="resources"></a>Risorse

Per informazioni più dettagliate sull'installazione, la configurazione e l'utilizzo di MCCA, vedere le istruzioni [README](https://github.com/OfficeDev/MCCA#overview) su GitHub (nessun account GitHub necessario).

Per ulteriori informazioni su Windows PowerShell, iniziare da [Come usare la documentazione di PowerShell.](/powershell/scripting/how-to-use-docs?view=powershell-7) Vedere anche [Starting Windows PowerShell](/powershell/scripting/windows-powershell/starting-windows-powershell?view=powershell-7).
