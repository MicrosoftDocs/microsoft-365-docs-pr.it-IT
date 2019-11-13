---
title: Distribuzione di Windows 10 Enterprise per nuovi dispositivi con Windows Autopilot
description: Vengono fornite indicazioni per la configurazione e la distribuzione di Windows 10 Enterprise con Windows Autopilot.
keywords: Microsoft 365, Microsoft 365 Enterprise, Microsoft 365 Documentation, Windows 10 Enterprise, Deployment, Windows Autopilot
author: greg-lindsay
localization_priority: Normal
ms.collection: M365-modern-desktop
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 08/30/2018
ms.author: greglin
ms.openlocfilehash: 244aa9a2749c41471760c5263a6df6d745e5ade6
ms.sourcegitcommit: 9083036e787cf997fbceb19c66af594d0fa81d0f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/13/2019
ms.locfileid: "38302943"
---
# <a name="step-3-deploy-windows-10-enterprise-for-new-devices-with-windows-autopilot"></a>Passaggio 3: distribuzione di Windows 10 Enterprise per nuovi dispositivi con Windows Autopilot

*Questo articolo si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*

![Fase 3: Windows 10 Enterprise](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

Se si dispone di nuovi PC con Windows 10, è possibile usare Windows Autopilot per personalizzare l'esperienza di utilizzo della casella di controllo (OOBE) per l'organizzazione e distribuire un nuovo sistema con le app e le impostazioni già configurate. Non ci sono immagini da distribuire, nessun driver da iniettare e nessuna infrastruttura da gestire. Gli utenti possono passare attraverso il processo di distribuzione in modo indipendente, senza che sia necessario consultare l'amministratore IT.

È possibile impostare e preconfigurare nuovi dispositivi Windows 10 e prepararli per l'uso produttivo tramite il programma automatico di Windows. Per ulteriori informazioni su Windows Autopilot, inclusi i vantaggi e gli scenari di Windows Autopilot, vedere [Overview of Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-Autopilot/windows-10-Autopilot). Quando pronto, segui queste parti per iniziare a configurare nuovi dispositivi.

## <a name="the-windows-autopilot-deployment-process-poster"></a>Manifesto del processo di distribuzione di Windows Autopilot

Il poster di Windows Autopilot è costituito da due pagine in modalità verticale (11x17). Fare clic sull'immagine seguente per visualizzare un file PDF nel browser. 

[![Distribuzione di Windows 10 con il poster di Autopilot](./media/windows10-deploy-autopilot/windows10-autopilot-flowchart.png)](https://opdhsblobprod04.blob.core.windows.net/contents/d0d41f25ce48460387a79ace64acad6b/d00f8fc01db0b512e4953663c8331588?sv=2015-04-05&sr=b&sig=RWOcP%2BhJZYpYcGKMhuTUEL6lcuWdBFefqR%2BQQfmj6IM%3D&st=2019-11-12T23%3A48%3A59Z&se=2019-11-13T23%3A58%3A59Z&sp=r)

È anche possibile scaricare il poster in formato[PDF](https://github.com/MicrosoftDocs/windows-itpro-docs/raw/public/windows/deployment/media/Windows10AutopilotFlowchart.pdf) o [Visio](https://github.com/MicrosoftDocs/windows-itpro-docs/raw/public/windows/deployment/media/Windows10Autopilotflowchart.vsdx).

## <a name="part-1-start-windows-autopilot-deployment"></a>Parte 1: avviare la distribuzione di Windows Autopilot
Vedere [Overview of Windows Autopilot](https://docs.microsoft.com/windows/deployment/windows-Autopilot/windows-10-Autopilot) to:

1. Informazioni su e su come completare i prerequisiti per la distribuzione di Windows Autopilot. I prerequisiti includono:
    - **Registrazione del dispositivo e personalizzazione Configurazione guidata**

        Per registrare i dispositivi, è necessario acquisire l'ID hardware e registrarlo. Stiamo lavorando attivamente con vari fornitori di hardware per consentire loro di fornire le informazioni necessarie o di caricarle per conto di voi. È inoltre possibile acquisire queste informazioni utilizzando uno script di PowerShell che genera un file CSV con l'ID hardware del dispositivo.

        Dopo la registrazione dei dispositivi, è possibile configurare le opzioni di personalizzazione di OOBE, tra cui le impostazioni di privacy ignorate e l'EULA.

    - **Informazioni personalizzate distintive dell'azienda per Configurazione guidata**

        In questo modo è possibile aggiungere il marchio all'utente durante la configurazione guidata del dispositivo.

    - **Registrazione automatica MDM in Microsoft Intune**
        
        La registrazione automatica consente agli utenti di registrare i propri dispositivi Windows 10 in Intune per la gestione dei dispositivi quando collegano i propri dispositivi ad Azure AD. Per eseguire la registrazione, gli utenti aggiungono il proprio account di lavoro ai propri dispositivi personali o uniscono i dispositivi aziendali a Azure AD. In background, il dispositivo viene inoltre registrato per la gestione con Intune.

    - **Connettività di rete ai servizi cloud utilizzati da Windows Autopilot**

        Il programma di distribuzione di Windows Autopilot utilizza una serie di servizi cloud per ottenere i dispositivi a uno stato produttivo e questi servizi devono essere accessibili da dispositivi registrati come dispositivi Autopilot di Windows. 

    - **Dispositivi preinstallati con Windows 10, versione 1703 o successiva**

2. Informazioni su e selezionare il programma di distribuzione Autopilot di Windows per l'organizzazione. È possibile selezionare una delle seguenti applicazioni di distribuzione:
    - **Microsoft Store for Business**
    - **Microsoft Intune**
    - **Centro partner**

## <a name="part-2-set-up-a-windows-10-device-for-microsoft-365"></a>Parte 2: configurare un dispositivo Windows 10 per Microsoft 365
Prima di poter configurare i dispositivi Windows per gli utenti di Microsoft 365, verificare che tutti i dispositivi Windows eseguano Windows 10, versione 1703 (creatori Update) o versioni successive.

Dopo che tutti i dispositivi Windows nell'organizzazione sono stati aggiornati all'aggiornamento di Windows 10 Creator o sono già in esecuzione l'aggiornamento di Windows 10 Creator, è possibile aggiungere questi dispositivi all'Azure Active Directory dell'organizzazione.

### <a name="set-up-a-brand-new-or-newly-upgraded-windows-10-device"></a>Configurare un dispositivo Windows 10 nuovo o aggiornato di recente
Seguire questa procedura per configurare un dispositivo utilizzando il file OOBE di Windows 10 su un dispositivo nuovo di zecca che esegue l'aggiornamento di Windows 10 Creator (o versioni successive) o su un dispositivo che è stato eseguito l'aggiornamento a Windows 10 Creator Update (o versioni successive), ma non è stata eseguita la configurazione fuori campo.

1. Se non si dispone di una rete wireless configurata, assicurarsi di connettere il dispositivo a Internet tramite una connessione cablata o Ethernet.
2. Passare all'esperienza di installazione dei dispositivi di Windows. Su un dispositivo nuovo o reimpostare, l'esperienza di installazione inizia con l' **area inizia con. È vero?** schermata.
3. Seguire la procedura di installazione di Windows 10 finché non viene visualizzata la pagina **Che configurazione vuoi eseguire?**. In questa sezione, selezionare **Configura per un'organizzazione**.
4. Accedere utilizzando l'account e la password dell'utente di Microsoft 365. A seconda dell'impostazione della password utente, potrebbe essere richiesto di aggiornare la password. 
5. Completare la configurazione del dispositivo con Windows 10.

Al termine, il dispositivo verrà connesso all'Azure AD dell'organizzazione.

### <a name="set-up-a-device-that-has-already-completed-out-of-box-setup"></a>Configurare un dispositivo che ha già completato l'installazione fuori campo
Se nel dispositivo è installato Windows 10 Creator (o versioni successive) ed è già stata eseguita la configurazione fuori sede, attenersi alla seguente procedura.

1. Nel PC Windows dell'utente che esegue Windows 10, versione 1703 (Creators Update), selezionare il logo di **Windows** , quindi selezionare l'icona **Impostazioni** .
2. In **Impostazioni** passare ad **Account**.
3. Nella pagina delle **informazioni** selezionare **Access Work o School** > **Connect**.
4. Nella finestra di dialogo **configura un account aziendale o dell'Istituto di istruzione** , in **azioni alternative**, selezionare **Unisci questo dispositivo ad Azure Active Directory**.
5. Nella pagina **Let ' s Get You signed in** , immettere l'account aziendale o dell'Istituto di istruzione, quindi fare clic su **Avanti**.
6. Nella pagina **immettere la password** , immettere la password, quindi selezionare **Accedi**.
7. Nella pagina controlla che **sia la tua organizzazione** , verifica che le informazioni siano corrette e seleziona **Unisci**.
8. Sul **è tutto pronto!** pagina fare clic su **fine**.

Al termine dell'operazione, l'utente sarà connesso all'Azure AD dell'organizzazione.

### <a name="verify-the-device-is-connected-to-azure-ad"></a>Verificare che il dispositivo sia connesso a Azure AD
Seguire questa procedura per verificare lo stato di sincronizzazione del dispositivo con Azure AD e quindi iniziare a usare l'account Microsoft 365 sul dispositivo. 

1. Aprire **le impostazioni**.
2. Nella pagina **Access Work or School** selezionare l'area **connessa a <organization name> ** per esporre i pulsanti **info** e **Disconnetti**.
3. Selezionare **info** per ottenere lo stato di sincronizzazione.
4. Nella pagina **stato sincronizzazione** selezionare **Sincronizza** per ottenere i criteri di gestione dei dispositivi mobili più recenti nel PC.
5. Per iniziare a usare l'account Microsoft 365, passare al pulsante **Start** di Windows, fare clic con il tasto destro del mouse sull'immagine dell'account corrente e quindi scegliere **Cambia** account.
6. Accedere usando l'indirizzo di posta elettronica e la password della propria organizzazione.

Se si verificano problemi durante l'utilizzo di Windows 10 in un ambiente aziendale, è possibile consultare [le principali soluzioni di supporto tecnico Microsoft per i problemi più comuni](https://docs.microsoft.com/windows/client-management/windows-10-support-solutions). Tali risorse includono articoli, aggiornamenti e articoli relativi alla raccolta di KB.

Come checkpoint provvisorio, vedere i [criteri di completamento](windows10-exit-criteria.md#crit-windows10-step3) relativi a questo passaggio.

## <a name="next-step"></a>Passaggio successivo

|||
|:-------|:-----|
|![Passaggio 4](./media/stepnumbers/Step4.png)| [Monitorare l'integrità e la conformità del dispositivo](windows10-enable-windows-analytics.md) |
