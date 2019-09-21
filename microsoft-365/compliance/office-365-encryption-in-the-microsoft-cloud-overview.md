---
title: Crittografia nel Microsoft Cloud
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_Enterprise
- M365-security-compliance
- Strat_O365_Enterprise
description: Panoramica della crittografia nel cloud Microsoft.
ms.openlocfilehash: 36bb50cda5f39461401b14ca3e7ada77a6e2cc0d
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/20/2019
ms.locfileid: "37084461"
---
# <a name="encryption-in-the-microsoft-cloud"></a>Crittografia nel Microsoft Cloud

I dati dei clienti all'interno dei servizi cloud aziendali di Microsoft sono protetti da una vasta gamma di tecnologie e processi, tra cui varie forme di crittografia. I dati dei clienti di Office 365 in questo documento includono il contenuto della cassetta postale di Exchange Online (corpo di posta elettronica, voci del calendario e il contenuto di allegati di posta elettronica e, se applicabile, il contenuto di Skype for business), il contenuto del sito di SharePoint Online e i file archiviati all'interno siti e file caricati su OneDrive for business o Skype for business. Microsoft utilizza più metodi di crittografia, protocolli e cifrati tra i propri prodotti e servizi per fornire un percorso sicuro per i dati dei clienti per viaggiare attraverso i servizi cloud e per proteggere la riservatezza dei dati del cliente archiviati all'interno Servizi cloud. Microsoft utilizza alcuni dei più potenti protocolli di crittografia più sicuri disponibili per fornire barriere all'accesso non autorizzato ai dati dei clienti. La corretta gestione delle chiavi è anche un elemento essenziale delle procedure consigliate per la crittografia e Microsoft funziona per garantire che tutte le chiavi di crittografia gestite da Microsoft siano protette correttamente.

Indipendentemente dalla configurazione dei clienti, i dati dei clienti archiviati all'interno dei servizi cloud Microsoft Enterprise sono protetti utilizzando una o più forme di crittografia. La convalida dei criteri di crittografia e la relativa applicazione sono verificate in modo indipendente da più revisori di terze parti e i rapporti di tali controlli sono disponibili nel [Service Trust Portal](https://aka.ms/stp).

