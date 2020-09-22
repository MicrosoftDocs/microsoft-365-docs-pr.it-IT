---
title: Concedere agli utenti l'accesso al Centro sicurezza e conformità
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
f1_keywords:
- ms.o365.cc.PermissionsHelp
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 2cfce2c8-20c5-47f9-afc4-24b059c1bd76
description: Gli utenti devono disporre delle autorizzazioni nel centro conformità di sicurezza & Microsoft 365 prima di poter gestire qualsiasi funzionalità di sicurezza o conformità.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5d586684d44545f7aea94c30f5474b1fe5fa4651
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202808"
---
# <a name="give-users-access-to-the-security--compliance-center"></a>Concedere agli utenti l'accesso al Centro sicurezza e conformità

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Gli utenti devono disporre delle autorizzazioni nel centro sicurezza & compliance prima di poter gestire qualsiasi funzionalità di sicurezza o conformità. In qualità di amministratore globale o membro del gruppo di ruoli OrganizationManagement nel centro sicurezza & conformità, è possibile concedere queste autorizzazioni agli utenti. Gli utenti potranno solo gestire le funzionalità di sicurezza o conformità per le quali è stato concesso loro l'accesso.

Per ulteriori informazioni sulle diverse autorizzazioni che è possibile assegnare agli utenti nel centro sicurezza & conformità, vedere [autorizzazioni nel centro sicurezza & conformità](permissions-in-the-security-and-compliance-center.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare

- Per completare la procedura descritta in questo articolo, è necessario essere un amministratore globale o un membro del gruppo di ruoli OrganizationManagement nel centro sicurezza & Compliance.

- I gruppi di ruoli per il Centro sicurezza & conformità potrebbero avere nomi simili ai gruppi di ruoli in Exchange Online, ma non sono gli stessi.

- Le appartenenze ai gruppi di ruoli non sono condivise tra Exchange Online e il Centro sicurezza & conformità.

- I partner di autorizzazione accesso delegato (DAP) con amministra per conto di (AOBO) le autorizzazioni non possono accedere al centro sicurezza & conformità.

## <a name="use-the-security--compliance-center-to-give-another-user-access-to-the-security--compliance-center"></a>Utilizzare il Centro sicurezza & conformità per consentire a un altro utente di accedere al centro sicurezza & conformità

1. Aprire il Centro sicurezza & conformità <https://protection.office.com> e quindi andare a **autorizzazioni**. Per passare direttamente alla scheda **autorizzazioni** , Apri <https://protection.office.com/permissions> .

2. Nell'elenco dei gruppi di ruoli, scegliere il gruppo di ruoli, quindi fare clic su **modifica** ![ icona modifica ](../../media/O365-MDM-CreatePolicy-EditIcon.gif) .

3. Nella pagina delle proprietà del gruppo di ruoli in **membri**fare clic su **Aggiungi** ![ icona ](../../media/ITPro-EAC-AddIcon.gif) e selezionare il nome dell'utente (o degli utenti) che si desidera aggiungere.

4. Dopo aver selezionato tutti gli utenti che si desidera aggiungere al gruppo di ruoli, fare clic su **Aggiungi \> ** e quindi su **OK**.

5. Al termine, scegliere **Salva**.

## <a name="use-security--compliance-center-powershell-to-give-another-user-access-to-the-security--compliance-center"></a>Utilizzare la sicurezza & Compliance Center PowerShell per concedere a un altro utente l'accesso al centro sicurezza & conformità

1. [Connettersi a PowerShell in Centro sicurezza e conformità](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).

2. Utilizzare la sintassi seguente:

   ```powershell
   Add-RoleGroupMember -Identity <RoleGroup> -Member <UserIdentity>

   - _Identity_ is the role group.
   - _Member_ is the user or universal security group (USG). You can specify only one member at a time.

   This example adds MatildaS to the Organization Management role group.

   ```PowerShell
   Add-RoleGroupMember -Identity "Organization Management" -Member MatildaS
   ```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Add-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/add-rolegroupmember)

### <a name="how-do-you-know-this-worked"></a>Come verificare se l'operazione ha avuto esito positivo

Per verificare di aver correttamente concesso l'accesso al centro sicurezza & Compliance, eseguire una delle operazioni seguenti:

- Nel centro sicurezza & conformità, accedere a **autorizzazioni** e selezionare il gruppo di ruoli. Nel riquadro a comparsa dettagli che si apre, verificare i membri del gruppo di ruoli. 

- In PowerShell Centro sicurezza & conformità, sostituire \<RoleGroupName\> con il nome del gruppo di ruolo ed eseguire il comando seguente:

  ```powershell
  Get-RoleGroupMember -Identity "<RoleGroupName>"
  ```

  Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Get-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroupMember).
