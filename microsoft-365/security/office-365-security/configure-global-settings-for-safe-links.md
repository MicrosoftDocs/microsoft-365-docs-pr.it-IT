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
description: Gli amministratori possono imparare a visualizzare e configurare le impostazioni globali (l'elenco e la protezione "Blocca gli URL seguenti" per le app di Office 365) per i collegamenti sicuri in Microsoft Defender per Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d52a4dc5ed35ec73c1410d6428a581b098bf2c52
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287462"
---
# <a name="configure-global-settings-for-safe-links-in-microsoft-defender-for-office-365"></a>Configurare le impostazioni globali per i collegamenti sicuri in Microsoft Defender per Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Si applica a**
- [Microsoft Defender per Office 365 piano 1 e piano 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

> [!IMPORTANT]
> Questo articolo è rivolto ai clienti aziendali di [Microsoft Defender per Office 365](office-365-atp.md). Per informazioni sui collegamenti sicuri in Outlook, vedere [Advanced Outlook.com security.](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)

Collegamenti sicuri è una funzionalità di [Microsoft Defender per Office 365](office-365-atp.md) che fornisce l'analisi degli URL dei messaggi di posta elettronica in ingresso nel flusso di posta e l'ora della verifica degli URL e dei collegamenti nei messaggi di posta elettronica e in altre posizioni. Per altre informazioni, vedere [Collegamenti sicuri in Microsoft Defender per Office 365.](atp-safe-links.md)

La maggior parte delle impostazioni dei collegamenti sicuri viene configurata nei criteri Collegamenti sicuri. Per istruzioni, vedere [Configurare i criteri collegamenti sicuri in Microsoft Defender per Office 365.](set-up-atp-safe-links-policies.md)

Tuttavia, collegamenti sicuri utilizza anche impostazioni globali che si applicano a tutti gli utenti inclusi nei criteri collegamenti sicuri attivi. Queste aree di impostazioni globali:

- **L'elenco Blocca gli URL** seguenti. Per ulteriori informazioni, vedere [l'elenco "Bloccare gli URL seguenti" per i collegamenti sicuri](atp-safe-links.md#block-the-following-urls-list-for-safe-links)
- Protezione collegamenti sicuri per le app di Office 365. Per altre informazioni, vedere [Impostazioni dei collegamenti sicuri per le app di Office 365.](atp-safe-links.md#safe-links-settings-for-office-365-apps)

È possibile configurare le impostazioni globali dei collegamenti sicuri nel Centro sicurezza & e conformità o in PowerShell (PowerShell di Exchange Online per le organizzazioni di Microsoft 365 idonee con cassette postali in Exchange Online; PowerShell EOP autonomo per le organizzazioni senza cassette postali di Exchange Online, ma con sottoscrizioni ai componenti aggiuntivi di Microsoft Defender per Office 365).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Che cosa è necessario sapere prima di iniziare?

- Le funzionalità fornite dalle impostazioni globali per i collegamenti sicuri vengono applicate solo agli utenti inclusi nei criteri collegamenti sicuri attivi. Non è disponibile alcun criterio collegamenti sicuri predefinito o predefinito, pertanto è necessario creare almeno un criterio Collegamenti sicuri affinché queste impostazioni globali siano attive. Per istruzioni, vedere [Configurare i criteri collegamenti sicuri in Microsoft Defender per Office 365.](set-up-atp-safe-links-policies.md)

- Aprire il Centro sicurezza e conformità in <https://protection.office.com/>. Per passare direttamente alla **pagina Collegamenti sicuri,** utilizzare <https://protection.office.com/safelinksv2> .

- Per informazioni su come connettersi a PowerShell per Exchange Online, vedere [Connettersi a PowerShell per Exchange Online](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Per connettersi a PowerShell di EOP autonomo, vedere [Connettersi a PowerShell per Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Per poter eseguire le procedure contenute in questo articolo è necessario disporre delle autorizzazioni appropriate nel Centro sicurezza e conformità:
  - Per configurare le impostazioni globali per i collegamenti sicuri, è necessario essere membri dei gruppi di ruoli **Gestione** organizzazione o **Amministratore** sicurezza.
  - Per l'accesso in sola lettura alle impostazioni globali per i  collegamenti  sicuri, è necessario essere membri dei gruppi di ruoli Lettore globale o Lettore di sicurezza.

  Per altre informazioni, vedere [Autorizzazioni nel Centro sicurezza e conformità](permissions-in-the-security-and-compliance-center.md).

  **Note**:

  - L'aggiunta di utenti al ruolo di Azure Active Directory corrispondente nell'interfaccia di amministrazione di Microsoft 365 fornisce agli utenti le autorizzazioni necessarie nel centro Sicurezza e conformità _e_ le autorizzazioni per altre funzionalità di Microsoft 365. Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](../../admin/add-users/about-admin-roles.md).
  - Anche il gruppo di ruoli di **Gestione organizzazione sola visualizzazione** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) offre inoltre l'accesso di sola lettura a tale funzionalità.

- Per i valori consigliati per le impostazioni globali per i collegamenti sicuri, vedere [Impostazioni collegamenti sicuri.](recommended-settings-for-eop-and-office365-atp.md#safe-links-settings)

- Consentire fino a 30 minuti per l'applicazione di un criterio nuovo o aggiornato.

- [Nuove funzionalità vengono continuamente aggiunte a Microsoft Defender per Office 365.](office-365-atp.md#new-features-in-microsoft-defender-for-office-365) Quando vengono aggiunte nuove funzionalità, potrebbe essere necessario apportare modifiche ai criteri collegamenti sicuri esistenti.

## <a name="configure-the-block-the-following-urls-list-in-the-security--compliance-center"></a>Configurare l'elenco "Blocca gli URL seguenti" nel Centro sicurezza & conformità

**L'elenco Blocca gli URL seguenti identifica** i collegamenti che devono essere sempre bloccati dall'analisi dei collegamenti sicuri nelle app supportate. Per ulteriori informazioni, vedere l'elenco "Bloccare gli [URL seguenti" per Collegamenti sicuri.](atp-safe-links.md#block-the-following-urls-list-for-safe-links)

1. Nel Centro sicurezza & conformità, accedere **a** Collegamenti sicuri dei criteri di gestione delle minacce ATP e quindi fare clic \>  \> su **Impostazioni globali.**

2. Nel riquadro **a comparsa dei criteri** collegamenti sicuri per l'organizzazione visualizzato passare alla casella Blocca gli **URL** seguenti.

3. Configurare una o più voci come descritto nella sintassi delle voci per [l'elenco "Blocca gli URL seguenti".](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list)

   Al termine, fare clic su **Salva**.

### <a name="configure-the-block-the-following-urls-list-in-powershell"></a>Configurare l'elenco "Blocca gli URL seguenti" in PowerShell

Per informazioni dettagliate sulla sintassi delle voci, vedere La sintassi delle voci per [l'elenco "Bloccare gli URL seguenti".](atp-safe-links.md#entry-syntax-for-the-block-the-following-urls-list)

È possibile utilizzare il cmdlet **Get-AtpPolicyForO365** per visualizzare le voci esistenti nella _proprietà BlockURLs._

- Per aggiungere valori che sostituiranno le voci esistenti, utilizzare la seguente sintassi in PowerShell di Exchange Online o PowerShell di Exchange Online Protection:

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

## <a name="configure-safe-links-protection-for-office-365-apps-in-the-security--compliance-center"></a>Configurare la protezione dei collegamenti sicuri per le app di Office 365 nel Centro sicurezza & conformità

La protezione collegamenti sicuri per le app di Office 365 si applica ai documenti nelle app desktop, mobili e Web di Office supportate. Per altre informazioni, vedere [Impostazioni dei collegamenti sicuri per le app di Office 365.](atp-safe-links.md#safe-links-settings-for-office-365-apps)

1. Nel Centro sicurezza & conformità, accedere **a** Collegamenti sicuri dei criteri di gestione delle minacce ATP e quindi fare clic \>  \> su **Impostazioni globali.**

2. Nel riquadro **a comparsa dei criteri** collegamenti sicuri per l'organizzazione, configurare le impostazioni seguenti nella sezione Impostazioni applicabili al contenuto ad eccezione della **posta** elettronica:

   - **Applicazioni di Office 365:** verificare che l'interruttore sia a destra per abilitare Collegamenti sicuri per le app di Office 365 ![ supportate: attivare o disattivare ](../../media/scc-toggle-on.png) .

   - **Non tenere traccia quando** gli utenti fanno clic su Collegamenti sicuri: spostare l'interruttore a sinistra per tenere traccia dei clic degli utenti correlati agli URL bloccati nelle app di Office 365 ![ supportate: disattivare ](../../media/scc-toggle-off.png) .

   - **Non** consentire agli utenti di fare clic su Collegamenti sicuri all'URL originale: verificare che l'interruttore sia a destra per impedire agli utenti di fare clic sull'URL bloccato originale nelle app di Office 365 supportate: ![ Attiva/Disattiva. ](../../media/scc-toggle-on.png)

   Al termine, fare clic su **Salva**.

### <a name="configure-safe-links-protection-for-office-365-apps-in-powershell"></a>Configurare la protezione dei collegamenti sicuri per le app di Office 365 in PowerShell

Se si preferisce utilizzare PowerShell per configurare la protezione dei collegamenti sicuri per le app di Office 365, utilizzare la sintassi seguente in PowerShell di Exchange Online o PowerShell di Exchange Online Protection:

```powershell
Set-AtpPolicyForO365 [-EnableSafeLinksForO365Clients <$true | $false> [-AllowClickThrough <$true | $false>] [-TrackClicks <$true | $false>]
```

In questo esempio vengono configurate le impostazioni seguenti per la protezione dei collegamenti sicuri nelle app di Office 365:

- Collegamenti sicuri per le app di Office 365 è attivato (non viene utilizzato il parametro _EnableSafeLinksForO365Clients_ e il valore predefinito è $true).
- I clic degli utenti correlati agli URL bloccati nelle app di Office 365 supportate vengono monitorati.
- Agli utenti non è consentito fare clic sull'URL bloccato originale nelle app di Office 365 supportate (non viene utilizzato il parametro _AllowClickThrough_ e il valore predefinito è $false).

```powershell
Set-AtpPolicyForO365 -TrackClicks $true
```

Per informazioni dettagliate sulla sintassi e sui parametri, [vedere Set-AtpPolicyForO365.](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365)

## <a name="how-do-you-know-these-procedures-worked"></a>Come verificare se queste procedure hanno avuto esito positivo?

Per verificare di aver configurato correttamente le impostazioni  globali per i collegamenti sicuri (l'elenco Blocca gli URL seguenti e le impostazioni di protezione delle app di Office 365), eseguire una delle operazioni seguenti:

- Nel Centro sicurezza & conformità, accedere  a Collegamenti sicuri \>  \> **ATP** dei criteri di gestione delle minacce, fare clic su Impostazioni globali e verificare le impostazioni nel riquadro a comparsa visualizzato.

- In PowerShell di Exchange Online o PowerShell di Exchange Online Protection, eseguire il comando seguente e verificare le impostazioni:

  ```powershell
  Get-AtpPolicyForO365 | Format-List BlockUrls,EnableSafeLinksForO365Clients,AllowClickThrough,TrackClicks
  ```

  Per informazioni dettagliate sulla sintassi e sui parametri, vedere [Get-AtpPolicyForO365.](https://docs.microsoft.com/powershell/module/exchange/get-atppolicyforo365)
