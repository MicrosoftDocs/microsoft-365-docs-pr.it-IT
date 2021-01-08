---
title: Preparare un dominio non instradabile per la sincronizzazione della directory
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365E_SetupDirSyncLocalDir
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: e7968303-c234-46c4-b8b0-b5c93c6d57a7
description: Informazioni su cosa fare se si dispone di un dominio non instradabile associato agli account utente locali prima di sincronizzarlo con il tenant Microsoft 365.
ms.openlocfilehash: dcd941bbae159afeb0cf6ef4f5acbaf409966295
ms.sourcegitcommit: ec293978e951b09903b79e6642aa587824935e0c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2021
ms.locfileid: "49780333"
---
# <a name="prepare-a-non-routable-domain-for-directory-synchronization"></a>Preparare un dominio non instradabile per la sincronizzazione della directory

Quando si sincronizza la directory locale con Microsoft 365, è necessario disporre di un dominio verificato in Azure Active Directory (Azure AD). Solo i nomi dell'entità utente (UPN) associati al dominio di servizi di dominio Active Directory locale (AD DS) sono sincronizzati. Tuttavia, tutti gli UPN che contengono un dominio non instradabile, ad esempio ". local" (example: billa@contoso. local), verranno sincronizzati con un dominio. onmicrosoft.com (ad esempio: billa@contoso.onmicrosoft.com). 

Se attualmente si utilizza un dominio ". local" per gli account utente in servizi di dominio Active Directory, si consiglia di modificarli in modo da utilizzare un domini verificati, ad esempio billa@contoso.com, per sincronizzarlo correttamente con il dominio Microsoft 365.
  
## <a name="what-if-i-only-have-a-local-on-premises-domain"></a>Che cosa succede se si dispone solo di un dominio locale ". local"?

Si utilizza Azure AD Connect per sincronizzare i servizi di dominio Active Directory con il tenant di Azure AD del tenant Microsoft 365. Per ulteriori informazioni, vedere [integrazione delle identità locali con Azure ad](https://docs.microsoft.com/azure/architecture/reference-architectures/identity/azure-ad).
  
Azure AD Connect sincronizza l'UPN e la password degli utenti in modo che gli utenti possano accedere con le stesse credenziali che utilizzano in locale. Tuttavia, Azure AD Connect sincronizza solo gli utenti nei domini che sono stati verificati da Microsoft 365. Questo significa che il dominio è stato verificato anche da Azure AD, in quanto le identità di Microsoft 365 sono gestite da Azure AD. In altre parole, il dominio deve essere un dominio Internet valido (ad esempio,. com,. org, .NET,. US). Se il dominio Active Directory interno di AD DS utilizza solo un campo non instradabile (ad esempio, ". local"), questo non può corrispondere al dominio verificato che si ha per il tenant di Microsoft 365. È possibile risolvere il problema modificando il dominio principale in un servizio Active Directory locale oppure aggiungendo uno o più suffissi UPN.
  
### <a name="change-your-primary-domain"></a>Modificare il dominio principale

Modificare il dominio principale in un dominio verificato in Microsoft 365, ad esempio contoso.com. Ogni utente con il dominio contoso. local viene quindi aggiornato a contoso.com. Si tratta di un processo molto coinvolto, tuttavia, e una soluzione più semplice è descritta nella sezione seguente.
  
### <a name="add-upn-suffixes-and-update-your-users-to-them"></a>Aggiungere suffissi UPN e aggiornare gli utenti

È possibile risolvere il problema ". local" registrando nuovi suffissi UPN o suffissi in servizi di dominio Active Directory in modo che corrispondano a quelli che sono stati verificati in Microsoft 365. Dopo aver registrato il nuovo suffisso, aggiornare l'utente UPN per sostituire ". local" con il nuovo nome di dominio, ad esempio, in modo che un account utente sia simile a billa@contoso.com.
  
Dopo aver aggiornato l'UPN per l'utilizzo del dominio verificato, si è pronti per sincronizzare AD DS locale con Microsoft 365.
  
#### <a name="step-1-add-the-new-upn-suffix"></a>Passaggio 1: aggiungere il nuovo suffisso UPN * *
  
1. Nel controller di dominio ad DS, in Server Manager scegliere **gli strumenti** \> **domini e trust di Active Directory**.
    
    **In alternativa, se non si dispone di Windows Server 2012**
    
    Premere il **tasto Windows + R** per aprire la finestra di dialogo **Esegui** e quindi digitare Domain. msc e quindi fare clic su **OK**.
    
    ![Scegliere domini e trust di Active Directory.](../media/46b6e007-9741-44af-8517-6f682e0ac974.png)
  
2. Nella finestra **domini e trust di Active Directory** fare clic con il pulsante destro del mouse su **domini e trust di Active Directory** e quindi scegliere **proprietà**.
    
    ![Fare clic con il pulsante destro del mouse su domini e trust di Active Directory e scegliere Proprietà](../media/39d20812-ffb5-4ba9-8d7b-477377ac360d.png)
  
3. Nella scheda **suffissi** UPN, nella casella **suffissi UPN alternativi** , digitare il nuovo suffisso UPN o suffissi, quindi fare clic su **Aggiungi** \> **applica**.
    
    ![Aggiungere un nuovo suffisso UPN](../media/a4aaf919-7adf-469a-b93f-83ef284c0915.PNG)
  
    Scegliere **OK** al termine dell'aggiunta di suffissi. 
    
 #### <a name="step-2-change-the-upn-suffix-for-existing-users"></a>Passaggio 2: modificare il suffisso UPN per gli utenti esistenti
  
1. Nel controller di dominio ad DS, in Server Manager scegliere **strumenti** \> **e utenti di Active Directory**.
    
    **In alternativa, se non si dispone di Windows Server 2012**
    
    Premere il **tasto Windows + R** per aprire la finestra di dialogo **Esegui** e quindi digitare dsa. msc e quindi fare clic su **OK** .
    
2. Selezionare un utente, fare clic con il pulsante destro del mouse e quindi scegliere **Proprietà**.
    
3. Nell'elenco a discesa suffisso UPN della scheda **account** scegliere il nuovo suffisso UPN e quindi fare clic su **OK**.
    
    ![Aggiungere un nuovo suffisso UPN per un utente](../media/54876751-49f0-48cc-b864-2623c4835563.png)
  
4. Completare questa procedura per ogni utente.
    
   
### <a name="use-powershell-to-change-the-upn-suffix-for-all-of-your-users"></a>Utilizzo di PowerShell per modificare il suffisso UPN per tutti gli utenti

Se si dispone di un sacco di account utente da aggiornare, è più facile usare PowerShell. Nell'esempio seguente vengono utilizzati i cmdlet [Get-ADUser](https://go.microsoft.com/fwlink/p/?LinkId=624312) e [set-aduser](https://go.microsoft.com/fwlink/p/?LinkId=624313) per modificare tutti i suffissi contoso. local in contoso.com in servizi di dominio Active Directory. 

Ad esempio, è possibile eseguire i seguenti comandi di PowerShell per aggiornare tutti i suffissi contoso. local a contoso.com:
    
  ```powershell
  $LocalUsers = Get-ADUser -Filter "UserPrincipalName -like '*contoso.local'" -Properties userPrincipalName -ResultSetSize $null
  $LocalUsers | foreach {$newUpn = $_.UserPrincipalName.Replace("@contoso.local","@contoso.com"); $_ | Set-ADUser -UserPrincipalName $newUpn}
  ```

Per ulteriori informazioni sull'utilizzo di Windows PowerShell in servizi di dominio Active Directory, vedere il [modulo di Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=624314) . 

