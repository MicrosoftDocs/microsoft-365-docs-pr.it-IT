---
title: Eseguire il rollforward o la rotazione di una chiave del cliente o di una chiave di disponibilità
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 02/05/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Informazioni su come eseguire il rollback delle chiavi principali del cliente archiviate in Azure Key Vault che vengono utilizzate con la chiave del cliente di Office 365. I servizi includono Exchange Online, Skype for business, SharePoint Online, OneDrive for business e i file dei team.
ms.openlocfilehash: 9699960666eaa9aa62bb027d3a4549cb50cd52e3
ms.sourcegitcommit: 5ff1dc62e8855be155cb2de45cf4ee5a02c321fd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41804812"
---
# <a name="roll-or-rotate-a-customer-key-or-an-availability-key"></a>Eseguire il rollforward o la rotazione di una chiave del cliente o di una chiave di disponibilità

> [!CAUTION]
> Eseguire il rollforward di una chiave di crittografia da utilizzare con il codice "Customer Key" quando i requisiti di sicurezza o conformità prevedono che è necessario ripristinare la chiave. Inoltre, non eliminare le chiavi che sono o sono state associate ai criteri. Quando si esegue il rollback delle chiavi, verranno crittografati i contenuti con le chiavi precedenti. Ad esempio, mentre le cassette postali attive verranno crittografate di frequente, le cassette postali inattive, disconnesse e disabilitate potrebbero essere ancora crittografate con le chiavi precedenti. SharePoint Online esegue il backup del contenuto per scopi di ripristino e ripristino, per cui è possibile che il contenuto archiviato sia ancora utilizzato con i tasti precedenti.

## <a name="about-rolling-the-availability-key"></a>Informazioni su Rolling The availability Key

Microsoft non espone il controllo diretto della chiave di disponibilità ai clienti. Ad esempio, è possibile eseguire il rollback solo delle chiavi di cui si dispone in Azure Key Vault. Office 365 esegue il rollback delle chiavi di disponibilità in base a una pianificazione definita internamente. Non è previsto alcun contratto di servizio per questi rotoli di chiavi. Office 365 ruota la chiave di disponibilità utilizzando il codice del servizio di Office 365 in un processo automatizzato e non manuale. Gli amministratori di Microsoft possono avviare il processo di rollforward. La chiave viene rotolata utilizzando meccanismi automatici senza accesso diretto all'archivio delle chiavi. L'accesso all'archivio segreto della chiave di disponibilità non viene eseguito a Microsoft Administrators. Chiave di disponibilità la rotazione utilizza lo stesso meccanismo utilizzato per generare inizialmente la chiave. Per ulteriori informazioni sulla chiave di disponibilità, vedere [understand the availability Key](customer-key-availability-key-understand.md).

> [!IMPORTANT]
> Le chiavi di disponibilità di Exchange Online e Skype for business possono essere effettivamente arrotolate dai clienti che creano una nuova funzionalità di protezione esecuzione programmi, poiché viene generata una chiave di disponibilità univoca per ogni DEP creato. Le chiavi di disponibilità per SharePoint Online, OneDrive for business e i file di teams esistono a livello di foresta e sono condivise tra DEPs e Customers, il che significa che il rollforward si verifica solo in base a una pianificazione definita internamente da Microsoft. Per ridurre il rischio di non rotolare la chiave di disponibilità ogni volta che viene creata una nuova protezione esecuzione programmi, SharePoint, OneDrive e teams eseguono il rollforward del tasto di intermediazione del tenant, la chiave racchiusa tra le chiavi principali del cliente e la chiave di disponibilità, ogni volta che viene creata una nuova protezione esecuzione programmi.

## <a name="request-a-new-version-of-each-existing-root-key-you-want-to-roll"></a>Richiedere una nuova versione di ogni chiave radice esistente che si desidera eseguire il rollback

Quando si esegue il rollback di una chiave, viene richiesta una nuova versione di una chiave esistente. Per richiedere una nuova versione di una chiave esistente, è necessario utilizzare lo stesso cmdlet [Add-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/add-azkeyvaultkey), con la stessa sintassi utilizzata per creare la chiave in primo luogo. Dopo aver completato il rollforward di qualsiasi tasto associato a un criterio di crittografia dei dati, è possibile eseguire un altro cmdlet per assicurarsi che la chiave del cliente inizi a utilizzare la nuova chiave. Eseguire questo passaggio in ogni Vault Key di Azure (AKV).

