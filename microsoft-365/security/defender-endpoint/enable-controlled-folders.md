---
title: Abilitare l’accesso controllato alle cartelle
keywords: Accesso controllato alle cartelle, Windows 10, windows defender, ransomware, proteggere, file, cartelle, abilitare, attivare, usare
description: Informazioni su come proteggere i file importanti abilitando l'accesso controllato alle cartelle
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: dansimp
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: ee87ac3bdfe88596a5f1625904af53499488f35f
ms.sourcegitcommit: 6e5c00f84b5201422aed094f2697016407df8fc2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2021
ms.locfileid: "51571009"
---
# <a name="enable-controlled-folder-access"></a>Abilitare l’accesso controllato alle cartelle

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

[L'accesso controllato](controlled-folders.md) alle cartelle consente di proteggere i dati importanti da minacce e app dannose, ad esempio ransomware. L'accesso controllato alle cartelle è incluso in Windows 10 e Windows Server 2019.

È possibile abilitare l'accesso controllato alle cartelle utilizzando uno dei metodi seguenti:

* [App Sicurezza di Windows](#windows-security-app)
* [Microsoft Intune](#intune)
* [Gestione di dispositivi mobili (MDM)](#mobile-device-management-mdm)
* [Microsoft Endpoint Configuration Manager](#microsoft-endpoint-configuration-manager)
* [Criteri di gruppo](#group-policy)
* [PowerShell](#powershell)

[La modalità](evaluate-controlled-folder-access.md) di controllo consente di testare il funzionamento della funzionalità (e di esaminare gli eventi) senza influire sul normale utilizzo del dispositivo.

Le impostazioni di Criteri di gruppo che disabilitano l'unione degli elenchi di amministratori locali avranno la precedenza su impostazioni di accesso controllato alle cartelle. Ignorano anche le cartelle protette e le app consentite impostate dall'amministratore locale tramite l'accesso controllato alle cartelle. Questi criteri includono:

* Microsoft Defender Antivirus **Configurare il comportamento di unione dell'amministratore locale per gli elenchi**
* System Center Endpoint Protection **Consenti agli utenti di aggiungere esclusioni e sostituzioni**

Per ulteriori informazioni sulla disabilitazione dell'unione di elenchi locali, vedere Impedire o consentire agli utenti di modificare localmente le impostazioni dei criteri [di Microsoft Defender AV.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-local-policy-overrides-microsoft-defender-antivirus#configure-how-locally-and-globally-defined-threat-remediation-and-exclusions-lists-are-merged)

## <a name="windows-security-app"></a>App Sicurezza di Windows

1. Apri l'app Sicurezza di Windows selezionando l'icona scudo nella barra delle applicazioni. Puoi anche cercare Defender nel menu **Start.**

2. Seleziona il **riquadro Protezione da &** virus (o l'icona scudo sulla barra dei menu sinistra) e quindi seleziona Protezione **ransomware.**

3. Impostare l'opzione **Accesso controllato alle cartelle** su **Attiva.**

> [!NOTE]
> Se l'accesso controllato alle cartelle è configurato con Criteri di gruppo, PowerShell o CSP MDM, lo stato cambierà nell'app Sicurezza di Windows dopo un riavvio del dispositivo.
> Se la funzionalità è impostata sulla **modalità** di controllo con uno di questi strumenti, l'app Sicurezza di Windows mostrerà lo stato come **Disattivato.**
> Se stai proteggendo i dati del profilo utente, ti consigliamo di usare il profilo utente nell'unità di installazione predefinita di Windows.

## <a name="intune"></a>Intune

1. Accedi al portale [di Azure e](https://portal.azure.com) apri Intune.

2. Vai a **Profili di configurazione** dei  >  **dispositivi**  >  **Crea profilo**.

3. Assegnare un nome al profilo, **scegliere Windows 10 e versioni successive** e Endpoint **protection.** <br/> ![Creare il profilo di endpoint protection](/microsoft-365/security/defender-endpoint/images/create-endpoint-protection-profile) <br/>

4. Vai a **Configura Windows Defender** accesso controllato alla cartella di  >  **Exploit Guard**  >    >  **Abilita**.

5. Digitare il percorso di ogni applicazione che ha accesso alle cartelle protette e il percorso di qualsiasi cartella aggiuntiva che necessita di protezione. Selezionare **Aggiungi**.<br/> ![Abilitare l'accesso controllato alle cartelle in Intune](/microsoft-365/security/defender-endpoint/images/enable-cfa-intune)<br/>

   > [!NOTE]
   > Wilcard è supportato per le applicazioni, ma non per le cartelle. Le sottocartelle non sono protette. Le app consentite continueranno a attivare eventi finché non vengono riavviate.

6. Selezionare **OK** per salvare ogni pannello aperto e **Crea**.

7. Selezionare il profilo **Assegnazioni,** assegnare a **Tutti gli utenti & Tutti i dispositivi** e **Salva**.

## <a name="mobile-device-management-mdm"></a>Gestione di dispositivi mobili (MDM)

Usa il provider di servizi di configurazione [./Vendor/MSFT/Policy/Config/ControlledFolderAccessProtectedFolders](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-controlledfolderaccessprotectedfolders) per consentire alle app di apportare modifiche alle cartelle protette.

## <a name="microsoft-endpoint-configuration-manager"></a>Microsoft Endpoint Configuration Manager

1. In Microsoft Endpoint Configuration Manager, vai a **Assets and Compliance**  >  **Endpoint Protection**  >  **Windows Defender Exploit Guard**.

2. Selezionare **Home**  >  **Create Exploit Guard Policy**.

3. Immettere un nome e una descrizione, selezionare **Accesso controllato alle cartelle** e selezionare **Avanti.**

4. Scegli se bloccare o controllare le modifiche, consentire altre app o aggiungere altre cartelle e selezionare **Avanti.**
   > [!NOTE]
   > Wilcard è supportato per le applicazioni, ma non per le cartelle. Le sottocartelle non sono protette. Le app consentite continueranno a attivare eventi finché non vengono riavviate.

5. Rivedere le impostazioni e selezionare **Avanti** per creare il criterio.

6. Dopo la creazione del criterio, **chiudere**.

## <a name="group-policy"></a>Criteri di gruppo

1. Nel dispositivo di gestione di Criteri di gruppo, aprire la [Console](https://technet.microsoft.com/library/cc731212.aspx)Gestione Criteri di gruppo, fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e scegliere **Modifica**.

2. **Nell'Editor Gestione Criteri di gruppo** passare a Configurazione **computer** e selezionare **Modelli amministrativi.**

3. Espandi l'albero fino ai componenti **di Windows > Microsoft Defender Antivirus > Windows Defender Exploit Guard > accesso controllato alle cartelle.**

4. Fare doppio clic **sull'impostazione Configura accesso controllato alle** cartelle e impostare l'opzione su **Abilitato.** Nella sezione opzioni è necessario specificare una delle opzioni seguenti:
    * **Abilita:** le app dannose e sospette non possono apportare modifiche ai file nelle cartelle protette. Nel registro eventi di Windows verrà fornita una notifica.
    * **Disabilita (impostazione predefinita):** la funzionalità Accesso controllato alle cartelle non funzionerà. Tutte le app possono apportare modifiche ai file nelle cartelle protette.
    * **Modalità di controllo:** le modifiche saranno consentite se un'app dannosa o sospetta tenta di apportare una modifica a un file in una cartella protetta. Tuttavia, verrà registrato nel registro eventi di Windows in cui è possibile valutare l'impatto sull'organizzazione.
    * **Blocca solo la modifica del disco:** i tentativi da parte di app non attendibili di scrivere nei settori del disco verranno registrati nel registro eventi di Windows. Questi registri sono disponibili in **Registri** applicazioni e servizi > Microsoft > Windows > Windows Defender > Operational > ID 1123.
    * **Controlla solo** la modifica del disco: solo i tentativi di scrittura nei settori del disco protetti verranno registrati nel registro eventi di Windows (in Registri applicazioni e servizi Microsoft Windows Windows Defender ID operativo  >    >    >    >    >  **1124**). I tentativi di modifica o eliminazione di file nelle cartelle protette non verranno registrati.

      ![Screenshot of the group policy option Enabled and Audit Mode selected in the drop-down](/microsoft-365/security/defender-endpoint/images/cfa-gp-enable)

> [!IMPORTANT]
> Per abilitare completamente l'accesso controllato alle cartelle, devi impostare l'opzione Criteri di gruppo su **Abilitato** e selezionare **Blocca** nel menu a discesa delle opzioni.

## <a name="powershell"></a>PowerShell

1. Digita **powershell** nel menu Start, fai clic con il pulsante destro **del** mouse Windows PowerShell e scegli Esegui **come amministratore.**

2. Immettere il cmdlet seguente:

    ```PowerShell
    Set-MpPreference -EnableControlledFolderAccess Enabled
    ```

È possibile abilitare la funzionalità in modalità di controllo specificando `AuditMode` invece `Enabled` di .

Consente `Disabled` di disattivare la funzionalità.

## <a name="see-also"></a>Vedere anche

* [Proteggere le cartelle importanti con l'accesso controllato alle cartelle](controlled-folders.md)
* [Personalizzare l’accesso controllato alle cartelle](customize-controlled-folders.md)
* [Valutare Microsoft Defender per endpoint.](evaluate-mde.md)
