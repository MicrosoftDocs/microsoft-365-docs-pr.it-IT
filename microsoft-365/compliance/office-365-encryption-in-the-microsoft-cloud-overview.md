---
title: Crittografia nel Microsoft Cloud
f1.keywords:
- NOCSH
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
description: In questo articolo, leggere una panoramica delle varie forme di crittografia usate per mantenere al sicuro i dati dei clienti nel cloud Microsoft.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e48cc4fc54f0bc4553bab655611900523e11bd4d
ms.sourcegitcommit: 1c90bcc5c56f24895f01c3e0423c3f6b73715c13
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "44214274"
---
# <a name="encryption-in-the-microsoft-cloud"></a>Crittografia nel Microsoft Cloud

I dati dei clienti all'interno dei servizi cloud aziendali di Microsoft sono protetti da un'ampia gamma di tecnologie e processi, tra cui varie forme di crittografia. I dati dei clienti in questo documento includono il contenuto della cassetta postale di Exchange Online, il corpo del messaggio di posta elettronica, le voci del calendario e il contenuto degli allegati di posta elettronica e, se applicabile, il contenuto di Skype for Business), il contenuto del sito di SharePoint Online e i file archiviati nei siti e i file caricati in OneDrive for Business o Skype for Business. Microsoft usa più metodi di crittografia, protocolli e crittografie tra i propri prodotti e servizi per fornire un percorso sicuro per consentire ai dati dei clienti di attraversare i servizi cloud e per proteggere la riservatezza dei dati dei clienti archiviati all'interno dei servizi cloud. Microsoft usa alcuni dei protocolli di crittografia più sicuri e più sicuri disponibili per fornire barriere contro l'accesso non autorizzato ai dati dei clienti. La corretta gestione delle chiavi è anche un elemento essenziale delle procedure consigliate per la crittografia e Microsoft lavora per garantire che tutte le chiavi di crittografia gestite da Microsoft siano protette correttamente.

Indipendentemente dalla configurazione del cliente, i dati dei clienti archiviati all'interno dei servizi cloud aziendali di Microsoft sono protetti tramite una o più forme di crittografia. La convalida dei criteri di crittografia e la relativa applicazione vengono verificate in modo indipendente da più revisori di terze parti e i report di tali controlli sono disponibili nel [Service Trust Portal.](https://aka.ms/stp)

