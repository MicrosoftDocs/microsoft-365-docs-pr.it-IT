---
title: Gestire un sito del team di SharePoint Online isolato
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 79a61003-4905-4ba8-9e8a-16def7add37c
description: Gestire un sito del team di SharePoint Online isolato, aggiungere nuovi utenti e gruppi, rimuovere utenti e gruppi e creare una sottocartella di documenti con autorizzazioni personalizzate.
ms.openlocfilehash: 05e3cf742482d34c158e14253eed9d1b99c82995
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "44036633"
---
# <a name="manage-an-isolated-sharepoint-online-team-site"></a>Gestire un sito del team di SharePoint Online isolato

 **Sintesi:** gestire il sito del team di SharePoint Online isolato con queste procedure.
  
In questo articolo vengono descritte le comuni operazioni di gestione per un sito del team di SharePoint Online isolato.
  
## <a name="add-a-new-user"></a>Aggiungere un nuovo utente

Quando un nuovo utente accede al sito, è necessario decidere il livello di partecipazione di tale utente nel sito:
  
- Amministrazione: aggiungere il nuovo account utente al gruppo di accesso degli amministratori del sito
    
- Collaborazione attiva: aggiungere l'account utente al gruppo di accesso dei membri del sito
    
- Visualizzazione: aggiungere l'account utente al gruppo di accesso dei visualizzatori del sito
    
Se si gestiscono gli account utente e i gruppi tramite servizi di dominio Active Directory, aggiungere gli utenti idonei ai gruppi di accesso appropriato utilizzando le normali procedure di gestione di utenti e gruppi di AD DS e attendere la sincronizzazione con l'abbonamento.
  
Se si gestiscono gli account utente e i gruppi tramite Microsoft 365, è possibile utilizzare l'interfaccia di amministrazione di Microsoft 365 o Microsoft PowerShell:
  
- Per l'interfaccia di amministrazione di Microsoft 365, accedere con un account utente a cui è stato assegnato l'amministratore dell'account utente o il ruolo di amministratore dell'azienda e utilizzare i gruppi per aggiungere gli utenti adatti ai gruppi di accesso appropriato.
    
- Per PowerShell, [connettersi prima con il modulo di Azure Active Directory PowerShell per Graph](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module). Per aggiungere un account utente a un gruppo di accesso con il relativo nome dell'entità utente (UPN), utilizzare il seguente blocco di comandi di PowerShell:
    
```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

Per aggiungere un account utente a un gruppo di accesso con il relativo nome visualizzato, utilizzare il seguente blocco di comandi di PowerShell:

```powershell
$userDisplayName="<display name of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="add-a-new-group"></a>Aggiungere un nuovo gruppo

Per aggiungere l'accesso per un intero gruppo, è necessario decidere il livello di partecipazione di tutti i membri del gruppo nel sito:
  
- Amministrazione: aggiungere il gruppo al gruppo di accesso degli amministratori del sito
    
- Collaborazione attiva: aggiungere il gruppo al gruppo di accesso dei membri del sito
    
- Visualizzazione: aggiungere il gruppo al gruppo di accesso dei visualizzatori del sito
    
Se si gestiscono account utente e gruppi tramite servizi di dominio Active Directory, aggiungere i gruppi adatti ai gruppi corretti utilizzando le normali procedure di gestione di utenti e gruppi di servizi di dominio Active Directory e attendere la sincronizzazione con l'abbonamento.
  
Se si gestiscono gli account utente e i gruppi tramite Office 365, è possibile utilizzare l'interfaccia di amministrazione di Microsoft 365 o PowerShell:
  
- Per l'interfaccia di amministrazione di Microsoft 365, accedere con un account utente a cui è stato assegnato l'amministratore dell'account utente o il ruolo di amministratore dell'azienda e utilizzare i gruppi per aggiungere i gruppi adatti ai gruppi di accesso appropriato.
    
- Per PowerShell, [connettersi prima con il modulo di Azure Active Directory PowerShell per Graph](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).
 Successivamente, utilizzare i comandi di PowerShell seguenti:
 
```powershell
$newGroupName="<display name of the new group to add>"
$siteGrpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $newGroupName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $siteGrpName }).ObjectID
```

## <a name="remove-a-user"></a>Rimuovere un utente

Quando è necessario rimuovere l'accesso di un utente dal sito, si rimuove tale utente dal gruppo di accesso di cui è attualmente membro in base alla sua partecipazione nel sito:
  
- Amministrazione: rimuovere l'account utente dal gruppo di accesso degli amministratori del sito
    
- Collaborazione attiva: rimuovere l'account utente dal gruppo di accesso dei membri del sito
    
- Visualizzazione: rimuovere l'account utente dal gruppo di accesso dei visualizzatori del sito
    
Se si gestiscono account utente e gruppi tramite servizi di dominio Active Directory, rimuovere gli utenti idonei dai gruppi di accesso appropriato utilizzando le normali procedure di gestione di utenti e gruppi di servizi di dominio Active Directory e attendere la sincronizzazione con l'abbonamento.
  
Se si gestiscono gli account utente e i gruppi tramite Office 365, è possibile utilizzare l'interfaccia di amministrazione di Microsoft 365 o PowerShell:
  
- Per l'interfaccia di amministrazione di Microsoft 365, accedere con un account utente a cui è stato assegnato l'amministratore dell'account utente o il ruolo di amministratore dell'azienda e utilizzare i gruppi per rimuovere gli utenti idonei dai gruppi di accesso appropriato.
    
