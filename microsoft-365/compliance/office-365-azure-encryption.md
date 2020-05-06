---
title: Crittografia in Azure
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
description: Informazioni sulla crittografia disponibile in Azure, ad esempio la crittografia su disco di Azure
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: d5d334c56228a372d7e389bd5d0eff9859184d5b
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "44033634"
---
# <a name="encryption-in-azure"></a>Crittografia in Azure

Le misure di salvaguardia tecnologiche in Azure, ad esempio le comunicazioni crittografate e i processi operativi, consentono di proteggere i dati. È inoltre possibile implementare ulteriori funzionalità di crittografia e gestire le proprie chiavi di crittografia. Indipendentemente dalla configurazione dei clienti, Microsoft applica la crittografia per proteggere i dati dei clienti in Azure. Microsoft consente inoltre di controllare i dati ospitati in Azure tramite una serie di tecnologie avanzate per crittografare, controllare e gestire le chiavi di crittografia, nonché controllare e verificare l'accesso ai dati. Nello spazio di archiviazione di Azure sono inoltre disponibili una serie completa di funzionalità di sicurezza che consentono agli sviluppatori di creare applicazioni sicure.

## <a name="introduction"></a>Introduzione

Azure offre numerosi meccanismi per la protezione dei dati quando si sposta da una posizione a un'altra. Microsoft utilizza TLS per proteggere i dati durante il viaggio tra i servizi cloud e i clienti. I Data Center di Microsoft negoziano una connessione TLS con i sistemi client che si connettono ai servizi di Azure. La perfetta segretezza avanzata (PFS) protegge le connessioni tra i sistemi client dei clienti e i servizi cloud di Microsoft tramite chiavi univoche. Le connessioni utilizzano anche la lunghezza della chiave di crittografia a 2.048 bit basata su RSA. Questa combinazione rende difficile l'intercettazione e l'accesso ai dati in transito.

È possibile proteggere i dati in transito tra un'applicazione e Azure utilizzando la [crittografia sul retro del client](https://docs.microsoft.com/azure/storage/storage-client-side-encryption), HTTPS o SMB 3,0. È possibile abilitare la crittografia per il traffico tra le macchine virtuali (VM) e gli utenti. Con le [reti virtuali di Azure](https://azure.microsoft.com/services/virtual-network/), è possibile utilizzare il protocollo IPSec standard del settore per crittografare il traffico tra il gateway VPN aziendale e Azure, nonché tra le macchine virtuali situate nella rete virtuale.

