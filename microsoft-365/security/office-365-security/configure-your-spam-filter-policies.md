---
title: Configurare i criteri di filtro della posta indesiderata
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 12/05/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 316544cb-db1d-4c25-a5b9-c73bbcf53047
ms.collection:
- M365-security-compliance
description: Le impostazioni di base del filtro della posta indesiderata includono la possibilità di eliminare i messaggi identificati come posta indesiderata.
ms.openlocfilehash: 0fa597887a75ff71d768d4df0b1ac4f17fe9ef13
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2020
ms.locfileid: "42857358"
---
# <a name="configure-your-spam-filter-policies"></a>Configurare i criteri di filtro della posta indesiderata
Le impostazioni del filtro della posta indesiderata includono la possibilità di eliminare i messaggi identificati come posta indesiderata. Le impostazioni del filtro della posta indesiderata vengono applicate solo ai messaggi in arrivo e sono di due tipi:

  - Predefinito: il criterio di filtro della posta indesiderata predefinito consente di configurare le impostazioni del filtro della posta indesiderata a livello aziendale. Questo criterio non può essere rinominato ed è sempre attivo.

  - Personalizzato: i criteri del filtro della posta indesiderata personalizzati possono essere granulari e applicati a utenti, gruppi o domini specifici nell'organizzazione. I criteri personalizzati hanno sempre la precedenza sui criteri predefiniti. È possibile modificare l'ordine di esecuzione dei criteri personalizzati modificando la priorità di ogni criterio personalizzato; tuttavia, solo il criterio con la massima priorità (ad esempio, il numero più vicino a 0) verrà applicato se più criteri soddisfano i criteri impostati.

## <a name="what-you-must-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare

Tempo stimato per il completamento: 30 minuti

Devi disporre delle autorizzazioni per poter eseguire queste procedure.  Per sapere quali autorizzazioni sono necessarie, vedere la voce Protezione da posta indesiderata nell'argomento [Autorizzazioni funzionalità in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions).

Le impostazioni dei criteri del filtro della posta indesiderata si trovano tutte nel Centro sicurezza e conformità. Per ulteriori informazioni, vedere [Accedere al Centro sicurezza e conformità di Office 365](../../compliance/go-to-the-securitycompliance-center.md). La pagina delle impostazioni del filtro della posta indesiderata si trova nella sezione \> **Gestione delle minacce** \> **Criterio** \> **Protezione posta indesiderata** del Centro sicurezza e conformità.

## <a name="access-and-create-spam-filter-policies"></a>Accedere e creare criteri del filtro della posta indesiderata

All'interno della pagina delle impostazioni del filtro della posta indesiderata, le impostazioni predefinite possono essere visualizzate nella scheda Standard. Per modificare queste impostazioni, passare alla scheda **Personalizzato**. Sarà possibile vedere e configurare alcune delle impostazioni predefinite all'interno del criterio del filtro della posta indesiderata predefinito.

Per abilitare più impostazioni personalizzate o per aggiungere criteri personalizzati, spostare il selettore **Impostazioni personalizzate** su **On** per abilitare i criteri personalizzati del filtro della posta indesiderata. È possibile visualizzare i criteri personalizzati esistenti aprendoli da qui.

## <a name="configure-custom-spam-filter-policy-settings"></a>Configurare le impostazioni dei criteri personalizzati del filtro della posta indesiderata

1. Selezionare e fare clic su **Modifica criterio** se si sta modificando un criterio; altrimenti, fare clic su **Crea criterio**

2. È possibile specificare un nome univoco per i criteri personalizzati, ma non è possibile rinominare quello predefinito. Opzionalmente, è anche possibile specificare una descrizione più dettagliata per i criteri.

