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
description: Con Office 365, il contenuto viene crittografato in fase di riposo e in transito con la crittografia, i protocolli e le tecnologie più potenti disponibili. Ottenere una panoramica della crittografia in Office 365.
ms.openlocfilehash: c54508434c5ae5126a79eba1cb6dab3851d8f746
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926444"
---
# <a name="encryption"></a>Crittografia

La crittografia è una parte importante della strategia di protezione dei file e di protezione delle informazioni. In questo articolo viene fornita una panoramica della crittografia per Office 365. Informazioni su come configurare la crittografia per l'organizzazione e come proteggere i documenti Office con password.
  
- Per informazioni sui certificati e sulle tecnologie come TLS, vedere Informazioni di riferimento tecniche sulla crittografia [in Office 365](technical-reference-details-about-encryption.md).

- Per informazioni su come configurare o configurare la crittografia per l'organizzazione, vedere [Set up encryption in Office 365 Enterprise](set-up-encryption.md).

## <a name="what-is-encryption-and-how-does-it-work-in-office-365"></a>Che cos'è la crittografia e come funziona in Office 365?

Il processo di crittografia codifica i dati (denominati testo normale) in testo crittografato. A differenza del testo normale, il testo crittografato non può essere utilizzato da utenti o computer a meno che e fino a quando il testo crittografato non viene decrittografato. La decrittografia richiede una chiave di crittografia che solo gli utenti autorizzati hanno. La crittografia garantisce che solo i destinatari autorizzati possano decrittografare il contenuto. Il contenuto include file, messaggi di posta elettronica, voci di calendario e così via.
  
La crittografia da sola non impedisce l'intercettazione del contenuto. La crittografia fa parte di una strategia di protezione delle informazioni più ampia per l'organizzazione. Utilizzando la crittografia, si garantisce che solo le parti autorizzate possano utilizzare i dati crittografati.
  
È possibile disporre di più livelli di crittografia contemporaneamente. Ad esempio, è possibile crittografare i messaggi di posta elettronica e anche i canali di comunicazione attraverso i quali la posta elettronica passa. Con Office 365, i dati vengono crittografati in transito e in transito, utilizzando diversi protocolli di crittografia avanzati e tecnologie che includono Transport Layer Security/Secure Sockets Layer (TLS/SSL), IPSec (Internet Protocol Security) e Advanced Encryption Standard (AES).
  
## <a name="encryption-for-data-at-rest-and-data-in-transit"></a>Crittografia dei dati in pausa e dei dati in transito

  Tra gli esempi di dati in pausa sono inclusi i file caricati in una raccolta SharePoint, i dati Project Online, i documenti caricati in una riunione di Skype for Business, i messaggi di posta elettronica e gli allegati archiviati nelle cartelle della cassetta postale e i file caricati in OneDrive for Business.
  
 **Tra gli esempi di dati in transito** sono inclusi i messaggi di posta elettronica in fase di recapito o le conversazioni in corso in una riunione online. In Office 365, i dati sono in transito ogni volta che il dispositivo di un utente comunica con un server Microsoft o quando un server Microsoft comunica con un altro server.
  
Con Office 365, più livelli e tipi di crittografia funzionano insieme per proteggere i dati. Nella tabella seguente sono inclusi alcuni esempi, con collegamenti a informazioni aggiuntive.
  
