---
title: Come configurare Skype for Business locale per utilizzare l'autenticazione moderna ibrida
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/3/2019
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 522d5cec-4e1b-4cc3-937f-293570717bc6
ms.collection:
- M365-security-compliance
f1.keywords:
- NOCSH
description: Informazioni su come configurare Skype for Business in locale per l'utilizzo dell'autenticazione moderna ibrida (HMA, Hybrid Modern Authentication), offrendo un'autenticazione e un'autorizzazione degli utenti più sicure.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f3177bafb6eff27053dca61ec576666cae4a97bb
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911151"
---
# <a name="how-to-configure-skype-for-business-on-premises-to-use-hybrid-modern-authentication"></a>Come configurare Skype for Business locale per utilizzare l'autenticazione moderna ibrida

*Questo articolo può essere applicato sia a Microsoft 365 Enterprise che a Office 365 Enterprise.*

Autenticazione moderna, è un metodo di gestione delle identità che offre un'autenticazione e un'autorizzazione degli utenti più sicure, è disponibile per i server Skype for Business locali e exchange server locali e ibridi Skype for Business con dominio diviso.
  
 **Importante** Vuoi saperne di più sull'autenticazione moderna (MA) e sul motivo per cui preferisci usarlo nella tua azienda o nell'organizzazione? Consultare [questo documento](hybrid-modern-auth-overview.md) per una panoramica. Se è necessario sapere quali topologie di Skype for Business sono supportate con MA, questo è documentato qui.
  
 **Prima di iniziare,** uso questi termini:
  
- Autenticazione moderna

- Autenticazione moderna ibrida (HMA)

- Exchange locale (EXCH)

- Exchange Online (EXO)

- Skype for Business locale (SFB)

- Skype for Business online (SFBO)

Inoltre, se un elemento grafico in questo articolo ha un oggetto in grigio o in grigio, significa che **l'elemento** visualizzato in grigio non è incluso nella configurazione specifica di Ma.
  
## <a name="read-the-summary"></a>Leggere il riepilogo

Questo riepilogo suddivide il processo in passaggi che altrimenti potrebbero andare persi durante l'esecuzione ed è consigliabile un elenco di controllo globale per tenere traccia della posizione in cui ci si trova.
  
1. Prima di tutto, assicurati di soddisfare tutti i prerequisiti.

1. Poiché molti **prerequisiti sono** comuni sia per Skype for Business che per Exchange, vedere l'articolo di panoramica [per l'elenco di controllo pre-req.](hybrid-modern-auth-overview.md) Eseguire questa  *operazione prima*  di iniziare una delle operazioni descritte in questo articolo.

1. Raccogliere le informazioni specifiche di HMA necessarie in un file o in OneNote.

1. Attivare l'autenticazione moderna per EXO (se non è già attivata).

1. Attivare l'autenticazione moderna per SFBO (se non è già attivata).

1. Attivare l'autenticazione moderna ibrida per Exchange locale.

1. Attivare l'autenticazione moderna ibrida per Skype for Business locale.

Questi passaggi attivano MA per SFB, SFBO, EXCH ed EXO, ovvero tutti i prodotti che possono partecipare a una configurazione HMA di SFB e SFBO (incluse le dipendenze da EXCH/EXO). In altre parole, se gli utenti sono ospitati o hanno cassette postali create in qualsiasi parte dell'ambiente ibrido (EXO + SFBO, EXO + SFB, EXCH + SFBO o EXCH + SFB), il prodotto finito sarà simile al seguente:
  
![Una topologia HMA Misto 6 di Skype for business è attivata in tutte e quattro le posizioni possibili.](../media/ab89cdf2-160b-49ac-9b71-0160800acfc8.png)
  
Come puoi vedere, ci sono quattro diversi posti in cui attivare MA! Per un'esperienza utente ottimale, ti consigliamo di attivare Ma in tutte e quattro queste posizioni. Se non è possibile attivare Ma in tutte queste posizioni, modificare i passaggi in modo da attivare MA solo nelle posizioni necessarie per l'ambiente.
  