3. Nella sezione **Azioni per posta indesiderata e inviata in blocco**:

   - Selezionare un'azione per i tipi **Posta indesiderata**, **Posta indesiderata con alta confidenza**, **Posta di phishing con alta confidenza**, **Posta di phishing** e **Posta elettronica inviata in blocco**. I valori disponibili sono i seguenti:

     - **Sposta i messaggi nella cartella Posta indesiderata**: sposta i messaggi di destinatari specifici nella cartella Posta indesiderata. Questa è l'azione predefinita per la posta indesiderata, la posta indesiderata con alta confidenza e la posta elettronica inviata in blocco.

       > [!NOTE]
       > Affinché tale operazione funzioni con cassette postali locali, è necessario configurare due regole del flusso di posta di Exchange (note come regole di trasporto) nei server locali per individuare intestazioni di posta indesiderata aggiunte da EOP. Per ulteriori informazioni, vedere [Verifica del reindirizzamento della posta indesiderata nella cartella Posta indesiderata degli utenti](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md). Questo passaggio è critico per i clienti autonomi di Exchange Online Protection (EOP).

     - **Aggiungi X-header**: invia i messaggi di destinatari specifici ma aggiunge un testo X-header all'intestazione del messaggio per identificarlo come posta indesiderata. Usando questo testo come identificativo, è possibile anche scegliere di creare regole per la posta in arrivo o usare un dispositivo downstream per agire sul messaggio. Il testo X-header predefinito è **Il messaggio sembra essere posta indesiderata**.
     
       È possibile personalizzare il testo X-header utilizzando la casella di input **Aggiungi testo all'X-header**. Se si personalizza il testo X-header, è necessario tenere presenti le seguenti condizioni:

       - Se si specifica solo l'intestazione nel formato \< *header*  \>, dove non sono presenti spazi tra \<  *header*  \>, un carattere di due punti verrà aggiunto al testo personalizzato, seguito dal testo predefinito. Ad esempio, se si specifica "Questa-è-la-intestazione-personalizzata", il testo X-header verrà visualizzato come "Questa è l'intestazione personalizzata: il messaggio sembra essere posta indesiderata".

       - Se si includono spazi nel testo dell'intestazione personalizzata oppure se si aggiunge manualmente un carattere di due punti, ad esempio "X Questa è l'intestazione personalizzata" oppure "X-Questa-è-la-intestazione-personalizzata:", sarà ripristinato il testo X-header predefinito come "X-This-Is-Spam: il messaggio sembra essere posta indesiderata".

       - Non è possibile specificare il testo dell'intestazione nel formato \<*intestazione*\>:\<*valore*\>. Se si compie questa operazione, entrambi i valori prima e dopo il carattere di due punti verranno ignorati e verrà visualizzato il testo X-header predefinito: "X-This-Is-Spam: il messaggio sembra essere posta indesiderata".

       - Tenere presente che i messaggi con X-header possono comunque essere spostati nella cartella Posta indesiderata della cassetta postale per via della configurazione della posta indesiderata della cassetta postale. È possibile modificare l'impostazione disabilitando questa funzionalità con Set-MailboxJunkEmailConfiguration.

   - **Anteponi oggetto al testo:** invia il messaggio al destinatario desiderato e antepone l'oggetto al testo specificato nella casella di input **Anteponi oggetto a questo testo**. Utilizzando questo testo come identificatore, è eventualmente possibile creare delle regole per filtrare o instradare i messaggi in base alle esigenze.
    
     > [!NOTE]
     > Il messaggio verrà comunque spostato nella cartella Posta indesiderata.

   - **Reindirizza messaggio a indirizzo di posta elettronica:** invece di inviare il messaggio ai destinatari, lo invia all'indirizzo di posta elettronica designato. Specificare l'indirizzo nella casella di input **Reindirizza a questo indirizzo di posta elettronica**.

   - **Elimina messaggio:** elimina l'intero messaggio, inclusi gli allegati.

   - **Messaggio in quarantena:** il messaggio non viene inviato ai destinatari, ma viene messo in quarantena. Si tratta dell'azione predefinita per il phishing. Selezionando questa opzione nella casella di controllo **Conserva la posta indesiderata per (giorni)**, si specifica per quanti giorni i messaggi indesiderati vengono messi in quarantena (il messaggio viene eliminato automaticamente al termine del tempo trascorso. Il valore predefinito massimo è 30 giorni. Il valore minimo è 1 giorno).

     > [!TIP]
     > Per informazioni su come gli amministratori gestiscono i messaggi di posta elettronica presenti nella quarantena, vedere [Quarantena](quarantine.md) e [Gestire i messaggi e i file in quarantena come amministratore in Office 365](manage-quarantined-messages-and-files.md) <br/><br/> Per informazioni su come configurare i messaggi di notifica per la posta indesiderata per gli utenti, vedere [Configurare le notifiche di posta indesiderata dell'utente finale in EOP](configure-end-user-spam-notifications-in-eop.md) o [Configurare le notifiche di posta indesiderata dell'utente finale in Exchange Online](configure-end-user-spam-notifications-in-exchange-online.md).

   - Configurare **Seleziona la soglia** per determinare il modo in cui si vuole gestire la posta elettronica in blocco come posta indesiderata, in base al Livello di reclamo in blocco del messaggio. È possibile scegliere un'impostazione di soglia tra 1 e 9, dove 1 indica la maggior parte della posta elettronica come posta indesiderata e 9 consente di recapitare la maggior parte della posta elettronica in blocco. Il servizio quindi esegue l'azione configurata, ad esempio, l'invio del messaggio alla cartella Posta indesiderata del destinatario. Vedere [Valori del Livello di reclamo in blocco](bulk-complaint-level-values.md) e [Differenza tra posta elettronica indesiderata e posta elettronica in blocco](what-s-the-difference-between-junk-email-and-bulk-email.md) per ulteriori dettagli.

