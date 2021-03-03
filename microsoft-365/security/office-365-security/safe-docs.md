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
ms.openlocfilehash: 75dfa9e5687a4c4b561067190e7ce338074b2f66
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/03/2021
ms.locfileid: "50407421"
---
# <a name="safe-documents-in-microsoft-365-e5"></a>Sicurezza documenti in Microsoft 365 E5

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Microsoft Defender per Office 365 Piano 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Documenti sicuri è una funzionalità di Microsoft 365 E5 o Microsoft 365 E5 Security che usa [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) per analizzare documenti e file aperti in Visualizzazione [protetta.](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare?

- Documenti sicuri è disponibile solo per gli utenti con licenze Di sicurezza di *Microsoft 365 E5* o *Microsoft 365 E5.* Queste licenze non sono incluse nei piani di Microsoft Defender per Office 365.

- Documenti sicuri è supportato in Microsoft 365 Apps for enterprise (in precedenza noto come Office 365 ProPlus) versione 2004 o successiva.

- Aprire il Centro sicurezza e conformità in <https://protection.office.com>. Per passare direttamente alla pagina **Allegati sicuri di ATP,** aprire <https://protection.office.com/safeattachmentv2> .

- Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

- Per eseguire le procedure descritte in questo articolo, è necessario disporre delle autorizzazioni in **Exchange Online:**
  - Per configurare le impostazioni di Documenti sicuri, è necessario essere membri dei gruppi di ruoli **Gestione** organizzazione o **Amministratore** sicurezza.
  - Per l'accesso in sola lettura alle impostazioni di  Documenti sicuri, è necessario essere membri dei gruppi di ruoli Lettore globale o Lettore **di** sicurezza.

  Per ulteriori informazioni, vedere [Autorizzazioni in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo).

  > [!NOTE]
  >
  > - L'aggiunta di utenti al ruolo di Azure Active Directory corrispondente nell'interfaccia di amministrazione di Microsoft 365 offre agli utenti le autorizzazioni e le autorizzazioni necessarie per altre funzionalità di Microsoft 365.  Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](../../admin/add-users/about-admin-roles.md).
  >
  > - Anche il gruppo di ruoli di **Gestione organizzazione sola visualizzazione** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) offre inoltre l'accesso di sola lettura a tale funzionalità.

### <a name="how-does-microsoft-handle-your-data"></a>In che modo Microsoft gestisce i dati?

Per proteggere l'utente, Documenti sicuri invia i file al cloud [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) per l'analisi. I dettagli su come Microsoft Defender per Endpoint gestisce i dati sono disponibili qui: [Microsoft Defender per l'archiviazione e la privacy dei dati degli endpoint.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)

I file inviati da Documenti sicuri non vengono conservati in Defender oltre il tempo necessario per l'analisi (in genere, meno di 24 ore).

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a>Usare il Centro sicurezza & conformità per configurare Documenti sicuri

1. Nel Centro sicurezza & conformità passare **a** Allegati sicuri dei criteri di gestione delle minacce ATP e quindi fare clic \>  \> su **Impostazioni globali.**

2. Nel **riquadro a comparsa** Impostazioni globali visualizzato configura le impostazioni seguenti:

   - **Attivare Documenti sicuri per i client di Office:** spostare l'interruttore a destra per attivare la funzionalità: ![ attiva. ](../../media/scc-toggle-on.png)

   - **Consentire agli** utenti di fare clic su Visualizzazione protetta anche se Documenti sicuri identifica il file come dannoso: è consigliabile lasciare disattivata questa opzione (lasciare l'interruttore a sinistra: ![ ](../../media/scc-toggle-off.png) Disattiva).

   Al termine, fare clic su **Salva**.

   ![Impostazioni di Documenti sicuri dopo aver selezionato Impostazioni globali nella pagina Allegati sicuri.](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-to-configure-safe-documents"></a>Utilizzare PowerShell di Exchange Online per configurare Documenti sicuri

Utilizzare la sintassi seguente:

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- Il _parametro EnableSafeDocs_ consente di abilitare o disabilitare Documenti sicuri per l'intera organizzazione.
- Il _parametro AllowSafeDocsOpen_ consente o impedisce agli utenti di uscire da Visualizzazione protetta, ovvero l'apertura del documento, se il documento è stato identificato come dannoso.

In questo esempio vengono abilitati i documenti sicuri per l'intera organizzazione e viene impedito agli utenti di aprire documenti identificati come dannosi da Visualizzazione protetta.

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-AtpPolicyForO365.](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365)

### <a name="how-do-i-know-this-worked"></a>Come verificare se l'operazione ha avuto esito positivo?

Per verificare di aver abilitato e configurato Documenti sicuri, eseguire una delle operazioni seguenti:

- Nel Centro sicurezza & conformità passare  a Allegati sicuri \>  \> **atp**   dei criteri di  gestione delle minacce, fare clic su Impostazioni globali e verificare l'opzione Attiva documenti sicuri per i client di Office e Consenti agli utenti di fare clic su Visualizzazione protetta anche se Documenti sicuri identifica il file come impostazioni dannose.

- Eseguire il comando seguente in PowerShell di Exchange Online e verificare i valori delle proprietà:

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```

- I file seguenti sono disponibili per testare la protezione dei documenti sicuri. Questi documenti sono simili al file EICAR.TXT per testare le soluzioni antimalware e antivirus. I file non sono dannosi, ma attiveranno la protezione dei documenti sicuri.

  - [SafeDocsDemo.docx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.docx)
  - [SafeDocsDemo.pptx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.pptx)
  - [SafeDocsDemo.xlsx](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/SafeDocsDemo.xlsx)
