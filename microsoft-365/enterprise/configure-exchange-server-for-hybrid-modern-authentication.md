---
title: Come configurare Exchange Server locale per utilizzare l'autenticazione moderna ibrida
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 06/16/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: cef3044d-d4cb-4586-8e82-ee97bd3b14ad
ms.collection:
- M365-security-compliance
f1.keywords:
- NOCSH
description: Informazioni su come configurare un Exchange Server locale per l'utilizzo dell'autenticazione moderna ibrida (HMA), offrendo un'autenticazione e un'autorizzazione utente più sicure.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3841f429399500cfc24ebadc89c74d478d2290d9
ms.sourcegitcommit: ec293978e951b09903b79e6642aa587824935e0c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2021
ms.locfileid: "49780285"
---
# <a name="how-to-configure-exchange-server-on-premises-to-use-hybrid-modern-authentication"></a>Come configurare Exchange Server locale per utilizzare l'autenticazione moderna ibrida

*Questo articolo si applica sia a Microsoft 365 Enterprise che a Office 365 Enterprise*.

L'autenticazione moderna ibrida (HMA, Hybrid Modern Authentication) è un metodo di gestione delle identità che offre un'autenticazione e un'autorizzazione utente più sicure ed è disponibile per le distribuzioni ibride locali del server Exchange.

## <a name="fyi"></a>FYI

Prima di iniziare, chiamo:

- HMA per \> l'autenticazione moderna ibrida

- EXCH locale di Exchange \>

- Exchange Online \> EXO

Inoltre, se un elemento grafico in questo articolo ha un oggetto *"in grigio"* o "in grigio", significa che l'elemento visualizzato in grigio non è incluso nella configurazione specifica di HMA.

## <a name="enabling-hybrid-modern-authentication"></a>Abilitazione dell'autenticazione moderna ibrida

L'attivazione di HMA significa:

1. Assicurarsi di soddisfare i prereq prima di iniziare.

1. Poiché molti **prerequisiti sono** comuni sia per Skype for Business che per Exchange, panoramica dell'autenticazione moderna ibrida e prerequisiti per l'utilizzo con i server Skype for Business ed [Exchange locali.](hybrid-modern-auth-overview.md) Eseguire questa operazione prima di iniziare uno dei passaggi descritti in questo articolo.

1. Aggiunta di URL di servizi Web locali come nomi dell'entità servizio **(SPN)** in Azure AD.

1. Verificare che tutte le directory virtuali siano abilitate per HMA

1. Verifica dell'oggetto EvoSTS Auth Server

1. Abilitazione di HMA in EXCH.

 **Nota** La versione di Office in cui si è installato supporta Ma? Vedere Come funziona l'autenticazione moderna per le app client di [Office 2013 e Office 2016.](modern-auth-for-office-2013-and-2016.md)

## <a name="make-sure-you-meet-all-the-prerequisites"></a>Assicurarsi di soddisfare tutti i prerequisiti

Poiché molti prerequisiti sono comuni sia per Skype for Business che per Exchange, esaminare la panoramica dell'autenticazione moderna ibrida e i prerequisiti per l'utilizzo con i server Skype for Business ed [Exchange locali.](hybrid-modern-auth-overview.md) Eseguire questa  *operazione prima*  di iniziare uno dei passaggi descritti in questo articolo.

## <a name="add-on-premises-web-service-urls-as-spns-in-azure-ad"></a>Aggiungere URL dei servizi Web locali come nomi SPN in Azure AD

Eseguire i comandi che assegnano gli URL dei servizi Web locali come nomi SPN di Azure AD. I nomi SPN vengono utilizzati dai computer client e dai dispositivi durante l'autenticazione e l'autorizzazione. Tutti gli URL che possono essere usati per connettersi dall'ambiente locale ad Azure Active Directory (Azure AD) devono essere registrati in Azure AD (inclusi gli spazi dei nomi interni ed esterni).

Prima di tutto, raccogliere tutti gli URL che è necessario aggiungere in AAD. Eseguire questi comandi in locale:

```powershell
Get-MapiVirtualDirectory | FL server,*url*
Get-WebServicesVirtualDirectory | FL server,*url*
Get-ClientAccessServer | fl Name, AutodiscoverServiceInternalUri
Get-OABVirtualDirectory | FL server,*url*
Get-AutodiscoverVirtualDirectory | FL server,*url*
Get-OutlookAnywhere | FL server,*url*
```

Verificare che gli URL a cui i client possano connettersi siano elencati come nomi dell'entità servizio HTTPS in AAD.

1. Prima di tutto, connettersi ad AAD con [queste istruzioni.](connect-to-microsoft-365-powershell.md)

   **Nota** Devi usare _l'opzione Connect-MsolService_ in questa pagina per poter usare il comando seguente.

2. Per gli URL correlati a Exchange, digitare il comando seguente:

   ```powershell
   Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 | select -ExpandProperty ServicePrincipalNames
   ```

   Prendere nota (e screenshot per un confronto successivo) dell'output di questo comando, che deve includere un URL https://  *autodiscover.yourdomain.com*  e https://  *mail.yourdomain.com,* ma principalmente costituito da nomi SPN che iniziano con 000000002-0000-0ff1-ce00-0000000000000/. Se mancano https:// URL locali, sarà necessario aggiungere tali record specifici all'elenco.

