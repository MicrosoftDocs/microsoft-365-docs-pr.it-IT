---
title: Funzionalità di crittografia gestite dai clienti
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
ms.custom:
- seo-marvel-mar2020
description: In questo articolo vengono trattate le tecnologie di crittografia che è possibile gestire e configurare in Microsoft 365.
ms.openlocfilehash: 6a693c512100c59eef47414fdd6eab4a2924e835
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926234"
---
# <a name="customer-managed-encryption-features"></a>Funzionalità di crittografia gestite dai clienti

Insieme alle tecnologie di crittografia in Microsoft 365 gestite da Microsoft, Microsoft 365 funziona anche con tecnologie di crittografia aggiuntive che è possibile gestire e configurare, ad esempio:

- [Azure Rights Management](/azure/information-protection/what-is-azure-rms)

- [Secure Multipurpose Internet Mail Extension](https://blogs.technet.com/b/exchange/archive/2014/12/15/how-to-configure-s-mime-in-office-365.aspx)

- [Crittografia dei messaggi di Office 365](https://products.office.com/en-us/exchange/office-365-message-encryption)

- [Proteggere il flusso di posta con un'organizzazione partner](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner)

Per ulteriori informazioni su queste tecnologie, vedere le [descrizioni Microsoft 365 servizio.](/office365/servicedescriptions/office-365-service-descriptions-technet-library)

## <a name="azure-rights-management"></a>Azure Rights Management

[Azure Rights Management](/azure/information-protection/what-is-azure-rms) (Azure RMS) è la tecnologia di protezione utilizzata da [Azure Information Protection.](/information-protection/understand-explore/what-is-information-protection) Usa criteri di crittografia, identità e autorizzazione per proteggere i file e la posta elettronica su più piattaforme e dispositivi, ovvero telefoni, tablet e PC. Le informazioni possono essere protette sia all'interno che all'esterno dell'organizzazione perché la protezione rimane con i dati. Azure RMS offre una protezione permanente di tutti i tipi di file, protegge i file ovunque, supporta la collaborazione tra aziende e un'ampia gamma di dispositivi Windows e non Windows. La protezione di Azure RMS può anche aumentare i criteri di prevenzione [della perdita dei dati (DLP).](/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention) Per ulteriori informazioni sulle applicazioni e i servizi che possono usare il servizio Azure Rights Management da Azure Information Protection, vedere Come le applicazioni [supportano il servizio Azure Rights Management.](/information-protection/understand-explore/applications-support)

Azure RMS è integrato con Microsoft 365 e disponibile per tutti i clienti. Per configurare Microsoft 365 per l'utilizzo di Azure RMS, vedere [Configure IRM to use Azure Rights Management e Set up Information Rights Management (IRM) in SharePoint admin center](../enterprise/activate-rms-in-microsoft-365.md). Se si utilizza un server RMS di Active Directory (AD) locale, è anche possibile configurare [IRM](/office365/SecurityCompliance/configure-irm-to-use-an-on-premises-ad-rms-server)per l'utilizzo di un server AD RMS locale, ma è consigliabile eseguire la migrazione ad [Azure RMS](/azure/information-protection/migrate-from-ad-rms-to-azure-rms) per usare nuove funzionalità come la collaborazione sicura con altre organizzazioni.

Quando si proteggono i dati dei clienti con Azure RMS, Azure RMS usa una chiave asimmetrica RSA a 2048 bit con algoritmo hash SHA-256 per l'integrità per crittografare i dati. La chiave simmetrica per Office e la posta elettronica è AES a 128 bit. Per ogni documento o messaggio di posta elettronica protetto da Azure RMS, Azure RMS crea una singola chiave AES (la "chiave di contenuto") e tale chiave viene incorporata nel documento e viene mantenuta nelle edizioni del documento. La chiave di contenuto è protetta con la chiave RSA dell'organizzazione (la "chiave tenant di Azure Information Protection") come parte dei criteri nel documento e il criterio viene firmato anche dall'autore del documento. Questa chiave tenant è comune a tutti i documenti e i messaggi di posta elettronica protetti da Azure RMS per l'organizzazione e questa chiave può essere modificata solo da un amministratore di Azure Information Protection se l'organizzazione usa una chiave tenant gestita dal cliente. Per ulteriori informazioni sui controlli di crittografia usati da Azure RMS, vedere [Funzionamento di Azure RMS? Sotto il cofano](/information-protection/understand-explore/how-does-it-work).

In un'implementazione di Azure RMS predefinita, Microsoft genera e gestisce la chiave radice univoca per ogni tenant. I clienti possono gestire il ciclo di vita della chiave radice in Azure RMS con Azure Key Vault Services usando un metodo di gestione delle chiavi denominato [Bring Your Own Key (BYOK)](/azure/information-protection/plan-implement-tenant-key) che consente di generare la chiave negli HSM locali (moduli di sicurezza hardware) e di mantenere il controllo di questa chiave dopo il trasferimento agli HMS convalidati da FIPS 140-2 di Microsoft. L'accesso alla chiave radice non viene fornito ad alcun personale perché le chiavi non possono essere esportate o estratte dagli HMS che le proteggono. Inoltre, è possibile accedere a un registro quasi in tempo reale che mostra tutti gli accessi alla chiave radice in qualsiasi momento. Per ulteriori informazioni, vedere [Logging and Analyzing Azure Rights Management Usage.](/azure/information-protection/log-analyze-usage)

Azure Rights Management consente di mitigare minacce quali intercettazioni telefoniche, attacchi man-in-the-middle, furti di dati e violazioni involontarie dei criteri di condivisione dell'organizzazione. Allo stesso tempo, qualsiasi accesso ingiustificato ai dati dei clienti in transito o in pausa da parte di un utente non autorizzato che non dispone delle autorizzazioni appropriate viene impedito tramite criteri che seguono questi dati, riducendo così il rischio che i dati cadano nelle mani sbagliate consapevolmente o inconsapevolmente e fornendo funzioni di prevenzione della perdita dei dati. Se usato come parte di Azure Information Protection, Azure RMS fornisce anche funzionalità di classificazione e etichettatura dei dati, contrassegno del contenuto, verifica dell'accesso ai documenti e funzionalità di revoca dell'accesso. Per altre informazioni su queste funzionalità, vedere Che [cos'è Azure Information Protection,](/information-protection/understand-explore/what-is-information-protection)Roadmap per la distribuzione di [Azure Information Protection](/information-protection/plan-design/deployment-roadmap)e Esercitazione introduttiva per Azure Information [Protection.](/information-protection/get-started/infoprotect-quick-start-tutorial)

## <a name="secure-multipurpose-internet-mail-extension"></a>Secure Multipurpose Internet Mail Extension

Secure/Multipurpose Internet Mail Extensions (S/MIME) è uno standard per la crittografia a chiave pubblica e la firma digitale dei dati MIME. S/MIME è definito nelle RFC 3369, 3370, 3850, 3851 e altre. Consente a un utente di crittografare un messaggio di posta elettronica e firmare digitalmente un messaggio di posta elettronica. Un messaggio di posta elettronica crittografato tramite S/MIME può essere decrittografato solo dal destinatario del messaggio utilizzando la chiave privata, disponibile solo per tale destinatario. Di conseguenza, i messaggi di posta elettronica non possono essere decrittografati da persone diverse dal destinatario del messaggio di posta elettronica.

[Microsoft supporta S/MIME](https://blogs.technet.com/b/exchange/archive/2014/12/15/how-to-configure-s-mime-in-office-365.aspx). I certificati pubblici vengono distribuiti ad Active Directory locale del cliente e archiviati in attributi che possono essere replicati in un tenant Microsoft 365 locale. Le chiavi private corrispondenti alle chiavi pubbliche rimangono locali e non vengono mai trasmesse Office 365. Gli utenti possono comporre, crittografare, decrittografare, leggere e firmare digitalmente i messaggi di posta elettronica tra due utenti di un'organizzazione utilizzando Outlook, Outlook sul Web e client Exchange ActiveSync. Per ulteriori informazioni, vedere [Crittografia S/MIME ora in Office 365](https://blogs.office.com/2014/02/26/smime-encryption-now-in-office-365/).

## <a name="office-365-message-encryption"></a>Crittografia dei messaggi di Office 365

[Office 365 Message Encryption](https://products.office.com/exchange/office-365-message-encryption) (OME) basato su [Azure Information Protection](/information-protection/understand-explore/what-is-information-protection) (AIP) consente di inviare posta crittografata e protetta da diritti a chiunque. OME mitiga minacce quali attacchi di intercettazione e man-in-the-middle e altre minacce, ad esempio l'accesso ingiustificato ai dati da parte di un utente non autorizzato che non dispone delle autorizzazioni appropriate. Abbiamo effettuato investimenti che offrono un'esperienza di posta elettronica più semplice, intuitiva e sicura, integrata in Azure Information Protection. È possibile proteggere i messaggi inviati da Microsoft 365 a chiunque all'interno o all'esterno dell'organizzazione. Questi messaggi possono essere visualizzati in un set diversificato di client di posta utilizzando qualsiasi identità, inclusi Azure Active Directory, account Microsoft e ID Google. Per ulteriori informazioni su come l'organizzazione può utilizzare i messaggi crittografati, [vedere Office 365 Message Encryption](./ome.md).

## <a name="transport-layer-security"></a>Transport Layer Security   

Se si desidera garantire comunicazioni sicure con un partner, è possibile utilizzare i connettori in ingresso e in uscita per garantire la sicurezza e l'integrità dei messaggi. È possibile configurare TLS in ingresso e in uscita forzato su ogni connettore, utilizzando un certificato. L'utilizzo di un canale SMTP crittografato può impedire il furto dei dati tramite un attacco man-in-the-middle. Per ulteriori informazioni, vedere [How Exchange Online uses TLS to secure email connections](./exchange-online-uses-tls-to-secure-email-connections.md).

## <a name="domain-keys-identified-mail"></a>Domain Keys Identified Mail

Exchange Online Protection (EOP) ed Exchange Online supportano la convalida in ingresso di messaggi Domain Keys Identified Mail (DKIM). DKIM è un metodo per confermare che il messaggio è stato inviato dal dominio di origine dichiarato e che non è stato soggetto a spoofing da parte di altri. Lega un messaggio di posta elettronica all'organizzazione responsabile dell'invio e fa parte di un paradigma più ampio della crittografia della posta elettronica. Per altre informazioni sulle tre parti di questo paradigma, vedi:

- [Configurazione di SPF per evitare lo spoofing](/office365/SecurityCompliance/set-up-spf-in-office-365-to-help-prevent-spoofing)

- [Usare DKIM per convalidare la posta elettronica in uscita inviata dal dominio personalizzato](/office365/SecurityCompliance/use-dkim-to-validate-outbound-email)

- [Usare DMARC per convalidare la posta elettronica](/office365/SecurityCompliance/use-dmarc-to-validate-email)