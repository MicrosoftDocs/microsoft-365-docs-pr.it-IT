---
title: Criteri consigliati per la protezione dei documenti - Microsoft 365 Enterprise | Microsoft Docs
description: Descrive i criteri consigliati da Microsoft riguardo alla protezione dell'accesso ai file di SharePoint.
author: BrendaCarter
manager: laurawi
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.author: bcarter
ms.date: 06/07/2018
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.openlocfilehash: 72dd50649dba9e290d50c2831557c06db3cb7586
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2019
ms.locfileid: "26868564"
---
# <a name="policy-recommendations-for-securing-sharepoint-sites-and-files"></a>Suggerimenti di criteri per la protezione dei file e i siti di SharePoint
In questo articolo viene descritto come implementare l'identità consigliata e i criteri di accesso ai dispositivi per la protezione di SharePoint Online e OneDrive for Business. Questa guida si basa sul [dispositivo le regole di accesso e identità comuni](identity-access-policies.md). 

Queste procedure consigliate basate su tre diversi livelli di sicurezza e protezione per i file di SharePoint che possono essere applicati in base la granularità delle proprie esigenze: **linea di base**, **riservati**e **altamente regolamentato**. È possibile ulteriori informazioni su questi livelli di sicurezza e i sistemi operativi client consigliato, per fare riferimento a questi suggerimenti in [Panoramica](microsoft-365-policies-configurations.md).

