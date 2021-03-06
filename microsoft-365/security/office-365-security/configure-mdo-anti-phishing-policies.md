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
ms.openlocfilehash: 71baf947c5834e2eb4b8ef62af69da77ea5bd090
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/30/2021
ms.locfileid: "53230044"
---
# <a name="configure-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>Configurare i criteri anti-phishing in Microsoft Defender per Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Microsoft Defender per Office 365 piano 1 e piano 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

I criteri anti-phishing in [Microsoft Defender per Office 365](defender-for-office-365.md) possono aiutare a proteggere l'organizzazione da attacchi di phishing dannosi basati sulla rappresentazione e da altri tipi di attacchi di phishing. Per ulteriori informazioni sulle differenze tra i criteri anti-phishing in Exchange Online Protection (EOP) e i criteri anti-phishing in Microsoft Defender per Office 365, vedere [Protezione anti-phishing.](anti-phishing-protection.md)

Gli amministratori possono visualizzare, modificare e configurare (ma non eliminare) il criterio anti-phishing predefinito. Per una maggiore granularità, è inoltre possibile creare criteri anti-phishing personalizzati che si applicano a utenti, gruppi o domini specifici nell'organizzazione. I criteri personalizzati hanno sempre la precedenza sul criterio predefinito, ma non è possibile modificarne la priorità (in funzione).

È possibile configurare i criteri anti-phishing in Defender per Office 365 nel portale di Microsoft 365 Defender o in Exchange Online PowerShell.

Per informazioni sulla configurazione dei criteri anti-phishing più limitati disponibili in Exchange Online Protection (ovvero le organizzazioni senza Defender per Office 365), vedere [Configure anti-phishing policies in EOP.](configure-anti-phishing-policies-eop.md)

Gli elementi di base di un criterio anti-phishing sono:

- **Il criterio anti-phishing**: Specifica le protezioni anti-phishing da abilitare o disabilitare e le azioni da applicare.
- **La regola anti-phish**: Specifica la priorità e i filtri destinatario (a chi si applica il criterio) per un criterio anti-phish.

La differenza tra questi due elementi non è ovvia quando si gestiscono i criteri anti-phishing nel portale Microsoft 365 Defender:

- Quando crei un criterio, stai creando una regola anti-phish e il criterio anti-phish associato contemporaneamente usando lo stesso nome per entrambi.
- Quando si modifica un criterio, le impostazioni relative al nome, alla priorità, abilitate o disabilitate e ai filtri destinatari modificano la regola anti-phish. Tutte le altre impostazioni modificano il criterio anti-phish associato.
- Quando si rimuove un criterio, vengono rimossi la regola anti-phish e il criterio anti-phish associato.

In Exchange Online PowerShell, il criterio e la regola vengono gestiti separatamente. Per ulteriori informazioni, vedere la sezione [Use Exchange Online PowerShell to configure anti-phishing policies](#use-exchange-online-powershell-to-configure-anti-phishing-policies) più avanti in questo articolo.

Ogni defender per Office 365 ha un criterio anti-phishing predefinito denominato Office365 AntiPhish Default con queste proprietà:

- Il criterio viene applicato a tutti i destinatari dell'organizzazione, anche se al criterio non è associata alcuna regola anti-phish (filtri destinatari).
- Il valore personalizzato della priorità del criterio è **Minore** e non può essere modificato (il criterio viene sempre applicato per ultimo). Qualsiasi criterio personalizzato creato avrà sempre una priorità più alta.
- Il criterio è quello predefinito (la proprietà **IsDefault** contiene il valore `True`), e non è possibile eliminarlo.

Per aumentare l'efficacia della protezione anti-phishing in Defender per Office 365, è possibile creare criteri anti-phishing personalizzati con impostazioni più rigide applicate a utenti o gruppi di utenti specifici.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare?

- Per aprire il portale di Microsoft 365 Defender, andare alla pagina <https://security.microsoft.com>. Per passare direttamente alla pagina **Anti-phishing,** utilizzare <https://security.microsoft.com/antiphishing> .

- Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).

- Prima di eseguire le procedure descritte in questo articolo, occorre disporre delle autorizzazioni in **Exchange Online**:
  - Per aggiungere, modificare ed eliminare criteri anti-phishing, è necessario essere membri dei gruppi **di** ruoli Gestione organizzazione o Amministratore **sicurezza.**
  - Per l'accesso in sola lettura ai criteri anti-phishing, è necessario essere membri dei gruppi di ruoli **Lettore** globale o **Lettore** di sicurezza <sup>\*</sup> .

  Per altre informazioni, vedere [Autorizzazioni in Exchange Online](/exchange/permissions-exo/permissions-exo).

  **Note**:

  - L'aggiunta di utenti al ruolo di Azure Active Directory corrispondente nell'interfaccia di amministrazione di Microsoft 365 fornisce agli utenti le autorizzazioni necessarie _e_ le autorizzazioni per altre funzionalità di Microsoft 365. Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](../../admin/add-users/about-admin-roles.md).
  - Anche il gruppo di ruoli di **Gestione organizzazione sola visualizzazione** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) offre inoltre l'accesso di sola lettura a tale funzionalità.

