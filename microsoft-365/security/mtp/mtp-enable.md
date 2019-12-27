---
title: Attivare Microsoft Threat Protection nel Centro sicurezza Microsoft 365
description: Informazioni su come abilitare Microsoft Threat Protection e iniziare a integrare i problemi di sicurezza e le relative risposte.
keywords: Introduzione, abilitare MTP, Microsoft Threat Protection, M365, sicurezza, percorso dati, autorizzazioni necessarie, idoneità licenza
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
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
ms.openlocfilehash: 842c3be031e96467c8b82e8cf482435e66124960
ms.sourcegitcommit: 5b0a2e11c86c00e6e6b534f8b0a19962d1bb2805
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/27/2019
ms.locfileid: "40881977"
---
# <a name="turn-on-microsoft-threat-protection"></a>Attivare Microsoft Threat Protection

**Si applica a:**
- Microsoft Threat Protection

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Microsoft Threat Protection unifica il processo di risposta agli eventi imprevisti integrando le funzionalità principali in Microsoft Defender Advanced Threat Protection (ATP), Office 365 ATP, Microsoft Cloud App Security e Azure ATP. Questa esperienza unificata aggiunge importanti funzionalità alle quali è possibile accedere nel Centro sicurezza Microsoft 365.

## <a name="check-license-eligibility-and-required-permissions"></a>Verificare l'idoneità delle licenze e le autorizzazioni necessarie
I clienti che dispongono di Microsoft 365 E5 o di una licenza equivalente possono usare Microsoft Threat Protection. Per altre informazioni [consultare i requisiti di licenza](prerequisites.md#licensing-requirements).

 Per poter abilitare Microsoft Threat Protection, è necessario essere un **amministratore globale** o un **amministratore della sicurezza** in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles).

## <a name="start-using-the-service"></a>Iniziare a usare il servizio
L'attivazione del servizio Microsoft Threat Protection aggrega i dati dai vari servizi integrati. I dati vengono elaborati e archiviati in modo centralizzato per identificare nuovi approfondimenti e consentire flussi di lavoro di risposte centralizzate.

Prima dell'attivazione del servizio, nel Centro sicurezza Microsoft 365 ([security.microsoft.com](https://security.microsoft.com)) non vengono visualizzati gli **Eventi imprevisti** e le opzioni del **Centro operativo** nel menu.

![Immagine del menu del Centro sicurezza Microsoft 365 senza funzionalità di Microsoft Threat Protection](../images/mtp-off.png)
*Centro sicurezza Microsoft 365 con Microsoft Threat Protection disattivato*

Per attivare il servizio Microsoft Threat Protection, passare a **Impostazioni** > **Microsoft Threat Protection** > ** Consenso esplicito/rifiuto esplicito** nel Centro sicurezza Microsoft 365.

Se è stato eseguito il provisioning di Microsoft Defender ATP per l'organizzazione, i dati verranno archiviati ed elaborati nella stessa area data center selezionata per i [dati di Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy). Se non si dispone di Microsoft Defender ATP, verrà chiesto di scegliere una nuova area data center specifica per Microsoft Threat Protection. Sarà necessario fornire il consenso prima che i dati vengano condivisi tra i servizi e gli aggregati.

### <a name="confirm-that-the-service-is-on"></a>Verificare che il servizio sia attivo
Dopo aver eseguito il provisioning il servizio aggiunge:

- [Gestione degli eventi imprevisti](incidents-overview.md)
- Un centro operativo per la gestione delle [analisi e risposte automatiche](mtp-autoir.md)
- Funzionalità di [ricerca avanzata](advanced-hunting-overview.md) alla pagina **Ricerca** esistente

![Immagine del menu del Centro sicurezza Microsoft 365 con funzionalità di Microsoft Threat Protection](../images/mtp-on.png)
*Centro sicurezza Microsoft 365 con gestione degli eventi imprevisti e altre funzionalità di Microsoft Threat Protection*

### <a name="getting-azure-atp-data"></a>Ottenere i dati di Azure ATP
Per condividere i dati di Azure ATP con Microsoft Threat Protection, accertarsi che l'integrazione di Microsoft Cloud App Security e Azure ATP sia attivata. [Altre informazioni sull'integrazione](https://docs.microsoft.com/cloud-app-security/aatp-integration)


## <a name="turn-off-microsoft-threat-protection"></a>Disattivare Microsoft Threat Protection
Per interrompere l'uso del servizio Microsoft Threat Protection, passare a **Impostazioni** > **Microsoft Threat Protection** > ** Consenso esplicito/rifiuto esplicito** nel Centro sicurezza Microsoft 365. Deselezionare **Attiva Microsoft Threat Protection** e salvare le modifiche.

I dati verranno eliminati definitivamente e le funzionalità corrispondenti verranno rimosse dal Centro sicurezza Microsoft 365.

## <a name="get-assistance"></a>Ottenere assistenza

Il personale Microsoft può fornire assistenza per eseguire il provisioning o deprovisioning del servizio e delle risorse correlate nel tenant. Per assistenza [contattare il supporto tecnico Premier](https://go.microsoft.com/fwlink/?LinkID=733758).

## <a name="related-topics"></a>Argomenti correlati

- [Panoramica di Microsoft Threat Protection](microsoft-threat-protection.md)
- [Requisiti relativi alle licenze e altri prerequisiti](prerequisites.md)
- [Panoramica di Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [Panoramica di Office 365 ATP](../office-365-security/office-365-atp.md)
- [Panoramica di Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [Panoramica di Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [Archiviazione dei dati di Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