4. Nella pagina **Proprietà della posta indesiderata**, è possibile impostare le opzioni della modalità di test per il criterio configurando:

   - **Nessuna**: per impostazione predefinita, non vengono intraprese azioni in modalità test sul messaggio.

   - **Aggiungi il testo X-Header predefinito per il test** Il messaggio viene inviato ai destinatari specificati, ma con l'aggiunta di un testo X-header speciale che lo identifica come corrispondente a una specifica opzione avanzata di filtro di protezione da posta indesiderata.

   - **Invia un messaggio Ccn a questo indirizzo** Viene inviata una copia per conoscenza nascosta del messaggio all'indirizzo di posta elettronica specificato nella casella.  <br/><br/>Per ulteriori informazioni sulle opzioni di filtro della posta indesiderata, comprese le descrizioni di ogni opzione e del testo X-header associato a ognuna, vedere [Opzioni avanzate per il filtro della posta indesiderata](advanced-spam-filtering-asf-options.md).

5. Solo per i criteri personalizzati, fare clic sulla voce di menu **Applica a**, quindi creare una regola basata sulle condizioni per specificare utenti, gruppi e domini ai quali applicare il criterio. È possibile creare più condizioni, ammesso che siano uniche.

   - Per selezionare gli utenti, scegliere **Il destinatario è**. Nella finestra di dialogo successiva, selezionare uno o più mittenti dall'azienda dall'elenco di selezione utenti, quindi fare clic su **aggiungi**. Per aggiungere mittenti non presenti nell'elenco, digitarne l'indirizzo di posta elettronica, quindi fare clic su **Controlla nomi**. Inoltre, in questa casella è possibile utilizzare caratteri jolly per più indirizzi di posta elettronica (ad esempio: \*@ _domainname_). Una volta terminate le selezioni fare clic su **OK** per tornare alla schermata principale.

   - Per selezionare i gruppi, selezionare **Il destinatario è un membro di**. Quindi, nella finestra di dialogo successiva, selezionare o specificare i gruppi. Fare clic su **OK** per tornare alla schermata principale.

   - Per selezionare i domini, selezionare **Il dominio del destinatario è**. Quindi, nella finestra di dialogo successiva, aggiungere i domini. Fare clic su **OK** per tornare alla schermata principale.

     È possibile creare eccezioni all'interno della regola. Ad esempio, è possibile filtrare i messaggi da tutti i domini, eccetto per alcuni. Fare clic su **Aggiungi eccezione**, quindi creare le condizioni di eccezione nel modo in cui sono state create le altre condizioni.

     L'applicazione di criteri di posta indesiderata a un gruppo è supportata solo per i **gruppi di sicurezza abilitati alla posta**.

6. Fare clic su **Salva**. Nel riquadro destro viene visualizzato un riepilogo delle impostazioni dei criteri.

Non è possibile disabilitare o eliminare i criteri predefiniti e i criteri personalizzati hanno sempre la precedenza sui criteri predefiniti. Per i criteri personalizzati, è possibile selezionare o deselezionare le caselle di controllo nella colonna **ABILITATO** per abilitarli o disabilitarli. Per impostazione predefinita, tutti i criteri sono abilitati. Per eliminare un criterio personalizzato, selezionare il criterio e fare clic sull'icona **Elimina** ![Icona Elimina](../../media/ITPro-EAC-DeleteIcon.gif), quindi confermare che si vuole eliminare il criterio.

