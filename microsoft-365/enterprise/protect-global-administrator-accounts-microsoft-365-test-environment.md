---
title: Proteggere gli account di amministratore globale nell'ambiente di testing Microsoft 365 per le aziende
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
description: Eseguire questa procedura per proteggere gli account di amministratore globale nell'ambiente Microsoft 365 per l'ambiente di testing aziendale.
ms.openlocfilehash: 3eab538b59e460857e2fa195aaacf51051f94d6b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918883"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-for-enterprise-test-environment"></a>Proteggere gli account di amministratore globale nell'ambiente di testing Microsoft 365 per le aziende

*Questa guida al laboratorio di testing può essere utilizzata solo per Microsoft 365 per ambienti di test aziendali.*

È possibile impedire attacchi digitali all'organizzazione assicurando che gli account di amministratore siano il più sicuri possibile. 

Questo articolo descrive come usare i criteri di accesso condizionale Azure Active Directory (Azure AD) per proteggere gli account di amministratore globale.

La protezione degli account di amministratore globale nell'ambiente Microsoft 365 per l'ambiente di testing aziendale prevede due fasi:
- [Fase 1: creare l'ambiente di testing Microsoft 365 per le aziende](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fase 2: configurare i criteri di accesso condizionale](#phase-2-configure-conditional-access-policies)

![Guide al lab di test per il cloud Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Per una mappa visiva a tutti gli articoli dello stack Microsoft 365 per enterprise Test Lab Guide, passare a [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: creare l'ambiente di testing Microsoft 365 per le aziende

Se si desidera testare la protezione dell'account amministratore globale in modo leggero con i requisiti minimi, seguire le istruzioni in [Configurazione di base leggera](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Se si desidera testare la protezione dell'account amministratore globale in un'organizzazione simulata, seguire le istruzioni in [Autenticazione pass-through.](pass-through-auth-m365-ent-test-environment.md)
  
> [!NOTE]
> Il test della protezione dell'account amministratore globale non richiede l'ambiente di testing aziendale simulato, che include una rete Intranet simulata connessa a Internet e la sincronizzazione della directory per Servizi di dominio Active Directory. Viene fornito qui come opzione in modo da poter testare la protezione dell'account amministratore globale e sperimentarla in un ambiente che rappresenta un'organizzazione tipica. 
  
## <a name="phase-2-configure-conditional-access-policies"></a>Fase 2: configurare i criteri di accesso condizionale

Creare innanzitutto un nuovo account utente come amministratore globale dedicato.

1. In una scheda separata, aprire [l'Microsoft 365 di amministrazione.](https://admin.microsoft.com/)
2. Selezionare **Utenti**  >  **Utenti attivi** e quindi Aggiungi **utente.**
3. Nel riquadro **Aggiungi utente** immettere **DedicatedAdmin** nelle caselle **Nome,** **Nome visualizzato** e **Nome utente.**
4. Selezionare **Password,** selezionare **Consenti la creazione della password** e quindi immettere una password complessa. Registrare la password per il nuovo account in una posizione sicura.
5. Selezionare **Avanti**.
6. Nel riquadro **Assegna licenze di prodotto** selezionare Microsoft 365 E5 e quindi selezionare **Avanti**. 
7. Nel riquadro **Impostazioni facoltative** selezionare **Ruoli**  >  **Accesso all'interfaccia di amministrazione** Amministratore  >  **globale**  >  **Avanti**.
8. Nel riquadro **You're almost done** selezionare **Finish adding** e quindi **close**.

Successivamente, creare un nuovo gruppo denominato GlobalAdmins e aggiungerne l'account DedicatedAdmin.

1. Nella scheda **Microsoft 365 dell'interfaccia** di amministrazione selezionare **Gruppi** nel riquadro di spostamento sinistro e quindi selezionare **Gruppi**.
2. Selezionare **Aggiungi un gruppo**.
3. Nel riquadro **Scegliere un tipo di gruppo** selezionare **Sicurezza** e quindi fare clic su **Avanti.**
4. Nel riquadro **Configura le nozioni di** base selezionare Crea **gruppo** e quindi fare clic su **Chiudi.**
5. Nel riquadro **Rivedere e completare l'aggiunta del** gruppo, immettere **GlobalAdmins** e quindi selezionare **Avanti.**
7. Nell'elenco dei gruppi selezionare il **gruppo GlobalAdmins.**
8. Nel riquadro **GlobalAdmins** selezionare **Membri** e quindi **Selezionare Visualizza tutti e gestisci membri**.
9. Nel riquadro **GlobalAdmins** selezionare **Aggiungi** membri, selezionare **l'account DedicatedAdmin** e l'account amministratore globale, quindi selezionare **Salva**  >  **Chiudi**  >  **Chiudi.**

Successivamente, creare criteri di accesso condizionale per richiedere l'autenticazione a più fattori per gli account amministratore globale e per negare l'autenticazione se il rischio di accesso è medio o elevato.

Questo primo criterio richiede che tutti gli account amministratore globale utilizzino l'autenticazione a più fattori.

1. In una nuova scheda del browser passare a [https://portal.azure.com](https://portal.azure.com) .
2. Fare **clic Azure Active Directory**  >  **sicurezza** accesso  >  **condizionale**.
3. Nel riquadro **Accesso condizionale - Criteri** selezionare Criterio di **base: Richiedi MFA per gli amministratori (anteprima).**
4. Nel riquadro **Criteri di base** selezionare Usa criteri immediatamente > **Salva**.

Questo secondo criterio blocca l'accesso all'autenticazione dell'account amministratore globale quando il rischio di accesso è medio o elevato.

1. Nel riquadro **Accesso condizionale - Criteri** selezionare Nuovo **criterio.**
2. Nel riquadro **Nuovo** immettere **Amministratori globali** in **Nome**.
3. Nella sezione **Assegnazioni** selezionare **Utenti e gruppi**.
4. Nella scheda **Includi** del riquadro **Utenti** e gruppi selezionare **Seleziona** utenti e gruppi  >  **Utenti e** gruppi  >  **Selezionare**.
5. Nel riquadro **Seleziona** selezionare il **gruppo GlobalAdmins** e quindi **selezionare Seleziona**  >  **fatto.**
6. Nella sezione **Assegnazioni** selezionare **Condizioni**.
7. Nel riquadro **Condizioni** selezionare **Rischio** di accesso, **selezionare** Sì per **Configura,** **selezionare** Alto e **Medio** e quindi **selezionare Seleziona** e **Fatto.**
8. Nella sezione **Controlli di** accesso del **riquadro Nuovo** selezionare **Concedi**.
9. Nel riquadro **Concedi** seleziona **Blocca accesso** e quindi seleziona **Seleziona.**
10. Nel riquadro **Nuovo** selezionare **Attivato** per **Abilita criterio** e quindi selezionare **Crea**.
11. Chiudere il **portale di Azure e** Microsoft 365 schede **dell'interfaccia di amministrazione.**

Per testare il primo criterio, disconnettersi e accedere con l'account DedicatedAdmin. Dovrebbe essere richiesto di configurare l'autenticazione a più fattori. Questo dimostra che viene applicato il primo criterio.

## <a name="next-step"></a>Passaggio successivo

Esplorare altre caratteristiche e funzionalità [identità](m365-enterprise-test-lab-guides.md#identity) nell'ambiente di test.

## <a name="see-also"></a>Vedere anche

[Guida di orientamento all'identità](identity-roadmap-microsoft-365.md)

[Guide ai lab di test di Microsoft 365 per le aziende](m365-enterprise-test-lab-guides.md)

[Panoramica di Microsoft 365 per le aziende](microsoft-365-overview.md)

[Documentazione di Microsoft 365 for enterprise](/microsoft-365-enterprise/)