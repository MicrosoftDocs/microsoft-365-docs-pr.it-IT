---
title: Configurare le impostazioni globali per le impostazioni dei collegamenti sicuri in Defender per Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Gli amministratori possono ottenere informazioni su come visualizzare e configurare le impostazioni globali (l'elenco ' blocca gli URL seguenti ' e la protezione per le app di Office 365) per i collegamenti sicuri in Microsoft Defender per Office 365.
ms.openlocfilehash: 2793985e6289b26baad268925cbf9c5e9a89dce9
ms.sourcegitcommit: d81c7cea85af6ad5fef81d3c930514a51464368c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/04/2020
ms.locfileid: "49572430"
---
# <a name="configure-global-settings-for-safe-links-in-microsoft-defender-for-office-365"></a>Configurare le impostazioni globali per i collegamenti sicuri in Microsoft Defender per Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> Questo articolo è destinato ai clienti aziendali che dispongono di [Microsoft Defender per Office 365](office-365-atp.md). Se si è un utente di casa che cerca informazioni su Safelinks in Outlook, vedere [Advanced Outlook.com Security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).

Collegamenti attendibili è una funzionalità di [Microsoft Defender per Office 365](office-365-atp.md) che fornisce l'analisi degli URL dei messaggi di posta elettronica in ingresso nel flusso di posta e l'ora in cui si fa clic su verifica degli URL e dei collegamenti nei messaggi di posta elettronica e in altre posizioni. Per ulteriori informazioni, vedere [collegamenti sicuri in Microsoft Defender per Office 365](atp-safe-links.md).

È possibile configurare la maggior parte delle impostazioni dei collegamenti sicuri nei criteri collegamenti sicuri. Per istruzioni, vedere [configurare i criteri per i collegamenti sicuri in Microsoft Defender per Office 365](set-up-atp-safe-links-policies.md).

Tuttavia, i collegamenti sicuri utilizzano anche le impostazioni globali che si applicano a tutti gli utenti inclusi in tutti i criteri collegamenti sicuri attivi. Queste aree delle impostazioni globali:

- **Blocca l'elenco degli URL seguenti** . Per ulteriori informazioni, vedere [l'elenco "blocca gli URL seguenti" per i collegamenti sicuri](atp-safe-links.md#block-the-following-urls-list-for-safe-links)
- Protezione dei collegamenti sicuri per le app di Office 365. Per ulteriori informazioni, vedere [impostazioni dei collegamenti sicuri per le app di Office 365](atp-safe-links.md#safe-links-settings-for-office-365-apps).

È possibile configurare le impostazioni globali dei collegamenti sicuri nel centro sicurezza & Compliance o in PowerShell (Exchange Online PowerShell per organizzazioni Microsoft 365 idonee con cassette postali in Exchange Online; standalone EOP PowerShell per organizzazioni senza cassette postali di Exchange Online, ma con gli abbonamenti del componente aggiuntivo Microsoft Defender per Office 365).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare

- Le funzionalità fornite dalle impostazioni globali per i collegamenti sicuri vengono applicate solo agli utenti inclusi nei criteri dei collegamenti sicuri attivi. Non esiste alcun criterio di collegamenti sicuri incorporato o predefinito, pertanto è necessario creare almeno un criterio collegamenti sicuri affinché tali impostazioni globali siano attive. Per istruzioni, vedere [configurare i criteri per i collegamenti sicuri in Microsoft Defender per Office 365](set-up-atp-safe-links-policies.md).

- Aprire il Centro sicurezza e conformità in <https://protection.office.com/>. Per passare direttamente alla pagina **collegamenti sicuri** , utilizzare <https://protection.office.com/safelinksv2> .

- Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Per connettersi a PowerShell di EOP autonomo, vedere [Connettersi a PowerShell per Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Prima di poter eseguire le procedure descritte in questo articolo, è necessario disporre delle autorizzazioni per il Centro sicurezza & Compliance:
  - Per configurare le impostazioni globali per i collegamenti sicuri, è necessario essere membri dei gruppi di ruoli **Gestione organizzazione** o **amministratore sicurezza** .
  - Per l'accesso in sola lettura alle impostazioni globali per i collegamenti sicuri, è necessario essere membri dei gruppi di ruoli **lettore globale** o **lettore di sicurezza** .

  Per altre informazioni, vedere [Autorizzazioni nel Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).

  **Note**:

  - L'aggiunta di utenti al ruolo di Azure Active Directory corrispondente nell'interfaccia di amministrazione di Microsoft 365 fornisce agli utenti le autorizzazioni necessarie per il Centro sicurezza & Compliance _e_ le autorizzazioni per altre funzionalità di Microsoft 365. Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).
  - Il gruppo di ruoli di **gestione dell'organizzazione di sola visualizzazione** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) fornisce anche l'accesso in sola lettura alla funzionalità.

- Per i valori consigliati per le impostazioni globali per i collegamenti sicuri, vedere [Safe Links Settings](recommended-settings-for-eop-and-office365-atp.md#safe-links-settings).

- Consentire l'applicazione di un criterio nuovo o aggiornato fino a 30 minuti.

- Le [nuove funzionalità vengono continuamente aggiunte a Microsoft Defender per Office 365](office-365-atp.md#new-features-in-microsoft-defender-for-office-365). Man mano che si aggiungono nuove funzionalità, potrebbe essere necessario apportare modifiche ai criteri dei collegamenti sicuri esistenti.

## <a name="configure-the-block-the-following-urls-list-in-the-security--compliance-center"></a>Configurare l'elenco "blocca gli URL seguenti" nel centro sicurezza & Compliance

Il **blocco l'elenco degli URL seguente** identifica i collegamenti che devono essere sempre bloccati dall'analisi dei collegamenti sicuri nelle app supportate. Per ulteriori informazioni, vedere [l'elenco "blocca gli URL seguenti" per i collegamenti sicuri](atp-safe-links.md#block-the-following-urls-list-for-safe-links).

1. Nel centro sicurezza & conformità, accedere a collegamenti sicuri ATP per i criteri di **gestione delle minacce** \> **Policy** \> **ATP Safe Links** e quindi fare clic su **Impostazioni globali**.

2. Nel **criterio collegamenti sicuri per l'organizzazione** è possibile volare fuori che viene visualizzato, passare alla casella **blocca gli URL seguenti** .

3. Configurare una o più voci come descritto in [sintassi voce per l'elenco "blocca gli URL seguenti"](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list).

   Al termine, scegliere **Salva**.

### <a name="configure-the-block-the-following-urls-list-in-powershell"></a>Configurare l'elenco "blocca gli URL seguenti" in PowerShell

Per informazioni dettagliate sulla sintassi delle voci, vedere la [sintassi della voce per l'elenco "blocca gli URL seguenti"](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list).

È possibile utilizzare il cmdlet **Get-AtpPolicyForO365** per visualizzare le voci esistenti nella proprietà _BlockURLs_ .

- Per aggiungere valori che sostituiranno le voci esistenti, utilizzare la sintassi seguente in Exchange Online PowerShell o Exchange Online Protection PowerShell:

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "Entry1","Entry2",..."EntryN"
  ```

  In questo esempio vengono aggiunte all'elenco le voci seguenti:

  - Bloccare il dominio, i sottodomini e i percorsi di fabrikam.com.
  - Bloccare la ricerca sottodominio, ma non il dominio padre o altri sottodomini in tailspintoys.com

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "fabrikam.com","https://research.tailspintoys.com*"
  ```

- Per aggiungere o rimuovere valori senza alterare altre voci esistenti, utilizzare la sintassi seguente:

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}
  ```

  In questo esempio viene aggiunta una nuova voce per adatum.com e viene rimossa la voce per fabrikam.com.

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="adatum.com"; Remove="fabrikam"}
  ```

## <a name="configure-safe-links-protection-for-office-365-apps-in-the-security--compliance-center"></a>Configurare la protezione dei collegamenti sicuri per le app di Office 365 nel centro sicurezza & conformità

Protezione dei collegamenti sicuri per le app di Office 365 si applica ai documenti nelle app desktop, mobili e Web di Office supportate. Per ulteriori informazioni, vedere [impostazioni dei collegamenti sicuri per le app di Office 365](atp-safe-links.md#safe-links-settings-for-office-365-apps).

1. Nel centro sicurezza & conformità, accedere a collegamenti sicuri ATP per i criteri di **gestione delle minacce** \> **Policy** \> **ATP Safe Links** e quindi fare clic su **Impostazioni globali**.

2. Nel **criterio collegamenti sicuri per l'organizzazione** è possibile volare fuori, configurare le impostazioni seguenti nelle **impostazioni che si applicano al contenuto, ad eccezione della sezione posta elettronica** :

   - **Applicazioni di office 365**: verificare che l'interruttore sia a destra per abilitare i collegamenti sicuri per le app di Office 365 supportate: ![ attiva o disattiva l'attivazione ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) .

   - **Non monitorare quando gli utenti fanno clic su collegamenti sicuri**: spostare l'interruttore verso sinistra per tener conto dei clic degli utenti relativi agli URL bloccati nelle app di Office 365 supportate: disattivazione ![ ](../../media/scc-toggle-off.png) .

   - **Non consentire agli utenti di fare clic su collegamenti sicuri con l'URL originale**: verificare che l'interruttore sia a destra per impedire agli utenti di fare clic sull'URL bloccato originale nelle app di Office 365 supportate: ![ Attiva/disattiva ](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) .

   Al termine, scegliere **Salva**.

### <a name="configure-safe-links-protection-for-office-365-apps-in-powershell"></a>Configurare la protezione dei collegamenti sicuri per le app di Office 365 in PowerShell

Se si preferisce utilizzare PowerShell per configurare la protezione dei collegamenti sicuri per le app di Office 365, utilizzare la sintassi seguente in Exchange Online PowerShell o Exchange Online Protection PowerShell:

```powershell
Set-AtpPolicyForO365 [-EnableSafeLinksForO365Clients <$true | $false> [-AllowClickThrough <$true | $false>] [-TrackClicks <$true | $false>]
```

In questo esempio vengono configurate le impostazioni seguenti per la protezione dei collegamenti sicuri nelle app di Office 365:

- I collegamenti sicuri per le app di Office 365 sono attivati (non si utilizza il parametro _EnableSafeLinksForO365Clients_ e il valore predefinito è $true).
- Gli utenti che fanno clic su URL bloccati nelle app di Office 365 supportate vengono monitorati.
- Agli utenti non è consentito fare clic sull'URL bloccato originale nelle app di Office 365 supportate (non si utilizza il parametro _AllowClickThrough_ e il valore predefinito è $false).

```powershell
Set-AtpPolicyForO365 -TrackClicks $true
```

Per informazioni dettagliate sulla sintassi e sui parametri, vedere [set-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365).

## <a name="how-do-you-know-these-procedures-worked"></a>Come verificare se queste procedure hanno avuto esito positivo?

Per verificare di aver configurato correttamente le impostazioni globali per i collegamenti sicuri ( **blocca l'elenco degli URL seguenti** e le impostazioni di protezione delle app di Office 365), eseguire una delle operazioni seguenti:

- Nel centro sicurezza & conformità, accedere a criteri di **gestione delle minacce** per i \> **Policy** \> **collegamenti sicuri ATP**, fare clic su **Impostazioni globali** e verificare le impostazioni nel volo che viene visualizzato.

- In Exchange Online PowerShell o Exchange Online Protection PowerShell, eseguire il comando riportato di seguito e verificare le impostazioni:

  ```powershell
  Get-AtpPolicyForO365 | Format-List BlockUrls,EnableSafeLinksForO365Clients,AllowClickThrough,TrackClicks
  ```

  Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Get-AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365).
