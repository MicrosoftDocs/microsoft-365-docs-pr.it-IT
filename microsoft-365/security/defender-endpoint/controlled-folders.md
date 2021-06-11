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
ms.date: 06/10/2021
ms.reviewer: v-maave
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: c60620d2a589c8473764b810d1fcb0e24f674451
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/11/2021
ms.locfileid: "52904057"
---
# <a name="protect-important-folders-with-controlled-folder-access"></a>Proteggere le cartelle importanti con l'accesso controllato alle cartelle

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="what-is-controlled-folder-access"></a>Che cos'è l'accesso controllato alle cartelle?

L'accesso controllato alle cartelle consente di proteggere i dati importanti da app e minacce dannose, ad esempio ransomware. L'accesso controllato alle cartelle protegge i dati controllando le app da un elenco di app note e attendibili. Supportato nei client Windows Server 2019 e Windows 10, l'accesso controllato alle cartelle può essere attivato tramite l'app Sicurezza di Windows, Microsoft Endpoint Configuration Manager o Intune (per i dispositivi gestiti). 

> [!NOTE]
> I motori di script non sono attendibili e non è possibile consentire loro l'accesso alle cartelle protette controllate.  Ad esempio, PowerShell non è considerato attendibile dall'accesso controllato alle cartelle, anche se si consente con [indicatori di file e certificati.](/microsoft-365/security/defender-endpoint/indicator-certificates) 

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
- [Windows 10 versione 1709](/windows/whats-new/whats-new-windows-10-version-1709) e successive
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)

## <a name="windows-system-folders-are-protected-by-default"></a>Windows cartelle di sistema sono protette per impostazione predefinita

Windows cartelle di sistema sono protette per impostazione predefinita, insieme a diverse altre cartelle: 

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
> È possibile configurare cartelle aggiuntive come protette, ma non è possibile rimuovere Windows di sistema protette per impostazione predefinita.

## <a name="requirements-for-controlled-folder-access"></a>Requisiti per l'accesso controllato alle cartelle

L'accesso controllato alle cartelle [richiede Antivirus Microsoft Defender protezione in tempo reale.](/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus)

## <a name="review-controlled-folder-access-events-in-the-microsoft-365-defender-portal"></a>Esaminare gli eventi di accesso controllato alle cartelle nel portale Microsoft 365 Defender

Defender for Endpoint fornisce report dettagliati su [](investigate-alerts.md) eventi e blocchi nell'ambito degli scenari di analisi degli avvisi nel portale Microsoft 365 Defender. (Vedi [Microsoft Defender per Endpoint in Microsoft 365 Defender](../defender/microsoft-365-security-center-mde.md).)

Puoi eseguire una query su Microsoft Defender per i dati dell'endpoint usando [Ricerca avanzata.](/microsoft-365/security/defender-endpoint/advanced-hunting-windows-defender-advanced-threat-protection) Se usi la modalità [di](audit-windows-defender.md)controllo, puoi usare la ricerca avanzata per vedere in che modo le impostazioni di accesso controllato alle cartelle influirebbero sull'ambiente se fossero abilitate. [](advanced-hunting-overview.md)

Query di esempio:

```PowerShell
DeviceEvents
| where ActionType in ('ControlledFolderAccessViolationAudited','ControlledFolderAccessViolationBlocked')
```

## <a name="review-controlled-folder-access-events-in-windows-event-viewer"></a>Esaminare gli eventi di accesso controllato alle cartelle nel Visualizzatore Windows eventi

Puoi esaminare il registro Windows eventi per visualizzare gli eventi che vengono creati quando un'app controlla o blocca l'accesso controllato alle cartelle:You can review the Windows event log to see events that are created when controlled folder access blocks (or audits) an app:

1. Scarica il [pacchetto di valutazione](https://aka.ms/mp7z2w) ed estrai il file *cfa-events.xml* in un percorso facilmente accessibile nel dispositivo.
2. Digita **Visualizzatore eventi** nel menu Start per aprire il Visualizzatore Windows eventi.
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

1. Nel dispositivo Windows 10, apri l'app Sicurezza di Windows app.
2. Selezionare **Protezione da virus e minacce**.
3. In **Protezione ransomware** seleziona Gestisci protezione **ransomware.**
4. Se l'accesso controllato alle cartelle è disattivato, è necessario attivarlo. Selezionare **cartelle protette**.
5. Esegui uno dei seguenti passaggi:
   - Per aggiungere una cartella, selezionare **+ Aggiungi una cartella protetta.**
   - Per rimuovere una cartella, selezionarla e quindi **selezionare Rimuovi.** 

> [!NOTE]
> [Windows cartelle di](#windows-system-folders-are-protected-by-default) sistema sono protette per impostazione predefinita e non è possibile rimuoverle dall'elenco.