- Per le impostazioni consigliate per i criteri anti-phishing in Defender per Office 365, vedi [Criteri anti-phishing in Defender per Office 365 impostazioni](recommended-settings-for-eop-and-office365.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365).

- Consentire fino a 30 minuti per l'applicazione di un criterio nuovo o aggiornato.

- Per informazioni su dove vengono applicati i criteri anti-phishing nella pipeline di filtro, vedere [Order and precedence of email protection.](how-policies-and-protections-are-combined.md)

## <a name="use-the-microsoft-365-defender-portal-to-create-anti-phishing-policies"></a>Utilizzare il portale Microsoft 365 Defender per creare criteri anti-phishing

La creazione di un criterio anti-phishing personalizzato nel portale di Microsoft 365 Defender crea la regola anti-phishing e il criterio anti-phishing associato contemporaneamente utilizzando lo stesso nome per entrambi.

1. Nel portale Microsoft 365 Defender, passare **a** Criteri di collaborazione & e-mail & regole Criteri di minaccia sezione \>  \>  Criteri \>  \> **sezione Anti-phishing.**

2. Nella pagina **Anti-phishing** fare clic su ![ Crea icona ](../../media/m365-cc-sc-create-icon.png) **Crea**.

3. Viene aperta la creazione guidata criteri. Nella pagina **Nome criterio** configurare queste impostazioni:
   - **Nome**: immettere un nome univoco descrittivo per il criterio.
   - **Descrizione**: immettere una descrizione opzionale per il criterio.

   Al termine dell'operazione, fare clic su **Avanti**.

4. Nella pagina **Utenti, gruppi e domini** visualizzata identificare i destinatari interni a cui si applicano i criteri (condizioni del destinatario):
   - **Utenti**: la cassette postali specificate, utenti di posta o contatti di posta specificati nell'organizzazione.
   - **Gruppi**: i gruppi di distribuzione specificati, gruppi di sicurezza abilitati alla posta elettronica o gruppi di Microsoft 365 nell'organizzazione.
   - **Domini**: tutti i destinatari nei domini specificati [accettati](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) nell'organizzazione.

   Fare clic nella casella appropriata, iniziare a digitare un valore e selezionare il valore desiderato nei risultati. Ripetere questa procedura tutte le volte necessarie. Per rimuovere un valore esistente, fare clic su Rimuovi ![Icona Rimuovi](../../media/m365-cc-sc-remove-selection-icon.png) accanto al valore.

   Per utenti o gruppi è possibile usare la maggior parte degli identificatori, ad esempio nome, nome visualizzato, alias, indirizzo di posta elettronica, nome dell'account e così via, ma il nome visualizzato corrispondente viene visualizzato nei risultati. Per gli utenti, immettere un asterisco (\*) da solo per visualizzare tutti i valori disponibili.

   Più valori della stessa condizione utilizzano la logica OR (ad esempio, _\<recipient1\>_ o _\<recipient2\>_). Condizioni diverse utilizzano la logica AND (ad esempio, _\<recipient1\>_ e _\<member of group 1\>_).

   - **Escludere questi utenti, gruppi e domini**: per aggiungere eccezioni per i destinatari interni a cui si applicano i criteri (eccezione destinatari), selezionare questa opzione e configurare le eccezioni. Impostazioni e comportamento sono equivalenti alle condizioni.

   Al termine dell'operazione, fare clic su **Avanti**.

