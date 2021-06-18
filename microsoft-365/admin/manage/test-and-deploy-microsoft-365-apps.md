---
title: Testare e distribuire Microsoft 365 Apps dai partner nel portale delle app integrate
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: ''
ms.custom: AdminSurgePortfolio
search.appverid: MET150
ROBOTS: NOINDEX, NOFOLLOW
description: Trova, testa e distribuisci app partner Microsoft e Microsoft per utenti e gruppi nell'organizzazione dal portale delle app integrate nella interfaccia di amministrazione di Microsoft 365.
ms.openlocfilehash: dcd4a91d9e43c0a740094615cd3dca0b0e8bc0f6
ms.sourcegitcommit: bbad1938b6661d4a6bca99f235c44e521b1fb662
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/18/2021
ms.locfileid: "53007058"
---
# <a name="test-and-deploy-microsoft-365-apps-by-partners-in-the-integrated-apps-portal"></a>Testare e distribuire Microsoft 365 Apps dai partner nel portale delle app integrate

Il interfaccia di amministrazione di Microsoft 365 offre la flessibilità di distribuire app dello Store singolo, una linea aziendale personalizzata di app e Microsoft 365 app partner da un'unica posizione. È possibile accedere alla posizione nelle impostazioni dell'interfaccia di amministrazione di Microsoft, in App integrate. La possibilità di trovare, testare e distribuire completamente le app acquistate e con licenza dai partner Microsoft dal portale delle app integrate offre la comodità e i vantaggi necessari all'organizzazione per mantenere i servizi aziendali aggiornati regolarmente e in modo efficiente.

