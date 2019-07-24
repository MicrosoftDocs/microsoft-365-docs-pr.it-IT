---
title: Centro di distribuzione desktop
ms.author: jogruszc
author: JGruszczyk
manager: jemed
ms.date: 06/01/19
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Panoramica del centro di distribuzione desktop.
ms.openlocfilehash: b19c2f5df6368fd6066b6506a17ed81ddf57f8c6
ms.sourcegitcommit: 275d5c2d74e55ef6488594165367b02e735dc540
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/23/2019
ms.locfileid: "35834029"
---
# <a name="desktop-deployment-center"></a>Centro di distribuzione desktop

<table border="0">
 <tr>
 <td>
  <strong>Aggiornamento da Windows 7 a Windows 10</strong><p>Il supporto esteso di Windows 7 termina il 14 gennaio 2020. L'aggiornamento sul posto da Windows 7 a Windows 10 rappresenta il metodo di distribuzione più rapido. È possibile <a href="https://docs.microsoft.com/it-IT/microsoft-365/enterprise/windows-7-to-windows-10-upgrade-manual">aggiornare un singolo PC</a> o <a href="https://docs.microsoft.com/it-IT/microsoft-365/enterprise/windows-7-to-windows-10-upgrade-automated">aggiornare migliaia di PC con System Center Configuration Manager</a>. Non è necessario concentrarsi sulla consegna dell'app, sulla migrazione dei file, sulla creazione dell'immagine personalizzata o sull'abilitazione di servizi basati sul cloud con aggiornamenti sul posto. È possibile usare gli strumenti già a disposizione per aggiornare PC esistenti e concentrarsi sui passaggi di distribuzione seguenti per gli aggiornamenti: </td>
 </tr>
 <tr>
 <td>
    <table border="0">
     <tr>
     <td>
        <table border="0">
             <tr>
                  <td>
                  <img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-5.png" alt="Upgrade ConfigMgr" height="144" width="144" />
              </td>
              <td>
              <strong>Aggiornare ConfigMgr a Current Branch</strong>
                  </td>
                 </tr>
                </table>
    </td>
        <td>
        <table border="0">
             <tr>
                  <td>
                  <img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-3.png" alt="Device and App Readiness" height="144" width="144" />
              </td>
              <td>
              <strong>Convalidare la conformità di dispositivi e app</strong>
                  </td>
                 </tr>
                </table>
    </td>
        <td>
        <table border="0">
             <tr>
                  <td>
                  <img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-9.png" alt="Upgrade Windows 7 PCs" height="144" width="144" />
              </td>
              <td>
              <strong>Aggiornare PC con Windows 7 a Windows 10</strong>
                  </td>
                 </tr>
                </table>
        </td>
        </tr>
    </td>
    </tr>
    <tr>
    <td>
Parte del passaggio di conformità della directory e della rete per le organizzazioni che usano SCCM </td>
    <td>
Parte del passaggio di conformità di dispositivi e app; è possibile richiedere assistenza tramite Desktop App Assure </td>
    <td>
Parte del passaggio di distribuzione del sistema operativo e degli aggiornamenti delle funzionalità per i PC gestiti dall'utente </td>
    </tr>
</table>

<img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-2.png" alt="Desktop Deployment Wheel" height="450" width="802" align="middle" style="background-color: #fff;" />

