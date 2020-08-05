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
ms.date: 08/28/2019
f1.keywords:
- NOCSH
ms.author: greglin
ms.openlocfilehash: 3b4a0174e96fec1591bcac7ba58bcc7d57db8c87
ms.sourcegitcommit: 89178b8f20d59ca88cfca303a13062b91fbeae9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/04/2020
ms.locfileid: "46552687"
---
# <a name="phase-3-windows-10-enterprise"></a>Fase 3: Windows 10 Enterprise

![Fase 3: Windows 10 Enterprise](../media/deploy-foundation-infrastructure/win10enterprise_icon.png)

Microsoft 365 Enterprise include Windows 10 Enterprise, che offre gli strumenti per fare di più e mantenere la sicurezza. Windows 10 Enterprise:

- **È integrato per semplicità** : sfrutta la potenza del cloud per contribuire a ridurre la complessità della gestione dell'ambiente dei dispositivi IT moderni di oggi, indipendentemente dalle dimensioni.
- **Sicurezza intelligente** : è la versione più sicura di Windows mai, con funzionalità di sicurezza intelligenti progettate per collaborare per una migliore protezione dell'organizzazione.
- **Consente la creatività** e il lavoro di squadra: Sblocca la creatività e il lavoro di squadra per offrire un'esperienza più produttiva che sia gli utenti che lo ameranno.

È necessario comprendere i diversi modi in cui è possibile distribuire il sistema operativo Windows 10 e scegliere quello giusto per la propria organizzazione. A seconda dell'abbonamento a Microsoft 365 Enterprise, esistono anche servizi e funzionalità di sicurezza di Windows 10 che è necessario configurare per ottenere il massimo da Windows 10.

>[!Note]
>Per distribuire insieme le app di Windows 10 Enterprise e Microsoft 365 per l'organizzazione e passare a un [desktop moderno](https://www.microsoft.com/microsoft-365/modern-desktop), vedere il [centro di distribuzione desktop moderno](https://aka.ms/howtoshift).
>

## <a name="windows-10-deployment"></a>Distribuzione di Windows 10

È possibile distribuire Windows 10 Enterprise per l'organizzazione in diversi modi. Di seguito viene illustrato come configurare e distribuire un'immagine di Windows 10 Enterprise tramite questi scenari di distribuzione moderni.

| Scenario di distribuzione | Quando usarlo |
|:--- |:--- |
| [Utilizzo di Microsoft endpoint Configuration Manager come aggiornamento sul posto](windows10-deploy-inplaceupgrade.md) | Selezionare questa opzione se è necessario aggiornare i computer Windows 7 o Windows 8,1 alla <a href="https://aka.ms/windows-10-release-information" target="_blank">versione corrente</a> di Windows 10 Enterprise e i computer sono attualmente gestiti con <a href="https://docs.microsoft.com/mem/configmgr/core/understand/introduction" target="_blank">Configuration Manager (Current Branch)</a>. |
| [Utilizzo di Windows Autopilot](windows10-deploy-autopilot.md) | Selezionare questa opzione se si stanno configurando nuovi computer Windows che dispongono di Windows 10 Enterprise, versione 1703 o successiva preinstallata. Gli utenti finali avvierà il programma di installazione utilizzando la configurazione desiderata immettendo le proprie credenziali dell'account aziendale o dell'Istituto di istruzione. |

Se questi scenari di distribuzione non soddisfano le esigenze dell'organizzazione, è possibile conoscere altri scenari e comprendere le funzionalità e le limitazioni di ognuno negli [scenari di distribuzione di Windows 10](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios). È anche possibile <a href="https://aka.ms/planforwin10deployment" target="_blank">pianificare la distribuzione di Windows 10</a> autonomamente.

Per ulteriori informazioni su Windows 10, vedere gli articoli seguenti:

- [Pagina del prodotto Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise)
- [Windows 10](https://docs.microsoft.com/windows/windows-10)
- [Distribuire e aggiornare Windows 10](https://docs.microsoft.com/windows/deployment/)


## <a name="additional-services-and-features"></a>Servizi e funzionalità aggiuntivi
Nell'ambito della distribuzione di Windows 10 Enterprise, è possibile aggiungere questi servizi e funzionalità aggiuntivi.

### <a name="desktop-analytics"></a>Desktop Analytics

Windows utilizza i dati di diagnostica per fornire informazioni dettagliate, utili per ottenere approfondimenti sull'efficienza operativa e sull'integrità dei dispositivi Windows 10 nel proprio ambiente.

* Preparazione per l'aggiornamento: la preparazione all'aggiornamento consente di passare a Windows 10 e di rimanere aggiornati con i nuovi aggiornamenti delle funzionalità di Windows 10. 
* Update Compliance-la conformità degli aggiornamenti è destinata all'amministratore IT che desidera ottenere una visione olistica di tutti i dispositivi Windows 10, senza ulteriori requisiti di infrastruttura.
* Integrità del dispositivo: è possibile utilizzare l'integrità del dispositivo per rilevare e correggere in modo proattivo i problemi di impatto dell'utente finale.

Per ulteriori informazioni, vedere [Desktop Analytics Overview](https://docs.microsoft.com/mem/configmgr/desktop-analytics/overview) .

### <a name="windows-security"></a>Sicurezza di Windows

Windows 10 fornisce funzionalità che consentono di proteggere le minacce, la protezione dei dispositivi e la guida per il controllo di accesso. Con Windows 10, è possibile ottenere funzionalità di sicurezza critiche che proteggono il dispositivo fin dall'inizio. Microsoft 365 E3 aggiunge funzionalità di sicurezza quali Windows Hello for business, Windows Defender Application Control e Windows Information Protection. Con Microsoft 365 E5, è possibile ottenere tutta la protezione dalla sicurezza di Microsoft 365 E3 oltre alle funzionalità di sicurezza basate sul cloud e Microsoft Defender Advanced Threat Protection. 

Per ulteriori informazioni sulle funzionalità di sicurezza disponibili con Windows 10 Enterprise e su come è possibile distribuire, gestire, configurare e risolvere i problemi relativi a tre funzionalità di sicurezza principali, vedere [passaggio 5: distribuire le funzionalità di sicurezza di Windows 10 Enterprise](windows10-enable-security-features.md).

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Come Microsoft esegue Microsoft 365 Enterprise

Sbircia all'interno di Microsoft e Scopri come la società [ha distribuito Windows 10 Enterprise e utilizza Strong Authentication, Intune e Microsoft Defender ATP](https://www.microsoft.com/itshowcase/deploying-and-managing-microsoft-365#primaryR6).

## <a name="how-contoso-did-microsoft-365-enterprise"></a>Come ha agito Contoso con Microsoft 365 Enterprise

Vedere come Contoso Corporation, un'azienda multinazionale fittizia ma rappresentativa, ha [distribuito Windows 10 Enterprise](contoso-win10.md).

![Contoso Corporation](../media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a>Passaggio successivo

|||
|:-------|:-----|
|![Passaggio 1](../media/stepnumbers/Step1.png)| [Preparare l'organizzazione per Windows 10 Enterprise](windows10-prepare-your-org.md) |
