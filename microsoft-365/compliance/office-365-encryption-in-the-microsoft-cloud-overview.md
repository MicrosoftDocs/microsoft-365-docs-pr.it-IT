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
description: In questo articolo, leggere una panoramica delle varie forme di crittografia utilizzate per mantenere al sicuro i dati dei clienti nel cloud Microsoft.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0d05c904fc70d02d8694b8f2d3b451fd1d51dc91
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841295"
---
# <a name="encryption-in-the-microsoft-cloud"></a>Crittografia nel Microsoft Cloud

I dati dei clienti all'interno dei servizi cloud aziendali di Microsoft sono protetti da diverse tecnologie e processi, tra cui diverse forme di crittografia. I dati dei clienti in questo documento includono il contenuto della cassetta postale di Exchange Online, il corpo della posta elettronica, le voci del calendario e il contenuto degli allegati di posta elettronica e, se applicabile, il contenuto del sito Skype for Business), il contenuto del sito di SharePoint Online e i file archiviati nei siti e i file caricati in OneDrive for Business o Skype for Business. Microsoft usa più metodi di crittografia, protocolli e crittografie tra i propri prodotti e servizi per fornire un percorso sicuro per consentire ai dati dei clienti di viaggiare attraverso i servizi cloud e per proteggere la riservatezza dei dati dei clienti archiviati all'interno dei servizi cloud. Microsoft usa alcuni dei protocolli di crittografia più sicuri e più sicuri disponibili per fornire barriere contro l'accesso non autorizzato ai dati dei clienti. La gestione corretta delle chiavi è anche un elemento essenziale delle procedure consigliate per la crittografia e Microsoft lavora per garantire che tutte le chiavi di crittografia gestite da Microsoft siano protette correttamente.

