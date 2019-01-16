---
title: Come vengono gestiti gli aggiornamenti in Microsoft Managed Desktop
description: Mantenere aggiornati i Desktop gestiti Microsoft è un servizio di bilanciamento della velocità e la stabilità.
keywords: Servizio Microsoft Desktop gestiti, Microsoft 365, documentazione
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 01/09/2019
ms.openlocfilehash: bee6381b0f2b7b1e2d929329c3cf628ab7657678
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2019
ms.locfileid: "26868385"
---
# <a name="how-updates-are-handled-in-microsoft-managed-desktop"></a>Come vengono gestiti gli aggiornamenti in Microsoft Managed Desktop


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/update-rings); do not delete.-->

<!--Update management -->

Microsoft Desktop gestiti si connette tutti i dispositivi a un'infrastruttura basata su cloud moderna. Mantenere aggiornati Windows, Office, driver, firmware e Store Microsoft Business degli aggiornamenti dell'applicazione è un servizio di bilanciamento della velocità e la stabilità. Squilla distribuzione verrà utilizzato per garantire del sistema operativo e distribuire i criteri in modo sicuro. 

## <a name="update-groups"></a>Gruppi di aggiornamento

Desktop gestiti Microsoft utilizza quattro gruppi di Azure Active Directory per gestire gli aggiornamenti:

- Test: Dispositivi Non di produzione lo scopo di convalidare le modifiche prima di distribuire le modifiche tra il resto del tenant. I dispositivi in questa chiama rientrano nell'ambito di supporto per utenti finali documentata. 
- Primo: Contiene adottato, software e i dispositivi possono essere soggetto a versioni non definitive aggiornamenti.
- Fast: Assegna una priorità velocità su stabilità. Utile per rilevare i problemi di qualità prima che sono disponibili per il gruppo di grandi dimensioni. 
- Ampia: Ultimo gruppo di qualità e funzionalità di aggiornamenti disponibili. Questo gruppo contiene la maggior parte degli utenti nel tenant e pertanto favorisce la stabilità della velocità di distribuzione.

Aggiornamenti rilasciati da Microsoft sono cumulativi e potrebbero essere suddivise in aggiornamenti qualità o la caratteristica. Per ulteriori informazioni, vedere [Windows Update: domande frequenti su](https://support.microsoft.com/help/12373/windows-update-faq). 

Come aggiornare funzionamento della distribuzione:
- Microsoft Desktop gestiti consente di distribuire un nuovo aggiornamento qualità o funzionalità di base pianificazione specificata di seguito.
- Durante la distribuzione Desktop gestiti Microsoft esegue il monitoraggio di segnali di errore o un'interruzione del servizio (basato su segnali telemetria e il sistema di supporto per l'utente finale). In questo caso, la distribuzione a tutti i gruppi attuali e future immediatamente in pausa.
    - Esempio: se viene rilevato un problema durante la distribuzione di un aggiornamento di qualità al primo gruppo, quindi le distribuzioni di aggiornamento prima, Fast e ampia verranno tutti essere sospesa fino a quando non viene risolto il problema.
    - Problemi di compatibilità possono essere segnalati presentando un ticket nel portale di amministrazione IT di Desktop gestiti Microsoft.
- Aggiornamenti di qualità e funzionalità vengono sospese in modo indipendente. Sospendi è valido per 35 giorni per impostazione predefinita, ma possono essere ridotto o estese in base al fatto è risolte il problema.
- Una volta riavviati, i gruppi di distribuzione consente di riprendere in base alla pianificazione seguente.
- Questo processo di distribuzione si applica agli aggiornamenti la caratteristica e la qualità, anche se la sequenza temporale varia per ogni.

<table>
<tr><th colspan="5">Aggiornare le impostazioni di distribuzione</th></tr>
<tr><th>Tipo di aggiornamento</th><th>Testing</th><th>Funzionalità</th><th>Fast</th><th>Ampia</th></tr>
<tr><td>Aggiornamenti di qualità del sistema operativo</td><td>0 giorni</td><td>0 giorni</td><td>0 giorni</td><td>3 giorni</td></tr>
<tr><td>Aggiornamenti di funzionalità del sistema operativo</td><td>0 giorni</td><td>30 giorni</td><td>60 giorni</td><td>90 giorni</td></tr>
<tr><td>Driver/firmware</td><td colspan="4">Dopo la pianificazione per gli aggiornamenti di qualità</td></tr>
<tr><td>Definizione antivirus</td><td colspan="4">Aggiornamento con ogni analisi</td></tr>
</table>

Tali periodi di rinvio intenzionalmente sono progettati per garantire prestazioni standard per tutti gli utenti e protezione avanzata. Inoltre, basate sui dati raccolti tra tutti i dispositivi Desktop gestiti Microsoft e l'ambito e impatto degli aggiornamenti diversi, Desktop gestiti Microsoft si riserva flessibilità per modificare la durata dei periodi di rinvio precedente per i gruppi di distribuzione di qualsiasi su un annuncio base apposita.

## <a name="windows-insider-program"></a>Programma Windows persona interna

Desktop gestiti Microsoft non supporta i dispositivi che fanno parte del programma persona interna di Windows. Il programma di Windows dal viene utilizzato per convalidare il software Windows versione non definitiva ed è progettato per i dispositivi di importanza non critici. Mentre si tratta di un importante progetto di Microsoft, non deve essere ampia distribuzione negli ambienti di produzione. 

Tutti i dispositivi sono stato riscontrati build persona interna di Windows verranno inseriti nel gruppo di Test e non viene incluso per aggiornamento service level agreement (SLA.

## <a name="bandwidth-management"></a>Gestione della larghezza di banda

Ottimizzazione di recapito viene utilizzato per gli aggiornamenti di sistema e driver tutti operativi. Riduce la dimensione del download dal servizio Windows Update (WU) per la ricerca degli aggiornamenti da altri utenti all'interno della rete aziendale.


