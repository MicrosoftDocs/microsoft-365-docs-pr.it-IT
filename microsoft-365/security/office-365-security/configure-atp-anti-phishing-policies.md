---
title: Configurare i criteri anti-phishing in Microsoft Defender per Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Gli amministratori possono imparare a creare, modificare ed eliminare i criteri anti-phishing avanzati disponibili nelle organizzazioni con Microsoft Defender per Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d75455df972e9db0ef1cf4bbeba9f3b78b11002b
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/03/2021
ms.locfileid: "50406199"
---
# <a name="configure-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Configurare i criteri anti-phishing in Microsoft Defender per Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Microsoft Defender per Office 365 piano 1 e piano 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

I criteri anti-phishing in [Microsoft Defender per Office 365](office-365-atp.md) consentono di proteggere l'organizzazione da attacchi di phishing dannosi basati sulla rappresentazione e altri tipi di attacchi di phishing. Per ulteriori informazioni sulle differenze tra i criteri anti-phishing in Exchange Online Protection (EOP) e i criteri anti-phishing in Microsoft Defender per Office 365, vedere [Protezione anti-phishing.](anti-phishing-protection.md)

Gli amministratori possono visualizzare, modificare e configurare (ma non eliminare) il criterio anti-phishing predefinito. Per una maggiore granularità, è inoltre possibile creare criteri anti-phishing personalizzati che si applicano a utenti, gruppi o domini specifici nell'organizzazione. I criteri personalizzati hanno sempre la precedenza sul criterio predefinito, ma non è possibile modificarne la priorità (in funzione).

È possibile configurare i criteri anti-phishing nel Centro sicurezza & conformità o in PowerShell di Exchange Online.

Per informazioni sulla configurazione dei criteri di anti-phishing più limitati disponibili nelle organizzazioni di Exchange Online Protection (ovvero le organizzazioni senza Microsoft Defender per Office 365), vedere Configurare i criteri [anti-phishing in EOP.](configure-anti-phishing-policies-eop.md)

Gli elementi di base di un criterio anti-phishing sono:

- **Il criterio anti-phishing**: specifica le protezioni anti-phishing da abilitare o disabilitare e le azioni da applicare.
- **La regola anti-phish**: specifica la priorità e i filtri destinatario (a chi si applica il criterio) per un criterio anti-phish.

La differenza tra questi due elementi non è ovvia quando si gestiscono i criteri anti-phishing nel Centro sicurezza & conformità:

- Quando crei un criterio, stai creando contemporaneamente una regola anti-phish e il criterio anti-phish associato usando lo stesso nome per entrambi.
- Quando si modifica un criterio, le impostazioni relative al nome, alla priorità, all'attivazione o alla disabilitazione e i filtri destinatari modificano la regola anti-phish. Tutte le altre impostazioni modificano il criterio anti-phish associato.
- Quando si rimuove un criterio, vengono rimossi la regola anti-phish e il criterio anti-phish associato.

In PowerShell di Exchange Online, il criterio e la regola vengono gestiti separatamente. Per ulteriori informazioni, vedere la sezione Utilizzare PowerShell di Exchange Online per configurare i criteri [anti-phishing in Microsoft Defender per Office 365](#use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365) più avanti in questo articolo.

Ogni organizzazione di Microsoft Defender per Office 365 dispone di un criterio anti-phishing predefinito denominato Office365 AntiPhish Default con queste proprietà:

- Il criterio viene applicato a tutti i destinatari nell'organizzazione, anche se al criterio non è associata alcuna regola anti-phish (filtri destinatari).
- Il valore personalizzato della priorità del criterio è **Minore** e non può essere modificato (il criterio viene sempre applicato per ultimo). Qualsiasi criterio personalizzato creato avrà sempre una priorità più alta.
- Il criterio è quello predefinito (la proprietà **IsDefault** contiene il valore `True`), e non è possibile eliminarlo.

Per aumentare l'efficacia della protezione anti-phishing in Microsoft Defender per Office 365, è possibile creare criteri anti-phishing personalizzati con impostazioni più rigide applicate a utenti o gruppi di utenti specifici.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare?

- Aprire il Centro sicurezza e conformità in <https://protection.office.com/>. Per passare direttamente alla pagina **anti-phishing di ATP,** utilizzare <https://protection.office.com/antiphishing> .

- Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

- Per eseguire le procedure descritte in questo articolo, è necessario disporre delle autorizzazioni in **Exchange Online:**
  - Per aggiungere, modificare ed eliminare criteri anti-phishing, è necessario essere membri dei gruppi di ruoli **Gestione** organizzazione o Amministratore **sicurezza.**
  - Per l'accesso in sola lettura ai criteri anti-phishing, è  necessario essere membri dei gruppi di ruoli **Lettore** globale o Lettore di <sup>\*</sup> sicurezza.

  Per ulteriori informazioni, vedere [Autorizzazioni in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo).

  **Note**:

  - L'aggiunta di utenti al ruolo di Azure Active Directory corrispondente nell'interfaccia di amministrazione di Microsoft 365 offre agli utenti le autorizzazioni e le autorizzazioni necessarie per altre funzionalità di Microsoft 365.  Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](../../admin/add-users/about-admin-roles.md).
  - Il **gruppo di ruoli Gestione organizzazione** di sola visualizzazione in Exchange [Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) consente inoltre l'accesso in sola lettura alla <sup>\*</sup> funzionalità.
  - <sup>\*</sup> Nel Centro sicurezza & conformità, l'accesso in sola lettura consente agli utenti di visualizzare le impostazioni dei criteri anti-phishing personalizzati. Gli utenti di sola lettura non possono visualizzare le impostazioni nel criterio anti-phishing predefinito.

