---
title: Gestire come e dove Antivirus Microsoft Defender ricevere gli aggiornamenti
description: Gestire l'ordine di fallback per la modalità Antivirus Microsoft Defender ricevere gli aggiornamenti di protezione.
keywords: aggiornamenti, linee di base della sicurezza, protezione, ordine di fallback, ADL, MMPC, UNC, percorso file, condivisione, wsus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.reviewer: pahuijbr
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.openlocfilehash: 35873b371e773e793ae966a338150e2e5e256a42
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926032"
---
# <a name="manage-the-sources-for-microsoft-defender-antivirus-protection-updates"></a>Gestire le origini per gli aggiornamenti di protezione di Microsoft Defender Antivirus

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**

- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=22154037)

<a id="protection-updates"></a>
<!-- this has been used as anchor in VDI content -->

Mantenere aggiornata la protezione antivirus è fondamentale. Esistono due componenti per la gestione degli aggiornamenti di protezione per Antivirus Microsoft Defender: 
- *Da* dove vengono scaricati gli aggiornamenti; e 
- *Quando* gli aggiornamenti vengono scaricati e applicati. 

In questo articolo viene descritto come specificare da dove scaricare gli aggiornamenti (questo è noto anche come ordine di fallback). Per [una panoramica sul](manage-updates-baselines-microsoft-defender-antivirus.md) funzionamento degli aggiornamenti e su come configurare altri aspetti degli aggiornamenti, ad esempio la pianificazione degli aggiornamenti, vedere Gestire gli aggiornamenti Antivirus Microsoft Defender e applicare le linee di base.