5. Nella pagina **Soglia di & phishing** visualizzata configurare le impostazioni seguenti:

   - **Soglia posta elettronica di phishing**: usa il dispositivo di scorrimento per selezionare uno dei valori seguenti:
     - **1 - Standard** (questo è il valore predefinito).
     - **2 - Aggressivo**
     - **3 - Più aggressivo**
     - **4 - Più aggressivo**

     Per ulteriori informazioni, vedere [Soglie avanzate di phishing nei criteri anti-phishing in Microsoft Defender per Office 365](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365).

   - **Rappresentazione:** queste impostazioni sono una condizione per il criterio che identifica mittenti specifici da cercare (singolarmente o per dominio) nell'indirizzo mittente dei messaggi in ingresso. Per ulteriori informazioni, vedere [Impostazioni di rappresentazione nei criteri anti-phishing in Microsoft Defender per Office 365](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).

     > [!NOTE]
     >
     > - In ogni criterio anti-phishing è possibile specificare un massimo di 350 utenti protetti (indirizzi di posta elettronica del mittente). Non è possibile specificare lo stesso utente protetto in più criteri.
     > - La protezione della rappresentazione dell'utente non funziona se il mittente e il destinatario hanno precedentemente comunicato tramite posta elettronica. Se il mittente e il destinatario non hanno mai comunicato tramite posta elettronica, il messaggio verrà identificato come tentativo di rappresentazione.

     - **Consenti agli utenti di proteggere**: il valore predefinito è disattivato (non selezionato). Per attivarla, selezionare la casella di controllo e quindi fare clic sul collegamento Gestisci **mittenti (nn)** visualizzato.

       Nel riquadro **a comparsa Gestisci mittenti** per la protezione della rappresentazione visualizzato eseguire la procedura seguente:

       - **Mittenti interni**: fare clic ![ su Aggiungi icona interna Seleziona ](../../media/m365-cc-sc-add-internal-icon.png) **interno.** Nel riquadro **a comparsa Aggiungi mittenti** interni visualizzato fare clic nella casella e selezionare un utente interno nell'elenco. È possibile filtrare l'elenco digitando l'utente e quindi selezionandolo dai risultati. È possibile utilizzare la maggior parte degli identificatori (nome, nome visualizzato, alias, indirizzo di posta elettronica, nome account e così via), ma il nome visualizzato corrispondente viene visualizzato nei risultati.

         Ripetere questo passaggio tutte le volte necessarie. Per rimuovere un valore esistente, fare clic su Rimuovi ![Icona Rimuovi](../../media/m365-cc-sc-remove-selection-icon.png) accanto al valore.

         Al termine, fare clic su **Aggiungi**

       - **Mittenti esterni**: fare clic ![ su Aggiungi icona esterna Seleziona ](../../media/m365-cc-sc-create-icon.png) **esterno.** Nel riquadro a comparsa Add **external senders** that appears, enter a display name in the **Add a name** box and an email address in the Add a **vaild email** box, and then click **Add**.

         Ripetere questo passaggio tutte le volte necessarie. Per rimuovere un valore esistente, fare clic su Rimuovi ![Icona Rimuovi](../../media/m365-cc-sc-remove-selection-icon.png) accanto al valore.

         Al termine, fare clic su **Aggiungi**

       Tornare al **riquadro a** comparsa Gestisci mittenti per la rappresentazione, è possibile rimuovere le voci selezionando una o più voci dall'elenco. È possibile cercare voci utilizzando la casella Di ricerca ![ icona ](../../media/m365-cc-sc-create-icon.png) **di** ricerca.

       Dopo aver selezionato almeno una voce, viene visualizzata l'icona Rimuovi utenti selezionati Icona Rimuovi utenti selezionati, che è possibile utilizzare per rimuovere ![ ](../../media/m365-cc-sc-remove-selected-users-icon.png)  le voci selezionate.

       Al termine, fare clic su **Fine**.

     - **Abilita domini da proteggere**: il valore predefinito è disattivato (non selezionato). Per attivarla, selezionare la casella di controllo e quindi configurare una o entrambe le impostazioni seguenti:
       - **Includi i domini di cui sono proprietario:** per attivare questa impostazione, selezionare la casella di controllo. Per visualizzare i domini di cui si è proprietari, fare **clic su Visualizza domini.**
       - **Includi domini personalizzati:** per attivare questa impostazione, selezionare la casella di controllo e quindi fare clic sul collegamento Gestisci **(nn)** dominio personalizzato visualizzato. Nel riquadro **a comparsa Gestisci domini personalizzati per la protezione della** rappresentazione visualizzato fare clic su Aggiungi domini icona Aggiungi ![ ](../../media/m365-cc-sc-create-icon.png) **domini**.

         Nel riquadro a comparsa **Aggiungi** domini personalizzati visualizzato fare clic nella casella **Dominio,** immettere un valore e quindi premere INVIO o selezionare il valore visualizzato sotto la casella. Ripetere questo passaggio tutte le volte necessarie. Per rimuovere un valore esistente, fare clic su ![Rimuovi icona](../../media/m365-cc-sc-remove-selection-icon.png) accanto al valore.

         Al termine, fare clic su **Aggiungi domini**

         > [!NOTE]
         > È possibile avere un massimo di 50 domini in tutti i criteri anti-phishing.

       Tornare al **riquadro a** comparsa Gestisci domini personalizzati per la rappresentazione, è possibile rimuovere le voci selezionando una o più voci dall'elenco. È possibile cercare voci utilizzando la casella Di ricerca ![ icona ](../../media/m365-cc-sc-create-icon.png) **di** ricerca.

       Dopo aver selezionato almeno una voce, viene visualizzata l'icona Elimina l'icona Elimina domini, che può essere utilizzata per ![ rimuovere le voci ](../../media/m365-cc-sc-delete-icon.png)  selezionate.

   - **Aggiungere mittenti e** domini attendibili : : specificare le eccezioni di protezione della rappresentazione per il criterio facendo clic su Gestisci **(nn)** mittenti attendibili e domini. Nel riquadro **a comparsa Gestisci domini personalizzati** per la protezione della rappresentazione visualizzato configurare le impostazioni seguenti:
      - **Mittenti:** verificare che la **scheda Mittente** sia selezionata e fare clic ![ su Aggiungi mittenti icona ](../../media/m365-cc-sc-create-icon.png) . Nel riquadro **a comparsa Aggiungi mittenti** attendibili visualizzato immettere un indirizzo di posta elettronica nella casella e quindi fare clic su **Aggiungi.** Ripetere questo passaggio tutte le volte necessarie. Per rimuovere una voce esistente, fare clic ![ sull'icona Elimina ](../../media/m365-cc-sc-close-icon.png) per la voce.

        Al termine, fare clic su **Aggiungi**.

      - **Domini**: selezionare la **scheda Dominio** e fare clic ![ sull'icona Aggiungi ](../../media/m365-cc-sc-create-icon.png) domini.
  
        Nel riquadro **a** comparsa Aggiungi domini attendibili  visualizzato fare clic nella casella Dominio, immettere un valore e quindi premere INVIO o selezionare il valore visualizzato sotto la casella. Ripetere questo passaggio tutte le volte necessarie. Per rimuovere un valore esistente, fare clic su ![Rimuovi icona](../../media/m365-cc-sc-remove-selection-icon.png) accanto al valore.

        Al termine, fare clic su **Aggiungi**.

     Tornare al **riquadro a** comparsa Gestisci domini personalizzati per la  rappresentazione, è possibile rimuovere le voci dalle schede Mittente e Dominio selezionando una o più voci dall'elenco.  È possibile cercare voci utilizzando la casella Di ricerca ![ icona ](../../media/m365-cc-sc-create-icon.png) **di** ricerca.

     Dopo aver selezionato almeno una voce, viene visualizzata **l'icona** Elimina, che può essere utilizzata per rimuovere le voci selezionate.

     Al termine, fare clic su **Fine**.

   - **Abilitare l'intelligence delle** cassette postali : il valore predefinito è attivato (selezionato) e si consiglia di lasciarlo attivato. Per disattivarla, deselezionare la casella di controllo.

     - **Abilita protezione della rappresentazione basata sull'intelligence**: questa impostazione è disponibile solo se **Abilita intelligence cassetta postale** è attivata (selezionata). Questa impostazione consente all'intelligence delle cassette postali di intervenire sui messaggi identificati come tentativi di rappresentazione. Specificare l'azione da eseguire **nell'impostazione Se l'intelligence** delle cassette postali rileva un utente rappresentato nella pagina successiva.

       È consigliabile attivare questa impostazione selezionando la casella di controllo. Per disattivare questa impostazione, deselezionare la casella di controllo.

   - **Spoof**: in questa sezione, utilizzare la casella di controllo **Abilita spoof intelligence** per attivare o disattivare spoof intelligence. Il valore predefinito è on (selezionato) e ti consigliamo di lasciarlo. È possibile specificare l'azione da eseguire sui messaggi provenienti da mittenti spoofing bloccati nell'impostazione Se il messaggio viene rilevato come **spoofing** nella pagina successiva.

     Per disattivare lo spoof intelligence, deselezionare la casella di controllo.

     > [!NOTE]
     > Non è necessario disattivare la protezione anti-spoofing se il record MX non punta a Microsoft 365; si abilita invece il filtro avanzato per i connettori. Per istruzioni, vedere [Enhanced Filtering for Connectors in Exchange Online](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors).

   Al termine dell'operazione, fare clic su **Avanti**.

6. Nella pagina **Azioni** visualizzata configurare le impostazioni seguenti:

   - **Azioni messaggio**: configurare le azioni seguenti in questa sezione:
     - **Se il messaggio viene rilevato come utente rappresentato:** questa impostazione è disponibile solo se è stata selezionata l'opzione Consenti agli utenti di **proteggere** nella pagina precedente. Selezionare una delle azioni seguenti nell'elenco a discesa per i messaggi in cui il mittente è uno degli utenti protetti specificati nella pagina precedente:
       - **Non applicare alcuna azione**
       - **Reindirizzare il messaggio ad altri indirizzi di posta elettronica**
       - **Spostare il messaggio nelle cartelle posta indesiderata dei destinatari**
       - **Mettere in quarantena il messaggio**
       - **Recapitare il messaggio e aggiungere altri indirizzi alla riga Ccn**
       - **Eliminare il messaggio prima che venga recapitato**

     - **Se il messaggio viene rilevato come** dominio rappresentato: questa impostazione è disponibile solo se è stata selezionata l'opzione Abilita domini da proteggere nella pagina precedente.  Selezionare una delle azioni seguenti nell'elenco a discesa per i messaggi in cui l'indirizzo di posta elettronica del mittente si trova in uno dei domini protetti specificati nella pagina precedente:
       - **Non applicare alcuna azione**
       - **Reindirizzare il messaggio ad altri indirizzi di posta elettronica**
       - **Spostare il messaggio nelle cartelle posta indesiderata dei destinatari**
       - **Mettere in quarantena il messaggio**
       - **Recapitare il messaggio e aggiungere altri indirizzi alla riga Ccn**
       - **Eliminare il messaggio prima che venga recapitato**

     - **If mailbox intelligence detects an impersonated user**: This setting is available only if you selected **Enable intelligence for impersonation protection** on the previous page. Selezionare una delle azioni seguenti nell'elenco a discesa per i messaggi identificati come tentativi di rappresentazione dall'intelligence delle cassette postali:
       - **Non applicare alcuna azione**
       - **Reindirizzare il messaggio ad altri indirizzi di posta elettronica**
       - **Spostare il messaggio nelle cartelle posta indesiderata dei destinatari**
       - **Mettere in quarantena il messaggio**
       - **Recapitare il messaggio e aggiungere altri indirizzi alla riga Ccn**
       - **Eliminare il messaggio prima che venga recapitato**

     - **Se il messaggio viene rilevato come spoof:** questa impostazione è disponibile solo se è stato selezionato **Abilita spoof intelligence** nella pagina precedente. Selezionare una delle azioni seguenti nell'elenco a discesa per i messaggi provenienti da mittenti falsificati bloccati:
       - **Spostare il messaggio nelle cartelle posta indesiderata dei destinatari**
       - **Mettere in quarantena il messaggio**

   - **Suggerimenti per la sicurezza & indicatori**: Configurare le impostazioni seguenti:
     - **Show first contact suggerimento per la sicurezza**: Per ulteriori informazioni, vedere [First contact suggerimento per la sicurezza](set-up-anti-phishing-policies.md#first-contact-safety-tip).
     - **Mostra rappresentazione utente suggerimento per la sicurezza**: questa impostazione è disponibile solo se è stata selezionata l'opzione Consenti agli utenti **di proteggere** nella pagina precedente.
     - **Show domain impersonation suggerimento per la sicurezza**: Questa impostazione è disponibile solo se è stato selezionato Abilita domini **da proteggere** nella pagina precedente.
     - **Mostra caratteri insoliti di rappresentazione utente suggerimento per la sicurezza** Questa impostazione è disponibile solo se è stata selezionata l'opzione Consenti agli **utenti di proteggere** o Abilitare i domini per la **protezione** nella pagina precedente.
     - **Mostra (?) per i mittenti** non autenticati per lo spoofing: questa impostazione è disponibile solo se è stato selezionato **Abilita spoof intelligence** nella pagina precedente. Aggiunge un punto interrogativo alla foto del mittente nella casella Da di Outlook se il  messaggio non supera i controlli SPF o DKIM e il messaggio non supera l'autenticazione DMARC o [composita.](email-validation-and-authentication.md#composite-authentication)
     - **Mostra tag "via":** questa impostazione è disponibile solo se è stata selezionata l'opzione **Abilita spoof intelligence** nella pagina precedente. Aggiunge un tag via (chris@contoso.com tramite fabrikam.com) all'indirizzo From se è diverso dal dominio nella firma DKIM o nell'indirizzo **MAIL FROM.** Il valore predefinito è on (selezionato). Per disattivarla, deselezionare la casella di controllo.

       > [!NOTE]
       > Se non si dispone dell'impostazione Mostra **tag "via",** il punto interrogativo e il tag via sono entrambi controllati dall'impostazione Mostra **(?)** per i mittenti non autenticati per lo spoofing nell'organizzazione. 

     Per attivare un'impostazione, selezionare la casella di controllo. Per disattivarla, deselezionare la casella di controllo.

   Al termine dell'operazione, fare clic su **Avanti**.

7. Nella pagina **Controllo** visualizzata controllare le impostazioni. È possibile selezionare **Modifica** in ogni sezione per modificare le impostazioni all'interno della sezione. Oppure è possibile fare clic su **Indietro** o selezionare la pagina specifica della procedura guidata.

   Al termine, fare clic su **Salva**.

8. Nel messaggio di conferma visualizzato fare clic su **Fatto**.

## <a name="use-the-microsoft-365-defender-portal-to-view-anti-phishing-policies"></a>Utilizzare il portale Microsoft 365 Defender per visualizzare i criteri anti-phishing

1. Nel portale Microsoft 365 Defender, passare **a** Criteri di collaborazione & e-mail & regole Criteri di minaccia sezione \>  \>  Criteri \>  \> **sezione Anti-phishing.**

2. Nella pagina **Anti-phishing** vengono visualizzate le proprietà seguenti nell'elenco dei criteri anti-phishing:

   - **Nome**
   - **Stato**
   - **Priorità**
   - **Data ultima modifica**

3. Quando si seleziona un criterio facendo clic sul nome, le impostazioni dei criteri vengono visualizzate in un riquadro a comparsa.

## <a name="use-the-microsoft-365-defender-portal-to-modify-anti-phishing-policies"></a>Utilizzare il portale Microsoft 365 Defender per modificare i criteri anti-phishing

1. Nel portale Microsoft 365 Defender, passare **a** Criteri di collaborazione & e-mail & regole Criteri di minaccia sezione \>  \>  Criteri \>  \> **sezione Anti-phishing.**

2. Nella pagina **Anti-phishing** selezionare un criterio dall'elenco facendo clic sul nome.

3. Nel riquadro a comparsa dei dettagli sui criteri visualizzato selezionare **Modifica** in ogni sezione per modificare le impostazioni all'interno della sezione. Per ulteriori informazioni sulle impostazioni, vedere la sezione Usare il portale di Microsoft 365 Defender per creare criteri [anti-phishing](#use-the-microsoft-365-defender-portal-to-create-anti-phishing-policies) più indietro in questo articolo.  

   Per il criterio anti-phishing predefinito, la sezione **Utenti,** gruppi e domini non è disponibile (il criterio si applica a tutti) e non è possibile rinominare il criterio.

Per abilitare o disabilitare un criterio o impostare l'ordine di priorità dei criteri, vedere le sezioni seguenti.

### <a name="enable-or-disable-custom-anti-phishing-policies"></a>Abilitare o disabilitare i criteri anti-phishing personalizzati

Non è possibile disabilitare il criterio anti-phishing predefinito.

1. Nel portale Microsoft 365 Defender, passare **a** Criteri di collaborazione & e-mail & regole Criteri di minaccia sezione \>  \>  Criteri \>  \> **sezione Anti-phishing.**

2. Nella pagina **Anti-phishing** selezionare un criterio personalizzato nell'elenco facendo clic sul nome.

3. Nella parte superiore del riquadro a comparsa dei dettagli sui criteri visualizzato è presente uno dei valori seguenti:
   - **Criterio disattivato**: per attivare il criterio, fare clic su ![Attiva icona](../../media/m365-cc-sc-turn-on-off-icon.png) **Attiva** .
   - **Criterio attivato**: per disattivare il criterio, fare clic su ![Disattiva icona](../../media/m365-cc-sc-turn-on-off-icon.png) **Disattiva**.

4. Nella finestra di dialogo di conferma visualizzata fare clic su **Attiva** o **Disattiva**.

5. Fare clic su **Chiudi** nel riquadro a comparsa dei dettagli del criterio.

Tornare alla pagina dei criteri principale, il valore **Stato** del criterio sarà **Attivato** o **Disattivato**.

### <a name="set-the-priority-of-custom-anti-phishing-policies"></a>Impostare la priorità dei criteri anti-phishing personalizzati

Per impostazione predefinita, ai criteri anti-phishing viene data una priorità basata sull'ordine in cui sono stati creati (i criteri più recenti hanno una priorità più bassa rispetto ai criteri precedenti). Un valore di priorità inferiore indica una priorità più alta per il criterio (0 è il massimo) e i criteri vengono elaborati nell'ordine di priorità (i criteri con priorità più elevata vengono elaborati prima di quelli con priorità più bassa). Nessun criterio può avere la stessa priorità e l'elaborazione dei criteri termina dopo l'applicazione del primo criterio.

Per modificare la priorità di un criterio, fare clic su **Aumenta priorità** o **Riduci priorità** nelle proprietà del criterio. Non è possibile modificare direttamente il valore **Priorità** nel portale di Microsoft 365 Defender. La modifica di priorità di un criterio è utile solo se si hanno più criteri.

 **Note**:

- Nel portale Microsoft 365 Defender, è possibile modificare la priorità del criterio anti-phishing solo dopo aver creato il criterio. In PowerShell, è possibile ignorare la priorità predefinita quando si crea la regola anti-phish (che può influire sulla priorità delle regole esistenti).
- I criteri anti-phishing vengono elaborati nell'ordine in cui vengono visualizzati (il primo criterio ha il **valore Priority** 0). Il criterio anti-phishing predefinito ha il valore di priorità **Lowest** e non è possibile modificarlo.

1. Nel portale Microsoft 365 Defender, passare **a** Criteri di collaborazione & e-mail & regole Criteri di minaccia sezione \>  \>  Criteri \>  \> **sezione Anti-phishing.**

2. Nella pagina **Anti-phishing** selezionare un criterio personalizzato nell'elenco facendo clic sul nome.

3. Nella parte superiore del riquadro a comparsa dei dettagli sui criteri visualizzato viene visualizzato **Aumenta priorità** o **Riduci priorità** in base al valore di priorità corrente e al numero di criteri personalizzati:
   - Per il criterio con **valore Priority** **0 è** disponibile solo **l'opzione Riduci** priorità.
   - Il criterio con il valore **Di priorità** più basso (ad esempio, **3)** ha solo l'opzione **Aumenta** priorità disponibile.
   - Se si dispone di tre o più criteri, per i  criteri tra i valori di priorità più alta e più bassa sono disponibili le opzioni Aumenta priorità e **Riduci** priorità.

   Fare clic![ sull’icona Aumenta priorità](../../media/m365-cc-sc-increase-icon.png) **Aumenta priorità** o ![sull’icona Riduci priorità](../../media/m365-cc-sc-decrease-icon.png) **Riduci priorità** per modificare il valore **Priorità**.

4. Al termine, fare clic su **Chiudi** nel riquadro a comparsa dei dettagli del criterio.

## <a name="use-the-microsoft-365-defender-portal-to-remove-custom-anti-phishing-policies"></a>Utilizzare il portale Microsoft 365 Defender per rimuovere criteri anti-phishing personalizzati

Quando si utilizza il portale Microsoft 365 Defender per rimuovere un criterio anti-phishing personalizzato, la regola anti-phishing e il criterio anti-phishing corrispondente vengono eliminati entrambi. Non è possibile rimuovere il criterio anti-phishing predefinito.

1. Nel portale Microsoft 365 Defender, passare **a** Criteri di collaborazione & e-mail & regole Criteri di minaccia sezione \>  \>  Criteri \>  \> **sezione Anti-phishing.**

2. Nella pagina **Anti-phishing** selezionare un criterio personalizzato nell'elenco facendo clic sul nome del criterio.

3. Nella parte superiore del riquadro a comparsa dei dettagli sui criteri visualizzato fare clic![ sull'icona Altre azioni](../../media/m365-cc-sc-more-actions-icon.png) **Altre azioni** \> ![Icona Elimina criterio](../../media/m365-cc-sc-delete-icon.png) **Elimina criterio**.

4. Nella finestra di dialogo di conferma che viene visualizzata fare clic su **Sì**.

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies"></a>Utilizzare Exchange Online PowerShell per configurare i criteri anti-phishing

Come descritto in precedenza, un criterio di protezione da posta indesiderata è costituito da un criterio anti-phish e da una regola anti-phish.

In Exchange Online PowerShell, è evidente la differenza tra i criteri anti-phish e le regole anti-phish. È possibile gestire i criteri anti-phish utilizzando i cmdlet **\* -AntiPhishPolicy** e gestire le regole anti-phish utilizzando i cmdlet **\* -AntiPhishRule.**

- In PowerShell, si crea prima il criterio anti-phish, quindi si crea la regola anti-phish che identifica il criterio a cui si applica la regola.
- In PowerShell, le impostazioni dei criteri anti-phish e della regola anti-phish vengono modificate separatamente.
- Quando si rimuove un criterio anti-phish da PowerShell, la regola anti-phish corrispondente non viene rimossa automaticamente e viceversa.

### <a name="use-powershell-to-create-anti-phishing-policies"></a>Utilizzare PowerShell per creare criteri anti-phishing

La creazione di un criterio anti-phishing in PowerShell è un processo in due passaggi:

1. Creare i criteri anti-phish.
2. Creare la regola anti-phish che specifica il criterio anti-phish a cui si applica la regola.

 **Note**:

- È possibile creare una nuova regola anti-phish e assegnarle un criterio anti-phish esistente e non associazione. Una regola anti-phish non può essere associata a più di un criterio anti-phish.
- È possibile configurare le impostazioni seguenti nei nuovi criteri anti-phish in PowerShell che non sono disponibili nel portale di Microsoft 365 Defender fino a quando non si crea il criterio:
  - Creare il nuovo criterio come disabilitato (_Abilitato_ `$false` nel cmdlet **New-AntiPhishRule).**
  - Impostare la priorità del criterio durante la creazione (_Priority_ _\<Number\>_ ) nel cmdlet **New-AntiPhishRule.**
- Un nuovo criterio anti-phish creato in PowerShell non è visibile nel portale di Microsoft 365 Defender finché non si assegna il criterio a una regola anti-phish.

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a>Passaggio 1: Usare PowerShell per creare un criterio anti-phish

Per creare un criterio anti-phish, utilizzare la sintassi seguente:

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

In questo esempio viene creato un criterio anti-phish denominato Research Quarantine con le impostazioni seguenti:

- Il criterio è abilitato (non viene utilizzato il _parametro Enabled_ e il valore predefinito è `$true` ).
- La descrizione è: Criteri del reparto di ricerca.
- Abilita la protezione dei domini dell'organizzazione per tutti i domini accettati e la protezione dei domini di destinazione per fabrikam.com.
- Specifica Mai Fujito (mfujito@fabrikam.com) come l'utente da proteggere da imitazione.
- Abilita l'intelligence della cassetta postale.
- Abilita la protezione dell'intelligence delle cassette postali e specifica l'azione di quarantena.
- Abilita i suggerimenti per la sicurezza.

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -EnableOrganizationDomainsProtection $true -EnableTargetedDomainsProtection $true -TargetedDomainsToProtect fabrikam.com -TargetedDomainProtectionAction Quarantine -EnableTargetedUserProtection $true -TargetedUsersToProtect "Mai Fujito;mfujito@fabrikam.com" -TargetedUserProtectionAction Quarantine -EnableMailboxIntelligence $true -EnableMailboxIntelligenceProtection $true -MailboxIntelligenceProtectionAction Quarantine -EnableSimilarUsersSafetyTips $true -EnableSimilarDomainsSafetyTips $true -EnableUnusualCharactersSafetyTips $true
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere New-AntiPhishPolicy](/powershell/module/exchange/New-AntiPhishPolicy).

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a>Passaggio 2: Usare PowerShell per creare una regola anti-phish

Per creare una regola anti-phish, utilizzare la sintassi seguente:

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

In questo esempio viene creata una regola anti-phish denominata Research Department con le condizioni seguenti:

- La regola è associata al criterio anti-phish denominato Quarantena ricerche.
- La regola viene applicata ai membri del gruppo denominato Research Department.
- Poiché non si utilizza il parametro _Priority,_ viene utilizzata la priorità predefinita.

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere New-AntiPhishRule](/powershell/module/exchange/New-AntiPhishRule).

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

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Get-AntiPhishPolicy](/powershell/module/exchange/Get-AntiPhishPolicy).

### <a name="use-powershell-to-view-anti-phish-rules"></a>Usare PowerShell per visualizzare le regole anti-phish

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

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Get-AntiPhishRule](/powershell/module/exchange/Get-AntiPhishrule).

