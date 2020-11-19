---
title: Criteri di sicurezza dei documenti consigliati-Microsoft 365 per Enterprise | Documenti Microsoft
description: Descrive i criteri consigliati da Microsoft riguardo alla protezione dell'accesso ai file di SharePoint.
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 7e8104e234bd1b724bc62fb1a9b401ab83a2bcb4
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/19/2020
ms.locfileid: "49357528"
---
# <a name="policy-recommendations-for-securing-sharepoint-sites-and-files"></a>Suggerimenti sui criteri per la protezione di siti e file di SharePoint

In questo articolo viene descritto come implementare i criteri di identità e accesso ai dispositivi consigliati per la protezione di SharePoint e OneDrive for business. Queste linee guida si basano sui [criteri comuni di identità e accesso ai dispositivi](identity-access-policies.md).

Questi suggerimenti si basano su tre diversi livelli di sicurezza e protezione per i file di SharePoint che possono essere applicati in base alla granularità delle proprie esigenze: **linea di base**, **sensibile** e **altamente regolamentata**. È possibile ottenere ulteriori informazioni su questi livelli di sicurezza e sui sistemi operativi client consigliati, a cui si fa riferimento in questa [sezione](microsoft-365-policies-configurations.md).

Oltre all'implementazione di queste linee guida, assicurarsi di configurare i siti di SharePoint con la giusta quantità di protezione, tra cui l'impostazione delle autorizzazioni appropriate per i contenuti sensibili e altamente regolamentati.

## <a name="updating-common-policies-to-include-sharepoint-and-onedrive-for-business"></a>Aggiornamento dei criteri comuni per includere SharePoint e OneDrive for business

Per proteggere i file in SharePoint e OneDrive, nel diagramma seguente vengono illustrati i criteri da aggiornare dai criteri di identità e accesso ai dispositivi comuni.

