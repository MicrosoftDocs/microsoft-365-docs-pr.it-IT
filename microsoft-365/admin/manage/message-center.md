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
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 38fb3333-bfcc-4340-a37b-deda509c2093
description: Panoramica del Centro messaggi di Microsoft 365 e del suo ruolo nella gestione delle modifiche.
ms.openlocfilehash: 58dec5676e7f2fd0ef590761dfa1e745cbb6814d
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926367"
---
# <a name="message-center"></a>Centro messaggi


Per tenere traccia delle modifiche imminenti, incluse funzionalità nuove e modificate, manutenzione pianificata o altri annunci importanti, passare al <a href="https://go.microsoft.com/fwlink/p/?linkid=2070717" target="_blank">Centro messaggi.</a> 
  
Per aprire il Centro messaggi:

::: moniker range="o365-worldwide"

- Nell'interfaccia di amministrazione passare a **Centro** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2070717" target="_blank">messaggi integrità.</a>

::: moniker-end

::: moniker range="o365-germany"

- <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Nell'interfaccia di amministrazione</a>passare a **Centro** > **messaggi integrità.**

::: moniker-end

::: moniker range="o365-21vianet"
 
- <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Nell'interfaccia di amministrazione</a>passare a **Centro** > **messaggi integrità.**

::: moniker-end

È anche possibile usare l'app Amministratore di [Microsoft 365](https://go.microsoft.com/fwlink/p/?linkid=627216) nel dispositivo mobile per visualizzare il Centro messaggi, un ottimo modo per rimanere al corrente delle notifiche push. 
  
  
### <a name="frequently-asked-questions"></a>Domande frequenti

