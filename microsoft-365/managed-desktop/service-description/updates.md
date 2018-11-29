---
title: Come vengono gestiti gli aggiornamenti in Microsoft Managed Desktop
description: Mantenere aggiornati i Desktop gestiti Microsoft è un servizio di bilanciamento della velocità e la stabilità.
keywords: Servizio Microsoft Desktop gestiti, Microsoft 365, documentazione
ms.service: m365-md
author: jdeckerms
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: 513e03b7d703e0a9f78281ddac764d8a29ed5c8f
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868385"
---
# <a name="how-updates-are-handled-in-microsoft-managed-desktop"></a>Come vengono gestiti gli aggiornamenti in Microsoft Managed Desktop


<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/update-rings); do not delete.-->

<!--Update management -->

Microsoft Desktop gestiti si connette tutti i dispositivi a un'infrastruttura basata su cloud moderna. Mantenere aggiornati Windows, Office, driver, firmware e Store Microsoft Business degli aggiornamenti dell'applicazione è un servizio di bilanciamento della velocità e la stabilità. Squilla distribuzione verrà utilizzato per garantire del sistema operativo e distribuire i criteri in modo sicuro. 

## <a name="update-rings"></a>Aggiornare squilla

Desktop gestiti Microsoft utilizza quattro gruppi di Azure Active Directory per gestire gli aggiornamenti:

- Test: Chiama test solo è progettato per test e convalida delle modifiche apportate nel tenant dei clienti.  
- Primo: Innanzitutto deve essere un anello test anticipati con gli utenti esperti tech limitata che si desidera installare il software all'inizio ed essere soggetti alcuni aggiornamenti di versione non definitiva.
- Fast: L'opzione chiama fast è a cui si prevede un elevato numero di utenti.  L'obiettivo per questo chiama deve mantenere dispositivi aggiornato e protetto con una rapida velocità di distribuzione del software.  
- Ampia: L'opzione chiama lenta è un fuori aggiornamenti di qualità e funzionalità (in inglese) tradizionale bilanciato.  Aggiornamenti di qualità ancora vengono recapitati in modo rapido ritmo della presentazione, ma non immediatamente. 

Gli aggiornamenti del sistema chiama sono suddivise in qualità o gli aggiornamenti delle funzionalità:
- Qualità per la protezione, critical e driver aggiornamenti.  Si tratta in genere mensili aggiornamenti. 
- Aggiornamenti per la caratteristica contengono non solo sicurezza e le revisioni di qualità, ma anche importanti funzioni aggiunte e le modifiche. vengono rilasciati semestrale. 

Come funziona la promozione chiama:
- Microsoft Desktop gestiti consente di distribuire un nuovo aggiornamento qualità o funzionalità di base pianificazione specificata di seguito.
- Durante la distribuzione Desktop gestiti Microsoft esegue il monitoraggio di segnali di errore o per altri problemi (tramite segnali di telemetria e il sistema di supporto per l'utente finale). In questo caso, la distribuzione di tutti i squilla attuali e future immediatamente in pausa.
    - Esempio: se viene rilevato un problema durante la distribuzione di un aggiornamento di qualità prima chiama, quindi in primo luogo, Fast e ampia verrà tutti essere sospesa fino a quando non viene risolto il problema.
    - Problemi di compatibilità possono essere segnalati presentando un ticket nel portale di amministrazione IT di Desktop gestiti Microsoft.
- Aggiornamenti di qualità e funzionalità vengono sospese in modo indipendente.  Sospendi è valido per 35 giorni per impostazione predefinita, ma possono essere ridotto o estese in base al fatto è risolte il problema.
- Dopo aver installato lo squilla riavviato, in base alla pianificazione seguente riprende la distribuzione.
- Questo processo promozione si applica agli aggiornamenti la caratteristica e la qualità, anche se la sequenza temporale varia per ogni.

<table>
<tr><th colspan="5">Squilla e le impostazioni di rinvio</th></tr>
<tr><th>Tipo di aggiornamento</th><th>Chiama test</th><th>Funzionalità</th><th>Fast</th><th>Ampia</th></tr>
<tr><td>Aggiornamenti di qualità del sistema operativo</td><td>0 giorni</td><td>0 giorni</td><td>1 giorno</td><td>5 giorni</td></tr>
<tr><td>Aggiornamenti di funzionalità del sistema operativo</td><td>Canale semestrale (specifiche) + 0 giorni</td><td>Canale semestrale (specifiche) + 30 giorni</td><td>Canale semestrale (specifiche) + 60 giorni</td><td>Canale semestrale + 30 giorni</td></tr>
<tr><td>Driver/firmware</td><td colspan="4">Dopo la pianificazione per gli aggiornamenti di qualità</td></tr>
<tr><td>Definizione antivirus</td><td colspan="4">Aggiornamento con ogni analisi</td></tr>
<tr><td>Fare clic su Pro-più Office per l'esecuzione</td><td colspan="4">Allineata semestrale canale</td></tr>
</table>


## <a name="windows-insider-program"></a>Programma Windows persona interna

Desktop gestiti Microsoft non supporta i dispositivi che fanno parte del programma persona interna di Windows. Questo programma viene utilizzato per convalidare il software Windows versione non definitiva ed è progettato per i dispositivi di importanza non critici. Mentre si tratta di un importante progetto di Microsoft, non deve essere ampia distribuzione negli ambienti di produzione. 

Tutti i dispositivi sono stato riscontrati dal Windows compilazioni verranno inseriti in chiama Test e non viene incluso per l'aggiornamento contratti di servizio.

## <a name="bandwidth-management"></a>Gestione della larghezza di banda

Ottimizzazione di recapito viene utilizzato per gli aggiornamenti di sistema e driver tutti operativi. Riduce la dimensione del download dal servizio Windows Update (WU) per la ricerca degli aggiornamenti da altri utenti all'interno della rete aziendale.