Per ulteriori informazioni sull'acquisto e sulla gestione delle licenze Microsoft 365 app dai partner per l'organizzazione, vedere Gestire e distribuire Microsoft 365 Apps [dall'interfaccia di amministrazione di Microsoft 365](https://techcommunity.microsoft.com/t5/microsoft-365-blog/manage-and-deploy-microsoft-365-apps-from-the-microsoft-365/ba-p/1194324).

Per altre info su come i partner creano queste app, vedi Come pianificare un'offerta [SaaS per il marketplace commerciale](https://go.microsoft.com/fwlink/?linkid=2158277)

Il portale delle app integrate è accessibile solo agli amministratori globali e disponibile solo per i clienti a livello mondiale. Questa funzionalità non è disponibile nei cloud sovrani e governativi.

Il portale delle app integrate visualizza un elenco di app, che include singole app e Microsoft 365 app dei partner distribuiti nell'organizzazione. Sono elencate solo app Web, SPFx, Office componenti aggiuntivi e Teams app. Per le app Web, puoi visualizzare due tipi di app.

- App SaaS disponibili in appsource.microsoft.com e che possono essere distribuite dagli amministratori che acconsentino per conto dell'organizzazione.
- App della raccolta SAML collegate ai componenti aggiuntivi di Office.

## <a name="manage-apps-in-the-integrated-apps-portal"></a>Gestire le app nel portale delle app integrate

È possibile gestire i test e la distribuzione dei prodotti acquistati e concessi Microsoft 365 Apps dai partner.

1. Nell'interfaccia di amministrazione seleziona **Impostazioni** e quindi seleziona **App integrate.**

2. Scegli un'app con **stato** **Altre app disponibili** per aprire il **riquadro** Gestisci. Lo stato **di altre app disponibili** ti consente di sapere che ci sono più integrazioni dagli ISV che non sono ancora state distribuite.

3. Nella scheda **Panoramica** selezionare **Distribuisci**. Alcune app richiedono l'aggiunta di utenti prima di poter selezionare Distribuisci.

4. Selezionare **Utenti,** scegliere **Si tratta di una distribuzione di test** e quindi scegliere Intera **organizzazione,** **Utenti/gruppi specifici** o Solo **io.** Puoi anche scegliere **Test distribuzione** se preferisci attendere per distribuire l'app nell'intera organizzazione. Utenti o gruppi specifici possono essere un Microsoft 365, un gruppo di sicurezza o un gruppo di distribuzione.

5. Selezionare **Aggiorna** e quindi **Fatto.** È ora possibile selezionare Distribuisci nella scheda Panoramica.

6. Esaminare le informazioni sull'app e quindi selezionare **Distribuisci**.

7. Selezionare **Fatto** nella pagina Distribuzione completata ed esaminare i dettagli del test o della distribuzione completa nella **scheda** Panoramica.

8. Se lo stato dell'app è Aggiornamento **in** sospeso, puoi fare clic sull'app per aprire il riquadro Gestisci e aggiornare l'app.

## <a name="find-published-apps-for-testing-and-full-deployment"></a>Trovare le app pubblicate per il testing e la distribuzione completa

Puoi trovare, testare e distribuire completamente le app pubblicate che non sono già visualizzate nell'elenco nella pagina App integrate. Acquistando e licenze per le app dall'interfaccia di amministrazione, puoi aggiungere app partner Microsoft e Microsoft all'elenco da un'unica posizione.

1. Nell'interfaccia di amministrazione, nel riquadro di spostamento sinistro, **scegliere Impostazioni** e quindi scegliere **App integrate.**

2. Seleziona **Ottieni app** per ottenere una visualizzazione delle app.

3. Nella pagina **Microsoft 365 Apps** app pubblicate seleziona l'app che vuoi distribuire scegliendo **Scarica ora**. Le app visualizzate sono principalmente Word, PowerPoint, Excel, componenti aggiuntivi Outlook, app Teams e app SharePoint (basata sulla tecnologia SharePoint Framework). Accettare le autorizzazioni e selezionare **Continua.**

5. Selezionare **Distribuisci** nella parte superiore della pagina accanto al messaggio che fa riferimento all'attesa di distribuzione.

    Se l'app selezionata è collegata a un'offerta SaaS da un ISV, tutte le altre app che fanno parte di questa offerta collegata verranno visualizzate nella pagina Configurazione. Se scegli di distribuire tutte le app, seleziona **Avanti.** In caso contrario, **seleziona Modifica** e scegli le app che vuoi distribuire. Alcune app richiedono l'aggiunta di utenti prima di poter selezionare **Distribuisci**.

6. Selezionare **Aggiungi utenti,** scegliere **Si tratta di una distribuzione di test** e quindi **scegliere** Intera organizzazione o **Utenti/gruppi specifici** o **Solo io.**

    Utenti/gruppi specifici possono essere un Microsoft 365, un gruppo di sicurezza o un gruppo distribuito. Puoi anche scegliere **Test distribuzione** se preferisci attendere per distribuire l'app nell'intera organizzazione.

7. Selezionare **Avanti** per accedere alla **pagina Accetta richiesta di** autorizzazione. Sono elencate le funzionalità e le autorizzazioni delle app. Se l'app necessita del consenso, seleziona **Accetta autorizzazioni.** Solo un amministratore globale può fornire il consenso.

8. Selezionare **Avanti** per esaminare la distribuzione e scegliere **Fine distribuzione**. È possibile visualizzare la distribuzione dalla **scheda Panoramica** scegliendo Visualizza **questa distribuzione**. Nell'interfaccia di amministrazione di Microsoft 365, puoi visualizzare lo stato di ogni app distribuita e la data di distribuzione dell'app.

> [!NOTE]
> Se un'app è stata distribuita in precedenza da un punto diverso dal portale delle app integrate, il **tipo di distribuzione** è **Personalizzato.**

## <a name="unsupported-scenarios"></a>Scenari non supportati

Non potrai distribuire una singola app dello Store o Microsoft 365 Apps partner dal portale delle app integrate per gli scenari seguenti.

- Lo stesso componente aggiuntivo è collegato a più offerte SaaS.
- L'offerta SaaS è collegata ai componenti aggiuntivi, ma non si integra con Microsoft Graph e non viene fornito alcun ID app AAD.
- L'offerta SaaS è collegata ai componenti aggiuntivi, ma l'ID app AAD fornito per l'integrazione di Microsoft Graph è condiviso tra più offerte SaaS.

## <a name="upload-custom-line-of-business-apps-for-testing-and-full-deployment"></a>Upload app line-of-business personalizzate per il testing e la distribuzione completa

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione scegliere **Impostazioni** e quindi **App integrate**.

2. Seleziona **Upload app personalizzate.** È supportata solo una linea personalizzata di app per Word, PowerPoint, Excel e Outlook.

3. Upload il file manifesto dal dispositivo o aggiungi un collegamento URL. Alcune app richiedono l'aggiunta di utenti prima di poter selezionare Distribuisci.

4. Selezionare **Aggiungi utenti,** scegliere **Distribuzione** test e **scegliere** Intera organizzazione o **Utenti/gruppi specifici** o Solo **io.**

    Utenti/gruppi specifici possono essere un Microsoft 365, un gruppo di sicurezza o un gruppo distribuito. Puoi anche scegliere **Test distribuzione** se vuoi attendere di distribuire l'app nell'intera organizzazione.

5. Selezionare **Avanti** per accedere alla **pagina Accetta richiesta di** autorizzazione. Sono elencate le funzionalità e le autorizzazioni delle app. Se l'app necessita del consenso, seleziona **Accetta autorizzazioni.** Solo un amministratore globale può fornire il consenso.

6. Selezionare **Avanti** per esaminare la distribuzione e scegliere **Fine distribuzione**. È possibile visualizzare la distribuzione dalla **scheda Panoramica** scegliendo Visualizza **questa distribuzione**.

## <a name="prepare-to-deploy-add-ins-in-integrated-apps"></a>Preparare la distribuzione dei componenti aggiuntivi nelle app integrate

Office componenti aggiuntivi consentono di personalizzare i documenti e semplificare il modo in cui si accede alle informazioni sul Web (vedere Iniziare a usare Office componente aggiuntivo). 

I componenti aggiuntivi offre i vantaggi seguenti: 

- All'avvio dell Office appalto pertinente, il componente aggiuntivo viene scaricato automaticamente. Se il componente aggiuntivo supporta i comandi del componente aggiuntivo, il componente aggiuntivo verrà visualizzato automaticamente nella barra multifunzione all'interno dell Office applizione. 

- I componenti aggiuntivi non vengono più visualizzati per gli utenti se l'amministratore disattiva o elimina il componente aggiuntivo o se l'utente viene rimosso da Azure Active Directory o da un gruppo a cui è assegnato il componente aggiuntivo. 

I componenti aggiuntivi sono supportati in tre piattaforme desktop Windows, Mac e Online Office app. È supportato anche in iOS e Android (Outlook solo componenti aggiuntivi per dispositivi mobili). 

La visualizzazione di un componente aggiuntivo per tutti gli utenti può richiedere fino a 24 ore. 

Oggi sia Exchange amministratori globali che amministratori globali possono distribuire componenti aggiuntivi da app integrate.   

### <a name="before-you-begin"></a>Prima di iniziare

La distribuzione dei componenti aggiuntivi richiede che gli utenti utilizzino licenze di Microsoft 365 Enterprise (E3/E5/F3) o licenze di Microsoft 365 Business (Business Basic, Business Standard, Business Premium). Gli utenti devono inoltre essere connessi Office l'ID dell'organizzazione) e disporre di Exchange Online e delle cassette postali Exchange Online attive. La directory di sottoscrizione deve essere in o federata per Azure Active Directory. 

