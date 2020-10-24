---
title: Distribuzione di Microsoft 365 Apps for enterprise per Contoso
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: Informazioni sul modo in cui Contoso usa Microsoft Endpoint Configuration Manager per distribuire Microsoft 365 Apps for enterprise.
ms.openlocfilehash: 2c02c28ddba7c24592ce09d87bf6f5c9df700a2a
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754345"
---
# <a name="microsoft-365-apps-for-enterprise-deployment-for-contoso"></a>Distribuzione di Microsoft 365 Apps for enterprise per Contoso

Contoso ha aggiornato i propri PC a Windows 10 Enterprise e Microsoft 365 Apps for Enterprise per consentire una collaborazione più efficace, una maggiore sicurezza e un'esperienza desktop più moderna. Dopo aver valutato la propria infrastruttura e le proprie esigenze aziendali, Contoso ha identificato i requisiti fondamentali per la distribuzione:

- Tutti i PC devono eseguire le app Microsoft 365 per Enterprise.
- Quando possibile, la distribuzione deve utilizzare gli strumenti di gestione e l'infrastruttura esistenti.
- La distribuzione deve supportare più lingue e architetture esistenti nei dispositivi degli utenti.
- I PC devono rimanere aggiornati e sicuri con costi amministrativi IT minimi e un impatto minimo per gli utenti.

## <a name="deployment-tools"></a>Strumenti di distribuzione

In base ai propri requisiti, Contoso ha scelto di distribuire Windows 10 Enterprise e Microsoft 365 Apps for Enterprise tramite Configuration Manager (Current Branch). Configuration Manager consente di ridimensionare gli ambienti di grandi dimensioni e di controllare l'installazione, gli aggiornamenti e le impostazioni. Ha anche funzionalità predefinite per rendere più semplice ed efficiente la distribuzione e la gestione di Office, tra cui:

- Cache peer, che può essere utile per una capacità di rete limitata durante la distribuzione ai dispositivi in posizioni remote.
- Dashboard di gestione client di Office, che semplifica la distribuzione di Office e il monitoraggio degli aggiornamenti e consente agli amministratori di accedere alle funzionalità di distribuzione e gestione più recenti.
- Distribuzione Intelligent Language Pack, inclusa la distribuzione automatica della stessa lingua del sistema operativo.
- Metodo completamente supportato e di facile utilizzo per rimuovere le versioni di Office esistenti da un client durante la distribuzione.

