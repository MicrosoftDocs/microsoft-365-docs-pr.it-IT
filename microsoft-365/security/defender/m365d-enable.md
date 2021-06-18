---
title: Attivare Microsoft 365 Defender nel Centro sicurezza Microsoft 365 sicurezza
description: Informazioni su come abilitare le Microsoft 365 Defender e iniziare a integrare l'evento imprevisto e la risposta di sicurezza.
keywords: introduzione, abilitare Microsoft 365 Defender, Microsoft 365 Defender, M365, sicurezza, posizione dei dati, autorizzazioni necessarie, idoneità alla licenza, pagina impostazioni
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 102666834562d0576920c746842582c2870b3738
ms.sourcegitcommit: bbad1938b6661d4a6bca99f235c44e521b1fb662
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/18/2021
ms.locfileid: "53007610"
---
# <a name="turn-on-microsoft-365-defender"></a>Attivare Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender

[Microsoft 365 Defender](microsoft-365-defender.md) unifica il processo di risposta agli eventi imprevisti integrando le funzionalità chiave in Microsoft Defender for Endpoint, Microsoft Defender per Office 365, Microsoft Cloud App Security e Microsoft Defender for Identity. Questa esperienza unificata aggiunge importanti funzionalità alle quali è possibile accedere nel Centro sicurezza Microsoft 365.

Microsoft 365 Defender si attiva automaticamente quando i clienti idonei con le autorizzazioni necessarie visitano Microsoft 365 centro sicurezza. Leggere questo articolo per comprendere i diversi prerequisiti e come Microsoft 365 Defender viene eseguito il provisioning.

## <a name="check-license-eligibility-and-required-permissions"></a>Verificare l'idoneità della licenza e le autorizzazioni necessarie

Una licenza per un prodotto Microsoft 365 sicurezza in genere consente di usare Microsoft 365 Defender nel centro sicurezza Microsoft 365 senza costi aggiuntivi per la gestione delle licenze. Ti consigliamo di ottenere una licenza Microsoft 365 E5, E5 Security, A5 o A5 Security o una combinazione valida di licenze che fornisce l'accesso a tutti i servizi supportati.

Per informazioni dettagliate sulle licenze, [leggere i requisiti di licenza](prerequisites.md#licensing-requirements).

### <a name="check-your-role"></a>Controllare il ruolo

È necessario essere un **amministratore globale** o un amministratore **della** sicurezza in Azure Active Directory per attivare Microsoft 365 Defender. [Visualizzare i ruoli in Azure AD](/azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a>Servizi supportati

Microsoft 365 Defender aggrega i dati dei vari servizi supportati già distribuiti. I dati verranno processati e archiviati centralmente per identificare nuove informazioni dettagliate e rendere possibili flussi di lavoro di risposta centralizzati. Questa operazione non influisce sulle distribuzioni, le impostazioni o i dati esistenti associati ai servizi integrati.

Per ottenere la migliore protezione e ottimizzare Microsoft 365 Defender, è consigliabile distribuire tutti i servizi supportati applicabili nella rete. Per ulteriori informazioni, [vedere distribuzione di servizi supportati.](deploy-supported-services.md)

## <a name="onboard-to-the-service"></a>Onboard al servizio
L'onboarding Microsoft 365 Defender è semplice. Dal menu di spostamento seleziona qualsiasi elemento, ad esempio Eventi imprevisti **& avvisi,** **Ricerca,** Centro notifiche o **Analisi** delle minacce per avviare il processo di onboarding. 

### <a name="data-center-location"></a>Posizione del data center

Microsoft 365 Defender i dati verranno archiviati ed evasi nello [stesso percorso utilizzato da Microsoft Defender per Endpoint.](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy) Se non si dispone di Microsoft Defender for Endpoint, viene selezionata automaticamente una nuova posizione del data center in base alla posizione dei servizi di sicurezza Microsoft 365 attivi. La posizione del data center selezionata viene visualizzata sullo schermo.

Selezionare **Serve assistenza?** nel centro sicurezza Microsoft 365 per contattare il supporto Microsoft per il provisioning Microsoft 365 Defender in un'altra posizione del data center.

> [!NOTE]
> In passato, Microsoft Defender for Endpoint eseguiva automaticamente il provisioning nei data center dell'Unione Europea (UE) quando è attivato tramite Azure Defender. Microsoft 365 Defender il provisioning automatico nello stesso data center dell'UE per i clienti che hanno effettuato il provisioning di Defender per Endpoint in questo modo in passato.

### <a name="confirm-that-the-service-is-on"></a>Verificare che il servizio sia attivo

Dopo aver eseguito il provisioning il servizio aggiunge:

- [Gestione degli eventi imprevisti](incidents-overview.md)
- [Coda di avvisi](investigate-alerts.md)
- Un centro operativo per la gestione delle [analisi e risposte automatiche](m365d-autoir.md)
- [Funzionalità di ricerca](advanced-hunting-overview.md) avanzate
- Analisi delle minacce

![Immagine del riquadro Microsoft 365 di spostamento del centro sicurezza con Microsoft 365 Defender funzionalità Microsoft 365 centro sicurezza con gestione degli eventi imprevisti e ](../../media/overview-incident.png)
 *altre funzionalità Microsoft 365 Defender sicurezza*

### <a name="getting-microsoft-defender-for-identity-data"></a>Recupero dei dati di Microsoft Defender for Identity 
Per abilitare l'integrazione con Microsoft Cloud App Security, devi accedere al Microsoft Cloud App Security almeno una volta.

## <a name="get-assistance"></a>Ottenere assistenza

Per ottenere risposte alle domande più frequenti sull'attivazione Microsoft 365 Defender, leggere [le domande frequenti](m365d-enable-faq.md).

Il personale di supporto Microsoft può aiutare a eseguire il provisioning o il deprovisioning del servizio e delle risorse correlate nel tenant. Per assistenza, selezionare **Serve assistenza?** nel centro Microsoft 365 sicurezza. Quando si contatta il supporto, menzionare Microsoft 365 Defender.

## <a name="related-topics"></a>Argomenti correlati

- [Domande frequenti](m365d-enable-faq.md)
- [Requisiti relativi alle licenze e altri prerequisiti](prerequisites.md)
- [Distribuire i servizi supportati](deploy-supported-services.md)
- [Microsoft 365 Defender panoramica](microsoft-365-defender.md)
- [Panoramica di Microsoft Defender for Endpoint](../defender-endpoint/microsoft-defender-endpoint.md)
- [Panoramica di Defender Office 365](../office-365-security/defender-for-office-365.md)
- [Panoramica di Microsoft Cloud App Security](/cloud-app-security/what-is-cloud-app-security)
- [Panoramica di Microsoft Defender for Identity](/azure-advanced-threat-protection/what-is-atp)
- [Archiviazione dei dati di Microsoft Defender for Endpoint](../defender-endpoint/data-storage-privacy.md)
