---
title: Gestire i caricamenti di file di automazione
description: Abilitare l'analisi del contenuto e configurare l'estensione di file e le estensioni degli allegati di posta elettronica che verranno inviate per l'analisi
keywords: automazione, file, caricamenti, contenuto, analisi, file, estensione, posta elettronica, allegato
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
ms.openlocfilehash: 72405ad7500bf5d672f66ea64634e60c29ad1704
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51068874"
---
# <a name="manage-automation-file-uploads"></a>Gestire i caricamenti di file di automazione

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Si applica a:**
- [Microsoft Defender ATP](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-automationefileuploads-abovefoldlink)

Abilita la funzionalità di analisi del contenuto in modo che determinati file e allegati di posta elettronica possano essere caricati automaticamente nel cloud per un'ulteriore ispezione nell'indagine automatizzata.

Identificare i file e gli allegati di posta elettronica specificando i nomi delle estensioni di file e i nomi delle estensioni degli allegati di posta elettronica. 

Ad esempio, se si aggiungono *exe* e *bat* come nomi di estensione di file o allegati, tutti i file o gli allegati con tali estensioni verranno inviati automaticamente al cloud per un'ulteriore ispezione durante l'indagine automatizzata. 

## <a name="add-file-extension-names-and-attachment-extension-names"></a>Aggiungere i nomi delle estensioni di file e i nomi delle estensioni degli allegati.

1. Nel riquadro di spostamento selezionare **Impostazioni**  >  **Caricamenti file di automazione**. 

2. Attiva e disattiva l'impostazione **di** analisi **del contenuto.**

3. Configurare i nomi di estensione seguenti e separare i nomi delle estensioni con una virgola:
   - **Nomi delle estensioni di file:** i file sospetti, ad eccezione degli allegati di posta elettronica, verranno inviati per un'ulteriore ispezione
  

## <a name="related-topics"></a>Argomenti correlati
- [Gestire le esclusioni delle cartelle di automazione](manage-automation-folder-exclusions.md)
