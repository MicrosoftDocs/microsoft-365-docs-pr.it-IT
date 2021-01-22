---
title: Strumento di verifica della preparazione scaricabile
description: Controlla le impostazioni del dispositivo e della rete, inclusi gli endpoint necessari
keywords: Microsoft Managed Desktop, Microsoft 365, servizi, documentazione
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 2080b2fc924320f38d9972c82c0425fa1d8026e7
ms.sourcegitcommit: 7ecd10b302b3b3dfa4ba3be3a6986dd3c189fbff
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/21/2021
ms.locfileid: "49922022"
---
# <a name="downloadable-readiness-assessment-checker"></a>Strumento di verifica della preparazione scaricabile

Per funzionare correttamente con Microsoft Managed Desktop, i dispositivi devono soddisfare determinati requisiti hardware e impostazioni. Inoltre, ogni dispositivo deve essere in grado di raggiungere gli endpoint chiave. Scaricare ed eseguire questo strumento per ottenere un report HTML, visualizzare i risultati e quindi eseguire un'azione. Dovrai scaricare lo strumento e i file di supporto e quindi eseguirlo manualmente in ogni dispositivo che vuoi registrare in Microsoft Managed Desktop.

Per ogni controllo, lo strumento segnala uno dei tre possibili risultati:


|Risultato  |Significato  |
|---------|---------|
|Pronto     | Non è necessaria alcuna azione prima di completare la registrazione.        |
|Avviso    | Seguire i passaggi dello strumento per un'esperienza ottimale con la registrazione e per gli utenti. È *possibile* completare la registrazione, ma è necessario risolvere questi problemi prima di distribuire il primo dispositivo.        |
|Non pronto | *La registrazione avrà esito* negativo se questi problemi non vengono risolti. Seguire i passaggi dello strumento per risolverli.        |

## <a name="obtain-the-checker"></a>Ottenere lo verifica

Scaricare il file ZIP da https://aka.ms/mmddratoolv0 .

> [!NOTE]
> L'utente che esegue lo strumento deve disporre dei diritti di amministratore locale nel dispositivo in cui lo esegue.

 Eseguire quindi lo strumento seguendo questi passaggi:

1. Copia il file ZIP scaricato in ogni dispositivo che vuoi controllare.
2. Estrarre tutti i file nel download compresso.
3. Eseguire **Microsoft.MMD.DeviceReadinessAssessmentTool.exe**.
4. Quando viene visualizzata la richiesta di controllo di accesso utente, selezionare **Sì.** Lo strumento viene eseguito e apre un report nel browser predefinito.

Puoi anche scaricare ed estrarre l'archivio ZIP  in un percorso condiviso, accedereMicrosoft.MMD.DeviceReadinessAssessmentTool.exeda ogni dispositivo e quindi eseguirlo localmente.


## <a name="checks"></a>Controlli

Lo strumento scaricabile controlla questi elementi correlati al dispositivo e alla rete:

### <a name="hardware"></a>Hardware

I dispositivi devono soddisfare requisiti hardware specifici per funzionare con Microsoft Managed Desktop. Attualmente, solo dispositivi [approvati specifici](../service-description/device-list.md) sono autorizzati a registrarsi. 

Se il dispositivo non supera uno dei controlli, non è compatibile con Microsoft Managed Desktop.

### <a name="network-endpoints"></a>Endpoint di rete

I dispositivi sono in grado di raggiungere diversi [endpoint chiave](network.md) per funzionare con Microsoft Managed Desktop.

Se lo strumento segnala **un risultato** Non pronto, vedi il report dettagliato per scoprire quali endpoint non erano raggiungibili. Regola quindi il firewall o altre impostazioni di rete per assicurarti che tali endpoint possano essere raggiunti.

### <a name="other-settings"></a>Altre impostazioni

#### <a name="enterprise-wi-fi-profiles"></a>Profili Wi-Fi aziendali

Un **risultato di avviso** indica che stai usando alcuni profili Wi-Fi che necessitano di certificati e profili per funzionare correttamente. Per altre informazioni, vedi [Distribuire certificati e profilo Wi-Fi/VPN.](certs-wifi-lan.md#deploy-certificates-and-wi-fivpn-profile)

#### <a name="lan-profiles"></a>Profili LAN

Un **risultato di avviso** indica che sono disponibili LAN che necessitano di certificati e profili per funzionare correttamente. Per ulteriori informazioni, vedere [Preparare certificati e profili di rete per Microsoft Managed Desktop.](certs-wifi-lan.md)

#### <a name="vpn-profiles"></a>Profili VPN

Un **risultato di** avviso indica che stai usando una rete privata virtuale (VPN). Creare un profilo VPN che distribuisca i certificati integrati con Microsoft Intune. Per ulteriori informazioni, vedere [Preparare certificati e profili di rete per Microsoft Managed Desktop.](certs-wifi-lan.md)

#### <a name="mapped-drives"></a>Unità mappate

Un **risultato di avviso** indica che alcune unità mappate non sono consigliate. Per ulteriori informazioni, vedere [Preparare le unità mappate per Microsoft Managed Desktop.](mapped-drives.md)

#### <a name="print-queues"></a>Code di stampa

Un **risultato di avviso** indica che si dispone di alcune code di stampa in sospeso, che non sono consigliate. Una soluzione consiste nell'usare la stampa cloud. Per ulteriori informazioni, vedere [Preparare le risorse di stampa per Microsoft Managed Desktop.](printing.md)

#### <a name="proxies"></a>Proxy

Un **risultato di avviso** indica che è in uso un server proxy. Per ulteriori informazioni, vedere [Configurazione di rete per Microsoft Managed Desktop.](network.md)

