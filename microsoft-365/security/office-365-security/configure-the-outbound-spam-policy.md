---
title: Configurare il filtro posta indesiderata in uscita
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a44764e9-a5d2-4c67-8888-e7fb871c17c7
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Gli amministratori possono imparare a visualizzare, creare, modificare ed eliminare i criteri di posta indesiderata in uscita in Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 97b429584371dbe49778163a7f1bbe6f36aea54c
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108416"
---
# <a name="configure-outbound-spam-filtering-in-eop"></a>Configurare il filtro posta indesiderata in uscita in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Nelle organizzazioni Microsoft 365 con cassette postali in Exchange Online o in organizzazioni di Exchange Online Protection (EOP) autonome senza cassette postali di Exchange Online, i messaggi di posta elettronica in uscita inviati tramite EOP vengono controllati automaticamente alla ricerca di posta indesiderata e attività di invio insolite.

La posta indesiderata in uscita da un utente dell'organizzazione indica in genere un account compromesso. I messaggi in uscita sospetti vengono contrassegnati come posta indesiderata (indipendentemente dal livello di probabilità di posta indesiderata o dal livello di probabilità di posta indesiderata) e vengono instradati attraverso il [pool](high-risk-delivery-pool-for-outbound-messages.md) di recapito ad alto rischio per proteggere la reputazione del servizio Microsoft 365 ,ovvero mantenere i server di posta elettronica di origine fuori dagli elenchi di indirizzi IP bloccati. Agli amministratori viene automaticamente notificata l'attività di posta elettronica in uscita sospetta e gli utenti bloccati tramite [criteri di avviso.](../../compliance/alert-policies.md)

EOP utilizza i criteri di posta indesiderata in uscita come parte della difesa generale dell'organizzazione dalla posta indesiderata. Per altre informazioni, vedere [Protezione dalla posta indesiderata](anti-spam-protection.md).

Gli amministratori possono visualizzare, modificare e configurare (ma non eliminare) il criterio di posta indesiderata in uscita predefinito. Per una maggiore granularità, è inoltre possibile creare criteri di posta indesiderata in uscita personalizzati che si applicano a utenti, gruppi o domini specifici dell'organizzazione. I criteri personalizzati hanno sempre la precedenza sul criterio predefinito, ma non è possibile modificarne la priorità (in funzione).

È possibile configurare i criteri di posta indesiderata in uscita nel portale di Microsoft 365 Microsoft 365 Defender o in PowerShell (Exchange Online PowerShell per le organizzazioni Microsoft 365 con cassette postali in Exchange Online; PowerShell EOP autonomo per le organizzazioni senza cassette postali di Exchange Online).

Gli elementi di base di un criterio di posta indesiderata in uscita in EOP sono:

- **Il criterio di filtro della posta** indesiderata in uscita : Specifica le azioni per i verdetti del filtro posta indesiderata in uscita e le opzioni di notifica.
- **Regola filtro posta indesiderata in uscita**: Specifica la priorità e i filtri destinatario (a chi si applica il criterio) per un criterio di filtro della posta indesiderata in uscita.

La differenza tra questi due elementi non è ovvia quando si gestiscono i criteri di protezione da posta indesiderata in uscita nel portale Microsoft 365 Defender:

- Quando si crea un criterio, si sta creando contemporaneamente una regola di filtro della posta indesiderata in uscita e il criterio di filtro della posta indesiderata in uscita associato utilizzando lo stesso nome per entrambi.
- Quando si modifica un criterio, le impostazioni relative al nome, alla priorità, abilitate o disabilitate e ai filtri destinatari modificano la regola di filtro della posta indesiderata in uscita. Tutte le altre impostazioni modificano il criterio di filtro della posta indesiderata in uscita associato.
- Quando si rimuove un criterio, la regola di filtro della posta indesiderata in uscita e il criterio di filtro della posta indesiderata in uscita associato vengono rimossi.

In PowerShell di Exchange Online o in EOP PowerShell autonomo i criteri e la regola vengono gestiti separatamente. Per ulteriori informazioni, vedere la sezione Use [Exchange Online PowerShell or standalone EOP PowerShell to configure outbound spam policies](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies) più avanti in questo articolo.

Ogni organizzazione dispone di un criterio di protezione da posta indesiderata in uscita predefinito denominato Default con queste proprietà:

- Il criterio viene applicato a tutti i destinatari dell'organizzazione, anche se al criterio non è associata alcuna regola di filtro della posta indesiderata in uscita (filtri destinatari).
- Il valore personalizzato della priorità del criterio è **Minore** e non può essere modificato (il criterio viene sempre applicato per ultimo). Qualsiasi criterio personalizzato creato avrà sempre una priorità più alta rispetto al criterio denominato Predefinito.
- Il criterio è quello predefinito (la proprietà **IsDefault** contiene il valore `True`), e non è possibile eliminarlo.

