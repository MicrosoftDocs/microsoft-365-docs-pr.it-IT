---
title: Crittografia in Microsoft 365
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
- m365solution-mip
- m365initiative-compliance
description: Con Office 365, i contenuti vengono crittografati in transito e in transito con la crittografia, i protocolli e le tecnologie più potenti disponibili. Panoramica della crittografia in Office 365.
ms.openlocfilehash: 1aee9d401891e807f572c1eed2bc22a54f39e534
ms.sourcegitcommit: c0495e224f12c448bfc162ef2e4b33b82f064ac8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/17/2020
ms.locfileid: "49709569"
---
# <a name="encryption"></a>Crittografia

La crittografia è una parte importante della strategia di protezione dei file e delle informazioni. In questo articolo viene fornita una panoramica della crittografia per Office 365. Informazioni su come configurare la crittografia per l'organizzazione e come proteggere i documenti di Office con password.
  
- Per informazioni sui certificati e sulle tecnologie come TLS, vedere Informazioni di riferimento tecniche [sulla crittografia in Office 365.](technical-reference-details-about-encryption.md)

- Per informazioni su come configurare o configurare la crittografia per l'organizzazione, vedere [Configurare la crittografia in Office 365 Enterprise.](set-up-encryption.md)

## <a name="what-is-encryption-and-how-does-it-work-in-office-365"></a>Che cos'è la crittografia e come funziona in Office 365?

Il processo di crittografia codifica i dati (denominati testo normale) in testo crittografato. A differenza del testo normale, il testo crittografato non può essere utilizzato da utenti o computer a meno che il testo crittografato non venga decrittografato e non venga decrittografato. La decrittografia richiede una chiave di crittografia di cui dispongono solo gli utenti autorizzati. La crittografia garantisce che solo i destinatari autorizzati possano decrittografare il contenuto. Il contenuto include file, messaggi di posta elettronica, voci del calendario e così via.
  
La crittografia da sola non impedisce l'intercettazione del contenuto. La crittografia fa parte di una strategia di protezione delle informazioni più ampia per l'organizzazione. Utilizzando la crittografia, è possibile garantire che solo le parti autorizzate possano utilizzare i dati crittografati.
  
È possibile disporre di più livelli di crittografia contemporaneamente. Ad esempio, è possibile crittografare i messaggi di posta elettronica e anche i canali di comunicazione attraverso i quali fluisce la posta elettronica. Con Office 365, i dati vengono crittografati in transito e in transito, utilizzando diversi protocolli di crittografia avanzati e tecnologie che includono Transport Layer Security/Secure Sockets Layer (TLS/SSL), IPSec (Internet Protocol Security) e Advanced Encryption Standard (AES).
  
## <a name="encryption-for-data-at-rest-and-data-in-transit"></a>Crittografia per i dati in stato di inquieto e i dati in transito

  Alcuni esempi di dati archiviati includono i file caricati in una raccolta di SharePoint, i dati di Project Online, i documenti caricati in una riunione Skype for Business, i messaggi di posta elettronica e gli allegati archiviati nelle cartelle della cassetta postale e i file caricati in OneDrive for Business.
  
 **Alcuni esempi di dati in transito** includono i messaggi di posta elettronica in fase di recapito o le conversazioni in corso in una riunione online. In Office 365, i dati sono in transito ogni volta che il dispositivo di un utente comunica con un server Microsoft o quando un server Microsoft comunica con un altro server.
  
Con Office 365, più livelli e tipi di crittografia funzionano insieme per proteggere i dati. Nella tabella seguente sono inclusi alcuni esempi, con collegamenti a informazioni aggiuntive.
  
