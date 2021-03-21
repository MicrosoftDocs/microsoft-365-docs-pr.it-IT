---
title: Implementare o distribuire una Customer Key o una chiave di disponibilità
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
description: Scopri come eseguire il roll-to-roll delle chiavi radice dei clienti archiviate in Azure Key Vault usate con la chiave del cliente. I servizi includono i file di Exchange Online, Skype for Business, SharePoint Online, OneDrive for Business e Teams.
ms.openlocfilehash: 980d6b198b326cb75bb2b4ef4d2c980f605f23e5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923332"
---
# <a name="roll-or-rotate-a-customer-key-or-an-availability-key"></a>Implementare o distribuire una Customer Key o una chiave di disponibilità

> [!CAUTION]
> Implementare solo una chiave di crittografia che si usa con customer key quando i requisiti di sicurezza o conformità determinano che è necessario implementare la chiave. Inoltre, non eliminare le chiavi associate o associate ai criteri. Quando si esembono le chiavi, il contenuto verrà crittografato con le chiavi precedenti. Ad esempio, mentre le cassette postali attive verranno crittografate di frequente, le cassette postali inattive, disconnesse e disabilitate potrebbero comunque essere crittografate con le chiavi precedenti. SharePoint Online esegue il backup del contenuto per scopi di ripristino e ripristino, pertanto potrebbe essere ancora presente contenuto archiviato con chiavi precedenti.

## <a name="about-rolling-the-availability-key"></a>Informazioni sull'implementazione della chiave di disponibilità

Microsoft non espone ai clienti il controllo diretto della chiave di disponibilità. Ad esempio, è possibile ruotare solo le chiavi di cui si è proprietari in Azure Key Vault. Microsoft 365 esegue il roll delle chiavi di disponibilità in base a una pianificazione definita internamente. Non esiste un contratto di servizio (SLA) rivolto ai clienti per questi rotoli chiave. Microsoft 365 ruota la chiave di disponibilità usando il codice di servizio di Microsoft 365 in un processo automatizzato e non manuale. Gli amministratori Microsoft possono avviare il processo di roll. La chiave viene rollata utilizzando meccanismi automatizzati senza accesso diretto all'archivio chiavi. L'accesso all'archivio segreto chiave di disponibilità non viene effettuato agli amministratori Microsoft. L'implementazione della chiave di disponibilità sfrutta lo stesso meccanismo usato per generare inizialmente la chiave. Per ulteriori informazioni sulla chiave di disponibilità, vedere [Informazioni sulla chiave di disponibilità.](customer-key-availability-key-understand.md)

> [!IMPORTANT]
> Le chiavi di disponibilità di Exchange Online e Skype for Business possono essere effettivamente rollate dai clienti che creano una nuova protezione esecuzione programmi, poiché viene generata una chiave di disponibilità univoca per ogni protezione esecuzione programmi creata. Le chiavi di disponibilità per i file di SharePoint Online, OneDrive for Business e Teams sono presenti a livello di foresta e sono condivise tra dep e clienti, il che significa che il roll-on viene eseguito solo in base a una pianificazione definita internamente da Microsoft. Per ridurre il rischio di non implementare la chiave di disponibilità ogni volta che viene creata una nuova protezione esecuzione programmi, SharePoint, OneDrive e Teams rotolano la chiave intermedia tenant (TIK), la chiave racchiusa dalle chiavi radice del cliente e dalla chiave di disponibilità, ogni volta che viene creata una nuova protezione esecuzione programmi.

## <a name="request-a-new-version-of-each-existing-root-key-you-want-to-roll"></a>Richiedere una nuova versione di ogni chiave radice esistente che si desidera implementare

Quando si esegue il roll-to-roll di una chiave, si richiede una nuova versione di una chiave esistente. Per richiedere una nuova versione di una chiave esistente, utilizzare lo stesso [cmdlet, Add-AzKeyVaultKey](/powershell/module/az.keyvault/add-azkeyvaultkey), con la stessa sintassi utilizzata per creare la chiave. Dopo aver completato l'esecuzione di qualsiasi chiave associata a un criterio di crittografia dei dati, eseguire un altro cmdlet per assicurarsi che Customer Key inizi a utilizzare la nuova chiave. Eseguire questo passaggio in ogni Azure Key Vault (AKV).

Ad esempio:

