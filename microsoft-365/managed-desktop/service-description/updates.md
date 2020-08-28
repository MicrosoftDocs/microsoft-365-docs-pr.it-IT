---
title: Come vengono gestiti gli aggiornamenti in Microsoft Managed Desktop
description: Mantenere il desktop gestito Microsoft aggiornato è un bilanciamento della velocità e della stabilità.
keywords: Microsoft Managed Desktop, Microsoft 365, servizio, documentazione
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 1349b58bdd6243b05323f14197e0ad92c1fc0d7b
ms.sourcegitcommit: abf63669daf12993ad3353e4b578f41c8910b20f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/27/2020
ms.locfileid: "47289496"
---
# <a name="how-updates-are-handled-in-microsoft-managed-desktop"></a>Come vengono gestiti gli aggiornamenti in Microsoft Managed Desktop


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/update-rings); do not delete.-->

<!--Update management -->

Microsoft Managed Desktop connette tutti i dispositivi a una moderna infrastruttura basata su cloud. Mantenere aggiornate le applicazioni di Windows, Office, driver, firmware e Microsoft Store for business è un bilanciamento della velocità e della stabilità. I gruppi di distribuzione verranno utilizzati per garantire che gli aggiornamenti del sistema operativo e i criteri vengano implementati in modo sicuro. Per ulteriori informazioni, vedere la pagina relativa al [processo di modifica e rilascio del video Microsoft Managed Desktop](https://www.microsoft.com/videoplayer/embed/RE4mWqP).

Gli aggiornamenti rilasciati da Microsoft sono cumulativi e vengono categorizzati come aggiornamenti di qualità o funzionalità.
Per ulteriori informazioni, vedere [Windows Update for business: tipi di aggiornamento](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb#update-types). 

## <a name="update-groups"></a>Aggiornare i gruppi

Microsoft Managed Desktop utilizza quattro gruppi di Azure ad per la gestione degli aggiornamenti:

- **Test**: utilizzato per convalidare le modifiche ai criteri di Microsoft Managed Desktop, gli aggiornamenti del sistema operativo, gli aggiornamenti delle funzionalità e altre modifiche apportate al tenant. Gli utenti non devono essere inseriti nel gruppo di test. Il gruppo di test è esente da tutti i contratti di servizio e il supporto utente stabiliti. Questo gruppo è disponibile per l'utilizzo per convalidare la compatibilità delle applicazioni con nuove modifiche al criterio o al sistema operativo.  
- **Primo**: contiene gli utenti e i dispositivi software precoci che potrebbero essere soggetti agli aggiornamenti precedenti alla versione precedente. I dispositivi di questo gruppo possono riscontrare interruzioni se esistono scenari che non sono stati analizzati durante il testing nell'anello di test.
- **Fast**: priorità della velocità rispetto alla stabilità. Utile per rilevare i problemi di qualità prima che vengano offerti al gruppo generale. Questo gruppo funge da livello successivo di convalida, ma in genere è più stabile rispetto al test e ai primi gruppi. 
- **Broad**: ultimo gruppo in cui sono disponibili aggiornamenti di funzionalità e qualità. Questo gruppo contiene la maggior parte degli utenti nel tenant e quindi favorisce la stabilità sulla velocità della distribuzione. Il testing delle app dovrebbe essere effettuato qui perché l'ambiente è più stabile. 

> [!NOTE]
> Se è necessario spostare un utente in un gruppo di aggiornamento diverso, inviare una richiesta di supporto. Per ulteriori informazioni sull'invio delle richieste di supporto, vedere [supporto per Microsoft Managed Desktop](support.md) . Se si sposta un utente manualmente, lo spostamento verrà ripristinato.

Per ulteriori informazioni sui ruoli e le responsabilità di questi gruppi di distribuzione, vedere [ruoli e responsabilità di Microsoft Managed Desktop](../intro/roles-and-responsibilities.md)

Funzionamento della distribuzione degli aggiornamenti:
- Microsoft Managed Desktop distribuisce una nuova funzionalità o un aggiornamento di qualità in base alla pianificazione specificata di seguito.
- Durante la distribuzione, Microsoft Managed Desktop monitora i segni di errori o interruzioni (in base ai dati di diagnostica e al sistema di supporto utente). Se vengono rilevati, la distribuzione a tutti i gruppi correnti e futuri viene sospesa immediatamente.
    - Esempio: se viene rilevato un problema durante la distribuzione di un aggiornamento di qualità al primo gruppo, le distribuzioni di aggiornamento a First, Fast e Broad verranno sospese finché il problema non viene risolto.
    - I problemi di compatibilità possono essere segnalati archiviando un ticket nel portale di amministrazione di Microsoft Managed Desktop.
- Gli aggiornamenti di funzionalità e qualità sono sospesi in modo indipendente. La pausa è attiva per 35 giorni per impostazione predefinita, ma può essere ridotta o estesa a seconda che il problema venga rimediato.
- Dopo che i gruppi sono stati sospesi, la distribuzione riprende in base alla pianificazione seguente.
- Questo processo di distribuzione si applica a tutti gli aggiornamenti di funzionalità e qualità, anche se la sequenza temporale varia per ogni.




<table>
<tr><th colspan="5">Aggiornare le impostazioni di distribuzione</th></tr>
<tr><th>Tipo di aggiornamento</th><th>Test</th><th>Prima</th><th>Veloce</th><th>Ampio</th></tr>
<tr><td>Aggiornamenti della qualità per il sistema operativo</td><td>0 giorni</td><td>0 giorni</td><td>0 giorni</td><td>3 giorni</td></tr>
<tr><td>Aggiornamenti delle funzionalità per il sistema operativo</td><td>0 giorni</td><td>30 giorni</td><td>60 giorni</td><td>90 giorni</td></tr>
<tr><td>Driver/firmware</td><td colspan="4">Segue la pianificazione per gli aggiornamenti della qualità</td></tr>
<tr><td>Definizione di antivirus</td><td colspan="4">Aggiornato con ogni analisi</td></tr>
<tr><td>Microsoft 365 Apps for enterprise</td><td colspan="4">Segue il canale corrente di Office
</table>

Per ulteriori informazioni sul canale corrente per le app Microsoft 365 per Enterprise, vedere [Overview of Update channels for microsoft 365 Apps](https://docs.microsoft.com/deployoffice/overview-update-channels).

>[!NOTE]
>Questi periodi di rinvio sono stati intenzionalmente studiati per garantire elevati standard di sicurezza e prestazioni per tutti gli utenti. Inoltre, in base ai dati raccolti su tutti i dispositivi desktop Microsoft gestiti e all'ambito e all'impatto variabile degli aggiornamenti, Microsoft Managed Desktop si riserva la possibilità di modificare la durata dei periodi di rinvio sopra indicati per tutti e tutti i gruppi di distribuzione su base ad hoc.
>
>Microsoft Managed Desktop conduce una valutazione indipendente di ogni versione di funzionalità di Windows per valutarne la necessità e l'utilità per i tenant gestiti. Di conseguenza, Microsoft Managed Desktop potrebbe o non potrebbe distribuire tutti gli aggiornamenti delle funzionalità di Windows. 

## <a name="windows-insider-program"></a>Programma Windows Insider

Microsoft Managed Desktop non supporta i dispositivi che fanno parte del programma Windows Insider. Il programma Windows Insider viene utilizzato per convalidare il software Windows già rilasciato ed è destinato a dispositivi che non sono mission critical. Anche se si tratta di un'iniziativa Microsoft importante, non è destinata a una distribuzione di grandi dimensioni in ambienti di produzione. 

Tutti i dispositivi trovati con Windows Insider Builds potrebbero essere inseriti nel gruppo di test e verranno esonerati dall'aggiornamento dei contratti di servizio e dal supporto degli utenti da Microsoft Managed Desktop.

## <a name="bandwidth-management"></a>Gestione della larghezza di banda

Viene utilizzata l' [ottimizzazione della distribuzione](https://docs.microsoft.com/windows/deployment/update/waas-delivery-optimization) per tutti gli aggiornamenti del sistema operativo e dei driver. Questo riduce al minimo le dimensioni di download dal servizio Windows Update, cercando gli aggiornamenti dei peer all'interno della rete aziendale.


