---
title: Servizio di crittografia di Office 365
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: 'Riepilogo: informazioni sulla resilienza dei dati in Microsoft Office 365.'
ms.openlocfilehash: 385bb936de2c0cfcb478f0b20d2f7367d5b55ff4
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37084451"
---
# <a name="office-365-service-encryption"></a>Servizio di crittografia di Office 365

Oltre a utilizzare la crittografia a livello di volume, Exchange Online, Skype for business, SharePoint Online e OneDrive for business utilizzano anche la crittografia del servizio per crittografare i dati dei clienti. La crittografia del servizio consente di eseguire due opzioni di gestione principali:
- Microsoft gestisce tutte le chiavi di crittografia. Questa opzione è attualmente disponibile in SharePoint Online, OneDrive for business e Skype for business. La Guida di orientamento per Exchange Online è attualmente disponibile.
- Il cliente fornisce le chiavi radice utilizzate con la crittografia del servizio e il cliente gestisce queste chiavi utilizzando Azure Key Vault. Microsoft gestisce tutte le altre chiavi. Questa opzione è denominata Customer Key ed è attualmente disponibile per Exchange Online, SharePoint Online e OneDrive for business. (In precedenza denominato crittografia avanzata con BYOK. Vedere [miglioramento della trasparenza e del controllo per i clienti di Office 365](http://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/) per l'annuncio originale.

La crittografia dei servizi offre molteplici vantaggi. Ad esempio:
- fornisce funzionalità di gestione e protezione dei diritti al di sopra della protezione dalla crittografia avanzata.
- include un'opzione di chiave Customer che consente ai servizi multi-tenant di fornire la gestione delle chiavi per tenant.
- consente di separare gli amministratori del sistema operativo Windows dall'accesso ai dati dei clienti archiviati o elaborati dal sistema operativo.
- consente di migliorare la capacità di Office 365 di soddisfare le esigenze dei clienti con requisiti di conformità relativi alla crittografia.

## <a name="customer-key"></a>Customer Key
Utilizzando la chiave del cliente, è possibile generare chiavi di crittografia personalizzate utilizzando un HSM locale o un Vault chiave di Azure. Indipendentemente dal modo in cui viene generata la chiave, i clienti utilizzano Azure Key Vault per controllare e gestire le chiavi di crittografia utilizzate da Office 365. Una volta che le chiavi vengono archiviate nel Vault Key di Azure, è possibile assegnarle ai carichi di lavoro come Exchange Online e SharePoint Online e come radice del keychain utilizzato per crittografare i dati e i file delle cassette postali.
Uno degli altri vantaggi derivanti dall'utilizzo della chiave del cliente consiste nel controllare la capacità di Microsoft di elaborare i dati dei clienti. Questa funzionalità esiste in modo che un cliente che desidera rimuovere i dati da Office 365 (ad esempio quando un cliente termina il servizio con Microsoft o rimuove una parte dei dati archiviati nel cloud) sia in grado di eseguire tale operazione e utilizzare la chiave del cliente come controllo tecnico per garantire che nessuno , incluso Microsoft, può accedere ai dati o elaborarli. Questo è in aggiunta (e un complemento) alla funzionalità dell'archivio protetto dei clienti che può essere utilizzata per controllare l'accesso ai dati dei clienti da parte di personale Microsoft.

Per informazioni su come configurare Customer Key per Office 365 per Exchange Online, Skype for business, SharePoint Online e OneDrive for business, vedere [controlling your data in office 365 using Customer Key](https://support.office.com/article/Controlling-your-data-in-Office-365-using-Customer-Key-f2cd475a-e592-46cf-80a3-1bfb0fa17697). Per ulteriori informazioni, vedere le [domande frequenti su Customer Key per Office 365](https://support.office.com/article/Customer-Key-for-Office-365-FAQ-41ae293a-bd5c-4083-acd8-e1a2b4329da6)e [gestire e controllare i dati per soddisfare i requisiti di conformità con la chiave del cliente](https://techcommunity.microsoft.com/t5/Microsoft-Ignite-Content-2017/Manage-and-control-your-data-to-help-meet-compliance-needs-with/td-p/117580).
