---
title: Gestire le notifiche di blocco
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
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Utilizzare il flusso di lavoro per le comunicazioni in Advanced eDiscovery per tenere conto dello stato delle notifiche di archiviazione legale e, se necessario, aggiornarlo e inviarlo nuovamente.
ms.openlocfilehash: 8852bfd1651e1855d276b60ba6fac35c378d4631
ms.sourcegitcommit: 6d672eb8287526a9db90df5fa85bc4984a7047d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/26/2020
ms.locfileid: "42280114"
---
# <a name="manage-hold-notifications"></a>Gestire le notifiche di blocco

Dopo aver avviato il flusso di lavoro di notifica per la conservazione legale, è possibile utilizzare il flusso di lavoro comunicazioni in Advanced eDiscovery per tenere conto dello stato delle comunicazioni. La scheda comunicazioni contiene un elenco di tutte le notifiche all'interno del caso eDiscovery avanzato. È possibile visualizzare i dettagli, ad esempio il numero di depositari che sono stati assegnati o che hanno riconosciuto l'avviso.

## <a name="monitor-acknowledgments"></a>Monitorare i ringraziamenti

Dopo aver selezionato una comunicazione dalla scheda **comunicazioni** , è possibile visualizzare un elenco di depositari che hanno riconosciuto un avviso di esenzione. 

1. Nel centro conformità, accedere a **eDiscovery > Advanced eDiscovery**.

2. Selezionare un caso e quindi fare clic sulla scheda **comunicazioni** .

3. Selezionare una comunicazione per visualizzare la pagina del riquadro a comparsa **comunicazione depositaria** .

Un elenco di depositari associati alla comunicazione selezionata viene visualizzato nella pagina riquadro a comparsa di comunicazione. Questa pagina Visualizza anche informazioni dettagliate e sul numero di messaggi di riconoscimento ricevuti e su quanti sono inevasi. La pagina Visualizza inoltre i depositari che hanno inviato un riconoscimento per aver ricevuto la notifica di blocco.

## <a name="re-send-a-hold-notice"></a>Inviare di nuovo un avviso di esenzione

Occasionalmente, i depositari perdono la cognizione dei messaggi di posta elettronica nel lavoro quotidiano. O per un caso di controversia legale di lunga durata, un custode può contattare l'utente o altri utenti e richiedere di inviare di nuovo un avviso. Quando si gestisce il flusso di lavoro per le comunicazioni per gli avvisi di conservazione legale, potrebbe essere necessario inviare nuovamente una notifica per riportarla nella "parte superiore della cassetta postale di un utente".

Per inviare di nuovo un avviso di blocco a un custode:

1. In Advanced eDiscovery, selezionare un caso, quindi fare clic sulla scheda **comunicazioni** .

2. Selezionare una comunicazione per visualizzare la pagina del riquadro a comparsa **comunicazione depositaria** .

3. Fare clic su **altro > inviare nuovamente l'avviso di**conservazione.

4. Nella pagina **Rispedisci** il riquadro a comparsa di avviso di archiviazione, selezionare i depositari che consentono di inviare di nuovo la notifica e digitare un motivo facoltativo.

5. Fare clic su **re-send** per inviare la notifica ai depositari selezionati.

Se un custode non riconosce la notifica di archiviazione, viene riavviato il flusso di lavoro promemoria e escalation. Se un custode ha riconosciuto la notifica di conservazione, il custode riceverà una copia dell'avviso di conservazione originale.

> [!NOTE]
> È possibile inviare nuovamente una notifica di conservazione legale solo ai depositari che sono assegnati alla comunicazione. 

## <a name="update-preservation-requirements"></a>Aggiornare i requisiti di conservazione
  
Quando il caso progredisce, potrebbe essere necessario che i depositari possano conservare dati aggiuntivi o meno rispetto a quelli precedentemente istruiti. In termini di eDiscovery, è necessario riemettere la notifica di conservazione con il contenuto aggiornato.

Per aggiornare il contenuto dell'avviso di blocco iniziale:

1. In Advanced eDiscovery, selezionare un caso, quindi fare clic sulla scheda **comunicazioni** .

2. Selezionare l'avviso di blocco che si desidera aggiornare e fare clic su **modifica** nella pagina riquadro a comparsa **comunicazione custode** .

3. Nella procedura guidata **modifica comunicazione** fare clic su **Definisci contenuto portale** nel riquadro sinistro della procedura guidata e aggiornare il contenuto dell'avviso.

4. Fare clic su **Salva**.

L'avviso di riemissione verrà inviato a tutti i depositari assegnati alla notifica di conservazione legale. Inoltre, se l'avviso di promemoria o escalation è abilitato, i flussi di lavoro per tali tipi di notifiche verranno riavviati.

## <a name="update-legal-hold-notifications-and-settings"></a>Aggiornare le notifiche e le impostazioni per il blocco legale

Quando si aggiorna il contenuto o le impostazioni dell'avviso di emissione, rilascio, ristampa, promemoria o escalation, queste modifiche verranno applicate a tutte le comunicazioni future generate dal flusso di lavoro.

## <a name="more-information"></a>Altre informazioni

- [Aggiungere responsabili a un caso](add-custodians-to-case.md)

- [Creare un avviso per la conservazione legale](create-hold-notification.md)

- [Confermare la ricezione di una notifica di blocco](acknowledge-hold-notification.md)
