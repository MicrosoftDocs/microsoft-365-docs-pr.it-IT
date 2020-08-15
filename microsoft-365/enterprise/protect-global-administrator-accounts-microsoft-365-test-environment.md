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
ms.openlocfilehash: fff09ca41ff0b648d46b5c33f753affc01242264
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695183"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-for-enterprise-test-environment"></a>Proteggere gli account di amministratore globale nell'ambiente di testing di Microsoft 365 per l'organizzazione

*Questa guida del laboratorio di testing può essere utilizzata solo per Microsoft 365 per gli ambienti di testing dell'organizzazione.*

È possibile impedire attacchi digitali all'organizzazione assicurando che gli account di amministratore siano il più sicuro possibile. In questo articolo viene descritto come utilizzare i criteri di accesso condizionale di Azure Active Directory (Azure AD) per proteggere gli account di amministratore globale.

Sono disponibili due fasi per la protezione degli account amministratore globale nell'ambiente di testing di Microsoft 365 per l'organizzazione:

1.  Creare l'ambiente di testing di Microsoft 365 per l'organizzazione.
2.  Proteggere l'account di amministratore globale dedicato.

![Guide al lab di test per il cloud Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Fare clic [qui](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) per consultare una mappa di tutti gli articoli disponibili nella serie di guide al lab di test di Microsoft 365 per le aziende.

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: creare l'ambiente di testing di Microsoft 365 per l'organizzazione

Se si desidera semplicemente testare la protezione degli account amministratore globale con i requisiti minimi, seguire le istruzioni riportate in [Lightweight base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Se si desidera testare la protezione degli account amministratore globale in un'azienda simulata, seguire le istruzioni riportate nell' [autenticazione pass-through](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Testing Global Administrator account Protection non richiede l'ambiente di testing dell'organizzazione simulata, che include una rete Intranet simulata connessa a Internet e la sincronizzazione della directory per un servizio di dominio Active Directory (AD DS). Viene fornito come opzione in modo che sia possibile testare la protezione degli account amministratore globale e sperimentarla in un ambiente che rappresenta un'organizzazione tipica. 
  
## <a name="phase-2-configure-conditional-access-policies"></a>Fase 2: configurare i criteri di accesso condizionale

Per prima cosa, creare un nuovo account utente come amministratore globale dedicato.

1. In una scheda separata, aprire l'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com/).
2. Fare clic su **utenti > utenti attivi**, quindi fare clic su **Aggiungi utente**.
3. Nel riquadro **Aggiungi utente** , digitare **DedicatedAdmin** in **nome**, **nome visualizzato**e **nomeutente**.
4. Fare clic su **password**, fare clic su **fammi creare la password**e quindi digitare una password complessa. Registrare la password per il nuovo account in una posizione sicura.
5. Fare clic su **Avanti**.
6. Nel riquadro **assegna licenze di prodotto** selezionare **Microsoft 365 E5**e quindi fare clic su **Avanti**.
7. Nel riquadro **impostazioni facoltative** fare clic su **ruoli**, quindi selezionare interfaccia di **Amministrazione** e **amministratore globale**. Fare clic su **Avanti**.
8. Nel riquadro **quasi finito** , fare clic su **fine aggiungendo**, quindi fare clic su **Chiudi**.

Successivamente, creare un nuovo gruppo denominato GlobalAdmins e aggiungere l'account di DedicatedAdmin.

1. Nella scheda interfaccia di **amministrazione di Microsoft 365** fare clic su **gruppi** nel riquadro di spostamento sinistro e quindi su **gruppi**.
2. Fare clic su **Aggiungi gruppo**.
3. Nel riquadro **scegliere un tipo di gruppo** selezionare **sicurezza**e quindi fare clic su **Avanti**.
4. Nel riquadro **Configura le nozioni di base** fare clic su **Crea gruppo**e quindi fare clic su **Chiudi**.
5. Nel riquadro **revisione e termina aggiunta gruppo** digitare **GlobalAdmins**e quindi fare clic su **Avanti**.
7. Nell'elenco dei gruppi fare clic sul gruppo **GlobalAdmins** .
8. Nel riquadro **GlobalAdmins** , fare clic su **membri**, quindi fare clic su **Visualizza tutti e Gestisci membri**.
9. Nel riquadro **GlobalAdmins** , fare clic su **Aggiungi membri**, selezionare l'account **DedicatedAdmin** e l'account di amministratore globale, quindi fare clic su **Salva > Chiudi > Chiudi**.

Successivamente, creare criteri di accesso condizionale per richiedere l'autenticazione a più fattori per gli account di amministratore globale e negare l'autenticazione se il rischio di ingresso è medio o elevato.

Questo primo criterio richiede che tutti gli account di amministratore globale utilizzino AMF.

1. In una nuova scheda del browser, passare a [https://portal.azure.com](https://portal.azure.com) .
2. Fare clic su **Azure Active Directory > sicurezza > accesso condizionale**.
3. Nel riquadro **criteri di accesso condizionale** fare clic su **criteri di base: richiedere l'autenticazione master per gli amministratori (anteprima)**.
4. Nel riquadro **criteri di base** , fare clic su **usa criteri immediatamente > Salva**.

Questo secondo criterio blocca l'accesso all'autenticazione dell'account amministratore globale quando il rischio di ingresso è medio o elevato.

1. Nel riquadro **criteri di accesso condizionale** fare clic su **nuovo criterio**.
2. Nel **nuovo** riquadro, digitare **Global Administrators** in **nome**.
3. Nella sezione **assegnazioni** fare clic su **utenti e gruppi**.
4. Nella scheda **Includi** del riquadro **utenti e gruppi** fare clic su **Seleziona utenti e gruppi > utenti e gruppi > selezionare**.
5. Nel riquadro **Seleziona** fare clic sul gruppo **GlobalAdmins** e quindi fare clic su **Seleziona > operazione completata**.
6. Nella sezione **assegnazioni** fare clic su **condizioni**.
7. Nel riquadro **condizioni** fare clic su **rischio di accesso**, fare clic **su Sì** per **Configura**, fare clic su **alto** e **medio**, quindi fare clic su **Seleziona** e **Chiudi**.
8. Nella sezione **controlli di accesso** del **nuovo** riquadro fare clic su **Concedi**.
9. Nel riquadro **Concedi** , fare clic su **Blocca accesso**, quindi fare clic su **Seleziona**.
10. Nel **nuovo** riquadro, fare clic **su** attiva per **abilitare il criterio**, quindi fare clic su **Crea**.
11. Chiudere le schede di interfaccia di amministrazione di **Azure Portal** e **Microsoft 365** .

Per testare il primo criterio, disconnettersi e accedere con l'account DedicatedAdmin. È necessario che venga richiesto di configurare l'autenticazione master. Questo dimostra che il primo criterio viene applicato.

## <a name="next-step"></a>Passaggio successivo

Esplorare altre caratteristiche e funzionalità [identità](m365-enterprise-test-lab-guides.md#identity) nell'ambiente di test.

## <a name="see-also"></a>Vedere anche

[Roadmap dell'identità](identity-roadmap-microsoft-365.md)

[Guide ai lab di test di Microsoft 365 per le aziende](m365-enterprise-test-lab-guides.md)

[Panoramica di Microsoft 365 per le aziende](microsoft-365-overview.md)

[Microsoft 365 per la documentazione relativa all'organizzazione](https://docs.microsoft.com/microsoft-365-enterprise/)
