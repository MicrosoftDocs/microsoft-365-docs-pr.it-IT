---
title: Abilitare l'archiviazione illimitata in Office 365-Guida per gli amministratori
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/29/2018
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
description: "Per gli amministratori: informazioni su come abilitare l'archiviazione in espansione automatica in Office 365, che consente agli utenti di disporre di spazio di archiviazione illimitato per le cassette postali di Exchange Online. È possibile abilitare l'archiviazione in espansione automatica per l'intera organizzazione o solo per utenti specifici."
ms.openlocfilehash: d37243c65770ff7bbcce4cbe4cfd593b68b7a869
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "41593207"
---
# <a name="enable-unlimited-archiving-in-office-365--admin-help"></a>Abilitare l'archiviazione illimitata in Office 365-Guida per gli amministratori

È possibile utilizzare la funzionalità di archiviazione per l'espansione automatica di Exchange online in Office 365 per abilitare lo spazio di archiviazione illimitato per le cassette postali di archiviazione. Quando l'archiviazione in espansione automatica è attivata, lo spazio di archiviazione aggiuntivo viene aggiunto automaticamente alla cassetta postale di archiviazione di un utente quando si avvicina al limite di archiviazione. Il risultato è una capacità illimitata di archiviazione delle cassette postali. È possibile abilitare l'archiviazione in espansione automatica per tutti gli utenti dell'organizzazione o solo per i clienti specifici. Per ulteriori informazioni sull'archiviazione automatica, vedere [Overview of Unlimited Archiving in Office 365](unlimited-archiving.md).

## <a name="before-you-begin"></a>Prima di iniziare

- È necessario essere un amministratore globale dell'organizzazione di Office 365 o un membro del gruppo di ruoli Gestione organizzazione nell'organizzazione di Exchange Online per abilitare l'archiviazione in espansione automatica per l'intera organizzazione o per utenti specifici. In alternativa, è necessario essere membri di un gruppo di ruoli a cui è stato assegnato il ruolo destinatari di posta elettronica per abilitare l'archiviazione in espansione automatica per utenti specifici.
    
- La cassetta postale di archiviazione di un utente deve essere abilitata prima di poter abilitare l'archiviazione automatica. A un utente deve essere assegnata una licenza di Exchange Online piano 2 per abilitare la cassetta postale di archiviazione. Se a un utente è assegnata una licenza di Exchange Online piano 1, è necessario assegnare loro una licenza di archiviazione Exchange Online separata per abilitare la cassetta postale di archivio. Vedere [abilitare le cassette postali di archiviazione nel centro sicurezza & Compliance](enable-archive-mailboxes.md).
    
