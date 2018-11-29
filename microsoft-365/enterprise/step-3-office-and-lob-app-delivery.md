---
title: Passaggio 3 - Distribuzione di Office e app line-of-business
ms.author: jogruszc
author: JGruszczyk
manager: jemed
ms.date: 09/14/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Informazioni su come distribuire Office e app line-of-business.
ms.openlocfilehash: 2bae1f159f7c8ae947d4afddfe1e608cdd8bc85b
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868933"
---
# <a name="step-3-office-and-lob-app-delivery"></a>Passaggio 3: distribuzione di Office e app line-of-business

È ora il momento di distribuire Office e le app line-of-business. Esistono molti modi per farlo, tra cui alcune entusiasmanti nuove opzioni. Analizzare le proprie esigenze e scegliere i metodi più indicati.

![](media/step-3-office-and-lob-app-delivery-media/step-3-office-and-lob-app-delivery-media-1.png)

<table>
<thead>
<td><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-6.png" alt="Step 3" height="130" width="130" /></td>
<td><p><strong>Passaggio 3: distribuzione di Office e app line-of-business</strong></p>
<p>Verificare che le app siano compresse e pronte per l'installazione automatica. Ottenere maggiori informazioni sulle nuove opzioni offerte dai pacchetti a portata di clic di Office 365 ProPlus per configurare, distribuire e mantenere aggiornate le app di Office.</p></td>
<td><a href="https://aka.ms/ddev3" target="_blank"><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-16.png" alt="Step 3" height="120" width="213" /></a></td>
</thead>
</table>

