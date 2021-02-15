---
title: Modalità di gestione degli aggiornamenti in Microsoft Managed Desktop
description: Mantenere Microsoft Managed Desktop aggiornato è un equilibrio tra velocità e stabilità.
keywords: Microsoft Managed Desktop, Microsoft 365, servizi, documentazione
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 4d8de363cc9111fade719fdf5384519d1236f431
ms.sourcegitcommit: 05657b39eaafc0503b01c6adcc5d8a5e615dc02c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/27/2021
ms.locfileid: "50031340"
---
# <a name="how-updates-are-handled-in-microsoft-managed-desktop"></a>Modalità di gestione degli aggiornamenti in Microsoft Managed Desktop


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/update-rings); do not delete.-->

<!--Update management -->

Microsoft Managed Desktop connette tutti i dispositivi a un'infrastruttura moderna basata sul cloud. Mantenere aggiornati Windows, Office, driver, firmware e applicazioni di Microsoft Store per le aziende è un equilibrio tra velocità e stabilità. I gruppi di distribuzione verranno utilizzati per garantire l'implementazione sicura degli aggiornamenti e dei criteri del sistema operativo. Per ulteriori informazioni, vedere il video sul processo di modifica e rilascio di [Microsoft Managed Desktop.](https://www.microsoft.com/videoplayer/embed/RE4mWqP)

Gli aggiornamenti rilasciati da Microsoft sono cumulativi e sono classificati come aggiornamenti qualitativi o delle funzionalità.
Per altre informazioni, vedi [Windows Update for Business: Tipi di aggiornamento.](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb#update-types) 

## <a name="update-groups"></a>Aggiornare i gruppi

Microsoft Managed Desktop usa quattro gruppi di Azure AD per gestire gli aggiornamenti:

- **Test:** usato per convalidare le modifiche ai criteri di Microsoft Managed Desktop, gli aggiornamenti del sistema operativo, gli aggiornamenti delle funzionalità e altre modifiche push nel tenant. Non dovrebbero essere presenti utenti inseriti nel gruppo di test. Il gruppo di test è esente da eventuali contratti di servizio stabiliti e dal supporto per gli utenti. Questo gruppo è disponibile per l'uso per convalidare la compatibilità delle applicazioni con nuovi criteri o modifiche del sistema operativo.  
- **First**: Contiene early software adopter e dispositivi che potrebbero essere soggetti a aggiornamenti non definitiva. I dispositivi in questo gruppo potrebbero verificarsi interruzioni se sono presenti scenari non coperti durante i test nell'anello di test.
- **Veloce:** assegna priorità alla velocità rispetto alla stabilità. Utile per rilevare i problemi di qualità prima che siano offerti al gruppo Generale. Questo gruppo funge da ulteriore livello di convalida, ma in genere è più stabile dei gruppi Test e First. 
- **Generale:** ultimo gruppo in cui sono disponibili aggiornamenti qualitativi e delle funzionalità. Questo gruppo contiene la maggior parte degli utenti nel tenant e quindi favorisce la stabilità sulla velocità nella distribuzione. Il testing delle app deve essere eseguito qui perché l'ambiente è più stabile. 

### <a name="moving-devices-between-update-groups"></a>Spostamento di dispositivi tra gruppi di aggiornamento
Potresti volere che alcuni dispositivi ricevano gli aggiornamenti per ultimi e altri che vuoi prima. Per spostare questi dispositivi nel gruppo di aggiornamento appropriato, [invia una richiesta](https://docs.microsoft.com/microsoft-365/managed-desktop/working-with-managed-desktop/admin-support?view=o365-worldwide) di supporto dell'amministratore e i dispositivi verranno spostati automaticamente. 

> [!NOTE]
> Se è necessario spostare un utente in un gruppo di aggiornamento diverso, inviare una richiesta di supporto. Non spostare manualmente i dispositivi tra i gruppi di aggiornamento. Ci sono gravi conseguenze se un dispositivo viene spostato in modo errato. Il dispositivo potrebbe essere aggiornato in modo imprevisto e i criteri potrebbero essere in conflitto, modificando la configurazione del dispositivo.

Per ulteriori informazioni sui ruoli e le responsabilità all'interno di questi gruppi di distribuzione, vedere Ruoli e responsabilità [di Microsoft Managed Desktop](../intro/roles-and-responsibilities.md)

### <a name="using-microsoft-managed-desktop-update-groups"></a>Uso dei gruppi di aggiornamento di Microsoft Managed Desktop 
Esistono parti del servizio che gestisci, ad esempio la distribuzione di app, in cui potrebbe essere necessario scegliere come destinazione tutti i dispositivi gestiti. In questi casi, è opportuno usare i gruppi di aggiornamento per raggiungere tali utenti con la comprensione che non è possibile aggiungere, rimuovere o modificare l'appartenenza di tali gruppi. 

## <a name="how-update-deployment-works"></a>Funzionamento della distribuzione degli aggiornamenti:
1. Microsoft Managed Desktop distribuisce una nuova funzionalità o un aggiornamento qualitativo in base alla pianificazione specificata nella tabella seguente.
2. Durante la distribuzione, Microsoft Managed Desktop monitora eventuali segni di errore o interruzione in base ai dati di diagnostica e al sistema di supporto degli utenti. Se ne vengono rilevati, la distribuzione viene sospesa immediatamente per tutti i gruppi correnti e futuri.
    - Esempio: se viene rilevato un problema durante la distribuzione di un aggiornamento qualitativo al primo gruppo, le distribuzioni verranno tutte sospese fino alla risoluzione del problema.
    - È possibile segnalare i problemi di compatibilità tramite l'archiviazione di un ticket nel portale di amministrazione di Microsoft Managed Desktop.
    - Gli aggiornamenti delle funzionalità e della qualità vengono sospesi in modo indipendente. La sospensione è in vigore per 35 giorni per impostazione predefinita, ma può essere ridotta o estesa a seconda che il problema sia stato risolto.
3. Una volta sospesi i gruppi, la distribuzione riprende in base alla pianificazione riportata nella tabella.

Questo processo di distribuzione si applica sia agli aggiornamenti delle funzionalità che agli aggiornamenti qualitativi, anche se la sequenza temporale varia per ognuno.




<table>
    <tr><th colspan="5">Aggiornare le impostazioni di distribuzione</th></tr>
    <tr><th>Tipo di aggiornamento</th><th>Test</th><th>First</th><th>Veloce</th><th>Generale</th></tr>
    <tr><td>Aggiornamenti qualitativi per il sistema operativo</td><td>0 giorni</td><td>0 giorni</td><td>0 giorni</td><td>3 giorni</td></tr>
    <tr><td>Aggiornamenti delle funzionalità per il sistema operativo</td><td>0 giorni</td><td>30 giorni</td><td>60 giorni</td><td>90 giorni</td></tr>
    <tr><td>Driver/firmware</td><td colspan="4">Segue la pianificazione per gli aggiornamenti qualitativi</td></tr>
    <tr><td>Definizione antivirus</td><td colspan="4">Aggiornato con ogni analisi</td></tr>
    <tr><td>Microsoft 365 Apps for enterprise</td><td colspan="4"><a href="https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/m365-apps#updates-to-microsoft-365-apps">Altre informazioni</a></td></tr>
    <tr><td>Microsoft Edge</td><td colspan="4"><a href="https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/edge-browser-app#updates-to-microsoft-edge">Altre informazioni</a></td></tr>
    <tr><td>Microsoft Teams</td><td colspan="4"><a href="https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/teams#updates">Altre informazioni</a></td></tr>
</table>

>[!NOTE]
>Questi periodi di differimento sono progettati intenzionalmente per garantire standard di sicurezza e prestazioni elevati per tutti gli utenti. Inoltre, in base ai dati raccolti in tutti i dispositivi Microsoft Managed Desktop e al diverso ambito e impatto degli aggiornamenti, Microsoft Managed Desktop si riserva la flessibilità di modificare la durata dei periodi di rinvio precedenti per tutti i gruppi di distribuzione su base ad hoc.
>
>Microsoft Managed Desktop esegue una valutazione indipendente di ogni rilascio di funzionalità di Windows per valutarne la necessità e l'utilità per i tenant gestiti. Di conseguenza, Microsoft Managed Desktop potrebbe distribuire o meno tutti gli aggiornamenti delle funzionalità di Windows. 

## <a name="windows-insider-program"></a>Programma Windows Insider

Microsoft Managed Desktop non supporta i dispositivi che fanno parte del programma Windows Insider. Il programma Windows Insider viene usato per convalidare il software Windows non definitiva ed è destinato ai dispositivi che non sono critici. Sebbene si tratta di un'importante iniziativa Di Microsoft, non è destinata a una distribuzione su larga base negli ambienti di produzione. 

Tutti i dispositivi trovati con le build di Windows Insider potrebbero essere inseriti nel gruppo Test ed essere esenti dai contratti di servizio di aggiornamento e dal supporto degli utenti da Microsoft Managed Desktop.

## <a name="bandwidth-management"></a>Gestione della larghezza di banda

Usiamo Ottimizzazione [recapito per](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization) tutti gli aggiornamenti del sistema operativo e dei driver. In questo modo si riducono al minimo le dimensioni di download dal servizio Windows Update cercando aggiornamenti dai peer all'interno della rete aziendale.

