---
title: 'Passaggio 1: preparazione di dispositivi e app'
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
description: Informazioni su come valutare la conformità di dispositivi e app nell'ambiente.
ms.openlocfilehash: a9fa85ea37de06399aa2264b09c61e588edc2107
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868927"
---
# <a name="step-1-device-and-app-readiness"></a><span data-ttu-id="3b276-103">Passaggio 1: preparazione di dispositivi e app</span><span class="sxs-lookup"><span data-stu-id="3b276-103">Step 1: Device and App Readiness</span></span>

<span data-ttu-id="3b276-104">Iniziare il progetto di distribuzione desktop con un inventario dei dispositivi e delle app, con l'assegnazione delle priorità, con l'esecuzione di test sui dispositivi e sulle app cui è stata assegnata la priorità, quindi con la correzione di quanto necessario per prepararsi alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="3b276-104">Begin your desktop deployment project with an inventory of your devices and apps, prioritize what you to move forward, test prioritized apps and devices, then remediate what’s needed to get ready for deployment.</span></span>

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-1.png)

<table>
<thead>
<td><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-3.png" alt="Step 1" height="130" width="130" /></td>
<td><p><span data-ttu-id="3b276-105"><strong>Passaggio 1: preparazione di dispositivi e app</strong></span><span class="sxs-lookup"><span data-stu-id="3b276-105"><strong>Step 1: Device and App Readiness</strong></span></span></p>
<p><span data-ttu-id="3b276-106">Iniziare il progetto di distribuzione desktop con un inventario dei dispositivi e delle app, con l'assegnazione delle priorità, con l'esecuzione di test sui dispositivi e sulle app cui è stata assegnata la priorità, quindi con la correzione di quanto necessario per prepararsi alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="3b276-106">Begin your desktop deployment project with an inventory of your devices and apps, prioritize what you to move forward, test prioritized apps and devices, then remediate what’s needed to get ready for deployment.</span></span></p></td>
<td><a href="https://aka.ms/ddev1" target="_blank"><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-14.png" alt="Step 1" height="120" width="213" /></a></td>
</thead>
</table>

