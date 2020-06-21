---
title: Attivazione di Office 365 ATP-SharePoint, OneDrive, & Teams
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 02/06/2019
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 07e76024-0c80-40dc-8c48-1dd0d0f863cb
ms.collection:
- M365-security-compliance
- SPO_Content
description: Informazioni su come abilitare ATP per SharePoint, OneDrive e teams, inclusa la procedura per impostare gli avvisi per i file rilevati.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 976911abe047be350ae6c64409cd6607ea75de7a
ms.sourcegitcommit: 7a59d83a8660c2344ebdb92e0ea0171c9c2d9498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/19/2020
ms.locfileid: "44811075"
---
# <a name="turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>Attivare ATP per SharePoint, OneDrive e Microsoft Teams

> [!IMPORTANT]
> Questo articolo è rivolto ai clienti aziendali di [Office 365 Advanced Threat Protection](office-365-atp.md). Se si è un utente di casa che cerca informazioni sui collegamenti sicuri in Outlook, vedere [Advanced Outlook.com Security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).

[Office 365 ATP per SharePoint, OneDrive e Microsoft teams](atp-for-spo-odb-and-teams.md) protegge l'organizzazione dalla condivisione involontaria di file dannosi. Quando viene rilevato un file dannoso, il file viene bloccato in modo che nessuno possa aprirlo, copiarlo, spostarlo o condividerlo fino a quando non vengono intraprese altre azioni da parte del team di sicurezza dell'organizzazione. Leggere questo articolo per abilitare ATP per SharePoint, OneDrive e teams, impostare gli avvisi per ricevere una notifica sui file rilevati e seguire i passaggi successivi.

Per definire (o modificare) i criteri ATP, è necessario essere assegnati a un ruolo appropriato. Alcuni esempi sono descritti nella tabella seguente:

|Ruolo|Dove/come assegnato|
|---------|---------|
|amministratore globale|La persona che si iscrive all'acquisto di Microsoft 365 è un amministratore globale per impostazione predefinita. Per ulteriori informazioni, vedere [informazioni sui ruoli di amministratore di Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) .|
|Amministratore della sicurezza|Interfaccia di amministrazione di Azure Active Directory ( [https://aad.portal.azure.com](https://aad.portal.azure.com) )|
|Gestione organizzazione di Exchange Online|Interfaccia di amministrazione di Exchange ( [https://outlook.office365.com/ecp](https://outlook.office365.com/ecp) ) <br>oppure <br>  Cmdlet di PowerShell (vedere [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell))|

## <a name="turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>Attivare ATP per SharePoint, OneDrive e Microsoft Teams

**Prima di iniziare questa procedura, verificare che la registrazione di controllo sia già attiva per l'ambiente Microsoft 365**. Questa operazione viene in genere fatta da una persona a cui è stato assegnato il ruolo registri di controllo in Exchange Online. Per altre informazioni, vedere [Attivare o disattivare la ricerca nel log di controllo](../../compliance/turn-audit-log-search-on-or-off.md).

1. Passare a [https://protection.office.com](https://protection.office.com) e accedere con l'account aziendale o dell'Istituto di istruzione.

2. Nel riquadro di spostamento a sinistra del Centro sicurezza & conformità, in **gestione minacce**scegliere **Policy** \> **allegati sicuri**per i criteri.

   ![Nel centro sicurezza & conformità scegliere criteri di gestione delle minacce \>](../../media/08849c91-f043-4cd1-a55e-d440c86442f2.png)

3. Selezionare **attiva ATP per SharePoint, OneDrive e Microsoft teams**.

   ![Abilitare Advanced Threat Protection per SharePoint Online, OneDrive for business e Microsoft Teams](../../media/48cfaace-59cc-4e60-bf86-05ff6b99bdbf.png)

4. Fare clic su **Salva**.

5. Rivedere (e, a seconda dei casi, modificare) i [criteri per gli allegati sicuri](set-up-atp-safe-attachments-policies.md) dell'organizzazione e i [criteri collegamenti sicuri](set-up-atp-safe-links-policies.md).

6. Consigliato In qualità di amministratore globale o amministratore di SharePoint Online, eseguire il cmdlet **[set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** con il parametro _DisallowInfectedFileDownload_ impostato su *true*.

   - L'impostazione del parametro su *true* blocca tutte le azioni (eccetto Delete) per i file rilevati. Gli utenti non possono aprire, spostare, copiare o condividere i file rilevati.

   - Se si imposta il parametro su *false* , vengono bloccate tutte le azioni ad eccezione di Delete e download. Gli utenti possono scegliere di accettare il rischio e scaricare un file rilevato.

7. Consentono fino a 30 minuti affinché le modifiche vengano estese a tutti i datacenter di Microsoft 365.

8. Consigliato Procedere alla configurazione degli avvisi per i file rilevati.

Per ulteriori informazioni sull'utilizzo di PowerShell con Microsoft 365, vedere [gestire microsoft 365 con PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell).

Per ulteriori informazioni sull'esperienza utente quando un file è stato rilevato come dannoso, vedere [cosa fare quando si trova un file dannoso in SharePoint Online, OneDrive o Microsoft teams](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2).

## <a name="set-up-alerts-for-detected-files"></a>Configurare gli avvisi per i file rilevati

Per ricevere una notifica quando un file in SharePoint Online, OneDrive for business o Microsoft teams è stato identificato come dannoso, è possibile impostare un avviso.

1. Nel [Centro sicurezza & conformità](https://protection.office.com), scegliere **avvisi** \> **Gestione avvisi**.

2. Scegliere **nuovi criteri di avviso**.

3. Specificare un nome per l'avviso. Ad esempio, è possibile digitare file dannosi nelle raccolte.

4. Digitare una descrizione per l'avviso. Ad esempio, è possibile digitare notifiche agli amministratori quando vengono rilevati file dannosi in SharePoint Online, OneDrive o Microsoft teams.

5. Nella sezione **Invia questo avviso quando...** eseguire le operazioni seguenti:

   a. Nell'elenco **attività** scegliere **rilevato malware nel file**.

   b. Lasciare vuoto il campo **Users** .

6. Nella sezione **Invia questo avviso a...** selezionare uno o più amministratori globali, amministratori della sicurezza o lettori di sicurezza che dovrebbero ricevere una notifica quando viene rilevato un file dannoso.

7. Fare clic su **Salva**.

Per ulteriori informazioni sugli avvisi, vedere [creare avvisi di attività nel centro sicurezza & Compliance](../../compliance/create-activity-alerts.md).

## <a name="next-steps"></a>Passaggi successivi

1. [Visualizzare informazioni sui file dannosi rilevati in SharePoint, OneDrive o Microsoft Teams](malicious-files-detected-in-spo-odb-or-teams.md)

2. [Gestire i messaggi e i file in quarantena come amministratore in Microsoft 365](manage-quarantined-messages-and-files.md)
