---
title: Configurare Azure Rights Management per la versione precedente di Crittografia messaggi
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/30/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 2cba47b3-f09e-4911-9207-ac056fcb9db7
description: La versione precedente della crittografia dei messaggi di Office 365 dipende da Microsoft Azure Rights Management (precedentemente noto come Windows Azure Active Directory Rights Management).
ms.openlocfilehash: 978a8027c79de574b80aeedabcbbd51fa6f9e2a0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919492"
---
# <a name="set-up-azure-rights-management-for-the-previous-version-of-message-encryption"></a>Configurare Azure Rights Management per la versione precedente di Crittografia messaggi

In questo argomento vengono descritti i passaggi da seguire per attivare e configurare Azure Rights Management (RMS), parte di Azure Information Protection, per l'utilizzo con la versione precedente di Office 365 Message Encryption (OME).

## <a name="this-article-only-applies-to-the-previous-version-of-ome"></a>Questo articolo si applica solo alla versione precedente di OME

Se l'organizzazione non è stata ancora spostata nelle nuove funzionalità OME, ma si è già distribuito OME, le informazioni contenute in questo articolo si applicano all'organizzazione. Microsoft consiglia di pianificare il passaggio alle nuove funzionalità OME non appena è ragionevole per l'organizzazione. Per istruzioni, vedere [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md). Per ulteriori informazioni sul funzionamento delle nuove funzionalità, vedere Crittografia dei messaggi di [Office 365.](ome.md) Il resto di questo articolo fa riferimento al comportamento OME prima del rilascio delle nuove funzionalità OME.

## <a name="prerequisites-for-using-the-previous-version-of-office-365-message-encryption"></a>Prerequisiti per l'utilizzo della versione precedente di Crittografia messaggi di Office 365
<a name="warmprereqs"> </a>

Crittografia messaggi di Office 365 (OME), incluso IRM, dipende da Azure Rights Management (Azure RMS). Azure RMS è la tecnologia di protezione utilizzata da Azure Information Protection. Per usare OME, l'organizzazione deve includere un abbonamento a Exchange Online o Exchange Online Protection che, a sua volta, include una sottoscrizione di Azure Rights Management.
  
- Se non si è certi di cosa include l'abbonamento, vedere le descrizioni del servizio Exchange Online per Criteri [messaggio, ripristino e conformità.](/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)

- Se si dispone di Azure Rights Management ma non è configurato per Exchange Online o Exchange Online Protection, questo articolo spiega come attivare Azure Rights Management e quindi descrive il modo migliore per configurare OME per l'utilizzo con Azure Rights Management.

- Se OME è già stato configurato per l'utilizzo con Azure Rights Management per Exchange Online o Exchange Online Protection, a seconda di come è stato configurato, potrebbe essere possibile iniziare subito a usare OME e le nuove funzionalità. Questo articolo spiega come determinare se OME è stato configurato correttamente, cosa fare se è necessario modificare la configurazione e cosa succede se si sceglie di non modificare la configurazione. Ad esempio, per usare le nuove funzionalità, è necessario usare Azure RMS con OME. Non è possibile utilizzare le nuove funzionalità con un server Active Directory RMS locale.

## <a name="activate-azure-rights-management-for--the-previous-version-of-ome-in-office-365"></a>Attivare Azure Rights Management per la versione precedente di OME in Office 365

È necessario attivare Azure Rights Management in modo che gli utenti dell'organizzazione possano applicare la protezione delle informazioni ai messaggi inviati e aprire i messaggi e i file protetti dal servizio Azure Rights Management. Per istruzioni, vedere [Attivazione di Azure Rights Management.](/azure/information-protection/activate-service) Dopo aver completato l'attivazione, tornare qui e continuare con le attività in questo articolo.
  
## <a name="set-up-the-previous-version-of-ome-to-use-azure-rms-by-importing-trusted-publishing-domains-tpds"></a>Configurare la versione precedente di OME per l'utilizzo di Azure RMS importando domini di pubblicazione trusted (TPD)

Un TPD è un file XML che contiene informazioni sulle impostazioni di rights management dell'organizzazione. Ad esempio, il TPD contiene informazioni sul certificato di licenza del server (SLC) utilizzato per firmare e crittografare certificati e licenze, sugli URL utilizzati per le licenze e la pubblicazione e così via. È possibile importare il TPD nell'organizzazione usando Windows PowerShell.
  
> [!IMPORTANT]
> In precedenza, è possibile scegliere di importare IPD da Active Directory Rights Management Service (AD RMS) nell'organizzazione. Tuttavia, questa operazione impedirà l'utilizzo delle nuove funzionalità OME e non è consigliata. Se l'organizzazione è attualmente configurata in questo modo, Microsoft consiglia di creare un piano per la migrazione da Active Directory RMS locale ad Azure Information Protection basato su cloud. Per ulteriori informazioni, vedere [Migrating from AD RMS to Azure Information Protection.](/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms) Non sarà possibile usare le nuove funzionalità OME fino a quando non sarà stata completata la migrazione ad Azure Information Protection.
  
 **Per importare TPD da Azure RMS**
  
