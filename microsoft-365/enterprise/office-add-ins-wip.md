---
title: Proteggere i documenti dell'organizzazione che eseguono i componenti aggiuntivi di Microsoft Office-Microsoft 365 Enterprise | Documenti Microsoft
description: In questo articolo viene descritto come utilizzare WIP e Intune per proteggere i dati dell'organizzazione nei documenti che eseguono i componenti aggiuntivi di Office.
author: barlanmsft
manager: angrobe
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 08/14/2017
ms.author: barlan
ms.reviewer: jsnow
ms.custom: it-pro
ms.openlocfilehash: 6871f288a7e5849b147cbf0aedb056f84575f376
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32290761"
---
# <a name="use-wip-and-intune-to-protect-enterprise-data-in-documents-running-office-add-ins"></a>Usare WIP e Intune per proteggere i dati aziendali contenuti nei documenti che usano i componenti aggiuntivi per Office
Quando gli utenti di un'organizzazione usano i componenti aggiuntivi per Office per interagire con i dati dell'organizzazione viene introdotto un potenziale rischio di perdita di alcuni dati. È possibile usare Windows Information Protection (WIP) e Microsoft Intune per proteggere i dati aziendali quando gli utenti usano i componenti aggiuntivi per Office.

[WIP](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/protect-enterprise-data-using-wip), in precedenza noto come Protezione dei dati aziendali, consente alle aziende di proteggere la proprietà intellettuale e i dati aziendali. WIP consente di proteggere le app e i dati aziendali da perdite di dati accidentali, sia sui dispositivi di proprietà dell'azienda, sia su quelli personali che i dipendenti portano al lavoro, senza richiedere modifiche all'ambiente o altre app.

