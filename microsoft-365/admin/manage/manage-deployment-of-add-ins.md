---
title: Distribuire i componenti aggiuntivi nell'interfaccia di amministrazione
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: Informazioni sulla distribuzione di componenti aggiuntivi a utenti e gruppi nell'organizzazione tramite distribuzione centralizzata nell'interfaccia di amministrazione.
ms.openlocfilehash: 2d3b90a75f38a2c1146c0b0e5470c80b0af2c63f
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572274"
---
# <a name="deploy-add-ins-in-the-admin-center"></a>Distribuire i componenti aggiuntivi nell'interfaccia di amministrazione

Office componenti aggiuntivi consentono di personalizzare i documenti e semplificare il modo in cui si accede alle informazioni sul Web [(vedere Iniziare a utilizzare il componente aggiuntivo Office distribuzione](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)). In qualità di amministratore, è possibile distribuire Office componenti aggiuntivi per gli utenti dell'organizzazione utilizzando la funzionalità Distribuzione centralizzata nell'interfaccia di Microsoft 365 di amministrazione. La distribuzione centralizzata è il modo consigliato e più ricco di funzionalità per la maggior parte degli amministratori di distribuire componenti aggiuntivi a utenti e gruppi all'interno di un'organizzazione.

Per ulteriori informazioni su come determinare se l'organizzazione è in grado di supportare la distribuzione centralizzata, [vedere Determine if Centralized Deployment of add-ins works for your organization](centralized-deployment-of-add-ins.md).

Per altre informazioni sulla gestione dei componenti aggiuntivi dopo la distribuzione, vedere [Manage add-ins in the admin center](manage-addins-in-the-admin-center.md)
  
> [!NOTE]
>  Per Word, Excel e PowerPoint usano [un catalogo app SharePoint](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog) per distribuire componenti aggiuntivi agli utenti in un ambiente locale senza alcuna connessione a Microsoft 365 e/o supporto per i componenti aggiuntivi SharePoint necessari. Per Outlook utilizzare Exchange pannello di controllo per eseguire la distribuzione in un ambiente locale senza una connessione a Microsoft 365.
  
## <a name="recommended-approach-for-deploying-office-add-ins"></a>Approccio consigliato per la distribuzione dei componenti aggiuntivi per Office

Per implementare componenti aggiuntivi utilizzando un approccio graduale, è consigliabile:
  
1. Distribuire il componente aggiuntivo in un gruppo ristretto di stakeholder dell'azienda e di membri del reparto IT. Se la distribuzione ha esito positivo, passare al passaggio 2.
    
2. Distribuire il componente aggiuntivo a più persone all'interno dell'azienda. Anche in questo caso, valutare i risultati e, in caso di esito positivo, continuare con la distribuzione completa.
    
3. Eseguire un'implementazione completa per tutti gli utenti.
    
A seconda delle dimensioni del gruppo di destinatari, è possibile aggiungere o rimuovere i passaggi di implementazione.
  
## <a name="deploy-an-office-add-in-using-the-admin-center"></a>Distribuire un componente aggiuntivo per Office con l'interfaccia di amministrazione