Vedi [l'argomento Supportability per Skype for Business con MA](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported) per le topologie supportate.
  
 **Importante** Verificare di aver soddisfatto tutti i prerequisiti prima di iniziare. Queste informazioni sono disponibili in Panoramica e prerequisiti dell'autenticazione moderna [ibrida.](hybrid-modern-auth-overview.md)
  
## <a name="collect-all-hma-specific-info-youll-need"></a>Raccogliere tutte le informazioni specifiche di HMA necessarie

Dopo aver verificato di soddisfare i [](hybrid-modern-auth-overview.md) prerequisiti per l'uso dell'autenticazione moderna (vedi la nota precedente), devi creare un file per contenere le informazioni necessarie per configurare HMA nei passaggi successivi. Esempi usati in questo articolo:
  
- **Dominio SIP/SMTP**

  - Ex. contoso.com (federato con Office 365)

- **Tenant ID**

  - GUID che rappresenta il tenant di Office 365 (all'accesso di contoso.onmicrosoft.com).

- **URL del servizio Web SFB 2015 CU5**

sono necessari URL di servizi Web interni ed esterni per tutti i pool SfB 2015 distribuiti. Per ottenere queste informazioni, eseguire le operazioni seguenti da Skype for Business Management Shell:
  
```powershell
Get-CsService -WebServer | Select-Object PoolFqdn, InternalFqdn, ExternalFqdn | FL
```

- Ex. Interno: https://lyncwebint01.contoso.com

- Ex. Esterno: https://lyncwebext01.contoso.com

Se si utilizza un server Standard Edition, l'URL interno sarà vuoto. In questo caso, utilizzare il nome di dominio completo del pool per l'URL interno.
  
## <a name="turn-on-modern-authentication-for-exo"></a>Attivare l'autenticazione moderna per EXO

Seguire le istruzioni qui: [Exchange Online: Come abilitare il tenant per l'autenticazione moderna.](https://social.technet.microsoft.com/wiki/contents/articles/32711.exchange-online-how-to-enable-your-tenant-for-modern-authentication.aspx)
  
## <a name="turn-on-modern-authentication-for-sfbo"></a>Attivare l'autenticazione moderna per SFBO

Seguire le istruzioni qui: [Skype for Business online: Abilitare il tenant per l'autenticazione moderna.](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)
  
## <a name="turn-on-hybrid-modern-authentication-for-exchange-on-premises"></a>Attivare l'autenticazione moderna ibrida per Exchange locale

Seguire le istruzioni qui: Come configurare Exchange Server locale per [l'utilizzo dell'autenticazione moderna ibrida](configure-exchange-server-for-hybrid-modern-authentication.md).
  
## <a name="turn-on-hybrid-modern-authentication-for-skype-for-business-on-premises"></a>Attivare l'autenticazione moderna ibrida per Skype for Business locale

### <a name="add-on-premises-web-service-urls-as-spns-in-azure-active-directory"></a>Aggiungere URL del servizio Web locale come SPN in Azure Active Directory

Ora dovrai eseguire comandi per aggiungere gli URL (raccolti in precedenza) come entità servizio in SFBO.
  
 **Nota** I nomi delle entità servizio (SPN) identificano i servizi Web e li associano a un'entità di sicurezza ,ad esempio un nome di account o un gruppo, in modo che il servizio possa agire per conto di un utente autorizzato. I client che e autenticano un server utilizzano le informazioni contenute nei nomi SPN.
  
1. Prima di tutto, connettersi ad Azure Active Directory (Azure AD) con [queste istruzioni.](/powershell/azure/active-directory/overview?view=azureadps-1.0)

2. Eseguire questo comando, in locale, per ottenere un elenco degli URL del servizio Web SFB.

   Tieni presente che AppPrincipalId inizia con `00000004` . Corrisponde a Skype for Business online.

   Prendere nota (e screenshot per un confronto successivo) dell'output di questo comando, che includerà un URL SE e WS, ma costituito principalmente da SPN che iniziano con `00000004-0000-0ff1-ce00-000000000000/` .

```powershell
Get-MsolServicePrincipal -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 | Select -ExpandProperty ServicePrincipalNames
```

3. Se gli **URL** SFB interni o esterni da locale non sono presenti ( ad esempio, e sarà necessario aggiungere tali https://lyncwebint01.contoso.com record specifici a questo https://lyncwebext01.contoso.com) elenco.

    Assicurati di sostituire  *gli URL di esempio* seguenti con gli URL effettivi nei comandi Aggiungi.
  
```powershell
$x= Get-MsolServicePrincipal -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
$x.ServicePrincipalnames.Add("https://lyncwebint01.contoso.com/")
$x.ServicePrincipalnames.Add("https://lyncwebext01.contoso.com/")
Set-MSOLServicePrincipal -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $x.ServicePrincipalNames
```
  
4. Verificare che i nuovi record siano stati aggiunti eseguendo di nuovo il **comando Get-MsolServicePrincipal** del passaggio 2 e esaminando l'output. Confronta l'elenco o lo screenshot di prima con il nuovo elenco di SPN. È inoltre possibile creare uno screenshot del nuovo elenco per i record. Se hai avuto esito positivo, vedrai i due nuovi URL nell'elenco. In base all'esempio, l'elenco degli SPN includerà ora gli URL specifici https://lyncwebint01.contoso.com e https://lyncwebext01.contoso.com/ .

### <a name="create-the-evosts-auth-server-object"></a>Creare l'oggetto server di autenticazione EvoSTS

Eseguire il comando seguente in Skype for Business Management Shell.
  
```powershell
New-CsOAuthServer -Identity evoSTS -MetadataURL https://login.windows.net/common/FederationMetadata/2007-06/FederationMetadata.xml -AcceptSecurityIdentifierInformation $true -Type AzureAD
```

### <a name="enable-hybrid-modern-authentication"></a>Abilitare l'autenticazione moderna ibrida

Questo è il passaggio che attiva effettivamente MA. Tutti i passaggi precedenti possono essere eseguiti in anticipo senza modificare il flusso di autenticazione client. Quando si è pronti a modificare il flusso di autenticazione, eseguire questo comando in Skype for Business Management Shell.

```powershell
Set-CsOAuthConfiguration -ClientAuthorizationOAuthServerIdentity evoSTS
```

## <a name="verify"></a>Verificare

Dopo aver abilitato HMA, l'accesso successivo di un client userà il nuovo flusso di autenticazione. Tieni presente che l'attivazione di HMA non attiverà una riautenticazione per alcun client. I client eserciteranno nuovamente l'autenticazione in base alla durata dei token di autenticazione e/o dei certificati di cui dispongono.
  
Per verificare che HMA funzioni dopo aver abilitato, disconnettersi da un client Windows SFB di prova e fare clic su "elimina le credenziali". Accedi di nuovo. Il client deve ora usare il flusso di autenticazione moderna e l'account di accesso includerà ora un prompt di **Office 365** per un account aziendale o dell'istituto di istruzione, visualizzato subito prima che il client contatti il server ed eseere l'accesso.
  
Dovresti anche controllare "Informazioni di configurazione" per i client Skype for Business per un'"autorità OAuth". A tale scopo, tenere premuto CTRL mentre si fa clic con il pulsante destro del mouse sull'icona Skype for Business nella barra delle notifiche di Windows. Fare **clic su Informazioni** di configurazione nel menu visualizzato. Nella finestra "Informazioni di configurazione di Skype for Business" che verrà visualizzata sul desktop, cercare quanto segue:
  
![Le informazioni di configurazione di un client Skype for Business che utilizza l'autenticazione moderna mostrano un URL dell'autorità OAUTH di Lync ed EWS di https://login.windows.net/common/oauth2/authorize .](../media/4e54edf5-c8f8-4e7f-b032-5d413b0232de.png)
  
È inoltre necessario tenere premuto IL TASTO CTRL contemporaneamente a fare clic con il pulsante destro del mouse sull'icona del client di Outlook (anche nella barra delle notifiche di Windows) e scegliere "Stato connessione". Cercare l'indirizzo SMTP del client rispetto a un tipo AuthN di 'Bearer', che rappresenta il token del portatore \* utilizzato in OAuth.
  
## <a name="related-articles"></a>Articoli correlati

[Collegamento alla panoramica dell'autenticazione moderna.](hybrid-modern-auth-overview.md)
  
È necessario sapere come usare l'autenticazione moderna (ADAL) per i client Skype for Business? Di seguito sono riportati i [passaggi.](./hybrid-modern-auth-overview.md)