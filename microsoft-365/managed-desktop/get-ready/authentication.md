---
title: Preparare l'accesso alle risorse locali per Microsoft Managed Desktop
description: Passaggi importanti per assicurarsi che un annuncio di Azure sia in grado di comunicare con Active Directory locale per fornire l'autenticazione
keywords: Microsoft Managed Desktop, Microsoft 365, Service, documentazione
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 0f9cbe6712b8d16f435cfdf5fd84875656fa9c2e
ms.sourcegitcommit: ef589025820ddf6edb5f454826b1c12c9bcb8e49
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/11/2019
ms.locfileid: "31824466"
---
#  <a name="prepare-on-premises-resources-access-for-microsoft-managed-desktop"></a>Preparare l'accesso alle risorse locali per Microsoft Managed Desktop

In Microsoft Managed Desktop, i dispositivi vengono automaticamente aggiunti a Azure Active Directory. Questo significa che se si utilizza Active Directory locale, è necessario verificare alcuni elementi per garantire che i dispositivi aggiunti a Azure AD possano comunicare con Active Directory locale. 

> [!NOTE]  
> ** Ambiente ibrido Azure AD join non è supportato da Microsoft Managed Desktop.

Azure Active Directory consente agli utenti di utilizzare Single Sign-on (SSO), il che significa che in genere non è necessario fornire le credenziali ogni volta che si desidera eseguire un'operazione. Se si è completamente nuovi in Azure Active Directory, vedere [How to: Plan your Azure ad join implementation](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan)--tuttavia, quando si fa riferimento alla documentazione di Azure Active Directory, tenere presente che *Hybrid* Azure ad join non è supportato da Microsoft Desktop gestito.


In questo argomento vengono illustrate le operazioni che è necessario controllare per garantire che le app e altre risorse che dipendono dalla connettività di Active Directory locale funzionino agevolmente con Microsoft Managed Desktop.


> [!IMPORTANT]  
> Affinché gli utenti siano in grado di registrare i dispositivi in Azure Active Directory e di registrarsi in Intune (necessario per Microsoft Managed Desktop), seguire la procedura illustrata in [configurare le impostazioni del dispositivo](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#configure-your-device-settings) prima di continuare con il resto di questo argomento.


## <a name="single-sign-on-for-on-premises-resources"></a>Single Sign-on per le risorse locali

Il servizio Single Sign-on (SSO) per i dispositivi tramite UPN o password (il metodo predefinito) deve già funzionare per impostazione predefinita. Tuttavia, è anche possibile utilizzare Windows Hello for business, che richiede alcuni passaggi di installazione aggiuntivi. Per informazioni di base su SSO, vedere [How SSO to locali Resources Works on Azure ad joined Devices](https://docs.microsoft.com/azure/active-directory/devices/azuread-join-sso#how-it-works).


### <a name="single-sign-on-by-using-upn-and-passwords"></a>Accesso Single Sign-on tramite UPN e password

Non è necessaria alcuna configurazione speciale per consentire agli utenti di eseguire l'autenticazione tramite UPN e password, per impostazione predefinita da Azure. Tuttavia, per assicurarsi che questo funzionerà, è necessario eseguire due controlli:

- Verificare che Azure Active Directory (AAD) Connect sia configurato con un server Active Directory locale che esegue Windows Server 2008 R2 o versione successiva.
- AAD Connect è in esecuzione una versione supportata ed è impostato per sincronizzare questi tre attributi chiave con Azure AD: 
    - Nome di dominio DNS in cui l'utente è presente in Active Directory locale
    - Nome di dominio NetBIOS in cui l'utente è presente in Active Directory locale
    - Nome account SAM dell'utente


### <a name="sso-by-using-windows-hello-for-business"></a>SSO tramite Windows Hello for business

In alternativa, è possibile offrire agli utenti un'esperienza veloce e con password utilizzando Windows Hello for business. Per configurarlo, visitare [Configure Azure ad joined devices for on-premises Single-Sign on using Windows Hello for business](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base) per controllare i requisiti e quindi seguire i passaggi forniti qui.


## <a name="apps-and-resources-that-use-authentication"></a>App e risorse che utilizzano l'autenticazione

Fare riferimento a comprendere le considerazioni relative alle [applicazioni e alle risorse](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#understand-considerations-for-applications-and-resources) del set di contenuti di Azure per informazioni complete sulla configurazione delle app per l'utilizzo con Azure Active Directory. In sintesi:


- Se si utilizzano **app basate su cloud**, ad esempio quelle aggiunte alla raccolta delle app di Azure ad, la maggior parte non richiede alcuna ulteriore preparazione per l'utilizzo con Microsoft Managed Desktop. Tuttavia, qualsiasi applicazione Win32 che non utilizza Web Account Manager (WAM) {verifica questa sigla} potrebbe comunque richiedere agli utenti di eseguire l'autenticazione.

- Per le app ospitate in **locale**, accertarsi di aggiungere tali app all'elenco dei siti attendibili nei browser. Ciò consentirà l'autenticazione di Windows in modo che funzioni correttamente, senza che vengano richiesti gli utenti per le credenziali.

- Se si utilizzano i servizi federati di Active Directory, seguire i passaggi descritti in [Verify and Manage Single Sign-on with ad FS](https://docs.microsoft.com/previous-versions/azure/azure-services/jj151809(v=azure.100)). 

- Per le app che sono **in locale e utilizzano protocolli meno recenti**, non è necessaria alcuna configurazione aggiuntiva, purché i dispositivi abbiano accesso a un controller di dominio locale. Per fornire l'accesso sicuro per queste applicazioni, è tuttavia necessario distribuire il proxy di applicazione Azure AD. Per ulteriori informazioni, vedere [Remote Access to on-premises Applications through Azure Active Directory ' s application proxy](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy).

- Le app eseguite **in locale e si basano sull'autenticazione del computer** non sono supportate, pertanto è consigliabile prendere in considerazione la possibilità di sostituire queste con versioni più recenti.

## <a name="network-shares-that-use-authentication"></a>Condivisioni di rete che utilizzano l'autenticazione

Non è necessaria alcuna configurazione aggiuntiva per consentire agli utenti di accedere alle condivisioni di rete, purché i dispositivi abbiano accesso a un controller di dominio locale utilizzando un percorso UNC.

## <a name="printers"></a>Stampanti

Sebbene le stampanti non possano essere scoperte automaticamente in un ambiente solo cloud, gli utenti possono anche utilizzare il percorso UNC delle stampanti per aggiungerli direttamente.

<!--add fuller material on printers when available-->