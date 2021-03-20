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
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MOE150
- MET150
ms.assetid: 2cfce2c8-20c5-47f9-afc4-24b059c1bd76
description: Gli utenti devono disporre delle autorizzazioni nel Centro sicurezza & e conformità di Microsoft 365 prima di poter gestire qualsiasi funzionalità di sicurezza o conformità.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6ab02773a19e1b5881858104097b0b03e4385b40
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907229"
---
# <a name="give-users-access-to-the-security--compliance-center"></a>Concedere agli utenti l'accesso al Centro sicurezza e conformità

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Gli utenti devono disporre delle autorizzazioni nel Centro sicurezza & conformità prima di poter gestire qualsiasi funzionalità di sicurezza o conformità. In quanto amministratore globale o membro del gruppo di ruoli OrganizationManagement nel Centro sicurezza & conformità, è possibile concedere queste autorizzazioni agli utenti. Gli utenti potranno solo gestire le funzionalità di sicurezza o conformità per le quali è stato concesso loro l'accesso.

Per ulteriori informazioni sulle diverse autorizzazioni che è possibile concedere agli utenti nel Centro sicurezza & conformità, vedere Autorizzazioni nel [Centro sicurezza & conformità.](permissions-in-the-security-and-compliance-center.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare

- Per completare i passaggi descritti in questo articolo, è necessario essere un amministratore globale o un membro del gruppo di ruoli OrganizationManagement nel Centro sicurezza & conformità.

- I gruppi di ruoli per il Centro sicurezza & conformità potrebbero avere nomi simili ai gruppi di ruoli in Exchange Online, ma non sono uguali.

- Le appartenenze ai gruppi di ruoli non vengono condivise tra Exchange Online e il Centro sicurezza & conformità.

- I partner con autorizzazioni di accesso delegato (DAP) con autorizzazioni Amministra per conto di (AOBO) non possono accedere al Centro sicurezza & conformità.

## <a name="use-the-security--compliance-center-to-give-another-user-access-to-the-security--compliance-center"></a>Usare il Centro sicurezza & conformità per concedere a un altro utente l'accesso al Centro sicurezza & conformità

1. Aprire il Centro sicurezza & conformità <https://protection.office.com> in e quindi passare a **Autorizzazioni**. Per passare direttamente alla **scheda Autorizzazioni,** aprire <https://protection.office.com/permissions> .

2. Nell'elenco dei gruppi di ruoli scegliere il gruppo di ruoli e quindi fare clic su **Modifica** ![ icona ](../../media/O365-MDM-CreatePolicy-EditIcon.gif) Modifica.

3. Nella pagina delle proprietà del gruppo di ruoli **in** Membri fare clic su Aggiungi Icona Aggiungi e selezionare il nome dell'utente (o degli ![ ](../../media/ITPro-EAC-AddIcon.gif) utenti) che si desidera aggiungere.

4. Dopo aver selezionato tutti gli utenti che si desidera aggiungere al gruppo di ruoli, fare clic su **aggiungi- \>** e quindi **su OK.**

5. Al termine, fare clic su **Salva**.

## <a name="use-security--compliance-center-powershell-to-give-another-user-access-to-the-security--compliance-center"></a>Usare PowerShell & Centro sicurezza e conformità per concedere a un altro utente l'accesso al Centro sicurezza & conformità

1. [Connettersi a PowerShell in Centro sicurezza e conformità](/powershell/exchange/connect-to-scc-powershell).

2. Usare la sintassi seguente:

   ```powershell
   Add-RoleGroupMember -Identity <RoleGroup> -Member <UserIdentity>

   - _Identity_ is the role group.
   - _Member_ is the user or universal security group (USG). You can specify only one member at a time.

   This example adds MatildaS to the Organization Management role group.

   ```PowerShell
   Add-RoleGroupMember -Identity "Organization Management" -Member MatildaS
   ```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Add-RoleGroupMember](https://docs.microsoft.com/powershell/module/exchange/add-rolegroupmember)

### <a name="how-do-you-know-this-worked"></a>Come verificare se l'operazione ha avuto esito positivo

Per verificare di aver concesso correttamente l'accesso al Centro sicurezza & conformità, eseguire una delle operazioni seguenti:

- Nel Centro sicurezza & conformità passare a **Autorizzazioni** e selezionare il gruppo di ruoli. Nel riquadro a comparsa dei dettagli che si apre, verificare i membri del gruppo di ruoli.

- In PowerShell & Centro sicurezza e conformità sostituire con il nome del gruppo di ruoli \<RoleGroupName\> ed eseguire il comando seguente:

  ```powershell
  Get-RoleGroupMember -Identity "<RoleGroupName>"
  ```

  Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Get-RoleGroupMember](/powershell/module/exchange/Get-RoleGroupMember).