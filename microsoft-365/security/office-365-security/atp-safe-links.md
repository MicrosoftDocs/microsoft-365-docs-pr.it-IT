---
title: Collegamenti sicuri
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: Admin
ms.article: overview
f1_keywords:
- "197503"
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- ZVO160
- ZXL160
- ZPP160
- ZWD160
ms.assetid: dd6a1fef-ec4a-4cf4-a25a-bb591c5811e3
description: In questo articolo, gli amministratori possono ottenere informazioni sulla protezione dei collegamenti sicuri in Office 365 Advanced Threat Protection (ATP) per proteggere la propria organizzazione dal phishing e da altri attacchi che utilizzano URL dannosi.
ms.openlocfilehash: 742ccc82fe5c6fafa4e6c3463cb471b674b77fa9
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2020
ms.locfileid: "48326673"
---
# <a name="safe-links-in-office-365-atp"></a>Collegamenti sicuri in Office 365 ATP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> Questo articolo è destinato ai clienti aziendali che dispongono di [Office 365 Advanced Threat Protection (ATP)](office-365-atp.md). Se si sta utilizzando Outlook.com, Microsoft 365 Family o Microsoft 365 Personal e si cercano informazioni su Safelinks in Outlook, vedere [Advanced Outlook.com Security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).

Collegamenti sicuri è una funzionalità di [Office 365 Advanced Threat Protection](office-365-atp.md) che fornisce l'analisi e la riscrittura degli URL dei messaggi di posta elettronica in ingresso nel flusso di posta e la verifica del tempo di clic su URL e collegamenti nei messaggi di posta elettronica e in altre posizioni. L'analisi dei collegamenti sicuri si verifica in aggiunta alla normale [protezione da posta indesiderata e anti-malware](anti-spam-and-anti-malware-protection.md) nei messaggi di posta elettronica in ingresso in Exchange Online Protection (EOP). L'analisi dei collegamenti sicuri può aiutare a proteggere l'organizzazione da collegamenti dannosi che vengono utilizzati in tentativi di phishing e altri attacchi.

Protezione dei collegamenti sicuri è disponibile nei seguenti percorsi:

