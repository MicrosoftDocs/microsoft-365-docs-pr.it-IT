---
title: Consentire ai dispositivi Windows 10 aggiunto al dominio da gestire da Microsoft 365 Business
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 9b4de218-f1ad-41fa-a61b-e9e8ac0cf993
description: Informazioni su come abilitare 365 Microsoft proteggere i dispositivi Windows 10 aggiunto al Active Directory locale.
ms.openlocfilehash: 6e66a2c5417c9037232c1ada654d4cac3c520607
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2019
ms.locfileid: "26868428"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business"></a>Consentire ai dispositivi Windows 10 aggiunto al dominio da gestire da Microsoft 365 Business

Se l'organizzazione utilizza Windows Server Active Directory locale, è possibile impostare Microsoft 365 Business per proteggere i dispositivi Windows 10, mantenendo l'accesso alle risorse locali che richiedono l'autenticazione locale. È possibile impostare questo grazie alla prima sincronizzazione di Active Directory con Azure Active Directory, seguita registrando i dispositivi Windows 10 con Azure Active Directory e li la registrazione per la gestione dei dispositivi mobili da Microsoft 365 Business.
  
## <a name="set-up-domain-joined-devices-to-be-managed-by-microsoft-365-business"></a>Configurare i dispositivi aggiunti al dominio da gestire da Microsoft 365 Business

Per impostare i dispositivi aggiunti al dominio dell'organizzazione per usufruire delle funzionalità fornite da Azure Active Directory oltre a Active Directory locale, è possibile implementare **ibrida Azure Active Directory appartenente dispositivi**. Si tratta di dispositivi che vengono aggiunti sia di Active Directory locale e Azure Active Directory. Ibrida Azure Active Directory appartenente dispositivi possono essere protetti e gestiti da Microsoft 365 Business.. 
  
Completare la procedura seguente per verificare i dispositivi di 10 Windows Azure Active Directory aggiunto e gestito da Microsoft 365 Business ibrida.
  
1. Per sincronizzare gli utenti, gruppi e contatti da Active Directory locale in Azure Active Directory, eseguire la procedura guidata di sincronizzazione della Directory e Azure Active Directory la connessione come descritto in [configurare la sincronizzazione delle directory per Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).
    
    > [!NOTE]
    > I passaggi sono esattamente gli stessi per Microsoft 365 Business. 
  
2. Prima di completare il passaggio 3 per consentire ai dispositivi Windows 10 da ibrida Azure Active Directory aggiunti, è necessario assicurarsi che siano soddisfatti i prerequisiti seguenti:
    
   - Si esegue la versione più recente di Azure Active Directory la connessione.
    
   - La connessione di Azure Active Directory è sincronizzato tutti gli oggetti computer dei dispositivi che si desidera essere ibrida Azure Active Directory aggiunti. Connettere anche se gli oggetti computer appartengono a specifiche unità organizzative (OU), quindi verificare che siano impostate le unità organizzative per la sincronizzazione di Azure Active Directory.
    
3. Registrare dominio Windows 10 dispositivi esistenti per ibrida Joined Azure Active Directory e li registrare per la gestione dei dispositivi mobili da Intune (Microsoft Business 365):
    
4. Seguire le istruzioni dettagliate su [come configurare i dispositivi di Azure Active Directory appartenente ibrida](https://go.microsoft.com/fwlink/p/?linkid=872870). In questo modo la sincronizzazione di Active Directory locale aggiunto al computer Windows 10 e renderli cloud ready.
    
5. Per registrare un dispositivo Windows 10 per la gestione dei dispositivi mobili, vedere [registrazione un dispositivo Windows 10 con Intune utilizzando criteri di gruppo](https://go.microsoft.com/fwlink/p/?linkid=872871) per le istruzioni. È possibile impostare i criteri di gruppo in un computer locale livello o per le operazioni in blocco, è possibile creare questa impostazione di criteri di gruppo nel server di controller di dominio. 
    

