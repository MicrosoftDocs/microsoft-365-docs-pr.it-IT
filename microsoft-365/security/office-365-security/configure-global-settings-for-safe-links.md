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
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Gli amministratori possono imparare a visualizzare e configurare le impostazioni globali (l'elenco "Blocca gli URL seguenti" e la protezione per le app Office 365) per i collegamenti sicuri in Microsoft Defender per Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4e77373657d3167ca8f5bafa544923ab3a2320ce
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2021
ms.locfileid: "52821986"
---
# <a name="configure-global-settings-for-safe-links-in-microsoft-defender-for-office-365"></a>Configurare le impostazioni globali per i collegamenti sicuri in Microsoft Defender per Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Microsoft Defender per Office 365 piano 1 e piano 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> Questo articolo è rivolto ai clienti aziendali di [Microsoft Defender per Office 365](defender-for-office-365.md). Se si è un utente principale che cerca informazioni sui collegamenti sicuri in Outlook, vedere [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).

Collegamenti sicuri è una funzionalità di [Microsoft Defender per Office 365 che](defender-for-office-365.md) fornisce l'analisi URL dei messaggi di posta elettronica in ingresso nel flusso di posta e l'ora della verifica degli URL e dei collegamenti nei messaggi di posta elettronica e in altre posizioni. Per altre informazioni, vedi [Collegamenti sicuri in Microsoft Defender per Office 365](safe-links.md).

La maggior parte delle impostazioni dei collegamenti sicuri viene configurata nei criteri Collegamenti sicuri. Per istruzioni, vedi [Configurare i criteri collegamenti sicuri in Microsoft Defender per Office 365](set-up-safe-links-policies.md).

Tuttavia, collegamenti sicuri utilizza anche le impostazioni globali seguenti configurate all'esterno dei criteri collegamenti sicuri stessi:

- **L'elenco Blocca gli URL seguenti.** Questa impostazione si applica a tutti gli utenti inclusi nei criteri collegamenti sicuri attivi. Per ulteriori informazioni, vedere [l'elenco "Bloccare](safe-links.md#block-the-following-urls-list-for-safe-links) gli URL seguenti" per Collegamenti sicuri
- Protezione dei collegamenti sicuri per Office 365 app. Queste impostazioni si applicano a tutti gli utenti dell'organizzazione con licenza per Defender per Office 365, indipendentemente dal fatto che gli utenti siano inclusi o meno nei criteri collegamenti sicuri attivi. Per altre informazioni, vedi [Impostazioni dei collegamenti sicuri per Office 365 app](safe-links.md#safe-links-settings-for-office-365-apps).

È possibile configurare le impostazioni globali dei collegamenti sicuri nel Centro sicurezza Microsoft 365 o in PowerShell (Exchange Online PowerShell per le organizzazioni Microsoft 365 idonee con cassette postali in Exchange Online; PowerShell EOP autonomo per le organizzazioni senza cassette postali di Exchange Online, ma con sottoscrizioni di componenti aggiuntivi di Microsoft Defender per Office 365).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare?

- Non è disponibile alcun criterio collegamenti sicuri predefinito o predefinito, quindi è necessario creare almeno un criterio Collegamenti sicuri affinché l'elenco Blocca gli **URL** seguenti sia attivo. Per istruzioni, vedi [Configurare i criteri collegamenti sicuri in Microsoft Defender per Office 365](set-up-safe-links-policies.md).

- Aprire il Centro sicurezza a <https://security.microsoft.com>. Per passare direttamente alla **pagina Collegamenti sicuri,** utilizzare <https://security.microsoft.com/safelinksv2> .

- Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell). Per connettersi a PowerShell di EOP autonomo, vedere [Connettersi a PowerShell per Exchange Online Protection](/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Prima di eseguire le procedure descritte in questo articolo, occorre disporre delle autorizzazioni in **Exchange Online**:
  - Per configurare le impostazioni globali per i collegamenti sicuri, è necessario essere membri dei **gruppi di** ruoli Gestione organizzazione o Amministratore **sicurezza.**
  - Per l'accesso in sola lettura alle impostazioni globali per i collegamenti sicuri, è necessario essere membri dei gruppi di ruoli **Lettore** globale o **Lettore** di sicurezza.

  Per altre informazioni, vedere [Autorizzazioni in Exchange Online](/exchange/permissions-exo/permissions-exo).

  **Note**:

  - L'aggiunta di utenti al ruolo di Azure Active Directory corrispondente nell'interfaccia di amministrazione di Microsoft 365 fornisce agli utenti le autorizzazioni necessarie _e_ le autorizzazioni per altre funzionalità di Microsoft 365. Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](../../admin/add-users/about-admin-roles.md).
  - Anche il gruppo di ruoli di **Gestione organizzazione sola visualizzazione** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) offre inoltre l'accesso di sola lettura a tale funzionalità.

