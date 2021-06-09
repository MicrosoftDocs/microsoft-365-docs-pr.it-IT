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
description: Utilizzare il flusso di lavoro delle comunicazioni in Advanced eDiscovery per tenere traccia dello stato delle notifiche di blocco legale e, se necessario, aggiornarle e inviarle di nuovo.
ms.openlocfilehash: 8852bfd1651e1855d276b60ba6fac35c378d4631
ms.sourcegitcommit: 6d672eb8287526a9db90df5fa85bc4984a7047d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/26/2020
ms.locfileid: "42280114"
---
# <a name="manage-hold-notifications"></a>Gestire le notifiche di blocco

Dopo aver avviato il flusso di lavoro di notifica di blocco legale, è possibile utilizzare il flusso di lavoro delle comunicazioni in Advanced eDiscovery per tenere traccia dello stato delle comunicazioni. La scheda Comunicazioni contiene un elenco di tutte le notifiche nell'Advanced eDiscovery caso. È possibile visualizzare dettagli quali il numero di custodi che sono stati assegnati o che hanno riconosciuto l'avviso.

## <a name="monitor-acknowledgments"></a>Monitorare i riconoscimenti

Dopo aver selezionato una comunicazione dalla **scheda Comunicazioni,** è possibile visualizzare un elenco di custodi che hanno riconosciuto un avviso di blocco. 

1. Nel Centro conformità passare a **eDiscovery > Advanced eDiscovery**.

2. Selezionare un caso e quindi fare clic **sulla scheda** Comunicazioni.

3. Selezionare una comunicazione per visualizzare la pagina del riquadro **a comparsa** di comunicazione di Custodian.

Nella pagina a comparsa di comunicazione viene visualizzato un elenco di custodi associati alla comunicazione selezionata. In questa pagina vengono inoltre visualizzate informazioni dettagliate sul numero di riconoscimenti ricevuti e su quanti sono in sospeso. La pagina mostra anche quali custodi hanno inviato un riconoscimento di aver ricevuto la notifica di blocco.

## <a name="re-send-a-hold-notice"></a>Inviare nuovamente un avviso di blocco

Occasionalmente, i custodi perdono traccia dei messaggi di posta elettronica nel loro lavoro quotidiano. In caso di controversia legale di lunga durata, un responsabile può contattare l'utente o altri utenti e richiedere di inviare di nuovo un avviso. Man mano che si gestisce il flusso di lavoro delle comunicazioni per gli avvisi di blocco legale, potrebbe essere necessario inviare di nuovo un avviso per riportarlo nella "parte superiore della cassetta postale di un utente".

Per inviare di nuovo un avviso di blocco a un responsabile:

1. In Advanced eDiscovery selezionare un caso e quindi fare clic sulla **scheda** Comunicazioni.

2. Selezionare una comunicazione per visualizzare la pagina del riquadro **a comparsa** di comunicazione di Custodian.

3. Fare **clic su Altro > nuovo avviso di blocco.**

4. Nella pagina **riquadro a** comparsa Invia nuovamente avviso di blocco, selezionare i custodi a cui inviare di nuovo l'avviso e digitare un motivo facoltativo.

5. Fare **clic su Invia di** nuovo per inviare l'avviso ai custodi selezionati.

Se un responsabile non ha riconosciuto la notifica di blocco, il flusso di lavoro promemoria e escalation viene riavviato. Se un responsabile ha riconosciuto l'avviso di blocco, il responsabile riceverà una copia dell'avviso di blocco originale.

> [!NOTE]
> È possibile inviare di nuovo una notifica di blocco legale solo ai custodi assegnati alla comunicazione. 

## <a name="update-preservation-requirements"></a>Aggiornare i requisiti di conservazione
  
Con l'avanzamento del caso, i custodi potrebbero essere tenuti a conservare dati aggiuntivi o meno di quelli precedentemente richiesti. In termini di eDiscovery, è necessario riemettere l'avviso di blocco con il contenuto aggiornato.

Per aggiornare il contenuto dell'avviso di blocco iniziale:

1. In Advanced eDiscovery selezionare un caso e quindi fare clic sulla **scheda** Comunicazioni.

2. Selezionare l'avviso di blocco che si desidera aggiornare e fare clic **su Modifica** **nella** pagina del riquadro a comparsa Comunicazione depositario.

3. Nella procedura **guidata Modifica** comunicazione fare clic **su Definisci** contenuto portale nel riquadro sinistro della procedura guidata e aggiornare il contenuto dell'avviso.

4. Fare clic su **Salva**.

L'avviso di riemissione verrà inviato a tutti i custodi assegnati alla notifica di blocco legale. Inoltre, se l'avviso Promemoria o Escalation è abilitato, i flussi di lavoro per questi tipi di avvisi verranno riavviati.

## <a name="update-legal-hold-notifications-and-settings"></a>Aggiornare le impostazioni e le notifiche di blocco legale

Quando si aggiornano il contenuto o le impostazioni dell'avviso Rilascio, Rilascio, Riemissione, Promemoria o Escalation, queste modifiche verranno applicate a tutte le comunicazioni future generate dal flusso di lavoro.

## <a name="more-information"></a>Ulteriori informazioni

- [Aggiungere responsabili a un caso](add-custodians-to-case.md)

- [Creare un avviso di blocco legale](create-hold-notification.md)

- [Confermare la ricezione di una notifica di blocco](acknowledge-hold-notification.md)
