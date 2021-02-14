---
title: Configurare Azure Rights Management per la versione precedente della crittografia dei messaggi
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
description: La versione precedente della crittografia dei messaggi di Office 365 dipende da Microsoft Azure Rights Management (in precedenza noto come Windows Azure Active Directory Rights Management).
ms.openlocfilehash: 879f4ec1db8a8cfe1fe3c8d3b1dd9e1fc68dd687
ms.sourcegitcommit: 46644f9778bc70ab6d62783e0a1e60ba2eccc27f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2020
ms.locfileid: "44165917"
---
# <a name="set-up-azure-rights-management-for-the-previous-version-of-message-encryption"></a>Configurare Azure Rights Management per la versione precedente della crittografia dei messaggi

In questo argomento vengono descritti i passaggi da seguire per attivare e configurare Azure Rights Management (RMS), parte di Azure Information Protection, da utilizzare con la versione precedente di Office 365 Message Encryption (OME).

## <a name="this-article-only-applies-to-the-previous-version-of-ome"></a>Questo articolo si applica solo alla versione precedente di OME

Se l'organizzazione non è stata ancora spostata nelle nuove funzionalità di OME, ma OME è già stato distribuito, le informazioni contenute in questo articolo si applicano all'organizzazione. Microsoft consiglia di pianificare il passaggio alle nuove funzionalità di OME non appena è ragionevole per l'organizzazione. Per istruzioni, vedere Configurare le nuove funzionalità di crittografia dei [messaggi di Office 365.](set-up-new-message-encryption-capabilities.md) Per ulteriori informazioni sul funzionamento delle nuove funzionalità, vedere Crittografia messaggi di [Office 365.](ome.md) Il resto di questo articolo fa riferimento al comportamento di OME prima del rilascio delle nuove funzionalità di OME.

## <a name="prerequisites-for-using-the-previous-version-of-office-365-message-encryption"></a>Prerequisiti per l'utilizzo della versione precedente della crittografia dei messaggi di Office 365
<a name="warmprereqs"> </a>

Office 365 Message Encryption (OME), incluso IRM, dipende da Azure Rights Management (Azure RMS). Azure RMS è la tecnologia di protezione usata da Azure Information Protection. Per utilizzare OME, l'organizzazione deve includere una sottoscrizione di Exchange Online o Exchange Online Protection che, a sua volta, includa una sottoscrizione di Azure Rights Management.
  
- Se non si è sicuri di cosa include l'abbonamento, vedere le descrizioni del servizio Exchange Online per i criteri dei messaggi, il ripristino [e la conformità.](https://technet.microsoft.com/library/exchange-online-message-policy-recovery-and-compliance.aspx)

- Se si dispone di Azure Rights Management ma non è configurato per Exchange Online o Exchange Online Protection, questo articolo spiega come attivare Azure Rights Management e quindi descrive il modo migliore per configurare OME per l'utilizzo con Azure Rights Management.

- Se OME è già stato configurato per l'uso con Azure Rights Management per Exchange Online o Exchange Online Protection, a seconda di come è stato configurato, è possibile iniziare subito a usare OME e le nuove funzionalità. Questo articolo spiega come determinare se OME è stato configurato correttamente, cosa fare se è necessario modificare la configurazione e cosa succede se si sceglie di non modificare la configurazione. Ad esempio, per usare le nuove funzionalità, è necessario usare Azure RMS con OME. Non è possibile utilizzare le nuove funzionalità con un server Active Directory RMS locale.

## <a name="activate-azure-rights-management-for--the-previous-version-of-ome-in-office-365"></a>Attivare Azure Rights Management per la versione precedente di OME in Office 365

È necessario attivare Azure Rights Management in modo che gli utenti dell'organizzazione possano applicare la protezione delle informazioni ai messaggi inviati e aprire i messaggi e i file protetti dal servizio Azure Rights Management. Per istruzioni, vedere [Attivazione di Azure Rights Management.](https://go.microsoft.com/fwlink/p/?LinkId=525775) Dopo aver completato l'attivazione, torna qui e continua con le attività in questo articolo.
  
## <a name="set-up-the-previous-version-of-ome-to-use-azure-rms-by-importing-trusted-publishing-domains-tpds"></a>Configurare la versione precedente di OME per l'utilizzo di Azure RMS importando domini di pubblicazione trusted (TPD)

Un TPD è un file XML che contiene informazioni sulle impostazioni di rights management dell'organizzazione. Ad esempio, il TPD contiene informazioni sul certificato concessore di licenze server (SLC) usato per firmare e crittografare certificati e licenze, gli URL utilizzati per la gestione delle licenze e la pubblicazione e così via. Puoi importare il TPD nell'organizzazione usando Windows PowerShell.
  
