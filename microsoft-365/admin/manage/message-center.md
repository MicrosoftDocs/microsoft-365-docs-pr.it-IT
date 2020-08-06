---
title: Centro messaggi
f1.keywords:
- CSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 38fb3333-bfcc-4340-a37b-deda509c2093
description: Ottenere una panoramica del centro messaggi di Microsoft 365 e del relativo ruolo nella gestione delle modifiche.
ms.openlocfilehash: cec60a7ae5df1af01625f8feef84ff258d798659
ms.sourcegitcommit: 48f3c002678906189bfba079bbf055d67d08a60f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2020
ms.locfileid: "46564026"
---
# <a name="message-center"></a>Centro messaggi


Per tenere conto delle modifiche imminenti, incluse le funzionalità nuove e modificate, la manutenzione pianificata o altri annunci importanti, visitare il <a href="https://go.microsoft.com/fwlink/p/?linkid=2070717" target="_blank">centro messaggi</a>. 
  
Per aprire il centro messaggi:

::: moniker range="o365-worldwide"

- Nell'interfaccia di amministrazione, accedere a **Health** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2070717" target="_blank">centro messaggi</a>di integrità.

::: moniker-end

::: moniker range="o365-germany"

- Nell'interfaccia di <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Amministrazione</a>, accedere a **Health** > **centro messaggi**di integrità.

::: moniker-end

::: moniker range="o365-21vianet"
 
- Nell'interfaccia di <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Amministrazione</a>, accedere a **Health** > **centro messaggi**di integrità.

::: moniker-end

È inoltre possibile utilizzare l' [app Microsoft 365 admin](https://go.microsoft.com/fwlink/p/?linkid=627216) sul dispositivo mobile per visualizzare il centro messaggi, che è un ottimo modo per rimanere aggiornati con le notifiche push. 
  
  
### <a name="frequently-asked-questions"></a>Domande frequenti

