---
title: Utilizzare le query condivise in Microsoft 365 Defender Advanced Hunting
description: Avviare subito la ricerca delle minacce con query predefinite e condivise. Condividere le query con il pubblico o la propria organizzazione.
keywords: caccia avanzata, caccia alle minacce, Cyber Threat Hunting, Microsoft Threat Protection, Microsoft 365, MTP, M365, Search, query, telemetria, rilevamenti personalizzati, schema, kusto, GitHub repo, My Querys, Shared queries
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 48da1a3a64926f44582e7872f0b0ee03240409ca
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844081"
---
# <a name="use-shared-queries-in-advanced-hunting"></a>Usare le query condivise nella ricerca avanzata

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Si applica a:**
- Microsoft 365 Defender



[Le query Ricerca avanzata](advanced-hunting-overview.md) possono essere condivise tra con gli utenti della stessa organizzazione. È anche possibile trovare query condivise pubblicamente su GitHub. Queste query consentono di intraprendere rapidamente specifici scenari di ricerca delle minacce senza dover scrivere le query da zero.

![Immagine di query condivise](../../media/advanced-hunting-shared-queries.png)

## <a name="save-modify-and-share-a-query"></a>Salvare, modificare e condividere una query
È possibile salvare una query nuova o esistente in modo che sia solo accessibile all'utente o condivisa con altri utenti della propria organizzazione. 

1. Creare o modificare una query. 

2. Fare clic sul pulsante a discesa **Salva query** e selezionare **Salva con nome**.
    
3. Immettere un nome per la query. 

   ![Immagine del salvataggio di una query](../../media/advanced-hunting-save-query.png)

4. Selezionare la cartella in cui si vuole salvare la query.
    - **Query condivise** : query condivise con tutti gli utenti dell'organizzazione
    - **Query personali** : query accessibili solo all'utente
    
5. Selezionare **Salva**. 

## <a name="delete-or-rename-a-query"></a>Eliminare o rinominare una query
1. Fare clic con il pulsante destro del mouse su una query che si vuole rinominare o eliminare.

    ![Immagine dell'eliminazione di una query](../../media/advanced_hunting_delete_rename.png)

2. Selezionare **Elimina** per confermare l'eliminazione. In alternativa, selezionare **Rinomina** e immettere un nuovo nome per la query.

## <a name="create-a-direct-link-to-a-query"></a>Creare un collegamento diretto a una query
Per generare un collegamento che apra la query direttamente nell'editor di query di ricerca avanzata, finalizzare la query e selezionare **Condividi collegamento**.

## <a name="access-queries-in-the-github-repository"></a>Accedere alle query nel repository GitHub  
I ricercatori della sicurezza Microsoft condividono regolarmente query di ricerca avanzata in un [repository pubblico designato in GitHub](https://aka.ms/hunting-queries). È possibile collaborare a questo repository. Per collaborare, [iscriversi a GitHub gratuitamente](https://github.com/).

>[!tip]
>I ricercatori della sicurezza Microsoft forniscono anche query di ricerca avanzata che è possibile usare per trovare le attività e gli indicatori associati alle minacce emergenti. Queste query sono incluse nei report di [analisi delle minacce](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/threat-analytics) nel Microsoft Defender Security Center.

## <a name="related-topics"></a>Argomenti correlati
- [Panoramica della ricerca avanzata](advanced-hunting-overview.md)
- [Capire il linguaggio delle query](advanced-hunting-query-language.md)
- [Usare i risultati delle query](advanced-hunting-query-results.md)
- [Cercare tra dispositivi, posta elettronica, app e identità](advanced-hunting-query-emails-devices.md)
- [Comprendere lo schema](advanced-hunting-schema-tables.md)
- [Applicare le procedure consigliate per le query](advanced-hunting-best-practices.md)