### <a name="use-powershell-to-modify-anti-phish-policies"></a>Utilizzare PowerShell per modificare i criteri anti-phish

Oltre agli elementi seguenti, le stesse impostazioni sono disponibili quando si modifica un criterio anti-phish in PowerShell come quando si crea il criterio come descritto nella sezione Passaggio 1: utilizzare PowerShell per creare un criterio [anti-phish](#step-1-use-powershell-to-create-an-anti-phish-policy) in precedenza in questo articolo.

- L'opzione _MakeDefault_ che trasforma il criterio specificato nel  criterio predefinito (applicato a tutti, sempre con priorità minima e non è possibile eliminarlo) è disponibile solo quando si modifica un criterio anti-phish in PowerShell.

- Non è possibile rinominare un criterio anti-phish (il cmdlet **Set-AntiPhishPolicy** non dispone di _alcun parametro Name)._ Quando si rinomina un criterio anti-phishing nel portale Microsoft 365 Defender, si rinomina solo la regola _anti-phishing._

Per modificare un criterio anti-phish, utilizzare la sintassi seguente:

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-AntiPhishPolicy.](/powershell/module/exchange/Set-AntiPhishPolicy)

### <a name="use-powershell-to-modify-anti-phish-rules"></a>Utilizzare PowerShell per modificare le regole anti-phish