Oltre a Configuration Manager, Contoso ha utilizzato il [Toolkit di conformità per i componenti aggiuntivi di Office e VBA](https://docs.microsoft.com/deployoffice/readiness-toolkit-application-compatibility-microsoft-365-apps), uno strumento gratuito di Microsoft, per valutare i problemi di compatibilità con le macro e i componenti aggiuntivi di Office.

## <a name="managing-deployment-and-updates"></a>Gestione della distribuzione e degli aggiornamenti

Microsoft 365 Apps for Enterprise ha un nuovo modello di rilascio: Office As a Service. Il modello di servizio rende più facile rimanere aggiornati sulle nuove funzionalità. Tuttavia, è spesso necessario che i reparti IT modifichino il modo in cui distribuiscono e testano nuove versioni. Per ridurre al minimo i problemi di compatibilità e per garantire che i propri computer siano sempre aggiornati, Contoso ha distribuito Windows e Office in due fasi:

- In primo luogo, sono state distribuite le app Microsoft 365 per Enterprise a un piccolo gruppo di dispositivi rappresentativi all'interno dell'organizzazione. Questo gruppo pilota è stato utilizzato per testare le app, i componenti aggiuntivi e l'hardware con le app Microsoft 365 per Enterprise.
- Quattro mesi dopo, in seguito alla correzione di tutti i problemi critici con app, componenti aggiuntivi e hardware nel gruppo pilota, Contoso ha distribuito Microsoft 365 Apps for enterprise al resto dei dispositivi nell'organizzazione (il gruppo di grandi dimensioni).

Invece di gestire gli aggiornamenti a Office utilizzando Configuration Manager, Contoso ha abilitato gli aggiornamenti automatici dal cloud. Gli aggiornamenti basati sul cloud riducono il sovraccarico amministrativo assicurando che i dispositivi siano sempre aggiornati.

Contoso ha seguito lo stesso approccio in due fasi per gli aggiornamenti delle funzionalità utilizzati per la distribuzione di Office: i dispositivi nel gruppo pilota hanno ricevuto gli aggiornamenti delle funzionalità quattro mesi prima rispetto ai dispositivi nel resto dell'organizzazione (il gruppo di grandi dimensioni). Per farlo per Office, Contoso ha usato due [canali di aggiornamento](https://docs.microsoft.com/DeployOffice/overview-update-channels) consigliati:

- Canale Enterprise semestrale (Anteprima) per gli aggiornamenti del gruppo pilota
- Semi-Annual Channel Enterprise per gli aggiornamenti del gruppo generale

Poiché il Canale Enterprise semestrale (Anteprima) rilascia una versione di Microsoft 365 Apps for enterprise quattro mesi prima del Canale Enterprise semestrale, Contoso ha il tempo di convalidare gli aggiornamenti senza avere la necessità di gestirli.

## <a name="deployment-process"></a>Processo di distribuzione

Per completare la distribuzione di Office, Contoso ha implementato la procedura seguente, che include le procedure consigliate da Microsoft:

1. Prima della distribuzione, Contoso ha utilizzato il Toolkit di preparazione per i componenti aggiuntivi di Office e VBA per testare le app e i componenti aggiuntivi di Office per valutarne la compatibilità con le app Microsoft 365 per Enterprise.
1. In Configuration Manager hanno abilitato la cache peer sui propri dispositivi client, contribuendo a una capacità di rete limitata durante la distribuzione ai dispositivi client in posizioni remote. 
1. Contoso ha definito due gruppi di distribuzione come insiemi di dispositivi in Configuration Manager: un gruppo pilota e un gruppo di grandi dimensioni. Il gruppo pilota, che includeva un piccolo gruppo di dispositivi rappresentativi all'interno dell'organizzazione, è stato utilizzato per il testing aggiuntivo di app, componenti aggiuntivi e hardware con Windows 10 Enterprise e Microsoft 365 Apps for Enterprise.
1. Sono stati creati pacchetti di distribuzione per Office utilizzando il dashboard di gestione client di Office e la procedura guidata di installazione di Office 365, che sono entrambi parte della console di Configuration Manager. Sono state costruite due app Microsoft 365 per i pacchetti Enterprise, una per il gruppo pilota sul canale Semi-Annual Enterprise (Preview) e una per il gruppo generale nel canale Semi-Annual Enterprise.
2. In ogni pacchetto di Office sono inclusi i Language Pack in inglese, francese e tedesco. Se un dispositivo richiede una lingua non inclusa nel pacchetto di Office, tale Language Pack è stato scaricato automaticamente dalla rete di distribuzione di contenuti (CDN) di Office.
3. Ha usato la funzionalità integrata nel pacchetto di Office per rimuovere automaticamente tutte le versioni di MSI esistenti di Office prima di installare Microsoft 365 Apps for enterprise.
4. In Configuration Manager sono stati distribuiti i pacchetti di Windows e di Office ai punti di distribuzione nella propria rete. Poi hanno eseguito le sequenze di attività di distribuzione di Configuration Manager per distribuire il pacchetto pilota delle app di Microsoft 365 per l'organizzazione al gruppo pilota.
5. Dopo aver risolto i problemi di compatibilità con il gruppo pilota, Contoso ha eseguito le sequenze di attività per distribuire il pacchetto Microsoft 365 Apps for Enterprise al gruppo generale.

Poiché Contoso ha scelto di aggiornare automaticamente i dispositivi dal cloud, non è stato necessario gestire il processo in Configuration Manager. I dispositivi vengono automaticamente aggiornati direttamente dal cloud, in base al canale di aggiornamento definito nella distribuzione iniziale.

Di seguito sono riportate le app Contoso Microsoft 365 per l'installazione Enterprise e l'architettura di distribuzione degli aggiornamenti in continuazione.

![Infrastruttura di distribuzione di Contoso per Microsoft 365 Apps for Enterprise](../media/contoso-o365pp/contoso-o365pp-fig1.png)
 
## <a name="next-step"></a>Passaggio successivo

Informazioni su come Contoso [utilizza Microsoft Intune](contoso-mdm.md) in Microsoft 365 for Enterprise per gestire i dispositivi e le app che eseguono nell'organizzazione.

## <a name="see-also"></a>Vedere anche

[App Microsoft 365 per grandi imprese](https://docs.microsoft.com/deployoffice/deployment-guide-microsoft-365-apps)

[Panoramica di Microsoft 365 per le aziende](microsoft-365-overview.md)

[Guide dei laboratori di testing](m365-enterprise-test-lab-guides.md)
