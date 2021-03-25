---
title: Criteri consigliati per i documenti sicuri - Microsoft 365 per le aziende | Documenti Microsoft
description: Descrive i criteri consigliati da Microsoft riguardo alla protezione dell'accesso ai file di SharePoint.
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: m365-security
ms.topic: article
audience: Admin
f1.keywords:
- NOCSH
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- m365solution-identitydevice
- m365solution-scenario
ms.technology: mdo
ms.openlocfilehash: 1771f71e444233ffce60a4a56273d3062fe8b70d
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2021
ms.locfileid: "51204975"
---
# <a name="policy-recommendations-for-securing-sharepoint-sites-and-files"></a>Suggerimenti per i criteri per la protezione di file e siti di SharePoint

**Si applica a**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender per Office 365 piano 1 e piano 2](defender-for-office-365.md)
- SharePoint Online 


In questo articolo viene descritto come implementare i criteri di identità e accesso ai dispositivi consigliati per proteggere SharePoint e OneDrive for Business. Queste indicazioni si basano sui [criteri comuni di identità e accesso ai dispositivi.](identity-access-policies.md)

Questi suggerimenti si basano su tre diversi livelli di sicurezza e protezione per i file di SharePoint che possono essere applicati in base alla granularità delle proprie **esigenze:** di **base,** sensibile e **altamente regolamentato.** Ulteriori informazioni su questi livelli di sicurezza e sui sistemi operativi client consigliati, a cui fanno riferimento questi suggerimenti [nella panoramica](microsoft-365-policies-configurations.md).

Oltre a implementare queste indicazioni, assicurarsi di configurare i siti di SharePoint con la giusta quantità di protezione, inclusa l'impostazione delle autorizzazioni appropriate per contenuti sensibili e altamente regolamentati.

## <a name="updating-common-policies-to-include-sharepoint-and-onedrive-for-business"></a>Aggiornamento dei criteri comuni per includere SharePoint e OneDrive for Business

Per proteggere i file in SharePoint e OneDrive, nel diagramma seguente vengono illustrati i criteri da aggiornare dai criteri comuni di identità e accesso ai dispositivi.

