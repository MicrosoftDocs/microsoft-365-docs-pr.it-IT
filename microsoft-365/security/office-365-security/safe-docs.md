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
description: Informazioni sui documenti attendibili in Office 365 ATP.
ms.openlocfilehash: 40554365cf41ac37b9f9b8399b10dc8f6ab81f42
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "44617287"
---
# <a name="safe-documents-in-office-365-advanced-threat-protection"></a>Sicurezza documenti in Office 365 Advanced Threat Protection

Documenti attendibili è una funzionalità di Office 365 Advanced Threat Protection (Office 365 ATP) che utilizza [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) per analizzare i documenti e i file aperti in [visualizzazione protetta](https://support.office.com/article/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare

- Questa funzionalità è disponibile solo per gli utenti che dispongono della licenza di sicurezza Microsoft 365 E5 o Microsoft 365 E5.

- I documenti attendibili sono attualmente disponibili per l'anteprima pubblica, disponibili per gli utenti che fanno parte del [programma Office Insider](https://insider.office.com/en-us/join) sul ' canale mensile (mirato)' con office versione 2002 (12527,20092) o superiore. Questa funzionalità è disattivata per impostazione predefinita e dovrà essere abilitata dall'amministratore della sicurezza.

- Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Per connettersi a PowerShell di EOP autonomo, vedere [Connettersi a PowerShell per Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Prima di poter eseguire le procedure descritte in questo argomento, è necessario disporre delle autorizzazioni assegnate. Per abilitare e configurare documenti attendibili, è necessario essere membri dei gruppi di ruoli **Gestione organizzazione** o **amministratore sicurezza** . Per altre informazioni sui gruppi di ruoli nel Centro sicurezza e conformità, vedere [Autorizzazioni nel Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).

## <a name="how-does-microsoft-handle-your-data"></a>In che modo Microsoft gestisce i dati?

Per proteggersi, i documenti sicuri inviano i file al cloud di [protezione avanzata delle minacce di Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) per l'analisi.

- Informazioni dettagliate su come Microsoft Defender Advanced thread Protection gestisce i dati possono essere trovati [qui](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
- Oltre alle linee guida sopra riportate, i file inviati dai documenti attendibili non vengono conservati in Defender oltre il tempo necessario per l'analisi, che in genere è inferiore a 24 ore.

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a>Utilizzare il Centro sicurezza & conformità per configurare i documenti attendibili

1. Aprire il Centro sicurezza & Compliance all'indirizzo <https://protection.office.com> .

2. Accedere a criteri di **gestione delle minacce** per gli \> **Policy** \> **allegati sicuri ATP**.

3. Nella sezione **informazioni su come mantenere la sicurezza per la protezione di un file da aprire visualizzazione protetta esterna in applicazioni di Office** , configurare una delle seguenti impostazioni:

   - **Attiva documenti attendibili per i client di Office (i file verranno anche inviati a Microsoft Cloud per analisi approfondite)**

   - **Consenti agli utenti di fare clic su una visualizzazione protetta anche se i documenti sicuri identificano il file come dannoso**: si consiglia di non abilitare questa opzione.

4. Al termine, scegliere **Salva**.

![Pagina allegati sicuri ATP](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-documents"></a>Utilizzare Exchange Online PowerShell o standalone EOP PowerShell per configurare documenti sicuri

Utilizzare la sintassi seguente:

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true|$false> -AllowSafeDocsOpen <$true|$false>
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