La distribuzione non supporta quanto segue: 

- Componenti aggiuntivi per Word, Excel o PowerPoint in Office 2013 
- Servizio di directory locale 
- Distribuzione di componenti aggiuntivi in una Exchange locale 
- Distribuzione di componenti aggiuntivi COM (Component Object Model) o Visual Studio Tools per Office (VSTO). 
- Distribuzioni di Microsoft 365 che non includono Exchange Online, ad esempio Microsoft 365 Apps for Business e Microsoft 365 Apps per Enterprise.  

### <a name="office-requirements"></a>Office Requisiti 

Per Word, Excel e PowerPoint componenti aggiuntivi, gli utenti devono utilizzare uno dei componenti seguenti: 
- In un dispositivo Windows versione 1704 o successiva delle licenze di Microsoft 365 Enterprise (E3/E5/F3) o Microsoft 365 Business (Business Basic, Business Standard, Business Premium). 
- In un Mac, versione 15.34 o successiva. 

Per Outlook, gli utenti devono utilizzare una delle opzioni seguenti: 
- Versione 1701 o successiva delle licenze di Microsoft 365 Enterprise (E3/E5/F3) o Microsoft 365 Business (Business Basic, Business Standard, Business Premium). 
- Versione 1808 o successiva di Office Professional Plus 2019 o Office Standard 2019. 
- Versione 16.0.4494.1000 o successiva di Office Professional Plus 2016 (MSI) o Office Standard 2016 (MSI).
    > [!NOTE]
    > Le versioni MSI di Outlook mostrano i componenti aggiuntivi installati dall'amministratore nella barra multifunzione di Outlook appropriata, non nella sezione "Componenti aggiuntivi".  