[![Riepilogo degli aggiornamenti dei criteri per la protezione dell'accesso a Teams e ai relativi servizi dipendenti](../../media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)

Se al momento della creazione dei criteri comuni è stato incluso SharePoint, è necessario creare solo i nuovi criteri. Per i criteri di accesso condizionale, SharePoint include OneDrive.

I nuovi criteri implementano la protezione dei dispositivi per contenuti riservati e altamente regolamentati applicando requisiti di accesso specifici ai siti di SharePoint specificati.

Nella tabella seguente sono elencati i criteri che è necessario esaminare e aggiornare o creare nuovi per SharePoint. I criteri comuni sono link alle istruzioni di configurazione associate [nell'articolo Criteri di identità](identity-access-policies.md) e accesso ai dispositivi comuni.

|Livello di protezione|Criteri|Ulteriori informazioni|
|---|---|---|
|**Protezione di base**|[Richiedi autenticazione a più fattori quando il rischio di accesso *è medio* o *alto*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Includere SharePoint nell'assegnazione delle app cloud.|
||[Bloccare i client che non supportano l'autenticazione moderna](identity-access-policies.md#block-clients-that-dont-support-multi-factor)|Includere SharePoint nell'assegnazione delle app cloud.|
||[Applicare criteri di protezione dei dati APP](identity-access-policies.md#apply-app-data-protection-policies)|Assicurati che tutte le app consigliate siano incluse nell'elenco delle app. Assicurati di aggiornare i criteri per ogni piattaforma (iOS, Android, Windows).|
||[Richiedere computer conformi](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Includere SharePoint nell'elenco delle app cloud.|
||[Usare le restrizioni applicate alle app in SharePoint](#use-app-enforced-restrictions-in-sharepoint)|Aggiungi questo nuovo criterio. Ciò indica ad Azure Active Directory (Azure AD) di usare le impostazioni specificate in SharePoint. Questo criterio si applica a tutti gli utenti, ma influisce solo sull'accesso ai siti inclusi nei criteri di accesso di SharePoint.|
|**Sensibili**|[Richiedi autenticazione a più fattori quando il rischio di accesso è *basso,* *medio* o *alto*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Includere SharePoint nelle assegnazioni delle app cloud.|
||[Richiedere PC e *dispositivi* mobili conformi](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|Includere SharePoint nell'elenco delle app cloud.|
||[Criteri di controllo di accesso di SharePoint:](#sharepoint-access-control-policies)consente l'accesso solo tramite browser a siti di SharePoint specifici da dispositivi non gestiti.|In questo modo si impedisce la modifica e il download dei file. Utilizzare PowerShell per specificare i siti.|
|**Riservatezza elevata**|[*Richiedi* sempre MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Includere SharePoint nell'assegnazione delle app cloud.|
||[Criteri di controllo di accesso di SharePoint:](#use-app-enforced-restrictions-in-sharepoint)bloccare l'accesso a siti di SharePoint specifici da dispositivi non gestiti.|Utilizzare PowerShell per specificare i siti.|
|

## <a name="use-app-enforced-restrictions-in-sharepoint"></a>Usare restrizioni applicate alle app in SharePoint

Se si implementano i controlli di accesso in SharePoint, è necessario creare questo criterio di accesso condizionale in Azure AD per indicare ad Azure AD di applicare i criteri che si configurano in SharePoint. Questo criterio si applica a tutti gli utenti, ma influisce solo sull'accesso ai siti specificati tramite PowerShell quando si creano i controlli di accesso in SharePoint.

Per configurare questo criterio, vedere "Bloccare o limitare l'accesso a specifiche raccolte siti di SharePoint o a account di OneDrive" in [Controllare l'accesso da dispositivi non gestiti.](/sharepoint/control-access-from-unmanaged-devices)

## <a name="sharepoint-access-control-policies"></a>Criteri di controllo di accesso di SharePoint

Microsoft consiglia di proteggere il contenuto nei siti di SharePoint con contenuti sensibili e altamente regolamentati con controlli di accesso ai dispositivi. A tale scopo, creare un criterio che specifichi il livello di protezione e i siti a cui applicare la protezione.

- Siti riservati: consente l'accesso solo tramite browser. Ciò impedisce agli utenti di modificare e scaricare file.
- Siti altamente regolamentati: blocca l'accesso da dispositivi non gestiti.

Vedere "Bloccare o limitare l'accesso a specifiche raccolte siti di SharePoint o a account di OneDrive" in [Controllare l'accesso da dispositivi non gestiti.](/sharepoint/control-access-from-unmanaged-devices)

## <a name="how-these-policies-work-together"></a>Modalità di collaborazione di questi criteri

È importante comprendere che le autorizzazioni dei siti di SharePoint si basano in genere sulla necessità aziendale di accedere ai siti. Queste autorizzazioni sono gestite dai proprietari del sito e possono essere altamente dinamiche. L'uso dei criteri di accesso ai dispositivi di SharePoint garantisce la protezione di questi siti, indipendentemente dal fatto che gli utenti siano assegnati a un gruppo di Azure AD associato a una protezione di base, sensibile o altamente regolamentata.

Nella figura seguente viene fornito un esempio di come i criteri di accesso dei dispositivi di SharePoint proteggono l'accesso ai siti per un utente.

[![Esempio di come i criteri di accesso ai dispositivi di SharePoint proteggono i siti](../../media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)

[Vedi una versione più grande di questa immagine](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)

A Giacomo sono assegnati criteri di accesso condizionale di base, ma può avere accesso ai siti di SharePoint con protezione sensibile o altamente regolamentata.

- Se Giacomo accede a un sito sensibile o altamente regolamentato, è membro dell'uso del PC, il suo accesso viene concesso purché il PC sia conforme.
- Se Giacomo accede a un sito sensibile, è membro dell'utilizzo del telefono non gestito, che è consentito agli utenti di base, riceverà l'accesso solo tramite browser al sito sensibile a causa dei criteri di accesso al dispositivo configurati per questo sito.
- Se Giacomo accede a un sito altamente regolamentato di cui è membro utilizzando il telefono non gestito, verrà bloccato a causa dei criteri di accesso configurati per questo sito. Può accedere a questo sito solo usando il PC gestito e conforme.

## <a name="next-step"></a>Passaggio successivo

![Passaggio 4: Criteri per le app cloud di Microsoft 365](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

Configurare i criteri di accesso condizionale per:

- [Microsoft Teams](teams-access-policies.md)
- [Exchange Online](secure-email-recommended-policies.md)