Prima di iniziare, vedere [Determinare se la distribuzione centralizzata dei componenti aggiuntivi funziona per l'organizzazione](centralized-deployment-of-add-ins.md).
  
1. Nell'interfaccia di amministrazione passare **alla pagina Impostazioni** componenti \> **aggiuntivi.** Se la pagina del componente **aggiuntivo non è presente,** passare **alla pagina Impostazioni** \> **componenti** aggiuntivi \> **per app** integrate.

2. Selezionare **Distribuisci componente** aggiuntivo nella parte superiore della pagina e quindi **Avanti**.

    > [!NOTE]
    > L'interfaccia di amministrazione viene aggiornata all'esperienza di distribuzione con le app integrate. Le app integrate sono visibili solo agli amministratori globali, mentre per altri la vecchia esperienza esiste ancora. Se i passaggi precedenti non sono disponibili, passare alla sezione Distribuzione centralizzata per passare a **Impostazioni**  >  **app integrate**. Nella parte superiore della **pagina App** integrate scegliere **Componenti aggiuntivi**.

3. Selezionare un'opzione e seguire le istruzioni.
  
4. Se hai selezionato l'opzione per aggiungere un componente aggiuntivo dal Office Store, fai la selezione del componente aggiuntivo. </br>

    È possibile visualizzare i componenti aggiuntivi disponibili per categorie: **Suggerito per l'utente**, **Classificazione** o **Nome**. Solo i componenti aggiuntivi gratuiti sono disponibili dal Office Store. Quelli a pagamento non sono al momento supportati. Dopo aver selezionato un componente aggiuntivo, accettare i termini e le condizioni per procedere. <br/> 

    > [!NOTE]
    > Con l Office di Archiviazione, gli aggiornamenti e i miglioramenti vengono distribuiti automaticamente agli utenti.

5. Nella stessa pagina selezionare **Tutti**, **Utenti/gruppi specifici** o **Soltanto io** per specificare per chi distribuire il componente aggiuntivo. Usare la casella di ricerca per trovare utenti o gruppi specifici. <br/>

    > [!NOTE]
    > Per informazioni su altri stati applicabili a un componente aggiuntivo, vedere [Stati componente aggiuntivo](./manage-addins-in-the-admin-center.md).
  
6. Selezionare **Distribuisci**.
  
7. Quando viene distribuito il componente aggiuntivo viene visualizzato un segno di spunta verde. Seguire le istruzioni visualizzate per testare il componente aggiuntivo.

    > [!NOTE]
    > Gli utenti potrebbero dover riavviare Office per visualizzare l'icona del componente aggiuntivo sulla barra multifunzione dell'app. Outlook componenti aggiuntivi possono richiedere fino a 24 ore per essere visualizzati sulle barre multifunzione dell'app.

8. Al termine, selezionare **Avanti**. Se è stata distribuita solo in te stesso, puoi selezionare **Cambia chi ha accesso al componente aggiuntivo da** distribuire a più utenti.

    Se il componente aggiuntivo è stato distribuito ad altri membri dell'organizzazione, seguire le istruzioni per annunciare la distribuzione del componente aggiuntivo. <br/>
  
    È buona pratica informare utenti e gruppi che il componente aggiuntivo distribuito è disponibile. Valutare la possibilità di inviare un messaggio di posta elettronica che descriva quando e come usare il componente aggiuntivo. Includere o collegare al contenuto della Guida o alle domande frequenti che potrebbero aiutare gli utenti in caso di problemi con il componente aggiuntivo.
  
### <a name="considerations-when-assigning-an-add-in-to-users-and-groups"></a>Considerazioni per l'assegnazione di un componente aggiuntivo a utenti e gruppi

Gli amministratori e gli amministratori Exchange globali possono assegnare un componente aggiuntivo a tutti o a utenti e gruppi specifici. Ogni opzione ha delle implicazioni:
  
- **Tutti** Questa opzione assegna il componente aggiuntivo a tutti gli utenti dell'organizzazione. Usare questa opzione con moderazione e solo per i componenti aggiuntivi che effettivamente servono a tutti gli utenti dell'organizzazione.

- **Utenti** Se si assegna un componente aggiuntivo a un singolo utente e quindi si distribuisce il componente aggiuntivo a un nuovo utente, è innanzitutto necessario aggiungere il nuovo utente.

- **Gruppi** Se si assegna un componente aggiuntivo a un gruppo, agli utenti aggiunti al gruppo viene assegnato automaticamente il componente aggiuntivo. Quando un utente viene rimosso da un gruppo, l'utente perde l'accesso al componente aggiuntivo. In entrambi i casi, non è richiesta alcuna azione aggiuntiva da parte dell'amministratore.

- **Solo io** Se assegni un componente aggiuntivo solo a te stesso, il componente aggiuntivo viene assegnato solo al tuo account, ideale per testare il componente aggiuntivo.

L'opzione giusta per l'organizzazione dipende dalla configurazione. Tuttavia, è consigliabile effettuare assegnazioni utilizzando i gruppi. In qualità di amministratore, potrebbe essere più facile gestire i componenti aggiuntivi utilizzando i gruppi e controllando l'appartenenza a tali gruppi anziché assegnare ogni volta singoli utenti. In alcune situazioni, è possibile limitare l'accesso a un piccolo set di utenti effettuando assegnazioni a utenti specifici assegnando manualmente gli utenti.
  
## <a name="more-about-office-add-ins-security"></a>Altre informazioni sulla Office dei componenti aggiuntivi

I componenti aggiuntivi per Office combinano un file manifesto XML che contiene alcuni metadati sul componente aggiuntivo, ma soprattutto che punta a un'applicazione Web che contiene tutto il codice e la logica. Le funzionalità dei componenti aggiuntivi possono variare. Ad esempio, i componenti aggiuntivi possono:
  
- Visualizzare i dati.

- Leggere il documento di un utente per offrire servizi contestuali.

- Leggere e scrivere dati da e verso il documento di un utente per fornire valore all'utente.

Per altre informazioni sui tipi e le funzionalità dei componenti aggiuntivi per Office, vedere [Panoramica della piattaforma Componenti aggiuntivi per Office](/office/dev/add-ins/overview/office-add-ins), in particolare la sezione "Anatomia di un componente aggiuntivo per Office".
  
Per interagire con il documento dell'utente, il componente aggiuntivo deve dichiarare il tipo di autorizzazione necessario nel manifesto. Un modello di autorizzazioni di accesso per API JavaScript con cinque livelli costituisce la base per la privacy e la sicurezza degli utenti per i componenti aggiuntivi del riquadro attività. La maggior parte dei componenti aggiuntivi in Office Store sono di livello ReadWriteDocument e quasi tutti i componenti aggiuntivi supportano almeno il livello ReadDocument. Per altre informazioni sui livelli di autorizzazione, vedere [Richiesta di autorizzazioni per l'uso di API nei componenti aggiuntivi del contenuto e del riquadro attività](/office/dev/add-ins/develop/requesting-permissions-for-api-use-in-content-and-task-pane-add-ins).
  