>[!NOTE]
>La distribuzione di Office e delle app line-of-business rappresenta il terzo passaggio del processo di distribuzione consigliato e tratta le opzioni di installazione e gestione di Office e LOB. Per una distribuzione corretta, non saltare i primi due passaggi. Per vedere il processo di distribuzione della versione desktop completa, visitare il [Centro di distribuzione desktop moderno](https://aka.ms/HowToShift).
>

Anche se alcune applicazioni sono disponibili solo in una versione compilata a 32 bit o 64 bit, altre, tra cui Office 365 ProPlus, sono disponibili come codice compilato nativo a 32 bit e 64 bit e una delle decisioni principali da prendere, sarà quella relativa alla versione da distribuire. Per sfruttare la potenza di elaborazione e la RAM aggiuntive dei nuovi dispositivi, si userà la versione a 64 bit, ma prima di farlo sarà necessario individuare eventuali sfide correlate alla compatibilità con componenti aggiuntivi o file. A questo scopo, potrebbe essere necessario tornare al Passaggio 1 - Preparazione app e dispositivo.

Se non ci sono problemi, consigliamo di distribuire le versioni a 64 bit di tutte le app, incluso Microsoft Office. Le app compilate native a 64 bit offrono le migliori prestazioni e sono la scelta più lungimirante.

Esistono molti metodi e modelli per l'installazione di applicazioni in Windows, esaminiamo quindi le opzioni di distribuzione a disposizione.

[Gestione di applicazioni di Windows 10](https://docs.microsoft.com/it-IT/windows/application-management/)

## <a name="msi-based-deployments"></a>Distribuzioni basate su MSI

Per le app line-of-business, probabilmente verranno utilizzati pacchetti o file eseguibili basati su MSI e le app verranno installate nell'ambito di una sequenza di attività di implementazione del sistema operativo. Windows 10 continuerà a funzionare con questi pacchetti.

Gli strumenti di distribuzione software come System Center Configuration Manager e Microsoft Intune sono inoltre ottimizzati per fornire app con MSI. Dopo aver convalidato le app su Windows 10, è possibile utilizzare System Center Configuration Manager (current branch) per la distribuzione di app. Se si utilizza il portale dell'azienda in Microsoft Intune, è possibile estendere la scelta di app approvate dall'IT affinché l'organizzazione possa includere le applicazioni più recenti e gli utenti possano selezionare autonomamente cosa gli serve.

![](media/step-3-office-and-lob-app-delivery-media/step-3-office-and-lob-app-delivery-media-3.png)

## <a name="pc-imaging"></a>Acquisizione immagine PC

Un altro metodo popolare di distribuzione delle app è l'acquisizione immagine del PC. In questo caso, le applicazioni vengono installate attraverso una sequenza di attività o manualmente su un PC campione, quindi viene acquisita un'immagine del sistema con le applicazioni necessarie preinstallate. L'approccio dell'acquisizione immagine per creare e acquisire può far risparmiare tempo quando si effettua il provisioning di nuovi PC, ma ricordare i sistemi operativi e le app nell'immagine può diventare rapidamente poco efficiente. Il modello di aggiornamento cumulativo in Windows 10 e Office 365 ProPlus può aiutare a risolvere questo problema, ma non lo elimina del tutto. Ecco perché consigliamo un approccio che prevede l'uso delle immagini leggero, in cui le applicazioni vengono installate dall'esterno dell'immagine al momento della distribuzione.

![](media/step-3-office-and-lob-app-delivery-media/step-3-office-and-lob-app-delivery-media-4.png)

Se si desidera includere Office 365 ProPlus nell'immagine, tenere presente che utilizza un'attivazione basata sull'utente; non può essere pre-attivato dall'amministratore di sistema. Utilizzare lo strumento di distribuzione di Office per pre-installare Office nel dispositivo di cui si sta acquisendo l'immagine e ignorare l'accesso utente. Gli utenti possono accedere, gli può essere assegnata l'attivazione e possono sfruttare altre funzionalità che utilizzano l'accesso al primo utilizzo.

[Creare una sequenza di attività per installare un sistema operativo](https://docs.microsoft.com/it-IT/sccm/osd/deploy-use/create-a-task-sequence-to-install-an-operating-system)

## <a name="click-to-run"></a>A portata di clic 

Office 365 ProPlus viene installato A portata di clic e A portata di clic sostituisce il packaging basato su MSI in ogni versione del prossimo rilascio di Office 2019 per Windows. Porta con sé una serie di vantaggi, tra cui installazioni più rapide, aggiornamento più rapido ed efficiente e una disinstallazione più semplice.

I programmi distribuiti tramite A portata di clic vengono eseguiti in un ambiente applicativo virtuale sul computer e quindi coesistono con altre applicazioni senza conflitti; occupano anche metà dello spazio su disco che occuperebbero come pacchetto basato su MSI. Poiché A portata di clic supporta lo streaming dei programmi, eseguendo innanzitutto lo streaming delle funzionalità più usate, gli utenti possono iniziare a usare Office in pochi minuti invece di dover attendere che Office venga interamente installato. Ciò è importante non solo per la distribuzione iniziale, significa anche che gli aggiornamenti possono essere facilmente inviati come flusso in background con un minimo impatto sugli utenti.

Se si usa System Center Configuration Manager, è possibile usarlo anche per una distribuzione ampia di Office 365 ProPlus. System Center Configuration Manager (current branch) presenta supporto nativo per lo strumento di personalizzazione di Office aggiornato, la personalizzazione dei pacchetti per A portata di clic al momento dell'installazione e il supporto nativo della gestione degli aggiornamenti software dopo l'installazione.

[Guida alla distribuzione di Office 365 ProPlus](https://docs.microsoft.com/it-IT/deployoffice/deployment-guide-for-office-365-proplus)

[Rimuovere le versioni MSI di Office esistenti quando si effettua l'aggiornamento a Office 365 ProPlus](https://docs.microsoft.com/it-IT/deployoffice/upgrade-from-msi-version)

[Gestire Office 365 ProPlus con Configuration Manager](https://docs.microsoft.com/it-IT/sccm/sum/deploy-use/manage-office-365-proplus-updates)

[Assegnare le app di Office 365 ai dispositivi Windows 10 con Microsoft Intune](https://docs.microsoft.com/it-IT/intune/apps-add-office365)

## <a name="browser-based-apps"></a>App basate su browser

Esistono alcuni elementi da considerare per assicurarsi che le applicazioni basate su browser continuino a funzionare nel modo previsto. Se si dispone di siti Web e app specifici per i quali sono noti problemi di compatibilità con Microsoft Edge, è possibile usare l'elenco siti di modalità Enterprise affinché i siti Web si aprano automaticamente utilizzando Internet Explorer 11.

Inoltre, se si sa che i siti Intranet non funzioneranno correttamente con Microsoft Edge, è possibile configurare tutti i siti Intranet affinché si aprano automaticamente con Internet Explorer 11. Questo processo usa un file XML per gestire l'utilizzo di IE11 per ogni sito, utilizzando Criteri di gruppo per applicare le impostazioni.

Finora, abbiamo trattato metodi di distribuzione ben noti. Ma esistono due nuovi approcci per la distribuzione di app che potrebbe essere interessante prendere in considerazione.

[Che cos'è la modalità Enterprise](https://docs.microsoft.com/it-IT/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode#what-is-enterprise-mode)

## <a name="microsoft-store-for-business"></a>Microsoft Store for Business 

Microsoft Store for Business offre un modo flessibile di individuare, acquisire, gestire e distribuire app gratuite e a pagamento nei dispositivi Windows 10 su vasta scala. Come amministratore IT, è possibile pubblicare app selezionate nel Microsoft Store, insieme ad app personalizzate nello sto privato e assegnare e riutilizzare licenze in base alle proprie esigenze. Gli utenti vengono indirizzati solo a questo store, quindi potranno trovare e installare app approvate.

Le app dello store possono essere create nativamente come app UWP o è possibile usare il Desktop Bridge per creare un nuovo pacchetto delle app esistenti per lo Store e aggiungere esperienze moderne per Windows 10. A parte il codice utilizzato per attivare le esperienze di Windows 10, l'app rimane invariata e continua a essere eseguita in modalità utente con attendibilità totale.

## <a name="msix-containerization"></a>Containerizzazione MSIX

Una nuova opzione per il packaging delle applicazioni è MSIX. MSIX utilizza la tecnologia di containerizzazione disponibile in Windows, apportando i migliori aspetti dei pacchetti A portata di clic, UWP e MSI. Con gli strumenti per eseguire la migrazione dei programmi di installazione esistenti come EXE, MSI, APPV e APPX direttamente in MSIX, vediamo che la containerizzazione MSIX offre un percorso unificato per le diverse tecnologie di installazione in uso oggi. Il supporto di MSIX è incluso nelle versioni correnti di Windows: tutti i dispositivi che eseguono Windows 10 RS5 o versione più recente, includono tutto il necessario per installare ed eseguire le app con MSIX. Windows 10 si integra in modo dinamico con i contenitori MSIX che riceve, mantenendo le applicazioni separate dal sistema operativo.

La containerization consente una disinstallazione e una rimozione dei pacchetti semplici, diversamente da molti dei pacchetti basati su EXE e MSI che possono lasciare elementi nel sistema. Significa anche che è necessario usare esclusivamente le credenziali utente standard per installare le applicazioni, non servono le credenziali Amministratore per installare i contenitori MSIX. I contenitori MSIX sono anche più efficienti da aggiornare. Quando viene pubblicato un aggiornamento, l'uso di differenziali a livello di blocco significa che vengono applicati solo binari completamente nuovi, riducendo il payload dell'aggiornamento, per distribuzioni più rapide con un consumo inferiore della larghezza di banda.

Ulteriori informazioni su MSIX tramite il [sito Community IT MSIX](https://techcommunity.microsoft.com/t5/MSIX/ct-p/MSIX)

## <a name="next-step"></a>Passaggio successivo

## <a name="step-4-user-files-and-settingshttpsakamsmdd4"></a>[Passaggio 4: impostazioni e file utente](https://aka.ms/mdd4)

## <a name="previous-step"></a>Passaggio precedente

## <a name="step-2-directory-and-network-readinesshttpsakamsmdd2"></a>[Passaggio 2: conformità directory e rete](https://aka.ms/mdd2) 