---
title: Reimpostazione della password per l'ambiente di testing di Microsoft 365
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/13/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLGS
- Ent_TLGs
ms.assetid: ''
description: "Riepilogo: informazioni sulla configurazione e sul test di reimpostazione della password per l'ambiente di testing di Microsoft 365."
ms.openlocfilehash: c8d5ed0c7feac98afd3230a305f4ab1f850ca7f8
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/13/2020
ms.locfileid: "42633174"
---
# <a name="password-reset-for-your-microsoft-365-test-environment"></a>Reimpostazione della password per l'ambiente di testing di Microsoft 365

*Questa guida al lab di test può essere usata solo per ambienti di testing di Microsoft 365 Enterprise.*

La reimpostazione self-service (SSPR) di Azure Active Directory (AD Azure) consente agli utenti di reimpostare o sbloccare le proprie password o account. 

Questo articolo descrive come configurare e testare la reimpostazione della password nel proprio ambiente di test di Microsoft 365 in tre fasi:

1.  Creare l'ambiente di testing di Microsoft 365 Enterprise.
2.  Attivare il writeback delle password.
3.  Configurare e testare la reimpostazione della password per l'account utente 3.
    
![Guide al lab di test per il cloud Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Fare clic [qui](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) per consultare una mappa di tutti gli articoli relativi alla guida al lab test di Microsoft 365 Enterprise.

## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Fase 1: configurare la sincronizzazione hash delle password per l'ambiente di testing di Microsoft 365

Prima di tutto, seguire le istruzioni riportate in [Sincronizzazione hash delle password](password-hash-sync-m365-ent-test-environment.md). Di seguito è riportata la configurazione risultante.
  
![L'organizzazione simulata con ambiente di testing per la sincronizzazione hash delle password](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
Questa configurazione è costituita da: 
  
- Abbonamenti di valutazione o a pagamento a Microsoft 365 E5 o a Office 365 E5.
- Una intranet dell’organizzazione semplificata connessa a Internet e costituita dalle macchine virtuali DC1 APP1 e CLIENT1 in una sottorete di una rete virtuale Azure. 
- Azure AD Connect viene eseguito su APP1 per sincronizzare il dominio TESTLAB di Active Directory Domain Services con il tenant di Azure AD dell'abbonamento a Microsoft 365 o a Office 365.

## <a name="phase-2-enable-password-writeback"></a>Fase 2: Abilitare il writeback delle password

Seguire le istruzioni in[Fase 2 delle guide al lab di test sul writeback delle password](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).

Per usare la reimpostazione delle password è necessario abilitare il writeback delle password.
  
## <a name="phase-3-configure-and-test-password-reset"></a>Fase 3: Configurare e testare la reimpostazione della password

In questa fase, è possibile configurare la reimpostazione della password nel tenant di Azure AD attraverso l'appartenenza a un gruppo e quindi verificarne il funzionamento.

Innanzitutto, abilitare la reimpostazione della password per gli account in un gruppo specifico di Azure AD.

1. Aprire [https://portal.azure.com](https://portal.azure.com) da un'istanza privata del browser, quindi accedere usando le credenziali dell'account di amministratore globale.
2. Nel portale di Azure fare clic su **Azure Active Directory > Gruppi > Nuovo gruppo**.
3. Impostare **Tipo di gruppo** su **Sicurezza**, **Nome del gruppo** su **Reimpostazione della password** e **Tipo di appartenenza** su **Assegnato**. 
4. Fare clic su **Membri**, trovare e selezionare **Utente 3**, quindi fare clic su **Seleziona** e infine fare clic su **Crea**.
5. Chiudere il riquadro **Gruppi**.
6. Nel menu di spostamento a sinistra del riquadro di Azure Active Directory fare clic su **Reimpostazione password**.
7. Nel riquadro **Reimpostazione password-Proprietà** scegliere **Selezionato** sotto l'opzione **Reimpostazione password self-service abilitata**.
8. Fare clic su **Seleziona gruppo**, selezionare il gruppo **PWReset** e quindi fare clic su **Seleziona > Salva**.
9. Chiudere l'istanza privata del browser.

Successivamente, testare la reimpostazione della password per l'account utente 3.

1. Aprire una nuova istanza privata del browser e passare alla pagina [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup).
2. Accedere con le credenziali dell'account utente 3.
3. In **Sono necessarie altre informazioni ** fare clic su **Avanti**. 
5. In **Mantenere l'accesso all'account **, inserire il proprio numero di telefono cellulare e l'account di posta elettronica personale o aziendale per l'autenticazione.
7. Dopo che sono stati verificati entrambi, fare clic su **Approvato** e chiudere l'istanza privata del browser.
8. Aprire una nuova istanza del browser privata e accedere a [https://aka.ms/sspr](https://aka.ms/sspr).
9. Digitare il nome dell'account utente 3, digitare i caratteri del CAPTCHA e quindi fare clic su **Avanti**.
10. Come **primo passaggio di verifica**, fare clic su **Inviare un messaggio all'indirizzo di posta elettronica alternativo**, quindi fare clic su **Posta elettronica**. All'avvenuta ricezione, digitare il codice di verifica e quindi fare clic su **Avanti**.
11. In **Tornare all'account** digitare una nuova password per l'account utente 3 e quindi fare clic su **Fine**. Prendere nota della password cambiata dell'account utente 3 e conservarla in un luogo sicuro.
12. In una scheda separata del browser stesso, passare a [https://portal.office.com](https://portal.office.com) e quindi accedere con il nome dell'account utente 3 e la nuova password. Verrà visualizzata la **Home Page Microsoft Office**.

Vedere il passaggio [Semplificare la reimpostazione della password](identity-secure-your-passwords.md#identity-pw-reset) nella fase Identità per informazioni e collegamenti per configurare la reimpostazione della password.

## <a name="next-step"></a>Passaggio successivo

Esplorare altre caratteristiche e funzionalità [identità](m365-enterprise-test-lab-guides.md#identity) nell'ambiente di test.

## <a name="see-also"></a>Vedere anche

[Guide al lab di test di Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Distribuzione di Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Documentazione di Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