- Per i valori consigliati per le impostazioni globali per i collegamenti sicuri, vedere [Safe Links settings.](recommended-settings-for-eop-and-office365.md#safe-links-settings)

- Consentire fino a 30 minuti per l'applicazione di un criterio nuovo o aggiornato.

- [Nuove funzionalità vengono continuamente aggiunte a Microsoft Defender per Office 365](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365). Quando vengono aggiunte nuove funzionalità, potrebbe essere necessario apportare modifiche ai criteri collegamenti sicuri esistenti.

## <a name="configure-the-block-the-following-urls-list-in-the-security-center"></a>Configurare l'elenco "Blocca gli URL seguenti" nel Centro sicurezza

**L'elenco Blocca gli URL** seguenti identifica i collegamenti che devono essere sempre bloccati dall'analisi dei collegamenti sicuri nelle app supportate. Per ulteriori informazioni, vedere [l'elenco "Bloccare gli URL seguenti" per Collegamenti sicuri.](safe-links.md#block-the-following-urls-list-for-safe-links)

1. Nel centro sicurezza passare a Criteri di collaborazione & **e-mail** & regole Criteri di minaccia \>  \>  \>  sezione \> **Collegamenti sicuri**.

2. Nella pagina **Collegamenti sicuri** fare clic su **Impostazioni globali.** Nel riquadro **a comparsa Dei** collegamenti sicuri per l'organizzazione visualizzato passare alla casella Blocca gli **URL** seguenti.

3. Configurare una o più voci come descritto in [Sintassi voce per l'elenco "Blocca gli URL seguenti".](safe-links.md#entry-syntax-for-the-block-the-following-urls-list)

   Al termine, scegliere **Salva**.

### <a name="configure-the-block-the-following-urls-list-in-powershell"></a>Configurare l'elenco "Blocca gli URL seguenti" in PowerShell

Per informazioni dettagliate sulla sintassi delle voci, vedere [Entry syntax for the "Block the following URLs" list](safe-links.md#entry-syntax-for-the-block-the-following-urls-list).

È possibile utilizzare il cmdlet **Get-AtpPolicyForO365** per visualizzare le voci esistenti nella _proprietà BlockURLs._

- Per aggiungere valori che sostituiranno eventuali voci esistenti, utilizzare la sintassi seguente in Exchange Online PowerShell o Exchange Online Protection PowerShell:

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "Entry1","Entry2",..."EntryN"
  ```

  In questo esempio vengono aggiunte le voci seguenti all'elenco:

  - Bloccare il dominio, i sottodomini e i percorsi per fabrikam.com.
  - Bloccare la ricerca di sottodomini, ma non il dominio padre o altri sottodomini in tailspintoys.com

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "fabrikam.com","https://research.tailspintoys.com*"
  ```

- Per aggiungere o rimuovere valori senza influire sulle altre voci esistenti, utilizzare la sintassi seguente:

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}
  ```

  In questo esempio viene aggiunta una nuova voce per adatum.com e viene rimossa la voce per fabrikam.com.

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="adatum.com"; Remove="fabrikam"}
  ```

## <a name="configure-safe-links-protection-for-office-365-apps-in-the-security-center"></a>Configurare la protezione dei collegamenti sicuri per Office 365 app nel Centro sicurezza

La protezione collegamenti sicuri per Office 365 app si applica ai documenti nelle app Office desktop, mobili e Web supportate. Per altre informazioni, vedi [Impostazioni dei collegamenti sicuri per Office 365 app](safe-links.md#safe-links-settings-for-office-365-apps).

1. Nel centro sicurezza passare a Criteri di collaborazione & **e-mail** & regole Criteri di minaccia \>  \>  \>  sezione \> **Collegamenti sicuri**.

2. Nella pagina **Collegamenti sicuri** fare clic su **Impostazioni globali.** Nel riquadro **a comparsa** Collegamenti sicuri per l'organizzazione visualizzato configurare le impostazioni seguenti nel Impostazioni che si applicano al contenuto **nelle** app Office 365 supportate:

   - **Usa collegamenti sicuri nelle app Office 365**: verifica che l'interruttore sia a destra per abilitare Collegamenti sicuri per le app Office 365 supportate: ![ Attiva/disattiva ](../../media/scc-toggle-on.png) .

   - **Non tenere** traccia quando gli utenti fanno clic su collegamenti protetti nelle app di Office 365 : sposta l'interruttore a sinistra per tenere traccia dei clic degli utenti correlati agli URL bloccati nelle app Office 365 supportate: Disattiva ![ ](../../media/scc-toggle-off.png) .

   - Non consentire agli utenti di fare clic sull'URL originale nelle app **di Office 365:** verificare che l'interruttore sia a destra per impedire agli utenti di fare clic sull'URL bloccato originale nelle app Office 365 supportate: Attiva/disattiva ![ ](../../media/scc-toggle-on.png) .

   Al termine, scegliere **Salva**.

### <a name="configure-safe-links-protection-for-office-365-apps-in-powershell"></a>Configurare la protezione dei collegamenti sicuri per Office 365 app in PowerShell

Se si preferisce usare PowerShell per configurare la protezione dei collegamenti sicuri per le app Office 365, utilizzare la sintassi seguente in Exchange Online PowerShell o Exchange Online Protection PowerShell:

```powershell
Set-AtpPolicyForO365 [-EnableSafeLinksForO365Clients <$true | $false> [-AllowClickThrough <$true | $false>] [-TrackClicks <$true | $false>]
```

In questo esempio vengono configurate le impostazioni seguenti per la protezione dei collegamenti sicuri nelle Office 365 app:

- Collegamenti sicuri per Office 365 app è attivato (non viene utilizzato il parametro _EnableSafeLinksForO365Clients_ e il valore predefinito è $true).
- I clic degli utenti correlati agli URL bloccati nelle app Office 365 vengono monitorate.
- Agli utenti non è consentito fare clic sull'URL bloccato originale nelle app Office 365 supportate (non viene utilizzato il parametro _AllowClickThrough_ e il valore predefinito è $false).

```powershell
Set-AtpPolicyForO365 -TrackClicks $true
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-AtpPolicyForO365.](/powershell/module/exchange/set-atppolicyforo365)

## <a name="how-do-you-know-these-procedures-worked"></a>Come verificare se queste procedure hanno avuto esito positivo?

Per verificare di aver configurato correttamente le impostazioni  globali per i collegamenti sicuri (l'elenco Blocca gli URL seguenti e le impostazioni di protezione delle app di Office 365), eseguire una delle operazioni seguenti:

- Nel centro sicurezza passare **a** Criteri di collaborazione & posta elettronica & Regole Criteri di minaccia sezione Collegamenti sicuri fare clic su Impostazioni globali e verificare le impostazioni nel riquadro a comparsa \>  \>  \>  \>  \> visualizzato. 

- In Exchange Online PowerShell o Exchange Online Protection PowerShell, eseguire il comando seguente e verificare le impostazioni:

  ```powershell
  Get-AtpPolicyForO365 | Format-List BlockUrls,EnableSafeLinksForO365Clients,AllowClickThrough,TrackClicks
  ```

  Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Get-AtpPolicyForO365](/powershell/module/exchange/get-atppolicyforo365).
