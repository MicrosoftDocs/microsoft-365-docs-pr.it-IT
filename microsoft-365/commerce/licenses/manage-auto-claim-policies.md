---
title: Gestire i criteri di attestazione automatica
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
description: Scopri come creare e gestire i criteri di attestazione automatica che assegnano automaticamente licenze agli utenti per determinate app.
ms.custom:
- AdminSurgePortfolio
- commerce
search.appverid:
- MET150
ms.openlocfilehash: c1715d2420315c6e645303c959512a45d47fddfe
ms.sourcegitcommit: bf9e0091e5bdc78d9b23be64583eb816bb059eb2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2021
ms.locfileid: "50759207"
---
# <a name="manage-auto-claim-policies"></a>Gestire i criteri di attestazione automatica

Un criterio di attestazione automatica consente agli utenti di richiedere automaticamente una licenza per un prodotto al primo accesso a un'app. Gli amministratori assegnano in genere le licenze agli utenti manualmente o usando le licenze basate su gruppo. Utilizzando i criteri di attestazione automatica, puoi gestire i prodotti per i quali gli utenti possono richiedere automaticamente le licenze. Puoi anche controllare i prodotti da cui provengono le licenze.

Dopo aver creato un criterio di attestazione automatica, è possibile eseguire le attività seguenti per gestire il criterio:

