---
title: Autenticazione pass-through per l'ambiente di testing di Microsoft 365
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
- TLG
- Ent_TLGs
ms.assetid: ''
description: "Riepilogo: configurare l'autenticazione pass-through per l'ambiente di testing di Microsoft 365."
ms.openlocfilehash: d83de4ece4d1eaeddac882cf46a4fe85b8ba7cd4
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487447"
---
# <a name="pass-through-authentication-for-your-microsoft-365-test-environment"></a>Autenticazione pass-through per l'ambiente di testing di Microsoft 365

*Questa guida del laboratorio di testing può essere utilizzata per ambienti di testing Microsoft 365 per Enterprise e Office 365 Enterprise.*

Le organizzazioni che vogliono usare direttamente l'infrastruttura di Active Directory Domain Services locale per l'autenticazione per le applicazioni e servizi basati sul cloud di Microsoft, possono usare l'autenticazione pass-through. In questo articolo viene descritto come configurare l'ambiente di testing di Microsoft 365 per l'autenticazione pass-through, con la seguente configurazione come risultato:
  
![L'organizzazione simulata con ambiente di testing per l'autenticazione pass-through](../media/pass-through-auth-m365-ent-test-environment/Phase2.png)
  
Le fasi principali della configurazione dell'ambiente di testing sono tre:

1.    Creare l'ambiente di testing dell'organizzazione simulata di Microsoft 365 con per la sincronizzazione hash delle password.
2.    Configurare Azure AD Connect su APP1 per l'autenticazione pass-through.
    
![Guide del laboratorio di testing per il cloud Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Fare clic [qui](../downloads/Microsoft365EnterpriseTLGStack.pdf) per consultare una mappa di tutti gli articoli disponibili nella serie di guide al lab di test di Microsoft 365 per le aziende.
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Fase 1: configurare la sincronizzazione hash delle password per l'ambiente di testing di Microsoft 365

Seguire le istruzioni riportate in [sincronizzazione hash delle password per Microsoft 365](password-hash-sync-m365-ent-test-environment.md). Di seguito è riportata la configurazione risultante.
  
![L'organizzazione simulata con ambiente di testing per la sincronizzazione hash delle password](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
Questa configurazione è costituita da: 
  
- Microsoft 365 E5 o sottoscrizione a pagamento.
- Una intranet dell’organizzazione semplificata connessa a Internet e costituita dalle macchine virtuali DC1 APP1 e CLIENT1 in una sottorete di una rete virtuale Azure. Azure AD Connect viene eseguito su APP1 per sincronizzare periodicamente il dominio TESTLAB di Active Directory Domain Services con il tenant di Azure AD dell'abbonamento a Microsoft 365.

## <a name="phase-2-configure-azure-ad-connect-on-app1-for-pass-through-authentication"></a>Fase 2: configurare Azure AD Connect su APP1 per l'autenticazione pass-through

Questa fase riguarda la configurazione di Azure AD Connect su APP1 per l'uso dell'autenticazione pass-through e verificare che funzioni.

### <a name="configure-azure-ad-connect-on-app1"></a>Configurare Azure AD Connect su APP1

1.    Dal [portale di Azure](https://portal.azure.com), accedere con l'account di amministratore globale e connettersi ad APP1 con l'account TESTLAB\User1.

2.    Dal desktop di APP1, eseguire Azure AD Connect.

3.    Nella **Pagina di benvenuto** fare clic su **Configura**.

4.    Nella pagina Attività addizionali fare clic su **Cambia l'accesso utente**, quindi su **Avanti**.

5.    Nella pagina **Connessione ad Azure AD**, digitare le credenziali dell'account amministratore globale e fare clic su **Avanti**.

6.    Nella pagina **Accesso utente** fare clic su **Autenticazione pass-through**, quindi su **Avanti**.

7.    Nella pagina **Pronto per la configurazione** fare clic su **Configura**.

8.    Nella pagina **Configurazione completata**, fare clic su **Esci**.

9.    Dal portale di Azure, nel riquadro sinistro, fare clic su **Azure Active Directory > Azure AD Connect**. Verificare che la funzionalità **Autenticazione pass-through** venga visualizzata come **Attivata**.

10.    Fare clic su **Autenticazione pass-through**. Nel riquadro **Autenticazione pass-through** sono elencati i server in cui sono installati gli Agenti di autenticazione. APP1 sarà presente nell'elenco. Chiudere il riquadro **Autenticazione pass-through**.

Successivamente, verificare la possibilità di accedere all'abbonamento con il <strong>User1@testlab.</strong>\<your public domain> per l’account User1.

1. Da APP1, disconnettersi e quindi accedere nuovamente specificando un account diverso.

2. Quando vengono richiesti nome utente e password, specificare <strong>user1@testlab.</strong>\<your public domain> e la password User1. Dovrebbe essere possibile accedere come User1.

Si noti che sebbene User1 disponga di autorizzazioni di amministratore di dominio per il dominio TESTLAB AD DS, non è un amministratore globale. Di conseguenza, l'icona **Amministratore** non sarà visibile.

Di seguito è riportata la configurazione risultante:

![L'organizzazione simulata con ambiente di testing per l'autenticazione pass-through](../media/pass-through-auth-m365-ent-test-environment/Phase2.png)
 
Questa configurazione è costituita da:

- Una versione di valutazione di Microsoft 365 E5 o abbonamenti a pagamento con dominio DNS testlab.\<your domain name> registrato.
- Una intranet dell'organizzazione semplificata connessa a Internet e costituita dalle macchine virtuali DC1, APP1 e CLIENT1 in una sottorete di una rete virtuale Azure. Un Agente di autenticazione viene eseguito su APP1 per gestire le richieste di autenticazione pass-through dal tenant di Azure AD dell'abbonamento a Microsoft 365.

## <a name="next-step"></a>Passaggio successivo

Esplorare altre caratteristiche e funzionalità [identità](m365-enterprise-test-lab-guides.md#identity) nell'ambiente di test.

## <a name="see-also"></a>Vedere anche

[Guide ai lab di test di Microsoft 365 per le aziende](m365-enterprise-test-lab-guides.md)

[Panoramica di Microsoft 365 per le aziende](microsoft-365-overview.md)

[Microsoft 365 per la documentazione relativa all'organizzazione](https://docs.microsoft.com/microsoft-365-enterprise/)
