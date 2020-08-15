---
title: Panoramica dell'autenticazione moderna ibrida e dei prerequisiti per l'uso con i server di Skype for Business ed Exchange locali
ms.author: kvice
ms.reviewer: smithre4
author: kelleyvice-msft
manager: laurawi
ms.date: 04/15/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.assetid: ef753b32-7251-4c9e-b442-1a5aec14e58d
ms.collection:
- M365-security-compliance
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
description: In questo articolo vengono fornite informazioni sull'autenticazione moderna ibrida e sui prerequisiti per l'utilizzo con i server Skype for business e Exchange locali.
ms.openlocfilehash: 1dbea7643685d68564b1ba09b17c41aa2e5e42f1
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690979"
---
# <a name="hybrid-modern-authentication-overview-and-prerequisites-for-using-it-with-on-premises-skype-for-business-and-exchange-servers"></a>Panoramica dell'autenticazione moderna ibrida e dei prerequisiti per l'uso con i server di Skype for Business ed Exchange locali

*Questo articolo si riferisce sia a Microsoft 365 Enterprise che a Office 365 Enterprise*.

L'_autenticazione moderna_ è un metodo di gestione delle identità che offre un servizio di autenticazione e autorizzazione utente più sicuro. È disponibile per le distribuzioni ibride di Office 365 relative ai server di Skype for Business ed Exchange locali, oltre che per le distribuzioni ibride di Skype for Business con domini separati. Questo articolo contiene collegamenti a documenti correlati sui prerequisiti, la configurazione e la disabilitazione dell'autenticazione moderna e alle informazioni su alcuni client correlati, ad esempio i client di Outlook e Skype.
  