[![Riepilogo degli aggiornamenti dei criteri per la protezione dell'accesso ai team e ai servizi dipendenti](../../media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)

[Visualizzazione di una versione più grande di questa immagine](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-sharepoint.png)

Se è stato incluso SharePoint quando sono stati creati i criteri comuni, è necessario creare solo i nuovi criteri. Per i criteri di accesso condizionale, SharePoint include OneDrive.

I nuovi criteri implementano la protezione del dispositivo per soddisfare sensibili e altamente regolamentati applicando specifici requisiti di accesso ai siti di SharePoint specificati.

Nella tabella seguente sono elencati i criteri che è necessario rivedere e aggiornare o creare nuovi per SharePoint. I criteri comuni collegano le istruzioni di configurazione associate nell'articolo [Common Identity and Device Access Policies](identity-access-policies.md) .

|Livello di protezione|Criteri|Ulteriori informazioni|
|---|---|---|
|**Protezione di base**|[Richiedere l'AMF quando il rischio di accesso è *medio* o *elevato*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Includere SharePoint nell'assegnazione delle app cloud.|
||[Bloccare i client che non supportano l'autenticazione moderna](identity-access-policies.md#block-clients-that-dont-support-modern-authentication)|Includere SharePoint nell'assegnazione delle app cloud.|
||[Applicare i criteri di protezione dei dati dell'APP](identity-access-policies.md#apply-app-data-protection-policies)|Assicurarsi che tutte le app consigliate siano incluse nell'elenco delle app. Assicurarsi di aggiornare i criteri per ogni piattaforma (iOS, Android, Windows).|
||[Richiedere computer conformi](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Includere SharePoint nell'elenco delle app cloud.|
||[Utilizzare le restrizioni applicate dalle app in SharePoint](#use-app-enforced-restrictions-in-sharepoint)|Aggiungere il nuovo criterio. Questo indica ad Azure Active Directory (Azure AD) di utilizzare le impostazioni specificate in SharePoint. Questo criterio si applica a tutti gli utenti, ma influenza solo l'accesso ai siti inclusi nei criteri di accesso di SharePoint.|
|**Sensibili**|[Richiedere l'AMF quando il rischio di accesso è *basso*, *medio* o *alto*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Includere SharePoint nelle assegnazioni delle app cloud.|
||[Richiedere PC conformi *e* dispositivi mobili](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|Includere SharePoint nell'elenco delle app cloud.|
||[Criteri di controllo di accesso di SharePoint](#sharepoint-access-control-policies): Consenti accesso solo browser a siti di SharePoint specifici da dispositivi non gestiti.|In questo modo si impedisce la modifica e il download dei file. Utilizzare PowerShell per specificare i siti.|
|**Riservatezza elevata**|[Richiede *sempre* l'autenticazione Master](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Includere SharePoint nell'assegnazione delle app cloud.|
||[Criteri di controllo dell'accesso di SharePoint](#use-app-enforced-restrictions-in-sharepoint): bloccare l'accesso a siti di SharePoint specifici da dispositivi non gestiti.|Utilizzare PowerShell per specificare i siti.|
|

## <a name="use-app-enforced-restrictions-in-sharepoint"></a>Utilizzare le restrizioni applicate dalle app in SharePoint

Se si implementano i controlli di accesso in SharePoint, è necessario creare il criterio di accesso condizionale in Azure ad per indicare ad Azure ad di applicare i criteri configurati in SharePoint. Questo criterio si applica a tutti gli utenti, ma influenza solo l'accesso ai siti specificati tramite PowerShell quando si creano i controlli di accesso in SharePoint.

Per configurare questo criterio, vedere "bloccare o limitare l'accesso a specifiche raccolte siti di SharePoint o account OneDrive" in [controllare l'accesso da dispositivi non gestiti](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices).

## <a name="sharepoint-access-control-policies"></a>Criteri di controllo di accesso di SharePoint

Microsoft consiglia di proteggere il contenuto nei siti di SharePoint con contenuti sensibili e altamente regolamentati con i controlli di accesso ai dispositivi. A tale scopo, è possibile creare un criterio che specifichi il livello di protezione e i siti a cui applicare la protezione.

- Siti sensibili: Consenti accesso solo ai browser. In questo modo si impedisce agli utenti di modificare e scaricare file.
- Siti altamente regolamentati: blocca l'accesso da dispositivi non gestiti.

Vedere "bloccare o limitare l'accesso a specifiche raccolte siti di SharePoint o account di OneDrive" in [controllo accesso da dispositivi non gestiti](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices).

## <a name="how-these-policies-work-together"></a>Modalità di collaborazione tra questi criteri

È importante comprendere che le autorizzazioni per il sito di SharePoint in genere si basano sull'esigenza aziendale di accedere ai siti. Queste autorizzazioni vengono gestite dai proprietari del sito e possono essere estremamente dinamiche. L'utilizzo dei criteri di accesso ai dispositivi di SharePoint garantisce la protezione di tali siti, indipendentemente dal fatto che gli utenti siano assegnati a un gruppo di Azure AD associato a una protezione di base, sensibile o fortemente regolamentata.

Nella figura seguente viene illustrato un esempio di come i criteri di accesso ai dispositivi di SharePoint proteggono l'accesso ai siti per un utente.

[![Esempio di come i criteri di accesso ai dispositivi di SharePoint proteggono i siti](../../media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)

[Visualizzazione di una versione più grande di questa immagine](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/SharePoint-rules-scenario.png)

James dispone di criteri di accesso condizionale di base assegnati, ma può essere consentito l'accesso ai siti di SharePoint con protezione sensibile o fortemente regolamentata.

- Se James accede a un sito sensibile o altamente regolamentato, è membro dell'utilizzo del PC, il suo accesso è concesso purché il PC sia conforme.
- Se James accede a un sito sensibile che è membro dell'utilizzo del telefono non gestito, consentito per gli utenti di base, riceverà l'accesso solo ai browser al sito riservato a causa dei criteri di accesso al dispositivo configurati per il sito.
- Se James accede a un sito fortemente regolamentato, è membro dell'utilizzo del telefono non gestito, verrà bloccato a causa dei criteri di accesso configurati per il sito. Può accedere a questo sito solo utilizzando il suo PC gestito e conforme.

## <a name="next-step"></a>Passaggio successivo

![Passaggio 4: criteri per le app cloud di Microsoft 365](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

Configurare i criteri di accesso condizionale per:

- [Microsoft Teams](teams-access-policies.md)
- [Exchange Online](secure-email-recommended-policies.md)
