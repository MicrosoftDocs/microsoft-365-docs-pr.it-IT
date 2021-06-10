---
title: Creare un processo di implementazione graduale personalizzato per gli aggiornamenti di Microsoft Defender
description: Informazioni su come usare gli strumenti supportati per creare un processo di implementazione graduale personalizzato per gli aggiornamenti
keywords: strumenti di aggiornamento, gpo, intune, mdm, microsoft endpoint manager, criteri, powershell
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: ec39a47a68f98f3fad63c10e633d54fd5a091db9
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2021
ms.locfileid: "52862012"
---
# <a name="create-a-custom-gradual-rollout-process-for-microsoft-defender-updates"></a>Creare un processo di implementazione graduale personalizzato per gli aggiornamenti di Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**

- [Microsoft Defender per endpoint](/microsoft-365/security/defender-endpoint/)

> [!NOTE]
> Questa funzionalità richiede Antivirus Microsoft Defender versione 4.18.2105.4 o successiva.

Per creare un processo di implementazione graduale personalizzato per gli aggiornamenti di Defender, puoi usare Criteri di gruppo, Microsoft Endpoint Manager e PowerShell.

Nella tabella seguente sono elencate le impostazioni di Criteri di gruppo disponibili per la configurazione dei canali di aggiornamento:

| Titolo dell'impostazione  | Descrizione  | Posizione  |
|-|-|-|
| Selezionare il canale graduale di implementazione dell'aggiornamento mensile della piattaforma Microsoft Defender  | Abilita questo criterio per specificare quando i dispositivi ricevono gli aggiornamenti della piattaforma Microsoft Defender durante l'implementazione graduale mensile. Canale beta: i dispositivi impostati su questo canale saranno i primi a ricevere nuovi aggiornamenti. Seleziona Canale beta per partecipare all'identificazione e alla segnalazione di problemi a Microsoft. I dispositivi nel Windows Insider Sono sottoscritti a questo canale per impostazione predefinita. Per l'uso solo in ambienti di test (manuali) e in un numero limitato di dispositivi.  <br><br>  Canale corrente (anteprima): i dispositivi impostati su questo canale riceveranno gli aggiornamenti prima durante il ciclo di rilascio graduale mensile. Consigliato per ambienti di pre-produzione/convalida.  <br><br>  Canale corrente (a fasi): i dispositivi verranno offerti aggiornamenti dopo il ciclo di rilascio graduale mensile. Si consiglia di applicarsi a una piccola parte rappresentativa della popolazione di produzione (~10%).  <br><br>  Canale corrente (Generale): ai dispositivi verranno offerti aggiornamenti solo al termine del ciclo di rilascio graduale. Consigliato per l'applicazione a un ampio set di dispositivi nella popolazione di produzione (~10-100%).  <br><br>   Se disabiliti o non configurerai questo criterio, il dispositivo rimarrà aggiornato automaticamente durante il ciclo di rilascio graduale. Adatto per la maggior parte dei dispositivi.  | Windows Components\Antivirus Microsoft Defender  |
| Selezionare il canale graduale di implementazione degli aggiornamenti mensili del motore di Microsoft Defender  | Abilita questo criterio per specificare quando i dispositivi ricevono gli aggiornamenti del motore di Microsoft Defender durante l'implementazione graduale mensile.  <br><br>  Canale beta: i dispositivi impostati su questo canale saranno i primi a ricevere nuovi aggiornamenti. Seleziona Canale beta per partecipare all'identificazione e alla segnalazione di problemi a Microsoft. I dispositivi nel Windows Insider Sono sottoscritti a questo canale per impostazione predefinita. Per l'uso solo in ambienti di test (manuali) e in un numero limitato di dispositivi.  <br><br>  Canale corrente (anteprima): i dispositivi impostati su questo canale riceveranno gli aggiornamenti prima durante il ciclo di rilascio graduale mensile. Consigliato per ambienti di pre-produzione/convalida.  <br><br>  Canale corrente (a fasi): i dispositivi verranno offerti aggiornamenti dopo il ciclo di rilascio graduale mensile. Si consiglia di applicarsi a una piccola parte rappresentativa della popolazione di produzione (~10%).  <br><br>  Canale corrente (Generale): ai dispositivi verranno offerti aggiornamenti solo al termine del ciclo di rilascio graduale. Consigliato per l'applicazione a un ampio set di dispositivi nella popolazione di produzione (~10-100%).  <br><br>  Se disabiliti o non configurerai questo criterio, il dispositivo rimarrà aggiornato automaticamente durante il ciclo di rilascio graduale. Adatto per la maggior parte dei dispositivi.  | Windows Components\Antivirus Microsoft Defender  |
| Selezionare il canale di implementazione graduale degli aggiornamenti delle definizioni giornaliere di Microsoft Defender  | Abilita questo criterio per specificare quando i dispositivi ricevono gli aggiornamenti delle definizioni di Microsoft Defender durante l'implementazione graduale giornaliera. <br><br> Canale corrente (a fasi): i dispositivi saranno disponibili aggiornamenti dopo il ciclo di rilascio. Si consiglia di applicarsi a una piccola parte rappresentativa della popolazione di produzione (~10%). <br><br>   Canale corrente (Generale): ai dispositivi verranno offerti aggiornamenti solo al termine del ciclo di rilascio graduale. Consigliato per l'applicazione a un ampio set di dispositivi nella popolazione di produzione (~10-100%). <br><br>   Se disabiliti o non configurerai questo criterio, il dispositivo rimarrà aggiornato automaticamente durante il ciclo di rilascio giornaliero. Adatto per la maggior parte dei dispositivi.  | Windows Components\Antivirus Microsoft Defender  |
| Disabilitare l'implementazione graduale degli aggiornamenti di Microsoft Defender  | Abilita questo criterio per disabilitare l'implementazione graduale degli aggiornamenti di Defender. <br><br> Canale corrente (generale): i dispositivi impostati su questo canale verranno offerti gli aggiornamenti per ultimi durante il ciclo di rilascio graduale. Ideale per i computer datacenter che ricevono solo aggiornamenti limitati. <br><br> Nota: questa impostazione si applica sia agli aggiornamenti mensili che giornalieri di Defender e sostituisce qualsiasi selezione di canale configurata in precedenza per gli aggiornamenti della piattaforma e del motore. <br><br> Se disabiliti o non configurerai questo criterio, il dispositivo rimarrà nel Canale corrente (predefinito), a meno che non venga specificato diversamente in canali specifici per gli aggiornamenti della piattaforma e del motore. Rimanere aggiornati automaticamente durante il ciclo di rilascio graduale. Adatto per la maggior parte dei dispositivi.  | Windows Components\Antivirus Microsoft Defender  |

