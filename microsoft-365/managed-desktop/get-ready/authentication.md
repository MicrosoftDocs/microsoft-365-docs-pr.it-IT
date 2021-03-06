---
title: Preparare l'accesso alle risorse locali per Microsoft Managed Desktop
description: Passaggi importanti per assicurarsi che Azure AD possa comunicare con AD locale per fornire l'autenticazione
keywords: Microsoft Managed Desktop, Microsoft 365, servizio, documentazione
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 6df23e0d7e3ea0ecd7ebacd96f00cb47b9e0aa84
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574596"
---
#  <a name="prepare-on-premises-resources-access-for-microsoft-managed-desktop"></a>Preparare l'accesso alle risorse locali per Microsoft Managed Desktop

In Microsoft Managed Desktop, i dispositivi vengono aggiunti automaticamente a Azure Active Directory (Azure AD). Per questo motivo, se si usa active Directory locale, è necessario verificare alcuni aspetti per assicurarsi che i dispositivi aggiunti ad Azure AD possano comunicare con Active Directory locale. 

> [!NOTE]  
> *Ibrido* L'aggiunta ad Azure AD non è supportata Microsoft Managed Desktop.

Azure Active Directory consente agli utenti di sfruttare single Sign-On (SSO), il che significa che in genere non sarà necessario fornire credenziali ogni volta che usano risorse.

Per informazioni sull'aggiunta Azure Active Directory, vedere [Procedura: Pianificare l'implementazione dell'aggiunta ad Azure AD.](/azure/active-directory/devices/azureadjoin-plan) Per informazioni di base su Single Sign-On (SSO) nei dispositivi aggiunti ad Azure AD, vedere Funzionamento del servizio SSO per le risorse locali nei dispositivi aggiunti [ad Azure AD.](/azure/active-directory/devices/azuread-join-sso#how-it-works)


In questo articolo vengono illustrati gli elementi da controllare per garantire che le app e altre risorse che dipendono dalla connettività di Active Directory locale funzionino senza problemi con Microsoft Managed Desktop.


## <a name="single-sign-on-for-on-premises-resources"></a>Single Sign-On per le risorse locali

Single Sign-On (SSO) tramite UPN e la password è abilitata per impostazione predefinita Microsoft Managed Desktop dispositivi. Tuttavia, gli utenti possono anche usare Windows Hello for Business, che richiede alcuni passaggi di configurazione aggiuntivi. 

### <a name="single-sign-on-by-using-upn-and-password"></a>Single Sign-On utilizzando UPN e password

Nella maggior parte delle organizzazioni, gli utenti potranno utilizzare SSO per l'autenticazione tramite UPN e password Microsoft Managed Desktop dispositivi. Tuttavia, per assicurarsi che questa funzione funzioni, è consigliabile controllare le operazioni seguenti:

- Verificare che Azure AD Connessione sia configurato e utilizzi un server Active Directory locale che esegue Windows Server 2008 R2 o versione successiva.
- Verificare che Azure AD Connessione sia in esecuzione una versione supportata ed è impostato per sincronizzare questi tre attributi con Azure AD: 
    - Nome di dominio DNS di Active Directory locale (in cui si trovano gli utenti)
    - NetBIOS di Active Directory locale (dove si trovano gli utenti)
    - Nome account SAM dell'utente


### <a name="single-sign-on-by-using-windows-hello-for-business"></a>Single Sign-On usando Windows Hello for Business

Microsoft Managed Desktop dispositivi offrono agli utenti un'esperienza veloce e senza password utilizzando Windows Hello for Business. Per assicurarsi che Windows Hello for Business funzioni senza che gli utenti devono fornire upn e password corrispondenti, visitare Configurare i dispositivi aggiunti ad Azure AD per Single-Sign Locale Su [usando Windows Hello for Business](/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base) per verificare i requisiti e quindi seguire i passaggi indicati.