L'unica impostazione non disponibile quando si modifica una regola anti-phish in PowerShell è il parametro _Enabled_ che consente di creare una regola disabilitata. Per abilitare o disabilitare le regole anti-phish esistenti, vedi la sezione successiva.

In caso contrario, non sono disponibili impostazioni aggiuntive quando si modifica una regola anti-phish in PowerShell. Le stesse impostazioni sono disponibili quando si crea una regola come descritto nella sezione Passaggio 2: Utilizzare PowerShell per creare una regola [anti-phish](#step-2-use-powershell-to-create-an-anti-phish-rule) in precedenza in questo articolo.

Per modificare una regola anti-phish, utilizzare la sintassi seguente:

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-AntiPhishRule.](/powershell/module/exchange/set-antiphishrule)

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a>Usare PowerShell per abilitare o disabilitare le regole anti-phish

L'abilitazione o la disabilitazione di una regola anti-phishing in PowerShell abilita o disabilita l'intero criterio anti-phishing (la regola anti-phishing e il criterio anti-phishing assegnato). Non è possibile abilitare o disabilitare il criterio anti-phishing predefinito (viene sempre applicato a tutti i destinatari).

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

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule) e [Disable-AntiPhishRule.](/powershell/module/exchange/disable-antiphishrule)

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a>Usare PowerShell per impostare la priorità delle regole anti-phish