1. Accedere alla sottoscrizione di Azure con Azure PowerShell. Per istruzioni, vedere [Sign in with Azure PowerShell](/powershell/azure/authenticate-azureps).

2. Eseguire il cmdlet Add-AzKeyVaultKey come illustrato nell'esempio seguente:

   ```powershell
   Add-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination HSM -KeyOps @('wrapKey','unwrapKey') -NotBefore (Get-Date -Date "12/27/2016 12:01 AM")
   ```

   In questo esempio, poiché una chiave denominata **Contoso-O365EX-NA-VaultA1-Key001** è presente nell'insieme di credenziali **Contoso-O365EX-NA-VaultA1,** il cmdlet crea una nuova versione della chiave. Questa operazione mantiene le versioni chiave precedenti nella cronologia delle versioni per la chiave. È necessaria la versione precedente della chiave per decrittografare i dati ancora crittografati. Dopo aver completato il rollover di una chiave associata a protezione esecuzione programmi, eseguire un cmdlet aggiuntivo per assicurarsi che customer key inizi a usare la nuova chiave. Le sezioni seguenti descrivono i cmdlet in modo più dettagliato.
  
## <a name="update-the-customer-key-for-exchange-online-and-skype-for-business"></a>Aggiornare il codice "Customer Key" per Exchange Online e Skype for Business

Quando si esegue il rollover di una delle chiavi dell'insieme di credenziali delle chiavi di Azure associate a una protezione esecuzione programmi utilizzata con Exchange Online e Skype for Business, è necessario aggiornare la funzionalità Protezione esecuzione programmi in modo che punti alla nuova chiave. In questo modo non viene ruotata la chiave di disponibilità.

Per indicare a Customer Key di utilizzare la nuova chiave per crittografare le cassette postali, eseguire il cmdlet Set-DataEncryptionPolicy seguente:

1. Eseguire il cmdlet Set-DataEncryptionPolicy in Azure PowerShell:
  
   ```powershell
   Set-DataEncryptionPolicy -Identity <DataEncryptionPolicyID> -Refresh
   ```

   Entro 72 ore, le cassette postali attive associate a protezione esecuzione programmi vengono crittografate con la nuova chiave.

2. Per controllare il valore della proprietà DataEncryptionPolicyID per la cassetta postale, utilizzare la procedura descritta in [Determine the DEP assigned to a mailbox](customer-key-manage.md#determine-the-dep-assigned-to-a-mailbox). Il valore di questa proprietà cambia dopo che il servizio ha applicato la chiave aggiornata.
  
## <a name="update-the-customer-key-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>Aggiornare il codice "Customer Key" per i file di SharePoint Online, OneDrive for Business e Teams

SharePoint Online consente di eseguire il roll-to-roll di una sola chiave alla volta. Se si desidera eseguire il roll-to-roll di entrambe le chiavi in un insieme di credenziali delle chiavi, attendere il completamento della prima operazione. Microsoft consiglia di scaglionare le operazioni per evitare questo problema. Quando si esegue il rollover di una delle chiavi di Azure Key Vault associate a una protezione esecuzione programmi usata con SharePoint Online e OneDrive for Business, è necessario aggiornare la funzionalità Protezione esecuzione programmi in modo che punti alla nuova chiave. In questo modo non viene ruotata la chiave di disponibilità.

1. Eseguire il cmdlet Update-SPODataEncryptionPolicy seguente:
  
   ```powershell
   Update-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl> -KeyVaultName <ReplacementKeyVaultName> -KeyName <ReplacementKeyName> -KeyVersion <ReplacementKeyVersion> -KeyType <Primary | Secondary>
   ```

   Mentre questo cmdlet avvia l'operazione di roll delle chiavi per SharePoint Online e OneDrive for Business, l'azione non viene completata immediatamente.

2. Per visualizzare lo stato dell'operazione di roll-to-key, eseguire il cmdlet Get-SPODataEncryptionPolicy seguente:

   ```powershell
   Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
   ```

## <a name="related-articles"></a>Articoli correlati

- [Crittografia del servizio con codice Cliente per Office 365](customer-key-overview.md)

- [Configurare Customer Key per Office 365](customer-key-set-up.md)

- [Gestire Customer Key per Office 365](customer-key-manage.md)

- [Informazioni sulla chiave di disponibilità](customer-key-availability-key-understand.md)