>[!NOTE]
><span data-ttu-id="3b276-p101">La preparazione di dispositivi e app rappresenta il primo passaggio del processo di distribuzione consigliato e copre gli aspetti olistici della compatibilità tra applicazione e hardware. Per vedere il processo di distribuzione della versione desktop completa, visitare il [Centro di distribuzione desktop moderno](https://aka.ms/HowToShift).</span><span class="sxs-lookup"><span data-stu-id="3b276-p101">Device and App Readiness is the first step in our recommended deployment process wheel by covering the holistic aspects of application and hardware compatibility. To see the full desktop deployment process, visit the [Modern Desktop Deployment Center](https://aka.ms/HowToShift).</span></span>
>

<span data-ttu-id="3b276-p102">In passato, l'ostacolo principale per l'aggiornamento dei computer desktop degli utenti era la compatibilità di hardware e applicazioni. Finalmente, passando a Windows 10 e Office 365 ProPlus, praticamente ogni applicazione creata negli ultimi 10 anni sarà compatibile con Windows 10 e qualsiasi componente aggiuntivo COM e macro VBA utilizzato dall'organizzazione nelle versioni precedenti di Office (fino a Office 2010) continuerà a essere compatibile nelle versioni più recenti di Office, senza nessuna modifica.</span><span class="sxs-lookup"><span data-stu-id="3b276-p102">In the past, a major hurdle to upgrading the users’ desktops is application and hardware compatibility. The good news as you plan your shift to Windows 10 and Office 365 ProPlus, is just about any application written in the last 10 years will run on Windows 10, and any COM add-ins and VBA macros your organization used on versions of Office dating back to Office 2010, will continue to work on the latest versions of Office, without modification.</span></span>

<span data-ttu-id="3b276-111">Premesso ciò, a seconda delle dimensioni e della longevità dell'organizzazione, la verifica della compatibilità di hardware e applicazioni rimane comunque un passaggio iniziale fondamentale nel nostro processo di distribuzione a 8 fasi consigliato.</span><span class="sxs-lookup"><span data-stu-id="3b276-111">That said, depending on the size and age of your organization, verifying application and hardware compatibility is likely still an essential initial step in our recommended 8-phase deployment process.</span></span>

<span data-ttu-id="3b276-112">In questo articolo vengono fornite delle indicazioni per guidare gli utenti dalla prima fase (Preparazione di dispositivi e app) usando il nuovo strumento Preparazione aggiornamenti di Windows Analytics, una soluzione basata sul cloud intelligente disponibile con la licenza Windows.</span><span class="sxs-lookup"><span data-stu-id="3b276-112">In this article we take you through that first phase – Device and App Readiness – using the new Windows Analytics Upgrade Readiness tool, an intelligent cloud-based solution available with your Windows license.</span></span>

<span data-ttu-id="3b276-113">Se al momento Windows Analytics non è configurato per l'ambiente o se si desidera iscriversi per una prova, accedere alla [pagina di Windows Analytics](http://www.aka.ms/windowsanalytics) e iniziare.</span><span class="sxs-lookup"><span data-stu-id="3b276-113">If you don’t currently have Windows Analytics set up for your environment or would like to sign up for a trial, go the [Windows Analytics page](http://www.aka.ms/windowsanalytics) and get started.</span></span>

## <a name="recommended-tool-windows-analytics-upgrade-readiness"></a><span data-ttu-id="3b276-114">Strumento consigliato: Preparazione aggiornamenti di Windows Analytics</span><span class="sxs-lookup"><span data-stu-id="3b276-114">Recommended Tool: Windows Analytics Upgrade Readiness</span></span>

<span data-ttu-id="3b276-p103">Preparazione aggiornamenti di Windows Analytics offre numerosi vantaggi rispetto ai sistemi di gestione di desktop tradizionali ed è lo strumento che consigliamo. È senza agente, guida l'utente nelle operazioni che devono essere effettuate e sfrutta le informazioni sulla compatibilità di driver e applicazioni raccolte durante l'aggiornamento di centinaia di milioni di PC utente, per fornire una valutazione dettagliata individuando i problemi relativi alla compatibilità che potrebbero impedire l'aggiornamento, con collegamenti alle correzioni consigliate note di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3b276-p103">Windows Analytics Upgrade Readiness offers many advantages over traditional desktop management systems and is our recommended tool. It is agentless; it guides you through what needs to be done; and, it makes use of application and driver compatibility information gathered through the upgrade of hundreds of millions of consumer PCs, to give you a detailed assessment, identifying compatibility issues that might block your upgrade, with links to suggested fixes known to Microsoft.</span></span>

<span data-ttu-id="3b276-p104">Per configurare Preparazione aggiornamenti di Window Analytics, prima di tutto è necessario configurare un abbonamento ad Azure e includervi un'area di lavoro di Azure Log Analytics. Una volta che il servizio Preparazione aggiornamenti di Windows Analytics è in esecuzione, è possibile registrare qualsiasi dispositivo Windows 7 SP1 o versioni successive connesso a Internet tramite le impostazioni di Criteri di gruppo. È semplicissimo. Non ci sono agenti da distribuire e il flusso di lavoro visivo di Preparazione aggiornamenti di Windows Analytics guida l'utente dalla distribuzione pilota alla distribuzione di produzione. Se si desidera, è possibile esportare i dati da Preparazione aggiornamenti di Windows Analytics agli strumenti di distribuzione software come System Center Configuration Manager, per raggiungere direttamente i PC e creare raccolte non appena diventano disponibili per la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="3b276-p104">To set up Window Analytics Upgrade Readiness you’ll first need to set up an Azure subscription and include an Azure Log Analytics workspace to that. Once you have the Windows Analytics Upgrade Readiness service running, you can then enroll any Internet-connected Windows 7 SP1 or newer device via Group Policy settings. It’s that simple. There are no agents to deploy, and Windows Analytics Upgrade Readiness’s visual workflow guides you from pilot to production deployment. If you wish, you can export data from Windows Analytics Upgrade Readiness to software deployment tools such as System Center Configuration Manager, to target PCs directly and build collections as they become ready for deployment.</span></span>

## <a name="device-and-app-readiness-process"></a><span data-ttu-id="3b276-122">Processo di preparazione di dispositivi e app</span><span class="sxs-lookup"><span data-stu-id="3b276-122">Device and App Readiness Process</span></span>

<span data-ttu-id="3b276-p105">Il processo di preparazione di dispositivi e app è costituito dai quattro passaggi descritti di seguito: 1. Inventario, 2. Assegnazione della priorità, 3. Test, 4. Correzione.</span><span class="sxs-lookup"><span data-stu-id="3b276-p105">Device and App Readiness compromises four steps: 1. Inventory, 2. Prioritize, 3. Test, 4. Remediate. Let’s look at each of these in turn.</span></span>

### <a name="1-inventory"></a><span data-ttu-id="3b276-p106">1\. Inventario</span><span class="sxs-lookup"><span data-stu-id="3b276-p106">1\. Inventory</span></span>

<span data-ttu-id="3b276-131">Il servizio Preparazione aggiornamenti di Windows Analytics si avvale di un processo senza agente per effettuare un inventario dei computer, delle applicazioni e dei componenti aggiuntivi di Office tra i vari desktop in uso.</span><span class="sxs-lookup"><span data-stu-id="3b276-131">Windows Analytics Upgrade Readiness service uses an agent-less process to inventory the computers, applications and Office add-ins across your desktop estate.</span></span>

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-3.png)

