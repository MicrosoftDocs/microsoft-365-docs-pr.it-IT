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
description: Informazioni su come distribuire componenti aggiuntivi a utenti e gruppi dell'organizzazione tramite distribuzione centralizzata nell'interfaccia di amministrazione.
ms.openlocfilehash: 796517ba13a4718c38d5200fcf9cbe38b5dc62d0
ms.sourcegitcommit: 50f484fc501d81506a714b127a56a6979888d849
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/05/2021
ms.locfileid: "52779639"
---
# <a name="deploy-add-ins-in-the-admin-center"></a>Distribuire i componenti aggiuntivi nell'interfaccia di amministrazione

Office componenti aggiuntivi consentono di personalizzare i documenti e semplificare il modo in cui si accede alle informazioni sul Web (vedere Iniziare a usare il Office [componente aggiuntivo](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)). Gli amministratori possono distribuire Office componenti aggiuntivi per gli utenti dell'organizzazione utilizzando la funzionalità distribuzione centralizzata nell'interfaccia di amministrazione di Microsoft 365 centrale. La distribuzione centralizzata è il modo consigliato e più ricco di funzionalità per la maggior parte degli amministratori di distribuire componenti aggiuntivi a utenti e gruppi all'interno di un'organizzazione.

Per ulteriori informazioni su come determinare se l'organizzazione è in grado di supportare la distribuzione centralizzata, vedere [Determine if Centralized Deployment of add-ins works for your organization](centralized-deployment-of-add-ins.md).

