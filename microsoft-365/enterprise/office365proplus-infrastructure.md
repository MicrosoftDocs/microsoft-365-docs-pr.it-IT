---
title: 'Fase 4: Microsoft 365 Apps for enterprise'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: I passaggi per distribuire l'infrastruttura di Microsoft 365 Apps for enterprise per Microsoft 365 Enterprise.
ms.openlocfilehash: fe29b8025a8ccf5babf2c52cd62ebc72860a8a5c
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631430"
---
# <a name="phase-4-microsoft-365-apps-for-enterprise"></a>Fase 4: Microsoft 365 Apps for enterprise

![Fase 4: Microsoft 365 Apps for enterprise](../media/deploy-foundation-infrastructure/O365proplus_icon.png)

*Questo passaggio si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise e Microsoft 365 Education*

Microsoft 365 Enterprise include Microsoft 365 Apps for enterprise, la versione in abbonamento di Office. Come Office 2019, Microsoft 365 Apps for enterprise include tutte le applicazioni di Office, che vengono installate direttamente nei dispositivi client. A differenza di Office 2019, Microsoft 365 Apps for enterprise viene aggiornato regolarmente con nuove funzionalità e usa un modello di gestione delle licenze basato sugli utenti, che consente di installare Office in più dispositivi. Per saperne di più consultare le [informazioni su Microsoft 365 Apps for enterprise nell'impresa](https://docs.microsoft.com/deployoffice/about-office-365-proplus-in-the-enterprise).

In questa fase, si distribuisce Microsoft 365 Apps for enterprise nei dispositivi client nell'ambito di Microsoft 365 Enterprise. Oltre a queste linee guida, consigliamo di usare [Microsoft Fastrack](https://fasttrack.microsoft.com/office) a supporto dell'implementazione. 

Se è stato già implementato Microsoft 365 Apps for enterprise, vedere i [criteri uscita](office365proplus-exit-criteria.md) per questa fase per assicurarsi che soddisfino le condizioni obbligatorie di Microsoft 365 Enterprise.

>[!Note]
>Per la distribuzione di Windows 10 Enterprise e Microsoft 365 Apps for enterprise insieme, vedere il [Centro di distribuzione desktop](desktop-deployment-center-home.md).
>

## <a name="step-1-assess-your-environment"></a>Passaggio 1: valutazione dell'ambiente

Prima di distribuire Microsoft 365 Apps for enterprise, seguire le istruzioni in [Valutazione dell'ambiente e dei requisiti per la distribuzione di Microsoft 365 Apps for enterprise](https://docs.microsoft.com/DeployOffice/assess-office-365-proplus). La valutazione include informazioni sui requisiti, dettagli dei dispositivi client (come le architetture e lingue richieste), i requisiti di licenza, la funzionalità di rete e la compatibilità delle applicazioni. Completare la valutazione consente di prendere decisioni chiave durante la pianificazione della distribuzione.

## <a name="step-2-plan-your-deployment"></a>Passaggio 2: pianificare la distribuzione

Dopo la valutazione dell'ambiente, seguire le istruzioni in [Pianificazione della distribuzione di Microsoft 365 Apps for enterprise](https://docs.microsoft.com/DeployOffice/plan-office-365-proplus) per creare un piano di distribuzione. Include le decisioni seguenti: 

- Come distribuire Office, incluso lo strumento da usare (ad esempio, Microsoft Endpoint Configuration Manager o lo strumento di distribuzione di Office) e da dove installare Office
- Come gestire gli aggiornamenti in Office
- Quali canali di aggiornamento usare (i canali di aggiornamento di Office controllano la frequenza con cui gli utenti ricevono aggiornamenti delle funzionalità nelle proprie applicazioni Office)
- I pacchetti di installazione di Office e i gruppi di distribuzione da usare, tra cui le applicazioni di Office e le lingue che devono essere installate per determinati utenti

L'[articolo sulla pianificazione](https://docs.microsoft.com/DeployOffice/plan-office-365-proplus) include le procedure consigliate per tutte queste opzioni, tra cui la gestione della distribuzione, degli aggiornamenti, la definizione dei pacchetti di installazione e la creazione dei gruppi di distribuzione. 

## <a name="step-3-deploy"></a>Passaggio 3: distribuzione

In base al piano di distribuzione, scegliere la modalità di distribuzione:

- **[Distribuire Microsoft 365 Apps for enterprise con Configuration Manager](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-with-system-center-configuration-manager):** gestire la distribuzione con Configuration Manager e scaricare e distribuire Office dai punti di distribuzione sulla rete

- **[Distribuire Microsoft 365 Apps for enterprise con lo strumento ODT dal cloud](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-from-the-cloud):** gestire la distribuzione con lo strumento ODT e installare Office nei dispositivi client direttamente dalla rete CDN di Office
 
- **[Installare autonomamente Microsoft 365 Apps for enterprise dal portale Office](https://docs.microsoft.com/deployoffice/manage-software-download-settings-office-365):** gestire la distribuzione dal portale Office e far installare agli utenti Office nei propri dispositivi client direttamente dal portale

Molte organizzazioni usano una combinazione di queste opzioni per utenti diversi. Ad esempio, l'organizzazione potrebbe usare Configuration Manager per distribuire Office alla maggior parte dei propri utenti, ma consentire l'installazione autonoma a un piccolo gruppo di dipendenti che non si connettono spesso alla rete interna. 

Se l'organizzazione usa Configuration Manager, consigliamo di effettuare l'aggiornamento a Current Branch e alla versione corrente. Per ulteriori dettagli, vedere [Scelta del ramo di Configuration Manager da usare?](https://docs.microsoft.com/configmgr/core/understand/which-branch-should-i-use)

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Come Microsoft esegue Microsoft 365 Enterprise

Informazioni sul modo in cui gli esperti di Microsoft [distribuiscono e gestiscono gli aggiornamenti per Microsoft 365 Apps for enterprise](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR7).

## <a name="how-contoso-did-microsoft-365-enterprise"></a>Come ha agito Contoso con Microsoft 365 Enterprise

Vedere come Contoso Corporation, un'azienda multinazionale fittizia ma rappresentativa, [ha distribuito Microsoft 365 Apps for enterprise](contoso-o365pp.md).

![Contoso Corporation](../media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a>Passaggio successivo

[Criteri di uscita dall'infrastruttura per Microsoft 365 Apps for enterprise](office365proplus-exit-criteria.md)
