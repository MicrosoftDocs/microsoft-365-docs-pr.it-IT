---
title: Proteggere le cartelle importanti dal ransomware dalla crittografia dei file con accesso controllato alle cartelle
description: I file nelle cartelle predefinite possono essere protetti da modifiche da app dannose. Impedire a ransomware di crittografare i file.
keywords: accesso controllato alle cartelle, windows 10, windows defender, ransomware, proteggere, file, cartelle
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
audience: ITPro
ms.date: 02/03/2021
ms.reviewer: v-maave
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: b937dd41f0296f2cf4102f41f8ab10bd55e1c35d
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2021
ms.locfileid: "51200282"
---
# <a name="protect-important-folders-with-controlled-folder-access"></a>Proteggere le cartelle importanti con l'accesso controllato alle cartelle

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="what-is-controlled-folder-access"></a>Che cos'è l'accesso controllato alle cartelle?

L'accesso controllato alle cartelle consente di proteggere i dati importanti da app e minacce dannose, ad esempio ransomware. L'accesso controllato alle cartelle protegge i dati controllando le app da un elenco di app note e attendibili. Supportato nei client Windows Server 2019 e Windows 10, l'accesso controllato alle cartelle può essere attivato tramite App di sicurezza di Windows, Microsoft Endpoint Configuration Manager o Intune (per i dispositivi gestiti). 

> [!NOTE]
> I motori di script non sono attendibili e non è possibile consentire loro l'accesso alle cartelle protette controllate.  Ad esempio, PowerShell non è considerato attendibile dall'accesso controllato alle cartelle, anche se si consente con [indicatori di file e certificati.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/indicator-certificates) 

L'accesso controllato alle cartelle funziona meglio con [Microsoft Defender for Endpoint,](microsoft-defender-endpoint.md)che fornisce report dettagliati sugli eventi di accesso controllato alle cartelle e sui blocchi nell'ambito dei soliti scenari di analisi [degli avvisi.](investigate-alerts.md)

> [!TIP]
> I blocchi di accesso controllato alle cartelle non generano avvisi nella [coda avvisi.](alerts-queue.md) Tuttavia, puoi visualizzare le informazioni sui blocchi di accesso controllato alle cartelle nella visualizzazione sequenza temporale del [dispositivo,](investigate-machines.md)usando la ricerca avanzata [o](advanced-hunting-overview.md)con regole di [rilevamento personalizzate.](custom-detection-rules.md)

## <a name="how-does-controlled-folder-access-work"></a>Come funziona l'accesso controllato alle cartelle?

L'accesso controllato alle cartelle funziona consentendo solo alle app attendibili di accedere alle cartelle protette. Le cartelle protette vengono specificate quando viene configurato l'accesso controllato alle cartelle. In genere, le cartelle di uso comune, ad esempio quelle utilizzate per documenti, immagini, download e così via, sono incluse nell'elenco delle cartelle controllate. 

L'accesso controllato alle cartelle funziona con un elenco di app attendibili. Le app incluse nell'elenco del software attendibile funzionano come previsto. Alle app non incluse nell'elenco non viene impedito di apportare modifiche ai file all'interno delle cartelle protette. 

Le app vengono aggiunte all'elenco in base alla loro diffusione e reputazione. Le app altamente diffuse in tutta l'organizzazione e che non hanno mai visualizzato alcun comportamento ritenuto dannoso sono considerate attendibili. Tali app vengono aggiunte automaticamente all'elenco.

Le app possono anche essere aggiunte manualmente all'elenco attendibile tramite Configuration Manager o Intune. Altre azioni, ad esempio [l'aggiunta di un indicatore di file](respond-file-alerts.md#add-indicator-to-block-or-allow-a-file) per un'app, possono essere eseguite dalla console del Centro sicurezza.

## <a name="why-controlled-folder-access-is-important"></a>Perché l'accesso controllato alle cartelle è importante

L'accesso controllato alle cartelle è particolarmente utile per proteggere i documenti e le informazioni da [ransomware.](https://www.microsoft.com/wdsi/threats/ransomware) In un attacco ransomware, i file possono essere crittografati e tenuti in ostaggio. Con l'accesso controllato alle cartelle, viene visualizzata una notifica nel computer in cui un'app ha tentato di apportare modifiche a un file in una cartella protetta. Puoi personalizzare [la notifica con i](customize-attack-surface-reduction.md#customize-the-notification) dettagli dell'azienda e le informazioni di contatto. È inoltre possibile abilitare le regole singolarmente per personalizzare le tecniche monitorate dalla funzionalità.

Le [cartelle protette](#review-controlled-folder-access-events-in-windows-event-viewer) includono cartelle di sistema comuni (inclusi i settori di avvio) ed è possibile [aggiungere altre cartelle.](customize-controlled-folders.md#protect-additional-folders) Puoi anche consentire [alle app](customize-controlled-folders.md#allow-specific-apps-to-make-changes-to-controlled-folders) di concedere loro l'accesso alle cartelle protette.

È possibile utilizzare [la modalità di controllo](audit-windows-defender.md) per valutare l'impatto dell'accesso controllato alle cartelle nell'organizzazione se fosse abilitato. È inoltre possibile visitare il sito Web Windows Defender test di base [all'indirizzo demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) per verificare che la funzionalità funzioni e vedere come funziona.

L'accesso controllato alle cartelle è supportato nelle seguenti versioni di Windows:
- [Windows 10, versione 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) e successive
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)