Microsoft fornisce tecnologie sul fianco del servizio che crittografano i dati dei clienti a riposo e in transito. Ad esempio, per i dati dei clienti a riposo, Microsoft Azure utilizza [BitLocker](https://docs.microsoft.com/windows/device-security/bitlocker/bitlocker-overview) e [dm-crypt](https://en.wikipedia.org/wiki/Dm-crypt)e Microsoft Office 365 utilizza BitLocker, la [crittografia del servizio di archiviazione di Azure](https://azure.microsoft.com/documentation/articles/storage-service-encryption/), [Distributed Key Manager](https://support.office.com/article/989ba10c-f73f-4efb-ad1b-af3322e5f376) (DKM) e Office 365 Service crittografia. Per i dati dei clienti in transito, Azure, Office 365, Microsoft Commercial Support, Microsoft Dynamics 365, Microsoft Power BI e Visual Studio Team Services utilizzano protocolli di trasporto sicuro standard del settore, ad esempio IPsec (Internet Protocol Security) e Transport Layer Security (TLS), tra i datacenter Microsoft e tra i dispositivi utente e i datacenter Microsoft.

Oltre al livello di base della sicurezza crittografica fornita da Microsoft, i servizi cloud includono anche ulteriori opzioni di crittografia che è possibile gestire. Ad esempio, è possibile abilitare la crittografia per il traffico tra le macchine virtuali di Azure (VM) e gli utenti. Con le [reti virtuali di Azure](https://azure.microsoft.com/services/virtual-network/), è possibile utilizzare il protocollo IPSec standard del settore per crittografare il traffico tra il gateway VPN aziendale e Azure, nonché tra le macchine virtuali situate nella rete virtuale. Inoltre, le [nuove funzionalità di crittografia dei messaggi di Office 365](set-up-new-message-encryption-capabilities.md) consentono di inviare posta crittografata a tutti gli utenti.

In conformità con lo standard di sicurezza operativo dell'infrastruttura a chiave pubblica, che è un componente dei [criteri di sicurezza di Microsoft](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=5868ecc8-50b7-4f91-b43f-640e2b99e86e&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ%20and%20White%20Papers), Microsoft utilizza le funzionalità di crittografia incluse nel sistema operativo Windows per i certificati e meccanismi di autenticazione, che include l'utilizzo di moduli di crittografia che soddisfano lo standard FIPS ( [Federal Information Processing Standards](http://csrc.nist.gov/publications/PubsFIPS.html) ) del governo degli stati Uniti 140-2. (I numeri di certificato NIST rilevanti per Microsoft sono reperibili suhttp://csrc.nist.gov/groups/STM/cmvp/documents/140-1/1401vend.htm.)

> Nota Per accedere ai criteri di sicurezza Microsoft come risorsa, è necessario eseguire l'accesso utilizzando l'account aziendale o dell'Istituto di istruzione. Se non si dispone ancora di un abbonamento, [è possibile iscriversi per una versione di valutazione gratuita](https://servicetrust.microsoft.com/Home/TrialSubscriptions).

FIPS 140-2 è uno standard progettato appositamente per la convalida dei moduli di prodotto che implementano la crittografia anziché i prodotti che li utilizzano. I moduli di crittografia implementati all'interno di un servizio possono essere certificati come rispondenti ai requisiti per la forza hash, la gestione delle chiavi e simili. Ogni volta che vengono utilizzate le funzionalità di crittografia per proteggere la riservatezza, l'integrità o la disponibilità dei dati nei servizi cloud di Microsoft, i moduli e i cifrari utilizzati soddisfano lo standard FIPS 140-2.

Microsoft certifica i moduli di crittografia sottostanti utilizzati nei servizi cloud con ogni nuova versione del sistema operativo Windows:

- Governo degli Stati Uniti di Azure e Azure
- Governo degli Stati Uniti Dynamics 365 e Dynamics 365
- Office 365, Office 365 US Government e Office 365 US Government Defense

La crittografia dei dati del cliente di Office 365 a riposo è fornita da più tecnologie sul fianco del servizio, tra cui BitLocker, DKM, crittografia del servizio di archiviazione di Azure e crittografia del servizio in Exchange Online, Skype for business, OneDrive for business e SharePoint Online. La crittografia dei servizi di Office 365 include un'opzione per l'utilizzo delle chiavi di crittografia gestite dal cliente archiviate in Azure Key Vault. Questa opzione di chiave gestita dal cliente, denominata [chiave del cliente di Office 365](https://support.office.com/article/f2cd475a-e592-46cf-80a3-1bfb0fa17697), è disponibile per Exchange Online, SharePoint Online, Skype for business e OneDrive for business.

Per i dati dei clienti in transito, tutti i server di Office 365 negoziano le sessioni sicure tramite TLS per impostazione predefinita con i computer client per proteggere i dati dei clienti.  Questo vale per i protocolli su qualsiasi dispositivo utilizzato dai client, ad esempio Skype for business, Outlook e Outlook sul Web, i client mobili e i Web browser.

(Tutti i server rivolti ai clienti negoziano su TLS 1,2 per impostazione predefinita, ma è anche possibile supportare la negoziazione fino a un livello inferiore, se necessario).

## <a name="related-links"></a>Collegamenti correlati

- [Crittografia in Azure](office-365-azure-encryption.md)
- [BitLocker e Distributed Key Manager (DKM) per la crittografia](office-365-bitlocker-and-distributed-key-manager-for-encryption.md)
- [Servizio di crittografia di Office 365](office-365-service-encryption.md)
- [Crittografia di Office 365 per Skype for business, OneDrive for business, SharePoint Online ed Exchange Online](office-365-encryption-for-skype-onedrive-sharepoint-and-exchange.md)
- [Crittografia per i dati in transito](office-365-encryption-for-data-in-transit.md)
- [Funzionalità di crittografia gestite dai clienti](office-365-customer-managed-encryption-features.md)
- [Protezione e rischi della crittografa](office-365-encryption-risks-and-protections.md)
- [Crittografia in Microsoft Dynamics 365](office-365-encryption-in-microsoft-dynamics-365.md)