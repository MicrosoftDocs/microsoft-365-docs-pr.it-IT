---
title: Domande frequenti quando si attiva Microsoft 365 Defender
description: Ottenere le risposte alle domande più frequenti sulla gestione delle licenze, delle autorizzazioni, delle impostazioni iniziali e di altri prodotti e servizi correlati all'abilitazione di Microsoft 365 Defender
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
ms.openlocfilehash: bfb58cb043f2bc641245814c41e389ddcdbfdefa
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "48842417"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-365-defender"></a>Domande frequenti quando si attiva Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender

Leggere le risposte alle domande più frequenti relative all'attivazione di [Microsoft 365 Defender](microsoft-threat-protection.md), tra cui le licenze e le autorizzazioni necessarie, la distribuzione dei servizi di supporto e le impostazioni iniziali.

Per istruzioni su come abilitare il servizio, [leggere attiva Microsoft 365 Defender](mtp-enable.md).

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-365-defender"></a>Non si dispone di una licenza Microsoft 365 E5. È ancora possibile utilizzare Microsoft 365 Defender?

I clienti con le seguenti licenze non E5 possono utilizzare Microsoft 365 Defender:

- Microsoft Defender ATP
- Microsoft Defender per identità
- Microsoft Cloud App Security
- Difensore per Office 365 (piano 2)
 
Per un elenco completo delle licenze supportate, [leggere i requisiti di licenza](prerequisites.md#licensing-requirements).

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-365-defender"></a>È necessario installare o distribuire qualsiasi cosa per iniziare a utilizzare Microsoft 365 Defender?

No, Microsoft 365 Defender consolida i dati dai servizi di sicurezza di Microsoft 365 che sono già stati distribuiti. Una volta attivati, gli eventi incidentati, di automazione e di caccia inizieranno a funzionare nell'ambito dei prodotti distribuiti. Se nessuno di questi prodotti è stato distribuito correttamente, Microsoft 365 Defender non visualizzerà alcun dato e non sarà in grado di intraprendere alcuna azione.

Per ottimizzare le esperienze di Microsoft 365 Defender, è consigliabile distribuire *tutti i* [prodotti e servizi di sicurezza di Microsoft 365](deploy-supported-services.md)supportati.

## <a name="where-does-microsoft-365-defender-process-and-store-my-data"></a>Dove Microsoft 365 Defender elabora e archivia i dati personali?
Microsoft 365 Defender seleziona automaticamente una posizione ottimale per il Data Center in cui vengono elaborati e archiviati i dati consolidati. Se si dispone di Microsoft Defender per endpoint, viene selezionato lo stesso percorso utilizzato da Defender per endpoint.

>[!NOTE]
>Microsoft Defender per endpoint si riattiva automaticamente nei data center dell'Unione europea (EU) quando viene attivato tramite Azure Defender *. Microsoft 365 Defender provvederà alla provisioning automatico nello stesso data center EU per i clienti che hanno sottoposto a Microsoft Defender per endpoint in questo modo. 

La posizione del Data Center viene visualizzata prima e dopo il provisioning del servizio nella pagina impostazioni di Microsoft 365 Defender ( **impostazioni > microsoft 365 Defender** ). Se si preferisce utilizzare un altro percorso Data Center, selezionare **serve assistenza?** nel centro sicurezza Microsoft 365 per contattare il supporto tecnico Microsoft.

## <a name="where-can-i-access-microsoft-365-defender"></a>Dove è possibile accedere a Microsoft 365 Defender?

Microsoft 365 Defender è disponibile in Microsoft 365 Security Center. Per accedere al centro sicurezza, passare all'URL [https://security.microsoft.com](https://security.microsoft.com) .

##  <a name="what-permissions-do-i-need-to-access-microsoft-365-defender-in-microsoft-365-security-center"></a>Quali autorizzazioni sono necessarie per accedere a Microsoft 365 Defender in Microsoft 365 Security Center?

Gli account assegnati ai seguenti ruoli di Azure Active Directory (AD) possono accedere alla funzionalità e ai dati di Microsoft 365 Defender:

- Amministratore globale
- Amministratore della sicurezza
- Operatore della sicurezza
- Ruolo con autorizzazioni di lettura globali
- Ruolo con autorizzazioni di lettura per la sicurezza

>[!NOTE]
>Le impostazioni del controllo di accesso basato sui ruoli in Microsoft Defender per endpoint influiscono sull'accesso ai dati. Per ulteriori informazioni, vedere [Managing Access to Microsoft 365 Defender](mtp-permissions.md).

## <a name="what-time-zone-does-microsoft-365-defender-default-to"></a>A quale fuso orario è impostato il valore predefinito di Microsoft 365 Defender?
Per impostazione predefinita, Microsoft 365 Defender Visualizza le informazioni sull'ora nel fuso orario UTC. È possibile modificare questa impostazione per utilizzare il fuso orario locale. [Informazioni su come impostare il fuso orario](mtp-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-365-defender-feature-and-ui-updates"></a>Come è possibile conoscere le nuove funzionalità di Microsoft 365 Defender e gli aggiornamenti dell'interfaccia utente?

Microsoft fornisce periodicamente informazioni tramite i diversi canali, tra cui:

- [Centro messaggi](../../admin/manage/message-center.md) nell'interfaccia di amministrazione di Microsoft 365
- Blogposts in [Microsoft 365 security & Compliance Tech Community](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)

Ottenere le ultime esperienze disponibili pubblicamente attivando le [funzionalità di anteprima](preview.md).

## <a name="is-microsoft-365-defender-available-for-us-government-community-cloud-gcc-or-gcc-high"></a>Microsoft 365 Defender è disponibile per US Government community Cloud (GCC) o GCC High?
Al momento non è disponibile.

## <a name="related-topics"></a>Argomenti correlati

- [Panoramica di Microsoft 365 Defender](microsoft-threat-protection.md)
- [Attiva Microsoft 365 Defender](mtp-enable.md).
- [Requisiti relativi alle licenze e altri prerequisiti](prerequisites.md)
- [Distribuire i servizi supportati](deploy-supported-services.md)
- [Attivare funzionalità di anteprima](preview.md)