Quando si aggiorna un manifesto, le modifiche tipiche riguardano l'icona e il testo di un componente aggiuntivo. In alcuni casi, vengono modificati i comandi del componente aggiuntivo. Tuttavia, le autorizzazioni del componente aggiuntivo non cambiano. L'applicazione Web in cui viene eseguito tutto il codice e la logica per il componente aggiuntivo può essere modificata in qualsiasi momento, come accade per tutte le applicazioni Web.
  
Gli aggiornamenti per i componenti aggiuntivi vengono eseguiti come segue:
  
- **Componente aggiuntivo line-of-business:** In questo caso, in cui un amministratore ha caricato in modo esplicito un manifesto, il componente aggiuntivo richiede che l'amministratore carichi un file manifesto nuovo per supportare le modifiche dei metadati. All'avvio successivo delle applicazioni di Office rilevanti, il componente aggiuntivo verrà aggiornato. L'applicazione Web può essere modificata in qualsiasi momento.

    > [!NOTE]
    > L'amministratore non deve rimuovere un componente aggiuntivo LOB per l'aggiornamento.   Nella sezione Componenti aggiuntivi, Admin può semplicemente fare clic sul componente aggiuntivo LOB e scegliere il **pulsante Aggiorna nell'angolo** in basso a destra. L'aggiornamento funzionerà solo se la versione del nuovo componente aggiuntivo è maggiore di quella del componente aggiuntivo esistente.

- **Componente aggiuntivo di Office Store:** Se un amministratore ha selezionato un componente aggiuntivo da Office Store e questo viene aggiornato in Office Store, il componente aggiuntivo verrà aggiornato in un secondo momento nella distribuzione centralizzata. All'avvio successivo delle applicazioni di Office rilevanti, il componente aggiuntivo verrà aggiornato. L'applicazione Web può essere modificata in qualsiasi momento.
  
## <a name="related-content"></a>Contenuti correlati

[Gestire i componenti aggiuntivi nell'interfaccia di amministrazione](manage-addins-in-the-admin-center.md) (articolo)

[Creare il primo componente aggiuntivo del riquadro attività di Word](/office/dev/add-ins/quickstarts/word-quickstart?tabs=yeomangenerator) (articolo)

[Minori e acquisizione di componenti aggiuntivi dal negozio](minors-and-acquiring-addins-from-the-store.md) (articolo)
  
[Utilizzare i cmdlet di PowerShell per la distribuzione centralizzata per gestire i componenti aggiuntivi](../../enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins.md) (articolo)
  
[Risoluzione dei problemi: utente che non vede i componenti aggiuntivi](/office365/troubleshoot/access-management/user-not-seeing-add-ins) (articolo)