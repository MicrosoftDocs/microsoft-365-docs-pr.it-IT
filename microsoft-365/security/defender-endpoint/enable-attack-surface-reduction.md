---
title: Abilitare le regole di riduzione della superficie di attacco
description: Abilita le regole di riduzione della superficie di attacco (ASR) per proteggere i dispositivi da attacchi che usano macro, script e tecniche di inserimento comuni.
keywords: Riduzione della superficie di attacco, fianchi, sistema di prevenzione delle intrusioni host, regole di protezione, anti-exploit, antiexploit, exploit, prevenzione delle infezioni, abilitare, attivare
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: levinec
ms.author: ellevin
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 1deec767c6af777b23ab5a91c9e719f690e0c048
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165142"
---
# <a name="enable-attack-surface-reduction-rules"></a>Abilitare le regole di riduzione della superficie di attacco

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender ATP](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

[Le regole di riduzione della superficie](attack-surface-reduction.md) di attacco (regole ASR) consentono di impedire azioni che il malware spesso abuso per compromettere dispositivi e reti. Puoi impostare le regole asr per i dispositivi che eseguono una delle seguenti edizioni e versioni di Windows:
- Windows 10 Pro, [versione 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) o successiva
- Windows 10 Enterprise, [versione 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) o successiva
- Windows Server, [versione 1803 (Canale semestraale)](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) o versione successiva
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)

Ogni regola asr contiene una delle tre impostazioni seguenti:

- Non configurato: disabilitare la regola asr
- Block: Enable the ASR rule
- Controllo: valutare l'impatto della regola asr sull'organizzazione se abilitata

È consigliabile usare le regole asr con una licenza di Windows E5 (o una SKU di licenza simile) per sfruttare le funzionalità avanzate di monitoraggio e creazione di report disponibili in [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) (Defender for Endpoint). Tuttavia, per altre licenze come Windows Professional o E3 che non hanno accesso alle funzionalità avanzate di monitoraggio e creazione di report, è possibile sviluppare strumenti di monitoraggio e creazione di report personalizzati oltre agli eventi generati in ogni endpoint quando vengono attivate le regole di registrazione asr (ad esempio, Inoltro eventi).

