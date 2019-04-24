---
title: 'Fase 4: Office 365 ProPlus'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/18/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-modern-desktop
- Strat_O365_Enterprise
ms.custom: ''
description: La procedura per distribuire l'infrastruttura di Office 365 ProPlus per Microsoft 365 Enterprise.
ms.openlocfilehash: c4fc3805dd2ea97e1a9797e5adfc31ab83f028ae
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32290945"
---
# <a name="phase-4-office-365-proplus"></a>Fase 4: Office 365 ProPlus

![](./media/deploy-foundation-infrastructure/O365proplus_icon.png)

*Questo passaggio si applica alle versioni E3 ed E5 di Microsoft 365 Enterprise e Microsoft 365 Education*

Microsoft 365 Enterprise include Office 365 ProPlus, la versione in abbonamento di Office. Come Office 2016, Office 365 ProPlus include tutte le applicazioni di Office e quelle applicazioni installate direttamente nel dispositivo client. A differenza di Office 2016, Office 365 ProPlus viene aggiornato con nuove funzionalità a intervalli regolari e contiene un modello di gestione delle licenze basato sull'utente che consente alle persone di installare Office in un numero massimo di 5 dispositivi. Per ulteriori informazioni, vedere [Informazioni su Office 365 ProPlus nell'azienda](https://docs.microsoft.com/deployoffice/about-office-365-proplus-in-the-enterprise).

In questa fase, si distribuisce Office 365 ProPlus nei dispositivi client nell'ambito di Microsoft 365 Enterprise. Oltre a queste linee guida, consigliamo di usare [Microsoft Fastrack](https://fasttrack.microsoft.com/office) a supporto dell'implementazione. 

Office 365 ProPlus consente i seguenti scenari aziendali per Microsoft 365 Enterprise:

- Collaborare su documenti in tempo reale e non, per semplificare il processo di cooperazione
- Sfruttare le conoscenze e competenze collettive consentendo alle persone di trovare, condividere ed elaborare file, informazioni e idee all'interno dell'organizzazione
- Consentire agli utenti di trasformare i processi aziendali e aumentare l'efficienza
- Gestire progetti, attività e scadenze per soddisfare gli obiettivi di business
- Usufruire di assistenza intelligente per la progettazione, la scrittura, la ricerca di contenuti e molto altro, incrementando l'efficienza del proprio lavoro
- Trovare approfondimenti, analizzare dati e condividere i risultati per consentire a tutti di compiere decisioni basate su informazioni aggiornate
- Comunicare con il team per restare aggiornati, sollecitare input e creare coesione e consenso
- Comunicare con partner, colleghi e clienti in tutto il mondo, per chiamate ad hoc e pianificate e riunioni online con gruppi di qualsiasi dimensione
- Archiviare e condividere file all'interno e all'esterno dell'organizzazione per collaborare facilmente nell'organizzazione
- Lavorare ovunque e in qualsiasi momento in modo sicuro attraverso il proprio dispositivo, per ottenere il massimo risultato pur mantenendo flessibile lo stile di lavoro
- Fornire sicurezza, controlli e visibilità, offrendo conformità verificata nel settore agli standard globali
- Proteggere le informazioni e ridurre il rischio di perdita di dati
- Restare sempre aggiornati sui propri dispositivi e software desktop, riducendo i rischi per la sicurezza e ottimizzando l'efficienza IT

Per ulteriori informazioni, vedere [Trasformazione digitale tramite Microsoft 365](http://transform.microsoft.com). 

Se è stato già implementato Office 365 ProPlus, vedere i [criteri uscita](office365proplus-exit-criteria.md) per questa fase per assicurarsi che soddisfino le condizioni obbligatorie di Microsoft 365 Enterprise.

>[!Note]
>Per distribuire insieme Windows 10 Enterprise e Office 365 ProPlus e passare a un [desktop moderno](https://www.microsoft.com/microsoft-365/modern-desktop), vedere il [Centro di distribuzione desktop moderno](http://aka.ms/howtoshift).
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

In base al piano di distribuzione del passaggio 2, scegliere la modalità di distribuzione:

- **[Distribuire Office 365 ProPlus con System Center Configuration Manager](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-with-system-center-configuration-manager):** gestire la distribuzione con Configuration Manager e scaricare e distribuire Office dai punti di distribuzione sulla rete

- **[Distribuire Office 365 ProPlus con lo strumento ODT dal cloud](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-from-the-cloud):** gestire la distribuzione con lo strumento ODT e installare Office nei dispositivi client direttamente dalla rete CDN di Office
 
- **[Distribuire Office 365 ProPlus con lo strumento ODT da un'origine locale](https://docs.microsoft.com/deployoffice/deploy-office-365-proplus-from-a-local-source):** gestire la distribuzione con lo strumento ODT e scaricare e distribuire Office da un'origine locale sulla rete 

- **[Installare autonomamente Office 365 Pro Plus dal portale Office](https://support.office.com/article/Download-and-install-or-reinstall-Office-365-or-Office-2016-on-a-PC-or-Mac-4414EAAF-0478-48BE-9C42-23ADC4716658):** gestire la distribuzione dal portale Office e far installare agli utenti Office nei propri dispositivi client direttamente dal portale

Molte organizzazioni usano una combinazione di queste opzioni per utenti diversi. Ad esempio, l'organizzazione potrebbe usare Configuration Manager per distribuire Office alla maggior parte dei propri utenti, ma consentire l'installazione autonoma a un piccolo gruppo di dipendenti che non si connettono spesso alla rete interna. 

Se l'organizzazione usa Configuration Manager, consigliamo di effettuare l'aggiornamento a Current Branch e alla versione corrente. Per ulteriori dettagli, vedere [Scelta del ramo di Configuration Manager da usare?](https://docs.microsoft.com/sccm/core/understand/which-branch-should-i-use)

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Come Microsoft esegue Microsoft 365 Enterprise

Informazioni su come gli esperti di Microsoft hanno pianificato e implementato Office 365 ProPlus in Microsoft 365 Enterprise con queste risorse:

- [Distribuzione e aggiornamento di Microsoft Office 365 ProPlus](https://www.microsoft.com/itshowcase/Article/Content/757/Deploying-and-updating-Microsoft-Office-365-ProPlus)
- [Automazione e aggiornamento dei canali per supportare la distribuzione di Microsoft Office 365 ProPlus](https://www.microsoft.com/itshowcase/Article/Content/794/Automation-and-update-channels-help-deploy-Microsoft-Office-365-ProPlus) (video)

## <a name="how-contoso-did-microsoft-365-enterprise"></a>Come ha agito Contoso con Microsoft 365 Enterprise

Vedere come Contoso Corporation, un'azienda multinazionale fittizia ma rappresentativa, [ha distribuito Office 365 ProPlus](contoso-o365pp.md).

![](./media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a>Passaggio successivo

[Fase 365: criteri uscita dell'infrastruttura di rete di Office 365 ProPlus](office365proplus-exit-criteria.md)