Per aumentare l'efficacia del filtro posta indesiderata in uscita, è possibile creare criteri di protezione da posta indesiderata in uscita personalizzati con impostazioni più rigorose applicate a utenti o gruppi di utenti specifici.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare?

- Per aprire il portale di Microsoft 365 Defender, andare alla pagina <https://security.microsoft.com>. Per passare direttamente alla pagina **Impostazioni di filtro della posta indesiderata**, usare <https://security.microsoft.com/antispam>.

- Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell). Per connettersi a PowerShell di EOP autonomo, vedere [Connettersi a PowerShell per Exchange Online Protection](/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Prima di eseguire le procedure descritte in questo articolo, occorre disporre delle autorizzazioni in **Exchange Online**:
  - Per aggiungere, modificare ed eliminare i criteri di posta indesiderata in uscita, è necessario essere membri dei gruppi di ruoli **Gestione** organizzazione o Amministratore **sicurezza.**
  - Per l'accesso in sola lettura ai criteri di posta indesiderata in uscita, è necessario essere membri dei gruppi di ruoli **Lettore** globale o **Lettore** di sicurezza.

  Per altre informazioni, vedere [Autorizzazioni in Exchange Online](/exchange/permissions-exo/permissions-exo).

  **Note**:

  - L'aggiunta di utenti al ruolo di Azure Active Directory corrispondente nell'interfaccia di amministrazione di Microsoft 365 fornisce agli utenti le autorizzazioni necessarie _e_ le autorizzazioni per altre funzionalità di Microsoft 365. Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](../../admin/add-users/about-admin-roles.md).
  - Anche il gruppo di ruoli di **Gestione organizzazione sola visualizzazione** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) offre inoltre l'accesso di sola lettura a tale funzionalità.

