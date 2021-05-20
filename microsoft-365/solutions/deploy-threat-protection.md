---
title: Distribuire funzionalità di protezione dalle minacce tra Microsoft 365
description: Panoramica dei servizi di protezione dalle minacce e delle funzionalità di sicurezza in Microsoft 365 E5. Proteggi gli account utente, i dispositivi, il contenuto di posta elettronica e altro ancora con Microsoft 365 E5.
keywords: microsoft threat protection, defender, setup, advanced threat protection, security, Microsoft 365 E5, protect devices
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.audience: ITPro
ms.topic: article
ms.prod: m365-security
ms.technology: m365d
audience: ITPro
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-threatprotection
ms.custom: ''
f1.keywords: NOCSH
ms.openlocfilehash: 4008f4e0198058e2b13de62c34697e3034d499b2
ms.sourcegitcommit: 9541d5e6720a06327dc785e3ad7e8fb11246fd72
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2021
ms.locfileid: "52583221"
---
# <a name="deploy-threat-protection-capabilities-across-microsoft-365-e5"></a>Distribuire funzionalità di protezione dalle minacce tra Microsoft 365 E5

Questa soluzione descrive potenti funzionalità di protezione dalle minacce in Microsoft 365 E5 e perché la protezione dalle minacce è importante. Ottieni una panoramica della protezione dalle minacce in Microsoft 365 E5 e scopri come affrontare la configurazione e la configurazione per la tua organizzazione.

## <a name="why-threat-protection-is-important"></a>Perché la protezione dalle minacce è importante 

[Malware](/windows/security/threat-protection/intelligence/understanding-malware)e attacchi informatici sofisticati, ad esempio minacce [senza file,](/windows/security/threat-protection/intelligence/fileless-threats)sono un evento comune. Le aziende devono proteggere se stessi e i propri clienti con funzionalità di sicurezza IT efficaci. Gli attacchi informatici possono causare problemi importanti per l'organizzazione, dalla perdita di fiducia ai problemi finanziari, ai tempi di inattività che minacciano l'azienda e altro ancora. La protezione dalle minacce è importante, ma può essere difficile determinare dove concentrare il tempo, l'impegno e le risorse dell'organizzazione. Microsoft 365 E5 può essere utile. 

## <a name="threat-protection-in-microsoft-365-e5"></a>Protezione dalle minacce in Microsoft 365 E5

Le soluzioni di sicurezza Microsoft sono integrate nei nostri prodotti e servizi. Le funzionalità di automazione e machine learning riducono il carico dei team di sicurezza per assicurarsi che gli elementi siano indirizzati. Il punto di forza delle soluzioni di sicurezza Microsoft si basa su trilioni di segnali che eserciteremo ogni giorno nel nostro [intelligent security Graph](/graph/security-concept-overview). Microsoft 365 soluzioni di sicurezza [includono Microsoft 365 Defender](../security/defender/microsoft-365-defender.md), una soluzione che riunisce i segnali attraverso la posta elettronica, i dati, i dispositivi e le identità per disegnare un'immagine delle minacce avanzate contro l'organizzazione.

[Microsoft 365 E5](https://www.microsoft.com/microsoft-365/enterprise-e5-business-software?activetab=pivot%3aoverviewtab) consente di proteggere l'organizzazione con un'intelligence integrata adattiva. Con le funzionalità di sicurezza di Microsoft 365 E5, è possibile rilevare e analizzare minacce avanzate, identità compromesse e azioni dannose nell'ambiente (locale e nel cloud).

## <a name="better-protection-with-integration"></a>Migliore protezione con l'integrazione

In Microsoft 365 E5, le funzionalità di protezione dalle minacce sono integrate per impostazione predefinita. I segnali di ogni funzionalità aggiungono forza alla capacità complessiva di rilevare e rispondere alle minacce. L'insieme combinato di funzionalità offre la migliore protezione per le organizzazioni, in particolare per le organizzazioni multi-nazionali, rispetto all'esecuzione di prodotti non Microsoft. L'immagine seguente illustra i servizi e le funzionalità di protezione dalle minacce descritti in questo articolo.

![Panoramica di Microsoft 365 Defender](../media/deploy-threat-protection/deploy-threat-protection-across-m365-overview.png)

Microsoft 365 Defender riunisce i segnali e i dati in un centro sicurezza Microsoft 365 [unificato.](/microsoft-365/security/defender/overview-security-center) 

> [!div class="mx-imgBorder"]
> ![Illustrazione concettuale Microsoft 365 dashboard di Defender](../media/deploy-threat-protection/deploy-threat-protection-across-m365-mtp.png)

## <a name="deployment-overview"></a>Panoramica della distribuzione

Nella figura seguente viene illustrato un percorso consigliato per la distribuzione di queste singole funzionalità. 

> [!div class="mx-imgBorder"]
> ![Segnali di protezione dalle minacce M365](../media/deploy-threat-protection/deploy-threat-protection-across-m365.png)

Guarda questo video per una panoramica sulla procedura di implementazione.
<br><br>
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4vsI7]

Nella tabella seguente vengono descritte le varie soluzioni/funzionalità da configurare e le relative operazioni.

