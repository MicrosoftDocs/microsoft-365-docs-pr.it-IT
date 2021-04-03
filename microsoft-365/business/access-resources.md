---
title: Accedere alle risorse locali da un dispositivo aggiunto ad Azure AD in Microsoft 365 Business
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.collection: M365-subscription-management
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: b0f4d010-9fd1-44d0-9d20-fabad2cdbab5
description: Informazioni su come accedere a risorse locali, come le app line-of-business, le condivisioni file e le stampanti, da un dispositivo Windows 10 aggiunto ad Azure Active Directory.
ms.openlocfilehash: 27549d6c3b03413f2f05c69845caad155333ca97
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580315"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business-premium"></a>Accedere alle risorse locali da un dispositivo aggiunto ad Azure AD in Microsoft 365 Business Premium

Questo articolo si applica a Microsoft 365 Business Premium.

Qualsiasi dispositivo Windows 10 aggiunto ad Azure Active Directory ha accesso a tutte le risorse basate sul cloud, ad esempio le app di Microsoft 365, e può essere protetto da Microsoft 365 Business Premium. È anche possibile consentire l'accesso a risorse locali come le app line-of-business (LOB), le condivisioni file e le stampanti. Per consentire l'accesso, utilizzare [Azure AD Connect](/azure/active-directory/connect/active-directory-aadconnect) per sincronizzare Active Directory locale con Azure Active Directory. 

Per altre informazioni, vedere [Introduzione alla gestione dei dispositivi in Azure Active Directory](/azure/active-directory/device-management-introduction).
Le procedure sono riepilogate anche nelle sezioni seguenti.
 
## <a name="run-azure-ad-connect"></a>Eseguire Azure AD Connect.

Completare la procedura seguente per consentire ai dispositivi dell'organizzazione aggiunti ad Azure AD di accedere alle risorse locali.
  
1. Per sincronizzare gli utenti, i gruppi e i contatti da Active Directory locale ad Azure Active Directory, eseguire la procedura guidata di sincronizzazione della directory e Azure AD Connect come descritto in [Configurare la sincronizzazione della directory per Office 365](../enterprise/set-up-directory-synchronization.md).
    
2. Una volta completata la sincronizzazione della directory, accertarsi che i dispositivi Windows 10 dell'organizzazione siano associati ad Azure AD. Questa fase viene eseguita singolarmente in ogni dispositivo con Windows 10. Per informazioni dettagliate, vedi Configurare i dispositivi Windows per gli utenti [di Microsoft 365 Business](set-up-windows-devices.md) Premium. 
    
3. Una volta aggiunti i dispositivi Windows 10 ad Azure AD, ogni utente deve riavviare i dispositivi e accedere con le credenziali di Microsoft 365 Business Premium. Tutti i dispositivi hanno ora accesso alle risorse locali.
    
Non ci sono ulteriori fasi per accedere alle risorse locali per i dispositivi aggiunti ad Azure AD. Questa funzionalità è integrata in Windows 10. 

Se si ha intenzione di eseguire l'accesso al dispositivo AADJ con un metodo diverso da quello con la password, come quello tramite PIN o credenziali biometriche WHFB, eseguire l'accesso e accedere alle risorse locali (condivisioni, stampanti e così via), seguire https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base
  
Se l'organizzazione non è pronta per la distribuzione nella configurazione di un dispositivo aggiunto ad Azure AD descritta in precedenza, è consigliabile impostare la [configurazione di un dispositivo aggiunto ad Azure AD ibrido](manage-windows-devices.md).
  
### <a name="considerations-when-you-join-windows-devices-to-azure-ad"></a>Considerazioni sull'aggiunta di un dispositivo Windows ad Azure AD

Se il dispositivo Windows aggiunto ad Azure AD è già stato associato al dominio o a un gruppo di lavoro, prendere in considerazione le limitazioni seguenti:
  
- Quando un dispositivo viene aggiunto ad Azure AD, viene creato un nuovo utente che non fa riferimento a un profilo esistente. I profili devono essere migrati manualmente. Un profilo utente include informazioni come preferiti, file locali, impostazioni del browser e impostazioni del menu Avvio. Il migliore approccio consiste nel trovare uno strumento di terze parti per eseguire il mapping dei file e delle impostazioni esistenti al nuovo profilo.

- Se il dispositivo utilizza Oggetti Criteri di gruppo (GPO), alcuni di questi potrebbero non avere un [provider di servizi di configurazione](/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) confrontabile in Intune. Eseguire lo [strumento MMAT](https://www.microsoft.com/download/details.aspx?id=45520) per trovare un CSP confrontabile per gli Oggetti Criteri di gruppo esistenti.

- Gli utenti potrebbero non essere in grado di eseguire l'autenticazione in applicazioni che dipendono dall'autenticazione di Active Directory. Valutare l'applicazione legacy e prendere in considerazione l'aggiornamento a un'applicazione che utilizzi l'autenticazione moderna, se possibile.

- L'individuazione della stampante Active Directory non funziona. È possibile fornire percorsi di stampa diretti per tutti gli utenti o utilizzare [Universal Print.](/universal-print/)

### <a name="related-articles"></a>Articoli correlati

[Prerequisiti per Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites)