<span data-ttu-id="3b276-132">Inoltre, fornisce dei report sui siti Internet più visitati, sulle app e sui percorsi Intranet per aiutare l'utente con la fase di test della compatibilità successiva.</span><span class="sxs-lookup"><span data-stu-id="3b276-132">It also provides reports on highly visited Internet sites, apps and Intranet locations to help you with compatibility testing later.</span></span>

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-4.png)

### <a name="2-prioritize"></a><span data-ttu-id="3b276-p107">2\. Assegnazione delle priorità</span><span class="sxs-lookup"><span data-stu-id="3b276-p107">2\. Prioritize</span></span>

<span data-ttu-id="3b276-135">Una volta effettuato l'inventario, Preparazione aggiornamenti di Windows Analytics consente di identificare e classificare in ordine di priorità l'hardware e le app più comuni utilizzati nell'organizzazione, oltre a indicare su cosa concentrarsi per sbloccare il maggior numero possibile di PC per la distribuzione,</span><span class="sxs-lookup"><span data-stu-id="3b276-135">With inventory taken, Windows Analytics Upgrade Readiness helps you to identify and prioritize the most common apps and hardware used in your organization, and what to focus on to unblock as many PCs as possible for deployment,</span></span>

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-5.png)

<span data-ttu-id="3b276-136">fornendo anche delle indicazioni che aiutino l'utente a valutare se siano necessari degli aggiornamenti per risolvere i problemi durante il passaggio successivo: il test.</span><span class="sxs-lookup"><span data-stu-id="3b276-136">also providing guidance to help you assess the updates are necessary to resolve issues during the next step: testing.</span></span>

### <a name="3-testing"></a><span data-ttu-id="3b276-p108">3\. Test</span><span class="sxs-lookup"><span data-stu-id="3b276-p108">3\. Testing</span></span>

<span data-ttu-id="3b276-p109">Si noterà che la maggior parte delle applicazioni, dei driver e dei componenti aggiuntivi di cui viene effettuato l'inventario funziona com'è. Per gli elementi di cui Preparazione aggiornamenti di Windows Analytics rileva problemi, vengono fornite informazioni note, come dove trovare gli aggiornamenti delle versioni per risolvere i problemi relativi alla compatibilità. Anziché spendere tempo e risorse nella risoluzione di problemi complessi di dispositivi meno recenti e applicazioni non fondamentali e con una distribuzione limitata, è possibile concentrarsi sulla collaborazione con gli utenti per ritirare e sostituire tali elementi.</span><span class="sxs-lookup"><span data-stu-id="3b276-p109">You will find that most of the applications, drivers, and add-ins inventoried, will work as-is. For items Windows Analytics Upgrade Readiness assesses to have issues, it provides you with known information, including where to find version updates to resolve compatibility problems. Rather than devoting time and resource resolving complex issues in non-critical, sparsely deployed applications and older devices, you may choose instead to work with users to retire and replace these items.</span></span>

