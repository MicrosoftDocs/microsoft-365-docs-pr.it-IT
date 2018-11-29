---
title: Reimpostazione della password per l'ambiente di testing di Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/30/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- TLGS
- Ent_TLGs
ms.assetid: ''
description: "Riepilogo: informazioni sulla configurazione e sul test di reimpostazione della password per l'ambiente di testing di Microsoft 365."
ms.openlocfilehash: a90cb362a2831bf0bcf3fe05932e3a4345d52b2e
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868861"
---
# <a name="password-reset-for-your-microsoft-365-test-environment"></a>Reimpostazione della password per l'ambiente di testing di Microsoft 365

La reimpostazione della password self-service di Azure AD consente agli utenti di reimpostare o sbloccare le password o gli account. 

Questo articolo descrive come configurare e testare le reimpostazioni della password nell'ambiente di testing di Microsoft 365 in due fasi:

1.  Creare l'ambiente di testing dell'organizzazione simulata di Microsoft 365 con per la sincronizzazione hash delle password.
2.  Configurare e testare la reimpostazione della password per l'account utente 2.
    
![Guide del laboratorio di testing per il cloud Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Fare clic [qui](https://aka.ms/m365etlgstack) per consultare una mappa di tutti gli articoli relativi alla guida al lab test di Microsoft 365 Enterprise.
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Fase 1: configurare la sincronizzazione hash delle password per l'ambiente di testing di Microsoft 365

Seguire le istruzioni riportate in [sincronizzazione hash delle password per Microsoft 365](password-hash-sync-m365-ent-test-environment.md). Di seguito è riportata la configurazione risultante.
  
![L'organizzazione simulata con ambiente di testing per l'autenticazione pass-through](media/pass-through-auth-m365-ent-test-environment/Phase2.png)
  
Questa configurazione è costituita da: 
  
- Abbonamenti di valutazione o permanenti a Office 365 E5 ed EMS E5.
- Una intranet dell’organizzazione semplificata connessa a Internet e costituita dalle macchine virtuali DC1 APP1 e CLIENT1 in una sottorete di una rete virtuale Azure. 
- Azure AD Connect viene eseguito su APP1 per sincronizzare il dominio TESTLAB Windows Server AD per il tenant Azure AD degli abbonamenti a Office 365 ed EMS E5.

## <a name="phase-2-configure-and-test-password-reset"></a>Fase 2: configurare e testare la reimpostazione della password

In questa fase, è possibile configurare la reimpostazione della password nel tenant di Azure AD attraverso l'appartenenza a un gruppo e quindi verificarne il funzionamento.

Innanzitutto, abilitare la reimpostazione della password per gli account in un gruppo specifico di Azure AD.

1. Aprire [https://portal.azure.com](https://portal.azure.com) da un'istanza privata del browser, quindi accedere usando le credenziali dell'account di amministratore globale.
2. Nel portale di Azure fare clic su **Azure Active Directory > Gruppi > Nuovo gruppo**.
3. Impostare **Tipo di gruppo** su **Sicurezza**, **Nome del gruppo** su **Reimpostazione della password** e **Tipo di appartenenza** su **Assegnato**. Fare clic su **Crea**.
5. Fare clic sul gruppo **Reimpostazione della password** nell'elenco, quindi fare clic su **Membri**.
6. Fare clic su **Aggiungi membri**, su **Utente 2**, quindi su **Seleziona**. Chiudere le pagine **Reimpostazione della password** e **Gruppo**.
7. Nella pagina di Azure Active Directory, fare clic su **Reimpostazione della password**.
8. Dalla pagina **Proprietà**, sotto l'opzione **Reimpostazione password self-service abilitata**, scegliere **Selezionato**.
9. Da **Seleziona gruppo**, selezionare **Reimpostazione della password**, quindi fare clic su **Salva**.
10. Chiudere l'istanza privata del browser.

Successivamente, testare la reimpostazione della password per l'account utente 2.

1. Aprire una nuova istanza privata del browser e passare alla pagina [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup).
2. Accedere con le credenziali dell'account utente 2.
3. In **Mantenere l'accesso all'account **, inserire il proprio numero di telefono cellulare e l'account di posta elettronica personale o aziendale per l'autenticazione.
4. Dopo che sono stati verificati entrambi, fare clic su **Approvato** e chiudere l'istanza privata del browser.
5. Aprire una nuova istanza del browser privata e accedere a [https://aka.ms/sspr](https://aka.ms/sspr).
6. Accedere con le credenziali dell'account utente 2, digitare i caratteri del CAPTCHA e quindi fare clic su **Avanti**.
8. Come **primo passaggio di verifica**, fare clic su **Inviare un messaggio all'indirizzo di posta elettronica alternativo**, quindi fare clic su **Posta elettronica**. All'avvenuta ricezione, digitare il codice di verifica e quindi fare clic su **Avanti**.
9. In **Recuperare l'account**, digitare la nuova password per l'account utente 2 e quindi fare clic su **Fine**. Annotare la password dell'account utente 2 modificata e archiviarla in un luogo sicuro.
10. In una scheda separata dello stesso browser, digitare [https://portal.office.com](https://portal.office.com), quindi accedere con il nome dell'account utente 2 e la nuova password. Dovrebbe essere visualizzata la pagina **Office Home**.

Vedere il passaggio [Semplificare la reimpostazione della password](identity-password-reset.md) nella fase Identità per informazioni e collegamenti per configurare la reimpostazione della password.

## <a name="next-step"></a>Passaggio successivo

Esplorare altre caratteristiche e funzionalità [identità](m365-enterprise-test-lab-guides.md#identity) nell'ambiente di test.

## <a name="see-also"></a>Vedere anche

[Guide al lab di test di Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Distribuzione di Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Documentazione di Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
