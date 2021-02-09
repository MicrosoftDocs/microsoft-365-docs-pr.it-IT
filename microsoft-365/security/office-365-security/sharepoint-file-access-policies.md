---
title: Criteri di protezione dei documenti consigliati - Microsoft 365 per le aziende | Microsoft Docs
description: Descrive i criteri consigliati da Microsoft riguardo alla protezione dell'accesso ai file di SharePoint.
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: m365-security
ms.topic: article
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
ms.openlocfilehash: 5c739a47ccab79561277436812c36f842b6b578c
ms.sourcegitcommit: d739f48b991793c08522a3d5323beba27f0111b2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/08/2021
ms.locfileid: "50142814"
---
# <a name="policy-recommendations-for-securing-sharepoint-sites-and-files"></a>Suggerimenti per i criteri per la protezione di siti e file di SharePoint

**Si applica a**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender per Office 365 piano 1 e piano 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- SharePoint Online 


In questo articolo viene descritto come implementare i criteri di identità e accesso ai dispositivi consigliati per proteggere SharePoint e OneDrive for Business. Queste indicazioni si basano sui [criteri comuni di identità e accesso ai dispositivi.](identity-access-policies.md)

Questi suggerimenti si basano su tre diversi livelli di sicurezza e protezione per i file di SharePoint che possono essere applicati in base alla granularità delle proprie **esigenze:** di **base,** sensibile e **altamente regolamentato.** Per ulteriori informazioni su questi livelli di sicurezza e sui sistemi operativi client consigliati, vedere questi suggerimenti [nella panoramica.](microsoft-365-policies-configurations.md)

Oltre a implementare queste indicazioni, assicurarsi di configurare i siti di SharePoint con la giusta quantità di protezione, inclusa l'impostazione delle autorizzazioni appropriate per i contenuti sensibili e altamente regolamentati.

## <a name="updating-common-policies-to-include-sharepoint-and-onedrive-for-business"></a>Aggiornamento dei criteri comuni per includere SharePoint e OneDrive for Business

Per proteggere i file in SharePoint e OneDrive, nel diagramma seguente vengono illustrati i criteri da aggiornare dai criteri comuni di identità e accesso ai dispositivi.