3. Se i record MAPI/HTTP, EWS, ActiveSync, OAB e Autodiscover interni ed esterni non sono presenti in questo elenco, è necessario aggiungerli utilizzando il comando seguente (gli URL di esempio sono ' `mail.corp.contoso.com` ' e ' ', ma è necessario sostituire gli URL di esempio con i `owa.contoso.com` **propri**):

   ```powershell
   $x= Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000
   $x.ServicePrincipalnames.Add("https://mail.corp.contoso.com/")
   $x.ServicePrincipalnames.Add("https://owa.contoso.com/")
   Set-MSOLServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $x.ServicePrincipalNames
   ```

4. Verificare che i nuovi record siano stati aggiunti eseguendo di nuovo il Get-MsolServicePrincipal del passaggio 2 e esaminando l'output. Confrontare l'elenco o lo screenshot di prima con il nuovo elenco di nomi SPN. È inoltre possibile acquisire uno screenshot del nuovo elenco per i record. Se l'operazione ha avuto esito positivo, nell'elenco verranno visualizzati i due nuovi URL. In base all'esempio, l'elenco dei nomi SPN includerà ora gli URL e  `https://mail.corp.contoso.com`  `https://owa.contoso.com` .

## <a name="verify-virtual-directories-are-properly-configured"></a>Verificare che le directory virtuali siano configurate correttamente

Verificare ora che OAuth sia abilitato correttamente in Exchange in tutte le directory virtuali che Outlook potrebbe utilizzare eseguendo i comandi seguenti:

```powershell
Get-MapiVirtualDirectory | FL server,*url*,*auth*
Get-WebServicesVirtualDirectory | FL server,*url*,*oauth*
Get-OABVirtualDirectory | FL server,*url*,*oauth*
Get-AutoDiscoverVirtualDirectory | FL server,*oauth*
```

Controlla l'output per assicurarti che **OAuth** sia abilitato in ognuno di questi VDir, avrà un aspetto simile al seguente (e la cosa chiave da osservare è "OAuth"):

```powershell
Get-MapiVirtualDirectory | fl server,*url*,*auth*

Server                        : EX1
InternalUrl                   : https://mail.contoso.com/mapi
ExternalUrl                   : https://mail.contoso.com/mapi
IISAuthenticationMethods      : {Ntlm, OAuth, Negotiate}
InternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
ExternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
```

Se OAuth non è presente in alcun server e in una delle quattro directory virtuali, è necessario aggiungerlo utilizzando i comandi pertinenti prima di procedere ([Set-MapiVirtualDirectory,](https://docs.microsoft.com/powershell/module/exchange/set-mapivirtualdirectory) [Set-WebServicesVirtualDirectory,](https://docs.microsoft.com/powershell/module/exchange/set-webservicesvirtualdirectory) [Set-OABVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/set-oabvirtualdirectory)e [Set-AutodiscoverVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/set-autodiscovervirtualdirectory)).

## <a name="confirm-the-evosts-auth-server-object-is-present"></a>Verificare che l'oggetto server di autenticazione EvoSTS sia presente

Tornare a Exchange Management Shell locale per l'ultimo comando. Ora è possibile verificare che l'ambiente locale abbia una voce per il provider di autenticazione evoSTS:

```powershell
Get-AuthServer | where {$_.Name -eq "EvoSts"}
```

L'output dovrebbe mostrare un AuthServer con il nome EvoSts e lo stato "Enabled" deve essere True. Se non viene visualizzato, è consigliabile scaricare ed eseguire la versione più recente della procedura guidata di configurazione ibrida.

 **Importante** Se si esegue Exchange 2010 nell'ambiente, il provider di autenticazione EvoSTS non verrà creato.

## <a name="enable-hma"></a>Abilitare HMA

Eseguire il comando seguente in Exchange Management Shell, locale:

```powershell
Set-AuthServer -Identity EvoSTS -IsDefaultAuthorizationEndpoint $true
Set-OrganizationConfig -OAuth2ClientProfileEnabled $true
```

## <a name="verify"></a>Verificare

Dopo aver abilitato HMA, l'accesso successivo di un client userà il nuovo flusso di autenticazione. Tieni presente che l'attivazione di HMA non attiverà una nuova autenticazione per alcun client. I client e autenticano di nuovo in base alla durata dei token di autenticazione e/o dei certificati di cui dispongono.

È inoltre necessario tenere premuto il tasto CTRL quando si fa clic con il pulsante destro del mouse sull'icona del client Di Outlook (anche nella barra delle notifiche di Windows) e si fa clic su "Stato connessione". Cercare l'indirizzo SMTP del client su un tipo "Authn" di "Bearer", che rappresenta il token bearer utilizzato \* in OAuth.

 **Nota** È necessario configurare Skype for Business con HMA? Sono necessari due articoli: uno in cui sono elencate [le topologie](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)supportate e uno che illustra come eseguire [la configurazione.](configure-skype-for-business-for-hybrid-modern-authentication.md)

## <a name="using-hybrid-modern-authentication-with-outlook-for-ios-and-android"></a>Utilizzo dell'autenticazione moderna ibrida con Outlook per iOS e Android

Se si è un cliente locale che utilizza il server Exchange su TCP 443, ignorare l'elaborazione del traffico per i seguenti intervalli IP:

```text
52.125.128.0/20
52.127.96.0/23
```

## <a name="related-topics"></a>Argomenti correlati

[Requisiti di configurazione dell'autenticazione moderna per la transizione da Office 365 dedicato/ITAR a vNext](https://docs.microsoft.com/exchange/troubleshoot/modern-authentication/modern-authentication-configuration)
