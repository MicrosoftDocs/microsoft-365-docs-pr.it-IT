---
title: Come vengono gestiti gli aggiornamenti in Microsoft Managed Desktop
description: Mantenere il desktop Microsoft gestito aggiornato è un bilanciamento della velocità e della stabilità.
keywords: Microsoft Managed Desktop, Microsoft 365, Service, documentazione
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.date: 01/09/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 7709779c73293a4523bf3cc381d0b59f7fbca325
ms.sourcegitcommit: d137cb1bd67a79d8af84357dc156824830d35aa7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/29/2019
ms.locfileid: "35924869"
---
# <a name="how-updates-are-handled-in-microsoft-managed-desktop"></a>Come vengono gestiti gli aggiornamenti in Microsoft Managed Desktop


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/update-rings); do not delete.-->

<!--Update management -->

Microsoft Managed Desktop connette tutti i dispositivi a una moderna infrastruttura basata su cloud. Mantenere aggiornati gli aggiornamenti delle applicazioni di Windows, Office, driver, firmware e Microsoft Store for business è un bilanciamento della velocità e della stabilità. I gruppi di distribuzione verranno utilizzati per garantire che il sistema operativo e i criteri vengano srotolati in modo sicuro. 

Gli aggiornamenti rilasciati da Microsoft sono cumulativi e vengono categorizzati come aggiornamenti di qualità o funzionalità.
Per ulteriori informazioni, vedere [Windows Update for business: tipi di aggiornamento](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb#update-types). 

## <a name="update-groups"></a>Aggiornare i gruppi

Microsoft Managed Desktop utilizza quattro gruppi di Azure ad per la gestione degli aggiornamenti:

- **Test**: utilizzato per convalidare le modifiche ai criteri di Microsoft Managed Desktop, gli aggiornamenti del sistema operativo, gli aggiornamenti delle funzionalità e altre modifiche apportate al tenant. Non è necessario che gli utenti finali vengano inseriti nel gruppo di test. Il gruppo di test è esente da qualsiasi SLA stabilito e dal supporto degli utenti finali. Questo gruppo è disponibile per convalidare la compatibilità delle applicazioni con i nuovi criteri o le modifiche apportate al sistema operativo.  
- **Primo**: contiene gli utenti e i dispositivi software precoci che potrebbero essere soggetti agli aggiornamenti precedenti alla versione precedente. I dispositivi di questo gruppo possono riscontrare interruzioni se esistono scenari che non sono stati analizzati durante il testing nell'anello di test.
- **Fast**: priorità della velocità rispetto alla stabilità. Utile per rilevare i problemi di qualità prima che vengano offerti al gruppo generale. Questo gruppo funge da livello successivo di convalida, ma in genere è più stabile rispetto al test e ai primi gruppi. 
- **Broad**: ultimo gruppo in cui sono disponibili aggiornamenti di funzionalità e qualità. Questo gruppo contiene la maggior parte degli utenti nel tenant e quindi favorisce la stabilità sulla velocità della distribuzione. Il testing delle app dovrebbe essere effettuato qui perché l'ambiente è più stabile. 

Per ulteriori informazioni sui ruoli e le responsabilità di questi gruppi di distribuzione, vedere [ruoli e responsabilità di Microsoft Managed Desktop](../intro/roles-and-responsibilities.md)

Funzionamento della distribuzione degli aggiornamenti:
- Microsoft Managed Desktop distribuisce una nuova funzionalità o un aggiornamento di qualità in base alla pianificazione specificata di seguito.
- Durante la distribuzione, Microsoft Managed Desktop Monitors è in grado di segnalare errori o interruzioni (basati su segnali di dati diagnostici e su un sistema di supporto per gli utenti finali). Se vengono rilevati, la distribuzione a tutti i gruppi correnti e futuri viene sospesa immediatamente.
    - Esempio: se viene rilevato un problema durante la distribuzione di un aggiornamento di qualità al primo gruppo, le distribuzioni di aggiornamento a First, Fast e Broad verranno sospese finché il problema non viene risolto.
    - I problemi di compatibilità possono essere segnalati archiviando un ticket nel portale di amministrazione IT di Microsoft Managed Desktop IT.
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

>[!NOTE]
>Questi periodi di rinvio sono stati intenzionalmente studiati per garantire elevati standard di sicurezza e prestazioni per tutti gli utenti. Inoltre, in base ai dati raccolti su tutti i dispositivi Microsoft Managed Desktop e all'ambito e all'impatto variabile degli aggiornamenti, Microsoft Managed Desktop è in grado di modificare la durata dei periodi di rinvio sopra indicati per tutti i gruppi di distribuzione di un annuncio. base hoc.
>
>Microsoft Managed Desktop conduce una valutazione indipendente di ogni versione di funzionalità di Windows per valutarne la necessità e l'utilità per i tenant gestiti. Di conseguenza, Microsoft Managed Desktop potrebbe o non potrebbe distribuire tutti gli aggiornamenti delle funzionalità di Windows. 

## <a name="windows-insider-program"></a>Programma Windows Insider

Microsoft Managed Desktop non supporta i dispositivi che fanno parte del programma Windows Insider. Il programma Windows Insider viene utilizzato per convalidare il software Windows già rilasciato ed è progettato per i dispositivi non critici. Anche se si tratta di un'iniziativa Microsoft importante, non è destinata a una distribuzione di grandi dimensioni in ambienti di produzione. 

Tutti i dispositivi trovati con Windows Insider Builds potrebbero essere inseriti nel gruppo di test e verranno esonerati da Update Service Level Agreements (SLA) e dal supporto degli utenti finali da Microsoft Managed Desktop.

## <a name="bandwidth-management"></a>Gestione della larghezza di banda

L'ottimizzazione del recapito viene utilizzata per tutti gli aggiornamenti del sistema operativo e dei driver. Consente di ridurre al minimo le dimensioni di download dal servizio Windows Update ricercando gli aggiornamenti da peer all'interno della rete aziendale.