Per i dati a riposo, Azure offre numerose opzioni di crittografia, ad esempio il supporto per AES-256, offrendo la possibilità di scegliere lo scenario di archiviazione dei dati più adatto alle proprie esigenze. I dati possono essere crittografati automaticamente quando vengono scritti nello spazio di archiviazione di Azure tramite la [crittografia del servizio di archiviazione](https://docs.microsoft.com/azure/storage/storage-service-encryption)e i dischi di sistema e di dati utilizzati dalle macchine virtuali possono essere crittografati. Per ulteriori informazioni, vedere [Suggerimenti per la sicurezza per le macchine virtuali Windows in Azure](https://docs.microsoft.com/azure/security/azure-security-disk-encryption). Inoltre, l'accesso delegato agli oggetti dati in Azure Storage può essere concesso utilizzando le [firme di accesso condiviso](https://docs.microsoft.com/azure/storage/storage-dotnet-shared-access-signature-part-1). Azure fornisce inoltre la crittografia dei dati a REST tramite la [crittografia dei dati trasparente per database SQL di Azure e data warehouse](https://docs.microsoft.com/sql/relational-databases/security/encryption/transparent-data-encryption-azure-sql).

Per ulteriori informazioni sulla crittografia in Azure, vedere [Azure Encryption Overview](https://docs.microsoft.com/azure/security/security-azure-encryption-overview) e [Azure Data Encryption-at-rest](https://docs.microsoft.com/azure/security/azure-security-encryption-atrest).

## <a name="azure-disk-encryption"></a>Crittografia del disco di Azure

La crittografia del disco di Azure consente di crittografare i dischi VM di Windows e Linux come servizio (IaaS). La crittografia su disco di Azure utilizza la funzionalità BitLocker di Windows e la funzionalità DM-Crypt di Linux per fornire la crittografia a livello di volume per il sistema operativo e i dischi di dati. Inoltre, garantisce che tutti i dati sui dischi VM siano crittografati a riposo nello spazio di archiviazione di Azure. La crittografia del disco di Azure è integrata con il Vault Key di Azure per facilitare il controllo, la gestione e la verifica dell'utilizzo delle chiavi di crittografia e dei segreti.

Per ulteriori informazioni, vedere [Suggerimenti per la sicurezza per le macchine virtuali Windows in Azure](https://docs.microsoft.com/azure/virtual-machines/windows/security-recommendations).

## <a name="azure-storage-service-encryption"></a>Crittografia del servizio di archiviazione di Azure

Con la [crittografia del servizio di archiviazione di Azure](https://docs.microsoft.com/azure/storage/storage-service-encryption), lo spazio di archiviazione di Azure esegue automaticamente la crittografia dei dati prima di mantenerlo in archiviazione e di decrittografare i dati prima del recupero. I processi di crittografia, decrittografia e gestione delle chiavi sono totalmente trasparenti per gli utenti. La crittografia del servizio di archiviazione di Azure può essere utilizzata per l' [archiviazione BLOB di Azure](https://azure.microsoft.com/services/storage/blobs/) e [i file Azure](https://azure.microsoft.com/services/storage/files/). È inoltre possibile utilizzare le chiavi di crittografia gestite da Microsoft con la crittografia del servizio di archiviazione di Azure oppure è possibile utilizzare le proprie chiavi di crittografia. Per informazioni sull'utilizzo di chiavi proprie, vedere [crittografia del servizio di archiviazione utilizzando le chiavi gestite del cliente in Azure Key Vault](https://docs.microsoft.com/azure/storage/common/storage-service-encryption-customer-managed-keys). Per informazioni sull'utilizzo delle chiavi gestite da Microsoft, vedere [Storage Service Encryption for data at rest](https://docs.microsoft.com/azure/storage/storage-service-encryption). È inoltre possibile automatizzare l'utilizzo della crittografia. Ad esempio, è possibile abilitare o disabilitare a livello di programmazione la crittografia del servizio di archiviazione su un account di archiviazione utilizzando l' [API REST di Azure Storage Resource Provider](https://msdn.microsoft.com/library/azure/mt163683.aspx), la [libreria client del provider di risorse di archiviazione per .NET](https://msdn.microsoft.com/library/azure/mt131037.aspx), [Azure PowerShell](https://docs.microsoft.com/powershell/azureps-cmdlets-docs)o la [CLI di Azure](https://docs.microsoft.com/azure/storage/storage-azure-cli).

Alcuni servizi Microsoft 365 utilizzano Azure per l'archiviazione dei dati. Ad esempio, i dati di SharePoint Online e OneDrive for business nell'archiviazione BLOB di Azure e Microsoft teams memorizza i dati per il servizio chat nelle tabelle, nei BLOB e nelle code. Inoltre, la feature Score Compliance nel centro conformità di Microsoft 365 archivia i dati immessi dall'utente archiviati in formato crittografato in [Azure Cosmos DB](https://docs.microsoft.com/azure/cosmos-db/database-encryption-at-rest), un database multi-modello di piattaforma come servizio (PaaS), distribuito a livello globale. Crittografia del servizio di archiviazione di Azure consente di crittografare i dati archiviati nell'archiviazione BLOB di Azure e nelle tabelle e la crittografia su disco di Azure crittografa i dati nelle code, nonché i dischi delle macchine virtuali di Windows e IaaS per fornire la crittografia del volume per il sistema operativo e per il disco di dati. La soluzione garantisce che tutti i dati sui dischi della macchina virtuale siano crittografati a riposo nello spazio di archiviazione di Azure. [La crittografia a Rest in Azure Cosmos DB](https://docs.microsoft.com/azure/cosmos-db/database-encryption-at-rest) viene implementata utilizzando diverse tecnologie di sicurezza, tra cui sistemi di archiviazione delle chiavi sicure, reti crittografate e API di crittografia.

## <a name="azure-key-vault"></a>Azure Key Vault

La gestione sicura delle chiavi non è solo la base per le procedure consigliate per la crittografia; è inoltre essenziale per la protezione dei dati nel cloud. Il [Vault Key di Azure](https://docs.microsoft.com/azure/key-vault/key-vault-whatis) consente di crittografare le chiavi e i piccoli segreti come password che utilizzano chiavi archiviate in moduli di sicurezza hardware (HSM). Azure Key Vault è la soluzione consigliata da Microsoft per la gestione e il controllo dell'accesso alle chiavi di crittografia utilizzate dai servizi cloud. È possibile assegnare le autorizzazioni per i tasti di accesso ai servizi o agli utenti con account di Azure Active Directory. Il Vault Key di Azure allevia le organizzazioni della necessità di configurare, applicare patch e gestire HSM e il software di gestione delle chiavi. Con Vault Key di Azure, Microsoft non vede mai le chiavi e le applicazioni non hanno accesso diretto a loro; mantenere il controllo. È inoltre possibile importare o generare chiavi in HSM. Le organizzazioni che dispongono di un abbonamento che include Azure Information Protection possono configurare il tenant di Azure Information Protection per utilizzare una chiave gestita dal cliente per [portare la propria chiave](https://docs.microsoft.com/information-protection/plan-design/byok-price-restrictions) (BYOK)) e [registrarne l'utilizzo](https://docs.microsoft.com/information-protection/deploy-use/log-analyze-usage).
