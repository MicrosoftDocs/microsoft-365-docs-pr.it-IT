---
title: Valutare l’accesso controllato alle cartelle
description: Scopri in che modo l'accesso controllato alle cartelle consente di proteggere i file dalle modifiche da parte di app dannose.
keywords: Protezione degli exploit, Windows 10, windows defender, ransomware, proteggere, valutare, testare, demo, provare
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: dansimp
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 15ea4696052a6c987314e3c7b0dd282a49ed4df8
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842915"
---
# <a name="evaluate-controlled-folder-access"></a>Valutare l’accesso controllato alle cartelle

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)


[L'accesso controllato](controlled-folders.md) alle cartelle è una funzionalità che consente di proteggere i documenti e i file da modifiche da app sospette o dannose. L'accesso controllato alle cartelle è supportato Windows Server 2019 e Windows 10 client.

È particolarmente utile per proteggere da [ransomware](https://www.microsoft.com/wdsi/threats/ransomware) che tenta di crittografare i file e tenerli in ostaggio.

Questo articolo consente di valutare l'accesso controllato alle cartelle. Viene illustrato come abilitare la modalità di controllo in modo da poter testare la funzionalità direttamente nell'organizzazione.

> [!TIP]
> Puoi anche visitare il sito Web dello scenario demo di Microsoft Defender per Endpoint [all'indirizzo demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) per verificare che la funzionalità funzioni e vedere come funziona.

## <a name="use-audit-mode-to-measure-impact"></a>Usare la modalità di controllo per misurare l'impatto

Abilita l'accesso controllato alle cartelle in  modalità di controllo per visualizzare un record di ciò che sarebbe successo se fosse stata completamente abilitata. Testare il funzionamento della funzionalità nell'organizzazione per assicurarsi che non influisca sulle app line-of-business. Puoi anche avere un'idea del numero di tentativi di modifica dei file sospetti in genere eseguiti in un determinato periodo di tempo.

Per abilitare la modalità di controllo, utilizzare il cmdlet PowerShell seguente:

```PowerShell
Set-MpPreference -EnableControlledFolderAccess AuditMode
```

> [!TIP]
> Se si desidera controllare completamente il funzionamento dell'accesso controllato alle cartelle nell'organizzazione, è necessario utilizzare uno strumento di gestione per distribuire questa impostazione nei dispositivi della rete.
Puoi anche usare Criteri di gruppo, Intune, gestione dei dispositivi mobili (MDM) o Microsoft Endpoint Manager per configurare e distribuire l'impostazione, come descritto nell'argomento principale accesso controllato [alle cartelle.](controlled-folders.md)

## <a name="review-controlled-folder-access-events-in-windows-event-viewer"></a>Esaminare gli eventi di accesso controllato alle cartelle nel Visualizzatore Windows eventi

I seguenti eventi di accesso controllato alle cartelle vengono visualizzati Windows visualizzatore eventi in Microsoft/Windows/Windows Defender/Operational.

ID evento | Descrizione
-|-
 5007 | Evento quando vengono modificate le impostazioni
 1124 | Evento di accesso controllato alle cartelle controllato
 1123 | Evento di accesso controllato alla cartella bloccato

> [!TIP]
> È possibile configurare una sottoscrizione [Windows inoltro eventi per](/windows/win32/wec/setting-up-a-source-initiated-subscription) raccogliere i registri in modo centralizzato. 

## <a name="customize-protected-folders-and-apps"></a>Personalizzare le app e le cartelle protette

Durante la valutazione, potresti voler aggiungere all'elenco delle cartelle protette o consentire a determinate app di modificare i file.

Vedi [Proteggere le cartelle importanti con](controlled-folders.md) accesso controllato alle cartelle per configurare la funzionalità con strumenti di gestione, tra cui Criteri di gruppo, PowerShell e provider di servizi di configurazione MDM .

## <a name="see-also"></a>Vedere anche

* [Proteggere le cartelle importanti con l'accesso controllato alle cartelle](controlled-folders.md)
* [Valutare Microsoft Defender per endpoint.](evaluate-mde.md)
* [Usare la modalità di controllo](audit-windows-defender.md)