- Per le impostazioni consigliate per i criteri anti-phishing in Microsoft Defender per Office 365, vedere Criteri anti-phishing in Defender per le impostazioni [di Office 365.](recommended-settings-for-eop-and-office365-atp.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365)

- Consentire fino a 30 minuti per l'applicazione di un criterio nuovo o aggiornato.

- Per informazioni su dove vengono applicati i criteri anti-phishing nella pipeline di filtro, vedere [Ordine e precedenza della protezione della posta elettronica.](how-policies-and-protections-are-combined.md)

## <a name="use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Usare il Centro sicurezza & conformità per creare criteri anti-phishing in Microsoft Defender per Office 365

La creazione di un criterio anti-phishing personalizzato nel Centro sicurezza & conformità crea contemporaneamente la regola anti-phishing e il criterio anti-phishing associato usando lo stesso nome per entrambi.

Quando si crea un criterio anti-phishing, è possibile specificare solo il nome, la descrizione e il filtro destinatario che identifica a chi si applica il criterio. Dopo aver creato il criterio, è possibile modificare il criterio per modificare o rivedere le impostazioni di anti-phishing predefinite.

1. Nel Centro sicurezza & conformità passare **a** Anti-phishing dei criteri di gestione delle \>  \> **minacce ATP.**

2. Nella pagina **Anti-phishing** fare clic su **Crea.**

3. Verrà visualizzata la procedura guidata Crea un nuovo **criterio anti-phishing.** Nella pagina **Assegnare un nome al** criterio configurare le impostazioni seguenti:

   - **Nome**: immettere un nome univoco descrittivo per il criterio.

   - **Descrizione**: immettere una descrizione opzionale per il criterio.

   Al termine dell'operazione, fare clic su **Avanti**.

4. Nella pagina **Applicato a** visualizzata, identificare i destinatari interni a cui si applica il criterio.

   È possibile utilizzare una condizione o un'eccezione solo una volta, ma è possibile specificare più valori per la condizione o l'eccezione. Più valori della stessa condizione o eccezione utilizzano la logica OR (ad esempio, _\<recipient1\>_ o _\<recipient2\>_). Condizioni o eccezioni diverse utilizzano la logica AND (ad esempio, _\<recipient1\>_ e _\<member of group 1\>_).

   Fare **clic su Aggiungi condizione.** Nell'elenco a discesa visualizzato selezionare una condizione in **Applicato se:**

   - **Il destinatario è**: specifica una o più cassette postali, utenti di posta o contatti di posta nell'organizzazione.
   - **Il destinatario è membro di**: Specifica uno o più gruppi nell'organizzazione.
   - **Il dominio del destinatario** è : specifica i destinatari in uno o più domini accettati configurati nell'organizzazione.

   Dopo aver selezionato la condizione, viene visualizzato un elenco a discesa corrispondente con **una qualsiasi di queste** caselle.

   - Fare clic nella casella e scorrere l'elenco dei valori da selezionare.
   - Fare clic nella casella e iniziare a digitare per filtrare l'elenco e selezionare un valore.
   - Per aggiungere ulteriori valori, fare clic in un'area vuota della casella.
   - Per rimuovere singole voci, fare **clic sull'icona** ![ Rimuovi sul ](../../media/scc-remove-icon.png) valore.
   - Per rimuovere l'intera condizione, fare **clic sull'icona** ![ Rimuovi nella ](../../media/scc-remove-icon.png) condizione.

   Per aggiungere una condizione aggiuntiva, fare clic **su Aggiungi una condizione** e selezionare un valore rimanente in Applicato **se.**

   Per aggiungere eccezioni, fare clic **su Aggiungi una condizione** e selezionare un'eccezione in Tranne **se**. Impostazioni e comportamento sono equivalenti alle condizioni.

   Al termine dell'operazione, fare clic su **Avanti**.

5. Nella pagina **Controlla le impostazioni** visualizzata, rivedere le impostazioni. È possibile fare **clic su** Modifica per ogni impostazione per modificarla.

   Al termine, fare clic **su Crea questo criterio.**

6. Fare **clic su OK** nella finestra di dialogo di conferma visualizzata.