Per ulteriori informazioni sulla gestione dei componenti aggiuntivi dopo la distribuzione, vedere [Gestire i componenti aggiuntivi nell'interfaccia di amministrazione](manage-addins-in-the-admin-center.md)
  
> [!NOTE]
>  Per Word, Excel e PowerPoint utilizzano un Catalogo app [di SharePoint](/office/dev/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog) per distribuire componenti aggiuntivi agli utenti in un ambiente locale senza alcuna connessione a Microsoft 365 e/o supporto per i componenti aggiuntivi di SharePoint necessari. Ad Outlook usare Exchange pannello di controllo per la distribuzione in un ambiente locale senza una connessione a Microsoft 365.
  
## <a name="recommended-approach-for-deploying-office-add-ins"></a>Approccio consigliato per la distribuzione dei componenti aggiuntivi per Office

Per implementare i componenti aggiuntivi utilizzando un approccio graduale, è consigliabile:
  
1. Distribuire il componente aggiuntivo in un gruppo ristretto di stakeholder dell'azienda e di membri del reparto IT. Se la distribuzione ha esito positivo, andare al passaggio 2.
    
2. Implementare il componente aggiuntivo a più utenti all'interno dell'azienda. Valutare nuovamente i risultati e, in caso di esito positivo, continuare con la distribuzione completa.
    
3. Eseguire un'implementazione completa per tutti gli utenti.
    
A seconda delle dimensioni del gruppo di destinatari, è possibile aggiungere o rimuovere passaggi di implementazione.
  
## <a name="deploy-an-office-add-in-using-the-admin-center"></a>Distribuire un componente aggiuntivo per Office con l'interfaccia di amministrazione

Prima di iniziare, vedere [Determine if Centralized Deployment of add-ins works for your organization](centralized-deployment-of-add-ins.md).
  
1. Nell'interfaccia di amministrazione passare alla **Impostazioni** \> **componenti aggiuntivi.** Se la pagina componenti  aggiuntivi non è visualizzata, passare alla pagina componenti aggiuntivi Impostazioni  \>  \> **app integrate.**

2. Selezionare **Distribuisci componente aggiuntivo** nella parte superiore della pagina e quindi selezionare **Avanti.**

    > [!NOTE]
    > L'interfaccia di amministrazione viene aggiornata all'esperienza di distribuzione con le app integrate. Le app integrate sono visibili solo agli amministratori globali, mentre per altri esiste ancora la vecchia esperienza. Se non vedi i passaggi precedenti, vai alla sezione Distribuzione centralizzata andando a Impostazioni  >  **app integrate**. Nella parte superiore della **pagina App integrate** scegliere Componenti **aggiuntivi.**

3. Selezionare un'opzione e seguire le istruzioni.
  
4. Se hai selezionato l'opzione per aggiungere un componente aggiuntivo da Office Store, seleziona il componente aggiuntivo. </br>

    È possibile visualizzare i componenti aggiuntivi disponibili per categorie: **Consigliato per te,** **Valutazione** o **Nome.** Solo i componenti aggiuntivi gratuiti sono disponibili Office Store. Quelli a pagamento non sono al momento supportati. Dopo aver selezionato un componente aggiuntivo, accetta i termini e le condizioni per procedere. <br/> 

    > [!NOTE]
    > Con l'opzione Office Store, gli aggiornamenti e i miglioramenti vengono distribuiti automaticamente agli utenti.

5. Nella stessa pagina selezionare **Tutti**, **Utenti/gruppi specifici** o **Soltanto io** per specificare per chi distribuire il componente aggiuntivo. Utilizzare la casella Di ricerca per trovare utenti o gruppi specifici. <br/>

    > [!NOTE]
    > Per informazioni sugli altri stati applicabili a un componente aggiuntivo, vedere [Stati dei componenti aggiuntivi](./manage-addins-in-the-admin-center.md).
  
6. Selezionare **Distribuisci**.
  
7. Quando il componente aggiuntivo viene distribuito, viene visualizzato un segno di spunta verde. Seguire le istruzioni visualizzate nella pagina per testare il componente aggiuntivo.

    > [!NOTE]
    > Gli utenti potrebbero dover Office per visualizzare l'icona del componente aggiuntivo sulla barra multifunzione dell'app. Outlook componenti aggiuntivi possono richiedere fino a 24 ore per essere visualizzati sulle barre multifunzione dell'app.

8. Al termine, selezionare **Avanti**. Se si è distribuito a se stessi, è possibile selezionare Cambia chi ha accesso al componente aggiuntivo **per** la distribuzione a più utenti.

    Se il componente aggiuntivo è stato distribuito ad altri membri dell'organizzazione, seguire le istruzioni per annunciare la distribuzione del componente aggiuntivo. <br/>
  
    È consigliabile informare utenti e gruppi che il componente aggiuntivo distribuito è disponibile. Prendere in considerazione l'invio di un messaggio di posta elettronica che descrive quando e come utilizzare il componente aggiuntivo. Includere o collegare il contenuto della Guida o le domande frequenti che potrebbero aiutare gli utenti in caso di problemi con il componente aggiuntivo.
  
### <a name="considerations-when-assigning-an-add-in-to-users-and-groups"></a>Considerazioni per l'assegnazione di un componente aggiuntivo a utenti e gruppi

Gli amministratori globali e Exchange possono assegnare un componente aggiuntivo a tutti gli utenti o a utenti e gruppi specifici. Ogni opzione ha delle implicazioni:
  
- **Tutti** Questa opzione consente di assegnare il componente aggiuntivo a ogni utente dell'organizzazione. Usare questa opzione con moderazione e solo per i componenti aggiuntivi che effettivamente servono a tutti gli utenti dell'organizzazione.

- **Utenti** Se si assegna un componente aggiuntivo a un singolo utente e quindi si distribuisce il componente aggiuntivo a un nuovo utente, è necessario innanzitutto aggiungere il nuovo utente.

- **Gruppi** Se si assegna un componente aggiuntivo a un gruppo, agli utenti aggiunti al gruppo verrà assegnato automaticamente il componente aggiuntivo. Quando un utente viene rimosso da un gruppo, perde l'accesso al componente aggiuntivo. In entrambi i casi, l'amministratore non richiede alcuna azione aggiuntiva.

- **Just me** Se assegni un componente aggiuntivo solo a te stesso, il componente aggiuntivo viene assegnato solo al tuo account, ideale per testare il componente aggiuntivo.

L'opzione giusta per l'organizzazione dipende dalla configurazione. Tuttavia, è consigliabile eseguire le assegnazioni utilizzando i gruppi. Gli amministratori possono semplificare la gestione dei componenti aggiuntivi utilizzando i gruppi e controllando l'appartenenza a tali gruppi anziché assegnare ogni volta singoli utenti. In alcuni casi, è possibile limitare l'accesso a un piccolo set di utenti assegnando manualmente gli utenti a utenti specifici.
  
## <a name="more-about-office-add-ins-security"></a>Altre informazioni Office sicurezza dei componenti aggiuntivi

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
    > L'amministratore non deve rimuovere un componente aggiuntivo LOB per eseguire un aggiornamento.   Nella sezione Componenti aggiuntivi, l'amministratore può semplicemente fare clic sul componente aggiuntivo LOB e scegliere il **pulsante Aggiorna** nell'angolo in basso a destra. L'aggiornamento funzionerà solo se la versione del nuovo componente aggiuntivo è maggiore di quella del componente aggiuntivo esistente.

- **Componente aggiuntivo di Office Store:** Se un amministratore ha selezionato un componente aggiuntivo da Office Store e questo viene aggiornato in Office Store, il componente aggiuntivo verrà aggiornato in un secondo momento nella distribuzione centralizzata. All'avvio successivo delle applicazioni di Office rilevanti, il componente aggiuntivo verrà aggiornato. L'applicazione Web può essere modificata in qualsiasi momento.
  
## <a name="related-content"></a>Contenuto correlato

[Gestire i componenti aggiuntivi nell'interfaccia di amministrazione](manage-addins-in-the-admin-center.md) (articolo)\
[Creare il primo componente aggiuntivo del riquadro attività di Word](/office/dev/add-ins/quickstarts/word-quickstart?tabs=yeomangenerator) (articolo\
[Minors and acquiring add-ins from the store](minors-and-acquiring-addins-from-the-store.md) (article)\ [Use Centralized Deployment PowerShell cmdlets to manage add-ins](../../enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins.md) (article)\  
[Risoluzione dei problemi: l'utente non vede i componenti aggiuntivi](/office365/troubleshoot/access-management/user-not-seeing-add-ins) (articolo)