[![Riepilogo degli aggiornamenti dei criteri per la protezione dell'accesso a Teams e ai relativi servizi dipendenti](../../media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)

[Vedere una versione più grande di questa immagine](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)

Se è stato incluso SharePoint durante la creazione dei criteri comuni, è necessario creare solo i nuovi criteri. Per i criteri di accesso condizionale, SharePoint include OneDrive.

I nuovi criteri implementano la protezione dei dispositivi per contenuti sensibili e altamente regolamentati applicando requisiti di accesso specifici ai siti di SharePoint specificati.

Nella tabella seguente sono elencati i criteri che è necessario esaminare e aggiornare o crearne di nuovi per SharePoint. I criteri comuni sono associati alle istruzioni di configurazione [nell'articolo Criteri comuni di](identity-access-policies.md) identità e accesso ai dispositivi.

|Livello di protezione|Criteri|Altre informazioni|
|---|---|---|
|**Protezione di base**|[Richiedere l'autenticazione a più fattori quando il rischio di accesso *è medio* o *alto*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Includere SharePoint nell'assegnazione delle app cloud.|
||[Bloccare i client che non supportano l'autenticazione moderna](identity-access-policies.md#block-clients-that-dont-support-multi-factor)|Includere SharePoint nell'assegnazione delle app cloud.|
||[Applicare i criteri di protezione dei dati app](identity-access-policies.md#apply-app-data-protection-policies)|Assicurati che tutte le app consigliate siano incluse nell'elenco delle app. Assicurati di aggiornare i criteri per ogni piattaforma (iOS, Android, Windows).|
||[Richiedere computer conformi](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Includere SharePoint nell'elenco delle app cloud.|
||[Usare le restrizioni applicate alle app in SharePoint](#use-app-enforced-restrictions-in-sharepoint)|Aggiungere questo nuovo criterio. Ciò indica ad Azure Active Directory (Azure AD) di usare le impostazioni specificate in SharePoint. Questo criterio si applica a tutti gli utenti, ma influisce solo sull'accesso ai siti inclusi nei criteri di accesso di SharePoint.|
|**Sensibili**|[Richiedere l'autenticazione a più fattori quando il rischio di accesso è *basso,* *medio* o *alto*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Includere SharePoint nelle assegnazioni delle app cloud.|
||[Richiedere PC e *dispositivi* mobili conformi](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|Includere SharePoint nell'elenco delle app cloud.|
||[Criteri di controllo di accesso di SharePoint:](#sharepoint-access-control-policies)consente l'accesso solo tramite browser a siti di SharePoint specifici da dispositivi non gestiti.|In questo modo si impedisce la modifica e il download dei file. Utilizzare PowerShell per specificare i siti.|
|**Riservatezza elevata**|[*Richiedi sempre* L'autenticazione a più fattori](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Includere SharePoint nell'assegnazione delle app cloud.|
||[Criteri di controllo di accesso di SharePoint:](#use-app-enforced-restrictions-in-sharepoint)bloccare l'accesso a siti di SharePoint specifici da dispositivi non gestiti.|Utilizzare PowerShell per specificare i siti.|
|

## <a name="use-app-enforced-restrictions-in-sharepoint"></a>Usare restrizioni applicate dall'app in SharePoint

Se si implementano i controlli di accesso in SharePoint, è necessario creare questo criterio di accesso condizionale in Azure AD per indicare ad Azure AD di applicare i criteri che si configurano in SharePoint. Questo criterio si applica a tutti gli utenti, ma influisce solo sull'accesso ai siti specificati tramite PowerShell quando si creano i controlli di accesso in SharePoint.

Per configurare questo criterio, vedere "Bloccare o limitare l'accesso a specifiche raccolte siti di SharePoint o account di OneDrive" in Controllare l'accesso [da dispositivi non gestiti.](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)

## <a name="sharepoint-access-control-policies"></a>Criteri di controllo di accesso di SharePoint

Microsoft consiglia di proteggere i contenuti nei siti di SharePoint con contenuti sensibili e altamente regolamentati con controlli di accesso ai dispositivi. A tale scopo, creare un criterio che specifichi il livello di protezione e i siti a cui applicare la protezione.

- Siti sensibili: consente l'accesso solo ai browser. Ciò impedisce agli utenti di modificare e scaricare file.
- Siti altamente regolamentati: bloccare l'accesso da dispositivi non gestiti.

Vedere "Bloccare o limitare l'accesso a raccolte siti di SharePoint o account di OneDrive specifici" in [Controllare l'accesso da dispositivi non gestiti.](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)

## <a name="how-these-policies-work-together"></a>Funzionamento di questi criteri

È importante comprendere che le autorizzazioni dei siti di SharePoint si basano in genere sulle esigenze aziendali per l'accesso ai siti. Queste autorizzazioni sono gestite dai proprietari del sito e possono essere altamente dinamiche. L'uso dei criteri di accesso ai dispositivi di SharePoint garantisce la protezione di questi siti, indipendentemente dal fatto che gli utenti siano assegnati a un gruppo di Azure AD associato a una protezione di base, sensibile o altamente regolamentata.

Nella figura seguente viene fornito un esempio di come i criteri di accesso dei dispositivi di SharePoint proteggono l'accesso ai siti per un utente.

[![Esempio di come i criteri di accesso ai dispositivi di SharePoint proteggono i siti](../../media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)

[Vedere una versione più grande di questa immagine](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)

A Luisa sono stati assegnati criteri di accesso condizionale di base, ma può avere accesso ai siti di SharePoint con protezione sensibile o altamente regolamentata.

- Se Luisa accede a un sito sensibile o altamente regolamentato, è un membro dell'uso del PC, il suo accesso viene concesso purché il suo PC sia conforme.
- Se Luisa accede a un sito sensibile, è membro dell'uso del telefono non gestito, che è consentito agli utenti di base, riceverà l'accesso solo tramite browser al sito sensibile a causa dei criteri di accesso al dispositivo configurati per questo sito.
- Se Luisa accede a un sito altamente regolamentato di cui è membro utilizzando il telefono non gestito, verrà bloccato a causa dei criteri di accesso configurati per il sito. Può accedere a questo sito solo usando il suo PC gestito e conforme.

## <a name="next-step"></a>Passaggio successivo

![Passaggio 4: Criteri per le app cloud di Microsoft 365](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

Configurare i criteri di accesso condizionale per:

- [Microsoft Teams](teams-access-policies.md)
- [Exchange Online](secure-email-recommended-policies.md)
