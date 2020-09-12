---
title: Migrazioni delle cassette postali di Microsoft 365
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: In questo articolo è incluso un breve riepilogo delle migrazioni delle cassette postali di Microsoft 365 e un elenco dei cmdlet utilizzati per le migrazioni.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 63080643e4994d6b16e77298907725a827997cef
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/12/2020
ms.locfileid: "47546799"
---
# <a name="microsoft-365-mailbox-migrations"></a><span data-ttu-id="4d340-103">Migrazioni delle cassette postali di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4d340-103">Microsoft 365 mailbox migrations</span></span>

<span data-ttu-id="4d340-104">Con una distribuzione ibrida basata su Exchange, i clienti possono scegliere di spostare le cassette postali di Exchange locali in un'organizzazione di [Exchange Online](https://docs.microsoft.com/Exchange/exchange-online) o di spostare le cassette postali di Exchange online in un'organizzazione di [Exchange locale](https://docs.microsoft.com/Exchange/exchange-server) .</span><span class="sxs-lookup"><span data-stu-id="4d340-104">With an Exchange-based hybrid deployment, customers can choose to either move on-premises Exchange mailboxes to an [Exchange Online](https://docs.microsoft.com/Exchange/exchange-online) organization or move Exchange Online mailboxes to an [Exchange on-premises](https://docs.microsoft.com/Exchange/exchange-server) organization.</span></span> <span data-ttu-id="4d340-105">Quando si spostano le cassette postali tra organizzazioni locali e di Exchange Online, vengono utilizzati i batch di migrazione.</span><span class="sxs-lookup"><span data-stu-id="4d340-105">Migration batches are used when moving mailboxes between on-premises and Exchange Online organizations.</span></span>

<span data-ttu-id="4d340-106">I clienti possono esaminare le statistiche e altre informazioni sulle migrazioni delle cassette postali con i cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="4d340-106">Customers can review statistics and other information about mailbox migrations with the following cmdlets:</span></span>

- <span data-ttu-id="4d340-107">[Get-MoveRequestStatistics](https://docs.microsoft.com/powershell/module/exchange/get-moverequeststatistics): fornisce statistiche predefinite per una cassetta postale utente, che include lo stato, la dimensione della cassetta postale, la dimensione della cassetta postale di archiviazione e la percentuale di completamento.</span><span class="sxs-lookup"><span data-stu-id="4d340-107">[Get-MoveRequestStatistics](https://docs.microsoft.com/powershell/module/exchange/get-moverequeststatistics): Provides default statistics for a user mailbox, which includes the status, mailbox size, archive mailbox size, and percentage complete.</span></span>
- <span data-ttu-id="4d340-108">[Get-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Get-Mailbox
): fornisce un elenco riepilogativo degli oggetti e degli attributi delle cassette postali nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="4d340-108">[Get-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Get-Mailbox
): Provides a summary list of mailbox objects and attributes in the organization.</span></span>
- <span data-ttu-id="4d340-109">[Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/get-recipient): fornisce un elenco di oggetti esistenti abilitati alla posta elettronica, quali cassette postali, utenti di posta elettronica, contatti e gruppi di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="4d340-109">[Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/get-recipient): Provides a list of existing mail-enabled objects such as mailboxes, mail users, contacts, and distribution groups.</span></span>
- <span data-ttu-id="4d340-110">[Get-MoveRequest](https://docs.microsoft.com/powershell/module/exchange/get-moverequest): fornisce uno stato dettagliato di una migrazione delle cassette postali in continuazione.</span><span class="sxs-lookup"><span data-stu-id="4d340-110">[Get-MoveRequest](https://docs.microsoft.com/powershell/module/exchange/get-moverequest): Provides a detailed status of an ongoing mailbox migration.</span></span>
- <span data-ttu-id="4d340-111">[Get-MigrationUser](https://docs.microsoft.com/powershell/module/exchange/get-migrationuser): vengono fornite informazioni sugli utenti di migrazione e spostamento delle cassette postali.</span><span class="sxs-lookup"><span data-stu-id="4d340-111">[Get-MigrationUser](https://docs.microsoft.com/powershell/module/exchange/get-migrationuser): Provides information about the mailbox move and migration users.</span></span>
- <span data-ttu-id="4d340-112">[Get-MigrationBatch](https://docs.microsoft.com/powershell/module/exchange/get-migrationbatch): fornisce informazioni sullo stato del batch di migrazione corrente.</span><span class="sxs-lookup"><span data-stu-id="4d340-112">[Get-MigrationBatch](https://docs.microsoft.com/powershell/module/exchange/get-migrationbatch): Provides information on the status of current migration batch.</span></span>
- <span data-ttu-id="4d340-113">[Get-MigrationUserStatistics](https://docs.microsoft.com/powershell/module/exchange/get-migrationuserstatistics): vengono fornite informazioni dettagliate sullo stato della migrazione per un utente specifico.</span><span class="sxs-lookup"><span data-stu-id="4d340-113">[Get-MigrationUserStatistics](https://docs.microsoft.com/powershell/module/exchange/get-migrationuserstatistics): Provides detailed information about the migration status for a specific user.</span></span>
- <span data-ttu-id="4d340-114">[Get-MailboxStatistics](https://docs.microsoft.com/powershell/module/exchange/get-mailboxstatistics): vengono fornite informazioni sulle cassette postali, ad esempio le dimensioni, il numero di messaggi e l'ora dell'ultimo accesso.</span><span class="sxs-lookup"><span data-stu-id="4d340-114">[Get-MailboxStatistics](https://docs.microsoft.com/powershell/module/exchange/get-mailboxstatistics): Provides information about mailboxes, such as size, the number of messages, and the last accessed time.</span></span>

<span data-ttu-id="4d340-115">Per ulteriori informazioni sui cmdlet, vedere [Move and Migration cmdlets in Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="4d340-115">For more information about cmdlets, see [Move and Migration cmdlets in Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell).</span></span>