Il valore di priorità più alto che è possibile impostare in una regola è 0. Il valore più basso che è possibile impostare dipende dal numero di regole. Se si dispone di cinque regole predefinite, è possibile utilizzare i valori di priorità da 0 a 4. Modificare la priorità di una regola esistente può avere un effetto a catena su altre regole. Ad esempio, se si dispone di cinque regole (priorità da 0 a 4) e si modifica la priorità di una regola a 2, la regola esistente con priorità 2 viene modificata a livello di priorità 3 e la regola con priorità 3 viene modificata a livello di priorità 4.

Per impostare la priorità di una regola anti-phish in PowerShell, utilizzare la sintassi seguente:

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

Nell'esempio seguente la priorità della regola denominata Marketing Department viene impostata su 2. Tutte le regole esistenti che hanno una priorità minore o uguale a 2 vengono abbassate di 1 valore (i numeri di priorità vengono aumentati di 1).

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

**Note**:

- Per impostare la priorità di una nuova regola al momento della creazione, utilizzare invece il parametro _Priority_ nel cmdlet **New-AntiPhishRule.**

- Il criterio anti-phish predefinito non dispone di una regola anti-phish corrispondente e ha sempre il valore di priorità non modificabile **Lowest**.

### <a name="use-powershell-to-remove-anti-phish-policies"></a>Usare PowerShell per rimuovere i criteri anti-phish