|**Domanda**|**Risposta**|
|:-----|:-----|
|Chi può visualizzare i post nel Centro messaggi?  <br/> |La maggior parte degli utenti a cui è stato assegnato un ruolo di amministratore in Microsoft 365 può visualizzare i post del Centro messaggi. [Ecco un elenco dei](#admin-roles-that-dont-have-access-to-the-message-center) ruoli di amministratore che non hanno accesso al Centro messaggi. È inoltre possibile assegnare il ruolo di lettore del Centro messaggi agli utenti che dovrebbero essere in grado di leggere e condividere i post del Centro messaggi senza disporre di altri privilegi di amministratore.<br/>|
|Questo è l'unico modo in cui Microsoft comunicherà le modifiche su Microsoft 365?  <br/> |No, ma il Centro messaggi è il modo principale per comunicare la tempistica delle singole modifiche in Microsoft 365. Per informazioni sulle risorse aggiuntive, vedere Mantenere il controllo delle modifiche di [Microsoft 365 .](stay-on-top-of-updates.md)  <br/> |
|Come si visualizzano i post in una lingua specifica?  <br/> |I post del Centro messaggi sono scritti solo in inglese, ma puoi controllare se, per impostazione predefinita, i post vengono visualizzati in inglese o vengono tradotti automaticamente nella lingua preferita. Puoi anche scegliere di tradurre automaticamente i post in qualsiasi lingua che supportiamo. Per [ulteriori dettagli, vedere](language-translation-for-message-center-posts.md) Traduzione in lingua per i post del Centro messaggi.  <br/> |
|È possibile ottenere un'anteprima delle modifiche o delle caratteristiche prima che vengano distribuite nell'organizzazione?  <br/> |Alcune modifiche e nuove funzionalità possono essere visualizzate in anteprima acconsentendo esplicitamente al programma Targeted Release. Per acconsentire esplicitamente, nell'interfaccia di amministrazione passare **a** Impostazioni  >  **preferenze di rilascio del profilo**  >  **dell'organizzazione.** Nell'interfaccia di amministrazione potrebbe essere  necessario selezionare Mostra tutto nella parte inferiore del riquadro di spostamento sinistro per visualizzare **Impostazioni.** È possibile scegliere Targeted Release per l'intera organizzazione o solo per gli utenti selezionati. Per altre informazioni sul programma, vedere Opzioni standard o [targeted release in Microsoft 365.](release-options-in-office-365.md)  <br/> |
|È possibile individuare la data esatta in cui una modifica verrà resa disponibile a un'organizzazione?  <br/> |Purtroppo non è possibile indicare la data esatta in cui verrà apportata una modifica all'organizzazione. Nel post del Centro messaggi vengono fornite tutte le informazioni disponibili al momento del rilascio, in base al livello di probabilità. Stiamo lavorando a miglioramenti per migliorare questo livello di dettaglio.  <br/> |
|I messaggi sono specifici per l'organizzazione di ogni utente?  <br/> |Microsoft si impegna al massimo perché a ogni utente vengano visualizzati solo i post del Centro messaggi che interessano la sua organizzazione. La roadmap di Microsoft 365 include tutte le funzionalità attualmente in fase di implementazione, ma non tutte si applicano a tutte le organizzazioni. <br/> |
|È possibile ricevere i post del Centro messaggi tramite posta elettronica?  <br/> |Sì. È possibile scegliere di inviare un riepilogo settimanale tramite posta elettronica all'utente e a un massimo di altri due indirizzi di posta elettronica. Il riepilogo settimanale inviato tramite posta elettronica è attivato per impostazione predefinita. Se non si riceve il riepilogo settimanale, controllare la cartella della posta indesiderata. Vedi la [sezione Preferenze](#preferences) di questo articolo per altre informazioni su come configurare il riepilogo settimanale.  <br/> |
|Come si interrompe il recupero del digest del Centro messaggi?  <br/> |Accedere al Centro messaggi nell'interfaccia di amministrazione e selezionare **Modifica preferenze.** Disattivare l'opzione Per **inviare un riepilogo settimanale dei messaggi.** Se inoltre non si desidera più ricevere messaggi di posta elettronica sugli aggiornamenti principali, disattivare Inviami messaggi di posta **elettronica per gli aggiornamenti principali.**  <br/> |
|Come posso garantire che le notifiche sulla privacy dei dati siano ricevute dai contatti giuste nell'organizzazione? <br/> |Gli amministratori globali riceveranno messaggi sulla privacy dei dati per l'organizzazione. Inoltre, è possibile assegnare il ruolo di lettore della privacy del Centro messaggi agli utenti che devono visualizzare i messaggi sulla privacy dei dati. Altri ruoli di amministratore con accesso al Centro messaggi non possono visualizzare i messaggi sulla privacy dei dati.   <br/><br/>Per altre info, vedi [Preferenze](#preferences) in questo articolo.<br/> |
|Perché non è possibile visualizzare un messaggio presente in precedenza? <br/> |Per gestire il numero di messaggi all'interno del Centro messaggi, ogni messaggio scadrà e verrà rimosso dopo un periodo di tempo. In genere, i messaggi scadono 30 giorni dopo il periodo di tempo indicato nel corpo del messaggio. <br/> |

### <a name="messages"></a>Messaggi

Il Centro messaggi presenta una visualizzazione di tutti i messaggi attivi in formato tabella. Per impostazione predefinita, viene visualizzato il messaggio più recente all'inizio dell'elenco. È possibile selezionare una scheda per visualizzare Tutti i messaggi **attivi,** Messaggi con **priorità** alta, Messaggi non **letti** e **Messaggi ignorati.** È inoltre possibile utilizzare il menu a discesa **Filtro** per visualizzare tutti i messaggi in una categoria di messaggi specifica.

Ecco una rapida panoramica delle informazioni che vedrai in ogni colonna. Selezionare una delle intestazioni di colonna per modificare l'ordinamento.
  
|**Colonna**|**Descrizione**|
|:-----|:-----|
|Segno di spunta  <br/> |Se si seleziona il segno di spunta nella riga dell'intestazione di colonna, verranno selezionati tutti i messaggi attualmente visualizzati. Selezionando il segno di spunta accanto a uno o più messaggi, è possibile intervenire su tali messaggi.  <br/> |
|Icona applicazione <br/> |Le icone indicano l'applicazione a cui si applica il messaggio.<br/> |
|Titolo messaggio  <br/> |I titoli dei messaggi sono brevi descrizioni delle modifiche future. Se il titolo completo non viene visualizzato, posizionare il puntatore del mouse su di esso e l'intero titolo verrà visualizzato in una casella popup.  <br/> |
|Altre opzioni <br/> |Altre opzioni consentono di ignorare un messaggio, contrassegnarlo come letto o non letto o condividerlo con un altro amministratore. Per ripristinare un messaggio ignorato, selezionare la scheda **Messaggi** ignorati, selezionare il segno di spunta accanto al messaggio e selezionare **Ripristina**. <br/> |
|Aggiornamento principale <br/> |Un punto esclamativo in questa colonna indica un aggiornamento principale. <br/> |
|Intervento entro  <br/> |Qui verranno specificate solo le date se Microsoft intende apportare una modifica che richiede l'intervento dell'utente entro una certa data di scadenza. Dal momento che raramente viene utilizzata la colonna Act **by,** se si vede qualcosa, è consigliabile prestare particolare attenzione.  <br/> |
|Categoria  <br/> | I messaggi sono identificati da una delle tre categorie seguenti: <br/><br/> **Prevenzione o risoluzione dei** problemi: informa l'utente dei problemi noti che interessano l'organizzazione e potrebbe richiedere l'intervento dell'utente per evitare interruzioni del servizio. I messaggi di tipo Prevenire o risolvere problemi sono diversi da quelli di tipo Integrità dei servizi, in quanto richiedono che l'utente sia proattivo per evitare problemi. <br/> <br/> **Pianificare la modifica:** informa l'utente delle modifiche apportate a Microsoft 365 che potrebbero richiedere l'intervento dell'utente per evitare interruzioni del servizio. Ad esempio, verranno comunicate le modifiche apportate ai requisiti di sistema o le caratteristiche in fase di rimozione. Per assicurare la normale operatività del servizio, Microsoft fornisce almeno 30 giorni di preavviso per ogni modifica che richiede l'intervento di un amministratore. <br/> <br/> **Rimanere informati:** indica le funzionalità nuove o aggiornate che stiamo attivando nell'organizzazione. Le funzionalità vengono in genere annunciate per prime nella roadmap di [Microsoft 365.](https://go.microsoft.com/fwlink/?linkid=2070821) <br/><br/>Può inoltre inserirvi informazioni sulla manutenzione pianificata in conformità al contratto di servizio. La manutenzione pianificata può comportare tempi di insod0>, in cui l'utente o gli utenti non possono accedere a Microsoft 365, a una funzionalità specifica o a un servizio come la posta elettronica o OneDrive for Business.  <br/> |
|Ultimo aggiornamento  <br/> |Data dell'ultimo aggiornamento o pubblicazione del messaggio.  <br/> |
|ID messaggio  <br/> |Microsoft tiene traccia dei post del Centro messaggi in base agli ID messaggio. È possibile fare riferimento a questo ID se si desidera inviare commenti e suggerimenti o se si chiama il supporto tecnico per un determinato messaggio.  <br/> |

Per altre informazioni sulle operazioni che è possibile eseguire con i messaggi, vedere [Gestire i messaggi nel Centro messaggi](manage-messages.md).
  
### <a name="major-updates"></a>Aggiornamenti principali

Gli aggiornamenti principali possono essere esaminati selezionando la **scheda** Priorità alta nella parte superiore del Centro messaggi.

Gli aggiornamenti principali vengono comunicati con almeno 30 giorni di anticipo quando è necessaria un'azione e possono includere:
  
- Modifiche alla produttività giornaliera, ad esempio posta in arrivo, riunioni, deleghe, condivisione e accesso

- Modifiche a temi, web part e altri componenti che possono influire sulle caratteristiche personalizzate

- Aumenta o riduce la capacità visibile, ad esempio l'archiviazione, il numero di regole, gli elementi o le durate

- Modifiche alla personalizzazione del prodotto che possono:

  - Causare confusione all'utente finale,

  - Sono state apportate modifiche ai processi dell'help desk e al materiale di riferimento oppure

  - Modificare un URL

- Un nuovo servizio o una nuova applicazione

- Modifiche che richiedono un'azione dell'amministratore (esclusive di prevenire o risolvere i problemi)

- Modifiche alla posizione di archiviazione dei dati
  
### <a name="preferences"></a>Preferenze

Se l'amministrazione è distribuita all'interno dell'organizzazione, potrebbe non essere necessario o meno visualizzare post su tutti i servizi di Microsoft 365. Ogni amministratore può:

- Impostare le preferenze che controllano quali messaggi vengono visualizzati nel Centro messaggi.
- Filtrare i messaggi
- Impostare le preferenze di posta elettronica per ricevere un riepilogo settimanale di tutti i messaggi, messaggi di posta elettronica solo per gli aggiornamenti principali e messaggi di posta elettronica per i messaggi di privacy dei dati.  

::: moniker range="o365-worldwide"

1. Selezionare **Modifica preferenze** nella parte superiore del Centro messaggi.

2. Verificare che la casella di controllo sia selezionata per ogni servizio che si desidera monitorare. Deselezionare le caselle di controllo relative ai servizi che si desidera filtrare dalla visualizzazione Del Centro messaggi.

3. I messaggi di posta elettronica di riepilogo sono attivati per impostazione predefinita e inviati all'indirizzo di posta elettronica principale. Per interrompere la ricezione del riepilogo settimanale, deselezionare la casella di controllo Invia un riepilogo settimanale dei **messaggi.** <br/><br/>La notifica tramite posta elettronica per gli aggiornamenti principali è un controllo separato. Se si desidera ricevere avvisi tramite posta elettronica sugli aggiornamenti principali, verificare che sia selezionata l'opzione Inviami messaggi di posta elettronica **per gli aggiornamenti** principali. Deselezionare la casella di controllo per interrompere la posta elettronica sugli aggiornamenti principali. <br><br/>Selezionare la casella di controllo accanto a **Inviami** messaggi di posta elettronica per i messaggi di privacy dei dati per ricevere notifiche di posta elettronica separate dei messaggi di privacy dei dati (i messaggi sulla privacy dei dati non sono inclusi nel riepilogo settimanale). <br><br/>È possibile selezionare o deselezionare l'indirizzo di posta elettronica principale, ma non è possibile modificarlo. Per specificare altri indirizzi di posta elettronica a cui  inviare il messaggio di posta elettronica sulla privacy dei dati, selezionare la casella di controllo Altri indirizzi di posta elettronica e immettere gli altri indirizzi di posta elettronica a cui si desidera inviare il messaggio di posta elettronica. Immettere l'indirizzo di posta elettronica per un gruppo di Microsoft 365 o una lista di distribuzione se più di due persone devono ricevere un messaggio di posta elettronica sulla privacy dei dati.

4. Selezionare **Salva** per mantenere le modifiche.
  
::: moniker-end 

::: moniker range="o365-germany"

1. Selezionare **Modifica preferenze Centro messaggi** nella parte superiore del Centro messaggi.

2. Assicurarsi che il tasto di alternanza sia impostato su **Sì** per ogni servizio che si vuole monitorare. Utilizzare l'interruttore per modificare l'impostazione su **Disattivato** per i servizi che si desidera filtrare dalla visualizzazione del Centro messaggi.

3. I messaggi di posta elettronica di riepilogo sono attivati per impostazione predefinita e inviati all'indirizzo di posta elettronica principale. Per interrompere la ricezione del riepilogo settimanale, modificare l'impostazione Invia un **riepilogo** settimanale dei messaggi su **Disattivato.** <br/><br/>La notifica tramite posta elettronica per gli aggiornamenti principali è un controllo separato. Se si desidera ricevere avvisi tramite posta elettronica sugli aggiornamenti principali, verificare che l'opzione Inviami messaggi di posta elettronica per **gli aggiornamenti principali** sia impostata su **On.** Modificare l'impostazione su **Disattivato** per interrompere la posta elettronica sugli aggiornamenti principali. <br/><br/>Per ricevere notifiche tramite posta elettronica sui messaggi sulla privacy dei dati, verificare che l'impostazione Inviami messaggi di posta elettronica per **i messaggi sulla privacy** dei dati sia **impostata su On.** Per interrompere la ricezione di questi avvisi, modificare l'impostazione su **Disattivato.** I messaggi sulla privacy dei dati non sono inclusi nel riepilogo settimanale.<br/><br/>È possibile selezionare o deselezionare l'indirizzo di posta elettronica principale, ma non è possibile modificarlo. Per specificare altri indirizzi di posta elettronica a cui viene inviato il riepilogo settimanale della posta elettronica, verificare che l'opzione Invia un riepilogo settimanale **dei messaggi** sia impostata su **On.** Immettere l'indirizzo di posta elettronica per un gruppo di Microsoft 365 o una lista di distribuzione se più di due persone devono ricevere il messaggio di posta elettronica di riepilogo.

4. Selezionare **Salva** per mantenere le modifiche.<br/>

::: moniker-end

::: moniker range="o365-21vianet"

1. Selezionare **Modifica preferenze Centro messaggi** nella parte superiore del Centro messaggi.

2. Assicurarsi che il tasto di alternanza sia impostato su **Sì** per ogni servizio che si vuole monitorare. Utilizzare l'interruttore per modificare l'impostazione su **Disattivato** per i servizi che si desidera filtrare dalla visualizzazione del Centro messaggi.

3. I messaggi di posta elettronica di riepilogo sono attivati per impostazione predefinita e inviati all'indirizzo di posta elettronica principale. Per interrompere la ricezione del riepilogo settimanale, modificare l'impostazione Invia un **riepilogo** settimanale dei messaggi su **Disattivato.** <br/><br/>La notifica tramite posta elettronica per gli aggiornamenti principali è un controllo separato. Se si desidera ricevere avvisi tramite posta elettronica sugli aggiornamenti principali, verificare che l'opzione Inviami messaggi di posta elettronica per **gli aggiornamenti principali** sia impostata su **On.** Modificare l'impostazione su **Disattivato** per interrompere la posta elettronica sugli aggiornamenti principali. <br/><br/>Per ricevere notifiche tramite posta elettronica sui messaggi sulla privacy dei dati, verificare che l'impostazione Inviami messaggi di posta elettronica per **i messaggi sulla privacy** dei dati sia **impostata su On.** Per interrompere la ricezione di questi avvisi, modificare l'impostazione su **Disattivato.** I messaggi sulla privacy dei dati non sono inclusi nel riepilogo settimanale.<br/><br/>È possibile selezionare o deselezionare l'indirizzo di posta elettronica principale, ma non è possibile modificarlo. Per specificare altri indirizzi di posta elettronica a cui viene inviato il riepilogo settimanale della posta elettronica, verificare che l'opzione Invia un riepilogo settimanale **dei messaggi** sia impostata su **On.** Immettere l'indirizzo di posta elettronica per un gruppo di Microsoft 365 o una lista di distribuzione se più di due persone devono ricevere il messaggio di posta elettronica di riepilogo.

4. Selezionare **Salva** per mantenere le modifiche.<br/>

::: moniker-end

#### <a name="display-messages-in-your-preferred-language"></a>Visualizzare i messaggi nella lingua preferita
  
Usiamo la traduzione automatica per visualizzare automaticamente i messaggi nella lingua preferita. Leggi [la traduzione in lingua per i post](language-translation-for-message-center-posts.md) del Centro messaggi per ulteriori informazioni su come impostare la lingua.
  
> [!NOTE]
> Il riepilogo settimanale e i post inviati tramite posta elettronica vengono inviati solo in inglese. I destinatari possono [utilizzare Translator per Outlook](https://support.microsoft.com/office/3d7e12ed-99d6-406e-a453-b9db0d9653fa) per leggere il messaggio nella lingua preferita. 
  
### <a name="admin-roles-that-dont-have-access-to-the-message-center"></a>Ruoli di amministratore che non hanno accesso al Centro messaggi

- Amministratore di conformità
- Amministratore dell'accesso condizionale
- Responsabile approvazione dell'accesso a Customer LockBox
- Amministratori dei dispositivi
- Lettori di directory
- Account di sincronizzazione della directory
- Ruoli con autorizzazioni di scrittura nella directory
- Amministratore del servizio Intune
- Amministratore dei ruoli con privilegi
- Ruolo con autorizzazioni di lettura per i report

## <a name="unsubscribe-from-message-center-emails"></a>Annullare la sottoscrizione ai messaggi di posta elettronica del Centro messaggi

1. I messaggi di posta elettronica di riepilogo sono attivati per impostazione predefinita e inviati all'indirizzo di posta elettronica principale. Per interrompere la ricezione del riepilogo settimanale, modificare l'impostazione Invia un **riepilogo** settimanale dei messaggi su **Disattivato.** <br/><br/>La notifica tramite posta elettronica per gli aggiornamenti principali è un controllo separato. Se non si desidera ricevere notifiche tramite posta elettronica sugli aggiornamenti principali, verificare che l'opzione Inviami messaggi di posta elettronica per **gli aggiornamenti principali** sia **disattivata.**  <br/><br/>Per interrompere la ricezione di notifiche tramite posta elettronica sui messaggi sulla privacy dei dati, verificare che l'impostazione Invia messaggi di posta elettronica per i **messaggi di privacy** dei dati sia **disattivata.**  I messaggi sulla privacy dei dati non sono inclusi nel riepilogo settimanale.<br/><br/>

2. Selezionare **Salva** per mantenere le modifiche.<br/>