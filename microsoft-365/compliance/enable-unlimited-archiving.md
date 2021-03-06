---
title: Abilitare l'archiviazione illimitata - Guida per gli amministratori
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
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: e2a789f2-9962-4960-9fd4-a00aa063559e
description: "Per gli amministratori: informazioni su come abilitare l'archiviazione con espansione automatica, che fornisce agli utenti uno spazio di archiviazione illimitato per le Exchange Online cassette postali. È possibile abilitare l'archiviazione con espansione automatica per l'intera organizzazione o solo per utenti specifici."
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ac5661ac43ed9c0f35eba20007f0c4c4406ebf20
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927826"
---
# <a name="enable-unlimited-archiving---admin-help"></a>Abilitare l'archiviazione illimitata - Guida per gli amministratori

È possibile utilizzare la funzionalità di Exchange Online di archiviazione con espansione automatica per abilitare spazio di archiviazione illimitato per le cassette postali di archiviazione. Quando l'archiviazione con espansione automatica è attivata, viene aggiunto automaticamente ulteriore spazio di archiviazione alla cassetta postale di archiviazione di un utente quando si avvicina al limite di archiviazione. Il risultato è una capacità di archiviazione illimitata delle cassette postali. È possibile attivare l'archiviazione con espansione automatica per tutti gli utenti dell'organizzazione o solo per utenti specifici. Per ulteriori informazioni sull'espansione automatica dell'archiviazione, vedere [Overview of unlimited archiving in Office 365](unlimited-archiving.md).

## <a name="before-you-enable-auto-expanding-archiving"></a>Prima di abilitare l'archiviazione con espansione automatica

- È necessario essere un amministratore globale dell'organizzazione o un membro del gruppo di ruoli Gestione organizzazione nell'organizzazione di Exchange Online per abilitare l'archiviazione con espansione automatica per l'intera organizzazione o per utenti specifici. In alternativa, è necessario essere membri di un gruppo di ruoli a cui è assegnato il ruolo Destinatari di posta per abilitare l'espansione automatica dell'archiviazione per utenti specifici.

- Prima di poter abilitare l'espansione automatica dell'archiviazione, è necessario abilitare la cassetta postale di archiviazione di un utente. A un utente deve essere assegnata una licenza Exchange Online Piano 2 per abilitare la cassetta postale di archiviazione. Se a un utente viene assegnata una licenza Exchange Online Piano 1, è necessario assegnargli una licenza di Archiviazione Exchange Online separata per abilitare la cassetta postale di archiviazione. Vedere [Enable archive mailboxes in the Security & Compliance Center.](enable-archive-mailboxes.md)