|**Domanda**|**Risposta**|
|:-----|:-----|
|Chi può visualizzare i post nel Centro messaggi?  <br/> |La maggior parte degli utenti a cui è stato assegnato un ruolo di amministratore in Microsoft 365 può visualizzare i post del centro messaggi. Di [seguito è indicato un elenco](#admin-roles-that-dont-have-access-to-the-message-center) dei ruoli di amministratore che non dispongono dell'accesso al centro messaggi. È inoltre possibile assegnare il ruolo lettore centro messaggi agli utenti che devono essere in grado di leggere e condividere i post del centro messaggi senza avere altri privilegi di amministratore.<br/>|
|Questo è l'unico modo in cui Microsoft comunica le modifiche apportate a Microsoft 365?  <br/> |No, ma il centro messaggi è il modo principale in cui si comunica la tempistica delle singole modifiche in Microsoft 365. Per informazioni sulle risorse aggiuntive, vedere [Stay on top of Microsoft 365 changes](stay-on-top-of-updates.md) .  <br/> |
|Come si visualizzano i post in una lingua specifica?  <br/> |I post del centro messaggi sono scritti solo in inglese, ma è possibile controllare se, per impostazione predefinita, i post vengono visualizzati in inglese oppure vengono convertiti automaticamente nella lingua preferita. È anche possibile scegliere di tradurre i post in una lingua supportata. Per ulteriori informazioni, vedere [Traduzione in lingua per i post del centro messaggi](language-translation-for-message-center-posts.md) .  <br/> |
|È possibile ottenere un'anteprima delle modifiche o delle caratteristiche prima che vengano distribuite nell'organizzazione?  <br/> |È possibile visualizzare in anteprima alcune modifiche e nuove funzionalità optando per il programma di rilascio di destinazione. Per scegliere l'opzione, nell' **interfaccia di amministrazione, accedere a**  >  Preferenze di rilascio del**profilo dell'organizzazione**  >  **Release preferences**. (Nell'interfaccia di amministrazione, potrebbe essere necessario selezionare **Mostra tutto** nella parte inferiore del riquadro di spostamento a sinistra per visualizzare **le impostazioni**). È possibile scegliere la versione di destinazione per l'intera organizzazione o solo per gli utenti selezionati. Per ulteriori informazioni sul programma, vedere [Opzioni di rilascio standard o mirate in Microsoft 365](release-options-in-office-365.md) .  <br/> |
|È possibile individuare la data esatta in cui una modifica verrà resa disponibile a un'organizzazione?  <br/> |Purtroppo, non è possibile indicare la data esatta in cui verrà apportata una modifica all'organizzazione. Nel post del Centro messaggi vengono fornite tutte le informazioni disponibili al momento del rilascio, in base al livello di probabilità. Stiamo lavorando su miglioramenti per migliorare il livello di dettaglio.  <br/> |
|I messaggi sono specifici per l'organizzazione di ogni utente?  <br/> |Microsoft si impegna al massimo perché a ogni utente vengano visualizzati solo i post del Centro messaggi che interessano la sua organizzazione. La roadmap di Microsoft 365 include tutte le funzionalità attualmente in fase di elaborazione e di implementazione, ma non tutte queste funzionalità sono valide per ogni organizzazione. <br/> |
|È possibile ottenere messaggi al centro messaggi tramite posta elettronica?  <br/> |Sì! È possibile selezionare un digest settimanale inviato tramite posta elettronica e fino a altri due indirizzi di posta elettronica. Il digest settimanale inviato tramite posta elettronica è attivato per impostazione predefinita. Se non si ricevono i digest settimanali, controllare la cartella posta indesiderata. Per ulteriori informazioni su come configurare il digest settimanale, vedere la sezione [Preferenze](#preferences) di questo articolo.  <br/> |
|Come si interrompe l'ottenimento del digest del centro messaggi?  <br/> |Accedere a centro messaggi nell'interfaccia di amministrazione e selezionare **Modifica preferenze**. Disattivare l'opzione per **inviare un digest settimanale dei messaggi di posta elettronica**. Se non si desidera più ricevere messaggi di posta elettronica sugli aggiornamenti più importanti, disattivare **Inviami le email per gli aggiornamenti principali**.  <br/> |
|Come è possibile garantire che le notifiche relative alla privacy dei dati siano ricevute dai contatti giusti nell'organizzazione? <br/> |Come amministratore globale, verranno ricevuti i messaggi sulla privacy dei dati per l'organizzazione. Inoltre, è possibile assegnare il ruolo di lettore di privacy del centro messaggi alle persone che dovrebbero visualizzare i messaggi sulla privacy dei dati. Altri ruoli di amministratore con accesso al centro messaggi non sono in grado di visualizzare i messaggi sulla privacy dei dati.   <br/><br/>Per altre informazioni, vedere [Preferenze](#preferences) in questo articolo.<br/> |

### <a name="messages"></a>Messaggi

Centro messaggi presenta una visualizzazione di tutti i messaggi attivi in un formato di tabella. Per impostazione predefinita, viene visualizzato il messaggio più recente all'inizio dell'elenco. È possibile selezionare una scheda per visualizzare **tutti**i messaggi attivi, i messaggi di **priorità alta** , i messaggi non **letti**e **i messaggi ignorati**. È possibile utilizzare il menu a discesa **filtro** per visualizzare tutti i messaggi in una categoria di messaggi specifica.

Di seguito viene illustrata una breve panoramica delle informazioni visualizzate in ogni colonna. Selezionare una delle intestazioni di colonna per modificare l'ordinamento.
  
|**Colonna**|**Descrizione**|
|:-----|:-----|
|Segno di spunta  <br/> |Se si seleziona il segno di spunta nella riga di intestazione di colonna, verranno selezionati tutti i messaggi attualmente visualizzati. Se si seleziona il segno di spunta accanto a uno o più messaggi, è possibile eseguire l'azione su tali messaggi.  <br/> |
|Icona applicazione <br/> |Le icone indicano l'applicazione a cui si applica il messaggio.<br/> |
|Titolo messaggio  <br/> |I titoli dei messaggi sono una breve descrizione delle modifiche imminenti. Se il titolo completo non viene visualizzato, passa il puntatore del mouse su di esso e l'intero titolo viene visualizzato in una finestra popup.  <br/> |
|Altre opzioni <br/> |Altre opzioni consentono di ignorare un messaggio, contrassegnarlo come letto o da leggere oppure condividerlo con un altro amministratore. Per ripristinare un messaggio respinto, selezionare la scheda **messaggi ignorati** , selezionare il segno di spunta accanto al messaggio e selezionare **Ripristina**. <br/> |
|Aggiornamento principale <br/> |Un punto esclamativo in questa colonna indica un aggiornamento importante. <br/> |
|Intervento entro  <br/> |Qui verranno specificate solo le date se Microsoft intende apportare una modifica che richiede l'intervento dell'utente entro una certa data di scadenza. Poiché raramente si utilizza la colonna **Act by** , se viene visualizzato qualcosa, è necessario prestare particolare attenzione.  <br/> |
|Category  <br/> | I messaggi vengono identificati da una delle tre categorie seguenti: <br/><br/> **Prevenire o risolvere i problemi**: informa l'utente dei problemi noti che interessano l'organizzazione e potrebbe richiedere di intervenire per evitare interruzioni del servizio. I messaggi di tipo Prevenire o risolvere problemi sono diversi da quelli di tipo Integrità dei servizi, in quanto richiedono che l'utente sia proattivo per evitare problemi. <br/> <br/> **Pianificare la modifica**: informa le modifiche apportate a Microsoft 365 che possono richiedere l'intervento per evitare interruzioni del servizio. Ad esempio, verranno comunicate le modifiche apportate ai requisiti di sistema o le caratteristiche in fase di rimozione. Per assicurare la normale operatività del servizio, Microsoft fornisce almeno 30 giorni di preavviso per ogni modifica che richiede l'intervento di un amministratore. <br/> <br/> **Rimanere informati**: informazioni sulle funzionalità nuove o aggiornate che si stanno attivando nell'organizzazione. Le funzionalità vengono in genere annunciate per prime nella [Roadmap di Microsoft 365](https://go.microsoft.com/fwlink/?linkid=2070821). <br/><br/>Può anche informare sulla manutenzione pianificata in conformità con il contratto di servizio. La manutenzione pianificata può causare un tempo di inattività, in cui l'utente o gli utenti non possono accedere a Microsoft 365, a una funzionalità specifica o a un servizio, ad esempio la posta elettronica o OneDrive for business.  <br/> |
|Ultimo aggiornamento  <br/> |Data in cui il messaggio è stato pubblicato o ultimo aggiornamento.  <br/> |
|ID messaggio  <br/> |Microsoft tiene traccia dei post del Centro messaggi in base agli ID messaggio. È possibile fare riferimento a questo ID se si desidera inviare commenti e suggerimenti oppure se si chiama il supporto per un messaggio specifico.  <br/> |

Per altre informazioni sulle operazioni che è possibile eseguire con i messaggi, vedere [Gestire i messaggi nel Centro messaggi](manage-messages.md).
  
### <a name="major-updates"></a>Aggiornamenti principali

È possibile rivedere gli aggiornamenti principali selezionando la scheda priorità **alta** nella parte superiore del centro messaggi.

Gli aggiornamenti principali vengono comunicati con almeno 30 giorni di anticipo quando è necessaria un'azione e possono includere:
  
- Modifiche alla produttività giornaliera, ad esempio posta in arrivo, riunioni, delegazioni, condivisione e accesso

- Modifiche apportate a temi, Web part e altri componenti che possono influire sulle caratteristiche personalizzate

- Aumenta o diminuisce la capacità visibile, ad esempio l'archiviazione, il numero di regole, gli elementi o le durate

- Modifiche apportate al branding del prodotto che può:

  - Causa della confusione degli utenti finali

  - Consente di apportare modifiche ai processi di supporto tecnico e ai materiali di riferimento, oppure

  - Modificare un URL

- Nuovo servizio o applicazione

- Modifiche che richiedono un'azione di amministratore (in esclusiva per evitare o risolvere i problemi)

- Modifiche alla posizione in cui sono archiviati i dati
  
### <a name="preferences"></a>Preferenze

Se l'amministrazione è distribuita all'interno dell'organizzazione, è possibile che non si desideri o che sia necessario visualizzare i post su tutti i servizi di Microsoft 365. Ogni amministratore può:

- Impostare le preferenze che controllano i messaggi visualizzati nel centro messaggi.
- Filtrare i messaggi
- Impostare le preferenze di posta elettronica per ricevere un digest settimanale di tutti i messaggi, le e-mail solo per gli aggiornamenti più importanti e i messaggi di posta elettronica per la privacy dei dati.  

::: moniker range="o365-worldwide"

1. Selezionare **Modifica preferenze** nella parte superiore del centro messaggi.

2. Verificare che sia selezionata la casella di controllo per ogni servizio che si desidera monitorare. Deselezionare le caselle di controllo relative ai servizi che si desidera escludere dalla visualizzazione centro messaggi.

3. I messaggi di posta elettronica del digest sono attivati per impostazione predefinita e vengono inviati all'indirizzo di posta elettronica principale. Per interrompere la ricezione del digest settimanale, deselezionare la casella **di controllo Invia un messaggio di posta elettronica settimanale dei messaggi personali** . <br/><br/>La notifica tramite posta elettronica per gli aggiornamenti principali è un controllo separato. Se si desidera ricevere notifiche di posta elettronica sugli aggiornamenti principali, verificare che sia selezionata l'opzione **Invia messaggi di posta elettronica per gli aggiornamenti principali** . Deselezionare la casella di controllo per evitare di ricevere posta elettronica sugli aggiornamenti principali. <br><br/>Selezionare la casella di controllo accanto a **Inviami** messaggi di posta elettronica per la privacy dei dati per ricevere notifiche di posta elettronica separate per i messaggi di privacy dei dati (i messaggi sulla privacy dei dati non sono inclusi nel digest settimanale). <br><br/>È possibile selezionare o deselezionare l'indirizzo di posta elettronica principale, ma non è possibile modificarlo. Per specificare gli altri indirizzi di posta elettronica a cui viene inviato il messaggio di posta elettronica per la privacy dei dati, selezionare la casella di controllo **altri indirizzi** di posta elettronica e immettere gli altri indirizzi di posta elettronica in cui si desidera inviare la posta elettronica. Immettere l'indirizzo di posta elettronica di un gruppo di Microsoft 365 o di una lista di distribuzione se più di due persone devono ottenere la posta elettronica sulla privacy dei dati.

4. Selezionare **Salva** per mantenere le modifiche.
  
::: moniker-end 

::: moniker range="o365-germany"

1. Selezionare **modifica le preferenze del centro messaggi** nella parte superiore del centro messaggi.

2. Assicurarsi che il tasto di alternanza sia impostato su **Sì** per ogni servizio che si vuole monitorare. Per modificare l'impostazione su **Disattiva** per i servizi che si desidera escludere dalla visualizzazione centro messaggi, utilizzare l'interruttore.

3. I messaggi di posta elettronica del digest sono attivati per impostazione predefinita e vengono inviati all'indirizzo di posta elettronica principale. Per interrompere la ricezione del digest settimanale, modificare l'impostazione **Invia un digest settimanale di messaggi personali** su **disattivata**. <br/><br/>La notifica tramite posta elettronica per gli aggiornamenti principali è un controllo separato. Se si desidera ricevere notifiche di posta elettronica sugli aggiornamenti principali, verificare che **i messaggi di posta elettronica inviati per gli aggiornamenti principali** siano **attivati**. Modificare l'impostazione su **disattivata** per interrompere l'invio di posta elettronica sugli aggiornamenti principali. <br/><br/>Per ricevere le notifiche di posta elettronica sui messaggi relativi alla privacy dei dati, verificare che i messaggi di posta elettronica **inviati per la privacy dei dati** siano **attivati**. Per interrompere la ricezione di tali notifiche, modificare l'impostazione su **disattivato**. I messaggi sulla privacy dei dati non sono inclusi nel digest settimanale.<br/><br/>È possibile selezionare o deselezionare l'indirizzo di posta elettronica principale, ma non è possibile modificarlo. Per specificare gli altri indirizzi di posta elettronica a **cui viene inviato**il riepilogo settimanale della posta elettronica, verificare che l' **invio di un digest settimanale dei messaggi** sia attivato. Immettere l'indirizzo di posta elettronica di un gruppo di Microsoft 365 o di una lista di distribuzione se più di due persone devono ottenere la posta elettronica del digest.

4. Selezionare **Salva** per mantenere le modifiche.<br/>

::: moniker-end

::: moniker range="o365-21vianet"

1. Selezionare **modifica le preferenze del centro messaggi** nella parte superiore del centro messaggi.

2. Assicurarsi che il tasto di alternanza sia impostato su **Sì** per ogni servizio che si vuole monitorare. Per modificare l'impostazione su **Disattiva** per i servizi che si desidera escludere dalla visualizzazione centro messaggi, utilizzare l'interruttore.

3. I messaggi di posta elettronica del digest sono attivati per impostazione predefinita e vengono inviati all'indirizzo di posta elettronica principale. Per interrompere la ricezione del digest settimanale, modificare l'impostazione **Invia un digest settimanale di messaggi personali** su **disattivata**. <br/><br/>La notifica tramite posta elettronica per gli aggiornamenti principali è un controllo separato. Se si desidera ricevere notifiche di posta elettronica sugli aggiornamenti principali, verificare che **i messaggi di posta elettronica inviati per gli aggiornamenti principali** siano **attivati**. Modificare l'impostazione su **disattivata** per interrompere l'invio di posta elettronica sugli aggiornamenti principali. <br/><br/>Per ricevere le notifiche di posta elettronica sui messaggi relativi alla privacy dei dati, verificare che i messaggi di posta elettronica **inviati per la privacy dei dati** siano **attivati**. Per interrompere la ricezione di tali notifiche, modificare l'impostazione su **disattivato**. I messaggi sulla privacy dei dati non sono inclusi nel digest settimanale.<br/><br/>È possibile selezionare o deselezionare l'indirizzo di posta elettronica principale, ma non è possibile modificarlo. Per specificare gli altri indirizzi di posta elettronica a **cui viene inviato**il riepilogo settimanale della posta elettronica, verificare che l' **invio di un digest settimanale dei messaggi** sia attivato. Immettere l'indirizzo di posta elettronica di un gruppo di Microsoft 365 o di una lista di distribuzione se più di due persone devono ottenere la posta elettronica del digest.

4. Selezionare **Salva** per mantenere le modifiche.<br/>

::: moniker-end

#### <a name="display-messages-in-your-preferred-language"></a>Visualizzazione dei messaggi nella lingua preferita
  
Viene utilizzata la traduzione automatica per visualizzare automaticamente i messaggi nella lingua preferita. Leggere la [Traduzione in lingua per i post del centro messaggi](language-translation-for-message-center-posts.md) per ulteriori informazioni su come impostare la lingua.
  
> [!NOTE]
> Il digest settimanale e qualsiasi post inviato tramite posta elettronica vengono inviati solo in inglese. I destinatari possono utilizzare [Translator per Outlook](https://support.microsoft.com/office/3d7e12ed-99d6-406e-a453-b9db0d9653fa) per leggere il messaggio nella loro lingua preferita. 
  
### <a name="admin-roles-that-dont-have-access-to-the-message-center"></a>Ruoli di amministratore che non dispongono dell'accesso al centro messaggi

- Amministratore di conformità
- Amministratore dell'accesso condizionale
- Responsabile approvazione accesso protetto dei clienti
- Amministratori di dispositivi
- Lettori di directory
- Account di sincronizzazione della directory
- Ruoli con autorizzazioni di scrittura nella directory
- Amministratore del servizio Intune
- Amministratore dei ruoli con privilegi
- Ruolo con autorizzazioni di lettura per i report

## <a name="unsubscribe-from-message-center-emails"></a>Annullamento della sottoscrizione ai messaggi di posta elettronica del centro messaggistica

1. I messaggi di posta elettronica del digest sono attivati per impostazione predefinita e vengono inviati all'indirizzo di posta elettronica principale. Per interrompere la ricezione del digest settimanale, modificare l'impostazione **Invia un digest settimanale di messaggi personali** su **disattivata**. <br/><br/>La notifica tramite posta elettronica per gli aggiornamenti principali è un controllo separato. Se non si desidera ricevere notifiche di posta elettronica sugli aggiornamenti importanti, verificare che l'opzione **Invia messaggi di posta elettronica per gli aggiornamenti importanti** sia **disattivata**.  <br/><br/>Per interrompere la ricezione di notifiche di posta elettronica sui messaggi relativi alla privacy dei dati, verificare che i messaggi **di posta elettronica inviati per la privacy dei dati** siano **spenti**.  I messaggi sulla privacy dei dati non sono inclusi nel digest settimanale.<br/><br/>

2. Selezionare **Salva** per mantenere le modifiche.<br/>