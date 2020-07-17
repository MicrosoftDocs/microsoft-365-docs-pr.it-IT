---
title: Distribuire un sito del team di SharePoint Online isolato
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/30/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 3033614b-e23b-4f68-9701-f62525eafaab
description: Utilizzare questa guida alla distribuzione dettagliata per creare e configurare un sito del team di SharePoint Online isolato in Microsoft Office 365.
ms.openlocfilehash: 05fdbcfff792805708bfe0b8027e955d54a1ec6f
ms.sourcegitcommit: 2acd9ec5e9d150389975e854c7883efc186a9432
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755225"
---
# <a name="deploy-an-isolated-sharepoint-online-team-site"></a>Distribuire un sito del team di SharePoint Online isolato

 **Sintesi:** istruzioni dettagliate per distribuire un nuovo sito del team di SharePoint Online isolato.
  
In questo articolo viene fornita una guida dettagliata alla distribuzione per creare e configurare un sito del team di SharePoint Online isolato in Microsoft Office 365. Questa procedura presuppone l'utilizzo di tre gruppi di SharePoint predefiniti e dei livelli di autorizzazione corrispondenti, con un singolo gruppo di Azure Active Directory (AD) per ogni livello di accesso.
  
## <a name="phase-1-create-and-populate-the-team-site-access-groups"></a>Fase 1: creare e popolare i gruppi di accesso al sito del team

In questa fase, vengono creati tre gruppi di accesso basati su Azure AD per i tre gruppi di SharePoint predefiniti e vengono popolati con gli account utente appropriati.
  
> [!NOTE]
> La procedura seguente presuppone che tutti gli account utente necessari già esistano e siano dotati delle licenze appropriate. In caso contrario, aggiungerli e assegnare le licenze prima di procedere con il passaggio 1. 
  
### <a name="step-1-list-the-sharepoint-online-admins-for-the-site"></a>Passaggio 1: elencare gli amministratori di SharePoint Online per il sito

Determinare il set di account utente corrispondenti agli amministratori di SharePoint Online per il sito del team isolato.
  
Se si gestiscono gli account utente e i gruppi tramite Microsoft 365 e si desidera utilizzare Windows PowerShell, fare un elenco dei loro nomi dell'entità utente (UPN), ad esempio UPN: belindan@contoso.com.
  
### <a name="step-2-list-the-members-for-the-site"></a>Passaggio 2: elencare i membri del sito

Determinare il set di account utente corrispondenti ai membri del sito del team isolato, quelli che collaboreranno sulle risorse archiviate nel sito.
  
Se si gestiscono gli account utente e i gruppi tramite Microsoft 365 e si desidera utilizzare PowerShell, fare un elenco dei loro UPN. Se sono presenti molti membri del sito, è possibile archiviare l'elenco di UPN in un file di testo e aggiungerli con un singolo comando di PowerShell.
  
### <a name="step-3-list-the-viewers-for-the-site"></a>Passaggio 3: elencare i visualizzatori del sito

Determinare il set di account utente corrispondenti ai visualizzatori del sito del tam isolato, quelli che possono visualizzare le risorse archiviate nel sito ma non modificarle o collaborare direttamente sui contenuti.
  
Se si gestiscono gli account utente e i gruppi tramite Microsoft 365 e si desidera utilizzare PowerShell, fare un elenco dei loro UPN. Se sono presenti molti membri del sito, è possibile archiviare l'elenco di UPN in un file di testo e aggiungerli con un singolo comando di PowerShell.
  
I visualizzatori del sito potrebbero includere la direzione esecutiva, i consulenti legali o gli stakeholder interdipartimentali.
  
### <a name="step-4-create-the-three-access-groups-for-the-site-in-azure-ad"></a>Passaggio 4: creare i tre gruppi di accesso per il sito di Azure AD

È necessario creare i gruppi di accesso seguenti in Azure AD:
  
