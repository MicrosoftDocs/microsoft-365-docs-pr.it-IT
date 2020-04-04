---
title: Passaggio 4 - Migrazione delle impostazioni e dei file utente
f1.keywords:
- NOCSH
ms.author: jogruszc
author: JGruszczyk
manager: jemed
ms.date: 06/10/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Informazioni su come eseguire la migrazione di file e impostazioni degli utenti.
ms.openlocfilehash: f17b11efe889359f97087ac5d96ffa968ca8cd88
ms.sourcegitcommit: 9ca28ae8f7804eb488cf76ca4b09fe88787e0a49
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2020
ms.locfileid: "43113542"
---
# <a name="step-4-user-files-and-settings-migration"></a>Passaggio 4: migrazione delle impostazioni e dei file utente

Spostare i file e le impostazioni degli utenti ai PC nuovi o aggiornati è un processo critico; non è possibile sbagliare. È possibile eseguire manualmente la migrazione di ogni PC o scegliere uno dei tanti modi per automatizzare il processo. Qualsiasi sia il metodo di migrazione scelto, devono essere messe in conto tre considerazioni principali: il trasferimento dei file degli utenti, le impostazioni e la gestione di Windows 10 Start e dei layout della barra delle applicazioni.

![](../media/step-4-user-files-and-settings-migration-media/step-4-user-files-and-settings-migration-media-1.png)

<table>
<thead>
<td><img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-7.png" alt="Step 4" height="135" width="135" /></td>
<td><p><strong>Passaggio 4: impostazioni e file utente</strong></p>
<p>Durante l'aggiornamento o la sostituzione dei PC, è possibile risparmiare tempo automatizzando il backup e il ripristino dello stato utente. Le nuove opzioni per la sincronizzazione dei file sul cloud consentono di applicare la sincronizzazione per utente delle cartelle desktop, documenti e immagini in OneDrive per l'accesso semplificato ai file da nuove installazioni di Windows.</p></td>
<td><a href="https://aka.ms/ddev4" target="_blank"><img src="../media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-17.png" alt="Step 4" height="130" width="231" /></a></td>
</thead>
</table>

