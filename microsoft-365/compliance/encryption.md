---
title: Crittografia
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 8/15/2019
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 0a322724-08ca-43db-b69a-afbfa20484cd
ms.collection:
- M365-security-compliance
- Strat_O365_IP
description: Con Office 365, il contenuto viene crittografato a riposo e in transito con la crittografia, i protocolli e le tecnologie più forti disponibili. Ottenere una panoramica della crittografia in Office 365.
ms.openlocfilehash: 2b1f2927b5d6daeb5e83aae2521d96e329e77c43
ms.sourcegitcommit: f80c6c52e5b08290f74baec1d64c4070046c32e4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/12/2020
ms.locfileid: "44717229"
---
# <a name="encryption"></a>Crittografia

La crittografia è una parte importante della strategia di protezione dei file e della protezione delle informazioni. In questo articolo viene fornita una panoramica della crittografia per Office 365. Ottenere assistenza per le attività di crittografia come configurare la crittografia per l'organizzazione e come proteggere tramite password i documenti di Office.
  
- Per informazioni su certificati e tecnologie come TLS, vedere informazioni di [riferimento tecnico sulla crittografia in Office 365](technical-reference-details-about-encryption.md).

- Per informazioni su come configurare o impostare la crittografia per l'organizzazione, vedere Configurare la [crittografia in Office 365 Enterprise](set-up-encryption.md).

## <a name="what-is-encryption-and-how-does-it-work-in-office-365"></a>Che cos'è la crittografia e come funziona in Office 365?

Il processo di crittografia codifica i dati (denominati con testo non crittografato) in testo crittografato. A differenza del testo non crittografato, il testo crittografato non può essere utilizzato da persone o computer, a meno che non venga decrittografato. La decrittografia richiede una chiave di crittografia che dispone solo degli utenti autorizzati. La crittografia consente di verificare che solo i destinatari autorizzati possano decrittografare il contenuto. Il contenuto include file, messaggi di posta elettronica, voci del calendario e così via.
  
La crittografia non impedisce l'intercettazione del contenuto. La crittografia è parte di una strategia di protezione delle informazioni più ampia per la propria organizzazione. Utilizzando la crittografia, è possibile garantire che solo le parti autorizzate possano utilizzare i dati crittografati.
  
È possibile disporre di più livelli di crittografia sul posto contemporaneamente. Ad esempio, è possibile crittografare i messaggi di posta elettronica e anche i canali di comunicazione tramite i quali il flusso di posta elettronica scorre. Con Office 365, i dati vengono crittografati a riposo e in transito, utilizzando diversi protocolli di crittografia avanzata e tecnologie che includono Transport Layer Security/Secure Sockets Layer (TLS/SSL), IPSec (Internet Protocol Security) e AES (Advanced Encryption Standard).
  
## <a name="encryption-for-data-at-rest-and-data-in-transit"></a>Crittografia dei dati a riposo e dati in transito

 **Esempi di dati a riposo** sono i file caricati in una raccolta di SharePoint, i dati di Project online, i documenti caricati in una riunione di Skype for business, i messaggi di posta elettronica e gli allegati archiviati in cartelle nella cassetta postale e i file caricati in OneDrive for business.
  
 Tra gli **esempi di dati in transito** sono inclusi i messaggi di posta elettronica in fase di recapito o le conversazioni che si svolgono in una riunione online. In Office 365, i dati sono in transito ogni volta che il dispositivo di un utente comunica con un server Microsoft o quando un server Microsoft comunica con un altro server.
  
Con Office 365, più livelli e tipi di crittografia interagiscono per proteggere i dati. Nella tabella seguente sono inclusi alcuni esempi, con collegamenti a ulteriori informazioni.
  
