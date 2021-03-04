---
title: Distribuire le funzionalità di protezione dalle minacce in Microsoft 365
description: Informazioni su come distribuire i servizi di protezione dalle minacce e le funzionalità di sicurezza in Microsoft 365 E5.
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.audience: ITPro
ms.topic: article
ms.prod: m365-security
ms.technology: m365d
audience: Admin
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-threatprotection
ms.custom: ''
f1.keywords: NOCSH
ms.openlocfilehash: a2d758ca4628e4cd5f73e77d0d86946e350163c5
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/04/2021
ms.locfileid: "50424108"
---
# <a name="deploy-threat-protection-capabilities-across-microsoft-365"></a>Distribuire le funzionalità di protezione dalle minacce in Microsoft 365

[Il malware](https://docs.microsoft.com/windows/security/threat-protection/intelligence/understanding-malware)e gli attacchi informatici sofisticati, come le minacce [senza file,](https://docs.microsoft.com/windows/security/threat-protection/intelligence/fileless-threats)sono un evento comune. Le aziende devono proteggere se stessi e i loro clienti con efficaci funzionalità di sicurezza IT. I cyberattacchi possono causare problemi importanti per l'organizzazione, dalla perdita di fiducia ai problemi finanziari, ai tempi di inattività per le aziende e altro ancora. La protezione dalle minacce è importante, ma può essere difficile determinare dove concentrare il tempo, l'impegno e le risorse dell'organizzazione. 

Le soluzioni di sicurezza Microsoft sono integrate nei prodotti e nei servizi microsoft. Le funzionalità di automazione e machine learning riducono il carico sui team di sicurezza per assicurarsi che gli elementi siano stati indirizzati in modo corretto. E la forza delle soluzioni di sicurezza Microsoft si basa su trilioni di segnali che esercitiamo ogni giorno nel [nostro Intelligent Security Graph.](https://cloud-platform-assets.azurewebsites.net/intelligent-security-graph) Le soluzioni di sicurezza di Microsoft [365 includono Microsoft 365 Defender,](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection)una soluzione che riunisce segnali in tutta la posta elettronica, i dati, i dispositivi e le identità per disegnare un quadro delle minacce avanzate contro l'organizzazione.


Guarda questo video per una panoramica sulla procedura di implementazione.
<br><br>
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vsI7]

>[!Note]
>Questo video usa i nomi precedenti dei prodotti e delle funzionalità di protezione dalle minacce, ma i concetti sono gli stessi. È in corso un aggiornamento di questo video.
>

Utilizzare questo articolo come guida per l'implementazione della soluzione di protezione dalle minacce.

## <a name="threat-protection-in-microsoft-365-e5"></a>Protezione dalle minacce in Microsoft 365 E5

[Microsoft 365 E5](https://www.microsoft.com/microsoft-365/enterprise-e5-business-software?activetab=pivot%3aoverviewtab) consente di proteggere l'organizzazione con intelligence integrata adattiva. Con le funzionalità di protezione dalle minacce in Microsoft 365 E5, è possibile rilevare e analizzare minacce avanzate, identità compromesse e azioni dannose nell'ambiente locale e cloud.

In Microsoft 365 E5, le funzionalità di protezione dalle minacce sono integrate per impostazione predefinita. I segnali di ogni funzionalità aggiungono forza alla capacità complessiva di rilevare e rispondere alle minacce. L'insieme combinato di funzionalità offre la migliore protezione per le organizzazioni, in particolare per le organizzazioni multi-nazionali, rispetto all'esecuzione di prodotti non Microsoft. L'immagine seguente illustra i servizi e le funzionalità di protezione dalle minacce in Microsoft 365 E5 descritti in questo articolo.

![Panoramica di Microsoft 365 Defender](../media/deploy-threat-protection/deploy-threat-protection-across-m365-overview.png)

Non appena si distribuisce una qualsiasi delle funzionalità di Defender per Office 365, è possibile attivare Microsoft 365 Defender, che riunisce segnali e dati in un'unica posizione. 

![Illustrazione concettuale del dashboard di Microsoft 365 Defender](../media/deploy-threat-protection/deploy-threat-protection-across-m365-mtp.png)

Nella figura seguente viene illustrato un percorso consigliato per la distribuzione di queste singole funzionalità. 

![Segnali di protezione dalle minacce M365](../media/deploy-threat-protection/deploy-threat-protection-across-m365.png)

|Soluzione/funzionalità  |Descrizione  |
|---------|---------|
|Autenticazione a più fattori e accesso condizionale     |Proteggersi da identità e dispositivi compromessi. Iniziare con questa protezione perché è di base. La configurazione consigliata in questa guida include Azure AD Identity Protection come prerequisito.     |
|Che cosa è Microsoft Defender per identità?     |  Una soluzione di sicurezza basata sul cloud che sfrutta i segnali di Active Directory Domain Services (AD DS) locali per identificare, rilevare e analizzare minacce avanzate, identità compromesse e azioni Insider dannose indirizzate all'organizzazione. Concentrarsi su Microsoft Defender per l'identità in seguito perché protegge l'infrastruttura locale e cloud, non ha dipendenze o prerequisiti e può offrire vantaggi immediati per la sicurezza. | 
|Microsoft Defender per Office 365     | Protegge l'organizzazione dalle minacce dannose poste da messaggi di posta elettronica, collegamenti (URL) e strumenti di collaborazione. Protezioni per malware, phishing, spoofing e altri tipi di attacco. La configurazione di Microsoft Defender per Office 365 è consigliata successivamente perché la distribuzione può richiedere più tempo per la modifica del controllo, la migrazione delle impostazioni dal sistema precedente e altre considerazioni. <br><br>Nota: assicurarsi di configurare le funzionalità di protezione dalle minacce incluse in tutti gli abbonamenti a Office 365 (Exchange Online Protection).       |
|Microsoft Defender per endpoint    | Una piattaforma di protezione degli endpoint che consente di prevenire, rilevare, analizzare e rispondere alle minacce avanzate.  La distribuzione di Defender per Endpoint può richiedere del tempo, ma la configurazione può essere eseguita in parallelo con altre funzionalità.   |
|Microsoft Cloud App Security     |   Un broker di sicurezza dell'accesso cloud per l'individuazione, l'indagine e la governance. È possibile abilitare Microsoft Cloud App Security in anticipo per iniziare a raccogliere dati e informazioni dettagliate. L'implementazione di informazioni e altre protezioni mirate nelle app SaaS implica la pianificazione e può richiedere più tempo.       | 

> [!TIP]
> Le organizzazioni con più team di sicurezza possono implementare queste funzionalità in parallelo.

## <a name="deploy-your-threat-protection-solution"></a>Distribuire la soluzione di protezione dalle minacce

Per assicurarsi che l'organizzazione abbia la protezione migliore possibile, configurare e distribuire la soluzione di sicurezza in modo da includere i passaggi seguenti:

1. [Configurare l'autenticazione a più fattori e i criteri di accesso condizionale](deploy-threat-protection-configure.md#step-1-set-up-multi-factor-authentication-and-conditional-access-policies)
2. [Configurare Microsoft Defender per l'identità](deploy-threat-protection-configure.md#step-2-configure-microsoft-defender-for-identity)
3. [Attivare Microsoft 365 Defender](deploy-threat-protection-configure.md#step-3-turn-on-microsoft-365-defender)
4. [Configurare Defender per Office 365](deploy-threat-protection-configure.md#step-4-configure-microsoft-defender-for-office-365)
5. [Configurare Microsoft Defender per Endpoint](deploy-threat-protection-configure.md#step-5-configure-microsoft-defender-for-endpoint)
6. [Configurare Microsoft Cloud App Security](deploy-threat-protection-configure.md#step-6-configure-microsoft-cloud-app-security)
7. [Monitorare lo stato ed eseguire azioni](deploy-threat-protection-configure.md#step-7-monitor-status-and-take-actions)
8. [Formare gli utenti](deploy-threat-protection-configure.md#step-8-train-users)

Le funzionalità di protezione dalle minacce possono essere configurate in parallelo, quindi se si dispone di più team di sicurezza di rete responsabili di servizi diversi, possono configurare le funzionalità di protezione dell'organizzazione contemporaneamente. Il diagramma seguente illustra il processo di alto livello per la distribuzione delle funzionalità di protezione dalle minacce. 

![Processo per la distribuzione delle funzionalità di protezione dalle minacce](../media/deploy-threat-protection/deploy-threat-protection-across-m365-grid.png) 
