---
title: Creare un ambiente di condivisione guest sicuro
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-security-compliance
- M365solutions
ms.custom:
- seo-marvel-apr2020
localization_priority: Priority
f1.keywords: NOCSH
description: Questo articolo offre informazioni sulle opzioni disponibili per creare un ambiente di condivisione guest sicuro in Microsoft 365.
ms.openlocfilehash: b567be8df8d0b9dc96400627c6607560fefd9c39
ms.sourcegitcommit: 9c828bc27cd73a1bb85e9fe38d818190025ebb3f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2020
ms.locfileid: "44159480"
---
# <a name="create-a-secure-guest-sharing-environment"></a>Creare un ambiente di condivisione guest sicuro

In questo articolo verranno descritte varie opzioni per la creazione di un ambiente di condivisione guest sicuro in Microsoft 365. Si tratta di uno scenario di esempio pensato per offrire una panoramica delle opzioni disponibili. È possibile usare queste procedure in diverse combinazioni per soddisfare le esigenze di sicurezza e conformità della propria organizzazione. Alla fine dell'articolo verrà illustrato un test case per osservare il funzionamento combinato di alcune di queste opzioni.

Questo scenario include:

- Configurazione dell'autenticazione a più fattori per i guest.
- Configurazione di condizioni per l'utilizzo per gli utenti guest.
- Configurazione di verifiche trimestrali dell'accesso guest per controllare periodicamente se per gli utenti guest continuano a essere necessarie autorizzazioni per team e siti.
- Limitazione degli utenti guest all'accesso solo Web per i dispositivi non gestiti.
- Configurazione di criteri di timeout della sessione per assicurarsi che gli utenti guest eseguano l'autenticazione quotidianamente.
- Creazione e pubblicazione di etichette di riservatezza per classificare il contenuto.
- Creazione di un tipo di informazioni sensibili per un progetto estremamente riservato.
- Assegnazione automatica di un'etichetta *Estremamente riservato* ai documenti che contengono il tipo di informazioni sensibili.
- Rimozione automatica dell'accesso guest dai file etichettati come *estremamente riservati*.

Alcune delle opzioni descritte in questo articolo richiedono che i guest abbiano un account in Azure Active Directory. Per fare in modo che gli utenti guest siano inclusi nella directory quando si condividono con loro file e cartelle, usare l'[anteprima dell'integrazione di SharePoint e OneDrive con Azure AD B2B](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview).

