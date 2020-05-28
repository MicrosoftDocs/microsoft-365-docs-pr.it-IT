---
title: Consenti la gestione di dispositivi Windows 10 con dominio per essere gestiti da Microsoft 365 for business
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 9b4de218-f1ad-41fa-a61b-e9e8ac0cf993
description: Informazioni su come consentire a Microsoft 365 di proteggere i dispositivi Windows 10 locali con l'aggiunta di Active Directory in pochi passaggi.
ms.openlocfilehash: e7f83e620fbb43a478dba98f78d5f471a541aea7
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "44403059"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-for-business"></a>Consenti la gestione di dispositivi Windows 10 con dominio per essere gestiti da Microsoft 365 for business

Se l'organizzazione utilizza Windows Server Active Directory in locale, è possibile configurare Microsoft 365 for business in modo da proteggere i dispositivi Windows 10, mantenendo comunque l'accesso alle risorse locali che richiedono l'autenticazione locale.
Per impostare questa protezione, è possibile implementare i **dispositivi ibridi di Azure ad Uniti**. Questi dispositivi sono associati sia a Active Directory locale che a Azure Active Directory.

In questo video vengono illustrati i passaggi da eseguire per la configurazione dello scenario più comune, che è anche dettagliato nei passaggi successivi.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  

## <a name="1-prepare-for-directory-synchronization"></a>1. preparare la sincronizzazione della directory 

Prima di sincronizzare gli utenti e i computer dal dominio Active Directory locale, esaminare [prepararsi per la sincronizzazione della directory in Office 365](https://docs.microsoft.com/office365/enterprise/prepare-for-directory-synchronization). In particolare:

   - Verificare che nella directory non siano presenti duplicati per gli attributi seguenti: **mail**, **proxyAddresses**e **userPrincipalName**. Questi valori devono essere univoci e tutti i duplicati devono essere rimossi.
   
   - Si consiglia di configurare l'attributo **userPrincipalName** (UPN) per ogni account utente locale in modo che corrisponda all'indirizzo di posta elettronica principale corrispondente all'utente con licenza Microsoft 365. Ad esempio: *Mary.Shelley@contoso.com* anziché *Mary@contoso. local*
   
   - Se il dominio Active Directory termina con un suffisso non instradabile come *. local* o *. LAN*, invece di un suffisso instradabile su Internet, ad esempio *. com* o *. org*, modificare il suffisso UPN degli account utente locali come descritto in [preparare un dominio non instradabile per la sincronizzazione della directory](https://docs.microsoft.com/office365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization). 

## <a name="2-install-and-configure-azure-ad-connect"></a>2. installare e configurare Azure AD Connect

Per sincronizzare gli utenti, i gruppi e i contatti da Active Directory locale ad Azure Active Directory, installare Azure Active Directory Connect e configurare la sincronizzazione della directory. Per ulteriori informazioni, vedere [configurare la sincronizzazione della directory per Office 365](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization) .

> [!NOTE]
> I passaggi sono esattamente gli stessi per Microsoft 365 for business. 

Quando si configurano le opzioni per Azure AD Connect, è consigliabile abilitare la **sincronizzazione delle password**, l' **accesso Single Sign-on senza**problemi e la funzionalità writeback delle **password** , supportata anche in Microsoft 365 for business.

> [!NOTE]
> Sono disponibili ulteriori passaggi per il writeback delle password oltre la casella di controllo in Azure AD Connect. Per ulteriori informazioni, vedere [How-to: Configure password writeback](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback). 

## <a name="3-configure-hybrid-azure-ad-join"></a>3. configurare la join ibrido di Azure AD

Prima di abilitare i dispositivi Windows 10 a essere Uniti ad Azure ibrido, verificare che siano soddisfatti i prerequisiti seguenti:

   - Si sta eseguendo la versione più recente di Azure AD Connect.

   - Azure AD Connect ha sincronizzato tutti gli oggetti computer dei dispositivi in cui si desidera essere Uniti AD Azure ibrido. Se gli oggetti computer appartengono a specifiche unità organizzative (OU), assicurarsi che le unità organizzative siano impostate per la sincronizzazione anche in Azure AD Connect.

Per registrare i dispositivi Windows 10 aggiunti a un dominio come ibridi di Azure AD Uniti, seguire la procedura illustrata nell' [esercitazione: Configure Hybrid Azure Active Directory join for Managed](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join)Domains. Questo ibrido consente di abilitare Active Directory locale esistente in computer Windows 10 e renderli pronti per il cloud.
    
## <a name="4-enable-automatic-enrollment-for-windows-10"></a>4. abilitare la registrazione automatica per Windows 10

 Per registrare automaticamente i dispositivi Windows 10 per la gestione dei dispositivi mobili in Intune, vedere [registrazione di un dispositivo Windows 10 automaticamente tramite criteri di gruppo](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy). È possibile impostare criteri di gruppo a livello di computer locale o per operazioni in blocco, è possibile utilizzare la console Gestione criteri di gruppo e i modelli ADMX per creare questa impostazione di criteri di gruppo nel controller di dominio.

## <a name="5-configure-seamless-single-sign-on"></a>5. configurare l'accesso Single Sign-on senza problemi

  SSO senza soluzione di continuità firma automaticamente gli utenti nelle risorse cloud di Microsoft 365 quando utilizzano i computer aziendali. È sufficiente distribuire una delle due opzioni di criteri di gruppo descritte in [Azure Active Directory Single Sign-on senza problemi: avvio veloce](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sso-quick-start#step-2-enable-the-feature). L'opzione **criteri di gruppo** non consente agli utenti di modificare le relative impostazioni, mentre l'opzione **preferenza criteri di gruppo** consente di impostare i valori, ma anche di lasciarli configurabili dall'utente.

## <a name="6-set-up-windows-hello-for-business"></a>6. configurare Windows Hello for business

 Windows Hello for business sostituisce le password con una forte autenticazione a due fattori (2FA) per l'accesso a un computer locale. Un fattore è una coppia di chiavi asimmetriche e l'altro è un PIN o un altro gesto locale, ad esempio l'impronta digitale o il riconoscimento facciale, se il dispositivo lo supporta. Se possibile, è consigliabile sostituire le password con 2FA e Windows Hello for business.

Per configurare le finestre ibride Hello for business, vedere i [prerequisiti di Windows Hello for business per le chiavi ibride](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-key-trust-prereqs). Seguire le istruzioni riportate in [Configure Hybrid Windows Hello for business Key Trust Settings](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-key-whfb-settings). 
