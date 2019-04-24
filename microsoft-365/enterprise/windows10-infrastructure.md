---
title: Infrastruttura di Windows 10 Enterprise per Microsoft 365 Enterprise
description: Fornisce una guida di alto livello sui passaggi necessari per distribuire Windows 10 Enterprise sui PC come parte di Microsoft 365 Enterprise.
keywords: Microsoft 365, Microsoft 365 Enterprise, Microsoft 365 Documentation, Windows 10 Enterprise, distribuzione
author: greg-lindsay
localization_priority: Normal
ms.collection: M365-modern-desktop
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 09/18/2018
ms.author: greglin
ms.openlocfilehash: 88517c6b8de95c54ee9a2e47d4545266eb198249
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "32289437"
---
# <a name="phase-3-windows-10-enterprise"></a>Fase 3: Windows 10 Enterprise

![](./media/deploy-foundation-infrastructure/win10enterprise_icon.png)

Microsoft 365 Enterprise include Windows 10 Enterprise, che offre gli strumenti per fare di più e mantenere la sicurezza. Windows 10 Enterprise:

- **È integrato per semplicità** : sfrutta la potenza del cloud per contribuire a ridurre la complessità della gestione dell'ambiente dei dispositivi IT moderni di oggi, indipendentemente dalle dimensioni.
- **Sicurezza intelligente** : è la versione più sicura di Windows mai, con funzionalità di sicurezza intelligenti progettate per collaborare per una migliore protezione dell'organizzazione.
- **Consente la creatività** e il lavoro di squadra: Sblocca la creatività e il lavoro di squadra per offrire un'esperienza più produttiva che sia gli utenti che lo ameranno.

È necessario comprendere i diversi modi in cui è possibile distribuire il sistema operativo Windows 10 e scegliere quello giusto per la propria organizzazione. A seconda dell'abbonamento a Microsoft 365 Enterprise, esistono anche servizi e funzionalità di sicurezza di Windows 10 che è necessario configurare per ottenere il massimo da Windows 10.

Windows 10 consente di abilitare questi scenari aziendali strategici per Microsoft 365 Enterprise:

- Sfruttare le conoscenze e competenze collettive consentendo alle persone di trovare, condividere ed elaborare file, informazioni e idee all'interno dell'organizzazione
- Lavorare ovunque e in qualsiasi momento in modo sicuro attraverso il proprio dispositivo, per ottenere il massimo risultato pur mantenendo flessibile lo stile di lavoro
- Fornire sicurezza, controlli e visibilità, offrendo conformità verificata nel settore agli standard globali
- Proteggere le informazioni e ridurre il rischio di perdita di dati
- Rilevare e proteggere dalle minacce esterne: monitorare, segnalare e analizzare le attività per rispondere prontamente per garantire la sicurezza organizzativa
- Proteggi gli utenti e i loro account
- Supportare l'organizzazione con privacy e conformità avanzate per soddisfare il regolamento generale sulla protezione dei dati (GDPR)
- Restare sempre aggiornati sui propri dispositivi e software desktop, riducendo i rischi per la sicurezza e ottimizzando l'efficienza IT

