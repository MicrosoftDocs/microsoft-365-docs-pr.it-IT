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
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLGS
- Ent_TLGs
ms.assetid: ''
description: "Riepilogo: informazioni sulla configurazione e sul test di reimpostazione della password per l'ambiente di testing di Microsoft 365."
ms.openlocfilehash: 5d98dcc50f16bc08da787a928beeeacf825201c9
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487425"
---
# <a name="password-reset-for-your-microsoft-365-test-environment"></a>Reimpostazione della password per l'ambiente di testing di Microsoft 365

*Questa guida del laboratorio di testing può essere utilizzata solo per Microsoft 365 per gli ambienti di testing dell'organizzazione.*

La reimpostazione self-service (SSPR) di Azure Active Directory (AD Azure) consente agli utenti di reimpostare o sbloccare le proprie password o account.

In questo articolo viene descritto come configurare e testare la reimpostazione delle password nell'ambiente di testing di Microsoft 365.

La configurazione di SSPR comporta tre fasi:
- [Fase 1: configurare la sincronizzazione hash delle password per l'ambiente di testing di Microsoft 365](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [Fase 2: Abilitare il writeback delle password](#phase-2-enable-password-writeback)
- [Fase 3: Configurare e testare la reimpostazione della password](#phase-3-configure-and-test-password-reset)
    
![Guide al lab di test per il cloud Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Per una mappa visiva su tutti gli articoli della guida del laboratorio di testing di Microsoft 365 for Enterprise, accedere a [microsoft 365 per la guida dello stack del laboratorio di testing dell'organizzazione](../downloads/Microsoft365EnterpriseTLGStack.pdf).

## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Fase 1: configurare la sincronizzazione hash delle password per l'ambiente di testing di Microsoft 365

Per prima cosa, seguire le istruzioni riportate in [sincronizzazione hash delle password](password-hash-sync-m365-ent-test-environment.md). 

La configurazione risultante è simile alla seguente:
  
![L'organizzazione simulata con ambiente di testing per la sincronizzazione hash delle password](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
Questa configurazione è costituita da:
  
- Un abbonamento di valutazione o a pagamento a Microsoft 365 E5.
- Una Intranet dell'organizzazione semplificata connessa a Internet, costituita dalle macchine virtuali DC1, APP1 e CLIENT1 in una subnet di una rete virtuale di Azure.
- Azure AD Connect viene eseguito su APP1 per sincronizzare il dominio TESTLAB di Active Directory Domain Services con il tenant di Azure AD dell'abbonamento a Microsoft 365.

## <a name="phase-2-enable-password-writeback"></a>Fase 2: Abilitare il writeback delle password

Seguire le istruzioni in[Fase 2 delle guide al lab di test sul writeback delle password](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).

Per usare la reimpostazione delle password è necessario abilitare il writeback delle password.
  
## <a name="phase-3-configure-and-test-password-reset"></a>Fase 3: Configurare e testare la reimpostazione della password

In questa fase, configurare la reimpostazione della password nel tenant di Azure AD tramite l'appartenenza al gruppo e quindi verificare che funzioni correttamente.

Innanzitutto, abilitare la reimpostazione della password per gli account in un gruppo specifico di Azure AD.

1. Aprire [https://portal.azure.com](https://portal.azure.com) da un'istanza privata del browser, quindi accedere usando le credenziali dell'account di amministratore globale.
2. Nel portale di Azure, selezionare gruppi di **Azure Active Directory**  >  **Groups**  >  **nuovo gruppo**.
3. Impostare **Tipo di gruppo** su **Sicurezza**, **Nome del gruppo** su **Reimpostazione della password** e **Tipo di appartenenza** su **Assegnato**.
4. Seleziona **membri**, trova e seleziona **utente 3**, seleziona **Seleziona**, quindi seleziona **Crea**.
5. Chiudere il riquadro **Gruppi**.
6. Nel riquadro di Azure Active Directory, selezionare **Reimposta password** nella barra di spostamento a sinistra.
7. Nel riquadro **Reimpostazione password-Proprietà** scegliere **Selezionato** sotto l'opzione **Reimpostazione password self-service abilitata**.
8. Selezionare **Seleziona gruppo**, selezionare il gruppo **reimpostazione della password** e **quindi selezionare**  >  **Salva**.
9. Chiudere l'istanza privata del browser.

Successivamente, verificare la reimpostazione della password per l'account User 3.

1. Aprire una nuova istanza privata del browser e passare alla pagina [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup).
1. Accedere con le credenziali dell'account utente 3.
1. Per **ulteriori informazioni**, fare clic su **Avanti**. 
1. In **Mantenere l'accesso all'account **, inserire il proprio numero di telefono cellulare e l'account di posta elettronica personale o aziendale per l'autenticazione.
1. Dopo aver verificato entrambi, selezionare **sembra buono**e quindi chiudere l'istanza privata del browser.
1. In una nuova istanza del browser privato, andare a [https://aka.ms/sspr](https://aka.ms/sspr) .
1. Immettere il nome dell'account utente 3, immettere i caratteri del CAPTCHA, quindi selezionare **Avanti**.
1. Per la **verifica passaggio 1**, selezionare posta elettronica **il messaggio**di posta elettronica alternativo, quindi selezionare **posta**elettronica. Quando si riceve il messaggio di posta elettronica, immettere il codice di verifica e quindi fare clic su **Avanti**.
1. In torna all' **account**, immetti una nuova password per l'account User 3 e quindi seleziona **fine**. Prendere nota della password cambiata dell'account utente 3 e conservarla in un luogo sicuro.
1. In una scheda separata del browser stesso, passare a [https://portal.office.com](https://portal.office.com) e quindi accedere con il nome dell'account utente 3 e la nuova password. Verrà visualizzata la **Home Page Microsoft Office**.

## <a name="next-step"></a>Passaggio successivo

Esplorare altre caratteristiche e funzionalità [identità](m365-enterprise-test-lab-guides.md#identity) nell'ambiente di test.

## <a name="see-also"></a>Vedere anche

[Guide ai lab di test di Microsoft 365 per le aziende](m365-enterprise-test-lab-guides.md)

[Panoramica di Microsoft 365 per le aziende](microsoft-365-overview.md)

[Microsoft 365 per la documentazione relativa all'organizzazione](https://docs.microsoft.com/microsoft-365-enterprise/)
