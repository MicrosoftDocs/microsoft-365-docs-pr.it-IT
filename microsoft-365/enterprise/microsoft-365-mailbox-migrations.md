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
# <a name="microsoft-365-mailbox-migrations"></a>Migrazioni delle cassette postali di Microsoft 365

Con una distribuzione ibrida basata su Exchange, i clienti possono scegliere di spostare le cassette postali di Exchange locali in un'organizzazione di [Exchange Online](https://docs.microsoft.com/Exchange/exchange-online) o di spostare le cassette postali di Exchange online in un'organizzazione di [Exchange locale](https://docs.microsoft.com/Exchange/exchange-server) . Quando si spostano le cassette postali tra organizzazioni locali e di Exchange Online, vengono utilizzati i batch di migrazione.

I clienti possono esaminare le statistiche e altre informazioni sulle migrazioni delle cassette postali con i cmdlet seguenti:

- [Get-MoveRequestStatistics](https://docs.microsoft.com/powershell/module/exchange/get-moverequeststatistics): fornisce statistiche predefinite per una cassetta postale utente, che include lo stato, la dimensione della cassetta postale, la dimensione della cassetta postale di archiviazione e la percentuale di completamento.
- [Get-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Get-Mailbox
): fornisce un elenco riepilogativo degli oggetti e degli attributi delle cassette postali nell'organizzazione.
- [Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/get-recipient): fornisce un elenco di oggetti esistenti abilitati alla posta elettronica, quali cassette postali, utenti di posta elettronica, contatti e gruppi di distribuzione.
- [Get-MoveRequest](https://docs.microsoft.com/powershell/module/exchange/get-moverequest): fornisce uno stato dettagliato di una migrazione delle cassette postali in continuazione.
- [Get-MigrationUser](https://docs.microsoft.com/powershell/module/exchange/get-migrationuser): vengono fornite informazioni sugli utenti di migrazione e spostamento delle cassette postali.
- [Get-MigrationBatch](https://docs.microsoft.com/powershell/module/exchange/get-migrationbatch): fornisce informazioni sullo stato del batch di migrazione corrente.
- [Get-MigrationUserStatistics](https://docs.microsoft.com/powershell/module/exchange/get-migrationuserstatistics): vengono fornite informazioni dettagliate sullo stato della migrazione per un utente specifico.
- [Get-MailboxStatistics](https://docs.microsoft.com/powershell/module/exchange/get-mailboxstatistics): vengono fornite informazioni sulle cassette postali, ad esempio le dimensioni, il numero di messaggi e l'ora dell'ultimo accesso.

Per ulteriori informazioni sui cmdlet, vedere [Move and Migration cmdlets in Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell).
