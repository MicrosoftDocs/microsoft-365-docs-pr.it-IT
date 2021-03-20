---
title: Creare un blocco per controversia legale
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 3/13/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: MET150
ms.assetid: 39db1659-0b12-4243-a21c-2614512dcb44
description: Informazioni su come inserire una cassetta postale in blocco per controversia legale, conservando tutto il contenuto della cassetta postale durante un'indagine.
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: 046ee6fdc7c42026b1a69805883175982e3100b7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50908400"
---
# <a name="create-a-litigation-hold"></a>Creare un blocco per controversia legale

È possibile impostare una cassetta postale sul blocco per controversia legale per conservare tutto il contenuto della cassetta postale, inclusi gli elementi eliminati e le versioni originali degli elementi modificati. Quando si attiva il blocco per controversia legale per una cassetta postale utente, viene conservato anche il contenuto nella cassetta postale di archiviazione dell'utente (se abilitata). Quando si crea un'esenzione, è possibile specificare una durata del blocco (detta anche conservazione basata sul *tempo)* in modo che gli elementi eliminati e modificati siano conservati per un periodo specificato e quindi eliminati definitivamente dalla cassetta postale. In alternativa, è possibile conservare il contenuto a tempo indeterminato (denominato blocco *infinito)* o fino a quando non viene rimossa la conservazione per controversia legale. Se si specifica un periodo di durata del blocco, viene calcolato a partire dalla data di ricezione di un messaggio o dalla creazione di un elemento della cassetta postale. 
  
Ecco cosa accade quando si crea un blocco per controversia legale.
  
- Gli elementi eliminati definitivamente dall'utente vengono conservati nella cartella Elementi ripristinabili nella cassetta postale dell'utente per tutta la durata del blocco.
    
- Gli elementi eliminati dalla cartella Elementi ripristinabili dall'utente vengono conservati per tutta la durata del blocco.
    
- La quota di archiviazione per la cartella Elementi ripristinabili è aumentata da 30 GB a 110 GB.
    
- Gli elementi nelle cassette postali principali e di archiviazione dell'utente vengono conservati
    
## <a name="assign-an-exchange-online-plan-2-license"></a>Assegnare una licenza di Exchange Online Piano 2

- Per impostare una cassetta postale di Exchange Online sul blocco per controversia legale, è necessario assegnare una licenza di Exchange Online Piano 2. Se a una cassetta postale viene assegnata una licenza di Exchange Online Piano 1, è necessario assegnarle una licenza Archiviazione Exchange Online separata per metterla in attesa.
    

## <a name="place-a-mailbox-on-litigation-hold"></a>Blocco per controversia legale di una cassetta postale

Ecco i passaggi per inserire una cassetta postale in conservazione per controversia legale utilizzando l'interfaccia di amministrazione di Exchange.

