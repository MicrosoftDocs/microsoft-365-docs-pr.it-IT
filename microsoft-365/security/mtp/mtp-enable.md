---
title: Attivare Microsoft 365 Defender nel Centro sicurezza Microsoft 365
description: Informazioni su come abilitare Microsoft 365 Defender e iniziare a integrare l'incidente di sicurezza e la risposta.
keywords: introduzione, abilitare MTP, Microsoft Threat Protection, M365, sicurezza, posizione dei dati, autorizzazioni necessarie, idoneità alle licenze, pagina impostazioni
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 19f035a271626077911b05082a4aba6d67355cdb
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930223"
---
# <a name="turn-on-microsoft-365-defender"></a>Attivare Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender

[Microsoft 365 Defender](microsoft-threat-protection.md) unifica il processo di risposta agli incidenti integrando le principali funzionalità tra Microsoft Defender per Endpoint, Microsoft Defender per Office 365, Microsoft Cloud App Security e Microsoft Defender for Identity. Questa esperienza unificata aggiunge importanti funzionalità alle quali è possibile accedere nel Centro sicurezza Microsoft 365.

Microsoft 365 Defender si attiva automaticamente quando i clienti idonei con le autorizzazioni necessarie visitano il Centro sicurezza Microsoft 365. Leggere questo articolo per comprendere i diversi prerequisiti e come viene eseguito il provisioning di Microsoft 365 Defender.

## <a name="check-license-eligibility-and-required-permissions"></a>Verificare l'idoneità delle licenze e le autorizzazioni necessarie

Una licenza per un prodotto di sicurezza di Microsoft 365 in genere consente di usare Microsoft 365 Defender nel Centro sicurezza Microsoft 365 senza costi di licenza aggiuntivi. È consigliabile ottenere una licenza di Microsoft 365 E5, E5 Security, A5 o A5 Security o una combinazione valida di licenze che fornisce l'accesso a tutti i servizi supportati.

Per informazioni dettagliate sulle licenze, [leggere i requisiti di licenza.](prerequisites.md#licensing-requirements)

### <a name="check-your-role"></a>Controllare il ruolo

Per attivare  Microsoft 365 Defender, è necessario essere un amministratore globale o un amministratore della sicurezza **in** Azure Active Directory. [Visualizzare i ruoli in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a>Servizi supportati

Microsoft 365 Defender aggrega i dati dei vari servizi supportati già distribuiti. I dati verranno elaborati e archiviati centralmente per identificare nuove informazioni dettagliate e rendere possibili flussi di lavoro di risposta centralizzati. Questa operazione non influisce sulle distribuzioni, le impostazioni o i dati esistenti associati ai servizi integrati.

Per ottenere la migliore protezione e ottimizzare Microsoft 365 Defender, è consigliabile distribuire tutti i servizi supportati applicabili nella rete. Per ulteriori informazioni, [vedere Distribuzione dei servizi supportati .](deploy-supported-services.md)

## <a name="before-starting-the-service"></a>Prima di avviare il servizio

Prima di attivare il servizio, il Centro sicurezza Microsoft 365 ([security.microsoft.com](https://security.microsoft.com)) mostra la pagina delle impostazioni di  Microsoft 365 Defender quando si seleziona Eventi imprevisti, Centro notifiche o Ricerca nel riquadro di spostamento. Questi elementi di spostamento non vengono visualizzati se non si è idonei a usare Microsoft 365 Defender.

![Immagine della pagina delle impostazioni di Microsoft 365 Defender visualizzata se Microsoft 365 Defender non è stato attivato nelle impostazioni di ](../../media/mtp-enable/mtp-settings.png)
 *Microsoft 365 Defender nel Centro sicurezza Microsoft 365*

## <a name="starting-the-service"></a>Avvio del servizio

Per attivare Microsoft 365 Defender, è sufficiente selezionare **Attiva Microsoft 365 Defender** e applicare la modifica. È anche possibile accedere a questa opzione selezionando Impostazioni **(** [security.microsoft.com/settings](https://security.microsoft.com/settings)) nel riquadro di spostamento e quindi selezionando **Microsoft 365 Defender.**

> [!NOTE]
> Se non vedi Impostazioni **nel** riquadro di spostamento o non hai potuto accedere alla pagina, controlla le autorizzazioni e le licenze.

### <a name="data-center-location"></a>Posizione del data center

Microsoft 365 Defender archivierà ed eelaborare i dati nella stessa posizione usata [da Microsoft Defender per Endpoint.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy) Se non si dispone di Microsoft Defender per Endpoint, viene selezionata automaticamente una nuova posizione del data center in base alla posizione dei servizi di sicurezza di Microsoft 365 attivi. La posizione del data center selezionato viene visualizzata sullo schermo.

Select **Need help?** in the Microsoft 365 security center to contact Microsoft support about provisioning Microsoft 365 Defender in a different data center location.

> [!NOTE]
> Microsoft Defender for Endpoint effettua automaticamente il provisioning nei data center dell'Unione Europea (UE) quando è attivato tramite Azure Defender. Microsoft 365 Defender eseguirà automaticamente il provisioning nello stesso data center dell'Unione Europea per i clienti che hanno effettuato il provisioning di Defender per Endpoint in questo modo.

### <a name="confirm-that-the-service-is-on"></a>Verificare che il servizio sia attivo

Dopo aver eseguito il provisioning il servizio aggiunge:

- [Gestione degli eventi imprevisti](incidents-overview.md)
- Un centro operativo per la gestione delle [analisi e risposte automatiche](mtp-autoir.md)
- [Funzionalità di ricerca](advanced-hunting-overview.md) avanzate

![Immagine del riquadro di spostamento del Centro sicurezza Microsoft 365 con il Centro sicurezza Microsoft 365 Defender con gestione degli eventi imprevisti e altre funzionalità di ](../../media/mtp-enable/mtp-on.png)
 *Microsoft 365 Defender*

### <a name="getting-microsoft-defender-for-identity-data"></a>Recupero dei dati di Microsoft Defender for Identity

Per condividere i dati di Microsoft Defender for Identity con Microsoft 365 Defender, verificare che l'integrazione di Microsoft Cloud App Security e Microsoft Defender for Identity sia attivata. [Ulteriori informazioni su questa integrazione.](https://docs.microsoft.com/cloud-app-security/mdi-integration)

## <a name="get-assistance"></a>Ottenere assistenza

Per ottenere risposte alle domande più frequenti sull'attivazione di Microsoft 365 Defender, [leggere le domande frequenti.](mtp-enable-faq.md)

Il personale di supporto Microsoft può aiutare a eseguire il provisioning o il deprovisioning del servizio e delle risorse correlate nel tenant. Per assistenza, selezionare **Serve aiuto?** nel Centro sicurezza Microsoft 365. Quando si contatta il supporto tecnico, menzionare Microsoft 365 Defender.

## <a name="related-topics"></a>Argomenti correlati

- [Domande frequenti](mtp-enable-faq.md)
- [Requisiti relativi alle licenze e altri prerequisiti](prerequisites.md)
- [Distribuire i servizi supportati](deploy-supported-services.md)
- [Panoramica di Microsoft 365 Defender](microsoft-threat-protection.md)
- [Panoramica di Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [Panoramica di Defender per Office 365](../office-365-security/office-365-atp.md)
- [Panoramica di Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [Panoramica di Microsoft Defender for Identity](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
- [Microsoft Defender per l'archiviazione dei dati degli endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