Dopo aver creato il criterio anti-phishing con queste impostazioni generali, seguire le istruzioni nella sezione successiva per configurare le impostazioni di protezione nel criterio.

## <a name="use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Usare il Centro sicurezza & conformità per modificare i criteri anti-phishing in Microsoft Defender per Office 365

Utilizzare le procedure seguenti per modificare i criteri anti-phishing: un nuovo criterio creato dall'utente o criteri esistenti già personalizzati.

1. Se non si è già presenti, aprire il Centro sicurezza  & conformità e passare a Criteri di gestione delle minacce \>  \> **anti-phishing ATP.**

2. Selezionare il criterio anti-phishing personalizzato che si desidera modificare. Se è già selezionato, deselezionalo e selezionalo di nuovo.

3. Verrà **visualizzato \<name\> il riquadro a comparsa** Modifica criterio. Facendo **clic su** Modifica in qualsiasi sezione è possibile accedere alle impostazioni di tale sezione.

   - I passaggi seguenti vengono presentati nell'ordine in cui vengono visualizzate le sezioni, ma non sono sequenziali (è possibile selezionare e modificare le sezioni in qualsiasi ordine).

   - Dopo aver fatto clic su Modifica **in** una sezione, le impostazioni disponibili vengono presentate in un  formato di procedura guidata,  ma è possibile passare all'interno delle pagine in qualsiasi ordine e fare clic su Salva in qualsiasi pagina (o  ![ ](../../media/scc-remove-icon.png) **\<name\>** sull'icona Annulla o Chiudi chiudi per tornare alla pagina Modifica i criteri (non è necessario visitare l'ultima pagina della procedura guidata per salvare o uscire).

4. **Impostazione dei criteri:** **fare** clic su Modifica per modificare le stesse impostazioni disponibili quando [è](#use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365) stato creato il criterio nella sezione precedente:

   - **Nome**
   - **Descrizione**
   - **Applicato a**
   - **Rivedere le impostazioni**

   Al termine, fare clic su **Salva** in qualsiasi pagina.

5. **Rappresentazione:** fare **clic su Modifica** per modificare i mittenti protetti e i domini protetti nel criterio. Queste impostazioni sono una condizione per il criterio che identifica i mittenti falsificati da cercare (singolarmente o per dominio) nell'indirizzo del mittente dei messaggi in ingresso. Per ulteriori informazioni, vedere [Impostazioni di rappresentazione nei criteri anti-phishing in Microsoft Defender per Office 365.](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)

   - **Aggiungere utenti da proteggere:** il valore predefinito è **Disattivato.** Per attivarlo, far scorrere l'interruttore su **Attivato** e quindi fare **clic** sul pulsante Aggiungi utente visualizzato.

     Nel riquadro **a comparsa** Aggiungi utente visualizzato configurare i valori seguenti:

     - **Indirizzo di posta elettronica**:

       - Fare clic nella casella e scorrere l'elenco degli utenti da selezionare.
       - Fare clic nella casella e iniziare a digitare per filtrare l'elenco e selezionare un utente.
       - Per rimuovere una voce, fare **clic sull'icona** ![ Rimuovi ](../../media/scc-remove-icon.png) nell'utente.

     - **Nome:** questo valore viene popolato in base all'indirizzo di posta elettronica selezionato, ma è possibile modificarlo.

     Al termine, fare clic su **Salva** in qualsiasi pagina.

     Per modificare una voce esistente, selezionare l'utente protetto nell'elenco.

     > [!NOTE]
     >
     > - In ogni criterio anti-phishing è possibile specificare un massimo di 60 utenti protetti (indirizzi di posta elettronica del mittente). Non è possibile specificare lo stesso utente protetto in più criteri.
     >
     > - La protezione della rappresentazione dell'utente non funziona se il mittente e il destinatario hanno già comunicato tramite posta elettronica. Se il mittente e il destinatario non hanno mai comunicato tramite posta elettronica, il messaggio verrà identificato come tentativo di rappresentazione.

   - **Aggiungere domini da proteggere:** configurare una o entrambe le impostazioni seguenti:

     - **Includi automaticamente i domini di cui sono proprietario:** il valore predefinito è **Disattivato.** Per attivarlo, far scorrere l'interruttore su **Attivato.**
     - **Includi domini personalizzati**: il valore predefinito è **Disattivato.** To turn it on, slide the toggle to **On**, and in the **Add domains** box, enter the domain name (for example, contoso.com), press INVIO, and repeat as necessary.

     > [!NOTE]
     > È possibile disporre di un massimo di 50 domini in tutti i criteri anti-phishing.

   - **Azioni**: fare clic su **Modifica**

     - **Se la posta elettronica** viene inviata da un utente rappresentato: configurare una delle azioni seguenti per i messaggi in cui il mittente falsificato è uno degli utenti protetti specificati in Aggiungi utenti **da proteggere:**

       - **Non applicare alcuna azione**
       - **Reindirizzare il messaggio ad altri indirizzi di posta elettronica**
       - **Sposta messaggio nella cartella Posta indesiderata**
       - **Mettere in quarantena il messaggio**
       - **Recapitare il messaggio e aggiungere altri indirizzi alla riga Ccn**
       - **Eliminare il messaggio prima che venga recapitato**

     - **Se la posta elettronica** viene inviata da un dominio rappresentato: configurare una delle azioni seguenti per i messaggi in cui il mittente falsificato si trova in uno dei domini protetti specificati in Aggiungi domini **da proteggere:**

       - **Non applicare alcuna azione**
       - **Reindirizzare il messaggio ad altri indirizzi di posta elettronica**
       - **Sposta messaggio nella cartella Posta indesiderata**
       - **Mettere in quarantena il messaggio**
       - **Recapitare il messaggio e aggiungere altri indirizzi alla riga Ccn**
       - **Eliminare il messaggio prima che venga recapitato**

   - Fare **clic su Attiva suggerimenti per la sicurezza della** rappresentazione e configurare una delle impostazioni seguenti:

     - **Mostra suggerimento per gli utenti rappresentati:** il valore predefinito è **Disattivato.** Per attivarlo, far scorrere l'interruttore su **Attivato.**
     - **Mostra suggerimento per i domini rappresentati:** il valore predefinito è **Disattivato.** Per attivarlo, far scorrere l'interruttore su **Attivato.**
     - **Mostra suggerimento per caratteri insoliti**: il valore predefinito è **Disattivato.** Per attivarlo, far scorrere l'interruttore su **Attivato.**

     Al termine, fare clic su **Salva**.

   - **Intelligence per le cassette postali:**

     - **Abilitare l'intelligence per le** cassette postali? : il valore predefinito è **Attivato.** Per disattivarlo, far scorrere l'interruttore su **Disattivato.**

     - **Abilitare la protezione della rappresentazione basata sull'intelligence** delle cassette postali? : Questa impostazione è disponibile solo se Abilita intelligence cassetta **postale?** **è attivata.**

       In **Se** la posta elettronica viene inviata da un utente rappresentato, è possibile specificare una delle seguenti azioni da eseguire sui messaggi che non riescono a usare l'intelligence per le cassette postali (le stesse azioni disponibili per gli utenti protetti e i domini protetti):

       - **Non applicare alcuna azione**
       - **Reindirizzare il messaggio ad altri indirizzi di posta elettronica**
       - **Sposta messaggio nella cartella Posta indesiderata**
       - **Mettere in quarantena il messaggio**
       - **Recapitare il messaggio e aggiungere altri indirizzi alla riga Ccn**
       - **Eliminare il messaggio prima che venga recapitato**

   - **Aggiungere domini e mittenti attendibili:** specificare le eccezioni per il criterio:

     - **Mittenti attendibili:**

       - Fare clic nella casella e scorrere l'elenco degli utenti da selezionare.
       - Fare clic nella casella e iniziare a digitare per filtrare l'elenco e selezionare un utente.
       - Per rimuovere una voce, fare **clic sull'icona** ![ Rimuovi ](../../media/scc-remove-icon.png) nell'utente.

     - **Domini attendibili:** immettere il nome di dominio (ad esempio, contoso.com), premere INVIO e ripetere in base alle esigenze.

   - **Rivedere le impostazioni:** invece di fare clic su ogni singolo passaggio, le impostazioni vengono visualizzate in un riepilogo.

     - È possibile fare **clic su Modifica** in ogni sezione per tornare alla pagina pertinente.
     - È possibile attivare o **disattivare** le **impostazioni** seguenti direttamente in questa pagina:

       - **Utenti protetti**
       - **Domini protetti** \> **Includere i domini di cui sono proprietario**
       - **Domini protetti** \> **Domini protetti** (domini personalizzati)
       - **Intelligence della cassetta postale**

   Al termine, fare clic su **Salva** in qualsiasi pagina.

6. **Spoof**:  fare clic su Modifica per attivare o disattivare spoof intelligence, attivare o disattivare l'identificazione del mittente non autenticato in Outlook e configurare l'azione da applicare ai messaggi provenienti da mittenti falsificati bloccati. Per ulteriori informazioni, vedere [Impostazioni di spoofing nei criteri anti-phishing.](set-up-anti-phishing-policies.md#spoof-settings)

   Si noti che queste stesse impostazioni sono disponibili anche nei criteri anti-phishing in EOP.

   - **Impostazioni del filtro per lo spoofing**: il valore predefinito è **On** e si consiglia di lasciarlo. Per disattivarlo, far scorrere l'interruttore su **Disattivato.** Per ulteriori informazioni, vedere [Configurare spoof intelligence in EOP.](learn-about-spoof-intelligence.md)

     > [!NOTE]
     > Non è necessario disabilitare la protezione anti-spoofing se il record MX non punta a Microsoft 365; si abilita invece il filtro avanzato per i connettori. Per istruzioni, vedere [Enhanced Filtering for Connectors in Exchange Online.](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)

   - **Abilita la funzionalità mittente non autenticato:** il valore predefinito è **Attivato.** Per disattivarlo, far scorrere l'interruttore su **Disattivato.**

   - **Azioni**: specificare l'azione da eseguire sui messaggi che non riescono a spoof intelligence:

     Se la posta elettronica viene inviata da un utente a cui non è consentito **effettuare lo spoofing del dominio:**

     - **Spostare il messaggio nelle cartelle Posta indesiderata dei destinatari**
     - **Mettere in quarantena il messaggio**

   - **Rivedere le impostazioni:** invece di fare clic su ogni singolo passaggio, le impostazioni vengono visualizzate in un riepilogo.

     - È possibile fare **clic su Modifica** in ogni sezione per tornare alla pagina pertinente.
     - È possibile attivare o **disattivare** le **impostazioni** seguenti direttamente in questa pagina:
       - **Abilitare la protezione antispoofing**
       - **Abilitare la funzionalità Mittente non autenticato**

   Al termine, fare clic su **Salva** in qualsiasi pagina.

7. **Impostazioni avanzate:** fare clic **su Modifica** per configurare le soglie di phishing avanzate. Per ulteriori informazioni, vedere [Soglie di phishing avanzate nei criteri anti-phishing in Microsoft Defender per Office 365.](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)

   - **Soglie di phishing avanzate:** selezionare uno dei seguenti valori:

   - **1 - Standard** (questo è il valore predefinito).
   - **2 - Aggressivo**
   - **3 - Più aggressivo**
   - **4 - Più aggressivo**

   - **Rivedere le impostazioni:** fare clic **su Modifica** per tornare alla **pagina Soglie di phishing** avanzate.

   Al termine, fare clic su **Salva** in entrambe le pagine.

8. Tornare alla pagina **Modifica i \<Name\> criteri,** rivedere le impostazioni e quindi fare clic su **Chiudi.**

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy-in-microsoft-defender-for-office-365"></a>Usare il Centro sicurezza & conformità per modificare il criterio anti-phishing predefinito in Microsoft Defender per Office 365

Il criterio anti-phishing predefinito in Microsoft Defender per Office 365 è denominato Office365 AntiPhish Default e non viene visualizzato nell'elenco dei criteri. Per modificare il criterio anti-phishing predefinito, eseguire la procedura seguente:

1. Nel Centro sicurezza & conformità passare **a** Anti-phishing dei criteri di gestione delle \>  \> **minacce ATP.**

2. Nella pagina **Anti-phishing** fare clic su **Criterio predefinito.**

3. Verrà **visualizzata la pagina Modifica i criteri predefiniti di Office365 AntiPhish.** Sono disponibili le sezioni seguenti, che contengono le stesse impostazioni per la modifica [di un criterio personalizzato:](#use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365)

   - **Rappresentazione**
   - **Spoofing**
   - **Impostazioni avanzate**

   Le impostazioni seguenti non sono disponibili quando si modifica il criterio predefinito:

   - È possibile  visualizzare la sezione e i valori  dell'impostazione dei criteri, ma non è disponibile alcun collegamento Modifica, quindi non è possibile modificare le impostazioni (nome del criterio, descrizione e a chi si applica il criterio (si applica a tutti i destinatari)).
   - Non è possibile eliminare il criterio predefinito.
   - Non è possibile modificare la priorità del criterio predefinito (viene sempre applicato per ultimo).

4. Nella pagina **Modifica i criteri predefiniti di Office365,** rivedere le impostazioni e quindi fare clic su **Chiudi.**

### <a name="enable-or-disable-custom-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Abilitare o disabilitare i criteri anti-phishing personalizzati in Microsoft Defender per Office 365

1. Nel Centro sicurezza & conformità passare **a** Anti-phishing dei criteri di gestione delle \>  \> **minacce ATP.**

2. Si noti il valore nella **colonna** Stato:

   - Fai scorrere **l'interruttore su Off** per disabilitare il criterio.

   - Fai scorrere **l'interruttore su On** per abilitare il criterio.

Non è possibile disabilitare il criterio anti-phishing predefinito.

### <a name="set-the-priority-of-custom-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Impostare la priorità dei criteri anti-phishing personalizzati in Microsoft Defender per Office 365

Per impostazione predefinita, ai criteri anti-phishing viene data una priorità che si basa sull'ordine in cui sono stati creati (i criteri più recenti hanno una priorità inferiore rispetto ai criteri precedenti). Un valore di priorità inferiore indica una priorità più alta per il criterio (0 è il massimo) e i criteri vengono elaborati nell'ordine di priorità (i criteri con priorità più elevata vengono elaborati prima di quelli con priorità più bassa). Nessun criterio può avere la stessa priorità e l'elaborazione dei criteri termina dopo l'applicazione del primo criterio.

Per altre informazioni sull'ordine di precedenza e su come vengono valutati e applicati multipli criteri, vedere [Ordine e precedenza della protezione della posta elettronica](how-policies-and-protections-are-combined.md).

I criteri anti-phishing personalizzati vengono visualizzati nell'ordine in cui vengono elaborati (il primo criterio ha il **valore Di** priorità 0). Il criterio anti-phishing predefinito denominato Office365 AntiPhish Default ha il valore di priorità personalizzato **Lowest** e non è possibile modificarlo.

 **Nota:** nel Centro sicurezza & conformità, è possibile modificare la priorità del criterio anti-phishing solo dopo aver creato il criterio. In PowerShell, è possibile ignorare la priorità predefinita quando si crea la regola anti-phish (che può influire sulla priorità delle regole esistenti).

Per modificare la priorità di  un criterio, fare clic su Aumenta priorità o Diminuisci  priorità nelle proprietà del criterio (non è possibile modificare direttamente il numero di priorità nel Centro sicurezza & conformità).  La modifica della priorità di un criterio è utile solo se si dispone di più criteri.

1. Nel Centro sicurezza & conformità passare **a** Anti-phishing dei criteri di gestione delle \>  \> **minacce ATP.**

2. Selezionare il criterio che si desidera modificare. Se è già selezionato, deselezionalo e selezionalo di nuovo.

3. Verrà **visualizzato \<name\> il riquadro a comparsa** Modifica criterio.

   - Il criterio anti-phishing personalizzato con **il valore Priority** **0** ha solo il **pulsante Diminuisci** priorità disponibile.

   - Il criterio anti-phishing personalizzato con il valore **Di** priorità più basso (ad esempio, **3)** ha solo il pulsante **Aumenta** priorità disponibile.

   - Se si dispone di tre o più criteri anti-phishing personalizzati,  i criteri tra i valori di priorità più alta e più bassa hanno entrambi i pulsanti Aumenta priorità e **Diminuisci** priorità disponibili.

4. Fare **clic su Aumenta priorità** o **Diminuisci priorità** per modificare il valore **di** Priorità.

5. Al termine, fare clic su **Chiudi**.

## <a name="use-the-security--compliance-center-to-view-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Usare il Centro sicurezza & conformità per visualizzare i criteri anti-phishing in Microsoft Defender per Office 365

1. Nel Centro sicurezza & conformità e passare a Criteri di **gestione** delle minacce \>  \> **ANTI-phishing ATP.**

2. Eseguire una delle operazioni seguenti:

   - Selezionare un criterio anti-phishing personalizzato che si desidera visualizzare. Se è già selezionato, deselezionalo e selezionalo di nuovo.

   - Fare **clic su Criterio predefinito** per visualizzare il criterio anti-phishing predefinito.

3. Viene **visualizzato \<name\> il riquadro a comparsa** Modifica il criterio, in cui è possibile visualizzare le impostazioni e i valori.

## <a name="use-the-security--compliance-center-to-remove-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Usare il Centro sicurezza & conformità per rimuovere i criteri anti-phishing in Microsoft Defender per Office 365

1. Nel Centro sicurezza & conformità passare **a** Anti-phishing dei criteri di gestione delle \>  \> **minacce ATP.**

2. Selezionare il criterio che si desidera rimuovere. Se è già selezionato, deselezionalo e selezionalo di nuovo.

3. Nel riquadro **a \<name\> comparsa Modifica** criterio visualizzato fare clic su Elimina criterio **e** quindi su **Sì** nella finestra di dialogo di avviso visualizzata.

Non è possibile rimuovere il criterio predefinito.

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Utilizzare PowerShell di Exchange Online per configurare i criteri anti-phishing in Microsoft Defender per Office 365

Come descritto in precedenza, un criterio di protezione da posta indesiderata è costituito da un criterio anti-phish e da una regola anti-phish.

In PowerShell di Exchange Online, la differenza tra i criteri anti-phish e le regole anti-phish è evidente. È possibile gestire i criteri anti-phish utilizzando i cmdlet **\* -AntiPhishPolicy** e gestire le regole anti-phish utilizzando i cmdlet **\* -AntiPhishRule.**

- In PowerShell, si crea prima il criterio anti-phish, quindi si crea la regola anti-phish che identifica il criterio a cui si applica la regola.
- In PowerShell, le impostazioni dei criteri anti-phish e della regola anti-phish vengono modificate separatamente.
- Quando si rimuove un criterio anti-phish da PowerShell, la regola anti-phish corrispondente non viene rimossa automaticamente e viceversa.

### <a name="use-powershell-to-create-anti-phishing-policies"></a>Utilizzare PowerShell per creare criteri anti-phishing

La creazione di un criterio anti-phishing in PowerShell è un processo in due passaggi:

1. Creare il criterio anti-phish.
2. Creare la regola anti-phish che specifica il criterio anti-phish a cui si applica la regola.

 **Note**:

- È possibile creare una nuova regola anti-phish e assegnarle un criterio anti-phish esistente e non associazione. Una regola anti-phish non può essere associata a più criteri anti-phish.

- È possibile configurare le impostazioni seguenti nei nuovi criteri anti-phish in PowerShell che non sono disponibili nel Centro sicurezza & conformità fino a quando non si crea il criterio:

  - Creare il nuovo criterio come disabilitato (_abilitato_ `$false` nel cmdlet **New-AntiPhishRule).**
  - Impostare la priorità del criterio durante la creazione (_Priority_ ) nel _\<Number\>_ cmdlet **New-AntiPhishRule.**

- Un nuovo criterio anti-phish creato in PowerShell non è visibile nel Centro sicurezza & conformità finché non si assegna il criterio a una regola anti-phish.

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a>Passaggio 1: Utilizzare PowerShell per creare un criterio anti-phish

Per creare un criterio anti-phish, utilizzare la sintassi seguente:

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

In questo esempio viene creato un criterio anti-phish denominato Research Quarantine con le impostazioni seguenti:

- Il criterio è abilitato (non viene utilizzato il parametro _Enabled_ e il valore predefinito è `$true` ).
- La descrizione è: Criteri del reparto ricerche.
- Abilita la protezione dei domini dell'organizzazione per tutti i domini accettati e la protezione dei domini di destinazione per fabrikam.com.
- Specifica Mai Fujito (mfujito@fabrikam.com) come l'utente da proteggere da imitazione.
- Abilita l'intelligence della cassetta postale.
- Abilita la protezione intelligence delle cassette postali e specifica l'azione di quarantena.
- Abilita i suggerimenti per la sicurezza.

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -EnableOrganizationDomainsProtection $true -EnableTargetedDomainsProtection $true -TargetedDomainsToProtect fabrikam.com -TargetedDomainProtectionAction Quarantine -EnableTargetedUserProtection $true -TargetedUsersToProtect "Mai Fujito;mfujito@fabrikam.com" -TargetedUserProtectionAction Quarantine -EnableMailboxIntelligence $true -EnableMailboxIntelligenceProtection $true -MailboxIntelligenceProtectionAction Quarantine -EnableSimilarUsersSafetyTips $true -EnableSimilarDomainsSafetyTips $true -EnableUnusualCharactersSafetyTips $true
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere New-AntiPhishPolicy.](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy)

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a>Passaggio 2: Utilizzare PowerShell per creare una regola anti-phish

Per creare una regola anti-phish, utilizzare la sintassi seguente:

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

In questo esempio viene creata una regola anti-phish denominata Research Department con le condizioni seguenti:

- La regola è associata al criterio anti-phish denominato Quarantena ricerche.
- La regola viene applicata ai membri del gruppo denominato Research Department.
- Poiché non viene utilizzato il parametro _Priority,_ viene utilizzata la priorità predefinita.

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere New-AntiPhishRule.](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule)

### <a name="use-powershell-to-view-anti-phish-policies"></a>Usare PowerShell per visualizzare i criteri anti-phish

Per visualizzare i criteri anti-phish esistenti, utilizzare la sintassi seguente:

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

In questo esempio viene restituito un elenco riepilogativo di tutti i criteri anti-phish insieme alle proprietà specificate.

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

In questo esempio vengono restituiti tutti i valori delle proprietà per il criterio anti-phish denominato Executives.

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Get-AntiPhishPolicy.](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy)

### <a name="use-powershell-to-view-anti-phish-rules"></a>Utilizzare PowerShell per visualizzare le regole anti-phish

Per visualizzare le regole anti-phish esistenti, utilizzare la sintassi seguente:

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

In questo esempio viene restituito un elenco riepilogativo di tutte le regole anti-phish insieme alle proprietà specificate.

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

Per filtrare l'elenco in base alle regole abilitate o disabilitate, eseguire i comandi seguenti:

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

In questo esempio vengono restituiti tutti i valori delle proprietà per la regola anti-phish denominata Contoso Executives.

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Get-AntiPhishRule.](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule)

