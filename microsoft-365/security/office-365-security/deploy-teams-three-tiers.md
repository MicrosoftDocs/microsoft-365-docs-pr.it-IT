---
title: Distribuire team per tre livelli di protezione dei file
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_Solutions
ms.assetid: 1e8e3cfd-b878-4088-b941-9940363a5fae
description: Creare e configurare team con Microsoft Teams per diversi livelli di protezione delle informazioni per i file.
ms.openlocfilehash: d8912900a02149d198222a4402e101b0dce53310
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43637641"
---
# <a name="deploy-teams-for-three-tiers-of-protection-for-files"></a>Distribuire team per tre livelli di protezione dei file

Usare i passaggi descritti in questo articolo per progettare e implementare team di base, sensibili ed estremamente riservati. Per ulteriori informazioni su questi tre livelli di protezione, vedere [Proteggere i file in Microsoft Teams](secure-files-in-teams.md).

## <a name="baseline-teams"></a>Team di base

La protezione di base include team pubblici e privati. I team pubblici possono essere individuati e usati da chiunque nell'organizzazione. I siti privati possono essere individuati e sono accessibili solo dai membri del gruppo Microsoft 365 associato al team. Entrambi questi tipi di team consentono ai membri di condividere il sito con altri utenti.

### <a name="public"></a>Pubblico

Seguire le istruzioni disponibili in [questo articolo](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b) per creare un Team di base con autorizzazioni e accesso pubblico.

Questa è la configurazione risultante.

![Protezione di base per un team pubblico.](../../media/baseline-public-team.png)

### <a name="private"></a>Privato

Seguire le istruzioni disponibili in [questo articolo](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b) per creare un Team di base con autorizzazioni e accesso privato.

Questa è la configurazione risultante.

![Protezione di base per un team privato.](../../media/baseline-private-team.png)

## <a name="sensitive-teams"></a>Team sensibili

Per un team sensibile, è possibile iniziare [creando un team privato](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b).

Successivamente, si configura il sito di SharePoint sottostante per impedire la condivisione ai membri del team.

1. Nella barra degli strumenti per il team fare clic su **File**.

2. Fare clic sui puntini di sospensione, quindi selezionare **Apri in SharePoint**.

3. Nella barra degli strumenti del sito di SharePoint sottostante fare clic sull'icona delle impostazioni, quindi su **Autorizzazioni sito**.

4. Nel riquadro **Autorizzazioni sito** fare clic su **Modifica impostazioni di condivisione** in **Impostazioni di condivisione**.

5. In **Impostazioni di condivisione** scegliere **Solo i proprietari del sito possono condividere file, cartelle e il sito**, quindi fare clic su **Salva**.

Di seguito è riportata la configurazione risultante.

![Protezione dati sensibili per un team.](../../media/sensitive-team.png)

## <a name="highly-confidential-teams"></a>Team estremamente riservati

Con un team estremamente riservato, si inizia [creando un team privato](https://support.office.com/article/174adf5f-846b-4780-b765-de1a0a737e2b).

Successivamente, si configura il sito di SharePoint sottostante per impedire la condivisione ai membri del team e la richiesta di accesso per i non membri del team.

1. Nella barra degli strumenti per il team fare clic su **File**.

2. Fare clic sui puntini di sospensione, quindi selezionare **Apri in SharePoint**.

3. Nella barra degli strumenti del sito di SharePoint sottostante fare clic sull'icona delle impostazioni, quindi su **Autorizzazioni sito**.

4. Nel riquadro **Autorizzazioni sito** fare clic su **Modifica impostazioni di condivisione** in **Impostazioni di condivisione**.

5. In **Impostazioni di condivisione** scegliere **Solo i proprietari del sito possono condividere file, cartelle e il sito**.

6. Disattivare **Consenti richieste di accesso** e quindi fare clic su **Salva**.

Di seguito è riportata la configurazione risultante.

![Protezione dati estremamente riservati per un team.](../../media/highly-confidential-team.png)

## <a name="next-step"></a>Passaggio successivo

[Proteggere i file nei team con etichette di conservazione e prevenzione della perdita dei dati](deploy-teams-retention-DLP.md)

## <a name="see-also"></a>Vedere anche

[Proteggere i file in Microsoft Teams](secure-files-in-teams.md)

[Adozione del cloud e soluzioni ibride](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