- [Attivare o disattivare il criterio](#turn-a-policy-on-or-off)
- [Modificare il nome descrittivo dei criteri](#edit-the-policy-friendly-name)
- [Aggiungere o rimuovere prodotti di backup](#add-or-remove-backup-products)
- [Gestire l'assegnazione di app e servizi](#change-the-assigning-apps-and-services)
- [Modificare l'ordine di assegnazione](#change-the-assigning-order-for-backup-products)
- [Visualizzare un report dei criteri](#view-an-auto-claim-policy-report)

> [!IMPORTANT]
> I criteri di attestazione automatica sono attualmente disponibili solo per Microsoft Teams. Altri prodotti saranno disponibili per l'uso in futuro.

## <a name="before-you-begin"></a>Informazioni preliminari

Devi essere un amministratore globale, fatturazione o utente per creare e gestire i criteri di attestazione automatica. Per altre informazioni, vedere [Informazioni sui ruoli di amministratore di Microsoft 365](../../admin/add-users/about-admin-roles.md).

## <a name="turn-the-auto-claim-policy-feature-on-or-off"></a>Attivare o disattivare la funzionalità dei criteri di attestazione automatica

Per impostazione predefinita, la funzionalità dei criteri di attestazione automatica è disattivata. Prima di poter utilizzare la funzionalità, è necessario attivarla. Dopo aver attivata la funzionalità, puoi creare un criterio di attestazione automatica.

### <a name="turn-on-auto-claim-policies"></a>Attivare i criteri di attestazione automatica

1. Nell'interfaccia di amministrazione passare alla pagina **Licenze** \> **di** fatturazione, quindi selezionare la <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">scheda Criteri di richiesta</a> automatica.
2. Al centro della pagina seleziona il **pulsante Attiva impostazione.**

### <a name="turn-off-auto-claim-policies"></a>Disattivare i criteri di attestazione automatica

1. Nell'interfaccia di amministrazione passare alla pagina **Impostazioni** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2053743" target="_blank">organizzazione.</a>
2. Nella parte inferiore della tabella seleziona App e servizi **di proprietà dell'utente.**
3. Nel riquadro destro deselezionare la casella Consenti agli utenti di richiedere automaticamente le licenze al **primo accesso.**

Se si dispone già di un criterio attivo, ma non si desidera che altri utenti rivendicare licenze, [disattivare il criterio](#turn-a-policy-on-or-off). Quando dissegni un criterio di attestazione automatica, nessun altro utente può richiedere una licenza da quel momento in avanti. Gli utenti che hanno già richiesto una licenza non perdono la licenza.

## <a name="create-an-auto-claim-policy"></a>Creare un criterio di attestazione automatica

Nella <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">scheda Criteri di attestazione</a> automatica sono elencati i criteri creati. In questa scheda è possibile visualizzare il nome del criterio, l'app associata al criterio, il prodotto assegnato al criterio, il numero di licenze disponibili e lo stato del criterio.

Quando si crea un criterio di attestazione automatica, è possibile aggiungervi un prodotto di backup. Se il prodotto principale non ha licenze, il prodotto di backup viene utilizzato per assegnare licenze agli utenti. È possibile aggiungere fino a quattro prodotti di backup [e modificare l'ordine in cui vengono utilizzati.](#change-the-assigning-order-for-backup-products) Per ulteriori informazioni, vedere [Aggiungere o rimuovere prodotti di backup.](#add-or-remove-backup-products)

> [!NOTE]
> Attualmente, è possibile creare un solo criterio di attestazione automatica. Il numero di criteri che è possibile creare aumenterà man quando più prodotti saranno in grado di utilizzare questa funzionalità.

1. Nell'interfaccia di amministrazione passare alla pagina **Licenze** \> **di** fatturazione, quindi selezionare la <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">scheda Criteri di richiesta</a> automatica.
2. Selezionare **Aggiungi un criterio.**
3. Nella pagina **Assegnare un nome al criterio** di attestazione automatica immettere un nome per il criterio, quindi selezionare **Avanti.**
4. Nella pagina **Imposta un'app e** un prodotto per l'attestazione automatica seleziona un'app e l'abbonamento da cui assegnare le licenze.
5. Se si desidera aggiungere un prodotto di backup, selezionare Aggiungi un prodotto **di backup a questo criterio,** quindi selezionare il prodotto nell'elenco.
6. Selezionare **Avanti**.
7. Nella pagina **Seleziona app** deselezionare o selezionare le caselle per le app da escludere o includere con la licenza, quindi selezionare **Avanti.**
8. Se sono stati aggiunti uno o più prodotti di backup, ripetere il passaggio 7 per ogni prodotto. In caso contrario, andare al passaggio 9.
9. Nella pagina **Revisione e fine** verificare le nuove informazioni sui criteri, apportare le modifiche necessarie, quindi selezionare Crea **criterio.**
10. Selezionare **Chiudi**.

## <a name="turn-a-policy-on-or-off"></a>Attivare o disattivare un criterio

Quando si disattiva un criterio, nessun altro utente può richiedere licenze in base a tale criterio. La modifica non influisce sugli utenti che hanno già richiesto licenze in base a tale criterio.

1. Nell'interfaccia di amministrazione passare alla pagina **Licenze** \> **di** fatturazione, quindi selezionare la <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">scheda Criteri di richiesta</a> automatica.
2. Selezionare il criterio che si desidera modificare.
3. Nel riquadro dei dettagli, in Attiva o disattiva **questo criterio,** selezionare o deselezionare la casella di controllo.
4. Selezionare **Salva** per chiudere il riquadro dei dettagli.

## <a name="edit-the-policy-friendly-name"></a>Modificare il nome descrittivo dei criteri

1. Nell'interfaccia di amministrazione passare alla pagina **Licenze** \> **di** fatturazione, quindi selezionare la <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">scheda Criteri di richiesta</a> automatica.
2. Selezionare il criterio che si desidera modificare.
3. Nella sezione Nome criterio  del riquadro dei dettagli selezionare **Modifica**.
4. Immettere un nuovo nome di criterio, quindi selezionare **Salva**.
5. Selezionare **Salva** per chiudere il riquadro dei dettagli.

## <a name="add-or-remove-backup-products"></a>Aggiungere o rimuovere prodotti di backup

Quando si crea un criterio, si aggiunge un prodotto. Le licenze vengono quindi assegnate automaticamente agli utenti di tale pool di licenze. Puoi aggiungere o rimuovere prodotti per un criterio di attestazione automatica in qualsiasi momento. Se al criterio è già associato un prodotto, tutti i prodotti aggiunti vengono considerati prodotti di backup. Quando viene utilizzato il numero di licenze disponibili del primo prodotto, il criterio utilizza il prodotto di backup successivo nell'elenco per assegnare le licenze. Puoi [riordinare l'elenco dei prodotti](#change-the-assigning-apps-and-services) come vuoi.

Quando si rimuove un prodotto di backup, non viene più utilizzato per assegnare licenze. Gli utenti con una licenza esistente dispongono ancora di tale licenza, ma nessun nuovo utente può ricevere licenze per tale prodotto.

> [!NOTE]
> Un criterio di attestazione automatica deve contenere almeno un prodotto. Non è possibile rimuovere tutti i prodotti da un criterio. Se non vuoi più assegnare licenze da uno specifico criterio di attestazione automatica, [disattiva il criterio](#view-an-auto-claim-policy-report).

### <a name="add-a-backup-product"></a>Aggiungere un prodotto di backup

1. Nell'interfaccia di amministrazione passare alla pagina **Licenze** \> **di** fatturazione, quindi selezionare la <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">scheda Criteri di richiesta</a> automatica.
2. Selezionare il criterio che si desidera modificare.
3. Nel riquadro dei dettagli, nella parte inferiore, selezionare **Aggiungi un prodotto di backup a questo criterio.**
    > [!NOTE]
    > Se non vedi questo collegamento, è perché hai un solo prodotto associato al tuo account.
4. Nel riquadro **Aggiungi un prodotto** usa l'elenco a discesa per scegliere un prodotto da aggiungere al criterio, quindi seleziona **Aggiungi.**
5. Selezionare **Salva** per chiudere il riquadro dei dettagli.

### <a name="remove-a-backup-product"></a>Rimuovere un prodotto di backup

1. Nell'interfaccia di amministrazione passare alla pagina **Licenze** \> **di** fatturazione, quindi selezionare la <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">scheda Criteri di richiesta</a> automatica.
2. Selezionare il criterio che si desidera modificare.
3. Nel riquadro dei dettagli, nella parte inferiore, selezionare **Rimuovi un prodotto.**
4. Nel riquadro **Rimuovi un prodotto dal criterio** selezionare la casella per il criterio che si desidera rimuovere, quindi selezionare **Salva**.
5. Chiudere il riquadro dei dettagli.

## <a name="change-the-assigning-apps-and-services"></a>Modificare le app e i servizi di assegnazione

A ogni prodotto è associata una raccolta di app e servizi.
Per ogni prodotto nei criteri di attestazione automatica, puoi specificare quali app e servizi includere quando a un utente viene assegnata automaticamente una licenza a tale prodotto.

1. Nell'interfaccia di amministrazione passare alla pagina **Licenze** \> **di** fatturazione, quindi selezionare la <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">scheda Criteri di richiesta</a> automatica.
2. Selezionare il criterio che si desidera modificare.
3. Nel riquadro dei dettagli, in **App e servizi,** selezionare **Modifica.**
4. **Nell'elenco** a discesa **Prodotto** del riquadro App e servizi selezionare un singolo prodotto oppure selezionare Tutti **i prodotti**.
5. Seleziona o deseleziona le caselle per le app e i servizi a cui vuoi che gli utenti hanno o meno accesso.
6. Al termine, selezionare **Salva** e quindi chiudere il riquadro dei dettagli.

## <a name="change-the-assigning-order-for-backup-products"></a>Modificare l'ordine di assegnazione per i prodotti di backup

Se al criterio sono stati assegnati prodotti di backup, puoi modificare l'ordine in cui vengono usati per assegnare le licenze quando gli utenti a volta a volta a un'app.

1. Nell'interfaccia di amministrazione passare alla pagina **Licenze** \> **di** fatturazione, quindi selezionare la <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">scheda Criteri di richiesta</a> automatica.
2. Selezionare il criterio che si desidera modificare.
3. Nella sezione Licenze prodotto  del riquadro dei dettagli selezionare la casella accanto al  prodotto che si desidera spostare, quindi selezionare Sposta su **o Sposta giù.**
4. Ripetere il passaggio 3 per ogni prodotto che si desidera riordinare.
5. Al termine dell'ordinamento dei prodotti, selezionare **Salva** per chiudere il riquadro dei dettagli.

## <a name="view-an-auto-claim-policy-report"></a>Visualizzare un report dei criteri di attestazione automatica

1. Nell'interfaccia di amministrazione passare alla pagina **Licenze** \> **di** fatturazione, quindi selezionare la <a href="https://go.microsoft.com/fwlink/p/?linkid=2134398" target="_blank">scheda Criteri di richiesta</a> automatica.
2. Selezionare **Visualizza report.** Nella **pagina Report dei criteri di** attestazione automatica sono elencate tutte le licenze assegnate da ogni criterio negli ultimi 90 giorni. Per impostazione predefinita, la pagina mostra gli ultimi 90 giorni.
3. Per modificare il periodo di tempo visualizzato, selezionare **l'elenco a discesa Ultimi 30** giorni. È possibile visualizzare i report degli ultimi 1, 7, 30 e 90 giorni.

## <a name="next-steps"></a>Passaggi successivi

È possibile tornare periodicamente alla **scheda** Criteri di attestazione automatica per visualizzare un elenco di utenti che hanno richiesto licenze in base ai criteri creati.

## <a name="related-content"></a>Contenuti correlati

[Assegnare licenze agli utenti](../../admin/manage/assign-licenses-to-users.md) (articolo)\
[Acquistare o rimuovere licenze di sottoscrizione](buy-licenses.md) (articolo)\
[Informazioni su sottoscrizioni e licenze](subscriptions-and-licenses.md) (articolo)
