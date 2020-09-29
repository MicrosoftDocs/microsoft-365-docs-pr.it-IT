---
title: Distribuire i componenti aggiuntivi nell'interfaccia di amministrazione
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: Informazioni su come distribuire i componenti aggiuntivi per gli utenti e i gruppi dell'organizzazione tramite la distribuzione centralizzata nell'interfaccia di amministrazione.
ms.openlocfilehash: 20ebdfd2072c49fabadcbaf66dead54e75f9becd
ms.sourcegitcommit: 888b9355ef7b933c55ca6c18639c12426ff3fbde
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/29/2020
ms.locfileid: "48304793"
---
# <a name="deploy-add-ins-in-the-admin-center"></a>Distribuire i componenti aggiuntivi nell'interfaccia di amministrazione

::: moniker range="o365-21vianet"

> [!NOTE]
> L'interfaccia di amministrazione sta cambiando. Se alcuni dettagli non corrispondono a quelli presentati qui, vedere [Informazioni sulla nuova interfaccia di amministrazione di Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

I componenti aggiuntivi di Office consentono di personalizzare i documenti e semplificare la modalità di accesso alle informazioni sul Web (vedere [iniziare a utilizzare il componente aggiuntivo di Office](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)). Come amministratore, è possibile distribuire i componenti aggiuntivi di Office per gli utenti dell'organizzazione utilizzando la funzionalità di distribuzione centralizzata nell'interfaccia di amministrazione di Microsoft 365. La distribuzione centralizzata è il metodo consigliato e più ricco di funzionalità per la maggior parte degli amministratori per la distribuzione di componenti aggiuntivi per utenti e gruppi all'interno di un'organizzazione. 

Per ulteriori informazioni su come determinare se l'organizzazione è in grado di supportare la distribuzione centralizzata, vedere [determinare se la distribuzione centralizzata dei componenti aggiuntivi funziona per l'organizzazione](centralized-deployment-of-add-ins.md).

Per ulteriori informazioni sulla gestione dei componenti aggiuntivi dopo la distribuzione, vedere [Manage Add-ins in the Admin Center](manage-addins-in-the-admin-center.md)
  
> [!NOTE]
>  Per Word, Excel e PowerPoint utilizzano un [Catalogo app di SharePoint](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog) per distribuire i componenti aggiuntivi per gli utenti in un ambiente locale senza alcuna connessione a Microsoft 365 e/o il supporto per i componenti aggiuntivi di SharePoint necessari. Per Outlook utilizzare il pannello di controllo di Exchange per la distribuzione in un ambiente locale senza una connessione a Microsoft 365.
  
## <a name="recommended-approach-for-deploying-office-add-ins"></a>Approccio consigliato per la distribuzione dei componenti aggiuntivi per Office

Per implementare i componenti aggiuntivi utilizzando un approccio graduale, è consigliabile eseguire le operazioni seguenti:
  
1. Eseguire il rollforward del componente aggiuntivo in un piccolo gruppo di parti interessate e membri del reparto IT. Se la distribuzione ha esito positivo, passare al passaggio 2.
    
2. Distribuire il componente aggiuntivo a più persone all'interno dell'azienda. Valutare di nuovo i risultati e, in caso di esito positivo, continuare con la distribuzione completa.
    
3. Eseguire un'implementazione completa per tutti gli utenti.
    
A seconda delle dimensioni del gruppo di destinatari, è possibile aggiungere o rimuovere passaggi di roll-out.
  
## <a name="deploy-an-office-add-in-using-the-admin-center"></a>Distribuire un componente aggiuntivo di Office utilizzando l'interfaccia di amministrazione

