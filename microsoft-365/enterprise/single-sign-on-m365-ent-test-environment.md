---
title: Azure AD Seamless Single Sign-On per l'ambiente di testing di Microsoft 365
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/21/2019
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
description: "Riepilogo: informazioni sulla configurazione e sul test di Azure AD Seamless Single Sign-On per l'ambiente di testing di Microsoft 365."
ms.openlocfilehash: f98f82de50feb2a9f92d1ecc4775c5307b314a72
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487607"
---
# <a name="azure-ad-seamless-single-sign-on-for-your-microsoft-365-test-environment"></a>Azure AD Seamless Single Sign-On per l'ambiente di testing di Microsoft 365

*Questa guida del laboratorio di testing può essere utilizzata per ambienti di testing Microsoft 365 per Enterprise e Office 365 Enterprise.*

Azure AD seamless Single Sign-On (SSO senza soluzione di continuità) consente di firmare automaticamente gli utenti quando sono presenti nei propri PC o dispositivi connessi alla propria rete organizzativa. Azure AD seamless SSO fornisce agli utenti un facile accesso alle applicazioni basate su cloud senza bisogno di ulteriori componenti locali.

In questo articolo viene descritto come configurare l'ambiente di testing di Microsoft 365 per Azure AD seamless SSO.

La configurazione di Azure AD seamless SSO comporta due fasi:
- [Fase 1: configurare la sincronizzazione hash delle password per l'ambiente di testing di Microsoft 365](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [Fase 2: configurare Azure AD Connect su APP1 per Azure AD Seamless Single Sign-On](#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso)
   
![Guide del laboratorio di testing per il cloud Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Per una mappa visiva su tutti gli articoli della guida del laboratorio di testing di Microsoft 365 for Enterprise, accedere a [microsoft 365 per la guida dello stack del laboratorio di testing dell'organizzazione](../downloads/Microsoft365EnterpriseTLGStack.pdf).
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Fase 1: configurare la sincronizzazione hash delle password per l'ambiente di testing di Microsoft 365

Seguire le istruzioni riportate in [sincronizzazione hash delle password per Microsoft 365](password-hash-sync-m365-ent-test-environment.md). 

La configurazione risultante è simile alla seguente:
  
![L'organizzazione simulata con ambiente di testing per la sincronizzazione hash delle password](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
Questa configurazione è costituita da:
  
- Un abbonamento di valutazione o a pagamento a Microsoft 365 E5.
- Una Intranet dell'organizzazione semplificata connessa a Internet, costituita dalle macchine virtuali DC1, APP1 e CLIENT1 in una subnet di una rete virtuale di Azure.
- Azure AD Connect viene eseguito su APP1 per sincronizzare periodicamente il dominio servizi di dominio Active Directory di TESTLAB con il tenant di Azure AD della sottoscrizione Microsoft 365.

## <a name="phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso"></a>Fase 2: configurare Azure AD Connect su APP1 per Azure AD Seamless Single Sign-On

In questa fase, configurare Azure AD Connect su APP1 per Azure AD seamless SSO e quindi verificarne il funzionamento.

### <a name="configure-azure-ad-connect-on-app1"></a>Configurare Azure AD Connect su APP1

1. Dal [portale di Azure](https://portal.azure.com), accedere con l'account di amministratore globale e connettersi ad APP1 con l'account TESTLAB\User1.

2. Dal desktop di APP1, eseguire Azure AD Connect.

3. Nella **pagina iniziale**, selezionare **Configura**.

4. Nella pagina **attività aggiuntive** selezionare **Cambia accesso utente**e quindi fare clic su **Avanti**.

5. Nella pagina **connessione ad Azure ad** , immettere le credenziali dell'account amministratore globale e quindi fare clic su **Avanti**.

6. Nella pagina **di accesso dell'utente** , selezionare **Abilita Single Sign-on**, quindi fare clic su **Avanti**.

7. Nella pagina **Abilita Single Sign-on** selezionare **Enter credentials**.

8. Nella finestra di dialogo **sicurezza di Windows** , immettere **User1** e la password dell'account User1, selezionare **OK**, quindi fare clic su **Avanti**.

9. Nella pagina **pronto per la configurazione** , selezionare **Configure**.

10. Nella pagina **Configurazione completata** selezionare **Esci**.

11. Dal portale di Azure, nel riquadro sinistro, selezionare **Azure Active Directory**  >  **Azure ad Connect**. Verificare che la funzionalità **Single Sign-on** venga visualizzata come **abilitata**.

Successivamente, verificare la possibilità di accedere all'abbonamento con il <strong>User1@testlab.</strong>\<*your public domain*> per l’account User1.

1. Da Internet Explorer su APP1, selezionare l'icona Impostazioni, quindi selezionare **Opzioni Internet**.
 
2. In **Opzioni Internet**selezionare la scheda **sicurezza** .

3. Selezionare **Intranet locale**e quindi selezionare **siti**.

4. In **Intranet locale**, selezionare **Avanzate**.

5. In **Aggiungi questo sito Web all'area**, immettere **https<span>://</span>AutoLogon.microsoftazuread-SSO.com**, selezionare **Aggiungi**  >  **Chiudi**  >  **OK**  >  **OK**.

6. Disconnettersi e quindi accedere nuovamente specificando un account diverso.

7. Quando viene richiesto di eseguire l'accesso, specificare <strong>User1@testlab.</strong>\<*your public domain*> nome e quindi fare clic su **Avanti**. È quindi possibile accedere come User1 senza che venga richiesta una password. Ciò dimostra che Seamless SSO funziona correttamente.

Si noti che sebbene User1 disponga di autorizzazioni di amministratore di dominio per il dominio TESTLAB di Active Directory Domain Services, non è un amministratore globale per Azure AD. Di conseguenza, l'icona **Amministratore** non sarà visibile.

Di seguito è riportata la configurazione risultante:

![L'organizzazione simulata con ambiente di testing per l'autenticazione pass-through](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)

Questa configurazione è costituita da:

- Una versione di valutazione di Microsoft 365 E5 o abbonamenti a pagamento con dominio DNS testlab.\<*your domain name*> registrato.
- Una Intranet dell'organizzazione semplificata connessa a Internet, costituita dalle macchine virtuali DC1, APP1 e CLIENT1 in una subnet di una rete virtuale di Azure.
- Azure AD Connect viene eseguito su APP1 per sincronizzare l'elenco di account e gruppi dal tenant di Azure AD dell'abbonamento a Microsoft 365 al dominio TESTLAB di Active Directory Domain Services.
- Azure AD seamless SSO è abilitato in modo che i computer della rete Intranet simulata possano accedere alle risorse cloud di Microsoft 365 senza specificare una password per l'account utente.

## <a name="next-step"></a>Passaggio successivo

Esplorare altre caratteristiche e funzionalità [identità](m365-enterprise-test-lab-guides.md#identity) nell'ambiente di test.

## <a name="see-also"></a>Vedere anche

[Guide ai lab di test di Microsoft 365 per le aziende](m365-enterprise-test-lab-guides.md)

[Panoramica di Microsoft 365 per le aziende](microsoft-365-overview.md)

[Microsoft 365 per la documentazione relativa all'organizzazione](https://docs.microsoft.com/microsoft-365-enterprise/)