Oltre all'implementazione di questa Guida, assicurarsi di configurare siti di SharePoint con la quantità di protezione, inclusa l'impostazione delle autorizzazioni appropriate per il contenuto sensibile e altamente regolamentato destra. Per ulteriori informazioni sulla creazione di siti per la protezione riservati e altamente regolamentato linea di base, vedere [file e siti di SharePoint Online sicura](https://docs.microsoft.com/office365/enterprise/secure-sharepoint-online-sites-and-files). 

## <a name="updating-common-policies-to-include-sharepoint-and-onedrive-for-business"></a>Aggiornamento dei criteri comuni per includere SharePoint e OneDrive for Business
Nel diagramma seguente illustra il set di criteri consigliati per la protezione dei file in SharePoint Online e OneDrive for Business. Indica i criteri devono essere aggiornati o appena creati per l'applicazione della protezione in SharePoint Online e OneDrive for Business.

![Riepilogo dei criteri per SharePoint Online e OneDrive](../images/identity-access-ruleset-sharepoint.png)

Se è stato incluso SharePoint Online durante la creazione di criteri comuni, è necessario creare solo i nuovi criteri. Quando si configurano le regole di accesso condizionale, SharePoint Online include OneDrive for Business.

I nuovi criteri di implementano di protezione di dispositivo per contenuti sensibili e altamente regolamentato applicando requisiti specifici di accesso ai siti di SharePoint specificato. 

Nella tabella seguente sono elencati i criteri che è necessario eseguire una revisione e l'aggiornamento o crearne uno nuovo per SharePoint Online. I criteri comuni collegamento alle istruzioni di configurazione associata nell'articolo [comuni criteri di accesso di dispositivi e identità](identity-access-policies.md) .


|Livello di protezione|Criteri|Ulteriori informazioni|
|:---------------|:-------|:----------------|
|**Protezione di base**|[È necessario MFA per i rischi di accesso impostato *su medio* o *alta*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Includere SharePoint Online all'assegnazione di applicazioni basate su cloud|
|        |[Bloccare i client che non supportano l'autenticazione moderno](identity-access-policies.md#block-clients-that-dont-support-modern-authentication)|Includere SharePoint Online all'assegnazione di applicazioni basate su cloud|
|        |[Definire criteri di protezione delle app](identity-access-policies.md#define-app-protection-policies)|Assicurarsi che tutte le app consigliate sono inclusi nell'elenco delle applicazioni. È necessario aggiornare il criterio per ogni piattaforma (iOS, Android, Windows)|
|        |[Richiedi PC Compatible](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Includere SharePoint Online nell'elenco delle applicazioni basate su cloud|
|        |[Utilizzare le restrizioni applicate app in SharePoint Online](#use-app-enforced-restrictions-in-sharepoint-online)|Aggiungere il nuovo criterio. In questo modo si comunica Azure Active Directory per utilizzare le impostazioni specificate in SharePoint Online. Questa regola si applica a tutti gli utenti, ma riguarda solo l'accesso ai siti inclusi in Criteri di accesso di SharePoint Online|
|**Dati sensibili**|[È necessario MFA per i rischi di accesso sono *bassa*, *Media* o *alta*](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Includere SharePoint Online nelle assegnazioni di applicazioni basate su cloud|
|         |[Richiedi compatibile con PC *e* dispositivi mobili](identity-access-policies.md#require-compliant-pcs-and-mobile-devices)|Includere SharePoint Online nell'elenco delle applicazioni basate su cloud|
||[Criteri di controllo di accesso SharePoint Online](#sharepoint-online-access-control-policies): consentire l'accesso solo browser specifici siti di SharePoint da dispositivi non gestiti|In tal modo, modifica e per il download dei file. Utilizzare PowerShell per specificare i siti|
|**Protezione per ambienti altamente regolamentati**|[*Sempre* richiedono MFA](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Includere SharePoint Online all'assegnazione di applicazioni basate su cloud|
||[Criteri di controllo di accesso SharePoint Online](#use-app-enforced-restrictions-in-sharepoint-online): bloccare l'accesso a siti di SharePoint specifici dai dispositivi non gestiti|Utilizzare PowerShell per specificare i siti|

## <a name="use-app-enforced-restrictions-in-sharepoint-online"></a>Utilizzare le restrizioni applicate app in SharePoint Online
Se si implementa accedere a controlli in SharePoint Online, è necessario creare questo criterio di accesso condizionale in Azure Active Directory per comunicare ai Azure Active Directory per applicare i criteri di che configurazione in SharePoint Online. Questa regola si applica a tutti gli utenti, ma solo influisce sull'accesso ai siti specificati utilizzando PowerShell quando si creano i controlli di access in SharePoint Online.

Per configurare questo Vedere criterio "bloccare o limitare l'accesso per specifiche raccolte siti di SharePoint o gli account OneDrive" in questo articolo: [controllare l'accesso dai dispositivi non gestiti](https://support.office.com/article/Control-access-from-unmanaged-devices-5ae550c4-bd20-4257-847b-5c20fb053622).


## <a name="sharepoint-online-access-control-policies"></a>Criteri di controllo di accesso SharePoint Online
È consigliabile che proteggere il contenuto nei siti di SharePoint con contenuti sensibili e altamente regolamentato con controllo di accesso di dispositivi. Questo scopo si crea un criterio che specifica il livello di protezione e applicare la protezione per i siti. 
- Siti riservati: consentire l'accesso solo browser. In questo modo si impedisce agli utenti di modifica e il download dei file.
- Altamente regolamentato siti: bloccare l'accesso dai dispositivi non gestiti.

Vedere "bloccare o limitare l'accesso per specifiche raccolte siti di SharePoint o gli account OneDrive" in questo articolo: [controllare l'accesso dai dispositivi non gestiti](https://support.office.com/article/Control-access-from-unmanaged-devices-5ae550c4-bd20-4257-847b-5c20fb053622) . 

## <a name="how-these-policies-work-together"></a>Interagiscono tra questi criteri
È importante tenere presente che le autorizzazioni del sito di SharePoint vengono in genere in base alle esigenze di business per l'accesso ai siti. Queste autorizzazioni vengono gestite dai proprietari dei siti e possono essere molto dinamiche. Utilizzando criteri di accesso di dispositivi garantisce la protezione per i siti, indipendentemente dal fatto che gli utenti vengono assegnati a un gruppo di Azure Active Directory di SharePoint associati a previsto riservata, oppure altamente regolamentato protection. 

Nella figura seguente viene fornito un esempio di come i criteri di accesso dispositivo SharePoint proteggono l'accesso ai siti.

![Criteri di accesso di dispositivi di SharePoint come proteggere i siti](../images/SharePoint-rules-scenario.png)

Nella figura:
- James viene assegnato a criteri di accesso condizionale associati a protezione previsto, ma è possibile ottenere l'accesso ai siti di SharePoint associati riservati o altamente regolamentato protection. 
- Se James accede a un sito riservato o altamente regolamentato che sia un membro di tramite il PC, il suo accesso viene concesso a condizione che il PC è compatibile con.
- James accede a un sito riservato che sia un membro di utilizzando il suo telefono non gestito, è consentita agli utenti di base, riceverà solo browser accedere al sito riservato a causa del criterio di accesso di dispositivi configurato per il sito. 
- Se James accede a un sito molto regolamentato è sia un membro del utilizzando il suo telefono non gestito, questi verranno bloccato a causa del criterio di accesso configurato per il sito. È possibile accedere solo questo sito utilizzando il suo PC gestiti e alla conformità.


<!---
##Block access to content from unmanaged devices (SharePoint admin center)
In the case of SharePoint Online, when a conditional access policy is applied to enforce Intune app protection policies, this might not apply to all applications that access SharePoint Online. Some applications, such as Exchange, have access to some SharePoint resources. For example, Exchange allows attaching SharePoint files by default. Conditional access policies applied to SharePoint Online will not restrict this access. 

To ensure baseline protection is applied uniformly, regardless of which service is accessing SharePoint Online and OneDrive for Business, configure access controls directly in SharePoint admin center. We recommend you configure the following:
- Block access from unmanaged devices. This includes devices that aren't compliant or joined to a domain. 
- Block access from app that don't use modern authentication.

See [Control access from unmanaged devices](https://support.office.com/article/Control-access-from-unmanaged-devices-5ae550c4-bd20-4257-847b-5c20fb053622).
-->



## <a name="next-steps"></a>Passaggi successivi
[Protezione di file e siti di SharePoint Online](https://docs.microsoft.com/office365/enterprise/secure-sharepoint-online-sites-and-files)
