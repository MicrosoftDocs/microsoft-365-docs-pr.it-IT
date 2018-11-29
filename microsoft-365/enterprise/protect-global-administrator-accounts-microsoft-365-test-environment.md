---
title: Proteggere gli account di amministratore globale nell'ambiente di test Microsoft 365 Enterprise
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- TLG
- Ent_TLGs
description: Utilizzare la procedura seguente per proteggere gli account di amministratore globale nell'ambiente di test Microsoft 365 aziendale.
ms.openlocfilehash: 233e2178b060df4950c340e034d5f51216fac8fb
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868302"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-enterprise-test-environment"></a>Proteggere gli account di amministratore globale nell'ambiente di test Microsoft 365 Enterprise

È possibile impedire attacchi di tipo digitale nella propria organizzazione per garantire che l'account amministratore siano la massima protezione. In questo articolo viene descritto come utilizzare criteri di accesso condizionale sicurezza App Cloud di Office 365 e Azure Active Directory per proteggere gli account di amministratore globale.

Esistono due fasi di proteggere gli account di amministratore globale nell'ambiente di test Microsoft 365 aziendale:

1.  Creare l'ambiente di test Microsoft 365 Enterprise.
2.  Proteggere il tuo account amministratore globale dedicato.

![Guide al lab di test per il cloud Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Fare clic [qui](https://aka.ms/m365etlgstack) per consultare una mappa di tutti gli articoli relativi alla guida al lab test di Microsoft 365 Enterprise.
  

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Fase 1: Preparare l'ambiente di testing Microsoft 365 Enterprise

Se si desidera testare la protezione dell'account amministratore globale in un modo semplice con i requisiti minimi, seguire le istruzioni di [configurazione di base semplificata](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Se si desidera testare la protezione dell'account amministratore globale in un'azienda simulata, seguire le istruzioni [nell'autenticazione pass-through](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Test account amministratore globale protection non richiede l'ambiente di testing simulato enterprise, che include una rete intranet simulata connessi a Internet e la sincronizzazione delle directory per una foresta Windows Server Active Directory. Viene fornito qui come un'opzione in modo da poter testare la protezione dell'account amministratore globale e sperimentare in un ambiente che rappresenta una tipica organizzazione. 
  
## <a name="phase-2-configure-cloud-app-security-and-conditional-access-policies"></a>Fase 2: Configurare la sicurezza di applicazione Cloud e i criteri di accesso condizionale

Creare un criterio di protezione di applicazioni di Office 365 Cloud per monitorare l'attività di account amministratore globale e inviare gli avvisi per l'indirizzo di posta elettronica dell'account di amministratore globale. 

1. Accedere al portale di Office 365 in [http://portal.office.com](http://portal.office.com) utilizzando l'account amministratore globale.
2. Fare clic su tessera di **amministrazione** . Nella scheda di **interfaccia di amministrazione di Office** , fare clic su **Admin Center > sicurezza e conformità**.
3. Nel riquadro di spostamento a sinistra fare clic su **Avvisi > Gestisci gli avvisi avanzati**.
4. Nella pagina **Gestisci gli avvisi avanzati**, fare clic su **Attiva Office 365 Cloud App Security**, quindi fare clic su **Vai a Office 365 Cloud App Security**.
5. Nella nuova scheda **Dashboard**, fare clic su **Controllo > Criteri**.
6. Nella pagina **Criterio**, fare clic su **Crea criterio**, quindi fare clic su **Criteri attività**.
7. In **Nome criterio**, digitare **Attività amministrativa**.
8. In **Gravità del criterio**, fare clic su **Elevata**.
9. In **Categoria**, fare clic su **Account con privilegi**.
10. In **Crea filtri per il criterio**, in **Attività corrispondenti a tutti gli elementi seguenti**, fare clic su **Attività amministrativa**.
11. In **Avvisi**, fare clic su **Invia l'avviso come messaggio di posta elettronica**. In **A**, digitare l'indirizzo di posta elettronica dell'account di amministratore globale.
12. Nella parte inferiore della pagina fare clic su **Crea**.
13. Chiudere la scheda **del Dashboard** .
    
Successivamente, creare un nuovo account utente come amministratore globale dedicato.

1. Nella scheda di **interfaccia di amministrazione di Office** , in **utenti attivi**, fare clic su **Aggiungi utente**.
2. Nella pagina **nuovo utente** , digitare **DedicatedAdmin** in **nome**, **nome visualizzato**e **nome utente**.
3. Fare clic su **Password**, fare clic su **Crea la password**e quindi digitare una password complessa. Registrare la password per il nuovo account in un luogo sicuro.
4. Deselezionare **che l'utente di modificare la password quando accedono prima**.
5. Fare clic su **ruoli**e quindi fare clic su **amministratore globale**.
6. Fare clic su **licenze per i prodotti**e quindi attivare la **mobilità aziendale + E5 di sicurezza** e **le licenze di Office 365 Enterprise E5** .
7. Fare clic su **Aggiungi**.
8. In **utente è stato aggiunto pagina**, deselezionare **inviare password tramite posta elettronica**e quindi fare clic su **Chiudi**.

Successivamente, creare un nuovo gruppo denominato GlobalAdmins e aggiungere l'account di DedicatedAdmin.

1. Nella scheda di **interfaccia di amministrazione di Office** , fare clic sull'icona gruppi nel riquadro di spostamento sinistra e quindi fare clic su **gruppi**.
2. Fare clic su **Aggiungi un gruppo**.
3. Nella pagina **Nuovo gruppo** digitare **GlobalAdmins**.
4. Fare clic su fare clic su **Seleziona proprietario** l'account amministratore globale e quindi fare clic su **Aggiungi > Chiudi**.
5. Nell'elenco dei gruppi fare clic sul gruppo **GlobalAdmins** .
6. Nella pagina **GlobalAdmins** , fare clic su **Modifica per membro**e quindi fare clic su **Aggiungi membri**.
7. Nell'elenco, fare clic sull'account **DedicatedAdmin** e quindi fare clic su **salvare > Chiudi > Chiudi > Admin center**.

Successivamente, creare criteri di accesso condizionale per richiedere l'autenticazione a più fattori per gli account di amministratore globale e Nega l'autenticazione se il rischio di accesso è medio o elevato.

Questo criterio primo richiede che tutti gli account di amministratore globale utilizzano MFA.

1. In una nuova scheda del browser, accedere a [https://portal.azure.com](https://portal.azure.com).
2. Fare clic su **Azure Active Directory > accesso condizionato**.
3. Su blade **accesso condizionato-criteri** , fare clic su **dei criteri di base: richiedono MFA per gli amministratori (preview)**.
4. Su blade **... criteri di base** , fare clic su **utilizzare immediatamente criterio > Salva**.

In questo secondo criterio blocca l'accesso all'autenticazione account amministratore globale quando il rischio di accesso è medio o elevato.

1. Su blade **accesso condizionato-criteri** , fare clic su **nuovo criterio**.
2. Blade **New** , nella **casella Nome**digitare **gli amministratori globali** .
3. Nella sezione **assegnazioni** , fare clic su **utenti e gruppi**.
4. Nella scheda **Includi** della blade **utenti e gruppi** , fare clic su **selezionare utenti e gruppi > utenti e gruppi > selezionare**.
5. Scegliere blade **Selezionare** il **GlobalAdmins > selezionare > Fine**.
6. Nella sezione **assegnazioni** , fare clic su **condizioni**.
7. Su blade **condizioni** , fare clic su **accesso rischio**, fare clic su **Sì** per **configurare**, fare clic su **Medium**e **High** e quindi fare clic su **Seleziona** e **Fine**.
8. Nella sezione **accedere a controlli** di blade **New** , fare clic su **Concedi**.
9. Su blade **Grant** , fare clic su **bloccare l'accesso**e quindi fare clic su **Seleziona**.
10. Su blade **New** , fare clic **su** per **abilitare i criteri**e quindi fare clic su **Crea**.
11. Chiudere le schede di **interfaccia di amministrazione di Office** e **portale Azure** .

Per testare il primo criterio, disconnettersi e accedere con l'account DedicatedAdmin. È necessario richiedere configurare MFA l'account utente. Dimostra che il primo criterio viene applicato.

Nella fase di identità per informazioni e collegamenti per proteggere gli account di amministratore globale nell'ambiente di produzione, vedere la sezione [account amministratore globale di protezione](identity-designate-protect-admin-accounts.md) .

## <a name="next-step"></a>Passaggio successivo

Esplorare altre caratteristiche e funzionalità [identità](m365-enterprise-test-lab-guides.md#identity) nell'ambiente di test.

## <a name="see-also"></a>Vedere anche

[Fase 2: identità](identity-infrastructure.md)

[Guide al lab di test di Microsoft 365 Enterprise](m365-enterprise-test-lab-guides.md)

[Distribuzione di Microsoft 365 Enterprise](deploy-microsoft-365-enterprise.md)

[Documentazione di Microsoft 365 Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
