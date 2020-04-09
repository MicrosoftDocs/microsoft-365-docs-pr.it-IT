---
title: Servizio di crittografia di Office 365
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.date: 4/8/2020
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 'Riepilogo: informazioni sulla crittografia dei dati a livello di servizio in Microsoft Office 365.'
ms.openlocfilehash: a8faded033ade013924eeeab269aa213840430b4
ms.sourcegitcommit: 13f28aa762e467bab8ab1e95e1917b3ac28931da
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2020
ms.locfileid: "43193462"
---
# <a name="office-365-service-encryption"></a>Servizio di crittografia di Office 365

Oltre a utilizzare BitLocker per la crittografia a livello di volume, Exchange Online, Skype for business, SharePoint Online, OneDrive for business e i team utilizzano anche la crittografia del servizio per crittografare i dati dei clienti. La crittografia del servizio consente di eseguire due opzioni di gestione principali:

- Microsoft gestisce tutte le chiavi di crittografia. Questa opzione è attualmente disponibile in SharePoint Online, OneDrive for business, Skype for business e chat teams. I dati vengono crittografati per impostazione predefinita con le chiavi gestite Microsoft.

- L'organizzazione fornisce le chiavi radice. È possibile gestire queste chiavi utilizzando il Vault Key di Azure. Questa opzione è denominata Customer Key. La chiave del cliente è attualmente disponibile per i file di Exchange Online, SharePoint Online, OneDrive for business, Skype for business e teams. Se si utilizza il codice "Customer Key", queste chiavi sostituiscono le chiavi gestite Microsoft per crittografare i dati.

Indipendentemente dall'opzione scelta, la crittografia dei servizi fornisce molteplici vantaggi:

- Impone l'autenticazione utente per recuperare e decrittografare i dati richiesti da un utente autorizzato.

- Consente di separare gli amministratori del sistema operativo Windows dall'accesso ai dati dei clienti archiviati o elaborati dal sistema operativo.

- Consente di migliorare la capacità di Office 365 di soddisfare le esigenze dei clienti con requisiti di conformità relativi alla crittografia.

Per informazioni su come configurare la chiave del cliente per Office 365 per Exchange Online, Skype for business, SharePoint Online, OneDrive for business e i file teams, vedere gli articoli seguenti:

- [Crittografia del servizio con la chiave del cliente in Office 365](customer-key-overview.md)

- [Configurare la chiave cliente per Office 365](customer-key-set-up.md)

- [Gestire la chiave del cliente per Office 365](customer-key-manage.md)

- [Eseguire il rollforward o la rotazione di una chiave del cliente o di una chiave di disponibilità](customer-key-availability-key-roll.md)

- [Comprendere il codice di disponibilità](customer-key-availability-key-understand.md)