### <a name="use-powershell-to-modify-anti-phish-policies"></a>Utilizzare PowerShell per modificare i criteri anti-phish

Oltre agli elementi seguenti, le stesse impostazioni sono disponibili quando si modifica un criterio anti-phish in PowerShell come quando si crea il criterio come descritto nel passaggio 1: Utilizzare PowerShell per creare una sezione dei criteri [anti-phish](#step-1-use-powershell-to-create-an-anti-phish-policy) più indietro in questo articolo.

- L'opzione _MakeDefault_ che trasforma il criterio specificato nel  criterio predefinito (applicato a tutti, sempre con priorità bassa e non è possibile eliminarlo) è disponibile solo quando si modifica un criterio anti-phish in PowerShell.

- Non è possibile rinominare un criterio anti-phish (il cmdlet **Set-AntiPhishPolicy** non dispone di alcun _parametro_ Name). Quando si rinomina un criterio anti-phishing nel Centro sicurezza & conformità, si rinomina solo la regola anti-phishing.

Per modificare un criterio anti-phish, utilizzare la sintassi seguente:

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-AntiPhishPolicy.](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy)

### <a name="use-powershell-to-modify-anti-phish-rules"></a>Utilizzare PowerShell per modificare le regole anti-phish

L'unica impostazione non disponibile quando si modifica una regola anti-phish in PowerShell è il parametro _Enabled_ che consente di creare una regola disabilitata. Per abilitare o disabilitare le regole anti-phish esistenti, vedere la sezione successiva.