- Versione 15.0.4937.1000 o successiva di Office Professional Plus 2013 (MSI) o Office Standard 2013 (MSI).
- Versione 16.0.9318.1000 o successiva di Office 2016 per Mac. 
- Versione 2.75.0 o successiva di Outlook mobile per iOS. 
- Versione 2.2.145 o successiva di Outlook mobile per Android. 



### <a name="exchange-online-requirements"></a>Requisiti di Exchange Online 
Microsoft Exchange archivia i manifesti dei componenti aggiuntivi all'interno del tenant dell'organizzazione. L'amministratore che distribuisce i componenti aggiuntivi e gli utenti che ricevono tali componenti aggiuntivi devono essere in una versione di Exchange Online che supporta l'autenticazione OAuth. 

Contattare l'amministratore di Exchange dell'organizzazione per sapere quale configurazione è in uso. La connettività OAuth per utente può essere verificata utilizzando il cmdlet [Test-OAuthConnectivity](/powershell/module/exchange/test-oauthconnectivity)   di PowerShell. 

### <a name="user-and-group-assignments"></a>Assegnazioni di utenti e gruppi
La distribuzione del componente aggiuntivo è attualmente supportata per la maggior parte dei gruppi supportati da Azure Active Directory, inclusi i gruppi di Microsoft 365, le liste di distribuzione e i gruppi di sicurezza. La distribuzione supporta gli utenti di gruppi di primo livello o gruppi senza gruppi padre, ma non gli utenti di gruppi annidati o gruppi con gruppi padre. 

> [!NOTE]
> I gruppi di sicurezza non abilitati alla posta elettronica non sono attualmente supportati. 

Nell'esempio seguente, Sandra, Sheila e il gruppo Sales Department vengono assegnati a un componente aggiuntivo. Reparto vendite costa occidentale è un gruppo annidato, quindi Gianni e Albertino non sono assegnati a un componente aggiuntivo. 

![Diagramma del reparto vendite](../../media/683094bb-1160-4cce-810d-26ef7264c592.png)

### <a name="find-out-if-a-group-contains-nested-groups"></a>Scoprire se un gruppo contiene gruppi annidati

Il modo più semplice per rilevare se un gruppo contiene gruppi annidati consiste nel visualizzare la scheda contatto del gruppo in Outlook. Se si immette il nome del gruppo nel campo **A** di un messaggio di posta elettronica e quindi si seleziona il nome del gruppo quando viene risolto, verrà visualizzato se contiene utenti o gruppi   annidati. Nell'esempio seguente, nella **scheda** Membri della scheda contatto di Outlook per il gruppo di test non vengono visualizzati utenti e   solo due sottogrumi. 

![Scheda Membri della scheda contatto di Outlook](../../media/d9db88c4-d752-426c-a480-b11a5b3adcd6.png)

È possibile eseguire la query opposta risolvendo il gruppo per vedere se è un membro di un gruppo. Nell'esempio seguente, è possibile <b></b>visualizzare nella scheda Appartenenza della scheda contatto di Outlook che Il gruppo secondario 1 è un   membro del gruppo di test. 

![Scheda Appartenenza della scheda contatto di Outlook](../../media/a9f9b6ab-9c19-4822-9e3d-414ca068c42f.png)

