---
title: Configurare Advanced eDiscovery in Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-aed
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: In questo articolo viene descritto come configurare Advanced eDiscovery in modo che sia possibile iniziare a creare e gestire i casi. Vengono inoltre descritti gli abbonamenti e le licenze Microsoft necessari. Dopo aver completato alcuni passaggi rapidi, lo strumento Advanced eDiscovery è pronto per l'uso.
ms.openlocfilehash: aef5cd2e465306b4401cda66d4ba30c97b9fc8cd
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841177"
---
# <a name="set-up-microsoft-365-advanced-ediscovery"></a>Configurare Microsoft 365 Advanced eDiscovery

Advanced eDiscovery in Microsoft 365 offre un [flusso di lavoro end-to-end](overview-ediscovery-20.md#advanced-ediscovery-workflow) per conservare, raccogliere, esaminare, analizzare ed esportare i dati che rispondono alle indagini interne ed esterne dell'organizzazione. Non è necessario eseguire alcuna operazione per la distribuzione di Advanced eDiscovery, ma sono necessarie alcune attività prerequisite che devono essere completate da un amministratore IT e da un responsabile di eDiscovery prima che l'organizzazione possa iniziare a creare e utilizzare i casi avanzati di eDiscovery per gestire le indagini.

In questo articolo vengono illustrati i passaggi necessari per configurare Advanced eDiscovery. In questo modo è possibile garantire la corretta gestione delle licenze necessarie per accedere a Advanced eDiscovery e aggiungere i depositari ai casi, nonché assegnare le autorizzazioni al team legale e investigativo affinché possano accedere e gestire i casi.

## <a name="step-1-verify-and-assign-appropriate-licenses"></a>Passaggio 1: verifica e assegnazione delle licenze appropriate

La gestione delle licenze per Advanced eDiscovery richiede la sottoscrizione dell'organizzazione appropriata e la gestione delle licenze per utente.

- **Sottoscrizione organizzazione:** Per accedere alle funzionalità avanzate di eDiscovery nel centro conformità di Microsoft 365 o nel centro sicurezza & conformità, è necessario che l'organizzazione disponga di uno dei seguenti elementi:

  - Abbonamento a Microsoft 365 E5 o a Office 365 E5
  
  - Abbonamento a Microsoft 365 E3 con il componente aggiuntivo E5 Compliance

  - Sottoscrizione Microsoft 365 E3 con E5 eDiscovery e componente aggiuntivo di controllo

  Se non si dispone di un piano Microsoft 365 E5 esistente e si desidera provare Advanced eDiscovery, è possibile [aggiungere microsoft 365](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365) alla sottoscrizione esistente oppure [iscriversi per una versione di valutazione](https://www.microsoft.com/microsoft-365/enterprise) di Microsoft 365 E5.

- **Licenze per utente:** Per aggiungere un utente come custode in un caso di eDiscovery Advance, all'utente deve essere assegnata una delle licenze seguenti, a seconda dell'abbonamento dell'organizzazione:

  - Microsoft 365: agli utenti deve essere assegnata una licenza Microsoft 365 E5, una licenza per i componenti aggiuntivi per la conformità E5 o una licenza E5 eDiscovery e Audit Add-on.

  - Office 365: agli utenti deve essere assegnata una licenza di Office 365 E5.

   Per informazioni su come assegnare le licenze, vedere [assegnare licenze agli utenti](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).

> [!NOTE]
> Gli utenti hanno solo bisogno di una licenza E5 (o la licenza del componente aggiuntivo appropriato) da aggiungere come depositari a un caso avanzato di eDiscovery. Gli amministratori IT, i responsabili di eDiscovery, gli avvocati, i paralegals o gli investigatori che utilizzano Advanced eDiscovery per gestire i casi e esaminare i dati del caso non necessitano di una licenza E5 o di un componente aggiuntivo.

## <a name="step-2-assign-ediscovery-permissions"></a>Passaggio 2: assegnare autorizzazioni di eDiscovery

Per accedere a Advanced eDiscovery o aggiunto come membro di un caso avanzato di eDiscovery, a un utente devono essere assegnate le autorizzazioni appropriate. In particolare, un utente deve essere aggiunto come membro del gruppo di ruoli di gestione di eDiscovery nel centro sicurezza & conformità. I membri di questo gruppo di ruoli possono creare e gestire i casi di eDiscovery avanzati. Sono in grado di aggiungere e rimuovere membri, inserire depositari e posizioni di contenuto in attesa, gestire le notifiche per la conservazione legale, creare e modificare le ricerche associate a un caso, aggiungere i risultati di ricerca a un set di revisione, analizzare i dati in un set di revisione ed esportare e scaricare da un caso avanzato di eDiscovery.

Completare la procedura seguente per aggiungere gli utenti al gruppo di ruoli eDiscovery Manager:

1. Accedere a [https://protection.office.com/permissions](https://protection.office.com/permissions) e accedere usando le credenziali per un account di amministratore nell'organizzazione Microsoft 365.

2. Nella pagina **autorizzazioni** selezionare il gruppo di ruoli **eDiscovery Manager** .

3. Nella pagina riquadro a comparsa di eDiscovery Manager, fare clic su **modifica** accanto alla sezione **gestione eDiscovery** .

4. Nella pagina **Scegli eDiscovery Manager** nella procedura guidata modifica gruppo di ruoli fare clic su **Scegli gestione eDiscovery**.

5. Fare clic su **Aggiungi** e quindi selezionare la casella di controllo per tutti gli utenti che si desidera aggiungere al gruppo di ruoli.

6. Fare clic su **Aggiungi** per aggiungere gli utenti selezionati, quindi fare clic su **fine**.

7. Fare clic su **Salva** per aggiungere gli utenti al gruppo di ruoli, quindi fare clic su **Chiudi** per completare il passaggio.

### <a name="more-information-about-the-ediscovery-manager-role-group"></a>Ulteriori informazioni sul gruppo di ruoli eDiscovery Manager

Nel gruppo di ruoli eDiscovery Manager sono presenti due sottogruppi. La differenza tra questi sottogruppi dipende dall'ambito.

- **eDiscovery Manager:** È possibile visualizzare e gestire i casi di eDiscovery avanzati che creano o sono membri di. Se un altro Manager di eDiscovery crea un caso ma non aggiunge un secondo Manager di eDiscovery come membro del caso, il secondo responsabile di eDiscovery non sarà in grado di visualizzare o aprire il caso nella pagina Advanced eDiscovery nel centro conformità. In generale, la maggior parte delle persone nell'organizzazione può essere aggiunta al sottogruppo di gestione di eDiscovery.

- **amministratore di eDiscovery:** È in grado di eseguire tutte le attività di gestione dei casi che un Manager di eDiscovery può eseguire. Inoltre, un amministratore di eDiscovery è in grado di:

  - Visualizzare tutti i casi elencati nella pagina Advanced eDiscovery.
  
  - Gestire qualsiasi caso nell'organizzazione dopo che si è aggiunto come membro del caso.

  - Accedere ed esportare i dati del caso per qualsiasi caso nell'organizzazione.

  A causa dell'ampio ambito di accesso, un'organizzazione deve disporre di un numero limitato di amministratori che sono membri del sottogruppo Administrators di eDiscovery.

Per ulteriori informazioni sulle autorizzazioni di eDiscovery e una descrizione di ogni ruolo assegnato al gruppo di ruoli Gestione eDiscovery, vedere [assign eDiscovery Permissions](assign-ediscovery-permissions.md).

## <a name="step-3-configure-global-settings-for-advanced-ediscovery"></a>Passaggio 3: configurare le impostazioni globali per Advanced eDiscovery

L'ultimo passaggio da eseguire prima che gli utenti dell'organizzazione inizino a creare e a utilizzare i casi è la configurazione delle impostazioni globali che si applicano a tutti i casi nell'organizzazione. In questo momento, l'unica impostazione globale è il *rilevamento dei privilegi avvocato-client* (altre impostazioni globali saranno disponibili in futuro). Questa impostazione consente l'esecuzione del modello di privilegio avvocato-client quando si analizzano i dati in un set di revisione. Il modello utilizza l'apprendimento automatico per determinare la probabilità che un documento contenga contenuto che sia di natura legale. Confronta anche i partecipanti dei documenti con un elenco di avvocati (che viene inviato quando si configura il modello) per determinare se un documento ha almeno un partecipante che è un avvocato.

Per ulteriori informazioni sulla configurazione e sull'utilizzo del modello di rilevamento dei privilegi di avvocato-client, vedere [set up Attorney-Client Privilege Detection in Advanced eDiscovery](attorney-privilege-detection.md).

> [!NOTE]
> Si tratta di un passaggio facoltativo che è possibile eseguire in qualsiasi momento. L'implementazione del modello di rilevamento dei privilegi avvocato-client non impedisce la creazione e l'utilizzo di casi di eDiscovery avanzati.

## <a name="next-steps"></a>Passaggi successivi

Dopo aver configurato Advanced eDiscovery, si è pronti per [creare un caso](create-and-manage-advanced-ediscoveryv2-case.md).