> [!IMPORTANT]
> In precedenza, era possibile scegliere di importare IPD da Active Directory Rights Management Service (AD RMS) nell'organizzazione. In questo modo, tuttavia, non è possibile utilizzare le nuove funzionalità di OME e non è consigliabile. Se l'organizzazione è attualmente configurata in questo modo, Microsoft consiglia di creare un piano per la migrazione da Active Directory RMS locale a Azure Information Protection basato su cloud. Per ulteriori informazioni, vedere [Migrazione da AD RMS ad Azure Information Protection.](https://docs.microsoft.com/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms) Non sarà possibile utilizzare le nuove funzionalità di OME fino a quando non sarà stata completata la migrazione ad Azure Information Protection.
  
 **Per importare TPD da Azure RMS**
  
1. [Connettersi a Exchange Online utilizzando Remote PowerShell.](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx)

2. Scegliere l'URL di condivisione delle chiavi che corrisponde alla posizione geografica dell'organizzazione:

|**Posizione**|**URL percorso di condivisione chiave**|
|:-----|:-----|
|Nord America  <br/> |https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|Unione Europea  <br/> |https://sp-rms.eu.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|Asia  <br/> |https://sp-rms.ap.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|Sud America  <br/> |https://sp-rms.sa.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|Office 365 per il governo (Government Community Cloud)  <br/> Questa posizione di condivisione delle chiavi RMS è riservata ai clienti che hanno acquistato Office 365 per SKU per enti pubblici.  <br/> |https://sp-rms.govus.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
  
3. Configurare il percorso di condivisione delle chiavi eseguendo il cmdlet [Set-IRMConfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.160%29.aspx) nel modo seguente: 

   ```powershell
   Set-IRMConfiguration -RMSOnlineKeySharingLocation "<RMSKeySharingURL >"
   ```
  
   Ad esempio, per configurare il percorso di condivisione delle chiavi se l'organizzazione si trova in Nord America:

   ```powershell
   Set-IRMConfiguration -RMSOnlineKeySharingLocation "https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc"
   ```

4. Eseguire il cmdlet [Import-RMSTrustedPublishingDomain](https://technet.microsoft.com/library/jj200724%28v=exchg.150%29.aspx) con l'opzione -RMSOnline per importare il dominio di pubblicazione attendibile da Azure Rights Management: 

   ```powershell
   Import-RMSTrustedPublishingDomain -RMSOnline -Name "<TPDName> "
   ```

   Dove  *TPDName*  è il nome che si desidera utilizzare per il dominio di dominio di dominio di cui si desidera eseguire la ricerca. Ad esempio, "Contoso North American TPD". 

5. Per verificare la corretta configurazione dell'organizzazione per l'utilizzo del servizio Azure Rights Management, eseguire il cmdlet [Test-IRMConfiguration](https://technet.microsoft.com/library/dd979798%28v=exchg.160%29.aspx) con l'opzione -RMSOnline nel modo seguente:

   ```powershell
   Test-IRMConfiguration -RMSOnline
   ```

   Tra le altre cose, questo cmdlet controlla la connettività con il servizio Azure Rights Management, scarica il TPD e ne verifica la validità.

6. Eseguire il cmdlet [Set-IRMConfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.150%29.aspx) come indicato di seguito per disabilitare la disponibilità dei modelli di Azure Rights Management in Outlook sul Web e Outlook: 

   ```powershell
   Set-IRMConfiguration -ClientAccessServerEnabled $false
   ```

7. Eseguire il cmdlet [Set-IRMConfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.150%29.aspx) come indicato di seguito per abilitare Azure Rights Management per l'organizzazione di posta elettronica basata su cloud e configurarlo per l'utilizzo di Azure Rights Management per la crittografia dei messaggi di Office 365:

   ```powershell
   Set-IRMConfiguration -InternalLicensingEnabled $true
   ```

8. Per verificare di aver importato correttamente il TPD e abilitato Azure Rights Management, utilizzare il cmdlet Test-IRMConfiguration per testare la funzionalità Azure Rights Management. Per informazioni dettagliate, vedere "Esempio 1" in [Test-IRMConfiguration](https://technet.microsoft.com/library/dd979798%28v=exchg.150%29.aspx).

## <a name="i-have-the-previous-version-of-ome-set-up-with-active-directory-rights-management-not-azure-information-protection-what-do-i-do"></a>La versione precedente di OME è stata impostata con Active Directory Rights Management e non con Azure Information Protection, cosa fare?
<a name="importTPDs"> </a>

È possibile continuare a usare le regole esistenti del flusso di posta di Crittografia messaggi di Office 365 con Active Directory Rights Management, ma non è possibile configurare o usare le nuove funzionalità di OME. È invece necessario eseguire la migrazione ad Azure Information Protection. Per informazioni sulla migrazione e su cosa significa per l'organizzazione, vedere Migrazione da [AD RMS ad Azure Information Protection.](https://docs.microsoft.com/information-protection/deploy-use/prepare-environment-adrms)
  
## <a name="next-steps"></a>Passaggi successivi
<a name="importTPDs"> </a>

Dopo aver completato la configurazione di Azure Rights Management, se si desidera abilitare le nuove funzionalità di OME, vedere Configurare le nuove funzionalità di crittografia dei messaggi di [Office 365](https://docs.microsoft.com/microsoft-365/compliance/set-up-new-message-encryption-capabilities) integrate in Azure Information Protection.
  
Dopo aver configurato l'organizzazione per l'utilizzo delle nuove funzionalità di OME, è possibile definire le regole del flusso di posta per proteggere i messaggi di posta elettronica con le nuove [funzionalità di OME.](define-mail-flow-rules-to-encrypt-email.md)
  
## <a name="related-topics"></a>Argomenti correlati
<a name="importTPDs"> </a>

[Crittografia in Office 365](encryption.md)
  
[Dettagli tecnici di riferimento sulla crittografia in Office 365](technical-reference-details-about-encryption.md)
  
[Informazioni su Azure Rights Management](https://docs.microsoft.com/information-protection/understand-explore/what-is-azure-rms)
