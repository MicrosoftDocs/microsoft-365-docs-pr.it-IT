---
title: Specificare il livello di protezione fornito dal cloud per Antivirus Microsoft Defender
description: Impostare il livello di protezione fornito dal cloud per Antivirus Microsoft Defender.
keywords: Antivirus Microsoft Defender, antimalware, sicurezza, difensore, cloud, aggressività, livello di protezione
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.date: 10/26/2020
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.openlocfilehash: f441b1bd444cd70fb5b00dfcb5ebcddadf62b220
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274905"
---
# <a name="specify-the-cloud-delivered-protection-level"></a>Specificare il livello di protezione fornita dal cloud

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**

- [Microsoft Defender per endpoint](/microsoft-365/security/defender-endpoint/)

Puoi specificare il livello di protezione offerto dal cloud offerto da Antivirus Microsoft Defender usando Microsoft Endpoint Manager (scelta consigliata) o Criteri di gruppo.

> [!TIP]
> La protezione cloud non è semplicemente la protezione per i file archiviati nel cloud. Il Antivirus Microsoft Defender cloud è un meccanismo per fornire una protezione aggiornata alla rete e ai dispositivi (denominati anche endpoint). La protezione cloud con Antivirus Microsoft Defender risorse distribuite e l'apprendimento automatico per fornire protezione agli endpoint a una velocità molto più veloce rispetto agli aggiornamenti tradizionali di intelligence per la sicurezza. Microsoft Intune e Microsoft Endpoint Manager ora fanno parte di [Microsoft Endpoint Manager](/mem/endpoint-manager-overview). 


## <a name="use-microsoft-endpoint-manager-to-specify-the-level-of-cloud-delivered-protection"></a>Usare Microsoft Endpoint Manager per specificare il livello di protezione fornito dal cloud

1. Accedere all'Microsoft Endpoint Manager di amministrazione ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) e accedere.

2. Scegliere **Endpoint security**  >  **Antivirus**.

3. Selezionare un profilo antivirus. Se non ne hai ancora uno o se vuoi creare un nuovo profilo, vedi Configurare le impostazioni di restrizione dei dispositivi [in Microsoft Intune](/intune/device-restrictions-configure).

4. Selezionare **Proprietà**. Quindi, accanto a **Impostazioni di configurazione** scegliere **Modifica.**

5. Espandere **Protezione cloud** e  quindi selezionare una delle opzioni seguenti nell'elenco Livello di protezione fornito dal cloud:

    1. **High**: applica un livello elevato di rilevamento.
    2. **High plus**: usa **il livello High** e applica misure di protezione aggiuntive (potrebbe influire sulle prestazioni del client).
    3. **Tolleranza zero:** blocca tutti i file eseguibili sconosciuti.

6. Scegliere **Rivedi e salva** e quindi Salva.  

> [!TIP]
> Serve aiuto? Vedere le risorse seguenti:
> - [Configurare Endpoint Protection](/mem/configmgr/protect/deploy-use/endpoint-protection-configure)
> - [Aggiungere le impostazioni di endpoint protection in Intune](/mem/intune/protect/endpoint-protection-configure)
  

## <a name="use-group-policy-to-specify-the-level-of-cloud-delivered-protection"></a>Usare Criteri di gruppo per specificare il livello di protezione fornito dal cloud

1.  Nel computer di gestione di Criteri di gruppo aprire Console [Gestione Criteri di gruppo.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))

2. Fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e quindi scegliere **Modifica**.

3.  **Nell'Editor Gestione Criteri di gruppo** passare a Configurazione **computer**  >  **Modelli amministrativi.**

4.  Espandere l'albero per **Windows componenti**  >  **Antivirus Microsoft Defender**  >  **MpEngine**.

5.  Fare doppio clic **sull'impostazione Seleziona** livello di protezione cloud e impostarla su **Abilitato.** Selezionare il livello di protezione:
    - **Il livello di blocco predefinito** offre un rilevamento sicuro senza aumentare il rischio di rilevare file legittimi.
    - **Il livello di blocco moderato** fornisce un livello moderato solo per i rilevamenti di probabilità elevata
    - **Un livello di blocco elevato** applica un livello elevato di rilevamento ottimizzando le prestazioni del client (ma può anche offrire maggiori probabilità di falsi positivi).
    - **Il livello alto e di** blocco applica misure di protezione aggiuntive (potrebbe influire sulle prestazioni del client e aumentare la probabilità di falsi positivi).
    - **Il livello di blocco della tolleranza zero** blocca tutti i file eseguibili sconosciuti.
    
    > [!WARNING]
    > Sebbene improbabile, l'impostazione di questa opzione su **High** o **High +** potrebbe causare il rilevamento di alcuni file legittimi (anche se si avrà la possibilità di sbloccare o contestare tale rilevamento).

6. Fare clic su **OK**.

7. Distribuire l'oggetto Criteri di gruppo aggiornato. Vedere [Console Gestione Criteri di gruppo](/windows/win32/srvnodes/group-policy)

> [!TIP]
> Si usano oggetti Criteri di gruppo in locale? Scopri come traducono nel cloud. Analizzare gli oggetti Criteri di gruppo [locali usando l'analisi di Criteri](/mem/intune/configuration/group-policy-analytics)di gruppo in Microsoft Endpoint Manager - Anteprima . 
  
## <a name="related-articles"></a>Articoli correlati

- [Antivirus Microsoft Defender in Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Abilitare la protezione basata sul cloud](enable-cloud-protection-microsoft-defender-antivirus.md)
- [Come creare e distribuire criteri antimalware: servizio di protezione cloud](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)