|**Tipi di contenuto**|**Tecnologie di crittografia**|**Risorse per approfondire**|
|:-----|:-----|:-----|
|File in un dispositivo. Questi file possono includere i messaggi di posta elettronica salvati in una cartella, i documenti di Office salvati in un computer, un tablet o un telefono o i dati salvati nel cloud Microsoft.  <br/> |BitLocker nei datacenter Microsoft. BitLocker può essere utilizzato anche nei computer client, ad esempio Windows e Tablet  <br/> Distributed Key Manager (DKM) nei datacenter Microsoft  <br/> Chiave del cliente per Microsoft 365  <br/> |[Centro IT di Windows: BitLocker](https://docs.microsoft.com/windows/device-security/bitlocker/bitlocker-overview) <br/> [Centro protezione Microsoft: crittografia](https://www.microsoft.com/TrustCenter/Security/Encryption) <br/> [Serie di controlli di sicurezza cloud: crittografia dei dati a riposo](https://blogs.microsoft.com/microsoftsecure/2015/09/10/cloud-security-controls-series-encrypting-data-at-rest) <br/> [Modalità di protezione dei segreti di posta elettronica in Exchange Online](exchange-online-secures-email-secrets.md) <br/> [Crittografia del servizio con la chiave del cliente](customer-key-overview.md) <br/> |
|File in transito tra gli utenti. Questi file possono includere documenti di Office o elementi di elenchi di SharePoint condivisi tra gli utenti.  <br/> |TLS per i file in transito  <br/> |[Crittografia dei dati in OneDrive for Business e SharePoint Online](data-encryption-in-odb-and-spo.md) <br/> [Skype for business online: sicurezza e archiviazione](https://technet.microsoft.com/library/skype-for-business-online-security-and-archiving.aspx) <br/> |
|Messaggi di posta elettronica in transito tra i destinatari. Questo messaggio di posta elettronica include la posta elettronica ospitata da Exchange Online.  <br/> |Crittografia dei messaggi di Office 365 con Azure Rights Management, S/MIME e TLS per la posta elettronica in transito  <br/> |[Office 365 Message Encryption (OME)](ome.md) <br/> [Crittografia della posta elettronica in Office 365](email-encryption.md) <br/> [Modalità d'uso di TLS in Exchange Online per proteggere le connessioni di posta elettronica in Office 365](exchange-online-uses-tls-to-secure-email-connections.md) <br/> |
|Chat, messaggi e file in transito tra i destinatari tramite Microsoft teams. <br/> |I team utilizzano TLS e MTLS per crittografare i messaggi istantanei. Il traffico multimediale viene crittografato utilizzando la sicurezza RTP (SRTP). Teams utilizza algoritmi FIPS (Federal Information Processing Standard) conformi per gli scambi di chiavi di crittografia. <br/> |[Crittografia per i team](https://docs.microsoft.com/microsoftteams/teams-security-guide#encryption-for-teams) <br/> |

## <a name="what-if-i-need-more-control-over-encryption-to-meet-security-and-compliance-requirements"></a>Che cosa succede se è necessario un maggiore controllo sulla crittografia per soddisfare I requisiti di sicurezza e conformità?

Microsoft 365 fornisce soluzioni gestite da Microsoft per la crittografia dei volumi, la crittografia dei file e la crittografia delle cassette postali in Office 365. Inoltre, Microsoft fornisce soluzioni di crittografia che è possibile gestire e controllare. Queste soluzioni di crittografia sono basate su Azure.
  
Per altre informazioni, vedere le risorse seguenti:
  
- [Informazioni su Azure Rights Management](https://docs.microsoft.com/information-protection/understand-explore/what-is-azure-rms)

- [Attivare Rights Management nell'interfaccia di amministrazione](https://docs.microsoft.com/office365/enterprise/activate-rms-in-office-365)

- [Set up Information Rights Management (IRM) in SharePoint admin center](set-up-irm-in-sp-admin-center.md)

- [Crittografia del servizio con Customer Key in Office 365](customer-key-overview.md)

## <a name="how-do-i"></a>Come si fa?

|**Per eseguire questa attività**|**Vedere queste risorse**|
|:-----|:-----|
|Configurare la crittografia per l'organizzazione  <br/> |[Configurare la crittografia in Office 365 Enterprise](set-up-encryption.md) <br/> |
|Visualizzare i dettagli relativi ai certificati, alle tecnologie e ai gruppi di crittografia TLS <br/> |[Informazioni tecniche sulla crittografia](technical-reference-details-about-encryption.md) <br/> |
|Utilizzo dei messaggi crittografati in un dispositivo mobile  <br/> |[Visualizzazione dei messaggi crittografati sul dispositivo Android](https://support.office.com/article/83d60f17-2305-407a-a762-7d518401fdeb) <br/> [Visualizzare i messaggi crittografati sul tuo iPhone o iPad](https://support.microsoft.com/en-us/office/view-protected-messages-on-your-iphone-or-ipad-4d631321-0d26-4bcc-a483-d294dd0b1caf) <br/> |
|Crittografare un documento mediante la protezione tramite password  <br/><br/>  La protezione tramite password non è supportata in un browser. Utilizzare le versioni desktop di Word, Excel e PowerPoint per la protezione delle password. |[Aggiungere o rimuovere la protezione nel documento, nella cartella di lavoro o nella presentazione](https://support.office.com/article/05084cc3-300d-4c1a-8416-38d3e37d6826) <br/> Scegliere una sezione **Aggiungi protezione** e quindi fare clic **su Crittografa con password**.  |
|Rimuovere la crittografia da un documento  <br/> |[Aggiungere o rimuovere la protezione nel documento, nella cartella di lavoro o nella presentazione](https://support.office.com/article/05084cc3-300d-4c1a-8416-38d3e37d6826) <br/> Scegliere una sezione **Rimuovi protezione** e quindi fare clic su **Rimuovi crittografia password**.  |


## <a name="related-topics"></a>Argomenti correlati

[Pianificare le funzionalità di sicurezza e protezione delle informazioni di Microsoft 365](plan-for-security-and-compliance.md)

[Top 10 modi per proteggere i piani Microsoft 365 for business](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data?view=o365-worldwide)