Quando si utilizza PowerShell per rimuovere un criterio anti-phish, la regola anti-phish corrispondente non viene rimossa.

Per rimuovere un criterio anti-phish in PowerShell, utilizzare la sintassi seguente:

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

In questo esempio viene rimosso il criterio anti-phish denominato Marketing Department.

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Remove-AntiPhishPolicy.](/powershell/module/exchange/Remove-AntiPhishPolicy)

### <a name="use-powershell-to-remove-anti-phish-rules"></a>Usare PowerShell per rimuovere le regole anti-phish

Quando si utilizza PowerShell per rimuovere una regola anti-phish, il criterio anti-phish corrispondente non viene rimosso.

Per rimuovere una regola anti-phish in PowerShell, utilizzare la sintassi seguente:

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

In questo esempio viene rimossa la regola anti-phish denominata Marketing Department.

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Remove-AntiPhishRule.](/powershell/module/exchange/Remove-AntiPhishRule)

## <a name="how-do-you-know-these-procedures-worked"></a>Come verificare se queste procedure hanno avuto esito positivo?

Per verificare di aver configurato correttamente i criteri anti-phishing in Defender per Office 365, eseguire una delle operazioni seguenti:

- Nel portale Microsoft 365 Defender, passare **a** Criteri di collaborazione & e-mail & regole Criteri di minaccia sezione \>  \>  Criteri \>  \> **sezione Anti-phishing.** Verificare l'elenco dei criteri, i **relativi valori status** e i relativi valori **Priority.** Per visualizzare altri dettagli, selezionare il criterio dall'elenco facendo clic sul nome e visualizzando i dettagli nel riquadro a comparsa visualizzato.

- In Exchange Online PowerShell, sostituire con il nome del criterio o della regola ed eseguire il \<Name\> comando seguente e verificare le impostazioni:

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
