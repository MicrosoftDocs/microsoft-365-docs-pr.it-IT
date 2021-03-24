---
title: S/MIME per la crittografia in Exchange Online - Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 887c710b-0ec6-4ff0-8065-5f05f74afef3
description: Gli amministratori possono ottenere informazioni sull'utilizzo di S/MIME (Secure/Multipurpose Internet Mail Extensions) in Exchange Online per crittografare i messaggi di posta elettronica e firmarli digitalmente.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d189bf7f52dd6f9fb11dc360c17d5fe15729c9fa
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51061914"
---
# <a name="smime-for-message-signing-and-encryption-in-exchange-online"></a>S/MIME per la firma e la crittografia dei messaggi in Exchange Online

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


S/MIME (Secure/Multipurpose Internet Mail Extensions) è un metodo ampiamente accettato (o più precisamente, un protocollo) per l'invio di messaggi firmati digitalmente e crittografati. S/MIME consente di crittografare i messaggi di posta elettronica e di apporvi la firma digitale. Quando si utilizza S/MIME con un messaggio di posta elettronica, consente alle persone che ricevono il messaggio di essere certi che ciò che viene visualizzato nella posta in arrivo è l'esatto messaggio iniziato con il mittente. Consente inoltre alle persone che ricevono messaggi di essere certi che il messaggio proveniva dal mittente specifico e non da qualcuno che fingeva di essere il mittente. A tale scopo, S/MIME fornisce servizi di protezione crittografica quali autenticazione, integrità dei messaggi e non-rifiuto dell'origine (utilizzando le firme digitali). Consente inoltre di migliorare la privacy e la sicurezza dei dati (utilizzando la crittografia) per la messaggistica elettronica. Per un quadro completo della storia e dell'architettura di S/MIME nel contesto della posta elettronica, vedere [Concetti relativi a S/MIME](/previous-versions/tn-archive/aa995740(v=exchg.65)).

Gli amministratori di Exchange Online possono abilitare la sicurezza basata su S/MIME per le cassette postali dell'organizzazione. Utilizzare le indicazioni negli argomenti qui collegati insieme a PowerShell di Exchange Online per configurare S/MIME. Per utilizzare S/MIME nei client di posta elettronica supportati, gli utenti dell'organizzazione devono disporre di certificati emessi a scopo di firma e crittografia e di dati pubblicati nel Servizio di dominio Active Directory locale. Servizi di dominio Active Directory deve trovarsi nei computer in una posizione fisica che si controlla e non in una struttura remota o in un servizio basato su cloud in internet. Per ulteriori informazioni su Servizi di dominio Active Directory, vedere [Panoramica di Servizi di dominio Active Directory.](/windows-server/identity/ad-ds/get-started/virtual-dc/active-directory-domain-services-overview)

## <a name="supported-scenarios-and-technical-considerations"></a>Scenari supportati e considerazioni tecniche

È possibile configurare S/MIME per utilizzare uno qualsiasi dei seguenti endpoint:

- Outlook 2010 o versioni successive
- Outlook sul Web (in precedenza noto come Outlook Web App).
- Exchange ActiveSync (EAS)

La procedura da seguire per configurare S/MIME con ognuno di questi punti finali è leggermente diversa. In genere, è necessario eseguire la procedura seguente:

1. Installare un'Autorità di certificazione (CA) basata su Windows e configurare un'infrastruttura a chiave pubblica per emettere certificati S/MIME. Sono supportati anche i certificati emessi da provider di certificati di terze parti. Per informazioni dettagliate, vedere [Panoramica di Servizi certificati Active Directory](/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/hh831740(v=ws.11)).

   **Note**:

   - I certificati emessi da un'autorità di certificazione di terze parti hanno il vantaggio di essere automaticamente considerati attendibili da tutti i client e i dispositivi. I certificati emessi da un'autorità di certificazione privata interna non vengono automaticamente considerati attendibili da client e dispositivi e non tutti i dispositivi (ad esempio i telefoni) possono essere configurati per considerare attendibili i certificati privati.

   - Prendere in considerazione l'utilizzo di un certificato intermedio anziché del certificato radice per emettere certificati agli utenti. In questo modo, se è necessario revocare ed emettere di nuovo i certificati, il certificato radice è ancora intatto.

2. Pubblicare il certificato utente in un account di Servizi di dominio Active Directory locale negli **attributi UserSMIMECertificate** e/o **UserCertificate.**