- Per le impostazioni consigliate per i criteri di posta indesiderata in uscita, vedere [EOP outbound spam filter settings](recommended-settings-for-eop-and-office365.md#eop-outbound-spam-policy-settings).

- I [](../../compliance/alert-policies.md) criteri di avviso predefiniti denominati Limite di invio  della posta elettronica **superato,** Modelli di invio di posta elettronica sospetti rilevati e Utente con restrizioni per l'invio di messaggi di posta elettronica già inviano notifiche di posta elettronica ai membri del gruppo **TenantAdmins** (**Amministratori** globali ) sull'attività insolita di posta elettronica in uscita e sugli utenti bloccati a causa della posta indesiderata in uscita. Per ulteriori informazioni, vedere [Verify the alert settings for restricted users](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users). È consigliabile utilizzare questi criteri di avviso anziché le opzioni di notifica nei criteri di posta indesiderata in uscita.

## <a name="use-the-microsoft-365-defender-portal-to-create-outbound-spam-policies"></a>Utilizzare il portale Microsoft 365 Defender per creare criteri di posta indesiderata in uscita

La creazione di un criterio di posta indesiderata in uscita personalizzato nel portale di Microsoft 365 Defender crea la regola di filtro della posta indesiderata e il criterio di filtro della posta indesiderata associato contemporaneamente utilizzando lo stesso nome per entrambi.

1. Nel portale Microsoft 365 Defender, passare a Posta **elettronica &** Criteri di collaborazione & \> **regole** \> **Criteri** \>  di \> minaccia sezione Criteri di protezione da posta indesiderata .

2. Nella pagina **Criteri di protezione da posta indesiderata** fare clic su Crea icona Crea criterio e quindi selezionare In uscita ![ ](../../media/m365-cc-sc-create-icon.png)  dall'elenco a discesa. 

3. Viene aperta la creazione guidata criteri. Nella pagina **Assegna un nome alla pagina criteri** configurare queste impostazioni:
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

5. Nella pagina **Impostazioni di** protezione visualizzata configurare le impostazioni seguenti:
   - **Limiti dei messaggi**: le impostazioni in questa sezione configurano i limiti per i messaggi di posta elettronica in uscita **Exchange Online** cassette postali:
     - **Impostare un limite per i messaggi esterni**: numero massimo di destinatari esterni all'ora.
     - **Impostare un limite per i messaggi interni**: Numero massimo di destinatari interni all'ora.
     - **Impostare un limite giornaliero per i messaggi**: Numero massimo totale di destinatari al giorno.

     Un valore valido è compreso tra 0 e 10000. Il valore predefinito è 0, ovvero vengono utilizzati i valori predefiniti del servizio. Per ulteriori informazioni, vedere [Limiti di invio.](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1)

    Immettere un valore nella casella oppure utilizzare le frecce di aumento/diminuzione nella casella.

   - **Restrizioni applicate agli utenti che raggiungono** il limite dei messaggi: selezionare un'azione dall'elenco a discesa quando viene superato uno dei limiti nella sezione **Impostazioni** di protezione.

     Per tutte le azioni,  i destinatari specificati nel criterio Utente con restrizioni per l'invio di avvisi di posta elettronica (e nell'impostazione Ora ridondante Notifica a questi utenti e gruppi se un mittente è bloccato **a** causa dell'invio di posta indesiderata in uscita più avanti in questa pagina) ricevono le notifiche tramite posta elettronica.

     - **Limitare l'invio della posta elettronica all'utente fino al giorno seguente:** questo è il valore predefinito. Le notifiche di posta elettronica vengono inviate e l'utente non sarà in grado di inviare altri messaggi fino al giorno successivo, in base all'ora UTC. L'amministratore non può ignorare questo blocco.
       - L'avviso attività denominato **Utente con restrizioni per** l'invio di messaggi di posta elettronica notifica agli amministratori (tramite posta elettronica e nella pagina **Visualizza** avvisi).
       - Vengono inoltre notificati tutti i destinatari specificati nell'impostazione Notifica a persone specifiche se un mittente è bloccato a causa dell'invio di posta indesiderata in uscita nel criterio. 
       - L'utente non sarà in grado di inviare altri messaggi fino al giorno successivo, in base all'ora UTC. L'amministratore non può ignorare questo blocco.
     - **Impedire** all'utente di inviare messaggi di posta  elettronica: le notifiche di posta elettronica vengono inviate, l'utente viene aggiunto agli utenti con restrizioni nel portale di Microsoft 365 Defender e l'utente non può inviare messaggi di posta elettronica finché non viene rimosso dagli utenti con restrizioni da un <https://security.microsoft.com/restrictedusers> amministratore.  Dopo che un amministratore ha rimosso l'utente dall'elenco, l'utente non sarà più limitato per quel giorno. Per istruzioni, vedere Rimozione di un utente dal portale utenti con [restrizioni dopo l'invio di posta indesiderata.](removing-user-from-restricted-users-portal-after-spam.md)
     - **Nessuna azione, solo avviso:** vengono inviate notifiche tramite posta elettronica.

   - **Regole di inoltro**: utilizzare le impostazioni di questa sezione per controllare l'inoltro automatico della posta elettronica **Exchange Online cassette postali** a mittenti esterni. Per ulteriori informazioni, vedere [Control automatic external email forwarding in Microsoft 365](external-email-forwarding.md).

     > [!NOTE]
     > Quando l'inoltro automatico è disabilitato, il destinatario riceverà un rapporto di mancato recapito (noto anche come rapporto di mancato recapito o messaggio di mancato recapito) se i mittenti esterni inviano messaggi di posta elettronica a una cassetta postale con inoltro sul posto. Se il messaggio viene inviato  da un mittente interno e il metodo di inoltro è l'inoltro delle cassette postali [(noto](/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) anche come _inoltro SMTP),_ il mittente interno otterrà il rapporto di mancato recapito. Il mittente interno non ottiene un rapporto di mancato recapito se l'inoltro è avvenuto a causa di una regola di Posta in arrivo.

     Selezionare una delle azioni seguenti **nell'elenco a** discesa Regole di inoltro automatico:

     - **Automatico - Controllato dal sistema:** consente al filtro posta indesiderata in uscita di controllare l'inoltro automatico della posta elettronica esterna. Questo è il valore predefinito.
     - **On**: L'inoltro automatico della posta elettronica esterna non è disabilitato dal criterio.
     - **Disattivato**: l'inoltro automatico della posta elettronica esterna è disabilitato dal criterio.

   - **Notifiche**: utilizzare le impostazioni nella sezione per configurare altri destinatari che devono ricevere copie e notifiche di messaggi di posta elettronica in uscita sospetti:

     - **Invia una copia di** messaggi in uscita sospetti che superano questi limiti a questi utenti e gruppi: questa impostazione aggiunge i destinatari specificati al campo Ccn dei messaggi in uscita sospetti.

       > [!NOTE]
       > Questa impostazione funziona solo nel criterio di posta indesiderata in uscita predefinito. Non funziona nei criteri di posta indesiderata in uscita personalizzati creati dall'utente.

       Per abilitare questa impostazione, selezionare la casella di controllo. Nella casella visualizzata fare clic nella casella, immettere un indirizzo di posta elettronica valido e quindi premere INVIO o selezionare il valore completo visualizzato sotto la casella.

       Ripetere questo passaggio tutte le volte necessarie. Per rimuovere un valore esistente, fare clic su Rimuovi ![Icona Rimuovi](../../media/m365-cc-sc-remove-selection-icon.png) accanto al valore.

   - **Notificare a questi utenti e gruppi se un mittente è bloccato a causa dell'invio di posta indesiderata in uscita**

     > [!IMPORTANT]
     >
     > - Questa impostazione è in fase di rimozione dai criteri di posta indesiderata in uscita.
     >
     > - Il criterio di  avviso predefinito denominato Utente a cui è stato impedito di inviare messaggi di posta elettronica invia già  notifiche tramite posta elettronica ai membri del gruppo **TenantAdmins** ( [](../../compliance/alert-policies.md) **Amministratori** globali ) quando gli utenti vengono bloccati a causa del superamento dei limiti nella sezione Limiti destinatari. **È consigliabile utilizzare il criterio** di avviso anziché questa impostazione nel criterio di posta indesiderata in uscita per inviare una notifica agli amministratori e ad altri utenti. Per istruzioni, vedere [Verificare le impostazioni degli avvisi per gli utenti con restrizioni.](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)

   Al termine dell'operazione, fare clic su **Avanti**.

6. Nella pagina **Controllo** visualizzata controllare le impostazioni. È possibile selezionare **Modifica** in ogni sezione per modificare le impostazioni all'interno della sezione. Oppure è possibile fare clic su **Indietro** o selezionare la pagina specifica della procedura guidata.

   Al termine, fare clic su **Crea**.

7. Nel messaggio di conferma visualizzato fare clic su **Fatto**.

## <a name="use-the-microsoft-365-defender-portal-to-view-outbound-spam-policies"></a>Utilizzare il portale Microsoft 365 Defender per visualizzare i criteri di posta indesiderata in uscita

1. Nel portale Microsoft 365 Defender, passare a Posta **elettronica &** Criteri di collaborazione & \> **regole** \> **Criteri** \>  di \> minaccia sezione Criteri di protezione da posta indesiderata .

2. Nella pagina **Criteri filtro posta indesiderata** cercare uno dei valori seguenti:
   - Il **valore Type** è Custom outbound spam **policy**
   - Il **valore Name** è **Anti-spam outbound policy (Default)**

   Nell'elenco dei criteri di protezione dalla posta indesiderata vengono visualizzate le proprietà seguenti:

   - **Nome**
   - **Stato**
   - **Priorità**
   - **Type**

3. Quando si seleziona un criterio di posta indesiderata in uscita facendo clic sul nome, le impostazioni dei criteri vengono visualizzate in un riquadro a comparsa.

## <a name="use-the-microsoft-365-defender-portal-to-modify-outbound-spam-policies"></a>Utilizzare il portale Microsoft 365 Defender per modificare i criteri di posta indesiderata in uscita

1. Nel portale Microsoft 365 Defender, passare a Posta **elettronica &** Criteri di collaborazione & \> **regole** \> **Criteri** \>  di \> minaccia sezione Criteri di protezione da posta indesiderata .

2. Nella pagina **Criteri di protezione da posta indesiderata** selezionare un criterio di posta indesiderata in uscita dall'elenco facendo clic sul nome:
   - Un criterio personalizzato creato in cui il valore nella colonna **Tipo** è Criterio di posta indesiderata **in uscita personalizzato.**
   - Il criterio predefinito denominato **Criterio di posta indesiderata in uscita (predefinito)**.

3. Nel riquadro a comparsa dei dettagli sui criteri visualizzato selezionare **Modifica** in ogni sezione per modificare le impostazioni all'interno della sezione. Per ulteriori informazioni sulle impostazioni, vedere la sezione precedente Utilizzare il portale Microsoft 365 Defender [per creare](#use-the-microsoft-365-defender-portal-to-create-outbound-spam-policies) criteri di posta indesiderata in uscita in questo articolo.

   Per il criterio di  posta indesiderata in uscita predefinito, la sezione Applicato a non è disponibile (il criterio si applica a tutti) e non è possibile rinominare il criterio.

Per abilitare o disabilitare un criterio, impostare l'ordine di priorità dei criteri o configurare le notifiche di quarantena per gli utenti finali. Vedere le sezioni seguenti.

### <a name="enable-or-disable-custom-outbound-spam-policies"></a>Abilitare o disabilitare i criteri di posta indesiderata in uscita personalizzati

Non è possibile disabilitare il criterio di posta indesiderata in uscita predefinito.

1. Nel portale Microsoft 365 Defender, passare a Posta **elettronica &** Criteri di collaborazione & \> **regole** \> **Criteri** \>  di \> minaccia sezione Criteri di protezione da posta indesiderata .

2. Nella pagina **Criteri di protezione** da posta indesiderata  selezionare un criterio con il valore **Tipo** di Criterio di posta indesiderata in uscita personalizzato dall'elenco facendo clic sul nome.

3. Nella parte superiore del riquadro a comparsa dei dettagli sui criteri visualizzato è presente uno dei valori seguenti:
   - **Criterio disattivato**: per attivare il criterio, fare clic su ![Attiva icona](../../media/m365-cc-sc-turn-on-off-icon.png) **Attiva** .
   - **Criterio attivato**: per disattivare il criterio, fare clic su ![Disattiva icona](../../media/m365-cc-sc-turn-on-off-icon.png) **Disattiva**.

4. Nella finestra di dialogo di conferma visualizzata fare clic su **Attiva** o **Disattiva**.

5. Fare clic su **Chiudi** nel riquadro a comparsa dei dettagli del criterio.

Tornare alla pagina dei criteri principale, il valore **Stato** del criterio sarà **Attivato** o **Disattivato**.

### <a name="set-the-priority-of-custom-outbound-spam-policies"></a>Impostare la priorità dei criteri di posta indesiderata in uscita personalizzati

Per impostazione predefinita, ai criteri di posta indesiderata in uscita viene data una priorità basata sull'ordine in cui sono stati creati (i criteri più recenti hanno una priorità inferiore rispetto ai criteri precedenti). Un valore di priorità inferiore indica una priorità più alta per il criterio (0 è il massimo) e i criteri vengono elaborati nell'ordine di priorità (i criteri con priorità più elevata vengono elaborati prima di quelli con priorità più bassa). Nessun criterio può avere la stessa priorità e l'elaborazione dei criteri termina dopo l'applicazione del primo criterio.

Per modificare la priorità di un criterio, fare clic su **Aumenta priorità** o **Riduci priorità** nelle proprietà del criterio. Non è possibile modificare direttamente il valore **Priorità** nel portale di Microsoft 365 Defender. La modifica di priorità di un criterio è utile solo se si hanno più criteri.

 **Note**:

- Nel portale Microsoft 365 Defender, è possibile modificare la priorità del criterio di posta indesiderata in uscita solo dopo aver creato il criterio. In PowerShell, è possibile sovrascrivere la priorità predefinita quando si crea la regola di filtro della posta indesiderata (che può interessare la priorità delle regole esistenti).
- I criteri di posta indesiderata in uscita vengono elaborati nell'ordine in cui vengono visualizzati (il primo criterio ha il **valore Priority** 0). Il criterio di posta indesiderata in uscita predefinito ha il valore di priorità **Lowest** e non è possibile modificarlo.

1. Nel portale Microsoft 365 Defender, passare a Posta **elettronica &** Criteri di collaborazione & \> **regole** \> **Criteri** \>  di \> minaccia sezione Criteri di protezione da posta indesiderata .

2. Nella pagina **Criteri di protezione** da posta indesiderata selezionare  un criterio con il valore **Tipo** di Criterio di protezione da posta indesiderata in uscita personalizzato nell'elenco facendo clic sul nome.

3. Nella parte superiore del riquadro a comparsa dei dettagli sui criteri visualizzato viene visualizzato **Aumenta priorità** o **Riduci priorità** in base al valore di priorità corrente e al numero di criteri personalizzati:
   - Il criterio di posta indesiderata in uscita con **il valore Priority** **0** ha solo l'opzione **Riduci** priorità disponibile.
   - Il criterio di posta indesiderata in uscita con il valore **di priorità** più basso (ad esempio, **3**) ha solo l'opzione **Aumenta** priorità disponibile.
   - Se si dispone di tre o più criteri di posta indesiderata  in uscita, i criteri tra i valori di priorità più alta e più bassa hanno entrambe le opzioni Aumenta priorità e Riduci **priorità** disponibili.

   Fare clic![ sull’icona Aumenta priorità](../../media/m365-cc-sc-increase-icon.png) **Aumenta priorità** o ![sull’icona Riduci priorità](../../media/m365-cc-sc-decrease-icon.png) **Riduci priorità** per modificare il valore **Priorità**.

4. Al termine, fare clic su **Chiudi** nel riquadro a comparsa dei dettagli del criterio.

## <a name="use-the-microsoft-365-defender-portal-to-remove-custom-outbound-spam-policies"></a>Utilizzare il portale Microsoft 365 Defender per rimuovere criteri di posta indesiderata in uscita personalizzati

Quando si utilizza il portale Microsoft 365 Defender per rimuovere un criterio di posta indesiderata in uscita personalizzato, la regola di filtro della posta indesiderata e il criterio di filtro della posta indesiderata corrispondente vengono eliminati entrambi. Non è possibile rimuovere il criterio di posta indesiderata in uscita predefinito.

1. Nel portale Microsoft 365 Defender, passare a Posta **elettronica &** Criteri di collaborazione & \> **regole** \> **Criteri** \>  di \> minaccia sezione Criteri di protezione da posta indesiderata .

2. Nella pagina **Criteri di protezione** da posta indesiderata  selezionare un criterio con il valore **Tipo** di Criterio di posta indesiderata in uscita personalizzato dall'elenco facendo clic sul nome. Nella parte superiore del riquadro a comparsa dei dettagli sui criteri visualizzato fare clic![ sull'icona Altre azioni](../../media/m365-cc-sc-more-actions-icon.png) **Altre azioni** \> ![Icona Elimina criterio](../../media/m365-cc-sc-delete-icon.png) **Elimina criterio**.

3. Nella finestra di dialogo di conferma che viene visualizzata fare clic su **Sì**.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies"></a>Utilizzare Exchange Online PowerShell o PowerShell EOP autonomo per configurare i criteri di posta indesiderata in uscita

Come descritto in precedenza, un criterio di posta indesiderata in uscita è costituito da un criterio di filtro della posta indesiderata in uscita e da una regola di filtro della posta indesiderata in uscita.

In Exchange Online PowerShell o PowerShell EOP autonomo, la differenza tra i criteri di filtro della posta indesiderata in uscita e le regole di filtro della posta indesiderata in uscita è evidente. È possibile gestire i criteri di filtro della posta indesiderata in uscita utilizzando i cmdlet **\* -HostedOutboundSpamFilterPolicy** e gestire le regole di filtro della posta indesiderata in uscita utilizzando i cmdlet **\* -HostedOutboundSpamFilterRule.**

- In PowerShell, si crea prima il criterio di filtro della posta indesiderata in uscita, quindi si crea la regola di filtro della posta indesiderata in uscita che identifica il criterio a cui si applica la regola.
- In PowerShell le impostazioni vengono modificate separatamente nei criteri di filtro della posta indesiderata in uscita e nella regola di filtro della posta indesiderata in uscita.
- Quando si rimuove un criterio di filtro della posta indesiderata in uscita da PowerShell, la regola di filtro della posta indesiderata in uscita corrispondente non viene rimossa automaticamente e viceversa.

### <a name="use-powershell-to-create-outbound-spam-policies"></a>Utilizzare PowerShell per creare criteri di posta indesiderata in uscita

La creazione di un criterio di posta indesiderata in uscita in PowerShell è un processo in due passaggi:

1. Creare il criterio di filtro della posta indesiderata in uscita.
2. Creare la regola di filtro della posta indesiderata in uscita che specifica il criterio di filtro della posta indesiderata in uscita a cui si applica la regola.

   **Note**:

   - È possibile creare una nuova regola di filtro della posta indesiderata in uscita e assegnarle un criterio di filtro della posta indesiderata in uscita esistente e non associazione. Una regola di filtro della posta indesiderata in uscita non può essere associata a più di un criterio di filtro della posta indesiderata in uscita.
   - È possibile configurare le impostazioni seguenti nei nuovi criteri di filtro della posta indesiderata in uscita in PowerShell che non sono disponibili nel portale di Microsoft 365 Defender fino a quando non si crea il criterio:
     - Creare il nuovo criterio come disabilitato (_Abilitato_ `$false` nel cmdlet **New-HostedOutboundSpamFilterRule).**
     - Impostare la priorità del criterio durante la creazione (_Priority_ _\<Number\>_ ) nel cmdlet **New-HostedOutboundSpamFilterRule.**
   - Un nuovo criterio di filtro della posta indesiderata in uscita creato in PowerShell non è visibile nel portale di Microsoft 365 Defender finché non si assegna il criterio a una regola di filtro della posta indesiderata in uscita.

#### <a name="step-1-use-powershell-to-create-an-outbound-spam-filter-policy"></a>Passaggio 1: Utilizzare PowerShell per creare un criterio di filtro della posta indesiderata in uscita

Per creare un criterio di filtro della posta indesiderata in uscita, utilizzare la sintassi seguente:

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

In questo esempio viene creato un nuovo criterio di filtro della posta indesiderata in uscita denominato Contoso Executives con le impostazioni seguenti:

- I limiti di frequenza dei destinatari sono limitati ai valori più piccoli predefiniti. Per ulteriori informazioni, vedere [Limiti di invio tra Microsoft 365 opzioni.](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)

- Dopo aver raggiunto uno dei limiti, all'utente viene impedito di inviare messaggi.

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "Contoso Executives" -RecipientLimitExternalPerHour 400 -RecipientLimitInternalPerHour 800 -RecipientLimitPerDay 800 -ActionWhenThresholdReached BlockUser
```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [New-HostedOutboundSpamFilterPolicy.](/powershell/module/exchange/new-hostedoutboundspamfilterpolicy)

#### <a name="step-2-use-powershell-to-create-an-outbound-spam-filter-rule"></a>Passaggio 2: Utilizzare PowerShell per creare una regola di filtro della posta indesiderata in uscita

Per creare una regola di filtro della posta indesiderata in uscita, utilizzare la sintassi seguente:

```PowerShell
New-HostedOutboundSpamFilterRule -Name "<RuleName>" -HostedOutboundSpamFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

In questo esempio viene creata una nuova regola di filtro della posta indesiderata in uscita denominata Contoso Executives con queste impostazioni:

- Il criterio di filtro della posta indesiderata in uscita denominato Contoso Executives è associato alla regola.
- La regola viene applicata ai membri del gruppo Contoso Executives Group.

```PowerShell
New-HostedOutboundSpamFilterRule -Name "Contoso Executives" -HostedOutboundSpamFilterPolicy "Contoso Executives" -FromMemberOf "Contoso Executives Group"
```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [New-HostedOutboundSpamFilterRule](/powershell/module/exchange/new-hostedoutboundspamfilterrule).

### <a name="use-powershell-to-view-outbound-spam-filter-policies"></a>Usare PowerShell per visualizzare i criteri di filtro della posta indesiderata in uscita

Per restituire un elenco riepilogativo di tutti i criteri di filtro della posta indesiderata in uscita, eseguire questo comando:

```PowerShell
Get-HostedOutboundSpamFilterPolicy
```

Per restituire informazioni dettagliate su uno specifico criterio di filtro della posta indesiderata in uscita, utilizzare la sintassi seguente:

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

In questo esempio vengono restituiti tutti i valori delle proprietà per il criterio di filtro della posta indesiderata in uscita denominato Executives.

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "Executives" | Format-List
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Get-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/get-hostedoutboundspamfilterpolicy).