[Intune](https://www.microsoft.com/cloud-platform/microsoft-intune) offre un ampio set di strumenti per gestire ambienti per dispositivi mobili complessi. La combinazione di opzioni di gestione di applicazioni mobili e gestione dei dispositivi di Intune offre ad amministratori IT e utenti finali la flessibilità necessaria per gestire e proteggere la produttività dei dispositivi mobili.

È possibile usare Intune per [creare e distribuire criteri WIP](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/overview-create-wip-policy). Con Intune è possibile scegliere le app protette e il livello di protezione WIP, nonché trovare i dati aziendali nella rete.

Con WIP e Intune:

-   Le aziende possono assicurarsi che i criteri vengano applicati in modo adeguato ai dati aziendali, anche quando questi vengono scaricati sui dispositivi personali.

-   Le aziende possono usare una formazione contestuale sui criteri per informare gli utenti sulle modalità di protezione dalla divulgazione accidentale dei dati a servizi e app non gestiti.

-   Gli utenti finali possono mantenere la conformità ai criteri relativi ai dati aziendali senza interrompere il normale flusso di lavoro.

-   Gli utenti finali possono passare facilmente dagli strumenti di lavoro a quelli per la produttività personale e viceversa.

WIP e Intune vengono eseguiti in background e sono praticamente invisibili quando gli utenti non mescolano contenuto personale e aziendale.

I [componenti aggiuntivi per Office](https://dev.office.com/docs/add-ins/overview/office-add-ins) si basano su tecnologie Web. Arricchiscono le applicazioni di Office con la potenza e le informazioni del Web. I componenti aggiuntivi interagiscono con il contenuto in un'applicazione di Office tramite le API disponibili in Office.js. I principi fondamentali su cui si basano i componenti aggiuntivi per Office includono:

-   **Sicurezza**: l'architettura della piattaforma JavaScript di Office assicura che il codice del componente aggiuntivo sia in modalità sandbox e venga eseguito in un processo distinto rispetto all'applicazione host di Office. Ciò consente alla piattaforma di intraprendere un'azione correttiva quando un componente aggiuntivo non soddisfa gli standard di prestazioni o è potenzialmente dannoso inviando una notifica all'utente e, in alcuni casi, disabilitando il componente aggiuntivo. Questa architettura funziona su tutte le piattaforme che supportano i componenti aggiuntivi per Office.

-   **Resilienza**: la natura "out-of-process" della piattaforma dei componenti aggiuntivi assicura che il componente aggiuntivo non influisca sulle prestazioni o sull'esperienza utente dell'applicazione host di Office. Questo è fondamentale per mantenere Office veloce e reattivo alle azioni dell'utente.

-   **Multipiattaforma**: i componenti aggiuntivi possono essere eseguiti su tutte le piattaforme in cui viene eseguito Office. Sono attualmente supportati in Windows, Office Online, Mac e iPad. Presto sarà disponibile il supporto per i componenti aggiuntivi sulle piattaforme Android e Universal.

È possibile usare i componenti aggiuntivi per Office con contenuto aziendale e potenzialmente sensibile all'interno di un documento. In base ai principi di estendibilità dell'applicazione, i componenti aggiuntivi ereditano l'accesso dai criteri dell'applicazione host. Ad esempio, se le impostazioni di WIP impediscono a Word di accedere al contenuto aziendale, i componenti aggiuntivi non potranno accedere a questo tipo di contenuto in un documento di Word.

Uno degli obiettivi per i componenti aggiuntivi è l'eliminazione dei problemi gravi per gli utenti finali consentendo allo stesso tempo agli amministratori dell'organizzazione di bloccare i componenti aggiuntivi se necessario. I principi fondamentali per i componenti aggiuntivi per Office relativamente all'abilitazione della protezione dei dati includono:

-   Offrire agli amministratori IT un modo per bloccare il caricamento dei componenti aggiuntivi.

-   Ridurre o eliminare il lavoro degli amministratori per preparare i componenti aggiuntivi per l'uso in azienda.

-   Ridurre al minimo richieste di conferma e messaggi per gli utenti finali durante l'uso del componente aggiuntivo.

-   Eliminare le richieste di conferma da parte degli utenti finali quando il documento e il componente aggiuntivo hanno lo stesso contesto.

## <a name="add-ins-and-wip"></a>Componenti aggiuntivi e WIP

Quando si abilita WIP nel proprio ambiente, è possibile abilitare gli scenari seguenti per i componenti aggiuntivi per Office:

-   I componenti aggiuntivi per Office vengono attivati usando il contesto del documento. Per Outlook il contesto per il componente aggiuntivo si basa sulla cassetta postale attiva corrente. Le autorizzazioni per il componente aggiuntivo sono chiaramente definite nella richiesta di conferma dell'attendibilità prima che il componente aggiuntivo venga attivato. L'utente decide se il componente aggiuntivo è appropriato in un documento specifico e se consentirne o meno l'esecuzione.

-   Gli amministratori possono usare i criteri di gruppo per bloccare tutti i componenti aggiuntivi di Office Store o tutti i componenti aggiuntivi per Office. In questo modo, gli utenti potranno attivare solo i componenti aggiuntivi attendibili contenuti in un [catalogo aziendale SharePoint o Office 365](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog).

-   Gli amministratori possono bloccare i componenti aggiuntivi a livello di firewall mediante la gestione di dispositivi mobili (MDM). Si noti che ciò non funziona in scenari con dispositivi mobili o Bring Your Own Device (BYOD).

-   I componenti aggiuntivi applicano l'operazione di copia e incolla tra contesti aziendali e personali. Ad esempio, quando un utente copia dal componente aggiuntivo di un contesto aziendale e incolla in un documento personale, viene visualizzata la richiesta di conferma predefinita dell'operazione di copia e incolla tra contesti.

La tabella seguente illustra il comportamento previsto del componente aggiuntivo in contesti e documenti aziendali e personali quando WIP è abilitato.

> [!NOTE]
> - Le operazioni taglia, copia e incolla all'interno e all'esterno dell'applicazione host funzionano come previsto in tutti gli scenari.
> - Il trasferimento dei dati ai servizi del componente aggiuntivo non è protetto in tutti gli scenari.

|**Tipo di documento o cassetta postale**|**Componente aggiuntivo in contesto personale**|**Componente aggiuntivo in contesto aziendale**|
|:----------------|:-------------------------------------------------|:---------------------------------------------------|
|**Personale**     |Il componente aggiuntivo viene caricato nel contesto personale.<br><br>L'accesso agli URL aziendali non è consentito (anche se nel dominio della propria app).<br><br>L'accesso agli URL personali è consentito|Il caricamento o l'attivazione del componente aggiuntivo non riesce.<br><br>Se il contesto del documento è elevato (ad esempio, tramite il salvataggio in un percorso aziendale):<br><br>- L'accesso agli URL aziendali è consentito.<br><br>- L'accesso agli URL personali è consentito.|
|**Aziendale**   |Il componente aggiuntivo viene caricato nel contesto aziendale.<br><br>L'accesso agli URL aziendali è consentito.<br><br>L'accesso agli URL personali è consentito.|Il componente aggiuntivo viene caricato nel contesto aziendale.<br><br>L'accesso agli URL aziendali è consentito.<br><br>L'accesso agli URL personali è consentito.|
|**Non salvato**      |Il componente aggiuntivo viene caricato nel contesto personale.<br><br>L'accesso agli URL aziendali non è consentito (anche se nel dominio della propria app).<br><br>L'accesso agli URL personali è consentito.|Il componente aggiuntivo viene caricato nel contesto aziendale e il documento viene automaticamente convertito al contesto aziendale. Ciò significa che il documento deve essere salvato in un percorso aziendale.<br><br>L'accesso agli URL aziendali è consentito. L'accesso agli URL personali è consentito.            |


## <a name="add-ins-and-intune"></a>Componenti aggiuntivi e Intune

In Office per iPad i componenti aggiuntivi per Office sono attualmente supportati per Word, Excel e PowerPoint. Outlook attualmente supporta i componenti aggiuntivi in iOS (iPad e iPhone). Gli amministratori di Outlook possono disattivare i componenti aggiuntivi per impostazione predefinita, inclusi quelli installati dagli sviluppatori, e abilitare solo i componenti aggiuntivi specifici approvati dall'organizzazione. La tabella seguente descrive il supporto per gli scenari di protezione dei dati per i componenti aggiuntivi in esecuzione in Office per i dispositivi iOS che usano gli strumenti di Protezione app di Intune.

> [!NOTE]
> Per informazioni sui componenti aggiuntivi di Outlook in esecuzione su dispositivi Android e iOS, vedere [Gestire l'accesso utente ai componenti aggiuntivi per Outlook](https://technet.microsoft.com/library/jj943757(v=exchg.150).aspx) e [Componenti aggiuntivi per Outlook](https://technet.microsoft.com/library/jj943753(v=exchg.150).aspx).

|**Tipo di documento o cassetta postale**|**Componenti aggiuntivi in contesto personale per iOS con Protezione app di Intune<sup>*</sup>**|**Componenti aggiuntivi in contesto aziendale per iOS con Protezione app di Intune<sup>*</sup>**|
|:-----|:-----|:-----|
|**Personale**|La presenza di Protezione app di Intune nei documenti personali non influisce sull'uso dei componenti aggiuntivi.|La presenza di Protezione app di Intune nei documenti personali non influisce sull'uso dei componenti aggiuntivi.|
|**Aziendale**|L'attivazione dei componenti aggiuntivi personali è consentita.<br><br>I criteri di Protezione app di Intune sono in grado di proteggere le operazioni taglia, copia, incolla e gli scenari di trasferimento dei dati tra il componente aggiuntivo e le altre applicazioni presenti sul dispositivo.<br><br>Il trasferimento dei dati ai servizi del componente aggiuntivo non è protetto.|L'attivazione dei componenti aggiuntivi aziendali è consentita. Gli amministratori possono controllare quali componenti aggiuntivi vengono pubblicati tramite gli strumenti di gestione di Office [(Distribuzione centralizzata di Office 365)](https://support.office.com/article/Deploy-Office-add-ins-in-the-Office-365-admin-center-737e8c86-be63-44d7-bf02-492fa7cd9c3f).<br><br>I criteri di Protezione app di Intune sono in grado di proteggere le operazioni taglia, copia, incolla e gli scenari di trasferimento dei dati tra il componente aggiuntivo e le altre applicazioni presenti sul dispositivo.<br><br>Il trasferimento dei dati ai servizi del componente aggiuntivo non è protetto.|

>**<sup>*</sup>** Gli amministratori possono usare la [Distribuzione centralizzata di Office 365](https://support.office.com/article/Deploy-Office-add-ins-in-the-Office-365-admin-center-737e8c86-be63-44d7-bf02-492fa7cd9c3f) per distribuire i componenti aggiuntivi di Word, Excel e PowerPoint a singoli utenti, gruppi o a un'organizzazione direttamente dall'interfaccia di amministrazione di Office 365 o usando gli script di PowerShell. Quando l'utente apre un'applicazione di Office in Windows, Mac o in Office Online, il componente aggiuntivo viene automaticamente installato sulla barra multifunzione.

## <a name="summary"></a>Riepilogo

Visti i principi su cui si basano i componenti aggiuntivi per Office, WIP e Intune consentono agli amministratori di gestire i dati aziendali e offrono agli utenti finali gli strumenti necessari per svolgere il proprio lavoro. Ciò crea un potenziale rischio di divulgazione dei dati aziendali all'esterno dell'organizzazione. Le API JavaScript di Office attualmente non offrono agli sviluppatori il modo di riconoscere il tipo di dati trasmesso tra il documento di Office e il componente aggiuntivo. Gli sviluppatori sono quindi costretti a presentare all'utente molteplici richieste di conferma e in alcuni casi i file personali vengono erroneamente contrassegnati come file aziendali determinando effetti negativi sull'esperienza utente e il mancato allineamento ai principi relativi alla protezione dei dati.

Microsoft si impegna a proteggere i dati dei clienti e continuerà a investire per migliorare le tecnologie e l'esperienza d'uso di Intune e WIP per i clienti.

## <a name="learn-more"></a>Altre informazioni

-   [Linee guida generali e procedure consigliate per Windows Information Protection (WIP)](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/guidance-and-best-practices-wip)

-   [Informazioni su Intune](https://docs.microsoft.com/intune/introduction-intune)

-   [Panoramica dei metodi di registrazione dei dispositivi](https://docs.microsoft.com/sccm/mdm/plan-design/device-enrollment-methods)

-   [Modificare l'autorità di gestione dei dispositivi mobili](https://docs.microsoft.com/sccm/mdm/deploy-use/change-mdm-authority)

-   [Prepararsi alla configurazione dei criteri di protezione delle app per Windows 10](https://docs.microsoft.com/intune-classic/deploy-use/get-ready-to-configure-app-protection-policies-for-windows-10)