> [!TIP]
> È possibile cambiare la priorità (ordine di esecuzione) dei criteri personalizzati facendo clic su ![Icona Freccia in su](../../media/ITPro-EAC-UpArrowIcon.gif) freccia su e ![Icona Freccia in giù](../../media/ITPro-EAC-DownArrowIcon.gif) freccia giù. Il criterio con **PRIORITÀ** pari a **0** verrà eseguito per primo, seguito da quello con priorità **1**, poi **2** e così via.

## <a name="use-powershell-to-configure-spam-filter-policies"></a>Utilizzo di PowerShell per la configurazione dei criteri di filtro di protezione dalla posta indesiderata

È inoltre possibile configurare e applicare i criteri di filtro di protezione dalla posta indesiderata in PowerShell. Per informazioni su come usare Windows PowerShell per connettersi a Exchange Online, vedere [Connessione a Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell). Per informazioni su come usare Windows PowerShell per connettersi a Exchange Online Protection, vedere [Connessione a Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).

- [Get-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-hostedcontentfilterpolicy) Visualizzare le impostazioni di filtro di protezione dalla posta indesiderata.

- [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterpolicy) Modificare le impostazioni di filtro di protezione dalla posta indesiderata.

- [New-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/new-hostedcontentfilterpolicy) Creare un nuovo criterio di filtro di protezione dalla posta indesiderata personalizzato.

- [Remove-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/remove-hostedcontentfilterpolicy) Eliminare un criterio di filtro di protezione dalla posta indesiderata personalizzato.

Per applicare un criterio di filtro di protezione dalla posta indesiderata personalizzato a utenti, gruppi e/o domini, utilizzare il cmdlet [New-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/new-hostedcontentfilterrule) (per creare una nuova regola di filtro che possa essere applicata ai criteri personalizzati) oppure il cmdlet [Set-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedcontentfilterrule) (per modificare una regola di filtro esistente che possa essere applicata ai criteri personalizzati). Utilizzare il cmdlet [Enable-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/enable-hostedcontentfilterrule) oppure il cmdlet [Disable-HostedContentFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/disable-hostedcontentfilterrule) per abilitare o disabilitare la regola applicata al criterio.

## <a name="how-do-you-know-this-worked"></a>Come verificare se l'operazione ha avuto esito positivo

Per assicurarsi di aver identificato correttamente la posta indesiderata, è possibile inviare un messaggio GTUBE tramite il servizio. Come il file di test antivirus EICAR, GTUBE fornisce un test tramite il quale è possibile verificare se il servizio individua la posta indesiderata in arrivo. Un messaggio GTUBE viene sempre identificato come posta indesiderata e le azioni eseguite sul messaggio potrebbero corrispondere alle impostazioni configurate.

Includere il seguente testo GTUBE in un messaggio di posta o in una singola riga, senza spazi o interruzioni di riga:

```text
XJS*C4JDBQADN1.NSBN3*2IDNEN*GTUBE-STANDARD-ANTI-UBE-TEST-EMAIL*C.34X
```

## <a name="fine-tuning-your-spam-filter-policy-to-prevent-false-positives-and-false-negatives"></a>Regolazione dei criteri del filtro della posta indesiderata per impedire falsi positivi e falsi negativi

Se si desidera intraprendere un approccio più aggressivo, è possibile attivare opzioni avanzate per il filtro della posta indesiderata. Per informazioni sulle impostazioni relative alla posta indesiderata per un'intera organizzazione, consultare [Come evitare che i messaggi effettivi vengano contrassegnati come indesiderati in Office 365](prevent-email-from-being-marked-as-spam.md) o [Bloccare la posta indesiderata con il filtro di posta indesiderata di Office 365 per prevenire il problema dei falsi negativi](reduce-spam-email.md). Questi articoli sono utili se si svolge il ruolo di amministratore e si desidera impedire la visualizzazione di falsi negativi o di falsi positivi.

## <a name="allowblock-lists"></a>Elenchi di elementi consentiti/bloccati