### <a name="use-powershell-to-view-outbound-spam-filter-rules"></a>Utilizzare PowerShell per visualizzare le regole di filtro della posta indesiderata in uscita

Per visualizzare le regole di filtro della posta indesiderata in uscita esistenti, utilizzare la sintassi seguente:

```PowerShell
Get-HostedOutboundSpamFilterRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>]
```

Per restituire un elenco riepilogativo di tutte le regole di filtro della posta indesiderata in uscita, eseguire questo comando:

```PowerShell
Get-HostedOutboundSpamFilterRule
```

Per filtrare l'elenco in base alle regole abilitate o disabilitate, eseguire i comandi seguenti:

```PowerShell
Get-HostedOutboundSpamFilterRule -State Disabled
```

```PowerShell
Get-HostedOutboundSpamFilterRule -State Enabled
```

Per restituire informazioni dettagliate su una specifica regola di filtro della posta indesiderata in uscita, utilizzare la sintassi seguente:

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

In questo esempio vengono restituiti tutti i valori delle proprietà per la regola di filtro della posta indesiderata in uscita denominata Contoso Executives.

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "Contoso Executives" | Format-List
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Get-HostedOutboundSpamFilterRule](/powershell/module/exchange/get-hostedoutboundspamfilterrule).

### <a name="use-powershell-to-modify-outbound-spam-filter-policies"></a>Utilizzare PowerShell per modificare i criteri di filtro della posta indesiderata in uscita

