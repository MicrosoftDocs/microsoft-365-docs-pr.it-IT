---
title: Sicurezza documenti in Microsoft Defender per Office 365
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: kshi
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Informazioni su Documenti sicuri in Microsoft 365 E5 o Microsoft 365 E5 Security.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a1dc6c5dc54acd73b68fcd6241a270d2abdcc5c1
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205676"
---
# <a name="safe-documents-in-microsoft-365-e5"></a>Sicurezza documenti in Microsoft 365 E5

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Microsoft Defender per Office 365 Piano 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Documenti sicuri è una funzionalità di Microsoft 365 E5 o Microsoft 365 E5 Security che utilizza [Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) per analizzare documenti e file aperti in Visualizzazione [protetta.](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare

- Documenti sicuri è disponibile solo per gli utenti con *licenze microsoft 365 E5* o *Microsoft 365 E5 Security.* Queste licenze non sono incluse nei piani di Microsoft Defender per Office 365.

- Documenti sicuri è supportato in Microsoft 365 Apps for enterprise (in precedenza noto come Office 365 ProPlus) versione 2004 o successiva.

- Aprire il Centro sicurezza e conformità in<https://protection.office.com>. Per passare direttamente alla pagina Allegati sicuri **ATP,** aprire <https://protection.office.com/safeattachmentv2> .

- Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell).

- Prima di eseguire le procedure descritte in questo articolo, occorre disporre delle autorizzazioni in **Exchange Online**:
  - Per configurare le impostazioni di Documenti sicuri, è necessario essere membri dei **gruppi di** ruoli Gestione organizzazione o Amministratore sicurezza. 
  - Per l'accesso in sola lettura alle impostazioni dei documenti sicuri, è necessario essere membri dei gruppi di ruoli **Lettore** globale o **Lettore** di sicurezza.

  Per altre informazioni, vedere [Autorizzazioni in Exchange Online](/exchange/permissions-exo/permissions-exo).

  > [!NOTE]
  >
  > - L'aggiunta di utenti al ruolo di Azure Active Directory corrispondente nell'interfaccia di amministrazione di Microsoft 365 fornisce agli utenti le autorizzazioni necessarie _e_ le autorizzazioni per altre funzionalità di Microsoft 365. Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](../../admin/add-users/about-admin-roles.md).
  >
  > - Anche il gruppo di ruoli di **Gestione organizzazione sola visualizzazione** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) offre inoltre l'accesso di sola lettura a tale funzionalità.

### <a name="how-does-microsoft-handle-your-data"></a>In che modo Microsoft gestisce i dati?

Per mantenere la protezione, Documenti sicuri invia i file al cloud [Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) per l'analisi. I dettagli su come Microsoft Defender for Endpoint gestisce i dati sono disponibili qui: [Microsoft Defender for Endpoint data storage and privacy](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy).

I file inviati da Documenti sicuri non vengono conservati in Defender oltre il tempo necessario per l'analisi (in genere, meno di 24 ore).

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a>Usare il Centro sicurezza & conformità per configurare Documenti sicuri

1. Nel Centro sicurezza & conformità passare a **Criteri** di gestione delle minacce Allegati sicuri ATP e quindi fare clic \>  \> su **Impostazioni globali.**

2. Nel **riquadro a comparsa** Impostazioni globali visualizzato configurare le impostazioni seguenti:

   - **Attivare Documenti sicuri per i client di Office**: spostare l'interruttore a destra per attivare la funzionalità: ![ Attiva/ ](../../media/scc-toggle-on.png) attiva.

   - **Consentire agli** utenti di fare clic su Visualizzazione protetta anche se Documenti sicuri identifica il file come dannoso: è consigliabile lasciare disattivata questa opzione (lasciare l'interruttore a sinistra: ![ Interruttore ](../../media/scc-toggle-off.png) disattivato).

   Al termine, scegliere **Salva**.

   ![Impostazioni documenti sicuri dopo aver selezionato Impostazioni globali nella pagina Allegati sicuri.](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-to-configure-safe-documents"></a>Utilizzare PowerShell di Exchange Online per configurare documenti sicuri

Usare la sintassi seguente:

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- Il _parametro EnableSafeDocs_ consente di abilitare o disabilitare Documenti sicuri per l'intera organizzazione.
- Il _parametro AllowSafeDocsOpen_ consente o impedisce agli utenti di uscire da Visualizzazione protetta, ovvero l'apertura del documento, se il documento è stato identificato come dannoso.

In questo esempio vengono abilitati i documenti sicuri per l'intera organizzazione e viene impedito agli utenti di aprire documenti identificati come dannosi da Visualizzazione protetta.

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-AtpPolicyForO365.](/powershell/module/exchange/set-atppolicyforo365)

### <a name="how-do-i-know-this-worked"></a>Come verificare se l'operazione ha avuto esito positivo?

Per verificare di aver abilitato e configurato Documenti sicuri, eseguire una delle operazioni seguenti:

- Nel Centro sicurezza & conformità passare  a Criteri di gestione delle minacce Allegati sicuri \>  \> **ATP,** fare  clic su Impostazioni globali e verificare l'opzione Attiva documenti sicuri per i client **di Office** e Consenti agli utenti di fare clic su Visualizzazione protetta anche se Documenti sicuri identifica il file come impostazioni dannose.

- Eseguire il comando seguente in PowerShell di Exchange Online e verificare i valori delle proprietà:

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```

- I file seguenti sono disponibili per testare la protezione dei documenti sicuri. Questi documenti sono simili al file EICAR.TXT per testare le soluzioni antimalware e antivirus. I file non sono dannosi, ma attiveranno la protezione dei documenti sicuri.

  - [SafeDocsDemo.docx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.docx)
  - [SafeDocsDemo.pptx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.pptx)
  - [SafeDocsDemo.xlsx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.xlsx)