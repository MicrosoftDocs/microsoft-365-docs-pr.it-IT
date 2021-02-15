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

Contoso ha aggiornato i pc a Windows 10 Enterprise e Microsoft 365 Apps for enterprise per consentire una collaborazione più efficace, una maggiore sicurezza e un'esperienza desktop più moderna. Dopo aver valutato l'infrastruttura e le esigenze aziendali, Contoso ha identificato i requisiti chiave per la distribuzione:

- Tutti i PC devono eseguire Microsoft 365 Apps for enterprise.
- La distribuzione deve utilizzare l'infrastruttura e gli strumenti di gestione esistenti, se possibile.
- La distribuzione deve supportare più lingue e architetture esistenti nei dispositivi degli utenti.
- I PC devono rimanere aggiornati e protetti con costi amministrativi IT minimi e un impatto minimo sugli utenti.

## <a name="deployment-tools"></a>Strumenti di distribuzione

In base alle proprie esigenze, Contoso ha scelto di distribuire Windows 10 Enterprise e Microsoft 365 Apps for enterprise tramite Configuration Manager (Current Branch). Configuration Manager è scalabile per ambienti di grandi dimensioni e offre un controllo completo sull'installazione, gli aggiornamenti e le impostazioni. Sono inoltre disponibili funzionalità integrate per semplificare e rendere più efficiente la distribuzione e la gestione di Office, tra cui:

- Peer cache, che può essere utile con capacità di rete limitata durante la distribuzione in dispositivi in posizioni remote.
- Dashboard gestione client di Office, che semplifica la distribuzione di Office e il monitoraggio degli aggiornamenti e consente agli amministratori di accedere alle funzionalità di distribuzione e gestione più recenti.
- Distribuzione intelligente dei Language Pack, inclusa la distribuzione automatica della stessa lingua del sistema operativo.
- Un metodo completamente supportato e facile da usare per rimuovere le versioni esistenti di Office da un client durante la distribuzione.