Le stesse impostazioni sono disponibili quando si modifica un criterio di filtro antimalware in PowerShell come quando si crea il criterio come descritto nella sezione [Passaggio 1:](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) utilizzare PowerShell per creare un criterio di filtro della posta indesiderata in uscita in precedenza in questo articolo.

> [!NOTE]
> Non è possibile rinominare un criterio di filtro della posta indesiderata in uscita (il cmdlet **Set-HostedOutboundSpamFilterPolicy** non dispone di _alcun parametro Name)._ Quando si rinomina un criterio di posta indesiderata in uscita nel portale Microsoft 365 Defender, si rinomina solo la regola di filtro della posta indesiderata in _uscita._

Per modificare un criterio di filtro della posta indesiderata in uscita, utilizzare la sintassi seguente:

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" <Settings>
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-HostedOutboundSpamFilterPolicy.](/powershell/module/exchange/set-hostedoutboundspamfilterpolicy)

### <a name="use-powershell-to-modify-outbound-spam-filter-rules"></a>Utilizzare PowerShell per modificare le regole di filtro della posta indesiderata in uscita

L'unica impostazione non disponibile quando si modifica una regola di filtro della posta indesiderata in uscita in PowerShell è il parametro _Enabled_ che consente di creare una regola disabilitata. Per abilitare o disabilitare le regole di filtro della posta indesiderata in uscita esistenti, vedere la sezione successiva.

