---
title: Strumento di verifica di valutazione dell’idonietà scaricabile
description: Controlla le impostazioni di dispositivo e di rete, inclusi gli endpoint obbligatori
keywords: Microsoft Managed Desktop, Microsoft 365, servizio, documentazione
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: eec6bdff2e494e0f55b06cb581c5775d3ffeb9e3
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2021
ms.locfileid: "51581035"
---
# <a name="downloadable-readiness-assessment-checker"></a>Strumento di verifica di valutazione dell’idonietà scaricabile

Per funzionare correttamente con Microsoft Managed Desktop, i dispositivi devono soddisfare determinati requisiti per l'hardware e le impostazioni. Inoltre, ogni dispositivo deve essere in grado di raggiungere gli endpoint chiave. Scaricare ed eseguire questo strumento per ottenere un report HTML, visualizzare i risultati e quindi eseguire un'azione. Dovrai scaricare lo strumento e i file di supporto e quindi eseguirlo manualmente in ogni dispositivo che vuoi registrare Microsoft Managed Desktop.

Per ogni controllo, lo strumento segnala uno dei tre possibili risultati:


|Risultato  |Significato  |
|---------|---------|
|Pronto     | Non è necessaria alcuna azione prima di completare la registrazione.        |
|Avviso    | Seguire i passaggi nello strumento per un'esperienza ottimale con la registrazione e per gli utenti. Puoi *completare* la registrazione, ma devi risolvere questi problemi prima di distribuire il primo dispositivo.        |
|Non pronto | *La registrazione avrà esito* negativo se questi problemi non vengono risolti. Segui i passaggi nello strumento per risolverli.        |

## <a name="obtain-the-checker"></a>Ottenere lo correttore

Scaricare il .zip file da https://aka.ms/mmddratoolv0 .

> [!NOTE]
> L'utente che esegue lo strumento deve disporre dei diritti di amministratore locale nel dispositivo in cui è in esecuzione.

 Eseguire quindi lo strumento seguendo questi passaggi:

1. Copia il file .zip scaricato in ogni dispositivo che vuoi controllare.
2. Estrarre tutti i file nel download compresso.
3. Eseguire **Microsoft.MMD.DeviceReadinessAssessmentTool.exe**.
4. Quando viene visualizzato il prompt Controllo di accesso utente, selezionare **Sì**. Lo strumento viene eseguito e apre un report nel browser predefinito.

Puoi anche scaricare ed estrarre l'.zip in un  percorso condiviso, accedereMicrosoft.MMD.DeviceReadinessAssessmentTool.exefile da ogni dispositivo ed eseguirlo in locale.


## <a name="checks"></a>Controlli

Lo strumento scaricabile controlla questi elementi correlati al dispositivo e alla rete:

### <a name="hardware"></a>Hardware

I dispositivi devono soddisfare requisiti hardware specifici per funzionare con Microsoft Managed Desktop. Attualmente, solo specifici [dispositivi approvati](../service-description/device-list.md) sono autorizzati a registrare. 

Se il dispositivo non supera uno dei controlli, non è compatibile con Microsoft Managed Desktop.

### <a name="network-endpoints"></a>Endpoint di rete

I dispositivi sono in grado di raggiungere diversi [endpoint chiave](network.md) per funzionare con Microsoft Managed Desktop.

Se lo strumento segnala un **risultato Non** pronto, vedi il report dettagliato per scoprire quali endpoint non erano raggiungibili. Regola quindi il firewall o altre impostazioni di rete per assicurarti che tali endpoint possano essere raggiunti.

### <a name="other-settings"></a>Altre impostazioni

#### <a name="enterprise-wi-fi-profiles"></a>Enterprise profili Wi-Fi

Un **risultato di advisory** significa che stai usando alcuni profili Wi-Fi che necessitano di certificati e profili per funzionare correttamente. Per altre informazioni, vedi [Distribuire certificati e profilo Wi-Fi/VPN.](certs-wifi-lan.md#deploy-certificates-and-wi-fivpn-profile)

#### <a name="lan-profiles"></a>Profili LAN

Un **risultato di advisory** indica che sono disponibili reti LAN che necessitano di certificati e profili per funzionare correttamente. Per ulteriori informazioni, vedere [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).

#### <a name="vpn-profiles"></a>Profili VPN

Un **risultato di** advisory indica che stai usando una rete privata virtuale (VPN). Creare un profilo VPN che distribuisca i certificati integrati con Microsoft Intune. Per ulteriori informazioni, vedere [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).

#### <a name="mapped-drives"></a>Unità mappate

Un **risultato di advisory** indica che sono disponibili alcune unità mappate, che non sono consigliate. Per ulteriori informazioni, vedere [Prepare mapped drives for Microsoft Managed Desktop](mapped-drives.md).

#### <a name="print-queues"></a>Code di stampa

Un **risultato di advisory** indica che sono disponibili alcune code di stampa in sospeso, che non sono consigliate. Una soluzione consiste nell'usare la stampa cloud. Per ulteriori informazioni, vedere [Prepare printing resources for Microsoft Managed Desktop](printing.md).

#### <a name="proxies"></a>Proxy

Un **risultato di advisory** indica che è in uso un server proxy. Per ulteriori informazioni, vedere [Configurazione di rete per Microsoft Managed Desktop](network.md).