A volte i filtri non riescono a bloccare i messaggi o impiegano molto tempo a farlo. In questi casi, i criteri di protezione da posta indesiderata presentano Elenchi di elementi consentiti/bloccati per ignorare il verdetto corrente. Questa opzione deve essere usata solo in modo parsimonioso, perché gli elenchi possono diventare ingestibili e temporaneamente perché il nostro stack di filtri deve svolgere il proprio lavoro.

Entrambi gli elenchi sono configurati in qualsiasi criterio di protezione da posta indesiderata del cliente:

1. Nella sezione **Elenchi di elementi consentiti**, è possibile specificare voci, come mittenti o domini, che verranno sempre recapitati alla posta in arrivo. La posta elettronica proveniente da tali voci non viene elaborata dal filtro di protezione da posta indesiderata.

   - Aggiungere i mittenti attendibili a Elenco mittenti consentiti. Fare clic su **Modifica**![Icona Aggiungi](../../media/ITPro-EAC-AddIcon.gif), quindi nella finestra di dialogo di selezione, aggiungere gli indirizzi dei mittenti che si desidera autorizzare. È possibile separare più voci con un punto e virgola o una nuova riga. Fare clic su **Salva** per tornare alla pagina **Elenchi di elementi consentiti**.

   - Aggiungere i domini attendibili a Elenco di domini consentiti. Fare clic su **Modifica**![Icona Aggiungi](../../media/ITPro-EAC-AddIcon.gif), quindi nella finestra di dialogo di selezione, aggiungere i domini che si desidera autorizzare. È possibile separare più voci con un punto e virgola o una nuova riga. Fare clic su **Salva** per tornare alla pagina **Elenchi di elementi consentiti**.

   > [!CAUTION]
   > Non è mai consigliabile elencare i domini accettati (ossia quelli proprietari) o i domini comuni come Microsoft.com, office.com e così via, in un elenco di elementi consentiti. Ciò consente agli spoofer di inviare messaggi di posta elettronica senza restrizioni nell'organizzazione.

2. Nella pagina **Elenchi contatti bloccati**, è possibile specificare voci, come mittenti o domini, che verranno sempre contrassegnati come Posta indesiderata. Il servizio applica l'azione di probabilità di posta indesiderata configurata alla posta elettronica che corrisponde a tali voci.

   - Aggiungere i mittenti indesiderati all'elenco dei mittenti bloccati. Fare clic su **Modifica**![Icona Aggiungi](../../media/ITPro-EAC-AddIcon.gif), quindi nella finestra di dialogo di selezione, aggiungere gli indirizzi dei mittenti che si desidera bloccare. È possibile separare più voci con un punto e virgola o una nuova riga. Fare clic su **Salva** per tornare alla pagina degli **elenchi di indirizzi bloccati**.

   - Aggiungere i domini indesiderati all'elenco dei domini bloccati. Fare clic su **Modifica**![Icona Aggiungi](../../media/ITPro-EAC-AddIcon.gif) e, nella finestra di dialogo di selezione, aggiungere i domini che si desidera bloccare. È possibile separare più voci con un punto e virgola o una nuova riga. Fare clic su **Salva** per tornare alla pagina degli **elenchi di indirizzi bloccati**.
   
     > [!NOTE]
     > Nei criteri filtro posta indesiderata è possibile bloccare interi domini o mittenti specifici, ma non è possibile usare i caratteri jolly (\*). 

> [!TIP]
> Ci potrebbero essere situazioni in cui l'organizzazione potrebbe non concordare con il verdetto fornito dal servizio. In questo caso, è consigliabile mantenere permanenti gli elenchi di elementi consentiti o bloccati. Tuttavia, se si vuole inserire un dominio nell'elenco di quelli consentiti per un periodo di tempo prolungato, è consigliabile indicare al mittente di verificare che il proprio dominio sia autenticato e impostato su DMARC, rifiutare se non lo è.

## <a name="for-more-information"></a>Ulteriori informazioni
<a name="sectionSection6"> </a>

[Configurazione del dominio per DMARC](use-dmarc-to-validate-email.md)

[Quarantena](quarantine.md)

[Come evitare che i messaggi effettivi vengano contrassegnati come indesiderati in Office 365](prevent-email-from-being-marked-as-spam.md)

[Come ridurre la posta indesiderata in Office 365](reduce-spam-email.md)

[Livelli di sicurezza della protezione contro la posta indesiderata](spam-confidence-levels.md)