Tieni presente che puoi usare l'API Graph di Azure Active Directory per eseguire query per trovare l'elenco dei gruppi all'interno di un gruppo. Per ulteriori informazioni, vedere [Operazioni sui gruppi | Informazioni di riferimento sulle API graph.](/previous-versions/azure/ad/graph/api/groups-operations) 

## <a name="recommended-approach-for-deploying-office-add-ins"></a>Approccio consigliato per la distribuzione dei componenti aggiuntivi per Office 
Per implementare i componenti aggiuntivi utilizzando un approccio graduale, è consigliabile: 
1. Distribuire il componente aggiuntivo in un gruppo ristretto di stakeholder dell'azienda e di membri del reparto IT. È possibile attivare il flag **Si tratta di una distribuzione di test.** Se la distribuzione ha esito positivo, andare al passaggio 2. 

2. Implementare il componente aggiuntivo a più utenti all'interno dell'azienda. Valutare nuovamente i risultati e, in caso di esito positivo, continuare con la distribuzione completa. 

3. Eseguire un'implementazione completa per tutti gli utenti. Disattivare il flag da **È una distribuzione di test**. 

A seconda delle dimensioni del gruppo di destinatari, è possibile aggiungere o rimuovere passaggi di implementazione.  

## <a name="deploy-an-office-add-in-using-the-admin-center"></a>Distribuire un componente aggiuntivo per Office con l'interfaccia di amministrazione 

1. Nell'interfaccia di amministrazione seleziona **Impostazioni,** quindi seleziona **App integrate.** 

2. Seleziona **Ottieni app** nella parte superiore della pagina. AppSource verrà caricato in un formato incorporato. Cercare un componente aggiuntivo o trovarlo facendo clic su Prodotto nella barra di spostamento sinistra.  Se il componente aggiuntivo è stato collegato dall'ISV a un'app SaaS o ad altre app e componenti aggiuntivi e se l'app SaaS è un'app a pagamento, verrà visualizzata una finestra di dialogo per acquistare la licenza o distribuire. Indipendentemente dal fatto che la licenza sia stata acquistata o meno, è possibile procedere con la distribuzione. Selezionare **Distribuisci**.  

3. Verrà visualizzata la **pagina Configurazione** in cui sono elencate tutte le app. Se non hai le autorizzazioni o l'accesso giusto per distribuire l'app, verranno evidenziate le rispettive informazioni. Puoi selezionare le app che vuoi distribuire. Selezionando **Avanti,** verrà visualizzata la **pagina** Utenti. Se il componente aggiuntivo non è stato collegato dall'ISV, verrà instradato alla pagina Utenti. 

4. Selezionare **Tutti,** **Utenti/gruppi specifici** o **Solo io** per specificare a chi verrà distribuito il componente   aggiuntivo. Utilizzare la casella Di ricerca per trovare utenti o gruppi specifici. Se si sta testando il componente aggiuntivo, selezionare **Si tratta di una distribuzione di test.** 

5. Selezionare **Avanti**. Tutte le funzionalità e le autorizzazioni dell'app vengono visualizzate in un singolo riquadro insieme alle informazioni di certificazione se l'app ha la certificazione Microsoft 365. La selezione del logo di certificazione consente all'utente di visualizzare ulteriori dettagli sulla certificazione.  

6. Rivedere e quindi selezionare **Fine distribuzione**.  

7. Quando il componente aggiuntivo viene distribuito, viene visualizzata un'icona di graduazione verde. Seguire le istruzioni visualizzate nella pagina per testare il componente aggiuntivo. 

> [!NOTE]
> Gli utenti potrebbero dover rilanciare Office per visualizzare l'icona del componente aggiuntivo sulla barra multifunzione dell'app. La visualizzazione dei componenti aggiuntivi di Outlook sulle barre multifunzione dell'app può richiedere fino a 24 ore. 

È consigliabile informare utenti e gruppi che il componente aggiuntivo distribuito è disponibile. Prendere in considerazione l'invio di un messaggio di posta elettronica che descrive quando e come utilizzare il componente aggiuntivo. Includere o collegare il contenuto della Guida o le domande frequenti che potrebbero aiutare gli utenti in caso di problemi con il componente aggiuntivo. 