Seguire la procedura descritta di seguito per pianificare ed eseguire una distribuzione di Windows 10 e Office 365 ProPlus su vasta scala. Ogni passaggio fa parte del processo generale di pianificazione e distribuzione e i passaggi vanno in genere eseguiti in parallelo in una distribuzione in fasi. Scaricare la versione gratuita di [Distribuzione del desktop e Management Lab Kit](https://aka.ms/howtoshiftlabs) per un'esercitazione pratica con gli strumenti evidenziati nel processo di distribuzione. Per la distribuzione desktop è anche possibile [richiedere assistenza](https://aka.ms/mddhelp) a partner Microsoft e servizi FastTrack.

<br>

<table>
<tr class="even">
<td><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-1.png" alt="Getting Started" height="144" width="144" /></td>
<td><p><strong><a href="https://aka.ms/mdd0">Guida introduttiva: indicazioni su utenti, processi e tecnologia</a></strong></p>
<p>Informazioni sui vantaggi correlato al passaggio a Windows 10 e Office 365 ProPlus e sulle principali modifiche, considerazioni rispetto alle distribuzioni precedenti e procedure consigliate per una transizione a Windows 10 e Office 365 ProPlus priva di problemi.</p></td>
<td><a href="https://aka.ms/ddev0" target="_blank"><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-13.png" alt="Getting Started" height="130" width="231" /></a></td>
</tr>
<tbody>
<tr class="odd">
<td><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-3.png" alt="Step 1" height="144" width="144" /></td>
<td><p><strong><a href="https://aka.ms/mdd1">Passaggio 1: conformità di dispositivi e app</a></strong></p>
<p>Iniziare il progetto di distribuzione desktop con un inventario dei dispositivi e delle app, con l'assegnazione delle priorità, con l'esecuzione di test sui dispositivi e sulle app cui è stata assegnata la priorità, quindi con la correzione di quanto necessario per prepararsi alla distribuzione.</p></td>
<td><a href="https://aka.ms/ddev1" target="_blank"><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-14.png" alt="Step 1" height="130" width="231" /></a></td>
</tr>
<tr class="even">
<td><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-5.png" alt="Step 2" height="144" width="144" /></td>
<td><p><strong><a href="https://aka.ms/mdd2">Passaggio 2: conformità della directory e della rete</a></strong></p>
<p>I servizi connessi tramite cloud in Office 365 ProPlus e le nuove opzioni di distribuzione come Windows Autopilot richiedono Azure Active Directory. Anche la rete e la connettività sono aree importanti da pianificare quando si trasferiscono immagini, app, driver e file correlati nei PC. Ottenere informazioni su come i nuovi strumenti e opzioni di distribuzione riducono e ottimizzano il traffico di rete.</p></td>
<td><a href="https://aka.ms/ddev2" target="_blank"><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-15.png" alt="Step 2" height="130" width="231" /></a></td>
</tr>
<tr class="odd">
<td><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-6.png" alt="Step 3" height="144" width="144" /></td>
<td><p><strong><a href="https://aka.ms/mdd3">Passaggio 3: distribuzione di Office e app line-of-business</a></strong></p>
<p>Verificare che le app siano compresse e pronte per l'installazione automatica. In questo passaggio vengono fornite informazioni sulle nuove opzioni offerte dai pacchetti a portata di clic di Office 365 ProPlus per configurare, distribuire e mantenere aggiornate le app di Office.</p></td>
<td><a href="https://aka.ms/ddev3" target="_blank"><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-16.png" alt="Step 3" height="130" width="231" /></a></td>
</tr>
<tr class="even">
<td><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-7.png" alt="Step 4" height="144" width="144" /></td>
<td><p><strong><a href="https://aka.ms/mdd4">Passaggio 4: file e impostazioni utente</a></strong></p>
<p>Durante l'aggiornamento o la sostituzione dei PC, è possibile risparmiare tempo automatizzando il backup e il ripristino dello stato utente. Le nuove opzioni per la sincronizzazione dei file sul cloud consentono di applicare la sincronizzazione per utente delle cartelle desktop, documenti e immagini in OneDrive per l'accesso semplificato ai file da nuove installazioni di Windows.</p></td>
<td><a href="https://aka.ms/ddev4" target="_blank"><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-17.png" alt="Step 4" height="130" width="231" /></a></td>
</tr>
<tr class="odd">
<td><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-8.png" alt="Step 5" height="144" width="144" /></td>
<td><p><strong><a href="https://aka.ms/mdd5">Passaggio 5: considerazioni sulla sicurezza e conformità</a></strong></p>
<p>Windows 10 e Office 365 ProPlus forniscono nuovi modi per proteggere dati, dispositivi e utenti e per rilevare rapidamente e rispondere alle minacce. In questo passaggio vengono inoltre fornite informazioni su come gestire i problemi comuni relativi alla crittografia del disco, alle app antimalware e ai criteri quando si passa a Windows 10.</p></td>
<td><a href="https://aka.ms/ddev5" target="_blank"><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-18.png" alt="Step 5" height="130" width="231" /></a></td>
</tr>
<tr class="even">
<td><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-9.png" alt="Step 6" height="144" width="144" /></td>
<td><p><strong><a href="https://aka.ms/mdd6">Passaggio 6: distribuzione del sistema operativo e aggiornamenti delle caratteristiche</a></strong></p>
<p>La distribuzione basata sulla sequenza di attività è usata per automatizzare su vasta scala, la distribuzione in fasi per installazioni bare metal, aggiornamento del PC e sostituzione del PC. Le sequenze di attività di aggiornamento consentono inoltre di restare al passo con gli aggiornamenti semestrali principali. E Windows Autopilot è una novità che modernizza il processo di acquisizione di un nuovo PC.</p></td>
<td><a href="https://aka.ms/ddev6" target="_blank"><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-19.png" alt="Step 6" height="130" width="231" /></a></td>
</tr>
<tr class="odd">
<td><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-10.png" alt="Step 7" height="144" width="144" /></td>
<td><p><strong><a href="https://aka.ms/mdd7">Passaggio 7: manutenzione di Windows e Office</a></strong></p>
<p>Windows 10 e Office 365 ProPlus aggiungono continuamente nuove funzionalità per continuare a offrire esperienze utente e protezione con le ultime novità. In questo passaggio vengono fornite informazioni su come restare al passo con gli aggiornamenti mensili e semestrali, su come funziona il nuovo modello di manutenzione e sugli strumenti e opzioni già disponibili.</p></td>
<td><a href="https://aka.ms/ddev7" target="_blank"><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-20.png" alt="Step 7" height="130" width="231" /></a></td>
</tr>
<tr class="even">
<td><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-11.png" alt="Step 8" height="144" width="144" /></td>
<td><p><strong><a href="https://aka.ms/mdd8">Passaggio 8: formazione e comunicazione utente</a></strong></p>
<p>Verificare che gli utenti siano informati sulle nuove esperienze e sulle nuove modalità di lavoro quando si passa a Windows 10 e Office 365 ProPlus. Ottenere informazioni su come sfruttare l’assistenza per l’adozione da parte degli utenti con Microsoft FastTrack, sui materiali di formazione e sui modelli di comunicazione, oltre che sui nuovi modi per monitorare l'utilizzo e l’accettazione da parte degli utenti.</p></td>
<td><a href="https://aka.ms/ddev8" target="_blank"><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-21.png" alt="Step 8" height="130" width="231" /></a></td>
</tr>
<tr class="odd">
<td><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-12.png" alt="Value Discovery and Business Case" height="144" width="144" /></td>
<td><p><strong><a href="https://transform.microsoft.com" target="_blank">Coinvolgere i dirigenti: Value Discovery e caso aziendale</a></strong></p>
<p>Se si è effettuata la ricerca sulla distribuzione, la valutazione della conformità delle app e dei dispositivi, creato il piano di distribuzione e iniziato la distribuzione pilota, ma non si hanno il supporto o le risorse necessarie da parte del team di gestione per soddisfare le sequenze temporali della distribuzione, il programma BVP (Business Value Program) Microsoft può risultare molto utile. In questo passaggio vengono fornite informazioni su come creare un caso aziendale per il passaggio a Windows 10 e Office 365 ProPlus e coinvolgere tutti.</p></td>
<td><a href="https://transform.microsoft.com" target="_blank"><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-22.png" alt="Value Discovery and Business Case" height="130" width="231" /></td>
</tr>
</tbody>
</table>
