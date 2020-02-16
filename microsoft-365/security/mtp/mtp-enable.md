---
title: Attivare Microsoft Threat Protection nel Centro sicurezza Microsoft 365
description: Informazioni su come abilitare Microsoft Threat Protection e iniziare a integrare i problemi di sicurezza e le relative risposte.
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
ms.openlocfilehash: 8f966060ebc9a30166647b397b93f2b45356df74
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42083727"
---
# <a name="turn-on-microsoft-threat-protection"></a>Attivare Microsoft Threat Protection

**Si applica a:**
- Microsoft Threat Protection

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Microsoft Threat Protection unifica il processo di risposta agli eventi imprevisti integrando le funzionalità principali in Microsoft Defender Advanced Threat Protection (ATP), Office 365 ATP, Microsoft Cloud App Security e Azure ATP. Questa esperienza unificata aggiunge importanti funzionalità alle quali è possibile accedere nel Centro sicurezza Microsoft 365.

## <a name="check-license-eligibility-and-required-permissions"></a>Verificare l'idoneità delle licenze e le autorizzazioni necessarie
I clienti con Microsoft 365 E5, Microsoft 365 E5 Security o una combinazione equivalente di licenze possono utilizzare Microsoft Threat Protection. Per altre informazioni [consultare i requisiti di licenza](prerequisites.md#licensing-requirements).

Per abilitare Microsoft Threat Protection, è necessario essere un amministratore **globale** o un **amministratore della sicurezza** in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) .

## <a name="start-using-the-service"></a>Iniziare a usare il servizio
Microsoft Threat Protection aggrega i dati provenienti dai vari servizi integrati. I dati verranno elaborati e archiviati in modo centralizzato per identificare nuove informazioni e rendere possibili flussi di lavoro di risposta centralizzati.

Prima di abilitare il servizio, Microsoft 365 Security Center ([Security.Microsoft.com](https://security.microsoft.com)) non Visualizza gli **eventi** non consentiti e le opzioni del **Centro azioni** nel riquadro di spostamento.

![Immagine del riquadro di spostamento Microsoft 365 Centro sicurezza senza Microsoft Threat Protection](../../media/mtp-off.png)
caratteristiche*Microsoft 365 Security Center con Microsoft Threat Protection disattivata*

Per abilitare Microsoft Threat Protection, selezionare **Impostazioni** nel riquadro di spostamento. Nella **[pagina Impostazioni](https://security.microsoft.com/settings)**, accedere a **Microsoft Threat Protection** > **opt-in/opt-out**.

>[!NOTE]
>Se non si visualizzano le **Impostazioni** nel riquadro di spostamento o non è stato possibile accedere alla pagina, controllare autorizzazioni e licenze.

### <a name="select-data-center-location"></a>Selezionare percorso Data Center
Se è stato eseguito il provisioning di Microsoft Defender ATP per l'organizzazione, i dati verranno archiviati ed elaborati nella stessa area data center selezionata per i [dati di Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy). Se non si dispone di Microsoft Defender ATP, verrà chiesto di scegliere una nuova area data center specifica per Microsoft Threat Protection. 

È necessario fornire il consenso prima che i dati vengano condivisi tra i servizi e aggregati.

### <a name="confirm-that-the-service-is-on"></a>Verificare che il servizio sia attivo
Dopo aver eseguito il provisioning il servizio aggiunge:

- [Gestione degli eventi imprevisti](incidents-overview.md)
- Un centro operativo per la gestione delle [analisi e risposte automatiche](mtp-autoir.md)
- Funzionalità di [ricerca avanzata](advanced-hunting-overview.md) alla pagina **Ricerca** esistente

![Immagine del riquadro di spostamento Microsoft 365 Centro sicurezza con Microsoft Threat Protection](../../media/mtp-on.png)
caratteristiche*Microsoft 365 Security Center con gestione degli incidenti e altre funzionalità di Microsoft Threat Protection*

### <a name="getting-azure-atp-data"></a>Ottenere i dati di Azure ATP
Per condividere i dati di Azure ATP con Microsoft Threat Protection, accertarsi che l'integrazione di Microsoft Cloud App Security e Azure ATP sia attivata. [Altre informazioni sull'integrazione](https://docs.microsoft.com/cloud-app-security/aatp-integration)


## <a name="turn-off-microsoft-threat-protection"></a>Disattivare Microsoft Threat Protection
Per interrompere l'uso del servizio Microsoft Threat Protection, passare a **Impostazioni** > **Microsoft Threat Protection** > ** Consenso esplicito/rifiuto esplicito** nel Centro sicurezza Microsoft 365. Deselezionare **Attiva Microsoft Threat Protection** e salvare le modifiche.

I dati verranno eliminati in modo definitivo e le funzionalità corrispondenti verranno rimosse dal centro sicurezza Microsoft 365.

## <a name="get-assistance"></a>Ottenere assistenza

Il personale del supporto tecnico Microsoft può contribuire a provisionare o deprovisionare il servizio e le risorse correlate sul tenant. Per assistenza, selezionare **serve assistenza?** nel centro sicurezza Microsoft 365. Per contattare il supporto tecnico, fare riferimento a Microsoft Threat Protection.

## <a name="related-topics"></a>Argomenti correlati

- [Panoramica di Microsoft Threat Protection](microsoft-threat-protection.md)
- [Requisiti relativi alle licenze e altri prerequisiti](prerequisites.md)
- [Panoramica di Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [Panoramica di Office 365 ATP](../office-365-security/office-365-atp.md)
- [Panoramica di Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [Panoramica di Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [Archiviazione dei dati di Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
