---
title: Funzionalità di crittografia gestite dal cliente
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
ms.collection: Strat_O365_Enterprise
description: 'Riepilogo: informazioni sulla resilienza dei dati in Microsoft 365.'
ms.openlocfilehash: 365cde7137247e20bb4fd2b57039057398deafd5
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43637342"
---
# <a name="customer-managed-encryption-features"></a>Funzionalità di crittografia gestite dal cliente

Insieme alle tecnologie di crittografia in Microsoft 365 gestite da Microsoft, Microsoft 365 funziona anche con tecnologie di crittografia aggiuntive che è possibile gestire e configurare, ad esempio:

- [Azure Rights Management](https://docs.microsoft.com/azure/information-protection/what-is-azure-rms)

- [Estensione sicura per la posta Internet multiuso](https://blogs.technet.com/b/exchange/archive/2014/12/15/how-to-configure-s-mime-in-office-365.aspx)

- [Crittografia dei messaggi di Office 365](https://products.office.com/en-us/exchange/office-365-message-encryption)

- [Protezione del flusso di posta con un'organizzazione partner](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner)

Per ulteriori informazioni su queste tecnologie, vedere le [descrizioni del servizio Microsoft 365](https://technet.microsoft.com/library/office-365-service-descriptions.aspx).

## <a name="azure-rights-management"></a>Azure Rights Management

[Azure Rights Management](https://docs.microsoft.com/azure/information-protection/what-is-azure-rms) (Azure RMS) è la tecnologia di protezione utilizzata da [Azure Information Protection](https://docs.microsoft.com/information-protection/understand-explore/what-is-information-protection). Utilizza criteri di crittografia, identità e autorizzazione per proteggere i file e la posta elettronica su più piattaforme e dispositivi, ovvero telefoni, tablet e PC. Le informazioni possono essere protette sia all'interno che all'esterno dell'organizzazione perché la protezione rimane associata ai dati. Azure RMS fornisce una protezione permanente di tutti i tipi di file, protegge i file ovunque, supporta la collaborazione tra aziende e una vasta gamma di dispositivi Windows e non Windows. La protezione di Azure RMS può anche incrementare [i criteri di prevenzione della perdita di dati (DLP)](https://docs.microsoft.com/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention). Per ulteriori informazioni sulle applicazioni e sui servizi che possono utilizzare il servizio Azure Rights Management da Azure Information Protection, vedere [come le applicazioni supportano il servizio Azure Rights Management](https://docs.microsoft.com/information-protection/understand-explore/applications-support).

Azure RMS è integrato con Microsoft 365 e disponibile per tutti i clienti. Per configurare Microsoft 365 per l'utilizzo di Azure RMS, vedere [Configure IRM to use Azure Rights Management e set up Information Rights Management (IRM) in SharePoint Admin Center](https://technet.microsoft.com/library/dn151475(v=exchg.150).aspx). Se si utilizza il server Active Directory (AD) RMS locale, è anche possibile [configurare IRM per l'utilizzo di un server ad RMS locale](https://docs.microsoft.com/office365/SecurityCompliance/configure-irm-to-use-an-on-premises-ad-rms-server), ma è consigliabile [eseguire la migrazione a Azure RMS](https://docs.microsoft.com/azure/information-protection/migrate-from-ad-rms-to-azure-rms) per utilizzare nuove funzionalità come la collaborazione sicura con altre organizzazioni.

Quando si proteggono i dati dei clienti con Azure RMS, Azure RMS utilizza una chiave asimmetrica RSA a 2048 bit con algoritmo hash SHA-256 per garantire l'integrità per crittografare i dati. La chiave simmetrica per i documenti di Office e la posta elettronica è AES 128-bit (modalità CBC con imbottitura PKCS # 7). Per ogni documento o messaggio di posta elettronica protetto da Azure RMS, Azure RMS crea una singola chiave AES (la "chiave del contenuto") e la chiave è incorporata nel documento e viene mantenuta tramite le edizioni del documento. La chiave del contenuto è protetta con la chiave RSA dell'organizzazione (la chiave tenant di Azure Information Protection) come parte del criterio del documento e il criterio viene firmato anche dall'autore del documento. Questa chiave del tenant è comune a tutti i documenti e i messaggi di posta elettronica protetti da Azure RMS per l'organizzazione e questa chiave può essere modificata solo da un amministratore di Azure Information Protection se l'organizzazione utilizza una chiave tenant gestita dal cliente. Per ulteriori informazioni sui controlli di crittografia utilizzati da Azure RMS, vedere [modalità di funzionamento di Azure RMS Sotto la cappa](https://docs.microsoft.com/information-protection/understand-explore/how-does-it-work).

In un'implementazione di Azure RMS predefinita, Microsoft genera e gestisce la chiave radice che è univoca per ogni tenant. I clienti possono gestire il ciclo di vita della chiave radice in Azure RMS con i Servizi Key Vault di Azure utilizzando un metodo di gestione delle chiavi denominato [Bring your own key (BYOK)](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key) , che consente di generare la chiave in HSM locale (moduli di sicurezza hardware) e di mantenere il controllo di questa chiave dopo il trasferimento a HSM di Microsoft FIPS 140-2 Level 2-convalidated. L'accesso alla chiave radice non viene assegnato a nessun personale, in quanto le chiavi non possono essere esportate o estratte da HSM per proteggerle. Inoltre, è possibile accedere a un log quasi in tempo reale che Mostra tutti gli accessi alla chiave radice in qualsiasi momento. Per ulteriori informazioni, vedere [Logging and analyzing Azure Rights Management Usage](https://docs.microsoft.com/azure/information-protection/log-analyze-usage).

Azure Rights Management consente di attenuare le minacce come la filettatura, gli attacchi man-in-the-Middle, i furti di dati e le violazioni involontarie dei criteri di condivisione organizzativa. Nello stesso tempo, qualsiasi accesso ingiustificato ai dati dei clienti in transito o a riposo da parte di un utente non autorizzato che non dispone di autorizzazioni appropriate è impedito tramite criteri che seguono tali dati, attenuando in tal modo il rischio che i dati cadano nelle mani sbagliate consapevolmente o inconsapevolmente e forniscano funzioni di prevenzione della perdita di dati. Se viene utilizzato come parte di Azure Information Protection, Azure RMS fornisce anche funzionalità di classificazione e etichettatura dei dati, marcatura del contenuto, monitoraggio dell'accesso ai documenti e funzionalità di revoca di accesso. Per ulteriori informazioni su queste funzionalità, vedere [che cos'è Azure Information Protection](https://docs.microsoft.com/information-protection/understand-explore/what-is-information-protection), Guida di [orientamento alla distribuzione di Azure Information Protection](https://docs.microsoft.com/information-protection/plan-design/deployment-roadmap)e Esercitazione introduttiva su [Azure Information Protection](https://docs.microsoft.com/information-protection/get-started/infoprotect-quick-start-tutorial).

## <a name="secure-multipurpose-internet-mail-extension"></a>Estensione sicura per la posta Internet multiuso

Secure/Multipurpose Internet Mail Extensions (S/MIME) è uno standard per la crittografia a chiave pubblica e la firma digitale dei dati MIME. S/MIME è definito nelle RFC 3369, 3370, 3850, 3851 e altri. Consente a un utente di crittografare un messaggio di posta elettronica e di firmare digitalmente un messaggio di posta elettronica. Un messaggio di posta elettronica crittografato con S/MIME può essere decrittografato solo dal destinatario del messaggio di posta elettronica utilizzando la propria chiave privata, che è disponibile solo per il destinatario. Pertanto, i messaggi di posta elettronica non possono essere decrittografati da altri che non siano il destinatario del messaggio.

[Microsoft supporta S/MIME](https://blogs.technet.com/b/exchange/archive/2014/12/15/how-to-configure-s-mime-in-office-365.aspx). I certificati pubblici vengono distribuiti all'Active Directory locale del cliente e archiviati in attributi che possono essere replicati in un tenant di Microsoft 365. Le chiavi private che corrispondono alle chiavi pubbliche restano in locale e non vengono mai trasmesse a Office 365. Gli utenti possono comporre, crittografare, decrittografare, leggere e firmare digitalmente i messaggi di posta elettronica tra due utenti di un'organizzazione tramite Outlook, Outlook sul Web e i client di Exchange ActiveSync. Per ulteriori informazioni, vedere [crittografia S/MIME ora in Office 365](https://blogs.office.com/2014/02/26/smime-encryption-now-in-office-365/).

## <a name="office-365-message-encryption"></a>Crittografia dei messaggi di Office 365

La [crittografia dei messaggi di Office 365](https://products.office.com/exchange/office-365-message-encryption) (OME) basata su [Azure Information Protection](https://docs.microsoft.com/information-protection/understand-explore/what-is-information-protection) (AIP) consente di inviare messaggi crittografati e protetti da diritti a tutti gli utenti. OME attenua le minacce come la filettatura metallica e gli attacchi man-in-the-Middle e altre minacce, ad esempio l'accesso ingiustificato dei dati da parte di un utente non autorizzato che non dispone di autorizzazioni appropriate. Sono stati apportati investimenti che forniscono un'esperienza di posta elettronica più semplice, più intuitiva e sicura, basata su Azure Information Protection. È possibile proteggere i messaggi inviati da Microsoft 365 a tutti gli utenti all'interno o all'esterno dell'organizzazione. Questi messaggi possono essere visualizzati in un insieme diversificato di client di posta elettronica utilizzando qualsiasi identità, tra cui Azure Active Directory, Microsoft account e Google IDs. Per ulteriori informazioni sul modo in cui l'organizzazione può utilizzare i messaggi crittografati, vedere [crittografia dei messaggi di Office 365](https://support.office.com/article/F87CB016-7876-4317-AE3C-9169B311FF8A).

## <a name="transport-layer-security"></a>Transport Layer Security   

Se si desidera garantire la comunicazione sicura con un partner, è possibile utilizzare i connettori in ingresso e in uscita per fornire la sicurezza e l'integrità dei messaggi. È possibile configurare la TLS forzata in ingresso e in uscita su ogni connettore utilizzando un certificato. L'utilizzo di un canale SMTP crittografato può impedire che i dati vengano rubati tramite un attacco di tipo man-in-the-Middle. Per ulteriori informazioni, vedere [come Exchange Online USA TLS per proteggere le connessioni di posta elettronica](https://support.office.com/article/How-Exchange-Online-uses-TLS-to-secure-email-connections-in-Office-365-4CDE0CDA-3430-4DC0-B489-F2C0736C929F).

## <a name="domain-keys-identified-mail"></a>Chiavi di dominio identificate tramite posta elettronica

Exchange Online Protection (EOP) ed Exchange Online supportano la convalida in ingresso di messaggi Domain Keys Identified Mail (DKIM). DKIM è un metodo per confermare che il messaggio è stato inviato dal dominio di origine dichiarato e che non è stato soggetto a spoofing da parte di altri. Collega un messaggio di posta elettronica all'organizzazione responsabile dell'invio e fa parte di un paradigma più esteso della crittografia della posta elettronica. Per ulteriori informazioni sulle tre parti di questo paradigma, vedere:

- [Configurare SPF per impedire lo spoofing](https://docs.microsoft.com/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing)

- [Utilizzare DKIM per convalidare la posta elettronica in uscita inviata dal dominio personalizzato](https://docs.microsoft.com/office365/SecurityCompliance/use-dkim-to-validate-outbound-email)

- [Usare DMARC per convalidare la posta elettronica](https://docs.microsoft.com/office365/SecurityCompliance/use-dmarc-to-validate-email)