Per ulteriori informazioni, vedere [Trasformazione digitale tramite Microsoft 365](http://transform.microsoft.com). 

>[!Note]
>Per distribuire insieme Windows 10 Enterprise e Office 365 ProPlus e passare a un [desktop moderno](https://www.microsoft.com/microsoft-365/modern-desktop), vedere il [Centro di distribuzione desktop moderno](http://aka.ms/howtoshift).
>

## <a name="windows-10-deployment"></a>Distribuzione di Windows 10

È possibile distribuire Windows 10 Enterprise per l'organizzazione in diversi modi. Di seguito viene illustrato come configurare e distribuire un'immagine di Windows 10 Enterprise tramite questi scenari di distribuzione moderni.

| Scenario di distribuzione | Quando usarlo |
|:--- |:--- |
| [Utilizzo di System Center Configuration Manager come aggiornamento sul posto](windows10-deploy-inplaceupgrade.md) | Selezionare questa opzione se è necessario aggiornare i computer Windows 7 o Windows 8,1 alla <a href="https://aka.ms/windows-10-release-information" target="_blank">versione corrente</a> di Windows 10 Enterprise e i computer sono attualmente gestiti con <a href="https://aka.ms/introtosccm" target="_blank">System Center Configuration Manager (Current Branch)</a>. |
| [Utilizzo di Windows Autopilot](windows10-deploy-autopilot.md) | Selezionare questa opzione se si stanno configurando nuovi computer Windows che dispongono di Windows 10 Enterprise, versione 1703 o successiva preinstallata. Gli utenti finali avvierà il programma di installazione utilizzando la configurazione desiderata immettendo le proprie credenziali dell'account aziendale o dell'Istituto di istruzione. |

Se questi scenari di distribuzione non soddisfano le esigenze dell'organizzazione, è possibile conoscere altri scenari e comprendere le funzionalità e le limitazioni di ognuno negli [scenari di distribuzione di Windows 10](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios). È inoltre possibile <a href="https://aka.ms/planforwin10deployment" target="_blank">pianificare la distribuzione di Windows 10</a> autonomamente.

Per ulteriori informazioni su Windows 10, vedere gli articoli seguenti:

- [Pagina del prodotto Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise)
- [Windows 10](https://docs.microsoft.com/windows/windows-10)
- [Distribuire e aggiornare Windows 10](https://docs.microsoft.com/windows/deployment/)


## <a name="additional-services-and-features"></a>Servizi e funzionalità aggiuntivi
Nell'ambito della distribuzione di Windows 10 Enterprise, è possibile aggiungere questi servizi e funzionalità aggiuntivi.

### <a name="windows-analytics"></a>Windows Analytics

Windows utilizza i dati di diagnostica per fornire informazioni dettagliate, utili per ottenere approfondimenti sull'efficienza operativa e sull'integrità dei dispositivi Windows 10 nel proprio ambiente.

* Preparazione per l'aggiornamento: la preparazione all'aggiornamento consente di passare a Windows 10 e di rimanere aggiornati con i nuovi aggiornamenti delle funzionalità di Windows 10. 
* Update Compliance-la conformità degli aggiornamenti è destinata all'amministratore IT che desidera ottenere una visione olistica di tutti i dispositivi Windows 10, senza ulteriori requisiti di infrastruttura.
* Integrità del dispositivo: è possibile utilizzare l'integrità del dispositivo per rilevare e correggere in modo proattivo i problemi di impatto dell'utente finale.

Per ulteriori informazioni, vedere [Panoramica di Windows Analytics](https://docs.microsoft.com/windows/deployment/update/windows-analytics-overview) .

### <a name="windows-security"></a>Sicurezza di Windows

Windows 10 fornisce funzionalità che consentono di proteggere le minacce, la protezione dei dispositivi e la guida per il controllo di accesso. Con Windows 10, è possibile ottenere funzionalità di sicurezza critiche che proteggono il dispositivo fin dall'inizio. Microsoft 365 E3 aggiunge funzionalità di sicurezza quali Windows Hello for business, Windows Defender Application Control e Windows Information Protection. Con Microsoft 365 E5, è possibile ottenere tutta la protezione da Microsoft 365 E3 Security Plus cloud-based Security features e Windows Defender Advanced Threat Protection. 

Per ulteriori informazioni sulle funzionalità di sicurezza disponibili con Windows 10 Enterprise e su come è possibile distribuire, gestire, configurare e risolvere i problemi relativi a tre funzionalità di ecurity principali, vedere [passaggio 5: distribuire le funzionalità di sicurezza di Windows 10 Enterprise](windows10-enable-security-features.md).

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Come Microsoft esegue Microsoft 365 Enterprise

Per sbirciare all'interno di Microsoft e scoprire in che modo la società ha pianificato, distribuito e gestisce gli aggiornamenti per Windows 10, vedere:

- [Preparazione dell'organizzazione per una distribuzione semplice di Windows 10](https://www.microsoft.com/itshowcase/windows10deployment?wt.mc_id=bmkg_itsc)
- [Adozione di Windows as a Service in Microsoft](https://www.microsoft.com/itshowcase/Article/Content/851/Adopting-Windows-as-a-service-at-Microsoft)
- [Distribuzione di Windows 10 in Microsoft come aggiornamento sul posto](https://www.microsoft.com/itshowcase/Article/Content/668/Deploying-Windows-10-at-Microsoft-as-an-inplace-upgrade)
- [Implementazione dell'autenticazione utente avanzata con Windows Hello for Business](https://www.microsoft.com/itshowcase/Article/Content/756/Implementing-strong-user-authentication-with-Windows-Hello-for-Business)
- [Distribuzione di Windows 10: suggerimenti e consigli da IT Microsoft](https://www.microsoft.com/itshowcase/Article/Content/951/Windows-10-deployment-tips-and-tricks-from-Microsoft-IT) (video)
- [Windows Defender ATP consente di individuare le minacce avanzate](https://www.microsoft.com/itshowcase/Article/Content/854/Windows-Defender-ATP-helps-detect-sophisticated-threats)
- [Protezione dell'azienda moderna con Windows Defender e Windows Defender ATP](https://www.microsoft.com/itshowcase/Article/Content/903/Securing-the-modern-enterprise-with-Windows-Defender-and-Windows-Defender-ATP) (video)

## <a name="how-contoso-did-microsoft-365-enterprise"></a>Come ha agito Contoso con Microsoft 365 Enterprise

Vedere come Contoso Corporation, un'azienda multinazionale fittizia ma rappresentativa, ha [distribuito Windows 10 Enterprise](contoso-win10.md).

![](./media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a>Passaggio successivo

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)| [Preparare l'organizzazione per Windows 10 Enterprise](windows10-prepare-your-org.md) |