<span data-ttu-id="3b276-p110">È possibile utilizzare Preparazione aggiornamenti di Windows Analytics anche per valutare i problemi di compatibilità basati sul browser, identificando siti Web e app Web a cui gli utenti continuano ad accedere con controlli ActiveX, oggetti browser helper, VBScript o altre tecnologie legacy non supportate dal browser Microsoft Edge. Gli utenti dovranno continuare a usare Internet Explorer 11 per questi siti ed è possibile aggiungerli all'[elenco di siti con modalità Enterprise](https://docs.microsoft.com/it-IT/microsoft-edge/deploy/emie-to-improve-compatibility) con Enterprise Mode Site List Manager.</span><span class="sxs-lookup"><span data-stu-id="3b276-p110">You can use Windows Analytics Upgrade Readiness to assess browser-based compatibility issues too, identifying websites and web apps accessed by users still using ActiveX controls, Browser Helper Objects, VBScript, or other legacy technology not supported by the Microsoft Edge browser. Your users will still need to use Internet Explorer 11 for these sites, and you can add them to the [Enterprise Mode site list](https://docs.microsoft.com/it-IT/microsoft-edge/deploy/emie-to-improve-compatibility), using the Enterprise Mode Site List Manager.</span></span>

<span data-ttu-id="3b276-144">Inoltre, per facilitare il passaggio a Office 365 ProPlus, è consigliabile usare [Readiness Toolkit for Office](https://docs.microsoft.com/it-IT/deployoffice/use-the-readiness-toolkit-to-assess-application-compatibility-for-office-365-pro) per testare la compatibilità dei componenti aggiuntivi e delle macro Microsoft Visual Basic for Applications (VBA).</span><span class="sxs-lookup"><span data-stu-id="3b276-144">Additionally, to assist in your move to Office 365 ProPlus, you may wish to make use of the [Readiness Toolkit for Office](https://docs.microsoft.com/it-IT/deployoffice/use-the-readiness-toolkit-to-assess-application-compatibility-for-office-365-pro) to test the compatibility of your add-ins and Microsoft Visual Basic for Applications (VBA) macros.</span></span>

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-6.png)

### <a name="4-remediation"></a><span data-ttu-id="3b276-p111">4\. Correzione</span><span class="sxs-lookup"><span data-stu-id="3b276-p111">4\. Remediation</span></span>

<span data-ttu-id="3b276-p112">La fase finale della preparazione di dispositivi e app consiste nella "correzione". Sarà necessario raccogliere i pacchetti driver e software obbligatori che verranno usati per sostituire o aggiornare le versioni precedenti nell'ambito del processo di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="3b276-p112">As the final phase of device and app readiness is to ‘remediate’. Here you’ll want to collect the required software or driver packages; you are going to use these to supersede or update older versions as part of the deployment process.</span></span>

![](media/step-1-device-and-app-readiness-media/step-1-device-and-app-readiness-media-7.png)

<span data-ttu-id="3b276-p113">Man mano che vengono esaminati problemi, un numero sempre maggiore di PC diventa "pronto per la distribuzione". Ciò significa che sia i driver che le app sui PC vengono considerati compatibili con la versione di Windows 10 che si intende utilizzare per la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="3b276-p113">As you work through the list remediating issues, you’ll see that more and more PCs become “Ready for Deployment”. This means that both the drivers and apps on the PCs are noted as compatible with the version of Windows 10 you are targeting for deployment.</span></span>

## <a name="continued-use-of-telemetry-tools"></a><span data-ttu-id="3b276-151">Uso continuo degli strumenti di telemetria</span><span class="sxs-lookup"><span data-stu-id="3b276-151">Continued use of telemetry tools</span></span>

<span data-ttu-id="3b276-p114">Preparazione aggiornamenti di Windows Analytics non è solo uno strumento che consente di passare a Windows 10 e Office 365 ProPlus. Una volta installato Windows 10 e Office 365 nei computer desktop, è possibile usarlo per gestire la distribuzione e gli aggiornamenti delle funzionalità semestrali per avere sempre le ultime versioni a disposizione.</span><span class="sxs-lookup"><span data-stu-id="3b276-p114">Windows Analytics Upgrade Readiness isn’t just a tool to help you shift to Windows 10 and Office 365 ProPlus. Once you have desktops running on Windows 10 and Office 365 you can use it to help maintain your deployment and manage semi-annual Feature Updates so that you can stay current.</span></span>

## <a name="next-step"></a><span data-ttu-id="3b276-154">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="3b276-154">Next Step</span></span> 

## <a name="step-2-directory-and-network-readinesshttpsakamsmdd2"></a>[<span data-ttu-id="3b276-155">Passaggio 2: conformità directory e rete</span><span class="sxs-lookup"><span data-stu-id="3b276-155">Step 2: Directory and Network Readiness</span></span>](https://aka.ms/mdd2)