## <a name="considerations-when-assigning-an-add-in-to-users-and-groups"></a>Considerazioni per l'assegnazione di un componente aggiuntivo a utenti e gruppi 

Gli amministratori globali e gli amministratori di Exchange possono assegnare un componente aggiuntivo a tutti gli utenti o a utenti e gruppi specifici. Ogni opzione ha delle implicazioni: 

- **Tutti**   Questa opzione consente di assegnare il componente aggiuntivo a ogni utente dell'organizzazione. Usare questa opzione con moderazione e solo per i componenti aggiuntivi che effettivamente servono a tutti gli utenti dell'organizzazione. 

- **Utenti**   Se si assegna un componente aggiuntivo a un singolo utente e quindi si distribuisce il componente aggiuntivo a un nuovo utente, è necessario innanzitutto aggiungere il nuovo utente. 

- **Gruppi**   Se si assegna un componente aggiuntivo a un gruppo, agli utenti aggiunti al gruppo verrà assegnato automaticamente il componente aggiuntivo. Quando un utente viene rimosso da un gruppo, perde l'accesso al componente aggiuntivo. In entrambi i casi, l'amministratore non richiede alcuna azione aggiuntiva. 

- **Just me**   Se assegni un componente aggiuntivo solo a te stesso, il componente aggiuntivo viene assegnato solo al tuo account, ideale per testare il componente aggiuntivo. 

L'opzione giusta per l'organizzazione dipende dalla configurazione. Tuttavia, è consigliabile eseguire le assegnazioni utilizzando i gruppi. Gli amministratori possono semplificare la gestione dei componenti aggiuntivi utilizzando i gruppi e controllando l'appartenenza a tali gruppi anziché assegnare ogni volta singoli utenti. In alcuni casi, è possibile limitare l'accesso a un piccolo set di utenti assegnando manualmente gli utenti a utenti specifici. 

### <a name="more-about-office-add-ins-security"></a>Ulteriori informazioni sulla sicurezza dei componenti aggiuntivi di Office 
I componenti aggiuntivi per Office combinano un file manifesto XML che contiene alcuni metadati sul componente aggiuntivo, ma soprattutto che punta a un'applicazione Web che contiene tutto il codice e la logica. Le funzionalità dei componenti aggiuntivi possono variare. Ad esempio, i componenti aggiuntivi possono:
- Visualizzare i dati. 
- Leggere il documento di un utente per offrire servizi contestuali. 
- Leggere e scrivere dati da e verso il documento di un utente per fornire valore all'utente.  

Per ulteriori informazioni sui tipi e sulle funzionalità dei componenti aggiuntivi di Office, vedere Panoramica della piattaforma dei componenti aggiuntivi di [Office,](/office/dev/add-ins/overview/office-add-ins)in particolare la sezione "Anatomia di un componente aggiuntivo di Office". 

Per interagire con il documento dell'utente, il componente aggiuntivo deve dichiarare le autorizzazioni necessarie nel manifesto. Un modello di autorizzazioni di accesso api JavaScript a cinque livelli fornisce la base per la privacy e la sicurezza per gli utenti dei componenti aggiuntivi del riquadro attività. La maggior parte dei componenti aggiuntivi in Office Store è a livello ReadWriteDocument con quasi tutti i componenti aggiuntivi che supportano almeno il livello ReadDocument. Per ulteriori informazioni sui livelli di autorizzazione, vedere [Requesting permissions for API use in content and task pane add-ins](/office/dev/add-ins/develop/requesting-permissions-for-api-use-in-content-and-task-pane-add-ins). 

Quando si aggiorna un manifesto, le modifiche tipiche riguardano l'icona e il testo di un componente aggiuntivo. In alcuni casi, vengono modificati i comandi del componente aggiuntivo. Tuttavia, le autorizzazioni del componente aggiuntivo non cambiano. L'applicazione Web in cui viene eseguito tutto il codice e la logica per il componente aggiuntivo può essere modificata in qualsiasi momento, come accade per tutte le applicazioni Web. 

