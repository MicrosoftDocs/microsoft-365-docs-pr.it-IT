---
title: Accesso locale risorse da un dispositivo Azure Active Directory aggiunti in Microsoft 365 Business
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: b0f4d010-9fd1-44d0-9d20-fabad2cdbab5
description: Informazioni su come accedere a risorse locali come in applicazioni Line-Of-Business, condivisioni file e stampanti da un Azure Active Directory appartenente dispositivo Windows 10.
ms.openlocfilehash: 0a5d4b0828888fcb99676223000c446479f84ddc
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2019
ms.locfileid: "26868306"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business"></a>Accesso locale risorse da un dispositivo Azure Active Directory aggiunti in Microsoft 365 Business

Eventuali dispositivi 10 Windows Azure Active Directory appartenente potranno accedere a tutte le risorse basate su cloud, ad esempio le applicazioni di Office 365 e possono essere protetti da Microsoft 365 Business. Per consentire l'accesso alle risorse locali come applicazioni Line Of Business (LOB), condivisioni file e stampanti anche, è necessario sincronizzare Active Directory locale con Azure Active Directory utilizzando [Connetti Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect). [Introduzione alla gestione dei dispositivi in Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/device-management-introduction) per ulteriori informazioni, vedere. 
  
## <a name="run-azure-ad-connect"></a>Connettere Esegui Azure Active Directory

Completare la procedura seguente per consentire ai dispositivi dell'organizzazione Azure Active Directory appartenente accedere alle risorse locali.
  
1. Per sincronizzare gli utenti, gruppi e contatti da Active Directory locale in Azure Active Directory, eseguire la procedura guidata sincronizzazione della Directory e Azure Active Directory Connetti come descritto in [configurare la sincronizzazione delle directory per Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).
    
2. Dopo aver completato la sincronizzazione della directory, verificare che i dispositivi dell'organizzazione Windows 10 siano Azure Active Directory aggiunti. Questo passaggio viene eseguito singolarmente ogni dispositivo Windows 10. Per informazioni dettagliate, vedere [configurare i dispositivi di Windows per utenti Business 365 Microsoft](set-up-windows-devices.md) . 
    
3. Dopo aver installato i dispositivi 10 Windows Azure Active Directory appartenente, ogni utente deve riavviare i dispositivi e account di accesso con le proprie credenziali aziendali 365 Microsoft. Tutti i dispositivi verranno concesso l'accesso alle risorse locali anche.
    
Nessun passaggi aggiuntivi sono necessari per accedere alle risorse per Azure Active Directory appartenente dispositivi in locale. Questo è disponibile in Windows 10 funzionalità incorporate. 
  
Se l'organizzazione non è possibile distribuire in Azure Active Directory appartenente dispositivo configurazione descritta in precedenza, è consigliabile configurare [Configurazione dispositivo ibrida Azure Active Directory Joined](manage-windows-devices.md).
  
### <a name="considerations-when-joining-your-windows-devices-to-azure-ad"></a>Considerazioni per la partecipazione i dispositivi di Windows per Azure Active Directory

In caso di Azure AD accesso a un dispositivo Windows che in precedenza è stato aggiunto al dominio o un gruppo di lavoro, è necessario prendere in considerazione le limitazioni seguenti:
  
- Quando si unisce a un dispositivo di Azure Active Directory, viene creato un nuovo utente senza fare riferimento a un profilo esistente. Per risolvere questo problema, è necessario eseguire manualmente la migrazione profili. Un profilo utente contiene informazioni come Preferiti, file locali, le impostazioni del browser, le impostazioni del menu di avvio e così via. È un approccio più adatto per individuare uno strumento di terze parti per mappare i file esistenti e le impostazioni per il nuovo profilo
    
- Se il dispositivo utilizza gli oggetti Criteri di gruppo (GPO), alcuni oggetti Criteri di gruppo che non sia un paragonabili [Provider di servizi di configurazione](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) Intune. Eseguire lo [strumento MMAT](https://www.microsoft.com/download/details.aspx?id=45520) per individuare CSP paragonabili di oggetti Criteri di gruppo esistenti. 
    
- Gli utenti non saranno in grado di eseguire l'autenticazione per le applicazioni che dipendono da autenticazione di Active Directory. Per gestire questo valutare utilizzando un'app legacy e prendere in considerazione l'aggiornamento a un'applicazione che utilizza autenticazione moderno se possibile.
    
- Rilevamento della stampante di Active Directory non funzionerà. Per risolvere questo problema, inserire percorsi di stampante diretto per tutti gli utenti o sfruttare [Ibrida Cloud stampa](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy).
    

