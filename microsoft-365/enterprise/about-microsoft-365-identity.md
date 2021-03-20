---
title: Modelli di identità di Microsoft 365 e Azure Active Directory
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.date: 09/30/2020
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- M365-identity-device-management
- M365-security-compliance
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-mar2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 06a189e7-5ec6-4af2-94bf-a22ea225a7a9
description: Informazioni su come gestire il servizio di identità utente di Azure AD in Microsoft 365 usando modelli di identità solo cloud o ibridi.
ms.openlocfilehash: b54ccce6ea2a468e02d9db95e7932d847df4e64b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905705"
---
# <a name="microsoft-365-identity-models-and-azure-active-directory"></a>Modelli di identità di Microsoft 365 e Azure Active Directory

*Questo articolo può essere applicato sia a Microsoft 365 Enterprise che a Office 365 Enterprise.*

Microsoft 365 usa Azure Active Directory (Azure AD), un servizio di autenticazione e identità utente basato su cloud incluso nell'abbonamento a Microsoft 365, per gestire le identità e l'autenticazione per Microsoft 365. Configurare correttamente l'infrastruttura di identità è fondamentale per gestire l'accesso utente e le autorizzazioni di Microsoft 365 per l'organizzazione.

Prima di iniziare, guardare questo video che illustra i modelli di identità e l'autenticazione per Microsoft 365.

<p> </p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2Pjwu]

La prima scelta di pianificazione è il modello di identità di Microsoft 365.

## <a name="microsoft-365-identity-models"></a>Modelli di identità di Microsoft 365

Per pianificare gli account utente, è necessario prima di tutto conoscere i due modelli di gestione delle identità disponibili in Microsoft 365. È possibile mantenere le identità dell'organizzazione solo nel cloud. In alternativa, è possibile mantenere le identità Active Directory Domain Services (AD DS) in locale e usarle per l'autenticazione quando gli utenti accedono ai servizi cloud di Microsoft 365.  

Ecco i due tipi di identità con la descrizione dei vantaggi e dell'ambiente in cui sono più indicati.

| Attributo | Identità solo cloud | Identità ibrida |
|:-------|:-----|:-----|
| **Definizione** | L'account utente esiste solo nel tenant di Azure AD per l'abbonamento a Microsoft 365. | L'account utente esiste in AD DS, ma una copia si trova anche nel tenant di Azure AD per l'abbonamento a Microsoft 365. L'account utente in Azure AD potrebbe includere anche una versione con hash della password dell'account utente di Servizi di dominio Active Directory già con hash. |
| **Autenticazione delle credenziali utente in Microsoft 365** | Per eseguire l'autenticazione, il tenant di Azure AD per l'abbonamento a Microsoft 365 usa l'account dell'identità cloud. | Il tenant di Azure AD per l'abbonamento a Microsoft 365 gestisce il processo di autenticazione oppure reindirizza l'utente a un altro provider di identità. |
| **Indicato per** | Organizzazioni che non hanno o necessitano di un'istanza locale di AD DS. | Organizzazioni che usano AD DS o un altro provider di identità. |
| **Principale vantaggio** | Semplice da usare. Non richiede altri strumenti o server di directory. | Gli utenti possono usare le stesse credenziali per accedere a risorse locali o basate sul cloud. |
||||

## <a name="cloud-only-identity"></a>Identità solo cloud

Un'identità solo cloud usa solo gli account utente che esistono in Azure AD. L'identità solo cloud viene in genere utilizzata da organizzazioni di piccole dimensioni che non dispongono di server locali o non utilizzano Servizi di dominio Active Directory per gestire le identità locali. 

Ecco i componenti di base dell'identità solo cloud.
 
![Componenti di base dell'identità solo cloud](../media/about-microsoft-365-identity/cloud-only-identity.png)

Sia gli utenti locali che gli utenti remoti (online) usano gli account utente e le password di Azure AD per accedere ai servizi cloud di Microsoft 365. Azure AD autentica le credenziali utente in base agli account utente e alle password archiviate.

### <a name="administration"></a>Amministrazione
Poiché gli account utente sono archiviati solo in Azure AD, è possibile gestire le identità cloud con strumenti quali l'interfaccia di amministrazione di [Microsoft 365](../admin/add-users/index.yml) [e Windows PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md). 

## <a name="hybrid-identity"></a>Identità ibrida

L'identità ibrida usa gli account che provengono da un'istanza locale di AD DS e per i quali esiste una copia nel tenant di Azure AD di un abbonamento a Microsoft 365. Tuttavia, la maggior parte delle modifiche è unidirezionale. Le modifiche apportate agli account utente di AD DS vengono sincronizzate con le copie corrispondenti in Azure AD. Le modifiche apportate agli account basati sul cloud in Azure AD, ad esempio i nuovi account utente, non vengono invece sincronizzate con AD DS.

Azure AD Connect offre la sincronizzazione continua degli account. Viene eseguito in un server locale, verifica la presenza di modifiche in AD DS e invia queste modifiche ad Azure AD. Azure AD Connect consente di filtrare gli account sincronizzati e scegliere se eseguire la sincronizzazione di una versione con hash delle password utente, nota come sincronizzazione dell'hash delle password (PHS).

Durante l'implementazione dell'identità ibrida, l'istanza locale di AD DS costituisce l'origine autorevole delle informazioni sull'account. Questo significa che le attività di amministrazione vengono eseguite principalmente in locale e quindi sincronizzate con Azure AD. 

Ecco i componenti dell'identità ibrida.

![Componenti dell'identità ibrida](../media/about-microsoft-365-identity/hybrid-identity.png)

Il tenant di Azure AD contiene una copia degli account di AD DS. In questa configurazione sia gli utenti locali che gli utenti remoti che accedono ai servizi cloud di Microsoft 365 eseguono l'autenticazione in Azure AD.

>[!Note]
>È sempre necessario usare Azure AD Connect per sincronizzare gli account utenti per l'identità ibrida. Gli account utente sincronizzati in Azure AD sono necessari per l'assegnazione di licenze e la gestione dei gruppi, nonché per configurare le autorizzazioni e per altre attività amministrative che interessano gli account utente.
>

### <a name="administration"></a>Amministrazione

Poiché gli account utente originali e autorevoli sono archiviati in Servizi di dominio Active Directory locale, le identità vengono gestite con gli stessi strumenti utilizzati per gestire Servizi di dominio Active Directory. 

Non si usa l'interfaccia di amministrazione di Microsoft 365 o PowerShell per Microsoft 365 per gestire gli account utente sincronizzati in Azure AD.

## <a name="next-step"></a>Passaggio successivo

Se è necessario il modello di identità solo cloud, vedere [Identità solo cloud.](cloud-only-identities.md)

Se è necessario il modello di identità ibrido, vedere [Identità ibrida](plan-for-directory-synchronization.md).


## <a name="see-also"></a>Vedere anche

[Panoramica di Microsoft 365 Enterprise](microsoft-365-overview.md)