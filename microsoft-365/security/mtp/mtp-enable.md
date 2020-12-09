---
title: Attiva Microsoft 365 Defender in Microsoft 365 Security Center
description: Informazioni su come abilitare Microsoft 365 Defender e avviare l'integrazione degli incidenti di sicurezza e della risposta.
keywords: Introduzione, abilitare MTP, Microsoft Threat Protection, M365, sicurezza, percorso dati, autorizzazioni necessarie, idoneità licenza, pagina impostazioni
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: fbe98b814b253551432ea35102f2bd6eeba921f8
ms.sourcegitcommit: 1beaf89d2faa32f11fe1613be2fa2b31c4bc4a91
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/08/2020
ms.locfileid: "49602092"
---
# <a name="turn-on-microsoft-365-defender"></a>Attiva Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender

[Microsoft 365 Defender](microsoft-threat-protection.md) unifica il processo di risposta agli incidenti mediante l'integrazione delle funzionalità chiave in Microsoft Defender per endpoint, Microsoft Defender per Office 365, Microsoft cloud app Security e Microsoft Defender per Identity. Questa esperienza unificata aggiunge importanti funzionalità alle quali è possibile accedere nel Centro sicurezza Microsoft 365.

Microsoft 365 Defender si attiva automaticamente quando i clienti idonei con le autorizzazioni necessarie visitano il Centro sicurezza di Microsoft 365. Leggere questo articolo per comprendere i vari prerequisiti e il provisioning di Microsoft 365 Defender.

## <a name="check-license-eligibility-and-required-permissions"></a>Verificare l'idoneità delle licenze e le autorizzazioni necessarie
Una licenza per un prodotto di sicurezza di Microsoft 365 generalmente autorizza l'utilizzo di Microsoft 365 Defender in Microsoft 365 Security Center senza ulteriori costi di licenza. Si consiglia di ottenere una licenza di sicurezza Microsoft 365 E5, E5 Security, a5 o a5 o una combinazione valida di licenze che fornisce l'accesso a tutti i servizi supportati.