- **Messaggi di posta elettronica**: la protezione dei collegamenti sicuri per i collegamenti nei messaggi di posta elettronica è controllata da criteri collegamenti sicuri. Non esiste alcun criterio di collegamenti sicuri predefinito, **in modo da ottenere la protezione dei collegamenti sicuri nei messaggi di posta elettronica, è necessario creare uno o più criteri collegamenti sicuri**. Per istruzioni, vedere [configurare i criteri per i collegamenti sicuri in ATP](set-up-atp-safe-links-policies.md).

  Per ulteriori informazioni sulla protezione dei collegamenti sicuri per i messaggi di posta elettronica, vedere la sezione relativa alle [impostazioni dei collegamenti sicuri per i messaggi di posta elettronica](#safe-links-settings-for-email-messages) più avanti in questo articolo.

- **Microsoft teams** (attualmente in tap Preview): la protezione dei collegamenti sicuri per i collegamenti nelle conversazioni dei team, nelle chat di gruppo o nei canali è controllata anche dai criteri collegamenti sicuri. Non esiste alcun criterio di collegamenti sicuri predefinito, **in modo da ottenere la protezione dei collegamenti sicuri nei team, è necessario creare uno o più criteri collegamenti sicuri**.

  Per ulteriori informazioni sulla protezione dei collegamenti sicuri nei team, vedere la sezione [impostazioni collegamenti sicuri per Microsoft teams](#safe-links-settings-for-microsoft-teams) più avanti in questo argomento.

- **App di office 365**: la protezione dei collegamenti sicuri per le app di Office 365 è disponibile in APS desktop, mobili e Web supportati. È possibile **configurare** la protezione dei collegamenti sicuri per le app di Office 365 nell'impostazione globale **all'esterno** dei criteri collegamenti sicuri. Per istruzioni, vedere [Configure Global Settings for Safe Links Settings in Office 365 ATP](configure-global-settings-for-safe-links.md).

  Tuttavia, la protezione dei collegamenti sicuri per le app di Office 365 viene **applicata** solo agli utenti inclusi nei criteri dei collegamenti sicuri attivi. Se un utente non è incluso in un criterio di collegamenti sicuri attivo, l'utente non riceve la protezione dei collegamenti sicuri nelle app di Office 365 supportate.

  Per ulteriori informazioni sulla protezione dei collegamenti sicuri nelle app di Office 365, vedere la sezione [impostazioni collegamenti attendibili per office 365 Apps](#safe-links-settings-for-office-365-apps) più avanti in questo articolo.

In questo articolo sono incluse descrizioni dettagliate dei tipi di impostazioni dei collegamenti sicuri seguenti:

- **Impostazioni nei criteri collegamenti sicuri**: queste impostazioni si applicano solo agli utenti inclusi nei criteri specifici e le impostazioni potrebbero essere diverse tra i criteri. Tali impostazioni includono:

  - [Impostazioni dei collegamenti sicuri per i messaggi di posta elettronica](#safe-links-settings-for-email-messages)
  - [Impostazioni dei collegamenti sicuri per Microsoft Teams](#safe-links-settings-for-microsoft-teams)
  - ["Non riscrivere gli URL seguenti" nell'elenco dei criteri collegamenti sicuri](#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)

- **Impostazioni dei collegamenti sicuri globali**: queste impostazioni sono configurate globalmente e non nei criteri collegamenti sicuri. Tuttavia, le impostazioni si applicano solo agli utenti inclusi nei criteri dei collegamenti sicuri attivi. Tali impostazioni includono:

  - [Impostazioni dei collegamenti sicuri per le app di Office 365](#safe-links-settings-for-office-365-apps)
  - ["Blocca l'elenco degli URL seguenti" per i collegamenti sicuri](#block-the-following-urls-list-for-safe-links)

Nella tabella seguente vengono descritti gli scenari per i collegamenti sicuri in Microsoft 365 e le organizzazioni di Office 365 che includono ATP (in altre parole, la mancanza di licenze non è mai un problema negli esempi).

****

|Scenario|Risultato|
|---|---|
|Jean è un membro del reparto marketing. La protezione dei collegamenti sicuri per le app di Office 365 è attivata nelle impostazioni globali per i collegamenti sicuri e viene applicato un criterio di collegamenti sicuri che si applica ai membri del reparto marketing. Jean apre una presentazione di PowerPoint in un messaggio di posta elettronica e quindi fa clic su un URL nella presentazione.|Jean è protetto da collegamenti sicuri. <br/><br/> Jean è incluso in un criterio per i collegamenti sicuri e la protezione dei collegamenti sicuri per le app di Office 365 è attivata. <br/><br/> Per ulteriori informazioni sui requisiti per la protezione dei collegamenti sicuri nelle app di Office 365, vedere la sezione relativa alle [impostazioni dei collegamenti sicuri per office 365 Apps](#safe-links-settings-for-office-365-apps) più avanti in questo articolo.|
|L'organizzazione Microsoft 365 E5 di Chris non dispone di criteri collegamenti sicuri configurati. Chris riceve un messaggio di posta elettronica da un mittente esterno che contiene un URL di un sito Web dannoso che infine fa clic su.|Chris non è protetto da collegamenti sicuri. <br/><br/> Un amministratore deve creare almeno un criterio di collegamenti sicuri per tutti gli utenti per ottenere la protezione dei collegamenti sicuri nei messaggi di posta elettronica in ingresso. Chris deve essere incluso nelle condizioni di criteri per ottenere la protezione dei collegamenti sicuri.|
|Nell'organizzazione di Pat, nessun amministratore ha creato alcun criterio per i collegamenti sicuri, ma la protezione dei collegamenti sicuri per le app di Office 365 è attivata. Pat apre un documento di Word e fa clic su un URL nel file.|Pat non è protetto da collegamenti sicuri. <br/><br/> Anche se la protezione dei collegamenti sicuri per le app di Office 365 è attivata globalmente, Pat non è incluso in tutti i criteri per i collegamenti sicuri attivi, pertanto non è possibile applicare la protezione.|
|Nell'organizzazione di Lee, `https://tailspintoys.com` è configurato nell'elenco **blocca gli URL seguenti** nelle impostazioni globali per i collegamenti sicuri. Un criterio per i collegamenti sicuri che include Lee esiste già. Lee riceve un messaggio di posta elettronica che contiene l'URL `https://tailspintoys.com/aboutus/trythispage` . Lee fa clic sull'URL.|L'URL potrebbe essere bloccato automaticamente per Lee. dipende dalla voce URL nell'elenco e dal client di posta elettronica utilizzato Lee. Per ulteriori informazioni, vedere la sezione ["blocca gli URL seguenti" per i collegamenti sicuri](#block-the-following-urls-list-for-safe-links) più avanti in questo argomento.|
|Jamie e Julia lavorano entrambi per contoso.com. Molto tempo fa, gli amministratori hanno configurato i criteri per i collegamenti sicuri che si applicano sia a Jamie che a Julia. Jamie Invia un messaggio di posta elettronica a Julia, non sapendo che l'indirizzo di posta elettronica contiene un URL dannoso.|Julia è protetta da collegamenti sicuri **se** il criterio collegamenti sicuri che si applica a lei è configurato per essere applicato ai messaggi tra i destinatari interni. Per ulteriori informazioni, vedere la sezione relativa alle [impostazioni dei collegamenti sicuri per i messaggi di posta elettronica](#safe-links-settings-for-email-messages) più avanti in questo argomento.|

## <a name="safe-links-settings-for-email-messages"></a>Impostazioni dei collegamenti sicuri per i messaggi di posta elettronica

Collegamenti sicuri analizza la posta elettronica in arrivo per i collegamenti ipertestuali noti. Gli URL analizzati vengono riscritti utilizzando il prefisso URL standard Microsoft: `https://nam01.safelinks.protection.outlook.com` . Dopo che il collegamento è stato riscritto, viene analizzato per il contenuto potenzialmente dannoso.

Dopo che i collegamenti sicuri riscrivono un URL, l'URL rimane riscritto, anche se il messaggio è inoltrato o ha risposto. I collegamenti aggiuntivi aggiunti al messaggio inoltrato o risposto a non vengono riscritti.

Le impostazioni dei criteri collegamenti sicuri che si applicano ai messaggi di posta elettronica sono descritte nel seguente elenco:

- **Selezionare l'azione per gli URL potenzialmente dannosi sconosciuti nei messaggi**: attiva o disattiva l'analisi dei collegamenti sicuri nei messaggi di posta elettronica. Il valore consigliato è **on**. Se si attiva questa impostazione, vengono riportate le azioni seguenti.

  - L'analisi dei collegamenti sicuri è abilitata in Outlook (C2R) in Windows.
  - Gli URL vengono riscritti e gli utenti vengono instradati attraverso la protezione dei collegamenti sicuri quando fanno clic su URL nei messaggi.
  - Quando si fa clic su, gli URL vengono controllati in base a un elenco di URL dannosi noti e all' [elenco "blocca gli URL seguenti"](#block-the-following-urls-list-for-safe-links).
  - Gli URL che non dispongono di una reputazione valida vengono detonati in modo asincrono in background.

- **Applicare l'analisi degli URL in tempo reale per collegamenti e collegamenti sospetti che puntano a file**: consente l'analisi in tempo reale dei collegamenti, inclusi i collegamenti nei messaggi di posta elettronica che puntano al contenuto scaricabile. Il valore consigliato è abilitato.

  - **Attendere il completamento dell'analisi degli URL prima di recapitare il messaggio**:

    - Enabled: i messaggi che contengono URL vengono mantenuti finché l'analisi non è terminata. I messaggi vengono recapitati solo dopo che gli URL sono stati confermati come attendibili. Questo è il valore consigliato.
    - Disabled: se l'analisi dell'URL non può essere completata, recapitare il messaggio.

- **Applicare collegamenti sicuri ai messaggi di posta elettronica inviati all'interno dell'organizzazione**: Abilita o Disabilita l'analisi dei collegamenti sicuri sui messaggi inviati tra i mittenti interni e i destinatari interni all'interno della stessa organizzazione di Exchange Online. Il valore consigliato è abilitato.

- **Non tenere conto dei clic degli utenti**: Abilita o Disabilita l'archiviazione di collegamenti sicuri fare clic su dati per gli URL su cui si è fatto clic nei messaggi di posta elettronica. Il valore consigliato consiste nel lasciare deselezionata questa impostazione (per tenere presenti gli scatti degli utenti).

  URL fare clic su rilevamento per i collegamenti nei messaggi di posta elettronica inviati tra i mittenti interni e i destinatari interni non è attualmente supportato.

- **Non consentire agli utenti di fare clic sull'URL originale**: consente o blocca gli utenti facendo clic sulla [pagina di avviso](#warning-pages-from-safe-links) nell'URL originale. Il valore recommend è abilitato.

- **Non riscrivere gli URL seguenti**: consente di lasciare gli URL così come sono. Mantiene un elenco personalizzato di URL sicuri che non devono essere analizzati. L'elenco è univoco per tutti i criteri collegamenti sicuri. Per ulteriori informazioni sull'elenco non **riscrivere gli URL seguenti** , vedere la sezione ["non riscrivere gli URL seguenti" negli elenchi dei criteri collegamenti sicuri](#do-not-rewrite-the-following-urls-lists-in-safe-links-policies) più avanti in questo articolo.

Per ulteriori informazioni sui valori consigliati per le impostazioni dei criteri standard e rigorosi per i criteri collegamenti sicuri, vedere [impostazioni dei criteri collegamenti sicuri](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings).

- **Filtri destinatario**: è necessario specificare le condizioni del destinatario e le eccezioni che determinano gli utenti a cui si applica il criterio. È possibile utilizzare queste proprietà per le condizioni e le eccezioni:

  - **Il destinatario è**
  - **Il dominio del destinatario è**
  - **Il destinatario è un membro di**

  È possibile utilizzare solo un'eccezione una volta, ma la condizione o l'eccezione può contenere più valori. Più valori della stessa condizione o eccezione utilizzano la logica OR (ad esempio, _\<recipient1\>_ o _\<recipient2\>_). Condizioni o eccezioni diverse utilizzano la logica AND (ad esempio, _\<recipient1\>_ e _\<member of group 1\>_).

- **Priorità**: se si creano più criteri, è possibile specificare l'ordine in cui sono stati applicati. Nessun criterio può avere la stessa priorità e l'elaborazione dei criteri termina dopo l'applicazione del primo criterio.

  Per altre informazioni sull'ordine di precedenza e su come vengono valutati e applicati multipli criteri, vedere [Ordine e precedenza della protezione della posta elettronica](how-policies-and-protections-are-combined.md).

### <a name="how-safe-links-works-in-email-messages"></a>Funzionamento dei collegamenti sicuri nei messaggi di posta elettronica

A livello elevato, ecco come funziona la protezione dei collegamenti sicuri sugli URL nei messaggi di posta elettronica:

1. Tutti i messaggi di posta elettronica passano attraverso EOP, dove il protocollo IP (Internet Protocol) e filtri busta, protezione antimalware basata sulle firme, filtri anti-spam e antispam prima che il messaggio venga recapitato alla cassetta postale del destinatario.

2. L'utente apre il messaggio nella propria cassetta postale e fa clic su un URL del messaggio.

3. Collegamenti attendibili verifica immediatamente l'URL prima dell'apertura del sito Web:

   - Se l'URL è incluso nell'elenco **blocca gli URL seguenti** , verrà visualizzato un [avviso URL bloccato](#blocked-url-warning) .

   - Se l'URL punta a un sito Web che è stato determinato come dannoso, verrà aperta una pagina di avviso per il [sito Web dannoso](#malicious-website-warning) (o una pagina di avviso diversa).

   - Se l'URL punta a un file scaricabile e l'opzione **applica scansione URL in tempo reale per collegamenti sospetti e collegamenti che puntano a file** è abilitata nei criteri che si applicano all'utente, il file scaricabile viene controllato.

   - Se l'URL è determinato per la sicurezza, il sito Web verrà aperto.

## <a name="safe-links-settings-for-microsoft-teams"></a>Impostazioni dei collegamenti sicuri per Microsoft Teams

> [!IMPORTANT]
> A marzo 2020, questa funzionalità è in anteprima ed è disponibile solo per i membri del Microsoft teams Technology Adoption Program (TAP).

È possibile abilitare o disabilitare la protezione dei collegamenti sicuri per Microsoft Teams nei criteri collegamenti sicuri. In particolare, è possibile utilizzare l'impostazione **selezionare l'azione per gli URL sconosciuti o potenzialmente dannosi all'interno di Microsoft teams** . Il valore consigliato è **on**.

Le seguenti impostazioni dei criteri collegamenti sicuri che si applicano ai collegamenti nei messaggi di posta elettronica si applicano anche ai collegamenti nei team:

- **Applicazione dell'analisi degli URL in tempo reale per collegamenti e collegamenti sospetti che puntano a file**
- **Non monitorare i clic dell'utente**
- **Non consentire agli utenti di fare clic sull'URL originale**

Queste impostazioni vengono spiegate nelle [impostazioni dei collegamenti sicuri precedenti per i messaggi di posta elettronica](#safe-links-settings-for-email-messages) .

Dopo aver attivato la protezione dei collegamenti sicuri per Microsoft teams, gli URL nei team vengono controllati in base a un elenco di collegamenti dannosi noti quando l'utente protetto fa clic sul collegamento (protezione del tempo di clic). Gli URL non vengono riscritti. Se si trova un collegamento dannoso, gli utenti avranno le seguenti esperienze:

- Se il collegamento è stato selezionato in una conversazione di Team, in una chat di gruppo o nei canali, la pagina di avviso come illustrato nella schermata seguente viene visualizzata nel Web browser predefinito.
- Se il collegamento è stato selezionato da una scheda bloccata, la pagina di avviso viene visualizzata nell'interfaccia teams all'interno di tale scheda. L'opzione per aprire il collegamento in un Web browser è disabilitata per motivi di sicurezza.
- A seconda del modo in cui non è possibile **consentire agli utenti di fare clic sull'impostazione di un URL originale** nel criterio, l'utente potrà o non sarà autorizzato a fare clic sull'URL originale (**continuare comunque (non consigliato)** nello screenshot). È consigliabile abilitare l'impostazione non **consentire agli utenti di fare clic su all'URL originale** in modo che gli utenti non possano fare clic sull'URL originale.

Se l'utente che ha inviato il collegamento non è incluso in un criterio per i collegamenti sicuri in cui è abilitata la protezione dei team, l'utente è libero di fare clic sull'URL originale nel computer o nel dispositivo.

![Una pagina collegamenti sicuri per i team che segnalano un collegamento dannoso.](../../media/tp-safe-links-for-teams-malicious.png)

Se si fa clic sul pulsante **Torna indietro** nella pagina avviso, la pagina verrà chiusa o potrebbe verificarsi una pagina vuota che può essere chiusa dagli utenti. Tuttavia, facendo nuovamente clic sul collegamento originale, i collegamenti sicuri verranno rianalizzati nell'URL, in modo che la pagina di avviso riapparirà.

### <a name="how-safe-links-works-in-teams"></a>Funzionamento di collegamenti sicuri nei team

A livello elevato, ecco come funziona la protezione dei collegamenti sicuri per gli URL in Microsoft teams:

1. Un utente avvia l'app teams.

2. Microsoft 365 verifica che l'organizzazione dell'utente includa Office 365 ATP e che l'utente sia incluso in un criterio di collegamenti sicuri attivo in cui è abilitata la protezione per Microsoft teams.

3. Gli URL vengono convalidati al momento di fare clic per l'utente nelle chat, nelle chat di gruppo, nei canali e nelle schede.

## <a name="safe-links-settings-for-office-365-apps"></a>Impostazioni dei collegamenti sicuri per le app di Office 365

Protezione dei collegamenti sicuri per le app di Office 365 verifica i collegamenti nei documenti di Office, non i collegamenti nei messaggi di posta elettronica, ma è possibile controllare i collegamenti nei documenti di Office allegati nei messaggi di posta elettronica dopo l'apertura del documento.

Protezione dei collegamenti sicuri per le app di Office 365 sono necessari i requisiti client seguenti:

- Microsoft 365 Apps o Microsoft 365 Business Premium.
  - Versioni correnti di Word, Excel e PowerPoint su Windows, Mac o in un Web browser.
  - App di Office su dispositivi iOS o Android.
  - Visio su Windows.
  - OneNote in un Web browser.

- Le app di Office 365 sono configurate per l'utilizzo dell'autenticazione moderna. Per ulteriori informazioni, vedere [come funziona l'autenticazione moderna per le app client di office 2013, office 2016 e office 2019](https://docs.microsoft.com/microsoft-365/enterprise/modern-auth-for-office-2013-and-2016).

- Gli utenti hanno eseguito l'accesso utilizzando gli account di lavoro o della scuola. Per ulteriori informazioni, vedere [accedere a Office](https://support.microsoft.com/office/b9582171-fd1f-4284-9846-bdd72bb28426).

È possibile configurare la protezione dei collegamenti sicuri per le app di Office 365 nelle impostazioni globali per i collegamenti sicuri e non nei criteri collegamenti sicuri. Tuttavia, per poter applicare la protezione dei collegamenti sicuri per le app di Office 365, l'utente che apre il documento di Office e fa clic sul collegamento deve essere incluso in un criterio di collegamenti sicuri attivo.

Le seguenti impostazioni dei collegamenti sicuri sono disponibili per le app di Office 365:

- **Applicazioni di office 365**: consente di abilitare o disabilitare l'analisi dei collegamenti sicuri nelle app di Office 365 supportate. Il valore predefinito e **consigliato è attivato**.

- **Non tenere conto di quando gli utenti fanno clic su collegamenti sicuri**: Abilita o Disabilita l'archiviazione dei collegamenti sicuri fare clic su dati per gli URL su cui si fa clic nelle versioni desktop Word, Excel, PowerPoint e Visio. Il valore consigliato è **disattivato**, il che significa che i clic dell'utente vengono registrati.

- **Non consentire agli utenti di fare clic su collegamenti sicuri con l'URL originale**: consente o blocca gli utenti di fare clic sulla [pagina di avviso](#warning-pages-from-safe-links) nell'URL originale nelle versioni desktop di Word, Excel, PowerPoint e Visio. Il valore predefinito e **consigliato è attivato**.

Per configurare le impostazioni dei collegamenti sicuri per le app di Office 365, vedere [Configure Safe Links Protection for office 365 Apps](configure-global-settings-for-safe-links.md#configure-safe-links-protection-for-office-365-apps-in-the-security--compliance-center).

Per ulteriori informazioni sui valori consigliati per le impostazioni dei criteri standard e rigorose, vedere [Global Settings for Safe Links](recommended-settings-for-eop-and-office365-atp.md#global-settings-for-safe-links).

### <a name="how-safe-links-works-in-office-365-apps"></a>Funzionamento di collegamenti sicuri nelle app di Office 365

A livello elevato, ecco come funziona la protezione dei collegamenti sicuri per gli URL nelle app di Office 365. Le app di Office 365 supportate sono descritte nella sezione precedente.

1. Un utente accede utilizzando l'account aziendale o dell'Istituto di istruzione in un'organizzazione che include Microsoft 365 Apps o Microsoft 365 Business Premium.

2. L'utente viene aperto e fa clic su un collegamento di un documento di Office in un'app di Office supportata.

3. Collegamenti attendibili verifica immediatamente l'URL prima di aprire il sito Web di destinazione:

   - Se l'URL è incluso nell'elenco che ignora l'analisi dei collegamenti sicuri ( **blocca l'elenco degli URL seguenti** ) viene visualizzata una pagina di avviso per gli [URL bloccati](#blocked-url-warning) .

   - Se l'URL punta a un sito Web che è stato determinato come dannoso, verrà aperta una pagina di avviso per il [sito Web dannoso](#malicious-website-warning) (o una pagina di avviso diversa).

   - Se l'URL punta a un file scaricabile e il criterio collegamenti sicuri applicato all'utente è configurato per eseguire l'analisi dei collegamenti al contenuto scaricabile (**applicare l'analisi degli URL in tempo reale per collegamenti sospetti e collegamenti che puntano ai file**), viene controllato il file scaricabile.

   - Se l'URL è considerato sicuro, l'utente viene reindirizzato al sito Web.

   - Se l'analisi dei collegamenti sicuri non è in grado di essere completata, la protezione dei collegamenti sicuri non viene attivata. Nei client di Office Desktop, l'utente verrà avvisato prima di procedere con il sito Web di destinazione.

> [!NOTE]
> All'inizio di ogni sessione potrebbero essere necessari alcuni secondi per verificare che l'utente disponga di collegamenti sicuri per Office abilitato.

## <a name="block-the-following-urls-list-for-safe-links"></a>"Blocca l'elenco degli URL seguenti" per i collegamenti sicuri

Il **blocco l'elenco degli URL seguenti** definisce i collegamenti che vengono sempre bloccati dall'analisi dei collegamenti sicuri nelle posizioni seguenti:

- Messaggi di posta elettronica.
- Documenti nelle app di Office 365 in Windows e Mac.
- Documenti in Office per iOS e Android.

Quando un utente di un criterio collegamenti sicuri attivo fa clic su un collegamento bloccato in un'app supportata, viene visualizzato nella pagina [avviso bloccato URL](#blocked-url-warning) .

È possibile configurare l'elenco di URL nelle impostazioni globali per i collegamenti sicuri. Per istruzioni, vedere [Configure the "Block The seguente URLs" list](configure-global-settings-for-safe-links.md#configure-the-block-the-following-urls-list-in-the-security--compliance-center).

**Note**:

- Per un elenco veramente universale di URL bloccati ovunque, vedere [gestire gli URL nell'elenco Consenti/blocca tenant](tenant-allow-block-list.md).

- Limiti
  - Il numero massimo di voci è 500.
  - La lunghezza massima di una voce è di 128 caratteri.
  - Tutte le voci non possono superare 10.000 caratteri.

- Non includere una barra ( `/` ) alla fine dell'URL. Utilizzare, ad esempio `https://www.contoso.com` , Not `https://www.contoso.com/` .

- Un solo dominio URL (ad esempio `contoso.com` o `tailspintoys.com` ) BLOCCHERÀ qualsiasi URL contenente il dominio.

- È possibile bloccare un sottodominio senza bloccare il dominio completo. Ad esempio, `toys.contoso.com*` blocca qualsiasi URL contenente il sottodominio, ma non blocca gli URL che contengono il dominio completo `contoso.com` .

- È possibile includere fino a tre caratteri jolly ( `*` ) per voce URL.

### <a name="entry-syntax-for-the-block-the-following-urls-list"></a>Sintassi voce per l'elenco "blocca gli URL seguenti"

Gli esempi dei valori che è possibile immettere e i relativi risultati sono descritti nella tabella seguente:

****

|Valore|Risultato|
|---|---|
|`contoso.com` <br/> oppure <br/> `*contoso.com*`|Blocca il dominio, i sottodomini e i percorsi. Ad esempio, `https://www.contoso.com` `https://sub.contoso.com` e `https://contoso.com/abc` sono bloccati.|
|`https://contoso.com/a`|Blocca `https://contoso.com/a` ma non altri sottopercorsi come `https://contoso.com/a/b` .|
|`https://contoso.com/a*`|Blocchi `https://contoso.com/a` e sottopercorsi aggiuntivi come `https://contoso.com/a/b` .|
|`https://toys.contoso.com*`|Blocca un sottodominio ( `toys` in questo esempio) ma consente di fare clic su altri URL di dominio (come `https://contoso.com` or `https://home.contoso.com` ).|
|

## <a name="do-not-rewrite-the-following-urls-lists-in-safe-links-policies"></a>"Non riscrivere gli URL seguenti" nell'elenco dei criteri collegamenti sicuri

> [!NOTE]
> Se nell'organizzazione vengono utilizzati criteri dei collegamenti sicuri, gli elenchi di **URL seguenti non verranno riscritti** come l'unico metodo supportato per i test di phishing di terze parti.

Tutti i criteri collegamenti sicuri contengono un non **riscrivere l'elenco URL seguente** che è possibile utilizzare per specificare gli URL non riscritti dall'analisi dei collegamenti sicuri. In altre parole, l'elenco consente agli utenti inclusi nel criterio di accedere agli URL specificati che altrimenti verrebbero bloccati da collegamenti sicuri. È possibile configurare elenchi diversi in criteri di collegamenti sicuri diversi. L'elaborazione dei criteri si interrompe dopo l'applicazione del primo criterio (probabilmente la priorità più alta) all'utente. Pertanto, solo uno non **riscrivere l'elenco URL seguente** viene applicato a un utente che è incluso in più criteri di collegamenti sicuri attivi.

Per aggiungere voci all'elenco nei criteri dei collegamenti sicuri nuovi o esistenti, vedere [creare criteri](set-up-atp-safe-links-policies.md#use-the-security--compliance-center-to-create-safe-links-policies) collegamenti sicuri o [modificare i criteri collegamenti sicuri](set-up-atp-safe-links-policies.md#use-the-security--compliance-center-to-modify-safe-links-policies).

**Note**:

- I client seguenti non riconoscono la non **riscrittura degli elenchi di URL seguenti** nei criteri collegamenti sicuri. Gli utenti inclusi nelle polizie possono essere bloccati dall'accesso agli URL in base ai risultati dell'analisi dei collegamenti sicuri nei client:

  - Microsoft Teams
  - Office Web Apps

  Per un elenco veramente universale di URL consentiti in tutto il mondo, vedere [Manage URLs nell'elenco tenant Allow/Block](tenant-allow-block-list.md).

- Valutare l'aggiunta di URL interni di uso comune all'elenco per migliorare l'esperienza dell'utente. Ad esempio, se si dispone di servizi locali, come Skype for business o SharePoint, è possibile aggiungere tali URL per escluderli dall'analisi.

- Se si dispone già di **non riscrivere le voci degli URL seguenti** nei criteri dei collegamenti sicuri, controllare gli elenchi e aggiungere i caratteri jolly come richiesto. Ad esempio, l'elenco contiene una voce come `https://contoso.com/a` e successivamente si decide di includere i sottopercorsi come `https://contoso.com/a/b` . Invece di aggiungerne una nuova, aggiungere un carattere jolly alla voce esistente in modo che diventi `https://contoso.com/a/*` .

- È possibile includere fino a tre caratteri jolly ( `*` ) per voce URL. I caratteri jolly includono in modo esplicito prefissi o sottodomini. Ad esempio, la voce `contoso.com` non è la stessa `*.contoso.com/*` , perché `*.contoso.com/*` consente agli utenti di visitare i sottodomini e i percorsi nel dominio specificato.

### <a name="entry-syntax-for-the-do-not-rewrite-the-following-urls-list"></a>Sintassi voce per l'elenco "non riscrivere gli URL seguenti"

Gli esempi dei valori che è possibile immettere e i relativi risultati sono descritti nella tabella seguente:

****

|Valore|Risultato|
|---|---|
|`contoso.com`|Consente l'accesso `https://contoso.com` ma non ai sottodomini o ai percorsi.|
|`*.contoso.com/*`|Consente l'accesso a un dominio, a sottodomini e a percorsi (ad esempio,,, `https://www.contoso.com` `https://www.contoso.com` `https://maps.contoso.com` o `https://www.contoso.com/a` ). <br/><br/> Questa voce è intrinsecamente migliore di `*contoso.com*` , perché non consente siti potenzialmente fraudolenti, come `https://www.falsecontoso.com` o `https://www.false.contoso.completelyfalse.com`|
|`https://contoso.com/a`|Consente di accedere `https://contoso.com/a` , ma non di sottopercorsi come `https://contoso.com/a/b`|
|`https://contoso.com/a/*`|Consente l'accesso `https://contoso.com/a` e i sottopercorsi come `https://contoso.com/a/b`|
|

## <a name="warning-pages-from-safe-links"></a>Pagine di avviso da collegamenti sicuri

In questa sezione sono inclusi esempi delle diverse pagine di avviso attivate dalla protezione dei collegamenti sicuri quando si fa clic su un URL.

Si noti che sono state aggiornate diverse pagine di avviso. Se non si vedono già le pagine aggiornate, sarà presto possibile. Nelle pagine aggiornate sono disponibili una nuova combinazione di colori, maggiori dettagli e la possibilità di procedere a un sito nonostante gli avvisi e i suggerimenti specificati.

### <a name="scan-in-progress-notification"></a>Notifica di analisi in corso

L'URL selezionato viene analizzato tramite collegamenti sicuri. Potrebbe essere necessario attendere alcuni istanti prima di riprovare il collegamento.

![Notifica "il collegamento è in fase di scansione"](../../media/ee8dd5ed-6b91-4248-b054-12b719e8d0ed.png)

La pagina di notifica originale è simile alla seguente:

![Notifica originale "il collegamento è in fase di scansione"](../../media/04368763-763f-43d6-94a4-a48291d36893.png)

### <a name="suspicious-message-warning"></a>Avviso del messaggio sospetto

L'URL su cui si è fatto clic è stato in un messaggio di posta elettronica analogo ad altri messaggi sospetti. Si consiglia di controllare il messaggio di posta elettronica prima di procedere con il sito.

![Avviso "è stato fatto clic su un collegamento da un messaggio sospetto"](../../media/33f57923-23e3-4b0f-838b-6ad589ba897b.png)

### <a name="phishing-attempt-warning"></a>Avviso del tentativo di phishing

L'URL su cui si è fatto clic è stato in un messaggio di posta elettronica identificato come un attacco di phishing. Di conseguenza, tutti gli URL del messaggio di posta elettronica vengono bloccati. Si consiglia di non procedere al sito.

!["Avviso il collegamento è stato selezionato da un messaggio di phishing"](../../media/6e544a28-0604-4821-aba6-d5a57bb917e5.png)

### <a name="malicious-website-warning"></a>Avviso per il sito Web dannoso

L'URL selezionato punta a un sito che è stato identificato come dannoso. Si consiglia di non procedere al sito.

![Avviso "questo sito Web è classificato come dannoso"](../../media/058883c8-23f0-4672-9c1c-66b084796177.png)

La pagina di avviso originale è simile alla seguente:

![Avviso originale "questo sito Web è stato classificato come dannoso"](../../media/b9efda09-6dd8-46ef-82cb-56e4d538b8f5.png)

### <a name="blocked-url-warning"></a>Avviso URL bloccato

L'URL su cui è stato fatto clic è stato bloccato manualmente da un amministratore dell'organizzazione ( **blocca l'elenco degli URL seguenti** nelle impostazioni globali per i collegamenti sicuri). Il collegamento non è stato analizzato da collegamenti sicuri perché è stato bloccato manualmente.

Sono diversi i motivi per cui un amministratore bloccherà manualmente URL specifici. Se si ritiene che il sito non debba essere bloccato, contattare l'amministratore.

![Avviso "questo sito Web è stato bloccato dall'amministratore"](../../media/6b4bda2d-a1e6-419e-8b10-588e83c3af3f.png)

La pagina di avviso originale è simile alla seguente:

![Avviso originale "questo sito Web è stato bloccato per il criterio URL dell'organizzazione"](../../media/3d6ba028-30bf-45fc-958e-d3aad3defc83.png)

### <a name="error-warning"></a>Avviso di errore

Si è verificato un errore e l'URL non può essere aperto.

![Avviso "la pagina in cui si sta tentando di accedere non può essere caricata"](../../media/2f7465a4-1cf4-4c1c-b7d4-3c07e4b795b4.png)

La pagina di avviso originale è simile alla seguente:

![Avviso originale "Questa pagina Web non è stato caricato"](../../media/9aaa4383-2f23-48be-bdaa-8efbcb2acc70.png)