|**Tipi di contenuto**|**Tecnologie di crittografia**|**Risorse per approfondire**|
|:-----|:-----|:-----|
|File in un dispositivo. Questi file possono includere messaggi di posta elettronica salvati in una cartella, documenti di Office salvati in un computer, tablet o telefono o dati salvati nel cloud Microsoft.  <br/> |BitLocker nei datacenter Microsoft. BitLocker può essere usato anche nei computer client, ad esempio computer e tablet Windows  <br/> Distributed Key Manager (DKM) nei datacenter Microsoft  <br/> Customer Key per Microsoft 365  <br/> |[Windows IT Center: BitLocker](https://docs.microsoft.com/windows/device-security/bitlocker/bitlocker-overview) <br/> [Centro protezione Microsoft: crittografia](https://www.microsoft.com/TrustCenter/Security/Encryption) <br/> [Serie di controlli di sicurezza cloud: Crittografia dei dati in pausa](https://blogs.microsoft.com/microsoftsecure/2015/09/10/cloud-security-controls-series-encrypting-data-at-rest) <br/> [Modalità di protezione dei segreti di posta elettronica in Exchange Online](exchange-online-secures-email-secrets.md) <br/> [Crittografia del servizio con Customer Key](customer-key-overview.md) <br/> |
|File in transito tra utenti. Questi file possono includere documenti di Office o elementi di elenchi di SharePoint condivisi tra gli utenti.  <br/> |TLS per i file in transito  <br/> |[Crittografia dei dati in OneDrive for Business e SharePoint Online](data-encryption-in-odb-and-spo.md) <br/> [Skype for Business online: Sicurezza e archiviazione](https://technet.microsoft.com/library/skype-for-business-online-security-and-archiving.aspx) <br/> |
|Posta elettronica in transito tra destinatari. Questo messaggio di posta elettronica include la posta elettronica ospitata da Exchange Online.  <br/> |Crittografia dei messaggi di Office 365 con Azure Rights Management, S/MIME e TLS per la posta elettronica in transito  <br/> |[Office 365 Message Encryption (OME)](ome.md) <br/> [Crittografia della posta elettronica in Office 365](email-encryption.md) <br/> [Modalità d'uso di TLS in Exchange Online per proteggere le connessioni di posta elettronica in Office 365](exchange-online-uses-tls-to-secure-email-connections.md) <br/> |
|Chat, messaggi e file in transito tra destinatari che usano Microsoft Teams. <br/> |Teams usa TLS e MTLS per crittografare i messaggi istantanei. Il traffico multimediale viene crittografato con Secure RTP (SRTP). Teams usa algoritmi conformi a FIPS (Federal Information Processing Standard) per lo scambio di chiavi di crittografia. <br/> |[Crittografia per Teams](https://docs.microsoft.com/microsoftteams/teams-security-guide#encryption-for-teams) <br/> |

## <a name="what-if-i-need-more-control-over-encryption-to-meet-security-and-compliance-requirements"></a>Cosa succede se è necessario un maggiore controllo sulla crittografia per soddisfare i requisiti di sicurezza e conformità?

Microsoft 365 fornisce soluzioni gestite da Microsoft per la crittografia del volume, la crittografia dei file e la crittografia delle cassette postali in Office 365. Inoltre, Microsoft fornisce soluzioni di crittografia che è possibile gestire e controllare. Queste soluzioni di crittografia si basano su Azure.
  
Per altre informazioni, vedere le risorse seguenti:
  
- [Informazioni su Azure Rights Management](https://docs.microsoft.com/information-protection/understand-explore/what-is-azure-rms)

- [Attivare Rights Management nell'interfaccia di amministrazione](https://docs.microsoft.com/microsoft-365/enterprise/activate-rms-in-microsoft-365)

- [Configurare Information Rights Management (IRM) nell'interfaccia di amministrazione di SharePoint](set-up-irm-in-sp-admin-center.md)

- [Crittografia del servizio con Customer Key in Office 365](customer-key-overview.md)

- [Crittografia a chiave doppia per Microsoft 365](double-key-encryption.md)

## <a name="how-do-i"></a>Come si fa?

|**Per eseguire questa attività**|**Vedere queste risorse**|
|:-----|:-----|
|Configurare la crittografia per l'organizzazione  <br/> |[Configurare la crittografia in Office 365 Enterprise](set-up-encryption.md) <br/> |
|Visualizzare i dettagli su certificati, tecnologie e pacchetti di crittografia TLS <br/> |[Dettagli tecnici sulla crittografia](technical-reference-details-about-encryption.md) <br/> |
|Utilizzare i messaggi crittografati in un dispositivo mobile  <br/> |[Visualizzare i messaggi crittografati nel dispositivo Android](https://support.office.com/article/83d60f17-2305-407a-a762-7d518401fdeb) <br/> [Visualizzare i messaggi crittografati su iPhone o iPad](https://support.microsoft.com/en-us/office/view-protected-messages-on-your-iphone-or-ipad-4d631321-0d26-4bcc-a483-d294dd0b1caf) <br/> |
|Crittografare un documento tramite password di protezione  <br/><br/>  La protezione tramite password non è supportata in un browser. Utilizzare le versioni desktop di Word, Excel e PowerPoint per la protezione tramite password. |[Aggiungere o rimuovere protezione nel documento, nella cartella di lavoro o nella presentazione](https://support.office.com/article/05084cc3-300d-4c1a-8416-38d3e37d6826) <br/> Scegliere una **sezione Aggiungi** protezione e quindi vedere **Crittografa con password.**  |
|Rimuovere la crittografia da un documento  <br/> |[Aggiungere o rimuovere protezione nel documento, nella cartella di lavoro o nella presentazione](https://support.office.com/article/05084cc3-300d-4c1a-8416-38d3e37d6826) <br/> Scegliere una **sezione Rimuovi protezione** e quindi vedere Rimuovere la crittografia della **password.**  |


## <a name="related-topics"></a>Argomenti correlati

[Pianificare le funzionalità di sicurezza e protezione delle informazioni di Microsoft 365](plan-for-security-and-compliance.md)

[10 modi principali per proteggere i piani di Microsoft 365 per le aziende](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data)

[Flusso di riproduzione e crittografia a livello di microsoft Stream Video](https://docs.microsoft.com/stream/network-overview#video-level-encryption-and-playback-flow)