Gli aggiornamenti per i componenti aggiuntivi vengono eseguiti come segue: 
- **Componente aggiuntivo line-of-business:** in questo caso, in cui un amministratore ha caricato esplicitamente un manifesto, il componente aggiuntivo richiede che l'amministratore carichi un nuovo file manifesto per supportare le modifiche ai metadati. All'avvio successivo delle applicazioni di Office rilevanti, il componente aggiuntivo verrà aggiornato. L'applicazione Web può essere modificata in qualsiasi momento. 

- Componente aggiuntivo **di Office Store:** quando un amministratore seleziona un componente aggiuntivo da Office Store, se un componente aggiuntivo viene aggiornato in Office Store, al successivo avvio delle applicazioni di Office rilevanti, il componente aggiuntivo verrà aggiornato. L'applicazione Web può essere modificata in qualsiasi momento. 

> [!NOTE]
> Per Word, Excel e PowerPoint utilizzare un Catalogo app di [SharePoint](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog)per distribuire componenti aggiuntivi agli utenti in un ambiente locale senza connessione a Microsoft 365 e/o supporto per i componenti aggiuntivi di   SharePoint necessari. Per Outlook utilizzare il Pannello di controllo di Exchange per la distribuzione in un ambiente locale senza una connessione a Microsoft 365.  

## <a name="add-in-states"></a>Stati dei componenti aggiuntivi
Un componente aggiuntivo può essere nello stato **Attivo**   o **Disattivato.**   

| Stato | Quando si verifica lo stato | Impatto |
|:-----|:-----|:-----|
|**Attivazione**  <br/> |L'amministratore ha caricato il componente aggiuntivo e lo ha assegnato a utenti o gruppi.  <br/> |Gli utenti e i gruppi assegnati al componente aggiuntivo lo vedono nei client pertinenti.  <br/> |
|**Disattivato**  <br/> |L'amministratore ha disattivato il componente aggiuntivo.  <br/> |Gli utenti e i gruppi assegnati al componente aggiuntivo non possono più accedervi.  <br/> Se lo stato del componente aggiuntivo viene modificato su Attivo, gli utenti e i gruppi potranno accedervi di nuovo.  <br/> |
|**Eliminato**  <br/> |L'amministratore ha eliminato il componente aggiuntivo.  <br/> |Gli utenti e i gruppi assegnati al componente aggiuntivo non possono più accedervi.  <br/> |
 
Prendere in considerazione l'eliminazione di un componente aggiuntivo se non viene più utilizzato da nessuno. Ad esempio, la disattivazione di un componente aggiuntivo potrebbe avere senso se un componente aggiuntivo viene utilizzato solo in periodi specifici dell'anno. 

## <a name="manage-an-office-add-in-using-the-admin-center"></a>Gestire un Office componente aggiuntivo tramite l'interfaccia di amministrazione

Dopo la distribuzione, gli amministratori possono anche gestire l'accesso degli utenti ai componenti aggiuntivi. 

1. Nell'interfaccia di amministrazione seleziona **Impostazioni** e quindi seleziona **App integrate.** 
2. Nella pagina App integrate verrà visualizzato un elenco di app che saranno componenti aggiuntivi singoli o componenti aggiuntivi collegati ad altre app. 
3. Seleziona un'app **con stato**   Altre app **disponibili** per aprire   il **riquadro**   Gestisci. Lo stato **di altre app disponibili** ti consente di sapere che ci sono più integrazioni dagli ISV che non sono ancora state   distribuite. 
4. Nella scheda **Panoramica**   selezionare **Distribuisci**. Alcune app richiedono l'aggiunta di utenti prima di poter selezionare Distribuisci. 
5. Selezionare **Utenti,** selezionare **Si tratta di una distribuzione di test** e quindi selezionare Intera **organizzazione,** **Utenti/gruppi specifici** o Solo    **io.** Puoi anche selezionare **Test deployment**   se preferisci attendere per distribuire l'app nell'intera organizzazione. Utenti o gruppi specifici possono essere un Microsoft 365, un gruppo di sicurezza o un gruppo di distribuzione. 
6. Selezionare  **Aggiorna**   e quindi Fare clic su **Fine.** È ora possibile selezionare **Distribuisci** nella **scheda** Panoramica. 
7. Esaminare le informazioni sull'app e quindi selezionare **Distribuisci**.
8. Selezionare **Fatto** nella pagina Distribuzione completata ed esaminare i dettagli del test o della   distribuzione completa nella **scheda**    Panoramica. 
9. Se lo stato dell'app è Aggiornamento  **in** sospeso, puoi fare clic sull'app per aprire **il** riquadro Gestisci e aggiornare l'app. 
10. Per aggiornare solo gli utenti, selezionare la **scheda Utenti** e apportare la modifica appropriata. Selezionare **Aggiorna** dopo aver apportato le modifiche.  

