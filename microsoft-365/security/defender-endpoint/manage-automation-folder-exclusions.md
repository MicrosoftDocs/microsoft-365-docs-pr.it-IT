---
title: Gestire le esclusioni delle cartelle di automazione
description: Aggiungi esclusioni di cartelle di automazione per controllare i file esclusi da un'indagine automatizzata.
keywords: gestire, automazione, esclusione, bloccare, pulire, dannoso
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
ms.openlocfilehash: 37a251acd3b7631cffffaf2eb76bf0f2b4954ee6
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185838"
---
# <a name="manage-automation-folder-exclusions"></a>Gestire le esclusioni delle cartelle di automazione 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-automationexclusionfolder-abovefoldlink)

Le esclusioni delle cartelle di automazione consentono di specificare le cartelle che verranno ignorate dall'analisi automatica. 

È possibile controllare gli attributi seguenti relativi alla cartella che si desidera ignorare:
- Cartelle 
- Estensioni dei file
- Nomi di file


**Cartelle**<br>
È possibile specificare una cartella e le relative sottocartelle da ignorare. 


>[!NOTE]
>Al momento, l'uso di caratteri jolly come modo per escludere i file in una directory non è ancora supportato. 


**Estensioni**<br>
È possibile specificare le estensioni da escludere in una directory specifica. Le estensioni sono un modo per impedire a un utente malintenzionato di usare una cartella esclusa per nascondere un exploit. Le estensioni definiscono in modo esplicito i file da ignorare. 

**Nomi di file**<br>
È possibile specificare i nomi di file che si desidera escludere in una directory specifica. I nomi sono un modo per impedire a un utente malintenzionato di usare una cartella esclusa per nascondere un exploit. I nomi definiscono in modo esplicito i file da ignorare. 



## <a name="add-an-automation-folder-exclusion"></a>Aggiungere un'esclusione di cartella di automazione
1. Nel riquadro di spostamento selezionare **Impostazioni**  >  **Esclusioni cartella automazione**.  

2. Fare **clic su Esclusione nuova cartella.**  

3. Immetti i dettagli della cartella:

    - Cartella
    - Estensioni
    - Nomi di file
    - Descrizione
    

4. Fare clic su **Salva**.

>[!NOTE]
> I comandi di Live Response per raccogliere o esaminare i file esclusi avranno esito negativo con l'errore: "File escluso". Inoltre, le indagini automatizzate ignoreranno gli elementi esclusi.

## <a name="edit-an-automation-folder-exclusion"></a>Modificare l'esclusione di una cartella di automazione 
1. Nel riquadro di spostamento selezionare **Impostazioni**  >  **Esclusioni cartella automazione**. 

2. Fare **clic su** Modifica nell'esclusione della cartella.  

3. Aggiornare i dettagli della regola e fare clic su **Salva.**

## <a name="remove-an-automation-folder-exclusion"></a>Rimuovere un'esclusione di cartelle di automazione 
1. Nel riquadro di spostamento selezionare **Impostazioni**  >  **Esclusioni cartella automazione**.  
2. Fare clic **su Rimuovi esclusione.** 


## <a name="related-topics"></a>Argomenti correlati
- [Gestire gli elenchi di automazione consentiti/bloccati](manage-indicators.md)
- [Gestire i caricamenti di file di automazione](manage-automation-file-uploads.md)
