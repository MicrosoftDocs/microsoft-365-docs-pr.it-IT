---
title: Proteggere gli account di amministratore globale nell'ambiente di testing di Microsoft 365 per le aziende
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/12/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Seguire questa procedura per proteggere gli account amministratore globale nell'ambiente di testing di Microsoft 365 per le aziende.
ms.openlocfilehash: 1ae04e4761ed86e087e647464ad522466ed6abef
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487637"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-for-enterprise-test-environment"></a>Proteggere gli account di amministratore globale nell'ambiente di testing di Microsoft 365 per le aziende

*Questa guida del laboratorio di testing può essere usata solo per gli ambienti di testing di Microsoft 365 per le aziende.*

È possibile impedire attacchi digitali all'organizzazione garantendo che gli account amministratore siano il più sicuri possibile. 

Questo articolo descrive come usare i criteri di accesso condizionale di Azure Active Directory (Azure AD) per proteggere gli account amministratore globale.

La protezione degli account amministratore globale nell'ambiente di testing di Microsoft 365 per le aziende prevede due fasi:
- [Fase 1: creare l'ambiente di testing di Microsoft 365 per le aziende](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fase 2: configurare i criteri di accesso condizionale](#phase-2-configure-conditional-access-policies)

![Guide al lab di test per il cloud Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Per una mappa visiva di tutti gli articoli della guida del lab di test di Microsoft 365 per le aziende, passare a [Microsoft 365 per enterprise Test Lab Guide Stack.](../downloads/Microsoft365EnterpriseTLGStack.pdf)

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: creare l'ambiente di testing di Microsoft 365 per le aziende

Se si desidera testare la protezione dell'account amministratore globale in modo leggero con i requisiti minimi, seguire le istruzioni in [Configurazione di base lightweight.](lightweight-base-configuration-microsoft-365-enterprise.md)
  
Se si desidera testare la protezione dell'account amministratore globale in un'organizzazione simulata, seguire le istruzioni in [Autenticazione pass-through.](pass-through-auth-m365-ent-test-environment.md)
  
> [!NOTE]
> Il test della protezione dell'account amministratore globale non richiede l'ambiente di testing aziendale simulato, che include una rete Intranet simulata connessa a Internet e la sincronizzazione della directory per Servizi di dominio Active Directory. Qui viene fornito come opzione in modo da poter testare la protezione dell'account amministratore globale e sperimentarla in un ambiente che rappresenta un'organizzazione tipica. 
  
## <a name="phase-2-configure-conditional-access-policies"></a>Fase 2: configurare i criteri di accesso condizionale

Prima di tutto, creare un nuovo account utente come amministratore globale dedicato.

1. In una scheda separata, aprire l'interfaccia di amministrazione di [Microsoft 365.](https://admin.microsoft.com/)
2. Selezionare **Utenti**  >  **attivi e** quindi Aggiungi **utente.**
3. Nel riquadro **Aggiungi utente** immettere **DedicatedAdmin** nelle **caselle** Nome , **Nome** visualizzato e **Nome utente.**
4. Selezionare **Password,** selezionare **Consenti la creazione della password** e quindi immettere una password complessa. Registrare la password per il nuovo account in una posizione sicura.
5. Selezionare **Avanti**.
6. Nel riquadro **Assegnare licenze di** prodotto selezionare **Microsoft 365 E5** e quindi fare clic su **Avanti.**
7. Nel riquadro **Impostazioni facoltative,** selezionare **Ruoli**  >  **Admin center access** Global  >  **admin**  >  **Next**.
8. Nel riquadro **You're almost done,** select **Finish adding**, and then select **Close.**

Successivamente, creare un nuovo gruppo denominato GlobalAdmins e aggiungerne l'account DedicatedAdmin.

1. Nella scheda **dell'interfaccia di amministrazione di Microsoft 365** selezionare Gruppi **nel** riquadro di spostamento sinistro e quindi **selezionare Gruppi.**
2. Selezionare **Aggiungi gruppo.**
3. Nel riquadro **Scegliere un tipo di** gruppo selezionare **Sicurezza** e quindi fare clic su **Avanti.**
4. Nel riquadro **Set up the basics** selezionare **Create group** e quindi **close.**
5. Nel riquadro **Rivedi e completa l'aggiunta** del gruppo, immettere **GlobalAdmins** e quindi selezionare **Avanti.**
7. Nell'elenco dei gruppi selezionare il **gruppo GlobalAdmins.**
8. Nel riquadro **GlobalAdmins** selezionare **Membri** e quindi selezionare **Visualizza tutti e gestisci membri.**
9. Nel riquadro **GlobalAdmins** selezionare Aggiungi **membri,** selezionare l'account **DedicatedAdmin** e l'account amministratore globale, quindi selezionare **Salva**  >  **chiudi.**  >  

Successivamente, creare criteri di accesso condizionale per richiedere l'autenticazione a più fattori per gli account amministratore globale e per negare l'autenticazione se il rischio di accesso è medio o alto.

Questo primo criterio richiede che tutti gli account amministratore globale utilizzino l'autenticazione a più fattori.

1. In una nuova scheda del browser passare a [https://portal.azure.com](https://portal.azure.com) .
2. Fare clic **su Accesso condizionale per la sicurezza** di Azure Active  >    >  Directory.
3. Nel riquadro **Accesso condizionale - Criteri** selezionare Criteri di base: Richiedi MFA per gli amministratori **(anteprima).**
4. Nel riquadro **Criteri di base** selezionare Usa immediatamente i criteri > **Salva.**

Questo secondo criterio blocca l'accesso all'autenticazione dell'account amministratore globale quando il rischio di accesso è medio o alto.

1. Nel riquadro **Accesso condizionale - Criteri** selezionare Nuovo **criterio.**
2. Nel riquadro **Nuovo** immettere **Amministratori globali** in **Nome**.
3. Nella sezione **Assegnazioni** selezionare **Utenti e gruppi.**
4. Nella scheda **Includi** del **riquadro** Utenti e gruppi selezionare **Seleziona** utenti e  >  **gruppi.**  >  
5. Nel riquadro **Seleziona** selezionare il **gruppo GlobalAdmins** e quindi **selezionare Fatto.**  >  
6. Nella sezione **Assegnazioni** selezionare **Condizioni.**
7. Nel riquadro **Condizioni** selezionare **Rischio** di  accesso, selezionare Sì per **Configura,** **selezionare** Alto e **Medio** e quindi selezionare **Seleziona** e **fatto.**
8. Nella sezione **Controlli di** accesso del **riquadro Nuovo** selezionare **Concedi.**
9. Nel riquadro **Concedi** selezionare **Blocca accesso** e quindi **Selezionare.**
10. Nel riquadro **Nuovo** selezionare **Attivato** per **Abilita criterio** e quindi selezionare **Crea.**
11. Chiudere il **portale di Azure e** le schede dell'interfaccia di amministrazione di Microsoft **365.**

Per testare il primo criterio, disconnettersi e accedere con l'account DedicatedAdmin. Dovrebbe essere richiesto di configurare l'autenticazione a più fattori. Ciò dimostra che viene applicato il primo criterio.

## <a name="next-step"></a>Passaggio successivo

Esplorare altre caratteristiche e funzionalità [identità](m365-enterprise-test-lab-guides.md#identity) nell'ambiente di test.

## <a name="see-also"></a>Vedere anche

[Guida di orientamento all'identità](identity-roadmap-microsoft-365.md)

[Guide ai lab di test di Microsoft 365 per le aziende](m365-enterprise-test-lab-guides.md)

[Panoramica di Microsoft 365 per le aziende](microsoft-365-overview.md)

[Documentazione di Microsoft 365 for enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
