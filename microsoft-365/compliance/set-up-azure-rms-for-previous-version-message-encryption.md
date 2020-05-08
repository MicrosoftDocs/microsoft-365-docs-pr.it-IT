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
description: La versione precedente della crittografia dei messaggi di Office 365 dipende da Microsoft Azure Rights Management (precedentemente noto come Windows Azure Active Directory Rights Management).
ms.openlocfilehash: 879f4ec1db8a8cfe1fe3c8d3b1dd9e1fc68dd687
ms.sourcegitcommit: 46644f9778bc70ab6d62783e0a1e60ba2eccc27f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2020
ms.locfileid: "44165917"
---
# <a name="set-up-azure-rights-management-for-the-previous-version-of-message-encryption"></a>Configurare Azure Rights Management per la versione precedente della crittografia dei messaggi

In questo argomento vengono descritti i passaggi da seguire per poter attivare e configurare Azure Rights Management (RMS), parte di Azure Information Protection, per l'utilizzo con la versione precedente di Office 365 Message Encryption (OME).

## <a name="this-article-only-applies-to-the-previous-version-of-ome"></a>Questo articolo si applica solo alla versione precedente di OME

Se l'organizzazione non è stata ancora spostata nelle nuove funzionalità OME, ma è già stata distribuita OME, le informazioni contenute in questo articolo si applicano all'organizzazione. Microsoft consiglia di effettuare un piano per passare alle nuove funzionalità OME non appena è ragionevole per la propria organizzazione. Per istruzioni, vedere [configurare le nuove funzionalità di crittografia dei messaggi di Office 365](set-up-new-message-encryption-capabilities.md). Per ulteriori informazioni sul funzionamento delle nuove funzionalità, vedere [crittografia dei messaggi di Office 365](ome.md). Il resto di questo articolo si riferisce al comportamento OME prima del rilascio delle nuove funzionalità OME.

## <a name="prerequisites-for-using-the-previous-version-of-office-365-message-encryption"></a>Prerequisiti per l'utilizzo della versione precedente della crittografia dei messaggi di Office 365
<a name="warmprereqs"> </a>

La crittografia dei messaggi di Office 365 (OME), tra cui IRM, dipende da Azure Rights Management (Azure RMS). Azure RMS è la tecnologia di protezione utilizzata da Azure Information Protection. Per utilizzare OME, è necessario che l'organizzazione includa un abbonamento a Exchange Online o Exchange Online Protection che, a sua sua disposizione, includa una sottoscrizione di Azure Rights Management.
  