|Passaggio |Soluzione/funzionalità  |Descrizione  |
|--|---------|---------|
| 1 |[Autenticazione a più fattori e accesso condizionale](deploy-threat-protection-configure.md#step-1-set-up-multi-factor-authentication-and-conditional-access-policies)     |Proteggere da identità e dispositivi compromessi. Iniziare con questa protezione perché è di base. La configurazione consigliata in questa guida include Azure AD Identity Protection come prerequisito. Per ulteriori informazioni, vedere [Azure AD Identity Protection.](/azure/security/fundamentals/threat-detection#azure-active-directory-identity-protection)     |
| 2 |[Microsoft Defender per identità](deploy-threat-protection-configure.md#step-2-configure-microsoft-defender-for-identity)     |  Una soluzione di sicurezza basata sul cloud che utilizza i segnali di Servizi di dominio Active Directory (AD DS) locali per identificare, rilevare e analizzare minacce avanzate, identità compromesse e azioni insider dannose indirizzate all'organizzazione. Concentrarsi su Microsoft Defender per l'identità in seguito perché protegge l'infrastruttura locale e cloud, non ha dipendenze o prerequisiti e può offrire vantaggi di sicurezza immediati. Per ulteriori informazioni, vedere [Che cos'è Identity Protection?](/azure/active-directory/identity-protection/overview-identity-protection). | 
| 3 |[Microsoft 365 Defender](deploy-threat-protection-configure.md#step-3-turn-on-microsoft-365-defender) |Combina i segnali e orchestra le funzionalità in un'unica soluzione. Consente ai professionisti della sicurezza di unire i segnali di minaccia e determinare l'ambito completo e l'impatto di una minaccia. Microsoft 365 Defender adotta azioni automatiche per impedire o arrestare l'attacco e auto-sanare le cassette postali, gli endpoint e le identità degli utenti interessati. Per ulteriori informazioni, vedere [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender). |
| 4  |[Microsoft Defender per Office 365](deploy-threat-protection-configure.md#step-4-configure-microsoft-defender-for-office-365)     | Protegge l'organizzazione da minacce dannose poste da messaggi di posta elettronica, collegamenti (URL) e strumenti di collaborazione. Protegge da malware, phishing, spoofing e altri tipi di attacco. È consigliabile configurare Microsoft Defender per Office 365 perché il controllo delle modifiche, la migrazione delle impostazioni dal sistema in uso e altre considerazioni possono richiedere più tempo per la distribuzione. Per altre informazioni, vedi [Microsoft Defender per Office 365.](/microsoft-365/security/office-365-security/defender-for-office-365)       |
| 5  |[Microsoft Defender per endpoint](deploy-threat-protection-configure.md#step-5-configure-microsoft-defender-for-endpoint)    | Aiuta a prevenire, rilevare, analizzare e rispondere alle minacce avanzate tra i dispositivi (denominati anche endpoint). Defender for Endpoint è una solida offerta di protezione dalle minacce. Per altre informazioni, vedi [Microsoft Defender for Endpoint.](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint)  |
| 6  |[Microsoft Cloud App Security](deploy-threat-protection-configure.md#step-6-configure-microsoft-cloud-app-security)     | Un broker di sicurezza per l'accesso al cloud per l'individuazione, l'indagine e la governance. Puoi abilitare le Microsoft Cloud App Security per iniziare a raccogliere dati e informazioni dettagliate. L'implementazione di informazioni e altre misure di protezione mirate nelle app SaaS implica la pianificazione e può richiedere più tempo. Per ulteriori informazioni, vedere [What is Cloud App Security?](/cloud-app-security/what-is-cloud-app-security)      | 

> [!TIP]
> Le organizzazioni che dispongono di più team di sicurezza possono implementare le funzionalità in parallelo. Ad esempio, un team può configurare Defender per Office 365 mentre un altro team configura Defender per Endpoint. La configurazione non deve seguire esattamente l'ordine suggerito. 

## <a name="plan-to-deploy-your-threat-protection-solution"></a>Pianificare la distribuzione della soluzione di protezione dalle minacce

Il diagramma seguente illustra il processo di alto livello per la distribuzione delle funzionalità di protezione dalle minacce. 

![Processo per la distribuzione delle funzionalità di protezione dalle minacce](../media/deploy-threat-protection/deploy-threat-protection-across-m365-grid.png)

Per assicurarsi che l'organizzazione abbia la migliore protezione [possibile,](deploy-threat-protection-configure.md) configurare e distribuire la soluzione di sicurezza con un processo che include i passaggi seguenti:

1. [Configurare l'autenticazione a più fattori e i criteri di accesso condizionale.](deploy-threat-protection-configure.md#step-1-set-up-multi-factor-authentication-and-conditional-access-policies)
2. [Configurare Microsoft Defender per l'identità](deploy-threat-protection-configure.md#step-2-configure-microsoft-defender-for-identity).
3. [Attivare Microsoft 365 Defender](deploy-threat-protection-configure.md#step-3-turn-on-microsoft-365-defender).
4. [Configurare Defender per Office 365](deploy-threat-protection-configure.md#step-4-configure-microsoft-defender-for-office-365).
5. [Configurare Microsoft Defender per Endpoint](deploy-threat-protection-configure.md#step-5-configure-microsoft-defender-for-endpoint).
6. [Configurare Microsoft Cloud App Security](deploy-threat-protection-configure.md#step-6-configure-microsoft-cloud-app-security).
7. [Monitorare lo stato ed eseguire azioni](deploy-threat-protection-configure.md#step-7-monitor-status-and-take-actions).
8. [Formare gli utenti](deploy-threat-protection-configure.md#step-8-train-users).

Le funzionalità di protezione dalle minacce possono essere configurate in parallelo, quindi se si dispone di più team di sicurezza di rete responsabili di servizi diversi, possono configurare le funzionalità di protezione dell'organizzazione contemporaneamente.

## <a name="next-step"></a>Passaggio successivo

Continua a [Configurare le funzionalità di protezione dalle minacce Microsoft 365](deploy-threat-protection-configure.md).


