---
title: Abilitare i dispositivi Windows 10 associati a un dominio per essere gestiti da Microsoft 365 business
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
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
search.appverid:
- BCS160
- MET150
ms.assetid: 9b4de218-f1ad-41fa-a61b-e9e8ac0cf993
description: Informazioni su come consentire a Microsoft 365 di proteggere gli annunci locali con i dispositivi Windows 10.
ms.openlocfilehash: d61b3bf6be50d6b21e7b883774567bb63995e60e
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32278078"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business"></a>Abilitare i dispositivi Windows 10 associati a un dominio per essere gestiti da Microsoft 365 business

Se l'organizzazione utilizza Windows Server Active Directory in locale, è possibile configurare Microsoft 365 business per proteggere i dispositivi Windows 10, mantenendo comunque l'accesso alle risorse locali che richiedono l'autenticazione locale. È possibile configurarlo eseguendo prima la sincronizzazione di Active Directory con Azure Active Directory, seguito dalla registrazione dei dispositivi Windows 10 con Azure AD e dall'iscrizione per la gestione dei dispositivi mobili da parte di Microsoft 365 business.
  
## <a name="set-up-domain-joined-devices-to-be-managed-by-microsoft-365-business"></a>Configurare i dispositivi associati a un dominio per essere gestiti da Microsoft 365 business

Per configurare i dispositivi appartenenti al dominio dell'organizzazione in modo da trarre vantaggio dalle funzionalità fornite da Azure Active Directory oltre che da Active Directory locale, è possibile implementare i **dispositivi ibridi di Azure ad Uniti**. Si tratta di dispositivi che si uniscono sia a Active Directory locale che a Azure Active Directory. I dispositivi ibridi di Azure AD Uniti possono essere protetti e gestiti da Microsoft 365 business. 
  
Completare i passaggi riportati di seguito per rendere i dispositivi Windows 10 ibridi di Azure AD Uniti e gestiti da Microsoft 365 business.
  
1. Per sincronizzare gli utenti, i gruppi e i contatti da Active Directory locale ad Azure Active Directory, eseguire la procedura guidata di sincronizzazione della directory e Azure Active Directory Connect come descritto in [configurare la sincronizzazione della directory per Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).
    
    > [!NOTE]
    > I passaggi sono esattamente gli stessi per Microsoft 365 business. 
  
2. Prima di completare il passaggio 3 per consentire ai dispositivi Windows 10 di essere Uniti ad Azure ibrido, è necessario verificare che siano soddisfatti i prerequisiti seguenti:
    
   - Si sta eseguendo la versione più recente di Azure AD Connect.
    
   - Azure AD Connect ha sincronizzato tutti gli oggetti computer dei dispositivi in cui si desidera essere Uniti AD Azure ibrido. Se gli oggetti computer appartengono a specifiche unità organizzative (OU), assicurarsi che le unità organizzative siano impostate per la sincronizzazione anche in Azure AD Connect.
    
3. Registrare i dispositivi Windows 10 aggiunti a un dominio esistenti per essere ibridi di Azure AD e iscriverli per la gestione dei dispositivi mobili da Intune (Microsoft 365 business):
    
4. Seguire le istruzioni dettagliate su [come configurare i dispositivi Uniti ibridi di Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=872870). In questo modo, la sincronizzazione di Active Directory locale è stata aggiunta ai computer Windows 10 e li rende pronti per il cloud.
    
5. Per registrare un dispositivo Windows 10 per la gestione dei dispositivi mobili, vedere [registrazione di un dispositivo Windows 10 con Intune tramite criteri di gruppo](https://go.microsoft.com/fwlink/p/?linkid=872871) per le istruzioni. È possibile impostare criteri di gruppo a livello di computer locale o per le operazioni in blocco, è possibile creare questa impostazione di criteri di gruppo nel server del controller di dominio. 
    