Microsoft fornisce tecnologie sul lato servizio che crittografano i dati dei clienti in stato di inquieto e in transito. Ad esempio, per i dati dei clienti in stato di inquieto, Microsoft Azure usa [BitLocker](https://docs.microsoft.com/windows/device-security/bitlocker/bitlocker-overview) e [DM-Crypt](https://en.wikipedia.org/wiki/Dm-crypt)e Microsoft 365 usa BitLocker, Crittografia del servizio di archiviazione di [Azure,](https://docs.microsoft.com/azure/) [Distributed Key Manager](https://docs.microsoft.com/microsoft-365/compliance/exchange-online-secures-email-secrets) (DKM) e la crittografia del servizio Microsoft 365. Per i dati dei clienti in transito, Azure, Office 365, Supporto commerciale Microsoft, Microsoft Dynamics 365, Microsoft Power BI e Visual Studio Team Services usano protocolli di trasporto sicuri standard del settore, come IPsec (Internet Protocol Security) e Transport Layer Security (TLS), tra datacenter Microsoft e tra dispositivi utente e datacenter Microsoft.

Oltre al livello di base di sicurezza crittografica fornito da Microsoft, i servizi cloud includono anche altre opzioni di crittografia che è possibile gestire. Ad esempio, è possibile abilitare la crittografia per il traffico tra le macchine virtuali di Azure e i relativi utenti. Con le reti virtuali di [Azure,](https://azure.microsoft.com/services/virtual-network/)è possibile utilizzare il protocollo IPsec standard del settore per crittografare il traffico tra il gateway VPN aziendale e Azure, nonché tra le macchine virtuali presenti nella rete virtuale. Inoltre, le nuove funzionalità di crittografia dei messaggi di [Office 365](set-up-new-message-encryption-capabilities.md) consentono di inviare posta crittografata a chiunque.

In conformità con lo standard di sicurezza operativo dell'infrastruttura a chiave pubblica, che è un componente dei criteri di sicurezza [Microsoft,](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=5868ecc8-50b7-4f91-b43f-640e2b99e86e&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ%20and%20White%20Papers)Microsoft sfrutta le funzionalità di crittografia incluse nel sistema operativo Windows per i certificati e i meccanismi di autenticazione, che includono l'uso di moduli crittografici che soddisfano lo standard FIPS [(Federal Information Processing Standards)](https://csrc.nist.gov/publications/PubsFIPS.html) 140-2 del governo degli Stati Uniti. I numeri di certificato NIST pertinenti per Microsoft sono disponibili all'indirizzo https://csrc.nist.gov/groups/STM/cmvp/documents/140-1/1401vend.htm.)

> [NOTA] Per accedere ai Criteri di sicurezza Microsoft come risorsa, è necessario accedere con l'account aziendale o dell'istituto di istruzione. Se non si ha ancora un abbonamento, è possibile iscriversi [per una versione di valutazione gratuita.](https://servicetrust.microsoft.com/Home/TrialSubscriptions)

FIPS 140-2 è uno standard progettato appositamente per convalidare i moduli di prodotto che implementano la crittografia anziché i prodotti che li usano. I moduli crittografici implementati all'interno di un servizio possono essere certificati come soddisfare i requisiti per la forza dell'hash, la gestione delle chiavi e simili. Ogni volta che vengono utilizzate funzionalità di crittografia per proteggere la riservatezza, l'integrità o la disponibilità dei dati nei servizi cloud di Microsoft, i moduli e le crittografie usati soddisfano lo standard FIPS 140-2.

Microsoft certifica i moduli crittografici sottostanti utilizzati nei servizi cloud con ogni nuova versione del sistema operativo Windows:

- Azure e Azure U.S. Government
- Dynamics 365 e Dynamics 365 U.S. Government
- Office 365, Office 365 U.S. Government e Office 365 U.S. Government Defense

La crittografia dei dati dei clienti in pausa è fornita da più tecnologie sul lato servizio, tra cui BitLocker, DKM, crittografia del servizio di archiviazione di Azure e crittografia del servizio in Exchange Online, Skype for Business, OneDrive for Business e SharePoint Online. La crittografia del servizio Office 365 include un'opzione per usare le chiavi di crittografia gestite dal cliente archiviate in Azure Key Vault. Questa opzione chiave gestita dal cliente, denominata [Customer Key,](https://docs.microsoft.com/microsoft-365/compliance/customer-key-overview)è disponibile per Exchange Online, SharePoint Online, Skype for Business e OneDrive for Business.

Per i dati dei clienti in transito, tutti i server Office 365 negoziano sessioni sicure tramite TLS per impostazione predefinita con i computer client per proteggere i dati dei clienti.  Questo vale per i protocolli su qualsiasi dispositivo utilizzato dai client, ad esempio Skype for Business, Outlook e Outlook sul Web, client mobili e Web browser.

Per impostazione predefinita, tutti i server rivolti ai clienti negoziano con TLS 1.2, ma supportiamo anche la negoziazione verso uno standard inferiore, se necessario.

## <a name="related-links"></a>Collegamenti correlati

- [Crittografia in Azure](office-365-azure-encryption.md)
- [BitLocker e Distributed Key Manager (DKM) per la crittografia](office-365-bitlocker-and-distributed-key-manager-for-encryption.md)
- [Servizio di crittografia di Office 365](office-365-service-encryption.md)
- [Crittografia di Office 365 per Skype for Business, OneDrive for Business, SharePoint Online ed Exchange Online](office-365-encryption-for-skype-onedrive-sharepoint-and-exchange.md)
- [Crittografia per i dati in transito](office-365-encryption-for-data-in-transit.md)
- [Funzionalità di crittografia gestite dai clienti](office-365-customer-managed-encryption-features.md)
- [Protezione e rischi della crittografa](office-365-encryption-risks-and-protections.md)
- [Crittografia in Microsoft Dynamics 365](office-365-encryption-in-microsoft-dynamics-365.md)
