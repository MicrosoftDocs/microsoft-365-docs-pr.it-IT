---
title: Abilitare i dispositivi Windows 10 associati a un dominio per essere gestiti da Microsoft 365 business
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
ms.custom: OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: 9b4de218-f1ad-41fa-a61b-e9e8ac0cf993
description: Informazioni su come consentire a Microsoft 365 di proteggere gli annunci locali con i dispositivi Windows 10.
ms.openlocfilehash: d1dbfc6a35d54db653ae0f911fad05ac2ce0a993
ms.sourcegitcommit: 6003d6da0a85c97357eb3dba3918eb145f381fe1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/27/2019
ms.locfileid: "37288036"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business"></a>Abilitare i dispositivi Windows 10 associati a un dominio per essere gestiti da Microsoft 365 business

Se l'organizzazione utilizza Windows Server Active Directory in locale, è possibile configurare Microsoft 365 business per proteggere i dispositivi Windows 10, mantenendo comunque l'accesso alle risorse locali che richiedono l'autenticazione locale.
Per configurarlo, è possibile implementare i **dispositivi ibridi di Azure ad Uniti**. Si tratta di dispositivi che si uniscono sia a Active Directory locale che a Azure Active Directory.

Nei video seguenti vengono illustrati i passaggi per la configurazione di questa procedura per lo scenario più comune, che è anche dettagliato nei passaggi seguenti.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  

## <a name="1-prepare-for-directory-synchronization"></a>1. preparare la sincronizzazione della directory 

Prima di sincronizzare gli utenti e i computer dal dominio Active Directory locale, esaminare [prepararsi per la sincronizzazione della directory in Office 365](https://docs.microsoft.com/office365/enterprise/prepare-for-directory-synchronization). In particolare:

   - Verificare che nella directory non siano presenti duplicati per gli attributi seguenti: **mail**, **proxyAddresses**e **userPrincipalName**. Questi valori devono essere univoci e tutti i duplicati devono essere rimossi.
   
   - È consigliabile che l'attributo **userPrincipalName** (UPN) per ogni account utente locale sia configurato in modo che corrisponda all'indirizzo di posta elettronica principale corrispondente all'utente con licenza Microsoft 365. Ad esempio, *Mary. Shelley<span>@ Contoso<span> . com* anziché *Mary @ contoso. local*
   
   - Se il dominio Active Directory termina con un suffisso non instradabile come *. local* o *. LAN*, invece di un suffisso instradabile su Internet, ad esempio *. com* o *. org*, sarà necessario modificare prima il suffisso UPN degli account utente locali come descritto in [Preparare un dominio non instradabile per la sincronizzazione della directory](https://docs.microsoft.com/office365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization). 

## <a name="2-install-and-configure-azure-ad-connect"></a>2. installare e configurare Azure AD Connect

Per sincronizzare gli utenti, i gruppi e i contatti da Active Directory locale ad Azure Active Directory, installare Azure Active Directory Connect e configurare la sincronizzazione della directory. Per ulteriori informazioni, vedere [configurare la sincronizzazione della directory per Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846) .

> [!NOTE]
> I passaggi sono esattamente gli stessi per Microsoft 365 business. 

Quando si configurano le opzioni per Azure AD Connect, è consigliabile abilitare la **sincronizzazione delle password** e l' **accesso Single Sign-on senza**problemi, nonché la funzionalità **writeback delle password** , supportata anche in Microsoft 365 business.

> [!NOTE]
> Sono disponibili ulteriori passaggi per il writeback delle password oltre la casella di controllo in Azure AD Connect. Per ulteriori informazioni, vedere [How-to: Configure password writeback](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback). 

## <a name="3-configure-hybrid-azure-ad-join"></a>3. configurare la join ibrido di Azure AD

Prima di abilitare i dispositivi Windows 10 a essere Uniti ad Azure ibrido, è necessario verificare che vengano soddisfatti i prerequisiti seguenti:

   - Si sta eseguendo la versione più recente di Azure AD Connect.

   - Azure AD Connect ha sincronizzato tutti gli oggetti computer dei dispositivi in cui si desidera essere Uniti AD Azure ibrido. Se gli oggetti computer appartengono a specifiche unità organizzative (OU), assicurarsi che le unità organizzative siano impostate per la sincronizzazione anche in Azure AD Connect.

Per registrare i dispositivi Windows 10 aggiunti a un dominio come ibridi di Azure AD Uniti, seguire la procedura illustrata nell' [esercitazione: Configure Hybrid Azure Active Directory join for Managed](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join)Domains. Ciò consentirà agli ibridi di attivare Active Directory locale con Windows 10 e renderli pronti per il cloud.
    
## <a name="4-enable-automatic-enrollment-for-windows-10"></a>4. abilitare la registrazione automatica per Windows 10

 Per registrare automaticamente i dispositivi Windows 10 per la gestione dei dispositivi mobili in Intune, vedere [registrazione di un dispositivo Windows 10 automaticamente tramite criteri di gruppo](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy). È possibile impostare criteri di gruppo a livello di computer locale o per operazioni in blocco, è possibile creare questa impostazione di criteri di gruppo nel controller di dominio utilizzando la console Gestione criteri di gruppo e i modelli ADMX.

## <a name="5-configure-seamless-single-sign-on"></a>5. configurare l'accesso Single Sign-on senza problemi

  SSO senza soluzione di continuità firmerà automaticamente gli utenti nelle proprie risorse cloud di Microsoft 365 quando utilizzeranno computer aziendali. È sufficiente distribuire una delle due opzioni di criteri di gruppo descritte in [Azure Active Directory Single Sign-on senza problemi: avvio veloce](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sso-quick-start#step-2-enable-the-feature). L'opzione **criteri di gruppo** non consente agli utenti di modificare le relative impostazioni, mentre l'opzione **preferenza criteri di gruppo** consente di impostare i valori, ma anche di lasciarli configurabili dall'utente.

## <a name="6-set-up-windows-hello-for-business"></a>6. configurare Windows Hello for business

 Windows Hello for business sostituisce le password con una forte autenticazione a due fattori (2FA) per l'accesso a un computer locale. Un fattore è una coppia di chiavi asimmetriche e l'altro è un PIN o un altro gesto locale, ad esempio l'impronta digitale o il riconoscimento facciale, se il dispositivo lo supporta. Si consiglia di sostituire le password con 2FA e Windows Hello for business laddove possibile.

Per configurare le finestre ibride Hello for business, vedere i [prerequisiti di Windows Hello for business per le chiavi ibride](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-key-trust-prereqs). Seguire le istruzioni riportate in [Configure Hybrid Windows Hello for business Key Trust Settings](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-key-whfb-settings). 
