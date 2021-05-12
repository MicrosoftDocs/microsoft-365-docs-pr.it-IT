---
title: Gestire i componenti aggiuntivi nell'interfaccia di amministrazione
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: Informazioni sull'utilizzo di componenti aggiuntivi centralizzati per distribuire componenti aggiuntivi a utenti e gruppi dell'organizzazione.
ms.openlocfilehash: 76bfa6272ec784518f045a50299fc7cda719eec8
ms.sourcegitcommit: 68383240ef7a673d5f28e2ecfab9f105bf1d8c8f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2021
ms.locfileid: "52327199"
---
# <a name="manage-add-ins-in-the-admin-center"></a>Gestire i componenti aggiuntivi nell'interfaccia di amministrazione

I componenti aggiuntivi di Office consentono di personalizzare i documenti e semplificare il modo in cui si accede alle informazioni sul Web (vedere Iniziare a usare il componente aggiuntivo [di Office).](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862) 

Dopo che un amministratore distribuisce componenti aggiuntivi per gli utenti di un'organizzazione, l'amministratore può disattivare o attivare, modificare, eliminare e gestire l'accesso ai componenti aggiuntivi.

Per ulteriori informazioni sull'installazione di componenti aggiuntivi dall'interfaccia di amministrazione, vedere [Distribuire componenti aggiuntivi nell'interfaccia di amministrazione.](./manage-deployment-of-add-ins.md)
  
## <a name="add-in-states"></a>Stati dei componenti aggiuntivi

Un componente aggiuntivo può essere nello stato **Attivo** **o Disattivato.**
  
| Stato | Quando si verifica lo stato | Impatto |
|:-----|:-----|:-----|
|**Attivo**  <br/> |L'amministratore ha caricato il componente aggiuntivo e lo ha assegnato a utenti o gruppi.  <br/> |Gli utenti e i gruppi assegnati al componente aggiuntivo lo vedono nei client pertinenti.  <br/> |
|**Disattivato**  <br/> |L'amministratore ha disattivato il componente aggiuntivo.  <br/> |Gli utenti e i gruppi assegnati al componente aggiuntivo non possono più accedervi.  <br/> Se lo stato del componente aggiuntivo viene modificato su Attivo, gli utenti e i gruppi potranno accedervi di nuovo.  <br/> |
|**Eliminato**  <br/> |L'amministratore ha eliminato il componente aggiuntivo.  <br/> |Gli utenti e i gruppi assegnati al componente aggiuntivo non possono più accedervi.  <br/> |
   
Prendere in considerazione l'eliminazione di un componente aggiuntivo se non viene più utilizzato da nessuno. Ad esempio, la disattivazione di un componente aggiuntivo potrebbe avere senso se un componente aggiuntivo viene utilizzato solo in periodi specifici dell'anno.

## <a name="delete-an-add-in"></a>Eliminare un componente aggiuntivo

È inoltre possibile eliminare un componente aggiuntivo distribuito.

1. Nell'interfaccia di amministrazione passare alla pagina  >  **Servizi & componenti aggiuntivi.**

    > [!NOTE]
    > L'interfaccia di amministrazione viene aggiornata all'esperienza di distribuzione con le app integrate. Se non vedi i passaggi precedenti, vai alla sezione Distribuzione centralizzata andando a **Impostazioni**  >  **App integrate.** Nella parte superiore della **pagina App integrate** scegliere Componenti **aggiuntivi.**

2. Selezionare il componente aggiuntivo distribuito.

3. Fare clic **su Elimina componente aggiuntivo**. Rimuovi il pulsante Componente aggiuntivo nell'angolo in basso a destra.

4. Convalidare le selezioni e scegliere **Rimuovi componente aggiuntivo.**

## <a name="edit-add-in-access"></a>Modificare l'accesso ai componenti aggiuntivi

Dopo la distribuzione, gli amministratori possono anche gestire l'accesso degli utenti ai componenti aggiuntivi.

1. Nell'interfaccia di amministrazione passare alla pagina  >  **Servizi & componenti aggiuntivi.**

    > [!NOTE]
    > L'interfaccia di amministrazione viene aggiornata all'esperienza di distribuzione con le app integrate. Se non vedi i passaggi precedenti, vai alla sezione Distribuzione centralizzata andando a **Impostazioni**  >  **App integrate.** Nella parte superiore della **pagina App integrate** scegliere Componenti **aggiuntivi.**

2. Selezionare il componente aggiuntivo distribuito.

3. Fare clic **su Modifica** in Chi **ha accesso**.

4. Salvare le modifiche.

## <a name="prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook"></a>Impedire i download di componenti aggiuntivi disattivando Office Store in tutti i client (ad eccezione di Outlook)

> [!NOTE]
> L'installazione del componente aggiuntivo di Outlook è gestita da [un processo diverso.](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/specify-who-can-install-and-manage-add-ins)

In quanto organizzazione è possibile impedire il download di nuovi componenti aggiuntivi di Office da Office Store. Può essere utilizzato insieme alla distribuzione centralizzata per garantire che solo i componenti aggiuntivi approvati dall'organizzazione siano distribuiti agli utenti all'interno dell'organizzazione.
  
**Per disattivare l'acquisizione di componenti aggiuntivi**
  
1. Nell'interfaccia di amministrazione passare a **Impostazioni** \> [Servizi &amp; componenti aggiuntivi](https://go.microsoft.com/fwlink/p/?linkid=2053743).

    > [!NOTE]
    > L'interfaccia di amministrazione viene aggiornata all'esperienza di distribuzione con le app integrate. Se non vedi i passaggi precedenti, vai alla sezione Distribuzione centralizzata andando a **Impostazioni**  >  **App integrate.** Nella parte superiore della **pagina App integrate** scegliere Componenti **aggiuntivi.**
    
3. Selezionare **App e servizi di proprietà dell'utente.**
    
4. Deselezionare l'opzione per consentire agli utenti di accedere a Office Store.

    Questo impedirà a tutti gli utenti di acquisire i componenti aggiuntivi seguenti dallo Store.
      
    - Componenti aggiuntivi per Word, Excel e PowerPoint 2016 da:
        
      - Windows
      - Mac
      - Office
        
        
    - Acquisizioni a partire da **AppSource**
        
    - Componenti aggiuntivi in Microsoft 365
        
    Un utente che tenta di accedere all'archivio visualizza il messaggio seguente: **Spiacenti, Microsoft 365 è** stato configurato per impedire l'acquisizione individuale di componenti aggiuntivi di Office Store.
  
Il supporto per la disattivazione di Office Store è disponibile nelle versioni seguenti:
  
- Windows: 16.0.9001 - Attualmente disponibile.
    
- Mac: 16.10.18011401 - Attualmente disponibile.
    
- iOS: 2.9.18010804 - Attualmente disponibile.
    
- Web - Attualmente disponibile.
    
Ciò non impedisce a un amministratore di utilizzare la distribuzione centralizzata per assegnare un componente aggiuntivo da Office Store.
  
Per impedire a un utente di accedere con un account Microsoft, è possibile limitare l'accesso in modo che utilizzi solo l'account dell'organizzazione. Per ulteriori informazioni, vedere [Identity, authentication, and authorization in Office 2016](/DeployOffice/security/identity-authentication-and-authorization-in-office).  

> [!NOTE] 
> Impedire agli utenti di accedere all'Office Store impedirà anche loro di sideload dei componenti aggiuntivi di Office per il [testing da una condivisione di rete.](/office/dev/add-ins/testing/create-a-network-shared-folder-catalog-for-task-pane-and-content-add-ins)

## <a name="more-about-the-end-user-experience-with-add-ins"></a>Altre informazioni sull'esperienza dell'utente finale con i componenti aggiuntivi

Dopo aver distribuito un componente aggiuntivo, gli utenti finali possono iniziare a usarlo nelle applicazioni di Office (vedere Iniziare a [usare il componente aggiuntivo di Office](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)). Il componente aggiuntivo viene visualizzato in tutte le piattaforme supportate dal componente aggiuntivo.
  
Se il componente aggiuntivo supporta i comandi dell'interfaccia, questi vengono visualizzati sulla barra multifunzione di Office. Nell'esempio seguente il comando **Cerca citazione** viene visualizzato per il componente aggiuntivo **Citazioni**. 

![Barra multifunzione di Office con citazioni di ricerca](../../media/553b0c0a-65e9-4746-b3b0-8c1b81715a86.png)
  
Se il componente aggiuntivo distribuito non supporta i comandi dei componenti aggiuntivi o se si desidera visualizzare tutti i componenti aggiuntivi distribuiti, è possibile visualizzarli tramite I **miei componenti aggiuntivi.** 
  
### <a name="in-word-2016-excel-2016-or-powerpoint-2016"></a>In Word 2016, Excel 2016 o PowerPoint 2016

1. Selezionare **Inserisci \> componenti aggiuntivi.** 
    
2. Selezionare la scheda **Gestito dall'amministratore** nella finestra Componenti aggiuntivi per Office. 
    
3. Fare doppio clic sul componente aggiuntivo distribuito in precedenza (in questo esempio **Citations**).

    ![Scheda Gestito dall'amministratore della pagina Componenti aggiuntivi di Office](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)
  
### <a name="in-outlook"></a>In Outlook

1. Sulla barra **multifunzione Home** selezionare Ottieni **componenti aggiuntivi.**

    ![Pulsante Store in Outlook](../../media/getaddinsicon.png)
  
2. Seleziona **Gestito dall'amministratore** nel riquadro di spostamento sinistro. 

## <a name="learn-more"></a>Altre informazioni

[Distribuire i componenti aggiuntivi nell'interfaccia di amministrazione](./manage-deployment-of-add-ins.md)

Altre informazioni sulla creazione e sulla compilazione dei [componenti aggiuntivi per Office](/office/dev/add-ins/overview/office-add-ins).
  
[Utilizzare i cmdlet di PowerShell per la distribuzione centralizzata per gestire i componenti aggiuntivi.](../../enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins.md)
  
[Risoluzione dei problemi: l'utente non vede i componenti aggiuntivi](/office365/troubleshoot/access-management/user-not-seeing-add-ins)

[Minori e acquisizione di componenti aggiuntivi da Microsoft Store](./minors-and-acquiring-addins-from-the-store.md)