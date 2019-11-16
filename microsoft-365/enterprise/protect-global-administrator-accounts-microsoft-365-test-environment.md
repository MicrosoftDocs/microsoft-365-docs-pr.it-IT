---
title: Proteggere gli account di amministratore globale nell'ambiente di testing di Microsoft 365 Enterprise
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/16/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Attenersi alla procedura seguente per proteggere gli account di amministratore globale nell'ambiente di testing di Microsoft 365 Enterprise.
ms.openlocfilehash: 89985f99f5471aab87189e78035062add2c6bad9
ms.sourcegitcommit: 9ee873c6a2f738a0c99921e036894b646742e706
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/15/2019
ms.locfileid: "38673332"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-enterprise-test-environment"></a>Proteggere gli account di amministratore globale nell'ambiente di testing di Microsoft 365 Enterprise

*Questa guida del laboratorio di testing può essere utilizzata solo per gli ambienti di testing di Microsoft 365 Enterprise.*

È possibile impedire attacchi digitali all'organizzazione assicurando che gli account di amministratore siano il più sicuro possibile. In questo articolo viene descritto come utilizzare i criteri di accesso condizionale di Azure Active Directory (Azure AD) per proteggere gli account di amministratore globale.

Sono disponibili due fasi per la protezione degli account amministratore globale nell'ambiente di testing di Microsoft 365 Enterprise:

1.  Creare l'ambiente di testing di Microsoft 365 Enterprise.
2.  Proteggere l'account di amministratore globale dedicato.

![Guide del laboratorio di testing per il cloud Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Fare clic [qui](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) per consultare una mappa di tutti gli articoli relativi alla guida al lab test di Microsoft 365 Enterprise.

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Fase 1: Creare l'ambiente di testing di Microsoft 365 Enterprise

Se si desidera semplicemente testare la protezione degli account amministratore globale con i requisiti minimi, seguire le istruzioni riportate in [Lightweight base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Se si desidera testare la protezione degli account amministratore globale in un'azienda simulata, seguire le istruzioni riportate nell' [autenticazione pass-through](pass-through-auth-m365-ent-test-environment.md).

  
> [!NOTE]
> Testing Global Administrator account Protection non richiede l'ambiente di testing dell'organizzazione simulata, che include una rete Intranet simulata connessa a Internet e la sincronizzazione della directory per un servizio di dominio Active Directory (AD DS). Viene fornito come opzione in modo che sia possibile testare la protezione degli account amministratore globale e sperimentarla in un ambiente che rappresenta un'organizzazione tipica. 
  
## <a name="phase-2-configure-conditional-access-policies"></a>Fase 2: configurare i criteri di accesso condizionale

Per prima cosa, creare un nuovo account utente come amministratore globale dedicato.

1. In una scheda separata, aprire l'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com/).
2. In **utenti attivi**fare clic su **Aggiungi utente**.
3. Nella pagina **nuovo utente** , digitare **DedicatedAdmin** in **nome**, **nome visualizzato**e nome **utente**.
4. Fare clic su **password**, fare clic su **fammi creare la password**e quindi digitare una password complessa. Registrare la password per il nuovo account in una posizione sicura.
5. Cancellare **fare in modo che l'utente modifichi la password al primo accesso**.
6. Fare clic su **ruoli**, quindi su **amministratore globale**.
7. Fare clic su **licenze di prodotto**e quindi accendere le licenze **Enterprise Mobility + Security e5** e **Office 365 Enterprise E5** .
8. Fare clic su **Aggiungi**.
9. Nella **pagina utente è stata aggiunta**l'opzione **Invia password tramite posta elettronica**e quindi fare clic su **Chiudi**.

Successivamente, creare un nuovo gruppo denominato GlobalAdmins e aggiungere l'account di DedicatedAdmin.

1. Nella scheda interfaccia di **amministrazione di Microsoft 365** fare clic sull'icona gruppi nel riquadro di spostamento a sinistra, quindi fare clic su **gruppi**.
2. Fare clic su **Aggiungi gruppo**.
3. Nella pagina **nuovo gruppo** digitare **GlobalAdmins**.
4. Fare clic su **Seleziona proprietario** fare clic sull'account amministratore globale, quindi fare clic su **Aggiungi > Chiudi**.
5. Nell'elenco dei gruppi fare clic sul gruppo **GlobalAdmins** .
6. Nella pagina **GlobalAdmins** fare clic su **modifica per membro**, quindi fare clic su **Aggiungi membri**.
7. Nell'elenco, fare clic sull'account **DedicatedAdmin** , quindi fare clic su **salva > chiudi > Chiudi >** interfaccia di amministrazione.

Successivamente, creare criteri di accesso condizionale per richiedere l'autenticazione a più fattori per gli account di amministratore globale e negare l'autenticazione se il rischio di ingresso è medio o elevato.

Questo primo criterio richiede che tutti gli account di amministratore globale utilizzino AMF.

1. In una nuova scheda del browser, passare a [https://portal.azure.com](https://portal.azure.com).
2. Fare clic su **Azure Active Directory > accesso condizionale**.
3. Nel pannello **criteri di accesso condizionale** fare clic su **criteri di base: richiedere l'autenticazione master per gli amministratori (anteprima)**.
4. Nei **criteri di base...** Blade, fare clic su **Usa criteri immediatamente > Salva**.

Questo secondo criterio blocca l'accesso all'autenticazione dell'account amministratore globale quando il rischio di ingresso è medio o elevato.

1. Nel pannello **criteri di accesso condizionale** fare clic su **nuovo criterio**.
2. Nel **nuovo** Blade, digitare **Global Administrators** in **Name**.
3. Nella sezione **assegnazioni** fare clic su **utenti e gruppi**.
4. Nella scheda **Includi** del Blade **utenti e gruppi** fare clic su **Seleziona utenti e gruppi > utenti e gruppi > selezionare**.
5. Nel pannello **Seleziona** , fare clic sul **GlobalAdmins > seleziona > fatto**.
6. Nella sezione **assegnazioni** fare clic su **condizioni**.
7. Nel pannello **condizioni** fare clic su **rischio di accesso**, fare clic **su Sì** per **Configura**, fare clic su **alto** e **medio**, quindi fare clic su **Seleziona** e **Chiudi**.
8. Nella sezione **controlli di accesso** del **nuovo** Blade, fare clic su **Grant**.
9. Sul Blade **Grant** , fare clic su **Blocca accesso**, quindi fare clic su **Seleziona**.
10. Nel **nuovo** Blade, fare clic **su** **attiva per abilitare il criterio**, quindi fare clic su **Crea**.
11. Chiudere le schede di interfaccia di amministrazione di **Azure Portal** e **Microsoft 365** .

Per testare il primo criterio, disconnettersi e accedere con l'account DedicatedAdmin. È necessario che venga richiesto di configurare l'autenticazione master nell'account utente. Questo dimostra che il primo criterio viene applicato.

Vedere il passaggio [Proteggi account amministratore globale](identity-create-protect-global-admins.md#identity-global-admin) nella fase di identità per informazioni e collegamenti per proteggere gli account di amministratore globale in produzione.

## <a name="next-step"></a>Passaggio successivo

Esplorare altre caratteristiche e funzionalità [identità](m365-enterprise-test-lab-guides.md#identity) nell'ambiente di test.

## <a name="see-also"></a>Vedere anche

[Fase 2: identità](identity-infrastructure.md)

[Guide al lab di test di Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Distribuzione di Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md).

[Documentazione di Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
