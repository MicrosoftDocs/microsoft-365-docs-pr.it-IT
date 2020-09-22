---
title: Domande frequenti quando si attiva Microsoft Threat Protection
description: Ottenere le risposte alle domande più frequenti sulla gestione delle licenze, delle autorizzazioni, delle impostazioni iniziali e di altri prodotti e servizi correlati all'abilitazione di Microsoft Threat Protection
keywords: domande frequenti, FAQ, GCC, introduzione, abilitare MTP, Microsoft Threat Protection, M365, sicurezza, percorso dati, autorizzazioni necessarie, idoneità licenza, pagina impostazioni
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 6b0d8d9be0cc84e61a3228f79fc14f1bfc9f8a83
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/22/2020
ms.locfileid: "48198840"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-threat-protection"></a>Domande frequenti quando si attiva Microsoft Threat Protection

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft Threat Protection

Leggere le risposte alle domande più frequenti relative all'attivazione di [Microsoft Threat Protection](microsoft-threat-protection.md), tra cui le licenze e le autorizzazioni necessarie, la distribuzione dei servizi di supporto e le impostazioni iniziali.

Per istruzioni su come abilitare il servizio, [leggere attiva Microsoft Threat Protection](mtp-enable.md).

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-threat-protection"></a>Non si dispone di una licenza Microsoft 365 E5. È ancora possibile utilizzare Microsoft Threat Protection?

I clienti con le seguenti licenze non E5 possono utilizzare Microsoft Threat Protection:

- Microsoft Defender Advanced Threat Protection
- Azure Advanced Threat Protection
- Microsoft Cloud App Security
- Protezione avanzata dalle minacce di Office 365 (piano 2)
 
Per un elenco completo delle licenze supportate, [leggere i requisiti di licenza](prerequisites.md#licensing-requirements).

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-threat-protection"></a>È necessario installare o distribuire qualsiasi cosa per iniziare a utilizzare Microsoft Threat Protection?

No, Microsoft Threat Protection consolida i dati dai servizi di sicurezza di Microsoft 365 che sono già stati distribuiti. Una volta attivati, gli eventi incidentati, di automazione e di caccia inizieranno a funzionare nell'ambito dei prodotti distribuiti. Se nessuno di questi prodotti è stato distribuito correttamente, Microsoft Threat Protection non visualizzerà alcun dato e non sarà in grado di intraprendere alcuna azione.

Per ottimizzare le esperienze di Microsoft Threat Protection, è consigliabile distribuire *tutti i* [prodotti e servizi di sicurezza di Microsoft 365](deploy-supported-services.md)supportati.

## <a name="where-does-microsoft-threat-protection-process-and-store-my-data"></a>Dove viene trattato Microsoft Threat Protection e archiviare i dati personali?
Microsoft Threat Protection seleziona automaticamente una posizione ottimale per il Data Center in cui vengono elaborati e archiviati i dati consolidati. Se si dispone di Microsoft Defender ATP, seleziona lo stesso percorso utilizzato da Microsoft Defender ATP.

>[!NOTE]
>Microsoft Defender ATP accantona automaticamente i data center dell'Unione europea (EU) quando viene attivato tramite il Centro sicurezza di Azure. Microsoft Threat Protection provisionerà automaticamente nello stesso data center dell'Unione europea per i clienti che hanno eseguito il provisioning di Microsoft Defender ATP in questo modo. 

La posizione del Data Center viene visualizzata prima e dopo il provisioning del servizio nella pagina impostazioni di Microsoft Threat Protection (**impostazioni > Microsoft Threat Protection**). Se si preferisce utilizzare un altro percorso Data Center, selezionare **serve assistenza?** nel centro sicurezza Microsoft 365 per contattare il supporto tecnico Microsoft.

## <a name="where-can-i-access-microsoft-threat-protection"></a>Dove è possibile accedere a Microsoft Threat Protection?

Microsoft Threat Protection è disponibile in Microsoft 365 Security Center. Per accedere al centro sicurezza, passare all'URL [https://security.microsoft.com](https://security.microsoft.com) .

##  <a name="what-permissions-do-i-need-to-access-microsoft-threat-protection-in-microsoft-365-security-center"></a>Quali autorizzazioni sono necessarie per accedere a Microsoft Threat Protection in Microsoft 365 Security Center?

Gli account assegnati ai seguenti ruoli di Azure Active Directory (AD) possono accedere alle funzionalità e ai dati di Microsoft Threat Protection:

- Amministratore globale
- Amministratore della sicurezza
- Operatore della sicurezza
- Ruolo con autorizzazioni di lettura globali
- Ruolo con autorizzazioni di lettura per la sicurezza

>[!NOTE]
>Le impostazioni del controllo di accesso basato sui ruoli in Microsoft Defender ATP influiscono sull'accesso ai dati. Per ulteriori informazioni, vedere [gestione dell'accesso a Microsoft Threat Protection](mtp-permissions.md).

## <a name="what-time-zone-does-microsoft-threat-protection-default-to"></a>A quale fuso orario è impostato il valore predefinito di Microsoft Threat Protection?
Per impostazione predefinita, Microsoft Threat Protection Visualizza le informazioni sull'ora nel fuso orario UTC. È possibile modificare questa impostazione per utilizzare il fuso orario locale. [Informazioni su come impostare il fuso orario](mtp-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-threat-protection-feature-and-ui-updates"></a>Come è possibile conoscere le nuove funzionalità di Microsoft Threat Protection e gli aggiornamenti dell'interfaccia utente?

Microsoft fornisce periodicamente informazioni tramite i diversi canali, tra cui:

- [Centro messaggi](../../admin/manage/message-center.md) nell'interfaccia di amministrazione di Microsoft 365
- Blogposts in [Microsoft 365 security & Compliance Tech Community](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)

Ottenere le ultime esperienze disponibili pubblicamente attivando le [funzionalità di anteprima](preview.md).

## <a name="is-microsoft-threat-protection-available-for-us-government-community-cloud-gcc-or-gcc-high"></a>Microsoft Threat Protection è disponibile per US Government Community Cloud (GCC) o GCC High?
Al momento non è disponibile.

## <a name="related-topics"></a>Argomenti correlati

- [Panoramica di Microsoft Threat Protection](microsoft-threat-protection.md)
- [Attiva Microsoft Threat Protection](mtp-enable.md).
- [Requisiti relativi alle licenze e altri prerequisiti](prerequisites.md)
- [Distribuire i servizi supportati](deploy-supported-services.md)
- [Abilitare le funzionalità di anteprima](preview.md)