- È inoltre possibile utilizzare PowerShell per abilitare le cassette postali di archiviazione. Vedere la sezione [ulteriori informazioni](#more-information) per un esempio di comando di PowerShell che è possibile utilizzare per abilitare le cassette postali di archiviazione per tutti gli utenti dell'organizzazione. 
    
- L'espansione automatica dell'archivio supporta anche le cassette postali condivise. Per abilitare l'archivio per una cassetta postale condivisa, è necessaria una licenza di Exchange Online piano 2 o una licenza di Exchange Online piano 1 con una licenza di archiviazione Exchange Online.
    
- Non è possibile utilizzare l'interfaccia di amministrazione di Exchange o il Centro sicurezza & Compliance per abilitare l'archiviazione in espansione automatica. È necessario utilizzare Exchange Online PowerShell. Per connettersi a un'organizzazione di Exchange Online utilizzando PowerShell remoto, vedere [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).
    
  
## <a name="enable-auto-expanding-archiving-for-your-entire-organization"></a>Abilitare l'archiviazione in espansione automatica per l'intera organizzazione

È possibile abilitare l'archiviazione in espansione automatica per l'intera organizzazione. Dopo averlo attivato, l'archiviazione con espansione automatica sarà abilitata per le cassette postali degli utenti esistenti e per le nuove cassette postali degli utenti create. Quando si creano cassette postali utente, assicurarsi di abilitare la cassetta postale di archiviazione principale dell'utente in modo che la funzionalità di archiviazione in espansione automatica funzioni per la nuova cassetta postale utente.
  
1. [Connettersi a PowerShell per Exchange Online](https://go.microsoft.com/fwlink/p/?linkid=396554)
    
2. Eseguire il seguente comando in PowerShell di Exchange Online per abilitare l'archiviazione in espansione automatica per l'intera organizzazione.

    ```powershell
    Set-OrganizationConfig -AutoExpandingArchive
    ```

## <a name="enable-auto-expanding-archiving-for-specific-users"></a>Abilitazione dell'archiviazione con espansione automatica per utenti specifici

Invece di abilitare l'archiviazione automatica per tutti gli utenti dell'organizzazione, è possibile abilitarla solo per utenti specifici. È possibile eseguire questa operazione perché solo alcuni utenti potrebbero avere la necessità di disporre di una capacità di archiviazione di grandi dimensioni.
  
Quando si Abilita l'archiviazione in espansione automatica per un utente specifico e la cassetta postale dell'utente in attesa o assegnata a un criterio di conservazione di Office 365, vengono apportate le due modifiche seguenti relative alle configurazioni:
  
- La quota di archiviazione per la cassetta postale di archivio principale dell'utente è aumentata di 10 GB (da 100 GB a 110 GB). La quota di avviso per l'archiviazione è aumentata anche di 10 GB (da 90 GB a 100 GB).
    
- La quota di archiviazione per la cartella elementi ripristinabili nella cassetta postale principale dell'utente è aumentata di 10 GB (anche da 100 GB a 110 GB). La quota di avviso per gli elementi ripristinabili è aumentata anche di 10 GB (da 90 GB a 100 GB). Tali modifiche sono applicabili solo se la cassetta postale è in attesa o assegnata a un criterio di conservazione di Office 365.
    
Questo spazio aggiuntivo viene aggiunto per evitare eventuali problemi di archiviazione che possono verificarsi prima del provisioning dell'archivio con espansione automatica. Lo spazio di archiviazione aggiuntivo *non viene* aggiunto quando si attiva l'archiviazione con espansione automatica per l'intera organizzazione, come descritto nella sezione precedente. 
  
1. [Connettersi a PowerShell per Exchange Online](https://go.microsoft.com/fwlink/p/?linkid=396554)
    
2. Eseguire il seguente comando in PowerShell di Exchange Online per abilitare l'archiviazione in espansione automatica per un utente specifico. Come spiegato in precedenza, la cassetta postale di archiviazione dell'utente (archivio principale) deve essere abilitata prima di poter attivare l'archiviazione in espansione automatica per tale utente.
    
    ```powershell
    Enable-Mailbox <user mailbox> -AutoExpandingArchive
    ```


> [!IMPORTANT]
> In una distribuzione ibrida di Exchange, non è possibile utilizzare il comando **Enable-Mailbox-AutoExpandingArchive** per abilitare l'archiviazione in espansione automatica per un utente specifico la cui cassetta postale principale è in locale e la cassetta postale di archiviazione è basata sul cloud. Per abilitare l'archiviazione in espansione automatica per le cassette postali di archiviazione basate sul cloud in una distribuzione ibrida di Exchange, è necessario eseguire il comando **Set-OrganizationConfig-AutoExpandingArchive** in Exchange Online PowerShell per abilitare l'archiviazione in espansione automatica per l'intera organizzazione. Se le cassette postali primarie e di archiviazione di un utente sono entrambe basate sul cloud, è possibile utilizzare il comando **Enable-Mailbox-AutoExpandingArchive** per abilitare l'archiviazione in espansione automatica per tale utente specifico. 
  
## <a name="verify-that-auto-expanding-archiving-is-enabled"></a>Verificare che l'archiviazione con espansione automatica sia abilitata

Per verificare che l'archiviazione con espansione automatica sia abilitata per l'organizzazione, eseguire il comando seguente in PowerShell di Exchange Online.

```powershell
Get-OrganizationConfig | FL AutoExpandingArchiveEnabled
```

Il valore `True` indica che l'archiviazione con espansione automatica è abilitata per l'organizzazione. 
  
Per verificare che l'archiviazione con espansione automatica sia abilitata per un utente specifico, eseguire il comando seguente in PowerShell di Exchange Online.
  
```powershell
Get-Mailbox <user mailbox> | FL AutoExpandingArchiveEnabled
```

Il valore `True` indica che l'archiviazione con espansione automatica è abilitata per l'utente. 
  
Dopo aver abilitato l'archiviazione automatica, tenere presenti le considerazioni seguenti:
  
- Se si esegue il comando **Set-OrganizationConfig-AutoExpandingArchive** per abilitare l'archiviazione con espansione automatica per la propria organizzazione, non è necessario eseguire **Enable-Mailbox-AutoExpandingArchive** su singole cassette postali. L'esecuzione del cmdlet **Set-OrganizationConfig** per abilitare l'archiviazione in espansione automatica per l'organizzazione non comporta la modifica della proprietà *AutoExpandingArchiveEnabled* nelle `True`cassette postali degli utenti.
    
- Analogamente, i valori per le proprietà delle cassette postali di *ArchiveQuota* e *ArchiveWarningQuota* non vengono modificati quando si Abilita l'archiviazione in espansione automatica. Infatti, quando si Abilita l'archiviazione automatica per una cassetta postale utente e la proprietà *AutoExpandingArchiveEnabled* è impostata su `True`, le proprietà *ArchiveQuota* e *ArchiveWarningQuota* vengono ignorate. Di seguito è riportato un esempio di queste proprietà della cassetta postale dopo che l'archiviazione in espansione automatica è abilitata per la cassetta postale di un utente. 
    
    ![Le proprietà ArchiveQuota e ArchiveWarningQuota vengono ignorate dopo l'abilitazione dell'archiviazione con espansione automatica](media/6a1c1b69-5c4c-4267-aac8-53577667f03e.png)

  
## <a name="more-information"></a>Ulteriori informazioni

- È inoltre possibile utilizzare PowerShell per abilitare le cassette postali di archiviazione. Ad esempio, è possibile eseguire il comando seguente in Exchange Online PowerShell per abilitare le cassette postali di archiviazione per tutti gli utenti la cui cassetta postale di archiviazione non è già abilitata.

    ```powershell
    Get-Mailbox -Filter {ArchiveStatus -Eq "None" -AND RecipientTypeDetails -eq "UserMailbox"} | Enable-Mailbox -Archive
    ```

- Dopo aver attivato l'espansione automatica dell'archiviazione per l'organizzazione o per un utente specifico, una cassetta postale di archiviazione viene convertita in un archivio in espansione automatica quando la cassetta postale di archiviazione (inclusa la cartella elementi ripristinabili) raggiunge 90 GB. Possono essere necessari fino a 30 giorni per il provisioning dello spazio di archiviazione aggiuntivo.
    
- Dopo aver attivato l'archiviazione automatica, non è possibile disattivarla.
    
- L'archiviazione in espansione automatica è supportata per le cassette postali di archiviazione basate sul cloud in una distribuzione ibrida di Exchange per gli utenti che dispongono di una cassetta postale principale locale. Tuttavia, dopo che l'archiviazione in espansione automatica è abilitata per una cassetta postale di archiviazione basata sul cloud, non è possibile disattivare la cassetta postale di archiviazione nell'organizzazione di Exchange locale. L'archiviazione in espansione automatica non è supportata per le cassette postali locali in Exchange Server 2010.
    
- Per un elenco di client di Outlook che gli utenti possono utilizzare per accedere agli elementi nell'area di archiviazione aggiuntiva nella propria cassetta postale di archiviazione, vedere la sezione "requisiti di Outlook per l'accesso agli elementi in un archivio con espansione automatica" in [Overview of Unlimited Archiving in Office 365](unlimited-archiving.md#outlook-requirements-for-accessing-items-in-an-auto-expanded-archive).
    
- Come spiegato in precedenza, 10 GB viene aggiunto alla quota di archiviazione della cassetta postale di archivio principale dell'utente (e alla cartella elementi ripristinabili se la cassetta postale è in attesa) quando si esegue il comando **Enable-Mailbox-AutoExpandingArchive** . Questo fornisce ulteriore spazio di archiviazione fino a quando non viene effettuato il provisioning dell'ambiente di archiviazione automatico (che può richiedere fino a 30 giorni). Questo spazio di archiviazione aggiuntivo non viene aggiunto quando si esegue il **Set-OrganizationConfig-AutoExpandingArchive** per abilitare l'archiviazione in espansione automatica per tutte le cassette postali dell'organizzazione. Se è stata abilitata l'archiviazione automatica per l'intera organizzazione, ma è necessario aggiungere altri 10 GB di spazio di archiviazione per un utente specifico, è possibile eseguire il comando **Enable-Mailbox-AutoExpandingArchive** su tale cassetta postale. Verrà visualizzato un messaggio di errore che indica che l'archiviazione in espansione automatica è già stata abilitata, ma che lo spazio di archiviazione aggiuntivo verrà aggiunto alla cassetta postale. 

- Gli amministratori non possono modificare la quota di archiviazione.

> [!IMPORTANT]
> L'archiviazione in espansione automatica è supportata solo per le cassette postali utilizzate per singoli utenti o per le cassette postali condivise con una frequenza di crescita non superiore a 1 GB al giorno. L'utilizzo dell'inserimento nel journal, delle regole di trasporto o delle regole di inoltro automatico per copiare i messaggi in una cassetta postale di archiviazione ai fini dell'archiviazione non è consentito. Una cassetta postale di archiviazione di un utente è destinata esclusivamente a quell'utente. Microsoft si riserva il diritto di negare l'archiviazione illimitata nei casi in cui la cassetta postale di archiviazione di un utente viene utilizzata per archiviare i dati di archiviazione per altri utenti o in altri casi di utilizzo inappropriato.