- [Che cos’è l’autenticazione moderna](hybrid-modern-auth-overview.md#BKMK_WhatisModAuth)
- [Cosa cambia con l’uso dell'autenticazione moderna](hybrid-modern-auth-overview.md#BKMK_WhatChanges)
- [Controllare lo stato di autenticazione moderna nell’ambiente locale](hybrid-modern-auth-overview.md#BKMK_CheckStatus)
- [Come soddisfare i prerequisiti di autenticazione moderna](#do-you-meet-modern-authentication-prerequisites)
- [Altre informazioni necessarie per iniziare a usare l’autenticazione moderna](hybrid-modern-auth-overview.md#BKMK_Whatelse)

## <a name="what-is-modern-authentication"></a>Che cos’è l’autenticazione moderna
<a name="BKMK_WhatisModAuth"> </a>

Autenticazione moderna è un termine che indica una combinazione di metodi di autenticazione e autorizzazione tra un client, ad esempio il portatile o il telefono, e un server oltre ad alcune misure di sicurezza basate su criteri di accesso, con cui l’utente potrebbe avere già familiarità. Ciò include:
  
- **Metodi di autenticazione**: autenticazione a più fattori (MFA), autenticazione con smart card, autenticazione basata sui certificati del client
- **Metodi di autorizzazione**: implementazione Microsoft dell’autorizzazione OAuth (Open Authorization)
- **Criteri di accesso condizionale**: gestione di applicazioni mobili (MAM) e accesso condizionale Azure Active Directory (Azure AD)

La gestione delle identità utente con l'autenticazione moderna offre agli amministratori numerosi strumenti da usare per la protezione delle risorse e metodi più sicuri di gestione delle identità in locale (Exchange e Skype for Business), Exchange ibrido e gli scenari ibridi o con domini separati di Skype for Business.
  
Tenere presente che, poiché il funzionamento di Skype for Business è strettamente correlato a quello di Exchange, l’approccio di accesso degli utenti client di Skype for Business sarà influenzato dallo stato di autenticazione moderna di Exchange. Ciò si applica anche se si ha un’architettura ibrida dei _domini separati_ di Skype for Business in cui si ha sia Skype for Business Online che Skype for Business in locale, con utenti ospitati in entrambe le posizioni.

Per altre informazioni sull'autenticazione moderna in Office 365, vedere [Supporto per l’app client di Office 365: autenticazione moderna](microsoft-365-client-support-modern-authentication.md).
  
> [!IMPORTANT]
> Dal mese di agosto 2017 tutti i nuovi tenant di Office 365 che includono Skype for Business Online ed Exchange Online hanno l'autenticazione moderna abilitata per impostazione predefinita. I tenant preesistenti non cambiano lo stato autenticazione moderna predefinito, tutti i nuovi tenant invece supportano automaticamente il set espanso delle funzionalità d’identità elencate in precedenza. Per controllare lo stato di autenticazione moderna, vedere la sezione [Verifica dello stato di autenticazione moderna in ambiente locale](hybrid-modern-auth-overview.md#BKMK_CheckStatus).
  
## <a name="what-changes-when-i-use-modern-authentication"></a>Che cosa cambia con l’uso dell'autenticazione moderna
<a name="BKMK_WhatChanges"> </a>

Se si usa l'autenticazione moderna con il server locale di Skype for Business o Exchange, si effettua ancora l’*autenticazione* degli utenti in locale, tuttavia la modalità di *autorizzazione* dell’accesso alle risorse, ad esempio i file o i messaggi di posta elettronica, cambia. Per questo motivo, anche se l'autenticazione moderna si riferisce alle comunicazioni tra client e server, i passaggi eseguiti durante la configurazione dell’autenticazione moderna in evoSTS (un servizio token di sicurezza usato da Azure AD) risultano impostati come server di autenticazione per i server di Skype for Business ed Exchange locali.
  
La modifica eseguita in evoSTS consente ai server locali di sfruttare le funzionalità OAuth (emissione di token) per l'autorizzazione dei client e inoltre consente loro di usare i metodi di sicurezza comuni nel cloud, ad esempio l'autenticazione a più fattori. Inoltre, evoSTS genera token che consentono agli utenti di richiedere l'accesso alle risorse senza specificare la password come parte della richiesta. Indipendentemente dalla posizione degli utenti, online o in locale, dalla posizione che ospita la risorsa necessaria, EvoSTS diventa il centro di autorizzazione degli utenti e dei client dopo che è stata configurata l'autenticazione moderna.
  
Ad esempio, se un client di Skype for Business deve accedere a un server Exchange per ottenere informazioni sul calendario per conto di un utente, usa Active Directory Authentication Library (ADAL) per eseguire questa operazione. ADAL è una libreria di codice creata per rendere disponibili le risorse protette della directory alle applicazioni del client tramite i token di sicurezza OAuth. ADAL è compatibile con OAuth per verificare le attestazioni e scambiare i token, anziché le password, per consentire a un utente l’accesso a una risorsa. In passato, l'autorità in una transazione di questo tipo, ossia il server che convalida le attestazioni degli utenti e genera i token necessari, era un servizio token di sicurezza locale o persino Active Directory Federation Services. Tuttavia, l'autenticazione moderna centralizza tale autorità tramite l’uso di Azure AD.
  
Inoltre, anche se gli ambienti del server di Exchange e Skype for Business sono interamente locali, il server di autorizzazione è online e l'ambiente locale deve essere in grado di creare e mantenere una connessione all'abbonamento a Office 365 nel cloud, e all'istanza di Azure Active Directory usata dall'abbonamento come directory.
  
Caratteristiche che non cambiano Sia che ci si trovi in una versione ibrida con dominio separato o che si usino i server di Skype for Business e di Exchange in locale, tutti gli utenti devono prima autenticarsi *in locale*. In un'implementazione ibrida dell'autenticazione moderna, _Lyncdiscovery_ e _AutoDiscovery_ puntano entrambi al server locale.
  
> [!IMPORTANT]
> Se è necessario conoscere le topologie specifiche di Skype for Business supportate dall’autenticazione moderna, vedere [qui](https://technet.microsoft.com/library/mt803262.aspx).
  
## <a name="check-the-modern-authentication-status-of-your-on-premises-environment"></a>Controllare lo stato dell’autenticazione moderna nell’ambiente locale
<a name="BKMK_CheckStatus"> </a>

Poiché l'autenticazione moderna cambia il server di autorizzazione usato quando i servizi sfruttano il protocollo OAuth/S2S, è necessario sapere se l'autenticazione moderna è abilitata o disabilitata per gli ambienti di Skype for Business e Exchange locali. Per controllare lo stato dei server Exchange eseguire il comando di PowerShell seguente:

```powershell
Get-OrganizationConfig | ft OAuth*
```

Se il valore della proprietà _OAuth2ClientProfileEnabled_ è **Falso**, l'autenticazione moderna è disabilitata.

Per altre informazioni sul cmdlet Get-OrganizationConfig, vedere [Get-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/organization/get-organizationconfig).

Per controllare lo stato dei server di Skype for Business eseguire il comando di PowerShell seguente:

```powershell
Get-CSOAuthConfiguration
```

Se il comando restituisce una proprietà _OAuthServers_ vuota o se il valore della proprietà _ClientADALAuthOverride_ non è **Consentito**, l'autenticazione moderna è disabilitata.

Per altre informazioni sul cmdlet Get-CsOAuthConfiguration, vedere [Get-CsOAuthConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csoauthconfiguration).
  
## <a name="do-you-meet-modern-authentication-prerequisites"></a>Come soddisfare i prerequisiti di autenticazione moderna

Prima di procedere, verificare questi elementi nell’elenco:
  
- **Informazioni specifiche per Skype for Business**
  - Tutti i server devono aver eseguito gli aggiornamenti cumulativi di maggio 2017 (CU5) per Skype for Business Server 2015 o versione successiva
    - **Eccezione:** Survivable Branch Appliance (SBA) può avere la versione corrente (basata su Lync 2013)
  - Il dominio SIP viene aggiunto come dominio federato in Office 365
  - Tutti i front end di Skype for Business devono avere connessioni in uscita a Internet, agli URL di autenticazione di Office 365 (TCP 443) e agli elenchi CRL radice dei certificati noti (TCP 80) elencati nelle righe 56 e 125 della sezione "Microsoft 365 Common and Office" degli [URL e intervalli di indirizzi IP per Office 365](urls-and-ip-address-ranges.md).
  
- **Skype for Business in locale in un ambiente ibrido di Office 365**
  - Distribuzione di Skype for Business Server 2019 con tutti i server che eseguono Skype for Business Server 2019.
  - Distribuzione di Skype for Business Server 2015 con tutti i server che eseguono Skype for Business Server 2015.
  - Distribuzione con un massimo di due versioni del server differenti, come indicato di seguito:
    - Skype for Business Server 2015
    - Skype for Business Server 2019
  - Tutti i server di Skype for Business devono avere installato gli aggiornamenti cumulativi più recenti, vedere [Aggiornamenti dei server di Skype for Business](https://docs.microsoft.com/skypeforbusiness/sfb-server-updates) per trovare e gestire tutti gli aggiornamenti disponibili.
  - Nell’ambiente ibrido non è disponibile Lync Server 2010 o 2013.

>[!NOTE]
>Se i server front-end di Skype for Business usano un server proxy per l'accesso a Internet, l'IP del server proxy e il numero di porta usati devono essere immessi nella sezione di configurazione del file web.config per ogni front-end.
  
- C:\Program Files\Skype for Business Server 2015\Web Components\Web ticket\int\web.config
- C:\Program Files\Skype for Business Server 2015\Web Components\Web ticket\ext\web.config

```xml
<configuration>
  <system.net>
    <defaultProxy>
      <proxy
        proxyaddress="https://192.168.100.60:8080"
        bypassonlocal="true" />
    </defaultProxy>
  </system.net>
</configuration>
```

> [!IMPORTANT]
> Assicurarsi di sottoscrivere il feed RSS per [URL e intervalli di indirizzi IP di Office 365](urls-and-ip-address-ranges.md) per rimanere aggiornati con gli elenchi più recenti di URL necessari.
  
- **Informazioni specifiche per Exchange Server**
  - È possibile usare Exchange Server 2013 CU19 e versioni successive, Exchange Server 2016 CU8 e versioni successive o Exchange Server 2019 CU1 e versioni successive.
  - Non è disponibile Exchange Server 2010 nell'ambiente ibrido.
  - La ripartizione del carico SSL non è configurata. Sono supportate la terminazione e la nuova esecuzione della crittografia SSL.
  - Nel caso l’ambiente utilizzi un'infrastruttura del server proxy per consentire ai server di connettersi a Internet, assicurarsi che tutti i server di Exchange abbiano il server proxy definito nella proprietà [InternetWebProxy](https://technet.microsoft.com/library/bb123716%28v=exchg.160%29.aspx).
  
- **Exchange Server in locale in un ambiente ibrido di Office 365**

  - Se si usa Exchange Server 2013, per almeno un server devono essere installati i ruoli server Accesso client e Cassette postali. Sebbene sia possibile installare i ruoli Accesso client e Cassette postali su server separati, si consiglia vivamente di installare entrambi i ruoli sullo stesso server per fornire una maggiore affidabilità e prestazioni migliorate.
  - Se si usa Exchange Server 2016, per almeno un server devono essere installati il ruolo server Cassette postali.
  - Nell’ambiente ibrido non è disponibile Exchange Server 2007 o 2010.
  - Tutti i server di Exchange devono avere installato gli aggiornamenti cumulativi più recenti, vedere [Aggiornamento di Exchange agli aggiornamenti cumulativi più recenti](https://docs.microsoft.com/exchange/plan-and-deploy/install-cumulative-updates?view=exchserver-2019) per trovare e gestire tutti gli aggiornamenti disponibili.

- **Requisiti del client e del protocollo di Exchange**
  
  - I client seguenti supportano l'autenticazione moderna:

  |**Client**|**Protocollo principale**|**Note**|
  |:-----|:-----|:-----|
  |Outlook 2013 e Outlook 2016  <br/> |MAPI su HTTP  <br/> |MAPI su HTTP deve essere abilitato in Exchange per sfruttare l'autenticazione moderna con tali client, in genere abilitato o impostato su Vero per le nuove installazioni dell’Exchange 2013 Service Pack 1 e versioni successive. Per altre informazioni, vedere [Funzionamento dell'autenticazione moderna per le app client di Office 2013 e Office 2016](modern-auth-for-office-2013-and-2016.md).  <br/> Verificare che sia in esecuzione la build minima richiesta di Outlook, vedere [Aggiornamenti più recenti delle versioni di Outlook in uso di Windows Installer (MSI)](https://docs.microsoft.com/officeupdates/outlook-updates-msi).  <br/> |
  |Outlook 2016 per Mac  <br/> |Servizi Web Exchange  <br/> |  <br/> |
  |Outlook per iOS e Android  <br/> |  <br/> |Per altre informazioni, vedere [Utilizzo dell'autenticazione moderna ibrida con Outlook per iOS e Android](https://docs.microsoft.com/Exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth).  <br/> |
  |Client Exchange ActiveSync (ad esempio la posta di iOS11)  <br/> |Exchange ActiveSync  <br/> |Nei client Exchange ActiveSync che supportano l'autenticazione moderna, è necessario ricreare il profilo per passare dall'autenticazione di base all'autenticazione moderna.  <br/> |

- **Prerequisiti generali**
  - Se si usa AD FS (Active Directory Federation Services), per la federazione è necessario Windows 2012 R2 AD FS 3.0 e versioni successive.
  - Le configurazioni delle identità sono costituite da uno dei tipi supportati da Azure AD Connect, ad esempio sincronizzazione hash delle password, autenticazione pass-through e STS locali supportati da Office 365.
  - Azure AD Connect è configurato e funziona per la replica e sincronizzazione utente.
  - È stato verificato che la distribuzione ibrida sia configurata con la modalità di topologia ibrida classica di Exchange tra l'ambiente locale e Office 365. Le istruzioni del supporto ufficiale per la distribuzione ibrida di Exchange indicano che è necessario avere CU o CU1 corrente.
    > [!NOTE]
    > L'autenticazione moderna ibrida non è compatibile con l’[Agente ibrido](https://docs.microsoft.com/exchange/hybrid-deployment/hybrid-agent).

  - Verificare che un utente di test locale e un utente di test ibrido ospitato in Office 365, possano accedere al client desktop di Skype for Business, se si vuole usare l'autenticazione moderna con Skype, e a Microsoft Outlook, se si vuole usare l'autenticazione moderna con Exchange.

## <a name="what-else-do-i-need-to-know-before-i-begin"></a>Altre informazioni necessarie per iniziare
<a name="BKMK_Whatelse"> </a>

- Tutti gli scenari per i server locali implicano la configurazione dell'autenticazione moderna in locale (a tale scopo per Skype for Business è disponibile un elenco di topologie supportate), in modo che il server responsabile dell'autenticazione e dell'autorizzazione si trovi nel cloud Microsoft (servizio token di sicurezza di Azure Active Directory, detto "evoSTS"), e come aggiornamento di Azure AD sugli URL o gli spazi dei nomi usati nell’installazione locale di Skype for Business o Exchange. Di conseguenza, i server locali assumono una dipendenza cloud Microsoft. Questa operazione potrebbe essere considerata come la configurazione dell’"autenticazione ibrida".
- Questo articolo contiene collegamenti ad altri articoli che semplificano la scelta delle topologie di autenticazione moderna supportate, obbligatorie solo per Skype for Business. Sono inoltre presenti collegamenti ad articoli sulle procedure per configurare Exchange o Skype for Business locale oppure per disabilitarne l'autenticazione moderna. Aggiungere questa pagina ai Preferiti del browser per avere un riferimento di base per l'uso dell'autenticazione moderna nell'ambiente server.

## <a name="related-topics"></a>Argomenti correlati
<a name="BKMK_URLListforMA"> </a>

- [Come configurare Exchange Server locale per utilizzare l'autenticazione moderna](configure-exchange-server-for-hybrid-modern-authentication.md)
- [Topologie di Skype for Business supportate per l'autenticazione moderna](https://technet.microsoft.com/library/mt803262.aspx)
- [Come configurare Skype for Business locale per utilizzare l'autenticazione moderna](configure-skype-for-business-for-hybrid-modern-authentication.md)
- [Rimuovere o disabilitare l'autenticazione moderna ibrida da Skype for Business ed Exchange](remove-or-disable-hybrid-modern-authentication-from-skype-for-business-and-excha.md)
