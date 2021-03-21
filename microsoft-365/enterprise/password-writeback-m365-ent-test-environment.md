---
title: Writeback della password per l'ambiente di testing di Microsoft 365
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/22/2019
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
description: "Riepilogo: configurare il writeback della password per l'ambiente di testing di Microsoft 365."
ms.openlocfilehash: f1118c22ad1f65ea29bb14afacb7506a60d1fe1a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921481"
---
# <a name="password-writeback-for-your-microsoft-365-test-environment"></a>Writeback della password per l'ambiente di testing di Microsoft 365

*Questa guida al laboratorio di testing può essere utilizzata solo per gli ambienti di testing di Microsoft 365 per le aziende.*

Gli utenti possono usare il writeback delle password per aggiornare le password tramite Azure Active Directory (Azure AD), che viene quindi replicato in Servizi di dominio Active Directory (AD DS) locale. Con il writeback delle password, gli utenti non devono aggiornare le password tramite Servizi di dominio Active Directory locale in cui sono archiviati gli account utente originali. Ciò consente agli utenti mobili o remoti che non dispongono di una connessione di accesso remoto alla rete locale.

In questo articolo viene descritto come configurare l'ambiente di testing di Microsoft 365 per il writeback delle password.

La configurazione dell'ambiente di testing per il writeback delle password prevede due fasi:
- [Fase 1: configurare la sincronizzazione hash delle password per l'ambiente di testing di Microsoft 365](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [Fase 2: abilitare il writeback delle password per il dominio TESTLAB Active Directory Domain Services.](#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain)
  
![Guide al lab di test per il cloud Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Per una mappa visiva a tutti gli articoli nello stack guida del laboratorio di testing di Microsoft 365 per le aziende, passare a [Microsoft 365 per enterprise Test Lab Guide Stack.](../downloads/Microsoft365EnterpriseTLGStack.pdf)

## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Fase 1: configurare la sincronizzazione hash delle password per l'ambiente di testing di Microsoft 365

Prima di tutto, seguire le istruzioni in [Sincronizzazione hash password](password-hash-sync-m365-ent-test-environment.md). La configurazione risultante è simile alla seguente:
  
![L'organizzazione simulata con ambiente di testing per la sincronizzazione hash delle password](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
Questa configurazione è costituita da:
  
- Un abbonamento di valutazione o a pagamento a Microsoft 365 E5.
- Intranet dell'organizzazione semplificata connessa a Internet, costituita da macchine virtuali DC1, APP1 e CLIENT1 in una subnet di una rete virtuale di Azure.
- Azure AD Connect viene eseguito su APP1 per sincronizzare il dominio TESTLAB di Active Directory Domain Services con il tenant di Azure AD dell'abbonamento a Microsoft 365.

## <a name="phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain"></a>Fase 2: abilitare il writeback delle password per il dominio TESTLAB Active Directory Domain Services.

Per iniziare, configurare l'account utente 1 con il ruolo amministratore globale.

1. Dall’[Interfaccia di amministrazione di Microsoft 365](https://portal.microsoft.com), accedere con l'account di amministratore globale.

2. Selezionare **Utenti attivi**.
 
3. Nella pagina **Utenti attivi** selezionare l'account **user1,**

4. Nel riquadro **user1** selezionare **Modifica** accanto a **Ruoli**.

5. Nel riquadro **Modifica ruoli utente** per utente1 selezionare Amministratore **globale,** **salva** e **quindi** chiudi.

Quindi, configurare l'account Utente 1 con le impostazioni di sicurezza che gli consentono di cambiare le password per conto di altri utenti nel dominio TESTLAB Active Directory Domain Services.

1. Dal [portale di Azure](https://portal.azure.com), accedere con l'account di amministratore globale e connettersi ad APP1 con l'account TESTLAB\Utente1.

2. Dal desktop di APP1, selezionare **Start**, immettere **active** e quindi selezionare **Utenti e computer di Active Directory**.

3. Sulla barra dei menu selezionare **Visualizza**. Se **funzionalità avanzate** non è abilitata, selezionarla per abilitarla.

4. Nel riquadro dell'albero, selezionare e tenere premuto (o fare clic con il pulsante destro del mouse) sul dominio, selezionare **Proprietà** e quindi selezionare la **scheda** Sicurezza.

5. Selezionare **Avanzate**.

6. Nella scheda **Autorizzazioni** selezionare **Aggiungi**.

7. Selezionare **Selezionare un'entità,** immettere **User1** e quindi selezionare **OK.**

8. In **Si applica a**, selezionare **Oggetti utente discendenti**.

9. In **Autorizzazioni**, selezionare le opzioni seguenti:

    - **Cambia password**
    - **Reimpostare la password**

10. In **Proprietà**, selezionare le opzioni seguenti:
    - **Scrittura lockoutTime**
    - **Scrittura pwdLastSet**

11. Selezionare **OK** tre volte per salvare le modifiche.

12. Chiudere **Utenti e computer di Active Directory**.

Successivamente, configurare Azure AD Connect su APP1 per il writeback delle password.

1. Se necessario, connettersi ad APP1 con l'account TESTLAB\Utente1.

2. Dal desktop di APP1, fare doppio clic su **Azure AD Connect**.

3. Nella pagina **iniziale selezionare** **Configura**.

4. Nella pagina **Attività aggiuntive** selezionare Personalizza opzioni **di sincronizzazione** e **quindi** avanti .

5. Nella pagina **Connetti ad Azure AD** immetti le credenziali dell'account amministratore globale e quindi seleziona **Avanti.**

6. Nelle pagine **Connect directories** and **Domain/OU filtering** selezionare **Next.**

7. Nella pagina **Funzionalità facoltative** selezionare **Writeback password** e **quindi** avanti .

8. Nella pagina **Pronto per la configurazione** selezionare **Configura** e attendere il completamento del processo.

9. Al termine della configurazione, selezionare **Esci.**

A questo punto è possibile testare il writeback delle password per gli utenti di computer che non sono connessi alla rete virtuale della rete Intranet simulata.

La configurazione risultante è simile alla seguente:

![L'organizzazione simulata con ambiente di testing per l'autenticazione pass-through](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)

Questa configurazione è costituita da:

- Una versione di valutazione di Microsoft 365 E5 o sottoscrizioni a pagamento con il dominio DNS TESTLAB.\<*your domain name*> registrato.
- Intranet dell'organizzazione semplificata connessa a Internet, costituita da macchine virtuali DC1, APP1 e CLIENT1 in una subnet di una rete virtuale di Azure.
- Azure AD Connect viene eseguito su APP1 per sincronizzare l'elenco di account e gruppi dal tenant di Azure AD dell'abbonamento a Microsoft 365 al dominio TESTLAB di Active Directory Domain Services.
- Il writeback delle password è abilitato in modo che gli utenti possono modificare la password tramite Azure AD senza dover essere connessi alla rete intranet semplificata.

## <a name="next-step"></a>Passaggio successivo

Esplorare altre caratteristiche e funzionalità [identità](m365-enterprise-test-lab-guides.md#identity) nell'ambiente di test.

## <a name="see-also"></a>Vedere anche

[Guide ai lab di test di Microsoft 365 per le aziende](m365-enterprise-test-lab-guides.md)

[Panoramica di Microsoft 365 per le aziende](microsoft-365-overview.md)

[Documentazione di Microsoft 365 for enterprise](/microsoft-365-enterprise/)