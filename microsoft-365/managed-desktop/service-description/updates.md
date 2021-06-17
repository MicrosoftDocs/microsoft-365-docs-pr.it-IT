---
title: Modalità di gestione degli aggiornamenti in Microsoft Managed Desktop
description: Mantenere Microsoft Managed Desktop aggiornato è un equilibrio tra velocità e stabilità.
keywords: Microsoft Managed Desktop, Microsoft 365, servizio, documentazione
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 5d78f695785cd81b51e20b90cdefbb3790cf6197
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2021
ms.locfileid: "52984737"
---
# <a name="how-updates-are-handled-in-microsoft-managed-desktop"></a>Modalità di gestione degli aggiornamenti in Microsoft Managed Desktop


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/update-rings); do not delete.-->

<!--Update management -->

Microsoft Managed Desktop connette tutti i dispositivi a un'infrastruttura moderna basata sul cloud. Mantenere windows, Office, driver, firmware e le applicazioni di Microsoft Store per le aziende aggiornate è un equilibrio tra velocità e stabilità. Usiamo i gruppi di aggiornamento per garantire che gli aggiornamenti e i criteri del sistema operativo siano stati applicati in modo sicuro. Per ulteriori informazioni, vedere il video [Microsoft Managed Desktop Change and Release Process](https://www.microsoft.com/videoplayer/embed/RE4mWqP). 