- Per PowerShell, [connettersi prima con il modulo di Azure Active Directory PowerShell per Graph](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).
Per rimuovere un account utente da un gruppo di accesso con il relativo UPN, utilizzare il seguente blocco di comandi di PowerShell:
    
```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

Per rimuovere un account utente da un gruppo di accesso con il relativo nome visualizzato, utilizzare il seguente blocco di comandi di PowerShell:
    
```powershell
$userDisplayName="<display name of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="remove-a-group"></a>Rimuovere un gruppo

Per rimuovere l'accesso per un intero gruppo, si rimuove tale gruppo dal gruppo di accesso di cui è attualmente membro in base alla sua partecipazione nel sito:
  
- Amministrazione: rimuovere il gruppo dal gruppo di acceso degli amministratori del sito
    
- Collaborazione attiva: rimuovere il gruppo dal gruppo di acceso dei membri del sito
    
- Visualizzazione: rimuovere il gruppo dal gruppo di acceso dei visualizzatori del sito
    
Se si gestiscono gli account utente e i gruppi tramite Windows Server Active Directory, rimuovere i gruppi corretti dai gruppi di accesso appropriato utilizzando le normali procedure di gestione di utenti e gruppi di servizi di dominio Active Directory e attendere la sincronizzazione con l'abbonamento.
  
Se si gestiscono gli account utente e i gruppi tramite Office 365, è possibile utilizzare l'interfaccia di amministrazione di Microsoft 365 o PowerShell:
  
- Per l'interfaccia di amministrazione di Microsoft 365, accedere con un account utente a cui è stato assegnato l'amministratore dell'account utente o il ruolo di amministratore dell'azienda e utilizzare i gruppi per rimuovere i gruppi corretti dai gruppi di accesso appropriato.
    
- Per PowerShell, [connettersi prima con il modulo di Azure Active Directory PowerShell per Graph](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).    
Per rimuovere un gruppo da un gruppo di accesso con il relativo nome visualizzato, utilizzare il seguente blocco di comandi di PowerShell:
    
```powershell
$groupMemberName="<display name of the group to remove>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="create-a-documents-subfolder-with-custom-permissions"></a>Creare una sottocartella di documenti con autorizzazioni personalizzate

In alcuni casi, un sottoinsieme di utenti che lavorano all'interno del sito isolato necessitano di una posizione più privata per la collaborazione. Per i siti di SharePoint Online, è possibile creare una sottocartella nella cartella Documenti del sito e assegnare autorizzazioni personalizzate. Gli utenti privi di autorizzazioni non saranno in grado di visualizzare la sottocartella.
  
Per creare una sottocartella di documenti con autorizzazioni personalizzate, eseguire le operazioni seguenti:
  
1. Accedere a un account membro del gruppo di accesso Admins per il sito. Per informazioni, vedere [Dove accedere a Microsoft 365](https://support.office.com/article/e9eb7d51-5430-4929-91ab-6157c5a050b4).
    
2. Accedere al sito del team isolato e fare clic su **Documenti**.
    
3. Passare alla cartella dei documenti contenente la sottocartella con autorizzazioni personalizzate, creare la cartella e quindi aprirla.
    
4. Fare clic su **Condividi**.
    
5. Fare clic su **Condiviso con > Avanzate**.
    
6. Fare clic su **Interrompi ereditarietà autorizzazioni**, quindi su **OK**.
    
7. Fare clic su **Condividi**.
    
8. Fare clic su **Condiviso con > Avanzate**.
    
9. Fare clic su **Concedi autorizzazioni > Condiviso con > Avanzate**.
    
10. Nella pagina relativa alle autorizzazioni, fare clic su **\<Membri di <nome sito> nell'elenco**.
    
11. Nella pagina **\<Membri di <nome sito>**, selezionare la casella di controllo accanto al gruppo di accesso dei membri del sito, fare clic su **Azioni**, fare clic su **Rimuovi utenti dal gruppo** e infine su **OK**.
    
12. Per aggiungere membri specifici a questa sottocartella, fare clic su **Nuovo > Aggiungi utenti**.
    
13. Nella finestra di dialogo **Condividi**, digitare i nomi degli account utente che possono collaborare sui file nella sottocartella, quindi fare clic su **Condividi**.
    
14. Aggiornare la pagina Web per visualizzare i nuovi risultati.
    
15. In **Gruppi** nella barra di spostamento sinistra, fare clic sul gruppo **\<Visitatori di <nome sito>** e seguire i passaggi 11-14 per specificare il set di account utente in grado di visualizzare i file nella sottocartella (in base alle esigenze).
    
16. In **Gruppi** nella barra di spostamento sinistra, fare clic sul gruppo **\<Proprietari di <nome sito>** e seguire i passaggi 11-14 per specificare il set di account utente in grado di amministrare le autorizzazioni nella sottocartella (in base alle esigenze).
    
17. Chiudere la scheda **Utenti e gruppi** visualizzata nel browser.
    
## <a name="see-also"></a>Vedere anche

[Siti del team di SharePoint Online isolati](isolated-sharepoint-online-team-sites.md)
  
[Progettare un sito del team di SharePoint Online isolato](design-an-isolated-sharepoint-online-team-site.md)

[Distribuire un sito del team di SharePoint Online isolato](deploy-an-isolated-sharepoint-online-team-site.md)