Oltre a Configuration Manager, Contoso ha utilizzato i componenti aggiuntivi [Readiness Toolkit per Office](https://docs.microsoft.com/deployoffice/readiness-toolkit-application-compatibility-microsoft-365-apps)e VBA, uno strumento gratuito di Microsoft, per valutare i problemi di compatibilità con le macro e i componenti aggiuntivi di Office.

## <a name="managing-deployment-and-updates"></a>Gestione della distribuzione e degli aggiornamenti

Microsoft 365 Apps for enterprise ha un nuovo modello di rilascio: Office as a Service. Il modello di servizio consente di rimanere sempre aggiornati con le nuove funzionalità. Tuttavia, spesso i reparti IT devono modificare il modo in cui distribuiscono e testano le nuove versioni. Per ridurre al minimo i problemi di compatibilità e garantire che i computer rimangano aggiornati, Contoso ha distribuito Windows e Office in due fasi:

- Prima di tutto, hanno distribuito Microsoft 365 Apps for enterprise in un piccolo set di dispositivi rappresentativi all'interno dell'organizzazione. Questo gruppo pilota è stato usato per testare app, componenti aggiuntivi e hardware con Microsoft 365 Apps for enterprise.
- Quattro mesi dopo, in seguito alla correzione di tutti i problemi critici con app, componenti aggiuntivi e hardware nel gruppo pilota, Contoso ha distribuito Microsoft 365 Apps for enterprise al resto dei dispositivi nell'organizzazione (il gruppo di grandi dimensioni).

Invece di gestire gli aggiornamenti di Office tramite Configuration Manager, Contoso ha abilitato gli aggiornamenti automatici dal cloud. Gli aggiornamenti basati sul cloud riducono il sovraccarico amministrativo garantendo al contempo che i dispositivi rimangano aggiornati.

Contoso ha seguito lo stesso approccio in due fasi per gli aggiornamenti delle funzionalità usati per la distribuzione di Office: i dispositivi nel gruppo pilota hanno ricevuto gli aggiornamenti delle funzionalità quattro mesi prima dei dispositivi nel resto dell'organizzazione (il gruppo generale). Per farlo per Office, Contoso ha usato due [canali di aggiornamento](https://docs.microsoft.com/DeployOffice/overview-update-channels) consigliati:

- Canale Enterprise semestrale (Anteprima) per gli aggiornamenti del gruppo pilota
- Semi-Annual Enterprise Channel per gli aggiornamenti del gruppo generale

Poiché il Canale Enterprise semestrale (Anteprima) rilascia una versione di Microsoft 365 Apps for enterprise quattro mesi prima del Canale Enterprise semestrale, Contoso ha il tempo di convalidare gli aggiornamenti senza avere la necessità di gestirli.

## <a name="deployment-process"></a>Processo di distribuzione

Per completare la distribuzione di Office, Contoso ha implementato la procedura seguente, che include le procedure consigliate da Microsoft:

1. Prima della distribuzione, Contoso ha usato il componente aggiuntivo Readiness Toolkit for Office e VBA per testare le app e i componenti aggiuntivi di Office per valutarne la compatibilità con Microsoft 365 Apps for enterprise.
1. In Configuration Manager, hanno abilitato la peer cache nei propri dispositivi client, il che consente di ridurre la capacità di rete durante la distribuzione nei dispositivi client in posizioni remote. 
1. Contoso ha definito due gruppi di distribuzione come raccolte di dispositivi in Configuration Manager: un gruppo pilota e un gruppo generale. Il gruppo pilota, che includeva un piccolo set di dispositivi rappresentativi all'interno dell'organizzazione, è stato usato per ulteriori test di app, componenti aggiuntivi e hardware con Windows 10 Enterprise e Microsoft 365 Apps for enterprise.
1. Hanno creato pacchetti di distribuzione per Office usando il dashboard di Gestione client di Office e la procedura guidata del programma di installazione di Office 365, che fanno entrambi parte della console di Configuration Manager. Hanno creato due pacchetti Microsoft 365 Apps for enterprise, uno per il gruppo pilota nel canale Enterprise di Semi-Annual (anteprima) e uno per il gruppo generale nel canale Enterprise di Semi-Annual.
2. Ogni pacchetto di Office includeva Language Pack per l'inglese, il francese e il tedesco. Se un dispositivo richiedeva una lingua non inclusa nel pacchetto di Office, il Language Pack è stato scaricato automaticamente dalla rete per la distribuzione di contenuti (CDN) di Office.
3. Ha usato la funzionalità integrata nel pacchetto di Office per rimuovere automaticamente tutte le versioni di MSI esistenti di Office prima di installare Microsoft 365 Apps for enterprise.
4. In Configuration Manager, i pacchetti di Windows e Office sono stati distribuiti nei punti di distribuzione della rete. Quindi hanno eseguito le sequenze di attività di distribuzione di Configuration Manager per distribuire il pacchetto pilota di Microsoft 365 Apps for enterprise al gruppo pilota.
5. Dopo aver corretto i problemi di compatibilità con il gruppo pilota, Contoso ha eseguito le sequenze di attività per distribuire il pacchetto Microsoft 365 Apps for enterprise al gruppo generale.

Poiché Contoso ha scelto di aggiornare automaticamente i dispositivi dal cloud, non è stato necessario gestire il processo in Configuration Manager. I dispositivi vengono aggiornati automaticamente direttamente dal cloud in base al canale di aggiornamento definito nella distribuzione iniziale.

Ecco l'architettura di distribuzione degli aggiornamenti continui e dell'installazione di Microsoft 365 Apps for enterprise di Contoso.

![Infrastruttura di distribuzione di Contoso per Microsoft 365 Apps for enterprise](../media/contoso-o365pp/contoso-o365pp-fig1.png)
 
## <a name="next-step"></a>Passaggio successivo

Informazioni su come Contoso [usa Microsoft Intune](contoso-mdm.md) in Microsoft 365 per le aziende per gestire i dispositivi e le app eseguite nell'organizzazione.

## <a name="see-also"></a>Vedere anche

[App Microsoft 365 per grandi imprese](https://docs.microsoft.com/deployoffice/deployment-guide-microsoft-365-apps)

[Panoramica di Microsoft 365 per le aziende](microsoft-365-overview.md)

[Guide dei laboratori di testing](m365-enterprise-test-lab-guides.md)