1. Accedere a [https://outlook.office.com/ecp](https://outlook.office.com/ecp) e accedere utilizzando l'account amministratore globale.

2. Fare **clic su > cassette** postali nel riquadro di spostamento sinistro.

3. Selezionare la cassetta postale che si desidera inserire nel blocco per controversia legale e quindi fare clic su **Modifica**.

4. Nella pagina delle proprietà della cassetta postale, fare clic su **Funzionalità cassetta postale**.
    
5. In **Blocco per controversia legale: disabilitato**, fare clic su **Abilita** per attivare il blocco per controversia legale nella cassetta postale.
    
6. Nella pagina **Conservazione per controversia** legale immettere le informazioni facoltative seguenti: 
    
    - Durata conservazione per controversia **legale (giorni)** - Utilizzare questa casella per creare un blocco basato sul tempo e specificare per quanto tempo gli elementi della cassetta postale vengono mantenuti quando la cassetta postale viene messa in conservazione per controversia legale. La durata viene calcolata a partire dalla data di ricezione o creazione dell'elemento della cassetta postale. Quando la durata del blocco scade per un elemento specifico, tale elemento non verrà più conservato. Se si lascia vuota questa casella, gli elementi vengono mantenuti per un periodo indefinito o fino a quando non viene rimossa l'esenzione. Usare un numero di giorni per specificare la durata.
    
    - **Nota:** utilizzare questa casella per informare l'utente che la cassetta postale è in attesa per controversia legale. La nota verrà visualizzata nella pagina Informazioni account nella cassetta postale dell'utente se utilizza Outlook 2010 o versione successiva. Per accedere a questa pagina, gli utenti possono fare **clic su File** in Outlook.
    
    - **URL:** utilizzare questa casella per indirizzare l'utente a un sito Web per ulteriori informazioni sulla conservazione per controversia legale. Questo URL viene visualizzato nella pagina Informazioni account nella cassetta postale dell'utente se utilizza Outlook 2010 o versione successiva. Per accedere a questa pagina, gli utenti possono fare **clic su File** in Outlook.

7. Fare **clic su Salva** nella pagina Conservazione **per** controversia legale, quindi fare clic su **Salva** nella pagina delle proprietà della cassetta postale.

### <a name="create-a-litigation-hold-using-powershell"></a>Creare un blocco per controversia legale con PowerShell

È inoltre possibile creare un blocco per controversia legale eseguendo il comando seguente in [PowerShell di Exchange Online:](/powershell/exchange/connect-to-exchange-online-powershell)

```powershell
Set-Mailbox <username> -LitigationHoldEnabled $true
```

Il comando precedente mantiene gli elementi a tempo indeterminato perché la durata del blocco non è specificata. Per creare un'esenzione basata sul tempo, utilizzare il comando seguente:

```powershell
Set-Mailbox <username> -LitigationHoldEnabled $true -LitigationHoldDuration <number of days>
```

Per altre informazioni, vedere [Set-Mailbox](/powershell/module/exchange/set-mailbox).

## <a name="how-does-litigation-hold-work"></a>Come funziona il blocco per controversia legale?

Nel normale flusso di lavoro degli elementi eliminati, un elemento della cassetta postale viene spostato nella sottocartella Eliminazioni nella cartella Elementi ripristinabili quando un utente lo elimina definitivamente (MAIUSC + CANC) o lo elimina dalla cartella Posta eliminata. Un criterio di eliminazione (che è un tag di conservazione configurato con un'azione di conservazione Elimina) sposta anche gli elementi nella sottocartella Eliminazioni alla scadenza del periodo di conservazione. Quando un utente elimina un elemento nella cartella Elementi ripristinabili o quando scade il periodo di conservazione degli elementi eliminati per un elemento, viene spostato nella sottocartella Elimina nella cartella Elementi ripristinabili e contrassegnato per l'eliminazione definitiva. Verrà eliminata da Exchange la volta successiva che la cassetta postale viene elaborata dall'Assistente cartelle gestite (MFA).

Quando una cassetta postale viene messa in conservazione per controversia legale, gli elementi nella sottocartella Purges vengono mantenuti per la durata del blocco specificata dalla conservazione per controversia legale. La durata del blocco viene calcolata a partire dalla data originale in cui un elemento è stato ricevuto o creato e definisce per quanto tempo vengono mantenuti gli elementi nella sottocartella Ripuliture. Quando la durata del blocco scade per un elemento nella sottocartella Ripuliture, l'elemento viene contrassegnato per l'eliminazione definitiva e verrà eliminato da Exchange alla successiva elaborazione della cassetta postale da parte dell'MFA. Se viene impostata una conservazione indefinita su una cassetta postale, gli elementi non verranno mai eliminati dalla sottocartella Ripuliture.

La figura seguente mostra le sottocartelle presenti nelle cartelle Elementi ripristinabili e il processo del flusso di lavoro del blocco.

![Ciclo di vita del blocco per controversia legale](../media/LitigationHoldLifeCycle.png)

> [!NOTE]
> Se una conservazione associata a un caso di eDiscovery viene inserita in una cassetta postale, gli elementi eliminati vengono spostati dalla sottocartella Eliminazioni alla sottocartella DiscoveryHolds e vengono mantenuti fino a quando la cassetta postale non viene rilasciata dal blocco di eDiscovery.
