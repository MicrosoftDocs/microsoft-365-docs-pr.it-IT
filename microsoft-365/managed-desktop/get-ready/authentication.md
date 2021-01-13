---
title: Preparare l'accesso alle risorse locali per Microsoft Managed Desktop
description: Passaggi importanti per assicurarsi che un annuncio di Azure sia in grado di comunicare con Active Directory locale per fornire l'autenticazione
keywords: Microsoft Managed Desktop, Microsoft 365, servizi, documentazione
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: c1732dc17188427f9a181d1c47abe71bb8f39584
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841412"
---
#  <a name="prepare-on-premises-resources-access-for-microsoft-managed-desktop"></a>Preparare l'accesso alle risorse locali per Microsoft Managed Desktop

In Microsoft Managed Desktop, i dispositivi vengono automaticamente aggiunti a Azure Active Directory (Azure AD). Per questo motivo, se si utilizza Active Directory locale, è necessario verificare alcuni elementi per garantire che i dispositivi aggiunti a Azure AD possano comunicare con Active Directory locale. 

> [!NOTE]  
> Ambiente *ibrido* Azure AD join non è supportato da Microsoft Managed Desktop.

Azure Active Directory consente agli utenti di usufruire di single Sign-On (SSO), il che significa che in genere non dovranno fornire le credenziali ogni volta che utilizzano le risorse.

Per informazioni sull'aggiunta di Azure Active Directory, fare riferimento a [procedura: pianificare l'implementazione del join di Azure ad](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan). Per informazioni di base sulle singole Sign-On (SSO) sui dispositivi associati ad Azure AD, vedere [How SSO to on-premises Resources on Azure ad joind Devices](https://docs.microsoft.com/azure/active-directory/devices/azuread-join-sso#how-it-works).


In questo articolo vengono illustrate le operazioni che è necessario controllare per garantire che le app e le altre risorse che dipendono dalla connettività di Active Directory locale funzionino correttamente con Microsoft Managed Desktop.


## <a name="single-sign-on-for-on-premises-resources"></a>Sign-On singoli per le risorse locali

Single Sign-On (SSO) tramite UPN e password è abilitata per impostazione predefinita sui dispositivi Microsoft Managed Desktop. Tuttavia, gli utenti possono anche utilizzare Windows Hello for business, che richiede alcuni passaggi di installazione aggiuntivi. 

### <a name="single-sign-on-by-using-upn-and-password"></a>Sign-On singola tramite UPN e password

Nella maggior parte delle organizzazioni, gli utenti saranno in grado di utilizzare SSO per l'autenticazione tramite UPN e la password sui dispositivi Microsoft Managed Desktop. Tuttavia, per assicurarsi che questa funzione funzioni, è necessario controllare le seguenti operazioni:

- Verificare che Azure AD Connect sia configurato e utilizzi un server Active Directory locale che esegue Windows Server 2008 R2 o versione successiva.
- Verificare che Azure AD Connect esegua una versione supportata ed è impostato per sincronizzare questi tre attributi con Azure AD: 
    - Nome di dominio DNS dell'Active Directory locale (in cui si trovano gli utenti)
    - NetBIOS dell'Active Directory locale (in cui si trovano gli utenti)
    - Nome account SAM dell'utente


### <a name="single-sign-on-by-using-windows-hello-for-business"></a>Sign-On singolo tramite Windows Hello for business

I dispositivi Microsoft Managed Desktop offrono agli utenti un'esperienza veloce e con password utilizzando Windows Hello for business. Per garantire che Windows Hello for Business funzioni senza che gli utenti debbano fornire la propria UPN e la relativa password, visitare [Configure Azure ad joined devices for on-premises Single-Sign using Windows Hello for business](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base) per controllare i requisiti e quindi seguire i passaggi disponibili.


## <a name="apps-and-resources-that-use-authentication"></a>App e risorse che utilizzano l'autenticazione

Fare riferimento a comprendere le considerazioni relative alle [applicazioni e alle risorse](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#understand-considerations-for-applications-and-resources) del set di contenuti di Azure per informazioni complete sulla configurazione delle app per l'utilizzo con Azure Active Directory. In sintesi:


- Se si utilizzano **app basate su cloud**, ad esempio quelle aggiunte alla raccolta delle app di Azure ad, la maggior parte non richiede alcuna ulteriore preparazione per l'utilizzo con Microsoft Managed Desktop. Tuttavia, qualsiasi applicazione Win32 che non utilizza Web Account Manager (WAM) potrebbe comunque richiedere agli utenti di eseguire l'autenticazione.

- Per le app **ospitate in locale**, accertarsi di aggiungere tali app all'elenco dei siti attendibili nei browser. Questo passaggio consentirà l'autenticazione di Windows in modo che funzioni perfettamente, senza che gli utenti vengano richieste le credenziali. Per aggiungere app, fare riferimento a [siti attendibili](https://docs.microsoft.com/microsoft-365/managed-desktop/working-with-managed-desktop/config-setting-ref#trusted-sites) nella Guida di [riferimento alle impostazioni configurabili](https://docs.microsoft.com/microsoft-365/managed-desktop/working-with-managed-desktop/config-setting-ref).

- Se si utilizzano i servizi federati di Active Directory, verificare che SSO sia abilitato utilizzando la procedura descritta in [Verify and Manage Single Sign-on with ad FS](https://docs.microsoft.com/previous-versions/azure/azure-services/jj151809(v=azure.100)). 

- Per le app che sono **in locale e utilizzano protocolli meno recenti**, non è necessaria alcuna configurazione aggiuntiva, purché i dispositivi abbiano accesso a un controller di dominio locale per l'autenticazione. Per fornire l'accesso sicuro per queste applicazioni, è tuttavia necessario distribuire il proxy di applicazione Azure AD. Per ulteriori informazioni, vedere [Remote Access to on-premises Applications through Azure Active Directory ' s application proxy](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy).

- Le app che vengono eseguite **in locale e si basano sull'autenticazione del computer** non sono supportate, pertanto è consigliabile prendere in considerazione la possibilità di sostituirle con versioni più recenti.

### <a name="network-shares-that-use-authentication"></a>Condivisioni di rete che utilizzano l'autenticazione

Non è necessaria alcuna configurazione aggiuntiva per consentire agli utenti di accedere alle condivisioni di rete, purché i dispositivi abbiano accesso a un controller di dominio locale utilizzando un percorso UNC.

### <a name="printers"></a>Stampanti

I dispositivi Microsoft Managed Desktop non sono in grado di connettersi a stampanti pubblicate in Active Directory locale, a meno che non sia stata configurata la [stampa ibrida del cloud](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy).

Anche se le stampanti non possono essere scoperte automaticamente in un ambiente solo cloud, gli utenti possono utilizzare le stampanti locali utilizzando il percorso della stampante o il percorso della coda della stampante, purché i dispositivi abbiano accesso a un controller di dominio locale.

<!--add fuller material on printers when available-->