## <a name="apps-and-resources-that-use-authentication"></a>App e risorse che usano l'autenticazione

Fare riferimento [a Informazioni sulle considerazioni per le](/azure/active-directory/devices/azureadjoin-plan#understand-considerations-for-applications-and-resources) applicazioni e le risorse nel set di contenuti di Azure per istruzioni complete sulla configurazione delle app per l'utilizzo Azure Active Directory. Riepilogo:


- Se usi app basate sul **cloud,** ad esempio quelle aggiunte alla raccolta app di Azure AD, la maggior parte non richiede ulteriori operazioni di preparazione per lavorare con Microsoft Managed Desktop. Tuttavia, qualsiasi app Win32 che non usa Web Account Manager (WAM) potrebbe comunque richiedere l'autenticazione agli utenti.

- Per le app **ospitate in** locale, assicurati di aggiungere tali app all'elenco dei siti attendibili nei browser. Questo passaggio consentirà Windows'autenticazione senza problemi, senza che agli utenti vengano richieste le credenziali. Per aggiungere app, fare riferimento a [Siti attendibili](../working-with-managed-desktop/config-setting-ref.md#trusted-sites) nel riferimento [Impostazioni configurabili.](../working-with-managed-desktop/config-setting-ref.md)

- Se si utilizza Active Directory Federated Services, verificare che il servizio SSO sia abilitato utilizzando la procedura descritta in Verificare e gestire l'accesso [Single #A0 con AD FS.](/previous-versions/azure/azure-services/jj151809(v=azure.100)) 

- Per le app locali e che usano protocolli **precedenti,** non è necessaria alcuna configurazione aggiuntiva, purché i dispositivi hanno accesso a un controller di dominio locale per l'autenticazione. Per fornire l'accesso sicuro per queste applicazioni, tuttavia, è consigliabile distribuire il proxy dell'applicazione Azure AD. Per ulteriori informazioni, vedere [Remote access to on-premises applications through Azure Active Directory's Application Proxy](/azure/active-directory/manage-apps/application-proxy).

- Le app eseguite **in locale e** che si basano sull'autenticazione del computer non sono supportate, pertanto è consigliabile sostituirle con versioni più recenti.

### <a name="network-shares-that-use-authentication"></a>Condivisioni di rete che utilizzano l'autenticazione

Non è necessaria alcuna configurazione aggiuntiva per consentire agli utenti di accedere alle condivisioni di rete, purché i dispositivi hanno accesso a un controller di dominio locale utilizzando un percorso UNC.

### <a name="printers"></a>Stampanti

Microsoft Managed Desktop dispositivi non possono connettersi alle stampanti pubblicate in Active Directory locale a meno che non sia stato configurato [Hybrid Cloud Print.](/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy)

Anche se le stampanti non possono essere individuate automaticamente in un ambiente solo cloud, gli utenti possono utilizzare le stampanti locali utilizzando il percorso della stampante o il percorso della coda della stampante, purché i dispositivi possano accedere a un controller di dominio locale.

<!--add fuller material on printers when available-->
## <a name="steps-to-get-ready"></a>Passaggi per prepararsi

1. Esaminare [i prerequisiti per Microsoft Managed Desktop](prerequisites.md).
2. Utilizzare [gli strumenti di valutazione della conformità](readiness-assessment-tool.md).
3. [Prerequisiti per gli account Guest](guest-accounts.md)
4. [Configurazione rete in Microsoft Managed Desktop](network.md)
5. [Preparare certificati e profili di rete per Microsoft Managed Desktop](certs-wifi-lan.md)
6. [Preparare l'accesso alle risorse](authentication.md) locali per Microsoft Managed Desktop (questo articolo)
7. [App in Microsoft Managed Desktop](apps.md)
8. [Preparare unità mappate per Microsoft Managed Desktop](mapped-drives.md)
9. [Preparare risorse di stampa per Microsoft Managed Desktop](printing.md)
