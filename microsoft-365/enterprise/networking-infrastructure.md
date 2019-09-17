---
title: 'Fase 1: infrastruttura di rete di Microsoft 365 Enterprise'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: La procedura per distribuire l'infrastruttura di rete di Microsoft 365 Enterprise.
ms.openlocfilehash: 35c65515854bb0c47a45e48d8e3c6af6a80d907c
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/14/2019
ms.locfileid: "36982797"
---
# <a name="phase-1-networking-infrastructure-for-microsoft-365-enterprise"></a>Fase 1: infrastruttura di rete di Microsoft 365 Enterprise

![](./media/deploy-foundation-infrastructure/networking_icon.png)

Microsoft 365 Enterprise include Office 365, Microsoft Intune e molti servizi di identità e sicurezza di Microsoft Azure. Tutti questi servizi basati su cloud si basano su sicurezza, prestazioni e affidabilità delle connessioni dei dispositivi client su Internet o circuiti dedicati. Per ospitare questi servizi e renderli disponibili per i clienti in tutto il mondo, Microsoft ha progettato un'infrastruttura di rete che mette in evidenza le prestazioni e l'integrazione. 

In questa fase, si esaminano le considerazioni chiave sulla creazione di una connessione ad alte prestazioni ai servizi cloud di Microsoft 365 Enterprise. Per una panoramica, vedere [Principi di rete di Office 365](https://techcommunity.microsoft.com/t5/Office-365-Blog/Getting-the-best-connectivity-and-performance-in-Office-365/ba-p/124694).

>[!Note]
>Se è stata già implementata un'infrastruttura di rete, vedere i [criteri uscita](networking-exit-criteria.md) per questa fase per assicurarsi che soddisfino le condizioni facoltative e obbligatorie di Microsoft 365 Enterprise.

## <a name="plan-and-deploy-your-microsoft-365-enterprise-networking-infrastructure"></a>Pianificare e distribuire l'infrastruttura di rete di Microsoft 365 Enterprise 

Usare la procedura seguente per creare l'infrastruttura di rete per i requisiti e le funzionalità di Microsoft 365 Enterprise.

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)|[Preparare la rete per Microsoft 365](networking-provide-bandwidth-cloud-services.md)|
|![](./media/stepnumbers/Step2.png)|[Configurare le connessioni Internet locali per ogni sede](networking-dns-resolution-same-location.md)|
|![](./media/stepnumbers/Step3.png)|[Evitare fenomeni di "hairpinning" di rete](networking-avoid-network-hairpins.md)|
|![](./media/stepnumbers/Step4.png)|[Configurare il bypass di traffico](networking-configure-proxies-firewalls.md)|
|![](./media/stepnumbers/Step5.png)|[Ottimizzare prestazioni di client e del servizio di Office 365](networking-optimize-tcp-performance.md)|


Dopo aver completato questi passaggi, passare ai [criteri uscita](networking-exit-criteria.md) per questa fase per garantire che vengano rispettate le condizioni facoltative e obbligatorie per Microsoft 365 Enterprise.

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Come Microsoft esegue Microsoft 365 Enterprise

Ulteriori informazioni su come la società [ha ottimizzato la rete Microsoft per i servizi cloud](https://www.microsoft.com/it-IT/itshowcase/deploying-and-managing-microsoft-365#primaryR4).

## <a name="how-contoso-did-microsoft-365-enterprise"></a>Come ha agito Contoso con Microsoft 365 Enterprise

Vedere come Contoso Corporation, un'azienda multinazionale fittizia ma rappresentativa, [ha ottimizzato i propri dispositivi di rete e le connessioni Internet](contoso-networking.md) per i servizi cloud Microsoft 365.

![](./media/contoso-overview/contoso-icon.png)

## <a name="next-step"></a>Passaggio successivo

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)|[Preparare la rete per Microsoft 365](networking-provide-bandwidth-cloud-services.md)|