In caso contrario, non sono disponibili impostazioni aggiuntive quando si modifica una regola di filtro della posta indesiderata in uscita in PowerShell. Le stesse impostazioni sono disponibili quando si crea una regola come descritto nella sezione [Passaggio 2:](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) Utilizzare PowerShell per creare una regola di filtro della posta indesiderata in uscita più indietro in questo articolo.

Per modificare una regola di filtro della posta indesiderata in uscita, utilizzare la sintassi seguente:

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" <Settings>
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-HostedOutboundSpamFilterRule](/powershell/module/exchange/set-hostedoutboundspamfilterrule).

### <a name="use-powershell-to-enable-or-disable-outbound-spam-filter-rules"></a>Utilizzare PowerShell per abilitare o disabilitare le regole di filtro della posta indesiderata in uscita

L'abilitazione o la disabilitazione di una regola di filtro della posta indesiderata in uscita in PowerShell abilita o disabilita l'intero criterio di posta indesiderata in uscita (la regola di filtro della posta indesiderata in uscita e il criterio di filtro della posta indesiderata in uscita assegnato). Non è possibile abilitare o disabilitare il criterio di posta indesiderata in uscita predefinito (viene sempre applicato a tutti i destinatari).

Per abilitare o disabilitare una regola di filtro della posta indesiderata in uscita in PowerShell, utilizzare la sintassi seguente:

