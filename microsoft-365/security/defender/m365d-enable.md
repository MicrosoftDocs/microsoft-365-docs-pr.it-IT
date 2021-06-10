---
title: Attivare Microsoft 365 Defender nel centro sicurezza Microsoft 365 sicurezza
description: Scopri come abilitare Microsoft 365 Defender e iniziare a integrare l'incidente di sicurezza e la risposta.
keywords: introduzione, abilitare Microsoft 365 Defender, Microsoft 365 Defender, M365, sicurezza, posizione dei dati, autorizzazioni necessarie, idoneità alla licenza, pagina delle impostazioni
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
ms.openlocfilehash: 3f05cc8c9b2509f8c95b802f56905e2859221cd2
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861600"
---
# <a name="turn-on-microsoft-365-defender"></a>Attivare Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender

[Microsoft 365 Defender](microsoft-365-defender.md) unifica il processo di risposta agli eventi imprevisti integrando le funzionalità chiave in Microsoft Defender for Endpoint, Microsoft Defender per Office 365, Microsoft Cloud App Security e Microsoft Defender for Identity. Questa esperienza unificata aggiunge importanti funzionalità alle quali è possibile accedere nel Centro sicurezza Microsoft 365.

Microsoft 365 Defender si attiva automaticamente quando i clienti idonei con le autorizzazioni necessarie visitano Microsoft 365 centro sicurezza. Leggere questo articolo per comprendere diversi prerequisiti e come viene eseguito il provisioning Microsoft 365 Defender.

## <a name="check-license-eligibility-and-required-permissions"></a>Verificare l'idoneità della licenza e le autorizzazioni necessarie

Una licenza per un prodotto Microsoft 365 sicurezza in genere ti autorizza a usare Microsoft 365 Defender nel centro sicurezza Microsoft 365 senza costi aggiuntivi per le licenze. Ti consigliamo di ottenere una licenza Microsoft 365 E5, E5 Security, A5 o A5 Security o una combinazione valida di licenze che fornisce l'accesso a tutti i servizi supportati.

Per informazioni dettagliate sulle licenze, [leggere i requisiti di licenza](prerequisites.md#licensing-requirements).

### <a name="check-your-role"></a>Controllare il ruolo

Devi essere un **amministratore globale o** un amministratore della sicurezza in Azure Active Directory per attivare Microsoft 365 Defender.  [Visualizzare i ruoli in Azure AD](/azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a>Servizi supportati

Microsoft 365 Defender aggrega i dati dei vari servizi supportati che hai già distribuito. I dati verranno processati e archiviati centralmente per identificare nuove informazioni dettagliate e rendere possibili flussi di lavoro di risposta centralizzati. Questa operazione non influisce sulle distribuzioni, le impostazioni o i dati esistenti associati ai servizi integrati.

Per ottenere la migliore protezione e ottimizzare Microsoft 365 Defender, ti consigliamo di distribuire tutti i servizi supportati applicabili nella rete. Per ulteriori informazioni, [vedere distribuzione di servizi supportati.](deploy-supported-services.md)

## <a name="onboard-to-the-service"></a>Onboard al servizio
L'onboarding Microsoft 365 Defender è semplice. Dal menu di spostamento seleziona qualsiasi Microsoft 365 Defender, ad esempio Eventi imprevisti, Ricerca, Centro notifiche o Analisi delle minacce per avviare il processo di onboarding. 

### <a name="data-center-location"></a>Posizione del data center

Microsoft 365 Defender archivierà ed eelaborare i dati nella [stessa posizione usata da Microsoft Defender per Endpoint.](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy) Se non si dispone di Microsoft Defender for Endpoint, viene selezionata automaticamente una nuova posizione del data center in base alla posizione dei servizi di sicurezza Microsoft 365 attivi. La posizione del data center selezionata viene visualizzata sullo schermo.

Selezionare **Serve assistenza?** nel centro sicurezza Microsoft 365 per contattare il supporto Tecnico Microsoft per il provisioning di Microsoft 365 Defender in un'altra posizione del data center.

> [!NOTE]
> In passato, Microsoft Defender for Endpoint eseguiva automaticamente il provisioning nei data center dell'Unione Europea (UE) quando è attivato tramite Azure Defender. Microsoft 365 Defender eseguirà automaticamente il provisioning nello stesso data center dell'UE per i clienti che hanno effettuato il provisioning di Defender per Endpoint in questo modo in passato.

### <a name="confirm-that-the-service-is-on"></a>Verificare che il servizio sia attivo

Dopo aver eseguito il provisioning il servizio aggiunge:

- [Gestione degli eventi imprevisti](incidents-overview.md)
- [Coda di avvisi](investigate-alerts.md)
- Un centro operativo per la gestione delle [analisi e risposte automatiche](m365d-autoir.md)
- [Funzionalità di ricerca](advanced-hunting-overview.md) avanzate
- Analisi delle minacce

![Immagine del riquadro Microsoft 365 di spostamento del centro sicurezza con Microsoft 365 Defender Microsoft 365 centro sicurezza con gestione degli eventi imprevisti e altre ](../../media/overview-incident.png)
 *funzionalità Microsoft 365 Defender*

### <a name="getting-microsoft-defender-for-identity-data"></a>Recupero dei dati di Microsoft Defender for Identity 
Per abilitare l'integrazione con Microsoft Cloud App Security, devi accedere al Microsoft Cloud App Security almeno una volta.

## <a name="get-assistance"></a>Ottenere assistenza

Per ottenere risposte alle domande più frequenti sull'attivazione di Microsoft 365 Defender, leggere [le domande frequenti](m365d-enable-faq.md).

Il personale di supporto Microsoft può aiutare a eseguire il provisioning o il deprovisioning del servizio e delle risorse correlate nel tenant. Per assistenza, selezionare **Serve assistenza?** nel centro Microsoft 365 sicurezza. Quando si contatta il supporto, menzionare Microsoft 365 Defender.

## <a name="related-topics"></a>Argomenti correlati

- [Domande frequenti](m365d-enable-faq.md)
- [Requisiti relativi alle licenze e altri prerequisiti](prerequisites.md)
- [Distribuire i servizi supportati](deploy-supported-services.md)
- [Microsoft 365 Panoramica di Defender](microsoft-365-defender.md)
- [Panoramica di Microsoft Defender for Endpoint](../defender-endpoint/microsoft-defender-endpoint.md)
- [Panoramica di Defender Office 365](../office-365-security/defender-for-office-365.md)
- [Panoramica di Microsoft Cloud App Security](/cloud-app-security/what-is-cloud-app-security)
- [Panoramica di Microsoft Defender for Identity](/azure-advanced-threat-protection/what-is-atp)
- [Archiviazione dei dati di Microsoft Defender for Endpoint](../defender-endpoint/data-storage-privacy.md)
