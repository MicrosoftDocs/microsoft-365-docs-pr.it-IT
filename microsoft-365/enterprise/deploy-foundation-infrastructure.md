---
title: Infrastruttura di base di Microsoft 365 Enterprise
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 06/27/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Comprendere le fasi principali della distribuzione dell'infrastruttura di base per Microsoft 365 Enterprise all'interno dell'organizzazione.
ms.openlocfilehash: abc38dc0eb3d33f7af9e2c91f020a735cf0c8d96
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868278"
---
# <a name="microsoft-365-enterprise-foundation-infrastructure"></a>Infrastruttura di base di Microsoft 365 Enterprise

Per trarre vantaggi da Microsoft 365 Enterprise, iniziare la distribuzione con la sua infrastruttura di base. 

## <a name="foundation-infrastructure-for-deploying-microsoft-365-enterprise"></a>Infrastruttura di base per la distribuzione di Microsoft 365 Enterprise

L'infrastruttura di base è la base da cui è possibile distribuire i carichi di lavoro per la produttività (come Exchange Online e Microsoft Teams in Office 365) e scenari (come una migrazione a Microsoft 365 e aggiornamenti client automatizzati). Fornisce sicurezza e integrazione intelligenti che semplificano la gestione continuativa, garantendo che il software client sia aggiornato con i miglioramenti più recenti relativi a produttività e sicurezza.

Per pianificare e distribuire l'infrastruttura di base di Microsoft 365 Enterprise all'interno dell'organizzazione si usano le seguenti fasi:

|||
|:-------|:-----|
|![](./media/deploy-foundation-infrastructure/networking_icon-small.png)|[Fase 1: rete](networking-infrastructure.md)|
|![](./media/deploy-foundation-infrastructure/identity_icon-small.png)|[Fase 2: identità](identity-infrastructure.md)|
|![](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)|[Fase 3: Windows 10 Enterprise](windows10-infrastructure.md)|
|![](./media/deploy-foundation-infrastructure/O365proplus_icon-small.png)|[Fase 4: Office 365 ProPlus](office365proplus-infrastructure.md)|
|![](./media/deploy-foundation-infrastructure/mobiledevicemgmt_icon-small.png)|[Fase 5: gestione dei dispositivi mobili](mobility-infrastructure.md)|
|![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)|[Fase 6: protezione delle informazioni](infoprotect-infrastructure.md)|


Prima di uscire da ogni fase, è necessario esaminare i relativi criteri uscita, ovvero un insieme di condizioni necessarie che è necessario soddisfare e di condizioni facoltative da prendere in considerazione. I criteri uscita di ogni fase garantiscono che l'infrastruttura cloud e locale e la risultante configurazione end-to-end soddisfino i requisiti di una distribuzione Microsoft 365 Enterprise.

Guardare questo breve video sul funzionamento del contenuto dell'infrastruttura di base.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE23VRG]

La figura seguente mostra l'infrastruttura di base nel contenuto della distribuzione generale di Microsoft 365 Enterprise e il relativo percorso.

![](./media/deploy-foundation-infrastructure/m365-deploy-content-arch-foundation.png)

## <a name="fasttrack"></a>FastTrack

FastTrack è un vantaggio continuo e ripetibile, disponibile come parte dell'abbonamento, fornito dai tecnici Microsoft per consentire di passare al cloud secondo le proprie tempistiche. FastTrack inoltre offre l'accesso a partner qualificati per servizi aggiuntivi, in base alle proprie esigenze. Con al momento oltre 40.000 utenti abilitati, FastTrack consente di massimizzare il ROI, di accelerare la distribuzione e di aumentare l'adozione all'interno dell'organizzazione. Vedere [FastTrack per Microsoft 365](https://fasttrack.microsoft.com/microsoft365). 

Se si desidera sfruttare FastTrack per la distribuzione di Microsoft 365 Enterprise, è possibile usare l'[assistente distribuzione di Microsoft 365](https://aka.ms/microsoft365setupguide) di FastTrack per indicazioni su come distribuire e configurare l'infrastruttura di base. Per accedere a questa pagina è necessario essere connesso come amministratore globale in un tenant di Office 365 o Microsoft 365.

## <a name="next-step"></a>Passaggio successivo

Se si dispone dell'infrastruttura per Office 365, Enterprise Mobility + Security o Windows 10 Enterprise, vedere [Distribuzione di Microsoft 365 Enterprise con l'infrastruttura esistente](deploy-with-existing-infrastructure.md). In questo articolo vengono descritti i passaggi dei criteri uscita di ogni fase. Con queste informazioni, è possibile determinare più rapidamente cosa è necessario cambiare per rendere l'infrastruttura IT conforme a Microsoft 365 Enterprise.

In caso contrario, è possibile iniziare la distribuzione end-to-end di Microsoft 365 Enterprise da [Fase 1: rete](networking-infrastructure.md).