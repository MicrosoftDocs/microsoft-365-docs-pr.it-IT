---
title: ID evento e codici di errore di Microsoft Defender AV
description: Cercare le cause e le soluzioni per Antivirus Microsoft Defender e gli errori degli eventi
keywords: evento, codice di errore, siem, registrazione, risoluzione dei problemi, wef, inoltro di eventi di Windows
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/11/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: cd222760f3a5cc005c679bf28365237cc70e8950
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275349"
---
# <a name="review-event-logs-and-error-codes-to-troubleshoot-issues-with-microsoft-defender-antivirus"></a>Esaminare i log eventi e i codici di errore per risolvere i problemi relativi a Microsoft Defender Antivirus

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**

- [Microsoft Defender per endpoint](/microsoft-365/security/defender-endpoint/)

Se si verifica un problema con Antivirus Microsoft Defender, è possibile cercare nelle tabelle di questo argomento un problema corrispondente e una soluzione potenziale.

L'elenco delle tabelle:

- [Antivirus Microsoft Defender ID evento](#windows-defender-av-ids) (si applicano sia a Windows 10 che Windows Server 2016)
- [Antivirus Microsoft Defender di errore del client](#error-codes)
- [Codici Antivirus Microsoft Defender client interni (utilizzati da Microsoft durante lo sviluppo e il testing)](#internal-error-codes)

> [!TIP]
> Puoi anche visitare il sito Web demo di Microsoft Defender for Endpoint [all'indirizzo demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) per verificare che le funzionalità seguenti funzionino:
> 
> - Protezione fornita dal cloud
> - Apprendimento rapido (incluso Blocco a prima vista)
> - Blocco di applicazioni potenzialmente indesiderate

<a id="windows-defender-av-ids"></a>
## <a name="microsoft-defender-antivirus-event-ids"></a>Antivirus Microsoft Defender ID evento

Antivirus Microsoft Defender registra gli ID evento nel Windows eventi.

È possibile visualizzare direttamente il registro eventi oppure, se si dispone di uno strumento siem (Security Information and Event Management) di terze parti, è inoltre possibile utilizzare gli ID evento [client Antivirus Microsoft Defender](troubleshoot-microsoft-defender-antivirus.md#windows-defender-av-ids) per esaminare eventi ed errori specifici dagli endpoint.

Nella tabella di questa sezione sono elencati gli ID Antivirus Microsoft Defender eventi principali e, se possibile, vengono fornite soluzioni suggerite per correggere o risolvere l'errore. 

## <a name="to-view-a-microsoft-defender-antivirus-event"></a>Per visualizzare un Antivirus Microsoft Defender evento

1.  Aprire **visualizzatore eventi**.
2.  Nell'albero della console espandere **Registri applicazioni** e servizi , **quindi Microsoft**, quindi **Windows**, **quindi Windows Defender**.
3.  Fare doppio clic su **Operativo**.
4.  Nel riquadro dei dettagli, visualizzare l'elenco dei singoli eventi per trovare l'evento.
5.  Fare clic sull'evento per visualizzare dettagli specifici su un evento nel riquadro inferiore, nelle **schede Generale** **e** Dettagli.

<table> 
<tr>
<th colspan="2" >ID evento: 1000</th>
</tr>
<tr>
<td>
Nome simbolico:
</td>
<td>
<b>MALWAREPROTECTION_SCAN_STARTED</b>
</td>
</tr>
<tr>
<td>
Messaggio:
</td>
<td >
<b>Analisi antimalware avviata. </b>
</td>
</tr>
<tr>
<td >
Descrizione:
</td>
<td >
<dl>
<dt>ID analisi: &lt; Numero ID dell'analisi &gt; pertinente.</dt> 
<dt> Tipo di analisi: &lt; Tipo di &gt; analisi, ad esempio:<ul>
<li>Antivirus</li>
<li>Antispyware</li>
<li>Antimalware</li>
</ul>
</dt>
<dt>Parametri analisi: &lt; parametri di &gt; analisi, ad esempio:<ul>
<li>Analisi completa</li>
<li>Analisi rapida</li>
<li>Analisi del cliente</li>
</ul>
</dt>
<dt>Risorse analisi: &lt; Risorse (ad esempio file/directory/BHO) &gt; analizzate.</dt> 
<dt>Utente: &lt; Dominio &gt; \& lt; Utente &gt; </dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">ID evento: 1001</th>
</tr>
<tr><td>
Nome simbolico:
</td>
<td >
<b>MALWAREPROTECTION_SCAN_COMPLETED</b>
</td>
</tr>
<tr>
<td>
Messaggio:
</td>
<td >
<b>Analisi antimalware completata.</b>
</td>
</tr>
<tr>
<td>
Descrizione:
</td>
<td >
<dl>
<dt>ID analisi: &lt; Numero ID dell'analisi &gt; pertinente.</dt> 
<dt> Tipo di analisi: &lt; Tipo di &gt; analisi, ad esempio:<ul>
<li>Antivirus</li>
<li>Antispyware</li>
<li>Antimalware</li>
</ul>
</dt>
<dt>Parametri analisi: &lt; parametri di &gt; analisi, ad esempio:<ul>
<li>Analisi completa</li>
<li>Analisi rapida</li>
<li>Analisi del cliente</li>
</ul>
</dt>
<dt>Utente: &lt; Dominio &gt; \& lt; User &gt; </dt>
<dt>Scan Time: &lt; durata di &gt; un'analisi.</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">ID evento: 1002</th>
</tr>
<tr><td>
Nome simbolico:
</td>
<td >
<b>MALWAREPROTECTION_SCAN_CANCELLED </b>
</td>
</tr>
<tr>
<td>
Messaggio:
</td>
<td >
<b>Un'analisi antimalware è stata interrotta prima del termine. </b>
</td>
</tr>
<tr>
<td>
Descrizione:
</td>
<td >
<dl>
<dt>ID analisi: &lt; Numero ID dell'analisi &gt; pertinente.</dt> 
<dt> Tipo di analisi: &lt; Tipo di &gt; analisi, ad esempio:<ul>
<li>Antivirus</li>
<li>Antispyware</li>
<li>Antimalware</li>
</ul>
</dt>
<dt>Parametri analisi: &lt; parametri di &gt; analisi, ad esempio:<ul>
<li>Analisi completa</li>
<li>Analisi rapida</li>
<li>Analisi del cliente</li>
</ul>
</dt>
<dt>Utente: &lt; Dominio &gt; &amp; lt; User &gt; </dt>
<dt>Scan Time: &lt; durata di &gt; un'analisi.</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">ID evento: 1003</th>
</tr>
<tr><td>
Nome simbolico:
</td>
<td >
<b>MALWAREPROTECTION_SCAN_PAUSED </b>
</td>
</tr>
<tr>
<td>
Messaggio:
</td>
<td >
<b>Un'analisi antimalware è stata sospesa. </b>
</td>
</tr>
<tr>
<td>
Descrizione:
</td>
<td >
<dl>
<dt>ID analisi: &lt; Numero ID dell'analisi &gt; pertinente.</dt> 
<dt> Tipo di analisi: &lt; Tipo di &gt; analisi, ad esempio:<ul>
<li>Antivirus</li>
<li>Antispyware</li>
<li>Antimalware</li>
</ul>
</dt>
<dt>Parametri analisi: &lt; parametri di &gt; analisi, ad esempio:<ul>
<li>Analisi completa</li>
<li>Analisi rapida</li>
<li>Analisi del cliente</li>
</ul>
</dt>
<dt>Utente: &lt; Dominio &gt; \& lt; Utente&gt;</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">ID evento: 1004</th>
</tr>
<tr><td>
Nome simbolico:
</td>
<td >
<b>MALWAREPROTECTION_SCAN_RESUMED </b>
</td>
</tr>
<tr>
<td>
Messaggio:
</td>
<td >
<b>È stata ripresa un'analisi antimalware. </b>
</td>
</tr>
<tr>
<td>
Descrizione:
</td>
<td >
<dl>
<dt>ID analisi: &lt; Numero ID dell'analisi &gt; pertinente.</dt> 
<dt> Tipo di analisi: &lt; Tipo di &gt; analisi, ad esempio:<ul>
<li>Antivirus</li>
<li>Antispyware</li>
<li>Antimalware</li>
</ul>
</dt>
<dt>Parametri analisi: &lt; parametri di &gt; analisi, ad esempio:<ul>
<li>Analisi completa</li>
<li>Analisi rapida</li>
<li>Analisi del cliente</li>
</ul>
</dt>
<dt>Utente: &lt; Dominio &gt; \& lt; Utente&gt;</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">ID evento: 1005</th>
</tr>
<tr><td>
Nome simbolico:
</td>
<td >
<b>MALWAREPROTECTION_SCAN_FAILED </b>
</td>
</tr>
<tr>
<td>
Messaggio:
</td>
<td >
<b>Analisi antimalware non riuscita. </b>
</td>
</tr>
<tr>
<td>
Descrizione:
</td>
<td >
<dl>
<dt>ID analisi: &lt; Numero ID dell'analisi &gt; pertinente.</dt> 
<dt> Tipo di analisi: &lt; Tipo di &gt; analisi, ad esempio:<ul>
<li>Antivirus</li>
<li>Antispyware</li>
<li>Antimalware</li>
</ul>
</dt>
<dt>Parametri analisi: &lt; parametri di &gt; analisi, ad esempio:<ul>
<li>Analisi completa</li>
<li>Analisi rapida</li>
<li>Analisi del cliente</li>
</ul>
</dt>
<dt>Utente: &lt; Dominio &gt; \& lt; User &gt; </dt>
<dt>Error Code: &lt; Codice di errore Codice di risultato associato allo stato della &gt; minaccia. Valori HRESULT standard.</dt> 
<dt>Descrizione errore: &lt; Descrizione &gt; dell'errore Descrizione dell'errore.</dt>
</dl>
</td>
</tr>
<tr>
<td>
Azione utente:
</td>
<td >
Il client antivirus ha rilevato un errore e l'analisi corrente è stata interrotta. L'analisi potrebbe non riuscire a causa di un problema sul lato client. Questo record di evento include l'ID analisi, il tipo di analisi (Antivirus Microsoft Defender, antispyware, antimalware), i parametri di analisi, l'utente che ha avviato l'analisi, il codice di errore e una descrizione dell'errore.
Per risolvere i problemi relativi a questo evento:
<ol>
<li>Eseguire di nuovo l'analisi.</li>
<li>Se si verifica un errore nello stesso modo, accedere al <b></b> sito del Supporto <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Tecnico Microsoft,</a>immettere il numero di errore nella casella Cerca per cercare il codice di errore.</li>
<li>Contatta il <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Supporto tecnico Microsoft</a>.
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2">ID evento: 1006</th>
</tr>
<tr><td>
Nome simbolico:
</td>
<td >
<b>MALWAREPROTECTION_MALWARE_DETECTED </b>
</td>
</tr>
<tr>
<td>
Messaggio:
</td>
<td >
<b>Il motore antimalware ha rilevato malware o altro software potenzialmente indesiderato. </b>
</td>
</tr>
<tr>
<td>
Descrizione:
</td>
<td >
Per ulteriori informazioni, vedere gli argomenti seguenti:
<dl>
<dt>Nome: &lt; ID &gt; nome</dt>
<dt>minaccia: &lt; Gravità &gt; ID</dt> 
<dt> minaccia: &lt; &gt; Gravità, ad esempio:<ul>
<li>Bassa</li>
<li>Moderato</li>
<li>Fortemente</li>
<li>Grave</li>
</ul>
</dt>
<dt>Categoria: &lt; Descrizione della &gt; categoria, ad esempio qualsiasi tipo di minaccia o malware.</dt> 
<dt>Percorso: &lt; Percorso &gt; file</dt> 
<dt> Origine rilevamento: &lt; origine &gt; rilevamento, ad esempio:<ul>
<li>Unknown</li>
<li>Computer locale</li>
<li>Condivisione di rete</li>
<li>Internet</li>
<li>Traffico in ingresso</li>
<li>Traffico in uscita</li>
</ul>
</dt>
<dt>Tipo di rilevamento: &lt; tipo di &gt; rilevamento, ad esempio:<ul>
<li>Euristica</li>
<li>Generale</li>
<li>Concrete</li>
<li>Firma dinamica</li>
</ul>
</dt>
<dt>Origine di rilevamento: &lt; origine &gt; di rilevamento, ad esempio:<ul>
<li>Utente: avviato dall'utente</li>
<li>Sistema: sistema avviato</li>
<li>Tempo reale: componente in tempo reale avviato</li>
<li>IOAV: download di Internet Outlook express allegati avviati</li>
<li>NIS: sistema di ispezione della rete</li>
<li>IEPROTECT: IE - IExtensionValidation; ciò protegge dai controlli delle pagine Web dannosi</li>
<li>Antimalware di avvio anticipato (ELAM). Ciò include il malware rilevato dalla sequenza di avvio</li>
<li>Attestazione remota</li>
</ul>Antimalware Scan Interface (AMSI). Usato principalmente per proteggere gli script (PS, VBS), anche se può essere richiamato anche da terze parti.
Stato controllo </dt> 
<dt>dell'account utente: &lt; &gt; Stato</dt>
<dt>Utente: &lt; Dominio &gt; \& lt; User &gt; </dt>
<dt>Process Name: &lt; Process &gt; in the PID</dt>
<dt>Signature Version: &lt; Definition version &gt; </dt>Engine
<dt>Version: Antimalware Engine &lt; version &gt; </dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">ID evento: 1007</th>
</tr>
<tr><td>
Nome simbolico:
</td>
<td >
<b>MALWAREPROTECTION_MALWARE_ACTION_TAKEN </b>
</td>
</tr>
<tr>
<td>
Messaggio:
</td>
<td >
<b>La piattaforma antimalware ha eseguito un'azione per proteggere il sistema da malware o altro software potenzialmente indesiderato. </b>
</td>
</tr>
<tr>
<td>
Descrizione:
</td>
<td >
Antivirus Microsoft Defender ha intrapreso azioni per proteggere il computer da malware o altro software potenzialmente indesiderato. Per ulteriori informazioni, vedere gli argomenti seguenti:
<dl>
<dt>Utente: &lt; Dominio &gt; \& lt; Nome &gt; </dt>
<dt>utente: &lt; ID nome minaccia: &gt; </dt>
<dt> &lt; Gravità ID &gt; </dt> 
<dt> minaccia: &lt; Gravità, ad &gt; esempio:<ul>
<li>Bassa</li>
<li>Moderato</li>
<li>Fortemente</li>
<li>Grave</li>
</ul>
</dt>
<dt>Categoria: &lt; Descrizione della &gt; categoria, ad esempio qualsiasi tipo di minaccia o malware.</dt> 
<dt> Azione: &lt; Azione , ad &gt; esempio:<ul>
<li>Clean: la risorsa è stata pulita</li>
<li>Quarantena: la risorsa è stata messi in quarantena</li>
<li>Rimuovi: la risorsa è stata eliminata</li>
<li>Consenti: la risorsa è stata consentita per l'esecuzione/l'esistenza</li>
<li>Definito dall'utente: azione definita dall'utente che in genere è una di queste azioni specificate dall'utente</li>
<li>Nessuna azione: nessuna azione</li>
<li>Blocca: l'esecuzione della risorsa è stata bloccata</li>
</ul>
</dt>
<dt>Stato: &lt; Status &gt; </dt>
<dt>Signature Version: &lt; Definition version &gt; </dt>Engine
<dt>Version: Antimalware Engine &lt; version &gt; </dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">ID evento: 1008</th>
</tr>
<tr><td>
Nome simbolico:
</td>
<td >
<b>MALWAREPROTECTION_MALWARE_ACTION_FAILED</b>
</td>
</tr>
<tr>
<td>
Messaggio:
</td>
<td >
<b>La piattaforma antimalware ha tentato di eseguire un'azione per proteggere il sistema da malware o altro software potenzialmente indesiderato, ma l'azione non è riuscita.</b>
</td>
</tr>
<tr>
<td>
Descrizione:
</td>
<td >
Antivirus Microsoft Defender si è verificato un errore durante l'azione su malware o altro software potenzialmente indesiderato. Per ulteriori informazioni, vedere gli argomenti seguenti:
<dl>
<dt>Utente: &lt; Dominio &gt; \& lt; Nome &gt; </dt>
<dt>utente: &lt; ID nome minaccia: &gt; </dt>
<dt> &lt; Gravità ID &gt; </dt> 
<dt> minaccia: &lt; Gravità, ad &gt; esempio:<ul>
<li>Bassa</li>
<li>Moderato</li>
<li>Fortemente</li>
<li>Grave</li>
</ul>
</dt>
<dt>Categoria: &lt; Descrizione della &gt; categoria, ad esempio qualsiasi tipo di minaccia o malware.</dt> 
<dt>Percorso: &lt; Percorso &gt; file</dt> 
<dt> Azione: &lt; &gt; Azione, ad esempio:<ul>
<li>Clean: la risorsa è stata pulita</li>
<li>Quarantena: la risorsa è stata messi in quarantena</li>
<li>Rimuovi: la risorsa è stata eliminata</li>
<li>Consenti: la risorsa è stata consentita per l'esecuzione/l'esistenza</li>
<li>Definito dall'utente: azione definita dall'utente che in genere è una di queste azioni specificate dall'utente</li>
<li>Nessuna azione: nessuna azione</li>
<li>Blocca: l'esecuzione della risorsa è stata bloccata</li>
</ul>
</dt>
<dt>Codice errore: &lt; Codice di errore &gt; Codice di risultato associato allo stato della minaccia. Valori HRESULT standard. </dt> 
<dt>Descrizione errore: &lt; Descrizione &gt; errore Descrizione dell'errore.</dt> 
<dt>Stato: &lt; Status &gt; </dt>
<dt>Signature Version: &lt; Definition version &gt; </dt>Engine
<dt>Version: Antimalware Engine &lt; version &gt; </dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">ID evento: 1009</th>
</tr>
<tr><td>
Nome simbolico:
</td>
<td >
<b>MALWAREPROTECTION_QUARANTINE_RESTORE </b>
</td>
</tr>
<tr>
<td>
Messaggio:
</td>
<td >
<b>La piattaforma antimalware ha ripristinato un elemento dalla quarantena. </b>
</td>
</tr>
<tr>
<td>
Descrizione:
</td>
<td >
Antivirus Microsoft Defender ha ripristinato un elemento dalla quarantena. Per ulteriori informazioni, vedere gli argomenti seguenti:
<dl>
<dt>Nome: &lt; ID &gt; nome</dt>
<dt>minaccia: &lt; Gravità &gt; ID</dt> 
<dt> minaccia: &lt; &gt; Gravità, ad esempio:<ul>
<li>Bassa</li>
<li>Moderato</li>
<li>Fortemente</li>
<li>Grave</li>
</ul>
</dt>
<dt>Categoria: &lt; Descrizione della &gt; categoria, ad esempio qualsiasi tipo di minaccia o malware.</dt> 
<dt>Percorso: &lt; Percorso &gt; file</dt>
<dt>Utente: &lt; Dominio &gt; \& lt; Versione &gt; </dt>
<dt>firma utente: &lt; versione definizione &gt; </dt>Versione
<dt>motore: Antimalware Engine &lt; versione &gt; </dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">ID evento: 1010</th>
</tr>
<tr><td>
Nome simbolico:
</td>
<td >
<b>MALWAREPROTECTION_QUARANTINE_RESTORE_FAILED </b>
</td>
</tr>
<tr>
<td>
Messaggio:
</td>
<td >
<b>La piattaforma antimalware non è in grado di ripristinare un elemento dalla quarantena. </b>
</td>
</tr>
<tr>
<td>
Descrizione:
</td>
<td >
Antivirus Microsoft Defender si è verificato un errore durante il tentativo di ripristinare un elemento dalla quarantena. Per ulteriori informazioni, vedere gli argomenti seguenti:
<dl>
<dt>Nome: &lt; ID &gt; nome</dt>
<dt>minaccia: &lt; Gravità &gt; ID</dt> 
<dt> minaccia: &lt; &gt; Gravità, ad esempio:<ul>
<li>Bassa</li>
<li>Moderato</li>
<li>Fortemente</li>
<li>Grave</li>
</ul>
</dt>
<dt>Categoria: &lt; Descrizione della &gt; categoria, ad esempio qualsiasi tipo di minaccia o malware.</dt> 
<dt>Percorso: &lt; Percorso &gt; file</dt>
<dt>Utente: &lt; Dominio &gt; \& lt; User &gt; </dt>
<dt>Error Code: &lt; Codice di errore Codice di risultato associato allo stato della &gt; minaccia. Valori HRESULT standard. </dt> 
<dt>Descrizione errore: &lt; Descrizione &gt; errore Descrizione dell'errore.</dt> 
<dt>Versione firma: &lt; Versione &gt; della definizione</dt>
<dt>Versione motore: Antimalware Engine &lt; versione &gt; </dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">ID evento: 1011</th>
</tr>
<tr><td>
Nome simbolico:
</td>
<td >
<b>MALWAREPROTECTION_QUARANTINE_DELETE</b>
</td>
</tr>
<tr>
<td>
Messaggio:
</td>
<td >
<b>La piattaforma antimalware ha eliminato un elemento dalla quarantena. </b>
</td>
</tr>
<tr>
<td>
Descrizione:
</td>
<td >
Antivirus Microsoft Defender ha eliminato un elemento dalla quarantena.<br/>Per ulteriori informazioni, vedere gli argomenti seguenti:
<dl>
<dt>Nome: &lt; ID &gt; nome</dt>
<dt>minaccia: &lt; Gravità &gt; ID</dt> 
<dt> minaccia: &lt; &gt; Gravità, ad esempio:<ul>
<li>Bassa</li>
<li>Moderato</li>
<li>Fortemente</li>
<li>Grave</li>
</ul>
</dt>
<dt>Categoria: &lt; Descrizione della &gt; categoria, ad esempio qualsiasi tipo di minaccia o malware.</dt> 
<dt>Percorso: &lt; Percorso &gt; file</dt>
<dt>Utente: &lt; Dominio &gt; \& lt; Versione &gt; </dt>
<dt>firma utente: &lt; versione definizione &gt; </dt>Versione
<dt>motore: Antimalware Engine &lt; versione &gt; </dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">ID evento: 1012</th>
</tr>
<tr><td>
Nome simbolico:
</td>
<td >
<b>MALWAREPROTECTION_QUARANTINE_DELETE_FAILED </b>
</td>
</tr>
<tr>
<td>
Messaggio:
</td>
<td >
<b>La piattaforma antimalware non è stata in grado di eliminare un elemento dalla quarantena.</b>
</td>
</tr>
<tr>
<td>
Descrizione:
</td>
<td >
Antivirus Microsoft Defender si è verificato un errore durante il tentativo di eliminare un elemento dalla quarantena.
Per ulteriori informazioni, vedere gli argomenti seguenti:
<dl>
<dt>Nome: &lt; ID &gt; nome</dt>
<dt>minaccia: &lt; Gravità &gt; ID</dt> 
<dt> minaccia: &lt; &gt; Gravità, ad esempio:<ul>
<li>Bassa</li>
<li>Moderato</li>
<li>Fortemente</li>
<li>Grave</li>
</ul>
</dt>
<dt>Categoria: &lt; Descrizione della &gt; categoria, ad esempio qualsiasi tipo di minaccia o malware.</dt> 
<dt>Percorso: &lt; Percorso &gt; file</dt>
<dt>Utente: &lt; Dominio &gt; \& lt; User &gt; </dt>
<dt>Error Code: &lt; Codice di errore Codice di risultato associato allo stato della &gt; minaccia. Valori HRESULT standard. </dt> 
<dt>Descrizione errore: &lt; Descrizione &gt; errore Descrizione dell'errore.</dt> 
<dt>Versione firma: &lt; Versione &gt; della definizione</dt>
<dt>Versione motore: Antimalware Engine &lt; versione &gt; </dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">ID evento: 1013</th>
</tr>
<tr><td>
Nome simbolico:
</td>
<td >
<b>MALWAREPROTECTION_MALWARE_HISTORY_DELETE </b>
</td>
</tr>
<tr>
<td>
Messaggio:
</td>
<td >
<b>La piattaforma antimalware ha eliminato la cronologia del malware e di altro software potenzialmente indesiderato.</b>
</td>
</tr>
<tr>
<td>
Descrizione:
</td>
<td >
Antivirus Microsoft Defender ha rimosso la cronologia del malware e di altro software potenzialmente indesiderato.
<dl>
<dt>Time: ora in cui si è verificato l'evento, ad esempio quando la cronologia viene eliminata. Questo parametro non viene utilizzato negli eventi di minaccia in modo da non creare confusione riguardo al tempo di correzione o all'infezione. Per questi, li chiamiamo in modo specifico come Tempo azione o Tempo di rilevamento.</dt> 
<dt>Utente: &lt; Dominio &gt; \& lt; Utente &gt; </dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">ID evento: 1014</th>
</tr>
<tr><td>
Nome simbolico:
</td>
<td >
<b>MALWAREPROTECTION_MALWARE_HISTORY_DELETE_FAILED </b>
</td>
</tr>
<tr>
<td>
Messaggio:
</td>
<td >
La piattaforma antimalware non è in grado di eliminare la cronologia del malware e di altro software potenzialmente indesiderato.
</td>
</tr>
<tr>
<td>
Descrizione:
</td>
<td >
Antivirus Microsoft Defender si è verificato un errore durante il tentativo di rimuovere la cronologia del malware e di altro software potenzialmente indesiderato.
<dl>
<dt>Time: ora in cui si è verificato l'evento, ad esempio quando la cronologia viene eliminata. Questo parametro non viene utilizzato negli eventi di minaccia in modo da non creare confusione riguardo al tempo di correzione o all'infezione. Per questi, li chiamiamo in modo specifico come Tempo azione o Tempo di rilevamento.</dt> 
<dt>Utente: &lt; Dominio &gt; \& lt; User &gt; </dt>
<dt>Error Code: &lt; Codice di errore Codice di risultato associato allo stato della &gt; minaccia. Valori HRESULT standard. </dt> 
<dt>Descrizione errore: &lt; Descrizione &gt; errore Descrizione dell'errore.</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">ID evento: 1015</th>
</tr>
<tr><td>
Nome simbolico:
</td>
<td >
<b>MALWAREPROTECTION_BEHAVIOR_DETECTED </b>
</td>
</tr>
<tr>
<td>
Messaggio:
</td>
<td >
<b>La piattaforma antimalware ha rilevato comportamenti sospetti.</b>
</td>
</tr>
<tr>
<td>
Descrizione:
</td>
<td >
Antivirus Microsoft Defender ha rilevato un comportamento sospetto.<br/>Per ulteriori informazioni, vedere gli argomenti seguenti:
<dl>
<dt>Nome: &lt; ID &gt; nome</dt>
<dt>minaccia: &lt; Gravità &gt; ID</dt> 
<dt> minaccia: &lt; &gt; Gravità, ad esempio:<ul>
<li>Bassa</li>
<li>Moderato</li>
<li>Fortemente</li>
<li>Grave</li>
</ul>
</dt>
<dt>Categoria: &lt; Descrizione della &gt; categoria, ad esempio qualsiasi tipo di minaccia o malware.</dt> 
<dt>Percorso: &lt; Percorso &gt; file</dt> 
<dt> Origine rilevamento: &lt; origine &gt; rilevamento, ad esempio:
<ul>
<li>Unknown</li>
<li>Computer locale</li>
<li>Condivisione di rete</li>
<li>Internet</li>
<li>Traffico in ingresso</li>
<li>Traffico in uscita</li>
</ul>
</dt>
<dt>Tipo di rilevamento: &lt; tipo di &gt; rilevamento, ad esempio:<ul>
<li>Euristica</li>
<li>Generale</li>
<li>Concrete</li>
<li>Firma dinamica</li>
</ul>
</dt>
<dt>Origine di rilevamento: &lt; origine &gt; di rilevamento, ad esempio:<ul>
<li>Utente: avviato dall'utente</li>
<li>Sistema: sistema avviato</li>
<li>Tempo reale: componente in tempo reale avviato</li>
<li>IOAV: download di Internet Outlook express allegati avviati</li>
<li>NIS: sistema di ispezione della rete</li>
<li>IEPROTECT: IE - IExtensionValidation; ciò protegge dai controlli delle pagine Web dannosi</li>
<li>Antimalware di avvio anticipato (ELAM). Ciò include il malware rilevato dalla sequenza di avvio</li>
<li>Attestazione remota</li>
</ul>Antimalware Scan Interface (AMSI). Usato principalmente per proteggere gli script (PS, VBS), anche se può essere richiamato anche da terze parti.
Stato controllo </dt> 
<dt>dell'account utente: &lt; &gt; Stato</dt>
<dt>Utente: &lt; Dominio &gt; \& lt; User &gt; </dt>
<dt>Process Name: &lt; Process &gt; in the PID</dt>
<dt>Signature ID: Enumeration matching severity.</dt> 
<dt>Versione firma: &lt; Versione &gt; definizione</dt>
<dt>Versione motore: &lt; Antimalware Engine &gt; versione</dt>
<dt>Fidelity Label:</dt>
<dt>Target File Name: File name Name Name &lt; of the &gt; file.</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">ID evento: 1116</th>
</tr>
<tr><td>
Nome simbolico:
</td>
<td >
<b>MALWAREPROTECTION_STATE_MALWARE_DETECTED</b>
</td>
</tr>
<tr>
<td>
Messaggio:
</td>
<td >
<b>La piattaforma antimalware ha rilevato malware o altro software potenzialmente indesiderato. </b>
</td>
</tr>
<tr>
<td>
Descrizione:
</td>
<td >
Antivirus Microsoft Defender ha rilevato malware o altro software potenzialmente indesiderato.<br/>Per ulteriori informazioni, vedere gli argomenti seguenti:
<dl>
<dt>Nome: &lt; ID &gt; nome</dt>
<dt>minaccia: &lt; Gravità &gt; ID</dt> 
<dt> minaccia: &lt; &gt; Gravità, ad esempio:<ul>
<li>Bassa</li>
<li>Moderato</li>
<li>Fortemente</li>
<li>Grave</li>
</ul>
</dt>
<dt>Categoria: &lt; Descrizione della &gt; categoria, ad esempio qualsiasi tipo di minaccia o malware.</dt> 
<dt>Percorso: &lt; Percorso &gt; file</dt> 
<dt> Origine rilevamento: &lt; origine &gt; rilevamento, ad esempio:
<ul>
<li>Unknown</li>
<li>Computer locale</li>
<li>Condivisione di rete</li>
<li>Internet</li>
<li>Traffico in ingresso</li>
<li>Traffico in uscita</li>
</ul>
</dt>
<dt>Tipo di rilevamento: &lt; tipo di &gt; rilevamento, ad esempio:<ul>
<li>Euristica</li>
<li>Generale</li>
<li>Concrete</li>
<li>Firma dinamica</li>
</ul>
</dt>
<dt>Origine di rilevamento: &lt; origine &gt; di rilevamento, ad esempio:<ul>
<li>Utente: avviato dall'utente</li>
<li>Sistema: sistema avviato</li>
<li>Tempo reale: componente in tempo reale avviato</li>
<li>IOAV: download di Internet Outlook express allegati avviati</li>
<li>NIS: sistema di ispezione della rete</li>
<li>IEPROTECT: IE - IExtensionValidation; ciò protegge dai controlli delle pagine Web dannosi</li>
<li>Antimalware di avvio anticipato (ELAM). Ciò include il malware rilevato dalla sequenza di avvio</li>
<li>Attestazione remota</li>
</ul>Antimalware Scan Interface (AMSI). Usato principalmente per proteggere gli script (PS, VBS), anche se può essere richiamato anche da terze parti.
Utente </dt> 
<dt>UAC: &lt; Dominio &gt; \& lt; User &gt; </dt>
<dt>Process Name: &lt; Process &gt; in the PID</dt>
<dt>Signature Version: &lt; Definition version &gt; </dt>Engine
<dt>Version: Antimalware Engine &lt; version &gt; </dt>
</dl>
</td>
</tr>
<tr>
<td>
Azione utente:
</td>
<td >
Non è necessaria alcuna azione. Antivirus Microsoft Defender possibile sospendere ed eseguire azioni di routine su questa minaccia. Se si desidera rimuovere manualmente la minaccia, nell'interfaccia Antivirus Microsoft Defender fare clic su <b>Pulisci computer</b>.
</td>
</tr>
<tr>
<th colspan="2">ID evento: 1117</th>
</tr>
<tr><td>
Nome simbolico:
</td>
<td >
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_TAKEN </b>
</td>
</tr>
<tr>
<td>
Messaggio:
</td>
<td >
<b>La piattaforma antimalware ha eseguito un'azione per proteggere il sistema da malware o altro software potenzialmente indesiderato. </b>
</td>
</tr>
<tr>
<td>
Descrizione:
</td>
<td >
Antivirus Microsoft Defender ha intrapreso azioni per proteggere il computer da malware o altro software potenzialmente indesiderato.<br/>Per ulteriori informazioni, vedere gli argomenti seguenti:
<dl>
<dt>Nome: &lt; ID &gt; nome</dt>
<dt>minaccia: &lt; Gravità &gt; ID</dt> 
<dt> minaccia: &lt; &gt; Gravità, ad esempio:<ul>
<li>Bassa</li>
<li>Moderato</li>
<li>Fortemente</li>
<li>Grave</li>
</ul>
</dt>
<dt>Categoria: &lt; Descrizione della &gt; categoria, ad esempio qualsiasi tipo di minaccia o malware.</dt> 
<dt>Percorso: &lt; Percorso &gt; file</dt> 
<dt> Origine rilevamento: &lt; origine &gt; rilevamento, ad esempio:
<ul>
<li>Unknown</li>
<li>Computer locale</li>
<li>Condivisione di rete</li>
<li>Internet</li>
<li>Traffico in ingresso</li>
<li>Traffico in uscita</li>
</ul>
</dt>
<dt>Tipo di rilevamento: &lt; tipo di &gt; rilevamento, ad esempio:<ul>
<li>Euristica</li>
<li>Generale</li>
<li>Concrete</li>
<li>Firma dinamica</li>
</ul>
</dt>
<dt>Origine di rilevamento: &lt; origine &gt; di rilevamento, ad esempio:<ul>
<li>Utente: avviato dall'utente</li>
<li>Sistema: sistema avviato</li>
<li>Tempo reale: componente in tempo reale avviato</li>
<li>IOAV: download di Internet Outlook express allegati avviati</li>
<li>NIS: sistema di ispezione della rete</li>
<li>IEPROTECT: IE - IExtensionValidation; ciò protegge dai controlli delle pagine Web dannosi</li>
<li>Antimalware di avvio anticipato (ELAM). Ciò include il malware rilevato dalla sequenza di avvio</li>
<li>Attestazione remota</li>
</ul>Antimalware Scan Interface (AMSI). Usato principalmente per proteggere gli script (PS, VBS), anche se può essere richiamato anche da terze parti.
Utente </dt> 
<dt>UAC: &lt; Dominio &gt; \& lt; User &gt; </dt>
<dt>Process Name: &lt; Process &gt; in the PID</dt> 
<dt> Action: &lt; Action , ad &gt; esempio:<ul>
<li>Clean: la risorsa è stata pulita</li>
<li>Quarantena: la risorsa è stata messi in quarantena</li>
<li>Rimuovi: la risorsa è stata eliminata</li>
<li>Consenti: la risorsa è stata consentita per l'esecuzione/l'esistenza</li>
<li>Definito dall'utente: azione definita dall'utente che in genere è una di queste azioni specificate dall'utente</li>
<li>Nessuna azione: nessuna azione</li>
<li>Blocca: l'esecuzione della risorsa è stata bloccata</li>
</ul>
</dt>
<dt>Stato azione: &lt; Descrizione delle &gt; azioni aggiuntive</dt>
<dt>Codice di errore: Codice di errore &lt; Codice di risultato associato allo stato della &gt; minaccia. Valori HRESULT standard.</dt> 
<dt>Descrizione errore: &lt; Descrizione &gt; dell'errore Descrizione dell'errore.</dt> 
<dt>Versione firma: &lt; Versione &gt; del</dt>motore versione
<dt>definizione: &lt; versione Antimalware Engine &gt; </dt> NOTA: ogni volta che Antivirus Microsoft Defender, Microsoft Security Essentials, Lo strumento di rimozione di software dannoso o System Center Endpoint Protection rileva un malware, ripristina le impostazioni di sistema e i servizi seguenti che il malware potrebbe essere cambiato:<ul>
<li>Impostazione predefinita di Internet Explorer o Microsoft Edge predefinita</li>
<li>Impostazioni di Controllo di accesso utente</li>
<li>Impostazioni di Chrome</li>
<li>Dati di controllo di avvio</li>
<li>Impostazioni del Registro di sistema di Regedit e Task Manager</li>
<li>Windows Aggiornamento, Servizio trasferimento intelligente in background e Servizio di chiamata di procedura remota</li>
<li>Windows File del sistema operativo</li></ul>
Il contesto precedente si applica alle versioni client e server seguenti:
<table>
<tr>
<th>Sistema operativo</th>
<th>Versione del sistema operativo</th>
</tr>
<tr>
<td>
Sistema operativo client
</td>
<td>
Windows Vista (Service Pack 1 o Service Pack 2), Windows 7 e versioni successive
</td>
</tr>
<tr>
<td>
Sistema operativo server
</td>
<td>
Windows Server 2008, Windows Server 2008 R2, Windows Server 2012 e Windows Server 2016
</td>
</tr>
</table>
</dl>
</td>
</tr>
<tr>
<td>
Azione utente:
</td>
<td >
Non è necessaria alcuna azione. Antivirus Microsoft Defender rimosso o messo in quarantena una minaccia. 
</td>
</tr>
<tr>
<th colspan="2">ID evento: 1118</th>
</tr>
<tr><td>
Nome simbolico:
</td>
<td >
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_FAILED</b>
</td>
</tr>
<tr>
<td>
Messaggio:
</td>
<td >
<b>La piattaforma antimalware ha tentato di eseguire un'azione per proteggere il sistema da malware o altro software potenzialmente indesiderato, ma l'azione non è riuscita. </b>
</td>
</tr>
<tr>
<td>
Descrizione:
</td>
<td >
Antivirus Microsoft Defender si è verificato un errore non critico quando si esegue un'azione su malware o altro software potenzialmente indesiderato.<br/>Per ulteriori informazioni, vedere gli argomenti seguenti:
<dl>
<dt>Nome: &lt; ID &gt; nome</dt>
<dt>minaccia: &lt; Gravità &gt; ID</dt> 
<dt> minaccia: &lt; &gt; Gravità, ad esempio:<ul>
<li>Bassa</li>
<li>Moderato</li>
<li>Fortemente</li>
<li>Grave</li>
</ul>
</dt>
<dt>Categoria: &lt; Descrizione della &gt; categoria, ad esempio qualsiasi tipo di minaccia o malware.</dt> 
<dt>Percorso: &lt; Percorso &gt; file</dt> 
<dt> Origine rilevamento: &lt; origine &gt; rilevamento, ad esempio:
<ul>
<li>Unknown</li>
<li>Computer locale</li>
<li>Condivisione di rete</li>
<li>Internet</li>
<li>Traffico in ingresso</li>
<li>Traffico in uscita</li>
</ul>
</dt>
<dt>Tipo di rilevamento: &lt; tipo di &gt; rilevamento, ad esempio:<ul>
<li>Euristica</li>
<li>Generale</li>
<li>Concrete</li>
<li>Firma dinamica</li>
</ul>
</dt>
<dt>Origine di rilevamento: &lt; origine &gt; di rilevamento, ad esempio:<ul>
<li>Utente: avviato dall'utente</li>
<li>Sistema: sistema avviato</li>
<li>Tempo reale: componente in tempo reale avviato</li>
<li>IOAV: download di Internet Outlook express allegati avviati</li>
<li>NIS: sistema di ispezione della rete</li>
<li>IEPROTECT: IE - IExtensionValidation; ciò protegge dai controlli delle pagine Web dannosi</li>
<li>Antimalware di avvio anticipato (ELAM). Ciò include il malware rilevato dalla sequenza di avvio</li>
<li>Attestazione remota</li>
</ul>Antimalware Scan Interface (AMSI). Usato principalmente per proteggere gli script (PS, VBS), anche se può essere richiamato anche da terze parti.
Utente </dt> 
<dt>UAC: &lt; Dominio &gt; \& lt; User &gt; </dt>
<dt>Process Name: &lt; Process &gt; in the PID</dt> 
<dt> Action: &lt; Action , ad &gt; esempio:<ul>
<li>Clean: la risorsa è stata pulita</li>
<li>Quarantena: la risorsa è stata messi in quarantena</li>
<li>Rimuovi: la risorsa è stata eliminata</li>
<li>Consenti: la risorsa è stata consentita per l'esecuzione/l'esistenza</li>
<li>Definito dall'utente: azione definita dall'utente che in genere è una di queste azioni specificate dall'utente</li>
<li>Nessuna azione: nessuna azione</li>
<li>Blocca: l'esecuzione della risorsa è stata bloccata</li>
</ul>
</dt>
<dt>Stato azione: &lt; Descrizione delle &gt; azioni aggiuntive</dt>
<dt>Codice di errore: Codice di errore &lt; Codice di risultato associato allo stato della &gt; minaccia. Valori HRESULT standard.</dt> 
<dt>Descrizione errore: &lt; Descrizione &gt; dell'errore Descrizione dell'errore.</dt> 
<dt>Versione firma: &lt; Versione &gt; della definizione</dt>
<dt>Versione motore: Antimalware Engine &lt; versione &gt; </dt>
</dl>
</td>
</tr>
<tr>
<td>
Azione utente:
</td>
<td >
Non è necessaria alcuna azione. Antivirus Microsoft Defender non è riuscito a completare un'attività correlata alla correzione del malware. Non si tratta di un errore critico.
</td>
</tr>
<tr>
<th colspan="2">ID evento: 1119</th>
</tr>
<tr><td>
Nome simbolico:
</td>
<td >
<b>MALWAREPROTECTION_STATE_MALWARE_ACTION_CRITICALLY_FAILED </b>
</td>
</tr>
<tr>
<td>
Messaggio:
</td>
<td >
<b>La piattaforma antimalware ha riscontrato un errore critico quando si tenta di intervenire su malware o altro software potenzialmente indesiderato. Nel messaggio dell'evento sono disponibili ulteriori dettagli.</b>
</td>
</tr>
<tr>
<td>
Descrizione:
</td>
<td >
Antivirus Microsoft Defender si è verificato un errore critico durante l'azione su malware o altro software potenzialmente indesiderato.<br/>Per ulteriori informazioni, vedere gli argomenti seguenti:
<dl>
<dt>Nome: &lt; ID &gt; nome</dt>
<dt>minaccia: &lt; Gravità &gt; ID</dt> 
<dt> minaccia: &lt; &gt; Gravità, ad esempio:<ul>
<li>Bassa</li>
<li>Moderato</li>
<li>Fortemente</li>
<li>Grave</li>
</ul>
</dt>
<dt>Categoria: &lt; Descrizione della &gt; categoria, ad esempio qualsiasi tipo di minaccia o malware.</dt> 
<dt>Percorso: &lt; Percorso &gt; file</dt> 
<dt> Origine rilevamento: &lt; origine &gt; rilevamento, ad esempio:
<ul>
<li>Unknown</li>
<li>Computer locale</li>
<li>Condivisione di rete</li>
<li>Internet</li>
<li>Traffico in ingresso</li>
<li>Traffico in uscita</li>
</ul>
</dt>
<dt>Tipo di rilevamento: &lt; tipo di &gt; rilevamento, ad esempio:<ul>
<li>Euristica</li>
<li>Generale</li>
<li>Concrete</li>
<li>Firma dinamica</li>
</ul>
</dt>
<dt>Origine di rilevamento: &lt; origine &gt; di rilevamento, ad esempio:<ul>
<li>Utente: avviato dall'utente</li>
<li>Sistema: sistema avviato</li>
<li>Tempo reale: componente in tempo reale avviato</li>
<li>IOAV: download di Internet Outlook express allegati avviati</li>
<li>NIS: sistema di ispezione della rete</li>
<li>IEPROTECT: IE - IExtensionValidation; ciò protegge dai controlli delle pagine Web dannosi</li>
<li>Antimalware di avvio anticipato (ELAM). Ciò include il malware rilevato dalla sequenza di avvio</li>
<li>Attestazione remota</li>
</ul>Antimalware Scan Interface (AMSI). Usato principalmente per proteggere gli script (PS, VBS), anche se può essere richiamato anche da terze parti.
Utente </dt> 
<dt>UAC: &lt; Dominio &gt; \& lt; User &gt; </dt>
<dt>Process Name: &lt; Process &gt; in the PID</dt> 
<dt> Action: &lt; Action , ad &gt; esempio:<ul>
<li>Clean: la risorsa è stata pulita</li>
<li>Quarantena: la risorsa è stata messi in quarantena</li>
<li>Rimuovi: la risorsa è stata eliminata</li>
<li>Consenti: la risorsa è stata consentita per l'esecuzione/l'esistenza</li>
<li>Definito dall'utente: azione definita dall'utente che in genere è una di queste azioni specificate dall'utente</li>
<li>Nessuna azione: nessuna azione</li>
<li>Blocca: l'esecuzione della risorsa è stata bloccata</li>
</ul>
</dt>
<dt>Stato azione: &lt; Descrizione delle &gt; azioni aggiuntive</dt>
<dt>Codice di errore: Codice di errore &lt; Codice di risultato associato allo stato della &gt; minaccia. Valori HRESULT standard.</dt> 
<dt>Descrizione errore: &lt; Descrizione &gt; dell'errore Descrizione dell'errore.</dt> 
<dt>Versione firma: &lt; Versione &gt; della definizione</dt>
<dt>Versione motore: Antimalware Engine &lt; versione &gt; </dt>
</dl>
</td>
</tr>
<tr>
<td>
Azione utente:
</td>
<td >
Il Antivirus Microsoft Defender client ha riscontrato questo errore a causa di problemi critici. L'endpoint potrebbe non essere protetto. Esamina la descrizione dell'errore e segui i passaggi <b>pertinenti per l'azione dell'utente</b> riportati di seguito.
<table>
<tr>
<th>Azione</th>
<th>Azione utente</th>
</tr>
<tr>
<td>
<b>Rimuovi</b>
</td>
<td>
Aggiornare le definizioni, quindi verificare che la rimozione sia stata eseguita correttamente.
</td>
</tr>
<tr>
<td>
<b>Clean</b>
</td>
<td>
Aggiornare le definizioni, quindi verificare che la correzione sia stata eseguita correttamente.
</td>
</tr>
<tr>
<td>
<b>Quarantena</b>
</td>
<td>
Aggiornare le definizioni e verificare che l'utente sia autorizzato ad accedere alle risorse necessarie.
</td>
</tr>
<tr>
<td>
<b>Consenti</b>
</td>
<td>
Verificare che l'utente sia autorizzato ad accedere alle risorse necessarie.
</td>
</tr>
</table>

Se questo evento persiste:<ol>
<li>Eseguire di nuovo l'analisi.</li>
<li>Se si verifica un errore nello stesso modo, accedere al <b></b> sito del Supporto <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Tecnico Microsoft,</a>immettere il numero di errore nella casella Cerca per cercare il codice di errore.</li>
<li>Contatta il <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Supporto tecnico Microsoft</a>.
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2">ID evento: 1120</th>
</tr>
<tr><td>
Nome simbolico:
</td>
<td >
<b>MALWAREPROTECTION_THREAT_HASH</b>
</td>
</tr>
<tr>
<td>
Messaggio:
</td>
<td >
<b>Antivirus Microsoft Defender ha dedotto gli hash per una risorsa di minaccia.</b>
</td>
</tr>
<tr>
<td>
Descrizione:
</td>
<td >
Antivirus Microsoft Defender client è attivo e in esecuzione in uno stato integro.
<dl>
<dt>Versione piattaforma corrente: &lt; Current platform &gt; version</dt>
<dt>Threat Resource Path: &lt; Path &gt; </dt>
<dt>Hashes: &lt; Hashes &gt; </dt>
</dl>
</td>
</tr>
<tr>
<td></td>
<td >
<div class="alert"><b>Nota: questo evento verrà registrato solo se è impostato il criterio seguente: <b>ThreatFileHashLogging unsigned</b>.</div>
<div> </div>
</td>
</tr>
<tr>
<th colspan="2">ID evento: 1150</th>
</tr>
<tr><td>
Nome simbolico:
</td>
<td >
<b>MALWAREPROTECTION_SERVICE_HEALTHY</b>
</td>
</tr>
<tr>
<td>
Messaggio:
</td>
<td >
<b>Se la piattaforma antimalware segnala lo stato a una piattaforma di monitoraggio, questo evento indica che la piattaforma antimalware è in esecuzione e in uno stato integro. </b>
</td>
</tr>
<tr>
<td>
Descrizione:
</td>
<td >
Antivirus Microsoft Defender client è attivo e in esecuzione in uno stato integro.
<dl>
<dt>Versione piattaforma: &lt; Versione corrente &gt; della piattaforma</dt>
<dt>Versione firma: versione di &lt; definizione &gt; </dt>
<dt>Versione motore: Antimalware Engine &lt; versione &gt; </dt>
</dl>
</td>
</tr>
<tr>
<td>
Azione utente:
</td>
<td >
Non è necessaria alcuna azione. Il Antivirus Microsoft Defender client è in uno stato integro. Questo evento viene segnalato ogni ora.
</td>
</tr>

<tr>
<th colspan="2">ID evento: 1151</th>
</tr>
<tr><td>
Nome simbolico:
</td>
<td >
<b>MALWAREPROTECTION_SERVICE_HEALTH_REPORT</b>
</td>
</tr>
<tr>
<td>
Messaggio:
</td>
<td >
<b>Endpoint Protection stato del client (ora UTC)</b>
</td>
</tr>
<tr>
<td>
Descrizione:
</td>
<td >
Rapporto integrità client antivirus.
<dl>
<dt>Versione piattaforma: &lt; Versione corrente &gt; </dt>della piattaforma Versione
<dt>motore: &lt; Antimalware Engine &gt; </dt>versione Network Realtime Inspection engine
<dt>version: Network &lt; Realtime &gt; Inspection</dt>engine version Antivirus signature
<dt>version: Antivirus signature &lt; version &gt; </dt>
<dt>Antispyware signature version: &lt; Antispyware signature version &gt; </dt>Network
<dt>Realtime Inspection signature version: Network &lt; Realtime Inspection signature version &gt; </dt>
<dt>RTP state: Realtime Stato di protezione (Abilitato o &lt; &gt; Disabilitato)</dt>Stato
<dt>OA: Stato di accesso (Abilitato o &lt; &gt; Disabilitato)</dt>Stato IOAV: Stato IE Download e allegati di Outlook Express (abilitato o
<dt> &lt; &gt; disabilitato):</dt>stato monitoraggio del comportamento (abilitato o
<dt> &lt; &gt; disabilitato)</dt>Validità della firma antivirus: validità della firma antivirus
<dt> &lt; &gt; (in giorni) </dt>Validità firma antispyware: validità firma 
<dt> &lt; antispyware &gt; (in giorni)</dt>Validità ultima analisi rapida: Validità ultima analisi rapida
<dt> &lt; &gt; (in giorni)</dt>Validità ultima analisi completa: Validità ultima analisi completa
<dt> &lt; &gt; (in giorni)</dt>Ora creazione firma
<dt>antivirus: ? &lt; Tempo creazione &gt; firma antivirus</dt>
<dt>Tempo creazione firma Antispyware: ? &lt; Ora creazione firma &gt; antispyware</dt>Ultima ora di avvio
<dt>dell'analisi rapida: ? &lt; Ora ultima inizio &gt; analisi rapida</dt>
<dt>Ultima ora di fine analisi rapida: ? &lt; &gt;</dt>Ora di fine ultima analisi rapida Ultima origine di analisi rapida: Ultima origine di analisi rapida (0&#39;= analisi non eseguita, 1 = avviata dall'utente, 2 = avviata dal
<dt> &lt; &gt; sistema)</dt>Ultima ora di avvio dell'analisi
<dt>completa: ? &lt; Ultima ora di &gt; inizio dell'analisi completa</dt>
<dt>Ultima ora di fine analisi completa: ? &lt; Ora &gt; </dt>di fine ultima analisi completa Ultima origine analisi completa: Ultima origine analisi completa (0&#39;= analisi non eseguita, 1 = avviata dall'utente, 2 = avviata dal
<dt> &lt; &gt; sistema)</dt>Stato del prodotto: per la risoluzione dei problemi 
<dt> interni
</dl>
</td>
</tr>

<tr>
<th colspan="2">ID evento: 2000</th>
</tr>
<tr><td>
Nome simbolico:
</td>
<td >
<b>MALWAREPROTECTION_SIGNATURE_UPDATED </b>
</td>
</tr>
<tr>
<td>
Messaggio:
</td>
<td >
<b>Le definizioni antimalware sono state aggiornate correttamente. </b>
</td>
</tr>
<tr>
<td>
Descrizione:
</td>
<td >
La versione della firma antivirus è stata aggiornata.
<dl>
<dt>Versione firma corrente: &lt; Versione firma &gt; corrente</dt>
<dt>Versione firma precedente: versione firma &lt; precedente &gt; </dt>Tipo di 
<dt> firma: Tipo di &lt; &gt; firma, ad esempio: <ul>
<li>Antivirus</li>
<li>Antispyware</li>
<li>Antimalware</li>
<li>Network Inspection System</li>
</ul>
</dt>
<dt>Tipo di aggiornamento: &lt; Tipo di &gt; aggiornamento , Completo o Delta.</dt> 
<dt>Utente: &lt; Dominio &gt; \& lt; User &gt; </dt>
<dt>Current Engine Version: &lt; Current engine version &gt; </dt>Previous Engine
<dt>Version: Previous engine &lt; version &gt; </dt>
</dl>
</td>
</tr>
<tr>
<td>
Azione utente:
</td>
<td >
Non è necessaria alcuna azione. Il Antivirus Microsoft Defender client è in uno stato integro. Questo evento viene segnalato quando le firme vengono aggiornate correttamente.
</td>
</tr>
<tr>
<th colspan="2">ID evento: 2001</th>
</tr>
<tr><td>
Nome simbolico:
</td>
<td >
<b>MALWAREPROTECTION_SIGNATURE_UPDATE_FAILED</b>
</td>
</tr>
<tr>
<td>
Messaggio:
</td>
<td >
<b>L'aggiornamento della sicurezza intelligence non è riuscito. </b>
</td>
</tr>
<tr>
<td>
Descrizione:
</td>
<td >
Antivirus Microsoft Defender si è verificato un errore durante il tentativo di aggiornare le firme.
<dl>
<dt>Nuova versione di security intelligence: &lt; Nuovo numero &gt; di versione</dt>
<dt>Versione intelligence di sicurezza precedente: Versione &lt; precedente &gt; </dt> 
<dt> Origine aggiornamento: Origine &lt; &gt; aggiornamento, ad esempio:
<ul>
<li>Cartella di aggiornamento delle funzionalità di intelligence per la sicurezza</li>
<li>Server di aggiornamento intelligence per la sicurezza interna</li>
<li>Microsoft Update Server</li>
<li>Condivisione file</li>
<li>Microsoft Malware Protection Center (MMPC)</li>
</ul>
</dt>
<dt>Fase di aggiornamento: &lt; fase di &gt; aggiornamento, ad esempio:
<ul>
<li>Ricerca</li>
<li>Scarica</li>
<li>Installare</li>
</ul>
</dt>
<dt>Source Path: File share name for Universal Naming Convention (UNC), server name for Windows Server Update Services (WSUS)/Microsoft Update/ADL.</dt> 
<dt> Tipo di firma: &lt; Tipo di &gt; firma, ad esempio: <ul>
<li>Antivirus</li>
<li>Antispyware</li>
<li>Antimalware</li>
<li>Network Inspection System</li>
</ul>
</dt>
<dt>Tipo di aggiornamento: &lt; Tipo di &gt; aggiornamento , Completo o Delta.</dt> 
<dt>Utente: &lt; Dominio &gt; \& lt; User &gt; </dt>
<dt>Current Engine Version: &lt; Current engine version &gt; </dt>Previous Engine
<dt>Version: Previous engine &lt; &gt; version</dt>Error
<dt>Code: Error code Result code associated &lt; with threat &gt; status. Valori HRESULT standard.</dt> 
<dt>Descrizione errore: &lt; Descrizione &gt; dell'errore Descrizione dell'errore.</dt>
</dl>
</td>
</tr>
<tr>
<td>
Azione utente:
</td>
<td >
Questo errore si verifica quando si verifica un problema durante l'aggiornamento delle definizioni.
Per risolvere i problemi relativi a questo evento:
<ol>
<li><a href="manage-updates-baselines-microsoft-defender-antivirus.md" data-raw-source="[Update definitions](manage-updates-baselines-microsoft-defender-antivirus.md)">Aggiornare le definizioni</a> e forzare una nuova analisi direttamente nell'endpoint.</li>
<li>Esaminare le voci nel file %Windir%\WindowsUpdate.log per ulteriori informazioni su questo errore.</li>
<li>Contatta il <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Supporto tecnico Microsoft</a>.
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2">ID evento: 2002</th>
</tr>
<tr><td>
Nome simbolico:
</td>
<td >
<b>MALWAREPROTECTION_ENGINE_UPDATED</b>
</td>
</tr>
<tr>
<td>
Messaggio:
</td>
<td >
<b>Il motore antimalware è stato aggiornato correttamente. </b>
</td>
</tr>
<tr>
<td>
Descrizione:
</td>
<td >
Antivirus Microsoft Defender versione del motore è stata aggiornata.
<dl>
<dt>Versione motore corrente: &lt; Versione corrente &gt; del motore</dt>Versione motore
<dt>precedente: &lt; &gt; Versione</dt>precedente motore Tipo di motore: Tipo di motore, motore
<dt> &lt; antimalware o motore di Network Inspection &gt; System.</dt> 
<dt>Utente: &lt; Dominio &gt; \& lt; Utente &gt; </dt>
</dl>
</td>
</tr>
<tr>
<td>
Azione utente:
</td>
<td >
Non è necessaria alcuna azione. Il Antivirus Microsoft Defender client è in uno stato integro. Questo evento viene segnalato quando il motore antimalware viene aggiornato correttamente.
</td>
</tr>
<tr>
<th colspan="2">ID evento: 2003</th>
</tr>
<tr><td>
Nome simbolico:
</td>
<td >
<b>MALWAREPROTECTION_ENGINE_UPDATE_FAILED</b>
</td>
</tr>
<tr>
<td>
Messaggio:
</td>
<td >
<b>Aggiornamento del motore antimalware non riuscito. </b>
</td>
</tr>
<tr>
<td>
Descrizione:
</td>
<td >
Antivirus Microsoft Defender si è verificato un errore durante il tentativo di aggiornare il motore.
<dl>
<dt>Nuova versione del motore:</dt>versione precedente
<dt>del motore: &lt; &gt; versione</dt>precedente Tipo di motore: Tipo di motore, motore
<dt>antimalware o motore del sistema di ispezione di &lt; &gt; rete.</dt> 
<dt>Utente: &lt; Dominio &gt; \& lt; User &gt; </dt>
<dt>Error Code: &lt; Codice di errore Codice di risultato associato allo stato della &gt; minaccia. Valori HRESULT standard.</dt> 
<dt>Descrizione errore: &lt; Descrizione &gt; dell'errore Descrizione dell'errore.</dt>
</dl>
</td>
</tr>
<tr>
<td>
Azione utente:
</td>
<td >
L'Antivirus Microsoft Defender client non è riuscito. Questo evento si verifica quando il client non riesce ad aggiornarsi. Questo evento è in genere dovuto a un'interruzione della connettività di rete durante un aggiornamento.
Per risolvere i problemi relativi a questo evento:
<ol>
<li><a href="manage-updates-baselines-microsoft-defender-antivirus.md" data-raw-source="[Update definitions](manage-updates-baselines-microsoft-defender-antivirus.md)">Aggiornare le definizioni</a> e forzare una nuova analisi direttamente nell'endpoint.</li>
<li>Contatta il <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Supporto tecnico Microsoft</a>.
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2">ID evento: 2004</th>
</tr>
<tr><td>
Nome simbolico:
</td>
<td >
<b>MALWAREPROTECTION_SIGNATURE_REVERSION</b>
</td>
</tr>
<tr>
<td>
Messaggio:
</td>
<td >
<b>Si è verificato un problema durante il caricamento delle definizioni antimalware. Il motore antimalware tenterà di caricare l'ultimo set di definizioni valido noto.</b>
</td>
</tr>
<tr>
<td>
Descrizione:
</td>
<td >
Antivirus Microsoft Defender si è verificato un errore durante il tentativo di caricare le firme e tenterà di ripristinare un set di firme valido.
<dl>
<dt>Firme tentate:</dt>
<dt>Codice di errore: codice di errore Codice di risultato associato allo stato della &lt; &gt; minaccia. Valori HRESULT standard.</dt> 
<dt>Descrizione errore: &lt; Descrizione &gt; dell'errore Descrizione dell'errore.</dt> 
<dt>Versione firma: &lt; Versione &gt; della definizione</dt>
<dt>Versione motore: versione &lt; &gt; del motore antimalware</dt>
</dl>
</td>
</tr>
<tr>
<td>
Azione utente:
</td>
<td >
Il Antivirus Microsoft Defender ha tentato di scaricare e installare il file di definizioni più recente e non è riuscito. Questo errore può verificarsi quando il client rileva un errore durante il tentativo di caricamento delle definizioni o se il file è danneggiato. Antivirus Microsoft Defender tenterà di ripristinare un set di definizioni noto.
Per risolvere i problemi relativi a questo evento:
<ol>
<li>Riavviare il computer e riprovare.</li>
<li>Scaricare le definizioni più recenti <a href="https://aka.ms/wdsi">dal sito Intelligence di sicurezza Microsoft .</a>
Nota: le dimensioni del file di definizioni scaricato dal sito possono superare i 60 MB e non devono essere utilizzate come soluzione a lungo termine per l'aggiornamento delle definizioni.
</li>
<li>Contatta il <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Supporto tecnico Microsoft</a>.
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2">ID evento: 2005</th>
</tr>
<tr><td>
Nome simbolico:
</td>
<td >
<b>MALWAREPROTECTION_ENGINE_UPDATE_PLATFORMOUTOFDATE</b>
</td>
</tr>
<tr>
<td>
Messaggio:
</td>
<td >
<b>Impossibile caricare il motore antimalware perché la piattaforma antimalware non è aggiornata. La piattaforma antimalware carica l'ultimo motore antimalware valido noto e tenta di aggiornarsi.</b>
</td>
</tr>
<tr>
<td>
Descrizione:
</td>
<td >
Antivirus Microsoft Defender non è stato possibile caricare il motore antimalware perché la versione corrente della piattaforma non è supportata. Antivirus Microsoft Defender verrà ripristinato l'ultimo motore noto e verrà eseguito un tentativo di aggiornamento della piattaforma.
<dl>
<dt>Versione corrente della piattaforma: &lt; versione corrente della piattaforma&gt;</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">ID evento: 2006</th>
</tr>
<tr><td>
Nome simbolico:
</td>
<td >
<b>MALWAREPROTECTION_PLATFORM_UPDATE_FAILED </b>
</td>
</tr>
<tr>
<td>
Messaggio:
</td>
<td >
<b>Aggiornamento della piattaforma non riuscito. </b>
</td>
</tr>
<tr>
<td>
Descrizione:
</td>
<td >
Antivirus Microsoft Defender si è verificato un errore durante il tentativo di aggiornare la piattaforma.
<dl>
<dt>Versione piattaforma corrente: &lt; Versione corrente &gt; della piattaforma</dt>
<dt>Codice di errore: codice di errore &lt; Codice di risultato associato allo stato della &gt; minaccia. Valori HRESULT standard.</dt> 
<dt>Descrizione errore: &lt; Descrizione &gt; dell'errore Descrizione dell'errore.</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">ID evento: 2007</th>
</tr>
<tr><td>
Nome simbolico:
</td>
<td >
<b>MALWAREPROTECTION_PLATFORM_ALMOSTOUTOFDATE</b>
</td>
</tr>
<tr>
<td>
Messaggio:
</td>
<td >
<b>La piattaforma sarà presto non aggiornata. Scarica la piattaforma più recente per mantenere una protezione aggiornata.</b>
</td>
</tr>
<tr>
<td>
Descrizione:
</td>
<td >
Antivirus Microsoft Defender presto sarà necessaria una versione della piattaforma più recente per supportare le versioni future del motore antimalware. Scarica la piattaforma Antivirus Microsoft Defender più recente per mantenere il miglior livello di protezione disponibile.
<dl>
<dt>Versione corrente della piattaforma: &lt; versione corrente della piattaforma&gt;</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">ID evento: 2010</th>
</tr>
<tr><td>
Nome simbolico:
</td>
<td >
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_UPDATED </b>
</td>
</tr>
<tr>
<td>
Messaggio:
</td>
<td >
<b>Il motore antimalware ha utilizzato il servizio di firma dinamico per ottenere ulteriori definizioni. </b>
</td>
</tr>
<tr>
<td>
Descrizione:
</td>
<td >
Antivirus Microsoft Defender <i>utilizzato dynamic signature service</i> per recuperare firme aggiuntive per proteggere il computer.
<dl>
<dt>Versione firma corrente: &lt; Versione firma &gt; corrente</dt> 
<dt> Tipo di firma: Tipo di &lt; &gt; firma, ad esempio: <ul>
<li>Antivirus</li>
<li>Antispyware</li>
<li>Antimalware</li>
<li>Network Inspection System</li>
</ul>
</dt>
<dt>Versione motore corrente: &lt; Versione motore &gt; corrente</dt> 
<dt> Tipo di firma dinamica: tipo di firma &lt; &gt; dinamica, ad esempio:
<ul>
<li>Version</li>
<li>Timestamp</li>
<li>Nessun limite</li>
<li>Durata</li>
</ul>
</dt>
<dt>Percorso di persistenza: &lt; Path &gt; </dt>
<dt>Dynamic Signature Version: &lt; Version &gt; number</dt>Dynamic Signature Compilation
<dt>Timestamp: &lt; Timestamp &gt; </dt>Persistence Limit 
<dt> Type: Persistence limit type , ad &lt; &gt; esempio:
<ul>
<li>Versione VDM</li>
<li>Timestamp</li>
<li>Nessun limite</li>
</ul>
</dt>
<dt>Limite di persistenza: limite di persistenza della firma fastpath.</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">ID evento: 2011</th>
</tr>
<tr><td>
Nome simbolico:
</td>
<td >
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_DELETED </b>
</td>
</tr>
<tr>
<td>
Messaggio:
</td>
<td >
<b>Il servizio di firma dinamica ha eliminato le definizioni dinamiche non aggiornate. </b>
</td>
</tr>
<tr>
<td>
Descrizione:
</td>
<td >
Antivirus Microsoft Defender il <i>servizio di firma dinamico per</i> eliminare le firme obsolete.
<dl>
<dt>Versione firma corrente: &lt; Versione firma &gt; corrente</dt> 
<dt> Tipo di firma: Tipo di &lt; &gt; firma, ad esempio: <ul>
<li>Antivirus</li>
<li>Antispyware</li>
<li>Antimalware</li>
<li>Network Inspection System</li>
</ul>
</dt>
<dt>Versione motore corrente: &lt; Versione motore &gt; corrente</dt> 
<dt> Tipo di firma dinamica: tipo di firma &lt; &gt; dinamica, ad esempio:
<ul>
<li>Version</li>
<li>Timestamp</li>
<li>Nessun limite</li>
<li>Durata</li>
</ul>
</dt>
<dt>Percorso di persistenza: &lt; Path &gt; </dt>
<dt>Dynamic Signature Version: &lt; Version &gt; number</dt>Dynamic Signature Compilation
<dt>Timestamp: &lt; Timestamp &gt; </dt>Removal
<dt>Reason:</dt> 
<dt> Persistence Limit Type: Persistence limit type , ad &lt; &gt; esempio:
<ul>
<li>Versione VDM</li>
<li>Timestamp</li>
<li>Nessun limite</li>
</ul>
</dt>
<dt>Limite di persistenza: limite di persistenza della firma fastpath.</dt>
</dl>
</td>
</tr>
<tr>
<td>
Azione utente:
</td>
<td >
Non è necessaria alcuna azione. Il Antivirus Microsoft Defender client è in uno stato integro. Questo evento viene segnalato quando il servizio di firma dinamica elimina correttamente le definizioni dinamiche non aggiornate.
</td>
</tr>
<tr>
<th colspan="2">ID evento: 2012</th>
</tr>
<tr><td>
Nome simbolico:
</td>
<td >
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_UPDATE_FAILED </b>
</td>
</tr>
<tr>
<td>
Messaggio:
</td>
<td >
<b>Il motore antimalware ha riscontrato un errore durante il tentativo di utilizzare il servizio di firma dinamico. </b>
</td>
</tr>
<tr>
<td>
Descrizione:
</td>
<td >
Antivirus Microsoft Defender si è verificato un errore durante il tentativo di utilizzo <i>del servizio di firma dinamico.</i>
<dl>
<dt>Versione firma corrente: &lt; Versione firma &gt; corrente</dt> 
<dt> Tipo di firma: Tipo di &lt; &gt; firma, ad esempio: <ul>
<li>Antivirus</li>
<li>Antispyware</li>
<li>Antimalware</li>
<li>Network Inspection System</li>
</ul>
</dt>
<dt>Versione motore corrente: &lt; Versione corrente &gt; del motore</dt>
<dt>Codice di errore: codice di errore &lt; Codice di risultato associato allo stato della &gt; minaccia. Valori HRESULT standard.</dt> 
<dt>Descrizione errore: &lt; Descrizione &gt; dell'errore Descrizione dell'errore.</dt> 
<dt> Tipo di firma dinamica: &lt; tipo di firma &gt; dinamico, ad esempio:
<ul>
<li>Version</li>
<li>Timestamp</li>
<li>Nessun limite</li>
<li>Durata</li>
</ul>
</dt>
<dt>Percorso di persistenza: &lt; Path &gt; </dt>
<dt>Dynamic Signature Version: &lt; Version &gt; number</dt>Dynamic Signature Compilation
<dt>Timestamp: &lt; Timestamp &gt; </dt>Persistence Limit 
<dt> Type: Persistence limit type , ad &lt; &gt; esempio:
<ul>
<li>Versione VDM</li>
<li>Timestamp</li>
<li>Nessun limite</li>
</ul>
</dt>
<dt>Limite di persistenza: limite di persistenza della firma fastpath.</dt>
</dl>
</td>
</tr>
<tr>
<td>
Azione utente:
</td>
<td >
Controllare le impostazioni di connettività Internet.
</td>
</tr>
<tr>
<th colspan="2">ID evento: 2013</th>
</tr>
<tr><td>
Nome simbolico:
</td>
<td >
<b>MALWAREPROTECTION_SIGNATURE_FASTPATH_DELETED_ALL </b>
</td>
</tr>
<tr>
<td>
Messaggio:
</td>
<td >
<b>Il servizio di firma dinamica ha eliminato tutte le definizioni dinamiche. </b>
</td>
</tr>
<tr>
<td>
Descrizione:
</td>
<td >
Antivirus Microsoft Defender tutte le firme <i>del servizio di firma</i> dinamica.
<dl>
<dt>Versione firma corrente: &lt; versione della firma corrente&gt;</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">ID evento: 2020</th>
</tr>
<tr><td>
Nome simbolico:
</td>
<td >
<b>MALWAREPROTECTION_CLOUD_CLEAN_RESTORE_FILE_DOWNLOADED </b>
</td>
</tr>
<tr>
<td>
Messaggio:
</td>
<td >
<b>Il motore antimalware ha scaricato un file pulito. </b>
</td>
</tr>
<tr>
<td>
Descrizione:
</td>
<td >
Antivirus Microsoft Defender scaricato un file pulito.
<dl>
<dt>Nome file: &lt; Nome file &gt; Nome del file.</dt> 
<dt>Versione firma corrente: &lt; Versione firma &gt; corrente</dt>
<dt>Versione motore corrente: versione corrente del &lt; motore &gt; </dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">ID evento: 2021</th>
</tr>
<tr><td>
Nome simbolico:
</td>
<td >
<b>MALWAREPROTECTION_CLOUD_CLEAN_RESTORE_FILE_DOWNLOAD_FAILED</b>
</td>
</tr>
<tr>
<td>
Messaggio:
</td>
<td >
<b>Il motore antimalware non è riuscito a scaricare un file pulito. </b>
</td>
</tr>
<tr>
<td>
Descrizione:
</td>
<td >
Antivirus Microsoft Defender si è verificato un errore durante il tentativo di scaricare un file pulito.
<dl>
<dt>Nome file: &lt; Nome file &gt; Nome del file.</dt> 
<dt>Versione firma corrente: &lt; Versione firma &gt; corrente</dt>
<dt>Versione motore corrente: versione &lt; &gt; corrente del motore</dt>Codice di errore: codice di errore Codice di errore Codice di risultato associato allo stato della
<dt> &lt; &gt; minaccia. Valori HRESULT standard.</dt> 
<dt>Descrizione errore: &lt; Descrizione &gt; dell'errore Descrizione dell'errore.</dt>
</dl>
</td>
</tr>
<tr>
<td>
Azione utente:
</td>
<td >
Controllare le impostazioni di connettività Internet.
Il client Antivirus Microsoft Defender ha riscontrato un errore quando si utilizza il servizio di firma dinamico per scaricare le definizioni più recenti in una minaccia specifica. Questo errore è probabilmente causato da un problema di connettività di rete. 
</td>
</tr>
<tr>
<th colspan="2">ID evento: 2030</th>
</tr>
<tr><td>
Nome simbolico:
</td>
<td >
<b>MALWAREPROTECTION_OFFLINE_SCAN_INSTALLED</b>
</td>
</tr>
<tr>
<td>
Messaggio:
</td>
<td >
<b>Il motore antimalware è stato scaricato ed è configurato per l'esecuzione offline al successivo riavvio del sistema.</b>
</td>
</tr>
<tr>
<td>
Descrizione:
</td>
<td >
Antivirus Microsoft Defender antivirus offline scaricato e configurato per l'esecuzione al riavvio successivo.
</td>
</tr>
<tr>
<th colspan="2">ID evento: 2031</th>
</tr>
<tr><td>
Nome simbolico:
</td>
<td >
<b>MALWAREPROTECTION_OFFLINE_SCAN_INSTALL_FAILED </b>
</td>
</tr>
<tr>
<td>
Messaggio:
</td>
<td >
<b>Il motore antimalware non è stato in grado di scaricare e configurare un'analisi offline.</b>
</td>
</tr>
<tr>
<td>
Descrizione:
</td>
<td >
Antivirus Microsoft Defender si è verificato un errore durante il tentativo di scaricare e configurare l'antivirus offline.
<dl>
<dt>Codice errore: &lt; Codice di errore &gt; Codice di risultato associato allo stato della minaccia. Valori HRESULT standard.</dt> 
<dt>Descrizione errore: &lt; Descrizione &gt; dell'errore Descrizione dell'errore.</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">ID evento: 2040</th>
</tr>
<tr><td>
Nome simbolico:
</td>
<td >
<b>MALWAREPROTECTION_OS_EXPIRING </b>
</td>
</tr>
<tr>
<td>
Messaggio:
</td>
<td >
<b>Il supporto antimalware per questa versione del sistema operativo terminerà presto. </b>
</td>
</tr>
<tr>
<td>
Descrizione:
</td>
<td >
Il supporto per il sistema operativo scadrà a breve. L'Antivirus Microsoft Defender in un sistema operativo fuori supporto non è una soluzione adeguata per la protezione dalle minacce.
</td>
</tr>
<tr>
<th colspan="2">ID evento: 2041</th>
</tr>
<tr><td>
Nome simbolico:
</td>
<td >
<b>MALWAREPROTECTION_OS_EOL </b>
</td>
</tr>
<tr>
<td>
Messaggio:
</td>
<td >
<b>Il supporto antimalware per questo sistema operativo è terminato. È necessario aggiornare il sistema operativo per continuare a supportare. </b>
</td>
</tr>
<tr>
<td>
Descrizione:
</td>
<td >
Il supporto per il sistema operativo è scaduto. L'Antivirus Microsoft Defender in un sistema operativo fuori supporto non è una soluzione adeguata per la protezione dalle minacce.
</td>
</tr>
<tr>
<th colspan="2">ID evento: 2042</th>
</tr>
<tr><td>
Nome simbolico:
</td>
<td >
<b>MALWAREPROTECTION_PROTECTION_EOL </b>
</td>
</tr>
<tr>
<td>
Messaggio:
</td>
<td >
<b>Il motore antimalware non supporta più questo sistema operativo e non protegge più il sistema da malware. </b>
</td>
</tr>
<tr>
<td>
Descrizione:
</td>
<td >
Il supporto per il sistema operativo è scaduto. Antivirus Microsoft Defender non è più supportato nel sistema operativo, ha smesso di funzionare e non protegge dalle minacce malware.
</td>
</tr>
<tr>
<th colspan="2">ID evento: 3002</th>
</tr>
<tr><td>
Nome simbolico:
</td>
<td >
<b>MALWAREPROTECTION_RTP_FEATURE_FAILURE </b>
</td>
</tr>
<tr>
<td>
Messaggio:
</td>
<td >
<b>La protezione in tempo reale ha riscontrato un errore e non è riuscita.</b>
</td>
</tr>
<tr>
<td>
Descrizione:
</td>
<td >
Antivirus Microsoft Defender Real-Time funzionalità di protezione ha riscontrato un errore e non è riuscita.
<dl>
<dt>Funzionalità: &lt; funzionalità , ad &gt; esempio:
<ul>
<li>On Access</li>
<li>Download di Internet Explorer e allegati di Microsoft Outlook Express</li>
<li>Monitoraggio del comportamento</li>
<li>Network Inspection System</li>
</ul>
</dt>
<dt>Codice errore: &lt; Codice di errore &gt; Codice di risultato associato allo stato della minaccia. Valori HRESULT standard.</dt> 
<dt>Descrizione errore: &lt; Descrizione &gt; dell'errore Descrizione dell'errore.</dt> 
<dt>Motivo: il motivo Antivirus Microsoft Defender protezione in tempo reale ha riavviato una funzionalità.</dt>
</dl>
</td>
</tr>
<tr>
<td>
Azione utente:
</td>
<td >
È consigliabile riavviare il sistema e quindi eseguire un'analisi completa&#39;possibile che il sistema non sia stato protetto per un certo periodo di tempo.
Il Antivirus Microsoft Defender client&#39;funzionalità di protezione in tempo reale ha riscontrato un errore perché non è stato possibile avviare uno dei servizi. Se è seguito da un ID evento 3007, l'errore è stato temporaneo e il client antimalware è stato ripristinato dall'errore. 
</td>
</tr>
<tr>
<th colspan="2">ID evento: 3007</th>
</tr>
<tr><td>
Nome simbolico:
</td>
<td >
<b>MALWAREPROTECTION_RTP_FEATURE_RECOVERED</b>
</td>
</tr>
<tr>
<td>
Messaggio:
</td>
<td >
<b>Protezione in tempo reale recuperata da un errore. È consigliabile eseguire un'analisi completa del sistema quando viene visualizzato questo errore. </b>
</td>
</tr>
<tr>
<td>
Descrizione:
</td>
<td >
Antivirus Microsoft Defender Protezione in tempo reale ha riavviato una funzionalità. È consigliabile eseguire un'analisi completa del sistema per rilevare eventuali elementi che potrebbero essere stati persi mentre l'agente non era in esecuzione.
<dl>
<dt>Funzionalità: &lt; funzionalità , ad &gt; esempio:
<ul>
<li>On Access</li>
<li>Download di IE e allegati Outlook Express</li>
<li>Monitoraggio del comportamento</li>
<li>Network Inspection System</li>
</ul>
</dt>
<dt>Motivo: il motivo Antivirus Microsoft Defender protezione in tempo reale ha riavviato una funzionalità.</dt>
</dl>
</td>
</tr>
<tr>
<td>
Azione utente:
</td>
<td >
La funzionalità di protezione in tempo reale è stata riavviata. Se questo evento si verifica di nuovo, contattare il <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Supporto tecnico Microsoft.</a> 
</td>
</tr>
<tr>
<th colspan="2">ID evento: 5000</th>
</tr>
<tr><td>
Nome simbolico:
</td>
<td >
<b>MALWAREPROTECTION_RTP_ENABLED </b>
</td>
</tr>
<tr>
<td>
Messaggio:
</td>
<td >
<b>La protezione in tempo reale è abilitata. </b>
</td>
</tr>
<tr>
<td>
Descrizione:
</td>
<td >
Antivirus Microsoft Defender l'analisi della protezione in tempo reale per malware e altro software potenzialmente indesiderato è stato abilitato.
</td>
</tr>
<tr>
<th colspan="2">ID evento: 5001</th>
</tr>
<tr><td>
Nome simbolico:
</td>
<td >
<b>MALWAREPROTECTION_RTP_DISABLED</b>
</td>
</tr>
<tr>
<td>
Messaggio:
</td>
<td >
<b>La protezione in tempo reale è disabilitata. </b>
</td>
</tr>
<tr>
<td>
Descrizione:
</td>
<td >
Antivirus Microsoft Defender'analisi della protezione in tempo reale per malware e altro software potenzialmente indesiderato è stato disabilitato. 
</td>
</tr>
<tr>
<th colspan="2">ID evento: 5004</th>
</tr>
<tr><td>
Nome simbolico:
</td>
<td >
<b>MALWAREPROTECTION_RTP_FEATURE_CONFIGURED </b>
</td>
</tr>
<tr>
<td>
Messaggio:
</td>
<td >
<b>La configurazione della protezione in tempo reale è cambiata. </b>
</td>
</tr>
<tr>
<td>
Descrizione:
</td>
<td >
Antivirus Microsoft Defender configurazione delle funzionalità di protezione in tempo reale è cambiata.
<dl>
<dt>Funzionalità: &lt; funzionalità , ad &gt; esempio:
<ul>
<li>On Access</li>
<li>Download di IE e allegati Outlook Express</li>
<li>Monitoraggio del comportamento</li>
<li>Network Inspection System</li>
</ul>
</dt>
<dt>Configurazione: </dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">ID evento: 5007</th>
</tr>
<tr><td>
Nome simbolico:
</td>
<td >
<b>MALWAREPROTECTION_CONFIG_CHANGED </b>
</td>
</tr>
<tr>
<td>
Messaggio:
</td>
<td >
<b>La configurazione della piattaforma antimalware è cambiata.</b>
</td>
</tr>
<tr>
<td>
Descrizione:
</td>
<td >
Antivirus Microsoft Defender configurazione è cambiata. Se si tratta di un evento imprevisto, è consigliabile esaminare le impostazioni perché questo potrebbe essere il risultato di malware.
<dl>
<dt>Valore precedente: &lt; Old value number &gt; Vecchio valore di configurazione antivirus.</dt> 
<dt>Nuovo valore: &lt; Nuovo numero di valore &gt; Nuovo valore di configurazione antivirus.</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">ID evento: 5008</th>
</tr>
<tr><td>
Nome simbolico:
</td>
<td >
<b>MALWAREPROTECTION_ENGINE_FAILURE</b>
</td>
</tr>
<tr>
<td>
Messaggio:
</td>
<td >
<b>Il motore antimalware ha rilevato un errore e non è riuscito.</b>
</td>
</tr>
<tr>
<td>
Descrizione:
</td>
<td >
Antivirus Microsoft Defender motore è stato terminato a causa di un errore imprevisto.
<dl>
<dt>Tipo errore: &lt; Tipo di &gt; errore, ad esempio: Codice di eccezione di arresto</dt>anomalo o
<dt>blocco: codice di &lt; &gt; errore</dt>
<dt>Risorsa: &lt; risorsa &gt; </dt>
</dl>
</td>
</tr>
<tr>
<td>
Azione utente:
</td>
<td >
Per risolvere i problemi relativi a questo evento:<ol>
<li>Provare a riavviare il servizio.<ul>
<li>Per antimalware, antivirus e spyware, al prompt dei comandi con privilegi elevati digitare <b>net stop msmpsvc</b>e quindi digitare <b>net start msmpsvc</b> per riavviare il motore antimalware.</li>
<li>Per <i>Network Inspection System</i>, al prompt dei comandi con privilegi elevati digitare <b>net start nissrv</b>e quindi <b>digitare net start nissrv</b> per riavviare il motore <i>di Network Inspection System</i> utilizzando il file NiSSRV.exe.
</li>
</ul>
</li>
<li>Se non riesce nello stesso modo, cercare il codice di errore accedendo al <b></b> sito di supporto <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Microsoft</a> e immettendo il numero di errore nella casella di ricerca e contattare il Supporto tecnico <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Microsoft.</a></li>
</ol>
</td>
</tr>
<tr>
<td>
Azione utente:
</td>
<td >
Il Antivirus Microsoft Defender client è stato arrestato a causa di un errore imprevisto.
Per risolvere i problemi relativi a questo evento:
<ol>
<li>Eseguire di nuovo l'analisi.</li>
<li>Se si verifica un errore nello stesso modo, accedere al <b></b> sito del Supporto <a href="https://go.microsoft.com/fwlink/?LinkId=215163">Tecnico Microsoft,</a>immettere il numero di errore nella casella Cerca per cercare il codice di errore.</li>
<li>Contatta il <a href="https://go.microsoft.com/fwlink/?LinkId=215491">Supporto tecnico Microsoft</a>.
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2">ID evento: 5009</th>
</tr>
<tr><td>
Nome simbolico:
</td>
<td >
<b>MALWAREPROTECTION_ANTISPYWARE_ENABLED </b>
</td>
</tr>
<tr>
<td>
Messaggio:
</td>
<td >
<b>La ricerca di malware e altro software potenzialmente indesiderato è abilitata. </b>
</td>
</tr>
<tr>
<td>
Descrizione:
</td>
<td >
Antivirus Microsoft Defender è stata abilitata la ricerca di malware e altro software potenzialmente indesiderato.
</td>
</tr>
<tr>
<th colspan="2">ID evento: 5010</th>
</tr>
<tr><td>
Nome simbolico:
</td>
<td >
<b>MALWAREPROTECTION_ANTISPYWARE_DISABLED </b>
</td>
</tr>
<tr>
<td>
Messaggio:
</td>
<td >
<b>La ricerca di malware e altro software potenzialmente indesiderato è disabilitata.</b>
</td>
</tr>
<tr>
<td>
Descrizione:
</td>
<td >
Antivirus Microsoft Defender la ricerca di malware e altro software potenzialmente indesiderato è disabilitata.
</td>
</tr>
<tr>
<th colspan="2">ID evento: 5011</th>
</tr>
<tr><td>
Nome simbolico:
</td>
<td >
<b>MALWAREPROTECTION_ANTIVIRUS_ENABLED</b>
</td>
</tr>
<tr>
<td>
Messaggio:
</td>
<td >
<b>La ricerca di virus è abilitata.</b>
</td>
</tr>
<tr>
<td>
Descrizione:
</td>
<td >
Antivirus Microsoft Defender la ricerca di virus è stata abilitata. 
</td>
</tr>
<tr>
<th colspan="2">ID evento: 5012</th>
</tr>
<tr><td>
Nome simbolico:
</td>
<td >
<b>MALWAREPROTECTION_ANTIVIRUS_DISABLED </b>
</td>
</tr>
<tr>
<td>
Messaggio:
</td>
<td >
<b>L'analisi dei virus è disabilitata. </b>
</td>
</tr>
<tr>
<td>
Descrizione:
</td>
<td >
Antivirus Microsoft Defender la ricerca di virus è disabilitata. 
</td>
</tr>
<tr>
<th colspan="2">ID evento: 5100</th>
</tr>
<tr><td>
Nome simbolico:
</td>
<td >
<b>MALWAREPROTECTION_EXPIRATION_WARNING_STATE </b>
</td>
</tr>
<tr>
<td>
Messaggio:
</td>
<td >
<b>La piattaforma antimalware scadrà a breve. </b>
</td>
</tr>
<tr>
<td>
Descrizione:
</td>
<td >
Antivirus Microsoft Defender è stato immesso un periodo di tolleranza e scadrà a breve. Dopo la scadenza, questo programma disabiliterà la protezione da virus, spyware e altro software potenzialmente indesiderato.
<dl>
<dt>Motivo scadenza: motivo Antivirus Microsoft Defender scadenza.</dt> 
<dt>Data di scadenza: la data Antivirus Microsoft Defender scadrà.</dt>
</dl>
</td>
</tr>
<tr>
<th colspan="2">ID evento: 5101</th>
</tr>
<tr><td>
Nome simbolico:
</td>
<td >
<b>MALWAREPROTECTION_DISABLED_EXPIRED_STATE </b>
</td>
</tr>
<tr>
<td>
Messaggio:
</td>
<td >
<b>La piattaforma antimalware è scaduta. </b>
</td>
</tr>
<tr>
<td>
Descrizione:
</td>
<td >
Antivirus Microsoft Defender periodo di tolleranza è scaduto. La protezione da virus, spyware e altro software potenzialmente indesiderato è disabilitata.
<dl>
<dt>Motivo scadenza:</dt>
<dt>data di scadenza: </dt>codice di 
<dt>errore: codice di errore Codice di &lt; risultato associato allo stato della &gt; minaccia. Valori HRESULT standard.</dt> 
<dt>Descrizione errore: &lt; Descrizione &gt; dell'errore Descrizione dell'errore.</dt>
</dl>
</td>
</tr>
</table>

<a id="error-codes"></a>
##Antivirus Microsoft Defender codici di errore client Se Antivirus Microsoft Defender si verificano problemi, in genere verrà visualizzato un codice di errore che consente di risolvere il problema. Molto spesso un errore indica che si è verificato un problema durante l'installazione di un aggiornamento.
In questa sezione vengono fornite le informazioni seguenti sugli errori Antivirus Microsoft Defender client.
-   Il codice di -   errore Il possibile motivo dell'errore Consigli su cosa fare -   ora

Utilizzare le informazioni contenute in queste tabelle per risolvere i Antivirus Microsoft Defender di errore.


<table> 
<tr>
<th colspan="2">Codice di errore: 0x80508007</th>
</tr>
<tr>
<td>Messaggio</td>
<td>
<b>ERR_MP_NO_MEMORY </b>
</td>
</tr>
<tr>
<td>
Motivo possibile
</td>
<td>
Questo errore indica che la memoria potrebbe essere insufficiente. 
</td>
</tr>
<tr>
<td>Risoluzione</td>
<td>
<ol>
<li>Controlla la memoria disponibile nel dispositivo.</li>
<li>Chiudi tutte le applicazioni inutilizzate in esecuzione per liberare memoria nel dispositivo.</li>
<li>Riavviare il dispositivo ed eseguire di nuovo l'analisi. 
</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2">Codice di errore: 0x8050800C</th>
</tr><tr><td>Messaggio</td>
<td><b>ERR_MP_BAD_INPUT_DATA</b>
</td></tr><tr><td>Motivo possibile</td>
<td>
Questo errore indica che potrebbe verificarsi un problema con il prodotto di sicurezza.
</td>
</tr><tr><td>Risoluzione</td><td>
<ol>
<li>Aggiornare le definizioni. Uno dei seguenti:<ol>
<li>Fare clic <b>sul pulsante Aggiorna</b> definizioni nella <b>scheda</b> Aggiornamento in Antivirus Microsoft Defender. <img src="images/defender-updatedefs2.png" alt="Update definitions in Microsoft Defender Antivirus"/>Oppure
</li>
<li>Scaricare le definizioni più recenti <a href="https://aka.ms/wdsi">dal sito Intelligence di sicurezza Microsoft .</a>
Nota: le dimensioni del file di definizioni scaricato dal sito possono superare i 60 MB e non devono essere utilizzate come soluzione a lungo termine per l'aggiornamento delle definizioni.
</li>
</ol>
</li>
<li>Eseguire un'analisi completa.
</li>
<li>Riavviare il dispositivo e riprovare.</li>
</ol>
</td>
</tr>
<tr>
<th colspan="2">Codice di errore: 0x80508020</th>
</tr><tr><td>Messaggio</td>
<td><b>ERR_MP_BAD_CONFIGURATION </b>
</td></tr><tr><td>Motivo possibile</td>
<td>
Questo errore indica che potrebbe esserci un errore di configurazione del motore. In genere, ciò è correlato ai dati di input che non consentono al motore di funzionare correttamente. 
</td>
</tr>
<tr>
<th colspan="2">Codice di errore: 0x805080211
</th>
</tr><tr><td>Messaggio</td>
<td><b>ERR_MP_QUARANTINE_FAILED </b>
</td></tr><tr><td>Motivo possibile</td>
<td>
Questo errore indica che non è Antivirus Microsoft Defender mettere in quarantena una minaccia. 
</td>
</tr>
<tr>
<th colspan="2">Codice di errore: 0x80508022
</th>
</tr><tr><td>Messaggio</td>
<td><b>ERR_MP_REBOOT_REQUIRED </b>
</td></tr><tr><td>Motivo possibile</td>
<td>
Questo errore indica che è necessario un riavvio per completare la rimozione delle minacce. 
</td>
</tr>
<tr>
<th colspan="2">
0x80508023
</th>
</tr><tr><td>Messaggio</td>
<td><b>ERR_MP_THREAT_NOT_FOUND </b>
</td></tr><tr><td>Motivo possibile</td>
<td>
Questo errore indica che la minaccia potrebbe non essere più presente nel supporto o che il malware potrebbe impedirti di analizzare il dispositivo. 
</tr><tr><td>Risoluzione
</td>
<td>
Eseguire il <a href="https://www.microsoft.com/security/scanner/default.aspx">Microsoft Safety Scanner</a> quindi aggiornare il software di sicurezza e riprovare. 
</td>
</tr>
<tr>
<th colspan="2">Codice di errore: 0x80508024 </th></tr>
<tr>
<td>Messaggio</td>
<td><b>ERR_MP_FULL_SCAN_REQUIRED </b>
</td></tr><tr><td>Motivo possibile</td>
<td>
Questo errore indica che potrebbe essere necessaria un'analisi completa del sistema. 
</td></tr>
<tr>
<td>Risoluzione</td><td>
Eseguire un'analisi completa del sistema. 
</td>
</tr>
<tr>
<th colspan="2">Codice di errore: 0x80508025
</th>
</tr><tr><td>Messaggio</td>
<td><b>ERR_MP_MANUAL_STEPS_REQUIRED </b>
</td></tr><tr><td>Motivo possibile</td>
<td>
Questo errore indica che sono necessari passaggi manuali per completare la rimozione delle minacce. 
</td></tr><tr><td>Risoluzione</td><td>
Seguire la procedura di correzione manuale descritta <a href="https://www.microsoft.com/security/portal/threat/Threats.aspx">nell'enciclopedia Microsoft Malware Protection.</a> È possibile trovare un collegamento specifico per le minacce nella cronologia degli eventi.<br/></td>
</tr>
<tr>
<th colspan="2">Codice di errore: 0x80508026
</th>
</tr><tr><td>Messaggio</td>
<td><b>ERR_MP_REMOVE_NOT_SUPPORTED </b>
</td></tr><tr><td>Motivo possibile</td>
<td>
Questo errore indica che la rimozione all'interno del tipo di contenitore potrebbe non essere supportata. 
</td></tr><tr><td>Risoluzione</td><td>
Antivirus Microsoft Defender non è in grado di correggere le minacce rilevate all'interno dell'archivio. Prendere in considerazione la rimozione manuale delle risorse rilevate. 
</td>
</tr>
<tr>
<th colspan="2">Codice di errore: 0x80508027
</th>
</tr><tr><td>Messaggio</td>
<td><b>ERR_MP_REMOVE_LOW_MEDIUM_DISABLED </b>
</td></tr><tr><td>Motivo possibile</td>
<td>
Questo errore indica che la rimozione delle minacce di medie e medie dimensioni potrebbe essere disabilitata. 
</td></tr><tr><td>Risoluzione</td><td>
Controllare le minacce rilevate e risolverle in base alle esigenze. 
</td>
</tr>
<tr>
<th colspan="2">Codice di errore: 0x80508029
</th>
</tr><tr><td>Messaggio</td>
<td><b>ERROR_MP_RESCAN_REQUIRED </b>
</td></tr><tr><td>Motivo possibile</td>
<td>
Questo errore indica che è necessaria una nuova analisi della minaccia. 
</td></tr><tr><td>Risoluzione</td><td>
Eseguire un'analisi completa del sistema. 
</td>
</tr>
<tr>
<th colspan="2">Codice di errore: 0x80508030
</th>
</tr><tr><td>Messaggio</td>
<td><b>ERROR_MP_CALLISTO_REQUIRED </b>
</td></tr><tr><td>Motivo possibile</td>
<td>
Questo errore indica che è necessaria un'analisi offline. 
</td></tr><tr><td>Risoluzione</td><td>
Esegui offline Antivirus Microsoft Defender. Per informazioni su come eseguire questa operazione, vedere <a href="https://windows.microsoft.com/windows/what-is-windows-defender-offline">l'articolo offline Antivirus Microsoft Defender .</a>
</td>
</tr>
<tr>
<th colspan="2">Codice di errore: 0x80508031
</th>
</tr><tr><td>Messaggio</td>
<td><b>ERROR_MP_PLATFORM_OUTDATED<br/></b>
</td></tr><tr><td>Motivo possibile</td>
<td>
Questo errore indica che Antivirus Microsoft Defender non supporta la versione corrente della piattaforma e richiede una nuova versione della piattaforma. 
</td></tr><tr><td>Risoluzione</td><td>
È possibile utilizzare solo Antivirus Microsoft Defender in Windows 10. Ad Windows 8, Windows 7 e Windows Vista, è possibile utilizzare <a href="https://www.microsoft.com/server-cloud/system-center/endpoint-protection-2012.aspx">System Center Endpoint Protection</a>.<br/></td>
</tr>
</table>

<a id="internal-error-codes"></a>I codici di errore seguenti vengono utilizzati durante i test interni di Antivirus Microsoft Defender.

Se vengono visualizzati questi errori, puoi provare ad [aggiornare](manage-updates-baselines-microsoft-defender-antivirus.md) le definizioni e forzare una nuova analisi direttamente nell'endpoint.


<table> 
<tr>
<th colspan="3">Codici di errore interni</th>
</tr>
<tr>
<th><b>Codice di errore</b></th>
<th>Messaggio visualizzato</th>
<th>Possibile motivo dell'errore e della risoluzione</th>
</tr>
<tr>
<td>
0x80501004
</td>
<td>
<b>ERROR_MP_NO_INTERNET_CONN </b>
</td>
<td>
Controllare la connessione Internet, quindi eseguire di nuovo l'analisi.
</td>
</tr>
<tr>
<td>
0x80501000
</td>
<td>
<b>ERROR_MP_UI_CONSOLIDATION_BAS</b> E
</td>
<td rowspan="34">
Si tratta di un errore interno. La causa non è chiaramente definita.
</td>
<td rowspan="36">

</td>
</tr>
<tr>
<td>
0x80501001
</td>
<td>
<b>ERROR_MP_ACTIONS_FAILED</b>
</td>
</tr>
<tr>
<td>
0x80501002
</td>
<td>
<b>ERROR_MP_NOENGINE</b>
</td>
</tr>
<tr>
<td>
0x80501003
</td>
<td>
<b>ERROR_MP_ACTIVE_THREATS</b>
</td>
</tr>
<tr>
<td>
0x805011011
</td>
<td>
<b>MP_ERROR_CODE_LUA_CANCELLED </b>
</td>
</tr>
<tr>
<td>
0x80501101
</td>
<td>
<b>ERROR_LUA_CANCELLATION </b>
</td>
</tr>
<tr>
<td>
0x80501102
</td>
<td>
<b>MP_ERROR_CODE_ALREADY_SHUTDOWN</b>
</td>
</tr>
<tr>
<td>
0x80501103
</td>
<td>
<b>MP_ERROR_CODE_RDEVICE_S_ASYNC_CALL_PENDING </b>
</td>
</tr>
<tr>
<td>
0x80501104
</td>
<td>
<b>MP_ERROR_CODE_CANCELLED</b>
</td>
</tr>
<tr>
<td>
0x80501105
</td>
<td>
<b>MP_ERROR_CODE_NO_TARGETOS</b>
</td>
</tr>
<tr>
<td>
0x80501106
</td>
<td>
<b>MP_ERROR_CODE_BAD_REGEXP</b>
</td>
</tr>
<tr>
<td>
0x80501107
</td>
<td>
<b>MP_ERROR_TEST_INDUCED_ERROR</b>
</td>
</tr>
<tr>
<td>
0x80501108
</td>
<td>
<b>MP_ERROR_SIG_BACKUP_DISABLED</b>
</td>
</tr>
<tr>
<td>
0x80508001
</td>
<td>
<b>ERR_MP_BAD_INIT_MODULES</b>
</td>
</tr>
<tr>
<td>
0x80508002
</td>
<td>
<b>ERR_MP_BAD_DATABASE</b>
</td>
</tr>
<tr>
<td>
0x80508004
</td>
<td>
<b>ERR_MP_BAD_UFS </b>
</td>
</tr>
<tr>
<td>
0x8050800C
</td>
<td>
<b>ERR_MP_BAD_INPUT_DATA</b>
</td>
</tr>
<tr>
<td>
0x8050800D
</td>
<td>
<b>ERR_MP_BAD_GLOBAL_STORAGE</b>
</td>
</tr>
<tr>
<td>
0x8050800E
</td>
<td>
<b>ERR_MP_OBSOLETE</b>
</td>
</tr>
<tr>
<td>
0x8050800F
</td>
<td>
<b>ERR_MP_NOT_SUPPORTED</b>
</td>
</tr>
<tr>
<td>
0x8050800F 0x80508010
</td>
<td>
<b>ERR_MP_NO_MORE_ITEMS </b>
</td>
</tr>
<tr>
<td>
0x80508011
</td>
<td>
<b>ERR_MP_DUPLICATE_SCANID</b>
</td>
</tr>
<tr>
<td>
0x80508012
</td>
<td>
<b>ERR_MP_BAD_SCANID</b>
</td>
</tr>
<tr>
<td>
0x80508013
</td>
<td>
<b>ERR_MP_BAD_USERDB_VERSION</b>
</td>
</tr>
<tr>
<td>
0x80508014
</td>
<td>
<b>ERR_MP_RESTORE_FAILED</b>
</td>
</tr>
<tr>
<td>
0x80508016
</td>
<td>
<b>ERR_MP_BAD_ACTION</b>
</td>
</tr>
<tr>
<td>
0x80508019
</td>
<td>
<b>ERR_MP_NOT_FOUND</b>
</td>
</tr>
<tr>
<td>
0x80509001
</td>
<td>
<b>ERR_RELO_BAD_EHANDLE</b>
</td>
</tr>
<tr>
<td>
0x80509003
</td>
<td>
<b>ERR_RELO_KERNEL_NOT_LOADED</b>
</td>
</tr>
<tr>
<td>
0x8050A001
</td>
<td>
<b>ERR_MP_BADDB_OPEN</b>
</td>
</tr>
<tr>
<td>
0x8050A002
</td>
<td>
<b>ERR_MP_BADDB_HEADER</b>
</td>
</tr>
<tr>
<td>
0x8050A003
</td>
<td>
<b>ERR_MP_BADDB_OLDENGINE</b>
</td>
</tr>
<tr>
<td>
0x8050A004
</td>
<td>
<b>ERR_MP_BADDB_CONTENT </b>
</td>
</tr>
<tr>
<td>
0x8050A005
</td>
<td>
<b>ERR_MP_BADDB_NOTSIGNED</b>
</td>
</tr>
<tr>
<td>
0x8050801
</td>
<td>
<b>ERR_MP_REMOVE_FAILED</b>
</td>
<td>
Si tratta di un errore interno. Potrebbe essere attivato quando la rimozione malware non riesce. 
</td>
</tr>
<tr>
<td>
0x80508018
</td>
<td>
<b>ERR_MP_SCAN_ABORTED </b>
</td>
<td>
Si tratta di un errore interno. Potrebbe essere stato attivato quando un'analisi non viene completata. 
</td>
</tr>
</table>

## <a name="related-topics"></a>Argomenti correlati

- [Report sulla Antivirus Microsoft Defender protezione](report-monitor-microsoft-defender-antivirus.md)
- [Antivirus Microsoft Defender in Windows 10](microsoft-defender-antivirus-in-windows-10.md)