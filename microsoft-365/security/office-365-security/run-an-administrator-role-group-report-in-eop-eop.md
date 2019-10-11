---
title: 'Eseguire un report di un gruppo di ruoli amministratore in Exchange Online Protection '
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 23b47b57-0eec-46a3-a03b-366ea014ab31
description: Gli amministratori possono ottenere informazioni su come eseguire un rapporto del gruppo di ruoli di amministratore in Exchange Online Protection (EOP). Questo rapporto si registra quando un amministratore aggiunge o rimuove membri dai gruppi di ruoli di amministratore, Microsoft Exchange Online Protection (EOP) registra ogni occorrenza.
ms.openlocfilehash: 59557f6fab2281cd36569b40afcf3e0225bd9347
ms.sourcegitcommit: cbf117a4cd92a907115c9f10752f3c557361e586
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/10/2019
ms.locfileid: "37441403"
---
# <a name="run-an-administrator-role-group-report-in-eop"></a>Eseguire un report di un gruppo di ruoli amministratore in Exchange Online Protection

 Quando un amministratore aggiunge o rimuove membri dai gruppi di ruoli di amministratore, Exchange Online Protection (EOP) registra ogni occorrenza. Quando si esegue un rapporto del gruppo di ruoli di amministratore nell'interfaccia di amministrazione di Exchange, le voci vengono visualizzate come risultati della ricerca e includono i gruppi di ruoli interessati, che hanno modificato l'appartenenza al gruppo di ruoli e quando e quali sono stati apportati gli aggiornamenti di appartenenza. Utilizzare questo rapporto per monitorare le modifiche apportate alle autorizzazioni amministrative assegnate agli utenti dell'organizzazione.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare

- Tempo stimato per il completamento: 2 minuti

- Per aprire l'interfaccia di amministrazione di Exchange, vedere interfaccia [di amministrazione di Exchange in Exchange Online Protection](exchange-admin-center-in-exchange-online-protection-eop.md).

- Per eseguire queste procedure, è necessario disporre delle autorizzazioni appropriate. Per sapere quali autorizzazioni sono necessarie, vedere "Rapporti" dell'argomento [Autorizzazioni di funzionalità in EOP](feature-permissions-in-eop.md).

- Per informazioni sui tasti di scelta rapida che possono essere applicati alle procedure descritte in questo argomento, vedere tasti [di scelta rapida per l'interfaccia di amministrazione di Exchange in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).

> [!TIP]
> Problemi? Chiedere assistenza nel forum di [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) .

## <a name="use-the-eac-to-run-an-administrator-role-group-report"></a>Esecuzione del report del gruppo di ruoli amministratore tramite EAC

Eseguire il rapporto del gruppo di ruoli amministratore per trovare le modifiche ai gruppi di ruoli di gestione nell'organizzazione in un determinato intervallo di tempo.

1. Nell'interfaccia di amministrazione di Exchange selezionare **Gestione della conformità** \> **Controllo**, quindi fare clic su **Esegui il rapporto di un gruppo di ruoli amministratore**.

2. Scegliere **Data di inizio** e **Data di fine**. Per impostazione predefinita, il rapporto cerca le modifiche apportate ai gruppi di ruoli amministratore nelle ultime due settimane.

3. Per visualizzare le modifiche per un gruppo di ruoli specifico, fare clic su **Seleziona gruppi di ruoli**. Selezionare il gruppo o i gruppi di ruoli nella finestra di dialogo successiva, quindi fare clic su **OK**. È inoltre possibile lasciare il campo vuoto per trovare tutti i gruppi di ruolo modificati.

4. Fare clic su **Cerca**.

Se utilizzando i criteri specificati vengono trovate delle modifiche, queste verranno visualizzate nel riquadro dei risultati. Fare clic su un gruppo di ruoli nei risultati della ricerca per visualizzare le modifiche nel riquadro dei dettagli.

## <a name="how-do-you-know-this-worked"></a>Come verificare se l'operazione ha avuto esito positivo

Se è stato eseguito correttamente un report dei gruppi di ruoli di amministratore, i gruppi di ruoli modificati entro l'intervallo di date vengono visualizzati nel riquadro dei risultati della ricerca. Se non è presente alcun risultato, non è stata eseguita alcuna modifica entro l'intervallo di date specificato. Se è prevista la presenza di risultati, modificare l'intervallo di date, quindi eseguire di nuovo il report.

## <a name="monitor-changes-to-role-group-membership"></a>Monitorare le modifiche apportate all'appartenenza ai gruppi di ruoli

Quando si aggiungono o si rimuovono i membri di un gruppo di ruoli, nei risultati di ricerca visualizzati nel riquadro dei dettagli viene indicato che l'appartenenza al gruppo di ruoli è stata aggiornata e vengono elencati i membri correnti. I risultati non dichiarano in modo esplicito quale utente è stato aggiunto o rimosso.

Per determinare se un utente è stato aggiunto o rimosso, è necessario confrontare due voci separate del rapporto. Ad esempio, osservare le voci di registro seguenti per il gruppo di ruoli **HelpDesk**:

> 1/27/2018 4:43 PM <br> Amministratore <br> Membri aggiornati: Administrator;annb,florencef;pilarp <br> 2/06/2018 10:09 AM <br> Amministratore <br> Membri aggiornati: Administrator;annb;florencef;pilarp;tonip <br> 2/19/2018 2:12 PM <br> Amministratore <br> Membri aggiornati: Administrator;annb;florencef;tonip

In questo esempio, l'account utente Amministratore ha apportato le modifiche seguenti:

- Il 2/06/2018, hanno aggiunto l'utente tonip.

- Il 2/19/2018, hanno rimosso l'utente pilarp.