- Amministratori del sito (che contiene l'elenco creato al passaggio 1)
    
- Membri del sito (che contiene l'elenco creato al passaggio 2)
    
- Visualizzatori del sito (che contiene l'elenco creato al passaggio 3)
    
1. Nel browser, accedere al portale di Azure [https://portal.azure.com](https://portal.azure.com) e accedere con le credenziali di un account assegnato con l'amministratore di gestione utenti o con il ruolo Administrator dell'azienda.
    
2. Nel portale di Azure fare clic su **Azure Active Directory > Gruppi**.
    
3. Nel pannello **Gruppi - Tutti i gruppi** fare clic su **+ Nuovo gruppo**.
    
4. Nel **nuovo gruppo** Blade:
    
    - Selezionare **Sicurezza** in **Tipo di gruppo**.

    - Digitare il nome del gruppo in **nome**.

    - Digitare una descrizione del gruppo nella **Descrizione del gruppo**.

    - Selezionare **Assegnato** in **Tipo di appartenenza**.
    
5. Fare clic su **Crea** e quindi chiudere il pannello **Gruppo**.
    
6. Ripetere i passaggi 3-5 per i gruppi aggiuntivi.
    
> [!NOTE]
> È necessario utilizzare il portale di Azure per creare i gruppi in modo che dispongano delle funzionalità di Office abilitate. Se un sito di SharePoint Online isolato viene configurato in un secondo momento come sito estremamente riservato con un'etichetta di Azure Information Protection per crittografare i file e assegnare l'autorizzazione a gruppi specifici, è necessario che i gruppi consentiti siano stati creati con le funzionalità di Office abilitate. Non è possibile modificare l'impostazione delle caratteristiche di Office di un gruppo di Azure AD dopo che è stata creata. 
  
Ecco la configurazione risultante con i tre gruppi di accesso al sito.
  
![I tre gruppi di accesso per la distribuzione di un sito di SharePoint Online isolato.](../../media/c2557f61-478b-4494-95e9-d79fe5909e8b.png)
  
### <a name="step-5-add-the-user-accounts-to-the-access-groups"></a>Passaggio 5. Aggiungere gli account utente ai gruppi di accesso

In questo passaggio, eseguire la procedura riportata di seguito:
  
1. Aggiungere l'elenco di utenti creato nel passaggio 1 al gruppo di accesso degli amministratori del sito
    
2. Aggiungere l'elenco di utenti creato nel passaggio 2 al gruppo di accesso dei membri del sito
    
3. Aggiungere l'elenco di utenti creato nel passaggio 3 al gruppo di accesso dei visualizzatori del sito
    
Se si gestiscono gli account utente e i gruppi tramite servizi di dominio Active Directory, aggiungere gli utenti ai gruppi di accesso appropriato utilizzando le normali procedure di gestione di utenti e gruppi di AD DS e attendere la sincronizzazione con l'abbonamento a Microsoft 365.
  
Se si gestiscono gli account utente e i gruppi tramite Office 365, è possibile utilizzare l'interfaccia di amministrazione di Microsoft 365 o PowerShell. Se si dispone di nomi di gruppo duplicati per uno qualsiasi dei gruppi di accesso, è consigliabile utilizzare l'interfaccia di amministrazione di Microsoft 365.
  
Per l'interfaccia di amministrazione di Microsoft 365, accedere con un account utente a cui è stato assegnato l'amministratore dell'account utente o il ruolo di amministratore dell'azienda e utilizzare i gruppi per aggiungere gli account utente e i gruppi corretti ai gruppi di accesso appropriato.
  
Per PowerShell, [connettersi prima con il modulo di Azure Active Directory PowerShell per Graph](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).
  
Successivamente, utilizzare il seguente blocco di comandi per aggiungere un singolo account utente a un gruppo di accesso:
  
```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```
Se gli UPN degli account utente per uno dei gruppi di accesso è archiviato in un file di testo, è possibile utilizzare il seguente blocco di comandi PowerShell per aggiungerli tutti contemporaneamente:
  
```powershell
$grpName="<display name of the access group>"
$fileName="<path and name of the file containing the list of account UPNs>"
$grpID=(Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
Get-Content $fileName | ForEach { $userUPN=$_; Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID $grpID }
```

Per PowerShell, utilizzare il seguente blocco di comandi per aggiungere un singolo gruppo a un gruppo di accesso:
  
```powershell
$nestedGrpName="<display name of the group to add to the access group>"
$grpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $nestedGrpName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID

```

Dovrebbero essere visualizzati i seguenti risultati:
  
- Il gruppo di Azure AD degli amministratori del sito contiene gli account utente o i gruppi di amministratori del sito.
    
- Il gruppo di Azure AD dei membri del sito contiene gli account utente o i gruppi di membri del sito.
    
- Il gruppo di Azure AD dei visualizzatori del sito contiene gli account utente o i gruppi che possono visualizzare solo il contenuto del sito.
    
Convalidare l'elenco dei membri del gruppo di ogni gruppo di accesso con l'interfaccia di amministrazione di Microsoft 365 o con il seguente blocco di comandi di PowerShell:
  
```powershell
$grpName="<display name of the access group>"
Get-AzureADGroupMember -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID | Sort UserPrincipalName | Select UserPrincipalName,DisplayName,UserType
```

Di seguito è configurata la configurazione risultante con i tre gruppi di accesso al sito popolati con account utente o gruppi.
  
![I tre gruppi di accesso popolati con gli account utente.](../../media/2320107c-dad6-4c8f-94e5-f6427c125e71.png)
  
## <a name="phase-2-create-and-configure-the-isolated-team-site"></a>Fase 2: creare e configurare il sito del team isolato

In questa fase, viene creato il sito di SharePoint Online isolato e vengono configurate le autorizzazioni per i livelli di autorizzazione di SharePoint Online predefiniti affinché vengano utilizzati i nuovi gruppi di accesso basati su Azure AD. Per impostazione predefinita, i nuovi siti del team includono un gruppo di Microsoft 365 e altre risorse correlate, ma in questo caso verrà creato un sito del team senza un gruppo di Microsoft 365. In questo modo è possibile gestire le autorizzazioni completamente tramite SharePoint.
  
Creare innanzitutto il sito del team di SharePoint Online seguendo questa procedura.
  
1. Accedere all'interfaccia di amministrazione di Microsoft 365 con un account che verrà utilizzato anche per amministrare il sito del team di SharePoint Online (un amministratore di SharePoint Online). Per informazioni, vedere [Dove accedere a Office 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).

2. Nell'interfaccia di amministrazione di Microsoft 365, in interfaccia di **Amministrazione**, fare clic su **SharePoint**.

3. Nell'interfaccia di amministrazione di SharePoint espandere **siti** e fare clic su **siti attivi**.

4. Fare clic su **Crea**e quindi scegliere **altre opzioni**.

5. Nell'elenco **scegliere un modello** scegliere sito del **Team**.
   
6. In **nome sito**Digitare un nome per il sito del team. 
    
7. In **amministratore principale**, digitare l'account con cui si è connessi.
 
8. Fare clic su **Fine**.
    
Successivamente, dal nuovo sito del team di SharePoint Online configurare le autorizzazioni.
  
1. Nella barra degli strumenti fare clic sull'icona delle impostazioni, quindi su **Autorizzazioni sito**.

2. In **condivisione siti**fare clic su **cambia come possono essere condivisi i membri**.

3. Scegliere gli **unici proprietari di siti possono condividere file, cartelle e il sito**.

4. Impostare **Consenti le richieste di accesso** su **disattivato**.

5. Fare clic su **Salva**.
    
6. Nel riquadro **autorizzazioni** , fare clic su **Impostazioni avanzate autorizzazioni**.
    
7. Nella scheda **autorizzazioni** del browser fare clic su ** \<site name> membri** nell'elenco.
    
8. In **Utenti e gruppi** fare clic su **Nuovo**.
    
9. Nella finestra di dialogo **Condividi**, digitare il nome del gruppo di Azure AD dei membri del sito di accesso, selezionarlo e fare clic su **Condividi**.
    
10. Fare clic sul pulsante Indietro del browser.
    
11. Fare clic su ** \<site name> proprietari** nell'elenco.
    
12. In **Utenti e gruppi** fare clic su **Nuovo**.
    
13. Nella finestra di dialogo **Condividi**, digitare il nome del gruppo di accesso degli amministratori del sito, selezionarlo e fare clic su **Condividi**.
    
14. Fare clic sul pulsante Indietro del browser.
    
15. Fare clic su ** \<site name> visitatori** nell'elenco.
    
16. In **Utenti e gruppi** fare clic su **Nuovo**.
    
17. Nella finestra di dialogo **Condividi**, digitare il nome del gruppo di Azure AD dei visualizzatori del sito di accesso, selezionarlo e fare clic su **Condividi**.
    
18. Chiudere la scheda **Autorizzazioni** del browser.
    
I risultati di queste impostazioni delle autorizzazioni sono i seguenti:
  
- Il gruppo ** \<site name> proprietari** di SharePoint contiene il gruppo di accesso degli amministratori del sito, in cui tutti i membri hanno il livello di autorizzazione **controllo completo** .
    
- Il gruppo ** \<site name> membri** di SharePoint contiene il gruppo di accesso dei membri del sito, in cui tutti i membri hanno il livello di autorizzazione **modifica** .
    
- Il gruppo ** \<site name> visitatori** di SharePoint contiene il gruppo di accesso dei visualizzatori del sito, in cui tutti i membri hanno il livello di autorizzazione **lettura** .
    
- I membri non hanno la possibilità di invitare altri membri o di richiedere l'accesso per utenti non membri.
    
Ecco la configurazione risultante con i tre gruppi di SharePoint per il sito configurati per l'utilizzo dei tre gruppi di accesso, che sono popolati con gli account utente o i gruppi di Azure AD.
  
![La configurazione finale del sito di SharePoint Online isolato con i gruppi di accesso e gli account utente.](../../media/e7618971-06ab-447b-90ff-d8be3790fe63.png)
  
I membri del sito, tramite l'appartenenza a uno dei gruppi di accesso, possono ora collaborare utilizzando le risorse del sito.
  
## <a name="next-step"></a>Passaggio successivo

Se è necessario modificare l'appartenenza al gruppo di accesso del sito o creare una cartella di documenti con autorizzazioni personalizzate, vedere [Manage an isolated SharePoint Online team site](manage-an-isolated-sharepoint-online-team-site.md).
  
## <a name="see-also"></a>Vedere anche

[Siti del team di SharePoint Online isolati](isolated-sharepoint-online-team-sites.md)
  
[Progettare un sito del team di SharePoint Online isolato](design-an-isolated-sharepoint-online-team-site.md)
  
[Gestire un sito del team di SharePoint Online isolato](manage-an-isolated-sharepoint-online-team-site.md)
  



