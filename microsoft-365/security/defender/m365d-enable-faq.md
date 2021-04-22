---
title: Domande frequenti sull'attivazione di Microsoft 365 Defender
description: Risposte alle domande più frequenti su licenze, autorizzazioni, impostazioni iniziali e altri prodotti e servizi correlati all'abilitazione di Microsoft 365 Defender
keywords: domande frequenti, domande frequenti, GCC, iniziare, abilitare Microsoft 365 Defender, Microsoft 365 Defender, M365, sicurezza, posizione dati, autorizzazioni necessarie, idoneità alla licenza, pagina impostazioni
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 55c1a3807fe8e28ca12f4f638c1ab2ca717523ed
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933434"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-365-defender"></a>Domande frequenti sull'attivazione di Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender

Leggere le risposte alle domande più frequenti sull'attivazione di [Microsoft 365 Defender,](microsoft-365-defender.md)incluse le licenze e le autorizzazioni necessarie, la distribuzione dei servizi di supporto e le impostazioni iniziali.

Per istruzioni su come attivare il servizio, [vedere Attivare Microsoft 365 Defender.](m365d-enable.md)

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-365-defender"></a>Non ho una licenza di Microsoft 365 E5. Posso ancora usare Microsoft 365 Defender?

I clienti con le seguenti licenze non E5 possono usare Microsoft 365 Defender:

- Microsoft Defender per endpoint
- Microsoft Defender per identità
- Microsoft Cloud App Security
- Defender per Office 365 (Piano 2)
 
Per un elenco completo delle licenze supportate, [leggere i requisiti di licenza](prerequisites.md#licensing-requirements).

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-365-defender"></a>Devo installare o distribuire qualsiasi elemento per iniziare a usare Microsoft 365 Defender?

No, Microsoft 365 Defender consolida i dati dei servizi di sicurezza di Microsoft 365 già distribuiti. Dopo l'attivazione, le esperienze di evento imprevisto, automazione ed attività di ricerca inizieranno a funzionare nell'ambito dei prodotti distribuiti. Se nessuno di questi prodotti viene distribuito correttamente, Microsoft 365 Defender non visualizza alcun dato e non è in grado di eseguire alcuna azione.

Per ottimizzare le esperienze di Microsoft 365 Defender, è consigliabile distribuire tutti i prodotti e i servizi di sicurezza [di Microsoft 365 supportati.](deploy-supported-services.md) 

## <a name="where-does-microsoft-365-defender-process-and-store-my-data"></a>Dove microsoft 365 Defender elabora e archivia i miei dati?
Microsoft 365 Defender seleziona automaticamente una posizione ottimale per il data center in cui vengono elaborati e archiviati i dati consolidati. Se hai Microsoft Defender per Endpoint, seleziona la stessa posizione usata da Defender per Endpoint.

>[!NOTE]
>Microsoft Defender for Endpoint effettua automaticamente il provisioning nei data center dell'Unione Europea (UE) quando è attivato tramite Azure Defender. Microsoft 365 Defender eseguirà automaticamente il provisioning nello stesso data center ue per i clienti che hanno effettuato il provisioning di Microsoft Defender per Endpoint in questo modo. 

La posizione del data center viene visualizzata prima e dopo il provisioning del servizio nella pagina delle impostazioni di Microsoft 365 Defender (**Impostazioni > Microsoft 365 Defender**). Se si preferisce utilizzare un'altra posizione del data center, selezionare Serve **assistenza?** nel Centro sicurezza Microsoft 365 per contattare il supporto Tecnico Microsoft.

## <a name="where-can-i-access-microsoft-365-defender"></a>Dove è possibile accedere a Microsoft 365 Defender?

Microsoft 365 Defender è disponibile nel Centro sicurezza Microsoft 365. Per accedere al Centro sicurezza, passare all'URL [https://security.microsoft.com](https://security.microsoft.com) .

##  <a name="what-permissions-do-i-need-to-access-microsoft-365-defender-in-microsoft-365-security-center"></a>Quali autorizzazioni sono necessarie per accedere a Microsoft 365 Defender nel Centro sicurezza Microsoft 365?

Gli account assegnati ai ruoli di Azure Active Directory (AD) seguenti possono accedere ai dati e alle funzionalità di Microsoft 365 Defender:

- Amministratore globale
- Amministratore della sicurezza
- Operatore della sicurezza
- Ruolo con autorizzazioni di lettura globali
- Ruolo con autorizzazioni di lettura per la sicurezza

>[!NOTE]
>Le impostazioni di controllo dell'accesso basato sui ruoli in Microsoft Defender for Endpoint influiscono sull'accesso ai dati. Per ulteriori informazioni, vedere gestione [dell'accesso a Microsoft 365 Defender](m365d-permissions.md).

## <a name="what-time-zone-does-microsoft-365-defender-default-to"></a>Qual è il fuso orario predefinito di Microsoft 365 Defender?
Per impostazione predefinita, Microsoft 365 Defender visualizza le informazioni sull'ora nel fuso orario UTC. Puoi modificare questa impostazione per usare il fuso orario locale. [Informazioni sull'impostazione del fuso orario](m365d-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-365-defender-feature-and-ui-updates"></a>Come posso ottenere informazioni sulle nuove funzionalità di Microsoft 365 Defender e sugli aggiornamenti dell'interfaccia utente?

Microsoft fornisce regolarmente informazioni attraverso i vari canali, tra cui:

- Centro [messaggi nell'interfaccia](../../admin/manage/message-center.md) di amministrazione di Microsoft 365
- Blogpost nella community tecnica sulla sicurezza di [Microsoft 365 & conformità](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)

Ottieni le esperienze più recenti disponibili pubblicamente attivando le [funzionalità di anteprima.](preview.md)

## <a name="is-microsoft-365-defender-available-for-us-government-community-cloud-gcc-or-gcc-high"></a>Microsoft 365 Defender è disponibile per US Government Community Cloud (GCC) o GCC High?
Al momento non è disponibile.

## <a name="related-topics"></a>Argomenti correlati

- [Panoramica di Microsoft 365 Defender](microsoft-365-defender.md)
- [Attivare Microsoft 365 Defender](m365d-enable.md).
- [Requisiti relativi alle licenze e altri prerequisiti](prerequisites.md)
- [Distribuire i servizi supportati](deploy-supported-services.md)
- [Attivare funzionalità di anteprima](preview.md)