Ad esempio:

1. Accedere alla sottoscrizione di Azure con Azure PowerShell. Per istruzioni, vedere [accedere con Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).

2. Eseguire il cmdlet Add-AzKeyVaultKey come illustrato nell'esempio seguente:

   ```powershell
   Add-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination HSM -KeyOps @('wrapKey','unwrapKey') -NotBefore (Get-Date -Date "12/27/2016 12:01 AM")
   ```

   In questo esempio, poiché una chiave denominata **Contoso-O365EX-na-VaultA1-Key001** esiste nel Vault **Contoso-O365EX-na-VaultA1** , il cmdlet crea una nuova versione della chiave. Questa operazione consente di conservare le versioni principali precedenti nella cronologia delle versioni per la chiave. È necessaria la versione precedente della chiave per decrittografare i dati che vengono ancora crittografati. Dopo aver completato il rollforward di qualsiasi tasto associato a una funzionalità di protezione esecuzione programmi, eseguire un cmdlet aggiuntivo per assicurarsi che la chiave del cliente inizi a utilizzare la nuova chiave. Nelle sezioni seguenti vengono descritti i cmdlet in modo più dettagliato.
  
## <a name="update-the-customer-key-for-exchange-online-and-skype-for-business"></a>Aggiornare la chiave del cliente per Exchange Online e Skype for business

Quando si esegue il rollback delle chiavi del Vault Key di Azure associate a una DEP utilizzata con Exchange Online e Skype for business, è necessario aggiornare la funzionalità DEP in modo che punti alla nuova chiave. La chiave di disponibilità non viene ruotata.

Per indicare alla chiave del cliente di utilizzare la nuova chiave per crittografare le cassette postali in Office 365, eseguire il cmdlet Set-DataEncryptionPolicy come indicato di seguito:

1. Eseguire il cmdlet Set-DataEncryptionPolicy in Azure PowerShell:
  
   ```powershell
   Set-DataEncryptionPolicy -Identity <DataEncryptionPolicyID> -Refresh
   ```

   Entro 72 ore, le cassette postali attive associate a questo DEP diventano crittografate con la nuova chiave.

2. Per controllare il valore della proprietà DataEncryptionPolicyID per la cassetta postale, attenersi alla procedura descritta in [determinare la funzionalità DEP assegnata a una cassetta postale](customer-key-manage.md#determine-the-dep-assigned-to-a-mailbox). Il valore di questa proprietà viene modificato dopo che il servizio ha applicato la chiave aggiornata.
  
## <a name="update-the-customer-key-for-sharepointonlineonedriveforbusinessandteamsfiles"></a>Aggiornare la chiave del cliente per i file di SharePoint Online, OneDrive for business e teams

SharePoint Online consente solo di eseguire il rollforward di una chiave alla volta. Se si desidera eseguire il rollforward di entrambe le chiavi in un Vault chiave, attendere che venga completata la prima operazione. Microsoft consiglia di scaglionare le operazioni per evitare questo problema. Quando si esegue il rollback delle chiavi del Vault Key di Azure associate a una DEP utilizzata con SharePoint Online e OneDrive for business, è necessario aggiornare la funzionalità DEP in modo che punti alla nuova chiave. La chiave di disponibilità non viene ruotata.

1. Eseguire il cmdlet Update-SPODataEncryptionPolicy come indicato di seguito:
  
   ```powershell
   Update-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl> -KeyVaultName <ReplacementKeyVaultName> -KeyName <ReplacementKeyName> -KeyVersion <ReplacementKeyVersion> -KeyType <Primary | Secondary>
   ```

   Anche se questo cmdlet avvia l'operazione di rollforward delle chiavi per SharePoint Online e OneDrive for business, l'azione non viene completata immediatamente.

2. Per visualizzare lo stato dell'operazione di rollforward delle chiavi, eseguire il cmdlet Get-SPODataEncryptionPolicy nel modo riportato di seguito:

   ```powershell
   Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
   ```

## <a name="related-articles"></a>Articoli correlati

- [Crittografia del servizio con la chiave del cliente per Office 365](customer-key-overview.md)

- [Configurare la chiave cliente per Office 365](customer-key-set-up.md)

- [Gestire la chiave del cliente per Office 365](customer-key-manage.md)

- [Informazioni sulla chiave di disponibilità](customer-key-availability-key-understand.md)
