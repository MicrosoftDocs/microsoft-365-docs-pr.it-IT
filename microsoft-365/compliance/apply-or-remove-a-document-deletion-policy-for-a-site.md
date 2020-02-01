---
title: Applicare o rimuovere un criterio di eliminazione del documento per un sito
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: 6/29/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3e92668-f9b2-46ee-8e5e-c623870588b6
description: Le organizzazioni spesso sono soggette a regolamentazioni di conformità, normative legali o di altro tipo, che richiedono di mantenere i documenti per un certo periodo di tempo. Tuttavia, mantenere i documenti più a lungo del necessario può esporre l'organizzazione a rischi legali. Per questo motivo, la tua organizzazione potrebbe aver creato un criterio di eliminazione del documento per il tuo sito; per esempio, potrebbe essere necessario eliminare i documenti dell'attività generale cinque anni dopo la loro creazione.
ms.openlocfilehash: 67bbe3339b492e5199799a21e5b3b249a3a98c08
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "41596073"
---
# <a name="apply-or-remove-a-document-deletion-policy-for-a-site"></a>Applicare o rimuovere un criterio di eliminazione del documento per un sito

Le organizzazioni spesso sono soggette a regolamentazioni di conformità, normative legali o di altro tipo, che richiedono di mantenere i documenti per un certo periodo di tempo. Tuttavia, mantenere i documenti più a lungo del necessario può esporre l'organizzazione a rischi legali. Per questo motivo, è possibile che l'organizzazione abbia creato un criterio di eliminazione dei&mdash;documenti per il sito, ad esempio, i documenti aziendali generali potrebbero essere necessari per essere eliminati cinque anni dopo la loro creazione.
  
A seconda dell'organizzazione, un criterio di eliminazione del documento può essere:
  
- **Obbligatorio** Il proprietario di un sito non può escludere un criterio obbligatorio, che viene automaticamente applicato al sito. 
    
- **Predefinito** Un criterio predefinito è applicato al sito automaticamente, ma il proprietario del sito può: 
    
  - Selezionare un altro criterio, se disponibile.
    
  - Escludere completamente il criterio se non è pertinente per il contenuto del sito.
    
- **Né obbligatorio né predefinito** In questo caso, nessun criterio è applicato al sito automaticamente e il proprietario del sito deve eseguire determinate azioni per applicarne uno. 
    
Un criterio di eliminazione dei documenti può contenere più di&mdash;una regola, ad esempio, una regola potrebbe dire eliminare i documenti un anno dopo che sono stati creati, ma un'altra regola potrebbe dire eliminare i documenti un anno dopo l'ultima modifica. Se un criterio contiene più di una regola, è possibile selezionare la regola che meglio si applica al sito. La regola di eliminazione verrà applicata a tutte le raccolte all'interno del sito. Solo un criterio e una regola alla volta possono essere attivi in un sito. Analogamente a un criterio, è possibile impostare una regola come predefinita, in modo che venga applicata automaticamente quando viene applicato il criterio.
  
Infine, i criteri di eliminazione del documento vengono ereditati. Quando selezioni un criterio o una regola per il tuo sito, tale scelta viene ereditata da tutti i siti secondari, anche se il proprietario di un sito secondario può interrompere l'ereditarietà selezionando un criterio o una regola diversi. Quando selezioni un criterio o una regola, tieni presente il contenuto di eventuali siti secondari all'interno del tuo sito.
  
## <a name="view-the-document-deletion-policies-available-in-a-site-collection"></a>Visualizzare i criteri di eliminazione del documento disponibili in una raccolta siti

La tua organizzazione può assegnare criteri diversi a raccolte siti diverse. A livello della raccolta siti, il proprietario di una raccolta siti può visualizzare tutti i criteri di eliminazione del documento disponibili per tale raccolta siti. I criteri possono essere stati resi disponibili per il modello della raccolta siti (e di conseguenza per tutte le raccolte siti create da quel modello) oppure per quella specifica raccolta siti.
  
1. Nel sito principale della raccolta siti, nell'angolo in alto a destra, scegliere **Impostazioni** [icona Gear] \> **Impostazioni sito**.
    
2. In **criteri di eliminazione dei documenti**di **Amministrazione** \> raccolta siti.
    
    > [!NOTE]
    > Il collegamento **criteri di eliminazione dei documenti** non verrà visualizzato a meno che non siano stati assegnati criteri alla raccolta siti. Inoltre, il collegamento non viene visualizzato subito dopo che i criteri sono stati assegnati al sito, ma può richiedere fino a 24 ore da quando i criteri vengono assegnati quando viene visualizzato il collegamento **criteri di eliminazione dei documenti** . 
  
3. In questa pagina puoi trovare:
    
  - I criteri attualmente assegnati e le regole associate. Seleziona un criterio per visualizzare le regole nel riquadro destro.
    
  - Se presente, il criterio predefinito presenta l'opzione **Sì** nella colonna **predefinita**. 
    
  - Se è stato assegnato un criterio **obbligatorio**, al di sotto dell'elenco viene visualizzato un messaggio.
    
Questo elenco è solo in modalità visualizzazione e consente al proprietario della raccolta siti di vedere tutti i criteri e le regole disponibili. Per informazioni sull'applicazione di un criterio, consulta la sezione successiva.
  
![Visualizzare i criteri di eliminazione dei documenti assegnati a una raccolta siti](media/f2c0433b-2bb5-407d-a364-ae07c9627176.png)
  