3. Per le organizzazioni di Exchange Online, sincronizzare i certificati utente da Servizi di dominio Active Directory ad Azure Active Directory utilizzando una versione appropriata di Azure AD Connect. Questi certificati verranno quindi sincronizzati da Azure Active Directory alla directory di Exchange Online e verranno utilizzati per crittografare un messaggio a un destinatario.

4. Configurare una raccolta di certificati virtuali per convalidare S/MIME. Queste informazioni vengono utilizzate da Outlook sul Web per convalidare la firma di un messaggio di posta elettronica e per garantire che sia stato firmato da un certificato attendibile.

5. Configurare l'endpoint Outlook o EAS per utilizzare S/MIME.

> [!NOTE]
> Non è possibile installare il controllo S/MIME in Outlook sul Web su Mac, iOS, Android o altri dispositivi non Windows. Per ulteriori informazioni, vedere [Encrypt messages by using S/MIME in Outlook on the web](https://support.microsoft.com/office/878c79fc-7088-4b39-966f-14512658f480).

## <a name="set-up-smime-with-outlook-on-the-web"></a>Configurare S/MIME con Outlook sul Web

La configurazione di S/MIME per Exchange Online con Outlook sul Web prevede i passaggi chiave seguenti:

1. [Configurare le impostazioni S/MIME per Outlook sul web](configure-s-mime-settings-for-outlook-web-app.md)
2. [Configurare la raccolta di certificati virtuali per convalidare S/MIME](set-up-virtual-certificate-collection-to-validate-s-mime.md)
3. [Sincronizzare i certificati dell'utente con Office 365 per S/MIME](sync-user-certificates-to-office-365-for-s-mime.md)

## <a name="related-message-encryption-technologies"></a>Tecnologie di crittografia del messaggio correlato

Quando la sicurezza dei messaggi diventa più importante, gli amministratori devono comprendere i principi e i concetti della messaggistica protetta. Questa comprensione è particolarmente importante a causa della crescente varietà di tecnologie correlate alla protezione (tra cui S/MIME) disponibili. Per ulteriori informazioni su S/MIME e sul suo funzionamento nel contesto della posta elettronica, vedere [Understanding S/MIME](/previous-versions/tn-archive/aa995740(v=exchg.65)). Un'ampia gamma di tecnologie di crittografia lavorano insieme per fornire protezione per i messaggi in transito e in transito. S/MIME può funzionare contemporaneamente con le tecnologie seguenti, ma non dipende da esse:

- **Transport Layer Security (TLS)** crittografa il tunnel o la route tra i server di posta elettronica per evitare snooping e intercettazioni.

- **Secure Sockets Layer (SSL) crittografa** la connessione tra i client di posta elettronica e i server Microsoft 365.

- **BitLocker** crittografa i dati su un disco rigido in un datacenter in modo che se un utente ottiene l'accesso non autorizzato, non può leggerlo.

### <a name="smime-compared-with-office-365-message-encryption"></a>S/MIME rispetto alla crittografia dei messaggi di Office 365

S/MIME richiede un certificato e un'infrastruttura di pubblicazione spesso utilizzata nelle situazioni interaziendali o tra azienda e consumatori. L'utente controlla le chiavi crittografiche in S/MIME e può scegliere se utilizzarle per ogni messaggio inviato. I programmi di posta elettronica come Outlook cercano la posizione di un'autorità di certificazione radice attendibile per eseguire la firma digitale e la verifica della firma. Crittografia messaggi di Office 365 è un servizio di crittografia basato su criteri che può essere configurato da un amministratore e non da un singolo utente per crittografare la posta inviata a chiunque all'interno o all'esterno dell'organizzazione. Si tratta di un servizio online basato su Azure Rights Management (RMS) e che non si basa su un'infrastruttura a chiave pubblica. Crittografia messaggi di Office 365 offre anche funzionalità aggiuntive, ad esempio la possibilità di personalizzare la posta con il marchio dell'organizzazione. Per ulteriori informazioni sulla crittografia dei messaggi di Office 365, vedere [Crittografia in Office 365.](../../compliance/encryption.md)

## <a name="more-information"></a>Ulteriori informazioni

[Outlook sul web](/exchange/exchange-admin-center)

[Posta sicura (2000)](/previous-versions/windows/it-pro/windows-2000-server/cc962043(v=technet.10))