- È inoltre possibile utilizzare PowerShell per abilitare le cassette postali di archiviazione. Vedere la [sezione Ulteriori informazioni](#more-information) per un esempio del comando PowerShell che è possibile utilizzare per abilitare le cassette postali di archiviazione per tutti gli utenti dell'organizzazione.

- L'espansione automatica dell'archivio supporta anche le cassette postali condivise. Per abilitare l'archivio per una cassetta postale condivisa, è necessaria una licenza di Exchange Online Piano 2 o una licenza di Exchange Online Piano 1 con una licenza Archiviazione Exchange Online condivisa.

- L'espansione automatica dell'archiviazione impedisce il ripristino o il ripristino di una cassetta postale [inattiva.](inactive-mailboxes-in-office-365.md#what-are-inactive-mailboxes) Ciò significa che se si abilita l'archiviazione con espansione automatica per una cassetta postale e la cassetta postale viene resa inattiva in un secondo momento, non sarà possibile ripristinare la cassetta postale [inattiva](recover-an-inactive-mailbox.md) (converterla in una cassetta postale attiva) o ripristinarla [(unendo](restore-an-inactive-mailbox.md) il contenuto a una cassetta postale esistente). Se l'archiviazione con espansione automatica è abilitata in una cassetta postale inattiva, l'unico modo per recuperare i dati è utilizzare lo strumento Ricerca contenuto nel Centro conformità di Microsoft 365 per esportare i dati dalla cassetta postale e importare in un'altra cassetta postale. Per ulteriori informazioni, vedere la sezione "Cassette postali inattive e archivi con espansione automatica" in [Overview of inactive mailboxes](inactive-mailboxes-in-office-365.md#inactive-mailboxes-and-auto-expanding-archives).

- Non è possibile utilizzare l'interfaccia Exchange o il Centro sicurezza & conformità per abilitare l'archiviazione con espansione automatica. È necessario utilizzare Exchange Online PowerShell. Per connettersi all'Exchange Online tramite PowerShell remoto, vedere [Connessione to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

## <a name="enable-auto-expanding-archiving-for-your-entire-organization"></a>Abilitare l'archiviazione con espansione automatica per l'intera organizzazione

È possibile abilitare l'archiviazione con espansione automatica per l'intera organizzazione. Dopo l'attivazione, l'archiviazione con espansione automatica verrà abilitata per le cassette postali degli utenti esistenti e per le nuove cassette postali utente create. Quando si creano cassette postali utente, assicurarsi di abilitare la cassetta postale di archiviazione principale dell'utente in modo che la funzionalità di archiviazione con espansione automatica funzioni per la nuova cassetta postale utente.
  
1. [Connettersi a PowerShell di Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell)

2. Eseguire il comando seguente in Exchange Online PowerShell per abilitare l'espansione automatica dell'archiviazione per l'intera organizzazione.

    ```powershell
    Set-OrganizationConfig -AutoExpandingArchive
    ```

## <a name="enable-auto-expanding-archiving-for-specific-users"></a>Abilitare l'archiviazione con espansione automatica per utenti specifici

Invece di abilitare l'archiviazione con espansione automatica per ogni utente dell'organizzazione, è possibile abilitarla solo per utenti specifici. È possibile eseguire questa operazione perché solo alcuni utenti potrebbero avere la necessità di una capacità di archiviazione di archiviazione di grandi dimensioni.
  
Quando si abilita l'archiviazione con espansione automatica per un utente specifico e la cassetta postale dell'utente in attesa o assegnata a un criterio di conservazione, vengono apportate le due modifiche seguenti alle configurazioni:
  
- La quota di archiviazione per la cassetta postale di archiviazione principale dell'utente viene aumentata di 10 GB (da 100 GB a 110 GB). Anche la quota di avviso di archiviazione viene aumentata di 10 GB (da 90 GB a 100 GB).

- La quota di archiviazione per la cartella Elementi ripristinabili nella cassetta postale principale dell'utente viene aumentata di 10 GB (anche da 100 GB a 110 GB). La quota di avviso degli elementi ripristinabili viene inoltre aumentata di 10 GB (da 90 GB a 100 GB). Queste modifiche sono applicabili solo se la cassetta postale è in attesa o assegnata a un criterio di conservazione.

Questo spazio aggiuntivo viene aggiunto per evitare eventuali problemi di archiviazione che possono verificarsi prima del provisioning dell'archivio con espansione automatica. Lo spazio di  *archiviazione aggiuntivo non viene*  aggiunto quando si abilita l'archiviazione con espansione automatica per l'intera organizzazione, come descritto nella sezione precedente.
  
1. [Connettersi a PowerShell di Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell)

2. Eseguire il comando seguente in Exchange Online PowerShell per abilitare l'archiviazione con espansione automatica per un utente specifico. Come spiegato in precedenza, la cassetta postale di archiviazione dell'utente (archivio principale) deve essere abilitata prima di poter attivare l'espansione automatica dell'archiviazione per tale utente.

    ```powershell
    Enable-Mailbox <user mailbox> -AutoExpandingArchive
    ```

> [!IMPORTANT]
> In una distribuzione ibrida Exchange, non è possibile utilizzare il comando **Enable-Mailbox -AutoExpandingArchive** per abilitare l'archiviazione con espansione automatica per un utente specifico la cui cassetta postale principale è locale e la cui cassetta postale di archiviazione è basata sul cloud. Per abilitare l'archiviazione con espansione automatica per le cassette postali di archiviazione basate sul cloud in una distribuzione ibrida di Exchange, è necessario eseguire il comando **Set-OrganizationConfig -AutoExpandingArchive** in Exchange Online PowerShell per abilitare l'archiviazione con espansione automatica per l'intera organizzazione. Se le cassette postali principale e di archiviazione di un utente sono entrambe basate sul cloud, è possibile utilizzare il comando **Enable-Mailbox -AutoExpandingArchive** per abilitare l'archiviazione con espansione automatica per tale utente specifico.
  
## <a name="verify-that-auto-expanding-archiving-is-enabled"></a>Verificare che l'archiviazione con espansione automatica sia abilitata

Per verificare che l'archiviazione con espansione automatica sia abilitata per l'organizzazione, eseguire il comando seguente in Exchange Online PowerShell.

```powershell
Get-OrganizationConfig | FL AutoExpandingArchiveEnabled
```

Il valore di  `True` indica che l'archiviazione con espansione automatica è abilitata per l'organizzazione. 
  
Per verificare che l'archiviazione con espansione automatica sia abilitata per un utente specifico, eseguire il comando seguente in Exchange Online PowerShell.
  
```powershell
Get-Mailbox <user mailbox> | FL AutoExpandingArchiveEnabled
```

Il valore di  `True` indica che l'archiviazione con espansione automatica è abilitata per l'utente.
  
Per determinare se l'archiviazione con espansione automatica è abilitata per le cassette postali inattive, eseguire il comando seguente in Exchange Online PowerShell.
  
```powershell
Get-Mailbox -InactiveMailboxOnly | FL UserPrincipalName,AutoExpandingArchiveEnabled
```

Il valore di  `True` indica che l'archiviazione con espansione automatica è abilitata per la cassetta postale inattiva. Il valore di `False` indica che l'archiviazione con espansione automatica non è abilitata.

Dopo aver abilitato l'archiviazione con espansione automatica, tenere presente quanto segue:
  
- Se si esegue il comando **Set-OrganizationConfig -AutoExpandingArchive** per abilitare l'archiviazione con espansione automatica per l'organizzazione, non è necessario eseguire **Enable-Mailbox -AutoExpandingArchive** sulle singole cassette postali. L'esecuzione del cmdlet **Set-OrganizationConfig** per abilitare l'archiviazione con espansione automatica per l'organizzazione non modifica la  *proprietà AutoExpandingArchiveEnabled*  nelle cassette postali degli utenti su `True` .

- Analogamente, i valori per le proprietà delle cassette postali  *ArchiveQuota*  e  *ArchiveWarningQuota*  non vengono modificati quando si abilita l'espansione automatica dell'archiviazione. Infatti, quando si abilita l'archiviazione con espansione automatica per una cassetta postale utente e la  *proprietà AutoExpandingArchiveEnabled*  è impostata su , le proprietà  `True`  *ArchiveQuota*  e  *ArchiveWarningQuota*  vengono ignorate. Ecco un esempio di queste proprietà della cassetta postale dopo l'a espansione automatica dell'archiviazione è abilitata per la cassetta postale di un utente. 

    ![Le proprietà ArchiveQuota e ArchiveWarningQuota vengono ignorate dopo aver abilitato l'espansione automatica dell'archiviazione](../media/6a1c1b69-5c4c-4267-aac8-53577667f03e.png)

## <a name="more-information"></a>Ulteriori informazioni

- È inoltre possibile utilizzare PowerShell per abilitare le cassette postali di archiviazione. Ad esempio, è possibile eseguire il comando seguente in Exchange Online PowerShell per abilitare le cassette postali di archiviazione per tutti gli utenti la cui cassetta postale di archiviazione non è già abilitata.

    ```powershell
    Get-Mailbox -Filter {ArchiveStatus -Eq "None" -AND RecipientTypeDetails -eq "UserMailbox"} | Enable-Mailbox -Archive
    ```

- Dopo aver abilitato l'archiviazione con espansione automatica per l'organizzazione o per un utente specifico, una cassetta postale di archiviazione viene convertita in un archivio con espansione automatica quando la cassetta postale di archiviazione (inclusa la cartella Elementi ripristinabili) raggiunge i 90 GB. Il provisioning dello spazio di archiviazione aggiuntivo può richiedere fino a 30 giorni.

- Dopo aver attivato l'espansione automatica dell'archiviazione, non è possibile disattivarla. Inoltre, gli amministratori non possono modificare la quota di archiviazione per l'espansione automatica dell'archiviazione.

- L'archiviazione con espansione automatica è supportata per le cassette postali di archiviazione basate su cloud in una distribuzione ibrida Exchange per gli utenti che dispongono di una cassetta postale principale locale. Tuttavia, dopo aver abilitato l'archiviazione con espansione automatica per una cassetta postale di archiviazione basata su cloud, non è possibile eseguire l'off-board della cassetta postale di archiviazione nell'organizzazione locale Exchange locale. L'archiviazione con espansione automatica non è supportata per le cassette postali locali in qualsiasi versione di Exchange Server.

- Per un elenco dei client Outlook che gli utenti possono utilizzare per accedere agli elementi nell'area di archiviazione aggiuntiva nella cassetta postale di archiviazione, vedere la sezione "Requisiti di Outlook per l'accesso agli elementi in un archivio espanso automaticamente" in [Panoramica](unlimited-archiving.md#outlook-requirements-for-accessing-items-in-an-auto-expanded-archive)dell'archiviazione illimitata.

- Come spiegato in precedenza, vengono aggiunti 10 GB alla quota di archiviazione della cassetta postale di archiviazione principale dell'utente (e alla cartella Elementi ripristinabili se la cassetta postale è in attesa) quando si esegue il comando **Enable-Mailbox -AutoExpandingArchive.** Ciò fornisce ulteriore spazio di archiviazione fino al provisioning dello spazio di archiviazione espanso automaticamente (che può richiedere fino a 30 giorni). Questo ulteriore spazio di archiviazione non viene aggiunto quando si esegue **Set-OrganizationConfig -AutoExpandingArchive** per abilitare l'archiviazione con espansione automatica per tutte le cassette postali dell'organizzazione. Se è stata abilitata l'archiviazione con espansione automatica per l'intera organizzazione, ma è necessario aggiungere altri 10 GB di spazio di archiviazione per un utente specifico, è possibile eseguire il comando **Enable-Mailbox -AutoExpandingArchive** su tale cassetta postale. Verrà visualizzato un errore che indica che l'archiviazione con espansione automatica è già stata abilitata, ma lo spazio di archiviazione aggiuntivo verrà aggiunto alla cassetta postale.

> [!IMPORTANT]
> L'archiviazione con espansione automatica è supportata solo per le cassette postali utilizzate per singoli utenti o cassette postali condivise con un tasso di crescita che non supera 1 GB al giorno. Non è consentito utilizzare l'inserimento nel journal, le regole di trasporto o le regole di inoltro automatico per copiare i messaggi in una cassetta postale di archiviazione ai fini dell'archiviazione. Una cassetta postale di archiviazione di un utente è destinata esclusivamente a quell'utente. Microsoft si riserva il diritto di non consentire uno spazio di archiviazione illimitato nei casi in cui una cassetta postale di archiviazione dell'utente sia utilizzata per l'archiviazione di dati di altri utenti, o in altri casi di usi inappropriati.