---
title: Concedere agli utenti l'accesso al Centro sicurezza e conformità
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: article
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
ms.openlocfilehash: bfded9d3f75f57eca1097fec6f18dc55410b65fb
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "44616975"
---
# <a name="give-users-access-to-the-security--compliance-center"></a>Concedere agli utenti l'accesso al Centro sicurezza e conformità

Gli utenti devono disporre delle autorizzazioni nel centro sicurezza & compliance prima di poter gestire qualsiasi funzionalità di sicurezza o conformità. In qualità di amministratore globale o membro del gruppo di ruoli OrganizationManagement nel centro sicurezza & conformità, è possibile concedere queste autorizzazioni agli utenti. Gli utenti potranno solo gestire le funzionalità di sicurezza o conformità per le quali è stato concesso loro l'accesso.

Per ulteriori informazioni sulle diverse autorizzazioni che è possibile assegnare agli utenti nel centro sicurezza & conformità, vedere [autorizzazioni nel centro sicurezza & conformità](permissions-in-the-security-and-compliance-center.md).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare

- Per completare la procedura descritta in questo articolo, è necessario essere un amministratore globale o un membro del gruppo di ruoli OrganizationManagement nel centro sicurezza & Compliance.

- I gruppi di ruoli per il Centro sicurezza & conformità potrebbero avere nomi simili ai gruppi di ruoli in Exchange Online, ma non sono gli stessi.

- Le appartenenze ai gruppi di ruoli non sono condivise tra Exchange Online e il Centro sicurezza & conformità.

- I partner di autorizzazione accesso delegato (DAP) con amministra per conto di (AOBO) le autorizzazioni non possono accedere al centro sicurezza & conformità.

## <a name="use-the-admin-center-to-give-another-user-access-to-the-security--compliance-center"></a>Utilizzare l'interfaccia di amministrazione per concedere a un altro utente l'accesso al centro sicurezza & conformità

1. [Accedere e passare all'interfaccia di amministrazione](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center).

2. Nell'interfaccia di amministrazione di Microsoft 365 aprire interfaccia di **Amministrazione** e quindi fare clic su **sicurezza & conformità**.

3. Nel centro sicurezza & conformità, accedere a **autorizzazioni**.

4. Nell'elenco scegliere il gruppo di ruoli a cui si desidera aggiungere l'utente e fare clic su **modifica** ![ icona modifica ](../../media/O365-MDM-CreatePolicy-EditIcon.gif) .

5. Nella pagina delle proprietà del gruppo di ruoli in **membri**fare clic su **Aggiungi** ![ icona ](../../media/ITPro-EAC-AddIcon.gif) e selezionare il nome dell'utente (o degli utenti) che si desidera aggiungere.

6. Dopo aver selezionato tutti gli utenti che si desidera aggiungere al gruppo di ruoli, fare clic su **Aggiungi \> ** e quindi su **OK**.

7. Fare clic su **Salva** per salvare le modifiche al gruppo di ruoli.

### <a name="how-do-you-know-this-worked"></a>Come verificare se l'operazione ha avuto esito positivo?

1. Nel centro sicurezza & conformità, accedere a **autorizzazioni**.

2. Nell'elenco, selezionare il gruppo di ruoli per visualizzare i membri.

3. A destra, nei dettagli del gruppo di ruoli, è possibile visualizzare i membri del gruppo di ruoli.

## <a name="use-powershell-to-give-another-user-access-to-the-security--compliance-center"></a>Utilizzo di PowerShell per consentire a un altro utente di accedere al centro sicurezza & Compliance

1. [Connettersi a PowerShell in Centro sicurezza e conformità](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).

2. Usa il comando **Add-RoleGroupMember** per aggiungere un utente al ruolo Gestione organizzazione, come mostrato nell'esempio seguente.

   ```PowerShell
   Add-RoleGroupMember -Identity "Organization Management" -Member MatildaS
   ```

   **Parametri**:

   - _Identity_ è il gruppo di ruoli a cui aggiungere un membro.

   - _Member_ è la cassetta postale, il gruppo di protezione universale (USG) o il computer da aggiungere al gruppo di ruoli. Puoi specificare solo un membro per volta.

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Add-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Add-RoleGroupMember).

### <a name="how-do-you-know-this-worked"></a>Come verificare se l'operazione ha avuto esito positivo

Per verificare di aver concesso agli utenti l'accesso al centro sicurezza & conformità, utilizzare il cmdlet **Get-RoleGroupMember** per visualizzare i membri nel gruppo di ruoli Gestione organizzazione, come illustrato nell'esempio seguente.

```PowerShell
Get-RoleGroupMember -Identity "Organization Management"
```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Get-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/Get-RoleGroupMember).
