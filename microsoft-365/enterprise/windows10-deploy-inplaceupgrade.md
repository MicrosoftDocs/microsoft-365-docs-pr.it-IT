---
title: Distribuire Windows 10 Enterprise per i dispositivi esistenti come aggiornamento sul posto
description: Vengono fornite indicazioni per la configurazione e la distribuzione di un'immagine di Windows 10 Enterprise tramite Microsoft endpoint Configuration Manager come aggiornamento sul posto.
keywords: Microsoft 365, Microsoft 365 Enterprise, Microsoft 365 Documentation, Windows 10 Enterprise, Deployment, upgrade sul posto, Configuration Manager, Configuration Manager
author: greg-lindsay
localization_priority: Normal
ms.collection: M365-modern-desktop
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 08/30/2018
f1.keywords:
- NOCSH
ms.author: greglin
ms.openlocfilehash: 0078931be23039dac3a323f4747494803d1acd4d
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "41602853"
---
# <a name="step-2-deploy-windows-10-enterprise-for-existing-devices-as-an-in-place-upgrade"></a>Passaggio 2: distribuire Windows 10 Enterprise per i dispositivi esistenti come aggiornamento sul posto

*Questo articolo si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise*

![Fase 3: Windows 10 Enterprise](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

Il percorso più semplice per aggiornare i computer che eseguono Windows 7 o Windows 8,1 a Windows 10 è tramite un aggiornamento sul posto. È possibile utilizzare una sequenza di attività di gestione configurazione (Configuration Manager) per automatizzare completamente il processo. 

Se sono presenti computer che eseguono Windows 7 o Windows 8,1, è consigliabile questo percorso se l'organizzazione sta distribuendo Windows 10. In questo modo viene utilizzato il programma di installazione di Windows (Setup. exe) per eseguire un aggiornamento sul posto, che consente di conservare automaticamente tutti i dati, le impostazioni, le applicazioni e i driver dalla versione del sistema operativo esistente. Questo richiede il minimo sforzo, perché non è necessaria alcuna infrastruttura di distribuzione complessa.

Eseguire la procedura seguente per configurare e distribuire un'immagine di Windows 10 Enterprise utilizzando Microsoft endpoint Configuration Manager come aggiornamento sul posto.

## <a name="the-windows-10-deployment-with-configuration-manager-poster"></a>Distribuzione di Windows 10 con il poster di Configuration Manager

Il poster di Configuration Manager è una pagina in modalità landscape (17x11). Fare clic sull'immagine seguente per visualizzare un file PDF nel browser. 

[![Distribuzione di Windows 10 con il poster di Configuration Manager](./media/windows10-deploy-inplaceupgrade/windows10-deployment-config-manager.png)](https://docs.microsoft.com/windows/deployment/media/Windows10DeploymentConfigManager.pdf)

È anche possibile scaricare il poster in formato[PDF](https://github.com/MicrosoftDocs/windows-itpro-docs/raw/public/windows/deployment/media/Windows10DeploymentConfigManager.pdf) o [Visio](https://github.com/MicrosoftDocs/windows-itpro-docs/raw/public/windows/deployment/media/Windows10DeploymentConfigManager.vsdx).

## <a name="part-1-verify-readiness-to-upgrade-windows"></a>Parte 1: verificare la disponibilità per l'aggiornamento di Windows

In primo luogo, utilizzare la funzionalità di preparazione per l'aggiornamento di Windows Analytics per fornire informazioni e suggerimenti utili sui computer, le applicazioni e i driver nell'organizzazione, senza costi aggiuntivi e con requisiti di infrastruttura aggiuntivi. Questo nuovo servizio guida l'utente attraverso l'aggiornamento e l'aggiornamento delle funzionalità dei progetti utilizzando un flusso di lavoro basato su procedure consigliate Microsoft. I dati di inventario aggiornati consentono di bilanciare i costi e i rischi nei progetti di aggiornamento.

Vedere [gestire gli aggiornamenti di Windows con la preparazione dell'aggiornamento](https://docs.microsoft.com/windows/deployment/upgrade/manage-windows-upgrades-with-upgrade-readiness) per ulteriori informazioni, per iniziare, utilizzare e risolvere i problemi relativi all'aggiornamento.

Successivamente, seguire la guida per l'utilizzo di Configuration Manager (Current Branch) per aggiornare il sistema operativo Windows 7 o versioni successive a Windows 10. Come per qualsiasi distribuzione ad alto rischio, è consigliabile eseguire il backup dei dati degli utenti prima di continuare. Lo spazio di archiviazione cloud di OneDrive è pronto per l'uso per gli utenti con licenza di Microsoft 365 e può essere utilizzato per archiviare in modo sicuro i propri file. Per altre informazioni, vedere [Guida](https://aka.ms/ODfBquickstartguide)introduttiva di OneDrive. Per accedere a questa pagina, è necessario eseguire l'accesso come amministratore del tenant o amministratore globale in un tenant di Office 365 o Microsoft 365.

Per un elenco delle versioni di Configuration Manager e delle versioni client di Windows 10 corrispondenti supportate, vedere [supporto per Windows 10 per Configuration Manager](https://docs.microsoft.com/configmgr/core/plan-design/configs/support-for-windows-10).

**Per verificare la disponibilità dell'aggiornamento di Windows**

Esaminare questi requisiti prima di avviare la distribuzione di Windows 10:

- **Edizioni di Windows idonee per l'aggiornamento** : i dispositivi devono eseguire edizioni di Windows 7 o Windows 8,1 che sono idonee per l'aggiornamento a Windows 10 Enterprise. Per un elenco delle edizioni supportate, vedere [percorsi di aggiornamento di Windows 10](https://aka.ms/win10upgradepaths). 
- **Dispositivi supportati** : la maggior parte dei computer compatibili con Windows 8,1 sarà compatibile con Windows 10. Potrebbe essere necessario installare i driver aggiornati in Windows 10 affinché i dispositivi funzionino correttamente. Per altre informazioni, vedere [specifiche di Windows 10](https://aka.ms/windows10specifications) .
- **Preparazione della distribuzione** : prima di iniziare a configurare la distribuzione, assicurarsi di avere la seguente procedura.
    - Supporto di installazione di Windows 10-il supporto di installazione deve trovarsi in un'unità distinta, con la ISO già montata. È possibile ottenere la ISO da [download abbonati MSDN](https://aka.ms/msdn-subscriber-downloads) o dal [centro servizi per contratti multilicenza](https://aka.ms/mvlsc).
    - Backup dei dati degli utenti-sebbene i dati dell'utente verranno migrati nell'aggiornamento, la procedura consigliata consiste nel configurare uno scenario di backup. Ad esempio, esportare tutti i dati degli utenti in un account OneDrive, BitLocker to go-Encrypted USB Flash Drive o network file server. Per ulteriori informazioni, vedere [eseguire il backup o il trasferimento dei dati in Windows](https://aka.ms/backuptransferdatawindows).
- **Preparazione dell'ambiente** : si utilizzerà una struttura del Server Configuration Manager esistente per preparare la distribuzione del sistema operativo. Oltre alla configurazione di base, è necessario effettuare le seguenti configurazioni nell'ambiente Configuration Manager:
    1. [Estendere lo schema di Active Directory](https://aka.ms/extendadschema) e [creare un contenitore di gestione del sistema](https://aka.ms/createsysmancontainer).
    2. Abilitare l'individuazione della foresta di Active Directory e l'individuazione del sistema di Active Directory. Per altre informazioni, vedere [Configure Discovery Methods for Configuration Manager](https://aka.ms/configurediscoverymethods).
    3. Creare confini dell'intervallo IP e gruppo di limiti per il contenuto e l'assegnazione del sito. Per altre informazioni, vedere [definire i limiti del sito e i gruppi di limiti per Configuration Manager](https://aka.ms/definesiteboundaries).
    4. Aggiungere e configurare il ruolo del punto di Reporting Services di Configuration Manager. Per altre informazioni, vedere [Configuring Reporting in Configuration Manager](https://aka.ms/configurereporting).
    5. Creare una struttura di cartelle di file System per i pacchetti.
    6. Creare una struttura di cartelle console di Configuration Manager per i pacchetti.
    7. Installare Configuration Manager (Current Branch) e gli eventuali ulteriori prerequisiti di Windows 10.

## <a name="part-2-add-a-windows-10-os-image-using-configuration-manager"></a>Parte 2: aggiungere un'immagine del sistema operativo Windows 10 tramite Configuration Manager
A questo punto è necessario creare un pacchetto di aggiornamento del sistema operativo che contenga il supporto di installazione completo di Windows 10. Nei passaggi seguenti viene utilizzato Configuration Manager per creare un pacchetto di aggiornamento per Windows 10 Enterprise x64.

**Per aggiungere un'immagine del sistema operativo Windows 10 tramite Configuration Manager**

1. Utilizzando la console di Configuration Manager, nell'area di lavoro **raccolta software** fare clic con il pulsante destro del mouse sul nodo **pacchetti di aggiornamento del sistema operativo** e quindi scegliere **Aggiungi pacchetto di aggiornamento del sistema operativo**.
2. Nella pagina **origine dati** specificare il percorso UNC del supporto Windows 10 Enterprise x64 e quindi fare clic su **Avanti**.
3. Nella pagina **generale** , specificare l' **aggiornamento di Windows 10 Enterprise x64**e quindi fare clic su **Avanti**. 
4. Nella pagina **Riepilogo** fare clic su **Avanti**e quindi su **Chiudi**. 
5. Fare clic con il pulsante destro del mouse sul pacchetto di **aggiornamento di Windows 10 Enterprise x64** creato e quindi scegliere **Distribuisci contenuto**. 
6. Scegliere il punto di distribuzione.

## <a name="part-3-configure-deployment-settings"></a>Parte 3: configurare le impostazioni di distribuzione
In questo passaggio verrà configurata una sequenza di attività di aggiornamento che contiene le impostazioni per l'aggiornamento di Windows 10. Verranno quindi identificati i dispositivi di cui eseguire l'aggiornamento e quindi la distribuzione della sequenza di attività in tali dispositivi.

### <a name="create-a-task-sequence"></a>Creare una sequenza di attività
Per creare una sequenza di attività di aggiornamento, eseguire le operazioni seguenti:
  
1. Nella console di Configuration Manager, nell'area di lavoro della **raccolta software** , espandere **sistemi operativi**. 
2. Fare clic con il pulsante destro del mouse sul nodo **sequenze attività** e quindi scegliere **Crea sequenza attività**.
3. Nella pagina **Crea una nuova sequenza di attività** , selezionare **Aggiorna un sistema operativo dal pacchetto di aggiornamento**, quindi fare clic su **Avanti**.
4. Nella pagina **informazioni sequenza attività** specificare l' **aggiornamento di Windows 10 Enterprise x64**e quindi fare clic su **Avanti**.
5. Nella pagina **aggiornare il sistema operativo Windows** , selezionare **Sfoglia** e scegliere il **pacchetto di aggiornamento di Windows 10 Enterprise x64 upgrade System**, selezionare **OK**, quindi fare clic su **Avanti**.
6. Continuare nelle pagine rimanenti della procedura guidata e quindi fare clic su **Chiudi**.

### <a name="create-a-device-collection"></a>Creare un insieme di dispositivi
Dopo aver creato la sequenza di attività di aggiornamento, sarà necessario creare una raccolta che contenga i dispositivi da aggiornare.

> [!NOTE]
> Utilizzare le impostazioni seguenti per testare la distribuzione su un singolo dispositivo. È possibile utilizzare regole di appartenenza diverse per includere gruppi di dispositivi quando si è pronti. Per altre informazioni, vedere [come creare raccolte in Configuration Manager](https://docs.microsoft.com/configmgr/core/clients/manage/collections/create-collections).

1. Nella console di Configuration Manager, nell'area di lavoro **asset e conformità** , fare clic con il pulsante destro del mouse su **Raccolte dispositivi**e quindi scegliere **Crea insieme di dispositivi**. 
2. Nella pagina **generale** della creazione guidata raccolta dispositivi immettere le impostazioni seguenti e quindi fare clic su **Avanti**:
    - Nome: aggiornamento di Windows 10 Enterprise x64
    - Limitazione della raccolta: tutti i sistemi
3. Nella pagina **regole di appartenenza** selezionare **Aggiungi** > regola**diretta** per avviare la creazione guidata regola di appartenenza diretta.
4. Nella pagina **iniziale** della procedura guidata Create Direct Membership Rule selezionare **Avanti**.
5. Nella pagina **Cerca risorse** immettere le impostazioni seguenti, sostituendo il testo del **valore** segnaposto con il nome del dispositivo che si sta aggiornando: 
    - Classe Resource: risorsa di sistema
    - Nome attributo: nome
    - Valore: *PC0003*
6. Nella pagina **Seleziona risorse** selezionare il dispositivo e quindi fare clic su **Avanti**.
7. Completare la procedura guidata Crea regola di appartenenza diretta e la procedura guidata Crea raccolta dispositivi.  
8. Esaminare la raccolta di aggiornamenti di Windows 10 Enterprise x64. Non continuare finché non vengono visualizzati i computer aggiunti nell'insieme.

### <a name="create-an-operating-system-deployment"></a>Creare una distribuzione del sistema operativo
Eseguire la procedura seguente per creare una distribuzione per la sequenza di attività.

1. Nella console di Configuration Manager, nell'area di lavoro **raccolta software** fare clic con il pulsante destro del mouse sulla sequenza di attività creata in un passaggio precedente e quindi scegliere **Distribuisci**.
2. Nella pagina **generale** selezionare la raccolta di **aggiornamento di Windows 10 Enterprise x64** e quindi fare clic su **Avanti**.
3. Nella pagina **contenuto** selezionare **Avanti**.
4. Nella pagina **impostazioni di distribuzione** , selezionare le impostazioni seguenti e quindi fare clic su **Avanti**:

    > [!NOTE]
    > Per la distribuzione dei test, è necessario impostare lo scopo di **available**, che richiede l'intervento dell'utente per avviare la distribuzione. In un ambiente di produzione, è possibile automatizzare la distribuzione utilizzando lo scopo necessario, che implica la configurazione di opzioni aggiuntive, ad esempio la pianificazione durante l'esecuzione della distribuzione. 

    - Azione: install
    - Scopo: disponibile

5. Nella pagina **pianificazione** accettare le impostazioni predefinite e quindi fare clic su **Avanti**.
6. Nella pagina **esperienza utente** , accettare le impostazioni predefinite e quindi fare clic su **Avanti**.
7. Nella pagina **avvisi** accettare le impostazioni predefinite e quindi fare clic su **Avanti**.
8. Nella pagina **Riepilogo** fare clic su **Avanti**e quindi su **Chiudi**.

## <a name="part-4-start-the-windows-10-upgrade-task-sequence"></a>Parte 4: avviare la sequenza di attività di aggiornamento di Windows 10
Eseguire la procedura seguente per avviare la sequenza di attività di aggiornamento di Windows 10 nel dispositivo che si sta aggiornando.
 
1. Accedere al computer Windows e avviare il **Centro software**.
2. Selezionare la sequenza di attività creata in un passaggio precedente e quindi fare clic su **Installa**.
3. Quando la sequenza di attività inizia, viene avviato automaticamente il processo di aggiornamento sul posto richiamando il programma di installazione di Windows (Setup. exe) con i parametri della riga di comando necessari per eseguire un aggiornamento automatico, che conserva tutti i dati, le impostazioni, le app e driver.
4. Una volta completata la sequenza di attività, il computer verrà aggiornato completamente a Windows 10.

Se si verificano problemi durante l'utilizzo di Windows 10 in un ambiente aziendale, è possibile consultare [le principali soluzioni di supporto tecnico Microsoft per i problemi più comuni](https://docs.microsoft.com/windows/client-management/windows-10-support-solutions). Tali risorse includono articoli, aggiornamenti e articoli relativi alla raccolta di KB.

Durante l'implementazione degli aggiornamenti all'interno dell'organizzazione, utilizzare la funzionalità di conformità dell'aggiornamento di Windows Analytics per fornire una visualizzazione olistica della conformità dell'aggiornamento del sistema operativo, dell'aggiornamento della distribuzione e della risoluzione dei problemi relativi ai dispositivi Windows 10. Questo nuovo servizio utilizza i dati di diagnostica, tra cui l'avanzamento dell'installazione, la configurazione di Windows Update e altre informazioni per fornire tali intuizioni, senza costi aggiuntivi e con requisiti infrastrutturali aggiuntivi. Se viene utilizzato con Windows Update for business o con altri strumenti di gestione, è possibile garantire che i dispositivi siano stati aggiornati correttamente.

Vedere [monitorare gli aggiornamenti di Windows e Windows Defender antivirus con la conformità](https://docs.microsoft.com/windows/deployment/update/update-compliance-monitor) degli aggiornamenti per ulteriori informazioni, per iniziare e utilizzare la conformità dell'aggiornamento.

Come checkpoint provvisorio, vedere i [criteri di completamento](windows10-exit-criteria.md#crit-windows10-step2) relativi a questo passaggio.

## <a name="next-step"></a>Passaggio successivo

|||
|:-------|:-----|
|![Passaggio 3](./media/stepnumbers/Step3.png)| [Distribuzione di Windows 10 Enterprise per nuovi dispositivi con Windows Autopilot](windows10-deploy-autopilot.md) |