Per informazioni dettagliate sulla licenza, [leggere i requisiti di licenza](prerequisites.md#licensing-requirements).

### <a name="check-your-role"></a>Controllare il ruolo
È necessario essere un **amministratore globale** o un **amministratore della sicurezza** in Azure Active Directory per abilitare Microsoft 365 Defender. [Visualizzare i ruoli in Azure AD](https://docs.microsoft.com//azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a>Servizi supportati
Microsoft 365 Defender aggrega i dati provenienti dai vari servizi supportati già distribuiti. I dati verranno elaborati e archiviati in modo centralizzato per identificare nuove informazioni e rendere possibili flussi di lavoro di risposta centralizzati. In questo caso, senza influire sulle distribuzioni, le impostazioni o i dati esistenti associati ai servizi integrati.

Per ottenere la migliore protezione e ottimizzare Microsoft 365 Defender, è consigliabile distribuire tutti i servizi supportati applicabili sulla rete. Per ulteriori informazioni, [vedere informazioni sulla distribuzione di servizi supportati](deploy-supported-services.md).

## <a name="before-starting-the-service"></a>Prima di avviare il servizio
Prima di abilitare il servizio, Microsoft 365 Security Center ([Security.Microsoft.com](https://security.microsoft.com)) Visualizza la pagina delle impostazioni di Microsoft 365 Defender quando si seleziona **incidenti**, **Centro azioni** o **ricerca** nel riquadro di spostamento. Questi elementi di spostamento non vengono visualizzati se non si è idonei per l'utilizzo di Microsoft 365 Defender.

![Immagine della pagina Microsoft 365 Defender Settings visualizzata se Microsoft 365 Defender non è stato attivato ](../../media/mtp-enable/mtp-settings.png)
 *nelle impostazioni di Microsoft 365 Defender in Microsoft 365 Security Center*

## <a name="starting-the-service"></a>Avvio del servizio
Per abilitare Microsoft 365 Defender, è sufficiente selezionare **attiva microsoft 365 Defender** e applicare la modifica. È inoltre possibile accedere a questa opzione selezionando **Impostazioni** ([Security.Microsoft.com/settings](https://security.microsoft.com/settings)) nel riquadro di spostamento e quindi selezionando **Microsoft 365 Defender**.

>[!NOTE]
>Se non si visualizzano le **Impostazioni** nel riquadro di spostamento o non è stato possibile accedere alla pagina, controllare autorizzazioni e licenze.

### <a name="data-center-location"></a>Percorso Data Center
Microsoft 365 Defender archivierà e elaborerà i dati nello [stesso percorso utilizzato da Microsoft Defender per endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy). Se non si dispone di Microsoft Defender per endpoint, viene selezionata automaticamente una nuova posizione del Data Center in base alla posizione dei servizi di sicurezza Microsoft 365 attivi. La posizione del Data Center selezionato viene visualizzata nella schermata. 

Selezionare **serve assistenza?** nel centro sicurezza Microsoft 365 contattare il supporto tecnico Microsoft per il provisioning di Microsoft 365 Defender in una posizione data center diversa. 

>[!NOTE]
>Microsoft Defender per endpoint si riattiva automaticamente nei data center dell'Unione europea (EU) quando viene attivato tramite Azure Defender. Microsoft 365 Defender provvederà alla provisioning automatico nello stesso data center EU per i clienti che hanno eseguito il preprovisioning di Defender per endpoint in questo modo. 

### <a name="confirm-that-the-service-is-on"></a>Verificare che il servizio sia attivo
Dopo aver eseguito il provisioning il servizio aggiunge:

- [Gestione degli eventi imprevisti](incidents-overview.md)
- Un centro operativo per la gestione delle [analisi e risposte automatiche](mtp-autoir.md)
- Funzionalità di [ricerca avanzata](advanced-hunting-overview.md)

![Immagine del riquadro di spostamento Microsoft 365 Centro sicurezza con Microsoft 365 Defender caratteristiche ](../../media/mtp-enable/mtp-on.png)
 *Centro sicurezza Microsoft 365 con gestione eventi non consentiti e altre funzionalità di Microsoft 365 Defender*

### <a name="getting-microsoft-defender-for-identity-data"></a>Ottenere Microsoft Defender per i dati dell'identità
Per condividere Microsoft Defender per i dati di identità con Microsoft 365 Defender, verificare che Microsoft cloud app Security e Microsoft Defender per l'integrazione delle identità sia attivata. [Altre informazioni sull'integrazione](https://docs.microsoft.com/cloud-app-security/aatp-integration)


## <a name="get-assistance"></a>Ottenere assistenza

Per ottenere le risposte alle domande più frequenti sull'attivazione di Microsoft 365 Defender, [Leggi le domande frequenti](mtp-enable-faq.md).

Il personale del supporto tecnico Microsoft può contribuire a provisionare o deprovisionare il servizio e le risorse correlate sul tenant. Per assistenza, selezionare **serve assistenza?** nel centro sicurezza Microsoft 365. Quando si contatta il supporto tecnico, fare riferimento a Microsoft 365 Defender.

## <a name="related-topics"></a>Argomenti correlati

- [Domande frequenti](mtp-enable-faq.md)
- [Requisiti relativi alle licenze e altri prerequisiti](prerequisites.md)
- [Distribuire i servizi supportati](deploy-supported-services.md)
- [Panoramica di Microsoft 365 Defender](microsoft-threat-protection.md)
- [Panoramica di Microsoft Defender per endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [Panoramica del difensore per Office 365](../office-365-security/office-365-atp.md)
- [Panoramica di Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [Panoramica di Microsoft Defender per l'identità](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [Microsoft Defender per l'archiviazione dei dati di endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
