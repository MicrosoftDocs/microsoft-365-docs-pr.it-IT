---
title: Passaggio 7 - Manutenzione di Windows e Office
f1.keywords:
- NOCSH
ms.author: jogruszc
author: JGruszczyk
manager: jemed
ms.date: 05/20/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Informazioni su come prepararsi per la manutenzione di Windows e Office nel proprio ambiente.
ms.openlocfilehash: e9de339c6bc66e5cd3c02af5f6a53c32b7573b1f
ms.sourcegitcommit: 584e2e9db8c541fe32624acdca5e12ee327fdb63
ms.contentlocale: it-IT
ms.lasthandoff: 06/10/2020
ms.locfileid: "44679003"
---
# <a name="step-7-windows-and-office-servicing"></a>Passaggio 7: manutenzione di Windows e Office

![](../media/step-7-windows-and-office-as-a-service-media/step-7-windows-and-office-as-a-service-media-1.png)

<table>
<thead>
<td><img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-10.png" alt="Step 7" height="144" width="144" /></td>
<td><p><strong>Passaggio 7: manutenzione di Windows e Office</strong></p>
<p>Both Windows 10 and Microsoft 365 Apps for enterprise continually add new capabilities to keep bringing user experiences and security forward with the latest innovations. Learn how to stay current with semi-annual and monthly updates, how the new servicing model works and the tools and options you have.</p></td>
<td><a href="https://aka.ms/ddev7" target="_blank"><img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-20.png" alt="Step 7" height="130" width="231" /></a></td>
</thead>
</table>

