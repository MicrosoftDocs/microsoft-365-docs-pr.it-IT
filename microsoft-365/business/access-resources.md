---
title: Accedere alle risorse locali da un dispositivo di Azure AD-join in Microsoft 365 business
ms.author: sirkkuw
author: Sirkkuw
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
search.appverid:
- BCS160
- MET150
ms.assetid: b0f4d010-9fd1-44d0-9d20-fabad2cdbab5
description: Informazioni su come accedere alle risorse locali come le app di linea di business, le condivisioni di file e le stampanti di un dispositivo Windows 10 collegato a Azure Active Directory.
ms.openlocfilehash: fdc1eca6913ba6af4f6b65691fdee2165e7c827e
ms.sourcegitcommit: 8193b7da5b1a415835d02ca96883c351df7326ed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/14/2019
ms.locfileid: "38323396"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business"></a>Accedere alle risorse locali da un dispositivo di Azure AD-join in Microsoft 365 business

Qualsiasi dispositivo Windows 10 che è Azure Active Directory joined ha accesso a tutte le risorse basate su cloud, ad esempio le app di Office 365, e può essere protetto da Microsoft 365 business. È inoltre possibile consentire l'accesso a risorse locali come le app line-of-business (LOB), le condivisioni di file e le stampanti. Per consentire l'accesso, utilizzare [Azure ad Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) per sincronizzare Active Directory locale con Azure Active Directory. 

Per ulteriori informazioni, vedere [Introduzione alla gestione dei dispositivi in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/device-management-introduction).
I passaggi vengono riepilogati anche nelle sezioni seguenti.

## <a name="run-azure-ad-connect"></a>Eseguire Azure AD Connect

Completare i passaggi seguenti per consentire ai dispositivi di Azure AD Uniti dell'organizzazione di accedere alle risorse locali.
  
1. Per sincronizzare gli utenti, i gruppi e i contatti da Active Directory locale ad Azure Active Directory, eseguire la procedura guidata per la sincronizzazione della directory e Azure AD Connect come descritto in [set up Directory Synchronization for Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).
    
2. Dopo aver completato la sincronizzazione della directory, verificare che i dispositivi Windows 10 dell'organizzazione siano Uniti AD Azure AD. Questo passaggio viene effettuato singolarmente in ogni dispositivo Windows 10. Per informazioni dettagliate, vedere [configurare i dispositivi Windows per gli utenti aziendali di Microsoft 365](set-up-windows-devices.md) . 
    
3. Dopo che i dispositivi Windows 10 sono Stati Uniti AD Azure AD, ogni utente deve riavviare i propri dispositivi e accedere con le proprie credenziali di Microsoft 365 business. Tutti i dispositivi ora hanno accesso alle risorse locali.
    
Non è necessario eseguire ulteriori passaggi per accedere alle risorse locali per i dispositivi collegati a Azure AD. Questa funzionalità è incorporata in Windows 10. 
  
Se l'organizzazione non è pronta per la distribuzione nella configurazione del dispositivo di Azure AD join descritta in alto, valutare la possibilità di configurare la [configurazione del dispositivo ibrido di Azure ad aggiunto](manage-windows-devices.md).
  
### <a name="considerations-when-you-join-windows-devices-to-azure-ad"></a>Considerazioni su come unire i dispositivi Windows ad Azure AD

Se il dispositivo Windows a cui è stato aggiunto Azure-AD è stato precedentemente aggiunto a un dominio o in un gruppo di lavoro, tenere presente le limitazioni seguenti:
  
- Quando si aggiunge un dispositivo Azure AD, viene creato un nuovo utente senza fare riferimento a un profilo esistente. I profili devono essere migrati manualmente. Un profilo utente contiene informazioni quali Preferiti, file locali, impostazioni del browser e impostazioni del menu Start. L'approccio migliore consiste nel trovare uno strumento di terze parti per mappare i file e le impostazioni esistenti al nuovo profilo.

- Se il dispositivo utilizza oggetti Criteri di gruppo (GPO), alcuni GPO potrebbero non disporre di un [provider di servizi di configurazione](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) paragonabile in Intune. Eseguire lo [strumento MMAT](https://www.microsoft.com/download/details.aspx?id=45520) per trovare DSN confrontabili per gli oggetti Criteri di stato esistenti.

- Gli utenti non saranno in grado di eseguire l'autenticazione per le applicazioni che dipendono dalle autenticazioni di Active Directory. Valutare l'applicazione legacy e prendere in considerazione l'aggiornamento a un'app che utilizza l'autenticazione moderna, se possibile.

- L'individuazione della stampante di Active Directory non funzionerà. È possibile fornire percorsi Direct Printer per tutti gli utenti o utilizzare la [stampa cloud ibrida](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy).