> [!TIP]
> Per altre informazioni sulle licenze di Windows, vedi [Licenze di Windows 10](https://www.microsoft.com/licensing/product-licensing/windows10?activetab=windows10-pivot:primaryr5) e ottieni la guida per i [contratti multilicenza per Windows 10.](https://download.microsoft.com/download/2/D/1/2D14FE17-66C2-4D4C-AF73-E122930B60F6/Windows-10-Volume-Licensing-Guide.pdf)

Puoi abilitare le regole di riduzione della superficie di attacco usando uno dei metodi seguenti:

- [Microsoft Intune](#intune)
- [Gestione di dispositivi mobili (MDM)](#mdm)
- [Microsoft Endpoint Configuration Manager](#microsoft-endpoint-configuration-manager)
- [Criteri di gruppo](#group-policy)
- [PowerShell](#powershell)

È consigliabile gestire a livello aziendale, ad esempio Intune o Microsoft Endpoint Manager. La gestione a livello aziendale sovrascriverà tutte le impostazioni di Criteri di gruppo o PowerShell in conflitto all'avvio.

## <a name="exclude-files-and-folders-from-asr-rules"></a>Escludere file e cartelle dalle regole asr

È possibile escludere file e cartelle dalla maggior parte delle regole di riduzione della superficie di attacco. Ciò significa che, anche se una regola asr determina che il file o la cartella contiene comportamenti dannosi, non blocchi l'esecuzione del file. Ciò potrebbe potenzialmente consentire l'esecuzione di file non sicuri e infettare i dispositivi.

Puoi anche escludere le regole asr dall'attivazione in base agli hash di certificati e file consentendo a Defender per gli indicatori di certificato e file dell'endpoint specificati. (Vedere [Gestire gli indicatori](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-indicators).)

> [!IMPORTANT]
> L'esclusione di file o cartelle può ridurre notevolmente la protezione fornita dalle regole asr. L'esecuzione dei file esclusi sarà consentita e non verrà registrato alcun report o evento.
> Se le regole di ripristino automatico rilevano file che ritieni non debbano essere rilevati, devi prima usare la modalità di controllo per [testare la regola.](evaluate-attack-surface-reduction.md)


È possibile specificare singoli file o cartelle (utilizzando percorsi di cartelle o nomi di risorse completi), ma non è possibile specificare le regole a cui si applicano le esclusioni. Un'esclusione viene applicata solo all'avvio dell'applicazione o del servizio escluso. Ad esempio, se si aggiunge un'esclusione per un servizio di aggiornamento già in esecuzione, il servizio di aggiornamento continuerà a attivare eventi finché il servizio non viene arrestato e riavviato.

Le regole asr supportano variabili di ambiente e caratteri jolly. Per informazioni sull'utilizzo dei caratteri jolly, vedere [Use wildcards in the file name and folder path or extension exclusion lists](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists).

Le procedure seguenti per l'abilitazione delle regole asr includono istruzioni su come escludere file e cartelle.

## <a name="intune"></a>Intune

1. Selezionare **Profili di configurazione** del  >  **dispositivo**. Scegliere un profilo di endpoint protection esistente o crearne uno nuovo. Per crearne uno nuovo, selezionare **Crea profilo** e immettere le informazioni per il profilo. Per **Tipo di profilo** selezionare Endpoint **protection.** Se è stato scelto un profilo esistente, selezionare **Proprietà** e quindi **Impostazioni.**

2. Nel riquadro **Endpoint protection** seleziona Windows Defender **Exploit Guard** e quindi seleziona Riduzione della superficie **di attacco.** Selezionare l'impostazione desiderata per ogni regola asr.

3. In **Eccezioni di riduzione della superficie di attacco** immetti singoli file e cartelle. È inoltre possibile selezionare **Importa per** importare un file CSV contenente file e cartelle da escludere dalle regole asr. Ogni riga del file CSV deve essere formattata come segue:

   `C:\folder`, `%ProgramFiles%\folder\file`, `C:\path`

4. Selezionare **OK** nei tre riquadri di configurazione. Seleziona Quindi **Crea** se stai creando un nuovo file di endpoint protection o **Salva** se ne stai modificando uno esistente.

## <a name="mdm"></a>MDM

Usa il provider di servizi di configurazione [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductionrules) per abilitare e impostare singolarmente la modalità per ogni regola.

Di seguito è riportato un esempio di riferimento, utilizzando [i valori GUID per le regole asr.](attack-surface-reduction.md#attack-surface-reduction-rules)

`OMA-URI path: ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules`

`Value: 75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84=2|3B576869-A4EC-4529-8536-B80A7769E899=1|D4F940AB-401B-4EfC-AADC-AD5F3C50688A=2|D3E037E1-3EB8-44C8-A917-57927947596D=1|5BEB7EFE-FD9A-4556-801D-275E5FFC04CC=0|BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550=1`

I valori da abilitare, disabilitare o abilitare in modalità di controllo sono:

- Disable = 0
- Block (enable ASR rule) = 1
- Controllo = 2

Usa il provider di servizi di configurazione [./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) per aggiungere esclusioni.

Esempio:

`OMA-URI path: ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions`

`Value: c:\path|e:\path|c:\Exclusions.exe`

> [!NOTE]
> Assicurati di immettere valori URI OMA senza spazi.

## <a name="microsoft-endpoint-configuration-manager"></a>Microsoft Endpoint Configuration Manager

1. In Microsoft Endpoint Configuration Manager, vai a **Assets and Compliance**  >  **Endpoint Protection**  >  **Windows Defender Exploit Guard**.

2. Selezionare **Home**  >  **Create Exploit Guard Policy**.

3. Immetti un nome e una descrizione, seleziona **Riduzione superficie di attacco** e seleziona **Avanti.**

4. Scegliere le regole che verranno bloccate o le azioni di controllo e selezionare **Avanti.**

5. Rivedere le impostazioni e selezionare **Avanti** per creare il criterio.

6. Dopo la creazione del criterio, **chiudere**.

## <a name="group-policy"></a>Criteri di gruppo

> [!WARNING]
> Se gestisci i computer e i dispositivi con Intune, Configuration Manager o un'altra piattaforma di gestione a livello aziendale, il software di gestione sovrascriverà tutte le impostazioni di Criteri di gruppo in conflitto all'avvio.

1. Nel computer di gestione di Criteri di gruppo aprire Console Gestione Criteri di [gruppo,](https://technet.microsoft.com/library/cc731212.aspx)fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e scegliere **Modifica**.

2. **Nell'Editor Gestione Criteri di gruppo** passare a Configurazione **computer** e selezionare **Modelli amministrativi.**

3. Espandi l'albero fino ai **componenti di Windows** Microsoft Defender Antivirus Windows Defender riduzione della superficie di attacco  >    >  di Exploit **Guard.**  >  

4. Selezionare **Configura regole di riduzione della superficie di attacco** e selezionare **Abilitato.** È quindi possibile impostare il singolo stato per ogni regola nella sezione opzioni.

   Selezionare **Mostra...** e immettere l'ID regola nella colonna **Nome valore** e lo stato scelto nella colonna **Valore** come indicato di seguito:

   - Disable = 0
   - Block (enable ASR rule) = 1
   - Controllo = 2

   ![Impostazione di Criteri di gruppo che mostra un ID regola di riduzione della superficie di attacco vuota e un valore pari a 1](/microsoft-365/security/defender-endpoint/images/asr-rules-gp)

5. Per escludere file e cartelle dalle  regole asr, selezionare l'impostazione Escludi file e percorsi dalle regole di riduzione della superficie di attacco e impostare l'opzione su **Abilitato.** Selezionare **Mostra** e immettere ogni file o cartella nella **colonna Nome** valore. Immettere **0** nella **colonna Valore** per ogni elemento.

> [!WARNING]
> Non utilizzare le virgolette perché non sono supportate per la colonna **Nome valore** o **Valore.**

## <a name="powershell"></a>PowerShell

> [!WARNING]
> Se gestisci i computer e i dispositivi con Intune, Configuration Manager o un'altra piattaforma di gestione a livello aziendale, il software di gestione sovrascriverà tutte le impostazioni di PowerShell in conflitto all'avvio. Per consentire agli utenti di definire il valore tramite PowerShell, utilizzare l'opzione "Definito dall'utente" per la regola nella piattaforma di gestione.

1. Digita **powershell** nel menu Start, fai clic con il pulsante destro **del** mouse Windows PowerShell e scegli Esegui **come amministratore.**

2. Immettere il cmdlet seguente:

    ```PowerShell
    Set-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Enabled
    ```

    Per abilitare le regole di registrazione asr in modalità di controllo, utilizzare il cmdlet seguente:

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions AuditMode
    ```

    Per disattivare le regole asr, utilizzare il cmdlet seguente:

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Disabled
    ```

    > [!IMPORTANT]
    > È necessario specificare lo stato singolarmente per ogni regola, ma è possibile combinare regole e stati in un elenco delimitato da virgole.
    >
    > Nell'esempio seguente verranno abilitate le prime due regole, la terza verrà disabilitata e la quarta verrà abilitata in modalità di controllo:
    >
    > ```PowerShell
    > Set-MpPreference -AttackSurfaceReductionRules_Ids <rule ID 1>,<rule ID 2>,<rule ID 3>,<rule ID 4> -AttackSurfaceReductionRules_Actions Enabled, Enabled, Disabled, AuditMode
    > ```

    È inoltre possibile utilizzare il `Add-MpPreference` verbo PowerShell per aggiungere nuove regole all'elenco esistente.

    > [!WARNING]
    > `Set-MpPreference` sovrascriverà sempre il set di regole esistente. Se vuoi aggiungerlo al set esistente, usa `Add-MpPreference` invece.
    > È possibile ottenere un elenco di regole e il relativo stato corrente utilizzando `Get-MpPreference` .

3. Per escludere file e cartelle dalle regole asr, utilizzare il cmdlet seguente:

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionOnlyExclusions "<fully qualified path or resource>"
    ```

    Continuare a utilizzare `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` per aggiungere altri file e cartelle all'elenco.

    > [!IMPORTANT]
    > Usa `Add-MpPreference` per aggiungere o aggiungere app all'elenco. `Set-MpPreference`L'utilizzo del cmdlet sovrascriverà l'elenco esistente.

## <a name="related-articles"></a>Articoli correlati

- [Ridurre le superfici di attacco con le regole di riduzione della superficie di attacco](attack-surface-reduction.md)

- [Valutare la riduzione della superficie di attacco](evaluate-attack-surface-reduction.md)

- [Domande frequenti sulla riduzione della superficie di attacco](attack-surface-reduction.md)