>[!NOTE]
>La manutenzione di Windows e Office è il settimo passaggio del nostro processo di distribuzione consigliato e illustra la pianificazione per la preparazione agli aggiornamenti semestrali delle funzionalità. Per vedere l’intero processo di distribuzione, visitare il [Centro distribuzione desktop](https://aka.ms/HowToShift).
>

Sia Windows 10 che Microsoft 365 Apps for enterprise introducono nuove opzioni di manutenzione, modelli di supporto e tempistiche di aggiornamento. Queste modifiche semplificano il processo per rimanere aggiornati sulle ultime funzionalità. Oltre a questi aggiornamenti sono disponibili nuove opzioni di configurazione, per creare piani di manutenzione sulla base delle proprie specifiche esigenze. Di seguito viene illustrato come prepararsi per gli aggiornamenti dei canali semestrali, che offrono nuove funzionalità in Windows 10 e Microsoft 365 Apps for enterprise sfruttando le nuove funzionalità di Microsoft Endpoint Configuration Manager (Current Branch).

[Aiutare i clienti a passare a Windows 10 e Microsoft 365 Apps for enterprise](https://www.microsoft.com/microsoft-365/blog/2018/09/06/helping-customers-shift-to-a-modern-desktop/)

## <a name="update-types"></a>Tipi di aggiornamento

Gli aggiornamenti si dividono in due categorie principali, aggiornamenti delle funzionalità e aggiornamenti qualitativi e di sicurezza che contengono correzioni cumulative di errori, per l'affidabilità e la sicurezza. In termini di frequenza, sia Windows che Office offrono un canale semestrale che fornisce nuove funzionalità due volte all'anno intorno a marzo e settembre, mentre gli aggiornamenti qualitativi e della sicurezza vengono rilasciati mensilmente. Inoltre, solo per le app di Office 365, è disponibile un'opzione Canale corrente completamente supportata, che fornisce sia nuove funzionalità che aggiornamenti qualitativi.

Chi è abituato a un ciclo più lungo tra il sistema operativo desktop e gli aggiornamenti delle app, potrebbe chiedere:

  - Gli aggiornamenti saranno compatibili?

  - Gli utenti devono ricevere un'altra formazione?

  - E quali sono i rischi?

Per rispondere a queste domande e spiegare il motivo dell'offerta più frequente di nuove funzionalità, di seguito vengono presentati alcuni dei vantaggi di questo approccio

### <a name="feature-update-benefits"></a>Vantaggi dell'aggiornamento delle funzionalità

First, we’ve moved away from the model of the past that would introduce huge waves of change around every three years to now incremental smaller changes with feature updates twice per year. Why? With technology trends moving so fast in addition to rapidly evolving security threats, this keeps experiences and protections current. Some of the security related updates for example can’t just be delivered by monthly security updates or antivirus signature files; they may be low-level changes platform, like virtualization-based security.

[Guida rapida di Windows as a Service](https://docs.microsoft.com/windows/deployment/update/waas-quick-start)

[Ridurre le minacce con le funzionalità di sicurezza di Windows 10](https://docs.microsoft.com/windows/security/threat-protection/overview-of-threat-mitigations-in-windows-10%20%20)

### <a name="cumulative-update-model-benefits"></a>Vantaggi del modello di aggiornamento cumulativo

Second delivering quality and security updates as a cumulative update package corrects many of the issues of the past. It used to be that you might pick and choose sometimes from a dozen updates or more each month for both Windows and Office. As you can imagine, this creates a nearly impossible set of test matrices for support. Also, if you install a version of Windows or Office that is a year or more old, it might take hours or sometimes days to apply all updates delivered since that version was released.

With the cumulative model, you’re always one update away from being current and in doing so the number of monthly updates that you need to deploy is reduced. Each update builds upon updates from previous months and contains all of the fixes that you need to get current. Cumulative updates are especially helpful when PCs has been turned off for several months because they are in storage waiting to be reassigned to a different user.

### <a name="expanded-validation-of-updates"></a>Convalida estesa degli aggiornamenti

Un altro vantaggio è che, prima di implementare gli aggiornamenti per la distribuzione generale, vengono rilasciate build tramite i programmi Insider per [Office](https://products.office.com/office-insider?tab=Windows-Desktop) e [Windows](https://insider.windows.com/) e ciò consente di raccogliere dati di diagnostica e feedback prima del rilascio su larga scala. Attualmente i programmi Insider sono aperti a tutti e permettono di conoscere in anticipo gli aggiornamenti. Prima del rilascio degli aggiornamenti, Microsoft avrà ricevuto dati di diagnostica da milioni di configurazioni, pertanto al momento dell'implementazione la qualità sarà intrinsecamente più prevedibile.

Inoltre, poiché le build di Insider di Microsoft 365 Apps for enterprise riflettono gli aggiornamenti del canale mensili, se si utilizza il canale semestrale di Office per fornire aggiornamenti delle funzionalità due volte all'anno in linea con Windows, è possibile convalidare tali build in anticipo utilizzando anche le versioni del Canale Enterprise semestrale (Anteprima).

### <a name="supporting-management-tools"></a>Strumenti di gestione di supporto

We've also thought through how to make the deployment of updates seamless to you. Configuration Manager (Current Branch) is updated frequently to support the roll-out of these updates to Windows and Office and any new capabilities.

[Distribuire gli aggiornamenti di Windows 10 con Configuration Manager](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-configuration-manager)

[Gestire Microsoft 365 Apps for enterprise con Configuration Manager](https://docs.microsoft.com/mem/configmgr/sum/deploy-use/manage-office-365-proplus-updates)

## <a name="overview-of-windows-and-office-channels"></a>Panoramica dei canali di Windows e Office

Windows 10 offre tre canali di manutenzione:

- [**Programma Windows Insider**](https://docs.microsoft.com/windows/deployment/update/waas-overview#windows-insider), che le organizzazioni possono usare per testare e fornire feedback sulle funzionalità fornite con il l'aggiornamento delle funzionalità successivo
- **Canale semestrale**, che offre aggiornamenti delle funzionalità due volte l'anno
- **Long Term Servicing Channel**, progettato solo per dispositivi specialistici che richiedono un'opzione di manutenzione con tempi più lunghi

Microsoft 365 offre quattro canali di manutenzione:

- [**Programma Office Insider**](https://products.office.com/office-insider), che le organizzazioni possono usare per testare e fornire feedback sulle nuove funzionalità di Office ancora in fase di sviluppo
- **Canale corrente**, che fornisce agli utenti le funzionalità più recenti di Office non appena sono disponibili
- **Canale Enterprise semestrale**, che fornisce nuove funzionalità e caratteristiche solo due volte l'anno
- **Canale Enterprise semestrale (Anteprima)**, una build di Office completamente supportata che consente a utenti pilota e tester della compatibilità di testare e convalidare il Canale Enterprise semestrale successivo.

Per informazioni dettagliate sui canali di manutenzione di Windows e Office, vedere la documentazione seguente:

- [Panoramica di Windows as a Service](https://docs.microsoft.com/windows/deployment/update/waas-overview#servicing-channels)
- [Panoramica dei canali di aggiornamento per Microsoft 365 Apps](https://docs.microsoft.com/DeployOffice/overview-update-channels#BKMK_SAC)

## <a name="phased-deployment-of-updates"></a>Distribuzione a fasi degli aggiornamenti

Now let’s shift gears to how you will roll out these updates. For any release, we recommend at least three deployment phases for IT – validation, piloting and broad production deployment. Once you’re up and running on Windows 10 and Microsoft 365 Apps for enterprise, you'll use monthly servicing to stay current with critical security and quality updates, then you’ll move to semi-annual servicing for new features.

### <a name="monthly-updating"></a>Aggiornamento mensile

The service model is designed so you can choose to limit the roll-out of new features to twice per year, and if needed you can even skip a semi-annual update and continue receiving quality and security updates. As mentioned, the cumulative nature of monthly updates means each will increase in size per month.

#### <a name="express-updates"></a>Express Updates

Using a technology called "Express Updates" in Windows and Binary Delta Compression in Office, we can reduce the download size significantly. In both approaches, the update engines compare what’s on the PC and finds only the differentials needed to update what’s there.

[Aggiornamenti qualitativi di Windows 10 illustrati e fine degli aggiornamenti delta](https://techcommunity.microsoft.com/t5/Windows-IT-Pro-Blog/Windows-10-quality-updates-explained-amp-the-end-of-delta/ba-p/214426)

Windows Update per le aziende e Windows Server Update Services hanno supportato gli Express Updates per un lungo periodo, tuttavia ora è stato esteso il supporto a Microsoft Endpoint Configuration Manager (Current Branch) in modo che possa utilizzare anche gli Express Updates.

![](../media/step-7-windows-and-office-as-a-service-media/step-7-windows-and-office-as-a-service-media-3.png)

#### <a name="binary-delta-compression"></a>Binary Delta Compression

Binary Delta Compression (compressione delle differenze binarie) in Office viene utilizzato solo se si esegue l'aggiornamento dalla versione più recente di Microsoft 365 Apps for enterprise. Di conseguenza, per utilizzare questo approccio è necessario aggiornare la build precedente e non è possibile ignorare gli aggiornamenti.

Windows and Office update channels can be managed via Configuration Manager using the standard approval and targeting process. Additionally, you can use policy settings in Office and Windows to enforce update channels used, as well as related settings.

### <a name="semi-annual-updates"></a>Aggiornamenti semestrali

Quindi queste sono le considerazioni sugli aggiornamenti mensili. Ora si può passare agli aggiornamenti semestrali più grandi.

Come descritto nella sezione relativa alla preparazione di dispositivi e applicazioni, sarà necessario prepararsi per questi aggiornamenti più grandi utilizzando gli stessi strumenti di preparazione configurati nel Passaggio 1 del grafico circolare del processo di distribuzione.

As for tooling, you can use policy settings with Windows Update for Business, software update management via Microsoft Endpoint Configuration Manager (Current Branch), Windows Server Update Services (WSUS), or update policies set by Microsoft Intune. If you are concerned about network bandwidth, see Step 2: Directory and Network Readiness, to learn about your options to reduce network traffic via Delivery Optimization and other peer to peer caching technologies.

![](../media/step-7-windows-and-office-as-a-service-media/step-7-windows-and-office-as-a-service-media-4.png)

[Canale semestrale per Windows](https://docs.microsoft.com/windows/deployment/update/waas-overview#semi-annual-channel)

[Canale Enterprise semestrale per Microsoft 365 Apps](https://docs.microsoft.com/DeployOffice/overview-update-channels#BKMK_SAC)

#### <a name="upgrade-task-sequences"></a>Sequenze di attività di aggiornamento

L'installazione degli aggiornamenti di funzionalità più grandi tramite routine di gestione degli aggiornamenti software standard è un'opzione supportata, ma molte organizzazioni sceglieranno di utilizzare una sequenza di attività di aggiornamento con Microsoft Endpoint Configuration Manager (Current Branch) o Microsoft Deployment Toolkit.

Una sequenza di attività consente di creare controlli personalizzati o attività PRIMA dell'installazione dell'aggiornamento delle funzionalità e consente di eseguire attività personalizzate DOPO che l'installazione dell'aggiornamento è stata completata. Le attività di post-aggiornamento potrebbero includere servizi di sospensione temporanea se necessario durante l'aggiornamento, installazione sostituzione di driver, aggiornamenti di applicazioni o barra delle applicazioni e impostazioni Start personalizzate di Windows 10.

![](../media/step-7-windows-and-office-as-a-service-media/step-7-windows-and-office-as-a-service-media-5.png)

If you’re already using task sequences to migrate your Windows 7 machines to Windows 10 and are well-versed with those tools, this is a great place to start and provides ultimate control. While you can use a single task sequence for the entire upgrade, it is quite common that organizations use two task sequences. One task sequence for making sure the machines are ready for the upgrade, that silently pre-stages all the required setup files on target computers, and one to do the actual upgrade. This approach ensures that your user productivity is less impacted.

[Creare una sequenza di attività per aggiornare un sistema operativo in Configuration Manager](https://docs.microsoft.com/mem/configmgr/osd/deploy-use/create-a-task-sequence-to-upgrade-an-operating-system)

#### <a name="semi-annual-channel-support-for-feature-updates"></a>Supporto canale semestrale per l'aggiornamento delle funzionalità

[Come annunciato nel settembre 2018](https://www.microsoft.com/microsoft-365/blog/2018/09/06/helping-customers-shift-to-a-modern-desktop/), per il supporto di sequenza temporale per gli aggiornamenti canale semestrali verrà utilizzato il modello seguente.

  - Tutti gli aggiornamenti delle funzionalità attualmente supportati di Windows 10 Enterprise ed Education, a partire dalla versione 1607, saranno supportati per 30 mesi dalla data di rilascio originale.

  - Tutti gli aggiornamenti di funzionalità futuri, a partire da 1809, con assegnazione settembre saranno supportati per 30 mesi dalla data di rilascio.

  - Gli aggiornamenti delle funzionalità future con assegnazione marzo e a partire da 1903 continueranno a essere supportati per 18 mesi dalla data di rilascio.

  - Gli aggiornamenti semestrali di Microsoft 365 Apps for enterprise continuano a essere supportati per 18 mesi

#### <a name="additional-setup-automation-options-outside-of-task-sequences"></a>Ulteriori opzioni di automazione della configurazione al di fuori delle sequenze di attività

Se non si utilizzano le sequenze di attività di aggiornamento, ora è possibile eseguire azioni personalizzate o applicare file del driver durante gli aggiornamenti delle funzioni nella fase di pre-installazione (prima che l'installazione esegua i controlli di compatibilità) o nella fase di pre-commit (prima che l'aggiornamento venga applicato).

[Novità in Windows 10, versione 1803](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1803%23windows-setup)

## <a name="next-step"></a>Passaggio successivo 

## <a name="step-8-user-communications-and-training"></a>[Passaggio 8: formazione e comunicazioni utente](https://aka.ms/mdd8)

## <a name="previous-step"></a>Passaggio precedente 

## <a name="step-6-os-deployment-and-feature-updates"></a>[Passaggio 6: distribuzione del sistema operativo e aggiornamenti delle funzionalità](https://aka.ms/mdd6)