I dati dei clienti archiviati nei servizi cloud aziendali di Microsoft sono protetti utilizzando una o più forme di crittografia. La convalida dei criteri di crittografia e la relativa applicazione vengono verificate in modo indipendente da più revisori di terze parti e i report di tali controlli sono disponibili nel [Service Trust Portal.](https://aka.ms/stp)

Microsoft fornisce tecnologie sul lato servizio che crittografano i dati dei clienti in pausa e in transito. Ad esempio, per i dati dei clienti in pausa, Microsoft Azure usa [BitLocker](/windows/device-security/bitlocker/bitlocker-overview) e [DM-Crypt](https://en.wikipedia.org/wiki/Dm-crypt)e Microsoft 365 usa BitLocker, [Archiviazione di Azure Service Encryption,](/azure/) [Distributed Key Manager](./exchange-online-secures-email-secrets.md) (DKM) e la crittografia del servizio Microsoft 365. Per i dati dei clienti in transito, Azure, Office 365, Supporto commerciale Microsoft, Microsoft Dynamics 365, Microsoft Power BI e Visual Studio Team Services usano protocolli di trasporto sicuri standard del settore, come IPsec (Internet Protocol Security) e TRANSPORT Layer Security (TLS), tra i datacenter Microsoft e tra i dispositivi utente e i datacenter Microsoft.

Oltre al livello di base di sicurezza crittografica fornito da Microsoft, i nostri servizi cloud includono anche le opzioni di crittografia che puoi gestire. Ad esempio, è possibile abilitare la crittografia per il traffico tra le macchine virtuali di Azure e i relativi utenti. Con [Le reti virtuali di Azure](https://azure.microsoft.com/services/virtual-network/)è possibile utilizzare il protocollo IPsec standard del settore per crittografare il traffico tra il gateway VPN aziendale e Azure. È inoltre possibile crittografare il traffico tra le macchine virtuali nella rete virtuale. Inoltre, [le nuove Office 365 Message Encryption consentono](set-up-new-message-encryption-capabilities.md) di inviare posta crittografata a chiunque.

Seguendo lo standard di sicurezza operativa dell'infrastruttura a chiave pubblica, che è un componente dei criteri di sicurezza [Microsoft,](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=5868ecc8-50b7-4f91-b43f-640e2b99e86e&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ%20and%20White%20Papers)Microsoft utilizza le funzionalità di crittografia incluse nel sistema operativo Windows per i certificati e i meccanismi di autenticazione. Questi meccanismi includono l'uso di moduli crittografici che soddisfano lo standard FIPS [(Federal Information Processing Standards)](https://csrc.nist.gov/publications/PubsFIPS.html) 140-2 del governo degli Stati Uniti. È possibile cercare i numeri di certificato NIST pertinenti per Microsoft utilizzando [cmvp (Cryptographic Module Validation Program).](https://csrc.nist.gov/projects/cryptographic-module-validation-program/validated-modules/search)

> [NOTA] Per accedere ai Criteri di sicurezza Microsoft come risorsa, è necessario accedere utilizzando l'account aziendale o dell'istituto di istruzione. Se non si dispone ancora di un abbonamento, è possibile iscriversi [per una versione di valutazione gratuita.](https://servicetrust.microsoft.com/Home/TrialSubscriptions)

FIPS 140-2 è uno standard progettato appositamente per convalidare i moduli di prodotto che implementano la crittografia anziché i prodotti che li usano. I moduli crittografici implementati all'interno di un servizio possono essere certificati come soddisfare i requisiti per la forza dell'hash, la gestione delle chiavi e simili. I moduli crittografici e le crittografie utilizzati per proteggere la riservatezza, l'integrità o la disponibilità dei dati nei servizi cloud di Microsoft soddisfano lo standard FIPS 140-2.

Microsoft certifica i moduli crittografici sottostanti utilizzati nei servizi cloud con ogni nuova versione del Windows operativo:

- Azure e Azure U.S. Government
- Dynamics 365 e Dynamics 365 U.S. Government
- Office 365, Office 365 U.S. Government e Office 365 U.S. Government Defense

La crittografia dei dati dei clienti in pausa è fornita da più tecnologie sul lato servizio, tra cui BitLocker, DKM, crittografia del servizio Archiviazione di Azure e crittografia dei servizi in Exchange Online, Skype for Business, OneDrive for Business e SharePoint Online. Office 365 servizio di crittografia include un'opzione per usare le chiavi di crittografia gestite dal cliente archiviate in Azure Key Vault. Questa opzione della chiave gestita dal cliente, denominata [Customer Key,](./customer-key-overview.md)è disponibile per Exchange Online, SharePoint Online, Skype for Business e OneDrive for Business.

Per i dati dei clienti in transito, tutti Office 365 negoziano sessioni protette utilizzando TLS per impostazione predefinita con i computer client per proteggere i dati dei clienti. Ad esempio, Office 365 le sessioni protette verranno negoziate Skype for Business, Outlook e Outlook sul Web, i client mobili e i Web browser.

Per impostazione predefinita, tutti i server rivolti al cliente negoziano con TLS 1.2.

## <a name="related-links"></a>Collegamenti correlati

- [Crittografia in Azure](office-365-azure-encryption.md)
- [BitLocker e Distributed Key Manager (DKM) per la crittografia](office-365-bitlocker-and-distributed-key-manager-for-encryption.md)
- [Servizio di crittografia di Office 365](office-365-service-encryption.md)
- [Office 365 Crittografia per Skype for Business, OneDrive for Business, SharePoint Online e Exchange Online](/compliance/assurance/assurance-encryption-for-microsoft-365-services) 
- [Crittografia per i dati in transito](/compliance/assurance/assurance-encryption-in-transit)
- [Funzionalità di crittografia gestite dai clienti](office-365-customer-managed-encryption-features.md)
- [Protezione e rischi della crittografa](office-365-encryption-risks-and-protections.md)
- [Crittografia in Microsoft Dynamics 365](office-365-encryption-in-microsoft-dynamics-365.md)