---
title: Visualizzare eventi per la riduzione della superficie di attacco
description: Importa visualizzazioni personalizzate per visualizzare gli eventi di riduzione della superficie di attacco.
keywords: visualizzazione eventi, exploit guard, controllo, revisione, eventi
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: f8de3d8b2d7c07f8d783ecbe85b7e4a9c612aae5
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985463"
---
# <a name="view-attack-surface-reduction-events"></a>Visualizzare eventi per la riduzione della superficie di attacco

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**

- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)

Esaminare gli eventi di riduzione della superficie di attacco nel Visualizzatore eventi per monitorare le regole o le impostazioni in uso. Puoi anche determinare se le impostazioni sono troppo "rumorose" o influiscono sul flusso di lavoro quotidiano.

La revisione degli eventi è utile quando si valutano le funzionalità. Puoi abilitare la modalità di controllo per le funzionalità o le impostazioni e quindi esaminare cosa sarebbe successo se fossero state abilitate completamente.

In questo articolo vengono elencati tutti gli eventi, la funzionalità o l'impostazione associata e viene descritto come creare visualizzazioni personalizzate da filtrare in base a eventi specifici.

Ottieni report dettagliati su eventi, blocchi e avvisi come parte di Sicurezza di Windows se hai una sottoscrizione E5 e usi [Microsoft Defender for Endpoint.](microsoft-defender-endpoint.md)

## <a name="use-custom-views-to-review-attack-surface-reduction-capabilities"></a>Usare visualizzazioni personalizzate per esaminare le funzionalità di riduzione della superficie di attacco

Crea visualizzazioni personalizzate nel Visualizzatore Windows eventi per visualizzare solo gli eventi per funzionalità e impostazioni specifiche. Il modo più semplice è importare una visualizzazione personalizzata come file XML. È possibile copiare il codice XML direttamente da questa pagina.

Puoi anche passare manualmente all'area dell'evento corrispondente alla funzionalità.

### <a name="import-an-existing-xml-custom-view"></a>Importare una visualizzazione personalizzata XML esistente

1. Creare un file .txt vuoto e copiare il codice XML per la visualizzazione personalizzata che si desidera utilizzare nel file .txt file. Eseguire questa operazione per ognuna delle visualizzazioni personalizzate che si desidera utilizzare. Rinominare i file come segue (assicurarsi di modificare il tipo da .txt a .xml):
    - Visualizzazione personalizzata degli eventi di accesso controllato alle *cartelle:cfa-events.xml*
    - Visualizzazione personalizzata degli eventi di protezione degli *exploit:ep-events.xml*
    - Visualizzazione personalizzata degli eventi di riduzione della superficie di *attacco:asr-events.xml*
    - Visualizzazione personalizzata eventi di *rete/protezione:np-events.xml*

2. Digitare **Visualizzatore eventi** nel menu Start e aprire **Visualizzatore eventi.**

3. Seleziona **Azione**  >  **Importa visualizzazione personalizzata...**

  > [!div class="mx-imgBorder"]
  > ![Animazione evidenziazione Importa visualizzazione personalizzata a sinistra della finestra del visualizzatore pari](images/events-import.gif)

4. Passare al percorso in cui è stato estratto il file XML per la visualizzazione personalizzata desiderata e selezionarlo.

5. Seleziona **Apri**.

6. Verrà creata una visualizzazione personalizzata che filtra solo gli eventi correlati a tale funzionalità.

### <a name="copy-the-xml-directly"></a>Copiare direttamente il codice XML

1. Digitare **visualizzatore eventi** nel menu Start e aprire il Visualizzatore Windows **eventi**.

