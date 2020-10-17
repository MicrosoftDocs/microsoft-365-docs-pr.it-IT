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
ms.openlocfilehash: b999d50b0e98b11638199327bd7ffe7269b261ce
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487129"
---
# <a name="password-writeback-for-your-microsoft-365-test-environment"></a>Writeback della password per l'ambiente di testing di Microsoft 365

*Questa guida del laboratorio di testing può essere utilizzata solo per Microsoft 365 per gli ambienti di testing dell'organizzazione.*

Gli utenti possono utilizzare il writeback delle password per aggiornare le proprie password tramite Azure Active Directory (Azure AD), che viene quindi replicato nei servizi di dominio Active Directory locali (AD DS). Con il writeback delle password, gli utenti non devono aggiornare le proprie password tramite il servizio di dominio Active Directory locale in cui sono archiviati gli account utente originali. Questo consente agli utenti di roaming o remoti che non dispongono di una connessione di accesso remoto alla rete locale.

In questo articolo viene descritto come configurare l'ambiente di testing di Microsoft 365 per il writeback delle password.

La configurazione dell'ambiente di testing per il writeback delle password comporta due fasi:
- [Fase 1: configurare la sincronizzazione hash delle password per l'ambiente di testing di Microsoft 365](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [Fase 2: abilitare il writeback delle password per il dominio TESTLAB Active Directory Domain Services.](#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain)
  
![Guide al lab di test per il cloud Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Per una mappa visiva su tutti gli articoli della guida del laboratorio di testing di Microsoft 365 for Enterprise, accedere a [microsoft 365 per la guida dello stack del laboratorio di testing dell'organizzazione](../downloads/Microsoft365EnterpriseTLGStack.pdf).

## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Fase 1: configurare la sincronizzazione hash delle password per l'ambiente di testing di Microsoft 365

Per prima cosa, seguire le istruzioni riportate in [sincronizzazione hash delle password](password-hash-sync-m365-ent-test-environment.md). La configurazione risultante è simile alla seguente:
  
![L'organizzazione simulata con ambiente di testing per la sincronizzazione hash delle password](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
Questa configurazione è costituita da:
  
- Un abbonamento di valutazione o a pagamento a Microsoft 365 E5.
- Una Intranet dell'organizzazione semplificata connessa a Internet, costituita dalle macchine virtuali DC1, APP1 e CLIENT1 in una subnet di una rete virtuale di Azure.
- Azure AD Connect viene eseguito su APP1 per sincronizzare il dominio TESTLAB di Active Directory Domain Services con il tenant di Azure AD dell'abbonamento a Microsoft 365.

## <a name="phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain"></a>Fase 2: abilitare il writeback delle password per il dominio TESTLAB Active Directory Domain Services.

Per iniziare, configurare l'account utente 1 con il ruolo amministratore globale.

1. Dall’[Interfaccia di amministrazione di Microsoft 365](https://portal.microsoft.com), accedere con l'account di amministratore globale.

2. Selezionare **utenti attivi**.
 
3. Nella pagina **utenti attivi** selezionare l'account **User1**

4. Nel riquadro **User1** selezionare **modifica** accanto a **ruoli**.

5. Nel riquadro **Modifica ruoli utente** per User1, selezionare **amministratore globale**, fare clic su **Salva**, quindi selezionare **Chiudi**.

Quindi, configurare l'account Utente 1 con le impostazioni di sicurezza che gli consentono di cambiare le password per conto di altri utenti nel dominio TESTLAB Active Directory Domain Services.

1. Dal [portale di Azure](https://portal.azure.com), accedere con l'account di amministratore globale e connettersi ad APP1 con l'account TESTLAB\Utente1.

2. Dal desktop di APP1, selezionare **Start**, immettere **Active**, quindi selezionare **utenti e computer di Active Directory**.

3. Sulla barra dei menu, selezionare **Visualizza**. Se **funzionalità avanzate** non è abilitata, selezionarla per abilitarla.

4. Nel riquadro dell'albero, seleziona e tieni premuto (o fai clic con il pulsante destro del mouse) sul dominio, seleziona **Proprietà**e quindi seleziona la scheda **sicurezza** .

5. Selezionare **Avanzate**.

6. Nella scheda **autorizzazioni** selezionare **Aggiungi**.

7. Selezionare **Seleziona un'entità**, immettere **User1**e quindi fare clic su **OK**.

8. In **Si applica a**, selezionare **Oggetti utente discendenti**.

9. In **Autorizzazioni**, selezionare le opzioni seguenti:

    - **Cambia password**
    - **Reimpostare la password**

10. In **Proprietà**, selezionare le opzioni seguenti:
    - **Scrittura lockoutTime**
    - **Scrittura pwdLastSet**

11. Selezionare tre volte **OK** per salvare le modifiche.

12. Chiudere **Utenti e computer di Active Directory**.

Successivamente, configurare Azure AD Connect su APP1 per il writeback delle password.

1. Se necessario, connettersi ad APP1 con l'account TESTLAB\Utente1.

2. Dal desktop di APP1, fare doppio clic su **Azure AD Connect**.

3. Nella **pagina iniziale**, selezionare **Configura**.

4. Nella pagina **attività aggiuntive** selezionare Personalizza le **Opzioni di sincronizzazione**, quindi fare clic su **Avanti**.

5. Nella pagina **connessione ad Azure ad** , immettere le credenziali dell'account amministratore globale e quindi fare clic su **Avanti**.

6. Nelle pagine **Connect Directories** and **Domain/ou Filtering** fare clic su **Avanti**.

7. Nella pagina **funzionalità facoltative** , selezionare **writeback password**e quindi fare clic su **Avanti**.

8. Nella pagina **pronto per la configurazione** , selezionare **Configura** e attendere il completamento del processo.

9. Quando viene visualizzata la configurazione finale, selezionare **Esci**.

È ora possibile testare il writeback delle password per gli utenti nei computer che non sono connessi alla rete virtuale della Intranet simulata.

La configurazione risultante è simile alla seguente:

![L'organizzazione simulata con ambiente di testing per l'autenticazione pass-through](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)

Questa configurazione è costituita da:

- Una versione di valutazione di Microsoft 365 E5 o abbonamenti a pagamento con dominio DNS TESTLAB.\<*your domain name*> registrato.
- Una Intranet dell'organizzazione semplificata connessa a Internet, costituita dalle macchine virtuali DC1, APP1 e CLIENT1 in una subnet di una rete virtuale di Azure.
- Azure AD Connect viene eseguito su APP1 per sincronizzare l'elenco di account e gruppi dal tenant di Azure AD dell'abbonamento a Microsoft 365 al dominio TESTLAB di Active Directory Domain Services.
- Il writeback delle password è abilitato in modo che gli utenti possono modificare la password tramite Azure AD senza dover essere connessi alla rete intranet semplificata.

## <a name="next-step"></a>Passaggio successivo

Esplorare altre caratteristiche e funzionalità [identità](m365-enterprise-test-lab-guides.md#identity) nell'ambiente di test.

## <a name="see-also"></a>Vedere anche

[Guide ai lab di test di Microsoft 365 per le aziende](m365-enterprise-test-lab-guides.md)

[Panoramica di Microsoft 365 per le aziende](microsoft-365-overview.md)

[Microsoft 365 per la documentazione relativa all'organizzazione](https://docs.microsoft.com/microsoft-365-enterprise/)