1. [Connettersi a Exchange Online utilizzando Remote PowerShell.](/powershell/exchange/connect-to-exchange-online-powershell)

2. Scegliere l'URL di condivisione delle chiavi che corrisponde alla posizione geografica dell'organizzazione:

|**Posizione**|**URL percorso condivisione chiave**|
|:-----|:-----|
|Nord America  <br/> |https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|Unione Europea  <br/> |https://sp-rms.eu.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|Asia  <br/> |https://sp-rms.ap.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|Sud America  <br/> |https://sp-rms.sa.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|Office 365 per il governo (Government Community Cloud)  <br/> Questa posizione di condivisione delle chiavi RMS è riservata ai clienti che hanno acquistato SKU di Office 365 per enti pubblici.  <br/> |https://sp-rms.govus.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
  
3. Configurare il percorso di condivisione delle chiavi eseguendo il cmdlet [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) come segue: 

   ```powershell
   Set-IRMConfiguration -RMSOnlineKeySharingLocation "<RMSKeySharingURL >"
   ```
  
   Ad esempio, per configurare il percorso di condivisione delle chiavi se l'organizzazione si trova in Nord America:

   ```powershell
   Set-IRMConfiguration -RMSOnlineKeySharingLocation "https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc"
   ```

4. Eseguire il cmdlet [Import-RMSTrustedPublishingDomain](/powershell/module/exchange/import-rmstrustedpublishingdomain) con l'opzione -RMSOnline per importare il dominio di pubblicazione pubblicazione siti da Azure Rights Management: 

   ```powershell
   Import-RMSTrustedPublishingDomain -RMSOnline -Name "<TPDName> "
   ```

   Dove  *TPDName*  è il nome che si desidera utilizzare per il dominio TPD. Ad esempio, "Contoso North American TPD". 

5. Per verificare la corretta configurazione dell'organizzazione per l'utilizzo del servizio Azure Rights Management, eseguire il cmdlet [Test-IRMConfiguration](/powershell/module/exchange/test-irmconfiguration) con l'opzione -RMSOnline come indicato di seguito:

   ```powershell
   Test-IRMConfiguration -RMSOnline
   ```

   Tra l'altro, questo cmdlet controlla la connettività con il servizio Azure Rights Management, scarica il disco di distribuzione di active directory e ne verifica la validità.

6. Eseguire il cmdlet [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) come indicato di seguito per disabilitare la disponibilità dei modelli di Azure Rights Management in Outlook sul Web e Outlook: 

   ```powershell
   Set-IRMConfiguration -ClientAccessServerEnabled $false
   ```

7. Eseguire il cmdlet [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) come segue per abilitare Azure Rights Management per l'organizzazione di posta elettronica basata su cloud e configurarlo per l'utilizzo di Azure Rights Management per la crittografia dei messaggi di Office 365:

   ```powershell
   Set-IRMConfiguration -InternalLicensingEnabled $true
   ```

8. Per verificare di aver importato correttamente il disco di distribuzione di azure e aver abilitato Azure Rights Management, utilizzare il cmdlet Test-IRMConfiguration per testare la funzionalità Azure Rights Management. Per informazioni dettagliate, vedere "Esempio 1" in [Test-IRMConfiguration](/powershell/module/exchange/test-irmconfiguration).

## <a name="i-have-the-previous-version-of-ome-set-up-with-active-directory-rights-management-not-azure-information-protection-what-do-i-do"></a>La versione precedente di OME è stata impostata con Active Directory Rights Management e non con Azure Information Protection, cosa devo fare?
<a name="importTPDs"> </a>

È possibile continuare a usare le regole esistenti del flusso di posta di Crittografia messaggi di Office 365 con Active Directory Rights Management, ma non è possibile configurare o usare le nuove funzionalità OME. È invece necessario eseguire la migrazione ad Azure Information Protection. Per informazioni sulla migrazione e su cosa significa per l'organizzazione, vedere [Migrating from AD RMS to Azure Information Protection.](/information-protection/deploy-use/prepare-environment-adrms)
  
## <a name="next-steps"></a>Passaggi successivi
<a name="importTPDs"> </a>

Dopo aver completato la configurazione di Azure Rights Management, se si desidera abilitare le nuove funzionalità OME, vedere [Set up new Office 365 Message Encryption capabilities built on top of Azure Information Protection.](./set-up-new-message-encryption-capabilities.md)
  
Dopo aver configurato l'organizzazione per l'utilizzo delle nuove funzionalità OME, è possibile definire le regole del flusso di posta per proteggere i messaggi di posta elettronica con nuove [funzionalità OME.](define-mail-flow-rules-to-encrypt-email.md)
  
## <a name="related-topics"></a>Argomenti correlati
<a name="importTPDs"> </a>

[Crittografia in Office 365](encryption.md)
  
[Dettagli tecnici di riferimento sulla crittografia in Office 365](technical-reference-details-about-encryption.md)
  
[Informazioni su Azure Rights Management](/information-protection/understand-explore/what-is-azure-rms)