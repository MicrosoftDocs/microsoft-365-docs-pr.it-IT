---
title: Sicurezza documenti di Office 365 ATP
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: kshi
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Informazioni sui documenti attendibili in Microsoft 365 E5 o Microsoft 365 E5 Security.
ms.openlocfilehash: d2220bb088ddf6e739b79212c3c1f7f0ac7bd865
ms.sourcegitcommit: dcbcd5ef278949c777059b0aa6db072e821f72dd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/21/2020
ms.locfileid: "48173297"
---
# <a name="safe-documents-in-microsoft-365-e5"></a>Documenti attendibili in Microsoft 365 E5

Documenti attendibili è una funzionalità di sicurezza di Microsoft 365 E5 o Microsoft 365 E5 che utilizza [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) per analizzare documenti e file aperti in [visualizzazione protetta](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare

- I documenti attendibili sono disponibili solo per gli utenti con licenze di sicurezza *microsoft 365 E5* o *Microsoft 365 E5* . Queste licenze non sono incluse nei piani di Office 365 Advanced Threat Protection (ATP).

- Aprire il Centro sicurezza e conformità in <https://protection.office.com>. Per passare direttamente alla pagina degli **allegati sicuri di ATP** , Apri <https://protection.office.com/safeattachmentv2> .

- Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

- Prima di poter eseguire le procedure descritte in questo argomento, è necessario disporre delle autorizzazioni assegnate. Per abilitare e configurare documenti attendibili, è necessario essere membri dei gruppi di ruoli **Gestione organizzazione** o **amministratore sicurezza** . Per altre informazioni sui gruppi di ruoli nel Centro sicurezza e conformità, vedere [Autorizzazioni nel Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).

### <a name="how-does-microsoft-handle-your-data"></a>In che modo Microsoft gestisce i dati?

Per proteggersi, i documenti sicuri inviano i file al cloud di [protezione avanzata delle minacce di Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) per l'analisi. Informazioni dettagliate su come Microsoft Defender ATP gestisce i dati possono essere reperiti qui: [Microsoft Defender ATP data storage and privacy](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).

I file inviati dai documenti attendibili non vengono conservati in Defender oltre il tempo necessario per l'analisi (in genere, meno di 24 ore).

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a>Utilizzare il Centro sicurezza & conformità per configurare i documenti attendibili

1. Nel centro sicurezza & conformità, accedere a criteri di **gestione delle minacce** per gli \> **Policy** \> **allegati sicuri ATP**e quindi fare clic su **Impostazioni globali**.

2. Nelle **Impostazioni globali** volare che viene visualizzato, configurare le seguenti impostazioni:

   - **Attivare documenti attendibili per i client di Office**: spostare l'interruttore verso destra per attivare la caratteristica: ![ Toggle on ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) .

   - **Consenti agli utenti di fare clic su una visualizzazione protetta anche se i documenti sicuri identificano il file come dannoso**: si consiglia di lasciare questa opzione disattivata (lasciare l'interruttore a sinistra: disattivazione ![ ](../../media/scc-toggle-off.png) ).

   Al termine, scegliere **Salva**.

   ![Impostazioni dei documenti attendibili dopo aver selezionato le impostazioni globali nella pagina allegati sicuri di ATP.](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-to-configure-safe-documents"></a>Utilizzo di PowerShell di Exchange Online per configurare documenti sicuri

Utilizzare la sintassi seguente:

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- Il parametro _EnableSafeDocs_ consente di abilitare o disabilitare i documenti attendibili per l'intera organizzazione.
- Il parametro _AllowSafeDocsOpen_ consente o impedisce agli utenti di lasciare la visualizzazione protetta, ovvero l'apertura del documento, se il documento è stato identificato come dannoso.

In questo esempio vengono abilitati i documenti attendibili per l'intera organizzazione e viene impedito agli utenti di aprire documenti identificati come dannosi dalla visualizzazione protetta.

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).

### <a name="how-do-i-know-this-worked"></a>Come verificare se l'operazione ha avuto esito positivo?

Per verificare di aver abilitato e configurato documenti attendibili, eseguire una delle operazioni seguenti:

- Nel centro sicurezza & conformità, accedere a criteri di **gestione delle minacce** per gli \> **Policy** \> **allegati sicuri ATP**, fare clic su **Impostazioni globali**e verificare l' **attivazione dei documenti attendibili per i client di Office** e **consentire agli utenti di fare clic su tramite visualizzazione protetta anche se i documenti sicuri identificano il file come impostazioni dannose** .

- Eseguire il seguente comando in PowerShell di Exchange Online e verificare i valori delle proprietà:

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```

- I file seguenti sono disponibili per testare la protezione dei documenti attendibili. Questi documenti sono simili al file EICAR.TXT per testare le soluzioni anti-malware e antivirus. I file non sono nocivi, ma attivano la protezione dei documenti attendibili.

  - [SafeDocsDemo.docx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.docx)
  - [SafeDocsDemo.pptx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.pptx)
  - [SafeDocsDemo.xlsx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.xlsx)
