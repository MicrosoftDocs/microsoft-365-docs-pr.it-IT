---
title: Personalizzare l’accesso controllato alle cartelle
description: Aggiungi altre cartelle che devono essere protette dall'accesso controllato alle cartelle o consenti alle app che bloccano in modo errato le modifiche ai file importanti.
keywords: Accesso controllato alle cartelle, windows 10, windows defender, ransomware, proteggere, file, cartelle, personalizzare, aggiungere cartella, aggiungere app, consentire, aggiungere eseguibile
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: jcedola, dbodorin, vladiso, nixanm, anvascon
manager: dansimp
ms.date: 05/10/2021
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: e12368b6241a2c79eead66ed77b30b7864af3955
ms.sourcegitcommit: 68383240ef7a673d5f28e2ecfab9f105bf1d8c8f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "52326535"
---
# <a name="customize-controlled-folder-access"></a>Personalizzare l’accesso controllato alle cartelle

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

L'accesso controllato alle cartelle consente di proteggere i dati importanti da minacce e app dannose, ad esempio ransomware. L'accesso controllato alle cartelle è supportato Windows Server 2019 e Windows 10 client. In questo articolo viene descritto come personalizzare le funzionalità di accesso controllato alle cartelle e sono incluse le sezioni seguenti:

- [Proteggere cartelle aggiuntive](#protect-additional-folders)
- [Aggiungere app a cui dovrebbe essere consentito l'accesso alle cartelle protette](#allow-specific-apps-to-make-changes-to-controlled-folders)
- [Consenti ai file eseguibili firmati di accedere alle cartelle protette](#allow-signed-executable-files-to-access-protected-folders)
- [Personalizzare la notifica](#customize-the-notification)

> [!IMPORTANT]
> L'accesso controllato alle cartelle monitora le app per le attività rilevate come dannose. A volte, alle app legittime viene impedito di apportare modifiche ai file. Se l'accesso controllato alle cartelle influisce sulla produttività dell'organizzazione, è consigliabile eseguire questa funzionalità [in](audit-windows-defender.md) modalità di controllo per valutarne completamente l'impatto.

## <a name="protect-additional-folders"></a>Proteggere cartelle aggiuntive

L'accesso controllato alle cartelle si applica a molte cartelle di sistema e posizioni predefinite, incluse cartelle quali **Documenti,** **Immagini** e **Filmati.** È possibile aggiungere altre cartelle da proteggere, ma non è possibile rimuovere le cartelle predefinite nell'elenco predefinito.

L'aggiunta di altre cartelle all'accesso controllato alle cartelle può essere utile nei casi in cui non si archiviano file nelle raccolte Windows predefinite o se è stato modificato il percorso predefinito delle raccolte.

È inoltre possibile specificare condivisioni di rete e unità mappate. Sono supportati variabili di ambiente e caratteri jolly. Per informazioni sull'utilizzo dei caratteri jolly, vedere [Use wildcards in the file name and folder path or extension exclusion lists](configure-extension-file-exclusions-microsoft-defender-antivirus.md).

Puoi usare l'app Sicurezza di Windows, Criteri di gruppo, cmdlet di PowerShell o provider di servizi di configurazione per la gestione dei dispositivi mobili per aggiungere e rimuovere cartelle protette.

### <a name="use-the-windows-security-app-to-protect-additional-folders"></a>Usare l'app Sicurezza di Windows per proteggere cartelle aggiuntive

1. Apri l Sicurezza di Windows app selezionando l'icona scudo nella barra delle applicazioni o cercando sicurezza *nel* menu Start.

2. Seleziona **Protezione da & virus** e quindi scorri verso il basso fino alla sezione Protezione **ransomware.**

3. Seleziona **Gestisci protezione ransomware** per aprire il riquadro Protezione **ransomware.**

4. Nella sezione **Accesso controllato alle cartelle** selezionare Cartelle **protette**.

5. Scegliere **Sì** nel prompt **Controllo di accesso utente.** Verrà **visualizzato il** riquadro Cartelle protette.

6. Selezionare **Aggiungi una cartella protetta** e seguire le istruzioni per aggiungere cartelle.

### <a name="use-group-policy-to-protect-additional-folders"></a>Usare Criteri di gruppo per proteggere cartelle aggiuntive

1. Nel computer di gestione dei Criteri di gruppo aprire la [Console Gestione Criteri di gruppo](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true). 

2. Fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e quindi scegliere **Modifica**.

3. **Nell'Editor Gestione Criteri di gruppo** passare a Criteri di configurazione **computer**  >    >  **Modelli amministrativi.**

4. Espandere l'albero per **Windows componenti Antivirus Microsoft Defender** Windows Defender accesso controllato alle cartelle di  >    >  **Exploit Guard.**  >   <br/>**NOTA:** nelle versioni precedenti di Windows, potrebbe essere visualizzato **Windows Defender Antivirus** invece **di Antivirus Microsoft Defender**.

5. Fare doppio clic **su Cartelle protette configurate** e quindi impostare l'opzione su **Abilitato.** Selezionare **Mostra** e specificare ogni cartella che si desidera proteggere.

6. Distribuisci l'oggetto Criteri di gruppo come di solito.

### <a name="use-powershell-to-protect-additional-folders"></a>Usare PowerShell per proteggere cartelle aggiuntive

1. Digita **PowerShell** nel menu Start, fai clic con il pulsante destro **del** mouse Windows PowerShell e scegli Esegui **come amministratore**

2. Digitare il cmdlet PowerShell seguente, sostituendo con il percorso della `<the folder to be protected>` cartella (ad `"c:\apps\"` esempio):

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessProtectedFolders "<the folder to be protected>"
    ```
3. Ripetere il passaggio 2 per ogni cartella che si desidera proteggere. Le cartelle protette sono visibili nell Sicurezza di Windows app.

   :::image type="content" source="images/cfa-allow-folder-ps.png" alt-text="Finestra di PowerShell con il cmdlet visualizzato":::

> [!IMPORTANT]
> Usa `Add-MpPreference` per aggiungere o aggiungere app all'elenco e non `Set-MpPreference` . `Set-MpPreference`L'utilizzo del cmdlet sovrascriverà l'elenco esistente.

### <a name="use-mdm-csps-to-protect-additional-folders"></a>Usare CSP MDM per proteggere cartelle aggiuntive

Usa il provider di servizi di configurazione [./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersList](/windows/client-management/mdm/policy-csp-defender#defender-guardedfolderslist) per consentire alle app di apportare modifiche alle cartelle protette.

## <a name="allow-specific-apps-to-make-changes-to-controlled-folders"></a>Consenti ad app specifiche di apportare modifiche alle cartelle controllate

Puoi specificare se determinate app sono sempre considerate sicure e concedere l'accesso in scrittura ai file nelle cartelle protette. Consentire le app può essere utile se una determinata app che conosci e considera attendibile viene bloccata dalla funzionalità di accesso controllato alle cartelle.

> [!IMPORTANT]
> Per impostazione predefinita, Windows app considerate descrittive all'elenco di elementi consentiti. Tali app aggiunte automaticamente non vengono registrate nell'elenco visualizzato nell'app Sicurezza di Windows o tramite i cmdlet di PowerShell associati. Non è necessario aggiungere la maggior parte delle app. Aggiungi app solo se vengono bloccate e puoi verificarne l'attendibilità.

Quando aggiungi un'app, devi specificare la posizione dell'app. Solo l'app in tale percorso sarà autorizzata ad accedere alle cartelle protette. Se l'app (con lo stesso nome) si trova in un percorso diverso, non verrà aggiunta all'elenco degli elementi consentiti e potrebbe essere bloccata dall'accesso controllato alle cartelle.

Un'applicazione o un servizio consentito ha accesso in scrittura a una cartella controllata solo dopo l'avvio. Ad esempio, un servizio di aggiornamento continuerà a attivare eventi dopo che è consentito fino a quando non viene arrestato e riavviato.

### <a name="use-the-windows-defender-security-app-to-allow-specific-apps"></a>Usare l'app Windows Defender Sicurezza per consentire app specifiche

1. Apri l Sicurezza di Windows app cercando Sicurezza **nel** menu Start.

2. Seleziona il **riquadro Protezione da &** virus (o l'icona scudo sulla barra dei menu sinistra) e quindi seleziona Gestisci protezione **ransomware.**

3. Nella sezione **Accesso controllato alle cartelle** seleziona Consenti **un'app tramite Accesso controllato alle cartelle**

4. Seleziona **Aggiungi un'app consentita** e segui le istruzioni per aggiungere app.

   :::image type="content" source="images/cfa-allow-app.png" alt-text="Pulsante Aggiungi un'app consentita":::

### <a name="use-group-policy-to-allow-specific-apps"></a>Usare Criteri di gruppo per consentire app specifiche

1. Nel dispositivo di gestione di Criteri di gruppo, aprire la [Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true)Gestione Criteri di gruppo, fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e scegliere **Modifica**.

2. Nell **'Editor Gestione Criteri di gruppo** passare a **Configurazione computer** e selezionare **Modelli amministrativi**.

3. Espandere l'albero per **Windows componenti Antivirus Microsoft Defender** Windows Defender accesso controllato alle cartelle di  >    >  **Exploit Guard.**  >  

4. Fare doppio clic **sull'impostazione Configura applicazioni consentite** e impostare l'opzione su **Abilitato.** Seleziona **Mostra** e immetti ogni app.

### <a name="use-powershell-to-allow-specific-apps"></a>Usare PowerShell per consentire app specifiche

1. Digita **PowerShell** nel menu Start, fai clic con il pulsante destro **del** mouse Windows PowerShell e scegli Esegui **come amministratore**
2. Immettere il cmdlet seguente:

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessAllowedApplications "<the app that should be allowed, including the path>"
    ```

    Ad esempio, per aggiungere il *test.exe* eseguibile nella cartella *C:\apps,* il cmdlet sarà il seguente:

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessAllowedApplications "c:\apps\test.exe"
    ```

   Continua a usare `Add-MpPreference -ControlledFolderAccessAllowedApplications` per aggiungere altre app all'elenco. Le app aggiunte utilizzando questo cmdlet verranno visualizzate nell'app Sicurezza di Windows app.

   :::image type="content" source="images/cfa-allow-app-ps.png" alt-text="Cmdlet di PowerShell per consentire un'app":::

> [!IMPORTANT]
> Usa `Add-MpPreference` per aggiungere o aggiungere app all'elenco. `Set-MpPreference`L'utilizzo del cmdlet sovrascriverà l'elenco esistente.

### <a name="use-mdm-csps-to-allow-specific-apps"></a>Usare CSP MDM per consentire app specifiche

Usa il provider di servizi di configurazione [./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersAllowedApplications](/windows/client-management/mdm/policy-csp-defender#defender-guardedfoldersallowedapplications) per consentire alle app di apportare modifiche alle cartelle protette.

## <a name="allow-signed-executable-files-to-access-protected-folders"></a>Consenti ai file eseguibili firmati di accedere alle cartelle protette

Gli indicatori di file e certificati di Microsoft Defender for Endpoint possono consentire ai file eseguibili firmati di accedere alle cartelle protette. Per informazioni dettagliate sull'implementazione, vedere [Create indicators based on certificates](indicator-certificates.md).

> [!Note]
> Ciò non si applica ai motori di script, incluso Powershell

## <a name="customize-the-notification"></a>Personalizzare la notifica

Per altre informazioni sulla personalizzazione della notifica quando viene attivata una regola e blocca un'app o un file, vedi Configurare le notifiche di [avviso in Microsoft Defender for Endpoint.](configure-email-notifications.md)

## <a name="see-also"></a>Vedere anche

- [Proteggere le cartelle importanti con l'accesso controllato alle cartelle](controlled-folders.md)
- [Abilitare l’accesso controllato alle cartelle](enable-controlled-folders.md)
- [Valutare le regole per la riduzione della superficie di attacco](evaluate-attack-surface-reduction.md)
