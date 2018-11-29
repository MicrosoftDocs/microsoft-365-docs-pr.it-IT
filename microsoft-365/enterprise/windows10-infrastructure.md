---
title: Infrastruttura di Windows 10 aziendale Microsoft 365 Enterprise
description: Istruzioni generali operazioni che è necessario distribuire Enterprise 10 Windows su PC come parte di Microsoft 365 Enterprise.
keywords: Distribuzione di Windows 10 Enterprise documentazione Microsoft 365 Microsoft 365 Microsoft 365 Enterprise
author: greg-lindsay
localization_priority: Normal
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 09/18/2018
ms.author: greglin
ms.openlocfilehash: 80d7c1b56434647387b9c428ca07effdff929abf
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868283"
---
# <a name="phase-3-windows-10-enterprise"></a>Fase 3: Windows 10 Enterprise

![](./media/deploy-foundation-infrastructure/win10enterprise_icon.png)

Microsoft Enterprise 365 include Enterprise 10 Windows, che offre gli strumenti per eseguire più operazioni e gestione della sicurezza. Windows 10 Enterprise:

- **È integrato per semplicità** - cablaggio le potenzialità del cloud per contribuire a ridurre la complessità della gestione oggi 's moderno IT dispositivo ambiente di qualsiasi dimensione.
- **Con protezione intelligente** - è la versione di Windows più sicura mai, con protezione intelligente funzionalità che sono progettate per collaborare in modo migliore proteggere l'organizzazione.
- **Consente il lavoro del team e creatività** - sbloccata creatività il lavoro del team per fornire più produttivi possono verificarsi e che sia gli utenti che verrà IT AMO.

È necessario comprendere i diversi modi, è possibile distribuire il sistema operativo Windows 10 e scegliere quella più appropriata per l'organizzazione. A seconda dell'abbonamento Microsoft 365 Enterprise, sono disponibili anche Windows 10 servizi e funzionalità di sicurezza, è necessario configurare per sfruttare al meglio Windows 10.

Windows 10 consente gli scenari aziendali strategiche 365 Microsoft Enterprise:

- Sfruttare le conoscenze e competenze collettive consentendo alle persone di trovare, condividere ed elaborare file, informazioni e idee all'interno dell'organizzazione
- Lavorare ovunque e in qualsiasi momento in modo sicuro attraverso il proprio dispositivo, per ottenere il massimo risultato pur mantenendo flessibile lo stile di lavoro
- Fornire sicurezza, controlli e visibilità, offrendo conformità verificata nel settore agli standard globali
- Proteggere le informazioni e ridurre il rischio di perdita di dati
- Rileva e proteggendo report minacce esterne - Monitor e analizzare l'attività per rispondere immediatamente per garantire la sicurezza dell'organizzazione
- Proteggere gli utenti e i relativi account
- Supportare l'organizzazione con privacy e conformità avanzate per soddisfare il regolamento generale sulla protezione dei dati (GDPR)
- Restare sempre aggiornati sui propri dispositivi e software desktop, riducendo i rischi per la sicurezza e ottimizzando l'efficienza IT