Prima di iniziare, vedere [determinare se la distribuzione centralizzata dei componenti aggiuntivi funziona per l'organizzazione](centralized-deployment-of-add-ins.md).
  
1. Nell'interfaccia di amministrazione, andare alla pagina dei componenti aggiuntivi di **Impostazioni** \> **Add-ins** . Se la pagina del **componente aggiuntivo** non è visualizzata, passare alla pagina **Impostazioni** \> componenti aggiuntivi **applicazioni integrate** \> **Add-ins** .
    
2. Selezionare **Distribuisci componente aggiuntivo nella** parte superiore della pagina e quindi fare clic su **Avanti**.
 
    > [!NOTE]
    > L'interfaccia di amministrazione si sta aggiornando all'esperienza di distribuzione con le app integrate. Se non vengono visualizzati i passaggi descritti in questo articolo, accedere alla sezione distribuzione centralizzata accedendo alle **impostazioni delle**  >  **app integrate**. Nella parte superiore della pagina **Apps integrata** scegliere **componenti**aggiuntivi.
    
3. Seleziona un'opzione e segui le istruzioni.
  
4. Se è stata selezionata l'opzione per aggiungere un componente aggiuntivo da Office Store, fare la selezione del componente aggiuntivo. </br>

    È possibile visualizzare i componenti aggiuntivi disponibili per categorie: **consigliati per te**, **classificazione**o **nome**. Solo i componenti aggiuntivi gratuiti sono disponibili in Office Store. Quelli a pagamento non sono al momento supportati. Dopo aver selezionato un componente aggiuntivo, accettare i termini e le condizioni per procedere. <br/> 

    > [!NOTE] 
    > Con l'opzione Office Store, gli aggiornamenti e i miglioramenti sono automaticamente agli utenti.

5. Nella pagina successiva selezionare **tutti**, **utenti/gruppi specifici**o **solo me** per specificare l'utente a cui è distribuito il componente aggiuntivo. Utilizzare la casella di ricerca per trovare utenti o gruppi specifici. <br/>

    > [!NOTE] 
    > Per ulteriori informazioni sugli altri Stati che si applicano a un componente aggiuntivo, vedere [stati dei componenti](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center.md)aggiuntivi.
  
6. Fare clic su **Distribuisci**.
  
7. Quando si distribuisce il componente aggiuntivo, viene visualizzato un segno di spunta verde. Seguire le istruzioni visualizzate nella pagina per testare il componente aggiuntivo.

    > [!NOTE]
    > Gli utenti potrebbero dover rilanciare Office per visualizzare l'icona del componente aggiuntivo sulla barra multifunzione dell'app. I componenti aggiuntivi di Outlook possono richiedere fino a 24 ore per essere visualizzati sui nastri delle app.
    
8. Al termine, selezionare **Avanti**. Se è stata distribuita solo da solo, è possibile selezionare **cambia chi ha accesso al componente aggiuntivo** per la distribuzione a più utenti.

    Se il componente aggiuntivo è stato distribuito ad altri membri dell'organizzazione, seguire le istruzioni per annunciare la distribuzione del componente aggiuntivo. <br/>
  
    È consigliabile informare gli utenti e i gruppi che è disponibile il componente aggiuntivo distribuito. È consigliabile inviare un messaggio di posta elettronica che descrive quando e come utilizzare il componente aggiuntivo. Includere o collegare un collegamento al contenuto o alle domande frequenti che potrebbero essere utili agli utenti in caso di problemi con il componente aggiuntivo.
  
### <a name="considerations-when-assigning-an-add-in-to-users-and-groups"></a>Considerazioni per l'assegnazione di un componente aggiuntivo a utenti e gruppi

Gli amministratori possono assegnare un componente aggiuntivo a tutti gli utenti o a gruppi e utenti specifici. Ogni opzione ha delle implicazioni:
  
- **Tutti gli utenti** Questa opzione consente di assegnare il componente aggiuntivo a tutti gli utenti dell'organizzazione. Usare questa opzione con moderazione e solo per i componenti aggiuntivi che effettivamente servono a tutti gli utenti dell'organizzazione. 
    
- **Utenti** Se si assegna un componente aggiuntivo a un singolo utente e quindi si distribuisce il componente aggiuntivo in un nuovo utente, è necessario innanzitutto aggiungere il nuovo utente.
    
- **Gruppi** Se si assegna un componente aggiuntivo a un gruppo, agli utenti aggiunti al gruppo viene assegnato automaticamente il componente aggiuntivo. Quando un utente viene rimosso da un gruppo, l'utente perde l'accesso al componente aggiuntivo. In entrambi i casi, non è richiesta alcuna azione aggiuntiva da parte dell'amministratore. 

- **Solo me** Se si assegna un componente aggiuntivo solo a te stesso, il componente aggiuntivo viene assegnato solo al tuo account, che è l'ideale per testare il componente aggiuntivo.
    
L'opzione adatta per l'organizzazione dipende dalla configurazione. Tuttavia, è consigliabile effettuare le assegnazioni utilizzando i gruppi. Come amministratore, è possibile che sia più facile gestire i componenti aggiuntivi utilizzando gruppi e controllando l'appartenenza di tali gruppi invece di assegnare singoli utenti ogni volta. In alcuni casi, è possibile limitare l'accesso a un piccolo gruppo di utenti facendo assegnazioni a utenti specifici assegnando manualmente gli utenti.
  
## <a name="more-about-office-add-ins-security"></a>Ulteriori informazioni sulla sicurezza dei componenti aggiuntivi di Office

I componenti aggiuntivi per Office combinano un file manifesto XML che contiene alcuni metadati sul componente aggiuntivo, ma soprattutto che punta a un'applicazione Web che contiene tutto il codice e la logica. Le funzionalità dei componenti aggiuntivi possono variare. Ad esempio, i componenti aggiuntivi possono:
  
- Visualizzare i dati.
    
- Leggere il documento di un utente per offrire servizi contestuali.
    
- Leggere e scrivere dati da e verso il documento di un utente per fornire valore all'utente.
    
Per altre informazioni sui tipi e le funzionalità dei componenti aggiuntivi per Office, vedere [Panoramica della piattaforma Componenti aggiuntivi per Office](https://docs.microsoft.com/office/dev/add-ins/overview/office-add-ins), in particolare la sezione "Anatomia di un componente aggiuntivo per Office".
  
Per interagire con il documento dell'utente, il componente aggiuntivo deve dichiarare il tipo di autorizzazione necessario nel manifesto. Un modello di autorizzazioni di accesso per API JavaScript con cinque livelli costituisce la base per la privacy e la sicurezza degli utenti per i componenti aggiuntivi del riquadro attività. La maggior parte dei componenti aggiuntivi in Office Store sono di livello ReadWriteDocument e quasi tutti i componenti aggiuntivi supportano almeno il livello ReadDocument. Per altre informazioni sui livelli di autorizzazione, vedere [Richiesta di autorizzazioni per l'uso di API nei componenti aggiuntivi del contenuto e del riquadro attività](https://docs.microsoft.com/office/dev/add-ins/develop/requesting-permissions-for-api-use-in-content-and-task-pane-add-ins).
  
Quando si aggiorna un manifesto, le modifiche tipiche riguardano l'icona e il testo di un componente aggiuntivo. In alcuni casi, vengono modificati i comandi del componente aggiuntivo. Tuttavia, le autorizzazioni del componente aggiuntivo non cambiano. L'applicazione Web in cui viene eseguito tutto il codice e la logica per il componente aggiuntivo può essere modificata in qualsiasi momento, come accade per tutte le applicazioni Web.
  
Gli aggiornamenti per i componenti aggiuntivi vengono eseguiti come segue:
  
- **Componente aggiuntivo line-of-business:** In questo caso, in cui un amministratore ha caricato in modo esplicito un manifesto, il componente aggiuntivo richiede che l'amministratore carichi un file manifesto nuovo per supportare le modifiche dei metadati. All'avvio successivo delle applicazioni di Office rilevanti, il componente aggiuntivo verrà aggiornato. L'applicazione Web può essere modificata in qualsiasi momento. 

    > [!NOTE]
    > Non è necessario che l'amministratore elimini un componente aggiuntivo LOB per eseguire un aggiornamento.   Nella sezione componenti aggiuntivi, l'amministratore può semplicemente fare clic sul componente aggiuntivo LOB e scegliere il **pulsante Aggiorna** nell'angolo in basso a destra. L'aggiornamento funzionerà solo se la versione del nuovo componente aggiuntivo è maggiore di quella del componente aggiuntivo esistente.   
    
- **Componente aggiuntivo di Office Store:** Se un amministratore ha selezionato un componente aggiuntivo da Office Store e questo viene aggiornato in Office Store, il componente aggiuntivo verrà aggiornato in un secondo momento nella distribuzione centralizzata. All'avvio successivo delle applicazioni di Office rilevanti, il componente aggiuntivo verrà aggiornato. L'applicazione Web può essere modificata in qualsiasi momento. 
  
## <a name="learn-more"></a>Altre informazioni

[Gestire i componenti aggiuntivi nell'interfaccia di amministrazione](manage-addins-in-the-admin-center.md)

[Creazione di componenti aggiuntivi di Office](https://docs.microsoft.com/office/dev/add-ins/overview/office-add-ins-fundamentals).

[Minorenni e acquisizione di componenti aggiuntivi dallo Store](minors-and-acquiring-addins-from-the-store.md)
  
[Utilizzare i cmdlet di PowerShell per la distribuzione centralizzata per gestire i componenti aggiuntivi](https://docs.microsoft.com/microsoft-365/enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins)
  
[Risoluzione dei problemi: utenti che non vedono componenti aggiuntivi](https://docs.microsoft.com/office365/troubleshoot/access-management/user-not-seeing-add-ins)
