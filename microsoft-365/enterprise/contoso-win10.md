---
title: Distribuzione di Windows 10 Enterprise per Contoso
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 09/13/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: Comprendere in che modo Contoso ha utilizzato System Center Configuration Manager per la distribuzione degli aggiornamenti sul posto per Windows 10 Enterprise.
ms.openlocfilehash: 03ee4d9efcedf42eb976e001411299d2080abf83
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "34073856"
---
# <a name="windows-10-enterprise-deployment-for-contoso"></a>Distribuzione di Windows 10 Enterprise per Contoso

**Riepilogo:** comprendere in che modo Contoso ha utilizzato System Center Configuration Manager per la distribuzione degli aggiornamenti sul posto per Windows 10 Enterprise.

Prima dell'implementazione estesa di Microsoft 365 Enterprise, Contoso disponeva di computer compatibili con Windows e dispositivi con una combinazione di Windows 7 (10%), Windows 8.1 (65%) e Windows 10 (25%). Contoso desiderava aggiornare i computer per consentire a Windows 10 Enterprise di usufruire della maggiore sicurezza e del ridotto IT generati dalle distribuzioni automatiche degli aggiornamenti. 

Dopo aver valutato la propria infrastruttura e le proprie esigenze aziendali, Contoso ha identificato i seguenti requisiti chiave per la distribuzione:

- Esecuzione di Windows 10 Enterprise sul maggior numero possibile di computer e dispositivi
- Sfruttamento dell'infrastruttura System Center Configuration Manager esistente per l'implementazione degli aggiornamenti sul posto
- Controllo sulle versioni di Windows 10 Enterprise da distribuire e sugli aggiornamenti che vengono eseguiti tramite gli anelli
- PC e dispositivi devono rimanere sempre aggiornati con costi di amministrazione dell'IT minimi e un impatto minimo sugli utenti finali

Con il termine "aggiornato" si intende la versione di Windows 10 Enterprise più adatta alle esigenze aziendali di Contoso, che può essere diverso dall'avere tutti i computer compatibili con Windows che utilizzano la versione più aggiornata di Windows 10 Enterprise.

## <a name="deployment-tools"></a>Strumenti di distribuzione

Prima e durante gli aggiornamenti sul posto di Windows 10 Enterprise, Contoso utilizzava le soluzioni di seguenti di Windows Analytics:

- Preparazione aggiornamenti  

  Raccoglie dati di sistema, applicazione e driver per l'analisi e quindi identifica i problemi di compatibilità che possono bloccare un aggiornamento e suggerisce le correzioni ai problemi noti a Microsoft.

- Conformità aggiornamenti  

  Raccoglie i dati di sistema e diagnostici tra cui lo stato dell'installazione degli aggiornamenti, i dati di configurazione di Windows Update per le aziende (WUfB), i dati di Windows Defender Antivirus e altre informazioni specifiche per gli aggiornamenti e quindi memorizza questi dati nell'analisi e nell'uso del cloud.

- Integrità del dispositivo  

  Raccoglie i dati di sistema e diagnostici di Windows 10, inclusi lo stato dell'installazione degli aggiornamenti, i dati di configurazione di Windows Update per le aziende (WUfB), i dati di Windows Defender Antivirus e altre informazioni specifiche per gli aggiornamenti e quindi memorizza questi dati nell'analisi e nell'uso del cloud.
 
Contoso dispone di un'infrastruttura System Center Configuration Manager (Current Branch). Configuration Manager è in grado di scalare per gli ambienti di grandi dimensioni e fornisce controllo esteso sull'installazione, gli aggiornamenti e le impostazioni. Inoltre, dispone di funzionalità integrate per semplificare e rendere più efficiente la distribuzione e la gestione di Windows 10 Enterprise.

## <a name="planning-process"></a>Processo di pianificazione

Prima della distribuzione, Contoso ha definito i seguenti anelli:

- Tre anelli per la gestione temporanea della convalida e la distribuzione 
  - Uno per le build di anteprima 
  - Uno per le build delle nuove versioni
  - Uno per una build precedente 
- Un anello l'ampia distribuzione di Windows 10 Enterprise basata sui dati degli anelli di convalida

Contoso inoltre ha utilizzato la soluzione Preparazione aggiornamenti di Windows Analytics per identificare il gruppo di app installate e la loro compatibilità con Windows 10 Enterprise.

## <a name="deployment-process"></a>Processo di distribuzione

Per completare la distribuzione degli aggiornamenti sul posto di Windows 10 Enterprise, Contoso ha implementato la procedura seguente, che include le procedure consigliate da Microsoft:

1. Abilitazione della cache peer per Configuration Manager.
2. Creazione di pacchetti di Windows personalizzati basati sulle immagini del Volume Licensing Service Center.
3. Utilizzo di Configuration Manager per distribuire i pacchetti di Windows ai punti di distribuzione nella propria rete e distribuzione di build ai tre anelli per la gestione temporanea della convalida e della distribuzione.
4. Esecuzione della valutazione della riuscita per i computer e i dispositivi negli anelli di gestione temporanea della convalida e della distribuzione mediante soluzioni Integrità del dispositivo e Conformità aggiornamenti di Windows Analytics.
5. Sulla base delle informazioni di Windows Analytics, Contoso ha determinato la versione di Windows 10 Enterprise da distribuire all'anello per la distribuzione generale.
6. Esecuzione delle sequenze di attività di distribuzione di Configuration Manager per distribuire il pacchetto di Windows selezionato all'anello di distribuzione generale.
7. Monitoraggio di computer e dispositivi nell'anello di distribuzione generale mediante le soluzioni Integrità del dispositivo e Conformità aggiornamenti fornite da Windows Analytics per risolvere i problemi.

La Figura 1 mostra l'architettura di distribuzione degli aggiornamenti sul posto e degli aggiornamenti continui l'architettura di distribuzione.

![](./media/contoso-win10/contoso-win10-fig1.png)
 
**Figura 1: Infrastruttura di distribuzione di Windows 10 Enterprise di Contoso**

Questa infrastruttura è costituita da:

- System Center Configuration Manager, che effettua le seguenti operazioni:
  - Ottiene le immagini per i pacchetti di Windows 10 Enterprise da Microsoft Volume Licensing Center in Microsoft Network.
  - Si tratta del punto di amministrazione centrale per i pacchetti di distribuzione.
- Punti di distribuzione regionali che in genere si trovano nelle filiali di Contoso.
- Computer e dispositivi Windows in diversi punti che ricevono e installano pacchetti di distribuzione per l'aggiornamento sul posto e gli aggiornamenti continui basati sull'appartenenza all'anello.

## <a name="next-step"></a>Passaggio successivo

[Informazioni su](contoso-o365pp.md) come Contoso si avvale dell'infrastruttura di System Center Configuration Manager per distribuire e mantenere aggiornato Office 365 ProPlus nell'organizzazione. 

## <a name="see-also"></a>Vedere anche

[Windows 10 Enterprise per Microsoft 365 Enterprise](windows10-infrastructure.md)

[Guida alla distribuzione](deploy-microsoft-365-enterprise.md)

[Guide dei laboratori di testing](m365-enterprise-test-lab-guides.md)