2. Nel riquadro sinistro, in **Azioni,** selezionare **Crea visualizzazione personalizzata...**

  > [!div class="mx-imgBorder"]
  > ![Animazione che evidenzia l'opzione crea visualizzazione personalizzata nella finestra visualizzatore eventi](images/events-create.gif)

3. Passare alla scheda XML e selezionare **Modifica query manualmente.** Verrà visualizzato un avviso che indica che non è possibile modificare la query utilizzando la scheda **Filtro** se si utilizza l'opzione XML. Selezionare **Sì**.

4. Incollare il codice XML per la funzionalità da cui si desidera filtrare gli eventi nella sezione XML.

5. Selezionare **OK**. Specificare un nome per il filtro. In questo modo viene creata una visualizzazione personalizzata che filtra solo gli eventi correlati a tale funzionalità.

### <a name="xml-for-attack-surface-reduction-rule-events"></a>XML per gli eventi delle regole di riduzione della superficie di attacco

```xml
<QueryList>
  <Query Id="0" Path="Microsoft-Windows-Windows Defender/Operational">
   <Select Path="Microsoft-Windows-Windows Defender/Operational">*[System[(EventID=1121 or EventID=1122 or EventID=5007)]]</Select>
   <Select Path="Microsoft-Windows-Windows Defender/WHC">*[System[(EventID=1121 or EventID=1122 or EventID=5007)]]</Select>
  </Query>
</QueryList>
```

### <a name="xml-for-controlled-folder-access-events"></a>XML per eventi di accesso controllato alle cartelle

```xml
<QueryList>
  <Query Id="0" Path="Microsoft-Windows-Windows Defender/Operational">
   <Select Path="Microsoft-Windows-Windows Defender/Operational">*[System[(EventID=1123 or EventID=1124 or EventID=5007)]]</Select>
   <Select Path="Microsoft-Windows-Windows Defender/WHC">*[System[(EventID=1123 or EventID=1124 or EventID=5007)]]</Select>
  </Query>
</QueryList>
```

### <a name="xml-for-exploit-protection-events"></a>XML per gli eventi di protezione degli exploit

```xml
<QueryList>
  <Query Id="0" Path="Microsoft-Windows-Security-Mitigations/KernelMode">
   <Select Path="Microsoft-Windows-Security-Mitigations/KernelMode">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/Concurrency">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/Contention">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/Messages">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/Operational">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/Power">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/Render">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/Tracing">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Win32k/UIPI">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="System">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
   <Select Path="Microsoft-Windows-Security-Mitigations/UserMode">*[System[Provider[@Name='Microsoft-Windows-Security-Mitigations' or @Name='Microsoft-Windows-WER-Diag' or @Name='Microsoft-Windows-Win32k' or @Name='Win32k'] and ( (EventID &gt;= 1 and EventID &lt;= 24)  or EventID=5 or EventID=260)]]</Select>
  </Query>
</QueryList>
```

### <a name="xml-for-network-protection-events"></a>XML per eventi di protezione di rete

```xml
<QueryList>
 <Query Id="0" Path="Microsoft-Windows-Windows Defender/Operational">
  <Select Path="Microsoft-Windows-Windows Defender/Operational">*[System[(EventID=1125 or EventID=1126 or EventID=5007)]]</Select>
  <Select Path="Microsoft-Windows-Windows Defender/WHC">*[System[(EventID=1125 or EventID=1126 or EventID=5007)]]</Select>
 </Query>
</QueryList>
```

## <a name="list-of-attack-surface-reduction-events"></a>Elenco degli eventi di riduzione della superficie di attacco

Tutti gli eventi di riduzione della superficie di attacco si trovano in Registri applicazioni e servizi **> Microsoft > Windows** e quindi nella cartella o nel provider elencati nella tabella seguente.

Puoi accedere a questi eventi nel Visualizzatore Windows eventi:

1. Apri il menu **Start** e digita **Visualizzatore eventi** e quindi seleziona il **risultato visualizzatore** eventi.
2. Espandere **Registri applicazioni e servizi > Microsoft > Windows** quindi passare alla cartella elencata in **Provider/origine** nella tabella seguente.
3. Fai doppio clic sull'elemento secondario per visualizzare gli eventi. Scorrere gli eventi per trovare quello che si sta cercando.

   ![Animazione che mostra l'utilizzo del Visualizzatore eventi](images/event-viewer.gif)

Funzionalità | Provider/origine | ID evento | Descrizione
:-|:-|:-:|:-
Protezione dagli exploit | Security-Mitigations (modalità kernel/modalità utente) | 1 | Controllo ACG
Protezione dagli exploit | Security-Mitigations (modalità kernel/modalità utente) | 2 | Applicazione ACG
Protezione dagli exploit | Security-Mitigations (modalità kernel/modalità utente) | 3 | Non consentire il controllo dei processi figlio
Protezione dagli exploit | Security-Mitigations (modalità kernel/modalità utente) | 4  | Non consentire il blocco dei processi figlio
Protezione dagli exploit | Security-Mitigations (modalità kernel/modalità utente) | 5  | Bloccare il controllo delle immagini con integrità bassa
Protezione dagli exploit | Security-Mitigations (modalità kernel/modalità utente) | 6  | Blocca il blocco di immagini con integrità bassa
Protezione dagli exploit | Security-Mitigations (modalità kernel/modalità utente) | 7  | Bloccare il controllo delle immagini remote
Protezione dagli exploit | Security-Mitigations (modalità kernel/modalità utente) | 8  | Bloccare il blocco di immagini remote
Protezione dagli exploit | Security-Mitigations (modalità kernel/modalità utente) | 9  | Disabilitare il controllo delle chiamate di sistema win32k
Protezione dagli exploit | Security-Mitigations (modalità kernel/modalità utente) | 10   | Disabilitare il blocco delle chiamate di sistema win32k
Protezione dagli exploit | Security-Mitigations (modalità kernel/modalità utente) | 11 | Controllo di Protezione dell'integrità del codice
Protezione dagli exploit | Security-Mitigations (modalità kernel/modalità utente) | 12  | Blocco di protezione dell'integrità del codice
Protezione dagli exploit | Security-Mitigations (modalità kernel/modalità utente) | 13 | Controllo EAF
Protezione dagli exploit | Security-Mitigations (modalità kernel/modalità utente) | 14  | Imposizione EAF
Protezione dagli exploit | Security-Mitigations (modalità kernel/modalità utente) | 15 | Controllo EAF+
Protezione dagli exploit | Security-Mitigations (modalità kernel/modalità utente) | 16  | Imposizione EAF+
Protezione dagli exploit | Security-Mitigations (modalità kernel/modalità utente) | 17  | Controllo IAF
Protezione dagli exploit | Security-Mitigations (modalità kernel/modalità utente) | 18  | Imposizione IAF
Protezione dagli exploit | Security-Mitigations (modalità kernel/modalità utente) | 19 | Controllo ROP StackPivot
Protezione dagli exploit | Security-Mitigations (modalità kernel/modalità utente) | 20 | Applicazione ROP StackPivot
Protezione dagli exploit | Security-Mitigations (modalità kernel/modalità utente) |  21 | Controllo ROP CallerCheck
Protezione dagli exploit | Security-Mitigations (modalità kernel/modalità utente) | 22 | ROP CallerCheck enforce
Protezione dagli exploit | Security-Mitigations (modalità kernel/modalità utente) | 23 | Controllo ROP SimExec
Protezione dagli exploit | Security-Mitigations (modalità kernel/modalità utente) | 24 | ROP SimExec enforce
Protezione dagli exploit | WER-Diagnostics | 5  | Blocco CFG
Protezione dagli exploit | Win32K (operativo) | 260 | Tipo di carattere non attendibile
Protezione di rete | Windows Defender (operativo) | 5007 | Evento quando vengono modificate le impostazioni
Protezione di rete | Windows Defender (operativo) | 1125 | Evento quando protezione di rete viene attivata in modalità di controllo
Protezione di rete | Windows Defender (operativo) | 1126 | Evento quando protezione di rete viene attivata in modalità blocco
Accesso controllato alle cartelle | Windows Defender (operativo) | 5007 | Evento quando vengono modificate le impostazioni
Accesso controllato alle cartelle | Windows Defender (operativo) | 1124 | Evento di accesso controllato controllato alle cartelle controllato
Accesso controllato alle cartelle | Windows Defender (operativo) | 1123 | Evento accesso controllato bloccato alle cartelle
Accesso controllato alle cartelle | Windows Defender (operativo) | 1127 | Evento blocco scrittura settore accesso controllato bloccato
Accesso controllato alle cartelle | Windows Defender (operativo) | 1128 | Audited Controlled folder access sector write block event
La riduzione della superficie di attacco | Windows Defender (operativo) | 5007 | Evento quando vengono modificate le impostazioni
La riduzione della superficie di attacco | Windows Defender (operativo) | 1122 | Evento quando la regola viene attivata in modalità di controllo
La riduzione della superficie di attacco | Windows Defender (operativo) | 1121 | Evento quando la regola viene attivata in modalità blocco
