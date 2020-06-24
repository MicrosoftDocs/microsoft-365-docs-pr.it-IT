---
title: Sicurezza documenti di Office 365 ATP
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: kshi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Informazioni sui documenti attendibili in Microsoft 365 E5 o Microsoft 365 E5 Security.
ms.openlocfilehash: c574e28a01dc961d898638184afe9ece90e31133
ms.sourcegitcommit: aa7f7350d1342ff9713bb840b2cc96d1a4234ef4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/22/2020
ms.locfileid: "44835352"
---
# <a name="safe-documents-in-microsoft-365-e5"></a>Documenti attendibili in Microsoft 365 E5

Documenti attendibili è una funzionalità di sicurezza di Microsoft 365 E5 o Microsoft 365 E5 che utilizza [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) per analizzare documenti e file aperti in [visualizzazione protetta](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare?

- I documenti attendibili sono ora generalmente disponibili per gli utenti con Office versione 2004 (12730. x) o versioni successive. Questa funzionalità è disattivata per impostazione predefinita e dovrà essere abilitata dall'amministratore della sicurezza.

- Questa funzionalità è disponibile solo per gli utenti che dispongono della licenza di sicurezza *microsoft 365 E5* o *Microsoft 365 E5* (non inclusa nei piani di Office 365 ATP).

- Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Per connettersi a PowerShell di EOP autonomo, vedere [Connettersi a PowerShell per Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Prima di poter eseguire le procedure descritte in questo argomento, è necessario disporre delle autorizzazioni assegnate. Per abilitare e configurare documenti attendibili, è necessario essere membri dei gruppi di ruoli **Gestione organizzazione** o **amministratore sicurezza** . Per altre informazioni sui gruppi di ruoli nel Centro sicurezza e conformità, vedere [Autorizzazioni nel Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).

## <a name="how-does-microsoft-handle-your-data"></a>In che modo Microsoft gestisce i dati?

Per proteggersi, i documenti sicuri inviano i file al cloud di [protezione avanzata delle minacce di Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) per l'analisi.

- Informazioni dettagliate su come Microsoft Defender Advanced Threat Protection gestisce i dati possono essere trovati [qui](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
- Oltre alle linee guida sopra riportate, i file inviati dai documenti attendibili non vengono conservati in Defender oltre il tempo necessario per l'analisi, che in genere è inferiore a 24 ore.

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a>Utilizzare il Centro sicurezza & conformità per configurare i documenti attendibili

1. Aprire il Centro sicurezza & Compliance all'indirizzo <https://protection.office.com> .

2. Accedere a criteri di **gestione delle minacce** per gli \> **Policy** \> **allegati sicuri ATP**.

3. Nella sezione **informazioni su come mantenere la sicurezza per la protezione di un file da aprire visualizzazione protetta esterna in applicazioni di Office** , configurare una delle seguenti impostazioni:

   - **Attivazione di documenti attendibili per i client di Office**

   - **Consenti agli utenti di fare clic su una visualizzazione protetta anche se i documenti sicuri identificano il file come dannoso**: si consiglia di non abilitare questa opzione.

4. Al termine, scegliere **Salva**.

![Pagina allegati sicuri ATP](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-documents"></a>Utilizzare Exchange Online PowerShell o standalone EOP PowerShell per configurare documenti sicuri

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

- Nel centro sicurezza & conformità andare al criterio di **gestione delle minacce** per gli \> **Policy** \> **allegati sicuri di ATP**e verificare che le selezioni nelle **persone di supporto siano sicure quando si considera attendibile un file per aprire la visualizzazione protetta esterna nella sezione applicazioni di Office** .

- Eseguire il seguente comando in PowerShell di Exchange Online e verificare i valori delle proprietà:

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```
