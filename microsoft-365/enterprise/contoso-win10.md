---
title: Distribuzione di Windows 10 Enterprise per Contoso
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
description: Comprendere in che modo Contoso ha usato Microsoft Endpoint Configuration Manager per la distribuzione degli aggiornamenti sul posto per Windows 10 Enterprise.
ms.openlocfilehash: 0543f24665048d0679bc1b099fdd0a2d431c1e54
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754248"
---
# <a name="windows-10-enterprise-deployment-for-contoso"></a>Distribuzione di Windows 10 Enterprise per Contoso

Prima dell'implementazione di Microsoft 365 per le aziende, Contoso aveva PC e dispositivi compatibili con Windows che eseguono una combinazione di Windows 7 (10%), Windows 8.1 (65%) e Windows 10 (25%). Contoso desiderava aggiornare i propri PC per Windows 10 Enterprise sfruttando la sicurezza avanzata e ridurre il sovraccarico IT dovuto alle distribuzioni automatizzate degli aggiornamenti. 

Dopo aver valutato la propria infrastruttura e le proprie esigenze aziendali, Contoso ha identificato i seguenti requisiti chiave per la distribuzione:

- Esecuzione di Windows 10 Enterprise sul maggior numero possibile di computer e dispositivi
- Sfruttamento dell'infrastruttura di Configuration Manager esistente per l'implementazione degli aggiornamenti sul posto
- Controllo sulle versioni di Windows 10 Enterprise da distribuire e sugli aggiornamenti che vengono eseguiti tramite gli anelli
- PC e dispositivi devono rimanere sempre aggiornati con costi di amministrazione dell'IT minimi e un impatto minimo sugli utenti finali

Con il termine "aggiornato" si intende la versione di Windows 10 Enterprise più adatta alle esigenze aziendali di Contoso, che può essere diverso dall'avere tutti i computer compatibili con Windows che utilizzano la versione più aggiornata di Windows 10 Enterprise.

## <a name="deployment-tools"></a>Strumenti di distribuzione

Prima e durante gli aggiornamenti sul posto di Windows 10 Enterprise, Contoso utilizzava le soluzioni di seguenti di Windows Analytics:

- Preparazione aggiornamenti  

  Raccoglie dati di sistema, applicazione e driver per l'analisi e quindi identifica i problemi di compatibilità che possono bloccare un aggiornamento e suggerisce le correzioni ai problemi noti a Microsoft.

- Conformità aggiornamenti  

  Mostra lo stato dei dispositivi rispetto agli aggiornamenti di Windows, in modo che sia possibile verificare che dispongano degli aggiornamenti più recenti.

- Integrità del dispositivo  

  Identifica i dispositivi che si arrestano spesso in modo anomalo e quindi potrebbe essere necessario ricreare o sostituire e i driver di dispositivo che causano arresti anomali, con suggerimenti sulle versioni alternative di tali driver che potrebbero ridurre il numero di errori. Notifica la presenza di configurazioni errate di Windows Information Protection con invio di messaggi agli utenti finali.
 
Contoso dispone di un'infrastruttura di Configuration Manager (Current Branch) esistente. Configuration Manager si adatta ad ambienti di grandi dimensioni e fornisce un controllo completo sull'installazione, gli aggiornamenti e le impostazioni. Inoltre, dispone di funzionalità integrate per semplificare e rendere più efficiente la distribuzione e la gestione di Windows 10 Enterprise.

## <a name="planning-process"></a>Processo di pianificazione

Contoso ha usato Preparazione aggiornamenti in Windows Analytics per determinare il set di app installate e la loro compatibilità con Windows 10 Enterprise.

## <a name="deployment-process"></a>Processo di distribuzione

Per completare la distribuzione degli aggiornamenti sul posto di Windows 10 Enterprise, Contoso ha implementato la procedura seguente, che include le procedure consigliate da Microsoft:

1. Abilitazione della cache peer per Configuration Manager.
2. Creazione di pacchetti di Windows personalizzati basati sulle immagini del Volume Licensing Service Center.
3. Ha usato Configuration Manager per distribuire i pacchetti di Windows ai punti di distribuzione nella rete e ha distribuito le build ai tre gruppi di gestione temporanea di convalida e distribuzione.
4. Esecuzione della valutazione della riuscita per i computer e i dispositivi negli anelli di gestione temporanea della convalida e della distribuzione mediante soluzioni Integrità del dispositivo e Conformità aggiornamenti di Windows Analytics.
5. In base alle informazioni di Windows Analytics, Contoso ha determinato la versione di Windows 10 Enterprise da distribuire al gruppo di distribuzione generale.
6. Ha eseguito le sequenze di attività di distribuzione di Configuration Manager per distribuire il pacchetto di Windows selezionato al gruppo di distribuzione generale.
7. Computer e dispositivi monitorati nel gruppo di distribuzione generale usando le soluzioni Integrità dei dispositivi e Conformità aggiornamenti per risolvere i problemi.

Ecco l'architettura di distribuzione degli aggiornamenti sul posto e degli aggiornamenti continui di Contoso.

![Infrastruttura di distribuzione di Windows 10 Enterprise di Contoso](../media/contoso-win10/contoso-win10-fig1.png)

Questa infrastruttura è costituita da:

- Configuration Manager, che:
  - Ottiene le immagini per i pacchetti di Windows 10 Enterprise da Microsoft Volume Licensing Center in Microsoft Network.
  - Si tratta del punto di amministrazione centrale per i pacchetti di distribuzione.
- Punti di distribuzione regionali che in genere si trovano negli hub regionali di Contoso.
- PC e dispositivi Windows in varie posizioni che ricevono e installano i pacchetti di distribuzione per l'aggiornamento sul posto o gli aggiornamenti continui in base all'appartenenza ai gruppi.

## <a name="next-step"></a>Passaggio successivo

Informazioni su come Contoso usa l'infrastruttura di Configuration Manager per distribuire e mantenere [microsoft 365 Apps for enterprise corrente](contoso-o365pp.md) all'interno dell'organizzazione. 

## <a name="see-also"></a>Vedere anche

[Windows 10 Enterprise](https://docs.microsoft.com/windows/deployment/)

[Panoramica di Microsoft 365 per le aziende](microsoft-365-overview.md)

[Guide dei laboratori di testing](m365-enterprise-test-lab-guides.md)