>[!NOTE]
>Anche se è possibile continuare a utilizzare i processi di migrazione utilizzati in passato, con il passaggio a Office 365 ProPlus consigliamo di usare lo "Spostamento di cartelle note" di OneDrive (vedere di seguito). Per vedere l’intero processo di distribuzione, visitare il [Centro distribuzione desktop](https://aka.ms/HowToShift).
>

Una delle attività più complesse e spesso più manuale di una distribuzione su vasta scala è quella del trasferimento dei file e delle impostazioni degli utenti. In questo articolo, illustreremo le opzioni disponibili per eseguire la migrazione degli utenti in PC nuovi, aggiornati o di cui è stata ricreata l'immagine.

## <a name="manual-migration"></a>Migrazione manuale

Quando arriva il momento di decidere cosa mantenere quando si passa a un nuovo PC o a una nuova versione di Windows, alcuni utenti vorrebbero conservare tutto, altri vorrebbero approfittare dell'occasione per pulire le unità. Per questo motivo, alcuni reparti IT scelgono di gestire la migrazione dei file degli utenti manualmente, a volte inviando team di supporto dagli utenti e a volte allestendo centri di supporto dove gli utenti possono portare i propri PC. In entrambi i modi, gli utenti vengono coinvolti nel decidere cosa conservare e cosa eliminare.

Questa opzione è disponibile a seconda dell'entità della migrazione che si intende eseguire. Ovviamente, è limitata a tempistiche e logistiche richieste per lavorare direttamente con gli utenti, per capire le loro esigenze e copiare i file nei nuovi PC o in quelli aggiornati.

Se si sceglie di eseguire una migrazione manuale, usare una delle opzioni seguenti per automatizzare la migrazione oppure richiedere l'assistenza di altre persone.

## <a name="automated-migration-using-usmt"></a>Migrazione automatica tramite USMT 

Per le distribuzioni su larga scala, è possibile automatizzare buona parte del processo utilizzando gli strumenti di automazione della distribuzione basati su sequenze di attività quali Microsoft Endpoint Configuration Manager o Microsoft Deployment Toolkit (MDT). Entrambe le soluzioni adottano l'Utilità di migrazione stato utente (USMT) nell'ambito del processo di distribuzione end-to-end. USMT fa parte di [Windows Assessment and Deployment Kit (Windows ADK)](https://docs.microsoft.com/windows-hardware/get-started/adk-install)

USMT acquisisce account utente, file utente, impostazioni del sistema operativo e delle applicazioni, quindi ne esegue la migrazione a una nuova installazione di Windows. Inoltre, offre all'amministratore IT la possibilità di controllare esattamente cosa viene migrato e, nel caso, escludere tipi di file non desiderati, ad esempio, file audio e video o file eseguibili.

Durante il processo di migrazione, è necessario avere sufficiente capacità di archiviazione sul server per usarlo come archivio delle migrazioni temporaneo. Qui USMT offre due importanti funzionalità. Innanzitutto, è in grado di stimare, per PC, la quantità di archiviazione necessaria. In secondo luogo, consente agli archivi delle migrazioni di essere crittografati, riducendo il rischio di violazione dei dati mente si trova nei file server.

Se si sta eseguendo un aggiornamento del PC e non si sta formattando la partizione di Windows principale, è anche possibile utilizzare un archivio delle migrazioni con collegamento reale con USMT. Questo processo mantiene lo stato utente sul PC mentre il sistema operativo e le app precedenti vengono rimossi e aggiornati. Con il processo di ripristino derivante dalla stessa partizione locale, questa opzione garantisce miglioramenti delle prestazioni significativi e riduce il traffico di rete.

[Panoramica sull'Utilità migrazione stato utente (USMT)](https://docs.microsoft.com/windows/deployment/usmt/usmt-overview)

## <a name="onedrive-known-folder-move"></a>Spostamento di cartelle note di OneDrive

Se gli utenti sono su OneDrive o si sta aggiungendo OneDrive nell'ambito della distribuzione, esiste una nuova opzione disponibile. Utilizzando il cloud per sincronizzare i file utente, la funzionalità "Spostamento di cartelle note" di OneDrive offre un livello di flessibilità non possibile con opzioni di migrazione dei file basate sulla rete locale. Se abilitata prima della migrazione, questa funzionalità offre accesso sicuro ai nuovi PC e a quelli aggiornati ed elimina la necessità di creare archivi delle migrazioni temporanei sui propri server. Inoltre, è completamente trasparente per l'utente.

[Reindirizzare e spostare le cartelle note di Windows su OneDrive](https://docs.microsoft.com/onedrive/redirect-known-folders)

Se si usa già OneDrive, sarà noto che gli utenti possono selezionare le cartelle e i percorsi che desiderano sincronizzare da OneDrive a SharePoint sul proprio dispositivo; tuttavia, ciò grava sull'utente finale. Con lo Spostamento di cartelle note, è possibile selezionare le cartelle Documenti, Desktop e Immagini in un profilo utente e proteggerle tutte su OneDrive. Un utente può farlo da solo o, importante per questo scenario, l'amministratore può [applicare la funzionalità tramite le impostazioni Criteri di gruppo](https://docs.microsoft.com/onedrive/use-group-policy?redirectSourcePath=%252fen-us%252farticle%252fUse-Group-Policy-to-control-OneDrive-sync-client-settings-0ecb2cf5-8882-42b3-a6e9-be6bda30899c).

Con lo Spostamento di cartelle note, gli utenti non modificano il flusso di lavoro: tutto rimane uguale, durante e al termine della sincronizzazione con OneDrive. Attraverso Criteri di gruppo, è anche possibile scegliere se informare o meno gli utenti che documenti, immagini e desktop sono protetti su OneDrive. Se si sceglie di non farlo, tutto si verifica automaticamente in background. Gli utenti sapranno solo quando possono ritirare il PC o quando il PC sarà stato aggiornato. Non appena effettueranno l'accesso al proprio account OneDrive, i file saranno di nuovo disponibili e verranno ripristinati nel nuovo PC. Ovviamente, OneDrive rende i file disponibili in modo sicuro in qualsiasi momento da telefoni o altri dispositivi.

L'autenticazione per OneDrive con Azure Active Directory: quindi per maggiore sicurezza, è possibile attivare facilmente l'autenticazione a più fattori ed è possibile impostare criteri per controllare la larghezza di banda utilizzata da OneDrive per il caricamento e il download per limitare l'attività di rete.

Non è necessario eseguire la migrazione di ogni utente contemporaneamente. È possibile distribuire in fasi le impostazioni di Criteri di gruppo oppure [limitare la sincronizzazione dei file ai PC aggiunti al dominio](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenantSyncClientRestriction?view=sharepoint-ps).

## <a name="start-menu-and-task-bar-customization"></a>Personalizzazione del menu Start e della barra delle applicazioni

OneDrive è progettato per sincronizzare e proteggere file e cartelle; non sincronizza le impostazioni delle applicazioni o di Windows. In passato, per farlo, si usava il metodo Copia profilo per configurare layout standard per le impostazioni di menu Start e barre delle applicazioni degli utenti. In Windows 10 Pro Enterprise ed Education, è possibile usare Criteri di gruppo, MDM, PowerShell o il provisioning dei pacchetti per distribuire [layout di Start e della barra delle applicazioni personalizzati](https://docs.microsoft.com/windows/configuration/windows-10-start-layout-options-and-policies). Non è necessario creare una nuova immagine e il layout può essere aggiornato semplicemente sovrascrivendo il file .xml contenente il layout.

Per creare un nuovo layout basta configurare un sistema di esempio e utilizzare il cmdlet di PowerShell [Export-StartLayout](https://docs.microsoft.com/powershell/module/startlayout/export-startlayout?view=win10-ps) per generare un file XML, quindi posizionare il file in una condivisione di rete o memorizzarlo nella cache locale durante la sequenza di distribuzione; deve semplicemente essere raggiungibile come file di sola lettura quando l'utente accede. È possibile quindi usare il criterio o il cmdlet [Import-StartLayout](https://docs.microsoft.com/powershell/module/startlayout/import-startlayout?view=win10-ps) per fare riferimento a questo file.

## <a name="removing-unwanted-in-box-apps"></a>Rimozione delle app incluse non desiderate

Windows 10 include molte app integrate utili nell'installazione standard, ma gli amministratori potrebbero voler rimuoverne alcune dai PC gestiti e magari configurare un'installazione personalizzata per impedire a queste app di tornare, ad esempio XBOX o Zune Music. È possibile recuperare un elenco di queste app tramite i comandi [PowerShell Get-AppxPackage](https://technet.microsoft.com/library/hh856044.aspx) e rimuovere quelle non desiderate con il comando [Remove-AppxPackage](https://technet.microsoft.com/library/hh856038.aspx). In alternativa, è possibile montare il file Windows Image (.img) offline prima della distribuzione ed estrarre i pacchetti non desiderati utilizzando lo strumento da riga di comando [Deployment Image Servicing and Management (DISM)](https://docs.microsoft.com/windows-hardware/manufacture/desktop/what-is-dism) e il comando [Remove-AppxProvisionedPackage](https://docs.microsoft.com/powershell/module/dism/remove-appxprovisionedpackage?view=win10-ps).

## <a name="next-step"></a>Passaggio successivo

## <a name="step-5-security-and-compliance-considerations"></a>[Passaggio 5: considerazioni sulla sicurezza e conformità](https://aka.ms/mdd5)

## <a name="previous-step"></a>Passaggio precedente

## <a name="step-3-office-and-lob-app-delivery"></a>[Passaggio 3: distribuzione di Office e app line-of-business](https://aka.ms/mdd3)