In caso contrario, non sono disponibili impostazioni aggiuntive quando si modifica una regola anti-phish in PowerShell. Le stesse impostazioni sono disponibili quando si crea una regola come descritto nel passaggio 2: Utilizzare PowerShell per creare una regola [anti-phish](#step-2-use-powershell-to-create-an-anti-phish-rule) descritta in precedenza in questo articolo.

Per modificare una regola anti-phish, utilizzare la sintassi seguente:

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-AntiPhishRule.](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule)

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a>Utilizzare PowerShell per abilitare o disabilitare le regole anti-phish

L'abilitazione o disabilitazione di una regola anti-phishing in PowerShell abilita o disabilita l'intero criterio anti-phishing (la regola anti-phishing e il criterio anti-phishing assegnato). Non è possibile abilitare o disabilitare il criterio anti-phishing predefinito (viene sempre applicato a tutti i destinatari).

Per abilitare o disabilitare una regola anti-phish in PowerShell, utilizzare la sintassi seguente:

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

In questo esempio viene disabilitata la regola anti-phish denominata Marketing Department.

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

In questo esempio viene abilitata la stessa regola.

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-antiphishrule) e [Disable-AntiPhishRule.](https://docs.microsoft.com/powershell/module/exchange/disable-antiphishrule)

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a>Usare PowerShell per impostare la priorità delle regole anti-phish

Il valore di priorità più alto che è possibile impostare in una regola è 0. Il valore più basso che è possibile impostare dipende dal numero di regole. Se si dispone di cinque regole, ad esempio, è possibile utilizzare i valori di priorità da 0 a 4. Modificare la priorità di una regola esistente può avere un effetto a catena su altre regole. Ad esempio, se si dispone di cinque regole personalizzate (priorità da 0 a 4) e si modifica la priorità di una regola su 2, la regola esistente con priorità 2 viene modificata a livello di priorità 3 e la regola con priorità 3 viene modificata a livello di priorità 4.

Per impostare la priorità di una regola anti-phish in PowerShell, utilizzare la sintassi seguente:

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

Nell'esempio seguente la priorità della regola denominata Marketing Department viene impostata su 2. Tutte le regole esistenti che hanno una priorità minore o uguale a 2 vengono abbassate di 1 valore (i numeri di priorità vengono aumentati di 1).

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

**Note**:

- Per impostare la priorità di una nuova regola al momento della creazione, utilizzare il parametro _Priority_ nel cmdlet **New-AntiPhishRule.**

- Il criterio anti-phish predefinito non dispone di una regola anti-phish corrispondente e ha sempre il valore di priorità non modificabile **Lowest.**

### <a name="use-powershell-to-remove-anti-phish-policies"></a>Utilizzare PowerShell per rimuovere i criteri anti-phish

Quando si utilizza PowerShell per rimuovere un criterio anti-phish, la regola anti-phish corrispondente non viene rimossa.

Per rimuovere un criterio anti-phish in PowerShell, utilizzare la sintassi seguente:

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

In questo esempio viene rimosso il criterio anti-phish denominato Marketing Department.

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Remove-AntiPhishPolicy.](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy)