|**Tipi di contenuto**|**Tecnologie di crittografia**|**Risorse per approfondire**|
|:-----|:-----|:-----|
|File in un dispositivo. Questi file possono includere messaggi di posta elettronica salvati in una cartella, Office documenti salvati in un computer, un tablet o un telefono o dati salvati nel cloud Microsoft.  <br/> |BitLocker nei datacenter Microsoft. BitLocker possono essere utilizzati anche su computer client, ad esempio Windows computer e tablet  <br/> Distributed Key Manager (DKM) nei datacenter Microsoft  <br/> Codice Cliente per Microsoft 365  <br/> |[Windows Centro IT: BitLocker](/windows/device-security/bitlocker/bitlocker-overview) <br/> [Centro protezione Microsoft: crittografia](https://www.microsoft.com/TrustCenter/Security/Encryption) <br/> [Serie di controlli di sicurezza cloud: Crittografia dei dati in pausa](https://blogs.microsoft.com/microsoftsecure/2015/09/10/cloud-security-controls-series-encrypting-data-at-rest) <br/> [Modalità di protezione dei segreti di posta elettronica in Exchange Online](exchange-online-secures-email-secrets.md) <br/> [Crittografia del servizio con Customer Key](customer-key-overview.md) <br/> |
|File in transito tra utenti. Questi file possono includere Office documenti o SharePoint di elenco condivisi tra gli utenti.  <br/> |TLS per i file in transito  <br/> |[Crittografia dei dati in OneDrive for Business e SharePoint Online](data-encryption-in-odb-and-spo.md) <br/> [Skype for Business Online: Sicurezza e archiviazione](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-features) <br/> |
|Posta elettronica in transito tra destinatari. Questo messaggio di posta elettronica include la posta elettronica ospitata da Exchange Online.  <br/> |Office 365 Message Encryption con Azure Rights Management, S/MIME e TLS per la posta elettronica in transito  <br/> |[Office 365 Message Encryption (OME)](ome.md) <br/> [Crittografia della posta elettronica in Office 365](email-encryption.md) <br/> [Modalità d'uso di TLS in Exchange Online per proteggere le connessioni di posta elettronica in Office 365](exchange-online-uses-tls-to-secure-email-connections.md) <br/> |
|Chat, messaggi e file in transito tra destinatari che utilizzano Microsoft Teams. <br/> |Teams utilizza TLS e MTLS per crittografare i messaggi istantanei. Il traffico multimediale viene crittografato tramite Secure RTP (SRTP). Teams algoritmi fips (Federal Information Processing Standard) compatibili per gli scambi di chiavi di crittografia. <br/> |[Crittografia per Teams](/microsoftteams/teams-security-guide#encryption-for-teams) <br/> |

## <a name="what-if-i-need-more-control-over-encryption-to-meet-security-and-compliance-requirements"></a>Cosa succede se è necessario un maggiore controllo sulla crittografia per soddisfare i requisiti di sicurezza e conformità?

Microsoft 365 soluzioni gestite da Microsoft per la crittografia dei volumi, la crittografia dei file e la crittografia delle cassette postali in Office 365. Inoltre, Microsoft fornisce soluzioni di crittografia che è possibile gestire e controllare. Queste soluzioni di crittografia si basano su Azure.
  
Per altre informazioni, vedere le risorse seguenti:
  
- [Informazioni su Azure Rights Management](/information-protection/understand-explore/what-is-azure-rms)

- [Attivare Rights Management nell'interfaccia di amministrazione](../enterprise/activate-rms-in-microsoft-365.md)

- [Configurare Information Rights Management (IRM) nell'interfaccia di amministrazione di SharePoint](set-up-irm-in-sp-admin-center.md)

- [Crittografia del servizio con Customer Key in Office 365](customer-key-overview.md)

- [Crittografia a chiave doppia per Microsoft 365](double-key-encryption.md)

## <a name="how-do-i"></a>Come si fa?

|**Per eseguire questa attività**|**Vedi queste risorse**|
|:-----|:-----|
|Configurare la crittografia per l'organizzazione  <br/> |[Configurare la crittografia in Office 365 Enterprise](set-up-encryption.md) <br/> |
|Visualizzare i dettagli su certificati, tecnologie e suite di crittografia TLS <br/> |[Dettagli tecnici sulla crittografia](technical-reference-details-about-encryption.md) <br/> |
|Usare i messaggi crittografati in un dispositivo mobile  <br/> |[Visualizzare i messaggi crittografati nel dispositivo Android](https://support.office.com/article/83d60f17-2305-407a-a762-7d518401fdeb) <br/> [Visualizzare i messaggi crittografati iPhone o iPad](https://support.microsoft.com/en-us/office/view-protected-messages-on-your-iphone-or-ipad-4d631321-0d26-4bcc-a483-d294dd0b1caf) <br/> |
|Crittografare un documento con password di protezione  <br/><br/>  La protezione tramite password non è supportata in un browser. Utilizzare le versioni desktop di Word, Excel e PowerPoint per la protezione tramite password. |[Aggiungere o rimuovere protezione nel documento, nella cartella di lavoro o nella presentazione](https://support.office.com/article/05084cc3-300d-4c1a-8416-38d3e37d6826) <br/> Scegliere una **sezione Aggiungi** protezione e quindi vedere **Crittografa con password.**  |
|Rimuovere la crittografia da un documento  <br/> |[Aggiungere o rimuovere protezione nel documento, nella cartella di lavoro o nella presentazione](https://support.office.com/article/05084cc3-300d-4c1a-8416-38d3e37d6826) <br/> Scegliere una **sezione Rimuovi protezione** e quindi vedere Rimuovere la crittografia delle **password.**  |


## <a name="related-topics"></a>Argomenti correlati

[Pianificare le funzionalità Microsoft 365 sicurezza e protezione delle informazioni](plan-for-security-and-compliance.md)

[I 10 modi principali per proteggere i Microsoft 365 per le aziende](/office365/admin/security-and-compliance/secure-your-business-data)

[Flusso di riproduzione e crittografia a livello di microsoft Stream Video](/stream/network-overview#video-level-encryption-and-playback-flow)