- Se non si è sicuri di cosa include la sottoscrizione, vedere le descrizioni del servizio Exchange Online per i [criteri dei messaggi, il ripristino e la conformità](https://technet.microsoft.com/library/exchange-online-message-policy-recovery-and-compliance.aspx).

- Se si dispone di Azure Rights Management, ma non è configurato per Exchange Online o Exchange Online Protection, in questo articolo viene illustrato come attivare Azure Rights Management e quindi viene descritto il modo migliore per configurare OME per l'utilizzo con Azure Rights Management.

- Se la OME è già stata configurata per l'utilizzo con Azure Rights Management per Exchange Online o Exchange Online Protection, a seconda del modo in cui è stata configurata, potrebbe essere possibile iniziare a utilizzare OME e le sue nuove funzionalità subito. In questo articolo viene illustrato come determinare se è stato impostato correttamente OME, cosa fare se è necessario modificare la configurazione e cosa succede se si sceglie di non modificare la configurazione. Ad esempio, per poter utilizzare le nuove funzionalità, è necessario utilizzare Azure RMS con OME. Non è possibile utilizzare le nuove funzionalità con un RMS di Active Directory locale.

## <a name="activate-azure-rights-management-for--the-previous-version-of-ome-in-office-365"></a>Attivare Azure Rights Management per la versione precedente di OME in Office 365

È necessario attivare Azure Rights Management in modo che gli utenti dell'organizzazione possano applicare la protezione delle informazioni ai messaggi inviati e aprire i messaggi e i file protetti dal servizio Azure Rights Management. Per istruzioni, vedere [attivazione di Azure Rights Management](https://go.microsoft.com/fwlink/p/?LinkId=525775). Dopo aver completato l'attivazione, tornare qui e continuare con le attività descritte in questo articolo.
  
## <a name="set-up-the-previous-version-of-ome-to-use-azure-rms-by-importing-trusted-publishing-domains-tpds"></a>Impostare la versione precedente di OME per l'utilizzo di Azure RMS importando domini di pubblicazione trusted (pubblicazione trusted)

Un dominio di pubblicazione trusted è un file XML che contiene informazioni sulle impostazioni di gestione dei diritti dell'organizzazione. Ad esempio, il dominio di pubblicazione trusted contiene informazioni sul certificato concessore di licenze server (SLC) utilizzato per la firma e la crittografia dei certificati e della licenza, gli URL utilizzati per la gestione delle licenze e la pubblicazione e così via. Si importa il dominio di pubblicazione trusted nell'organizzazione tramite Windows PowerShell.
  
> [!IMPORTANT]
> In precedenza, è possibile scegliere di importare pubblicazione trusted da Active Directory Rights Management Service (AD RMS) nell'organizzazione. Tuttavia, in questo modo si eviterà di utilizzare le nuove funzionalità OME e non è consigliabile. Se l'organizzazione è attualmente configurata in questo modo, Microsoft consiglia di creare un piano per la migrazione dall'RMS di Active Directory locale a cloud-based Azure Information Protection. Per ulteriori informazioni, vedere [migrazione da ad RMS a Azure Information Protection](https://docs.microsoft.com/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms). Non sarà possibile utilizzare le nuove funzionalità OME fino a quando non è stata completata la migrazione a Azure Information Protection.
  
 **Per importare pubblicazione trusted da Azure RMS**
  
1. [Connettersi a Exchange Online tramite Remote PowerShell](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx).

2. Scegliere l'URL di condivisione delle chiavi corrispondente alla posizione geografica dell'organizzazione:

|**Posizione**|**URL del percorso di condivisione della chiave**|
|:-----|:-----|
|Nord America  <br/> |https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|Unione Europea  <br/> |https://sp-rms.eu.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|Asia  <br/> |https://sp-rms.ap.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|Sud America  <br/> |https://sp-rms.sa.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|Office 365 per il governo (Government Community Cloud)  <br/> Questo percorso di condivisione della chiave di RMS è riservato ai clienti che hanno acquistato Office 365 per gli SKU governativi.  <br/> |https://sp-rms.govus.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
  
3. Configurare il percorso di condivisione della chiave eseguendo il cmdlet [Set-IRMConfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.160%29.aspx) come indicato di seguito: 

   ```powershell
   Set-IRMConfiguration -RMSOnlineKeySharingLocation "<RMSKeySharingURL >"
   ```
  
   Ad esempio, per configurare il percorso di condivisione della chiave se l'organizzazione si trova in Nord America:

   ```powershell
   Set-IRMConfiguration -RMSOnlineKeySharingLocation "https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc"
   ```

4. Eseguire il cmdlet [Import-RMSTrustedPublishingDomain](https://technet.microsoft.com/library/jj200724%28v=exchg.150%29.aspx) con l'opzione-RMSOnline per importare il dominio di pubblicazione trusted da Azure Rights Management: 

   ```powershell
   Import-RMSTrustedPublishingDomain -RMSOnline -Name "<TPDName> "
   ```

   Dove *TPDName* è il nome che si desidera utilizzare per il dominio di pubblicazione trusted. Ad esempio, "contoso North American di pubblicazione trusted". 

5. Per verificare che l'organizzazione sia stata configurata correttamente per l'utilizzo del servizio Azure Rights Management, eseguire il cmdlet [Test-IRMConfiguration](https://technet.microsoft.com/library/dd979798%28v=exchg.160%29.aspx) con l'opzione-RMSOnline, come indicato di seguito:

   ```powershell
   Test-IRMConfiguration -RMSOnline
   ```

   Tra le altre cose, questo cmdlet consente di verificare la connettività con il servizio Azure Rights Management, di scaricare il dominio di pubblicazione trusted e di verificarne la validità.

6. Eseguire il cmdlet [Set-IRMConfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.150%29.aspx) come segue per disabilitare i modelli di Azure Rights Management disponibili in Outlook sul Web e Outlook: 

   ```powershell
   Set-IRMConfiguration -ClientAccessServerEnabled $false
   ```

7. Eseguire il cmdlet [Set-IRMConfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.150%29.aspx) come segue per abilitare Azure Rights Management per l'organizzazione di posta elettronica basata sul cloud e configurarla per l'utilizzo di Azure Rights Management per la crittografia dei messaggi di Office 365:

   ```powershell
   Set-IRMConfiguration -InternalLicensingEnabled $true
   ```

8. Per verificare di aver importato correttamente il dominio di pubblicazione trusted e abilitato Azure Rights Management, utilizzare il cmdlet Test-IRMConfiguration per testare la funzionalità di Azure Rights Management. Per informazioni dettagliate, vedere "Esempio 1" in [Test-IRMConfiguration](https://technet.microsoft.com/library/dd979798%28v=exchg.150%29.aspx).

## <a name="i-have-the-previous-version-of-ome-set-up-with-active-directory-rights-management-not-azure-information-protection-what-do-i-do"></a>La versione precedente di OME è stata configurata con Active Directory Rights Management non Azure Information Protection, cosa fare?
<a name="importTPDs"> </a>

È possibile continuare a utilizzare le regole del flusso di posta di crittografia dei messaggi di Office 365 con Active Directory Rights Management, ma non è possibile configurare o utilizzare le nuove funzionalità OME. Al contrario, è necessario eseguire la migrazione a Azure Information Protection. Per informazioni sulla migrazione e su cosa significa per la propria organizzazione, vedere [migrazione da ad RMS a Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/prepare-environment-adrms).
  
## <a name="next-steps"></a>Passaggi successivi
<a name="importTPDs"> </a>

Dopo aver completato il programma di installazione di Azure Rights Management, se si desidera abilitare le nuove funzionalità OME, vedere [configurare le nuove funzionalità di crittografia dei messaggi di Office 365 basate su Azure Information Protection.](https://docs.microsoft.com/microsoft-365/compliance/set-up-new-message-encryption-capabilities)
  
Dopo aver configurato l'organizzazione per l'utilizzo delle nuove funzionalità OME, è possibile [definire le regole del flusso di posta per proteggere i messaggi di posta elettronica con le nuove funzionalità ome](define-mail-flow-rules-to-encrypt-email.md).
  
## <a name="related-topics"></a>Argomenti correlati
<a name="importTPDs"> </a>

[Crittografia in Office 365](encryption.md)
  
[Dettagli tecnici di riferimento sulla crittografia in Office 365](technical-reference-details-about-encryption.md)
  
[Informazioni su Azure Rights Management](https://docs.microsoft.com/information-protection/understand-explore/what-is-azure-rms)