```PowerShell
<Enable-HostedOutboundSpamFilterRule | Disable-HostedOutboundSpamFilterRule> -Identity "<RuleName>"
```

In questo esempio viene disabilitata la regola di filtro della posta indesiderata in uscita denominata Marketing Department.

```PowerShell
Disable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

In questo esempio viene abilitata la stessa regola.

```PowerShell
Enable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Enable-HostedOutboundSpamFilterRule](/powershell/module/exchange/enable-hostedoutboundspamfilterrule) [e Disable-HostedOutboundSpamFilterRule](/powershell/module/exchange/disable-hostedoutboundspamfilterrule).

### <a name="use-powershell-to-set-the-priority-of-outbound-spam-filter-rules"></a>Utilizzare PowerShell per impostare la priorità delle regole di filtro della posta indesiderata in uscita

Il valore di priorità più alto che è possibile impostare in una regola è 0. Il valore più basso che è possibile impostare dipende dal numero di regole. Se si dispone di cinque regole predefinite, è possibile utilizzare i valori di priorità da 0 a 4. Modificare la priorità di una regola esistente può avere un effetto a catena su altre regole. Ad esempio, se si dispone di cinque regole (priorità da 0 a 4) e si modifica la priorità di una regola a 2, la regola esistente con priorità 2 viene modificata a livello di priorità 3 e la regola con priorità 3 viene modificata a livello di priorità 4.

