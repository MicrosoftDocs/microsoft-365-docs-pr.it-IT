---
title: 'Fase 4: Office 365 ProPlus'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/29/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: La procedura per distribuire l'infrastruttura di Office 365 ProPlus per Microsoft 365 Enterprise.
ms.openlocfilehash: 5c32257fb9066f170da1f1a3cfe4b865e383cfcb
ms.sourcegitcommit: 1e3916bbe94d4fbb858566e7db5018e1e46bcd0d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/23/2019
ms.locfileid: "37646401"
---
# <a name="phase-4-office-365-proplus"></a>Fase 4: Office 365 ProPlus

![Fase 4: Office 365 ProPlus](./media/deploy-foundation-infrastructure/O365proplus_icon.png)

*Questo passaggio si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise e Microsoft 365 Education*

Microsoft 365 Enterprise include Office 365 ProPlus, la versione in abbonamento di Office. Come Office 2019, Office 365 ProPlus include tutte le applicazioni di Office, che vengono installate direttamente nei dispositivi client. A differenza di Office 2019, Office 365 ProPlus viene aggiornato regolarmente con nuove funzionalità e usa un modello di gestione delle licenze basato sugli utenti, che consente di installare Office in più dispositivi. Per maggiori informazioni, vedere [Informazioni su Office 365 ProPlus nell'azienda](https://docs.microsoft.com/deployoffice/about-office-365-proplus-in-the-enterprise).

In questa fase, si distribuisce Office 365 ProPlus nei dispositivi client nell'ambito di Microsoft 365 Enterprise. Oltre a queste linee guida, consigliamo di usare [Microsoft Fastrack](https://fasttrack.microsoft.com/office) a supporto dell'implementazione. 

Se è stato già implementato Office 365 ProPlus, vedere i [criteri uscita](office365proplus-exit-criteria.md) per questa fase per assicurarsi che soddisfino le condizioni obbligatorie di Microsoft 365 Enterprise.

>[!Note]
>Per la distribuzione di Windows 10 Enterprise e Office 365 ProPlus insieme, vedere la [Centro di distribuzione desktop](desktop-deployment-center-home.md).
>

## <a name="step-1-assess-your-environment"></a>Passaggio 1: valutazione dell'ambiente

Prima di distribuire Office 365 ProPlus, seguire le istruzioni in [Valutazione dell'ambiente e dei requisiti per la distribuzione di Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/assess-office-365-proplus). La valutazione include informazioni sui requisiti, dettagli dei dispositivi client (come le architetture e lingue richieste), i requisiti di licenza, la funzionalità di rete e la compatibilità delle applicazioni. Completare la valutazione consente di prendere decisioni chiave durante la pianificazione della distribuzione.

## <a name="step-2-plan-your-deployment"></a>Passaggio 2: pianificare la distribuzione

Dopo la valutazione dell'ambiente, seguire le istruzioni in [Pianificazione della distribuzione di Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/plan-office-365-proplus) per creare un piano di distribuzione. Include le decisioni seguenti: 

- Come distribuire Office, incluso lo strumento da usare (ad esempio, System Center Configuration Manager o lo strumento di distribuzione di Office) e da dove installare Office
- Come gestire gli aggiornamenti in Office
- Quali canali di aggiornamento usare (i canali di aggiornamento di Office controllano la frequenza con cui gli utenti ricevono aggiornamenti delle funzionalità nelle proprie applicazioni Office)
- I pacchetti di installazione di Office e i gruppi di distribuzione da usare, tra cui le applicazioni di Office e le lingue che devono essere installate per determinati utenti

L'[articolo sulla pianificazione](https://docs.microsoft.com/DeployOffice/plan-office-365-proplus) include le procedure consigliate per tutte queste opzioni, tra cui la gestione della distribuzione, degli aggiornamenti, la definizione dei pacchetti di installazione e la creazione dei gruppi di distribuzione. 

## <a name="step-3-deploy"></a>Passaggio 3: distribuzione

In base al piano di distribuzione, scegliere la modalità di distribuzione:

- **[Distribuire Office 365 ProPlus con System Center Configuration Manager](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-with-system-center-configuration-manager):** gestire la distribuzione con Configuration Manager e scaricare e distribuire Office dai punti di distribuzione sulla rete

- **[Distribuire Office 365 ProPlus con lo strumento ODT dal cloud](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-from-the-cloud):** gestire la distribuzione con lo strumento ODT e installare Office nei dispositivi client direttamente dalla rete CDN di Office
 
- **[Installare autonomamente Office 365 Pro Plus dal portale Office](https://support.office.com/article/Download-and-install-or-reinstall-Office-365-or-Office-2016-on-a-PC-or-Mac-4414EAAF-0478-48BE-9C42-23ADC4716658):** gestire la distribuzione dal portale Office e far installare agli utenti Office nei propri dispositivi client direttamente dal portale

Molte organizzazioni usano una combinazione di queste opzioni per utenti diversi. Ad esempio, l'organizzazione potrebbe usare Configuration Manager per distribuire Office alla maggior parte dei propri utenti, ma consentire l'installazione autonoma a un piccolo gruppo di dipendenti che non si connettono spesso alla rete interna. 

Se l'organizzazione usa Configuration Manager, consigliamo di effettuare l'aggiornamento a Current Branch e alla versione corrente. Per ulteriori dettagli, vedere [Scelta del ramo di Configuration Manager da usare?](https://docs.microsoft.com/sccm/core/understand/which-branch-should-i-use)

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Come Microsoft esegue Microsoft 365 Enterprise

Informazioni sul modo in cui gli esperti di Microsoft [distribuiscono e gestiscono gli aggiornamenti per Office 365 ProPlus](https://www.microsoft.com/it-IT/itshowcase/deploying-and-managing-microsoft-365#primaryR7).

## <a name="how-contoso-did-microsoft-365-enterprise"></a>Come ha agito Contoso con Microsoft 365 Enterprise

Vedere come Contoso Corporation, un'azienda multinazionale fittizia ma rappresentativa, [ha distribuito Office 365 ProPlus](contoso-o365pp.md).

![Contoso Corporation](./media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a>Passaggio successivo

[Fase 365: criteri uscita dell'infrastruttura di rete di Office 365 ProPlus](office365proplus-exit-criteria.md)