## <a name="windows-system-folders-are-protected-by-default"></a>Le cartelle di sistema di Windows sono protette per impostazione predefinita

Le cartelle di sistema di Windows sono protette per impostazione predefinita, insieme a diverse altre cartelle: 

- `c:\Users\<username>\Documents`
- `c:\Users\Public\Documents`
- `c:\Users\<username>\Pictures`
- `c:\Users\Public\Pictures`
- `c:\Users\Public\Videos`
- `c:\Users\<username>\Videos`
- `c:\Users\<username>\Music`
- `c:\Users\Public\Music`
- `c:\Users\<username>\Favorites`

> [!NOTE]
> È possibile configurare cartelle aggiuntive come protette, ma non è possibile rimuovere le cartelle di sistema di Windows protette per impostazione predefinita.

## <a name="requirements-for-controlled-folder-access"></a>Requisiti per l'accesso controllato alle cartelle

L'accesso controllato alle cartelle richiede [l'abilitazione](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus)della protezione in tempo reale di Microsoft Defender Antivirus.

## <a name="review-controlled-folder-access-events-in-the-microsoft-defender-security-center"></a>Esaminare gli eventi di accesso controllato alle cartelle in Microsoft Defender Security Center

Defender for Endpoint fornisce report dettagliati su eventi e blocchi nell'ambito degli scenari di [analisi degli avvisi.](investigate-alerts.md)

Puoi eseguire una query su Microsoft Defender per i dati dell'endpoint usando [Ricerca avanzata.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/advanced-hunting-windows-defender-advanced-threat-protection) Se usi la modalità [di](audit-windows-defender.md)controllo, puoi usare la ricerca avanzata per vedere in che modo le impostazioni di accesso controllato alle cartelle influirebbero sull'ambiente se fossero abilitate. [](advanced-hunting-overview.md)

Query di esempio:

```PowerShell
DeviceEvents
| where ActionType in ('ControlledFolderAccessViolationAudited','ControlledFolderAccessViolationBlocked')
```

## <a name="review-controlled-folder-access-events-in-windows-event-viewer"></a>Esaminare gli eventi di accesso controllato alle cartelle nel Visualizzatore eventi di Windows

Puoi esaminare il registro eventi di Windows per visualizzare gli eventi che vengono creati quando un'app controlla o blocca l'accesso controllato alle cartelle:

1. Scarica il [pacchetto di valutazione](https://aka.ms/mp7z2w) ed estrai il file *cfa-events.xml* in un percorso facilmente accessibile nel dispositivo.
2. Digita **Visualizzatore** eventi nel menu Start per aprire il Visualizzatore eventi di Windows.
3. Nel riquadro sinistro, in **Azioni,** selezionare **Importa visualizzazione personalizzata...**.
4. Passare al punto in cui è stato *cfa-events.xml* e selezionarlo. In alternativa, [copiare il codice XML direttamente](event-views.md).
5. Selezionare **OK**.

La tabella seguente mostra gli eventi correlati all'accesso controllato alle cartelle:

|ID evento | Descrizione |
|:---|:---|
|5007 | Evento quando vengono modificate le impostazioni |
|1124 | Evento di accesso controllato alle cartelle controllato | 
|1123 | Evento di accesso controllato alla cartella bloccato |

## <a name="view-or-change-the-list-of-protected-folders"></a>Visualizzare o modificare l'elenco delle cartelle protette

Puoi usare l'app Sicurezza di Windows per visualizzare l'elenco delle cartelle protette dall'accesso controllato alle cartelle. 

1. Nel dispositivo Windows 10 apri l'app Sicurezza di Windows.
2. Selezionare **Protezione da & virus**.
3. In **Protezione ransomware** seleziona Gestisci protezione **ransomware.**
4. Se l'accesso controllato alle cartelle è disattivato, è necessario attivarlo. Selezionare **cartelle protette**.
5. Eseguire una delle operazioni seguenti:
   - Per aggiungere una cartella, selezionare **+ Aggiungi una cartella protetta.**
   - Per rimuovere una cartella, selezionarla e quindi **selezionare Rimuovi.** 

> [!NOTE]
> [Le cartelle di sistema](#windows-system-folders-are-protected-by-default) di Windows sono protette per impostazione predefinita e non è possibile rimuoverle dall'elenco.

## <a name="see-also"></a>Vedere anche

- [Valutare l'accesso controllato alle cartelle](evaluate-controlled-folder-access.md)
- [Personalizzare l'accesso controllato alle cartelle](customize-controlled-folders.md)
- [Proteggere più cartelle](customize-controlled-folders.md#protect-additional-folders)
