---
title: Abilitare l’accesso controllato alle cartelle
keywords: Accesso controllato alle cartelle, Windows 10, windows defender, ransomware, proteggere, file, cartelle, abilitare, attivare, usare
description: Informazioni su come proteggere i file importanti abilitando l'accesso controllato alle cartelle
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.topic: article
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
ms.openlocfilehash: 5a90a12457597fa38c648fd44bf194d2322a26af
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861223"
---
# <a name="enable-controlled-folder-access"></a>Abilitare l’accesso controllato alle cartelle

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

[L'accesso controllato](controlled-folders.md) alle cartelle consente di proteggere i dati importanti da minacce e app dannose, ad esempio ransomware. L'accesso controllato alle cartelle è incluso Windows 10 e Windows Server 2019.

È possibile abilitare l'accesso controllato alle cartelle utilizzando uno dei metodi seguenti:

* [Sicurezza di Windows app](#windows-security-app)
* [Microsoft Endpoint Manager](#endpoint-manager)
* [Gestione di dispositivi mobili (MDM)](#mobile-device-management-mdm)
* [Microsoft Endpoint Configuration Manager](#microsoft-endpoint-configuration-manager)
* [Criteri di gruppo](#group-policy)
* [PowerShell](#powershell)

[La modalità](evaluate-controlled-folder-access.md) di controllo consente di testare il funzionamento della funzionalità (e di esaminare gli eventi) senza influire sul normale utilizzo del dispositivo.

Le impostazioni di Criteri di gruppo che disabilitano l'unione degli elenchi di amministratori locali avranno la precedenza su impostazioni di accesso controllato alle cartelle. Ignorano anche le cartelle protette e le app consentite impostate dall'amministratore locale tramite l'accesso controllato alle cartelle. Questi criteri includono:

* Antivirus Microsoft Defender comportamento **di unione dell'amministratore locale per gli elenchi**
* System Center Endpoint Protection consentire **agli utenti di aggiungere esclusioni e sostituzioni**

Per ulteriori informazioni sulla disabilitazione dell'unione di elenchi locali, vedere Impedire o consentire agli utenti di modificare localmente le impostazioni dei criteri [di Microsoft Defender AV.](/windows/security/threat-protection/microsoft-defender-antivirus/configure-local-policy-overrides-microsoft-defender-antivirus#configure-how-locally-and-globally-defined-threat-remediation-and-exclusions-lists-are-merged)

## <a name="windows-security-app"></a>Sicurezza di Windows app

1. Apri l Sicurezza di Windows app selezionando l'icona scudo nella barra delle applicazioni. Puoi anche cercare Defender nel menu **Start.**

2. Seleziona il **riquadro Protezione da &** virus (o l'icona scudo sulla barra dei menu sinistra) e quindi seleziona Protezione **ransomware.**

3. Impostare l'opzione **Accesso controllato alle cartelle** su **Attiva.**

> [!NOTE]
> Se l'accesso controllato alle cartelle è configurato con Criteri di gruppo, PowerShell o CSP MDM, lo stato cambierà nell'app Sicurezza di Windows dopo un riavvio del dispositivo.
> Se la funzionalità è impostata sulla **modalità** di controllo con uno di questi strumenti, l Sicurezza di Windows app mostrerà lo stato **come Disattivato.**
> Se si proteggono i dati del profilo utente, è consigliabile che il profilo utente si presenti nell'unità di Windows di installazione predefinita.

## <a name="endpoint-manager"></a>Endpoint Manager

1. Accedi al Endpoint Manager [e](https://endpoint.microsoft.com) apri **Endpoint Security.**

2. Vai a **Criteri di riduzione della superficie di**  >  **attacco.**

3. Seleziona **Piattaforma,** scegli Windows 10 **e versioni successive** e seleziona il profilo Regole di riduzione della superficie di **attacco**  >  **Crea.**

4.  Assegnare un nome al criterio e aggiungere una descrizione. Selezionare **Avanti**.

5.  Scorrere verso il basso verso il basso, selezionare l'elenco a discesa **Abilita protezione** cartelle e scegliere **Abilita**.

6.  Selezionare **Elenco di cartelle aggiuntive che devono essere protette** e aggiungere le cartelle che devono essere protette.

7.  Seleziona **Elenco di app che hanno accesso alle cartelle protette** e aggiungi le app che hanno accesso alle cartelle protette.

8.  Seleziona **Escludi file e percorsi dalle regole di** riduzione della superficie di attacco e aggiungi i file e i percorsi che devono essere esclusi dalle regole di riduzione della superficie di attacco.

9.  Selezionare il profilo **Assegnazioni,** assegnare a **Tutti gli & tutti i** dispositivi e selezionare **Salva.**

10.  Selezionare **Avanti** per salvare ogni pannello aperto e quindi **Crea**.

   > [!NOTE]
   > I caratteri jolly sono supportati per le applicazioni, ma non per le cartelle. Le sottocartelle non sono protette. Le app consentite continueranno a attivare eventi finché non vengono riavviate.

## <a name="mobile-device-management-mdm"></a>Gestione di dispositivi mobili (MDM)

Usa il provider di servizi di configurazione [./Vendor/MSFT/Policy/Config/ControlledFolderAccessProtectedFolders](/windows/client-management/mdm/policy-csp-defender#defender-controlledfolderaccessprotectedfolders) per consentire alle app di apportare modifiche alle cartelle protette.

## <a name="microsoft-endpoint-configuration-manager"></a>Microsoft Endpoint Configuration Manager

1. In Microsoft Endpoint Configuration Manager, andare a **Assets and Compliance**  >  **Endpoint Protection** Windows Defender  >  **Exploit Guard**.

2. Selezionare **Home**  >  **Create Exploit Guard Policy**.

3. Immettere un nome e una descrizione, selezionare **Accesso controllato alle cartelle** e selezionare **Avanti.**

4. Scegli se bloccare o controllare le modifiche, consentire altre app o aggiungere altre cartelle e selezionare **Avanti.**
   > [!NOTE]
   > Wilcard è supportato per le applicazioni, ma non per le cartelle. Le sottocartelle non sono protette. Le app consentite continueranno a attivare eventi finché non vengono riavviate.

5. Rivedere le impostazioni e selezionare **Avanti** per creare il criterio.

6. Dopo la creazione del criterio, **chiudere**.

## <a name="group-policy"></a>Criteri di gruppo

1. Nel dispositivo di gestione di Criteri di gruppo, aprire la [Console](https://technet.microsoft.com/library/cc731212.aspx)Gestione Criteri di gruppo, fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e scegliere **Modifica**.

2. Nell **'Editor Gestione Criteri di gruppo** passare a **Configurazione computer** e selezionare **Modelli amministrativi**.

3. Espandi l'albero per **Windows componenti > Antivirus Microsoft Defender > Windows Defender Exploit Guard > accesso controllato alle cartelle**.

4. Fare doppio clic **sull'impostazione Configura accesso controllato alle** cartelle e impostare l'opzione su **Abilitato.** Nella sezione opzioni è necessario specificare una delle opzioni seguenti:
    * **Abilita:** le app dannose e sospette non possono apportare modifiche ai file nelle cartelle protette. Una notifica verrà fornita nel registro Windows eventi.
    * **Disabilita (impostazione predefinita):** la funzionalità Accesso controllato alle cartelle non funzionerà. Tutte le app possono apportare modifiche ai file nelle cartelle protette.
    * **Modalità di controllo:** le modifiche saranno consentite se un'app dannosa o sospetta tenta di apportare una modifica a un file in una cartella protetta. Tuttavia, verrà registrato nel registro eventi di Windows in cui è possibile valutare l'impatto sull'organizzazione.
    * **Blocca solo la modifica del disco:** i tentativi da parte di app non attendibili di scrivere nei settori del disco verranno registrati Windows registro eventi. Questi registri sono disponibili in **Registri applicazioni** e servizi > Microsoft > Windows > Windows Defender > operativo > ID 1123.
    * **Controlla** solo la modifica del disco: solo i tentativi di scrittura nei settori del disco protetti verranno registrati nel registro eventi di Windows (in Registri applicazioni e servizi Microsoft Windows Windows Defender ID operativo  >    >    >    >    >  **1124).** I tentativi di modifica o eliminazione di file nelle cartelle protette non verranno registrati.

      ![Screenshot of the group policy option Enabled and Audit Mode selected in the drop-down](/microsoft-365/security/defender-endpoint/images/cfa-gp-enable)

> [!IMPORTANT]
> Per abilitare completamente l'accesso controllato alle cartelle, devi impostare l'opzione Criteri di gruppo su **Abilitato** e selezionare **Blocca** nel menu a discesa delle opzioni.

## <a name="powershell"></a>PowerShell

1. Digitare **powershell** nel menu Start, fare clic con il pulsante destro **del** mouse Windows PowerShell e scegliere Esegui **come amministratore.**

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