Gli aggiornamenti rilasciati da Microsoft sono cumulativi e sono classificati come aggiornamenti qualitativi o delle funzionalità.
Per altre informazioni, vedi [Windows Update for Business: Tipi di aggiornamento.](/windows/deployment/update/waas-manage-updates-wufb#update-types) 

## <a name="update-groups"></a>Gruppi di aggiornamento


Microsoft Managed Desktop usa quattro gruppi di Azure AD per gestire gli aggiornamenti:

- **Test**: usato per convalidare le modifiche ai criteri di Microsoft Managed Desktop, gli aggiornamenti del sistema operativo, gli aggiornamenti delle funzionalità e altre modifiche apportate all'organizzazione di Azure AD ("tenant"). Ideale per test o utenti in grado di fornire feedback precoce. Il gruppo di test è esente da eventuali contratti di servizio stabiliti e dal supporto degli utenti. Questo gruppo è disponibile per l'utilizzo per convalidare la compatibilità delle applicazioni con nuovi criteri o modifiche al sistema operativo.  
- **First**: Contiene i primi utenti che adottano software e i dispositivi che potrebbero essere soggetti a aggiornamenti non rilasciati. I dispositivi in questo gruppo potrebbero verificarsi interruzioni se sono presenti scenari che non sono stati coperti durante i test nell'anello di test.
- **Veloce:** assegna priorità alla velocità rispetto alla stabilità. Utile per rilevare i problemi di qualità prima che siano offerti al gruppo Generale. Questo gruppo funge da livello di convalida successivo, ma in genere è più stabile dei gruppi Test e First. 
- **Generale:** ultimo gruppo in cui sono disponibili aggiornamenti qualitativi e delle funzionalità. Questo gruppo contiene la maggior parte degli utenti nell'organizzazione di Azure AD e quindi favorisce la stabilità rispetto alla velocità nella distribuzione. Il testing delle app deve essere eseguito qui perché l'ambiente è più stabile.

### <a name="moving-devices-between-update-groups"></a>Spostamento di dispositivi tra gruppi di aggiornamento
Potresti volere che alcuni dispositivi ricevano gli aggiornamenti per ultimi e altri che vuoi prima di tutto. Per spostare questi dispositivi nel gruppo di aggiornamento appropriato, vedi [Assegnare dispositivi a un gruppo di distribuzione.](../working-with-managed-desktop/assign-deployment-group.md)

Per ulteriori informazioni sui ruoli e sulle responsabilità all'interno di questi gruppi di distribuzione, vedere Ruoli e responsabilità [di Microsoft Managed Desktop](../intro/roles-and-responsibilities.md)

### <a name="using-microsoft-managed-desktop-update-groups"></a>Utilizzo dei gruppi di aggiornamento di Microsoft Managed Desktop 
Ci sono parti del servizio che gestisci, come la distribuzione di app, in cui potrebbe essere necessario scegliere come destinazione tutti i dispositivi gestiti.

## <a name="how-update-deployment-works"></a>Funzionamento della distribuzione degli aggiornamenti:
1. Microsoft Managed Desktop distribuisce una nuova funzionalità o un aggiornamento qualitativo in base alla pianificazione specificata nella tabella seguente.
2. Durante la distribuzione, Microsoft Managed Desktop monitora i segni di errore o di interruzione in base ai dati di diagnostica e al sistema di supporto degli utenti. Se vengono rilevati, la distribuzione viene sospesa immediatamente in tutti i gruppi correnti e futuri.
    - Esempio: se viene rilevato un problema durante la distribuzione di un aggiornamento qualitativo al gruppo First, le distribuzioni di aggiornamento a First, Fast e Broad verranno tutte sospese fino a quando il problema non viene risolto.
    - È possibile segnalare i problemi di compatibilità tramite l'archiviazione di un ticket nel portale di amministrazione di Microsoft Managed Desktop.
    - Gli aggiornamenti delle funzionalità e della qualità vengono sospesi in modo indipendente. La sospensione è in vigore per 35 giorni per impostazione predefinita, ma può essere ridotta o estesa a seconda che il problema sia stato risolto.
3. Quando i gruppi non vengono scaricati, la distribuzione riprende in base alla pianificazione nella tabella.

Questo processo di distribuzione si applica sia agli aggiornamenti qualitativi che alle funzionalità, anche se la sequenza temporale varia per ognuno di essi.


<table>
    <tr><th colspan="5">Aggiornare le impostazioni di distribuzione</th></tr>
    <tr><th>Tipo di aggiornamento</th><th>Test</th><th>First</th><th>Veloce</th><th>Broad</th></tr>
    <tr><td>Aggiornamenti qualitativi per il sistema operativo</td><td>0 giorni</td><td>0 giorni</td><td>0 giorni</td><td>3 giorni</td></tr>
    <tr><td>Aggiornamenti delle funzionalità per il sistema operativo</td><td>0 giorni</td><td>30 giorni</td><td>60 giorni</td><td>90 giorni</td></tr>
    <tr><td>Driver/firmware</td><td colspan="4">Segue la pianificazione per gli aggiornamenti qualitativi</td></tr>
    <tr><td>Definizione antivirus</td><td colspan="4">Aggiornato con ogni analisi</td></tr>
    <tr><td>Microsoft 365 Apps for enterprise</td><td colspan="4"><a href="/microsoft-365/managed-desktop/get-started/m365-apps#updates-to-microsoft-365-apps">Altre informazioni</a></td></tr>
    <tr><td>Microsoft Edge</td><td colspan="4"><a href="/microsoft-365/managed-desktop/get-started/edge-browser-app#updates-to-microsoft-edge">Altre informazioni</a></td></tr>
    <tr><td>Microsoft Teams</td><td colspan="4"><a href="/microsoft-365/managed-desktop/get-started/teams#updates">Altre informazioni</a></td></tr>
</table>

>[!NOTE]
>Questi periodi di differimento sono progettati intenzionalmente per garantire standard di sicurezza e prestazioni elevati per tutti gli utenti. Inoltre, in base ai dati raccolti in tutti i dispositivi Microsoft Managed Desktop e all'ambito e all'impatto variabili degli aggiornamenti, Microsoft Managed Desktop si riserva la flessibilità di modificare la durata dei periodi di rinvio precedenti per tutti i gruppi di distribuzione su base ad hoc.
>
>Microsoft Managed Desktop esegue una valutazione indipendente di ogni rilascio di funzionalità di Windows per valutarne la necessità e l'utilità per i tenant gestiti. Di conseguenza, Microsoft Managed Desktop potrebbe o meno distribuire tutti gli aggiornamenti delle funzionalità di Windows. 

## <a name="windows-insider-program"></a>Programma Windows Insider

Microsoft Managed Desktop non supporta i dispositivi che fanno parte del programma Windows Insider. Il programma Windows Insider viene usato per convalidare il software Windows non definitiva ed è destinato ai dispositivi che non sono mission critical. Sebbene si tratta di un'importante iniziativa Microsoft, non è progettata per una distribuzione generale in ambienti di produzione. 

Tutti i dispositivi trovati con le build di Windows Insider potrebbero essere inseriti nel gruppo Test e saranno esenti dai contratti di servizio di aggiornamento e dal supporto degli utenti da Microsoft Managed Desktop.

## <a name="bandwidth-management"></a>Gestione della larghezza di banda

Usiamo [Ottimizzazione recapito per](/windows/deployment/update/waas-delivery-optimization) tutti gli aggiornamenti del sistema operativo e dei driver. Ottimizzazione recapito riduce al minimo le dimensioni del download dal servizio Windows Update cercando aggiornamenti dai peer all'interno della rete aziendale.