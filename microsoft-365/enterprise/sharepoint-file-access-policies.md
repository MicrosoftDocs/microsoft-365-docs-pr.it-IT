---
title: Criteri consigliati per la protezione dei documenti - Microsoft 365 Enterprise | Microsoft Docs
description: Descrive i criteri consigliati da Microsoft riguardo alla protezione dell'accesso ai file di SharePoint.
author: BrendaCarter
manager: laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: bcarter
ms.date: 06/07/2018
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.openlocfilehash: 784a4d617d74916ae7b0ec4b431cc298ce45531e
ms.sourcegitcommit: d6b641d0ef92f4176da9f4a98d3d5aa3d4f2e184
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/11/2020
ms.locfileid: "46617187"
---
# <a name="policy-recommendations-for-securing-sharepoint-sites-and-files"></a>Suggerimenti sui criteri per la protezione di siti e file di SharePoint

In questo articolo viene descritto come implementare i criteri di identità e accesso ai dispositivi consigliati per la protezione di SharePoint Online e OneDrive for business. Queste linee guida si basano sui [criteri comuni di identità e accesso ai dispositivi](identity-access-policies.md).

Questi suggerimenti si basano su tre diversi livelli di sicurezza e protezione per i file di SharePoint che possono essere applicati in base alla granularità delle proprie esigenze: **linea di base**, **sensibile**e **altamente regolamentata**. È possibile ottenere ulteriori informazioni su questi livelli di sicurezza e sui sistemi operativi client consigliati, a cui si fa riferimento in questa [sezione](microsoft-365-policies-configurations.md).

Oltre all'implementazione di queste linee guida, assicurarsi di configurare i siti di SharePoint con la giusta quantità di protezione, tra cui l'impostazione delle autorizzazioni appropriate per i contenuti sensibili e altamente regolamentati.

## <a name="updating-common-policies-to-include-sharepoint-and-onedrive-for-business"></a>Aggiornamento dei criteri comuni per includere SharePoint e OneDrive for business

Nel diagramma seguente viene illustrato il set di criteri consigliati per la protezione dei file in SharePoint Online e OneDrive for business. Indica quali criteri devono essere aggiornati o creati di nuovo per aggiungere protezione per SharePoint Online e OneDrive for business.

