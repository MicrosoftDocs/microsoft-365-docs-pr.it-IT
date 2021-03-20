---
title: Creare un centro contenuti in Microsoft SharePoint Syntex
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Informazioni su come creare un centro contenuti.
ms.openlocfilehash: 34ba45cd62214743e5a6784893e0f24e9815fdfb
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905825"
---
# <a name="create-a-content-center-in-microsoft-sharepoint-syntex"></a>Creare un centro contenuti in Microsoft SharePoint Syntex


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CPSF]

</br>

Per creare e gestire i modelli di analisi del documento, è necessario prima di tutto un centro contenuti. Il centro contenuti è l'interfaccia per la creazione di modelli e include anche informazioni sulle raccolte documenti a cui sono stati applicati i modelli pubblicati.</br>

   ![Selezionare una raccolta documenti](../media/content-understanding/content-center-page.png)</br>

È possibile creare un centro contenuti predefinito durante la [configurazione](set-up-content-understanding.md). Ma un amministratore di SharePoint può anche scegliere di creare altri centri, se necessario. Anche se un singolo centro contenuti può essere utile per gli ambienti in cui si vuole eseguire un rollup di tutte le attività del modello, è consigliabile avere altri centri per più reparti all'interno dell'organizzazione, che possono avere esigenze e requisiti di autorizzazione diversi per i propri modelli.

> [!NOTE]
> In un [ambiente Microsoft 365 Multi-Geo](../enterprise/microsoft-365-multi-geo.md) se si ha un unico centro contenuti predefinito nella posizione centrale, è possibile fornire un roll-up dell'attività del modello solo dall'interno di tale posizione. Attualmente non è possibile ottenere un roll-up dell'attività del modello attraverso i limiti della farm nell'ambiente multi-geografico. 


## <a name="create-a-content-center"></a>Creare un centro contenuti

Un amministratore di SharePoint può creare un sito del centro contenuti come [creerebbe qualsiasi altro sito di SharePoint](/sharepoint/create-site-collection) tramite il pannello di provisioning del sito dell'interfaccia di amministrazione.

Per creare un nuovo centro contenuti:

1. Nell'interfaccia di amministrazione di Microsoft 365, passare all’interfaccia di amministrazione di SharePoint.

2. Nella interfaccia di amministrazione di SharePoint selezionare **Siti attivi** in **Siti**.

3. Nella pagina **Siti attivi** fare clic su **Creare** e quindi selezionare **Altre opzioni**.

4. Nel menu **Scegliere un modello**, selezionare **Centro contenuti**.

5. Per il nuovo sito, fornire un **nome del sito**, un **amministratore principale** e una **lingua**.</br>

   > [!NOTE] 
   > È possibile selezionare un sito del centro contenuti per il rendering in una qualsiasi delle lingue disponibili, ma si noti che attualmente i modelli possono essere creati solo per i file in inglese. Si noti anche che, come altri modelli di sito, la lingua del sito predefinita non è modificabile dopo la creazione del sito.</br>

6. Selezionare **Completato**.
 
Dopo aver creato un sito del centro contenuti, questo verrà elencato nella pagina **Siti attivi** nell'interfaccia di amministrazione di SharePoint. 

### <a name="give-access-to-additional-users"></a>Assegnare l'accesso ad altri utenti
 
Dopo aver creato il sito, è possibile concedere ad altri utenti l'accesso al sito tramite il [modello di autorizzazioni del sito di SharePoint](/sharepoint/modern-experience-sharing-permissions)standard.

## <a name="see-also"></a>Vedere anche
[Creare un classificatore](create-a-classifier.md)

[Creare un estrattore](create-an-extractor.md)

[Creare un centro contenuti](create-a-content-center.md)

[Panoramica sull'analisi dei documenti](document-understanding-overview.md)

[Creare un modello di elaborazione moduli](create-a-form-processing-model.md)

[Applicare un modello](apply-a-model.md)