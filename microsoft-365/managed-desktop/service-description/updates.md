---
title: Come vengono gestiti gli aggiornamenti in Microsoft Managed Desktop
description: Mantenere il desktop Microsoft gestito aggiornato è un bilanciamento della velocità e della stabilità.
keywords: Microsoft Managed Desktop, Microsoft 365, Service, documentazione
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 01/09/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 0dad909ce9e17f993de64ba39b08f388c71abb89
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32278645"
---
# <a name="how-updates-are-handled-in-microsoft-managed-desktop"></a>Come vengono gestiti gli aggiornamenti in Microsoft Managed Desktop


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/update-rings); do not delete.-->

<!--Update management -->

Microsoft Managed Desktop connette tutti i dispositivi a una moderna infrastruttura basata su cloud. Mantenere aggiornati gli aggiornamenti delle applicazioni di Windows, Office, driver, firmware e Microsoft Store for business è un bilanciamento della velocità e della stabilità. I gruppi di distribuzione verranno utilizzati per garantire che il sistema operativo e i criteri vengano srotolati in modo sicuro. 

Gli aggiornamenti rilasciati da Microsoft sono cumulativi e possono essere classificati come aggiornamenti di qualità o funzionalità.
Per ulteriori informazioni, vedere [Windows Update for business: tipi di aggiornamento](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb#update-types). 

## <a name="update-groups"></a>Aggiornare i gruppi

Microsoft Managed Desktop utilizza quattro gruppi di Azure ad per la gestione degli aggiornamenti:

- **Test**: utilizzato per convalidare le modifiche ai criteri di Microsoft Managed Desktop, gli aggiornamenti del sistema operativo, gli aggiornamenti delle funzionalità e altre modifiche apportate al tenant. Non è necessario che gli utenti finali vengano inseriti nel gruppo di test. Il gruppo di test è esente da qualsiasi SLA stabilito e dal supporto degli utenti finali. Questo gruppo è disponibile per convalidare la compatibilità delle applicazioni con i nuovi criteri o le modifiche apPortate al sistema operativo.  
- **Primo**: contiene gli adottanti e i dispositivi software precoci che possono essere soggetti agli aggiornamenti precedenti alla versione precedente. I dispositivi di questo gruppo possono riscontrare interruzioni se esistono scenari che non sono stati analizzati durante il testing nell'anello di test.
- **Fast**: priorità della velocità rispetto alla stabilità. Utile per rilevare i problemi di qualità prima che vengano offerti al gruppo generale. Questo gruppo funge da livello successivo di convalida, ma in genere è più stabile rispetto al test e ai primi gruppi. 
- **Broad**: ultimo gruppo in cui sono disponibili aggiornamenti di funzionalità e qualità. Questo gruppo contiene la maggior parte degli utenti nel tenant e quindi favorisce la stabilità sulla velocità della distribuzione. Il testing delle app dovrebbe essere effettuato qui perché l'ambiente è più stabile. 

Per ulteriori informazioni sui ruoli e le responsabilità di questi gruppi di distribuzione, vedere [ruoli e responsabilità di Microsoft managEd desktop](../intro/roles-and-responsibilities.md)

Funzionamento della distribuzione degli aggiornamenti:
- Microsoft Managed Desktop distribuisce una nuova funzionalità o un aggiornamento di qualità in base alla pianificazione specificata di seguito.
- Durante la distribuzione, Microsoft Managed Desktop Monitors è in grado di segnalare errori o interruzioni (basati su segnali di dati diagnostici e su un sistema di supporto per gli utenti finali). Se vengono rilevati, la distribuzione a tutti i gruppi correnti e futuri viene sospesa immediatamente.
    - Esempio: se viene rilevato un problema durante la distribuzione di un aggiornamento di qualità al primo gruppo, le distribuzioni di aggiornamento a First, Fast e Broad verranno sospese finché il problema non viene risolto.
    - I problemi di compatibilità possono essere segnalati dalla presentazione di un ticket nel portale di amministrazione IT di Microsoft Managed Desktop IT.
- Gli aggiornamenti di funzionalità e qualità sono sospesi in modo indipendente. La pausa è attiva per 35 giorni per impostazione predefinita, ma può essere ridotta o estesa a seconda che il problema venga rimediato.
- Dopo che i gruppi sono stati sospesi, la distribuzione riprende in base alla pianificazione seguente.
- Questo processo di distribuzione si applica a tutti gli aggiornamenti di funzionalità e qualità, anche se la sequenza temporale varia per ogni.

<table>
<tr><th colspan="5">Aggiornare le impostazioni di distribuzione</th></tr>
<tr><th>Tipo di aggiornamento</th><th>Testing</th><th>Prima</th><th>Veloce</th><th>Ampio</th></tr>
<tr><td>Aggiornamenti della qualità per il sistema operativo</td><td>0 giorni</td><td>0 giorni</td><td>0 giorni</td><td>3 giorni</td></tr>
<tr><td>Aggiornamenti delle funzionalità per il sistema operativo</td><td>0 giorni</td><td>30 giorni</td><td>60 giorni</td><td>90 giorni</td></tr>
<tr><td>Driver/firmware</td><td colspan="4">Segue la pianificazione per gli aggiornamenti della qualità</td></tr>
<tr><td>Definizione di antivirus</td><td colspan="4">Aggiornato con ogni analisi</td></tr>
</table>

Questi periodi di rinvio sono stati intenzionalmente studiati per garantire elevati standard di sicurezza e prestazioni per tutti gli utenti. Inoltre, in base ai dati raccolti su tutti i dispositivi Microsoft Managed Desktop e all'ambito e all'impatto variabile degli aggiornamenti, Microsoft Managed Desktop è in grado di modificare la durata dei periodi di rinvio sopra indicati per tutti i gruppi di distribuzione di un annuncio. base hoc.

## <a name="windows-insider-program"></a>Programma Windows inSider

Microsoft Managed Desktop non supporta i dispositivi che fanno parte del programma Windows inSider. Il programma Windows inSider viene utilizzato per convalidare il software Windows già rilasciato ed è progettato per i dispositivi non critici. Anche se si tratta di un'iniziativa Microsoft importante, non è destinata a una distribuzione di grandi dimensioni in ambienti di produzione. 

Qualsiasi dispositivo trovato con Windows inSider Builds verrà inserito nel gruppo di testing e non verrà incluso per gli SLA (Update Service Level Agreements).

## <a name="bandwidth-management"></a>Gestione della larghezza di banda

L'ottimizzazione del reCapito viene utilizzata per tutti gli aggiornamenti del sistema operativo e dei driver. Consente di ridurre al minimo le dimensioni del download dal servizio Windows Update (WU) ricercando gli aggiornamenti dei peer all'interno della rete aziendale.


