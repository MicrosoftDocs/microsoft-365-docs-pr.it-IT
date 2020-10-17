---
title: Proteggere gli account di amministratore globale nell'ambiente di testing di Microsoft 365 per l'organizzazione
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
description: Attenersi alla procedura seguente per proteggere gli account di amministratore globale nell'ambiente di testing di Microsoft 365 per l'organizzazione.
ms.openlocfilehash: 1ae04e4761ed86e087e647464ad522466ed6abef
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487637"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-for-enterprise-test-environment"></a>Proteggere gli account di amministratore globale nell'ambiente di testing di Microsoft 365 per l'organizzazione

*Questa guida del laboratorio di testing può essere utilizzata solo per Microsoft 365 per gli ambienti di testing dell'organizzazione.*

È possibile impedire attacchi digitali all'organizzazione assicurando che gli account di amministratore siano il più sicuro possibile. 

In questo articolo viene descritto come utilizzare i criteri di accesso condizionale di Azure Active Directory (Azure AD) per proteggere gli account di amministratore globale.

La protezione degli account di amministratore globale nell'ambiente di testing di Microsoft 365 per l'organizzazione implica due fasi:
- [Fase 1: creare l'ambiente di testing di Microsoft 365 per l'organizzazione](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fase 2: configurare i criteri di accesso condizionale](#phase-2-configure-conditional-access-policies)

![Guide al lab di test per il cloud Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Per una mappa visiva su tutti gli articoli della guida del laboratorio di testing di Microsoft 365 for Enterprise, accedere a [microsoft 365 per la guida dello stack del laboratorio di testing dell'organizzazione](../downloads/Microsoft365EnterpriseTLGStack.pdf).

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: creare l'ambiente di testing di Microsoft 365 per l'organizzazione

Se si desidera testare la protezione degli account amministratore globale con i requisiti minimi, seguire le istruzioni contenute in [Lightweight base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Se si desidera testare la protezione degli account amministratore globale in un'azienda simulata, seguire le istruzioni riportate nell' [autenticazione pass-through](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Testing Global Administrator account Protection non richiede l'ambiente di testing dell'organizzazione simulata, che include una rete Intranet simulata connessa a Internet e la sincronizzazione della directory per un servizio di dominio Active Directory (AD DS). Viene fornito come opzione in modo che sia possibile testare la protezione degli account amministratore globale e sperimentarla in un ambiente che rappresenta un'organizzazione tipica. 
  
## <a name="phase-2-configure-conditional-access-policies"></a>Fase 2: configurare i criteri di accesso condizionale

Per prima cosa, creare un nuovo account utente come amministratore globale dedicato.

1. In una scheda separata, aprire l'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com/).
2. Selezionare **utenti**  >  **attivi**e quindi fare clic su **Aggiungi utente**.
3. Nel riquadro **Aggiungi utente** , immettere **DedicatedAdmin** nelle caselle **nome**e cognome, **nome visualizzato**e nome **utente** .
4. Seleziona **password**, quindi **fammi creare la password**e quindi immetti una password complessa. Registrare la password per il nuovo account in una posizione sicura.
5. Selezionare **Avanti**.
6. Nel riquadro **assegna licenze di prodotto** , selezionare **Microsoft 365 E5**, quindi fare clic su **Avanti**.
7. Nel riquadro **impostazioni facoltative** , selezionare **ruoli**amministratore dell'interfaccia di amministrazione di  >  **accesso**  >  **globale**  >  **successivo**.
8. Nel riquadro **quasi finito** , selezionare **fine aggiunta**, quindi selezionare **Chiudi**.

Successivamente, creare un nuovo gruppo denominato GlobalAdmins e aggiungere l'account di DedicatedAdmin.

1. Nella scheda dell'interfaccia di **amministrazione di Microsoft 365** selezionare **gruppi** nel riquadro di spostamento sinistro e quindi selezionare **gruppi**.
2. Selezionare **Aggiungi un gruppo**.
3. Nel riquadro **scegliere un tipo di gruppo** , selezionare **sicurezza**, quindi fare clic su **Avanti**.
4. Nel riquadro **Configura le nozioni di base** , selezionare **Crea gruppo**e quindi **Chiudi**.
5. Nel riquadro **revisione e termina aggiunta gruppo** , immettere **GlobalAdmins**, quindi fare clic su **Avanti**.
7. Nell'elenco dei gruppi, selezionare il gruppo **GlobalAdmins** .
8. Nel riquadro **GlobalAdmins** , selezionare **membri**, quindi fare clic su **Visualizza tutti e Gestisci membri**.
9. Nel riquadro **GlobalAdmins** , selezionare **Aggiungi membri**, selezionare l'account **DedicatedAdmin** e l'account di amministratore globale e quindi fare clic su **Salva**  >  **Chiudi Chiudi**  >  **Close**.

Successivamente, creare criteri di accesso condizionale per richiedere l'autenticazione a più fattori per gli account di amministratore globale e negare l'autenticazione se il rischio di ingresso è medio o elevato.

Questo primo criterio richiede che tutti gli account di amministratore globale utilizzino AMF.

1. In una nuova scheda del browser, passare a [https://portal.azure.com](https://portal.azure.com) .
2. Fare **Azure Active Directory**clic su  >  **Security**  >  **accesso condizionale**per la sicurezza di Azure Active Directory.
3. Nel riquadro **criteri di accesso condizionale** selezionare **criteri di base: richiedere l'autenticazione master per gli amministratori (anteprima)**.
4. Nel riquadro **criteri di base** , selezionare **usa criteri immediatamente > Salva**.

Questo secondo criterio blocca l'accesso all'autenticazione dell'account amministratore globale quando il rischio di ingresso è medio o elevato.

1. Nel riquadro **criteri di accesso condizionale** selezionare **nuovo criterio**.
2. Nel **nuovo** riquadro, immettere gli **amministratori globali** in **nome**.
3. Nella sezione **assegnazioni** selezionare **utenti e gruppi**.
4. Nella scheda **Includi** del riquadro **utenti e gruppi** Selezionare Seleziona utenti e **gruppi utenti e**  >  **gruppi**  >  **Select**.
5. Nel riquadro **Seleziona** selezionare il gruppo **GlobalAdmins** e **quindi selezionare**  >  **fine**.
6. Nella sezione **assegnazioni** selezionare **condizioni**.
7. Nel riquadro **condizioni** selezionare rischio di **accesso**, selezionare **Sì** per **Configura**, selezionare **alto** e **medio**e quindi selezionare **Seleziona** e **Chiudi**.
8. Nella sezione **controlli di accesso** del **nuovo** riquadro selezionare **Concedi**.
9. Nel riquadro **Concedi** selezionare **blocca l'accesso**e quindi selezionare **Seleziona**.
10. Nel **nuovo** riquadro, selezionare attivato **per** **attivare il criterio**, quindi selezionare **Crea**.
11. Chiudere le schede di interfaccia di amministrazione di **Azure Portal** e **Microsoft 365** .

Per testare il primo criterio, disconnettersi e accedere con l'account DedicatedAdmin. È necessario che venga richiesto di configurare l'autenticazione master. Questo dimostra che il primo criterio viene applicato.

## <a name="next-step"></a>Passaggio successivo

Esplorare altre caratteristiche e funzionalità [identità](m365-enterprise-test-lab-guides.md#identity) nell'ambiente di test.

## <a name="see-also"></a>Vedere anche

[Roadmap dell'identità](identity-roadmap-microsoft-365.md)

[Guide ai lab di test di Microsoft 365 per le aziende](m365-enterprise-test-lab-guides.md)

[Panoramica di Microsoft 365 per le aziende](microsoft-365-overview.md)

[Microsoft 365 per la documentazione relativa all'organizzazione](https://docs.microsoft.com/microsoft-365-enterprise/)
