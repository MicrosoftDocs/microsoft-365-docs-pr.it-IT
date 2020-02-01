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
ms.openlocfilehash: dbcddd57fcf2d1471b4a4aa4b715dcae22dbc40c
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "41596193"
---
# <a name="create-a-litigation-hold"></a>Creare un blocco per controversia legale

È possibile inserire una cassetta postale sul blocco per controversia legale per mantenere tutto il contenuto delle cassette postali, inclusi gli elementi eliminati e le versioni originali degli elementi modificati. Quando si posiziona una cassetta postale utente in conservazione per controversia legale, viene conservato anche il contenuto della cassetta postale di archiviazione dell'utente (se abilitata). Quando si crea un'esenzione, è possibile specificare una durata del blocco, denominata anche *blocco basato sul tempo*, in modo che gli elementi eliminati e modificati vengano conservati per un periodo specificato e quindi eliminati definitivamente dalla cassetta postale. In alternativa, è possibile conservare il contenuto a tempo indeterminato (denominato *blocco infinito*) oppure fino a quando non viene rimosso il blocco per controversia legale. Se si specifica un periodo di durata del blocco, viene calcolato a partire dalla data di ricezione di un messaggio o dalla creazione di un elemento della cassetta postale. 
  
Ecco cosa succede quando si crea un blocco per controversia legale.
  
- Gli elementi eliminati in modo definitivo dall'utente vengono conservati nella cartella elementi ripristinabili nella cassetta postale dell'utente per tutta la durata del blocco.
    
- Gli elementi eliminati dalla cartella elementi ripristinabili da parte dell'utente vengono conservati per la durata del blocco.
    
- La quota di archiviazione per la cartella elementi ripristinabili è aumentata da 30 GB a 110 GB.
    
- Gli elementi nelle cassette postali primarie e di archiviazione dell'utente vengono conservati
    
## <a name="before-you-begin"></a>Prima di iniziare

- Per attivare il blocco per controversia legale in una cassetta postale di Exchange Online, deve essere assegnata una licenza di Exchange Online piano 2. Se a una cassetta postale viene assegnata una licenza di Exchange Online piano 1, è necessario assegnarle una licenza di archiviazione Exchange Online separata per inserirla in blocco.
    

## <a name="place-a-mailbox-on-litigation-hold"></a>Blocco per controversia legale di una cassetta postale

Di seguito sono riportati i passaggi per inserire una cassetta postale per controversia legale utilizzando l'interfaccia di amministrazione di Exchange.

1. Accedere a [https://outlook.office.com/ecp](https://outlook.office.com/ecp) e accedere utilizzando l'account di amministratore globale.

2. Fare clic su **destinatari > cassette postali** nel riquadro di spostamento a sinistra.

3. Selezionare la cassetta postale che si desidera inserire nel blocco per controversia legale, quindi fare clic su **modifica**.

4. Nella pagina delle proprietà della cassetta postale, fare clic su **funzionalità cassette postali**.
    
5. In **Blocco per controversia legale: disabilitato**, fare clic su **Abilita** per attivare il blocco per controversia legale nella cassetta postale.
    
6. Nella pagina **blocco per controversia legale** , immettere le informazioni facoltative seguenti: 
    
    - Durata della conservazione per **controversia legale (giorni)** : utilizzare questa casella per creare un blocco basato sul tempo e specificare il periodo di conservazione degli elementi della cassetta postale quando la cassetta postale viene inserita nel blocco per controversia legale. La durata viene calcolata a partire dalla data di ricezione o creazione dell'elemento della cassetta postale. Quando la durata del blocco scade per un elemento specifico, l'elemento non verrà più mantenuto. Se si lascia vuota questa casella, gli elementi vengono conservati a tempo indeterminato o fino a quando non viene rimosso il blocco. Usare un numero di giorni per specificare la durata.
    
    - **Nota** : utilizzare questa casella per informare l'utente che la cassetta postale è in blocco per controversia legale. La nota verrà visualizzata nella pagina informazioni account nella cassetta postale dell'utente se utilizza Outlook 2010 o versione successiva. Per accedere a questa pagina, gli utenti possono fare clic su **file** in Outlook.
    
    - **URL** : utilizzare questa casella per indirizzare l'utente a un sito Web per ulteriori informazioni sul blocco per controversia legale. Questo URL viene visualizzato nella pagina informazioni account nella cassetta postale dell'utente se utilizza Outlook 2010 o versione successiva. Per accedere a questa pagina, gli utenti possono fare clic su **file** in Outlook..

7. Fare clic su **Salva** nella pagina **blocco per controversia legale** , quindi fare clic su **Salva** nella pagina delle proprietà della cassetta postale.

### <a name="create-a-litigation-hold-using-powershell"></a>Creazione di un blocco per controversia legale tramite PowerShell

È inoltre possibile creare un blocco per controversia legale eseguendo il comando seguente in [PowerShell di Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell):

```powershell
Set-Mailbox <username> -LitigationHoldEnabled $true
```

Il comando precedente conserva gli elementi per un periodo di tempo indefinito, perché non viene specificata la durata del blocco. Per creare un blocco basato sul tempo, utilizzare il seguente comando:

```powershell
Set-Mailbox <username> -LitigationHoldEnabled $true -LitigationHoldDuration <number of days>
```

Per altre informazioni, vedere [Set-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox).

## <a name="how-does-litigation-hold-work"></a>Come funziona il blocco per controversia legale?

Nel flusso di lavoro normale degli elementi eliminati, un elemento della cassetta postale viene spostato nella sottocartella Eliminazioni nella cartella elementi ripristinabili quando un utente lo elimina definitivamente (MAIUSC + CANC) oppure lo elimina dalla cartella Posta eliminata. Un criterio di eliminazione (che è un tag di conservazione configurato con un'azione di conservazione Delete) sposta anche gli elementi nella sottocartella Deletions quando scade il periodo di conservazione. Quando un utente elimina un elemento nella cartella elementi ripristinabili o quando il periodo di conservazione dell'elemento eliminato scade per un elemento, viene spostato nella sottocartella Purges nella cartella elementi ripristinabili e contrassegnata per l'eliminazione definitiva. Verrà eliminato da Exchange la volta successiva che la cassetta postale viene elaborata dall'Assistente cartelle gestite (AMF, Managed Folder Assistant).

Quando una cassetta postale viene inserita nella conservazione per controversia legale, gli elementi nella sottocartella Purges vengono conservati per la durata del blocco specificata dal blocco per controversia legale. La durata del blocco viene calcolata a partire dalla data originale di ricezione o creazione di un elemento e viene definito il periodo di conservazione degli elementi nella sottocartella Purges. Quando la durata del blocco scade per un elemento nella sottocartella Purges, l'elemento viene contrassegnato per l'eliminazione definitiva e verrà eliminato da Exchange alla successiva elaborazione della cassetta postale da parte dell'AMF. Se in una cassetta postale viene inserito un blocco indefinito, gli elementi non verranno mai eliminati dalla sottocartella Purges.

La figura seguente mostra le sottocartelle presenti nelle cartelle Elementi ripristinabili e il processo del flusso di lavoro del blocco.

![Ciclo di vita del blocco per controversia legale](media/LitigationHoldLifeCycle.png)

> [!NOTE]
> Se un blocco associato a un caso di eDiscovery è posizionato in una cassetta postale, gli elementi eliminati vengono spostati dalla sottocartella Deletions alla sottocartella DiscoveryHolds e vengono mantenuti fino a quando la cassetta postale non viene rilasciata dal blocco eDiscovery.
  