## <a name="group-policy"></a>Criteri di gruppo

> [!NOTE]
> Verrà pubblicato un modello ADMX di Defender aggiornato insieme alla versione 21H2 di Windows 10. Una versione non localizzata è disponibile per il download all'indirizzo https://github.com/microsoft/defender-updatecontrols .

Puoi usare [Criteri di gruppo](/windows/win32/srvnodes/group-policy?redirectedfrom=MSDN)per configurare e gestire Antivirus Microsoft Defender nei tuoi   endpoint.

In generale, è possibile utilizzare la procedura seguente per configurare o modificare Antivirus Microsoft Defender criteri di gruppo:

1. Nel computer di gestione di Criteri di gruppo, aprire la  **Console** Gestione Criteri di gruppo, fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo **che** si desidera configurare e scegliere  **Modifica**.

2. Utilizzando l'Editor Gestione Criteri di gruppo passare a **Configurazione computer**.

3. Fare clic **su Modelli amministrativi**.

4. Espandere l'albero per **Windows componenti > Antivirus Microsoft Defender**.

5. Espandere la sezione (denominata **** Percorso nella tabella di questo argomento) contenente l'impostazione che si desidera configurare, fare doppio clic sull'impostazione per aprirla e apportare modifiche   alla configurazione.

6. [Distribuire l'oggetto Criteri di gruppo aggiornato come si fa normalmente.](https://msdn.microsoft.com/library/ee663280(v=vs.85).aspx)

## <a name="intune"></a>Intune

Segui le istruzioni nel collegamento seguente per creare un criterio personalizzato in Intune:

[Aggiungere impostazioni personalizzate per Windows 10 dispositivi in Microsoft Intune - Documentazione microsoft di Azure \|](/mem/intune/configuration/custom-settings-windows-10)

## <a name="powershell"></a>PowerShell

Utilizzare il `Set-MpPreference` cmdlet per configurare l'implementazione degli aggiornamenti graduali.

Utilizzare i parametri seguenti:

```powershell
Set-MpPreference
-PlatformUpdatesChannel Beta|Preview|Staged|Broad|NotConfigured
-EngineUpdatesChannel Beta|Preview|Staged|Broad|NotConfigured
-DisableGradualRelease True|False
-SignaturesUpdatesChannel Staged|Broad|NotConfigured
```

Esempio:

Usa `Set-MpPreference -PlatformUpdatesChannel Beta` per configurare gli aggiornamenti della piattaforma per l'arrivo dal Canale beta.

Per altre informazioni sui parametri e su come configurarli, vedi [Set-MpPreference (Defender) | Documenti Microsoft](/powershell/module/defender/set-mppreference?view=windowsserver2019-ps).