Si noti che in questo articolo non verranno illustrate le impostazioni per l'abilitazione della condivisione guest. Per informazioni dettagliate su come abilitare la condivisione guest per scenari diversi, vedere [Collaborare con utenti esterni all'organizzazione](https://docs.microsoft.com/Office365/Enterprise/collaborate-with-people-outside-your-organization).

## <a name="set-up-multi-factor-authentication-for-guests"></a>Configurare l'autenticazione a più fattori per gli utenti guest

L'autenticazione a più fattori riduce notevolmente la possibilità di compromissione di un account. Dal momento che gli utenti guest possono usare account di posta elettronica personali che non aderiscono a criteri di governance o procedure consigliate, richiedere l'autenticazione a più fattori per i guest è particolarmente importante. Qualora il nome utente e la password di un utente guest fossero rubati, l'uso di un secondo fattore di autenticazione ridurrebbe notevolmente le possibilità che soggetti sconosciuti possano accedere ai siti e ai file dell'organizzazione.

In questo esempio verrà configurata l'autenticazione a più fattori per gli utenti guest usando criteri di accesso condizionale in Azure Active Directory.

Per configurare l'autenticazione a più fattori per i guest
1. In Microsoft Azure cercare *Accesso condizionale*.
2. Nel pannello **Accesso condizionale - Criteri** selezionare **Nuovi criteri**.
3. Nel campo **Nome** digitare *MFA guest*.
4. In **Assegnazioni** fare clic su **Utenti e gruppi**.
5. Nel pannello **Utenti e gruppi** scegliere **Seleziona utenti e gruppi**, selezionare la casella di controllo **Tutti gli utenti guest ed esterni** e quindi fare clic su **Fatto**.
4. In **Controlli di accesso** fare clic su **Concedi**.
5. Nel pannello **Concedi** selezionare la casella di controllo **Richiedi autenticazione a più fattori** e quindi fare clic su **Seleziona**.
6. Nel pannello **Nuovo**, in **Abilita criterio** fare clic su **Sì** e quindi su **Crea**.

Ora gli utenti guest dovranno effettuare la registrazione all'autenticazione a più fattori per poter accedere a team, siti o contenuti condivisi.

### <a name="more-information"></a>Altre informazioni

[Pianificazione di una distribuzione di Azure Multi-Factor Authentication basata su cloud](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted)

## <a name="set-up-a-terms-of-use-for-guests"></a>Configurare un documento di condizioni per l'utilizzo per gli utenti guest

Spesso gli utenti guest non hanno firmato accordi di non divulgazione o altri accordi legali con l'organizzazione. Si può richiedere ai guest di accettare le condizioni per l'utilizzo prima di accedere ai file che sono stati condivisi con loro. Le condizioni per l'utilizzo possono essere visualizzate al primo tentativo di accesso a un file o a un sito condiviso.

Per creare le condizioni di utilizzo, è necessario prima di tutto creare il documento in Word o in un'altra applicazione e quindi salvarlo come file PDF. Successivamente, si potrà caricare il file in Azure AD.

Per creare un documento di condizioni per l'utilizzo di Azure AD
1. Accedere ad Azure come amministratore globale, amministratore della sicurezza o amministratore di accesso condizionale.
2. Passare a [Condizioni per l'utilizzo](https://aka.ms/catou).
3. Fare clic su **Nuove condizioni**.</br>
   ![Screenshot delle impostazioni per le nuove condizioni per l'utilizzo di Azure AD](../media/azure-ad-guest-terms-of-use.png)
4. Nelle caselle **Nome** e **Nome visualizzato** digitare *Condizioni per l'utilizzo guest*.
6. Per **Documento sulle Condizioni per l'utilizzo** passare al file PDF creato e selezionarlo.
7. Selezionare la lingua per il documento delle condizioni per l'utilizzo.
8. Impostare **Richiedi agli utenti di espandere le Condizioni per l'utilizzo** su **Attivata**.
9. In **Accesso condizionale**, nell'elenco **Applica con i modelli di criteri per l'accesso condizionale** scegliere **Crea criteri di accesso condizionale in seguito**.
10. Fare clic su **Crea**.

Dopo aver creato le condizioni per l'utilizzo, il passaggio successivo consiste nel creare criteri di accesso condizionale che mostrano il documento agli utenti guest.

Per creare i criteri di accesso condizionale
1. In Microsoft Azure cercare *Accesso condizionale*.
2. Nel pannello **Accesso condizionale - Criteri** selezionare **Nuovi criteri**.
3. Nella casella **Nome** digitare *Condizioni per l'utilizzo per gli utenti guest*.
4. In **Assegnazioni** fare clic su **Utenti e gruppi**.
5. Nel pannello **Utenti e gruppi** scegliere **Seleziona utenti e gruppi**, selezionare la casella di controllo **Tutti gli utenti guest ed esterni** e quindi fare clic su **Fatto**.
6. In **Assegnazioni** fare clic su **Applicazioni cloud o azioni**.
7. Nella scheda **Includi** scegliere **Seleziona le app** e quindi fare clic su **Seleziona**.
8. Nel pannello **Seleziona** scegliere **Microsoft Teams**, **Office 365 SharePoint Online** e **Outlook Groups **, quindi fare clic su **Seleziona**.
9. Nel pannello **Applicazioni cloud o azioni** fare clic su **Fatto**.
10. In **Controlli di accesso** fare clic su **Concedi**.
11. Nel pannello **Concedi** selezionare **Condizioni per l'utilizzo guest** e quindi fare clic su **Seleziona**.
12. Nel pannello **Nuovo**, in **Abilita criterio** fare clic su **Sì** e quindi su **Crea**.

Ora, la prima volta che un utente guest tenterà di accedere al contenuto, a un team o a un sito dell'organizzazione, dovrà accettare le condizioni per l'utilizzo.

### <a name="more-information"></a>Altre informazioni
[Condizioni per l'utilizzo di Azure Active Directory](https://docs.microsoft.com/azure/active-directory/conditional-access/terms-of-use)

## <a name="set-up-guest-access-reviews"></a>Configurare le verifiche di accesso per gli utenti guest

Le verifiche di accesso in Azure AD consentono di automatizzare una revisione periodica dell'accesso degli utenti a diversi team e gruppi. Richiedendo una verifica di accesso per gli utenti guest, ci si può assicurare che questi ultimi non mantengano l'accesso alle informazioni riservate dell'organizzazione più a lungo del necessario.

Le verifiche di accesso possono essere organizzate in programmi. Un programma è un raggruppamento di verifiche di accesso simili, che è possibile usare per organizzare le verifiche di accesso a scopi di reporting e controllo.

In questo esempio si creerà un programma per le verifiche di accesso degli utenti guest.

Per creare un programma
1. Accedere al portale di Azure e aprire la pagina [Identity Governance](https://portal.azure.com/#blade/Microsoft_AAD_ERM/DashboardBlade).
2. Nel menu a sinistra fare clic su **Programmi**.
3. Fare clic su **Nuovo programma**.
4. Nella casella **Nome** digitare *Programma verifiche accesso guest*.
5. Nella casella **Descrizione** digitare *Programma per le verifiche di accesso degli utenti guest*.
6. Fare clic su **Crea**.

Una volta creato il programma, è possibile creare una verifica di accesso guest e associarla al programma.

Per configurare una verifica di accesso per gli utenti guest
1. Nel menu a sinistra della pagina [Identity Governance](https://portal.azure.com/#blade/Microsoft_AAD_ERM/DashboardBlade) fare clic su **Verifiche di accesso**.
2. Fare clic su **Nuova verifica di accesso**.</br>
   ![Screenshot delle impostazioni di verifica di accesso di Azure AD](../media/azure-ad-create-access-review.png)
3. Nella casella **Nome** digitare *Verifica trimestrale accesso guest*.
4. Per **Frequenza** scegliere **Trimestrale**.
5. Per **Fine** scegliere **Mai**.
6. Per **Ambito** scegliere **Solo utenti guest**.
7. Fare clic su **Raggruppa**, selezionare i gruppi che si vogliono includere nella verifica di accesso e quindi fare clic su **Seleziona**.
8. In **Programmi** fare clic su **Collegamento al programma**.
9. Nel pannello **Selezionare un programma** scegliere **Programma verifiche accesso guest**
10. Fare clic su **Avvia**.

Verrà creata una revisione di accesso separata per ogni gruppo specificato. I proprietari di ogni gruppo riceveranno un messaggio di posta elettronica trimestrale per approvare o negare l'accesso guest ai propri gruppi.

È importante tenere presente che è possibile concedere ai guest l'accesso a team o gruppi oppure a singoli file e cartelle. Quando si fornisce loro l'accesso a file e cartelle, gli utenti guest possono anche non far parte di un gruppo specifico. Se si vogliono eseguire verifiche di accesso sugli utenti guest che non appartengono a un team o a un gruppo, è possibile creare un gruppo dinamico in Azure AD per includere tutti i guest e quindi creare una verifica di accesso per tale gruppo.

### <a name="more-information"></a>Altre informazioni
[Gestire l'accesso guest con le verifiche di accesso di Azure AD](https://docs.microsoft.com/azure/active-directory/governance/manage-guest-access-with-access-reviews)

[Creare una verifica di accesso di gruppi o applicazioni nelle verifiche di accesso di Azure AD](https://docs.microsoft.com/azure/active-directory/governance/create-access-review)

## <a name="set-up-web-only-access-for-guest-users"></a>Configurare l'accesso solo Web per gli utenti guest

Richiedendo agli utenti guest di accedere ai team, ai siti e ai file solo tramite un Web browser, è possibile ridurre la superficie di attacco e semplificare l'amministrazione. Per fare questo si usano i criteri di accesso condizionale di Azure AD.

Per limitare i guest al solo accesso Web
1. In Microsoft Azure cercare *Accesso condizionale*.
2. Nel pannello **Accesso condizionale - Criteri** selezionare **Nuovi criteri**.
3. Nella casella **Nome** digitare *Accesso browser utenti guest*.
4. In **Assegnazioni** fare clic su **Utenti e gruppi**.
5. Nel pannello **Utenti e gruppi** scegliere **Seleziona utenti e gruppi**, selezionare la casella di controllo **Tutti gli utenti guest ed esterni** e quindi fare clic su **Fatto**.
6. In **Assegnazioni** fare clic su **Applicazioni cloud o azioni**.
7. Nella scheda **Includi** scegliere **Seleziona le app** e quindi fare clic su **Seleziona**.
8. Nel pannello **Seleziona** scegliere **Microsoft Teams**, **Office 365 SharePoint Online** e **Outlook Groups **, quindi fare clic su **Seleziona**.
9. Nel pannello **Applicazioni cloud o azioni** fare clic su **Fatto**.
10. In **Assegnazioni** fare clic su **Condizioni**.
11. Nel pannello **Condizioni** fare clic su **App client**.
12. Nel pannello **App client** fare clic su **Sì** per **Configura** e quindi selezionare le impostazioni **App per dispositivi mobili e client desktop** e **Client con autenticazione moderna**.</br>
    ![Screenshot delle impostazioni per le app client dell'accesso condizionale di Azure AD](../media/azure-ad-conditional-access-client-mobile.png)
13. Fare clic su **Fatto** e quindi sul pannello **Condizioni** fare di nuovo clic su **Fatto**.
14. In **Controlli di accesso** fare clic su **Concedi**.
15. Nel pannello **Concedi** selezionare **Richiedi che i dispositivi siano contrassegnati come conformi** e **Richiedi dispositivo aggiunto ad Azure AD ibrido**.
16. In **Per più controlli** selezionare **Richiedi uno dei controlli selezionati** e quindi fare clic su **Seleziona**.
17. Nel pannello **Nuovo**, in **Abilita criterio** fare clic su **Sì** e quindi su **Crea**.

## <a name="configure-a-session-timeout-for-guest-users"></a>Configurare un timeout della sessione per gli utenti guest

Richiedere ai guest di eseguire l'autenticazione a intervalli regolari può ridurre la possibilità che utenti sconosciuti accedano al contenuto dell'organizzazione se il dispositivo di un utente guest non è mantenuto al sicuro. È possibile configurare un criterio di accesso condizionale di timeout della sessione per gli utenti guest in Azure AD.

Per configurare un criterio di timeout della sessione guest
1. In Microsoft Azure cercare *Accesso condizionale*.
2. Nel pannello **Accesso condizionale - Criteri** selezionare **Nuovi criteri**.
3. Nella casella **Nome** digitare *Timeout sessioni guest*.
4. In **Assegnazioni** fare clic su **Utenti e gruppi**.
5. Nel pannello **Utenti e gruppi** scegliere **Seleziona utenti e gruppi**, selezionare la casella di controllo **Tutti gli utenti guest ed esterni** e quindi fare clic su **Fatto**.
6. In **Assegnazioni** fare clic su **Applicazioni cloud o azioni**.
7. Nella scheda **Includi** scegliere **Seleziona le app** e quindi fare clic su **Seleziona**.
8. Nel pannello **Seleziona** scegliere **Microsoft Teams**, **Office 365 SharePoint Online** e **Outlook Groups **, quindi fare clic su **Seleziona**.
9. Nel pannello **Applicazioni cloud o azioni** fare clic su **Fatto**.
10. In **Controlli di accesso** fare clic su **Sessione**.
11. Nel pannello **Sessione** selezionare **Frequenza di accesso**.
12. Selezionare **1** e **Giorni** per il periodo di tempo e quindi fare clic su **Seleziona**.
13. Nel pannello **Nuovo**, in **Abilita criterio** fare clic su **Sì** e quindi su **Crea**.

## <a name="create-sensitivity-labels"></a>Creare etichette di riservatezza

Le etichette di riservatezza possono essere usate in vari modi per classificare e proteggere le informazioni dell'organizzazione. In questo esempio viene illustrato come usare le etichette per semplificare la gestione dell'accesso guest a cartelle e file condivisi.

Prima di tutto, si creeranno tre etichette di riservatezza nel Centro conformità di Microsoft 365:

- Generale
- Riservato
- Estremamente riservato

Attenersi alla procedura seguente per creare le etichette *Generale* e *Riservato*.

Per creare un'etichetta di classificazione (Generale e Riservato)
1. Nel riquadro di spostamento sinistro del [Centro conformità Microsoft 365](https://compliance.microsoft.com) espandere **Classificazione** e quindi fare clic su **Etichette di riservatezza**.
2. Fare clic su **Crea un'etichetta**.
3. In **Nome etichetta** digitare *Generale* o *Riservato*.
4. In **Descrizione comando** digitare *Informazioni generali che possono essere condivise con dipendenti, guest e partner* o *Informazioni riservate. Condividere solo con dipendenti e guest autorizzati* e quindi fare clic su **Avanti**.
5. Lasciare la crittografia** **disattivata e fare clic su **Avanti**.
6. Lasciare il contrassegno dei contenuti** **disattivato e fare clic su **Avanti**.
7. Lasciare la prevenzione della perdita dei dati degli endpoint** **disattivata e fare clic su **Avanti**.
8. Lasciare l'applicazione automatica di etichette** **disattivata e fare clic su **Avanti**.
9. Fare clic su **Crea**.

Con l'etichetta *Estremamente riservato*, ai documenti verranno aggiunte automaticamente filigrane con l'etichetta.

Per creare un'etichetta di classificazione (Estremamente riservato)
1. Fare clic su **Crea un'etichetta**.
2. In **Nome etichetta** digitare *Estremamente riservato*.
3. In **Descrizione comando** digitare *Informazioni estremamente riservate. Non condividere con utenti guest*, e quindi fare clic su **Avanti**.
4. Lasciare la crittografia** **disattivata e fare clic su **Avanti**.
5. Attivare il** **contrassegno contenuti, selezionare la casella di controllo **Aggiungi un'intestazione** e quindi fare clic su **Personalizza testo**.
6. Digitare *Estremamente riservato* come testo dell'intestazione e quindi fare clic su **Salva**.
7. Nella pagina **Contrassegno contenuti**** **attivare il contrassegno dei contenuti.
8. Selezionare la casella di controllo **Aggiungi a filigrana** e quindi fare clic su **Personalizza testo**.
9. Per **Testo della filigrana** digitare *Estremamente riservato*.
10. Digitare *24* per **Dimensioni carattere** e quindi fare clic su **Salva**.
11. Nella pagina **Contrassegno contenuti** fare clic su **Avanti**.
12. Lasciare la prevenzione della perdita dei dati degli endpoint** **disattivata e fare clic su **Avanti**.
13. Lasciare l'applicazione automatica di etichette** **disattivata e fare clic su **Avanti**.
14. Fare clic su **Crea**.

![Screenshot delle etichette di riservatezza nel Centro conformità di Microsoft 365](../media/microsoft-365-sharing-sensitivity-labels.png)

Dopo aver creato le etichette, il passaggio successivo consiste nel pubblicarle. 

Per pubblicare le etichette
1. Nella pagina **Etichette di riservatezza** fare clic su **Pubblica etichette**.
2. Fare clic su **Scegliere le etichette da pubblicare**.
3. Fare clic su **Aggiungi**, selezionare le etichette create e quindi fare clic su **Aggiungi**.
4. Fare clic su **Fatto**.
5. Fare clic su **Avanti**.
6. Lasciare gli utenti e i gruppi impostati su **Tutti** e fare clic su **Avanti**.
7. Nell'elenco **Applica questa etichetta per impostazione predefinita a documenti e messaggi di posta elettronica** scegliere **Generale** e quindi fare clic su **Avanti**.
8. Nella pagina **Impostazioni criteri** digitare *Riservatezza documento * come nome e quindi fare clic su **Avanti**.
9. Fare clic su **Pubblica**.

Dopo la pubblicazione, le etichette sono disponibili agli utenti delle app desktop di Office. Quando gli utenti applicano l'etichetta **Estremamente riservato**, al documento viene aggiunta automaticamente una filigrana.

### <a name="more-information"></a>Ulteriori informazioni
[Panoramica delle etichette di riservatezza](https://docs.microsoft.com/Office365/SecurityCompliance/sensitivity-labels)

## <a name="create-a-sensitive-information-type-for-a-highly-sensitive-project"></a>Creare un tipo di informazioni sensibili per un progetto estremamente riservato

I tipi di informazioni sensibili sono stringhe predefinite che è possibile usare nei flussi di lavoro dei criteri per applicare i requisiti di conformità. Il Centro conformità di Microsoft 365 include oltre 100 tipi di informazioni sensibili, tra cui numeri di patente, numeri di carta di credito, numeri di conto corrente bancario e così via.

È possibile creare tipi personalizzati di informazioni sensibili per facilitare la gestione di contenuto specifico dell'organizzazione. In questo esempio verrà creato un tipo di informazioni sensibili personalizzato per un progetto estremamente riservato. Si potrà poi usare questo tipo di informazioni sensibili per applicare un'etichetta di classificazione.

Per creare un tipo di informazioni sensibili
1. Nel riquadro di spostamento sinistro del [Centro conformità Microsoft 365](https://compliance.microsoft.com) espandere **Classificazione** e quindi fare clic su **Tipi di informazioni sensibili**.
2. Fare clic su **Crea**.
3. Per **Nome** e **Descrizione** digitare **Progetto Saturno** e quindi fare clic su **Avanti**.
4. Fare clic su **Aggiungere un elemento**.
5. Nell'elenco **Rilevare il contenuto che contiene** selezionare **Parole chiave** e quindi digitare *Progetto Saturno* nella casella delle parole chiave.
6. Fare clic su **Avanti** e quindi su **Fine**.
7. Se viene chiesto se si vuole testare il tipo di informazioni sensibili, fare clic su **No**.

### <a name="more-information"></a>Altre informazioni
[Tipi di informazioni sensibili personalizzati](https://docs.microsoft.com/Office365/SecurityCompliance/custom-sensitive-info-types)

## <a name="create-a-policy-to-assign-a-label-based-on-a-sensitive-information-type"></a>Creare un criterio per assegnare un'etichetta in base a un tipo di informazioni sensibili

Una volta creato il tipo di informazioni sensibili, è possibile creare un criterio file in Microsoft Cloud App Security in modo da applicare automaticamente l'etichetta *Estremamente riservato* ai documenti che contengono la stringa *Progetto Saturno*.

> [!NOTE]
> Esiste un processo di replica che rende disponibili le etichette di riservatezza in Cloud App Security. L'etichetta per un criterio potrebbe non essere immediatamente disponibile.

Per creare un criterio basato su un tipo di informazioni sensibili
1. Aprire [Microsoft Cloud App Security](https://portal.cloudappsecurity.com).
2. Nel riquadro di spostamento a sinistra espandere **Controllo**e quindi fare clic su **Criteri**.
3. Fare clic su **Crea criterio** e quindi selezionare **Criteri file**.
4. Per **Nome criterio** digitare *Etichette Progetto Saturno*.
5. In **Crea un filtro per i file a cui verrà applicato il criterio** fare clic sulla X due volte per eliminare i filtri predefiniti.
7. Nell'elenco **Seleziona un filtro** scegliere **App** e quindi scegliere **Microsoft SharePoint Online** nell'elenco **Seleziona le app**.
8. In **Metodo di ispezione** scegliere **Servizio di classificazione dei dati**.
9. Nell'elenco **Scegliere un tipo di ispezione** selezionare **Tipo di informazioni sensibili**.
10. Cercare e selezionare l'etichetta di riservatezza *Progetto Saturno* e quindi fare clic su **Fatto**.</br>
   ![Screenshot delle impostazioni del metodo di ispezione di Cloud App Security](../media/mcas-sensitive-info-type-project-saturn.png)
11. In **Governance** espandere **Microsoft SharePoint Online**.
12. Selezionare la casella di controllo **Applica un'etichetta di classificazione** e selezionare l'etichetta **Estremamente riservato**.
13. Fare clic su **Crea**.

Una volta impostato il criterio, se un utente digita "Progetto Saturno" in un documento, Cloud App Security applicherà automaticamente l'etichetta *Estremamente riservato* quando analizza il file.

### <a name="more-information"></a>Ulteriori informazioni
[Criteri file](https://docs.microsoft.com/cloud-app-security/data-protection-policies)

## <a name="create-a-policy-to-remove-guest-access-to-highly-sensitive-files"></a>Creare un criterio per rimuovere l'accesso guest ai file estremamente riservati

Nell'esempio di questo articolo, i file con l'etichetta *Estremamente riservato* non devono essere condivisi con gli utenti guest. È possibile creare un criterio file in Cloud App Security che rimuove automaticamente l'accesso guest dai file con tale etichetta.

Tenere presente che questo non impedisce agli utenti di condividere o ricondividere questi file. L'organizzazione dipende comunque dal fatto che gli utenti rispettino i criteri di governance per i file archiviati in siti che consentono la condivisione guest. Tuttavia, può essere uno strumento utile per rimuovere l'accesso guest dai file in cui sono state aggiunte informazioni riservate dopo che sono stati condivisi con utenti guest.

Per creare criteri file basati su etichette
1. Aprire [Microsoft Cloud App Security](https://portal.cloudappsecurity.com).
2. Nel riquadro di spostamento a sinistra espandere **Controllo**e quindi fare clic su **Criteri**.
3. Fare clic su **Crea criterio** e quindi selezionare **Criteri file**.
4. Per **Nome criterio** digitare *Progetto Saturno - rimozione accesso guest*.
5. In **Crea un filtro per i file a cui verrà applicato il criterio** fare clic sulla X due volte per eliminare i filtri predefiniti.
6. Nell'elenco **Seleziona un filtro** scegliere **App** e quindi scegliere **Microsoft SharePoint Online** nell'elenco **Seleziona le app**.
7. Fare clic su **Aggiungi filtro**.
8. Nell'elenco **Seleziona un filtro** scegliere **Etichetta di classificazione** e quindi scegliere **Azure Information Protection** nell'elenco **Seleziona un filtro**.
9. Nell'elenco **Selezionare un'etichetta di classificazione** scegliere **Estremamente riservato**.</br>
   ![Screenshot delle impostazioni del filtro del criterio di Cloud App Security](../media/mcas-sharepoint-confidential-label-filter.png)
10. In **Governance** espandere **Microsoft SharePoint Online**.
11. Selezionare le caselle di controllo **Invia digest sulla corrispondenza con criteri al proprietario del file** e **Rimuovi gli utenti esterni**.
12. Per il messaggio di notifica personalizzato, digitare *Questo file è estremamente riservato. I criteri aziendali ne vietano la condivisione con utenti guest*.
13. Fare clic su **Crea**.

È importante sottolineare che questo criterio rimuove l'accesso ai file condivisi con un collegamento *Utenti specifici*. Non rimuove l'accesso dai collegamenti non autenticati (*Chiunque*). Inoltre, non rimuove l'accesso se il guest è membro del sito o del team nel suo complesso. Se si prevede di avere documenti estremamente riservati in un sito o in un team con utenti guest, è consigliabile usare [canali privati in Teams](https://support.office.com/article/60ef929a-4d68-418b-bf4f-5784db184ec9) e consentire l'accesso ai canali privati solo ai membri dell'organizzazione.

## <a name="test-the-solution"></a>Testare la soluzione

Per testare la soluzione descritta in questo articolo, creare un documento di Word e salvarlo in una raccolta documenti. Condividere il file con un utente guest. Quando il guest prova ad accedere al documento, gli deve essere richiesto di effettuare la registrazione all'autenticazione a più fattori e quindi accettare le condizioni per l'utilizzo.

Quando il guest ha accesso al documento, digitare *Progetto Saturno* nel documento e salvarlo. Quando Cloud App Security analizza il documento, dovrebbe essere applicata l'etichetta *Estremamente riservato* e l'utente guest non dovrebbe potervi più accedere.

È possibile usare gli strumenti descritti in questo articolo in varie combinazioni, per creare un ambiente di condivisione con gli utenti guest produttivo, ma allo stesso tempo sicuro per l'organizzazione.

## <a name="additional-options"></a>Opzioni aggiuntive

Sono disponibili delle opzioni aggiuntive in Microsoft 365 e Azure Active Directory che possono aiutare a proteggere l'ambiente di condivisione guest.

- È possibile creare un elenco di domini di condivisione consentiti o rifiutati per limitare le persone con cui gli utenti possono condividere contenuti. Per altre informazioni, vedere [Limitare la condivisione di contenuti di SharePoint e OneDrive per dominio](https://docs.microsoft.com/sharepoint/restricted-domains-sharing) e [Consentire o bloccare gli inviti per gli utenti B2B da organizzazioni specifiche](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).
- È possibile porre limiti agli altri tenant di Azure Active Directory a cui gli utenti possono connettersi. Per informazioni, vedere [Utilizzare le restrizioni del tenant per gestire l'accesso alle applicazioni cloud SaaS](https://docs.microsoft.com/azure/active-directory/manage-apps/tenant-restrictions).
- È possibile creare un ambiente gestito in cui i partner possano contribuire alla gestione degli account guest. Per informazioni, vedere [Creare una Extranet B2B con guest gestiti](https://docs.microsoft.com/Office365/Enterprise/b2b-extranet).

## <a name="see-also"></a>Vedere anche

[Limitare l'esposizione accidentale ai file durante la condivisione con gli utenti guest](share-limit-accidental-exposure.md)

[Procedure consigliate per la condivisione di file e cartelle con utenti non autenticati](best-practices-anonymous-sharing.md)

[Creare una Extranet B2B con guest gestiti](b2b-extranet.md).
