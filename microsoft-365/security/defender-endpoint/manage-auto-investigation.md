---
title: Esaminare le azioni di correzione dopo indagini automatizzate
description: Esaminare e approvare (o rifiutare) le azioni di correzione dopo un'indagine automatizzata.
keywords: autoir, automatizzato, indagine, rilevamento, correzione, azione, in sospeso, approvato
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: JoeDavies-MSFT
ms.author: josephd
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: how-to
ms.date: 01/29/2021
ms.technology: mde
ms.openlocfilehash: 410972bd823c3a3c4fda53cacc225014d83f3457
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844011"
---
# <a name="review-remediation-actions-following-an-automated-investigation"></a>Esaminare le azioni di correzione dopo un'indagine automatizzata

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


## <a name="remediation-actions"></a>Azioni correttive

Quando viene [eseguita un'indagine automatizzata,](automated-investigations.md) viene generato un verdetto per ogni prova esaminata. I verdetti possono essere *Dannosi,* *Sospetti* o *Nessuna minaccia trovata.* 

A seconda

- il tipo di minaccia, 
- il verdetto risultante e 
- come vengono configurati i gruppi [di dispositivi dell'organizzazione,](/microsoft-365/security/defender-endpoint/machine-groups) 

le azioni di correzione possono essere eseguite automaticamente o solo dopo l'approvazione da parte del team delle operazioni di sicurezza dell'organizzazione. 

Ecco alcuni esempi:

- **Esempio 1:** i gruppi di dispositivi di Fabrikam sono impostati su Completo - correggere **automaticamente** le minacce (impostazione consigliata). In questo caso, le azioni di correzione vengono eseguite automaticamente per gli artefatti considerati dannosi a seguito di un'indagine automatizzata (vedere [Review completed actions](#review-completed-actions)).

- **Esempio 2:** i dispositivi di Contoso sono inclusi in un gruppo di dispositivi impostato per Semi - richiede l'approvazione per **qualsiasi correzione.** In questo caso, il team delle operazioni di sicurezza di Contoso deve esaminare e approvare tutte le azioni di correzione dopo un'indagine automatizzata (vedere [Review pending actions](#review-pending-actions)).

- **Esempio 3:** i gruppi di dispositivi di Tailspin Toys sono impostati su **Nessuna risposta automatica** (scelta non consigliata). In questo caso, non si verificano indagini automatizzate. Nessuna azione di correzione viene eseguita o in sospeso [](/microsoft-365/security/defender-endpoint/auto-investigation-action-center#the-action-center) e nessuna azione viene registrata nel centro notifiche per i dispositivi (vedere [Gestire i gruppi di dispositivi](/microsoft-365/security/defender-endpoint/machine-groups#manage-device-groups)).

Se eseguita automaticamente o dopo l'approvazione, un'indagine automatizzata può comportare una o più azioni di correzione:
- Mettere in quarantena un file
- Rimuovere una chiave del Registro di sistema 
- Uccidi un processo 
- Arrestare un servizio 
- Disabilitare un driver 
- Rimuovere un'attività pianificata

## <a name="review-pending-actions"></a>Rivedere le azioni in sospeso

1. Accedere al centro Microsoft 365 sicurezza ( [https://security.microsoft.com](https://security.microsoft.com) ) ed eseguire l'accesso.
2. Nel riquadro di spostamento, scegliere **Centro notifiche**. 
3. Esaminare gli elementi nella **scheda In** sospeso. 
4. Selezionare un'azione per aprire il riquadro a comparsa.
5. Nel riquadro a comparsa esaminare le informazioni e quindi eseguire una delle operazioni seguenti:
   - Selezionare **Apri pagina di indagine** per visualizzare ulteriori dettagli sull'indagine.
   - Selezionare **Approva** per avviare un'azione in sospeso.
   - Selezionare **Rifiuta** per impedire l'esecuzione di un'azione in sospeso.
   - Seleziona **Vai a ricerca** per passare a Ricerca [avanzata.](advanced-hunting-overview.md) 

## <a name="review-completed-actions"></a>Rivedere le azioni completate

1. Accedere al centro Microsoft 365 sicurezza ( [https://security.microsoft.com](https://security.microsoft.com) ) ed eseguire l'accesso.
2. Nel riquadro di spostamento, scegliere **Centro notifiche**. 
3. Esaminare gli elementi nella **scheda** Cronologia. 
4. Selezionare un elemento per visualizzare ulteriori dettagli sull'azione di correzione.
 
## <a name="undo-completed-actions"></a>Annullare le azioni completate

Se hai determinato che un dispositivo o un file non è una minaccia, puoi annullare le azioni di correzione eseguite, indipendentemente dal fatto che tali azioni siano state eseguite automaticamente o manualmente. Nel centro notifiche, nella **scheda Cronologia,** è possibile annullare una delle azioni seguenti:  

| Origine azione | Azioni supportate |
|:---|:---|
| - Indagine automatizzata <br/>- Antivirus Microsoft Defender <br/>- Azioni di risposta manuale | - Isola dispositivo <br/>- Limitare l'esecuzione del codice <br/>- Mettere in quarantena un file <br/>- Rimuovere una chiave del Registro di sistema <br/>- Arrestare un servizio <br/>- Disabilitare un driver <br/>- Rimuovere un'attività pianificata |

### <a name="to-undo-multiple-actions-at-one-time"></a>Per annullare più azioni contemporaneamente

1. Vai al centro notifiche ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ) e accedi.
2. Nella scheda **Cronologia** selezionare le azioni che si desidera annullare. Assicurarsi di selezionare gli elementi con lo stesso tipo di azione. Verrà visualizzato un riquadro a comparsa.
3. Nel riquadro a comparsa selezionare **Annulla.**

### <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a>Per rimuovere un file dalla quarantena su più dispositivi 

1. Vai al centro notifiche ( [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) ) e accedi.
2. Nella scheda **Cronologia** selezionare un elemento con il tipo di azione **File quarantena.**
3. Nel riquadro a comparsa, selezionare **Applica a X altre istanze del file** e quindi fare clic su **Annulla.**

## <a name="automation-levels-automated-investigation-results-and-resulting-actions"></a>Livelli di automazione, risultati delle indagini automatizzate e azioni risultanti

I livelli di automazione influiscono sul fatto che determinate azioni di correzione siano eseguite automaticamente o solo dopo l'approvazione. A volte il team delle operazioni di sicurezza ha più passaggi da eseguire, a seconda dei risultati di un'indagine automatizzata. Nella tabella seguente sono riepilogati i livelli di automazione, i risultati delle indagini automatizzate e le operazioni da eseguire in ogni caso. 

|Impostazione del gruppo di dispositivi | Risultati dell'indagine automatizzata | Soluzione |
|:---|:---|:---|
|**Completo : correggere automaticamente le minacce** (impostazione consigliata) |Viene raggiunto un verdetto *di Dannoso* per una prova. <br/><br/>Le azioni correttive appropriate vengono eseguite automaticamente. |[Rivedere le azioni completate](#review-completed-actions) |
|**Completo : correggere automaticamente le minacce** |Viene raggiunto un verdetto *di Sospetto* per un elemento di prova. <br/><br/>Le azioni di correzione sono in attesa di approvazione per procedere. | [Approvare (o rifiutare) le azioni in sospeso](#review-pending-actions) |
|**Semi - Richiede l'approvazione per qualsiasi correzione**  |Viene raggiunto un verdetto di *dannoso* *o* sospetto per un elemento di prova. <br/><br/>Le azioni di correzione sono in attesa di approvazione per procedere.  |[Approvare (o rifiutare) le azioni in sospeso](#review-pending-actions) |
|**Semi - Richiede l'approvazione per la correzione delle cartelle principali** |Viene raggiunto un verdetto *di Dannoso* per una prova. <br/><br/>Se l'elemento è un file o un file eseguibile e si trova in una directory del sistema operativo, ad esempio la cartella Windows o la cartella Programmi, le azioni di correzione sono in attesa di approvazione. <br/><br/>Se l'artefatto *non si trova* in una directory del sistema operativo, le azioni di correzione vengono eseguite automaticamente. |1. [Approvare (o rifiutare) le azioni in sospeso](#review-pending-actions)<br/><br/>2. [Rivedere le azioni completate](#review-completed-actions) |
|**Semi - Richiede l'approvazione per la correzione delle cartelle principali** |Viene raggiunto un verdetto *di Sospetto* per un elemento di prova. <br/><br/>Le azioni di correzione sono in attesa di approvazione.  |[Approvare (o rifiutare) le azioni in sospeso.](#review-pending-actions)|
|**Semi - Richiede l'approvazione per la correzione delle cartelle non temporanee** |Viene raggiunto un verdetto *di Dannoso* per una prova. <br/><br/>Se l'elemento è un file o un file eseguibile che non si trova in una cartella temporanea, ad esempio la cartella di download o la cartella temporanea dell'utente, le azioni di correzione sono in attesa di approvazione. <br/><br/>Se l'elemento è un file o un file *eseguibile* in una cartella temporanea, le azioni di correzione vengono eseguite automaticamente.  |1. [Approvare (o rifiutare) le azioni in sospeso](#review-pending-actions)<br/><br/>2. [Rivedere le azioni completate](#review-completed-actions)  |
|**Semi - Richiede l'approvazione per la correzione delle cartelle non temporanee** |Viene raggiunto un verdetto *di Sospetto* per un elemento di prova. <br/><br/>Le azioni di correzione sono in attesa di approvazione. |[Approvare (o rifiutare) le azioni in sospeso](#review-pending-actions)  | 
|Qualsiasi livello **di automazione completo** o **semiautorizzazione** |Viene raggiunto il verdetto *Nessuna minaccia* trovata per un elemento di prova. <br/><br/>Non vengono eseguite azioni di correzione e nessuna azione è in attesa di approvazione. |[Visualizzare dettagli e risultati delle indagini automatizzate](/microsoft-365/security/defender-endpoint/auto-investigation-action-center) |
|**Nessuna risposta automatica** (scelta non consigliata)|Non vengono eseguite indagini automatizzate, quindi non vengono raggiunti verdetti e non vengono intraprese azioni di correzione o in attesa di approvazione. |[Valuta la possibilità di configurare o modificare i gruppi di dispositivi per usare **l'automazione** completa **o semiautonotica**](/microsoft-365/security/defender-endpoint/machine-groups) |

In Microsoft Defender per Endpoint, tutti i verdetti vengono monitorati nel [centro notifiche.](auto-investigation-action-center.md#new-a-unified-action-center)

## <a name="next-steps"></a>Passaggi successivi

- [Informazioni sulle funzionalità di risposta in tempo reale](live-response.md)
- [Ricerca proattiva di minacce con ricerca avanzata](advanced-hunting-overview.md)
- [Indirizzare i falsi positivi/negativi in Microsoft Defender per Endpoint](defender-endpoint-false-positives-negatives.md)

## <a name="see-also"></a>Vedere anche

- [Panoramica delle indagini automatizzate](automated-investigations.md)