## <a name="apply-or-remove-a-document-deletion-policy-for-a-site"></a>Applicare o rimuovere un criterio di eliminazione del documento per un sito

È possibile che la tua organizzazione abbia creato dei criteri che, in qualità di proprietario di un sito o di una raccolta siti, puoi sia applicare al tuo sito sia disattivare completamente.
  
1. Nell'angolo in alto a destra, scegliere **Impostazioni** [icona ingranaggi] \> **Impostazioni sito**.
    
2. In **criteri di eliminazione dei documenti**di amministrazione \> del **sito** .
    
    > [!NOTE]
    > Il collegamento **criteri di eliminazione dei documenti** non verrà visualizzato a meno che non siano stati assegnati criteri alla raccolta siti. Inoltre, il collegamento non viene visualizzato subito dopo che i criteri sono stati assegnati al sito, ma può richiedere fino a 24 ore da quando i criteri vengono assegnati quando viene visualizzato il collegamento **criteri di eliminazione dei documenti** . 
  
3. Eseguire una delle operazioni seguenti:
    
  - **Per applicare un criterio** Selezionare un criterio \> selezionare una regola per il \> **salvataggio**di un criterio.
    
    Solo un criterio e una regola alla volta possono essere attivi in un sito. L'organizzazione può fornire più criteri e regole tra cui scegliere oppure metterne a disposizione solo uno.
    
    ![Selezionare l'opzione criterio](media/f7c7c055-fca7-4a4f-bb97-63e35a65beac.png)
  
  - **Per rifiutare l'esclusione di un criterio** Scegliere **opt-out: do note Delete** \> **Save**.
    
    Come proprietario di un sito, è possibile escludere un criterio di eliminazione dei documenti se si determina che il criterio non è applicabile al contenuto del sito. Tuttavia, non è possibile escludere un criterio contrassegnato come **obbligatorio**.
    
    ![Opzione opt-out](media/efac709c-bef7-4a02-a09d-5bc7d2b4ec63.png)
  
## <a name="document-deletion-policies-override-other-policies"></a>I criteri di eliminazione del documento ignorano altri criteri

Un sito può utilizzare altri criteri per il mantenimento e l'eliminazione dei contenuti:
  
- Criteri tipo di contenuto per la raccolta siti.
    
- Criteri di gestione delle informazioni per un elenco o una libreria.
    
Se applichi un criterio di eliminazione del documento a un sito che già utilizza criteri tipo di contenuto o criteri di gestione delle informazioni per un elenco o una libreria, tali criteri vengono ignorati mentre il criterio di eliminazione del documento è attivo. Se altri criteri vengono ignorati, verrà visualizzato il messaggio "contenuto in questo sito utilizza i criteri di eliminazione dei documenti".
  
Questo significa che dovresti pianificare un sito che utilizzi solo criteri destinati a contenuti strutturati (criteri di gestione delle informazioni e criteri tipo di contenuto) o contenuti non strutturati (criteri di eliminazione del documento) e non ad entrambi. Se si sceglie di escludere un criterio di eliminazione dei documenti, l'avviso non verrà visualizzato e altri tipi di criteri continueranno a funzionare.
  
I criteri di eliminazione del documento non hanno alcun effetto sui criteri sito.
  
### <a name="determine-if-content-type-policies-are-being-ignored"></a>Determinare se i criteri tipo di contenuto vengono ignorati

Se il tuo sito stava utilizzando criteri tipo di contenuto e ne ricevi il messaggio solo adesso, quei criteri non sono più attivi. Per ripristinare i criteri dei tipi di contenuto, è possibile rimuovere il criterio di eliminazione dei documenti dal sito, come descritto in precedenza, se è disponibile un'opzione di disattivazione. Se non è possibile escludere l'opzione, i criteri di eliminazione dei documenti sono obbligatori ed è necessario contattare il responsabile della conformità nell'organizzazione.
  
1. Nell'angolo in alto a destra, scegliere **Impostazioni** [icona ingranaggi] \> **Impostazioni sito**.
    
2. In \> **modelli di criteri tipo di contenuto** **Amministrazione sito** .
    
    ![Avviso sul sito in cui vengono utilizzati i criteri di eliminazione dei documenti](media/4cc3d703-9aff-4695-9670-f78c291c0010.png)
  
### <a name="determine-if-information-management-policies-are-being-ignored"></a>Determinare se i criteri di gestione delle informazioni vengono ignorati

Se il tuo sito stava utilizzando criteri di gestione delle informazioni e ne ricevi il messaggio solo adesso, quei criteri non sono più attivi. Per ripristinare i criteri di gestione delle informazioni, è possibile rimuovere il criterio di eliminazione dei documenti dal sito, come descritto in precedenza, se è disponibile un'opzione di disattivazione. Se non è possibile escludere l'opzione, i criteri di eliminazione dei documenti sono obbligatori ed è necessario contattare il responsabile della conformità nell'organizzazione.
  
- Per un elenco o una raccolta, nelle impostazioni \> della \> **raccolta** \> **schede della raccolta della** barra multifunzione in **autorizzazioni e gestione** \> delle informazioni di gestione **delle impostazioni dei criteri**.
    
    ![Avviso sul sito in cui vengono utilizzati i criteri di eliminazione dei documenti](media/3f043057-a741-4cd8-a165-6d139b986064.png)
  
## <a name="see-also"></a>Vedere anche

[Panoramica dei criteri di eliminazione dei documenti](document-deletion-policies.md)
  
[Creare un criterio di eliminazione dei documenti](create-a-document-deletion-policy.md)