[![Riepilogo dei criteri per SharePoint Online e OneDrive ](../media/identity-access-ruleset-sharepoint.png)](../media/identity-access-ruleset-sharepoint.png#lightbox)

Se è stato incluso SharePoint Online quando sono stati creati i criteri comuni, è necessario creare solo i nuovi criteri. Quando si configurano le regole di accesso condizionale, SharePoint Online include OneDrive for business.

I nuovi criteri implementano la protezione del dispositivo per soddisfare sensibili e altamente regolamentati applicando specifici requisiti di accesso ai siti di SharePoint specificati.

Nella tabella seguente sono elencati i criteri che è necessario rivedere e aggiornare o creare nuovi per SharePoint Online. I criteri comuni collegano le istruzioni di configurazione associate nell'articolo [Common Identity and Device Access Policies](identity-access-policies.md) .

|Livello di protezione|Criteri|Altre informazioni|
|:---------------|:-------|:----------------|
|**Protezione di base**|[Richiedere l'AMF quando il rischio di accesso è *medio* o *elevato*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Includere SharePoint Online nell'assegnazione delle app Cloud|
|        |[Bloccare i client che non supportano l'autenticazione moderna](identity-access-policies.md#block-clients-that-dont-support-modern-authentication)|Includere SharePoint Online nell'assegnazione delle app Cloud|
|        |[Applicare i criteri di protezione dei dati dell'APP](identity-access-policies.md#apply-app-data-protection-policies)|Assicurarsi che tutte le app consigliate siano incluse nell'elenco delle app. Assicurarsi di aggiornare i criteri per ogni piattaforma (iOS, Android, Windows)|
|        |[Richiedere computer conformi](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Includere SharePoint Online nell'elenco delle app Cloud|
|        |[Utilizzare le restrizioni applicate dalle app in SharePoint Online](#use-app-enforced-restrictions-in-sharepoint-online)|Aggiungere il nuovo criterio. Questo indica ad Azure ad di utilizzare le impostazioni specificate in SharePoint Online. Questa regola si applica a tutti gli utenti, ma influenza solo l'accesso ai siti inclusi nei criteri di accesso di SharePoint Online|
|**Sensibili**|[Richiedere l'AMF quando il rischio di accesso è *basso*, *medio* o *alto*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Includere SharePoint Online nelle assegnazioni delle app Cloud|
|         |[Richiedere PC conformi *e* dispositivi mobili](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|Includere SharePoint Online nell'elenco delle app Cloud|
||[Criteri di controllo dell'accesso di SharePoint Online](#sharepoint-online-access-control-policies): Consenti l'accesso solo ai browser a siti di SharePoint specifici da dispositivi non gestiti|In questo modo si impedisce la modifica e il download dei file. Utilizzo di PowerShell per specificare i siti|
|**Riservatezza elevata**|[Richiede *sempre* l'autenticazione Master](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Includere SharePoint Online nell'assegnazione delle app Cloud|
||[Criteri di controllo dell'accesso di SharePoint Online](#use-app-enforced-restrictions-in-sharepoint-online): bloccare l'accesso a siti di SharePoint specifici da dispositivi non gestiti|Utilizzo di PowerShell per specificare i siti|

## <a name="use-app-enforced-restrictions-in-sharepoint-online"></a>Utilizzare le restrizioni applicate dalle app in SharePoint Online

Se si implementano i controlli di accesso in SharePoint Online, è necessario creare questo criterio di accesso condizionale in Azure ad per indicare ad Azure ad di applicare i criteri configurati in SharePoint Online. Questa regola si applica a tutti gli utenti, ma influenza solo l'accesso ai siti specificati tramite PowerShell quando si creano i controlli di accesso in SharePoint Online.

Per configurare questo criterio, vedere "bloccare o limitare l'accesso a specifiche raccolte siti di SharePoint o account OneDrive" in questo articolo: [controllare l'accesso da dispositivi non gestiti](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices).

## <a name="sharepoint-online-access-control-policies"></a>Criteri di controllo dell'accesso di SharePoint Online

Microsoft consiglia di proteggere il contenuto nei siti di SharePoint con contenuti sensibili e altamente regolamentati con i controlli di accesso ai dispositivi. A tale scopo, è possibile creare un criterio che specifichi il livello di protezione e i siti a cui applicare la protezione.

- Siti sensibili: Consenti accesso solo ai browser. In questo modo si impedisce agli utenti di modificare e scaricare file.
- Siti altamente regolamentati: blocca l'accesso da dispositivi non gestiti.

Vedere "bloccare o limitare l'accesso a specifiche raccolte siti di SharePoint o account OneDrive" in questo articolo: [controllare l'accesso da dispositivi non gestiti](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices).

## <a name="how-these-policies-work-together"></a>Modalità di collaborazione tra questi criteri

È importante comprendere che le autorizzazioni per il sito di SharePoint in genere si basano sull'esigenza aziendale di accedere ai siti. Queste autorizzazioni vengono gestite dai proprietari del sito e possono essere estremamente dinamiche. L'utilizzo dei criteri di accesso ai dispositivi di SharePoint garantisce la protezione di tali siti, indipendentemente dal fatto che gli utenti siano assegnati a un gruppo di Azure AD associato a una protezione di base, sensibile o fortemente regolamentata.

Nella figura seguente viene illustrato un esempio di come i criteri di accesso ai dispositivi di SharePoint proteggono l'accesso ai siti.

[![Come i criteri di accesso ai dispositivi di SharePoint proteggono siti ](../media/SharePoint-rules-scenario.png)](../media/SharePoint-rules-scenario.png#lightbox)

Nella figura:

- James viene assegnato ai criteri di accesso condizionale associati alla protezione di base, ma può essere consentito l'accesso ai siti di SharePoint associati a una protezione sensibile o fortemente regolamentata.
- Se James accede a un sito sensibile o altamente regolamentato, è membro dell'utilizzo del PC, il suo accesso è concesso purché il PC sia conforme.
- Se James accede a un sito sensibile che è membro dell'utilizzo del telefono non gestito, consentito per gli utenti di base, riceverà l'accesso solo ai browser al sito riservato a causa dei criteri di accesso al dispositivo configurati per il sito.
- Se James accede a un sito fortemente regolamentato, è membro dell'utilizzo del telefono non gestito, verrà bloccato a causa dei criteri di accesso configurati per il sito. Può accedere a questo sito solo utilizzando il suo PC gestito e conforme.


