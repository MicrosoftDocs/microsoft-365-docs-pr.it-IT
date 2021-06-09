---
title: Report sull'integrità e la conformità dei dispositivi in Microsoft Defender for Endpoint
description: Tenere traccia dei rilevamenti dello stato di integrità dei dispositivi, dello stato antivirus, della piattaforma del sistema operativo e delle Windows 10 usando il report di conformità e integrità del dispositivo
keywords: stato di integrità, antivirus, piattaforma del sistema operativo, versione di Windows 10, versione, integrità, conformità, stato
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 35100a4b8bdaee23c427816450e948ced9ed3191
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2021
ms.locfileid: "51860292"
---
# <a name="device-health-and-compliance-report-in-microsoft-defender-for-endpoint"></a>Report sull'integrità e la conformità dei dispositivi in Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Vuoi provare Microsoft Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Il rapporto sullo stato dei dispositivi fornisce informazioni di alto livello sui dispositivi dell'organizzazione. Il report include informazioni sulle tendenze che mostrano lo stato di integrità del sensore, lo stato antivirus, le piattaforme del sistema operativo e Windows 10 versioni.

Il dashboard è strutturato in due sezioni: ![ Immagine del report del dispositivo](images/device-reports.png)
 
Sezione | Descrizione
:---|:---
1 | Tendenze dei dispositivi
2 | Riepilogo dispositivo (giorno corrente)
 
 
## <a name="device-trends"></a>Tendenze dei dispositivi 
Per impostazione predefinita, le tendenze dei dispositivi visualizzano le informazioni sul dispositivo del periodo di 30 giorni che termina con l'ultimo giorno completo. Per ottenere una prospettiva migliore sulle tendenze che si verificano nell'organizzazione, è possibile ottimizzare il periodo di reporting modificando il periodo di tempo visualizzato. Per regolare il periodo di tempo, selezionare un intervallo di tempo dalle opzioni a discesa:
 
- 30 giorni
- 3 mesi
- 6 mesi
- Personalizzato

>[!NOTE]
>Questi filtri vengono applicati solo nella sezione tendenze del dispositivo. Non influisce sulla sezione di riepilogo del dispositivo.

## <a name="device-summary"></a>Riepilogo dei dispositivi 
Mentre le tendenze dei dispositivi mostrano informazioni sui dispositivi di tendenza, il riepilogo dei dispositivi mostra le informazioni sul dispositivo nell'ambito del giorno corrente. 

>[!NOTE]
>L'ambito dei dati visualizzati nella sezione di riepilogo è 180 giorni prima della data corrente. Ad esempio, se la data odierna è il 27 marzo 2019, i dati nella sezione di riepilogo rifletteranno i numeri a partire dal 28 settembre 2018 al 27 marzo 2019.<br>
> Il filtro applicato alla sezione tendenze non viene applicato alla sezione di riepilogo. 
 
La sezione tendenze dei dispositivi consente di eseguire il drill-down nell'elenco dei dispositivi con il filtro corrispondente applicato. Ad esempio, facendo clic sulla barra Inattiva nella scheda Stato di integrità sensore verrà visualizzato l'elenco dei dispositivi con risultati che mostrano solo i dispositivi il cui stato del sensore è inattivo. 
 
 
 
## <a name="device-attributes"></a>Attributi del dispositivo
Il report è costituito da schede che visualizzano gli attributi del dispositivo seguenti:
 
- **Stato di** integrità : mostra informazioni sullo stato del sensore nei dispositivi, fornendo una visualizzazione aggregata dei dispositivi attivi, con comunicazioni compromesse, inattive o in cui non vengono visualizzati dati del sensore.
  
- **Stato antivirus per i dispositivi Windows 10**: mostra il numero di dispositivi e lo stato di Antivirus Microsoft Defender.
    
- **Piattaforme del sistema operativo**: mostra la distribuzione delle piattaforme del sistema operativo esistenti all'interno dell'organizzazione. 
 
- **Windows 10:** mostra la distribuzione dei dispositivi Windows 10 e delle relative versioni nell'organizzazione.
 
 
 
## <a name="filter-data"></a>Filtrare i dati
 
Usa i filtri forniti per includere o escludere i dispositivi con determinati attributi.

Puoi selezionare più filtri da applicare dagli attributi del dispositivo. 
 
>[!NOTE]
>Questi filtri si **applicano a** tutte le schede del report.
 
Ad esempio, per visualizzare i dati sui dispositivi Windows 10 con stato di integrità del sensore attivo:
 
1. In **Filtri > stato di integrità sensore > Attivo**.
2. Seleziona quindi **Piattaforme del sistema operativo > Windows 10**.
3. Selezionare **Applica**.


## <a name="related-topic"></a>Argomento correlato
- [Report di protezione dalle minacce](threat-protection-reports.md)