### <a name="use-powershell-to-remove-anti-phish-rules"></a>Utilizzare PowerShell per rimuovere le regole anti-phish

Quando si utilizza PowerShell per rimuovere una regola anti-phish, il criterio anti-phish corrispondente non viene rimosso.

Per rimuovere una regola anti-phish in PowerShell, utilizzare la sintassi seguente:

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

In questo esempio viene rimossa la regola anti-phish denominata Marketing Department.

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Remove-AntiPhishRule.](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule)

## <a name="how-do-you-know-these-procedures-worked"></a>Come verificare se queste procedure hanno avuto esito positivo?

Per verificare la corretta configurazione dei criteri anti-phishing in Microsoft Defender per Office 365, eseguire una delle operazioni seguenti:

- Nel Centro sicurezza & conformità passare **a** Anti-phishing dei criteri di gestione delle \>  \> **minacce ATP.** Verificare l'elenco dei criteri, i relativi **valori di** stato e i relativi **valori di** priorità. Per visualizzare ulteriori dettagli, eseguire una delle operazioni seguenti:

  - Selezionare il criterio nell'elenco e visualizzare i dettagli nel riquadro a comparsa.
  - Fare **clic su Criterio** predefinito e visualizzare i dettagli nel riquadro a comparsa.

- In PowerShell di Exchange Online, sostituire con il nome del criterio o della regola ed eseguire il \<Name\> comando seguente e verificare le impostazioni:

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
