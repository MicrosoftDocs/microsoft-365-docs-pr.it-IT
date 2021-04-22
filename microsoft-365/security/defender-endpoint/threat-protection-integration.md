---
title: Integrare Microsoft Defender for Endpoint con altre soluzioni Microsoft
description: Scopri come Microsoft Defender for Endpoint si integra con altre soluzioni Microsoft, tra cui Microsoft Defender for Identity e Azure Defender.
author: mjcaparas
ms.author: macapara
ms.prod: m365-security
keywords: microsoft 365 defender, accesso condizionale, office, Microsoft Defender for Endpoint, microsoft defender for identity, microsoft defender for office, Azure Defender, microsoft cloud app security, azure sentinel
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: ce8dbef2f4fb7c3503f04f15148d2071b449b2dc
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935534"
---
# <a name="microsoft-defender-for-endpoint-and-other-microsoft-solutions"></a>Microsoft Defender per Endpoint e altre soluzioni Microsoft

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="integrate-with-other-microsoft-solutions"></a>Integrazione con altre soluzioni Microsoft

Microsoft Defender for Endpoint si integra direttamente con varie soluzioni Microsoft.

### <a name="azure-defender"></a>Azure Defender
Microsoft Defender for Endpoint offre una soluzione completa di protezione del server, incluse le funzionalità di rilevamento e risposta degli endpoint nei server Windows.

### <a name="azure-sentinel"></a>Azure Sentinel
Il connettore Microsoft Defender for Endpoint consente di trasmettere gli avvisi da Microsoft Defender per Endpoint in Azure Sentinel. In questo modo sarà possibile analizzare in modo più completo gli eventi di sicurezza all'interno dell'organizzazione e creare playbook per una risposta efficace e immediata.

### <a name="azure-information-protection"></a>Azure Information Protection
L'integrazione di Azure Information Protection è stata recentemente deprecata poiché le funzionalità DLP degli endpoint incorporano una soluzione di individuazione e protezione migliorata per i dati sensibili archiviati nei dispositivi endpoint, che facilita una maggiore visibilità e integrazione tra le soluzioni. Questo è stato annunciato nel [blog seguente.](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/protecting-sensitive-information-on-devices/ba-p/2143555) È consigliabile che i clienti si spostino all'uso di Endpoint DLP.

### <a name="conditional-access"></a>Accesso condizionale
Il punteggio di rischio del dispositivo dinamico di Microsoft Defender for Endpoint è integrato nella valutazione dell'accesso condizionale, assicurando che solo i dispositivi sicuri hanno accesso alle risorse. 

### <a name="microsoft-cloud-app-security"></a>Microsoft Cloud App Security
Microsoft Cloud App Security sfrutta i segnali degli endpoint di Microsoft Defender for Endpoint per consentire la visibilità diretta sull'utilizzo delle applicazioni cloud, incluso l'uso di servizi cloud non supportati (IT shadow) da tutti i dispositivi monitorati da Microsoft Defender per Endpoint.

### <a name="microsoft-defender-for-identity"></a>Microsoft Defender per identità
Le attività sospette sono processi in esecuzione in un contesto utente. L'integrazione tra Microsoft Defender for Endpoint e Microsoft Defender for Identity offre la flessibilità di condurre un'indagine sulla sicurezza informatica tra le attività e le identità.

### <a name="microsoft-defender-for-office"></a>Microsoft Defender per Office
[Defender per Office 365](https://docs.microsoft.com/office365/securitycompliance/office-365-atp) consente di proteggere l'organizzazione da malware nei messaggi di posta elettronica o nei file tramite collegamenti sicuri, allegati sicuri, funzionalità avanzate di anti-phishing e spoofing intelligence. L'integrazione tra Microsoft Defender per Office 365 e Microsoft Defender for Endpoint consente agli analisti della sicurezza di passare a monte per analizzare il punto di ingresso di un attacco. Attraverso la condivisione delle informazioni sulle minacce, gli attacchi possono essere contenuti e bloccati. 

>[!NOTE]
> Defender for Office 365 data is displayed for events within the last 30 days. Per gli avvisi, i dati di Defender per Office 365 vengono visualizzati in base alla prima attività. Successivamente, i dati non sono più disponibili in Defender per Office 365.

### <a name="skype-for-business"></a>Skype for Business
L'integrazione di Skype for Business consente agli analisti di comunicare con un utente o un proprietario di dispositivo potenzialmente compromesso tramite un semplice pulsante dal portale.

## <a name="microsoft-365-defender"></a>Microsoft 365 Defender
Con Microsoft 365 Defender, Microsoft Defender for Endpoint e varie soluzioni di sicurezza Microsoft formano una famiglia di prodotti di difesa aziendale unificata pre e post-violazione che si integra in modo nativo tra endpoint, identità, posta elettronica e applicazioni per rilevare, impedire, analizzare e rispondere automaticamente ad attacchi sofisticati. 
 
[Altre informazioni su Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/defender/microsoft-threat-protection)


## <a name="related-topics"></a>Argomenti correlati
- [Configurare l'integrazione e altre funzionalità avanzate](advanced-features.md)
- [Panoramica di Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/defender/microsoft-threat-protection)
- [Attivare Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/defender/mtp-enable)
- [Proteggere utenti, dati e dispositivi con accesso condizionale](conditional-access.md)