## <a name="delete-an-add-in"></a>Eliminare un componente aggiuntivo

È inoltre possibile eliminare un componente aggiuntivo distribuito.

1. Nell'interfaccia di amministrazione seleziona **Impostazioni** e quindi seleziona **App integrate.**
2. Selezionare una riga qualsiasi per visualizzare il riquadro di gestione. 
3. Selezionare la **scheda** Configurazione. 
4. Selezionare il componente aggiuntivo che si desidera eliminare e quindi selezionare **Rimuovi**.  

> [!NOTE]
>  Se il componente aggiuntivo è stato distribuito da un altro amministratore, il pulsante Rimuovi verrà disabilitato. Solo l'amministratore che ha distribuito l'app o un amministratore globale può eliminare il componente aggiuntivo.

## <a name="scenarios-where-exchange-admin-cannot-deploy-an-add-in"></a>Scenari in cui Exchange amministratore non può distribuire un componente aggiuntivo 

Esistono due casi in cui un Exchange amministratore non sarà in grado di distribuire un componente aggiuntivo:
- Se un componente aggiuntivo necessita dell'autorizzazione per LE GRAPH e necessita del consenso di un amministratore globale.
- Se un componente aggiuntivo è collegato a due o più componenti aggiuntivi e webapp e almeno uno di questi componenti aggiuntivi viene distribuito da un altro amministratore (exchange/global) e l'assegnazione utente non è uniforme. È consentita la distribuzione di componenti aggiuntivi solo quando l'assegnazione utente è la stessa per tutte le app già distribuite.  


## <a name="frequently-asked-questions"></a>Domande frequenti

### <a name="which-administrator-role-do-i-need-to-access-integrated-apps"></a>Quale ruolo di amministratore è necessario per accedere alle app integrate?

Solo gli amministratori globali possono accedere alle app integrate. Le app integrate non vengono mostrate nel riquadro di spostamento sinistro per altri amministratori.

### <a name="why-do-i-see-add-in-in-the-left-nav-under-setting-but-not-integrated-apps"></a>Perché il componente aggiuntivo viene visualizzato nel riquadro di spostamento a sinistra in Impostazione ma non nelle app integrate?

Esistono alcuni motivi:

- L'amministratore connesso è un Exchange amministratore.
- Il cliente è nel cloud sovrano e l'esperienza delle app integrate è ancora disponibile per i clienti cloud sovrani.

### <a name="what-apps-can-i-deploy-from-integrated-apps"></a>Quali app è possibile distribuire da app integrate?

Le app integrate consentono la distribuzione di app Web, app Teams, Excel, PowerPoint, Word, Outlook componenti aggiuntivi e SPFx app. Per i componenti aggiuntivi, le app integrate supportano la distribuzione Exchange cassette postali online e non locali Exchange cassette postali.

### <a name="can-administrators-delete-or-remove-apps"></a>Gli amministratori possono eliminare o rimuovere app?

Sì. Gli amministratori globali possono eliminare o rimuovere app.

- Seleziona un'app dalla visualizzazione elenco. Nella scheda **Configurazione** seleziona le app da rimuovere.  

### <a name="is-integrated-apps-available-in-sovereign-cloud"></a>Le app integrate sono disponibili nel cloud sovrano?

No. Le app integrate non sono disponibili per i clienti cloud sovrani.

### <a name="is-integrated-apps-available-in-government-clouds"></a>Le app integrate sono disponibili nei cloud per enti pubblici?

No. Le app integrate non sono disponibili per i clienti del cloud per enti pubblici.