> [!IMPORTANT]
> Antivirus Microsoft Defender Gli aggiornamenti delle funzionalità di intelligence per la sicurezza vengono recapitati tramite Windows Update e a partire da lunedì 21 ottobre 2019, tutti gli aggiornamenti di intelligence per la sicurezza saranno firmati esclusivamente da SHA-2. I dispositivi devono essere aggiornati per supportare SHA-2 per aggiornare le informazioni di sicurezza. Per ulteriori informazioni, vedere [2019 Sha-2 Code Signing Support requirement for Windows and WSUS](https://support.microsoft.com/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus).  


<a id="fallback-order"></a>

## <a name="fallback-order"></a>Ordine di fallback

In genere, si configurano gli endpoint per scaricare singolarmente gli aggiornamenti da un'origine principale seguita da altre origini in ordine di priorità, in base alla configurazione di rete. Gli aggiornamenti vengono ottenuti dalle origini nell'ordine specificato. Se non è disponibile un'origine, viene utilizzata immediatamente l'origine successiva nell'elenco.

Quando vengono pubblicati gli aggiornamenti, viene applicata una logica per ridurre al minimo le dimensioni dell'aggiornamento. Nella maggior parte dei casi, vengono scaricate e applicate solo le differenze tra l'aggiornamento più recente e l'aggiornamento attualmente installato (denominato delta). Tuttavia, le dimensioni del delta dipendono da due fattori principali:
- Validità dell'ultimo aggiornamento nel dispositivo; e 
- Origine utilizzata per scaricare e applicare gli aggiornamenti. 

Più vecchi sono gli aggiornamenti in un endpoint, più grande sarà il download. Tuttavia, è necessario considerare anche la frequenza di download. Una pianificazione di aggiornamento più frequente può comportare un maggiore utilizzo della rete, mentre una pianificazione meno frequente può comportare dimensioni di file più grandi per download. 

Esistono cinque posizioni in cui è possibile specificare dove un endpoint deve ottenere gli aggiornamenti: 

- [Microsoft Update](https://support.microsoft.com/help/12373/windows-update-faq)
- [Windows Server Update Service](/windows-server/administration/windows-server-update-services/get-started/windows-server-update-services-wsus)
- [Microsoft Endpoint Configuration Manager](/configmgr/core/servers/manage/updates)
- [Condivisione file di rete](#unc-share)
- Aggiornamenti di intelligence per la sicurezza per Antivirus Microsoft Defender e altri [antimalware Microsoft](https://www.microsoft.com/en-us/wdsi/defenderupdates) (il criterio e il Registro di sistema potrebbero essere elencati come intelligence di sicurezza Microsoft Malware Protection Center (MMPC), il suo nome precedente.

Per garantire il miglior livello di protezione, Microsoft Update consente rilasci rapidi, ovvero download più piccoli su base frequente. Le origini Windows server Update Service, Microsoft Endpoint Configuration Manager e Microsoft security intelligence offrono aggiornamenti meno frequenti. Di conseguenza, il delta può essere più grande, con conseguente download più grandi. 

> [!IMPORTANT]
> Se gli aggiornamenti delle pagine di Intelligence per la sicurezza [Microsoft](https://www.microsoft.com/security/portal/definitions/adl.aspx) sono stati impostati come origine di fallback dopo Windows Server Update Service o Microsoft Update, gli aggiornamenti vengono scaricati solo dagli aggiornamenti delle funzionalità di intelligence per la sicurezza quando l'aggiornamento corrente viene considerato non aggiornato. Per impostazione predefinita, si tratta di sette giorni consecutivi in cui non è possibile applicare gli aggiornamenti da Windows Server Update Service o Microsoft Update Services.
> È tuttavia possibile impostare il numero di giorni prima che la protezione venga segnalata come [non aggiornata.](/windows/threat-protection/microsoft-defender-antivirus/manage-outdated-endpoints-microsoft-defender-antivirus#set-the-number-of-days-before-protection-is-reported-as-out-of-date)<p>
> A partire da lunedì 21 ottobre 2019, gli aggiornamenti dell'intelligence per la sicurezza saranno firmati in esclusiva con SHA-2. I dispositivi devono essere aggiornati per supportare SHA-2 per ottenere gli aggiornamenti più recenti delle funzionalità di intelligence per la sicurezza. Per ulteriori informazioni, vedere [2019 Sha-2 Code Signing Support requirement for Windows and WSUS](https://support.microsoft.com/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus).

Ogni origine presenta scenari tipici che dipendono dalla configurazione della rete, oltre alla frequenza con cui pubblicano gli aggiornamenti, come descritto nella tabella seguente:

|Posizione | Scenario di esempio |
|---|---|
|Windows Server Update Service | Si sta utilizzando Windows Server Update Service per gestire gli aggiornamenti per la rete.|
|Microsoft Update | Vuoi che gli endpoint si connettano direttamente a Microsoft Update. Ciò può essere utile per gli endpoint che si connettono in modo irregolare alla rete aziendale o se non si utilizza Windows Server Update Service per gestire gli aggiornamenti.|
|Condivisione file | Si dispone di dispositivi non connessi a Internet ,ad esempio macchine virtuali. È possibile usare l'host vm connesso a Internet per scaricare gli aggiornamenti in una condivisione di rete, da cui le macchine virtuali possono ottenere gli aggiornamenti. Vedi la [guida alla distribuzione di VDI](deployment-vdi-microsoft-defender-antivirus.md) per informazioni su come usare le condivisioni file in ambienti VDI (Virtual Desktop Infrastructure).|
|Microsoft Endpoint Manager | Si sta usando Microsoft Endpoint Manager per aggiornare gli endpoint.|
|Aggiornamenti delle informazioni di sicurezza per Antivirus Microsoft Defender e altri antimalware Microsoft (in precedenza noto come MMPC) |[Assicurati che i dispositivi siano aggiornati per supportare SHA-2.](https://support.microsoft.com/help/4472027/2019-sha-2-code-signing-support-requirement-for-windows-and-wsus) Antivirus Microsoft Defender Gli aggiornamenti delle informazioni di sicurezza vengono recapitati tramite Windows Update e a partire da lunedì 21 ottobre 2019 gli aggiornamenti delle informazioni di sicurezza saranno firmati esclusivamente da SHA-2. <br/>Scaricare gli aggiornamenti di protezione più recenti a causa di un'infezione recente o per fornire un'immagine di base avanzata per [la distribuzione VDI.](deployment-vdi-microsoft-defender-antivirus.md) Questa opzione in genere deve essere utilizzata solo come origine di fallback finale e non come origine primaria. Verrà utilizzato solo se non è possibile scaricare gli aggiornamenti da Windows Server Update Service o Microsoft Update per [un numero di giorni specificato.](/windows/threat-protection/microsoft-defender-antivirus/manage-outdated-endpoints-microsoft-defender-antivirus#set-the-number-of-days-before-protection-is-reported-as-out-of-date)|

È possibile gestire l'ordine in cui le origini di aggiornamento vengono utilizzate con Criteri di gruppo, Microsoft Endpoint Configuration Manager, cmdlet di PowerShell e WMI.

> [!IMPORTANT]
> Se si imposta Windows Server Update Service come percorso di download, è necessario approvare gli aggiornamenti, indipendentemente dello strumento di gestione utilizzato per specificare il percorso. È possibile configurare una regola di approvazione automatica con Windows Server Update Service, che potrebbe essere utile in quanto gli aggiornamenti arrivano almeno una volta al giorno. Per ulteriori informazioni, vedere [synchronize endpoint protection updates in standalone Windows Server Update Service.](/configmgr/protect/deploy-use/endpoint-definitions-wsus#to-synchronize-endpoint-protection-definition-updates-in-standalone-wsus)

Le procedure descritte in questo articolo descrivono innanzitutto come impostare l'ordine e quindi come configurare l'opzione **Condivisione file,** se è stata abilitata.

## <a name="use-group-policy-to-manage-the-update-location"></a>Utilizzare Criteri di gruppo per gestire il percorso di aggiornamento

1. Nel computer di gestione di Criteri di gruppo, aprire Console Gestione Criteri di [gruppo,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e scegliere **Modifica**.

2. **Nell'Editor Gestione Criteri di gruppo** passare a Configurazione **computer**.

3. Fare **clic su Criteri** e quindi su Modelli **amministrativi.**

4. Espandere l'albero per **Windows componenti > Windows Defender > aggiornamenti delle firme** e configurare le impostazioni seguenti:

   1.  Fare doppio clic **sull'impostazione Definisci l'ordine** delle origini per il download degli aggiornamenti delle funzionalità di intelligence per la sicurezza e impostare l'opzione su **Abilitato.**

   2.  Immettere l'ordine delle origini, separato da una singola pipe, ad esempio: `InternalDefinitionUpdateServer|MicrosoftUpdateServer|MMPC` , come illustrato nello screenshot seguente.

   ![Screenshot dell'impostazione di Criteri di gruppo che elenca l'ordine delle origini](images/defender/wdav-order-update-sources.png)

   3. Fare clic su **OK**. In questo modo verrà impostato l'ordine delle origini degli aggiornamenti di protezione.

   4. Fare doppio clic **sull'impostazione Definisci condivisioni file per il download degli aggiornamenti di Security Intelligence** e impostare l'opzione su **Abilitato.**

   5. Immettere l'origine della condivisione file. Se si dispone di più origini, immettere ogni origine nell'ordine in cui devono essere utilizzate, separate da una singola pipe. Utilizzare [la notazione UNC standard](/openspecs/windows_protocols/ms-dtyp/62e862f4-2a51-452e-8eeb-dc4ff5ee33cc) per denotare il percorso, ad esempio: `\\host-name1\share-name\object-name|\\host-name2\share-name\object-name` .  Se non si immette alcun percorso, questa origine verrà ignorata quando la macchina virtuale scarica gli aggiornamenti.

   6. Fare clic su **OK**. In questo modo verrà impostato l'ordine delle  condivisioni file quando viene fatto riferimento a tale origine nell'impostazione di Criteri di gruppo Definisci l'ordine delle origini.

> [!NOTE]
> Per Windows 10, versioni 1703 fino alla 1809 inclusa, il percorso dei criteri è **Windows Components > Antivirus Microsoft Defender > Signature Updates** For Windows 10, versione 1903, il percorso dei criteri è Windows Components > Antivirus Microsoft Defender > Security Intelligence **Updates**

## <a name="use-configuration-manager-to-manage-the-update-location"></a>Usare Configuration Manager per gestire il percorso di aggiornamento

Vedere [Configure Security intelligence Updates for Endpoint Protection](/configmgr/protect/deploy-use/endpoint-definition-updates) for details on configuring Microsoft Endpoint Manager (current branch).


## <a name="use-powershell-cmdlets-to-manage-the-update-location"></a>Utilizzare i cmdlet di PowerShell per gestire il percorso di aggiornamento

Utilizzare i cmdlet di PowerShell seguenti per impostare l'ordine di aggiornamento.

```PowerShell
Set-MpPreference -SignatureFallbackOrder {LOCATION|LOCATION|LOCATION|LOCATION}
Set-MpPreference -SignatureDefinitionUpdateFileSharesSource {\\UNC SHARE PATH|\\UNC SHARE PATH}
```
Per ulteriori informazioni, vedere gli articoli seguenti:
- [Set-MpPreference -SignatureFallbackOrder](/powershell/module/defender/set-mppreference)
- [Set-MpPreference -SignatureDefinitionUpdateFileSharesSource](/powershell/module/defender/set-mppreference#-signaturedefinitionupdatefilesharessources)
- [Utilizzare i cmdlet di PowerShell per configurare ed eseguire Antivirus Microsoft Defender](use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [Cmdlet defender](/powershell/module/defender/index)

## <a name="use-windows-management-instruction-wmi-to-manage-the-update-location"></a>Utilizzare Windows Management Instruction (WMI) per gestire il percorso di aggiornamento

Utilizzare il [ **metodo Set** della **classe MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) per le proprietà seguenti:

```WMI
SignatureFallbackOrder
SignatureDefinitionUpdateFileSharesSource
```

Per ulteriori informazioni, vedere gli articoli seguenti:
- [Windows Defender API WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="use-mobile-device-management-mdm-to-manage-the-update-location"></a>Usare Gestione dispositivi mobili (MDM) per gestire la posizione di aggiornamento

Vedi [CSP criteri - Defender/SignatureUpdateFallbackOrder](/windows/client-management/mdm/policy-csp-defender#defender-signatureupdatefallbackorder) per informazioni dettagliate sulla configurazione di MDM.

## <a name="what-if-were-using-a-third-party-vendor"></a>Cosa succede se si utilizza un fornitore di terze parti?

In questo articolo viene descritto come configurare e gestire gli aggiornamenti per Antivirus Microsoft Defender. Tuttavia, è possibile utilizzare fornitori di terze parti per eseguire queste attività. 

Si supponga, ad esempio, che Contoso abbia assunto Fabrikam per gestire la soluzione di sicurezza, che include Antivirus Microsoft Defender. Fabrikam in [genere utilizza Windows Management Instrumentation,](./use-wmi-microsoft-defender-antivirus.md)i [](./command-line-arguments-microsoft-defender-antivirus.md) cmdlet [di PowerShell](./use-powershell-cmdlets-microsoft-defender-antivirus.md)o Windows riga di comando per distribuire patch e aggiornamenti. 

> [!NOTE]
> Microsoft non testa soluzioni di terze parti per la gestione Antivirus Microsoft Defender.

<a id="unc-share"></a>
## <a name="create-a-unc-share-for-security-intelligence-updates"></a>Creare una condivisione UNC per gli aggiornamenti delle funzionalità di intelligence per la sicurezza

Configurare una condivisione file di rete (unità UNC/mappata) per scaricare gli aggiornamenti delle informazioni di sicurezza dal sito MMPC utilizzando un'attività pianificata.

1. Nel sistema in cui si desidera effettuare il provisioning della condivisione e scaricare gli aggiornamenti, creare una cartella in cui salvare lo script.
    ```DOS
    Start, CMD (Run as admin)
    MD C:\Tool\PS-Scripts\
    ```

2. Creare la cartella in cui si salveranno gli aggiornamenti delle firme.
    ```DOS
    MD C:\Temp\TempSigs\x64
    MD C:\Temp\TempSigs\x86
    ```

3. Scaricare lo script di PowerShell [da www.powershellgallery.com/packages/SignatureDownloadCustomTask/1.4](https://www.powershellgallery.com/packages/SignatureDownloadCustomTask/1.4).

4. Fare clic **su Download manuale**.

5. Fare **clic su Scarica il file nupkg non elaborato.**

6. Estrarre il file.

7. Copiare il SignatureDownloadCustomTask.ps1 file nella cartella creata in precedenza, C:\Tool\PS-Scripts\ .

8. Utilizzare la riga di comando per configurare l'attività pianificata.
    > [!NOTE]
    > Esistono due tipi di aggiornamenti: completo e delta.
   - Per delta x64:

       ```DOS
       Powershell (Run as admin)
    
       C:\Tool\PS-Scripts\
    
       ".\SignatureDownloadCustomTask.ps1 -action create -arch x64 -isDelta $true -destDir C:\Temp\TempSigs\x64 -scriptPath C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1 -daysInterval 1"
       ```

   - Per x64 completo:

       ```DOS
       Powershell (Run as admin)
    
       C:\Tool\PS-Scripts\
    
       ".\SignatureDownloadCustomTask.ps1 -action create -arch x64 -isDelta $false -destDir C:\Temp\TempSigs\x64 -scriptPath C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1 -daysInterval 1"
       ```

   - Per delta x86:

       ```DOS
       Powershell (Run as admin)
    
       C:\Tool\PS-Scripts\
    
       ".\SignatureDownloadCustomTask.ps1 -action create -arch x86 -isDelta $true -destDir C:\Temp\TempSigs\x86 -scriptPath C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1 -daysInterval 1"
       ```

   - Per x86 completo:

       ```DOS
       Powershell (Run as admin)
    
       C:\Tool\PS-Scripts\
    
       ".\SignatureDownloadCustomTask.ps1 -action create -arch x86 -isDelta $false -destDir C:\Temp\TempSigs\x86 -scriptPath C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1 -daysInterval 1"
       ```

    > [!NOTE]
    > Quando vengono create le attività pianificate, è possibile trovarle nell'Utilità di pianificazione in Microsoft\Windows\Windows Defender
9. Eseguire ogni attività manualmente e verificare di disporre di dati (mpam-d.exe, mpam-fe.exe e nis_full.exe) nelle cartelle seguenti (è possibile che siano state scelte posizioni diverse):

   - C:\Temp\TempSigs\x86
   - C:\Temp\TempSigs\x64

   Se l'attività pianificata ha esito negativo, eseguire i comandi seguenti:

    ```DOS
    C:\windows\system32\windowspowershell\v1.0\powershell.exe -NoProfile -executionpolicy allsigned -command "&\"C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1\" -action run -arch x64 -isDelta $False -destDir C:\Temp\TempSigs\x64"
    
    C:\windows\system32\windowspowershell\v1.0\powershell.exe -NoProfile -executionpolicy allsigned -command "&\"C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1\" -action run -arch x64 -isDelta $True -destDir C:\Temp\TempSigs\x64"
    
    C:\windows\system32\windowspowershell\v1.0\powershell.exe -NoProfile -executionpolicy allsigned -command "&\"C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1\" -action run -arch x86 -isDelta $False -destDir C:\Temp\TempSigs\x86"
    
    C:\windows\system32\windowspowershell\v1.0\powershell.exe -NoProfile -executionpolicy allsigned -command "&\"C:\Tool\PS-Scripts\SignatureDownloadCustomTask.ps1\" -action run -arch x86 -isDelta $True -destDir C:\Temp\TempSigs\x86"
    ```
    > [!NOTE]
    > I problemi potrebbero essere dovuti anche ai criteri di esecuzione.
    
10. Creare una condivisione che punti a C:\Temp\TempSigs (ad \\ esempio, server\aggiornamenti).
    > [!NOTE]
    > Come minimo, gli utenti autenticati devono disporre dell'accesso "Lettura".
11. Imposta il percorso di condivisione nel criterio sulla condivisione.

    > [!NOTE]
    > Non aggiungere la cartella x64 (o x86) nel percorso. Il mpcmdrun.exe viene aggiunto automaticamente.

## <a name="related-articles"></a>Articoli correlati

- [Distribuire Antivirus Microsoft Defender](deploy-manage-report-microsoft-defender-antivirus.md)
- [Gestire Antivirus Microsoft Defender aggiornamenti e applicare linee di base](manage-updates-baselines-microsoft-defender-antivirus.md)
- [Gestire gli aggiornamenti per gli endpoint non aggiornati](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [Gestire gli aggiornamenti forzati basati su eventi](manage-event-based-updates-microsoft-defender-antivirus.md)
- [Gestire gli aggiornamenti per dispositivi mobili e macchine virtuali](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [Antivirus Microsoft Defender in Windows 10](microsoft-defender-antivirus-in-windows-10.md)