Per impostare la priorità di una regola di filtro della posta indesiderata in uscita in PowerShell, utilizzare la sintassi seguente:

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" -Priority <Number>
```

Nell'esempio seguente la priorità della regola denominata Marketing Department viene impostata su 2. Tutte le regole esistenti che hanno una priorità minore o uguale a 2 vengono abbassate di 1 valore (i numeri di priorità vengono aumentati di 1).

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "Marketing Department" -Priority 2
```

**Note**:

- Per impostare la priorità di una nuova regola al momento della creazione, utilizzare il parametro _Priority_ nel cmdlet **New-HostedOutboundSpamFilterRule.**
- Il criterio di filtro della posta indesiderata predefinito in uscita non dispone di una regola di filtro della posta indesiderata corrispondente e ha sempre il valore di priorità non modificabile **Lowest**.

### <a name="use-powershell-to-remove-outbound-spam-filter-policies"></a>Utilizzare PowerShell per rimuovere i criteri di filtro della posta indesiderata in uscita

Quando si utilizza PowerShell per rimuovere un criterio di filtro della posta indesiderata in uscita, la regola di filtro della posta indesiderata in uscita corrispondente non viene rimossa.

Per rimuovere un criterio di filtro della posta indesiderata in uscita in PowerShell, utilizzare questa sintassi:

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>"
```

In questo esempio viene rimosso il criterio di filtro della posta indesiderata in uscita denominato Marketing Department.

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "Marketing Department"
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Remove-HostedOutboundSpamFilterPolicy.](/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy)

### <a name="use-powershell-to-remove-outbound-spam-filter-rules"></a>Utilizzare PowerShell per rimuovere le regole di filtro della posta indesiderata in uscita

Quando si utilizza PowerShell per rimuovere una regola di filtro della posta indesiderata in uscita, il criterio di filtro della posta indesiderata in uscita corrispondente non viene rimosso.

Per rimuovere una regola di filtro della posta indesiderata in uscita in PowerShell, utilizzare la sintassi seguente:

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "<PolicyName>"
```

In questo esempio viene rimossa la regola di filtro della posta indesiderata in uscita denominata Marketing Department.

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Remove-HostedOutboundSpamFilterRule](/powershell/module/exchange/remove-hostedoutboundspamfilterrule).

## <a name="for-more-information"></a>Ulteriori informazioni

[Rimuovere gli utenti bloccati dal portale utenti con restrizioni](removing-user-from-restricted-users-portal-after-spam.md)

[Pool di recapito ad alto rischio per i messaggi in uscita](high-risk-delivery-pool-for-outbound-messages.md)

[Domande frequenti sulla protezione da posta indesiderata](anti-spam-protection-faq.yml)

[Report dei messaggi inoltrati automaticamente](mfi-auto-forwarded-messages-report.md)