Per ulteriori informazioni, vedere [Trasformazione digitale tramite Microsoft 365](http://transform.microsoft.com). 

>[!Note]
>Per distribuire insieme Windows 10 Enterprise e Office 365 ProPlus e passare a un [desktop moderno](https://www.microsoft.com/microsoft-365/modern-desktop), vedere il [Centro di distribuzione desktop moderno](http://aka.ms/howtoshift).
>

## <a name="windows-10-deployment"></a>Distribuzione di Windows 10

Esistono diversi modi, è possibile distribuire Enterprise 10 Windows per l'organizzazione. In questo caso, verrà posta attenzione su come configurare e distribuire un'immagine Windows 10 organizzazione tramite questi scenari di distribuzione moderno.

| Scenario di distribuzione | Quando utilizzarla |
|:--- |:--- |
| [Utilizzo di System Center Configuration Manager come un aggiornamento sul posto](windows10-deploy-inplaceupgrade.md) | Selezionare questa opzione se è necessario eseguire l'aggiornamento di Windows 7 o Windows 8.1 computer alla <a href="https://aka.ms/windows-10-release-information" target="_blank">versione corrente</a> di Windows 10 Enterprise e i computer attualmente gestiti con <a href="https://aka.ms/introtosccm" target="_blank">System Center Configuration Manager (branch corrente)</a>. |
| [Utilizzo di Windows Autopilot](windows10-deploy-autopilot.md) | Selezionare questa opzione se si sta impostando un nuovo computer di Windows con Windows 10 Enterprise 1703 o versione successiva pre. Gli utenti finali verrà avviare il programma di installazione della configurazione desiderata immettendo il proprio lavoro o scuola le credenziali dell'account. |

Se questi scenari di distribuzione si adatta alle esigenze dell'organizzazione, è possibile conoscere altri scenari e acquisire familiarità con le funzionalità e restrizioni di ciascun negli [scenari di distribuzione di Windows 10](https://docs.microsoft.com/windows/deployment/windows-10-deployment-scenarios). È inoltre possibile <a href="https://aka.ms/planforwin10deployment" target="_blank">pianificare la distribuzione di Windows 10</a> autonomamente.

È possibile trovare ulteriori informazioni Windows 10 con questi articoli:

- [Pagina del prodotto Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise)
- [Windows 10](https://docs.microsoft.com/windows/windows-10)
- [Distribuire e aggiornare Windows 10](https://docs.microsoft.com/windows/deployment/)


## <a name="additional-services-and-features"></a>Funzionalità e i servizi aggiuntivi
Durante la distribuzione di Windows 10 Enterprise, è possibile aggiungere questi servizi aggiuntivi e funzionalità.

### <a name="windows-analytics"></a>Windows Analytics

Windows utilizza i dati di diagnostica per fornire informazioni avanzate e pronti per interventi che consentono di ottenere informazioni complete su efficienza operativa e l'integrità dei dispositivi Windows 10 nell'ambiente in uso.

* Aggiornare lo stato di preparazione - preparazione dell'aggiornamento consentono di spostare in Windows 10 ed essere sempre aggiornati con gli aggiornamenti nuove funzionalità di 10 Windows. 
* Compatibilità di aggiornamento - aggiornamento conformità è prevista per l'amministratore IT che necessita di ottenere una visione globale di tutti i dispositivi Windows 10, senza requisiti di infrastruttura aggiuntiva.
* Dispositivo integrità - è possibile utilizzare dispositivi integrità per rilevare in modo proattivo e correggere i problemi corretti per l'utente finale.

Per ulteriori informazioni, vedere [Windows Analitica Overview](https://docs.microsoft.com/windows/deployment/update/windows-analytics-overview) .

### <a name="windows-security"></a>Protezione di Windows

Windows 10 offre funzionalità per garantire la protezione contro le minacce, Guida proteggere i dispositivi e Guida per il controllo di accesso. Con Windows 10, si ottengono le funzioni critico per la protezione che impedisce la data di inizio del diritto dell'utente dispositivo. Microsoft 365 E3 aggiunge funzionalità di sicurezza, ad esempio Windows Hello for Business, Windows Defender applicazione controllo e la protezione delle informazioni di Windows. Con Microsoft 365 E5, si riceve tutti la protezione di Microsoft 365 E3 e funzionalità di sicurezza basato su cloud di protezione di Windows Defender avanzate rischio. 

Per ulteriori informazioni sulle caratteristiche di protezione che si ottiene con Windows 10 Enterprise e get indicazioni su come è possibile distribuire, gestire, configurare e risoluzione dei problemi tre funzionalità principali ecurity, vedere [passaggio 5: funzionalità di sicurezza di distribuire Windows 10 Enterprise](windows10-enable-security-features.md).

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Come Microsoft esegue Microsoft 365 Enterprise

Per informazioni su come la società pianificate per, distribuiti ed è la gestione degli aggiornamenti per Windows 10 comparsa all'interno di Microsoft, vedere:

- [Preparazione dell'organizzazione per una distribuzione semplice di Windows 10](https://www.microsoft.com/itshowcase/windows10deployment?wt.mc_id=bmkg_itsc)
- [Adozione di Windows as a Service in Microsoft](https://www.microsoft.com/itshowcase/Article/Content/851/Adopting-Windows-as-a-service-at-Microsoft)
- [Distribuzione di Windows 10 in Microsoft come aggiornamento sul posto](https://www.microsoft.com/itshowcase/Article/Content/668/Deploying-Windows-10-at-Microsoft-as-an-inplace-upgrade)
- [Implementazione dell'autenticazione utente avanzata con Windows Hello for Business](https://www.microsoft.com/itshowcase/Article/Content/756/Implementing-strong-user-authentication-with-Windows-Hello-for-Business)
- [Distribuzione di Windows 10: suggerimenti e consigli da IT Microsoft](https://www.microsoft.com/itshowcase/Article/Content/951/Windows-10-deployment-tips-and-tricks-from-Microsoft-IT) (video)
- [Windows Defender ATP consente di individuare le minacce avanzate](https://www.microsoft.com/itshowcase/Article/Content/854/Windows-Defender-ATP-helps-detect-sophisticated-threats)
- [Protezione dell'azienda moderna con Windows Defender e Windows Defender ATP](https://www.microsoft.com/itshowcase/Article/Content/903/Securing-the-modern-enterprise-with-Windows-Defender-and-Windows-Defender-ATP) (video)

## <a name="how-contoso-did-microsoft-365-enterprise"></a>Come ha agito Contoso con Microsoft 365 Enterprise

Vedere modalità di Contoso Corporation, business multinazionale fittizia ma rappresentative, [distribuito Windows 10 Enterprise](contoso-win10.md).

![](./media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a>Passaggio successivo

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)| [Preparazione dell'organizzazione per Windows 10 Enterprise](windows10-prepare-your-org.md) |
